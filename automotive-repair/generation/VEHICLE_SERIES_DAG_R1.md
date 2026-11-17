# 汽修知识生成 · 车型系列适用性子 DAG — v0.4.2 R1 候选

> MAIN：[parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) · 基线：[已独立审核通过的 v0.4.1 PLAN](./PLAN.md) · STATUS：**`CANDIDATE_SERIES_PLAN__INDEPENDENT_REVIEW_PENDING`**。
>
> 本文是**增量执行规划**，不是车辆专属的已生成知识、配件 fitment 表、维修许可或 OEM 专业事实签名。**不修改基线 PLAN Blob `1df1f116a9f4e1effc46840aa4ec57be1289b6cf` 的原有节点/依赖**；本候选仅影响新增 `SER-*` 分支，未独立审核前不得称 `SERIES_PLAN_READY`，但已准入的通用 `STR/FUN/FAIL/REP` 可继续并行执行。

## 1. 先正确区分“车系 / 代际 / 平台 / 配置 / 总成家族”

| 维度 | 含义及知识作用 | 不可混淆 |
|---|---|---|
| **品牌 / 车系（Nameplate / Model Series）** | 厂商、市场名称及一段可追踪的产品系列，例如 Corolla 或 Model 3；只作为发现入口 | 车系名称长期不变不代表几十年结构、供应商或维修程序相同 |
| **产品代际 / 平台（Generation / Platform）** | 同一车系在一组设计或制造期间的架构/车身/电子平台与大版本变更 | 代际通常不是“一个固定动力总成”且各市场更迭时间可不同 |
| **动力/总成家族（Powertrain / Component Family）** | 发动机或电驱代码、变速器类型/系列、制动执行器/电池及充电代次等在多个车系之间可复用 | 同一名称/系统不保证一模一样的部件或功能；同一零件可跨车系适用 |
| **具体车辆配置（Vehicle Configuration）** | 地区/销售市场、年款/制造区间、发动机与变速器/驱动型式、选装/ADAS、软硬件版本及相关 VIN 范围（可证实时） | “Toyota Corolla 2020”或“Model 3”本身不足以确定全部维修限值、软硬件或故障处理方式 |
| **维修知识适用条件（Knowledge Applicability）** | 一条结构/功能/失效/诊断知识在哪个上述范围成立、哪些排除、是否尚不确定 | 配件适配、VIN 解码或一份厂商产品宣传不等于完整 OEM 维修资格 |

**执行时采用两条正交索引**：`system/assembly/component` 与 `model-series/generation/configuration`；一条专业知识可被多个车型系列引用。**系列不是部件父节点，也不是“一个车型生成整本维修手册”的固定配额**。

推荐复用层次：`L0 UNIVERSAL_PRINCIPLE` → `L1 ARCHITECTURE_FAMILY` → `L2 COMPONENT_FAMILY_OR_PLATFORM` → `L3 MODEL_SERIES_GENERATION` → `L4 CONFIGURATION_EFFECTIVE_VERSION`。此处 L2/L3/L4 是*知识适用性细化层*，不是要求每个 Task 都必须输出五层文章。先有一般知识，再以 `delta` 方式生成真正不同的车型内容。

## 2. 事实源与现实边界

- **Auto Care ACES/VCdb/Qdb**：官方解释 Year/Make/Model/Submodel、Region/Engine 与附加适配限定，可用于车型配置标识和零件 fitment 思路；不是 OEM 维修步骤权威。https://www.autocare.org/data-and-information/data-standards/databases/vehicle-configuration-database-vcdb ；https://www.autocare.org/data-and-information/data-standards/databases/qualifier-database-qdb
- **Toyota TIS**：厂商技术资料支持按 Model/Model Year 检索，并需具体资料权限/地区限定。https://techinfo.toyota.com/techInfoPortal/appmanager/t3/ti?_nfpb=true&_pageLabel=ti_whats_tis
- **Tesla Model 3 2024+ 服务手册**：公开可见的独立产品代际文档索引；是具体车型系列发现的候选，**不等于已检查每项维修操作、选装或构型**。https://service.tesla.com/docs/Model3/ServiceManual/2024/en-us/
- **NHTSA vPIC**：公开的 VIN 基本信息解码来源，不能单独证明 ECU 版本、售后更换零件、选装、精确修理或实际安全状态。https://vpic.nhtsa.dot.gov/about/
- 来源可见性必须真实标明 `OFFICIAL_PUBLIC_INDEX / OEM_BODY_VIEWED / SUBSCRIPTION_NOT_ACCESSED / OTHER_PUBLIC / MODEL_HYPOTHESIS / UNKNOWN`。**只看到目录/搜索卡片不得把书或手册正文视为已读**，禁止虚构 OEM 参数或来源页码；官方资料的版权/使用条款要按实际复制/分享行为遵守，原创总结不等于可复制长图文。

