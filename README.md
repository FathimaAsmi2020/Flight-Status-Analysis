# Flight Status Analysis Dashboard (FAA Data)

![Dashboard Preview](Images/dashboard_main.png)

## 📝 Project Overview
This project involves playing the role of a Data Analyst for the **Federal Aviation Administration (FAA)**. Using a massive dataset of over 2 million commercial flight records, I built an interactive Power BI dashboard to monitor flight reliability, identify delay patterns, and understand the root causes of cancellations across major US airports.

---

## 🚩 Problem Statement
In the aviation industry, operational efficiency is critical. The FAA needs to identify whether flight disruptions are driven by specific airlines, regional airport congestion, or external factors like weather. Without a centralized visual tool, it is difficult to see which airports or carriers are consistently underperforming.

---

## 🎯 Objective
* **Analyze** flight status distribution (On-time vs. Delayed vs. Cancelled).
* **Identify** which airlines and airports experience the highest frequency of delays.
* **Visualize** the primary reasons for cancellations (Weather, Carrier, National Air System, etc.).
* **Track** flight volume trends over months and days of the week.

---

## 📊 Dataset Information
The project utilizes a relational database consisting of four primary tables:
* **Flights (Fact Table):** 2 million+ records containing flight numbers, origin/destination, departure delays, and cancellation flags.
* **Airlines (Lookup):** Mapping of IATA airline codes to full carrier names.
* **Airports (Lookup):** Geographic data including airport names, cities, states, and coordinates.
* **Cancellation Codes (Lookup):** Descriptions for the reasons behind cancelled flights (A, B, C, D).

---

## 🛠 Data Cleaning & Transformation
Using **Power Query Editor**, I performed the following ETL steps:
1.  **Column Selection:** Isolated relevant fields (Year, Month, Day of Week, Airline, Origin, Delay, and Cancellation data).
2.  **Conditional Logic:** Created a custom **"Status"** column to categorize every flight as either `On-Time`, `Delayed`, or `Cancelled` based on departure delay minutes and cancellation flags.
3.  **Data Modeling:** Established a **Star Schema** relationship, connecting the Flights fact table to the Airline, Airport, and Cancellation dimension tables.

---

## 🧰 Tools & Tech Used
* **Power BI Desktop:** For data modeling and visualization.
* **Power Query:** For data cleaning and conditional column logic.
* **DAX (Data Analysis Expressions):** Created several key measures:
    * `Total Flights = COUNTROWS(Flights)`
    * `Delayed Flights = CALCULATE([Total Flights], Flights[Status] = "Delayed")`
    * `% Delayed = DIVIDE([Delayed Flights], [Total Flights], 0)`
    * `% On-Time` and `% Cancelled` metrics.

---

## ✨ Dashboard Features
* **KPI Scorecards:** Instant visibility into total flight volume and total delays/cancellations.
* **Monthly Trends:** Line charts showing how flight volume and delay rates fluctuate over the year.
* **Regional Performance:** A bar chart breaking down traffic by Airport City (e.g., Atlanta, Chicago, Dallas).
* **Airline Reliability:** A ranked list of airlines based on their `% Delayed` rate.
* **Cancellation Breakdown:** A Donut chart showing the percentage of cancellations due to Weather vs. Carrier issues.
* **Visual Interactions:** Fully interactive cross-filtering where selecting an airline or airport updates the entire dashboard context.

---

## 🚀 Importance of Project
This dashboard provides a clear, data-driven story of aviation performance. It allows stakeholders to pinpoint "bottleneck" airports and helps airlines compare their punctuality against competitors, ultimately leading to better scheduling and improved passenger experiences.

---

## 🖼 Dashboard Screenshots
<img width="1446" height="809" alt="Screenshot 2026-05-04 135201" src="https://github.com/user-attachments/assets/0306161c-8ef1-4493-b6cb-8bb3aa9f85e9" />

---

## 🏁 Conclusion
The analysis shows that while weather is a major driver for cancellations, certain airlines and airport hubs (like Chicago and Atlanta) consistently face higher congestion. By using this dashboard, the FAA can better allocate resources to improve the overall efficiency of the National Air System.# Flight-Status-Analysis
