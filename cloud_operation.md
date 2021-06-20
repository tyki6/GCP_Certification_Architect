# Cloud Monitoring (Stackdriver Monitoring)
[On your Console > Monitoring](https://console.cloud.google.com/monitoring)  
Tools to **monitor** your infrastructure
## Features
- measures key aspects of services (Metrics)
- Create visualizations(Graphs and Dashboard)
- Configure Alerts(when metrics are not healthy)
- Monitor one or more GCP project
- Monitor one or more AWS accounts
## Workspace
Workspaces are needed to organize monitoring information
## DashBoard
[On your Console > Monitoring](https://console.cloud.google.com/monitoring)  
Create your own **Dashboards** with GCP metrics Like _Grafana_ or _Datadog_.  
[DashBoard Editor](https://console.cloud.google.com/monitoring/dashboards/builder/fd01110c-8610-4cc2-acfc-9f52bc524042)
## Services
[On your Console > Monitoring > Services](https://console.cloud.google.com/monitoring)  
All Service Enabled for collecting metrics.
## Metrics Explorer
[On your Console > Monitoring > Metrics Explorer](https://console.cloud.google.com/monitoring)  
All Metrics present.
## Alerting
[On your Console > Monitoring > Alerting](https://console.cloud.google.com/monitoring)  
Like _AlertManager_. Create **Alert when metrics fired**.
## Uptime Checks
[On your Console > Monitoring > Uptime Checks](https://console.cloud.google.com/monitoring)  
SLA
## Group
[On your Console > Monitoring > Group](https://console.cloud.google.com/monitoring)  
Monitoring lets you define and monitor groups of resources, such as VM instances, databases, and load balancers. You can organize resources into groups based on criteria that make sense for your applications. 
## Price
**Cloud Monitoring** pricing is based on the following components:
- Data
- Api Calls  
[Full Documentation](https://cloud.google.com/stackdriver/pricing)
## CLI
List Dashboard: `gcloud monitoring dashboards list`  
Create DashBoard: `gcloud monitoring dashboards create my-dash`  
[Full Documentation](https://cloud.google.com/sdk/gcloud/reference/alpha/monitoring)
# Cloud Logging (Stackdriver Logging)
[On your Console > Logging](https://console.cloud.google.com/logs/query)  
Real time log management and analysis tool
## Features
- Allow storing, search, analyze and alert on massive volume of data
- exabyte scale, fully managed service
- Ingest Log Data from any source
- Key Features
## Log Type
- Admin Access Logs: need Logging/Logs Viewer or Project/Viewer
- Data Access Logs: need Logging/Private, Logs Viewer, Project/Owner
- System Event Audit Logs: need Logging/LOgs Viewer, Project Viewer
- Policy Denied Logs: Logging/Logs Viewer, Project Viewer
## Logs DashBoard
[On your Console > Logging > Logs Dashboard](https://console.cloud.google.com/logs/dashboard)  
DashBoard where give you info about log present.
## Logs-based Metrics
[On your Console > Logging > Logs-based Metrics](https://console.cloud.google.com/logs/metrics)  
**Logs-based metrics** count the log entries that match a given filter. Logs-based metrics only apply to logs generated in this project, not to logs routed from other projects to buckets in this project.
## Logs Router
[On your Console > Logging > Logs Storage](https://console.cloud.google.com/logs/storage)  
Send logs into an other service like BigQuery, Cloud Pub/sub etc...
### Create Sink
[On your Console > Logging > Logs Storage](https://console.cloud.google.com/logs/storage)  
- specify name
- specify service
## Logs Storage
[On your Console > Logging > Logs Storage](https://console.cloud.google.com/logs/storage)  
ALl Logs Bucket. You can create a new Bucket
### Create Logs Bucket
[On your Console > Logging > Logs Storage > Create logs bucket](https://console.cloud.google.com/logs/storage/bucket)  
- specify Name
- specify retention period
## Price
**Cloud Logging** pricing is based on the following components:
- Ingestion
- Storage  
[Full Documentation](https://cloud.google.com/stackdriver/pricing)
## CLI
Read Logs: `gcloud logging read "resource.type=cloud_run_revision AND resource.labels.service_name=SERVICE" --project PROJECT-ID --limit 10`  
Create logs-based metric: `gcloud logging metrics create METRIC_NAME --description=DESCRIPTION`  
[Full Documentation](https://cloud.google.com/run/docs/logging)
# Cloud Trace (Stackdriver Trace)
[On your Console > Trace](https://console.cloud.google.com/traces/list)  
Distributed Tracing system for gcp: Collect Latency data from Supported Google Cloud Service, Instrumented applications using Cloud Trace Api
# Cloud Debugger (Stackdriver Debugger)
[On your Console > Debugger](https://console.cloud.google.com/debug)  
Capture State of a running applications
- inspect the state of the application directly in the gcp environment
- Take a snapshots variables and call stack
- no need to add logging statements
# Cloud Profiler (Stackdriver Profiler)
[On your Console > Profiler](https://console.cloud.google.com/profiler)  
Identify performance bottlenecks in production