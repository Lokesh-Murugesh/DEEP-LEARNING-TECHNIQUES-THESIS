# DEEP-LEARNING-TECHNIQUES-THESIS

# 🔐 Malicious URL Detection with Deep Learning and Machine Learning

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.18.0-orange.svg)](https://www.tensorflow.org/)

This repository contains code for detecting malicious URLs using a hybrid approach of Deep Learning (CNN + LSTM) and classical Machine Learning models. The project includes:

- Text and feature-based URL preprocessing
- Balanced data training and evaluation
- Comparative analysis of traditional ML and hybrid DL models

---

## 📂 Dataset

The dataset used is `malicious_phish.csv`, which includes URLs labeled as:

- `benign`
- `malware`
- `phishing`
- `defacement`

It is assumed to be in the local path: `/content/malicious_phish.csv`

---

## 🛠 Features Extracted

A custom `FeatureExtractor` class computes lexical and structural URL features:

- URL entropy
- Length, digits, subdomains, parameters
- `http`, `https`, `@`, `%20` presence
- Is IP-based
- Domain extension
- Suspicious keywords
- Shortening services
- URL component statistics (`count-`, `count@`, etc.)

---

## 📈 Model Architectures

### 🔬 Deep Learning (Hybrid CNN-LSTM)

- **Tokenizer + Padding** for URL text
- **Embedding Layer**: 64-dimensional
- **LSTM Layer**: Captures sequential dependencies
- **Dense Layers**: Processes extracted features
- **Fusion**: Concatenates LSTM + Dense output
- **Final Dense**: Softmax output for 4-class classification

**📊 Accuracy:** `0.9317`  
**🎯 ROC-AUC (OvR):** `0.9907`

---

### 🤖 Classical ML Models

| Model           | Accuracy |
|-----------------|----------|
| Decision Tree   | 92.23%   |
| Random Forest   | 93.05%   |
| SVM (Linear)    | 91.89%   |
| CNN-LSTM (DL)   | 94.50%   |

All models were trained using TF-IDF vectorization of URLs (for ML) and hybrid features (for DL).

---

## 📊 Visualizations

- Word Clouds for each label category
- Confusion Matrices
- ROC Curves
- Precision-Recall Curves
- Character Frequency Heatmaps
- Distribution plots (URL length, tokens, symbols)

---

## 📦 Requirements

Install dependencies with:

```bash
pip install -r requirements.txt
```

If `requirements.txt` is not provided, install manually:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn tensorflow keras pyquery whois tld wordcloud xgboost lightgbm
```

---

## 🚀 Usage

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/malicious-url-detection.git
    cd malicious-url-detection
    ```

2. Launch the notebook:
    - `model_training.ipynb` or equivalent Colab notebook

3. Ensure `malicious_phish.csv` is in the working directory

---

## 📜 File Structure

```
📦malicious-url-detection/
 ┣ 📄 README.md
 ┣ 📄 model_training.ipynb
 ┣ 📄 malicious_phish.csv
 ┣ 📄 requirements.txt (optional)
```

---

## 🤝 Contributing

Contributions are welcome! Please open an issue or submit a PR with improvements, bug fixes, or feature requests.

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 📬 Citation

If you use this code in your research, please cite this repository or the original dataset source.

---
