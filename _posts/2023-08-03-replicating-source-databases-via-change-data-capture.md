---
toc: true
toc_label: "Contents"
toc_icon: "file-alt"
title:  "Replicating source databases via change data capture"
last_modified_at: 2023-08-03T14:41:00-01:00
---

This post describes how .

## Status before the migration
### Query based snapshot data extraction
One massive DAG in airflow (orchestration tool)
240 tables
14 databases
data pipeline via Spark
connect to production Databases via jdbc 
upsert data into db_mirror tables 
e.g. db_mirror.catalog__country
mostly full load, big tables incrementally
dedicated history tables in fishfarm DB (trigger-based CDC)
no historization apart from FF

### Why not use audit columns?
data model changes
does not scale for large tables (https://shopify.engineering/capturing-every-change-shopify-sharded-monolith)
no delete operations
multiple changes between polling interval are not captured

## Motivation for moving from batch to streaming
Get rid of history tables in production databases
It’s a infrastructural burden (size, cost, maintenance)
some data has been moved to other DBs anyways (catalog)
Reduce load to production DBs, even if it’s just read-replicas
We enable pot. historization for all streamed tables
Improve SLA, we only load changelogs instead of full snapshot
We’re ready to use streaming applications on production data

## Architecture and design

### Requirements
no downtime
change 100+ downstreams and inform consumers
POC migration of catalog history tables 
db_mirror_dbz pipeline
Reliable
fault-tolerant, monitoring, validation
Scalable
performance, latency, throughput
Maintainable
make it more manageable by setting up 1 DAG per DB

### Architecture of the db_mirror_dbz pipeline

### Reliability

### Scalability

### Enabling Data Historization


## Conclusion/Learnings

## Links
* [Shopify using Debezium for change data capture](https://shopify.engineering/capturing-every-change-shopify-sharded-monolith)
* [Advantages of log based change data capture](https://debezium.io/blog/2018/07/19/advantages-of-log-based-change-data-capture/
)
