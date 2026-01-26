# Challenge 6: Optimize

> **Duration**: 45 minutes | **Type**: Whiteboard Design Session | **Points**: Included in overall scoring

## Objective

Design a cost optimization and governance strategy for your migrated environment, including hybrid management with Azure Arc.

---

## The Business Challenge

Contoso's CFO wants to know:

1. **How much will this cost?** — Monthly and annual projections
2. **How can we save money?** — Reserved Instances, right-sizing, hybrid benefit
3. **What about the servers we can't migrate?** — Hybrid management strategy
4. **How do we govern this?** — Policies, compliance, management groups

The migration will only be approved if the business case is solid!

---

## Prerequisites

Before starting this challenge, ensure:

- [ ] Challenges 3-5 completed
- [ ] Assessment cost estimates available
- [ ] GDPR requirements incorporated (from Challenge 5)

---

## Your Tasks

### Part A: Cost Estimation (15 min)

Build a complete cost picture for Contoso:

#### Direct Migration Costs

| Category | One-Time | Monthly | Annual |
|----------|----------|---------|--------|
| Azure Migrate tooling | $0 | $0 | $0 |
| Data transfer (egress) | Estimate | $0 | — |
| Network connectivity | Setup | Ongoing | Annual |
| **Subtotal** | | | |

#### Running Costs (from Assessment)

| Server | Azure VM Size | Compute/Month | Storage/Month | Total/Month |
|--------|---------------|---------------|---------------|-------------|
| ArcBox-Win2K22 | [from assessment] | $ | $ | $ |
| ArcBox-Win2K25 | [from assessment] | $ | $ | $ |
| ArcBox-SQL | [from assessment] | $ | $ | $ |
| ArcBox-Ubuntu-01 | [from assessment] | $ | $ | $ |
| ArcBox-Ubuntu-02 | [from assessment] | $ | $ | $ |
| **Total IaaS** | | | | $ |

#### Additional Services

| Service | Purpose | Monthly Cost |
|---------|---------|--------------|
| Azure Monitor | Monitoring & alerts | $ |
| Log Analytics | Log storage | $ |
| Backup vault | VM backups | $ |
| Key Vault | Secrets management | $ |
| **Total Platform** | | $ |

**Total Monthly Cloud Spend**: $________

---

### Part B: Cost Optimization Strategies (15 min)

Identify savings opportunities:

#### Azure Hybrid Benefit

If Contoso has Windows Server licenses with Software Assurance:

| Benefit | Savings | Applicable To |
|---------|---------|---------------|
| Azure Hybrid Benefit (Windows) | Up to 40% | Windows VMs |
| Azure Hybrid Benefit (SQL) | Up to 55% | SQL Server |

**Question**: Does Contoso have eligible licenses?

#### Reserved Instances

| Commitment | Discount | Risk |
|------------|----------|------|
| 1-year RI | ~20-30% | Low commitment |
| 3-year RI | ~40-60% | Higher commitment |

**Question**: Which workloads are stable enough for 3-year commitment?

#### Right-Sizing

Review assessment recommendations:

| Server | Assessed Size | Recommended Size | Monthly Savings |
|--------|---------------|------------------|-----------------|
| [Server] | D4s_v5 | D2s_v5 | $ |
| ... | | | |

#### Other Optimizations

| Strategy | Description | Potential Savings |
|----------|-------------|-------------------|
| Auto-shutdown | Dev/test VMs off at night | 50-70% |
| Spot instances | Fault-tolerant workloads | 60-90% |
| Azure Advisor | Recommendations engine | Varies |
| Cost Management | Budgets and alerts | Visibility |

**Deliverable**: Whiteboard showing optimization strategy with projected savings

---

### Part C: Hybrid Management with Azure Arc (10 min)

Not everything may migrate to Azure. Design a hybrid strategy:

#### Hybrid Scenarios

| Scenario | Solution |
|----------|----------|
| Servers that can't migrate (legacy apps, compliance) | Azure Arc-enabled servers |
| SQL databases staying on-prem | Azure Arc-enabled SQL Server |
| Kubernetes clusters on-prem | Azure Arc-enabled Kubernetes |
| Data services on-prem | Azure Arc data services |

