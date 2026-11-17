# Honda Fit / Jazz：不同代际的自动变速器与混动动力路径差量 — R1

> TASK_ID：`SER-DELTA-FIT-TRANS` · 研究级别：`L3 SERIES-GENERATION` × `L2 POWERTRAIN-FAMILY` · 市场：缅甸在用旧车研究**候选**，不能自动把日本款型映射到某个缅甸 VIN  
> 直接前置：[`SER-DISC-FIT`](./discovery.md) Blob `2c8ab39f67c076352586eed2a2f2187147fa909a`（[独立生成质量审核 ACCEPT](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6962478386)）；[传统液力行星 AT 结构](../../../../topics/transmission/automatic/structure.md) 仅为**有级 AT 的可选结构对照**，不是 CVT/MT/i-DCD/e:HEV 的硬技术前提  
> 交付状态：`GENERATED_REVIEW_PENDING` / `MODEL_GENERATED_UNVERIFIED`；**OEM 车型维修实操、正式事实/N3 资格未授予**。  
> source_visibility：`HONDA_OFFICIAL_JAPAN_PRODUCT_RELEASE + HONDA_OEM_TECHNICAL_OVERVIEW`；`MYANMAR_SPECIFIC_VIN_SERVICE_DATA=UNKNOWN`。本稿是**厂商证实的传动家族差异**，不是所有 Honda Fit 的通用固定变速器型号表。

## 1. 具体问题：为什么“Fit Automatic”不是一个维修知识对象

同样在二手市场被称为“Fit 自动挡”，Honda 公开发布的日本市场 Fit 家族至少包含传统手动变速器（MT）、采用液力变矩器的 CVT、特定四驱版本的有级 5AT、IMA 混动配套 CVT、i-DCD 7DCT，以及后来 e:HEV **Electric CVT**。这些分支动力流、执行器和热/电控制的技术作用不同，不应生成“Fit 自动变速箱常见故障”这样无机型适用边界的单一结论。

