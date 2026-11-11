
## Overview
This project demonstrates the development of a Governance, Risk and Compliance (GRC) program for a fictional Canadian Managed Service Provider (MSP) serving dental clinics.

Key Deliverables
* Built a GRC program aligned to ISO/IEC 27001:2022 and NIST Cybersecurity Framework (CSF) 2.0.
* Defined the ISMS scope, context and interested parties, and summarized Canadian legal requirements (PIPEDA, provincial health-information laws, Québec Law 25, breach-notification and record-keeping duties) that shape the program.
* Classified information assets, including patient health data and privileged client credentials, and mapped data flows and cross-border hosting concerns.
* Conducted an asset-based risk assessment using a 5x5 likelihood-impact methodology, producing a risk register of 14 risks, a 22-asset inventory and a heat map of risk before and after treatment.
*  Developed a risk treatment plan with 26 prioritized actions mapped to ISO 27001 Annex A controls and NIST CSF categories, with owners, target dates and evidence of completion.
*  Produced a Statement of Applicability covering all 93 ISO 27001:2022 Annex A controls (82 applicable, 11 excluded with justification), tied back to the risk assessment.
* Built an ISO 27001 to NIST CSF 2.0 crosswalk, scored all 106 CSF subcategories for current and target profiles, and produced a gap analysis with a phased roadmap.

# IT@serve Company: GRC Personal Project

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
| **1** | Scope and context | `README.md`, company profile, ISMS scope, services and data flow | `01-scope-and-context/` | **COMPLETED** |
| **2** | Risk assessment | Risk methodology, risk register, asset register, risk treatment plan | `02-risk-assessment/` | **IN-Progress** |
| **3** | Controls, frameworks and gaps | Statement of Applicability, Annex A to CSF crosswalk, CSF profile, gap analysis, updated risk treatment plan | `03-iso27001-mapping/` and `04-nist-csf/` |  **IN-Progress** |

The risk treatment plan lives in Part 2 and is updated in Part 3, where the Statement of Applicability added actions TP-18 to TP-26.

### Why this order

Each part feeds the next. A change in Part 1 (for example the Canadian focus) flows into the risks and assets in Part 2, and then into the controls and profile in Part 3. Revising in order avoids rework.

## Repository structure

```
grc-project/
├── README.md                         (Part 1)
├── 01-Scope-and-Context/             (Part 1)
│   ├── Company-Profile.md
│   ├── ISMS-Scope.md
│   └── Services-and-Data-Flow.md
├── 02-Risk-Assessment/               (Part 2)
│   ├── Risk-Methodology.md
│   ├── Asset-Register.xlsx
│   ├── Risk-Register.xlsx
│   └── Risk-Treatment-plan.md        (Part 3)
├── 03-ISO27001-Mapping/              (Part 3)
│   ├── README.md
│   ├── Statement-of-Applicability.xlsx / .md
│   └── AnnexA-to-csf-Crosswalk.xlsx / .md
└── 04-NIST-CSF/                      (Part 3)
    ├── README.md
    ├── CSF-Profile.xlsx / .md
    └── Gap-Analysis.md
```

## How to read this project

1. Part 1: start with `01-scope-and-context/isms-scope.md` for the organization, the Canadian legal context and what is in scope.
2. Part 2: read `02-risk-assessment/risk-methodology.md`, then open `risk-register.xlsx`.
3. Part 3: read `03-iso27001-mapping/README.md` for the Statement of Applicability and crosswalk, then `04-nist-csf/gap-analysis.md` for the roadmap.

Spreadsheets (`.xlsx`) are the working files. GitHub does not preview them, so key tables are also provided as Markdown.

## Key results (current state of Parts 2 and 3, before their Canadian revision)

| Area | Result |
|---|---|
| Assets | 22 assets rated for confidentiality, integrity and availability |
| Risks | 14 risks: 5 Critical, 6 High, 3 Medium before treatment; none above Medium after |
| Treatment plan | 26 actions with owners, priorities, dates and evidence |
| Statement of Applicability | 82 of 93 Annex A controls applicable, 11 excluded with justification |
| Crosswalk | 93 Annex A controls mapped to NIST CSF 2.0, with coverage by function |
| NIST CSF 2.0 profile | 106 subcategories scored; average maturity 1.3 now, target 3.0; 20 P1 priorities |

## Assumptions

- The company operates in **Canada** and serves clinics in several provinces. The legal summary in `01-scope-and-context/isms-scope.md`, section 4, covers the main federal and provincial rules and should be narrowed to the provinces actually served.
- All money values are in Canadian dollars (CAD).
- Tool names are kept generic (e.g. "RMM platform") so the project does not depend on a specific vendor.
- Scores, dates and costs are illustrative judgments, not measured data.
- The Annex A to CSF mapping is my own analysis, not NIST's official mapping.


### Carry-forward to Part 2

Part 1 changes that Part 2 must pick up:

1. Add risks for cross-border hosting of patient data (theme 11) and missing provincial service-provider agreements (theme 12) to the risk register.
2. Strengthen risk R-10 (legal and breach-notification duties) and action TP-14: legal register, 24-month breach record, prompt notice to clinics.
3. Add hosting region and cross-border status to the supplier work (TP-10) and the asset register.
4. Show impact values in the methodology in **CAD**.
5. Add the dental regulatory colleges and privacy commissioners as sources of requirements.

*Version 0.3, November 2026*
