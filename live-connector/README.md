# [live-connector](https://docs.rilldata.com/build/connectors/olap)
A Rill project demonstrating live data connectors with real-world examples and recommended folder structure.

---

##  Project Structure

The live-connector project structure:

```text
live-connector/
├── connectors/
│   └── clickhouse.yaml
├── dashboards/
│   └── trips_metrics_explore.yaml
├── metrics/
│   └── trips_metrics.yaml
├── alerts/
│   └── project_errors.yaml
├── apis/
│   ├── metrics_sql_api.yaml
│   ├── sql_api.yaml
│   └── status.yaml
├── themes/
│   └── theme.yaml
├── rill.yaml
├── env
└── README.md
```



---

## Key Features

- **Live Data Connectors**: Examples of connecting to ClickHouse and other live data sources
- **Real-time Metrics**: Pre-configured metrics for trips data with live updates
- **Interactive Dashboards**: Trip metrics exploration dashboard with live data visualization
- **APIs**: SQL APIs for programmatic data access
- **Alerts**: Project error monitoring and alerting

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

Your dashboards, metrics, and connector configurations will auto-reload as you modify them.

## Documentation Index

- [Connectors README](./connectors/README.md)
- [Dashboards README](./dashboards/README.md)
- [Metrics README](./metrics/README.md)
- [APIs README](./apis/README.md)
- [Alerts README](./alerts/README.md)