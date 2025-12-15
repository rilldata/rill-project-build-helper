# [rill-managed](https://docs.rilldata.com/build/connectors/data-source)
A starter Rill project that includes a recommended folder structure, example files, and guidance for connecting data sources.

---

##  Project Structure

A typical Rill project looks like this:

```text
rill-managed/
├── connectors/
│   └── connector.yaml
├── dashboards/
│   └── sample_dashboard.yaml
├── metrics/
│   └── sample_metrics.yaml
├── models/
│   └── sample_model.sql
├── sources/
│   └── sample_source.yaml
├── rill.yaml
└── README.md
```

Each directory includes starter files with examples you can modify.

---

## ▶️ Running the Project

```bash
curl https://rill.sh | sh
rill start
```

Rill will launch a local development UI at:

```text
http://localhost:9009
```

Your dashboards, sources, and models will auto-reload as you modify them.

## Documentation Index

- [Connectors README](./connectors/README.md)
- [Sources README](./sources/README.md)
- [Models README](./models/README.md)
- [Dashboards README](./dashboards/README.md)