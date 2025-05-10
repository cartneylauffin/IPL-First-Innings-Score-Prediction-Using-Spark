# IPL-First-Innings-Score-Prediction-Using-Spark

**ABSTRACT**

This project presents a machine learning approach to predict the first innings score in Indian Premier League (IPL) cricket matches using PySpark. The dataset is preprocessed by removing inconsistent teams, early overs, null values, and outliers, ensuring high-quality inputs for modeling. Categorical features such as batting and bowling teams are encoded using StringIndexer and OneHotEncoder, while numerical features include overs, current runs, wickets, and performance in the last five overs. The data is split into training (2008–2016) and testing (2017–2019) sets. Four regression models—Linear Regression, Decision Tree, Random Forest, and Gradient Boosted Trees (used as an AdaBoost alternative)—are implemented and evaluated using metrics such as MAE, MSE, RMSE, and R². Among these, Linear Regression demonstrated competitive performance and was selected for final prediction. The model allows real-time prediction of team scores based on match progress, aiding analysts and broadcasters in assessing game dynamics.

**Steps**

1. Data Collection
	•	Load the IPL dataset containing ball-by-ball match details.

2. Data Cleaning
	•	Remove irrelevant or inconsistent teams (e.g., “Rising Pune Supergiants”).
	•	Filter overs: consider only data from 5th to 20th overs (to avoid early-game volatility).
	•	Drop rows with null values.
	•	Remove outliers from the total_runs column to improve model accuracy.

3. Feature Engineering
	•	Select relevant features:
	•	Categorical: batting_team, bowling_team
	•	Numerical: overs, runs, wickets, runs_last_5, wickets_last_5
	•	Encode categorical variables using:
	•	StringIndexer to convert string categories to numerical indices.
	•	OneHotEncoder to convert indices to binary vectors.

4. Data Splitting
	•	Split dataset based on match year:
	•	Training Set: Matches from 2008–2016
	•	Testing Set: Matches from 2017–2019

5. Model Building
	•	Create a feature vector using VectorAssembler.
	•	Train the following regression models:
	•	Linear Regression
	•	Decision Tree Regressor
	•	Random Forest Regressor
	•	Gradient Boosted Tree Regressor (used as a proxy for AdaBoost)

6. Model Evaluation
	•	Use the test data to evaluate each model.
	•	Calculate evaluation metrics:
	•	Mean Absolute Error (MAE)
	•	Mean Squared Error (MSE)
	•	Root Mean Squared Error (RMSE)
	•	R² Score

7. Final Prediction
	•	Select the best-performing model (Linear Regression in this case).
	•	Use it to predict first innings scores in real-time based on current match data.
