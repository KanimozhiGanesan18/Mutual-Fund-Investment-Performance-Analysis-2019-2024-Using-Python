# 📊 Mutual Fund Investment & Performance Analysis (2019–2024) Using Python

> A data-driven analysis of AMFI mutual fund data to understand investment trends, investor participation, fund flows, and Net AUM across different mutual fund scheme categories from 2019 to 2024.

---

🚀 Mutual Fund Dataset • 2019–2024 • End‑to‑End Analytics
🔎 Descriptive → Diagnostic → Predictive → Prescriptive  
💡 Turning raw AMFI mutual fund data into actionable investment insights

---

## 📌 Project Overview

This project analyzes **AMFI mutual fund data from 2019 to 2024** using Python to understand mutual fund investment and performance patterns.

The analysis focuses on:

* Mutual fund scheme categories
* Investor participation
* Fund mobilization
* Repurchase and redemption
* Net inflow and outflow
* Net Assets Under Management (Net AUM)
* Average Net AUM
* Changes across reporting years
* Differences between scheme types and categories

The project combines **Data Cleaning, Exploratory Data Analysis (EDA), Feature Engineering, Statistical Analysis, and Data Visualization** to transform raw mutual fund data into meaningful business insights.

---

## 🎯 Objectives

The main objective of this project is to analyze AMFI mutual fund data using Python and identify useful patterns in mutual fund investment and investor participation.

### Key Objectives

1. Identify which mutual fund categories attract more investors and investments.
2. Analyze how **Net AUM changes over time**.
3. Compare mutual fund performance across different scheme types and categories.
4. Identify categories with higher **fund mobilization and redemption**.
5. Analyze positive and negative **net inflow/outflow** patterns.
6. Examine investor participation using the **number of folios**.
7. Study the relationship between **number of folios and Net AUM**.
8. Analyze investment activity across different reporting periods.
9. Identify categories that consistently attract investments.
10. Generate data-driven business insights through statistical analysis and visualization.

---

# ❓ Problem Statement

The raw mutual fund dataset does not directly show which scheme categories perform better, how investment activity changes over time, or where positive and negative fund flows occur.

Therefore, this project analyzes AMFI mutual fund data using Python to identify:

* Mutual fund performance
* Investment trends
* Investor participation
* Fund-flow patterns
* Differences across scheme categories
* Changes across reporting periods

The analysis uses **statistical techniques and visualizations** to convert raw data into meaningful business insights.

---

# 🏢 Business Understanding

The analysis is designed to answer the following business questions.

### 💰 Fund Performance

* Which scheme category has the highest Net AUM?
* Which scheme type performs better?
* How does AUM change over time?

### 💵 Investment Activity

* Which categories receive the highest fund mobilization?
* Which categories have the highest redemption?
* Which categories have positive or negative net inflow/outflow?

### 👥 Investor Participation

* Which categories have the highest number of folios?
* How does investor participation change over time?
* Is there a relationship between folios and AUM?

### 📈 Trend Analysis

* How does mutual fund activity change across reporting periods?
* Are there periods with unusually high or low investment activity?
* Which categories consistently attract investments?

---

# 📂 Dataset Information

| Attribute       | Details                           |
| --------------- | --------------------------------- |
| **Data Source** | India's Extensive Public Datasets |
| **Location**    | India                             |
| **Domain**      | Economy                           |
| **Period**      | 2019–2024                         |
| **Records**     | 3,115                             |
| **Attributes**  | 14                                |
| **File Format** | Excel                             |
| **Environment** | Google Colab                      |

The dataset contains mutual fund information related to scheme names, scheme types, scheme categories, investor folios, fund mobilization, redemption, net flows, Net AUM, and segregated portfolios.

---

# 📋 Attribute / Data Dictionary

