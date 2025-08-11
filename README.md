# data-architecture-learning-hub
This repo aims at setting ground knowledge about Data Architecture to understand the Why rather that the How

```
data-architecture-learning-hub/
│
├── README.md
│
├── 01_case_overview/
│   ├── business_context.md         # goals, KPIs, business processes
│   └── architecture_diagram.md     # high-level diagram + sequence flows
│
├── 02_oltp_layer/                  # Operational side (why & when in each)
│   ├── postgres_core/
│   │   ├── why_and_when.md
│   │   ├── schema.ddl.sql          # DDL for orders, payments, shipments...
│   │   └── seed_data.sql           # small seeds for demos
│   ├── mongodb_catalog/
│   │   ├── why_and_when.md
│   │   └── product_document_examples.json
│   ├── redis_cache/
│   │   └── why_and_when.md
│   └── elasticsearch_search/
│       ├── why_and_when.md
│       └── index_template.json
│
├── 03_data_integration_layer/
│   ├── etl_vs_elt.md
│   ├── change_data_capture.md
│   ├── streaming_vs_batch.md
│   ├── data_quality.md              # SLAs, expectations, tests
│   └── comparison.md                # Choosing ETL vs ELT, batch vs streaming
│
├── 04_olap_and_analytics_layer/
│   ├── olap_concepts.md
│   ├── semantic_layers.md
│   ├── self_service_bi.md
│   └── comparison.md                  # OLAP vs OLTP, BI tool choices
│
├── 05_data_modeling_techniques/
│   ├── kimball_dimensional_modeling.md
│   ├── inmon_cif.md
│   ├── medallion_architecture.md
│   ├── data_vault_modeling.md
│   └── comparison.md               # Choosing Kimball vs Inmon vs Vault vs Medallion
│
├── 06_modern_data_architectures/
│   ├── data_platform.md
│   ├── data_mesh.md
│   ├── data_fabric.md
|   ├── datawarehouse
|   ├── datalake
│   ├── lakehouse_architecture.md
│   ├── case_studies_architecture.md
│   └── comparison.md                  # When to choose Mesh, Fabric, Lakehouse
│
├── 07_system_design_for_data/
│   ├── scaling_data_systems.md
│   ├── designing_data_pipelines.md
│   ├── designing_realtime_systems.md
│   ├── high_availability_and_dr.md
│   ├── cost_optimization.md
│   ├── examples/
│   └── comparison.md                  # Trade-offs in system design choices
│
├── 08_governance_and_security/
│   ├── data_governance.md
│   ├── metadata_management.md
│   ├── access_control.md
│   ├── compliance_and_regulations.md
│   ├── monitoring_and_observability.md
│   └── comparison.md                  # When governance/security decisions differ
│
├── 09_real_world_case_studies/
│   ├── uber_data_platform.md
│   ├── netflix_data_infrastructure.md
│   ├── airbnb_data_engineering.md
│   ├── spotify_data_pipeline.md
│   ├── linkedin_analytics.md
│   └── lessons_learned.md               # Extracting patterns from case studies
│
├── diagrams/
│   ├── png/
│   ├── svg/
│   └── drawio/
│
└── resources/
    ├── references.md
    ├── tools_landscape.md
    └── further_reading.md
```