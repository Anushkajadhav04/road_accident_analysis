🚦 UK Road Accident Analysis Dashboard (2005–2012)

Built with Microsoft Power BI | Real Government Data

📌 Project Overview
An interactive Power BI dashboard analyzing 1.5 Million+ real UK road accident records (2005–2012) sourced from the UK Department for Transport. This project uncovers hidden patterns in road safety data to support data-driven policy decisions.

📊 Key Insights:

● 1.19 Million total casualties recorded over 7 years
● 84% of all casualties were Slight — but 2% were Fatal (that's thousands of lives)
● Single carriageways accounted for 871K casualties — the most dangerous road type
● Shocking truth: 73% of accidents happened in FINE weather — not rain or fog!
● Rural roads had far fewer total accidents — but significantly higher fatality rates
● Good news: Accidents declined consistently from 227K (2005) to 171K (2011)


🛠️ Tools Used:

✅ Power BI — Interactive 2-page dashboard with slicers & drill-through
✅ Power Query — Data cleaning & transformation of 1.5M+ rows
✅ DAX — Custom measures for KPIs, YoY trends & severity analysis
✅ Data Source: UK Department for Transport (via Kaggle)


📂 Dataset Information

Source: UK Department for Transport (via Kaggle)
Original Size: 1,504,150 rows × 32 columns
Sample Used: 1,000 rows (balanced across all years)
Years Covered: 2005 – 2012
License: Open Government Licence (OGL)
Link: UK Road Safety Data on Kaggle


⚙️ DAX Measures Used

-- Total Casualties
Total Casualties = SUM('Road Accident'[Number_of_Casualties])

-- Fatal Casualties
Fatal Casualties = 
CALCULATE([Total Casualties], 
'Road Accident'[Accident_Severity] = "Fatal")

-- Fatal %
Fatal % = DIVIDE([Fatal Casualties], [Total Casualties], 0)

-- Year over Year Change
YoY Change % = 
VAR CY = TOTALYTD([Total Casualties], 'Date'[Date])
VAR PY = CALCULATE([Total Casualties], SAMEPERIODLASTYEAR('Date'[Date]))
RETURN DIVIDE(CY - PY, PY, 0)


💡 Key Learnings

● Data Cleaning: Handled nulls, fixed data types, removed duplicates using Power Query
● DAX: Built custom measures for KPIs, severity percentages, and trend analysis
● Insight Generation: Learned to find non-obvious patterns (fine weather causing more accidents)
● Dashboard Design: Applied professional dark navy theme with intuitive layout

