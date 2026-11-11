# Company Profile: IT@serve Company

*Fictional organization. Part 1 of 3. Version 0.3 (revised for a Canadian focus), November 2026.*

## 1. Overview

| Item | Detail |
|---|---|
| Name | IT@serve Company |
| Type | Managed Service Provider (MSP), startup |
| Country of operation | **Canada** (Canadian-incorporated; staff based in Canada) |
| Founded | 2024 |
| Target market | Independent and small group **dental clinics in Canada** with **1 to 10 chairs** |
| Staff | 12 employees (+ 2 part-time contractors) |
| Clients | 18 dental clinics in several Canadian provinces, about 220 managed endpoints and 25 servers |
| Working model | Remote-first, small office for equipment staging and storage |
| Revenue model | Monthly per-user / per-device managed service contracts, billed in Canadian dollars (CAD) |

> **What "chairs" means:** in dentistry, a chair is one treatment room (also called an *operatory*). Clinics describe their size by the number of chairs. "1 to 10 chairs" therefore means anything from a solo dentist with a single treatment room to a larger practice with about ten. A clinic of this size usually has no IT staff, a fairly uniform set of systems, and cannot treat patients when IT fails.

## 2. Mission and business objectives

**Mission:** Give Canadian dental clinics reliable, secure and compliant IT so they can focus on patient care.

| # | Objective | Why it matters for security |
|---|---|---|
| O1 | Keep client clinics running with minimal downtime | Availability is critical: no systems means no appointments |
| O2 | Protect patient data handled on client systems | Confidentiality; clinics trust IT@serve with privileged access |
| O3 | Grow from 18 to 40 clinics in 24 months | Larger attack surface, more tenants, more staff |
| O4 | Win larger group-practice clients | Larger clients ask for ISO 27001 or similar evidence |
| O5 | Meet Canadian privacy, health-information and professional record-keeping expectations of clinics | Clinics are legally accountable for patient data and rely on IT@serve to help them comply |
| O6 | Prefer Canadian data residency for client data and backups where practical | Reduces cross-border transfer obligations and simplifies client assurance |

## 3. Canadian context

| Topic | What it means for IT@serve |
|---|---|
| **Who is accountable** | The dental clinic is responsible for patient information. IT@serve acts as its service provider. Depending on the province this role has a legal name (for example "information manager" in Alberta, or "agent" or "electronic service provider" in Ontario) and usually requires a written agreement |
| **Privacy laws** | Federal private-sector law (PIPEDA), provincial private-sector laws (PIPA) (for example in Alberta, British Columbia and Québec) and provincial health-information laws apply in different places. The legal summary is in `isms-scope.md`, section 4 |
| **Breach duties** | Privacy law requires clinics to assess breaches, report and notify when there is a real risk of significant harm, and keep breach records. IT@serve must tell clinics quickly and give them what they need |
| **Professional regulators** | Each province has a dental regulatory college that sets standards for patient records and privacy. Clinics expect their IT provider to support those standards |
| **Cyber guidance** | The Canadian Centre for Cyber Security publishes baseline controls for small and medium organizations that clinics and insurers recognize |
| **Cross-border data** | Many tools are hosted by vendors outside Canada. Some provinces (notably Québec) require an assessment before personal information leaves the province |

> ** "PIPEDA (Personal Information Protection and Electronic Documents Act)" and PIPA (Personal Information Protection Act)** 

## 4. Services

| Service | Description |
|---|---|
| Helpdesk and remote support | Ticketing, remote desktop support for clinic staff |
| Endpoint management | Patching, antivirus/EDR, configuration via RMM platform |
| Network and firewall management | Firewalls, Wi-Fi, VPN, segmentation (clinical vs. guest) |
| Backup and disaster recovery | Daily backups of practice management DB and imaging, restore testing |
| Cloud and email administration | Microsoft 365 tenant admin, MFA, mailbox management |
| Practice software and imaging support | Installation and support of practice management software, X-ray/imaging sensors and viewers |
| Security services | Vulnerability scanning, security awareness training, basic monitoring |
| Onsite visits | Hardware installs, replacements, new clinic onboarding |

## 5. Organization structure

| Role | Headcount | Security-relevant responsibilities |
|---|---|---|
| Founder / CEO | 1 | Top management; approves ISMS policy and risk acceptance |
| Operations Manager | 1 | Service delivery, supplier management |
| Security and Compliance Lead | 1 | Runs ISMS and risk process, internal audits, acts as privacy contact |
| Service desk technicians (L1/L2) | 5 | Privileged access to client systems |
| Field engineers | 2 | Onsite work, physical access to clinics |
| Systems / network engineer | 1 | Builds and maintains tooling, firewalls, backups |
| Sales and onboarding | 1 | Handles client contracts and onboarding data |

## 6. Technology environment (internal)

| Category | Examples of what exists |
|---|---|
| RMM platform | Remote monitoring, scripting, patching of client endpoints |
| PSA / ticketing | Tickets, client contacts, contracts, asset lists |
| Remote access tool | Remote sessions into clinic workstations and servers |
| Password manager | Shared vault of client admin credentials |
| Backup platform | Cloud backup management console for all clients |
| Identity | Company Microsoft 365 tenant with MFA |
| Endpoint security | EDR on staff laptops |
| Documentation | Client network diagrams, configuration notes |
| Staff devices | Company laptops, some personal phones (BYOD) for MFA and email |

> **Why this matters:** the RMM, remote access tool and password manager give access to *every client*. Compromise of one of these is a supply-chain event for all 18 clinics.

## 7. Assumptions and limitations

- No dedicated SOC; monitoring is partly outsourced and partly tool alerts.
- No existing certification; policies are informal. The ISMS is being built from scratch.
- Budget is limited, so controls must be proportionate and justified by risk.
- All money values in this project are in **Canadian dollars (CAD)**.
- Clients are in Canada only. Clinics in other countries are outside this scenario.
- Some tool vendors host data outside Canada. Where this happens it is treated as a risk and a compliance item, not ignored.
