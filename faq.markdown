---
layout: default
title: Frequently Asked Questions (FAQ)
description: Frequently asked questions about Package URLs (PURLs), Software Bill of Materials (SBOM) standards, and deterministic supply chain verification.
permalink: /faq/
---

<article class="about-article article-layout">
  
  <!-- Header: Left-Justified -->
  <header class="article-header">
    <div class="article-badge">
      ✦ Knowledge Base &amp; Standards
    </div>
    <h1 class="article-title">Frequently Asked Questions</h1>
    <p class="article-subtitle">
      Essential reference for Package URLs (PURLs), SBOM segment anatomy, generic binary identifiers, and deterministic supply chain verification.
    </p>
  </header>

  <!-- Article Body -->
  <div class="article-content">

    <!-- FAQ 1: PURL Segments -->
    <section class="article-section" id="purl-segments">
      <h2>What are the segments of a Package URL (PURL)?</h2>
      
      <p>
        A <strong>Package URL (PURL)</strong> is an open specification standard for reliably identifying and locating software packages across disparate ecosystems. Defined by the <a href="https://github.com/package-url/purl-spec" target="_blank" rel="noopener">Package URL Specification</a>, every canonical PURL follows a standard URL-like string format:
      </p>

      <!-- Soft Mid-Tone Terminal Pane: PURL Syntax Anatomy -->
      <div class="soft-pane terminal-pane" style="margin-bottom: 1.75rem;">
        <div class="terminal-bar">
          <span class="term-dot"></span><span class="term-dot"></span><span class="term-dot"></span>
          <span class="term-title">canonical purl syntax anatomy</span>
        </div>
        <pre class="terminal-body" style="padding: 1.25rem 1.5rem; font-size: 0.95rem; line-height: 1.6; color: #f1f5f9; overflow-x: auto;"><code><span style="color: #22D3EE; font-weight: 700;">pkg:</span><span style="color: #38bdf8;">type</span>/<span style="color: #cbd5e1;">namespace</span>/<span style="color: #ffffff; font-weight: 700;">name</span>@<span style="color: #34d399;">version</span>?<span style="color: #fbbf24;">qualifiers</span>#<span style="color: #f472b6;">subpath</span></code></pre>
      </div>

      <p>
        A canonical PURL comprises seven distinct segments, arranged in strict hierarchical sequence:
      </p>

      <div style="overflow-x: auto; margin-bottom: 2rem;">
        <table style="width: 100%; border-collapse: collapse; font-size: 0.88rem; background: rgba(14, 27, 46, 0.7); border-radius: 8px; overflow: hidden; border: 1px solid rgba(255, 255, 255, 0.08);">
          <thead>
            <tr style="background: rgba(14, 27, 46, 0.95); border-bottom: 1px solid rgba(34, 211, 238, 0.25); text-align: left;">
              <th style="padding: 0.75rem 1rem; color: #22D3EE; font-weight: 800; text-transform: uppercase; font-size: 0.72rem; letter-spacing: 0.05em;">Segment</th>
              <th style="padding: 0.75rem 1rem; color: #22D3EE; font-weight: 800; text-transform: uppercase; font-size: 0.72rem; letter-spacing: 0.05em;">Requirement</th>
              <th style="padding: 0.75rem 1rem; color: #22D3EE; font-weight: 800; text-transform: uppercase; font-size: 0.72rem; letter-spacing: 0.05em;">Description</th>
              <th style="padding: 0.75rem 1rem; color: #22D3EE; font-weight: 800; text-transform: uppercase; font-size: 0.72rem; letter-spacing: 0.05em;">Example</th>
            </tr>
          </thead>
          <tbody>
            <tr style="border-bottom: 1px solid rgba(255, 255, 255, 0.05);">
              <td style="padding: 0.8rem 1rem; font-family: 'IBM Plex Mono', monospace; color: #22D3EE; font-weight: 700;">scheme</td>
              <td style="padding: 0.8rem 1rem; color: #34d399; font-weight: 700; font-size: 0.78rem;">Required</td>
              <td style="padding: 0.8rem 1rem; color: #cbd5e1;">Constant URL scheme protocol prefix; must always be <code>pkg</code>.</td>
              <td style="padding: 0.8rem 1rem; font-family: 'IBM Plex Mono', monospace; color: #94a3b8; font-size: 0.82rem;">pkg</td>
            </tr>
            <tr style="border-bottom: 1px solid rgba(255, 255, 255, 0.05);">
              <td style="padding: 0.8rem 1rem; font-family: 'IBM Plex Mono', monospace; color: #38bdf8; font-weight: 700;">type<br><span style="font-size: 0.72rem; color: #94a3b8; font-weight: normal;">(Package type)</span></td>
              <td style="padding: 0.8rem 1rem; color: #34d399; font-weight: 700; font-size: 0.78rem;">Required</td>
              <td style="padding: 0.8rem 1rem; color: #cbd5e1;">Package manager, package ecosystem, or registry type (e.g. <code>golang</code>, <code>npm</code>, <code>pypi</code>, <code>cargo</code>, <code>deb</code>, <code>generic</code>). In Packablock reports, this segment is referred to as <strong>Package type</strong>.</td>
              <td style="padding: 0.8rem 1rem; font-family: 'IBM Plex Mono', monospace; color: #94a3b8; font-size: 0.82rem;">golang</td>
            </tr>
            <tr style="border-bottom: 1px solid rgba(255, 255, 255, 0.05);">
              <td style="padding: 0.8rem 1rem; font-family: 'IBM Plex Mono', monospace; color: #cbd5e1; font-weight: 700;">namespace</td>
              <td style="padding: 0.8rem 1rem; color: #94a3b8; font-size: 0.78rem;">Optional</td>
              <td style="padding: 0.8rem 1rem; color: #cbd5e1;">Name prefix, vendor, organization, or user scope. Ecosystem-specific conventions apply (e.g., Maven <code>groupId</code>, GitHub owner, npm scope).</td>
              <td style="padding: 0.8rem 1rem; font-family: 'IBM Plex Mono', monospace; color: #94a3b8; font-size: 0.82rem;">sigs.k8s.io</td>
            </tr>
            <tr style="border-bottom: 1px solid rgba(255, 255, 255, 0.05);">
              <td style="padding: 0.8rem 1rem; font-family: 'IBM Plex Mono', monospace; color: #ffffff; font-weight: 700;">name</td>
              <td style="padding: 0.8rem 1rem; color: #34d399; font-weight: 700; font-size: 0.78rem;">Required</td>
              <td style="padding: 0.8rem 1rem; color: #cbd5e1;">The primary name of the package or software component.</td>
              <td style="padding: 0.8rem 1rem; font-family: 'IBM Plex Mono', monospace; color: #94a3b8; font-size: 0.82rem;">yaml</td>
            </tr>
            <tr style="border-bottom: 1px solid rgba(255, 255, 255, 0.05);">
              <td style="padding: 0.8rem 1rem; font-family: 'IBM Plex Mono', monospace; color: #34d399; font-weight: 700;">version</td>
              <td style="padding: 0.8rem 1rem; color: #94a3b8; font-size: 0.78rem;">Optional</td>
              <td style="padding: 0.8rem 1rem; color: #cbd5e1;">Specific release tag, semantic version, git commit hash, or build identifier, preceded by <code>@</code>.</td>
              <td style="padding: 0.8rem 1rem; font-family: 'IBM Plex Mono', monospace; color: #94a3b8; font-size: 0.82rem;">v1.4.0</td>
            </tr>
            <tr style="border-bottom: 1px solid rgba(255, 255, 255, 0.05);">
              <td style="padding: 0.8rem 1rem; font-family: 'IBM Plex Mono', monospace; color: #fbbf24; font-weight: 700;">qualifiers</td>
              <td style="padding: 0.8rem 1rem; color: #94a3b8; font-size: 0.78rem;">Optional</td>
              <td style="padding: 0.8rem 1rem; color: #cbd5e1;">Extra key-value query parameters preceded by <code>?</code> (e.g. architecture, distro, repository URL, checksum).</td>
              <td style="padding: 0.8rem 1rem; font-family: 'IBM Plex Mono', monospace; color: #94a3b8; font-size: 0.82rem;">arch=x86_64</td>
            </tr>
            <tr>
              <td style="padding: 0.8rem 1rem; font-family: 'IBM Plex Mono', monospace; color: #f472b6; font-weight: 700;">subpath</td>
              <td style="padding: 0.8rem 1rem; color: #94a3b8; font-size: 0.78rem;">Optional</td>
              <td style="padding: 0.8rem 1rem; color: #cbd5e1;">Relative sub-path pointing to a specific file or sub-component inside the package, preceded by <code>#</code>.</td>
              <td style="padding: 0.8rem 1rem; font-family: 'IBM Plex Mono', monospace; color: #94a3b8; font-size: 0.82rem;">dist/bundle.js</td>
            </tr>
          </tbody>
        </table>
      </div>

      <!-- Real-World Examples Callout -->
      <aside class="soft-pane callout-pane">
        <div class="pane-tag">Real-World PURL Examples</div>
        <ul style="margin: 0.5rem 0 0 0; padding-left: 1.25rem; color: #e2e8f0; line-height: 1.8; font-size: 0.9rem;">
          <li>
            <strong>Go Module:</strong> <code style="color: #22D3EE;">pkg:golang/sigs.k8s.io/yaml@v1.4.0</code><br />
            <span style="color: #94a3b8; font-size: 0.82rem;">type = <code>golang</code>, namespace = <code>sigs.k8s.io</code>, name = <code>yaml</code>, version = <code>v1.4.0</code></span>
          </li>
          <li style="margin-top: 0.5rem;">
            <strong>Scoped npm Package:</strong> <code style="color: #22D3EE;">pkg:npm/%40angular/animation@12.3.1</code><br />
            <span style="color: #94a3b8; font-size: 0.82rem;">type = <code>npm</code>, namespace = <code>%40angular</code> (URL-encoded <code>@angular</code>), name = <code>animation</code>, version = <code>12.3.1</code></span>
          </li>
          <li style="margin-top: 0.5rem;">
            <strong>Debian Package with Qualifiers:</strong> <code style="color: #22D3EE;">pkg:deb/debian/curl@7.50.3-1?arch=i386&amp;distro=jessie</code><br />
            <span style="color: #94a3b8; font-size: 0.82rem;">type = <code>deb</code>, namespace = <code>debian</code>, name = <code>curl</code>, version = <code>7.50.3-1</code>, qualifiers = <code>arch=i386&amp;distro=jessie</code></span>
          </li>
        </ul>
      </aside>
    </section>

    <!-- FAQ 2: Binary Generic -->
    <section class="article-section" id="pkg-generic">
      <h2>What does "Binary (pkg:generic)" mean?</h2>
      
      <p>
        The <code>pkg:generic</code> type identifies software components, compiled binaries, native shared libraries, or downloaded release archives that do not belong to a language-specific package manager like npm, PyPI, or Cargo.
      </p>

      <p>
        Many critical infrastructure components (such as OpenSSL, zlib, SQLite, or CLI binaries) are distributed as pre-compiled executable binaries or embedded directly into runtime runtimes. Because they lack a <code>package.json</code> or <code>Cargo.toml</code> file, standard lockfile scanners completely miss them.
      </p>

      <p>
        In Packablock inspection reports:
      </p>
      <ul style="color: #cbd5e1; line-height: 1.7; font-size: 0.95rem; margin-bottom: 1.5rem;">
        <li>
          <strong><code>pkg:generic/openssl@3.0.13</code></strong> denotes the authoritative upstream C/C++ cryptographic library bundled directly into the official Node.js 22 LTS distribution.
        </li>
        <li>
          It allows SBOM engines (like SPDX and CycloneDX) to link vulnerabilities (CVEs) affecting native libraries to the host binary, even when language dependency graphs only list pure JavaScript or Go modules.
        </li>
      </ul>
    </section>

    <!-- FAQ 3: Interactive Tooltips -->
    <section class="article-section" id="report-tooltips">
      <h2>How do I inspect PURL segments on Packablock reports?</h2>
      
      <p>
        Every Packablock dependency intelligence report highlights Package URLs with a subtle dotted underline (e.g., <span style="font-family: 'IBM Plex Mono', monospace; font-size: 0.85rem; color: #22D3EE; border-bottom: 1px dotted rgba(34, 211, 238, 0.45); cursor: help;" title="Package URL (PURL) Segments:&#10;• scheme: pkg&#10;• Package type: golang&#10;• namespace: sigs.k8s.io&#10;• name: yaml&#10;• version: v1.4.0">pkg:golang/sigs.k8s.io/yaml@v1.4.0</span>).
      </p>

      <p>
        Hovering your mouse or focus cursor over any PURL badge will automatically display an interactive tooltip breaking down the exact canonical segments: scheme, Package type, namespace, name, version, qualifiers, and subpath.
      </p>

      <aside class="soft-pane callout-pane">
        <div class="pane-tag">Try It in Action</div>
        <p style="margin: 0; color: #e2e8f0; font-size: 0.92rem; line-height: 1.6;">
          Explore our live reports to see segment tooltips in action:
          <br />
          &bull; <a href="{{ "/reports/yaml-in-kubernetes-1-31/" | relative_url }}">sigs.k8s.io/yaml in Kubernetes 1.31</a>
          <br />
          &bull; <a href="{{ "/reports/openssl-in-nodejs-22/" | relative_url }}">OpenSSL 3.0 in Node.js 22 LTS</a>
          <br />
          &bull; <a href="{{ "/reports/hcl-in-terraform-1-9/" | relative_url }}">HashiCorp HCL in Terraform 1.9</a>
        </p>
      </aside>
    </section>

    <!-- FAQ 4: Supported Ecosystems & Package Managers -->
    <section class="article-section" id="supported-ecosystems">
      <h2>What ecosystems and package managers does Packablock support?</h2>
      
      <p>
        Packablock ingests dependency graphs and attestation blocks across language-level package managers, operating system package registries, and unmanaged native releases:
      </p>

      <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.25rem; margin-top: 1.25rem; margin-bottom: 1.75rem;">
        
        <!-- Card 1: Language Registries -->
        <div class="soft-pane" style="padding: 1.25rem 1.5rem; background: rgba(14, 27, 46, 0.7); border: 1px solid rgba(255, 255, 255, 0.08); border-radius: 8px;">
          <div style="font-size: 0.72rem; font-weight: 800; color: #22D3EE; text-transform: uppercase; letter-spacing: 0.08em; margin-bottom: 0.75rem;">
            Language Package Registries
          </div>
          <ul style="margin: 0; padding-left: 1.25rem; color: #cbd5e1; font-size: 0.88rem; line-height: 1.8;">
            <li><strong style="color: #ffffff;">Go Modules:</strong> <code>pkg:golang</code> (Go proxy / <code>go.mod</code>)</li>
            <li><strong style="color: #ffffff;">npm:</strong> <code>pkg:npm</code> (npmjs.org / <code>package-lock.json</code>)</li>
            <li><strong style="color: #ffffff;">PyPI:</strong> <code>pkg:pypi</code> (Python wheels &amp; sdist)</li>
            <li><strong style="color: #ffffff;">Cargo:</strong> <code>pkg:cargo</code> (crates.io / <code>Cargo.lock</code>)</li>
            <li><strong style="color: #ffffff;">Maven Central:</strong> <code>pkg:maven</code> (Java POM / artifacts)</li>
            <li><strong style="color: #ffffff;">NuGet:</strong> <code>pkg:nuget</code> (.NET assemblies / nuget.org)</li>
            <li><strong style="color: #ffffff;">Composer:</strong> <code>pkg:composer</code> (PHP / Packagist)</li>
            <li><strong style="color: #ffffff;">RubyGems:</strong> <code>pkg:gem</code> (Ruby / rubygems.org)</li>
            <li><strong style="color: #ffffff;">Pub:</strong> <code>pkg:pub</code> (Dart &amp; Flutter / pub.dev)</li>
            <li><strong style="color: #ffffff;">Swift PM:</strong> <code>pkg:swift</code> (Apple Swift Package Index)</li>
          </ul>
        </div>

        <!-- Card 2: OS & Binary Registries -->
        <div class="soft-pane" style="padding: 1.25rem 1.5rem; background: rgba(14, 27, 46, 0.7); border: 1px solid rgba(255, 255, 255, 0.08); border-radius: 8px;">
          <div style="font-size: 0.72rem; font-weight: 800; color: #34d399; text-transform: uppercase; letter-spacing: 0.08em; margin-bottom: 0.75rem;">
            Operating System &amp; Binary Registries
          </div>
          <ul style="margin: 0; padding-left: 1.25rem; color: #cbd5e1; font-size: 0.88rem; line-height: 1.8;">
            <li><strong style="color: #ffffff;">Debian &amp; Ubuntu:</strong> <code>pkg:deb</code> (official <code>dpkg</code> control files)</li>
            <li><strong style="color: #ffffff;">Alpine Linux:</strong> <code>pkg:apk</code> (official <code>APKBUILD</code> &amp; packages)</li>
            <li><strong style="color: #ffffff;">RPM / RHEL / Fedora:</strong> <code>pkg:rpm</code> (official RPM spec files)</li>
            <li><strong style="color: #ffffff;">No Package Manager:</strong> <code>pkg:generic</code> (unmanaged binaries, embedded C/C++ runtimes, and release tarballs)</li>
          </ul>
        </div>

      </div>

      <p style="font-size: 0.95rem; line-height: 1.6; color: #cbd5e1;">
        For each ecosystem, Packablock correlates transitive dependency trees with official upstream release registries, CVE trackers, and OpenSSF Scorecards without cloning source repositories.
      </p>
    </section>

  </div>
</article>
