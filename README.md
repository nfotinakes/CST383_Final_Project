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
* Numpy
* Pandas
* Matplotlib
* Seaborn

Methods/Models:
* KNN
* Linear Regression
* Decision Tree

*File created using Jupyter Notebook via Anaconda*

Using the tool set above, we first explored the dataset, did some data preprocessing/datamunging, and visualized the data relationship. 

We then ran experiments using the three methods/machine learning models to see what provided more accurate test predictions for this dataset. Within each model, we ran some subset experiments to test some feature selection/engineering to see if we could fine tune or improve each model.


## Results


## Discussion


## Summary

