# Azure - DR Failover Strategies

## 1.0 - Problem statement

## 2.0 - Objective

## 3.0 - Architecting for Disaster Recovery

- ```Active-Active (highest):``` Deploy to two active regions and distribute traffic.
- ```Active-Passive (medium):``` Deploy to main region and keep DR region on-standby. Upon disaster failover to secondary region.
- ```Active, Backup and Restore (low):``` Deploy to main region and backup required settings and data. Upon disaster create all the requiresed services in a secondary region and restore the settings and data.

## 4.0 - Using SLAs and resiliency concepts

### 4.1 - Determine your SLA requirements

### 4.2 - Define your RTO & RPO

### 4.3 - Calculate Compound SLA

- Don't forget about SLAs for infrastructure componets (VNEts, Application Gateways, Firewall, etc.).
- What about dependecies to on-prem systems?.
- Offered SLA may not improved with multi-zone deployment and does not guard against a region wide outage.

### 4.4 - Build for resiiency and self-healing

- Resiliency design patterns
- Application resiliency design patterns
  - Circuit breaker, retry back-off, etc.

## 5.0 - Leverage Instrastructure as Code

### 5.1 - IaC Concepts

- Deploy your environments using IaC
  - Leverage technologies such as ARM, Bicep and Terraform
- Don't forget your governance and security settings (RBAC, NSGs, diagnostic settings, log analytics workspaces)

### 5.1 - Dependent services that take a long time to install

- If your architecture depends on services that may take a long time to install, determine if you need to keep these services in a passive state

## 6.0 - DevOps/GitOps

- Deploy your workloads with DevOps pipelines

## 7.0 - Data Replication

- Leverage data replication

## 8.0 - Monitoring

## 9.0 - Reherse your DR failover strategy

- Review, plan, and test your failovers
- Perform a retrospective and incorporate learning from the the rehersal

## 10.0 - DR Strategies

### 10.1 - Active-Active

