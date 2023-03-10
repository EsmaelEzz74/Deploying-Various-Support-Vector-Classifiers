# Deploying-Various-Support-Vector-Classifiers
A Comparative Study of SVC Kernels
- From my inspections, the IRIS dataset contains five columns, four of which are numeric and the fifth is categorical
- Next I checked for zeros and didn't find any, but for duplicate rows, three rows need to be handled. So I deleted them
- And to check the data balance I used the seaborn countplot to draw a bar chart to describe the data
- <img src = "https://user-images.githubusercontent.com/85246622/208245558-b1798d86-244b-49d8-a176-d4a529b9fd84.png" width="400" height="400"/>
---------------------------------------------
- For the outliers I used a boxplot to check  if I found them and then using the IQR formula which is Quartile3 minus Quartile1 I removed the outliers which are only 4 rows
- <img src = "https://user-images.githubusercontent.com/85246622/208245772-0972a6b5-c035-4b3a-8260-83cb294bb768.png" width="400" height="400" alt = "Before" /> <img src = "https://user-images.githubusercontent.com/85246622/208245781-5812418e-5084-4395-8311-9f5f5e14aff6.png" alt = "After" width="400" height="400"/>
---------------------------------------------
- For data preparation to fit in the model i partitioned the data frame into two dataframes first the X containing the numerical columns and the Y containing the categorical one
- Then split them into training and test sets using train_test_split and use MinMaxScaler to perform data normalization of these two Sklearn techniques  to validate the model after fitting the training data
- And the accuracy function used to get the accuracy of the model in both the training and testing sets
- To get to the function, which takes all the training and testing data and a tolerance integer as a parameter, I set a fixed kernel type for four different sizes of C, which is linear SVC fron SVM, and fit the data and then get the train and test precision and for each different number of C I used the best comparison experience namely plot_decision_regions from mlxtend.plotting library to plot the decision surface explaining the model's decision boundaries and the train and Test accuracy printed for each graph for C
- <img src = "https://user-images.githubusercontent.com/85246622/208247324-0f59eb85-a51b-4e19-88d0-b9fbc6066b1e.png" width="600" height="600"/>
---------------------------------------------
- For a general purpose function, I allow the user to select all model parameters such as tolerance integer, kernel type, gamma and polygrade
- The function is similar to the previous ones, comparing four different sizes of C, but this time it's not a fixed kernel type
- When first testing the function i select the Linear kernel type of SVC and for comparing the results i found a slight difference between the two functions may be according to the gamma parameter 
- But for the secong type of SVC kernels which is RBF there is different in the two decision surface and train & test score 
- <img src = "https://user-images.githubusercontent.com/85246622/208249398-4ead809c-60e2-44bc-b22d-c27099c8936d.png" width="600" height="600"/>
---------------------------------------------
- And for the linear SVC kernel it show a slight difference from the linearSVR from SVM
- <img src = "https://user-images.githubusercontent.com/85246622/209471913-5525d7d3-51ca-42f7-bb85-9eb1a24c99d7.png" width = "600" height = "600" />
---------------------------------------------
- And for the Poly SVC kernel it show a huge difference specially in the decision surface as below
- <img src = "https://user-images.githubusercontent.com/85246622/208249475-6cafdcd9-ac53-472f-b057-c17437fd839f.png" width="600" height="600"/>


