# Automotive book knowledge (canonical-derived)

Source: `master:automotive-books`

Review: `PROVISIONAL_NO_ENTITY_COLLAPSE`

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
- **has_component**: 书中说明起动系统主要由起动机等组成（Q5 正文列出四个主要组成部件之一）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p16:e1.  
- **has_component**: 书中说明起动系统主要由起动机继电器等组成（Q5 正文列出四个主要组成部件之一）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p16:e1.  
- **has_component**: 书中说明起动系统主要由点火开关等组成（Q5 正文列出四个主要组成部件之一）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p16:e1.  
- **has_component**: 书中说明起动系统主要由蓄电池等组成（Q5 正文列出四个主要组成部件之一）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p16:e1.  
- **performs_function**: Q5 正文给出起动系统的功用：把蓄电池电能转化为机械能，经飞轮齿圈带动发动机由静止进入自行运转。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p16:e1.  
- **has_component**: 图1-6 中起动机内部标出吸拉线圈（与保持线圈共同构成电磁开关线圈部分）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p16:e2.  
- **has_component**: 图1-6 中起动机内部标出保持线圈。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p16:e2.  
- **has_component**: 图1-6 中起动机输出侧标出单向离合器。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p16:e2.  
- **has_component**: 图1-6 中起动机标出拨叉（经支点拨动单向离合器一侧）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p16:e2.  
- **has_component**: 图1-6 中起动机标出电枢与磁场绕组（电动机本体部分）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p16:e2.  
- **realizes_mechanism**: 图1-6 示意起动系统的组成及工作原理：控制回路各元件与起动机端子的连接关系，以及电磁开关经拨叉驱动单向离合器的内部传动链。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p16:e2.  
- **associated_with**: 图1-6 起动控制回路中串有空档起动开关（MT/AT 触点），正文的组成文字未单独列出该部件。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p16:e2.  
- **part_of**: Q6 正文称点火系统是汽油发动机上的重要组成部分。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p16:e3.  
- **has_component**: Q6 正文列出点火系统主要组成部件之一：点火线圈。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p16:e3.  
- **has_component**: Q6 正文列出点火系统主要组成部件之一：火花塞（图1-7 编号6 亦示出）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p16:e3.  
- **has_component**: Q6 正文列出点火系统主要组成部件之一：高压线；图1-7 编号1 对应部件名为点火高压线。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p16:e3.  
- **has_component**: Q6 正文泛称点火系统含传感器；图1-7 具体示出爆燃传感器1（编号10）与爆燃传感器2（编号8）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p17:e1.  
- **has_component**: 图1-7 编号14 示出点火系统组成中的霍尔传感器（正文仅泛称传感器，未点名霍尔传感器）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p17:e1.  
- **affects**: Q6 正文给出点火系统工作性能与发动机动力性、环保性、经济性的直接影响关系。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p16:e3.  
- **realizes_mechanism**: Q6 正文给出点火系统工作机理：低压12V 升压为15000～30000V、高压电引入燃烧室、火花塞跳火并按工作循环与点火顺序逐缸点燃。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p16:e3.  
- **has_component**: 图1-7 以编号爆炸图登记点火系统组成部件（含功能件与插头、紧固件、垫片、隔板等安装件）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p17:e1.  
- **performs_function**: Q7 正文给出燃油供给系统功用：按工况定量供给可燃混合气或雾状燃料，燃烧后把热能转化为机械能；供什么介质随机型而异。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p17:e2.  
- **has_component**: 图1-8 与图1-9 均示出燃油供给系统中的燃油箱（图1-9 编号19 称油箱）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p18:e1, book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p18:e2.  
- **has_component**: 图1-8 示出燃油供给系统中的电动燃油泵（置于燃油箱内）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p18:e1.  
- **has_component**: 图1-8 供油管路中示出燃油滤清器（图1-9 编号24 亦列为燃油箱附属件之一）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p18:e1, book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p18:e2.  
- **has_component**: 图1-8 示出燃油分配管（各缸喷油器装于其上）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p18:e1.  
- **has_component**: 图1-8 示出燃油分配管下方的4只喷油器（雾状喷射部位）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p18:e1.  
- **has_component**: 图1-8 示出油压调节器（带回油口）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p18:e1.  
- **realizes_mechanism**: 图1-8 示意燃油供给系统的供油-回油路线：从燃油箱内电动燃油泵到喷油器喷射，油压调节器带回油。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p18:e1.  
- **has_component**: 图1-9 以编号爆炸图登记燃油箱及其附属件（加油/通气/回油/供油/泵与油量表传感器/安装紧固件等）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p18:e2.  
- **part_of**: 图1-9 编号5 的重力阀属燃油箱附属件（通气管一侧）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p18:e2.  
- **has_component**: 图1-10 以编号图登记活性炭罐装置的组成部件（罐体、电磁阀、节气门体接口、通风管与安装件）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p19:e1.  
- **part_of**: 图1-10 编号7 的活性炭罐是活性炭罐装置的主体部件。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p19:e1.  
- **part_of**: 图1-10 编号4 的活性炭罐电磁阀是活性炭罐装置的组成部件。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p19:e1.  
- **associated_with**: 图1-10 编号9 通风管接燃油箱重力阀，把活性炭罐装置与燃油箱通气侧连通。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p19:e1.  
- **part_of**: Q7 正文称燃油供给系统（与电子控制系统）的组成如图1-8、图1-9和图1-10所示，活性炭罐装置（图1-10）在该组图之内。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p17:e2.  
- **performs_function**: Q7 电控释文段给出电子控制系统功用：按工况定最佳控制方案并执行，含故障自诊断。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p19:e2.  
- **has_component**: 正文称电子控制系统都由传感器、电子控制器（ECU）和执行器3部分组成，本条对应传感器部分。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p19:e2.  
- **has_component**: 正文称电子控制系统都由传感器、电子控制器（ECU）和执行器3部分组成，本条对应电子控制器（ECU）部分。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p19:e2.  
- **has_component**: 正文称电子控制系统都由传感器、电子控制器（ECU）和执行器3部分组成，本条对应执行器部分。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p19:e2.  
- **realizes_mechanism**: 正文说明电子控制系统的体系结构（单片机为中心的微型计算机控制系统）与核心部件（ECU）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p19:e2.  
- **realizes_mechanism**: 图1-11 示出汽油机电子控制系统的组成和流程：传感器清单、发动机电控单元、执行器清单及诊断插座与附加信号。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e1.  
- **has_component**: 图1-11 传感器侧列出空气流量计。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e1.  
- **has_component**: 图1-11 传感器侧列出曲轴位置传感器。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e1.  
- **has_component**: 图1-11 传感器侧列出上止点位置传感器。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e1.  
- **has_component**: 图1-11 中节气门组件同时出现在传感器侧（内含节气门电位计、节气门定位电位计、怠速开关）与执行器侧。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e1.  
- **has_component**: 图1-11 传感器侧列出进气温度传感器。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e1.  
- **has_component**: 图1-11 传感器侧列出冷却液温度传感器。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e1.  
- **has_component**: 图1-11 传感器侧列出氧传感器。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e1.  
- **has_component**: 图1-11 传感器侧列出爆燃传感器I 与爆燃传感器II（与图1-7 编号8/10 的爆燃传感器2/1 同为爆燃传感器，称谓与编号不同）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e1, book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p17:e1.  
- **has_component**: 图1-11 执行器侧列出燃油泵继电器。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e1.  
- **associated_with**: 图1-11 执行器侧标注'燃油泵继电器'指向'燃油泵'，示意由继电器控制燃油泵。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e1.  
- **has_component**: 图1-11 执行器侧列出点火线圈总成（含点火模块）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e1.  
- **has_component**: 图1-11 执行器侧列出炭罐清污电磁阀；图1-10 中对应部件名为活性炭罐电磁阀。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e1, book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p19:e1.  
- **has_component**: 图1-11 执行器侧列出氧传感器加热器。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e1.  
- **has_component**: 图1-11 中故障检测诊断插座接于电控单元下方，属汽油机电子控制系统的组成环节。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e1.  
- **has_component**: 图1-11 执行器侧列出喷油器（与图1-8 燃油供给系统中的喷油器同名称谓一致）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e1, book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p18:e1.  
- **has_component**: Q8 正文列出润滑系统组成之一：油底壳（图1-12 编号13 亦示出）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e2.  
- **has_component**: Q8 正文把机油列为润滑系统的组成（作为被循环供给的工作介质）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e2.  
- **has_component**: Q8 正文列出润滑系统组成之一：机油滤清器。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e2.  
- **has_component**: Q8 正文列出润滑系统组成之一：机油泵（图1-12 编号19 称带链轮的机油泵）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e2.  
- **has_component**: Q8 正文列出润滑系统组成之一：机油集滤器。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e2.  
- **has_component**: Q8 正文列出润滑系统组成之一：主油道。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e2.  
- **has_component**: Q8 正文列出润滑系统组成之一：分油道。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e2.  
- **has_component**: Q8 正文把'各摩擦表面'与油道等并列为润滑系统组成，语义上为机油的供给对象而非独立部件。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e2.  
- **performs_function**: Q8 正文给出润滑系统的核心功用：持续向各运动件摩擦表面供油，减摩耐磨。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e2.  
- **performs_function**: Q8 正文给出机油的清洗功用：流动机油带走摩擦表面磨屑等杂质。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e2.  
- **performs_function**: Q8 正文给出机油的冷却功用：流动机油冷却摩擦表面。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e2.  
- **performs_function**: Q8 正文给出机油油膜的密封功用：气缸壁与活塞环间油膜提高气缸密封性。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e2.  
- **performs_function**: Q8 正文给出机油的防锈防护功用。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p20:e2.  
- **has_component**: 图1-12 以编号爆炸图登记润滑系统部件（加油/测量件、油底壳组件、带链轮机油泵及链条传动、前密封法兰与曲轴端同步带轮等）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p21:e1.  
- **part_of**: 图1-12 编号1 的机油加油口盖属润滑系统部件。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p21:e1.  
- **part_of**: 图1-12 编号2 的机油标尺属润滑系统部件（油面测量件）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p21:e1.  
- **associated_with**: 图1-12 中机油泵为'带链轮的机油泵'（编号19），配机油泵链条（编号21）与链条张紧器（编号27）、链轮（编号26），示意链条传动布置。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p21:e1.  
- **part_of**: 图1-12 编号18 的放油螺栓装于油底壳（编号13）上。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p21:e1.  
- **has_component**: Q9 正文列出冷却系统主要组成之一：水泵。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p22:e1.  
- **has_component**: Q9 正文列出冷却系统主要组成之一：散热器（图1-13 编号1 亦示出）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p22:e1.  
- **has_component**: Q9 正文列出冷却系统主要组成之一：节温器。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p22:e1.  
- **has_component**: Q9 正文列出冷却系统主要组成之一：冷却液温度传感器（图1-11 传感器侧亦列有同名部件）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p22:e1.  
- **has_component**: Q9 正文列出冷却系统主要组成之一：冷却风扇（图1-13 编号11 称风扇）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p22:e1.  
- **has_component**: Q9 正文列出冷却系统主要组成之一：膨胀罐；图1-13 编号14 对应部件名为膨胀箱（另有编号13 冷却液膨胀箱盖）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p22:e1.  
- **performs_function**: Q9 正文给出冷却系统的功用：任何工况下对高温机件适当冷却，维持最适宜工作温度范围。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p22:e1.  
- **provides_for**: Q9 正文说明冷却系统还为暖风系统提供热源。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p22:e1.  
- **has_parameter**: Q9 正文给出冷却系统正常工作压力数值范围 0.13～0.15MPa。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p22:e1.  
- **has_parameter**: Q9 正文给出冷却系统工作温度数值范围 80～120℃。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p22:e1.  
- **has_parameter**: Q9 正文给出冷却液量约 6.0L。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p22:e1.  
- **has_component**: 图1-13 以编号爆炸图登记冷却系统部件（散热器及导板、软管与卡箍、风扇与护圈、膨胀箱及盖、热敏开关等）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p22:e2.  
- **part_of**: 图1-13 编号6 的热敏开关属冷却系统部件（正文的组成文字未单独点名该件）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p22:e2.  
- **part_of**: 图1-13 编号8 的冷却液上软管属冷却系统管路部件。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p22:e2.  
- **part_of**: 图1-13 编号10 的冷却液下软管属冷却系统管路部件。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p22:e2.  
- **part_of**: 图1-13 编号12 的风扇护圈属冷却系统部件（护风罩类安装件）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p22:e2.  
- **part_of**: 图1-13 编号13 的冷却液膨胀箱盖属冷却系统部件（配膨胀箱编号14）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p22:e2.  
- **part_of**: 图1-13 编号4 的空气导板属冷却系统部件（散热器周边导流件）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:15oExvt_2DQ0bBWxR1s-cp8fmvmFJdt6y:ev:p22:e2.  
- **is_defined_as**: 汽油机点火系统被定义为能够按时在火花塞两电极之间产生电火花的全部装置。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p139:e1.  
- **performs_function**: 点火系统的作用是适时地为汽油发动机气缸内已压缩的可燃混合气提供足够能量的电火花，使发动机能及时、迅速地做功；点火系统性能好坏对发动机工作有十分重要的影响。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p139:e1.  
- **realizes_mechanism**: 点火系工作机理是将蓄电池或发电机供给的12V低压电转变为上万伏的高压电，并按工作需要分送到各缸火花塞，使电极间产生电火花。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p139:e2.  
- **has_variant**: 点火系统种类较多，传统点火系统是其中的主要种类之一。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p139:e3.  
- **has_variant**: 点火系统种类较多，无触点电子点火系统是其中的主要种类之一。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p139:e3.  
- **has_variant**: 点火系统种类较多，微机控制点火系统是其中的主要种类之一。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p139:e3.  
- **integrates_with**: 随着化油器发动机的淘汰，现代汽油车普遍采用电控燃油喷射系统，将燃油喷射控制与点火控制结合在一起实行集中控制，共用很多传感器信号。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p139:e3.  
- **has_component**: 微机控制点火系统主要由传感器（包括各种开关）、电子控制器、点火器、点火线圈等组成。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p139:e4.  
- **has_component**: 电子控制器是微机控制点火系统的主要组成部件之一。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p139:e4.  
- **has_component**: 点火器是微机控制点火系统的主要组成部件之一。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p139:e4.  
- **has_component**: 点火线圈是微机控制点火系统的主要组成部件之一。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p139:e4.  
- **includes_component**: 微机控制点火系统的传感器（包括各种开关）主要有：曲轴位置传感器、空气流量计（或绝对压力传感器）、冷却液温度传感器、进气温度传感器、氧(O2)传感器、节气门位置传感器、车速传感器、爆燃传感器、空调开关信号等。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p139:e6.  
- **performs_function**: 电子控制器的作用是根据发动机各传感器输入的信息及内存的数据进行运算、处理、判断，然后输出指令（信号）控制有关执行器（如点火器）动作，达到快速、准确地控制发动机工作的目的。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p139:e7.  
- **controls**: 点火器根据电子控制器输出的指令，通过内部大功率晶体管的导通和截止，控制点火线圈初级电流的通断，进而使点火线圈的次级产生高压，完成点火工作。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p139:e8, book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p140:e1.  
- **realizes_mechanism**: 采用微机点火控制以后，可以由控制系统直接进行高压电的分配，成为无分电器电子点火系统。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p140:e2.  
- **has_variant**: 无分电器电子点火系统分两种：一种为每两缸装一个点火线圈，两缸同时点火；另一种为每缸一个点火线圈，各缸独立进行控制。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p140:e3.  
- **is_variant_of**: 两缸一个点火线圈、两缸同时点火的点火系统（图7-2）是无分电器电子点火系统的一种类型。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p140:e3.  
- **is_variant_of**: 每缸一个点火线圈、各缸独立控制的点火系统（图7-3）是无分电器电子点火系统的一种类型。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p140:e3.  
- **presents_as**: 图7-2示出两缸一个点火线圈的点火系统电路链路：曲轴位置传感器信号送电子控制装置，电子控制装置输出IGt/IGd信号至点火器（内含点火基准判断与点火分配器），点火器驱动两个点火线圈，每个点火线圈次级接两缸火花塞。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p140:e4.  
- **presents_as**: 图7-3示出每缸一个点火线圈的点火系统组成与信号流：各缸独立笔式点火线圈由功率管/功率放大驱动，ECU综合转速、曲轴转角、空气流量、冷却液温度、起动、爆燃、节气门开度等信号发出点火信号；图中标注各缸（1-5-3-6-2-4缸）点火顺序波形与曲轴位置传感器输出信号的角度区段（1°CA、32°CA、16°CA、8°CA、24°CA、6~120°CA）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p140:e6.  
- **has_component**: 点火线圈由初级绕组、次级绕组和铁心等组成。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p141:e1.  
- **has_variant**: 点火线圈按磁路的结构形式不同可分为开磁路式点火线圈和闭磁路式点火线圈，开磁路式是其中一类。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p141:e1.  
- **has_variant**: 点火线圈按磁路的结构形式不同可分为开磁路式点火线圈和闭磁路式点火线圈，闭磁路式是其中一类。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p141:e1.  
- **has_advantage**: 闭磁路点火线圈具有漏磁少、转换效率高、体积小、质量轻、铁心裸露易于散热等优点，故已在电子点火系中广泛采用。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p141:e2.  
- **realizes_mechanism**: 闭磁路式点火线圈在“口”字形或“日”字形铁心内绕初级绕组，在初级绕组外面绕次级绕组；初级绕组在铁心中的磁通通过铁心形成闭合磁路，故称闭磁路式点火线圈。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p141:e3.  
- **presents_as**: 图7-4示出闭磁路式点火线圈的结构与端子布置：初级绕组、次级绕组绕于铁心，设正接线柱、负接线柱和高压接线柱，磁力线沿“口”字形或“日”字形铁心形成闭合回路。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p141:e4.  
- **presents_as**: 火花塞在钢制壳体内部固定有高氧化铝陶瓷绝缘体，使中心电极与侧电极之间保持足够的绝缘强度；绝缘体孔上部装有金属杆，通过接线螺母与高压导线相连，下部装有中心电极；金属杆与中心电极之间用导电玻璃密封。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p141:e6.  
- **presents_as**: 图7-5示出火花塞的构造，由接线柱、绝缘体、金属杆、垫圈、壳体、导电玻璃、多层密封垫圈、内垫、侧电极和中心电极等组成。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p141:e8.  
- **uses_material**: 火花塞中心电极用镍锰合金制成，具有良好的耐高温、耐腐蚀和导电性能。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p141:e6.  
- **connects_to**: 火花塞借壳体下部的螺纹旋入气缸盖中，旋紧时密封垫圈受压变形，保证壳体与缸盖之间密封良好。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p141:e6.  
- **has_variant**: 为适应不同发动机的需要，火花塞因壳体下部的形状和绝缘体裙部长度的不同有多种形式。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p141:e6.  
- **determines**: 火花塞的热特性主要取决于绝缘体裙部的长度。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p141:e7.  
- **is_variant_of**: 绝缘体裙部长的火花塞受热面积大、传热距离长、散热困难、裙部温度高，称为热型火花塞，它是火花塞按热特性分类的一类。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p141:e7.  
- **is_variant_of**: 绝缘体裙部短的火花塞称为冷型火花塞，它是火花塞按热特性分类的一类。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p141:e7.  
- **applies_to**: 热型火花塞适用于低速、低压缩比、小功率发动机。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p141:e7.  
- **applies_to**: 冷型火花塞适用于高速、高压缩比、大功率发动机。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p141:e7.  
- **performs_function**: 起动机的作用就是起动发动机，发动机起动之后，起动机便立即停止工作。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p142:e1.  
- **has_variant_context**: 发动机常用的起动方式有人力起动、辅助汽油机起动和电力起动机起动三种，目前大多数运输车辆都采用电力起动机起动。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p142:e2.  
- **has_component**: 电力起动系一般由蓄电池、起动机、起动继电器、点火开关等组成，蓄电池是其组成部件之一。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p142:e3.  
- **has_component**: 电力起动系一般由蓄电池、起动机、起动继电器、点火开关等组成，起动机是其组成部件之一。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p142:e3.  
- **has_component**: 电力起动系一般由蓄电池、起动机、起动继电器、点火开关等组成，起动继电器是其组成部件之一。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p142:e3.  
- **has_component**: 电力起动系一般由蓄电池、起动机、起动继电器、点火开关等组成，点火开关是其组成部件之一。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p142:e3.  
- **located_in**: 起动机安装在汽车发动机飞轮壳前端的座孔上。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p142:e3.  
- **has_component**: 起动机由串励直流电动机、传动机构和操纵机构三个部分组成，串励直流电动机是其中之一（图7-7）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p142:e5, book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e2.  
- **has_component**: 起动机由串励直流电动机、传动机构和操纵机构三个部分组成，传动机构是其中之一（图7-7）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p142:e5, book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e2.  
- **has_component**: 起动机由串励直流电动机、传动机构和操纵机构三个部分组成，操纵机构是其中之一（图7-7）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p142:e5, book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e2.  
- **performs_function**: 直流电动机的作用是将蓄电池输入的电能转换为机械能，产生电磁转矩。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p142:e6.  
- **has_component**: 直流电动机主要由电枢、磁极、换向器等部件构成。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p142:e6.  
- **presents_as**: 图7-6以立体图示出起动系统的组成与连接：点火开关与起动继电器控制起动机，起动机经起动机电缆接蓄电池正极、经搭铁电缆回蓄电池，起动机驱动齿轮与发动机飞轮（齿圈）啮合。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p142:e4.  
- **presents_as**: 图7-7起动机构造剖视按零件表给出24个编号零件，覆盖电磁开关（回位弹簧、保持线圈、吸拉线圈、壳体、触点、接线柱、接触盘）、直流电动机（后端盖、电刷弹簧、换向器、电刷、磁极、磁极铁心、电枢、励磁绕组）与传动部分（移动衬套、缓冲弹簧、单向离合器、电枢轴花键、驱动齿轮、罩盖、制动盘、传动套筒、拨叉）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e1.  
- **is_a**: 电枢是直流电动机的旋转部分，包括电枢轴、换向器、电枢铁心、电枢绕组。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e3.  
- **has_design_characteristic**: 为了获得足够的转矩，通过起动机电枢绕组的电流一般为200～600A，因此电枢绕组采用较粗的矩形裸铜线绕制成成型绕组。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e3.  
- **connects_to**: 电枢绕组各线圈的端头均焊接在换向器片上，通过换向器和电刷将蓄电池的电流引进来。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e3.  
- **realizes_mechanism**: 换向片和云母片迭压成换向器。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e3.  
- **has_design_characteristic**: 为了避免电刷磨损的粉末落入换向片之间造成短路，起动机换向片间的云母一般不必割低。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e3.  
- **has_design_characteristic**: 起动机直流电动机的磁极一般是4个，两对磁极相对交错安装在电动机定子内壳上。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e4.  
  Counterexamples: 也有用6个磁极的起动机（claim:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:c07:0058）
