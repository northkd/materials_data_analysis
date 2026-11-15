# Na₂VNiF₇ / mp-1191842：Na运动、局部环境、改造与用途的附件复核

材料组：Na2VNiF7；唯一成员：mp-1191842；run：aimd_1200K。科学独立接受状态：**UNVERIFIED**；本次后处理不构成独立验收或发表授权。实际分析时间及归档状态见 RESULT_META.json。本文中的Na编号、金属/F原子ID均从0开始。

## 先确认本次实际输入

本次实际读取20个上传附件：3份Markdown、5份JSON、10份CSV、2张PNG。没有压缩表，也没有打不开的附件。CSV均完整解析；JSON均读取完整对象，而非只依赖网页截断。下列I01–I20是本报告的来源标识，完整列名/主要字段见附录A，逐文件覆盖另见 INPUT_COVERAGE.csv。没有访问原报告中的本机路径，也没有把其跨材料链接、清单或引用当作本次输入。

|来源|实际附件|本次读取量|
|---|---|---|
|I01|`core__REPORT.md`|225文本行|
|I02|`core__data__strict_events__results__SUMMARY.json`|完整JSON|
|I03|`core__data__strict_events__results__event_control_phases.csv`|1554数据行|
|I04|`core__data__strict_events__results__events.json`|259个事件对象|
|I05|`core__data__strict_events__results__first_origin_msd.csv`|1000数据行|
|I06|`core__data__strict_events__results__per_na_motion.csv`|32数据行|
|I07|`core__data__vectors_geometry__CLAIM_LEDGER.json`|11条主张，完整JSON|
|I08|`core__data__vectors_geometry__results__CONTROL_UNION_AUDIT.json`|259套控制，完整JSON|
|I09|`core__data__vectors_geometry__results__SUMMARY.json`|完整JSON|
|I10|`core__data__vectors_geometry__results__event_control_vector_geometry.csv`|518数据行|
|I11|`core__data__vectors_geometry__results__fit_diagnostics.csv`|15数据行|
|I12|`core__data__vectors_geometry__results__per_na_vector_motion.csv`|160数据行|
|I13|`core__figures__full_windows__figures__01_dynamics_MSD_temperature.png`|完整PNG|
|I14|`core__figures__full_windows__figures__04_true_geometry_sequence.png`|完整PNG|
|I15|`core__methods__full_windows__METHODS.md`|26文本行|
|I16|`core__methods__strict_events__METHODS.md`|29文本行|
|I17|`details__data__full_windows__results__event_control_environment.csv`|3828数据行|
|I18|`details__data__strict_events__results__per_na_environment_motion.csv`|32000数据行|
|I19|`details__data__vectors_geometry__results__event_control_sameframe_geometry.csv`|19047数据行|
|I20|`details__data__vectors_geometry__results__per_na_vectors_20fs.csv`|32000数据行|

**身份与窗口核对。** I02明确写入formula、mp_id和run；I09的material与之相同。I18/I20各有32,000条记录，实际覆盖32个Na×1000帧，frame=0…999，absolute_ps=0.02+0.02×frame，严格绝对窗为0.02–20.00 ps，实际跨度19.98 ps，保存间隔20 fs。I20与I18的CN、F6身份和最近V/Ni身份逐行吻合；这比按上传顺序认同名文件可靠。176原子以及Na32/V16/Ni16/F112来自摘要/报告与化学计量，近邻ID实际吻合V32…47、Ni48…63、F64…175。没有O，不能套用O配位或PO₄等多原子阴离子机制。未上传POSCAR、XDATCAR、INCAR、OSZICAR、CIF和完整全宿主坐标，因此没有重新核验原始元素排列、电子结构参数或积分步长。20 fs是保存间隔，不能冒充离子积分步长。

**温度。** run和方法标注目标1200 K；I13温度面板显示大部分时间在该量级波动，启动有接近2000 K的尖峰。原报告称最大1976 K发生在0.062 ps，但温度逐步表未上传，精确峰值和发生时间本次仅属报告引用，不是重算。不同Na都来自同一run，不是独立温度实验。

**两个补充分支各自有效。** strict_events是历史1001帧检测的有效1000帧前缀及删失修正；其路径、多原点MSD和新控制几何中的null保留原意。vectors_geometry是相同严格窗的向量/固定F6几何补充，复用259个事件、259个已选对照，不是宣布旧前缀作废，也不是对全程完整重算。I20现在足以重算host_equal与raw两种参考的严格窗MSD；其他三个参考的完整时间流未上传，只能检查I12与I11保存汇总，不能称本次五参考全重算。

**其他窗口的实际覆盖。** 历史common0_20是绝对0.02–20.02 ps、1001帧；full是绝对0.02–30.00 ps、1500帧。I17确实含common0_20的1554行和full的2274行事件/控制环境相位，合计3828行，但它不是完整坐标流。历史1001帧末端、full逐Na端点和后段MSD的精确量，仅在摘要/原报告中部分存在；本次不从相位表或图片补造缺失坐标。20 ps后的Na3只能作为全程报告/图像和部分相位证据讨论，不倒填为严格20 ps内的远移。

**估计器与标尺。** 主参考host_equal扣除全部非Na的等权平移；raw为保存的展开坐标；host_mass、Ni_mean、host_rigid分别是宿主质量平移、Ni均值和宿主刚性对齐的保存诊断。首原点MSD只以首保存帧为起点；多原点MSD对给定lag的所有可用起点平均，两者不能互换。固定F6参考绑定各事件/对照起点的六个F身份和周期像，扣除这批F的平移；它不是每帧重新选六个最近F，也不是自动去掉旋转/形变。

本文“已支持”只指在本次可读派生输入内可以定位/重算；“部分支持”指仅有汇总、缺关键原始环节或仅能支持关联；“不足”指当前无决定性数据；“反例否定”用于否定一个过强的普遍命题。它们都不等同于科学accepted。主张编号及逐条定位见 CLAIM_EVIDENCE.csv。

## 一、核心判断

**判断一：Na确实有若干较大的净移动，但总体不是32个Na均匀、稳定地向外扩散。〔已支持；M01–M05〕** 严格窗末端平均距离1.7283 Å，均方根距离2.3531 Å，首原点MSD=5.536915 Å²；10/32个Na末端超过2 Å。Na9最远，达到6.6974 Å，贡献末端MSD的25.32%；Na9、Na17、Na27、Na20合计55.96%。这说明末端统计明显偏向少数Na，但并非只有一个Na在动。来源为I06的endpoint_A/endpoint_MSD_share及I20的host_relative_cart_A，实际重算结果见 NA_MOTION_RECHECK.csv。

**判断二：累计“走了两百多埃”主要说明热运动和离返多，不是两百多埃的净输运。〔已支持；M02；反例否定“长路程等于长输运”〕** 32个Na的20 fs保存折线路程平均206.7594 Å，范围194.3505–215.9580 Å，远大于末端距离；Na21路程最长，但末端仅0.3798 Å。Na5和Na16也有明显外出后回归，不能简单叫“从来没离开过原位”。