## 3. 系列知识生成 Task 的最小 Markdown 适用性字段

| 字段 | 期望记录 |
|---|---|
| `task_id / source_task / output_md` | 不重复的稳定 ID、唯一被引用的上游和独占输出文件 |
| `level / series_id / model_generation` | `L0–L4` 中实际目标层；制造商/车系与**有证据的**代际，未知写 `UNKNOWN` |
| `region / model_year_or_build_range / variants` | 仅在来源真实可见时精确；年款不是制造日期、地区也不由英文车型名自动推定 |
| `engine_transmission_or_drive / component_family / sw_hw_revision` | 仅与当前知识结论相关时记录；未见来源写 `UNKNOWN`，不可猜测 |
| `included / excluded / unknown` | 明确适用、不适用和未确定的分支；`OUT_OF_INITIAL_SLICE` 不当成 `NOT_APPLICABLE` |
| `variation_trigger / knowledge_delta` | **哪个实质差异**使通用 STR/FUN/FAIL/REP 不足，以及新增研究问题；仅别名/装饰差异不生成重复知识 |
| `evidence_link / visible_part / evidence_version` | 外部原始出版方、访问/版次/范围；证据未到位时只能发资料发现任务，不能交付车型维修结论 |
| `prerequisites / claim / exact_commit_blob / review` | 真正阻塞关系、Writer/Reviewer、Blob 与生成质量状态；本期仍 `MODEL_GENERATED_UNVERIFIED` |

**语义验收**：系列发现稿必须实际区分“同系列不同代际/地区/总成”，说明真实可见资料支持了哪条区分、什么尚未知；差量稿必须有**原通用知识引用 + 具体差异 + 导致哪项结构/功能/故障/维修决策变化 + 可见来源/UNKNOWN**，不能换个车型标题重写原通用文章。

## 4. 新增子 DAG（只处理系列分支；不改旧图）

完整节点/前置/唯一写集：

