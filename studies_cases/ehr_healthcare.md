# EHR Healthcare Overview
[Link](https://services.google.com/fh/files/blogs/master_case_study_ehr_healthcare.pdf)
## Keywords need your attentions
- iot
- multinational
- growing exponentially
- actually in on premise
## Technical Env
- webb app
- docker
- kubernetes
- SQL + NoSQL
- Azure AD
- alerts via email
## Requirement
- High Availability
- Low Latency
- need prediction
- Security between on-premise system and GCP
- Monitoring & Logging
## GCP Services they needs
- Anthos -> Run Kubernetes clusters anywhere(cloud and on-premises)
- Cloud Logging & Cloud Monitoring -> Alerting Policies for notifications
- BigQuery -> Prediction (Batch: Cloud Storage > DataFlow > BigQuery, Stream: Pub/Sub > Dataflow > BigQuery)
- Cloud Dedicated Interconnect: Secure and high-performance connection
- Cloud CDN: Reduce latency
- ADFS: Azure AD
- Cloud SQL & Cloud Marketplace MongoDB: MYsql -> Cloud SQL, Redis -> Memory Store, MongoDB -> Marketplace