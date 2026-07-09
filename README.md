<!--
  Profile README · g2h / Gyu-hyeok Lee

  GitHub-compatible stack:
  - Markdown
  - GitHub-rendered HTML
  - Shields.io badges
  - Typing SVG
  - Capsule Render
  - Mermaid diagram
  - <details>/<summary>
  - Optional third-party dynamic GitHub cards

  Account:
  - GitHub username: g2hsec
  - Profile repository: g2hsec/g2hsec
-->

<div align="center">

<img
  src="https://capsule-render.vercel.app/api?type=waving&height=230&color=0:0D1117,45:1F6FEB,100:B31B1B&text=g2h%20%7C%20Gyu-hyeok%20Lee&fontColor=F0F6FC&fontSize=44&fontAlignY=37&desc=Offensive%20Security%20%C2%B7%20Vulnerability%20Research%20%C2%B7%20Coordinated%20Disclosure&descAlignY=58&descSize=16&animation=fadeIn"
  alt="g2h profile header"
/>

<h3>Security Researcher · Penetration Tester · Vulnerability Researcher</h3>

<p>
  <img
    src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=18&duration=2600&pause=700&color=58A6FF&center=true&vCenter=true&width=720&lines=Offensive+Security+%7C+Vulnerability+Research;Production-Scope+Pentest+%7C+Code-First+Research;Read+Deeply+%E2%86%92+Prove+Cleanly+%E2%86%92+Coordinate+Responsibly"
    alt="Typing SVG"
  />
</p>

<p>
  <a href="https://github.com/g2hsec">
    <img alt="GitHub" src="https://img.shields.io/badge/GitHub-g2hsec-0D1117?style=for-the-badge&logo=github&logoColor=white" />
  </a>
  <a href="#selected-findings">
    <img alt="CVE" src="https://img.shields.io/badge/CVE-6%20credited-B31B1B?style=for-the-badge&labelColor=0D1117" />
  </a>
  <a href="#research-focus">
    <img alt="Focus" src="https://img.shields.io/badge/Focus-Web%20%7C%20Mobile%20%7C%20Pentest-1F6FEB?style=for-the-badge&labelColor=0D1117" />
  </a>
  <a href="#operating-model">
    <img alt="Method" src="https://img.shields.io/badge/Method-Read%20%E2%86%92%20Prove%20%E2%86%92%20Coordinate-238636?style=for-the-badge&labelColor=0D1117" />
  </a>
</p>

<p>
  <a href="#mission">Mission</a>
  ·
  <a href="#selected-findings">Selected Findings</a>
  ·
  <a href="#research-focus">Research Focus</a>
  ·
  <a href="#operating-model">Operating Model</a>
  ·
  <a href="#toolbelt">Toolbelt</a>
  ·
  <a href="#github-signal">GitHub Signal</a>
  ·
  <a href="#contact">Contact</a>
</p>

</div>

---

## Mission

```text
g2h@research:~$ whoami
security researcher / penetration tester

g2h@research:~$ focus
offensive security · vulnerability research · production-scope assessment

g2h@research:~$ principle
read deeply → prove cleanly → report precisely → coordinate responsibly
```

I work in **offensive security**: penetration testing, vulnerability research, and production-scope security assessment across web, mobile, and internal systems.

My work focuses on the places where real systems disagree about trust:

- an application route and a framework route disagree about authentication;
- a public object accidentally expands into private configuration;
- a tenant boundary depends on legacy metadata;
- a client-side assumption is treated as a server-side guarantee;
- a parser, template engine, stream, proxy, or framework interprets the same value differently.

<p>
  <img alt="Security research" src="https://img.shields.io/badge/Security-Research-B31B1B?style=for-the-badge&labelColor=0D1117" />
  <img alt="Pentest" src="https://img.shields.io/badge/Pentest-Production%20Scope-1F6FEB?style=for-the-badge&labelColor=0D1117" />
  <img alt="Disclosure" src="https://img.shields.io/badge/Disclosure-Coordinated-238636?style=for-the-badge&labelColor=0D1117" />
</p>

---

