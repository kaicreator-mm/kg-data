# M03 r2 self-QA

- 原创专业候选：8；新增有向关系：16；r1原有12条不重写。
- 8个新ID唯一；关系目标均指向本批8个或已存在r1的12个ID：PASS（生成前内存检查）。
- JSON-LD JSON.stringify/parse：PASS；CSV通过确定性引号转义生成。
- YAML canonical 使用 JSON（YAML 1.2合法子集）；专用YAML parser：NOT_RUN。
- CSV独立解析器、RDF parser、LinkML CLI、独立专业Source-First/OEM：NOT_RUN。
- 本批只补3.9及部分3.1/3.3/3.5/3.7/3.8，其他细分主题和全书未完成；整书IN_PROGRESS。
- 所有命题均 MODEL_GENERATED_UNVERIFIED；仅实际目录主题索引，无原书正文证据、无OEM阈值。
