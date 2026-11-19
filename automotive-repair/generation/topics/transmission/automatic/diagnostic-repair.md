# 传统液力行星 AT：证据驱动的诊断与维修决策研究 — REP-AT R1

> TASK_ID: `REP-AT` · 主控 [parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) · 通用 Task DAG [PLAN.md](../../../PLAN.md) Blob `1df1f116a9f4e1effc46840aa4ec57be1289b6cf` · 上游 [FAIL-AT](./failure.md) Blob `042c8d6bb21c53b877a6cd36238d854044759307` 已由不同 Writer 对话[独立限定生成质量接受](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6995905451)。
>
> **研究状态：`MODEL_GENERATED_UNVERIFIED / GENERATED_REVIEW_PENDING`。** 这里的“维修决策”是关于何时可以/不可以支持某种故障假说、如何避免误修及记录知识来源的**非操作性判断契约**，不是实际车辆的诊断报告、带载测试步骤、拆装说明或授权维修建议。**车型 OEM/VIN 适配、专业事实/N3 资格 = NONE**。
>
> **硬范围**：典型液力变矩器＋固定挡行星齿轮机构＋液压离合器/制动器的 AT；不包括带式 CVT、DCT、e:HEV Electric CVT。缅甸 Probox/Succeed、Fit/Jazz 的车型挂牌不等于已核对真实变速箱代码。具体 ATF、温度、油压、测试口、换挡表、ECU 软件、DTC、维修扭矩、操作安全条件：`UNKNOWN`。

## 1. 为什么不能从症状直接跳到维修

同一个“换挡冲击/迟滞/不走”在发动机输入、变矩器耦合、行星机构约束、泵与主压调节、支路流量/离合器充油、TCM 目标/传感以及驱动轴/车轮这些不同环节都可能出现。单症状没有唯一逆映射。即使某案例文章描述“4L60-E 的 #7 checkball 泄漏导致 3–4 clutch 损伤”，也只能证明**此特定结构的可行因果机制**，不能外推缅甸 Toyota/Honda 某辆车的零件、故障概率或修法。

**知识决策要经过的门禁**：

```text
真实 VIN/总成/市场/制造与软件版本 ──[不符或不明]──> UNKNOWN / STOP
                  │明确且来源合法
                  v
             症状与真实工况
                  v
       多个竞争因果候选（含外部原因）
                  v
     各候选的必要条件 / 反例 / 可鉴别证据类型
                  v
   有无实际 OEM 对应的可允许安全诊断证据？
      ├─ 没有 → UNKNOWN / REFUSE_TO_ATTRIBUTE / NO_REPAIR_DECISION
      └─ 有 → 专业诊断人员按原厂有效规则作证据解释；本稿不代行

任何单一来源矛盾或关键信息版本冲突 → STALE / STOP
```

这里列出的是**知识层证据类型**和决策资格，不指示人员实际运行压力测试、拆卸阀体、带车道路试或测量高温/带电部件。

## 2. 竞争失效机理、必要的独立证据与反证

| 观察标签 | 候选机械/液压路径 | 相互独立的证据类别（必须是适用车型，未经取得则 UNKNOWN） | 重要反例/STOP |
|---|---|---|---|
| `SHIFT_HARSH` 换挡冲击 | 摩擦元件充油/释放重叠、调压/蓄压器变化、行星约束与惯量耦合 | 实际 OEM 该挡离合结合表、TCM **指令与真实反馈分别**、车型允许换挡特性、液压支路及输入扭矩工况 | 正常标定的扭矩变化、发动机负载/车轮路面效应可能相似；不能直接指定电磁阀或阀体 |
| `SHIFT_FLARE` 换挡升转速 | 旧约束释放与新元件实际接合迟滞、离合摩擦承载不足、供流或支路泄漏 | OEM 当前目标挡与真实输入/输出转速的关系、独立供流/支路压力证据、真实总成的机械接合元件 | TCM 目标不等于执行完成；不能从转速抬升单独认定离合器烧损 |
| `DELAYED_ENGAGEMENT` 挂挡迟滞 | 元件充油/主压调节/泄漏，或机械接合与请求许可原因 | 变速箱型号、指令/许可、实际档域/转速、符合原厂边界的对应油路证据 | 某型号正常的控制或温度响应、发动机/安全许可可竞争，禁止按通用文稿指定换 ATF |
| `DRIVE_LOSS` 无驱动 | 离合/制动实际约束未成立、传动输出/半轴或轮端外部断路、供流限制 | 已核实的传动机械连通性与档域、对应总成油路、驱动桥/制动/发动机竞争原因的独立事实 | “挂 D 不动 = 必换变速箱”不是有效推断；不触发高风险路试 |
| `TCC_SHUDDER` 锁止抖动 | 变矩器离合器摩擦/供排油调制或正常锁止过渡 | OEM 锁止允许工况、**TCM 目标与实际滑差**、真实热负载/输入扭矩环境 | 不把变矩器液力耦合滑差当每时每刻机械故障；CVT 也可有变矩器 |
| `HOT_ONLY` 热后异常 | 介质/密封/泵与内部泄漏、冷却供流/热负荷、保护标定差异 | 同一 OEM 型号的实际热条件、真实液压支路与冷却流量证据、工况/软件对应 | 一次主油压正常并不能证明冷却/润滑正常；不能照搬陌生型号油温阈值 |
| `ENGINE_OR_ROAD_MIMIC` 外部相似现象 | 发动机供扭波动、差速器/半轴、制动拖滞、轮胎附着/道路 | 与 OEM 动力总成和驱动配置匹配的真实数据类别 | 先排除其他系统的可能性，不能把广告字段 `Automatic` 作为总成鉴定证据 |

