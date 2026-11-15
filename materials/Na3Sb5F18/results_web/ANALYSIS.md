# Na₃Sb₅F₁₈ / mp-28286：附件复核与用途判断

**判断：这条1200 K轨迹确有多Na的大范围运动，但它发生在明显活动的Sb/F环境中，且局部返回很多、运动随时间改变。现在应优先确认结构状态与Na/F分别承担的输运，而不是把它列为已证实的固态快钠电解质，或直接开始“减Na造空位”的优化。**

科学独立接受状态：**UNVERIFIED**。本次是对上传派生数据的复核、描述性重算与公开资料核对，不是原始AIMD重跑、独立科学验收或发表授权。未启动新AIMD、DFT、NEB、模型训练；未构造掺杂坐标。

## 输入核对：实际读到了什么

实际读取21个附件：3个Markdown、6个JSON、9个CSV、3张PNG。9个CSV合计60,990数据行。下面I01–I21为内部定位号；没有压缩附件、没有打不开的附件。CSV行数不含表头；文中CSV“第几行”含表头。JSON按event_id、na、窗口和字段定位。所有附件均计算SHA-256，见RESULT_META.json。列出文件不代表读过它所引用的其他文件。

I01 `core__REPORT.md`：全文200行（splitlines计数），作为待核解释。

I02 `core__data__full_windows__results__ALL_EVENT_CONTROL_PHASES.csv`：1494数据行。列：`window,event_id,Na_id_0based,kind,interval_start_ps,interval_end_ps,phase_first_frame,phase_last_frame,actual_phase_samples,expected_full_phase_samples,complete_plusminus200fs_phase,CN28_min,CN28_max,CN28_mean,adjacent_knn6_Jaccard_mean,distinct_F_in_phase_knn6,causal_contrast`。

I03 `core__data__full_windows__results__ANALYSIS_SUMMARY.json`：全文解析。顶层15字段：`formula,mp_id,run,windows,temperature,unwrap,event_recheck,reference_regions,F8_layers,new_full_resolution_Na_environment_frames,old_stream_verification_n,original_plot_audit,single_run_not_independent_material_replicates,scientific_acceptance,publication_authorized`。windows内含逐Na端点向量、r90、最大探索、保存步路程和离返；F8_layers含配位计数、周期秩、接触身份变化数。

I04 `core__data__full_windows__results__Na_individual_summary.csv`：24数据行。列：`window,Na_id_0based,Na_atom_1based,endpoint_A,r90_A,max_from_start_A,leave_return_pairs,path_saved20fs_A,unreturned_last_leave_frame,CN28_mean,CN28_min,CN28_max,unique_F_ever_in_knn6,knn6_final_vs_first_Jaccard`。

I05 `core__data__full_windows__results__REFERENCE_REGION_SUMMARY.json`：全文解析。六组合键：`translation:0.6,translation:0.8,translation:1.0,rigid:0.6,rigid:0.8,rigid:1.0`；每组含总访问、至少200fs访问、其他Na访问、访问者、末端指派和位点全集不完整标志。

I06 `core__data__strict__CLAIM_LEDGER.json`：全文解析，12条旧主张；顶层`schema,claims,scientific_acceptance,independent_review_completed,publication_authorized`。旧“已支持”标签不是本次自动接受结论。

I07 `core__data__strict__results__JOINT_EVENT_INTERVALS.json`：459记录；字段`na,start_frame,end_frame`。

I08 `core__data__strict__results__MSD_CURVES.csv`：2000数据行。列：`reference,lag_ps,origins_per_Na,all_origins_MSD_A2,first_origin_MSD_A2`。

I09 `core__data__strict__results__MSD_FITS.csv`：12数据行。列：`reference,estimator,lower_ps,upper_ps,n_points,slope_A2_per_ps,intercept_A2,r2,alpha_loglog,D_exploratory_cm2_s,independent_origins,transport_qualified`。

I10 `core__data__strict__results__PER_NA.csv`：24数据行。列：`na,endpoint_A,endpoint_vector_A,max_from_start_A,r90_A,path_A,leave_return_pairs,leave_return_times,unreturned_last_leave_frame,exposure_Na_ps,leave_return_rate_per_Na_ps,endpoint_returned,Na_atom_1based`。

I11 `core__data__strict__results__PHASE_AGGREGATES.csv`：582数据行。列：`CN28_max,CN28_mean,CN28_min,Na_index0,actual_samples,causal_contrast,distinct_F_in_phase,event_id,expected_samples,kind,phase_first_frame,phase_last_frame,status`。

I12 `core__data__strict__results__SUMMARY.json`：全文解析，顶层37字段：`formula,mp_id,run,frames,Na_count,start_absolute_ps,end_absolute_ps,span_ps,sampling_fs,no_physical_zero_frame,previous_common_frames,previous_common_abs_end_ps,contribution,mean_endpoint_A,mean_r90_A,leave_return_pairs_to_window_origin,candidate_count,candidate_sensitivity,outcomes_singlepoint_labels_not_site_truth,valid_controls,unique_control_ids,control_reuse_max,union_sources,complete_closed_event_phases,complete_halfopen_dwell200,global_return200_states,local_reused_return200_states,local_geometry_missing_changed_intervals,local_geometry_not_recomputed,control_local_dwell,phase_sample_rows,phase_aggregate_rows,Na_environment_samples_in_window,raw_trajectory_read,full_rerun,scientific_state,publication_authorized`。

