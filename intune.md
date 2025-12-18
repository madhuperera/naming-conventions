# Intune Naming Conventions

Naming conventions for Microsoft Intune resources.

## 📋 Table of Contents

- [Apple Business Manager](#apple-business-manager)
  - [Enrollment Tokens](#enrollment-tokens)
  - [Enrollment Profiles](#enrollment-profiles)
  - [VPP Tokens](#vpp-tokens)

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

[Back to Main Documentation](README.md)
