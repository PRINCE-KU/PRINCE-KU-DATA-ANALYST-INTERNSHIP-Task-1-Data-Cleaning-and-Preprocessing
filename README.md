# DATA-ANALYST-INTERNSHIP-Task-1-Data-Cleaning-and-Preprocessing
<h1 align="center">Customer Personality Analysis 🧠</h1>
<h3 align="center">🧹 Task 1: Data Cleaning and Preprocessing</h3>

---

## 📌 Objective

Clean and prepare a raw dataset by handling:
- Missing values
- Duplicate rows
- Inconsistent formats (e.g., date, text)
- Incorrect data types

---

## 📁 Dataset Used
**Customer Personality Analysis** (from Kaggle)  
- Rows: 2240  
- Columns: 29  
- Format: CSV  

---

## 🧼 Data Cleaning Steps

### 🔹 1. Handle Missing Values
- Checked using `.isnull().sum()`
- Filled 24 missing `Income` values using the median value.

### 🔹 2. Remove Duplicates
- Used `.drop_duplicates()` to remove duplicate rows.

### 🔹 3. Standardize Column Names
- Converted all column names to lowercase with underscores:
  ```python
  df.columns = df.columns.str.lower().str.replace(' ', '_')

🔹 4. Convert Date Format
dt_customer converted to datetime using:
df['dt_customer'] = pd.to_datetime(df['dt_customer'], errors='coerce', dayfirst=True)
 5. Standardize Text Columns
Cleaned education and marital_status to lowercase and stripped extra spaces.

🔹 6. Create and Fix age Column
Created age column from year_birth:
df['age'] = datetime.now().year - df['year_birth']
df['age'] = df['age'].astype(int)
✅ Final Output
Cleaned dataset saved as: cleaned_customer_personality.csv

All nulls handled, types fixed, and formatting standardized.

💡 Interview Prep (Q&A Summary)
What are missing values?
Values not recorded or unavailable. Handled using fillna() or dropna().

How do you handle duplicates?
Use .drop_duplicates() to remove repeated records.

dropna() vs fillna()?

dropna(): removes missing rows

fillna(): replaces them with a value

What is outlier treatment?
Detecting and handling extreme values that can skew results.

Standardizing data?
Making data consistent in format (e.g., lowercase text, fixed date format).

How to handle date formats?
Use pd.to_datetime() to unify inconsistent formats.

Data cleaning challenges?
Missing values, inconsistent types, outliers, typos, duplicates.

How to check data quality?
Use .info(), .isnull(), .describe() and visualizations.