**判断三：Na的活动发生在非刚性的Ni/F环境中；“V-F相对保留”比“完整骨架稳定”更符合证据。〔部分支持；H01〕** I02在20.00 ps给出V、Ni、F的宿主参考RMS分别0.5785、3.1569、2.8440 Å；宿主等权平移仅0.06337 Å。后者可由I20的raw−host_equal坐标差直接复核，前三项没有完整全宿主流可重算。I18逐Na附近的V/Ni短壳与I13图像提供同方向证据，但不能据此断言发生熔化、确定相变或室温失稳。

**判断四：现阶段最值得检验的限制是“离开后能否在结构可保持的条件下继续向前交换”，不是先假定缺Na空位。〔部分支持；H03〕** Na9在4.18–4.68 ps净移5.0320 Å，但7.58 ps又进入初始0.5 Å球；Na5先外出、再反向，15.86 ps回到初始球。能启动一次较大移动和形成持续净输运是两个问题。能量障碍、终点陷阱、下一段连接以及可参与Na数量都仍需区分。

**判断五：用途尚未成立。〔不足；U01–U04〕** 这是一条1200 K短轨迹的机制线索，不是室温离子电导、能垒或电池资格。先做结构/价态/电子输运的低成本分流，再做储Na可逆性或薄层界面验证；主体固态电解质投入暂缓。正式D和电导率保持null。

## 二、Na运动与具体环境怎样对应

### 2.1 逐Na，而不是只看平均曲线

下表全部来自严格0.02–20.00 ps、host_equal参考的I20重算，并与I06核对。r90是相对首帧距离的90%分位；“最大”不是两两位置的最大直径。离开/返回采用大于1 Å后小于0.5 Å的滞回规则，统计的是初始参考球访问，不是晶格跳跃。D/R/C依次为离开数/窗内返回数/窗末右删失数。最后一列是在16.00–20.00 ps重新比较两个端点的净向量模，不是两个径向距离相减；它是本次另行定义的尾段诊断，不是原来未生成的Na1/Na3 18.02–20.00 ps可选聚合。

|Na|末端 Å|r90 Å|最大 Å|路程 Å|末端MSD贡献 %|D/R/C|16–20ps净移 Å|
|---:|---:|---:|---:|---:|---:|---|---:|
|0|0.949|1.192|2.313|206.66|0.51|25/24/1|0.597|
|1|0.552|1.191|1.810|207.87|0.17|25/24/1|1.055|
|2|1.346|1.234|1.917|202.00|1.02|29/28/1|1.175|
|3|0.992|1.214|2.057|202.55|0.56|27/26/1|0.369|
|4|0.627|1.215|1.846|202.77|0.22|26/25/1|1.106|
|5|0.388|3.425|4.414|208.54|0.09|14/14/0|0.608|
|6|0.723|1.120|1.848|210.24|0.29|27/26/1|0.687|
|7|3.284|1.443|4.060|194.35|6.09|23/22/1|2.620|
|8|0.679|1.232|2.000|207.69|0.26|24/24/0|1.119|
|9|6.697|5.291|7.172|215.69|25.32|8/7/1|4.420|
|10|0.463|1.107|1.775|197.84|0.12|22/22/0|1.082|
|11|0.558|1.248|2.073|209.04|0.18|27/27/0|1.298|
|12|0.722|1.166|1.718|210.79|0.29|23/22/1|1.341|
|13|1.599|1.350|2.891|207.08|1.44|24/23/1|0.853|
|14|1.260|1.127|1.809|204.81|0.90|25/24/1|1.144|
|15|3.432|4.124|4.641|211.46|6.65|11/10/1|1.875|
|16|0.357|2.064|3.818|205.69|0.07|14/14/0|2.153|
|17|4.555|4.201|6.891|214.49|11.71|8/7/1|2.357|
|18|0.818|1.304|2.596|207.22|0.38|22/22/0|0.424|
|19|3.047|1.474|3.742|211.15|5.24|21/20/1|2.033|
|20|3.779|2.701|4.375|209.92|8.06|19/18/1|3.755|
|21|0.380|1.529|2.373|215.96|0.08|21/21/0|0.960|
|22|0.585|1.068|3.183|198.07|0.19|18/18/0|3.237|
|23|2.740|3.365|4.192|202.59|4.24|8/7/1|0.668|
|24|3.651|3.880|4.528|203.45|7.52|4/3/1|2.337|
|25|0.314|1.433|2.145|205.95|0.06|27/27/0|1.712|
|26|0.367|1.242|2.559|209.27|0.08|25/25/0|0.436|
|27|4.390|4.336|5.077|206.68|10.88|10/9/1|1.210|
|28|1.344|1.103|1.637|208.58|1.02|26/25/1|1.227|
|29|0.954|1.173|2.029|206.99|0.51|24/23/1|2.599|
|30|3.171|3.921|5.215|202.31|5.68|5/4/1|1.428|
|31|0.580|1.534|2.536|208.59|0.19|23/23/0|0.920|

末端超过2 Å的是Na7、9、15、17、19、20、23、24、27、30。Na7与Na19的r90仍只有1.4435、1.4742 Å，说明“最后走远”和“绝大多数时候都走远”不同；其尾段净移分别2.620、2.033 Å。Na20尾段净移3.755 Å，不能把较大运动一概归于启动。Na9、17、27则同时有较大的r90和末端距离。

Na5是重要反例：r90=3.4253 Å、最大4.4136 Å，末端却只有0.3881 Å，14段离开均在窗内返回。Na16最大3.8183 Å、末端0.3569 Å；Na22最大3.1827 Å、末端0.5850 Å，且16–20 ps端点净移3.237 Å，主要体现返回/重定位，不能仅因尾段位移大就叫持续向外输运。Na1全窗最大1.8098 Å、末端0.5522 Å；Na3全窗最大2.0571 Å、末端0.9923 Å，这两者在严格窗没有成为主要远移贡献者。

共有635段离开、614段窗内返回、21段窗末右删失。21不是“21个不可逆迁移”：例如Na1末端0.5522 Å虽已很靠近起点，仍没满足严格小于0.5 Å的返回判据。返回与否受球半径和窗口影响，不能将其直接转换为成功率或寿命。初始参考位置还会受到宿主局部重排影响。

### 2.2 多原点MSD和参考敏感性

本次实际采用I20保存坐标计算：

`MSD(lag=k)=mean_{n,t=0…999-k} |q_n(t+k)-q_n(t)|²`，k=1…999，lag=0.02k ps；首原点为`mean_n |q_n(t)-q_n(0)|²`。路径为`sum_{t=1…999}|q_n(t)-q_n(t-1)|`。所有量都是保存点定义，20 fs内部运动没有解析。

host_equal首原点曲线与I05最大差8.9×10⁻¹⁶ Å²；逐Na末端与I06最大差8.9×10⁻¹⁶ Å。host_equal与raw各999个lag实际重算，拟合的六组斜率与I11吻合到浮点精度。结果见 MSD_RECHECK.csv.gz，而不是把缺失的原`msd_strict1000.csv`伪称已上传。

