---
title: Ontology vs Database vs 概念模型
domain: ontology
topic: 基础概念
source: Keet, An Introduction to Ontology Engineering, Ch1 §1.2.1
page: 4-6
prerequisites:
- '[[definition-of-ontology]]'
related:
- '[[open-world-vs-closed-world]]'
- '[[ontology-philosophical-vs-engineering]]'
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
    front: "Relational DB、概念模型（UML）、Ontology 在作用域上的核心区别是什么？"
    back: "DB 和概念模型都是 application-specific（绑定特定应用），Ontology 是 application-independent（表达领域知识，不绑定具体应用，可跨应用复用）"
    tags: [ontology, database, conceptual-model, comparison]
  - anki_note_id: null
    type: cloze
    text: "Description Logic 将知识库分为两层：{{c1::TBox（Terminological Box）定义概念和关系规则}}，{{c2::ABox（Assertional Box）声明具体实例事实}}"
    back_extra: "类比：TBox ≈ TypeScript 的 interface/type，ABox ≈ 运行时的实际对象"
    tags: [ontology, tbox-abox, description-logic]
  - anki_note_id: null
    type: basic
    front: "Ontology 中 inherence 是什么意思？以 'Flower hasColour Colour' 为例说明。"
    back: "Inherence 指 dependent particular（依存性个体）不能脱离其 bearer 独立存在。花₁的红色₁是一个特定 quality instance，依存于花₁——花₁不存在则该颜色实例也不存在。但 Colour 作为 universal（类）本身不依存于任何特定花"
    tags: [ontology, inherence, quality, dependent-particular]
  - anki_note_id: null
    type: basic
    front: "为什么把 UML 翻译成 OWL 不会自动产生一个 ontology？"
    back: "因为 ontology 需要 ontological commitment——显式声明如何分类世界。UML 不区分属性的本体论性质（如 colour 是 inherent quality，price 是 relational property，id 是技术标识符），而 ontology 要求对每个属性做这种显式声明"
    tags: [ontology, uml, owl, ontological-commitment]
  - anki_note_id: null
    type: basic
    front: "Knowledge Graph 和 Ontology 各自偏重 TBox 还是 ABox？两者共存叫什么？"
    back: "Knowledge Graph 偏 ABox（大量实例三元组，概念层相对简单）；Ontology 偏 TBox（精心设计的概念层级和推理规则，实例可以很少）。两者共存 = Knowledge Base (KB)"
    tags: [ontology, knowledge-graph, tbox-abox, knowledge-base]
created: 2026-08-22
modified: 2026-08-24
tags:
- comparison
- database
- uml
- schema
- tbox-abox
- inherence
- ontoUML
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

## TBox 与 ABox

Description Logic（OWL 的理论基础）将知识库分为两层：

| | TBox (Terminological Box) | ABox (Assertional Box) |
|---|---|---|
| 内容 | 概念定义和关系规则 | 具体实例声明 |
| 类比 | TypeScript 的 `interface` / `type` | 运行时创建的实际对象 |
| 例子 | `Employee SubClassOf Person`<br>`hasManager range Employee` | `Alice: Employee`<br>`Alice hasManager Bob` |
| 说的是 | "世界的结构可以/必须是什么样" | "世界里有什么具体事实" |

- **Knowledge Graph 偏 ABox**：大量实例三元组，概念层相对简单
- **Ontology 偏 TBox**：精心设计的概念层级和推理规则，实例可以很少
- 两者共存 = Knowledge Base (KB)

## Knowledge Graph Schema 与 Ontology 的关系

KG 的 schema/metadata 与 ontology 是一个光谱关系，不是等价：

```
Neo4j constraints ← 很弱                              很强 → OWL Formal Ontology
     │                                                         │
  结构约束        controlled      taxonomy      lightweight    formal
  (CWA 验证)     vocabulary                    ontology       ontology
```

Neo4j 级别的 constraints（uniqueness, existence, node key）本质是 **DB 级结构验证**（CWA），不能表达：
- 类层级 + 推理继承（`Manager SubClassOf Employee`）
- 关系的传递性、对称性等特征
- 从已有事实推导新关系
- Disjointness（互斥类）

大多数企业 KG（包括 Palantir）落在 **lightweight ontology** 位置：有类层级、有关系语义、有基本约束，但不做完整 DL 推理。

## Inherence 的精确含义

`Flower hasColour Colour` 中的 inherence 需要区分 universal 与 particular 两个层面：

| 层面 | 声明 | 依存？ |
|---|---|---|
| Universal | Colour 这个类存在 | 不依存于任何特定花 |
| Particular | 花₁ 的红色₁（特定 quality instance） | **依存于**花₁ |

Inherence 的 ontological commitment：颜色作为 **dependent particular**（依存性个体），不能脱离其 bearer 独立存在。Tree 也可以 hasColour，那是另一个 particular quality instance。

## UML Composition vs Ontological Inherence

| | UML Composition（◆） | Ontological Inherence |
|---|---|---|
| 本体论类别 | Mereology（部分论） | Quality dependence |
| 例子 | 花瓣是花的 part | 花的红色 inheres in 花 |
| 共同点 | 依存者随宿主消亡 | 同左 |
| 区别 | part 是独立实体（有质量、有位置） | quality 不是独立实体 |

UML Composition 能表达 part-whole，但没有语法表达 inherence。

## UML Association 的 Role/Cardinality/Constraint vs Ontology

三者有表面相似性，但在不同层面操作：

| UML 要素 | Ontology 类似物 | 关键区别 |
|---|---|---|
| Role name（`+employer`） | Ontological role | UML 只命名位置；ontology 声明 rigid vs anti-rigid |
| Cardinality（`1..*`） | OWL cardinality restriction | UML 违反→报错(CWA)；OWL 违反→推理(OWA) |
| Constraints（`{xor}`, OCL） | OWL axioms | UML = 验证；OWL = 影响逻辑一致性 |

核心区别：**UML 描述模型的形状（structural），Ontology 声明事物的存在方式（ontological）。**

## UML Attribute 的本体论暧昧性

UML 把所有字段统一为 `name: Type`，不区分其本体论性质：

| UML attribute | 实际本体论性质 | 算 inherence？ |
|---|---|---|
| `flower.colour = Red` | 内禀性质（quality） | ✅ |
| `flower.weight = 5g` | 内禀性质（quantity） | ✅ |
| `flower.id = "F001"` | 技术标识符 | ❌ |
| `flower.price = 5.99` | 关系性属性（依赖市场/时间） | ❌ |
| `flower.supplier = "X"` | 到另一实体的关系 | ❌ |
| `flower.species = "Rosa"` | 分类/实例化 | ❌ |

Ontology 要求对每个"属性"做本体论性质的显式声明。这是"UML 转 OWL ≠ ontology"的深层原因。

## OntoUML：桥接 UML 与 Ontology

OntoUML 是一种在 UML 语法上叠加 ontological commitment 层的扩展：

| OntoUML 要求 | 例子 |
|---|---|
| Class 是 Kind（本质）还是 Role（角色）？ | `Person` = Kind; `Customer` = Role |
| 关系由什么 Relator 中介？ | `Employment` 中介 Person 和 Company |
| 属性是 intrinsic moment 还是 relational？ | `colour` = intrinsic; `price` = relational |

OntoUML 强制 UML 建模者做本体论决策，弥合结构描述与存在声明之间的鸿沟。
