---
title: "Ontology vs Database vs 概念模型"
domain: ontology
topic: 基础概念
source: "Keet, An Introduction to Ontology Engineering, Ch1 §1.2.1"
page: "4-6"
prerequisites:
  - "[[definition-of-ontology]]"
related:
  - "[[open-world-vs-closed-world]]"
  - "[[ontology-philosophical-vs-engineering]]"
last_review: 2026-08-22
next_review: 2026-08-23
interval_days: 1
ease_factor: 2.5
mastery: 0.0
correct_streak: 0
error_log: []
created: 2026-08-22
modified: 2026-08-22
tags:
  - comparison
  - database
  - uml
  - schema
---

# Ontology vs Database vs 概念模型

## 三层对比

| 维度 | Relational DB | 概念模型 (UML/EER) | Ontology |
|---|---|---|---|
| 目的 | 存储和查询数据 | 描述某应用的数据结构 | 表达某领域的知识（应用无关） |
| 作用域 | Application-specific | Application-specific | **Application-independent** |
| 知识表示 | 隐式（在 query 和 app 逻辑中） | 半显式（图形化） | **显式**（形式化规则） |
| 推理能力 | SQL 查询（无推理） | 无 | **自动推理**（推导隐含知识、检测矛盾） |
| 世界假设 | Closed World（不在 DB 中 = 假） | 无明确立场 | **Open World**（不在 KB 中 = 未知） |
| 复用性 | 低（绑定应用） | 中 | **高**（跨应用共享） |
| 形式化程度 | SQL DDL | 图形+自然语言 | 逻辑语言（OWL/DL） |

## 核心洞察

### 概念模型 vs Ontology

> "A conceptual data model provides an **application-specific** implementation-independent representation, whereas ontologies provide an **application-independent** representation of a subject domain."
> — Keet, §1.2.1

类比 developer 经验：
- **概念模型** ≈ 你为某个微服务设计的 domain model
- **Ontology** ≈ 整个行业的 domain model，任何人都可以基于它建应用

### DB vs Ontology (Knowledge Base)

数据库和本体（作为知识库）的三个关键区别：

1. **显式知识表示**：Ontology 包含规则（rules），不只是数据
2. **自动推理**：能从已有知识推导出新知识、发现矛盾
3. **Open World Assumption**：没说的不等于假——见 [[open-world-vs-closed-world]]

### 类比：代码世界的对应

| 概念 | 代码世界类比 |
|---|---|
| DB Schema | `CREATE TABLE` — 纯结构 |
| 概念模型 | UML Class Diagram — 设计某 app |
| Ontology TBox | Type system + inference rules — 跨项目通用 |
| Ontology ABox | 具体实例数据 |

## 分层架构

Keet 书中 Figure 1.5 展示的经典三层：

```
┌─────────────────────────────────┐
│         Ontology                │ ← 共享语义层
│   (application-independent)     │    "Flower", "Colour", "qt" relation
├─────────────────────────────────┤
│   Conceptual Data Models        │ ← 各应用的设计
│   (EER, UML, ORM...)           │    各自命名、各自约束
├─────────────────────────────────┤
│   Implementations               │ ← 实际系统
│   (DB, C++ app, ...)           │    各自数据类型、各自存储
└─────────────────────────────────┘
```

**Ontology 的角色**：连接不同实现和不同概念模型的"统一语义层"。

这正是 Palantir Foundry 的 Ontology layer 在做的事：在碎片化的企业数据系统之上提供一个统一语义。

## 重要区分

- 把 UML 翻译成 OWL **不会**自动让它变成 ontology
- Ontology 需要额外的东西：ontological commitment（你选择如何分类世界）
- 例子：`Flower hasColor Color` 中的 `hasColor` 不是随便一个关联——在本体论中它是一个 **inherence** 关系（颜色依存于花，花不存在则该颜色实例不存在）
