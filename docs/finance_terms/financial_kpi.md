# Financial KPI Documentation (add GL accounting terms)

## 1. Overview
Financial Key Performance Indicators (KPIs) are metrics used to evaluate a company’s financial health, operational efficiency, and overall performance. These KPIs are essential for tracking progress against strategic objectives, identifying areas for improvement, and making informed financial decisions.

---

## 2. Key KPI Formulas

### 2.1 Cash Conversion Cycle (CCC)
The **Cash Conversion Cycle (CCC)** measures the time (in days) it takes for a company to convert its investments in inventory and other resources into cash flows from sales. It is **measured using dollar amounts**.

**Formula:**  
`CCC = DIO + DSO - DPO`

- **DIO (Days Inventory Outstanding):** Average number of days inventory is held before it’s sold.  
- **DSO (Days Sales Outstanding):** Average number of days it takes to collect payment after a sale.  
- **DPO (Days Payable Outstanding):** Average number of days the company takes to pay its suppliers.

| Component | Formula | GL Accounts Used | Purpose |
|-----------|---------|------------------|---------|
| **DIO** (Days Inventory Outstanding) | (Average Inventory ÷ COGS) × 365 | Inventory (Current Assets), COGS (Expense) | Measures how long inventory is held. |
| **DSO** (Days Sales Outstanding) | (Accounts Receivable ÷ Net Credit Sales) × 365 | Accounts Receivable (Current Assets), Revenue (Sales GL) | Measures how quickly receivables are collected. |
| **DPO** (Days Payable Outstanding) | (Accounts Payable ÷ COGS) × 365 | Accounts Payable (Current Liabilities), COGS (Expense) | Measures how long supplier payments are delayed. |

**Interpretation:** Shorter CCC = better liquidity and efficiency.

---

### 2.2 DSI (Days Sales of Inventory)  
This is primarily a **Supply Chain Management (SCM)** metric, used to measure how long (in days) it takes for inventory to be sold or used. It is typically **measured using units**.

**Formula:**  
`DSI = (Average Inventory / Cost of Goods Sold (COGS)) * 365`

- Often derived using **Inventory on Hand (IOL units)** for SCM analysis.
- **GL Accounts Used:** Inventory (Balance Sheet), COGS (Income Statement).  
- **Interpretation:** Measures how quickly inventory is sold or consumed.

---

### 2.3 VAW (Value Added Wages)  
**Value Added Wages (VAW)** refers to the wages paid to employees as part of the value-added process in production or services. It reflects the company’s investment in human capital and can be used to assess labor productivity and contribution to value creation.

**Formula:**  
`VAW = (Wages ÷ Value Added) × 100`  

- **GL Accounts Used:** Payroll Expense (Operating Expense GL), Benefits Expense.  
- **Interpretation:** Shows the share of value added distributed to employees, reflecting labor productivity.

---

## 3. Categories of Financial KPIs

### 3.1 Profitability KPIs

| KPI | Formula | GL Accounts Used | Purpose |
|-----|---------|------------------|---------|
| **Gross Profit Margin** | (Gross Profit ÷ Revenue) × 100 | Revenue (Sales), COGS (Expense) | Profitability after direct costs. |
| **Operating Profit Margin** | (Operating Profit ÷ Revenue) × 100 | Revenue, Operating Expenses (SG&A, R&D) | Efficiency from operations. |
| **EBIT (Earnings Before Interest and Taxes)** | Revenue − COGS − Operating Expenses − Depreciation & Amortization<br>or<br>Net Income + Interest Expense + Taxes | Revenue (Sales), COGS, Operating Expenses (SG&A, R&D, Depreciation/Amortization) | Core measure of operating profitability before financing and taxes. |
| **Net Profit Margin** | (Net Profit ÷ Revenue) × 100 | Revenue, All Expenses (Operating, Interest, Taxes) | Overall profitability. |
| **ROA (Return on Assets)** | (Net Income ÷ Total Assets) × 100 | Net Income (P&L), Total Assets (Balance Sheet) | Measures efficiency of asset use. |
| **ROE (Return on Equity)** | (Net Income ÷ Shareholder’s Equity) × 100 | Net Income, Equity Accounts | Profitability for shareholders. |

