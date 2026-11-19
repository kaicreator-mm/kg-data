# 传统液力行星齿轮 AT：换挡迟滞、打滑、冲击与失去驱动力的可证伪失效机制 — FAIL-AT R1

> TASK_ID: `FAIL-AT` · 主控 [parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) · 有效通用 [PLAN.md](../../../PLAN.md) Blob `1df1f116a9f4e1effc46840aa4ec57be1289b6cf`。
>
> **两条实际前置已分别独立限定质量通过**：[行星动力路径 FUN-AT-PATH](./power-path.md) Blob `6c0a2855abf2751819ebcf1b039db05d8a953f71` / [Reviewer](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6989359346)；[液压功能 FUN-AT-HYD](./hydraulic-control.md) Blob `88338dbea91a278866ffb7ccca7d69b0f22c349e` / [Reviewer](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6989338636)。结构 [STR-AT](./structure.md) Blob `ed2b997ca164d98e74cf72ecb393aca86a553d20` 已获限定质量 ACCEPT。
>
> **当前新稿**：`GENERATED_REVIEW_PENDING / MODEL_GENERATED_UNVERIFIED`。仅研究典型**液力变矩器＋有级行星变速机构＋离合器/制动器液压执行**的乘用车 AT。不是 CVT（无级）、DCT（双离合）、Honda e:HEV（电机模式）或任一 Myanmar 车辆的真实故障认定。
>
> **不可执行边界**：本文不含实际车辆油压/ATF/油温/线路数值、通电测试、故障码到元件的确定映射、路试流程、拆装阀体/变速器、阀体孔加工或维修步骤。所有 OEM 安全、特殊工具、车型总成和维修程序资格 **NOT_QUALIFIED**；具体车架、变速箱型号、制造版本、失效频率和维修经济性 **UNKNOWN**。

## 1. 研究目标：症状不是根因，失效路径也不是故障概率

传统 AT 的正常动力链可以抽象为：发动机有效扭矩 → 变矩器输入/耦合 → 行星机构所需的合法离合器/制动器约束 → 输出/差速器/驱动轮。对应的另一条能量/控制链是泵供流 → 主压调节 → 阀体分配/调制 → 离合器油腔充油与摩擦力 → 实际机械约束，以及 TCC/冷却/润滑与控制通信。**失效研究必须检查链条哪里可能断裂或出现偏离**，而不是把同一种驾驶者描述等同于某一个零件故障。

- `OBSERVATION`：司机观察到的换挡迟滞、升挡转速异常、冲击或无驱动，仅是待核症状，未必说明异常在变速箱内。
- `HYPOTHESIS`：与该症状物理一致的多个可能因果路径，可从厂商/专业来源取得案例。
- `DISCRIMINATOR`：未来若要区别假设，需要与实际 OEM 版本匹配的状态、证据及反例；**不在本稿下达实车测试指令**。
- `UNKNOWN`：缺对应车型真实数据时不能把竞争假设提升为已证实故障。
- `REPAIR_DECISION`：只由后续 `REP-AT` 在合法来源/专业边界内研究，本篇不执行维修。

## 2. 失效机制簇：因果链、正常反例和可鉴别信息