| 新 Task ID | 执行内容 / 可核验交付 | **新分支真实前置** | 独占 Markdown 输出 | 初始状态 |
|---|---|---|---|---|
| `SER-PLAN-REVIEW` | 不同对话核查本文件源/车型名分类/依赖/并行/无环/车型效果边界；写入 #61 Exact Blob 结论 | 本文件实际可回读 | NEEDS_REVIEW |
| `SER-DISPATCH` | 仅在 `SER-PLAN-REVIEW=ACCEPT_SCOPED_SERIES_PLAN_READY` 后准入新系列 Writer；检查当前 Claim + 写集 | SER-PLAN-REVIEW | BLOCKED_BY_REVIEW |
| `SER-DISC-COROLLA` | **Toyota Corolla** 车系：从 Toyota 当前实际可访问的 TIS/公开官方资料发现地区/年款/代际/发动机/变速器差异及 UNKNOWN；不假定 E210、CVT 或传统液力 AT 对所有 Corolla 适用 | SER-DISPATCH | `series/toyota/corolla/discovery.md` | READY_AFTER_SERIES_REVIEW |
| `SER-DISC-MODEL3-2024` | **Tesla Model 3 2024+**：从官方 2024+ Manual 的索引识别适用地区/制造日期、驱动型式/电池/热管理/制动/软硬件变体；没有资料不猜值 | SER-DISPATCH | `series/tesla/model-3-2024plus/discovery.md` | READY_AFTER_SERIES_REVIEW |
| `SER-DELTA-COROLLA-LUBE` | 根据真实 Corolla 车系切片，对照已生成通用 `STR-ENG-LUBE`，标出不同发动机/润滑结构与 UNKNOWN；**仅对确认属于相关 ICE 切片的变体生效** | SER-DISC-COROLLA; STR-ENG-LUBE | `series/toyota/corolla/engine-lubrication-delta.md` | BLOCKED_BY_DISCOVERY |
| `SER-DELTA-COROLLA-TRANS` | 对实际 Corolla 车型系列中真实可见的 CVT/MT/AT/混动 e-CVT **先识别总成类别**，和 `STR-AT` 的适用边界对照；不把 Corolla 全部变速器视作传统液力 AT | SER-DISC-COROLLA; STR-AT **仅用于边界对照** | `series/toyota/corolla/transmission-applicability-delta.md` | BLOCKED_BY_DISCOVERY |
| `SER-DELTA-MODEL3-HV` | 对照通用 `STR-HV`，说明 Model 3 2024+ 的已知架构差异与尚未确认的电池/驱动/充电/版本条件；**不进行带电操作推导** | SER-DISC-MODEL3-2024; STR-HV | `series/tesla/model-3-2024plus/high-voltage-delta.md` | BLOCKED_BY_DISCOVERY |
| `SER-DELTA-MODEL3-BRK` | 对照通用 `STR-BRK`，明确与再生/摩擦制动联动的已知车型差异、不同版本的安全界限；不写车型专属维修操作 | SER-DISC-MODEL3-2024; STR-BRK | `series/tesla/model-3-2024plus/braking-delta.md` | BLOCKED_BY_DISCOVERY |
| `SER-VARIANT-CHECK` | 汇总已交付 2 车系 delta，找出是否必须再下钻为特定配置/地区/制造日期/软硬件版本；只列真实知识缺口、价值及出处 | 至少一个 SER-DELTA 实际生成（按事件触发，**不是四个全部完成门禁**） | `series/series-variant-gaps.md` | WAITING |
| `SER-REPLAN` | 仅对已发现且有必要、可验证的差异创建 `SER-VARIANT-*` / `SER-CONFIG-*` 新任务，写明来源、依赖、独占文件、实际应用价值与全图校验收据；Integrator 独占 PLAN 改动 | 至少一篇真实发现或 delta + 具体差异 | WAITING |

**注意**：`SER-VARIANT-CHECK` 是由单个真实完成事件激活的动态任务，不将“不存在的某个 delta”当成静态前置。其触发条件与必需的静态依赖区分记录；新增实际配置节点时再由 Integrator 明确稳定 ID。

文字版拓扑（同上表）：

```text
原 v0.4.1 已审核 DAG：  C-DISPATCH ──> STR/FUN/FAIL/REP 继续独立运行
                                         └─> 已生成的 STR-ENG-LUBE / STR-AT / STR-BRK / STR-HV

新车型系列候选 DAG：
VEHICLE_SERIES_DAG_R1.md 当前 Blob ──> SER-PLAN-REVIEW ──> SER-DISPATCH
                                                             ├─> SER-DISC-COROLLA ──┬─> SER-DELTA-COROLLA-LUBE  ← STR-ENG-LUBE
                                                             │                       └─> SER-DELTA-COROLLA-TRANS ← STR-AT（边界对照）
                                                             └─> SER-DISC-MODEL3-2024 ├─> SER-DELTA-MODEL3-HV ← STR-HV
                                                                                      └─> SER-DELTA-MODEL3-BRK ← STR-BRK

任意完成的 SER-DELTA -> SER-VARIANT-CHECK（内容/条件增量）-> SER-REPLAN（核验后新节点）
```

- **两个系列发现独立并行**，四个 delta 独立写集；每个 delta 只在自身真实前置完成后开始，不必等待另一车型系列。原有所有通用系统任务不受 SER 的审核门禁阻塞。
- SERIES-DISCOVERY 是**差异来源发现**，不是“每个系列都复制全部 STR/FUN/FAIL/REP”。`SER-CONFIG-*` 不得在车型、地区、硬件和专业材料缺失时编造；没找到真实差异时写 `NO_MATERIAL_DELTA_YET` 与证据限制，结束这条分支而不是水文章。
- 数据输出依然只用 **Markdown**；上述建议的 `series/` 独立于现有 `topics/`，避免多个 Worker 修改同一结构稿，交叉引用优先而不是全文重复。
- 新的 SER DAG 是**受审候选**。当前 Reviewer 不同对话审核通过前 **不执行系列知识生成**；不重新冻结现行 v0.4.1 通用 DAG，不倒填任何已完成任务的适用资格。

