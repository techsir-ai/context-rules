# dsh-change-log

操作日志，依 context-rules AGENTS.md 规则 5.4 记录每次写执行，以备回滚。

## 260814005:174801
- 指令：修改 README.md，加入 deepseek harness 适配章节，并调整简介措辞。
- 操作：
  - 单文件修改 README.md（备份为 README.md.001）。
  - 删除 README 中「AGENTS.md / opencode.md 为只读源」表述，改为「为了在各个不同的 agent 下都能使用统一的上下文文件，创建此仓库，作为各个不同的 agent 上下文规则的唯一事实源」。
  - opencode 适配第 1 条注明「opencode系统级上下文文件」。
  - 新增「## deepseek harness 适配」章节：AGENTS.md → ~/.dsh/AGENTS.md/AGENTS.md（dsh系统级上下文文件）。
  - 其余章节（其他 agent、更新机制）保持不变。
- 状态：已提交 git。

## 260814006:175128
- 指令：修正 deepseek harness 适配章节路径错误。
- 操作：
  - 单文件修改 README.md：`~/.dsh/AGENTS.md/AGENTS.md` → `~/.dsh/AGENTS.md`（dsh 系统级上下文文件为单文件，不是目录下的文件）。
- 状态：已提交 git。
