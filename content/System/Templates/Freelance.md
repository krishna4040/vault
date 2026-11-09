---
publish: true
title: <% tp.file.title %>
created: <% tp.date.now() %>
modified: 2026-10-15T16:16:14.669Z
published: 2026-10-15T16:16:14.669Z
tags:
  - freelance
  - template
cover:
status: active
priority: 3
mode: Full Mode
"- [Rough Total Estimate": 3 Months]
"- [Buffer Rule": 25%]
"\n# Budget\n- [Pricing Model": Fixed / Hourly / Monthly]
"- [Ad-hoc Rule": Add to backlog, Impact cost and timeline]
Rough Total Estimate: 3 Months
Buffer Rule: 25%
Pricing Model: Fixed / Hourly / Monthly
Ad-hoc Rule: Add to backlog, Impact cost and timeline
---

# Overview

- \[Name::{{Name}}]
- \[Description::{{Description}}]
- \[ORG::{{URL}}]
- \[Contract::{{URL}}]
- \[Project Type::{{Type}}]

# Stakeholder Description

| Name | Role | Influence | Contacts | Notes |
| ---- | ---- | --------- | -------- | ----- |
|      |      |           |          |       |

# Goals / Outcomes

**Purpose (Primary Goal)**

> Why This Exists?

**Sub Goal**

- [ ] {{GOAL1}}
- [ ] {{GOAL2}}
- [ ] {{GOAL3}}

**Success Metrics (Checks)**

| Metric          | Type    | Current | Target        | Cadence |
| --------------- | ------- | ------- | ------------- | ------- |
| Sprint Velocity | Process |         |               | 15 days |
| user signups    | Outcome | 0       | 100 per month | monthly |
| API response    | Outcome | 100ms   | 10ms          | monthly |

**Definition of Done**

> When this project is considered complete?

# Risks

| Risk                | Trigger                  | Action                               |
| ------------------- | ------------------------ | ------------------------------------ |
| Scope Creep (AdHoc) | New request Mid sprint   | Move to next sprint or Increase cost |
| Delay               | Missed Sprint Goals      | Re-estimate timeline                 |
| Spike tasks         | New Research task        | extra time required                  |
| Compliance          | Legal Risk with business | extra time required                  |

# Time

- \[Daily Working Hours::{{4 Hrs}}]
- \[Availability Constraints::{{Weekdays}}]
- \[Rough Total Estimate:: 3 Months]
- \[Buffer Rule:: 25%]

# Budget

- \[Pricing Model:: Fixed / Hourly / Monthly]
- \[Ad-hoc Rule:: Add to backlog, Impact cost and timeline]

_Invoice Tracker_

| Invoice ID | Date | Amount | Due Date | Status  | Paid On |
| ---------- | ---- | ------ | -------- | ------- | ------- |
| INV001     |      |        |          | pending |         |

# Communication

- \[Communication Channel::{{Channel}}]
- \[Meetings::{{Zoom/Meet/etc}}]
- \[Sprint Duration::15 Days]

| Meetings        | Cadence              | Purpose                       | Duration | status    | Invite |
| --------------- | -------------------- | ----------------------------- | -------- | --------- | ------ |
| Standup         | Daily                | Daily sync up                 | 15 mins  | scheduled |        |
| Grooming        | Before End of sprint | New Requirments               | 30 mins  | pending   |        |
| Sprint Planning | Start of sprint      | what to do in upcoming spring | 30 mins  | pending   |        |
| Demo            | End of sprint        | show case progress            | 30 mins  | pending   |        |
| Retro           | End of sprint        | Improvements that can be made | 15 mins  | pending   |        |

# Access and Infrastructure

_Accounts and Access_

| Service | Owner  | Account Type | Status  |
| ------- | ------ | ------------ | ------- |
| AWS     | Client | IAM          | pending |
| Github  | Client | Collaborator | pending |
| Domain  | Client | Full Access  | pending |
_Infrastructure Cost_

| Service | Usage    | Estimated Cost (Monthly) | Notes |
| ------- | -------- | ------------------------ | ----- |
| AWS EC2 | t2.micro | ₹                        |       |
| S3      | Storage  | ₹                        |       |
| Domain  | Yearly   | ₹                        |       |
_Ownership Notes_

- All accounts owned by client
- Access provided via roles (not personal accounts)
- Handover required after completion

_Environments_

| ENV     | URL |
| ------- | --- |
| Prod    |     |
| Staging |     |
| Dev     |     |

---

## References

```tabs
tab: Recent Meeting Notes
| File | date | attendees |
| ---- | ---- | --------- |

tab: Documents

tab: Resources
~

<%await tp.file.move("PARA/Projects/PARA")%>

<%*
tp.hooks.on_all_templates_executed(async () => {  
const file = tp.file.find_tfile(tp.file.path(true));  
let title = await tp.system.prompt("Project/Area Name:")  
let tags = await tp.system.prompt("Tags:","moc",false,true);
let date = tp.date.now()
await tp.app.fileManager.processFrontMatter(file,(frontmatter) => {  
frontmatter.tags = tags
frontmatter.title = title
frontmatter.created = date
});  
});  
%>
```
