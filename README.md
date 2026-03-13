<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/home-screen-en.png" alt="Dependa" width="480" />
</p>

<h1 align="center">Dependa</h1>

<p align="center">
  Dependency risk analysis for Windows — vulnerabilities, licenses, and compatibility in one scan.
</p>

<p align="center">
  <a href="https://apps.microsoft.com/detail/9P84RLQQ401D">
    <img src="https://get.microsoft.com/images/en-us%20dark.svg" alt="Get it from Microsoft Store" width="200" />
  </a>
</p>

<p align="center">
  <img alt="Platform" src="https://img.shields.io/badge/platform-Windows%2010%2F11-blue" />
  <img alt=".NET 8" src="https://img.shields.io/badge/.NET-8.0-purple" />
  <img alt="Tests" src="https://img.shields.io/badge/tests-396%20passing-brightgreen" />
</p>

<p align="center">
  <a href="docs/README.ja.md">🇯🇵 日本語版はこちら</a>
</p>

---

## The Problem

Copilot added three packages to your `requirements.txt`. Did you check the licenses? Cursor generated a `package.json` — are any of those transitive deps on the CVE list?

With AI-assisted coding, you're shipping dependencies you didn't choose. But the risk is still yours. Checking licenses means cross-referencing SPDX identifiers by hand. Vulnerability scanning means querying OSV one package at a time. Generating an SBOM means configuring yet another tool. And tomorrow the deps change again.

Most SCA tools expect a CI pipeline and a Linux box. A lot of real projects don't have either — they live on a Windows machine, built by a small team or a solo developer.

**Dependa runs locally on Windows, works offline, and gives you answers. No cloud. No account. No setup.**

## What You Get

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/scan-results-en.png" alt="Scan Results" width="720" />
</p>

### Scan

- **Python** (pip), **NuGet** (.csproj / packages.config), **Node.js** (npm)
- Vulnerability matching against a bundled advisory database — no network required
- License classification: Approved / Caution / Prohibited / Unknown
- Script and browser extension inspection for external references

### Report

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/html-report-en.png" alt="HTML Report" width="720" />
</p>

- Self-contained HTML — no external CSS/JS, prints cleanly, works offline
- CycloneDX 1.5 SBOM (JSON)
- Structured prompts you can paste into ChatGPT, Claude, or any LLM for fix guidance

### Analyze (Pro)

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/license-analysis-en.png" alt="License Analysis" width="720" />
</p>

- **License compatibility** — Apache-2.0 + GPL-2.0 patent clause conflict? Copyleft in a proprietary project? Detected and explained.
- **Vulnerability triage** — severity breakdown, affected packages, remediation paths
- **Delta Scan** — what changed since your last scan
- **Online OSV lookup** — real-time CVE data, opt-in
- **Online license metadata** — PyPI and npm registry supplement

## Offline by Default

Zero network requests unless you opt in. Vulnerability matching, license classification, policy checks, HTML reports, SBOM — all local, all bundled.

Online features (OSV API, PyPI, npm) exist. They're off until you turn them on.

## CLI + GUI

Same binary.

```powershell
Dependa.exe                                                    # GUI
Dependa.exe scan --path ./myproject --accept-terms             # scan
Dependa.exe scan --path ./myproject --ai-prompt vuln           # AI fix prompt
Dependa.exe scan --path ./myproject --lang en                  # English output
```

```
Exit 0  Success
Exit 2  Policy violation detected
Exit 3  Pro license required
```

## Free vs Pro

**Free** — Python + NuGet scanning, local vulnerability matching, license classification, HTML report, SBOM, script inspection. Answers: *do I have a problem?*

**Pro** — adds Node.js, online OSV lookup, license compatibility analysis, vulnerability triage, Delta Scan. Answers: *how bad, and what do I fix first?* One-time purchase via Microsoft Store.

## Install

**[Microsoft Store](https://apps.microsoft.com/detail/9P84RLQQ401D)** — auto-updates, self-contained, no runtime needed.

## Language

Japanese and English. UI, reports, CLI output — everything switches with one setting.

## Privacy

No telemetry. No analytics. No account. [Privacy Policy](https://dependa.sumikkolab.com/privacy-policy.html).

## Roadmap

Java (Maven/Gradle) and Go (go.mod) are next. Star count decides priority.

This project is actively maintained but not community-managed. No PR reviews, no feature negotiations. File an issue if you hit a bug — it gets read.

## License

Proprietary. Free edition at no cost. [Sumikko Lab](https://dependa.sumikkolab.com). Third-party licenses: see [ThirdPartyNotices](https://dependa.sumikkolab.com/manual/licensing.html).