I13 `core__figures__full_windows__figures__MSD_host_temperature.png`：已查看2048×1489像素图，full分支。

I14 `core__figures__full_windows__figures__individual_Na_environment.png`：已查看2048×1675像素图，full分支。

I15 `core__figures__full_windows__figures__selected_periodic_edges_and_motion.png`：已查看2048×1194像素图，full分支。

I16 `core__methods__full_windows__METHODS.md`：全文31行。

I17 `core__methods__strict__METHODS.md`：全文23行。

I18 `details__data__full_windows__results__Na_environment_20fs.csv`：36000数据行。列：`frame,time_ps,Na_id_0based,from_first_A,F_CN28,knn6_F_ids,adjacent_knn6_Jaccard,step20fs_A`。

I19 `details__data__full_windows__results__event_environment.csv`：747数据行。列：`window,event_id,Na_id_0based,start_ps,end_ps,global_fixed200_A,local_fixed200_A,global_returned,local_returned,post_window_missing,Na_F_CN28_before,Na_F_CN28_mid,Na_F_CN28_end,knn6_Jaccard_start_end,F_rotation_deg,F_nonrigid_RMS_A,control_id,control_CN28_before,control_CN28_end,event_full_phase_legal`。

I20 `details__data__strict__results__EVENTS.json`：全文解析，291记录。主要字段：`event_id,na,start_frame,end_frame,start_relative_ps,end_relative_ps,disp_A,net_disp_A,path_A,merged_straightness,d_min_A,detection_window_fs,post_distance_A,post_full,outcome,site_transition_proven,start_absolute_ps,end_absolute_ps,control,global_dwell,local_fixed_ligand_dwell,fixed_ligand_atom_ids,ligand_rigid_fit_archived,local_geometry_status,control_local_dwell,control_local_dwell_reason,control_global_dwell200,environment_five_points`。

I21 `details__data__strict__results__PHASE_SAMPLES.csv`：20107数据行。列：`event_id,Na_index0,kind,phase_first_frame,phase_last_frame,complete_closed_phase,frame,absolute_ps,F_CN28,nearest_F6_indices0,adjacent_knn6_Jaccard,from_first_A`。

### 身份、时标、估计器

I03、I12、I16明示Na3Sb5F18、mp-28286、run=aimd_1200K。逐Na表、事件表和36000行环境表以Na编号、帧、端点数值互相吻合。24个Na的数据网格完整；方法/报告记载40Sb、144F、208原子，即八个化学式单元。40×1500=60000也与四层Sb配位计数总和一致。没有初始CIF/POSCAR或元素列表，组成与结构身份核到派生文件内部一致，不声称从原始结构重新鉴定。无mp字段的CSV通过这些对应关系归属，不靠上传顺序。

名义温度1200K。I03.temperature记录原温度序列15000点、峰13369K；本次只读摘要和I13图，没有读取那15000点温度原件。20fs保存间隔在I18所有帧时间中核实；POTIM=2fs、NBLOCK=10来自I17，不是本次读取INCAR。首保存帧绝对时间0.02ps，没有物理t=0帧。以下案例默认相对首保存帧时间，绝对时间加0.02ps。

|分支/窗口|帧号及帧数|相对时间ps|绝对时间ps|本次证据范围|
|---|---|---|---|---|
|strict1000|0–999；1000|0–19.98|0.02–20.00|完整派生事件、相位、逐Na、MSD曲线及拟合|
|历史common20|0–1000；1001|0–20.00|0.02–20.02|主摘要、事件环境、相位汇总、环境标量截取|
|full|0–1499；1500|0–29.98|0.02–30.00|逐Na环境完整，事件/相位汇总；无full三维坐标或MSD曲线CSV|
|late20_29p98|1000–1499；500|20.00–29.98|20.02–30.00|I03重置起点指标、端点向量|
|after1ps|50–1499；1450|1.00–29.98|1.02–30.00|窗口摘要；不同于温度绝对1ps后|
|after4ps_absolute|199–1499；1301|3.98–29.98|4.00–30.00|窗口摘要；不同于旧生产段相对4.00/绝对4.02ps|

这些是同一运行的嵌套/相邻窗口，不是独立重复。common20与后段共享frame1000；strict截止999。三张原图均为full分支，图中common20为历史1001帧，不是strict新图。

主逐Na距离和事件整体参考为全非Na宿主平均平移扣除，不假定质量加权质心。I08/I09只有host_translation_subtracted和raw，没有strict刚体对齐曲线。full三参考比较只有图与方法描述。局部参考固定事件开始的六F身份，仅扣共同平移，不是每帧换一套近邻，也不是完整静止笼子。

首原点MSD为各Na的from_first_A平方平均；所有原点MSD为相同时间差三维位移平方平均。标量离起点距离不能恢复任意两帧三维位移。本次能重算host首原点MSD和重拟合已存曲线，不能声称从原轨迹重算all-origins、raw、局部F或Sb/F MSD。strict lag10ps每Na有500重叠原点，lag19.98ps只剩1个；这些不是重复实验。[I08–I09、I16–I18]

