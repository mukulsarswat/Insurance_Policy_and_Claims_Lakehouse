# Source System Design

## Overview

The original Kaggle insurance dataset is a single denormalized CSV containing customer, policy, claim, incident, vehicle, and fraud information.

In a real insurance company, this data would come from multiple operational systems.

To simulate a production environment, the dataset will be logically split into six source systems before ingestion into the Lakehouse.

---

# Source Systems

## 1. Customer Management System

Source Table

customer_source

Purpose

Stores customer demographic and profile information.

Columns

- customer_id (Generated)
- months_as_customer
- age
- insured_zip
- insured_sex
- insured_education_level
- insured_occupation
- insured_hobbies
- insured_relationship
- capital-gains
- capital-loss

Primary Key

customer_id

---

## 2. Policy Administration System

Source Table

policy_source

Purpose

Stores insurance policy information.

Columns

- policy_number
- customer_id
- policy_bind_date
- policy_state
- policy_csl
- policy_deductable
- policy_annual_premium
- umbrella_limit

Primary Key

policy_number

Foreign Key

customer_id

---

## 3. Claims Management System

Source Table

claim_source

Purpose

Stores claim financial information.

Columns

- claim_id (Generated)
- policy_number
- total_claim_amount
- injury_claim
- property_claim
- vehicle_claim

Primary Key

claim_id

Foreign Key

policy_number

---

## 4. Incident Management System

Source Table

incident_source

Purpose

Stores accident and incident information.

Columns

- incident_id (Generated)
- claim_id
- incident_date
- incident_type
- collision_type
- incident_severity
- authorities_contacted
- incident_state
- incident_city
- incident_location
- incident_hour_of_the_day
- number_of_vehicles_involved
- property_damage
- bodily_injuries
- witnesses
- police_report_available

Primary Key

incident_id

Foreign Key

claim_id

---

## 5. Vehicle Registry System

Source Table

vehicle_source

Purpose

Stores insured vehicle information.

Columns

- vehicle_id (Generated)
- policy_number
- auto_make
- auto_model
- auto_year

Primary Key

vehicle_id

Foreign Key

policy_number

---

## 6. Fraud Monitoring System

Source Table

fraud_source

Purpose

Stores fraud investigation results.

Columns

- fraud_case_id (Generated)
- claim_id
- fraud_reported

Primary Key

fraud_case_id

Foreign Key

claim_id

---

# Source System Relationships

Customer
↓

Policy
↓

Claim
↓

Incident

Vehicle

Fraud

---

# Ingestion Strategy

Each source table will be independently ingested into the Bronze Layer using PySpark.

Bronze Tables

- bronze_customer
- bronze_policy
- bronze_claim
- bronze_incident
- bronze_vehicle
- bronze_fraud