|严格窗lag / ps|host_equal多原点MSD / Å²|可用起点数（每Na）|
|---:|---:|---:|
|0.20|0.850109|990|
|1.00|1.301152|950|
|2.00|1.600928|900|
|5.00|2.245158|750|
|10.00|3.256632|500|
|15.00|4.445464|250|
|19.00|5.815802|50|
|19.98|5.536915|1|

最长lag只剩一个时间起点，其值自然等于全窗首尾MSD，不是第二份独立证据。19 ps到19.98 ps的回落也提醒：长lag端的形状受少量配对影响。拟合0.2–2、2–5、5–10 ps的斜率分别0.361336、0.213632、0.197493 Å²/ps，R²分别0.97255、0.98704、0.99314；斜率随区间明显改变，截距约0.91–1.23 Å²。高R²并未给出渐近扩散、稳态或可靠误差条；不得把斜率除6升级为正式D。

末端前4个Na贡献55.96%，但多原点2、5、10 ps下前4个的贡献分别24.64%、31.23%、40.83%，且成员会变。例如10 ps前4个是Na17、15、9、30；Na5在2和5 ps的贡献也较大，即使全窗末端已回到起点附近。这进一步说明“只靠少数Na”的强弱必须附带估计器与lag，不能从端点占比一概推到整条曲线。

|参考|严格窗平均末端 / Å|首尾MSD / Å²|平均保存路程 / Å|本次证据层级|
|---|---:|---:|---:|---|
|host_equal|1.728268|5.536915|206.759371|完整Na向量实际复算|
|raw|1.729653|5.508574|205.489312|完整Na向量实际复算|
|host_mass|1.745909|5.602093|206.664316|I12的32条保存汇总|
|Ni_mean|1.928107|6.155386|208.787825|I12的32条保存汇总|
|host_rigid|1.795460|5.822579|207.408176|I12的32条保存汇总|

整体平移不是Na表观位移的主要来源：raw与host_equal非常接近。但Ni_mean变化更大，不能据此把Ni子晶格视作静止标准。host_rigid仅是整体最佳刚性变换，不能修复真实非刚性重排。原报告关于30 ps末端宿主旋转3.15°、非刚性残差3.003 Å的数值本次仍只作报告引用，未上传host_motion表，不冒充重新拟合。

### 2.3 远移过程：Na9，事件77与85

**事件77：4.18–4.68 ps，先明显脱离旧局部F群，但后来返回初始区域。〔已支持运动；部分支持环境机制；E03〕** I04事件77为frame208–233。宿主参考净向量为(2.9683, −2.0912, 3.4838) Å，模5.0320 Å；扣除起点固定F6平移后仍有5.1953 Å。因此不是这六个F整群平移把Na带走。固定F群的非刚性残差1.4456 Å，旋转10.54°，又说明它并非保持形状的刚性笼。

同一Na、同一帧的环境链如下。4.18 ps时Na9距初始点0.350 Å，Na短壳计数8，F6为[139,129,105,64,72,121]；最近V33的F短壳为6，与Na共享F139/F105，最近Ni60短壳为3，共享F72/F139。4.42 ps时Na9距初始点2.647 Å、Na短壳降到4，最近V换成V45（短壳6），最近Ni仍为Ni60（短壳4）。4.68 ps时Na9距初始点4.906 Å、短壳恢复6，F6变成[100,125,69,124,132,81]，与起点六个身份无交集；最近V38与Ni53接替，分别短壳6和4。旧固定F6的平均Na–F距离按pre/mid/post相位为2.596→4.208→5.293 Å，而动态最近壳重新补上邻居。这是“离开旧配体群、在另一组F附近重新配位”的具体证据，不是单纯配位数下降。

同Na对照为5.46–5.96 ps、frame272–297，完整前中后为frame262–307；它位于存储联合禁区[198,261]之后、[340,422]之前，闭区间不相交。对照宿主/固定F6净移只有0.666/0.424 Å，但最近Ni短壳均值也从pre2.545增到mid3.769，F6身份相似度也变化。这直接反驳“Ni配位一变化，Na就必定远移”。事件中的Na短壳均值5.462低于对照6.462，是关联线索；不是因果证明。

更重要的是，Na9在7.58 ps再次进入初始0.5 Å球。因此事件77的persistent标签不能解释为不可逆的成功长程跳跃。位置球的返回不证明回到同一个低能晶格位点，因为局部F群已经在换。

**事件85：17.62–18.26 ps，形成严格窗末段较大的保留净偏移。〔已支持；E04〕** 宿主净向量(0.1622, −4.0570, 0.2926) Å，模4.0708 Å；固定F6参考仍为3.9795 Å，非刚性残差0.9566 Å。17.62 ps的F6=[139,149,72,81,153,92]，最近V45短壳6、Ni60短壳3；18.26 ps变为[150,131,151,78,69,172]，两组六个身份无交集，最近V44短壳5、Ni53短壳3。Na距初始位置从3.004到6.132 Å，20.00 ps仍为6.697 Å；直到窗末没有再次进入初始0.5 Å球，结论止于“本窗未见返回”，不能称永久迁移。

前/中/后Na短壳均值为6.545/6.667/6.364，没有像事件77那样在中段明显降低；最近Ni短壳均值反而3.182→3.848→4.727。最近Ni会换身份，不能把这一变化称为“同一Ni的配位随时间增加”。旧固定F6平均距离2.665→3.665→4.990 Å、距离标准差均值0.376→0.853→1.246 Å，支持离开旧邻域并伴随形变，而不是低配位必然开门。

对照为18.68–19.32 ps、frame933–965，完整相位923–975，正好在该Na最后禁区870–922之后；宿主/固定F6净移1.505/1.613 Å，仍有活动，不是“静止对照”。其F群旋转30.70°反而大于事件的8.82°，却没有相当的4 Å净移，故大转角本身不足以解释远移。

这些过程的I19同帧行范围分别为：事件77及其对照5559–5654，事件85及其对照6169–6278（CSV表头为第1行）；I03相位按event_id/role/phase定位，I18按na/frame定位。核心相位均值另存 EVENT_PHASE_RECHECK.csv。

### 2.4 活跃但不形成大末端净移：Na5，以及更局部的Na1

**Na5不是“没有迁移能力”，而是此次明显外出后又回来了。〔已支持；E05〕** 事件47为10.98–11.36 ps，宿主净移3.6346 Å、固定F6净移3.4313 Å；事件48为14.68–15.26 ps，分别3.5202、3.9898 Å。两次宿主净向量夹角余弦−0.9472，方向近乎相反。11.04 ps离开初始1 Å球后，到15.86 ps才进入0.5 Å球，中间最远4.4136 Å；20.00 ps末端0.3881 Å。

