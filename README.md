# Predicting Employee Promotion Decisions Using Machine Learning: A Comparison of XGBoost and Logistic Regression
## Background
The productivity of a company largely depends on employee performance in achieving the organization’s vision and mission. To accomplish this, effective human resource management (HRM) is essential to retain competent employees and minimize the level of employee attrition. High employee attrition is often associated with employee termination and replacement recruitment processes, which can lead to financial losses for the company.

Therefore, preventive efforts are needed by promoting high-performing employees to reduce the risk of attrition. In this context, prediction plays an important role in supporting promotion decision-making. This study applies two reliable machine learning methods, namely XGBoost and Logistic Regression. XGBoost is known for its ability to handle complex data and deliver high accuracy, while Logistic Regression is a simple and fast model with a low risk of overfitting.
## Bussines Understanding
Employee promotion is a crucial factor in maintaining work motivation and improving a company’s overall productivity. Conducting promotion decisions manually can lead to bias and inconsistency. When this occurs, it may result in high employee attrition, causing financial and operational losses for the company. Therefore, organizations need a data-driven approach to identify potential employees objectively, particularly by utilizing historical promotion data as a reference for decision-making. This approach enables the company to improve decision-making efficiency, enhance fairness in promotions, and reduce employee turnover. 
This project follows the CRISP-DM framework, which consists of several key stages: Business Understanding, Data Understanding, Data Preparation, Modeling, Evaluation, and Deployment. The modeling stage focuses on applying two algorithms, XGBoost and Logistic Regression to classify whether an employee is eligible for promotion. Model performance is then evaluated based on accuracy metrics to determine the best-performing model.
## Data Understanding
The dataset represents employee-related information from previous years, which can be used to analyze factors influencing promotion decisions. Each record corresponds to an individual employee and includes demographic details, performance indicators, and career-related attributes. The target variable 'is_promoted' indicates whether the employee received a promotion, serving as the output label for classification.
- The dataset consists of 13 attributes and 1 target variable (is_promoted).
- Most features are categorical such as department, education, and recruitment_channel.
- Several features are numerical, including age, no_of_trainings, and avg_training_score, each with different value ranges.
- Some columns, such as education and previous_year_rating contain missing values that need to be handled.
- The target variable is_promoted is imbalanced with the majority of employees not being promoted.
- Initial observations suggest that factors such as previous year rating, average training score, and awards won may have a strong influence on promotion decisions.
## Data Preparation
1. Handling Missing Values
   - Filled missing values in the education column using `ffill()` from `dataframe `pandas`.
   - Replaced missing values in the previous_year_rating column with the median.
2. Dropping Factors
   - Dropped the employee_id column since it contains unique identifiers that do not contribute to the model.
   - Removed the gender column to prevent potential bias in promotion prediction.
3. Checked Duplicate
   - Checked for duplicate rows to ensure data consistency.
   - Dropped duplicate entries to avoid redundancy and potential bias in model training.
4. Balancing Target Factor
   - Detected an imbalance in the target variable (is_promoted).
   - Applied upsampling on the minority class to create a balanced dataset and improve model performance.
5. Encoding Categorical Variables
   - Converted categorical variables (department, region, education, recruitment_channel) into numerical form using One-Hot Encoding (Dummy Variables).
## Modelling 
In this stage, two machine learning models were built to predict whether an employee is eligible for promotion:
- Logistic Regression - used as the baseline model because it’s simple, interpretable, and performs well on linearly separable data.
- XGBoost (Extreme Gradient Boosting) - applied for comparison due to its strong performance in handling complex, non-linear relationships and its ability to improve prediction accuracy.
Both models were trained using an 80:20 train-test split and evaluated using common classification metrics: Accuracy, Precision, Recall, and F1-Score. The results were compared to determine which algorithm performed better in predicting employee promotions.
# Evaluation
<img width="896" height="181" alt="Screenshot 2025-11-13 02 26 08" src="https://github.com/user-attachments/assets/548b5e0c-febc-4ecb-90c7-c6436199e545" />
<img width="567" height="435" alt="Visualisasi" src="https://github.com/user-attachments/assets/467b570f-54f0-47b5-b151-e436213834ce" />

Both models were evaluated using Accuracy, Precision, Recall, and F1-Score to measure their performance in predicting employee promotions. Logistic Regression achieved a decent level of accuracy, showing consistent performance on balanced data. While, XGBoost performed slightly better, thanks to its ability to capture non-linear relationships and interactions between features.
### Top Features of XGBoost Model
The plot below highlights the **top 20 most influential features** identified by the XGBoost model.  
These features had the greatest impact on predicting whether an employee is promoted.
<img src="https://github.com/user-attachments/assets/475621e2-1647-4873-8b0a-ec5473c4ff25.png" width="700" alt="Top 20 Feature Importance - XGBoost"/>
Based on the plot, we knew that:
- avg_training_score, age, and length_of_service are the strongest predictors.
- Performance-related variables like previous_year_rating also show high importance.
- Department and region variables contribute moderately, reflecting their contextual influence.
## Deployment
- XGBoost was selected as best model due to its higher accuracy and overall superior performance compared to Logistic Regression.
- Most Influential Features is avg_training_score, age, and length_of_service are the top factors driving employee promotion predictions.
## Recommendation (HR/Management)
- Focus on enhancing employee performance and experience when designing promotion strategies, rather than relying solely on demographics or location.
- Deploy the XGBoost model in the HR system to predict promotion potential automatically and support data-driven decision-making.
### Latisa Alifa Maura
#### Data Scientist | Data Analyst | Bussines Intelligence
