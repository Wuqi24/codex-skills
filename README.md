# codex-skills

Codex Skills 母仓库：只维护索引与技能说明，技能代码、版本与 Release 都在各自的**独立子仓库**中。

## 收录技能

| 技能 | 子仓库 | 说明 | 最新 Release |
|:---|:---|:---|:---|
| [skillspector-scan](https://github.com/Wuqi24/skillspector-scan) | [Wuqi24/skillspector-scan](https://github.com/Wuqi24/skillspector-scan) | 离线静态安全审查：对本地 AI Agent 技能做只读扫描（16+ 类风险、简报模式、已审记录） | [v1.1.0](https://github.com/Wuqi24/skillspector-scan/releases/tag/v1.1.0) |

每个子仓库的 Release 页面只属于它自己，互不混排。

## 安装

母仓库不含技能代码，请从技能子仓库获取：

```powershell
git clone https://github.com/Wuqi24/skillspector-scan.git "$HOME\.codex\skills\skillspector-scan"
```

## 约定

- **母仓库只做门面**：索引、技能卡片、维护说明；不存放技能代码副本
- **技能各归其仓**：版本、Release、issue、star 都在子仓库，互不干扰
- **新增技能**：建子仓库 → 在 `skills/` 加卡片（参考 `skills/_template.md`）→ 更新本索引
- **审核约定**：1 skill → 1 Target → 1 Scan Result → 1 审核决策，安装前用 skillspector-scan 审查

## License

MIT，见 [LICENSE](LICENSE)；各技能仓库另有独立 LICENSE。