事件47起点F6=[79,103,117,94,150,143]，最近V37短壳6、Ni49短壳3；终点F6=[164,161,158,118,79,64]，只保留F79，最近V42短壳6、Ni49短壳3。事件48起点F6=[118,139,161,121,117,79]，最近V33短壳4、Ni57短壳3；终点F6=[135,79,94,103,85,87]，仍只保留F79，最近V37短壳6、Ni49短壳4。动态F身份、共享F和最近金属都改变，两次都不是固定旧笼一起平移；但最终空间上回到初始区域附近。全窗首末F6甚至无共同身份，故“回到初始球”不能等同于“原晶体位点与原配体完整恢复”。

事件47的同Na对照11.78–12.16 ps，完整相位frame578–617，避开禁区538–577与723–772；宿主净移1.1046 Å，F6相似度mid0.370与事件mid0.325并非天壤之别。事件48的对照完整相位773–822，避开723–772及823–878。这些对照支持“环境很活跃也可以主要局部运动/返回”，不支持把所有F换位都列为推动长期Na迁移的门控事件。I19事件47/48及对照分别行3427–3510、3511–3614。

**Na1事件4是局部参考的重要反例。〔反例否定“persistent即成功跳跃”；E06〕** 0.26–0.64 ps，宿主首尾净移0.5317 Å，扣除固定F6平移后仅0.0440 Å；起点与终点六个F身份相同，只是排序改变。其标签仍是persistent，因为标签检查的是合并事件之后定义中的采样状态，并不要求合并首尾向量一定大。固定F6非刚性残差0.5717 Å，因此它也不是完全刚性的笼，只是Na相对这一群F的首尾偏移很小。同Na对照0.3355 Å宿主净移、0.4769 Å固定F6净移，配体旋转15.39°、非刚性残差0.5749 Å，与事件的14.36°、0.5717 Å接近。这个片段不能称为稳定低能位点间的正式跃迁。来源I04事件4、I10同event_id两行、I19行294–377。

### 2.5 259个候选、相位与联合控制，哪些确实核到了

I04实际有259个事件，编号0…258；134 persistent、123 transient、2 right_censored。最大事件末帧999，两个随访不足者是Na3事件36（末帧996）和Na17事件158（末帧999）。完整前后相位252个；缺相位的event_id为36、86、123、130、158、201、230，分别是2个末端post不足和5个启动pre不足。I03的相应数值/帧数空项保留，不用短相位硬填成完整均值。

本次可直接核验259套保存向量及518条事件/对照净向量和保存路程与I20完全吻合。还核验I03中1547个完整相位的8个环境均值，合计12,376个数值，全部与I18逐Na逐帧聚合相同；19,047条I19的固定F坐标、六个距离、15个夹角及CN/金属身份亦核对，距离和键向量误差为0，夹角最大浮点差约1.9×10⁻¹²度。检查的是已保存派生量的内部一致性，不是重做AIMD或证明物理模型正确。

I08的259个控制完整前中后区间均在0…999内，实际检查没有任何区间与其列出的同Na联合闭禁区相交；所有当前strict事件±10帧也被这些联合区间覆盖。但是其他历史窗口的完整事件源表、PREFIX_CERTIFICATE、原检测源码/哈希清单未上传，因此“联合禁区确实包含历史全部1209条来源”的追溯，只能沿用已保存审计，不能声称本次从所有历史源事件独立重建。1001→1000前缀的原始证书同样没有独立重新签发；本次支持的是有效保存集合的边界与向量一致，不重新检测候选。

259个控制中，按(na,start,end)去重仅230段，按(na,start)仅159种起点；还有相互重叠。19,047行同帧几何按(event_id,role,frame)去重为18,018，按(na,frame)去重为13,729，既有闭相位边界重复，也有控制/事件复用。这些都不能作为独立重复。若只对252个完整配对做描述，事件mid的Na短壳均值比对照平均低0.2934、F6_J200低0.08278；先在每个Na内平均再等权平均32个Na，分别为−0.2861、−0.08070，方向不变。但最近Ni短壳差从事件加权的+0.0227变为等Na的−0.0126，既小又改变符号，不支持“Ni统一降配位触发Na迁移”。这里不计算独立样本p值或因果效应。

F6_J200实为当前F6集合与max(frame−10,0)集合的Jaccard，I18全32,000行可复核。启动前10帧没有完整200 fs过去史；相位均值还包含过去窗口，故不能把mid相似度降低精确解释成“运动后才换配体”。pre/mid/post闭窗也共用边界点，先后需逐帧判断。

43/259个合并事件首尾净移小于1.5 Å，135/259的合并直度小于0.7。这不自动说明算法错误：阈值施加于200 fs基本候选，随后合并邻近候选，合并后的路径可折返。它直接否定把259解释为259个满足同样首尾阈值的真实位点跳跃。事件规则次数与位点输运次数必须分开。

固定200 fs驻留中心的独立明细未上传。I02保存宿主参考252套中心、234套进入前中心1 Å球、18套删失、7套缺中心；固定F6对应235/17/7，并分别含51、79套事件末已在球内。这里只列为汇总支持，不能称本次逐事件返回锚独立复核。环境相位前后闭窗为11点/200 fs跨度；驻留中心半开窗每侧10点，采样中心首尾跨度180 fs，两种定义不混。原未生成的INTERPRETATION.json及Na1/Na3指定片段可选聚合继续缺失，没有恢复或改写为既有成果。

## 三、机制解释、竞争解释与反例

### 3.1 目前支持的过程链

本包支持的最小链条是：**Na在旧F邻域内热运动/离返 → 某些片段相对原固定F群明显移动 → 动态近邻和共享F改变、最近V/Ni对象接替 → 有的片段返回，有的在观察末端仍偏离较远。** Na9事件77、85和Na5事件47、48提供了同一Na、相同时段的连续证据。V近邻通常保持接近六个F，而最近Ni短壳更可变，这使Ni/F区域成为优先检查的位置，但还不是已证实的控制因子。

关键区别是：动态近邻负责描述“此刻谁围着Na”，固定F6负责检验“是否仍跟随原来的F群”。大位移时动态CN可恢复到6–7，而旧固定F距离增大到4–5 Å，这更像从旧邻域离开并获得新邻域，而不是始终同一个笼变大。无论如何，没有能量数据就不能将距离增大叫越过特定能垒。

### 3.2 哪些解释受到反例限制

“所有Na只在原点振动”被Na9、Na17等数埃净移否定；但“所有活跃Na都形成持续输运”被Na5的反向返回和Na9事件77的后续返回否定。“F身份替换足以导致长程迁移”也被Na5和Na1全窗首末身份变化但小末端净移限制。Na1首末F6只保留1个身份，末端仍只有0.552 Å；不能把换配体单独当作迁移驱动力。

“必须先降低Na配位才走远”不是通用规则：事件77中段CN下降，事件85中段却不降。瞬时CN依赖冻结的距离壳、局部热涨落及最近金属身份更换；尤其Ni短壳约3不等于Ni在任意距离都只有三个F，也不能据此直接判定Ni价态或Ni–F化学键断裂。

