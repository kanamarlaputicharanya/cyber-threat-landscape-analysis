# cyber-threat-landscape-analysis
# 🔐 Cybersecurity Events Exploratory Data Analysis

## 📌 Project Overview

Cybersecurity incidents occur across different industries, threat actors, motivations, and attack types. However, raw cyber-event records alone do not provide an immediate understanding of where threats are concentrated or how attack patterns change over time.

This project performs an end-to-end **Exploratory Data Analysis (EDA)** on the **University of Maryland Cyber Events Database** to identify meaningful patterns in cyber incidents across **time, industries, threat actors, motivations, and event types**.

The project focuses on transforming raw cybersecurity event data into structured insights that can support **cybersecurity monitoring, risk assessment, and threat analysis**.

---

## ⭐ STAR Framework

### 🟦 Situation

Organizations face different types of cyber threats from different threat actors with varying motivations. Understanding these patterns is important for identifying high-risk industries, recognizing attacker behavior, and improving cybersecurity preparedness.

The dataset contains historical cyber-event records with information about:

- Event date and year
- Threat actor and actor type
- Affected organization
- Industry
- Attack motivation
- Event type and subtype
- Target country
- Actor country
- Event description
- Source information

---

### 🟨 Task

The objective of this project was to analyze the cybersecurity event data and answer questions such as:

- Which types of cyber events occur most frequently?
- Which threat actors dominate the dataset?
- What are the major motivations behind cyber attacks?
- Which industries experience the highest number of recorded events?
- How do attack patterns differ between threat actors?
- How have cyber events changed over time?
- Are certain industries more associated with specific attack types or actors?
- What actionable cybersecurity insights can be derived from the data?

---

### 🟩 Analysis

The analysis was performed using **Python and Pandas**, with visualization and statistical exploration used to understand relationships within the data.

### Data Preparation

The dataset was evaluated for:

- Dataset structure and dimensions
- Column names and data types
- Missing values
- Duplicate records
- Unique identifiers
- Outliers
- Categorical distributions
- Class/category imbalance
- Categorical consistency

### Missing Value Handling

A small number of missing values were identified in:

- `event_subtype`
- `actor_country`
- `source_url`
- `description`

Instead of removing these records, missing categorical/text values were replaced with meaningful labels such as `Unknown` and `Not Available`.

This preserved the original cyber-event records without introducing artificial numerical values.

### Duplicate Check

The dataset contained **13,841 records**.

- Complete duplicate rows: **0**
- Duplicate `slug` identifiers: **0**
- Unique event identifiers: **13,841**

Therefore, no records were removed due to duplication.

### Outlier Analysis

The numerical columns were:

- `year`
- `month`
- `industry_code`

Traditional statistical outlier treatment was not applied because:

- `year` represents a time period
- `month` represents a calendar month
- `industry_code` represents a classification code rather than a continuous measurement

Applying IQR-based removal to these variables could incorrectly remove valid cybersecurity records.

### Class Imbalance

The dataset naturally contains uneven category distributions.

For example:

| Event Type | Percentage |
|---|---:|
| Exploitive | ~49.75% |
| Disruptive | ~31.22% |
| Mixed | ~17.77% |
| Undetermined | ~1.26% |

The imbalance was retained because this project focuses on understanding the **real-world distribution of recorded cyber events**, rather than building a predictive machine-learning model.

---

## 📊 Exploratory Data Analysis

### 1. Univariate Analysis

The following variables were individually analyzed:

- Event Type
- Actor Type
- Industry
- Motive
- Event Subtype
- Year

Visualizations included:

- Count plots
- Horizontal bar charts
- Line charts
- Distribution summaries

### 2. Bivariate Analysis

Relationships between two variables were analyzed, including:

- Event Type × Actor Type
- Industry × Event Type
- Motive × Event Type
- Industry × Actor Type
- Year × Event Type
- Year × Actor Type

### 3. Multivariate Analysis

Multiple dimensions were analyzed together using heatmaps and pivot tables:

- Year × Event Type × Actor Type
- Industry × Event Type × Actor Type
- Motive × Event Type × Actor Type
- Industry × Year × Event Type

---

## 🟪 Results & Key Findings

### 🔹 Cyber Event Types

**Exploitive events** were the most common event type, accounting for approximately **49.75%** of recorded events.

Disruptive events represented approximately **31.22%**, followed by Mixed events.

---

### 🔹 Threat Actors

**Criminal actors dominated the dataset**, with:

**10,523 recorded events**

followed by:

- Hacktivists – 1,907
- Nation-State – 790
- Undetermined – 402
- Hobbyists – 189
- Terrorists – 30

This indicates that financially motivated criminal activity represents a major component of the recorded cyber-event landscape.

---

### 🔹 Attack Motivation

Financial motivation was the most frequently recorded motive.

Among Criminal actors:

**7,765 events** were associated with financial motivation.

Hacktivist activity showed a strong association with **Protest**, with:

**1,495 events**

Nation-State activity showed stronger associations with:

- Political-Espionage
- Sabotage

---

### 🔹 Most Affected Industries

The industries with the highest number of recorded cyber events were:

