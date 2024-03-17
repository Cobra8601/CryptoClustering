# CryptoClustering

## Data Preparation
Load crypto_market_data.csv, and print the summary statistics and plot to observe the original dataset. Normalized seven numeric variables using StandardScaler. Created a new dataframe and used "coin_id" as the index.

## Find the K value of the Original Dataset
Created a list of 10 k values. Created an empty list to store the inertia values. Used a 'for' loop to compute the inertia for each possible value of k and stored that in the inertia list. Created a dictionary of the data and used that data to build a  DataFrame of to plot the elbow curve of k values (x) and inertia (y). The elbow curve plot supported the best value for k to be 4. 

## Cluster the Cryptocurrencies with K-Means using the Original Dataset
Initialized the model using 4 clusters and a random state of 1 and fit the model to the scaled dataset. Initiated the prediction of the cryptocurrencies to the clusters and made a copy of the of the DataFrame including a new column to display the predicted clusters. Visualized the data in a scatter plot; x = price change % of the currency over 24 hours, y = price change % of the currency over the past week using the ten k predictor values.

## Optimizing the Clusters using PCA
Created a PCA model with 3 components and transformed the data. Obtained the variance (0.88862186) of the three components. Created a new DataFrame of the PCA data and used the 'coin_id' as the index column. 

## Find the K value for the PCA Dataset
Created a list of 10 k values. Created an empty list to store the second set of inertia values. Used a 'for' loop to compute the inertia for each possible value of k and stored that in the inertia list. Created a dictionary of the data and used it to build a  DataFrame to plot the elbow curve of k values (x) and inertia2 (y). The elbow curve plot supported the best value for k to be 4. 

## Cluster the Cryptocurrencies with K-Means using the PCA Dataset
Initialized the model using 4 clusters and a random state of 1 and fit the model to the PCA dataset. Initiated the prediction of the cryptocurrencies to the clusters and made a copy of the of the DataFrame including a new column to display the predicted clusters. Visualized the data in a scatter plot; x = PCA1 aka price change % of the currency over 24 hours, y = PCA2 aka price change % of the currency over the past week using the ten k predictor values.

## Results Interpretation
Created composite plots to compare the Elbow curves. Created composite plots to contrast the clusters. The PCA method supports tighter, cluster relationships indicating low inertia and low standard deviation; i.e. the points are very similar in each cluster. However the PCA scatter plot supports the majority of the data points in 2 groups, red and blue. If the data was looking to answer a binary question, (aka yes/no or male/female), the PCA data would be very strong. However as there are 4 groups, a statistician may want to run this through 5 groups, just to see if those red and blue groups on the PCA scat plot break up. Personally I look at the PCA plot and I can't help to love that strength shown there, but I can't help to think that there is something different vs the Original, like maybe they are clustering on something different, or something is not being accounted for in the PCA scat plot. Maybe I'm overthinking this. 
