# Azure Naming Conventions

Naming conventions for Microsoft Azure resources.

**Reference:** For a comprehensive list of Azure resource abbreviations, see [Microsoft's recommended abbreviations for Azure resource types](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-best-practices/resource-abbreviations).

## 📋 Table of Contents

- [Subscriptions](#subscriptions)
- [Resource Groups](#resource-groups)

---

## Subscriptions

**Format:** `<Type>-<SID>-<Location>-SUB-<Sequence>`

**Components:**
- `<Type>` - Subscription type
  - `CSP` = Cloud Service Provider
  - `NFP` = Not-for-Profit Grant
- `<SID>` - System ID / Environment
  - `PROD` = Production
  - `DEV` = Development
  - Other system identifiers as needed
- `<Location>` - Azure region
  - `AUEAST` = Australia East
  - `USWEST` = US West
  - `USEAST` = US East
  - Other region codes as needed
- `SUB` - Subscription suffix
- `<Sequence>` - Two-digit sequence number (01, 02, 03, etc.)

**Examples:**
```
CSP-PROD-AUEAST-SUB-01
NFP-DEV-USWEST-SUB-01
CSP-PROD-USEAST-SUB-02
```

---

## Resource Groups

**Format:** `<ResourceType>-<Workload/AppProject>-<Environment>-<Region>-<InstanceNumber>`

**Components:**
- `<ResourceType>` - Type of resource
  - `rg` = Resource Group
  - `vm` = Virtual Machine
  - `st` = Storage Account
  - `app` = Application
  - `log` = Log Analytics Workspace
  - See [Microsoft's resource abbreviations](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-best-practices/resource-abbreviations) for complete list
- `<Workload/AppProject>` - Workload, application, or project name
  - Examples: `navigator`, `sentinel`, `spo`
- `<Environment>` - Environment identifier
  - `prod` = Production
  - `dev` = Development
  - Other environment codes as needed
- `<Region>` - Azure region
  - `aueast` = Australia East
  - `uswest` = US West
  - `useast` = US East
  - Other region codes as needed
- `<InstanceNumber>` - Three-digit instance number (001, 002, 003, etc.)

**Examples:**
```
rg-sentinel-prod-aueast-001
rg-navigator-dev-uswest-001
log-sentinel-prod-aueast-001
```

---

[Back to Main Documentation](README.md)
