# Automotive book knowledge (canonical-derived)

Source: `book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8`

Review: `GENERATED_REVIEW_PENDING`

This is an original summary, not a reproduction of source text; scope and evidence follow each claim.

- **feeds_power_through**: 蓄电池正极经 FL MAIN 3.0W 主熔丝向起动机及全车配电母线供电（printed 3 配电图与 printed 4 启动/充电图一致）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p6:e4, book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e4.  
- **feeds_power_through**: 蓄电池经 120A ALT 熔丝向点火开关 AM1/AM2 支路供电。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e1, book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p6:e1.  
- **has_specification**: FL MAIN 主熔丝额定规格标注为 3.0W。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p6:e4.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **has_specification**: 交流发电机主熔丝额定电流 120A。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p6:e1.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **has_specification**: ST/AM2 熔丝额定电流 30A，向点火开关 AM2(针5) 供电。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e1.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **has_specification**: AM1 熔丝额定电流 7.5A，经 O 色线向点火开关 AM1(针4) 供电。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e1.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **has_specification**: GAUGE NO.1 熔丝(IG 电源)额定电流 10A，经 R/O 线向发电机 IC 调节器 IG 端供电。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e6.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **has_specification**: GAUGE NO.2 熔丝(IG 电源)额定电流 7.5A，经 GR 线向充电指示灯 IG2 侧供电。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e6.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **has_terminal**: E23 点火开关端子：AM1(针4,进线O)、ACC、IG1、ST1(针3,出线GR)、AM2(针5,进线B)、IG2、ST2(针7,出线L)。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e1.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **connects_to**: 点火开关 ST2(针7) 经 L 色线、AE7 针2 接启动继电器线圈；ST1(针3) 经 GR 线、[3F][3E] 接 EA1 针6。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e1, book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e3.  
- **enables_starting_for**: M/T 车型：A22 离(高)合器启动开关串入启动继电器线圈回路（G 色线）；A22 名称首字在 150/300dpi 下离/高字形相近，按丰田 M/T 标准配置判读为离合器启动开关，保留 PARTIAL。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e2.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","transmission":["M/T"]}`  
- **enables_starting_for**: A/T 车型：P/N 位置开关矩阵(L/B/P/N)经 C1(A)/B(B) 中继线连接器(9A:2GR-FE/5B:2AZ-FE)参与启动使能回路；CA2 针8→Y(A/T)→变速器 ECU<7-23>。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e7.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","transmission":["A/T"]}`  
- **has_terminal**: 启动继电器端子：线圈 5/1，触点 3/2；触点侧 GR 与 SB 两线的输入/输出方向在分块边缘未能完全区分（PARTIAL_UNCONFIRMED，不作诊断结论）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e2.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **receives_power_from**: 起动机(C3(A)/C29(B)/D1(C)) B 端经 B 色线、C 接点、FL MAIN 3.0W 熔丝接蓄电池正极；磁性开关由 CA1(针1) B 线（A/T:A / M/T:B）供电；电机壳体接地。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e4.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **has_subcomponent**: 起动机包含磁性开关（电磁开关）与 M 电机两部分（图示）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e4.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **has_subcomponent**: 发电机内置三相定子绕组与 6 管整流桥（图示），整流输出经 B 端（针1:A=2GR-FE / 1:B=2AZ-FE）以 B 色线并入 FL MAIN/蓄电池母线。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e5.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **has_subcomponent**: 发电机内置 IC 调节器，端子 B/M/S/IG/L（针 B; M=3B; S=1B; IG=2B; L=4B）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e5.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **connects_to**: IC 调节器 M 端(针3) 经 L 色线(2AZ-FE)、[3B] 接线位置接发动机 ECU<8-9>。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e6.  
- **connects_to**: IC 调节器 IG 端(针2) 经 R 线、[2B]→10 CA2→14 EA1→16 IH 接 10A GAUGE NO.1(IG) 熔丝。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e6.  
- **connects_to**: 充电指示灯一端 IG2(针13) 经 GR 线、[3Q][3G]、[12 IG] 接 7.5A GAUGE NO.2(IG)；另一端 CHG-(针23) 经 Y 线、[4B] 接发电机 L 端(针4)。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e6.  
- **connects_to**: 发电机 IC 调节器 L 端经 Y 色线接组合仪表 F1(A)（充电指示灯 CHG- 侧）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e6.  
- **receives_signal_from**: 发动机控制系统经 CA2(针7)→W(A/T)→V(蓝箭头=传感器/反馈) 与调节器/发电机相关信号相连（图例颜色定义反馈方向）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e7, book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p6:e6.  
- **connects_to**: 点火电路：四个点火线圈 C11/C13/C12/C14（黑色4针）1=+B(BR 母线)、4=GND(W-B 经 C4 接地)；IGT1/2/3/4（W/G-R/G/LG，绿色执行器信号）与 IGF（W-L，蓝色反馈信号，图例定义）汇合接发动机控制模块<8-10>。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p6:e3, book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p6:e6.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **connects_to**: C16 静噪滤波器(点火右) 针1 接 IGF(W-L) 汇流线（图示）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p6:e3.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **feeds_power_through**: 配电：30A 主电喷装置(Y)→[12 1E]→电子控制喷油装置继电器→[6 1B]→B→15A 2号电喷(R)/10A 3号电喷(GR)；15A 喷油(点火)熔丝经 7→10 B 接线位置向点火线圈 +B(BR) 母线供电。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p6:e3, book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p6:e2.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **has_terminal**: 右后除霜继电器端子 4/5/3/1/2，关联 W-B/Y/W/G/V 色线与 50A 右后除霜、10A 后视镜加热熔丝。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p6:e2.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **identifies**: 图内接线位置代号（1A/1B/1C/1E/1F/1G/1I/3E/3F/3G/3Q/12/16/IH/FE3 等）按图集识读页的代号体系标注接线盒/中继位置。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p4:e1, book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p6:e1.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **identifies**: 中继线连接器代号 A41(A)/A42(B)、C1(A)/B(B) 用于跨区导线中继（printed 4）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e7.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **uses_wire_color**: 配电/启动/充电回路接地采用 W-B 色线，接地点含 A1、A3、C4 及起动机/蓄电池壳体接地（图示）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e4, book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p6:e3.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **connects_to**: 变速器 ECU<7-23> 经 Y(A/T)/L-B/L(2GR-FE) 与 P/N 位置矩阵相连（printed 4）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p7:e7.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","transmission":["A/T"]}`  
- **documented_in_analysis**: 分析栏列出整车配电说明与编号(1)-(16)熔丝供电路径（可读部分：40A 冷凝器风扇/发电机励磁/50A 主风扇/40A 散热器风扇/50A 加热器/30A ABS 2号/50A(ABS 1号?)/25A 1号门/15A 右前雾灯/7.5A OBD/30A 电动座椅/25A 电动窗/30A 天窗/7.5A 空调/10A 制动灯），右缘裁切尾字不全，完整文本待原图复核。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:144Tg2v0fgnu-b_n6hAXE8UMVtUUyfif8:ev:p6:e5.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
- **expected_operation**: 推断（非本书断言）：启动继电器线圈经 ST2→L 得电、触点接通后由 GR/SB 支路向磁性开关供电——该方向性判断部分依赖常规继电器拓扑推断，图中触点进出方向未完全可辨。  
  Source kind: `MODEL_INFERENCE`; status: `EXTRACTED_UNCHECKED`; evidence: NONE.  
  Applicability: `{"engine":["2AZ-FE","2GR-FE"],"make":"Toyota","market":null,"model":"凯美瑞/Camry","model_code":null}`  