| Column                             | Description                                                         |
| ---------------------------------- | ------------------------------------------------------------------- |
| `id`                               | Unique identifier for each record                                   |
| `date`                             | Reporting date of the mutual fund data                              |
| `scheme_name`                      | Name of the mutual fund scheme                                      |
| `scheme_type`                      | Type of scheme such as Open Ended, Close Ended, or Interval Schemes |
| `scheme_category`                  | Category of the mutual fund scheme                                  |
| `no_of_schemes`                    | Number of schemes                                                   |
| `no_of_folios`                     | Number of investor folios                                           |
| `fund_mobilized`                   | Amount of funds mobilized                                           |
| `repurchase_redemption`            | Amount involved in repurchase/redemption                            |
| `net_inflow_outflow`               | Net movement of funds                                               |
| `net_aum`                          | Net Assets Under Management                                         |
| `avg_net_aum`                      | Average Net Assets Under Management                                 |
| `no_of_segregated_portfolios`      | Number of segregated portfolios                                     |
| `net_aum_in_segregated_portfolios` | Net AUM held in segregated portfolios                               |

The dataset contains **56 scheme names, 3 scheme types, and 5 scheme categories**.

---

# 🛠️ Tools & Technologies

### Programming Language

* Python 3.10+

### Libraries

* **Pandas** – Data manipulation and analysis
* **NumPy** – Numerical operations
* **Matplotlib** – Data visualization
* **Seaborn** – Statistical visualization

### Development Environment

* **Google Colab**

---

# 🔄 Project Workflow

```text
Data Collection
      ↓
Initial EDA
      ↓
Data Inspection
      ↓
Data Cleaning
      ↓
Data Validation
      ↓
Feature Engineering
      ↓
Final EDA
      ↓
Statistical Analysis
      ↓
Univariate Analysis
      ↓
Bivariate Analysis
      ↓
Multivariate Analysis
      ↓
Business Insights
```

---

# 🧹 Data Pre-Processing

The dataset was systematically inspected and cleaned before performing statistical and visual analysis.

### Initial Data Inspection

The following checks were performed:

* Dataset shape
* First and last records
* Sample records
* Data types
* Missing values
* Duplicate IDs
* Unique values
* Value counts
* Descriptive statistics
* Special characters
* Zero values
* Negative values

### Dataset Shape

```text
Rows    : 3,115
Columns : 14
```

### ID Cleaning

The `id` column was checked for:

* Data type
* Missing values
* Duplicate values

No missing IDs or duplicate IDs were found. The column was subsequently converted from integer to string.

### Scheme Name Cleaning

Special characters such as:

```text
#
$
```

were identified in some scheme names and removed to maintain consistent categorical values.

### Zero-Value Handling

Zero values were not automatically treated as missing values because a zero can represent a genuine observation in the dataset.

---

# 🔍 Data Validation

### Net Inflow/Outflow Validation

The following relationship was verified:

```text
Net Inflow/Outflow
=
Fund Mobilized - Repurchase/Redemption
```

A temporary `calculated_net_flow` feature was created to validate the existing `net_inflow_outflow` column.

The maximum absolute difference was approximately:

```text
0.010000000043874024
```

This represents a very small floating-point difference, confirming that the relationship is consistent.

The temporary validation column was removed after verification.

---

# ⚙️ Feature Engineering

Feature engineering was applied to derive new, meaningful variables from the raw dataset. These features help classify fund flows, investment activity, and enable year‑wise analysis.

# 1. Net Flow Status
Purpose:  
Classify whether a scheme’s net inflow/outflow is positive, negative, or neutral.

# Result:

Positive → 1,633 records

Negative → 1,157 records

No Flow → 325 records

# 2. Investment Status
Purpose:  
Compare fund mobilization vs redemption to identify investment behavior.

# Result:

More Mobilization → 1,633 records

More Redemption → 1,157 records

Equal → 325 records

---

# 📊 Statistical Analysis

## 1. Measure of Central Tendency

Mean, Median, and Mode were calculated for the major numerical variables.

### Variables

```text
net_aum
avg_net_aum
net_inflow_outflow
no_of_folios
fund_mobilized
repurchase_redemption
```

### Key Results

| Variable                |      Mean |    Median |
| ----------------------- | --------: | --------: |
| `net_aum`               | 75,805.39 | 31,617.13 |
| `avg_net_aum`           | 76,722.93 | 31,897.35 |
| `net_inflow_outflow`    |    473.37 |     26.85 |
| `no_of_folios`          | 2,518,408 |   521,606 |
| `fund_mobilized`        | 20,263.59 |  1,022.55 |
| `repurchase_redemption` | 19,790.22 |    880.05 |

### Visual

