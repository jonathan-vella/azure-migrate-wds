# Challenge 3: Assessment

## Challenge Snapshot

| Field | Value |
|---|---|
| Duration | 45 minutes |
| Type | Hands-on Lab |
| Points | 20 |
| Deliverable | Azure VM and SQL assessment outputs with readiness findings |

## Objective

Analyze discovered workloads and create Azure assessments to understand migration readiness, sizing recommendations, and cost estimates.

---

## The Business Challenge

Now that discovery has run (hopefully over lunch!), Contoso needs answers:

1. **Which workloads are ready for Azure?** — Any blockers?
2. **What Azure resources do we need?** — VM sizes, storage types
3. **How much will it cost?** — Monthly estimates for budgeting
4. **What about the SQL database?** — Can it go to Azure SQL?

Time to turn raw discovery data into actionable insights!

---

## Prerequisites

Before starting this challenge, ensure:

- [ ] Challenge 2 completed — discovery running
- [ ] At least some servers visible in Azure Migrate (check the portal)
- [ ] You have access to the Azure portal

---

## Your Tasks

### Part A: Verify Discovered Servers (5 min)

1. Navigate to **Azure Migrate** → **Servers, databases and web apps**

2. In the **Azure Migrate: Discovery and assessment** tile, note:
   - Number of discovered servers
   - Number of SQL instances discovered
   - Number of web apps discovered

3. Click on the **Discovered servers** count

4. Review the server inventory:

   | Expected Server | OS | Status |
   |-----------------|-----|--------|
   | ArcBox-Win2K22 | Windows Server 2022 | Should show |
   | ArcBox-Win2K25 | Windows Server 2025 | Should show |
   | ArcBox-SQL | Windows + SQL | Should show |
   | ArcBox-Ubuntu-01 | Ubuntu 22.04 | Should show |
   | ArcBox-Ubuntu-02 | Ubuntu 22.04 | Should show |

5. Click on any server to see details:
   - Configuration (cores, memory, disks)
   - Performance data (if available)
   - Dependencies (if enabled)

✅ **Verify**:
- [ ] At least 5 servers discovered
- [ ] Can view server details

---

### Part B: Create Azure VM Assessment (15 min)

1. In Azure Migrate, click **Assess** → **Azure VM**

2. **Assessment settings**:

   | Setting | Recommended Value | Notes |
   |---------|-------------------|-------|
   | Target location | **Sweden Central** | Nearest EU region to Contoso |
   | Storage type | **Automatic** | Let Azure recommend |
   | Savings options | **Pay-as-you-go** | For initial estimate |
   | Sizing criteria | **Performance-based** | Uses collected metrics |
   | Performance history | **1 day** | Workshop timeframe |
   | Percentile utilization | **95th** | Default, handles spikes |
   | Comfort factor | **1.3** | 30% buffer for growth |
   | VM series | Deselect A-series | Exclude burstable |

3. **Select servers to assess**:
   - Click **Edit** next to "Selected servers"
   - Create a new group: `contoso-all-servers`
   - Select all 5 discovered servers
   - Click **Create assessment**

4. **Wait for assessment** (2-5 minutes)

5. **Review assessment results**:
   - Click on the assessment name
   - Note the **Azure readiness** summary
   - Review **Monthly cost estimate**

✅ **Verify**:
- [ ] Assessment created
- [ ] Readiness results visible
- [ ] Cost estimate generated

---

### Part C: Analyze Readiness Results (10 min)

Click into your assessment and explore each section:

#### Readiness Overview

| Status | Meaning | Action |
|--------|---------|--------|
| ✅ Ready for Azure | Can migrate as-is | Proceed |
| ⚠️ Ready with conditions | Minor issues | Review and remediate |
| ❌ Not ready for Azure | Blockers exist | Investigate |
| ❓ Readiness unknown | Insufficient data | Add credentials/wait |

**Document for each server**:

| Server | Readiness | Issues (if any) | Recommended Azure VM |
|--------|-----------|-----------------|---------------------|
| ArcBox-Win2K22 | | | |
| ArcBox-Win2K25 | | | |
| ArcBox-SQL | | | |
| ArcBox-Ubuntu-01 | | | |
| ArcBox-Ubuntu-02 | | | |

