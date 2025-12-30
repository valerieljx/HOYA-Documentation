# DAX Fundamentals

## What DAX Is

DAX (Data Analysis Expressions) is a **semantic query language** used to define analytical logic on top of a tabular data model (Power BI, SSAS Tabular, Excel Power Pivot).

Unlike SQL or Power Query:

- DAX does **not** reshape data
- DAX does **not** persist results (for measures)
- DAX evaluates expressions **at query time**, based on context

DAX answers questions of the form:
> “What is the value of this metric *given the current filters, relationships, and user interactions*?”

As such, DAX is **context-driven**, not procedural.

## Measures vs Calculated Columns

### Measures

Measures:

- Are evaluated at query time
- Are not stored in the model
- React dynamically to slicers, filters, and visuals
- Are optimized for aggregation and analytics

Typical use cases:

- KPIs
- Ratios
- Variances
- Time intelligence
- Business metrics

Example of Measures:
`Gross Margin := DIVIDE([Total Revenue] - [Total Cost], [Total Revenue])`

### Calculated Columns

Calculated columns:

- Are evaluated during data refresh
- Are stored in the VertiPaq model
- Do **not** respond to slicers or filters
- Increase model size and cardinality

Typical use cases:

- Surrogate keys
- Flags and classifications
- Static groupings
- Relationship support

Example of Columns:
`Customer Segment := IF (Customers[LifetimeValue] >= 100000, "High Value", "Standard")`


### Design Principle

> If a value depends on **user interaction or filter context**, it must be a **measure**.  
> If a value must exist **per row regardless of filters**, it may be a **calculated column**.

Misplacing logic here is one of the most common causes of performance and correctness issues.

## Row Context

Row context exists when DAX evaluates an expression **one row at a time**.

Row context is introduced by:

- Calculated columns
- Iterator functions (`SUMX`, `AVERAGEX`, `MINX`, etc.)

Within row context:

- Column references resolve to the current row’s value
- No automatic filtering occurs on related tables

Row context alone **cannot aggregate data across tables**.

## Filter Context

Filter context defines **which subset of rows is visible** during evaluation.

Filter context is created by:

- Slicers
- Report/page/visual filters
- Visual structure (rows, columns, legends)
- Explicit filters in DAX expressions

Filter context:

- Propagates through relationships
- Drives aggregation behaviour
- Is the primary determinant of a measure’s result

> Measures do not compute fixed values — they compute results *under the current filter context*.

## Relationship Between Row Context and Filter Context

Row context and filter context are **independent concepts**.

- Row context evaluates expressions row-by-row and do not automatically filters other tables
- Filter context determines which rows are included in aggregations

## Context Transition

Context transition is the mechanism that converts **row context into filter context**.

- Triggered explicitly by `CALCULATE()`
- Allows values from the current row to act as filters

Without context transition:

- Iterators cannot influence related tables
- Row-level values remain isolated

Context transition is essential for:

- Per-row calculations involving multiple tables
- Correct evaluation of measures inside iterators

## CALCULATE: The Core of DAX

`CALCULATE()` is the most important function in DAX.

Conceptually, `CALCULATE()` performs two steps:

1. **Modify the filter context**
2. **Evaluate the expression under the new context**

It can:

- Add filters
- Remove filters
- Override existing filters
- Trigger context transition

Because of this, `CALCULATE()` is both powerful and dangerous when misused.

> If a DAX measure behaves unexpectedly, `CALCULATE()` is usually involved.

## Filter Modification Functions

Common filter-modifying functions include:

- `ALL()` – removes filters
- `REMOVEFILTERS()` – removes filters explicitly
- `VALUES()` – preserves granularity
- `FILTER()` – creates conditional filters

## Iterators vs Aggregators

### Aggregators
Functions such as `SUM()` and `AVERAGE()`:

- Operate directly on columns
- Rely entirely on filter context
- Are highly optimized

### Iterators
Functions such as `SUMX()` and `AVERAGEX()`:

- Evaluate expressions row-by-row
- Introduce row context
- Are computationally more expensive

**Best practice:**
> Use aggregators whenever possible.  
> Use iterators only when row-level logic is required.

## Variables (`VAR`)

Variables allow intermediate results to be stored within a measure.

Benefits:

- Improved readability
- Easier debugging
- Reduced repeated computation
- More predictable evaluation order

Variables are evaluated **once per query context**, not per row.

> Any measure with non-trivial logic should use variables.

## Evaluation Order and Mental Model

When a measure is evaluated:

1. Visual and slicers define initial filter context
2. Relationships propagate filters
3. `CALCULATE()` modifies filter context (if present)
4. Expression is evaluated by the engine
5. Results are aggregated and returned

Understanding this flow is more important than memorizing syntax.

## Common Conceptual Pitfalls

- Expecting calculated columns to respond to slicers
- Confusing row context with filter context
- Overusing iterators unnecessarily
- Writing monolithic measures without variables
- Removing filters too aggressively with `ALL()`

## Key Takeaways

- DAX is **context-driven**, not procedural
- Measures are the foundation of analytical logic
- Filter context determines meaning
- `CALCULATE()` defines power and complexity
- Correct mental models matter more than formulas

Mastery of DAX begins with **understanding how evaluation works**, not with writing complex expressions.