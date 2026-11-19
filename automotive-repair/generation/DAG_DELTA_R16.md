# 汽修知识生成 Task DAG · R16 下一批八条跨系统独立增量

> 主控：[parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) · 数据仓：`kaicreator-mm/kg-data` · OUTPUT_LABEL：`PARTS_AUTOREPAIR_V054_R16_DAG_DELTA_PROPOSAL_W1`  
> **当前状态：`PROPOSED__INDEPENDENT_DELTA_PLAN_REVIEW_PENDING`；本文新增八节点全部 `NOT_ADMITTED`。** 作者只负责提出 Task DAG，不能自行批准、分派或生成本提案内容。继续保持第一阶段 `Markdown-only`、`MODEL_GENERATED_UNVERIFIED`、`OEM/VIN/N3=0`。

## 1. 从真实交付出发，不重开已审工作

- 既有图：`PLAN.md`、`VEHICLE_SERIES_DAG_R1.md`、`SERIES_FAMILY_DAG_R1.md`、`DAG_DELTA_R9.md`，共 **54 个已准入 Task 节点**。本提案不覆盖、撤销或修改任何旧计划/知识 Blob；R9 独立审核 [#7002477265](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7002477265) 与放行 [#7003606901](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7003606901) 原样保留。
- R9 六个新增叶知识 **六篇均真实生成且限定质量独立接受**：[R16 四篇集中审核 RELEASE](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7009726587)、[R15 前两篇 RELEASE](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7005136682)。两轮审核均仅为知识生成质量，不是原厂故障认证。
- 旧 `PLAN.md` 已批准但尚未生成的 `REP-BRK` 和 `FAIL-HV` **可按各自原有合法前置立即并行认领**，无需经过此新计划；其独占输出分别为 `topics/braking/diagnostic-repair.md` 与 `topics/electrified/high-voltage/failure.md`。
- 新近 `REP-ENG-LUBE` 已由原旧 `PLAN.md` 入场并生成，Commit `079287ddfa9e8faf521b20ac87108ca305eca962` / Blob `a0df6804853ac7638e2d9045b30f2cb14393d41d`，[Writer RELEASE #7009858172](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7009858172)，**独立内容审核待做**。它也不是 R16 新任务。
- 本提案编写时累计 **36 篇实际生成 / 35 篇限定接受 / 1 篇独立审核待完成**；该数是快照，未来以新 GitHub Claim/Commit/Blob/REVIEW 实时重算，不是全领域知识覆盖率。

**扩张理由**：当前已形成热管理、低压电气、转向悬架、传动轴/差速、CVT/HEV 及发动机进排气、车身安全的结构或功能前置，但多个系统止步于“由什么组成/正常怎么运行”；维修知识体系需要在**安全边界内**继续把结构→功能→失效→竞争诊断串起。新增八个**独立叶**既补广度也补维修深度，不对所有车型发固定配额。

## 2. 八个具体 Task、直接知识前置与独占 Markdown 写集

所有八个新节点的共同有效前置：`C-R16-PLAN-REVIEW=ACCEPT_SCOPED_DELTA_PLAN_READY` **AND** `C-R16-DISPATCH=ADMITTED` **AND** 表中的上游真实当前 Markdown 与原内容质量审核有效 **AND** 独占 Writer Claim 二次仲裁成功。新路径的具体一跳知识前置如下，八个任务**不互为前置**，能够独立开工与流水线调度。

| 新 Task ID | 已有上游、提案编写时 Exact Blob | 唯一新增 Markdown 路径（相对本目录） | 目标语义与验收 |
|---|---|---|---|
| `FUN-ENG-AIRFUEL` | `STR-ENG-AIRFUEL@a0a5dceadb22a1588876d1001e5a0a0451709469`；[已审 #7002551083](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7002551083) | `topics/engine/air-fuel-emissions/function.md` | 汽油机进气、PFI/GDI 燃油供给、点火/燃烧、氧反馈与排气后处理如何按工况协同；输入→机理→输出，区分控制命令/物理结果、闭环许可、催化温度与反例，不填造喷油/点火标定 |
| `FUN-BODY-SAFETY` | `STR-BODY-SAFETY@8b9ec87fa448110e449c0b6233b6b812d8e9120a`；[已审 #7002553385](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7002553385) | `topics/body-safety/function.md` | BCM、照明、门锁车窗、低压/车内通信、座椅安全带和被动约束 SRS 的正常职责、指令与真实动作/反馈；按配置适用并记录危险未知，**绝不**提供气囊引爆/检测/旁路、碰撞阈值和拆装步骤 |
| `FAIL-LOWV` | `FUN-LOWV@8d9f33e77445cc84f1e0952ff547da87a51341a2`；[已审 #7005120636](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7005120636) | `topics/electrical-low-voltage/failure.md` | 起动许可 vs 电池供流、ICE 充电 vs BEV DC/DC、电源支路/回流/熔断 vs 唤醒/网关/CAN/LIN 的失效机理、症状与竞争假设；无车系针脚/搭电/高压操作 |
| `FAIL-STEER-SUSP` | `FUN-STEER-SUSP@3975342848e3f0883289dbfb73c81be50f331d5c`；[已审 #7005121662](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7005121662) | `topics/steering-suspension/failure.md` | EPS/HPS/EHPS 电/液/机械失效竞争原因，弹簧/阻尼/球节/衬套/轮胎/几何及附着造成的方向、噪声、姿态/稳定性表现和反例；安全 STOP，无弹簧拆装、转向路试或四轮定位数值 |
| `FAIL-DRIVELINE` | `FUN-DRIVELINE@2a61e9eb0027194db141b302b98af19e246a1fb8`；[已审 #7009685420](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7009685420) | `topics/driveline/failure.md` | 终传齿面/轴承、开差速/LSD/锁止、半轴 CVJ 防护/润滑、AWD 耦合与电控许可失效；区分牵引不足、轮胎打滑、旋转噪声、振动/冲击，不把正常轮速差当缺陷 |
| `FAIL-THERMAL` | `FUN-THERMAL@f366249ef942a6fbb03e8621ebaf149a018fc370`；[已审 #7009684524](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7009684524) | `topics/thermal/failure.md` | ICE 冷却/机油、HVAC 蒸汽压缩、BEV 电池/电驱/客舱换热的温度/流量/控制/传感竞争机理，工况与反例；分冷却液与制冷剂、热泵选配，无制冷剂/高压现场工序 |
| `REP-CVT-FAMILY` | `FAIL-CVT-FAMILY@5409cdafd8763f7ce4c06d0df2a7ed8f37c41214`；[已审 #7009686309](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7009686309) | `topics/transmission/cvt/diagnostic-repair.md` | 钢带/链夹持、变比执行、油压/温度、起步离合/变矩器、传感/控制与下游传动的鉴别证据和误修代价；不把 CVT/DCT/行星 AT/e:HEV 混为一类，无换油压测/路试诱发/刷写工序 |
| `REP-HEV-FAMILY` | `FAIL-HEV-FAMILY@886a6c1e5c0223a18942048165084d21ac86b997`；[已审 #7009687202](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-7009687202) | `topics/electrified/hybrid/diagnostic-repair.md` | IMA+CVT、i-DCD+7DCT、e:HEV 双电机/直驱的请求→许可→实体扭矩/再生路径证据与维修决定边界，历史召回仅按范围引用；保留高压与制动 STOP、具体 VIN 资格 UNKNOWN |

**写集检查**：八个新路径在本提案写入前均真实 GitHub 404，八个源路径均真实回读，与上表八个 SHA 一致。若未来某个新 Writer/资料版本先改变这些事实，调度器必须单任务重新仲裁，**不重跑与之无关七条**。

## 3. 全图无环与实际并发

新增八条直接知识边仅从既有 54 个 Task 指向新叶子节点：

`STR-ENG-AIRFUEL → FUN-ENG-AIRFUEL`  
`STR-BODY-SAFETY → FUN-BODY-SAFETY`  
`FUN-LOWV → FAIL-LOWV`  
`FUN-STEER-SUSP → FAIL-STEER-SUSP`  
`FUN-DRIVELINE → FAIL-DRIVELINE`  
`FUN-THERMAL → FAIL-THERMAL`  
`FAIL-CVT-FAMILY → REP-CVT-FAMILY`  
`FAIL-HEV-FAMILY → REP-HEV-FAMILY`

此增量不添加新→旧/新→新回边，原 54 节点 DAG 如果无环，在其末尾添加八条新叶后仍无环。**只有经独立计划审与合法 Integrator 准入，图才由 54→62；在此之前仍是 54。** 新节点仅取已有生成知识的直接上游，不迫使所有 STR、FUN、FAIL 全局完成。

若有八个不同 Writer 会话，八条可同时进行；资源不足时优先保持**系统广度**（进排气/车身安全）与**维修深度**（CVT/HEV）各至少一个槽位，余量交给低压、热管理、转向、传动真实重要缺口。四篇 R9 已审上游不再重做；原已有的 `REP-BRK`、`FAIL-HV` 与本八条不交叉写集，按旧 DAG 合法独立启动。全域系统遗漏及后续任务从 `COVERAGE.md` 动态发现，不把八节点变成固定知识类型配额。

## 4. 最小独立审核与准入步骤

1. **另一个非本作者对话**对新 `DAG_DELTA_R16.md` 当前 Exact Git Blob 独立审八个 ID、单一输出路径、当前上游 SHA/接受证据、合法安全边界、相对链接、无环及基础/车型架构差异；只写回 `ACCEPT_SCOPED_DELTA_PLAN_READY` 或 `REWORK` 和 P0/P1/P2，不编辑此源、不自建 Writer 内容、不提升 N3。
2. 若通过，**非本计划 Reviewer 的 Integrator** 最小复核当前 HEAD、活跃 Claims、八上游内容身份及八目标路径独占，写入 `C-R16-DISPATCH=ADMITTED`；只有被准入的具体 READY 节点才可 Writer Claim。
3. Writer 在新对话或独立合法工作会话按各自唯一任务二次仲裁后，只写**一个** Markdown 文件；明确问题、专业机理/因果、真实来源范围、不同竞争解释、车型/工况条件、反例、UNKNOWN 与安全 STOP；Commit→Exact Blob 回读→RELEASE；其它对话独立审新增内容质量。
4. 遇到真正有问题的 P0/P1，原 Writer 最小修复后只复审受影响内容。无变化的旧计划/31+ 已接受文章绝不因新增节点而重审。生成通过≠OEM/VIN/专业事实/N3 通过。

## 5. 停止条件、未来扩张和质量尺度

不使用预设文章字数、节点数和文档数冒充完整汽车维修知识。每次新增任务的目标是解决一个明确的**未回答技术问题**，且能说明与已有文章的真实信息增量。低压、制动、SRS、转向/悬架、高压与制冷剂的危险操作必须限制为条件机理/证据与专业移交而非通用操作流程。缅甸 Probox/Succeed、Fit/Jazz 的年份、底盘、发动机、变速箱、配置和真实故障率依原始 OEM/市场资料进一步分层，缺证据持续 `UNKNOWN`。

最终阶段性 closeout 仅报告：哪些明确架构/系统/部件与故障问题获得实质性知识、还有哪些重要 OPEN、什么已审核及哪些仍为模型未证实。新计划通过前绝不宣称 **62 节点已生效** 或 **8 篇已生成**。
