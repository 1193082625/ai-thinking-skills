---
name: fact-checking
description: "This skill should be used when the user wants to verify whether a claim in a document or statement is true. Typical signals include 是不是真的, 核实一下, 查证, 有没有依据, 事实核查. It separates verifiable claims from opinions, checks sources and evidence, and reports a verdict with confidence. Do NOT trigger for learning a new concept (use dual-layer-explanation) or open discussion (use question-dialogue-rules)."
agent_created: true
---

# 事实核查

## 用途

当用户想知道某份资料或某个说法到底是不是真的时，把其中的可验证主张逐条挑出，核对来源与证据，给出带置信度的结论。

## 何时使用

当用户表达"是不是真的""核实一下""查证""有没有依据""事实核查"这类意图时，加载本 skill。

## 方法规则

请先把要核查的东西拆成：

1. 可以被外部验证的事实；
2. 从事实推出的结论；
3. 其中包含的价值判断；



对于事实部分，请联网核查来源、样本、时间和完整上下文，并标记为：

1. 已证实；
2. 基本成立，但需要收窄；
3. 存在争议；
4. 证据不足；
5. 明显错误。



在假设相关事实成立的情况下，继续检查：

1. 这些事实能否推出当前结论；
2. 是否藏着未经验证的假设；
3. 是否混淆相关性和因果关系；
4. 是否遗漏了其他解释或关键信息；
5. 结论在什么条件下成立或失败；



最后请输出：

1. 哪些事实可信，哪些需要修正；

2. 推理链中最关键的漏洞；

3. 补强后的最合理版本；

4. 我目前可以相信到什么程度。

## 使用方式

1. 读取「方法规则」一节，将其中的每条作为核查的硬性约束。
2. 按规则核查；规则为空时，退化为默认值：区分事实主张与观点，逐条核对来源与证据，标注结论与置信度。
3. 核查中若遇到用户完全不懂的概念，转 `dual-layer-explanation` 补基础后再判断。

## 注意事项

- 「方法规则」是唯一需要用户维护的区域；其余章节保持不变即可。
- 区分"缺乏证据"与"证据表明为假"，不要混为一谈。
- 不要在输出中复述规则本身，除非用户明确要求。