## Operating principles

### 01. Read before fuzzing

Most reportable bugs are hidden in logic, not payload lists.  
I start with source, traffic, routes, roles, state, and assumptions.

### 02. Model the boundary

The target is rarely just an endpoint.  
The target is usually a boundary: auth, tenant, session, origin, parser, framework, ownership, or trust.

### 03. Prove with minimum noise

A finding should have a deterministic PoC, pinned preconditions, and a clean reproduction path.  
No destructive test. No “probably exploitable.” No vague impact claim.

### 04. Write for the fix

The report should explain the vulnerable path, the failing invariant, the concrete impact, and the patch direction.

---

## Selected findings

> Six CVEs credited in 2026. Full version matrices, affected configurations, and vendor-specific details live in each advisory.

<table>
<tr>
<td valign="top">

### Spring Boot — Actuator authentication bypass

<p>
  <a href="https://spring.io/security/cve-2026-22731/">
    <img alt="CVE-2026-22731" src="https://img.shields.io/badge/CVE--2026--22731-High%208.2-B31B1B?style=flat-square&labelColor=0D1117" />
  </a>
  <a href="https://spring.io/security/cve-2026-22733/">
    <img alt="CVE-2026-22733" src="https://img.shields.io/badge/CVE--2026--22733-High%208.2-B31B1B?style=flat-square&labelColor=0D1117" />
  </a>
</p>

Application endpoints declared under Actuator Health-group or CloudFoundry paths are served without authentication.

<ul>
  <li><b>Affected line:</b> Spring Boot <code>2.7 → 4.0</code></li>
  <li><b>Bug class:</b> framework integration / authentication boundary confusion</li>
  <li><b>Core issue:</b> Actuator path mapping can win over the application's intended security configuration.</li>
  <li><b>Impact style:</b> unauthenticated access to protected application paths under specific endpoint mappings.</li>
</ul>

</td>
</tr>

<tr>
<td valign="top">

### Spring Framework — MVC / WebFlux flaws

<p>
  <a href="https://spring.io/security/cve-2026-22735/">
    <img alt="CVE-2026-22735" src="https://img.shields.io/badge/CVE--2026--22735-Low%202.6-238636?style=flat-square&labelColor=0D1117" />
  </a>
  <a href="https://spring.io/security/cve-2026-22737/">
    <img alt="CVE-2026-22737" src="https://img.shields.io/badge/CVE--2026--22737-Medium%205.9-DAA520?style=flat-square&labelColor=0D1117" />
  </a>
</p>

Two Spring Framework findings around stream framing and template path resolution.

<ul>
  <li>
    <b><a href="https://spring.io/security/cve-2026-22735/">CVE-2026-22735</a>:</b>
    SSE stream corruption through unvalidated newlines in <code>SseEmitter</code> / <code>ServerSentEvent</code> <code>id</code> and <code>event</code> fields.
  </li>
  <li>
    <b><a href="https://spring.io/security/cve-2026-22737/">CVE-2026-22737</a>:</b>
    script-template path traversal where JRuby/Jython template views can resolve files outside configured locations.
  </li>
  <li><b>Bug class:</b> parser boundary / stream framing / path resolution</li>
  <li><b>Impact style:</b> downstream framing corruption and template path boundary bypass.</li>
</ul>

</td>
</tr>

<tr>
<td valign="top">

### Grafana — datasource exposure & tenant boundary weakness

<p>
  <a href="https://grafana.com/security/security-advisories/cve-2026-27877">
    <img alt="CVE-2026-27877" src="https://img.shields.io/badge/CVE--2026--27877-Medium%206.5-DAA520?style=flat-square&labelColor=0D1117" />
  </a>
  <a href="https://grafana.com/security/security-advisories/cve-2026-21727/">
    <img alt="CVE-2026-21727" src="https://img.shields.io/badge/CVE--2026--21727-Low%203.3-238636?style=flat-square&labelColor=0D1117" />
  </a>
</p>

Two Grafana findings around shared platform objects crossing visibility, ownership, or organization boundaries.