“Ni先重排，随后开门”目前不足。事件77前相位已有F身份变化，中段更显著；事件85则原固定配体距离与Na移动共同增大，最近Ni短壳的较大均值出现在post。对照本身也有Ni/F变化，事件85控制旋转甚至更大。能够说伴随或有时先已出现背景变化，不能给出统一因果顺序。共同热浴驱动、Na移动后环境调整、局部结构松弛及按位移筛选带来的选择偏差都是竞争解释。

### 3.3 温度、整体漂移、非刚性和窗口必须分开

启动温度尖峰和初始结构松弛有可能改变后续运动背景，但本次没有温度数值流，不能定量分离贡献。Na9事件85、Na20事件176在约18 ps仍有大移动，所以“全部位移只是最初尖峰的一次瞬态”与现有记录不符；相反，这也不证明前4 ps删去后结构已经重新平衡。热历史造成的重排可延续到后段。

整体宿主平移小且raw/host_equal相近，故整体漂移不能解释主要Na位移。Ni/F大RMS与固定F群显著非刚性表明标尺本身不刚性；这不能通过只做整体平移/旋转消除。固定F6参考可揭示Na1事件4的大部分首尾位移是跟随局部群运动，也可表明Na9事件85不是局部群搬运，但固定F群在长时间后不再是“当前笼”，不应以其全部距离增长衡量稳定束缚强弱。

full图中Na3在20 ps后活跃是真正需要保留的后段线索，而不是严格窗主角。I17在Na3的21.20–21.46 ps事件中段（full event45，表行273）保存Na短壳均值6.286、最近Ni短壳1.714、最近V短壳5.786；24.12–24.34 ps（full event46，行279）仍有相位环境量。但原报告“20–22 ps净移4.40 Å”、全程末端2.60 Å等精确运动数字没有对应全程向量输入可重算；本次不把它们升级。I14黑线是保存轨迹图，虚线为共享F几何边，不是能量路径。

### 3.4 当前最值得检验的限制环节

优先问题是：**在局部F/Ni排列仍能保持或可逆调整的情况下，Na进入新区域后，是否有稳定的下一处可达区域，使其不只是返回？** 此问题比“有没有运动”更接近数据暴露的限制。Na5能完成数埃移动，说明至少某些通路在1200 K可被访问；其返回可能来自起点/终点能量差、下一段连接不利、局部F/Ni重排后路径关闭或简单有限时随机返回，当前不能选定其一。

能量障碍决定某一段是否容易过；稳定位置决定进入后停在哪里；可达连接决定能否接着走；可参与Na数量决定多少载流离子真正参加。这四者不可互相替代。少数Na末端贡献较大不等于其余Na永久不导电；减少Na总数不等于有效载流数或空位迁移率增加。

初始Na球访问、完整周期连接表和空间网格表未上传，只在原报告/账本被引用。原报告所称9个Na访问别人的初始球、Na共享F图秩3或不同排除半径下开放空间改变，均只能列为历史几何线索。我们没有从初始参考球重建完整位点容量或空位率，也没有把共享F网络的图秩叫真实扩散维数。完整母结构、热态位点、可达而未占位置及相应自由能仍缺。

## 四、改造候选：先做能区分机制的对照，不强推“最优掺杂”

目前没有本材料真实价态、外来元素占位/形成能、分相边界或掺杂后动力学。因此下面只保留两个有明确判别目的的候选，不是已优化配方。共同形式前提是Na⁺、F⁻，于是平均V价态+平均Ni价态=5；V³⁺/Ni²⁺只是待验证的一种分配。形式配平与实际替位稳定是两回事。

### 4.1 优先机制对照：Mg²⁺少量替Ni²⁺，不主动造Na缺位

**候选表达：Na₂VNi₁₋ₓMgₓF₇。〔元素/位置理由部分支持；性能收益不足；C01〕** 在V³⁺/Ni²⁺前提下总形式电荷为2+3+2(1−x)+2x=7，不需要移走Na。以x=1/16作稀释计量示例，组成Na₂VNi₀.₉₃₇₅Mg₀.₀₆₂₅F₇，当前16化学式尺度为Na32V16Ni15Mg1F112。此为计量账本，没有生成任何替位坐标，也没有声称这个浓度最优。

为什么先试Ni位置？本包中Ni/F区域比V-F更明显重排，替Ni能检验“抑制/改变这一区域的无序是否改善持续交换”；替V会先扰动相对保留的部分，替Na则直接占用移动物种区域、混入堵塞因素。Mg而不是任意二价元素的理由是：常用六配位Shannon有效半径Mg²⁺0.72 Å与Ni²⁺0.69 Å较接近，明显比Ca²⁺1.00 Å更适合作为小尺寸差对照；Mg²⁺是闭壳层对照，且MgF₂/NiF₂在独立二元氟化物实验中曾形成共同金红石型晶格。这只提供F配位相容性的有限先例，不证明本四元结构可替位，更不证明Mg–F“更强”或本材料更稳定。[W1–W2]

这也是为什么此处不直接选Al³⁺：它会把异价补偿和尺寸变化一起引入，难以分离Ni/F结构效应；Zn²⁺等也不是被证明无效，只是本轮没有本材能量或占位证据支持把候选再扩大。原Ni在热轨迹中的短壳并非始终六配位，所以六配位半径只能粗筛，不能当作真实1200 K局部尺寸或迁移孔径。[W1]

预期收益是减少不可逆Ni/F连接改写，维持可重复进出的Na邻域；也可能反过来冻结有利的局部松弛，使Na更难移动。Na总数保持32，并不保证有效移动Na数保持不变。若Ni参与电极氧化还原，Mg替代还可能稀释可用活性位；本包未测Ni是否参与，因此这项是条件代价。

主要风险是MgF₂分相、Mg占错Na位造成阻塞、局部收缩形成较深Na势阱、等价替位的应变吸引已有缺陷，以及杂质/含氧水解产物改变补偿。等价替位不强制产生带电Na空位，但也不保证没有本征缺陷缔合。成本没有本次可核报价，不能宣称一定更便宜；新增高纯前驱体、气氛、相纯度及废物处理可能超过少量Ni替换的收益。减少一点Ni不是消除Ni/V/F职业暴露风险。[W3–W5]

**最小区分验证与否定条件。** 先确认母相价态，再用低x样品/经验证结构检查Mg实际位于Ni还是Na、是否出现MgF₂；与不掺杂样品在相同热历史下比较Ni/F结构保持、Na长时位置交换和电子电导。若Mg主要分相/占Na位，候选即被否定；若结构更稳定但Na持续交换降低，则“稳定Ni/F即可提高输运”被否定，不以更低结构RMS强称性能改善。

### 4.2 次级判别候选：Ti⁴⁺替V³⁺，有条件地引入Na不足

**候选表达：Na₂₋ₓV₁₋ₓTiₓNiF₇。〔形式计量已支持；元素稳定/输运收益不足；C02〕** 仅在V³⁺/Ni²⁺、Ti⁴⁺且唯一补偿为移走Na时，(2−x)+3(1−x)+4x+2=7。x=1/16对应Na₁.₉₃₇₅V₀.₉₃₇₅Ti₀.₀₆₂₅NiF₇，计量为Na31V15Ti1Ni16F112：V位替6.25%，Na数少1/32=3.125%。这不是测得的本材空位浓度，也没有构造缺位坐标。

