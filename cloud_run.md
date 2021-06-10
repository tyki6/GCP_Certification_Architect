# Cloud Run
[On Your console > Cloud Run](https://console.cloud.google.com/run)
Container to production in seconds. Type: CAAS,Serveless
## Create Service
[On Your console > Cloud Run > Create Service](https://console.cloud.google.com/run)
- specify Name
- Select container image url
- Specify Ingress
- Specify Authentication (**allow unauthenticated** = juste need to run url // **Require authentication** = need authentication present on IAM)
## Details
[On Your console > Cloud Run](https://console.cloud.google.com/run) > Your cloud run name > Service details
- Metrics: monitoring your cloud run
- Revisions: versions of your like [App Engine](app_engine.md#version)
- Logs: all logs concerning your container
- Triggers: ingress & authentication configuration
- Details: get region, url, last revision deployed
- Yaml: yaml configuration like kubernetes(_edition is enable_)
- Permissions: 
## Price
Pricing factors  are Cpu, Memory & Requests and Networking
[Full Documentation](https://cloud.google.com/run/pricing)
## CLI
Deploy a container: `gcloud run deploy my-service --image my-image-url`
List All services: `gcloud run services list`
List All revisions (version): `gcloud run revisions list`
Adjust traffic: `gcloud run services update-traffic my-service --to-revisions=1.0.0=10,2.0.0=90`