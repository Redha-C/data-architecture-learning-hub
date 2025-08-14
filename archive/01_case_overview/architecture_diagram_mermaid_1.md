## Architecture Diagram

```mermaid
flowchart LR
  subgraph FE[Frontend]
    NX[Nextjs React TS]
    CDN[CDN and Edge Cache]
  end

  NX --> AGW[API Gateway]

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

  OBJ[(Object Storage)]
  NX --- CDN
  CDN --- OBJ

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

  subgraph BUS[Event Bus]
    KAF[Kafka or SNS SQS]
  end

  ORD -- OrderCreated or OrderPaid --> KAF
  PAY -- PaymentAuthorized or Failed --> KAF
  INV -- InventoryReserved or Released --> KAF
  SHP -- ShipmentCreated --> KAF
  KAF -- Reindex --> SRCH
  KAF -- Send Emails --> NOTIF
  KAF -- Cache Invalidation --> CART
