# 缅甸旧车 Suzuki Swift：2007–2013 汽油机与 CVT/4AT/5MT 车型差异发现（SER-DISC-SWIFT）

> TASK_ID：`SER-DISC-SWIFT` · MAIN：[parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) · 格式：原生 Markdown。  
> 缅甸存量车优先计划：[MYANMAR_FLEET_PRIORITY_R1.md](../../../../MYANMAR_FLEET_PRIORITY_R1.md) Blob `9b6c66311da069b28d2b1681bf98b0723e193ea3`，不同对话审核 [#7013143644](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7013143644)，正式准入 [#7013561465](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7013561465)。  
> **阶段/资格**：`MODEL_GENERATED_UNVERIFIED / GENERATED_REVIEW_PENDING`、`OEM_VIN_N3=NOT_GRANTED`。当前只把缅甸历史旧车交易线索与 Suzuki 日本官方版本分账：不含缅甸任何具体 VIN、ECU/TCM 版本、原厂维修步骤、零件互换证明或故障发生率。

## 1. 为什么研究缅甸 Swift，但不能照搬日本全部配置

[Myanmar Digital News / GNLM 2022 年二手车报道](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand)在 2022-09-29 的交易报价中明确列出 **2011/2012 Suzuki Swift**。这支持 `MARKET_EVIDENCE_TYPE=LOCAL_USED_TRADE` 和 `MARKET_EVIDENCE_DATE=2022-09-29`，不能说明 2026 缅甸注册数量、各代份额、实装发动机或“通病”概率。Swift 海外出口市场、由日本进口的 Swift、本地卖家标题中的车型年份，仍需分别核对。

Suzuki 日本本土 2007 和 2010 公告本身给出了**不同的变速器家族**：2007 年的部分 1.3/1.5L 等级配 4AT，1.2L 部分配 CVT，另有 MT；2010 年的该日本新款主表则有 K12B、5MT、**带副变速机构的 CVT**、2WD/4WD。这使“Swift 自动挡”绝不是完整且安全的维修技术识别对象。

| 命名/来源 | 本阶段可以说的事实 | 不能借此认定 |
|---|---|---|
| `MYANMAR_USED_SWIFT_2011_2012` | 2022 本地旧车报道出现过相应年份的 Swift 报价 | 2026 年这两个年款占全国 Swift 最高份额，或配件一定与日本市场某款相同 |
| `JAPAN_SWIFT_2007_MODEL_REVISION` | Suzuki 原始 2007-05-24 公告明确 K12B 1.2L/CVT 与 1.3/1.5L 的其他变型 | 所有 2007 缅甸 Swift 必定装 K12B+CVT、或 2007 所有 Swift 没有 4AT |
| `JAPAN_SWIFT_2010_NEW_SERIES` | Suzuki 2010-08-26 原厂发布明确新的 1.2L DOHC VVT / K12B 家族、副变速 CVT、5MT、2WD/4WD | 缅甸 2011 号称 Swift 的车辆实际生产期、等级与原厂设计一一对应 |
| `JAPAN_SWIFT_2013_TECH_REVISION` | Suzuki 2013 有 Dualjet/Ene-Charge 分支 | 任何 2011/2012 Swift 必有双喷嘴、启停或能量管理 |

## 2. 原始厂商资料的技术与年份矩阵

| 日本原厂资料切片 | 可以确认的产品配置 | 为什么对后续维修知识重要 | 局限 |
|---|---|---|---|
| **2007-05-24 Swift 部分改良** | [Suzuki 官方公告](https://www.suzuki.co.jp/release/a/2007/0524/index.html)：在某些 2WD Swift/Swift Style 上配 `K12B 1.2L + CVT`；同一表出现 **1.3L 5MT**、某些 **1.3/1.5L 4AT**、Swift Sport **1.6L MT/AT** 等条件化版本 | 不能将“起步迟滞/升档冲击/油温”等症状一律归类 CVT：有级 4AT 的控制、手动离合、机械 CVT 传力路径不同 | 仅日本所列车种/年份和等级有效 |
| **2010-08-26 全新 Swift 日本版** | [Suzuki 2010 官方新车表](https://www.suzuki.co.jp/release/a/2010/0826/index.html)：`1.2L DOHC VVT`、`XG/XL 2WD 5MT 或 CVT`，`XG/XL/XS 4WD CVT`，XS 2WD CVT；技术页明确 **两档副变速机构 + CVT**，以及前支柱与后扭力梁、可变转向齿比和具体等级制动差异 | 同时代内仍有 MT、CVT、2WD/4WD、等级制动装备分叉。带副变速机构的 CVT 不可被认作普通 4AT 的固定四挡或全车无机械级变速结构 | 2010 日本型式≠缅甸 2011/2012 实车配置证明；具体变速箱型号/油液 UNKNOWN |
| **2013-07 Swift 技术分支** | [Suzuki 2013 日本 Dualjet / Ene-Charge 发布](https://www.suzuki.co.jp/release/a/2013/0717/index.html)：在特定车上提供较新燃烧/喷油与能量管理方案 | 不能把 2013 以后系统和 DTC 倒推至旧 Swift；不同发动机和节能系统影响低压与喷油诊断知识 | 不说明缅甸相应年份实装 |
| **Suzuki 数字图书馆历史** | [官方 Swift 历史](https://www.suzuki.co.jp/suzuki_digital_library/1_auto/swift.html)：产品和技术家族持续演化 | 支持先按制造时期划范围，再复用共享发动机/传动知识 | 是品牌技术史；不能替代生产车架/部件适用资料 |

**细节注意**：2010 Suzuki 原始公告中 ``XS` 在日本某配置可有 ESP 和不同前/后制动硬件等级，**绝不**由这项事实断言缅甸某一 Swift 有 ESC、后盘式制动、线控制动或相同轮速信号。硬件、等级、安全装备和驱动型式与同一名称下不同实车不能任意互换。

## 3. 从车型结构到正常工作：为什么二手 Swift 不能统一诊断

### 3.1 先分动力与燃油/点火版本

K12B 1.2L 的不同年代 VVT、喷油与节能装置可以由 Suzuki 对应公告研究，但真正车辆的燃油压力、点火系统、氧传感器、空气计量、冷却、低压电气和 ECU 策略必须依据具体引擎/版本。**发动机运转不稳**可能有燃油、点火、进气、传感器、机械或低压控制多种竞争解释，不能凭 Swift 品牌直接指认零件。

旧报告 `ENGINE_CODE=UNKNOWN_LOCAL`，不得自动写入 `K12B`、`M13A`、`M15A`、`M16A` 其中一个，也不把日本 VVT 公告中的排放数值当缅甸车辆的检测要求。

### 3.2 CVT、副变速器、有级 4AT 与 MT

- **2007 部分日本 Swift 4AT**：维修理论关注有级固定档位、液力/机械执行、离合/制动与控制（具体变速器总成尚未认定）。可复用项目已审[传统行星液力 AT 结构](../../../../topics/transmission/automatic/structure.md)的限定机理，不能把 4AT 当作 CVT 带轮无级变比。
- **2007 或 2010 特定 CVT**：需求是连续变比、离合/起步耦合、油压/夹持与温度的条件机理。2010 Suzuki 资料明确有 **副变速机构的 low/high 两档**，但这不等于所有 Swift CVT 完全一样，也不授权未查证总成的具体齿比、CVTF 或诊断测压。
- **5MT**：离合器分离、同步器、选择机构与变速器本体是独立机制；即使驾驶者报告“打滑”“有冲击”，不能强行套用 CVT 夹紧不足或 AT 换挡阀失效。
- **4WD**：原厂 2010 某些等级 4WD-CVT 存在，轴端/后驱传动差异需要实际布局证据；不能将 2WD 前半轴、轮端或差速件作通用互换判断。

**证据类型**：可以记录车辆合法身份、车架与制造时间、真实变速器类型/标识与 OEM 匹配来源、既有用户症状和客观专业资料；这些是推理输入而不是要求普通车主拆检/路试的操作步骤。

### 3.3 悬架、制动和车身版本为什么同样要条件化

2010 原厂资料有特定款 **前麦弗逊支柱/后扭力梁** 及按等级区分制动装置。基于某日本版本的结构，我们可以组织制动效能、轮胎附着、弹簧阻尼、转向控制之间的知识，但不能声明缅甸 2007/2011/2012 全部 Swift 后轴零件、ESC、方向机或后轮制动型式一致。车辆负载与磨损频率也不能从厂商年款表推算。

## 4. 当前对维修最有价值的未回答任务（尚未准入）

| 候选后继 Task | 可执行前置 | 实际增量价值 |
|---|---|---|
| `SER-DELTA-SWIFT-TRANS` | 有真实缅甸 Swift 实车动力/变速器/出厂版本证据及原厂资料 | 区分 2007 4AT 与 2010 带副变速机构 CVT、5MT；避免错误油品/阀体/传动假设 |
| `SER-DELTA-SWIFT-ENG` | 匹配 K12B 或其他真实装备发动机，明确制造/市场来源 | 区分不同 VVT/喷油/节能控制，避免把 2013 技术倒填旧车 |
| `SER-DELTA-SWIFT-BRK-SUSP` | 实际制动/ESC/悬架的车型等级和硬件来源 | 失效从摩擦制动、轮胎附着、悬架定位、助力/电子控制中正确分叉 |
| `SER-DELTA-SWIFT-LOWV` | 实际蓄电/充电/启停规格得到 OEM 版本证据 | 不把 Ene-Charge 的电能管理假设强加给早期普通汽油 Swift |

这些只是研究候选，必须依实际缅甸车型与维修问题发生价值进一步做最小计划审核。**不按年款×系统自动填空**。

## 5. 反例、停止条件及安全边界

| 常见错误假设 | 可证伪反例/限制 |
|---|---|
| “Swift 2007 全部是 CVT” | Suzuki 2007 日本原始表同时列 5MT、4AT 版本，部分 1.2L 才是 CVT |
| “2011 Swift 的 CVT 等于某个 2007 Swift 的 CVT” | Suzuki 2010 日本推出带副变速机构的另一技术切片；是否等同具体车要依实装总成证明 |
| “所有 Swift 都是 K12B 1.2L” | 同一 2007 表有 1.3/1.5/1.6L 其他选项；出口版更需单独核证 |
| “2010 Swift 都有 ESC 和后盘刹” | 原厂页面按等级/驱动限定相关制动配置，不能用一条产品宣传推广所有款 |
| “2013 Ene-Charge 是旧缅甸 Swift 共同问题” | 没有实车和本地需求来源；不得为此扩张无关电驱/BEV 通用故障树 |
| “二手交易文章证明这是全国最高故障率车型” | 交易相关性不等于注册数量或实际维修工单分母 |

制动效果明显不足、方向失控、过热、严重转动异常需停止正常使用并由专业人员处理。本文不是维修施工指令：不提供制动放气、ABS 诱发测试、危险道路试验、车辆举升拆卸、电子执行器动作、具体油液/压力/扭矩/零件匹配数值。`SAFE_TO_DRIVE=NOT_GRANTED`。

## 6. 来源与版本范围账本

| 可复核来源 | `evidence_type / evidence_date / region` | 可支持结论及限制 |
|---|---|---|
| [Myanmar Digital News / GNLM](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand) | `MYANMAR_USED_TRADE / 2022-09-29 / MYANMAR` | 当时列 Swift 2011、2012 报价；不代表现时全国车量 |
| [Suzuki 2007 Swift 产品变更](https://www.suzuki.co.jp/release/a/2007/0524/index.html) | `OEM_JAPAN_GRADE_TABLE / 2007-05-24 / JAPAN` | 1.2L K12B/CVT 与 1.3/1.5L MT/AT 等同年多分支 |
| [Suzuki 2010 新 Swift](https://www.suzuki.co.jp/release/a/2010/0826/index.html) | `OEM_JAPAN_GRADE_TABLE / 2010-08-26 / JAPAN` | 1.2L VVT、CVT 副变速机构、5MT、2WD/4WD 和制动等级差异 |
| [Suzuki 2013 Dualjet / Ene-Charge](https://www.suzuki.co.jp/release/a/2013/0717/index.html) | `OEM_JAPAN_OPTIONAL_TECH / 2013-07-17 / JAPAN` | 较新节能技术为版本差异；不证明旧缅甸 Swift 有此装备 |
| [Suzuki 数字产品史](https://www.suzuki.co.jp/suzuki_digital_library/1_auto/swift.html) | `OEM_HERITAGE / JAPAN` | 跨代产品历史；不是任意 VIN 的服务手册 |

`model_family=SUZUKI_SWIFT`，`market=MYANMAR_USED_FLEET_RESEARCH_CANDIDATE`，`chassis_code=UNKNOWN_LOCAL`，`production_month=UNKNOWN_LOCAL`，`region_import_origin=UNKNOWN_LOCAL`，`engine_code=UNKNOWN_LOCAL`，`transmission=UNKNOWN_LOCAL`，`equipment=UNKNOWN_LOCAL`，`publisher_source_version=SUZUKI_JP_2007_2010_2013`，`national_stock_rank=UNKNOWN`，`failure_rate=UNKNOWN`，`OEM_VIN_N3=NOT_GRANTED`。

交付后的另一不同对话负责审核当前 Exact Git Blob、厂商资料范围与缅甸候选适用性，并回写 `ACCEPT_SCOPED_GENERATION_ONLY` 或 `REWORK` / P0/P1/P2；原 Writer 不自签。