未上传：原始Na/Sb/F三维轨迹、晶胞/CIF/POSCAR、OSZICAR/OUTCAR/vasprun.xml、完整Sb-F逐接触/周期边流、区域逐访问记录、full原始事件JSON/full MSD曲线、旧xlsx/来源审计、运行日志、能量/能垒/力/压力。报告声称过去核过不等于本次已读。本次未访问报告私人路径，未以仓库清单替代输入。

## 一、核心判断

**已支持：多人走远，后段更强。** full末端MSD50.17738Å²，24/24端点超过3Å；strict为15.01189Å²、12/24。最大单Na贡献full平方位移总和12.48%，前三31.29%，不是一两颗原子独撑曲线。[I18重算；I03、I10、I12]

**部分支持：运动与动态F配位环境同现；不足：稳定晶格空位跳跃或单一旋转开门机制。** 事件期换邻居稍多，但控制也在换；相同CN可对应远移与返回，局部参考还会改变返回标签。[I02、I11、I19–I21]

**反例否定：persistent等于永久迁移。** strict202个persistent中22个结束已返、146个后来返回、34个截止未见返回。168/202在固定中心定义下返回；两个操作指标不等价。几何连通是否对应真实通过、低Na密度是否意味着空位多，则是证据不足；初始24球不是完整位点容量。[I20逐条计数；I05]

**不足：室温电导及器件资格。** 1200K单次短轨迹、启动过冲、宿主活动和估计器差异不能给出室温Na电导、电化学窗口、电子绝缘、机械强度或真实可逆容量。[I03、I08–I09、I13]

最值得检验的限制环节不是默认空位不够，而是能否在明确、可保持的结构中形成连续且可重复的Na交换，并区分F/宿主重排和电子导电。

## 二、Na运动与具体环境对应

### 2.1 时间窗决定看到什么

|窗口|平均端点Å|平均r90Å|端点MSDÅ²|端点>3Å|前三贡献|
|---|---:|---:|---:|---:|---:|
|strict1000|3.54654|3.17046|15.01189|12/24|28.0919%|
|历史common20|3.55057|3.17640|15.03528|13/24|28.0284%|
|full|6.70056|6.15237|50.17738|24/24|31.2881%|
|后段20–29.98ps重置起点|5.29652|5.59255|33.04019|20/24|30.3408%|

前三行由I18标量重算并核对I03/I10/I12。后段为I03摘要，本次额外核full端点向量−common端点向量=late向量，误差<9×10⁻¹⁶Å，不声称重算后段整条轨迹和r90。

strict比common端点MSD低0.155565%，但Na7由2.94583到3.08616Å跨3Å，计数12变13。20fs边界也须分清。full首原点MSD在相对10/15/20/25/29.98ps为1.44169/3.63537/15.03528/33.88689/50.17738Å²；10ps时没有Na端点超过3Å，最后全部超过。[I18 frame500/750/1000/1250/1499]

r90是该Na距本窗起点距离的90百分位，不是90%的Na走多远、不是速度。I18保存步折线路程求和与I04/I10路径一致至1.2×10⁻¹³Å，但包含振动与折返，不等于净输运。

### 2.2 全部24个Na

按I10、I04、I03后段metrics的零基na对齐。正文统一一基。起点球离返是先离起点>1Å再到<0.5Å，不是晶格跳回。

|Na|strict端点Å|full端点Å|full r90/最大探索Å|后段重置端点Å|full起点球离返对|full平方位移贡献|
|---:|---:|---:|---:|---:|---:|---:|
|1|5.978|7.951|8.243/9.582|3.619|15|5.25%|
|2|3.932|9.563|8.253/10.389|8.678|17|7.59%|
|3|5.261|5.702|5.433/6.629|6.394|11|2.70%|
|4|2.699|6.879|4.939/7.637|6.192|10|3.93%|
|5|5.765|12.258|10.554/13.489|7.334|17|12.48%|
|6|1.750|3.903|3.214/5.624|3.889|18|1.27%|
|7|2.946|8.285|8.172/9.873|6.565|14|5.70%|
|8|2.796|6.928|6.067/7.033|6.924|12|3.99%|
|9|1.685|4.104|5.255/6.305|3.892|21|1.40%|
|10|2.815|7.070|6.953/8.019|4.392|13|4.15%|
|11|1.898|3.765|3.269/5.684|4.640|7|1.18%|
|12|2.410|3.788|3.937/4.703|4.033|5|1.19%|
|13|4.029|3.466|4.002/5.380|1.539|13|1.00%|
|14|1.142|6.619|5.676/8.275|6.227|13|3.64%|
|15|2.193|7.562|6.043/8.511|9.215|9|4.75%|
|16|3.827|7.303|6.368/7.742|6.514|12|4.43%|
|17|0.871|6.147|5.622/6.973|5.840|17|3.14%|
|18|5.093|6.658|6.147/7.166|2.155|14|3.68%|
|19|5.185|11.623|11.151/12.993|8.964|10|11.22%|
|20|5.678|6.561|6.668/8.936|5.016|9|3.57%|
|21|4.713|3.931|4.045/5.482|2.349|14|1.28%|
|22|5.007|6.453|6.552/8.444|1.591|18|3.46%|
|23|5.017|8.939|6.385/8.939|7.828|8|6.64%|
|24|2.428|5.355|4.711/5.795|3.327|16|2.38%|

