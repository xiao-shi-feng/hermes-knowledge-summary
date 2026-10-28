# 📚 knowledge-summary · 知识点总结

> **每次对话结束，给用户一条能带走的收获。**
> Turn every chat into a lesson.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-1.1.0-blue.svg)](https://github.com/xiao-shi-feng/hermes-knowledge-summary)
[![Skill Format](https://img.shields.io/badge/Skill-AGENTSKILLS.io-purple.svg)](https://agentskills.io/specification)

一个让 AI 对话"不白聊"的通用技能：在回复末尾自动补一段 **📚知识点总结** —— 用 1-3 句提炼出这次对话真正有用的东西，复杂内容先配一个"说人话"的生活化类比。

> **注意：本 skill 的输出为中文**（📚知识点总结 / 类比说人话 / 下次…先…）。中文用户开箱即用；其他语言用户可将输出模板自行替换为母语。

**装机即用，无需配置，任何模型都适用。**

---

## 为什么这个模式有效

| 原理 | 说明 |
|---|---|
| 🧠 **近因效应** | 人最容易记住最后看到的内容。结尾的金句 = 最强的记忆锚点 |
| ⏳ **遗忘曲线** | 对话结束几小时后，90% 细节都会被忘掉。总结 = 留住那 10% 真正重要的 |
| 🎯 **行动导向** | 普通总结是"我们聊了什么"，好总结是"你下次可以怎么做" |
| 🗣️ **认知负荷** | 复杂话题先用生活类比破冰，零门槛理解，再讲知识点就不费力 |

> 一句话：**不是让 AI 说得更多，而是让用户记得更牢。**

---

## 效果对比

### 没有这个 skill ❌
> 用户：免费 AI 模型和付费的有什么区别？
>
> AI：免费模型有使用次数限制，付费模型响应更快、上下文更长，还支持更多功能，建议根据实际需求选择。

——聊完就忘，等于没聊。

### 有这个 skill ✅
> 用户：免费 AI 模型和付费的有什么区别？
>
> AI：免费模型有使用次数限制，付费模型响应更快、上下文更长，还支持更多功能，建议根据实际需求选择。
>
> 📚**知识点总结**
> - 类比说人话：免费模型 = 实习生前台 —— 不花钱、能干活，但复杂专业的事别指望它。
> - 免费 AI 适合简单任务；关键、专业任务用付费模型更稳。
> - 下次纠结选哪个：先想清楚任务是"日常杂活"还是"重要工程"，答案自然就有了。

——结束对话时，用户带走了一条真正有用的判断标准。

---

## 前置要求

本 skill 是 **Hermes Agent**（[Nous Research](https://github.com/NousResearch/hermes-agent) 开源的跨模型 AI agent 框架）的通用技能格式，符合 [agentskills.io](https://agentskills.io/specification) 开放标准，也可被其他支持 SKILL.md 格式的 agent 使用。

- **Hermes Agent 官网：** https://hermes-agent.nousresearch.com
- **安装 Hermes：** `curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash`

---

## 快速安装

### Hermes Agent（推荐）

```bash
# 方式一：直接从本仓库安装
hermes skills install https://raw.githubusercontent.com/xiao-shi-feng/hermes-knowledge-summary/main/skills/knowledge-summary/SKILL.md

# 方式二：添加为 skill 源（source），之后随时更新
hermes skills tap add xiao-shi-feng/hermes-knowledge-summary
hermes skills install knowledge-summary
```

### 其他 Agent（OpenCode / Claude Code / Codex / Cursor 等）

把 `skills/knowledge-summary/SKILL.md` 复制到你的 Agent 技能目录即可。

```bash
# OpenCode（项目级技能目录）
mkdir -p .agents/skills/knowledge-summary
cp skills/knowledge-summary/SKILL.md .agents/skills/knowledge-summary/

# OpenCode（用户全局技能目录，跨项目复用）
mkdir -p ~/.agents/skills/knowledge-summary
cp skills/knowledge-summary/SKILL.md ~/.agents/skills/knowledge-summary/

# Claude Code
mkdir -p .claude/skills/knowledge-summary
cp skills/knowledge-summary/SKILL.md .claude/skills/knowledge-summary/

# 或直接复制整个目录
cp -r skills/knowledge-summary .claude/skills/
```

> **精简替代方案（功能有损）：** 如果不支持技能目录，可将核心 5 条规则粘贴到系统提示词里。注意：此方案没有触发机制、没有版本管理，效果不如完整安装。

```
1. 回复结尾加 📚**知识点总结**，1-3 句，绝不超
2. 提炼可复用的规则/洞察，不是复述对话
3. 复杂话题先给生活化类比（零术语、老人能懂）
4. 知识点写成可执行："下次遇到X，先做Y"
5. 宁精勿多：只留最值得带走的 1-3 条
```

---

## 核心规则速览（5 条）

1. **📚 前缀 + 1-3 句**，单条知识点一句话，短胜过全
2. **提炼而非复述**：写"下次…先…"，不写"我们讨论了…"
3. **复杂话题，类比先行**：生活化、零术语、老人能懂
4. **可执行**：每一条都是下次能用的动作
5. **宁缺毋滥**：挑最值得带走的，不堆砌

---

## 项目结构

```
hermes-knowledge-summary/
├── LICENSE                          # MIT License
├── README.md                        # 本文件
└── skills/
    └── knowledge-summary/
        └── SKILL.md                 # 技能本体（规则 + 格式 + 避坑 + 自检清单）
```

---

## 版本更新

* **v1.1.0**
  * 增加多场景示例（技术 / 工作 / 生活）
  * 细化类比自检标准和"不要使用"场景
  * 补充 OpenCode 安装说明
  * 提升 frontmatter 元数据与标签，便于检索
* **v1.0.0**
  * 首个正式版本：📚 知识点总结规则 + 类比标准 + 格式 + 自检清单

---

## 许可

MIT License · 自由使用、修改、分发

Made with ❤️ by [时煜源创科技](https://github.com/xiao-shi-feng)
