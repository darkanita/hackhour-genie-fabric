# 🏆 Hack Hours – AI/ML Edition  
**Databricks Genie + Microsoft Fabric**

Welcome to the **Compete Hack Hours – AI/ML Edition**!  
This repository contains all resources and setup guides to prepare your environment in **Databricks Genie** and **Microsoft Fabric** for hands-on exploration of AI/BI.  

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
![Step 2 Confirmation](b73147e6-80d0-49cf-bce9-88993ec40147.png)  
- Name: `hack_hours_dbws`  
- Type: `Standard`  
- Storage: default workspace location  
- Click **Create**  

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
SELECT * FROM hack_hours_dbws.v01.products LIMIT 5;
```

### 8. Use Genie ✨
Ask natural questions like:  
- “Top 5 products by price”  
- “List customers from California”  

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

### 4. Load Files into Tables
![Fabric Step 4](media/a876c128-2a93-4176-9f58-aea9595b9613.png)  
Right-click each CSV → **Load to Tables → New table**.  

### 5. Verify Tables
![Fabric Step 5](media/00bb60e9-398c-4073-93a3-513f1640af85.png)  
Tables `products`, `customers`, `orders`, `opportunities` should appear under **Tables**.  

---

## 🔄 Cross-Platform Comparison

- **Databricks Genie** → Conversational BI, dashboard-driven insights.  
- **Fabric Data Agent** → Natural language data exploration (SQL/DAX/KQL).  

During the Hack Hour, you’ll explore both platforms, compare features, and experience **AI-powered analytics in action**.  

---

## 📚 Resources
- [Databricks Genie](https://www.databricks.com/product/genie)  
- [Microsoft Fabric](https://learn.microsoft.com/fabric/)  
- [Unity Catalog Docs](https://learn.microsoft.com/azure/databricks/data-governance/unity-catalog/)  
- [Fabric Lakehouse Docs](https://learn.microsoft.com/fabric/data-engineering/lakehouse-overview)  

---

## ✅ You’re Ready!
Your environments in **Databricks** and **Fabric** are set up.  
Let’s Hack! 🚀
