## Operations Management Suite (OMS)
[Operations Management Suite (OMS) Overview](https://azure.microsoft.com/en-us/resources/videos/operations-management-suite-oms-overview/)
* Can deploy on-premises or in Azure Iaas VM
  * Recommend on-premises deployment due to system requirements for management server and supporting SQL database
* Monitor Azure by adding Azure Management Pack
* Monitor IaaS Vms by deploying agents directly on VMs that report back to gateway server or management server

### Operations Manager Azure Management Pack
* Discovery only
  * Application Insights
  * Automation
  * Backup
  * BizTalk
  * Logic App
  * Media Services
  * Networks
  * Notifications Hubs
  * Operational Insights
  * Scheduler
  * Search
  * Service Bus
  * Traffic Manager
* Discovers and provides performance counters
  * Cloud Service (web and worker roles)
  * Data Factory
  * DocumentDB
  * Mobile Services
  * Redis Cache
  * Virtual machines
  * Websites

## Azure Monitoring for Iaas VMs
[Azure Virtual Machine Agent overview](https://docs.microsoft.com/en-us/azure/virtual-machines/extensions/agent-windows)

#### Diagnostics
* Ensure that VM agent is installed
* Enable monitoring, and the following will be monitored:
  * Basic metric
  * Network and web metrics
  * .Net metrics
  * Windows event system logs
  * Windows event security logs
  * Windows event application logs
  * Diagnostic infrastructre logs
  * IIS logs

This will put this information in a storage account and access that information through the console. You can see if the agent is installed by verifying this at the Diagnostics settings. This will also be the place where you can find the information back from the above named monitoring options.

#### Alerts Rules
* Configure for a specific target think of Memory,CPU,Network
* You can configure a Runbook


