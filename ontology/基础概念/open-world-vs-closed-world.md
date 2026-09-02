---
title: Open World Assumption vs Closed World Assumption
domain: ontology
topic: 基础概念
source: Keet, An Introduction to Ontology Engineering, Ch1 §1.2.1
page: '5'
prerequisites: []
related:
- '[[ontology-vs-database-vs-conceptual-model]]'
- '[[definition-of-ontology]]'
last_review: 2026-08-29
next_review: 2026-08-31
interval_days: 2
ease_factor: 2.6
mastery: 0.4
correct_streak: 1
error_log: []
anki_cards:
  - anki_note_id: null
    type: basic
    front: "CWA 和 OWA 的核心原则分别是什么？"
    back: "CWA（Closed World Assumption）：不在数据库中的信息视为**假**。OWA（Open World Assumption）：不在知识库中的信息视为**未知**。CWA 常用于关系型数据库，OWA 常用于 Ontology / Knowledge Base。"
    tags: [ontology, owa, cwa, reasoning]
  - anki_note_id: null
    type: basic
    front: "在 OWL 中声明 Bob: Person 但未声明 Bob 是 Student，推理器会得出什么结论？为什么？"
    back: "推理器**无法断定** Bob 不是 Student（OWA：缺失信息 = 未知）。若需否定，必须显式声明 Person DisjointWith Student，或声明 Bob: ¬Student。"
    tags: [ontology, owa, owl, negation]
  - anki_note_id: null
    type: cloze
    text: "在 {{c1::OWA}} 下，缺失信息 = {{c2::未知}}；在 {{c1::CWA}} 下，缺失信息 = {{c2::假}}"
    tags: [ontology, owa, cwa, reasoning]
  - anki_note_id: null
    type: basic
    front: "Ontology 为什么采用 OWA 而非 CWA？（三个原因）"
    back: '1. **分布式知识**：Ontology 跨系统共享，无单一来源掌握所有事实；2. **不完备信息**：现实知识永远不完整，断言"不存在"比断言"存在"需要更强证据；3. **可扩展性**：新知识随时可加入，不应破坏已有推理。'
    tags: [ontology, owa, reasoning, fundamental]
created: 2026-08-22
modified: 2026-08-22
tags:
- owa
- cwa
- reasoning
- fundamental
---


# Open World Assumption vs Closed World Assumption

## 核心区分

| | Closed World Assumption (CWA) | Open World Assumption (OWA) |
|---|---|---|
| 原则 | 不在 DB 中的 = **假** | 不在 KB 中的 = **未知** |
| 典型场景 | 关系型数据库 | Ontology / Knowledge Base |
| 类比 | 花名册上没你 → 你不是学生 | 花名册上没你 → 不确定你是不是学生 |
| 对 NULL 的态度 | NULL = 不存在/不适用 | NULL = 我们还不知道 |

## 为什么 Ontology 用 OWA

1. **分布式知识**：Ontology 设计为跨系统、跨组织共享。没有任何单一来源掌握所有事实。
2. **不完备信息**：现实世界的知识永远不完整。断言某事"不存在"比断言"存在"需要更强的证据。
3. **可扩展性**：新知识随时可加入，不应破坏已有推理。

## 对推理的影响

### CWA 下（数据库）
```sql
-- "谁没选课？" → 查不到选课记录 = 没选课
SELECT * FROM students WHERE id NOT IN (SELECT student_id FROM enrollments);
```

### OWA 下（Ontology）
```
-- "Bob 选了什么课？" → KB 中没有 Bob 选课的记录
-- 结论：不知道 Bob 是否选了课（NOT: Bob 没选课）
-- 要断言 Bob 没选课，需要显式声明
```

## 实际影响：OWL 中的典型"坑"

### 坑 1：Negation 不按直觉来

你在 OWL 中声明 `Bob: Person`，没有说 Bob 是 Student。
- **你期望**：Bob 不是 Student ← CWA 直觉
- **OWL 推理**：不知道 Bob 是不是 Student ← OWA

要在 OWL 中得出 "Bob 不是 Student"，需要：
- 声明 `Person DisjointWith Student`，或
- 显式声明 `Bob: ¬Student`

### 坑 2：Cardinality 约束不按直觉来

声明 `Person hasChild exactly 2`，但 KB 中只列了 Alice 的一个孩子。
- **CWA 期望**：违反约束！
- **OWA 实际**：合法——可能还有一个孩子我们不知道

### 坑 3：Unique Name Assumption

OWA 通常也不假设 Unique Names：
- `Alice` 和 `Bob` 可能是同一个个体，除非你显式声明 `DifferentIndividuals(Alice, Bob)`

## 类比

| CWA | OWA |
|---|---|
| 法庭判决：证据不足 = 无罪释放 | 科学研究：证据不足 = 尚无定论 |
| 编译器 type check：类型不匹配 = 错误 | 动态类型：运行时才知道 |
| 我的通讯录里没你 = 你不是我朋友 | 我的通讯录里没你 = 我可能还没加你 |

## 工程启示

对于建 knowledge graph / ontology 的 developer：
- 设计推理规则时，要时刻记住 OWA：**没有的信息 ≠ 否定信息**
- 如果你需要 CWA 行为（比如"列出所有没选课的学生"），需要额外机制（SPARQL `NOT EXISTS`、SHACL validation、或应用层逻辑）
- Palantir 的 Ontology 在实际使用中混合了两种假设：schema 层 OWA（新数据类型可随时加入），应用层 CWA（Action 执行时假设当前数据完整）
