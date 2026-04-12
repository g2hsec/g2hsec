```
╭─────────────────────────────────────────────────────╮
│  g2h · Gyu-hyeok Lee                                │
│  Security researcher — Seoul, KR                    │
╰─────────────────────────────────────────────────────╯
```

I work in **offensive security** — penetration testing and vulnerability research against production systems.
On the side, I take what I learn from engagements back to upstream frameworks and help vendors fix it.

<p>
  <a href="#selected-findings"><img alt="CVE" src="https://img.shields.io/badge/CVE-6_credited-B31B1B?style=flat-square&labelColor=0D1117" /></a>
  <a href="#research-interests"><img alt="Focus" src="https://img.shields.io/badge/Focus-Web_·_Mobile_·_Pentest-1F6FEB?style=flat-square&labelColor=0D1117" /></a>
  <a href="#contact"><img alt="Location" src="https://img.shields.io/badge/Seoul-KR-238636?style=flat-square&labelColor=0D1117" /></a>
</p>

---

### `whoami`

Penetration tester by day, vulnerability researcher by night.
My day job is breaking into production systems under scope — web apps, mobile apps, internal networks — and writing the kind of report that gets the finding fixed instead of filed away.

What I try to do well:

- **Read before I fuzz.** Most of the bugs worth reporting are in logic the scanner never saw. I start in source or in traffic, not in a payload list.
- **Prove, don't claim.** Every finding ships with a deterministic PoC and the exact preconditions. No "theoretically exploitable."
- **Think in boundaries.** Auth, tenant, trust, session, origin — the interesting bugs are always one layer underneath where people were looking.

---

### `currently`

- Running red-team and pentest engagements across web, mobile, and internal network scope
- Exploring how **LLMs can augment offensive security workflows** — recon synthesis, reading large unfamiliar codebases fast, generating and triaging payloads, drafting findings without losing technical precision
- Building small internal tools that sit between "off-the-shelf scanner" and "hand-written exploit" — where I think the interesting leverage is right now

---

### Research interests

| Area | What I'm actually looking for |
|---|---|
| **Web** | Server-side logic flaws, authn/authz boundaries, IDOR and tenant isolation, SSRF, deserialization, API design mistakes that scanners miss |
| **Mobile** | Android / iOS client-server trust assumptions, insecure storage, IPC and deep-link abuse, pinning bypass, backend APIs reachable outside the app |
| **Penetration testing** | Internal network pivots, identity and session weaknesses, CI/CD and supply-chain trust paths, end-to-end attack chains instead of single-issue pokes |
| **AI × offensive security** | How LLMs actually help during a real engagement — recon, source triage, payload generation, report drafting — and where they hurt more than they help |

---

### Selected findings

Six CVEs credited to me in 2026. Full version matrices and vectors live in each advisory.

**Spring Boot — Actuator authentication bypass (CVSS 8.2, High)**
[`CVE-2026-22731`](https://spring.io/security/cve-2026-22731/) · [`CVE-2026-22733`](https://spring.io/security/cve-2026-22733/)
Application endpoints declared under Actuator Health-group or CloudFoundry paths are served without authentication. The Actuator's path mapping wins over the application's security configuration. Affects Spring Boot `2.7 → 4.0`.

**Spring Framework — MVC / WebFlux flaws**
[`CVE-2026-22735`](https://spring.io/security/cve-2026-22735/) · SSE stream corruption (CVSS 2.6, Low) — unvalidated newlines in `SseEmitter` / `ServerSentEvent` `id` & `event` fields let attacker data break downstream framing.
[`CVE-2026-22737`](https://spring.io/security/cve-2026-22737/) · Script-template path traversal (CVSS 5.9, Medium) — JRuby/Jython template views can resolve files outside configured locations.

**Grafana — tenant & credential exposure**
[`CVE-2026-27877`](https://grafana.com/security/security-advisories/cve-2026-27877) · Public dashboards leak passwords for **all** direct data sources, referenced or not (CVSS 6.5, Medium).
[`CVE-2026-21727`](https://grafana.com/security/security-advisories/cve-2026-21727/) · Legacy `org_id = 0` correlation records cross the tenant boundary — a datasource-management user could read and permanently delete another org's data (CVSS 3.3, Low).

---

### How I work

```
1.  read the code     ── threat model, trust boundaries, expected invariants
2.  find the seam     ── where two components disagree about the same path/value
3.  prove it          ── deterministic PoC, environment pinned, minimal dependencies
4.  write it up       ── code path + condition + impact, no speculation
5.  coordinate        ── disclose, patch review, fix verification
```

Every report I send includes: the offending code path with line references, a minimal PoC that runs on a stock install, the exact preconditions, and a suggested fix written against the actual source — not a generic "validate input" note.

---

### Toolbelt

**Recon**   `ffuf` · `httpx` · `subfinder` · `nuclei` · OSINT flows
**Read**    Burp · `ripgrep` on source · IDE walk-through before fuzzing
**Prove**   Python · Go · short PoC harnesses · Frida · `objection` (mobile)
**Pivot**   Docker · ESXi · pfSense · GitLab · Jenkins for lab chains
**AI**      Local and API-based LLMs wired into the loop — not as a chatbot, as a tool in the pipeline

<p>
  <img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white&labelColor=0D1117" />
  <img alt="Go" src="https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white&labelColor=0D1117" />
  <img alt="Java" src="https://img.shields.io/badge/Java-E76F00?style=flat-square&logo=openjdk&logoColor=white&labelColor=0D1117" />
  <img alt="Burp" src="https://img.shields.io/badge/Burp-FF6633?style=flat-square&logo=burpsuite&logoColor=white&labelColor=0D1117" />
  <img alt="Frida" src="https://img.shields.io/badge/Frida-D53A3A?style=flat-square&labelColor=0D1117" />
  <img alt="Android" src="https://img.shields.io/badge/Android-3DDC84?style=flat-square&logo=android&logoColor=white&labelColor=0D1117" />
  <img alt="Docker" src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white&labelColor=0D1117" />
  <img alt="LLM" src="https://img.shields.io/badge/LLM-in_the_loop-8E44AD?style=flat-square&labelColor=0D1117" />
</p>

---

### GitHub

<p>
  <a href="https://github.com/g2hssec">
    <img height="155" src="https://github-readme-stats.vercel.app/api?username=g2hssec&show_icons=true&hide_border=true&bg_color=0D1117&title_color=1F6FEB&icon_color=B31B1B&text_color=C9D1D9&count_private=true&include_all_commits=true" />
  </a>
  <a href="https://github.com/g2hssec">
    <img height="155" src="https://github-readme-stats.vercel.app/api/top-langs/?username=g2hssec&layout=compact&hide_border=true&bg_color=0D1117&title_color=1F6FEB&text_color=C9D1D9&langs_count=6" />
  </a>
</p>

---

### Contact

```
github    github.com/g2hssec
linkedin  linkedin.com/in/leegyuhyeok
pgp       [fingerprint]
```

Coordinated disclosure preferred for vendor issues.
Open to collaboration on offensive engagements, secure code review, and research on applying LLMs to real pentest workflows — not demo-ware.
