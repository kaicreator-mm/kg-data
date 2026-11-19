# R20 · Toyota Probox / Succeed 缅甸在用车型优先维修知识 Task DAG 增量

> MAIN：[parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) · 数据仓：`kaicreator-mm/kg-data` · `OUTPUT_LABEL=PARTS_AUTOREPAIR_R20_PROBOX_FLEET_FIRST_INCREMENTAL_DAG_PROPOSAL`。  
> **状态：`PROPOSED__INDEPENDENT_PLAN_REVIEW_PENDING`。R20 的三个新叶全部尚未准入、未生成、不得自动派发。** 既有已接受的 Probox 车型与变速器知识无需重复生成或复审。第一阶段只产生 Markdown，`OEM/VIN/N3=0`。

## 1. 本次 Owner 执行方向：把 Probox 置于缅甸车型优先队列首位

[缅甸 Myanmar Digital News / GNLM 2022-09-29 历史二手车报道](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand)明确列出 Probox 和 Succeed 等市场交易车型；本仓已审的 [Probox Discovery](./series/myanmar/toyota/probox/discovery.md)亦记录本地挂牌与个别行政来源。该证据支持**维修知识优先候选**，不证明 Probox 在 2026 年全国保有量排名第一，也不证明所有在缅甸上路的 Probox 都属于某一种动力或车架。`MYANMAR_2026_MODEL_STOCK_RANK=UNKNOWN`，`LOCAL_REPAIR_FAILURE_FREQUENCY=UNKNOWN`。

**调度意义：** 在新车系 Nissan AD Van、Toyota Vitz、Suzuki Swift、Toyota Wish 已生成 Discovery 并独立审核时，绝不能遗漏早已正式纳入首批的 **Toyota Probox / Toyota Succeed**。今后优先做 Probox 的**真实装配差异及维修机理**，而非重新做一次介绍或追加通用 BEV 知识。Probox 与 Succeed 使用两个车型名称及独立配置适用性记录，不假定全部互换。

## 2. 已完成成果直接复用（不加 DAG 节点）

| 原已准入任务 | 当前真实内容及 Exact Blob | 当前资格 | 后继如何用 |
|---|---|---|---|
| `SER-DISC-PROBOX` | [车型发现](./series/myanmar/toyota/probox/discovery.md) `c8f011229a4e6fa6c66ae092a6f19a21142b4f19` | [独审 ACCEPT_SCOPED_GENERATION_ONLY](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6962402777) | 已有本地市场、2002/2014 结构和车型来源，后继只写差异 |
| `SER-DELTA-PROBOX-TRANS` | [变速箱差量](./series/myanmar/toyota/probox/transmission-applicability-delta.md) `2a0bfda60bc63ea484c45a6c0b01fe31f7db51a0` | [独审 ACCEPT_SCOPED_GENERATION_ONLY](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6976215650) | 已分早期 4AT/5MT 与 2014 日本 Super CVT-i；不可复制为新稿 |
| `SER-DELTA-PROBOX-LUBE` | [已接受旧 SERIES DAG](./VEHICLE_SERIES_DAG_R1.md)，**现不存在正文**：`series/myanmar/toyota/probox/engine-lubrication-delta.md` | `ALREADY_IN_BASE_DAG__CONDITIONAL_SOURCE_GAP`，不是 R20 新节点 | 对已证实具体发动机版本**且有可核对的油路硬件差异**时才动笔；目前不能把发动机名称更替冒充油泵/油压/滤芯已证实差异 |
| 通用共用机理 | 已接受的 [汽油机燃油/进气结构](./topics/engine/air-fuel-emissions/structure.md)、[润滑结构](./topics/engine/lubrication/structure.md)、[制动结构](./topics/braking/structure.md)、[转向悬架结构](./topics/steering-suspension/structure.md)、[低压电气结构](./topics/electrical-low-voltage/structure.md) | 已审范围内可复用 | 不为每一个 Probox 年款复制全套系统技术 |

新 Probox R20 提案产生前 **正式有效 DAG 是 58 个节点**：基础 54 + R17 四个车系发现；`SER-DISC-PROBOX` 和 `SER-DELTA-PROBOX-TRANS` 已在基础图内。不能因“加入 Probox”再计入一个重复车系 Discovery 节点。

## 3. Toyota 一手来源指向真正的发动机与传动差异

