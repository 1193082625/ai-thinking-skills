---
name: expert-consultation
description: "This skill should be used when the user wants several distinct expert roles to independently diagnose one problem and then have their views cross-examined and synthesized. Typical signals include 专家会诊, 多专家视角, 集思广益, 听听各方意见. It convenes several complementary expert roles, lets each reframe and diagnose the problem from their own discipline, then surfaces consensus and disagreement. Do NOT trigger for borrowing structurally similar solutions from other fields (use cross-domain-borrowing), verifying a claim (use fact-checking), learning a concept (use dual-layer-explanation), or clarifying the question itself (use question-dialogue-rules)."
agent_created: true
---

# 专家会诊

## 用途

当用户面对一个复杂问题、需要多方视角时，召集若干不同领域的虚拟专家各自诊断，再综合他们的判断给出一个立体、可执行的结论。

## 何时使用

当用户表达"专家会诊""多专家视角""集思广益""听听各方意见""从不同角度看"这类意图，且目标是解决一个实际问题时，加载本 skill。

## 方法规则

如果用户信息提供不足时可以引导用户：填写问题、已知事实、目标和现实约束。先不要直接给方案。

请为这个问题选择3种真正互补的专业视角，并说明每种视角为什么必要。



让每种视角分别回答：

1. 它怎样重新定义这个问题；
2. 它最推荐的解决路径；
3. 其他视角最容易忽略的风险；
4. 什么新证据会让它改变判断。



然后让三种视角互相质疑，找出：

1. 共同认可的事实；
2. 真正的分歧；
3. 分歧背后的不同假设。



最后请综合输出：

1. 综合后最推荐的方案；
2. 适用条件；
3. 最大风险；
4. 退出条件；
5. 第一步行动；



不要选择三个高度相似的身份，也不要模仿或编造真实人物的观点。

信息不足时，先只问我一个最关键的问题。

## 使用方式

1. 读取「方法规则」一节，将其中的每条作为会诊的硬性约束。
2. 按规则组织多方会诊；规则为空时，退化为默认值：选定几位互补的专家角色，各自独立诊断，再综合共识与分歧。
3. 会诊中若某位专家的说法需要核实真伪，转 `fact-checking`。
4. 会诊中若用户对自己不熟悉的领域概念不理解，转 `dual-layer-explanation` 补基础。
5. 若问题本身还不清晰、需要先厘清真实诉求，转 `question-dialogue-rules`。

## 注意事项

- 「方法规则」是唯一需要用户维护的区域；其余章节保持不变即可。
- 不同专家之间要真的有视角差异，不要换皮重复同一个观点。
- 不要在输出中复述规则本身，除非用户明确要求。
