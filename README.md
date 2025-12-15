# rill-project-build-helper
A starter Rill project that includes a recommended folder structure, example files, and guidance for connecting data sources.

---

##  Overview
This repository provides a boilerplate Rill project you can use as a starting point for analytics development. It includes:

- A pre-built folder structure (`models/`, `sources/`, `dashboards/`, `connectors/`, etc.)
- Sample configuration files
- Inline documentation to help you understand how projects are organized
- Guidance for choosing your compute engine and connecting to data

Rill lets you build **real-time dashboards** powered either by its managed embedded OLAP engine (DuckDB or ClickHouse) or by connecting live to external OLAP systems like MotherDuck, ClickHouse, or Druid.

---

## Repository Layout

This repo contains two example project setups, one for each compute mode:
```
rill-project-build-helper/
├── rill-managed/      # Use this for Option A (embedded DuckDB/ClickHouse)
├── live-connector/    # Use this for Option B (Live connect to external OLAP)
└── README.md
```

---

##  Getting Started

### 1. Choose your compute mode
Rill supports two execution models:

#### Option A: Managed Embedded Engine (default)
Rill runs a local managed DuckDB or ClickHouse instance.

Advantages:
- Extremely fast in-memory queries
- Real-time interactions without burdening your warehouse
- Reduced cloud compute costs
- Zero operational overhead

This is the mode used in this project.

#### Option B: Live Connect to an External OLAP Engine
Examples: MotherDuck, ClickHouse, Druid

In this mode, Rill does *not* ingest or store your data — instead it queries your OLAP engine directly.

Advantages:
- Centralized governance
- Leverage an already managed cluster
- Query performance dependent on your OLAP engine

---

## 🙌 Contributing

Feel free to fork, open issues, or submit PRs to improve the project template.
