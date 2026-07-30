# 📊 Exploratory Data Analysis (EDA) — E-Commerce Order Data

**DecodeLabs Data Analytics Internship — Project 2**

A hands-on exploratory data analysis of a 1,200-row e-commerce order dataset, uncovering
sales trends, customer behavior patterns, and statistical outliers using Microsoft Excel.

---

## 🎯 Objective
- Calculate basic descriptive statistics (mean, median, count, std dev)
- Identify sales trends across products, time, and customer behavior
- Detect statistical outliers using the IQR method
- Summarize key business observations

---

## 🛠️ Tools & Techniques
`Microsoft Excel` — `AVERAGE` · `MEDIAN` · `COUNT` · `MAX` · `MIN` · `STDEV` · `QUARTILE` ·
Pivot Tables · Column/Line/Pie/Bar Charts · IQR Outlier Detection

---

## 📂 Dataset
1,200 e-commerce orders × 14 columns: `OrderID`, `Date`, `CustomerID`, `Product`, `Quantity`,
`UnitPrice`, `ShippingAddress`, `PaymentMethod`, `OrderStatus`, `TrackingNumber`,
`ItemsInCart`, `CouponCode`, `ReferralSource`, `TotalPrice`.

*(This is the cleaned dataset produced in Project 1 — Data Cleaning & Preparation.)*

---

## 📈 1. Descriptive Statistics

| Metric | Quantity | UnitPrice | ItemsInCart | TotalPrice |
|---|---:|---:|---:|---:|
| Mean | 2.95 | 356.41 | 5.48 | **1,053.97** |
| Median | 3 | 364.21 | 5 | **823.62** |
| Count | 1,200 | 1,200 | 1,200 | 1,200 |
| Max | 5 | 699.93 | 10 | 3,456.40 |
| Min | 1 | 11.39 | 1 | 11.39 |
| Std Dev | 1.41 | 197.18 | 2.28 | 819.86 |

> Mean order value ($1,053.97) is well above the Median ($823.62) — a classic sign of a
> **right-skewed distribution**, where a handful of high-value orders pull the average up.

---

## 📊 2. Trend Analysis (Pivot Tables)

### 🏆 Product Sales
| Product | Sum of TotalPrice | Order Count |
|---|---:|---:|
| Chair | $195,620.11 | 178 |
| Printer | $195,612.61 | 181 |
| Laptop | $192,126.56 | 173 |
| Tablet | $186,568.95 | 179 |
| Desk | $167,459.93 | 170 |
| Monitor | $175,651.41 | 163 |
| Phone | $151,722.39 | 156 |

**Insight:** Chair and Printer are near-tied revenue leaders (~$195.6K each); Phone trails
with the lowest revenue and order count.

### 📅 Monthly Trend
Highest sales month: **June 2024** ($68,068.54)
Lowest sales month: **April 2023** ($27,751.71)

**Insight:** No clear seasonal cycle — sales fluctuate month to month, suggesting demand is
driven more by external factors (promotions, marketing) than seasonality.

### 💳 Payment Method
| Method | Orders |
|---|---:|
| Online | 258 |
| Cash | 246 |
| Credit Card | 234 |
| Debit Card | 232 |
| Gift Card | 230 |

**Insight:** Usage is fairly balanced across all 5 methods, with Online slightly preferred.

### 📦 Order Status
| Status | Orders |
|---|---:|
| Cancelled | 250 |
| Returned | 247 |
| Pending | 237 |
| Shipped | 235 |
| Delivered | 231 |

**Insight:** Cancelled + Returned orders account for **~41%** of all orders — a signal worth
deeper business investigation.

---

## 🔎 3. Outlier Detection (IQR Method)

| Metric | Value |
|---|---:|
| Q1 (25th percentile) | $410.52 |
| Q3 (75th percentile) | $1,578.48 |
| IQR | $1,167.96 |
| Lower Bound | -$1,341.41 |
| Upper Bound | $3,330.41 |
| **Outliers detected** | **8 orders** (TotalPrice > $3,330.41) |

**Method:** Any order with `TotalPrice` outside `[Q1 − 1.5×IQR, Q3 + 1.5×IQR]` is flagged as
a statistical outlier — the industry-standard approach that avoids the distortion caused by
extreme values when using simple averages.

---

## 📝 4. Key Business Observations

1. **Right-skewed order values** — most orders cluster below $1,050, but a few high-value
   orders raise the average significantly.
2. **Balanced product performance** — no single product dominates; Chair and Printer lead by
   a narrow margin.
3. **No strong seasonality** — monthly sales vary without a repeating pattern.
4. **Even payment adoption** — customers don't strongly favor one payment method over another.
5. **High cancellation/return rate (~41%)** — a potential red flag for customer satisfaction
   or fulfillment issues, worth deeper investigation.
6. **8 high-value outliers** — likely bulk orders or data anomalies, flagged for manual review.

---

## 📁 Repository Contents
```
├── README.md
├── data/
│   └── Project2_EDA.xlsx     # Full workbook: raw+cleaned data, statistics, outlier
│                              # calculations, 4 pivot tables, charts, and summary
└── screenshots/               # Visual evidence of pivot tables & charts
```

---

## 🔗 Related
Part of a 3-project Data Analytics Internship series:
1. Data Cleaning & Preparation ✅
2. **Exploratory Data Analysis (EDA)** ✅ *(this repository)*
3. Reporting / Dashboard 🔜
