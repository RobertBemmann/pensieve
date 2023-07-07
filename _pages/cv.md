---
title: "CV Robert Bemmann"
permalink: /cv/
layout: single
author_profile: true
---

_Data Engineer based in Berlin 🇩🇪_ <br>

[Email](mailto:bemmann.data@gmail.com) / [Website](https://robertbemmann.github.io/pensieve/) / [LinkedIn](https://www.linkedin.com/in/robert-bemmann/)

## Engineering Experience

**Senior Data Engineer** @ [Getyourguide](https://www.getyourguide.com/) _(Apr 2020 - Present)_ <br>
Berlin-based online travel agency and online marketplace for tour guides and excursions.
  - Led the design and development of mirroring our production Databases (15, >300 tables, core ETL) via Debezium Change Data Capture streaming technology (DB->Kafka->S3->Spark->DWH), owned project and roadmap end-to-end, cutting landing times by improving the SLA for 1 hour, cutting costs by factor 50, built with Kafka, Spark, Airflow
  - Migrated our self-service BI Tool Looker from Databricks (Spark) to Snowflake, incl. for automated tests via Looker API (shared in [public webinar w/ Snowflake](https://resources.snowflake.com/customer-stories/getyourguide-turning-travel-dreams-into-reality-with-snowflake), [blog article](https://medium.com/tech-getyourguide/migrating-our-self-service-bi-tool-looker-from-hive-apache-spark-to-snowflake-492441bca934) and Berlin data meetup)
  - Redesigned and centralized the architecture and layout of our daily prio1 reports end-to-end via Spark, Snowflake, Airflow and Looker
  - Build an application which enables the monitoring of our orchestration tool Airflow for tasks statistics (landing times) and its dependencies, reducing root cause analysis to seconds
  - Held internal learning session on Spark performance optimizations and shared learning on improvements on how to test our existing self service Spark SQL processing framework
  - Responsible for initial design and event ingestion for our CRM data model (event enrichment from Braze source data as well as building CRM subscriptions from existing events)
  - Building ETLs via Spark (S3 data lake) and enhancing data models (various teams like Finance, CRM, etc.)
  - Main technologies/tools: Apache Spark, Snowflake, Apache Airflow, Looker, Kafka, Terraform
  - Main languages: Python, Scala, SQL

**Data Engineer** @ [Raisin DS](https://www.raisin.com/en/about-raisin/) _(Sep 2014 - Mar 2020)_ <br>
Trailblazer for open banking in the deposits and investments space.
  - Conceptualization and creation of a DWH w/ an integrated data model for Deposit Solutions in Snowflake
  - Creation and maintenance of Savedo-BI-DWH for Data Analysis (PostgreSQL)
  - Automated Job-Scheduling (e.g. Talend, dockerized setup) on AWS-EC2 instance via Cron-Job
  - Aggregation and Import of web traffic, cost and conversion data from various sources (structured RDBMS, semi-structured NoSQL), ELT/ETL via Python and Talend
  - Data modelling through SQL (Postgres, MySQL, Snowflake) and Python
  - Creation, automation and visualization of reports in order to share data internally (tools: Power BI, metabase, Looker)
  - Tag Management of 5 websites (Javascript, all trackers, cookie switch)
  - customised website tracking through Google Analytics (w/ in depth knowledge of data schema of GA)
  - close cooperation w/ operations, sales, CRM, product management and the developers, actively writing tickets for improvement of data products
  - deep involvement in 3 financial audits (providing and explaining relevant data)
  - kicked off data quality assurance concept
  - Conceptualization and creation of the bank invoicing process
  - Advances skills in Python for Data Analysis (Anaconda environment, Spyder IDE, Jupyter Notebooks), e.g. writing web crawler for market analysis

<br>

## Skills & Aptitudes
## Concepts
* Distributed processing
  * Apache Spark (Databricks): partitioning, skew, and spilling to disk
  * Snowflake: micro-partitions and cluster management
* Job orchestration
  * Airflow, CRON
* Infrastructure as code
  * Terraform
* Data lake 
  * Hive / Delta (metadata management) on AWS S3
* Database internals
  * Change data capture via Debezium
* Messaging Queues
  * Apache Kafka
* Data visualization
  * Looker, Metabase, Power BI
* Data compression and serialization
  * Avro, Parquet, JSON

### Programming Languages

| Language    | Familiartity  |
|-------------|---------------|
| Python      | ■ ■ ■ ■ ■     |
| Scala       | ■ ■ ■ ■ □     |
| SQL         | ■ ■ ■ ■ ■     |
| Javascript  | ■ ■ □ □ □     |
| Bash        | ■ ■ □ □ □     |

### Databases
* RDBMS
  * Postgres, MySQL, H2
* Cloud Databases 
  * Snowflake, Hive, BigQuery

### Sports
* 24-year competitive football experience, e.g. Junioren-Bundesliga, snowboarding, scuba diving

### Other interests
* Stock market, future of capitalism (business models and entrepreneurship), economics, money theories

## Education
* 2020 - Udacity
  * [Data Streaming Nanodegree](https://graduation.udacity.com/confirm/73LM999P)
  * Kafka & Spark Streaming
* 2019 - Udacity
  * [Data Science Nanodegree](https://graduation.udacity.com/confirm/SLTPFCMM)
* 2014 - [Munich Business School](https://www.munich-business-school.de/)
  * Master of Arts in International Business
* 2013 - [Fudan University Shanghai](https://www.fudan.edu.cn/en/)
  * Study abroad MBA-Exchange program 
* 2011 - [Chemnitz University of Technology](https://www.tu-chemnitz.de/index.html)
  * Bachelor of Science in Business Administration and Mechanical Engineering


## Internships
* 2014 - Rheingau Founders
  * Venture Capital, Berlin
* 2013 - High-Tech Gründerfonds
  * Venture Capital, Bonn
* 2012 - Deutsche Bank
  * Corporate & Investment Banking, Chemnitz
* 2010 - adidas 
  * Football Footwear, Herzogenaurach
