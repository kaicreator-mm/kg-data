# 缅甸存量车型系列发现：Toyota Probox / 关联 Succeed — R1

> TASK_ID：`SER-DISC-PROBOX` · MAIN：[parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) · SERIES_PLAN：R2 Blob `4229bb3913cff46ccb780247d78d5a94bd6dd049` · GATE：`SER-DISPATCH=ADMITTED`  
> **文件性质**：原生 Markdown 的“来源可见性与车型/总成差异发现”，不是可直接用于维修的车型手册。  
> **事实资格**：`MODEL_GENERATED_UNVERIFIED` / `GENERATED_REVIEW_PENDING`；不是 OEM Source-First 全断言签名、实车验车、全部缅甸车型统计或 N3。  
> **applicability_level**：`L3 MODEL_SERIES`，仅以有公开来源的日本市场产品史说明配置家族；`L4` 具体缅甸车架/生产日期/维修限值仍 `UNKNOWN`。  
> **source_visibility**：`TOYOTA_OFFICIAL_BODY_VIEWED`、`MYANMAR_MARKET_ARTICLE_VIEWED`、`MYANMAR_USED_LISTING_VIEWED`；`OEM_VIN_SPECIFIC_SERVICE_MANUAL=NOT_ACCESSED`。  
> **证据检视日期**：2026-11-18；网络挂牌是动态页面，本稿固定 URL 与观察日期，不声称网页永久不可变。

## 1. 研究范围与两个必须分账的问题

本任务不是“生成所有 Probox 维修知识”，而是回答两件具体问题：

1. **缅甸市场是否有支持将 Probox 列为存量维修知识候选的真实线索？**——有来自缅甸本地二手市场的历史报道与本期个别挂牌。它们只证明存在交易/挂牌线索，**不**构成全国在用保有量、维修频率或故障率排名。
2. **Probox 与 Succeed、不同年份/型号会不会出现影响维修知识的真实结构差异？**——Toyota 官方资料显示存在不同车身尺寸、发动机、传动与驱动组合，尤其 2002 早期家族和 2014 日本改款之间不能用一个变速器或油路结论覆盖。缅甸某辆车是否属于其中哪一配置，仍需匹配实际车架和可信资料。

**Probox/Succeed 并非完全相同的单个车型条目**：Toyota 历史材料称两者为相关产品系列，早期存在车长/载货和车型定位差异；本文的关联只是为了**共享已证实的发动机/平台知识**，不能自动认定保险杠、底盘附件、变速器或所有零件互换。

## 2. 缅甸市场线索和统计口径

