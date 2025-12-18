# Exchange Online Naming Conventions

Naming conventions for Microsoft Exchange Online resources.

## 📋 Table of Contents

- [Transport Rules](#transport-rules)

---

## Transport Rules

**Format:** `<SequenceNumber>-<Action>-<Direction>-<Target>-<AdditionalInfo>`

**Components:**
- `<SequenceNumber>` - Rule sequence identifier (e.g., TR001, TR002)
  - `TR` = Transport Rule prefix
  - Followed by three-digit number (001, 002, etc.)
- `<Action>` - Action taken by the rule
  - `Quarantine` = Quarantine the message
  - `Block` = Block/Reject the message
  - `Allow` = Allow/Permit the message
  - `Redirect` = Redirect to another recipient
  - `Delete` = Delete the message
- `<Direction>` - Mail flow direction
  - `Inbound` = Incoming mail
  - `Outbound` = Outgoing mail
  - `Internal` = Internal organization mail
- `<Target>` - Target scope or condition
  - Examples: `OnMicrosoft`, `External`, `AllUsers`, `Executives`
- `<AdditionalInfo>` - Optional additional details

**Examples:**
```
TR001-Quarantine-Inbound-OnMicrosoft-SOFT
TR002-Block-Outbound-External-Executable
TR003-Redirect-Inbound-Executive-Legal
TR004-Allow-Inbound-Partner-Whitelist
```

---

[Back to Main Documentation](README.md)
