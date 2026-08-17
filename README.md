# context-rules
为了在各个不同的 agent 下都能使用统一的上下文文件，创建此仓库，作为各个不同的 agent 上下文规则的唯一事实源。修改一律通过本仓库提交。

## opencode 适配
1. context.md → ~/.config/opencode/AGENTS.md（opencode系统级上下文文件）
2. opencode.json 的 instructions 加入 opencode.md 远程地址：
   "instructions": ["https://raw.githubusercontent.com/techsir-ai/context-rules/main/opencode.md"]
   无代理环境用 CDN 前缀拼接，如 https://gh-proxy.com/https://raw.githubusercontent.com/techsir-ai/context-rules/main/opencode.md

## deepseek harness 适配
1. context.md → ~/.dsh/AGENTS.md（dsh系统级上下文文件）

## WorkBuddy 适配
1. context.md → ~/.workbuddy/CODEBUDDY.md（WorkBuddy系统级上下文文件）
2. 或部署到具体项目的 AGENTS.md 作为项目级上下文
3. WorkBuddy 上下文文件体系：
   - 系统级（~/.workbuddy/）：SOUL.md（身份内核）、IDENTITY.md（身份记录）、USER.md（用户画像）、CODEBUDDY.md（全局规则）、MEMORY.md（跨项目记忆）
   - 项目级（{workspace}/）：AGENTS.md（项目规则，自动注入为 project_context）

## 更新机制
各 agent 从 context.md「本文件说明」段落读取仓库地址（base url 或 CDN 前缀），自行拉取更新。