| 证据编号 | 观察与精确来源 | 能说明什么 | **不能**说明什么 |
|---|---|---|---|
| MMR-PB-01 | Myanmar Digital News / GNLM 于 2022-09-29 的二手车市场报道，点名 Probox、Succeed、AD Van 等当时受关注车型。[原文](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand) | **2022 年的本地二手市场相关性** | 不证明 2026 全国在用车总量、维修保养频率或品牌市占率 |
| MMR-PB-02 | 缅甸 CarMM 单个 [Toyota Probox 2011 挂牌](https://car.com.mm/cars/toyota-probox-2011-1113)，2026-11-18 可见，页面商品标题为“Probox 2011”，另有“生产年份 2012”文本、汽油/Automatic 及 Yangon 线索 | 可复查的一条**挂牌记录**，存在自相矛盾的年份字段；对应实车的生产月份尚未验证 | 不能由标题推断真实 2011 年款；挂牌自报“Automatic”不能自动断言 4AT 或 CVT，车架与变速器代码均 UNKNOWN |
| MMR-PB-03 | 缅甸 CarMM 单个 [Toyota Succeed 挂牌](https://car.com.mm/cars/toyota-succeed-1126)，2026-11-18 可见、页面自报 2007 | 一条与 Probox 相关但名称不同的当地挂牌线索 | 不能据此推定与 Probox 任意部件完全互换；无独立 VIN/车架查证 |
| MMR-PB-04 | 缅甸 RTAD 公开行政名单曾出现 Probox/NCP51 形式的个例，原始 [政府下载入口](https://myanmarrtad.com/?q=en/download/file/fid/4998) | 最多只能说明行政记录中存在这种车架名称的样本 | 该文件属于**遗失车辆登记簿补办名单**性质，不是全国在用车辆普查或其现在仍在路上行驶的证明 |

市场证据类型分别记录为 `HISTORICAL_USED_MARKET_REPORT`、`SINGLE_SELLER_LISTING`、`ADMIN_LOST_REGISTRATION_REISSUE`；`ON_ROAD_STOCK_COUNT=UNKNOWN`，`REPAIR_ORDER_SHARE=UNKNOWN`，`FAULT_OCCURRENCE_RATE=UNKNOWN`。

### 2.1 二手挂牌的“同一条数据自身冲突”必须拒绝传播

CarMM 的 Probox 挂牌标题为 “Toyota Probox 2011”，内部生产年份写“2012”，这是**平台记录的字段冲突**。页面还可能有里程单位等动态/模板差异。正确处理为 `SELLER_CLAIMED_YEAR_CONFLICT`，而不是为方便生成把标题年份当真实生产年。**没有实车铭牌/车架代码/匹配 OEM 数据时，不允许写“2011 Probox 的机油型号、变速器型号和维修阈值”**。

卖家宣称检查/平台声称 verified 也不能当作 ChatGPT 独立核验了 VIN、发动机型号或选配；本研究不需要也不保留车牌、手机号或卖家身份。

## 3. Toyota 原始资料直接支持的车型/总成分界

| OEM 车型时期 / 日本市场来源 | 可核实的产品家族差异 | 可关联的知识任务 | 不能从该行反推的内容 |
|---|---|---|---|
| **2002 发布的 Probox / Succeed 家族** | Toyota 官方《75 Years of Toyota》列示 **2NZ-FE 1.3L 汽油、1NZ-FE 1.5L 汽油、早期 1ND-TV 柴油**；柴油版随后停止销售；传动为 **4 速 AT 或 5 速 MT**，另有 1.5L 的四驱等选项；Probox 与 Succeed 的定位和部分车身尺寸不同 | 适用范围发现、通用发动机润滑结构、传统 AT 的边界、柴油架构另立切片 | 不可把所有早期车都断言为 1NZ-FE / 4AT，也不可把日本 2002 车型直接变成缅甸任意年份实车配置 |
| **Toyota 2003 CNG 专门变型** | 官方 Toyota 75 年史提及 1NZ-FNE CNG 变型的存在 | 将燃料供给与控制差异列为候选 `VAR-PROBOX-CNG`（未准入） | 不能由该产品史推断缅甸挂牌中的普通汽油车是 CNG |
| **2014 日本市场改款 Probox / Succeed** | Toyota 2014 官方新闻：Probox 配置 1.3L **1NR-FE**（仅 Probox）、1.5L **1NZ-FE**，与 **Super CVT-i** 的版本结合；同时公布制动/车辆稳定性等改进 | 车型家族年代/发动机/传动变化，`SER-DELTA-PROBOX-TRANS` 候选及可变机理范围 | 不能把“2014 年日本新款 CVT”套给 2007/2011 等旧车，更不能由 “Automatic” 推导“CVT” |
| **Probox vs Succeed 共享与差异** | Toyota 官方称相关产品家族，但早期车身空间尺寸不同；2014 日本官方价格/配置区分两名称 | 跨系列知识共享索引 + 差异附注 | 不可假定两车每个发动机、转向机、制动件、车架和控制程序完全一样 |

**Toyota 原始资料来源（明确来源的年款范围）**：
- [TOYOTA: 75 Years of Toyota — Probox 车型历史/参数](https://www.toyota-global.com/company/history_of_toyota/75years/vehicle_lineage/car/id60012554B/index.html)，历史节点，包含 UB-NCP51V/NCP50V 代表性型号和引擎代码。
- [TOYOTA: 75 Years of Toyota — Succeed 车型历史/参数](https://www.toyota-global.com/company/history_of_toyota/75years/vehicle_lineage/car/id60006139B/index.html)，关联车型及 2002 年家族说明。
- [TOYOTA: Probox / Succeed 2014 日本市场改款公告](https://global.toyota/en/detail/3737378)，1NR-FE/1NZ-FE、Super CVT-i 及日本版配置/安全设备明确以该公告时间为限。

以上均为厂商材料，**不是已浏览匹配缅甸具体 VIN 的 Toyota TIS 维修手册**；产品发布的配置表不能用于生成具体机油压力/扭矩/ATF 或诊断维修的车型级确定事实。

## 4. 实际产生维修价值的五组变型问题

### 4.1 发动机家族与润滑/供油条件

`2NZ-FE / 1NZ-FE / 1NR-FE` 并非一个完全相同的发动机代码。已有共享 [STR-ENG-LUBE](../../../../topics/engine/lubrication/structure.md)（仅通用油路）能帮助建立泵、滤清、调压、主油道、VVT 及冷却/回油概念，**但不能证明**某款 Probox 上实际的油泵结构、滤芯旁通设置、传感测点和压力阈值。后续仅在明确机型/年款/OEM 资料时才做 `SER-DELTA-PROBOX-LUBE` 实质差量；未证实则 `BLOCKED_SOURCE`。

### 4.2 传动型式的断裂点（高价值、优先）

2002 家族含 4AT/5MT；2014 日本改款含 Super CVT-i。可以明确**不应跨代复制 AT 机理、油液规格或排故思路**。现有 [STR-AT](../../../../topics/transmission/automatic/structure.md) 仅限“液力变矩器＋行星齿轮＋液压执行”家族，作为**对照/适用性排除**；对 CVT/MT 不是技术前置。后续需要先发现实际车架/驱动/变速器代码与生产范围，才能把特定技术关联到缅甸现车。**不能从旧车标题 Automatic 推断是否 4AT 或 CVT。**

### 4.3 2WD / 4WD 与传动、底盘及轮端

Toyota 2002 产品家族有 1.5L 四驱变型；具体尾桥、分动、差速和轴承结构是否与 2WD 不同，只能作为明显需要研究的部件家族差异。无需生成所有车架型号完整文章，先将 `DRIVELINE_VARIANT=UNKNOWN_UNTIL_CHASSIS` 记录下来。

### 4.4 车身/货物用途与悬架、制动结构

Toyota 历史材料说明 Probox/Succeed 早期后悬架与载货用途设计及相关车身尺寸不同；这说明通用结构稿需要映射各车型安装位置/承载设计，而不是提供某辆车的可执行载荷试验或私自修改制动/悬架设定。车辆的真实使用强度、改装、维修历史仍 UNKNOWN。

### 4.5 维修资料、零件和市场版本

JDM 车型可能通过车架号而非北美格式 VIN 识别配置。所有 OEM 零件号、发动机/变速器序号、ECU 软件、制造区间与适用保养规范均要通过适当版本的 Toyota 官方数据或可靠实际车辆证据验证。缅甸销售平台只是当地覆盖线索，不能替代配置核实。

## 5. 车型系列发现所得：当前可判定与不能判定

| 字段 | 当前结论 |
|---|---|
| `series_id` | `TOYOTA_PROBOX`，相关名称 `TOYOTA_SUCCEED` 独立记载 |
| `market_scope` | Myanmar used-car/trading candidates；**不是 stock-top-N** |
| `OEM_source_region` | 日本原始产品史及 2014 日本车型公告 |
| `generation_or_build_range` | 2002 家族与 2014 改款是确定的**技术版本研究切点**；具体车辆年款和生产日期 UNKNOWN |
| `component_families` | 早期 2NZ-FE/1NZ-FE、部分 1ND-TV/CNG；2014 1NR-FE/1NZ-FE；**仅在适用的官方版本内** |
| `transmission_families` | 早期 4AT/5MT；2014 日本 Super CVT-i；具体缅甸挂牌车 UNKNOWN |
| `powertrain_and_drive` | 日本官方文献中存在 FF/4WD、汽油/柴油/CNG 等**特定时间点变型**；当前缅甸目标车辆 UNKNOWN |
| `repair_procedures_and_limits` | **UNKNOWN：无匹配 OEM 车型维修版次** |
| `stock_population/rank/fault_frequency` | **UNKNOWN：无可用全缅甸分车型统计/工单分母** |
| `source-rights` | 只原创归纳可见资料，不复制官方原图、付费维修手册正文或挂牌照片 |

## 6. 实质差量触发/停止决定

- **`SER-DELTA-PROBOX-TRANS`：CANDIDATE_MATERIAL_DELTA**。有 Toyota 官方证实“早期 4AT/5MT vs 2014 CVT”的构型差异，确实会改变传动结构与诊断思路。**可进入独立差量 Writer 候选**，但写成“版本适用性对照”而非无证据的缅甸实车维修步骤；需独立 Claim/Reviewer，不能在本 DISC 中冒充已交付该 delta。
- **`SER-DELTA-PROBOX-LUBE`：SOURCE_GAP / CONDITIONAL**。只见 1NZ/2NZ/1NR 等发动机家族差异，未直接读取各家族润滑油路的 OEM 工程差量；**不得凭发动机代码不同捏造具体油路/压力差异**。可先搜集各对应 Toyota 技术资料，若并未找到实质结构差异则 `NO_MATERIAL_DELTA_YET`。
- **`SER-VARIANT-CHECK`：WAITING_EVENT**。必须至少一个真正的 delta Markdown 交付才能触发，不因本文件完成便偷设为 READY。
- **`SER-REPLAN`：WAITING**。未来对新增车型或配置必须根据真实输入增量校验主图+子图拓扑无环、稳定 ID、唯一写集、必要独审；本发现稿不能新增未准入车辆系列节点。

## 7. 反例与质量保护

1. **错误**：“挂牌是 2011 Probox，必然是 2011 年产。” 反例：当前单条卖家页面标题 2011，生产年份字段 2012；无实车核验。
2. **错误**：“Succeed 和 Probox 同一零件套装。” 反例：Toyota 历史材料显示车身长度等区别，且发动机/装配条件随版次不同。
3. **错误**：“只要写 Automatic，就代表 CVT。” 反例：Toyota 早期 4AT，2014 特定版本 Super CVT-i；两者不能由挂牌短标题区分。
4. **错误**：“Probox 都是汽油前驱。” 反例：历史官方记录中另有柴油、CNG 与四驱变型；**不等于它们都在缅甸当地挂牌中出现**。
5. **错误**：“4AT 就一定等于已证明某具体 Toyota 变速箱代码和 ATF。” 反例：没有 VIN/维修资料/变速箱铭牌，不得从挡位数推定专有编码、油液规范和维修参数。
6. **错误**：“Probox 在二手新闻中受欢迎，所以发生率最高。” 反例：媒体报道不是维修工单或全车保有量统计。

## 8. 后续真正需要的证据与移交

**适用性资料缺口**：具体车辆 VIN/车架和铭牌（可去敏后记录代码类别）、制造年月及地区、发动机/变速器代码、驱动形式、Toyota 匹配版次 OEM 服务说明、真实维修零件对应与改装/更换记录。没有这些就只能保持 `L3 SERIES DISCOVERY`，不能宣布 L4 配置完整。

**后续推荐**：优先通过 Probox 的实际车架/变速器配置来源分辨“旧 4AT 或 5MT / 2014 CVT”，再为可验证系列差异形成内容深度合格的 `SER-DELTA-PROBOX-TRANS`。润滑 delta 需真实家族油路差异来源，不强制凑文章。

**结论**：本篇实际完成“为何选这条缅甸存量研究系列、有哪些厂商证实的变型、哪些 OEM/市场事实 UNKNOWN、何时真正拆差量”的**系列发现**，不等于整个汽车技术知识或专业事实资格已经完成。
