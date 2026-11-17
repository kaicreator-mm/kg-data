# Toyota Probox / Succeed：跨产品时期的传动结构适用性差量 — R1

> TASK_ID: `SER-DELTA-PROBOX-TRANS` · 研究轴：`L3 MODEL_SERIES + L2 TRANSMISSION_FAMILY` · 市场：`MYANMAR_USED_FLEET_CANDIDATE` · 来源技术版本：**2002 Toyota 日本车型家族 / 2014 Toyota 日本市场改款**  
> 直接前置：[`SER-DISC-PROBOX`](./discovery.md) 当前 Blob `c8f011229a4e6fa6c66ae092a6f19a21142b4f19`（[独立生成质量接受](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6962402777)）  
> 对照基础：[`STR-AT`](../../../../topics/transmission/automatic/structure.md) Blob `ed2b997ca164d98e74cf72ecb393aca86a553d20`，**只在被证实的传统液力行星齿轮 AT 范围内适用；不是 CVT/MT 的真实技术硬前置**。  
> 本稿状态：`GENERATED_REVIEW_PENDING / MODEL_GENERATED_UNVERIFIED`。不是缅甸某一实车的变速器识别、维修程序或 OEM 事实认证。  
> **研究问题**：Toyota 同一 Probox/Succeed 相关车系为什么不可用一套自动变速器原理和诊断推断覆盖不同生产时期？哪些厂商来源证实了差异，哪些配置仍未判定？

## 1. 先澄清被比较的两个“官方产品范围”

| 官方来源切片 | 来源原文确证的信息 | 技术分界 | 限制 |
|---|---|---|---|
| Toyota 2002 首次推出的相关产品家族 | Probox 与 Succeed 均有商用 van 和乘用 wagon 变型；发动机家族包含 2NZ-FE/1NZ-FE 及早期 1ND-TV 等；原厂历史明确写有 **4 速自动变速箱或 5 速手动变速箱**，并存在 1.5L 4WD 分支 | 至少存在“有级 AT / 机械 MT”的不同传动机械家族；不能只因都是 Probox 就假设任意车辆为 AT | 该叙述是**日本历史产品线整体**，并未列每个缅甸挂牌所对应的 gearbox code、制造年月、是否发生换装 |
| Toyota 2014-08-06 日本市场的 Probox/Succeed 改款 | Toyota 发布新闻显示新采用的 1NR-FE 1.3L（**仅部分 Probox**）、1NZ-FE 1.5L 与 **Super CVT-i** 的产品结合，列出驱动/型号/价格不同组合 | 相比 2002 公开家族的 4AT/5MT，在该 2014 日本版产品公告切片中存在**无级变速 CVT 家族**；其变比原理与传统固定挡位行星 AT 不同 | 这不是“2014 以前全球所有 Probox 一定无 CVT/2014 以后所有市场所有车型都 CVT”的普遍结论；地区/配置/生产时点仍需匹配 |

