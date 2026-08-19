---
layout: page
title: Get Your CRA Compliance Checklist
permalink: /cra-compliance-checklist/
---

# Get Your CRA Compliance Checklist
## Deterministic Guardrails for CI/CD Pipelines
### The Architectural Checklist for Tamper-Proof Software Supply Chains

> **Executive Brief**: Traditional software supply chain security relies on awareness—static SBOM snapshots and post-incident CVE alerts that notify you after a compromised artifact has already entered production. Packablock transforms compliance into active prevention by embedding deterministic, cryptographic guardrails directly into your CI/CD pipelines.

---

## 🎯 Why Static Checklists Are No Longer Enough

Modern regulatory frameworks (such as the EU Cyber Resilience Act, SLSA Level 3+, and executive cybersecurity mandates) demand continuous, verifiable provenance rather than point-in-time assertions.

* **The Resolution Gap**: Static dependency exports often scrape declared ranges rather than absolute runtime state.
* **The "Eve" Build-Tampering Attack**: Attackers with runner access or compromised credentials can mutate compiled release binaries while leaving source trees and pull requests looking pristine.
* **Passive vs. Preventative Posture**: Retroactive notifications alert teams hours or days after execution; deterministic guardrails stop untrusted, unverified builds at the runner boundary.

---

## 📋 The Deterministic CI/CD Guardrail Checklist

```text
           [ Commit / PR ]
                  │
                  ▼
   ┌──────────────────────────────┐
   │ 1. INGESTION & LOCK GAUNTLET │ ➔ Parse lockfiles, evaluate SemVer boundaries
   └──────────────┬───────────────┘
                  │
                  ▼
   ┌──────────────────────────────┐
   │ 2. HERMETIC RUNNER ISOLATION │ ➔ OIDC auth, build binary, compute SHA-256
   └──────────────┬───────────────┘
                  │
                  ▼
   ┌──────────────────────────────┐
   │ 3. CRYPTOGRAPHIC LEDGER LINK │ ➔ Append delta, sign block, push out-of-band
   └──────────────┬───────────────┘
                  │
                  ▼
   ┌──────────────────────────────┐
   │ 4. DETERMINISTIC ENFORCEMENT │ ➔ Assert O(1) hash chain, verify anchors
   └──────────────┬───────────────┘
                  │
                  ▼
           [ Deploy / Pack ]
```

### Phase 1: Ingestion & Dependency Boundary Guardrails
*Prevent untrusted, floating, or unpinned dependencies from silently entering execution paths.*

* [ ] **Deterministic Lockfile Ingestion**: Lockfile states (`package-lock.json`, `bun.lockb`, Cargo manifests) must be deterministically parsed into an immutable baseline during pipeline initialization.
* [ ] **SemVer Drift & Wick Monitoring**: Establish bounds between installed pins and upper semantic ceilings to prevent upstream "ghost wick" dependency drift and breaking changes.
* [ ] **Pre-Execution Challenge Gates**: Require incoming dependencies to validate against an authoritative registry before build scripts or pre/post-install hooks run.

### Phase 2: Hermetic Isolation & Build Attestation
*Ensure that source code intent strictly matches compiled runtime artifacts.*

* [ ] **Sandboxed Build Runners**: Execute builds within isolated, minimal container environments with restricted memory caps and dropped capabilities (`--no-new-privileges`).
* [ ] **Ephemeral, Keyless Authentication (OIDC)**: Eliminate long-lived static secrets in runner environments by minting short-lived OpenID Connect (OIDC) JWT tokens tied directly to GitHub JWKS claims.
* [ ] **Atomic Build Attestation**: Calculate byte-for-byte SHA-256 hashes of compiled binaries immediately upon compilation and bind them cryptographically to the commit SHA and committer identity.

### Phase 3: Out-of-Band Cryptographic Ledger
*Maintain an un-rewritable audit trail without polluting main development branches.*

* [ ] **Multi-Document YAML State Streams**: Capture every dependency transition as an append-only, human-readable transactional delta block (`packablock.yaml`).
* [ ] **Zero Main Branch Pollution**: Ensure pipeline enforcers write ledger states strictly out-of-band to a dedicated metadata branch (`sbom-ledger` / `packablock-log`) or an OCI registry artifact layer.
* [ ] **Constant-Memory (O(1)) Stream Verification**: Implement raw-byte streaming verification to validate block indices, metadata signatures, and chain hashes linearly without loading multi-gigabyte logs into runner memory.

### Phase 4: Continuous Provenance, Time-Travel & Audit Readiness
*Ensure historic accountability and zero-overhead audit compliance across the software lifecycle.*

* [ ] **Deterministic Time-Travel Verification**: Reconstruct exact byte-for-byte replicas of past configurations at any arbitrary historical timestamp via forward-replay state machines (`pkablk checkout <file> --time <timestamp>`).
* [ ] **Genesis Rollover (Log Pruning)**: Automatically seal, archive, and rollover historical ledger chains once threshold limits are reached, inheriting terminal hash anchors to maintain millisecond verification speeds.
* [ ] **Tiered Trust Anchoring**: Enforce pipeline verification policies across standalone offline runs (P2P / degraded trust warnings) and cloud-anchored registries (ALME protocol).

---

## 🔬 Matrix: Legacy Compliance vs. Packablock Determinism

| Compliance Vector | Legacy / Static Approach | Packablock Deterministic Guardrail |
| :--- | :--- | :--- |
| **SBOM Architecture** | Static SPDX/CycloneDX exports generated post-build. | Transactional Delta Chains: Live multi-document YAML stream tracking every change linearly. |
| **Storage & Git History** | Heavy JSON blobs committed to main or unindexed S3 buckets. | Out-of-Band Isolation: Dedicated metadata branches (`packablock-log`) or OCI registry layers. |
| **Runner Verification** | Trust-on-first-use; runners assume installed binaries are safe. | O(1) Raw-Byte Stream Verification: Instant rejection of altered or forged blocks. |
| **Audit & Provenance** | Speculative git diffs over thousands of manifest lines. | Time-Travel Checkouts: Deterministic state reconstruction at exact historical timestamps. |
| **Onboarding** | Manual creation and copying of long-lived API tokens. | ALME Protocol: Automatic nonce challenges via `.well-known/sbom-challenge`. |

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
