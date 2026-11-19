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
| 传统液力行星 AT | ACCEPT_SCOPED_GENERATION_ONLY | ACCEPT_SCOPED_GENERATION_ONLY | GENERATED_REVIEW_PENDING | OPEN | [FAIL-AT](./topics/transmission/automatic/failure.md) 本轮实际提交、需异对话独审；REP-AT 仍未准入 | [FUN-AT-PATH 独立 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6989359346)；[FUN-AT-HYD 独立 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6989338636)；新 FAIL Blob `042c8d6bb21c53b877a6cd36238d854044759307`，待内容独审，不等于 OEM 维修结论 |
| 传动/差速器 | OPEN | OPEN | OPEN | OPEN | STR-DRIVELINE | 待激活广度 |
| 制动 / ABS/ESC | ACCEPT_SCOPED_GENERATION_ONLY | OPEN | OPEN | OPEN | FUN-BRK | [STR-BRK 独立质量 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6955581575)；安全关键，发生频率 UNKNOWN |
| 转向悬架/轮胎 | GENERATED_REVIEW_PENDING | OPEN | OPEN | OPEN | STR-STEER-SUSP 内容质量独审；未来 FUN 须独立增量计划 | [结构稿](./topics/steering-suspension/structure.md) Blob `1c84e3329bfcb40bcc2a01dac1b6af15ef5bfb40` 已实际生成，涵盖 HPS/EHPS/EPS、悬架、轮胎与 UNKNOWN |
| 低压电气/网络 | ACCEPT_SCOPED_GENERATION_ONLY | OPEN | OPEN | OPEN | 后续 FUN-LOWV 需单独新受审 DAG | [STR-LOWV 限定质量 ACCEPT（P2×1）](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6984507844)，ICE/BEV 起动、供电与 CAN/LIN；非具体车型 OEM 事实 |
| 空调/热管理 | OPEN | OPEN | OPEN | OPEN | STR-THERMAL | 待激活广度 |
| 车身/被动安全 | OPEN | OPEN | OPEN | OPEN | STR-BODY-SAFETY | 待激活广度，高风险操作边界 |
| BEV 高压/电驱/充电 | ACCEPT_SCOPED_GENERATION_ONLY | OPEN | OPEN | OPEN | FUN-HV | [STR-HV 独立质量 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6955609189)；仅非操作性结构知识 |
| 跨系统诊断/维护通用技术 | OPEN | OPEN | OPEN | OPEN | DISC-METHOD | 先定义跨系统共享原则 |
| 机械式 CVT 共用家族（增量 R1） | ACCEPT_SCOPED_GENERATION_ONLY | ACCEPT_SCOPED_GENERATION_ONLY | OPEN | OPEN | 仅当新 DAG 审核后才可新增 FAIL/REP-CVT | [STR-CVT 独立 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6988497818)；[FUN-CVT 独立 ACCEPT P2×2](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6989372961)，Blob `368e0e8fb644674df5262a3bad8f394a810db164`；OEM/VIN 事实 0 |
| HEV 共用家族 IMA/i-DCD/e:HEV（增量 R1） | ACCEPT_SCOPED_GENERATION_ONLY | REWORK_R2_REVIEW_PENDING | OPEN | OPEN | [FUN-HEV 独立 R1 REWORK P1×1](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6989371968)；R2 原 Writer 最小修复后待异对话增量审 | [STR-HEV 独立 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6988518984)；FUN-HEV 原 Blob `2196e74550b7d4b2f4ed4c0a09ed3f83db4bfa87` 为 REWORK，新 Blob `f625c181d59471bfff80724583127099430c400c` 尚未审 |
| 柴油/独立 DCT/PHEV/其它电驱/重型等尚未研究切片 | OUT_OF_INITIAL_SLICE | OUT_OF_INITIAL_SLICE | OUT_OF_INITIAL_SLICE | OUT_OF_INITIAL_SLICE | ARCH-EXPAND | 家族增量仅覆盖明确 CVT 与 HEV，不能把未覆盖系统误标完成或不适用 |

## 缅甸车型系列适用性覆盖（与通用 S/F/X/R 正交）

> SERIES_PLAN：[VEHICLE_SERIES_DAG_R1.md](./VEHICLE_SERIES_DAG_R1.md) · Exact Blob `4229bb3913cff46ccb780247d78d5a94bd6dd049` · [其它对话独立 PLAN ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6959482030) P2×3 非阻断 · [SER-DISPATCH 准入](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6960479119)。不改变已审核主 PLAN DAG，车型系列发现不自动计作系统知识 S/F/X/R 文章。

