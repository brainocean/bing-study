---
title: Ontology 的定义演进
domain: ontology
topic: 基础概念
source: Keet, An Introduction to Ontology Engineering, Ch1 §1.2
page: 4-7
prerequisites: []
related:
- '[[ontology-philosophical-vs-engineering]]'
- '[[ontology-vs-database-vs-conceptual-model]]'
last_review: 2026-08-29
next_review: 2026-08-31
interval_days: 2
ease_factor: 2.6
mastery: 0.4
correct_streak: 1
error_log: []
created: 2026-08-22
modified: 2026-08-22
tags:
- definition
- gruber
- guarino
---


# Ontology 的定义演进

## 核心定义序列

学界对 "什么是 ontology" 没有统一定义，但有一条越来越精确的演进链：

### Def 1: Gruber (1993)

> "An ontology is a specification of a conceptualization."

**问题**："conceptualization" 和 "specification" 都是模糊词，用两个模糊词解释第三个。

### Def 2: Studer, Benjamins, Fensel (1998)

> "An ontology is a **formal, explicit** specification of a **shared** conceptualization."

**改进**：加了三个约束——formal（机器可处理）、explicit（显式声明）、shared（社群共识）。
**遗留问题**：shared 到什么程度算 shared？两个人够不够？

### Def 3: Guarino (1998) — 最完整

> "An ontology is a logical theory accounting for the **intended meaning** of a formal vocabulary, i.e. its **ontological commitment** to a particular conceptualization of the world."

**关键概念**：
- **Ontological commitment**（本体论承诺）：选择某个 vocabulary 就意味着你承诺了一种世界观
- **Intended models**：不是所有逻辑上合法的解释，而是你*想要*的那些解释
- Ontology 通过约束把"所有可能的模型"收窄到"你意图中的模型"

### Def 4: W3C / OWL (2003)

> "An ontology [is] equivalent to a Description Logic knowledge base."

**问题**：过度限制——把"OWL 文件"等同于"ontology"，但 thesaurus 转成 OWL 不自动变成 ontology；非 OWL 表达的东西也可以是 ontology。

## 实用理解

对 developer 来说，工作定义：

**Ontology = 一个领域中的概念、关系和约束的形式化表达，使得机器可以进行推理，并且这套表达反映了社群的共识。**

与纯 schema 的区别在于：
- Schema 告诉你数据*长什么样*（结构）
- Ontology 告诉你世界里*有什么*以及它们*是什么*（语义）

## 大写 vs 小写

| 写法 | 含义 |
|---|---|
| Ontology（大写、单数） | 哲学学科：研究"存在"的本质 |
| ontology / ontologies（小写、可复数） | 工程制品：某领域的形式化知识表示 |

## 易错点

- "只要用 OWL 写了就是 ontology" ← 错。Thesaurus in OWL ≠ ontology
- "Ontology = taxonomy" ← 错。Taxonomy 只有 is-a 层级；ontology 还有 relations、constraints、rules
- "Ontology = knowledge graph" ← 不完全。KG 通常偏实例数据（ABox），ontology 偏概念层（TBox）
