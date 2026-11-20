# Risk Treatment Plan: IT@serve Company

*Supports ISO/IEC 27001:2022 clause 6.1.3. Fictional Canadian organization. Part 2 of 3 (updated in Part 3). Version 0.3 (revised for a Canadian focus), November 2026.*

## 1. Summary

The assessment identified **16 risks**: 5 Critical, 7 High and 4 Medium before treatment (see `risk-register.xlsx`). With the planned actions complete, all risks fall to **Medium or Low**, within the appetite set in `risk-methodology.md`. The plan has **28 actions**.

| Treatment option | Risks |
|---|---|
| Reduce | R-01, R-02, R-04, R-05, R-07, R-08, R-09, R-10, R-11, R-12, R-15, R-16 |
| Reduce + Transfer | R-03, R-06 |
| Avoid | R-14 |
| Accept | R-13 |

| Rating | Inherent | Residual (planned) |
|---|---|---|
| Critical | 5 | 0 |
| High | 7 | 0 |
| Medium | 4 | 13 |
| Low | 0 | 3 |

| Actions by priority | P1 | P2 | P3 |
|---|---|---|---|
| 28 actions | 14 | 12 | 2 |

## 2. Priority actions

Priority follows the highest inherent rating of the risks each action addresses: **P1** = Critical, **P2** = High, **P3** = Medium.

TP-27 and TP-28 were added in the Canadian revision (v0.3). TP-18 to TP-26 are in section 6.

