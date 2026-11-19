# 缅甸存量 Toyota Vitz / Yaris：年款、发动机、CVT/MT 与驱动差异发现（SER-DISC-VITZ）

> TASK_ID：`SER-DISC-VITZ` · 主控：[parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) · 单文件 Markdown 第一阶段知识生成。  
> R17 缅甸车型优先计划：[MYANMAR_FLEET_PRIORITY_R1](../../../../MYANMAR_FLEET_PRIORITY_R1.md) Blob `9b6c66311da069b28d2b1681bf98b0723e193ea3`，独立计划审核 [#7013143644](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7013143644)，正式准入 [#7013561465](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7013561465)。  
> **`MODEL_GENERATED_UNVERIFIED / GENERATED_REVIEW_PENDING`**。本稿对日本 Toyota 原始发布和缅甸历史二手车市场做**可追溯的关联研究**，没有当前缅甸 VIN/车架/ECU/总成核实，不提供原厂专属维修值、施工步骤或“最常见故障率”。`OEM/VIN/N3=NOT_GRANTED`。

## 1. 为什么 Vitz 应纳入缅甸在用车型维修知识

2022 年 9 月 29 日 [Myanmar Digital News / GNLM 汽车市场报道](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand)明确提到 **2007、2008、2009 Toyota Vitz** 的当时二手市场报价。这是市场交易讨论和报价例证，并非截至 2026 年的全国车型保有量统计，不能推出 Vitz 排名、年款比例或车型故障概率。

Toyota 2010 年的日本 [第三代 Vitz 官方发布](https://global.toyota/en/newsroom/toyota/24139993.html)指出，海外部分地区采用 **Yaris** 名称，但“Vitz=Yaris”只是车型家族/市场命名线索：不同地区的年款、发动机、变速器、排放与安全配置不一定一致，**不能将日本某一销售配置按名称映射到缅甸具体进口车**。缅甸的单条卖家挂牌或车型名称同样无法确认确切出厂年月。

| 证据对象 | 有证据的结论 | 没有证据的结论 |
|---|---|---|
| 缅甸 2022 年二手市场 | 报道曾讨论 2007–2009 Toyota Vitz 的价格及市场参与 | 2026 全国 Vitz 保有量/排名；缅甸车都搭载哪一种发动机 |
| Toyota 2005 日本第二代发布 | 存在多款汽油发动机、CVT/驱动与配套技术 | 任何在缅甸登记的 2007 Vitz 一定采用该日本某一等级 |
| Toyota 2010 日本第三代发布 | 1.0/1.3/1.5L 发动机、Super CVT-i、RS 手动车、部分四驱配置存在 | 2007–2009 缅甸二手车可使用 2010 新世代配置清单 |
| Toyota 2017 日本 Vitz Hybrid 发布 | 日本市场后来新增 THS II 混动款，仍有纯汽油车 | 2017 混动车已经是缅甸 Vitz 主流，或 2008 Vitz 必有高压动力系统 |

结论是：本地市场证据使 **Vitz 旧车成为值得优先调查的维修候选**；Toyota 厂商公告使**按实际代际和动力/变速器版本分支**成为必要。两类来源不可以拼成未经验证的 VIN 装配清单。

## 2. 原始 Toyota 公告所支持的车型版本矩阵

| 车型时间切片 | Toyota 日本原始资料 | 已可确认的差异 | 缅甸适配边界 |
|---|---|---|---|
| **2005-02 发布第二代 Vitz** | [Toyota 2005 官方发布](https://global.toyota/en/newsroom/toyota/24119734.html) | 1.0/1.3/1.5L 车型家族，公开资料出现 `1KR-FE`、`2SZ-FE`、`1NZ-FE` 等发动机；日本前驱配置中的 `Super CVT-i` 以及随等级变化的驱动/舒适安全功能 | 不能直接宣称 2007、2008、2009 缅甸每辆 Vitz 都是某一发动机、CVT 或相同制动/悬架 |
| **2010-12 日本新第三代 Vitz** | [Toyota 2010 原始车型配置表](https://global.toyota/en/newsroom/toyota/24139993.html) | `1KR-FE 1.0L`、`1NR-FE 1.3L`、`1NZ-FE 1.5L`，各等级对应 Super CVT-i；`RS` 表列 5MT 与 Super CVT-i 选择；`1NR-FE` 部分等级有 2WD / 4WD 分支 | 本次公告的 2010 发售配置不回填旧版；日本发布月不等于缅甸车架生产或进口年月 |
| **2017-01 日本小改款加入 Hybrid** | [Toyota 2017 官方发布](https://global.toyota/en/newsroom/toyota/24129866.html) | 纯汽油车依旧存在，同时有 **THS II + 1NZ-FXE** 混动等级；这不是同一机械 Super CVT-i 的默认动力流 | `MYANMAR_HYBRID_VITZ_SHARE=UNKNOWN`；没有当地真实车或维修需求证据时**不启动纯电/混动通用扩张** |

**重要物理分界**：即使 Toyota 品牌均使用 “CVT” 类名称，普通汽油 **Super CVT-i 机械无级变速器**与 2017 所列 **THS II 混动减速器/电机能量转换**不应在失效机理、油液、控制命令和维修方式上混同。本文只做年份排除边界，不给混动车现场操作步骤。

### 2.1 可用于下一轮逐车查证的标识，不是既成 VIN 事实

- `MODEL_SERIES_NAME=VITZ / YARIS (REGION_SCOPED)`，`MYANMAR_MARKET_USE=2022_HISTORICAL_USED_TRADE`。
- `EXAMPLE_OEM_JP_ENGINES=1KR-FE|2SZ-FE|1NZ-FE|1NR-FE`；这些是上述日本产品时期的可见家族，不代表全部发动机/年款/地区。
- `EXAMPLE_OEM_JP_TRANSMISSIONS=SUPER_CVT_I|5MT_RS`；某个版本可能有其他技术配置，不能凭一个发布表默认排除未审市场。
- `EXAMPLE_JP_DRIVE=2WD|SELECTED_4WD`；发布页能证明这两种选项在部分时期存在，却不能确证缅甸具体车辆的差速器、后桥或维修零件。
- 对实际缅甸 Vitz/Yaris 必须进一步确认 `CHASSIS_CODE=UNKNOWN`、`PRODUCTION_MONTH=UNKNOWN`、`IMPORT_ORIGIN=UNKNOWN`、`ENGINE_CODE=UNKNOWN`、`GEARBOX_CODE=UNKNOWN`、`DRIVE=UNKNOWN`、`ABS_ESC_FITMENT=UNKNOWN`、`ECU_VERSION=UNKNOWN`。

本文没有用未经检验的卖家标题/单一网络车架解码表填入这些字段。

## 3. 面向真实维修价值：车型版本如何改变知识 DAG

### 3.1 汽油/进气燃油控制的差异入口

已确认为 **1KR-FE / 1NR-FE / 1NZ-FE / 2SZ-FE** 中某个真实发动机，才根据该总成的原厂系统图理解进气、点火、喷射、气门正时、冷却与润滑；同样的冷启动不稳、油耗异常、过热或报码可以是传感、供油、空气漏入、点火、机械或线路的多种竞争原因。**不能以 Vitz 名称生成“一种喷油嘴、某个 DTC、统一火花塞/机油标准”。**

2010 Toyota 原厂 `1NR-FE` 是其特定阶段 1.3L 双 VVT-i 产品差异；此处不据其营销表述直接推定缅甸 2007 Vitz 具有相同正时执行器。

### 3.2 CVT 与 RS 5MT 是维修知识不同的分叉

- **若总成被证实是汽油 Super CVT-i**：通用机械 CVT 问题空间包括目标变比与实际转速、夹紧/油压与温度、发动机扭矩/起步耦合和控制信号。Toyota 2005 页面提及紧凑液力变矩器，说明**“有变矩器”不等于传统多挡行星 AT**。不能在不知道 CVT 总成型号时指定某种油品、带/链材质、油压、拆装或故障概率。
- **若是原厂 2010 日本 RS 5MT 对应配置**：驱动请求→离合器/人为选挡→固定机械速比→差速器/轮端；其离合、换挡杆、同步器和轴承等证据不能用 CVT 带轮夹持问题替代。
- **若采用四驱等配置**：车速/轮速差、传动轴/差速总成、轮胎等会改变噪声、振动和驱动力的竞争因果关系，必须以对应的实际车架/原厂硬件布局为依据。
- **若仅看到 “Automatic”**：不能从卖家宣传判断具体为 Super CVT-i、普通 4AT 还是其他地区销售变体；`TRANSMISSION_FAMILY=UNKNOWN`。

本段仅为技术类别的受限推理，引用项目已审通用知识时必须按实际传动家族选相应模块，禁止一次复制所有 CVT/AT/MT 到每个 Vitz 年款。

### 3.3 车身、制动与低压电子不可直接按“新一代”升级

2005 Toyota 公告体现特定配置的车身安全、智能启动、空调等新设计，但它们可能是选配，因地区/等级/制造期不同而变化。尤其 `Smart Entry/Start`、`ABS/ESC`、`Stop & Start`、某种电池/启停控制架构，不可无 OEM 型号证据就认定缅甸任意 Vitz 必装。低压系统故障也不能由动力总成类别单因确定。

## 4. 结构→功能→失效→诊断维修的最小差量任务候选

| 后继知识候选（尚未准入） | 有效触发条件 | 为什么对真实缅甸旧车维修有增量价值 |
|---|---|---|
| `SER-DELTA-VITZ-TRANS` | 车架/出厂日期/变速器总成来源证实实际 5MT/CVT 或其它变速器 | 避免自动变速器误分类、错误诊断/油品/部件匹配；复用已审通用 AT/CVT/手动原理 |
| `SER-DELTA-VITZ-ENGINE` | 对应实车发动机代号可证实，且有具体配置差异 | 特定气门/燃油/点火/冷却的真实部件差异，防止把 2010 1NR-FE 套给 2008 1KR-FE |
| `SER-DELTA-VITZ-STEER-BRK` | 逐车确定 ABS/EBD/电助力等实装和厂商资料 | 同一警报/制动/转向症状的竞争原因可按真实系统切片分流，不猜测装备 |
| `SER-DELTA-VITZ-HVAC-LOWV` | 配置不同的空调、启停、发电机、智能启动或线路得到证实 | 减少以“Vitz 全车型一样”替换错件或归因错低压/热管理 |
| `SER-VITZ-YARIS-CROSSMARKET` | 当地实际车辆进口来源能区分日本 Vitz 与别的国家 Yaris | 对接地区车型历史，禁止因为英文名称相近而混用原厂服务版本 |

新候选仅作动态发现，**没有被本稿授予新 DAG 入场资格**；项目重点仍是缅甸有市场证据的在用旧车，而非所有 Toyota 全球版本的百科。

## 5. 反例与知识有效性的 STOP

| 看似合理但错误的假设 | 反例/证据分离方式 |
|---|---|
| “缅甸 Vitz 都是 2010 年那代” | 缅甸 2022 报道的二手样本明确列 2007–2009；Toyota 2010 是**新上市版本**，不能倒推 |
| “Vitz 和 Yaris 名称一样，配件可以通用” | Toyota 的跨地区名称不等于车架、驱动、发动机、ECU 或安全部件适用一致 |
| “1.3L Vitz 肯定是 1NR-FE” | Toyota 2005/2010 车型所列 1.3L 发动机家族有时间差异，先证实生产期 |
| “所有 Vitz 自动挡都是同一 CVT，总可以用一种油” | 只证明某个日本配置表的 Super CVT-i，不知道缅甸具体箱型、油液、年款；同年不同装配可能不同 |
| “有 CVT 一定没有变矩器” | Toyota 2005 原始资料明确提到相关 CVT 结构的紧凑液力变矩器 |
| “2017 Vitz Hybrid 出现，缅甸旧 Vitz 都要扩充高压维修” | 2017 日本混动发布不能证明缅甸 2007–2009 二手车装配混动或本地维修需求高 |
| “仪表报码能直接确定换哪个总成” | 需要真实适用的 OEM 控制逻辑、工况、实体量与竞争原因；此生成研究未提供专业诊断结果 |

对于严重制动不足、转向失效、发动机过热或不确定高压系统风险，停止正常使用并由合格专业人员根据具体车型技术资料处置。本文不含制动放气、危险路试、启动机/高压拆装、带电测量、维修扭矩/油液数值或任何“可安全上路”授权。

## 6. 来源账本：发布日期不等于实车年份

| 来源 | `evidence_type / evidence_date / market_region` | 支持的有限事实 |
|---|---|---|
| [Myanmar Digital News / GNLM 市场报道](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand) | `LOCAL_USED_TRADE / 2022-09-29 / MYANMAR` | 当时市场列出 2007–2009 Vitz，不能推出 2026 全国排名 |
| [Toyota 日本第二代 Vitz 原厂发布](https://global.toyota/en/newsroom/toyota/24119734.html) | `OEM_PRODUCT_RELEASE / 2005-02 / JAPAN` | 第二代车型、发动机/传动/车身科技的原厂时间切片 |
| [Toyota 日本第三代 Vitz 原厂发布](https://global.toyota/en/newsroom/toyota/24139993.html) | `OEM_GRADE_TABLE / 2010-12-22 / JAPAN` | 1KR-FE、1NR-FE、1NZ-FE、Super CVT-i、部分 4WD、RS 5MT 按表格存在 |
| [Toyota 2017 日本 Vitz Hybrid](https://global.toyota/en/newsroom/toyota/24129866.html) | `OEM_GRADE_TABLE / 2017-01-12 / JAPAN` | THS II Hybrid 为后来增加的独立动力系统，不适用于未经核实的旧缅甸车 |
| [Toyota Vitz 产品历史](https://global.toyota/en/mobility/toyota-brand/gallery/vitz.html) | `OEM_HERITAGE / JAPAN_GLOBAL` | 厂商历史年代和代际对照；不是缅甸进口车实装证明 |

**持续未知**：`VIN_FRAME=UNKNOWN`、`MANUFACTURE_MONTH=UNKNOWN`、`IMPORT_ORIGIN=UNKNOWN`、`ENGINE_CODE=UNKNOWN`、`TRANSMISSION_CODE=UNKNOWN`、`DRIVE_ACTUAL=UNKNOWN`、`OEM_SERVICE_DATA=UNKNOWN`、`MYANMAR_2026_MODEL_SHARE=UNKNOWN`、`LOCAL_FAILURE_FREQUENCY=UNKNOWN`。如果后续获得真实车架和相匹配原厂资料，仅按新出现的技术差异生成车系 Delta，不反向更改已有知识为“已认证事实”。

下一动作：由**另一独立非 Writer 对话**按本文件 Exact Blob 进行 Source-First 生成质量审查，结果写回 `ACCEPT_SCOPED_GENERATION_ONLY` 或 `REWORK`，指出 P0/P1/P2；Writer 自己不得签收。
