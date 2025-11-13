# Claude Code 中文教程

## 安装 Claude Code

```bash
curl -fsSL https://claude.ai/install.sh | bash # macOS/linux 推荐的方式

brew install --cask claude-code # homebrew

irm https://claude.ai/install.ps1 | iex # Windows 用户 是的，CC 可以在Windows 上稳定运行

npm install -g @anthropic-ai/claude-code # 依赖  Node.js 前端生态的一个运行时环境
```

## 有关 AI 编程

这是一种由 `编辑器` 到 `终端`开发方式的转变。`Agentic Coding` 指的是代理编码。随着基础模型的能力更新、以及 Agentic 能力提升、编辑器/IDE 的产品形态正在被 CLI 挑战，当模型能力足够强的时候，CLI 是最佳的形态吗？答案是：没人知道

## 作者的主观偏见

1. 目前 Codex 和 Claude Code 可以作为主力

2. 终端可以使用 ghostty

3. 一方的产品正在成为主流。我们知道的几家模型厂商 Anthropic 出了 Claude Code、OpenAI 出了 Codex、谷歌出了 Gemini CLI 、Kimi 出了 Kimi CLI 、阿里出了 Qwen Code

## Opus vs Sonnet vs Haiku

- Opus (杰作/巨著) 在拉丁语中，“Opus” 意为“作品”，尤指重要的、大规模的艺术或音乐创作，常用来指代大师的“杰作”或“巨著”。

- Sonnet (十四行诗) Sonnet” 是一种结构严谨的抒情诗体，通常有 14 行 常用于表达爱情、美感或哲理。

- Haiku (俳句) “Haiku” 是一种日本古典短诗，通常由三句十七音组成（按 5-7-5 的音节排列）。

## Claude Code 下载的趋势

Claude Code 的本质是一个 npm 的包。如果你对趋势感兴趣可以在下述网站查阅安装趋势

- https://npmjs.com/package/@anthropic-ai/claude-code?activeTab=versions
- https://npmtrends.com/@anthropic-ai/claude-code
- https://npm-stat.com/charts.html?package=%40anthropic-ai%2Fclaude-code&from=2025-02-23&to=2025-07-05
- https://npmcharts.com/compare/@anthropic-ai/claude-code?interval=1&log=false

## 终端 CLI 更强大

两者底层能力一致，Extension 更适合喜欢图形界面的用户，CLI 更适合终端用户和需要高级功能的场景

在这里我推荐直接在终端中使用

## CC 问自己

Claude 还可以访问其自身的文档，并能回答有关其功能和能力的问题。当对 Claude Code 自身有疑问的时候，可以问，比如：

```sh
Claude Code 你联网是怎么实现的？
```

## 内置 Slash Commands

Claude Code 提供了 **34 个内置命令**，按功能分类如下：

### 📋 会话与账户管理

- `/exit` - 退出 REPL 环境
- `/login` - 切换 Anthropic 账户
- `/logout` - 退出当前账户
- `/help` - 显示帮助信息

### 💬 对话管理

- `/clear` - 清除所有对话历史（开始新任务时清空上下文）
- `/compact [instructions]` - 压缩对话历史（对话过长时精简上下文）
- `/rewind` - 回退对话和/或代码
- `/export [filename]` - 导出对话到文件或剪贴板
- `/memory` - 编辑 CLAUDE.md 记忆文件（设置持久化上下文）

### 🤖 模型与配置

- `/model` - 切换 AI 模型（Sonnet、Opus、Haiku）
- `/config` - 打开设置界面
- `/status` - 显示版本、模型、账户和连接状态
- `/statusline` - 配置状态栏 UI
- `/terminal-setup` - 安装 Shift+Enter 换行绑定（iTerm2/VSCode）
- `/vim` - 激活 vim 模式

### 🛠️ 开发工具

- `/add-dir` - 扩展工作目录（授予更多目录访问权限）
- `/review` - 请求代码审查
- `/bug` - 提交 bug 报告给 Anthropic
- `/doctor` - 检查安装健康状态

### 📊 监控与分析

- `/context` - 可视化 token 使用情况
- `/cost` - 显示 token 使用统计
- `/usage` - 显示计划限额和速率状态（订阅用户）
- `/todos` - 列出当前任务项

