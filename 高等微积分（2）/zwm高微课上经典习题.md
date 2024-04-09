级数部分
## 1.（知识点：Taylor展开）
$$\begin{aligned}&\text{判断级数 }\sum_{n=1}^\infty\left(\frac1n-\ln\left(1+\frac1n\right)\right)\text{ 的敛散性}\end{aligned}$$
首先，由带Peano 余项的Taylor 展开，
$$
\begin{aligned}\ln(1+x)&=x-\frac{x^2}2+o(x^2),&x\to0.\end{aligned}
$$
所以当$n\rightarrow +\infty$时：
$$\begin{aligned}&\frac{1}{n}-\ln\left(1+\frac{1}{n}\right)~=~\frac{1}{n}-\left(\frac{1}{n}-\frac{1}{2n^2}+o(\frac{1}{n^2})\right)\\& =\frac{1}{2n^2}-o(\frac{1}{n^2})=\begin{aligned}=&~\frac{1}{2n^2}\big(1+o(1)\big).\end{aligned} \end{aligned}$$
因此我们可以得到一个公式：$$\color{red}{\frac1n-\ln\left(1+\frac1n\right)=\frac1{2n^2}(1+o(1))}.$$
而级数$\Sigma \frac{1}{2n^2}$是收敛的，所以原级数收敛

## 2.（两次Taylor展开）
$$\text{判断级数 }\sum_{n=1}^\infty\left(e-\left(1+\frac1n\right)^n\right)^2\text{ 的敛散性}.$$
第一次展开：
证明：$$\Box:=\lim_{n\to+\infty}\frac{1-e^{n\ln(1+\frac1n)-1}}{1-n\ln(1+\frac1n)}=1.$$
（上面的证明本质上可以看做$e^x-1\sim x\quad (x\rightarrow 0^+)$这个近似的应用，不过在证明时构造上面这个极限证明要更有说服力一些）
第二次展开：
和上面一样，用到$ln(1+x)=x+-\frac{1}{2}x^2+o(x^2),x\rightarrow 0$ 这个展开
所以得到$$\begin{aligned}
\text{当}& \begin{aligned}n\to\infty&\text{ 时,我们有}\end{aligned}  \\
&\begin{aligned}e-\left(1+\frac1n\right)^n&=e-e^{n\ln(1+\frac1n)}=e\Big(1-e^{n\ln(1+\frac1n)-1}\Big)\end{aligned} \\
&\sim e\Big(1-n\ln(1+\frac1n)\Big)=en\Big(\frac1n-\ln(1+\frac1n)\Big) \\
&\sim en\Big(\frac1{2n^2}\Big)=\frac e{2n},
\end{aligned}$$
于是原通项在n足够大时满足$\frac{u_n}{\frac{e^2}{4n^2}}=1$,所以收敛
PS：需要回顾一下等价无穷小和Taylor展开了

## 3.（分类讨论、Cauchy积分判别法-级数敛散转换为广义积分敛散、L'Hospital法则）
$$\text{设 }p,q\in\mathbb{R}.\text{ 判断 }\sum_{n=2}^\infty\frac1{n^p(\ln n)^q}\text{ 的敛散性}.$$
I：当p＞1时令$$v_n=\frac1{n^{\frac12(1+p)}},则有\lim_{n\to\infty}\frac{u_n}{v_n}=\lim_{n\to\infty}\frac1{n^{\frac12(p-1)}(\ln n)^q} =0$$
这是因为无论q是正是负，$n^{\frac{1}{2}p-1}$增长速度都远超$(lnn)^q$  （可以使用洛必达法则证明，不过要先转化为连续函数才能用洛必达）
II：当p＜1时
$$\begin{aligned} & 令v_{n}=\frac{1}{n^{\frac{1}{2}(1+p)}}则 \lim_{n\to\infty}\frac{u_n}{v_n} =\lim_{n\to\infty}\frac{n^{\frac{1}{2}(1-p)}}{(\ln n)^q}=+\infty,\end{aligned}$$
显然不收敛（因为$v_n$对应级数都不收敛（$\frac{1}{2}(1+p)<1$））
III：p=1时级数$\sum_\limits{n=2}^\infty u_n$与对应的广义积分同敛散 
$$\int_2^{+\infty}\frac{\mathrm{d}x}{x(\ln x)^q}\overset{t=\ln x}{\operatorname*{=}}\int_{\ln2}^{+\infty}\frac{\mathrm{d}t}{t^q}$$
所以q>1时原级数收敛，否则发散

## 4. （含三角函数，分类讨论，一般级数敛散判定，Leibniz判定法则）
$$假设\alpha,\beta \in R,判断敛散性:\sum\limits_{n=1}^\infty sin(\frac{n^2+\alpha n+\beta}{n}\pi)$$ ![[b4dce9d960a9581ee6a7400eb953823.jpg]]
Trick：如果能找到极限下通项不趋于零的情况先排除这种情况。

## 5. （Leibniz判别法、根值判别法、绝对收敛、分类讨论）
$$设x \in R,判断敛散性:\sum\limits_{n=1}^\infty (-1)^n \frac{x^n}{n}$$
![[79d580c44c69808ea098ebae2d59e59.jpg]]

## 6.（分子有理化、Taylor展开、比较判别法）
$$判断敛散性： \sum\limits_{n=1}^\infty (\frac{1}{\sqrt{n}}-\sqrt{ln\frac{n+1}{n}})$$
![[a2ea5892a04a8dfb98b97c6efbac948.jpg]]

## 7.（含三角函数、绝对收敛和条件收敛、分类讨论、比较判别法、Leibniz定理）
$$设\alpha \in R,判断敛散性：\sum\limits_{n=1}^\infty \frac{sin(\frac{n^2+1}{n}\pi)}{{(n^2+1)}^\alpha}$$
![[8e84807136b72fd25f6aeb685ab5728.jpg]]
PS：1. 这个将$sin(...+n\pi)$ 中的 $n\pi$ 提取出来变成$(-1)^n$ 非常常见的一种做法
2.对通项（尤其是正项通项）做估计是非常常用的一种做法，参照上面的$u_n \sim \frac{1}{n^{1+2\alpha}}$

## 8.（含三角函数、cos(n)的求和（和差化积）、绝对收敛和条件收敛、Dirichlet收敛准则）
$$问\sum\limits_{n=1}^\infty\frac{cos(n)}{n}\text{是条件收敛还是绝对收敛？}$$
![[微信图片_20240307203926.jpg]]PS：1.这个$cos(n)$求和的化简方式非常实用，是和差化积的体现
2.利用到了cos的有界性（绝对值小于1）所以可以放缩到平方

## 9.（绝对收敛和条件收敛、Leibniz判别法、比较判别法）
$$假设p \in R,而x \geqslant 0,判断级数\sum\limits_{n=1}^\infty \frac{(-1)^n}{(n+x)^p}\text{何时条件收敛？}$$
![[微信图片_20240307203916.jpg]]