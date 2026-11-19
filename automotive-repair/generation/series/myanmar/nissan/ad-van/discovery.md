# 缅甸在用旧车研究：Nissan AD Van / AD Expert 与 Wingroad 的车型与传动适用性发现（SER-DISC-AD-VAN）

> TASK_ID：`SER-DISC-AD-VAN` · MAIN：[parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) · 唯一输出：本原生 Markdown 文件  
> **R17 缅甸存量车型优先方案**：[MYANMAR_FLEET_PRIORITY_R1.md](../../../../MYANMAR_FLEET_PRIORITY_R1.md)，Blob `9b6c66311da069b28d2b1681bf98b0723e193ea3`；异对话计划独审 [#7013143644](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7013143644) `ACCEPT_SCOPED_MARKET_FIRST_PLAN_READY`；合法 Integrator [C-R17-DISPATCH](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7013561465) `ADMITTED`。  
> **范围及资格**：`MARKET=MYANMAR_USED_VEHICLE_RESEARCH_CANDIDATE`、`MODEL_GENERATED_UNVERIFIED`、`GENERATED_REVIEW_PENDING`。使用缅甸历史二手市场证据与 Nissan 官方特定日本时期产品公告分别建立**待核的本地车型相关性**及**原厂技术家族差异**；不等于任何缅甸车辆的现有原装总成，亦未获得 OEM/VIN/N3 专业事实或维修操作资格。

## 1. 先回答“缅甸 AD Van 为什么值得研究”

缅甸 Myanmar Digital News / GNLM 于 **2022-09-29** 的当地二手汽车市场报道明确提及 `AD VAN`，与 Probox、Succeed、2003 年 Wish 等车型一起出现在当时市场交易讨论中。[原始本地报道](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand)。报道的统计对象是当时市场行情和受访商家说法，**不是**注册车辆普查、抽样分母或 2026 年某车型全国数量。它能支持 `LOCAL_USED_TRADE_VISIBILITY=YES@2022-09-29`，但 `NATIONAL_2026_AD_FLEET_SHARE=UNKNOWN`，`LOCAL_REPAIR_JOB_SHARE=UNKNOWN`。

这里的“AD Van”可能被卖家、修理厂或零配件商宽泛地用于某类 Nissan 商用旅行车。因此需要严分：

| 名称和入口 | 原始来源实际支持 | 技术适用性警告 |
|---|---|---|
| `AD Van` | 缅甸 2022 年本地二手市场历史称呼；Nissan 日本 2006 新品发布前的历史 AD Van 也是真实车型称呼 | 当地一个“AD Van”标题不证明就是 2007 改款 AD/AD Expert，也不证明车架、引擎或变速器 |
| `AD`（2006 年 12 月发布、2007 年 1 月起日本上市） | [Nissan 2006 英文原厂发布](https://global.nissannews.com/en/releases/061220-01-e) 确认新一代商用车 AD | 2006 新闻稿针对日本新产品；不能倒填缅甸所有 AD 年款 |
| `AD Expert` | Nissan 同一篇 2006 发布，作为相关但另有定位的型号；[Nissan 资料馆](https://global.nissannews.com/ja-JP/heritage_model_ad_expert)有 `VY12` 历史标签 | 名称相关不等于零件互换。`VY12` 仅是厂商历史车型示例，不是缅甸卖家车架已核实 |
| `Wingroad` | [Nissan 2005 原厂 Wingroad 产品公告](https://global.nissannews.com/en/releases/051114-01-e)为另一款乘用旅行车，分别公布 HR15DE/MR18DE 与相关变速器信息 | 与 AD/AD Expert 在平台、发动机或零件上可能存在重叠，但**不能把 Wingroad 作为 AD Van 的一款通用“高级配置”**；另设相邻车型来源与适用性记录 |

**实际车型唯一识别**还须车辆证件/合法车架记录、地区和出厂日期、可验证车架/引擎/变速器标识与对应 Nissan 原厂车型目录；本文完全没有对任何缅甸 VIN/Frame 开展核验。

## 2. 按时间和配置分支建立 Nissan 原厂事实矩阵

| Nissan 原厂技术切片 / 日期 | 官方可复核配置事实 | 维修知识首先应分开的分支 | 缅甸使用范围 |
|---|---|---|---|
| **2005-11-14 Wingroad 日本新车型** | Wingroad 官方发布 `HR15DE` / `MR18DE` 发动机家族；在所列 1.8L `MR18DE` 版本中描述与 CVT 组合，以及该车型前麦弗逊支柱和后扭转梁结构 | 是**乘用 Wingroad** 的车型事实；CVT 不能迁移成所有 AD Van 的变速器类型 | `MYANMAR_VIN_MATCH=UNKNOWN`，不得用作 AD Van 发动机/后悬架的正式适配清单 |
| **2006-12-20 AD / AD Expert 日本新品** | [原厂英文公告](https://global.nissannews.com/en/releases/061220-01-e)：`HR15DE` 和 `MR18DE` 为新产品发动机；旧 4WD 产品线保持一段过渡，旧 1.5L 手动车/CNG 构型继续供应 | 车型上市不是所有旧/新子型号同时完成替代；不能将 2006 一篇新品新闻稿推出全车系固定为 CVT | 具体过渡车架、出厂时点、传动类型和 JDM/进口差异为 `UNKNOWN` |
| **2012-05 AD/Expert 日本局部变更** | [Nissan 2012 官方公告](https://global.nissannews.com/ja-JP/releases/120510-01-j) 展示 4WD `HR16DE` 和 `E-ATx` 的适用分支 | 表明**驱动形式与发动机**可能同时改变变速器类别；即使外观类似也不得用单一油液、齿比/故障树覆盖全部 AD | 日本公告不证明某缅甸挂牌必为 4WD/HR16DE |
| **2013-05-20 AD / AD Expert 日本局部改良** | [Nissan 2013 原厂日文配置表](https://global.nissannews.com/ja-JP/releases/130520-01-j)：**1.5L 2WD HR15DE** 采用 Xtronic CVT；**2WD MR18DE** 所列型号为 `E-ATx`；**4WD HR16DE** 为 `E-ATx`，该公告解释 `E-ATx` 为电子控制四速 AT | 出现同一时期车系的**机械 CVT 与有级 4AT 并存**，是与本地 AD 维修有意义的实质差量。不同引擎/驱动路径必须先分清，再问变速、热、油液、控制和零件 | **仅按该原厂日本公告的行/日期成立**。不能说所有 2013 AD、所有 1.8L Wingroad 或任意缅甸车都 CVT/4AT |
| **2016-01 AD/Expert 日本法规/价格更新** | [Nissan 2016 原厂公告](https://global.nissannews.com/ja-JP/releases/160118-02-j) 继续在公布配置中出现 CVT 与 E-ATx 分支 | 再确认“某年起统一 CVT”是错误概括；需要车型代码/装配/驱动条件 | 对实际进口缅甸旧车依然 `UNKNOWN` |

这些是生产方产品公告的“某年份、某日本市场发布、某配置行”事实，不代表车辆事故、故障率、OEM 维修手册或任何跨车型通用的零件匹配结论。

## 3. 结构/正常机理如何直接改变诊断知识选择

### 3.1 传统 `E-ATx 4AT` 与 Xtronic `CVT` 不是同一传动机构

若以 2013 日本 AD 产品公告为例：

- **`HR15DE 2WD / CVT`**：应关联已审机械 CVT 家族（变比、液压夹紧、输入输出速度、控制许可、热态与传动效率的不同来源），而**不是**用 1–4 档固定传动比、行星离合/制动元件表直接解释所有变速过程。CVT 具体带、链、起步机构、变速箱型式和匹配油品在本车系没有逐总成 OEM 图纸，`UNKNOWN`。
- **`MR18DE 2WD 或 HR16DE 4WD / E-ATx 4AT`**：2013 日本公告说明该行是**电子控制四速有级 AT**。可以有限复用[传统行星液力 AT 的结构/工作知识](../../../../topics/transmission/automatic/structure.md)，但必须按确切变速器总成证明其内部机理，不能从 `E-ATx` 标签推断全部阀体、变矩器、档位离合器接合表和油液。
- **手动及历史 4WD 分支**：2006 新品公告明确旧手动/四驱方案有过渡时期，不得只按某年份/广告题头判定“只有自动 CVT”。手动离合/同步器诊断是另一家族；驱动轴、差速器及后桥的受载/异响判断也须看实装驱动形式。

**直接结论**：如果维修接待凭“AD Van 自动挡”就先生成“CVT 油压不足”或“4AT 电磁阀失效”的具体维修知识，都是在没有确认架构前的错误因果选择。

### 3.2 Wingroad 的特殊位置

Wingroad 的 2005 Nissan 官方文章确证 `MR18DE+CVT` 的乘用版本和前支柱/后扭转梁配置。它可以用于发现**同日产发动机家族不等于相同变速箱家族**的反例：在 2013 AD Expert `MR18DE` 日本型号中公布的是 `E-ATx`。因此：

- 同一个发动机名称不能证明同一变速器、后桥或 ECM/TCM 控制逻辑。
- 即使同一 OEM 家族、类似轮廓、部分零件号码相似，也不能未经原始 EPC/车架适用信息断言零件互换。
- 车型发现阶段仅保留 `WINGROAD_AD_OVERLAP=UNVERIFIED`、`PARTS_INTERCHANGE=UNKNOWN`，避免“Wingroad=AD Van”的车型污染。

## 4. 下一轮真正有维修价值的知识缺口

| 核实后可以做的后继任务 | 当前必须确认什么 | 为什么会改变维修诊断 |
|---|---|---|
| `SER-DELTA-AD-TRANS`（建议，尚未准入） | 缅甸实际 AD 车架/制造日期/驱动、CVT vs E-ATx vs MT、Nissan 匹配资料 | 区分变比/液压夹紧、AT 固定档位选择、手动离合/同步器、温度/信号与误修风险；**绝不**借通用车型名发布油液和拆装工序 |
| `SER-DELTA-AD-ENG`（建议，尚未准入） | HR15DE/HR16DE/MR18DE/历史 CR12DE 具体装车、地区排放与原始维修/零件资料 | 避免将某台日产发动机的燃油、正时、冷却、传感系统当全部 AD 的原厂配置 |
| `SER-DELTA-AD-DRIVELINE`（建议，尚未准入） | 2WD/4WD 类型、传动轴/后桥实际构成和车架来源 | 轴端/差速与轮胎附着、振动、载荷噪声不同，不能将前驱半轴处理规则套给所有 4WD |
| `SER-DELTA-AD-LOAD-SUSP`（建议，尚未准入） | 货车/旅行车身份、实装弹簧/阻尼/后桥、长期负载使用证据 | 业务车可能有载荷/热/磨损问题，但没有工单/实车不得声明 AD“高故障率”或任意换悬架部件 |
| `SER-WINGROAD-IDENTITY`（建议，尚未准入） | 独立的缅甸本地 Wingroad 交易证据、型号/车架与 Nissan 产品目录 | 如果当地常见，另立车系研究而不是直接把 Wingroad 知识塞进 AD Van 的原厂事实 |

后继 Task 仅是候选，不自动占用写集，不以“每车型都生成五篇”作为成功指标。真正有来源的未回答差异才请求增量计划审核，避免在工程上无止境生成技术目录。

## 5. 概念性证据链与反例（非施工）

1. **输入**：经合法来源获得的缅甸车辆车型、车架/制造年、驱动形式及接待主诉；卖家信息含糊则记 `UNKNOWN`。
2. **区分**：本地市场材料只确认 AD 作为研究候选；日本 Nissan 发布只确认原产地特定年份的技术选项。二者不能直接相乘构成实车技术资格。
3. **适用性分叉**：具体车辆若证实 HR15DE/2WD/Xtronic CVT，后续应按该变速器版本研究；若 HR16DE/4WD/E-ATx，走相应有级 AT 与四驱支路；若传统手动等，另走 MT 分支。**不能仅凭发动机名称或广告里的 Auto 断言箱型**。
4. **竞争问题**：同样“起步无动力”，可能与发动机输出、供油/点火、CVT/AT/MT 执行、差速/半轴、轮胎抓地、低压电气/控制授权等多系统相关；本系列发现不确定任何真实故障。
5. **终止条件**：没有实际车架/制造期或匹配原厂装配证据时，停在 `MODEL_SERIES_CANDIDATE` 与 `UNKNOWN`；不给具体油液标号、容量、油压、扭矩、拆装/路试或继续驾驶许可。涉及严重失速、制动/转向风险时转交专业人员。

## 6. 证据与权限账本（按来源时间、地域分开）

| 文献或数据源 | `evidence_type` / 日期 / 地区 | 可合法支撑什么 | 仍明确未知 |
|---|---|---|---|
| [Myanmar Digital News 二手车报道](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand) | `MYANMAR_LOCAL_USED_TRADE` / 2022-09-29 / Myanmar | 当地 AD Van 历史交易相关性 | `ON_ROAD_RANK_2026`、保有量分母、确切车架/故障频率 |
| [Nissan AD/AD Expert 2006 日本官方发布](https://global.nissannews.com/en/releases/061220-01-e) | `OEM_JAPAN_PRODUCT_RELEASE` / 2006-12-20 / Japan | AD/Expert 新车系、HR15DE/MR18DE 与旧 4WD/MT 过渡 | 某缅甸 AD VIN 属于哪一发布配置 |
| [Nissan AD/AD Expert 2012 日本局部更新](https://global.nissannews.com/ja-JP/releases/120510-01-j) | `OEM_JAPAN_PRODUCT_RELEASE` / 2012-05-10 / Japan | 特定 4WD HR16DE / E-ATx 表格存在 | 2012 缅甸车架精确码、是否为该等级 |
| [Nissan AD/AD Expert 2013 日本配置行](https://global.nissannews.com/ja-JP/releases/130520-01-j) | `OEM_JAPAN_GRADE_TABLE` / 2013-05-20 / Japan | 1.5L 2WD HR15DE/CVT、2WD MR18DE/E-ATx、4WD HR16DE/E-ATx 不同分支 | 某实车制造日、总成代码、原厂 CVTF/ATF、零件适配 |
| [Nissan 2016 AD/Expert 更新](https://global.nissannews.com/ja-JP/releases/160118-02-j) | `OEM_JAPAN_GRADE_TABLE` / 2016-01-18 / Japan | 后期仍不能将 AD 全部归纳为 CVT | 缅甸同期样本是否与 2016 日本表相符 |
| [Nissan 2005 Wingroad 发布](https://global.nissannews.com/en/releases/051114-01-e) | `OEM_JAPAN_SEPARATE_MODEL_RELEASE` / 2005-11-14 / Japan | Wingroad 是独立车型、部分 MR18DE+CVT 与底盘结构 | Wingroad/AD 零件互换及缅甸适用车架 |

`model_family=AD_VAN|AD|AD_EXPERT|WINGROAD_DISTINCT`，`generation_chassis=UNKNOWN_FOR_ANY_MYANMAR_VEHICLE`，`production_period=UNKNOWN_LOCAL`，`engine=UNKNOWN_LOCAL`，`transmission=UNKNOWN_LOCAL`，`source_version=2005_2006_2012_2013_2016_OEM_JP_RELEASE`，`market_evidence=MYANMAR_USED_2022_NOT_CENSUS`，`SCOPE=MODEL_GENERATED_UNVERIFIED`。

**生成完成≠质量审查完成**。后续另一个非本 Writer 对话必须用当前文件 Exact Git Blob、原始来源和明确适用边界写回 `ACCEPT_SCOPED_GENERATION_ONLY` 或 `REWORK`、P0/P1/P2；不得将其解读为 OEM 实车修复资格或缅甸国家车型统计证明。
