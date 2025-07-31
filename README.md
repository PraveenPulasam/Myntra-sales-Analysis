 Myntra Sales Analysis Dashboard
This project presents a comprehensive sales analysis dashboard for Myntra, a popular fashion e-commerce platform in India. Built using Power BI, the dashboard visualizes sales data to extract actionable business insights, track performance, and understand customer behavior across multiple dimensions.

 Project Overview
The goal of this project is to:

Analyze sales trends across categories and time periods.

Understand gender-based purchasing behavior.

Identify top-performing cities and brands.

Provide an interactive and visually rich dashboard for stakeholders.

 Key Insights
 Gender Sales Shift:
Men's products led in sales during 2021, but in 2022, the women’s category took the lead.

 Quarterly Sales Drop:
Sales decreased from Q1 to Q2 across all major categories:

Men: ↓ 29%

Women: ↓ 34%

Kids: ↓ 18%

Beauty: ↓ 27%

 Consistent Rankings:
Sales rankings by category remained unchanged quarter to quarter.

 Top Cities:

Ahmedabad in Gujarat

Bengaluru in Karnataka
These cities recorded the highest order volumes in their respective states.

 Brand Discount Analysis:
The Cantabil brand gave the least discount on women’s jeans—valuable for pricing strategy.

 Peak Sales Day:
Friday emerged as the top day for men’s category sales.

 Dashboard Preview
(You can add a screenshot of your Power BI dashboard here for visual impact)

The dashboard includes interactive visuals with filters by category, state, brand, product, and more.

🛠 Technical Implementation
 Calendar Table using DAX
To enable time-based analysis, a custom calendar table was created using the ADDCOLUMNS and CALENDAR functions in DAX:

Date_table = 
ADDCOLUMNS(
    CALENDAR(MIN(Fact_orders[Date]), MAX(Fact_orders[Date])),
    "Year", YEAR([Date]),
    "Month_Name", FORMAT([Date], "MMM"),
    "Month_id", MONTH([Date]),
    "Day of week", FORMAT([Date], "DDDD"),
    "week id", WEEKDAY([Date])
)

"Clear All Filters" Bookmark
For improved usability, a "Clear All Filters" button was implemented using Power BI's bookmarking feature. This allows users to instantly reset all applied filters and return to the default view of the dashboard with a single click, which enhances the user experience.

Brand and Product Name Hierarchy
To facilitate a multi-level analysis of product performance, a hierarchy was created for Brand Name and Product Name within a matrix visual. This allows users to drill down from a high-level brand view to see the performance of individual products under that brand, providing deeper insights into the product portfolio.

 Future Enhancements
Predictive Analytics: Incorporate forecasting models to predict future sales trends.

Customer Segmentation: Perform RFM (Recency, Frequency, Monetary) analysis to segment customers.

Inventory Management: Integrate inventory data to analyze stock levels and prevent stockouts.
