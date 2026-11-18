---
name: cross-domain-borrowing
description: "This skill should be used when the user wants to broaden their perspective, borrow experience from other fields, or abstract a problem into a domain-independent structure in order to find a solution. Typical signals include 扩展视角, 统一抽象, 跨领域借解, 借鉴别的行业, 类比其他领域, 有没有现成的解法, 换个领域找答案. It strips away domain jargon, finds structurally similar problems in distant fields, and transfers their proven solutions back. Do NOT trigger for a multi-expert role consultation (use expert-consultation), verifying a claim (use fact-checking), or understanding a concept the user knows nothing about (use dual-layer-explanation)."
agent_created: true
---

# 跨领域借解

## 用途

跨领域借解可以帮助用户看到其他领域里相通的解法，视角会更加扩散一些。

## 何时使用

当用户想扩展视角、从其他领域借鉴经验，或者想把问题统一抽象出来时，加载本 skill。

## 方法规则

如果用户提供信息不足，可以引导用户提供：说明背景、当前做法、现实约束和具体卡点。

请先剥掉行业术语，把它抽象成一个人类在其他领域也可能遇到的问题，并找出：

1. 问题的底层结构；
2. 真正的核心矛盾；
3. 普通解法失效的原因。



然后从历史案例，以及至少3个彼此距离较远的领域中，寻找底层结构相似的问题。

每个案例都要说明：

1. 那个领域遇到了什么问题；
2. 使用了什么解决机制；
3. 与我的问题相似在哪里；
4. 哪些部分可以迁移；
5. 什么条件下会失效。



最后请选出最值得借用的3种机制，把它们翻译成适合我当前处境的解决方案，再推荐一个最值得先试的低成本、可逆实验。

## 使用方式

1. 读取「方法规则」一节，将其中的每条作为借解的硬性约束。
2. 按规则跨领域寻找并迁移解法；规则为空时，退化为默认值：先抽象本问题的核心结构，再找出结构同构的领域及其成熟解法，最后评估迁移的可行性与边界。
3. 借来的解法若涉及用户不熟悉的领域概念，转 `dual-layer-explanation` 补基础。
4. 若借来的说法需要核实真伪，转 `fact-checking`。
5. 若问题本身需要厘清真实诉求，转 `question-dialogue-rules`。
6. 推荐出可迁移的机制后，转 `minimal-experiment` 把最值得试的那条设计成低成本、可逆的最小实验。

## 注意事项

- 「方法规则」是唯一需要用户维护的区域；其余章节保持不变即可。
- 借解要看结构是否同构，不要停留在表面的相似。
- 不要在输出中复述规则本身，除非用户明确要求。
