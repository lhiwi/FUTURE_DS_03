# FUTURE_DS_03 — Marketing Funnel & Conversion Performance Analysis

## Project Overview

This project analyzes marketing campaign funnel and conversion performance using the Bank Marketing dataset. The goal is to understand how contacted customers move through the campaign funnel, identify where conversion drop-offs occur, compare performance across customer segments and contact channels, and provide actionable recommendations to improve campaign effectiveness.

This work was completed as part of the **Future Interns Data Science & Analytics Internship — Task 3: Marketing Funnel & Conversion Performance Analysis**.

---

## Business Objective

The main objective of this project is to help a business answer the following questions:

1. Where are customers dropping off in the marketing funnel?
2. Which contact channels generate better conversion performance?
3. Which customer segments are more likely to convert?
4. How can campaign strategy be improved to increase conversion rates?

---

## Dataset

The project uses the **Bank Marketing Dataset** from the UCI Machine Learning Repository.

Dataset source:  
https://archive.ics.uci.edu/dataset/222/bank+marketing

The dataset contains direct marketing campaign records from a Portuguese banking institution. Each row represents a customer contacted during a marketing campaign, with demographic, financial, campaign, and previous-contact information.

Target variable:

- `y = yes` → customer converted
- `y = no` → customer did not convert

---

## Tools Used

- **Google Colab** — Python-based data cleaning, exploration, and analysis
- **Pandas / NumPy** — data manipulation and KPI calculation
- **Matplotlib** — exploratory visualizations
- **Power BI** — interactive dashboard development
- **GitHub** — project documentation and version control

---

## Project Structure

```text
FUTURE_DS_03/
│
├── data/
│   ├── bank_cleaned.csv
│   ├── funnel_summary.csv
│   ├── contact_conversion.csv
│   ├── previous_contact_conversion.csv
│   ├── job_conversion.csv
│   └── education_conversion.csv
│
├── notebooks/
│   ├── 01_data_understanding_and_cleaning.ipynb
│   └── 02_funnel_analysis_and_insights.ipynb
│
├── dashboard/
│   ├── FUTURE_DS_03.pbix
│   ├── FUTURE_DS_03_Dashboard.pdf
│   └── screenshots/
│
├── README.md
└── requirements.txt
````

---

## Methodology

### 1. Data Understanding and Cleaning

The dataset was first inspected to understand its structure, data types, missing values, duplicates, and categorical placeholders.

Key cleaning decisions:

* No duplicate records were found.
* No formal missing values were present.
* Values labeled as `unknown` were kept as meaningful categories rather than removed.
* A new feature, `was_contacted_before`, was created from the `pdays` column.
* A numeric `conversion_flag` column was created from the target variable `y`.

Created features:

```text
was_contacted_before:
- yes → customer had previous campaign contact
- no → customer had no previous campaign contact