Na5/19/2是full贡献前三，strict前三为Na1/5/20。Na5端点12.258Å、最大13.489Å，是远移例。Na13端点最小3.466Å，但探索至5.380Å，不能叫不动；其后段端点1.539Å，主要是后段相对局部的活动和折返。Na17 strict仅0.871Å，full6.147Å、后段5.840Å，早段返回不等于永久锁住。Na15后段9.215Å甚至大于full7.562Å，距最早起点不能替代后段真实位移。[I03、I04、I10]

Na6在相对28.98ps再次回到最初0.5Å球，之后离开、末端3.903Å。full313对起点球返回中312对strict已出现，新增一对是Na6。这不意味着后段只有一次局部返回，因为事件前球是另一种中心。[I18状态机重算；I03.full.metrics na5]

### 2.3 full与strict的事件、控制、返回、删失

规则为200fs净位移≥1.5Å且直度≥0.7，合并重叠/相邻候选；合并后可低于单窗阈值。固定200fs前后中心各10样本，首末样本跨度180fs；检测200fs是10个保存间隔，不能偷换。[I16–I17]

|项目|strict1000|full|
|---|---:|---:|
|1.5Å候选数|291|456|
|1.2/1.8Å敏感性候选数|395/156|621/249|
|控制使用/唯一ID/最大复用|291/254/4|456/397/4|
|完整事件闭相位/截断|287/4|451/5|
|完整控制闭相位|291|456|
|全局：已返/右删失未见/缺中心|253/34/4|370/81/5|
|局部：已返/右删失/缺中心/无几何项|265/22/3/1|393/58/5/0|
|重新匹配控制局部中心|291项均null|未提供完整控制局部中心序列|

strict全局253=41结束已返+212后来返，局部265=81+184；局部复用分母290，Na15改变边界缺项不能补成未返回。缺全局前/后中心为event65/183/220/258，即Na6/15/18/21。full CSV核到370返、81未见、5空；56结束已返/314后来返只在原报告，未上传full首次返回帧，不能称本次独立重算。full persistent/transient完整标签清单也未上传。[I12、I19、I20；I01仅补充引用]

full有49个完整事件全局/局部结果不同：36全局未见而局部返，13相反。完整451个事件中心分离均值全局1.3441、局部1.2072Å，但不是每个都下降。局部F平均转13.1135°、非刚性残差0.8705Å，它们不是静止笼。[I19新计数/均值]

本次重建459联合去重区间；strict291控制完整闭相位均避开同Na全部[start−10,end+10]联合禁区，接触边缘也排除。full456控制按full全部事件检查亦通过。合法性仅针对检测器识别的候选，不保证排除漏检运动。1494历史相位、582strict汇总由I18重算一致；20107strict逐帧对应无不匹配。[I02、I07、I11、I18、I20–I21]

不同control_id仍会重叠。full控制相位15880次Na-帧使用仅7298不同Na-帧；strict10068次仅4775不同Na-帧。控制中点平均比事件晚1.313/1.043ps，422/456和256/291选在后面。在非平稳轨迹中，结构年龄/热历史仍是混杂，不能用行数做独立样本显著性检验。[本次集合/中点计算]

**字段修正：**I19的747行Na_F_CN28_before全部对应事件起始帧CN，不是前200fs均值。9行缺后窗却仍event_full_phase_legal=True；完整性要看I02 actual/expected与complete_plusminus200fs_phase。full和strict不可只按event_id拼接，须Na+起止帧+窗口。

### 2.4 同一个Na的两种结局

**反例Na1 event0：相对0.96–1.20ps，绝对0.98–1.22ps。** CN5→3→5，六F集合Jaccard=1/3；净位移1.7855Å，但固定中心全局只分离0.3147、局部0.5702Å，结束已回前球。距最早起点反而从1.4164降至0.4507Å。短时移动较大、邻居更换，不等于向外有效跳跃。[I20 event0；I19第2行；I18 Na0 frame48/54/60]

六F全原子零基身份起始{118,120,124,184,197,206}，结束{65,124,156,184,192,197}，换3个；CN恢复不等于原笼恢复。同Na控制81–93帧（相对1.62–1.86ps，绝对1.64–1.88ps）中心分离0.3983Å，完整相位涉及12F，超过事件11F。换邻居不是远移充分条件。[I20 control_global_dwell200；I02 event0]

**远移Na1 event10：相对15.52–15.78ps，绝对15.54–15.80ps。** CN5→4→5，但六F由{121,125,136,170,184,202}变为{93,115,153,174,189,202}，只保留202，Jaccard=1/11。距最初起点0.4659→2.8052Å；中心全局2.2951、局部2.5179Å。局部F转12.42°，残差1.6051Å，不是刚体笼。[I19第12行；I20 event10；I18 frame776–789]