| 缅甸在用相关车系候选 | 发现任务 | 当前 Markdown Blob | 状态 | 实质差异候选与真正阻塞 |
|---|---|---|---|---|
| Toyota Probox（Succeed 单独关联） | `SER-DISC-PROBOX` | `c8f011229a4e6fa6c66ae092a6f19a21142b4f19` · [正文](./series/myanmar/toyota/probox/discovery.md) | `ACCEPT_SCOPED_GENERATION_ONLY` · [独审 P2×2](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6962402777) | `SER-DELTA-PROBOX-TRANS` 已写实质差量候选 [Markdown](./series/myanmar/toyota/probox/transmission-applicability-delta.md) Blob `2a0bfda60bc63ea484c45a6c0b01fe31f7db51a0`，[独立质量 ACCEPT P2×2](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6976215650)；润滑差量仍 `BLOCKED_SOURCE` |
| Honda Fit / Jazz（地域名称待核） | `SER-DISC-FIT` | `2c8ab39f67c076352586eed2a2f2187147fa909a` · [正文](./series/myanmar/honda/fit/discovery.md) | `ACCEPT_SCOPED_GENERATION_ONLY` · [独审 P2×3](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6962478386) | `SER-DELTA-FIT-TRANS` 已生成技术差量候选 [Markdown](./series/myanmar/honda/fit/transmission-variants-delta.md) Blob `a1a944399d2dd7dde3ce8e4be9bda06e94b431af`，[独立质量 ACCEPT P2×3](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6976201311)；制动差量仍 `BLOCKED_SOURCE` |

**严格统计（2026-11-19 / 本轮 R7）**：知识 Markdown **18 篇实际生成**；其中 **15 篇已获独立限定质量 ACCEPT**（基线 STR 5、Probox/Fit DISC 2、TRANS delta 2、VARIANT GAPS 1、CVT/HEV STR 2、FUN-CVT 1、FUN-AT 双功能 2）。**3 篇未通过/待审**：`FUN-HEV-FAMILY` 的 R1 REWORK P1×1 已由原 Writer 在 §2.2 最小修复，新 Blob `f625c181d59471bfff80724583127099430c400c` 待异对话增量审；新 `FAIL-AT` Blob `042c8d6bb21c53b877a6cd36238d854044759307` 待独审；新 `STR-STEER-SUSP` Blob `1c84e3329bfcb40bcc2a01dac1b6af15ef5bfb40` 待独审。原通用、缅甸车系及 CVT/HEV 计划 Blob 保持不变；另外两条车型差量仍 SOURCE_GAP，正式 OEM/VIN/N3 专业事实资格 0。

## 更新与再规划（每次真实交付后执行）

1. 读取最新 GitHub 正文 Commit/Blob、准确文件路径、独立内容质量审核结论；**仅在内容阶段符合对应状态时**改变 S/F/X/R，保留未知/适用范围。
2. 新增发现的真实系统/子系统/总成/部件，给出 `system_id / parent_or_crosslink / slice / source_visibility / status / gap` 的 Markdown 行，必要时细化为新表；不能靠已有行数推断整个汽车覆盖完整。
3. 至少指出**一个真实存在且当前未覆盖的分支候选**和它的优先级证据/UNKNOWN，并派生一个有问题、前置、唯一写集、语义验收的新 Task；若当前没有足够信息能创建任务，写清阻塞资料，不能编造。
4. 同一机理存在跨系统复用时，将链接指向已生成 Markdown；新增文章仅写差异，不复制。
5. 每次调度记录本轮 `BREADTH` 与 `DEPTH` 选择理由、被延期的最高价值真实 OPEN 分支、下次触发条件；高价值深度不能使全部结构广度永久饥饿。
6. 每轮仅更新 changed 行与收据，省略重复旧验收；记录 `task_id / exact_commit / exact_blob / reviewer_scope / claim / date / remaining_gap`。
7. 下一轮任务仅从未认领的 `READY` 候选与已确认缺口中选择；**执行 DAG 无环，但知识图可保留循环反馈关系**。

## R7 源码更新与独立审核交接（2026-11-19）

