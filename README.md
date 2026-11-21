# IT@serve Company: GRC Project

> **Disclaimer:** IT@serve Company is a **fictional** Canadian organization created for learning and portfolio purposes. All names, numbers and scenarios are invented. Nothing here is legal or compliance advice.

## Scenario

IT@serve Company is a small startup **Managed Service Provider (MSP) based in Canada** that supports **Canadian dental clinics** (1 to 10 chairs, meaning 1 to 10 treatment rooms). It manages clinic IT (workstations, servers, networks, backups, Microsoft 365, practice management software and imaging systems) and has privileged remote access to systems containing **patient health information**. That makes it a high-value target and a critical supplier for its clients. Canadian privacy and health-information law shapes what clinics, and therefore IT@serve, must do.

This project builds a Governance, Risk and Compliance (GRC) program for IT@serve using:

- **ISO/IEC 27001:2022** (ISMS, risk assessment, Annex A controls)
- **NIST Cybersecurity Framework (CSF) 2.0** (Govern, Identify, Protect, Detect, Respond, Recover)

## Project parts

The project is organized in three parts so each can be reviewed and corrected on its own.

| Part | Focus | Files | Folder | Status |
|---|---|---|---|---|
| **1** | Scope and context | `README.md`, company profile, ISMS scope, services and data flow | `01-scope-and-context/` | **Revised for Canada (v0.3)** |
| **2** | Risk assessment | Risk methodology, risk register, asset register, risk treatment plan | `02-risk-assessment/` | **Revised for Canada (v0.3)** |
| **3** | Controls, frameworks and gaps | Statement of Applicability, Annex A to CSF crosswalk, CSF profile, gap analysis, updated risk treatment plan | `03-iso27001-mapping/` and `04-nist-csf/` | To revise next |

The risk treatment plan lives in Part 2 and is updated in Part 3, where the Statement of Applicability added actions TP-18 to TP-26.

### Why this order

Each part feeds the next. A change in Part 1 (for example the Canadian focus) flows into the risks and assets in Part 2, and then into the controls and profile in Part 3. Revising in order avoids rework.

## Repository structure

```
grc-project/
├── README.md                         (Part 1)
├── 01-scope-and-context/             (Part 1)
│   ├── company-profile.md
│   ├── isms-scope.md
│   └── services-and-data-flow.md
├── 02-risk-assessment/               (Part 2)
│   ├── risk-methodology.md
│   ├── asset-register.xlsx
│   ├── risk-register.xlsx
│   └── risk-treatment-plan.md        (updated in Part 3)
├── 03-iso27001-mapping/              (Part 3)
│   ├── README.md
│   ├── statement-of-applicability.xlsx / .md
│   └── annexA-to-csf-crosswalk.xlsx / .md
└── 04-nist-csf/                      (Part 3)
    ├── README.md
    ├── csf-profile.xlsx / .md
    └── gap-analysis.md
```

## How to read this project

1. Part 1: start with `01-scope-and-context/isms-scope.md` for the organization, the Canadian legal context and what is in scope.
2. Part 2: read `02-risk-assessment/risk-methodology.md`, then open `risk-register.xlsx`.
3. Part 3: read `03-iso27001-mapping/README.md` for the Statement of Applicability and crosswalk, then `04-nist-csf/gap-analysis.md` for the roadmap.

Spreadsheets (`.xlsx`) are the working files. GitHub does not preview them, so key tables are also provided as Markdown.

## Key results (Part 2 is current; Part 3 figures will update when it is revised)

| Area | Result |
|---|---|
| Assets | 24 assets rated for confidentiality, integrity and availability, with hosting region and cross-border status |
| Risks | 16 risks: 5 Critical, 7 High, 4 Medium before treatment; none above Medium after |
| Treatment plan | 28 actions with owners, priorities, dates and evidence |
| Statement of Applicability | 82 of 93 Annex A controls applicable, 11 excluded with justification *(Part 3, not yet refreshed)* |
| Crosswalk | 93 Annex A controls mapped to NIST CSF 2.0, with coverage by function |
| NIST CSF 2.0 profile | 106 subcategories scored; average maturity 1.3 now, target 3.0; 20 P1 priorities |

## Assumptions

- The company operates in **Canada** and serves clinics in several provinces. The legal summary in `01-scope-and-context/isms-scope.md`, section 4, covers the main federal and provincial rules and should be narrowed to the provinces actually served.
- All money values are in Canadian dollars (CAD).
- Tool names are kept generic (e.g. "RMM platform") so the project does not depend on a specific vendor.
- Scores, dates and costs are illustrative judgments, not measured data.
- The Annex A to CSF mapping is my own analysis, not NIST's official mapping.

## Revision history

| Version | Date | Change |
|---|---|---|
| 0.1 | Nov 2026 | First draft of Part 1 |
| 0.2 | Nov 2026 | Parts 2 and 3 built (risk assessment, SoA, crosswalk, CSF profile) |
| 0.3 | Nov 2026 | Part 1 revised for a Canadian focus: Canadian context and legal summary, chairs explained, objectives O5 and O6, data residency view, two new risk themes, CAD |
| **0.4** | **Nov 2026** | **Part 2 revised for a Canadian focus:** risks R-15 and R-16 added, R-10 strengthened, two new assets, hosting-region columns, actions TP-27 and TP-28, CAD impact scale with Canadian breach thresholds, register and plan cross-checked |

### Carry-forward to Part 2: done in v0.4

- [x] Risks for cross-border hosting of patient data (R-15) and missing provincial service-provider agreements (R-16)
- [x] R-10 and TP-14 strengthened: legal register, 24-month breach record, prompt notice to clinics
- [x] Hosting region and cross-border status in the asset register and supplier action TP-10
- [x] Impact values in CAD
- [x] Privacy commissioners, health-information laws and dental regulatory colleges listed as sources of requirements

### Carry-forward to Part 3

Part 2 changes that Part 3 must pick up:

1. Refresh Statement of Applicability links and statuses for the new risks (R-15, R-16) and actions (TP-27, TP-28), especially controls 5.19 to 5.23, 5.31, 5.33, 5.34 and 5.37.
2. Recalculate the crosswalk coverage and the CSF profile scores (for example GV.OC-03, GV.SC-04, ID.AM-04) and add the Canadian baseline cyber controls as a reference.
3. Rebuild the gap analysis and roadmap for **28 actions** (TP-27 and TP-28 fall in phase 2).
4. Update the figures in the READMEs of `03-iso27001-mapping/` and `04-nist-csf/` (they still say 14 risks and 26 actions).

*Version 0.4, November 2026*
