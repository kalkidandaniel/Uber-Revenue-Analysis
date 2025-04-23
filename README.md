# Uber & Online Retail Data Analysis
## Data Cleaning & Transformation

#### * Executive Summary

Overview of Findings

This analysis combines Uber ride request data with online retail transaction records to uncover patterns in transportation demand and customer purchasing behavior. By cleaning, augmenting, and merging both datasets, we uncovered trends that reflect user engagement across industries. Key findings include the dominance of peak ride times during weekday commuting hours, elevated wait times for airport pickups, and significant sales contributions from high-spending customers. Notably, a correlation was observed between ride demand peaks and high retail spending windows, presenting opportunities for joint marketing and operational optimization.

The visual below summarizes part of the insights generated; more examples and interactive elements are available throughout this report.


#### * Data Structure

<table>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/47b7e0b0-029a-4e8d-9e0b-3fb4b598e169" width="400"/></td>
    <td><img src="https://github.com/user-attachments/assets/6f90101f-48dc-4dbe-885f-123eaba837e6" width="400"/></td>
  </tr>
</table>

#### * Data Cleaning & Preparation (CLEAN Framework)


<table >
  <tr>
    <td width="300">✅ Conceptualize
Grain: Individual transactions and ride requests
Measures: Quantity, TotalPrice, wait time
Dimensions: Date, time, location, customer, category 
Critical Columns: InvoiceDate, RequestTime, UnitPrice, Status, CustomerID
</td>

  
 <td width="300">🔍 Locate Issues
Missing CustomerIDs and DriverIDs
Inconsistent timestamp formats
Duplicate invoices and ride requests
</td>

 <td width="300">⚠️ Evaluate Unsolvable Issues
Dropped records with missing CustomerID (Retail) or DriverID (Uber)
Retained rows with essential timestamps for trend analysis
</td>

 <td width="300">🔧 Augment
Online Retail: TotalPrice, InvoiceHour, InvoiceDay, CustomerSegment
Uber: RequestHour, RequestDay, PeakHourTag
</td>

 <td width="300">📝 Note & Document
Detailed logs maintained for all cleaning and transformation steps
</td>

  </tr>
</table>

### * Data Augmentation & Merging

🧩 Augmentation

##### Uber Dataset:
request_hour, request_day, request_month: extracted from timestamps
peak_hour: tagged based on defined peak ride times (7–9 AM, 5–8 PM)

##### Retail Dataset:
TotalPrice: calculated as Quantity × UnitPrice
invoice_hour, invoice_day, invoice_month: from InvoiceDate
CustomerSegment: categorized by total spend (e.g., Low, Medium, High Spenders)

##### 🔗 Merging Strategy
Datasets merged using date components to align ride and purchase behaviors
Final dataset: 13,810,205 rows and 23 columns

### * Key Insights
   
<table >
  <tr>
    <td width="300">🚕 Uber Ride Patterns
Peak hours: 7–9 AM and 5–8 PM
Airport pickups had longer average wait times
Higher ride volume on weekdays compared to weekends
</td>

  
 <td width="300">🛍️ Retail Sales Insights
High Spenders generated a disproportionate share of revenue
Sales peaked during weekdays and holiday months
Top-selling product categories were clustered around business hours
</td>

 <td width="300">🔗 Integrated Insights
A significant overlap was observed between high retail transactions and peak Uber ride hours
Weekday evenings showed the strongest correlation between both datasets
</td>

  </tr>
</table>

### * Visualizations
##### Total Sales per Month – Bar chart visualizing revenue trends
##### Uber Requests by Hour – Heatmap of hourly ride volumes
##### Customer Segmentation – Pie chart showing spend tiers
##### Uber vs. Retail Trends – Dual-axis comparison of ride volume and sales

## * Recommendations
#### - Optimize Driver Allocation at Airports
Given the higher wait times observed at airport pickup points, Uber can improve service efficiency by reallocating more drivers to airports during peak hours. Predictive scheduling models based on historical request patterns would help minimize passenger wait time and enhance customer satisfaction.

#### - Leverage Cross-Industry Promotions During Peak Hours
Since both Uber ride demand and retail purchases spike during similar timeframes—particularly weekday evenings—coordinated promotions (e.g., ride discounts linked to retail spending) could drive customer engagement across both platforms, benefiting partner retailers and boosting ride frequency.

#### - Enhance Customer Targeting Through Segmentation
The “High Spender” customer segment contributed disproportionately to retail revenue. Targeted marketing campaigns focusing on these users, especially during peak ride hours, could lead to increased conversion rates and customer lifetime value.

#### - Develop Integrated Real-Time Dashboards
To sustain continuous improvement, it’s essential to develop dashboards that combine retail and ride-sharing metrics. Real-time visualization would help operational teams detect trends early, make agile decisions, and respond to customer behavior shifts more effectively.


