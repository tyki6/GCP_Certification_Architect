# FireStore
[On your console > Firestore](https://console.cloud.google.com/firestore)
## Mode
The mode you select here will be permanent for this project.
- Native Mode: **Recommended**
- Datastore Mode: if you have old Data in your datastore
## Import/Export
Move data between Datastore projects and GCS
## Indexes
Composite indexes support queries that mach data across multiple field
### Create Index
- Select collection
- Add your fields
## Price
**Cloud FireStore** pricing is based on the following components:
- Document reads
- Document writes
- Document deletes
- Stored Data  
[Full Documentation](https://cloud.google.com/datastore/pricing)
## CLI
Create Entity: `gcloud firestore databases create`  
Import Data: `gcloud firestore import  gs://exampleBucket/exampleExport/exampleExport.overall_export_metadata`  
Export Data: `gcloud firestore export gs://exampleBucket  --namespaces='exampleNs' --project='exampleProject'`  
[Full Documentation](https://cloud.google.com/sdk/gcloud/reference/datastore)
