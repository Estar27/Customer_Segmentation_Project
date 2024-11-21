#  Customer Segmentation For Automobile Manufacturing Company

## Table Of Contents
- [Project Overview](#project-overview)
- [Data Set](#dataset)
- [Tools and Techniques](#tools-and-techniques)
- [Data Extraction, Cleaning/ Modelling](#data-extraction-cleaning-modelling)
- [RFM Analysis](#rfm-analysis)
- [Exploratory Data Analysis](#eda-on-rfm-dataset)
- [K-Means Clustering](#k-means-clustering-analysis)
- [PowerBI Visualization](#powerbi-visualization)
- [Insights](#insights)
- [Marketing Recommendations](#marketing-recommendations)
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
![1](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/code_violin.png?raw=true)
![2](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/violin_plot1.png?raw=true)
![3](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/violin_plot2.png?raw=true)
![4](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/violin_plot3.png?raw=true)
- **Cluster Labeling**:
 Assigned descriptive labels to each cluster based on insights from the violin plots:
  - **Cluster 0**: Premium 
  - **Cluster 1**: Casual 
  - **Cluster 2**: Dormant 
  - **Cluster 3**: Active
Each label reflected the purchasing behaviors and attributes visible in the corresponding metrics.
- **Customer Distribution Analysis**: Created a bar plot to display the total number of customers in each cluster, showcasing their average Recency, Frequency, and Monetary Value. This visualization provided a clear overview of the customer distribution across segments, allowing us to understand customer profiles and segment sizes at a glance.
![](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/code_avg_rfm.png?raw=true)
![](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/avg_rfm.png?raw=true)

## PowerBI Visualization
In this project, the dataset containing the RFM (Recency, Frequency, Monetary) values and cluster labels was imported, along with the primary dataset called raw_data.xlsx. Data modeling was performed to establish relationships between these datasets to facilitate effective visualization. The visuals used in this project are as follows:

- **Cards**: Displays Key Performance Indicators, such as total profit, total number of customers, and total sales.
- **Line Graph**: Illustrates the quarterly trend of total profit.
- **Line and Stacked Column Chart**: Depicts the average recency, frequency, and monetary value for each cluster.
- **Pie Chart/Doughnut Chart**: Represents the distribution of total customers by gender and the percentage of sales by different product quality.
- **Stacked Column Chart**: Illustrates customer tenure, total transactions by clusters, and profit by product line.
- **Funnel Chart**: Displays the average sales made by each cluster.
- **Ribbon Chart**: Shows the number of customers in each cluster from different states.
- **100% Stacked Column Chart**: Depicts the different age categories represented in each cluster.
- **Treemap**: Displays total sales made by customers in different wealth segments.
![Visualization](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/pb_1.png?raw=true)
![Visualization2](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/pb_2.png?raw=true)
![Visualization3](https://github.com/Estar27/Customer_Segmentation_Project/blob/main/pb_3.png?raw=true)
These visualizations facilitate a better understanding of cluster's performance and customer preferences.


## Insights
After a detailed analysis and clustering of the customer data, the following insights were obtained:
- The company's customers can be grouped into four categories based on their purchasing behavior: **Premium, Casual, Dormant, and Active**.
- The **Premium and Active** segments are the most loyal to the brand and contribute the majority of the total revenue for the company.
- The **Premium** customers, while the best-performing group, represent only **16.1%** of the total customer base.
- The **Dormant and Casual** segments exhibit the least loyalty to the brand and contribute a minority to the total revenue.
- The** Dormant** group is the lowest-performing segment, making up **31.8%** of the total customer base, which negatively affects the company's sales performance.
- **Active** customers constitute the largest percentage **37.3%** of the customer base, while **Casual** customers represent the smallest percentage **14.8%**.
- The best-performing product line in terms of profit generated is **Standard**, while the top-performing product quality by total sales is **Medium**.
- There has been a significant increase in profit trend, with **Quarter 4** generating the highest profit for the company at over **$2,700,000**, contributing to a total of $10,600,000 generated for the year.
- The majority of customers have been with the company for **less than a year** and fall within the **Mass Customer** wealth segment.
- Most customers reside in **New South Wales**.


## Marketing Recommendations
From the Insights gotten from the the analysis and clustering the customers, the following marketing strategies are recommended to help improve the ales performance for the company and build a good customer relationship management.
- **Premium Customers**: Since these customers are your most loyal and best performing, the follwing strategies will help to retain them, turning them into advocates for your brand and further enhancing their loyalty:
  - *Tailored Communication*: Send personalized emails that highlight their purchase history.
  - *VIP Treatment*: Offer exclusive access to new products and consider assigning dedicated account managers.
  - *Tiered Loyalty Rewards*: Enhance loyalty programs with exclusive rewards for high-value customers.
  - *Direct Feedback*: Solicit insights through surveys or interviews to understand their experiences.
  - *Proactive Support*: Follow up after purchases to provide relevant assistance.
  - *Exclusive Events*: Host product launches and workshops specifically for them.
  - *Behind-the-Scenes Access*: Offer sneak peeks of new products and initiatives.
  - *Product Tutorials*: Provide advanced tutorials or consultations for product usage.
  - *Consistent Engagement*: Maintain regular contact through newsletters and personalized updates.
  - *Tailored Recommendations*: Use their purchase history for personalized product suggestions.
  - *Exclusive Community*: Create an online forum for them to connect with each other and the brand.

- **Dormant Customers**: The marketing strategies for these customers will involve several strategic actions to encourage these customers to engage with your brand more frequently and improving the recency overtime. Here are some specific strategies:
  - *Targeted Outreach*: Send personalized emails or direct mail to acknowledge their previous engagement and express a desire to reconnect. Highlight what’s new or improved since their last interaction.
  - *Incentivized Offers*: Provide special promotions, discounts, or limited-time offers to create urgency and encourage purchases.
  - *Educational Content*: Share valuable content such as newsletters, blog posts, or instructional videos that address their needs and interests.
  - *Feedback and Surveys*: Conduct surveys to understand their lack of engagement and gather insights to address potential barriers.
  - *Loyalty Programs*: Introduce or highlight loyalty programs that reward purchases, emphasizing that even small purchases can accumulate points.
  - *Retargeting Campaigns*: Use digital marketing strategies like retargeting ads to remind customers of products they viewed or similar items.
  - *Social Media Engagement*: Leverage social media to share engaging content, promotions, and customer stories that resonate with them.
  - *Community Building*: Create an online community or forum for customers to engage with your brand and each other, deepening their connection and encouraging return visits.

- **Casual Customers**: To encourage repeat business and increase lifetime value among Casual Customers (low monetary value, low frequency, high recency), consider the following strategies:
  - *Personalized Communication*: Customize communications based on previous interactions to make customers feel valued. Send personalized emails thanking them for past purchases and suggesting new products.
  - *Educational Outreach*: Share how-to guides and industry insights relevant to their interests, Offer free sessions to educate customers on using your products effectively.
  - *Reward Systems*: Introduce programs that reward even small purchases, emphasizing that every interaction counts, Provide perks like early access to products or member-only discounts.
  - *Feedback Mechanism*: Gather feedback to understand customer experiences and preferences, Create platforms for customers to share feedback and feel involved.
  - *Segmented Campaigns*: Tailor promotions based on their interests and past interactions, Use automated reminders for ongoing promotions or new arrivals.
  - *Community Engagement*: Engage customers on social media by responding to comments and sharing user-generated content, Encourage customers to share their experiences, fostering community and social proof.
  - *Customer Support and Assistance*: Follow up on past purchases with guidance and reminders of support resources and ensure support is available through chat, email, and phone.
  - *Retention Strategies*: Send special offers to celebrate milestones, Maintain monthly or quarterly communications to keep your brand top of mind.
By nurturing this segment, you can enhance their relationship with your brand, increase purchase frequency, and ultimately boost their value as loyal customers.

- **Active Customers**: For a cluster characterized by low monetary value, moderate frequency, and low recency, your goal should be to re-engage these customers and encourage them to increase their spending. Here are some tailored recommendations to effectively nurture this segment:
  - *Personalized Re-engagement*: Send tailored messages with exclusive offers based on past purchases, Use purchase history to customize communications.
  - *Value Proposition Enhancement*: Create time-limited discounts or bundles to encourage larger purchases. Also, emphasize how close they are to rewards; consider offering double points on their next purchase.
  - *Educational Content*: Share how-to content to maximize their use of previous purchases, Host free sessions to educate them about your products.
  - *Feedback and Engagement*: Gather feedback to understand their needs and address concerns, encourage dialogue through polls or questions about new products.
  - *Incentives for Engagement*: Use flash sales to create urgency for return purchases, Offer discounts for referrals to encourage re-engagement and new customer acquisition.
  - *Customer Support Outreach*: Reach out with personalized check-ins on their previous purchases, ensure easy access to help via multiple channels,Send birthday or anniversary discounts to show appreciation.
  - *Community Building*:Create forums for customers to share experiences and engage with your brand.
Implementing these strategies can help re-engage this customer segment, driving higher spending and loyalty over time.

- **Leverage Quarterly Trends**: Given the significant Q4 profit increase, design marketing campaigns that build upon this trend with holiday-themed promotions, exclusive offers, or events leading up to and during this peak period. Also, Conduct an annual review at the end of each financial year to analyze customer spending patterns, adjusting marketing strategies to maximize revenue during identified high-performance quarters.

-  **Maximize Product Performance**: Promote the Standard product line, which is the most profitable, through targeted marketing campaigns. Consider bundling them with Medium products to enhance overall sales. Ensure that high-performing products are highlighted in promotional campaigns, especially in areas with high customer concentrations, like New South Wales

-  **Expand Brand Awareness**: Increase advertising efforts in New South Wales, utilizing localized marketing strategies to reach potential customers within that region. Use social media and search engine marketing to target local audiences. Also, Consider partnering with local influencers or businesses in New South Wales to enhance brand visibility and credibility among potential customers in the area.

-   **Monitor and Analyze Customer Data**: Regularly analyze customer data to refine segments and monitor changes in purchasing behavior, allowing for agile marketing responses to trends. Create detailed customer journey maps for each segment to identify touchpoints and optimize engagement strategies tailored to each group.

## References

1. [Youtube](https://www.youtube.com/watch?v=V-s8c6jMRN0&list=PPSV)
2. [Udemy](https://www.udemy.com/course/complete-microsoft-sql-server-beginner-expert/learn/lecture/22126612#content)

💻 🖱️ 👁️
