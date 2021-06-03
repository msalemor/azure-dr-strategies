# Azure - DR Failover Strategies

## 1.0 - Problem statement

## 2.0 - Objective

## 3.0 - Architecting for Disaster Recovery

- ```Active-Active (highest):``` Deploy to two ore more active regions and distribute traffic among them.
- ```Active-Passive (medium):``` Deploy to main region and keep DR region on-standby. Upon disaster failover to secondary region.
- ```Active, Backup and Restore (low):``` Deploy to main region and backup required settings and data. Upon disaster create all the requiresed services in a secondary region and restore the settings and data.

> **Note:** Ranked from highest availability to lowest

## 4.0 - Using SLAs and resiliency concepts

### 4.1 - Determine your SLA requirements

- This is an important decision, is the solution critical and needs to be available 24/7 or is it a non-critical system that could be down for a number of hours with causing any impact?

### 4.2 - Define your RTO & RPO

### 4.3 - Calculate Compound SLA

- Understand how to calculate a compoud SLA
  - https://megamorf.gitlab.io/cheat-sheets/calculate-compound-availability/
- Account for infrastructure componets (VNEts, Application Gateways, Firewall, etc.).
- Account for on-prem dependencies?
- Offered SLA may not improved with multi-zone deployment, and does not guard against a region wide outage.

### 4.4 - Build for resiliency and self-healing

- Perform a failure mode anlysis
  - https://docs.microsoft.com/en-us/azure/architecture/resiliency/failure-mode-analysis
- Leverage resilient design patterns
- Leverage resilient application design patterns
  - https://docs.microsoft.com/en-us/dotnet/architecture/cloud-native/application-resiliency-patterns
- If possible, build for loose coupling and eventual consitency

Reference:
- https://github.com/Azure/fta-cloudarchitecture/blob/master/docs/reliability.md

## 5.0 - Leverage Instrastructure as Code

### 5.1 - IaC Concepts

- Deploy your environments using IaC
  - Leverage technologies such as ARM, Bicep and Terraform
- Don't forget to deploy your governance and security settings (RBAC, NSGs, diagnostic settings, log analytics workspaces)

### 5.1 - Dependent services that take a long time to install

- If your architecture depends on services that may take a long time to install, determine if you need to keep these services in a passive state
- Some services include:
  - API Management
  - Large AKS clusters
  - Application Gateway
  - VPN Gateway

## 6.0 - DevOps/GitOps

- Deploy your workloads with DevOps CI/CD pipelines
- Consider adding a failover stage to the pipelines where the services are provisioned and the applications deployed

## 7.0 - Data Replication

- Leverage data replication
- Leverage a write region closer to the users
- Consider globally distributed services (CosmosDB)

## 8.0 - Monitoring

- Enable monitoring and alerting capabilities to determine that a failover is required

## 9.0 - Reherse your DR failover strategy

- Review, plan, and test your failovers
- Perform a retrospective and incorporate learning from the the rehersal

## 10.0 - DR Strategies

### 10.1 - Active-Active

