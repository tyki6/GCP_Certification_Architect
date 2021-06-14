# Cloud Storage or Object Storage (GCS)
[On Your console > Cloud Storage](https://console.cloud.google.com/storage/browser)  
Most popular, very flexible & inexpensive **Storage Service**. **Type: SAAS**
## Class of Storage
- **Standard**: Best for short-term storage and frequently accessed data
- **Nearline**: Best for backups and data encrypted less than one a month
- **Coldline**: Vest for disaster recovery and data accessed than once a quarter
- **Archive**: Best for long-term digital preservation of data accessed less than once a year
## Object Versioning
Prevents accidental deletion & provides history:
- Enabled at bucket level (turn on/off at any time)
- **Liver version** is the **latest** version(_if you delete live object, it becomes noncurrent object version, if you delete noncurrent object, it is deleted_)
- **Older versions** are uniquely identified by **object key** + **a generation number**
- Reduce cost by deleting older versions
## LifeCycle: Object Lifecycle Management
[On Your console > Cloud Storage > Your Bucket > LifeCycle > Add Rule](https://console.cloud.google.com/storage/browser)
### Actions
- Deletion: deletion actions
- SetStorageClass: change form one storage class to another*
### Conditions:
- Age
- CreatedBefore
- IsLive
- MatchesStorageClass
- NumberOfNewerVersions
..
## Bucket Lock
[On Your console > Cloud Storage > Your Bucket > Retention > Set Retention](https://console.cloud.google.com/storage/browser)
- Specify time
## ACL (Access Control List)
[On Your console > Cloud Storage > Your Bucket > Permissions](https://console.cloud.google.com/storage/browser)  
- Uniform (Recommended): Uniform Bucket level access using iam
- Fine-grained: Use IAM and ACL to control Access
## Create Bucket
[On Your console > Cloud Storage > Create Bucket](https://console.cloud.google.com/storage/create-bucket)  
- Specify name
- Location type: Region, Dual-Region, Multi Region
- Specify Class
## Price
**Cloud Storage** pricing is based on the following components:
- Data storage: the amount of data stored in your buckets. Storage rates vary depending on the storage class of your data and location of your buckets.
- Network usage: the amount of data read from or moved between your buckets.
- Operations usage: the actions you take in Cloud Storage, such as listing the objects in your buckets.
- Retrieval and early deletion fees: applicable for data stored in the Nearline Storage, Coldline Storage, and Archive Storage classes.  
[Full Documentation](https://cloud.google.com/storage/pricing)
## CLI
Create Bucket: `gsutil mb gs://my_bucket`  
List version: `gsutil ls -a gs://my_bucket`  
Copy objects: `gsutil cp gs://my_bucket gs://my_bucket_2`  
Upload Object: `gsutil cp local/my_local_file gs://my_bucket_2`  
Download Object: `gsutil cp gs://my_bucket local/my_local_file`  
Create signed URL: `gsutil signurl -d 10m YOUR_KEY gs://my_bucket `  
[Full Documentation](https://cloud.google.com/storage/docs/gsutil)