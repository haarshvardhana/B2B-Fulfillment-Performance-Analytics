# 🚚 Apex Logistics: B2B Supply Chain & Fulfillment Command Center

## 📌 The Business Problem
In high-volume B2B logistics, delivery latency is the ultimate metric of system inefficiency. Apex Logistics was experiencing a degradation in Service Level Agreements (SLAs), specifically regarding "On-Time In-Full" (OTIF) deliveries across major regional hubs (Ahmedabad, Surat, Vadodara). 

The objective of this project was to architect an executive-level Power BI command center to isolate operational bottlenecks, track vendor performance, and quantify the exact "friction" in the delivery network.

## 🔬 Analytical Approach: The "Physics" of the Supply Chain
I approached this fulfillment network as a closed thermodynamic system. The target OTIF (86%) represents the state of maximum efficiency. Any deviation from this target is treated as "system entropy." By building dynamic DAX measures, I isolated a critical metric: **an average delivery delay of 1.69 days**, representing the exact friction causing customer churn.

## 📊 Executive KPIs Engineered
Instead of standard retail metrics (Sales/Profit), this dashboard tracks hardcore supply chain performance indicators:
* **OTIF% (On Time In Full):** The ultimate measure of supply chain equilibrium. Currently tracking at a critical 29.0% against an 86% target.
* **LIFR% (Line Fill Rate):** Measures inventory availability and order completeness (Tracking at 66.0%).
* **VOFR% (Volume Fill Rate):** Measures the total volume of goods successfully shipped, highlighting the delta between inventory volume and route efficiency.
* **Delivery Latency Variance:** Custom measures tracking the exact day-count delay of over 13,000 specific orders.

## 💡 Key Actionable Insights
1. **The Fulfillment Gap:** While the Volume Fill Rate (VOFR) is exceptionally high (96.6%), the OTIF% is severely lagging (29.0%). This proves the issue is **not inventory scarcity, but route optimization and last-mile delivery failure.**
2. **Regional Friction Nodes:** Vadodara is experiencing the highest system entropy with OTIF dropping to 27.8%, requiring immediate strategic intervention in local dispatch routing.
3. **The 1.69-Day Bottleneck:** The systemic delay of 1.69 days across the network is causing compounding failures in B2B client SLAs.

## 🛠️ Technical Architecture
* **Tool:** Power BI Desktop
* **Data Modeling:** Architected a high-performance Star Schema, connecting Central Fact Tables (`fact_order_lines`, `fact_orders_aggregate`) with surrounding Dimensions (`dim_customers`, `dim_products`, `dim_date`). 
* **Calculations:** Complex DAX Time-Intelligence stored cleanly in a dedicated Measures Table, utilizing conditional formatting to instantly highlight SLA breaches.
* **UI/UX:** High-contrast corporate dark mode designed for clear executive scanning in an operations war room.

## 🗄️ Data Architecture Note
The raw flat files (CSVs) have been fully transformed and loaded directly into the Power BI data model. I designed the relational model from the ground up to optimize query performance and DAX evaluation. Please download the included `.pbix` file to explore the embedded dataset, the Star Schema relationships, and the complete DAX Measures table.
