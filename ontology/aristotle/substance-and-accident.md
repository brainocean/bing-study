---
title: "Substance & Accident（实体与偶性）"
domain: ontology
topic: Aristotle 本体论
source: "Aristotle, Metaphysics VII (Z)"
page: "1028a-1041b"

prerequisites:
  - "[[categories]]"
  - "[[definition-of-ontology]]"
related:
  - "[[being-qua-being]]"
  - "[[hylomorphism]]"
  - "[[ontology-philosophical-vs-engineering]]"
  - "[[ddd-vs-ontology-engineering]]"

last_review: 2026-09-06
next_review: 2026-09-07
interval_days: 1
ease_factor: 2.5
mastery: 0.4
correct_streak: 0

error_log: []

anki_cards:
  - anki_note_id: null
    type: basic
    front: "Aristotle 的 ousia（οὐσία）有哪四层含义？"
    back: "1. 个体（τόδε τι, this something）；2. 本质（τὸ τί ἦν εἶναι, essence）；3. 种属（genus/species）；4. 基质（ὑποκείμενον, substratum）。Categories 中 primary substance = 层次1，secondary = 层次3。Metaphysics 的核心争论在层次2（essence）和层次4（substratum）之间。"
    tags: [ontology, aristotle, substance, ousia]
  - anki_note_id: null
    type: basic
    front: "Aristotle 为什么否决了'substance = bare substratum'？"
    back: "剥离一切属性后剩下的是一个没有任何属性的纯'钩子'——不可认识、不可指称、无法与其他基质区分。一个什么都不是的东西不能作为存在的根基。所以 Aristotle 转向 essence 作为 substance 的核心。"
    tags: [ontology, aristotle, substance, substratum, bare-particular]
  - anki_note_id: null
    type: basic
    front: "Proper accident 和 contingent accident 的区别是什么？"
    back: "Proper accident 从本质必然推出但不构成本质（如：人能使用工具，从理性推出）；contingent accident 与本质无必然关联、可变（如：苏格拉底坐着）。判断方法：能否从 essence 单独推出该属性。"
    tags: [ontology, aristotle, accident, proper-accident, contingent-accident]
  - anki_note_id: null
    type: cloze
    text: "Aristotle 认为 substance 的核心是{{c1::essence（本质, τὸ τί ἦν εἶναι）}}——使一个事物成为其所是的结构性原则，而非{{c2::bare substratum（纯基质）}}。"
    tags: [ontology, aristotle, substance, essence]
  - anki_note_id: null
    type: basic
    front: "Bundle theory 主张'个体只是属性的集合'。Aristotle 式的反驳是什么？"
    back: "两个论证：1）属性可逐一剥离但个体同一性不变，说明同一性不由属性集合构成；2）某些属性总是共现（如理性+哺乳+直立行走），bundle theory 无法解释这种共现规律——essence 作为统一原则解释了属性之间的必然关联。"
    tags: [ontology, aristotle, essence, bundle-theory, steel-man]
  - anki_note_id: null
    type: cloze
    text: "Ousia 四层：个体(τόδε τι) → {{c1::本质(τὸ τί ἦν εἶναι)}} → 种属(genus/species) → {{c2::基质(ὑποκείμενον)}}"
    tags: [ontology, aristotle, ousia]

anki_mastery_boost: 0

created: 2026-09-06
modified: 2026-09-06
tags:
  - aristotle
  - substance
  - accident
  - essence
  - substratum
  - metaphysics-z
---

# Substance & Accident（实体与偶性）

## 核心主张

Metaphysics Z 追问 Categories 未回答的问题：substance 本身是什么？不是它在范畴体系中的功能角色，而是它的内在本质。

Aristotle 的答案：**substance 的核心是 essence（τὸ τί ἦν εἶναι）——使一个事物成为其所是的结构性原则。**

## Ousia 的四层含义

| 层次 | 含义 | 类比 |
|---|---|---|
| 1. 个体（τόδε τι） | 这匹马、苏格拉底 | `new Human()` instance |
| 2. 本质（τὸ τί ἦν εἶναι） | 使人成为人的那个东西 | class invariant / contract |
| 3. 种属（genus/species） | "人"、"动物" | `class Human extends Animal` |
| 4. 基质（ὑποκείμενον） | 承载一切属性的底层 | bare object reference |

Categories 中 primary substance = 层次1，secondary = 层次3。Metaphysics 的核心争论在层次2 和 层次4 之间。

## Bare Substratum 路线的否决

逐一剥离所有属性后剩下什么？一个没有任何属性的纯"钩子"——不可认识、不可指称、无法与其他基质区分。Aristotle 认为这不能作为 substance 的答案。

> 佛教走了相反方向：anātman（无我）接受"剥到底什么都没有"的结论，质疑的是"必须有个东西在底下"这个预设本身。

## Essence 作为 Substance 的核心

Essence 回答"X 是什么？"而非"X 有什么特征？"。苏格拉底的 substance 是使他成为人的那个结构（rational soul），不是他的属性列表。

关键：essence 不是属性的集合——它是使属性共现成为统一整体的原则。{理性, 哺乳, 直立行走} 不是碰巧凑在一起，而是被一个统一的 essence 所关联。

## Accident 的两种类型

| 类型 | 定义 | 与 essence 的关系 | 可剥离性 |
|---|---|---|---|
| Proper accident | 从本质必然推出 | 必然关联 | 不可剥离，但不在定义中 |
| Contingent accident | 与本质无必然关联 | 偶然关联 | 可变 |

判断方法：能否从 essence 单独推出该属性？能推出 → proper；推不出 → contingent。

注意粒度：**能力** vs **具体实现**可能分属不同类型。语言能力（从理性推出）是 proper accident；会说普通话（依赖社会环境）是 contingent accident。

## 思想史位置

Aristotle: Categories（功能定义）→ **Metaphysics Z（essence 作为核心）** → Porphyry: genus + species + differentia = essence 的结构化 → Aquinas: transubstantiation → Locke: real vs nominal essence → Kripke: natural kinds 复兴

## 与 Nominalist 立场的对话

**Bundle theory 挑战**："人"只是一组属性的集合，没有独立的 essence。

**Aristotle 式反驳**：
1. 属性可逐一剥离但个体同一性不变 → 同一性不由属性集合构成
2. 属性共现规律（理性+哺乳+直立行走总一起出现）需要统一解释 → essence 提供了这个解释

**Nominalist 回应**：自然选择解释共现（演化压力使特征 co-evolve）——但注意这在功能上等价于给出一个替代性的统一解释原则。

## 关联知识点

- [[categories]]：substance 的功能定义（said of / present in 四格）
- [[being-qua-being]]：存在一门研究"存在之为存在"的学科
- [[hylomorphism]]：essence = form，将 substance/accident 与 form/matter 统一
- [[ddd-vs-ontology-engineering]]：Entity identity / invariant 是 essence 的工程对应物
