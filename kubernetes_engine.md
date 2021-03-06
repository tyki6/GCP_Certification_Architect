# Google Kubernetes Engine (GKE)
[On Your console > Kubernetes Engine](https://console.cloud.google.com/kubernetes/list)  
Managed Kubernetes service, auto-repair, auto-upgrade, provides pod and cluster autoscaling, enable cloud logging and monitorring
Uses container optimized os
## Type of cluster
- **Zone cluster**: Single zone master and node running in the same zone
- **Regional cluster**: Replicas of the control plane runs in multiple zones of a given region.Nodes also run in same zones where control plane runs
- **Private cluster**: VPC-native cluster.Nodes only have internal ip
- **Alpha cluster**: Cluster with alpha api & early features.
## Create a GKE
[On Your console > Kubernetes Engine > Create Cluster > Standard](https://console.cloud.google.com/kubernetes/list)  
- Specify a name
- Node Pool (numbers of vm): (Optional)  
- Click on create
## Details of your cluster
On Your console > Kubernetes Engine > Click on your Cluster
- **Details** is for global information like master nodes, number of worker nodes, os, regions etc...
- **Nodes** are for Nodes and node pools(template for groups of nodes created like [MIG](compute_engine.md#instance-group))
- **Storage** is for which disk is attached to cluster
- **Logs** is for all cluster logs
## Create Kubernetes object
Use kubectl commands.
## Workloads
[On Your console > Kubernetes Engine > Click on your Cluster > Workloads](https://console.cloud.google.com/kubernetes/list)  
Kubernetes References: [Deployments](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/), [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/), [StatefulSets](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)
If you select **one workload** you can have **all information** about this object like kubectl describe XXXX XXXXX or Events
## Service & Ingress
[On Your console > Kubernetes Engine > Click on your Cluster > Service & Ingress](https://console.cloud.google.com/kubernetes/list)  
Kubernetes References: [Service](https://kubernetes.io/docs/concepts/services-networking/service/), [Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/) in kubernetes
Services are all service in kubernetes, managed network endpoint that can be used for discovery and load balancing.
Ingress are all ingress in kubernetes, managed network endpoint in internet: collections of rules for routing external HTTP(S) traffic to Services.
## Applications
[On Your console > Kubernetes Engine > Click on your Cluster > Applications](https://console.cloud.google.com/kubernetes/list)  
Deploy a kubernetes applications  like Gitlab, Datadog etc.....(All Application available are present in marketplace)
## Configuration
[On Your console > Kubernetes Engine > Click on your Cluster > Configuration](https://console.cloud.google.com/kubernetes/list)  
ref: Secrets and ConfigMaps in kubernetes
Secrets are all Secrets in kubernetes, are sensitive pieces of information, such as passwords, keys, and tokens. 
ConfigMaps is all ConfigMaps in kubernetes, are designed to store information that is not sensitive, such as environment variables, command-line arguments, and configuration files.
## Storage
[On Your console > Kubernetes Engine > Click on your Cluster > Storage](https://console.cloud.google.com/kubernetes/list)  
ref: Persistent volume and Persistent volume claim in kubernetes
Persistent volume claims are requests for storage of specific size and access mode.
## Object Browser
[On Your console > Kubernetes Engine > Click on your Cluster > Object Browser](https://console.cloud.google.com/kubernetes/list)  
List all kubernetes objects available and list all object present in cluster
## Tips
You want to optimize price? Consider Preemptible vms, choose right machine type for node pools
You want auto-scaling ? configure HPA for deployment & configure auto-scaling for node pools.
## Price
[Price documentation](https://cloud.google.com/kubernetes-engine/pricing)
## CLI
Create a cluster: `gcloud container clusters create my-cluster`  
Connect to your cluster: `gcloud container clusters get-credentials my-cluster`  
Resize cluster: `gcloud container clusters resize my-cluster --node-pool my-node-pool --num-nodes=X`  
Auto-scale Deployment: `kubectl autoscale deployment my-deployment`  
Enable auto-scaling nodes: `gcloud container clusters update --enalbe-autoscaling`  
[Full Documentation](https://cloud.google.com/sdk/gcloud/reference/container/clusters)