strict只能说其后4.20ps内未返，full表也记末端未观察到返回，但缺full首次返回/逐局部坐标，不能说永久不可逆。其控制frame810–823（相对16.20–16.46ps）也有1.1183Å中心分离，并在frame828返回；控制不是静止同义词。[I20 control_global_dwell200]

两事件起末CN都恢复5，却留下0.315和2.295Å中心差。具体身份、中心、参考敏感性、随后去向比一个CN值更有解释力。缺F所属Sb列表、逐键长角度、瓶颈坐标，不能编成“特定SbF单元先转动、门打开、Na沿灰线进下一位点”的完整因果链。

### 2.5 Na5远移、Na13回摆与配对控制

Na5 full event89，相对26.24–26.58ps（I19第91行），CN6→4→6，J=0.2，中心全局2.5145/局部2.3490Å，至29.98ps未返，仅3.40ps随访。完整相位CN5.5526，控制5.2895；远移事件不总比控制低配位。[I02 full event89]

Na13 full event243，相对28.90–29.12ps（I19第245行），CN6→6→5，F转19.723°，中心0.9693/0.7595Å，两参考返回；相位9F、控制10F。Na5和Na13全程分别接触62/60个最近F身份，平均CN5.3487/5.1647，走远者并无更低平均CN。[I04；I02 event243]

|描述量|full事件/控制，451完整对|strict事件/控制，287完整对|
|---|---:|---:|
|平均2.8Å内F数|5.1228/5.2822|5.1490/5.2711|
|相位不同最近F身份数|11.5898/10.6319|11.4808/10.6829|
|相邻帧Jaccard均值|0.88761/0.89253|不作独立统计推断|

full配对CN均差−0.1594，先各Na求差再Na等权为−0.1645；不是某Na事件多单独造成。前10帧/期间/后10帧CN full5.1608→5.0612→5.1800，strict5.1704→5.1113→5.1864。最低在期间，未证明确提前门控信号。事件又按Na移动筛选，Na本身移动就会换邻居。目前支持伴随，不支持F变化先因、Na移动后果。结束CN恢复也不保证返回。[I18、I02/I11；前后半开窗，期间含端点]

Na5 full最后event93（29.76–29.98ps）缺完整后窗，不能宣称永久留在新位置；Na1 event12（25.84–26.06ps）全局未见返回、局部见返回，进一步说明参考敏感性。[I19按Na/时段定位]

## 三、机制解释、竞争解释与反例

### 3.1 Sb-F主/次层是距离截断层，不是已证晶体学层

本材只有Na、Sb、F，无O、PO₄等；Sb是唯一非Na阳离子。I03.F8_layers四半径各60000个Sb-帧计数：

|截断Å|由计数算平均CN|众数CN|共享F图周期秩|
|---|---:|---:|---|
|2.4|3.9667|4，占55.41%|1398/1500秩0，100秩1，2秩2|
|2.7|5.0048|5|1092/1500秩3|
|3.0|5.9955|6|1492/1500秩3|
|3.3|6.9914|7|全部1500秩3|

汇总层支持短接触多为局部构件、较远接触形成周期网络；不足以认定永久SbF₆骨架、唯一二维层或Na三维通道。2.4Å每Sb身份变化497–638次，3.3Å仍462–553次；能连上不等于具体邻居不变。热振动跨阈值也可计变化，不能逐次称断键/重构。未读逐接触流，无法把某Na事件接到具体Sb中心及变化先后。[I03、I16]

I01的301基础帧共棱0–6/共面0–1、壳层±0.1Å敏感性、61帧开放比例0.612/0.332/0.113缺底层输入，均为报告引用待复核，不作本次几何结果。无Na–Na排列/占据全表，不能指定Na5沿某晶向或层边通过。[I01；I15投影]

相关K₄Sb₂SnF₁₄一手晶体研究确有Sn(IV)六配位及Sb(III)短/长F接触，支持分开讨论主次接触的化学合理性，但不能把另一化合物层结构移植到mp-28286。[E2]

### 3.2 几何连接到实际交换的缺环

灰色Na共享F边表示规则下相同F及周期像，不是能量路径。Sb-F图、Na距离图、排除宿主空隙图是不同对象。I15将灰边和彩轨并列，不给鞍点或通量。投影相交、三向周期秩、离起点远均不证明沿该边穿过连续低能垒通道。

I05初始球0.6/0.8/1.0Å中其他Na至少200fs访问次数：平移2/6/9，刚体3/8/18。0.8Å平移6次来自零基2/9/21/22/23，即Na3/10/22/23/24这5个Na，不是6独立离子或已证晶格交换。全部末帧指派−1表示不属初始球，不是产生24空位。逐访问记录未上传，原报告Na3访问Na8区域的具体时段仍只是引用。[I05；I03.reference_regions是重复摘要]

还缺随宿主变化可跟踪的稳定位置模型、A→B驻留及B→C继续交换、原占据者离开的时序、跨周期重复通量、独立运行重现和合理自由能/能垒。现在最多支持动态几何区域重用。低Na数密度或每Na空间大不能直接翻译为空位多。

### 3.3 温度、漂移、非刚性和局部参照

