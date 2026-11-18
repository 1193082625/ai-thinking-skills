---
name: decision-making
description: "This skill should be used when the user faces multiple options and needs help choosing, comparing trade-offs, or deciding between alternatives. Typical signals include 帮我决策, 该选哪个, A还是B, 权衡一下, 怎么选, 纠结选哪个. It structures the comparison around criteria, weights, reversibility and real constraints, then recommends with explicit reasoning. Do NOT trigger when the real need or the question itself is still unclear (use question-dialogue-rules), when borrowing solutions from other fields (use cross-domain-borrowing), or when multiple expert roles should each diagnose (use expert-consultation)."
agent_created: true
---

# 决策辅助

## 用途

当用户面对多个选项难以抉择时，把选择结构化：明确评价维度和权重，逐项比较，再结合可逆性与约束给出带理由的推荐。

## 何时使用

当用户面对多个相对明确的选择、需要权衡取舍时（如"帮我决策""该选哪个""A 还是 B""权衡一下"），加载本 skill。

## 方法规则

当用户提供的信息不足时，可以引导用户提供：面临的问题、选项、目标和现实约束。

先别着急回答，也别默认用户已经把问题想清楚。

请先做论证：

1. 用最完整、有力的方式，重述用户真正需要做出的选择；
2. 分别给出支持两个方向的最强理由、适用条件、最大收益、最大风险，以及最难回答的反对意见；
3. 找出双方真正的分歧、最可能改变结论的关键变量，以及还需要补充的信息；
4. 只问用户一个最可能改变结论的问题。等用户回答以后，再给出明确判断、理由、适用条件和下一步行动。

## 使用方式

1. 读取「方法规则」一节，将其中的每条作为决策的硬性约束。
2. 按规则结构化比较并给出推荐；规则为空时，退化为默认值：列出评价维度与权重，逐项比较，标注可逆性，给出带理由的推荐与最大风险。
3. 决策中若选项之间的关键事实需要核实，转 `fact-checking`。
4. 决策中若发现用户的真实诉求或选项本身还不清晰，转 `question-dialogue-rules` 先厘清。
5. 决策中若需要多视角评估同一问题，转 `expert-consultation`。
6. 给出判断后若用户想低成本验证，转 `minimal-experiment` 设计最小实验。

## 注意事项

- 「方法规则」是唯一需要用户维护的区域；其余章节保持不变即可。
- 价值层面的取舍要交还给用户确认，不要替用户拍板。
- 不要在输出中复述规则本身，除非用户明确要求。