conversion_flag:
- 1 → converted
- 0 → not converted
```

---

### 2. Funnel and Conversion Analysis

The marketing campaign funnel was interpreted as:

```text
All contacted customers → Campaign exposure → Converted customers / Drop-offs
```

The analysis focused on:

* Overall conversion rate
* Converted vs non-converted customers
* Conversion by contact type
* Conversion by previous contact
* Conversion by job category
* Conversion by education level
* Campaign timing and contact frequency patterns

---

### 3. Power BI Dashboard Development

An interactive Power BI dashboard was created with multiple pages to avoid overcrowding and to answer the task questions clearly.

Dashboard pages:

1. **Overview**

   * Total customers
   * Converted customers
   * Drop-off customers
   * Overall conversion rate
   * Funnel outcome chart

2. **Channel Performance**

   * Conversion rate by contact type
   * Customer volume by contact type
   * Converted customers by contact type

3. **Customer Segment Analysis**

   * Conversion rate by job category
   * Conversion rate by education level
   * Conversion rate by marital status

4. **Campaign Optimization Insights**

   * Conversion rate by previous contact
   * Conversion rate by campaign contact frequency
   * Conversion rate by month
   * Optimization recommendations

---

## Key Results

### Overall Funnel Performance

The campaign reached **45,211 customers**.

| Metric                  |  Value |
| ----------------------- | -----: |
| Total Customers         | 45,211 |
| Converted Customers     |  5,289 |
| Drop-off Customers      | 39,922 |
| Overall Conversion Rate | 11.70% |

The campaign has a high final-stage drop-off, with only **11.70%** of contacted customers converting.

---

### Channel Performance

Conversion rate by contact type:

| Contact Type | Conversion Rate |
| ------------ | --------------: |
| Cellular     |          14.92% |
| Telephone    |          13.42% |
| Unknown      |           4.07% |

Cellular contact was the strongest channel, showing both high customer volume and the highest conversion rate. Unknown contact type performed poorly, suggesting a need for better channel tracking and campaign quality control.

---

### Previous Contact Effect

| Previously Contacted | Conversion Rate |
| -------------------- | --------------: |
| Yes                  |          23.07% |
| No                   |           9.16% |

Customers who had been contacted before converted more than twice as well as first-time contacted customers. This shows that follow-up and retargeting campaigns are highly valuable.

---

### Job Segment Performance

Top converting job categories:

| Job Category | Conversion Rate |
| ------------ | --------------: |
| Student      |          28.68% |
| Retired      |          22.79% |
| Unemployed   |          15.50% |
| Management   |          13.76% |
| Admin        |          12.20% |

Students and retired customers showed the strongest conversion performance, while blue-collar and entrepreneur groups had lower conversion rates.

---

### Education Segment Performance

| Education Level | Conversion Rate |
| --------------- | --------------: |
| Tertiary        |          15.01% |
| Unknown         |          13.57% |
| Secondary       |          10.56% |
| Primary         |           8.63% |

Customers with tertiary education had the highest conversion rate, while primary-educated customers showed the lowest conversion performance.

---

## Business Insights

1. The overall campaign conversion rate is low at **11.70%**, indicating a large drop-off between contacted customers and converted customers.

2. Cellular contact is the most effective channel, combining strong conversion performance with high customer volume.

3. Unknown contact methods show weak conversion, suggesting that incomplete channel tracking may hide campaign inefficiencies.

4. Previously contacted customers are significantly more likely to convert, showing the value of follow-up campaigns and retargeting.

5. Students, retired customers, and tertiary-educated customers represent higher-performing customer segments.

6. High campaign contact frequency does not consistently improve conversion, suggesting that over-contacting customers may reduce campaign efficiency.

---

## Recommendations

Based on the analysis, the business should:

1. **Prioritize follow-up campaigns**
   Previously contacted customers convert more than twice as well as customers with no prior contact.

2. **Focus on cellular outreach**
   Cellular contact has the strongest conversion performance and should be treated as a priority channel.

3. **Improve contact channel tracking**
   The poor performance of unknown contact types suggests that better data recording and campaign tracking are needed.

4. **Target high-performing customer segments**
   Students, retired customers, and tertiary-educated customers should receive more tailored campaign messaging.

5. **Avoid excessive repeated contact**
   Increasing the number of campaign contacts does not always improve conversion, so contact frequency should be optimized.

6. **Use monthly performance trends for campaign planning**
   Conversion rates vary by month, so campaign timing should be reviewed alongside monthly customer volume.

---

## Dashboard Preview

The Power BI dashboard includes the following pages:

* Marketing Funnel Overview
* Channel Performance Analysis
* Customer Segment Analysis
* Campaign Optimization Insights

Dashboard files are available in the `dashboard/` folder.

---

## How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/lhiwi/FUTURE_DS_03.git
cd FUTURE_DS_03
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Open notebooks

Open the notebooks in Google Colab or Jupyter Notebook:

```text
notebooks/01_data_understanding_and_cleaning.ipynb
notebooks/02_funnel_analysis_and_insights.ipynb
```

### 4. Open the dashboard

Open the Power BI file:

```text
dashboard/Marking_funnel_dashboard.pbix
```

---

## Final Deliverables

* Cleaned dataset
* Data understanding and cleaning notebook
* Funnel analysis and insights notebook
* Power BI dashboard
* Dashboard PDF export
* Dashboard screenshots
* Professional GitHub documentation

---

## Author

**Hiwot Lemma**
Data Science & Analytics Intern
Future Interns


````

