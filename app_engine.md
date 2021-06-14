# App Engine (GAE)
[On Your console > App Engine](https://console.cloud.google.com/appengine)  
**Simplest way** to deploy and scale your applications in gcp. **Type: PAAS**(Serverless)
## Features
- Automatic load balancing, auto-scaling
- Managed platform updates , Application health monitoring
- Application versioning
- traffic splitting
## Supports Language
- Go
- Java
- .Net
- Node.JS
- Python
- Docker
## Environment
- Standard: Application run in language specific sandboxes
- Flexible: Application instances run within docker
## Scaling
Scaling to zero only available for standard env
### Type
- Manual: Configure specific number of instance to run
- Basic (only available for standard env): Instance are created as and when request are received, can configure min and max instance
- Automatic: Automatically scale instance based on the load (cpu, utilization etc...) can configure min and max instance
### Startup
- Standard: in Seconds
- Flexible: in minutes
## Create App Engine
[In App Engine > Click create app](https://console.cloud.google.com/appengine)  
- select region
- select Env & Language 
- In your folder code > gcloud init > gcloud app deploy > wait several minutes
- gcloud app browse to open a tab in your browser with application
## Version
Each you deploy a code with gcloud app engine you deploy a new version.You can specify version name with flag `--version`.
Higher version will always set to active version if you don't want that add tag `--no-promote`.
You can **splitting traffic** between multiple version like that: `gcloud app services set-taffic splits=v1=.5,v2=.5` or in web-UI go to [App Engine](https://console.cloud.google.com/appengine) > [Versions](https://console.cloud.google.com/appengine/versions) > select version > split traffic
## Service
**One** Service = **One** application = **One** url dedicated, you can specify your service name in your app.yaml (_field:service_)
## Price
Pricing factors for **standard** environment is instance hours.  
Pricing factors for **flexible** environment are Cpu, Memory & persistent Disk  
[Price documentation](https://cloud.google.com/kubernetes-engine/pricing)
## CLI
Deploy an app: `gcloud app deploy`  
List services: `gcloud app services list`  
List versions: `gcloud app versions list`  
Open app in a browser: ` gcloud app browse --service=my-service`  
Split traffic: `gcloud app services set-taffic splits=v1=.5,v2=.5`  
[Full documentation](https://cloud.google.com/sdk/gcloud/reference/app)  