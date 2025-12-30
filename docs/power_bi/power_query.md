# Power Query

## Role of Power Query in the Power BI Stack

Power Query is responsible for **data ingestion and shaping** in Power BI.

It sits **upstream** of the semantic model and is executed:

- During data refresh
- Before data is loaded into the VertiPaq engine

Power Query is not an analytical layer. Its purpose is to ensure that data enters the model in a **clean, consistent, and analysis-ready form**.

> If logic does not depend on user interaction, it likely belongs in Power Query.


## Power Query vs DAX

A common source of confusion is deciding whether logic belongs in Power Query or DAX.

| Task | Power Query | DAX |
|----|------------|-----|
| Data cleaning | ✅ | ❌ |
| Data reshaping | ✅ | ❌ |
| Aggregations | ❌ | ✅ |
| KPIs and ratios | ❌ | ✅ |
| User-driven logic | ❌ | ✅ |
| Refresh-time logic | ✅ | ❌ |

**Design principle:**
> Power Query prepares data; DAX analyzes it.

Placing logic in the wrong layer leads to:

- Performance issues
- Incorrect results
- Reduced maintainability


## Shaping vs Aggregating Data

Power Query should focus on **structure**, not meaning.

### Appropriate Power Query Tasks

- Enforcing data types
- Normalizing schemas
- Splitting or merging columns
- Unpivoting wide tables
- Standardizing naming conventions

### Inappropriate Power Query Tasks

- Business KPIs
- Time intelligence
- Ratios and percentages
- Logic dependent on slicers or filters

Aggregation logic belongs in DAX, where it can respond dynamically to context.

## M Language Overview (Conceptual)

Power Query uses the **M language**, a functional, step-based language.

Key characteristics:

- Each step produces a new table
- Steps are evaluated sequentially
- Transformations are immutable
- Evaluation occurs during refresh

Understanding M syntax is less important than understanding **what transformations do and when they execute**.

## Common Transformations

### Data Type Enforcement

Explicitly setting data types:

- Improves reliability
- Prevents silent conversion errors
- Enables better compression downstream

Data types should be enforced **as early as possible**.

### Unpivoting and Normalization

Unpivoting converts:

- Wide, presentation-style tables
- Into tall, analytical tables

This is essential for:

- Time-series analysis
- Category-based aggregation
- Scalable modeling

Normalized data models perform significantly better in Power BI.

### Merging vs Appending Tables

- **Merge**: Join tables horizontally (similar to SQL JOIN)
- **Append**: Stack tables vertically (UNION)

Correct choice depends on:

- Schema compatibility
- Relationship requirements
- Analytical intent

### Deduplication and Filtering

Power Query is the correct place to:

- Remove duplicate rows
- Filter irrelevant records
- Exclude invalid data

This reduces:

- Model size
- Refresh time
- Downstream complexity

## Query Folding

### What Query Folding Is

Query folding occurs when Power Query:

- Translates transformations
- Back into source-native queries (e.g. SQL)
- Executes them at the data source

### Why Query Folding Matters

Query folding:

- Improves refresh performance
- Reduces memory usage
- Enables scalability

When folding breaks, Power BI must:

- Pull raw data
- Transform it locally
- Increase refresh cost

### Common Folding Breakers

Operations that often prevent folding:

- Row-by-row custom columns
- Complex conditional logic
- Certain text transformations
- Unsupported M functions

Preserving query folding should be a **deliberate design goal**.

## Best Practices for Scalable Models

### Push Logic Upstream

Whenever possible:

- Perform heavy transformations in SQL, Lakehouse, or ETL pipelines
- Use Power Query for light shaping
- Keep DAX focused on analytics

This creates clearer responsibility boundaries.

### Managing Refresh Performance

To improve refresh times:

- Remove unused columns early
- Filter rows before complex transformations
- Avoid unnecessary intermediate steps
- Disable load for staging queries

Refresh performance directly impacts user trust.

### Cleaning Before Modeling

Data should enter the semantic model:

- Typed correctly
- Normalized
- Free of duplicates
- Consistent in naming and format

A clean input model simplifies:

- DAX logic
- Performance tuning
- Long-term maintenance

## Common Mistakes and Anti-Patterns

- Performing KPI calculations in Power Query
- Leaving columns with ambiguous data types
- Breaking query folding unintentionally
- Applying complex business logic at refresh time
- Treating Power Query as a replacement for ETL

## Key Power Query Takeaways

- Power Query is a **data preparation layer**
- Logic placement matters
- Query folding is critical for scale
- Clean data enables simpler DAX
- Good Power Query design reduces downstream complexity
