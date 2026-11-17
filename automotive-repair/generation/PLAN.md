# 汽修知识生成 Task DAG — v0.4（结构 → 功能 → 失效 → 诊断维修）

> MAIN：[parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61)；数据仓：`kaicreator-mm/kg-data`；**本计划是未获独立计划审核的 Draft，非已生成/认证的知识**。
> 本版本根据 2026-11-17 Owner 对 R1“故障分析代替汽车知识体系”的纠偏编制；原 R1 可由 Git 历史提交 `cf6659b564843dff552944c8d04c8526518c44b7` 精确回访，先前 R1 Exact-BLOB 审核请求不适用于本修订版本。故障优先级方法原候选保留于 [FAULT_DRIVEN_DAG_R1.md](./FAULT_DRIVEN_DAG_R1.md)，其方法资格仍为候选。

## 1. 定义：结构树 ≠ 知识图 ≠ 执行 Task DAG

1. **结构覆盖图**：汽车（明确动力形式/车型适用范围）→ 系统 → 子系统 → 总成 → 组件；组件可以有多个别名、功能和跨系统引用；**不是要求每个组件生成固定 N 条**。
2. **知识关系图**：功能、工作原理、失效模式、故障现象、原因、后果、DTC、诊断证据、维修/维护判断；允许多对多、反馈和循环，**它本身不要求是 DAG**。
3. **任务执行 DAG**：为得到真实有意义 Markdown，管理“发现组成 → 说明功能 → 推导/研究失效 → 维修知识 → 补缺”，严格有向无环；只对真正需前置内容的生成任务设置阻塞。
4. **调度优先级**：决定 READY 任务的顺序、深度和生成预算，不凭空把优先级关系写作知识依赖。

## 2. 覆盖基线与范围

单一领域：**汽车维修与诊断**。不预设某一品牌、车型、年款或市场为全部领域；总控先区分汽油/柴油、HEV/PHEV、BEV、其它实际车辆架构，明确 `APPLICABLE/NOT_APPLICABLE/UNKNOWN`。首轮可从资料丰富的乘用车/轻型车专题起步，但**这不构成整体汽修完成**。

参考专业结构（仅为发现遗漏的可修订初始索引，而非分类配额）：发动机与其辅助系统、供气供油与排放、传动与驱动、制动、转向悬架/车轮轮胎、电气电子及车载通信、空调与热管理、车身/被动安全、混动/纯电高压与充电、跨系统诊断、周期维护/耗材与维修通用技术。按真实构型发现新增/合并/不适用节点，不机械填空。

**权威参考各司其职**：
- ASE A1–A9（https://ase.com/tests/a1-a9/）：维修专业/任务的遗漏检查，非车辆全部结构的唯一分类标准。
- OEM 原始维修手册/零件目录及明确合法可用的技术资料：具体车型的系统/总成分解与维修适用性；没有授权或未读正文时不声称已知具体车型事实。
- AIAG/VDA FMEA（https://www.aiag.org/docs/default-source/quality-/new_aiag_vda_fmea_-whitepaper.pdf）：参考“结构 → 功能 → 失效”的思考方法；不把设计制造风险表直接等同真实维修故障概率。
- SAE J2012（https://saemobilus.sae.org/standards/j2012_202509-diagnostic-trouble-code-definitions）：DTC 辅助关联；故障码不等于故障根因。
- Drive Books 真实可见目录和 `kg-data/books/` 旧生成候选：只作主题线索（TOC_ONLY / MODEL_GENERATED_UNVERIFIED），不冒充已读正文或独立事实证据。

## 3. 分层发现与知识生成协议

- **M0 范围与结构发现**：明确汽车架构、系统/子系统/部件/总成、共享部件、跨系统关系及已知缺口；以小批次逐层展开。
- **M1 功能与工作机理**：每个重要结构节点回答“是什么、为什么存在、如何与上下游协同、在什么条件下工作”；内容复杂度自然决定粒度。
- **M2 失效模式与故障**：按功能失效而非先按主诉构造原因；记录可能失效方式、诱发条件、可观察症状、非一一对应的 DTC；不把共因重复写成多份百科。
- **M3 诊断、维修和维护知识**：围绕机理与实际维修问题生成可理解的鉴别思路、维修决策、误诊代价、维护原理和适用条件。安全关键操作没有车型/资质依据时不得成为通用可执行步骤。
- **M4 动态补缺**：检测结构遗漏、功能空白、故障漏项、重复/矛盾及跨系统关联；有增量才增加或拆分任务；反复触发而非最后一次性写报告。

以上是**生成能力**，不是要求每个部件都产出 5 篇固定文章。已有共享功能机理，故障分支可引用，无需重写。当前**只交付原生 Markdown**；不做 LinkML/YAML/JSON-LD/CSV、正式独立专业事实认证或生产数据库接入。

## 4. 执行 DAG（控制任务）

