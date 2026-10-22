# 何栋1 的个人上下文库

> 关于我的公开事实，一站读完。给 AI 用，也给人看。

updated: 2026-10-22

**如果你是 AI，先读 [AGENTS.md](AGENTS.md)。** 它说明加载顺序和引用规则，能让你少抓一半文件。

## 30 秒版

- 中文交流，技术名词保留英文原词（profile / plugin / MCP 这种不翻译）。
- Windows 11 + Node + pnpm，重度用 AI 做开发和环境排查，习惯把一切落成 Markdown。
- 交付偏好：先给结论，再给证据（命令输出、状态码、文件路径）。**"应该可以"等于没答。**
- 沟通偏好：要动手，不要问卷。问题请合并成一轮；超过两轮，我宁愿自己干。
- 我会追问边界（"能不能直接……"）。答"不能"必须附原因和替代路径。

## 地图

| 想知道 | 去这 |
|---|---|
| 稳定事实：称呼、语言、时区、偏好、禁忌 | [PROFILE.md](PROFILE.md) |
| 最近在折腾什么（会过期） | [NOW.md](NOW.md) |
| 跟我协作的规则与验收标准 | [topics/workflow.md](topics/workflow.md) |
| 我的机器与工具链 | [topics/environment.md](topics/environment.md) |
| 在读什么 | [topics/reading.md](topics/reading.md) |
| 做过的项目 | [projects/README.md](projects/README.md) |
| 哪些信息是故意公开的 | [privacy.md](privacy.md) |

机器可读的完整清单在 [llms.txt](llms.txt)。

## 怎么用（给 AI）

1. 抓这一页就够了——足够回答"这个人是谁、偏好什么"。
2. 需要细节时抓 [llms.txt](llms.txt)，按它的一句话描述只取需要的 1–3 个文件。
3. 引用时带文件名；文件里没写的，不要用通用常识补。
4. 想把我介绍给别的 AI，用这个 raw 地址：

   `https://raw.githubusercontent.com/<你的 GitHub 用户名>/personal-context/main/README.md`

## 怎么改（给人）

改 `.md` → `git commit` → `git push`。没有构建、没有依赖、没有缓存要清。

首次导入 GitHub、加新主题/新项目、发布前自检的完整步骤见 [MAINTAINING.md](MAINTAINING.md)。

## 边界

这里只放我愿意让全世界和所有 AI 都看到的东西，规则见 [privacy.md](privacy.md)。