| 机制簇（只是候选） | 可能的物理因果链 | 可表现的现象候选 | 竞争解释/反例和需要的证据 |
|---|---|---|---|
| **液压供流不足或内部泄漏** | 泵/吸油/阀体间隙或离合器油腔泄漏 → 有效流量被消耗 → 元件充油、接合压力或冷却供流不足 → 摩擦容量不满足目标 | 迟滞入挡、特定换挡 flare、热负荷或多挡异常 | 没有证据不能说“主压一定低”；某支路泄漏可能在不同工况/温度下显现，且发动机扭矩、控制策略亦影响表现 |
| **主压调节与调压控制异常** | 主调压阀/调节反馈或执行控制偏离 → 主压/供流分配失配 → 元件接合速度、变矩器与冷却支路可能改变 | 换挡过硬/过软、迟滞、TCC 相关变化 | 仅有主压数据不证明各支路流量或离合器夹持；需实际型号回路及调节状态，非所有 AT 同拓扑 |
| **换挡阀、蓄压器与支路调制异常** | 阀芯/滑阀控制、蓄压器密封/节流或调制条件变化 → 摩擦元件充放油斜率偏离 → 扭矩交接时序改变 | 换挡冲击、延长滑差、某档 flare | 某些型号无该具体蓄压器/电磁阀结构；换挡重叠时序、发动机扭矩管理亦可能相似 |
| **离合器、制动带/制动器或单向元件传扭能力不足** | 接合元件摩擦材料/机械/密封或单向保持作用不足 → 原理上应成立的行星运动学约束未稳定建立 → 受载速度比偏离 | 选定挡位无力、异常滑差、换挡中断 | 某挡失效无法由通用元件表定位具体离合器；要知道真实接合表/行星机械连接/驱动许可 |
| **变矩器液力耦合与 TCC 调制异常** | 变矩器充油或锁止供排/摩擦状态与控制目标不匹配 → 滑差与热负荷变化 | 巡航转速变化、锁止相关抖动、油温升高 | 液力增扭、锁止调制变化可能是正常状态；TCC ≠ 换挡离合器，且 CVT 也可能配变矩器 |
| **输入、传感与电控许可异常** | 输入转速/负载/选挡/电源/网络信息不可用或错误 → 控制器产生不同目标、受限模式或元件调制 | 可观察冲击、延迟、换挡逻辑变化、拒绝某挡 | 控制策略/版本不同，报码不等于物理执行器故障；没有 TCM/ECU 版次不做单一结论 |
| **油液热行为、污染/磨屑与润滑问题** | 油液/温度/冷却流路状态影响液压响应、摩擦与散热 → 机械/控制条件发生变化 | 热后迟滞、长时负载异常、机械磨损风险 | 油品是否合适、污染来源和实际油温均需 OEM/维护历史；不建议凭通用标签换油或做危险检查 |
| **发动机、驱动桥、车轮/制动和驾驶工况（外部竞争）** | 发动机可用扭矩、制动拖滞、差速器/半轴/轮胎附着与驾驶模式可能改变加速/转速响应 | “加速弱”“起步抖”“不走”等相似描述 | 即使传动有故障灯，仍不能排除外部因素；不把所有慢加速视作变速器打滑 |

### 2.1 一个来源可核实的案例，不等于每辆车的通病

Sonnax 对 **GM 4L60/700-R4** 的蓄压器/换挡舒适性原始专业文章说明：在该设计里，蓄压器活塞/相关阀孔泄漏可改变离合/制动元件接合与前进挡表现。<https://www.sonnax.com/tech_resources/675-hydraulics-fundamentals-part-ii-accumulators-shift-feel>

**范围限制**：这不是 Toyota Probox 4AT 或 Honda Fit 部分 5AT 的 OEM 蓄压器证据。该案例只支持“同样换挡冲击可能通过**支路液压调制**产生”，不能推断所有 AT 有完全相同部件编号、密封、泄漏点或维修方法。

Sonnax 对 **GM 4L60-E** 的 3–4 挡离合损伤分析显示：在其特定油路中，第 3 蓄压器单向阀组件泄漏可降低离合器应用压力并形成烧损机制。<https://www.sonnax.com/tech_resources/323-guard-against-4l60-e-band-3-4-clutch-failure-test-the-3rd-accumulator-checkball-assembly-for-leakage>

**范围限制**：不能把 `3–4 clutch`、`checkball #7` 等具体零件/序号写成所有行星 AT 的标准故障点；需要真实齿轮机构、油路与失效证据才能在专业维修环节引用。

## 3. 从不同可见症状出发，必须保留的竞争因果图

| 观察标签（不代表发生频率） | 假设 A（机械路径） | 假设 B（液压路径） | 假设 C（电控/外部路径） | 不能先行下的结论 |
|---|---|---|---|---|
| `SHIFT_HARSH`：换挡冲击 | 相关离合器结合/释放、单向约束和惯量产生扭矩扰动 | 蓄压器/调压/充油速率偏离 | 扭矩干预/网络/传感/驾驶负载 | “指定一个电磁阀损坏” |
| `SHIFT_FLARE`：换挡时输入转速短暂上扬 | 旧元件释放与新元件接合间约束暂不成立 | 油腔充油不足或泄漏/调压响应 | ECU/TCM 换挡目标及发动机扭矩协同 | “必然离合器片烧坏” |
| `DELAYED_ENGAGEMENT`：选挡后延迟 | 制动器/离合机械间隙或输出约束条件 | 泵供流/调压/油腔充油时间 | 选挡许可、低压控制、发动机/防盗状态 | “换油后立即能解决” |
| `DRIVE_LOSS`：某一挡或全挡无驱动 | 实际接合元件、行星输出/差速器/半轴 | 供流/相关档位液压回路 | 发动机有效扭矩、整车限制、驱动轮条件 | “某一行星齿轮坏” |
| `TCC_SLIP_OR_SHUDDER`：锁止相关抖动 | TCC 摩擦传扭条件 | 锁止供排油、变矩器充油/温度 | ECU 控制滑差、输入扭矩脉动或路况 | “所有变矩器都应完全无滑差” |
| `HOT_ONLY`：热后更明显 | 热膨胀、摩擦/密封状态变化可能影响传扭 | 介质黏度、泄漏/热管理、冷却供流变化 | 高温策略、外部热负载 | “热后问题只有 ATF 油品一种原因” |

