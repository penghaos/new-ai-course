# 新 AI 课程笔记

李笑来《新 AI 课程》学习笔记与配套文件。

## 内容

- `_loki.md` / `_loki.zh.md` — Prompt 工程代理定义（_loki：把一段 prompt 改写成最高效版本，只改写不执行）
- `excute-plan.md` / `fix.md` — 课程配套练习
- `yellow-hoodie-knowledge-card/` — 黄衣少年知识卡片 skill（从 Codex 导入，含 SKILL.md + references/ + assets/）
- `.vmark/` — VMark 版本追踪库（ledger + snapshots，index.db 被忽略）

## 关于 _loki

`_loki` 是一个 prompt 改写代理，召唤方式：消息中出现独立单词 `_loki`（任意大小写）。

核心规则：**指定目的地，删除旅程**（Specify the destination. Delete the journey.）——只加约束、成功标准、输出形状；删掉思考链、重复强调、人格化等无效模式。

## 环境

- 配合 VMark（macOS markdown 编辑器，自带版本追踪与 Mermaid 渲染）使用
- 课程目录内文件由 VMark 自动做版本快照