| Task | 本轮实际改变 | Commit / 当前 Exact Blob | 内容结论 |
|---|---|---|---|
| `FUN-HEV-FAMILY` | [R1 P1 来源已知的 i-DCD 三种驱动模式缺口](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6989371968)，原 Writer **仅 §2.2 最小修改** | [Markdown](./topics/electrified/hybrid/function.md) Commit `e76013da96f9c81c820665e4da4caa90d4ec965a` / Blob `f625c181d59471bfff80724583127099430c400c` | **R1 REWORK / R2 INCREMENTAL_REVIEW_PENDING**；不得自动转 ACCEPT |
| `FUN-AT-PATH` | [独立内容质量 ACCEPT P2×2](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6989359346) | 原 Blob `6c0a2855abf2751819ebcf1b039db05d8a953f71` | ACCEPT_SCOPED_GENERATION_ONLY |
| `FUN-AT-HYD` | [独立内容质量 ACCEPT P2×1](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6989338636) | 原 Blob `88338dbea91a278866ffb7ccca7d69b0f22c349e` | ACCEPT_SCOPED_GENERATION_ONLY |
| `FUN-CVT-FAMILY` | [独立内容质量 ACCEPT P2×2](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6989372961) | 原 Blob `368e0e8fb644674df5262a3bad8f394a810db164` | ACCEPT_SCOPED_GENERATION_ONLY |
| `FAIL-AT` | 两 FUN 都已独审后，首次 [实质失效模式 Markdown](./topics/transmission/automatic/failure.md) | Commit `09a1babede4cde0e55747cd714f677dd20d38262` / Blob `042c8d6bb21c53b877a6cd36238d854044759307` | GENERATED_REVIEW_PENDING，REP-AT 尚未生成 |
| `STR-STEER-SUSP` | 原广度 DAG [转向/悬架/轮胎结构 Markdown](./topics/steering-suspension/structure.md) | Commit `4be9513c711b1afd6e2d52517e1750aa57b214e9` / Blob `1c84e3329bfcb40bcc2a01dac1b6af15ef5bfb40` | GENERATED_REVIEW_PENDING；后续 FUN 须新受审 DAG |

## 本轮传统 AT 双功能真实产出（R6）

> STR-AT Blob `ed2b997ca164d98e74cf72ecb393aca86a553d20` 已限定独立质量 ACCEPT。两个 FUN 分别 Claim、原子创建、Commit/Blob 回读并 RELEASE。**后继 FAIL-AT 尚未实际生成**，必须结合两篇功能的独立内容质量审核后再合法推进。

| Task | Markdown 文件 | Exact Commit / Blob | 质量状态 |
|---|---|---|---|
| `FUN-AT-PATH` | [动力路径](./topics/transmission/automatic/power-path.md) | `3b435b77deafec8041f8342c603f111b98563a42` / `6c0a2855abf2751819ebcf1b039db05d8a953f71` | GENERATED_REVIEW_PENDING |
| `FUN-AT-HYD` | [液压控制](./topics/transmission/automatic/hydraulic-control.md) | `9ea1604d6ed0a2dc3d781e0728efefe476961058` / `88338dbea91a278866ffb7ccca7d69b0f22c349e` | GENERATED_REVIEW_PENDING |

## 新共享家族结构→功能交付收据（R6：结构审核通过，功能待审）

> [新家族增量 DAG](./SERIES_FAMILY_DAG_R1.md) 已 [独立接受](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6984583673)；[C-FAM-DISPATCH 已另行准入](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6987899954)。相应两条链只依赖自身上游真实结构 Commit；独立内容审核未发生，结构如 REWORK，受影响功能必须 STALE。

| Task | 原生 Markdown 文件 | 最新 Commit | Exact Blob | 真实状态 |
|---|---|---|---|---|
| `STR-CVT-FAMILY` | [CVT 结构](./topics/transmission/cvt/structure.md) | `00824f94e9592c72734de7a2dbd12a85f621d2f0` | `19201970db7bb121d28df02f1c862cd05765cea4` | [独立质量 ACCEPT P2×2](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6988497818) |
| `FUN-CVT-FAMILY` | [CVT 功能](./topics/transmission/cvt/function.md) | `b0b36c5bd14654bb84a2fd3825f639ca5239f835` | `368e0e8fb644674df5262a3bad8f394a810db164` | GENERATED_REVIEW_PENDING，依赖 CVT STR |
| `STR-HEV-FAMILY` | [HEV 结构](./topics/electrified/hybrid/structure.md) | `e5170739a3a32354bcf09f0bd11a7cbf3f066ac0` | `23baed760bcf3dbb76cecfa609d8a7200532a8a9` | [独立质量 ACCEPT P2×2](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6988518984) |
| `FUN-HEV-FAMILY` | [HEV 功能](./topics/electrified/hybrid/function.md) | `e021cd177716ad574dd55ff9765fd5420f729026` | `2196e74550b7d4b2f4ed4c0a09ed3f83db4bfa87` | GENERATED_REVIEW_PENDING，依赖 HEV STR |

## 本轮新增通用广度收据

| Task | 实际文件 | 最新 Commit / Blob | 状态 |
|---|---|---|---|
| STR-LOWV | [低压电气/网络结构](./topics/electrical-low-voltage/structure.md) | Commit `0c824f0d206f53c965ace6ad95f69bfbc6e3e6d4` / Blob `27520498eefdc491c5e857600b902677730c400d` | [独立内容质量 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6984507844) P2×1 非阻断；OEM/专业事实仍 0 |

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