| ID | Action | Risks | Annex A | Owner | Priority | Target | Evidence of completion | Status |
|---|---|---|---|---|---|---|---|---|
| TP-01 | Enforce phishing-resistant MFA (e.g. FIDO2 security keys) on RMM, remote access, password manager and M365 admin accounts | R-01, R-02, R-14 | 5.17, 8.5 | Systems / Network Engineer | P1 | 2027-01-31 | MFA enforcement report from each tool | Planned |
| TP-02 | Restrict RMM and remote access by IP allowlist or conditional access; split RMM policies per client to limit blast radius | R-01 | 5.15, 8.2, 8.9, 8.20 | Systems / Network Engineer | P1 | 2027-02-28 | Config screenshots, policy list | Planned |
| TP-03 | Require approval and alerting for mass or global script deployment in the RMM | R-01, R-08 | 8.4, 8.15, 8.16, 8.32 | Operations Manager | P1 | 2027-02-28 | Change procedure, alert rule test | Planned |
| TP-04 | Run security awareness training at onboarding and quarterly phishing simulations | R-02, R-08 | 6.3 | Security and Compliance Lead | P1 | 2027-02-28 | Training records, simulation results | Planned |
| TP-05 | Add an immutable or offline backup copy for every clinic; run and record restore tests each quarter | R-03 | 5.29, 5.30, 8.13, 8.14, 8.33 | Systems / Network Engineer | P1 | 2027-03-31 | Restore test reports per clinic | Planned |
| TP-06 | Review cyber insurance cover and conditions (risk transfer) | R-03, R-06 | 5.31 | CEO | P1 | 2027-02-15 | Policy review memo | Planned |
| TP-07 | Enable full-disk encryption and device management on all company laptops; mandatory screen lock | R-04, R-14 | 7.9, 8.1, 8.24 | Systems / Network Engineer | P1 | 2027-02-28 | Device compliance report | Planned |
| TP-08 | Write an information classification and handling procedure; apply least privilege to client data | R-04 | 5.12, 5.13, 5.14, 8.3, 8.12 | Security and Compliance Lead | P2 | 2027-03-31 | Approved procedure, access list | Planned |
| TP-09 | Create a joiner-mover-leaver process with same-day access revocation; quarterly access reviews; remove shared admin accounts | R-05 | 5.16, 5.18, 6.5, 8.2 | Operations Manager | P1 | 2027-01-31 | Process document, first review record | Planned |
| TP-10 | Build a supplier register that records each supplier's hosting region and cross-border status; do security due diligence, contract clauses, annual review and exit plans for critical suppliers | R-06, R-15 | 5.19 to 5.23 | Operations Manager | P2 | 2027-04-30 | Supplier register with hosting regions, review records | Planned |
| TP-11 | Define a patch policy with SLAs; run monthly vulnerability scans; keep an exception register with compensating controls for legacy imaging systems | R-07 | 5.9, 8.8, 8.9, 8.22, 8.34 | Systems / Network Engineer | P2 | 2027-03-31 | Policy, scan reports, exception register | Planned |
| TP-12 | Log privileged remote sessions; require peer review of scripts; apply segregation of duties; confirm screening and NDAs | R-08 | 5.3, 6.1, 6.2, 6.6, 8.15 | Security and Compliance Lead | P2 | 2027-04-30 | Logging config, signed NDAs | Planned |
| TP-13 | Write runbooks for every clinic; cross-train staff; assign a backup technician per client | R-09 | 5.2, 5.37, 6.3 | Operations Manager | P3 | 2027-05-31 | Runbook coverage list | Planned |
| TP-14 | Create a Canadian legal and contractual requirements register (federal and provincial), a breach-notification procedure with clinic notice timelines, and a breach record kept for at least 24 months | R-10, R-16 | 5.26, 5.31, 5.33, 5.34 | Security and Compliance Lead | P2 | 2027-03-31 | Register, breach procedure, breach record template | Planned |
| TP-15 | Centralize logs and alerts; write an incident response plan; hold an annual tabletop exercise; evaluate outsourced 24x7 monitoring | R-11 | 5.24 to 5.27, 6.8, 8.15, 8.16 | Security and Compliance Lead | P2 | 2027-04-30 | IR plan, tabletop report, alert tests | Planned |
| TP-16 | Create a standard clinic onboarding and offboarding checklist with a security baseline | R-12 | 5.8, 5.37, 8.9 | Operations Manager | P3 | 2027-05-31 | Checklist used for next 3 clinics | Planned |
| TP-17 | Prohibit privileged client access from personal or unmanaged devices; enforce with conditional access | R-14 | 5.10, 6.7, 8.1, 8.5 | Security and Compliance Lead | P1 | 2027-01-31 | Policy, conditional access rule | Planned |
| TP-27 | Review Canadian data residency: record the hosting region of every tool, move backups and the M365 tenant to Canadian regions where offered, run a transfer assessment for clinics in Québec, and tell clinics which vendors and regions are used | R-15 | 5.23, 5.34 | Operations Manager | P2 | 2027-03-31 | Hosting-region register, transfer assessment, client notice | Planned |
| TP-28 | Create a clinic agreement pack with province-specific schedules (for example information manager terms in Alberta, agent or electronic service provider terms in Ontario, Québec outsourcing terms) and a go-live gate: no access to a clinic's systems until the agreement is signed | R-10, R-16 | 5.31, 5.34, 5.37 | Security and Compliance Lead | P2 | 2027-03-31 | Agreement pack, signed agreements for existing clients | Planned |

## 3. Accepted risk

| Risk | Residual rating | Reason | Compensating measure | Approved by | Review |
|---|---|---|---|---|---|
| R-13 Outage of internal ticketing (PSA) platform | Medium (6) | Cost of redundancy exceeds the impact; short outages only slow work | Phone and email fallback; vendor SLA and status monitoring | CEO (Operations Manager as risk owner) | 2027-11-30 |

## 4. Residual risk approval

| Item | Detail |
|---|---|
| Residual position | 13 Medium, 3 Low, none High or Critical |
| Condition | Residuals are valid only when the actions above are **implemented and effective**. Until then, inherent ratings apply |
| Approval | CEO sign-off required on this plan (fictional: *pending*) |
| Next review | After TP-01 to TP-09 are complete, or within 6 months |

## 5. Dependencies and notes

- The **Statement of Applicability** in Part 3 takes the Annex A controls from this plan and justifies each included or excluded control.
- Budget and resourcing are not modeled. A real plan would add costs and dependencies.
- Dates are illustrative.
- **Canadian legal items** (TP-14, TP-27, TP-28) depend on confirming the rules for each province served. A real organization would involve a lawyer or privacy professional. See `../01-scope-and-context/isms-scope.md`, section 4.

