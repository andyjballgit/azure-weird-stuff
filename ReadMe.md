# Introduction 
this is just a brain dump of misc weird behaviour / limitations / known issue that are on Azure.

# Azure Firewall
* No NSG available on Azure Firewall so can't do Traffic Analytics...
* With forced tunelling enabled on Azure traceroutr
* Excessive traffic for Managed Disks / UMS 
* CPU Metrics are not available for 
* Disabling IDPS reduces CPU load on Azure Firewall by about 30%


## IP Groups 
* Sometimes get issue issue with saying IP Groups in use by fireall when not..Will require support call to fix.

# Azure Network Files (ANF)
* UDRs can't be used on ANFs, this can be confusing when troubleshooting network issues.
* ANFs do respomd 

# Azure Resource Graph 
* When managing Azure Firewall Policy --> Rule Collection Groups -> Rule Collections --> Rules , Rule Collection Groups dont appear to be available in Resource Graph (23/9/2022 - Case opent with Microsoft)


