# Income Prediction
## Using the demographics of an individual as features to predict which income class do they belong to. 

### Navnoor Singh Kahlon

## Dataset:
<img width="1307" alt="Screen Shot 2022-12-26 at 1 47 22 PM" src="https://user-images.githubusercontent.com/86537623/209585071-74657883-2a75-4991-bf08-54967dc35e62.png">

## Preparing and Understanding the data

### Data Cleaning and Wrangling:
- Used Feature Enginnering to combine two columns, reduce the computational time and increase the prediction score. 
- Dropped columns that were not contributing anything to the dataset. 
- Used python methods like .isna() and .duplicated() to see if any columns had null values or any duplicates.
- Instead of null values the columns had '?' mark. Those were replaced with actual null values and dealth with during the machine learning stage. 

## Visualizations

### Heatmap:
#### A heatmap was created to look for any correlation among our columns. 
![heatmap_of_correlation_final5](https://user-images.githubusercontent.com/86537623/209460549-3e36525c-9f75-4227-aa45-42b651668751.png)
- The heatmap showed us that there was very weak positive and weak negative correlation between all the columns. 
- Correlation does not mean causation. 

### Univariate visualizations: 

##### 
![race_imbalance](https://user-images.githubusercontent.com/86537623/209460552-d6d57cf7-e11f-4a01-a54f-6aba24d19f6e.png)
- The dataset is heavily skewed towards the White Race.
- Other members like Asian, Black and American Indians barely reach half the number of the White Race combined. 

![gender_imbalance](https://user-images.githubusercontent.com/86537623/209460554-40ad8fae-2ce2-44e6-a047-6e71e9773ec2.png)
- Amongst the genders, the dataset is skewed towards men. 
- The skeweness is not as bad as the Race Imbalance of this dataset. 

#Multivariate Visualizations: 

![workclass_maritalStatus_Hours_worked](https://user-images.githubusercontent.com/86537623/209460551-23907385-ae6c-4abc-b80b-718649285533.png)
- Men worked more than women in every Marital Status and Working class. 
- This sheds a light on other responsibilities that women have, and are not recognized. 
- The dataset does not take into account the number of hours an individual spent taking care of their homes. Then that would have been skewed towards women. 

## Machine Learning Models 
#### This being a classification problem, there were two types of models in focus. KNN and Logistic Regression. 
#### The hyper-parameters were tuned of both models to find the best model with low False Negative and False Positives.  
#### Clustering was done on the numerical columns to see if the model would find any interesting aspests about the dataset. 

### KNN 
#### Hyper Paramerters:
- n_neighbours = 16

![knn1_tuned_model](https://user-images.githubusercontent.com/86537623/209478895-e6340f4d-a6e9-4323-a4aa-3019c462d043.png)

### Results: 
![knn_confusion_matrix](https://user-images.githubusercontent.com/86537623/209478974-b7f7e287-1ac7-4165-bc2c-6cec22bea00e.png)

- While this was a decent model with high True Positive, the next goal was to reduce the False Negative as much as possible. 

## Clustering
#### Clutering was applied to see if there were any interesting parterns in the dataset. 
#### Running a loop we found four to be the best number of clusters. 
![inertia_sil_score_final](https://user-images.githubusercontent.com/86537623/209480219-97c41879-96d9-493a-b51c-52c0f67772ef.png)

### Results
<img width="501" alt="Screen Shot 2022-12-26 at 2 41 42 PM" src="https://user-images.githubusercontent.com/86537623/209586970-f3ace853-c147-41ef-934d-4c8f47fbee1d.png">
- There is a clear relation between the number of hours one worked and their Net Capital Gain.

## The Best Model: 

### Logistic Regression
#### Hyper-Parameters:
- Penatly: L1
- C = 1.0
- Solver = liblinear


![liblinear_l1_log_graph](https://user-images.githubusercontent.com/86537623/209478720-f4f6fc84-965f-4a1f-abdc-565f53d49567.png)

### Results: 
![confusion_matrix_tune_log](https://user-images.githubusercontent.com/86537623/209479043-0de1f7a1-f997-4bc5-9f1d-44c6266297a0.png)

- While we did loose a percent on the True Positives, we were able to reduce the False Negative by three percent. 

### Recommendations:
- While the dataset had many detail oriented features, it could have been more balanced among race and gender. 
- There were no clear explanations on features like fnlwgt and educational-num, hence they were dropped. 
- 











