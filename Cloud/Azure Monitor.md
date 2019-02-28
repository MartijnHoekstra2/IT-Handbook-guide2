* [Azure status](https://azure.microsoft.com/en-us/status/#)
* Create your own Dashboard by selecting Service Health at the creation of a new dashboard. Make it personal
* Visual Studio and install the Azure Software Developtment Kit, or SDK.
* Visual Studio 2015 Community Edition is free software
  * New > Project, select Cloud and choose ASP.NET Web Application (.NET Framework)
  * Select Add Application Insight to project Optimize perfromance and monitor usage in your live application

* First Tier: Resource health
  * Looking at individual resource health. How to enable diagnostic streams, and how to go in and on a per-resource basis
* Second tier: Monitor center
* Third tier: Log Analytics and operations Management Suite (OMS)


* [Analyze log data in Azure Monitor](https://docs.microsoft.com/en-us/azure/azure-monitor/log-query/log-query-overview)









## Azure Monitor Components Overview
#### Monitoring Data Types
* Metrics
  * Numerical values (e.g. application response time
* Logs
  * Rich records of event (e.g. errors, traces)

#### Azure Monitor Data Sources
* Application monitoring data
  * Your code
* Guest OS monitoring data
  * CPU usage, memory usage, etc...
* Azure resource monitoring data
  * CosmosDB available storage, etc.
* Azure subscription monitoring data
  * Cost to data, Azure service health
  
#### Analyze
* Metrics Explorer
* Log Analytics

#### Insights
* Application Inisghts
  * Application Insights specializes in monitoring web applications from availability to performance and usage. It relies on metrics and Log Analytics to provide deep insights into your application and can help diagnose errors without waiting for a user to report them.
* Container Insights
  * As the name indicates, this is a feature designed to monitor the performance of applications running on Azure Kubernetes Service. With this feature, you will get visibility and memory and processor metrics for your controllers, nodes, and container running on AKS. Container logs will also be collected to give you a full picture of your application's performance.
* VM insights
  * will help you analyze the performance and health of your VMs, regardless of the operating system they are running. What is really cool is that you will even get the visibility on the performance of individual processes and their dependencies.
  
#### Visualize
* Azure Dashboard
  * Lets you create your own custom dashboard combining metrics and logs. This is extremely useful, as you could build a dashboard representing the full health and performance of an application, using graphs for metrics, tables of activity logs, user charts from Applications Insights, or the output of a query from Log Analytics. And of course, you can then share your dashboard with your team so everyone can benefit from it.
* Log Views
  * As part of the Azure Log Analytics service, you can also create custom views to help you visualize your Log Analytics data. This is typically used to summarize data from log records by using a combination of charts and lists of critical data. Once you create custom views, you will be able to add them to your Azure Dashboards as well to get comprehensive insights of your application's performance. 
* PowerBI
  * Although it is not really part of Azure Monitor, Power BI can be extremely useful to visualize monitoring data. In case you're not familiar with Power BI, it is a business analytics service specializing in providing interactive visualizations for a wide range of data sources. Azure Monitor is one of these sources, and Power BI can be configured to automatically import log data from Azure Monitor. This is a really nice alternative to Azure Dashboards.

#### Respond
* Alerts
  * You can set up alerts to notify you of potential issues with your application or its infrastructure. This could be as simple as sending an email or a text message to someone or a group of people, but you can also enable more advanced scenarios by using webhooks to have alerts trigger automated corrective actions.
* Autoscale
  *  In a similar way, you can take advantage of Azure autoscale to automatically add resources to handle increases in load on your application when a metric reaches a specific threshold.
  












## Azure Resource Logs
#### Activity Log
* Also called the audit log
* Records operational details
* Who did what, and when, in Azure

#### Diagnostic Log
* Performance Counters
* Event logs (System, Application, Security)
* IIS Logs
* Crash dump data
* Custom error logs


## Azure Monitor Components
* Activity Log
  * But on a much larger scale (Resource Group
* Metrics
  * Plot data points to a custom, shareable Dashboard
* Diagnostics Logs
  * Aggregated data can be analyzed with Power BI
* Alerts
  * Get notified when metrics exceed threshold values
  * Automatic remediation (Azure Automation runbook; webhook)
  


## Information
* You can use Visual Studio or OMS to read log data written to Azure storage
* [Metric Alerts with Dynamic Thresholds in Azure Monitor (Public Preview)](https://docs.microsoft.com/en-us/azure/azure-monitor/platform/alerts-dynamic-thresholds)
* [Supported resources for metric alerts in Azure Monitor](https://docs.microsoft.com/en-us/azure/azure-monitor/platform/alerts-metric-near-real-time)
* https://app.pluralsight.com/library/courses/microsoft-azure-performance-monitoring/table-of-contents
* https://app.pluralsight.com/library/courses/azure-iaas-monitoring-management-getting-started/table-of-contents

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


## (System Center) Operations Manager
* Can deploy on-premises or in Azure Iaas VM
  * Recommend on-premises deployment due to system requirements for management server and supporting SQL database
* Monitor Azure by adding Azure Management Pack
* Monitor IaaS Vms by deploying agents directly on VMs that report back to gateway server or management server

#### Operations Manager Azure Management Pack
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
  
#### Operations Manager Deployment Topologies
* With Site to Site VPN
  * Deploy agents on IaaS Vms in Azure in samen manner that you would with remote site in on-premises deployments
  * Can also perform agentless monitoring (less functionality)
* Without Site to Site VPN Configure Operations Manager gateway server in Azure
  * Monitored servers need
    * Operations Manager Auth certificate
  * Gateway server needs
    * Operations Manager Auth certificate
    * IPsec Certificate


## Application Insights > Is for the Developers and not for IT Operations
* Detect, triage, and diagnose issues in web apps and services
* Detect issues through e-mail and webhook alerts
* Diagnose exceptions and web app performance issues
* Perform root cause analysiswith ad-hoc queries and full-text search
* Live application monitoring


  * HTTP request rates, response times, success rates.
  * Dependency (HTTP & SQL) call rates, response times, success rates.
  * Exception traces from both server and client
  * Diagnostic log traces.
  * Page view counts, user and session counts, browser load times, exceptions.
  * AJAX call rates, response times and success rates.
  * Server performance countes.
  * Custom client and server telemetry.
  * Segmentation by client location, browser version, OS version, server instance, custom dimensions, and more
  * Availability tests





## Global Service Monitor
 * Web app monitoring tool
 * Check performances and run tasks from locations around the world
   * Test availability
   * Simulate logins and transactions
 * Requires System Center Operatiosn Manager 2012 or later
 * Total tests = the number of tests multiplied by the number of locations
   * GSM subscription: Total tests cannot exceed 25 per subscription (10 tests maximum for each location).
   * Minimum interval per tests must be greater than or equal to 5 minutes
   * Global tests timeout: 30 seconds
   * Maximum number of requests per web test: 100
   * Maximum web test file size: 100 kilobytes (KB)

## Log Analytics
* Use Azure Log Analyticss (v2)
* New query language



## Operations Manager Suite
[Operations Management Suite (OMS) Overview](https://azure.microsoft.com/en-us/resources/videos/operations-management-suite-oms-overview/)
* OMS Workspace = Log Analytics workspace (data warehouse)
* Needs to have an agent installed


* OMS has Log Analytics functionality
  * Collects and analyzes log data
  * Works with on-premises and cloud based deployments
* Connect Azure VMs to OMS Log Analytics
  * Azure Portal
  * Azure PowerShell
  * ARM Template

* Resource / Logs
  * Application Insights
    * Availability, Custom Events, Exceptions Requests
  * Automation
    * JobLogs, JobStreams
  * Key Vault
    * AuditEvent
  * Application Gateway
    * ApplicationGatewayAccessLog, ApplicationGatewayPerformanceLog
  * Network Security Group
    * NetworkSecurityGroupEvent, NetworkSecurityGroupRuleCounter
  * Service Fabric
    * ETWEvent, Operational Event, Reliable Actor Event, Reliable Service Event
  * Virtual Machines
    * Linux Syslog, Windows Event, IIS Log, Windows ETWEvent
  * Web Roles / Workes Roles
    * Linux Syslog, Windows Event, IIS Log, Windows ETWEvent
    
* Can read data from Azure storage in the following formats:
  * Azure tables
  * Azure blob
  * EventHub
* Can read data from Azure services that write data using Azure diagnostics logs

* Needs to be placed in a subscription, so each subscription needs an OSM instance
* The pricing tier you select will be the ammount of days the data will be sayed.
  * Standard = 30 days of data
* Offers alerting functionality
* Rules can be create centrally




