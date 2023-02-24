# Predicting National Happiness
CST383: Intro to Data Science - Final Project

#### Authors: Alonso Vega, Daniel Letterman, Gabe Williams, and Nicholas Fotinakes

## Introduction

  The objective of our project is to predict the overall happiness of a country and identify certain characteristics/features of a nation which may be strongly correlated with a higher happiness score. The happiness score is determined from the World Happiness Report which collects and determines a country’s happiness and ranking based off the Gallup World Poll in which life evaluation questions are asked of a countries population. Determining a nations state of happiness and correlating factors is important as this information is used by governments, health organizations, economists, psychologists and other organizations to influence research and policy-making decisions and assess the progress of a nation.
  
 ### Goal
 
Build a system to predict the Cantril Ladder based Happiness Score of a country using the six numerical predictors: 'Logged GDP per capita', 'Social support', 'Healthy life expectancy', 'Freedom to make life choices', 'Generosity', and 'Perceptions of corruption.'

## Selection of Data

**Dataset obtained from Kaggle:** https://www.kaggle.com/datasets/ajaypalsinghlo/world-happiness-report-2021?select=world-happiness-report-2021.csv

**Original Source:** https://worldhappiness.report/ed/2021/

*Local file also saved in this repository, accessed February 2023 for this report.*

  The dataset includes information from the 2021 World Happiness Report. The columns of the dataset include country names, region, and a ladder score. The ladder score is the overall happiness score of a country based on the numerical scale 0-10, 0 being the least happy and 10 being the most. This score is determined from the Gallup World Poll in which researchers ask respondents main life evaluation questions based off a technique called the Cantril ladder to determine the ladder score. In addition to the country and score columns, the dataset includes columns that represent different factors of a nation which may be influential factors to the overall happiness score of a country. 
  
For data munging/feature engineering, we decided to drop columns that do not neccesarily contribute to the happiness score. The columns of interest for this project include the logged GDP per capita, life expectancy, social support, freedom to make life choices, generosity, and perceptions of corruption. These predictors will use Z-score normalization for relevant machine learning tests such as KNN. 
  
### Additional details on dataset columns:

**Logged GDP per Capita:** Economic ouput of a nation per person (Gross domestic Product)

**Healthy Life Expectancy** – data extracted from the World Health Organization’s Global Health Observatory data repository.

**Social Support** – the national average of binary responses to the GWP question “If you were in trouble, do you have relatives or friends you can count on to help you whenever you need them, or not?”

**Freedom to make life choices** – national average of responses to GWP question “Are you satisfied or dissatisfied with your freedom to choose what you do with your life?”

**Generosity** – residual of regressing national average of response to the GWP question, “Have you donated money to a charity in the past month?” on GDP per capita.

**Corruption Perception** – national average of two binary response GWP questions, “Is corruption widespread within businesses or not?” and “Is corruption widespread throughout the government or not?”

Typical sample size per country is 1,000 people and dataset includes 149 countries.

*Additional information is from the 2021 World Happiness Report Statistical Appendix 1:*
https://happiness-report.s3.amazonaws.com/2021/Appendix1WHR2021C2.pdf  

## Methods

Tools:
* NumPy
* Pandas
* Matplotlib
* Seaborn

Methods/Models:
* KNN
* Linear Regression
* Decision Tree

*File created using Jupyter Notebook via Anaconda*

Using the tool set above, we first explored the dataset, did data preprocessing/datamunging, and visualized the data relationship between the target Ladder score and predictors. 

We then ran experiments using the three methods/machine learning models to see what provided more accurate test predictions for this dataset. Within each model, we ran some subset experiments to test some feature selection/engineering to see if we could fine tune or improve each model.


## Results

**Data exploration and preprocessing**
In our data exploration/preprocessing phase we found that the dataset had no missing values and was all already recorded as numeric values. There were 149 countries recorded each with 20 features. We kept the 6 features of interest for this report and dropped the other additional features. The dataset had a standard deviation of about 1.07 for the happiness score, with a minimum score of 2.52 and a high score of 7.84.

**Data visualization**
In the data visualization we found that of the 6 numeric features of interest, Logged GDP per capita, Social support, Healthy life expectancy, and Freedom to make life choices were the most correlated with the happiness Ladder score. These four features showed positive linear correlation with our target feature. The Logged GDP per capita had a correlation of 0.79, Social support of 0.76, Healthy life expectancy of 0.77, and Freedom to make life choices of 0.61.

**Machine Learning**
In the experimentation and machine learning phase the first model we created using KNN. We first ran the model with default parameters and also got the blind RMSE value. The Blind RMSE was 0.997 and the default KNN had an test RMSE value of 0.611.

We then fine tuned the KNN model hyperparameters to find the best k value of 11, the weight of distance, and brute for the algorithm. This gave a test RMSE of 0.56. Upon then using feature selection with the top four predictors, we further lowered the test RMSE to 0.53.

For the second model we used Linear Regression. We first again found a baseline/blind RMSE value of 1.00. With feature selection on the top four predictors we lowered this RMSE to 0.63 and an R-squared value of 0.78. Using the additional predictors showed very slight improvement to the RMSE. 

For the third model we used Decision Tree. We ran the model using all six numerical predictors as well as the top four correlated predictors. The model was tuned with hyperparameters of min_sample_split, min_sample_leaf, and max_features. Both tests showed a test accuracy of around 50-60%.

It appears that the KNN and Linear Regression models provided the most accurate predictions on the test data throughout our experiments. This seems to match the results found when visualizing the data, as the four most correlated features all showed a positive linear trend. Our hypothesis was fairly accurate with the top four correlating predictors improving some models in our testing. 

## Discussion

The results imply that our six predictors GDP, life expectancy, social support, freedom, generosity, and corruption of a nation all have influence to a nations overall happiness. Further, the top four predictors of GDP, life expectancy, social support and freedom seem to have higher correlation and heavier weight when it comes to the final happiness score. 

Upon further research, it aligns with our research that the income/wealth of a nation, access to healthcare, and freedom are the top indicators of a citizens happiness. This information could be useful to politicians and national leaders when focusing on areas to improve and work on. Passing legislature and tax breaks to help improve a citizens GDP and increasing their access to healthcare could vastly improve the overall happiness of that country. 

While our models gave fairly accurate predictions, they still seemed to top out at around 70% accuracy in predictions. Perhaps with further tuning and exploration this could be increased to provide further insight and more accurate analysis of the dataset. Additionally, this data set was on the smaller side. It could be interesting in further surveys to collect additional data on a country to help further tune future models. 


## Summary

