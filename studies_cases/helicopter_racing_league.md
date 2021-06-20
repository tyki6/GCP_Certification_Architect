# Helicopter Racing League Overview
[Link](https://services.google.com/fh/files/blogs/master_case_study_helicopter_racing_league.pdf)  
Global sports league for competitive helicopter racing
## Keywords need your attentions
- AI and ML
- public cloud-first company
- stream
- transcoding
- vm
- storage
## Technical Env
- Tensorflow
- VM
- CronJob
## Requirement
- Low Latency
- Increase telemetry and create additional insights
- new predictions
- High Availability
- expose the predictive models
## GCP Services they needs
- Bigquery + AI platform: migrate existing service to new platform
- Cloud Storage, Cloud CDN: Move the serving of real-time and recorded content closer to their users
- Apigee: expose the predictive models to partners
- Cloud Pub/Sub > Dataflow > BigQuery: Create real-time analytics of viewer consumption
- Transcoder API
- Video Intelligence API, Streaming API: Real-time streaming analysis for live media
