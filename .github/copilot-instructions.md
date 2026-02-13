# Project Guidelines

## Code Style
- This repository is workshop-content first: prefer concise, task-oriented markdown over long narrative prose.
- Follow `.github/instructions/markdown.instructions.md`: ordered heading levels, readable line length, relative links, and labeled code fences.
- Mirror challenge/doc patterns from `challenges/challenge-2-appliance.md`, `challenges/challenge-4-execute.md`, and `challenges/challenge-6-optimize.md`.
- For PowerShell, follow safe and explicit patterns in `scripts/*.ps1` and `.github/instructions/powershell.instructions.md`.

## Architecture
- Workshop flow is linear: `README.md` + `AGENDA.md` define canonical timing; `challenges/` is the execution sequence (0 -> 7).
- Audience boundaries are strict: `participant/` is learner-facing; `facilitator/` is confidential coaching/scoring content.
- `scripts/` contains facilitator automation (scoring, leaderboard, cleanup), not participant exercises.

## Build and Test
- There is no traditional app build/test pipeline in this repo.
- Before/after edits, run: `grep -RInE "14:45|15:00|Curveball|Points|Total" README.md AGENDA.md challenges facilitator participant`.
- Use quick inventory check: `find . -name "*.md" -o -name "*.ps1" | wc -l`.
- For script changes (if `pwsh` exists): `pwsh -NoProfile -Command "Get-Help ./scripts/Score-Team.ps1 -Detailed"` and `pwsh -NoProfile -Command "./scripts/Cleanup-Resources.ps1 -Teams @('team1') -WhatIf"`.

## Project Conventions
- Mandatory pre-edit research: confirm workshop intent (`README.md`, `AGENDA.md`), audience split (`participant/`, `facilitator/`), challenge progression, and script impact (`.github/instructions/agent-research-first.instructions.md`).
- Keep timing and scoring consistent across `README.md`, `AGENDA.md`, `challenges/README.md`, and `facilitator/scoring-rubric.md`.
- Do not leak facilitator-only answers/scripts into participant docs.
- Use file editing tools for file changes (no terminal heredocs).

## Integration Points
- External dependencies are Azure workshop resources (not package managers): Azure Migrate, CAF Migrate guidance, and ArcBox ITPro (see `README.md`, `participant/quick-reference-card.md`).
- Facilitator setup integrates Azure portal/CLI/PowerShell workflows (`facilitator/pre-deployment-guide.md`).
- Scripted operations integrate Azure resources and naming conventions via `scripts/Cleanup-Resources.ps1`.

## Security
- Treat `facilitator/` content as confidential; never mirror it into `participant/`.
- For script edits, preserve safe defaults: confirmations for destructive operations, no hardcoded credentials/secrets, and clear human-readable output.
- Prioritize P0/P1 review checks from `.github/instructions/code-review.instructions.md` for security, fairness, and consistency.