## 5. 深度与车型系列的调度价值

- **优先领域价值**：维修市场覆盖、能否区分同系列不同配置导致的不同根因、误换件成本、诊断/维护多版本差异，以及资料可见程度；没有车型数量或故障率统计就标 `UNKNOWN`，不虚构排名。
- **广度优先性**：初期两个车型系列仅为方法样本，汽车系统广度队列 `STR-LOWV/STR-THERMAL/STR-STEER-SUSP` 等仍占有资源位置。
- **高价值/高风险**：制动、高压、气囊等车型安全边界必须保留 OEM 来源/资质；生成知识可解释原理与风险，不能交付可直接操作的高危维修步骤。
- **去重阈值**：只在结构、机制、失效原因、证据鉴别或维修适用决策产生非同义差异时创建新 delta；单纯 marketing facelift/trim 名称/同一部件别名不值得独立专业知识文章。
- **多系列共用总成**：一个发动机/变速器平台的知识文件应优先作为共享家族知识，两个车系只链接及记录不同安装/参数/范围，不复制。

## 6. 并发、审核与动态全图保障

1. 每个新的系列发现 Writer 应先读取 #61 最新 Claim/计划审核；发表 Claim 后**再次读取**，同写集只取最小有效 GitHub COMMENT ID。目标文件首次创建须原子 create-file；同路径冲突停下。
2. SER 的 Reviewer 必须是其他对话且不得与该系列文件 Writer 是同一对话；审核 Exact Blob、来源可见性、车型适用性、是否存在实质增量和跨系统引用；结果 `ACCEPT_SCOPED_GENERATION_ONLY` 或 `REWORK/P0/P1/P2`，仍非专业 OEM 认证。
3. 每次 `SER-REPLAN` 真的新增 DAG 节点时，先检查**现行 v0.4.1 原图 + 全部 SER 子图**：稳定 ID 唯一、每条依赖 ID 存在、无自依赖、拓扑排序全部节点、唯一路径写集；验证失败拒绝激活。审查结论只覆盖对应 Blob，不能拿本批静态 DAG 核验冒充下一次动态验证。
4. 已生成的系列节点若发现上游架构证据 REWORK，传播 `STALE` 给**实际受影响**的后继，增量重做；不重审无关系统，GitHub 作为唯一交接事实源。
5. 阶段完成必须报告：各系列/代际/配置的**已实查**范围、实质差异、明确 UNKNOWN、引用的通用知识、生成质量限定审核状态，专业事实资格仍未授予。
6. 无本地环境需求。没有可见官方资料也可以交付**诚实的资料发现缺口**，但不能用无依据的车型配置表填满 Markdown。

## 7. 标准触发词注册（每个任务从 GitHub 独立新对话执行）

**主调度仍只需 `#61 继续推进`**；不为 series 另建主 Issue。

### SER-P00 — 独立计划审核
```text
OUTPUT_LABEL=PARTS_AUTOREPAIR_V042_SERIES_DAG_R1_INDEPENDENT_REVIEW
REPO=kaicreator-mm/parts-system MAIN=#61
DATA_REPO=kaicreator-mm/kg-data
FILE=automotive-repair/generation/VEHICLE_SERIES_DAG_R1.md
EXACT_BLOB=<CURRENT_BLOB>
ROLE=OTHER_CONVERSATION_NON_WRITER
审车型系列/代际/动力总成/年款地区/软硬件适用性分层；
核对 Toyota Corolla 与 Tesla Model 3 2024+ 来源入口和真实差量路径、
逐节点依赖/并行、唯一 Markdown、动态全图无环、不给出虚构车型事实；
确认原 v0.4.1 任务不被新门禁阻塞。
写回 ACCEPT_SCOPED_SERIES_PLAN_READY 或 REWORK/P0/P1/P2 + Exact Blob；
不改文件、不生成车型知识、不代签 OEM/N3。
```

