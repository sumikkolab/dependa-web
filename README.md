<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/dashboard-en.png?v=2.0" alt="Dependa Dashboard" width="720" />
</p>

<h1 align="center">Dependa</h1>

<p align="center">
  Decide if OSS is safe to use — then review, record, and explain your decision.
</p>

<p align="center">
  <a href="https://apps.microsoft.com/detail/9P84RLQQ401D">
    <img alt="Microsoft Store" src="https://img.shields.io/badge/Microsoft_Store-Get_it-0078d4?style=for-the-badge&logo=microsoft" />
  </a>
</p>

<p align="center">
  <img alt="Platform" src="https://img.shields.io/badge/platform-Windows%2010%2F11-blue" />
  <img alt=".NET 8" src="https://img.shields.io/badge/.NET-8.0-purple" />
  <img alt="Tests" src="https://img.shields.io/badge/tests-1284%20passing-brightgreen" />
  <img alt="Version" src="https://img.shields.io/badge/version-2.0.0-orange" />
</p>

<p align="center">
  <a href="docs/README.ja.md">日本語版はこちら</a>
</p>

---

## The Problem

Your team receives an SBOM from a vendor. 140 packages. Which licenses need review? Which have known vulnerabilities? Who approved what, and when?

Currently tracking this in Excel? Manually writing review notes in Word? No audit trail when someone asks "how do you manage OSS?"

You need a tool that **organizes the review** — not just scans.

**Dependa imports your SBOM, classifies risks, supports review decisions, tracks approvals, and generates reports. Final decisions are always made by humans. Locally. Offline. No cloud. No account.**

## Why This Tool Exists

Software is increasingly built on open source components. Organizations are now required to manage SBOMs, track licenses, and address vulnerabilities — not just as best practice, but as compliance obligations.

Most existing tools focus on **detection and scanning**. But in real organizations, the harder part is not detection — it is **review, approval, documentation, and explanation**.

Many teams still manage OSS usage reviews using Excel, emails, and Word documents. There is no standard tool for this workflow. Dependa was created to fill that gap.

> **Product category**: OSS Governance / SBOM Review Management Tool

## What Dependa Is — and What It Is Not

Dependa is an **OSS review workflow tool**. It organizes the information you need to make usage decisions, records those decisions, and produces reports you can show to auditors.

Dependa is not a scanner. It is a tool for reviewing, documenting, and explaining OSS usage decisions. Designed for teams that already have scan results or SBOMs, but need to review, approve, record, and explain their decisions.

| Dependa IS | Dependa is NOT |
|---|---|
| A review and approval workflow tool | A vulnerability scanner (use Trivy, Snyk) |
| A tool that classifies risk and organizes judgment | An SBOM generator (use Syft, CycloneDX CLI) |
| A tool that records decisions and generates audit reports | An auto-decision tool — humans make final calls |
| A local-first desktop tool | A SaaS platform or CI/CD integration |

---

## Import & Risk Analysis

Import **CycloneDX** (1.2–1.6) and **SPDX** (2.2–2.3) JSON — auto-detected. Or scan a local folder (Python / NuGet / Node.js).

Every component gets a **Risk Level** (High Risk / Risk / Known-Normal) with Risk Reason, Recommended Action, Evidence, and Confidence.

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/vulnerability-analysis-en.png?v=2.0" alt="Risk classification — High Risk components" width="720" />
  <br><sub>Unknown licenses classified as High Risk — guide panel shows next steps</sub>
</p>

---

## Review & Approval Workflow

Review each component: **Approve**, **Action Required**, or **In Review**. Track progress with review statistics and a completion bar. Non-technical reviewers can follow the built-in guide.

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/review-all-items-en.png?v=2.0" alt="Review screen with component details and review panel" width="720" />
  <br><sub>Full component list with detail panel — license info, risk level, PURL, and review controls</sub>
</p>

Workflow states: **Not Started → In Review → Completed → Pending Approval → Returned**

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/scan-results-en.png?v=2.0" alt="Review completed — ready for approval" width="720" />
  <br><sub>All risk items reviewed — ready to mark as completed</sub>
</p>

---

## Reports

Executive summary with risk breakdown, review statistics, and action items. Self-contained HTML — no external dependencies, prints cleanly. Show it to auditors, managers, or compliance teams.

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/html-report-en.png?v=2.0" alt="SBOM Review Report" width="720" />
  <br><sub>SBOM Review Report — component count, risk breakdown, review status, license types</sub>
</p>

---

## Policy

Define organization license rules: **Allowed / Need Approval / Prohibited**. Load templates, customize per license.

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/policy-builder-en.png?v=2.0" alt="Organization Policy" width="720" />
  <br><sub>24 license rules — GPL prohibited, LGPL needs approval, MIT/Apache allowed</sub>
</p>

---

## Project Management

Track multiple SBOM reviews across projects. Each project records owner, last review date, component count, and risk summary.

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/projects-en.png?v=2.0" alt="Project Management" width="720" />
  <br><sub>6 projects tracked — review history and risk counts at a glance</sub>
</p>

---

## Dashboard

Overview of all review activity: review counts, workflow status, policy compliance, and recent projects.

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/home-screen-en.png?v=2.0" alt="Dashboard" width="720" />
  <br><sub>Dashboard — 11 reviews, 7 action required, 34 high risk across 6 projects</sub>
</p>

---

## AI Governance (folder scan only)

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
| Review | Unlimited | Unlimited |
| Approval Workflow | View only | Full transitions |
| Reports | Watermarked | Full |
| SBOM Diff | — | Yes |
| Online Enrichment (PyPI / npm / NuGet) | — | Yes |
| AI Governance Report | View only | Included in report |
| Projects | 1 | Unlimited |

**Free** answers: *what risks exist in this SBOM?*
**Pro** answers: *review it, approve it, report it.*

Free is designed to show the value. Pro is designed to complete the workflow.

## Install

**[Microsoft Store](https://apps.microsoft.com/detail/9P84RLQQ401D)** — auto-updates, self-contained, no runtime needed.

## Language

Japanese and English. UI, reports, risk analysis — everything switches with one setting.

## Links

- [Product Website](https://dependa.sumikkolab.com)
- [User Manual](https://dependa.sumikkolab.com/manual/)
- [Pro Features Guide](https://dependa.sumikkolab.com/manual/pro-features.html)
- [Support](https://dependa.sumikkolab.com/support.html)

## Disclaimer

Dependa organizes information for review purposes. It does not provide legal advice, guarantee license compliance, or substitute for professional security assessments. Final usage decisions are the responsibility of the user and their organization.

## Privacy

No telemetry. No analytics. No account. [Privacy Policy](https://dependa.sumikkolab.com/privacy-policy.html).

## License

Proprietary. Free edition at no cost. [Sumikko Lab](https://dependa.sumikkolab.com). Third-party licenses: see [ThirdPartyNotices](https://dependa.sumikkolab.com/manual/licensing.html).
