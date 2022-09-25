# Introduction to Azure Weird Stuff
this is just a brain dump of misc weird behaviour / limitations / known issue that are on Azure.

Last updated 24/9/2022

# Azure Firewall
* No [NSGs available on Azure Firewall](https://learn.microsoft.com/en-us/azure/firewall/firewall-faq#are-network-security-groups--nsgs--supported-on-the-azurefirewallsubnet) so can't do Traffic Analytics on traffic passing through.
* With [forced tunelling](https://learn.microsoft.com/en-us/azure/firewall/forced-tunneling) enabled on Azure Firewall , tracert and Network Watcher will have a next hop of the AzureFirewallManagement Subnet.
* Excessive traffic for Managed Disks / UMS 
* CPU Metrics are not available for Azure Firewall. If there are suspected performance problems with it, a support call will need to raised with Microsoft. Excessive number of rule combinations can cause high CPU.
* Disabling IDPS reduces CPU load on Azure Firewall by about 30%
* If you have more than 1 policy attached to a Policy only 1 can be updated at once. Otherwise will get a message like "faulted referenced firewalls"
* see [FAQ](https://learn.microsoft.com/en-us/azure/firewall/firewall-faq) for more.

## IP Groups 
* Sometimes get issue issue with saying IP Groups in use by firewall when not. Currently a known issue and a fix is being worked on. Will require support call to fix.

# Azure Network Files (ANF)
* UDRs can't be used on ANFs, this can be confusing when troubleshooting network issues in an envrionment where UDRs are generally deployed.
* ANFs DO respond to ping / tracert requests.

# Azure Resource Graph 
* When managing Azure Firewall Policy --> Rule Collection Groups -> Rule Collections --> Rules , Rule Collection Groups dont appear to be available in Resource Graph (23/9/2022 - Case open with Microsoft)