<ul>
  <li>
    <b><a href="https://grafana.com/security/security-advisories/cve-2026-27877">CVE-2026-27877</a>:</b>
    public dashboards leak passwords for all direct data sources, even when those data sources are not referenced by the public dashboard.
  </li>
  <li>
    <b><a href="https://grafana.com/security/security-advisories/cve-2026-21727/">CVE-2026-21727</a>:</b>
    legacy <code>org_id = 0</code> correlation records cross the tenant boundary, allowing a datasource-management user to read and permanently delete another organization's correlation data.
  </li>
  <li><b>Bug class:</b> sensitive data exposure / multi-tenant authorization flaw</li>
  <li><b>Boundary:</b> public dashboard → private datasource config / organization isolation</li>
  <li><b>Research theme:</b> shared platform metadata accidentally crossing tenant or visibility boundaries.</li>
</ul>

</td>
</tr>
</table>

<details>
<summary><b>Finding validation model</b></summary>

<br/>

Every report I send should be reproducible without guessing.

<ul>
  <li><b>Root cause:</b> the code path, framework behavior, or trust-boundary mismatch</li>
  <li><b>Preconditions:</b> exact version, configuration, role, endpoint, and state</li>
  <li><b>PoC:</b> minimal, deterministic, non-destructive reproduction</li>
  <li><b>Impact:</b> concrete security consequence, not theoretical language</li>
  <li><b>Fix direction:</b> patch suggestion aligned with the actual source</li>
  <li><b>Verification:</b> how to prove the fix closes the bug</li>
</ul>

</details>

---

## Research focus

### Web security

Server-side logic flaws, authentication and authorization boundaries, IDOR, tenant isolation, SSRF, deserialization, and API design mistakes that scanners often miss.

<p>
  <img alt="Web" src="https://img.shields.io/badge/Web-Logic%20Flaws-B31B1B?style=flat-square&labelColor=0D1117" />
  <img alt="Auth" src="https://img.shields.io/badge/Auth-Boundaries-1F6FEB?style=flat-square&labelColor=0D1117" />
  <img alt="Tenant" src="https://img.shields.io/badge/Tenant-Isolation-238636?style=flat-square&labelColor=0D1117" />
  <img alt="SSRF" src="https://img.shields.io/badge/SSRF-Parser%20Gaps-8E44AD?style=flat-square&labelColor=0D1117" />
</p>

### Mobile security

Android / iOS client-server trust assumptions, insecure local storage, IPC and deep-link abuse, pinning bypass, and backend APIs reachable outside the app.

<p>
  <img alt="Android" src="https://img.shields.io/badge/Android-Client%20Trust-3DDC84?style=flat-square&logo=android&logoColor=white&labelColor=0D1117" />
  <img alt="iOS" src="https://img.shields.io/badge/iOS-Backend%20Trust-000000?style=flat-square&logo=apple&logoColor=white&labelColor=0D1117" />
  <img alt="Frida" src="https://img.shields.io/badge/Frida-Runtime%20Analysis-D53A3A?style=flat-square&labelColor=0D1117" />
  <img alt="Objection" src="https://img.shields.io/badge/Objection-Mobile%20Runtime-DAA520?style=flat-square&labelColor=0D1117" />
</p>

### Penetration testing

Internal network pivots, identity and session weaknesses, CI/CD trust paths, supply-chain exposure, and end-to-end attack chains instead of single-issue pokes.

<p>
  <img alt="Internal" src="https://img.shields.io/badge/Internal-Pivoting-B31B1B?style=flat-square&labelColor=0D1117" />
  <img alt="Identity" src="https://img.shields.io/badge/Identity-Session%20Weakness-1F6FEB?style=flat-square&labelColor=0D1117" />
  <img alt="CI/CD" src="https://img.shields.io/badge/CI%2FCD-Trust%20Paths-DAA520?style=flat-square&labelColor=0D1117" />
  <img alt="Attack Chain" src="https://img.shields.io/badge/Attack%20Chain-End--to--End-238636?style=flat-square&labelColor=0D1117" />
</p>

### AI × Offensive Security

