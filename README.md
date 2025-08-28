# 🏆 Hack Hours – AI/ML Edition – Genie + Fabric Data Agent

Welcome to the **Compete Hack Hours – AI/ML Edition**!  
This repository contains all resources and setup guides to prepare your environment in **Databricks Genie** and **Microsoft Fabric** for hands-on exploration of AI/BI.  

---

## ✅ Prerequisites
Before starting, make sure you have:  
 🔹 An active **Databricks workspace** with Unity Catalog enabled.  
 🔹 Access to **Microsoft Fabric** with at least **F2 capacity**.  

---

## 📋 Agenda
1. Welcome & Kickoff  
2. From BI → AI/BI vision  
3. AI/BI in Databricks  
   - What it is + Dashboard demo  
4. Databricks Genie  
   - Conversational analytics + demo  
5. Cross-Platform View  
   - Genie (BI insights) vs. Fabric Data Agent (data exploration)  
6. Wrap-Up & Resources  

---

## 🚀 Setup Part 1 – Databricks (Genie)

### 1. Open the **Catalog**
![Step 1](media/4fa91bcd-c573-401e-bdae-8a414e4611b2.png)  
Go to **Catalog** → **Add data → Create a catalog**.  

### 2. Create a Catalog
![Step 2](media/efb7952c-2f2b-4cac-b58a-4e488ae5c3f7.png)  
- Name: `hack_hours_dbws`  
- Type: `Standard`  
- Storage: default workspace location  
- Click **Create**  
![Step 2 Confirmation](media/b73147e6-80d0-49cf-bce9-88993ec40147.png)  
✅ You’ll see *Catalog created!*  

### 3. Create a Schema
![Step 3](media/04845176-2bd2-4f20-b757-f639755e4ac9.png)  
- Inside your catalog, click **Create schema**  
- Name: `v01`  
- Storage auto-fills → `hack_hours_dbws/v01`  

### 4. Create a Table
![Step 4](media/fadb002b-b8eb-43d0-85ca-300e3020f1b0.png)  
- **Create → Table**  
- Upload `products.csv`  
- Catalog: `hack_hours_dbws` | Schema: `v01` | Table: `products`  

### 5. Verify Table
![Step 5](media/00f13b4a-74c6-4634-bedb-c0a0e055a219.png)  
Check columns: `productid`, `productname`, `listprice`  
Databricks will suggest an **AI description** for the table.  

### 6. Add More Tables
![Step 6](media/90ffe617-74cb-495f-9dc1-5af014239f89.png)  
Repeat for `customers`, `orders`, `opportunities`.  

### 7. Run Queries
```sql
SHOW TABLES IN hack_hours_dbws.v01;
```
![Step 7](media/show-tables.png)
```sql
SELECT * FROM hack_hours_dbws.v01.products LIMIT 5;
```
![Step 7](media/products-table.png)

#### Where to run these queries in Databricks

You can execute the SQL above in Databricks using any of the following:

- Databricks SQL (SQL Editor)
  - Open the SQL workspace (SQL in the left nav).
  - Connect to a running SQL warehouse.
  - Create a new query, paste the SQL, and click Run.

- Databricks Notebook
  - Create/open a notebook and either:
    - Set the notebook language to SQL and paste the queries into cells, or
    - Use SQL cell magic:
```sql
%sql
SHOW TABLES IN hack_hours_dbws.v01;
```
    - Or run via Spark in Python:
```python
%python
display(spark.sql("SELECT * FROM hack_hours_dbws.v01.products LIMIT 5"))
```
  - Attach the notebook to a running cluster.

- Data Explorer / Table preview
  - Go to Data -> Tables, locate hack_hours_dbws.v01.products and use the Preview or Query Table option.

Notes and tips:
- If using Unity Catalog, keep using fully qualified names (catalog.schema.table) as shown.
- Ensure you have the required permissions and a running SQL warehouse or cluster.
- To avoid fully-qualified names in a session, you can set a default catalog/schema:
```sql
USE CATALOG hack_hours_dbws;
USE SCHEMA v01;
```

---

## 🚀 Setup Part 2 – Microsoft Fabric

### 1. Create a Workspace
![Fabric Step 1](media/5c41513a-29bf-4ded-ad2f-2d9c34f096d8.png)  
- New workspace → Name: `hack_hours_fabricws`  
- Select **Fabric capacity**  
- Apply  

### 2. Create a Lakehouse
![Fabric Step 2](media/9aa16a30-9fa5-424d-b6e4-b3d4bd4fb8f2.png)  
- New item → **Lakehouse**  
- Name: `lh_canada_sales_v01`  

### 3. Upload Data
![Fabric Step 3](media/41226fb0-a5c1-45f0-9bba-8f9147e29e34.png)  
Upload: `products.csv`, `customers.csv`, `orders.csv`, `opportunities.csv`.  

![Fabric Step 3](media/a876c128-2a93-4176-9f58-aea9595b9613.png)  

### 4. Load Files into Tables
![Fabric Step 4](media/00bb60e9-398c-4073-93a3-513f1640af85.png) 
Right-click each CSV → **Load to Tables → New table**.  

### 5. Verify Tables
![Fabric Step 4](media/02a3f0f4-d4b4-46ee-9620-0e674fe70f23.png) 
Tables `products`, `customers`, `orders`, `opportunities` should appear under **Tables**.  

### 6. Create a Semantic Model
![Fabric Step 5](media/create-semantic-model.png)  
- In your Lakehouse workspace, click **New semantic model**.  
- Select the tables you loaded (`products`, `customers`, `orders`, `opportunities`).  
- Click **Create** to generate the semantic model.  
- You can now use this model for Power BI reports and AI-powered insights in Fabric.  

---

## 🔄 Cross-Platform Comparison

- **Databricks Genie** → Conversational BI, dashboard-driven insights.  
- **Fabric Data Agent** → Natural language data exploration (SQL/DAX/KQL).  

During the Hack Hour, you’ll explore both platforms, compare features, and experience **AI-powered analytics in action**.  

---

## 📚 Resources
- [Databricks AI/BI](https://learn.microsoft.com/en-us/azure/databricks/ai-bi/)  
- [Databricks Dashboards](https://learn.microsoft.com/en-us/azure/databricks/dashboards/) 
- [Databricks Genie](https://learn.microsoft.com/en-us/azure/databricks/genie/)  
- [Microsoft Fabric Data Agent](https://learn.microsoft.com/en-us/fabric/data-science/concept-data-agent)  
- [Unity Catalog Docs](https://learn.microsoft.com/azure/databricks/data-governance/unity-catalog/)  
- [Fabric Lakehouse Docs](https://learn.microsoft.com/fabric/data-engineering/lakehouse-overview)  

---

## ✅ You’re Ready!
Your environments in **Databricks** and **Fabric** are set up.  
Let’s Hack! 🚀
