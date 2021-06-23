# Cloud BigTable
[On your Console > BigTable](https://console.cloud.google.com/bigtable/instances)  
Petabyte scale, wide column **NoSQL DB**(HBase API compatible), **Recommended** for streaming IOT & time series data. **Type: IAAS**
## Features
- handle millions of read/write TPS at very low latency
- single row transactions
- Not serverless: you need to create a server instance
- Time-Series Data
- Clusters Location: Zones, Cluster instaces must be in unique zones
## Create Instance
[On your Console > BigTable > Create Instance](https://console.cloud.google.com/bigtable/create-instance)  
- Specify name
- specify id
- Specify Storage Type: HDD (Good Performance, Lower cost), SSD(Best Performances, Higher cost)
- Create cluster: Region, node etc....
## Table 
View your tables.
## Backups
[On Your Console > BigTable > Your Instance > BackUps](https://console.cloud.google.com/bigtable/instances)  
- You can create a backup of your instance
- restore a backup
- Setup automated backups
## Price
**Cloud DataStore** pricing is based on the following components:
- Type of bigtable: **Prod** or **Dev** instance.
- Total **number of nodes** in your cluster
- Storage
- Network bandwidth  
[Full Documentation](https://cloud.google.com/bigtable/pricing)
## CLI
Create Instance: `gcloud bigtable instances create my-instance-id  --display-name="My Instance"  --cluster-config=id=my-cluster-id,zone=us-east1-c`  
Create Backup: `gcloud bigtable backups create BACKUP_NAME  --instance=INSTANCE_NAME --cluster=CLUSTER_NAME  
--table=TABLE_NAME --expiration-date=2019-03-30T10:49:41Z --async`  
Restore backup: `gcloud bigtable instances tables restore  --source-instance=instance1 --source-cluster=cluster1  --source=backup1 --destination-instance=instance1  --destination=table2`  
[Full Documentation](https://cloud.google.com/sdk/gcloud/reference/bigtable)