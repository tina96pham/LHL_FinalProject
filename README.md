# Final Project

## Project Overview  
Customer play a vital role as a stable funding source for banks, facilitating lending, investment, and revenue growth. Customer analytics is important for the bank since acquiring new customers is more expensive than retaining existing ones. Moreover, analysis signals dissatisfaction and areas for enhancement, allowing the bank to proactively address issues and improve its competitive edge. 
The goal of the project is to utilize machine learning to predict customer churn in a retail bank to diagnose area of disastifaction hence improving bank service and customer retention. 


## Data Set
https://www.kaggle.com/datasets/anwarsan/credit-card-bank-churn
The dataset was obtained from kaggle. The dataset contain customer identification information along with their expenditure patterns. The target variable for the model is the Attrition Flag.
Data dictionary for the dataset.
<img src= src/data_dictionary.png>




## Process
<img src= src/bank_churn_projectflow.drawio.png>

Here are a few key points to consider in ensuring the model's generalization to unseen data. 
1. During data preprocessing, it's important to address unknown categorical data that may result from unidentifiable markers during data entry. Escpecially with marital status, there is a large pipulation of unknown since there are are only 3 markers ['Married', 'Single', 'Divorced'], customer might be engaged and their fincanical model did not match with any pre-determined markers. There are still valuable numerical attach to these data point so it was leave as is and not deem as outlier. 
2. There are highly corellated features which can cause model overfitting. The higher weighted feature during correlation was picked for the modelling.
3. In feature engineering, caution is needed with  managing class imbalance to prevent data leakage during model evaluation. This resulted in a high accuracy score during modeling, prompting my focus on the recall score for a comprehensive model evaluation. Stratifacation is use duing data splitting and incorporate in model building. 
4. Parameter tuning is time consuming. Randomized search is more time efficient and can effectively optimize the model.
5. As a first phase of deployment, pickle file are use to call for the model and tableau is use to visualize the data to provide business insight and diagnose the  area of disastifaction.

## Results 
1. Pattern who likely leave the bank:
    - Older customer are more likely to leave 
    - Lower number of card with the bank
    - Higher number of inactive months withn 12 months
    - Slightly higgher contacts with the bank within 12 months
    - Lower cradit card limit
    - Lower in revolving balance
    - Lower in change in transaction count and spending
    - Lower utilization ration
2. This is an overview of the dashboard I created for my projects. 
<img src= src/Dashboard_overview.png>
- The dashboard reveals that the age group with the highest churn is between 40-50 years old. Graduate students display a higher likelihood of leaving, while married customers with lower income are also prone to churning. These insights can guide the creation of customer personas for targeted customer service and promotional strategies, ultimately enhancing customer outreach and boosting retention efforts.
3. Among the classification machine learning model, the XGBoost algorithm demonstrated superior prediction performance compared to other models. After meticulous tuning, the model achieved an impressive 88% recall score. This promising outcome signifies that the model has the capacity to generalize effectively with unseen data and is well-suited for predicting customer churn rate.

## Challenges 
- As the dataset originates from Kaggle, its generalizability to real-life data can be limited. This occasional challenge can hinder the project's potential for expansion and analysis. While I identified alternative datasets for improved project development, time constraints led me to complete the first iteration of the project with the current dataset and create a base model for future project expansion.
- I encountered challenges during feature selection due to the risk of overfitting caused by highly correlated features. The dataset's limited features posed a difficulty in achieving model generalization, and the backward selection algorithm's prolonged runtime further added complexity. My approach involved eliminating highly correlated features by selecting those with higher weights in the correlation. In the next iteration, I plan to employ techniques like PCA and SelectKBest to pinpoint the most relevant features, reducing their number for streamlined production and deployment.
- Model deployment, with limited front end and back end knowledge to deploy the model on a web server.

## Future Goals
In the upcoming project phase, my objective is to enhance model production. I intend to establish a streamlined model production pipeline, automating predictions on a scheduled basis for efficient deployment. Additionally, I aim to broaden the model's scope by collaborating with additional bank datasets to monitor performance. Lastly, I plan to deploy the model using a REST API, enhancing the prediction interface through advanced frontend and backend enhancements.