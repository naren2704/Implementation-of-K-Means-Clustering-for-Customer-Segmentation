### Implementation-of-K-Means-Clustering-for-Customer-Segmentation
## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1.Hardware – PCs
2.Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm
1. Import the necessary packages using import statement. 
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the outputs and end the program
## Program:

Program to implement the K Means Clustering for Customer 
Segmentation.


Developed by: NARENDRAN B 
RegisterNumber: 212222240069

```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
data.head(
data.info())
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.sc#atter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:
## Data.head():
![image](https://github.com/naren2704/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118706984/14528cda-b123-488a-80b1-5d834b41063e)
## Data.info():
![image](https://github.com/naren2704/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118706984/17c07823-e1c7-4666-8d87-bad35ae42436)
## Data.isnull().sum():
![image](https://github.com/naren2704/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118706984/45fdde83-1fb3-4302-942e-d031f46480b7)
## plt-Elbow Method:
![image](https://github.com/naren2704/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118706984/125726b3-fe53-42a0-8f3e-01c4a4a68a77)
## Km.fit(data.iloc):
![image](https://github.com/naren2704/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118706984/9f0f8876-2fc6-45e8-a8b1-d2b193541c03)
## plt-Customer Segments:
![image](https://github.com/naren2704/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118706984/27dec05a-f207-4248-b02a-d4f1ed432de1)
## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
