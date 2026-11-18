---
name: vertical-horizontal-analysis
description: "This skill should be used when the user wants to study something deeply and systematically. Typical signals include 深度研究, 系统研究, 全面分析, 梳理清楚, 搞透. It analyzes a topic along two axes: vertical depth (layers, mechanisms, root causes) and horizontal breadth (comparisons, related domains, context). Do NOT trigger for a quick concept explanation (use dual-layer-explanation) or checking whether a claim is true (use fact-checking)."
agent_created: true
---

# 横纵分析法

## 用途

当用户想深度、系统地研究某个东西时，沿两个轴展开：纵轴看一个东西怎么走到今天的，横轴看它今天跟一众竞品比到底有啥区别。两条轴交叉起来，才能看见历史上的选择，以及是怎么演化到今天这样的。

## 何时使用

当用户表达"深度研究""系统研究""全面分析""梳理清楚""搞透"这类意图时，加载本 skill。

## 方法规则

请用横纵分析法，对研究对象完成一份可追溯的深度研究。研究截止时间为执行当天。

### 纵向分析：

1. 它在什么背景和需求下诞生，关键推动者是谁；
2. 它经历了哪些重要转折、成功和失败；
3. 哪些早期选择变成了今天的能力、路径依赖或包袱；

### 横向分析：

1. 选择最值得比较的对象，并说明为什么选它们；
2. 用统一维度比较各自的强项、短板和独特性；
3. 解释用户、客户或市场为什么选择它，又为什么放弃他。



把两条轴合起来，继续判断：

1. 过去形成的能力、路径依赖和约束会怎样影响未来；
2. 未来最可能出现哪3条路径；
3. 每条路径出现的前提和预警信号是什么；



请遵守这些证据规则：

1. 优先使用官方资料、原始数据、论文、财报和访谈等一手来源；
2. 重要结论就近标注来源与日期；
3. 事实、推断和观点分开写；
4. 遇到冲突信息时并列呈现，找不到证据时明确写“暂未核实”。



最后按以下顺序输出：核心结论、关键时间线、横向对比表、详细分析、未来判断、仍待确认的问题。

报告需要在 10000 ~ 30000 字之间，语言尽量通俗，不要堆砌资料。

## 使用方式

1. 读取「方法规则」一节，将其中的每条作为研究的硬性约束。
2. 按规则沿纵向与横向两轴展开；规则为空时，退化为默认值：先纵向深挖机制与根因，再横向对比同类与语境。
3. 研究中若遇到用户完全不懂的基础概念，转 `dual-layer-explanation` 补基础。
4. 研究中若需要判断某条资料说法的真伪，转 `fact-checking`。

## 注意事项

- 「方法规则」是唯一需要用户维护的区域；其余章节保持不变即可。
- 纵横两轴要交汇出结论，不要只罗列不收束。
- 不要在输出中复述规则本身，除非用户明确要求。
