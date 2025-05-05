# Snowflake Schema

- A multi-dimensional dat amodel that is an extension of [star schema](./star_schema.md), where dimension tables are broken down into subdimensions. 

- Commonly used for business intelligence and reporting in OLAP data warehouses, data marts, and relational databases.

- It's called a snowflake schema because its entity-relationship diagram (ERD) looks like a snowflake, as seen below.

    <figure markdown="span">
    ![Snowflake Schema (Databricks)](../images/snowflake-schema-120723_0.png)
    <figcaption>Snowflake Schema (Databricks)</figcaption>
    </figure>

## Snowflake Schema vs. Star Schema

- Like star schemas, snowflake schemas have a central fact table which is connected to multiple dimension tables via foreign keys. However, the main difference is that they are more normalized than star schemas.

- Snowflake schemas offer more storage efficiency, due to their tighter adherence to high normalization standards, but query performance is not as good as with more denormalized data models. Denormalized data models like star schemas have more data redundancy (duplication of data), which makes query performance faster at the cost of duplicated data.