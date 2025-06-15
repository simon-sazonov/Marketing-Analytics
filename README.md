# Snowit Data Science Project

## Customer Insight & Strategy for a Seasonal Business

### Group Members

| Name           | Student ID | UNIMIB Email              |
|----------------|------------|---------------------------|
| Semen Sazonov  | 934361     | [s.sazonov@campus.unimib.it] |
| Junaid Ahmed   | 923714     | [j.ahmed6@campus.unimib.it] |
| Hadis Forghani | 920040     | [H.forghani@campus.unimib.it] |

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
- **Purpose**: Constructs a Recency-Frequency-Monetary (RFM) segmentation model.
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

## Setup Instructions

### Create Conda environment (only once)
conda create -n snowit_env python=3.10
conda activate snowit_env

### Install PDM
pip install pdm

### Clone the project and navigate inside
cd Marketing-Analytics

### Initialize PDM (only once)
pdm init

### Install dependencies
pdm add dill pandas numpy matplotlib seaborn scikit-learn nltk

### (Optional) Install Jupyter
pdm add jupyter

### Download NLTK data (only once)
pdm run python -c "import nltk; nltk.download('stopwords'); nltk.download('wordnet')"