为什么Ti及V位置？这是一条专门测试“Na不足是否改善持续交换”的对照，不是因为慢就必须缺空位。Ti⁴⁺六配位有效半径0.605 Å与条件V³⁺0.64 Å较接近；Zr⁴⁺0.72 Å、Hf⁴⁺0.71 Å会带来更大的同配位尺寸变化。Ti⁴⁺替Ni²⁺则每替一个需两份负补偿，削减Na/改变Ni-F的因素更复杂；所以先选V位置来简化电荷账本。但这会扰动本包中相对保留的V-F部分，代价不能忽略。[W1]

可能的收益是为Na进入下一位置提供可用缺口、减少排斥/拥堵；是否真的如此，需要完整位点模型。代价是Na总数与起始可脱嵌Na减少、V活性中心被稀释，且Ti相对于V³⁺多一个正有效电荷，可能与负有效Na空位缔合，使缺口被困在掺杂附近。空间上更开放也可能伴随更深陷阱。只有假定体积和离子相关性不变、参与比例不变，31个Na要抵消32个Na的数目损失，平均迁移能力至少需增加32/31−1≈3.23%；这只是n×迁移能力的条件算术，不是预测电导。

真实补偿可能是Ti/V的电子还原或F过量等，而非预期Na不足；F空位本身的正有效电荷不能单独补偿一个高一价阳离子替位。Ti变成Ti³⁺时上述“一替一减Na”的假定失效，并可能改变电子输运。还需检查Ti富集相、V/Ni氟化物分相、错占位及局部连接收缩。没有本次报价或本材合成先例，成本、前驱体相容性、含水/含氧杂质与规模制备窗口均待查；原体系Ni/V/F暴露风险仍在，不能称低毒路线。[W3–W5]

**最小区分验证与否定条件。** 先用价态/成分/占位测量确认Ti价态和真实Na不足；随后比较同一个替位位置旁近/远Na缺口的偏好，以及Na从缺口邻域继续离开的难易。未来形成能/局部迁移能量计算须在已验证结构上另行开展，本次没有启动。若主要通过变价补偿、Na不足未形成、缺口只困在Ti附近、母相分解，或Na数减少但长时净输运未改善，就否定这一用途方向；不能用更大的热振动或候选事件数作为成功标准。

**暂不增加第三候选。** Na位异价替代容易把载流数和堵塞混在一起；直接F/O混阴离子更改会同时改变价态、连接和化学稳定性，本包又无O。没有必要为凑数提出缺少占位依据的Cl/O/多元素共掺。应先用上面两条分离“Ni/F结构作用”和“Na不足作用”。

## 五、用途优先级与代价

### 5.1 包覆层：可作为有条件的界面筛选对象，不是已合格涂层

用户给定室温附近约10⁻⁶ S/cm作为包覆需求，本文不把它写成本材实测。薄层可以减少体相输运长度，但是否改善界面取决于工作电位下不被氧化/还原、电子泄漏低、与电极/电解质接触不持续反应、涂层覆盖与厚度合适。V/Ni价态未确定，不能凭“含F”宣称宽电化学稳定窗或高压正极兼容。高电压稳定和机械/堆叠压力稳定是两种不同问题；本轨迹没有界面反应、应力、压实或断裂数据。

最小投入是先做电子泄漏/实际工作电位稳定性及薄层界面阻抗的筛选；再检查循环后组成与覆盖。若涂层发生持续氧化还原、形成阻挡层，或电子导通促进副反应，即使Na可动也不适合作为绝缘离子通行层。Ni/V使用和相纯度成本、含F制备/废物处理不能省略。[W3–W5] 优先级：**第二层级、小规模条件验证**。

### 5.2 主体固态电解质：当前不宜重投入

用户给定室温附近约10⁻⁴ S/cm作为主体需求，不是本材测值。当前缺室温/多温离子电导、独立重复、电子输运分离、晶界与致密度、相保持、界面和机械数据；1200 K下Ni/F显著移动又使“稳定骨架中的Na选择性快传导”这一前提不能默认成立。Na多原点MSD向上和几何周期连通都不足以补上这些缺项。

若较低温度下Ni/F仍显著不可逆重排或出现电子泄漏，应尽早停止主体电解质方向。相反，即便室温结构稳定，Na也可能被冻结；必须直接测迁移或导电，不能从高温轨迹外推。优先级：**第三层级，暂缓主体器件开发**。

### 5.3 储Na电极：可先做低成本可逆性筛查，但不是正极资格认定

材料含Na与待定价态的V/Ni，提供了检查Na脱嵌与氧化还原的对象；本次数埃移动说明某些高温环境中Na能够重定位，但没有证明室温Na可以从颗粒/电极可逆进出。需确认实际V/Ni价态、活性氧化还原对、可逆脱嵌量、电压平台、容量、电子输运、结构保持及循环后的反应产物。质量计量可写`Q=nF/(3.6M)`，但n尚未知，因此这里不报理论容量作为性能承诺，也不决定其正极/负极归属。

电极需要足够电子通路，而包覆/主体电解质通常要抑制电子泄漏；因此电子输运测量是用途分流的关键，不是可省略的最后一步。若可逆氧化还原存在而主体电子绝缘不足，电极比电解质更值得继续；若反应只是不可逆转化、F流失或结构崩解，则不应把首圈容量当作可逆脱嵌。Mg替Ni可能损失金属活性位，Ti+Na不足路线还减少Na库存，这些代价在电极目标下更需要核算。

推荐投入顺序为：**先核结构/价态与电子输运 → 储Na可逆性的小规模筛查 → 具备绝缘与界面稳定线索时再做包覆 → 主体电解质最后考虑。** 这是信息收益/风险的条件排序，不是已经证明电极性能最好；若初筛无可逆氧化还原，电极优先级立即下调。

## 六、下一步验证及会否定当前解释的结果

**第一步，补齐决定解释边界的原始证据，而不是先加掺杂。** 需要本run实际结构/物种索引、温度逐步记录、势能/应力或体积控制、计算方法及磁性/价态设置、完整宿主坐标，以及历史1001帧检测源与前缀/联合禁区证书。若原始标签、PBC展开或时间映射不一致，应暂停机制结论；本次浮点一致性检查只能证明派生文件彼此一致。

**第二步，检验结构与Na可重复交换能否分离。** 在更接近目标温度、不同热历史和独立重复下，同时看Na的位置访问/返回与Ni/F配体保持；需要能够跟随结构的位点/区域模型，并验证不是把变形的初始球当固定位点。若Na大位移只出现在不可逆Ni/F重排或局部失序期间，就否定“稳定晶体骨架内的Na快离子通道”。若保留结构时仍有连续向前交换，则支持进一步分离能垒与占位作用。这里只提出验证，不启动新AIMD。

