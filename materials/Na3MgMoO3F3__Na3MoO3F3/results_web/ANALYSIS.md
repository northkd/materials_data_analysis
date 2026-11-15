# Na₃MgMoO₃F₃双结构与Na₃MoO₃F₃参照：附件复核报告

分析日期：2026-11-15（UTC）。材料成员：mp-2240200（源32）、mp-2240370（源33／用户34）、mp-18753（不同组成Mo参照）。科学状态：**UNVERIFIED**；本次归档不是独立科学验收，不产生发表授权。

本报告以本对话三批实际上传附件为基础。原报告仅作为待核对解释。没有访问其引用的本机路径，没有补读未上传轨迹，没有运行新AIMD、DFT、NEB、模型训练或构造结构坐标。正文中的“本次重算”仅指对上传派生表、事件记录和已给相位坐标的计算；不表示从VASP原始轨迹重做分析。关键判断对应 `CLAIM_EVIDENCE.csv` 的 C01–C42；实际读取范围和字段对应 `INPUT_COVERAGE.csv`；输入字节SHA256与归档状态见 `RESULT_META.json`。

## 0. 先确认实际输入

### 0.1 实际读取了什么

本次容器中有48个唯一附件：23份CSV（含2份gzip压缩CSV）、14份JSON、5份Markdown、6张PNG。23份CSV合计158,886条数据记录，不含表头。压缩表均成功解压并完整解析。第二、三批有7个同名重传附件；当前每个名称只有一个可读取字节版本，不能把重传当新重复，也不能声称已逐版本证明字节相同。48个当前版本均计算了SHA256。

文件定位规则：下表的M32、M33分别表示实际上传文件名前缀 `core__data__MgMo_full_windows__results__mp-2240200__`、`core__data__MgMo_full_windows__results__mp-2240370__`；D32、D33将其中 `core` 改成 `details`。Mo前缀完整写在表内。它们是附件名缩写，不是访问本机目录的指令。完整名称逐一列于INPUT_COVERAGE。

|实际附件组|数据记录数／读取范围|主要用途|
|---|---:|---|
|M32/M33 `per_Na_motion.csv`|216／144行|六窗逐Na端点、探索和贡献|
|M32/M33 `same_Na_environment_motion.csv`|216／144行|同Na环境与运动对应|
|M32/M33 `departures_returns.csv`|631／1513行|逐窗离返、删失|
|M32/M33 `MSD_curves.csv`|各4184行|原点数、四种参考、多原点及首原点MSD|
|M32/M33 `MSD_fits.json`|各32个顶层窗口／参考记录|实际滞后区间拟合复算|
|M32/M33 `motion_summary.json`|各6个窗口记录|与逐Na表交叉核对|
|M32/M33 `event_summary.json`|完整JSON|事件阈值及窗口敏感性|
|M32/M33 `SUMMARY.json`|完整JSON|mp身份、胞、时间、温度摘要|
|M32/M33 `geometric_space.csv`|各123行，即41帧×3排除距离|几何代理，不当能垒|
|D32/D33 `cation_environment.csv.gz`|60,000／40,000行|逐帧Na/Mg/Mo配位、身份、距离、像；本次共享接触重建|
|D32/D33 `events.json`|1238／232个顶层事件记录|含full、common、after4、late10；不能直接将总记录数当独立事件数|
|D32/D33 `after4_event_sameNa_examples.csv`|309／55行|全部与after4事件的Na及时间键匹配|
|`core__data__mp-18753__motion__per_na.csv`|54行|逐Na运动|
|同前缀 `endpoint_msd.csv`／`msd_time_origins.csv`|1000／500行|固定起点曲线／两种参考各250个滞后点|
|同前缀 `SUMMARY.json`|完整JSON|分窗逐Na距离、拟合、事件、宿主摘要|
|`details__data__mp-18753__motion__events.json`|106个事件|返回、固定配体参考、控制|
|同前缀 `full_phases.csv`|6903行|实际给出的事件及控制相位坐标|
|`details__data__mp-18753__environment__full_phase_environment.csv`|6903行|逐相位CN与身份保留率；ID证据为外部行指针|
|`core__data__mp-18753__environment__event_phase_summary.csv`／`SUMMARY.json`|635行／完整JSON|相位归约及宿主、配位摘要|
|`details__data__mp-18753__regions__reference_visits.csv`|31,046行|六种参考球设置的连续访问段|
|`core__data__mp-18753__regions__transitions.csv`／`SUMMARY.json`|0条数据行但有表头／完整JSON|零转移观察与区域、空间摘要|
|`core__data__MgMo_comparison__THREE_STRUCTURE_COMPARISON.csv`／`.md`|3行／全文|三成员对齐，不代替底层明细|
|`core__methods__MgMo_comparison__METHOD_ALIGNMENT.md`；`core__methods__MgMo_full_windows__METHODS_SPEC.md`；`core__methods__mp-18753__METHODS.md`|均全文|定义和复用边界|
|`core__REPORT.md`|全文|待核对原解释|
|两个MgMo各自 `01_windows.png`、`04_stored_connections.png`；Mo的 `motion.png`、`connections.png`|6张实际上传图视觉核对|不做OCR，不由像素补造数值；拓扑排版不当实际路线|

CSV完整列名和JSON主要字段见附录A；表中同名文件始终按mp、分支、窗口及内容交叉辨认。

### 0.2 身份、时标、参考与估计器

|项目|mp-2240200|mp-2240370|mp-18753|
|---|---:|---:|---:|
|组成|Na₃MgMoO₃F₃|Na₃MgMoO₃F₃|Na₃MoO₃F₃|
|Na／总原子数|36／132|24／88|54／180|
|体积，Å³|1941.664882|1194.545805|2335.975097|
|Na数密度，Å⁻³|0.01854079|0.02009132|0.02311668|
|每Na体积，Å³|53.93514|49.77274|43.25880|
|保存帧／间隔|1000／0.02 ps|1000／0.02 ps|1000／0.02 ps|
|首末绝对时间|0.02–20.00 ps|0.02–20.00 ps|0.02–20.00 ps|
|首末跨度|19.98 ps|19.98 ps|19.98 ps|
|方法记录的run|aimd_1200K|aimd_1200K|aimd_1200K|
|标称温度|1200 K|1200 K|1200 K|
|保存比较表中的ENCUT|410 eV|410 eV|400 eV|
|短壳与初始配体参考|首保存0.02 ps帧|首保存0.02 ps帧|MD POSCAR|
|形式Mo价态|+4|+4|+6|

