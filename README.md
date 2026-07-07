# Sales Performance Analytics Dashboard (MIS)

## 📌 Project Overview
An enterprise-grade, automated Management Information System (MIS) built in Microsoft Excel to ingest, clean, and visualize a multi-year commercial dataset. The system tracks transactional performance metrics across global product lines and regional networks, processing over **1,200 records**, **21,597 units sold**, and **29.96M INR in total profitability**.

The workbook is built following professional data engineering standards, leveraging a **3-tier decoupled architecture** (Ingestion $\rightarrow$ Logic $\rightarrow$ Presentation) to preserve data integrity and optimize processing speeds.

---

## 🛠️ Technical Architecture & Workflow

### 1. Ingestion & ETL Pipeline (Power Query / M-Code)
* **Data Staging:** Implemented automated data ingestion loops using the Power Query engine to eliminate manual data preparation workflows.
* **Text Hygiene & Transformation:** Programmed script logic via the Advanced Editor to handle text case normalization (`Text.Proper`), white-space stripping (`Text.Trim`), and null-value filter exclusions.
* **Schema Integrity:** Enforced explicit schema type-casting across data fields (e.g., date-times, transactional integers, currency decimals) to eliminate computational formula exceptions.

### 2. Analytical Logic & Backend Processing (`Calculations`)
* **Dynamic Range Vectors:** Built highly scalable formulas relying on entire column vector ranges (e.g., `=SUM(CleanedData!G:G)`) ensuring future data entries are automatically calculated without structural script updates.
* **Dynamic Array Arrays:** Combined `=COUNTA()` with `_xlfn.UNIQUE()` to dynamically evaluate non-duplicate active regional nodes and product model catalogs.
* **Interactive Ad-Hoc Lookup Engine:** Developed a specialized model query terminal on the calculations sheet utilizing:
  * `=XLOOKUP()` for rapid, single-condition value matching.
  * `=INDEX(..., MATCH())` to run highly resilient, position-independent matrix coordinate extractions across sheets.

### 3. Executive Visualization Layer (`Dashboard`)
* **Aggregation Engine:** Deployed high-performance Pivot Tables and Pivot Charts to compress raw transactional arrays into clean product velocity overviews.
* **Interactive Cross-Filtering:** Configured multiple interactive visual Slicers linked via unified **Report Connections** to enable non-technical stakeholders to effortlessly slice core operational metrics across time horizons and geographic locations.

---

## 📈 Core Business Insights Generated

By analyzing the aggregated sales data, several high-impact business trends were identified across the product catalog and distribution networks:

### 1. High-Margin Product Drivers (The Pareto Principle)
* **Insight:** While the **Hudson** model drove the highest transaction volume (**7,563 units sold**), the **Salish** model was the undisputed anchor for company profitability, contributing **12.45M INR**—nearly **41.5% of total corporate profits**. 
* **Business Action:** Management should focus premium marketing spend and inventory priority toward the Salish line, while treating Hudson as a volume-driving "loss leader" to attract foot traffic to dealership nodes.

### 2. Regional Performance & Dealer Efficiency
* **Insight:** Dealership performance varies significantly across the network. **Dealer 1288** and **Dealer 1301** emerged as elite hubs, both pushing high quantities (**2,500+ units**) and yielding top-tier profitability (over **1.7M INR** each per year). Conversely, **Dealer 1222** lags significantly in volume (**1,683 units**).
* **Business Action:** Conduct an operational audit on Dealer 1288's sales strategy to isolate best practices (e.g., local promos, floor management) and replicate that playbook at underperforming locations like Dealer 1222.

### 3. Catalog Optimization & Product Rationalization
* **Insight:** The **Champlain** model underperformed heavily across all operational metrics, capturing only **1,064 total units sold** and generating a low-tier profit footprint of **2.38M INR**. 
* **Business Action:** This indicates a lack of market fit or poor regional demand. Management should consider phasing out or discounting the Champlain catalog to free up manufacturing lines and warehouse floor space for high-velocity models like Hudson or high-margin models like Salish.

---

## 📁 Workbook Repository Structure
* `/Dashboard`: Front-facing executive control canvas with charts and connected interactive slicers.
* `/Calculations`: Secure backend storage holding core KPIs, dynamic arrays, and the interactive lookup terminal.
* `/CleanedData`: Power Query staging tab outputting pristine rows directly from the transformation pipeline.
* `/CarSales`: Core production ledger safeguarding active transactional records.



