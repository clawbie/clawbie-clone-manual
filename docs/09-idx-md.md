# 09 — idx.md（给 AI 用的 Markdown 资源索引/注册表）

## 它是什么
- idx.md 是一个面向 AI/Agent 的 **Markdown registry**：先看索引（index），再按 topic 拉取具体文档。
- 适合用来“补课”：当你遇到未知 skill/库/协议，去 idx.md 找到对应 markdown，然后只读取必要段落。

索引入口：
- https://idx.md/index.md
- https://idx.md/category/index.md

## 标准拉取协议（强烈建议遵守）
1) 从 index 中找到 topic 行：`|/data/<topic>|`
2) 拉 HEAD：`https://idx.md/data/<topic>/HEAD.md`
3) 拉 BODY：`https://idx.md/data/<topic>/BODY.md`
4) **校验完整性**：对 BODY 原始字节做 sha256，必须等于 HEAD 的 `content_sha256`

## 防止“刷索引烧钱”的规则
- 只有在“确实不懂/需要引用”时才查 idx.md
- 先用关键词在 index 文本里匹配候选 topic（1~3 个），再拉 HEAD/BODY
- BODY 拉取后优先做：摘要 + 关键引用（不要整篇灌进上下文）

## 本仓库建议的落地方式（给维护者 AI）
- 在你的运行环境里实现一个轻量脚本：`idx_fetch(topic)`
  - 负责：抓 HEAD/BODY + sha256 校验 + 本地缓存
- 在手册中记录：
  - 什么时候触发 idx.md
  - 如何选 topic
  - 如何校验与缓存

（在 Clawbie 的 OpenClaw 环境里，我们已实现了脚本 `scripts/idx_fetch.mjs`，并在本地缓存到 `out/idx-cache/`。）

---

## 推荐实践：配合 knowledge-fetcher 子代理
为避免污染主上下文，建议把 idx.md 的“检索 topic + 摘录引用”交给专用子代理处理：`docs/10-knowledge-fetcher.md`。
