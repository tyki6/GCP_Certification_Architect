# Load Balancing
Distributes user traffic across instances of an application.
## Features
- Health check
- Auto scalling
- Global load balancing with single anycast IP
- High Availability
## Protocols available
- Http(s) (multi-region)
- TCP (multi-region)
- UDP (single region)
## Create Load Balancer
In Network service > Load Balancer
- Specify Your protocol
- Specify If it's internal load Balancer or External Balancer. Internal balancer use HTTP/TCP protocol.External balancer use HTTPs/TLS protocol    
- Specify Name
- Backend Configuration: Group of endpoints that receive traffic from gcp Load Balancer(your vm for example.) 
- Specify Host and path rules like which path redirect to which backend etc...
- Specify Front configuration (port, protocol, ssl  etc...)
Creation take a time around 10 minutes. Don't worry


