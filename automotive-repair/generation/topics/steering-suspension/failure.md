# 转向助力与悬架失效的竞争机理及安全停止边界（FAIL-STEER-SUSP R23）

> TASK_ID: `FAIL-STEER-SUSP` · MAIN: [parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) · 独立准入：[#61/7021821148](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7021821148) · 派发：[#61/7021981579](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7021981579)。
> 直接上游：[转向、悬架和轮胎的正常功能 FUN-STEER-SUSP](./function.md)（SOURCE，本篇为其下游 FAIL 层），Exact Blob `3975342848e3f0883289dbfb73c81be50f331d5c`；结构前置 [STR-STEER-SUSP](./structure.md) Blob `1c84e3329bfcb40bcc2a01dac1b6af15ef5bfb40`；方法复用 [通用诊断方法 DISC-METHOD](../common/diagnostic-methods.md)，不重写结构与正常机理正文。
> 身份：`MODEL_GENERATED_UNVERIFIED` / `GENERATED_REVIEW_PENDING`；**OEM/VIN/N3=NOT_GRANTED**；不冒充 OEM 维修手册，不含故障率统计与任何现场作业授权。
> 主要问题：方向盘变重、跑偏、抖动、异响、车身弹跳出现时，如何在**转向助力失效（液压 vs EPS 按版本）、轮胎（气压/磨损/变形）、四轮定位、衬套/球头、减振器/弹簧、超载负荷**等物理上都成立的竞争机理之间用证据区分，哪些症状必须立即停止驾驶并移交？

## 1. 适用性先行：版本与车系边界决定哪一族假说合法

[Probox/Succeed 制动/悬架已接受差量](../../series/myanmar/toyota/probox/braking-suspension-variants.md)已确立的版本分界：Toyota [2014-08-06 日本改款公告](https://global.toyota/en/detail/3737378)原文「車速感応型電動パワーステアリングを全車に採用」确证 2014 改款后全系为车速感应 EPS（厂家同时把悬架优化目标绑定「空車時から積載時まで」）；改款前各 grade 转向形式为 `PRE_2014_STEERING_TYPE_PER_GRADE=UNKNOWN`。

| 研究对象 | 可进入本篇竞争矩阵的条件 | 明确不得做 |
|---|---|---|
| Probox 2014 改款后版本 | EPS 族（扭矩传感/电机/ECU/供电）与轮胎/悬架/载荷假说**并列** | 给出 EPS 标定、降级策略或部件参数 |
| Probox 2014 前或年款不明 | HPS/EHPS/EPS 三族**全部保留**，按油迹/泵声/供电线索分流（结构差异见 [STR-STEER-SUSP](./structure.md) 第 3 节） | 用挂牌年份断言助力族别——[发现稿](../../series/myanmar/toyota/probox/discovery.md) MMR-PB-02 的「Probox 2011」标题与「2012」年份字段自相矛盾 |
| Nissan AD Van/AD Expert | 商用载荷场景（重载/长期满载）作条件化假说；[AD Van 发现](../../series/myanmar/nissan/ad-van/discovery.md)中 `SER-DELTA-AD-LOAD-SUSP` 尚未准入 | 把 Wingroad 当「AD Van 高配」；宣称载荷致损的本地发生率 |
| Honda Fit / Suzuki Swift | 仅作已发现车系引用（[Swift 发现](../../series/myanmar/suzuki/swift/discovery.md)：2010 日本资料含前支柱/后扭力梁的等级限定表述） | 无 VIN/代际证据时套用任何具体转向/悬架硬件结论 |

无实车 VIN、铭牌与制造月证据时，`STEERING_TYPE`、`PART_FITMENT`、定位角/前束/胎压数值全部 `UNKNOWN`；本篇矩阵是**机理与证据区分知识**，不是对任何一辆缅甸车的诊断结论。

## 2. 失效机理分层：症状先归入五条物理路径

### 2.1 机械转向链（版本无关）

齿条与支承磨损产生**中间位置旷量与转向力不均**；外/内拉杆球头松旷伴随过坎异响、轮胎羽状磨损与漂移不定的跑偏；下球头磨损可改变轮端姿态观感，极端松旷存在**分离风险**（安全临界，见第 5 节）；转向柱中间轴/万向节卡滞造成转向阻力突变。这条链在 HPS 与 EPS 车上同样成立——「助力正常」不能排除机械链故障。

### 2.2 助力失效按版本条件化

| 助力族 | 失效候选对象 | 族征线索（非部件级结论） |
|---|---|---|
| HPS/EHPS 液压侧 | 泵、驱动皮带、油液泄漏与供流、阀/密封内漏 | 低速打方向的泵类异响、可见油迹、随怠速/转速/油温变化的手感 |
| EPS | 扭矩传感器、电机、ECU/供电/接地 | 仪表警告、助力左右不对称感、与车速相关助力变化的异常 |

Bosch 公开资料支持 EPS 存在柱式等多种构型（[Electric power steering systems](https://www.bosch-mobility.com/en/solutions/steering/electric-power-steering-systems/)、[Column EPS](https://www.bosch-mobility.com/en/solutions/steering/electric-power-steering-with-servo-unit-on-the-steering-column/)），ZF/TRW 支持 EHPS「电机泵＋液压执行」（[Function principle](https://aftermarket.zf.com/en/aftermarket-portal/knowledge-hub/function-principle-of-electrohydraulic-power-steering/)）——只证技术家族存在，不证明某缅甸车实装，也不提供任何降级安全承诺。助力消失后机械转向通常仍可施加，但**操纵力骤变本身是安全事件**。

### 2.3 轮胎/定位：跑偏的三个竞争来源

胎压左右不对称、轮胎锥形力（conicity，可来自制造或非对称磨损）、制动拖滞都能让车不走直线；路拱（road crown）造成的恒定轻微偏转属路面效应而非故障。NHTSA 轮胎安全资料支持轮胎状态与转向/稳定相关（[Tire Safety](https://www.nhtsa.gov/vehicle-safety/tires)）。本篇**不含任何前束/外倾/胎压/扭矩 SPEC 数值**。

### 2.4 悬架：储能、耗能、约束各自失效

弹簧塌陷或断裂先改变**承载与车高**（空/载姿态差变大、定位连带漂移）；减振器失效（漏油、内部阀系退化）丧失**耗能**——过坎后车身持续振荡、轮胎杯状磨损、高速接地不稳；衬套老化削弱**约束**，制动/过坎时几何漂移，把跑偏与异响连起来。Monroe 公开资料区分 shock/strut/弹簧职责（[Shocks vs Struts](https://www.monroe.com/technical-resources/shocks-101/shocks-vs-struts.html)），不构成某车安装方案与阻尼数值。

### 2.5 超载负荷（缅甸商用场景条件化）

Toyota 2002 后悬架设计动机即载货（4 连杆＋桶形非线性螺旋弹簧、减振器后倾，[75 年史 Probox](https://www.toyota-global.com/company/history_of_toyota/75years/vehicle_lineage/car/id60012554A/index.html)），2014 优化目标绑定空载到载重——设计层就承认**载荷改变转向悬架表现**。但实车载荷历史与超载失效率（`VEHICLE_LOAD_HISTORY`、`MYANMAR_OVERLOAD_FAULT_RATE`）为 UNKNOWN，只能作竞争假说，不作「必坏」断言。

## 3. 症状 → 竞争解释 → 有区分力的证据（核心矩阵）

每行假说物理上都成立；证据只调整可信度，冲突或缺失时出口是 `UNKNOWN`/移交，不是挑最贵的件换。

| 观察情境 | 竞争假说（均未证实） | 有区分价值的证据类型 | 不得直接下的结论 |
|---|---|---|---|
| **低速重、高速变正常** | 2014+ 车型 EPS 低速大助力未生效（供电/传感）；实为 HPS 族且低速辅助不足（油位/泵/皮带）；轮胎亏气或接地阻力大；机械链阻力 | 先落版本边界（2014-08 起才全系 EPS）；EPS 族看警告与供电线索，HPS 族找油迹/泵声；左右胎压相对差对照 | 无版本证据判「EPS 电机坏」；不因高速正常宣布「没问题」 |
| **平直路面恒定单侧跑偏** | 胎压不对称；轮胎锥形力；悬架衬套/几何漂移；伴发制动拖滞 | 平整路面双向对照（排除路拱）；**同轴左右交换轮胎——跑偏随胎翻转→轮胎侧，不变→几何/底盘侧**；拖滞伴轮端温升差 | 直接开四轮定位或换转向机；无参数时报任何定位数值 |
| **仅制动时跑偏/被拉** | 左右制动力不对称（[FAIL-BRK](../braking/failure.md) BRK-F07）；衬套/球头松旷在制动力矩下让几何移动；轮胎附着左右不均 | 松开制动是否立即回正；是否伴随踏板/异响异常；与「不踩制动也偏」的恒定跑偏分开 | 一律归转向器；或反称「制动没问题」——两族都保留 |
| **过坎「哐当/咯噔」** | 拉杆/下球头松旷；稳定杆连杆与衬套；减振器/支柱顶胶与轴承；弹簧座/断裂；非悬架源（排气、货物、备胎固定） | 异响与转向角度/制动/单侧坎/车速的关联描述；货载固定状态对照 | 凭一段声音直接换件；球头/支柱作业属安全件，移交 |
| **特定车速段方向盘/车身抖** | 车轮动不平衡；轮胎变形/鼓包/内部损伤；悬架旷量放大振动；制动盘厚差（踩制动才现） | 复现车速段是否稳定；踩制动后抖动变化；先抖的是方向盘还是车身 | 「动平衡后必好」；跳过旷量检查宣布悬架正常 |
| **直行蹭胎声＋异常磨损** | 定位连带磨损（羽状/锯齿状，常伴旷量）；杯状磨损＋阻尼丧失（减振器）；轮毂轴承；胎压/规格不一致 | 磨损形态记录（羽状 vs 杯状 vs 单侧）＋对应旷量/油迹证据；轴承声随转向加载变化 | 只补气/换胎不查减振器与旷量；给任何定位数值 |
| **过坎后连续弹跳、高速飘** | 减振器阻尼丧失；弹簧塌陷/断裂；超载超出弹性余量；胎压状态 | 空载 vs 载重车高/姿态对照；可见油迹＋杯状磨损组合；载荷历史分账 | 「弹两下＝减振器必坏」；用 2014 悬架优化表述反推老款「必然更差」 |
| **助力突然消失/警告灯亮** | EPS 供电/接地/ECU；扭矩传感器/电机；实为 HPS 族的泵/皮带/油路；助力正常仅主观口径 | 版本族别先行；仪表警告与供电线索；HPS 族油迹/皮带声；记录手感突变前后工况 | 无 OEM 后备策略证据时许诺「仍可安全驾驶」；**此行默认安全临界** |
| **空载正常、载重后重/响/跳** | 载荷超设计弹性/助力余量（商用超载，历史 UNKNOWN）；弹簧/减振器已退化被空载掩盖；轮胎载重状态不匹配（不给数值） | 载重对照复现；伴随的车高/磨损/油迹证据；2014「空車時から積載時まで」仅证明设计意图 | 无工单分母宣称「缅甸 Probox 必坏弹簧」类断言 |

## 4. 缅甸研究反例：错误出口与正确出口

### 案例 A：「2014 前 Probox 被按 EPS 诊断」

卖家挂牌「Probox 2011」（年份字段 2012，`SELLER_CLAIMED_YEAR_CONFLICT`），主诉低速转向重，按「EPS 扭矩传感器损坏」开件。反例：该年款转向形式 `PRE_2014_STEERING_TYPE_PER_GRADE=UNKNOWN`，EPS 传感推理整族可能不适用。正确出口：助力族别 `UNKNOWN`，HPS/EPS 两族并列、按油迹/泵声/供电线索分流；VIN/铭牌核实前不进部件级结论；严重时按第 5 节移交。

### 案例 B：「重载 AD Van 悬架异响被当轮胎」

AD Van 具 2022 本地交易可见性（[MDN 报道](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand)），商用重载场景下过坎异响，先行换胎无改善。反例：载荷场景下悬架族（衬套/减振器/弹簧）假说从未被排除，且 `SER-DELTA-AD-LOAD-SUSP` 未准入、载荷历史 UNKNOWN；「AD Van」称呼也可能混入 Wingroad。正确出口：悬架/轮胎/载荷三族并列，保留异响—载荷关联描述；安全临界则停止使用并移交。

### 案例 C：「卖家只写 2011 Probox、方向盘渐重，买方要求换方向机」

单条挂牌与字段冲突无法落到 L4 配置，方向机总成更换属高误修代价决策。正确出口：`STEERING_TYPE=UNKNOWN`、案例保留为候选研究对象；先采集版本族证据再谈部件；**本知识层只支持「停止推断、移交专业诊断」**，不支持任何换件顺序。

## 5. 安全 STOP：立即停止驾驶并移交

- **转向助力突然消失或操纵力骤变**（尤其高速/载重中）：立即安全停靠，停止驾驶，移交合格人员。
- **方向盘旷量突增、脱手感、可见车轮姿态异常**（球头分离征兆）：禁止继续行驶（含「开去修理厂」），拖运移交。
- **减振器明显漏油＋轮胎杯状磨损＋高速飘忽**，或**弹簧断裂/单侧车高塌落**：停止高速与载重使用，移交。
- 本篇不授权：转向/悬架/轮端拆卸、弹簧压缩与拆装、四轮定位作业、液压放气与油液作业、轮胎拆装、任何路试。矩阵中的「证据类型」须由合格人员按 OEM 版次与实车条件执行，研究级信息不是操作顺序。

## 6. 来源表与 UNKNOWN 清单

| 来源（均为已接受语料复用，检视 2026-11-20） | 可支持的限定事实 | 不支持的外推 |
|---|---|---|
| [Toyota 2014-08 改款公告](https://global.toyota/en/detail/3737378) | 2014 日本改款全系车速感应 EPS、前平台/悬架最优化、最大积载量 400 kg（2 名乗車時） | 改款前各 grade 转向形式、EPS 参数、缅甸实车装配 |
| [Toyota 75 年史 Probox](https://www.toyota-global.com/company/history_of_toyota/75years/vehicle_lineage/car/id60012554A/index.html) | 2002 后悬架 4 连杆＋桶形非线性弹簧、减振器后倾、载货设计动机 | 前悬架类型、失效行为与故障率 |
| [Bosch EPS](https://www.bosch-mobility.com/en/solutions/steering/electric-power-steering-systems/) / [Column EPS](https://www.bosch-mobility.com/en/solutions/steering/electric-power-steering-with-servo-unit-on-the-steering-column/) / [ZF EHPS](https://aftermarket.zf.com/en/aftermarket-portal/knowledge-hub/function-principle-of-electrohydraulic-power-steering/) | EPS/EHPS 技术家族与构型多样性 | 某车实装、DTC 语义、降级安全策略 |
| [Monroe Shocks vs Struts](https://www.monroe.com/technical-resources/shocks-101/shocks-vs-struts.html) / [NHTSA Tire Safety](https://www.nhtsa.gov/vehicle-safety/tires) | 阻尼/弹性/支柱职责差异；轮胎状态与稳定的关系 | 某车安装方案、阻尼值、定位与胎压数值 |
| [MDN 2022-09-29](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand) | Probox/Succeed/AD Van 的缅甸二手市场相关性 | 保有量、工单份额、任何故障率 |

**UNKNOWN 台账**：缅甸实车 `FRAME/VIN`、`BUILD_MONTH`、`STEERING_TYPE`（2014 前）、定位角/前束/胎压/扭矩全部数值、`EPS_DEGRADE_STRATEGY`、`VEHICLE_LOAD_HISTORY`、`MYANMAR_OVERLOAD_FAULT_RATE`、球头/减振器/弹簧各假说的本地故障率、维修成效与互换性——全部 `UNKNOWN`，禁止以任何方式补值。

## 7. 完成边界

本篇在已接受的 [FUN-STEER-SUSP](./function.md) 之上新增**失效竞争机理、证据区分矩阵、缅甸反例与安全停止边界**；质量状态 `GENERATED_REVIEW_PENDING`，`GENERATION_QUALITY` 只能由未来非 Writer 对话按本文件 Exact Blob 独立审核授予；即便限定接受，也不含 OEM/VIN/N3 专业事实资格或现场维修授权。
