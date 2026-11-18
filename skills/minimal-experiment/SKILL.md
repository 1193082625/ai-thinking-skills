---
name: minimal-experiment
description: "This skill should be used when the user wants to test an idea, judgment, or plan cheaply before committing, instead of overthinking. Typical signals include 最小实验, 低成本试一下, 怎么验证, 先试水, 小规模试点, 别空想, 先跑起来. It turns an idea into the smallest reversible action with a clear hypothesis, success or failure criteria, and a cost ceiling. Do NOT trigger for choosing between options (use decision-making), checking whether a claim is true (use fact-checking), or learning a concept (use dual-layer-explanation)."
agent_created: true
---

# 最小实验

## 用途

当用户不想停留在空想、想用最小代价验证一个想法时，把它转成一个可逆的小行动：明确假设、判定标准、成本上限和下一步，让结果能真正说明问题。

## 何时使用

当用户表达"最小实验""低成本试一下""怎么验证""先试水""小规模试点""别空想""先跑起来"这类意图，且目标是用行动检验一个想法时，加载本 skill。

## 方法规则

请先找出这个决定背后最需要验证的3个假设，再选出最可能改变最终结论的那一个。

围绕这个假设，帮用户设计一个低成本、可逆、能在【7天或者用户能接受的周期】内完成的最小实验。

请写清：

1. 具体要做什么；
2. 需要投入多少时间和资源；
3. 观察什么指标；
4. 什么结果支持继续；
5. 什么结果提醒用户停止；
6. 实验结束后能获得什么新信息。

最后告诉用户，明天就能开始的第一个动作是什么。

## 使用方式

1. 读取「方法规则」一节，将其中的每条作为设计实验的硬性约束。
2. 按规则设计最小实验；规则为空时，退化为默认值：明确要验证的假设，设计一个成本最低、可逆的行动，设定成功与失败的判定标准，给出成本上限和决策规则。
3. 设计实验前若用户的想法本身还不清晰，转 `question-dialogue-rules` 先厘清。
4. 若用户其实是在多个选项间选择，转 `decision-making`。
5. 实验中若某个关键事实需要先查证，转 `fact-checking`。

## 注意事项

- 「方法规则」是唯一需要用户维护的区域；其余章节保持不变即可。
- 实验要能产出"假设成立或不成立"的明确信号，避免做了等于没做。
- 不要在输出中复述规则本身，除非用户明确要求。
