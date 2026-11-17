# 汽修知识生成 Task DAG — v0.4.1 并行重构 / R1 REWORK 修复稿

> MAIN：[parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) | 数据仓：`kaicreator-mm/kg-data`。
> **状态：`REWORK_DELIVERED__INDEPENDENT_DELTA_REVIEW_PENDING`**。本稿根据 v0.4 `38e3a89b1abaa88d46df47fb09d9ce99572c8a10` 独立审核 `REWORK (P1×3,P2×3)` 修订，不得把审核完成误认为 PASS。**仍无 v0.4+ 专业知识正文生成，不放行 GEN，直到 v0.4.1 PLAN 获另一个对话独立增量 ACCEPT_SCOPED_PLAN_READY。**

## 1. 一领域、三张图、两个可并行维度

领域：**汽车维修与诊断**。当前仅第一阶段：生成原创知识 Markdown `.md`；不产 LinkML/YAML/JSON-LD/CSV，不代签 OEM/专业 Source-First 事实认证或正式 N3。

- **结构覆盖索引**：按已声明车辆架构，探索系统→子系统→总成→部件及跨系统引用；目的是防遗漏，不是强制文章配额。
- **知识关联网络**：结构、功能、工作机理、失效模式、原因、现象、诊断证据、维修判断之间多对多，可包含反馈循环。
- **执行 Task DAG**：控制真实任务依赖，**只在任务需要某个已交付的知识前置时设阻塞边**；跨系统多个 STR 可以并行，系统内已满足前置的 FUN/FAIL/REP 流水线并行，不等待其他系统的全部 STR/FUN/FAIL 完成。
- **BREADTH 广度**：持续从覆盖账本发现未解释的系统和部件；**DEPTH 深度**：依安全、维修价值、复杂度和未解问题增加机制/诊断分支。优先级不改写真实知识依赖。
- 所有专业知识仍默认 `MODEL_GENERATED_UNVERIFIED`，真实生成/内容质量审核和专业事实资格分别记账。

## 2. 本轮范围与控制工件（修复 P1-02）

| 控制工件 | 路径 | 当前状态与边界 |
|---|---|---|
| `C-SCOPE` | [SCOPE.md](./SCOPE.md) | `DRAFT_DELIVERED`：限定 `ARCH-ICE-GAS-LIGHT` 通用汽油乘用轻型车和 `ARCH-BEV-LIGHT` 通用纯电轻型车。**传统液力行星齿轮 AT 仅适用于前者的一个变速器子型**。不是任何具体 OEM 车型的认证或整车完备范围 |
| `C-STRUCT` | [STRUCTURE-INDEX.md](./STRUCTURE-INDEX.md) | `DRAFT_DELIVERED`：有真实研究问题的初始系统覆盖索引、跨系统关系和下一批结构发现分支（不是已验证整车部件数据库） |
| `C-COVERAGE` | [COVERAGE.md](./COVERAGE.md) | `DRAFT_INITIALIZED`：结构/功能/失效/诊断四视角，全部未生成均 OPEN；缺少材料 UNKNOWN；切片外 OUT_OF_INITIAL_SLICE（不能误当 N/A） |
| `C-PRIORITY` | `PRIORITY.md`（由 Controller 更新） | `PLANNED`：真实有证据的安全优先、诊断/维修收益、频率 UNKNOWN、广度防饥饿及本轮调度理由；不能依靠伪频率阻塞 STR |

**范围不是最终车型/系统全集**。 `C-SCOPE` 和 `C-STRUCT` 的初稿经真实 GitHub commit 和回读后可作为本次计划独审的输入；**不需要先完成专业知识内容或专业事实审核，计划独审才能运行**。

行业组织参考：ASE A1–A9 检查维修专业遗漏、OEM 维修手册/零件目录用于特定车型适用性、AIAG/VDA FMEA 的结构→功能→失效作为思考方式、SAE J2012 DTC 仅作为关联索引；Drive Books 可见目录和既往 `kg-data/books` 模型候选只用于线索，不冒充未读取书籍正文。

## 3. 控制 DAG 与生效门禁（修复 P1-01）

