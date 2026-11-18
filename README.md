# AI 思考工具箱（ai-thinking-skills）

一套让 AI 按你的方式思考的自定义 Skill 集合。

这套 skill 覆盖了一条完整的思考链条：**不懂 → 学会 → 厘清 → 解决 → 选择 → 验证**。每个 skill 都是一份独立的 `SKILL.md`，遵循开放的 Agent Skills 标准，可被 WorkBuddy、Claude Code、Codex 等支持该标准的 AI 工具直接加载。

---

## 这套 skill 解决什么

默认状态下，AI 对每个问题都用同一种方式回答。但真实需求是分场景的：

- 完全不懂一个概念时，你想要大白话 + 精确定义，而不是一上来就甩术语；
- 想记住一个东西时，你想要一个贴切的比喻或小故事；
- 问题本身还说不清时，你希望 AI 先反问、帮你厘清，而不是急着给答案；
- 面对多个选项时，你希望它把权衡结构化，而不是拍脑袋推荐。

这套 skill 就是把这些「我希望 AI 怎么回答」的规则，固化成一个个可被自动触发的能力。

---

## 11 个 skill 一览

### 问诊（1 个）

| Skill | 什么时候触发 | 做什么 |
|---|---|---|
| `question-dialogue-rules` | 「澄清一下」「讨论一下」、问题模糊需先厘清 | 按自定义对话规则逐步拆解、重构问题，确认后再作答 |

### 学习（5 个）

| Skill | 什么时候触发 | 做什么 |
|---|---|---|
| `dual-layer-explanation` | 「什么是」「讲一下」，对概念完全不懂 | 先用大白话建立直觉，再给严谨定义 |
| `fable-learning` | 「想轻松理解」「记住」「打个比方」 | 用贴切的比喻或小故事承载概念本质 |
| `reverse-deconstruction` | 看到一个厉害的成品、想模仿 | 拆开构成、关键决策与可复用套路 |
| `vertical-horizontal-analysis` | 想深度、系统研究某个东西 | 纵轴看演化、横轴看竞品对比 |
| `fact-checking` | 「这个说法是真的吗」 | 拆出可验证主张、核对证据、给置信度 |

### 解决问题（3 个）

| Skill | 什么时候触发 | 做什么 |
|---|---|---|
| `expert-consultation` | 复杂问题、需要多方视角 | 召集多个虚拟专家独立诊断、交叉质疑后综合 |
| `first-principles` | 想抛开惯例、从根本重推 | 拆到不可再分的事实，再层层重建结论 |
| `cross-domain-borrowing` | 想扩展视角、借别的领域的解法 | 剥掉行业术语、找结构同构，迁移成熟解法 |

### 决策与验证（2 个）

| Skill | 什么时候触发 | 做什么 |
|---|---|---|
| `decision-making` | 「该选哪个」「A 还是 B」 | 明确维度与权重、逐项比较、给带理由的推荐 |
| `minimal-experiment` | 「怎么低成本试一下」「别空想」 | 把想法转成可逆的小行动：假设、判定标准、成本上限 |

---

## 安装

Skill 的本质就是一个文件夹，里面放一份 `SKILL.md`。把 `skills/` 目录下你需要的文件夹，整个复制到对应工具读取 skill 的目录即可。

| 工具 | 目标目录 |
|---|---|
| WorkBuddy（用户级，全项目生效） | `~/.workbuddy/skills/` |
| WorkBuddy（项目级） | `<项目>/.workbuddy/skills/` |
| Claude Code | `~/.claude/skills/` |
| Codex | `~/.agents/skills/` |

复制单个 skill 的命令示例：

```bash
cp -r skills/decision-making ~/.workbuddy/skills/
```

重启对应工具后即可生效。

---

## 设计要点

几个在实践中沉淀下来的经验，供你改造时参考：

1. **`description` 是灵魂。** AI 判断要不要加载某个 skill，只看 `name` + `description`，正文要等加载后才读得到。所以触发意图必须写进 `description`，而不是正文的「何时使用」。
2. **用 `Do NOT trigger` 划边界。** 当两个 skill 语义接近时（比如「扩展视角」和「多专家视角」），在各自的 `description` 里写明何时让位给对方，避免抢触发。
3. **规则区留空，先跑再补。** 每个 skill 都预留了「方法规则」区，注释里有格式示例。建议先写最关键的 2～3 条，用起来再迭代——规则越具体，AI 执行越稳，但规则越少越不容易互相打架。
4. **skill 之间可以接力。** 每个 skill 的「使用方式」里都预置了跳转：遇到不懂的概念转 `dual-layer-explanation`，需要核实转 `fact-checking`，给出判断后想验证转 `minimal-experiment`。当前被触发的 skill 是主流程，转出去的只负责补一段。

---

## 自定义

Fork 本仓库后，直接编辑任意 `SKILL.md` 的「方法规则」一节即可。你可以：

- 增删规则条目，调整成自己偏好的回答风格；
- 修改 `description` 里的触发词，让它在你的高频场景下命中；
- 复制某个文件夹，改个名字，造一个全新的 skill。

---

## License

[MIT](./LICENSE) —— 自由使用、修改、分发，只需保留原始版权声明。