峰值绝对0.07ps、相对0.05ps为13369K；I03绝对1/4ps后平均1199.923/1199.946K。后续动能均值接近设定不证明结构忘掉启动冲击。full只有3候选开始于相对1ps前（无候选在1ps前完整结束）、453之后，后段20/24仍远移，否定运动只在尖峰瞬间；不排除尖峰改变结构后长时间松弛。[I03.temperature；I19新计数]

整体漂移不是主因：strict扣平移/原始末端MSD15.01189/14.97919Å²，仅差0.03270Å²，约0.22%；raw/host所有原点2–10ps探索D6.5601/6.6776×10⁻⁶cm²/s。full三参考图接近。报告称full末端宿主平移0.096Å、刚体10.29°、残差8.73Å，本次无坐标复算，保留报告级部分支持，不冒充新核验。[I08–I09、I13、I01]

宿主活动另有摘要支持：full lag10ps所有原点MSD Na17.0174、Sb10.0960、F30.3122Å²，图上各物种首原点也持续增长。因此Na在近乎不动的F骨架穿行不能描述此轨迹；但不足以断言熔化、特定相变、解离或真实F电导。[I03.windows.full.species_all_origin_MSD_10ps_or_shorter_A2；I13]

### 3.4 不能用一个漂亮D收尾

strict host lag10ps所有原点6.60313、首原点1.44169Å²，差约4.58倍。2–10ps拟合探索D分别6.67762×10⁻⁶/1.46765×10⁻⁶cm²/s；所有原点R²0.97160却α0.43920。1–5及5–10ps D为1.18155×10⁻⁵/5.55705×10⁻⁶，差2.13倍。本次12行重拟合误差约2.3×10⁻¹⁶，但只是拟合算术核验。[I08–I09]

α偏离1、曲线有截距，不能因R²高认定长时Fick扩散；α也不能独诊异常扩散机制。strict最大lag19.98ps不能冒充完整10–20ps拟合。报告full D0.267706Å²/ps及约0.29764S/cm缺对应原件，属于历史探索值，不据此排名或室温外推。[I01]

外部一手研究Shaw等2025年F⁻键价能筛选表2列Na₃Sb₅F₁₈（ICSD60000），1D/2D/3D指标0.177/0.364/0.364，单位为任意单位，不是eV，对象F⁻不是Na⁺。未建立ICSD与本mp逐位对应，筛选也不是实测电导，只提示不能忽视阴离子载流可能。[E1表2及方法]

保留三种竞争解释：稳定但高度动态高温相；启动导致的持续松弛；失序/类液态或其他相态中的多物种运动。第一种尚未胜出。即使固相成立，瓶颈也可能是局部陷阱、自由能障碍、稳定可占位置的连接或相关运动，不能简化成缺空位。

## 四、改造候选的理由和收益代价

### 4.1 先确定目标

合理目标是假设性稳定可保持的Sb/F结构，同时保留低温Na交换及高Na迁移数；增强F失序未必有利于钠电解质。未定相态前，不给最佳浓度或确定不等价晶位。只保留Ca@Na、Sn@Sb两条可区分假设，不凑新元素。□是名义计量空位，不是已测容量。形式账3(+1)+5vSb−18=0得Sb平均+3，不是实测价态分布。缺陷吸引是模型推断，不是已算结合能。

### 4.2 Ca²⁺替Na：直接改占据，却会占住一个Na位置

选择Na位是为直接改变移动区域和占据，Ca提供明确二价补偿算例。没有Ca与Mg/Sr等本材占位、相容性、成相或增导比较，因此Ca不是已优选元素，只是待检路线。

若Ca确占Na位、保持F18且只用Na空缺补偿：

`(Na_(3−2x) Ca_x □_x)Sb5F18`。

正电(3−2x)+2x+5×3=18。每Ca移走两个Na，一个位置被Ca占据，一个名义空位。数学0≤x≤1.5非可溶范围。x0.10示例Na2.8Ca0.1□0.1Sb5F18，Na库存−6.67%，不是推荐浓度。

若限制确是满占妨碍交换，可用空位置或有帮助；代价是Ca占节点、堵连接、约束F、俘获附近空位。形式Ca_Na相对+1、V_Na相对−1可能缔合，无本材结合能不能断言强弱。CaF₂/其他第二相、非目标占位、电子或阴离子补偿均可使公式失效。

定体积、有效电荷及相关因子不变时，σNa∝nNaDNa,eff，仅抵消库存损失需D新/D旧>3/(3−2x)，x0.10为1.0714。实际需考虑体积、活动比例和集体相关，示踪D小增不等于电导提高。

Ca不减少每式5Sb，不能消除富Sb职业健康/废物负担。前驱体、含水/含氧杂质、致密化和工艺成本待核，需真实试剂SDS和成相窗口。最小对照：同热历史未掺杂与少量Ca，定量Na/Ca/F组成、相分析、Ca占位/局部结构，再分开Na、F、电子响应。未来近/远Ca–空位构型和连续交换计算须另行授权，当前未执行。

否定条件：Ca主要第二相/不在Na位、其他补偿、空位长期束缚、关键节点堵塞，或控制致密度界面后Na分电导不升反降。总电导增加若来自F，不算Na空位路线成功。

