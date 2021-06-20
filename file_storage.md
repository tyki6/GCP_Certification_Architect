# FileStore
[On Your console > FileStore](https://console.cloud.google.com/filestore/instances)  
Cloud File Servers, Shared CLoud file Storage.**Type: SAAS**
## Create An instance
[On Your console > FileStore > Create Instance](https://console.cloud.google.com/filestore/instances/new)
- Specify id
- Specify Instance Type
- Specify Storage type: **HDD**(lower cost) or **SSD**(Best for performance, higher cost)
- Specify Allocate
## CLI
List All Instances: `gcloud filestore instances list`  
Create instance: `gcloud filestore instances create NAME  --description=DESCRIPTION --tier=TIER  --file-share=name=VOLUME_NAME,capacity=CAPACITY  --network=name=NETWORK_NAME,reserved-ip-range=RESERVED_IP_RANGE  --zone=ZONE  --flags-file=FLAGS_FILE`  
Get an instances: `gcloud filestore instances describe my-instance`  
[Full Documentation](https://cloud.google.com/sdk/gcloud/reference/filestore/instances)