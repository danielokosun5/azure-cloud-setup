# Azure Cloud Setup – Summary Report
**Name:** Daniel Okosun  
**Project:** Foundational Azure Cloud Environment Setup  
**Date:** May 2026

---

## 1. Region Selected

**Region:** South Africa North (Johannesburg)

### Why this region was chosen
South Africa North was selected as the primary region for all resources 
because it is the closest Azure region to Nigeria geographically. This 
means:
- Lower network latency for users based in West Africa
- Faster response times when accessing deployed resources
- Compliance with data residency preferences for African workloads

A latency test was conducted using azurespeedtest.azurewebsites.net which 
confirmed South Africa North as the fastest responding region from my 
network location in Nigeria.

### Availability Zones
South Africa North supports multiple availability zones (Zone 1, 2, 3), 
which provides redundancy and high availability for production workloads.

---

## 2. Resource Deployed

**Resource type:** Storage Account (PaaS)  
**Resource name:** devopslearningstorage01  
**Resource Group:** devops-learning-rg  
**Redundancy:** Locally Redundant Storage (LRS)

---

## 3. Shared Responsibility Model

The Shared Responsibility Model defines what Microsoft is responsible for 
versus what the customer (me) is responsible for when using Azure services.

For a **Storage Account (PaaS)**, responsibilities are divided as follows:

### Microsoft is responsible for:
- Physical datacentre security and hardware
- Network infrastructure and cooling
- Host operating system and hypervisor
- Storage service availability and uptime
- Platform-level encryption at rest

### I (the customer) am responsible for:
- Managing access keys and rotating them regularly
- Configuring firewall and virtual network rules
- Setting correct IAM/RBAC permissions (who can access the storage)
- Deciding what data is stored and classifying it appropriately
- Enabling soft delete and versioning for data protection
- Monitoring access logs for suspicious activity

### Key Takeaway
Because this is a PaaS service, Microsoft handles more of the 
infrastructure stack compared to IaaS (like a Virtual Machine), where 
the customer must also manage the operating system and runtime. This 
makes PaaS faster to deploy and easier to secure at the infrastructure 
level, but the customer must still take responsibility for data access 
and identity management.

---

## 4. Cost Management

A budget alert named **free-tier-guard** was created in the Cost 
Management section with a threshold of $1 USD per month. An email alert 
was configured to notify when spending reaches 90% of the budget. This 
ensures the account stays within Free Tier limits.

---

## 5. Screenshots Index

All screenshots are available in the `/screenshots/` folder of this 
repository:

1. `azure-portal-dashboard.png` – Azure Portal dashboard showing active subscription
2. `resource-group.png` – devops-learning-rg Resource Group overview
3. `storage-account.png` – devopslearningstorage01 Storage Account overview
4. `cost-management.png` – Cost Analysis and Budget configuration
