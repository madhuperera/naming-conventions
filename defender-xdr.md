# Defender XDR Naming Conventions

Naming conventions for Microsoft Defender XDR resources.

## 📋 Table of Contents

- [Quarantine Policies](#quarantine-policies)

---

## Quarantine Policies

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

[Back to Main Documentation](README.md)
