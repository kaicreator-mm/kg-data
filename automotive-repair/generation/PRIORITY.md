# 汽修知识生成动态优先级与并行调度 — R1

> MAIN: [parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) | PLAN: [v0.4.1](./PLAN.md) | 状态: `C-PRIORITY_DRAFT_R1`
> 计划入场：独立审核 [ACCEPT_SCOPED_PLAN_READY](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6954464408)，按 Blob `1df1f116a9f4e1effc46840aa4ec57be1289b6cf` 限定。详见 [C-DISPATCH Admission](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6954548597)。

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

## 缅甸在用车型系列双轴调度（R2）

- [SERIES R2 独立审核 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6959482030)、[SER-DISPATCH admitted](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6960479119)；批准的候选是 **Toyota Probox/Succeed 对照**与 **Honda Fit**，旧外部新车试点不恢复。
- `SER-DISC-PROBOX` 已真实交付 [Markdown](./series/myanmar/toyota/probox/discovery.md) · Commit `a248b9ae9cf2d8ee6d89be52435e153e3784c2aa` · Blob `c8f011229a4e6fa6c66ae092a6f19a21142b4f19`；`GENERATED_REVIEW_PENDING`。
- `SER-DISC-FIT` 已真实交付 [Markdown](./series/myanmar/honda/fit/discovery.md) · Commit `fc9308d352b0dd8273549bd86ef260e90ec5cc4e` · Blob `2c8ab39f67c076352586eed2a2f2187147fa909a`；`GENERATED_REVIEW_PENDING`。
- 两篇均落实源资料与当地挂牌分账：CarMM 个别 listing URL/2026-11-18；缅甸市场报道是 2022 历史交易；RTAD 行政样本不是 stock census；实际缅甸保有量、故障率、具体 VIN 配置均 UNKNOWN。
- **优先下轮任务（需要不同非 Writer 对话）：** 两篇 SERIES_DISC_CONTENT_REVIEW 可完全并行。只在质量审核通过且已有可证实的构型差异时，可按 PLAN 与 Claim 启动 `SER-DELTA-PROBOX-TRANS` / `SER-DELTA-FIT-TRANS` 两个候选；润滑和制动差量当前仍 `CONDITIONAL/SOURCE_GAP`，不灌水。
- **防饥饿**：仍保留 `STR-LOWV`/转向/热管理的广度 Writer 和 `FUN-AT-PATH`/`FUN-AT-HYD`/`FUN-BRK` 等通用深度 Writer 并行，不能因为新 series 就暂停旧主 DAG。
- **硬条件/可选对照 P2**：对 CVT/MT/DCT 的新子图不应把传统 AT STR 作强制先决；现行被独审接受的 R2 表不擅自改 Blob，下一次 C-REPLAN 必须按需要移除虚假 hard edge，并完整验证新图与增量审核。

## 4. 当前最高优先但延期的广度分支

| 候选 | 为什么值得下一轮启动 | 当前为何未认领 | 触发 |
|---|---|---|---|
| `STR-LOWV` | 低压供电、起动/充电、控制器通信是多个故障场景的通用知识前置 | 首次仅派出四个试点系统；不是低价值 | 新 Writer 资源空闲即可从 COVERAGE 的 OPEN 认领 |
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
