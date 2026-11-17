# #61 首批知识生成预检与审核待办 — R0 / 2026-11-18

> **角色**：Integrator/原结构稿 Writer 的准备性检查；**不是其它对话独立内容质量审核**。一切技术事实保持 `MODEL_GENERATED_UNVERIFIED`。  
> **唯一范围**：v0.4.1 `ARCH-ICE-GAS-LIGHT`、`ARCH-BEV-LIGHT` 的四个首批 `STR-*` Markdown。  
> **计划门禁**：PLAN Blob `1df1f116a9f4e1effc46840aa4ec57be1289b6cf` 已 [ACCEPT_SCOPED_PLAN_READY](https://github.com/kaicreator-mm/parts-system/issues/61#issuecomment-6954464408)。本文件不把准入视为专业知识审查通过。

## 1. 四份实际可回读产物（统一使用当前 Blob）

| Task | 文件 | 生成状态 | 当前 Blob | 预检范围结论 |
|---|---|---|---|---|
| `STR-ENG-LUBE` | `topics/engine/lubrication/structure.md` | GENERATED_REVIEW_PENDING | `ff103f4cfd948534be5ca2b9413128aee502987f` | 结构、油路、关键部件、变型、跨系统连接完整度较好；**显式 UNKNOWN P2 已补充 R2**；独审未做 |
| `STR-AT` | `topics/transmission/automatic/structure.md` | GENERATED_REVIEW_PENDING | `ed2b997ca164d98e74cf72ecb393aca86a553d20` | 液力变矩器/行星结构/液压执行和传感接口有实质内容，已排除 CVT/DCT/e-CVT；独审未做 |
| `STR-BRK` | `topics/braking/structure.md` | GENERATED_REVIEW_PENDING | `e231eda16a8d799d891e7604bee41437af29afb6` | 摩擦/液压助力/电液制动及 ABS/ESC/再生协调结构有实质内容，含风险界限；独审未做 |
| `STR-HV` | `topics/electrified/high-voltage/structure.md` | GENERATED_REVIEW_PENDING | `472127e80e95f022dc512b0c635b7a63282c94d2` | BEV 电池/BMS/配电/电驱/充电/热管理接口有实质内容，安全操作与资料未知界定清楚；独审未做 |

**检查证据**：直接从 GitHub 最新文件 fetch 回读，四个文件均有实体正文、车型或架构边界、关键部件关系、可见来源/参考、后继任务和未验证说明；非空 Markdown 结构成立。未执行实验台架、实车检测、形式化工具、所有外链逐条 fact-check，不能报告 `FACT_VERIFIED` 或 `ACCEPT_SCOPED_GENERATION_ONLY`。

## 2. 预检发现与处理（P0/P1/P2 只是前置质量候选，不是独立审核裁决）

| 候选等级 | 对象 | 缺陷/风险 | 处理 |
|---|---|---|---|
| P2 — 已补齐 | `STR-ENG-LUBE` | 旧 R1 只有中文“未知/缺口”，无显式 `UNKNOWN` 状态与对车型/OEM 判断影响的成组记录；覆盖账本容易把通用知识误读成实车已覆盖 | 同一原 Writer R2 增量补充了结构适用、滤清/旁通、油泵调压、传感器测点、OEM 参数、干式油底壳等 `UNKNOWN`；新 Blob `ff103f...`，需以**新版本**独审 |
| P2 — 本轮修正 | `C-COVERAGE` / `PRIORITY` | 其它三个 Writer 已经真实 RELEASE，但共享账本仍将其结构 S 标为 OPEN/READY，造成统计和调度假滞后 | Integrator 以真实 Commit/Blob 修正四行状态，保留 F/X/R 未完成 |
| P2 — 待独审关注 | `STR-AT` | 示例来源跨 GM 4L60、ZF 8HP，需核查每个案例是否保留**不同型号适用性**，不得扩张成全 AT 通用组成 | 独立 Reviewer 检查具体断言/文档范围；若发现断言错误，由可认领 Writer 做限定修复并转新 SHA |
| P2 — 待独审关注 | `STR-BRK` | 电液 one-box/two-box、再生融合与机械/液压后备因供应商/车型不同，需核查没有默认同一种失效保护或维修方式 | 同上；不因缺车型级制动操作步骤判其结构任务失败 |
| P2 — 待独审关注 | `STR-HV` | 公开 BEV 的 AC/DC 充电和高压配电概念图简化较多，需核查其**不是**隐含可执行接线/隔离流程 | 同上；遇可操作危险断言应升级 P1/P0 并立即修复 |

**目前没有可由本预检证实的 P0 或 P1；这不是“四份质量审核 PASS”的断言。** P2 审核关注项尚不等于确证缺陷。材料是否专业正确必须由独立 Reviewer 检查原始技术来源及具体断言。

## 3. 验收不能互相偷换

1. `GENERATED_REVIEW_PENDING`：已写入、Markdown 可读、候选正文非空，范围/深度看起来具备审查价值；**不代表已合格**。
2. `ACCEPT_SCOPED_GENERATION_ONLY`：其他对话独立审当前 EXACT Blob，没有阻断性 P0/P1 且 P2 妥善登记；仅认可本轮内容质量、结构/深度、明显错误控制。
3. `REWORK`：Reviewer 给出 P0/P1/P2 的确定缺陷与影响范围，原 Writer 或新认领唯一 Writer 做最小补充/修正，保留未变化的证据，提交新 Blob 并请其它对话增量复审。
4. `MODEL_GENERATED_UNVERIFIED`：即使上一步通过，仍不是 OEM 技术事实、来源逐 Claim 验证、维修操作授权或 DKE N3。

## 4. 后续真正 READY 的任务与优先级

- 四个 **独立内容质量审核**：分别检查 `STR-ENG-LUBE@ff103f...`、`STR-AT@ed2b...`、`STR-BRK@e231...`、`STR-HV@472127...`，不同对话领取不相交 Review Claim；Review 不改生成文件。
- 基于真实结构上游，`FUN-ENG-LUBE`、`FUN-AT-PATH`、`FUN-AT-HYD`、`FUN-BRK`、`FUN-HV` 都可作为后继**候选**；如果独立 Reviewer 发现上游关键错误，应先修复受影响上游、将后继标 `STALE`，禁止错误传播。
- BREADTH 必须继续覆盖 `STR-LOWV`、`STR-STEER-SUSP`、`STR-THERMAL` 等，避免四系统试点被误称汽车系统全集；全部真实故障频率依然 `UNKNOWN`。
- 本轮只更新现有已发现任务状态；未增加新 DAG 节点，不冒充已完成动态全图插入验证。

## 5. 审核接收规则

每个 Reviewer 需读取当前文件和 Writer RELEASE 提交、实际出版方公开技术资料及未核实声明。明确 `P0/P1/P2 / verdict / reviewed commit & Blob / applicable scope` 写回 #61。**没有 Reviewer 签收就保持全部四篇内容质量 Pending**。R2 Engine 旧审核目标 Blob `b43057...` 必须认定为 STALE，不得拿来签新稿。

---
*本预检只为首轮增量整改与并行审核分派，不能替代后续正式专业事实验证。*
