
# ARM Templates to deploy Application Gateway v2 for L7 Load balancing to existing VMSS

This ARM Template deploys the following architecture to Azure. 

- Deploy to Availability Zones

- Deploy to an existing Subnet & VNet

- Add Basic Listener, multiple Front End IP Configurations on different ports
Note: Basic listener is used here where the Front End IP Configuration uses common Public IP and different ports, one per listener. Multi-Site Listener would be used when it is not ok to expose non-standard ports. The URL has to be accessed on a standard 80/443 port. Multiple domains can be defined in Multi-Site Listener configuration, all on standard ports 80/443. 

- Add Basic Routing and URL based routing

- Add custom probes on the Back End Pools

## Virtual Machine Scale Set (Linux) Deployment to a new VNet

Refer to Template file AppGateway_vmss_v2.json

<img src="../images/appgateway.PNG" alt="drawing" height="500px">

> [!NOTE]
> The Template does not cover adding the existing VMSS to a Back End pool of the App Gateway being deployed through this template. CLI or PowerShell or Azure Portal could be used for that. This Template also does not cover deploying the Web Applications to the VMSS
