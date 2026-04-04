# OPAL Fuels — Company Analysis & Valuation

**Georgetown MSBA | FINC 6580: FinTech | Project 2**

SAXA 3 — Mike Johnson, Kris Lederer, Sebastian Martinez, Ryan Mathis, Khushi Patel

A fundamental analysis and Discounted Cash Flow (DCF) valuation of [OPAL Fuels](https://opalfuels.com/) (NASDAQ: OPAL), a renewable natural gas (RNG) producer and distributor focused on decarbonizing the transportation sector.

---

## Overview

OPAL Fuels collects biogas from organic waste streams — landfills, dairy farms, and wastewater treatment plants — and upgrades it into renewable natural gas used as a low-carbon fuel for heavy-duty trucking. This project builds a bottom-up financial model to assess the company's intrinsic value and growth prospects.

**Valuation conclusion:** See `dcf_model.xlsx` for the full DCF model, assumptions, and implied price range.

---

## Project Structure

```
opal_fuels/
├── financials.ipynb        # Python pipeline: pulls OPAL financials via yfinance, exports to Excel
├── financials.xlsx         # Output: Income Statement, Cash Flow, Balance Sheet (long format)
├── dcf_model.xlsx          # DCF valuation model with scenario analysis
├── OPAL_DCF.xlsx           # Supporting DCF workbook
├── Opal Sales FCST.html    # Rendered sales forecasting notebook
└── requirements.txt        # Python dependencies
```

---

## Methodology

### 1. Financial Data Extraction (`financials.ipynb`)
- Pulls 4 years of historical financial statements from Yahoo Finance via `yfinance`
- Unpivots wide-format data (years as columns) into long format for easier modeling
- Exports structured data to Excel — one sheet per statement

### 2. Sales Forecasting (`Opal Sales FCST.html`)
- Projects near-term revenue based on contracted RNG volumes and fuel station throughput
- Incorporates RNG pricing assumptions tied to Renewable Identification Numbers (RINs) and Low Carbon Fuel Standard (LCFS) credits

### 3. DCF Valuation (`dcf_model.xlsx`)
- Projects free cash flow over a 5-year explicit forecast period
- Terminal value estimated using the Gordon Growth Model
- WACC derived from CAPM with industry-adjusted beta
- Sensitivity tables across WACC and terminal growth rate assumptions

---

## Key Findings

- OPAL operates in a high-growth, policy-driven market where revenue is significantly influenced by RIN and LCFS credit prices
- Capital-intensive build-out phase suppresses near-term free cash flow; value is back-weighted
- Contracted fuel offtake agreements provide revenue visibility and reduce demand risk

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python (`yfinance`, `pandas`) | Financial data extraction |
| Jupyter Notebook | Reproducible data pipeline |
| Excel | DCF model, scenario analysis, sales forecast |

---

## Reproducing the Analysis

**Install dependencies:**
```bash
pip install -r requirements.txt
```

**Run the financial data pipeline:**
```bash
jupyter notebook financials.ipynb
```

Executing all cells will pull current OPAL Fuels financial statements from Yahoo Finance and write `financials.xlsx`.

---

README written with the assistance of [Claude Code](https://claude.ai/code) by Anthropic.
