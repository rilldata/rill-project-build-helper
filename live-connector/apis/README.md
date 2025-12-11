## [APIs](https://docs.rilldata.com/integrate/custom-api)

Rill lets you define **custom HTTP APIs** as project files so other systems can query your models and metrics programmatically.

- API definitions live in the apis/ folder of your project.
- Each file must set type: api.
- You can back an API with:
  - raw SQL query (sql)
  - a metrics view query (metrics_sql)
  - a file glob, resource status check, or another custom API 


## [API Tokens (Service Tokens)](https://docs.rilldata.com/manage/service-tokens)

To call APIs in Rill Cloud, you must send a bearer token in the Authorization header.

For production use, we recommend service tokens:

- Long-lived, not tied to a human user
- Great for backends, CI/CD, schedulers, and other automated jobs 
docs.rilldata.com
+1

### 1. Create a service + token

Organization-level role:
```
rill service create my-service --org-role admin
```

Project-level role:
```
rill service create my-service \
  --project my-project \
  --project-role viewer
```

The command prints an access token like:
```
Access token: rill_svc_XXXXXXXX
``` 

Store this token in a secrets manager (not in Git).

### 2. Use the token in API calls

```bash
curl "https://api.rilldata.com/v1/organizations/<org>/projects/<project>/runtime/api/<api-name>" \
  -H "Authorization: Bearer rill_svc_XXXXXXXX"
```