---
layout: default
title: EU Cyber Resilience Act (CRA) Compliance Checklist
description: Self-assessment checklist for Software Manufacturer Module A conformity under the EU Cyber Resilience Act, aligned with Eclipse Foundation ORC Working Group standards.
permalink: /cra-compliance-checklist/
---

<article class="about-article article-layout">
  
  <!-- Header: Left-Justified -->
  <header class="article-header">
    <div class="article-badge">
      ✦ Regulatory Compliance &amp; Standards
    </div>
    <h1 class="article-title">EU Cyber Resilience Act (CRA) Compliance Checklist</h1>
    <p class="article-subtitle">
      A practical self-assessment framework for Software Manufacturer Module A conformity under the EU Cyber Resilience Act, aligned with the Eclipse Foundation Open Regulatory Compliance (ORC) Working Group standards.
    </p>
  </header>

  <!-- Article Body -->
  <div class="article-content">

    <section class="article-section">
      <p class="lead-paragraph">
        Under the EU Cyber Resilience Act (CRA), products with digital elements classified as <strong>"Default / Standard"</strong>—as well as certain qualifying open-source software under Article 32—can demonstrate regulatory conformity through <strong>Conformity Assessment Module A (Internal Production Control / Manufacturer Self-Assessment)</strong>.
      </p>

      <p>
        This checklist incorporates guidance and criteria established by the <strong>Eclipse Foundation’s Open Regulatory Compliance (ORC) Working Group</strong> alongside affiliated industry initiatives (such as the <strong>OCCTET Project</strong> and the <strong>sCC4CRA / Simplified Common Criteria</strong> framework) to help software manufacturers and open-source stewards operationalize compliance across their engineering pipelines.
      </p>

      <!-- Soft Mid-Tone Download Pane -->
      <aside class="soft-pane download-pane">
        <div class="download-pane-content">
          <div class="pane-tag">Executive Resource</div>
          <p class="pane-quote">Download the printable self-assessment matrix for your compliance records.</p>
          <span class="pane-cite">Includes statutory reporting timelines, Module A criteria, and technical file requirements.</span>
        </div>
        <div class="download-pane-action">
          <a href="{{ '/assets/docs/packablock-security-checklist.pdf' | relative_url }}" class="btn-primary" download>
            <svg viewBox="0 0 24 24" width="18" height="18" fill="none" stroke="currentColor" stroke-width="2.5" style="margin-right: 8px; vertical-align: middle;"><path stroke-linecap="round" stroke-linejoin="round" d="M3 16.5v2.25A2.25 2.25 0 005.25 21h13.5A2.25 2.25 0 0021 18.75V16.5M16.5 12L12 16.5m0 0L7.5 12m4.5 4.5V3"></path></svg>
            Download PDF Checklist
          </a>
        </div>
      </aside>
    </section>

    <!-- Core Pillars Section -->
    <section class="article-section">
      <h2>The Five Core Pillars of CRA Self-Assessment</h2>
      <p>
        Manufacturers qualifying for Module A must document internal production controls across five foundational areas before affixing the CE mark:
      </p>

      <!-- Pillar 1 -->
      <div class="pillar-block">
        <h3>Pillar 1: Scope, Product Classification &amp; Support Period</h3>
        <p>Ensure the software product is accurately categorized and its operational support boundaries are formally defined:</p>
        <ul class="article-checklist">
          <li>
            <span class="check-icon">✓</span>
            <strong>Scope Verification:</strong> Confirm whether the software qualifies as a Product with Digital Elements (PDE) having direct or indirect logical or network data connections.
          </li>
          <li>
            <span class="check-icon">✓</span>
            <strong>Risk Tiering:</strong> Establish whether the product falls under Default/Standard (eligible for pure self-assessment), Important (Class I / Class II), or Critical.
          </li>
          <li>
            <span class="check-icon">✓</span>
            <strong>Defined Support Period:</strong> Formally document the guaranteed lifetime during which the manufacturer will provide free security updates (minimum expected lifetime).
          </li>
        </ul>
      </div>

      <!-- Pillar 2 -->
      <div class="pillar-block">
        <h3>Pillar 2: Product Security by Design &amp; Default (Annex I, Part I)</h3>
        <p>Assess whether cybersecurity controls are built into the architecture from conception through delivery:</p>

        <div class="soft-pane table-pane">
          <table class="cra-table">
            <thead>
              <tr>
                <th>Requirement Area</th>
                <th>Checklist Verification Items</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td><strong>No Known Exploitable Flaws</strong></td>
                <td>Evidence that software is shipped free of known, exploitable vulnerabilities prior to release.</td>
              </tr>
              <tr>
                <td><strong>Secure by Default</strong></td>
                <td>Default configurations are hardened; attack surfaces and unnecessary services/ports are minimized; reset mechanisms are available.</td>
              </tr>
              <tr>
                <td><strong>Access Control &amp; Identity</strong></td>
                <td>Robust authentication, authorization, token encryption, and least-privilege access enforcement.</td>
              </tr>
              <tr>
                <td><strong>Data Protection</strong></td>
                <td>Encryption of sensitive data in transit and at rest; protection against unauthorized data modification or corruption.</td>
              </tr>
              <tr>
                <td><strong>Data Minimization</strong></td>
                <td>Verification that the software only processes and retains data strictly necessary for its intended functionality.</td>
              </tr>
              <tr>
                <td><strong>Resilience &amp; Availability</strong></td>
                <td>Protection against denial-of-service (DoS) conditions and mitigation of negative impacts on neighboring network devices.</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>

      <!-- Pillar 3 -->
      <div class="pillar-block">
        <h3>Pillar 3: Vulnerability Handling &amp; Supply Chain Obligations (Annex I, Part II)</h3>
        <p>Evaluate whether the manufacturer has operationalized ongoing dependency tracking and lifecycle security:</p>
        <ul class="article-checklist">
          <li>
            <span class="check-icon">✓</span>
            <strong>Software Bill of Materials (SBOM):</strong> Maintaining a complete, machine-readable inventory of all first- and third-party dependencies (utilizing standards like CycloneDX or SPDX).
          </li>
          <li>
            <span class="check-icon">✓</span>
            <strong>Supply Chain Due Diligence:</strong> Documented process to screen, test, and vet third-party and open-source components for inherited flaws prior to integration.
          </li>
          <li>
            <span class="check-icon">✓</span>
            <strong>Security Testing in CI/CD:</strong> Ongoing vulnerability scanning, static/dynamic analysis (SAST/DAST), code reviews, and penetration testing.
          </li>
          <li>
            <span class="check-icon">✓</span>
            <strong>Coordinated Vulnerability Disclosure (CVD):</strong> A public policy (e.g., <code>SECURITY.md</code>, dedicated contact point) defining how external researchers can privately report security flaws.
          </li>
          <li>
            <span class="check-icon">✓</span>
            <strong>Patch Management:</strong> Capability to rapidly develop, validate, and securely distribute security fixes and patches (kept distinct from functional/feature updates).
          </li>
        </ul>
      </div>

      <!-- Pillar 4 -->
      <div class="pillar-block">
        <h3>Pillar 4: Incident &amp; Vulnerability Reporting Readiness (Article 14)</h3>
        <p>Verify the manufacturer’s incident response workflows against mandatory regulatory notification windows:</p>
        <ul class="article-checklist">
          <li>
            <span class="check-icon">✓</span>
            <strong>24-Hour Early Warning:</strong> Documented escalation procedures to notify the designated CSIRT and ENISA within 24 hours of becoming aware of an actively exploited vulnerability or severe security incident.
          </li>
          <li>
            <span class="check-icon">✓</span>
            <strong>72-Hour Notification:</strong> Follow-up detailed report with impact analysis, incident indicators, and mitigation/workaround steps.
          </li>
          <li>
            <span class="check-icon">✓</span>
            <strong>Final Report:</strong> Concluding report delivered within 14 days after a corrective patch or mitigation is available (or 1 month for severe unresolved incidents).
          </li>
        </ul>
      </div>

      <!-- Pillar 5 -->
      <div class="pillar-block">
        <h3>Pillar 5: Technical Documentation &amp; Conformity (Annex VII &amp; Module A)</h3>
        <p>Compile the formal Technical File required to affix the CE mark and demonstrate audit readiness:</p>
        <ul class="article-checklist">
          <li>
            <span class="check-icon">✓</span>
            <strong>Cybersecurity Risk Assessment:</strong> A formal threat model and risk assessment identifying potential threats across design, deployment, and maintenance.
          </li>
          <li>
            <span class="check-icon">✓</span>
            <strong>User Information &amp; Manuals (Annex II):</strong> End-user documentation detailing secure installation, recommended security configuration, and decommission/end-of-life procedures.
          </li>
          <li>
            <span class="check-icon">✓</span>
            <strong>EU Declaration of Conformity (DoC):</strong> A signed legal declaration confirming compliance with all applicable essential requirements of the CRA.
          </li>
          <li>
            <span class="check-icon">✓</span>
            <strong>CE Marking:</strong> Affixing the CE mark to the software packaging, documentation, or digital interface in accordance with Conformity Assessment Module A.
          </li>
        </ul>
      </div>
    </section>

    <!-- CI/CD Section -->
    <section class="article-section">
      <h2>Implementing the CI/CD Enforcer Workflow</h2>
      <p>
        Packablock provides continuous attestation gates to satisfy CRA Module A supply chain requirements deterministically. Drop this hardened workflow directly into your repository to enforce cryptographic dependency validation on every pull request:
      </p>

      <div class="soft-pane terminal-pane">
        <div class="terminal-bar">
          <span class="term-dot"></span><span class="term-dot"></span><span class="term-dot"></span>
          <span class="term-title">.github/workflows/packablock-enforcer.yml</span>
        </div>
        <pre><code><span class="c1"># Packablock Deterministic Supply Chain Enforcer</span>
