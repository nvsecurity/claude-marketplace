<div align="center">

<picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/nv-icon-dark.png">
    <img alt="NightVision" src="assets/nv-icon.png">
</picture>

# NightVision Plugin Marketplace for Claude Code and Codex

**Your best defense is a good offense: give your coding agent NightVision skills.**

<br>

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude_Code-Plugin-blueviolet)](https://docs.anthropic.com/en/docs/claude-code)
[![Codex](https://img.shields.io/badge/Codex-Plugin-black)](https://github.com/openai/codex)
[![NightVision](https://img.shields.io/badge/NightVision-DAST-orange)](https://www.nightvision.net)

</div>

---

[NightVision](https://www.nightvision.net) is a white-box-assisted DAST platform that combines **Source Intelligence** (static analysis to extract OpenAPI specs from source code), **dynamic scanning** (ZAP + Nuclei engines), and **Code Traceback** (tracing vulnerabilities back to exact source locations) to find exploitable vulnerabilities in web applications and REST APIs.

This plugin marketplace gives Claude Code and Codex the skills to run NightVision scans, triage results, and integrate security testing into your CI/CD pipelines — all from natural language.

## Quick Start

### Claude Code

**From the terminal:**

```bash
claude plugin marketplace add nvsecurity/claude-marketplace
claude plugin install nightvision@nvsecurity
claude
```

**From inside Claude Code:**

```
/plugin marketplace add nvsecurity/claude-marketplace
```
```
/plugin install nightvision@nvsecurity
```

> You may need to restart Claude Code for the plugin to load.

### Codex

```bash
codex plugin marketplace add https://github.com/nvsecurity/claude-marketplace
codex plugin add nightvision@nvsecurity
```

> Start a new Codex session for the skills to load.

## Skills

| Skill | What it does |
|:------|:-------------|
| **[`app-security-scan`](plugins/nightvision/skills/app-security-scan/)** | Run the DAST-first app scan harness for local, private, staging, and internal apps: preflight, Source Intelligence, target create/update, scan start, polling, SARIF export, and a local manifest |
| **[`scan-configuration`](plugins/nightvision/skills/scan-configuration/)** | Set up DAST scans — create targets, configure authentication (Playwright, headers, cookies), manage projects, define scope exclusions, and prepare private network scans |
| **[`scan-report`](plugins/nightvision/skills/scan-report/)** | Generate a shareable PDF security report: an executive summary for AppSec and leadership plus a findings appendix for developers, for one scan, a scan compared with the previous one, or a whole project |
| **[`scan-triage`](plugins/nightvision/skills/scan-triage/)** | Interpret scan results — read SARIF/CSV findings, understand vulnerabilities, locate the vulnerable code, validate with curl, prioritize by severity, suggest fixes, and mark false positives |
| **[`source-intelligence`](plugins/nightvision/skills/source-intelligence/)** | Extract OpenAPI specs from source code via static analysis, troubleshoot extraction issues, compare specs across versions, and leverage Code Traceback; `api-discovery` still loads it |
| **[`ci-cd-integration`](plugins/nightvision/skills/ci-cd-integration/)** | Wire NightVision into your pipeline — GitHub Actions, GitLab CI, Azure DevOps, Jenkins, BitBucket, and JFrog with SARIF/CSV export and breaking-change detection |

### Example Usage

Just ask your agent what you need:

```
> Set up a NightVision scan for my API running on localhost:8080

> Triage the results from my last scan and suggest fixes

> Make a PDF report of my last scan that I can send to our CISO

> Add NightVision to my GitHub Actions workflow

> Extract an OpenAPI spec from this Django project
```

In Claude Code, invoke skills directly with slash commands:

```
/app-security-scan
/scan-configuration
/scan-report
/scan-triage
/source-intelligence
/ci-cd-integration
```

In Codex, the skills are listed as `nightvision:<skill>`, and Codex picks the one your request calls for.

## Contributing

Contributions are welcome! Please open an [issue](https://github.com/nvsecurity/claude-marketplace/issues) or submit a pull request.

## License

Apache License 2.0 — see [LICENSE](LICENSE) for details.
