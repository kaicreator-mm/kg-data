# #61 跨车型共享 CVT / HEV 知识家族 · 增量 Task DAG v0.4.3 R1

> **定位**：`SER-REPLAN` 的独占 Markdown 计划候选；**`FAMILY_PLAN_REVIEW=PENDING` / `FAMILY_WRITERS=NOT_ADMITTED`**。  
> [主控 parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) · [既有通用 PLAN](./PLAN.md) Blob `1df1f116a9f4e1effc46840aa4ec57be1289b6cf` · [既有缅甸车系 PLAN](./VEHICLE_SERIES_DAG_R1.md) Blob `4229bb3913cff46ccb780247d78d5a94bd6dd049` · 本计划文档仅新增独立子图，不修改两个已审 Blob。
>
> 由 [SER-VARIANT-CHECK 的真实缺口稿](./series/myanmar/series-variant-gaps.md) Blob `81f3733e3df4131a23c98043112e3839fdc0b6eb` 触发；上游 [Probox 传动差量](./series/myanmar/toyota/probox/transmission-applicability-delta.md) Blob `2a0bfda60bc63ea484c45a6c0b01fe31f7db51a0` 已 [限定独立内容质量 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6976215650)，[Fit 传动差量](./series/myanmar/honda/fit/transmission-variants-delta.md) Blob `a1a944399d2dd7dde3ce8e4be9bda06e94b431af` 已 [限定独立内容质量 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6976201311)。**缺口稿自身仍待其它对话独审，不能偷用此计划为其签署质量通过**。
>
> **风险边界**：本期只生成通用研究级知识，不推断缅甸某辆车的真实变速器/混动硬件，不能用于高压或制动维修操作。所有生成件初始 `MODEL_GENERATED_UNVERIFIED`，不授予 OEM、L4 实车适配或 N3 资格。

## 1. 为什么需要共享家族 Task

- Toyota Probox 的 2002 日本产品家族列有 4AT、5MT；2014 日本改款宣布 Super CVT-i。Honda Fit 的多个日本发布时期出现汽油 CVT、部分 4WD 5AT、IMA-CVT、i-DCD 7DCT、e:HEV Electric CVT。**同一车系≠同一变速箱**；不同车系**可以共享** CVT 结构知识。
- 现有 [STR-AT](./topics/transmission/automatic/structure.md) 严格是“液力变矩器 + 行星齿轮 + 液压执行的传统有级 AT”。它不是 CVT/MT/DCT/e:HEV 的真实硬前置。**一个 CVT 可能同时具有液力变矩器，但变比机构仍是 CVT**。
- 现有 [STR-HV](./topics/electrified/high-voltage/structure.md) 严格是通用 BEV 高压结构。**IMA、i-DCD、e:HEV 都是不同的 HEV 架构，不能依靠 BEV 文章自动获得混动电气架构和安全维修资格**。
- **同名 CVT 不等于同构**。Toyota 2018 Direct Shift-CVT 宣传的起步齿轮不能直接贴给 2014 日本 Probox Super CVT-i；Honda 2020 e:HEV 的 `Electric CVT` 也不能填入机械带轮 CVT 家族成员。