来源：两个MgMo的SUMMARY、Mo三份SUMMARY、三结构比较CSV及方法对齐。Na数密度与每Na体积互为倒数，不是两条独立机制证据。Mo体积可由54×43.2587981 Å³交叉核对；本批没有其完整3×3胞矩阵，不能从XY图反构坐标。MgMo的胞行向量确实不同：32号为 `(12.169859,0,0);(9.762232,14.366497,0);(6.453269,2.663145,11.105493)`；33号为 `(13.023434,0,0);(8.070309,9.955877,0);(7.928701,3.504736,9.212930)`，单位Å。

mp身份由SUMMARY内的mp_id/formula及比较表锚定。没有mp字段的逐Na、环境和事件表，通过Na数量、1000帧时间网格、事件键、端点复算及比较数值交叉匹配。没有原始运行唯一ID或独立随机种子证明。方法说明记录POTIM=2 fs、NBLOCK=10；本次没有原始INCAR/XDATCAR/OSZICAR，不能将方法声明说成本次重新核验了原文件头。

主运动参考为逐保存步周期展开后，扣全部非Na原子的等权平均平移。32/33分别提供raw、host_equal、host_mass、all_equal的MSD；Mo提供raw和host_relative。去平移不去宿主内部形变。

固定起点端点MSD为 `mean_i |r_i(t_end)-r_i(t_start)|²`。多时间原点MSD为 `mean_(i,o) |r_i(o+lag)-r_i(o)|²`，平均对象是同一run的Na和重叠时间原点。平均净距离是 `mean_i |Δr_i|`，不是MSD开方的同义词。保存步折线路程是相邻帧位移模长之和，不是净输运距离。

本批实有的是1000帧数据，没有另一个strict1000分支或历史1001帧文件。full与common0to20_available为同一条19.98 ps暴露，不重复计数。MgMo绝对4–14 ps包含501帧，而历史命名的500样本窗口另列；discard4从4.02 ps开始，discard4_absolute从4.00 ps开始，两者不能混用。Mo后段重置起点有0.5、1、5、15 ps，不能补造其4–14 ps分支。[C01、C10–C12]

### 0.3 真实缺口及其影响

未上传完整轨迹、原始温度/能量日志、结构POSCAR/CIF、完整固定宿主单元时间序列、已验证共享边/寿命明细，以及MgMo的参考区域访问和逐条转移表。因此宿主拟合和MgMo球访问中的部分数字只能按保存摘要或报告引用；本次不能证明具体相、熔融、真实势垒或每一次实际通过。

Mo的 `full_phase_environment.csv.ligand_ID_evidence` 是诸如 `coordination.jsonl line 71, center 0` 的指针，不是瞬时配体ID本身；所指文件未上传。事件JSON的固定六配体ID也不能替代瞬时短壳全集。因此原报告关于Mo个别时刻“具体O/F编号如何更换”的细节不能全部升级为本次直接核实。[C22]

## 1. 核心判断

**32号：已支持“多数Na持续积累较大的净位移”，但只部分支持材料具有有用的连续迁移能力；不支持直接称为稳定固态快离子导体。** 大位移不是一两个离子抬高平均值，也不是单纯启动的第一下位移。然而它伴随Na/Mg邻域大幅更换及明显宿主重排，当前最重要的问题是“究竟在哪一种宿主状态中移动”，而不是继续抬高MSD。[C02、C05、C17、C31–C33]

**33号：已支持当前20 ps中主要局域往返；不支持把慢运动直接归因于缺空位。** 有可观局部位移、配体交换和跨周期共享接触图，却很少积累净位移。最值得检验的是相邻可停留位置、进入后继续离开的能量以及缺陷是否被俘获，而不只是几何连线够不够多。[C03、C07、C19、C28]

**Mo参照：已支持局域运动，并构成“配体更换／单元转向足以驱动持续Na输运”的反例。** 它不是第三个MgMo重复，也不是“只拿走Mg”的单因素实验。它与MgMo在组成、形式Mo价态、胞、Na排列、短壳参考、截断和电子设置上均不同。[C04、C08、C21、C24、C34]

本次对原报告最实质的补充有四处：一是从MgMo逐帧配体表重建了未做凸包筛选的共享接触；二是发现32号Na1“后快照O增加”晚于返回，不能用来解释最初前进；三是用完整事件/控制核实换配体在控制中也很普遍；四是指出晚窗MSD拟合的名义2–10 ps实际只有2–5 ps，以及Mo瞬时配体ID的真实缺口。运动分类大体保留，但机制语气必须收紧。

## 2. Na运动与具体环境对应

### 2.1 先把三个成员的运动尺度放在同一口径下

|重算／核对量|32号|33号|Mo参照|
|---|---:|---:|---:|
|full端点MSD，Å²|32.105276|0.733706|0.568986|
|full平均净距离，Å|5.306303|0.751346|0.675918|
|逐Na r90均值，Å|5.716562|0.910310|1.026146|
|full末端>2 Å|35/36|0/24|0/54|
|full前三大Na的MSD贡献|21.2205%|40.9934%|24.5128%|
|15–20 ps端点MSD，Å²|10.913172|0.992419|0.760886|
|15–20 ps末端>2 Å|22/36|1/24|0/54|
|每Na平均保存折线路程，Å|205.9157|207.5634|206.6638|

来源：两个per_Na_motion.csv、Mo per_na.csv、Mo SUMMARY的window_sensitivity。端点MSD和贡献由本次逐Na距离平方重新归约；MgMo向量模长与endpoint_A最大差分别1.78×10⁻¹⁵、2.22×10⁻¹⁶ Å。Mo后段54个距离的平方均值与保存摘要一致。r90是各Na相对其窗口起点的90%时间探索半径，不是位点间距，也不代表已走过完整通道。

32号全程top1只有7.6227%，top3为21.2205%；大量Na参与。33号top3比例较高，但其MSD总量很小，不能把“少数贡献突出”误读成少数离子已经远程扩散。三者累计路程几乎相同，而净距离完全不同，直接否定“累计走得多就传得远”。[C02–C09]

### 2.2 32号：有大范围离开，也有在活动环境中返回的Na

Na15末端9.3863 Å，r90=9.1023 Å，最大探索10.2808 Å；Na34和Na5末端分别8.8703、8.8589 Å。相反，Na29最大离开3.1100 Å，最后仅1.5669 Å，7次离开1 Å中有6次回到0.5 Å内。Na29的六近邻表仍记录全程遇到29个不同ID、首末六近邻Jaccard仅0.0909：明显换邻居并不保证最终走远。六近邻统计与短壳配体统计定义不同，不能直接混算保留率。[C06、C09]

