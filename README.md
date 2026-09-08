# Codex Skills

可复用的 Codex Skills 集合，面向 AI 产品研究、产品决策和后续扩展场景。

Reusable Codex skills for AI product research, product decisions, and future workflows.

## Skills

| Skill | 作用 |
| --- | --- |
| [ai-product-competitor-research](skills/ai-product-competitor-research/) | 结合当前项目，把 AI 竞品证据转成产品、架构、商业模式和验证决策 |

## 安装

安装单个 Skill：

```bash
git clone https://github.com/shaqiansi-maker/codex-skills.git
cp -R codex-skills/skills/ai-product-competitor-research ~/.codex/skills/
```

重新启动 Codex 或开启新会话后，可以显式调用：

```text
使用 $ai-product-competitor-research，结合当前项目分析这些竞品……
```

每个 Skill 的输入要求和使用示例见对应目录中的 `USAGE.md`。

## 目录约定

```text
skills/
  <skill-name>/
    SKILL.md
    agents/openai.yaml
    references/
```

Skill 目录名应与 `SKILL.md` 中的 `name` 保持一致。

## License

[MIT](LICENSE)
