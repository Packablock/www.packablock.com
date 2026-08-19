---
layout: page
title: EU Cyber Resilience Act (CRA) Compliance Checklist | Packablock
description: Self-assessment checklist for Software Manufacturer Module A conformity under the EU Cyber Resilience Act, aligned with Eclipse Foundation ORC Working Group standards.
permalink: /cra-compliance-checklist/
---

## The Software Manufacturer's Self-Assessment for EU Cyber Resilience Act (CRA)
### Prepared in alignment with the Eclipse Foundation’s Open Regulatory Compliance (ORC) Working Group

Under the EU Cyber Resilience Act (CRA), products with digital elements classified as **"Default / Standard"** (as well as certain qualifying open-source software under Article 32) can demonstrate conformity via **Conformity Assessment Module A (Internal Production Control / Manufacturer Self-Assessment)**. 

This checklist incorporates guidance and standards from the **Eclipse Foundation’s ORC Working Group** alongside its affiliated compliance initiatives (such as the **OCCTET Project** and the **sCC4CRA / Simplified Common Criteria** framework) to help software manufacturers and open-source stewards comply with the CRA.

<div class="download-checklist-container" style="margin: 30px 0; text-align: center;">
  <a href="{{ '/assets/docs/packablock-security-checklist.pdf' | relative_url }}" class="btn-primary" download>
    <svg viewBox="0 0 24 24" width="18" height="18" fill="none" stroke="currentColor" stroke-width="2.5" style="margin-right: 8px; vertical-align: middle;"><path stroke-linecap="round" stroke-linejoin="round" d="M3 16.5v2.25A2.25 2.25 0 005.25 21h13.5A2.25 2.25 0 0021 18.75V16.5M16.5 12L12 16.5m0 0L7.5 12m4.5 4.5V3"></path></svg>
    Download Printable PDF Checklist
  </a>
</div>

---

## 📋 The Five Core Pillars of CRA Self-Assessment

### Pillar 1: Scope, Product Classification & Support Period
Ensure the software product is accurately categorized and its operational support boundaries are formally defined:
* [ ] **Scope Verification**: Confirm whether the software qualifies as a Product with Digital Elements (PDE) having direct or indirect logical or network data connections.
* [ ] **Risk Tiering**: Establish if the product falls under Default/Standard (eligible for pure self-assessment), Important (Class I / Class II), or Critical.
* [ ] **Defined Support Period**: Formally document the guaranteed lifetime during which the manufacturer will provide free security updates (minimum expected lifetime).

---

### Pillar 2: Product Security by Design & Default (Annex I, Part I)
Assess whether cybersecurity controls are built into the architecture from conception to delivery:

| Requirement Area | Checklist Verification Items |
| :--- | :--- |
| **No Known Exploitable Flaws** | Evidence that software is shipped free of known, exploitable vulnerabilities. |
| **Secure by Default** | Default settings are hardened; attack surfaces/unnecessary services/ports are minimized; factory reset or configuration reset mechanisms are available. |
| **Access Control & Identity** | Robust authentication, authorization, token encryption, and least-privilege access enforcement. |
| **Data Protection** | Encryption of sensitive data in transit and at rest; protection against unauthorized data modification or corruption. |
| **Data Minimization** | Verification that the software only processes and retains data strictly necessary for its intended functionality. |
| **Resilience & Availability** | Protection against denial-of-service (DoS) conditions and mitigation of negative impacts on other network devices. |

---

### Pillar 3: Vulnerability Handling & Supply Chain Obligations (Annex I, Part II)
Evaluate whether the manufacturer has operationalized ongoing dependency tracking and lifecycle security:
* [ ] **Software Bill of Materials (SBOM)**: Maintaining a complete, machine-readable inventory of all first- and third-party dependencies (utilizing standards like CycloneDX or SPDX).
* [ ] **Supply Chain Due Diligence**: Documented process to screen, test, and vet third-party and open-source components for inherited flaws prior to integration.
* [ ] **Security Testing in CI/CD**: Ongoing vulnerability scanning, static/dynamic analysis (SAST/DAST), code reviews, and penetration testing.
* [ ] **Coordinated Vulnerability Disclosure (CVD)**: A public policy (e.g., `SECURITY.md`, dedicated contact point) defining how external researchers can privately report security flaws.
* [ ] **Patch Management**: Capability to rapidly develop, validate, and securely distribute security fixes and patches (kept distinct from functional/feature updates).

---

### Pillar 4: Incident & Vulnerability Reporting Readiness (Article 14)
Verify the manufacturer’s incident response workflows against mandatory regulatory notification windows:
* [ ] **24-Hour Early Warning**: Documented escalation procedures to notify the designated CSIRT and ENISA within 24 hours of becoming aware of an actively exploited vulnerability or severe security incident.
* [ ] **72-Hour Notification**: Follow-up detailed report with impact analysis and mitigation/workaround steps.
* [ ] **Final Report**: Concluding report delivered within 14 days after a corrective patch or mitigation is available (or 1 month for severe unresolved incidents).

---

### Pillar 5: Technical Documentation & Conformity (Annex VII & Module A)
Compile the formal Technical File required to affix the CE mark and verify compliance:
* [ ] **Cybersecurity Risk Assessment**: A formal threat model and risk assessment identifying potential threats across design, deployment, and maintenance.
* [ ] **User Information & Manuals (Annex II)**: End-user documentation detailing secure installation, recommended security configuration, and decommission/end-of-life procedures.
* [ ] **EU Declaration of Conformity (DoC)**: A signed legal declaration confirming compliance with all applicable essential requirements of the CRA.
* [ ] **CE Marking**: Affixing the CE mark to the software packaging, documentation, or digital interface in accordance with Conformity Assessment Module A.

---

## ⚙️ Implementing the CI/CD Enforcer Workflow

Drop this zero-friction, hardened workflow directly into your repository to activate deterministic pipeline guardrails:

```yaml
# .github/workflows/packablock-enforcer.yml
name: Packablock Deterministic Supply Chain Enforcer

on:
  pull_request:
    paths:
      - '**/package.json'
      - '**/package-lock.json'
      - '**/bun.lockb'
  push:
    branches:
      - main

permissions:
  contents: read
  id-token: write

jobs:
  enforce-guardrails:
    runs-on: ubuntu-latest
    container:
      image: ghcr.io/packablock/hardened-enforcer:v1
      options: --no-new-privileges

    steps:
      - name: Checkout Source
        uses: actions/checkout@v4

      - name: Verify Authoritative Ledger State
        run: |
          pkablk verify --server https://packablock.com

      - name: Evaluate Dependency Deltas & Append
        run: |
          pkablk append \
            --target-file package-lock.json \
            --out-of-band-branch packablock-log

      - name: Perform Build & Attestation Check
        run: |
          bun run build
          pkablk pack --assert-clean
```

---

## 🚀 Get Started with Packablock

* **Install the CLI Engine**: `bun add -g @packablock/client` or `npm install -g packablock`
* **Explore the Specifications**: Review the soft-schema specification and multi-document YAML primitives.
* **Automate Your Pipeline**: Integrate the GitHub Actions runner to establish deterministic CI/CD guardrails with zero developer friction.
