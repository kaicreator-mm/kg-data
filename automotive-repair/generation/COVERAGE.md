# 汽修知识生成覆盖账本 — v0.4.1

> MAIN: [parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) | CONTROL: `C-COVERAGE` | STATUS: `DRAFT_INITIALIZED__REVIEW_PENDING`。
> **这里的 OPEN 是缺口，不代表知识已生成。** 初始仅限 [SCOPE.md](./SCOPE.md) 规定的两个通用架构研究切片，非全部 OEM 车型/全部汽修。

## 四视角覆盖状态

`S` = 结构、`F` = 功能原理、`X` = 失效模式、`R` = 诊断维修维护。每个单元只记录实际观察状态：
- `OPEN`：真实计划问题尚未有满足验收的 Markdown
- `GENERATED_REVIEW_PENDING`：文件实际提交并回读，还未获限定内容质量审查
- `ACCEPT_SCOPED_GENERATION_ONLY`：限定的知识生成审阅通过，**非事实权威认证**
- `UNKNOWN`：证据/适用范围不足，不能假装已覆盖
- `NOT_APPLICABLE`：在**确定的车型/架构切片**中有理由证明不适用；不能用来忽略其它车型
- `OUT_OF_INITIAL_SLICE`：不在首轮范围，不能作为完成/不适用计算

| 对象/切片 | S | F | X | R | 下一具体缺口/任务 | 为什么选择或延期 |
|---|---|---|---|---|---|---|
| ICE 润滑 | OPEN | OPEN | OPEN | OPEN | STR-ENG-LUBE | 共有机械基础，首批广度 |
| ICE 空气/燃油/排放 | OPEN | OPEN | OPEN | OPEN | STR-ENG-AIRFUEL | 待激活广度 |
| 传统液力行星 AT | OPEN | OPEN | OPEN | OPEN | STR-AT | 既有 TOC 线索；不代表已读正文 |
| 传动/差速器 | OPEN | OPEN | OPEN | OPEN | STR-DRIVELINE | 待激活广度 |
| 制动 / ABS/ESC | OPEN | OPEN | OPEN | OPEN | STR-BRK | 可信安全重要性，但实测故障频率 UNKNOWN |
| 转向悬架/轮胎 | OPEN | OPEN | OPEN | OPEN | STR-STEER-SUSP | 待激活广度 |
| 低压电气/网络 | OPEN | OPEN | OPEN | OPEN | STR-LOWV | 待激活广度 |
| 空调/热管理 | OPEN | OPEN | OPEN | OPEN | STR-THERMAL | 待激活广度 |
| 车身/被动安全 | OPEN | OPEN | OPEN | OPEN | STR-BODY-SAFETY | 待激活广度，高风险操作边界 |
| BEV 高压/电驱/充电 | OPEN | OPEN | OPEN | OPEN | STR-HV | 首批广度+安全认知 |
| 跨系统诊断/维护通用技术 | OPEN | OPEN | OPEN | OPEN | DISC-METHOD | 先定义跨系统共享原则 |
| 混动/柴油/CVT/DCT/e-CVT/重型等 | OUT_OF_INITIAL_SLICE | OUT_OF_INITIAL_SLICE | OUT_OF_INITIAL_SLICE | OUT_OF_INITIAL_SLICE | ARCH-EXPAND | 未来扩展切片；不冒充不适用 |

## 更新与再规划（每次真实交付后执行）

1. 读取最新 GitHub 正文 Commit/Blob、准确文件路径、独立内容质量审核结论；**仅在内容阶段符合对应状态时**改变 S/F/X/R，保留未知/适用范围。
2. 新增发现的真实系统/子系统/总成/部件，给出 `system_id / parent_or_crosslink / slice / source_visibility / status / gap` 的 Markdown 行，必要时细化为新表；不能靠已有行数推断整个汽车覆盖完整。
3. 至少指出**一个真实存在且当前未覆盖的分支候选**和它的优先级证据/UNKNOWN，并派生一个有问题、前置、唯一写集、语义验收的新 Task；若当前没有足够信息能创建任务，写清阻塞资料，不能编造。
4. 同一机理存在跨系统复用时，将链接指向已生成 Markdown；新增文章仅写差异，不复制。
5. 每次调度记录本轮 `BREADTH` 与 `DEPTH` 选择理由、被延期的最高价值真实 OPEN 分支、下次触发条件；高价值深度不能使全部结构广度永久饥饿。
6. 每轮仅更新 changed 行与收据，省略重复旧验收；记录 `task_id / exact_commit / exact_blob / reviewer_scope / claim / date / remaining_gap`。
7. 下一轮任务仅从未认领的 `READY` 候选与已确认缺口中选择；**执行 DAG 无环，但知识图可保留循环反馈关系**。

## 当前实际记录
- 本文是结构先行的覆盖账本**初始化**，没有虚报正文生成；所有首批知识内容仍 OPEN。
- 不允许因创建目录、生成计划、上传文件、引用书目录而将内容状态改为 `GENERATED`。
- 生成前仍须先完成 v0.4.1 PLAN 的独立增量计划审查（#61 原 v0.4 审核结果为 REWORK）。
