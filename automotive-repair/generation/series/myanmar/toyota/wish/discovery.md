# 缅甸在用 Toyota Wish：2003 首代与 2009 改款的发动机、传动与底盘差异发现（SER-DISC-WISH）

> TASK_ID：`SER-DISC-WISH` · 主控：[parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) · 数据仓：`kaicreator-mm/kg-data` · 仅 Markdown。  
> 上游准入：[MYANMAR_FLEET_PRIORITY_R1.md](../../../../MYANMAR_FLEET_PRIORITY_R1.md) Blob `9b6c66311da069b28d2b1681bf98b0723e193ea3`，异对话计划审核 [#7013143644](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7013143644)，[C-R17-DISPATCH 准入](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7013561465)。  
> **范围**：`MYANMAR_USED_WISH_CANDIDATE` / `MODEL_GENERATED_UNVERIFIED` / `GENERATED_REVIEW_PENDING`；本篇只确认历史缅甸二手车研究价值与 Toyota 日本特定年份/等级公开配置。**没有**对缅甸某辆 Wish 的车架/实装变速箱、发动机、底盘、故障率和维修手册进行正式认证。`OEM/VIN/N3=NOT_GRANTED`。

## 1. 市场事实：重点应是旧的 2003 Wish，不是直接从 2009 年重做技术百科

2022-09-29 的 [Myanmar Digital News / GNLM 本地二手汽车市场报道](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand)明确提及 **没有改装的 2003 Wish** 在当时交易讨论中受到关注。该报道的有效范围是 2022 年二手市场，并不说明 2026 年缅甸 Wish 全国保有量、最新故障率或所有在售车辆的配置。

Toyota 于 2003-01 推出第一代 Wish，并在 2003-04 增设 2.0L G/Z；2009-04 才推出第二代 Wish。因此本项目应首先把 **2003 年周边存量车适用性** 与后续 **2009 新代际技术差异** 分开，而不是先研究市场资料无法证明的最新产品。

| 需要严格区分 | 现有证据 | 不能推出 |
|---|---|---|
| `2003_MYANMAR_USED_TRADE_WISH` | 缅甸 2022 本地媒体明确出现该年份和车型 | 具体车架、发动机、传动、货源/改装状态真正经过核验 |
| `2003_JAPAN_FIRST_WISH_1_8` | Toyota 2003 首发官方公告有 `1ZZ-FE 1.8L` 及前驱/四驱分支 | 在缅甸挂牌为 2003 Wish 的个体必为 1ZZ-FE FF、或具某种指定 AT 代号 |
| `2003_JAPAN_WISH_2_0_G_Z` | Toyota 2003 年后续官方公告有 `1AZ-FSE 2.0L D-4 + Super CVT` | 所有 2003 Wish 都是 2.0L D-4/CVT，或同一发动机适用于 1.8 车 |
| `2009_JAPAN_SECOND_WISH` | Toyota 2009 新车型版本存在 `2ZR-FAE 1.8L` 与 `3ZR-FAE 2.0L`、`Super CVT-i` 等配置 | 把 2009 Valvematic、CVT、制动/车身安全件无条件贴到缅甸 2003 样本 |

## 2. Source-First 原厂版本配置矩阵

| 来源日期/地区 | 可以从 Toyota 原始公告确认的产品家族 | 维修知识的真实分叉 | 实车未知 |
|---|---|---|---|
| **2003-01 日本初代 Wish** | [Toyota 第一代 Wish 发布](https://global.toyota/en/detail/1268031)：七座紧凑型车；列有 `1ZZ-FE 1.8L` 的 **FF 和 4WD** 车型。厂商强调不同造型、悬架及载人配置 | 发动机家族、前驱/四驱后桥、轮端与悬架载荷属于实际技术分支；不能假定任意 Wish 都是前驱 | 实际车架/驱动、制造年和变速箱型号缺证 |
| **2003-04 日本新增 2.0L G/Z** | [Toyota 2.0L Wish 公告](https://global.toyota/en/detail/1617129)：`1AZ-FSE` D-4 缸内直喷与 VVT-i、`Super CVT` 无级变速器，仅适用于列出的 **G/Z 2.0L** 技术切片 | **1.8L 1ZZ-FE 与 2.0L 1AZ-FSE D-4** 的燃油/点火/排放和部分变速器故障知识不能混同；G/Z 2.0L 的 CVT 不可泛化到全部 1.8L 车型 | 任何缅甸 2003 Wish 是否确实属于 G/Z、原装 D-4 和该 CVT 均 UNKNOWN |
| **2009-04 日本第二代 Wish** | [Toyota 2009 第二代 Wish 公告](https://global.toyota/en/detail/306764)：`2ZR-FAE 1.8L`、`3ZR-FAE 2.0L` 与 `Valvematic`、`Super CVT-i`；日本表列前驱/部分 1.8L 四驱、六/七座等级差异 | 第二代的可变气门升程控制、发动机家族、CVT 和后桥结构必须与 2003 第一代分开 | 没有任何来源说明 2022 报道中的缅甸 2003 Wish 是 2009 第二代动力和电子系统 |

**不能混用历史车系事实**：Toyota 的一次发布是某个年份日本产品的说明，不是今天缅甸每辆车的制造时期。所谓“第一代/第二代”用于发现原厂文档，不代表本系统已有能力通过车牌号码推导车型版本。

## 3. 组成和正常功能：为什么 Wish 的维修知识需要分开

### 3.1 发动机与燃油喷射系统

- **已证实为首代 1ZZ-FE 1.8L**：可以选择对应的汽油机进气、喷射、点火、冷却与润滑知识；但本文无实际原厂电控图、发动机代码的车辆级身份或具体 DTC 定义，不能根据“Wish 1.8”就断言某个传感器、VVT 阀或喷嘴损坏。
- **已证实为首代 2.0L 1AZ-FSE D-4**：官方文献提供了缸内直喷 D-4 和 VVT-i 技术存在性。其燃料喷射、燃烧和控制条件与 1ZZ-FE 的完整配置不应无证明地当作同一种结构；同样“难启动/怠速不稳”并非某种高压燃油泵或喷嘴故障的充分证明。
- **2009 第二代 2ZR-FAE/3ZR-FAE Valvematic**：原厂公告强调改变进气门升程/正时的技术，不能将其控制机构误写成早期 1ZZ-FE/1AZ-FSE 的通用功能。某缅甸车究竟装备何种引擎必须先有实际车辆/原厂来源。

### 3.2 CVT 与传统 AT：名称不足以判断液压与传力结构

2003 年 Toyota 确认 **特定 2.0L 1AZ-FSE G/Z + Super CVT**，2009 年确认新 Wish 一系列 Super CVT-i 技术；但这**不能说明 2003 所有 1.8L 车型都装同一种 CVT**。对一个维修需求来说应先分开：

| 物理问题 | 如果是已证实 CVT 家族 | 如果是旧 Wish 其它未确定箱型 |
|---|---|---|
| 发动机转速与车速比例 | 连续变比、起步耦合、控制需求、热态与传动输出构成研究候选 | 应先确认机械家族；不能直接套 CVT 带轮/链/液压夹紧 |
| 起步动力不足/冲击 | 可有 CVT/扭矩输入/离合执行/发动机/轮胎多种竞争机制 | 任何自动挡也不能仅凭驾驶者说“顿挫”就判断换某电磁阀 |
| 故障码和控制 | 不同 OEM 变速箱/TCM 版本必须查实 DTC 及冻结帧 | 无车架/型号时一律 `TRANSMISSION_DTC_APPLICABILITY=UNKNOWN` |
| 油液和维修方案 | 无确切总成与匹配手册时 `FLUID_TYPE_PRESSURE_SERVICE=UNKNOWN` | 禁止套用同车系其它年代的 ATF/CVTF/紧固参数 |

项目既有[传统行星液力 AT 通用结构](../../../../topics/transmission/automatic/structure.md)只用于确实属于对应结构家族的车辆；仅因为自动挡而将传统 AT 的行星换挡表用于 Toyota Super CVT 是错误的。

### 3.3 前驱/四驱、悬架载荷、六/七座结构

Toyota 2003 年 1ZZ-FE 家族有前驱/四驱；Toyota 2009 也有部分四驱等级。对后续维修知识有价值的不是“Wish 轮胎有几颗螺丝”等固定模板，而是**车辆实际驱动形式与轮端、后桥、万向节、差速器、制动附着和负载**的分叉。Toyota 2009 的六/七座等级不能直接作为任何缅甸 Wish 座椅数、载荷法规或悬架零件互换资格。

**反例**：同为起步异响，可能来自发动机/传动、半轴/差速、悬架衬套、轮胎/轮毂等，不能根据 Wish 2003 名称直接更换某一后桥部件。坐满七人的历史市场用途也不能直接推算某台车的悬架磨耗程度和故障率。

## 4. 维修知识下一步如何扩张（候选而非已准入任务）

| 后继候选任务 | 实际必要证据 | 相对通用知识的真实增量 |
|---|---|---|
| `SER-DELTA-WISH-ENGINE` | 有缅甸实际 Wish 车架及 1ZZ-FE / 1AZ-FSE / 2ZR-FAE / 3ZR-FAE 适用原厂资料 | 区分 D-4 直喷、早期 VVT-i 与后期 Valvematic；防止诊断维修错配 |
| `SER-DELTA-WISH-TRANS` | 有 2003 1.8/2.0 或 2009 等实车变速器总成证据 | 区分旧车未知 AT 与特定 Super CVT/Super CVT-i；避免错误油液/执行器假设 |
| `SER-DELTA-WISH-DRIVE-SUSP` | 能证明前驱/四驱、后桥、座位/级别和零件差异 | 解释后轴/差速、半轴、阻尼/制动与轮胎附着如何影响真实维修 |
| `SER-DELTA-WISH-LOWV-HVAC` | 对应车型原厂电子/空调配置和实装设备的可见证据 | 不能把高配自动空调/智能进入/制动电子全部推广给所有 2003 Wish |

成功不是生成所有候选，也不是用一辆车复制一整套保养手册。按缅甸已识别车型实际困难与 OEM 来源逐项决定，没证据则 `NO_MATERIAL_DELTA_YET` 或 `BLOCKED_LOCAL_EVIDENCE`。

## 5. 应拒绝的错误结论与安全边界

| 错误泛化 | 正确反例/未知 |
|---|---|
| “缅甸主流 Wish 一定是 2009 的 2ZR/3ZR” | 2022 本地报道明确提到 2003 Wish 的历史交易；没有具体 2009 本地存量排名 |
| “所有 2003 Wish 都是 1ZZ-FE 1.8L” | Toyota 2003-04 官方新增 2.0L 1AZ-FSE G/Z，需按配置/生产时期区分 |
| “所有 Wish 自动挡都是 CVT” | 厂商确认**特定** 2003 2.0L G/Z 为 CVT，不证明全部 1.8L 传动结构 |
| “2009 车型技术和零件可以套给 2003 Wish” | 2009 正式第二代有不同 2ZR/3ZR Valvematic 与 CVT 资料，不能倒填 |
| “G/Z 2.0 的 CVT 应该和所有新 Wish 零件互换” | 同一“CVT”名称不证明带/链、控制器、油液、阀体或总成可互换 |
| “二手市场有一款 Wish 报价，所以这是缅甸全国高发故障车” | 单一旧交易/报价不构成保有量或专业维修工单分母 |

严重制动效能减弱、方向失控、发动机过热或动力异常存在安全风险时应停止正常使用并由合格专业人员根据对应 OEM 文件处置。本文**不包含**燃油高压维修、路试诱发故障、车辆举升拆装、转向/制动危险操作、CVT/AT 换油方法、紧固力矩、油压限值、排放许可或“可继续驾驶”认证。

## 6. 来源与模型状态账本

| 原始来源 | `evidence_type / date / market_region` | 可信用途与边界 |
|---|---|---|
| [Myanmar Digital News / GNLM 二手车报道](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand) | `MYANMAR_USED_TRADE / 2022-09-29 / MYANMAR` | 有 2003 Wish 的当地市场线索，不是 2026 统计 |
| [Toyota 2003 初代 Wish 官方发布](https://global.toyota/en/detail/1268031) | `OEM_JAPAN_NEW_MODEL / 2003-01 / JAPAN` | 1ZZ-FE 1.8L 前驱/四驱、首代车系存在性 |
| [Toyota 2003-04 Wish 2.0 G/Z 官方扩充](https://global.toyota/en/detail/1617129) | `OEM_JAPAN_GRADE_ADDITION / 2003-04 / JAPAN` | 1AZ-FSE D-4 / VVT-i、特定 Super CVT 的独立配置 |
| [Toyota 2009 第二代 Wish 发布](https://global.toyota/en/detail/306764) | `OEM_JAPAN_NEW_GENERATION / 2009-04 / JAPAN` | 2ZR-FAE/3ZR-FAE、Valvematic 与 Super CVT-i、前驱/部分四驱等级 |
| [Toyota 2005 Wish 改款](https://global.toyota/en/detail/1649416) | `OEM_JAPAN_MODEL_CHANGE / 2005 / JAPAN` | 追加历史时间点，不证明缅甸某辆车的正确 VIN |

`market_evidence=LOCAL_USED_TRADE_2022`，`model_family=TOYOTA_WISH`，`chassis_code=UNKNOWN_LOCAL`，`build_date=UNKNOWN_LOCAL`，`engine_code=UNKNOWN_LOCAL`，`transmission_code=UNKNOWN_LOCAL`，`driveline=UNKNOWN_LOCAL`，`source_version=TOYOTA_JP_2003_2005_2009`，`national_fleet_rank_2026=UNKNOWN`，`failure_frequency=UNKNOWN`，`OEM_VIN_N3=NOT_GRANTED`。

下一动作：交**其它对话非本 Writer**独审当前文件 Exact Git Blob，检查 Toyota 原始配置行和缅甸旧车市场关联、真实变速器差异、知识深度及安全未知；写回 `ACCEPT_SCOPED_GENERATION_ONLY` 或 `REWORK` 与 P0/P1/P2，禁止原 Writer 自签或将生成稿当成实车认证。
