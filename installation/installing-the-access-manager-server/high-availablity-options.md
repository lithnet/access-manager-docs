# High availability options

![](../../images/badge-enterprise-edition-rocket.svg) High availability is an [Enterprise edition feature](../../access-manager-editions.md)

Access Manager supports several scenarios for enabling a highly available service.

## Multiple instances behind a load balancer

### Requirements

* If the load balancer 'hides' the real client IP address (eg a 'application/layer 7' load balancer), it must support supplying the client IP address in the X-Forwarded-For header
* A Lithnet Access Manager enterprise edition license
* At least one Windows Server 2012 R2 domain controller in the domain where AMS will be installed
* The [KDS root key](https://docs.microsoft.com/en-us/windows-server/security/group-managed-service-accounts/create-the-key-distribution-services-kds-root-key) in the domain must be enabled
* The same account must be used on all hosts in the farm. A group-managed service account is strongly recommended
* Each host must be running the same version of the Access Manager Service at all times
* An external SQL server, Azure SQL, or Amazon RDS SQL server. Using SQL express is not supported in a high availability scenario

### Load balancer probes/Health checks
#### Web app
If you are load balancing the web app, the load balancer can be configured to make a `HTTP GET` call to the `/health-check` endpoint to determine host availability. A HTTP `200 OK` response indicates the service is healthy. Any other response should be treated as a failure.

#### API
If you are load balancing the API host, you can make a HTTP GET call to the `api/v1.0/health-check` endpoint to determine host availability. A HTTP `200 OK` response indicates the service is healthy. Any other response should be treated as a failure.

## Failover cluster
### Requirements

