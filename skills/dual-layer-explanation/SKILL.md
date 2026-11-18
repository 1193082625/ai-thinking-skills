---
name: dual-layer-explanation
description: "This skill should be used when the user encounters a concept they know nothing about and wants to understand it from scratch. Typical openings include 什么是, 讲一下, 完全不懂, 从零开始. It explains through two layers: a plain-language intuition first, then a precise definition. Do NOT trigger when the user already has basic understanding and wants to remember it easily (use fable-learning), or when discussing an existing question (use question-dialogue-rules)."
agent_created: true
---

# 双层解释法

## 用途

当用户对一个概念完全不了解时，用两层结构讲解：先给一个直觉可懂的大白话版本，再给一个准确严谨的精确版本，让用户既有感觉又有定义。

## 何时使用

当用户以「什么是」「讲一下」「完全不懂」「从零开始」等措辞询问一个他不了解的概念时，加载本 skill。

## 方法规则

请分两层解释：

第一层，小白版。用生活化的语言和一个具体例子，让完全没有基础的人也能听懂。

第二层，专业版。使用准确术语，讲清核心机制、适用边界和常见误解。

最后请整理出：

1. 列出小白说法与专业术语的对应关系；

1. 我最容易理解错的地方；

1. 3个用于检查我是否真正理解的问题

## 使用方式

1. 读取「方法规则」一节，将其中的每条作为讲解的硬性约束。
2. 按规则组织两层解释；规则为空时，退化为默认值：先大白话说清直觉，再给出精确定义。
3. 讲解中若发现用户其实已具备基础、只是想更好记住，转 `fable-learning`。
4. 讲解中若发现话题需要厘清用户真实意图，转 `question-dialogue-rules`。

## 注意事项

- 「方法规则」是唯一需要用户维护的区域；其余章节保持不变即可。
- 不要在输出中复述规则本身，除非用户明确要求。
- 与其它学习 skill 接力时，保留已讲过的内容，不要重复开场。
