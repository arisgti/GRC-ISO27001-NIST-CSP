# CSF 2.0 Gap Analysis: IT@serve Company

*Fictional Canadian organization. Part 3 of 3. Version 0.3 (refreshed after the Canadian revision of Parts 1 and 2), November 2026. Data: `csf-profile.xlsx`.*

## 1. Summary

Of the 106 subcategories, **104 are in scope** (the other 2 are out of scope or accepted: PR.PS-06 secure software development, DE.CM-02 physical monitoring). The average current score is **1.3** against an average target of **3.0**, an average gap of **1.7**. 102 subcategories have an open gap.

| Function | In scope | Avg current | Avg target | Avg gap | Open gaps | P1 | P2 | P3 |
|---|---|---|---|---|---|---|---|---|
| Govern | 31 | 1.4 | 2.9 | 1.5 | 31 | 3 | 1 | 27 |
| Identify | 21 | 1.4 | 3.0 | 1.6 | 21 | 3 | 3 | 15 |
| Protect | 21 | 1.4 | 3.1 | 1.7 | 19 | 9 | 5 | 5 |
| Detect | 10 | 1.1 | 3.0 | 1.9 | 10 | 2 | 2 | 6 |
| Respond | 13 | 1.0 | 2.9 | 1.9 | 13 | 1 | 1 | 11 |
| Recover | 8 | 1.1 | 2.9 | 1.8 | 8 | 1 | 2 | 5 |
| **Total** | 104 | 1.3 | 3.0 | 1.7 | 102 | 19 | 14 | 69 |

- **Respond** has both the lowest average current score (1.0) and the largest average gap (1.9).
- Scores are similar across functions because the whole ISMS is being built at once. The priority ranking, not the averages, shows where to start.
- A score of 1 to 2 everywhere is expected for a young company. A real assessment would also record evidence for each score.

## 2. The 19 P1 subcategories

These have the biggest gap and the most Critical risks linked to them.

| ID | Outcome | Current | Target | Critical risks linked | Actions |
|---|---|---|---|---|---|
| PR.AA-03 | Users, processes, and hardware are authenticated | 1 | 4 | 4 | TP-01, TP-02, TP-09, TP-17 |
| PR.AA-05 | Access permissions, entitlements, and authorizations are managed and enforced, incorporating the principles of least privilege and separation of duties | 1 | 4 | 2 | TP-02, TP-03, TP-08, TP-09, TP-12, TP-25 |
| GV.SC-08 | Relevant suppliers and other third parties are included in incident planning, response, and recovery activities | 0 | 3 | 0 | TP-10, TP-15 |
| RC.RP-06 | The end of incident recovery is declared based on criteria, and incident-related documentation is completed | 0 | 3 | 0 | TP-15 |
| GV.PO-01 | Policy for managing cybersecurity risks is established based on organizational context, cybersecurity strategy, and priorities and is communicated and enforced | 1 | 3 | 4 | TP-02, TP-06, TP-08, TP-13, TP-14, TP-15, TP-16, TP-17, TP-18, TP-28 |
| PR.AA-01 | Identities and credentials for authorized users, processes, and hardware are managed by the organization | 1 | 3 | 4 | TP-01, TP-09, TP-20 |
| PR.IR-01 | Networks and environments are protected from unauthorized logical access and usage | 1 | 3 | 4 | TP-02, TP-11, TP-17, TP-18, TP-24 |
| DE.CM-01 | Networks and network services are monitored to find potentially adverse events | 1 | 3 | 3 | TP-02, TP-03, TP-15, TP-24 |
| PR.AA-04 | Identity assertions are protected, conveyed, and verified | 1 | 3 | 3 | TP-01, TP-17 |
| PR.DS-01 | The confidentiality, integrity, and availability of data-at-rest is protected | 1 | 3 | 3 | TP-05, TP-07, TP-08, TP-14, TP-17, TP-20, TP-21, TP-22, TP-27, TP-28 |
| PR.PS-04 | Log records are generated and made available for continuous monitoring | 1 | 3 | 3 | TP-03, TP-12, TP-15, TP-24 |
| PR.PS-05 | Installation and execution of unauthorized software are prevented | 1 | 3 | 3 | TP-24, TP-25 |
| DE.AE-07 | Cyber threat intelligence and other contextual information are integrated into the analysis | 1 | 3 | 2 | TP-23 |
| GV.SC-05 | Requirements to address cybersecurity risks in supply chains are established, prioritized, and integrated into contracts and other types of agreements with suppliers and other relevant third parties | 1 | 3 | 2 | TP-10, TP-12, TP-24 |
| ID.AM-08 | Systems, hardware, software, services, and data are managed throughout their life cycles | 1 | 3 | 2 | TP-02, TP-11, TP-16, TP-20, TP-22 |
| ID.RA-02 | Cyber threat intelligence is received from information sharing forums and sources | 1 | 3 | 2 | TP-23 |
| ID.RA-03 | Internal and external threats to the organization are identified and recorded | 1 | 3 | 2 | TP-23 |
| PR.AT-01 | Personnel are provided with awareness and training so that they possess the knowledge and skills to perform general tasks with cybersecurity risks in mind | 1 | 3 | 2 | TP-04, TP-13, TP-17, TP-18 |
| RS.CO-02 | Internal and external stakeholders are notified of incidents | 1 | 3 | 2 | TP-14, TP-15, TP-23 |

