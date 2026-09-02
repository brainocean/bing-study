---
title: 'Quine: Two Dogmas of Empiricism'
domain: ontology
topic: 基础概念
source: 'Quine (1951) Two Dogmas of Empiricism, The Philosophical Review 60(1): 20-43'
prerequisites:
- '[[definition-of-ontology]]'
related:
- '[[ontology-philosophical-vs-engineering]]'
- '[[open-world-vs-closed-world]]'
last_review: 2026-08-29
next_review: 2026-08-30
interval_days: 1
ease_factor: 2.5
mastery: 0.3
correct_streak: 0
error_log: []
anki_cards:
  - anki_note_id: null
    type: basic
    front: "Quine 在《Two Dogmas of Empiricism》中攻击的两个教条是什么？"
    back: "1. **分析/综合区分**：有些命题纯靠意义为真（分析），有些靠经验（综合）——Quine 论证这个区分无法给出非循环定义；2. **还原论**：每个有意义的命题都可还原为关于感觉经验的命题——Quine 以整体论反驳之。"
    tags: [ontology, quine, analytic-synthetic, epistemology]
  - anki_note_id: null
    type: basic
    front: "Quine 如何攻击分析/综合区分？核心策略是什么？"
    back: "追问'分析'的定义。'单身汉是未婚男性'靠'同义'成立，但'同义'的每种定义都陷入循环：字典记录用法习惯而非逻辑必然，可互换性预设已知哪些是分析的，语义规则只是踢皮球，验证等价又预设了第二教条。结论：分析与经验命题的区别只是程度性的，非种类性的。"
    tags: [ontology, quine, analytic-synthetic, epistemology]
  - anki_note_id: null
    type: cloze
    text: "Quine 的信念之网（Web of Belief）：{{c1::边缘}}节点直接面对经验，{{c2::核心}}节点（如逻辑/数学）改动代价最大但{{c3::原则上仍可修正}}"
    tags: [ontology, quine, holism, web-of-belief]
  - anki_note_id: null
    type: basic
    front: "Quine 的整体论对 ontological commitment 意味着什么？"
    back: "选择什么 ontology（承认什么存在）和选择什么物理定律是同一种选择——都是为了让整体信念网最融贯、最简洁、最能应对经验。没有'正确的 ontology'等着被发现，只有对当前目的最实用的 ontology，换了目的可以换 ontology。"
    tags: [ontology, quine, ontological-commitment, pragmatism]
  - anki_note_id: null
    type: cloze
    text: "在 Quine 的框架中，选择一种 ontology 和选择{{c1::物理定律}}是同一种选择——都是{{c2::实用主义决策}}"
    tags: [ontology, quine, ontological-commitment, pragmatism]
created: 2026-08-22
modified: 2026-08-22
tags:
- quine
- epistemology
- holism
- pragmatism
- analytic-synthetic
---


# Quine: Two Dogmas of Empiricism (1951)

20 世纪分析哲学最有影响力的论文之一。攻击逻辑实证主义的两根支柱。

## 背景：逻辑实证主义的两根支柱

Quine 之前，维也纳学派认为知识有两种干净划分：

1. **分析/综合区分**：有些命题纯靠意义为真（分析），有些靠经验（综合）
2. **还原论**：每个有意义的命题都可还原为关于感觉经验的命题

## 第一教条：分析/综合区分是虚假的

### 攻击策略：追问"分析"的定义

"单身汉是未婚男性"为什么是分析命题？标准回答：因为"单身汉"和"未婚男性"**同义**。

Quine 问：什么叫"同义"？每一种定义尝试都陷入循环：

| 尝试 | 问题 |
|---|---|
| 字典定义 | 字典只记录用法习惯，不是逻辑必然性来源 |
| 可互换性（salva veritate） | 预设了已知哪些陈述是分析的 → 循环 |
| 语义规则 | "在语言 L 中规定这些是分析的" → 只是把问题踢皮球 |
| 验证等价 | 预设命题能被单独验证 → 恰好是第二教条 |

**结论**：没有人能给"分析命题"一个非循环的定义。"2+2=4"和经验命题的区别只是**程度性的**（我们多不愿意放弃它），不是**种类性的**。

### 关键论点

> 连"逻辑数学在内部可证明"本身也依赖于你选择接受哪套逻辑。选经典逻辑还是直觉主义逻辑，本质是**实用主义决策**。

## 第二教条：还原论是虚假的

逻辑实证主义：每个命题可被经验独立验证/否证。

Quine 的反驳 — **整体论（Holism）**：

