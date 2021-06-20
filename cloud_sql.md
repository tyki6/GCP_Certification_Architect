# Cloud SQL
[On Your Console > SQL](https://console.cloud.google.com/sql/instances)  
Fully Managed Relational DataBase service.**Type: SAAS**(**Recommended** for migrate local Mysql, PostreSQL, Sql Server)
## Features
- Automatic encryption
- High Availability
- Read Replicas
- Automatics storage increase
- Backups (automated or on-demand)
## Supports
- MySQL
- PostreSQL
- SQL Server
## Create Instance
[On Your Console > SQL > Create Instance](https://console.cloud.google.com/sql/choose-instance-engine)  
- Choose your db engine
- Specify name
- Specify password (Don't forget to remember your password for connecting to your instance)
## Connections
Choose a network path for connecting to this instance. For extra security, consider using the Cloud SQL proxy:
- **Private** or **public** IP
- Add ssl certificate.
## Databases
[On Your Console > SQL > Your Instance > Databases](https://console.cloud.google.com/sql/instances)  
- You can create A Database
- You can manage existing database
## BackUps
[On Your Console > SQL > Your Instance > BackUps](https://console.cloud.google.com/sql/instances)  
- You can create a backup of your instance
- restore a backup
- Setup automated backups
## Replicas
[On Your Console > SQL > Your Instance > Replicas](https://console.cloud.google.com/sql/instances)  
You can create read replicas from any primary instance to replicate your data.
## Cloud proxy
For Connect your SQL instance to your app in [app engine](app_engine.md), [GKE](kubernetes_engine.md), etc...Use [Cloud Proxy](https://cloud.google.com/sql/docs/mysql/sql-proxy)
## Price
**Cloud SQL** pricing is based on the following components:
- CPU
- Memory
- Storage  
[Full Documentation](https://cloud.google.com/sql/pricing)
## CLI
Connect to your instance: `gcloud sql connect my-instance --user=root --quiet`  
Create Backup: `gcloud sql backups create --instance=my-instance`  
Restore Backup: `gcloud sql backups restore my-backup`  
Create Database: `gcloud sql databases create my-db --instance=my-instance`  
Import SQL: `gcloud sql import sql my-instance  my-file.sql.gz --database=testdb`  
[Full Documentation](https://cloud.google.com/sdk/gcloud/reference/sql)