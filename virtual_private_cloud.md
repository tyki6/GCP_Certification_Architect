# Google Cloud VPC
[On your Console > VPC network](https://console.cloud.google.com/networking/networks/list)  
Your own isolated network in GCP, VPC is a global resource & contains subnets in one or more region
## Subnet Mode
- Auto mode VPC: subnet are automatically created in each region
- Custom mode: No subnet created automatically, you have complete control over subnets and their ip (Recommended for Production)
## Create VPC Network
[On your Console > VPC Network > Create VPC network](https://console.cloud.google.com/networking/networks/add)  
- specify name
- Subnet Mode
## Create Subnet
- Specify name
- Specify Region
- Specify IP range (cidr blocks)
- Enable Private Google Access: allow VM to connect to Google API using private IP's
- Enable FlowLogs: To troubleshoot any vpc related to network issues

## External IP Addresses
[On your Console > VPC network > External IP Addresses](https://console.cloud.google.com/networking/addresses/list)
Reserve static ip address
### Reserve Static Address
[On your Console > VPC network > External IP Addresses > Reserve Static Address](https://console.cloud.google.com/networking/addresses/add)
- specify name
- Network Service Tier
- Ip version
- Type
## Firewall
[On your Console > VPC network > External IP Addresses](https://console.cloud.google.com/networking/firewalls/list)
Configure firewall Rules to control traffic going in or out of the network
Along with each rule, you can also define:
- Priority
- Action: Deny or Allow
- Protocol
- Port
### Ingress Rules
Incoming traffic from outside to GCP Targets
- Target(defines the destination): all instance with tag
- Source(defines where the traffic is coming from): cidr
### Egress Rules
Outgoing traffic to destination from GCP targets
- Target (define the source): All instances with tag
- Destination: CIDR block

### Create Firewall Rules
[On your Console > VPC network > Firewall > Create Firewall rule](https://console.cloud.google.com/networking/firewalls/add)

## Routes
## VPC Peering
[On your Console > VPC network > VPC Peering](https://console.cloud.google.com/networking/peering/list)  
Connect VPC networks across different organizations
### Create Peering Connection
[On your Console > VPC network > VPC Peering > Create Peering Connection](https://console.cloud.google.com/networking/peering/add)
- Specify Name
- Specify Your network
- Specify Peered VPC network
## Shared VPC
[On your Console > VPC network > Shared VPC](https://console.cloud.google.com/networking/xpn/details)  
Shared VPC allows an organization to connect resources from multiple projects to a common Virtual Private Cloud (VPC) network
[Documentation](https://cloud.google.com/vpc/docs/shared-vpc)
## Serverless VPC access
[On your Console > VPC network > Serverless VPC access](https://console.cloud.google.com/networking/networks/list)  
Serverless VPC Access allows Cloud Functions, Cloud Run (fully managed) services and App Engine standard environment apps to access resources in a VPC network using those resources’ private IPs
### Create Connector
[On your Console > VPC network > Serverless VPC access > Create Connector](https://console.cloud.google.com/networking/connectors/list)
- Specify Name
- Network
- Subnet
## Packet mirroring
[On your Console > VPC network > Packet minoring](https://console.cloud.google.com/networking/packetmirroring)  
Packet Mirroring aims to provide functionality in cloud, which can mirror a customers regular traffic and fulfill customers need for Advanced Security and Application Performance Monitoring.
### Create Policy
[On your Console > VPC network > Packet minoring > Create Policy](https://console.cloud.google.com/networking/packetmirroring/add)
## Price
**Google Cloud VPC** pricing is based on the following components:
- Ingress Traffic
- Egress traffic
- Network tier

[Full Documentation](https://cloud.google.com/vpc/pricing)
## CLI
[Full Documentation](https://cloud.google.com/sdk/gcloud/reference/compute/shared-vpc)