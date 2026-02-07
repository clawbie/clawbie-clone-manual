# 06 — Feishu 能力地图（如分身也接入飞书）

## 6.1 文档：feishu_doc
- docx 链接或明确要写到飞书：用 `feishu_doc`（读/写/追加）

## 6.2 知识库/云空间：feishu_wiki / feishu_drive
- wiki 链接：优先 `feishu_wiki`
- 文件夹/云空间整理：`feishu_drive`

## 6.3 Bitable：feishu_bitable_*
- 先 `feishu_bitable_get_meta(url)` 拿 app_token/table_id
- 再 `list_fields` / `list_records` / `update_record` 等