<img width="719" height="739" alt="Screenshot 2026-08-31 175759" src="https://github.com/user-attachments/assets/38ae0558-ae15-4ae3-82ed-b4c908348d10" />


### Insights

Most numerical variables show a considerable difference between their mean and median. This indicates that the dataset contains extreme high-value observations.

The distributions are generally right-skewed, meaning most observations are concentrated at lower values while a smaller number of observations have very high values.

Therefore, the **median can sometimes provide a more representative view of a typical observation than the mean**.

---

# 📏 2. Variance & Standard Deviation

Variance and standard deviation were used to understand the spread and variability of the numerical variables.

### Variance Results

| Variable                |     Variance |
| ----------------------- | -----------: |
| `no_of_folios`          |  1.52 × 10¹³ |
| `net_aum`               |  ~9.58 × 10⁹ |
| `avg_net_aum`           |  ~9.99 × 10⁹ |
| `fund_mobilized`        | ~1.18 × 10¹⁰ |
| `repurchase_redemption` | ~1.18 × 10¹⁰ |
| `net_inflow_outflow`    |   8.33 × 10⁷ |

### Visual

<img width="751" height="751" alt="Screenshot 2026-08-31 180433" src="https://github.com/user-attachments/assets/ef0c7341-6128-4edd-913d-40cae92dd883" />

### Insights

* `no_of_folios` has the highest variance, showing very uneven investor participation.
* `net_aum` and `avg_net_aum` show considerable variation.
* `fund_mobilized` and `repurchase_redemption` have similar levels of variability.
* `net_inflow_outflow` has comparatively lower variance.

### Standard Deviation

The standard deviation results show:

* `no_of_folios` → approximately **3.90 million**
* `net_aum` → approximately **97,880**
* `avg_net_aum` → approximately **99,935**
* `fund_mobilized` → approximately **108,655**
* `repurchase_redemption` → approximately **108,423**
* `net_inflow_outflow` → approximately **9,126**

### Visual

<img width="752" height="556" alt="Screenshot 2026-08-31 181710" src="https://github.com/user-attachments/assets/23c126d1-88a2-4505-88b9-6dd8e4d04b7e" />


### Insights

The number of folios has the largest absolute spread, indicating major differences in investor participation across records.

Fund mobilization and redemption have similar standard deviations, showing that their fluctuations occur at comparable magnitudes.

Net inflow/outflow has a much smaller standard deviation because inflows and outflows can offset one another.

---

# 📐 3. Skewness

Skewness was analyzed to understand whether the numerical variables are balanced or tilted toward one side.

### Results

| Variable                | Skewness |
| ----------------------- | -------: |
| `net_aum`               |     2.39 |
| `avg_net_aum`           |     2.43 |
| `net_inflow_outflow`    |    -3.42 |
| `no_of_folios`          |     1.98 |
| `fund_mobilized`        |    11.40 |
| `repurchase_redemption` |    11.29 |

### Visual

<img width="612" height="710" alt="Screenshot 2026-08-31 182608" src="https://github.com/user-attachments/assets/bed349ec-637b-47d1-8e1d-b968253d8542" />


### Insights

* `net_aum` and `avg_net_aum` are positively skewed because a few schemes have very large AUM.
* `no_of_folios` is positively skewed because some schemes have exceptionally high investor participation.
* `fund_mobilized` and `repurchase_redemption` are extremely positively skewed due to a small number of very large transactions.
* `net_inflow_outflow` has strong negative skewness because extreme negative outflows extend the distribution toward the left.

---

# 📊 4. Kurtosis

Kurtosis was analyzed to understand the presence of extreme observations and heavy tails.

### Results

| Variable                | Kurtosis |
| ----------------------- | -------: |
| `net_aum`               |     7.73 |
| `avg_net_aum`           |     7.75 |
| `net_inflow_outflow`    |   108.32 |
| `no_of_folios`          |     3.42 |
| `fund_mobilized`        |   175.82 |
| `repurchase_redemption` |   172.09 |

### Visual

<img width="691" height="724" alt="Screenshot 2026-08-31 183158" src="https://github.com/user-attachments/assets/305f743f-da48-4440-bc04-13ad4b9e1171" />


### Insights