| ID | 任务与具体完成条件 | 前置 | 状态 |
|---|---|---|---|
| `C-SCOPE` | 明确车辆/动力架构、资料与已知边界，区分真实来源/目录/模型假设；写入 Markdown 范围与差异 | 无 | DRAFT |
| `C-STRUCT` | 列出首轮有实际根据的系统与跨系统关联，给出各结构分支继续向下发现的策略，不称全领域已覆盖 | C-SCOPE | DRAFT |
| `C-COVERAGE` | 建立 Markdown 覆盖台账（结构/功能/失效/维修各自状态、UNKNOWN、NOT_APPLICABLE、来源范围），不是固定配额表 | C-STRUCT | PLANNED |
| `C-PRIORITY` | 为已发现任务提供安全优先/维修价值/频率/诊断难度/适用范围/缺口/证据可信度；UNKNOWN 保留，给出当前选择理由 | C-STRUCT | PLANNED |
| `C-PLAN-REVIEW` | 另一对话检查 R2 计划结构、无环依赖、真实任务/写集、无固定配额、是否可执行；不等同专业事实认证 | C-STRUCT | NEEDS_REVIEW |
| `C-DISPATCH` | 审阅有效后，从真实 READY 节点选择不同写集任务；每次按当前 GitHub HEAD/Claim 动态重选 | C-PLAN-REVIEW | BLOCKED_BY_REVIEW |
| `C-REPLAN` | 从每批生成结果中发现具体缺口与非重复增量；只修改未认领 DAG 节点 | 任一 GENERATED | WAITING |
| `C-CLOSEOUT` | 报告已探索的实际系统边界、文章与机制/故障链、剩余缺口、生成质量/成本，而不是宣称所有汽车知识已覆盖 | 实际完成一轮广度+深度和回顾 | WAITING |

`C-COVERAGE` 和 `C-PRIORITY` 可以在结构已知后并行；两者**不得通过没有统计数据的伪概率阻塞基础结构/功能任务**。

## 5. 首批领域任务 DAG（有真实输出目标，不是固定分区配额）

> **样本工作包，用于测试新方法能否从结构逐步得到有用维修知识。** 并非只研究四个系统，更不是把四系统设为汽修总分母。所有 GEN 节点目前 `PLANNED/NEEDS_REVIEW`，**没有一篇 v0.4 正文被宣称已生成**。

| Task ID | 具体知识问题及实际 Markdown | 真正前置 | 后续价值 |
|---|---|---|---|
| `STR-ENG-LUBE` | 发动机润滑系统由哪些实际部件和油路构成，如何与其它系统交互？`topics/engine/lubrication/structure.md` | C-STRUCT | 结构广度；功能基础 |
| `FUN-ENG-LUBE` | 机油循环、泵送、滤清、调压、温度/流量/压力如何作用？`topics/engine/lubrication/function.md` | STR-ENG-LUBE | 机理基础 |
| `FAIL-ENG-LUBE` | 润滑不足或压力异常可能有哪些失效模式、来源及症状？`topics/engine/lubrication/failure.md` | FUN-ENG-LUBE | 维修价值候选，安全后果 |
| `REP-ENG-LUBE` | 如何区分泵、油路、传感器、轴承间隙等竞争解释及维修判断边界？`topics/engine/lubrication/diagnostic-repair.md` | FAIL-ENG-LUBE | 诊断深度 |
| `STR-AT` | 自动变速器包含哪些结构与关键变型，何种车型/结构才适用？`topics/transmission/automatic/structure.md` | C-STRUCT | 复用历史 AT 研究候选 |
| `FUN-AT-PATH` | 传动比、动力路径、行星机构/离合器如何形成不同挡位？`topics/transmission/automatic/power-path.md` | STR-AT | 与液压功能可并行 |
| `FUN-AT-HYD` | 油泵、油压、阀体、执行元件在控制中的作用及边界？`topics/transmission/automatic/hydraulic-control.md` | STR-AT | 与动力路径可并行 |
| `FAIL-AT` | 换挡冲击/打滑/迟滞可由何种机械、液压、电控原因造成？`topics/transmission/automatic/failure.md` | FUN-AT-PATH, FUN-AT-HYD | 复杂故障候选 |
| `REP-AT` | 同样换挡现象如何根据工况与证据鉴别、避免误换件？`topics/transmission/automatic/diagnostic-repair.md` | FAIL-AT | 深度生成 |
| `STR-BRK` | 行车制动、液压、ABS/ESC 等结构如何分工并协同？`topics/braking/structure.md` | C-STRUCT | 安全关键优先 |
| `FUN-BRK` | 常规制动力、液压传递、ABS 干预的工作条件是什么？`topics/braking/function.md` | STR-BRK | 机理基础 |
| `FAIL-BRK` | 制动效果不足、异常拖滞、ABS 报警有哪些不同失效机理？`topics/braking/failure.md` | FUN-BRK | 安全关键 |
| `STR-HV` | HEV/PHEV/BEV 高压电池、电驱、充电及保护结构有哪些架构差异？`topics/electrified/high-voltage/structure.md` | C-STRUCT | 风险边界；非操作说明 |
| `FUN-HV` | 高压配电、隔离监测、互锁、热管理等保护机理的原理与边界？`topics/electrified/high-voltage/function.md` | STR-HV | 非执行性安全说明 |
| `FAIL-HV` | 绝缘或互锁异常如何形成风险及诊断信号，哪些必须保留 OEM/专业资质条件？`topics/electrified/high-voltage/failure.md` | FUN-HV | 安全关键；禁止无证操作步骤 |

