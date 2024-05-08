## Polish Company Bankruptcy Prediction

### Introduction

**Background:**  For nearly a century, economists have been engaged in developing methods to predict corporate bankruptcies, underscoring its critical importance for stakeholders. This research aids investors, creditors, and regulatory bodies in making informed decisions and managing risk effectively.

**Objective:** The primary goal of this project is to develop a robust predictive model that leverages various economic indicators to assess and forecast the financial health of companies. This model aims to enable early identification of potential bankruptcy, helping to mitigate financial losses and improve financial stability.

**Historical Approaches:**  Initially, the field focused on linear statistical techniques and basic hypothesis testing to identify financial distress. Over the decades, as computational power and data availability have increased, the focus has shifted towards more sophisticated methods. The integration of machine learning and artificial intelligence into this research represents the latest evolution, promising higher accuracy and better adaptability to complex financial environments..

**Project Focus:** This project seeks to apply cutting-edge machine learning algorithms learned in academic coursework to real-world data. By doing so, it aims to not only validate the effectiveness of these methods but also explore their potential to outperform traditional models in predicting company bankruptcies. The project will use historical data from Polish companies, combining traditional financial ratios with newer, non-linear modeling techniques to provide a comprehensive assessment of bankruptcy risk.

### Source

**Dataset:** Polish Companies Bankruptcy
- **Source:** UCI Machine Learning Repository
- **Description:** This dataset focuses on the prediction of bankruptcy for Polish companies.
- **Time Frame:** Bankrupt companies from 2000 to 2012, operating companies from 2007 to 2013.
- **Purpose:** To develop models that can accurately predict the financial health and potential bankruptcy of companies based on historical data.

### Data Setup

1. Drop Missing Values
2. Split into Test and Train sets
3. Target Variable: Bankruptcy (Binomial)
4. Feature Variables: A1-A64 (Numerical)

### Methodology

#### Logistic Regression
- **Technique:** Subset Selection Cross-validation

![Logistic Regression Model Performance](https://github.com/KenChen-GZ/QTM347_final_project/assets/123331887/87b439da-59d6-4916-9de7-884344bdb267)

![ROC Curve](https://github.com/KenChen-GZ/QTM347_final_project/assets/123331887/05a4c2bc-6b95-4c53-9e04-830061a2b98f)

![Precision-Recall Curve](https://github.com/KenChen-GZ/QTM347_final_project/assets/123331887/2c922989-d82b-45e0-8fc4-b08f96d863bb)

- **Performance Metrics:**
  - F1 Score ![F1 Score](https://github.com/KenChen-GZ/QTM347_final_project/assets/123331887/d1d2fd5a-3888-4d6b-afec-0c6a9f1127f8)

#### Gradient Boosting
- **Technique:** Features Selection Using Decision Trees

![Feature Importance](https://github.com/KenChen-GZ/QTM347_final_project/assets/123331887/4ff8a288-6fa3-49ae-ae08-50f1f2cca069)

![Decision Tree](https://github.com/KenChen-GZ/QTM347_final_project/assets/123331887/543c1a40-dbe9-4f95-aa25-183b562df0e4)

- **Performance Metrics:**
  - MSE, F1 Score ![MSE and F1 Score](https://github.com/KenChen-GZ/QTM347_final_project/assets/123331887/4d11f261-b042-4640-be01-e0d018613ff2)

### Discussion

1. **Variable Importance:** The predictors selected by the two models do not overlap, raising questions about which variables are most critical in predicting bankruptcy.
2. **Recall Rate:** Although model accuracy is high, the recall rate is low, indicating failure in identifying the majority of positive cases (bankruptcy).
3. **Correlation Between Variables:** Potential correlations may exist between variables.
4. **Multicollinearity:** All 64 features are transformations of basic indexes like gross profit, total liability, and book value. Treating them as individual predictors may lead to severe multicollinearity issues, suggesting a need for alternative methods or calculations.

### Future Improvement
![Imbalance Dataset](Imbalance.png)<br>
*Figure 1: Bar graph showing the distribution of bankruptcy vs non-bankruptcy in the dataset.*<br>

Because of imbalance dataset, we can see that our models often time falls into type II error. One potential way to improve is implementing the resamping technique.
#### Resampling Techniques for Handling Imbalanced Datasets
###### 1. **Undersampling the Majority Class**
Undersampling involves reducing the size of the majority class to balance the dataset. This method is straightforward and can help improve the run-time of training models since it reduces the dataset size. However, it has some significant drawbacks:<br>
**Pros and Cons**<br>
-*Loss of Information:* By randomly removing instances from the majority class, potentially valuable information is discarded, which could be important for building a robust model.<br>
-*Bias:* If the majority class instances that are removed are not representative of the class, this can introduce bias into the model.<br>

###### 2. **Oversampling the Minority Class**<br>
Oversampling involves increasing the size of the minority class by duplicating existing instances or generating synthetic instances. This approach is beneficial because no information from the majority class is lost, but it can lead to other issues:<br>
**Pros and Cons**<br>
-*Overfitting:* By replicating the minority class instances, the model might overfit these repeated or closely similar examples, performing well on training data but poorly on unseen data.<br>
-*Increased Training Time:* Increasing the number of samples can lead to longer training times.


