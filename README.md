# ⚡ Electric Vehicle Data Analysis | End-to-End Tableau Project

## 📊 Project Overview
This project involves the analysis of a dataset containing over **150,000 electric vehicle records**. The goal was to identify market trends, adoption rates by state, and the dominance of specific manufacturers (like Tesla) using a professional interactive dashboard.

**View the Interactive Dashboard:** [https://public.tableau.com/app/profile/chandan.amruthaluri/viz/EVData_17580497362530/Dashboard1]

---

## 🛠️ Tools & Technologies Used
* **Data Visualization:** Tableau Public (v2024.x)
* **Database:** MySQL (for data querying and validation)
* **Data Processing:** Microsoft Excel / CSV
* **Query Language:** SQL

---

## 📈 Key Insights & Visualizations
The dashboard provides a comprehensive view of the EV market through the following visuals:

### 1. KPI Cards (Key Performance Indicators)
* **Total Vehicles:** 150,413 registered EVs.
* **Avg Electric Range:** 67.83 miles.
* **BEV vs. PHEV Split:**
    * **BEV (Battery Electric):** 77.6% (Dominant preference).
    * **PHEV (Plug-in Hybrid):** 22.4%.

### 2. Advanced Charts Created
* **Adoption Trend (Area Chart):** visualizes the exponential growth of EV registrations from 2011 to 2024.
* **Geospatial Analysis (Choropleth Map):** Shows the concentration of vehicles by State (dominated by Washington).
* **Top Manufacturer Analysis (Bar Chart with Parameter):** A dynamic chart allowing users to filter the "Top N" manufacturers (Tesla leads with 52.7%).
* **CAFV Eligibility (Donut Chart):** A custom **dual-axis chart** showing that 41.8% of vehicles are eligible for Clean Alternative Fuel Vehicle incentives.

---

## 💻 Technical Implementation Details

### Tableau Features Utilized
* **Calculated Fields:** Used `COUNTD` for distinct vehicle counts and `IF/ELSE` logic to categorize BEV vs. PHEV.
* **Parameters:** Implemented a dynamic "Top N" parameter to allow users to adjust the number of top manufacturers displayed.
* **Dual Axis Charts:** Used to create the custom Donut Chart (merging two pie charts) and the Trend Line + Area Chart combo.
* **Custom Formatting:** Applied custom padding, background containers, and floating elements for a polished UI.

### SQL Data Analysis (Sample Queries)
Although visualization was done in Tableau, SQL was used for initial data exploration.

**1. Calculate Breakdown of EV Types:**
```sql
SELECT 
    Clean_Alternative_Fuel_Vehicle_Type,
    COUNT(*) AS Total_Vehicles,
    ROUND(COUNT(*) * 100.0 / (SELECT COUNT(*) FROM ev_population), 2) AS Percentage
FROM ev_population
GROUP BY Clean_Alternative_Fuel_Vehicle_Type;
