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
| ICE 润滑 | ACCEPT_SCOPED_GENERATION_ONLY | OPEN | OPEN | OPEN | FUN-ENG-LUBE | [STR-ENG-LUBE R2 独立质量 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6956153492)，另有非阻断 P2 ISO 草案来源时效问题 |
| ICE 空气/燃油/排放 | OPEN | OPEN | OPEN | OPEN | STR-ENG-AIRFUEL | 待激活广度 |
| 传统液力行星 AT | ACCEPT_SCOPED_GENERATION_ONLY | OPEN | OPEN | OPEN | FUN-AT-PATH / FUN-AT-HYD | STR-AT 已独立内容质量限定 ACCEPT；不代表 OEM/N3 事实合格 |
| 传动/差速器 | OPEN | OPEN | OPEN | OPEN | STR-DRIVELINE | 待激活广度 |
| 制动 / ABS/ESC | ACCEPT_SCOPED_GENERATION_ONLY | OPEN | OPEN | OPEN | FUN-BRK | [STR-BRK 独立质量 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6955581575)；安全关键，发生频率 UNKNOWN |
| 转向悬架/轮胎 | OPEN | OPEN | OPEN | OPEN | STR-STEER-SUSP | 待激活广度 |
| 低压电气/网络 | OPEN | OPEN | OPEN | OPEN | STR-LOWV | 待激活广度 |
| 空调/热管理 | OPEN | OPEN | OPEN | OPEN | STR-THERMAL | 待激活广度 |
| 车身/被动安全 | OPEN | OPEN | OPEN | OPEN | STR-BODY-SAFETY | 待激活广度，高风险操作边界 |
| BEV 高压/电驱/充电 | ACCEPT_SCOPED_GENERATION_ONLY | OPEN | OPEN | OPEN | FUN-HV | [STR-HV 独立质量 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6955609189)；仅非操作性结构知识 |
| 跨系统诊断/维护通用技术 | OPEN | OPEN | OPEN | OPEN | DISC-METHOD | 先定义跨系统共享原则 |
| 混动/柴油/CVT/DCT/e-CVT/重型等 | OUT_OF_INITIAL_SLICE | OUT_OF_INITIAL_SLICE | OUT_OF_INITIAL_SLICE | OUT_OF_INITIAL_SLICE | ARCH-EXPAND | 未来扩展切片；不冒充不适用 |

## 缅甸车型系列适用性覆盖（与通用 S/F/X/R 正交）

> SERIES_PLAN：[VEHICLE_SERIES_DAG_R1.md](./VEHICLE_SERIES_DAG_R1.md) · Exact Blob `4229bb3913cff46ccb780247d78d5a94bd6dd049` · [其它对话独立 PLAN ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6959482030) P2×3 非阻断 · [SER-DISPATCH 准入](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6960479119)。不改变已审核主 PLAN DAG，车型系列发现不自动计作系统知识 S/F/X/R 文章。

| 缅甸在用相关车系候选 | 发现任务 | 当前 Markdown Blob | 状态 | 实质差异候选与真正阻塞 |
|---|---|---|---|---|
| Toyota Probox（Succeed 单独关联） | `SER-DISC-PROBOX` | `c8f011229a4e6fa6c66ae092a6f19a21142b4f19` · [正文](./series/myanmar/toyota/probox/discovery.md) | `GENERATED_REVIEW_PENDING` | 厂商 2002 家族 4AT/5MT 与 2014 日本改款 CVT 差异是真实研究问题；`SER-DELTA-PROBOX-TRANS` 待独审/配置限定。润滑差量缺具体油路证据，暂 `BLOCKED_SOURCE` |
| Honda Fit / Jazz（地域名称待核） | `SER-DISC-FIT` | `2c8ab39f67c076352586eed2a2f2187147fa909a` · [正文](./series/myanmar/honda/fit/discovery.md) | `GENERATED_REVIEW_PENDING` | Honda 官方汽油 CVT/部分 4WD 5AT/IMA-CVT/i-DCD 7DCT/e:HEV 代际区分，`SER-DELTA-FIT-TRANS` 待独审与配置证据；`SER-DELTA-FIT-BRK` 安全相关来源不足仍 CONDITIONAL |

**严格统计**：已真实生成 `SER-DISC 2/2`、系列发现独立内容质量 `ACCEPT=0/2`；四个 `SER-DELTA` 为 **0/4 已生成**，`SER-VARIANT-CHECK` 为 `WAITING_EVENT`。缅甸全域各车型上路保有量/维修工单/故障发生率仍 `UNKNOWN`；挂牌/历史新闻不是保有量分母。两篇发现不是二手车数量排名或 OEM VIN 级适用资格。

