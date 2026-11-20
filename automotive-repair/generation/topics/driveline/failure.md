# 驱动系失效竞争诊断：差速器/CVJ/半轴/传动轴 vs 轮毂轴承与轮胎噪声，及失驱边界（FAIL-DRIVELINE R23）

> TASK_ID: `FAIL-DRIVELINE` · MAIN: [parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) · 独立准入：[C-R16-DISPATCH=ADMITTED_SCOPED](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7021821148) · 派发：[#61 R23 dispatch](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7021981579) · 范围：`ICE_FF_OR_4WD_CONDITIONAL_PROBOX_AD_SWIFT`。
> 直接上游：[FUN-DRIVELINE 正常功能](./function.md)，Exact Blob `2a61e9eb0027194db141b302b98af19e246a1fb8`（本稿 SOURCE 是其直接上游）；结构参考 [STR-DRIVELINE](./structure.md)；证据分层复用 [通用诊断方法 S0–S4](../common/diagnostic-methods.md)；轮胎/悬架竞争面参考 [转向悬架轮胎正常功能](../steering-suspension/function.md)；失驱上游竞争引 [CVT 诊断决策框架](../transmission/cvt/diagnostic-repair.md) 与 [AT 失效目录](../transmission/automatic/failure.md)，不重写其内容。
> 身份：`MODEL_GENERATED_UNVERIFIED` / `GENERATED_REVIEW_PENDING`；OEM/VIN/N3=NOT_GRANTED。本稿是研究级竞争假说与证据区分力知识，不是缅甸任一实车的维修程序、故障率结论或听诊定位手册。
> 主要问题：转弯/直线/加减速的嗡鸣、咔哒与振动，以及「发动机在转但车不走」时，如何在差速器（轴承/齿轮）、半轴/CVJ、传动轴（仅 4WD 条件）、终传、轮毂轴承、轮胎花纹/气压等竞争来源之间用可区分证据收缩假说，并识别从「异响」升级到「失驱/卡死」的风险边界？

## 1. 适用性先行：先定硬件存在性，再谈失效

| 适用性条件 | 本稿的处理 | 不允许的默认 |
|---|---|---|
| 驱动架构 | ICE 前驱（FF）为主研究骨架；4WD 分支**仅当实车证实存在**传动轴/分动/后差硬件才进入 | 缅甸存量候选 Probox/AD/Swift 均以 2WD 线索为主，日本产品线另有 4WD 分支（见 [Probox 差量](../../series/myanmar/toyota/probox/transmission-applicability-delta.md)、[AD 发现](../../series/myanmar/nissan/ad-van/discovery.md)、[Swift 发现](../../series/myanmar/suzuki/swift/discovery.md)），任一实车 `DRIVELINE_VARIANT=UNKNOWN` |
| LSD/AWD 多片离合器 | 不假设存在；开式差速器是默认**未证实**工作假设 | 由「有异响」推断装了 LSD/锁止并据此解释症状 |
| 传动轴 propshaft | 条件分支：`4WD_CONFIRMED` 才参与竞争假说；2WD 证据成立时该分支为 NOT_APPLICABLE | 在未证实四驱的 FF 车上生成「传动轴/中间支承」诊断 |
| 变速器内部 | 「发动机转车不走」的变速器侧候选移交 [CVT](../transmission/cvt/diagnostic-repair.md) / [AT](../transmission/automatic/failure.md) 各自失效目录 | 用本文重写 CVT/AT 失效机理或油液结论 |

## 2. 失效机理分层：每层的正常前提与偏离路径

[已接受 FUN-DRIVELINE](./function.md) 给出的正常前提（开式差速 `ω_left+ω_right≈2×ω_case`、外固定节/内滑移节分工、`P=T×ω`）是下表偏离的判据基线：

| 层 | 候选失效机理（物理链） | 症状方向 | 升级到失驱/卡死的路径 |
|---|---|---|---|
| 外侧固定 CVJ（outer Rzeppa） | 护套破损→脂流失/污染→钢球/滚道点蚀→大转角受载下间隙冲击 | 低速大转角「咔哒/咔嗒」 | 点蚀恶化→卡滞→异响升级+转向阻力异常 |
| 内侧滑移节（inner plunging/tripod） | 花键/滚道磨损或 plunge 卡滞→直线传力激励 | 直线嗡鸣/轻微振动候选 | 卡滞→轴向载荷交给悬架/壳体 |
| 半轴 sideshaft/花键 | 扭转过载断裂、花键磨损退出啮合 | 阶跃性失驱；开式差速下动力经断侧泄漏 | **开式差速一侧断裂=整轴失去有效输出**（理想对称开式差速两侧转矩近似相等的下游后果） |
| 差速器轴承与行星/侧齿轮 | 轴承滚道疲劳→速度相关嗡鸣；齿隙增大→驱动/滑行切换冲击 | 随车速嗡鸣；起步/换向金属敲击 | 断齿/碎屑→咬死，伴金属摩擦与卡死感 |
| 终传 final drive（FF 集成于变速驱动桥） | 环齿/小齿轮点蚀、预紧偏离 | 随车速的齿轮啸鸣 | 断齿→瞬时失驱 |
| 传动轴+中间支承（仅 4WD 条件） | 万向节磨损、支承橡胶失效、失衡 | 随车速振动/轰鸣 | 支承脱落→轴敲击壳体（条件分支内） |
| 轮毂轴承 wheel bearing | 滚道/钢球疲劳 | 随车速嗡鸣，**侧倾改变轴承载荷时噪声强度变化** | 极端磨损→轮端旷量/抱死风险（安全级） |
| 轮胎本身 | 块状/越野花纹周期噪声、偏磨、变形、气压失配 | 随车速嗡鸣+振动，**随路面类型切换变化** | 不是失驱来源，但可将「异响」误归为驱动系 |

**对抗性混淆核心（轴承 vs 轮胎）**：两者都产生随车速线性变化的嗡鸣。区分轴是：轻微变线/转弯改变左右载荷→轴承噪声随受载侧变化，轮胎花纹噪声不随载荷而随**路面材质**变化；换路面（沥青/混凝土/粗糙面）明显改变→轮胎候选上升。这是候选区分方向，不是听诊定位结论。

## 3. 症状 → 竞争解释 → 区分证据矩阵（研究级）

证据轴：**车速 / 转向角 / 驱动负荷 / 路面类型**。以下均为可区分假说的研究观察框架，不是举升、路试或听诊操作指令；噪声**不能单凭听诊定位总成**。

| 观察情境 | 竞争假说（均未证实） | 有区分力的证据（类型） | 不得直接下的结论 |
|---|---|---|---|
| 低速大转角「咔哒」周期出现 | 外 CVJ 磨损；轮毂轴承旷量；轮胎/轮拱异物或制动件间隙 | 咔哒是否仅在转向角超过阈值时出现、频率是否随车速变化、是否伴随振动 | 「咔哒=外球笼断」 |
| 直线嗡鸣随车速上升 | 轮胎花纹/偏磨；轮毂轴承；差速器或终传轴承；（4WD 条件）propshaft 支承 | 变线改变侧倾时强度变化→轴承；换路面类型变化→轮胎；驱动/滑行负荷改变→齿轮系 | 「嗡鸣=差速器坏」 |
| 加速时左转与右转噪声不对称 | 左/右轮毂轴承之一（受载侧更响）；差速器内部（载荷相关而非方向相关）；左右外 CVJ 磨损不对称 | 固定车速下噪声与转向方向、驱动/滑行状态的二维关联 | 「有方向性=某侧半轴」 |
| 起步/换向金属敲击 | 差速器齿隙/花键间隙；内侧 CVJ plunge 卡滞；悬架衬套或悬置（非驱动系）；制动件松动 | 敲击是否只出现在驱动/滑行转矩切换瞬间、是否与车身运动（过坎）重叠 | 「一敲就是齿轮断」 |
| 匀速振动随车速、不随发动机转速 | 车轮动平衡/轮胎变形；propshaft 失衡（4WD 条件）；半轴弯曲/CVJ 磨损；制动拖滞热变形 | 滑行（动力脱开）时振动保留→轮端/传动旋转件；消失→发动机/变速侧 | 「高速抖=传动轴失衡」 |
| 冷/热状态改变噪声 | 差速器/终传油温相关齿轮噪声（不涉及油品规格）；轮胎低温硬化；轴承热态间隙变化 | 温度轴与工况轴的先后关系记录 | 「热车响=该换齿轮油」 |
| 噪声升级为金属摩擦/卡死感 | 齿面点蚀→断齿前兆；CVJ 完全碎裂；轴承保持架解体 | 症状演化时间线、突变点；**此级属安全 STOP**（§5） | 继续行驶「观察观察」 |
| 发动机在转但车不走 | 见 §4 失驱竞争段 | — | 直接指认半轴或差速器 |

## 4. 失驱竞争段：发动机仍输出但车轮无扭矩

「RPM 正常/上升但车不动」至少有五条物理上成立的路径，必须并行保留，直到有区分证据：

| 路径 | 机理 | 与驱动系失效的区分点 | 出口 |
|---|---|---|---|
| H1 变速器内部 | CVT 夹持/带轮滑移、AT 摩擦元件/液压失效 | 档位/啮合感、RPM-车速关系异常早于异响 | 移交 [CVT REP 框架](../transmission/cvt/diagnostic-repair.md) 或 [AT FAIL](../transmission/automatic/failure.md)，本文不展开 |
| H2 半轴断裂/花键退出 | 开式差速下动力经断侧泄漏，整轴无有效输出 | 可有「啪」的阶跃事件史；此前可有 CVJ/护套异常线索 | 驱动系候选保留，需轮端与差速侧证据 |
| H3 差速器/终传损毁 | 行星齿轮碎裂、壳体咬死 | 通常有升级噪声时间线（§2 表末列） | 驱动系候选保留；伴卡死感则安全 STOP |
| H4 轮端脱离 | 半轴自轮毂脱出、极端机械分离 | 事件突发+可见轮端异常 | 安全 STOP，移交 |
| H5 控制性限扭 | 发动机 limp、ESC/牵引控制干预——**非机械断传** | 仪表/警告事件与控制上下文 | 按 [DISC-METHOD](../common/diagnostic-methods.md) 电控候选处理 |

缅甸存量候选车的传动家族（Probox 4AT/5MT/2014 CVT、AD CVT/E-ATx、Swift CVT/4AT/5MT）在无车架/铭牌证据时 `TRANSMISSION_ARCHITECTURE=UNKNOWN`，H1 内部再分账依赖该身份先成立。

## 5. 缅甸场景案例（研究反例，非实车结论）

| 案例 | 错误归因路径 | 正确出口 |
|---|---|---|
| 某辆换装块状花纹越野胎的 Swift 被报「差速器嗡鸣」 | 把随车速的胎噪当齿轮系噪声 | 路面类型切换观察→轮胎候选上升；`DIFF_TYPE=UNKNOWN`，不下「差速器坏」 |
| 「4WD Probox」传动轴振动被当半轴响（卖家宣传 4WD，实车硬件未证实） | 在未证实 propshaft 存在的车上生成传动轴诊断，或在确有 4WD 硬件时把支承振动归给半轴 | 先按 [Probox 差量](../../series/myanmar/toyota/probox/transmission-applicability-delta.md) 的证据条件确认驱动硬件；`4WD_CONFIRMED` 前 propshaft 分支 UNKNOWN 而非 NOT_APPLICABLE |
| 挂牌「2011 Automatic」Probox 起步发动机转车不走被直接当「半轴断」（[发现稿 MMR-PB-02](../../series/myanmar/toyota/probox/discovery.md) 年份字段自相冲突） | 跳过 H1/H5 直接拆驱动系 | `TRANSMISSION_ARCHITECTURE=UNKNOWN`；五路假说并行保留，移交合格人员做变速器/驱动系分账 |

## 6. 来源与可证伪边界

| 来源（均为已接受语料中已出现的原始 URL） | 支持的限定事实 | 不支持的外推 |
|---|---|---|
| [GKN Sideshafts](https://www.gknautomotive.com/en/aftermarket/portfolio/sideshafts/) / [CV joints](https://www.gknautomotive.com/en/aftermarket/portfolio/constant-velocity-joints/) | 外固定节+内滑移节产品范式、护套密封润滑角色、转向/悬架补偿的设计需求 | 任一车型的允许工作角、零件号、磨损限值 |
| [GKN Propshafts](https://www.gknautomotive.com/en/systems-and-solutions/sideshafts-propshafts/propshafts/) | 纵向轴、接头/支承布局多样性存在 | FF 车必有传动轴、支承维修参数 |
| [GKN AWD systems](https://www.gknautomotive.com/en/products-and-systems/awd-systems/) | 轴间耦合/脱开方案为可选技术 | 缅甸实车装有 AWD/LSD |
| [Spicer 齿比计算器](https://spicerparts.com/calculators/gear-ratio-calculator) / [差速总成](https://spicerparts.com/parts/axle/automotive-performance/differential-case-assemblies) / [Trac-Lok](https://spicerparts.com/press-release/dana-introduces-genuine-spicer-trac-lok-for-aftermarket) | 终传齿比计算原理、差速构件类别、LSD 产品类别存在 | Probox/AD/Swift 的齿比、LSD 装车或预紧规格 |
| [Toyota 2014 Probox 公告](https://global.toyota/en/detail/3737378) / [Nissan 2013 AD 表](https://global.nissannews.com/ja-JP/releases/130520-01-j) / [Suzuki 2010 Swift](https://www.suzuki.co.jp/release/a/2010/0826/index.html) | 日本产品线 2WD/4WD 分支与传动家族并存 | 任一缅甸实车的驱动/传动配置 |
| 本仓已接受 FUN/STR-DRIVELINE、CVT REP、AT FAIL、DISC-METHOD | 运动学基线、竞争框架、S0–S4 证据分层 | 任何 OEM 参数、实测定位率、维修成效 |

**UNKNOWN 清单**：`FRAME/VIN`、`BUILD_MONTH`、`DRIVELINE_VARIANT(2WD/4WD)`、`DIFF_TYPE`、`FINAL_DRIVE_RATIO`、`AXLE_CVJ_PART_NUMBER`、轴承预紧/齿隙 OEM 限值、`GEAR_OIL_SPEC/容量/更换周期`、缅甸各总成故障率、噪声→总成实测定位准确率、维修成效，全部 UNKNOWN，不推断。

## 7. 安全 STOP

- 异响升级为金属摩擦/卡死感、行驶中振动突增、失驱发生于坡道/车流：**立即安全停车并移交合格维修人员**；本稿不授权「继续观察行驶」。
- 禁止：举升后驱动轮旋转试验、齿轮油加注/更换操作、差速器/CVJ 拆解、任何扭矩/油品规格套用；旋转件接触有物理伤害风险。
- §2/§3 的速度/转向/负荷/路面观察是**证据分类框架**，实际采集须由具资格人员按适用 OEM 版次进行；研究级信息不是操作顺序。

## 8. 完成边界

本稿在已接受 FUN-DRIVELINE 基线上新增：失效机理分层、症状→竞争解释区分矩阵、失驱五路竞争与三个缅甸式反例。提交与 Blob 回读仅代表 `GENERATED_REVIEW_PENDING`；`GENERATION_QUALITY` 只能由未来非 Writer 独立审核授予，不晋升 OEM/VIN/N3，不修改任务 DAG 与其它 Writer 文件。
