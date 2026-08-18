# 🍽️ Zomato Restaurant Data Cleaning & Exploratory Data Analysis (EDA)

An end-to-end data analysis and engineering project combining multi-source tabular data with nested JSON API responses. The project cleans, enriches, standardizes, and performs in-depth exploratory data analysis across global restaurant markets.

---

## 📌 Project Overview
* **Goal**: Merge heterogeneous datasets, clean nested API responses, standardize regional variations (currencies, country codes), and uncover key drivers behind restaurant ratings, pricing, and services.
* **Scope**: Multi-country restaurant listings across Asia, the Americas, Europe, and Oceania.
* **Tech Stack**: Python 3.10+, Pandas, NumPy, Matplotlib, Seaborn, JSON, Google Colab.

---

## 📂 Data Sources & Architecture

| File | Type | Description |
| :--- | :--- | :--- |
| `zomato.csv` | CSV | Core dataset containing primary restaurant listings, addresses, cost, and aggregate ratings. |
| `Country-Code.xlsx` | Excel | Mapping table connecting numeric country codes to standardized country names. |
| `file1.json` – `file5.json` | Nested JSON | Raw API response payloads containing detailed nested restaurant metadata. |

---

## ⚙️ Key Data Pipeline & Engineering Steps

1. **Multi-Source Integration**:
   * Parsed and flattened deeply nested JSON structures using `pandas.json_normalize`.
   * Merged JSON metadata with tabular CSV listings on unique restaurant identifiers.

2. **Data Cleaning & Preprocessing**:
   * Handled missing and non-informative values across rating buckets and locality entries.
   * Dropped redundant metadata columns (e.g., intermediate IDs, raw API keys, unparsed URLs).
   * Corrected data types for geographical coordinates (`Latitude`, `Longitude`), ratings, and vote counts.

3. **Feature Enrichment & Standardization**:
   * **Country Code Mapping**: Mapped country IDs to official names via `Country-Code.xlsx`.
   * **Currency Harmonization**: Resolved mixed local currency symbols into standardized ISO representation.
   * **Cuisine Explosion**: Split multi-valued comma-separated cuisine strings into clean categorical lists for accurate individual cuisine analysis.

---

## 📊 Key Findings & Insights

* **Rating vs. Votes**: High vote counts strongly correlate with stable, verified ratings, whereas low-vote restaurants exhibit significant rating skew.
* **Online Delivery & Booking Impact**: Restaurants offering table booking and online ordering maintain consistently higher customer engagement and aggregate rating distributions.
* **Market Concentration**: The dataset is heavily concentrated in India, with key representations in the UAE, US, UK, and South Africa.
* **Cost Distribution**: Price ranges follow distinct regional thresholds; premium pricing does not always guarantee top ratings, highlighting value-for-money trends.

---

## 🚀 How to Run the Project

### Option 1: Google Colab (Recommended)
1. Open the repository's `zomato_eda.ipynb` in [Google Colab](https://colab.research.google.com/).
2. Run the notebook from top to bottom (`Runtime` $\rightarrow$ `Run all`).

### Option 2: Local Setup
```bash
# Clone the repository
git clone [https://github.com/shreyalr-2005/zomata-eda-project.git](https://github.com/shreyalr-2005/zomata-eda-project.git)
cd zomata-eda-project

# Install required dependencies
pip install numpy pandas matplotlib seaborn openpyxl jupyter

# Launch Jupyter Notebook
jupyter notebook zomato_eda.ipynb