**原厂锚点**：[Toyota 75 年史：Probox 2002 首发家族](https://www.toyota-global.com/company/history_of_toyota/75years/vehicle_lineage/car/id60012554A/index.html)、[Toyota 75 年史：Succeed 2002 首发家族](https://www.toyota-global.com/company/history_of_toyota/75years/vehicle_lineage/car/id60006139B/index.html)、[Toyota 2014-08-06 Probox/Succeed 改款公告](https://global.toyota/en/detail/3737378)。

不要把**一次改款公告**冒充完全独立平台代次证明。Toyota 2014 文件使用“minor change”的官方语义，本稿将其记录为“2014 技术/配置变更窗口”，而不凭空宣称车架平台必然换代。

## 2. 适用性矩阵：车型代码只能按可见 OEM 资料逐行绑定

| 车型/架构代码或分支 | Toyota 原始可见支持 | 确定范围 | 未知项与禁止推广 |
|---|---|---|---|
| `UA-NCP58G-EWMLK`（Probox wagon 代表 2WD） | Toyota 75 年史 Probox 表格记为 2WD、1.5L `1NZ-FE`、其代表车型代码 `NCP58G` | **特定历史页面代表 grade**，证明 Probox wagon 1.5L 前驱实存 | 该页面未用此行独立证实某个变速器代码，不能把 “NCP58G 全部 4AT” 写成事实 |
| `UA-NCP59G-EWMLK`（Probox wagon 代表 4WD） | 同一 Toyota 原始表格记 4WD、1.5L `1NZ-FE`、`NCP59G` | 证明车型家族至少有与 2WD 并存的四驱配置 | 不等于任意 NCP59G 的变速箱齿比/车型维修方案已验证 |
| `NCP50V / NCP51V / NCP55V / NLP51V` | Probox/Succeed 车型历史与缅甸个别行政样本有部分代码线索，但各型号与传动精确映射**本稿未获得完整对应的原厂表格** | **IDENTIFIER_CANDIDATE**，适合下一轮按车型/车架检索 | **未逐号提供发动机/驱动/传动确定映射**，不能因相似字符串就认定互换或当维修资料索引真值 |
| `2014 Japan 1NR-FE / 1NZ-FE + Super CVT-i` | Toyota 2014 官方配置公告 | 对该已列出的日本改款配置类别可认定是 CVT 家族 | 未匹配缅甸某辆车的实际车架、制造日、ECU 与所装 CVT 型号，全部 `UNKNOWN` |

这张表落实 Probox 独立 Reviewer 的 **P2-01：逐代码/来源映射精度**，同时对不完整的车架代码保持未验证。**有代码不等于证明具体变速箱**。

## 3. 对同样“Automatic”标识，传动结构知识为何不能复用

### 3.1 传统有级 4AT：扭矩流受离合/制动元件选择影响

在**确有传统行星液力 AT 结构的实例**，典型动力链是发动机→液力耦合/锁止元件（依实际配置）→行星机构及其离合器/制动器选择→输出轴/差速器。传动比通常由不同固定结构约束组合产生。油泵与阀体控制不同摩擦执行元件的接合，而不是假设有一个“变速带轮”的连续调速机构。

此处只引用通用 [STR-AT](../../../../topics/transmission/automatic/structure.md) 的**机理类型**。2002 Toyota 历史稿说明家族中有 4AT，尚未直接给出每个型号完整变速器内部零件、控制单元版本、挡位接合表和专用油液；**绝不能从“四速”反推出具体齿轮组/电磁阀/齿比、油压或维修步骤**。

### 3.2 5MT：驾驶者选挡/离合器与机械啮合路径

对 Toyota 2002 历史家族明确存在的**五速手动变速器**，动力路径由离合器和人工选挡/换挡机构形成档位传递，齿轮与同步器工作条件在专业分析上不同于液压控制的 AT 或无级变速 CVT。不能用“ATF 线压不足”解释所有手动车的传动中断，也不能按无级传动的带轮压力逻辑诊断手动同步器磨损。

这里没有匹配任意具体 Toyota 5MT 的齿比、油液、离合器驱动机构或操作步骤；均应做车型/总成版本核实。

### 3.3 Super CVT-i：无级变比技术族的不同问题空间

Toyota 2014 官方将该版本明确命名为 **Super CVT-i / continuously variable transmission**。与传统固定挡位 4AT 相比，CVT 的核心问题空间围绕连续变比、输入/输出端有效半径或等效变比机构、夹持/液压和相应控制（具体实现要看实际 CVT 型号及厂商技术图纸）；不应强行生成“4AT 每挡对应某离合器组合”的统一维修逻辑。

**本稿只把官方名称证实为 CVT 家族**。没有读取对应型号的 Toyota CVT 分解图，因此“此 Probox 必有某种带/链规格、某种变矩器结构、专用轴承或一套油压控制参数”均为 `UNKNOWN`。某些 CVT 也可能存在液力变矩器，**是否有变矩器不能当作传统行星 AT 的充分条件**。

## 4. 维修诊断知识真正受影响之处

| 客户可见现象（只是输入，不是车型故障率） | 可能关联的传动机理空间 | 若错把家族当同一型号的假阳性 | 正确的知识分支条件 |
|---|---|---|---|
| 加速时发动机转速与车速关系异常 | 4AT：有级换挡、锁止/执行摩擦元件；CVT：目标变比与实际变比；MT：离合器/所选档位 | 用“四速升挡电磁阀故障”解释一辆实际 CVT，或用 CVT 带轮推论解释 MT | **先确定实车传动家族和型式**，再研究该家族的正常现象/反例 |
| 起步时无驱动力 / 间歇中断 | 可能是发动机扭矩、离合/AT 液压/CVT 传力/驱动桥多个竞争路径 | “只有变速器油泵损坏”或“必然 CVT 打滑”均缺证据 | 必须保留跨发动机、传动、轮端、控制的竞争解释 |
| 液温上升 / 拖曳能力与热负荷 | 所有传动家族有热负载，但散热油路/传力摩擦机制不同 | 用一个 ATF 油温阈值/油液标号覆盖 4AT、MT 和 CVT | 需实际 gearbox code、OEM 适用技术资料、工况，缺则 UNKNOWN |
| 仪表或通用 OBD 代码提示传动控制 | 不同家族的 TCM、传感器、线束及故障监测策略不同 | 通用 DTC 描述直接等于部件损坏，或把某软件更新视作全部 Probox 通病 | 来源/年款/TCM 版本绑定；目前不提供具体 DTC 诊断 |
| 车型登记或卖家写 `Automatic` | 只是销售/行政标签，可能包含不同型式自动传动 | 根据广告词推断 4AT、CVT 或油液、维护程序 | 先确认车架/生产时间/总成铭牌，**在本知识阶段只列证据条件，不给现场操作** |

这些只是**维修知识分类及避免误判的结构化问题**，并非已通过实车实验、故障模式证明或任何“常见故障发生率”。失效与维修细节仍由后续 `FAIL-*` / `REP-*` 专门 Task（以及对应车型/总成的 OEM 资料）处理。

## 5. 缅甸存量车辆：市场证据与车型事实严格分账

[Probox/Succeed 已生成发现稿](./discovery.md) 和 [缅甸 2022 二手市场报道](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand) 只能证明该车型系列有本地研究价值。2026-11-18 检视的 [CarMM Probox 挂牌](https://car.com.mm/cars/toyota-probox-2011-1113) 标题“2011”与详情自报制造年份“2012”冲突；不能仅凭该挂牌确定 4AT/CVT，更不能用 2014 日本改款直接回填它的变速箱数据。

`MYANMAR_REAL_CHASSIS=UNKNOWN`，`ENGINE_TRANSMISSION_CODE=UNKNOWN`，`MODEL_YEAR_VS_BUILD_DATE=CONFLICTING_SELLER_METADATA`，`SERVICE_MANUAL_VERSION=UNKNOWN`，`ATF/CVTF/GearOil_SPEC=UNKNOWN`，`TCM_SW=UNKNOWN`，`ON_ROAD_STOCK/RATE=UNKNOWN`。

未进行车型登记样本抽样、无车辆分母/工单，**本稿不是“Probox 故障概率”**。

## 6. 差量结论、后续专业任务与 STOP

| 项目 | 结果 |
|---|---|
| `MATERIAL_DIFFERENCE_CONFIRMED_IN_OEM_FAMILY` | **是**：2002 家族有 4AT / 5MT，2014 日本改款公告有 Super CVT-i，二者传动家族与知识机制不同 |
| `APPLICABLE_TO_SPECIFIC_MYANMAR_VEHICLE` | **UNKNOWN**：没有实车车架/制造期与总成代码，不能套给具体挂牌 |
| `REUSE_FROM_GENERIC` | 传统 AT 结构稿只能用于官方或后续资料确认的**传统行星 AT**；其它家族需要独立共享 CVT/MT 机理知识，不是本车系全文重复 |
| `P2_ON_SOURCE_REPLAY` | 当前保留 Toyota 官方稳定 URL、发布时点和缅甸动态挂牌 URL/2026-11-18 访问日；未取得可发布/许可的非个人数据不可变快照，`IMMUTABLE_MARKET_SNAPSHOT=NOT_AVAILABLE` |
| `NEXT_VALUE_TASK` | 只对可信车架/变速器编码或 OEM 版本进行更窄 `SER-CONFIG-PROBOX-TRANS-*` 研究；无来源则 `BLOCKED_SOURCE` |
| `DUPLICATION_STOP` | 继续复制“有级/无级区别”的基本原理到每个 Probox 年款无价值；已在本文完成差量研究范围，下钻应有真实配置证据 |

**本任务的结论是“已生成可复核的系列传动知识差量候选”，不是“已获得缅甸车辆全配置对应关系”。** 后续仍需其他对话对本 Exact Blob 独立审 Markdown 深度、OEM 来源范围、错误泛化、差量与安全边界；即便接受，原始专业事实、车型安全维修操作和 N3/OEM 仍未授予。
