# Memorystore
[On Your console > Memorystore](https://console.cloud.google.com/memorystore/redis/instances)  
Reduce latency with scalable, secure, and highly available in-memory service for Redis and Memcached.
## Features
- Choice of engines: Redis or Memcached
- Security
- Fully Managed
## Create Redis Instance
[On Your console > Memorystore > Redis > Create Instance](https://console.cloud.google.com/memorystore/redis/locations/-/instances/new)  
- Specify instance ID
- Tier: Basic(Lower cost. Does not provide high availability.) or Standard(Includes a failover replica in a separate zone for high availability.)
- Location
- Security
- Redis version
## Create Memcached Instance
[On Your console > Memorystore > Memcached > Create Instance](https://console.cloud.google.com/memorystore/memcached/instances)  
- Specify instance ID
- Tier: Basic(Lower cost. Does not provide high availability.) or Standard(Includes a failover replica in a separate zone for high availability.)
- Location
- Nodes  number
- Memory per node
## Pricing
**Memorystore Redis** pricing is based on the following components:
- Service tier
- Provisioned capacity
- Region
[Full Documentation](https://cloud.google.com/memorystore/docs/redis/pricing)
**Memorystore Memcached**  pricing is based on the following components:
- CPU Usage
- Memory per node

[Full Documentation](https://cloud.google.com/memorystore/docs/redis/pricing)
## CLI
Create redis instance: `gcloud redis instances create myinstance --size=2 --region=us-central1 --redis-version=redis_5_0`  
Create Memcached instance: `gcloud memcache instances create myinstance --node-count=3 --node-cpu=4 --node-memory=10GB --region=us-central1`  
[Full Documentation for redis](https://cloud.google.com/memorystore/docs/redis/quickstart-gcloud)  
[Full Documentation for memcached](https://cloud.google.com/memorystore/docs/memcached/quickstart-gcloud)  