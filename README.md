#PowerShell Obfuscation Detector

This project is a machine learning-based system that detects whether a given PowerShell script is **obfuscated** or **clean** by analyzing its structure and statistical patterns.

##  Project Overview

PowerShell is a powerful scripting language widely used by system administrators—but also targeted by attackers for malicious activities through **obfuscated scripts**. This project aims to build a lightweight, effective classifier that can automatically detect such scripts before execution.

We leverage custom **feature engineering**, **visualization**, and a trained ML model to classify scripts based on their entropy, length, special character count, and more.

---

##  Key Features

- Binary classification: Obfuscated vs Non-obfuscated scripts  
- Feature engineering from raw scripts (e.g. entropy, special characters, length, etc.)
- Interactive visualizations using Plotly Express
- Machine Learning model (Random Forest) with hyperparameter tuning
- Streamlit web app interface for real-time prediction
- Ready for deployment on Render or any cloud provider

---

## Project Structure


├── app.py # Streamlit web app
├── obfuscation_detector.pkl # Trained model
├── requirements.txt # Python dependencies
├── README.md # Project overview
└── notebook.ipynb # Full ML workflow + visualizations

---

##  Features Extracted

| Feature | Description |
|--------|-------------|
| `length` | Total length of the script |
| `entropy` | Shannon entropy of the script (measures randomness) |
| `num_special_chars` | Count of non-alphanumeric characters |
| `num_uppercase` | Count of uppercase letters |
| `num_tokens` | Number of tokens (split by whitespace) |
| `avg_token_length` | Average length of each token |

---

##Visual Insights

Visualizations helped us understand the distribution and separability between obfuscated and clean scripts using:
- Entropy distribution histogram
- Special character boxplot
- Length vs Entropy scatter plot
- Feature correlation heatmap
- Feature importance bar chart

---

## Model Performance

| Metric        | Value     |
|---------------|-----------|
| Accuracy      | 95.9%     |
| Precision     | 92.4%     |
| Recall        | 100%      |
| F1 Score      | 96.0%     |

The model shows perfect recall on obfuscated scripts (no malicious script missed) with very few false positives.