**较活跃的同Na证据链：Na15，full事件144，15.00–15.24 ps。** 该合并片段净位移1.7739 Å；200 fs前后中心距2.0567 Å，事件表保存的局部平移诊断为2.2572 Å，两种诊断到20 ps均未观察到回到事前区域，剩余随访4.76 ps。局部参考数字只按该字段报告，不能与参考区域分析的最近四Mo模式混称为同一个参考。

逐帧短壳表给出：14.80 ps为1O+3F，即O69和F106/F112/F122；15.00 ps仍有O69，并增加F118；15.24 ps仍是1O+4F，但F118换成F130；15.44 ps变成O89/O96及F105/F106/F122/F130。14.80 ps的O69通过共享短壳接触连接Mo54；15.44 ps的O89、O96分别对应Mo53、Mo60。Na15也同时与多个Mg中心共享F/O。因此有证据说它从一个Mo/Mg配体邻域进入另一个邻域，而不是只在一个完全不变的笼子里振动。

距离亦有实质变化：O69在14.80、15.00、15.24 ps距Na分别2.8492、2.1669、2.0972 Å；到15.44 ps，O89/O96距离为2.7417/2.3459 Å。短壳径向畸变随上述四时刻为0.1496、0.0360、0.0584、0.0932，并非单调降低。F118在候选片段起点已进入壳层，O69在片段中仍保留，O89/O96的后快照出现于片段之后；这些时序不允许简单宣布“O配位改变首先驱动Na跳跃”。事件起点是算法阈值的起点，不是物理运动唯一的起始瞬间。

同一个事件的合法控制相位边界13.24–13.88 ps也从3O+2F变成1O+4F，配体ID明显更换。控制排除了同Na所有候选事件的闭禁区，但不是“完全不动的冻结环境”。因此这条链支持**运动伴随邻域交换**，尚不足以证明F门控、某个Mo转动或Mg重排是原因，也没有把它与某个稳定Na位点或具体参考球转移接上。MgMo转移明细缺失，不能把Na15指定到报告中的26次球访问之一。

定位：D32 cation_environment的CSV物理行44356、44956、45676、46276（表头为第1行）；frame739/749/761/771、center_1based=15；D32 events中window=full,event_id=144。原子编号为该表一基编号；周期像是每帧几何规范，不把像编号改变本身计作跳跃。[C17]

**明确返回反例：Na1，full事件2，4.74–5.02 ps。** 片段净位移2.3720 Å，200 fs中心距只有1.1212 Å，5.12 ps已返回事前中心1 Å球内。实际时序为：4.54 ps 3O+1F；4.74 ps 0O+3F；5.02 ps 2O+2F；5.12 ps返回时2O+1F；5.22 ps后快照才是4O+1F。原报告强调的“由3O增至4O”跨越了运动、返回及再次环境调整，4O快照在返回之后，不能用作最初前进的先因证据。

具体地，事前O75/O87/O88与F115，到返回帧成为O61/O87与F115，返回后环境没有恢复成原ID集合。这是“空间回来，但邻居不必回来”的直接例子。定位：D32 frame226/236/250/255/260，center1；CSV行13562/14162/15002/15302/15602。[C18]

### 2.3 33号：最活跃的末端个体也不能代表持续扩散

Na21最终仅0.1048 Å，中间最大1.7466 Å，25次离开后25次返回。Na3最大1.3094 Å，8次离开均返回。全程最远Na5最终1.7574 Å，而r90只有0.8306 Å：绝大多数时间探索范围较小，末端较远是少数末段时刻的现象。其full事件3跨19.78–20.00 ps，post缺失且right_censored；不能因为后5 ps只有它超过2 Å，就宣布材料在尾端进入扩散阶段。[C07]

Na12的full事件10（7.82–8.08 ps）净移2.1228 Å，200 fs中心距0.9179 Å，保存局部平移诊断0.6952 Å，8.12 ps已返回。7.62 ps前快照和8.28 ps后快照都是3O+1F，但ID由O44/O52/O62/F68变成O44/O52/O60/F76；O52在所列快照中有非零周期像，配体身份与像均保留。片段末端8.08 ps短暂为3O+3F，8.12 ps返回时已降为3O+1F。由此，CN相同不等于环境未变，CN升高也不意味着永久前进。

其控制在6.94–7.60 ps也从3O+3F变到3O+0F，而未触发同一候选规则。该材料的局域限制不能简单描述成“配体完全不换”或“没有结构活动”。定位：D33 events中full/e10；cation_environment frame380/390/403/405/413、center12，关键CSV行15213/15613/16133/16213/16533；控制边界frame346/379。[C19]

### 2.4 Mo参照：离开片段与停留中心迁移相差很大

Na8最大探索2.6319 Å，最后0.4250 Å，有25对离返。Na31最终0.2363 Å；Na43最终1.8956 Å，末次离开在frame993，即19.88 ps，随访只有0.12 ps。0/54末端>2 Å是本窗的观察，不是所有温度和无限时间下不能扩散的证明。[C08]

Na1事件0在1.62–1.82 ps净移2.1076 Å，但200 fs前后中心仅差0.2891 Å，1.86 ps已返回。Na8事件24在6.60–6.84 ps的中心差0.5569 Å，6.88 ps返回。以实际上传full_phases坐标复算106个事件向量及104个完整200 fs中心距离，与events保存数值的差均为0；这是相位数据上的复算，不是完整20 ps轨迹重新计算。

Na8事件前／中／后的平均O/F数为1.8/2.0、1.3077/2.5385、2.1/1.9。其合法控制7.26–7.50 ps的前后平均O数从1.1到2.5，F从2.8到1.6，变化不小于事件的简单前后差。相位环境6903行重新分组所得635项相位汇总与保存表完全一致。这里能够核实CN及保留率变化，却不能从未上传的coordination.jsonl补造瞬时配体ID链。[C21、C22]

### 2.5 全部候选与控制：不要只选漂亮例子

|full候选的200 fs中心分类|32号|33号|Mo参照|
|---|---:|---:|---:|
|候选数|375|72|106|
|较晚返回|250|35|64|
|候选末端已在前区|48|26|40|
|中心完整但随访内未返|74|0|0|
|缺前／后中心|3|11|2|
|事件本身完整前中后相位|370|61|104|
|合法控制数|375|72|106|
|不同完整控制区间数|360|68|101|

这些由events重新分类，分母为full全部候选，不混原报告persistent子集。32号372个完整中心与370个完整事件相位不矛盾：固定停留中心的post使用end..end+w−1，相位表post使用end+1..end+w，末边界要求不同。缺200 fs中心不由400 fs窗填补。未返是有限随访右删失，不自动变成永久离开。[C13–C16]