| Rank | Industry | Events |
|---:|---|---:|
| 1 | Public Administration | 2,733 |
| 2 | Health Care and Social Assistance | 1,899 |
| 3 | Information | 1,555 |
| 4 | Finance and Insurance | 1,353 |
| 5 | Educational Services | 1,335 |
| 6 | Professional, Scientific & Technical Services | 1,169 |
| 7 | Manufacturing | 670 |
| 8 | Retail Trade | 490 |
| 9 | Transportation & Warehousing | 466 |
| 10 | Arts, Entertainment & Recreation | 438 |

Public Administration recorded the highest overall number of events.

---

### 🔹 Cyber Events Over Time

The dataset showed considerable variation in recorded cyber activity over the years.

| Year | Total Events |
|---:|---:|
| 2014 | 633 |
| 2015 | 857 |
| 2016 | 1,104 |
| 2017 | 810 |
| 2018 | 824 |
| 2019 | 1,067 |
| 2020 | 1,747 |
| 2021 | 1,431 |
| 2022 | **2,561** |
| 2023 | 2,443 |
| 2024 | 364 |

**2022 recorded the highest total number of events with 2,561 incidents.**

The sharp decline in 2024 should be interpreted cautiously because the available data may not represent a complete year.

---

## 💡 Cybersecurity Insights

The analysis revealed several important patterns:

1. **Criminal activity dominates the recorded cyber-event landscape.**

2. **Financial motivation is strongly associated with Criminal actors**, highlighting the importance of fraud prevention, access controls, authentication, and financial security monitoring.

3. **Hacktivists show a strong association with Protest-driven Disruptive activity.**

4. **Nation-State actors show stronger associations with Political-Espionage and Sabotage.**

5. **Public Administration and Health Care are among the most affected industries**, indicating the importance of stronger sector-specific cybersecurity controls.

6. **Exploitive events are the dominant event type**, emphasizing the importance of vulnerability management, patching, secure configurations, and application security.

7. **Cyber-event patterns vary by industry, actor, motive, event type, and time**, demonstrating why cybersecurity monitoring should consider multiple dimensions rather than a single metric.

---

## 🛡️ Recommendations

Based on the analysis:

- Strengthen vulnerability and patch management.
- Prioritize protection of application servers and end hosts.
- Improve authentication and access-control mechanisms.
- Strengthen monitoring for financially motivated attacks.
- Develop sector-specific cybersecurity strategies.
- Monitor changes in threat-actor behavior over time.
- Use historical cyber-event trends for cybersecurity planning and resource allocation.
- Maintain structured incident records containing actor, motive, industry, event type, and timeline information.

---

## 🧰 Tech Stack

| Tool | Purpose |
|---|---|
| **Python** | Data analysis and processing |
| **Pandas** | Data cleaning, transformation and analysis |
| **NumPy** | Numerical operations |
| **Matplotlib** | Data visualization |
| **Seaborn** | Statistical visualization |
| **Jupyter Notebook** | Interactive analysis |
| **Excel** | Dataset source/initial inspection |
| **GitHub** | Project documentation and version control |

---

## 📁 Project Structure

```text
Cybersecurity-Events-EDA/
│
├── data/
│   └── UMD Cyber Attacks Dataset.xlsx
│
├── notebooks/
│   └── Cybersecurity_Events_EDA.ipynb
│
├── presentation/
│   └── Cybersecurity_Events_EDA_Presentation.pptx


Dataset

This project uses the University of Maryland Cyber Events Database, which contains structured information about publicly reported cyber events.

The database includes information related to:

Threat actors
Actor types
Motivations
Target organizations
Industries
Event types
Event subtypes
Countries
Dates
Event descriptions

Source: University of Maryland – Cyber Events Database

https://gotech.umd.edu/cyber-events-database

⚠️ Limitations
The dataset represents recorded cyber events and may not capture every cyber incident that occurred.
Recorded event counts can be influenced by reporting and data availability.
Some attacker identities and motivations are classified as Undetermined.
The available 2024 records are substantially lower and may represent incomplete coverage.
Some event subtype values contain combined categories or slightly inconsistent labels.
The analysis identifies patterns and associations but does not establish causal relationships.
🚀 Future Scope

This project can be extended into a more advanced cybersecurity analytics solution by:

Building an interactive Power BI cybersecurity dashboard
Adding severity and impact analysis
Performing cybersecurity time-series forecasting
Applying clustering to identify similar cyber-event patterns
Integrating vulnerability and data-breach datasets
Connecting external threat-intelligence feeds
Developing automated cybersecurity trend monitoring
Building a real-time cybersecurity analytics pipeline
🎓 What I Learned

Through this project, I strengthened my ability to:

Work with real-world cybersecurity data
Perform data cleaning and quality assessment
Handle missing values appropriately
Analyze categorical imbalance
Perform univariate, bivariate and multivariate EDA
Create and interpret meaningful visualizations
Build pivot tables for analytical summaries
Identify relationships between threat actors, motives and attack types
Translate data patterns into cybersecurity insights
Communicate technical findings in a business-friendly manner
👩‍💻 Author

Charanya Kanamarlaputi

B.Tech – Computer Science & Engineering (Cyber Security)

Skills: Python • SQL • Excel • Power BI • Data Analytics • Cybersecurity Analytics

⭐ If you found this project interesting, feel free to explore the notebook and analysis.
│
├── README.md
│
└── requirements.txt