**公开原出版方范围（研究入口，不是逐条 OEM 授权）：**
- [Toyota 2014 Probox/Succeed 日本车型公告](https://global.toyota/en/detail/3737378)：2014 型号家族 Super CVT-i，仅对应其具体版本。
- [Toyota CVT 技术说明](https://www.toyota.com/car-tips/types-of-transmissions/)：传统 CVT 的带/链/锥形带轮概念。
- [Toyota 2018 Direct Shift-CVT](https://global.toyota/en/mobility/tnga/powertrain2018/cvt/index.html)：可用于说明 CVT 家族的**差异**，**不是**证明 Probox 2014 具有起步齿轮。
- [Honda 2007 Fit 日本车型发布](https://global.honda/en/newsroom/news/2007/4071018-fit-eng.html)：部分配置 CVT 与液力变矩器共存、5AT/MT 的条件化型号。
- [Honda 2010 Fit/Fit Hybrid 配置](https://global.honda/en/newsroom/news/2010/4101008eng-fit.html)：汽油 CVT、4WD 5AT、IMA+CVT 的实际日本版范围。
- [Honda IMA 官方技术资料](https://www.honda.com.my/technology/honda-ima)、[Honda i-DCD 技术说明](https://global.honda/en/tech/hybrid_system_SPORT_HYBRID_i-DCD/)、[Honda e:HEV 双电机技术说明](https://global.honda/en/tech/two_motor_hybrid_system_honda_eHEV/)：HEV 家族的概念与控制边界；版本不同，不得强行汇总成统一的诊断参数。

## 2. 本增量 Task 表：6 个新节点 / 4 篇不同的 Markdown

| 新稳定 Task ID | 产出及应回答的**可证伪**问题 | 硬前置（非可选对照） | 独占写集 | 状态 |
|---|---|---|---|---|
| `C-FAM-PLAN-REVIEW` | 其它对话审本候选准确的 Task ID/依赖/文件路径、知识复用、CVT/HEV OEM 限制、拓扑与全图无环；写回 #61 当前 Blob 结论 | `SER-REPLAN` 的本文件实际提交 | #61 Reviewer 评论，源文件无写入 | **READY_FOR_INDEPENDENT_PLAN_REVIEW** |
| `C-FAM-DISPATCH` | Integrator 在当前计划通过限定独立审核、文件/CLAIM/原始资料准入条件满足后登记派发；不代签知识事实 | `C-FAM-PLAN-REVIEW=ACCEPT_SCOPED_FAMILY_PLAN_READY` | #61 Integrator 准入评论 | BLOCKED_BY_REVIEW |
| `STR-CVT-FAMILY` | 各家族 CVT 的共同/不同组成（输入耦合/变比、液压夹紧与控制、冷却/润滑、感知与输出）；区分固定挡 AT、MT、DCT 与 e:HEV Electric CVT | C-FAM-DISPATCH | `topics/transmission/cvt/structure.md` | BLOCKED_BY_REVIEW |
| `FUN-CVT-FAMILY` | 给出基本输入→变比目标→实际执行→输出/热/反例，明确部分 CVT 有液力变矩器、其他可能存在起步离合/起步齿轮而不通用 | STR-CVT-FAMILY 的**实际可回读 Markdown** | `topics/transmission/cvt/function.md` | BLOCKED_BY_STR |
| `STR-HEV-FAMILY` | 汽油 HEV 的动力电机、发电/再生、储能/PCU/DC/DC/低压、制动与动力系统接口；区别 **IMA / i-DCD / e:HEV**，不混同 BEV | C-FAM-DISPATCH | `topics/electrified/hybrid/structure.md` | BLOCKED_BY_REVIEW |
| `FUN-HEV-FAMILY` | 不同 HEV 的发动机/电机/电池/传动动力流，串/并联及多模式状态与反例；控制/能量许可和高压安全**只做非操作性机理** | STR-HEV-FAMILY 的**实际可回读 Markdown** | `topics/electrified/hybrid/function.md` | BLOCKED_BY_STR |

**设计的真实并行**：
- 两个 STR（CVT、HEV）只依赖新增计划级准入，彼此**无**执行前置，因此可由不同 Writer 并行。
- CVT 自己的 FUN 仅依赖 CVT STR；HEV 自己的 FUN 仅依赖 HEV STR。这两个后继也互不阻塞。
- 原 `STR/FUN/FAIL/REP` 通用系统任务、缅甸车系 DISC/DELTA 均**不等待**本计划审核。它们若后续引用这批共享知识，必须绑定真实提交 Blob，而不是规划文件路径。
- `STR-AT`、`STR-HV`、Probox/Fit 两份独立传动差量是 **可选对照与需求证据**，**不加入这 4 篇共享正文的硬前置**。不存在假互相依赖，不让 CVT 经由传统 AT 的自动通过继承事实资格。

## 3. 生成正文的语义验收、研究深度和安全边界

**CVT 结构**必须具备：通用液力/摩擦/机械接口、实际可证明的变比构型及实现边界、部件间油路/热/控制链接、传统固定挡 AT/CVT/混动 e-CVT 的明确反例；至少两个真实**不同**车型家族厂商来源示例并标注日本/美国或其他市场版本，不能凭营销名推导某型号有相同金属带尺寸、变矩器、油泵/阀体、扭矩或维修油液。任何特定生产时期和 Probox/Fit 对应关系未知则写 `UNKNOWN`。

**CVT 功能**必须具备：正常传动工作条件和目的（控制目标/执行/反馈）、变比/压力/热负载在不同工况下的区别、传动打滑与正常转速变化的**非诊断性**反例、至少一个不能套用有级 AT 挡位执行表的说明。禁止编造 CVTF 规格、液压阈值、油液更换/拆解/标定实操。

**HEV 结构**必须具备：发动机、电机/发电机、电池/PCU、传动/再生、低压供电/制动通信的互联关系；IMA 单电机辅助、i-DCD 单电机+7DCT、e:HEV 双电机的**来源和真实差异**；清楚排除 PHEV/BEV 和其它特定产品直接继承。高压及制动是危险系统，不写断电、验电、拆包、制动液排气/标定、故障带电检测操作。

**HEV 功能**必须具备：按各家族解释引擎驱动/发电/电驱/再生可行性与**状态条件**，负面示例“所有 Fit Hybrid 都是 DCT / 所有 e:HEV 都是传统带轮 CVT / BEV 高压服务程序可用于 HEV”。不虚构特定车辆控制器信号、SOC/电压安全限值、DTC、特殊维修权限。

**每篇 Markdown 必须记录** `task_id`、研究范围、包含/排除/未知、来源/版本/可见性、部件/关系或条件化机理、反例、证据与知识缺口、下游影响、Writer Claim/Commit/Blob；**由其它对话做独立内容质量审核，正式事实资格保持 0**。

## 4. 合并全图静态校验（本计划 Blob 内的可重复建模声明）

本候选基于真正回读的 **通用 PLAN@1df1f116... 的 32 个稳定 Task**、**车系 PLAN@4229bb39... 的 10 个稳定 Task**、本增量 **6 个 Task** 组合。原主图含 8 个控制和 24 个知识任务；series 包含 2 个 DISC、4 个 DELTA、一个事件型变型检查与其控制。此次静态投影使用已批准表内**硬依赖**（旧 series 的 STR-AT 可选对照错误写入硬前置仍按**原表**保留以维持原 Blob，不借此更改历史记录），以及新节点声明的依赖边：

| 审计项 | 本 R1 候选计算结果 | 解释 |
|---|---|---|
| 全图 Task | **48 = 32 + 10 + 6** | ID 唯一，新增前缀 `C-FAM-*`、`STR-CVT-FAMILY`、`FUN-CVT-FAMILY`、`STR-HEV-FAMILY`、`FUN-HEV-FAMILY` 均不撞旧 ID |
| 全图单向硬边 | **47 条建模边** | 控制准入与四类共享技术链；事件型 `SER-VARIANT-CHECK` 由真实 delta 完成激活，而非无前置即可任意调度 |
| 依赖 ID | **47/47 两端存在** | 没有自依赖；本候选的状态门禁不被视为假上游数据 |
| 拓扑无环 | **48/48 参与拓扑排序** | 静态子图可并行；未来新增不能沿用这份 R1 旧拓扑当全图证明 |
| 知识 Markdown 写集 | **35 = 24 原通用 + 7 原 series + 4 新家族** | 唯一输出文件路径 35/35，无写集碰撞；控制收据为 #61 不计入知识正文 |
| 外部来源和专业事实 | **不构成 OEM/实车事实认证** | 不能用研发计划和限定生成质量 ACCEPT 取代 L4 车架及精确技术版次 |

**校验边界**：这是从两份既有 Table DAG 加当前六节点构造的*显式静态边清单*的拓扑和写集检查，不是对 GitHub 所有未来动态任务的形式化证明。任何 `C-REPLAN/SER-REPLAN` 真正插入/替换依赖时，仍须重新扫描最新完整 Task DAG、稳定 ID、依赖目标、唯一写集、事件条件和拓扑；生成新 Blob 并交独立审核。旧 series PLAN 的 Probox/Fit CVT/MT 差量将传统 AT 对照当 hard predecessor 的 P2 应在**另一次真实受审改动**中修复，不能未修改源码却声称已消除。

## 5. 真正准入、退出和后继动态拓展

1. **阶段 0（当前完成）**：SER-VARIANT-CHECK 已真实提交，且两个传动 delta 现均获其它对话 `ACCEPT_SCOPED_GENERATION_ONLY`。本计划应先检查独立 Reviewer 对缺口稿的结论；其未审核前可生成此**候选**，但不得将它本身写成已通过。
2. **阶段 1（必须由其它对话完成）**：独立 Reviewer 认领本计划 **当前 EXACT_BLOB**，复核 48 节点、35 写集、专业范围/外部来源、原历史 P2 和适用条件；`ACCEPT_SCOPED_FAMILY_PLAN_READY` 或 `REWORK/P0/P1/P2` 写 #61。未过不得派发 CVT/HEV Writer。
3. **阶段 2（Integrator）**：确认无冲突 Claim、质量来源范围、计划 review 已 RELEASE、当前文件 Blob 不变，才记录 `C-FAM-DISPATCH=ADMITTED`。**允许 STR-CVT-FAMILY 和 STR-HEV-FAMILY 并行，不强制等另一个系列**。
4. **阶段 3（Writer）**：每个 Writer Claim 后二次回读，重叠 write_set 由最小有效 GitHub Comment ID 胜出；原子 create 新 .md、失败拒绝覆盖；提交与回读 Exact Commit/Blob，随后 RELEASE。独立 Reviewer 只审限定内容质量。
5. **阶段 4（演进）**：只有完成相应 STR/FUN 后，才考虑更深入的 `FAIL/REP` 家族知识（特别注意混动高压/制动安全）；仍按真实证据与实际维修价值动态增量审。缅甸具体 Probox/Fit 的 L4 配置任务依然需车架/总成/生产日期/OEM 匹配证据；来源不足 `BLOCKED_SOURCE`，不靠“生成更多字”解决。

**本轮停止条件**：不生成新 CVT/HEV 正文、不修改已审旧 PLAN、不假设缅甸车型真实分布、不代签审核身份。两个新增 STR 具备高复用价值，但只有新计划完成独立审核和准入，才从 `BLOCKED_BY_REVIEW` 转成 `READY_CLAIMABLE`。
