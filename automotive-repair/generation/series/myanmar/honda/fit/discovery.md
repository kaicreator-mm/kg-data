# 缅甸存量车型系列发现：Honda Fit / Jazz 适用性与传动代际 — R1

> TASK_ID：`SER-DISC-FIT` · MAIN：[parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) · SERIES_PLAN：v0.4.2 R2 Blob `4229bb3913cff46ccb780247d78d5a94bd6dd049` · GATE：`SER-DISPATCH=ADMITTED`  
> **交付类型**：车型系列、代际/传动及维修知识适用条件的原创 Markdown **发现稿**；不是 Honda 任一具体 VIN/车架的 OEM 维修指南。  
> **状态**：`GENERATED_REVIEW_PENDING` · `MODEL_GENERATED_UNVERIFIED` · `FACT_QUALIFICATION=NONE`。  
> **applicability_level**：`L3 MODEL_SERIES_GENERATION`（仅按原厂公开发布的日本版技术阶段）；`L4 MYANMAR_SPECIFIC_CONFIGURATION=UNKNOWN`。  
> **source_visibility**：`HONDA_OFFICIAL_BODY_VIEWED` + `MYANMAR_USED_LISTING_VIEWED` + `MYANMAR_PUBLIC_MARKET_REPORT_VIEWED`。无逐车 VIN、无 OEM 具体维修手册、无缅甸车型保有量统计。  
> **本轮来源检查**：2026-11-18；挂牌内容会变化，不据其直接确认实际车辆技术身份。

## 1. 本任务目标：车系名称相同，不等于总成和维修知识通用

缅甸在售旧 Honda Fit 的“Automatic”标记不足以确定它采用 CVT、传统 AT 或混动 DCT。车系经历了多代技术变化；只有**实际制造期、车架/发动机/变速箱/驱动类型及地区**匹配后，才可能判断某条结构/诊断/维修知识是否适用。

本次发现必须同时回答：
1. 缅甸本地是否有理由把 Fit 纳入**存量车型维修知识研究**？
2. Honda 官方真实发布的不同 Fit 版本，哪些差异足以阻止用“同一变速器/同一混动系统”解释全部车辆？
3. 当前缺少什么信息使具体车型故障诊断不能建立确定专业 Claim？

**Fit / Jazz 的品牌名称关系**：在不同地区存在不同市场名称使用，但**不能把任一地区的 Jazz 年款、动力总成或法规配置直接抄给缅甸当地挂牌的 Fit**。本稿不将 `JAZZ` 当作已证明相同 VIN 适用范围的别名。

## 2. 缅甸本地的实质但有限的市场证据