**严格边界**：缅甸 [GD1 卖家挂牌](https://car.com.mm/cars/honda-fit-gd1) 和 [GE6 卖家挂牌](https://car.com.mm/cars/honda-ge6) 仅说明当地可见有人使用这些车型字符串；两个页面自填发动机和年份等数据有矛盾/模板错误，不能把任一辆车判为特定 CVT/5AT/IMA/DCT。**直到实车车架/发动机与变速器代码、生产时期和匹配 OEM 来源验证前，具体 Myanmar FIT 仍为 `TRANSMISSION_FAMILY=UNKNOWN`**。

## 2. 日本市场原厂资料支持的“不同传动家族”矩阵

| 原始官方资料适用切片 | Honda 确认的技术变型 | 动力传递/控制机理不同之处 | 绝对不能因此推广 |
|---|---|---|---|
| **2001 首代 Fit 日本发售** | 1.3 i-DSI + Honda Multimatic S，Honda 技术材料确认为 CVT | 输入→无级变比机构→输出，控制目标不等同传统离合/制动组合选择的 4AT；具体 CVT 形式应以该版本原始图为准 | 不是所有 GD 代次、地区、年款完全相同控制器或油液 |
| **2007 第二代 Fit 日本发布** | 汽油版 CVT，部分 CVT 带**液力变矩器**；官方型号表另见**4WD 5AT、部分 5MT** | “有液力变矩器”不能推出必为多挡行星 AT。CVT 和有级 5AT 在结构/控制及诊断基线不同 | 不能说所有 GE/4WD 必然 CVT 或所有 2007 车型 5AT |
| **2010 第二代 Fit 日本改款** | **FWD CVT、特定 4WD 5AT、MT/RS 6MT、IMA Hybrid + CVT** 都有在 Honda 日本官网的配置表中 | **纯汽油 CVT、5AT、手动与 IMA-CVT** 即便同年同车系，其发动机-动力流及控制信号不同 | 不能把日本 2010 配置直接贴到缅甸卖家所写的“2008 GE6” |
| **2013 第三代 Fit 日本发布** | 适用汽油版 CVT/6MT、**Fit Hybrid i-DCD：单电机结合 7 速 DCT**，而非 IMA-CVT | 两个离合器/奇偶挡齿轮路径与电机耦合的机电控制问题不同于机械无级 CVT、油压多挡 AT | 不能因某辆是“Fit Hybrid”就断言 7DCT；具体地区/版本需来源 |
| **2020 第四代 Fit 日本发售** | Honda **e:HEV 双电机**混动；官方配置表称 `Electric CVT`，同时存在独立汽油版 `CVT Automatic` | **Electric CVT 不是同一个词就等于机械带轮/链条 CVT**：双电机发电/牵引与部分工况机械直连切换属于不同动力流 | 不能将 2020 e:HEV 视为纯 BEV 或将 e:HEV 一定映射到缅甸旧车的 GD/GE 标题 |

**原厂出处（来源切片的实际日期）**：
- [Honda 日本 2001 年首代 Fit](https://global.honda/jp/news/2001/4010621-fit.html)；[Honda Multimatic S 技术论文](https://global.honda/en/technical-review/papers/10003435/)。
- [Honda 2007-10-18 新一代 Fit 日本发布](https://global.honda/en/newsroom/news/2007/4071018-fit-eng.html)：“CVT with torque converter” 与 4WD 5AT / MT 是**按车型/驱动条件的变型**。
- [Honda 2010-10-08 Fit 与 Fit Hybrid 日本配置表](https://global.honda/en/newsroom/news/2010/4101008eng-fit.html)：包括 4WD 5AT、FWD CVT、RS MT、IMA CVT。
- [Honda 2013-09-05 Fit / Fit Hybrid 日本发布](https://global.honda/en/newsroom/news/2013/4130905eng-fit.html)、[Honda i-DCD 7DCT 技术论文](https://global.honda/en/technical-review/papers/10002116/)。
- [Honda 2020-02-13 Fit / e:HEV 日本发布](https://global.honda/en/newsroom/news/2020/4200213eng-fit.html)；[Honda e:HEV 两电机原理](https://global.honda/en/tech/two_motor_hybrid_system_honda_eHEV/)。
- **不能以发表日期代替每辆实车的制造日期**，任何日本 OEM 配置表都不自动覆盖 Myanmar 旧车。

## 3. 三条必须单独理解的机械/动力路径

### 3.1 汽油 CVT 与 4WD 5AT：液力变矩器 ≠ 有级自动变速箱

对于**确认为 CVT** 的 Fit，连续变比装置决定了转速/输出响应，不应直接使用“1、2、3、4、5 挡离合器接合表”去解释其正常控制。Honda 2007 官网特别说明 CVT 与新变矩器组合：变矩器可以改变起步扭矩耦合特性，**不改变 CVT 的无级变速核心分类**。

对于 2010 Honda 官方列出的**部分 4WD 5AT**，属于有级自动家族，但当前尚无该型号内部 OEM 分解资料，不能仅凭“5AT”推断任意液压阀、齿轮组、变矩器锁止图、变速箱代码或油液。已有 [通用传统 AT 结构](../../../../topics/transmission/automatic/structure.md) 可以作为一类**可能适用的概念参照**，是否同构仍必须按匹配车型资料证实。

### 3.2 IMA-CVT 与 i-DCD 7DCT：电机参与的传动系统位置不同

Honda 2010 日本 IMA Hybrid 的发动机、电机辅助和 CVT 构成不同于纯汽油 CVT 的**能量/扭矩路径**；其电池、控制器及能量回收由混动系统影响，但这**不自动**说明该车拥有 2013 i-DCD 的双离合器机构或相同的故障保护策略。

Honda 2013 的 **i-DCD** 使用内置高输出电机的 7 速 DCT，将奇偶挡/双离合器接合与电机参与耦合到同一整车驱动控制问题；不能用 2010 IMA-CVT 的油压/变比故障分析替代 i-DCD 机电控制。**本文不提供**离合器预充、啮合/TCU 标定、断高压或维修程序，真实步骤要基于完全匹配的厂商技术资料和专业资质。

### 3.3 e:HEV Electric CVT：官方名称不是“金属带 CVT”

Honda 2020 日本配置表对 e:HEV 使用 `Electric CVT` 术语，其 **双电机**（牵引电机、发电电机）可形成发动机发电→电机牵引动力路径；Honda 官方 e:HEV 技术说明还描述部分工况通过机械离合器连接发动机与驱动输出。由此得出**可核对的否定结论**：不能将此 Electric CVT 简化为“必有相同的带轮、金属带和液压夹紧控制的传统 CVT”。

此处只是**e:HEV 技术家族的机理解释**。Honda 的不同代 e:HEV、不同车型可能改变齿轮与离合结构；不能把厂家全球技术文章当成 2020 Fit 精确维修图。具体缅甸车是否为 e:HEV、是否使用某一具体减速器/离合结构，仍 `UNKNOWN`。

## 4. 车架/代次识别矩阵：哪些是真的，哪些只是待核标签

| 识别标签 | 当前来源及其精确性 | 在维修知识 DAG 的合法作用 |
|---|---|---|
| `GD1`、`GE6` | **缅甸卖家标题字段**，各自存在旧车挂牌；本轮没有对具体车架/出厂证实 | 只触发对应代际和型号的**资料查找**，不能据标题判定 CVT/5AT/发动机 |
| `GK3/GK4/GK5/GK6`、`GP5/GP6` | Honda [2024 年日本公告型号列表](https://global.honda/jp/news/2024/c240603.html) 有所列代号及对应公告范围；**本稿未逐型号匹配其全部传动和制造区间** | 说明同一 Fit 技术时期还存在汽油与混动的不同型号代码，禁止把全部第三代都简单称 `GK`；是否与缅甸样本相符 UNKNOWN |
| `GR*` 第四代候选 | 由车型研究线索提出，但本稿没有可复核的日本官方 GR 具体版本映射表 | `IDENTIFIER_TO_VERIFY`，不可因属于第四代就预测特定变速箱 |
| `VIN/FRAME_NO / BUILD_MONTH / ENGINE_CODE / TRANSMISSION_CODE / DRIVE_TYPE / REGION / ECU_VERSION` | 本期真实缅甸车辆资料全部未提供 | **L4 配置级专业断言的必要证据集合**；缺少时必须停在“厂商版本差异”层 |

Honda 2024 型号公告不能倒填 GD1/GE6 的真实配置，也不能由 Honda 第四代 e:HEV 的技术资料推断缅甸某台老 Fit 的保护/液压/电控状态。

## 5. 诊断知识因传动家族而变化的竞争解释（不可执行维修步骤）

| 被报告的现象 | 不同家族可能的**问题空间** | 最危险的错误泛化 | 本稿可支持的结论 |
|---|---|---|---|
| 起步不平顺或驱动力中断 | CVT 起步/变比控制；5AT 固定挡位执行/换挡；MT 离合/换挡；i-DCD DCT 及电机/驱动许可；e:HEV 双电机/能量转换 | 只凭“Fit 自动挡”让所有车检查“CVT 金属带打滑”或给同一种 ATF | **首先确认传动家族**，之后按各家族和车型证据细分；具体故障尚未认定 |
| 发动机转速与车速响应变化 | CVT 可能连续变比；5AT/MT 为选定挡位比；IMA/i-DCD/e:HEV 的电机参与使转速与车速关系更复杂 | 将任何“转速不随车速一致上升”直接认定变速箱故障 | 必须考虑车型、工况、动力分配与驾驶模式 |
| 混动“不能进入驱动”或警告 | IMA 的电机辅助/电池/控制，i-DCD 7DCT 的传动+电驱互锁，e:HEV 的发电/驱动/机械连接许可 | 全部解释成 CVT 油压或单个离合器打滑 | 保留低压电源、电池许可、控制通信及电机等竞争假设 |
| 再生制动相关异常 | IMA/i-DCD/e:HEV 电驱介入和制动融合条件因车型而异 | “任何 Fit 都有同一种再生制动或电液后备” | 不把 `SER-DELTA-FIT-BRK` 提前算完成，必须有对应混动变型和安全资料 |

**不提供具体油液规格、液位/油压/标定、接线、制动排气、拆装、高压断电或维修测试步骤**；这些属于车型/专业资格要求更高的后续研究。此表的症状只是有待证伪的**竞争解释空间**，没有真实工单统计或失效概率证据。

## 6. 合格差量与 STOP、真实范围剩余缺口

**已证实的专业差异候选**：在 Honda 日本原厂不同年份的产品家族中，存在 CVT、5AT、MT、IMA-CVT、7DCT 和 e:HEV Electric CVT 不同传动/动力流，因此同一名称不能推出同一机理。此差异**影响**车型适用、根因竞争集、维修资料/传动总成和安全边界，但**不意味着**本稿已逐辆确认 Myanmar 存量分布或具体故障频率。

| 决策项 | 当前事实 |
|---|---|
| `MATERIAL_FAMILY_DELTA` | `SOURCE_SUPPORTED` — 真实存在多个技术家族；资料按日本公布年份限定 |
| `MYANMAR_FIT_VARIANT_VERIFIED` | `NO` — GD1/GE6 仅来自卖家标题；实际车架码/配置 UNKNOWN |
| `CHASSIS_TO_GEARBOX_MATRIX` | `PARTIAL_AND_UNKNOWN` — Honda 某些 4WD 5AT 官方存在，但没有为缅甸每一车架建立年份/驱动/传动全映射 |
| `OEM_SERVICE_FLUIDS_DTC_TSB_REPAIR` | `NOT_AVAILABLE` — 后续须匹配真正官方资料，不能编造 |
| `SOURCE_VERSION_AND_MARKET` | `OFFICIAL_JAPAN_PRODUCT_SLICES` / `MYANMAR_USED_LISTINGS_SAMPLE_ONLY` |
| `MARKET_LISTING_REPLAY` | permalink + 2026-11-18 检视日期可用，`IMMUTABLE_NON_PII_SNAPSHOT=NOT_AVAILABLE`；不能采集/公开车主私人身份 |
| `PROFESSIONAL_FACT_QUALIFICATION` | `NONE`，即使独立内容审核通过仍为 `MODEL_GENERATED_UNVERIFIED` |

**停止条件**：本稿已经解释哪种家族差异值得再深入；在没有缅甸真实车架+OEM 对应技术资料之前，不为每个车款年份复制“CVT vs 5AT”的文章。若取得实际适用版本资料，再由 `SER-REPLAN` 新增真正具有独立价值的型号/配置子任务，并检查全图无环、写集与 Reviewer；不自动解锁制动或混动高压维修操作。

**下游建议**：两个系列传动差量文本可作为跨车系复用的“构型适用性知识”。CVT 家族通用机理、HEV 家族正常工作机制和不同年代 Fit 的 OEM 配置索引应分别建设共享组件家族知识；**不将本篇当作这些新通用任务已经完成**。待不同对话独立内容质量审核此 Exact Blob。
