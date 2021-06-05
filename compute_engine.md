# Compute Engine(GCE): Provision & Manage Virtual Machines

## Objects
- Compute Engine
- Persistent Disk
- Cloud Load Balancing

## Features
- create and Manage Lifecycle of vm instances (start - Stop)
- Load Balancing and auto scaling for multiple vm
- attach storage to your vm
- Manage network connectivity and configuration for your vm

# GCE
## New Vm Instance
### [Optional] Labels
Add labels for find your instance easiest 
### Machine Configuration
- General-purpose : common workload optimized for cost (machine type e2-XXXX), used for web application, small db, dev env
- Compute-optimized: high-performance machine types for compute-intensive-workload(machine type c2-xxx), used for gaming app
- Memory-optimized: large memory machine types for memory-intensive  (machine type m1-XXXX), used for large db
Naming convention: Machine Type Family - Type of workload - Number of Cpu (Example: e2-standard-2)
### Boot disk
Choose os, public os or your custom image present in your project
### Startup script
In automation Section when you create a vm you can specify a startup script that will run when your instance boosts up or restart.(Copy/paste your bash or shell script)
### Firewall
Tags for allow HTTP or HTTPS traffic (default: disable)
## Instance Templates
Define machine type, image, labels, startup script and other properties you want in a template and don't waste your time, to specify all details each times
### Details
- Can't Be updated (to make a change copy it and modify it)
- Define machine type, image, labels, startup script and other properties
### Custom Image
In Compute Engine > Storage > Images
### Details
- Reduce Launch Time
- Create a vm with os patches and software pre-installed
- Prefer using Custom Image to Startup script
### Use Custom Image for your vm
When you create a vm or a template change boot disk and select custom image. 
## Internal Ip vs External Ip
- Internal (Private) Ip addresses are internal to a corporate network
- External (Public) Ip addresses are Internet addressable ( by defautl: ip is not constant, every stop ip will be change)
## Price
Basic vm: $27.91 monthly estimate
That's about $0.038 hourly
[Price](https://cloud.google.com/compute/all-pricing?_ga=2.184066726.-1209525355.1611325597)
## Cli
Create VM: `gcloud beta compute instances create my-instance  --image-family=rhel-8 --image-project=rhel-cloud  --zone=europe-west-b`
SSH: `gcloud beta compute ssh --zone "europe-west1-b" "my-instance"  --tunnel-through-iap --project "my-project"`
List VM: `gcloud compute instances list`
List Custom Images: `gcloud compute images list`
VM Templates: `gcloud compute instance-templates describe my-instance-template`
Addresses: `gcloud compute addresses describe my-instance`
[Documentation](https://cloud.google.com/sdk/gcloud/reference/beta/compute/instances)
