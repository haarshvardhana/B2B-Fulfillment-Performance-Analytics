# 🚚 Apex Logistics: B2B Supply Chain & Fulfillment Command Center

## 📌 The Business Problem
In high-volume B2B logistics, delivery latency is the ultimate metric of system inefficiency. Apex Logistics was experiencing a degradation in Service Level Agreements (SLAs), specifically regarding "On-Time In-Full" (OTIF) deliveries across major regional hubs (Ahmedabad, Surat, Vadodara). 

The objective of this project was to architect an executive-level Power BI command center to isolate operational bottlenecks, track vendor performance, and quantify the exact "friction" in the delivery network.

## 🔬 Analytical Approach: The "Physics" of the Supply Chain
I approached this fulfillment network as a closed thermodynamic system. The target OTIF (86%) represents the state of maximum efficiency. Any deviation from this target is treated as "system entropy." By building dynamic DAX measures, I isolated a critical metric: **an average delivery delay of 1.69 days**, representing the exact friction causing customer churn.

## 📸 Dashboard Preview – Regional Friction Nodes
<img width="1193" height="793" alt="dashboard_01" src="https://github.com/user-attachments/assets/9aa0b498-689a-4711-80d9-e209bd3650c6" />

*Above: OTIF% split by Ahmedabad (29.3%), Surat (30.1%), and Vadodara (27.8%)*

## 📊 Executive KPIs Engineered
Instead of standard retail metrics (Sales/Profit), this dashboard tracks hardcore supply chain performance indicators:
* **OTIF% (On Time In Full):** The ultimate measure of supply chain equilibrium. Currently tracking at a critical 29.0% against an 86% target (defined in dim_targets_orders).
* **LIFR% (Line Fill Rate):** Measures inventory availability and order completeness (Tracking at 66.0%).
* **VOFR% (Volume Fill Rate):** Measures the total volume of goods successfully shipped, highlighting the delta between inventory volume and route efficiency.
* **Delivery Latency Variance:** Custom measures tracking the exact day-count delay of 13,000 late orders (out of 31,729 total orders).

<img width="1317" height="593" alt="dashboard_02" src="https://github.com/user-attachments/assets/c6177a8b-7743-44f2-a152-79a31b896e5c" />

*Above: Product Insights, Customer Insights, and KPI summary table*

## 💡 Key Actionable Insights
1. **The Fulfillment Gap:** While the Volume Fill Rate (VOFR) is exceptionally high (96.6%), the OTIF% is severely lagging (29.0%). This proves the issue is **not inventory scarcity, but route optimization and last-mile delivery failure.**
2. **Regional Friction Nodes:** Vadodara is experiencing the highest system entropy with OTIF dropping to 27.8%, requiring immediate strategic intervention in local dispatch routing.
3. **The 1.69-Day Bottleneck:** The systemic delay of 1.69 days across the network is causing compounding failures in B2B client SLAs, with 13,000 orders missing the agreed delivery date.
4. **VOF% Stability:** Volume Fill Rate remained stable between 96.56% - 96.62% across Q1-Q3, confirming inventory availability is not the bottleneck.

<img width="1015" height="735" alt="dashboard_03" src="https://github.com/user-attachments/assets/97019323-62fd-45e5-9b26-2cdf6be2877f" />

*Above: Late orders distribution (13K total) and VOF% performance trend*

## 🛠️ Technical Architecture
* **Tool:** Power BI Desktop
* **Data Modeling:** Architected a high-performance Star Schema, connecting Central Fact Tables (`fact_order_lines`, `fact_orders_aggregate`) with surrounding Dimensions (`dim_customers`, `dim_products`, `dim_date`). 
* **Calculations:** Complex DAX Time-Intelligence stored cleanly in a dedicated Measures Table, utilizing conditional formatting to instantly highlight SLA breaches.
* **UI/UX:** High-contrast corporate dark mode designed for clear executive scanning in an operations war room.

## 🗄️ Data Architecture Note
The raw flat files (CSVs) have been fully transformed and loaded directly into the Power BI data model. I designed the relational model from the ground up to optimize query performance and DAX evaluation. Please download the included `.pbix` file to explore the embedded dataset, the Star Schema relationships, and the complete DAX Measures table.

<img width="1188" height="822" alt="The Data Model view" src="https://github.com/user-attachments/assets/d4ebc720-0159-41d6-ab7d-69446ffefdeb" />
<img width="355" height="493" alt="The Measures Table view" src="https://github.com/user-attachments/assets/66f60678-14bd-4866-b4e2-6610a4a58161" />


