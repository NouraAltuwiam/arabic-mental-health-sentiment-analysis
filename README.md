# arabic-mental-health-sentiment-analysis
# Sentiment Analysis of Arabic Reviews for Mental Health Applications

IT362 (Principles of Data Science) course project — King Saud University, College of Computer and Information Sciences, Department of Information Technology.

تحليل مشاعر لتقييمات المستخدمين العرب لتطبيقات الصحة النفسية، باستخدام تقنيات معالجة اللغة الطبيعية والتعلم الآلي.

## Team / الفريق

- Noora Aluqaili
- Jana Alothman
- Haya Alhajri
- Noura Altuwiam
- Rahaf Alshalwi

**Supervised by:** Dr. Reem Alqifari

## Overview

Star ratings alone don't capture the nuanced emotions in user reviews. This project applies sentiment analysis to Arabic-language reviews of mental health apps to understand how Arabic-speaking users perceive these apps, and compares the results against a large English-language global dataset (MHARD).

**Research question:** How can sentiment analysis of user reviews help in understanding users' perceptions of mental health applications?

## Project Phases

| Phase | Focus |
|---|---|
| 1 | Literature review, data source selection, methodology, challenges & recommendations |
| 2 | Data collection, exploratory data analysis (EDA), primary vs. secondary dataset comparison, hypothesis generation |
| 3 | Text preprocessing, feature engineering (TF-IDF), model training, evaluation, hypothesis testing |

## Data

**Primary dataset:** 1,032 Arabic reviews scraped from Google Play Store using `google-play-scraper`
- Labayh (537 reviews)
- Calm (425 reviews)
- Estanara (60 reviews)
- BetterHelp (10 reviews)

**Secondary dataset:** MHARD — 18,000 English-language reviews (used for comparison)

## Methods

- **Preprocessing:** Arabic text normalization, stop word removal, tokenization, deduplication
- **Feature extraction:** TF-IDF vectorization (max_features=5000)
- **Models:** Logistic Regression (baseline), Random Forest, XGBoost
- **Evaluation:** Accuracy, Macro F1-score, confusion matrix analysis (80/20 stratified split)

## Results

| Model | Accuracy | Macro F1-score |
|---|---|---|
| **Logistic Regression** | **78.3%** | **0.54** |
| XGBoost | 70.5% | 0.52 |
| Random Forest | 71.0% | 0.48 |

Logistic Regression was the best-performing model. All models struggled to classify the neutral class due to class imbalance and less distinctive linguistic patterns.

## Key Findings

- Ratings show a **polarized pattern** — most reviews are 5-star or 1-star
- Arabic-speaking users show **lower average satisfaction** (3.15) compared to global users (3.94)
- Lower-rated reviews tend to be **longer and more detailed**
- Developer response rate is **higher** in the Arabic dataset (39%) than the global dataset (26%)

## Tech Stack

`Python` · `pandas` · `scikit-learn` · `XGBoost` · `google-play-scraper` · `langdetect` · `matplotlib` / `seaborn`

## Repository Contents

- `phase3.ipynb` — full analysis notebook (EDA, preprocessing, modeling, evaluation)
- Project report and logbook (PDF)
- Poster summary (PDF)