本次检查同Na控制的前10帧、事件本体及后10帧与全部闭禁区：三成员均无越界、无禁区交叠。控制复用最多为32号3次、33号3次、Mo2次；不同控制之间仍可能部分重叠，且同Na相关，不能把360/68/101当独立实验数。

仅在事件相位完整的配对中，取事件start−10与end+10两张短壳快照，控制取同样相对边界：32号事件366/370换ID，控制360/370换ID；33号事件53/61换ID，控制56/61换ID。O/F数相同而ID改变的事件分别44、8个。这个重算直接反驳“换ID就是迁移事件”的充分性。它不证明两组严格等效，不做伪独立显著性检验；控制按候选规则挑选，也不是随机因果对照。[C20]

阈值敏感性仍存在：32号full在1.2/1.5/1.8 Å阈值下候选516/375/201，33号119/72/39；规则计数强烈依赖阈值，不可当晶格跳跃真值。重叠候选合并后直度可低于原筛选0.7，不自动视为数据错误。

## 3. 机制解释、竞争解释与反例

### 3.1 MSD支持运动类型，不单独授予输运资格

本次从MSD_curves重新拟合全部160个MgMo区间，斜率与MSD_fits最大差1.11×10⁻¹⁵ Å²/ps。32号绝对4 ps以后、host_equal、lag=2–10 ps：斜率1.692394 Å²/ps，截距1.204408 Å²，R²=0.998033，幂指数0.852631；斜率/6=0.282066 Å²/ps只作有限窗诊断。后段持续增长说明大位移不全是首几帧造成，但非零截距、窗口依赖、相关原点和宿主变化使其不能直接成为稳定固相自扩散或电导。

33号同窗斜率0.006144 Å²/ps、截距0.603142 Å²、幂指数0.047775，主要是平台上的缓慢变化。late15toend保存的拟合标签仍写lag_range=[2,10]，实际31个点仅2–5 ps，最后只有1个原点。full最后保存曲线点为lag=19.9 ps，只有5个原点，其值0.927733 Å²也不能与19.98 ps的单一起点端点0.733706 Å²混为同一估计器。

Mo的host_relative斜率在0.1–1、0.5–2、1–5 ps依次0.047875、0.024143、0.006207 Å²/ps，截距约0.54–0.58 Å²。六个含raw的拟合本次复算一致；没有稳健长时线性增长段。三个材料均没有独立种子误差条，重叠原点只改善同轨迹平均，不增加独立材料样本。[C10–C12]

### 3.2 配位和保留：比较必须带上切距

|各自短壳全帧平均|32号|33号|Mo参照|
|---|---:|---:|---:|
|Na O/F数|1.9161/2.7054|2.2330/2.8699|2.1041/2.4170|
|Mg O/F数|1.6871/2.7688|2.4519/2.7918|不适用|
|Mo O/F数|2.9696/0.0557|2.9596/0.0420|3.0000/2.7147|
|Na初始ID保留|20.80%|77.26%|34.42%|
|Mg初始ID保留|39.83%|86.75%|不适用|
|Mo初始ID保留|89.46%|98.65%|95.24%|

MgMo数值来自本次完整环境表重算；Mo为已上传环境SUMMARY支持，不冒充全帧Mo配体明细复算。MgMo合计100,000行的CN与ID数组长度、O/F计数、距离不超过各自cutoff、frame到absolute_ps对应均通过核查。[C23]

32/33的Mo短壳切距分别约2.038/2.019 Å，Mo参照约2.332 Å。MgMo初始Mo短壳均约3个O，但这不是“Mo只与3个原子发生化学作用”的证明。MgMo自身提供共同Mo=2.5 Å的固定半径列，其Mo-F均值为0.3597、0.7049，明显高于短壳0.0557、0.0420。扩大到保存的次层还可见更多F。改变半径能显著改变配位描述，不能拿跨材料不同短壳的F数直接优选掺杂或判定成键强弱。[C24]

可保留的解释是：32号Na和Mg更难保持原邻域，33号更多保持原局部环境。但Mo参照Na保留只有34.42%，仍然局域，因此“低保留率必然带来净输运”被反例否定。保留率也依初始集合、中心运动和配体运动共同变化，不能单独分辨谁驱动谁。

### 3.3 本次新增：共享接触可以重建，真实通过仍不可以

MgMo环境表逐帧保存中心、配体ID和image_translations。本次用同一个配体ID配对中心，中心j相对i的整数平移取 `T=n_i−n_j`；边键为中心对和T，不进行三维凸包共顶/共棱/共面筛选。随后从整数回路平移计算每个连通分量的秩，再取最大，不能把互不相连分量的回路拼成一个更高维网络。

新结果：32号Mo共享短壳候选在692/1000帧出现，每帧0–5边，平均1.174边，所有帧最大分量周期秩仍为0；33号全部1000帧均0边。32号2.10 ps的Mo49与Mo53共同接触O84，距离分别1.9714和1.9760 Å，均低于各自约2.038 Å切距，对应整数平移(0,−1,0)。这正是低配位凸包过滤可能未纳入的接触候选。[C25、C26]

因此原报告“32号已验证Mo边0–2”的记录与本次原始候选0–5并不冲突；两者筛选不同。原报告77段已验证几何串、最长0.06 ps仍只能按文档引用，本次没有其寿命明细，未重算连续同像几何寿命。对于33号，本次有配体明细支持短壳候选为零，比单看空白图更强；但仍不能推成更远相互作用、所有半径下都无连接。

从同一表重建完整Mg/Mo共享接触图的最大分量秩，32号0/1/2/3帧数=244/390/276/90，33号0/1/2=2/107/891，与保存阳离子–配体二分图摘要完全一致。这是对字段和图定义的交叉校验，不是Na扩散维数测量。[C27]

Na图也提供反例：原已验证子集32/33分别997/996帧rank3；本次未几何筛选的Na共享接触图为999/997帧rank3。33号依旧局域，说明共享配体的周期连通不是充分的运输条件。Mo参照989/1000帧rank3仅由保存摘要支持，不能与MgMo本次raw图当同一筛选排名。rank0也不等于没有边，32号Mo有限簇就是现成例子。[C28]

### 3.4 参考区域能说明“访问了哪里”，不能给完整位点容量

MgMo比较表给出的0.8 Å、至少200 fs外来初始Na区域停留：32号全宿主参考26段、四Mo参考41段，33号均0。这些本次只能按汇总支持。原文Na3、Na5跨区域之间长时间未分配的个例缺转移明细，不能被重述为本次逐条核实的路径。[C29]

