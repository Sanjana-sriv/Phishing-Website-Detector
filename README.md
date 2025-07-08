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

## 🧪 How It Works

### 🔹 Rule-Based Detection

The rule-based engine evaluates URLs using logical checks to assign a phishing **risk score** out of 100 and generate warnings. It looks for:

-  **Excessive subdomains** (e.g., `login.verify.bank.example.com`)
-  **Use of IP addresses** instead of domain names (e.g., `http://192.168.0.1/login`)
-  **Suspicious keywords** in the URL such as `login`, `verify`, `account`, `bank`, `secure`, `paypal`, etc.
-  **Unusual top-level domains (TLDs)** like `.tk`, `.ga`, `.ml`, `.cf`, `.pp.ua`, etc. — commonly used in phishing attacks
-  **Long or obfuscated URLs** (e.g., very long URLs or those with multiple parameters)
-  **Unicode homograph attacks** (e.g., URLs with visually similar but different characters — Cyrillic `а`, `е`, etc.)
-  **Lack of HTTPS**
-  **URL shorteners** (e.g., `bit.ly`, `tinyurl.com`) which can hide destination domains

A risk score > 50 flags the URL as **phishing**.

---

### 🔹 ML-Based Detection (Optional)

The ML model uses a **Random Forest Classifier** to predict whether a URL is phishing or legitimate based on both content and structure.

**Key aspects:**

- 📈 **Character-level TF-IDF**:
  - Uses n-grams of 2 to 4 characters
  - Extracts textual patterns from URLs
- 🔢 **Numerical feature extraction**:
  - URL length, domain length, path/query lengths
  - Symbol counts: `.`, `-`, `_`, `@`, `=`, `?`, `&`, `%`, etc.
  - Boolean flags: Has IP, Has HTTPS, Has subdomain, etc.
- 🧪 **Sample training dataset included**:
  - 10 legitimate and 10 phishing URLs
  - Easy to replace or expand with larger datasets
- 🔁 **Hybrid scoring**:
  - Combines rule-based risk with ML prediction for more accurate results

If trained, the ML model contributes a **weighted score (70%)** to the final decision, while rule-based scoring contributes **30%**.

---

## 🖼️ Screenshots

### ✅ GUI Mode (Tkinter)
> Available only on local systems (Windows, macOS, Linux)

![GUI Screenshot](https://github.com/user-attachments/assets/5f18ff16-16cf-4c1e-8a1e-c4618a63cbba)
![GUI Screenshot2](https://github.com/user-attachments/assets/8cbe43e3-0be6-4b57-91e3-dbbc66a2e6fc)



---

### 🖥️ CLI Mode (Terminal or Colab)

![CLI Screenshot](https://github.com/user-attachments/assets/cafe486e-6805-43d0-9fe7-4a7c4a43a9fe)
![CLI Screensho2](https://github.com/user-attachments/assets/70cb0b92-7c84-49dd-bd44-9a236cbf9d64)



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
