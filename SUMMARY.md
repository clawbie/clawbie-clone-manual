# SUMMARY（任务路由索引）

> 目标：让分身在接到任务时，能快速决定“读哪份文档 + 用哪些工具”。

## 任务 → 阅读路径 → 工具

### I. 遇到未知库/协议/Skill：用 idx.md 补课
- 读：`docs/09-idx-md.md`
- 工具：`web_fetch`（index/HEAD/BODY）+（可选）本地 sha256 校验与缓存

### H. OpenCode 外包执行（长任务不阻塞主会话）
- 读：`docs/08-opencode-outsourcing.md`
- 工具：`exec`/`process`（运行与日志） + opencode CLI
- 关键：外包产出必须验收后再对外交付

### Z. 维护这份手册（新增技能如何写入）
- 读：`docs/90-maintenance.md`（维护流程） + `docs/91-ai-maintainer-protocol.md`（AI 自检/协议）
- 输出：更新对应模块 + `SUMMARY.md` + `CHANGELOG.md`（必要时 README）

### A. 写文档 / 产出可共享材料
- 读：`docs/02-tools-core.md`（文件与本地执行） + `docs/01-workflow.md`
- 工具：`read` / `write` / `edit`，必要时 `exec`

### B. 需要证据的查询（技术资料、对比、摘录）
- 读：`docs/03-web.md`
- 工具优先级：`web_search` → `web_fetch` →（必要时）`browser`

### C. 复杂任务：外包给子代理（研究/长文本/代码审计）
- 读：`docs/04-sessions-outsourcing.md`
- 工具：`sessions_spawn` / `sessions_history` / `sessions_send`

### D. 定时提醒 / 例行任务
- 读：`docs/05-scheduling-and-messaging.md`
- 工具：`cron`

### E. 主动对外发送消息
- 读：`docs/05-scheduling-and-messaging.md`
- 工具：`message`
- 关键约定：如果用 `message(action=send)` 作为最终交付，主回复要输出 `NO_REPLY` 避免重复。

### F. 飞书文档/知识库/表格（Feishu）
- 读：`docs/06-feishu.md`
- 工具：`feishu_doc` / `feishu_wiki` / `feishu_drive` / `feishu_bitable_*`

### G. Token / 成本审计（主会话 vs 外包）
- 读：`docs/07-token-audit.md`
- 工具：`sessions_list` + `jq`（配合 transcript 汇总）
