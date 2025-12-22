# Calendar Systems and Accounting Periods

Different teams, regions, and systems use **different calendar definitions** for budgeting, forecasting, and reporting.  

Misalignment between calendar definitions is a common cause of:

- Budget vs actual mismatches
- Incorrect variance analysis
- Confusion around year-to-date (YTD) reporting

## Type of Calender Terminology

### Calendar Year
- Runs from **1 January to 31 December**
- Aligns exactly with the Gregorian calendar
- Commonly used for:
  - External reporting
  - Public datasets
  - Many US-based companies

### Fiscal Year (FY)
- A **company-defined 12-month reporting period**
- Does not necessarily align with the calendar year
- Typically named by its **ending year**

  - Example: FY25 ends in 2025

Fiscal years are used for:
- Budgeting
- Forecasting
- Internal performance evaluation

### Accounting Period
- A subdivision of a fiscal year
- Often monthly, but system-dependent
- Used for:

  - Financial closing
  - Budget tracking
  - Variance analysis

## 1. Standard (Calendar) Calendar

### Definition
The standard calendar follows the Gregorian calendar:

- January (1) through December (12)
- Year boundaries align with the calendar year

### Typical Usage
- Most US companies
- External-facing financial communication
- Simplified time-based analysis

### Advantages
- Intuitive and widely understood
- Aligns with public benchmarks and datasets
- No year-crossing months

### Limitations
- May not reflect business seasonality
- Less suitable for companies with non-calendar operating cycles

## 2. Fiscal Calendars (Non-Standard)

Fiscal calendars shift the start of the year to better align with operational or regional business cycles.

### Japan Fiscal Calendar (April to March)

![Fiscal Calendar](../images/fiscal-calendar.png)

**Structure:**

- Fiscal Year starts in **April**
- Ends in **March**
- Example:

  - FY25 = April 2024 to March 2025

**Common Usage:**

- Japanese companies
- Subsidiaries reporting into Japan headquarters

**Implications:**

- Q1 = April to June
- Fiscal year crosses calendar year boundaries
- Calendar-based data must be remapped for fiscal reporting

### Singapore / Regional Fiscal Calendar (July to June)

**Structure:**

- Fiscal Year starts in **July**
- Ends in **June**
- Example:
  - FY25 = July 2024 to June 2025

**Common Usage:**

- Some Singapore-based or APAC regional organisations
- Government-linked or education-related entities

**Implications:**

- Budget cycles reset mid-calendar year
- Year-over-year comparisons require fiscal alignment

## 3. SAP Accounting Periods

### What SAP Periods Represent

SAP uses **posting periods** rather than relying purely on calendar months.

A fiscal year in SAP typically consists of:

- **12 normal operating periods**
- **Additional adjustment periods**

### SAP Period Structure

![SAP Calendar](../images/sap-calendar.png)

- Periods **1–12**  
  - Correspond to standard operating months within the fiscal year
- Periods **13–16**  
  - Special adjustment periods
  - Used for year-end and post-closing entries

These additional periods **do not represent new calendar months**.

### Purpose of SAP Adjustment Periods (13–16)

Adjustment periods exist to:

- Allow audit and accrual postings
- Prevent reopening closed operational periods
- Maintain clean month-end and year-end closes

Example:

- Period 12 is closed
- Adjustments are posted to Period 13–16 instead

### Key Distinction

> **SAP Period ≠ Calendar Month**

SAP periods are accounting constructs and should not be assumed to map one-to-one with calendar months.

## Example: Fiscal Year and SAP Period Mapping

![Comparison-calendar](../images/comparison-calendar.png)

Based on the current budgeting setup:

- Fiscal Year FY25 starts in **April 2025**
- Period mapping:

  - Period 1 → April 2025
  - Period 2 → May 2025
  - …
  - Period 9 → December 2025
  - Period 10 → January 2026
  - Period 11 → February 2026
  - Period 12 → March 2026
  - Period 16 → Year-end adjustment (March 2026)

### Key Observation

- FY25 spans **two calendar years**
- January to March 2026 still belong to FY25
- This is expected behaviour under a fiscal calendar

## Why Calendar Definitions Matter for Budgeting

### Budget vs Actual Alignment
- Budgets are set by **fiscal year and fiscal period**
- Actuals may be recorded by **calendar date**
- Misalignment leads to incorrect comparisons

### Forecasting Implications
- Rolling forecasts must respect fiscal boundaries
- Period-based forecasts cannot assume calendar alignment

### Variance Analysis
- Comparing calendar-month actuals to fiscal-period budgets can result in misleading variance conclusions

## Best Practices When Working with Multiple Calendars

### Always State the Calendar Definition
Every report or dataset should clearly specify:

- Calendar type
- Fiscal year start month
- Period definition (SAP vs calendar)

### Avoid Implicit Calendar Mixing
Do not:

- Assume Period 1 is January
- Aggregate SAP periods as if they are calendar months
- Mix regional fiscal calendars without reconciliation

### Maintain a Calendar Mapping Table

A central calendar reference should include:

- Calendar date
- Calendar month and year
- Fiscal year
- Fiscal period
- SAP posting period

## Forecasting Periods and Budgeting Cycle Expectations

Budgeting and forecasting follow a **rolling period-based approach**, where each period transitions from *Forecast* to *Actual* as financial results are closed.

The expectations for each period differ depending on whether the submission is:

- **For Review**, or
- **Final Submission**

The figure below illustrates how *Actuals* and *Forecasts* should be populated across the fiscal year for each budgeting cycle.

![Submission Requirements](../images/submission_requirements.png)

## Key Definitions

### Actual
- Financial results that have been:

  - Posted
  - Reviewed
  - Closed for the period

- Actuals should not change after period close

### Forecast
- Forward-looking estimates based on:

  - Latest business assumptions
  - Known risks and opportunities

- Forecast values are updated each budgeting cycle until the period closes

### Rolling Forecast
- As each month closes:

  - That period becomes **Actual**
  - Remaining future periods stay **Forecast**

- The forecast horizon shifts forward month by month

## For Review Submissions

### Expectations
- Only periods that are **fully closed** should be marked as Actual
- All open and future periods remain Forecast
- The cutoff reflects the **latest available actuals** at the time of review

## Final Submissions

Final submissions represent the **official budgeting or forecasting position**.

### Expectations
- All periods **up to and including the current reporting month** must be Actual
- Only periods **after the cutoff month** remain Forecast
- No forecast values should remain in closed periods
