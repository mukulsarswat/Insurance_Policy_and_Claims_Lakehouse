
# Business Requirements Document (BRD)

# Insurance Policy & Claims Lakehouse with SQL Mart Layer

Version: 1.0

Author: Mukul Sarswat

Project Type: End-to-End Data Engineering Lakehouse

Technology Stack:
- Python
- PySpark
- Spark SQL
- Delta Lake
- Databricks
- Git & GitHub
- Power BI
- Hive Metastore / Unity Catalog

---

# 1. Project Overview

Insurance organizations generate large volumes of data from multiple operational systems including customer management, policy administration, claims processing, incident reporting, vehicle registry, and fraud investigation.

These systems operate independently, making it difficult to generate unified business reports, monitor operational performance, detect fraudulent claims, and perform enterprise-level analytics.

The objective of this project is to build a modern Insurance Data Lakehouse that ingests data from multiple simulated source systems, transforms it using a Medallion Architecture (Bronze → Silver → Gold), creates governed analytical data marts, and exposes business-ready datasets for reporting and dashboarding.

---

# 2. Business Problem

Currently, insurance data exists across multiple independent operational systems.

Business users face several challenges:

- Customer information is isolated from policy information.
- Claims cannot be easily correlated with customer demographics.
- Fraud analysis requires manual investigation.
- Executives lack centralized reporting.
- Business KPIs require significant manual effort.
- Historical trend analysis is difficult.
- Data quality issues impact reporting accuracy.

The organization requires a centralized analytics platform capable of integrating all operational data into a single governed data model.

---

# 3. Business Objectives

The project aims to:

- Build a centralized Insurance Lakehouse.
- Simulate enterprise source systems from a denormalized dataset.
- Design a scalable Medallion Architecture.
- Create governed Gold Layer business models.
- Develop reusable ETL pipelines using PySpark.
- Create SQL Analytics Marts.
- Generate executive dashboards.
- Improve fraud visibility through analytical reporting.
- Support future machine learning initiatives.

---

# 4. Stakeholders

## Executive Team

Responsibilities

- Business performance
- Financial overview
- Premium growth
- Claim trends

Expected Reports

- Executive Dashboard
- Monthly KPIs
- Business Summary

---

## Policy Management Team

Responsibilities

- Policy administration
- Premium monitoring
- Coverage analysis

Expected Reports

- Policy Growth
- Premium Distribution
- Policy State Analysis

---

## Claims Management Team

Responsibilities

- Claim processing
- Claim monitoring
- Claim analytics

Expected Reports

- Total Claims
- Average Claim Amount
- Claim Severity
- Claims by State
- Claims by Vehicle

---

## Fraud Investigation Team

Responsibilities

- Fraud monitoring
- Suspicious claim detection

Expected Reports

- Fraud Rate
- Fraud by State
- Fraud by Vehicle
- Fraud by Occupation
- High Risk Claims

---

## Finance Team

Responsibilities

- Financial reporting
- Premium analysis
- Cost monitoring

Expected Reports

- Premium Collected
- Total Claims
- Average Claim
- Loss Ratio
- Claim Cost

---

## Data Analytics Team

Responsibilities

- Data modeling
- Dashboard creation
- Data governance

Expected Outputs

- Gold Layer
- SQL Marts
- Power BI Dataset

---

# 5. Project Scope

## In Scope

- Data ingestion
- Source system simulation
- Bronze Layer
- Silver Layer
- Gold Layer
- Star Schema
- SQL Analytics Marts
- Dashboard
- Data Quality Validation
- Incremental Load Design
- Fraud Analytics

---

## Out of Scope

- Real-time streaming
- Live API integration
- Production deployment
- Role-based access control
- CI/CD deployment
- Enterprise authentication

These can be future enhancements.

---

# 6. Source Systems

The original Kaggle dataset is denormalized.

To simulate an enterprise environment, the data will be logically separated into the following operational systems:

- Customer Management System
- Policy Administration System
- Claims Management System
- Incident Management System
- Vehicle Registry System
- Fraud Monitoring System

Each system will be independently ingested into the Bronze Layer.

---

# 7. Business KPIs

## Policy KPIs

- Total Policies
- Premium Collected
- Average Premium
- Premium by State
- Premium Distribution

---

## Claims KPIs

- Total Claims
- Average Claim Amount
- Injury Claims
- Property Claims
- Vehicle Claims
- Claims by Severity
- Claims by Incident Type

---

## Customer KPIs

- Customer Distribution
- Customer Tenure
- Customer Age Groups
- Occupation Distribution
- Education Distribution

---

## Fraud KPIs

- Fraud Rate
- Fraud by Occupation
- Fraud by State
- Fraud by Vehicle
- Fraud by Claim Amount

---

## Financial KPIs

- Total Premium
- Total Claim Amount
- Average Claim Cost

Note:
Loss Ratio and Claim Turnaround Time will be demonstrated using derived or simulated fields because the public dataset does not include claim settlement dates or earned premium calculations.

---

# 8. Success Criteria

The project will be considered successful if it delivers:

- Complete Medallion Architecture
- Bronze, Silver, and Gold Layers
- Enterprise Star Schema
- SQL Analytics Marts
- Incremental ETL Design
- Data Quality Framework
- Power BI Dashboard
- Fraud Analytics
- Comprehensive Documentation
- GitHub-ready Production Repository

---

# 9. Assumptions

- Public Kaggle dataset represents historical insurance transactions.
- Generated surrogate keys uniquely identify business entities.
- Simulated source systems represent enterprise operational databases.
- Missing business attributes (e.g., settlement date) will be derived when required.
- Data volumes are sufficient to demonstrate scalable ETL design.

---

# 10. Expected Deliverables

Documentation

- Business Requirements
- Source System Design
- Data Dictionary
- Architecture Diagram
- ER Diagram

Engineering

- PySpark ETL Pipelines
- Delta Lake Tables
- SQL Marts
- Incremental Load Logic
- Data Quality Validation

Analytics

- Executive Dashboard
- Claims Dashboard
- Policy Dashboard
- Fraud Dashboard

Repository

- Well-structured GitHub repository
- Source code
- SQL scripts
- Documentation
- Sample outputs