### 4.3 Sn⁴⁺替Sb³⁺：有相关化学依据，却改动宿主环境

选Sb位为避免直接占Na位置，调控Sb/F重排。E2证明Sn(IV)、Sb(III)可在同一氟化物共存、F桥连接，Sn为六配位，比单凭价差多一层依据；但该晶体Sn/Sb不同位置和几何，共存不等于本相任意替位。没有与Ti/Zr等四价元素比较，不称Sn最优或指定本相Sb晶位。

仅Na空缺补偿且Sn确+4：

`(Na_(3−x) □_x)(Sb_(5−x) Sn_x)F18`。

正电(3−x)+3(5−x)+4x=18。每Sn少一Na；x0.10为Na2.9□0.1Sb4.9Sn0.1F18，库存−3.33%。同名义空位比Ca少损失一Na且不直接占Na区。简化抵消门槛D新/D旧>3/(3−x)，x0.10为1.0345，是计量优势非增导证据。

可检验收益是假设Sn–F局部结构抑制不可控宿主重排并保留Na通过。竞争结果是约束更强使Na难通过；Sb短层常3–5配位，Sn局部几何不适配可重构/分相；Sn_Sb相对+1和V_Na相对−1也可能俘获。SnF₄/复盐第二相、电子补偿、F非计量待查。

若实际Sn+2，价差−1，不能沿上述Na空位公式。只加Na补偿的形式式为Na_(3+x)(Sb_(5−x)Sn_x)F18，但未证可放额外Na的位点；也可能F空缺或电子补偿。写Sn⁴⁺配平不能当价态实测。

少量替Sb仅小幅减Sb，不使材料无害；价态控制、前驱体纯度、含水/含氧杂质、烧结成相增加工艺变量。无实时价格/收率，成本优劣待查；不得套用有机锡毒性。[E3及计量]

最小验证：Sn价态、目标占位、同相保持、Na亏损是否约x及第二相；再比Na/F分输运和近远缺陷。若Sn主要+2、分相、空位俘获，或宿主稳了而目标温度Na分电导降低，即否定原Sn(IV)–Na空位增导解释。F或电子导致总电导上升也不算成功。

两路线均以同热历史母相作对照。顺序是母相/载流核验、再小规模可行性比较、最后浓度优化，而不是Ca/Sn性能排名。

## 五、用途优先级

### 5.1 包覆层：条件支线，未获资格

室温附近10⁻⁶S/cm为用户目标，不是测量。薄层跨越短；按膜体面积比电阻t/σ，10nm和1e−6S/cm为1Ω·cm²，100nm为10Ω·cm²，未计界面且不证明本相达到σ。

须分别验证Na分电导/迁移数、电子绝缘、具体电极化学反应、电位稳定、膜连续性与厚度。NaF可能为转化产物不等于整层优良Na导体；同时生成Sb等相还可能破坏电子阻隔。F易动不是钠包覆自动优点。附着、开裂、形变和堆叠压力是机械条件，不可用耐高电压替代。

可在稳定可制备相、界面相容后做薄层小样；现在不能宣布高电压正极包覆或Na金属保护层适用。稳定性/漏电失败、目标温度Na膜体与界面阻抗不达要求即否定。

### 5.2 主体固态电解质：当前最低优先

室温约10⁻⁴S/cm是目标。还需Na选择性、致密连续通路、晶界/孔隙可控、低电子泄漏、两极界面相容、压力下保持。1200K多物种强运动不证明降温同相导电，甚至不证明该状态固态。

缺低温阻抗、电子输运、相态、分解电压、真实力/应力、力学和界面数据。单粒子Nernst–Einstein换算缺不同离子电流相关，不能把总电导当Na电导。仅在稳定低温固相、高Na选择性成立后再工程投入；若导电依赖高温失序/非固态或主要非Na载流，否定当前钠主体定位。

### 5.3 储Na电极：有条件的转化/合金线索，不是已证高容量插层

原相3Na全可逆脱出的库存算术上限约78.85mAh/g；不证明可脱3Na、氧化还原中心、电压或结构保持。

形式Sb平均+3时：

`Na3Sb5F18 + 15 Na+ + 15 e− → 18 NaF + 5 Sb`

再假设：`5 Sb + 15 Na+ + 15 e− → 5 Na3Sb`。

以初始质量计，15e约394.24mAh/g，30e合计788.48mAh/g。CIAAW简表Na22.990、Sb121.76、F18.998得M1019.734g/mol；Faraday常数96485.33212C/mol；Q=nF/(3.6M)。这是条件配平/算术，与旧值一致不等于实验。[E4、E6]

E5金属Sb研究支持Na–Sb合金相和非晶中间体，不证明本氟化物可逆转化或本mp电压。完全转化不保持原氟化物骨架，不能同时宣传原结构保持。18NaF+5Sb产物中NaF质量约55.39%，需实际确认分布、离子/电子通路和再氟化可逆性。

首圈Na消耗、不可逆损失、体积/界面重构、电子接触、极化/滞后、Sb聚集与长期可逆性均为待验证风险，非本样品实测。最小证据是电压/电荷量与Sb价态、NaF/Na₃Sb演变对应，充电返回且循环重复。只有容量不能排除电解液或分解副反应；若主要不可逆，否定高可逆容量结论。

