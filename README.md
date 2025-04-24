# Clickstream Business Intelligence Application

This project is an end-to-end serverless Business Intelligence (BI) application built on AWS to analyze clickstream data from user behavior on a website.

## 📊 What It Does
This application helps you:
- Collect user event data (clickstream)
- Store and transform it for analytics
- Query it with SQL (Athena)
- Visualize it with dashboards (QuickSight)

## 🧱 Architecture Overview
- **Amazon S3** – stores raw, processed, and result datasets
- **AWS Glue** – performs ETL (Extract, Transform, Load) on clickstream JSON to produce CSV analytics data
- **Amazon Athena** – runs ad hoc SQL queries on the transformed data
- **Amazon QuickSight** – provides interactive dashboards for business users
- **EC2 Instance** – simulates user events (via Python generator)
- **AWS CloudFormation** – provisions all infrastructure

## 📁 Project Structure
```
clickstream-bi-app/
├── cloudformation/
│   └── clickstream-bi-app-template.yaml      # Full AWS infrastructure setup
├── aux/
│   └── generator.py                          # Simulated clickstream event generator
├── screenshots/                             # Contains all result visuals
│   ├── dashboard.png                         # QuickSight dashboard
│   └── s3-results.png                        # Processed data in S3
└── README.md
```

## 🚀 How to Deploy
1. **Launch CloudFormation stack** using the template in `/cloudformation`
2. **Use EC2 or CloudShell** to run the `generator.py` script (20 sample events)
3. **Run the Glue job** to process and transform the data
4. **Explore the output with Athena** via SQL
5. **Visualize results with QuickSight** (map, funnel, average age, etc.)

## 🖼️ Dashboard Sample
![Clickstream Dashboard](screenshots/dashboard.png)

## 🗂️ S3 Output Sample
![S3 Result Structure](screenshots/s3-results.png)

## ✅ Features
- Event data stored in S3
- Glue ETL transforms JSON to CSV
- Athena for SQL exploration
- QuickSight for dashboarding
- Fully serverless and scalable

## 🔒 Cost-Efficient & Secure
- All services are pay-per-use
- IAM roles follow least-privilege principle
- EC2 shuts down after event generation (optional)

## 🧩 Future Improvements
- Automate Glue ETL with Step Functions
- Add lifecycle policies to S3 (e.g., Glacier for old data)
- Use real-time streaming (Kinesis + Lambda)
- Add Cognito auth for QuickSight user restriction

---

Built for demonstration and educational purposes. You can expand it into a production-grade pipeline with more event types, users, and multi-source ingestion.
