# Agent Skills

可复用的跨平台 Agent Skills 集合。

Reusable, platform-neutral Agent Skills.

## Skills

| Skill | 作用 |
| --- | --- |
| [ai-product-research](ai-product-research/) | 对 AI 产品、竞品或跨产品能力进行证据驱动研究与功能验证，并形成项目决策或通用知识资产 |

## 兼容性

Skill 的跨平台核心使用 `SKILL.md + references/`。平台专属文件只提供可选的发现、界面或调用适配，不改变研究方法，也不为每个平台维护一份研究逻辑。

是否能联网、读取项目、调用 MCP/API、操作浏览器或写文件，取决于安装它的 Agent 和用户授权。能力不足时，Skill 会降级证据路径，不虚构已经完成的研究或测试。

## 安装

直接下载：[ai-product-research-v2.1.0.zip](dist/ai-product-research-v2.1.0.zip)

或克隆仓库：

```bash
git clone https://github.com/shaqiansi-maker/agent-skills.git
```

Codex：

```bash
cp -R agent-skills/ai-product-research ~/.codex/skills/
```

Claude Code：

```bash
cp -R agent-skills/ai-product-research ~/.claude/skills/
```

Kiro：

```bash
cp -R agent-skills/ai-product-research ~/.kiro/skills/
```

其他原生支持 Agent Skills 的平台，将整个 Skill 文件夹放入该平台声明的 Skills 目录。不原生支持的 Agent，可以把 `SKILL.md` 作为自定义指令，并允许它按需读取 `references/`。平台安装入口变化时以平台当前文档为准，核心 Skill 不随宿主复制分叉。

调用示例：

```text
请使用 ai-product-research，研究这些 AI 产品在 MCP、权限和审计上的共同设计，并判断哪些结论可以用于当前项目。
```

Codex 可使用 `$ai-product-research`，Kiro 可使用 `/ai-product-research`；其他平台可直接用自然语言点名该 Skill。完整说明见 [USAGE.md](ai-product-research/USAGE.md)。

## 目录约定

```text
agent-skills/
  <skill-name>/
    SKILL.md
    references/
    agents/        # 可选的平台元数据
  dist/            # 可分享的版本化压缩包
  evals/           # 发布前行为测试，不进入安装包
```

Skill 目录名应与 `SKILL.md` 中的 `name` 保持一致。

## License

[MIT](LICENSE)
