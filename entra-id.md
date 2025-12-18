# Entra ID Naming Conventions

Naming conventions for Microsoft Entra ID resources.

## 📋 Table of Contents

- [Security Groups](#security-groups)
  - [Core Naming Convention](#core-naming-convention)
  - [Conditional Access Policy Groups](#conditional-access-policy-groups)
- [Conditional Access Policies](#conditional-access-policies)
  - [CA Policy Naming](#ca-policy-naming)
  - [Sequence Number Ranges](#sequence-number-ranges)
- [Named Locations](#named-locations)

---

## Security Groups

### Core Naming Convention

**Format:** `<Prefix>-<GroupType>-<ObjectType>-<AssignmentType>-<Scope/Purpose>`

**Components:**
- `<Prefix>` - Service/Platform identifier
  - `EID` = Entra ID
  - `EXO` = Exchange Online
  - `SPO` = SharePoint Online
- `<GroupType>` - Type of group
  - `SEC` = Security Group
  - `DL` = Distribution List
- `<ObjectType>` - Type of object
  - `U` = User
  - `D` = Device
- `<AssignmentType>` - Membership type
  - `A` = Assigned (Static)
  - `D` = Dynamic
- `<Scope/Purpose>` - Specific scope and purpose (combination depends on use case)

**Examples:**
```
EID-SEC-U-A-Finance-Admins
EID-SEC-D-D-Windows-Laptops
EXO-DL-U-A-AllEmployees
SPO-SEC-U-A-Marketing-Contributors
```

### Conditional Access Policy Groups

Used for assignments in Conditional Access Policies.

**Format:** `EID-SEC-U-A-CAP-<Sequence Number>-<Include/Exclude>`

**Components:**
- `EID` - Entra ID prefix
- `SEC` - Security
- `U` - User
- `A` - Assignment
- `CAP` - Conditional Access Policy
- `<Sequence Number>` - Links to the CA Policy sequence number (e.g., CL001, CA403)
- `<Include/Exclude>` - Assignment type (Include or Exclude)

**Examples:**
```
EID-SEC-U-A-CAP-CL001-Exclude
EID-SEC-U-A-CAP-CA403-Include
```

---

## Conditional Access Policies

### CA Policy Naming

**Format:** `<SN>-<Cloud App>-<Response>For<Principal>When:<Condition>`

**Components:**
- `<SN>` - Sequence Number (e.g., CA403, CA010)
- `<Cloud App>` - Which Cloud App it applies to
- `<Response>` - Required action/response (e.g., RequireMFA, Block)
- `For` - Connector
- `<Principal>` - Who it applies to
- `When:` - Connector for condition
- `<Condition>` - When it applies

**Example:**
```
CA403-AllApps-RequireMFA-For:B2B.CollaborationGuests-When:AnyNetwork
```

### Sequence Number Ranges

| Range | Scope | Description |
|-------|-------|-------------|
| CA000-CA099 | Global | Global policies applying to all users/apps |
| CA100-CA199 | Admins | Administrator-specific policies |
| CA200-CA299 | Internals | Internal user policies |
| CA300-CA399 | Guests | Guest user policies (B2B, Service Providers) |
| CA800-CA899 | User Groups | Policies scoped to specific user groups |

**Examples:**
```
CA001-AllApps:Block-For:AllUsers-When:UnknownLocations&Algeria
CA102-AllApps:RequireMFA-For:Admins-When:AnyNetwork
CA200-O365:RequireAppProtectionPolicy-For:AllUsers-When:OnMobileDevices
CA300-AllApps:Block-For:UnallowedGuestTypes-When:AnyNetwork
CA301-AllApps:Block-For:B2BCollaborationGuests-When:OutsideOfTrustedCountries
```

---

## Named Locations

**Format:** `<SN>-<Type>-<Action>-<Cloud App>-<Principal>-<Description>`

**Components:**
- `<SN>` - Sequence Number (e.g., CL001)
- `<Type>` - Type indicator (e.g., CN=Country)
- `<Action>` - Action indicator (e.g., B=Block)
- `<Cloud App>` - Which Cloud App (e.g., M365APPS)
- `<Principal>` - Who it applies to (e.g., Global)
- `<Description>` - Description of the location(s)

**Example:**
```
CL001-CN-B-M365APPS-Global-UnknownLocations&Algeria
```

---

## Administrative Units

**Format:** `AU-<MembershipType>-<IsRestricted>-<Description>`

**Components:**
- `AU` - Administrative Unit prefix
- `<MembershipType>` - Type of membership
  - `A` = Assigned (Static)
  - `DU` = Dynamic User
  - `DD` = Dynamic Device
- `<IsRestricted>` - Restriction status
  - `RES` = Restricted
  - `UNRES` = Unrestricted
- `<Description>` - Descriptive name for the admin unit (no specific pattern)

**Examples:**
```
AU-DU-RES-PrivilegedAdminZone
AU-A-UNRES-FinanceDepartment
AU-DD-RES-CorporateDevices
```

---

[Back to Main Documentation](README.md)
