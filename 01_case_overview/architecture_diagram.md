## Architecture Diagram

```mermaid
flowchart LR
  %% Frontend
  subgraph FE[Frontend]
    NX[Next.js (React, TS)]
    CDN[CDN / Edge Cache]
  end

  NX -- HTTPS --> AGW[API Gateway / BFF]

  %% Backend services (own their data)
  subgraph SVC[Backend Microservices]
    AU[Auth] --> AUDB[(PostgreSQL)]
    UP[User Profile] --> UPDB[(PostgreSQL)]
    CAT[Catalog] --> CADB[(MongoDB)]
    INV[Inventory] --> INDB[(PostgreSQL)]
    CART[Cart] --> CR[(Redis)]
    CHK[Checkout] --> CHKDB[(PostgreSQL)]
    ORD[Orders] --> ORDB[(PostgreSQL)]
    PAY[Payments] --> PAYDB[(PostgreSQL)]
    SHP[Shipping] --> SHPDB[(PostgreSQL)]
    SRCH[Search API] --> ES[(Elasticsearch)]
    NOTIF[Notifications] --> NODB[(PostgreSQL)]
  end

  %% Event bus for async flows
  subgraph BUS[Event Bus]
    KAF[Kafka / SNS+SQS]
  end

  %% Object storage for assets
  OBJ[(Object Storage: S3/GCS)]
  MDS[(Media: images/videos)]
  MDS --- OBJ
  NX --- CDN
  CDN --- OBJ

  %% Calls
  NX --> SRCH
  AGW --> AU
  AGW --> UP
  AGW --> CAT
  AGW --> CART
  AGW --> CHK
  CHK --> INV
  CHK --> ORD
  CHK --> PAY
  ORD --> SHP
  SRCH --> ES

  %% Events
  ORD -- OrderCreated/OrderPaid --> KAF
  PAY -- PaymentAuthorized/Failed --> KAF
  INV -- InventoryReserved/Released --> KAF
  SHP -- ShipmentCreated --> KAF
  KAF -- reindex --> SRCH
  KAF -- send emails --> NOTIF
  KAF -- cache invalidation --> CART
