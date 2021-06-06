# Compute Engine(GCE): Provision & Manage Virtual Machines
Type: IAAS
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
## VM Manager
In Compute Engine > vm Manager
You have OS patch management, it's for automate os patch management or os configuration for large vm fleets
## Internal Ip vs External Ip
- Internal (Private) Ip addresses are internal to a corporate network
- External (Public) Ip addresses are Internet addressable ( by defautl: ip is not constant, every stop ip will be change)
## Price
billed by the second, not billed when vm is stopped
Basic vm: $27.91 monthly estimate
That's about $0.038 hourly
[Price](https://cloud.google.com/compute/all-pricing?_ga=2.184066726.-1209525355.1611325597)
## CLI
Create VM: `gcloud beta compute instances create my-instance  --image-family=rhel-8 --image-project=rhel-cloud  --zone=europe-west-b`
SSH: `gcloud beta compute ssh --zone "europe-west1-b" "my-instance"  --tunnel-through-iap --project "my-project"`
List VM: `gcloud compute instances list`
List Custom Images: `gcloud compute images list`
VM Templates: `gcloud compute instance-templates describe my-instance-template`
Addresses: `gcloud compute addresses describe my-instance`
[Full Documentation](https://cloud.google.com/sdk/gcloud/reference/beta/compute/instances)
# Instance Group
Group of vm instances managed as a single entity.
In Compute Engine > Instance Groups
## Types
### Managed
Identical Vms created using template.Auto-scaling, auto healing (if health check failed recreate a new vm), managed releases without downtime(rolling update, test new version).
#### Create MIG (Managed Instance Group)
- Instance Template is mandatory
- Choose multiple zones (Recommended)  
- Configure Auto scaling to automatically adjust number of instance(min max instance, auto-scalling metrics like cpu utilisation etc...)
- Configure auto healing to configure health check

Difference between stateless and stateful is: stateful is for managing database.
#### Rolling Update MIG
In  Compute Engine > Instance Groups > your instance > Rolling Update
- Specify new template
- Set mode : ProActive(now) or Opporturistic ( when ig is resized)
- Configure Max surge: how many instances are added at any point in time
- Configure Max unavailable: how many instances can be offline during update
#### Rolling Restart/Replace
In  Compute Engine > Instance Groups > your instance > Rolling Restart/Replace
- Specify replace vm or restart
- Configure Max surge: how many instances are added at any point in time
- Configure Max unavailable: how many instances can be offline during update
### Unmanaged
Different configuration for VM in same group.uto-scaling, auto healing aren't present.Not Recommended unless you need different kind of VMs.
## Location
Can be Zonal or Regional.Regional gives you higher availability( Recommended)
## CLI 
List Instance Group: `gcloud compute instance-groups list`
Create Managed Instance Group: `gcloud compute instance-groups managed create my-managed-instance-group --zone=europe-west-b --template example-instance-template --size 1`
Create Unmanaged Instance Group: `gcloud compute instance-groups managed create my-unmanaged-instance-group --zone=europe-west-b`
Rolling Update: ` gcloud compute instance-groups managed rolling-action start-update my-instance-groups`
Rolling Restart: ` gcloud compute instance-groups managed rolling-action restart my-instance-groups`
Rolling Replace: ` gcloud compute instance-groups managed rolling-action replace my-instance-groups`
[Full Documentation](https://cloud.google.com/sdk/gcloud/reference/compute/instance-groups)
# Preemptible VM
Short-lived cheaper
In Compute Engine > Create a vm Instance > Availability policy > Preemptibility
## Condition
- Your applications are fault tolerant
- You are very cost sensitive 
- Your workload is NOT immediate
## Restriction
- Not always available
- No SLA and Cannot be migrated to regular VM