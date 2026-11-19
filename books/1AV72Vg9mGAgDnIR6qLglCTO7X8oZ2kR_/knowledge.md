# Automotive book knowledge (canonical-derived)

Source: `book:1AV72Vg9mGAgDnIR6qLglCTO7X8oZ2kR_`

Review: `GENERATED_REVIEW_PENDING`

This is an original summary, not a reproduction of source text; scope and evidence follow each claim.

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
