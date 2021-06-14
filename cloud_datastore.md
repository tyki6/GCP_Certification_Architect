# DataStore
[On your Console > DataStore](https://console.cloud.google.com/datastore/entities/query/kind)  
Highly Scalable **NoSQL Document Database**. **Type: SAAS**
## Features
- Automatically scales and partitions data as it grows
- Recommended for upto a few TBs of data
- Supports Transactions, Indexes and SQL like queries
## Structure
You have Kind > Entity(Use namespaces to group Entities)
## Create Entity
[On your Console > Create Entity](https://console.cloud.google.com/datastore/entities/new)  
- Specify Namespace
- Specify Kind
## DashBoard
## Import/Export
Move data between Datastore projects and GCS
## Tips
Use **FireStore** is an **optimized datastore** for **multi device access**.(_Offline mode and data synchronization across multiples devices - mobile, IOT, etc.._)
## Price
**Cloud DataStore** pricing is based on the following components:
- Document reads
- Document writes
- Document deletes
- Stored Data  
[Full Documentation](https://cloud.google.com/datastore/pricing)
## CLI
Create Entity: `gcloud datastore databases create`  
Import Data: `gcloud datastore import  gs://exampleBucket/exampleExport/exampleExport.overall_export_metadata`  
Export Data: `gcloud datastore export gs://exampleBucket  --namespaces='exampleNs' --project='exampleProject'`  
[Full Documentation](https://cloud.google.com/sdk/gcloud/reference/datastore)