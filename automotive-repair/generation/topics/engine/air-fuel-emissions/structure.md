# 汽油机进气、燃油、点火与排放控制：结构组成与架构边界（STR-ENG-AIRFUEL）

> Task ID: `STR-ENG-AIRFUEL` · MAIN: [parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) · FIRST PHASE: `MARKDOWN_ONLY` · `MODEL_GENERATED_UNVERIFIED`。本文研究**轻型火花点火汽油发动机通用候选架构**，不是缅甸任何特定车型/年份/发动机代码的 OEM 零件清单、排放标准断言或可执行维修操作。公开原始厂商技术资料只支持其明确叙述的技术方案；制造商装车配置、VIN fitment、校准参数、排放法规版本与真实故障发生率均为 `UNKNOWN`。

## 1. 系统树：从空气、燃油到排气闭环，不从故障码开始分类

一辆汽油机汽车的相关系统可以条件化分为六个相互耦合的子系统：

```text
火花点火汽油动力总成（仅条件化结构）
├─ [A] 进气与充气：进气口/滤清/管路 → 节气门/歧管 → 进气门/气缸
│   ├─ 空气质量或压力/温度测量；机械/电子节气门
│   └─ 增压器、进气中冷器、可变进气机构（按发动机配置存在）
├─ [B] 燃油储存与供给：油箱/蒸发控制 → 泵/过滤/供油管路
│   ├─ PFI/MPI：低压侧供油轨/歧管或进气道喷油器
│   └─ GDI：低压供油 → 发动机高压泵/油轨/压力测量 → 缸内喷油器
├─ [C] 点火：供电/ECU 信号 → 驱动/点火线圈 → 火花塞 → 燃烧室
├─ [D] 排气与后处理：排气歧管 → 上游混合气传感/催化装置 → 下游监测
│   ├─ 三元催化器（适用时）；后置传感器（适用时）
│   └─ 汽油颗粒捕集 GPF、二次空气等（仅特定配置）
├─ [E] ECU/发动机管理：驾驶员/传动/排放/安全扭矩需求 → ECU
│   └─ 曲轴/凸轮、MAP/MAF/IAT、冷却液温度、爆震、λ、压力等传感
└─ [F] 关联边界：发动机润滑/冷却、起动/供电/网络、变速器/驱动轮
```

**结构索引与因果关系不同**：ECU 同时使用多传感器反馈形成跨系统闭环，可以有反馈环；执行 Task DAG 仍必须无环。这里是硬件和信号/物质接口图，不是故障率表，也不代表全部对象每车必备。

## 2. 进气链：空气滤清、计量、节流、歧管与气门

| 部件或功能组 | 典型结构位置/连接 | 存在条件及重要区别 |
|---|---|---|
| 空气滤清、入口与导管 | 外界空气 → 入口/滤清器 → 管道 → 节气门/增压段 → 歧管 | 车型进气管路、曲轴箱通风连接与谐振腔不同；不把某一张进气图当 OEM 通用路径 |
| MAF（空气质量流量） | 常装于进气管路测量吸入空气的质量流量 | 有些控制架构以 MAP/IAT/转速推算充气（speed-density）而不使用独立 MAF；不能凭“未见 MAF”判故障 |
| MAP/增压压力与 IAT | 歧管或增压管路中，用于压力/温度估计 | MAP 的物理量是压力，不是直接读到的实际汽缸进气质量；测量点与几何需核实 |
| 节气门 | 控制进气通道开度，机械或电子驱动视配置 | 踏板位置不是实际节气门角度；电子节气门可能同时受到怠速、牵引与保护需求影响 |
| 进气歧管、进气门与配气执行 | 分配进气至各缸；有些系统具可变气门正时/升程 | 多歧管、歧管喷射、EGR、VVT 的组合变化大；没有这些部件也不代表不是汽油机 |
| 增压与换热（可选） | 涡轮增压器/机械增压器、增压管路、中冷器、废气旁通等 | 自然吸气车型不应生造这些部件；排气增压与燃油蒸发控制不是同一回路 |

跨系统接口：VVT（适用时）可能利用主机油路液压执行，参见 [润滑结构](../lubrication/structure.md)；增压器可能连接润滑/冷却回路，参见 [热管理结构](../../thermal/structure.md)。**交叉引用不制造额外硬前置**。

