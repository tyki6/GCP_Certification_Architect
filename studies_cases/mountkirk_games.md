# Mountkirk Games Overview
[Link](https://services.google.com/fh/files/blogs/master_case_study_mountkirk_games.pdf)  
Online, session-based, multiplayer games for mobile platforms.
## Keywords need your attentions
- multiplayer games
- mobile
- on-premises environments
- multiple locations
- leaderboards
- Each new game exists in an isolated Google Cloud project
## Technical Env
- GKE
- CLoud Spanner
## Requirement
-  multiple regions
- Low Latency
- Scalability
- Managed Services
## GCP Services they needs
- Agones Kubernetes: Deliver seamless multiplayer gaming experiences
- MIG + VM + Global Load Balancing + GCPU
- Cloud Storage: Store game activity logs in structured files for future analysis
- Cloud Spanner: For leaderboards, but recommended to use memory Store Redis
- BigQuery -> Prediction (Batch: Cloud Storage > DataFlow > BigQuery, Stream: Pub/Sub > Dataflow > BigQuery)
- Cloud Build: CI/CD
- Cloud FireStore: Player Database
- Cloud Bigtable: Time series events