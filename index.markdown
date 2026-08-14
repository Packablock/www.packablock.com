---
layout: default
title: Welcome
permalink: /
---

<div class="early-access-banner">
  <div class="banner-badge">Early Access</div>
  <div class="banner-separator"></div>
  <div class="banner-content">
    <span class="banner-text">Reserve your slot for the Packablock developer preview.</span>
    <a href="/signup/" class="banner-link">Apply Now &rarr;</a>
  </div>
</div>

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
  <div class="hero-buttons">
    <a href="https://github.com/Packablock/packablock-client" class="btn-primary" target="_blank" rel="noopener">
      <svg viewBox="0 0 16 16" width="18" height="18" fill="currentColor" style="margin-right: 8px; vertical-align: middle;"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"></path></svg>
      Star on GitHub
    </a>
    <a href="https://docs.packablock.com" class="btn-secondary">
      Explore the Docs
      <svg width="16" height="16" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" stroke-width="2.5" style="margin-left: 8px; vertical-align: middle;"><path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5L21 12m0 0l-7.5 7.5M21 12H3"></path></svg>
    </a>
  </div>
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
