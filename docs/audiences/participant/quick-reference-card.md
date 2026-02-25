# Quick Reference Card

> 📄 **Print this page** for easy reference during the workshop.

---

## 📅 Schedule At-a-Glance

| Time | Activity | Points |
|------|----------|--------|
| 10:00 | Welcome & Azure 101 | — |
| 10:15 | Scenario Intro | — |
| 10:30 | **C1: Plan** (WDS) | 25 |
| 11:15 | **C2: Deploy Appliance** | 25 |
| 12:30 | 🍽️ Lunch | — |
| 13:15 | **C3: Assessment** | 20 |
| 14:00 | **C4: Execute** (WDS) | 15 |
| 14:30 | ☕ Break | — |
| 14:45 | **C5: Curveball** 🎲 | 10 |
| 15:15 | **C6: Optimize** (WDS) | — |
| 16:00 | **C7: Presentation** | 5 |
| 16:45 | Wrap-up | — |

**Total**: 100 points + bonus

---

## 🔗 Key URLs

| Resource | URL |
|----------|-----|
| Azure Portal | [portal.azure.com](https://portal.azure.com) |
| Azure Migrate Docs | [learn.microsoft.com/azure/migrate](https://learn.microsoft.com/azure/migrate/) |
| CAF Migrate | [learn.microsoft.com/azure/cloud-adoption-framework/migrate](https://learn.microsoft.com/azure/cloud-adoption-framework/migrate/) |

---

## 🖥️ ArcBox Servers

| Server | Role | IP |
|--------|------|-----|
| ArcBox-Win2K22 | App Server | 10.10.1.100 |
| ArcBox-Win2K25 | File Server | 10.10.1.101 |
| ArcBox-SQL | Database | 10.10.1.102 |
| ArcBox-Ubuntu-01 | Web Server | 10.10.1.103 |
| ArcBox-Ubuntu-02 | Monitoring | 10.10.1.104 |

**Credentials**: See facilitator

---

## 🛠️ Azure Migrate Quick Steps

1. **Create project**: Azure Migrate → Create project
2. **Generate key**: Discover → Hyper-V → Generate key
3. **Download VHD**: Download appliance
4. **Import**: Hyper-V Manager → Import VM
5. **Configure**: `https://<IP>:44368`
6. **Register**: Paste key → Login
7. **Add credentials**: Hyper-V host + server creds
8. **Discover**: Start discovery

---

## 📊 Scoring Summary

| Challenge | Points | Focus |
|-----------|--------|-------|
| C1: Plan | 25 | Strategy, waves, dependencies |
| C2: Appliance | 25 | Deploy, register, discover |
| C3: Assessment | 20 | Create, analyze, document |
| C4: Execute | 15 | Tools, sequence, rollback |
| C5: Curveball | 10 | GDPR adaptation |
| C7: Presentation | 5 | Delivery, objections |
| **Total** | **100** | |

---

## ⚡ CAF Migrate Phases

```
PLAN → PREPARE → EXECUTE → OPTIMIZE → DECOMMISSION
```

---

## 🎯 Presentation Objections

1. **PaaS vs IaaS**: Why SQL on VM vs Managed Instance?
2. **Rollback**: Walk through exact steps to revert
3. **GDPR**: How to guarantee EU data residency?

---

## 🆘 Need Help?

1. Check [Hints and Tips](hints-and-tips.md)
2. Ask your team
3. Raise your hand for facilitator

---

## 📝 Notes

```
Team Name: _______________________

Subscription ID: _______________________

ArcBox Resource Group: _______________________

Appliance Name: _______________________

Project Key: _______________________

```

---

Good luck! 🚀
