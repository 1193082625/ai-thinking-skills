---
name: question-dialogue-rules
description: "This skill should be used when the user opens a question with 澄清一下 (clarify) or 讨论一下 (discuss), or when a question involves ambiguous concepts or needs clarification before a reliable answer can be given. It applies a Socratic diagnostic protocol that asks one question at a time, separates facts from interpretations and value judgments, and reconstructs the real question before answering. Trigger examples: 澄清一下, 讨论一下, 帮我理清这个问题, vague or ambiguous concept. Do NOT trigger for simple factual lookups beginning with 什么是 or 讲一下, which should be answered directly, or for choosing among clear options (use decision-making)."
agent_created: true
---

# 问答对话规则

## 用途

针对需要拆解的问题，按「对话规则」一节的自定义规则逐步厘清、重构，最终给出一个准确、可继续行动的新问题；待用户确认后再给出判断、理由与下一步行动。

## 何时使用

当用户以「澄清一下」「讨论一下」等措辞开启话题，或问题涉及模糊概念、需要先厘清才能回答时，加载本 skill。

对于简单的、用户已经了解的信息查询（例如以「什么是」「讲一下」开头的基础概念询问），优先直接作答，不必启动本问诊流程——除非用户明确要求按规则讨论。

当选项已经明确、用户需要权衡取舍做选择时，转 `decision-making`；本 skill 只负责把不清晰的诉求厘清。

## 对话规则

1.每次只问一个问题，根据我的回答决定下一问，不要提前给我一整套问卷；

2.优先区分我说的是可验证的事实、对事实的解释、价值判断，还是我希望实现的目标；

3.检查关键词是否含糊、我默认了哪些前提、证据来自哪里、有没有相反解释，以及结论成立或不成立分别意味着什么；

4.每次提问前，用一句话说明上一条回答让你更新了什么判断；

5.只问可能改变结论的问题。信息足够时立刻停止，不必凑满6个。

问诊结束后，请整理出：

1.我最开始问的问题；

2.我真正想解决的问题；

3.已经确认的事实；

4.仍未验证的假设；

5.最可能改变结论的关键变量；

6.一个准确、具体、可以继续行动的新问题。

等我确认这个新问题以后，再给出你的判断、理由和下一步行动。

## 使用方式

1. 读取「对话规则」一节。
2. 将其中每条规则作为回答的硬性约束。
3. 生成回答时逐条对照，确保没有遗漏。

## 注意事项

- 「对话规则」是唯一需要用户维护的区域；其余章节保持不变即可。
- 规则之间如有冲突，以更靠前的条目为准，除非用户另有说明。
- 不要在回答中复述这些规则本身，除非用户明确要求。
- 规则 5 中的「6 个」不构成提问轮次上限。问诊轮数完全由「只问可能改变结论的问题」决定；若信息已足够，一轮不问就直接进入整理也可以。结束时的 6 项是固定的产出整理清单，与提问轮数无关。
