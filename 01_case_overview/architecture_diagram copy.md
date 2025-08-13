## Architecture Diagram

```mermaid
flowchart LR
  subgraph FE[Frontend]
    NX[Nextjs React TS]
    CDN[CDN and Edge Cache]
  end
  NX --> AGW[API Gateway]
  NX --- CDN

  %% Row of user facing services (aligned)
  subgraph EDGE[User Facing Services]
    direction LR
    AU[Auth]
    UP[User Profile]
    CAT[Catalog]
    CART[Cart]
    SRCH[Search API]
    CHK[Checkout]
  end

  %% Core services below
  subgraph CORE[Core Services]
    direction LR
    INV[Inventory]
    ORD[Orders]
    PAY[Payments]
    SHP[Shipping]
    NOTIF[Notifications]
  end

  %% Databases
  AU --> AUDB[(PostgreSQL)]
  UP --> UPDB[(PostgreSQL)]
  CAT --> CADB[(MongoDB)]
  CART --> CR[(Redis)]
  SRCH --> ES[(Elasticsearch)]
  CHK --> CHKDB[(PostgreSQL)]
  INV --> INDB[(PostgreSQL)]
  ORD --> ORDB[(PostgreSQL)]
  PAY --> PAYDB[(PostgreSQL)]
  SHP --> SHPDB[(PostgreSQL)]
  NOTIF --> NODB[(PostgreSQL)]

  %% Calls from gateway to aligned row
  AGW --> AU
  AGW --> UP
  AGW --> CAT
  AGW --> CART
  AGW --> SRCH
  AGW --> CHK

  %% Synchronous calls on checkout path
  CHK --> INV
  CHK --> ORD
  CHK --> PAY
  ORD --> SHP

  %% Object storage and CDN
  OBJ[(Object Storage)]
  CDN --- OBJ

  %% Event bus
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