#### Azure Arc Benefits

| Capability | Description |
|------------|-------------|
| **Single pane of glass** | Manage Azure + on-prem from Azure portal |
| **Azure Policy** | Apply governance across hybrid estate |
| **Azure Monitor** | Unified monitoring |
| **Microsoft Defender** | Security across environments |
| **Azure Update Manager** | Centralized patching |

**Design Exercise**:

If some servers must remain on-premises:
- Which servers would stay? (e.g., latency requirements, regulations)
- How would you manage them alongside Azure?
- What policies would apply to both environments?

**Deliverable**: Hybrid architecture showing Azure + Arc-managed on-prem

---

### Part D: Governance Design (5 min)

Design the governance structure:

#### Management Group Hierarchy

```
Root Management Group
├── Platform
│   ├── Identity
│   ├── Management
│   └── Connectivity
└── Landing Zones
    ├── Production
    │   └── Contoso-Prod (Subscription)
    └── Non-Production
        └── Contoso-Dev (Subscription)
```

#### Key Azure Policies

| Policy | Scope | Effect |
|--------|-------|--------|
| Allowed locations | Landing Zones | Deny non-EU regions |
| Allowed VM SKUs | Production | Deny expensive/burstable |
| Require tags | All | Deny resources without cost center |
| Enable backup | Production | DeployIfNotExists |
| Enable Defender | All | DeployIfNotExists |

#### RBAC Assignments

| Role | Scope | Assigned To |
|------|-------|-------------|
| Owner | Subscription | IT Admin team |
| Contributor | Resource Group | Migration team |
| Reader | Subscription | Finance/Audit |
| Security Reader | Management Group | Security team |

**Deliverable**: Governance structure on whiteboard

---

## Expected Deliverables

Add to your whiteboard:

1. ✅ **Cost Summary**
   - Monthly/annual estimates
   - Before and after optimization

2. ✅ **Optimization Strategy**
   - Hybrid Benefit applicability
   - Reserved Instance recommendations
   - Right-sizing opportunities

3. ✅ **Hybrid Architecture**
   - What's in Azure, what's Arc-managed
   - Single pane of glass approach

4. ✅ **Governance Structure**
   - Management groups
   - Key policies
   - RBAC design

📸 **Final whiteboard photo!**

---

## Coaching Tips

💡 **Hybrid Benefit is often forgotten** — Big savings if licenses exist

💡 **Start with Pay-as-you-go** — Commit to RIs after usage patterns stabilize

💡 **Right-sizing is iterative** — Use Azure Advisor ongoing

💡 **Azure Arc isn't just for non-migrated servers** — Consider for future acquisitions

💡 **Governance prevents cost surprises** — Policies save money!

---

## Reference: Azure Cost Management Tools

| Tool | Purpose | When to Use |
|------|---------|-------------|
| **Pricing Calculator** | Pre-migration estimates | Planning phase |
| **TCO Calculator** | Compare on-prem vs Azure | Business case |
| **Cost Management** | Track actual spend | Post-migration |
| **Azure Advisor** | Optimization recommendations | Ongoing |
| **Budgets & Alerts** | Spending limits | Governance |

---

## Reference: Well-Architected Framework - Cost Optimization

Key principles:
1. **Plan and estimate costs** — Before deployment
2. **Provision with optimization** — Right-size from start
3. **Use monitoring and analytics** — Track spending
4. **Maximize efficiency** — Optimize continuously
5. **Use governance** — Enforce standards

---

## Bonus Points Opportunity! (+5)

Impress the judges with advanced cost optimization:

- [ ] Detailed TCO comparison (on-prem vs Azure)
- [ ] Savings plan analysis
- [ ] Tagging strategy for cost allocation
- [ ] Showback/chargeback model

---

## Reflection Questions

- What surprised you about the cost estimates?
- How does governance impact cost management?
- Would you recommend Azure Arc for Contoso's hybrid strategy?

---

## Next Step

Prepare for [Challenge 7: Presentation](challenge-7-presentation.md) — Time to present your complete migration strategy!
