# Task 2: Customer Segmentation (Unsupervised Learning)

## Objective
The objective of this project is to perform unsupervised machine learning to segment a retail store's customer base into distinct, actionable cohorts based on their demographic features and financial behaviors (`Annual Income` and `Spending Score`). This allows marketing teams to target specific shopper segments with tailored promotions.

## Dataset Description
- **Source:** Mall Customers Dataset
- **Features Used:** - `Annual Income (k$)`: Total annual earnings of the customer.
  - `Spending Score (1-100)`: A score assigned by the mall based on customer behavior and spending nature.

## Approach & Methodology

### 1. Data Cleaning & Feature Scaling
- Isolated the critical behavioral features (`Annual Income` and `Spending Score`).
- Applied `StandardScaler` to normalize the data. Because K-Means relies heavily on Euclidean distance calculations, scaling prevents features with larger numerical values or variances from over-influencing the cluster borders.

### 2. Finding Optimal K (The Elbow Method)
- Evaluated the Within-Cluster Sum of Squares (WCSS) across cluster values ranging from $K = 1$ to $10$.
- The resulting line plot showed a distinct inflection bend (the "elbow") at **$K = 5$**, establishing that 5 unique customer groups exist naturally within this retail footprint.

### 3. Clustering Execution
- Trained the final K-Means algorithm using $K = 5$ clusters and assigned each mall customer their respective segment index.

## Target Shopper Archetypes Identified

The model effectively mapped out 5 clean customer personas:
* **Cluster 0 (High Income, Low Spending):** Earns a lot but spends conservatively. ("Careful Spenders")
* **Cluster 1 (Average Income, Average Spending):** Middle-class shoppers with stable, predictable buying habits. ("Standard Shoppers")
* **Cluster 2 (High Income, High Spending):** High earners who actively purchase premium products. ("VIP Targets")
* **Cluster 3 (Low Income, High Spending):** Lower income bracket but high frequency of impulse spending. ("Careless Spenders")
* **Cluster 4 (Low Income, Low Spending):** Frugal demographic focused entirely on essential savings. ("Budget Shoppers")

## Strategic Marketing Recommendations
- **Target Cluster 2 (VIPs)** with early loyalty access, luxury item launches, and white-glove customer support experiences to extract maximum revenue.
- **Target Cluster 0 (Careful Spenders)** with high-value promotions or bundle offers that convince them they are making a smart financial investment.
- **Target Cluster 3 (Careless Spenders)** with direct mobile flash sales, limited-time discount triggers, and impulse point-of-purchase displays.
