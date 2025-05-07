# SQL Database

- SQL Database in Microsoft Fabric is a developer-friendly transactional database, based on Azure SQL Database, that allows you to easily create your operational database in Fabric.

- A SQL Database in Fabric uses the same SQL Database Engine as Azure SQL Database.

- SQL Database in Fabric is:

    - The home in Fabric for [OLTP workloads](../general_terminology/data_engineering.md#online-transaction-processing-oltp).

    - Easy to configure and manage.

    - Set up for analytics by automatically replicating the data into OneLake near real time.

    - Integrated with development frameworks and analytics.

    - Based on the underlying technology of Mirroring in Fabric

    - Queried in all the same ways as Azure SQL Database, plus a web-based editor in the Fabric portal.

## Why SQL Database in Fabric?

- Data is accessible from other items in Fabric.

- SQL Database in Fabric creates three items in your Fabric workspace:

    - Data in your SQL database is automatically replicated of into the [OneLake](../terminology/onelake.md) and converted to Parquet, in an analytics-ready format. This enables downstream scenarios like data engineering, data science, and more.

    - A [SQL analytics endpoint](./sql_endpoint.md).

    - A [default semantic model](./semantic_model.md).

## Cross-database Queries

- With the data from your SQL database automatically stored in OneLake, you can write cross-database queries, joining data from other SQL databases, mirrored databases, warehouses, and the SQL analytics endpoint in a T-SQL query.

- All this is currently possible with queries on the SQL analytics endpoint of the SQL database, or lakehouse.

- Below is an example of how to write cross-database queries:

    ```SQL
    SELECT * 
    FROM ContosoWarehouse.dbo.ContosoSalesTable AS Contoso
    INNER JOIN AdventureWorksLT.SalesLT.Affiliation AS Affiliation
    ON Affiliation.AffiliationId = Contoso.RecordTypeID;
    ```

## Creating a SQL Database

1. In the workspace that you wnat to create a SQL Database in, select **+ New Item**.

2. Under **Store Data**, select the **SQL database (preview)** tile.

3. Provide a name for the new database. Select **Create**.

4. When the new database is provisioned, on the **Home** page for the database, notice the **Explorer** pane showing database objects.

5. Under **Build your database**, three useful tiles can help you get your newly created database up and running.

    - **Sample data**: lets you import a sample data into your Empty database.

    - **T-SQL**: gives you a web-editor that can be used to write T-SQL to create database object like schema, tables, views, and more.

    - **Connection strings**: shows the SQL database connection string that is required when you want to connect using SQL Server Management Studio, the mssql extension with Visual Studio Code, or other external tools.

## Creating a Table with T-SQL Queries

1. Open your SQL Database.

2. Select the **New Query** button in the main ribbon.

3. Create the definition of your table in T-SQL with this sample:

    ```SQL
    CREATE TABLE dbo.products ( 
    product_id INT IDENTITY(1000,1) PRIMARY KEY, 
    product_name VARCHAR(256), 
    create_date DATETIME2 
    ) 
    ```

4. Once you have a table design you like, select **Run** in the toolbar of the query window.

5. If the **Object Explorer** is already expanded to show tables, it will automatically refresh to show the new table upon create. If not, expand the tree to see the new table.

## Query the Database

- For lightweight queries where you just want to see the structure of a table, the type of data in the table or even what columns the table has, just select on table's name in the **Object Explorer**. The top 1,000 rows will automatically be returned.

- If you want to write a new query with T-SQL, select the **New Query** button from the toolbar of the query editor.

<div style="display: flex; justify-content: space-between;" markdown="1">

[:material-arrow-left: Warehouse](./warehouse.md){ .md-button }

[Dataflow :material-arrow-right:](./dataflow.md){ .md-button }

</div>