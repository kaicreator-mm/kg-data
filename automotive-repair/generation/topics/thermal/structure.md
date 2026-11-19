# 汽车热管理结构：ICE 冷却、空调与 BEV 电池/电驱热回路 — STR-THERMAL R1

> TASK_ID: STR-THERMAL · MAIN: [parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) · PLAN: [v0.4.1](../../PLAN.md), Blob 1df1f116a9f4e1effc46840aa4ec57be1289b6cf。
>
> 状态：MODEL_GENERATED_UNVERIFIED / GENERATED_REVIEW_PENDING。属于源范围限定的通用结构知识，并非缅甸任一具体 VIN/型号的维修事实。没有核实特定车型制冷剂、冷却液、温度或压力阈值、排气/加注操作、高压电气和制冷剂安全许可，均为 UNKNOWN。只交付 Markdown。

## 1. 四个不能混为一谈的热网络

热管理包含热源、传热介质、换热器、控制状态、热汇；热量经换热或储热转移，不会因控制器命令而自行消失。至少区分：

| 热/控制网络 | 典型实体及接口 | 不可错误等同 |
|---|---|---|
| 液态冷却回路 | 机体水套、电池冷却板、电机/功率电子冷却管路、水泵、阀/节温器、散热器/换热器（按架构） | 不一定全部串联或共用一款冷却液，不是制冷剂循环 |
| 制冷剂循环 | 压缩机、冷凝/气冷器、节流/膨胀装置、蒸发器、可选液冷 chiller、热泵阀（按型号） | 不可以制冷剂压力/换热器与电池冷却液的物理连通混淆 |
| 空气侧 | 风扇、环境进气、乘员舱鼓风机/风道、换热器空气通路 | 冷凝器风扇不等于冷却液泵；空调吹风不证明压缩制冷正常 |
| 电源与控制 | 温度/压力等实际安装的传感器、风扇/泵/压缩机许可、阀位和控制器 | ECU 目标与真实流量/阀位/热量搬运是不同证据 |

实际热回路常有旁通、多个泵、集成阀模块和不同目标温区。仅凭零件清单无法推导车型实际回路、控制状态或维修方法。

## 2. ICE 发动机及舱内暖风：基本结构

典型汽油机产生燃烧及摩擦热，发动机缸体/缸盖向冷却液传热；泵维持适用冷却流，节温器/流路调节改变旁通与散热器分配，散热器与环境空气通过风扇或行驶气流进行热交换。部分车辆从冷却液向暖风芯供热，经过 HVAC 风道向乘员舱送风。

研究级关联为：发动机热源 → 缸体/缸盖换热 → 冷却液泵/调节 → 散热器与外界；在适用配置下另有暖风芯、机油冷却器、进气中冷器等热接口。MAHLE 将发动机散热、增压空气冷却、油冷和客舱暖风区分为多个专业换热部件，不能把它们视为同一种液体管路。

- 泵提供流动能力，阀/节温器影响路径，换热器及空气流决定排热条件；三者是不同的结构职能。
- 皮带机械泵、电子水泵、双泵和主动阀等因车型而异，不能把现代设计倒填旧款 Probox/Fit。
- 发动机停止后暖风余热、怠速时风扇、车速改变散热能力等具有不同条件，不能把某种表现唯一归因于节温器。
- 发动机水温异常可能受负载、真实流量、空气侧、传感器和控制状态影响；本 STR 不产生故障认定。

## 3. BEV 电池、电驱、功率电子与空调的多温区关系

Bosch Mobility 的电驱热管理材料明确将电池、电机和电力电子的控温，与乘员舱舒适需求并列，并指出 BEV 缺少传统内燃机废热。典型架构可能如下，但是否存在相应支路必须按车型：

| 被调温对象 | 可能的热源/热汇 | 结构组成与能量关系 | UNKNOWN |
|---|---|---|---|
| 高压牵引电池 | 充放电损耗、环境温度、电池预调温 | 按车型可能使用冷却板、泵、冷却液回路、散热器、制冷剂-冷却液 chiller、电加热或热泵 | 并非所有电池液冷或采用相同温度窗口 |
| 电驱电机与减速机构 | 铜损/铁损、机械损耗 | 可能液冷、油冷或其它换热结构，连接独立或共享冷却回路 | 未知是否与电池串联、共用泵 |
| 逆变器/车载充电机/DC-DC | 电力电子损耗 | 可能与电驱共用某支路，也可能分开散热 | 不得由 BEV 名称确定安装位置或散热器 |
| 乘员舱 HVAC | 舱内/环境热负荷 | 电动压缩机、制冷剂回路、鼓风机、可选热泵/电阻加热 | 有电动压缩机不等于必有热泵 |
| 集成热管理模块 | 各回路共同的热交换/温区目标 | 部分车型使用多通阀、泵、换热器和控制器进行热量分配 | 供应商的模块设计不等于市场全部车的装配清单 |

