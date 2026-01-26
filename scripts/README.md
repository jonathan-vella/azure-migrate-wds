# Workshop Scripts

PowerShell scripts for workshop automation.

---

## Contents

| Script | Purpose | When to Use |
|--------|---------|-------------|
| [Score-Team.ps1](Score-Team.ps1) | Helper for scoring teams | During workshop |
| [Get-Leaderboard.ps1](Get-Leaderboard.ps1) | Display team rankings | During workshop |
| [Cleanup-Resources.ps1](Cleanup-Resources.ps1) | Delete all workshop resources | After workshop |

---

## Quick Start

### During Workshop

```powershell
# Display leaderboard
.\Get-Leaderboard.ps1

# Score a team
.\Score-Team.ps1 -TeamName "team1" -Challenge "C1" -Score 20
```

### After Workshop

```powershell
# Cleanup all resources
.\Cleanup-Resources.ps1 -Teams @("team1", "team2", "team3") -Confirm
```

---

## Notes

- All scripts require appropriate Azure permissions
- Test scripts in a non-production environment first
- Modify parameters as needed for your environment
