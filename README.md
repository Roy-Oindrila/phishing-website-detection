# 🛡️ Phishing Website Detection using Machine Learning

This project aims to detect phishing websites using various machine learning models based on URL and website metadata features. Implemented in **Google Colab**, it includes data preprocessing, model training, evaluation, and feature extraction from raw URLs for real-time phishing prediction.

---

## 📌 Project Highlights

- ✅ Uses **16 key features** extracted from URLs and metadata
- 🤖 Trains multiple models: Decision Tree, Random Forest, SVM, MLP, XGBoost, and Autoencoder
- 📊 Compares accuracy of models on training and testing sets
- 📈 Visualizes feature importance
- 🔍 Includes a **URL feature extraction function** for live detection
- 💾 Saves trained XGBoost model with `pickle` for reuse
- 🚀 Google Colab-based, no local setup required

---

## 📂 Files in the Repository

| File Name                      | Description |
|-------------------------------|-------------|
| `Phishing_Detection.ipynb`    | Main Colab notebook with all code |
| `5.urldata.csv`               | Dataset used for model training/testing |
| `XGBoostClassifier.pickle.dat`| Saved XGBoost model |
| `README.md`                   | Project overview and usage guide |

---

## 📊 Models Compared

| Model                 | Description |
|----------------------|-------------|
| Decision Tree        | Simple tree-based classifier |
| Random Forest        | Ensemble of decision trees |
| Multilayer Perceptron| Neural network with 3 hidden layers |
| XGBoost              | Gradient boosting algorithm |
| Autoencoder          | Neural network for anomaly detection |
| Support Vector Machine (SVM) | Linear kernel classifier |

### 🏆 Example Accuracy Scores (approx.)

| Model            | Train Accuracy | Test Accuracy |
|------------------|----------------|---------------|
| XGBoost          | ✅ High         | ✅ High        |
| Random Forest    | ✅ Good         | ✅ Good        |
| Decision Tree    | ✅ Moderate     | ✅ Moderate    |
| MLP              | ✅ Good         | ✅ Good        |
| Autoencoder      | ✅ Lower        | ✅ Lower       |
| SVM              | ✅ Moderate     | ✅ Moderate    |

---

## 🧪 How It Works

1. **Preprocessing:** Removes domain column, shuffles data, checks for nulls.
2. **Feature Extraction:** Uses `extract_url_features()` to analyze:
   - IP in URL, '@' symbol, URL length/depth, redirections
   - Domain tricks like hyphens, tiny URLs, HTTPS usage
   - Placeholder metadata like DNS, traffic, domain age
3. **Model Training:** Splits data (80/20), fits multiple ML models
4. **Evaluation:** Uses accuracy score, feature importance visualization
5. **Live Prediction:** Input a raw URL, convert to features, run model to classify as:
   - ✅ **Legitimate**
   - ⚠️ **Phishing**

---

## 📌 Example Live URL Detection

```python
url = "http://example.com/login"
features = extract_url_features(url)
features_df = pd.DataFrame([features])[X.columns]
prediction = model.predict(features_df)[0]
```

---

## 📎 Dataset Source

- UCI Repository: [Phishing Websites Dataset](https://archive.ics.uci.edu/ml/datasets/phishing+websites)

---

## ▶️ Run in Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/12ZZToJDdB0mklmEjyN9w5PJQfWBOpjcw?usp=sharing)

---

## 📥 How to Use

1. Clone this repo or open the notebook in Colab.
2. Upload the dataset (`5.urldata.csv`) into Colab.
3. Run the cells sequentially to:
   - Explore data
   - Train & evaluate models
   - Use `extract_url_features()` for new URLs
4. Save or load models using `pickle` as shown.

---

## 📌 Requirements

Install only if running locally:

```bash
pip install tldextract
pip install xgboost
pip install keras tensorflow
```

---