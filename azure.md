# Azure Naming Conventions

Naming conventions for Microsoft Azure resources.

**Reference:** For a comprehensive list of Azure resource abbreviations, see [Microsoft's recommended abbreviations for Azure resource types](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-best-practices/resource-abbreviations).

## 📋 Table of Contents

- [Subscriptions](#subscriptions)
- [Resource Groups](#resource-groups)
- [Budgets](#budgets)

---

## Subscriptions

**Format:** `<Type>-<Role>-<Environment>-SUB-<Sequence>`

**Components:**
- `<Type>` - Subscription type
  - `CSP` = Cloud Service Provider
  - `PAYG` = Pay as you go
  - `MCAE` = Microsoft Customer Agreement Enterprise
  - `NFP` = Not-for-Profit Grant
- `<Role>` - Subscription functional role
  - `PLATFORM` = Shared infrastructure and core services
  - `SECURITY` = Sentinel, Defender integrations, logging/security tooling
  - `DATA` = Analytics, SQL, data services
  - `APP` = Application hosting
  - `SANDBOX` = Testing / temporary
  - `MGMT` = Management tooling / automation / monitoring
- `<Environment>` - Environment identifier
  - `PROD` = Production
  - `DEV` = Development
  - Other environment codes as needed
- `SUB` - Subscription suffix
- `<Sequence>` - Sequence number (01, 02, 03, etc.)

**Examples:**
```
MCAE-PLATFORM-PROD-SUB-01
MCAE-SECURITY-PROD-SUB-02
NFP-SANDBOX-DEV-SUB-01
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

## Budgets

**Format:** `B-<Amount><Currency>_R-<ResetPeriod>_Exp-<ExpirationDate>_<Sequence>`

**Components:**
- `B` - Budget prefix
- `<Amount>` - Budget threshold amount (numeric value)
- `<Currency>` - Currency code
  - `NZD` = New Zealand Dollar
  - `USD` = US Dollar
  - `AUD` = Australian Dollar
  - Other currency codes as needed
- `R` - Reset period indicator
- `<ResetPeriod>` - Reset/evaluation period frequency
  - `M` = Monthly
  - `Q` = Quarterly
  - `A` = Annually
- `Exp` - Expiration indicator
- `<ExpirationDate>` - Budget expiration date in YYYY-MM-DD format
- `<Sequence>` - Two-digit sequence number (01, 02, 03, etc.)

**Examples:**
```
B-100NZD_R-M_Exp-2029-01-31_01
B-500USD_R-Q_Exp-2026-12-31_01
B-1000AUD_R-A_Exp-2027-06-30_02
```

---

[Back to Main Documentation](README.md)
