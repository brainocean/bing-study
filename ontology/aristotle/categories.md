---
title: "Aristotle's Categories（范畴篇）"
domain: ontology
topic: Aristotle 本体论
source: "Aristotle, Categories"
page: "1a-15b"

prerequisites:
  - "[[definition-of-ontology]]"
  - "[[ontology-philosophical-vs-engineering]]"
related:
  - "[[substance-and-accident]]"
  - "[[being-qua-being]]"
  - "[[open-world-vs-closed-world]]"
  - "[[ddd-vs-ontology-engineering]]"

last_review: 2026-09-04
next_review: 2026-09-05
interval_days: 1
ease_factor: 2.5
mastery: 0.4
correct_streak: 0

error_log:
  - date: 2026-09-04
    type: 表述不精确
    brief: "said of / present in 的方向说反了：应该是'白色 present in 墙'而非'墙 present in 白色'"

anki_cards:
  - anki_note_id: null
    type: basic
    front: "Aristotle 的 Categories 中，primary substance 和 secondary substance 分别指什么？"
    back: "Primary substance 是具体个体（如苏格拉底、这匹马）；secondary substance 是种（species）和属（genus）（如'人'、'动物'）。Primary substance 在本体论上优先——若无个体，种属无从谈起。"
    tags: [ontology, aristotle, categories, substance]
  - anki_note_id: null
    type: basic
    front: "'Said of' 和 'present in' 这两种本体论关系的区别是什么？"
    back: "Said of = 类型归属（'人' said of 苏格拉底），定义可传递；present in = 属性依附（'白色' present in 墙），定义不传递。关键判据：去掉后是否改变实体本质——类型不可剥离，属性可以变化。"
    tags: [ontology, aristotle, categories, said-of, present-in]
  - anki_note_id: null
    type: basic
    front: "Aristotle 的十范畴中，substance 为何享有特殊地位？"
    back: "Substance 是一切谓述和属性的终极承载者——其余九个范畴（quantity, quality, relation 等）都必须依附于 substance 存在，不能独立漂浮。Primary substance 既不 said of 任何东西，也不 present in 任何东西。"
    tags: [ontology, aristotle, categories, substance]
  - anki_note_id: null
    type: cloze
    text: "Aristotle 的 said of / present in 交叉组合中，primary substance 独占{{c1::既不 said of 也不 present in}}的位置，是整个范畴体系的终极承载者。"
    tags: [ontology, aristotle, categories]
  - anki_note_id: null
    type: basic
    front: "Aristotle 关于 universals 的立场与 Plato 有何不同？用 in rebus / ante rem 术语。"
    back: "Plato: universals ante rem（先于事物，独立存在于理念世界）。Aristotle: universals in rebus（在事物之中，种和属是个体内在的真实结构，但不脱离个体独立存在）。Aristotle 翻转了优先关系——个体先于类型。"
    tags: [ontology, aristotle, plato, universals, realism]
  - anki_note_id: null
    type: cloze
    text: "Aristotle 的十范畴：Substance, {{c1::Quantity}}, {{c2::Quality}}, {{c3::Relation}}, Place, Time, Position, Having, Action, Passion"
    tags: [ontology, aristotle, categories]

anki_mastery_boost: 0

created: 2026-09-04
modified: 2026-09-04
tags:
  - aristotle
  - categories
  - substance
  - universals
  - moderate-realism
---

# Aristotle's Categories（范畴篇）

## 核心主张

Aristotle 在 *Categories* 中为"存在的东西"建立分类系统——十个最高层的范畴（categories），所有存在者必属其一。

十范畴：**Substance（οὐσία）**、Quantity（ποσόν）、Quality（ποιόν）、Relation（πρός τι）、Place（ποῦ）、Time（ποτέ）、Position（κεῖσθαι）、Having（ἔχειν）、Action（ποιεῖν）、Passion（πάσχειν）。

Substance 不只是十个之一，而是本体论上优先的——其余九个范畴全部依附于 substance 存在。

## Primary vs Secondary Substance

- **Primary substance（第一实体）**：具体个体——这匹马、苏格拉底。即 instance。
- **Secondary substance（第二实体）**：种（species）和属（genus）——"马"、"动物"。即 class / type。

> "如果第一实体不存在，其他任何东西都不可能存在。"（*Categories* 2b5-6）

这直接反对 Plato：Plato 认为 Form 比个体更真实（类型先于实例），Aristotle 翻转——个体才是首要的。

## Said of vs Present in

两种本体论关系：

- **Said of（谓述于）**：类型归属。"人" said of 苏格拉底 → "人"的定义整个适用于苏格拉底。定义可传递。
- **Present in（存在于）**：属性依附。"白色" present in 墙 → 白色依附于墙而存在，但白色的定义不适用于墙。定义不传递。

交叉组合形成四格：

|  | Said of something | Not said of anything |
|---|---|---|
| **Present in something** | 普遍 accident（如"知识"） | 个别 accident（如"这一抹白"） |
| **Not present in anything** | Secondary substance（"人"） | **Primary substance**（苏格拉底） |

Primary substance 独占右下角：既不谓述于别的东西，也不存在于别的东西之中。

## 重要区分

- **Said of vs Present in 的判据**：去掉后是否改变实体本质？类型（said of）不可剥离——苏格拉底不可能不是人；属性（present in）可以变化——墙可以不白。
- **这个区分就是 substance / accident 的操作化定义**——不是拍脑袋判断重要性，而是用本体论关系精确划界。

## 实例

- "人" said of 苏格拉底 → 类型归属（`instanceof`）
- "白色" present in 墙 → 属性依附（property assignment）
- "动物" said of "人"，"人" said of 苏格拉底 → 定义沿类型链传递（继承）

## 思想史位置

Plato (Forms) → **Aristotle (Categories, ~350 BCE)** → Porphyry (Isagoge, 270 CE: 五谓词) → Boethius (传入拉丁世界) → 中世纪 universals 之争 → Kant (新范畴表，12个，认识论转向)

## 已知争议

- 十范畴是否完备？Aristotle 在其他著作中有时只提八个
- "Said of" 和 "present in" 是否穷尽了所有本体论关系？
- Primary substance 的个体化原则（individuation）——为什么**这匹**马和**那匹**马不同？Categories 未回答，需等 Metaphysics 的 hylomorphism

## 关联知识点

- [[substance-and-accident]]：深入 ousia 的两层含义
- [[being-qua-being]]：Metaphysics Γ 的核心问题
- [[ddd-vs-ontology-engineering]]：Entity/Value Object 区分与 substance/accident 的平行
- [[open-world-vs-closed-world]]：知识表示中的不同假设如何影响范畴建模

## 跨立场批判笔记

**唯名论挑战**（学习者自身立场）：Categories 作为建模工具有效，但不必承担本体论包袱——可以做 nominalist 使用 realist 工具。类别是语境相对的属性集合，没有客观的 natural kinds。佛教蕴分析（skandha）提供了平行的消解路径。关键张力：若砍掉 secondary substance 的客观性，primary substance 的同一性条件也随之动摇（Hume, Parfit）。
