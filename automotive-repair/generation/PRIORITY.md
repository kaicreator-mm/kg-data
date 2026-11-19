# 汽修知识生成动态优先级与并行调度 — R1

> MAIN: [parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) | PLAN: [v0.4.1](./PLAN.md) | 状态: `C-PRIORITY_DRAFT_R1`
> 计划入场：独立审核 [ACCEPT_SCOPED_PLAN_READY](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6954464408)，按 Blob `1df1f116a9f4e1effc46840aa4ec57be1289b6cf` 限定。详见 [C-DISPATCH Admission](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6954548597)。

## R10 最高优先级（2026-11-19，覆盖以下 R9 历史快照）

> **第二次真实交付已加入**：[FAIL-ENG-LUBE](./topics/engine/lubrication/failure.md) Commit `b5399838e85c992aba9b1ebbccecb7de56debea8` / Blob `8c2cbbcf9ea262d4945ecbb290874d3e10c86875`，独审待派。**当前 24 GENERATED / 21 SCOPED_ACCEPT / 3 REVIEW_PENDING**；之前 23/21/2 是本轮第一批快照，不再代表最新总数。新增 `FAIL-ENG-LUBE` 的上游 `FUN-ENG-LUBE` 仍待独审，若 REWORK 应按影响标 STALE。独审可将两个不同 Task 分交两个其它对话，避免自审或未经前置确认晋升。


- **真正新增**：`FUN-ENG-LUBE` [Markdown](./topics/engine/lubrication/function.md) Commit `94cac18b283cfa23ee500ce684648a331c3e3d3f` / Blob `1548f1d0d51b840f53e9fd101705d1ad49f0bc33` / [Writer RELEASE](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6997064528)；待另一对话独立内容质量审核。旧 `STR-ENG-LUBE@ff103f...` 审核可复用。
- **当轮总进度**：真实知识 `24 GENERATED / 21 SCOPED_ACCEPT / 3 REVIEW_PENDING`；另 6 个 [R9 新 DAG 候选](./DAG_DELTA_R9.md) 仍是 `PROPOSED__REVIEW_PENDING`，并非已准入/生成；OEM/VIN/N3=0。
- **旧 DAG 可立即再派**：`STR-ENG-AIRFUEL`、`STR-BODY-SAFETY`、`DISC-METHOD`、`FUN-HV`、`FAIL-BRK`（均旧 PLAN §4/§5）；`FAIL-ENG-LUBE` 已真实提交、待独审；后继 `REP-ENG-LUBE`（原 PLAN §4）须以已生成 FAIL 为前置且保持安全/来源限定，可滚动研究，遇上游 REWORK 则按影响标 `STALE` 并最小修复。
- **独立审**：优先 `STR-DRIVELINE@9f70017...`、`FUN-ENG-LUBE@1548f1d...`、`FAIL-ENG-LUBE@8c2cbbcf...` 三条不同 Reviewer 工作集，再审 `DAG_DELTA_R9@96bcd828...` 的六节点增量门禁；三条可由不同其它对话并行。所有审核**待真实领取**，上轮只是发 OFFER，不能算 RUNNING。
- **广度优先保障**：至少一个未覆盖整车系统结构节点（例如 `STR-ENG-AIRFUEL` 或 `STR-BODY-SAFETY`）并行于润滑/制动深度，不对缅甸 VIN/失效率/危险维修步骤作无来源外推。

## 历史 R9 派发优先级（2026-11-19；已被 R10 覆盖）