### 🚀 高级功能

- `/agents` - 管理自定义 AI 子代理
- `/bashes` - 列出和管理后台任务
- `/hooks` - 管理工具事件配置
- `/init` - 初始化项目（创建 CLAUDE.md）
- `/mcp` - 管理 MCP 服务器连接
- `/sandbox` - 启用沙箱 bash 工具
- `/permissions` - 配置访问控制
- `/privacy-settings` - 更新隐私配置
- `/pr_comments` - 显示 PR 反馈

### 💡 常用场景推荐

1. **开始新项目**：`/init` → `/memory`
2. **上下文过大**：`/context` → `/compact`
3. **切换任务**：`/clear` 或 `/rewind`
4. **性能监控**：`/cost` → `/usage`
5. **遇到问题**：`/doctor` → `/bug`

## 扩展思考

加强语气的短语，例如"keep hard"（持续努力思考）、"think more"（多思考）、"think a lot"（深入思考）或"think longer"（更长时间地思考），会触发更深层次的思考

## 状态栏配置

只需要： Claude code 你能帮我设置一下 状态行配置 吗？ Status line configuration

## CLAUDE.md

但需要注意：

- 所有 CLAUDE.md 内容会在每次对话时加载到上下文中

- 受 Claude 模型的总 token 限制影响（当前模型约 200K tokens）

- 建议保持精简和相关性，避免填充过多无关信息

- User CLAUDE.md：个人偏好（如语言偏好"使用中文"）

```sh
# 语言偏好

- 请使用中文简体进行所有交流和对话沟通
- 包括：文本回复、代码注释、提交信息、文档说明、规划说明等
- 思考过程可以使用英文以提高效率
- 保持专业、简洁的技术沟通风格

```

## 小技巧

- 从大的问 到小的，从宽泛的问到细节的，从高问到低的

## CC vs Codex

Codex CLI 是 2025 年 4 月 16 日 先发的，然后使用 Rust 重写。

Codex 是 2025 年 5 月 16 日后发的，跑在浏览器中的。

还有一个专码模型 Codex ，这个是 2021 年 08 月 10 日对外发的。当时主要为了驱动微软的 GitHub Copilot。

大家还记得 2025-05-16 OpenAI 发布的 codex-mini-latest 吗？

当时是基于 o4-mini 进行微调，主要面向 Codex CLI 应用。

## CC vs Gemini CLI

在 2025 年 06 月 25 的时候，谷歌发了 Gemini CLI。虽然谷歌这一路走的很飘逸：在 AI 编程的这个产品方向上一会又是在浏览器中的，一会又在终端的，一会又是插件呢，一会又扩展。不过作为 Claude Code 竞品，不发也不行。

因为是终端操作，所以终端记得代理一下，然后代理节点开一下。

安装一下：

```sh
npm install -g @google/gemini-cli

npm install -g @google/gemini-cli@latest

npm install -g @google/gemini-cli@preview

npm install -g @google/gemini-cli@nightly
```

## MCP

1. 文档和知识获取类

- Context7: 获取最新库文档
- Exa: 搜索代码和文档
- Web search/fetch: 获取实时信息

2. 开发工具集成类

- GitHub: 代码托管和协作
- GitLab: 类似 GitHub
- Linear: 项目管理
- Jira: 项目管理

3. 数据库操作类

- PostgreSQL MCP
- SQLite MCP
- MongoDB MCP

4. 浏览器自动化类

- Playwright 和 Puppeteer 提供强大的浏览器交互能力，可以实现自动化测试、网页抓取和交互场景。Chrome DevTools MCP
  则帮助深入调试和性能分析。

5. 云服务集成类

- AWS、Google Drive 和 Slack MCP 实现云端资源管理和协作，极大地扩展了开发工作流程。

6. 本地开发增强类

- Filesystem MCP 扩展文件操作能力
- Memory MCP 提供跨会话记忆
- Sequential thinking MCP 优化思考和推理过程

7. AI 增强类

- Perplexity MCP 提供更智能的搜索
- Claude Desktop prompts 帮助管理和优化提示词
