# context-rules
各 agent 上下文规则的唯一事实源。AGENTS.md / opencode.md 为只读源，修改一律通过本仓库提交。

## opencode 适配
1. AGENTS.md → ~/.config/opencode/AGENTS.md（一次部署，之后按更新机制自行拉取）
2. opencode.json 的 instructions 加入 opencode.md 远程地址：
   "instructions": ["https://raw.githubusercontent.com/techsir-ai/context-rules/main/opencode.md"]
   无代理环境用 CDN 前缀拼接，如 https://gh-proxy.com/https://raw.githubusercontent.com/techsir-ai/context-rules/main/opencode.md

## 其他 agent
待适配。

## 更新机制
各 agent 从 AGENTS.md「context 更新来源」读取仓库地址（base url 或 CDN 前缀），自行拉取更新。
