# THE MANUAL — Topic Map (Series 3 / Tier 3)

*Reduced to Sums & Differences · The hands-on working volume of the Principles Cyber set*

**Position in the set.** Principles (Books I–III) carries the *why*. The Standards carries what is *fixed* — law, reference, glossary. **The Manual carries the *work*.** It is not an exam prep book and not a question bank; it is the field manual for doing authorized cyber work — red and blue — competently. MCQs appear only as a **psychometric sharpener** (Domain 13), a tool to harden recall between hands-on modules, never the training itself.

**Design rules carried from the companion chemistry series.** Every module front-loads the source method/formula and *what varies*; concepts the job punishes you for missing get worked triples (worked → variant → your turn, increasing depth); no filler; definitions pooled to the Standards glossary; authorized/ethical framing throughout (scope, ROE, legality stated before any offensive technique).

**Granularity key:** `Domain → Module → Topic → subtopic`.

---

## DOMAIN 0 — Orientation, Ethics & The Lab

**0.1 The practitioner's method**
- The vector method: identify vector → run aggregate steps → note what varies
- Reading a problem as a *family*, not a novelty (junior vs senior)
- How this volume maps back to Principles & Standards (cross-reference spine)

**0.2 Law, ethics & authorization**
- Authorized vs unauthorized: the line that separates a professional from a criminal
- Scope, Rules of Engagement (ROE), get-out-of-jail letters, written permission
- Nigeria & international legal context: Cybercrimes Act (Nigeria, 2015), NDPR/NDPA, CFAA (US), Computer Misuse (UK) — jurisdiction awareness
- Responsible disclosure & bug-bounty norms
- Handling real data: minimization, confidentiality of client findings

**0.3 Building a safe lab (low-resource friendly)**
- Isolation first: host-only networks, VMs, snapshots, never test on production or others' systems
- Offline/low-bandwidth lab options (pre-downloaded VMs, local vulnerable targets) — built for slow-network realities
- Lab targets: intentionally vulnerable apps/VMs for *authorized self-practice*
- Virtualization basics (hypervisor, networking modes, snapshots/rollback)
- Note-keeping & evidence discipline from day one

**0.4 The toolkit map (categories, not weaponization)**
- Tool families by job: discovery, analysis, capture, monitoring, forensics
- Choosing the right category for the vector; why tools are interchangeable within a family

---

## DOMAIN 1 — Networking in Practice (ground truth)

**1.1 The models, applied**
- OSI vs TCP/IP mapped to real packets
- Encapsulation/decapsulation traced end to end
- "Where does this attack live?" — layer location drill

**1.2 Addressing & subnetting (worked triples)**
- IPv4 structure, CIDR, masks
- Usable-hosts / network / broadcast / range calculations
- Subnet design from host requirements
- IPv6 essentials (addressing, why it changes recon)
- VLANs & segmentation rationale

**1.3 Core protocols on the wire**
- DNS (resolution flow, record types, DoH/DoT, tunneling as a defensive signal)
- DHCP (lease flow, rogue-server risk)
- ARP (resolution, spoofing as a concept, defenses)
- HTTP/HTTPS (methods, status families, headers that matter for security)
- TLS handshake traced (ClientHello → cert → key exchange → finished)
- SMB, LDAP, SMTP, SNMP, RDP, SSH — purpose, port, secure form, exposure risk

**1.4 Packet analysis**
- Reading a capture (Wireshark/tcpdump) — filters, following streams
- Recognizing normal vs anomalous flows
- What plaintext leaks and what TLS hides

**1.5 The troubleshooting ladder**
- Layer-by-layer isolation of a connectivity/security fault
- "Is it reachable / resolving / listening / permitted / responding?" sequence

---

## DOMAIN 2 — Operating Systems for Defenders & Testers

**2.1 Linux fluency**
- Filesystem hierarchy, permissions (rwx, SUID/SGID, ownership)
- Processes, services, systemd, cron/scheduled jobs
- Users/groups, sudo, PAM basics
- Logs & their locations (auth, syslog, journald)
- Shell fluency: pipes, redirection, grep/awk/sed for log triage
- Package management & integrity

**2.2 Windows & Active Directory fluency**
- Users, groups, privileges, UAC
- Registry, services, scheduled tasks
- Event logs (security/system/application) & key event IDs
- PowerShell basics for administration and investigation
- Active Directory structure: domains, OUs, GPO, trusts
- SMB/shares, NTLM vs Kerberos

**2.3 Hardening baselines**
- CIS Benchmarks applied
- Attack surface reduction (disable, remove, restrict)
- Patch & configuration management in practice

---

## DOMAIN 3 — Identity, Authentication & Access (deep)

