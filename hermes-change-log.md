# hermes-change-log

操作日志，依 context-rules context.md 规则 5.4 记录每次写执行，以备回滚。

## 260818-003829
- 指令：在 README.md 增加 Hermes 适配段落，并提交。
- 操作：
  - 修改 README.md：第一行更新为总第七次修改。
  - 新增「## Hermes 适配」段落：context.md → ~/.hermes/SOUL.md（Hermes系统级上下文文件，始终加载）；注明 Hermes 无系统级 AGENTS.md 概念（AGENTS.md/CLAUDE.md 仅 cwd 生效）；项目级上下文文件与 SOUL.md 并存，系统级以 context.md 为唯一事实源。
  - 其余章节（其他 agent、更新机制）保持不变。
- 备份：无（目录有 git，按 5.5 使用 git 管理）。
- 状态：已提交 git。

## 260818-004000
- 指令：部署 context.md 到 ~/.hermes/SOUL.md（Hermes系统级上下文文件）。
- 操作：
  - 备份：~/.hermes/SOUL.md → ~/.hermes/SOUL.001.md（目录外文件无 git，按 5.6 文件备份）。
  - 部署：仓库 context.md 覆盖 ~/.hermes/SOUL.md，MD5 校验一致（f52850edcdf6e1dfb911b1a155d57897，75 行）。
  - ~/.hermes/CLAUDE.md（519B，最高规则简版）未改动，保持现状。
- 备份：~/.hermes/SOUL.001.md
- 状态：已部署，待 git 提交。回滚：cp ~/.hermes/SOUL.001.md ~/.hermes/SOUL.md
