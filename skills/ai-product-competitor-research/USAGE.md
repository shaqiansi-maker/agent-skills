# AI 产品竞品研究 Skill 跨平台使用说明

这个 Skill 用来分析一个或多个 AI 竞品，并结合你正在构建或迭代的项目，判断：哪些能力值得现在做、哪些要先验证、哪些以后再做、哪些不应该跟进。

它适合产品经理、创业者、产品架构师和负责 AI 产品迭代的人。它不会只给出功能清单，还会分析用户重叠、竞争威胁、商业模式、架构影响、证据强弱和验证方式。

## 最简单的使用方式

你只需要提供：

1. 当前项目的一句话介绍；
2. 项目现在处于什么阶段；
3. 要分析的竞品名称、链接、截图或文档；
4. 这次希望支持什么决策。

通用示例：

```text
请使用 ai-product-competitor-research Skill。
我们的项目是一个帮助个人创作者把知识做成可销售产品的 AI 工作台，目前在做 MVP。
请分析 A、B、C 三个竞品，重点支持“下一版应该先做任务系统还是多 Agent 团队”的决策。
```

如果当前 Agent 能访问项目，它会先自行阅读定位、现有能力、版本边界和相关文档，通常不需要你填写完整材料。如果无法访问，它只会询问会改变结论的必要信息。

## 关于截图

不需要默认准备截图。Skill 会先尝试公开链接和官方资料。

遇到登录后台、不可访问页面或公开信息无法证明关键能力时，它会明确告诉你：是否必须截图、要截哪些页面、每张图用于判断什么。如果你决定不补截图，它仍可继续分析，但会降低相关结论的证据等级。

## 你会得到什么

结果通常包括项目上下文、竞品分类、能力与用户对比、证据链、统一评分、产品和架构影响，以及五类明确行动：立即做、先验证、以后做、坚决不做、继续观察。

也可以要求输出“快速判断”“完整报告”或“管理层决策摘要”。

## 运行条件

为了得到完整结果，Agent 最好具备：

1. 读取目标项目文档或接收项目说明的能力；
2. 访问竞品网页，或理解用户提供的截图、录屏和文档的能力；
3. 在用户要求沉淀报告时写入目标目录的能力。

缺少其中一项并不会让 Skill 失效。它会改用最低必要提问、用户补证或对话内交付，并降低相关结论的证据等级。

## 文件结构

```text
ai-product-competitor-research/
├── SKILL.md
├── references/
│   ├── intake-and-evidence.md
│   ├── report-templates.md
│   └── scoring-and-decisions.md
├── agents/
│   └── openai.yaml
└── USAGE.md
```

`SKILL.md` 和 `references/` 是跨平台核心。`agents/openai.yaml` 只是 Codex/OpenAI 界面使用的可选元数据；其他平台可以忽略，不影响研究方法。

## 安装到原生支持 Agent Skills 的平台

分享时发送整个文件夹或仓库中的 Skill 子目录，不要只发送 `SKILL.md`，否则会丢失输入、证据、评分和报告模板。

### Codex

放入个人 Skill 目录：

```text
~/.codex/skills/ai-product-competitor-research/
```

可以自然语言触发，也可以明确写：

```text
使用 $ai-product-competitor-research，结合当前项目分析这些竞品……
```

### Kiro

个人范围放入：

```text
~/.kiro/skills/ai-product-competitor-research/
```

项目范围放入：

```text
<project>/.kiro/skills/ai-product-competitor-research/
```

Kiro 可以根据描述自动启用，也可以使用 `/ai-product-competitor-research` 明确调用。若使用不继承默认 Skills 的自定义 Agent，需要把该 Skill 加入 Agent 的 resources。具体能力和导入方式见 [Kiro Agent Skills 官方文档](https://kiro.dev/docs/skills/)。

### 其他兼容平台

将整个文件夹放入该平台声明的个人或项目级 Skills 目录。不同平台的安装路径和显式调用语法可能不同，但不应修改核心 `SKILL.md`；优先在平台配置层处理发现和调用。

## 不原生支持 Agent Skills 的平台

仍然可以使用：

1. 把 `SKILL.md` 作为自定义 Agent 或系统提示词；
2. 让 Agent 能够读取 `references/` 中的三个文件；
3. 提示 Agent 只在竞品研究任务中加载这些规则；
4. 用上面的通用示例发起任务。

这种方式可以复用研究方法，但自动触发、按需加载参考文件和工具权限由目标平台自己负责。