Mo有实际31,046段访问表，本次重计六设置，各自恰覆盖54,000个Na×帧，外来参考区≥0.2 ps停留均0；0.8 Å全宿主和四Mo参考的唯一分配比例分别69.7278%和81.1296%，与SUMMARY一致。transitions.csv确为有表头但零行。局部参考使覆盖率提高，却不改变没有持续外来球访问的结论。[C30]

这些球只围绕首帧已占Na位置，未覆盖帧不等于空位，零外来访问不等于不存在其他可占位置。32号观察更接近邻域交换，但“从旧稳定位置A，经可停留中间位置B，再到C，并在稳定宿主中重复”这一完整交换链，三者都没有由现有附件证明。

空间代理也不能补齐此链。MgMo的12³网格在统一1.5 Å宿主排除下，开放比例平均42.17%与37.85%；1.8 Å时降为19.04%与14.10%，连接判定明显变化。Mo使用另一网格规则，不能严格数值排名。统一距离不是离子半径，不含自由能或Na排斥；“图上有空隙”与“能进去、能留下、能再出去”是不同问题。

### 3.5 漂移、宿主形变、启动热历史分别讨论

**整体漂移。** MgMo四种平移参考的MSD仍保留远移／局域差别；Mo全程raw端点0.476513 Å²、去宿主平移0.568986 Å²，都属有限范围运动。不能把差别归结为整体平移。两个MgMo保存最大帧间增量1.381/0.990 Å小于各自半最小奇异值界4.294/3.906 Å，但这些是派生诊断，本次没有原轨迹重新展开，也不能据此恢复20 fs之间未保存的绕行。[C33]

**宿主非刚性重排。** 比较摘要中末端宿主整体刚体拟合残差为4.737、1.223、2.382 Å。32号很大，去掉整体平移或转动并不能将其解释为骨架不动。原报告给Mg固定初始配体非刚性残差均值2.612/0.429 Å，Mo单元均值0.315/0.138 Å；这些MgMo单元数值没有明细表，本次只按报告引用。Mo环境SUMMARY直接给固定Mo单元均值0.2191 Å，末端Mo/O/F去平移RMS=0.5168/2.5734/2.5739 Å，支持配体整体活动大而局部Mo单元相对保持。原文113.4°末端平均转角只有报告引用，不能说本次重算了该角度，更不能声称转动先于Na位移。[C31]

**启动温度。** MgMo SUMMARY温度块保存14155 K@0.072 ps与14612 K@0.076 ps；4–10 ps均温约1200.17/1200.12 K，15–20 ps约1200.28/1200.21 K。Mo的13540 K@0.072 ps在本批仅见文档引用。如此大的启动峰是必须优先追查的异常，但没有原始逐步温度日志，不能排除记录或解析问题，也不能把它写成已独立验证的热冲击全过程。若峰值真实，后段回到1200 K不撤销此前重排历史；若峰值是解析错误，原报告的热历史解释必须修正。32号后段仍大位移只排除“一切位移都集中在最初几帧”，不能排除启动改变了后续宿主。[C32]

三个成员的Na浓度、胞、初始布局、形式价态、电子设置及启动均不受控；32比33更疏且更活跃只能是对应关系。Mo更密却局域否定“密度高足以持续输运”，但不能证明密度越低越好，也不能估计Mg的单因素效应。[C34]

## 4. 改造候选：理由、收益和代价

当前不提出长名单。首先应把32号的宿主状态问题和33号的局域退出问题分开；Mo参照的作用是检验机制充分性，不是凭另一组成替32号完成因果消融。

### 4.1 候选一：Mg替Na，同时指定另一个Na位置为空；优先作为33号的诊断候选

条件式为 **Na_(3−2x)Mg_(1+x)MoO₃F₃**。假设Na⁺、Mg²⁺、O²⁻、F⁻且Mo保持形式+4，每个额外Mg占一个Na位置，再少一个Na：`(3−2x)+2(1+x)+4−6−3=0`。这是已支持的形式配平，不是已经支持的固溶或增导。[C35、C36]

为什么选Mg而不另列Ca/Al等：它已经在MgMo母体存在，本次环境表实际显示Mg可处于O/F混合邻域，因此作为第一项对照可减少新增元素变量；但没有跨元素占位能、尺寸与成相比较，不能称Mg最优。为什么尝试Na位置：直接改变Na占据，并问相邻Na能否进入空出的区域后继续离开；不是因为已经证明33号缺空位，也不是因为母体Mg能稳定存在就必然愿占Na位。

潜在收益是减少某些占据阻挡或提供中间停留机会；代价是Na总数减少2x。即使不考虑体积和相关性改变，若全Na均被当作等价载流数量，补偿数量损失需要每Na迁移能力的增益至少超过 `3/(3−2x)`；这只是条件性数量预算，不是电导预测。真实移动比例和相关因子尚未知。

目前小胞中加一个Mg，对32号12个化学式单元为x=1/12、Na36→34（少5.56%）；对33号8个单元为x=1/8、Na24→22（少8.33%）。它们不是相同掺杂浓度，也不是稀释极限；指定的“一个空Na位置”仅相对所选初态，不能当完整位点容量下的实验空位率。

主要失败方式是Mg偏好别的位置、Mg–空位缔合或俘获邻近Na、堵塞关键连接、以Mo变价或阴离子缺陷代替预期补偿，以及分相。32号本来已经远移，继续造缺陷可能只是进一步破坏宿主，故不应先于宿主核验。对Mo参照机械套用时公式应为Na_(3−2x)Mg_xMoO₃F₃并另行假设Mo+6；它不是Na₃MgMoO₃F₃，当前不优先推进。

最小可区分验证是：先核Mg实际占位和补偿；在相同浓度下区分靠近与远离空位、Na位与原Mg位的稳定性及缔合，再检验一次“进入并继续离开”而非只进入的完整链。若Mg不稳定于Na位、空位总被绑定、宿主分相，或Na活动仅增加局部往返而不增加连续交换，此路线即被否定。当前没有执行这些能量或结构计算。

### 4.2 候选二：先用同一化学体系的小幅Na含量变化检验可逆氧化还原；定位为电极探索而非保证增导

MgMo可写 **Na_(3−y)MgMoO₃F₃**；固定Mg/O/F形式电荷下，Mo形式价态为4+y。选这一路线而不先换Mo，是因为它保留母体元素，直接检验储Na用途真正需要的Na抽取与Mo响应，同时避免把新掺杂元素效应混入。它不再是“只造空位而电子状态不变”的实验。[C37]

