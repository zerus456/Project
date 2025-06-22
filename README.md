# Project: Assessing the financial growth of the business and ranking employees by region

## Table of Contents
[1. Overview of the topic](#1-Overview-of-the-topic)

[2. Data processing](#2-Data-processing)

[3. Dashboards](#3-Dashboards)

[4. View this dashboard](#4-View-this-dashboard)

[5. Conclusion](#5-Conclusion)

## 1. Overview of the topic

### Objectives
 This data analysis aims to provide detailed information to have a clear overview of the business performance in the year and its nationwide regional network and highlight key strengths in operational performance to improve efficiency across the network.

 In addition, it also helps us assess the capabilities of employees in each region through the Area Sales Manager (ASM) to promote a culture of responsibility and continuous development among ASMs. By analyzing different aspects of financial performance across all network areas and ASM KPIs, we can gain insights to maintain performance and improve the capabilities of senior managers in the company.

### Data Sources
Data is collected from various departments at the headquarters, including Sales and Operations, Accounting and ASM records.

- File `fact_txn_month_raw_data`: Records the income and expenses incurred by the financial activities of the enterprise in the General Ledger.

- File `fact_kpi_month_raw_data`: Records the final balance of card activities at the end of each month.

- File `fact_kpi_asm`: raw data on ASM monthly sales performance.

### Output
The objective is to develop a comprehensive regional business performance analysis report and a thorough employee performance evaluation report. Furthermore, a dashboard will be established to facilitate the visualization and analysis of these insights, thereby enabling more effective data-driven decision-making and strategic planning.





## 2. Data Processing
### Tool
- Data Processing: Dbeaver + Postgresql

- Data Visualization: Power BI

### Flowchart
![image](https://github.com/user-attachments/assets/a92e6ba3-5270-4d0f-9372-f91b130eb7e2)



### Data Transformation

- Project Description: [Description Projecct.xlsx](https://github.com/user-attachments/files/20520283/Description.Projecct.xlsx)


- Use Dbeaver to import into the database

 File `fact_txn_month_raw_data`

![image](https://github.com/user-attachments/assets/b4a94931-169a-4e51-a9b7-a3f92e90eafe)





 File `fact_kpi_month_raw_data`

 ![image](https://github.com/user-attachments/assets/9ab93669-f2af-424d-b692-dd1bd5c53d9a)



 File `fact_kpi_asm`

![image](https://github.com/user-attachments/assets/da8026a5-2b37-4c38-b9d8-195ba7385caf)


- Create dimension tables by using PostgreSQL Data Definition Language (DDL) [View more](https://github.com/NguyenDuc061104/sql_project/blob/main/SQL/table.sql)

Table: `dim_asm`: Information about employees in each area
![image](https://github.com/user-attachments/assets/0798757f-66e7-443d-b2b5-cca3e204c76c)


Table `dim_city`: Information about cities in each zone area
![image](https://github.com/user-attachments/assets/5ef1b30e-aa0e-4502-bf19-3e74dd3a79b8)

Table `dim_report_item`: Information about the criteria of the report table
![image](https://github.com/user-attachments/assets/0ab08467-e6ba-40c7-a721-a5c56bcec77e)

- Use PL/SQL programming to create a report that runs for each month in 2023.

By providing the YYYYMM parameter, the system can dynamically generate monthly reports by extracting relevant data from the fact tables and joining it with the pre-defined dimension tables. This automated process ensures consistency, reduces manual intervention, and allows for scalable reporting across different time periods with accurate and up-to-date information. [View more](https://github.com/NguyenDuc061104/sql_project/blob/main/SQL/procedure_report.sql)

## 3. Dashboards

- I used python to connect to the postgresql database on dbeaver using the psycopg2 library. I then used the Dash library to visualize the data for the report to give users a more general view.[View more](https://github.com/NguyenDuc061104/sql_project/blob/main/python/db.py)

- Based on the two output tables generated from the data processing and aggregation steps, I developed and visualized six distinct dashboard pages. Each page is equipped with detailed charts, key performance indicators, and in-depth analyses, providing the business with a comprehensive view of financial performance and employee capabilities across regions. These reports serve as powerful decision-support tools, enabling the leadership team to monitor business performance, identify issues, and propose effective strategies to enhance operational efficiency in the financial sector. 

**`Business requirements`**:  *Presents the goals, input data sources, report outputs, and data processing procedures illustrated with visual diagrams to help viewers understand the overall system.*
![image](https://github.com/user-attachments/assets/5c6e8f7a-4daf-4a45-b026-ae7c35b8ab74)



**`Regional summary report page`**: *Highlights key financial metrics and performance overview*

![image](https://github.com/user-attachments/assets/4233ee47-c96d-4d3f-b2e3-dc562a45c383)



**`Regional employee ranking report page`**: provides a detailed report of Regional Sales Manager rankings across all criteria and highlights the increase or decrease in rankings for each ASM*

![image](https://github.com/user-attachments/assets/cba0c44e-0eb7-4f61-8e4e-e99bb6ad6e98)





**`Overview report page`**: The consolidated revenue report page provides an overview of profit, revenue, expenses, and business performance by region with detailed charts and comments.

![image](https://github.com/user-attachments/assets/df861837-cff2-4109-8b71-fc7318a9599a)


**`Cumulative Expenses Page`**: The all-in-one cost tracking report page shows trends, distributions, and cost weights by region to help evaluate cost management effectiveness.

![image](https://github.com/user-attachments/assets/cf22b545-a635-4cec-ab1a-0603ac2b5bb3)


**`ASM Evaluation`**: The ASM evaluation report page summarizes personnel rankings, regional distribution, and outstanding individual business performance.

![image](https://github.com/user-attachments/assets/8638483e-bfcd-485b-978a-cf5e9f635351)


## 4. view this dashboard 

Check my dashboard here: [View my dashboard](https://app.powerbi.com/view?r=eyJrIjoiYTVjMmY5ZDAtNzliNC00YTM2LWJmNzQtMzQ0NWJiZGJiNWY5IiwidCI6IjZhYzJhZDA2LTY5MmMtNDY2My1iN2FmLWE5ZmYyYTg2NmQwYyIsImMiOjEwfQ==)




## 5. Conclusion


Through this personal project, I not only improved my SQL skills, but also learned how to organize data, store it efficiently, and retrieve it when needed. In addition, I gained experience in data visualization by connecting to a database and using PowerBI. Most importantly, I developed a clearer understanding of how data analysis can benefit a business. This allowed me to present data in a way that delivers the most valuable insights to viewers, especially the management team.

Since this is my first project, there are certainly unavoidable mistakes. If you have any feedback, please reach out at anduc061104@gmail.com.

**I believe this project showcases my end-to-end understanding of the data analysis pipeline—from data ingestion to dashboard delivery—and my ability to turn data into meaningful business insights.**



























💻📖😄