How LLMs actually help during real engagements: recon synthesis, source triage, payload generation, finding deduplication, and report drafting without losing technical precision.

<p>
  <img alt="LLM" src="https://img.shields.io/badge/LLM-Recon%20Synthesis-8E44AD?style=flat-square&labelColor=0D1117" />
  <img alt="Source triage" src="https://img.shields.io/badge/Source-Triage-1F6FEB?style=flat-square&labelColor=0D1117" />
  <img alt="Payloads" src="https://img.shields.io/badge/Payload-Pruning-B31B1B?style=flat-square&labelColor=0D1117" />
  <img alt="Reports" src="https://img.shields.io/badge/Reports-Precision%20First-238636?style=flat-square&labelColor=0D1117" />
</p>

---

## Operating model

```mermaid
flowchart LR
    A[Scope & Baseline] --> B[Read Code / Traffic]
    B --> C[Map Trust Boundaries]
    C --> D[Find the Seam]
    D --> E[Build Minimal PoC]
    E --> F[Prove Impact]
    F --> G[Write Root Cause]
    G --> H[Coordinate Fix]
    H --> I[Verify Patch]

    B -. avoid .-> X[Payload Spraying First]
    E -. avoid .-> Y[Noisy / Destructive Test]
    F -. avoid .-> Z[Theoretical Impact Only]
```

```text
1. read the code      ── threat model, trust boundaries, expected invariants
2. find the seam      ── where two components disagree about the same path/value
3. prove it           ── deterministic PoC, pinned environment, minimal dependencies
4. write it up        ── code path + condition + impact, no speculation
5. coordinate         ── disclose, patch review, fix verification
```

---

## Toolbelt

### Offensive workflow

<p>
  <img alt="Burp Suite" src="https://img.shields.io/badge/Burp%20Suite-FF6633?style=for-the-badge&logo=burpsuite&logoColor=white&labelColor=0D1117" />
  <img alt="Nuclei" src="https://img.shields.io/badge/Nuclei-00A7E1?style=for-the-badge&labelColor=0D1117" />
  <img alt="ffuf" src="https://img.shields.io/badge/ffuf-F05032?style=for-the-badge&labelColor=0D1117" />
  <img alt="httpx" src="https://img.shields.io/badge/httpx-1F6FEB?style=for-the-badge&labelColor=0D1117" />
  <img alt="subfinder" src="https://img.shields.io/badge/subfinder-8E44AD?style=for-the-badge&labelColor=0D1117" />
</p>

### Code, PoC, and reverse workflow

<p>
  <img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white&labelColor=0D1117" />
  <img alt="Go" src="https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white&labelColor=0D1117" />
  <img alt="Java" src="https://img.shields.io/badge/Java-E76F00?style=for-the-badge&logo=openjdk&logoColor=white&labelColor=0D1117" />
  <img alt="Frida" src="https://img.shields.io/badge/Frida-D53A3A?style=for-the-badge&labelColor=0D1117" />
  <img alt="Android" src="https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white&labelColor=0D1117" />
  <img alt="iOS" src="https://img.shields.io/badge/iOS-000000?style=for-the-badge&logo=apple&logoColor=white&labelColor=0D1117" />
</p>

### Lab and infrastructure

<p>
  <img alt="Docker" src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white&labelColor=0D1117" />
  <img alt="Linux" src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black&labelColor=0D1117" />
  <img alt="GitLab" src="https://img.shields.io/badge/GitLab-FC6D26?style=for-the-badge&logo=gitlab&logoColor=white&labelColor=0D1117" />
  <img alt="Jenkins" src="https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=jenkins&logoColor=white&labelColor=0D1117" />
  <img alt="pfSense" src="https://img.shields.io/badge/pfSense-212121?style=for-the-badge&labelColor=0D1117" />
  <img alt="ESXi" src="https://img.shields.io/badge/ESXi-607078?style=for-the-badge&labelColor=0D1117" />
</p>

### How I use tools

