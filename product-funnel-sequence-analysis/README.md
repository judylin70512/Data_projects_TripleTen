# Product Funnel Sequence Analysis

## Business Problem

Understanding how users move through a purchase funnel is essential for improving conversion rates.
However, traditional funnel calculations often count users who reached each stage regardless of the order of events, which can overestimate product performance.

This project analyzes user event data to compare a **Simple Funnel** calculation with a **Sequence Funnel** that enforces the correct event order.

---

## Analysis

The funnel consists of four stages:

pageview → add_to_cart → checkout → payment

The analysis was conducted in three steps:

* Create a pivot table to calculate the **earliest event time for each user and funnel stage**
* Use logical formulas to validate whether users followed the correct event sequence
* Compare conversion rates between a **Simple Funnel** and a **Sequence Funnel**

---

## Funnel Results

### Simple Funnel

| Stage       | Users | Conversion |
| ----------- | ----- | ---------- |
| pageview    | 1084  |            |
| add_to_cart | 802   | 74%        |
| checkout    | 272   | 34%        |
| payment     | 97    | 36%        |

### Sequence Funnel

| Stage       | Users | Conversion |
| ----------- | ----- | ---------- |
| pageview    | 1084  |            |
| add_to_cart | 637   | 58.8%      |
| checkout    | 191   | 30.0%      |
| payment     | 77    | 40.3%      |

---

## Key Insights

• The **Simple Funnel overestimates conversion rates** because it counts users who reached stages regardless of event order.

• When enforcing the correct sequence of events:

* add_to_cart decreases from **802 → 637 users**
* checkout decreases from **272 → 191 users**
* payment decreases from **97 → 77 users**

• The largest drop-off occurs between **Add to Cart and Checkout**, where only about **30% of users continue to the next stage**.

This suggests potential friction during checkout initiation, such as pricing surprises, UX issues, or account creation requirements.

---

## Analysis Preview

![Funnel Analysis](dashboard.png)

---

## Repository Structure

```
product-funnel-sequence-analysis
│
├── event_sequence_funnel_analysis.xlsx
├── funnel_result.png
└── README.md
```

The Excel file contains:

* Raw event data
* Pivot table for earliest event timestamps
* Sequence validation logic using formulas
* Final funnel summary and conversion calculations

---

## Files

[event_sequence_funnel_analysis.xlsx]（product-funnel-sequence-analysis/event_sequence_funnel_analysis.xlsx）

---

## Tools

* Excel / Google Sheets
* Pivot tables
* Logical formulas (AND, COUNTIF)
* Funnel analysis

---

## Skills Demonstrated

* Product funnel analysis
* User behavior analysis
* Event sequence validation
* Conversion rate analysis
* Business insight generation

