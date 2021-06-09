# Compute Engine(GCE)
[On Your console > Compute Engine](https://console.cloud.google.com/compute/instances)
Run Large-Scale Workloads On VMs Using Google's Infrastructure.**Type: IAAS**
## Objects
- Compute Engine( Virtual Machine)
- Storage (Persistent Disk)
- Instance groups (Groups of vms)  
- VM Manager (OS configuration)
## Features
- create and Manage Lifecycle of vm instances (start - Stop)
- Load Balancing and auto scaling for multiple vm
- attach storage to your vm
- Manage network connectivity and configuration for your vm
# Virtual Machine
[On Your console > Compute Engine > Virtual Machines](https://console.cloud.google.com/compute/instances)
## VM Instance
[On Your console > Compute Engine > Virtual Machines > VM instances](https://console.cloud.google.com/compute/instances)
### New Vm Instance
[On Your console > Compute Engine > Virtual Machines > Create Instance](https://console.cloud.google.com/compute/instancesAdd)
- Specify Name (**Required**)
- Specify Labels (_Optional_)
- Specify [Machine Configuration](#machine-configuration) (**Default**: e2-medium)
- Specify Boot disk (_Optional_): Choose os, public os or your custom image present in your project
- Specify Startup script (_Optional_): In automation Section when you create a vm you can specify a startup script that will run when your instance boosts up or restart.(Copy/paste your bash or shell script)
- Specify Tags for allow HTTP or HTTPS traffic (_Optional_) (**Default**: disable)
### Machine Configuration
- General-purpose : common workload optimized for cost (machine type e2-XXXX), used for web application, small db, dev env
- Compute-optimized: high-performance machine types for compute-intensive-workload(machine type c2-xxx), used for gaming app
- Memory-optimized: large memory machine types for memory-intensive  (machine type m1-XXXX), used for large db
Naming convention: Machine Type Family - Type of workload - Number of Cpu (Example: e2-standard-2)
## Instance Templates
[On Your console > Compute Engine > Virtual Machines > Instance templates](https://console.cloud.google.com/compute/instanceTemplates/list)
Define machine type, image, labels, startup script and other properties you want in a template and **don't waste your time**, to specify **all details** **each times**
### Details
- Can't Be **updated** (to make a change copy it and modify it)
- Define machine type, image, labels, startup script and other properties
### Use Custom Image for your vm
When you create a vm or a template change boot disk and select custom image.
## Preemptible VM
[On Your console > Compute Engine > Virtual Machines > Create Instance > Management > Availability policy > Preemptibility](https://console.cloud.google.com/compute/instancesAdd)
Short-lived cheaper
### Condition
- Your applications are **fault tolerant**
- You are **very cost sensitive** 
- Your workload is **NOT** immediate
### Restriction
- Not always available
- No SLA and Cannot be migrated to regular VM
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

# Storage
[On Your console > Compute Engine > Storage](https://console.cloud.google.com/compute/images)
Manage Os Image, Persistent Disk.
## Images
[On Your console > Compute Engine > Storage > Images](https://console.cloud.google.com/compute/images)
List of Os images
### Create Image
[On Your console > Compute Engine > Storage > Images > Create Image](https://console.cloud.google.com/compute/imagesAdd)
- Specify name
- Specify source: create image from Disk gcloud storage etc...
- Specify Source disk: compute engine disk that contains image
### Details
- Reduce Launch Time
- Create a vm with os patches and software pre-installed
- Prefer using Custom Image to Startup script
## CLI
Create Image: `gcloud compute images create my-image --source-disk=my-disk  --source-disk-zone=europe-west-b`
List Images: `gcloud compute images list`
Details of your image: `gcloud compute images describe my-images`
[Full Documentation](https://cloud.google.com/sdk/gcloud/reference/compute/images)
# Instance Group
[On Your console > Compute Engine > Instance groups](https://console.cloud.google.com/compute/instanceGroups/list)
Group of vm instances managed as a single entity.
## Types
### Managed
Identical Vms created using template.**Auto-scaling, auto healing** (if health check failed recreate a new vm), managed releases without downtime(rolling update, test new version).
#### Create MIG (Managed Instance Group)
[On Your console > Compute Engine > Instance groups > Create Instance Group > New Managed Instance Group](https://console.cloud.google.com/compute/instanceGroups/add?)
- Specify name
- Instance Template is **mandatory**
- Choose multiple zones (_Recommended_)  
- Configure Auto scaling to automatically adjust number of instance(min max instance, auto-scalling metrics like cpu utilisation etc...)
- Configure auto healing to configure health check

Difference between _stateless_ and _stateful_ is: **stateful** is for **managing database**.
#### Rolling Update MIG
On Your console > Compute Engine > Instance groups > Your IG > Rolling Update.
A rolling update is a gradual update of the instances in the instance group to the target configuration of templates.
- Specify new template
- Set mode : ProActive(`now`) or Opporturistic ( _when ig is resized_)
- Configure **Max surge**: how many instances are added at any point in time
- Configure **Max unavailable**: how many instances can be offline during update
#### Rolling Restart/Replace
On Your console > Compute Engine > Instance groups > Your IG > Rolling Restart/Replace.
Gradual restart or replace of all instances in the group.
- Specify replace vm or restart
- Configure **Max surge**: how many instances are added at any point in time
- Configure **Max unavailable**: how many instances can be offline during update
### Unmanaged
Different configuration for VM in same group.**Auto-scaling, auto healing aren't present**.**Not Recommended** unless _you need different kind of VMs_.
## Location
Can be Zonal or Regional.Regional gives you higher availability(**Recommended**)
## CLI 
List Instance Group: `gcloud compute instance-groups list`
Create Managed Instance Group: `gcloud compute instance-groups managed create my-managed-instance-group --zone=europe-west-b --template example-instance-template --size 1`
Create Unmanaged Instance Group: `gcloud compute instance-groups managed create my-unmanaged-instance-group --zone=europe-west-b`
Rolling Update: ` gcloud compute instance-groups managed rolling-action start-update my-instance-groups`
Rolling Restart: ` gcloud compute instance-groups managed rolling-action restart my-instance-groups`
Rolling Replace: ` gcloud compute instance-groups managed rolling-action replace my-instance-groups`
[Full Documentation](https://cloud.google.com/sdk/gcloud/reference/compute/instance-groups)
# VM Manager
[On Your console > Compute Engine > VM Manager](https://console.cloud.google.com/compute/patch/dashboard)
You have OS patch management, it's for automate os patch management or os configuration for large vm fleets