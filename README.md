# Predictive-Analysis-of-FIFA

## Objectives
- To analyze historical data of World Cup matches.
- To predict match outcomes of the FIFA World Cup 2022 based on statistical modeling.

## Feature Engineering:
New features were engineered, including FIFA rankings and match-specific variables like team groupings for the World Cup. These features are predictors that significantly influence match outcomes and were included to enhance model accuracy.

#### Cleaning and Structuring: 
The initial steps involved converting the date column to a datetime format, which is critical for time series analysis. 
Home and Away Teams - identifiers for teams which are later transformed into numeric codes. Converting team names into numerical data.
Calculating FIFA ranking points. 
#### **Data cleaning**: 
handling missing values by removing any records with incomplete data
#### **Categorical and Numerical Variable Processing**:
Match Results are used as labels for training the model, with results categorized into 'Win', 'Lost', or 'Draw' based on the scoreline. Key variables included the match outcome, which was treated as a categorical dependent variable (win, loss, draw). Numerical data such as match scores were also crucial and underwent normalization to ensure they were properly scaled for the predictive models.

## Exploratory Data Analysis (EDA):
Utilizing visualizations like box plots to examine the distribution of goals scored by home and away teams. This helped identify any potential biases or trends, such as home advantage, that might influence model outcomes.

## Model Training
A Random Forest Classifier within a MultiOutputRegressor framework is used. This setup allows for predicting multiple outputs at once, in this case, the scores of both the home and away teams.
The model is trained on historical match data alongside the corresponding FIFA rankings. The MultiOutputRegressor uses the underlying RandomForestClassifier to train a model on the training dataset. It creates a separate model internally for each output variable (home score and away score). Each model predicts its respective outcome based on the same set of input features.
## Prediction
For making predictions, the features are prepared in the same way as the training data. The features include the team IDs (transformed into numeric codes), their respective ranks, and points from the FIFA rankings.
The model predicts the likely scoreline of the matches, which are then used to determine the match outcomes.
## Evaluation
After prediction, the outcomes are evaluated by comparing them against true results to measure the accuracy and performance of the model. The MultiOutputRegressor in this project enables simultaneous predictions of both the home and away scores using a single integrated model approach, leveraging the versatility of the RandomForestClassifier to handle multiple prediction tasks efficiently. This approach is particularly suitable for the sports analytics domain, where predicting multiple aspects of a game outcome from the same dataset is common.

#### Why Use Random Forest?
It is highly accurate and robust due to the number of decision trees participating in the process.
It does not overfit the model due to the mechanism of averaging and bootstrapping.
The model also handles missing values and maintains accuracy for missing data.
It gives estimates of what variables are important in the classification.

## Technologies Used
- **Jupyter Notebook**: For interactive data analysis and model development.
- **Python**: The primary programming language for analysis and modeling.
- **Pandas & NumPy**: For data manipulation and numerical computations.
- **Matplotlib & Seaborn**: For data visualization.
- **Scikit-learn**: For machine learning model implementation.

## Methodology
1. **Data Collection**: Compiled historical World Cup data from various sources.
2. **Data Preprocessing**: Handling missing values, transforming categorical data, and creating training and test datasets.
Feature Engineering: Deriving new features like team rank differences and historical performance metrics.
3. **Exploratory Data Analysis (EDA)**: Analyzed trends and patterns using visualizations.
4. **Predictive Modeling**: Developed machine learning models to forecast match outcomes.
5. **Evaluation**: Assessed model performance with cross-validation techniques.
