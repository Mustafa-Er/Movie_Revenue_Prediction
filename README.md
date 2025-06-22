# Movie_Revenue_Prediction

You are provided with:

7,398 movies in the training set

4,398 movies in the test set
Each movie includes extensive metadata such as:

Cast & crew

Budget, revenue

Release date

Genre, keywords

Production information

Posters, languages, and more

🔍 Goal: Predict the worldwide box office revenue for each movie in the test set.

📊 Features Overview
I conducted exploratory data analysis (EDA) on all available features, including:

revenue

belongs_to_collection

homepage

genres

imdb_id

original_language

poster_path

production_companies

production_countries

release_date

runtime

spoken_languages

status

tagline

title

keywords

cast

crew

📌 The figure below shows the full feature list used in EDA and modeling.


⚙️ Model & Approach
Model: CatBoostRegressor

Target: log(revenue) (log transformation applied to stabilize variance and improve accuracy)

Validation: KFold cross-validation with 5 folds

Metric: Mean Absolute Percentage Error (MAPE)

🧠 Feature Selection
Using feature importance from the CatBoost model, I identified the top 20 most useful features that significantly impacted revenue prediction. These included both numerical and engineered categorical features.

📈 Results
KFold cross-validation yielded the following results:

📌 Mean MAPE: 333.40

📉 Standard Deviation: 116.54

These values reflect the model’s average error percentage in revenue prediction across 5 folds, showing moderate variance across the splits.