**第三步，区分因果时序而不把合并候选当跳跃。** 从Na9事件77/85、Na5事件47/48以及Na1事件4这样的已定位片段出发，比较固定金属/固定F身份的逐帧变化，在同Na无大净移片段中检查同样变化是否普遍存在；重新设计前史匹配的对照、去重并按Na/run处理相关性。若F/Ni变化经常在Na之后，或在控制中同样强，就否定“Ni先开门”的普遍说法。现有数据已经说明这一因果命题不能直接成立。

**第四步，改造先过占位/补偿关，再过迁移关。** Mg路线先确认Mg进Ni位且不分相、Na库存不被隐性改变；Ti路线先确认Ti⁴⁺与预期Na不足，而不是变价补偿。未来只在验证结构上比较替位位置、近远缺口结合与具体路径的能量，不能从共享F线生成并宣称已验证NEB路径。若缺陷被牢固束缚、通路被堵、分相或可移动Na数量下降多于迁移能力增加，否定该路线。DFT/NEB等均属未来另行开展的任务，本次未启动。

**第五步，用途分别设置停止条件。** 包覆先看实际电位下界面反应/电子泄漏和厚度相关阻抗；主体先看室温离子电导及相稳定/晶界/压力响应；电极先看价态和可逆脱嵌、真实电压/容量与结构恢复。目标门槛达不到、电子输运方向不匹配或不可逆反应占主导时，停止对应器件投入。不同温度与时间原点不得当独立重复；单温短轨迹不提供Arrhenius活化能，也不提供室温电导。

## 七、外部证据与本包观察分开

W1：R. D. Shannon, “Revised effective ionic radii and systematic studies of interatomic distances in halides and chalcogenides”, Acta Crystallographica A32, 751–767 (1976), DOI **10.1107/S0567739476001551**。本次实际查看论文PDF表1印刷页752–753的截图：六配位有效离子半径Mg²⁺0.72、Ni²⁺0.69、Ca²⁺1.00、V³⁺0.64、Ti⁴⁺0.605、Zr⁴⁺0.72、Hf⁴⁺0.71 Å。只作同价/同配位粗筛；论文自身强调畸变与共价性，半径不等于本材实际键长或能垒。稳定入口：https://doi.org/10.1107/S0567739476001551 ；本次所读公开原文副本：https://nilab.physics.ucla.edu/sites/default/files/shannon-1976-radius.pdf 。

W2：M. Wojciechowska, S. Łomnicki, M. Pietrowski, “Study on surface chemistry of porous NiF₂–MgF₂ system”, Journal of Fluorine Chemistry 76, 133–137 (1996), DOI **10.1016/0022-1139(95)03359-9**。实际核对出版方索引摘要和作者上传的一手论文文本，支持在所研究二元体系至少部分形成共同金红石型晶格；出版方正文直开403，未声称读取其全文PDF。它不是Na₂VNiF₇替位实验证据。稳定入口：https://doi.org/10.1016/0022-1139(95)03359-9 。

W3：CDC/NIOSH, Nickel metal and other compounds (as Ni)，https://www.cdc.gov/niosh/npg/npgd0445.html 。该官方资料支持Ni化合物暴露需要职业健康控制；不是本材特异毒性测定，本次不转述法规限值。

W4：CDC/NIOSH, Vanadium dust，https://www.cdc.gov/niosh/npg/npgd0653.html 。页面本身主要描述V₂O₅并列出钒化合物职业暴露范围，本文只用于提醒钒原料/粉尘需安全评估，不把V₂O₅毒理数值直接等同Na₂VNiF₇。

W5：CDC/NIOSH, Hydrogen fluoride，https://www.cdc.gov/niosh/npg/npgd0334.html ；Fluorides，https://www.cdc.gov/niosh/idlh/fluoride.html 。仅在工艺使用/生成HF或处理含F粉尘时作为安全依据；没有观测本材在本次条件下放出HF，不推定水解或具体分解反应。

本次没有找到足以核实本精确Na₂VNiF₇/mp-1191842配方电化学性能或Mg/Ti替位稳定的公开一手研究。因此上述候选和用途保持假说/待验证，不能由相邻氟化物研究补成“已知有效”。没有核实的材料成本、合成窗口和元素优选不作事实陈述。

## 八、本次新增产物、局限与归档

本次仅做上传派生数据的数值后处理：读取/计数/哈希、Na端点/r90/最大探索/20 fs路径/离返/末端贡献、两个实际可读参考的多原点MSD、16–20 ps尾段诊断、已保存事件向量/路径与同帧F6几何一致性检查、已存联合区间的交叉审计，以及小范围相位和个体对照。没有新AIMD、DFT、NEB、模型训练、未经验证的坐标构造或候选重检测。

随四份必需文件另保存 NA_MOTION_RECHECK.csv、MSD_RECHECK.csv.gz、EVENT_PHASE_RECHECK.csv、RECHECK_AUDIT.json；它们都是本次实际计算，并在RESULT_META中登记公式/输入。MSD_RECHECK.csv.gz为完整1998行CSV的gzip无损压缩，解压后包含两个参考各999个lag，不是抽样摘录。没有生成新图，没有把用户上传PNG重新发布为本次新图；INTERPRETATION.json、旧可选Na1/Na3片段净向量聚合、完整位点/占据/周期图、正式D及室温电导仍缺失。

本次结果的仓库相对目标位置：`materials/Na2VNiF7/results_web`。实际是否推送、main/PR状态以RESULT_META.json及最终回执为准；本地文件不等于推送成功。结果目录只包含本材料新结果；不修改或删除任何旧附件、旧报告、其他材料文件。元数据不写入自身提交SHA，实际提交SHA仅在回执提供。

## 附录A：实际读取字段与范围

CSV行号统一从表头第1行计算；数据键优先使用(mp/run/window/reference, na, frame, event_id, role, phase)，不依赖上传先后。所有输入SHA-256见RESULT_META.json；INPUT_COVERAGE.csv只记录本次真正读取范围。

I01 `core__REPORT.md`：完整读取1–225文本行；只作为待核对解释及历史来源。

I02 `core__data__strict_events__results__SUMMARY.json`完整对象主要键：`formula, mp_id, run, state, scientific_acceptance, publication_authorized, raw_reads, coordinate_redetection, window, endpoint_mean_A, endpoint_max_A, n_endpoint_gt2_A, r90_mean_A, max_exploration_mean_A, first_origin_endpoint_MSD_A2, top4_endpoint_MSD_share, initial_region_departures, initial_region_observed_returns, initial_region_right_censored, event_count, outcomes, events_full_phases, controls, controls_changed_from_legacy, dwell200, host_at_absolute20ps, selected_sameNa_examples, legacy_common1001, reused_full1500, multi_origin_MSD_A2, vector_path_A, formal_D, unresolved, execution_is_not_full_strict_goal_acceptance`。

I03 `core__data__strict_events__results__event_control_phases.csv`，1554数据行，全部列名：`event_id, na, role, phase, complete, first_frame, last_frame, first_absolute_ps, last_absolute_ps, n_frames, F6_ids_at_first, F6_ids_at_last, F6_J200_mean, Na_CN_mean, nearest_V_F_CN_mean, nearest_Ni_F_CN_mean, nearest_V_distance_A_mean, nearest_Ni_distance_A_mean, shared_F_with_nearest_V_mean, shared_F_with_nearest_Ni_mean`。

