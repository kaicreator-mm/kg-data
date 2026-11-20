# 汽油机「请求→充气→燃油→点火→λ反馈→催化→扭矩」正常工作机理（FUN-ENG-AIRFUEL R23）

> TASK_ID: `FUN-ENG-AIRFUEL` · MAIN: [parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) · 独立准入：[#61/7021821148](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7021821148) · 派发：[#61/7021981579](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7021981579)  
> 直接上游：[`structure.md`](./structure.md)，Exact Blob `a0a5dceadb22a1588876d1001e5a0a0451709469`，本文只写其结构之上的**正常功能机理层**，不写失效因果；证据分层方法复用 [通用诊断方法](../../common/diagnostic-methods.md)。  
> 身份：`MODEL_GENERATED_UNVERIFIED` / `GENERATED_REVIEW_PENDING`；OEM/VIN/N3=NOT_GRANTED。厂商技术页只支持其明确叙述的技术方案存在，不构成缅甸实车装配、维修参数或法规认证证据。  
> 主要问题：面对一台燃油/点火/排放配置未知的缅甸在用汽油机，「驾驶员请求→进气充气→燃油计量→点火→λ闭环→催化转化→实际扭矩输出」每一环节的物理输入/输出是什么，哪些常见理解是错的？

## 1. 适用性先行：车名不进入机理链，架构证据才进入

本文机理链对**点燃式、节气门量调节的汽油机**成立，且每一环节都存在架构分叉；落入哪一支必须由证据决定，不能由车型名自动填表：

| 判定对象 | 允许进入该分支的证据 | 证据缺失时的正确状态 |
|---|---|---|
| 燃料喷射架构 | 发动机代码 + OEM 资料（公告/认证/目录行） | `FUEL_ARCHITECTURE = PFI \| GDI \| DUAL \| OTHER \| UNKNOWN` 取 UNKNOWN |
| 进气计量方式 | 该机型 ECU 感知配置的原始资料 | `AIR_METERING = MAF \| SPEED_DENSITY \| OTHER \| UNKNOWN` |
| 上游 λ 传感器类型 | 传感器产品形态或原始装配资料 | `UPOS_SENSOR_TYPE = WIDEBAND \| NARROWBAND \| UNKNOWN` |
| 缅甸 2002–2016 候选（Probox 2NZ/1NZ/1NR、AD 汽油机、Swift、Wish） | 车架/铭牌/发动机代码 | 只保留「大概率 PFI」的研究性倾向，断言权为 0 |

已接受语料提供的架构分叉锚点：[Probox 发动机代际差量](../../../series/myanmar/toyota/probox/engine-generation-variants.md)证实 2NZ-FE/1NZ-FE/1NR-FE 的**喷射形式在厂商来源中未记载**（UNKNOWN）；同车名内 PFI 类与 GDI 类并存的厂商级反例见 §5 案例 B（Wish）。整条链的供电/起动/通信可用性是前置接口，见 [低压结构](../../electrical-low-voltage/structure.md)；VVT 相位执行依赖机油压的耦合见 [润滑结构](../lubrication/structure.md)；工作温度接口见 [热管理结构](../../thermal/structure.md)。

## 2. 正常机理分层：每层的物理输入与输出

链路的设计锚点是**过量空气系数 lambda（λ）= 实际空燃比 / 理论空燃比**；λ=1 表示理论完全燃烧比例。

| 环节 | 物理输入 | 物理输出 | 正常功能要点 |
|---|---|---|---|
| ① 驾驶员请求 | 踏板位置电信号、挡位/车速 | 目标扭矩请求（不是空气量，也不是喷油量） | 请求先经仲裁，非直通执行器 |
| ② 进气充气 | 大气状态、节气门流通面积、转速、VVT 相位 | 每缸实际空气充量（质量） | 充气是被测/被估对象，不直接测缸内 |
| ③ 充气测量 | 空气流（MAF）或歧管压力+进气温度+转速（speed-density） | 充气估计值 | 两类架构二选一，非叠加必需 |
| ④ 节气门执行 | ECU 目标开度（电子）或踏板拉线（机械） | 进气流通面积 | 电子节气门下踏板 ≠ 开度 |
| ⑤ 燃油计量 | 充气估计 + 目标 λ + 轨压信息 | PFI：喷油脉宽；GDI：脉宽+轨压+喷射相位 | PFI 靠时间计量，GDI 时间与压力并用 |
| ⑥ 点火 | 转速/相位、充气负荷、爆震反馈、电源电压 | 点火提前角 + 闭合角（决定火花能量） | 提前角与能量是两个独立输出 |
| ⑦ λ 闭环 | 排气残余氧（上游传感器） | 喷油脉宽修正（短期/长期） | 修正围绕目标 λ；传感器不测油压/催化器 |
| ⑧ 催化转化 | 排气温度窗口 + λ≈1 附近混合气 + 储氧能力 | HC/CO 氧化、NOx 还原 | 温度与混合气两个窗口须同时满足 |
| ⑨ 扭矩输出 | 充气 × 喷油 × 点火 × 燃烧与机械效率 | 曲轴实际扭矩 | 多请求源仲裁后的净结果 |

### 分层反例细化

- **充气与测量**：MAF（热膜式）直接测进气质量流量；speed-density 架构用 MAP+IAT+转速从充气模型推算——**未见 MAF 不是故障**。EGR、PCV、EVAP 脱附气体都会改变进入歧管的实际气体量，正常功能内它们是充气的合法输入，不是"漏气"。
- **踏板与节气门非单射**：电子节气门下踏板只是请求源之一，怠速稳定、冷机快怠速、牵引/稳定干预、换挡扭矩缓冲、过热与催化器保护都会修正实际开度；踏板到底 ≠ 节气门 100%，怠速时节气门也非按"全闭"理解。
- **燃油计量**：PFI 由调压器维持低压轨相对恒压，喷油器开启**脉宽**决定喷油质量，混合气在进气门附近形成；GDI 由发动机驱动高压泵把轨压提到随工况变化的水平，喷射相位与轨压共同参与缸内混合气形成。两类架构的部件差异（低压轨 vs 高压泵/高压轨）见 [STR-ENG-AIRFUEL](./structure.md) §3。
- **点火**：提前角按负荷/转速映射并受爆震闭环修正；闭合角决定线圈储能即火花能量。爆震反馈属正常功能：识别异常燃烧振动→推迟提前角，"听不到敲击"≠"没有爆震修正发生"。
- **λ 闭环**：窄域（切换型）传感器输出只在 λ≈1 附近翻转的开关信号，ECU 靠周期性摆动维持均值 λ≈1；宽域（线性）传感器给出连续 λ 信息。修正量在现代系统概念中表现为短期/长期燃油修正（STFT/LTFT）。氧传感器**不测量**燃油泵压力，也**不测量**催化器转化率。
- **催化转化条件**：三元催化器（TWC）高效工作需要起燃温度以上的排气温度窗口、λ≈1 附近的混合气供给、以及储氧材料的可用氧容量；冷机阶段排放偏高是设计内现象，不是"催化器已失效"的证据。实车判定阈值一律 UNKNOWN。
- **扭矩协调**：ECU 仲裁驾驶员请求、怠速、催化器暖机（推迟点火提升排温）、变速器换挡、空调接入、牵引/稳定干预、过热保护等请求源；任何一个源都可降低净扭矩——正常功能内的"踩油门反应弱"可由仲裁解释，不必然是故障。

## 3. 反例矩阵：常见误解 vs 实际机理

| 常见误解 | 实际机理 | 有区分力的理解要点 |
|---|---|---|
| 「没找到 MAF = MAF 坏了」 | speed-density 架构本就不用 MAF，靠 MAP+IAT+转速推算充气 | 先确认该机型感知架构，再谈部件 |
| 「踏板踩多深节气门就开多大」 | 电子节气门下踏板是请求，ECU 按怠速/牵引/保护修正开度 | 电子与机械拉线是两种不同架构 |
| 「油压高 = 喷油多」 | PFI 恒压+脉宽计量；GDI 才按工况调节轨压 | 计量维度：时间 vs 时间+压力+相位 |
| 「1.5L 自动挡 Probox = GDI / Dual VVT-i」 | 车名/排量/变速器名不决定喷射与配气架构 | 判定唯一入口是发动机代码+OEM 证据 |
| 「氧传感器电压 = 浓稀度直接读数」 | 窄域只在 λ≈1 附近开关摆动；宽域才是连续测量 | 传感器类型决定可读出的信息量 |
| 「λ 传感器与催化器好坏可以互证」 | 二者串联但对象不同：一个反馈混合气，一个转化污染物 | 上游修正正常 ≠ 催化器正常 |
| 「闭环 = 永远精确 λ=1.000」 | TWC 系统按设计围绕 λ≈1 摆动；暖机/加速等工况可开环 | 闭环是控制策略，不是常数 |
| 「冷车尾气臭 = 催化器坏了」 | 催化器需起燃温度窗口；冷机高排放是设计内 | 温度是转化条件之一，不是故障证据 |
| 「点火提前角越大越有力」 | 提前角在最优扭矩/爆震边界间闭环修正；过大→爆震，过小→排温升高 | 提前角是被优化折中的输出 |
| 「扭矩只由油门决定」 | 怠速/换挡/空调/保护等请求源都能降低净扭矩 | 输出是仲裁后的净结果 |

## 4. 与 FAIL/REP 层的边界声明

本文只回答「配置证实后各环节如何正常工作」。空燃比偏移、缺火、怠速异常、催化器退化等**失效因果、竞争根因、证据价值与维修决策**属 [STR §9](./structure.md) 列出的 FAIL/REP 候选任务，本文不预支任何失效结论，也不提供 DTC→零件映射或测量阈值。

## 5. 缅甸候选案例区：身份不明时的正确出口

### 案例 A：挂牌「Probox 2011 1.5L Automatic」被推断为 GDI + Dual VVT-i

CarMM 挂牌字段自相矛盾（标题 2011 / 生产年 2012），仅有车名/排量/变速器的口语信息（[Probox 发现](../../../series/myanmar/toyota/probox/discovery.md)）。已接受代际差量证实：1.5L 对应 1NZ-FE（等级名含 VVT-i），但三个汽油机的喷射形式在厂商来源中均未记载；1NR-FE Dual VVT-i 仅属 2014-08 起的 1.3L 且仅 Probox 设定。由「1.5L 自动挡」推出 GDI 或 Dual VVT-i 没有任何来源支持。正确出口：`ENGINE_CODE=UNKNOWN → FUEL_ARCHITECTURE=UNKNOWN`，保留「2002–2016 候选大概率 PFI」的研究倾向但不断言；机型与凸轮配置移交车型级身份核验。

### 案例 B：同为 2003 Wish，1.8L 与 2.0L G/Z 是两条燃油架构

Toyota 2003-01 首发公告列 1ZZ-FE 1.8L（喷射形式来源未记）；2003-04 追加公告对**特定 2.0L G/Z 切片**列 1AZ-FSE D-4 缸内直喷 + VVT-i（[Wish 发现](../../../series/myanmar/toyota/wish/discovery.md)）。同一车名、同一发布年份窗口内进气道喷射类与缸内直喷类**真实并存**——这是「车名+年份不能判定燃油架构」的厂商级反例。正确出口：按发动机代码分账；GDI 机理（轨压随工况、喷射相位参与混合气形成）只对证实为 D-4 的切片适用；缅甸任一实车的装配状态 UNKNOWN。

### 案例 C：2011/2012 Swift 挂牌被倒填 2013 双喷射技术

缅甸挂牌出现 2011/2012 Swift（[Swift 发现](../../../series/myanmar/suzuki/swift/discovery.md)）；Suzuki 2013 公告的 Dualjet/Ene-Charge 分支属**特定新车型的较新燃烧/喷油与能量管理方案**，其具体喷射构型在已复用来源中同样未记载——既不能把 2013 技术倒填旧车，也不能凭营销名称自动归类燃油架构。旧报告 `ENGINE_CODE=UNKNOWN_LOCAL`，不得自动写入 K12B/M13A/M15A/M16A 之一。正确出口：双喷射/能量管理配置 = UNKNOWN 或待证候选；架构判定移交发动机代码证据。同类分叉逻辑也适用于 AD Van 的 HR15DE/HR16DE/MR18DE 多机型并存（[AD Van 发现](../../../series/myanmar/nissan/ad-van/discovery.md)）。

## 6. 来源表（全部复用已接受语料中已出现的 URL，无新增）

| 来源（原出版方） | 可支持的限定事实 | 不支持的外推 |
|---|---|---|
| [Bosch：Gasoline port fuel injection](https://www.bosch-mobility.com/en/solutions/powertrain/gasoline/gasoline-port-fuel-injection/) | 进气道喷射、低压轨与 ECU 时序的架构存在；混合气在进气道形成 | 某缅甸年款必为 PFI；任何油压数值 |
| [Bosch：Gasoline direct injection](https://www.bosch-mobility.com/en/solutions/powertrain/gasoline/gasoline-direct-injection/) | 高压泵/高压轨/缸内喷油器组合、压力可按工况控制 | 任一实车轨压、喷射正时维修值 |
| [Bosch：Engine control unit](https://www.bosch-mobility.com/en/solutions/control-units/engine-control-unit/) | ECU 统筹空气、供油、喷射、点火、排气与扭矩协调 | 具体软件版本、仲裁优先级参数 |
| [Bosch：Hot film air-mass meter](https://www.bosch-mobility.com/en/solutions/sensors/hotfilm-airflow-sensor/) | MAF 以热膜方式测空气质量流量的产品范例 | 所有汽油机必有 MAF |
| [Bosch：MAP / boost pressure sensor](https://www.bosch-mobility.com/en/solutions/sensors/intake-manifold-and-boost-pressure-sensor/) | 歧管压力/温度感知作为另一类感知方式 | 该感知在特定车型的存在性 |
| [Bosch：Wideband lambda sensor](https://www.bosch-mobility.com/en/solutions/exhaust-gas-treatment/wideband-lambda-sensor/) | 宽域 λ 传感的连续余氧信息参与混合气调节 | 所有车型用宽域；统一 λ 阈值 |
| [DENSO：Lambda sensors](https://www.denso-am.eu/products/engine-management-systems/lambda-sensors) | λ 传感与空燃比控制、催化器高效运行的关系 | 实车催化器状态判定 |
| Toyota Wish 2003-04 公告（经已接受 [Wish 发现](../../../series/myanmar/toyota/wish/discovery.md) 复用） | 特定 2.0L G/Z 切片 1AZ-FSE D-4 缸内直喷存在 | 缅甸 Wish 装配 D-4 |
| Toyota 75 年史 Probox/Succeed 与 2014-08 公告（经已接受 [代际差量](../../../series/myanmar/toyota/probox/engine-generation-variants.md) 复用） | 2NZ/1NZ/1NR 机型存在、1NZ VVT-i 等级名、1NR Dual VVT-i（2014 起，仅 Probox） | 任一机型喷射形式；缅甸实车装配 |

## 7. UNKNOWN 清单与安全 STOP

**持续 UNKNOWN**：缅甸候选车的 `FRAME/VIN`、`BUILD_MONTH`、`ENGINE_CODE`、实车 `FUEL_ARCHITECTURE`、`AIR_METERING_TOPOLOGY`、`UPOS_SENSOR_TYPE`、`ECU_CALIBRATION`、`AFR_TOLERANCE`、`INJECTION_PRESSURE_SPEC`、`SPARK_ADVANCE_MAP`、`CAT_LIGHTOFF_TEMP` 实车值、`EMISSIONS_VERSION`、各架构 `FAILURE_RATE`、任何维修成效数据。

**安全 STOP**：燃油系统带压拆装、喷油器/油轨操作、点火高压部件带电作业、排气高温部件接触、氧传感器/催化器判定、ECU 刷写与路试验证均属合格人员按对应 OEM 版次执行的作业；本文是研究级机理叙述，**不是操作顺序**，不授权任何现场测量、拆装或替换动作。

**完成边界**：本文在 STR-ENG-AIRFUEL 结构层之上新增正常功能机理层（物理输入/输出、架构分支判定、反例矩阵、案例出口）。GENERATION_QUALITY 只能由未来非 Writer 独立审核按本 Exact Blob 授予；OEM/VIN/N3 资格仍为 0；FAIL/REP 层不在本文完成。
