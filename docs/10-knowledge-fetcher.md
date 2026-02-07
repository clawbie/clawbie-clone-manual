# 10 — knowledge-fetcher 专用子代理（补课/查资料不污染主上下文）

## 目标
把“补课/检索/引用整理”这类高噪声工作交给一个专用子代理（knowledge-fetcher）去做：
- 主会话只接收 **结构化结论 + 关键引用**
- 避免把大量原始材料灌进主会话上下文

## 适用场景
- 不熟的库/协议/工程实践，需要快速补课
- 想要更可靠的引用来源（而不是凭记忆编）
- 需要在 idx.md、README、spec 等 markdown 里摘关键段落

## 标准产出格式（子代理必须交付）
- TL;DR（<= 10 行）
- 关键步骤（bullet list，可执行）
- 风险/边界（什么时候不要做/需要人确认）
- 引用（2~5 条）：每条包含 URL + 摘录（尽量短）
- 建议下一步：主会话应该做什么

## 工作流 A（推荐）：OpenClaw 子代理 + idx.md
1) 主会话判断需要补课 → `sessions_spawn` 启动子代理
2) 子代理：
   - `web_fetch(idx.md/index.md)` 选 topic
   - 拉 HEAD/BODY（必要时校验 sha256；推荐用本地脚本缓存）
   - 读 BODY 只摘必要段落
3) 子代理按“标准产出格式”回传
4) 主会话验收：spot check 2~3 条引用，再输出最终答案/写入手册

## 工作流 B（可选）：外包给 OpenCode（opencode）
当补课任务非常大（多 topic、长文、多轮汇总），可以把执行外包给 opencode 跑：
- 优点：长任务不阻塞主会话；可并行检索+写作
- 缺点：多一层系统/模型，验收成本更高；需要避免让它接触敏感信息

### 何时用 opencode
- 需要跨多个 topic 做对比、整理成一份长文档
- 单次补课 > 10 分钟且产出较大

### opencode 外包要求
- 输入：只给公开材料的 URL / idx.md topic；不要给 secrets/memory
- 输出：必须包含引用与可复核链接
- 主会话验收：对关键结论做 spot check

（opencode 外包的具体执行模板见：`docs/08-opencode-outsourcing.md`）

## 安全边界
- 子代理/外包都**禁止**接触 token/PAT/cookie/credentials
- 只处理公开材料；涉及私密内容必须先脱敏再交付
