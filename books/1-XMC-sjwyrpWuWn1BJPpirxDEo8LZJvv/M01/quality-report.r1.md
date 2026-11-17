# M01 R1 自检报告

- 实际新生成：5 条 KnowledgeRecord、10 条有向关系；M03 历史 19 条未重写。
- 生成来源：已保存的真实目录主题“模块一 流体力学基础知识”；**不主张原书正文包含上述技术断言**。
- ID 唯一性：5/5；关系端点存在：10/10。
- JSON.parse：本运行内执行 PASS；CSV 行列引号转义由同一内存记录导出；YAML 独立解析器、LinkML CLI、JSON-LD RDF parser、独立专业审核：NOT_RUN。
- 公式检查：F=pA、Q=Av、P=ΔpQ、Q≈Cd A sqrt(2Δp/ρ) 均明确单位、前提和失效边界；实际车型参数未提供。
- 所有专业事实：MODEL_GENERATED_UNVERIFIED；正式 qualified=0。
- P0=0（仅自检范围），P1=0（仅自检范围），P2=2（需要独立技术来源核验；LinkML/RDF CLI 未运行）。