**调度图（真实阻塞边）**：
```text
C-SCOPE -> C-STRUCT -> C-PLAN-REVIEW -> C-DISPATCH
                    +-> C-COVERAGE
                    +-> C-PRIORITY

C-DISPATCH -> STR-ENG-LUBE -> FUN-ENG-LUBE -> FAIL-ENG-LUBE -> REP-ENG-LUBE
           -> STR-AT -> FUN-AT-PATH --+
                    -> FUN-AT-HYD  --+-> FAIL-AT -> REP-AT
           -> STR-BRK -> FUN-BRK -> FAIL-BRK
           -> STR-HV  -> FUN-HV  -> FAIL-HV

任一生成节点 -> C-REPLAN -> 下一批具体新 Task（不回连已完成节点）
```
这是**先行小样本**，下批必须从整车系统/组件覆盖表发现遗漏并创建任务，不能一直只写这四个系统。故障影响、维修价值和选择优先级是动态属性，**不能改变知识任务真实依赖**。

## 6. 故障常见性与维修价值的调度规范

- 不用单一“故障码数量/网页搜索热度/投诉数/TSB条数”冒充故障发生率。
- 频率 `F`（车型、年款、里程、地区、时间窗及来源分母）优先依据真实维修工单/保修/车队样本；没有分母时标 `UNKNOWN`。
- 维修价值 `V` 包括误诊返工/更换成本、停驶损失、诊断信息收益；风险 `S` 单列且不能被低 F 抵消；加考虑 `D` 诊断难度、`B` 适用范围、`G` 内容缺口、`C` 证据可信度。
- **安全关键**：优先生成风险识别与机理说明，不提供无车型/资质约束的高危维修可执行步骤。**高维修价值**：更多机制分支、反例、判断依据和迭代。**普通**：有实质内容即可收敛。**未知**：探索性任务，不因无 F 数据而永久阻塞。
- 广度底线：按已定义车型架构/覆盖边界逐步补全重要系统/组件及其功能；深度优先不会将其它结构长期遗忘。每次调度报告尚未覆盖的结构缺口和下一分支。
- **无硬性数量配额**：不强制每系统几篇、每零件几条、每故障几个子节点；用“是否回答关键专业问题、存在什么仍未解释的知识”决定继续或停止。

## 7. Writer 交付规则（Markdown-only）

每篇文章自然组织，不强制知识类型标题，但必须有：任务 ID、具体要回答的问题、涉及的车型/系统范围及可见输入来源标识（`TOC_ONLY|BOOK_BODY|OFFICIAL|MODEL` 按实际情况）、专业知识正文、必要条件与限制、仍需研究的问题、`MODEL_GENERATED_UNVERIFIED` 声明。
专业内容应解释工作机理/失效因果/条件差异，避免空标题、同义重写、虚构 OEM 限值、将目录当书籍正文。引用来源仅引用真实可见的资料及最小定位；资料读取范围不明时标 UNKNOWN。

以 GitHub Issue #61 认领，**同一文件同一时刻一个 Writer**；所有任务由新对话/Agent 均可接手，不能要求回到原对话。提交并 fetch-file 回读成功后再报 `GENERATED_REVIEW_PENDING`，不得自行宣布专业 FACT_VERIFIED/N3。其他对话审核生成质量（深度/重复/边界/文件有效性）后，才可 `ACCEPT_SCOPED_GENERATION_ONLY`。这不是专业来源事实审核。

## 8. DAG 再规划停止条件

- 如果新增子问题与现存文章实质重复、专业价值低或缺少可生成信息，记录 `DEFERRED/UNKNOWN` 而不是无限创建任务。
- 如果相同维修机理跨多症状共享，应归入共享基础知识任务并引用；保留一般知识图中的循环反馈关系，执行 Task DAG 仍保持无环。
- 如果完成后仍有实际系统/部件遗漏，继续广度覆盖；若高价值故障存在证据和原理缺口，安排深度任务。
- 计划不是“汽修全域已完成”证明。阶段性收尾只陈述具体覆盖范围、生成内容、未验证状态及下一阶段可行性。

**当前状态：v0.4 PLAN/DAG 已编写候选，独立计划审核、首批知识正文生成、专业事实验证均 NOT_RUN。**
