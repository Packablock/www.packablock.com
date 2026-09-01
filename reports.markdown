---
layout: default
title: "Dependency Intelligence Reports"
permalink: /reports/
---

<div class="reports-hub-container" style="max-width: 1040px; margin: 0 auto; padding: 2.5rem 1rem;">
  
  <!-- Header Banner -->
  <div style="text-align: center; margin-bottom: 3rem;">
    <div style="display: inline-block; background: rgba(34, 211, 238, 0.1); border: 1px solid rgba(34, 211, 238, 0.3); color: #22D3EE; font-size: 0.8rem; font-weight: 800; padding: 0.35rem 0.85rem; border-radius: 999px; text-transform: uppercase; letter-spacing: 0.08em; margin-bottom: 1rem;">
      ✦ Supply Chain Security Intelligence
    </div>
    <h1 style="font-size: 2.75rem; font-weight: 900; line-height: 1.15; color: #ffffff; letter-spacing: -0.03em; margin-bottom: 1rem;">
      What's in the Box?
    </h1>
    <p style="font-size: 1.15rem; color: #9ca3af; max-width: 720px; margin: 0 auto; line-height: 1.6;">
      Deep, concrete dependency inspections for popular software. Explore exact resolved versions, underlying specification levels, OpenSSF Scorecards, and syntax quirks.
    </p>
  </div>

  <!-- Reports Grid -->
  <div style="display: grid; grid-template-columns: repeat(auto-fill, minmax(320px, 1fr)); gap: 1.5rem;">
    {% for report in site.data.enriched_reports %}
    <a href="{{ site.baseurl }}/reports/{{ report.slug }}/" style="display: flex; flex-direction: column; background: rgba(14, 27, 46, 0.85); border: 1px solid rgba(34, 211, 238, 0.2); border-radius: 10px; padding: 1.5rem; text-decoration: none; transition: transform 0.2s, border-color 0.2s; box-shadow: 0 10px 25px -10px rgba(0,0,0,0.5);">
      
      <div style="display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 0.75rem; gap: 0.5rem;">
        <span style="font-size: 0.7rem; font-weight: 800; color: #22D3EE; text-transform: uppercase; letter-spacing: 0.05em; background: rgba(34, 211, 238, 0.1); padding: 0.2rem 0.5rem; border-radius: 4px;">
          {{ report.category }}
        </span>
        <span style="font-size: 0.75rem; font-weight: 700; color: {% if report.deps_dev_metadata.openssf_score >= 7 %}#10B981{% elsif report.deps_dev_metadata.openssf_score >= 4 %}#F59E0B{% else %}#9ca3af{% endif %};">
          Scorecard: {{ report.deps_dev_metadata.openssf_score | default: "N/A" }}/10
        </span>
      </div>

      <h2 style="font-size: 1.25rem; font-weight: 800; color: #ffffff; margin: 0 0 0.75rem; line-height: 1.3;">
        {{ report.title }}
      </h2>

      <div style="font-family: 'IBM Plex Mono', monospace; font-size: 0.85rem; color: #a5f3fc; background: rgba(0,0,0,0.3); padding: 0.6rem 0.75rem; border-radius: 6px; margin-bottom: 1rem; border: 1px solid rgba(255,255,255,0.05);">
        <div><strong>Host:</strong> {{ report.host.name }} {{ report.host.version }}</div>
        <div><strong>Target:</strong> {{ report.target.name }} @ {{ report.target.version }}</div>
      </div>

      <p style="font-size: 0.85rem; color: #9ca3af; line-height: 1.5; margin: 0 0 1.25rem; flex-grow: 1;">
        {{ report.summary | truncate: 120 }}
      </p>

      <div style="display: flex; justify-content: space-between; align-items: center; border-top: 1px solid rgba(255,255,255,0.06); padding-top: 0.75rem; font-size: 0.75rem; color: #9ca3af;">
        <span>Lag: {{ report.deps_dev_metadata.dependency_lag_months | default: 0 }} mos</span>
        <span style="color: #22D3EE; font-weight: 700;">View Report →</span>
      </div>
    </a>
    {% endfor %}
  </div>

</div>
