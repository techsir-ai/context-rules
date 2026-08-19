# workbuddy 操作日志

| 时间戳 | 操作内容 | 文件 | 备份/产出物 |
|---|---|---|---|
| 260817-235822 | AGENTS.md 末尾追加5项内容（交流风格、信息来源准则、AI推断标注规则、禁止行为、本地知识库），不影响原有章节1-9 | AGENTS.md | 备份: AGENTS.md.002 |
| 260818-000744 | AGENTS.md 备份规则统一：5.5-5.7从单文件/多文件/目录外三分改为统一判断逻辑（有git用git→没git建议→不愿意用xx.001.xx），版本号章节第15-16行同步修改，第一行更新为第十次修改 | AGENTS.md | 备份: AGENTS.md.003 |
| 260818-000915 | AGENTS.md 改名为 context.md（git mv）；context.md 第一行更新为第十一次修改；README.md 更新引用（AGENTS.md→context.md）+ 新增 WorkBuddy 适配段落（系统级/项目级上下文文件体系） | context.md, README.md | git commit: 260818-000915:AGENTS.md改名为context.md+README加WorkBuddy适配段落 |
| 260818-001629 | context.md 第15行改为commit格式说明（删除重复的备份判断逻辑）；5.7简化为"同样适用5.5-5.6"（删除重复的判断逻辑）；第一行更新为第十二次修改 | context.md | git commit: 260818-001629:第15行改为commit格式说明+5.7简化为引用5.5-5.6+第一行更新 |
| 260818-002133 | context.md 第15行加"如果commit没有反应出顺序，则是失败的和不合格的"；第一行括号内加"如果本文被修改，则必须用shell命令获取当天日期，然后变更本行内容"；第一行更新为第十三次修改 | context.md | git commit: 260818-002133:第15行加commit顺序要求+第一行加shell获取日期要求+更新为第十三次 |
| 260818-002322 | context.md 5.5末尾补充"日期和时间必须用shell命令获取当前date和time，不允许自行计算或硬编码"；第一行更新为第十四次修改 | context.md | git commit: 260818-002322:5.5补充shell命令获取日期时间要求+第一行更新为第十四次 |
| 260818-002423 | context.md 第一行删除"每次修改都要变更这一行"（已被shell获取日期的规则覆盖）；第一行更新为第十五次修改 | context.md | git commit: 260818-002423:第一行删除每次修改都要变更这一行+更新为第十五次 |
| 260818-002447 | context.md 第一行修正为第十四次修改（上一次误改为第十五次，老板给的是第十四次） | context.md | git commit: 260818-002447:第一行修正为第十四次修改 |
| 260818-002604 | README删除context.md部署到项目级AGENTS.md的错误描述 | README.md | git commit: 260818-002604:README删除context.md部署到项目级AGENTS.md的错误描述 |
| 260818-002734 | README第一行加日期版本（总第五次修改）；WorkBuddy适配段落删除项目级描述，只保留系统级 | README.md | git commit: 260818-002734:README加日期版本行+删除项目级描述只保留系统级 |
| 260818-002944 | README删除标题行`# context-rules`，第一行直接为日期版本行（总第六次修改）；删除旧备份文件 AGENTS.md.001、README.md.001 | README.md | git commit: 260818-002944:README删除标题行+修正第一行为日期版本行+删除旧备份文件 |
| 260818-003132 | context.md 部署到 ~/.workbuddy/CODEBUDDY.md（WorkBuddy系统级上下文文件），目录外文件无git，老板选择文件备份 | ~/.workbuddy/CODEBUDDY.md | 备份: ~/.workbuddy/CODEBUDDY.001.md |
| 260819-012130 | context.md 部署到 ~/.config/opencode/AGENTS.md（opencode系统级上下文文件），从旧版（无版本行）更新到260818第十四次修改 | ~/.config/opencode/AGENTS.md | 备份: ~/.config/opencode/AGENTS.md.002 |
| 260819-012130 | context.md 部署到 ~/.dsh/AGENTS.md（dsh系统级上下文文件），从260817第八次修改更新到260818第十四次修改 | ~/.dsh/AGENTS.md | 备份: ~/.dsh/AGENTS.md.003 |
| 260819-012318 | 流程修正：012130 两条部署实际走了 curl /tmp 中转+cp 弯路，本次按正流程重做——git pull 同步仓库后，用仓库 context.md 覆盖 opencode 与 dsh 副本，五处副本（CODEBUDDY/SOUL/opencode/dsh/仓库源）MD5 校验一致 f52850edcdf6e1dfb911b1a155d57897 | ~/.config/opencode/AGENTS.md, ~/.dsh/AGENTS.md | git commit: 260819-012318:流程修正重做部署并MD5校验 |
| 260819-012519 | 流程再修正：部署源只能是云端 raw 地址（README 更新机制），与本地仓库 git 同步是完全独立的两件事。012213 那次用仓库 context.md 部署也是错的。本次按云端流程重做：curl raw.githubusercontent.com 直接拉取覆盖 opencode 与 dsh 副本，五处副本 MD5 校验一致 f52850edcdf6e1dfb911b1a155d57897 | ~/.config/opencode/AGENTS.md, ~/.dsh/AGENTS.md | git commit: 260819-012519:部署改走云端raw流程并MD5校验 |
| 260819-145450 | SOUL.md 瘦身：删除与 context.md 重叠的三条（genuinely helpful≈交流风格客套话、resourceful before asking≈最高规则4、earn trust 内部大胆部分≈5.1-5.3）及整段 Vibe 重叠表述；删除冲突的自我演化授权句（"yours to evolve, update it"）；保留独有项：have opinions、guest 意识、四条 Boundaries、精简 Vibe（结论先行+可溯源）、Continuity。背景：实测确认 WorkBuddy 不加载 CODEBUDDY.md，SOUL.md 为实际生效的系统级规则载体 | ~/.workbuddy/SOUL.md | 备份: ~/.workbuddy/SOUL.001.md |
| 260819-150538 | README.md WorkBuddy 适配章节重写：部署目标从 CODEBUDDY.md（实测不被加载，废弃）改为 SOUL.md 部署区；写入部署区状态机规则（有分割线→替换分割线后内容，无分割线→全文件替换为分割线+context.md）；补充部署区 MD5 校验与 10000 字符硬上限；第一行更新为总第八次修改。老板已在 SOUL.md 末尾添加分割线（部署区当前为空，待首次部署） | README.md | git commit: 260819-150538:README改WorkBuddy部署目标为SOUL部署区+状态机规则 |
| 260819-152603 | context.md 首次部署到 ~/.workbuddy/SOUL.md 部署区（按 README 状态机：分割线存在→分割线后全部内容替换为云端 raw 最新 context.md）。部署源 = raw.githubusercontent.com 云端直拉；部署区（第1189字节起）MD5 = f52850edcdf6e1dfb911b1a155d57897，与云端 raw 一致；身份区 1-35 行未动；全文件 8766 字节 / 4080 字符，低于 10000 字符硬上限 | ~/.workbuddy/SOUL.md | 备份: ~/.workbuddy/SOUL.002.md |
