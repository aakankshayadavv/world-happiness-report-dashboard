# world-happiness-report-dashboard
An interactive multi-year Excel dashboard analyzing global happiness metrics (2015-2023) using Power Query for ETL and data transformation.


# World Happiness Report Dashboard (2015–2023)

## Project Overview
This project transforms 9 years of fragmented, inconsistent global spreadsheets from the World Happiness Report (2015–2023) into a single, interactive executive dashboard in Microsoft Excel. The analysis focuses on evaluating whether economic wealth (GDP) is the sole driver of global well-being or if qualitative metrics play a larger role.


---

## 🛠️ Data Engineering & ETL Pipeline (Power Query)
The primary challenge of this project was data structural misalignment, as the official datasets change their schema and column names annually. I built a dynamic transformation pipeline using **Power Query** to clean and append the data:

* **Workbook Schema Automation:** Utilized `= Excel.CurrentWorkbook()` to dynamically ingest all annual tables simultaneously without hardcoding static sheets.
* **Temporal Metadata Extraction:** Because the source tables lacked a "Year" attribute, I extracted the year variable directly from the metadata table names (e.g., `Table2023`) using text delimiters prior to row expansion.
* **Schema Alignment & Mapping:** Standardized and unified shifting multi-year column headers (such as combining legacy `Happiness.Score` or `Life Ladder` variations) into a uniform, single-column destination layout.
* **Time-Series Data Forcing:** Created a calculated calendar date anchor using `= #date([Year], 1, 1)` to allow integration with Excel’s native Timeline Slicers.

---

## Key Insights & Analytical Findings
* **The Wealth Baseline Paradox:** The correlation scatter plot reveals a very low **R-Squared value of 0.0033**, demonstrating that variance in GDP per capita alone does not cleanly predict a nation's overall happiness score.
* **The Social Support Anchor:** Top-performing nations (**Finland**, **Denmark**, and **Iceland**) owe their high placement to heavy density in **Social Support** and **Healthy Life Expectancy** rather than pure economic output.
* **The Freedom Multiplier:** The average index for "freedom to make life choices" sits exceptionally high (between 7.47 and 7.49) among the top 5 global nations, proving qualitative infrastructure is a massive differentiator for peak well-being.

---

## Tech & Tools Used
* **Microsoft Excel:** Data Modeling, Power Query (M-Code Engine), Pivot Tables, Regression Charts, Interactive Slicers.

---
📬 **Let's Connect!**
* **Developer:** Aakanksha Yadav
* **Role:** Aspiring Data Analyst & Developer
