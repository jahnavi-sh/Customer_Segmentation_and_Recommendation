# Customer Segmentation & Product Recommendation System

## Project Vision
The goal of this project is to enhance the e-commerce shopping experience by grouping customers into meaningful segments based on their purchasing behavior. By understanding these segments, businesses can offer tailored product recommendations, improve customer engagement, and optimize marketing strategies.

## Dataset Overview
The project utilizes an online retail dataset containing **541,909 records**.
* **Key Features:** Invoice Number, Stock Code, Description, Quantity, Unit Price, Customer ID, and Country.
* **Target:** Customer purchasing behavior for segmentation and recommendation modeling.

## Technical Methodology

### 1. Data Preprocessing & EDA
* **Data Cleaning:** Addressed missing `CustomerID` values (approx. 25%) and removed negative quantities related to returns or cancellations.
* **Exploratory Analysis:** Conducted visual analysis of unit price and quantity distributions, as well as correlation heatmaps to understand variable relationships.

### 2. Customer Segmentation (RFM + KMeans)
* **Feature Engineering:** Developed **RFM** features—**Recency** (days since last purchase), **Frequency** (number of transactions), and **Monetary** (total spending).
* **Clustering:** Applied **KMeans Clustering** to categorize customers into four distinct group:
    * **Cluster 0:** Loyal, high-spending frequent buyers.
    * **Cluster 1:** Occasional buyers with moderate spending.
    * **Cluster 2:** Infrequent, low-value buyers.
    * **Cluster 3:** Customers at risk of churning.
* **Validation:** Achieved a **Silhouette Score of ~0.64**, indicating well-defined clusters.

### 3. Recommendation System (Collaborative Filtering)
* **User-Item Matrix:** Created a sparse matrix using `csr_matrix` where rows represent customers and columns represent product stock codes.
* **Similarity Metric:** Utilized **Cosine Similarity** to measure the relationship between customers based on their purchase history.
* **Logic:** The system identifies the top *n* similar customers and suggests products they have purchased that the target customer has not yet discovered.

## Key Technologies
* **Languages:** Python 
* **Libraries:** Scikit-Learn (KMeans), Scipy (Sparse Matrices), Pandas, Matplotlib/Seaborn
* **Algorithms:** KMeans Clustering, Cosine Similarity 

## Real-World Impact
* **Targeted Marketing:** Enables loyalty rewards for high spenders and re-engagement campaigns for at-risk customers.
* **Inventory Planning:** Assists in stock management based on specific cluster behaviors.
* **Personalization:** Delivers a highly customized shopping journey for the end user.

---
**Prepared by:** [Jahnavi Sharma](https://www.linkedin.com/in/jahnavi-sh/) 