## 6. Actions added while building the Statement of Applicability (Part 3)

Mapping all 93 Annex A controls showed areas the first risk-driven pass did not cover. These nine actions close those gaps. The Annex A references in TP-02, TP-03, TP-05, TP-08, TP-11, TP-12 and TP-16 were also completed (5.8, 5.13, 5.15, 5.29, 6.2, 8.4, 8.12, 8.33, 8.34).

| ID | Action | Risks | Annex A | Owner | Priority | Target | Evidence of completion | Status |
|---|---|---|---|---|---|---|---|---|
| TP-18 | Approve a policy set: information security policy plus topic policies (access control, acceptable use, remote working, clear desk and screen, disciplinary process) | R-09, R-12, R-14 | 5.1, 5.2, 5.4, 5.10, 6.4, 6.7, 7.7 | CEO | P1 | 2027-02-28 | Signed policies, staff acknowledgements | Planned |
| TP-19 | Set up an internal audit and management review programme, with an independent review before any certification audit | R-10, R-12 | 5.35, 5.36 | Security and Compliance Lead | P2 | 2027-06-30 | Audit plan, first internal audit report | Planned |
| TP-20 | Define physical and equipment security rules for the office and staging area: entry control, locked storage, asset return, certified wiping of returned clinic drives | R-04, R-05 | 5.11, 7.1, 7.2, 7.3, 7.5, 7.8, 7.10, 7.13, 7.14 | Operations Manager | P1 | 2027-04-30 | Procedure, disposal and wipe certificates | Planned |
| TP-21 | Write a cryptography standard covering disk encryption, TLS, encrypted backups and secret handling | R-04 | 8.24 | Systems / Network Engineer | P2 | 2027-03-31 | Approved standard, encryption status report | Planned |
| TP-22 | Create a records retention and deletion schedule for client data in backups, tickets and session logs | R-04, R-10 | 5.33, 8.10 | Security and Compliance Lead | P2 | 2027-04-30 | Schedule, deletion record for a leaving client | Planned |
| TP-23 | Set up security contacts and threat information sources (authorities, vendor advisories, MSP and dental sector alerts) | R-01, R-03, R-11 | 5.5, 5.6, 5.7 | Security and Compliance Lead | P1 | 2027-03-31 | Contact list, subscribed sources, monthly threat note | Planned |
| TP-24 | Create a network and endpoint protection baseline: segmentation of clinical, imaging and guest networks, DNS/web filtering, time sync, EDR on all managed clinic servers | R-02, R-03, R-07, R-11 | 8.7, 8.17, 8.20, 8.21, 8.22, 8.23 | Systems / Network Engineer | P1 | 2027-03-31 | Baseline document, per-clinic compliance check | Planned |
| TP-25 | Control tool acquisition and software use: security checklist for new tools, licence tracking, control of privileged utilities and software installs | R-01, R-06, R-07 | 5.32, 8.18, 8.19, 8.26 | Operations Manager | P1 | 2027-04-30 | Checklist, licence register, allowed-software list | Planned |
| TP-26 | Define incident evidence handling and log retention so evidence can be shared with clients, insurers and authorities | R-11 | 5.28 | Security and Compliance Lead | P2 | 2027-06-30 | Evidence procedure, retention settings | Planned |

Several of these (TP-18, TP-19, TP-20, TP-22) are standard ISMS foundations that an auditor expects even when no single risk demands them.

## 7. Revision notes (v0.3, Canadian focus)

| Change | Where |
|---|---|
| New risks R-15 (data hosted outside Canada) and R-16 (missing provincial service-provider agreements) | `risk-register.xlsx` |
| R-10 strengthened: Canadian breach duties, 24-month breach record, prompt notice to clinics | `risk-register.xlsx`, TP-14 |
| Supplier work records hosting region and cross-border status | TP-10, `asset-register.xlsx` |
| New actions TP-27 (data residency review) and TP-28 (clinic agreement pack and go-live gate) | This plan |
| Impact scale in CAD with Canadian breach-reporting thresholds | `risk-methodology.md`, `risk-register.xlsx` |
