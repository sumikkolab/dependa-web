<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/home-screen-en.png" alt="Dependa" width="480" />
</p>

<h1 align="center">Dependa</h1>

<p align="center">
  Local dependency review for security and compliance
</p>

<p align="center">
  <a href="https://apps.microsoft.com/detail/9P84RLQQ401D">
    <img src="https://get.microsoft.com/images/en-us%20dark.svg" alt="Get it from Microsoft Store" width="200" />
  </a>
</p>

<p align="center">
  <img alt="Platform" src="https://img.shields.io/badge/platform-Windows%2010%2F11-blue" />
  <img alt=".NET 8" src="https://img.shields.io/badge/.NET-8.0-purple" />
  <img alt="Tests" src="https://img.shields.io/badge/tests-709%20passing-brightgreen" />
</p>

<p align="center">
  <a href="docs/README.ja.md">🇯🇵 日本語版はこちら</a>
</p>

---

## The Problem

Modern applications rely on dozens or hundreds of open-source dependencies. Understanding the security, licensing, and compatibility risks of those dependencies is often difficult.

Many SCA tools focus on CI/CD automation, but developers and reviewers still need a clear way to understand dependency risks before release.

**Dependa analyzes dependencies locally and generates a human-readable review report you can share with your team. No cloud upload. No account. No setup.**

## Who Uses This

- **Developers** — review dependency risks before shipping
- **Security teams** — vulnerability inventory and prioritization
- **Compliance reviewers** — license compatibility checks and audit reports
- **IT / Procurement** — risk evaluation before adopting third-party tools

## What You Get

### Scan

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/scan-results-en.png" alt="Scan Results" width="720" />
</p>

- **Python** (pip), **NuGet** (.csproj / packages.config), **Node.js** (npm)
- Vulnerability matching against a bundled advisory database — no network required
- License classification: Approved / Caution / Prohibited / Unknown
- **License confidence scoring**: High / Medium / Low / Conflicted
- Script and browser extension inspection for external references

### Policy & Judgments (v1.1.0)

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/policy-judgments-en.png" alt="Policy Judgments" width="720" />
</p>

- **Organization Policy Builder** — create from templates, customize rules, save and set as default
- **Package-level judgments** — detected facts, initial evaluation, policy action, and reason shown separately
- Color-coded status: Pass / Warning / Fail for initial evaluation, Allow / Conditional / Review / Deny for policy action
- Explainable results: every judgment includes the reason why

### Report

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/html-report-en.png" alt="HTML Report" width="720" />
</p>

- Self-contained HTML — no external CSS/JS, prints cleanly, works offline
- **Policy judgment records** in HTML — applied policy name, action summary badges, detailed judgment table
- CycloneDX 1.5 SBOM (JSON)
- CSV inventory (v2 schema with PolicyAction, ReasonCode, AppliedPolicyName, IsEffective)
- Structured prompts you can paste into ChatGPT, Claude, or any LLM for fix guidance

### Analyze (Pro)

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/license-analysis-en.png" alt="License Analysis" width="720" />
</p>

- **License compatibility** — Apache-2.0 + GPL-2.0 patent clause conflict? Copyleft in a proprietary project? Detected and explained.
- **Vulnerability triage** — severity breakdown, affected packages, remediation paths
- **Risk Score** — 0-100 quantitative evaluation per package
- **OSS Review Support** — recommended actions, commercial use guidance, organization review checklist
- **Delta Scan** — what changed since your last scan
- **Online verification** — verify local license definitions against online registries (PyPI, npm, NuGet)
- **Online OSV lookup** — real-time CVE data, opt-in

## Why Dependa

Dependa is not a replacement for CI-based SCA tools. It focuses on **the human review step** in your workflow.

|  | Snyk | Trivy | Dependency-Check | Dependa |
|---|:---:|:---:|:---:|:---:|
| CI/CD automation | ✓ | ✓ | ✓ | optional |
| No cloud required | — | ✓ | ✓ | ✓ |
| Human-readable review report | — | — | — | ✓ |
| Local execution | — | ✓ | ✓ | ✓ |
| Desktop GUI | — | — | — | ✓ |
| License confidence scoring | — | — | — | ✓ |
| Policy-based explainable judgments | — | — | — | ✓ |

> Dependa complements CI tools. Use CI for automated checks, Dependa for review reports.

## Example Workflow

```
1. Select a project directory
2. Run dependency analysis (vulnerabilities + licenses + compatibility)
3. Review results on screen (risk scores, confidence levels)
4. Generate HTML review report
5. Share report with your team for approval
```

## Offline by Default

Zero network requests unless you opt in. Vulnerability matching, license classification, policy checks, HTML reports, SBOM — all local, all bundled.

Data freshness warning after 90 days — Dependa tells you when bundled data may be stale.

Online features (OSV API, PyPI, npm, NuGet) exist. They're off until you turn them on.

## CLI + GUI

Same binary.

```powershell
Dependa.exe                                                    # GUI
Dependa.exe scan --path ./myproject --accept-terms             # scan
Dependa.exe scan --path ./myproject --export all --overwrite   # export CSV + Notice + Review
Dependa.exe scan --path ./myproject --ai-prompt vuln           # AI fix prompt
Dependa.exe scan --path ./myproject --lang en                  # English output
```

```
Exit 0  Success
Exit 2  Policy violation detected
Exit 3  Pro license required
```

## Free vs Pro

**Free** — Python + NuGet scanning, local vulnerability matching, license classification with confidence scoring, HTML report, SBOM, CSV inventory, license notice, script inspection. Answers: *do I have a problem?*

**Pro** — adds Node.js, online OSV lookup, online license verification, license compatibility analysis, vulnerability triage, risk scoring, OSS review support, Delta Scan, review report export. Answers: *how bad, what do I fix first, and what do I tell the reviewer?* One-time purchase via Microsoft Store.

## Install

**[Microsoft Store](https://apps.microsoft.com/detail/9P84RLQQ401D)** — auto-updates, self-contained, no runtime needed.

## Documentation

**[User Manual](https://dependa.sumikkolab.com/manual/)** — Getting started, scanning, reports, CLI reference, Pro features, and troubleshooting.

## Language

Japanese and English. UI, reports, CLI output — everything switches with one setting. Full Japanese localization including license labels, risk levels, and review guidance.

## Privacy

No telemetry. No analytics. No account. [Privacy Policy](https://dependa.sumikkolab.com/privacy-policy.html).

## Roadmap

Java (Maven/Gradle) and Go (go.mod) are next. Star count decides priority.

This project is actively maintained but not community-managed. No PR reviews, no feature negotiations. File an issue if you hit a bug — it gets read.

## License

Proprietary. Free edition at no cost. [Sumikko Lab](https://dependa.sumikkolab.com). Third-party licenses: see [ThirdPartyNotices](https://dependa.sumikkolab.com/manual/licensing.html).