- **part_of**: 低碳钢板制成的电动机机壳也是磁路的一部分。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e4.  
- **has_variant**: 除常见的4个磁极外，也有用6个磁极的起动机。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e4.  
- **presents_as**: 起动机电刷架一般为框式结构，其中正极刷架与端盖绝缘地固装，负极刷架直接搭铁。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e5.  
- **has_design_characteristic**: 起动机电刷由铜粉与石墨粉压制而成，呈棕红色；刷架上装有弹性较好的盘形弹簧。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e5.  
- **has_design_characteristic**: 因为起动机工作时间短暂（每次工作时间仅几秒钟），起动机轴承一般采用青铜石墨轴承或铁基含油轴承。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e6.  
- **has_component**: 起动机的传动机构包括离合器和拨叉两个部分，离合器是其主要组成部件。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e7.  
- **has_component**: 起动机的传动机构包括离合器和拨叉两个部分，拨叉是其中之一。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e7.  
- **performs_function**: 起动机传动机构中离合器的作用是将电动机的电磁转矩传递给发动机使之起动，同时又能在发动机起动后自动打滑，保护起动机不致飞散损坏。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e7.  
- **has_variant**: 传动机构中的离合器分为滚柱式离合器、摩擦片式离合器、弹簧式离合器几种，滚柱式离合器是其中之一。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e7.  
- **has_variant**: 传动机构中的离合器分为滚柱式离合器、摩擦片式离合器、弹簧式离合器几种，摩擦片式离合器是其中之一。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e7.  
- **has_variant**: 传动机构中的离合器分为滚柱式离合器、摩擦片式离合器、弹簧式离合器几种，弹簧式离合器是其中之一。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e7.  
- **performs_function**: 拨叉的作用是使离合器做轴向移动，将驱动齿轮啮入和脱离飞轮齿圈。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e7.  
- **realizes_mechanism**: 发动机起动时，按下按钮或起动开关，线圈通电产生电磁力将铁心吸入，带动拨叉转动，由拨叉头推出离合器，使驱动齿轮啮入飞轮齿圈；发动机起动后松开按钮或开关，线圈断电电磁力消失，在回位弹簧作用下铁心退出、拨叉返回，拨叉头将打滑工况下的离合器拨回，驱动齿轮脱离飞轮齿圈。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e8.  
- **presents_as**: 滚柱式离合器是目前国内外汽车起动机中使用最多的一种，解放牌汽车、东风牌汽车、北京牌吉普车等均使用滚柱式离合器。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p143:e9.  
- **realizes_structure**: 滚柱式离合器的驱动齿轮与外壳连成一体，外壳内装有十字块和4套滚柱及弹簧，十字块与花键套筒固定连接，壳底与外壳相互折合密封。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p144:e1.  
- **connects_to**: 滚柱式离合器花键套筒的外面装有缓冲弹簧及衬圈，末端固装着拨环与卡圈；整个离合器总成利用花键套筒套在起动机轴的花键部位上，可以做轴向移动和随轴转动。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p144:e1.  
- **presents_as**: 图7-8示出滚柱式离合器的结构：总成剖视与端面视图及构件分解图，零件包括外壳、花键套筒、卡圈、拨环、弹簧（2处）、滚柱、驱动齿轮、铜衬套、十字块。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p144:e2.  
- **realizes_mechanism**: 发动机起动时，经拨叉将离合器沿花键推出，驱动齿轮啮入发动机飞轮齿圈；由于十字块处于主动状态随电动机电枢一起旋转，促使4套滚柱进入槽的窄端，将花键套筒与外壳挤紧，于是电动机电枢的转矩可由十字块经滚柱、离合器外壳传给驱动齿轮，从而达到驱动发动机飞轮齿圈旋转、起动发动机运转的目的（图7-9a）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p144:e4, book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p144:e6.  
- **realizes_mechanism**: 发动机起动后，飞轮齿圈的转速高于驱动齿轮，十字块处于被动状态，促使滚柱进入槽的宽端而自由滚动，只有驱动齿轮随飞轮齿圈作高速旋转，起动机转速并不升高；在这种离合器打滑的功能下，防止了电枢超速飞散的危险（图7-9b）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p144:e7, book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p144:e6.  
- **realizes_mechanism**: 起动完毕，由于拨叉回位弹簧的作用，经拨环使离合器退回，驱动齿轮完全脱离飞轮齿圈。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p144:e7.  
- **has_advantage**: 滚柱式离合器具有结构简单、坚固耐用、体积小、质量轻、工作可靠等优点，因此得到广泛采用。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p144:e8.  
- **has_limitation**: 滚柱式离合器的不足是不能用于大功率起动机上。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p144:e8.  
- **performs_function**: 起动系控制装置的作用是用来接通和断开电动机与蓄电池之间的电路。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p145:e1.  
- **presents_as**: 电磁操纵式起动机的应用最为广泛。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p145:e1.  
- **performs_function**: 在电路中采用起动机的电磁开关作为控制电路的一部分，电磁开关的作用和工作原理都是相同的，图7-10是基本的电磁控制电路。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p145:e2.  
- **realizes_mechanism**: 直接控制式电磁开关在起动时（点火钥匙打到“ST”位）：电流由蓄电池正极经“50”端子→吸拉线圈→导电片→“C”端子→起动机励磁绕组→电枢→搭铁回蓄电池负极，起动机慢慢转动；同时电流经保持线圈回负极；吸拉线圈与保持线圈产生同方向的电磁力，铁心压缩回位弹簧移动并带动拨叉，使驱动小齿轮与发动机飞轮啮合。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p145:e3.  
- **realizes_mechanism**: 直接控制式电磁开关在驱动小齿轮与飞轮啮合时，电磁开关内的接触盘将“C”与“30”、旁通接柱相继接通，起动机主电路接通（蓄电池正极→“30”端子→接触盘→“C”端子→励磁绕组→电枢→搭铁→负极），电枢产生电磁转矩起动发动机；此时吸拉线圈被短路，保持线圈的电磁力使驱动小齿轮与飞轮保持啮合，保证发动机起动着车。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p145:e3.  
- **protects**: 起动后，发动机飞轮转速超过起动机电枢时，单向离合器切断飞轮与小齿轮之间的动力传递，保护起动机。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p145:e4.  
- **realizes_mechanism**: 松开点火钥匙后，“50”端子断电；由于机械惯性短时间内接触盘仍将“30”与“C”端子接通，蓄电池电流经接触盘→吸拉线圈→保持线圈→搭铁回负极；吸拉线圈与保持线圈产生相反方向的电磁力，接触盘接触不牢，在回位弹簧作用下铁心迅速回位，接触盘与“C”“30”端子分开，起动主电路被断开，起动完毕。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p145:e4.  
- **presents_as**: 图7-10示出基本的电磁控制电路：蓄电池经点火开关接电磁开关“50”端子，电磁开关内设吸拉线圈与保持线圈，经接触盘连接“30”端子、“C”端子与旁通接柱，起动机励磁线圈环绕电枢并经电刷供电。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p145:e5.  
- **connects_to**: 电磁开关上的旁通接柱接点火线圈附加电阻接柱（起动开关接柱）；由于起动机工作时电流很大，为保证点火系统火花能量，旁通接柱是在起动时将附加电阻短路的。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p145:e7.  
- **has_variant_context**: 目前汽车较多采用电子点火，点火系统已不再设置附加电阻，在这种类型的车上，起动机电磁开关也没有旁通接柱。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p145:e7.  
- **uses**: QD124型起动机采用带起动继电器控制的电磁开关，其接线见图7-11。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p146:e1.  
- **presents_as**: 图7-11示出QD124型起动机控制电路的接线与零件：起动继电器（触点、线圈）、点火开关、主/辅助接线柱、导电片、吸引线圈接线柱、电磁开关接线柱、触盘、活动杆、固定铁心、吸引线圈、保持线圈、电磁铁心、回位弹簧、螺杆、连接头、拨叉、滚柱式离合器、驱动齿轮、止推螺母、点火线圈附加电阻线；图中在驱动齿轮/止推螺母区域标注尺寸4.5±1(mm)与29~32(mm)。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p146:e2.  
- **realizes_mechanism**: 发动机起动时，将点火开关钥匙旋至起动档位，起动继电器通电后吸下可动臂使触点闭合，接通了电磁开关线圈电路，起动机投入工作；发动机起动后只需松开点火开关钥匙，点火开关自动转回到点火工作档位，起动继电器线圈断电触点打开，电磁开关也随即断开，起动机停止工作。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p146:e4.  
- **performs_function**: 利用起动继电器控制电磁开关，能减小通过点火开关起动触点的电流，避免烧蚀触点，延长使用寿命。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p146:e5.  
- **performs_function**: 有些汽车上的起动继电器在改进控制电路以后，还能起到自动停止起动机工作及安全保护的作用。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p146:e5.  
- **requires_precondition**: 对于装有自动变速器的车辆，起动机的工作电路还将受到变速器的档位开关信号的控制，只有在N档（空档）或P档（停车档）才允许起动机工作。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p146:e6.  
- **presents_as**: 第七章末思考题共4题，分别针对微机控制点火系统的工作、起动系统的组成、滚柱式离合器的工作原理和直接控制电磁开关强制啮合式起动机的工作过程。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:17Xm9TVoW7KCQSjN2P_QeRsnoXEo2mGmC:ev:p146:e7.  
- **realizes_mechanism**: [模型推断] 点火线圈初级电流通断使次级产生高压的机理是电磁感应（互感）：初级电流变化引起铁心中磁通变化，从而在次级绕组感应出高压电动势。书页仅描述“初级电流的通断→次级产生高压”这一因果链，未写明感应机理本身。  
  Source kind: `MODEL_INFERENCE`; status: `EXTRACTED_UNCHECKED`; evidence: NONE.  