* `net_aum` and `avg_net_aum` have high kurtosis, indicating heavy tails.
* `net_inflow_outflow` has extremely high kurtosis, showing that most observations are concentrated around zero while a few extreme observations exist.
* `fund_mobilized` and `repurchase_redemption` have very high kurtosis because occasional large transactions create extreme values.
* `no_of_folios` has comparatively moderate kurtosis.

---

# 📈 Exploratory Data Analysis

## Univariate Analysis

### 1. Distribution of Scheme Categories

**Chart Title:**
`Count of Records by Scheme Category`

<img width="987" height="486" alt="Screenshot 2026-08-31 183440" src="https://github.com/user-attachments/assets/311785d4-959d-42ad-98ba-6726577144ef" />


### Insights:
* The chart shows the distribution of records across scheme categories.

* Income/Debt Schemes → ~1,400 records, the largest share.

* Growth/Equity Schemes → ~900 records, second highest.

* Other Schemes → ~500 records.

* Hybrid Schemes → ~400 records.

* Solution Oriented Schemes → ~150 records, the smallest group.

* Debt schemes dominate in count, equity schemes follow strongly, while smaller categories (Hybrid, Other, Solution Oriented) are underrepresented.
  
* The dataset is skewed toward debt and equity schemes, meaning insights will be most reliable for these categories, while smaller groups may provide limited conclusions.

---

### 2. Distribution of Net AUM

**Chart Title:**
`Distribution of Net AUM`

<img width="982" height="606" alt="Screenshot 2026-08-31 183827" src="https://github.com/user-attachments/assets/add79b3d-39ff-46bc-859f-f8966cbda8c7" />


### Insights:

* The histogram shows how Net AUM is distributed across schemes.

* Most records cluster at low Net AUM values (0–50,000).

* A few schemes extend into the very high range (up to ~777,000), creating a long right tail.

* The majority of schemes manage relatively small assets, while only a handful dominate with very large AUM.

* The distribution is heavily right‑skewed. Small schemes are common, but large schemes disproportionately influence overall averages.

* Asset concentration is unequal — a few big schemes hold most of the assets, while the rest remain small. This highlights the need for category‑level analysis to see which groups dominate the high‑AUM tail.

---

# 📊 Bivariate Analysis

## 1. Average Net AUM by Scheme Category

**Chart Title:**
`Average Net AUM by Scheme Category`

<img width="1111" height="607" alt="Screenshot 2026-08-31 184102" src="https://github.com/user-attachments/assets/6464d6fc-e8a0-485e-82c5-cfc359cf4afa" />


### Insights:
* The chart compares average Net AUM across scheme categories.

* Growth/Equity Schemes → Highest average Net AUM (~180,000).

* Other Schemes → ~162,000, showing strong late growth.

* Hybrid Schemes → ~126,000, steady performance.

* Income/Debt Schemes → ~60,000–70,000, relatively stable.

* Solution Oriented Schemes → Lowest (~30,000–40,000), marginal role.

* Equity schemes dominate asset size, Hybrid schemes balance growth, Debt schemes plateau, Other Schemes surge post‑2021, and Solution Oriented remain weakest.

 * Investor preference leans toward equity and hybrid categories, while debt schemes provide stability and solution‑oriented schemes remain underutilized.

---

## 2. Average Number of Folios Across Years

**Chart Title:**
`Average Number of Folios Across Years`

<img width="1108" height="606" alt="Screenshot 2026-08-31 184417" src="https://github.com/user-attachments/assets/7a1e9d72-c428-4d51-a830-dd1d2aa256a2" />


### Insights:
* The line chart shows investor participation trends from 2019 to 2024

* 2019 → ~1.8 million average folios.

* 2020 → ~2.1 million.

* 2021 → ~2.5 million.

* 2022 → ~2.9 million.

* 2023 → ~3.2 million.

* 2024 → ~3.6 million.

* Folios increase steadily every year, nearly doubling over the six‑year period.

* Investor participation in mutual funds shows consistent growth, reflecting rising confidence and adoption across the reporting years.

---

## 3. Relationship Between Number of Folios and Net AUM

**Chart Title:**
`Relationship Between Number of Folios and Net AUM`

<img width="991" height="612" alt="Screenshot 2026-08-31 184630" src="https://github.com/user-attachments/assets/2805a43d-cd5d-430b-beef-9e1f4379ea48" />


### Insight 

