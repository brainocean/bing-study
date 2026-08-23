---
title: "DDD vs Ontology Engineering"
domain: ontology
topic: 基础概念
source: "Evans (2003) Domain-Driven Design; Keet Ch1; 讨论衍生"
prerequisites:
  - "[[definition-of-ontology]]"
  - "[[ontology-vs-database-vs-conceptual-model]]"
related:
  - "[[ontology-philosophical-vs-engineering]]"
  - "[[ontology-use-cases]]"
last_review: 2026-08-22
next_review: 2026-08-23
interval_days: 1
ease_factor: 2.5
mastery: 0.3
correct_streak: 0
error_log: []
created: 2026-08-22
modified: 2026-08-22
tags:
  - ddd
  - domain-model
  - bounded-context
  - comparison
  - expressiveness
  - decidability
---

# DDD vs Ontology Engineering

## 核心结论

> DDD 是 ontology engineering 的"应用内特化版"——做了同样的认识论工作（知识提取、ontological commitment），但有意识地限制在单个应用边界内，放弃了形式化推理和跨应用复用。

## 概念重叠（非常多）

| DDD 概念 | Ontology 对应 | 共同意图 |
|---|---|---|
| Ubiquitous Language | Shared vocabulary / formal terminology | 团队对概念有共识 |
| Entity | Class / Individual with identity | 有独立身份的存在物 |
| Value Object | Dependent entity / Quality | 依附于实体、无独立身份 |
| Aggregate | Composite entity with boundary | 一组有整体约束的存在物 |
| Domain Event | Event class | 世界中发生的事 |
| Invariant（不变量） | Axiom / Constraint | 关系间的必然约束 |
| "Knowledge Crunching" | Ontology elicitation | 从领域专家头脑中提取知识 |
| 选择 Entity vs Value Object | Ontological commitment | 决定某事物的存在论地位 |

当 Eric Evans 说"你选择把 `Order` 建模为 Entity 还是 Value Object"——这就是 ontological commitment。你在决定"订单是一个有持续身份的存在物，还是一个可替换的值"。

## 在三层架构中的位置

```
┌─────────────────────────────────┐
│         Ontology                │ ← 应用无关、可推理、跨团队共享
├─────────────────────────────────┤
│   DDD Domain Model             │ ← DDD 在这里
│   (application-specific)        │    为某个 bounded context 服务
├─────────────────────────────────┤
│   Implementation                │ ← 代码
└─────────────────────────────────┘
```

## 关键差异

| 维度 | DDD | Ontology |
|---|---|---|
| 作用域 | **Bounded Context**（一个团队/服务） | **整个领域**（跨组织共享） |
| 形式化载体 | 代码（class/interface） | 逻辑（OWL/DL） |
| 推理 | 无。不变量由程序员手写检查 | 有。推理机自动检查一致性、推导蕴含 |
| 世界假设 | CWA（aggregate 里没有的 = 不存在） | OWA（KB 里没有的 = 未知） |
| 复用目标 | 本团队内共享理解 | 跨团队、跨组织、跨应用共享 |
| 允许多视角 | ✅ 不同 Bounded Context 对同一概念可有不同模型 | 通常追求统一（或通过 ontology alignment 对接） |

## DDD Context Map ≈ Ontology Alignment

DDD 的 Context Map（管理不同 Bounded Context 之间的关系）非常像 ontology engineering 中的 ontology alignment / ontology mapping：

- 两个团队各自有 `Customer` 概念
- 需要定义翻译规则
- 这是 ontology engineering 的经典问题

如果把一个企业所有 Bounded Contexts 的 Ubiquitous Languages 统一起来，提升到形式化可推理的层面——就得到了 enterprise ontology。**Palantir Foundry 做的就是这件事。**

## 代码 vs OWL：不是形式化程度，是形式化种类

代码和 OWL 都是 100% 形式化的（无歧义、机器可处理）。真正的区别：

| | 代码 (Java/TS) | 逻辑 (OWL/DL) |
|---|---|---|
| 语义类型 | **操作性** — 告诉机器做什么步骤 | **声明性** — 告诉机器什么是真的 |
| 表达力 | 图灵完备（能表达一切可计算的） | **故意受限**（只表达 DL 片段） |
| 可推理性 | 几乎不可判定（Rice 定理） | **可判定**（关键问题算法保证终止） |
| 知识位置 | 埋在 if/else、方法实现中 | 显式声明，可被直接查询 |

### 为什么代码不能被推理：Rice 定理

> 对于图灵完备语言，几乎所有关于程序语义的非平凡性质都是不可判定的。

你无法写一个通用程序来自动判断另一个程序"是否满足某某性质"。

OWL/DL 的策略：**故意限制表达力，换取可判定性。**

### 具体对比

**代码版（DDD）：**
```java
class Employee {
    private Department dept;
    void setDept(Department d) {
        if (d == null) throw new IllegalArgumentException();
        this.dept = d;
    }
}
```

**OWL 版：**
```
Employee SubClassOf (belongsTo exactly 1 Department)
```

两者都表达"每个员工属于恰好一个部门"。但 OWL 版能做到代码版做不到的事：

1. **自动推导**：新加 `Manager SubClassOf Employee` → 推理机自动得出 Manager 也必须属于恰好一个 Department
2. **一致性检查**：声明 Bob 属于两个部门 → 推理机自动报告矛盾
3. **分类推理**：自动发现"你定义的 A 其实是 B 的子类"（即使你没显式声明）

对代码问不了的问题：
> "根据我这 500 个 class 的定义，逻辑上必然成立的所有结论是什么？"

对 500 条 OWL 公理，推理机可以回答。

### 根本 Tradeoff

```
表达力：   Code >>>>>>> OWL DL
可推理性： OWL DL >>>>> Code
```

- 要"能表达一切" → 代码 → 失去自动推理
- 要"机器能自动推导/检查一致性" → OWL → 接受表达力受限

### 精确表述

> 代码告诉机器**怎么做**（operational）；Ontology 告诉机器**什么是真的**（declarative）。前者更强大但不透明；后者更受限但可推理。这是表达力 vs 可判定性的根本 tradeoff。

## 总结

DDD 和 Ontology Engineering 的关系：
1. **做同样的前期工作**：知识提取、概念建模、做 ontological commitment
2. **DDD 停在中间层**：application-specific、不追求跨应用复用
3. **DDD 用更强但不可推理的形式化**（代码）；Ontology 用更弱但可推理的形式化（逻辑）
4. **Enterprise ontology = 所有 bounded contexts 的统一 + 形式化提升**

## 关联阅读

- Evans (2003) *Domain-Driven Design* — DDD 经典
- Vernon (2013) *Implementing Domain-Driven Design* — DDD 实践
- Guizzardi (2005) *Ontological Foundations for Structural Conceptual Models* — 用 ontology 分析概念建模
- de Cesare & Lycett (2006) "Business Modelling with UML: distilling directions for future research using a chauffeured inquiry" — DDD 与 ontology 的交叉研究
