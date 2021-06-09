# Cloud Function
[On Your console > Cloud Function](https://console.cloud.google.com/functions/list)
With Cloud Functions **you write simple, single-purpose functions** that are attached to **events** emitted from your cloud infrastructure and services. Your function is triggered when an event being watched is fired.**Type: FAAS**
## Supports Languages
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
- [On Your console > Cloud Function > Create Function](https://console.cloud.google.com/functions/add)
- Specify name
- Specify trigger
- Authentication (**allow unauthenticated** = juste need to run url // **Require authentication** = need authentication present on IAM)
- Choose runtime (python, java, etc...)
- Choose Entrypoint (started function)
## Details
[On Your console > Cloud Function](https://console.cloud.google.com/functions/list) > Your function name > Function details
- Metrics: monitoring your function
- Details: general information
- Source: source code
- Variable: environment variable
- trigger:  Trigger type, Trigger information
- permissions: allow members to call your function
- logs: all logs concerning your functions
- testing: you can trigger your function for testing your work.
## Price
Pay only for what you use:
- **Number** of _invocations_
- **Compute time** of the _invocations_
- Amount of **Memory** and **Cpu** provisioned
[Full Documentation](https://cloud.google.com/functions/pricing)
## CLI
Create Cloud Function: `gcloud functions deploy my_function --runtime=python37  gcloud functions deploy my_function --runtime=python37  --trigger-event=providers/cloud.firestore/eventTypes/document.write  --trigger-resource=projects/project_id/databases/(default)/documents/messages/{pushId}`
Details Cloud Function: `gcloud functions describe my_function`
List Cloud Function: `gcloud functions list`
Call Cloud function: `gcloud functions call my_function`
[Full documentation](https://cloud.google.com/sdk/gcloud/reference/functions)
