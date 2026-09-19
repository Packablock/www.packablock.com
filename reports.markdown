---
layout: default
title: "Dependency Intelligence & Supply Chain Reports | Packablock"
description: "Authoritative software supply chain reports, live edge-cached vulnerability feeds, and executive regulatory compliance models."
permalink: /reports/
---

<div class="reports-hub-container">
  
  <!-- Hero Section -->
  <div class="reports-hero">
    <div class="hero-tag">
      ✦ Supply Chain Policy &amp; Dependency Intelligence
    </div>
    <h1>Supply Chain Intelligence &amp; Report Catalog</h1>
    <p class="hero-desc">
      Direct concrete dependency inspections, live edge-cached datalake feeds, and executive regulatory compliance toolkits engineered to eliminate supply chain opacity.
    </p>

    <!-- Quick Navigation Pills -->
    <div class="nav-pills">
      <a href="#inspections">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M21 21l-5.197-5.197m0 0A7.5 7.5 0 105.196 5.196a7.5 7.5 0 0010.607 10.607z"/></svg>
        Deep Dive Inspections
      </a>
      <a href="#datalake">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M3.75 3v11.25A2.25 2.25 0 006 16.5h2.25M3.75 3h-1.5m1.5 0h16.5m0 0h1.5m-1.5 0v11.25A2.25 2.25 0 0118 16.5h-2.25m-7.5 0h7.5m-7.5 0l-1 3m8.5-3l1 3m0 0l.5 1.5m-.5-1.5h-9.5m0 0l-.5 1.5"/></svg>
        Live Datalake Feeds
      </a>
      <a href="#commercial">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M3.75 12h16.5m-16.5 3.75h16.5M3.75 19.5h16.5M5.625 4.5h12.75a1.875 1.875 0 010 3.75H5.625a1.875 1.875 0 010-3.75z"/></svg>
        Executive Models &amp; Toolkits
      </a>
      <a href="#consultation">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75"/></svg>
        Enterprise Consultation
      </a>
    </div>
  </div>

  <!-- Section 1: Dependency Deep Dives & SBOM Inspections -->
  <section id="inspections" class="reports-section">
    <div class="section-header">
      <div class="section-title-wrap">
        <div class="section-badge">CONCRETE VERIFICATION</div>
        <h2>Dependency Deep Dives &amp; SBOM Inspections</h2>
      </div>
      <p class="section-subtitle">
        Deep, concrete dependency inspections for popular software. Explore exact resolved versions, underlying specification levels, OpenSSF Scorecards, and syntax quirks.
      </p>
    </div>

    <div class="reports-grid">
      {% for report in site.data.enriched_reports %}
      <a href="{{ site.baseurl }}/reports/{{ report.slug }}/" class="report-card">
        
        <div class="card-top">
          <span class="card-category">
            {{ report.category }}
          </span>
          <span class="card-score" style="color: {% if report.deps_dev_metadata.openssf_score >= 7 %}#10B981{% elsif report.deps_dev_metadata.openssf_score >= 4 %}#F59E0B{% else %}#9ca3af{% endif %};">
            Scorecard: {{ report.deps_dev_metadata.openssf_score | default: "N/A" }}/10
          </span>
        </div>

        <h3 class="card-title">
          {{ report.title }}
        </h3>

        <div class="card-meta-box">
          <div class="meta-row">
            <span class="meta-label">Host:</span>
            <span class="meta-val">{{ report.host.name }} {{ report.host.version }}</span>
          </div>
          <div class="meta-row">
            <span class="meta-label">Target:</span>
            <span class="meta-val">{{ report.target.name }} @ {{ report.target.version }}</span>
          </div>
        </div>

        <p class="card-summary">
          {{ report.summary | truncate: 120 }}
        </p>

        <div class="card-footer">
          <span>Lag: {{ report.deps_dev_metadata.dependency_lag_months | default: 0 }} mos</span>
          <span class="card-link-cta">
            View Report <span class="card-link-arrow">→</span>
          </span>
        </div>
      </a>
      {% endfor %}
    </div>
  </section>

  <!-- Section 2: Open Datalake Live Feeds -->
  <section id="datalake" class="reports-section">
    <div class="section-header">
      <div class="section-title-wrap">
        <div class="section-badge">EDGE-CACHED CDN FEEDS</div>
        <h2>Packablock Open Datalake</h2>
      </div>
      <p class="section-subtitle">
        Public, edge-cached, zero-auth data feeds served via Cloudflare Pages CDN at <code>data.packablock.com</code> with permissive CORS headers for instant spreadsheet ingestion.
      </p>
    </div>

    <!-- Formula Box Callout -->
    <div class="formula-box">
      <div class="formula-title">✦ Instant Zero-OAuth Spreadsheet Syndication</div>
      <div class="formula-code">=IMPORTDATA("https://data.packablock.com/benchmarks/cisa-kev-epss.csv")</div>
      <p class="formula-note">
        Paste directly into cell <strong>A1</strong> of Google Sheets or Microsoft Excel. Streams fresh, cryptographically attested data on demand with zero macros, zero API tokens, and zero popup warnings.
      </p>
    </div>

    <div class="datalake-grid">
      <!-- Feed 1: CISA KEV & EPSS -->
      <div class="datalake-card">
        <span class="feed-badge">DAILY SYNC</span>
        <h3>CISA KEV &amp; EPSS Crosswalk</h3>
        <p>1,713+ active CISA Known Exploited Vulnerabilities joined with FIRST.org EPSS exploit probability scores and composite priority tiers.</p>
        <div class="feed-endpoint">benchmarks/cisa-kev-epss.csv</div>
        <a href="https://data.packablock.com/benchmarks/cisa-kev-epss.csv" class="feed-action" target="_blank" rel="noopener">
          Download CSV <span>↗</span>
        </a>
      </div>

      <!-- Feed 2: Runtime SBOM Matrix -->
      <div class="datalake-card">
        <span class="feed-badge">CANONICAL</span>
        <h3>Runtime Engine SBOM Crosswalk</h3>
        <p>Go, Node.js, Python, and Rust runtimes mapped to underlying cryptographic libraries, parsers, CycloneDX 1.5 JSON snippets, and PURLs.</p>
        <div class="feed-endpoint">supply-chain/runtime-sbom-matrix.csv</div>
        <a href="https://data.packablock.com/supply-chain/runtime-sbom-matrix.csv" class="feed-action" target="_blank" rel="noopener">
          Download CSV <span>↗</span>
        </a>
      </div>

      <!-- Feed 3: Parser Quirks -->
      <div class="datalake-card">
        <span class="feed-badge">SYNTAX SPEC</span>
        <h3>Parser Quirks &amp; Syntax Drift</h3>
        <p>Cross-ecosystem discrepancy matrix covering YAML 1.1 vs 1.2, HCL2 scoping, JSON deserialization, and shadow parameter caveats.</p>
        <div class="feed-endpoint">supply-chain/parser-quirks.csv</div>
        <a href="https://data.packablock.com/supply-chain/parser-quirks.csv" class="feed-action" target="_blank" rel="noopener">
          Download CSV <span>↗</span>
        </a>
      </div>

      <!-- Feed 4: FCC Broadband Labels -->
      <div class="datalake-card">
        <span class="feed-badge">REGULATORY</span>
        <h3>FCC Broadband Nutrition Labels</h3>
        <p>28 tier-1 residential broadband plan specifications across 9 major ISPs cataloging base fees, promotional roll-offs, and $/Mbps economics.</p>
        <div class="feed-endpoint">telecom/isp-labels.csv</div>
        <a href="https://data.packablock.com/telecom/isp-labels.csv" class="feed-action" target="_blank" rel="noopener">
          Download CSV <span>↗</span>
        </a>
      </div>

      <!-- Feed 5: SEC Form 8-K Incidents -->
      <div class="datalake-card">
        <span class="feed-badge">GOVERNANCE</span>
        <h3>SEC Form 8-K Incident Tracker</h3>
        <p>Item 1.05 material cyber incident filings under SEC Release 33-11216, disclosure lags, remediation costs, and DOJ delay exemptions.</p>
        <div class="feed-endpoint">regulatory/sec-8k-incidents.csv</div>
        <a href="https://data.packablock.com/regulatory/sec-8k-incidents.csv" class="feed-action" target="_blank" rel="noopener">
          Download CSV <span>↗</span>
        </a>
      </div>

      <!-- Feed 6: Corporate FOSS Stewardship -->
      <div class="datalake-card">
        <span class="feed-badge">BENCHMARK</span>
        <h3>FOSS Stewardship Arbitrage</h3>
        <p>Financial benchmarks comparing $3.5M+ in Big 4 advisory retainer spend against direct upstream open-source foundation grants and attestation.</p>
        <div class="feed-endpoint">benchmarks/stewardship-arbitrage.csv</div>
        <a href="https://data.packablock.com/benchmarks/stewardship-arbitrage.csv" class="feed-action" target="_blank" rel="noopener">
          Download CSV <span>↗</span>
        </a>
      </div>

      <!-- Feed 7: Breach Settlements Database -->
      <div class="datalake-card">
        <span class="feed-badge">LEGAL INTEL</span>
        <h3>Cyber Breach Settlements &amp; Fines</h3>
        <p>Empirical database of $6.1B+ in regulatory enforcement fines, class-action funds, and court-ordered mandatory security CAPEX decrees.</p>
        <div class="feed-endpoint">benchmarks/breach-settlements.csv</div>
        <a href="https://data.packablock.com/benchmarks/breach-settlements.csv" class="feed-action" target="_blank" rel="noopener">
          Download CSV <span>↗</span>
        </a>
      </div>

      <!-- Feed 8: Smart Home IoT Trust Mark -->
      <div class="datalake-card">
        <span class="feed-badge">TELECOM/IOT</span>
        <h3>Smart Home &amp; IoT Trust Mark</h3>
        <p>Consumer and enterprise IoT benchmarks evaluating compliance against FCC U.S. Cyber Trust Mark (FCC 24-26) and NIST IR 8425 baselines.</p>
        <div class="feed-endpoint">telecom/iot-trust-mark.csv</div>
        <a href="https://data.packablock.com/telecom/iot-trust-mark.csv" class="feed-action" target="_blank" rel="noopener">
          Download CSV <span>↗</span>
        </a>
      </div>

      <!-- Feed 9: 10-30 Yr IoT Hardware Maintenance TCO -->
      <div class="datalake-card">
        <span class="feed-badge">HARDWARE TCO</span>
        <h3>10–30 Yr IoT Maintenance TCO</h3>
        <p>Total cost of ownership models across 8 hardware asset classes navigating EU Cyber Resilience Act Article 10(6) extended lifetime obligations.</p>
        <div class="feed-endpoint">benchmarks/iot-lifecycle-tco.csv</div>
        <a href="https://data.packablock.com/benchmarks/iot-lifecycle-tco.csv" class="feed-action" target="_blank" rel="noopener">
          Download CSV <span>↗</span>
        </a>
      </div>

      <!-- Feed 10: Executive Cyber Metrics -->
      <div class="datalake-card">
        <span class="feed-badge">EXECUTIVE</span>
        <h3>Executive Cyber Metrics Index</h3>
        <p>Cross-sector benchmarks across 8 industries tracking dwell times, phishing test failure rates, and cyber insurance loss ratios.</p>
        <div class="feed-endpoint">benchmarks/executive-cyber-metrics.csv</div>
        <a href="https://data.packablock.com/benchmarks/executive-cyber-metrics.csv" class="feed-action" target="_blank" rel="noopener">
          Download CSV <span>↗</span>
        </a>
      </div>

      <!-- Feed 11: Zero-SaaS OSS Dependencies -->
      <div class="datalake-card">
        <span class="feed-badge">SUPPLY CHAIN</span>
        <h3>Zero-SaaS OSS License Auditor</h3>
        <p>29 enterprise software packages analyzed for SPDX licenses, copyleft triggers, OpenSSF Scorecards, and transitive license liability.</p>
        <div class="feed-endpoint">supply-chain/deps-ossf.csv</div>
        <a href="https://data.packablock.com/supply-chain/deps-ossf.csv" class="feed-action" target="_blank" rel="noopener">
          Download CSV <span>↗</span>
        </a>
      </div>

      <!-- Feed 12: M&A Tech Haircut Benchmarks -->
      <div class="datalake-card">
        <span class="feed-badge">VALUATION</span>
        <h3>M&amp;A Supply Chain Haircuts</h3>
        <p>Private equity and M&amp;A buy-side benchmarks for tech debt valuation discounts, escrow holdbacks, and post-merger supply chain remediation.</p>
        <div class="feed-endpoint">benchmarks/mna-haircut-benchmarks.csv</div>
        <a href="https://data.packablock.com/benchmarks/mna-haircut-benchmarks.csv" class="feed-action" target="_blank" rel="noopener">
          Download CSV <span>↗</span>
        </a>
      </div>
    </div>

    <div style="text-align: center; margin-top: 1.5rem;">
      <a href="https://data.packablock.com/" class="btn-secondary" target="_blank" rel="noopener">
        Explore Full Datalake Directory (data.packablock.com) &rarr;
      </a>
    </div>
  </section>

  <!-- Section 3: Commercial Toolkits & Decision Packs -->
  <section id="commercial" class="reports-section">
    <div class="section-header">
      <div class="section-title-wrap">
        <div class="section-badge">COMMERCIAL TOOLKITS</div>
        <h2>Living Spreadsheets &amp; Executive Packs</h2>
      </div>
      <p class="section-subtitle">
        Turn-key analytical models, 16:9 widescreen board decks, and living workbooks engineered for security practitioners, CISOs, and M&amp;A due diligence teams.
      </p>
    </div>

    <div class="commercial-grid">
      <!-- Track A Column -->
      <div class="commercial-column">
        <div class="track-header">
          <div class="track-badge">TRACK A &bull; LIVING SPREADSHEETS</div>
          <h3>Analyst &amp; Engineer Workbooks</h3>
          <p>Self-refreshing workbooks featuring zero-popup live datalake formulas, WCAG AAA styling, and automated scoring metrics ($5 &ndash; $9).</p>
        </div>

        <div class="product-list">
          <div class="product-item">
            <div class="item-top">
              <span class="item-id">SC-01</span>
              <span class="item-price">$9.00</span>
            </div>
            <div class="item-title">Runtime Crosswalk &amp; 1-Click SBOM Generator</div>
            <p class="item-desc">Interactive component resolver mapping host runtimes to embedded crypto engines with CycloneDX/SPDX export formatting.</p>
          </div>

          <div class="product-item">
            <div class="item-top">
              <span class="item-id">SC-02</span>
              <span class="item-price">$5.00</span>
            </div>
            <div class="item-title">Parser Quirks &amp; Syntax Drift Rosetta Stone</div>
            <p class="item-desc">Comparative syntax reference matrix detailing multi-ecosystem parsing discrepancies, security caveats, and attack mitigations.</p>
          </div>

          <div class="product-item">
            <div class="item-top">
              <span class="item-id">SEC-03</span>
              <span class="item-price">$9.00</span>
            </div>
            <div class="item-title">CISA KEV &amp; EPSS Exploitation Velocity Crosswalk</div>
            <p class="item-desc">Dynamic risk prioritization matrix combining CISA KEV catalog with EPSS exploitation percentiles and SLA timelines.</p>
          </div>

          <div class="product-item">
            <div class="item-top">
              <span class="item-id">TEL-01</span>
              <span class="item-price">$9.00</span>
            </div>
            <div class="item-title">FCC Broadband Nutrition Label Matrix</div>
            <p class="item-desc">Consumer broadband comparison model analyzing 28 tiers across 9 major ISPs with true cost and $/Mbps unit cost calculations.</p>
          </div>

          <div class="product-item">
            <div class="item-top">
              <span class="item-id">SEC-01</span>
              <span class="item-price">$9.00</span>
            </div>
            <div class="item-title">Executive Cybersecurity &amp; Risk Metric Index</div>
            <p class="item-desc">Cross-sector benchmark index mapping 8 industries against dwell time, cyber loss ratios, and NIST CSF / EU CRA controls.</p>
          </div>

          <div class="product-item">
            <div class="item-top">
              <span class="item-id">SC-03</span>
              <span class="item-price">$8.00</span>
            </div>
            <div class="item-title">Zero-SaaS OSS Dependency &amp; License Auditor</div>
            <p class="item-desc">Interactive project dependency risk classifier evaluating SPDX licenses, copyleft triggers, and OpenSSF Scorecards.</p>
          </div>

          <div class="product-item">
            <div class="item-top">
              <span class="item-id">STN-01</span>
              <span class="item-price">$7.00</span>
            </div>
            <div class="item-title">Main Street Merchant Wi-Fi &amp; PCI Audit</div>
            <p class="item-desc">Interactive 20-point retail network security checklist, VLAN isolation tester, and PCI-DSS v4.0 SAQ-A readiness calculator.</p>
          </div>

          <div class="product-item">
            <div class="item-top">
              <span class="item-id">STN-02</span>
              <span class="item-price">$7.00</span>
            </div>
            <div class="item-title">Family Tech Lead Network Defense Kit</div>
            <p class="item-desc">Home network defense checklist, IoT telemetry isolation matrix, and Pi-hole / AdGuard Home DNS blocklist catalog.</p>
          </div>

          <div class="product-item">
            <div class="item-top">
              <span class="item-id">SEC-02</span>
              <span class="item-price">$9.00</span>
            </div>
            <div class="item-title">SEC Form 8-K Item 1.05 Incident &amp; Materiality Tracker</div>
            <p class="item-desc">Item 1.05 filing tracker with quantitative materiality scoring model, disclosure lag calculators, and DOJ delay tracking.</p>
          </div>

          <div class="product-item">
            <div class="item-top">
              <span class="item-id">TEL-02</span>
              <span class="item-price">$7.00</span>
            </div>
            <div class="item-title">Smart Home &amp; IoT Trust Mark Tracker</div>
            <p class="item-desc">FCC 24-26 Cyber Trust Mark eligibility tracker and interactive 15-point NIST IR 8425 consumer pre-procurement audit checklist.</p>
          </div>
        </div>
      </div>

      <!-- Track B Column -->
      <div class="commercial-column">
        <div class="track-header">
          <div class="track-badge">TRACK B &bull; EXECUTIVE PACKS</div>
          <h3>Executive Consulting Bundles</h3>
          <p>Decision frameworks, board-ready 16:9 presentations, and financial exposure models for corporate leadership and audit defense ($79 &ndash; $149).</p>
        </div>

        <div class="product-list">
          <div class="product-item">
            <div class="item-top">
              <span class="item-id">CRA-01</span>
              <span class="item-price">$149.00</span>
            </div>
            <div class="item-title">EU CRA Financial Reserve &amp; Penalty Liability Model</div>
            <p class="item-desc">4-scenario Monte Carlo financial exposure workbook, 16:9 board-ready presentation deck, and self-assessment conformity checklist.</p>
          </div>

          <div class="product-item">
            <div class="item-top">
              <span class="item-id">CRA-02</span>
              <span class="item-price">$129.00</span>
            </div>
            <div class="item-title">M&amp;A Software Supply Chain Haircut Matrix &amp; Board Deck</div>
            <p class="item-desc">Pre-acquisition technical debt discounting framework, inherited vulnerability remediation pricing, and 12-slide investment committee deck.</p>
          </div>

          <div class="product-item">
            <div class="item-top">
              <span class="item-id">CRA-04</span>
              <span class="item-price">$79.00</span>
            </div>
            <div class="item-title">FOSS Stewardship vs. Big 4 Capital Allocation Model</div>
            <p class="item-desc">Financial arbitrage model and 12-slide board deck demonstrating 430%+ ROI by directing advisory spend to upstream foundation grants.</p>
          </div>

          <div class="product-item">
            <div class="item-top">
              <span class="item-id">SEC-04</span>
              <span class="item-price">$99.00</span>
            </div>
            <div class="item-title">Cyber Breach Settlement &amp; Penalty Model &amp; Board Deck</div>
            <p class="item-desc">Analysis of $6.1B+ in enforcement fines, class actions, and court-ordered security decrees with 12-slide board deck and fine estimator.</p>
          </div>

          <div class="product-item">
            <div class="item-top">
              <span class="item-id">CRA-03</span>
              <span class="item-price">$89.00</span>
            </div>
            <div class="item-title">10–30 Yr IoT Hardware Maintenance TCO Model &amp; Deck</div>
            <p class="item-desc">20-year fleet cash flow projection engine, embedded silicon obsolescence matrix, and 12-slide board deck navigating CRA Art. 10(6).</p>
          </div>

          <div class="product-item">
            <div class="item-top">
              <span class="item-id">ADVISORY</span>
              <span class="item-price">Custom</span>
            </div>
            <div class="item-title">Private SBOM &amp; Cryptographic Attestation Audits</div>
            <p class="item-desc">Tailored supply chain pipeline reviews, Windmill DAG attestation automation, and compliance certification support.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Section 4: Enterprise Audit Consultation Inquiry -->
  <section id="consultation" class="reports-section" style="margin-bottom: 2rem;">
    <div class="section-header">
      <div class="section-title-wrap">
        <div class="section-badge">BESPOKE ADVISORY</div>
        <h2>Enterprise Supply Chain Audits</h2>
      </div>
      <p class="section-subtitle">
        Partner with our security engineers to audit proprietary dependencies, implement continuous cryptographic attestations, or prepare for EU CRA enforcement.
      </p>
    </div>

    <div class="consultation-card">
      <div class="consultation-title">Request Custom Security &amp; SBOM Intelligence</div>
      <p class="consultation-desc">
        Submit your inquiry below to discuss custom dependency mapping, CRA readiness assessments, or dedicated Windmill pipeline deployments for your organization.
      </p>

      <script src="https://js-na2.hsforms.net/forms/embed/247045717.js" defer></script>
      <div class="hs-form-frame" data-region="na2" data-form-id="77f28b2c-e7e2-4d98-aa73-5254b3b03f1e" data-portal-id="247045717"></div>
    </div>
  </section>

</div>