**验收时必须区分四个“同名但不同证据对象”**：
1. `TCM_COMMANDED_PRESSURE`：控制器请求的目标，不能当作实测油压；Sonnax 的诊断教程特别指出有些诊断仪显示的是命令值，不是压力传感器测量值。
2. `OBSERVED_LINE_PRESSURE`：与车型适用安全程序绑定的主油压数据，仍不足以证明各离合支路、TCC 和冷却润滑供流。
3. `OBSERVED_BRANCH_OR_COOLER_FLOW`：若存在有资格的原始证据，才能分别限定支路充油、变矩器循环、冷却和润滑；不能把“不知道”写成“正常”。
4. `ACTUAL_CLUTCH_AND_OUTPUT_STATE`：机械约束确立、转速比例和输出条件，不由阀体/电磁阀请求单独保证。

在没有真实、合法、可复现的来源与专业测试收据时，以上项全部 `UNKNOWN`；这不是要求用户自行测量。

## 3. 防止单故障码到单零件的假阳性

| 推断捷径 | 为什么会产生错误维修决策 | 可接受的研究级表述 |
|---|---|---|
| DTC 涉及换挡控制 ⇒ 更换电磁阀 | 控制命令、供电、线路、阀体液压、机械元件和真实软件策略之间可能多层解耦 | “在适用车型规则下，该异常可能属于控制/执行路径；**尚需独立证据，禁止推断特定更换**” |
| 主油压看似正常 ⇒ 所有离合器/冷却正常 | 油压与泵流量、支路油腔和冷却/润滑流量并非相同量 | “主压证据仅限定被测回路/状态，未覆盖分支依然 UNKNOWN” |
| 热后变差 ⇒ 换油就能修复 | 热负载、控制策略、密封/泄漏、摩擦/冷却均可能参与 | “油液状态只是竞争候选，需要车型匹配的真实证据” |
| 某 4L60-E 资料证明具体球阀泄漏 ⇒ 所有 4AT 同病 | 专业资料限制于特定总成/代际，真实离合油路可能不同 | “该文只支持液压调制/泄漏可导致特定失效机制” |
| 加速无力 ⇒ 变速器滑差 | 发动机负载、车轮制动/附着与驱动轴均可能产生相似主诉 | “外部竞争原因未排除” |
| 使用某款 ATF 或维修升级件得到一个案例改善 ⇒ 所有型号可互换 | 零件/油液适配通常由变速箱型号、生产时期及 OEM 指令限制 | “没有合法匹配的 OEM 来源及专业确认，不作维修选择” |

本稿不提供现实施工决策（`REPLACE_PART`、`ADJUST_PRESSURE`、`FLASH_TCM`、`ROAD_TEST` 等）；只描述知识从假说到有效证据的条件。

## 4. 误修成本/安全风险为何必须与知识适用性绑定

不需要编造缅甸故障率或价格，仍可以明确识别风险路径：

- **错误总成分类**：传统 AT 与 CVT/DCT/e:HEV 的传动机理不同；错误油液/零件/诊断方法可能导致部件损坏或错误安全决策。
- **错误因果归因**：按报码或客户描述指定阀体、离合器，可能忽略真实控制、供流、驱动桥、发动机或制动因素，造成“已经更换但故障仍在”，甚至使原故障扩大。
- **忽略温度与供流**：在不理解主压与变矩器冷却/润滑支路区别时，可能误判已完成维修验收。
- **软件和学习程序差异**：某厂家/年代的 TCM 学习、重置/适配程序不能跨总成通用。只有匹配原始资料及专业安全资格才可能执行。
- **拆装与压力/车辆运动风险**：传动总成、旋转/高温油液和行车有固有安全风险，本稿不授权现场操作。不能把“安全未知”转成“可试一试”。

