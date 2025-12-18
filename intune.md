# Intune Naming Conventions

Naming conventions for Microsoft Intune resources.

## 📋 Table of Contents

- [Apple Business Manager](#apple-business-manager)
  - [Enrollment Tokens](#enrollment-tokens)
  - [Enrollment Profiles](#enrollment-profiles)
  - [VPP Tokens](#vpp-tokens)
- [Configuration Policies](#configuration-policies)
  - [Policy Types](#policy-types)
  - [Microsoft Defender for Endpoint (MDE)](#microsoft-defender-for-endpoint-mde)
  - [Baseline Policies](#baseline-policies)
- [Device Filters](#device-filters)

---

## Apple Business Manager

### Enrollment Tokens

**Format:** `<Platform>-ADE-<Manager>-Intune`

**Components:**
- `<Platform>` - Device platform
  - `IOS` = iOS/iPadOS devices
  - `MOS` = macOS devices
- `ADE` - Automatic Device Enrollment
- `<Manager>` - Apple manager type
  - `ABM` = Apple Business Manager
  - `ASM` = Apple School Manager
- `Intune` - Target MDM platform

**Examples:**
```
IOS-ADE-ABM-Intune
MOS-ADE-ABM-Intune
IOS-ADE-ASM-Intune
```

**💡 Tips:**
- Name the token when you create it in ABM/ASM
- Use IOS and MOS prefixes if you want to separate tokens by platform

---

### Enrollment Profiles

**Format:** `<Platform>-ENL-<UserAffinity>-<Supervised>-<Description>-<Sequence>`

**Components:**
- `<Platform>` - Device platform
  - `IOS` = iOS/iPadOS devices
  - `MOS` = macOS devices
- `ENL` - Enrollment Profile
- `<UserAffinity>` - User affinity setting
  - `UF` = User Affinity (with user)
  - `NU` = No User Affinity
  - `NF` = No User Affinity (alternate)
- `<Supervised>` - Supervision mode
  - `Supervised` = Device is supervised
  - `NotSupervised` = Device is not supervised
- `<Description>` - Descriptive name (e.g., CompanyDevices, BYOD, Kiosk)
- `<Sequence>` - Two-digit sequence number (01, 02, 03, etc.)

**Examples:**
```
IOS-ENL-UF-Supervised-CompanyDevices-01
IOS-ENL-NU-Supervised-Kiosk-01
MOS-ENL-UF-Supervised-CorporateLaptops-01
IOS-ENL-UF-NotSupervised-BYOD-01
```

---

### VPP Tokens

**Format:** `<Platform>-VPP-<Country>-<Manager>-A:<AutoUpdate>-<Sequence>`

**Components:**
- `<Platform>` - Device platform (static indicator)
  - `IOS` = iOS/iPadOS (used as standard prefix)
- `VPP` - Volume Purchase Program
- `<Country>` - Two-letter country code (e.g., NZ, US, AU, UK)
- `<Manager>` - Apple manager type
  - `ABM` = Apple Business Manager
  - `ASM` = Apple School Manager
- `A:<AutoUpdate>` - Automatic App Updates setting
  - `A:Y` = Automatic updates enabled
  - `A:N` = Automatic updates disabled
- `<Sequence>` - Two-digit sequence number (01, 02, 03, etc.)

**Examples:**
```
IOS-VPP-NZ-ABM-A:N-01
IOS-VPP-US-ABM-A:Y-01
IOS-VPP-AU-ASM-A:N-01
IOS-VPP-UK-ABM-A:Y-02
```

---

## Configuration Policies

### Policy Types

**Format:** `<OSType>-<PolicyType>-<Target>-<Scope/Purpose>-<Sequence>`

**Components:**
- `<OSType>` - Operating system type
  - `WIN` = Windows
  - `IOS` = iOS/iPadOS
  - `AOS` = Android
  - `MOS` = macOS
- `<PolicyType>` - Type of policy
  - `SEC` = Security
  - `PRO` = Profile / Configuration
  - `COM` = Compliance
  - `UPD` = Updates
- `<Target>` - Target scope
  - `D` = Device
  - `U` = User
- `<Scope/Purpose>` - Description of scope and purpose (see special categories below)
- `<Sequence>` - Two-digit sequence number (01, 02, 03, etc.)

**Examples:**
```
WIN-PRO-D-MicrosoftEdgeSettings-01
WIN-PRO-D-OneDriveBaseline-01
WIN-SEC-D-LAPS-01
WIN-COM-D-BitLockerRequired-01
WIN-UPD-D-WindowsUpdates-RingBroad
```

---

### Microsoft Defender for Endpoint (MDE)

For Microsoft Defender for Endpoint policies, use `MDE` prefix in the Scope/Purpose component.

**Format:** `<OSType>-SEC-<Target>-MDE-<Function>-<Sequence>`

**Examples:**
```
WIN-SEC-D-MDE-ASRRules-01
WIN-SEC-D-MDE-AVControls-01
WIN-SEC-D-MDE-AVUpdate-RingBroad
WIN-SEC-D-MDE-DefenderForEndpoint-01
WIN-SEC-D-MDE-FirewallLogging-01
WIN-SEC-D-MDE-Onboarding-01
WIN-SEC-D-MDE-SecurityExperience-01
WIN-SEC-D-MDE-Tag:CloudAutopilot-01
WIN-SEC-D-MDE-Tag:HybridAutopilot-01
WIN-SEC-D-MDE-Tag:HybridJoined-01
```

---

### Baseline Policies

For Security Baseline and other baseline policies, use `Baseline` prefix in the Scope/Purpose component.

**Format:** `<OSType>-SEC-<Target>-Baseline-<Application>-<Sequence>`

**Examples:**
```
WIN-SEC-D-Baseline-M365Apps-01
WIN-SEC-D-Baseline-MSEdge-01
WIN-SEC-D-Baseline-WindowsMDM-01
WIN-SEC-D-Baseline-Windows-01
```

---

## Device Filters

**Format:** `DF-<OSType>-<FilterType>-<Description>`

**Components:**
- `DF` - Device Filter prefix
- `<OSType>` - Operating system type
  - `WIN` = Windows
  - `IOS` = iOS/iPadOS
  - `AOS` = Android
  - `MOS` = macOS
- `<FilterType>` - Type of filter
  - `D` = Managed Device
  - `U` = Managed App
- `<Description>` - Descriptive name for the filter

**Examples:**
```
DF-IOS-D-AllCompanyOwnedDevices
DF-WIN-D-CorporateLaptops
DF-AOS-U-ManagedApps
DF-MOS-D-ExecutiveDevices
```

---

[Back to Main Documentation](README.md)