## 更新与再规划（每次真实交付后执行）

1. 读取最新 GitHub 正文 Commit/Blob、准确文件路径、独立内容质量审核结论；**仅在内容阶段符合对应状态时**改变 S/F/X/R，保留未知/适用范围。
2. 新增发现的真实系统/子系统/总成/部件，给出 `system_id / parent_or_crosslink / slice / source_visibility / status / gap` 的 Markdown 行，必要时细化为新表；不能靠已有行数推断整个汽车覆盖完整。
3. 至少指出**一个真实存在且当前未覆盖的分支候选**和它的优先级证据/UNKNOWN，并派生一个有问题、前置、唯一写集、语义验收的新 Task；若当前没有足够信息能创建任务，写清阻塞资料，不能编造。
4. 同一机理存在跨系统复用时，将链接指向已生成 Markdown；新增文章仅写差异，不复制。
5. 每次调度记录本轮 `BREADTH` 与 `DEPTH` 选择理由、被延期的最高价值真实 OPEN 分支、下次触发条件；高价值深度不能使全部结构广度永久饥饿。
6. 每轮仅更新 changed 行与收据，省略重复旧验收；记录 `task_id / exact_commit / exact_blob / reviewer_scope / claim / date / remaining_gap`。
7. 下一轮任务仅从未认领的 `READY` 候选与已确认缺口中选择；**执行 DAG 无环，但知识图可保留循环反馈关系**。

## 首轮并行新增交付收据

| Task | 当前正文 Commit | 当前 Blob | 源范围及审核状态 |
|---|---|---|---|
| `STR-ENG-LUBE` | `69f7584ff242eb452d77ceacd70d08863f7d8579` | `ff103f4cfd948534be5ca2b9413128aee502987f` | [独立质量 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6956153492) P2×1 非阻断，专业事实仍未证实 |
| `STR-AT` | `5eb2219e7afecde80920bf4c8277a68073a1e6f6` | `ed2b997ca164d98e74cf72ecb393aca86a553d20` | [独立生成质量 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6955520356)，源事实仍未获 OEM/N3 资格 |
| `STR-BRK` | `4ed14a5b8d24382c85e2989f56776ed5b2288a54` | `e231eda16a8d799d891e7604bee41437af29afb6` | [独立质量 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6955581575)，未获车型 OEM 资格 |
| `STR-HV` | `43c5d3da44fa72bc21f9d24c8fd32b03f1f5a370` | `472127e80e95f022dc512b0c635b7a63282c94d2` | [独立质量 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6955609189)，无高压实操/OEM 资格 |

详情见 [GENERATION_QUALITY_R0.md](./GENERATION_QUALITY_R0.md)；控制账本按实际提交更新，不把 Writer 生成资格冒充独立内容质量审查。

## 当前实际记录

- `STR-ENG-LUBE`：实际生成 Markdown `topics/engine/lubrication/structure.md`，初稿 Commit `74e8f3d575471d16c3052c3003931da0daf73d7a`、Blob `b43057bee5ef1ee291e55ca5b3a7f8aee04a5e4e`，R2 已补充 UNKNOWN：现 Commit `69f7584ff242eb452d77ceacd70d08863f7d8579`、Blob `ff103f4cfd948534be5ca2b9413128aee502987f`，GitHub readback 一致；**独立内容质量已限定 ACCEPT，P2 ISO 草案来源过时非阻断；专业事实未核验**。对应结构 S=`ACCEPT_SCOPED_GENERATION_ONLY`。后续 `FUN-ENG-LUBE` 可读取真实上游作为候选输入，任何上游 REWORK 需传播 `STALE`。
- 本轮 BREADTH 选择 ICE 润滑/制动/传统液力行星齿轮 AT/通用 BEV 高压结构，其它系统可独立并行启动而不等待四系统完成；`STR-LOWV` 为最高重要待派广度候选之一。F 仍 UNKNOWN，无发生率数据。
- 本账本现有四个真实结构 Markdown 交付，四个首批 STR 的结构 S 均已获得各自不同 Writer 对话的 `ACCEPT_SCOPED_GENERATION_ONLY`（STR-ENG-LUBE R2 P2×1 非阻断）。所有 F/X/R 均 OPEN，四篇专业事实仍 `MODEL_GENERATED_UNVERIFIED`。
- 不允许因创建目录、生成计划、上传文件、引用书目录而将内容状态改为 `GENERATED`。
- v0.4.1 PLAN 的独立增量审核已 `ACCEPT_SCOPED_PLAN_READY`，不再重开原 v0.4 REWORK；其放行只涉及计划与生成，不涉及四篇专业事实合格。详见 [审核结论](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6954464408)。
