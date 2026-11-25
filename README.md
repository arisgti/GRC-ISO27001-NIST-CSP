# IT@serve Company: GRC Project

> **Disclaimer:** IT@serve Company is a **fictional** Canadian organization created for learning and portfolio purposes. All names, numbers and scenarios are invented. Nothing here is legal or compliance advice.

## Contents

1. [Scenario](#1-scenario)
2. [Project at a glance](#2-project-at-a-glance)
3. [Repository structure](#3-repository-structure)
4. [How to read this project](#4-how-to-read-this-project)
5. [Part 1: Scope and context](#5-part-1-scope-and-context)
6. [Part 2: Risk assessment](#6-part-2-risk-assessment)
7. [Part 3: Controls, frameworks and gaps](#7-part-3-controls-frameworks-and-gaps)
   - [7.1 Statement of Applicability](#71-statement-of-applicability)
   - [7.2 ISO 27001 to NIST CSF crosswalk](#72-iso-27001-to-nist-csf-crosswalk)
   - [7.3 Understanding NIST CSF 2.0](#73-understanding-nist-csf-20)
   - [7.4 CSF profile and gap analysis](#74-csf-profile-and-gap-analysis)
   - [7.5 Canadian baseline controls](#75-canadian-baseline-controls)
8. [Reading the codes](#8-reading-the-codes)
9. [Assumptions and limitations](#9-assumptions-and-limitations)
10. [Revision history](#10-revision-history)
11. [Ideas for further work](#11-ideas-for-further-work)

## 1. Scenario

IT@serve Company is a small startup **Managed Service Provider (MSP) based in Canada** that supports **Canadian dental clinics** with 1 to 10 chairs. A *chair* is one treatment room, so a client is anything from a solo dentist to a practice with about ten treatment rooms. IT@serve manages clinic IT (workstations, servers, networks, backups, Microsoft 365, practice management software and imaging systems) and has privileged remote access to systems that hold **patient health information**. That makes it a high-value target and a critical supplier for its clients. Canadian privacy and health-information law shapes what clinics, and therefore IT@serve, must do.

This project builds a Governance, Risk and Compliance (GRC) program for IT@serve using:

- **ISO/IEC 27001:2022** (ISMS, risk assessment, Annex A controls)
- **NIST Cybersecurity Framework (CSF) 2.0** (Govern, Identify, Protect, Detect, Respond, Recover)

## 2. Project at a glance

The project has three parts. Each feeds the next, so a change in Part 1 (for example the Canadian focus) flows into the risks in Part 2 and then into the controls and profile in Part 3.

| Part | Focus | Folder | Main files |
|---|---|---|---|
| **1** | Scope and context | [`01-scope-and-context/`](01-scope-and-context/) | Company profile, ISMS scope, services and data flow |
| **2** | Risk assessment | [`02-risk-assessment/`](02-risk-assessment/) | Risk methodology, risk register, asset register, risk treatment plan |
| **3** | Controls, frameworks and gaps | [`03-iso27001-mapping/`](03-iso27001-mapping/) and [`04-nist-csf/`](04-nist-csf/) | Statement of Applicability, Annex A to CSF crosswalk, Canadian baseline mapping, CSF profile, gap analysis |

### Key results

| Area | Result |
|---|---|
| Assets | 24 assets rated for confidentiality, integrity and availability, with hosting region and cross-border status |
| Risks | 16 risks: 5 Critical, 7 High, 4 Medium before treatment; 13 Medium and 3 Low after, none above Medium |
| Treatment plan | 28 actions (14 P1, 12 P2, 2 P3) with owners, dates and evidence of completion |
| Statement of Applicability | 82 of 93 Annex A controls applicable, 11 excluded with justification |
| Crosswalk | 93 Annex A controls mapped to NIST CSF 2.0; Annex A reaches 77 of 106 subcategories (91 including ISO clauses) |
| NIST CSF 2.0 profile | 106 subcategories scored; average maturity 1.3 now, target 3.0; 19 P1 priorities; 3-phase roadmap |

## 3. Repository structure

```
grc-project/
├── README.md                          (this file)
├── 01-scope-and-context/              Part 1
│   ├── company-profile.md
│   ├── isms-scope.md
│   └── services-and-data-flow.md
├── 02-risk-assessment/                Part 2
│   ├── risk-methodology.md
│   ├── asset-register.xlsx
│   ├── risk-register.xlsx
│   └── risk-treatment-plan.md         (updated in Part 3)
├── 03-iso27001-mapping/               Part 3
│   ├── statement-of-applicability.xlsx / .md
│   ├── annexA-to-csf-crosswalk.xlsx / .md
│   └── cccs-baseline-mapping.md
└── 04-nist-csf/                       Part 3
    ├── csf-profile.xlsx / .md
    └── gap-analysis.md
```

Spreadsheets (`.xlsx`) are the working files. GitHub does not preview them, so the key tables are also provided as Markdown.

## 4. How to read this project

1. **Part 1:** start with [`isms-scope.md`](01-scope-and-context/isms-scope.md) for the organization, the Canadian legal context and what is in scope.
2. **Part 2:** read [`risk-methodology.md`](02-risk-assessment/risk-methodology.md), then open [`risk-register.xlsx`](02-risk-assessment/risk-register.xlsx) and [`risk-treatment-plan.md`](02-risk-assessment/risk-treatment-plan.md).
3. **Part 3:** read sections 7.1 to 7.5 below, then [`gap-analysis.md`](04-nist-csf/gap-analysis.md) for the roadmap.

## 5. Part 1: Scope and context

Files: [`company-profile.md`](01-scope-and-context/company-profile.md), [`isms-scope.md`](01-scope-and-context/isms-scope.md), [`services-and-data-flow.md`](01-scope-and-context/services-and-data-flow.md)

**The company.** 12 employees and 2 contractors, remote-first, with a small staging office. It serves 18 clinics in several Canadian provinces (about 220 managed endpoints and 25 servers) under monthly service contracts in Canadian dollars.

**Business objectives that drive security.**

| Code | Objective |
|---|---|
| O1 | Keep client clinics running with minimal downtime |
| O2 | Protect patient data handled on client systems |
| O3 | Grow from 18 to 40 clinics in 24 months |
| O4 | Win larger group-practice clients |
| O5 | Meet Canadian privacy, health-information and record-keeping expectations of clinics |
| O6 | Prefer Canadian data residency for client data and backups where practical |

**ISMS scope (ISO 27001 clauses 4.1 to 4.3).** The ISMS covers managed IT services to dental clinics in Canada: people, tools, work locations and the information IT@serve handles for itself and its clients. Clinic premises, clinical decisions, the clinic's own privacy program, third-party SaaS internals and clinics outside Canada are out of scope, each with a reason.

**Canadian context.** The clinic is accountable for patient information, and IT@serve is its service provider. Depending on the province, the provider has a legal role with its own terms (for example information manager in Alberta, or agent and electronic service provider in Ontario). The legal summary in `isms-scope.md` covers:

- PIPEDA, the federal private-sector law, including breach reporting when there is a real risk of significant harm, notification, and a breach record kept for 24 months
- provincial private-sector privacy laws and provincial health-information laws
- Québec Law 25, including incident reporting and transfer assessments for information leaving Québec
- provincial dental regulatory colleges, client contracts and cyber insurance conditions

It is a learning summary. A real organization would confirm it for each province with a lawyer or privacy professional.

**Data and data flows.** Four classification levels (Restricted, Confidential, Internal, Public). Patient data and client admin credentials are Restricted. The RMM platform, remote access tool, password manager and backup platform are single points of failure for every client. A hosting-region view shows which tools may keep data outside Canada.

## 6. Part 2: Risk assessment

Files: [`risk-methodology.md`](02-risk-assessment/risk-methodology.md), [`asset-register.xlsx`](02-risk-assessment/asset-register.xlsx), [`risk-register.xlsx`](02-risk-assessment/risk-register.xlsx), [`risk-treatment-plan.md`](02-risk-assessment/risk-treatment-plan.md)

**Method (ISO 27001 clauses 6.1.2 and 6.1.3).** Identify assets, identify risks (a mix of asset-based and scenario-based), score **inherent risk = likelihood x impact** on 5-point scales, evaluate against appetite, treat (reduce, accept, avoid or transfer), re-score **residual risk**, then monitor and review.

| Rating | Score | Required action |
|---|---|---|
| Critical | 15 to 25 | Treat immediately. CEO owns the risk. Cannot be accepted |
| High | 10 to 14 | Treat within 90 days with a funded plan |
| Medium | 5 to 9 | Treat, or accept with documented owner approval |
| Low | 1 to 4 | Accept and monitor |

**Appetite:** low for risks that could expose patient data or interrupt many clinics. After treatment, residual risk must be Medium or lower.

**Canadian scoring rules.** Impact values are in CAD. A privacy breach is impact 3 when the clinic only records it, and impact 4 or higher when the clinic must report to the privacy regulator and notify patients. Every breach is recorded for at least 24 months. Patient data hosted outside Canada, or outside Québec for a Québec clinic, is scored higher until an assessment and client approval are in place.

**Risk register (16 risks).**

| ID | Risk | Inherent | Treatment | Residual |
|---|---|---|---|---|
| R-01 | Compromise of RMM or remote access tooling | Critical (20) | Reduce | Medium (8) |
| R-02 | Phishing and credential theft against technicians | Critical (16) | Reduce | Medium (8) |
| R-03 | Ransomware at a client clinic with failed or untested backups | Critical (20) | Reduce + Transfer | Medium (9) |
| R-04 | Patient data exposure through device loss or mishandling | High (12) | Reduce | Medium (6) |
| R-05 | Excessive or lingering privileged access | Critical (16) | Reduce | Medium (6) |
| R-06 | Supplier outage or breach (RMM, backup, cloud vendors) | High (12) | Reduce + Transfer | Medium (8) |
| R-07 | Unpatched client systems and unsupported imaging or legacy software | High (12) | Reduce | Medium (6) |
| R-08 | Insider error or misuse by a technician | High (12) | Reduce | Medium (6) |
| R-09 | Loss of key personnel and undocumented knowledge | Medium (9) | Reduce | Low (4) |
| R-10 | Non-compliance with Canadian privacy, health-information, contract and breach-notification duties | High (12) | Reduce | Medium (6) |
| R-11 | Slow detection and response to security incidents | High (12) | Reduce | Medium (6) |
| R-12 | Inconsistent onboarding of new clinics as the company grows | Medium (9) | Reduce | Low (4) |
| R-13 | Outage of internal ticketing (PSA) platform | Medium (6) | Accept | Medium (6) |
| R-14 | Privileged client access from personal or unmanaged devices | Critical (16) | Avoid | Medium (8) |
| R-15 | Patient data hosted or accessed outside Canada without assessment or client approval | High (12) | Reduce | Medium (6) |
| R-16 | Missing or inconsistent provincial service-provider agreements with clinics | Medium (9) | Reduce | Low (3) |

The two risks added in the Canadian revision are **R-15** (patient data hosted or accessed outside Canada without assessment or client approval) and **R-16** (missing provincial service-provider agreements). R-10 was strengthened to cover Canadian breach duties.

**Treatment plan (28 actions).** Every action has an owner, priority, target date and evidence of completion, and maps to Annex A controls. 14 are P1, 12 P2 and 2 P3. Examples: phishing-resistant MFA (TP-01), immutable backups with restore tests (TP-05), supplier register with hosting regions (TP-10), legal requirements register and 24-month breach record (TP-14), data residency review (TP-27), and a clinic agreement pack with a go-live gate (TP-28). Actions TP-18 to TP-26 came from the Statement of Applicability in Part 3.

## 7. Part 3: Controls, frameworks and gaps

### 7.1 Statement of Applicability

Files: [`statement-of-applicability.xlsx`](03-iso27001-mapping/statement-of-applicability.xlsx), [`statement-of-applicability.md`](03-iso27001-mapping/statement-of-applicability.md)

The SoA lists all **93 controls** in ISO/IEC 27001:2022 Annex A (37 organizational, 8 people, 14 physical, 34 technological). Each control is linked to risks and actions, marked applicable or not for a stated reason (risk assessment, legal or regulatory, contractual, or business and good practice), and given a current status.

| Measure | Value |
|---|---|
| Applicable | **82 of 93** |
| Excluded | **11** |
| Implemented | 1 |
| Partially implemented | 19 |
| Planned | 62 |

| Theme | Total | Applicable | Excluded |
|---|---|---|---|
| Organizational | 37 | 37 | 0 |
| People | 8 | 8 | 0 |
| Physical | 14 | 10 | 4 |
| Technological | 34 | 27 | 7 |

Most controls are *Planned* because IT@serve is modelled as a young company building its ISMS from scratch.

**Exclusions** (each justified in the SoA, and tied to the Part 1 scope):

| Control | Reason |
|---|---|
| 7.4 Physical security monitoring | The office holds only spare equipment and no data stores. Building security is provided by the landlord. Risk is low and accepted |
| 7.6 Working in secure areas | No secure areas are defined in scope |
| 7.11 Supporting utilities, 7.12 Cabling security | Critical systems are cloud-hosted. The office has no server room |
| 8.11 Data masking | Patient data is not used for analytics or development. Access restriction (8.3) limits exposure |
| 8.25 and 8.27 to 8.31 (secure development, architecture, coding, testing, outsourced development, environment separation) | IT@serve does not develop software. Scripts are covered by 8.4 and change management (8.32) |

If the scope changes, for example IT@serve starts hosting client servers or writing its own software, these decisions must be reviewed.

**What the exercise revealed.** Mapping all 93 controls exposed areas the risk-driven pass had missed. Nine actions (TP-18 to TP-26) were added, among them a policy set, an internal audit programme, physical and equipment security, a records retention schedule and incident evidence handling. Eleven controls (5.5, 5.19, 5.20, 5.23, 5.24, 5.26, 5.31, 5.33, 5.34, 5.37, 8.10) have justifications that cite Canadian duties.

### 7.2 ISO 27001 to NIST CSF crosswalk

Files: [`annexA-to-csf-crosswalk.xlsx`](03-iso27001-mapping/annexA-to-csf-crosswalk.xlsx), [`annexA-to-csf-crosswalk.md`](03-iso27001-mapping/annexA-to-csf-crosswalk.md)

A two-way mapping between the 93 Annex A controls and the 106 CSF 2.0 subcategories, with one primary and up to three secondary matches per control.

> **Caveat:** the crosswalk is my own analysis, built for learning. It is not NIST's official mapping. Compare it with NIST's OLIR catalog and the Secure Controls Framework before relying on it.

| Result | CSF 2.0 subcategories (of 106) |
|---|---|
| Annex A control is the primary match | 48 |
| Annex A control is a secondary match only | 29 |
| Covered only by ISO 27001 management-system clauses 4 to 10 | 14 |
| No match found in this analysis | 15 |

| CSF function | Subcategories | Via Annex A | Via clauses only | No match |
|---|---|---|---|---|
| Govern | 31 | 16 | 11 | 4 |
| Identify | 21 | 17 | 3 | 1 |
| Protect | 22 | 22 | 0 | 0 |
| Detect | 11 | 9 | 0 | 2 |
| Respond | 13 | 9 | 0 | 4 |
| Recover | 8 | 4 | 0 | 4 |

- **Protect** is fully covered by Annex A, as expected from a control-based standard.
- **Govern** relies heavily on ISO 27001 clauses (context, leadership, planning, review). In practice the clauses are the Govern function.
- The **15 subcategories with no match** are mainly about incident coordination, recovery communication and supplier involvement in incident response (GV.SC-02, GV.SC-03, GV.SC-08, GV.SC-10, ID.RA-10, DE.AE-03, DE.AE-04, RS.MA-04, RS.MA-05, RS.AN-08, RS.CO-03, RC.RP-05, RC.RP-06, RC.CO-03, RC.CO-04). They are good candidates to add to IT@serve's own incident and supplier procedures.

### 7.3 Understanding NIST CSF 2.0

The NIST CSF is a voluntary, outcome-based framework. It describes **what** good cybersecurity risk management achieves, not which products to buy. Version 2.0 (February 2024) has **6 functions, 22 categories and 106 subcategories**.

| Function | Question it answers | Categories |
|---|---|---|
| **Govern (GV)** *new in 2.0* | How do we direct and oversee cybersecurity risk? | Organizational Context, Risk Management Strategy, Roles and Responsibilities, Policy, Oversight, Supply Chain Risk Management |
| **Identify (ID)** | What do we have and what could go wrong? | Asset Management, Risk Assessment, Improvement |
| **Protect (PR)** | How do we reduce likelihood and impact? | Identity and Access, Awareness and Training, Data Security, Platform Security, Infrastructure Resilience |
| **Detect (DE)** | How do we find attacks and problems? | Continuous Monitoring, Adverse Event Analysis |
| **Respond (RS)** | What do we do about a detected incident? | Incident Management, Analysis, Reporting and Communication, Mitigation |
| **Recover (RC)** | How do we restore normal operations? | Incident Recovery Plan Execution, Recovery Communication |

The functions are not a sequence. They run at the same time, and Govern wraps around the other five.

- **Subcategory:** one specific outcome, for example PR.AA-03 "Users, processes, and hardware are authenticated". The ID is function, category, number.
- **Organizational Profile:** a snapshot of the outcomes you achieve today (**Current Profile**) or aim to achieve (**Target Profile**). The difference is the **gap analysis**.
- **Tiers:** four levels describing how rigorous an organization's practices are (Partial, Risk Informed, Repeatable, Adaptive).
- **Relationship to ISO 27001:** ISO 27001 is a certifiable management system with controls. CSF is a flexible outcome framework. ISO gives the management system and controls, and CSF gives a common language and a way to measure outcomes.

### 7.4 CSF profile and gap analysis

Files: [`csf-profile.xlsx`](04-nist-csf/csf-profile.xlsx), [`csf-profile.md`](04-nist-csf/csf-profile.md), [`gap-analysis.md`](04-nist-csf/gap-analysis.md)

**Scale (0 to 4).** Modelled on the CSF Tiers but applied per subcategory.

| Score | Meaning |
|---|---|
| 0 | Not in place |
| 1 | Partial: ad hoc, or planned only |
| 2 | Risk informed: exists informally or partly documented |
| 3 | Repeatable: documented, approved and applied consistently |
| 4 | Adaptive: measured, enforced by tooling and continuously improved |

**How scores were set.**

- **Current:** where Annex A controls map to the subcategory, the score is the average of their SoA statuses (Planned = 1, Partially implemented = 2, Implemented = 3). Where no control applies, the score is a judgment based on what Parts 1 and 2 actually produced, with the reason written next to it.
- **Target:** 3 by default. 4 for authentication (PR.AA-03), privileged access (PR.AA-05) and backups (PR.DS-11), because they drive the Critical risks. Lower or 0 where an outcome is out of scope or disproportionate for a 12-person company.
- **Priority:** P1 = gap of 3, or gap of 2 or more with two or more Critical risks linked. P2 = gap of 2 or more with one Critical risk linked. P3 = other gaps.

**Results.** 104 of 106 subcategories are in scope (PR.PS-06 secure software development and DE.CM-02 physical monitoring are out of scope). The average current score is **1.3** against a target of **3.0**.

| Function | In scope | Avg current | Avg target | Avg gap | Open gaps | P1 | P2 | P3 |
|---|---|---|---|---|---|---|---|---|
| Govern | 31 | 1.4 | 2.9 | 1.5 | 31 | 3 | 1 | 27 |
| Identify | 21 | 1.4 | 3.0 | 1.6 | 21 | 3 | 3 | 15 |
| Protect | 21 | 1.4 | 3.1 | 1.7 | 19 | 9 | 5 | 5 |
| Detect | 10 | 1.1 | 3.0 | 1.9 | 10 | 2 | 2 | 6 |
| Respond | 13 | 1.0 | 2.9 | 1.9 | 13 | 1 | 1 | 11 |
| Recover | 8 | 1.1 | 2.9 | 1.8 | 8 | 1 | 2 | 5 |
| **Total** | 104 | 1.3 | 3.0 | 1.7 | 102 | 19 | 14 | 69 |

**Respond** has the lowest average current score (1.0) and the largest average gap (1.9). Scores are similar across functions because the whole ISMS is being built at once, so the priority ranking, not the averages, shows where to start.

**Roadmap.** The 28 treatment actions fall into three phases by target date: **Phase 1** by end of February 2027 (9 actions: authentication, privileged access, leavers, personal devices, policy set), **Phase 2** in March and April 2027 (15 actions: backups, network baseline, logging and incident response, suppliers, vulnerability management, and the Canadian compliance items), and **Phase 3** in May and June 2027 (4 actions: runbooks, onboarding baseline, evidence handling, internal audit). The full roadmap and the list of P1 outcomes are in [`gap-analysis.md`](04-nist-csf/gap-analysis.md).

### 7.5 Canadian baseline controls

File: [`cccs-baseline-mapping.md`](03-iso27001-mapping/cccs-baseline-mapping.md)

The Canadian Centre for Cyber Security publishes baseline cyber security controls for small and medium organizations (13 controls, BC.1 to BC.13). Clinics and insurers recognize them. The document says the baseline is meant for organizations whose potential injury from a breach is at or below "medium" and points organizations with higher risk to frameworks such as NIST CSF or ISO 27001. IT@serve handles patient health data and has privileged access to many clinics, so it works to ISO 27001 and CSF and treats the baseline as a **minimum** that clinics will expect. The mapping file links each baseline control to Annex A, CSF 2.0 and IT@serve's actions, and shows where IT@serve goes further.

## 8. Reading the codes

| Code | Meaning | Where defined |
|---|---|---|
| O1 to O6 | Business objectives | `company-profile.md` |
| A-01 to A-24 | Assets | `asset-register.xlsx` |
| R-01 to R-16 | Risks | `risk-register.xlsx` |
| TP-01 to TP-28 | Treatment actions | `risk-treatment-plan.md` |
| 5.1 to 8.34 | ISO/IEC 27001:2022 Annex A controls | `statement-of-applicability.xlsx` |
| GV, ID, PR, DE, RS, RC with category and number (for example PR.AA-03) | NIST CSF 2.0 subcategories | `csf-profile.xlsx` |
| BC.1 to BC.13 | Canadian baseline cyber security controls | `cccs-baseline-mapping.md` |
| RRA, LR, CO, BP | Reasons for selecting a control: risk assessment, legal or regulatory, contractual, business or good practice | `statement-of-applicability.xlsx` |
| P1, P2, P3 | Priority of an action or a CSF gap | `risk-treatment-plan.md`, `csf-profile.xlsx` |

## 9. Assumptions and limitations

- The company operates in **Canada** and serves clinics in several provinces. The legal summary covers the main federal and provincial rules and should be narrowed to the provinces actually served.
- All money values are in Canadian dollars (CAD).
- Tool names are kept generic (for example "RMM platform") so the project does not depend on a specific vendor.
- Scores, dates, statuses and costs are illustrative judgments for a fictional company, not measured data. A real profile needs evidence such as policies, screenshots and test records.
- The Annex A to CSF mapping is my own analysis, not NIST's official mapping.
- Links between CSF subcategories and actions come from the control mapping, so broad outcomes (for example GV.PO-01) list many actions.
- The legal summary is not legal advice and may change.

## 10. Revision history

| Version | Date | Change |
|---|---|---|
| 0.1 | Nov 2026 | First draft of Part 1 |
| 0.2 | Nov 2026 | Parts 2 and 3 built (risk assessment, SoA, crosswalk, CSF profile) |
| 0.3 | Nov 2026 | Part 1 revised for a Canadian focus: legal summary, chairs explained, objectives O5 and O6, data residency view |
| 0.4 | Nov 2026 | Part 2 revised for a Canadian focus: risks R-15 and R-16, stronger R-10, two new assets, hosting-region columns, TP-27 and TP-28, CAD impact scale |
| 0.5 | Nov 2026 | Part 3 refreshed: SoA and CSF profile rebuilt for 16 risks and 28 actions, Canadian baseline controls mapping, gap analysis and roadmap updated |
| **0.6** | **Nov 2026** | **The three READMEs merged into this single README** |

## 11. Ideas for further work

1. Compare the Annex A to CSF crosswalk with NIST's official mapping and note where they differ.
2. Replace the "To confirm" hosting regions in the asset register with real vendor facts for a chosen set of tools.
3. Narrow the legal summary to the provinces served and have it reviewed by a privacy professional.
4. Add evidence for each CSF score (policies, screenshots, test records).

*Version 0.6, November 2026*