| ID | 任务、验收与文件写集 | 真实前置 | 状态 |
|---|---|---|---|
| `C-SCOPE` | 声明架构切片、适用/不适用/未知、真实来源范围；`SCOPE.md` 可回读 | 无 | DRAFT_DELIVERED |
| `C-STRUCT` | 结构发现种子、系统未覆盖分支与跨架构关系；`STRUCTURE-INDEX.md` 可回读 | C-SCOPE DRAFT_DELIVERED | DRAFT_DELIVERED |
| `C-COVERAGE` | 初始化四视角全部 OPEN 的真实缺口账本、每轮新增遗漏分支和任务理由；`COVERAGE.md` | C-STRUCT DRAFT_DELIVERED | DRAFT_INITIALIZED |
| `C-PRIORITY` | 记录证据可信度/风险/价值/广度选择和被延期的最高重要 OPEN 分支；`PRIORITY.md` | C-STRUCT DRAFT_DELIVERED | PLANNED |
| `C-PLAN-REVIEW` | **审阅当前 v0.4.1 计划草稿及已交付的 Scope/Index/Coverage 草稿**，检查前置/并行/输出/AT 适用性/验收；写回 #61 | 当前 v0.4.1 PLAN Blob 与本轮文档草稿均可回读（**不需要 C-SCOPE/C-STRUCT 最终专业认定**） | **READY_FOR_INDEPENDENT_DELTA_REVIEW** |
| `C-DISPATCH` | 根据无冲突 Claim/写集和真实前置分发 GEN，记入 #61 / `PRIORITY.md` | `C-PLAN-REVIEW=ACCEPT_SCOPED_PLAN_READY` **且** SCOPE、STRUCTURE-INDEX、COVERAGE 当前文件可回读 | BLOCKED_BY_REVIEW |
| `C-REPLAN` | 按真实新文件与缺口变化追加下批独立 Task，分派下个广度分支；只改未认领任务 | 任一真实 GENERATE 完成 | WAITING |
| `C-CLOSEOUT` | 只报告已覆盖切片和内容、剩余结构/功能/故障/维修缺口、耗费和未验证状态 | 实际完成一轮 BREADTH + DEPTH + REPLAN | WAITING |

**硬门禁 `GATE-V041`：所有 `STR-*/FUN-*/FAIL-*/REP-*/DISC-METHOD` 知识生成节点，均显式依赖 `C-DISPATCH` 的合法完成。它不是隐含口头规定；表、下方图及 #61 主 Issue 一致。** 此门禁只放在知识生成入口，不把每个系统的深度任务强迫等待其他系统。

`C-COVERAGE` 与 `C-PRIORITY` 可在计划审查进行期间并行维护草稿/待调度候选；**不能**因它们尚无概率统计而阻塞已经合法 READY 的基础结构工作。任何 Writer 在未获得有效本版本计划审查前不得生成正文。

## 4. 首批可分派并行系统与真实依赖（修复 P1-03、P2-01/02）

下面每个 `STR/FUN/FAIL/REP` 的**完整有效前置**均为：`C-DISPATCH` **AND** 表中列明的直接知识前置。任何直接知识前置没生成真实 Markdown，则下游不可按完成认领；可在不同系统无冲突的情况下继续其他 READY 节点。

