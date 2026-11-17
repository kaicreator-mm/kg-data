# 汽修知识生成范围与证据边界 — v0.4.1 初始工作切片

> MAIN: [parts-system #61](https://github.com/kaicreator-mm/parts-system/issues/61) | CONTROL: `C-SCOPE` | STATUS: `DRAFT_DELIVERED__REVIEW_PENDING`
> 本文是规划范围声明，**不是已核实 OEM 车型分解、已生成知识或完整覆盖声明**。

## 唯一领域与阶段

唯一专业领域：汽车维修与诊断；当前仅生成可阅读的原创专业 Markdown，不做 LinkML/YAML/JSON-LD/CSV、来源逐 Claim 专业审核、正式 N3 认证、生产诊断操作软件。

本轮探索**两个明确的非全域参考架构切片**：

1. `ARCH-ICE-GAS-LIGHT`：常见轻型乘用燃油车的**通用汽油机**基础架构；自动变速器专题**仅选择有液力变矩器、行星齿轮机构、液压执行元件的传统液力行星齿轮 AT**。这是教学/研究概念，不宣称覆盖某 OEM 全部变型或自动变速器的所有类别。
2. `ARCH-BEV-LIGHT`：通用轻型纯电车概念架构；首轮只研究高压系统组成、保护机理与风险、与热管理/制动再生的协同概念；HEV/PHEV/增程、e-CVT、CVT、DCT 作为不同架构 `OUT_OF_INITIAL_SLICE`，不是错误地标 `NOT_APPLICABLE` 于整个汽修领域。

共享/跨架构候选：常规摩擦制动与 ABS/ESC、转向悬架、车轮轮胎、低压电气/网络、热管理、车身/被动安全；是否适用到具体车型与架构按生成内容分别界定。

## 来源与可信度边界

- ASE A1–A9、AIAG/VDA 结构→功能→失效分析、SAE J2012 的 DTC 与 OEM 整车/维修资料用作组织参考；任何单一标准都不是完整汽车结构的权威唯一划分。
- Drive Books 已可见书目录与 `kg-data/books` 既往候选只构成 `TOC_ONLY` / `MODEL_GENERATED_UNVERIFIED` 研究线索，绝不冒充阅读未读取的正文、真实 OEM 维修程序或测量数据。
- 安全关键制动/高压/气囊，只能生成非车型专用、非操作性的机理/风险/证据判断；无 OEM/技能依据不能编造实操高危步骤和限值。
- 未明确的车型、版次、地区、维修统计或具体构造必须标 `UNKNOWN`。暂时切片外领域为 `OUT_OF_INITIAL_SLICE`，不能被错误换算为 N/A 或“已覆盖”。
- 版权处理以真实复制/传输行为为准；知识与事实可原创重述，不向公开数据仓贴原书受保护长文、PDF 或插图。

## Scope 交付与接受条件

- [x] 汽修单领域；第一阶段 Markdown-only；明确两个非全域参考架构
- [x] 传统液力行星齿轮 AT 与 CVT/DCT/e-CVT 等明确区分
- [x] 输入可见范围、专业事实未验证、安全操作边界与未知策略
- [ ] **独立计划 Reviewer** 根据当前 Blob 审阅后才可标 `ACCEPT_SCOPED_SCOPE_ONLY`
- [ ] 任何具体 OEM 结构/数据还未获得专业验证

本文件可在后续发现车型/用途差异时增量扩展版本。修改已审核范围需重新限定审核受影响内容。