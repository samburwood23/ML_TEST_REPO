
# Women's Workplace Stress & DEI Analysis System

A **fuzzy logic-based machine learning system** for analyzing workplace stress and diversity, equity, and inclusion (DEI) impacts on women in technology.  
Originally based on the **Mental Health in Tech Survey (2014)**, this system provides personalized mental health assessments, organizational DEI insights, and actionable recommendations.

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![Flask](https://img.shields.io/badge/Flask-2.0+-green.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

---

## 🎯 Overview

This project implements a **fuzzy logic framework** that evaluates workplace factors to assess:

- **Overall stress levels** in women working in tech  
- **Burnout risk** based on workload and DEI conditions  
- **Intervention priority** for mental health support  
- **DEI health metrics** and inclusivity of workplace culture  

It is designed for **real-time personal assessments** and **future integration with empirical datasets** for validation.

---

## ✨ Key Features

- 🧠 **Fuzzy Logic Engine** with 20+ rules for nuanced, human-like reasoning  
- 🌐 **Interactive Web Interface** for real-time workplace stress analysis  
- 💬 **Personalized Recommendations** based on user input  
- 🧩 **REST API** for programmatic access and integration  
- 🎨 **Responsive UI** with dynamic visual indicators  
- 🧾 **Extensible Data Layer** — ready for integration with real-world datasets  

---

## 📊 Data Integration (Optional Enhancement)

This project is structured to support future integration with workplace stress or DEI-related datasets (e.g., Kaggle’s *Workplace Stress Dataset 2022*).

At present, no dataset is bundled with the repository.  
If you wish to extend the analysis:

1. Download a relevant dataset (e.g., [Workplace Stress Dataset on Kaggle](https://www.kaggle.com/datasets/ahmedabbas757/workplace-stress-dataset))  
2. Save it as `data/stress_dataset.csv`  
3. Run the included preprocessing and analysis notebooks once data is added.

---

## 🧠 Workflow (When Dataset is Added)

### 1️⃣ Data Preprocessing
`data/data_preprocessing.ipynb` – Cleans, normalizes, and visualizes raw dataset features.

### 2️⃣ Data Validation
`notebooks/stress_analysis.ipynb` – Performs exploratory analysis and fuzzy simulation validation.

Both notebooks are optional and will run only if a dataset is present.

---

## 🏗️ System Architecture

### Input Variables (0–10 scale unless noted)
1. **Work Hours per Week** (20–80 hours)  
2. **Company DEI Support Level**  
3. **Remote Work Flexibility**  
4. **Mental Health Benefits Quality**  
5. **Manager Support Quality**  
6. **Discrimination Experience Severity**

### Output Metrics (0–100 scale)
- **Stress Level** – Low / Moderate / High  
- **Burnout Risk** – Low / Moderate / High  
- **Intervention Priority** – Low / Medium / Urgent  

---

## 📁 Project Structure

```

ML_TEST_REPO/
├── data/
│   ├── (optional) stress_dataset.csv           # Place dataset here if available
│   ├── data_preprocessing.ipynb                # Data cleaning notebook
│   └── stress_dataset_cleaned.csv (auto)       # Output from preprocessing
├── notebooks/
│   └── stress_analysis.ipynb                   # Exploratory analysis notebook
├── src/
│   └── code/
│       ├── backend.py                          # Flask API with fuzzy logic
│       └── frontend.html                       # Interactive web UI
├── README.md
└── requirements.txt

````

---

## 🚀 Getting Started

### Installation

```bash
git clone https://github.com/samburwood23/ML_TEST_REPO.git
cd ML_TEST_REPO
pip install -r requirements.txt
````

### Run the Backend

```bash
cd src/code
python backend.py
```

Backend starts on `http://localhost:5000`

### Open the Frontend

```bash
python -m http.server 8000
# Visit http://localhost:8000/frontend.html
```

---

## 🧩 API Endpoints

**Health Check**

```bash
curl http://localhost:5000/health
```

**Analyze Single User**

```bash
curl -X POST http://localhost:5000/analyze \
 -H "Content-Type: application/json" \
 -d '{
   "work_hours": 50,
   "dei_support": 6,
   "remote_flexibility": 7,
   "mental_health_benefits": 5,
   "manager_support": 8,
   "discrimination_exp": 3
 }'
```

**Batch Dataset Analysis (future use)**

```bash
curl -X POST -F "file=@data/stress_dataset.csv" http://localhost:5000/analyze_dataset
```

---

## 🧠 Fuzzy Logic System Details

* **Inference Type:** Mamdani
* **Defuzzification:** Centroid
* **Membership Functions:** Triangular (trimf)
* **Rule Base:** 20+ contextual rules covering realistic workplace stress situations

**Example Rules:**

* High work hours + poor DEI → high stress
* Excellent DEI + strong management support → low burnout risk
* Discrimination + overwork → urgent intervention

---

## 🎨 Visual & Functional Highlights

* Responsive, mobile-friendly UI
* Animated progress bars with color-coded risk indicators
* Real-time backend connectivity check
* Smooth transitions and hover effects
* Personalized recommendations (Critical → Low Priority)

---

## 📚 Use Cases

| User Type         | Application                               |
| ----------------- | ----------------------------------------- |
| **Individuals**   | Self-assessment of workplace stress       |
| **HR Teams**      | Identify DEI and burnout patterns         |
| **Researchers**   | Fuzzy logic and mental health correlation |
| **Policy Makers** | Data-driven workplace equity planning     |

---

## 🛣️ Future Enhancements

* [ ] Add verified DEI dataset integration
* [ ] Real-time trend dashboard (Plotly/D3.js)
* [ ] ML model comparison (Random Forest, XGBoost)
* [ ] PDF report export
* [ ] Multi-user anonymous data aggregation
* [ ] Mobile app interface

---

## 🧾 Dependencies

* **Flask** – REST API backend
* **Flask-CORS** – CORS support
* **NumPy** – Numerical computations
* **scikit-fuzzy** – Fuzzy logic engine
* **Pandas** – Data manipulation
* **Matplotlib / Seaborn** – Visualization

Install all dependencies:

```bash
pip install flask flask-cors numpy scikit-fuzzy pandas matplotlib seaborn
```

---

## 🤝 Contributing

Contributions are welcome!
You can help by:

* Adding new fuzzy rules
* Improving dataset support
* Enhancing the UI
* Building dashboards or visual reports

---

## 📖 References

* **Mental Health in Tech Survey (2014)**
* **Fuzzy Logic in Human Factors Analysis**
* **DEI Best Practices in Tech Workplaces**

---

## 📧 Contact

**Author:** Sam Burwood
**GitHub:** [@samburwood23](https://github.com/samburwood23)

---

## 🙏 Acknowledgments

* OSMI Mental Health in Tech contributors
* scikit-fuzzy development team
* Women in Tech advocacy communities

---

> **Disclaimer:**
> This project is for educational and research purposes only.
> It does not provide medical advice or replace professional care.

```
