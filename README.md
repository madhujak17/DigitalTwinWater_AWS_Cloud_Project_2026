# Digital Twin Cloud Framework for Smart Water Distribution Optimization

## Project Overview
This project proposes an event-driven **Digital Twin Cloud Framework** for real-time water distribution optimization, leak localization, and predictive maintenance. Built on **Amazon Web Services (AWS)**, the system continuously synchronizes physical pipeline telemetry with a cloud replica using serverless ingestion pipelines, machine learning inference engines, and polyglot storage tiers.

---

## Project Details
* **Project Title:** Digital Twin Cloud Framework for Smart Water Distribution Optimization
* **Course:** Cloud Computing (BITE412L)
* **Execution Mode:** Individual Project
* **Release Tag:** v1.0-Phase1

---

## Problem Statement
Traditional water monitoring relies on periodic manual inspections and reactive maintenance, leading to high Non-Revenue Water (NRW) losses, delayed leak detection, and infrastructure damage. Existing smart water systems offer real-time visualization but lack predictive analytics and closed-loop valve recommendations required for proactive decision-making.

---

## Key Objectives
1. **Event-Driven Cloud Ingestion:** Ingest simulated pressure, flow, and valve data via AWS IoT Core and AWS Lambda with sub-2-second processing latency.
2. **Predictive AI Analytics:** Train ML models on Amazon SageMaker to achieve high precision and recall in detecting micro-leaks and pressure surges.
3. **Polyglot Storage & Security:** Deploy Amazon S3 for historical data lakes and Amazon RDS for operational states, secured by zero-trust AWS IAM policies.
4. **Automated Incident Response:** Dispatch multi-channel maintenance notifications via Amazon CloudWatch and Amazon SNS within 5 seconds of anomaly detection.
5. **Interactive Digital Twin:** Render real-time spatial heatmaps and valve adjustment suggestions on an EC2-hosted monitoring dashboard.

---

## Proposed Architecture & Framework
The architecture isolates physical simulation, cloud processing, MLOps, and user interaction into distinct logical tiers:

*   **Physical / Simulation Tier:** EPANET / Python Hydraulic Simulator generating pressure and flow telemetry.
*   **Ingestion & Processing Tier:** AWS IoT Core (MQTT Broker) $\rightarrow$ AWS Lambda (Data Cleansing & Rule Engine).
*   **Polyglot Storage Tier:** Amazon S3 (Raw Data Lake) + Amazon RDS (Hot Operational State Database).
*   **Analytics & ML Tier:** Amazon SageMaker (Predictive Model Inference for Leak Detection).
*   **Operations & Presentation Tier:** Amazon CloudWatch + Amazon SNS (Automated Alerts) $\rightarrow$ Amazon EC2 (Digital Twin Control Dashboard).

*Visual architecture diagrams are available in the `/architecture` directory.*

---

## Technology Stack
*   **Cloud Provider:** Amazon Web Services (AWS)
*   **Core AWS Services:** AWS IoT Core, AWS Lambda, Amazon S3, Amazon RDS, Amazon SageMaker, Amazon CloudWatch, Amazon SNS, Amazon EC2, AWS IAM, AWS VPC
*   **Simulation Engine:** EPANET / Python Water Network Tool for Resilience (WNTR)
*   **Data Processing & Machine Learning:** Python (Pandas, NumPy, Scikit-Learn, XGBoost)
*   **Frontend UI:** Web-based Dashboard (Streamlit / React hosted on EC2)

---

## Dataset Details
*   **Dataset Name:** L-TOWN Water Distribution Network Dataset (BattLeDIM Benchmark)
*   **Source:** Zenodo / University of Cyprus / University of Exeter
*   **URL:** `https://zenodo.org/records/4017659`
*   **Dataset Size:** ~150 MB (CSV format)
*   **Records & Features:** 105,120 time-series records across 34 continuous hydraulic features (pressure, flow rate, tank level, pump states)
*   **License:** Creative Commons Attribution 4.0 International (CC BY 4.0)
*   **Purpose:** To simulate realistic, high-frequency pipe network telemetry for streaming into AWS IoT Core and training predictive leak detection models in SageMaker.
*   *Full dataset specification and schema are documented in `/dataset/dataset_details.md`.*
