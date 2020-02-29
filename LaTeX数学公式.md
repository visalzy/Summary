# 数学公式

数学模式ctrl+m
$E=mc^2$
### 上下标

Einstein 's $E=mc^2$.

\[ E=mc^2. \]


---
### 根式与分式
根式使用 \sqrt{'}
分式使用 \frac{'}{'} 第一个参数为分子，第二个参数为分母
可以发现，在行间公式和行内公式中，分式的输出效果是有差异的。
如果要强制行内模式的分式显示为行间模式的大小，可以使用 \dfrac, 反之可以使用 \tfrac。
> \dfrac   $\dfrac{1}{2}$
> \tfrac   $\tfrac{1}{2}$


$\sqrt{x}$, $\frac{1}{2}$.

这个是好像是让符号放中间的东西
\[ \] 把要显示的公式，放到这个东西中间，就行了
>\[ \sqrt{x}, \]
>\[ \frac{1}{2}. \]
---

### 运算符

\[ \pm\; \times \; \div\; \cdot\; \cap\; \cup\;
\geq\; \leq\; \neq\; \approx \; \equiv \]
 显示单个字符

> 加减 $\pm$
> 乘法号 $\times$
> 除法号 $\div$
> 点乘 $\cdot$
> 交 $\cap$
> 并 $\cup$
> 大于等于$\geq$
> 小于等于$\leq$
> 不等于$\neq$
> 约等于$\approx$
> 不知道是啥了$\equiv$
> 连加 $\sum$
> 连乘 $\prod$
> 极限 $\lim$
> 积分 $\int$
> 多重积分 $\iint$ $\iiint\quad $
> 
----
### 定界符
各种括号用 (), [], \{\}, \langle\rangle 等命令表示；
注意花括号通常用来输入命令和环境的参数，所以在数学公式中它们前面要加 \。
因为 LaTeX 中 | 和 \| 的应用过于随意，amsmath 宏包推荐用 \lvert\rvert 和 \lVert\rVert 取而代之。
> 括号 $\langle\rangle$

**为了调整这些定界符的大小，amsmath 宏包推荐使用 \big, \Big, \bigg, \Bigg 等一系列命令放在上述括号前面调整大小**
> \[ \Biggl(\biggl(\Bigl(\bigl((x)\bigr)\Bigr)\biggr)\Biggr) \]
> \[ \Biggl[\biggl[\Bigl[\bigl[[x]\bigr]\Bigr]\biggr]\Biggr] \]
> 
---
### 省略号
省略号用 \dots, \cdots, \vdots, \ddots 等命令表示。
\dots 和 \cdots 的纵向位置不同，前者一般用于有下标的序列。
>省略号 \[ x_1,x_2,\dots ,x_n\quad 1,2,\cdots ,n\quad
\vdots\quad \ddots \]
---
### 矩阵
amsmath 的 pmatrix, bmatrix, Bmatrix, vmatrix, Vmatrix 等环境可以在矩阵两边加上各种分隔符。

>如果是pmatrix 圆括号
>\[ \begin{pmatrix} a&b\\c&d \end{pmatrix} \quad \]
>bmatrix 方括号
> \[\begin{bmatrix} a&b\\c&d \end{bmatrix} \quad\]
> Bmatrix 尖括号
> \[\begin{Bmatrix} a&b\\c&d \end{Bmatrix} \quad \]
> vmatrix 行列式应该
> 试用如何改变
> \[\begin{vmatrix} a&b\\c&d \end{vmatrix} \quad\]
> Vmatrix 双重行列式？？
> 更改了一下里面的内容
> \[\begin{Vmatrix} a&b&3&4 \end{Vmatrix} \]
> 
> 还可以生成小的
> smallmatrix
>-  $( \begin{smallmatrix} a&b\\c&d \end{smallmatrix} ) $.
>> a&b&c 只要有&就一直是一行
> 加入\\\\后，他才会换行
> 例如\[ \begin{pmatrix} a&b&1&2\\c&d\\1\\2 \end{pmatrix} \quad \]
---
### 多行公式
有的公式特别长，我们需要手动为他们换行；有几个公式是一组，我们需要将他们放在一起；还有些类似分段函数，我们需要给它加上一个左边的花括号。
#### 长公式
**不对齐**
无须对齐的长公式可以使用 multline 环境。(vscode markdown环境下似乎不能用)
 >   \begin{multline}
 >   x = a+b+c+{} \\
 >   d+e+f+g
 >   \end{multline}

**对齐**
需要对齐的公式，可以使用 aligned 次环境来实现，它必须包含在数学环境之内。
> \[\begin{aligned}
> x ={}& a+b+c+{} \\
> &d+e+f+g
> \end{aligned}\]
> 如何改变模式
> 如果在\\后面直接写公式
> 他会直接跳转到下一行 
$\begin{aligned}
    x={}&a+b+c+d+e\\1+2+3
\end{aligned}$
> 如果是在\\\\后面加个&,会在{}这个标记的地点开始下一段公式
$\begin{aligned}
    x=1+3{}&+4+5\\&+6+7    
\end{aligned}$

**公式组**
无需对齐的公式组可以使用 gather 环境，需要对齐的公式组可以使用 align 环境。他们都带有编号，如果不需要编号可以使用带星花的版本。
1. 对齐的公式组
$\begin{gathered}
a=b+c+d\\x=y+z  
\end{gathered}$
1. 通过&来控制对齐标杆
$\begin{aligned}
a &= b+c+d\\
x &= y+z    
\end{aligned}$

### 分段函数
分段函数可以用cases次环境来实现，它必须包含在数学环境之内。

$y=\begin{cases}
-x,\quad x\leq 0\\
x,\quad x>0    
\end{cases}$

----
### 一些数学公式案例

累加符号使用案例
- $\sum_{i=1}^n \quad$
- $\sum_{i_1}^2 \quad$
- $\prod_{i=1}^n$
在上下两边的的
- $ \sum\limits _{i=1}^n  $
- $ \prod\limits _{i=1}^n$
求极限 
\[ \lim_{x\to\cos(\pi)}x^2 \quad \]
\[ \int_a^b x^2 dx \]


\[ \lim\nolimits _{x\to0}x^2 \int\nolimits_a^b x^2 dx \]


$$
\begin{aligned} & \cos \omega(t+\mathrm{p}) * \cos 2 \omega(t+\mathrm{q}) \\=& \cos 3 \omega(t+\alpha)+\sin \omega(t+\mathrm{p}) * \sin 2 \omega(t+\mathrm{q}) \end{aligned}
$$

$\cos2\omega(t+\mathrm{q})$

LaTeX（TeX）中\mathrm{}的作用含义
使用 \mathrm{...} 可以将括号内的字母由数学斜体变为正体，即罗马体。

比如微分符号d、二项式系数C、等于号上的def、自然常数e、虚数单位i，一般打这些特殊符号的时候会将这些字母写在 \mathrm{...} 中，而不是直接打这个字母本身

比如不加 \mathrm 的 ABCDEFGabcdefg如下所示：ABCDEFGabcdefg

加了 \mathrm{ABCDEFGabcdefg} 如下所示：$\mathrm{ABCDEFGabcdefg}$

    $$
    x(t)=e^{j \omega t}=\cos (\omega t)+j \sin (\omega t)
    $$
    其中
    $j^2=-1$
    x(t)成为调谐信号