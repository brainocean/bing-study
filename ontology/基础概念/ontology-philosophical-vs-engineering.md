---
title: 'Ontology: 哲学本体论 vs 工程本体论'
domain: ontology
topic: 基础概念
source: 综合梳理：Aristotle → Gruber → Palantir
prerequisites: []
related:
- '[[substance-and-accident]]'
- '[[categories-aristotle]]'
last_review: 2026-08-29
next_review: 2026-08-31
interval_days: 2
ease_factor: 2.6
mastery: 0.4
correct_streak: 1
error_log: []
anki_cards:
- anki_note_id: 1788357098396
  type: cloze
  text: 哲学本体论的态度是 {{c1::Realism（试图描述世界真实结构）}}，工程本体论的态度是 {{c2::Instrumentalism（构建有用模型）}}
  back_extra: 哲学追问'什么真正存在'，工程追问'需要表达哪些概念'
  tags:
  - ontology
  - philosophical-ontology
  - engineering-ontology
- anki_note_id: 1788357098397
  type: basic
  front: Palantir 为什么把数据层叫 'Ontology' 而不是 'Schema'？比 DB schema 多了哪三层？
  back: 1) 业务含义：定义'什么是风险事件'等业务概念，不只是数据结构；2) 操作语义：AI agent 能对实体执行 action；3) 推理能力：从关系推导新知识（如供应链传递影响）
  tags:
  - ontology
  - palantir
  - schema
- anki_note_id: 1788357098398
  type: basic
  front: Aristotle 的本体论比工程 ontology 多追问哪三个问题？
  back: 1) 这个分类框架是否正确——是否对应世界的真实结构；2) 为什么是这些 categories 而不是别的——分类本身需要辩护；3) Substance 为什么是第一性的——存在论优先级的论证
  tags:
  - ontology
  - aristotle
  - categories
- anki_note_id: 1788357098399
  type: basic
  front: Aristotle 的 Substance、Accident、Relation 分别对应 Palantir Foundry 的什么概念？
  back: Substance（独立存在的实体）→ Object Type（如 Employee, Facility）；Accident（依附属性）→ Property（如 name, status）；Relation → Link Type（如
    employs, supplies_to）
  tags:
  - ontology
  - aristotle
  - palantir
  - mapping
created: 2026-08-22
modified: 2026-08-22
tags:
- meta
- aristotle
- palantir
- knowledge-graph
---


# Ontology: 哲学本体论 vs 工程本体论

## 核心区分

| | 哲学 Ontology | 工程 Ontology |
|---|---|---|
| 问题 | 什么*真正*存在？存在的基本结构是什么？ | 在这个领域中，我们需要表达哪些概念和关系？ |
| 态度 | Realism — 试图描述世界的*真实结构* | Instrumentalism — 构建一个*有用的模型* |
| 产出 | 形而上学理论 | 可计算的形式化 schema（OWL/RDF/知识图谱） |
| 数量 | 单数 "Ontology"（一个学科） | 复数 "ontologies"（一个领域一个） |
| 可错性 | 可以"错"——不符合实在 | 可以"不好用"——不能支持推理/决策 |

## 历史传承链

```
Aristotle《Categories》《Metaphysics》(~350 BC)
  │ "存在有多种说法"；Substance 是第一存在者
  │
  ├── 中世纪经院哲学 (Aquinas, Scotus, Ockham)
  │     形式化 substance/accident/relation
  │
  ├── Leibniz: characteristica universalis
  │     梦想：符号系统表达一切知识
  │
  ├── Frege/Russell → 现代形式逻辑
  │
  ↓
McCarthy & Hayes (1969): AI 需要 "知识表示"
  │ 问题：怎么让程序"知道"世界里有什么？
  │
  ↓
Gruber (1993): "An ontology is an explicit formal
                specification of a shared conceptualization"
  │ ← 这里术语从哲学迁移到 CS
  │
  ↓
W3C Semantic Web: RDF (2004), OWL (2004/2012)
  │ 标准化的本体描述语言
  │
  ├── Upper Ontologies: BFO (ISO 21838), DOLCE, SUMO
  │     试图提供跨领域通用分类框架
  │
  ↓
Industry: Palantir Foundry, Google Knowledge Graph,
          Neo4j, Amazon Neptune, enterprise KGs
```

## Aristotle ↔ Palantir 结构对应

| Aristotle 概念 | Palantir Foundry | 共同直觉 |
|---|---|---|
| Substance (οὐσία) — 独立存在的实体 | Object Type (Employee, Facility) | 世界由"东西"构成，东西是第一性的 |
| Accident — 依附于 substance 的属性 | Property (name, status, location) | 属性不能脱离实体独立存在 |
| Relation (πρός τι) — 实体间联系 | Link Type (employs, supplies_to) | 实体间有结构化关系 |
| Categories — 最高层分类框架 | Object Type 层级 / Upper Ontology | 需要一个顶层分类来组织一切 |
| Genus → Species → Differentia | 类型继承 (Vehicle → Truck) | 层级分类，越具体越往下 |
| Act (ἐνέργεια) — 实体的活动 | Action (approve, deploy, assign) | 实体能"做"事，不只是被动数据 |

## 关键差异

### Aristotle 多出来的追问

Aristotle 不只问"用什么分类框架"，还问：
1. **这个框架*正确*吗？** — 是否对应世界的真实结构
2. **为什么是这些 categories 而不是别的？** — 分类本身需要辩护
3. **Substance 为什么是第一性的？** — 存在论优先级的论证

工程 ontology 不问这些。它问：**这个模型能不能支持我要做的推理和决策？**

### Palantir 为什么用 "Ontology" 而非 "Schema"

因为它比 database schema 多了三层语义：
1. **业务含义**：不只定义数据结构，还定义"什么是风险事件"这种业务概念
2. **操作语义**：AI agent 能对实体执行什么 action
3. **推理能力**：从关系中推导出新知识（如 A 供应 B，B 供应 C → A 间接影响 C）

这恰恰是 Aristotle 的 Categories 想做的：不只列清单，而是说清楚每个东西*是什么*、*能干什么*。

## 对学习的启示

从 Palantir/工程 ontology 入手再回看哲学 ontology 是有效路径：
- 你已经直觉理解 Object / Property / Relation 这套东西
- Aristotle 的 Categories 就是在 2400 年前用自然语言做同一件事
- 差异在于：哲学还追问"这个框架本身的正当性"

## 关联阅读

- *Semantic Web for the Working Ontologist* (3rd ed) — 工程 ontology 的圣经
- Gruber (1993) "A Translation Approach to Portable Ontology Specifications" — CS ontology 定义的源头
- Aristotle《Categories》— 2400 年前的 v0.1
- Stanford SEP: [Ontology and Information Systems](https://plato.stanford.edu/entries/ontology-is/) — 桥梁文章
