# 🏥 Hospital Patient Data Analysis & Demographic Study  

## 📌 Table of Contents  
- [Description](#-description)  
- [Project Overview](#-project-overview)  
- [Data Source](#-data-source)  
- [Business Problem](#-business-problem)  
- [Project Objective](#-project-objective)  
- [Steps Followed](#-steps-followed)  
- [Tools](#-tools)  
- [Key Findings](#-key-findings)  
- [Python Code Snippets](#-python-code-snippets)  
- [Conclusion](#-conclusion)    

---

## 📖 Description  
This project performs an **exploratory data analysis (EDA)** on **8,000+ hospital patient visit records** to identify demographic patterns, disease prevalence, and gender-based variations.  

Using **Pandas** and **Matplotlib**, the analysis transforms raw patient data into meaningful insights for:  
- Hospital management  
- Public health planners  
- Disease surveillance teams  
- Healthcare policymakers  

---

## 🧠 Project Overview  
This analysis explores:  
- Gender distribution of patients  
- Age-group distribution  
- Top diseases by case count  
- Gender-specific disease ratios  
- Overall disease burden  

The goal is to provide actionable insights that support hospital planning and public health interventions.

---

## 🗂️ Data Source  
- Hospital patient visit dataset  
- ~8,000 rows  
- Columns include: **Gender, Age Group, Disease Type, Case Count**

---

## 🏥 Business Problem  
Hospitals need a clear understanding of patient demographics and disease burden to:  
- Allocate resources properly  
- Staff critical departments  
- Track disease trends  
- Improve patient care strategies  

However, raw data alone cannot provide actionable insights.

---

## 🎯 Project Objective  
To analyze hospital visits and uncover patterns by:  
- Identifying the **most prevalent diseases**  
- Studying **gender and age distributions**  
- Highlighting **public health gaps**  
- Supporting **data-driven planning**  

---

## 🔄 Steps Followed  
1. **Data Loading** using Pandas  
2. **Data Cleaning & Inspection**  
3. **Grouping & Aggregation** by gender, age, and disease  
4. **Calculating Percentages & Ratios**  
5. **Visualizing Insights** using Matplotlib  
6. **Interpreting Results** to support decision-making  

---

## 🛠 Tools  
| Tool | Purpose |
|------|---------|
| **Python** | Core programming language |
| **Pandas** | Data manipulation & cleaning |
| **Matplotlib** | Charts & visual insights |

---

## 📊 Key Findings  

### 1️⃣ Gender Distribution  
- **Male Patients:** 5,206 (65.07%)  
- **Female Patients:** 2,794 (34.93%)  
There is a clear gender imbalance in hospital visits.

---

### 2️⃣ Age-Group Distribution  
Age groups showed fairly even distribution, with the **21–40** group having the highest volume.

---

### 3️⃣ Top 5 Most Common Diseases  
| Disease | Cases | Percentage |
|---------|--------|-------------|
| Malaria | 1,193 | 15% |
| Asthma | 966 | 12% |
| Tuberculosis | 864 | 11% |
| Diabetes | 694 | 9% |
| Cancer | 691 | 9% |

---

### 4️⃣ Gender-Specific Disease Ratios  
Male patients consistently outnumber female patients across disease categories (often ~2:1).  

Examples:  
- **HIV/AIDS – 2.15:1**  
- **Asthma – 2.02:1**  
- **Liver Disease – 2.34:1**  

---

## 🐍 Python Code Snippets  

### 🔹 Total Patient & Gender Distribution  
```python
total_patients = 8000

gender_data = {'Male': 5206, 'Female': 2794}
male_percentage = (gender_data['Male'] / total_patients) * 100
female_percentage = (gender_data['Female'] / total_patients) * 100

print(f"Total Patients: {total_patients}")
print(f"Male Patients: {gender_data['Male']} ({male_percentage:.2f}%)")
print(f"Female Patients: {gender_data['Female']} ({female_percentage:.2f}%)")
```

---

### 🔹 Age Group Bar Chart  
```python
import matplotlib.pyplot as plt

age_groups = {
    '21-40': 1646,
    '41-60': 1608,
    '81-100': 1603,
    '61-80': 1580,
    '0-20': 1533
}

ages = list(age_groups.keys())
visits = list(age_groups.values())

plt.figure(figsize=(10, 6))
plt.bar(ages, visits)
plt.title('Patient Visits by Age Group')
plt.xlabel('Age Group')
plt.ylabel('Total Visits')
plt.grid(axis='y', linestyle='--')
plt.show()
```

---

### 🔹 Top 5 Diseases Bar Chart  
```python
top_diseases = {
    'Malaria': (1193, 0.15),
    'Asthma': (966, 0.12),
    'Tuberculosis': (864, 0.11),
    'Diabetes': (694, 0.09),
    'Cancer': (691, 0.09)
}

diseases = list(top_diseases.keys())
cases = [d[0] for d in top_diseases.values()]
percentages = [d[1] * 100 for d in top_diseases.values()]

plt.figure(figsize=(12, 7))
bars = plt.bar(diseases, cases)
plt.title('Top 5 Most Commonly Diagnosed Diseases')
plt.ylabel('Total Cases')

for bar, percent in zip(bars, percentages):
    yval = bar.get_height()
    plt.text(
        bar.get_x() + bar.get_width()/2,
        yval + 20,
        f'{int(yval)} ({percent:.0f}%)',
        ha='center', 
        va='bottom'
    )

plt.show()
```

---

## 🏁 Conclusion  
This analysis highlights critical trends such as:  
- High burden of **malaria and infectious diseases**  
- Noticeable **gender imbalance** in hospital visits  
- Even distribution of visits across age groups  
- Key diseases demanding urgent resource allocation  

The findings support stronger, data-driven decision-making in healthcare.
