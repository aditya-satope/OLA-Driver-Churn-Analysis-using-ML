### What I Learned
In this project, I got to dive deep into *advanced Pandas* to create individual driver profiles from monthly records. I also explored *EDA*, worked on *feature engineering* (like calculating the tenure of drivers and tracking their income and rating changes), and experimented with *bagging models* to figure out feature importance.

### Overview
This project focuses on analyzing the factors contributing to driver attrition at OLA, a major ride-hailing service. Using monthly data from 2019 and 2020, the goal was to build predictive models to determine whether a driver would leave the company. Given the high churn rate and the associated costs of recruiting new drivers, this analysis aims to provide insights that can help OLA improve driver retention strategies.

### Dataset
[Ola Driver Data (2019-2020)](https://d2beiqkhq929f0.cloudfront.net/public_assets/assets/000/002/492/original/ola_driver_scaler.csv)

The dataset consists of 19,104 records with 14 features, including:

- **MMM-YY**: Reporting Date (Monthly)
- **Driver_ID**: Unique identifier for drivers
- **Age**: Driver's age
- **Gender**: Gender of the driver (Male: 0, Female: 1)
- **City**: City code of the driver
- **Education_Level**: Educational qualification (0: 10+, 1: 12+, 2: Graduate)
- **Income**: Monthly average income of the driver
- **Dateofjoining**: Joining date of the driver
- **LastWorkingDate**: Last working date (most values missing, filled with '2021-06-01')
- **Joining Designation**: Designation at the time of joining
- **Grade**: Driver’s grade at the time of reporting
- **Total Business Value**: Total business value acquired in a month (negative indicates cancellation/refund or car EMI adjustments)
- **Quarterly Rating**: Quarterly rating (1 to 5, where 5 is the best)

### Data Profiling and Feature Engineering
- **Missing Values**: The Age and Gender columns had missing values, and the LastWorkingDate had many missing values filled with '2021-06-01'.
- **New Features**:
  - **Quarterly Rating Increase**: Indicates if there was an increase in quarterly rating for a driver.
  - **Income Increase**: Indicates if there was an increase in monthly income.
  - **Driver Tenure Days**: The number of days between the joining date and the last working date.

### Problem Statement
High churn among drivers is a significant challenge for OLA, impacting both financial stability and organizational morale. The ability to predict driver attrition is crucial for implementing effective retention strategies and reducing the costs associated with recruiting new drivers.

### Methodology

#### Data Preparation
- **Encoding**: City names were converted to numerical values using Target Encoding.
- **Scaling**: Data was scaled using StandardScaler from the scikit-learn library.

#### Feature Engineering
I engineered several new features, including Quarterly Rating Increase and Income Increase, to capture the dynamics of a driver's experience over time. This helped in improving the predictive power of the models.

#### Model Building
Several machine learning models were employed to predict driver churn, including:

- **Random Forest Classifier**
  - **Best score**: 92.91%
  - **Feature Importance**: The model highlighted Quarterly Rating, Income, and City as key predictors.

### Evaluation Metrics
- **Confusion Matrix**
- **F1 Score**
- **Precision**
- **Recall**
- **ROC-AUC Curve**

### Results and Insights
The Random Forest model provided solid performance, identifying Quarterly Rating, Income, and City as the most influential features. These insights are valuable for developing targeted retention strategies.

### Visualization
Various plots, such as feature importance and ROC curves, were used to visualize the model’s performance. Precision-Recall curves were also plotted to further understand the trade-offs in classification.

### Libraries Used
- **Pandas**: Data manipulation and analysis
- **Seaborn & Matplotlib**: Data visualization
- **Scikit-learn**: Model building, evaluation, and preprocessing
- **XGBoost**: Model building and hyperparameter tuning

### Conclusion
The project successfully identified key factors contributing to driver churn, providing OLA with actionable insights to enhance driver retention efforts. Future work could involve testing additional models, exploring more complex feature engineering techniques, and utilizing time-series forecasting methods.

### How to Use
To reproduce the results of this analysis:

1. Clone the repository.
2. Install the required libraries listed in `requirements.txt`.
3. Run the `analysis.ipynb` notebook.
