# Toyota Probox / Succeed：跨产品时期的发动机代际与燃料类别差量 — R1

> TASK_ID: `SER-DELTA-PROBOX-ENGINE` · 研究轴：`L3 MODEL_SERIES + L2 ENGINE_FUEL_FAMILY` · 市场：`MYANMAR_USED_FLEET_CANDIDATE` · 来源技术版本：**2002 日本首发家族 / 2008-08-01 一部改良 / 2014-08-06 改款 / 2016-08-30 一部改良**  
> 直接前置：[`SER-DISC-PROBOX`](./discovery.md) 当前 Blob `c8f011229a4e6fa6c66ae092a6f19a21142b4f19`（[独立生成质量接受](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6962402777)）与已审通用汽油机结构稿 [`STR-ENG-AIRFUEL`](../../../../topics/engine/air-fuel-emissions/structure.md)。  
> 兄弟差量：[`SER-DELTA-PROBOX-TRANS`](./transmission-applicability-delta.md) Blob `2a0bfda60bc63ea484c45a6c0b01fe31f7db51a0`（传动家族适用性，本文不重复其内容，只在交界处引用）。  
> 本稿状态：`GENERATED_REVIEW_PENDING / MODEL_GENERATED_UNVERIFIED`。不是缅甸某一实车的发动机识别、维修程序或 OEM 事实认证；`OEM/VIN/N3=0`。  
> **研究问题**：同一 Probox / Succeed 名称之下，为什么不同生产时期与燃料类别（2NZ-FE / 1NZ-FE / 1NR-FE 汽油 vs 1ND-TV 共轨柴油）不能用同一套发动机诊断推断覆盖？哪些差异被厂商来源证实？哪些仍是 UNKNOWN？

## 1. 先澄清四个官方产品时期切片

本文只把 Toyota 官方在四个明确日期发布/记载的产品事实当作可比切片；每个切片都是**日本市场公告或厂商产品史**，不是缅甸车架清单。