制冷剂和冷却液可以隔着换热器壁面交换热量，例如电池 chiller；这不是两种介质在同一管内混合。车辆充电、驾驶及停车预调温有不同许可条件，也不能由通用结构图确定实际高压接触器或带电操作顺序。

## 4. 空调制冷与热泵的边界

在适用的蒸汽压缩制冷循环中，压缩机、冷凝器、膨胀件和蒸发器共同把热量从低温一侧转移至高温一侧。部分 BEV 的热泵可按设计切换热源/热汇，用于客舱供暖、电池预调温或复用余热；另一些 BEV 只有电阻加热和冷气，不存在热泵。美国能源部公开的不同 BEV 低温运行研究便列出热泵＋电阻辅助与仅电阻供暖的不同样本。

不能把“热泵可改善某些工况能耗”写成所有缅甸车辆具有确定的续航百分比；也不能直接提供制冷剂回收、制冷剂高压检修、电动压缩机带电维修等步骤。

## 5. 结构差异如何影响后继功能/失效分析

| 观察 | 候选结构机制 | 反例或未知 |
|---|---|---|
| ICE 发动机温度升高 | 发热负载、泵、节温/旁通、散热器空气侧和控制许可均可能影响 | 有风扇不代表它已经在正确工况起动；无实际诊断证据不能判水泵损坏 |
| 车厢制冷不足 | 制冷剂/压缩机/换热器、舱内风门与风量、传感/控制等多个层次 | 鼓风机运转不代表制冷循环工作 |
| BEV 充电受限并伴温度变化 | 牵引电池、充电功率电子、电池热回路以及控制策略可能耦合 | 不能由限制功率直接推断电池冷却泵损坏 |
| 热后性能不同 | 冷却/润滑介质、换热器、流量、控制限值或其它外部环境变化 | 无 OEM 不提供温度或压力限值 |
| 同平台 ICE/BEV 热系统差异 | ICE 可利用燃烧废热，BEV 的电池/电驱/车厢存在额外热源和电能消耗路径 | HEV 组合方式可能不同，不自动套用 BEV 热泵方案 |

反例：有空调≠有热泵；有电池≠液冷电池；水泵命令≠实际流量；冷凝器≠发动机散热器；有 chiller≠电池与制冷剂直接接触；ICE 暖风≠总是电阻加热；电机/电池两者都发热≠同一温度目标。

## 6. 缅甸市场的严格适用边界

已生成的 [Toyota Probox/Succeed 发现稿](../../series/myanmar/toyota/probox/discovery.md) 和 [Honda Fit 发现稿](../../series/myanmar/honda/fit/discovery.md) 只是型号研究入口。车辆实际制造月、地区、发动机/混动版本、热回路图、电子泵/阀、制冷剂/冷却液、充注量、风扇/压缩机许可和维护历史都没有匹配 OEM 数据，必须 UNKNOWN。不能按车系名称推断“该车空调故障高发”，也不能生成具体换热器或压缩机更换建议。

后继 FUN-THERMAL 与 FAIL/REP-THERMAL 若有价值，须新 DAG 增量规划及异对话审核；当前通用受审 PLAN **没有**批准这几个 Task ID，不得倒填为已生成/READY。

## 7. 原始出版方资料与限定支持范围

- [Bosch Mobility — Thermal management for combustion engines](https://www.bosch-mobility.com/en/solutions/thermal-management/thermal-management-for-combustion-engines/)：发动机热平衡和泵/风扇的抽象关系。
- [Bosch Mobility — Thermal management for hybrid and electric drives](https://www.bosch-mobility.com/en/solutions/thermal-management/thermal-management-for-hybrid-systems-and-electric-drives/)：电池、电驱与热泵等技术模块及适用差异。
- [Bosch — Electric coolant pump PDE](https://www.bosch-mobility.com/en/solutions/thermal-management/electric-coolant-pump-pde/)：部分产品具有电动泵和电池冷却应用。
- [Bosch — Heat pump unit](https://www.bosch-mobility.com/en/solutions/thermal-management/heat-pump-unit/)：部分产品支持电池预调温与车厢调温。
- [MAHLE — Automotive Thermal Management](https://www.mahle-aftermarket.com/ap/en/products/engine-cooling-and-air-conditioning/)：ICE 冷却、油/增压空气/舱内换热以及 BEV 多回路的供应商技术说明。
- [US DOE — Impact of Cold Ambient Temperatures on Electric Vehicles](https://www.energy.gov/sites/default/files/2024-10/Impact_of_Cold_Ambient_Temperature_on_BEV_Performance_v15_TechEditFinal_12Sep2024__0.pdf)：不同 BEV 样本的热泵/电阻加热配置区别，绝非缅甸具体车型标定。

**交付状态**：结构关系、来源、适用边界、可证伪反例及安全 STOP 已形成 Markdown，需不同对话对当前 Exact Blob 独立 Source-First 内容质量审核；专业实车维修资格未授予。
