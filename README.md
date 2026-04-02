# Brazilian E-Commerce Data Analysis

Analysis of **99,441 orders** from the [Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) e-commerce platform (2016–2018), exploring order volume trends, delivery performance, customer retention, and cohort behavior.

---

## Business Questions Answered

- When do customers order most, and what drives seasonal spikes?
- How reliable is the delivery process — and how wide is the variance?
- What does cohort retention look like across the customer base?
- Are there structural data limitations that affect how metrics are interpreted?

---

## Key Findings

| Metric | Finding |
|--------|---------|
| Total orders | 99,441 across Sep 2016 – Oct 2018 |
| Peak month | November 2017 — 7,544 orders (Black Friday effect) |
| Mean delivery time | 11.9 days |
| Median delivery time | 10.0 days |
| Max delivery time | 209.8 days |
| Apparent repeat purchase rate | ~0% — explained by data structure (see below) |

---

## Analysis Highlights

### Order Volume Trends
- Steady growth from 4 orders in Sep 2016 to 7,000+ monthly by early 2018
- Clear November 2017 spike driven by Black Friday promotions
- Plateau in mid-2018 suggests market maturation

### Delivery Performance
- Mean (11.9 days) vs. median (10.0 days) gap indicates a right-skewed distribution
- Long tail of extreme outliers — max delivery of 209.8 days pulls the mean up significantly
- Most orders (>70%) delivered within 15 days

### Cohort & Retention Analysis
- Built cohort matrix tracking months since first purchase per customer
- All cohort retention values show 1.0 at month 0 (as expected)
- Apparent 0% repeat purchase rate is a **data artifact**: the dataset assigns a unique `customer_id` per order, not per person — meaning repeat buyers appear as new customers in the data

---

## Data Limitation

> The Olist dataset generates a new `customer_id` for each order rather than tracking a persistent user identity. As a result, true repeat purchase behavior **cannot be measured** from this dataset alone. Any repeat rate calculation using `customer_id` will return ~0% and should not be interpreted as actual churn or retention.

---

## Dataset

- **Source:** [Olist Brazilian E-Commerce Public Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) via Kaggle
- **Size:** 99,441 orders, 8 columns
- **Period:** September 2016 – October 2018
- **Missing values:** `order_delivered_carrier_date` (160), `order_delivered_customer_date` (2,965)

---

## Skills Demonstrated

- **Python:** Pandas, Matplotlib, NumPy
- **Data Cleaning:** Datetime parsing, null handling, type conversion
- **Exploratory Data Analysis:** Time series, distribution analysis, cohort construction
- **Statistical Analysis:** Mean vs. median interpretation, skewness, outlier identification
- **Data Visualization:** Line charts, histograms with reference lines, cohort matrices
- **Critical Thinking:** Identifying and documenting data structure limitations

---

## How to Run

```bash
git clone https://github.com/Nanacui61/ecommerce-data-analysis.git
cd ecommerce-data-analysis
jupyter notebook ecommerce_data_analysis.ipynb
```

---

## Author

**Yuqian (Nana) Cui** — CS + Economics, Boston University  
[GitHub](https://github.com/Nanacui61)
