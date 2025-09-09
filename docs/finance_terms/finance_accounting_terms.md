# Financial Terms Overview

This document explains the **core accounting terms, financial statements, and sign conventions** used in reporting.  
It also highlights where these terms appear in the **Financial KPI Documentation**.

## 1. Core Financial Statements

### 1.1 P&L (Profit & Loss Statement / Income Statement)

Shows the company’s **financial performance** over a period (monthly, quarterly, annual).

**Key Components**:
- **Revenue** – Total sales or income earned from operations.  
  - *Used in:* Gross Profit Margin, Net Profit Margin, Cash Flow Margin.  
- **COGS (Cost of Goods Sold)** – Direct costs of goods/services sold.  
  - *Used in:* Gross Margin, Inventory Turnover, CCC (DIO, DPO).  
- **Gross Margin** = Revenue − COGS.  
- **OPEX (Operating Expenses)** – Costs related to operations. Indirect costs not tied to production:  
  - Selling & Distribution  
  - General & Administrative (G&A)  
  - Research & Development (R&D)  
- **Operating Profit (EBIT: Earnings Before Interest and Taxes)** = Gross Margin − OPEX.  
  - *Used in:* Operating Profit Margin, Interest Coverage Ratio.  
- **Net Income (Profit After Tax)** = EBIT − Interest Expense − Taxes ± Non-operating items.  
  - *Used in:* Net Profit Margin, ROA, ROE.  
- **Non-Operating Income/Expense** – Items outside core business (e.g., investment gains, one-time losses, financing costs).
- **CapEx (Capital Expenditure)** – Cash spent on acquiring or upgrading assets.  
  - *Note:* CapEx does **not** appear in the P&L; only **depreciation** (the allocation of CapEx over time) is recorded as an expense. CapEx is shown in the **Cash Flow Statement (Investing Activities)**.

---

## 2. BS (Balance Sheet)

**Trial Balance Equation:**  
\[
\textbf{Assets = Liabilities + Equity}
\]

**Key Components**:
- **Assets** – Resources owned that provide future benefits.  
  - *Example:* cash, accounts receivable, inventory, equipment
  - *Used in:* ROA, Current Ratio, Quick Ratio, CCC (DIO, DSO).  
- **Liabilities** – Obligations or debt owed to third parties. 
  - *Example:* loans, accounts payable
  - *Used in:* Debt-to-Equity, Debt-to-Assets, Current Ratio, Quick Ratio.  
- **Equity** – Residual interest after liabilities are deducted. Ownership interest, has two main components: 1. Capital Contributions and 2. Retained Earnings.
  - *Used in:* ROE, Debt-to-Equity.

---

### 2.1 Assets
**Definition:** Resources owned or controlled by the company that are expected to deliver future economic benefits.  

**Types:**
- **Current Assets** – Realized/used within 12 months.  
  - Examples:  
    - **Cash and Cash Equivalents** – Highly liquid funds.  
    - **Accounts Receivable (AR):** Money customers owe to the company for credit sales.  
    - **Inventory** – Goods held for sale.  
    - **Prepaid Expenses** – Payments made in advance for future benefits.  
- **Non-Current Assets** – Long-term resources.  
  - Examples: Property, Plant & Equipment (PPE), buildings, Intangibles (patents, goodwill).
---

### 2.2 Liabilities
**Definition:** Present financial obligations or debts to transfer/owed resources to external parties due to past events. They typically require settlement in the form of cash, goods, or services.

**Types:**
- **Current Liabilities** – Due within 12 months.  
  - Examples:  
    - **Accounts Payable (AP):** Money the company owes to suppliers for goods/services purchased on credit.  
    - **Short-term Loans** – Borrowings repayable within a year.  
    - **Accrued Expenses** – Expenses incurred but not yet paid (e.g., wages, taxes).  
- **Non-Current Liabilities** – Due after 12 months.  
  - Examples: Long-term loans, Bonds payable, Lease obligations.
---

### 2.3 Equity
**Definition:** The residual value in the company after liabilities are subtracted from assets. Represents shareholders’ ownership value.  

**Components:**
1. **Share Capital** – Funds contributed by owners/shareholders.  
2. **Retained Earnings (RE)** – Accumulated profits reinvested into the business.  
   - **Current Year Net Income** - The company’s net profit for the current fiscal year → closes into RE in the Balance Sheet.  
3. **Additional Paid-In Capital (APIC)** – Funds received above the per value of share.  
4. **Other Comprehensive Income (OCI)** – Gains/losses bypassing Net Income (e.g., FX, revaluations).  

---

## 3. CF (Cash Flow Statement)

Tracks **cash inflows/outflows** across three sections.

1. **Operating Activities (OCF)** – Cash from day-to-day core operations.  
   - *Example:* sales 
   - *Used in:* Operating Cash Flow, Free Cash Flow, Cash Flow Margin.  
2. **Investing Activities** – CAPEX, asset purchases/sales, investments.  
3. **Financing Activities** – Borrowings/repayments, equity issuance, dividends.  

**Example: CAPEX Purchase ($100 equipment)**  
- Balance Sheet: Equipment (Asset) ↑ $100  
- Cash Flow (Investing): Cash ↓ $100  
- P&L: No immediate expense → depreciation spreads cost over time  

## 4. ALORE and Sign Conventions

Accounting balances follow **Debit (Dr) and Credit (Cr)** rules summarized by **ALORE**:

- **A – Assets**  
- **L – Liabilities**  
- **O – Owners’ Equity**  
- **R – Revenue**  
- **E – Expenses**

### 4.1 Debit vs Credit Rules
- **Debits (Dr):** Increase Assets & Expenses; decrease Liabilities, Equity, Revenue.  
- **Credits (Cr):** Increase Liabilities, Equity, Revenue; decrease Assets & Expenses.  

### 4.2 System Display Conventions
Some ERP systems display balances as positive/negative:
- **Assets & Liabilities** → shown as positive. [because they represent the total amounts owned (Assets) or owed (Liabilities).]
- **Revenue & Equity** → may show as negative when increasing (credit-normal). [because they are credit accounts, but negative here means an **increase** in those accounts. Revenue increases equity.]
- **Expenses** → shown as positive when increasing (debit-normal). [because they increase with debits (they reduce equity). Expenses reduce equity]

This ensures the accounting equation (Assets = Liabilities + Equity) stays balanced.

### 4.3 How to Read Signs
- **Positive Asset**: The company owns value (e.g., $100 in cash).
- **Positive Liability**: The company owes value (e.g., $50 loan).
- **Negative Revenue**: This means revenue is increasing (a credit).
- **Positive Expense**: Expenses are increasing (a debit).


### 4.4 Quick Reference: Display Signs
| Category | Displayed As | Negative Means |
|----------|--------------|----------------|
| **Assets (A)** | Positive | Asset decreased |
| **Liabilities (L)** | Positive | Liability decreased |
| **Equity (O)** | Often negative | Equity increased |
| **Revenue (R)** | Often negative | Revenue increased |
| **Expenses (E)** | Positive | Refund/reversal |

### 4.5 Quick Reference: Debit/Credit Effects
| Category | Debit (Dr) | Credit (Cr) |
|----------|------------|-------------|
| **Assets (A)** | Increase | Decrease |
| **Liabilities (L)** | Decrease | Increase |
| **Equity (O)** | Decrease | Increase |
| **Revenue (R)** | Decrease | Increase |
| **Expenses (E)** | Increase | Decrease |