Mo参照若考虑加Na，可条件性写 **Na_(3+y)MoO₃F₃**、Mo形式6−y，但必须先找到可占空间和稳定结构；初始参考球不是可加Na容量证明。反过来，直接从Na₃MoO₃F₃继续去Na而仍只让Mo补偿，会要求形式价态高于+6，不能照搬MgMo的+4出发路线；可能的阴离子反应或其他补偿须另查，不能由本包预言。

潜在收益是发现可逆Na含量范围及其对交换的影响；代价是Na数量、电子状态及相稳定同时改变。风险包括局域电子俘获、电子漏导增加、不可逆Mo/阴离子反应、析出第二相、转换反应或结构崩塌。对于电极，电子导电可能有用；对于包覆/电解质，同一电子导电增益可能反而有害。

最小验证是小范围Na含量变化后的实际价态、成分和结构，与回到原含量后的恢复性相互核对，随后才讨论电压与容量。若Na去除只引起不可逆分解，价态变化不符合设想，或回嵌不能恢复结构，就否定“可逆脱嵌电极”的路线。没有电压、能量或实际可逆电子数，本次不报理论容量充当性能。

### 4.3 对32号更优先的不是新元素，而是初态与热过程核验

维持Na₃MgMoO₃F₃组成，核实启动温度及弛豫初态，比较温和热启动下宿主状态与Na远移是否重现，是32号最有区分力的下一步。这里不指定未经验证的相或合成温度。若远移只出现在剧烈初期重排后的状态，原MP结构的“快离子晶体”解释应否定或重命名为另一实际宿主状态的结果；若在稳定宿主且不同初态/种子下重复出现，才值得增加后续输运投入。

### 4.4 成本、毒性与制备风险的边界

本包无原料报价、收率、前驱体SDS、空气/水稳定、溶出或热分解资料，不能把任何路线称为低成本、无毒或易合成。Mg路线不新增Mo元素，但仍保留Mo和F；是否比其他路线省钱要按实际前驱体、气氛、废物处理和相纯度核算。含氟体系的湿气、酸接触、挥发物与HF风险应按真实前驱体和分解行为核实，不能仅由化学式断言本材料必定放HF。NIOSH可溶Mo化合物及HF资料仅提示应查的职业暴露类别，不证明这三个晶体属于同一溶解性或危险等级。[C42；外部来源E4、E5]

## 5. 用途优先级

|方向|本包线索|关键代价与缺项|当前投入判断|
|---|---|---|---|
|薄包覆层，目标约10⁻⁶ S/cm|高温局部活动说明Na并非完全静止；33和Mo可作局域结构对照|无室温离子电导、电子绝缘、电极电位下稳定性和界面反应证据；32宿主重排尤其不利于直接外推稳定包覆|可作条件筛选，但不能入选；先证化学/电化学稳定和电子阻隔，再查实际厚度下Na阻抗|
|主体固态电解质，目标约10⁻⁴ S/cm|32提供最大Na净运动信号|稳定宿主未证，单温短轨迹不能外推；33/Mo目前没有持续远移；离子相关、界面及致密化问题均缺|三者均不具资格；32仅优先做“宿主稳定后还能否快”的验证，33做机制对照，Mo保留参照|
|储Na电极|MgMo形式Mo+4为检验抽Na氧化还原提供账面起点；Mo+6参照可检验另一反应方向|实际价态、自旋/电子输运、可逆Na位置、电压、容量和循环结构保持全部缺失；大MSD不能代替可逆脱嵌|MgMo值得小规模可逆性筛查，但不能指定正极/负极；Mo不因形式价态直接获得容量或负极资格|

电化学稳定是给定电极电位和化学势下是否反应；电子输运是是否漏电子；界面反应是接触另一相后是否生成产物；机械/堆叠压力是接触、变形、开裂等另一组问题。现有固定胞高温轨迹没有任何一项器件数据，不能用“高压稳定”混称高电压稳定与承受机械压力。[C38]

目标电导也不是脱离厚度的器件门槛。仅作理想平面层算术：`R_A=L/σ`，假设10 nm、σ=10⁻⁶ S/cm，则体相面电阻1 Ω·cm²；100 nm为10 Ω·cm²；100 μm主体、σ=10⁻⁴ S/cm则为100 Ω·cm²。未计界面/晶界/孔隙，这些是假设厚度下的数量说明，不是本材料预测。[C40]

研究投入顺序应为：先查32的热启动与宿主状态，并保留33作同组成结构对照；其次用33辨别位置/退出能量/缺陷绑定的限制；再按实际价态和可逆性决定是否走电极路线。Mo参照优先保留作“邻居更换和单元活动仍不足以持续输运”的机制对照，不优先将其包装为主体电解质。

## 6. 下一步验证与明确否定条件

|需区分的问题|最小有判别力的验证（本次未执行）|会否定当前假说的结果|
|---|---|---|
|32远移是原结构内输运，还是启动改变宿主后的运动？|原始温度/能量解析核对；受控初态和热启动；同时比较Na与Mg/Mo/O/F的长时运动及结构保持|温峰为解析错误则否定对应热冲击证据；温和启动不再远移或必须依赖强烈宿主破坏，则否定原结构稳定快导解释|
|33受限于缺可停留位置、难进入、难退出，还是有限采样？|先确定真实可占位置；分别考察进入和继续离开的能量与实际访问，而非只画初始球|存在位置但退出被困，否定“只增加空位置就足够”；观察足够长仍只折返，否定由当前尾部翘起推扩散|
|Mg@Na与空位是否有利？|相同浓度和实际占位下，区分近/远缺陷绑定；与未改造结构比宿主保持和连续交换|偏位、分相、强缔合、Na数量减少而净交换不增，均否定该配方收益|
|单元运动是否真正门控Na？|同Na、同局部单元的方向、时序和匹配控制；区分小倾斜、大转向及非刚性改变|同样活动在不远移Na和控制中同样出现，且无先行/条件依赖，则否定“活动本身足够”而非否定所有可能耦合|
|能否作包覆、电解质或电极？|室温附近离子/电子输运分别测定，目标电位与具体界面反应，压力/机械测试；电极另核可逆Na含量、价态、电压和结构|电子漏导、界面持续分解、压力下失效或不可逆反应，按各用途分别否定；不能用一项通过代替其他项|

本次已经否定的是若干“充分条件”：累计路程大、换配体多、Na共享图rank3、单元转向大，都不足以单独确认持续输运。尚未识别的是每个材料的唯一限制能垒、完整稳定位点容量和实际载流Na比例。没有把未知写成零，也没有把未返回写成永久迁移。

