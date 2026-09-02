# Frontmatter 规范

所有知识点 note 必须包含以下 YAML frontmatter。

---

## 完整字段

```yaml
---
# === 基本信息 ===
title: "Being qua Being"            # 知识点标题
domain: ontology                     # 所属领域
topic: 基础概念                       # 所属主题
source: "Aristotle, Metaphysics IV"  # 主要来源
page: "1003a-1003b"                  # 页码/段落（可选）

# === 依赖关系 ===
prerequisites:                       # 前置知识点（wikilink 列表）
  - "[[substance-and-accident]]"
related:                             # 关联知识点
  - "[[categories]]"
  - "[[universals]]"

# === 复习状态 ===
last_review: 2026-08-22              # 上次复习日期
next_review: 2026-08-23              # 下次复习日期
interval_days: 1                     # 当前间隔天数
ease_factor: 2.5                     # SM-2 ease factor（1.3-3.0）
mastery: 0.3                         # 掌握度（0.0-1.0）
correct_streak: 0                    # 连续正确次数

# === 错误记录 ===
error_log: []                        # 错误历史（见下方格式）

# === Anki 同步 ===
anki_cards: []                        # Anki 卡片（见下方格式）
anki_mastery_boost: 0                 # Anki 进度对 mastery 的累计加分（0-0.2）

# === 元数据 ===
created: 2026-08-22
modified: 2026-08-22
tags:                                # 自由标签
  - aristotle
  - first-philosophy
---
```

## error_log 条目格式

```yaml
error_log:
  - date: 2026-08-22
    type: 概念混淆          # 概念混淆 | 单点遗忘 | 表述不精确 | 前置缺失 | 理解表面化
    brief: "混淆了..."
```

## anki_cards 条目格式

Basic 卡片：
```yaml
anki_cards:
  - anki_note_id: null               # push 后由脚本填入 Anki note ID
    type: basic
    front: "Gruber (1993) 对 ontology 的定义是什么？"
    back: "An ontology is a specification of a conceptualization."
    tags: [ontology, definition, gruber]
```

Cloze 卡片：
```yaml
anki_cards:
  - anki_note_id: null
    type: cloze
    text: "Guarino 定义中的 {{c1::ontological commitment}} 指的是选择 vocabulary 就承诺了一种世界观"
    back_extra: "Guarino (1998)"      # 可选：显示在背面的补充信息
    tags: [ontology, guarino]
```

## 字段说明

| 字段 | 必填 | 说明 |
|---|---|---|
| title | ✅ | 知识点名称 |
| domain | ✅ | 所属领域（ontology, philosophy, history, ai...） |
| topic | ✅ | 领域内主题分组 |
| source | ✅ | 主要参考来源 |
| page | ❌ | 出处定位 |
| prerequisites | ❌ | 学习本知识点前需要掌握的 |
| related | ❌ | 相关但非前置的知识点 |
| last_review | ✅ | 初始为创建日期 |
| next_review | ✅ | 初始为创建日期 + 1 |
| interval_days | ✅ | 初始 1 |
| ease_factor | ✅ | 初始 2.5 |
| mastery | ✅ | 初始 0.3（学新后）或 0.0（仅 ingest 未学） |
| correct_streak | ✅ | 初始 0 |
| error_log | ✅ | 初始空数组 |
| created | ✅ | 创建日期 |
| modified | ✅ | 最后修改日期 |
| tags | ❌ | 自由标签，辅助检索 |
| anki_cards | ❌ | Anki 卡片列表，agent 生成，脚本同步。初始空数组 |
| anki_mastery_boost | ❌ | Anki 进度的累计 mastery 加分（0–0.2），脚本维护 |

## mastery 语义

| 范围 | 含义 |
|---|---|
| 0.0 | 仅 ingest，尚未学习 |
| 0.1-0.3 | 初学，刚接触 |
| 0.4-0.6 | 基本理解，偶有遗忘 |
| 0.7-0.8 | 掌握良好，能应用 |
| 0.9-1.0 | 融会贯通，能批判/综合 |