| Task | 要生成的明确专业问题 | 直接知识前置 | 唯一 Markdown 输出 | 语义完成证据（不强求字数/条数） |
|---|---|---|---|---|
| `STR-ENG-LUBE` | ICE 发动机润滑系统由何组成，与冷却/传感如何协作？ | 无 | `topics/engine/lubrication/structure.md` | 说明基本构成、油路/接口关系、典型结构差异与未知 |
| `FUN-ENG-LUBE` | 油泵、滤清、调压、润滑支路如何形成流量/压力/润滑？ | STR-ENG-LUBE | `topics/engine/lubrication/function.md` | 输入→机理→输出、工况/温度/间隙适用前提 |
| `FAIL-ENG-LUBE` | 润滑不足/压力异常有哪些有物理解释的失效模式？ | FUN-ENG-LUBE | `topics/engine/lubrication/failure.md` | 原因→物理作用→结果/症状，区别不同原因，反例 |
| `REP-ENG-LUBE` | 如何解释与区分泵、油路、传感器、轴承间隙等竞争故障？ | FAIL-ENG-LUBE | `topics/engine/lubrication/diagnostic-repair.md` | 诊断证据的区分价值、误判、适用/不可判定边界 |
| `STR-AT` | **仅传统液力变矩器+行星齿轮+液压执行 AT** 的结构、控制与适用条件是什么？CVT/DCT/e-CVT 如何区别？ | 无 | `topics/transmission/automatic/structure.md` | 明确上述 AT 结构及 excluded 技术差异，不能泛化所有 AT |
| `FUN-AT-PATH` | 对**上述传统行星齿轮 AT**，动力路径、离合器/制动器如何形成挡位？ | STR-AT | `topics/transmission/automatic/power-path.md` | 输入/保持/结合→传动状态→转矩/速度、工况边界 |
| `FUN-AT-HYD` | 对**上述液压执行 AT**，油泵、油路/阀体、执行器及电控阀如何协同？ | STR-AT | `topics/transmission/automatic/hydraulic-control.md` | 压力/流量→作用→输出与调压/泄漏/温度边界 |
| `FAIL-AT` | **仅此传统液压行星 AT** 换挡冲击、打滑、迟滞的不同失效机理？ | FUN-AT-PATH, FUN-AT-HYD | `topics/transmission/automatic/failure.md` | 机械/液压/电控候选因果链与鉴别信息，不推及 DCT/CVT/e-CVT |
| `REP-AT` | **仅此 AT** 如何从不同证据区分失效及误修后果？ | FAIL-AT | `topics/transmission/automatic/diagnostic-repair.md` | 各竞争原因对应证据与反例、OEM 版次/不可判定边界 |
| `STR-BRK` | 通用摩擦制动、助力、液压与 ABS/ESC 如何分工？BEV 再生制动何时另设条件？ | 无 | `topics/braking/structure.md` | 结构组成/交互/架构分界，不虚构通用部件清单即所有车型 |
| `FUN-BRK` | 液压制动力、摩擦转化、ABS 防抱死反馈如何运作？ | STR-BRK | `topics/braking/function.md` | 正常机理、工况、控制/机械边界 |
| `FAIL-BRK` | 制动效果不足、异常拖滞、报警有哪些不同的可能失效？ | FUN-BRK | `topics/braking/failure.md` | 失效→影响→可见症状与反例、安全风险 |
| `REP-BRK` | 如何认知制动异常的竞争原因、危险信号与停用/专业检修边界？ | FAIL-BRK | `topics/braking/diagnostic-repair.md` | 非可执行诊断证据选择、误判/风险，**无 OEM 指令时不生成具体危险操作步骤** |
| `STR-HV` | **仅通用 BEV 概念切片**的电池包/配电/电驱/充电/保护构成？HEV/PHEV 架构如何不同？ | 无 | `topics/electrified/high-voltage/structure.md` | 高压结构及工况/拓扑条件，清楚排除其它架构泛化 |
| `FUN-HV` | BEV 高压配电、隔离/互锁、热管理与充电的正常保护机理？ | STR-HV | `topics/electrified/high-voltage/function.md` | 输入→保护/反馈→结果与边界；非操作说明 |
| `FAIL-HV` | BEV 绝缘/互锁异常有什么机理、现象、风险与未知？ | FUN-HV | `topics/electrified/high-voltage/failure.md` | 区分原因与观测、风险/来源限制，非具体维修程序 |
| `REP-HV` | 如何理解 BEV 高压故障的非可执行鉴别信息、危险信号与专业移交条件？ | FAIL-HV | `topics/electrified/high-voltage/diagnostic-repair.md` | 风险解释、判断禁区、OEM/技能必要条件，**不含无资质高压操作步骤** |

**系统间并行**：
- 只要有效 `C-DISPATCH`，`STR-ENG-LUBE / STR-AT / STR-BRK / STR-HV` 可**四 Worker 并发**，各自唯一 Markdown 输出。
- `STR-AT` 生成并回读后，`FUN-AT-PATH` 与 `FUN-AT-HYD` 可**两 Worker 并发**。
- `STR-ENG-LUBE` 完成即可单独释放 `FUN-ENG-LUBE`，不等待其余系统。
- `STR-BRK` 与 `STR-HV` 同理可在其它系统未完成的情况下向各自 FUN 推进。
- 生成阶段下游可基于**真实已交付且明确 UNVERIFIED**的 Markdown（`GENERATED_REVIEW_PENDING`）开展进一步非操作性研究；高安全风险或发现明显矛盾时先通过相应内容质量限定审查并按 REWORK 修复；后续任一上游更正，应记录相关下游 `STALE` 并增量修复，禁止装作无影响。

