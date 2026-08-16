# codex-skills

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)

**Codex Skills 母仓库**：只维护索引与技能说明；技能代码、版本与 Release 都在各自的**独立子仓库**中。

> 审核约定：1 skill → 1 Target → 1 Scan Result → 1 审核决策；安装任何技能前，先使用 [skillspector-scan](https://github.com/Wuqi24/skillspector-scan) 做只读审查。

## 收录技能

| 技能 | 说明 | 最新 Release |
|:---|:---|:---|
| [skillspector-scan](https://github.com/Wuqi24/skillspector-scan) | 离线、证据驱动、可审计的 AI Agent Skill 安全审查器：16+ 类风险、简报模式、已审记录、Inspection Ledger、Docker / 云端 CI 扫描 | [v1.2.2](https://github.com/Wuqi24/skillspector-scan/releases/tag/v1.2.2) |

## 云端 CI 扫描

[skillspector-scan](https://github.com/Wuqi24/skillspector-scan) 提供可复用的 GitHub Actions workflow（`.github/workflows/skill-scan.yml`）：把任意技能放进 GitHub 仓库即可云端扫描，无需本地 PowerShell / Python / git，也无需 Docker。

其他仓库引用（完整说明见子仓库 [README](https://github.com/Wuqi24/skillspector-scan) 与 Wiki）：

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

引用方必须声明 `permissions: contents: read`，否则 GitHub 会在启动前校验失败。

## 约定

- **母仓库只做门面**：索引、技能卡片、维护说明；不存放技能代码副本
- **技能各归其仓**：版本、Release、issue、star 都在子仓库，互不干扰
- **新增技能**：建子仓库 → 在 `skills/` 加卡片（参考 `skills/_template.md`）→ 更新本索引

## License

MIT，见 [LICENSE](LICENSE)；各技能仓库另有独立 LICENSE。
