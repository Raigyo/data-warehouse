# Data Warehouse - The Ultimate Guide

*February 2024*

> 🔨 Master Data Warehousing, Dimensional Modeling & ETL process. From [Udemy](https://www.udemy.com/course/data-warehouse-the-ultimate-guide), Nikolai Schuler.

* * *

![rimg](_readme_img/datawarehouse.webp)

## Data Warehouse

A data warehouse, or enterprise data warehouse (EDW), is a system that aggregates data from different sources into a single, central, consistent data store to support data analysis, data mining, artificial intelligence (AI), and machine learning. A data warehouse system enables an organization to run powerful analytics on huge volumes  of historical data in ways that a standard database cannot.

### What is a data warehouse ? (DWH)

There are two kinds of data used in a company:

#### 1. Operational data keeping: 

- Receive orders
-  React to complaints
-  Fill up stock

=> Manage daily operations in the company

**OLTP** = Online Transactional Processing

#### 2. Analytical decision making (DWH):

- What's the best category ?
- What can be improved?
- How many sales compared to last month?

=> Evaluate performances

=> Decision making

**OLAP** = Online Analytical Processing

A data warehouse is used for reporting and data anylisis and to make fact-based decisions.

It's used and optimied for analytical purposes.

- User friendly
- Fast query performances
- Enabling data analysis from different sources

![olap-oltp](_readme_img/olap-oltp.png)

#### Goals of data warehouse

- Centralized and consistent location for data
- Data must be accessible fast (query performance)
- User-friendly (easy to understand)
- Must load data consistently and repeatedly (ETL)
- Reporting and data visualization built on top

## ETL (Extract, Transform, Load)

ETL is a process that extracts, transforms, and loads data from multiple sources to a data warehouse or other unified data repository.

First of all, we **extract** the data from different sources.

Then we **transform** the data from all the ressources and integrate them in the same structure.

Finally we **load** the data into our centralized location.

![etl](_readme_img/etl.png)

![etl](_readme_img/etl2.png)

## Business Intelligence (BI)

We create a DWH for Business Intelligence.

BI refers to different strategies, technologies, infrastructures, to create meaningful insights with data analysis.

By data analysis, we hear: 

- Data gathering
- Data storing
- Reporting
- Data visualization
- Data mining
- Predictive analytics

Raw data => Transform => DWH = Meaningful insights / Better decisions

![bi](_readme_img/bi.png)

### Data Lake

Data lake and data warehouse are both used as centralized data storage.

Data lake stores data from different systems, but these are unstructured raw data, using different formats (csv, json, sql, files...) and it's still biga data. The use cases are not or less defined yet.

Data lake is used by data scientists and analysts.

In the data warehouse, data are processed and structured  in a database. The DWH is specific and ready to be used with the main goal in mind. 

Data warehouse is used by business users and IT.

![Data lake vs data warehouse](_readme_img/data-lake.png)

## Data warehouse architecture

### Layers

Data warehouses have several functional layers, each with specific capabilities. The most common data warehouse architecture layers are the source, staging, warehouse, and consumption. 

**Source layer**

The logical layer of all systems of record (SOR) that feed data into the warehouse. They could include point-of-sale, marketing automation, CRM, or ERP systems. Each source SOR has a specific data format and may require a different data capture method based on that data format.

**Staging layer** 

A landing area for data from the source SOR. A data staging best practice is to ingest data from the SOR without applying business logic or transformations. It’s also critical to ensure that staging data is not used in production data analysis; data in the staging area has yet to be cleansed, standardized, modeled, governed, and verified.

Some new / updated data can be added to the DWH. To know what data has been modified or added, we use a delta column, generally the date.

So we can use temporary staging layer (truncated) or persitant one (not truncated).

![Layers](_readme_img/layers1.png)

**Warehouse layer**

The layer where all of the data is stored. The warehouse data is now subject-oriented, integrated, time-variant, and non-volatile. This layer will have the physical schemas, tables, views, stored procedures, and functions needed to access the warehouse-modeled data. This layer is also known as **the single point of truth**.

In real the DWH is composed of three layers : staging, core and data marts (cfr.infra).

![Layers](_readme_img/layers3.png)

**Consumption layer**

Also known as the analytics layer, is where you model data for consumption using analytics tools like ThoughtSpot, data analysts, data scientists, and business users.

![Layers](_readme_img/layers2.png)

### Data marts

A Data Mart focuses on a single functional area of an organisation and contains a subset of the data stored in a data warehouse. A Data Mart is a condensed version of a Data Warehouse and is designed to be used by a specific department, unit or set of users within an organisation. For example, marketing, sales, human resources or finance. It is often controlled by a single department within an organisation. They also can be built for a specific use case.

A data mart generally extracts data from just a few sources, compared with a data warehouse. Data marts are small and more flexible and usable than a data warehouse.

![Layers](_readme_img/datamart.png)

## Useful links

- [What is ETL? (IBM)](https://www.ibm.com/topics/etl)
- [Java](https://www.oracle.com/java/technologies/downloads/#jdk21-windows) (if needed : `SET PENTAHO_JAVA_HOME=C:\Program Files\Java\jdk-21\`)
- [Pentaho Community Edition](https://www.hitachivantara.com/en-us/products/pentaho-plus-platform/data-integration-analytics/pentaho-community-edition.html)
- [PostgreSQL](https://www.postgresql.org/)
- [pgAdmin](https://www.pgadmin.org/download/) (if needed delete : `C:\Users\%USERNAME%\AppData\Roaming\pgAdmin\sessions`)
- [The fundamentals of data warehouse architecture](https://www.thoughtspot.com/data-trends/data-modeling/data-warehouse-architecture)



  
