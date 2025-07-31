#  Myntra Sales Analysis Dashboard

This project presents a comprehensive sales analysis dashboard for **Myntra**, a popular fashion e-commerce platform in India. Built using **Power BI**, the dashboard visualizes sales data to extract actionable business insights, track performance, and understand customer behavior across multiple dimensions.

---

##  Project Overview

The goal of this project is to:

- Analyze sales trends across categories and time periods.
- Understand gender-based purchasing behavior.
- Identify top-performing cities and brands.
- Provide an interactive and visually rich dashboard for stakeholders.

---

##  Key Insights

- ** Gender Sales Shift:**  
  Men's products led in sales during 2021, but in 2022, women’s category took the lead.

- ** Quarterly Sales Drop:**  
  Sales decreased from Q1 to Q2 across all major categories:  
  - Men: ↓ 29%  
  - Women: ↓ 34%  
  - Kids: ↓ 18%  
  - Beauty: ↓ 27%

- ** Consistent Rankings:**  
  Sales rankings by category remained unchanged quarter to quarter.

- ** Top Cities:**  
  - **Ahmedabad** in Gujarat  
  - **Bengaluru** in Karnataka  
  These cities recorded the highest order volumes in their respective states.

- ** Brand Discount Analysis:**  
  The **Cantabil** brand gave the **least discount** on women’s jeans—valuable for pricing strategy.

- ** Peak Sales Day:**  
  **Friday** emerged as the top day for men’s category sales.

---

##  Dashboard Preview

<<img width="1050" height="487" alt="Myntra ss (2)" src="https://github.com/user-attachments/assets/783e3b10-a665-410f-94dc-746df4c61f67" />
/>
The dashboard includes interactive visuals with filters by category, state, brand, product, and more.

---

## 🛠 Technical Implementation

###  Calendar Table using DAX

To enable time-based analysis, a custom **calendar table** was created using the `ADDCOLUMNS` and `CALENDAR` functions in DAX:

```dax
Date_table = 
ADDCOLUMNS(
    CALENDAR(MIN(Fact_orders[Date]), MAX(Fact_orders[Date])),
    "Year", YEAR([Date]),
    "Month_Name", FORMAT([Date], "MMM"),
    "Month_id", MONTH([Date]),
    "Day of week", FORMAT([Date], "DDDD"),
    "week id", WEEKDAY([Date])
)
