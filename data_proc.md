# Cloud DataProc
[On Your Console > Dataproc](https://console.cloud.google.com/dataproc/clusters)  
**Managed** Spark and **Hadoop** service.**Type: SAAS**
## Features
- Multiple Cluster Modes: Single Node, Standard/ High Availability
- Variety of jobs are supported
## Create Cluster
[On Your Console > Dataproc > Create a cluster](https://console.cloud.google.com/dataproc/clustersAdd)  
- Specify Cluster Name
- Cluster type: Standard (1 master, N workers), Single Node(1 master, 0 workers), High Availability(3 master, N workers)
- Configure nodes
- Manage Security
## Setup Jobs
[On Your Console > Dataproc > Jobs](https://console.cloud.google.com/dataproc/jobs)  
Cloud Dataproc jobs lets you submit and manage any Hadoop, Hive, Spark, or Pig job that runs in a Cloud Dataproc clusters.
## Workflows
[On Your Console > Dataproc > Workflows](https://console.cloud.google.com/dataproc/workflows/instances)  
 Workflow is an operation that runs a Directed Acyclic Graph (DAG) of jobs on a cluster. Instantiate workflow templates to create a workflow. 
## Price
**Cloud DataProc** pricing is based on the following components:
- Cluster type
- CPU Usage
- Storage  
[Full Documentation](https://cloud.google.com/dataproc/pricing)
## CLI
Create Cluster: `gcloud dataproc clusters create my_cluster --region=us-central1`  
List Cluster: `gcloud dataproc clusters list --region='us-central1'`  
Create Hadoop Job: `gcloud dataproc jobs submit hadoop --cluster=my_cluster  --jar=my_jar.jar -- arg1 arg2`  
List Job: `gcloud dataproc jobs list --region=us-central1`  
[Full Documentation](https://cloud.google.com/sdk/gcloud/reference/dataproc)