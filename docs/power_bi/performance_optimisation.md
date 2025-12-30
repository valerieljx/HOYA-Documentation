# Performance Optimisation in Power BI

## Why Performance Matters

Performance in Power BI is not just about speed — it directly affects:

- User trust in dashboards
- Adoption by business stakeholders
- Scalability of analytical solutions

Most performance issues are **not caused by visuals**, but by:

- Poor data modeling decisions
- Inefficient DAX design
- Misalignment with the underlying storage engine

Performance optimisation begins at the **semantic model**, not the report layer.

## Understanding Where Time Is Spent

When a user interacts with a report, Power BI executes a query that flows through two main components:

### Formula Engine (FE)

- Interprets DAX expressions
- Generates query plans
- Handles row context, iterators, and logic

### Storage Engine (SE)

- Retrieves and aggregates data
- Operates on VertiPaq (Import mode) or external sources (DirectQuery)

The Formula Engine is **single-threaded**, while the Storage Engine can operate in parallel.  
Poorly written DAX often forces excessive work into the Formula Engine.

## Query Execution Flow

At a high level:

1. User interaction defines filter context
2. Relationships propagate filters
3. Formula Engine interprets the DAX
4. Storage Engine retrieves and aggregates data
5. Results are returned to the visual

Optimisation aims to:

- Push work to the Storage Engine
- Minimise Formula Engine overhead

## Data Model Design for Performance

### Cardinality and Data Types

High-cardinality columns:

- Increase memory usage
- Reduce compression efficiency
- Slow down scans

Best practices:

- Prefer integers over text
- Remove unused columns
- Avoid storing IDs as strings
- Reduce precision where possible

### Relationship Design

Efficient models typically use:

- One-to-many relationships
- Single-direction filter propagation

Avoid when possible:

- Many-to-many relationships
- Bi-directional filters

Relationships define how filter context flows — poor design leads to expensive query plans.

### Granularity Control

Fact tables should:

- Match the lowest required level of analysis
- Avoid unnecessary duplication
- Be aggregated upstream when detailed granularity is not required

Excessive granularity increases both memory usage and query cost.

## DAX Performance Principles

### Aggregators vs Iterators

Aggregators (`SUM`, `AVERAGE`):

- Operate directly in the Storage Engine
- Are highly optimized

Iterators (`SUMX`, `AVERAGEX`):

- Operate row-by-row
- Increase Formula Engine workload

**Rule of thumb:**
> Use iterators only when column-level aggregation is insufficient.

### Use of Variables

Variables:

- Prevent repeated evaluation
- Reduce query complexity
- Improve readability

Measures without variables are harder to debug and often less efficient.

### Reducing Context Transitions

`CALCULATE()` introduces context transition.

While necessary, excessive or nested context transitions:

- Increase Formula Engine cost
- Complicate evaluation logic

Use context transitions deliberately and sparingly.

## Storage Modes and Trade-offs

### Import Mode

- Data stored in-memory (VertiPaq)
- Fast query performance
- Periodic refresh required

Best for:

- Analytical workloads
- Medium to large datasets
- High interactivity

### DirectQuery Mode

- Queries executed at source
- Dependent on source performance
- Limited DAX functionality

Best for:

- Near real-time requirements
- Very large datasets
- Strong backend systems

### Dual Mode

- Hybrid behaviour
- Can use in-memory or source queries depending on context

Useful for:

- Dimension tables
- Composite models

## VertiPaq Considerations

VertiPaq is:

- Columnar
- In-memory
- Optimized for scanning few columns over many rows

Performance implications:

- Calculated columns increase model size
- High-cardinality columns reduce compression
- Wide tables are more expensive to scan

Understanding VertiPaq behaviour is essential for sustainable performance.

## Performance Debugging and Tuning

### Identifying Bottlenecks

Common symptoms:

- Slow visual rendering
- Delays after slicer interaction
- High CPU usage

Likely causes:

- Complex DAX logic
- Inefficient relationships
- Excessive cardinality

### Common Causes of Slow Reports

- Too many visuals on a page
- Overuse of calculated columns
- Nested iterators
- Removing filters unnecessarily
- Poor storage mode choices

## Key Performance Takeaways

- Performance starts with data model design
- Push computation to the Storage Engine
- Keep DAX logic simple and explicit
- Reduce cardinality and model width
- Treat performance as a first-class requirement, not an afterthought
