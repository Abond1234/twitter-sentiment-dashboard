# 🧠 Social Media Sentiment Analysis for Interbrand

## 📌 Overview

In today’s digital landscape, real-time public opinion plays a vital role in shaping brand perception. This project focuses on developing an automated sentiment analysis system that classifies brand-related tweets into one of four categories: **Positive**, **Negative**, **Neutral**, or **Irrelevant**. The system is designed with business stakeholders in mind — specifically **Interbrand**, a global leader in brand consultancy — to support data-driven brand monitoring and decision-making.

Using Natural Language Processing (NLP) and Machine Learning (ML), the project transforms raw tweet data into actionable sentiment insights that can guide marketing, product development, and public relations efforts.

---

## 📊 Dataset

The dataset was sourced from [Kaggle](https://www.kaggle.com/datasets) and consists of:

- **Training set:** `twitter_training.csv` (~74,681 rows)
- **Validation set:** `twitter_validation.csv` (999 rows)

Each tweet is labeled with:
- `Entity`: the brand or product mentioned (e.g., Amazon, Microsoft)
- `Sentiment`: one of `Positive`, `Negative`, `Neutral`, `Irrelevant`
- `Text`: the actual tweet content

---

## 🧹 Data Preparation

Several preprocessing steps were carried out:

- Removed missing and duplicate tweet entries
- Tokenized, lowercased, and cleaned tweets
- Removed mentions, hashtags, links, and special characters
- Lemmatized tokens and removed stopwords
- Handled class imbalances

---

## 🤖 Models Used

The following models were trained and evaluated:

| Model                          | Accuracy | Precision (avg) | Recall (avg) | F1-Score (avg) | Notes                                      |
|-------------------------------|----------|------------------|---------------|----------------|--------------------------------------------|
| Logistic Regression (Baseline)| 68%      | 0.68             | 0.68          | 0.68           | Struggled with Irrelevant & Neutral classes|
| Random Forest (Bi-grams)      | 89%      | 0.89             | 0.89          | 0.89           | Strong overall, improved Irrelevant recall |
| XGBoost (Bi-grams)            | 64%      | 0.65             | 0.64          | 0.63           | Weaker generalization, esp. Irrelevant     |
| Random Forest (Tuned)         | **89%**  | **0.89**         | **0.88**      | **0.88**       | Best model; balanced performance, stable   |
| Random Forest (Tuned, Valid.) | **92%**  | **0.92**         | **0.92**      | **0.92**       | Final validation performance — optimal     |

The best-performing model was a **Random Forest Classifier** trained with TF-IDF bi-grams and tuned using **RandomizedSearchCV**, achieving **92% accuracy** on the validation set.

---

## 📈 Business Recommendations

1. **Set Up Alerts for Negative Sentiment Spikes**  
   Proactively monitor Twitter for potential PR crises.

2. **Integrate Sentiment Data into Marketing Campaigns**  
   Align brand messaging with public sentiment for better engagement.

3. **Share Insights with Product Teams**  
   Use sentiment trends to inform feature development and product fixes.

4. **Implement Real-Time Dashboards**  
   Visualize sentiment trends, spikes, and keyword clouds for better awareness.

5. **Retrain Model Periodically**  
   Keep up with language trends and social media slang for long-term accuracy.

---

## ⚠️ Limitations

- **Missing Tweet Text:** Some entries lacked content and were removed.
- **No Metadata:** Lack of timestamps, user info, and tweet engagement limits deeper analysis.
- **Duplicate Content:** Many tweets had minor variations that required deduplication.
- **Subjectivity in Labels:** Sentiment labeling can be inconsistent or ambiguous.
- **Limited Language Diversity:** The dataset is mostly English, limiting global generalizability.

---

## ✅ Conclusion

This project demonstrates how NLP and machine learning can support real-time, data-driven brand monitoring on social media. Despite a few limitations, the final system delivers strong performance and is capable of empowering business stakeholders — particularly at **Interbrand** — with meaningful insights to enhance brand strategy, marketing, and public relations.

---

## 📁 Project Structure

📦 project-root/
├── twitter_training.csv
├── twitter_validation.csv
├── twitter_training_cleaned.csv
├── rf_pipeline_tuned.pkl
├── vertopal.com_Notebook.pdf
├── README.md <-- (this file)
└── notebook.ipynb

yaml
Copy
Edit
---

## 🛠️ Tools & Libraries

- Python 3.x
- Pandas, NumPy
- NLTK (tokenization, stopwords, lemmatization)
- scikit-learn (Logistic Regression, Random Forest, pipelines, model evaluation)
- XGBoost
- Matplotlib (visualization)

---

## 👥 Authors

- Ibrahim Salim  
- Abond Mwangi  
- Abigail Muthenya  
- Nelson Kamau

---

## 📬 Contact

For questions or contributions, feel free to reach out via GitHub or email.
