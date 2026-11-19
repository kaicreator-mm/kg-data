# Toyota Probox：低压起动/充电/供电与空调（HVAC）装备的年款与选配差量 — R1

> TASK_ID: `SER-DELTA-PROBOX-LOWV-HVAC` · 研究轴: `L3 MODEL_SERIES + L2 LOWV_SUPPLY + L2 HVAC_CONTROL` · 市场: `MYANMAR_USED_FLEET_CANDIDATE` · 来源技术版本: **Toyota 2002 日本产品家族 / 2008-08 / 2014-08 / 2016-08 日本市场公告**  
> 直接前置: [`SER-DISC-PROBOX`](./discovery.md) Blob `c8f011229a4e6fa6c66ae092a6f19a21142b4f19`（[独审接受](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6962402777)） · [`SER-DELTA-PROBOX-TRANS`](./transmission-applicability-delta.md) Blob `2a0bfda60bc63ea484c45a6c0b01fe31f7db51a0`（[独审接受](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6976215650)）  
> 对照基础: [`STR-LOWV`](../../../../topics/electrical-low-voltage/structure.md) 与 [`STR-THERMAL`](../../../../topics/thermal/structure.md) **只在通用机理范围内以相对链接引用**；两者自身明确不提供任何车型的 OEM 电路图、保险丝表、继电器端子图、电压阈值或 DTC 结论，不得当作车型级证据使用。  
> 本稿状态: `GENERATED_REVIEW_PENDING / MODEL_GENERATED_UNVERIFIED`。不是缅甸某一实车的电路识别、维修程序或 OEM 事实认证；`OEM/VIN/N3=0`。  
> **证据检视日期: 2026-11-20**——全部厂商/媒体 URL 为当日观察；动态页面固定 URL 与观察日期，不声称网页永久不可变。  
> **研究问题**: 为什么"起动无力 / 充电异常 / 空调不冷"不能用同一套低压或空调推断覆盖所有年款与发动机选配的 Probox？哪些装备差异有 dated 厂商公告证实？哪些电路与参数证据整体缺失、必须阻塞？

## 1. 研究范围与两个必须分账的问题

本稿回答两件具体问题，不生成"Probox 低压/空调大全"：

1. **丰田官方 dated 公告证实了哪些影响低压起动/充电/供电与空调知识结构的装备差异？**——存在被证实的装备时间线（2005 灯光调平、2008 高位制动灯、2014 修订版手动 A/C 与全车 EPS、2016 怠速起停与 Toyota Safety Sense C 等）。它们证明**配置分叉存在**，但不提供任何电路实现细节。
2. **同一症状在不同年款/发动机选配下为什么必须走不同的鉴别路径？**——怠速起停配置会把"停车熄火"变成设计行为、改变电池工作循环；Safety Sense C 增加持续供电与唤醒面；2014 前后 A/C 家族分叉。对缅甸任意一辆实车而言它属于哪个分叉，在没有车架/铭牌/OEM 资料前全部 `UNKNOWN`。

**车型电路级证据的整体缺位必须在开头声明**：本稿所有厂商来源均为产品公告/产品史页面，**均不含**车型电路图、保险丝/继电器分配、连接器映射、发电机/起动机额定值、充电电压阈值、A/C 压缩机型号或风机控制方式。这一整层记 `BLOCKED_OEM_CONFIGURATION_EVIDENCE`（见 §10），不以通用文章或推测填充。

## 2. 来源清单：每条证据能与不能证明什么

