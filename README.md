# BI_Dog_Shelter_Analytics_Project
Business Intelligence project transforming dog shelter operations data into actionable insights using SQL Server, SSAS, and Excel dashboards.


# BI Dog Shelter Analytics Project

## Overview
This project was developed for **ISM 6255 – Knowledge Management & Business Intelligence** at Seattle Pacific University.  
The goal was to design a full Business Intelligence solution: starting with an operational database in **Microsoft Access**, transforming it into a **data warehouse and data mart** using **SQL Server Management Studio** and **Visual Studio (SSAS)**, and finally delivering insights through **Excel PivotTables and dashboards**.  

By following this pipeline, I was able to turn scattered dog shelter records into a working cube that supports multidimensional analysis and decision-making.

---

## Build Process

### 1. Microsoft Access – Operational Database
- Created and cleaned an **operational database** in Access containing tables for dogs, adoptions, fosters, shelters, veterinary visits, and volunteers.  
- Verified relationships with primary and foreign keys.  
- Standardized date fields and removed duplicates.  
- This served as the **transactional system (OLTP)**.

### 2. SQL Server Management Studio – Data Warehouse
- Exported the Access database into **SQL Server**.  
- Built a **data warehouse schema** that centralized the shelter’s operational data.  
- Ensured referential integrity and prepared fact and dimension tables for cube design.

### 3. Visual Studio / SSAS – Data Mart (Cube)
- Designed a **star schema** with fact tables (Adoptions, Fosters, Veterinary, Volunteers) at the center.  
- Created dimensions for Dogs, Shelters, Adopters, Foster Homes, and Dates.  
- Added **role-playing date dimensions** to handle adoption dates, foster start/end, and visit timelines.  
- Defined **calculated measures** such as Adoption Rate, Average Foster Duration, Veterinary Cost per Dog, and Volunteer Contribution Ratio.  
- Processed and deployed the cube into an **offline .CUB file**.

### 4. Excel – BI Dashboards
- Connected Excel directly to the cube.  
- Built **PivotTables and PivotCharts** with slicers to enable interactive exploration.  
- Designed dashboards to analyze adoption trends, breed-specific costs, and volunteer engagement across shelters.  
- Excel acted as the **front-end visualization layer** for the BI system.

---

## Deliverables
- `SoyeongCha.accdb` – Access database (OLTP system)  
- `SoyeongCha.cub` – Offline cube (Data Mart)  
- `SoyeongCha.docx` / `SoyeongCha.pdf` – Final project report  
- `SoyeongCha.pptx` – Presentation slides  

---

## Key Insights
- Large dogs were fostered more often, while small and medium dogs had similar adoption rates.  
- German Shepherds showed higher medical costs and longer shelter stays compared to other breeds.  
- Volunteer support varied significantly across shelters, highlighting where additional outreach is needed.  

---

## Lessons Learned
- **Surrogate keys** (e.g., DateID) prevent hierarchy conflicts and should be defined early.  
- Aggregations in SSAS require careful setup—Excel provided a fallback for average calculations.  
- Role-playing dimensions were essential for handling multiple date fields in the cube.  
- Visual Studio offered flexibility in cube design, but debugging hierarchies and relationships took significant time.  

---

## How to Use
1. Open `SoyeongCha.accdb` in Access to see the original operational data model.  
2. Explore the `SoyeongCha.cub` file by opening Excel → *Data* → *From Other Sources* → *From Analysis Services* → connect to the cube.  
3. Use the PivotTables and slicers to analyze adoption trends, veterinary costs, foster durations, and volunteer activity.  
4. Review `SoyeongCha.docx` / `SoyeongCha.pdf` for detailed documentation, and `SoyeongCha.pptx` for a summary presentation.  

---

## Acknowledgment
This project was guided by **Dr. Ryan LaBrie** as part of ISM 6255 at Seattle Pacific University. Every step of the build—Access database design, SQL Server transformation, cube development in Visual Studio, and Excel dashboards—reflects how Business Intelligence tools can be applied to support real-world decisions in animal welfare.  
