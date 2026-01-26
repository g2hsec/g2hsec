<!-- =========================================================
  Portfolio README (No external images required)
  - Cinematic layout with "cards" using HTML tables
  - Scan-friendly: KPI → Featured → Proof → Capability → Lab
  - Optional Mermaid visuals (GitHub supports Mermaid)
========================================================= -->

<h1 align="center">[YOUR NAME / HANDLE]</h1>
<p align="center"><strong>Security Research · Red Team · Detection Engineering</strong></p>
<p align="center"><sub>Evidence-first · Reproducible PoC · Code-level root cause · Practical impact</sub></p>

<hr/>

<!-- ===================== KPI STRIP ===================== -->
<table>
  <tr>
    <td align="center" width="25%"><strong>Focus</strong><br/><sub>Web · Cloud · DevSecOps</sub></td>
    <td align="center" width="25%"><strong>Strength</strong><br/><sub>AuthZ · Injection · Supply Chain</sub></td>
    <td align="center" width="25%"><strong>Output</strong><br/><sub>PoC · Patch Guidance · Detections</sub></td>
    <td align="center" width="25%"><strong>Style</strong><br/><sub>High-signal · Low-noise</sub></td>
  </tr>
</table>

<p align="center">
  <a href="#featured">Featured</a> ·
  <a href="#proof">Proof</a> ·
  <a href="#capabilities">Capabilities</a> ·
  <a href="#tooling">Tooling</a> ·
  <a href="#lab--research">Lab</a> ·
  <a href="#contact">Contact</a>
</p>

---

## Executive Snapshot

> I deliver **high-signal security outcomes** by walking the full chain:  
> **Discover → Prove → Explain → Fix/Detect**

<table>
  <tr>
    <td valign="top" width="50%">
      <h3>What I do</h3>
      <ul>
        <li><b>Vulnerability research</b> with strict threat modeling and boundary analysis</li>
        <li><b>Pentest/Red team</b> scenarios aligned to enterprise realities</li>
        <li><b>Detection engineering</b> with validated telemetry and tuning</li>
      </ul>
    </td>
    <td valign="top" width="50%">
      <h3>What you get</h3>
      <ul>
        <li><b>Reproducible PoC bundles</b> (steps, env assumptions, evidence)</li>
        <li><b>Patch guidance</b> (root cause + minimal-risk fix strategy)</li>
        <li><b>Detection pack</b> (rules + mapping + validation notes)</li>
      </ul>
    </td>
  </tr>
</table>

---

## Featured

> Keep this section tight. 4–8 items is the sweet spot.

