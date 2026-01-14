🛡️ Security Operations Dashboard (SOC)

📌 Project Overview

This project focuses on building a Security Operations Center (SOC) Dashboard to monitor, analyze, and visualize security login events from system logs.

The goal is to simulate how a Security Analyst analyzes login activity to identify:

Failed login attempts

Suspicious users and IP addresses

Time-based attack patterns

High-risk behaviors such as late-night logins

The project follows an end-to-end analytics approach using Python, SQL, and Power BI.


🎯 Objectives

Clean and preprocess raw security log data using Python

Store and analyze cleaned data using SQL (MySQL)

Identify risky users, IPs, and login trends

Build an interactive SOC dashboard in Power BI

Present security insights in a clear and visual manner


🧰 Tools & Technologies Used

Python (Pandas, NumPy, Matplotlib)

Jupyter Notebook

MySQL (SQL Analysis)

Power BI

CSV Security Log Dataset

GitHub (Version Control)


📂 Project Structure
Security-Operations-Dashboard/
│
├── data/
│   ├── raw/
│   │   └── security_logs_raw.csv
│   │
│   └── processed/
│       └── security_logs_cleaned.csv
│
├── notebooks/
│   └── security_analysis.ipynb
│
├── sql/
│   └── security_analysis.sql
│
├── dashboard/
│   ├── Security_Operations_Dashboard.pbix
│   └── dashboard_screenshot.png
│
├── README.md
├── requirements.txt
└── .gitignore


🔍 Key Analysis Performed
🐍 Python (Data Cleaning & EDA)

Removed missing and duplicate records

Converted timestamps into date, hour, day, and month

Created new feature: late_night_login

Exploratory Data Analysis (EDA) to understand login behavior


🗄️ SQL Analysis (MySQL)

All SQL queries are available in:
📄 sql/security_analysis.sql

SQL analysis includes:

Total login attempts

Failed login count and percentage

Failed vs successful login comparison

Top risky users based on failed attempts

Top risky IP addresses

Country-wise login analysis

Login trends over time

Hour vs Day failed login heatmap logic

Late-night login risk analysis


📊 Power BI Dashboard KPIs

The dashboard visualizes the following metrics:

Total Login Attempts

Failed Login Percentage

Failed vs Successful Logins

Top 10 Risky Users

Top 10 Risky IP Addresses

Country-wise Login Attempts (Map)

Login Activity Over Time

Hour vs Day Failed Login Heatmap


🧠 Key Security Insights

Certain users and IP addresses generate repeated failed login attempts

Failed logins are concentrated during specific hours and days

Late-night login activity may indicate suspicious behavior

Time-based trends help identify peak attack windows


---Dashboard Preview---
open screenshot to see dashboard:-
Dashboard_Screenshot.png


🚀 How to Run This Project
1️⃣ Clone the Repository
https://github.com/Vandana0210/security_operations_dashboard

2️⃣ Run Python Analysis

Open notebooks/security_analysis.ipynb

Review data cleaning and EDA steps

3️⃣ SQL Analysis

Import security_logs_cleaned.csv into MySQL

Run queries from sql/security_analysis.sql

4️⃣ Power BI Dashboard

Open dashboard/Security_Operations_Dashboard.pbix

Explore interactive visuals

📌 Use Case

This project is useful for:

Aspiring Security Analysts / SOC Analysts

Cybersecurity portfolio projects

Learning SIEM-style log analysis

Demonstrating Python + SQL + Power BI integration

👤 Author

Vandana Kumari
B.Tech CSE (Cyber Security)

Skills:
Python | SQL | Power BI | Data Analytics

