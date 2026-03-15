# Customized Branch 定制记录

本文档记录 `customized` 分支相对于 `main` 分支的所有定制修改，便于从主分支合并功能时识别和保留这些定制内容。

---

## 1. Skills 定制

**原因**: 移除不使用的示例 skills，添加个人使用的 skills。

**修改内容**:

- **删除**: `skill-creator/*`、`summarize/SKILL.md`、`weather/SKILL.md`

**合并注意**: main 分支如新增/修改 skills，按需保留或忽略即可。skills 目录各文件相互独立。

---

## 2. 环境文件

**新增文件**:

- `.python-version` — Python 版本锁定
- `uv.lock` — uv 依赖锁定文件

**合并注意**: 这两个文件为本地环境配置，合并时保留本分支版本。

---

## 3. 模板定制

**原因**: 精简和重构默认模板，使其更符合个人使用习惯。

**涉及文件**:

| 文件 | 修改内容 |
|------|----------|
| `nanobot/templates/AGENTS.md` | 重写标题为 "Your Workspace"，新增 Memory 和 Safety 章节，移除旧的通用助手描述 |
| `nanobot/templates/SOUL.md` | 重写标题为 "Who You Are"，新增 "Honesty over Useful" 价值观，调整措辞（"when in doubt, ask before acting"） |
| `nanobot/templates/USER.md` | 大幅精简，移除 Communication Style/Response Length/Technical Level 等选项式配置，改为简洁的 User Context 结构 |
| `nanobot/templates/memory/MEMORY.md` | 标题改为 "Additional Information about User"，新增 "Installed CLI" 和 "Tool Configuration Notes" 章节 |

**合并注意**: 这些是模板文件（新用户初始化时使用），main 分支若有模板改动需手动对比取舍。