| 来源（全部 2026-11-20 检视） | 类型 | 确证内容（仅限原文可见） | 不能证明 |
|---|---|---|---|
| [Toyota 75 年史·Probox 2002 家族](https://www.toyota-global.com/company/history_of_toyota/75years/vehicle_lineage/car/id60012554A/index.html)（页面码 60012554A） | 厂商产品史 | 2002-07-02 上市；2NZ-FE 1.3L / 1NZ-FE 1.5L / 1ND-TV 1.4L 共轨柴油（2007-09 停售，wagon 无柴油）；4AT 或 5MT；1.5L 有 V-flex 全时 4WD；页面代表代码 UA-NCP58G/NCP59G；2005-08 全车型追加手动大灯调平 | 无 A/C、无任何电路/电池/发电机/起动机规格；NCP50V/NCP51V 等代码不在本页 |
| [Toyota 75 年史·Succeed 2002 家族](https://www.toyota-global.com/company/history_of_toyota/75years/vehicle_lineage/car/id60006139B/index.html)（页面码 60006139B） | 厂商产品史 | 同族发动机/传动；页面代表代码 UB-NCP51V / KP-NLP51V / UB-NCP55V；2005-08 全车型手动大灯调平；货厢 1,830 mm / 450 kg | 同上；且不证明与 Probox 低压/HVAC 零件互换 |
| [Toyota 2008-08-01 部分改款公告](https://global.toyota/en/detail/1641086) | 厂商新闻稿 | 原文「バンの一部グレードに…ハイマウントストップランプを標準装備することで全車に標準装備とした」；等级×发动机×变速器表（Probox van 2NZ-FE/1NZ-FE × 5MT/Super ECT 4AT；CNG 1NZ-FNE 仅 2WD Super ECT；Succeed van 1NZ-FE） | 无 A/C 与低压电气细节；Succeed wagon TX 传动未在表中列明 |
| [Toyota 2014-08-06 改款公告](https://global.toyota/en/detail/3737378)（en/jp 同 id 双语核对） | 厂商新闻稿 | 1NR-FE 1.3L **仅 Probox**（「1.3L車に1NR-FEエンジンを新搭載」「プロボックスのみに設定」）；1NZ-FE 1.5L；Super CVT-i 组合；「車速感応型電動パワーステアリングを全車に採用」；VSC＆TRC＋坡道起步辅助「全車標準装備」；大灯/后组合灯意匠变更；**「冷却効率を向上させたマニュアルエアコンを標準装備」** | 该 A/C 句措辞是「標準装備」而**非** VSC&TRC 那样的「全車標準装備」，逐等级 A/C 装备表未在已阅文本内；アクセサリーソケット/コンセント仅出现于下载图像清单，无正文规格（100V 与否无证据）；未说明 2014 前是否有 EPS |
| [Toyota 2016-08-30 一部改良公告](https://global.toyota/en/detail/13332599) | 厂商新闻稿 | 「コンライトやイルミネーテッドエントリーシステムを全車標準装備」；Toyota Safety Sense C（激光雷达＋单眼相机，含自动远光）标准；**1.5L 2WD 标准怠速起停「アイドリングストップ機能（Stop & Start System）」**；1NR-FE/1NZ-FE＋Super CVT-i、2WD/4WD 延续 | 无 A/C 变更；起停专用电池规格、再起动执行结构、各等级装备表均未提供 |
| [Myanmar Digital News / GNLM 2022-09-29](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand) | 本地市场报道 | PROBOX、SUCCEED 与 AD Van 等被点名为当时交易车型；<2000cc 车型需求最强 | 只证明二手市场相关性；不证明保有量排名、维修频率或任一实车配置（继承 discovery §2 口径） |

## 3. 已证实的低压装备差量时间线（P2-02 分账之一：确认事实）

| 时间点（来源同 §2 行） | 公告证实的变化 | 低压侧机理归类（结构含义，非车型电路事实） | 禁止推广之处 |
|---|---|---|---|
| 2002-07-02 首发 | 2NZ-FE/1NZ-FE/1ND-TV（柴油 2007-09 停售）×4AT/5MT×2WD/1.5L V-flex 4WD | 属传统"辅助电池＋发电机＋起动机"家族的机理类型（通用机理见 [`STR-LOWV`](../../../../topics/electrical-low-voltage/structure.md)）；不同发动机的起动阻力与附件布置可能不同 | 页面无任何低压规格；缅甸实车是否属于此家族任一组合 `MYANMAR_CHASSIS_AND_FITMENT=UNKNOWN` |
| 2005-08 | Probox 与 Succeed 两页各自记载：全车型追加手动大灯调平机构 | 灯光载荷/调节机构存在年款差异的证据点 | 只证明调平机构存在；灯泡类型、电路、开关逻辑 UNKNOWN |
| 2008-08-01 | 高位制动灯从部分 van 等级改为**全车标准**；等级×发动机×变速器组合表 | 制动灯电路的标准化时点；同一年款内不同等级装备不同是本家族的常态 | 无电路细节；"全车"仅指该公告范围，不是年款阈值之外的承诺 |
| 2014-08-06 | 車速感応型 EPS「全車に採用」；VSC＆TRC＋HAC「全車標準装備」；大灯/后组合灯意匠变更；1NR-FE 仅 Probox＋Super CVT-i | 转向助力由电机承担、稳定性控制增加轮速/横摆传感与液压执行控制面——控制与载荷基线相对 2014 前配置不同 | **是否 2014 年首次采用 EPS 未证实**（此前年款 EPS 存在与否 UNKNOWN）；CVT 车型的 TCM/ECU 控制面细节 UNKNOWN |
| 2016-08-30 | コンライト与照明进入系统「全車標準装備」；Toyota Safety Sense C（激光雷达＋单眼相机）标准含自动远光；**1.5L 2WD 标准怠速起停** | 怠速起停改变起动件工作循环与电池充放电 duty；Safety Sense C 增加持续供电/唤醒与传感控制面；照明进入改变上电时序——鉴别"起动/亏电"症状前必须先分辨车辆是否属此类配置 | 起停专用电池规格（类型/容量）、再起动执行结构（同一起动机或独立部件）、各等级映射全部 UNKNOWN；缅甸车队是否含此配置 UNKNOWN |

**这条时间线的知识价值**不在"新=好、旧=坏"，而在：同一组低压症状在 2016 怠速起停、2014 控制升级与更早的简单配置上，**候选原因集合与设计行为基线不同**（§5 展开竞争分叉）。

## 4. 已证实的 HVAC 装备差量（P2-02 分账之二：确认事实与未验证内容分离）

1. **唯一 A/C 正面证据是 2014-08-06 公告句**：「冷却効率を向上させたマニュアルエアコンを標準装備し、快適な室内空間を追求」。可确认：该日本改款将**制冷效率经修订的手动 A/C**列为标准装备。**不可确认**：该句未用与 VSC&TRC 同款的「全車標準装備」措辞，已阅文本中也没有逐等级 A/C 装备表，故"2014 后每一等级均为手动 A/C"不能由此句成立；该句出现在 Probox/Succeed 联合公告的共通特長段，逐模型映射同样未在已阅文本中确立。
2. **2002 产品史与 2008 公告两个页面均未提及 A/C**：2014 之前各等级 A/C 装备形态（手动/自动、标配/选装、有无自动温度控制）→ `UNKNOWN`。**不允许**用"同级别商用车通常配手动 A/C"这类行业惯例回填。
3. **压缩机组、风机与控制系统整体阻塞**：A/C 压缩机型式/排量/离合器控制、蒸发器/暖风芯布置、风机调速方式（电阻梯级或晶体管连续）、冷凝风扇与散热风扇的驱动/联动/温控策略、压力开关或压力传感器、温控执行（拉线或电动执行器）——**全部** `BLOCKED_OEM_CONFIGURATION_EVIDENCE`。以上任何"典型实现"描述都不得写入本文当事实。
4. 机理对照只引用 [`STR-THERMAL`](../../../../topics/thermal/structure.md) 的**四网络分离**（液态冷却回路 / 制冷剂回路 / 空气侧 / 电源与控制）作为故障解释的隔离框架；该通用稿自身也警示"不能把现代设计倒填旧款 Probox"——本稿沿用此约束。

## 5. 起动/充电症状的竞争诊断分叉（按配置家族，非维修步骤）

下表把同一症状拆成**不同配置下的不同候选原因集合**。"机理归类"列只是 [`STR-LOWV`](../../../../topics/electrical-low-voltage/structure.md) 的通用概念映射，不是车型电路断言；所有阈值、端子、保险丝、继电器与电压数值均 UNKNOWN。

| 症状输入 | 配置分叉 | 竞争解释空间（必须全部保留） | 禁止的错误归因 |
|---|---|---|---|
| 起动无力 / 无法起动 | **A. 非起停的传统配置**（2002 家族至 2014 公告范围，及 2016 公告中非 1.5L-2WD 组合） | 辅助电池状态与端子接触；主电路与接地回路；起动许可链（挡位/离合/防盗状态——机理概念）；起动机本体；发动机机械阻力（含 1ND-TV 柴油与汽油机的不同阻力特征） | "先换电池"不经验证成立；把任一单一原因当必然 |
| 同上 | **B. 怠速起停配置**（2016-08-30 公告：1.5L 2WD 标准 Stop & Start System） | 停车熄火属**设计行为**而非故障；频繁再起动改变电池工作循环与寿命压力；再起动的执行结构与电池规格 UNKNOWN | 把正常起停行为当"充电系统坏"；把起停车的电池要求套到非起停车，或反向套用 |
| 同上 | **C. 柴油 1ND-TV（2007-09 前存在）** | 除 A 类各项外，柴油冷起可能存在本车型未取证的附加电载荷（预热类系统属常见柴油机结构，但**本车型安装证据未获取**） | 从"是柴油车"直接断言预热塞电路/数值——`BLOCKED` |
| 充电异常（亏电、灯光变暗类描述） | **按 §3 装备时间线分层** | 发电/整流/调节环节；载荷基线随配置不同（2016 Safety Sense C、照明进入、コンライト；2014 EPS/VSC&TRC；更早配置更简单）；电池老化与充电之间的竞争；发电机传动假设属通用机理归类，本车型各年款实装 UNKNOWN | 用一个"充电电压应为 13.x–14.x V"的通用数值覆盖所有年款配置；把新增加载（如 Safety Sense C）直接当发电机故障证据 |
| 起动后仪表报警/起停不工作类描述 | 各配置 | 电池状态、传感器/网络状态、控制许可条件（机理概念，见 STR-LOWV 的电源/控制/数据三网分离） | 通用 DTC 描述直接等于部件损坏；本稿不提供任何 DTC 解释 |

**分账要求**：对缅甸任一实车，第一步证据是车架/铭牌/制造期与配置核实，不是症状套表。无 VIN 时上表只用于说明"为什么不能跨配置推断"，不用于现场判定。

## 6. 空调不冷 / 风量异常的竞争解释与配置分叉

| 症状输入 | 已可判定的家族分叉 | 竞争解释空间（按 STR-THERMAL 四网络隔离） | 状态 |
|---|---|---|---|
| 冷气不足 | 2014 公告范围内的车存在"修订版手动 A/C"家族；2014 前各等级装备 UNKNOWN；不存在任何已证实自动 A/C 证据 | 发动机冷却侧（散热/风扇/节温类机理概念）、制冷剂侧（压缩机/冷凝/蒸发/节流的概念链）、空气侧（风机/风道/混合风门概念）、电源与控制侧——四个网络必须分别取证，不能因"开 A/C 出热风"直接归因任一网络 | 部件与控制映射 `BLOCKED_OEM_CONFIGURATION_EVIDENCE` |
| 风机不转 / 风量档异常 | 控制家族（调速方式）UNKNOWN | 供电支路、控制支路、电机本体三类竞争解释按 STR-LOWV 的电源/控制分离保留 | 同上；禁止"档位电阻坏了"之类无证据断言 |
| 开 A/C 后怠速工况异常 | 压缩机驱动与排量控制 UNKNOWN；发动机选配（2NZ/1NZ/1NR）影响怠速控制基线 | 压缩机负载、怠速控制、电源负载三条竞争路径并存 | 同上 |

**HVAC 小结**：本域的"已证实差量"只有 §4 第 1 条这一句装备事实加 §3 时间线里的相关控制装备；其余实现层全部阻塞。任何进一步的车型级 A/C 维修知识需要匹配版次的 OEM 资料或可信实车配置证据，在此之前下钻即 `BLOCKED_SOURCE`。

## 7. Probox 与 Succeed 的适用性分账

- 车型代码族不同：Probox 页面代表代码 UA-NCP58G/NCP59G；Succeed 页面代表代码 UB-NCP51V / KP-NLP51V / UB-NCP55V（继承 discovery §3 与 trans 差量 §2 的逐代码分账）。货厢长度/载重不同（1,310 mm·400 kg 对 1,830 mm·450 kg）；销售渠道不同；2014 起另有 1NR-FE 仅 Probox。
- **低压/HVAC 零件互换性无任何 OEM 证据**：`PARTS_INTERCHANGE_LOWV_HVAC=UNKNOWN`。不因两车同族、同厂（京都/大发工厂）就假定发电机、电池规格、鼓风机、压缩机、开关或线束互换。
- 2014 的 A/C 公告句属联合公告共通段：Succeed 侧各等级 A/C 映射与 Probox 侧一样未被逐级确立，两侧**各自** `UNKNOWN`，不互相代证。

## 8. 缅甸存量车辆：市场证据与车型事实严格分账

[2022-09-29 市场报道](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand)（2026-11-20 复核可访问）点名 PROBOX/SUCCEED 为交易车型，仅支持"本地研究价值"。discovery 记录的 CarMM 挂牌年份字段冲突（`SELLER_CLAIMED_YEAR_CONFLICT`）继续适用。

`MYANMAR_CHASSIS_AND_FITMENT=UNKNOWN`；`MYANMAR_REAL_CONFIG_DISTRIBUTION=UNKNOWN`（2002/2005/2008/2014/2016 各装备层级在缅甸实车上的分布无任何统计）；无 VIN 不做任何零件适配断言；本稿不是"Probox 低压/空调故障概率"研究，`ON_ROAD_STOCK/RATE/FAULT_FREQUENCY=UNKNOWN`。

## 9. 电气安全边界

本稿不提供且明确排除：电气短接或跨接起动类操作细节、带电测量类危险步骤、任何对大电流回路的拆动、制冷剂回路作业、发电机/起动机带载试验。上述工作属专业人员与专用设备范畴，超出本文知识阶段。通用结构机理只经 [`STR-LOWV`](../../../../topics/electrical-low-voltage/structure.md) 与 [`STR-THERMAL`](../../../../topics/thermal/structure.md) 相对链接引用，不在本文复制其内容。

## 10. 差量结论、后续任务与 STOP

| 项目 | 结果 |
|---|---|
| `MATERIAL_DIFFERENCE_CONFIRMED_IN_OEM_ANNOUNCEMENTS` | **是**：装备时间线（2005 调平/2008 高位制动灯/2014 EPS＋VSC&TRC 全车＋修订版手动 A/C＋1NR-FE/2016 起停＋Safety Sense C＋照明进入）证实低压与 HVAC 相关配置存在年款与选配分叉 |
| `CIRCUIT_AND_PARAMETER_LEVEL_EVIDENCE` | **`BLOCKED_OEM_CONFIGURATION_EVIDENCE`**：电路图、保险丝/继电器分配、连接器映射、发电机/起动机额定值、充电阈值、压缩机型号、风机调速、风扇控制、压力传感——整层无来源 |
| `APPLICABLE_TO_SPECIFIC_MYANMAR_VEHICLE` | **UNKNOWN**：无实车车架/制造期/配置核实，本文分叉表不用于现场判定 |
| `REUSE_FROM_GENERIC` | 仅以相对链接复用 [`STR-LOWV`](../../../../topics/electrical-low-voltage/structure.md)、[`STR-THERMAL`](../../../../topics/thermal/structure.md) 的机理分类；零复制 |
| `P2_ON_SOURCE_REPLAY` | 全部来源 URL＋2026-11-20 观察日固定；`IMMUTABLE_MARKET_SNAPSHOT=NOT_AVAILABLE` |
| `NEXT_VALUE_TASK` | 只有获得匹配版次 OEM 电路/装备资料或可信实车配置证据时，才做更窄的 `SER-CONFIG-PROBOX-LOWV-*`；否则 `BLOCKED_SOURCE`，不产假差量 |
| `DUPLICATION_STOP` | 不为每个年款复制一篇通用低压或空调说明；本文已完成有证据支撑的差量范围 |

## 11. 反例与质量保护

1. **错误**："2014 改款后所有等级都是手动 A/C。" 反例：公告句只写「標準装備」，未用「全車標準装備」措辞，且无逐等级装备表；等级映射 UNKNOWN。
2. **错误**："停车熄火 = 充电系统故障。" 反例：2016 公告证实 1.5L 2WD 标准怠速起停——该行为是设计行为；但实车是否属该配置需先核实。
3. **错误**："起停车电池与普通车电池一样选型。" 反例：起停改变电池工作循环；但本车型起停电池的规格/类型无 OEM 来源 → 两侧都不得断言具体规格。
4. **错误**："2014 年才有电动助力转向。" 反例：公告只说该版本「全車に採用」；此前年款是否存在 EPS 未取证。
5. **错误**："空调不冷就是缺制冷剂/压缩机坏。" 反例：STR-THERMAL 四网络（冷却液侧/制冷剂侧/空气侧/控制侧）必须分别取证；本车型部件映射全部 BLOCKED。
6. **错误**："Succeed 零件可按 Probox 电路图查。" 反例：两车型代码族、装备表、渠道均分开记载；低压/HVAC 互换性 `UNKNOWN`。
7. **错误**："缅甸的 Probox 都是 2002 简单配置，所以诊断最简单。" 反例：缅甸实车装备层级分布 UNKNOWN；市场报道不构成配置统计。

## 12. UNKNOWN / BLOCKED 总清单

`BLOCKED_OEM_CONFIGURATION_EVIDENCE`：车型电路图、保险丝/继电器/连接器映射、线径与接地布局、发电机与起动机额定值、充电电压/电流阈值、A/C 压缩机型式与排量、风机调速方式、冷凝/散热风扇控制策略、压力开关/传感器、温控执行机构。  
`UNKNOWN`：2014 前 A/C 各等级装备形态；2014 A/C 句的逐等级/逐模型映射；2014 前 EPS 存在与否；2016 起停配置的电池规格与再起动执行结构；アクセサリーコンセント的电压规格；各年款发电机传动与调节策略实装；`MYANMAR_CHASSIS_AND_FITMENT`；`MYANMAR_REAL_CONFIG_DISTRIBUTION`；`PARTS_INTERCHANGE_LOWV_HVAC`（Probox↔Succeed 及跨年款）；`ON_ROAD_STOCK/RATE/FAULT_FREQUENCY`；任一实车的 DTC/仪表语义。  

**本任务结论是"已生成可复核的低压/HVAC 装备差量候选，并把无证据层诚实阻塞"**，不是"已获得缅甸实车低压/空调诊断能力"。后续仍需另一对话对本 Exact Blob 独立审 Markdown 深度、OEM 来源范围、错误泛化、P2-02 分账与安全边界。
