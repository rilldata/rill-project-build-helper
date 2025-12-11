# Connectors (rill-managed)

Rill connectors are split into two primary categories (described in the top-level README).
This document focuses specifically on data connectors and the `duckdb.yaml` connector.

All connectors in a Rill project must declare:

type: connector

Rill uses this parameter to understand how to interpret the file and how the project should be wired together.

## DuckDB Connector (`duckdb.yaml`)

Every newly created Rill project includes a `duckdb.yaml` file.
This explicitly defines the OLAP engine used by the project.
(Rill defaults to DuckDB even if this file is not present, but adding it makes configuration explicit.)

### Basic Example
```
type: connector
driver: duckdb
# managed: true
# mode: readwrite
```
- managed – Whether Rill manages the lifecycle of the DuckDB instance.
- mode – Controls read/write behavior.

While both values are inferred automatically, exposing them helps clarify project behavior.

## Optional DuckDB Parameters

### init_sql
Run arbitrary DuckSQL statements when the DuckDB engine initializes.

init_sql: >
  INSTALL datasketches FROM community;
  LOAD datasketches;

### path
Specify a file path to an existing DuckDB database.

path: '/path/to/main.db'