<table>
  <tr>
    <td valign="top" width="50%">
      <h3>⭐ [FEATURED #1 TITLE]</h3>
      <ul>
        <li><b>Category</b>: [CWE / type]</li>
        <li><b>Impact</b>: [C/I/A + what breaks]</li>
        <li><b>Prereq</b>: [role/auth/conditions]</li>
        <li><b>Evidence</b>: [link]</li>
        <li><b>PoC</b>: [link]</li>
        <li><b>Fix hint</b>: [one-liner]</li>
      </ul>
    </td>
    <td valign="top" width="50%">
      <h3>⭐ [FEATURED #2 TITLE]</h3>
      <ul>
        <li><b>Category</b>: [CWE / type]</li>
        <li><b>Impact</b>: [C/I/A + what breaks]</li>
        <li><b>Prereq</b>: [role/auth/conditions]</li>
        <li><b>Evidence</b>: [link]</li>
        <li><b>PoC</b>: [link]</li>
        <li><b>Fix hint</b>: [one-liner]</li>
      </ul>
    </td>
  </tr>

  <tr>
    <td valign="top" width="50%">
      <h3>🧩 [TOOL/PROJECT #1]</h3>
      <ul>
        <li><b>Type</b>: [triage automation / log enrichment / lab orchestration]</li>
        <li><b>Outcome</b>: [FP↓ / coverage↑ / time-to-triage↓]</li>
        <li><b>Repo</b>: [link]</li>
      </ul>
    </td>
    <td valign="top" width="50%">
      <h3>🧩 [TOOL/PROJECT #2]</h3>
      <ul>
        <li><b>Type</b>: [detector pack / pipeline / parser]</li>
        <li><b>Outcome</b>: [measurable result]</li>
        <li><b>Repo</b>: [link]</li>
      </ul>
    </td>
  </tr>
</table>

---

## Proof

<table>
  <tr>
    <td valign="top" width="33%">
      <h3>Findings</h3>
      <ul>
        <li><b>CVE</b>: [CVE-YYYY-XXXX] / [candidate]</li>
        <li><b>Advisories</b>: [link], [link]</li>
        <li><b>Writeups</b>: [link], [link]</li>
      </ul>
    </td>
    <td valign="top" width="33%">
      <h3>Programs</h3>
      <ul>
        <li><b>HackerOne</b>: [profile link]</li>
        <li><b>Intigriti</b>: [profile link]</li>
        <li><b>VDPs</b>: [link]</li>
      </ul>
    </td>
    <td valign="top" width="33%">
      <h3>Artifacts</h3>
      <ul>
        <li><b>PoC bundles</b>: deterministic steps + evidence pack</li>
        <li><b>Detection pack</b>: rules + mapping + validation notes</li>
        <li><b>Lab manifests</b>: reproducible infrastructure + scenarios</li>
      </ul>
    </td>
  </tr>
</table>

<details>
<summary><strong>Evidence Standard (What I attach)</strong></summary>

- Root-cause: code path + condition + boundary broken
- Reproduction: exact steps + environment assumptions
- Evidence: logs/pcap/requests + before/after diffs
- Risk: practical impact narrative (not speculative)
- Fix: minimal-risk remediation guidance + regression notes

</details>

---

## Capabilities

<table>
  <tr>
    <td valign="top" width="50%">
      <h3>Offensive</h3>
      <ul>
        <li><b>Web/API</b>: authz/IDOR, injection, SSRF, deserialization, business logic</li>
        <li><b>Multi-tenant</b>: org isolation, token scopes, delegated access abuse</li>
        <li><b>Supply chain</b>: CI/CD abuse paths, secrets, artifact integrity</li>
      </ul>
    </td>
    <td valign="top" width="50%">
      <h3>Defensive</h3>
      <ul>
        <li><b>Detection</b>: Suricata/Zeek/Sigma-style logic, tuning, validation</li>
        <li><b>IR</b>: triage playbooks, evidence capture, timeline reconstruction</li>
        <li><b>Signal engineering</b>: noise filters, correlation, enrichment</li>
      </ul>
    </td>
  </tr>
</table>

---

## Tooling

**Languages**: Python · Bash · [Go/JS/Ruby/…]  
**Security**: Burp Suite · [ffuf/nuclei/…] · Suricata · Zeek · ELK/Wazuh  
**Infra/Lab**: Docker · VMware/ESXi · pfSense · [GitLab/Jenkins/…]  

---

## Lab & Research

> A realistic lab to validate both **exploitation** and **detection**.

- Segmentation: **DMZ / Corp / Dev**
- Controls: **WAF (ModSecurity)** · **IPS (Suricata)** · centralized telemetry (**ELK/Wazuh**)
- Scenarios: **CI/CD chain** (GitLab→Jenkins→deploy) + adversary emulation + detection validation

```mermaid
flowchart LR
  A[Attacker / Red Team] --> B[Edge: pfSense]
  B --> C[IPS: Suricata]
  C --> D[WAF: ModSecurity]
  D --> E[Apps: Web/API]
  E --> F[Telemetry: ELK/Wazuh]
  F --> G[Detection Pack / Rules]
  G --> H[Validation: FP↓ / Coverage↑]