I04 `core__data__strict_events__results__events.json`，259个事件，事件字段：`window, frame_offset, na, t_start, t_end, disp, net_disp, path, straightness, post_window_fully_observed, outcome, event_id, control_start, event_phase_complete, same_na_all_events_banned, n_same_na_banned, control_phase_complete, global_atom, start_relative_ps, end_relative_ps, n_frames, start_absolute_ps, end_absolute_ps, historical_outcome, outcome_source, historical_control_start, control_geometry_net_A, all_window_sameNa_union_bans, candidate_source`。

I05 `core__data__strict_events__results__first_origin_msd.csv`，1000数据行，全部列名：`frame, absolute_ps, elapsed_from_first_ps, first_origin_MSD_A2, n_Na, n_time_origins, multi_origin_MSD_A2, multi_origin_missing_reason`。

I06 `core__data__strict_events__results__per_na_motion.csv`，32数据行，全部列名：`na, global_atom_zero_based, endpoint_A, r90_A, max_A, endpoint_squared_A2, endpoint_MSD_share, path_A, path_missing_reason, n_departures, n_returns, n_right_censored, absolute_first_ps, absolute_last_ps, n_frames, reference, full_site_capacity`。

I07 `core__data__vectors_geometry__CLAIM_LEDGER.json`，完整对象主要键：`schema, scientific_acceptance, publication_authorized, claims`；11条旧主张不自动继承为本次已支持。

I08 `core__data__vectors_geometry__results__CONTROL_UNION_AUDIT.json`，完整对象主要键：`controls, invalid_ids, n_saved_controls, no_control_reselected, source_union_equals_saved, independent_sample_count`。controls的实际字段：`event_id, na, saved_control_start, saved_control_end, full_pre_body_post_range, all_old_full_windows_and_strict_union, issues, valid, reselected`。`independent_sample_count=null`。

I09 `core__data__vectors_geometry__results__SUMMARY.json`，完整对象主要键：`schema, material, n_frames, Na, atoms, absolute_ps_bounds, actual_span_ps, dt_fs, raw_reads_this_stage, candidate_redetection, old_successful_checker_rerun, candidate_count_reused, saved_controls_reused, invalid_controls, complete_event_phases_reused, vector_sample_rows, sameframe_geometry_rows, phase_geometry_rows, first_origin_endpoint_MSD_A2, endpoint_mean_A, saved_step_path_mean_A, saved_step_path_min_A, saved_step_path_max_A, msd_references, MSD_rows, fit_diagnostics, formal_D, formal_conductivity, source_unchanged, fixed200_definition, scientific_acceptance, publication_authorized, B06_new_model`。

I10 `core__data__vectors_geometry__results__event_control_vector_geometry.csv`，518数据行，全部列名：`event_id, na, role, start_frame, end_frame, control_valid, fixed_F6_ids, fixed_F6_images_wrapped_at_anchor, continuous_ligand_offsets_A, host_equal_net_vector_A, fixed_F6_translation_net_vector_A, host_equal_net_A, fixed_F6_translation_net_A, host_equal_saved_step_path_A, fixed_F6_translation_saved_step_path_A, fixed_F6_rotation_deg, fixed_F6_nonrigid_A, missing_reason`。

I11 `core__data__vectors_geometry__results__fit_diagnostics.csv`，15数据行，全部列名：`reference, lag_min_ps, lag_max_ps, n_lags, min_time_origins, slope_A2_per_ps, intercept_A2, r2, slope_div6_A2_per_ps_diagnostic, formal_D, formal_conductivity, correlated_lags_and_origins`。

I12 `core__data__vectors_geometry__results__per_na_vector_motion.csv`，160数据行，全部列名：`na, global_atom_zero_based, reference, net_vector_A, endpoint_A, saved_step_path_A, straightness, r90_A, n_frames, absolute_first_ps, absolute_last_ps, sub20fs_path_resolved`。

I13 `core__figures__full_windows__figures__01_dynamics_MSD_temperature.png`及I14 `core__figures__full_windows__figures__04_true_geometry_sequence.png`：完整目视核对；没有可当作原始CSV读取的数值流，没有沿原图引用寻找未上传坐标。

I15 `core__methods__full_windows__METHODS.md`完整读取1–26行；I16 `core__methods__strict_events__METHODS.md`完整读取1–29行。两份方法用于核对窗口、参考、事件、配位和几何定义。

I17 `details__data__full_windows__results__event_control_environment.csv`，3828数据行，全部列名：`window, event_id, na, role, phase, complete, first_frame, last_frame, n_frames, CN_mean, CN_min, CN_max, knn6_200fs_J_mean, contact_ids_at_first, contact_ids_at_last, V_F_CN_mean, Ni_F_CN_mean, nearest_V_ids, nearest_Ni_ids, V_distance_mean_A, Ni_distance_mean_A, shared_F_V_mean, shared_F_Ni_mean`。

I18 `details__data__strict_events__results__per_na_environment_motion.csv`，32000数据行，全部列名：`frame, absolute_ps, na, displacement_from_first_A, CN, F6_ids, F6_J200, nearest_V_atom, nearest_V_image, nearest_V_distance_A, nearest_V_F_CN, shared_F_with_nearest_V, shared_F_ids_with_V, nearest_Ni_atom, nearest_Ni_image, nearest_Ni_distance_A, nearest_Ni_F_CN, shared_F_with_nearest_Ni, shared_F_ids_with_Ni`。

I19 `details__data__vectors_geometry__results__event_control_sameframe_geometry.csv`，19047数据行，全部列名：`event_id, na, role, phase, frame, absolute_ps, host_relative_Na_A, fixed_F6_translation_relative_Na_A, fixed_ligand_center_A, fixed_ligand_atom_ids, fixed_ligand_continuous_cart_A, fixed_F6_bond_vectors_A, fixed_F6_distances_A, mean_distance_A, distance_std_A, min_distance_A, max_distance_A, angles_deg, angle_mean_deg, CN_saved, nearest_V_atom_saved, nearest_Ni_atom_saved`。

I20 `details__data__vectors_geometry__results__per_na_vectors_20fs.csv`，32000数据行，全部列名：`frame, absolute_ps, na, global_atom_zero_based, wrapped_frac, unwrapped_cart_A, host_relative_cart_A, host_equal_displacement_from_first_A, saved_step_increment_A, saved_step_length_A, saved_increment_lattice_image, cumulative_lattice_image, unwrapped_frac, CN_saved, F6_ids_saved, nearest_V_atom_saved, nearest_Ni_atom_saved, source_environment`。

完整46条判断、支持等级、反例、计算公式与字段/行定位见 CLAIM_EVIDENCE.csv。科学状态始终为UNVERIFIED；附件一致性、软件核验通过、网页后处理完成与独立科学接受/发表授权互不等同。
