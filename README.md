# Agent Skills

可复用的跨平台 Agent Skills 集合。

Reusable, platform-neutral Agent Skills.

## Skills

| Skill | 作用 |
| --- | --- |
| [ai-product-research](ai-product-research/) | 对 AI 产品、竞品或跨产品能力进行证据驱动研究与功能验证，并形成项目决策或通用知识资产 |

## 兼容性

Skill 的跨平台核心使用 `SKILL.md + references/`。平台专属文件只提供可选的发现、界面或调用适配，不改变研究方法。

## 安装

直接下载：[ai-product-research-v2.0.0.zip](dist/ai-product-research-v2.0.0.zip)

或克隆仓库：

```bash
git clone https://github.com/shaqiansi-maker/agent-skills.git
```

Codex：

```bash
cp -R agent-skills/ai-product-research ~/.codex/skills/
```

Kiro：

```bash
cp -R agent-skills/ai-product-research ~/.kiro/skills/
```

其他原生支持 Agent Skills 的平台，将整个 Skill 文件夹放入该平台声明的 Skills 目录。不原生支持的 Agent，可以把 `SKILL.md` 作为自定义指令，并允许它读取 `references/`。

调用示例：

```text
请使用 ai-product-research，研究这些 AI 产品在 MCP、权限和审计上的共同设计，并判断哪些结论可以用于当前项目。
```

Codex 可使用 `$ai-product-research`，Kiro 可使用 `/ai-product-research`。完整说明见 [USAGE.md](ai-product-research/USAGE.md)。

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
