# [Customer Purchase Behavior Analysis --- EDA, PCA, K-menas, Logistic Regression](https://github.com/Ivan-Meng0115/R-for-Classification-and-Prediction/blob/main/Data%20Analysis%20and%20Graphs%20of%20Project.pdf)
### The project focus on helping company better understand the customers behavior and conduct a more efficient products service accordingly.  I find a common trend among the various customers and split them into different groups based on the cluster results to market for a specific type of product based on this analysis.


## Tidying and Reprocessing Aata
* drop duplicated and missing data
* split and create new features dataset
* merge the related datasets
* reformate the dataset

## Exploratory Data Analysis
![](https://github.com/Ivan-Meng0115/R-for-Classification-and-Prediction/blob/main/Heatmap%20with%20correlation%20matrix.png)

![](https://github.com/Ivan-Meng0115/R-for-Classification-and-Prediction/blob/main/correlation%20matrix%20with%20univariate%20and%20bivariate%20graphs.png)

![](https://github.com/Ivan-Meng0115/R-for-Classification-and-Prediction/blob/main/Marital%20status%20of%20customers%20in%20each%20category.png)

### Observations! There are 857 (38%) customers in the dataset are “Married”. There are 571 (25%) customers in the dataset are “Together”. There are 470 (21%) customers in the dataset are “Single”. There are 231 (10%) customers in the dataset are “Divorced”. There are 76 (3%) customers in the dataset are “Widow”. There is no significant amount of customers who are “Alone”,“Absurd”and “YOLO”. Most of our customers are in couple.

![](https://github.com/Ivan-Meng0115/R-for-Classification-and-Prediction/blob/main/Education%20level%20of%20customers%20in%20each%20category.png)
### Observations! There are 1115 (50%) of customers in the dataset are ‘Graduate’. There are 480 (21%) of customers in the dataset possess ‘PhD’ degree. There are 365 (16.5%) of customers in the dataset possess ‘Master’ degree. There are 198 (9%) of customers in the dataset possess ‘2n cycle’. There are 54 (2%) of customers in the dataset possess ‘Basic’ education.


## Clustering

![](https://github.com/Ivan-Meng0115/R-for-Classification-and-Prediction/blob/main/optimal%20number%20of%20clusters.png)
### Based on the graph, we can conclude that a number of cluster of 2 should be a good choice for this dataset. However, the average silhouette width is about 0.3, which is fairly low. This indicated that the structure of this dataset is weak and could be artificial.

![](https://github.com/Ivan-Meng0115/R-for-Classification-and-Prediction/blob/main/cluster%20plot.png)
### In this plot, the two clusters did not have a clear separation from each other. They have a heavily overlapping area and everything sort of remains in the center. To better understand these two clusters, we can perform a ggpair upon the dataset.

![](https://github.com/Ivan-Meng0115/R-for-Classification-and-Prediction/blob/main/heatmap%20cluster%20graphpng.png)
### As we can see in the plot, there are several findings we can conclude. First of all, the only valid correlation among all four variables we choose is between Total expense and income, which has a correlation factor of 0.793. All the other factor do not have a strong correlation with one anther. Another interesting relationship we found is that when the recency is the same, the customers from cluster 1 always have a higher total expense compare to customers from cluster 2. This relationship is also shown in the Age vs. Total_expense plot. In general, customers from cluster 1 seems to spend more money compare to customers from cluster 2 when all other conditions are the same.


## Dimensionality Reduction
![](https://github.com/Ivan-Meng0115/R-for-Classification-and-Prediction/blob/main/PCA%20Plot.png)
## As we can see in the plot, in order to keep about 80% of the variance, first 3 components should be kept. To further find out information about each of the PCs, we can visualize the contribution of each individual customers for each PC.

![](https://github.com/Ivan-Meng0115/R-for-Classification-and-Prediction/blob/main/Individuals%20--%20PCA.png)

![](https://github.com/Ivan-Meng0115/R-for-Classification-and-Prediction/blob/main/Variables%20PCA.png)

![](https://github.com/Ivan-Meng0115/R-for-Classification-and-Prediction/blob/main/PCA%20Biplot.png)
### As shown in the cirlce plot, we can see that both income and total expense has a highly negative relationship with dimension 1, but they both have a weak relationship with dimension 2. On the other hand, recency has a highly positive relationship with dimension 2, but a weak relationship with dimension 1. The plot also tells that total expense and the income are highly conrrelated, whereas recency is not correlated with any other 3 elements. These relationship is validated based on the early contribution plot that showed the contribution for each dimension.






## Classification and Cross-validation
### Fit a logistic regression model to trian and test the dataset for classification and prediction 
![](https://github.com/Ivan-Meng0115/R-for-Classification-and-Prediction/blob/main/Logistic%20regression.png)

![](https://github.com/Ivan-Meng0115/R-for-Classification-and-Prediction/blob/main/download.png)

![](https://github.com/Ivan-Meng0115/R-for-Classification-and-Prediction/blob/main/Fit%20a%20model%20to%20train%20and%20test%20data.png)

![](https://github.com/Ivan-Meng0115/R-for-Classification-and-Prediction/blob/main/ROC%20cruve.png)
### The receiver operating characteristic (ROC) curve evaluates the performance of binary classification algorithms. It provides a graphical representation of a classifier’s performance. From the graph above, we can learn the factor income is not the main factor to predict the response of customers. We also learn that the variables “Response” and “Income” have low correlations.