## 5. 广度扩张 Task 池（P1-02/P2-03 防四分支锁死）

以上四系统是**试行批次**。首批通过 GATE 后可在调度器资源允许时**与四条试行分支同期开启**以下不同路径的系统结构发现；前提仍是唯一 Writer Claim 与本轮真实可见来源，**不等待首批四系统完成**：

| 候选结构 Task | 研究问题 | 独立 Markdown 输出 | 依赖 |
|---|---|---|---|
| `STR-ENG-AIRFUEL` | 汽油机进气/喷射/点火/排气后处理与发动机控制构成？ | `topics/engine/air-fuel-emissions/structure.md` | C-DISPATCH |
| `STR-DRIVELINE` | 传动轴/差速器/半轴/驱动接头的基本结构与适用边界？ | `topics/driveline/structure.md` | C-DISPATCH |
| `STR-STEER-SUSP` | 转向助力/悬架/车轮轮胎怎样构成并关联？ | `topics/steering-suspension/structure.md` | C-DISPATCH |
| `STR-LOWV` | 低压供电/起动充电/控制器/车内网络怎样构成（按 ICE/BEV 分别注明）？ | `topics/electrical-low-voltage/structure.md` | C-DISPATCH |
| `STR-THERMAL` | ICE/BEV 的冷却、空调、热管理各有何结构差异？ | `topics/thermal/structure.md` | C-DISPATCH |
| `STR-BODY-SAFETY` | 车身电气、照明、车身控制、约束/气囊系统的安全边界？ | `topics/body-safety/structure.md` | C-DISPATCH |
| `DISC-METHOD` | 跨系统维修证据、诊断认知、维护原则与测量误差的共用基础？ | `topics/common/diagnostic-methods.md` | C-DISPATCH |

这些是**具体 READY 候选**，实际激活前核查真实输入和重复，按需要建立深入 FUN/FAIL/REP 后继；不按“必须完成 N 个系统”计功。不确定车型构造时先限制到说明可见的一般机理，不假装有 OEM 数据。

每轮 Controller 维护 `COVERAGE.md`：至少列出尚未生成的重要 OPEN 系统分支（若没有真实证据，列 UNKNOWN）、本轮 BREADTH/DEPTH 选择依据、**被延期的最高优先未覆盖候选及下次启动触发**。只要架构切片内存在能安全深入且有价值的结构缺口，长期连续深度任务不能剥夺所有广度位置；至少保留一个可用的广度 Worker 槽位（在可并发资源≥2时）。这是防饥饿**调度规则**，不是文章数量指标。

## 6. 可执行调度图（图与逐节点表一致）

```text
C-SCOPE [SCOPE.md DRAFT_DELIVERED] -> C-STRUCT [STRUCTURE-INDEX.md DRAFT_DELIVERED]
                                            +-> C-COVERAGE [COVERAGE.md DRAFT]
                                            +-> C-PRIORITY [PRIORITY.md planned]
v0.4.1 PLAN + 当前 Scope/Structure/Coverage 草稿可回读
    -> C-PLAN-REVIEW [跨对话对新 Blob 增量审核]
    -> C-DISPATCH [仅在 ACCEPT_SCOPED_PLAN_READY 且 Scope/Struct/Coverage 可回读后]
          | (GATE-V041 是**每一个**知识 GEN Task 的有效前置)
          +---> STR-ENG-LUBE -> FUN-ENG-LUBE -> FAIL-ENG-LUBE -> REP-ENG-LUBE
          +---> STR-AT ->+-> FUN-AT-PATH ---+
                        +-> FUN-AT-HYD  ---+-> FAIL-AT -> REP-AT
          +---> STR-BRK -> FUN-BRK -> FAIL-BRK -> REP-BRK
          +---> STR-HV  -> FUN-HV  -> FAIL-HV  -> REP-HV
          +---> STR-ENG-AIRFUEL / STR-DRIVELINE / STR-STEER-SUSP /
                 STR-LOWV / STR-THERMAL / STR-BODY-SAFETY / DISC-METHOD
任意已实际 GENERATED 的独立任务 -> C-REPLAN -> 新版本未认领 Task
```

