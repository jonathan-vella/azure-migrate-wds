## Plan: Full Docs Refresh + Folder Reorg

This plan uses the docs-writer skill guardrails to perform a full documentation refresh, validate content against Microsoft Learn + Azure Jumpstart sources, and reorganize workshop docs into a deeper structure while keeping root entrypoints stable. The approach is phased to avoid broken links and to preserve audience separation between participant and facilitator content. Root canonical files remain in place for compatibility, while challenge/audience docs move under a new docs tree with temporary compatibility stubs until link integrity is fully verified.

**Steps**
1. Establish baseline and freeze canonical anchors in [README.md](README.md), [AGENDA.md](AGENDA.md), and [feedback-form.md](feedback-form.md); keep these files at root.
2. Create target structure under [docs/workshop/README.md](docs/workshop/README.md), [docs/challenges/README.md](docs/challenges/README.md), [docs/audiences/participant/README.md](docs/audiences/participant/README.md), [docs/audiences/facilitator/README.md](docs/audiences/facilitator/README.md), and [docs/operations/scripts/README.md](docs/operations/scripts/README.md).
3. Move/rename challenge docs from [challenges/challenge-0-azure-101.md](challenges/challenge-0-azure-101.md) … [challenges/challenge-7-presentation.md](challenges/challenge-7-presentation.md) into numbered files under [docs/challenges/README.md](docs/challenges/README.md) (00–07 naming).
4. Move participant docs from [participant/README.md](participant/README.md) set into [docs/audiences/participant/README.md](docs/audiences/participant/README.md); preserve learner-facing tone and no facilitator leakage.
5. Move facilitator docs from [facilitator/README.md](facilitator/README.md) set into [docs/audiences/facilitator/README.md](docs/audiences/facilitator/README.md); keep confidentiality labels and scoring guidance intact.
6. Mirror script documentation from [scripts/README.md](scripts/README.md) into [docs/operations/scripts/README.md](docs/operations/scripts/README.md); do not move script files in [scripts/Cleanup-Resources.ps1](scripts/Cleanup-Resources.ps1), [scripts/Get-Leaderboard.ps1](scripts/Get-Leaderboard.ps1), [scripts/Score-Team.ps1](scripts/Score-Team.ps1).
7. Run docs-writer consistency pass across timing/scoring anchors in [README.md](README.md), [AGENDA.md](AGENDA.md), [docs/challenges/README.md](docs/challenges/README.md), and facilitator scoring content in [facilitator/scoring-rubric.md](facilitator/scoring-rubric.md) (or its relocated equivalent).
8. Perform online-source refresh using direct canonical URLs only: update CAF/Azure Migrate/ArcBox references in overview, participant pre-work, and facilitator setup docs; standardize Jumpstart links to jumpstart.azure.com and Learn links to learn.microsoft.com.
9. Update all internal links from root hubs first, then challenge chain, then cross-audience references; add temporary compatibility stubs at old paths (challenges/participant/facilitator) that point to new docs paths.
10. Remove legacy duplicated docs only after zero broken links and full consistency checks pass; finalize structure map in root navigation sections.

**Verification**
- Content inventory baseline and post-change:  
  find . -name "*.md" -o -name "*.ps1" | wc -l
- New structure presence:  
  find docs -type f -name "*.md" | sort
- Timing/scoring consistency sweep:  
  grep -RInE "14:45|15:00|Curveball|Points|Total" README.md AGENDA.md challenges facilitator participant docs
- Internal link migration sweep:  
  grep -RInE "\]\((\.\./|\.?/)?(docs/|challenges/|participant/|facilitator/|AGENDA\.md|feedback-form\.md)" README.md AGENDA.md challenges facilitator participant docs
- Legacy-path residue check before cleanup:  
  grep -RInE "challenges/|participant/|facilitator/" README.md AGENDA.md docs | grep -v ".github/"

**Decisions**
- Scope: full content refresh.
- Structure: deep docs reorganization.
- External links: direct canonical URLs (no short-link preference).
- Source validation scope: Microsoft Learn (CAF/Azure Migrate) + Azure Jumpstart/ArcBox only.