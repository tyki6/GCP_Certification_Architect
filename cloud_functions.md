# Cloud Function
In cloud Functions
With Cloud Functions you write simple, single-purpose functions that are attached to events emitted from your cloud infrastructure and services. Your function is triggered when an event being watched is fired.Type: FAAS
## Supports Language
- Node.js
- Python
- Go
- Java
- .Net
- Ruby
## Trigger
- Cloud Storage
- Cloud Pub/sub
- HTTP
- Firebase
- Stack drive logging
## Create Function
- Specify name
- Specify trigger
- Authentification (allow unauthentificated = juste need to run url // Reqsuire authentification = need authen present on iam)
- Choose runtime (python java, etc...)
- Choose Entrypoint
## Details
In Cloud function > Your function name > Function details
- metrics: monitorring your functions
- details: general information
- source: source code
- variable: environment variable
- trigger: 
- permissions: allow members to call your function
- logs
- testing: you can trigger your function for testing your work.
## Price
Pay only for what you use
- Number of invocations
- Compute time of the invocations
- Amount of Memory and Cpu provisionned
[Full Documentation](https://cloud.google.com/functions/pricing)
## CLI
Create Cloud Function: `gcloud functions deploy my_function --runtime=python37  gcloud functions deploy my_function --runtime=python37  --trigger-event=providers/cloud.firestore/eventTypes/document.write  --trigger-resource=projects/project_id/databases/(default)/documents/messages/{pushId}`
Details Cloud Function: `gcloud functions describe my_function`
List Cloud Function: `gcloud functions list`
Call Cloud function: `gcloud functions call my_function`
[Full documentation](https://cloud.google.com/sdk/gcloud/reference/functions)
