# 🎬 Movie_Revenue_Prediction

This project aims to predict the **worldwide box office revenue** for movies using metadata such as cast, budget, release date, genres, and production details. The task is tackled using regression modeling techniques on a rich dataset of film attributes.

---

## 🎯 Project Overview

- **Training Set**: 7,398 movies  
- **Test Set**: 4,398 movies  
- **Goal**: Predict the `revenue` for each movie in the test set

Each movie includes extensive metadata such as:

- 🎭 Cast & crew  
- 💰 Budget & revenue  
- 📆 Release date  
- 🎞️ Genres & keywords  
- 🏢 Production details  
- 🌍 Languages, posters, and more

---

## 📊 Features Overview

Exploratory Data Analysis (EDA) was conducted on all available metadata fields, including:

| **Feature**              | **Description**                            |
|--------------------------|--------------------------------------------|
| `revenue`                | Target variable (transformed using log)    |
| `belongs_to_collection`  | Movie franchise or collection              |
| `homepage`               | Official movie website                     |
| `genres`                 | List of genres                             |
| `imdb_id`                | IMDB identifier                            |
| `original_language`      | Original language of the movie             |
| `poster_path`            | Image/poster file path                     |
| `production_companies`   | Companies that produced the film           |
| `production_countries`   | Countries involved in production           |
| `release_date`           | Release date of the film                   |
| `runtime`                | Duration in minutes                        |
| `spoken_languages`       | Languages spoken in the film               |
| `status`                 | Release status (e.g., Released)            |
| `tagline`                | Marketing slogan or tagline                |
| `title`                  | Movie title                                |
| `keywords`               | Keywords describing themes or content      |
| `cast`                   | Main actors                                |
| `crew`                   | Director, writer, and other crew members   |

📌 A comprehensive EDA was performed across all features listed above.

---

## ⚙️ Model & Approach

| **Component**         | **Details**                               |
|-----------------------|--------------------------------------------|
| **Model**             | `CatBoostRegressor`                        |
| **Target Variable**   | `log(revenue)`                             |
| **Validation**        | `KFold Cross-Validation` (5 folds)         |
| **Evaluation Metric** | `Mean Absolute Percentage Error (MAPE)`    |

---

## 🧠 Feature Selection

Top 20 most important features were selected using **CatBoost’s built-in feature importance**. These included both numerical features (like `budget` and `runtime`) and engineered categorical features (e.g., encoded genres, collection membership, etc.).

![Feature Importance](https://github.com/user-attachments/assets/9c11c7d3-2500-4bb2-9833-6fb241bed71f)

---

## 📈 Results

| **Metric**        | **Value**     |
|-------------------|---------------|
| Mean MAPE         | **333.40**    |
| Standard Deviation| **116.54**    |

📌 These values reflect the model’s average error percentage in predicting revenue across 5 folds, with **moderate variance** observed.

---

## ✅ Summary

- **CatBoostRegressor** handled high-cardinality categorical features well.
- Log-transforming the revenue target stabilized training and improved model performance.
- K-Fold CV demonstrated reasonable generalization with moderate error spread.

This project showcases how machine learning can utilize movie metadata to provide a strong estimate of box office performance.
