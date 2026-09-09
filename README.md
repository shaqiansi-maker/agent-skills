# Agent Skills

可复用的跨平台 Agent Skills 集合，面向 AI 产品研究、产品决策和后续扩展场景。

Reusable, platform-neutral Agent Skills for AI product research, product decisions, and future workflows.

## Skills

| Skill | 作用 |
| --- | --- |
| [ai-product-competitor-research](ai-product-competitor-research/) | 结合当前项目，把 AI 竞品证据转成产品、架构、商业模式和验证决策 |

## 兼容性

Skill 的核心遵循 `SKILL.md + references/` 结构，不绑定特定 Agent。平台专属文件只提供可选的发现、界面或调用适配，不改变核心研究方法。

## 安装

直接下载：[ai-product-competitor-research-v1.2.0.zip](dist/ai-product-competitor-research-v1.2.0.zip)

先克隆仓库：

```bash
git clone https://github.com/shaqiansi-maker/agent-skills.git
```

Codex：

```bash
cp -R agent-skills/ai-product-competitor-research ~/.codex/skills/
```

Kiro：

```bash
cp -R agent-skills/ai-product-competitor-research ~/.kiro/skills/
```

其他原生支持 Agent Skills 的平台，将整个 Skill 文件夹放入该平台声明的 Skills 目录。不原生支持的 Agent，可以把 `SKILL.md` 作为自定义指令，并允许它读取 `references/`。

调用示例：

```text
请使用 ai-product-competitor-research Skill，结合当前项目分析这些竞品……
```

Codex 可使用 `$ai-product-competitor-research`，Kiro 可使用 `/ai-product-competitor-research`。每个 Skill 的输入要求和平台说明见对应目录中的 `USAGE.md`。

## 目录约定

```text
agent-skills/
  <skill-name>/
    SKILL.md
    references/
    agents/        # 可选的平台元数据
  dist/            # 可分享的版本化压缩包
```

Skill 目录名应与 `SKILL.md` 中的 `name` 保持一致。

## License

[MIT](LICENSE)
