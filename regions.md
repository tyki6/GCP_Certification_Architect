# Regions
## Definition
Specific geographical location to host your resources
## Regions GCP
Google provides 20+ regions around the world (expanding every year)
## Advantages
- High Availability
- Low latency
- Global footprint
- Adhere to government regulation
## Example
- us-west-1
- europe-north1
- asia-south1
# Zones
## Definition
Zone is a subdomain of Region, each Region has three or more zones in GCP.
## Advantages
- Increased availability and fault tolerance within same region
- Each Zone has one or more discrete clusters (distinct physical infrastructure that is housed in a data center)
- ZOnes in a region are connected through low-latency links
## Pattern
(region)-[a-z]{1}, example: europe-north1-a, europe-north1-b etc....