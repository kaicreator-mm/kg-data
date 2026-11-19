# Toyota Probox / Succeed：跨产品时期的制动与转向悬架适用性差量 — R1

> TASK_ID: `SER-DELTA-PROBOX-BRK-SUSP` · 研究轴：`L3 MODEL_SERIES + L2 BRAKING / STEERING-SUSPENSION_FAMILY` · 市场：`MYANMAR_USED_FLEET_CANDIDATE` · 来源技术版本：**2002 Toyota 日本车型家族 / 2008 部分改良 / 2014-08 日本改款 / 2016 一部改良**  
> 直接前置：[`SER-DISC-PROBOX`](./discovery.md) Blob `c8f011229a4e6fa6c66ae092a6f19a21142b4f19` · [`SER-DELTA-PROBOX-TRANS`](./transmission-applicability-delta.md) Blob `2a0bfda60bc63ea484c45a6c0b01fe31f7db51a0`（传动轴差量已在该稿完成，本文不重复）  
> 对照基础：[`STR-BRK`](../../../../topics/braking/structure.md) Blob `e231eda16a8d799d891e7604bee41437af29afb6`、[`STR-STEER-SUSP`](../../../../topics/steering-suspension/structure.md) Blob `1c84e3329bfcb40bcc2a01dac1b6af15ef5bfb40`，只作通用结构机理对照，不复制正文。  
> 本稿状态：`GENERATED_REVIEW_PENDING / MODEL_GENERATED_UNVERIFIED`。不是缅甸某一实车的制动/悬架识别、维修程序或 OEM 事实认证；`OEM_VIN_SPECIFIC_SERVICE_MANUAL=NOT_ACCESSED`。  
> **研究问题**：Toyota 同一 Probox/Succeed 相关车系在不同产品时期、驱动与车身形式下，制动与转向悬架装备/结构有哪些**厂商公开证实**的版本差量？哪些差量会真正改变诊断分支，哪些仍 `UNKNOWN`？

## 1. 安全件的输出边界先于内容

制动与转向悬架是安全件，本稿先立边界再写差量：

- **允许写**：有 dated publisher（Toyota 官方发布稿/官方产品史）来源的**版本化装备与结构差异**、可复核的机理类型、竞争解释与反例、`UNKNOWN` 明示。
- **禁止写**：通用制动放气、举升支撑点、接触高温/旋转部件、危险路试等操作步骤——通用知识一律指向已审 topics 文档，不在本文复制；任何扭矩、油液量、制动盘直径毫米值、放气顺序、电路图/连接器/诊断数值。**本稿没有匹配车型的 OEM 维修手册版次**，此类内容一律不出现，也不伪装成"参考值"。
- **停止使用边界**：实车出现制动效能明显下降、跑偏、助力消失、踏板异常、转向异响/卡滞等严重风险迹象时，本知识层只支持"停止使用并移交专业维修诊断"，不支持现场自行拆修。

## 2. 比较的官方产品切片与各自能证明什么

