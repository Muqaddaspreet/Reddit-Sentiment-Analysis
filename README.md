# Reddit Sentiment Analysis on AWS (EKS + EMR on EKS + S3 + Apache Spark)

> **Course:** COMP-6231 — Distributed System Design (Concordia University) 

## 🔖 Tags
`distributed-systems` · `apache-spark` · `aws-eks` · `emr-on-eks` · `kubernetes` · `aws-s3` · `pyspark` · `big-data` · `sentiment-analysis` · `cloudwatch`

---

## 📌 Overview

This project performs large-scale **sentiment analysis** on Reddit submissions using a **cloud-native distributed architecture** built on **Apache Spark**, **AWS Elastic Kubernetes Service (EKS)**, **EMR on EKS**, and **Amazon S3**. The input is a multi-year Reddit submissions dataset (≈ **14 GB**, **Jul 2008 → Jan 2013**), which requires distributed storage and compute to process efficiently. :contentReference[oaicite:1]{index=1}

We focus on demonstrating **distributed-system characteristics**—**auto-scaling**, **high availability**, **elasticity**, **data redundancy**, and **security & compliance**—while delivering an end-to-end pipeline from data ingestion to analytics and **CSV outputs** with monitoring via **CloudWatch**. :contentReference[oaicite:2]{index=2} :contentReference[oaicite:3]{index=3} :contentReference[oaicite:4]{index=4} :contentReference[oaicite:5]{index=5}

---

## 🧱 System Components

- **Amazon S3** — durable object storage for raw/processed data. :contentReference[oaicite:6]{index=6}  
- **Amazon EKS** — managed Kubernetes for container orchestration and availability. :contentReference[oaicite:7]{index=7}  
- **EMR on EKS** — optimized Spark runtime and job lifecycle on Kubernetes. :contentReference[oaicite:8]{index=8}  
- **Apache Spark** — distributed analytics engine powering the sentiment jobs. :contentReference[oaicite:9]{index=9}

---

## 🏗️ Architecture at a Glance

1. **Data at Rest:** Reddit dataset stored in **S3** buckets.  
2. **Compute Layer:** **Spark** jobs run via **EMR on EKS**, scheduled onto **EKS** worker nodes.  
3. **Observability:** Job and cluster metrics/logs in **CloudWatch**. :contentReference[oaicite:10]{index=10}

**Distributed Properties we exercise:**

- **Auto-Scaling (EKS):** Scale nodes/pods with workload. :contentReference[oaicite:11]{index=11}  
- **High Availability (EKS):** Multi-AZ cluster design. :contentReference[oaicite:12]{index=12}  
- **Elasticity (EMR):** Dynamically add/remove compute. :contentReference[oaicite:13]{index=13}  
- **Data Redundancy (AWS):** Prevents data loss; ensures continuity. :contentReference[oaicite:14]{index=14}  
- **Security & Compliance:** Encryption, secure networking, timely updates. :contentReference[oaicite:15]{index=15}

---

## 📊 Dataset

- **Source:** Reddit Submissions (Kaggle)  
- **Scale:** ~**14 GB**, **2008-07 → 2013-01** (submissions & engagement signals) :contentReference[oaicite:16]{index=16}  
- **Goal:** Extract **positive / negative / neutral** sentiments; analyze patterns across time/subreddits. :contentReference[oaicite:17]{index=17}

---

## ✅ What the Pipeline Does

1. **Ingest** Reddit data from **S3**.  
2. **Preprocess** text (cleaning/normalization). :contentReference[oaicite:18]{index=18}  
3. **Run distributed sentiment analysis** with **Spark** on **EMR on EKS**. :contentReference[oaicite:19]{index=19}  
4. **Persist results to CSV** back into **S3**. :contentReference[oaicite:20]{index=20}  
5. **Monitor** cluster/pods/logs in **CloudWatch**. :contentReference[oaicite:21]{index=21}

---

## 📬 Results & Findings**

After running the pipeline, the system categorized Reddit submissions into positive, negative, and neutral sentiments and saved a CSV of results. The orchestration of containers/pods in Kubernetes can be traced via CloudWatch logs during and after execution.

---

## 📚 References**

- Project Report excerpts (system/services, dataset scale & timeline, results & monitoring). :contentReference[oaicite:16]{index=16}  
- Presentation slides excerpts (component summaries; distributed characteristics). :contentReference[oaicite:17]{index=17}

---