Bosch 官方 MAF、MAP/增压压力传感器资料证实存在不同感知方式，未证明 Toyota Probox 或 Honda Fit 的具体配备情况。

## 3. 燃油链：歧管喷射与汽油缸内直喷的拓扑边界

### 3.1 汽油进气道/歧管喷射（PFI / MPI）

常见候选路径为：油箱 → 低压供给模块/相关调节与过滤 → 低压油轨 → 进气道喷油器 → 进气门附近混合 → 气缸。发动机转速、传感与 ECU 信号决定喷油时序/脉宽；**实际燃油压力和流量依装车系统，不能给出普适数值**。

PFI 中“混合发生在进入气缸之前”不同于 GDI 的缸内喷射；PFI 没有被 GDI 的独立汽油高压泵/缸内高压油轨结构强制要求。Bosch 原始资料明确区分这两类架构：[Gasoline port fuel injection](https://www.bosch-mobility.com/en/solutions/powertrain/gasoline/gasoline-port-fuel-injection/)。

### 3.2 汽油缸内直喷（GDI）

典型候选路径为：油箱低压供给 → 发动机驱动高压泵（按设计）→ 高压油轨及传感/调节 → 缸内喷油器 → 燃烧室。高压泵与油轨属于**缸内直喷专属相关架构**，不能把喷油器在进气道的传统 PFI 也判成高压直喷系统。厂家有不同燃油压力控制方案、缸内成层/均质燃烧策略，不假设任何版本所有工况同样运行。

Bosch 的 GDI 系统原始技术页支持高压泵、高压轨、缸内喷油器的组合存在，并介绍其自身系统组成：[Gasoline direct injection](https://www.bosch-mobility.com/en/solutions/powertrain/gasoline/gasoline-direct-injection/)。

### 3.3 同一车型或代际可有不同燃油架构

车型名称不足以唯一标识燃油系统。即使都是“1.5L”或“自动挡”，地区、发动机代号、生产期及排放规范也可能改变 PFI/GDI、燃油轨/传感器、线束与执行器。部分发动机允许 PFI+GDI 双喷射，这既不是“只有 PFI”也不是“仅 GDI”。`FUEL_ARCHITECTURE = PFI | GDI | DUAL | OTHER | UNKNOWN` 应按发动机代码与 OEM 证据选用，而非用户口述车型自动填表。

## 4. 点火链与 ECU 输入：火花控制不是“喷油器”的附属开关

- **火花点火链**：电源和控制器 → 点火驱动 → 线圈/高压转换 → 火花塞 → 混合气燃烧。线圈在火花塞上的 COP（coil-on-plug）与分缸/共线圈、旧式分电器架构不同，不能把现代 COP 视为所有缅甸老车的标配。
- **曲轴/凸轮信号**：发动机转速与相位信息为喷油/点火提供时序依据；相位关系、是否有单独凸轮传感和控制算法依机型不同。
- **爆震传感/点火校正（适用时）**：用于识别相关燃烧振动并调整控制，不等于每次噪声都由真实爆震引起，也不能反推没有听到敲击就无异常。
- **ECU 的扭矩协调**：驾驶员踏板、怠速、排放、发动机保护、变速器换挡、ESP/牵引控制等请求可能共同决定目标扭矩。踏板、喷油脉宽和车轮实际输出不是彼此单射关系。
- **电气基础**：起动/低压供电/继电器/保险/接地、CAN 等连接会影响 ECU/点火/燃油泵的可用性；这些部件归 [低压结构](../../electrical-low-voltage/structure.md) 共有主题，不重复制作一个“汽油机专属 CAN 网络”。

Bosch 原始 ECU 技术页明确区分燃油供给、空气管理、喷射、点火、排气系统协调与扭矩管理：[Engine control unit](https://www.bosch-mobility.com/en/solutions/control-units/engine-control-unit/)。

## 5. 排气与排放控制：流体路径、传感闭环和法规资格分账

在装备三元催化器与相应反馈的汽油机上，概念路径可写为：燃烧排气 → 排气歧管 → 上游氧/空燃比传感器（按设计）→ 催化处理部件 → 可能的下游氧传感器/GPF → 排气管。发动机控制利用排气中的残余氧信息调节混合气，但**氧传感器不是直接测量“燃油泵压力”或“催化器净化率”**。

| 排放/反馈对象 | 基本作用 | 不要混淆 |
|---|---|---|
| 上游 λ / A/F 传感器 | 反馈排气剩余氧及空燃比相关信息，辅助 ECU 混合气控制 | 宽域传感器和切换型窄域传感器的输出特性并不相同 |
| 下游传感器（适用时） | 可用于催化后端监控等策略 | 不能从“装有两个传感器”推断具体监测算法/阈值 |
| 三元催化器（TWC） | 在适合温度/混合气等条件下参与 HC、CO、NOx 等污染物转化 | 不是每种发动机/排放级别都用相同催化器和位置 |
| EGR（适用时） | 对特定架构将部分排气引回进气以影响燃烧/排放 | 没有外部 EGR 阀不等于发动机完全不采用内部残余气调节 |
| 曲轴箱通风/PCV | 与曲轴箱气体、进气管路及排放控制相联系 | 不是燃油箱 EVAP 活性炭罐 |
| EVAP 蒸发排放控制（适用时） | 油箱燃油蒸气储存/受控脱附，与进气系统联系 | 不是尾气三元催化本体，亦非柴油 SCR/DPF |
| GPF/颗粒过滤（特定汽油系统） | 在适用配置中管理发动机颗粒排放 | 不能将柴油 DPF/SCR 方案无条件套到汽油旧车 |

Bosch [wideband lambda](https://www.bosch-mobility.com/en/solutions/exhaust-gas-treatment/wideband-lambda-sensor/) 与 DENSO [lambda 传感器介绍](https://www.denso-am.eu/products/engine-management-systems/lambda-sensors) 为公开原出版方锚点；它们不构成“某款缅甸车达到 Euro 6、必须装 GPF”之证据。法律排放标准、年款区域、后处理实际安装状态全部依原始认证/出厂资料判断，`EMISSIONS_VERSION=UNKNOWN`。

## 6. 跨结构的功能接口与后续故障分析意义

| 系统接口 | 输入/输出与依赖 | 非唯一的故障解释候选（尚未生成 FAIL/FUN） |
|---|---|---|
| 进气 ↔ 喷油 | 实际充气和估计充气影响喷油与扭矩 | “混合气偏稀”可能涉及空气测量、漏气、燃油供给/喷油、排气传感，而非一个喷油器 |
| 点火 ↔ 机械状态 | 燃烧稳定与火花能量、压缩、配气和进气状态有关 | “缺火”不必然线圈损坏；机械/燃油/信号与点火都有竞争原因 |
| ECU ↔ 变速器/ESP | 请求扭矩、保护/干预、换挡工况相互影响 | “动力下降”可能是保护模式/变速器/制动介入，非纯发动机故障 |
| EVAP/PCV ↔ 进气 | 燃油蒸气或曲轴箱气体按设计进入进气系统 | “怠速异常”可能关联额外进气、蒸发脱附、节气门或测量 |
| 润滑/热管理 ↔ 配气/增压 | 油温、VVT、涡轮润滑/冷却与充气和燃烧共同作用 | 某高温工况的失效可能不在进气燃油系统内部 |
| 催化器 ↔ λ 反馈 | 混合气控制与后处理条件互相关联 | 下游异常不等于直接证实催化器本体已损坏 |

**状态边界**：该矩阵仅提出后续功能/失效/诊断研究题，不代表本文已完成它们，且不是 DTC 到零件的替换映射。

## 7. 缅甸在用车型与资料可见性

- **Toyota Probox/Succeed**：[既有车型发现](../../../series/myanmar/toyota/probox/discovery.md) 仅证明其作为缅甸存量维修候选的有限来源，不能由“Probox”自动填入 GDI、高压燃油轨或固定排放标准。
- **Honda Fit/Jazz**：[既有车型发现](../../../series/myanmar/honda/fit/discovery.md) 涵盖多个代际/动力候选；IMA、i-DCD、e:HEV 的驱动/发电/停机模式不可全部当传统独立汽油机，必须按实际发动机与传动版本限制燃油/点火运行状态。
- **通用与版次分离**：本篇 `L0/L1` 结构研究可供多车系引用；没有 `market+year+chassis+engine_code+emissions+ecu_calibration` 对应原始资料时，`L3/L4_INSTALLATION`、`FUEL_PRESSURE_SPEC`、`SPARK_PLUG_PART`、`AFR_TOLERANCE`、`CAT_TEST_THRESHOLD`、`PART_INTERCHANGEABILITY`、`FAILURE_RATE` 均保持 `UNKNOWN`。不把日本官网某年款资料倒灌缅甸任意 VIN。

## 8. 原始出版方来源表（实际可读页面；事实与研究综合分账）

| 原始资料 | 可支持的限定事实 | 不支持外推 |
|---|---|---|
| [Bosch：Gasoline port fuel injection](https://www.bosch-mobility.com/en/solutions/powertrain/gasoline/gasoline-port-fuel-injection/) | 进气道喷射、低压喷油轨与 ECU 等 PFI 结构 | 某 Probox 年款必然是 PFI 或其零件码 |
| [Bosch：Gasoline direct injection](https://www.bosch-mobility.com/en/solutions/powertrain/gasoline/gasoline-direct-injection/) | 高压泵/高压轨/缸内喷油器作为 GDI 技术组合 | 任一车型高压测试值、安装位置及维修步骤 |
| [Bosch：Engine control unit](https://www.bosch-mobility.com/en/solutions/control-units/engine-control-unit/) | ECU 统筹空气、供油、喷射、点火与扭矩协调 | 特定车型软件版本、ECU pinout 或故障逻辑 |
| [Bosch：Hot film MAF](https://www.bosch-mobility.com/en/solutions/sensors/hotfilm-airflow-sensor/) | MAF 通过传感方式测空气质量流量的产品范例 | 所有 ICE 必有 MAF |
| [Bosch：MAP / boost sensor](https://www.bosch-mobility.com/en/solutions/sensors/intake-manifold-and-boost-pressure-sensor/) | 歧管/增压压力与温度感知的供应商范例 | 所有车型有涡轮或相同歧管几何 |
| [Bosch：Wideband lambda](https://www.bosch-mobility.com/en/solutions/exhaust-gas-treatment/wideband-lambda-sensor/) | 尾气余氧信号参与 ECU 混合气/排放调节 | 全部排放车型都有该宽域部件、同一 λ 电压阈值 |
| [DENSO：How lambda sensors work](https://www.denso-am.eu/products/engine-management-systems/lambda-sensors) | 传感反馈与发动机空燃比、催化器有效运行关系 | 具体车辆催化器已经失效或达成某法规认证 |

以上技术页能够确定**这些汽车工程技术和可选部件真实存在**，却不能独立证明当地实际装车 BOM、VIN 适用性或真实维修值。本文的功能划分、系统树、条件化竞争原因是模型独立综合，`MODEL_GENERATED_UNVERIFIED`；不得将厂商产品目录冒充特定 OEM 服务手册。

## 9. 动态缺口与接续任务（不擅改已审 DAG）

1. `FUN-ENG-AIRFUEL`：不同进气估计/节气门、PFI/GDI、点火和 λ 反馈怎样形成请求→执行→实际燃烧扭矩的条件化机理；**当前未在已审 DAG 中单独准入**。
2. `FAIL-ENG-AIRFUEL`：空燃比偏移、缺火、怠速异常、排放监测等因果链、对温度/负荷敏感的反例与竞争根因；**当前未准入**。
3. `REP-ENG-AIRFUEL`：区分燃油/空气/点火/机械/信号/后处理的证据价值、误修代价及 UNKNOWN；非操作性研究，需新增量审核。
4. `SER-DELTA-AIRFUEL`：若有 Probox/Fit 精确底盘/发动机/排放及 OEM 零件资料，才新增同车型实际差异；否则继续 `SOURCE_GAP`。
5. 与 `STR-ENG-LUBE`、`STR-LOWV`、`STR-THERMAL` 的共享知识以链接复用，不创建从燃油到润滑的假依赖或循环。

**本次完成边界**：在明确范围内，构成了空气、燃油（PFI/GDI）、点火、ECU、排气/后处理与跨系统接口的结构知识；真正质量资格只有未来异对话内容审核能授予，OEM/N3 资格仍为 0。