| 证据编号 | 官方来源切片（检视日期 2026-11-20） | 原文确证的制动/转向/悬架相关内容 | **不能**证明什么 |
|---|---|---|---|
| OEM-PB-01 | [Toyota 75 年史·Probox 2002 首发](https://www.toyota-global.com/company/history_of_toyota/75years/vehicle_lineage/car/id60012554A/index.html) | 后悬架 "a specially developed 4-link system with barrel-shaped nonlinear coil springs"，减振器 "angled toward the rear"，动机为 "To flatten the cargo room floor"；代表 grade 整备质量 1030 kg(2WD)/1110 kg(4WD)；"With the Probox van, the length of the cargo room and the cargo carrying capacity were 1,310 mm and 400 kg"（两人乘坐前提） | 前悬架类型、前后制动器盘/鼓布局、转向助力形式、ABS/稳定控制装备、轮胎规格；表中为"representative model grades"，非逐 grade 配置表 |
| OEM-PB-02 | [Toyota 75 年史·Succeed 2002 首发](https://www.toyota-global.com/company/history_of_toyota/75years/vehicle_lineage/car/id60006139B/index.html) | 与 Probox 页面**相同文字**的后悬架设计描述；Succeed van 货舱 "1,830 mm and 450 kg"；车身 4300/1695/1525 mm、轴距 2550 mm（van grade；NCP55V 高 1530） | 同 OEM-PB-01 的全部"不能证明"项；以及两名称零件互换性 |
| OEM-PB-03 | [Toyota 2008-08-01 部分改良公告](https://global.toyota/en/detail/1641086) | 唯一宣布的装备变化是高位制动灯扩至全车标准（原文限定该改良范围）；同页列出 2NZ-FE/1NZ-FE/1NZ-FNE、5MT/Super ECT(4速AT)、2WD(FF)/4WD、van/wagon grade 表 | 该公告**未宣布任何制动/悬架/转向机械变更**；"未宣布"只证明公告未覆盖，不证明当时不存在其它年型改动 |
| OEM-PB-04 | [Toyota 2014-08-06 改款公告](https://global.toyota/en/detail/3737378) | 「全車大径のフロントディスクブレーキを採用し制動力を強化」；「VSC＆TRC」「ヒルスタートアシストコントロール」「緊急ブレーキシグナルを全車標準装備」；「車速感応型電動パワーステアリングを全車に採用することで、空車時から積載時まで扱いやすく」；「プラットフォームのフロント部を刷新し、サスペンションの構造を最適化」（目标「空車時から積載時まで…高い操縦安定性と乗り心地の良さを実現」）；「全車最大積載量400kg（２名乗車時）」；1NR-FE「プロボックスのみの設定」；grade/价格表含 1.3L 仅 2WD、1.5L 有 2WD/4WD | 各 grade 前后制动器盘/鼓明细、ABS 逐项配置、轮速传感器布置、盘径数值、改款前各 grade 转向/制动配置、悬架几何与刚度数值 |
| OEM-PB-05 | [Toyota 2016 一部改良公告](https://global.toyota/en/detail/13332599) | 「Toyota Safety Sense C」全车标准（毫米波/激光雷达+单眼相机的冲突回避支援型 pre-crash，可施加制动辅助）、Drive Start Control；1.5L 2WD 标准怠速停止 | 该公告未宣布制动/悬架/转向机械变更；pre-crash 的作动逻辑/阈值/执行通道无细节 |
| OEM-MMR-01 | [Myanmar Digital News / GNLM 2022-09-29](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand)（同[发现稿 MMR-PB-01](./discovery.md)） | "Types of cars such as PROBOX, SUCCEED, AD VAN, Toyota Mark II 200 and unmodified WISH 2003 model are popular in the market." | 只证明二手市场相关性；不构成保有量、维修频率或故障率分母 |

以上均为厂商/媒体公开材料，**不是已浏览匹配缅甸具体 VIN 的 Toyota 修理书**；发布稿配置表不能生成扭矩/油压/间隙类"车型级确定事实"。

## 3. 审计 P2-02：版本化装备事实与未验证维修数值的分账

**（a）2014 OEM 公开已证实的装备变化（可直接作为版本差量写）**：前盘制动加大径强化制动力（全车）；VSC＆TRC、坡道起步辅助、紧急制动信号全车标准化；车速感应 EPS 全车采用；前部平台刷新与悬架结构最优化（目标绑定空载到载重状态）。另有 2016 已证实的制动相关电子装备（TSS C pre-crash、Drive Start Control）。

**（b）未验证、本文不使用的**：电路图与连接器引脚、轮速传感器数量与布置、液压单元/阀体结构、制动盘直径与厚度数值、制动液规格与容量、放气顺序、扭矩值、各 grade 前后盘/鼓明细。这些一律 `NO_OEM_SERVICE_DATA`，本稿一个数值都不给，包括不给"常见值"。

**（c）资格边界**：公开 2014 发布**足以**支撑版本化装备研究（哪些装备在哪一版本成为全系标准），**不足以**支撑 VIN 级诊断（某辆缅甸实车究竟装什么、状态如何）。因此本稿的结论只到"版本适用性"层，不到"某车怎么修"层。不为凑数把有来源的内容硬标 `BLOCKED`，也不把未验证数值写成事实。

## 4. 制动系统：已证实差量与结构含义

### 4.1 2014 前盘制动强化：全车适用、改变跨年款对照基准

OEM-PB-04 原文「全車大径のフロントディスクブレーキを採用し制動力を強化」确证：2014 日本改款后全系前制动为盘式且直径加大。该表述以"大径"修饰同时**提示改款前版本已是前盘式**（否则不称"大径"），但改款前的盘径数值与逐 grade 前制动配置未在所阅来源列出，记 `PRE_2014_FRONT_BRAKE_SPEC=UNKNOWN`。

机理层（对照通用 [`STR-BRK`](../../../../topics/braking/structure.md) 摩擦制动路径）：盘径改变摩擦半径、热容与力矩输出，因此"踏板高低、磨损模式、热衰减表现"在 2014 前后版本**不构成同一硬件基准**；把一个年款的经验感受直接套到另一年款属于跨版本误判。

### 4.2 VSC＆TRC 与坡道起步辅助 2014 全车标准化

OEM-PB-04 确证三者全车标准。结构含义为**明确标注的机理性推断**：VSC/TRC 的作用路径依赖轮速感知与制动液压调制能力（`STR-BRK` 第 4 节 ABS/ESC 硬件共享机理），故"2014 后版本存在轮速传感与制动调制硬件"可作机理推断；但 OEM 公告未逐项列出 ABS 或传感器配置，`ABS_EQUIPMENT_PER_VERSION=UNKNOWN`。

反例保护：不能由"2014 标准化"反向断言"2014 前无任何稳定性控制装备"——所阅来源只证明 2014 这一标准化事件，此前哪些 grade 已带 VSC/TRC 未证实。也不能把 VSC/TRC 标准化自动换写成"ABS 标准化"，那是两个不同的装备命题。

### 4.3 2016 制动相关电子装备：出现"非驾驶人踩踏的自主制动"这一版本差

OEM-PB-05 确证 TSS C（含冲突回避支援型 pre-crash，激光雷达+单眼相机）全车标准、Drive Start Control 全车标准。对维修知识的影响是**解释集合**变化：2016 后版本存在"车辆自主施加制动/抑制起步"的装备事实，而更早版本无此公告证据；无此装备年份套用 TSS 解释属误判，反之亦然。作动条件、传感器布置与执行通道无来源，`TSS_C_BEHAVIOR_SPEC=UNKNOWN`。

### 4.4 后制动器与助力形式：无 OEM 公开配置来源

所阅六个来源均未给出前后制动器盘/鼓布局、助力器形式（真空/液压）的逐版本配置表。记 `REAR_BRAKE_LAYOUT_PER_VERSION=UNKNOWN`、`BRAKE_BOOSTER_TYPE_PER_VERSION=UNKNOWN`。禁止把"商用车通常后鼓"类行业常识写成 Probox/Succeed 事实——那正是本任务要消灭的"伪装备断言"。

## 5. 转向：2014 车速感应 EPS 全车采用

OEM-PB-04 原文「車速感応型電動パワーステアリングを全車に採用することで、空車時から積載時まで扱いやすく」确证：2014 日本改款全系采用车速感应 EPS，且厂商**自己把转向变更与载荷状态绑定**（空车到载重都可操控）。

"全車に採用"的措辞把该装备呈现为覆盖全部车型的采用动作，提示改款前并非全部车型为车速感应 EPS；但改款前各 grade 的转向形式（HPS/EHPS/EPS）未在所阅来源逐项列出，记 `PRE_2014_STEERING_TYPE_PER_GRADE=UNKNOWN`。通用 HPS/EHPS/EPS 架构差异见 [`STR-STEER-SUSP`](../../../../topics/steering-suspension/structure.md) 第 3 节，不在本文重复。

维修知识含义：EPS 与液压助力的噪声源、手感失效与供电/液压依赖不同族；跨年款把"助力泵异响"或"电机扭矩传感器"互套是典型错置。任何 EPS 标定、传感器更换数值无来源，不提供。

## 6. 悬架：2002 后悬架设计 vs 2014 前平台刷新

### 6.1 2002 家族已证实的后悬架设计（两名称同述）

OEM-PB-01/02 用相同文字确证：后悬架为专门开发的 4 连杆+桶形非线性螺旋弹簧，减振器向后倾角布置，动机是压平货舱地板。这是**厂商把后悬架设计与载货空间绑定**的公开设计动机，属有来源的载荷相关机理。前悬架类型在所阅来源未列出，`FRONT_SUSPENSION_TYPE_2002=UNKNOWN`。

### 6.2 2014 前平台刷新与悬架结构最优化

OEM-PB-04 确证「プラットフォームのフロント部を刷新し、サスペンションの構造を最適化」，官方目标表述为「空車時から積載時まで…高い操縦安定性と乗り心地の良さを実現」。这构成有来源的版本差量：2014 后前部平台/悬架结构与改款前不同，且官方把优化目标绑定在"空载到满载"区间。具体几何、弹簧刚度、衬套与限位数值无来源，`2014_SUSPENSION_SPEC_VALUES=UNKNOWN`。沿用传动差量稿的口径：Toyota 官方称 2014 为 "minor change"，本稿不宣称整车平台换代。

### 6.3 FF/4WD 与 van/wagon：已证实的质量差与未证实的硬件差

已证实（OEM-PB-01）：2002 代表 grade 中 1.5L 4WD（V-flex 全时四驱）整备质量 1110 kg，对应 2WD 1030 kg，差 80 kg；2014 公告价格表结构显示 1.3L 仅 2WD、1.5L 才有 4WD，Succeed 2014 切片仅 1.5L。未证实：4WD 版本专属的悬架弹簧率、后桥/衬套、制动载荷分配等硬件差，`4WD_CHASSIS_HARDWARE_DELTA=UNKNOWN`；轮胎规格与载重等级逐版本未列，`TIRE_SPEC_PER_VERSION=UNKNOWN`（轮胎/几何机理见 `STR-STEER-SUSP` 第 5 节）。80 kg 簧上质量差对制动与悬架需求的影响只能按通用机理提及，不写该车型阈值。

## 7. 商用载荷：有来源的设计机理与无来源的失效断言分账

| 有 dated publisher 来源、可写 | 无来源、必须 UNKNOWN |
|---|---|
| 2002 货舱/载荷对比：Probox van 1310 mm/400 kg，Succeed van 1830 mm/450 kg（两页交叉一致，均为两人乘坐前提，OEM-PB-01/02） | 缅甸实车长期超载比例、超载导致制动热衰减/悬架早期损坏的**本地发生率**（`MYANMAR_OVERLOAD_FAULT_RATE=UNKNOWN`） |
| 2014 全车最大积载量 400 kg（2 名乗車時）（OEM-PB-04） | 超载状态下具体制动距离/衰退数值——任何数值都无来源 |
| 后悬架 4 连杆+桶形非线性弹簧、减振器后倾，动机压平货舱地板（OEM-PB-01/02） | 非原厂载荷/悬架改装后的行为——本稿不给改装建议 |
| 2014 悬架最优化与 EPS 采用的官方目标均绑定"空车时から積載時まで"（OEM-PB-04） | 某辆缅甸车当前实际载荷历史、维修史（`VEHICLE_LOAD_HISTORY=UNKNOWN`） |

结论：商用载荷对制动/悬架的影响在**设计动机层**有 dated publisher 证据可写；在**缅甸实车失效层**没有证据，不写"缅甸 Probox 因拉货必坏 XX"类断言。载荷相关安全风险只落在停止使用与专业移交边界（第 1 节）。

## 8. 诊断知识受影响之处（竞争解释，非故障率）

| 现象输入（只是知识分支条件，不是发生率） | 版本相关机理空间 | 跨版本误判反例 | 正确分支条件 |
|---|---|---|---|
| 制动踏板低/软、行程异常 | 同名车型跨 2014 前盘径不同；助力形式逐版本 UNKNOWN；液压路径衰减（通用 `STR-BRK`） | 用单一"主缸/助力器老化"解释所有年款，或用 2014 后硬件感受评价 2014 前车 | 先确定版本与装备族，再进入对应机理分支；缺配置证据则 `UNKNOWN` |
| 行驶中非驾驶人意图的减速 | 2016+ TSS C pre-crash/Drive Start Control 的装备事实（OEM-PB-05）vs 制动卡滞/稳定控制介入 | 对无 TSS 装备年份套用"主动制动"解释，或把 2016+ 的正常装备行为一律当故障 | 先确认年款装备层；作动逻辑无来源，`TSS_C_BEHAVIOR_SPEC=UNKNOWN` |
| 稳定控制/制动警告指示 | 2014 后 VSC＆TRC 全车标准（OEM-PB-04）；2014 前装备未知 | 断言"这车没有 VSC"或"必然有 ABS"——都超出所阅来源 | 年款装备层先分账；传感器/液压单元布置无 OEM 资料，不下部件级结论 |
| 转向手感/噪声差异 | 2014 全车车速感应 EPS；此前形式 UNKNOWN（第 5 节） | "助力泵异响"与"EPS 电机/扭矩传感器"两族互套 | 确认转向形式后选机理族；EPS 标定/参数无来源不提供 |
| 空载正常、载重后异常 | 2014 悬架优化官方目标即"空车時から積載時まで"；2002 后悬架载荷导向设计（OEM-PB-01/02/04） | 把载重相关行为一律归因"弹簧疲软"而不看版本设计差异与载荷历史 | 版本+实际载荷历史分账；`VEHICLE_LOAD_HISTORY=UNKNOWN` |
| 2WD 与 4WD 前端/后端表现差异 | 已证实整备质量差 80 kg（2002 代表 grade）；4WD 专属硬件差 UNKNOWN | 用 2WD 件参数解释 4WD，或反之 | 驱动形式确认后仍受 `4WD_CHASSIS_HARDWARE_DELTA=UNKNOWN` 限制 |

此表是**避免跨版本误判的结构化知识**，不构成任何"常见故障排名"；失效与维修细节由后续有 OEM 版次资料的专门任务处理。

## 9. Probox 与 Succeed 分账及缅甸边界

- 2002 家族两名称在车身尺寸（4300/1695/1525 vs 4195/1690/1510）、货舱与载荷（1830 mm/450 kg vs 1310 mm/400 kg）上**厂商原文即不同**（OEM-PB-01/02）；2014 公告按两名称分别列 grade、价格与销售渠道，1NR-FE 仅 Probox（OEM-PB-04）。因此制动/悬架零件**不假定两名称互换**；Succeed 专属差量需独立证据与任务，`SUCCEED_SPECIFIC_DELTA=NOT_IN_THIS_TASK`。
- 缅甸边界：市场相关性沿用[发现稿](./discovery.md) MMR-PB-01/02/03/04 与 OEM-MMR-01；挂牌/行政样本不是配置证据。`MYANMAR_CHASSIS_AND_FITMENT=UNKNOWN`：不断言任何缅甸实车装哪个年款、哪种驱动、哪种制动配置；没有 VIN 不断言零件适配。传动轴（4AT/5MT vs 2014 CVT）见[传动差量稿](./transmission-applicability-delta.md)，本文不重复。

## 10. 差量结论、STOP 与 UNKNOWN 台账

| 项目 | 结果 |
|---|---|
| `MATERIAL_DIFFERENCE_CONFIRMED_IN_OEM_FAMILY` | **是**：2014 前盘大径化+VSC＆TRC/坡起辅助/紧急制动信号全车标准化+车速感应 EPS 全车采用+前平台/悬架最优化（OEM-PB-04）；2016 TSS C 制动相关装备（OEM-PB-05）；2002 后悬架载荷导向设计与两名称载荷差（OEM-PB-01/02） |
| `APPLICABLE_TO_SPECIFIC_MYANMAR_VEHICLE` | **UNKNOWN**：无实车车架/制造期/装备验证 |
| `REUSE_FROM_GENERIC` | [`STR-BRK`](../../../../topics/braking/structure.md)、[`STR-STEER-SUSP`](../../../../topics/steering-suspension/structure.md) 只作机理对照，不在本文复制；不为每个年款复制通用制动/悬架文章 |
| `NO_MATERIAL_DELTA_YET` 适用域 | 后制动布局、助力形式、ABS 逐版本配置、轮胎规格、4WD 专属底盘硬件差——这些子域当前只有"问题存在"的证据，没有配置答案，不写结论 |
| `P2_ON_SOURCE_REPLAY` | 全部来源保留原始 URL 与 2026-11-20 检视日期；`IMMUTABLE_MARKET_SNAPSHOT=NOT_AVAILABLE`（动态页面） |
| `NEXT_VALUE_TASK` | 只有取得匹配版次 OEM 资料（或可信实车配置证据）后才下钻 `SER-CONFIG-PROBOX-BRK-SUSP-*`；无来源则 `BLOCKED_SOURCE` |
| `DUPLICATION_STOP` | 本文已覆盖"版本化装备差量+机理分支"的可证范围；继续生成更多 Probox 制动/悬架变体文章无来源支撑即凑数 |

**UNKNOWN 台账（显式）**：`REAR_BRAKE_LAYOUT_PER_VERSION` / `ABS_EQUIPMENT_PER_VERSION` / `BRAKE_BOOSTER_TYPE_PER_VERSION` / `PRE_2014_FRONT_BRAKE_SPEC` / `PRE_2014_STEERING_TYPE_PER_GRADE` / `FRONT_SUSPENSION_TYPE_2002` / `2014_SUSPENSION_SPEC_VALUES` / `4WD_CHASSIS_HARDWARE_DELTA` / `TIRE_SPEC_PER_VERSION` / `TSS_C_BEHAVIOR_SPEC` / `MYANMAR_OVERLOAD_FAULT_RATE` / `MYANMAR_CHASSIS_AND_FITMENT` / `VEHICLE_LOAD_HISTORY` / `SUCCEED_SPECIFIC_DELTA=NOT_IN_THIS_TASK` / 所有扭矩·直径·油液量·电路图数值 `NO_OEM_SERVICE_DATA` / `OEM_VIN_SPECIFIC_SERVICE_MANUAL=NOT_ACCESSED`。

**来源（检视日期 2026-11-20）**：[Toyota 75 Years·Probox](https://www.toyota-global.com/company/history_of_toyota/75years/vehicle_lineage/car/id60012554A/index.html) · [Toyota 75 Years·Succeed](https://www.toyota-global.com/company/history_of_toyota/75years/vehicle_lineage/car/id60006139B/index.html) · [Toyota 2008 部分改良](https://global.toyota/en/detail/1641086) · [Toyota 2014 改款](https://global.toyota/en/detail/3737378) · [Toyota 2016 一部改良](https://global.toyota/en/detail/13332599) · [Myanmar Digital News 2022-09-29](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand)。

**本稿结论是"已生成可复核的车系制动/转向悬架版本差量候选"**，不是缅甸实车配置对应关系，也不是维修手册。即便独审接受，原始专业事实资格、VIN 级诊断与 N3/OEM 仍未授予；严重制动/转向风险永远落在停止使用与专业移交边界。