<span class="k">name:</span> <span class="s1">Packablock Deterministic Supply Chain Enforcer</span>

<span class="k">on:</span>
  <span class="k">pull_request:</span>
    <span class="k">paths:</span>
      <span class="s2">- '**/package.json'</span>
      <span class="s2">- '**/package-lock.json'</span>
      <span class="s2">- '**/bun.lockb'</span>
  <span class="k">push:</span>
    <span class="k">branches:</span>
      <span class="s2">- main</span>

<span class="k">permissions:</span>
  <span class="k">contents:</span> <span class="s1">read</span>
  <span class="k">id-token:</span> <span class="s1">write</span>

<span class="k">jobs:</span>
  <span class="k">enforce-guardrails:</span>
    <span class="k">runs-on:</span> <span class="s1">ubuntu-latest</span>
    <span class="k">container:</span>
      <span class="k">image:</span> <span class="s1">ghcr.io/packablock/hardened-enforcer:v1</span>
      <span class="k">options:</span> <span class="s1">--no-new-privileges</span>

    <span class="k">steps:</span>
      <span class="k">- name:</span> <span class="s1">Checkout Source</span>
        <span class="k">uses:</span> <span class="s1">actions/checkout@v4</span>

      <span class="k">- name:</span> <span class="s1">Verify Authoritative Ledger State</span>
        <span class="k">run:</span> <span class="s1">|</span>
          <span class="s2">pkablk verify --server https://packablock.com</span>

      <span class="k">- name:</span> <span class="s1">Evaluate Dependency Deltas &amp; Append</span>
        <span class="k">run:</span> <span class="s1">|</span>
          <span class="s2">pkablk append --target-file package-lock.json --out-of-band-branch packablock-log</span>

      <span class="k">- name:</span> <span class="s1">Perform Build &amp; Attestation Check</span>
        <span class="k">run:</span> <span class="s1">|</span>
          <span class="s2">bun run build</span>
          <span class="s2">pkablk pack --assert-clean</span></code></pre>
      </div>
    </section>

    <!-- Getting Started Section -->
    <section class="article-section">
      <h2>Getting Started with Packablock</h2>
      <p>
        Operationalize your CRA compliance pipeline and eliminate software supply chain opacity today:
      </p>

      <ul class="article-list">
        <li><strong>Install the CLI Engine:</strong> Run <code>bun add -g @packablock/client</code> or <code>npm install -g packablock</code> to initialize local attestation tracking.</li>
        <li><strong>Explore Regulatory Datalake Datasets:</strong> Query statutory penalty models and EU CRA benchmark crosswalks at <a href="https://data.packablock.com" target="_blank" rel="noopener">data.packablock.com ↗</a>.</li>
        <li><strong>Micro-Enterprise Exposure &amp; Inaction Index:</strong> Model sweat equity compliance costs vs. platform delisting and customs impoundment using our <a href="{{ '/reports/#commercial' | relative_url }}">CRA-05 Actuarial Model</a>.</li>
        <li><strong>Automate Your Pipeline:</strong> Integrate the GitHub Actions runner above to establish deterministic CI/CD guardrails with zero developer friction.</li>
        <li><strong>Enterprise Consultation:</strong> Schedule an architecture review for private trust registries at <a href="{{ '/reports/#consultation' | relative_url }}">Enterprise Consultation</a>.</li>
      </ul>
    </section>

  </div>

  <footer class="article-footer">
    <p>
      Published by <strong>Packablock, LLC</strong> &bull;
      Package Control, Block by Block.
    </p>
  </footer>

</article>