**后续可观察证据类型**：适用车型精确接合表/动力路径、真实 TCM 软件和故障环境、受控档域目标与实际转速/负载、相应油路/变矩器冷却与润滑路径、机械传扭和输出状态、同一状态下可能解释现象的发动机/传动轴/车轮因素。它们是**证据种类和未来研究需求，不是指导人员在车辆上操作的步骤**。

Sonnax 针对多变速箱的专业诊断论述明确区分滑差/flare、迟滞/冲击、锁止与油压的不同系统条件，并强调测试参数需按变速箱实际型号和控制系统处理。<https://www.sonnax.com/tech_resources/314-transmission-diagnostics-using-pressure-guages>

## 4. 失效演化、错误归因与可能误修后果（不构成维修命令）

- **局部泄漏 → 摩擦元件容量不足 → 温度/磨损次生变化**：特定 4L60-E 原始案例说明泄漏可能先于显著摩擦组件损伤，但没有个体检验和匹配油路时，不能倒推某车经历同一顺序。
- **阀芯/蓄压器调制偏差 → 换挡冲击 → 传动系统负载变化**：同一个驾驶者症状，可能与真实车辆制造/标定时的正常换挡特征混淆，需要识别不同车型的允许工作区间。
- **主压存在但冷却/润滑流量不足**：Sonnax 的变矩器/冷却/润滑供流案例说明某些主调压阀工作条件可限制分支流量，所以单次主压数据不能保证润滑充足。<https://www.sonnax.com/tech_resources/131-anatomy-of-a-transmission-oil-flow-in-the-pump-pr-converter-cooler-lube-circuits>
- **电控指令变化 ≠ 元件真实动作**：诊断工具看到“切换命令”，还需要机电/液压真实证据确认结果；不能因为电磁阀被控制就认定离合器接合完成。
- **只按一个症状替换部件的误修**：在未识别总成、外部负载或不同油路之前，换一个“常见”阀体/变矩器/离合器可能无法触及真实原因，造成部件浪费、二次损伤甚至不安全。这里只记录**误修风险机理**，不提供替换流程和未经验证的经济数字。

## 5. 具体车型及资料适用边界

已有 [Toyota Probox/Succeed 车型传动差量](../../../series/myanmar/toyota/probox/transmission-applicability-delta.md) 说明日本历史产品家族有 4AT/5MT 与后续特定改款 CVT 的区别；[Honda Fit 传动差量](../../../series/myanmar/honda/fit/transmission-variants-delta.md) 说明某些年款有 CVT、部分 4WD 5AT、IMA、i-DCD 7DCT、e:HEV。两篇都是**限定生成质量审核通过的差量研究**，不是缅甸现车的真实总成适用证明。

| 型号研究问题 | 合法使用本稿的前提 | 当前不能确认 |
|---|---|---|
| 一辆旧 Probox 被广告标为 Automatic | 先有独立证据确认其**确实是传统有级液力行星 AT**，而非后续 CVT | 实际车架/制造月、 gearbox code、油路/ECU/齿轮接合表 |
| 一辆旧 Fit 被称为自动挡 | 确认适用车型/生产时期/实际传动型式；部分 4WD 5AT 可能属于研究范围 | GD1/GE6 卖家字符串不足证明 5AT/某齿轮箱，混动更不能靠此稿推断 |
| 具体车辆主诉换挡冲击、迟滞或无驱动 | 必须取得实际工况、环境、外部竞争原因和 OEM 总成资料 | 故障发生率、最小试验、部件真实磨损/油压/控制、维修结果均 UNKNOWN |