**3.1 AuthN vs AuthZ vs Accounting — applied**
**3.2 Factors & modern auth**
- Know/have/are; MFA in practice; push-fatigue/MFA-bypass awareness
- FIDO2 / passkeys / WebAuthn — why phishing-resistant
**3.3 Kerberos in depth**
- KDC, TGT, service tickets — full flow traced
- Why tickets not passwords cross the wire; common AD attack surface (conceptual/defensive)
**3.4 Federation flows traced**
- SAML (IdP/SP, signed assertion) — enterprise SSO
- OAuth 2.0 (authorization, tokens, scopes, grant types)
- OIDC (ID token, the identity OAuth lacks)
- The OAuth-is-not-authentication trap
**3.5 PKI & certificates**
- CA hierarchy, chains of trust, revocation (CRL/OCSP)
- Certificate lifecycle & management
- Reading/validating a cert; common cert failures
**3.6 Access models in practice**
- RBAC/ABAC design; least privilege as an operational habit
- Joiner/mover/leaver; privilege creep; access reviews

---

## DOMAIN 4 — Cryptography, Applied

**4.1 The three routes in use** (symmetric / asymmetric / hashing — operational choices)
**4.2 Choosing current vs legacy** (what to use, what to retire — ref the Standards crypto table)
**4.3 TLS in depth** (versions, cipher suites, forward secrecy, misconfig)
**4.4 Password & secret storage** (salting, bcrypt/scrypt/Argon2, pepper, why fast hashes fail)
**4.5 Key & secret management** (rotation, vaults, secrets-in-code as a top real-world failure)
**4.6 Common crypto mistakes** (ECB, reused IV/nonce, rolling your own, hardcoded keys)

---

## DOMAIN 5 — Red Team / Offensive (authorized)

**5.1 The engagement as a contract** (scope, ROE, authorization, deliverable-first mindset)
**5.2 The lifecycle (PTES / NIST SP 800-115) end to end**
**5.3 Reconnaissance & OSINT**
- Passive vs active; footprinting an *authorized* target
- Public exposure mapping; what leaks about an organization
**5.4 Scanning & enumeration**
- Host discovery, service/version identification, banner reading
- Translating findings into a prioritized surface
**5.5 Vulnerability identification & validation**
- From scanner output to a *validated* finding (false-positive discipline)
- Mapping to CVE/CWE; scoring with CVSS
**5.6 Web application testing (methodology)**
- OWASP families as a test plan: access control, injection, auth, misconfig, etc.
- Authenticated vs unauthenticated testing; business-logic flaws
**5.7 Network & infrastructure testing (methodology)**
**5.8 Specialized surfaces (conceptual, strict ROE)**
- Wireless, cloud, mobile, social engineering/phishing simulation — consent & limits
**5.9 Post-exploitation *concepts* (for defensive understanding & reporting)**
- Privilege escalation, lateral movement, persistence, exfiltration — what they *demonstrate* about a gap, framed for the report and for blue-team detection, not as attack recipes
**5.10 Reporting — the real product**
- Finding structure: evidence, risk, business impact, remediation
- Ranking by CVSS + context; executive vs technical write-ups
- Retest & closure

---

## DOMAIN 6 — Blue Team / Defensive Operations

**6.1 SOC structure & roles** (tiers, escalation, shift discipline)
**6.2 Telemetry & logging**
- What to collect, where, retention; the "no logs, no investigation" rule
- Endpoint, network, identity, cloud log sources
**6.3 SIEM & detection engineering**
- Ingest → parse → correlate → alert
- Writing & reading detections; Sigma rules; tuning out noise
- Detection-as-code mindset
**6.4 Alert triage (worked method)**
- Scope → correlate → classify → act; false-positive vs true-positive
- Tempo as the signal machine-speed attackers can't hide (ties to Book III)
**6.5 Threat hunting**
- Hypothesis-driven hunting; ATT&CK-mapped gaps; IOCs vs behaviors
**6.6 Endpoint defense** (EDR, baselining, process/parent-child anomalies)
**6.7 Network defense** (IDS/IPS, segmentation, egress filtering, DNS monitoring)
**6.8 Email & phishing defense** (filtering, SPF/DKIM/DMARC, user reporting)

---

## DOMAIN 7 — Incident Response & Recovery

**7.1 The NIST SP 800-61 cycle applied** (prepare → detect/analyze → contain → eradicate → recover → post-incident)
**7.2 Preparation** (playbooks, tooling, logging, comms, retainers — the phase that decides the rest)
**7.3 Playbooks per incident vector**
- Phishing / BEC, ransomware, account/identity compromise, data exfiltration, insider, web compromise
**7.4 Containment decisions** (isolate vs observe; short- vs long-term; evidence vs speed trade-off)
**7.5 Evidence & forensics basics**
- Acquisition, chain of custody, volatile-data order
- Host artifacts (Windows/Linux), timeline building
- Memory & disk basics; when to call specialists
**7.6 Recovery & verification** (known-good restore, watch for re-entry)
**7.7 Post-incident** (lessons learned → back into Preparation; metrics: MTTD/MTTR)
**7.8 Tabletop exercises** (running and learning from them)

---

