# Customer Segmentation using K-Means Clustering (Oasis Infobyte - Task 2)

This project is part of my Data Analytics Internship at **Oasis Infobyte** (Task 2). The goal is to perform Customer Segmentation using RFM (Recency, Frequency, Monetary) analysis and the K-Means clustering algorithm to identify distinct customer groups and provide actionable marketing strategies.

## Project Overview
Understanding customer purchasing behavior is crucial for targeted marketing. In this project, transaction data was processed to calculate RFM metrics for each customer, scaled using `StandardScaler`, and clustered using K-Means to uncover valuable business segments.

##  Tools & Technologies Used
* **Python** (Data Cleaning & Modeling)
* **Pandas & NumPy** (Data Manipulation & Aggregation)
* **Scikit-Learn** (StandardScaler & K-Means Clustering)
* **Matplotlib & Seaborn** (Data Visualization with custom palettes)
* **Jupyter Notebook / VS Code**

##  Methodology & Steps
1. **Data Preprocessing:** Cleaned the dataset, handled missing values, and calculated RFM metrics (Recency, Frequency, Monetary) per customer.
2. **Feature Scaling:** Applied `StandardScaler` to normalize the RFM features for optimal clustering performance.
3. **Elbow Method:** Determined the optimal number of clusters ($K = 4$).
4. **Model Training:** Fitted the K-Means model and visualized the customer segments (Recency vs. Monetary scatter plot, and cluster distribution bar chart).

##  Key Insights & Marketing Recommendations
Based on the clustering results, customers were divided into 4 main segments:

* **1. VIP / Top Spenders:** High monetary value and frequent buyers.
  * *Action:* Provide exclusive VIP programs, early access to new products, and personalized perks.
* **2. Regular & Loyal Customers:** Consistent purchase frequency with stable spending.
  * *Action:* Encourage higher basket sizes through cross-selling and tiered reward systems.
* **3. At-Risk / Inactive Customers:** High recency (haven't purchased in a long time).
  * *Action:* Run targeted win-back campaigns with limited-time discount codes.
* **4. Occasional / Low-Value Shoppers:** Infrequent buyers with low total spend.
  * *Action:* Use automated, low-cost email marketing to encourage repeat purchases.

##  How to Run
1. Clone this repository or download the `.ipynb` file into your Task 2 folder.
2. Ensure Python, pandas, scikit-learn, matplotlib, and seaborn are installed in your environment.
3. Open `AyaMohammed_Task2_Level1.ipynb` in Jupyter Notebook or VS Code and run all cells.


   > **Note on Dataset:** The original dataset file is excluded from this repository due to GitHub's file size limits (>25MB). You can easily load your own customer dataset or place the CSV file locally in the working directory to run the notebook successfully.
