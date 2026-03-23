# 📊 Data Visualization Case Study — Pharma Sales Data (Python)

> A complete end-to-end exploratory data visualization project on two-year pharmaceutical sales data (2015–2016), solving 8 real-world business questions using Python, Pandas, NumPy, Matplotlib, and Seaborn.

![Alt text](https://www.elevate.so/content/images/2023/11/3697156.jpg)
---

## 🗂️ Project Structure
```
├── Data_Visualilzation_Case_Study_on_Sales_Data.ipynb   # Main solution notebook
├── SalesData.csv                                         # Dataset (3709 rows × 14 columns)
├── Data_Visualization_Case_Study_in_Python.pdf          # Problem statement & sample outputs
└── README.md
```

---

##  Business Objective

A leading pharmaceutical company wants to understand its **sales trends across 2015 and 2016** through a dynamic dashboard with KPIs at multiple levels — **National, Region, Territory, Division, Tier, and Quarter**.

The goal is to:
- Explore past performance data in a meaningful visual manner
- Identify regions and divisions that are **growing vs declining**
- Understand **customer tier contributions** to overall revenue
- Catalyze the **decision-making process** — making it easier, simpler, and more accurate

---

##  Dataset Description

| Column | Description |
|---|---|
| `AccountId` | Unique Customer ID |
| `AccountName` | Customer Name |
| `Region` | Sales Region — Central / East / West |
| `Division` | Sales Division (26 unique divisions) |
| `City` | City of the customer account |
| `State` | State of the customer account (44 unique states) |
| `Tier` | Customer Segment — High / Med / Low / Out |
| `Month` | Month of the sales record |
| `Sales2015` | Sales revenue for 2015 |
| `Sales2016` | Sales revenue for 2016 |
| `Units2015` | Number of units sold in 2015 |
| `Units2016` | Number of units sold in 2016 |
| `TargetAchieved2015` | Target achievement ratio for 2015 |
| `TargetAchieved2016` | Target achievement ratio for 2016 |

###  Dataset Stats 

| Metric | Value |
|---|---|
| Total Records | 3,709 rows |
| Total Features | 14 columns |
| Missing Values |  None |
| Year Coverage | 2015 & 2016 |
| Regions | 3 (Central, East, West) |
| Unique Divisions | 26 |
| Unique States | 44 |
| Customer Tiers | 4 (High, Med, Low, Out) |

---

## ❓ Business Questions Solved

| # | Business Question | Chart Type |
|---|---|---|
| 1 | Compare Sales by Region for 2016 vs 2015 | Grouped Bar Chart |
| 2 | Contributing factors to 2016 sales per region | Pie Chart |
| 3 | Compare total sales of 2015 & 2016 by Region and Tier | Faceted Bar Chart |
| 4 | Which state in East region had a sales decline in 2016? | Bar Chart |
| 5 | Which High-tier Division saw units decline in 2016? | Bar Chart |
| 6 | Create Quarter column from Month using `numpy.where()` | Feature Engineering |
| 7 | Compare Quarter-wise sales in 2015 and 2016 | Grouped Bar Chart |
| 8 | Composition of Quarter-wise 2016 sales by Tier | 4 Pie Charts (2×2 grid) |

---

## 🔍 Key Insights & Findings

###  1. Regional Sales Performance (2015 vs 2016)

- **East region dominated** in 2016 with total sales of ~**$12.67 million**, a significant jump from ~$9.51 million in 2015 — a growth of **~33%**.
- **Central region** grew from ~$7.89 million in 2015 to ~$9.79 million in 2016 — a solid **~24% increase**.
- **West region** showed the weakest performance — growing from ~$5.35 million to ~$7.21 million, a **~35% increase** but still the lowest absolute sales among all three regions.
- **All three regions showed positive YoY growth**, indicating a healthy national expansion for the company.
- East region alone contributed **over 42%** of total national sales in 2016.

---

###  2. Regional Contribution to 2016 Sales (Pie Chart)

- **East: 42.7%** — nearly half the total national sales came from the East alone.
- **Central: 33%** — a significant one-third share.
- **West: 24.3%** — the smallest share, suggesting potential for expansion or underperformance.
- The **East-Central corridor** collectively accounts for **~75.7%** of all 2016 sales, making the West a key target region for growth strategy.

---

###  3. Sales by Region × Tier (2015 vs 2016)

- **High-tier customers** are the biggest revenue drivers across ALL three regions in both years, contributing the majority of total sales in every region.
- In the **East region**, High-tier 2016 sales exceeded **$6 million** — the single largest segment-region combination.
- **Med-tier** customers ranked second in revenue contribution, especially strong in the East region.
- **Out-tier** customers showed notable growth from 2015 to 2016 in the Central region, suggesting a segment that was previously underperforming is now gaining traction.
- **Low-tier** customers had the lowest contribution across all regions and both years — indicating either a small customer base or very low per-customer sales.
- Every Tier in every Region showed **higher sales in 2016 than 2015**, reaffirming the overall growth trend.

---

###  4. East Region — State-Level Sales Decline

- Across all states in the East region, **New York (NY)** was the **only state that registered a decline** in sales from 2015 to 2016.
- All other East region states — CT, DC, FL, GA, MA, MD, ME, NC, NH, NJ, PA, RI, SC, TN, VA — showed **growth or stable performance** in 2016.
- NY's decline is notable because it is typically a high-value market, making this a **critical red flag** for the sales team to investigate.
- Possible factors could include increased competition, territory restructuring, or loss of key High-tier accounts in New York.

---

###  5. High-Tier Divisions — Units Sold Decline (2015 vs 2016)

- Within the **High-tier customer segment**, multiple divisions saw their **unit sales drop in 2016** compared to 2015.
- Even though revenue (Sales2016) grew overall, unit-level declines in specific High-tier divisions could indicate **price increases masking volume losses**.
- Divisions like **BOOSTERS, CROSSFIRE, KANGAROO** and a few others showed visible dips in units sold — making them priority divisions for the sales operations team to revisit.
- This also raises a question: are the remaining High-tier divisions compensating with **higher-value products** or just fewer but bigger transactions?

---

### 6. Quarter Column — Feature Engineering

- A new `Qtr` column was engineered from the `Month` column using `numpy.where()`:
  - **Q1:** Jan, Feb, Mar
  - **Q2:** Apr, May, Jun
  - **Q3:** Jul, Aug, Sep
  - **Q4:** Oct, Nov, Dec
- This enables time-series style analysis at a quarterly granularity without needing actual date parsing.

---

###  7. Quarter-wise Sales Comparison (2015 vs 2016)

- **Q3 had the highest sales** in 2016, crossing ~$7.5 million — the peak quarter of the year.
- **Q4 was the second highest** in 2016, showing strong year-end performance (~$7.4 million).
- In 2015, **Q1 was the weakest quarter** with sales just above $5 million, while 2016 Q1 grew significantly.
- **Every single quarter in 2016 outperformed the same quarter in 2015** — consistent growth throughout the year.
- The gap between 2015 and 2016 was **widest in Q3 and Q4**, suggesting a stronger second-half push in 2016 — possibly driven by new launches or seasonal demand.
- Q2 showed the **least improvement** between years, which may warrant a targeted strategy for the April–June period.

---

###  8. Quarter-wise Tier Composition in 2016

- Across **all 4 quarters (Q1–Q4)**, the tier composition pattern remains **remarkably consistent**:
  - **High-tier dominates** with the largest slice in every quarter.
  - **Out-tier** is the second largest contributor.
  - **Med-tier** ranks third.
  - **Low-tier** has the smallest contribution in all quarters.
- The stability of this composition across quarters suggests that **tier-based sales behavior is consistent year-round** — no major seasonal shifts in which segment contributes the most.
- The **High + Out tier combination** collectively accounts for well over **60–65%** of quarterly sales in 2016 across all quarters.
- This implies that the company's revenue is **heavily dependent on a smaller, premium customer base** — a concentration risk that should be addressed by growing Med and Low tier revenue.

---

### 📊 Overall Summary Statistics (From EDA)

| Metric | 2015 | 2016 |
|---|---|---|
| Mean Sales per Record | $6,135 | $7,998 |
| Max Sales per Record | $145,760 | $168,033 |
| Mean Units per Record | 2.29 | 3.01 |
| Mean Target Achievement | 1.07x | 1.24x |
| Total National Sales | ~$22.75M | ~$29.66M |

- Average **sales per transaction grew by ~30%** from 2015 to 2016.
- Average **units per transaction also increased** from 2.29 to 3.01, showing both volume and value growth.
- The **target achievement ratio improved** from 1.07x to 1.24x — meaning the sales force was 24% above target on average in 2016, up from 7% in 2015.
- The data contains **negative sales values** (returns/refunds), which were handled by filtering/clipping during visualization.

---

##  Tech Stack

| Library | Version | Usage |
|---|---|---|
| Python | 3.12 | Core language |
| Pandas | Latest | Data loading, groupby, pivot, reshape |
| NumPy | Latest | Quarter feature engineering with `np.where()` |
| Matplotlib | Latest | Bar charts, Pie charts, subplots |
| Seaborn | Latest | FacetGrid, styled bar charts |
| Jupyter Notebook | Latest | Interactive development |

---

##  Installation & Setup

### 1. Clone the repository
```bash
git clone https://github.com/vikasnagar31/pharma-sales-visualization.git
cd pharma-sales-visualization
```

### 2. Install required libraries
```bash
pip install pandas numpy matplotlib seaborn jupyter

---

##  Recommendations Based on Analysis

1. **Focus on West Region** — it has the lowest sales share (24.3%) despite positive growth; targeted campaigns could unlock significant revenue.
2. **Investigate NY decline** — the only East-region state to decline in 2016; understanding root causes is critical to prevent further loss.
3. **Address High-tier unit decline** — revenue grew but units fell in some High-tier divisions; monitor for customer churn risk.
4. **Strengthen Q2 performance** — Q2 showed the smallest YoY improvement; consider mid-year promotional strategies.
5. **Diversify revenue base** — over 60% of revenue comes from High + Out tiers only; growing Med and Low segments will reduce concentration risk.

---
