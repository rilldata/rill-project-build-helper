## [Alerts](https://docs.rilldata.com/reference/project-files/alerts)

Rill lets you define alerting logic as code by creating *.yaml files with type: alert in your project. These alerts run on a schedule and notify you when certain data conditions or resource states occur. 
docs.rilldata.com

When to Use Alerts

Use alerts for things like:

- Detecting data lag or stalled pipelines
- Notifying on KPI thresholds (e.g., revenue drops)
- Monitoring model refresh issues or error states
- Surface anomalies in production data

You can also create alerts in the UI, but YAML alerts give you full infrastructure-as-code control. 

### Supported data Sources

An alert’s data: can be:

- `SQL` — raw query against your project’s models
- `metrics_sql` — query against a defined metrics view
- `api` — call a custom API defined in your project
- `glob` — file glob matching data in storage
- `resource_status` — alert based on project resource states (e.g., failed models)

## Notification Targets

You can use various built-in notification channels:

- Email — list of email recipients
- Slack — channel IDs or user IDs

```
notify:
  email:
    recipients:
      - "alice@example.com"
  slack:
    channels:
      - "#ops-alerts"
```


- Detecting data lag or stalled pipelines
- Notifying on KPI thresholds (e.g., revenue drops)
- Monitoring model refresh issues or error states
- Surface anomalies in production data

You can also create alerts in the UI, but YAML alerts give you full infrastructure-as-code control. 

### Supported data Sources

An alert’s data: can be:

SQL — raw query against your project’s models

metrics_sql — query against a defined metrics view

api — call a custom API defined in your project

glob — file glob matching data in storage

resource_status — alert based on project resource states (e.g., failed models)