P1 items by function: Govern 3, Identify 3, Protect 9, Detect 2, Respond 1, Recover 1. The linked actions trace back to the Critical risks in Part 2: RMM compromise (R-01), phishing (R-02), ransomware with weak backups (R-03), lingering privileged access (R-05) and personal-device access (R-14). Items with no Critical risk linked are here because their gap is the largest (a score of 0 against a target of 3), for example supplier involvement in incident response.

## 3. Roadmap

The roadmap uses the target dates of the 28 treatment actions in `02-risk-assessment/risk-treatment-plan.md`.

### Phase 1: by end of February 2027 (9 actions)

Close the doors attackers use most: authentication, privileged access, leavers, personal devices and the policy set.

| Action | What | Priority | Target |
|---|---|---|---|
| TP-01 | Phishing-resistant MFA | P1 | 2027-01-31 |
| TP-09 | Joiner-mover-leaver and access reviews | P1 | 2027-01-31 |
| TP-17 | No privileged access from personal devices | P1 | 2027-01-31 |
| TP-06 | Cyber insurance review | P1 | 2027-02-15 |
| TP-02 | Restrict RMM access, per-client policies | P1 | 2027-02-28 |
| TP-03 | Approval and alerts for mass scripts | P1 | 2027-02-28 |
| TP-04 | Awareness training and phishing simulations | P1 | 2027-02-28 |
| TP-07 | Laptop encryption and device management | P1 | 2027-02-28 |
| TP-18 | Policy set | P1 | 2027-02-28 |

### Phase 2: March and April 2027 (15 actions)

Build resilience and detection (backups, network baseline, logging and incident response, suppliers, vulnerability management) and put the Canadian compliance items in place: legal requirements register, data residency review and the clinic agreement pack with its go-live gate.

| Action | What | Priority | Target |
|---|---|---|---|
| TP-05 | Immutable backups and restore tests | P1 | 2027-03-31 |
| TP-08 | Classification and data handling | P2 | 2027-03-31 |
| TP-11 | Patching and vulnerability management | P2 | 2027-03-31 |
| TP-14 | Legal register, DPA, breach notification | P2 | 2027-03-31 |
| TP-21 | Cryptography standard | P2 | 2027-03-31 |
| TP-23 | Contacts and threat intelligence | P1 | 2027-03-31 |
| TP-24 | Network and endpoint baseline | P1 | 2027-03-31 |
| TP-27 | Canadian data residency review | P2 | 2027-03-31 |
| TP-28 | Clinic agreement pack and go-live gate | P2 | 2027-03-31 |
| TP-10 | Supplier management | P2 | 2027-04-30 |
| TP-12 | Session logging, peer review, screening | P2 | 2027-04-30 |
| TP-15 | Logging, incident response plan, tabletop | P2 | 2027-04-30 |
| TP-20 | Physical and equipment security | P1 | 2027-04-30 |
| TP-22 | Retention and deletion schedule | P2 | 2027-04-30 |
| TP-25 | Tool acquisition and software control | P1 | 2027-04-30 |

### Phase 3: May and June 2027 (4 actions)

Embed and prove: runbooks, onboarding baseline, evidence handling, internal audit.

| Action | What | Priority | Target |
|---|---|---|---|
| TP-13 | Runbooks and cross-training | P3 | 2027-05-31 |
| TP-16 | Clinic onboarding baseline | P3 | 2027-05-31 |
| TP-19 | Internal audit and management review | P2 | 2027-06-30 |
| TP-26 | Evidence handling | P2 | 2027-06-30 |

## 4. Expected result

If the 28 actions are completed and working, each in-scope subcategory should reach its target score. That would take the overall average from about 1.3 to about 3.0 (Repeatable). Residual risk in Part 2 would then be Medium or lower for every risk.

## 5. Limits of this analysis

- Scores are self-assessed and based on a fictional company. A real profile needs evidence such as screenshots, policies and test records.
- The mapping from Annex A to CSF is my own and is not NIST's official mapping.
- Links between subcategories and actions come from the control mapping. Broad outcomes such as GV.PO-01 therefore list many actions, and the count of linked Critical risks is a rough guide to priority, not a precise measure.
- Averages treat every subcategory equally. In practice a few subcategories (authentication, backups) matter much more, which is why the priority ranking is used alongside the averages.
