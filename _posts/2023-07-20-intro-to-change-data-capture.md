---
title:  "Intro to change data capture (CDC)"
last_modified_at: 2023-07-20T14:41:00-01:00
---

## What is Change Data Capture and how is it used?
Change data capture (CDC) is a method of tracking and capturing changes made to a database, typically in real-time or near-real-time. 

In simple terms: capture any data change ideally with low latency.

CDC captures insert, update, and delete operations, and makes the data available in an easily consumable format, such as a stream of change events or a log file. 

This captured data can be used for a variety of purposes, such as data replication, auditing, and real-time analytics. Some database management systems, such as Oracle and SQL Server, have built-in CDC functionality, while others may require third-party tools to enable CDC.

## Use case examples
* Make transactional source data available for analytical datawarehouse (OLTP -> OLAP)
  * Mirror your production data in a data lake or analytics DWH 
* Migrating application data from old to new systems
  * if a microservice environment shifts sometimes the legacy data need to be transferred over
* Integrating data from recent corporate M&A
  * happened to me when I worked at Deposit Solutions / Raisin DS: our company was acquired and we then had to mirror the data to make the available in a unified datawarehouse 
* Integrating data from external suppliers or partners


## What types of change data capture for databases do exist?
There are several different types of change data capture (CDC) for databases. The best method to use depends on the specific requirements and constraints of the application or system.

*Log-based CDC*
* Capture changes by reading the database's transaction log, which contains a record of all changes made to the database. The changes are then for example forwarded to a messaging queue like Kafka.
* Pros
  * Efficient with low overhead
    * CDC and Kafka provide near real-time delivery of data changes 
    * by reading the transaction log we have lower latency and avoid increasing CPU load caused by frequent polling
    * 
  * Accurate: every change to a record is tracked
* Cons
  * requires higher system privileges for access to transaction logs
  * requires expert knowledge in terms of setup (for example Kafka Connect and Kafka for using Debezium)
  * requires a high amount of storage
  * for Debezium to work the tables need to have a primary key

*Query-based CDC*
* Periodically run SQL queries against the database 
  * identify any changes that have occurred since the last query (using audit columns)
  * snapshot of the whole table
* Pros
  * simple setup (SQL queries via JDBC) and requires fewer permissions on DB as you just querying
* Cons
  * less efficient 
    * snapshot type also stores records that haven't changed
    * additional load to the database by frequent querying
  * less accurate
    * if a record changes multiple times between a polling interval, you will only store the latest update to the record and miss previous changes
    * you are not able to track delete operations
  * you need so-called audit columns (`update_timestamp` or `last_modification_timestamp`) in each table you want to track

*Trigger-based CDC*
* Capture changes by using database triggers, which are special type of stored procedures that are automatically executed in response to specific events, such as an insert, update, or delete operation on a table.
* Pros
 * accurate - every change to a record is tracked
* Cons
 * Advanced database knowledge needed to set up
 * Puts additional load on the database, which is not a great design pattern 
 * The additional data stored in the database can become an operational burden soon


*Hybrid CDC* 
This method combines elements of different CDC methods in order to achieve the desired level of granularity or performance.

## Quick summary: 5 advantages of log-based CDC
https://debezium.io/blog/2018/07/19/advantages-of-log-based-change-data-capture/