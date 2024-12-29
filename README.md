# Spotify User Behavior Analysis

# Overview
This project aims to analyze Spotify user behavior and predict their likelihood of purchasing a premium subscription using advanced data mining techniques. By leveraging a combination of demographic data, listening habits, and interaction patterns, the project provides insights that can be used for targeted marketing and personalized user experiences.

# Objectives
- Understand Spotify user behavior through data analysis.
  
- Build predictive models to estimate the likelihood of users subscribing to Spotify Premium.
  
- Explore feature importance to identify key factors influencing user decisions.

# Data Source
- The dataset used for this project was the Spotify User Behavior Dataset. This dataset was obtained from Kaggle (https://www.kaggle.com/datasets/meeraajayakumar/spotify-user-behavior-dataset).
  
- The dataset contained 520 rows and 20 columns, offering a variety of features related to user demographics, listening habits, and attitudes towards premium subscriptions.
  
- The dataset included information on user demographics (age, gender), listening habits (preferred content, favorite genres, listening frequency), and attitudes towards premium subscriptions (willingness to pay, preferred plan).
  
- A key feature of the dataset was the explicit information about the user's current Spotify subscription plan ("spotify_subscription_plan"), which served as the target variable for predictive modeling.

# Methodology

# 1. Data Preprocessing:
- Missing values were handled by filling categorical columns with "Unknown" and numerical columns with the median.
  
- A binary variable (is_premium) was created to indicate whether a user has a premium subscription (1) or not (0).
  
- The pod_lis_frequency column was converted to a numerical scale.
  
- Categorical columns with multiple keywords, such as fav_music_genre, spotify_listening_device, and music_Influencial_mood, were encoded by creating separate columns for each unique keyword. These columns were then prefixed with the original feature name for clarity.

# 2. Exploratory Data Analysis (EDA):
- Visualizations were used to understand the distribution of various features, including spotify_subscription_plan, spotify_usage_period, age, and music_recc_rating.
  
- It was noted that there are far more free users than premium users in the dataset (424 vs 96).
  
- The most common usage period for both free and premium users was more than 2 years, although the distribution was more even for premium users.
  
- The 20-35 age group dominated both free and premium plans, but with significantly fewer users in the premium group.
  
- Free users had a slightly higher mean music recommendation rating (3.58) than premium users (3.15).

# 3. Modeling:
- Random Forest: The Random Forest algorithm was used to predict the is_premium variable. The initial accuracy was 75%. Feature selection based on correlation decreased the accuracy to 73%, while hyperparameter tuning using GridSearchCV increased the accuracy to 79%. The feature importance was evaluated using random forest, and the main features with at least 40% importance were premium willingness, preferred plan, and spotify music rating.
  
- Decision Tree Classifier: A Decision Tree Classifier was trained to predict "Premium Subscription Conversion Willingness". The model achieved 76% accuracy. It was found that users who have used Spotify for 6 months to 1 year, listen on a computer or laptop and have/had a student premium plan are more likely to upgrade to premium.

# Tools and Technologies

- Programming Languages: Python
  
- Libraries: Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn
  
- Development Environment: Google Colab
  
- Version Control: Git

# Results and Insights

- The Random Forest model, after hyperparameter optimization, achieved the highest accuracy (79%).
  
- The Decision Tree model provided interpretable insights with 76% accuracy.
  
- The main features that were most correlated with a premium subscription were: premium willingness, preferred plan, spotify music rating.
  
- Users who listen on computers or laptops, have/had a student premium plan, or used Spotify for 6 months to 1 year are more likely to upgrade to premium.
  
- The dataset was imbalanced, with more free users than premium users, which caused the model to perform better at predicting non-premium users.
  
- Free users tended to rate music recommendations slightly higher than premium users. This may be because they have fewer options to skip songs and rely more on the recommendations.
  
- The project highlighted the importance of feature engineering (e.g., multi-keyword encoding).

# Real-World Impact
- Spotify: The insights from this project can guide marketing strategies to target specific demographics, optimise user retention, and increase premium conversion rates.

- Artists: By understanding user behaviour, artists can better tailor their music to their fan base and target premium users.

- General Users: Evaluations based on user data enable better subscription decisions and engagement with the app.
