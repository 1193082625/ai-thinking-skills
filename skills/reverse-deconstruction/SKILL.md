---
name: reverse-deconstruction
description: "This skill should be used when the user admires a finished work and wants to learn how to make one themselves by taking it apart. Typical signals include 这个成品很厉害, 想模仿, 想学着做, 拆解一下. It reverse-engineers the work into its components, decisions, and reusable patterns. Do NOT trigger when the user simply wants to understand a concept (use dual-layer-explanation) or verify claims (use fact-checking)."
agent_created: true
---

# 反向拆解

## 用途

当用户看到一个厉害的成品、想模仿学习它时，把成品逐层拆开：还原它的构成、关键决策和可复用套路，让用户能照着做出来。

## 何时使用

当用户表达"这个做得很好""想模仿""想学着做""参考这个""拆解一下"这类意图，且对象是一个具体成品（文章、产品、设计、代码等）时，加载本 skill。

## 方法规则

请先用一句话说明它解决了什么问题，再反向拆解它为什么有效。

重点分析：

1. 它服务谁，目标是什么；
2. 它采用了什么结构或流程；
3. 哪些关键选择拉开了质量差距；
4. 它的完成标准是什么；
5. 哪些规律可以迁移，哪些细节只适合这个案例。

最后请给我：

1. 提炼3到5条可复用规律；
2. 一份可以照着执行的操作清单；
3. 一个最值得先尝试的小练习。

## 使用方式

1. 读取「方法规则」一节，将其中的每条作为拆解的硬性约束。
2. 按规则拆解成品；规则为空时，退化为默认值：先还原整体结构，再逐层拆要素，最后提炼可迁移的做法。
3. 拆解中若遇到用户完全不懂的底层概念，转 `dual-layer-explanation` 补基础。

## 注意事项

- 「方法规则」是唯一需要用户维护的区域；其余章节保持不变即可。
- 拆解要落到"怎么做"，而不只是"它是什么"。
- 不要在输出中复述规则本身，除非用户明确要求。
