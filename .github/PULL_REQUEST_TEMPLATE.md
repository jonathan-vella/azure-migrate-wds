## Description

<!-- Briefly describe what changed and why it is needed. -->

## Related Issue

<!-- Link the related issue, e.g. "Fixes #123" -->

Fixes #

## Type of Change

<!-- Mark all that apply with an "x" -->

- [ ] 📘 Participant documentation update
- [ ] 🧑‍🏫 Facilitator documentation update
- [ ] 🧩 Challenge flow/content update
- [ ] 🧮 Scoring/rubric update
- [ ] 🛠️ Script update (`scripts/*.ps1`)
- [ ] ⚙️ GitHub instructions/skills/workflow update
- [ ] 🐛 Bug fix

## Affected Areas

<!-- Mark all repository areas touched by this PR -->

- [ ] `README.md` or `AGENDA.md`
- [ ] `challenges/`
- [ ] `participant/`
- [ ] `facilitator/`
- [ ] `scripts/`
- [ ] `.github/instructions/`
- [ ] `.github/skills/`
- [ ] `.github/workflows/`

## Changes Made

<!-- Describe the most important changes and include file paths. -->

**Files added:**

--

- **Files modified:**

-

## Testing Performed

<!-- Describe what you validated for this PR -->

### Documentation Validation (if applicable)

- [ ] Reviewed for participant vs facilitator audience separation
- [ ] Verified challenge sequence and dependencies remain clear
- [ ] Verified timing/points consistency with `README.md`, `AGENDA.md`, and facilitator rubric
- [ ] Verified all added/changed internal links

### Script Validation (if applicable)

- [ ] Ran script in safe mode (`-WhatIf`) where supported
- [ ] Confirmed destructive behavior requires explicit confirmation
- [ ] Verified script output/messages are clear for facilitators

### General Validation

- [ ] No secrets, credentials, tenant IDs, or subscription IDs were added
- [ ] Markdown remains readable and consistent
- [ ] Existing workshop flow is not unintentionally broken

## Consistency Checks

<!-- Required when changing workshop content -->

- [ ] Challenge durations still align with the agenda
- [ ] Points totals still align with scoring rubric and scripts
- [ ] Curveball timing is consistent across participant/facilitator docs
- [ ] Facilitator-only content is not exposed in participant docs

## Pre-Submission Checklist

<!-- Verify all items before requesting review -->

### Documentation & Content Standards

- [ ] Objective/timebox/deliverables are clear in challenge-style docs
- [ ] Terminology remains aligned with CAF Migrate and Azure Migrate
- [ ] Audience separation preserved (`participant/` vs `facilitator/`)

### Script Standards (if applicable)

- [ ] Parameters and usage examples are accurate
- [ ] Safe defaults are preserved
- [ ] Any script behavior change is reflected in `scripts/README.md`

### Repository Hygiene

- [ ] Paths in `.github/instructions` and `.github/skills` reference real files/folders
- [ ] No stale references to old infra-delivery workflows remain
- [ ] CI/workflow checks pass (if applicable)

## Screenshots / Supporting Material

<!-- Add screenshots, whiteboard captures, diagrams, or script output when helpful -->

## Additional Notes

<!-- Add any other context for reviewers -->
