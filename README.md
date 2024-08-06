# blinkit-Dashboard

### Dashboard Link : https://mujmanipal-my.sharepoint.com/:u:/g/personal/mahak_2214508371_mujonline_edu_in/EZhIsC0HOsJAiK6Ar-n7IKcBVjYMxAoiio55nAzMVbBTkQ?e=njKeRt

## Problem Statement

Our company aims to enhance its sales performance analysis by leveraging visual data representations. The current dashboard provides an overview of sales data, including total sales, average sales, number of items sold, outlet location performance, and item type performance. However, we need to identify key insights and trends to make informed business decisions. The goal is to:

Analyze Sales Trends: Identify patterns in total sales, average sales, and the number of items sold over different periods.
Evaluate Outlet Performance: Compare the performance of various outlet locations to determine high-performing and underperforming areas.
Assess Product Performance: Understand which product types contribute most to sales and identify potential areas for improvement.
By addressing these points, we aim to optimize our sales strategies and improve overall business performance.


### Steps followed 

- Let's break this down step-by-step:

Data Preparation:

Import your data into Power BI
Ensure you have tables for sales, items, outlets, and ratings


Creating Measures (DAX formulas):

Total Sales: Total Sales = SUM(Sales[Amount])
Avg Sales: Avg Sales = AVERAGE(Sales[Amount])
No. of Items: No. of Items = DISTINCTCOUNT(Items[ItemID])
Avg Rating: Avg Rating = AVERAGE(Ratings[Rating])


Building Visuals:
a. Cards: Create cards for Total Sales, Avg Sales, No. of Items, and Avg Rating

b. Line Chart (Outlet Establishment):
X-axis: Year
Y-axis: Count of outlets
DAX for yearly outlet count: Outlets by Year = COUNTROWS(FILTER(Outlets, Outlets[EstablishmentYear] = SELECTEDVALUE(Calendar[Year])))

c. Donut Charts:
Fat Content: Group items by fat content, use count or sum of sales
Outlet Location: Group by location type, use count of outlets

d. Bar Chart (Item Type):
Y-axis: Item categories
X-axis: Total sales for each category
DAX: Sales by Category = CALCULATE([Total Sales], ALLEXCEPT(Items, Items[Category]))

e. Table (Outlet Type):
Columns: Outlet Type, Total Sales, No. of Items, Avg Sales, Avg Rating, Item Visibility
Use measures created earlier and calculate Item Visibility as needed


Filters and Slicers: Add slicers for Outlet Location Type, Outlet Size, and Item Type


Formatting: Apply yellow theme
Adjust fonts, colors, and layout to match the image


DAX for Tier Calculations:
Create a calculated column for Tiers based on sales or other criteria
Example: Tier = IF([Total Sales] > 400000, "Tier 3", IF([Total Sales] > 350000, "Tier 2", "Tier 1"))


Insights from the dashboard:

Sales Performance:
Total sales are $0.34M with an average of $141 per sale
Fruits and vegetables, and snack foods are top-selling categories

Product Mix:
There's a balance between low fat and regular fat items
Wide variety of product types available (2388 items)

Outlet Performance:
Supermarkets have higher total sales and average item visibility compared to grocery stores
There's a decline in outlet establishments from 2016 to 2018

Customer Satisfaction:
Average rating of 3.9 suggests generally positive customer experiences

Location Analysis:
Medium-sized locations dominate, followed by small and high-tier locations
Tier 3 locations contribute the most to sales

Trends:
The line chart shows a significant drop in outlet establishments after 2016, which might require further investigation

## Raw data file link: https://1drv.ms/x/c/30e75f7a37b4c5ed/EdAPq-gTwABJj_wvVzq2LYUBRwa3B0Qq_1TmwG5bzrsqvg?e=2ihlq0