- **explains_advantage**: [模型推断] 闭磁路点火线圈漏磁少、转换效率高的原因在于其磁通主要经铁心形成闭合回路，铁心磁阻远小于空气路径，减少了经空气泄漏的漏磁。书页只陈述了该优点本身，未解释原因。  
  Source kind: `MODEL_INFERENCE`; status: `EXTRACTED_UNCHECKED`; evidence: NONE.  
- **defined_as**: VTEC的中文全称为可变气门正时和升程电子控制系统，书中称其为本田的专有技术。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p5:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **adjusts_valvetrain_by_parameters**: VTEC能随发动机转速、负荷、冷却液温度等运行参数的变化，适当调整配气正时和气门升程，使发动机在高速、低速下均能达到最高效率。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p5:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **has_structure**: VTEC系统的进气凸轮轴上分别有三个凸轮面，分别顶置摇臂轴上的三个摇臂。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p5:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **forms_operating_mode**: 发动机处于低转速或低负荷时三个摇臂之间无任何连接，进气主摇臂和进气辅摇臂分别顶动两个进气门，使两者具有不同的正时及升程，形成低速工作模式。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p5:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **idle_behavior_in_low_speed_mode**: 低速工作模式下，中间的高速摇臂不顶动气门，只在摇臂轴上做无效的运动（该句自p0005行末跨页续至p0006行首）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p5:e1, book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p6:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **receives_and_processes_sensor_parameters**: 转速不断提高时，发动机各传感器将监测到的负荷、转速、车速以及冷却液温度等参数送到ECM/PCM，由ECM/PCM分析处理。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p6:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **triggers_high_speed_switch**: 当需要变换为高速工作模式时，ECM/PCM发出一个信号打开摇臂轴控制电磁阀（VTEC电磁阀），使压力机油进入摇臂轴内顶动VTEC切换活塞。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p6:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **connects_rockers_into_high_speed_mode**: VTEC切换活塞被压力机油顶动后，使三只摇臂连接成一体，两只气门都按高速模式工作。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p6:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **triggers_return_to_low_speed**: 当发动机转速降低到气门正时需要再次变换时，ECM/PCM再次发出信号打开VTEC电磁阀，使压力机油泄出，气门再次回到低速工作模式。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p6:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **depicted_low_speed_layout**: 图1-1以结构剖视与油路示意展示了低速工作模式的构成：两个低升程凸轮、三个进气摇臂、VTEC切换活塞与回位弹簧，压力机油来自机油泵并经摇臂轴控制电磁阀（阀芯）控制。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p5:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **depicted_high_speed_layout**: 图1-2展示高速工作模式：由高升程凸轮驱动，压力机油自机油泵经摇臂轴控制电磁阀进入摇臂轴，VTEC切换活塞移动将三只摇臂连为一体。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p6:e3.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **defined_as_composition**: i-VTEC系统是在VTEC系统的基础上增加一个称为VTC（Variable Timing Control，可变正时控制）的装置——一组进气门凸轮轴正时可变控制机构，即i-VTEC=VTEC+VTC。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p6:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **controls_exhaust_valve_timing_overlap**: 采用i-VTEC后，排气阀门的正时与开启的重叠时间是可变的，由VTC控制。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p6:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **composed_of**: VTC系统由VTC作动器、VTC油压控制阀、各种传感器以及ECM/PCM组成（图1-3）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p6:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **varies_cam_phase_continuously_by_pcm_signal**: VTC作动器与VTC油压控制阀根据ECM/PCM的信号产生动作，使进气凸轮轴的相位连续变化。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p6:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **raises_engine_power**: 书中称VTC令气门重叠时间更加精确、保证进排气门的最佳重叠时间，可将发动机功率提高20%。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p6:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **adaptively_cooperates_with_vtec_in_three_regions**: VTC系统的导入使气门配气相位能够“智能化地”适应发动机负荷的改变；VTC在发动机运转过程中配合VTEC系统，主要运用在三个方面。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p6:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **region_1_idle_and_lean_burn**: 在最佳怠速/稀薄燃烧区域内，VTC系统停止作用，此时气门重叠角最小；由于VTEC的作用产生强大的涡流，使发动机怠速工作稳定。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p6:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **region_2_fuel_economy_and_emission**: 在最佳油耗、排气控制区域内，VTEC发挥作用产生强大涡流使可燃混合气混合更加均匀，同时VTC的作用使气门重叠角加大，将部分废气重新吸入气缸，起到EGR的作用，以此达到最佳油耗和排气控制（句自p0006跨页续至p0007）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p6:e2, book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p7:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **region_3_torque_control**: 在最佳转矩控制区域内，通过VTC的控制以最适当的气门重叠角，同时配合VTEC系统的作用，使发动机的输出转矩最大限度地提高。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p7:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **depicted_vtc_oil_and_electric_layout**: 图1-3展示了VTC的油路与电路构成：机油泵经VTC滤网向VTC油控制电磁阀供油，电磁阀分配推进油压与延迟油压至VTC作动器（内有推进器、延迟器、叶片），另设排放油口；ECM/PCM根据各种传感器信号控制电磁阀并与凸轮轴位置传感器连接。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p7:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **composed_of**: 电子节气门控制系统由节气门电动机、节气门位置（TP）传感器A/B、加速踏板位置（APP）传感器A/B、电子节气门控制系统（ETCS）控制继电器及ECM/PCM组成（图1-4）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p7:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **regulates_intake_air**: 电子节气门控制系统主要运用节气门位置传感器感知节气门的开度，并通过车辆内部的加速踏板位置（APP）传感器A/B信号协同操作，来调节吸入气缸中的空气量。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p7:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **depicted_wiring_layout**: 图1-4示出ETCS电路连接关系：APP传感器A/B与TP传感器A/B分别经电源/信号/接地线接入ECM/PCM，节气门电动机由ETCSM+与ETCSM-两线驱动，系统还有IG1(ETCS)电源、PGM/ETCS接地，并接收来自发动机其他传感器与来自巡航控制继电器的信号。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p8:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **function**: 进气歧管调节控制系统主要用来调节发动机功率，通过打开和关闭进气歧管调节（IMT）作动器来实现控制（图1-5）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p7:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **torque_characteristic_by_valve_state**: 工作时，当IMT阀关闭时，发动机低速运转时转矩较高；当IMT阀打开时，发动机高速运转时的转矩较高。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p7:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **reports_valve_position_to_pcm**: 进气歧管调节阀作动器包括一个测试IMT阀位置、并将该信号发送至ECM/PCM的传感器。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p7:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **depicted_actuator_parts**: 图1-5展示进气歧管上的IMT阀与进气歧管调节(IMT)作动器，作动器内部标注有磁铁与电动机两个部件。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p8:e3.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **composed_of**: 废气再循环控制系统采用电控EGR系统，主要由EGR阀、EGR阀位置传感器、EGR管以及发动机控制单元（ECM/PCM）组成（图1-6）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p8:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **controls_egr_valve_by_ideal_opening_map**: EGR阀工作时，ECM/PCM根据存储器内的不同条件下理想的EGR阀开度控制EGR阀。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p8:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **closed_loop_correction**: EGR阀位置传感器检测EGR阀的开度并送至ECM/PCM；ECM/PCM将此开度与根据输入信号计算出的理想开度比较，如有不同，将减小EGR阀的电流、减小施加到EGR阀的真空度，使EGR再循环的废气量改变。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p8:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **depicted_gas_recirculation_path**: 图1-6示出EGR再循环路径：排气经排气歧管、EGR管与EGR阀引入进气歧管，图中还标注三元催化转化器(TWC)、节气门体、空气滤清器、EGR阀位置传感器及ECM/PCM的连接关系。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p9:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **composed_of**: 燃油蒸发排放控制系统采用电控EVAP系统，主要由EVAP双通阀、EVAP活性炭罐、EVAP活性炭罐净化阀、EVAP管以及ECM/PCM组成（图1-7）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p8:e4.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **function_store_and_purge**: EVAP系统的作用在于尽量减少排入大气的燃油蒸气；燃油蒸气被临时存储在EVAP活性炭罐内，直到从活性炭罐净化后输送至发动机进行燃烧。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p8:e4.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **composed_of_hose_routing**: 曲轴箱强制通风系统（PCV）主要由PCV软管、PCV阀组成；一般一条PCV软管接通空气滤清器至气门室盖，另一条接通PCV阀至进气歧管（图1-8）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p8:e4.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **structure_and_location**: PCV阀由柱塞式阀门和弹簧构成，位于进气歧管的一侧。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p10:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **vacuum_determines_blowby_flow**: 进气歧管的真空度决定了PCV阀的开闭及开启的程度，而PCV阀的开闭及开启程度又决定了窜气混合气被重新吸入进气歧管参加燃烧的数量。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p10:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **depicted_flow_legend**: 图1-8以图例标注两种流向：黑色箭头表示窜缸水蒸气，白色箭头表示新鲜空气，并标出两条PCV软管与PCV阀（局部放大）的位置。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p10:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **install_location_and_wiring**: 能源管理系统在蓄电池上增加了电流传感器（图1-9），安装在蓄电池的负极，带有2根连接端子：一端的电线为传感器提供电源，另一端的电线向ECM/PCM发送数据。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p10:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **adjusts_generator_voltage**: ECM/PCM根据蓄电池传感器的数据向发电机下达充电指令，通过此数据连接线可控制发电机电压在12.5~14.5V之间进行调整，增减以0.1V为单位。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p10:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **battery_benefit**: EMS系统可减少由于不规范的行驶模式引发的蓄电池问题，同时蓄电池维持一定的充电量也可提升蓄电池的寿命。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p10:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **tracks_charge_state_periodically**: EMS采用的蓄电池传感器可定期追踪调查蓄电池的整体充电状态（EMS主要功能之一）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p10:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **records_key_off_current_consumption**: 根据ECM/PCM，EMS可记录最近5次行驶周期内钥匙关闭状态下的电流消耗状况（EMS主要功能之二）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p10:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **raises_dtc_on_fault**: EMS在发生不良故障时会出现故障码并显示其故障内容（EMS主要功能之三）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p10:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **defined_as**: 主动噪声控制（ANC）系统也称有源噪声控制、有源消声、有源降噪，是一种利用附加声源在指定区域内人为地、有目的地产生抵消声信号来控制原始声信号的降噪方法。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p11:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **composed_of**: ANC系统包括ANC-ECU、误差信号传感器、初级声源传感器、扬声器四大部分，通过扬声器发送小声音来消除发动机噪声（图1-10）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p11:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **composed_of_and_control_chain**: 主动控制发动机支座（ACM）系统由前、后主动控制支座和ACM-ECU控制单元组成（图1-11）；工作时两个支座都由ACM-ECU控制单元进行控制，ACM-ECU从ECM/PCM接收信号。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p11:e3.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **structure**: 主动控制支座是一个充液式发动机支座，由一个上密封液体室和一个下线性电磁阀驱动室组成（图1-12），主要部件包括线性电磁阀、柱塞总成、支座橡胶以及振动板等。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p11:e3.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **counter_phase_vibration_mechanism**: 主动控制支座工作时由ACM-ECU控制，驱动电磁阀能使向密封液体加压和减压的柱塞移动；通过向与发动机振动相反的相位执行该程序，以减少传送到车身的发动机振动。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p11:e3.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **principle_outside_first**: 诊断原则（1）先外后里：发动机出现故障时，先对电子控制系统以外的可能故障部位予以检查。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p12:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **principle_simple_first**: 诊断原则（2）先简后繁：直观检查最为简单，可先用看、摸、听等就车检查项目进行检查——看线路是否松脱断裂、油路是否漏油、进气管路有无破损漏气；摸可疑线路连接处有无不正常高温以判断接触不良；听有无漏气声、发动机异响及喷油器有无规律的咔嗒声。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p12:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **principle_familiar_first**: 诊断原则（3）先熟后生：由于结构和使用环境等原因，某一故障现象可能以某些总成部件的故障最为常见，应先检查这些常见故障部位，若未找出故障，再检查其他不常见的可能故障部位。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p12:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **principle_code_first**: 诊断原则（4）代码优先：电子控制系统一般都有故障自诊断功能，应先读取故障码并检查、排除故障码所指的故障部位；待故障码所指故障消除后，如果故障现象还未消除，再检查可能存在故障的其他部位。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p12:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **principle_think_before_act**: 诊断原则（5）先思后行：对发动机的故障现象先进行故障分析，在了解了可能的故障原因的基础上再进行故障检查。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p12:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **principle_prepare_before_use**: 诊断原则（6）先备后用：检修该型车辆时应准备有关检修数据资料和相关检测工具；也可利用无故障车辆对其系统有关参数进行测量，作为检查同类车辆的检测比较参数。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p12:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **method_visual_diagnosis**: 诊断方法（1）直观诊断：通过人的感觉器官对汽车故障现象进行看、听、嗅等，了解和掌握故障现象的特点，进行分析判断，初步确定出故障范围及部位。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p12:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **method_self_diagnosis_system**: 诊断方法（2）利用自诊断系统诊断：随车诊断是利用汽车电控故障自诊断功能对电控发动机故障进行诊断的方法，即调取发动机电控系统故障码，然后根据故障码表的故障提示快速找出故障所在。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p12:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **method_simple_instruments**: 诊断方法（3）利用简单仪表诊断：如利用万用表对电控发动机故障进行诊断。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p12:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **method_dtc_diagnosis**: 诊断方法（4）故障码诊断法：使用故障诊断仪读取故障码、读取数据流进行检测分析并找出故障原因的一种方法。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p12:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **method_symptom_simulation**: 诊断方法（5）故障征兆模拟试验方法：主要有振动法、加热法、水淋法和电器全接通法四种。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p12:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **method_part_swapping**: 诊断方法（6）部件互换法：将怀疑有故障的电子部件用正常的电子部件替代，以判断故障原因的一种方法。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p12:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **depicted_as_flowchart**: 书中给出汽车故障诊断基本流程（图1-13），该流程以本田HDS诊断仪连接、读取与清除DTC为主线展开。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p12:e3.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **flow_step_intake_and_analysis**: 流程图1-13第一步：询问车主与故障相关的详细信息，包括发生故障的频率、路况、操作情况等；第二步：根据车主的描述进行故障分析。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p13:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **flow_step_connect_hds**: 流程图1-13第三步：将HDS诊断仪连接到诊断插座；如果没有通信，检查检测仪及连接情况。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p13:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **flow_step_read_and_clear_dtc**: 流程图1-13第四、五步：读取DTC（故障码）并将其记录，然后清除DTC。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p13:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **flow_step_confirm_symptom**: 流程图1-13第六步：检查并确认故障症状；若未确认故障，则进行故障症状模拟后回到重新读取DTC。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p13:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **flow_branch_by_dtc_result**: 流程图1-13在重新读取DTC后按结果分支：有故障码时参照具体车型的故障码诊断步骤进行排除；无故障码时执行基本检查，并参考故障症状诊断表。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p13:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **flow_step_locate_circuit_or_part**: 流程图1-13随后：找出故障的电路或元件并执行检查；为确认故障部位，需检查间歇性故障。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p13:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **flow_final_repair_and_recheck**: 流程图1-13收尾步骤：确认故障部位后更换或修理，进行路试并确认故障排除，最后重新连接HDS诊断仪读取故障码并清除。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p13:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **chapter_structure_from_toc**: 据全书目录页，第一章新款本田车系概述含四节：第一节新款本田车系新技术、第二节新款本田车系故障诊断方法、第三节本田专用故障诊断仪、第四节本田故障码表，分别始于印刷页1、8、21、27。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p4:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **name_equivalence_across_text_and_figure**: 正文所述的“VTC油压控制阀”与图1-3中标注的“VTC油控制电磁阀”应为同一部件，仅名称写法不同（模型推断，基于两处描述的功能与位置一致）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p6:e2.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **term_equivalence_across_text_and_figure**: 图1-8图例中的“窜缸水蒸气”与正文所述“窜气混合气”指同一介质（曲轴箱窜气），用词不同（模型推断，基于同一图与同一 PCV 流向语境）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p10:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **tool_identity_with_honda_scanner**: 图1-13流程中使用的“HDS诊断仪”即本田专用故障诊断仪（HDS为Honda Diagnostic System的通行缩写），对应本书第一章第三节“本田专用故障诊断仪”的主题（模型推断，本书在本批范围内未给出HDS全称）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_:ev:p13:e1.  
  Applicability: `{"engine":null,"make":"Honda","model":"本田车系"}`  
