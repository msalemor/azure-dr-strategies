# Strategies for DR Scenarios

## 1.0 - Problem statement

## 2.0 - Objective

## 3.0 - Architectures

- ```Active-Active (highest):``` Deploy to two active regions and distribute traffic.
- ```Active-Passive (medium):``` Deploy to main region and keep DR region on-standby. Upon disaster failover to secondary region.
- ```Active Backup and Restore (low):``` Deploy to main region and backup required settings and data. Upon disaster create all the requiresed services in a secondary region and restore the settings and data.

## 4.0 - Using SLAs and resiliency concepts

### 4.1 - Define your RTO & RPO

### 4.2 - Calculate Compound SLA

### 4.3 - Build for resiiency and self-healing

### 4.5 - Determine if single region deployment meets required SLA

## 5.0 - Instrastructure as code

### 5.1 - IaC Concepts

- Deploy your environments using IaC
  - Leverage technologies such as ARM, Bicep and Terraform
- Don't forget your governance and security settings (RBAC, NSGs, diagnostic settings, log analytics workspaces)

### 5.1 - Dependent services that take a long time to install

- If your architecture depends on services that may take a long time to install, determine if you need to keep this in a passive state

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

