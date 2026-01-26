# Challenges Overview

This folder contains all challenge instructions for the Azure Migration Workshop.

## Challenge Flow

```mermaid
graph TD
    C0[Challenge 0: Azure 101<br/>30 min | No points] --> C1[Challenge 1: Plan<br/>60 min | 25 pts]
    C1 --> C2[Challenge 2: Deploy Appliance<br/>90 min | 25 pts]
    C2 --> LUNCH[🍽️ Lunch<br/>Discovery runs]
    LUNCH --> C3[Challenge 3: Assessment<br/>60 min | 20 pts]
    C3 --> C4[Challenge 4: Execute<br/>45 min | 15 pts]
    C4 --> C5[Challenge 5: Curveball 🎲<br/>30 min | 10 pts]
    C5 --> C6[Challenge 6: Optimize<br/>45 min | Included]
    C6 --> C7[Challenge 7: Presentation<br/>30 min | 5 pts]
    
    style C0 fill:#e1f5fe
    style C2 fill:#e8f5e9
    style C3 fill:#e8f5e9
    style C1 fill:#fff3e0
    style C4 fill:#fff3e0
    style C5 fill:#ffebee
    style C6 fill:#fff3e0
    style C7 fill:#f3e5f5
```

**Legend**: 🔵 Prerequisite | 🟢 Hands-on Lab | 🟠 Whiteboard Design | 🔴 Curveball | 🟣 Presentation

---

## Challenge Index

| # | Challenge | Duration | Type | Points | CAF Phase |
|---|-----------|----------|------|--------|-----------|
| 0 | [Azure 101](challenge-0-azure-101.md) | 30 min | Hands-on | — | — |
| 1 | [Plan](challenge-1-plan.md) | 60 min | WDS | 25 | Plan |
| 2 | [Deploy Appliance](challenge-2-appliance.md) | 90 min | Hands-on | 25 | Prepare |
| 3 | [Assessment](challenge-3-assessment.md) | 60 min | Hands-on | 20 | Execute |
| 4 | [Execute](challenge-4-execute.md) | 45 min | WDS | 15 | Execute |
| 5 | [Curveball](challenge-5-curveball.md) | 30 min | WDS | 10 | Execute |
| 6 | [Optimize](challenge-6-optimize.md) | 45 min | WDS | — | Optimize |
| 7 | [Presentation](challenge-7-presentation.md) | 30 min | Present | 5 | All |

---

## Scoring Summary

| Category | Points | Challenges |
|----------|--------|------------|
| CAF Plan | 25 | Challenge 1 |
| CAF Prepare | 25 | Challenge 2 |
| CAF Execute | 45 | Challenges 3, 4, 5 |
| Presentation | 5 | Challenge 7 |
| **Total** | **100** | |
| Bonus | +15 | Arc, Cost, Security |

---

## Challenge Types

### 🟢 Hands-on Labs

Step-by-step technical exercises using Azure Migrate appliance and Azure portal. Teams work together on their shared ArcBox environment.

- Challenge 0: Azure 101
- Challenge 2: Deploy Appliance
- Challenge 3: Assessment

### 🟠 Whiteboard Design Sessions (WDS)

Collaborative design exercises using flip charts or whiteboards. Teams discuss, debate, and document their migration strategy.

- Challenge 1: Plan
- Challenge 4: Execute
- Challenge 5: Curveball
- Challenge 6: Optimize

### 🔴 Curveball

A surprise requirement announced mid-workshop that forces teams to adapt their plans. Simulates real-world project changes.

- Challenge 5: GDPR Compliance (announced at 15:00)

### 🟣 Presentation

Final team presentations in chalk-talk format with objection handling.

- Challenge 7: Presentation

---

## Tips for Success

1. **Read the entire challenge** before starting
2. **Divide and conquer** — use your team of 4 effectively
3. **Document as you go** — you'll need it for the presentation
4. **Ask for hints** — check [Hints and Tips](../participant/hints-and-tips.md)
5. **Time-box** — don't get stuck, move forward

---

**Start here**: [Challenge 0: Azure 101](challenge-0-azure-101.md)
