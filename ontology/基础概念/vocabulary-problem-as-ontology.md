---
title: 词汇问题的本体论根源（Furnas 1987 × Ontology）
domain: ontology
topic: 基础概念
source: "Furnas et al. (1987) The Vocabulary Problem in Human-System Communication, CACM 30(11): 964-971"
page: 964-971
prerequisites:
  - "[[being-qua-being]]"
  - "[[categories]]"
  - "[[substance-and-accident]]"
  - "[[quine-two-dogmas]]"
  - "[[definition-of-ontology]]"
related:
  - "[[ontology-philosophical-vs-engineering]]"
  - "[[ddd-vs-ontology-engineering]]"
  - "[[open-world-vs-closed-world]]"
  - "[[pirsig-quality-third-ontology]]"
last_review: "2026-09-29"
next_review: "2026-09-30"
interval_days: 1
ease_factor: 2.5
mastery: 0.3
correct_streak: 0
error_log: []
anki_cards:
  - anki_note_id: null
    type: basic
    front: "Furnas et al. (1987) 发现两人对同一对象使用相同术语的概率是多少？这个数据对'自然命名'意味着什么？"
    back: "概率 < 0.20（最低 0.07，最高 0.14）。即使使用统计最优的单一术语，失败率仍达 65-85%。'显而易见的名字'是一个神话——不存在单一好名字。"
    tags: [ontology, furnas, vocabulary-problem, naming]
  - anki_note_id: null
    type: basic
    front: "从 Aristotle 范畴论的角度，为什么人们对同一个对象起不同的名字？"
    back: "人们命名的不是 substance 本身，而是从不同范畴（quality, time, relation, place 等）入口抓住的不同 accident。同一个程序被叫做 nightlife（Time）、guide（Relation）、funtime（Quality）——每个名字隐含了不同的范畴优先级。"
    tags: [ontology, aristotle, categories, accident, naming]
  - anki_note_id: null
    type: basic
    front: "Guarino 的 ontological commitment 概念如何解释 Furnas 的词汇变异性？"
    back: "每个命名行为都是一个微型 ontological commitment。叫程序 nightlife 的人承诺了以时间为组织原则的世界观，叫 guide 的人承诺了以工具-用户关系为组织原则的世界观。1000 人产出 100+ 命名 = 100+ 种微型 ontological commitment。"
    tags: [ontology, guarino, ontological-commitment, vocabulary-problem]
  - anki_note_id: null
    type: basic
    front: "Zipf 分布的头部收敛（15-36% 的人选同一个词）除了文化共性之外，还有什么更深层的解释？"
    back: "至少三层：1) Zipf 的最省力原则——通信双方优化能耗的纳什均衡；2) 大脑硬件共性——Rosch 的 basic-level categories 是认知能耗最优的压缩层级；3) Friston 自由能原理——相似大脑对相似世界做最小能耗压缩，必然部分重叠。"
    tags: [ontology, zipf, rosch, friston, free-energy, naming]
  - anki_note_id: null
    type: basic
    front: "Rosch 的 basic-level categories 是什么？它为什么解释了 Furnas 数据中的头部收敛？"
    back: "人类命名物体时有一个特权层次——不太抽象也不太具体（说 chair 而非 furniture 或 kitchen chair with armrests）。这是信息增益与认知能耗的最优折中。所有人类大脑面临类似的代谢预算约束，所以收敛到相似的基本层次。Furnas 中命中率最高的词可能恰好位于 basic level。"
    tags: [ontology, rosch, basic-level, prototype-theory, naming]
  - anki_note_id: null
    type: cloze
    text: "Furnas 的 frequency-weighted unlimited aliasing 从贝叶斯角度看，是在用{{c1::人群的先验分布}}做推理。若先验部分来自{{c2::大脑结构（而非仅文化）}}，则跨文化仍大致成立。"
    tags: [ontology, furnas, bayesian, naming, cross-cultural]
  - anki_note_id: null
    type: basic
    front: "Naturalized pros hen 假说是什么？它如何综合 Aristotle、Kant 和 Quine？"
    back: "Pros hen 结构既非纯粹在世界中（Aristotle），也非纯粹在心灵中（Kant），而是世界结构与大脑结构的最优耦合产物。Substance 作为核心义，是因为识别稳定实体是预测能耗最低的策略——提供不变量，只需编码 accident 的变化。范畴是大脑与世界共同演化出的最低能耗接口。"
    tags: [ontology, aristotle, kant, quine, friston, pros-hen, naturalized]
  - anki_note_id: null
    type: cloze
    text: "Studer 定义 ontology 为 shared conceptualization 的 specification。Furnas 数据（一致率 < 0.20）直接挑战 shared：工程 ontology 的 sharing 不是{{c1::发现共识}}，而是{{c2::强制建立共识}}，因此本质上是脆弱的。"
    tags: [ontology, studer, shared-conceptualization, vocabulary-problem]