### SER-P01 — Toyota Corolla 系列发现（仅审核放行后可执行）
```text
OUTPUT_LABEL=PARTS_AUTOREPAIR_V042_SER_COROLLA_DISC_R1
REPO=kaicreator-mm/parts-system MAIN=#61
DATA_REPO=kaicreator-mm/kg-data TASK=SER-DISC-COROLLA
ROLE=CLAIMABLE_SINGLE_WRITER
WRITE_SET=automotive-repair/generation/series/toyota/corolla/discovery.md
确认最新 SER 计划独审 ACCEPT、Claim/路径；查真正可访问 Toyota 官方 TIS
及原始资料，区分车系、代际、地区年款和发动机/变速器家族；
仅生成可证的车型系列范围与 UNKNOWN，不编造 Corolla 都用传统 AT。
只交付原创 Markdown，提交/回读 Exact Blob/释放 Claim。
```

### SER-P02 — Tesla Model 3 2024+ 系列发现（仅审核放行后可执行）
```text
OUTPUT_LABEL=PARTS_AUTOREPAIR_V042_SER_TESLA_M3_2024_DISC_R1
REPO=kaicreator-mm/parts-system MAIN=#61
DATA_REPO=kaicreator-mm/kg-data TASK=SER-DISC-MODEL3-2024
ROLE=CLAIMABLE_SINGLE_WRITER
WRITE_SET=automotive-repair/generation/series/tesla/model-3-2024plus/discovery.md
确认最新 SER 计划独审 ACCEPT、Claim/路径；读取 Tesla 官方
2024+ Model 3 Service Manual 可见正文/索引，明确车型代际、
地区、驱动/电池/制动版本差异及 UNKNOWN；不提供高压实操。
仅写原创 Markdown，提交+回读+释放 Claim，不代签专业事实资格。
```

### SER-P03 — 车型差量生成（各 delta 实例必须独立标签/写集）
```text
OUTPUT_LABEL=PARTS_AUTOREPAIR_V042_SER_DELTA_<SERIES>_<SYSTEM>_R1
REPO=kaicreator-mm/parts-system MAIN=#61
DATA_REPO=kaicreator-mm/kg-data TASK=<EXACT_SER_DELTA_TASK>
ROLE=CLAIMABLE_SINGLE_WRITER
WRITE_SET=<SERIES_SPECIFIC_MD_PATH>
核对 SER 审核准入、系列发现真实提交、通用 STR Exact Blob 和独占 Claim。
只说明已证实的车型系列实质结构/功能/失效/诊断差异，
标注原始资料的可见范围、地区/年款/总成/软件版本 UNKNOWN；
无实质差异时交付 NO_MATERIAL_DELTA_YET 研究结论，不复制通用正文。
仅 Markdown，提交+回读+RELEASE，不授予 OEM/实车维修操作资格。
```

### SER-P04 — 车型动态再规划
```text
OUTPUT_LABEL=PARTS_AUTOREPAIR_V042_SERIES_DYNAMIC_REPLAN_R1
REPO=kaicreator-mm/parts-system MAIN=#61
DATA_REPO=kaicreator-mm/kg-data
ROLE=INTEGRATOR TASK=SER-REPLAN
读取已生成的系列证据与真实 delta；只增有实质价值、可判断适用性
和唯一写集的 VAR/CONFIG 节点，未证实型号/年款保留 UNKNOWN。
全图稳定 ID/依赖存在/无环验证并存新 Blob，变更范围交其它对话独审。
不覆盖已审核原 STR/FUN/FAIL/REP 知识稿；不恢复车型×系统固定配额。
```

## 8. 当前阶段真实性清单

- `DONE`：计划候选编制；真实外部行业入口确认；清晰区分模型系列、车型代际、总成家族与配置；制定并行发现和 delta 无重复任务。
- `PENDING`：候选计划与每个任务的真正 GitHub Review Claim、Exact Blob 独立审核。**没有审核 PASS 前 SERIES_DISPATCH=BLOCKED**。
- `NOT_RUN`：Corolla 与 Tesla 系列的资料发现、实际型号/平台 BOM 比对、车型参数及维修知识生成、独立内容质量审核、OEM/专业事实资格。
- `UNCHANGED`：v0.4.1 原系统知识 DAG 和其既有 Writer/Reviewer 结论继续按原 Blob 有效；本计划子图不倒填旧内容的适用资格。

**原则：车型系列是扩展覆盖和减少误诊的适用性维度，不是覆盖全部汽车的有限封闭品牌表。**
