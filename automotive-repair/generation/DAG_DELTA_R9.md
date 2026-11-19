# 汽修知识生成 Task DAG · R9 增量扩展候选（C-REPLAN）

> MAIN: [parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) · DATA: `kaicreator-mm/kg-data` · OUTPUT_LABEL: `PARTS_AUTOREPAIR_V047_C_REPLAN_DELTA_W1`  
> **状态：`PROPOSED__INDEPENDENT_DELTA_REVIEW_PENDING`；所有本文件新节点尚非 READY。** 当前仅第一阶段生成知识，必交原生 Markdown；计划不是 OEM 资格。此文件**只新增 DAG 节点，不修改/撤销既有已审计划 Blob**，审过才可合并为执行视图。

## 1. 已独立通过的三份基线（只读）

| 计划 | Exact Blob | 已审原图 |
|---|---|---|
| [PLAN v0.4.1](./PLAN.md) | `1df1f116a9f4e1effc46840aa4ec57be1289b6cf` | 通用 32 task，包括已存在的 `FAIL-BRK`、`FUN-HV`、`FUN-ENG-LUBE` |
| [缅甸 SERIES R2](./VEHICLE_SERIES_DAG_R1.md) | `4229bb3913cff46ccb780247d78d5a94bd6dd049` | 10 task，Probox/Succeed 与 Fit 研究切片 |
| [CVT/HEV FAMILY R1](./SERIES_FAMILY_DAG_R1.md) | `58d616663c2262efa4fc62851d8962a637294703` | 6 task，共用结构与正常机理 |

基线计划已在 #61 分别得到限定 `PLAN_READY` 和分支 `DISPATCH`。本轮只审新增六条直接依赖、文件写集、可执行边界与全图无环性。当前总图为 48 个原 Task；新增六个若获独审准入，合并执行图为 **54 Task**。此计数只是任务 DAG 节点数量，**不是文章数量或专业知识完成度**。

## 2. 六条非重叠新增任务及输出

所有任务的共同前置：当前合法 `C-DISPATCH`/对应家族 `C-FAM-DISPATCH` 与**表列具体知识前置真实 Markdown 已 GitHub 回读**；进入 Writer 前需额外获得本 R9 增量计划 `ACCEPT_SCOPED_DELTA_PLAN_READY` 和 `C-R9-DISPATCH=ADMITTED`。各任务另行 Claim、二次仲裁并独占单个文件。下面的输出目前均为候选，**没有把这些文件标记为已创建**。

