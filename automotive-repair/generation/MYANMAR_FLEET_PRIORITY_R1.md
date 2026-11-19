# #61 缅甸存量车型优先：证据、车型队列与 Task DAG 调度规则（R17）

> MAIN: [parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) · OUTPUT_LABEL: `PARTS_AUTOREPAIR_R17_MARKET_FIRST_EVIDENCE_AND_REPLAN` · OWNER SCOPE CHANGE [#7010490802](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7010490802)  
> **生效原则：先缅甸真实在用车型相关性，再选择真实装车架构/总成，然后生成结构→功能→失效→证据鉴别→维修知识。不是先按 BEV/HEV 等全球技术目录铺满知识。** 当前仍是 Markdown-only 研究生成；OEM/VIN/N3/实车专业资格均未获得。
>
> 本文件是动态市场调度/新 Task 候选，不修改历史已获独审的基础 `PLAN.md`、车型 Series、Family 或 R9 计划 Blob；**R16 旧增量虽然独立通过图拓扑审核，但在新的 Owner 市场约束下禁止直接 C-R16-DISPATCH 八叶全部准入**。必须先对各叶补车型证据与适用性，优先保留真实必要节点，暂停纯 BEV 扩张。状态事实以 #61 最新评论与 GitHub 当前文件为准。

## 1. 已核证的本地市场线索与数据口径

| 来源/时间 | 支持的有限事实 | 不可据此声称 |
|---|---|---|
| [RTAD → Global New Light of Myanmar，2024-12](https://www.gnlm.com.mm/rtad-records-17600-ev-registrations-by-dec-2024/) | 截至 2024-12-27，约 6,191 辆四轮 EV，另有摩托及三轮 EV；EV 总类别约 17,600 | 不是缅甸 2026 BEV 全国占比，更不是任意车型保有量 |
| [RTAD-linked EV 登记二次汇编，2025-08](https://evsworldwide.com/market-intelligence/myanmar) | 四轮电动车登记约 9,026（包含少量巴士）；分类与时间需保留 | 不把所有类别 27,000 辆 EV 当作乘用 BEV；不证明 BEV 是存量主流 |
| [缅甸中央统计局 / RTAD，2022-06](https://www.csostat.gov.mm/Content/pdf/SMEI/s6.3MA02.htm) | 2022-06 乘用车登记数为 738,604 辆，给出存量规模的历史基线 | 不可拿不同年份与口径算出 2026 EV 精确份额 |
| [Myanmar Digital News / GNLM，当地二手车市场，2022-09](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand) | 交易讨论明确提及 Probox、Succeed、Nissan AD Van、Toyota Wish、Fit、Vitz、Swift、March 等，主要反映当时市场需求与挂牌 | 不代表 2026 全国在用车系按数量排名、故障率或完整车辆变体 |
| [CarMM 当地二手挂牌](https://car.com.mm/en)、[Myanmar 二手市场个体挂牌](https://myanmarkt.com/ads/motors/all) | 可继续发现 Probox、Fit、Toyota/Nissan/Suzuki 旧车及底盘号线索；每辆车需要校验挂牌身份/日期/真实性 | 挂牌不是全国保有量或维修工单，不按单一页面样本量建精确排名 |
| [2026 新车销量行业估计](https://www.focus2move.com/myanmar-vehicles-industry/) | 新车中 BEV/PHEV 可能迅速增长，需持续关注 | **新销量占比、进口占比、全类别 EV 存量**不等于现在所有在用轻型汽车的比例 |

**截至 2026-11-19：没有找到同时覆盖缅甸全国、具体车系、底盘/动力/年款的最新可靠在用车辆排名。** `NATIONAL_2026_ON_ROAD_MODEL_RANK=UNKNOWN`，`TRUE_FAILURE_RATE=UNKNOWN`。现阶段采用可复核的**维修相关候选队列**，不是捏造绝对排名或频率。新线索必须记录来源、发布日期、统计对象（存量/交易/挂牌/进口/新车销售/实际维修工单）、地区与覆盖缺陷。

## 2. 模型优先于通用技术：当前车型队列

| 调度级别 | 缅甸在用候选及来源强度 | 允许优先生成的内容 | 不得默认假设 |
|---|---|---|---|
| **M1 · 先完成已有发现** | **Toyota Probox 与 Succeed 分开识别**、**Honda Fit/Jazz**；2022 市场报道 + 已生成当前系列发现 Markdown | 先基于具体底盘/年份/动力/变速器的配置差异定位结构、总成、控制原理与常见维修问题；复用已审核通用 ICE/AT/CVT、制动、悬架、电气、HVAC | 某一具体 VIN 的 4AT/CVT/MT、IMA/i-DCD/e:HEV、EPS/HPS 或 OEM 维修值 |
| **M1 · 接着并行发现** | **Nissan AD Van / Wingroad**、**Toyota Vitz/Yaris**；2022 市场资料 + 可继续寻找当地挂牌及 Nissan/Toyota 生产方资料 | 核对实际存量代际、底盘代码、汽油或柴油动力、MT/AT/CVT、常用驱动与零件差异，再生成与已有基础知识的局部差量 | 所有 AD Van/Wingroad 同平台或 CVT，所有 Vitz/Yaris 装同一变速箱 |
| **M2 · 市场证据继续补强** | **Suzuki Swift、Nissan March、Toyota Wish**；2022 市场报道明确提到，但全国存量排名未证实 | 并行做市场发现与车型身份验证，适用时补发动机/变速器/悬架/制动/空调差量 | 把少量挂牌误当真实主流全国份额 |
| **M2 · 商用/其他常见候选** | **Toyota Hilux/Hiace、Suzuki Carry、Mitsubishi Canter；Corolla Axio/Fielder、Belta** 等，需本地使用/维修证据补强 | 柴油高压共轨、MT、商用载荷、底盘、转向制动及汽油车共用机理等，按车型实装确认 | 无本地证据就给商用/柴油或其他车型强行分配配额 |
| **M3 · 证据触发** | **Honda Fit 特定 HEV 版本**，仅在真实当地车辆存在、具体架构及维修相关性成立时 | IMA / i-DCD / e:HEV 的既有知识可以**引用并补有限车型差量** | 把三种架构当作所有 Fit 必备；只因技术文章存在就调度所有 HEV 节点 |
| **HOLD · 非默认主线** | **纯 BEV、高压电池/充电/高压诊断专属节点**，尚无足够市场存量或实际维修需求资格支持与上述优先项竞争 | 保留已生成的通用 BEV 知识作研究参考；以后遇到确切缅甸当地车型、规模或真实工单需求，按证据开启局部专项 | 自动扩展 `FAIL-HV→REP-HV`、BMS/预充/OBC/充电每类一个节点，把增长中的新车销量直接当存量维修主需求 |

`M1/M2/M3` 是本项目**调度队列**而非统计比例与原厂车型评级。若新登记、汽修工单或商用车辆证据推翻候选次序，按真实材料更新优先级，不机械冻结车型清单。

## 3. 后续 Task DAG：先以车系作运行入口，再共享机理

```text
当地存量/交易/维修证据 → 车型系列候选 + UNKNOWN
                             │
        ┌────────────────────┼────────────────────────┐
        ▼                    ▼                        ▼
 Probox / Succeed        Honda Fit/Jazz          Nissan AD / Toyota Vitz
 已有 Discovery          已有 Discovery          新 Series Discovery
        │                    │                        │
        └───────────┬────────┴────────────┬───────────┘
                    ▼                     ▼
          底盘-年款-地区-动力-变速器真实架构差异
                    │
                    ▼
             实际装配系统/总成索引
                    │
                    ▼
       复用已有已审通用 STR/FUN/FAIL/REP
                    │
                    ▼
          仅对真实车型差异生成 Markdown 增量
                    │
                    ▼
           诊断价值/证据/误修条件/UNKNOWN
```

共享通用功能只生成一次；不同车型只写**真正差异**，不创建 `每车型×每系统×固定篇数` 矩阵。结构与正常机理先于失效与诊断；对资料缺乏的真实车系先生成候选研究及 UNKNOWN，不为了形式完整冒充 OEM 装配。

## 4. R17 建议四条独立 Series Discovery 任务（均待最小计划审核与准入）

| 候选 ID | 具体文件写集 | 实际回答的问题 |
|---|---|---|
| `SER-DISC-AD-VAN` | `series/myanmar/nissan/ad-van/discovery.md` | Nissan AD Van/Wingroad 不同代际、市场、实际出现的引擎/传动与驱动配置、与旧 AT/CVT 共性差异；先调查在缅甸的证据 |
| `SER-DISC-VITZ` | `series/myanmar/toyota/vitz/discovery.md` | Toyota Vitz/Yaris 旧车在用证据与底盘/引擎/MT/AT/CVT、地域年代差异 |
| `SER-DISC-SWIFT` | `series/myanmar/suzuki/swift/discovery.md` | Swift 在缅甸市场的真实代际及汽油/变速器和底盘差异 |
| `SER-DISC-WISH` | `series/myanmar/toyota/wish/discovery.md` | Wish 常见代际候选、发动机/AT/CVT/驱动构型，不误把某一市场装配认为所有旧车都一样 |

四个候选仅依赖 **本文件的市场证据 + 已有 SERIES Discovery 模板/来源适用规范 + 审核批准的 R17 计划**，彼此无依赖、唯一输出且只有合法 `C-R17-DISPATCH=ADMITTED` 才能开始新 Writer。每篇必须带 `market_evidence`、`evidence_time`、`market_region`、`model_family`、`generation/chassis`、`engine`、`transmission`、`known/unknown`、`publisher_source_version`；将不同证据源的适用边界严格分离。不得预先保证四者都已经达到全国主流阈值。

**后继任务不固定数量**：根据 Discovery 新发现有价值的实装差异再决定 `SER-DELTA`、共享系统功能或具体疑难症状；若信息不足，`BLOCKED_LOCAL_EVIDENCE`，不是填充通用 BEV 知识来替代。

## 5. 对已经批准与正在审核的 R16 八叶做最小改线

- **R16 旧计划保留其拓扑审核收据与原 Exact Blob**，但 Owner 新范围优先级在[最新纠偏评论](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7010490802)已生效。当前不发布全部八叶 `C-R16-DISPATCH`。
- `FUN-ENG-AIRFUEL`、`FAIL-LOWV`、`FAIL-STEER-SUSP`、`FAIL-DRIVELINE`、`FAIL-THERMAL`、`REP-CVT-FAMILY` 属于**可复用**的 ICE/Fit/Probox/AD/Vitz/Swift/Wish 潜在实际总成，需先写明车系/实装差异作为使用范围，再按维修价值并行启用，不必重复已有源/算法审核。
- `FUN-BODY-SAFETY` 也与传统车型有关，但气囊/SRS 子内容保持危险操作禁区；是否排在前列应看缅甸车型实际覆盖缺口。
- `REP-HEV-FAMILY` **HOLD**：先确认本地确实存在具体 Honda Fit HEV 架构以及面向本地的真实维修价值，优先复用旧稿，不再泛化全部 Honda 混动技术。
- `FAIL-HV` 已按旧已准入 DAG 真实生成与独立限定接受，**不撤销、不删除、不重审**；但后续 `REP-HV` 等 BEV 新任务停止自动扩张。共享低压、电气、HVAC、制动等内容仍可优先用于 ICE 主流车系。

## 6. 执行和审核最小约束

1. Integrator 先查最新 #61 Owner 范围与有效 Source，优先调度 M1 / M2 已有本地证据的车型任务，不再把“全球技术广度”当作主优化目标。
2. 只有当本地车型候选证据与实际对应配置成立时，才从已接受的通用机理挑可复用下游；`KNOWN` 与 `UNKNOWN` 分账，事实审核源始终能追踪来源版本。维修频率不靠论坛/挂牌推断。
3. 单独对 R17 四条新节点增量计划做**一次**非 Proposal 作者独立计划审，再由非 Reviewer Integrator 准入；本文件创建本身不是准入，不授权 Writer 自动执行。
4. 旧通用知识审核保持有效；新 Scope 不否认过往独立限定审核，但此后新增内容优先提交**实际主流车型差异与维修价值**。避免重复昂贵 CI/治理、非必要安全审计、虚构 OEM 参数或主动扩展 BEV。

