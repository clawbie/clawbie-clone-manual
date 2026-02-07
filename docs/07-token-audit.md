# 07 — Token 统计（给分身做自我审计）

> 目标：区分“主会话消耗”与“外包（spawn 子会话）消耗”。

## 7.1 快速看：sessions_list
- `sessions_list` 通常能提供各会话的 `totalTokens`（若该实现启用累计）
- 外包会话（spawn）会有独立 session，可单独统计

## 7.2 精确汇总：jq 汇总 transcript
如果要精确统计：
1) 从 `sessions_list` 找到会话的 `transcriptPath`
2) 对 jsonl 汇总每条消息里的 `usage.totalTokens`

示例（按实际路径调整）：
```bash
jq -r 'select(.messages) | .messages[]? | .usage.totalTokens? // empty' < TRANSCRIPT.jsonl \
  | awk '{s+=$1} END{print s}'
```