| 新 Task ID | 独立直接知识前置（基线节点、当前源 Blob） | 唯一新增 Markdown 输出 | 必须回答的专业问题 / 限定验收 |
|---|---|---|---|
| `FUN-THERMAL` | `STR-THERMAL` @ `377ee9339949f39d916591f2ada300a59e3c72f7`，独审 ACCEPT [#6996518885](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6996518885) | `topics/thermal/function.md` | ICE 冷却液-油-空气、A/C 冷媒与 BEV 电池/电驱/客舱不同热回路如何按运行需求传热、控制与限制？区别冷媒、冷却液、热泵以及组件可选性；不编造制冷剂维修动作 |
| `FUN-STEER-SUSP` | `STR-STEER-SUSP` @ `1c84e3329bfcb40bcc2a01dac1b6af15ef5bfb40`，独审 ACCEPT [#6995919397](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6995919397) | `topics/steering-suspension/function.md` | 转向力反馈、EPS/HPS/EHPS 助力/供能，弹簧与阻尼、四轮几何和轮胎侧向力的正常机理；不同工况与反例，不虚构车型四轮定位参数 |
| `FUN-LOWV` | `STR-LOWV` @ `27520498eefdc491c5e857600b902677730c400d`，独审 ACCEPT [#6984507844](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6984507844) | `topics/electrical-low-voltage/function.md` | ICE 起动/充电、BEV DC/DC 低压供电、保险和电源分配；CAN/LIN 通信与网关条件机理，区别供电、通信和控制故障指示；不编造车型线束/针脚 |
| `FUN-DRIVELINE` | `STR-DRIVELINE` @ `9f70017bc47e3bc30110dfbc15ad5070c75981e1`，**尚待**其他对话独审 | `topics/driveline/function.md` | FWD/RWD/AWD 的终传/差速/半轴与等速节如何满足轮速差、转角、轴向运动、转矩路径和控制耦合？说明理想运动学与真实附着限制；本上游如 REWORK 则禁止或标 STALE |
| `FAIL-CVT-FAMILY` | `FUN-CVT-FAMILY` @ `368e0e8fb644674df5262a3bad8f394a810db164`，独审 ACCEPT [#6989372961](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6989372961) | `topics/transmission/cvt/failure.md` | 在 CVT 类型差异明确时，夹紧/变比执行、液压、电控、热/润滑、输入耦合失效的机制与竞争诊断线索；不得把 DCT、传统液力行星 AT、Honda e:HEV Electric CVT 混成同一机械故障 |
| `FAIL-HEV-FAMILY` | `FUN-HEV-FAMILY` R2 @ `f625c181d59471bfff80724583127099430c400c`，独审 ACCEPT [#6995879183](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6995879183) | `topics/electrified/hybrid/failure.md` | 明确 IMA、i-DCD、e:HEV 的能量路径/模式差异，研究请求/允许/实际扭矩、充电状态、热/电气与模式保护竞争解释；不提供混动/高压/制动实操 |

注：若某个旧前置 Blob 在审核或 Writer 时改变，必须重新核查 `STALE` 对应任务与实际受影响范围；不能把已过审旧 Blob 当成新版本自动接受。

## 3. DAG 依赖、无环论证与对既有任务的影响

新增知识边（箭头左侧为上游）：

```text
STR-THERMAL -> FUN-THERMAL
STR-STEER-SUSP -> FUN-STEER-SUSP
STR-LOWV -> FUN-LOWV
STR-DRIVELINE -> FUN-DRIVELINE
FUN-CVT-FAMILY -> FAIL-CVT-FAMILY
FUN-HEV-FAMILY -> FAIL-HEV-FAMILY
```

- 新 ID 唯一；六条路径都不与基线 STR/FUN/FAIL/REP、Series delta 或其它新 Task 共用输出。每条新边只从**已存在的基线 Task**流向**一个全新、尚无任何下游边**的 Task；没有任何从新节点回指原节点或其它新节点的边，故旧已审 48 节点若无环，加入这六条单向叶子边后仍无环（拓扑顺序：原 48 节点原序，后跟六个新节点）。
- **不建立跨系统伪门禁**：FUN-THERMAL 不依赖 FUN-BRK；FUN-DRIVELINE 不依赖某品牌 AT；FAIL-CVT 不依赖传统行星 AT STR；FAIL-HEV 不依赖 BEV 专用结构；六个写集可并行。
- 旧图中的 `FAIL-BRK` 已在 [PLAN §4](./PLAN.md) 且 `FUN-BRK` [已独审 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6996547593)，应立即由旧 `C-DISPATCH` 派发，**不占用本 R9 增量审核资格或伪造新 Task**。
- 车型轴：通用差速/CVT/HEV 不等于 Probox/Fit 缅甸 VIN 配置；原 `SER-DELTA-PROBOX-LUBE`、`SER-DELTA-FIT-BRK` 的 `SOURCE_GAP` 保持，不能靠新通用节点关闭。
- 尚未修改 `PLAN.md`、`VEHICLE_SERIES_DAG_R1.md`、`SERIES_FAMILY_DAG_R1.md` 的旧 Blob；本文件只有其他对话明确增量接受并由 Integrator 登记 `C-R9-DISPATCH` 后，才成为执行有效增量，未接受前一律 `PROPOSED`。

## 4. 独立审核、放行与停止条件

1. 独立非本 Proposal Writer 对话读取三份原 PLAN Exact Blob、六个上游 Markdown 当前 Blob、六个目标路径是否被其它 Writer 占用、#61 现有 Claim 与本文件新 Blob；检查新增 ID/路径/前置、图无环、是否错误继承车型/OEM 和安全边界。
2. 审核只能回写 `ACCEPT_SCOPED_DELTA_PLAN_READY` 或 `REWORK` + P0/P1/P2 + Exact Blob；本计划审核不自动签署专业事实或质量验收；Source-First 重审只针对**新边界**而非全部旧知识。
3. Integrator 审核通过后对新六条中真正前置满足且唯一写集空闲的节点发 `C-R9-DISPATCH=ADMITTED`；可同时派发五条已有独审前置的节点，`FUN-DRIVELINE` 按上游内容审结论决定，不让一个下游阻塞其它五条。
4. Writer 各自只创建目标 `.md`、Source-First 可见来源、正常/失效机理、适用条件、竞争假说及 UNKNOWN；Commit→Blob 回读→RELEASE；由其他对话独立审质量。信息增量不足、找不到适用来源或有无法安全限定的问题可以 `DEFERRED/UNKNOWN`，不能填空凑数。
5. 后续只因新生成文件或真实新缺口扩张，不以 “任务数到 54” 宣布车系/整车汽修知识完整。