## 附录A：实际CSV列名与JSON主要字段

以下同名模式的两份MgMo文件具有相同表头；完整文件名与读取行数在INPUT_COVERAGE逐行给出。

**MgMo per_Na_motion.csv：** window, Na_1based, CIF_label, start_frame, end_frame, observed_span_ps, endpoint_A, endpoint_vector_A, r90_A, max_A, sampled_path_A, departures_gt1A, returns_lt0p5A, unreturned, sensitivity_departures_1p5A, sensitivity_returns_1A, endpoint_MSD_share。

**MgMo same_Na_environment_motion.csv：** window, Na_1based, start_absolute_ps, end_absolute_ps, endpoint_A, r90_A, mean_O_CN, mean_F_CN, six_nearest_ID_Jaccard, six_nearest_distinct_IDs。

**MgMo departures_returns.csv：** window, Na_1based, leave_frame, return_frame, leave_absolute_ps, away_ps, max_A, right_censored。

**MgMo MSD_curves.csv：** window, reference, start_frame, end_frame, lag_ps, origins_per_Na, multi_origin_MSD_A2, first_origin_MSD_A2, max_individual_contribution, top3_individual_contribution。

**MgMo geometric_space.csv：** frame, absolute_ps, grid, grid_vectors_A, uniform_exclusion_A, host_open_fraction, all_atom_open_fraction, host_open_components, host_open_periodic_rank。

**MgMo cation_environment.csv.gz：** frame, absolute_ps, center_1based, element, O_CN, F_CN, mixed_CN, cutoff_A, low_CN, high_CN, fixed_O_CN, fixed_F_CN, secondary_O_CN, secondary_F_CN, ligands_1based, ligand_elements, image_translations, canonical_images, distances_A, angles_deg, radial_distortion, initial_ligand_retained_fraction。

**MgMo after4_event_sameNa_examples.csv：** Na_1based, start_absolute_ps, end_absolute_ps, outcome, full_phase, control_start_relative_frame, pre_O_F, post_O_F, pre_ligands_1based, post_ligands_1based, center_separation200_A, first_return_window_frame, return_followup_ps, local_separation200_A, fixed_ligand_rigid_diagnostics。

**Mo per_na.csv：** na, endpoint_A, endpoint_vector_A, max_from_start_A, r90_A, path_A, leave_return_pairs, leave_return_times, unreturned_last_leave_frame, exposure_Na_ps, leave_return_rate_per_Na_ps, endpoint_returned, Na_one_based。

**Mo endpoint_msd.csv：** frame, absolute_ps, host_relative_MSD_A2, raw_MSD_A2。

**Mo msd_time_origins.csv：** reference, lag_frames, lag_ps, MSD_A2, overlapping_time_origins。

**Mo full_phases.csv：** event_id, Na_one_based, segment, phase, frame, absolute_ps, host_relative_x_A, host_relative_y_A, host_relative_z_A, raw_x_A, raw_y_A, raw_z_A, phase_complete, control_legal。

**Mo full_phase_environment.csv：** event_id, Na_one_based, segment, phase, frame, absolute_ps, CN_O, CN_F, retained_initial_ligands, distance_from_start_A, ligand_ID_evidence。

**Mo event_phase_summary.csv：** event_id, Na_one_based, segment, phase, n_frames, first_ps, last_ps, CN_O_mean, CN_F_mean, retention_mean。

**Mo reference_visits.csv：** Na_one_based, reference_id_zero_based, start_frame, end_frame, start_absolute_ps, end_absolute_ps, duration_ps, n_samples, is_foreign_initial_reference, right_censored, complete_site_universe, reference_mode_radius。

**Mo transitions.csv：** reference_mode_radius, Na_one_based, from_reference_id, to_reference_id, departure_frame, arrival_frame, departure_absolute_ps, arrival_absolute_ps, unresolved_gap_ps, return_frame, return_absolute_ps, followup_ps, censoring, direct_path_observed, crystallographic_exchange_proven。确为0条数据行。

**THREE_STRUCTURE_COMPARISON.csv：** formula, mp_id, Na_n, atoms, frames, absolute_start_ps, absolute_end_ps, span_ps, ENCUT_eV, Na_density_Aminus3, volume_per_Na_A3, endpoint_MSD_A2_full, Na_gt2A_full, endpoint_MSD_A2_absolute15to20, Na_gt2A_absolute15to20, r90_mean_A_full, r90_median_A_full, Na_CN_O, Na_CN_F, Na_initial_ligand_retention, Mo_CN_O, Mo_CN_F, Mo_initial_ligand_retention, environment_reference, host_endpoint_rigid_residual_A, event_count_full, complete_event_phases, legal_sameNa_controls, event_fixed200_later, event_fixed200_already_pre, event_fixed200_no_observed_return_censored, event_fixed200_missing, foreign_ref0p8_ge200fs_host, foreign_ref0p8_ge200fs_local4Mo, Na_shared_rank_hist_conditional, nonNa_bipartite_rank_hist_conditional, Mo_shared_contact_count, Mo_sensitivity_edge_count, vacancy_fraction, barrier_eV, true_crossing_verified, room_temperature_conductivity_S_cm, scientific_acceptance, publication_authorized。

**两个MgMo SUMMARY.json主要字段：** formula, mp_id, frames, atoms, Na_n, dt_ps, first_absolute_ps, last_absolute_ps, span_ps, cell_A, volume_A3, Na_density_Aminus3, volume_per_Na_A3, max_saved_increment_A, half_sigma_min_A, saved_image_sufficient_certificate, motion_windows, events, temperature_blocks, original_SHA_unchanged, runtime_s, scientific_state, publication_authorized, limits。原始SHA未变的布尔值是源摘要声明，不是本次重新核原轨迹。

**motion_summary.json：** window, start_frame, end_frame, start_absolute_ps, end_absolute_ps, observed_span_ps, endpoint_MSD_A2, Na_gt2A, mean_r90_A, top1_share, top3_share, top3_Na_1based, departures, returns。

**event_summary.json：** summaries, threshold_sensitivity, inherited_code_sha256, threshold, rule_events_are_not_true_hop_counts；threshold含net_A/span_fs/straightness_min/post_fs/pair_gap_fs/pair_tol_A。

**MSD_fits.json：** window, reference, fits；fit含lag_range_ps, n_lags, slope_A2_per_ps, slope_over6_A2_per_ps, R2, alpha。