* The scatterplot shows how Net AUM relates to the number of folios, with points colored by net flow status.

* General trend: higher folios → higher Net AUM.

* Clusters:

* Many schemes around 0.5–1 million folios with Net AUM ~30,000–50,000.

* Some schemes with few folios (<200,000) still reach Net AUM >200,000, showing large-ticket investors.

* Net flow status: Positive flows dominate in higher folio ranges, while negative flows appear scattered across lower folio counts.

* Strong positive correlation overall, but dispersion exists — not all schemes with high folios have equally high AUM.

* Investor participation generally drives asset growth, but institutional or high-value investors can skew results, allowing some schemes to achieve large AUM with fewer folios.

---

# 📊 Multivariate Analysis

## 1. Average Fund Mobilized by Scheme Type Across Years

**Chart Title:**
`Average Fund Mobilized by Scheme Type Across Years`

<img width="1109" height="606" alt="Screenshot 2026-08-31 185147" src="https://github.com/user-attachments/assets/863f506b-687c-4a43-9ce3-e87e6b2107dd" />


### Insights:
* The bar chart compares average fund mobilization across scheme types from 2019–2024.

* Open Ended Schemes → Consistently highest mobilization, peaking around 2019 (~ 20,000), dipping mid‑period, and rising again by 2024 (~ 18,000).

* Close Ended Schemes → Very low mobilization, generally <1,000.

* Interval Schemes → Negligible values, close to zero across all years.

* Open Ended schemes dominate every year, showing flexibility and liquidity appeal. Close Ended and Interval schemes remain flat and insignificant.

* Investment activity is driven almost entirely by Open Ended schemes, with 2019’s spike likely reflecting favorable market or regulatory conditions. Other scheme types play only a minor role.
  
---

## 2. Average Net AUM by Scheme Category Across Years

**Chart Title:**
`Average Net AUM by Scheme Category Across Years`

<img width="1205" height="608" alt="Screenshot 2026-08-31 185424" src="https://github.com/user-attachments/assets/e3d3f4d6-46a7-4335-a1b7-61e8bbbfa94b" />

### Insights:
The heatmap shows average Net AUM across scheme categories from 2019–2024, highlighting consistency and growth.

* Growth/Equity Schemes rise from ~58k in 2019 to ~180k in 2024.

* Hybrid Schemes grow steadily to ~126k.

* Income/Debt Schemes stay stable around ~60–70k.

* Other Schemes surge post-2021, reaching ~162k.

* Solution Oriented Schemes remain weakest, though gradually improving.

* Equity and Hybrid categories consistently attract higher AUM, Debt plateaus, and Other Schemes show late momentum. Overall growth is visible across most categories, especially after 2020.

* Equity drives expansion, Hybrids balance growth, Debt remains steady but less appealing, Other Schemes diversify investor choices, and Solution Oriented stay marginal.

---

## 3. Investment Activity and Investor Participation by Scheme Category

**Chart Title:**
`Investment Activity and Investor Participation by Scheme Category`

<img width="1255" height="729" alt="Screenshot 2026-08-31 201351" src="https://github.com/user-attachments/assets/91d9dac1-6b16-48c2-9b09-8c489c2771c0" />


The analysis compares normalized averages of:

* Fund Mobilized
* Repurchase/Redemption
* Net Inflow/Outflow
* Number of Folios

### Insights:
* The chart compares normalized averages of fund mobilization, redemption, net inflows/outflows, and folios across scheme categories.

* Income/Debt Schemes → Highest Fund Mobilized (~ 1.0) and Repurchase/Redemption (~0.95).
👉 Heavy liquidity cycles with large inflows and outflows.

Growth/Equity Schemes → Highest Number of Folios (~ 1.0).
👉 Broad investor participation and retail adoption.

Other Schemes → Highest Net Inflow/Outflow (~ 0.85).
👉 Strong positive fund flows, especially post‑2021.

Hybrid Schemes → Moderate across all metrics (~ 0.5–0.6).
👉 Balanced role in both investor participation and fund activity.

Solution Oriented Schemes → Lowest across all metrics (< 0.2).
👉 Minimal impact on overall investment activity.
  
Debt schemes dominate liquidity, equity schemes lead in participation, other schemes show strong inflows, hybrid schemes balance both, and solution‑oriented schemes remain marginal.

