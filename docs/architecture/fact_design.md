# Fact Design

## Fact Table Size

- Fact tables vary in size. THeir size corresponds to the dimensionality, granularity, number of measures, and amount of history.

- In comparison to dimension tables, fact tables are more narrow (fewer columns) but big or even immense in terms of rows (in excess of billions).

## Fact Table Types

### Transaction Fact Tables

- Stores business events or transactions.

- Each row stores facts in terms of dimension keys and measures, and optionally other attributes. 

    - All the data is fully known when inserted, and it never changes.

- Tyoically, transaction fact tables store facts at the lowest possible level of granularity, and they contain measures that are additive across all dimensions. A sales fact table that stores every sales order line is a good example of a transaction fact table.

### Periodic Snapshot Fact Tables

- Stores measurements at a predefined time, or specific intervals.

    - It provides a summary of key metrics or performance indicators over time, and so it's useful for trend analysis and monitoring change over time. 

    - Measures are always semi-additive.

- An inventory fact table is a good example of a periodic snapshot table. It's loaded every day with the end-of-day stock balance of every product.

- Periodic snapshot tables can be used instead of a transaction fact table when recording large volumes of transactions is expensive, and it doesn't support any useful analytic requirement. For example, there might be millions of stock movements in a day (which could be stored in a transaction fact table), but your analysis is only concerned with trends of end-of-day stock levels.

### Accumulating Snapshot Fact Tables

- Stores measurements that accumulate across a well-defined period or workflow.

    - It often records the state of a business process at distinct stages or milestones, which might take days, weeks, or even months to complete.

- A fact row is loaded soon after the first event in a process, and then the row is updated in a predictable sequence every time a milestone event occurs. Updates continue until the process completes.

## Measure Types

- Measures are typically numeric, and commonly additive. However, some measures can't always be added. These measures are categorized as either semi-additive or non-additive.

### Additive Measures

- Can be summed across any dimension.

- E.g.: order quantity and sales revenue are additive measures (providing revenue is recorded for a single currency).

### Semi-additive Measures

- Can be summed across certain dimensions only.

- Some examples:

    - Any measure in a periodic snapshot fact table can't be summed across other time periods. For example, you shouldn't sum the age of an inventory item sampled nightly, but you could sum the age of all inventory items on a shelf, each night.

    - A stock balance measure in an inventory fact table can't be summed across other products.

    - Sales revenue in a sales fact table that has a currency dimension key can't be summed across currencies.

### Non-additive Measures

- Can't be summed across any dimension.

    - E.g.: a temperature reading, which by its nature doesn't make sense to add to other readings.

- Other examples include rates, like unit prices, and ratios. However, it's considered a better practice to store the values used to compute the ratio, which allows the ratio to be calculated if needed. For example, a discount percentage of a sales fact could be stored as a discount amount measure (to be divided by the sales revenue measure). Or, the age of an inventory item on the shelf shouldn't be summed over time, but you might observe a trend in the average age of inventory items.

- While some measures can't be summed, they're still valid measures. They can be aggregated by using count, distinct count, minimum, maximum, average, and others. Also, non-additive measures can become additive when they're used in calculations. For example, unit price multiplied by order quantity produces sales revenue, which is additive.

## Factless Fact Tables

- When a fact table doesn't contain any measure columns.

- A factless fact table typically records events or occurrences, like students attending class. From an analytics perspective, a measurement can be achieved by counting fact rows.

## Aggregate Fact Tables

- Represents a rollup of a base fact table to a lower dimensionality and/or higher granularity. Its purpose is to accelerate query performance for commonly queried dimensions.

<div style="display: flex; justify-content: space-between;" markdown="1">

[:material-arrow-left: Dimension Design](./dimension_design.md){ .md-button }

[Naming Convention :material-arrow-right:](./naming_convention.md){ .md-button }

</div>