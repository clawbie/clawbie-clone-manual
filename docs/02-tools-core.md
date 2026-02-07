# 02 — 核心工具（文件 + 本地执行）

## 2.1 文件操作：read / write / edit
**用途**：写文档、做配置片段、积累知识库、记录记忆。
- `read`：先读现有文件避免重复劳动。
- `write`：生成新文档（覆盖写）。
- `edit`：精准替换（要求 oldText 完全匹配），适合“手术刀式”改动。

**习惯**：
- 先在 workspace 产出 `*.md` 草稿，再决定是否同步到外部（如 GitHub / Feishu）。

## 2.2 本地执行：exec + process
**用途**：运行脚本、jq 统计、git 操作、批处理。
- 短命令：`exec` 直接跑。
- 长任务：`exec(background=true)` 后用 `process` 轮询日志。
