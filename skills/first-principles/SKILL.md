---
name: first-principles
description: "This skill should be used when the user wants to solve a problem or understand something by reasoning up from fundamental truths rather than by analogy or convention. Typical signals include 第一性原理, 从头推导, 拆到最基本, 本质是什么, 回到根本. It breaks a problem down to irreducible facts, then rebuilds the answer from those foundations. Do NOT trigger for verifying a claim (use fact-checking), systematic research of an existing subject (use vertical-horizontal-analysis), or learning a concept from scratch (use dual-layer-explanation)."
agent_created: true
---

# 第一性原理

## 用途

当用户想抛开惯例和类比、从最基本的真理出发重新推导一个问题的答案时，先把问题拆到不可再分的事实，再从这些根基一层层重建结论。

## 何时使用

当用户表达"第一性原理""从头推导""拆到最基本""本质是什么""回到根本"这类意图时，加载本 skill。

## 方法规则

请用第一性原理把它拆回最底层，区分：

1. 已经确认、无法绕开的基本事实；
2. 习惯性接受、却没有验证过的假设；
3. 真正想实现的目标；
4. 现实中的资源与约束。

暂时放下行业惯例和现成方案，只从基本事实、目标和约束出发，重新推到可行路径。



最后请输出：

1. 原方案中只在修补表面的部分；
2. 从基本事实重新推导出的新路径；
3. 这条路径成立的前提；
4. 验证它的第一步。

## 使用方式

1. 读取「方法规则」一节，将其中的每条作为推理的硬性约束。
2. 按规则从根本事实重建答案；规则为空时，退化为默认值：列出基本事实与假设，逐层推导，最后得出与普通做法对照的结论。
3. 推导中若某条"基本事实"需要核实真伪，转 `fact-checking`。
4. 推导中若用户不理解某个基础概念，转 `dual-layer-explanation` 补基础。
5. 若想从历史演化与同类对比的角度系统研究，转 `vertical-horizontal-analysis`。
6. 推导出新路径后若想低成本检验，转 `minimal-experiment` 设计最小实验。

## 注意事项

- 「方法规则」是唯一需要用户维护的区域；其余章节保持不变即可。
- 区分"不可再分的事实"与"未经检验的假设"，后者要显式标出。
- 不要在输出中复述规则本身，除非用户明确要求。
