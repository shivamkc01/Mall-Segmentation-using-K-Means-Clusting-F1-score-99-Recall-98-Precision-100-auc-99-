# Customer Segmentation</br>
<h2>EDA</h2></br>
We start by taking a look at the distributions of the numerical variables Age, ID and Income.

We notice ID has a uniform distribution, which makes sense since it is an identifier of the customer and it will be dropped below.
The variable 'Age' has a heavy right skew, generated because of the lower limit at zero of the variable. If we are using K-Means clustering, there will be no need to normalize the feature, but we may have to do so for other models.
The feature 'Income' has the same right skew problem as the 'Age' feature. We'll have to be wary of this depending on the model we select.

<p float="left">
  <img src="https://user-images.githubusercontent.com/39437051/159079553-0dad471b-ed4d-4d8b-b1b0-4b04566238b6.png" width="500" />
  <img src="https://user-images.githubusercontent.com/39437051/159079559-c7e4e422-473d-4ba9-a02b-0f0435e8b090.png" width="500" /> 
</p>
<hr>

<img src="https://user-images.githubusercontent.com/39437051/159079755-5f1bcc06-52e8-4610-973a-0c92175b2bcd.png" width="700" />
There is some small correlation between the Age and Income features. We notice that the slope of the line is very small, which shows that the correlation between the features is low. Below we can see the calculation of the Pearson correlation factor, which states that values have a small correlation between them.</br>
<h2>General Conclusions about the data</h2></br>
Even though there was no missing data, we noticed a few trends that could be used or could be an expected outcome from the models.

First, we notice that some numerical features (Age and Income) have a right-skewed normal distribution. We will have to correct that for the model to perform correctly, since it assumes normality in our features. Most likely, a log transform will correct this skew.

Second, about the data itself, we noticed that there is a small correlation between age and income, as expected. People in smaller cities have lower income in the dataset. Income is higher as occupation feature is higher. Non-singles (married, divorced, widowed or separated) tend to have lower income than single people, and for some strange reason tend to be younger than single people (in this dataset). When they are older, males tend to have higher income than females. Most unemployed people and married people in the dataset live in small cities. There are more unemployed women than men in the dataset.
![Screen Shot 2022-03-19 at 1 48 57 PM](https://user-images.githubusercontent.com/39437051/159080062-82367120-9a14-4b29-9ec5-67032e22e33d.png)
![Screen Shot 2022-03-19 at 1 49 09 PM](https://user-images.githubusercontent.com/39437051/159080082-6dbe8778-1cf8-40f9-93dd-1a44a0d4fb1a.png)

<h2>Selecting the correct number of clusters using Elbow methods</hr></br>

![Screen Shot 2022-03-19 at 1 49 27 PM](https://user-images.githubusercontent.com/39437051/159080251-9aa97ba7-61d0-4404-9406-0526e5f6e618.png)
</hr>
<h2>Visualization</h2></br>
We have already clustered the data into 6 distinct groups and done PCA to get 3 features out of the 7 we originally had. It is always important to remember that using PCA inherently means a loss of information, so the projections of the data in the new features X1, X2 and X3 can have some overlapping points, but in reality, when using K-Means clustering the border points are clearly defined.</br>

![Screen Shot 2022-03-19 at 1 51 03 PM](https://user-images.githubusercontent.com/39437051/159080415-47eec52e-1c5f-44f2-b302-befa9cae290e.png)</br>

<h2>Decision Tree as a method to interpret clusters:</h2></br>
An alternative way to visualize and understand clusters is by way of using decision trees. We can make a decision tree predict the labels of each cluster we have determined, and in doing so the tree will determine splitting points based on the features we pass to the model. In this way, we can create the cluster descriptions based on how the decision tree splits the data.

We will use graphviz as our tree visualization tool. If you haven't downloaded this library, but have matplotlib, there is also an option to plot trees with the matplotlib library, but the visualization is way clearer with graphviz!</br>
<h2>Classification report using Confusion Martrix:</h2></br>

![Screen Shot 2022-03-19 at 1 59 56 PM](https://user-images.githubusercontent.com/39437051/159080720-bc3ea4fc-8241-49a0-b38b-14d3fa17d618.png)


<h2>Visualization of the Clustering Tree</h2></br>
I'm calling the following tree a 'Clustering Tree' as it aids in defining the clustering algorithm parameters and gives and idea of how the data should be interpreted from our results. The clustering tree returns the results shown below, it is important to note that clusters are named in the same order as they were defined in previous sections.</br>

![Screen Shot 2022-03-19 at 2 00 11 PM](https://user-images.githubusercontent.com/39437051/159080843-0db5f177-00ad-4953-aa1b-9c1844265b75.png)




