# 黎曼猜想完整证明（穿越前必看！！）

bitKrush，2026 年 11 月 21 日发布。B 站标注“含 AI 生成内容”。[原视频](https://www.bilibili.com/video/BV1nHy8z1EGJ/)

**整理方法**　以本地音轨的离线识别稿为底本，保留全部 35 段。时间显示到百分之一秒，点区间可从起点所在的整秒回看。逐段整理口播，借画面字幕辨认同音词、公式和代码名。第一人称及“如果”等判断沿用讲者口吻，〔〕中的说明和下方的校注框为整理者所加。Alpöge 的说明可对照从重数到 Theta 提升的思路。Rubinstein 的第二版工作稿详述 ζ 函数的情形，并在第 I.12 节列出仍待写出的常规数学论证。[作者说明，第 1、3–4 页](https://alpo.ge/remark.pdf) · [Rubinstein 工作稿及版本说明](https://www.math.uwaterloo.ca/~mrubinst/alpoge_claude_grh/)

## 阅读地图

- [00:00](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=0)　素数阶梯、欧拉乘积与临界线。函数方程把左右两侧的零点配成对。
- [02:43](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=163)　把零点问题改写成实轴上的问题。为什么给素数幂的加权和一个上界就够了？
- [03:46](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=226)　Stepanov 怎样用“点数 × 重数 ≤ 次数”数点？到整数上，要给重数和次数各找一个替身。
- [05:07](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=307)　Theta 提升逐次积累整除性，Bost 斜率不等式给它封顶。
- [07:58](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=478)　五个环节如何衔接，坏素数带来什么误差，以及讲者怎样把结论接回 RH 与 GRH。

## 分段转录

[00:00.00–00:22.72](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=0)　167 年前，数学家黎曼留下了一道关于素数分布的终极谜题。今天，我们借助刚刚发布的 Lean 4 形式化代码库，梳理它的完整证明思路。表面上看，素数像随机撒在数轴上的孤岛，毫无规律可言。但把目光拉远，素数分布却被一条极其光滑的对数积分曲线紧紧贴合。

[00:22.72–00:42.24](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=22)　素数阶梯之所以与复变函数息息相关，全靠欧拉发现的乘积公式。左边对全体自然数求和，通过唯一分解定理，竟然精确等于右边对全体素数取的无穷乘积。黎曼把这个函数解析延拓到整个复平面，发现零点的位置正好编码了素数的振荡波。

[00:42.24–01:04.46](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=42)　黎曼猜想断言，所有这些非平凡零点的实部都严格等于 $1/2$。2026 年底，莱文特·阿尔珀格（Levent Alpöge）发布了用计算机辅助证明系统 Lean 4 编写的证明仓库。整个仓库包含超过 17.5 万个文件，不依赖任何未证明的外部公理。入口文件 `Main.lean` 直接导出了 Mathlib 标准的黎曼猜想定理。

[01:04.46–01:27.06](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=64)　不需要数论专家背景，我们把它拆成五道彼此咬合的逻辑关卡来理解。第一步，先从复平面左右对称出发，把问题归约为消灭右半平面的零点。最后跨过迭代 Theta 提升、斜率不等式与弱化 Vandiver 条件，完成闭环。先看一个关键简化，为什么只需消灭临界带的右半边？

[01:27.06–01:43.66](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=87)　一百多年前，数学家已经知道，实部大于等于 1 的右侧区域没有零点。负偶数位置只是平凡零点，因此悬念全集中在 0 到 1 之间的临界带内。把函数乘上伽马因子后，它满足一个关于 $1/2$ 严格对称的函数方程。

[01:43.66–01:58.86](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=103)　假设左侧存在零点 $s_0$，那么镜像点 $1-s_0$ 也必然是右侧的零点。只要证明右半平面一个零点都没有，左边的镜像零点自然也不存在。这在 Lean 源码 `CritLine.lean` 中只用了短短十余行便形式化证毕。

[01:58.86–02:21.28](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=118)　更棒的是，这套新证明并非只针对单一的黎曼 ζ 函数。它把整数按余数周期性加权，一口气攻克了所有狄利克雷 $L$ 函数。这里的权函数 $\chi(n)$ 叫做狄利克雷特征。比如模 4 时，按正一、零、负一循环。取最平凡的模 1 特征 $\chi\equiv1$，$L$ 函数就立刻退化回原来的黎曼 ζ 函数。

[02:21.28–02:43.58](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=141)　最后，任何一个周期为 $N$ 的特征，都可以剥去多余因子，化为最精简的本原特征。在实部大于 $1/2$ 时，每个多余欧拉因子的模长都严格小于 1，永远不会为零。于是整个 RH 与 GRH 就等价于消灭所有本原特征在右半平面的零点。第二步，我们要把复平面上的零点问题——

> 校注　模 4 的非主特征从 $n=1$ 起的一个完整周期是 $1,0,-1,0$。此段口播说“因子的模长小于 1”，画面公式给出的是 $|\chi_{\rm prim}(p)p^{-s}|<1$，由此推出整个因子 $1-\chi_{\rm prim}(p)p^{-s}\ne0$。

[02:43.58–02:59.06](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=163)　转化成实数轴上的不等式。解析数论把素数分布打包成一把脉冲函数，叫做冯·曼戈尔特函数 $\Lambda(n)$。它只在素数和素数的幂次位置长出尖峰，把乘法性质变成加法计数。针对每个本原特征 $\psi$，

[02:59.06–03:13.18](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=179)　作者在它生成的循环群上构造了加权误差和 $G_m(y)$。这里 $G_\zeta(y)$ 减去了主趋势 $y\log y$，测量的是素数真实分布偏离平均趋势的涨落。其中的线性截断核，$y$ 除以 $n$ 减 1〔画面取正部，即 $\max(y/n-1,0)$〕，

[03:13.18–03:28.10](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=193)　能保证后面做积分时绝对收敛且非负。现在来看朗道正性定理的威力。为什么只需要单侧上界就够了？如果右半平面藏着复零点 $\rho$，显式公式就会生成振幅为 $y^\beta$ 的振荡波〔$\beta$ 是 $\rho$ 的实部〕。

[03:28.10–03:46.84](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=208)　由于余弦项不断反转符号，波峰一定会一次次冲破黄色的 $y^\theta$ 天花板。那万一零点刚好落在实轴上，从不振荡呢？这时换用 Mellin 积分的正性即可排除。于是只要对任意大于 $1/2$ 的 $\theta$，把 $G_m(y)$ 压在 $y^\theta$ 以下，

[03:46.84–04:04.00](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=226)　令 $\theta$ 逼近 $1/2$，所有本原特征在右半平面的零点就全部被消灭了。问题变成，到底用什么办法才能压住加权素数和 $G_m(y)$ 的上界？灵感来自 1969 年斯捷潘诺夫（Stepanov）证明有限域上黎曼猜想的方法。

> 校注　对 ζ 函数，Rubinstein 写出的误差还含线性修正项，$G(y)=\sum_{n\le y}\Lambda(n)(y/n-1)-y\log y+(1+\gamma)y$。画面上的 $G_m(y)$ 还加上非平凡特征所对应的加权项。图里要排除的是 $\beta>\theta$ 的零点。讲稿用 $y^\theta-G(y)$ 在充分大处的非负性应用朗道定理。[Rubinstein，第 I.1 节](https://www.math.uwaterloo.ca/~mrubinst/alpoge_claude_grh/zeta-paper_v2.pdf#page=5)

[04:04.00–04:26.58](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=244)　方法出奇简单。先利用基础线性代数，寻找一个不恒为零的辅助多项式 $P(X)$。只要未知系数的个数 $D+1$ 严格大于零点方程的个数 $N\times M$，齐次方程必有非零解。要求它在每一个我们想统计的有理点处，都与坐标轴高阶相切，具备重数 $M$。因为非零多项式的零点总重数不能超过次数 $D$，

[04:26.58–04:45.64](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=266)　于是点数 $N$ 自动被压低了。但想把 Stepanov 方法搬回真实的整数和素数世界，会立刻撞上两堵高墙。第一，整数上没有微积分意义下的导数，无法在素数处定义这样的零点重数。第二，整数上的数论构造也没有简单的多项式次数 $D$ 作为天花板。

[04:45.64–05:07.98](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=285)　莱文特·阿尔珀格这份证明最核心的突破，就是为这两堵高墙找到了精准翻译。他用迭代 Theta 提升替代零点重数，对长度为 $X$ 的和约提升 $\sqrt X$ 次。又用 Arakelov 几何中的 Bost 斜率不等式，替代多项式次数给出的上界。接下来两章，我们分别拆解这两件现代数论重武器到底是如何工作的。

[05:07.98–05:25.90](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=307)　要想在整数世界里制造高重数，证明的起点竟然是大家熟悉的高斯函数。把高斯函数在所有整数格点上采样求和，就得到了经典的 Theta 函数。它最神奇的天赋，是能够像桥梁一样，把对称性与整数格的算术信息连起来。

[05:25.90–05:44.90](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=325)　把一维高斯函数推广到双空间，我们就得到自守理论中的 Theta 积分核。这里的自守波 $f(g)$，你可以直观理解为对称曲面空间上的高维驻波。Theta 核就像一台精密转换器，把小空间的驻波无损地提升到高维空间。一次提升只能提供一点点局部约束。

[05:44.90–06:05.78](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=344)　于是作者把提升过程首尾相连，反复迭代。对长度为 $X$ 的素数和，大约迭代 $\sqrt X$ 次，每次都在目标素数处叠上一层整除增益。在代码库最底层，酉群 Theta 提升（画面标作 `TLiftK`）直接驱动了核心定理 `Row0b`。所谓 CM 域，就像加上虚数单位的数域 $\mathbb Q(i)$，

[06:05.78–06:24.36](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=365)　自带自然的复共轭对称。`Row0b` 把对称空间里的驻波翻译成控制素数分裂规律的伽罗瓦表示。有了迭代 Theta 提升造出的“重数”，下一步我们需要“多项式次数”的替代品。现在来看替代多项式次数的几何武器。

> 校注　片中画出了从 `TLiftK` 到 `Row0b` 的箭头。Rubinstein 核到了 `Row0b` 的陈述及其在 `VWin` 论证中的位置。讲者所说两者间的直接依赖关系未能独立核实。[Rubinstein，第 III.9 节](https://www.math.uwaterloo.ca/~mrubinst/alpoge_claude_grh/zeta-paper_v2.pdf#page=157)

[06:24.36–06:40.92](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=384)　理解 Arakelov 几何最直观的画面，就是平面上整齐排列的整数格。格点张出的基本平行四边形的面积叫做余体积。余体积越小，格点越密集。关键桥梁来了。在数论里，如果一组数被某个素数高次整除，

[06:40.92–06:58.48](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=400)　几何上就意味着它们掉进了极其稀疏的子格里，基本体积被迫成倍放大。对一个高维整数格，按子格最陡的斜率依次排列，就画出 Harder–Narasimhan 凸折线。第一段最陡的斜率叫最大斜率 $\mu_{\max}$，最后一段叫最小斜率 $\mu_{\min}$。

[06:58.48–07:19.50](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=418)　现在请出核心武器，Arakelov 几何中著名的 Bost 斜率不等式。至于诱导映射的贝塞尔周期，就像高维傅里叶系数，负责测量波的共振大小。`BesselId` 保证了这些周期是有理数，从而让我们能精确追踪整数格的缩放。当有理化的贝塞尔周期把格映射到另一端时，

> 校注　讲者说“有理数”。Rubinstein 在第 III.8 节用系数域 $L$ 表述这一步，代数配对经指定的嵌入 $L\hookrightarrow\mathbb C$ 与复配对相合。[Rubinstein，第 III.8 节的命题 (P)](https://www.math.uwaterloo.ca/~mrubinst/alpoge_claude_grh/zeta-paper_v2.pdf#page=139)

[07:19.50–07:40.20](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=439)　Bost 不等式锁死了输出斜率的上限。两边一夹逼，迭代提升叠出的素数整除性地板，绝不能突破斜率高度天花板。这正是 Stepanov 方法中“点数乘重数不超过次数”的数域翻版。到这里，你可能想问一个极其尖锐的问题，万一构造出的东西不小心退化为零怎么办？

[07:40.20–07:58.90](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=460)　如果算子彻底坍缩为零，当然也有“无穷高重数”，但那只是一场无意义的作弊。为了堵死退化漏洞，Lean 中的 `LinkS` 链条专门检验所有构造截面的内积矩阵。当尺度 $x$ 足够大时，非对角线干扰项指数级衰减，矩阵几乎等于单位矩阵。

[07:58.90–08:15.02](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=478)　一个接近单位矩阵的系统，绝对不可能坍缩为零，从而保证了非零构造的刚性。在 `GlobalTheoremInputs.lean` 中，一共有五大链条环环相扣。`LinkG` 把素数和化为整除增益，`LinkDIV` 用 Bost 斜率封顶。

[08:15.02–08:34.52](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=495)　刚刚见过的 `LinkS` 为整座结构担保，它绝不退化为零。再配合第四个环节 `LinkIRR`，用有限一般线性群上的 Green 特征标压低不可约残差。前四环全部就位，整个证明只剩下最后一道棘手的障碍，第五个环节 `LinkN`。坏素数上的误差公式里，

[08:34.52–08:51.06](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=514)　冒出了一个来自代数数论深处的红灯项，`vvTerm` 求和。第五步来到最后的拦路虎。为什么分歧误差公式里会出现 Sha 群？`LinkN` 公式右端的红灯项，正是代数数论中著名的障碍群，Sha 群。形象地说，

[08:51.06–09:10.06](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=531)　在每一个素数局域里，拼接都很完美，可绕一圈却首尾错开。如果这种错位障碍太大，就会淹没前面千辛万苦攒出的斜率收益。传统的范迪韦尔（Vandiver）猜想苛刻地要求这种错位障碍严格等于零，至今无人能证。但作者发现了一个绕行策略。

[09:10.06–09:30.78](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=550)　把严格为零换成“弱化 Vandiver 条件”。在特殊分圆子域 $E$ 上，只要 Sha 群的加权长度和不超过“指数根号尺度”就够了。作者特意用 2 的高次幂单位根和特殊同余素数对 $(q,d)$ 拼接出这个子域 $E$。这样一来，目标特征在子域上分裂得极其规整，后续大杀器就能顺畅发力。

[09:30.78–09:46.04](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=570)　这看似不可思议的定量上界，正是通过前面埋下的 `Row0b` 源头打通的。首先通过 Poitou–Tate 对偶与 Selmer 群，把 Sha 群与自守信息挂钩。再配合 Taylor–Wiles 自守提升与加藤（Kato）欧拉系统，最终一举拿下 `VWin`。

> 校注　“错位等于零”是视频的比喻。经典 Vandiver 猜想说，奇素数 $\ell$ 不整除第 $\ell$ 个分圆域最大实子域的类数。此处实际要控制的是一族伽罗瓦上同调群的加权长度和，界为 $\sqrt b$，其中 $b=\exp(x^\varepsilon)$。[Alpöge，第 4 页第 17 项](https://alpo.ge/remark.pdf#page=4) · [Rubinstein，第 III.9 节](https://www.math.uwaterloo.ca/~mrubinst/alpoge_claude_grh/zeta-paper_v2.pdf#page=151)

[09:46.04–10:04.10](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=586)　现在，让我们把整座跨越数域、自守形式与几何的宏大建筑一口气贯通。最底层由酉群 Theta 提升 `TLiftK` 与伽罗瓦表示源头 `Row0b` 稳稳托起。中间依靠弱化 Vandiver 条件与零外部公理的基础定理库，驱动五大链条咬合。

[10:04.10–10:19.22](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=604)　五大链条共同压出 $G_m(y)$ 的单侧上界，由朗道正性清零右半平面的所有零点。最后补回有限欧拉因子，并借助对称函数方程，正式导出黎曼猜想与 GRH。17 万多份 Lean 4 文件逐级扣合，

[10:19.22–10:36.16](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=619)　在 `Main.lean` 汇成两行导出定理。如果这份形式化证明通过数学界最终编译核验，无数条件定理将自动成真。素数计数达到理论最优精度，素性测试变确定算法，西格尔零点也会彻底消失。同时也要保持清醒。

> 校注　总结图把结论写成 RH 和狄利克雷 GRH 两项。“素性测试”在口播中未指明具体算法。Rubinstein 的核验记录列出入口文件中的五条定理，并确认其只依赖 Lean 的三条标准公理。[入口定理与公理核验记录](https://mrubinst.github.io/grh-lean-verification/)

[10:36.16–10:56.34](https://www.bilibili.com/video/BV1nHy8z1EGJ/?t=636)　它不会直接攻破 RSA 密码，也不能自动推出孪生素数。从一维数轴上的素数孤岛，到高斯核、整数格斜率，再到自动形式化检验，这条横跨数域与几何的证明之路，正展现了现代数学跨越门类、浑然一体的深邃之美。谢谢观看，下个故事再见。