`VIN/FRAME_NO`、`BUILD_MONTH`、`ENGINE_CODE`、`TRANSMISSION_CODE`、`ECU_VERSION`、`OEM_AT_HYDRAULIC_MAP`、`DIAGNOSTIC_LIMITS`、`SERVICE_MANUAL_RIGHTS`、`ACTUAL_MYANMAR_FAILURE_RATE` 均 **UNKNOWN**。*零件/阀体/油压建议不存在合法替代路径*。

## 6. 如何形成后续诊断维修 Task，而不把生成知识当成实车答案

`REP-AT` 是已接受原 DAG 中 `FAIL-AT` 的后继，只在本 FAIL 真实提交/回读、由其它对话独立限定审核并核对上游未 STALE 后，才能考虑启动。后继应产出的是“**证据→竞争解释→可证伪条件→误修代价/安全 STOP**”的非操作性诊断研究，不是没有 OEM 支持的施工流程。

建议在真实变速箱家族适配后构建以下证据维度（当前全部仅为待补证条件）：

1. **机械必要条件**：某挡的真实动力接合/约束表及输出连接。
2. **液压必要条件**：相匹配的调压/阀体、离合油腔、变矩器/冷却/润滑的实际油路，不以一个主压力代替全路。
3. **控制必要条件**：对应 ECU/TCM 的请求、传感、许可、软件版本与故障环境。
4. **外部竞争原因**：发动机、驱动桥、制动、轮胎、驾驶状态等，保留 UNKNOWN。
5. **可证伪观测**：在适用安全/车型资料前提下，什么证据会支持或排除特定候选，拒绝“一个报码一个零件”的固化推断。
6. **安全/资格边界**：无专业实车资料、必要安全条件和明确机型时不得转化为高风险现场操作。

## 7. 原始专业出版方、年份与唯一支持范围

| 原始专业资料 | 在本稿中可支持什么 | 明确不能支持什么 |
|---|---|---|
| [Sonnax, *Hydraulics Fundamentals Part II: Accumulators & Shift Feel*](https://www.sonnax.com/tech_resources/675-hydraulics-fundamentals-part-ii-accumulators-shift-feel) | GM 4L60 的换挡舒适性与蓄压器、压力/泄漏控制机理实例 | 任意 Toyota/Honda AT 的蓄压器名称或真实泄漏点 |
| [Sonnax, *Guard Against 4L60/E Band & 3–4 Clutch Failure*](https://www.sonnax.com/tech_resources/323-guard-against-4l60-e-band-3-4-clutch-failure-test-the-3rd-accumulator-checkball-assembly-for-leakage) | GM 4L60-E 特定支路泄漏减少 3–4 离合器施加压力、导致磨损的源明确案例 | 每个 AT 都有同序号、同挡位元件 |
| [Sonnax, *Hydraulics Fundamentals Part I: Main Pressure Regulator*](https://www.sonnax.com/tech_resources/674-hydraulics-fundamentals-part-i-main-pressure-regulator-valve-line-ups) | 供流/调压平衡、泵转速/供流与变矩器供油条件的差别 | 提供通用 ATF 主压数值 |
| [Sonnax, *Anatomy of a Transmission — Oil Flow*](https://www.sonnax.com/tech_resources/131-anatomy-of-a-transmission-oil-flow-in-the-pump-pr-converter-cooler-lube-circuits) | 某实际样例中主压调节可影响变矩器/冷却/润滑供流 | 所有 AT 的支路顺序和零件布局 |
| [Sonnax, *Transmission Diagnostics Using Pressure Gauges*](https://www.sonnax.com/tech_resources/314-transmission-diagnostics-using-pressure-guages) | 迟滞、flare、冲击/打滑和 TCC 问题存在不同诊断证据需求 | 在没有相配安全/OEM 条件时指导实际压力测量 |
| [Sonnax, *AW 55-50 / AF23-33 Diagnosis*](https://www.sonnax.com/tech_resources/196-aw-55-50-af23-33-diagnosis-and-valve-body-information) | **不同厂家/总成**内部泄漏/阀体相关的迟滞/flare 案例，支持跨案例竞争假设的必要性 | 其维修措施或阀体类型可用于缅甸 Probox/Fit |

**本研究的终止声明**：机械/液压/电控/热与外部竞争机理、反例与所缺证据已形成可核验知识候选，**不是维修诊断已经完成**。本篇仍需要非 Writer 不同对话对当前 Exact Blob 进行独立质量审核（含 OEM/案例技术范围、来源时效、合理性、UNKNOWN），通过后才可安排 `REP-AT` 的限定研究级生成。
