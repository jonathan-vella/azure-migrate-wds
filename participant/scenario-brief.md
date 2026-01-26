# Scenario Brief: Contoso Manufacturing

## Company Overview

**Contoso Manufacturing** is a mid-sized industrial equipment manufacturer headquartered in Munich, Germany, with operations across Europe.

| Attribute | Details |
|-----------|---------|
| Industry | Industrial Manufacturing |
| Employees | 2,500 |
| Revenue | €180M annually |
| Locations | Germany (HQ), France, Poland, UK |
| IT Staff | 25 (central IT team) |

---

## Business Context

### Current Situation

Contoso operates a traditional on-premises datacenter that hosts their critical business applications. The infrastructure is aging, and the company faces several challenges:

- **Hardware refresh due** — Primary servers are 5+ years old
- **Capacity constraints** — Struggling to meet growing demand
- **Skills gap** — Hard to hire on-prem infrastructure specialists
- **Business continuity** — Limited DR capabilities
- **Remote work** — COVID accelerated need for cloud access

### Strategic Initiative

The CTO has initiated a **"Cloud First" strategy** with the goal of migrating 80% of workloads to Azure within 18 months. This workshop focuses on the first wave of that migration.

---

## Current Environment

Your simulated on-premises datacenter (represented by ArcBox) contains:

### Server Inventory

| Server Name | Operating System | Role | Business Criticality |
|-------------|------------------|------|---------------------|
| **ArcBox-Win2K22** | Windows Server 2022 | Application Server | High |
| **ArcBox-Win2K25** | Windows Server 2025 | File Server | Medium |
| **ArcBox-SQL** | Windows Server 2022 + SQL Server 2022 | Database Server | Critical |
| **ArcBox-Ubuntu-01** | Ubuntu 22.04 LTS | Web Server | High |
| **ArcBox-Ubuntu-02** | Ubuntu 22.04 LTS | Monitoring Server | Medium |

### Application Landscape

```
┌─────────────────────────────────────────────────────────────────┐
│                    CONTOSO MANUFACTURING                         │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   [Customer Portal]         [Internal Apps]        [Monitoring]  │
│   Ubuntu-01 (Web)    ←→    Win2K22 (App)    →    Ubuntu-02      │
│         ↓                        ↓                              │
│         └──────────→ [SQL Database] ←──────────┘                │
│                      ArcBox-SQL                                  │
│                                                                  │
│   [File Shares]                                                  │
│   Win2K25 (Files)                                               │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

### Dependencies

| Application | Depends On | Notes |
|-------------|------------|-------|
| Customer Portal (Ubuntu-01) | SQL Database, App Server | Customer-facing, 24/7 |
| Internal Apps (Win2K22) | SQL Database | Business hours only |
| Monitoring (Ubuntu-02) | All servers | Collects metrics from everything |
| File Server (Win2K25) | Active Directory | Department file shares |

---

## Stakeholder Requirements

### CTO (Chief Technology Officer)

> "I want a solid migration plan that minimizes risk. We can't afford extended downtime — our production lines depend on these systems."

**Priorities**:
- Risk mitigation
- Clear rollback strategy
- Skills enablement for IT team

### CFO (Chief Financial Officer)

> "Show me the business case. I need to understand the costs — both migration and ongoing. And I want to see savings, not just different spending."

**Priorities**:
- Clear cost estimates
- ROI justification
- Cost optimization opportunities

### CISO (Chief Information Security Officer)

> "Our customer data is sensitive. I need assurance that security and compliance requirements are met — especially GDPR."

**Priorities**:
- Data protection
- GDPR compliance
- Security controls in Azure

### Operations Manager

> "My team runs these systems 24/7. We need minimal disruption and a clear handover plan. Don't break anything!"

**Priorities**:
- Minimal downtime
- Clear runbook documentation
- Monitoring continuity

---

## Constraints

| Constraint | Details |
|------------|---------|
| **Downtime window** | Maximum 4 hours for critical systems |
| **Timeline** | First wave must complete within 3 months |
| **Budget** | €50,000 for migration activities (tooling, services) |
| **Data residency** | Customer data must remain in EU (GDPR) |
| **Skills** | IT team has basic Azure experience, need guidance |

---

## Success Criteria

The migration will be considered successful when:

1. ✅ All 5 servers migrated to Azure (or managed via Arc)
2. ✅ Applications functional with same or better performance
3. ✅ GDPR compliance requirements met and documented
4. ✅ Monitoring operational with comparable visibility
5. ✅ IT team trained on Azure operations
6. ✅ Total cost of ownership reduced by 15% or justified

---

## Your Mission

As the migration consulting team, you will:

1. **Discover and assess** the current environment using Azure Migrate
2. **Design a migration strategy** aligned with Cloud Adoption Framework
3. **Plan migration waves** with proper sequencing and dependencies
4. **Address compliance requirements** including GDPR
5. **Optimize for cost** and design governance controls
6. **Present your plan** to Contoso leadership

---

## Questions to Consider

As you work through the challenges, think about:

- Which workload is the best pilot candidate?
- How do you handle the SQL database migration?
- What happens if the web server migration fails at 2 AM?
- How will you prove GDPR compliance?
- What's your recommendation for the monitoring server?

---

## Additional Context

### IT Environment Details

| Component | Current State |
|-----------|---------------|
| Virtualization | Hyper-V |
| Active Directory | On-premises AD DS |
| Backup | Veeam (local) |
| Monitoring | Nagios + Grafana |
| Network | 1 Gbps internal, 100 Mbps internet |

### Business Hours

| Region | Primary Hours | Critical Period |
|--------|---------------|-----------------|
| Germany (HQ) | 07:00-18:00 CET | Month-end close |
| UK | 08:00-17:00 GMT | Customer orders |
| France | 08:00-18:00 CET | Production runs |
| Poland | 07:00-16:00 CET | Manufacturing |

---

Good luck with your migration planning!
