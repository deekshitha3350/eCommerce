# Customer Analysis and Clustering Project

This project involves analyzing customer, product, and transaction data to generate insights, recommend similar customers, and perform customer clustering. Below is an overview of the steps and methods used in this project.

## Data Description

The project involves three datasets:
1. **Customers.csv**
   - Contains customer details like CustomerID, CustomerName, Region, and SignupDate.
2. **Products.csv**
   - Includes product details like ProductID, ProductName, Category, and Price.
3. **Transactions.csv**
   - Tracks transactions with details such as TransactionID, CustomerID, ProductID, TransactionDate, Quantity, TotalValue, and Price.

## Libraries Used
- pandas
- numpy
- matplotlib
- seaborn
- sklearn (StandardScaler, OneHotEncoder, KMeans, PCA, cosine_similarity)

## Steps Performed

### Data Exploration
1. **Data Inspection**:
   - Used `.info()` to check data structure and data types.
   - Checked for null values using `.isnull().sum()`.

2. **Data Merging**:
   - Merged Customers, Products, and Transactions datasets to form a unified dataset for analysis.

3. **Data Type Conversion**:
   - Converted `TransactionDate` and `SignupDate` columns to datetime format.

### Data Analysis
1. **Monthly Sales Trend**:
   - Grouped data by `MonthYear` to analyze revenue trends over time.

2. **Top 10 Products by Revenue**:
   - Identified the top 10 revenue-generating products using grouped `TotalValue` data.

3. **Region-wise Revenue**:
   - Calculated total revenue by region.

### Visualizations
- **Monthly Sales Trend** (line chart)
- **Top 10 Products by Revenue** (bar chart)
- **Region-wise Revenue Distribution** (pie chart)

### Feature Engineering
1. **Customer Features**:
   - Aggregated `TotalValue` and `Quantity` for each customer.

2. **Feature Normalization**:
   - Used `StandardScaler` to normalize `TotalValue` and `Quantity`.

### Similarity Analysis
- Calculated pairwise cosine similarity for customers based on normalized features.
- Created a lookalike report, identifying the top 3 similar customers for each customer.
- Saved the results to a CSV file (`FirstName_LastName_Lookalike.csv`).

### Clustering
1. **Encoding Categorical Features**:
   - Used `OneHotEncoder` for the `Region` column.

2. **Feature Combination**:
   - Combined encoded categorical features and normalized numerical features into a final feature set.

3. **K-Means Clustering**:
   - Applied K-Means to create 4 customer clusters.

4. **Cluster Evaluation**:
   - Calculated the Davies-Bouldin Index to evaluate clustering performance.

### Dimensionality Reduction
- Applied PCA (2 components) to reduce feature dimensions for visualization.
- Visualized customer clusters using a scatter plot.

## Results
1. **Davies-Bouldin Index**:
   - Achieved a score of `1.445`, indicating a good clustering performance.
2. **Customer Clusters**:
   - Identified distinct customer clusters and visualized them in 2D space using PCA.

## Files Generated
- **FirstName_LastName_Lookalike.csv**: Contains lookalike customer IDs with similarity scores.

## Usage Instructions
1. Place the `Customers.csv`, `Products.csv`, and `Transactions.csv` files in the project directory.
2. Run the Python script to analyze data and generate insights.
3. Review the visualizations for sales trends, top products, and regional revenue.
4. Check the `FirstName_LastName_Lookalike.csv` for customer similarity insights.
5. View cluster assignments and clustering results for customer segmentation.

## Requirements
- Python 3.x
- Libraries: pandas, numpy, matplotlib, seaborn, scikit-learn

## Acknowledgments
This project demonstrates the application of data science techniques, including EDA, clustering, and customer segmentation, to enhance business understanding and decision-making.
