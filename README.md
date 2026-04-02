<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/home-screen-en.png?v=2.0" alt="Dependa" width="480" />
</p>

<h1 align="center">Dependa</h1>

<p align="center">
  Review, approve, and report on OSS usage — SBOM-driven risk analysis for Windows.
</p>

<p align="center">
  <a href="https://apps.microsoft.com/detail/9P84RLQQ401D">
    <img src="https://get.microsoft.com/images/en-us%20dark.svg" alt="Get it from Microsoft Store" width="200" />
  </a>
</p>

<p align="center">
  <img alt="Platform" src="https://img.shields.io/badge/platform-Windows%2010%2F11-blue" />
  <img alt=".NET 8" src="https://img.shields.io/badge/.NET-8.0-purple" />
  <img alt="Tests" src="https://img.shields.io/badge/tests-1279%20passing-brightgreen" />
  <img alt="Version" src="https://img.shields.io/badge/version-2.0.0-orange" />
</p>

<p align="center">
  <a href="docs/README.ja.md">日本語版はこちら</a>
</p>

---

## The Problem

Your team receives an SBOM from a vendor. 140 packages. Which licenses need review? Which have known vulnerabilities? Who approved what, and when?

With AI-assisted coding shipping dependencies you didn't choose, and compliance teams asking "how do you manage OSS?", you need a tool that organizes the review — not just scans.

**Dependa imports your SBOM, classifies risks, supports review decisions, tracks approvals, and generates reports. Locally. Offline. No cloud. No account.**

## What Dependa Does

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/scan-results-en.png?v=2.0" alt="Review Screen" width="720" />
</p>

### Import & Risk Analysis

- Import **CycloneDX** (1.2–1.6) and **SPDX** (2.2–2.3) JSON — auto-detected
- Or scan a local folder (Python / NuGet / Node.js)
- Every component gets a **Risk Level** (High Risk / Risk / Known-Normal) with:
  - **Risk Reason** (18 categories) — why this needs attention
  - **Recommended Action** (12 types) — what to do next
  - **Evidence** — the data behind the classification
  - **Confidence** — how certain the analysis is

### Review & Approval Workflow

- Review each component: **Approve**, **Action Required**, or **In Review**
- Track progress with review statistics and completion percentage
- Workflow states: Not Started → In Review → Completed → Pending Approval → Returned
- Guide panel explains what to do at each step — accessible to non-technical reviewers

### Reports

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/html-report-en.png?v=2.0" alt="HTML Report" width="720" />
</p>

- Executive summary with risk breakdown and review statistics
- Action Required items highlighted with risk reasons and recommended actions
- Self-contained HTML — no external dependencies, prints cleanly
- CycloneDX SBOM output

### Policy

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/policy-builder-en.png?v=2.0" alt="Policy Builder" width="720" />
</p>

- Define organization license rules: Allowed / Need Approval / Prohibited
- Load templates, customize per license
- Applied automatically on every analysis

### AI Governance

- **AI BOM** — Inventory AI SDKs, model settings, API keys, endpoints
- **Excessive Agency Detection** — Overly broad permissions, auto-approve patterns
- **Data Sovereignty** — AI service region and data destination checks
- **IaC Support** — Terraform / Bicep / ARM JSON AI resource detection

## Offline by Default

Zero network requests unless you opt in. Risk analysis, license classification, policy checks, AI Governance, reports — all local.

## Free vs Pro

| | Free | Pro |
|---|---|---|
| SBOM Import (CycloneDX / SPDX) | 1 file | Unlimited |
| Risk Analysis (full detail) | All | All |
| Review | 5 items | Unlimited |
| Approval Workflow | View only | Full transitions |
| Reports | Watermarked | Full |
| SBOM Diff | — | Yes |
| Online Enrichment (PyPI / npm / NuGet) | — | Yes |
| AI Governance Report | View only | Included in report |
| Projects | 1 | Unlimited |

**Free** answers: *what risks exist in this SBOM?*
**Pro** answers: *review it, approve it, report it.*

## Install

**[Microsoft Store](https://apps.microsoft.com/detail/9P84RLQQ401D)** — auto-updates, self-contained, no runtime needed.

## Language

Japanese and English. UI, reports, risk analysis — everything switches with one setting.

## Privacy

No telemetry. No analytics. No account. [Privacy Policy](https://dependa.sumikkolab.com/privacy-policy.html).

## License

Proprietary. Free edition at no cost. [Sumikko Lab](https://dependa.sumikkolab.com). Third-party licenses: see [ThirdPartyNotices](https://dependa.sumikkolab.com/manual/licensing.html).