> "The unit of empirical significance is the whole of science, not individual statements."

单个命题**从不独自面对经验**，总是作为整个理论体系的一部分接受检验。

**例子**：观测到水星轨道异常。否证了什么？
- 牛顿力学？望远镜校准？初始条件测量？"无未知天体"假设？
- 实际历史：先假设有未知行星（发现海王星），后来才接受广义相对论

**推论**：
- 任何命题都可以通过调整体系其他部分而被"拯救"
- 反过来，任何命题在足够压力下都可以被放弃——包括逻辑定律

## Quine 的替代图景：信念之网（Web of Belief）

```
                    ┌─────────────────────────────┐
                    │                             │
                    │     逻辑 / 数学             │ ← 最核心：改动代价最大
                    │         │                   │     但原则上仍可修正
                    │     物理学基本定律          │
                    │         │                   │
                    │     具体科学理论            │
                    │         │                   │
                    │     经验观察陈述            │ ← 边缘：直接面对经验
                    │                             │
经验刺激 ──────────►│  periphery                  │
                    └─────────────────────────────┘
```

**四个关键原则：**
1. **没有命题免于修正** — 包括排中律（量子逻辑放弃了分配律）
2. **没有命题纯粹由经验决定** — 观察总是 theory-laden 的
3. **修正策略是实用主义的** — 倾向最小改动、保持整体融贯
4. **位置差异是程度性的** — 核心命题更稳定只因改动连锁代价大，非特殊认识论地位

## 对 Ontology 的直接影响

Quine 把 ontological commitment 放在信念之网框架内：

> 选择什么 ontology（承认什么东西存在），和选择什么物理定律，是**同一种选择**——都是为了让整体信念网最融贯、最简洁、最能应对经验。

推论：
- 没有"正确的 ontology"等着被发现
- 只有**对当前目的而言最实用的 ontology**
- 换了目的可以换 ontology — 完全合法
- 这为工程 ontology 的实用主义立场提供了哲学辩护

## 个人洞察：能耗最优 × Meme 竞争 × 美学

所谓"最融贯、最简洁、最能应对经验"的信念网络选择，可以从多个角度理解为同一件事：

### 奥卡姆剃刀 / 爱因斯坦"简洁即美"

这些方法论原则本质上是信念网络的**选择压力**：在多个融贯的信念网中，优先选更简洁的那个。

### 物理学/信息论角度

> 如果一个信念网络能以**能耗最低**的方式帮助人类应对客观世界的挑战，它相对其他信念网就具有生存优势。

大脑是有限资源系统。信念网络的"简洁"不只是审美偏好——它直接对应认知负荷（cognitive load）和代谢能耗。更紧凑的模型 = 更少神经元激活 = 更快决策 = 更好生存。

### Meme 竞争角度

信念网络作为 meme（Dawkins），在传播和存活上面临竞争压力：
- 更易理解（低编码成本）→ 更易传播
- 更能应对现实（高预测力）→ 使用者更有竞争力
- 更难被反例击破（鲁棒性）→ 更难被替代

因此"简洁 + 有效"的信念网络在 memetic evolution 中自然胜出。奥卡姆剃刀不是武断的审美，是进化压力的结果。

### 美学外推

> 一些人看起来更美，是因为他们的外貌让大脑消耗更低的能量就能理解和记忆。

这与"processing fluency"理论一致（Reber et al., 2004）：
- 对称性 → 更少计算量就能编码
- 平均面孔 → 更接近 prototype，匹配代价更低
- 流畅处理（fluent processing）产生积极情感 → 被解读为"美"

如果成立，则**真（有效信念）、善（有利生存的行为）、美（低能耗认知）都是同一个选择压力的不同投影**：最小自由能原则（Friston）在不同领域的表现。

## 一句话总结

> 没有纯粹靠意义为真的命题，也没有纯粹靠经验为真的命题。所有知识是一张网，边缘碰经验，核心是逻辑，但整张网的任何节点原则上都可修正。选择保留什么、放弃什么，是实用主义决策——最终可能归结为能耗最优化。

## 关联阅读

- Quine (1948) "On What There Is" — ontological commitment 的定义
- Quine (1960) *Word and Object* — 整体论的系统展开
- Kuhn (1962) *The Structure of Scientific Revolutions* — 范式转换 = 信念网大规模重构
- Friston (2010) "The Free-Energy Principle" — 最小自由能与认知/感知的统一
- Dawkins (1976) *The Selfish Gene* Ch.11 — meme 概念的来源
