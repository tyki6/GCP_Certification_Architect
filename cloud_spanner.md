# Cloud Spanner
[On your console > Spanner](https://console.cloud.google.com/spanner/instances)  
Fully Managed, missions critical, relation(SQL), Globally Distributed database. **Type: IAAS**
## Features
- Very High Availability
- Scales Horizontally for read and writes
- Multi Regional configuration
## Create Instance
[On your console > Spanner > Create Instance](https://console.cloud.google.com/spanner/instances/new)  
- Specify name
- Allocate nodes
## Create Database
[On your console > Spanner > Your Instance > Create Database](https://console.cloud.google.com/spanner/instances)  
- Specify Name
- Define Schema: SQL statement
## Create Table
[On your console > Spanner > Your Instance > Your Database > Create Table](https://console.cloud.google.com/spanner/instances)  
- Define Schema: SQL statement
## Query
[On your console > Spanner > Your Instance > Your Database > Query](https://console.cloud.google.com/spanner/instances)  
- Define your query: SQL statement
## Monitoring
All data for monitoring your instance.
## Query Stats
Top queries based on Cpu
## BackUps
[On your console > Spanner > Your Instance > Your Database > Create Backup](https://console.cloud.google.com/spanner/instances)  
- You can create a backup of your instance
- restore a backup
- Setup automated backups
## Price
**Cloud Spanner** pricing is based on the following components:
- number of **Nodes**
- Storage
- Storage for backup
- Network used  
[Full Documentation](https://cloud.google.com/spanner/pricing)
## CLI
Create Instance: `gcloud spanner instances create my-instance-id  --config=regional-us-east1  --description=my-instance-display-name --nodes=3`  
List Instance: `gcloud spanner instances list`  
Create Database: `gcloud spanner databases create testdb --instance=my-instance-id`  
List Database: `gcloud spanner databases list --instance=my-instance-id`  
Exec SQL Query: `gcloud spanner databases execute-sql example-database  --instance=example-instance  --sql='SELECT * FROM MyTable WHERE MyKey = 1'`  
[Full Documentation](https://cloud.google.com/sdk/gcloud/reference/spanner)