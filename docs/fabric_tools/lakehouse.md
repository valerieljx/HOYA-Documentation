# Lakehouse

## Interacting with Lakehouses

- **Lakehouse explorer**: This is the main Lakehouse interaction page. You can load data into the Lakehouse, explore data in the Lakehouse using the object explorer, and various other things.
- **Notebooks**: Notebooks can be used to write code to read, transform and write directly to Lakehouse as tables and/or folders.
- **Pipelines**: Data integration tools such as pipeline copy tool to pull data from other sources and land into the Lakehouse can be used.

### Lakehouse Explorer

<figure markdown="span">
  ![Lakehouse Explorer in Fabric (Microsoft, 2025)](../images/lakehouse-overview.gif)
  <figcaption>Lakehouse Explorer in Fabric (Microsoft, 2025)"</figcaption>
</figure>

- **Table Section**: All tables are stored here.
    - Organised and governed to facilitate efficient data processing and analysis.
    - You can select a table to preview, inspect the table schema, access underlying files, and execute various other actions related to the data.

- **Unidentified Area**: Displays folders or files present in the managed area that lack associated tables in SyMS.
    - If this happens when you create new tables: Refresh the 'Unidentified' folder, and the tables should appear under the 'Tables' folder.
    - If unsupported files (e.g.: images, audio) are uploaded to the managed area, they will not be automatically detected and linked to tables.
        - Prompts the user to either remove these files from the managed area or transfer them to the File Section for further processing. 