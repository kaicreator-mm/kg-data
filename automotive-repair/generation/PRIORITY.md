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
| 1 | `STR-ENG-LUBE` | `topics/engine/lubrication/structure.md` | 基础 ICE 系统，后续功能/润滑失效前置；真实提交 `74e8f3d` | UNKNOWN | GENERATED_REVIEW_PENDING |
| 2 | `STR-BRK` | `topics/braking/structure.md` | 制动安全关键，结构/功能知识具备跨架构解释价值；不写高风险操作 | UNKNOWN | READY_CLAIMABLE |
| 3 | `STR-HV` | `topics/electrified/high-voltage/structure.md` | BEV 高压安全与诊断基本机理，需严格 OEM 限定；不写高压操作程序 | UNKNOWN | READY_CLAIMABLE |
| 4 | `STR-AT` | `topics/transmission/automatic/structure.md` | 现存目录候选较多，易与 CVT/DCT/e-CVT 混淆，先固定**传统液力变矩器+行星齿轮+液压执行**结构范围 | UNKNOWN | READY_CLAIMABLE |

**四条 Writer 任务以真实 Claim 认领后为 `CLAIMED`**，这张调度表本身不能冒充认领或成果。每个 Writer 只修改自己的 topic 文件。下游功能/故障/维修知识只依自身真实已交付的前置并检查适用性，不等待其它系统。

## 3. 已释放的下游独立知识任务

`FUN-ENG-LUBE`：直接前置 `STR-ENG-LUBE` 已有真实 Markdown Commit `74e8f3d575471d16c3052c3003931da0daf73d7a`、Blob `b43057bee5ef1ee291e55ca5b3a7f8aee04a5e4e`；内容质量审核仍 PENDING，因此后续 Writer 应保留 `MODEL_GENERATED_UNVERIFIED` 并在上游 REWORK 时标记影响范围 `STALE`。下游可由其它对话按独占写集认领，不能把结构稿称为专业 OEM 已核实输入。

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