anki_mastery_boost: 0
created: "2026-09-29"
modified: "2026-09-29"
tags:
  - furnas
  - vocabulary-problem
  - naming
  - zipf
  - ontological-commitment
  - rosch
  - friston
  - free-energy
  - embodied-cognition
  - naturalized-kantianism
  - synthesis
---

# 词汇问题的本体论根源（Furnas 1987 × Ontology）

## 核心主张

Furnas et al. (1987) 的 vocabulary problem 表面是 HCI 问题，本质是本体论问题。人们对同一对象起不同的名字，不是"词汇贫乏"，而是因为**命名预设了分类，分类预设了本体论承诺，而本体论承诺因人而异**。

三层分析：

| 层次 | 问题 |
|---|---|
| 表层（Furnas） | 人们用不同的词指称同一个对象 |
| 中层（Aristotle） | 人们从不同的范畴/accident 入口认知同一个 substance |
| 深层（Quine） | 人们对同一刺激做出不同的 ontological commitment，因为不存在唯一正确的世界切割方式 |

## Furnas 的关键数据

五个应用领域（文本编辑命令、消息解码器、常见物体描述、分类广告、食谱关键词）：

| 策略 | 命中率 |
|---|---|
| Armchair naming（设计者凭直觉选一个名字） | 10–20% |
| 最优单词（统计频率最高的那个词） | 15–36% |
| 3 个最优别名 | 37–67% |
| 15 个最优别名 | 60–80% |
| Unlimited aliasing（前 3 次猜测） | 50–100% |

> "The idea of an 'obvious,' 'self-evident,' or 'natural' term is a myth!"

## 为什么人们用不同的词？——范畴入口的多样性

### Aristotle 视角：命名走 accident 路径

一个对象同时在所有十范畴上有存在方式。人们命名时抓住的是不同的 accident，而非 substance 本身。

以 Furnas 的经典例子（"一个告诉你周末城里有什么好玩的程序"）为例：

| 用户命名 | 抓住的范畴 |
|---|---|
| `nightlife` / `weekend` | Time |
| `events` / `activities` | Action |
| `funtime` / `amusements` | Quality |
| `aroundtown` / `downtown` | Place |
| `guide` | Relation（与用户的关系） |
| `goingson` / `happenings` | Passion（发生在世界上的事） |

这是 [[being-qua-being]] 中 pros hen 结构的微观实例：存在有多种方式，每个人从自己认知上最显著的那个方式入手。

### Essence 的不可达性

如果对象有明确的、认知可达的 essence，命名应当收敛。Furnas 的数据（< 0.20 一致率）提供了两种解读：

**温和实在论（Aristotle 式）**：essence 真实存在，但普通认知无法直接触及——人只能通过 accident 间接接近。不同人抓住的 accident 不同，所以命名发散。

**唯名论**：根本没有 essence 等在那里。"同一个对象"只是实用目的下画的边界。Furnas 的数据是唯名论的强力经验证据——如果 natural kinds 的 essence 是认知可达的，命名应该收敛。它没有。

### Guarino 的 ontological commitment 在个体层面

Guarino：选择一个 vocabulary = 承诺一种世界观。

Furnas 的数据把这个哲学论断变成经验事实：1000 人 × 1 个对象 = 100+ 种微型 ontological commitment。领域专家的变异性并不低于新手——变异性不是缺陷，是人类认知的结构性特征。

### 对 "shared conceptualization" 的挑战

Studer 定义 ontology 为 "shared conceptualization" 的 specification。一致率 < 0.20 意味着：
- 工程 ontology 的 sharing 不是"发现"共识，而是**强制建立**共识
- 共识是人工的——社会协调的产物，不反映自然认知收敛
- 因此新人进入系统时，自然词汇大概率与系统词汇不匹配

Furnas 的 unlimited aliasing = 放弃统一 ontological commitment 的幻想，用映射表把多种 commitment 路由到同一系统对象。**工程上的实用主义：不解决本体论分歧，用机制补偿。**

## Zipf 分布的深层解释——为什么有头部收敛？

Quine 解释了为什么人们**不同**（信念网因人而异），但没解释为什么**部分相同**。Zipf 分布在所有人类语言中成立，暗示比文化更底层的东西。

### 第一层：最省力原则（Zipf 1949）