| 有原始 Toyota 来源的时期 | 可证实的技术家族差异 | 对缅甸维修知识的有效结论 |
|---|---|---|
| [Toyota 75 年历史·Probox](https://www.toyota-global.com/company/history_of_toyota/75years/vehicle_lineage/car/id60012554A/index.html) / [Succeed](https://www.toyota-global.com/company/history_of_toyota/75years/vehicle_lineage/car/id60006139B/index.html)，2002 家族 | 有 `2NZ-FE 1.3L`、`1NZ-FE 1.5L` 汽油机及 `1ND-TV 1.4L` 共轨柴油家族；4AT/5MT 等以及 2WD/部分 4WD | 不能把柴油机燃油/涡轮/润滑问题套给汽油 Probox；也不能从商用“Probox”名称推断具体实装 |
| [Toyota 2008 Probox/Succeed 部分改款](https://global.toyota/en/detail/1641086) | 厂商日本版本表按车型、配置、发动机及驱动形式分列（部分 2NZ-FE/1NZ-FE、4AT/5MT） | 旧车车架/制造期可决定后续诊断体系，不能仅看登记年份推断全部配置 |
| [Toyota 2014-08-06 改款官方发布](https://global.toyota/en/detail/3737378) | 指定 **Probox 1.3L 1NR-FE**、**1.5L 1NZ-FE** 与 `Super CVT-i`；官方称其为 `minor change`，不等于所有市场和全部车架被彻底换代 | 发动机类别、CVT/AT/MT、不同年款的控制和维修风险是实质差量；未验证缅甸车架就不能写具体零件/油液/油压 |
| [Toyota 2016 一部改良](https://global.toyota/en/detail/13332599) | 在相关日本公布配置中继续存在 1NR-FE/1NZ-FE、2WD 等组合 | 2014 后仍须按实际车架和版本识别，不能保证所有 Succeed 与 Probox 完全一致 |

以上均是日本国内版本公告/产品历史，**不是缅甸车架清单、维修工单、真实 VIN 适配或失效频次**。若没有匹配的生产年月、车辆身份与来源版本，标记 `MYANMAR_CHASSIS_AND_FITMENT=UNKNOWN`。

## 4. R20 三条新叶任务：已有直接上游、互不依赖

三条新任务仅在独立增量计划审查通过并由独立 Integrator 写回 `C-R20-PROBOX-DISPATCH=ADMITTED` 后才能 Writer Claim。它们可以**同时执行**，但均不得先于真实证据；缺少实质资料的任务允许输出阻塞/取消而非凑数文章。

| R20 候选新 Task | 唯一 Markdown 写集（相对本目录） | 直接硬依赖与具体问题 | 证据/完成标准 |
|---|---|---|---|
| `SER-DELTA-PROBOX-ENGINE` | `series/myanmar/toyota/probox/engine-generation-variants.md` | `SER-DISC-PROBOX` + 已审 `STR-ENG-AIRFUEL`；明确 2002 日本 2NZ/1NZ 汽油、1ND 柴油与 2014 1NR/1NZ 的装车条件、燃油/进排气/点火或柴油共轨类别差异 | 来源分日本年份/型号，实证确有发动机类别差异；解释错误跨型诊断的原因与反例。不能编造同 VIN 装配及具体维修数据 |
| `SER-DELTA-PROBOX-BRK-SUSP` | `series/myanmar/toyota/probox/braking-suspension-variants.md` | `SER-DISC-PROBOX` + 已审 `STR-BRK`/`STR-STEER-SUSP`；研究 van/wagon、FF/4WD 与 Probox/Succeed 实车配置可能影响的制动助力/ABS/轮胎载荷、悬架/转向差异 | 必须从对应 Toyota 年款配置表证明实际硬件/等级差异后才写结论；仅有通用制动或悬架知识时 `NO_MATERIAL_DELTA_YET` |
| `SER-DELTA-PROBOX-LOWV-HVAC` | `series/myanmar/toyota/probox/low-voltage-hvac-variants.md` | `SER-DISC-PROBOX` + 已审 `STR-LOWV`/`STR-THERMAL`；旧 Probox 常见的起动/充电、空调/散热/风机控制与年款/发动机选配差异 | 若无可信车型电路/装备资料，`BLOCKED_OEM_CONFIGURATION_EVIDENCE`，不为补量复制一篇低压或空调通用说明 |

**R20 计划含三个新增节点，不包含既有 `SER-DELTA-PROBOX-LUBE`；若仅这三个新节点获合法准入，有效 DAG 才从 `58→61`。** 若原图或上游已变，按当前真实状态做增量差分；不重审未变更的 58 节点。

## 5. 可并行的已准入 Probox 润滑条件任务（不加新节点）

`SER-DELTA-PROBOX-LUBE` 早已在已接受的 `VEHICLE_SERIES_DAG_R1.md` 里，目标写集 `series/myanmar/toyota/probox/engine-lubrication-delta.md` 尚空，不需要为此再开一条相同新 Task。它的 **`CONDITIONAL`** 启动条件是：

1. 有证据将目标 Probox 发动机家族限定至具体 Toyota 原厂资料的年份、市场与装配配置；不能以一条卖家“1.5 Auto”确定。
2. 能找到**真正的油路/滤清/泵/油冷或润滑接口区别**，而不是仅能证实 1NZ、2NZ、1NR、1ND 名称不同。
3. 不使用通用油压值、粘度/容量、保养间隔替代 OEM 专属技术文件，不产出危险拆装/压测步骤；柴油与汽油分账。
4. 符合时可沿已批准图独立 Claim+生成 Markdown→Commit/Blob/RELEASE→其它对话审；不符合时在 #61 写 `NO_MATERIAL_DELTA_YET`，不生成假差量。

已有 [通用润滑故障鉴别](./topics/engine/lubrication/diagnostic-repair.md) 可作为条件研究参考，不能在没有车架和真正差异时整体复制入 Probox 文件。

## 6. 新图的方向、并行和质量出口

\`\`\`text
缅甸本地 Probox/Succeed 历史交易/挂牌候选
  └─ 已审 SER-DISC-PROBOX 〔复用，不再新建〕
      ├─ 已审 SER-DELTA-PROBOX-TRANS 〔复用，不重复审核〕
      ├─ 原已准入 SER-DELTA-PROBOX-LUBE [CONDITIONAL, Source Gap]
      ├─ R20 SER-DELTA-PROBOX-ENGINE [PROPOSED] ─→ 审核后条件化车型知识
      ├─ R20 SER-DELTA-PROBOX-BRK-SUSP [PROPOSED] ─→ 审核后条件化车型知识
      └─ R20 SER-DELTA-PROBOX-LOWV-HVAC [PROPOSED] ─→ 审核后条件化车型知识

当前已准入的其它 4 个车系发现，彼此和 Probox 的新叶
不加人为全局 AND 门禁；只各自检查真实上游/来源/写集。
\`\`\`

- **独立计划审**：由非本 Proposal 作者对话读取本文件当前 Exact Git Blob、旧 58 DAG 与 Probox 已审 2 篇、Toyota 原始产品资料；审核新 Task 写集无冲突、依赖无环、当地存量价值、具体机理差异与伪装备风险；给 `ACCEPT_SCOPED_PROBOX_DELTA_PLAN_READY` 或 `REWORK`、P0/P1/P2。**不得自行生成三个新任务。**
- **Integrator 准入**：只有真实计划独审通过且当前 Probox 上游、目标写集/Claims 均有效时，逐 Task 写回 `C-R20-PROBOX-DISPATCH=ADMITTED`；若三者全准入则 `58→61`，若仅部分符合就只计已实际准入数。
- **每个 Writer**：Claim/二次仲裁、独占 Markdown、来源、实际价值、技术机理、竞争解释和反例、UNKNOWN、提交后 Exact Blob 与 RELEASE；审核由另一对话完成。任何 P0/P1 只最小修复当前任务，不重审 Probox 已接受的历史。
- **职业安全边界**：严重制动、转向、机械损伤或高温风险需停止使用和专业移交；不提供通用制动放气、举升、接触高温/旋转件、柴油高压燃油处置、危险路试或电气短接操作。
- **非准入项目**：不增加通用 BEV/充电/高压技术分支，不因全球产品存在就优先调度。Succeed 要有单独车型与实装支持才做差量；不默认 Probox/Succeed 任何部件互换。

**生成数量不是维修知识完整性**：Probox 下一批是否完成，取决于被证实的本地车型变化和能够真正回答故障鉴别/维修问题的知识，不能以三篇文件占满表格视为专业覆盖完成。
