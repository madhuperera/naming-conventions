# Defender XDR Naming Conventions

Naming conventions for Microsoft Defender XDR resources.

## 📋 Table of Contents

- [Defender for Office 365](#defender-for-office-365)
  - [Quarantine Policies](#quarantine-policies)
- [Defender for Endpoint](#defender-for-endpoint)
  - [Device Groups](#device-groups)

---

## Defender for Office 365

### Quarantine Policies

**Format:** `QP-RA:<ReleaseAction>-A:<Actions>-N:<Notifications>`

**Components:**
- `QP` - Quarantine Policy prefix
- `RA` - Release Action
  - `RR` = Request Release
  - `RA` = Release Allow
- `A` - Actions (available user actions)
  - `D` = Delete
  - `P` = Preview
  - `B` = Block Sender
  - `A` = Allow Sender
- `N` - Notifications
  - `Include` = Notifications included
  - `Exclude` = Notifications excluded
  - `N` = No notifications

**Examples:**
```
QP-RA:RR-A:DPB-N:Exclude
QP-RA:RA-A:DPBA-N:Exclude
QP-RA:RR-A:DPB-N:N
QP-RA:RA-A:DPBO-N:N
QP-RA:RA-A:DPBO-N:Include
```

---

## Defender for Endpoint

### Device Groups

**Format:** `MDE-<Target>-<OSType>-<GroupType>-<MembershipType>-<Purpose>`

**Components:**
- `MDE` - Microsoft Defender for Endpoint prefix
- `<Target>` - Target type
  - `D` = Device
  - `U` = User
- `<OSType>` - Operating system type
  - `WIN` = Windows
  - `IOS` = iOS/iPadOS
  - `AOS` = Android
  - `MOS` = macOS
  - `LIN` = Linux
- `<GroupType>` - Type of group
  - `SEC` = Security
- `<MembershipType>` - Membership type
  - `Dynamic` = Dynamic membership
  - `Assigned` = Static/assigned membership
- `<Purpose>` - Descriptive purpose of the group

**Examples:**
```
MDE-D-WIN-SEC-Dynamic-HybridAutopilot
MDE-D-WIN-SEC-Dynamic-CloudAutopilot
MDE-D-WIN-SEC-Dynamic-HybridJoined
MDE-D-WIN-SEC-Assigned-TestDevices
```

---

[Back to Main Documentation](README.md)
