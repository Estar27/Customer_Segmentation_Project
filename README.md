#  Customer Segmentation For Automobile Manufacturing Company

## Table Of Contents
- [Project Overview](#project-overview)
- [Data Set](#dataset)
- [Tools and Techniques](#tools-and-techniques)
- [Data Extraction, Cleaning/ Modelling](#data-extraction-cleaning-modelling)
- [RFM Analysis](#rfm-analysis)
- [Exploratory Data Analysis](#eda-on-rfm-dataset)
- [K-Means Clustering](#k-means-clustering-analysis)
- [Visualization](#visualization)
- [Insights](#recommendations)
- [Marketing Recommendations](#marketing-recommendateions)
- [Limitations](#limitations)
- [References](#references)


## Project Overview
The Customer Segmentation project aims to identify key customer groups and predict future purchasing behaviors for a prominent automobile manufacturer that is experiencing a significant decline in sales among young professionals. This decline is largely attributed to a lack of personalized customer experiences and ineffective customer relationship management. By utilizing RFM (Recency, Frequency, Monetary) analysis to evaluate customer engagement and K-Means clustering for segmentation, this project is designed to help the company better understand its customer base. The analysis focuses on uncovering customer preferences, spending habits, and overall value, enabling the development of tailored marketing strategies. The insights derived from this project will empower stakeholders to make informed decisions regarding targeted promotions and customer outreach initiatives. Ultimately, this will address the decline in sales, improve engagement with the young professional segment, and enhance overall customer retention.
![CustomerSegment](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/Clusters_Of_Customers.png?raw=true)

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
In the Customer Segmentation project, the following steps were followed for data extraction and cleaning:
- **Extraction**: Used Python to extract each worksheet from the Excel workbook separately.
- **Data Type Conversion**: Identified and corrected data type issues for various columns to ensure accurate processing and analysis.
- **New Column Creation**: Created new columns for age, age group, and profit to assist with further analysis.
- **Null and Duplicate Check**: Checked for null values and duplicates across the datasets, correcting any issues found to ensure data integrity.
- **Data Standardization**: Standardized entries by inspecting value counts for each column using the .value_counts() function. Rectified discrepancies in representations, such as correcting the state column where "vic" and "victoria" were treated as different entries even though they refer to the same state.
![datastand](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/datastandastate.png?raw=true)
- **Final Data Validation**: Conducted a thorough review of the cleaned dataset to ensure all transformations were correctly applied and the data was ready for analysis.
This process ensured that the data was properly structured and clean for further analysis.

## RFM Analysis:
Performed RFM (Recency, Frequency, Monetary) analysis to segment customers based on their purchasing behaviors.
- **Recency**: Used the MAX function to obtain the last invoice date for each customer and calculated recency by subtracting each customer's invoice date from this maximum date. This measures how recently customers made their last purchase.
- **Frequency**: Employed the COUNT function on the invoice dates to determine how frequently customers purchase from the company, providing insights into customer loyalty.
- **Monetary Value**: Applied the SUM function on the calculated profit column to derive the total spending of each customer, allowing evaluation of overall value to the business.
This streamlined dataset, focused on key RFM metrics, enhances the analysis process and improves the effectiveness of customer segmentation into clusters
![RFM](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/code_rfm.png?raw=true)

## EDA on RFM Dataset:
Conducted exploratory data analysis (EDA) on the RFM dataset to uncover insights into customer behaviors, identify data quality issues, and prepare the dataset for further analysis or modeling.
- **Outlier Detection**: Employed histograms and subplot visualizations to analyze the distribution of each RFM metric.
  - Implementation: Created histograms for each metric to visualize the frequency distribution and identify any extreme values that deviate significantly from the norm. Used subplots to compare the distributions side by side, facilitating a comprehensive examination of potential outliers.
![outliers](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/Outliers1.png?raw=true)
![outliers2](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/Outliers2.png?raw=true)
- **Descriptive Analysis**: Utilized the .describe() function from the Pandas library on the RFM dataset to compute summary statistics.
  - Implementation: Generated key metrics including count, mean, standard deviation, minimum, maximum, and quartiles for each RFM variable, Evaluated the central tendency (mean and median) to understand typical customer behaviors and the spread (standard deviation and interquartile range) to assess variability within the dataset. This analysis provided clarity on the overall customer base, revealing patterns such as the average frequency of purchases and typical monetary expenditure, which informed subsequent segmentation strategies.
![describe](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/edaonrfm.png?raw=true)
- **Visualization**: Created a 3D scatter plot to visualize the relationships and distributions among the RFM metrics.
  - Implementation: Plotted Recency on one axis, Frequency on another, and Monetary Value on the third, allowing for an in-depth exploration of how these dimensions interact.


## K-means Clustering Analysis:
Implemented K-means clustering to segment customers based on their RFM metrics, facilitating targeted marketing strategies and personalized customer engagement.
- **Optimal Cluster Determination**: Used the Elbow Method and Silhouette Score to identify the optimal number of clusters for the dataset. Plotted both the Elbow Curve and Silhouette Scores to visually assess cluster compactness and separation.
    - The Elbow Method involved graphing the sum of squared distances between data points and their corresponding cluster centroids, looking for the “elbow” point where adding more clusters yields diminishing returns.
    - The Silhouette Score assessed the quality of clustering by measuring how similar an object is to its own cluster compared to other clusters.
![SILELB](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/Code_sil_Elb.png?raw=true)
![CHART](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/Silhouette_Elbow.png?raw=true)
The analysis revealed the most appropriate number of clusters to use for K-means, ensuring meaningful segmentation of customers.
- **K-means Clustering**:
Applied the `kmeans.fit_predict()` method on the RFM dataset to assign cluster labels to each customer. Then, Appended the cluster labels to the RFM dataset, indicating which cluster each customer belongs to, thus enabling easy identification of customer segments.
- **Visualization**: Created a 3D scatter plot to visualize the distribution of customers among the identified clusters. Used color coding based on cluster assignments to facilitate pattern recognition and better understand customer distribution across different segments.
![KM](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/code_kmeans_fit.png?raw=true)
![CD](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/code_cluster.png?raw=true)
![CustomerSegment](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/Clusters_Of_Customers.png?raw=true)
- **Cluster Analysis**: Generated three violin plots to further analyze the attributes of each cluster based on Recency, Frequency, and Monetary Value. The violin plots illustrated the distribution of RFM metrics within each cluster, revealing key characteristics of customer segments.
- **Cluster Labeling**:
 Assigned descriptive labels to each cluster based on insights from the violin plots:
  - **Cluster 0**: Premium 
  - **Cluster 1**: Casual 
  - **Cluster 2**: Dormant 
  - **Cluster 3**: Active
Each label reflected the purchasing behaviors and attributes visible in the corresponding metrics.
- **Customer Distribution Analysis**: Created a bar plot to display the total number of customers in each cluster, showcasing their average Recency, Frequency, and Monetary Value. This visualization provided a clear overview of the customer distribution across segments, allowing us to understand customer profiles and segment sizes at a glance.


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