---

# 🔑 Key Findings

### 📌 Mutual Fund Categories

**Income/Debt Oriented Schemes** dominate the dataset in terms of record representation.

### 📌 Asset Management

**Growth/Equity Oriented Schemes** have the highest average Net AUM.

### 📌 Investor Participation

Investor participation increased steadily between **2019 and 2024**.

### 📌 Fund Mobilization

**Open Ended Schemes** consistently dominate fund mobilization.

### 📌 Fund Flows

Other Schemes show strong net inflows, while Income/Debt Schemes have high mobilization and redemption activity.

### 📌 AUM Growth

Growth/Equity and Hybrid Schemes show strong growth in average Net AUM across the analyzed period.

### 📌 Data Distribution

Several financial variables are strongly skewed and contain extreme observations, making median and distribution-based analysis important.

---

# 💡 Business Insights

The analysis suggests that different mutual fund categories play different roles in the mutual fund ecosystem.

**Growth/Equity Schemes** demonstrate strong asset growth and broad investor participation, while **Income/Debt Schemes** contribute significantly to fund mobilization and redemption activity.

The increase in folios from 2019 to 2024 indicates growing investor participation. The positive relationship between folios and Net AUM further suggests that increasing investor participation is generally associated with higher assets under management.

The high skewness and kurtosis in financial variables also show that a relatively small number of observations can have a major influence on overall averages. Therefore, business decisions should consider **median values, category-level comparisons, and distribution patterns** rather than relying only on mean values.

---

# 📁 Project Structure

```text
Mutual-Fund-Investment-Performance-Analysis/
│
├── Main_Project_Mutual Fund Investment & Performance Analysis.ipynb
│
├── dataset/
│   └── main project - mutual fund.xlsx
│
├── README.md
│
└── visualizations/
    ├── univariate_analysis/
    ├── bivariate_analysis/
    └── multivariate_analysis/
```

---

▶️ How to Run the Project

### 1. Clone the Repository
bash
[git clone https://github.com/KanimozhiGanesan18/Mutual-Funds-Report-.git
](https://github.com/KanimozhiGanesan18/Mutual_Funds_Report-)

### 2. Open the Notebook
Open the notebook file:

text
[Main_Project_Mutual Fund Investment & Performance Analysis.ipynb
](https://drive.google.com/drive/folders/1upYOSiedc5vPhXYsE2Bj6KP4AwoOc8Zn?usp=drive_link)
You can run it using Google Colab or Jupyter Notebook.

### 3. Install Required Libraries
Make sure the following Python libraries are installed:

bash
pip install pandas , NumPy , matplotlib , seaborn

### 4. Run the Notebook

Execute the cells sequentially to reproduce:

* Data inspection
* Data cleaning
* Data validation
* Feature engineering
* Statistical analysis
* EDA
* Visualizations
* Business insights

---

# 📚 Analysis Techniques Used

```text
✔ Data Inspection
✔ Data Cleaning
✔ Missing Value Analysis
✔ Duplicate Detection
✔ Data Validation
✔ Feature Engineering
✔ Descriptive Statistics
✔ Central Tendency
✔ Variance
✔ Standard Deviation
✔ Skewness
✔ Kurtosis
✔ Univariate Analysis
✔ Bivariate Analysis
✔ Multivariate Analysis
✔ Trend Analysis
✔ Correlation / Relationship Analysis
✔ Business Insight Generation
```

---

# 🏁 Conclusion

This project demonstrates how Python can be used to analyze real-world mutual fund data and transform raw financial records into meaningful insights.

The analysis identifies important patterns in **Net AUM, fund mobilization, redemption, investor participation, and net fund flows** across different scheme categories and reporting years.

Overall, the project highlights the dominance of Open Ended Schemes in fund mobilization, the strong asset growth of Growth/Equity Schemes, increasing investor participation, and significant variability in financial metrics.

The project provides practical experience in **data preprocessing, statistical analysis, exploratory data analysis, visualization, and business-oriented interpretation**.

---

## 👩‍💻 Author

**Kanimozhi G**

### Skills Demonstrated

`Python` · `Pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `EDA` · `Data Cleaning` · `Feature Engineering` · `Statistical Analysis` · `Data Visualization` · `Business Analysis`

---
