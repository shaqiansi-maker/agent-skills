# AI 产品与竞品分析 Skill

面向正在构建、选型或迭代 AI 产品的团队，对单个产品、多个竞品或某项共有能力进行证据驱动研究与功能验证，并形成可用于产品、架构和采购决策的结论。

它不是只整理官网功能列表的调研模板。能实测时，Skill 会在用户授权范围内建立测试任务、记录调用和失败结果；不能实测时，会明确证据上限，不把宣传材料或推断写成已验证事实。

## 适合研究什么

### 单个 AI 产品深度分析

分析产品定位、用户、工作流、Agent 能力、技术架构、权限与数据边界、商业模式、成熟度和未来演进。

```text
请使用 ai-product-research，分析 Carrier 的产品定位、能力构成和后续演进，并验证它的 MCP 能力。
```

### 多个 AI 产品竞品分析

围绕明确的决策问题比较竞品，不默认堆砌完整功能矩阵。可以结合正在建设的项目，判断哪些能力值得采用、验证、观察或明确不做。

```text
请使用 ai-product-research，比较 Atoms、Tycoon 和 VentureCity，并判断它们对当前 AI 创业产品的威胁与启发。
```

### 跨产品能力专题研究

当用户只关心多个产品共有的一项能力时，只研究该能力，例如 Agent 编排、记忆、MCP、权限、审计、支付或商业化。

```text
请使用 ai-product-research，研究 Carrier、Dify 和扣子在 MCP、权限和审计方面的共同设计与差异，不需要完整竞品分析。
```

## 它会怎么工作

1. 识别用户要做的是产品深度分析、竞品比较还是能力专题研究。
2. 明确本次研究要支持的决策，以及什么情况不再继续扩大范围。
3. 有目标项目时读取项目定位、阶段、现有能力和约束；没有项目时沉淀通用能力模型。
4. 收集官网、文档、案例、界面、API、MCP 和实测结果，区分事实、推断、建议与待验证假设；必要时保留能直接佐证结论的关键截图。
5. 公开资料不足时，判断是否需要用户补充指定截图、登录观察或测试授权。
6. 获得授权后，由 Agent 优先自行设计和执行可复现测试；只有登录、验证码、业务判断和外部副作用授权需要用户介入。
7. 先给简单直接的决策摘要，再按研究问题提供最低充分的截图、关系图、流程图、时序图、边界图和证据；没有决策价值的内容不进入正文。

## 最终可以得到什么

- 一页式直接结论；
- 产品定位、用户和核心闭环分析；
- 竞品矩阵或能力专题对比；
- 能力架构、业务流程、Agent 控制流、时序、状态、对象关系或信任边界图；
- 功能实测记录、失败结果和证据边界；
- 必要的官网、后台或测试截图，并标注它支持和不能支持的结论；
- 产品、架构、安全、商业化与成熟度判断；
- 结合项目形成的 `do_now / test_first / do_later / do_not_do / observe` 建议；
- 没有目标项目时可复用的能力模型、测试方法和采用条件；
- 尚未验证的问题与下一步取证计划。

详细使用方式见 [USAGE.md](USAGE.md)，Skill 主入口见 [SKILL.md](SKILL.md)。

## 安装

### 下载 ZIP

下载 [ai-product-research-v2.2.2.zip](dist/ai-product-research-v2.2.2.zip)，解压后得到完整的 `ai-product-research` 文件夹。

### 从 GitHub 安装

Codex：

```bash
git clone https://github.com/shaqiansi-maker/ai-product-research.git ~/.codex/skills/ai-product-research
```

Claude Code：

```bash
git clone https://github.com/shaqiansi-maker/ai-product-research.git ~/.claude/skills/ai-product-research
```

Kiro：

```bash
git clone https://github.com/shaqiansi-maker/ai-product-research.git ~/.kiro/skills/ai-product-research
```

其他原生支持 Agent Skills 的平台，将整个仓库放入该平台声明的 Skills 目录。不原生支持 Skills 的 Agent，可以把 `SKILL.md` 作为自定义指令，并允许它按需读取 `references/`。

安装后可直接这样调用：

```text
请使用 ai-product-research，分析这个 AI 产品，并告诉我哪些结论已经得到证据验证。
```

Codex 可以使用 `$ai-product-research`，Kiro 可以使用 `/ai-product-research`；其他平台可直接用自然语言点名该 Skill。

## 兼容性说明

研究方法只维护一份，核心文件是 `SKILL.md` 和 `references/`。`agents/` 只提供可选的平台发现和界面元数据，不复制研究逻辑。

不同 Agent 是否能联网、读取项目、操作浏览器、调用 MCP/API 或写入文件，取决于宿主能力和用户授权。能力不足时，Skill 会降低证据等级并说明缺口，不虚构已经完成的研究或测试。

## 仓库结构

这是一个单 Skill 仓库，不是 Skills 合集。

```text
ai-product-research/
├── README.md
├── SKILL.md
├── USAGE.md
├── agents/          # 可选的平台元数据
├── references/      # 研究、证据、测试和报告方法
├── evals/           # 发布前行为测试，不进入安装包
├── dist/            # 可分享的版本化 ZIP
└── LICENSE
```

## License

[MIT](LICENSE)
