POLISH COMPANY BANKRUPTCY PREDICTION

INTRODUCTION
Background: Research on predicting bankruptcy has been ongoing for nearly a century, highlighting its importance in economics.
Objective: Develop a model to predict a company’s financial health using various economic indicators.
Historical Approaches: Initially focused on statistical hypothesis testing and modeling, with a shift towards artificial intelligence in recent years.
Project Focus: Applying contemporary ML methods learned in this course to enhance prediction accuracy.

Source
Polish Companies Bankruptcy
Source: UCI Machine Learning Repository
Description: This dataset focuses on the prediction of bankruptcy for Polish companies.
Time Frame:
Bankrupt companies were analyzed from 2000 to 2012. Operating companies were evaluated from 2007 to 2013.
Purpose: To develop models that can accurately predict the financial health and potential bankruptcy of companies based on historical data.

DATA SETUP
1.Drop Missing Values
2.Split into Test & Train
3.Target Variable: Bankruptcy (Binomial)
4.Feature Variables A1-A64 (Numerical)

METHOD
Logistic Regression：Subset Selection Cross-validation
<img width="369" alt="截屏2024-05-04 下午9 54 55" src="https://github.com/KenChen-GZ/QTM347_final_project/assets/123331887/87b439da-59d6-4916-9de7-884344bdb267">

<img width="356" alt="截屏2024-05-04 下午9 55 05" src="https://github.com/KenChen-GZ/QTM347_final_project/assets/123331887/05a4c2bc-6b95-4c53-9e04-830061a2b98f">

<img width="353" alt="截屏2024-05-04 下午9 55 26" src="https://github.com/KenChen-GZ/QTM347_final_project/assets/123331887/2c922989-d82b-45e0-8fc4-b08f96d863bb">


F1 Score

<img width="235" alt="截屏2024-05-04 下午9 55 32" src="https://github.com/KenChen-GZ/QTM347_final_project/assets/123331887/d1d2fd5a-3888-4d6b-afec-0c6a9f1127f8">



Gradient Boost：Features selection Decison Trees
<img width="650" alt="截屏2024-04-23 下午1 26 07" src="https://github.com/KenChen-GZ/QTM347_final_project/assets/123331887/4ff8a288-6fa3-49ae-ae08-50f1f2cca069">

<img width="1188" alt="image (1)" src="https://github.com/KenChen-GZ/QTM347_final_project/assets/123331887/543c1a40-dbe9-4f95-aa25-183b562df0e4">


![image](https://github.com/KenChen-GZ/QTM347_final_project/assets/123331887/2a9e6c37-0016-4c5a-b71e-a04c0dd1d6a7)


MSE
F1 Score

![image (1)](https://github.com/KenChen-GZ/QTM347_final_project/assets/123331887/4d11f261-b042-4640-be01-e0d018613ff2)





Discussion
1.The predictors selected by the 2 models are not overlapped, so we are not sure about which variables are the most important in predicting bankruptcy.
2.Although the model accuracy is high, the Recall Rate is low, suggesting that the model is failing to identify the majority of positive cases (bankruptcy).
3.Besides, there may exist correlations between variables. 
4.All the 64 features are transformations of basic indexes like gross profit, total liability, book value, and so on. So by treating them as individual predictors, we might encounter severe multicollinearity. It might be better to do some calculations, maybe try other methods.