通信博弈：
- 说话者想省力 → 用少量词覆盖多种意思（压缩）
- 听话者想清晰 → 每种意思有专属词（解压）
- 纳什均衡 → 幂律分布

这是**通信信道的物理约束**，不依赖具体文化内容。

### 第二层：大脑架构的共性——自然化的先验

Kant 的 a priori（空间、时间、因果）在神经层面部分被验证：

| Kant 先验 | 神经硬件 |
|---|---|
| 空间 | 视觉皮层拓扑映射、海马体 place/grid cells |
| 时间 | 海马体 time cells、小脑时序编码 |
| 因果 | 基底核 contingency tracking、前额叶预测模型 |
| 量 | 顶叶 approximate number system（婴儿即有） |

这些结构是物种共享的硬件，不需要文化传递。

**Rosch 的 basic-level categories**：人类命名有特权层次——说 "chair" 而非 "furniture"（太抽象）或 "kitchen chair with armrests"（太具体）。Basic level 是**信息增益与认知能耗的最优折中**，由大脑的有限代谢预算约束。Furnas 中命中率最高的词可能恰好位于 basic level。

**Lakoff & Johnson 的 embodied cognition**：概念隐喻根植于身体经验——"上=多/好"（直立行走）、"容器"（皮肤分内外）、"路径"（运动经验）。所有人类共享类似身体，部分概念结构跨文化普适。

### 第三层：自由能原理——最深层统一（Friston）

> 大脑是预测机器，持续最小化预测误差（自由能）。面对同一客观对象，所有人类大脑在做同一件事——用最小能耗建立生成模型。

若客观世界有结构（物理定律、因果、时空拓扑），且所有人类大脑用相似硬件做相似压缩，则压缩结果必然部分重叠。

Zipf 分布的完整形状：
- **头部**：脑结构 × 客观结构的交集（最小能耗路径，basic level，Kantian 先验 + 世界本身的 salient features）
- **中部**：文化/语言/领域经验的共享（Quine 式共同信念网核心）
- **长尾**：个人信念网的独特路径（个体经验、联想、隐喻偏好）

## Naturalized Pros Hen——一个综合假说

Aristotle：pros hen 结构是存在本身的结构。Kant：范畴是心灵的结构。Quine：两者的耦合是实用主义优化。

**自由能原理暗示第三种可能**：pros hen 结构既不纯粹在世界中，也不纯粹在心灵中，而是**世界结构与大脑结构的最优耦合产物**。

Substance 之所以是 pros hen 核心义，可能因为：识别稳定的独立实体是预测能耗最低的策略——substance 提供不变量，只需编码 accident 的变化，比每帧重编码整个感觉场高效得多。

> **十范畴不是任意分类，也不是纯先验——它们可能是在这个特定物理世界中、用这种特定碳基大脑做预测时、能耗最优的表征结构。**

换一种物理世界（纯流体宇宙，无稳定物体）或换一种大脑（分布式而非层级式），pros hen 结构可能就不成立。

## 可检验的预测

如果"脑结构先验"假说成立：

> 跨语言、跨文化的 Furnas 式实验中，basic-level 命名的一致率应显著高于 domain-specific 命名——即使翻译后比较。

Rosch 的跨文化研究（Dani 人颜色命名）指向这个方向，但尚未有人用 Furnas 的 repeat rate 方法做系统跨文化验证。

## Furnas 数据的贝叶斯重新解读

Furnas 的 frequency-weighted unlimited aliasing = 用**人群先验分布**做贝叶斯推理。若先验部分来自脑结构（而非仅文化），则：
- 跨文化迁移应部分成立（头部词汇在翻译后仍有效）
- 系统的频率排序不只是统计技巧，而是在利用人类共享的认知架构

## 关联知识点

- [[being-qua-being]]：pros hen 结构——"存在"以多种方式被言说
- [[categories]]：十范畴 = 命名的不同入口
- [[substance-and-accident]]：命名走 accident 路径，无法直接触及 substance
- [[quine-two-dogmas]]：信念之网 × ontological commitment = 词汇变异的根源
- [[definition-of-ontology]]：Guarino 的 ontological commitment 在个体层面
- [[pirsig-quality-third-ontology]]：Quality 作为第三种本体论可能与 basic-level salience 有关

## 开放问题

1. Rosch 的 basic-level 是否就是 Aristotle 的 secondary substance（种/属）的认知对应物？
2. 如果范畴是能耗最优的接口，那不同物种（如鸟类、章鱼）是否有完全不同的"范畴表"？
3. LLM 的 embedding space 中是否能观察到类似的 basic-level 收敛？——如果能，是因为训练数据反映了人类认知结构，还是因为 transformer 架构独立发现了相似的压缩最优解？