**MgMo events.json主要字段：** na, t_start, t_end, disp, net_disp, path, straightness, post_window_fully_observed, outcome, event_id, window, window_start_global_frame, Na_1based, start_global_frame, end_global_frame, start_absolute_ps, end_absolute_ps, full_event_phase, control_start_relative_frame, control_full_phase, sameNa_all_event_closed_bans, fixed_pre_ligands_1based, fixed_pre_ligand_elements, fixed_ligand_rigid_diagnostics, environment_pre, environment_post, dwell_by_window, local_translation_dwell200, control_dwell200, control_environment_pre, control_environment_post。

**Mo motion SUMMARY主要字段：** schema, window, reference, per_na, per_na_raw, endpoint_A, r90_A, max_from_start_A, endpoint_gt2A, leave_return_pairs, unreturned_last_leave, event_counts, base_event_outcomes, events_with_full_phases, events_with_legal_control, control_reuse_counts, global_200fs_return_status, window_sensitivity, time_origin_msd_fits, host_endpoint_RMS_A, host_endpoint_rigid_fit, host_shift_end_A, rule_class_histogram, complete_site_universe, scientific_acceptance。

**Mo environment SUMMARY主要字段：** schema, frames, interval_ps, center_elements, CN, CN_hist, retained_initial_ligand_atom_ID, bond_distortion, periodic_rank_frame_hist, Mo_is_all_nonNa_cation, nonNa_bipartite_includes_O_F_vertices, segments, cutoff_sensitivity_100fs, geometry_low_dimension_limit, phase_environment_rows, host_endpoint, fixed_Mo_nonrigid_RMS_A, scientific_acceptance。

**Mo regions SUMMARY主要字段：** schema, reference_definition, radii_A, minimum_residence_ps, continuous_duration, complete_site_universe, reference_summary, transition_count, primary_transition_count, space_frame_count, space_frame_spacing_ps, space_open_fraction, space_periodic_rank_hist, density_Na_A-3, volume_per_Na_A3, density_constant, scientific_acceptance。

**Mo events.json主要字段：** event_id, na, start_frame, end_frame, start_relative_ps, end_relative_ps, disp_A, net_disp_A, path_A, merged_straightness, d_min_A, detection_window_fs, post_distance_A, post_full, outcome, site_transition_proven, Na_one_based, global_atom_index, start_absolute_ps, end_absolute_ps, control, full_phase_complete, window_end_absolute_ps, global_dwell, raw_event_vector_A, host_relative_event_vector_A, fixed_ligand_layers, control_global_dwell。global_dwell内按100/200/400 fs保存pre/post、center_separation_A、return及删失；空值保留。

## 附录B：本次新计算与复现口径

1. 逐Na端点：`MSD=Σd_i²/N`；贡献 `s_i=d_i²/Σd_j²`；top3为最大三项之和。只在同mp、同窗口、同参考内归约；full/common不合并。
2. OLS：从保存MSD点拟合 `MSD=a·lag+b`，不强制过零；R²按残差平方和计算；alpha为log(MSD)对log(lag)的斜率。MgMo160个区间、Mo6个区间；记录实际可用lag，而非盲用标签上限。
3. 事件返回：先判200 fs pre/post是否缺失；完整时以first_return_frame为空、等于事件end、大于end分别计有限未返、末端已在前区、较晚返回。Mo按显式later_return_status交叉核对。
4. 控制：以同Na所有事件±10保存帧的闭禁区核查完整控制区间，边界接触也排除；复用按Na和起止帧键计数。
5. 环境：MgMo逐元素/逐窗直接平均CN、初始ID保留与固定半径列；数组一致性和距离截断校验覆盖100,000行。事件/控制ID变化用相位两端短壳ID集合是否相同，不把CN相同视为身份相同。
6. 共享接触：同帧同配体ID，平移T=n_i−n_j，按中心对及T去重；由连通分量的整数回路向量计算秩再取最大。无坐标生成，无凸包几何重算，无能垒，未据此重建Na真实路径。
7. Mo相位：用上传坐标计算事件end−start向量；pre均值用start−10..start−1，post停留中心用end..end+9；环境相位表仍保持其原end+1..end+10约定。106向量、104中心、635相位汇总均复核一致。
8. Mo访问：按reference_mode_radius重计n_samples、外国参考球标记及duration≥0.2 ps；duration采用(last−first)×0.02 ps，单帧为0；六设置各54,000样本，不将段或帧当独立重复。
9. 形式电荷和理想层面电阻均为显式假设下的代数，不是新DFT、电化学测量或器件模拟。所有新计算局限见正文及RESULT_META。

## 附录C：公开一手来源，与本包观察分开

E1. He, X.; Zhu, Y.; Epstein, A.; Mo, Y. *Statistical variances of diffusional properties from ab initio molecular dynamics simulations*. npj Computational Materials 4, 18 (2018). DOI: https://doi.org/10.1038/s41524-018-0074-y 。本次可核到发表信息与摘要；用于说明短时、小体系AIMD扩散统计可能不足，不据文献为本材生成误差条或电导。

E2. Smith, J. G.; Siegel, D. J. *Low-temperature paddlewheel effect in glassy solid electrolytes*. Nature Communications 11, 1483 (2020). DOI: https://doi.org/10.1038/s41467-020-15245-5 。该原始研究在特定锂硫磷玻璃中分析空间、时间、振动和能量相关性；其结论不直接适用于本Na–Mo体系。

E3. Jun, K. et al. *The nonexistence of a paddlewheel effect in superionic conductors*. PNAS 121, e2316493121 (2024). DOI: https://doi.org/10.1073/pnas.2316493121 ；开放全文 https://pmc.ncbi.nlm.nih.gov/articles/PMC11067015/ 。该研究区分大角转动与局部倾斜，并强调逐事件时空关联。E2/E3在体系和机制定义上有差别；此处不宣称普遍否定或普遍确认paddlewheel，只强调不能从平均转角直接给本材因果结论。

E4. CDC/NIOSH, *Molybdenum (soluble compounds, as Mo)*：https://www.cdc.gov/niosh/npg/npgd0434.html 。仅用作具体化合物暴露资料的入口，不将本材等同可溶Mo化合物。

E5. CDC/NIOSH, *Hydrogen Fluoride/Hydrofluoric Acid: Systemic Agent*：https://www.cdc.gov/niosh/ershdb/emergencyresponsecard_29750030.html 。用于提示实际含氟前驱体和分解物的风险核查，不断言本材必生成HF。

公开来源仅补充方法和风险边界；本材运动、结构数字来自已上传附件。本报告不将网页资料替代未上传的私人项目数据，也不因成功归档将UNVERIFIED升级为accepted。
