# Exp 4 Elbow Method using K-Means Clustering

**Date:** 29/10/2026

## AIM:
To implement the Elbow Method using K-Means Clustering in Python to determine the optimal number of clusters for customers based on their Annual Income and Spending Score by plotting WCSS against different values of K.

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create a Python project in the preferred IDE (VS Code/PyCharm/Jupyter Notebook).

### Step 3:
Create the Python program for implementing the Elbow Method using the Scikit-learn library.

### Step 4:
Load the customer dataset and select the features **Annual Income** and **Spending Score**.

### Step 5:
Run the K-Means algorithm for different values of **K** (number of clusters).

### Step 6:
Calculate the **Within-Cluster Sum of Squares (WCSS)** for each value of **K**.

### Step 7:
Plot the WCSS values against the corresponding values of **K** to identify the optimal number of clusters using the Elbow Method.

### Step 8:
Execute the program and analyze the elbow point in the graph.

## PROGRAM:

```
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

data = pd.read_csv("C:/Users/acer/Downloads/customers_large_dataset.csv")

X = data[["AnnualIncome", "SpendingScore"]]

wcss = [] 

for k in range(1, 11):   
    kmeans = KMeans(n_clusters=k, random_state=42)
    kmeans.fit(X)
    wcss.append(kmeans.inertia_)   

    plt.figure()
plt.plot(range(1, 11), wcss)
plt.xlabel("Number of Clusters (K)")
plt.ylabel("WCSS")
plt.title("Elbow Method")
plt.show()
```

## OUTPUT:

<img width="927" height="489" alt="image" src="https://github.com/user-attachments/assets/53a625d9-bc67-4fe0-96cd-106eda119c8d" />

<img width="576" height="455" alt="image" src="https://github.com/user-attachments/assets/8368615b-8295-4026-a27a-b1016d7ae514" />

## RESULT:

The Elbow Method using K-Means Clustering was implemented successfully. The optimal number of clusters was determined by analyzing the WCSS plot and identifying the elbow point, which can be used for effective customer segmentation based on Annual Income and Spending Score.
