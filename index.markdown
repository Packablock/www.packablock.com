---
layout: page
title: Welcome
permalink: /
---

<div class="hero-section">
  <div class="hero-logo">
    <svg width="96" height="96" class="w-24 h-24 text-[#22d3ee]" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 120 120" fill="none" stroke="none" role="img" aria-label="Packablock mark">
      <line x1="60" y1="20" x2="60" y2="100" stroke="currentColor" stroke-width="8" stroke-linecap="round"/>
      <circle cx="60" cy="30" r="8" fill="currentColor"/>
      <circle cx="60" cy="60" r="8" fill="currentColor"/>
      <circle cx="60" cy="90" r="8" fill="currentColor"/>
    </svg>
  </div>
  <h1 class="hero-title">Deterministic Supply Chain Policy Control</h1>
  <p class="hero-subtitle">
    Cryptographically secure attestation logs and parallel lockfile tracking to defend against software supply chain attacks and package tampering.
  </p>
  <a href="https://docs.packablock.com" class="btn-primary">
    Explore the Documentation
    <svg class="w-4 h-4 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5L21 12m0 0l-7.5 7.5M21 12H3"></path></svg>
  </a>
</div>

<div class="feature-grid">
  <div class="feature-card">
    <h3>🛡️ Cryptographic Attestation</h3>
    <p>Every change in your dependencies generates a cryptographically secured and linked metadata block. Any retroactive state tampering becomes mathematically evident.</p>
  </div>
  <div class="feature-card">
    <h3>🔄 Parallel Lockfile Tracking</h3>
    <p>Simultaneously track multiple package manifests and lockfiles (package-lock.json, bun.lockb, pnpm-lock.yaml, Gemfile.lock) side-by-side in a single repository chain.</p>
  </div>
  <div class="feature-card">
    <h3>⚡ SemVer Drift Detection</h3>
    <p>Analyze version drift, detect regressions, and evaluate incoming updates against compliance policies before dependencies make it to runtime.</p>
  </div>
  <div class="feature-card">
    <h3>⚙️ CI/CD Security Gates</h3>
    <p>Enforce attestation validation in your deployment pipelines. Block builds instantly on untracked dependency changes or compromised historical blocks before they reach production.</p>
  </div>
</div>
