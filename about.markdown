---
layout: default
title: About Packablock | Preventative Software Supply Chain Security
description: Our mission is to establish preventative, deterministic security models for modern CI/CD pipelines, transitioning away from passive, awareness-first vulnerability monitoring.
permalink: /about/
---

<div class="about-container">
  
  <!-- Hero Section -->
  <header class="about-hero">
    <div class="about-badge">
      ✦ Preventative Supply Chain Architecture
    </div>
    <h1 class="about-title">About Packablock</h1>
    <p class="about-lead">
      We are building preventative, deterministic security models for modern software delivery—transitioning engineering teams away from passive, awareness-first vulnerability monitoring.
    </p>
  </header>

  <div class="about-grid">

    <!-- Card 1: The Reactive Security Flaw -->
    <section class="block-pane about-pane">
      <div class="pane-header">
        <h2 class="pane-title">The Reactive Security Flaw</h2>
        <span class="pane-tag">The Problem</span>
      </div>
      <p>
        Every day, developers and automated CI/CD pipelines pull millions of open-source packages from public registries. Traditional tools monitor these dependencies in a passive, retrospective posture—scanning lockfiles after they are committed and alerting security teams hours or days after a vulnerability is cataloged in a public CVE database.
      </p>
      <div class="about-stat-box">
        <div class="stat-highlight">50%+</div>
        <div class="stat-detail">
          <strong>Malicious packages execute immediately upon installation.</strong>
          <span>Receiving a passive alert hours or days later means developer workstations, build runners, and production secrets are already compromised.</span>
        </div>
      </div>
      <p class="text-subtle">
        Source: <a href="https://arxiv.org/abs/2005.09535" target="_blank" rel="noopener">Academic research on package repository malware execution timing</a>.
      </p>
    </section>

    <!-- Card 2: Deterministic Policy Control -->
    <section class="block-pane about-pane">
      <div class="pane-header">
        <h2 class="pane-title">Deterministic Policy Control</h2>
        <span class="pane-tag">The Architecture</span>
      </div>
      <p>
        Packablock transitions software supply chains to a <strong>preventative, deterministic security model</strong>. By recording sequentially linked, cryptographically signed metadata ledgers for dependency modifications, Packablock acts as a continuous, tamper-evident validation gate.
      </p>
      <p>
        If a package is updated without validation, suffers silent tampering, or deviates from authorized timeline state, Packablock blocks the build before it can reach compile time or execute inside runtime environments.
      </p>
      
      <div class="about-terminal-pane">
        <div class="terminal-bar">
          <span class="term-dot"></span><span class="term-dot"></span><span class="term-dot"></span>
          <span class="term-title">pkablk &mdash; strict attestation gate</span>
        </div>
        <pre><code><span class="c1"># 1. Cryptographically verify local attestation log</span>
<span class="s2">pkablk</span> verify --strict --chain packablock.chain.json

<span class="c1"># 2. Enforce preventative CI/CD gate before build step</span>
<span class="s2">pkablk</span> gate --enforce-policy=slsa-l3 --allow-signed-only

<span class="k">[PASS]</span> <span class="s1">Chain integrity valid: 142 attested blocks, 0 drift, 0 unverified packages.</span></code></pre>
      </div>
    </section>

    <!-- Card 3: Open Standards & Mission -->
    <section class="block-pane about-pane">
      <div class="pane-header">
        <h2 class="pane-title">Engineered for Open Standards</h2>
        <span class="pane-tag">Our Mission</span>
      </div>
      <p>
        We are building the open-source foundation needed to achieve compliance with modern supply chain standards—such as <strong>SLSA Build L3</strong> and <strong>Sigstore</strong> cryptographic signing—without requiring complex, proprietary enterprise control systems.
      </p>
      <p>
        Packablock is engineered specifically for developers, SecOps teams, and autonomous AI agents who require deterministic dependency guarantees, parallel lockfile tracking (npm, Bun, pnpm, RubyGems), and zero-trust verification.
      </p>
      <ul class="about-features-list">
        <li><strong>Cryptographic Attestation Ledgers:</strong> Sequentially chained metadata blocks proving dependency provenance.</li>
        <li><strong>Parallel Multi-Manifest Tracking:</strong> Side-by-side reconciliation across polyglot package managers.</li>
        <li><strong>Compile-Time Security Gates:</strong> Immediate rejection of untracked or modified artifacts prior to build execution.</li>
        <li><strong>Open Datalake Integration:</strong> Direct access to edge-cached global supply chain intelligence at <a href="https://data.packablock.com" target="_blank" rel="noopener">data.packablock.com ↗</a>.</li>
      </ul>
    </section>

    <!-- Card 4: Leadership, Contact & Channels -->
    <section class="block-pane about-pane">
      <div class="pane-header">
        <h2 class="pane-title">Get in Touch</h2>
        <span class="pane-tag">Connect</span>
      </div>
      <p>
        Whether you are interested in deploying private trust registries, collaborating on the Continuous Attestation specification, or integrating our open-source CLI tools:
      </p>

      <div class="about-contact-grid">
        <a href="mailto:support@packablock.com" class="about-contact-card">
          <div class="contact-card-icon">✉️</div>
          <div class="contact-card-info">
            <span class="contact-card-title">Direct Support &amp; Deployment</span>
            <span class="contact-card-value">support@packablock.com</span>
          </div>
        </a>

        <a href="https://www.linkedin.com/in/aaronbronow" target="_blank" rel="noopener" class="about-contact-card">
          <div class="contact-card-icon">👤</div>
          <div class="contact-card-info">
            <span class="contact-card-title">Leadership &amp; Architecture</span>
            <span class="contact-card-value">Aaron Bronow on LinkedIn ↗</span>
          </div>
        </a>

        <a href="https://github.com/Packablock" target="_blank" rel="noopener" class="about-contact-card">
          <div class="contact-card-icon">🐙</div>
          <div class="contact-card-info">
            <span class="contact-card-title">Open Source Repositories</span>
            <span class="contact-card-value">Packablock Organization on GitHub ↗</span>
          </div>
        </a>

        <a href="https://data.packablock.com" target="_blank" rel="noopener" class="about-contact-card">
          <div class="contact-card-icon">⚡</div>
          <div class="contact-card-info">
            <span class="contact-card-title">Public Intelligence Datalake</span>
            <span class="contact-card-value">data.packablock.com ↗</span>
          </div>
        </a>
      </div>
    </section>

  </div>

  <footer class="about-page-footer">
    <p>
      Maintained by <strong>Packablock, LLC</strong> &bull;
      Package Control, Block by Block.
    </p>
  </footer>

</div>