**排序：先相态/热历史与载流物种鉴别。** 储Na反应识别和包覆界面筛查可留为条件支线；金属Sb化学线索比主体电解质直接，但非本相性能；包覆须先过绝缘/界面筛查。主体电解质放后，不凭高温MSD或条件容量发合格标签。

本式Sb质量约59.70%，小掺杂不消除富Sb负担。NIOSH对Sb及化合物有职业接触控制要求，支持粉体和废物风险管理，不能据此为未测Na₃Sb₅F₁₈指定毒性等级。[E3–E4] 实时价格、供应风险、收率、水解/吸湿、前驱体SDS待查，不编造成本或制备窗口。

## 六、下一步验证及否定条件

第一，确认可保持且不依赖启动方式的固态结构。另行授权计划中用温和升温、不同初速度、独立热历史及目标温区结构证据对照。若强Na运动只在严重过冲后、或随失序/非固态出现，否定原晶体本征固态快Na解释。温度平均回1200K不够；本次未执行新运行。

第二，分开Na、F、电子。阻抗需配合电子泄漏/离子选择性和Na/F动力学或集体输运分析，不能由总阻抗或各物种MSD直接报Na迁移数。若总响应主要F/电子，否定Na主体用途，不继续包装Na空位优化。

第三，把区域重用升级到可信交换。需完整坐标/晶胞、随宿主更新的位点模型，核A→B驻留、原占据者离开、B→C继续和跨周期重复，采用独立运行/合适分块处理相关性，验证灰边是否承载轨迹。若轨迹不沿边或只有限回摆，否定几何图=通道。位点/相态成立后才为特定路径另行设计能垒或自由能验证。

第四，Ca/Sn先做可否定小比较而非浓度优化。定价态、占位、Na/F计量、第二相、近远缺陷，控制热历史、致密度、界面。只有Na分电导收益超过库存损失且不牺牲相态/界面/绝缘，才值得继续。空位俘获或缺稳定可占位置否定补偿设计有效性。

最后按用途分别过关：包覆测膜体/界面面积比电阻与电子阻隔、电位及压力稳定；主体测稳定固相目标温度Na分电导约10⁻⁴S/cm与可加工性；电极测真实反应、电压、可逆电荷和产物演变，互不能替代。

### 本次新计算与边界

实际完成21附件SHA-256、9CSV全读；1500×24网格/时间；36000行六F唯一身份和35976相邻变化Jaccard；strict/full/common标量端点、r90、max、起点球返回、贡献；保存步路程和首原点MSD；12拟合；747事件CN/身份对帧；1494+582相位汇总；20107strict明细/连续性；459联合集合及291strict/456full控制禁区；返回/null/删失/复用/重叠/时间偏差；后段端点向量；补偿、库存门槛、容量算术。均为上传派生数据新核对，不是物理轨迹独立重算。

端点匹配误差约8.9×10⁻¹⁶Å，host首原点MSD约3.6×10⁻¹⁵Å²，相位/环境对应无不匹配。这些可能共享同一处理链，内部一致不等于原始轨迹正确或机制独立证实。无新坐标、模拟、几何网络、图片；本文24Na及统计表是实际生成的新表。科学状态保持UNVERIFIED。

## 外部一手来源

E1. Shaw R., Pérez G. E., Playford H., Hull S. A bond valence sum method to identify potential new fluoride ion conductors. J. Appl. Cryst.58 (2025)2134–2143. DOI10.1107/S1600576725009574。已读出版社HTML方法与表2；F⁻筛选不是Na电导实测。https://journals.iucr.org/j/issues/2025/06/00/pag5002/

E2. Gerasimenko A.V., Merkulov E.B., Usol'tseva T.I. Tetrapotassium diantimony(III) tin(IV) tetradecafluoride. Acta Cryst.E64 (2008)i32. DOI10.1107/S1600536808012865。已读HTML摘要、结构评论、键长；仅相关化合物类比。https://journals.iucr.org/e/issues/2008/06/00/fi2062/

E3. CDC/NIOSH Pocket Guide, Antimony。官方职业暴露来源，不替代本化合物毒理/SDS。https://www.cdc.gov/niosh/npg/npgd0036.html

E4. CIAAW Abridged Standard Atomic Weights2024。已核Na/F/Sb质量表。https://ciaaw.org/abridged-atomic-weights.htm

E5. Allan P.K. et al. Tracking Sodium-Antimonide Phase Transformations in Sodium-Ion Anodes: Insights from Operando Pair Distribution Function Analysis and Solid-State NMR Spectroscopy. JACS138 (2016)2352–2365. DOI10.1021/jacs.5b13273。ACS直接正文受限，已核作者机构库/PubMed摘要，不声称读完全文。https://www.repository.cam.ac.uk/handle/1810/253617

E6. NIST2022 CODATA complete listing，已核Faraday constant=96485.33212…C/mol。https://physics.nist.gov/cuu/Constants/Table/allascii.txt

检索日期2026-11-15。未核实的价格、溶解度、母相熔点、低温电导、能垒、制备条件不填为事实。网页分析不自动升级科学接受或发表授权。