#### Cost Breakdown

Review the cost details:
- Compute costs (VM hours)
- Storage costs (disk types)
- Total monthly estimate

**Questions to answer**:
- What's the total monthly cost estimate?
- Which server is the most expensive? Why?
- What disk types are recommended?

#### Confidence Rating

Look at the **confidence rating** (1-5 stars):

| Rating | Meaning |
|--------|---------|
| ⭐⭐⭐⭐⭐ | All data points available |
| ⭐⭐⭐⭐ | Most data available |
| ⭐⭐⭐ | Some data missing |
| ⭐⭐ | Limited data |
| ⭐ | Minimal data |

> 💡 **Tip**: Lower confidence often means discovery hasn't run long enough for performance data

✅ **Verify**:
- [ ] Documented readiness for all servers
- [ ] Noted cost estimate
- [ ] Checked confidence rating

---

### Part D: Create Azure SQL Assessment (15 min)

1. Return to **Azure Migrate** dashboard

2. Click **Assess** → **Azure SQL**

3. **Assessment settings**:

   | Setting | Value |
   |---------|-------|
   | Target deployment type | **Azure SQL MI, SQL DB, and SQL on Azure VM** |
   | Target location | Same region as VM assessment |
   | Compute tier | **General Purpose** |

4. Select the server group or individual SQL server

5. Click **Create assessment**

6. **Review SQL assessment results**:
   - Target readiness (SQL MI vs SQL DB vs SQL VM)
   - Instance details
   - Database compatibility

**Questions to answer**:
- What Azure SQL target is recommended?
- Are there any compatibility issues?
- What's the estimated SQL cost?

✅ **Verify**:
- [ ] SQL assessment created
- [ ] Target recommendation noted
- [ ] Compatibility reviewed

---

## Expected Deliverables

1. Click **Export assessment** to download Excel file

2. Save the file — you'll reference it in later challenges

3. **Key metrics to capture for your team**:
   - Total monthly cost estimate
   - Number of ready vs. not-ready servers
   - Recommended VM sizes
   - Any blockers or warnings

---

## Success Criteria (20 Points)

| Criterion | Points | Verification |
|-----------|--------|--------------|
| VM assessment created | 5 | Assessment visible in portal |
| SQL assessment created | 5 | SQL assessment visible |
| Readiness interpreted correctly | 5 | Can explain status for each server |
| Findings documented | 5 | Exported or captured key metrics |
| **Total** | **20** | |

---

## ⚠️ Watch out

| Issue | Solution |
|-------|----------|
| No servers in assessment | Wait longer for discovery, check appliance status |
| All servers "unknown" readiness | Add server credentials, wait for metadata |
| No performance data | Need more time (hours) for collection |
| SQL not discovered | Verify SQL credentials, check SQL instance is running |
| Cost seems wrong | Check VM series selection, verify region |

- Low-confidence assessments can mislead decisions; validate data quality before finalizing recommendations.
- Ensure SQL discovery credentials are correct before assuming incompatibility.

---

## 💡 Tip

- **Performance data improves over time** — Initial assessments may have lower confidence
- **Review the "Why" not just "What"** — Click into each server to understand recommendations
- **Cost is estimate only** — Actual costs depend on usage, reserved instances, hybrid benefit
- **Compare to your Challenge 1 plan** — Does reality match your assumptions?

---

### What Just Happened?

You created assessments that:

1. **Analyzed server configurations** — CPU, memory, storage
2. **Applied sizing algorithms** — Matched to Azure VM SKUs
3. **Evaluated readiness** — Checked for migration blockers
4. **Estimated costs** — Based on Azure pricing
5. **Provided recommendations** — Right-sized for your workload

This data drives migration decisions!

---

## Reflection Questions

- Did the assessment results match your expectations from Challenge 1?
- What surprised you about the readiness results?
- How would you improve the confidence rating?

---

## Next Step

Bring your assessment findings to [Challenge 4: Execute](04-execute.md) where you'll design the detailed migration strategy.

---

← [Challenge 2: Deploy Appliance](02-appliance.md) | [Challenges Overview](README.md) | [Challenge 4: Execute](04-execute.md) →