| 证据 | 当地公开页面和检视日期 | 该证据允许的判断 | 明确禁止的推断 |
|---|---|---|---|
| MMR-FIT-01 | [CarMM — Honda fit gd1](https://car.com.mm/cars/honda-fit-gd1)，2026-11-18。自报 2007 年、汽油、Automatic、Yangon，并用 “gd1” 作标题 | 当前公开平台有以 Fit GD1 识别的单条**在售**样本，可选择作第一代研究入口 | `GD1` 仅来自卖家标题，未实查车架；`Automatic` 不能证明变速器具体代号或维修油液 |
| MMR-FIT-02 | [CarMM — Honda ge6](https://car.com.mm/cars/honda-ge6)，2026-11-18。自报 2008 年/汽油/Automatic，标题含 “ge6” | 当前平台还有不同于 GD1 的第二种 Fit 车系代次线索 | 卖家标题 `GE6` 不是 OEM 车架认证；年份、选配和变速箱型式均须另行确认 |
| MMR-FIT-03 | [Myanmar Digital News / GNLM 2022-09-29 二手车报道](https://mdn.gov.mm/en/automobile-market-sees-weaker-demand) 当时列有 2008 Honda Fit 等旧车交易价格 | 证明 **2022 年二手车市场曾讨论 Fit**，对缅甸维修研究有相关性 | 不是 2026 全缅甸在用保有量普查、各代份额或真实维修工单统计 |
| MMR-FIT-04 | 2014 年的 [The Irrawaddy 市场报道](https://www.irrawaddy.com/business/car-market-expands-japanese-models-rule.html) 点名日本小型车市场偏好 | 只能支持历史市场背景 | 不能把旧报道直接当当前维修常见故障或排名 |

**质量陷阱：挂牌页可能自相矛盾。** 例如本地 Fit GD1 页面不同位置的里程单位可能是 miles/km，部分平台模板可能显示明显不合理的汽油机排量规格。为了避免将模板/人工输入错误“洗成技术事实”，本文**只使用“该车型名/年份在线挂牌可见”作为市场存在性线索**；不复制里程、排量、发动机功率、具体车牌或卖家联系方式。若公开资料冲突，状态设 `CONFLICTING_SELLER_METADATA`，而非自动挑一个字段当真实车型。

`MYANMAR_ON_ROAD_FIT_STOCK=UNKNOWN`，`MYANMAR_FIT_AGE_DISTRIBUTION=UNKNOWN`，`MYANMAR_FIT_FAULT_FREQUENCY=UNKNOWN`；本稿不能给这些数据造分母。

## 3. Honda 原始发布资料证实的真实技术分界

下面只列 Honda **日本市场产品发布时点**的型号/系统存在性，不能外推为缅甸每台 Fit 的具体配置。

| 厂商资料和车型时期 | 原厂公开技术事实 | 与维修知识的直接关系 | 不能泛化 |
|---|---|---|---|
| **2001 Fit 第 1 代发布** | Honda 日本官网 2001 年发布，提出 1.3L i-DSI、Honda Multimatic S **CVT**、车体中置燃料箱结构 | CVT 与普通固定挡位自动变速箱的核心机理不同；油箱/车身布局影响结构索引 | 不能据 2001 日本发布将任意 GD1 当作“与某一 2001 配置完全一致” |
| **2007 Fit 第 2 代发布** | Honda 日本官方 2007 年资料记录新 1.3L i-VTEC 与 CVT（部分设计含液力变矩器），4WD 和 MT 按型号另有配置 | **“有液力变矩器”仍可能是 CVT**，不能由此把车归到 `STR-AT` 的行星多挡家族；不同驱动布局会改变传动适用性 | 不能断言所有 GE 都是 CVT 或 2WD |
| **2010 第 2 代 Fit 与 Fit Hybrid** | Honda 官方 2010 年日本价格/技术配置表明确含 **FWD CVT、部分 4WD 的 5AT、MT，以及 IMA Hybrid + CVT** | 直接回应计划审核 P2：**4WD 5AT 为官方真实选配路径**；同一时期的 CVT/5AT/IMA-CVT 的排故前置和可能使用的油液不可混写 | 不等于 2008 缅甸 GE6 必为 5AT 或 hybrid；需要车型/年款/驱动匹配 |
| **2013 第 3 代 Fit / Fit Hybrid** | Honda 官方 2013 年日本产品发布：1.3L 汽油车型使用 CVT 的版本；**i-DCD 混动采用单电机 + 7 速 DCT**，并涉及电动伺服制动的再生协同 | `i-DCD DCT` 与 `IMA-CVT`、汽油 CVT 的机械和控制链不同；制动融合属于具体混动变型任务 | 不能把一条 “Fit Hybrid” 统称 e:HEV 或 7DCT |
| **2020 第 4 代 Fit / e:HEV** | Honda 官方 2020 年日本发布 **双电机 e:HEV** 变型，与前代 i-DCD 不是同一动力/传动控制架构 | 混动能量路径、驱动/再生制动与传动系统的知识必须分开 | 不能从平台上曾有新一代产品推断缅甸市场主要旧车样本属于这代，亦不能将其当纯电 BEV |

**Honda 官方来源（真实资料年份）**：
- [Honda Japan — Fit 2001 首代发布](https://global.honda/jp/news/2001/4010621-fit.html)：1.3L i-DSI、Multimatic S CVT 与车体布局。
- [Honda Global — New Fit 2007](https://global.honda/en/newsroom/news/2007/4071018-fit-eng.html)：第 2 代，传动/驱动条件因型号而异。
- [Honda Global — Fit / Fit Hybrid 2010](https://global.honda/en/newsroom/news/2010/4101008eng-fit.html)：明确日本市场 **4WD 部分 5AT / FWD CVT / Hybrid IMA-CVT** 等组合（本轮审核 P2-03 已落实）。
- [Honda Global — Fit / Fit Hybrid 2013](https://global.honda/en/newsroom/news/2013/4130905eng-fit.html)：CVT 与 i-DCD 7DCT 混动分别适用。
- [Honda Global — Fourth-generation Fit 2020](https://global.honda/en/newsroom/news/2020/4200213eng-fit.html)：e:HEV 双电机变型。
- 上述公开厂商新闻不是按车辆车架号调出的维修手册，**不能据此直接给出排气/制动标定、高压隔离、CVT/ATF 液位测量和故障码的车型操作要求**。

## 4. “车型系列 → 真正维修知识差异”映射

### 4.1 最重要的差异：自动变速箱名称不能当结构

```text
Fit 的实际车架/驱动/动力/年款待核验
  ├─ 一部分汽油车型：CVT（无级变速）
  ├─ 一部分汽油车型：5AT（2010 日本官方证实部分 4WD 配置）
  ├─ 某些配置：MT（手动）
  ├─ IMA Hybrid：IMA + CVT（2010 日本产品）
  ├─ i-DCD Hybrid：电机 + 7DCT（2013 日本产品）
  └─ e:HEV：2020 日本双电机混动架构
```

这是**产品家族分支候选图**，并不是证明缅甸正在售某辆 Fit 属于哪一分支；分支中的实际车架/ECU/传动版本仍 UNKNOWN。

适用性后果：
- `STR-AT` 的传统“液力变矩器＋行星齿轮＋液压执行摩擦元件”的知识**不能自动套给 Fit CVT/7DCT/e:HEV**；但 2010 公开有 `5AT` 变型，说明“Fit 一概没有普通 AT”同样错误。应先识别具体变速器代码/资料，必要时仅引用 STR-AT 作为 AT 家族边界。
- Honda 2007 年的 CVT 有某些设计采用液力变矩器，**但变速比由 CVT 机构调节，不会因为液力变矩器就变成行星多挡 AT**。
- `SER-DELTA-FIT-TRANS` 需要后续真正按配置/资料清晰关联家族、油液与维修判断差异；**目前这只是来源支持的“值得写的 delta 候选”，还不是已生成的 delta。**

### 4.2 混动系统：IMA、i-DCD、e:HEV 必须分清

这三种 Honda 混动家族的电机参与动力与传动方式不同。现有 `STR-HV` 是 **BEV** 通用高压构型，**不是 Fit HEV/I-DCD/e:HEV 的专业事实证明**；需要另立有来源的 `ARCH-HEV` / `VAR-HONDA-HYBRID` 专题，再将已有安全知识按证据引用。不能用纯电车“高压断电”文字推导 Fit 混动车维修步骤。

后续优先级取决于缅甸实际混动车配置与 OEM 资料可见程度：如果只发现汽油 GD1/GE6，**不应让整个研究被 2020 e:HEV 无关深度任务抢占**。

### 4.3 制动与再生制动：要按混动技术分支判断

通用 [STR-BRK](../../../../topics/braking/structure.md) 可作为制动/ABS/ESC 结构索引；Honda 2013 代 i-DCD 新闻明确提及电动伺服制动与再生协同，2020 e:HEV 架构又不同。普通汽油 Fit 不应被默认赋予混动制动融合部件，任何分支的失效后备、低压电源、传感器、再生逻辑和维修程序都需版本证据。**无型号、OEM 安全程序不可编造电液制动排气/标定或混动高压作业步骤**。

### 4.4 发动机/冷却/低压系统差异

2001 i-DSI 与后续 i-VTEC、以及混动相关发动机变体的结构和控制策略可能不同，但本发现稿没有逐车准确发动机维修图、保养规格、ECU 固件及更换零件记录。今后先从车型/车架/发动机代码识别开始；发动机润滑一般原理可用 [STR-ENG-LUBE](../../../../topics/engine/lubrication/structure.md)，不得直接把其中的“概念油路”说成具体 Fit 的 OEM 油路。

## 5. 车型识别时必须收集哪些条件

| 字段 | 当前 L3 发现值 | 升级到 L4 前缺失的证据 |
|---|---|---|
| `manufacturer/nameplate` | HONDA FIT；Jazz 仅按地区资料进一步核实 | 实车出厂/市场名称 |
| `Myanmar_stock_relevance` | 有历史二手市场报道及当前 GD1/GE6 个别挂牌 | 全国分车型在用量及分布：UNKNOWN |
| `generations` | 厂商发布序列：2001/2007/2013/2020 | 实车车架号/型号、准确生产日期及市场 |
| `powertrain_family` | 汽油、IMA、i-DCD、e:HEV **在 Honda 历史发布中存在** | 当前缅甸研究车辆是否安装其中一种 |
| `transmission_family` | CVT / 某些 4WD 5AT / MT / i-DCD DCT / e:HEV 专用传动技术 | 实车变速器编码与按年款、地区、驱动形式匹配的资料 |
| `regional_scope` | OEM 资料大多为日本市场 | 缅甸车辆原始销售地区/JDM 进口及后续更换情况 |
| `software/hardware_revision` | UNKNOWN | OEM 当前软件版本、模块代次、适用 TSB |
| `maintenance_limits/fluids/repair_steps` | **UNKNOWN** | VIN/车型匹配的正式维修资料与合格技术人员 |
| `fault_rate/repair_cost_share` | **UNKNOWN** | 在用车分母、工单或保修记录；不得把新闻挂牌变成频率 |

### 5.1 2026-11-18 观察收据精度

当前保存了实际单条 URL，而不只是某平台首页，并注明日期。卖家可修改或删除信息，研究中应进一步记录来源存档/版本；**不能下载/复制车主身份、车牌、私人手机号等个人数据进知识仓**。CarMM “Verified/RTAD Verified” 属平台标签，不等于本研究独立核实车架/配置。

## 6. 差量任务 READY 判断和真正 STOP 规则

| 候选 | 当前可见来源带来的知识机会 | 状态与阻塞 |
|---|---|---|
| `SER-DELTA-FIT-TRANS` | Honda 原厂已证实跨代 CVT、部分 4WD 5AT、IMA-CVT、i-DCD 7DCT、e:HEV 的实质型式区别 | **CANDIDATE_MATERIAL_DELTA**：可先生成“家族适用性差量”，但具体缅甸车架尚未匹配，不能给车型维修参数；新 Writer 必须按真实当前 PLAN/Claim 领取 |
| `SER-DELTA-FIT-BRK` | Honda 2013 官方提到 i-DCD 电动伺服制动与再生效率；不同于普通汽油版的安全相关研究方向 | **CONDITIONAL / SOURCE_GAP**：须进一步核查实际变型与适用原文，不可假定 GD1/GE6 装有它；暂不写车型级危险维修操作 |
| `SER-HEV-FAMILY`（仅提案，未新增已批准 Task） | IMA / i-DCD / e:HEV 机制之间差异显著，通用 BEV 知识不覆盖所有混动结构 | `REPLAN_CANDIDATE`：需先依真实高价值缅甸样本确定要研究哪一代，不得因为 Honda 官网有新一代就大规模生成无关文章 |
| `SER-VARIANT-CHECK` | 收集真正交付的一个或多个 delta 后做复用/缺口汇总 | **WAITING_EVENT**，本篇发现文件完成不等于已发生 delta 事件 |

如果实测市场/官方资料不足以确定某个维修参数、车架对应配置、具体 DTC 或失效后备策略，就把该具体结论留作 `UNKNOWN`；不因缺数据就写大量无证据的“常见故障”。

## 7. 反例：哪些知识不应自动归属于缅甸某台 Fit

1. **“2008 年 Fit 一定是 CVT”**：Honda 在同代日本产品中还存在部分 4WD 5AT 及其它不同配置；卖家写 Automatic 不够判定。
2. **“有液力变矩器就是传统行星齿轮 AT”**：Honda 2007 年官方 CVT 也可使用变矩器；基本变比机构不能混淆。
3. **“Fit Hybrid 一定采用 7DCT”**：2010 的 IMA-CVT 与 2013 i-DCD 7DCT、2020 e:HEV 系统不同。
4. **“Fit Hybrid 就是纯电 BEV”**：HEV 与 BEV 动力结构、保护和维修适用前置不同。
5. **“缅甸一个挂牌标题写 GE6，所有同名挂牌都确定是某发动机/车架配置”**：卖家元数据不是 OEM 身份证明；必须按实际车架/动力/驱动验证。
6. **“2013 年的混动再生制动可直接指导 2007 汽油车排气/维修”**：不同控制架构，缺 OEM 资料无操作依据。
7. **“挂牌多说明 Fit 故障率高”**：当前挂牌既不是车型总数也不是工单统计，缺分母。

## 8. 本任务与下游移交边界

本轮有实际源依据的发现：Fit 在缅甸旧车交易有资料线索；Honda 第 1–4 代、汽油/IMA/i-DCD/e:HEV、CVT/5AT/MT/7DCT 等存在**需要区别适用性的技术分界**。不同来源的地区与日期保持独立，未推定具体缅甸车辆实际装配哪一种。

建议下游 `SER-DELTA-FIT-TRANS` 优先按日本官方发布的多个传动家族写**结构/适用性差量**，不把它冒充缅甸所有旧 Fit 的维修手册。涉及 `SER-DELTA-FIT-BRK` 的电动伺服/再生，先补实质来源及实际代际证据，并须保留高安全风险边界。

**完成标准限定**：这只是 `SER-DISC-FIT` 一篇已生成候选的真实内容，等待不同对话按 Exact Blob 独立内容质量审核；没有 OEM/VIN/实车/专业事实资格，也没有生成 4 个后继 delta。
