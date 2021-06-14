# Cloud Pub Sub
[On Your Console > Pub/Sub](https://console.cloud.google.com/cloudpubsub/topic/list)  
Reliable, scalable, fully-managed asynchronous messaging service
## Features
- Support push and pull message deliveries
- Backbone for Highly Available and Highly Scalable 
- Low Cost
## Topic
[On Your Console > Pub/Sub > Topic](https://console.cloud.google.com/cloudpubsub/topic/list) 
### Create Topic
[On Your Console > Pub/Sub > Topic > Create Topic](https://console.cloud.google.com/cloudpubsub/topic/list)
- Specify id
## Subscription
[On Your Console > Pub/Sub > Subscription](https://console.cloud.google.com/cloudpubsub/subscription/list)
### Create Subscription
[On Your Console > Pub/Sub > Subscription > Create Subscription](https://console.cloud.google.com/cloudpubsub/subscription/create)  
- Specify id
- Delivery Mode: pull(Subscribers must request delivery) or push (Pub/Sub delivers messages as soon as they are published)
- Message Retention duration: (From 10 minutes to X days)
- Expiration period
## Price
**Cloud Pub Sub** pricing is based on the following components:
- Storage  

[Full Documentation](https://cloud.google.com/pubsub/pricing)
## CLI
Create Topic: `gcloud pubsub topics create my-topic`  
Create Subscription: `gcloud pubsub subscriptions create my-sub --topic=my-topic`  
Publish messages: `gcloud pubsub topics publish my-topic --message="hello"`  
Pull messages: `gcloud pubsub subscriptions pull my-sub --auto-ack`  
[Full Documentation](https://cloud.google.com/pubsub/docs/quickstart-cli)
