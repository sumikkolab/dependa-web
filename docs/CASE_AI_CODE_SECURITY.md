# Managing AI-Generated Code Dependencies with Dependa

## The situation

AI code assistants (Copilot, Cursor, Claude Code) write working code. They don't audit what they import. The `requirements.txt` or `package.json` they produce may include packages with known CVEs, licenses incompatible with your distribution model, or transitive dependencies you've never heard of.

This isn't a flaw in the tools — it's a gap in the workflow. Code generation and software composition analysis (SCA) are different jobs.

## What goes wrong

**Pinned to a vulnerable version.** AI suggests `requests==2.25.1` because that's what the training data contained. That version is affected by CVE-2023-32681. You'd need to check the OSV database or NVD manually to catch this — per package, per version, every time.

**License pulled in through a transitive dep.** You asked for an MIT package. The AI picked one. But its dependency tree includes a GPL-3.0 library two levels down. Your proprietary project now has a license compliance problem that `pip show` won't surface without digging.

**No SBOM, no audit trail.** AI doesn't generate a software bill of materials. When a client or an auditor asks what's in your build, you have nothing to hand over. Producing a CycloneDX or SPDX document from scratch is a separate task that most small teams skip.

## Where Dependa fits

Dependa is an SCA tool for Windows that runs locally and works offline. It doesn't replace your AI assistant — it checks what the AI brought in.

### 1. Scan

```powershell
Dependa.exe scan --path ./ai-generated-project --accept-terms
```

Detects `requirements.txt`, `package.json`, `.csproj`, and their lock files. Matches every dependency against a bundled vulnerability database. Classifies licenses as Approved, Caution, Prohibited, or Unknown.

No network connection needed. No account. No API key.

### 2. Report

Generates a self-contained HTML report (no external CSS/JS — works offline, prints to PDF) and a CycloneDX 1.5 SBOM in JSON. Both are produced in the same scan pass.

### 3. Feed it back to AI

This is the part that closes the loop. Dependa generates structured prompts from scan results:

```powershell
Dependa.exe scan --path ./myproject --ai-prompt vuln --accept-terms
Dependa.exe scan --path ./myproject --ai-prompt license --accept-terms
```

Dependa doesn't call any AI API. It outputs text you paste into whatever LLM you're using. The prompt includes package names, versions, advisory IDs, severity, and fix versions — structured so the AI can suggest concrete code changes.

Typical follow-ups:
- "Update these packages to the nearest non-vulnerable version"
- "Replace GPL-3.0 dependencies with MIT-compatible alternatives"
- "Review the Delta Scan diff and flag anything that needs attention"

AI wrote the deps. Dependa found the problems. AI writes the fix. You review.

### 4. Delta Scan (Pro)

After updating, run the scan again. Delta Scan compares against the previous result and shows:
- Dependencies added or removed
- New or resolved vulnerabilities
- License classification changes
- Policy status transitions (Pass → Fail, etc.)

Useful before tagging a release or after a bulk dependency update.

### 5. License compatibility (Pro)

Beyond per-package classification, the compatibility matrix checks pairwise interactions across your dependency tree. Apache-2.0 + GPL-2.0-only patent clause conflict. Copyleft mixed with proprietary. Flagged with an explanation of why it matters.

## The workflow

```
AI generates code with dependencies
        ↓
Dependa scans → vulnerabilities, licenses, SBOM
        ↓
Dependa outputs structured AI prompt
        ↓
AI suggests fixes based on scan results
        ↓
You review and approve
        ↓
Dependa Delta Scan confirms the fix
```

## Free vs Pro

Free handles Python + NuGet scanning, local vulnerability matching, license classification, HTML reports, SBOM, and basic AI prompts.

Pro adds Node.js, online OSV lookup, license compatibility analysis, vulnerability triage reports, and Delta Scan.

---

Currently under Microsoft Store review. Windows 10/11.
