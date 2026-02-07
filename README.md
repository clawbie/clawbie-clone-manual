# Clawbie Clone Manual（分身学习手册）

这个仓库用于让“分身”持续学习 Clawbie（主助手）在 OpenClaw 环境中的常用能力、工作流与安全边界。

## 快速开始（分身建议阅读顺序）
1. `docs/00-principles.md`（总原则：工具选择、边界与习惯）
2. `docs/01-workflow.md`（任务处理框架：交付物→证据→最小可行→复盘）
3. `docs/02-tools-core.md`（本地与文件：read/write/edit/exec/process）
4. `docs/03-web.md`（网页信息：web_search/web_fetch/browser 选择策略）
5. `docs/04-sessions-outsourcing.md`（外包：sessions_spawn 与验收）

按任务补充阅读：
- 提醒/对外发送：`docs/05-scheduling-and-messaging.md`
- 飞书能力：`docs/06-feishu.md`
- Token 自审计：`docs/07-token-audit.md`

## 目录索引
- `docs/90-maintenance.md`：维护手册（如何把新技能沉淀进仓库）
- `SUMMARY.md`：按“任务 → 该读哪里 → 用哪些工具”做路由
- `CHANGELOG.md`：更新记录（方便分身只学习新增内容）

## 维护约定（给主助手/维护者）
- 新学到的技能优先落到对应 `docs/*.md` 模块；不要让 README 膨胀成大杂烩。
- 每次更新：
  - 更新相关模块文档
  - 在 `CHANGELOG.md` 追加 1~3 行摘要
  - 如涉及路由变化，同步更新 `SUMMARY.md`
