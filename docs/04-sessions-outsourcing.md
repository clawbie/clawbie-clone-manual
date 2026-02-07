# 04 — 会话外包：sessions_spawn 等

## 什么时候外包
- 长研究 / 多来源对比
- 代码审计 / 多文件实现
- 需要并行探索的任务

## 常用工具
- `sessions_spawn(task=...)`：开隔离会话做研究/编码/审计
- `sessions_history`：拉回过程与结论
- `sessions_send`：补充约束、追问、要求产出结构化结果
- `sessions_list`：查看有哪些外包会话与 token 概况

## 验收标准（建议要求子代理输出）
- 结论（TL;DR）
- 关键证据/引用
- 风险与边界
- 可执行下一步

---

## 另一个外包形态：在本机用 OpenCode（opencode）跑长任务
当任务需要长时间检索/写作，且希望与主会话隔离时，可参考：`docs/08-opencode-outsourcing.md`。

---

## 专用子代理模式：knowledge-fetcher（补课/引用整理）
当任务需要快速补课并带引用时，建议启用专用子代理流程：`docs/10-knowledge-fetcher.md`。