`UNCERTAIN_ECONOMIC_IMPACT`、`MYANMAR_SHOP_RATE`、`MISREPAIR_FREQUENCY`：均为 `UNKNOWN`，不得给虚构金额或排名。

## 5. 不完整来源的合法终态及返工传播

以下任一条件均不能进入“确定维修方案”：

- `TRANSMISSION_ID_UNKNOWN`：无法确认车辆真实变速器类别、型号/制造版次。
- `OEM_EVIDENCE_MISSING`：没有与实际总成、地区、软件相符的完整原厂适用证据。
- `CONFLICTING_SOURCE`：厂商、型号、年代信息冲突，需要进一步来源消歧。
- `OBSERVATION_MISSING`：只有主诉/报码而缺可核查的实际工况与证据（不要求本稿产生测量）。
- `SAFETY_PREREQUISITE_UNKNOWN`：具体操作的机械/高温/带电/车辆运动等专业安全许可未知。
- `UPSTREAM_STALE`：STR/FUN/FAIL 关键机理发生有效变更而本稿未受影响审。

默认结论是 `UNDETERMINED / DEFER_FOR_MATCHED_OEM_EVIDENCE`，不是假装“最可能坏的是某个零件”，也不是声称已经完成维修。

## 6. 车型适用性与与现有知识 DAG 的关系

[Toyota Probox/Succeed 发现与传动差量](../../../series/myanmar/toyota/probox/transmission-applicability-delta.md) 和 [Honda Fit/Jazz 传动差量](../../../series/myanmar/honda/fit/transmission-variants-delta.md) 提供**日本原始产品家族的版本差异**；它们未核验任何缅甸特定 VIN 的自动变速器、维修案例或技术改型。不能把 Sonnax 的 GM 4L60/4L60-E 或 Aisin AW 55-50/AF23-33 示例硬套到 Probox/Fit。

本稿继承了已独立限定接受的 [STR-AT](./structure.md) → [FUN-AT-PATH](./power-path.md) + [FUN-AT-HYD](./hydraulic-control.md) → [FAIL-AT](./failure.md) 物理框架，**但这些是研究级来源与知识结构资格，不是 OEM 专业事实签署**。如果某个上游后来被 P1 REWORK、真实规则变化或适用范围缩窄，应依受影响边标记本稿 `STALE` 并增量修复，不把旧 ACCEPT 当新事实。

## 7. 原始专业文献与来源边界

| 来源 | 可支持的研究结论 | 明确不支持 |
|---|---|---|
| [Sonnax, Transmission Diagnostics Using Pressure Gauges](https://www.sonnax.com/tech_resources/314-transmission-diagnostics-using-pressure-guages) | 诊断仪命令主压和传感器/表计实际压力可能不同，需区别对应回路；仅参考概念 | 将任何非匹配总成的数据作为 Toyota/Honda 维修阈值 |
| [Sonnax, Hydraulics Fundamentals I: Main PR Valve Line-Ups](https://www.sonnax.com/tech_resources/674-hydraulics-fundamentals-part-i-main-pressure-regulator-valve-line-ups) | 油泵供流与调压/阀芯平衡及支路供流的区别 | 所有 AT 调压阀/泵位置相同 |
| [Sonnax, Anatomy of a Transmission: Oil Flow in Pump, PR, Converter, Cooler & Lube Circuits](https://www.sonnax.com/tech_resources/131-anatomy-of-a-transmission-oil-flow-in-the-pump-pr-converter-cooler-lube-circuits) | 型号限定的变矩器/冷却/润滑分支以及主压不足以代表全部供流 | 一份流路图适配所有 AT |
| [Sonnax, Hydraulics Fundamentals II: Accumulators & Shift Feel](https://www.sonnax.com/tech_resources/675-hydraulics-fundamentals-part-ii-accumulators-shift-feel) | GM 4L60/700-R4 的液压蓄压/换挡舒适性可证伪机制案例 | 缅甸车型的真实失效部件 |
| [Sonnax, AW 55-50 / AF23-33 Diagnosis and Valve Body](https://www.sonnax.com/tech_resources/196-aw-55-50-af23-33-diagnosis-and-valve-body-information) | 其他 AT 总成的控制/油路/机电差异说明必须核对型号 | 其改装、步骤或规格可自动用于 Probox/Fit |

**交付完成标准**：这是一篇把“候选故障→鉴别信息→反证→可判定/不可判定终态”结构化的非操作性研究 Markdown，仍须其它对话 Reviewer 对当前 Exact Blob 进行限定内容质量审核；其通过也不意味着某辆车已经诊断或修好。
