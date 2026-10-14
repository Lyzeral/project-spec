# project-spec

> 项目管理规范常驻技能 v1.0.0
> 更新日期：2026-10-06

| 版本 | 日期 | 修改说明 | 作者 |
|------|------|----------|------|
| v1.0.0 | 2026-10-06 | 初版：六大规范 + 六条提交前自查清单 | 刘松青 |

## 这是什么

一份对仓库所有产出（脚本、分析文档、数据文件）具有强制约束力的项目管理规范，设计目标是**常驻生效**——无需触发词，每轮对话/每个任务都自动遵守。

规范涵盖五大维度 + 一份自查清单：

1. **目录结构保护** — 严禁随意改动根目录
2. **文件归类存放** — 产出必须归入对应子目录
3. **脚本头部注释与参数管理** — 统一注释模板 + 参数集中定义
4. **版本号与更新日期管理** — 语义化版本 + 修改记录表
5. **主线逻辑维护** — 优先重构而非打补丁
6. **提交前自查清单** — 六项固定检查项

## 安装到豆包（Doubao）

豆包无插件 API，通过「自定义技能 + 偏好提醒」落地：

### 方式一：手动安装

1. 将 `SKILL.md` 复制到豆包用户技能目录：
   - Windows：`%USERPROFILE%\AppData\Local\Doubao\User Data\Default\.doubao\agent_mode\workspace\.user_skills\project-spec\SKILL.md`
   - macOS/Linux：`~/.doubao/agent_mode/workspace/.user_skills/project-spec/SKILL.md`
2. 在豆包偏好设置中添加：
   > 项目产出（脚本/文档/数据）须遵守 project-spec 技能规范，提交前完成六条自查清单。

### 方式二：人设常驻（推荐叠加）

将 `SKILL.md` 中 `# project-spec` 及之后的正文复制到豆包「人设 / 系统提示词」设置中，实现每轮对话全文携带。

## 安装到 Trae

Trae 同时支持「技能」（按需加载）和「规则」（始终生效），建议两者叠加：

### 全局技能（按需查阅）

将 `SKILL.md` 复制到：
- Windows：`%USERPROFILE%\.trae\skills\project-spec\SKILL.md`
- macOS/Linux：`~/.trae/skills/project-spec/SKILL.md`

在 Trae 中前往 **设置 → 技能与命令 → 全局**，确认开关已启用。

### 全局规则（始终生效，推荐）

1. 创建规则目录：`%USERPROFILE%\.trae\user_rules\`
2. 将规范正文保存为 `project-spec.md` 放入该目录
3. 在 Trae **设置 → 规则** 中确认该规则为「始终生效」

规则采用全量加载机制，每次对话自动注入，最接近原 DSH 插件的常驻效果。

## 从 DSH 移植说明

本技能移植自 DSH（DeepSeek Harness）插件 `dsh-project-spec`。原插件通过 Cordis `systemPrompt.section` 实现每轮系统提示全文注入。豆包和 Trae 均无对应插件 API，因此移植的是**意图 + 正文**，通过各自平台的技能/规则/偏好机制落地。

## 许可证

MIT
