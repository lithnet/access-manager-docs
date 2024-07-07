# Installing Access Manager behind a load balancer

![](../../images/badge-enterprise-edition-rocket.svg) High availability is an [Enterprise edition feature](../../access-manager-editions.md)

Access Manager is fully supported in load-balanced environments. You can have a load-balanced web app farm, and a separate agent API farm, or a single farm for both.

## Requirements
* If the load balancer 'hides' the real client IP address (e.g. a 'application/layer 7' load balancer), it must support supplying the client IP address in the X-Forwarded-For header
* The load balancer must support load balancing both HTTP and HTTPS. 'SSL offloading' is not supported.
* A Lithnet Access Manager enterprise edition license
* At least one Windows Server 2012 R2 domain controller in the domain where AMS will be installed
* The [KDS root key](https://docs.microsoft.com/en-us/windows-server/security/group-managed-service-accounts/create-the-key-distribution-services-kds-root-key) in the domain must be enabled
* The same account must be used on all hosts in the farm. A group-managed service account is strongly recommended
* Each host must be running the same version of the Access Manager Service at all times
* An external SQL server, Azure SQL, or Amazon RDS SQL server. Using SQL express is not supported in a high availability scenario

## Installation procedure
### 1. Prepare the SQL database
* You cannot use the built-in SQL express database instance when installing AMS for high availability, so you'll need to create your database in advance. This can be on a SQL standard or enterprise edition standalone host, or cluster, or you can deploy the database in an Azure SQL or Amazon RDS instance. See the [SQL installation guide](sql-installation-options.md) for more information.

### 2. Install Access Manager Service on the first node
* On the first node, follow the steps in the [installation guide](installing-the-access-manager-service.md) for configuring AMS features as appropriate for your environment.
* Make sure you provide your Enterprise edition license key, save your configuration, and restart the service before moving onto install subsequent nodes

### 3. Install Access Manager Service on the remaining nodes
* Repeat the installation process for the next node. Make sure to use the same service account, connection string, and TLS certificate on each server. 

{% hint style="info" %}
 Settings on the `Host configuration` page will need to be configured per-node. All other settings are stored centrally in the database. Therefore, you will not need to provide the license key after installing it on the first node.
{% endhint %}

If you want to separate web access from agent API access, you can create multiple individual load balanced farms with different nodes in each. Select the appropriate services on the `Host configuration` page for the role that the specific node will play. Ensure that the `External host name` field matches the name of the load balanced endpoint that either agents or web app users will connect to.

### 4. Configure the IP address detection settings
* If the load balancer 'hides' the real client IP address (e.g. a 'application/layer 7' load balancer), you must configure the IP address detection settings in the app. If you are using a 'transport layer' load balancer, such as Microsoft NLB, you can skip this step.
* From the `App configuration/IP detection` page, select the option to `Resolve client IP address from X-Forwarded-For headers`. 
* If you have multiple load balancers, web application firewalls, or reverse proxies in front of the application, adjust the `Maximum allowed entries in header` to reflect the number of trusted devices that will be contributing to the X-Forwarded-For header value. For example, if your AMS server sits behind a load balancer farm, which sits behind a WAF farm, then enter `2` for this value.
* Provide the IP address, or IP network range that the load balancer appliance (and other WAFs or proxies) sits in. This allows AMS to accurately detect which IP address belongs to the client.
* Test that the configuration is working correctly, by making an access request via the web app. In audit entry that appears in the event log, you should see the correct client IP address, and not the IP address of the load balancer.

### 5. Configure the load balancer
* Configure the load balancer to point to the nodes of the farm.
* If your load balancer provides customizable probes or health checks, see the 'Load balancer probes/Heath check` section below.

## Load balancer probes/Health checks
### Web app
If you are load balancing the web app, the load balancer can be configured to make a `HTTP GET` call to the `/health-check` endpoint to determine host availability. A HTTP `200 OK` response indicates the service is healthy. Any other response should be treated as a failure. Health check requests must be performed over HTTPS.

### API
If you are load balancing the agent API, you can make a HTTP GET call to the `api/v3.0/health-check` endpoint to determine host availability. A HTTP `200 OK` response indicates the service is healthy. Any other response should be treated as a failure. Health check requests must be performed over HTTPS.
