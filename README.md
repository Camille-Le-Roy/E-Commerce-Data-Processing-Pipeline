<!-- Title -->
<h1 align="center">E-Commerce Data Processing Pipeline</h1>

<p align="center" style="color:#D0D0D0; font-size:0.9em;">
I built a data processing pipeline in Python that transforms 9 relational datasets (100K+ orders) into three analytics-ready base tables with 40+ engineered features for business intelligence.
</p>

<p align="center">
  <img src="images/AI_Generated_ecommerce_elongate.png" alt="E-commerce pipeline header" width="100%" style="max-height:380px; border-radius:10px;">
</p>

---

## Motivation

<span style="color:#D0D0D0; font-size:0.9em;">
Real-world e-commerce data is rarely analysis-ready and often lacks key features needed for modeling tasks such as pricing optimization, churn prediction, or logistics improvement.  
A critical step is transforming raw, fragmented transactional tables into clean analytical datasets.  
In this project, I used a publicly available <a href="https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce" target="_blank" style="color:#D0D0D0; text-decoration:underline;">Brazilian marketplace dataset (2016–2018)</a> to demonstrate this process.
</span>

---

## Raw Datasets

<span style="color:#D0D0D0; font-size:0.9em;">
The initial 9 relational datasets are presented via an Entity Relationship Diagram (ERD), defining the cardinality and mapping the relationships between entities.
</span>

<p align="center">
  <img src="images/ERD list datasets.png" alt="Entity Relationship Diagram" width="90%" style="border-radius:10px;">
</p>

<p align="center" style="color:#9CA3AF; font-size:0.8em;">
  <strong>Figure 1.</strong> Entity Relationship Diagram showing the 9 relational datasets.  
  PK: Primary Key; FK: Foreign Key.
</p>

---

## How It Works

<span style="color:#D0D0D0; font-size:0.9em;">
The data pipeline follows a four-phase approach:
</span>

<ol style="color:#D0D0D0; font-size:0.9em; margin-top:0.5em;">
  <li><strong>Ingestion:</strong> Load data from 9 interconnected CSV files (Orders, Items, Payments, Reviews, Customers, Sellers, Products, Geolocation, and Translations) to form the initial relational model.</li>
  <li><strong>Preparation:</strong> Clean, standardize, and aggregate to resolve one-to-many relationships (e.g. multiple payments per order).</li>
  <li><strong>Merging:</strong> Use strategic left joins to enrich the core <code>Orders</code> table with contextual data (items, payments, reviews, customer info).</li>
  <li><strong>Feature Engineering:</strong> Derive 40+ business metrics including RFM scores, delivery logistics features, and seller performance indicators.</li>
</ol>

<span style="color:#D0D0D0; font-size:0.9em;">
The process outputs three complementary Analytical Base Tables (ABTs): at the order, product, and customer level, ready for modeling.
</span>

<p align="center">
  <img src="images/dataprocessing scheme full.png" alt="Data Processing Pipeline" width="90%" style="border-radius:10px;">
</p>

<p align="center" style="color:#9CA3AF; font-size:0.85em;">
  <strong>Figure 2.</strong> Data processing workflow showing ingestion, cleaning, merging, and feature engineering stages.
</p>

---

## Key Features

<span style="color:#D0D0D0; font-size:0.9em;">
The engineered features derived from the initial columns span the following analytical dimensions:
</span>

<ul style="color:#D0D0D0; font-size:0.9em; margin-top:0.5em;">
  <li><strong>Temporal Features:</strong> Year/month/day/hour extraction, weekend indicators, holiday season flags, approval delays, and carrier pickup times.</li>
  <li><strong>Delivery Performance:</strong> Delivery delay calculations, purchase-to-delivery times, and delivery status categories (early/on-time/late).</li>
  <li><strong>Customer Analytics (RFM):</strong> Order frequency, recency (days since last order), customer lifetime value, and repeat customer identification.</li>
  <li><strong>Economic Metrics:</strong> Average price per item, freight percentage, high-value order flags, and customer lifetime value calculations.</li>
  <li><strong>Product & Seller Analytics:</strong> Category popularity, seller performance rankings, weight-to-price ratios, premium product identification, and top-seller indicators.</li>
</ul>

---

## Results

<span style="color:#D0D0D0; font-size:0.9em;">
The pipeline successfully processed 100,000+ orders across a 2-year period, reducing analytical query complexity by merging 9 tables into 3 purpose-built ABTs.  
The engineered features enable advanced analytics, including RFM customer segmentation, delivery KPI monitoring, seller performance benchmarking, and product catalog optimization, all without complex multi-table joins at query time.
</span>

---

## Code

<p style="color:#D0D0D0; font-size:0.9em; margin-top:1em;">
This pipeline is implemented in Python and available in <a href="https://github.com/Camille-Le-Roy/E-Commerce-Data-Processing-Pipeline/blob/main/Olist_data_processing.ipynb" target="_blank" style="color:#D0D0D0; text-decoration:underline;">this Jupyter Notebook</a>.
</p>