1. **R8 的三个独立质量审核已完成**：[REP-AT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6996518832)、[STR-THERMAL](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6996518885)、[FUN-BRK](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6996547593) 均 ACCEPT_SCOPED_GENERATION_ONLY，P0/P1=0；不重做旧来源核对。
2. **真实广度生成+待独审**：[STR-DRIVELINE](./topics/driveline/structure.md) Commit `f94d9c000049b070cde4c77c8febd7cacc904fa1` / Blob `9f70017bc47e3bc30110dfbc15ad5070c75981e1`；只由其它对话独审，不由原 Writer 自审。
3. **六条旧 DAG READY Writer 并行**：`STR-ENG-AIRFUEL`、`STR-BODY-SAFETY`、`DISC-METHOD`、`FUN-ENG-LUBE`、`FUN-HV`、`FAIL-BRK`，每条不同独占文件；具体一次性触发词见 [#61 R9 dispatch](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6996741634)。**只是可领取任务，不能在没有 Claim/Commit 时计为运行或完成**。特别确认 `FAIL-BRK` 已在原独审 PLAN §4，现上游 FUN-BRK 获 ACCEPT，无需再虚构新的审核门禁。
4. **新增量计划已真实提交但尚未准入**：[DAG_DELTA_R9.md](./DAG_DELTA_R9.md) Commit `4bb1e482d0c7909ed5c765beaad5d788da1a70d4`、Blob `96bcd828aa18770b78ba9d27d9dea08a0576cfb1`；六条 `FUN-THERMAL`、`FUN-STEER-SUSP`、`FUN-LOWV`、`FUN-DRIVELINE`、`FAIL-CVT-FAMILY`、`FAIL-HEV-FAMILY` 只是 PROPOSED，需 [另一对话独审](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6996863590) 和 C-R9-DISPATCH 后才能 READY；原三个已审 PLAN Blob 未改变。
5. **真实进度**：知识 Markdown **22 GENERATED / 21 ACCEPT_SCOPED_GENERATION_ONLY / 1 GENERATED_REVIEW_PENDING**；范围不是整个汽修领域的完成率，所有缅甸 VIN/零件/OEM/N3 专业事实资格 0。Probox 润滑、Fit 制动两项依然 BLOCKED_SOURCE；无可靠频率数据时 `F=UNKNOWN`。继续保留至少一个结构广度 Worker，优先真正有增量的正文，不重复调度治理。

## 历史 R8 并行优先级（2026-11-19，已被 R9 覆盖）

1. **三个独立内容质量审核可并行**：[REP-AT](./topics/transmission/automatic/diagnostic-repair.md) Blob `2948cafc88693aa746520717068239a77d2c5d52`、[STR-THERMAL](./topics/thermal/structure.md) Blob `377ee9339949f39d916591f2ada300a59e3c72f7`、[FUN-BRK](./topics/braking/function.md) Blob `e5529c11339a5191de1ce46084923c8d38f88d7f`；三篇均真实 Commit/回读/Writer RELEASE，**不代表审核已执行**。
2. **通过的旧审核复用**：[HEV FUN R2](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6995879183)、[FAIL-AT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6995905451)、[STR-STEER-SUSP](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6995919397) 均独立限定质量 ACCEPT；旧 R1 HEV P1 REWORK 记录保留，当前有效是 R2 新 Blob。
3. **阶段里程碑**：传统 AT 已有 STR/FUN×2/FAIL 的独审链，REP 本轮已实际提交但仍需独审；ABS/ESC 已有 STR 独审、FUN 待审；热管理 STR 待审。当前共 **21 篇知识 Markdown 已生成、18 篇限定独立质量通过、3 篇待审**，正式 OEM/VIN/N3 事实 0。
4. **后续广度/深度**：`FUN-HV` 等旧已审 DAG 独占写集可另派；热管理 `FUN-THERMAL`、转向悬架 `FUN-STEER-SUSP`、制动 `FAIL-BRK` 未被当前已审计划授权，需要再做增量 DAG 计划/审核，不可倒填 READY。
5. **维修优先级**：缅甸车型无 VIN/变速箱号/电路/故障工单分母，模型只输出 UNKNOWN/条件化证据分类，不编造零件更换、油液/制动/HV 操作、故障发生率、售后真实结果。

## 最新 R7 优先队列（2026-11-19；覆盖后文旧 R6 快照）

- **三项可并发异对话审核**：`FUN-HEV-FAMILY` R2 Blob `f625c181d59471bfff80724583127099430c400c` 仅独审 i-DCD §2.2 的 P1 修复及必要影响；`FAIL-AT` Blob `042c8d6bb21c53b877a6cd36238d854044759307` 新源来源/因果机制内容审；`STR-STEER-SUSP` Blob `1c84e3329bfcb40bcc2a01dac1b6af15ef5bfb40` 广度内容审。必须有各自独立 Claim，避免同 Writer 自审。
- **已独立通过的三篇 FUN 不再重复**：[FUN-AT-PATH](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6989359346)、[FUN-AT-HYD](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6989338636)、[FUN-CVT-FAMILY](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6989372961)；无 P0/P1，原样 Blob 复用限定质量资格，不赋予 OEM 资格。
- **已提交并回读新 FAIL-AT**：[传统行星 AT 失效机制](./topics/transmission/automatic/failure.md) Commit `09a1babede4cde0e55747cd714f677dd20d38262`、Blob `042c8d6bb21c53b877a6cd36238d854044759307`；单症状保留机械/液压/控制/外部竞争解释，**REP-AT 暂不启动**直到本 FAIL 独审并满足专业资料限制。
- **新广度**：[STR-STEER-SUSP](./topics/steering-suspension/structure.md) Commit `4be9513c711b1afd6e2d52517e1750aa57b214e9`、Blob `1c84e3329bfcb40bcc2a01dac1b6af15ef5bfb40`；其它原有独立 `STR-THERMAL` 和 `FUN-BRK/FUN-HV` 仍可认领，不因 HEV 修复等待。
- **统计**：18 篇 Markdown 生成，15 篇限定独立内容质量 ACCEPT，3 篇待/重审，全部 OEM/VIN/N3 正式事实资格 0。通用/系列/共用家族三份已审 DAG 原 Blob 不修改，车型变型来源不足时保持 UNKNOWN。

## 最新优先队列（R6 / 2026-11-19；以下覆盖历史 R5 快照）

- **新共用家族结构已通过**：`STR-CVT-FAMILY@19201970...` 经 [独立 ACCEPT P2×2](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6988497818)；`STR-HEV-FAMILY@23baed76...` 经 [独立 ACCEPT P2×2](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6988518984)。原样 Blob 不重审。其各自的 `FUN-CVT-FAMILY@368e0e8f...`、`FUN-HEV-FAMILY@2196e745...` 已实际生成但质量待独审。
- **传统 AT 两篇功能新交付**：`FUN-AT-PATH` [Markdown](./topics/transmission/automatic/power-path.md) Commit `3b435b77deafec8041f8342c603f111b98563a42` / Blob `6c0a2855abf2751819ebcf1b039db05d8a953f71`；`FUN-AT-HYD` [Markdown](./topics/transmission/automatic/hydraulic-control.md) Commit `9ea1604d6ed0a2dc3d781e0728efefe476961058` / Blob `88338dbea91a278866ffb7ccca7d69b0f22c349e`。均 `GENERATED_REVIEW_PENDING`；两份可异对话并行审核。
- **总进度**：16 篇研究级知识 Markdown 真实生成，12 篇经其它对话限定质量 ACCEPT、4 篇待独审；所有专业 OEM/VIN/N3 事实资格 0，`FAIL-AT` 和 `REP-AT` 文件仍未生成。
- **广度并行**：原已审通用 DAG 的 `STR-STEER-SUSP`、`STR-THERMAL` 等可由不同 Worker 独立认领，不必等这四个功能审核；保持至少一个广度占位。车型 L4 匹配与另外两项 delta 继续 `BLOCKED_SOURCE`。
- **审核顺序**：先复用已审核的两条家族 STR，再对各自 FUN 提供最终内容判断；AT 的两个 FUN 审核互不依赖，完成后再考虑独立的 `FAIL-AT` 研究。

## 1. 两条队列，不为高价值深度牺牲整体覆盖

- **BREADTH**：车辆系统、总成、组件和正常功能未覆盖分支；按真实缺口选择，保证持续推进，不能为了追求某个高价值故障的无限深度而长期停滞。
- **DEPTH**：基于已交付工作原理及失效模式的有意义深入；按安全后果/诊断收益/维修误判代价/适用范围/证据可信度动态提高投入。
- 缺乏真实工单/保修/车辆分母时，所有特定故障发生频率均为 `F=UNKNOWN`；“很多人都听说过”不得换算成统计概率。优先级仅是**当前研究资源选择建议**，不是定量权威排名。
- 可并发 Worker ≥2 时保留至少一个 BREADTH 位置；新系统 STR 互相无全局屏障，不为下游某系统失效完成而等待。
- **资源实情**：本 Issue 评论派发的子任务不会自行在其它 ChatGPT 对话执行；只有真正启动并写回 GitHub Claim/Commit 的 Worker 才计进行中。

## 2. 已准入的第一批知识写集（四系统互相独立）

| Dispatch | Task | 唯一 Output .md | 调度理由（非故障频率） | F | 状态 |
|---|---|---|---|---|---|
| 1 | `STR-ENG-LUBE` | `topics/engine/lubrication/structure.md` | [独立质量 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6956153492)，P2×1 ISO 来源时效 | UNKNOWN | ACCEPT_SCOPED_GENERATION_ONLY |
| 2 | `STR-BRK` | `topics/braking/structure.md` | [独立内容质量 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6955581575)；安全架构 | UNKNOWN | ACCEPT_SCOPED_GENERATION_ONLY |
| 3 | `STR-HV` | `topics/electrified/high-voltage/structure.md` | [独立内容质量 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6955609189)；非操作性 | UNKNOWN | ACCEPT_SCOPED_GENERATION_ONLY |
| 4 | `STR-AT` | `topics/transmission/automatic/structure.md` | 传统液力行星 AT；[独立质量 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6955520356) | UNKNOWN | ACCEPT_SCOPED_GENERATION_ONLY |

**四条结构任务已真实生成并释放 Claim**；`STR-AT` 已获独立限定内容质量 `ACCEPT_SCOPED_GENERATION_ONLY`，其余 3 篇仍待审。所有专业事实都尚未获 OEM/N3 资格。每个 Writer 只修改自己的 topic 文件。下游功能/故障/维修知识只依自身真实已交付的前置并检查适用性，不等待其它系统。

## 3. 已释放的下游独立知识任务

`FUN-ENG-LUBE`：直接前置 `STR-ENG-LUBE` 已有 R2 Markdown Commit `69f7584ff242eb452d77ceacd70d08863f7d8579`、Blob `ff103f4cfd948534be5ca2b9413128aee502987f`；内容质量已限定 ACCEPT（P2 来源时效待后续维护），后续 Writer 仍应保留 `MODEL_GENERATED_UNVERIFIED` 并在上游 REWORK 时标记影响范围 `STALE`。下游可由其它对话按独占写集认领，不能把结构稿称为专业 OEM 已核实输入。

**此外**：`FUN-BRK` 与 `FUN-HV` 也各自具备独立质量接受的结构前置。 `FUN-AT-PATH` 与 `FUN-AT-HYD` 可并行研究（上游 `STR-AT@ed2b997c...` 已获限定内容质量 ACCEPT）；`FUN-BRK` 上游 `STR-BRK@e231eda...`；`FUN-HV` 上游 `STR-HV@472127e...`。任何上游独审若 REWORK，需把受影响下游标为 STALE 并重算前置。

四篇结构稿已获不同对话的限定内容质量 ACCEPT，可以各自启动 FUN；仍需各自保留 `MODEL_GENERATED_UNVERIFIED`、按真实来源进行车型适用性判断和未来有证据反例时局部回滚。

## 3A. 已合法准入并真实交付的共享家族（R5）

- [FAMILY 增量计划独立 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6984583673) Blob `58d616663c2262efa4fc62851d8962a637294703`，[Integrator C-FAM-DISPATCH](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6987899954) 已独立入场：Plan 通用 32 + Series 10 + Family 6 = 48 Task；新 4 篇 Markdown 写集独立，不改两个原已审 PLAN。
- **CVT**：[`STR`](./topics/transmission/cvt/structure.md) Blob `19201970db7bb121d28df02f1c862cd05765cea4`；[`FUN`](./topics/transmission/cvt/function.md) Blob `368e0e8fb644674df5262a3bad8f394a810db164`。都是实际 Writer 提交并 RELEASE，独立内容质量审 **0/2**。Honda Fit 2008 变矩器 CVT 与 Toyota 2018 Direct Shift-CVT 技术不可倒填 2014 Probox。
- **HEV**：[`STR`](./topics/electrified/hybrid/structure.md) Blob `23baed760bcf3dbb76cecfa609d8a7200532a8a9`；[`FUN`](./topics/electrified/hybrid/function.md) Blob `2196e74550b7d4b2f4ed4c0a09ed3f83db4bfa87`。都是实际 Writer 提交并 RELEASE，独立内容质量审 **0/2**。按 Honda 2010 IMA、2013 i-DCD、2020 e:HEV 不同版本；高压/制动是不可执行边界。
- **调度**：优先两个独立结构稿 Source-First 审核（可以并行）；其 FUN 在上游不 REWORK 时再按自己 Blob 独立增量审。如结构 REWORK，依赖 FUN 受影响范围需 STALE；不能一条链的审核代替另一条。
- **广度防饥饿**：继续保留 `STR-THERMAL / STR-STEER-SUSP` 等旧已审 PLAN 任务以及 `FUN-AT-PATH/FUN-AT-HYD/FUN-BRK` 的并行分发窗口，不因 CVT/HEV 四篇内容阻塞；完整 OEM/N3 资格依然 0。

## 缅甸在用车型系列双轴调度（R2）

- [SERIES R2 独立审核 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6959482030)、[SER-DISPATCH admitted](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6960479119)；批准的候选是 **Toyota Probox/Succeed 对照**与 **Honda Fit**，旧外部新车试点不恢复。
- `SER-DISC-PROBOX` 已交付 [Markdown](./series/myanmar/toyota/probox/discovery.md) · Blob `c8f011229a4e6fa6c66ae092a6f19a21142b4f19` · [独立内容质量 ACCEPT（P2×2）](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6962402777)。
- `SER-DISC-FIT` 已交付 [Markdown](./series/myanmar/honda/fit/discovery.md) · Blob `2c8ab39f67c076352586eed2a2f2187147fa909a` · [独立内容质量 ACCEPT（P2×3）](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6962478386)。
- 两篇均落实源资料与当地挂牌分账：CarMM 个别 listing URL/2026-11-18；缅甸市场报道是 2022 历史交易；RTAD 行政样本不是 stock census；实际缅甸保有量、故障率、具体 VIN 配置均 UNKNOWN。
- **本轮真实新产出**：Probox TRANS [Markdown](./series/myanmar/toyota/probox/transmission-applicability-delta.md) · Commit `b44c8fcd857df3a315322679734779b2f61a4a26` · Blob `2a0bfda60bc63ea484c45a6c0b01fe31f7db51a0`；Fit TRANS [Markdown](./series/myanmar/honda/fit/transmission-variants-delta.md) · Commit `80786eb8b1795751dc6295e77ab986a3e51d9a63` · Blob `a1a944399d2dd7dde3ce8e4be9bda06e94b431af`。两个 Writer 均已 RELEASE，且已分别取得 [Probox 限定内容质量 ACCEPT P2×2](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6976215650) 和 [Fit 限定内容质量 ACCEPT P2×3](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6976201311)；并非车型 OEM、VIN 或维修标准。
- **事件触发完成**：`SER-VARIANT-CHECK` [实际生成](./series/myanmar/series-variant-gaps.md) · Commit `b6ba674221c791c7223a54d9911060e1aca64466` · Blob `81f3733e3df4131a23c98043112e3839fdc0b6eb`；发现共用 CVT 和 HEV 家族知识候选。现上游两份 delta 均独审限定 ACCEPT，但 gap 自身仍 `GENERATED_REVIEW_PENDING`，需其他对话单独质量审查，后续有新反证仍须按影响范围 STALE。
- **不应启动**：`SER-DELTA-PROBOX-LUBE`、`SER-DELTA-FIT-BRK` 仍缺真正源码/适用版本，`SER-REPLAN` 已产出独立 [FAMILY_DAG_R1](./SERIES_FAMILY_DAG_R1.md) Blob `58d616663c2262efa4fc62851d8962a637294703`；新 `STR/FUN-CVT-FAMILY`、`STR/FUN-HEV-FAMILY` 已在独立计划审核和 C-FAM-DISPATCH 后**实际生成各自 Markdown**，均 `GENERATED_REVIEW_PENDING`，未获得各自内容质量 ACCEPT，不能冒充专业事实 READY。
- **下一轮优先**：两个 TRANS delta 已获得各自限定质量 ACCEPT；`SER-VARIANT-CHECK@81f3733e...`、`SERIES_FAMILY_DAG_R1@58d61666...` 和 `STR-LOWV@27520498...` 均已各自独立限定审核 ACCEPT，复用旧收据。现在优先并发审新四篇 CVT/HEV 家族 STR/FUN Exact Blob。原有 FUN-AT、FUN-BRK、FUN-HV 与其它广度仍可并行派发。
- **防饥饿**：STR-LOWV 已独立限定质量 ACCEPT；仍保留转向/热管理的广度 Writer 和 `FUN-AT-PATH`/`FUN-AT-HYD`/`FUN-BRK` 等通用深度 Writer 并行，不能因为新 series 就暂停旧主 DAG。
- **硬条件/可选对照 P2**：对 CVT/MT/DCT 的新子图不应把传统 AT STR 作强制先决；现行被独审接受的 R2 表不擅自改 Blob，下一次 C-REPLAN 必须按需要移除虚假 hard edge，并完整验证新图与增量审核。

## 4. 当前最高优先但延期的广度分支

| 候选 | 为什么值得下一轮启动 | 当前为何未认领 | 触发 |
|---|---|---|---|
| `STR-LOWV` | 已生成低压 ICE/BEV 结构及 CAN/LIN 网关 Markdown | [限定质量 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6984507844) P2×1 非阻断 | 后续 FUN-LOWV 只能经新受审 DAG 准入；不重复审核已过 Blob |
| `STR-STEER-SUSP` | 转向/悬架与轮胎影响安全和整车行为 | 非首批四个，尚无 Claim | 任意独立 Writer 资源空闲 |
| `STR-THERMAL` | ICE/BEV 温控与空调具有共享与差异，适合独立生成 | 尚无 Claim | 任意独立 Writer 资源空闲 |

其余按 [STRUCTURE-INDEX.md](./STRUCTURE-INDEX.md) 保持 OPEN；下一轮 C-REPLAN 从实际缺口选取新节点，防止四系统长期成为隐性全部汽修分母。

## 5. 当前门禁与异步/并发冲突处理

1. v0.4.1 PLAN 的精确审核已放行首批 **SCOPED GENERATION**；不是专业事实资格。
2. 认领和写入前须从 #61 重新读 Claims；Claim comment ID 数字最小者为同写集单 Writer 胜者；提交后还要再读检查。无合法 Claim 的 Writer 禁止写文件。
3. `create_file` 只允许目标文件当前不存在；若并发创建导致冲突要停下，不能无条件覆盖别人的文件。`update_file` 只能带最新 Blob SHA 并在提交失败时停下重读，不直接抢写。
4. C-REPLAN 每次修改当前 DAG 前，必须按全节点验证稳定 ID、所有依赖存在、无自环及整图拓扑无环，并记入当前 PLAN commit/Blob；不使用旧 32 节点证明为后续新版本背书。
5. 当前所有非计划内容即使生成并获质量限定审核，仍为 `MODEL_GENERATED_UNVERIFIED`。内容通过不自动授予 OEM/N3/正式专业诊断资格。
6. 此账本由 **Integrator/独占控制 Writer** 更新；系统 Writer 只负责自己的系统独占 Markdown 和 #61 任务收据。避免多个并行 Worker 争写此文件。

## 6. 真实收据

- 计划审核原文：https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6954464408
- Integrator C-DISPATCH 准入：https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6954548597
- 具体 Writer 认领及真实提交应在 #61 新评论中逐项记录；**没有真实提交前仍是 READY**。
