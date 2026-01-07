# Marketing Analytics Project

## Overview
This project focuses on analyzing customer behavior, predicting churn, segmenting customers based on **RFM (Recency, Frequency, Monetary)** analysis, performing **Sentiment Analysis** on reviews, and implementing **Market Basket Analysis** (MBA). 

### Project Member

| Name          | Student ID | UNIMIB Email              |
|---------------|------------|---------------------------|
| Junaid Ahmed  | 923714     | [j.ahmed6@campus.unimib.it] |

---

## Project Structure & Script Execution

All scripts and notebooks are organized inside the project following a **modular and replicable** structure. The project uses the `pdm` package manager and requires a dedicated Conda environment (see notes below). 

The following execution order must be followed:

### 1. `01_read_data.ipynb`
- **Purpose**: Loads raw data from `data_input/` and serializes it into `.pkl` format in `data_loaded/`.
- **Output**: Pickle files for orders, users, profiles, cards, and order_details.
- **Notes**: This must be executed first to ensure consistent data access for all subsequent scripts.

---

### 2. `02_Data_analysis.ipynb`
- **Purpose**: Performs Exploratory Data Analysis (EDA) on user behavior, seasonality, transactions, and product trends.
- **Output**: Visual insights, business-relevant observations, and seasonal usage patterns.

---

### 3. `03_RFM_analysis.ipynb`
- **Purpose**: Constructs a **Recency-Frequency-Monetary (RFM)** segmentation model.
- **Output**:
  - `rfm_segments.csv`: Exported table of customer segments.
  - Visualizations of RFM clusters.
- **Use**: Downstream targeting for marketing strategy.

---

### 4. `04_Churn_prediction.ipynb`
- **Purpose**: Trains a supervised ML model to predict customer churn.
- **Model**: Random Forest Classifier.
- **Output**:
  - `churn_prediction_model.pkl`: Serialized trained model.
  - Classification report and confusion matrix.
- **Use**: Define target audience for retention campaign.

---

### 5. `05_Sentiment_analysis.ipynb`
- **Purpose**:
  - Preprocess review data (`reviews.csv` and `reviews_labelled.csv`).
  - Train two sentiment classification models:
    - A traditional ML model (Logistic Regression, SVM, etc.).
    - A Transformer-based model using BERT (via transfer learning).
- **Output**:
  - Performance comparison (accuracy, F1-score, confusion matrix).
  - Optional model pickles for reuse.

---

### 6. `06_Market_Basket_Analysis.ipynb`
- **Purpose**: Applies the **Apriori algorithm** to perform **Market Basket Analysis (MBA)** on transactional data.
- **Output**:
  - **Frequent itemsets** of products purchased together.
  - **Association rules** derived from the itemsets (with support, lift, confidence).
  - **Visualizations** of frequent itemsets and association rules.
- **Use**: Insights for **cross-selling** and **upselling** strategies.

---

