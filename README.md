# 🛡️ Phishing Website Detection Tool

A smart and lightweight Python tool that helps users detect potentially harmful or phishing websites using a combination of **rule-based heuristics** and **machine learning (ML)**. This tool is designed to enhance cybersecurity awareness and prevent users from falling victim to phishing attacks.

---

## 🔍 Features

- ✅ **Rule-Based Detection**: Uses URL structure, suspicious keywords, TLDs, and other heuristics to determine if a URL is likely phishing.
- 🤖 **Machine Learning Support**: Trains a Random Forest classifier on sample URL datasets using text and numeric features.
- 💡 **Risk Scoring**: Outputs a phishing risk score (0–100) and highlights patterns or anomalies.
- 🧠 **Combined Verdict**: Blends ML prediction with rule-based scoring for improved accuracy.
- 🖥️ **Dual Mode Support**: 
  - GUI using Tkinter *(for local use)*
  - CLI fallback *(for environments like Google Colab or terminals)*
- 📁 **Self-contained**: Includes sample training data and works offline after setup.

---

## 🖼️ Screenshots

### ✅ GUI Mode (Tkinter)
> Available only on local systems (Windows, macOS, Linux)

![GUI Screenshot](screenshots/gui_example.png)

---

### 🖥️ CLI Mode (Terminal or Colab)

![CLI Screenshot](screenshots/cli_example.png)

---

## 📦 Requirements

- Python 3.7+
- `pandas`
- `numpy`
- `scikit-learn`
- `tkinter` *(default in most Python installations)*
- Optional: `streamlit` or `gradio` (for web deployment - not included)

Install dependencies:
```bash
pip install -r requirements.txt