**有效依赖表达**：图上从 C-DISPATCH 发出的 GATE-V041 分叉对每个节点强制生效（不只是 STR），而中间的 `STR→FUN→FAIL→REP` 是直接知识依赖。没有从“其他系统完成”到当前系统下游的全局边。

## 7. 语义验收、状态与真实证据（P2-01）

- `PLAN_READY`：新的 v0.4.1 Blob 独立审查通过；入口条件、真实输出路径、唯一写集和任务前置一致，范围可核对，不把结构探索候选误认为已验证 OEM 结构。
- `GENERATED_REVIEW_PENDING`：Writer 在唯一写集产出高信息密度 `.md`，真实 GitHub commit/fetch-file 对应 Blob，说明任务 ID、具体问题、来源可见性（`TOC_ONLY|BOOK_BODY|OFFICIAL|MODEL` 按真实情况）、适用边界、工作原理/因果与竞争解释的实际内容、缺口/UNKNOWN、`MODEL_GENERATED_UNVERIFIED`。不是空标题、重复套话、模型编造页码/限值或无依据“通用安全实操步骤”。
- `ACCEPT_SCOPED_GENERATION_ONLY`：另一对话只审当前 Exact SHA 的生成质量（问题回答、深度、去重、边界、显著矛盾），不能变成 OEM/专业事实认证。
- `DEFERRED/UNKNOWN`：没有可靠模型/OEM 适用条件时可对某些细节拒绝编造，**不能因 UNKNOWN 就宣布整篇专业知识已完整**。
- STR/FUN/FAIL/REP 每节点语义验收见上表；不得强制固定字数、知识类型、文档数。内容的输入→机制→结果，原因→作用→可见现象/反例，诊断→竞争解释证据与不可判定条件，各自只在相关任务使用。
- 每个 Writer `CLAIM:<TASK_ID>` 绑定唯一写集/起始 SHA，完成后 `RELEASE`、Commit/Blob、专业内容缺口；其他对话 Reviewer 增量审。不同 Worker **不得并发更新 PLAN.md、COVERAGE.md 或其它共享总控文件**；由 Integrator 统一汇总状态，系统 Worker 只写自己独占文件。
- 局部更正要追踪依赖方的旧链接/事实影响，按实际变更标记 `STALE` 并有针对性修复，不重做整个汽车知识。

## 8. 无真实频率时仍可高并发执行

优先级由可信 `S` 安全后果、`V` 维修价值、`D` 诊断复杂、`G` 知识缺口、`B` 架构适用范围与 `F` 真实频率一起决定；`F=UNKNOWN` 不可凭 NHTSA 投诉/TSB/DTC 数量换算概率。不把 F 等待变成结构知识的阻塞门禁。高价值深入，普通任务充分解释即可，低可信优先作保守探索；制动/高压无来源的实际危险操作不生成。

**调度选择**：所有依赖已满足、写集无冲突、前置真实内容可读的候选先进入 `READY`，跨系统可平行派发。每个系统内可滚动启动已经满足前置的下一级任务（流水线），不必形成全局阶段屏障。若资源不足，明确推迟理由和下次触发；避免反复调整算法或每轮重复 Source 审查消耗本来可用于生成的预算。

**阶段性结束不是全汽修知识完整**：只以实际范围、可读 Markdown、覆盖账本和剩余缺口统计结果；已覆盖重要系统的深度可评估，但专业事实资格仍为 NOT_VERIFIED。

---
**版本与审计**：R1 v0.4 基线 Blob `38e3a89b1abaa88d46df47fb09d9ce99572c8a10` 已独立 REVIEW=REWORK（P1×3,P2×3），本 v0.4.1 修复保持历史可追溯；**本稿尚待另一对话对新增 Blob 增量复审**，未获 PASS 之前禁止任何知识 GEN。
