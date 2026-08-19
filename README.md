最后修改日期:260819，总第八次修改
为了在各个不同的 agent 下都能使用统一的上下文文件，创建此仓库，作为各个不同的 agent 上下文规则的唯一事实源。修改一律通过本仓库提交。

## opencode 适配
1. context.md → ~/.config/opencode/AGENTS.md（opencode系统级上下文文件）
2. opencode.json 的 instructions 加入 opencode.md 远程地址：
   "instructions": ["https://raw.githubusercontent.com/techsir-ai/context-rules/main/opencode.md"]
   无代理环境用 CDN 前缀拼接，如 https://gh-proxy.com/https://raw.githubusercontent.com/techsir-ai/context-rules/main/opencode.md

## deepseek harness 适配
1. context.md → ~/.dsh/AGENTS.md（dsh系统级上下文文件）

## WorkBuddy 适配
1. context.md → ~/.workbuddy/SOUL.md 部署区（WorkBuddy 实际加载的系统级文件是 SOUL.md）
2. 部署规则（SOUL.md 部署区状态机，执行时不做任何内容判断，只定位分割线）：
   - 分割线 `<!-- context-rules 部署区：以下内容来自云端仓库，更新时整体替换本区；与上方身份区冲突时，以本区为准 -->` 存在 → 分割线以下的全部内容，整体替换为云端 raw 最新 context.md
   - 分割线不存在 → 全文件替换为 [分割线 + 云端 raw 最新 context.md]
3. 分割线之上是 WorkBuddy 身份区（onboarding 生成），部署时不做任何改动
4. 校验：部署区内容 MD5 = 云端 raw context.md MD5；SOUL.md 全文件须小于 10000 字符（WorkBuddy 身份文件硬上限，超限会被截断）
5. WorkBuddy 系统级上下文文件体系（~/.workbuddy/）：SOUL.md（身份内核，本仓库部署目标）、IDENTITY.md（身份记录）、USER.md（用户画像）、MEMORY.md（跨项目记忆）

## Hermes 适配
1. context.md → ~/.hermes/SOUL.md（Hermes系统级上下文文件，始终加载，对应身份+全局规则）
2. Hermes 无系统级 AGENTS.md 概念（AGENTS.md/CLAUDE.md 仅当前工作目录生效），官方明确不建议放 ~/.hermes/AGENTS.md
3. 项目级上下文文件（.hermes.md 沿 git root 向上继承 / AGENTS.md / CLAUDE.md / .cursorrules）与系统级 SOUL.md 并存，系统级规则一律以本仓库 context.md 为唯一事实源

## 更新机制
各 agent 从 context.md「本文件说明」段落读取仓库地址（base url 或 CDN 前缀），自行拉取更新。