**Interpretation:**  
Higher margins, ROA, and ROE generally indicate stronger profitability, but should be benchmarked against industry peers.

---

### 3.2 Liquidity KPIs

| KPI | Formula | GL Accounts Used | Purpose |
|-----|---------|------------------|---------|
| **Current Ratio** | Current Assets ÷ Current Liabilities | Cash, AR, Inventory vs. AP, Accruals, Short-Term Debt | Measures short-term solvency. |
| **Quick Ratio (Acid Test)** | (Current Assets − Inventory) ÷ Current Liabilities | Cash, AR, Short-Term Investments vs. CL | Tests immediate liquidity without relying on inventory. |
| **Cash Conversion Cycle (CCC)** | DIO + DSO − DPO | Inventory, AR, AP, COGS, Sales | Efficiency of working capital. |

---

### 3.3 Efficiency KPIs

| KPI | Formula | GL Accounts Used | Purpose |
|-----|---------|------------------|---------|
| **Inventory Turnover** | COGS ÷ Average Inventory | COGS, Inventory | Efficiency of inventory management. |
| **AR Turnover** | Net Credit Sales ÷ Avg. Accounts Receivable (AR) | Sales, Accounts Receivable | Collection efficiency. |
| **AP Turnover** | COGS ÷ Avg. Accounts Payable (AP) | COGS, Accounts Payable | Supplier payment speed. |

---

### 3.4 Solvency KPIs

| KPI | Formula | GL Accounts Used | Purpose |
|-----|---------|------------------|---------|
| **Debt-to-Equity** | Total Liabilities ÷ Shareholder’s Equity | Total Liabilities, Equity Accounts | Capital structure health. |
| **Debt-to-Assets** | Total Liabilities ÷ Total Assets | Liabilities, Assets | Measures leverage. |
| **Interest Coverage** | EBIT ÷ Interest Expense | Operating Profit (EBIT), Interest Expense | Ability to cover debt costs. |

---

### 3.5 Revenue KPIs

| KPI | Formula | GL Accounts Used | Purpose |
|-----|---------|------------------|---------|
| **Total Revenue** | Sum of Sales | Sales Revenue GL | Sales performance. |
| **Revenue Growth Rate** | ((Current Revenue − Previous Revenue) ÷ Previous Revenue) × 100 | Sales GL (Period over Period) | Growth tracking. |
| **Sales per Employee** | Total Revenue ÷ Number of Employees | Sales GL, HR Headcount (non-GL) | Productivity measure. |

---

### 3.6 Cash Flow KPIs

| KPI | Formula | GL Accounts Used | Purpose |
|-----|---------|------------------|---------|
| **Operating Cash Flow (OCF)** | Cash generated from Operations | GL: Operating Cash Flow (Cash Flow Statement) | Core business cash generation. |
| **Free Cash Flow (FCF)** | Operating Cash Flow − Capital Expenditures | Operating Cash Flow, Capital Expenditures | Cash available after investments. |
| **Cash Flow Margin** | (Operating Cash Flow ÷ Revenue) × 100 | Operating Cash Flow, Sales GL | Proportion of revenue turning into cash. |

---

## 4. Why Financial KPIs Matter

### 4.1 Performance Monitoring  
Financial KPIs provide a clear picture of how a business is performing financially over time. It tracks trends in revenue, profitability and liquidity.

### 4.2 Strategic Alignment  
They help ensure that financial strategies are aligned with overall business goals. 

### 4.3 Early Warning System  
It detects inefficiencies or financial risks early. Businesses can identify potential problems early on and take corrective actions.  

### 4.4 Informed Decision Making  
Financial KPIs provide data-driven insights that support better decision-making in areas like investment, pricing, and resource allocation.  

### 4.5 Investor Relations  
These provide transparency and confidence to stakeholder. They are essential for communicating a company’s financial health to investors and stakeholders.  