| Phase | Tools | Purpose |
|---|---|---|
| **Recon** | `subfinder`, `httpx`, `ffuf`, `nuclei`, OSINT flows | Build a map, not just a list |
| **Read** | Burp, source review, `ripgrep`, IDE navigation | Understand invariants before testing |
| **Prove** | Python, Go, short PoC harnesses | Deterministic reproduction |
| **Mobile** | Frida, objection, device/emulator labs | Validate client-server trust assumptions |
| **Pivot** | Docker, ESXi, pfSense, GitLab, Jenkins | Build realistic attack chains |
| **AI** | Local/API LLMs in the workflow | Assist triage, not replace judgment |

---

## GitHub signal

<div align="center">

<p>
  <a href="https://github.com/g2hsec">
    <img alt="GitHub" src="https://img.shields.io/badge/GitHub-g2hsec-0D1117?style=for-the-badge&logo=github&logoColor=white" />
  </a>
  <a href="https://github.com/g2hsec?tab=followers">
    <img alt="Followers" src="https://img.shields.io/github/followers/g2hsec?style=for-the-badge&label=FOLLOWERS&logo=github&labelColor=0D1117&color=238636" />
  </a>
  <a href="https://github.com/g2hsec/g2hsec/commits/main">
    <img alt="Profile updated" src="https://img.shields.io/github/last-commit/g2hsec/g2hsec?style=for-the-badge&label=PROFILE%20UPDATED&logo=github&labelColor=0D1117&color=B31B1B" />
  </a>
</p>

</div>

### Public research profile

```text
primary work      offensive security, vulnerability research, pentest
research style    code-first, PoC-driven, vendor-coordinated
main surfaces     web, mobile, internal network, framework boundaries
public signal     CVE credits, advisory collaboration, technical writeups
```

<p>
  <img alt="Code first" src="https://img.shields.io/badge/Code--First-Research-B31B1B?style=flat-square&labelColor=0D1117" />
  <img alt="PoC driven" src="https://img.shields.io/badge/PoC--Driven-Validation-1F6FEB?style=flat-square&labelColor=0D1117" />
  <img alt="Vendor coordinated" src="https://img.shields.io/badge/Vendor--Coordinated-Disclosure-238636?style=flat-square&labelColor=0D1117" />
  <img alt="Boundary focused" src="https://img.shields.io/badge/Boundary--Focused-Analysis-8E44AD?style=flat-square&labelColor=0D1117" />
</p>

<details>
<summary><b>Dynamic GitHub cards</b></summary>

<br/>

These cards depend on third-party dynamic image services. If they fail to load, the profile still works without them.

<div align="center">

<a href="https://github.com/g2hsec">
  <img
    width="48%"
    src="https://github-readme-stats.vercel.app/api?username=g2hsec&show_icons=true&hide_border=true&theme=tokyonight&rank_icon=github&cache_seconds=86400&v=20260709"
    alt="GitHub stats"
  />
</a>

<a href="https://github.com/g2hsec">
  <img
    width="48%"
    src="https://github-readme-stats.vercel.app/api/top-langs/?username=g2hsec&layout=compact&hide_border=true&theme=tokyonight&langs_count=8&cache_seconds=86400&v=20260709"
    alt="Top languages"
  />
</a>

<br/>

<a href="https://git.io/streak-stats">
  <img
    width="70%"
    src="https://streak-stats.demolab.com?user=g2hsec&theme=tokyonight&hide_border=true&date_format=%5BY.%5Dn.j"
    alt="GitHub streak"
  />
</a>

</div>

</details>

---

## Contact

```text
github    github.com/g2hsec
linkedin  linkedin.com/in/leegyuhyeok
pgp       [fingerprint]
```

Coordinated disclosure preferred for vendor issues.

Open to collaboration on offensive engagements, secure code review, and research on applying LLMs to real pentest workflows — not demo-ware.

---

<div align="center">

### Built around one rule

**Read deeply. Prove cleanly. Report precisely. Coordinate responsibly.**

<br/>

<img
  src="https://capsule-render.vercel.app/api?type=waving&height=120&section=footer&color=0:B31B1B,50:1F6FEB,100:0D1117"
  alt="footer"
/>

</div>
