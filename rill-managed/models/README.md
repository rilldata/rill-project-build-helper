## [Last mile ELT](https://docs.rilldata.com/build/models/models-101)

The “last mile” of ELT is where your transformed models become analytics-ready. This is typically where business logic is finalized, fields are cleaned and standardized, and the data is shaped into the form expected by dashboards and downstream consumers.

Rill helps ensure this layer stays reliable by supporting data validation and multiple materialization strategies. These safeguard the accuracy, performance, and stability of your final models.


### [Model Validation](https://docs.rilldata.com/build/models/data-quality-tests)
Model validation lets you assert expectations about your transformed data so issues are caught early—before they reach dashboards.

Common things to validate include:

No unexpected NULLs

Primary key uniqueness

Value ranges (e.g., non-negative revenue)

Allowed category values

Basic row-count checks

Validation rules are defined in your model YAML via the tests: block:
```
tests:
  - name: no_null_customer_id
    condition: "customer_id IS NOT NULL"
```

If a test fails, Rill surfaces the warning in logs during refresh.
(See the official docs for full validation capabilities.)


### [Materialization](https://docs.rilldata.com/build/models/performance#materialization)

Materialization defines how Rill stores the results of a model inside the OLAP engine. This controls both performance and how often data is recomputed.