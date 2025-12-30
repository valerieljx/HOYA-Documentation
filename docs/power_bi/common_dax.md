# Common DAX Patterns

## Purpose of DAX Patterns

While DAX fundamentals explain **how evaluation works**, DAX patterns explain **how business questions are consistently expressed** in DAX.

Patterns:

- Reduce duplicated logic
- Improve consistency across reports
- Make measures easier to reason about and debug
- Encode business semantics, not just calculations

A well-designed Power BI model relies more on **reusable patterns** than on complex one-off measures.

## Variance Analysis Patterns

Variance analysis is one of the most common analytical requirements, especially in finance, forecasting, and performance tracking.

### Absolute Variance

**Business question:**  
How much did actual performance differ from the benchmark?

**Conceptual pattern:**

- Evaluate both metrics under the same filter context
- Compute the difference

This pattern assumes:

- Both measures are defined at the same granularity
- Filters (time, region, product) apply symmetrically

### Percentage Variance

**Business question:**  
How large is the difference relative to the benchmark?

**Conceptual pattern:**

- Use the benchmark as the denominator
- Handle division-by-zero explicitly

Percentage variance patterns are sensitive to:

- Filter removal
- Inconsistent base measures
- Missing data

Clear definition of the **reference metric** is critical.

## Percent of Total and Percent of Parent

Contribution analysis answers the question:

> “How much does this item contribute to the whole?”

### Removing vs Preserving Filter Context

At the core of contribution analysis is **selective filter removal**.

Key design decision:

- Which filters should be removed?
- Which filters must remain?

Common approaches:

- Remove category-level filters
- Preserve time and scenario filters

Incorrect filter removal leads to misleading contributions.

### Common Contribution Scenarios

Typical use cases:

- Revenue by product as a share of total revenue
- Cost by department as a share of total cost
- Market share by region

Contribution patterns rely heavily on:

- `ALL()`
- `REMOVEFILTERS()`
- `VALUES()`

Understanding **scope of filter removal** is more important than the functions themselves.

## Time Intelligence Patterns

Time-based analysis is inherently contextual.

### Date Table Requirements

All time intelligence patterns require:

- A continuous date table
- One row per date
- Proper relationships to fact tables
- Marked as a date table

Without this foundation, time intelligence becomes unreliable.

### Year-to-Date (YTD)

**Business question:**  
What is the cumulative value from the start of the year to the current period?

YTD patterns depend on:

- Current evaluation date
- Calendar logic
- Preserved filter context

### Month-to-Date (MTD)

MTD follows the same logic as YTD, scoped to the current month.

Key consideration:

- Interaction with slicers and visual-level filters

### Rolling Period Calculations

Rolling metrics smooth short-term volatility.

Examples:

- Rolling 3-month average
- Rolling 12-month total

Rolling patterns require:

- Explicit window definitions
- Careful handling of incomplete periods

### Year-over-Year (YoY)

**Business question:**  
How does current performance compare to the same period last year?

YoY patterns require:

- Correct date shifting
- Consistent granularity
- Stable calendar definitions

## KPI and Threshold Classification

KPI classification translates numeric metrics into **actionable signals**.

### Target-Based Evaluation

Common comparisons:

- Actual vs Target
- Actual vs SLA
- Actual vs Budget

Targets should:

- Be stored centrally
- Be evaluated under identical context

### Status Banding (Green / Amber / Red)

Status logic:

- Encodes business thresholds
- Produces categorical outputs
- Supports conditional formatting

Best practice:
> Separate numeric calculation from status classification.

This improves maintainability and clarity.

## Dynamic and Slicer-Driven Measures

Dynamic measures allow **one visual to represent multiple metrics**.

### Metric Selection Patterns

Used for:

- KPI selectors
- Dashboard simplification
- Executive summaries

Pattern characteristics:

- User selection determines measure logic
- Reduces report duplication
- Centralizes business logic

### Scenario and Comparison Switching

Common scenarios:

- Actual vs Forecast
- Base vs Upside / Downside
- Current vs Prior period

Switching patterns require:

- Clear definitions of scenarios
- Stable reference measures
- Controlled user input

## Pattern Design Principles

Effective DAX patterns should be:

- Context-aware
- Modular
- Reusable
- Clearly named

Patterns should encode **business meaning**, not just arithmetic.

## Common Anti-Patterns

- Embedding business logic directly in visuals
- Duplicating similar measures with minor differences
- Removing too many filters indiscriminately
- Mixing numeric and classification logic in one measure
- Overusing iterators where aggregators suffice

## Key Takeaways

- DAX patterns formalize analytical intent
- Correct filter scoping is central to most patterns
- Time intelligence depends on data model quality
- Reusable patterns reduce complexity and errors
- Maintainability is as important as correctness
