# 汽修知识生成 · 缅甸存量车型系列子 DAG — v0.4.2 R2

> MAIN：[parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) | 既有已接受通用计划：[PLAN.md](./PLAN.md) | 本文：**`MYANMAR_STOCK_SERIES_PLAN_R2__INDEPENDENT_REVIEW_PENDING`**。
>
> **本 R2 原位取代 R1 车型试点选样。** 优先依据缅甸正在使用和维修的旧车/二手车市场证据选取车型；首批改为 **Toyota Probox（与 Succeed 分别识别）**、**Honda Fit（Jazz 名称按市场限定）**。不采用 R1 的国外新款纯电动车样本。原 R1 历史 Git commit `75d4bca5956137dd90abdae4a2e1819e9201e361` 可审计，但其 Exact Blob `d4e2d6ba8698ad970d7014bffe508e3cd01685b3` **不得用于 R2 计划审核/派发**。
>
> 当前严格分账：`SERIES_PLAN=PENDING_INDEPENDENT_REVIEW`、`SERIES_WRITER_NOT_RUN`、`OEM_FACT_QUALIFICATION=NONE`。**不修改原有 v0.4.1 PLAN Blob `1df1f116a9f4e1effc46840aa4ec57be1289b6cf`；原 STR/FUN/FAIL/REP 继续按已通过的计划独立执行。** 仅生成 Markdown；不引入 LinkML/YAML/JSON-LD/CSV 或按车型×知识类型硬配额。

## 1. 首批样本为什么代表缅甸现有维修需求

**市场口径必须分清**：`ON_ROAD_STOCK` 在用保有量、`USED_TRADING` 二手交易、`NEW_REGISTRATION` 当年新注册、`IMPORT` 进口、`LISTING` 平台在售、`RTAD_SAMPLE` 个别登记记录是不同统计对象。现有可见来源**没有完整且最新的全缅甸分车型在用车保有量普查**，因此以下是 **`MYANMAR_STOCK_RELEVANCE_CANDIDATE`**，不是“全国最多的两款车”、官方数量排名或精确故障发生率。

| 车型系列试点 | 缅甸市场相关性证据及有效范围 | 专业知识与差异重点 | 证据限定 |
|---|---|---|---|
| `SER-MMR-TOYOTA-PROBOX`：Toyota Probox；Toyota Succeed **作为相关但独立名称/配置对照** | 2022 年 Myanmar Digital News/GNLM 当地市场报道称 Probox、Succeed 属于当时有交易需求的旧车车型；2026 年本地二手平台仍可见 2011/2016 年 Probox 与 2007 Succeed 个别在售；缅甸 RTAD 公开登记样本中出现 Probox NCP51 | JDM/市场来源、车架/制造时期、发动机/变速箱/驱动、商用高使用强度下的润滑/冷却/底盘维修适用性；Probox 与 Succeed 不能自动当完全同一零件配置 | 2022 历史交易报道 + 当前挂牌 + RTAD 个别记录，不是 2026 全国 stock census；**不能由出租/商用用途推断每辆车的真实工况或磨损率** |
| `SER-MMR-HONDA-FIT`：Honda Fit，Jazz 名称仅按真实销售地区适用性关联 | 2014 年当地市场报道已列 Honda Fit 为受欢迎小型车；2022 年 Myanmar Digital News/GNLM 报道有 2008 Fit 价格，近期本地平台仍存在 Fit 在售线索 | 汽油版、不同代际 CVT 与混动 i-DCD 7DCT、IMA/e:HEV 差异及制动/低压/混动交互；**不能把 Fit Hybrid 统一当一种变速器/电驱结构** | 历史市场/当前样本证实研究价值，不是最新保有量前二；Honda 官方发布资料可核实**车型家族存在不同技术方案**，不能推出这些配置都在缅甸存量中占多少 |

