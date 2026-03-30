<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/home-screen-en.png" alt="Dependa" width="480" />
</p>

<h1 align="center">Dependa</h1>

<p align="center">
  Dependency &amp; AI governance analysis for Windows — vulnerabilities, licenses, and governance in one scan.
</p>

<p align="center">
  <a href="https://apps.microsoft.com/detail/9P84RLQQ401D">
    <img src="https://get.microsoft.com/images/en-us%20dark.svg" alt="Get it from Microsoft Store" width="200" />
  </a>
</p>

<p align="center">
  <img alt="Platform" src="https://img.shields.io/badge/platform-Windows%2010%2F11-blue" />
  <img alt=".NET 8" src="https://img.shields.io/badge/.NET-8.0-purple" />
  <img alt="Tests" src="https://img.shields.io/badge/tests-1034%20passing-brightgreen" />
</p>

<p align="center">
  <a href="docs/README.ja.md">🇯🇵 日本語版はこちら</a>
</p>

---

## The Problem

Copilot added three packages to your `requirements.txt`. Did you check the licenses? Cursor generated a `package.json` — are any of those transitive deps on the CVE list? Your Terraform defines Azure OpenAI resources — do you know where your data is processed?

With AI-assisted coding, you're shipping dependencies and AI configurations you didn't choose. But the risk is still yours.

**Dependa runs locally on Windows, works offline, and gives you answers. No cloud. No account. No setup.**

## What You Get

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/scan-results-en.png" alt="Scan Results" width="720" />
</p>

### Scan

- **Python** (pip), **NuGet** (.csproj / packages.config), **Node.js** (npm)
- Vulnerability matching against a bundled advisory database — no network required
- License classification: Approved / Caution / Prohibited / Unknown

### AI Governance (v1.5 New)

- **AI BOM** — Inventory AI SDKs, model settings, API keys, and endpoints from dependencies, source code, environment variables, and IaC definitions
- **Excessive Agency Detection** — Wildcard IAM, auto-approve, unlimited loops, and other overly broad permission candidates
- **Data Sovereignty Checks** — AI service region settings and data destination verification
- **Organization Policy Evaluation** — Compare against allowed regions and approved AI providers

### IaC Support (v1.5 New)

- **Terraform** (.tf) — Lightweight HCL structure recognition for AI resource detection
- **Bicep** (.bicep) — Azure AI resource detection with param default resolution
- **ARM JSON** (.json) — ARM template resource array scanning for AI resources

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

- **Multi-ecosystem scanning** — scan Python + npm simultaneously, unified results
- **License compatibility** — Apache-2.0 + GPL-2.0 patent clause conflict? Copyleft in a proprietary project? Detected and explained.
- **Vulnerability triage** — severity breakdown, affected packages, remediation paths
- **Delta Scan** — what changed since your last scan, including AI BOM and Finding changes (v1.5 New)
- **Exception management** — approve known issues with reason, approver, and expiry

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/exception-management-en.png" alt="Exception Management" width="720" />
</p>

- **Online OSV lookup** — real-time CVE data, opt-in
- **Online license metadata** — PyPI and npm registry supplement

### Policy Builder (Pro)

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/policy-builder-en.png" alt="Policy Builder" width="720" />
</p>

- Select a template, adjust rules per category, preview the impact
- Saved policies are applied automatically on every scan

## Offline by Default

Zero network requests unless you opt in. Vulnerability matching, license classification, policy checks, AI Governance, IaC analysis, HTML reports, SBOM — all local, all bundled.

## CLI + GUI

Same binary.

```powershell
Dependa.exe                                                    # GUI
Dependa.exe scan --path ./myproject --accept-terms             # scan
Dependa.exe scan --path ./myproject --ai-prompt vuln           # AI fix prompt
Dependa.exe scan --path ./myproject --lang en                  # English output
```

## Free vs Pro

**Free** — Python + NuGet scanning, local vulnerability matching, license classification, AI Governance (AI BOM / Excessive Agency / Data Sovereignty / Organization Policy), IaC support (Terraform / Bicep / ARM JSON), HTML report, SBOM. Answers: *what's the current state of my project?*

**Pro** — adds Node.js, multi-ecosystem scanning, Delta Scan (including AI Governance diff), exception management, online OSV lookup, license compatibility analysis, vulnerability triage. Answers: *what changed, how bad is it, and what do I fix first?* One-time purchase via Microsoft Store.

## Install

**[Microsoft Store](https://apps.microsoft.com/detail/9P84RLQQ401D)** — auto-updates, self-contained, no runtime needed.

## Language

Japanese and English. UI, reports, CLI output — everything switches with one setting.

## Privacy

No telemetry. No analytics. No account. [Privacy Policy](https://dependa.sumikkolab.com/privacy-policy.html).

## License

Proprietary. Free edition at no cost. [Sumikko Lab](https://dependa.sumikkolab.com). Third-party licenses: see [ThirdPartyNotices](https://dependa.sumikkolab.com/manual/licensing.html).
