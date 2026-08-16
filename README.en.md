[English](README.en.md) | [简体中文](README.md)

# codex-skills

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)

**Codex Skills Mother Repository**: maintains only the index and skill descriptions; skill code, versions, and Releases live in their own **separate sub-repositories**.

> **This is a personal repository of self-made Codex skills**: all skills are developed and maintained by an individual, are not OpenAI official products, and are provided AS-IS without any warranty.

> Review convention: 1 skill -> 1 Target -> 1 Scan Result -> 1 review decision. Before installing any skill, run a read-only review with [skillspector-scan](https://github.com/Wuqi24/skillspector-scan).

## Featured Skills

| Skill | Description | Latest Release |
|:---|:---|:---|
| [skillspector-scan](https://github.com/Wuqi24/skillspector-scan) | Offline, evidence-driven, auditable security scanner for AI agent skills: 16+ risk categories, brief mode, verified records, Inspection Ledger, Docker & cloud CI scanning | [v1.2.2](https://github.com/Wuqi24/skillspector-scan/releases/tag/v1.2.2) |
| [multi-agent-engineering](https://github.com/Wuqi24/multi-agent-engineering) | Gate-based multi-agent engineering workflow: five Gates + Spike/Bounded/Architectural scaling | [v0.1.0](https://github.com/Wuqi24/multi-agent-engineering/releases/tag/v0.1.0) |

Each sub-repository's Release page belongs only to itself — no mixed timelines.

Skill details: [skills/skillspector-scan.md](skills/skillspector-scan.md) and [skills/multi-agent-engineering.md](skills/multi-agent-engineering.md).

## Cloud CI Scanning

[skillspector-scan](https://github.com/Wuqi24/skillspector-scan) provides a reusable GitHub Actions workflow (`.github/workflows/skill-scan.yml`): put any skill into a GitHub repository to scan it in the cloud — no local PowerShell / Python / git / Docker required.

Reference from another repository (full docs in the sub-repo [README](https://github.com/Wuqi24/skillspector-scan) and Wiki):

```yaml
name: scan-skill
on: workflow_dispatch
jobs:
  scan:
    permissions:
      contents: read
    uses: Wuqi24/skillspector-scan/.github/workflows/skill-scan.yml@main
    with:
      skill_path: '.'
      mode: full
```

Callers must declare `permissions: contents: read`, otherwise GitHub fails validation before startup.

## Convention

- **Mother repo is facade only**: index, skill cards, maintenance notes; no skill code copies
- **One skill per repo**: versions, Releases, issues, and stars stay in their own repos
- **Adding a skill**: create a sub-repo -> add a card in `skills/` (see `skills/_template.md`) -> update this index

## Responsibility & Risk Disclaimer

- This is a **personal** collection of self-made Codex skills; not affiliated with OpenAI and not official
- Skills are provided AS-IS, may contain defects, behavior changes, or security risks, with no express or implied warranty
- **Review before install**: run [skillspector-scan](https://github.com/Wuqi24/skillspector-scan) on the target skill first
- The author is not liable for any direct or indirect loss from using these skills; beta skills may change or be discontinued at any time

## License

MIT, see [LICENSE](LICENSE); each skill repository has its own LICENSE.