**现阶段备用候选**：Suzuki Swift、Toyota Vitz、Nissan AD Van、Toyota Hilux/Hiace、Toyota Corolla Axio、Toyota Belta、Suzuki Carry。它们被不同年代缅甸市场报道与当前平台提及，但本 R2 **不激活新系列任务**；后续以维修业务工单、零配件需求、RTAD 分类统计、可靠地区样本、资料可得性动态选择。**不得把当前进口许可或新车销量当成已上路旧车保有量**。

**缅甸市场直接来源**：
1. [Myanmar Digital News / GNLM, 2022-09-29](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand)：明确提及 Probox、Succeed、AD Van 等，并列出 2008 Honda Fit 与其它车型当时价格；**是 2022 年二手车市场，不是 2026 登记保有量**。
2. [The Irrawaddy, 2014](https://www.irrawaddy.com/business/car-market-expands-japanese-models-rule.html)：当年 Yangon 展厅引用 Probox、Fit、Vitz 等需求；**属于历史销售描述，非今天的销量/车量排名**。
3. [CarMM Myanmar current used listings](https://car.com.mm/cars)：用来核对个别 Probox/Succeed/Fit 在售，**listing ≠ 交易数/保有量**。
4. [Myanmar RTAD official document (sample)](https://myanmarrtad.com/?q=en/download/file/fid/4998)：个别公开登记行出现 `TOYOTA PROBOX NCP51`；仅表明存在该注册车型，**不能由样本列表推断全国流行程度**。
5. [Toyota official Probox / Succeed model update (2014)](https://global.toyota/en/detail/3737378)：不同品牌名称/厂商版本是**具体**官方产品例证，不能推定缅甸某辆车实际配置。
6. [Honda official 2007 Fit launch](https://global.honda/en/newsroom/news/2007/4071018-fit-eng.html)、[2013 Fit Hybrid i-DCD](https://global.honda/en/newsroom/news/2013/4130719aeng.html)、[2020 Fit e:HEV](https://global.honda/en/newsroom/news/2020/4200213eng-fit.html)：证实技术版本差异；不能把一代的混动、变速器和制动结构复制给另一代。

## 2. 分类：结构轴 + 系列轴，不让车系取代整车专业知识

汽车系统主轴仍是 `车辆架构 → 系统 → 总成/部件 → 功能 → 失效 → 诊断维修`。车型适用性是平行关联轴：

- `L0 UNIVERSAL_PRINCIPLE`：基本机械/电气/液压/热规律；
- `L1 ARCHITECTURE_FAMILY`：ICE、传统行星液力 AT、CVT、DCT、BEV、HEV 等；
- `L2 PLATFORM_OR_COMPONENT_FAMILY`：发动机代码、变速器总成代次、制动控制器及零件家族，允许跨车系；
- `L3 MODEL_SERIES_AND_GENERATION`：Probox/Succeed 与 Fit 对应产品代次、车架代码和地区；
- `L4 SPECIFIC_CONFIGURATION_AND_EFFECTIVE_VERSION`：实际发动机/传动总成、年款/生产月份、地区、驱动形式、混动形态、选配、ECU/软硬件及 VIN 适用区间（只有可见依据时）。

**L0–L4 是适用性层，不是每个任务要产出五篇文章。** 一套部件家族可能覆盖多个车系；同一车系可有完全不同的发动机/变速器。研究可先从 L3 系列资料发现，再链接对应 L1/L2 通用知识，而不是让所有车型各自复制一篇“机油泵的原理”。

## 3. Markdown 任务最小契约与信息真实性

每个系列任务必须具备：`task_id`、`applicability_level`、`market_evidence_type`、`market_evidence_date`、`manufacturer/nameplate`、`generation/chassis_code`、`model_year_or_build_range`、`region/import_origin`、`powertrain/engine/transmission`、`component_variant`、`included/excluded/unknown`、`variation_trigger`、`source_visibility/evidence_version`、`source_task/actual_prerequisites`、`unique_output_md`、`claim`、`exact_commit_blob`、`review/status`。

- 只看到 2014 Toyota Probox 官方换代资讯，不等于知道 2008/2011 缅甸 Probox 的发动机、变速器或零件细节；先按年份/车架代码与 Toyota 官方资料匹配。
- Honda Fit 早期汽油/CVT、2010 前后 IMA、2013 i-DCD+7DCT、2020 e:HEV 属于**不同适用技术线索**；本 R2 不要求每个配置都生成，只有在实际研究的地区/年款与可见来源成立时才新增相应差量。
- 禁止把 `STR-AT`（只涵盖传统液力变矩器+行星齿轮+液压执行 AT）的机制强行套给 Probox/Fit 的 CVT、MT、DCT 或 hybrid transmission；此处可以把 STR-AT 作为**对比排除知识**，不是所有系列车的必然结构前置。
- `STR-HV` 是 BEV 电驱高压结构，**不自动支持 Honda Fit 的 HEV/IMA/i-DCD/e:HEV 具体事实**；涉及这些混动配置应先另建受审 `ARCH-HEV-*` / `VAR-*` 适用性任务，不能利用 BEV 的维修安全流程猜混动。
- VIN 或车架号码、Auto Care ACES/VCdb（主要针对北美 aftermarket fitment）的识别逻辑只能当线索。缅甸在用 JDM 车辆可能使用与北美市场不同的型号/底盘编码；必须在实际 OEM/车架/部件资料核实，不能由一个 VIN 解码自动给出整车标准维修方案。
- 专属油压、紧固扭矩、ATF/CVTF、制动规格、DTC 解释、TSB/召回和高风险作业程序，若无相匹配的 OEM 机型/版次/来源，标 `UNKNOWN` 并拒绝编造成通用结论。所有新知识稿初始 `MODEL_GENERATED_UNVERIFIED`。

## 4. 缅甸存量车型增量 Task DAG（首次两系列并行）

**生效原则**：所有新增 SER 系列任务需经当前 R2 的不同对话 `ACCEPT_SCOPED_SERIES_PLAN_READY`、Integrator `SER-DISPATCH` 准入。**既有 v0.4.1 通用 GEN 不受此新增门禁阻塞**。以下“DELTA”均须在系列 DISC 确认实质差异和可见来源后才真正启动；无实质差异或证据不足时记 `NO_MATERIAL_DELTA_YET / UNKNOWN`，不用填空文章。

| Task ID | 研究问题与原生 Markdown 目标 | 真正前置 | 唯一 Writer 写集 | 当前 |
|---|---|---|---|---|
| `SER-PLAN-REVIEW` | 另一对话验证缅甸存量选样证据、各任务约束、全图 DAG 与写集；回写 #61 Exact Blob/结论 | 本文件 Blob 可回读 | #61 Reviewer 评论（不修改源文） | READY_FOR_REVIEW |
| `SER-DISPATCH` | 验证本版审核通过、当前各 Task Claim/路径；只放行 SERIES 子图 | SER-PLAN-REVIEW ACCEPT | #61 Integrator 收据 | BLOCKED_BY_REVIEW |
| `SER-DISC-PROBOX` | Toyota Probox；Succeed 作为相关但独立型号名；发现本地可见制造区间、代次/车架、驱动、发动机/变速器/零件变型、维修源权限与 UNKNOWN | SER-DISPATCH | `series/myanmar/toyota/probox/discovery.md` | PLANNED |
| `SER-DISC-FIT` | Honda Fit；必要时区分 Jazz 地区称呼、GD/GE/GK/GR 代际线索、汽油/IMA/i-DCD/e:HEV 技术边界及缅甸样本可见性 | SER-DISPATCH | `series/myanmar/honda/fit/discovery.md` | PLANNED |
| `SER-DELTA-PROBOX-LUBE` | 对已确认适用的 Probox 汽油机总成，研究润滑构型和通用结构的**实际差异**；不造车型油压值 | SER-DISC-PROBOX; STR-ENG-LUBE；需资料证明实质差异 | `series/myanmar/toyota/probox/engine-lubrication-delta.md` | CONDITIONAL |
| `SER-DELTA-PROBOX-TRANS` | 对 Probox/Succeed 已识别实际车架及变速箱型式，区别传统 AT/CVT/MT 等；仅相关部分引用 STR-AT 的边界，不推断全部 Probox 为传统 AT | SER-DISC-PROBOX; STR-AT（仅分类/对照）；需真实配置与来源 | `series/myanmar/toyota/probox/transmission-applicability-delta.md` | CONDITIONAL |
| `SER-DELTA-FIT-TRANS` | 对真实 Fit 代际/动力型式区分汽油 CVT/MT、IMA 与 i-DCD DCT/e:HEV（只有真实资料可见者）；不能偷用传统 AT 机理 | SER-DISC-FIT; STR-AT（仅分类/对照）；具体构型源证据 | `series/myanmar/honda/fit/transmission-variants-delta.md` | CONDITIONAL |
| `SER-DELTA-FIT-BRK` | 对相应 Fit 汽油/混动版本，识别制动/ABS 及其与能量回收联动的实际差异；无型号资料不虚构制动策略 | SER-DISC-FIT; STR-BRK；具体构型源证据 | `series/myanmar/honda/fit/braking-variants-delta.md` | CONDITIONAL |
| `SER-VARIANT-CHECK` | 汇总任一已交付 delta 的真实差异、重复与版本缺口；一次一个真实事件/快照 | 任一 SER-DELTA 实际交付**事件**；非所有 delta 完成的静态 AND 门禁 | `series/myanmar/series-variant-gaps.md` | WAITING_EVENT |
| `SER-REPLAN` | 根据具体车型/总成版本及确有价值的差异，新增有来源的 `SER-VARIANT-*` / `SER-CONFIG-*` 并做全图增量检验；保持其它现有任务的独审资格 | SER-VARIANT-CHECK 有实际收据 | #61 Integrator + 计划控制文件（独占 Claim） | WAITING |

**Task DAG（仅硬依赖，事件条件分开）**：
```text
已审旧 DAG: PLAN_v0.4.1 -> C-DISPATCH -> STR/FUN/FAIL/REP   (不停)
                                         STR-ENG-LUBE ----┐
                                         STR-AT ---------┤
                                         STR-BRK --------┤
新增 R2: plan_Blob -> SER-PLAN-REVIEW -> SER-DISPATCH   │
                                              ├-> SER-DISC-PROBOX -> SER-DELTA-PROBOX-LUBE  <- STR-ENG-LUBE
                                              │                   -> SER-DELTA-PROBOX-TRANS <- STR-AT(边界)
                                              └-> SER-DISC-FIT    -> SER-DELTA-FIT-TRANS    <- STR-AT(边界)
                                                                  -> SER-DELTA-FIT-BRK      <- STR-BRK

任意 SER-DELTA 真实完成事件 -> SER-VARIANT-CHECK -> SER-REPLAN
新拓扑必须再次证明无环；不将“事件”写作无条件 READY。
```

**并行度**：两个 SER-DISC 可以不同 Worker 同时生成；其后真正触发的四个 delta 在独占写集/资料具备时可以跨车系或同车系并行；同时现有 FUN-AT/FUN-BRK/FUN-HV/STR-LOWV 等通用任务继续。两条系列分支的结构父节点和输出路径均不同，避免同文件抢写。实际资料不足时保留 UNKNOWN，不为追求“并行任务个数”生成空内容。

## 5. 动态再规划、合格标准、终止条件

1. **车型样本优先次序**：`维修业务需求/工单或本地样本证据`、`公开 OEM 资料可见性`、`车系技术差异价值`、`安全/误诊后果`、`广度`。不能用本地挂牌量冒充真实保有量，不能凭外推给“首批=最常见两款”。
2. **系列发现完成**：实际列出观察到的车型系列与可证的车架/代际/地区/总成变型、支持它们的原始资料版本、明确未可见的 JDM/OEM 版本和关键未知；不是复制一篇网上车型历史。
3. **差量知识完成**：说明通用 STR/FUN/FAIL/REP 中可复用部分、真实不同的硬件/控制/失效/诊断效果、具体适用范围与来源；仅装饰件/营销版次不同则不新建整篇。
4. **阶段性 STOP**：无实际技术差异/无足够来源/价值低时记录 `NO_MATERIAL_DELTA_YET` / `BLOCKED_SOURCE` 并收敛，不能无限拆每个年款；后续有新工单或 OEM 来源才重新评估。
5. **审核和写集**：每个 Writer 先从 #61 当前评论认领独占路径，发表 Claim 后复查最小有效 GitHub comment ID，原子创建/按 Blob 有条件更新，提交并回读。其它对话 Reviewer 仅对 Exact Blob 生成质量/清晰适用边界做 `ACCEPT_SCOPED_GENERATION_ONLY` 或 `REWORK`，不授予专业事实资格。
6. **动态全图**：修改任务时合并已批准 v0.4.1 主图与所有已放行 SER 子图，检查稳定 ID、依赖存在、无自环、拓扑可排序、唯一文件写集和未审变更范围，新的 PLAN Blob 由另一对话增量审。**本 R2 静态 DAG 自检不等于未来动态 DAG 可安全运行的证据**。
7. **增量改进**：保留其它内容的已审 Exact Blob，不因用户调整车型选样就撤回原 STR/FUN/FAIL/REP 已通过的限定内容结论；高压/BEV 通用知识仍为有效研究主题，**但不以此强行选择某款 BEV 为缅甸存量车首批试点**。

## 6. 提示词 Registry（GitHub 任务交接唯一入口）

### SER-P00 — 独立审核（新 R2）
```text
OUTPUT_LABEL=PARTS_AUTOREPAIR_V042_MMR_SERIES_R2_INDEPENDENT_REVIEW
REPO=kaicreator-mm/parts-system MAIN=#61
DATA_REPO=kaicreator-mm/kg-data
FILE=automotive-repair/generation/VEHICLE_SERIES_DAG_R1.md
EXACT_BLOB=<CURRENT_R2_BLOB>
ROLE=OTHER_CONVERSATION_NON_WRITER
按最新 #61 审核缅甸存量选样与证据口径；Probox/Succeed 与 Honda Fit
车系代际/总成/市场来源边界，四条 delta、并行、事件触发/无环、
唯一 Markdown 写集及 Reviewer 与 Writer 隔离。
不可用 2022 二手交易或 2026 挂牌冒充全缅甸车辆保有量统计。
确认旧 Tesla 样本已取消、旧 R1 Blob 审核失效，通用 v0.4.1 不阻塞。
写回 ACCEPT_SCOPED_SERIES_PLAN_READY 或 REWORK、P0/P1/P2、Exact Blob。
不改计划、不生成知识、不代签专业事实/OEM 资格。
```

### SER-P01 — Toyota Probox 车系发现（需 R2 计划审核通过）
```text
OUTPUT_LABEL=PARTS_AUTOREPAIR_V042_MMR_PROBOX_DISC_W1
REPO=kaicreator-mm/parts-system MAIN=#61
DATA_REPO=kaicreator-mm/kg-data TASK=SER-DISC-PROBOX
ROLE=CLAIMABLE_SINGLE_WRITER
WRITE_SET=automotive-repair/generation/series/myanmar/toyota/probox/discovery.md
核对 R2 当前审核 PASS、PLAN/Claim 与最小有效 GitHub Comment ID。
围绕缅甸实际在用/二手 Toyota Probox，Succeed 另记相关型号；
逐项确认可见 JDM/车型代际、车架代码、发动机/变速器、驱动、
来源/市场、年款/制造期与 UNKNOWN。基于 Toyota 原始公开资料
和缅甸市场证据，不猜全车系相同配置。
原创 Markdown、提交/回读 Exact Blob/释放 Claim，不授予 OEM 资格。
```

### SER-P02 — Honda Fit 车系发现（需 R2 计划审核通过）
```text
OUTPUT_LABEL=PARTS_AUTOREPAIR_V042_MMR_FIT_DISC_W1
REPO=kaicreator-mm/parts-system MAIN=#61
DATA_REPO=kaicreator-mm/kg-data TASK=SER-DISC-FIT
ROLE=CLAIMABLE_SINGLE_WRITER
WRITE_SET=automotive-repair/generation/series/myanmar/honda/fit/discovery.md
核对最新 #61 R2 计划审核 PASS、Claim/唯一文件路径。
先核真实缅甸 Fit 二手/在用线索与 Honda 官方代际/车型资料；
区分汽油/CVT、IMA、i-DCD 7DCT、e:HEV 等不同家族，只有证据
匹配具体地区年款时才赋确切配置。Jazz 仅记地区名称差异。
不把 Honda Fit Hybrid 全部当 BEV 或单一混动架构。
只交原创 Markdown、GitHub 回读和释放 Claim。
```

### SER-P03 — 系列差量 Writer（4 个节点需各自实例化）
```text
OUTPUT_LABEL=PARTS_AUTOREPAIR_V042_MMR_DELTA_<EXACT_TASK>_W1
REPO=kaicreator-mm/parts-system MAIN=#61
DATA_REPO=kaicreator-mm/kg-data TASK=<EXACT_SER_DELTA_TASK>
ROLE=CLAIMABLE_SINGLE_WRITER
WRITE_SET=<EXACT_SERIES_MD_PATH>
核对当前 R2 PLAN 审核、系列发现实际提交、相关通用 STR Blob、
车型年款/总成版本原始证据和 Claim 冲突。只有可证实的机理/维修
适用差异才产生新原创 Markdown；否则 NO_MATERIAL_DELTA_YET/
UNKNOWN，不能复制通用文章或拿传统 AT、BEV 强套其它技术。
提交/回读 Exact Blob/释放 Claim；不授予专业事实或危险操作资格。
```

### SER-P04 — 缅甸样本与后继系列动态重排
```text
OUTPUT_LABEL=PARTS_AUTOREPAIR_V042_MMR_SERIES_REPLAN_R1
REPO=kaicreator-mm/parts-system MAIN=#61
DATA_REPO=kaicreator-mm/kg-data ROLE=INTEGRATOR
TASK=SER-REPLAN
读现行市场证据、COVERAGE/PRIORITY、真实知识与 Reviewer 收据。
仅按实际缅甸保有/工单证据及 OEM 资料可见性动态加新车系，
可考虑 Swift、Vitz、Hilux/Hiace、Nissan AD Van、Corolla Axio 等；
不把挂牌/销售热度当 stock 或故障发生率。去重、唯一写集、
逐依赖完整检查、整图无环、必要增量独审后才激活新任务。
原通用 v0.4.1 并行生成不停。
```

## 7. 精确执行状态

- **本 R2 已编制**：2026-11-18 缅甸市场证据边界、Toyota Probox/Succeed 和 Honda Fit 车型发现、四个有真实前置和唯一输出的可选差量任务、源版本和未知/并发/动态无环规则、五个标准触发词。
- **未执行**：系列计划独立 R2 审核、具体两个系列的实际 Markdown 资料发现、任何差量文章、车型/车架的 OEM 事实认证。
- **不受影响**：原 v0.4.1 已通过计划、四个通用结构稿与其独立质量审核；原有通用系统任务可继续推进。
