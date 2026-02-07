# 05 — 定时与对外发送：cron / message

## 5.1 cron（提醒）
- 适合：一次性提醒、固定周期提醒
- 提醒文案要写成“到点直接可读”的提醒语气，并包含上下文

## 5.2 message（主动对外发送）
- 用于：向 Feishu/Telegram/Discord 等发送消息
- 关键规则：如果用 `message(action=send)` 交付最终答复，主回复需要输出 `NO_REPLY` 避免重复
- 未经用户明确授权，不要群发/广播
