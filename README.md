# Enterprise Customer Segmentation & Operational Analytics: SQL Case Study

##  Project Overview
This repository showcases an enterprise-level data analytics and engineering pipeline built inside a PostgreSQL environment using the mock Sakila DVD Rental database. 

As a data professional with a deep background in statistical programming, this project demonstrates my ability to bridge relational database architecture with strategic business intelligence. 
The pipeline extracts raw operational data and transforms it into structured layers optimized for executive decision-making, marketing campaign design and operational risk mitigation.

---

##  Tech Stack & Database Architecture
* **Database Engine:** PostgreSQL (v16)
* **Management Interface:** pgAdmin 4
* **SQL Concepts Deployed:** 
- Multi-Table Joins 
- Feature Engineering (Conditional Logic/Dummy Variables) 
- Analytical Window Functions (`PARTITION BY`) 
- Subqueries 
- Common Table Expressions (CTEs) 
- Missing Data Handling (`IS NULL`)
---

##  Core Analytical Pipelines & Business Insights

###  1. Inventory Optimization & Feature Engineering
* **Objective:** Map the relationship between film duration attributes and actual gross rental revenue.
* **Methodology:** Deployed `CASE WHEN` conditional logic to dynamically recode continuous running time durations into distinct categorical tiers (`Short Film`, `Medium Film`, `Long Movie`).
* **Strategic Value:** Enables procurement teams to optimize inventory acquisition budgets by doubling down on cinematic formats yielding the highest return on investment (ROI).

###  2. Customer Loyalty & Behavioral Sequencing
* **Objective:** Build a granular, chronological purchase sequence record per user without collapsing baseline transaction line details.
* **Methodology:** Implemented `ROW_NUMBER() OVER(PARTITION BY customer_id ORDER BY payment_date ASC)` alongside historical customer moving averages.
* **Strategic Value:** Provides the foundational data layer for Customer Lifetime Value (CLV) models, cohort retention pacing, and automated milestone loyalty rewards.

###  3. High-Value VIP Customer Segmentation
* **Objective:** Isolate high-performing revenue cohorts exceeding baseline lifecycle averages.
* **Methodology:** Constructed a scalable `WITH` clause (Common Table Expression) to pre-aggregate customer lifetime transactions before evaluating them via a scalar subquery.
* **Strategic Value:** Empowers marketing departments to identify high-value consumer targets for premium loyalty tiers and personalized retention outreach.

###  4. Revenue Leakage & Churn Tracking
* **Objective:** Audit active operational risk stemming from outstanding physical company assets.
* **Methodology:** Connected the transactional logging tables to user profile datasets, filtering exclusively for active unreturned states (`WHERE return_date IS NULL`).
* **Strategic Value:** Supplies the customer support and branch operations team with an automated, live-updating checklist of overdue accounts to mitigate asset loss.

---

##  Repository Contents
* `SQL_Project.sql`: The complete production-ready SQL script containing the documented multi-stage analytics pipelines.
* `README.md`: Executive-level summary and business intelligence documentation.

---

##  H ow to Run the Script Locally
1. Restore the `dvdrental` sample database on your local PostgreSQL instance.
2. Open `SQL_Project.sql` inside pgAdmin or any preferred SQL editor.
3. Highlight any of the four designated pillars and execute the script (`F5`).