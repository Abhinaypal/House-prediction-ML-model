****House Price Prediction using Machine Learning****

*Project Overview*

This project builds a Machine Learning model to predict house prices using the Boston Housing dataset. The notebook demonstrates the complete data science workflow, including data loading, preprocessing, visualization, model training, and performance evaluation.

The model uses *XGBoost Regressor*, a powerful gradient boosting algorithm, to predict house prices based on multiple housing features.

**Dataset Information**

The dataset used in this project is the Boston Housing Dataset, which contains information about housing areas in Boston.
Each row represents a housing area and includes features such as crime rate, number of rooms, property tax rate, and other factors that influence house prices.

*Important Features*

| Feature | Description                                            |
| ------- | ------------------------------------------------------ |
| CRIM    | Per capita crime rate                                  |
| ZN      | Proportion of residential land zoned                   |
| INDUS   | Proportion of non-retail business acres                |
| CHAS    | Charles River dummy variable                           |
| NOX     | Nitric oxide concentration                             |
| RM      | Average number of rooms per dwelling                   |
| AGE     | Proportion of owner-occupied units built before 1940   |
| DIS     | Distance to employment centers                         |
| RAD     | Accessibility to highways                              |
| TAX     | Property tax rate                                      |
| PTRATIO | Pupil-teacher ratio                                    |
| B       | Proportion of Black population                         |
| LSTAT   | Percentage of lower status population                  |
| MEDV    | Median value of owner-occupied homes (Target variable) |


**Project Workflow**

*1 Importing Libraries*

The project begins by importing necessary Python libraries for data analysis, visualization, and machine learning.
Libraries used:
- NumPy → numerical operations
- Pandas → data manipulation
- Matplotlib & Seaborn → data visualization
- Scikit-learn → machine learning utilities
- XGBoost → regression model

*2 Loading the Dataset*

The Boston housing dataset is loaded using sklearn.datasets.
- house_price_dataset = sklearn.datasets.load_boston()

Another method is used to load the dataset directly from the CMU dataset source.
- data_url = "http://lib.stat.cmu.edu/datasets/boston"
The raw dataset is read using pandas and converted into a structured format.

*3 Creating the DataFrame*

The dataset is converted into a Pandas DataFrame so it can be easily analyzed.
house_price_dataframe = pd.DataFrame(data, columns=feature_names)
house_price_dataframe['MEDV'] = target

This step creates a dataset where:
- Columns represent features
- Rows represent observations
- MEDV is the target variable (house price)

*4 Data Exploration*

Basic dataset exploration is performed.
Example operations:
house_price_dataframe.head()
house_price_dataframe.shape
house_price_dataframe.describe()

These commands help understand:
- Number of rows and columns
- Feature statistics
- Data distribution

*5 Data Visualization*

Visualization helps identify relationships between variables.

Common plots used:
- Correlation Heatmap
- Distribution plots
- Feature relationships

Example:
sns.heatmap(house_price_dataframe.corr(), annot=True)

This shows how strongly features are related to house prices.

*6 Splitting the Dataset*

The dataset is split into:
- Training Data (80%)
- Testing Data (20%)

Example:
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)
Training data is used to train the model, while testing data evaluates model performance.

*7 Model Training*

The model used is XGBoost Regressor, which is highly efficient for regression tasks.

Example:
model = XGBRegressor()
model.fit(X_train, y_train)

XGBoost works by combining multiple weak models to create a strong predictive model.

*8 Model Prediction*

After training, the model predicts house prices using test data.

Example:
prediction = model.predict(X_test)

*9 Model Evaluation*

The model performance is evaluated using regression metrics.

Example:
metrics.r2_score(y_test, prediction)

Common evaluation metrics:
- R² Score → measures prediction accuracy
- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)

A higher R² score indicates better model performance.

*Technologies Used*

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- Jupyter Notebook

*Project Outcome*

The model successfully predicts housing prices based on various socioeconomic and environmental features. This project demonstrates:

Data preprocessing

- Exploratory Data Analysis
- Machine Learning model training
- Model evaluation

*How to Run the Project*

1. Clone the repository
  git clone <repository_link>
2. Install dependencies
   pip install numpy pandas matplotlib seaborn scikit-learn xgboost
3. Run the notebook
   jupyter notebook


**Author**

*Abhinay Pal*
- MCA Student | Data Analytics & Machine Learning Enthusiast