- **part_of**: 冷却系统（冷却系）是发动机的组成系统；本书第四章研究对象为『发动机冷却系统的构造与维修』。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p37:e1.  
- **has_component**: 冷却系统的组成包括冷却装置（知识网络『组成』分支之一）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p37:e1.  
- **has_component**: 冷却系统的组成包括冷却强度调节装置（知识网络『组成』分支之一）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p37:e1.  
- **has_component**: 冷却系统的组成包括水温显示装置（知识网络『组成』分支之一）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p37:e1.  
- **has_component**: 冷却装置包括水泵（知识网络标注其学习点为作用、工作原理）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p37:e1.  
- **has_component**: 冷却装置包括散热器（知识网络标注其学习点为作用）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p37:e1.  
- **has_component**: 冷却装置包括风扇（知识网络标注其学习点为作用）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p37:e1.  
- **has_component**: 冷却强度调节装置包括节温器（知识网络标注其学习点为作用；p38 正文明确『节温器是冷却强度调节装置之一』）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p38:e2.  
- **has_component**: 冷却强度调节装置包括百叶窗。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p37:e1.  
- **has_component**: 冷却强度调节装置分支中亦列有风扇（与冷却装置分支重复列出，按知识网络原文登记）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p37:e1.  
- **has_component**: 冷却强度调节装置包括离合器（知识网络原文条目；结合 p38 方法②语境指风扇离合器类装置）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p38:e1.  
- **has_component**: 水温显示装置包括水温表。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p37:e1.  
- **has_component**: 水温显示装置包括水温感应塞。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p37:e1.  
- **has_process**: 冷却系统（冷却循环路线）包括大循环。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p37:e1.  
- **has_process**: 冷却系统（冷却循环路线）包括小循环。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p37:e1.  
- **has_process**: 冷却系统（冷却循环路线）包括混合循环。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p37:e1.  
- **purpose**: 冷却强度调节的目的：发动机使用条件（转速、负荷、环境气温）经常改变，冷却强度必须随之改变，才能保证发动机在有利的温度下工作。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p37:e4.  
- **performs_function**: 冷却强度调节方法①：利用节温器根据冷却液的温度变化自动改变冷却水循环路线和流量，实现冷却强度自动调节。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p37:e4.  
- **mechanism**: 冷却强度调节方法②：利用百叶窗、温控风扇离合器、温控电风扇等改变通过散热器的空气流量来调节（冷却强度）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p38:e1.  
- **performs_function**: 节温器是冷却强度调节装置之一，主要作用是根据冷却系水温度变化控制冷却水的循环路线（大循环、小循环、混合循环）及流量，保证发动机在最适宜温度下工作。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p38:e2.  
- **definition**: 大循环：当发动机水温高于 80℃ 时，节温器主阀门打开、副阀门关闭，冷却水全部由主阀座处进入散热器散热，水温迅速下降，然后再由水泵送入气缸体水套。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p38:e3.  
- **definition**: 小循环：当发动机水温低于 70℃ 时，节温器主阀门关闭、副阀门打开，气缸盖到散热器冷却水道被切断；冷却水由气缸盖水套流出，经节温器副阀座、旁通管进入水泵，并经水泵进入气缸体水套；因不经散热器散热，发动机温度迅速提高。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p38:e4.  
- **definition**: 混合循环：当水温在 70-80℃ 之间时，节温器主、副阀门都处于部分开启状态，此时大、小循环都存在，只有部分冷却水流经散热器进行散热。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p38:e5.  
- **controlled_state**: 大、小、混合循环比较表·大循环行：控制部件为节温器，控制温度 >80℃，节温器主阀门打开副阀门关闭，冷却水全部流经散热器。  
  Source kind: `BOOK_TABLE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p38:e6.  
- **controlled_state**: 大、小、混合循环比较表·小循环行：控制部件为节温器，控制温度 <70℃，节温器主阀门关闭副阀门打开，冷却水不经散热器。  
  Source kind: `BOOK_TABLE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p38:e6.  
