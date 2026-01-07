# Microsoft Teams Naming Conventions

Naming conventions for Microsoft Teams resources and configurations.

## 📋 Table of Contents

- [Base Naming Convention](#base-naming-convention)
- [Policy Domain Codes](#policy-domain-codes)

---

## Base Naming Convention

**Format:** `MST-<Environment>-<PolicyDomain>-<Description>-<Sequence>`

**Components:**
- `MST` = Microsoft Teams prefix
- `<Environment>` - Deployment environment
  - `PROD` = Production
  - `TEST` = Test/Development
  - `PILOT` = Pilot/Preview
- `<PolicyDomain>` = Policy type identifier (see [Policy Domain Codes](#policy-domain-codes) below)
- `<Description>` = Descriptive name (brief, meaningful identifier)
- `<Sequence>` = Two-digit sequence number (01, 02, 03, etc.)

**Examples:**
```
MST-PROD-MSG-StandardUsers-01
MST-PILOT-MTG-RecordingEnabled-01
MST-PROD-CALL-InternationalAccess-01
MST-TEST-WKLOC-HybridWorkers-01
```

**💡 Benefits:**
- All production policies group together when sorted alphabetically
- Easy to identify environment at a glance
- Simplifies filtering and reporting

---

## Policy Domain Codes

Common policy types in Microsoft Teams and their abbreviated codes:

| Code | Policy Type | Description |
|------|-------------|-------------|
| `MSG` | Messaging Policy | Chat, editing, deletion, Giphy, memes, stickers |
| `MTG` | Meeting Policy | Recording, transcription, screen sharing, breakout rooms |
| `CALL` | Calling Policy | Call forwarding, delegation, voicemail, simultaneous ring |
| `LIVE` | Live Events Policy | Organize and produce live events |
| `APPSETUP` | App Setup Policy | Pinned apps in Teams app bar |
| `APPPERM` | App Permission Policy | Which apps users can install and use |
| `UPDATE` | Update Policy | Teams client update channel and timing |
| `DIAL` | Dial Plan | Phone number normalization for locations |
| `VROUTE` | Voice Routing Policy | PSTN calling patterns and routes |
| `EMERG` | Emergency Policy | E911/emergency calling configuration |
| `WKLOC` | Work Location Policy | Work location detection and presence |

**💡 Note:** Policy domain codes can be extended as new Teams policy types are introduced.

---

## Additional Resources

- [Microsoft Teams Admin Documentation](https://learn.microsoft.com/en-us/microsoftteams/)
- [Teams Policy Packages](https://learn.microsoft.com/en-us/microsoftteams/manage-policy-packages)
- [Teams Voice Planning](https://learn.microsoft.com/en-us/microsoftteams/cloud-voice-landing-page)

---

**Last Updated:** January 7, 2026
