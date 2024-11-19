#  Customer Segmentation For Automobile Manufacturing Company

## Table Of Contents
- [Project Overview](#project-overview)
- [Data Set](#dataset)
- [Tools and Techniques](#tools-and-techniques)
- [Data Extraction, Cleaning/ Modelling](#data-extraction-cleaning-modelling)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [RFM Analysis](#rfm-analysis)
- [K-Means Clustering](#kmeans-clustering)
- [Visualization](#visualization)
- [Insights](#recommendations)
- [Marketing Recommendations](#marketing-recommendateions)
- [Limitations](#limitations)
- [References](#references)


## Project Overview
The Customer Segmentation project aims to identify key customer groups and predict future purchasing behaviors for a prominent automobile manufacturer that is experiencing a significant decline in sales among young professionals. This decline is largely attributed to a lack of personalized customer experiences and ineffective customer relationship management. By utilizing RFM (Recency, Frequency, Monetary) analysis to evaluate customer engagement and K-Means clustering for segmentation, this project is designed to help the company better understand its customer base. The analysis focuses on uncovering customer preferences, spending habits, and overall value, enabling the development of tailored marketing strategies. The insights derived from this project will empower stakeholders to make informed decisions regarding targeted promotions and customer outreach initiatives. Ultimately, this will address the decline in sales, improve engagement with the young professional segment, and enhance overall customer retention.
[Download Power BI Report](https://github.com/Estar27/PIZZA_SALES_ANALYSIS/blob/main/PIZZA_SALES_REPORT.pbix)

## Dataset
### Raw_data.xlsx
This Excel workbook serves as the primary data source for segmenting the customers.

### Worksheets
The dataset includes the following worksheets:

- **Transactions**: This contains the transaction details of the existing customers of the company, including columns like transaction ID, customer ID, product ID, order status, transaction date, product line, size and class, price, cost, etc.
- **Sheet1**: This contains descriptions of the columns that are in the other worksheets.
- **NewCustomerList**: This contains information about new customers who haven't made a purchase from the company. It includes columns like name, gender, past three years of bike-related purchases, DOB, job title, industry, wealth segment, etc.
- **CustomerDemographic**: This contains demographic information of the existing customers, featuring columns like customer ID, name, gender, past three years of bike-related purchases, DOB, job title, industry, wealth segment, etc.
- **CustomerAddress**: This contains the addresses of the existing customers of the company, which includes columns like address, postcode, state, country, and property valuation


## Tools and Techniques
In this Customer Segmentation project, the following tools and techniques were utilized:

- **Excel**:
Employed for initial data checking and organization. VLOOKUP was used to join the Customer Address worksheet to the Customer Demographic worksheet, ensuring comprehensive dataset integration. [Download here](https://microsoft.com)
- **Python**:
Utilized for data extraction, exploratory data analysis (EDA), RFM analysis, and K-Means clustering. Python provided powerful libraries for data manipulation and analysis, facilitating the identification of customer segments and behaviors. [Download here](https://microsoft.com)
- **Power BI**:
Used for data visualization and reporting. Power BI was instrumental in creating interactive dashboards that provided a visual overview of customer insights, segmentation results, and product analysis, enabling improved decision-making. [Download here](https://microsoft.com)
- **PowerPoint**:
Employed to create a presentation of findings, summarizing insights and providing marketing recommendations based on the analysis. This facilitated effective communication of results to stakeholders. [Download here](https://microsoft.com)


## Data Extraction/ Cleaning/ Modelling  
In the Pizza Sales Analysis project, the following steps were followed for data extraction and cleaning:  
1. **Extraction**:  
   - Used python to extract each worksheets in the workbook.
2. **Data Type Adjustments**:  
   - Encountered issues with the data type of one particular column that prevented successful extraction.
![DataTypeError](https://github.com/Estar27/PIZZA_SALES_ANALYSIS/blob/main/Screenshot%202024-11-04%20140832.png?raw=true) 
   - Changed the data type of the problematic column to a string to facilitate successful import.
![DataTypechange](https://github.com/Estar27/PIZZA_SALES_ANALYSIS/blob/main/Screenshot%202024-10-30%20130422.png?raw=true)
3. **Creating a New Column**:  
   - Created a new column to temporarily hold the values from the old column.  
4. **Data Transfer**:  
   - Transferred all data from the old column to the newly created column.  
5. **Dropping the Old Column**:  
   - Removed the old column from the dataset since it was no longer needed.  
6. **Final Data Type Conversion**:  
   - Converted the data type of the new column to a date format.  
   - Renamed the new column to match the original name of the old column.
![FixError](https://github.com/Estar27/PIZZA_SALES_ANALYSIS/blob/main/Screenshot%202024-10-30%20134044.png?raw=true)

This process ensured that the data was properly structured and clean for further analysis in Power BI.

## Exploratory Data Analysis  
The Exploratory Data Analysis involved using SQL to explore the pizza sales dataset to answer key questions, including:  
1. **Total Revenue**  
2. **Average Order Value**  
3. **Total Pizzas Sold**  
4. **Total Orders**  
5. **Average Pizza Per Order**  
6. **Daily Trend of Total Orders**  
7. **Monthly Trend of Total Orders**  
8. **Percentage of Sales by Pizza Category**  
9. **Top 5 Pizzas by Revenue by order, quantity and revenue**
10. **Bottom 5 Pizzas by order, quantity and revenue**
[Download the Word Document](https://github.com/Estar27/PIZZA_SALES_ANALYSIS/blob/main/PIZZA%20SQL%20RESULTS%20AND%20QUERY.docx)

These analyses provided valuable insights into sales performance and customer purchasing behavior.

## Visualization  
In this project, several visualizations were created to effectively communicate the insights from the pizza sales data:  
- **Bar Chart**: Displays the top 5 and bottom 5 pizzas based on order quantity and revenue.  
- **Line Graph**: Illustrates the monthly trend of total orders.  
- **Stacked Column Chart**: Depicts the daily trend of total orders.  
- **Doughnut Chart**: Represents the percentage of sales by pizza category and size.

![Visualization](https://github.com/Estar27/PIZZA_SALES_ANALYSIS/blob/main/Screenshot%202024-11-04%20143103.png?raw=true)

![Visualization2](https://github.com/Estar27/PIZZA_SALES_ANALYSIS/blob/main/Screenshot%202024-11-04%20143145.png?raw=true)
These visualizations facilitate a better understanding of sales performance and customer preferences.


## Results/ Findings  

The findings from the analysis can be summarized as follows:  
- **Fridays** and **Thursdays** has higher orders.
- **July** and **May** recorded higher orders.
- **Top 5 Pizzas by Order**:   
  1. Classic Deluxe  
  2. Hawaiian  
  3. Pepperoni  
  4. Barbecue Chicken  
  5. Thai Chicken Pizza  
- **Bottom 5 Pizzas by Order**:   
  1. Chicken Pesto  
  2. Spinach Supreme  
  3. Calabrese  
  4. Mediterranean  
  5. Brie Carré Pizza  
- **Top 5 Pizzas by Quantity**:   
  1. Classic Deluxe  
  2. Barbecue Chicken  
  3. Thai Chicken  
  4. California Chicken  
  5. Spicy Italian Pizza  
- **Bottom 5 Pizzas by Quantity**:   
  1. Green Garden  
  2. Spinach Pesto  
  3. Spinach Supreme  
  4. Mediterranean  
  5. Brie Carré Pizza  
- **Top 5 Pizzas by Revenue**:   
  1. Thai Chicken  
  2. Barbecue Chicken  
  3. California Chicken  
  4. Classic Deluxe  
  5. Spicy Italian Pizza  
- **Bottom 5 Pizzas by Revenue**:   
  1. Spinach Pesto  
  2. Mediterranean  
  3. Spinach Supreme  
  4. Green Garden  
  5. Brie Carré Pizza  
These results provide valuable insights into customer preferences and sales performance for the various pizza offerings.

## Limitations  
- **Temporal Limitations**: While the data spans a year, it may not adequately capture seasonal trends or variations in consumer behavior across different months.    
- **Geographical Limitations**: The findings may not be applicable to other locations or markets outside the dataset.    
- **Market Behavior Changes**: Shifts in consumer preferences over the years, influenced by trends, may not be fully reflected in the analysis.

## Recommendations  
1. **Promote Top Sellers**:  
   - Focus marketing efforts on high-performing pizzas, such as Classic Deluxe and Pepperoni. Offer special deals to boost sales.  
2. **Revise Underperformers**:  
   - Analyze and adjust recipes for low-selling pizzas, and consider promotions to increase awareness and sales.  
3. **Seasonal Promotions**:  
   - Introduce limited-time offerings during holidays or peak seasons, and monitor their performance for future adjustments.  
4. **Diversify Menu Options**:  
   - Expand the menu to include vegetarian, gluten-free, and vegan pizzas in response to consumer trends.  
5. **Focus on High-Revenue Items**:  
   - Highlight and promote high-revenue pizzas like Thai Chicken in advertising to maximize sales.  
6. **Cross-Sell Opportunities**:  
   - Implement strategies to suggest complementary sides and drinks during customer orders to increase average transaction value.  
7. **Data-Driven Insights**:  
   - Continuously analyze sales data to quickly adapt strategies based on customer behavior and market trends.  
By adopting these strategies, the company can enhance its offerings, improve customer satisfaction, and drive growth.

## References

1. [Youtube](https://www.youtube.com/watch?v=V-s8c6jMRN0&list=PPSV)
2. [Udemy](https://www.udemy.com/course/complete-microsoft-sql-server-beginner-expert/learn/lecture/22126612#content)

💻 🖱️ 👁️