- **controlled_state**: 大、小、混合循环比较表·混合循环行：控制部件为节温器，控制温度 70-80℃，节温器主、副阀门都处于部分开启，部分冷却水经散热器。  
  Source kind: `BOOK_TABLE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p38:e6.  
- **replacement_criterion**: 散热器盖蒸气阀开启压力低于 0.126 MPa 时，应更换散热器盖（散热器盖上设有蒸气阀，蒸气阀在规定压力时打开）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p38:e8.  
- **has_component**: 水冷却系主要零部件包括膨胀水箱；教学目标要求重点掌握水泵、散热器、膨胀水箱、节温器等构造及工作原理。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1P_0J0vEH3HmWTTIsDSTVOu-p028CBMa1:ev:p37:e2.  
- **has_subsystem**: 自动变速器包含机械系统，书中按系统分述其故障与诊断，机械系统部件长期使用或使用不当会发生故障。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e1.  
- **has_subsystem**: 自动变速器包含液压控制系统，书中按系统分述其故障与诊断。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e1.  
- **has_subsystem**: 自动变速器包含电子控制系统，书中按系统分述其故障与诊断。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e1.  
- **general_principle**: 书中给出诊断维修程序的总原则：分系统诊断、按一定步骤方法进行，并结合故障难易与诊断方法适配性总结出程序。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e1.  
- **durability_note**: 机械系统部件精度高，正常使用一到二年内一般不发生故障。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e2.  
- **durability_note**: 液压控制系统部件精度高，正常使用一到二年内一般不发生故障。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e2.  
- **common_cause**: 换挡粗糙、挡位不正确等常见故障的第一类原因是油位油质、联动装置调节与发动机怠速方面的不当。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e3.  
- **causes**: 液压控制系统漏油使液压不足，进而造成换挡打滑、延迟。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e3.  
- **manifests_as**: 电控系统是继油位油质类和漏油类之后较易发生故障的部位，故障表现包括没有某一挡、不能上挡等。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e3.  
- **alias**: ECU/ECM/PCM 是书中对汽车电子控制单元（电脑）的简称写法。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e3.  
- **failure_mode**: 长期或不当使用下机械/液压部件故障集中于离合器制动器磨损粘滞，阀体类高精度部件一般不出故障。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e4.  
- **method**: 诊断采用排除法：逐步排除不可能原因后确定具体故障部位。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e5.  
- **has_first_step**: 故障诊断的第一步往往是自动变速器的基础检查，用以先排除油位不当、油质不佳、联动机构及发动机本身状态不佳和漏油等引起的故障。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e5.  
- **uses_discriminator_test**: 要区分故障是电子控制系统引起的还是机械系统和液压控制系统引起的，可以通过自动变速器的手动换挡试验来鉴别。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e5, book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p12:e4.  
- **differentiated_from**: 机械系统和液压控制系统故障的区别要通过机械试验来进行，书中列举的机械试验包括液压试验、失速试验、时间滞后试验、变矩器试验、道路试验等。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p9:e1.  
- **final_step**: 诊断流程收尾：按故障所属系统选用不同诊断方法确定具体部位。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p9:e1.  
- **documented_by**: 自动变速器故障的检修步骤可按图1-1所示的步骤进行。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p9:e1.  
- **defines_step**: 图1-1 流程第(1)步为基础检查。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e6.  
- **defines_step**: 图1-1 流程第(2)步为检查发动机和液力变矩器。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e6.  
- **defines_step**: 图1-1 流程第(3)步为检查自动变速器：分别检查离合器、制动器和齿轮损伤情况，并检查管道压力（框内原印用词为『管道压力』）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e6.  
- **defines_step**: 图1-1 流程第(4)步为测量管道压力并进行液压管路的基础检查。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e6.  
- **defines_step**: 图1-1 流程第(5)步为进行道路试验以检查自动变速器。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e6.  
- **terminal_step**: 图1-1 流程终点为『就车修理』。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e6.  
- **branch_step**: 图1-1 中从道路试验步骤分支出『对自动变速器进行大修』的处理路径。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e6.  
- **verified_by**: 图1-1 注(2)：检查发动机和液力变矩器环节对应失速试验，试验后视需要修理。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e6.  
- **verified_by**: 图1-1 注(3)：检查自动变速器环节对应时滞试验，注文为『通过道路试验来确定，视需要修理』（按图注原印登记，表述与正文延时试验定义存在张力，见 open_questions）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e6.  
- **verified_by**: 图1-1 注(4)：测量管道压力环节对应液压试验，注文为『通过道路试验以确认变速点和振动程度，视需要进行修理』（按图注原印登记，见 open_questions）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e6.  
- **purpose**: 道路试验可确认故障是否在变速器本身；噪声或异常振动时需排查压缩机、发动机、传动轴、轮胎等非变速器部位。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e6.  
- **has_step**: 维修前准备工作第一项是故障征兆的确认。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p9:e2.  
- **has_step**: 维修前准备工作第二项是读出故障码。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p9:e2.  
- **has_step**: 维修前准备工作第三项是查对常见故障（诊断）表。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p9:e2.  
- **requires_user_interview_and_simulation**: 诊断前要请用户详细认真填写自动变速器故障分析表（表1-1）并详细询问故障情况，在此基础上摸索重现故障征兆、通过模拟来确认；因用户可能分辨不清征兆与正常现象、有的征兆不时时出现且描述可能不完整，只有通过维修人员模拟试验才能最后确认是否有故障。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p9:e3.  
- **covers**: 表1-1 用于结构化登记用户与车辆信息、故障发生规律、12 类故障现象勾选、故障指示灯状态与两次故障码检查结果。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p9:e4.  
- **mechanism**: AT 自诊断系统在出现故障时把相应故障码存入电控单元，供诊断修理使用。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p9:e5.  
- **diagnostic_value**: 读码有/无分别对应不同初判：有码指向电控系统，无码指向液压、机械或其他部位。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p9:e5.  
- **scope_note**: 具体各公司故障码读取方法与含义不在本书本章内容内，指向外部书籍。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p9:e5.  
- **rationale**: 查常见故障诊断表的价值在于缩小范围、缩短时间、提高效率。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p9:e6.  
- **definition**: 基本检查定义为对最常见故障原因相关部件的检查与重新调整，任何故障诊断都要首先进行。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e1.  
- **has_check_item**: 基本检查项目包括油面检查。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e2.  
- **has_check_item**: 基本检查项目包括油质检查。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e2.  
- **has_check_item**: 基本检查项目包括液压控制系统漏油检查。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e2.  
- **has_check_item**: 基本检查项目包括节气门拉索检查和调整。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e2.  
- **has_check_item**: 基本检查项目包括换挡操纵手柄位置检查和调整。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e2.  
- **has_check_item**: 基本检查项目包括超速挡控制开关（O/D）的检验。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e2.  
- **has_check_item**: 基本检查项目包括发动机怠速检查。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e2.  
- **requires_precondition**: 进行基本检查前须确认发动机、底盘尤其制动系统状态正常。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e2.  
- **interval**: 油面检查的时机：任何检查诊断之前，以及每行驶 1500～2000km 定期进行。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e3.  
- **method_step**: 油面检查第一步：水平地面、拉手制动、怠速运转至少 1 分钟。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e4.  
- **method_step**: 油面检查第二步：各挡位轮换停留充油后把手柄回到 P 位。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e4.  
- **method_step**: 油面检查第三步：拔油尺擦净、复插再拔出读油面高度。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e4.  
- **interpretation**: 油面合格区间随油温不同：冷态看下限、热态看上限。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e5.  
- **corrective_action**: 油面过低先补油到标准，再运转检查泄漏点，漏油立即修复。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e5.  
- **reference_interval**: ATF 使用/更换参考周期：正常工作温度下 40000km 或 24 个月。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e6.  
- **temperature_factors**: 油温是油质与寿命的关键变量，其升高源于变矩器故障、执行元件滑转、单向离合器滑转或油冷却器堵塞，属危险信号。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e6.  
- **harm**: 油温过高的六类危害最终导致自动变速器损坏。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e7.  
- **inspection_method**: 油质检查采用嗅味+搓检渣粒，按变质程度分三级处置：换油复检、拆检油底壳、立即拆修。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e8.  
- **maps_state_to_cause**: 表1-2 第1行：清洁带红色为正常 ATF 状态。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e9.  
- **maps_state_to_cause**: 表1-2 第2行：油中金属屑指向摩擦片或单向离合器严重磨损。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e9.  
- **maps_state_to_cause**: 表1-2 第3行：油尺胶质油膏对应油温过高。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e9.  
- **maps_state_to_cause**: 表1-2 第4行：烧焦味对应油温高油面低或油冷却器/管路堵塞两类原因。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e9.  
- **maps_state_to_cause**: 表1-2 第5行：油色极深对应未及时换油或重载/打滑损坏致过热。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e9.  
- **maps_state_to_cause**: 表1-2 第6行：加油管溢油对应油面过高或通气孔堵塞。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e9.  
- **maps_state_to_cause**: 表1-2 第7行：清淡无黏性对应油变质。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e9.  
- **maps_state_to_cause**: 表1-2 第8行：油液发白对应油中进水。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p10:e9.  
- **method**: 漏油检查对象为各连接处油封封垫，漏油通过降压引起打滑延迟，须逐一排查易漏部位。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p11:e1.  
- **method**: 节气门拉索检查标准：全闭/全开动作正常，索芯不松弛，索套端至索芯上限位杆间距 0～1mm。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p11:e2.  
- **method**: 手柄位置失准的三类后果：挂不进挡、指示灯显示不符、空挡/停车挡无法启动。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p11:e3.  
- **method**: 怠速检查规范：先查怠速再做进一步检查，手柄置 P/N，参考值 750r/min，偏高偏低均需调整。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p11:e4.  
- **requires_precondition**: O/D 检验的前提是蓄电池电压正常，否则自诊断系统会误诊断。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p11:e5.  
- **method**: O/D 检验流程与判读：灯熄灭为正常，闪烁为有故障，转故障码读取与车型码表排查。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p11:e5.  
- **has_test**: 性能测试第(1)项为道路试验。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p11:e6.  
- **has_test**: 性能测试第(2)项为失速试验。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p11:e7.  
- **has_test**: 性能测试第(3)项为油压试验（图1-1 注中称液压试验）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p12:e2.  
- **has_test**: 性能测试第(4)项为延时试验（第1问机械试验枚举中称时间滞后试验、图1-1 注中称时滞试验）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p12:e3.  
- **has_test**: 性能测试第(5)项为手动换挡试验。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p12:e4.  
- **purpose**: 道路试验兼具故障诊断与修后质检双重用途。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p11:e6.  
- **covers**: 道路试验三大观察内容：换挡车速、换挡质量、执行元件打滑。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p11:e6.  
- **requires_precondition**: 路试前置：中低速 5～10min 热车；O/D 开关 ON、模式开关普通/经济模式。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p11:e6.  
- **definition**: 失速工况/失速转速定义：D 或 R 挡制动踩死+全油门下涡轮停转、仅泵轮壳体随转，此时发动机转速即失速转速。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p11:e7.  
- **verifies**: 失速试验的检查对象：发动机输出功率、变矩器、换挡执行元件。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p11:e8.  
- **standard_value**: 失速转速标准值因车型而异，书中给出常见量级约 2300r/min。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p11:e8.  
- **interpretation**: 失速转速三段判读：相符=基本正常，偏高=油压低或打滑，偏低=动力不足或变矩器故障。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p11:e8.  
- **mechanism_case**: 书中以导轮单向超越离合器打滑为例说明失速转速偏低的机理链：偶合器工况→变矩比下降→负荷增大→转速下降。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p11:e8.  
- **maps_condition_to_causes**: 表1-3 第1行：任何挡位都失速过高的三类原因。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p11:e9.  
- **maps_condition_to_causes**: 表1-3 第2行：任何挡位都失速过低的两类原因。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p11:e9.  
- **maps_condition_to_causes**: 表1-3 第3行：仅在 D 位失速过高的两类原因（原印『前进离合器』）。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p12:e1.  
- **maps_condition_to_causes**: 表1-3 第4行：仅在 R 位一行原印标『过低』并给出倒挡油压/倒挡及高挡离合器两类原因；该行与正文判读逻辑存在张力，照原印登记。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p12:e1.  
  Counterexamples: 与正文『失速转速低于标准值→发动机动力不足或液力变矩器有故障』及表内『所有位置过低』行的成因模式不一致，疑误印（见 claim 0101 与 open_questions）
- **purpose**: 油压试验定义与地位：运转中测各油压支撑故障分析，正确油路油压是正常工作的先决条件。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p12:e2.  
- **interpretation**: 油压双向危害：过高→换挡冲击、损坏控制系统；过低→打滑、磨损、烧毁执行元件。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p12:e2.  
- **timing**: 油压试验的时机：分解修理前与修复后都要做，防止只换摩擦片不查真因的复发。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p12:e2.  
- **definition**: 延时试验定义：测 N→D/N→R 接合迟滞时间以判断主油路油压与执行元件状态。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p12:e3.  
- **standard_value**: 迟滞时间参考上限：N-D 小于 1.0～1.2 秒、N-R 小于 1.2～1.5 秒。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p12:e3.  
- **interpretation**: 迟滞过长的分方向归因：N-D 指向前进侧油压/离合器/单向超越离合器，N-R 指向倒挡侧油压/离合器/制动器。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p12:e3.  
- **purpose**: 手动换挡试验定位与排序：用于三系统区分，排在读码和基本检查之后、其他检查之前。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p12:e4.  
- **method**: 手动换挡试验操作：脱开全部换挡电磁阀插头、手动挂挡，挡位仅由手柄决定，且挡位-手柄对应关系因车型而异。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p12:e4.  
- **capability**: 自诊断电路能力边界：行驶中持续监测、可检出大部分（非全部）控制系统故障并以代码存储。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p12:e5.  
- **usage**: 电脑检测仪的接入方式：专用插座位置（发动机附近或仪表板下方）+连接后接通点火开关即可检测。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p12:e6.  
- **reads_dtc**: 检测项目 1)读取故障码：读码并显示含义，作为控制系统检修依据。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p12:e7.  
- **data_stream**: 检测项目 2)进行数据传送：串行输出瞬时数值→数据流显示→据变化判断或指令-反应比对；本页内容不完整。  
  Source kind: `BOOK_BODY_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p12:e7.  
- **operation_caution**: 模型补充常识：失速试验为全负荷工况，须控制持续时间防止油温过高（书中未述）。  
  Source kind: `MODEL_INFERENCE`; status: `EXTRACTED_UNCHECKED`; evidence: NONE.  
- **suspected_misprint**: 模型推断：表1-3 R 位行的失速转速标签存在误印可能，倾向应为『过高』（仅为推断，未改动原文登记）。  
  Source kind: `MODEL_INFERENCE`; status: `EXTRACTED_UNCHECKED`; evidence: NONE.  
- **preliminary_check_items**: 图1-1 注(1) 给出基础检查环节『初步检查』的六个子项及处置原则（视需要修理）。  
  Source kind: `BOOK_FIGURE_DIRECT`; status: `EXTRACTED_UNCHECKED`; evidence: book:1jDTXgUQ5NSX-YyBkMFuKnrwmhec4F84E:ev:p8:e6.  
