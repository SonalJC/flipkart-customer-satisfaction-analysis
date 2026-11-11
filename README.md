# Flipkart Customer Satisfaction Analysis

EDA of 85,907 customer-support tickets to find what drives customer satisfaction (CSAT). 82.5% of customers were satisfied (CSAT 4-5).

## Dataset
`Customer_support_data.csv` (85,907 rows, 20 columns). Not included in this repo; download it and update the `path` in the notebook.

## What I did
- Cleaned data: dropped identifiers and a column that was 99.7% empty, converted ~80% missing columns into flags (`has_order_info`, `has_city_info`, `Price_known`), parsed day-first dates correctly
- Engineered response time (minutes), response-time buckets, report hour and weekday
- Compared % satisfied across channel, issue category, product category, agent shift, tenure, manager, hour and weekday

## Key findings
- **Response time:** satisfaction falls as replies get slower (<=2 min: [X]% vs >4 hr: [Y]%)
- **Channel:** Email is weakest (73.5%) vs Inbound (82.7%) and Outcall (83.2%)
- **Product category:** Furniture (66.0%), Mobile (66.6%), Home Appliances (68.3%) are far below the 82.5% average
- **Managers:** 79.3% (William Kim) to 86.1% (Emily Chen)
- **Trend:** satisfaction rose from ~80.6% (1 Aug) to ~85-86% in late August
- **Weekday:** no real effect (82.1% to 83.3%)

## Recommendations
Set a response-time target (e.g. 15 minutes) and escalate tickets waiting over 4 hours; review the Email support process; focus on returns and installation issues for Furniture, Mobile and Home Appliances; share best practices from the top-performing team.

## Limitations
Findings are associations, not proven causes. The data has no information on whether the issue was resolved, and covers one month (Aug 2023).

## Tech stack
Python, Pandas, NumPy, Matplotlib, Seaborn