## DOMAIN 8 — Threat Intelligence & Adversary Emulation

**8.1 ATT&CK applied** (mapping observed activity, finding detection gaps)
**8.2 Threat actor profiles & TTPs** (commodity vs targeted vs APT; motivation → method)
**8.3 Indicators vs behaviors** (why behavior-based detection outlasts IOC lists)
**8.4 Purple teaming** (red+blue collaboration; detection validation)
**8.5 AI-era threats (ties to Book III / ARTEX)**
- Agentic attack frameworks: what changes (speed/scale), what doesn't (the vulns)
- Triaging machine-speed activity; detecting on tempo
- Defender's AI: automated triage/response, with human oversight

---

## DOMAIN 9 — Cloud & Modern Infrastructure

**9.1 Shared-responsibility model** (what the provider secures vs you)
**9.2 Cloud IAM** (the #1 cloud risk: roles, policies, over-permissioned identities, keys)
**9.3 Common cloud misconfigurations** (public buckets, exposed metadata, open management ports)
**9.4 Containers & Kubernetes basics** (images, secrets, namespaces, RBAC)
**9.5 CI/CD & supply-chain security** (pipeline secrets, dependency integrity, artifact signing)
**9.6 Secrets management at scale** (vaults, short-lived credentials, managed identities)

---

## DOMAIN 10 — Application & Secure Development

**10.1 OWASP Top Ten in depth** (per family: what it is → how it's found → how it's fixed)
**10.2 Secure SDLC & threat modeling** (STRIDE, data-flow diagrams, abuse cases)
**10.3 Input handling & output encoding** (trust boundaries, validation vs sanitization)
**10.4 Session & token management**
**10.5 API security** (authz per request, rate limits, mass-assignment, BOLA/IDOR)
**10.6 Dependency & supply-chain hygiene** (SBOM, pinning, known-vuln components)

---

## DOMAIN 11 — Governance, Risk & Compliance (real-world)

**11.1 Risk assessment & math** (likelihood × impact; SLE/ARO/ALE; qualitative vs quantitative)
**11.2 Frameworks applied** (NIST CSF, ISO 27001 ISMS, CIS Controls — how they're actually used)
**11.3 Policy/standard/procedure hierarchy** (writing and enforcing)
**11.4 Audit & evidence** (control testing, artifacts, continuous compliance)
**11.5 Regulatory landscape** (NDPR/NDPA for Nigeria; GDPR; sector rules like PCI DSS, HIPAA) — scoping obligations
**11.6 Third-party & vendor risk** (supply-chain trust, assessments)

---

## DOMAIN 12 — The Career Layer

**12.1 Certification ladder mapped to domains** (Security+/Network+ → CySA+/PenTest+ → CEH/OSCP → CISSP/GIAC)
**12.2 Home lab & continuous practice** (building, maintaining, documenting)
**12.3 CTFs & write-ups** (as skill-building and portfolio, not as the job itself)
**12.4 Portfolio & evidence of competence**
**12.5 Interview preparation** (the question vectors; "best next step" instincts; whiteboard/scenario reasoning)
**12.6 Specialization paths** (SOC analyst, pentester, DFIR, cloud security, GRC, detection engineer, appsec)

---

## DOMAIN 13 — Assessment & Sharpening (MCQs in their proper place)

> MCQs are **not** the training. They are a *psychometric sharpener* — spaced, low-stakes recall checks that harden what the hands-on modules built. They sit here, deliberately last, to mark that role.

**13.1 What MCQs are good for** (rapid recall of fixed facts: ports, CVSS bands, protocol roles, definitions)
**13.2 What they cannot test** (judgment, method, hands-on competence — the actual point)
**13.3 Spaced-recall drilling** (how to use them between modules without mistaking them for mastery)
**13.4 Scenario/performance items** (the bridge from recall toward judgment — closer to the real work)

---

## CROSS-CUTTING SPINES (threaded through every domain)

- **Authorization & ethics** — stated before any offensive content, every time.
- **The vector method** — identify → aggregate steps → what varies, applied in each domain.
- **Red ⇄ Blue duality** — every offensive topic paired with its detection/defense (the Creeper/Reaper symmetry from Book I).
- **Cross-references** — each module points back to its *why* (Principles) and its *fixed reference* (Standards).
- **Low-resource realism** — offline-capable labs, lightweight tooling, built for slow-network conditions.

---

## OPEN QUESTIONS FOR YOU (before the build)

1. **One volume or split?** This is large. Option: one Manual, or split into **The Manual — Red** and **The Manual — Blue** (Domain 0/1–4/11–13 shared as a common core). 
2. **Depth target per module** — same ~30-page re-handwritten feel as the chemistry notes, per volume? Or deeper, since this is reference-for-work rather than exam revision?
3. **Nigeria-context weighting** — how heavily to foreground NDPR/NDPA and local legal framing vs international.
4. **Any domain to cut or add** — e.g., is OT/ICS or mobile security in scope for your audience?
