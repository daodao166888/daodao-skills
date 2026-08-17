# daodao-skills

> daodao166888 的个人 Agent Skills 工具箱。内容创作 + AI 实战向，沉淀成可以直接用的 Skill。

**支持：Claude Code、Codex、Cursor，以及其他支持 Agent Skills 格式的工具。**

本仓库由 [daodao166888](https://github.com/daodao166888) 维护。目标是把内容创作里反复用到的能力（去 AI 味、选题、拆解、方法论）打包成 skill，随取随用，也把值得收藏的工具和方法论整理成文档。

## 快速开始

```bash
# 安装全部
npx skills add daodao166888/daodao-skills

# 或只装 daodao-deai
npx skills add https://github.com/daodao166888/daodao-skills -s daodao-deai
```

装完直接说：

```text
/daodao-deai 这段太AI了，帮我改得像人话：[粘贴你的文案]
```

## 当前内容

### Skills

| Skill | 作用 | 触发 |
|---|---|---|
| `/daodao-deai` | 去 AI 味：把生硬的 AI 文案改得像人写的，守住事实和原意 | 「去AI味」「降AI味」「改得像人话」 |

### 文档

| 文档 | 内容 |
|---|---|
| [去 AI 味开源工具大全](docs/de-ai-tools/README.md) | GitHub 16 个去 AI 味工具逐一深读：选型表、完整清单、通用方法论、演进脉络、安装速查（2026-08 更新） |

## 目录结构

```
daodao-skills/
├── README.md
├── LICENSE
├── .claude-plugin/          # marketplace 配置
├── docs/
│   └── de-ai-tools/         # 去AI味工具大全
└── skills/
    └── daodao-deai/            # 去AI味 skill
        └── SKILL.md
```

## 路线图

- [x] daodao-deai：去 AI 味 skill（综合 16 个工具方法论）
- [x] 去 AI 味开源工具大全
- [ ] 选题深化 skill（对接 Obsidian 内容工作流）
- [ ] X 推文全流程 skill（选题→写作→去味→标题）
- [ ] 内容拆解 skill

## 关联

- Obsidian 内容库：`D:\DaoDao-IP\`
- X：[daodao166888](https://x.com/daodao166888)
- 方法论来源：[去 AI 味开源工具大全](docs/de-ai-tools/README.md)（从 16 个开源项目的方法论中提炼）

## License

[MIT](LICENSE)