| 官方时期切片 | 来源（厂商、日期） | 与发动机直接相关的内容 | 不能推广的部分 |
|---|---|---|---|
| 2002-07-02 首发家族 | Toyota《75 Years of Toyota》Probox / Succeed 产品史页面（2026-11-20 检视） | 发动机阵容为 **1.3L 汽油 2NZ-FE、1.5L 汽油 1NZ-FE、1.4L 共轨柴油 1ND-TV** 三机；传动 4AT 或 5MT；FF 为标准布置，**1.5L 汽油另有 V-flex 全时 4WD**；柴油 **2007-09 停售**； wagon 不提供柴油 | 是日本历史产品线整体叙述；Probox 侧柴油 van 的具体车型代码本页未列；不代表缅甸任意实车配置 |
| 2008-08-01 一部改良 | Toyota 官方公告 [global.toyota/en/detail/1641086](https://global.toyota/en/detail/1641086)（2008-08-01） | 发动机仍列 **2NZ-FE / 1NZ-FE / 1NZ-FNE（CNG）**；传动为 5MT 与 **Super ECT（智能 4AT）**；改良内容是高位制动灯等装备，**不含动力总成更换** | 只是装备改良；不能读作"2008 起动力总成有新家族" |
| 2014-08-06 改款（09-01 上市） | Toyota 官方公告 [global.toyota/en/detail/3737378](https://global.toyota/en/detail/3737378)（2014-08-06） | **1.3L 新搭载 1NR-FE（仅 Probox 设定）**、1.5L 1NZ-FE 延续、与 **Super CVT-i** 结合；VSC/TRC/坡道辅助全等级标配；前制动盘加大；官方称 minor change | Succeed 该公告只有 1.5L 等级；不能回推 2014 前车辆，也不能套给其它市场 |
| 2016-08-30 一部改良 | Toyota 官方公告 [global.toyota/en/detail/13332599](https://global.toyota/en/detail/13332599)（2016-08-30） | Probox 价格表：1NR-FE 1.3L（2WD）与 1NZ-FE 1.5L（2WD/4WD），**全表 Super CVT-i**；Succeed 全部 1NZ-FE 1.5L；**1.5L 2WD 标配怠速停止（Stop & Start）**；Toyota Safety Sense C 标配 | 怠速停止只属 1.5L 2WD 组合，不是全车系；公告未列 CNG 等级，其后 CNG 状态 UNKNOWN |

**厂商锚点**：[Toyota 75 年史·Probox](https://www.toyota-global.com/company/history_of_toyota/75years/vehicle_lineage/car/id60012554A/index.html)、[Toyota 75 年史·Succeed](https://www.toyota-global.com/company/history_of_toyota/75years/vehicle_lineage/car/id60006139B/index.html)（两页均 2026-11-20 检视）、上述 2008/2014/2016 三份公告、[缅甸 MDN/GNLM 2022-09-29 二手车市场报道](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand)。

不要把任何一份改款公告冒充"平台换代证明"：2014 公告官方语义是 minor change。同理，2008 公告没有动力总成变更，**不能替本表制造"2008 发动机换代"假节点**。

## 2. 发动机适用性矩阵：逐机型绑定来源，未记即 UNKNOWN

| 发动机 / 燃料类别 | Toyota 原始可见支持 | 确定范围（仅限来源所述） | 未知项与禁止推广 |
|---|---|---|---|
| `2NZ-FE`（1.3L 汽油） | 75 年史 Probox/Succeed 两页正文均列为 2002 首发三机之一；2008-08-01 公告仍列 2NZ-FE | 2002-07 发布家族存在 1.3L 汽油；至少到 2008-08 日本公告仍在产品表 | 气门机构、VVT 有无、正时机构、喷射形式：**本稿来源未记载 = UNKNOWN**；2014/2016 两份公告价格表未见 2NZ 等级，其此后存在性 UNKNOWN（缺席 ≠ 停产普遍证明）；缅甸实车装配 UNKNOWN |
| `1NZ-FE`（1.5L 汽油） | Succeed 75 年史规格表：**1496 cm³、直列 4 缸 DOHC**；Probox 75 年史等级名含 VVT-i（UA-NCP58G/59G）；2002→2008→2014→2016 四个切片连续出现 | 1.5L 汽油贯穿全部四个时期；2WD 为标准，1.5L 有 4WD（2002 为 V-flex 全时四驱；2014/2016 价格表 1.5L 含 4WD） | 喷射形式、正时机构、VVT 具体相位执行布置：UNKNOWN；缅甸装配 UNKNOWN |
| `1NR-FE`（1.3L 汽油） | 2014-08-06 公告：1.3L 车新搭载 **1NR-FE（Dual VVT-i；仅 Probox 设定）**；2016-08-30 价格表列 1NR-FE 1.3L DX/Comfort/GL，均 2WD、Super CVT-i | 2014-08 起日本 Probox 的 1.3L 机型；Succeed 在 2014/2016 公告只有 1.5L → **按这两份公告 1NR-FE 不适用 Succeed** | 1.3L 是否存在 4WD（2016 价格表仅见 2WD）：UNKNOWN；正时机构/喷射形式 UNKNOWN；缅甸装配 UNKNOWN |
| `1ND-TV`（1.4L 共轨柴油） | 75 年史两页正文：**1.4L common rail 柴油 1ND-TV**；Succeed 页规格表：**1362 cm³、直列 4 缸 SOHC、涡轮增压**；Probox 页：柴油 **2007-09 停售**、wagon 无柴油选项；Succeed 页 van 代码 `NLP51V(1400)` | 2002 家族的 **van 专用**柴油：压燃 + 共轨 + 涡轮增压 + SOHC；日本销售至 2007-09 | Probox 侧柴油 van 的具体车型代码（来源只给出 Succeed 的 NLP51V）：UNKNOWN；共轨部件构成、预热/冷起动装置、喷射压力：UNKNOWN；缅甸存量与持续在用数量 UNKNOWN |
| `1NZ-FNE`（1.5L CNG）· **P2-01 显式分支** | 75 年史：2003-04 追加 CNG 车型（减 CO2）；2008-08-01 公告价格表仍列 CNG 车型（最高价等级）；2014/2016 公告未列 CNG 等级 | **`EXCLUDED_OR_CONDITIONAL_UNTIL_MYANMAR_EVIDENCE`**：在缅甸实车证据出现前，CNG 变体不并入本文任何汽油/柴油机理叙述，也不为它新开 DAG 节点 | 2014 后 CNG 在日本产品线状态 UNKNOWN（公告未列 ≠ 已停销证明）；**缅甸存在量产 CNG Probox = UNKNOWN**；不得因某挂牌写"1.5 汽油"就推测其为 CNG |

两处来源内部的口径差必须原样保留，不得"顺化"：正文称 1ND-TV 为 "1.4-liter"，同一 Succeed 页规格表实测排量 **1362 cm³**——"1.4L"是系列命名口径，不是实测值。柴油 van 代码 `NLP51V` 目前只有 Succeed 侧记载，Probox 侧代码不能由名称相似推定。

## 3. 结构与功能：为什么发动机类别改变诊断空间

### 3.1 三个汽油机共享的机理族与其边界

2NZ-FE / 1NZ-FE / 1NR-FE 同属**火花点燃、节气门量调节**的机理族：空气路径经滤清/节流/歧管进入气缸，燃油按喷射架构供给，点火由火花塞提供，负荷控制以进气量为主轴。通用候选架构（含 PFI/GDI 分界、传感布置的多种可能）见 [STR-ENG-AIRFUEL](../../../../topics/engine/air-fuel-emissions/structure.md)。

**但"同一机理族"不等于"同一具体结构"**：本文来源只证实了三个机型名称、排量与 1NZ 的 DOHC/VVT-i 等级命名、1NR 的 Dual VVT-i，**没有证实**任一机型的喷射形式（PFI 或 GDI）、正时机构类型或附件布置。排量名（1.3L/1.5L）与等级名不决定燃油架构；把 GDI 的高压泵、高压轨假设套给这些旧机型没有任何本文来源支持。

### 3.2 VVT 配置差：一个可证实的代际差量点

来源可证实的排序：1NR-FE 为 **Dual VVT-i**（2014 公告，1.3L、仅 Probox）；1NZ-FE 等级名载 **VVT-i**（75 年史 1.5L 等级）；2NZ-FE 的 VVT 状态 **UNKNOWN**（来源未记）。VVT 相位执行依赖发动机机油压这一机理关联，属已审通用润滑结构稿的叙述范围（见 [润滑结构](../../../../topics/engine/lubrication/structure.md)）；因此凡涉 VVT 类症状候选，**机油供给健康度与 VVT 执行器是耦合但不同的两个解释方向**——这是机理级区分，不涉及任何具体油压数值或零件号（那是 `SER-DELTA-PROBOX-LUBE` 的条件任务边界，见 §5）。

### 3.3 柴油 1ND-TV 是另一个机理族，不是"柴油版汽油机"

按 75 年史记载，1ND-TV = **压燃 + 共轨燃油 + 涡轮增压 + SOHC**。它与汽油机的诊断空间差异是机理类别的差异，而非参数差异：

- **着火方式**：压燃依靠压缩热与喷油定时/雾化的配合，不存在"火花塞失火"这一汽油机专属概念；冷起动依赖压燃条件（具体预热装置 UNKNOWN）。
- **燃油系统**：共轨架构的高压燃油路径与汽油机低压喷射/点火耦合路径不同；本稿无任何 1ND-TV 共轨压力、部件或维修数据（UNKNOWN），也**不提供任何燃油系统处置操作**（高压燃油处置属禁止输出的危险操作）。
- **进气与增压**：涡轮增压使"供气不足"（机理类：管路/中冷/旁通的状态异常）成为柴油机独有的动力丧失候选族；自然吸气汽油机上不存在涡轮供气路径，把"增压管泄漏"套给 1NZ-FE 是类别错误。
- 本仓 topics 树中**没有柴油机专题文档**；本节只做机理类别对照，不生成 1ND-TV OEM 细节，也不把汽油机 [STR-ENG-AIRFUEL](../../../../topics/engine/air-fuel-emissions/structure.md) 的部件清单强加给柴油车。

### 3.4 时期性装备窗口：同一车名下的新增机理面

- 2014 改款把 **EPS、加大前制动盘、悬架前段重构**列入公告——这些属于底盘/转向差量（归 `SER-DELTA-PROBOX-BRK-SUSP` 范围），本文只记录"2014 起发动机舱周边布置可能随改款变化"这一交界事实，不展开。
- 2016 公告 **1.5L 2WD 标配怠速停止（Stop & Start）**：起停系统改变起动系统与蓄电池的负荷循环（机理类：更频繁的起动事件），是 2016 后该特定组合（1NZ-FE 1.5L + 2WD + Super CVT-i）才有的新增机理面；**不能套给 2002–2014 车辆、4WD、1.3L 或柴油 van**。起动/供电系统通用结构见 [低压电气结构](../../../../topics/electrical-low-voltage/structure.md)。

## 4. 失效机理与竞争诊断：同一症状必须按代际/燃料类别分账

方法框架（证据分层 S0–S4、竞争假说、误修成本）见 [DISC-METHOD](../../../../topics/common/diagnostic-methods.md)。下表只列**机理候选空间与鉴别条件**，不执行任何现场操作、不提供测量规程，不声称任何故障发生率。

| 客户可见现象（仅输入） | 2002 代汽油（2NZ/1NZ + 4AT/5MT）候选机理空间 | 2014+ 汽油（1NR/1NZ + Super CVT-i）新增候选 | 柴油 1ND-TV（van，至 2007-09）候选机理空间 | 错误跨型套用的反例 |
|---|---|---|---|---|
| 加速无力 / 间歇失速 | 点火、混合气、喷射供给、VVT（机型确认后）、压缩等点燃族候选 | 上述候选 + Dual VVT-i 相位执行（1NR）；与 CVT 交界处先分账（见 [传动差量](./transmission-applicability-delta.md)） | 共轨供油、增压供气、压燃条件；**无点火系候选** | "涡轮增压管漏气"套给自然吸气 1NZ-FE；"火花塞失火"套给无火花塞的 1ND-TV——两者都是类别错误 |
| 冷起动困难 | 起动转速、混合气形成、点火能量（点燃族候选） | 同左；2016 起该组合若有起停系统，起动系统负荷循环更长（机理类） | 压燃条件/冷态燃油（具体预热装置 UNKNOWN，不得凭常识断言 1ND-TV 预热配置） | "预热塞坏了"套给汽油机；"混合气过稀"直接套给柴油机冷起动而不先确认燃料类别 |
| 怠速不稳 / 抖动 | 点燃族：混合气、点火、节气门体/怠速控制路径、VVT（机型确认后） | 同左 + 1NR Dual VVT-i；起停系统介入/退出时的转速过渡（仅 2016 特定组合） | 压燃族：各缸喷油一致性、供气、机件状态 | 用"点火线圈"解释柴油抖动；用"共轨压力"解释汽油怠速抖动 |
| 排烟 / 排气异味 | 汽油族：混合气过浓、机油消耗（蓝烟机理类）；三元催化状态（通用机理，具体配置 UNKNOWN） | 同左 | 柴油族：燃油雾化/供油、增压段机油路径（黑烟机理类）；后处理配置 UNKNOWN | 把柴油黑烟逻辑直接套给汽油排黑烟（两种烟的机理族不同）；把 GPF/汽油颗粒滤假设套给旧车（无来源支持） |
| 油耗显著上升 | 多因素：混合气控制、点火、机件状态、驾驶/载荷 | 起停系统失效只影响其设计工况（2016 特定组合），不是全油耗解释 | 喷油/供气、增压、机件状态 | "起停坏了所以费油"套给 2010 年车（该组合不存在）；柴油喷油量逻辑直接套给汽油 ECU |
| 前部 / 正时区异响 | 附件驱动、VVT 执行（机型确认后）；**正时机构类型 UNKNOWN，不得断言链/带** | 1NR Dual VVT-i 执行器为新增候选（机理类） | 柴油机燃烧噪声与机械噪声分账；具体结构 UNKNOWN | 未确认机型就把"VVT 链条张紧器"写成具体零件结论——本文无任何机型的正时/张紧 OEM 证据 |

### 4.1 错误跨型诊断为何会发生（机理与制度原因）

1. **车名恒定、机头多变**：2002–2016 官方切片内发动机 lineup 至少经历"2NZ/1NZ/1ND-TV → +1NZ-FNE(CNG) → 1NR/1NZ"的变化窗口。经验上"某年 Probox 是 X 症状 = Y 零件"的口传结论，其隐含机型前提经常未被复验。
2. **症状词汇跨燃料通用、机理候选不通用**：无力/抖动/冒烟这些主诉在点燃与压燃两类机上同名，但候选族交集极小（见上表）；修理语境若不先确认燃料类别，就会把候选池整体套错。
3. **"1.4L/1.5L"这类命名口径会掩盖实测差异**：1ND-TV 名义 1.4L、实测 1362 cm³ 的来源内部口径差说明，按名称匹配零件/参数天然有系统性风险。
4. **改款公告≠动力总成变更**：2008 公告只动装备。若把"改款"当成"换了发动机"，会制造不存在的代际差量；反之 2014 确实换了 1.3L 机型（仅 Probox），漏看会造成 Succeed/Probox 误互换。

### 4.2 鉴别路径的条件（知识层，非操作规程）

任何跨型鉴别的第一分叉是**燃料与机型确认**（车架/铭牌/机型代码的可信证据），第二分叉是**生产时期窗口**（2002 / 2008 / 2014 / 2016 切片属于哪段），第三分叉才是对应机理族内的候选排序。证据分层与竞争假说权重方法依 [DISC-METHOD](../../../../topics/common/diagnostic-methods.md)。本文不给出任何 DTC→零件映射；在无实车 VIN/OEM 资料前，所有"哪一年装哪一机、哪个零件适配"均为 `MYANMAR_CHASSIS_AND_FITMENT=UNKNOWN`。

## 5. 润滑差量的边界：既有条件任务，不是本文内容

`SER-DELTA-PROBOX-LUBE` 是既有 SERIES DAG 中的 **`CONDITIONAL`（SOURCE_GAP）任务**，其正文 `engine-lubrication-delta.md` **目前不存在**；本文不重建该文件、不写任何机油规格/容量/油压数值，也不把"发动机名称更替"冒充"油路硬件差异已证实"。本文涉及润滑的只有两点机理级引用：

1. VVT 相位执行与机油压的耦合关系——通用叙述见 [润滑结构](../../../../topics/engine/lubrication/structure.md)；
2. 润滑类故障与其它族候选的鉴别方法——通用叙述见 [润滑故障鉴别](../../../../topics/engine/lubrication/diagnostic-repair.md)。

该条件任务的启动条件（具体机型锁定 + 真实油路硬件差异证据 + 柴汽油分账）仍按计划文件 §5 执行；条件不满足时其正确输出是 `NO_MATERIAL_DELTA_YET`，不是凑一篇通用润滑文章。

## 6. Probox 与 Succeed 适用性分账

| 差量点 | 已证实内容与来源 | 禁止推断 |
|---|---|---|
| 1NR-FE 1.3L | 2014/2016 公告：仅 Probox 设定；Succeed 该两份公告只有 1NZ-FE 1.5L | **不得把任何 1.3L 诊断/零件结论平移给 Succeed** |
| 柴油 van 代码 | Succeed 页记载 `NLP51V(1400)`；Probox 页确认 wagon 无柴油、van 有柴油但未列 Probox 侧代码 | Probox 柴油代码 UNKNOWN，不得由 NLP51V 字符串相似推定 |
| 车身/载货 | 75 年史：两车 cabin/body 长度略不同（Succeed van 货厢 1830 mm / 450 kg vs Probox van 1310 mm / 400 kg） | 车身差不是发动机互换的依据，也不反推载荷相关故障率 |
| 传动交界 | 2002 家族 4AT/5MT；2014+ Super CVT-i（详见 [传动差量](./transmission-applicability-delta.md)） | 发动机症状与传动症状在两稿交界处必须先分账再深入 |

## 7. 缅甸存量分账：市场线索 ≠ 配置事实

[缅甸 MDN/GNLM 2022-09-29 报道](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand)原文："Types of cars such as **PROBOX, SUCCEED, AD VAN**, Toyota Mark II 200 and unmodified WISH 2003 model are popular in the market."——只证明该系列有本地交易关注度，**不提供任何一辆实车的发动机代码、燃料类别、生产月份或维修记录**。[SER-DISC-PROBOX](./discovery.md) 已记录的 CarMM 挂牌年份字段自相矛盾（标题 2011 / 详情 2012）同样约束本文：不得为挂牌年份回填任何机型的诊断结论。

`MYANMAR_CHASSIS_AND_FITMENT=UNKNOWN` · `MYANMAR_ENGINE_CODE_DISTRIBUTION=UNKNOWN` · `MYANMAR_FUEL_CLASS_DISTRIBUTION=UNKNOWN`（日本 2007-09 停售柴油不等于缅甸路上无 1ND-TV 车，也不等于有）· `MYANMAR_CNG_PRESENCE=UNKNOWN` · `FUEL_QUALITY_EFFECT_ON_COMMON_RAIL=UNKNOWN`（劣质燃油影响共轨/喷射系统属机理级候选，本文无缅甸实证，不断言）。

## 8. 差量结论与 STOP

| 项目 | 结果 |
|---|---|
| `MATERIAL_DIFFERENCE_CONFIRMED_IN_OEM_FAMILY` | **是**：燃料类别（点燃三机型 vs 压燃 1ND-TV）、代际（2NZ/1NZ → 1NR Probox 专属 + Super CVT-i 时期）、机型专属装备（2016 起停仅 1.5L 2WD）均为厂商来源证实的实质差量 |
| `APPLICABLE_TO_SPECIFIC_MYANMAR_VEHICLE` | **UNKNOWN**：无实车车架/制造期/机型代码，一切装配断言被禁止 |
| `REUSE_FROM_GENERIC` | 汽油机架构复用 [STR-ENG-AIRFUEL](../../../../topics/engine/air-fuel-emissions/structure.md)；VVT-机油压耦合与润滑鉴别复用 [润滑结构](../../../../topics/engine/lubrication/structure.md) / [润滑故障鉴别](../../../../topics/engine/lubrication/diagnostic-repair.md)；方法层复用 [DISC-METHOD](../../../../topics/common/diagnostic-methods.md)；柴油机**无**共享专题稿，本文仅机理类别对照 |
| `P2-01_CNG_BRANCH` | 已执行：1NZ-FNE 显式 `EXCLUDED_OR_CONDITIONAL_UNTIL_MYANMAR_EVIDENCE`，未并入汽油/柴油叙述，未新增 DAG 节点 |
| `LUBE_CONDITIONAL_STATUS` | `SER-DELTA-PROBOX-LUBE` 正文不存在、维持 CONDITIONAL；本文未代写、未重建 |
| `DUPLICATION_STOP` | 通用汽油机架构、VVT 原理、诊断方法不再逐年款复制；下钻必须先有真实机型/车架证据，否则 `BLOCKED_SOURCE` |
| 职业安全边界 | 本文不含燃油系统高压处置、举升、接触高温/旋转件、路试或任何现场操作；只做知识分类与鉴别条件 |

**本任务交付的是"已生成、可独立复核的发动机代际/燃料类别差量候选"**，不是缅甸实车配置对应关系，不是维修操作授权。原始专业事实、OEM 适配与 N3 均未授予；后续独立审阅应针对本 Exact Blob 检查 Markdown 深度、来源范围、错误跨型泛化与 UNKNOWN 完整性。

### 主要 UNKNOWN 清单（审阅锚）

`2NZ-FE 气门机构/VVT/正时/喷射形式` · `1NZ-FE VVT 相位执行布置/正时/喷射形式` · `1NR-FE 正时/喷射形式/1.3L 4WD 存在性` · `1ND-TV 共轨部件构成/预热装置/喷射压力/Probox 侧 van 代码` · `2NZ-FE 在 2014 后日本产品线的存在性` · `1NZ-FNE CNG 2014 后状态与缅甸存在性` · `MYANMAR_CHASSIS_AND_FITMENT / 机型分布 / 燃料类别分布` · `燃油品质对共轨系统的缅甸实证` · `各机型失效率/工单占比`（无任何统计分母）。
