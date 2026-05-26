# AI Learning Teacher

AI Learning Teacher 是一个 Codex skill，用来帮助用户快速理解并上手新的 AI 工具、Agent、插件、模型、MCP、自动化工具或开源项目。

它不写传统教程，也不要求用户先记住大量概念。它会把一个新工具拆成 1-3 个可以马上尝试的小任务，让用户通过真实操作理解这个工具能做什么、适不适合自己、第一步怎么用，以及怎么判断结果是否可用。

## 适合什么场景

- 想知道一个 AI 工具到底是做什么的
- 想判断一个工具值不值得现在学习
- 已经安装了某个工具，但不知道下一步怎么开始
- 看到了一个 GitHub AI 项目，但不知道它能不能解决自己的问题
- 想让 AI 用普通话解释工具能力、限制、风险和使用门槛
- 想获得可以直接复制的提问话术和小任务练习
- 想把一次上手经验沉淀成下次可复用的方法

## 它会输出什么

这个 skill 会生成一份快速上手方案，通常包括：

- 一句话结论
- 工具的通俗解释
- 能力边界表
- 是否值得现在学习
- 1-3 个小任务例子
- 可以直接复制给目标工具的提示词
- 入门完成标准
- 一张简短的上手卡

## 安装方式

这个仓库的根目录是项目说明，真正的 skill 在 `ai-learning-teacher/` 子目录下。

在 Codex 中，可以让 skill-installer 安装这个路径：

```text
使用 $skill-installer 安装 https://github.com/Cc-kris/AI-learning-teacher/tree/main/ai-learning-teacher
```

也可以手动安装：

```powershell
git clone https://github.com/Cc-kris/AI-learning-teacher.git
cd AI-learning-teacher
$dest = "$env:USERPROFILE\.codex\skills\ai-learning-teacher"
if (Test-Path $dest) { Remove-Item -Recurse -Force $dest }
Copy-Item -Recurse .\ai-learning-teacher $dest
```

安装后重启 Codex，让新 skill 生效。

## 使用方式

重启 Codex 后，直接用 `$ai-learning-teacher` 触发。

示例：

```text
使用 $ai-learning-teacher，帮我快速上手 Claude Code。
```

```text
使用 $ai-learning-teacher，帮我判断 Dify 是否值得我现在学，以及第一步应该怎么用。
```

```text
使用 $ai-learning-teacher，帮我看懂这个 GitHub AI 项目适合做什么：https://github.com/example/project
```

## 使用效果示例

你可以期待它把问题拆成这样的结构：

```text
1. 先说结论
2. 它到底是什么
3. 它能帮你做哪些事
4. 是否值得你现在学
5. 先做这几个小例子
6. 你可以直接问它的问题
7. 怎么判断你已经入门
8. 上手卡
```

## 项目结构

```text
.
+-- README.md
`-- ai-learning-teacher/
    +-- SKILL.md
    `-- agents/
        `-- openai.yaml
```

## 说明

- 不包含密钥、账号或私有配置。
- 不依赖特定操作系统。
- 不绑定某一个 AI 工具，可以用于 Codex、Claude Code、Dify、n8n、MCP、模型类工具等不同对象。
- 这个 skill 的目标是帮用户开始使用工具，而不是替代官方文档。
