# Power BI Performance Report

This project showcases an interactive **Power BI dashboard** built to analyze the **Plant Co. Sales Performance** using advanced DAX calculations and dynamic visuals.

## Project Features

- **Data Cleaning** using Power Query
- **Date Dimension Table** (Dim_Date) with InPast logic
- **Base Measures**: Sales, Quantity, COGs, Gross Profit
- **YTD vs PYTD** Analysis using `TOTALYTD` and `SAMEPERIODLASTYEAR`
- **SWITCH Logic** for dynamic measure toggling
- **Dynamic Titles** for visuals and charts
- **Conditional Formatting** on cards
- Visuals Used:
  - Line and Stacked Column Chart
  - Waterfall Chart
  - Scatter Plot with Zoom Slider
  - Treemap

## 📂 Files Included

| File Name                       | Description                                      |
|--------------------------------|--------------------------------------------------|
| `Performance_Report.pbix`      | Power BI dashboard file                          |
| `Plant_DTS.xlsx`               | Source data for the dashboard                    |
| `PowerBI_Project_Documentation.docx` | Technical details, DAX code, visuals used        |

## 🧠 Key Metrics & DAX Highlights

```DAX
YTD_Sales = TOTALYTD([Sales], Fact_Sales[Date_Time])
PYTD_Sales = CALCULATE([Sales], SAMEPERIODLASTYEAR(Dim_Date[Date]), Dim_Date[Inpast] = TRUE)
YTD vs PYTD = [S_YTD] - [S_PYTD]
