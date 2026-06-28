# ShopEasy Marketing Analytics: End-to-End E-Commerce Funnel & Sentiment Pipeline

[![SQL Server](https://img.shields.io/badge/SQL%20Server-2022-red.svg)](https://github.com/AksamAkbar/Marketing_analytics-Sports_products)
[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://github.com/AksamAkbar/Marketing_analytics-Sports_products)
[![VADER](https://img.shields.io/badge/NLP-VADER%20Sentiment-green.svg)](https://github.com/AksamAkbar/Marketing_analytics-Sports_products)
[![PowerBI](https://img.shields.io/badge/Power%20BI-Interactive%20Dashboard-orange.svg)](https://github.com/AksamAkbar/Marketing_analytics-Sports_products)

## 📌 Business Case Overview
ShopEasy, an online retail store specializing in sports apparel and equipment, rolled out several high-budget digital marketing campaigns. Despite elevated investments, performance dropped: **customer engagement decreased, downstream conversions stalled, and marketing expenses scaled without meeting ROI projections.**

This project delivers a complete data analysis pipeline to address these bottlenecks. By extracting, cleaning, and transforming dimensional datasets, the pipeline unifies quantitative campaign metrics with qualitative customer reviews to surface actionable, data-backed optimization insights.

---

## 🛠️ Data Pipeline Architecture

### 1. Data Extraction & Cleaning (SQL Server)
Raw operational files were ingested into SQL Server to construct clean relational reporting models. 
* **Customer Dimensions (`dim_customers`):** Extracted geography identifiers, addressed missing values, and isolated structural address movements.
* **Product Catalog (`dim_products`):** Segmented pricing categories, mapped out seasonal sports products (e.g., Ski Boots, Kayaks), and configured clean standard prices.
* **Customer Reviews (`fact_customer_reviews`):** Cleaned textual whitespace anomalies and standardized double-spacing patterns within raw feedback strings.
* **Customer Engagement (`fact_customer_engagement`):** Cleaned irregular engagement tags and converted text-based upper/lowercase tags into numeric attributes.

### 2. Natural Language Processing & Sentiment Scoring (Python)
To convert unstructured review text into quantitative metrics:
* Applied the **VADER (Valence Aware Dictionary and sEntiment Reasoner)** NLP model to compute programmatic sentiment scores (`Positive`, `Negative`, `Neutral`) for each product review.
* Standardized text data layouts, stripped non-alphanumeric noise, and integrated the finalized tabular sentiment scores directly back into the database architecture.

### 3. Business Intelligence & Dashboard Engineering (Power BI)
Built an interactive dashboard featuring specialized views for stakeholders:
* **Overview Matrix:** High-level tracking of **Conversion Rate, Engagement Rate, Average Order Value (AOV), and Review Scores**.
* **Conversion Funnel Exploration:** Tracks monthly traffic flow, isolating peak conversion windows and seasonal product spikes.
* **Engagement Insights:** Discovers engagement velocities by content vertical (e.g., evaluating high-performing blog media against stable video modules).
* **Sentiment Analysis:** Maps numerical review ratings alongside VADER sentiment metrics to identify specific feedback trends.

---

## 📈 Key Analytical Insights & Data Discoveries
* **Funnel Conversion Velocity:** Conversion metrics bottomed out at 5.0% in October but recovered drastically to 10.2% in December, primarily catalyzed by targeted winter apparel demand (e.g., Ski Boots surging by over 150% in seasonal transaction velocity).
* **Media Engagement Variance:** Blog posts drove the highest raw engagement count across the platform, whereas video assets remained stable but yielded a lower aggregate click-through density.
* **Customer Friction Analysis:** The global store review rating hovered at 3.7 (under the corporate 4.0 KPI target). Python sentiment modeling isolated that negative remarks clustered tightly around specific delivery delays and product sizing inconsistencies.

---

## 📂 Repository Layout
```

├── data/
│   ├── raw/                  # Original data files (customers, engagement, products, reviews)
│   └── processed/            # Programmatically cleaned and scored datasets
├── scripts/
│   ├── data_cleaning.sql     # SQL Server scripts transforming and formatting raw dimension tables
│   └── views_creation.sql    # Finalized views prepared for Power BI ingestion
    └── sentiment_analysis.ipynb # Python VADER model processing customer review text
├── reports/
│   └── Report - Marketing Analytics Business Case (Clean).pptx # Consulting-style executive presentation
    └── Dashboard - Marketing Analytics dashboard (Power BI)
└── README.md                 # Project summary and documentation
