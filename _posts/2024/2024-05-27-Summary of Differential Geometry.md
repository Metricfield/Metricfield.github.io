---
title:      "Summary of Differential Geometry"
date:       2024-05-27
categories: [Mathematics, Topology]
tag: [Differential Geometry]
toc: True
math: True
description: This article records the content of differential geometry from the first five chapters of Professor Liang Canbin's 'Introduction to Differential Geometry and General Relativity, Volume I'.
---

## 前言

在这里,我将会*简明扼要*地摘录《微分几何入门与广义相对论》(上册)1-5章,微分几何相关的概念、定理以及公式等.为了更快地掌握(至少熟悉)微分几何的语言,我们不得不暂时先略去相关的数学证明,而这在书上以及[梁灿彬老师的现场教学](https://www.bilibili.com/video/BV1qF411t72r/?spm_id_from=333.337.search-card.all.click)上都有所涉及.

除正文以外,本文还有如下环境

> 这用来表示“建议”或者“提示”,通常与本文内容关系不大,仅仅起到提示的作用.
{: .prompt-tip }

> 这用来表示作者(即梁和周)的“注记”,是书里面提到过的,并且有助于深刻理解的内容.
{: .prompt-info }

> 这用来表示我的“注记”,是我(Metricfield)的理解,未必准确到位,读者自行参考.
{: .prompt-warning }

> 这用来表示“警告”,常常出现在某些易错、易混淆的内容后面.
{: .prompt-danger }

很遗憾,并非所有的公式在该环境下都完整渲染出来了.但好在我们有教材.
如果你连教材也没有,那问题其实也不会很大,因为我会不定期更新公式以期适配目前这个渲染环境.不过为了更好的学习效果,我还是建议你先看教材或是网课.

 <del>当然,没有时间看书或者看课,将本文用作半日速成微几的材料也未尝不可(笑.</del>

 下面是本文的维护信息:






好了,废话结束.接下来,让我们进入**微分几何**的学习旅途.😊


<hr>


## 第1章 拓扑空间简介

### 1.1 集论初步

> 这部分内容很早就学习过,印象深刻可以跳过.
{: .prompt-tip }

#### 集合

- 确切指定了的若干事物的全体称为**集合**(set).集合中每一个事物叫做一个**元素**(element)或者**点**(point).不含任何元素的集合叫做**空集**(empty set),记作 $ \emptyset $ .

- 表示集合的常用方法有**列举法**与**描述法**两种.

> 当然还有用[文氏图](https://zh.wikipedia.org/wiki/%E6%96%87%E6%B0%8F%E5%9B%BE)(Venn diagram)表示集合关系的,特点是直观,但不够严格.
{: .prompt-warning }

#### 子集
   
- 若 $ \forall x\in A $ 都有 $ x\in X $ ,称 $ A $ 是 $ X $ 的子集(subset),记作 $ A\subset X $ .
规定空集是任一集合的子集.若进一步 $ A\neq X $ ,称 $ A $ 是 $ X $ 的真子集(proper subset),记作 $ A \subsetneqq X $ .

- 若 $ A\subset X,X\subset A, $ 则 $ A=X $ ,称为集合相等.

#### 集合的运算
1. 并集(union): $$ A \cup B := \{ x  \mid  x \in  A \text{或} x \in B \}. $$ 
2. 交集(intersection): $$ A \cap B:= \{x  \mid  x \in A,x \in B \}. $$ 
3. 差集(difference): $$ A-B:= \{ x  \mid  x \in A,x \notin B \}. $$ 
4. 补集(complement):若 $$ A \subset X $$ ,则补集 $$ -A:=X-A. $$ 

> “A := B ”表示A被定义为B，参见[Mathematics Stack Exchange上的相关回答](https://math.stackexchange.com/questions/25214/what-does-mean).
{: .prompt-warning }


#### 集合满足的运算律

1. 交换律: $ A\cup B=B\cup A,A\cap B=B\cap A. $ 
2. 结合律: $ (A\cup B)\cup C=A\cup (B\cup C),(A\cap B)\cap C=A\cap (B\cap C) .$ 
3. 分配律: $ (A\cap B)\cup C=(A\cup C)\cap(B\cup C),(A\cup B)\cap C=(A\cap C)\cup(B\cap C) .$ 
4. De Morgen定律: $ A-(B\cup C)=(A-B)\cap (A-C),A-(B\cap C)=(A-B)\cup(A-C) $. 
  
#### 卡氏积

- 非空集合 $ X,Y $ 的**卡氏积**(Cartesian product) $ X\times Y $ 定义为 
$$ X\times Y:=\{(x,y) \mid x\in X,y\in Y\}. $$ 
   
- 有限个集合的卡氏积可以定义为: $$ X \times Y \times Z := \{(x,y,z) \mid  x \in X,y \in Y,z \in Z \}. $$ 

- 规定卡氏积满足结合律: $ (X\times Y)\times Z=X\times (Y\times Z). $ 

> 实际上卡氏积就是对集合内的多个元素按照一定顺序打包封装而已,并未对元素进行任何处理.
{: .prompt-warning }

- 定义$ \mathbb{R}^n:=\mathbb{R}\times \cdots\times\mathbb{R} $ 的任意两个元素 $ x=(x^1,\cdots,x^n),y=(y^1,\cdots,y^n) $ 之间的距离为 
 $$  \mid y-x \mid :=\sqrt{\sum\limits_{i=1}^n(y^i-x^i)^2}. $$ 

#### 映射
   
- 设集合 $ X,Y $ 非空.一个从 $ X $ 到 $ Y $ 的映射是一个法则,它给 $ X $ 的每一元素指定 $ Y $ 的唯一对应元素.若 $ y\in Y $ 是 $ x\in X $ 的对应元素,就写 $ y=f(x) $ ,并称 $ y $ 为 $ x $ 在映射 $ f $ 下的**像**(image),称 $ x $ 为**原像**或者逆像(inverse image). $ X $ 称为映射 $ f $ 的**定义域**(domain), $ X $ 的全体元素在映射 $ f $ 下的像的集合 $ f[x] $ 称为映射 $ f:X\to Y $ 的**值域**(range).

> - 映射的定义只要求 $ \forall x\in X,x\mapsto y\in Y $ 必须唯一,而无论到底是“一对一”还是“多对一”,也不论 $ Y $ 中是不是有元素剩余.于是可以继续对映射加以限制从而进一步分类.
> - 集合 $ Y $称为[Codomain](https://zh.wikipedia.org/wiki/%E5%88%B0%E8%BE%BE%E5%9F%9F),北京大学丘维生教授在国内首先将其译作“陪域”.显然, 
$f[x] \subset Y .$
{: .prompt-warning }

- 映射 $ f:X\to Y $ 和 $ f':X\to Y $ 称为相等的,若 $ \forall x\in X,f(x)=f'(x) .$ 

- 设 $ A \subset X, $ 则 $ A $ 的元素在 $ f $ 下的像组成的子集记作 $ f[A] $ ,即 
 $$ f[A] \equiv \{ y \in Y  \mid  \exists x \in A,y=f(x) \} \subset Y.$$ 

- 映射的分类
  - 映射 $ f:X\to Y $ 称为**一一的**(one-to-one),若 $ \forall y \in Y $ ,有不多于一个逆像,可以一个也没有. 
 
    - 若 $ f $ 为一一映射,则存在逆映射 $ f^{-1}: f[X] \to X $ .无论 $ f:X\to Y $ 是否有逆,都可以定义任一子集 $ B \subset Y $ 在 $ f $ 下的逆像 $ f^{-1}[B] $ 为: $$ f^{-1}[B]:=\{x\in X \mid f(x)\in B\}\subset X. $$ 这里的逆像是 $ X $ 的子集而非元素.
    - 映射 $ f:X\to Y $ 称为**到上的**(onto),若 $ \forall y \in Y $ ,都有逆像,可以多于一个. $
  -  f $ 为到上映射的充要条件是值域 $ f[X]=Y $ .
  - 既是一一映射,又是到上映射,则称为一一到上的映射.
  - $ f:X\to Y $ 称为常值映射,若 $ \forall x,x'\in X,f(x)=f(x') $ .
  - 设 $ X,Y,Z $ 为集合, $ f:X\to Y,g:Y\to Z $ 为映射,则 $ f $ 和 $ g $ 的复合映射 $ g\circ f $ 是从 $ X $ 到 $ Z $ 的映射,定义为 
  $$ (g \circ f)(x):=g(f(x))\in Z,\forall x \in X $$ .

> 一一映射亦即排除了“多对一”的映射,数学书称其为单射.而到上映射排除了$Y$中元素剩余的情况,数学书上则称为满射.一一到上的映射保证了“一个萝卜一个坑”,在数学上称为双射或者一一对应.
{: .prompt-warning }

#### 一元函数 $ f:\mathbb{R}\to \mathbb{R} $ 连续性的定义

- 微积分采用 $ \varepsilon-\delta $ 语言定义,即
  - 称 $ f $ 在 $ x $ 点连续,若 $ \forall \varepsilon > 0,\exists \delta >0 $ 使得当 $  \mid  x'-x \mid  <\delta $ 时有 $  \mid f(x')-f(x) \mid <\varepsilon $ .
  - 称 $ f $ 在 $ \mathbb{R} $ 上是连续的,若它在 $ \mathbb{R} $ 的任一点连续.

- 点集拓扑采用开子集定义,即

设 $ X=Y=\mathbb{R} $ ,映射 $ f:X\to Y $ 叫做连续的,若 $ Y $ 中任意开区间的“逆像”都是 $ X $ 的开区间之并或是空集. 

>为什么会存在连续的开子集定义?因为连续的概念如果按照微积分中的定义,不易于推广到拓扑领域.这体现了数学的精神,那就是从人们熟悉的某个概念、某个事物当中尽量抽象然后提取出本质、内在的东西,从而向外推广,研究这一概念在另一领域上的性质.
{: .prompt-warning }

#### 开子集
 
- 定义: $ \mathbb{R} $ 的任一可以表示为开区间之并的子集(连同空集)称为开子集.
- 开子集的本质性质有
1.  $ \mathbb{R} $ 和空集 $ \emptyset $ 都是开子集.
2. 有限个开子集之交仍是开子集.
3. 任意个开子集之并仍是开子集.

将上述性质推广到任意集合 $ X $ ,即可定义任意集合的开子集概念.定义了开子集的集合叫做拓扑空间.

---

### 1.2 拓扑空间

#### 拓扑、拓扑结构与拓扑空间

- 对任意非空集合 $ X $ 可用适当方式指定其中的某些子集是开的,其他为非开的,并且约定任何指定方式都要满足:
1.  $ X $ 本身和空集 $ \emptyset $ 为开子集.
2. 有限个开子集之交仍是开子集.
3. 任意个(可以是有限个也可以是无限个)开子集之并仍为开子集.

每种满足上述三要求的指定给集合 $ X $ 赋予了一种附加结构,称为**拓扑结构**.
  
> - 对定义了拓扑结构的集合的任一子集,其是否为开子集非“是”即“否”.
> - 注意条件2仅允许有限数目开集的交.如在实数轴 $ \mathbb{R} $ 上,无限多个以 $ b $ 点为中心的开集的交 $ \bigcap\limits_{n=1}^\infty B\left(b,\frac{1}{n}\right) $ 为 $ b $ 点自身,而点 $ b $ 不是 $ \mathbb{R} $ 中开集,仅为闭集.
{: .prompt-info }

> 为何单点集合 $ \{b\} $ 为闭集呢?有两种理解
> 1. 只需要说明补集 $ \mathbb{R}/\{b\} $ 是开集. $ \forall x\in \mathbb{R}/\{b\},\exists \varepsilon >0,s.t.(x-\varepsilon,x+\varepsilon) $   完全包含在 $ \mathbb{R}/\{b\} $ 内.
> 2. 按照闭集的定义,闭集包含它的所有极限点.对于单点集合 $ \{𝑏\} $ 
,唯一的点 $ 𝑏 $ 自然是它的极限点,没有其他点可以无限接近 $ b $ 而不等于 $ b $ .因此,单点集合 $ \{𝑏\} $ 是闭集.
{: .prompt-warning}

定义了拓扑结构的集合 $ X $ 的全体开子集组成一个集合,称为 $ X $ 的一个**拓扑**(topology),记作 $ \mathscr{T} $ .

- 拓扑用数学语言表述为:非空集合 $ X $ 的一个拓扑 $ \mathscr{T} $ 是 $ X $ 的若干子集的集合,满足:
1.  $ X,\emptyset \in \mathscr{T}. $ 
2. 若 $ O_i\in \mathscr{T},i=1,\cdots,n $ ,则 $ \bigcap\limits_{i=1}^n O_i\in \mathscr{T}. $ 
3. 若 $ \forall \alpha,O_\alpha \in \mathscr{T} $ ,则 $ \bigcup\limits_{\alpha}O_\alpha\in \mathscr{T}. $ 

指定了拓扑 $ \mathscr{T} $ 的集合 $ X $ 称为**拓扑空间**,拓扑空间的子集 $ O $ 称为开子集或者开集,若 $ O\in \mathscr{T} $ .

#### 常见拓扑
1. 设 $ X $ 为任意非空集合,令 $ \mathscr{T} $ 为 $ X $ 的全部子集的集合,则 $ \mathscr{T} $ 构成 $ X $ 的一个拓扑, 称为**离散拓扑**(discrete topology).
2. 设 $ X $ 为任意非空集合,令 $ \mathscr{T}=\{X,\emptyset\} $ ,则 $ \mathscr{T} $ 构成 $ X $ 的一个拓扑, 称为**凝聚拓扑**(indiscrete topology).
3. 设 $ X=\mathbb{R} $ ,则 $$ \mathscr{T}_u:=\{\text{空集或者}\mathbb{R}\text{中能够表示为开区间之并的子集}\} $$ 称为 $ \mathbb{R} $ 的**通常拓扑**.
设 $ X=\mathbb{R}^n $ ,则 $ \mathscr{T}_u:=\{\text{空集或者}\mathbb{R}^n\text{中能够表示为开球之并的子集}\} $ 称为 $ \mathbb{R}^n $ 的**通常拓扑**.
4. 设 $ (X_1,\mathscr{T}_1) $ 和 $ (X_2,\mathscr{T}_2) $ 为拓扑空间, $ X=X_1\times X_2 $ ,定义 $ X $ 的拓扑为 $$ \mathscr{T}:=\{O\subset X \mid O\text{可以表示为形如}O_1\times O_2\text{的子集之并},O_1 \in\mathscr{T}_1,O_2\in \mathscr{T}_2\} $$ 则 $ \mathscr{T} $ 称为 $ X $ 的**乘积拓扑**(product topology).
5. 设 $ (X,\mathscr{T}) $ 是拓扑空间, $ A $ 为 $ X $ 的任一非空子集.把 $ A $ 看成集合,指定拓扑 $ \mathscr{S} $ 为 
  $$ \mathscr{S}:=\{V\subset A \mid \exists\ O\in \mathscr{T}s.t.V=A\cap O\}, $$
这样定义的 $ \mathscr{S} $ 叫做 $ A\subset X $ 的、由 $ \mathscr{T} $ 导出的**诱导拓扑**(induced topology).  $ (A,\mathscr{S}) $ 称为 $ (X,\mathscr{T}) $ 的**拓扑子空间**(topological subspace).

>  - $ \mathbb{R}^n $ 的通常拓扑中,开球(open ball)定义为 $ B(x_0,r):=\{x\in \mathbb{R}^n \mid  \mid x-x_0 \mid <r\} $ , $ x_0 $ 称为球心, $ r>0 $ 称为半径.$ \mathbb{R}^2 $ 中的开球称为开圆盘, $ \mathbb{R} $ 中的开球就是开区间.
>
> <img src="/assets/img/in-post/2024/youdaotuopu.jpg" alt="诱导拓扑的一个简单例子" width="200" height="200">
> - 上图为诱导拓扑的一个典型例子,设 $$ A:=\{x\in\mathbb{R}^2 \mid   \mid x-x_0\mid =1\} $$ ,由于 $ A $ 仅仅是圆周无法表示为 $ \mathbb{R}^2 $ 中的开圆盘之并,所以 $ A $ 以 $ \mathbb{R}^2 $ 的 $ \mathscr{T}_u $ 衡量不是开的.然而按照上面定义的 $ \mathscr{S} $ , $ A $ 却是开的.
> - 显然,在拓扑中,离散拓扑的元素最多，而凝聚拓扑的元素最少.
{: .prompt-info }



#### 连续

- 设 $ (X,\mathscr{T}) $ 和 $ (Y,\mathscr{S}) $ 为拓扑空间,映射 $ f:X\to Y $ 称为**连续的**(continuous),若 $ f^{-1}[O]\in \mathscr{T},\forall O \in \mathscr{S}. $ 

- 设 $ (X,\mathscr{T}) $ 和 $ (Y,\mathscr{S}) $ 为拓扑空间,映射 $ f:X\to Y $ 称为在点 $ x\in X $ 处连续,若 $ \forall $ 满足 $ f(x)\in G' $ 的 $ G'\in \mathscr{S},\exists\ G\in \mathscr{T} $ 使得 $ x\in G $ 且 $ f[G]\subset G'. $  

- $ f:X\to Y $ 称为**连续**，若它在所有点 $ x=X $ 上连续.

#### 同胚

- 拓扑空间 $ (X,\mathscr{T}) $ 和 $ (Y,\mathscr{S}) $ 称为**互相同胚**(homeomorphic to each other),若存在映射 $ f:X\to Y $ 满足

1.  $ f $ 是一一到上的;
2.  $ f $ 和 $ f^{-1} $ 都连续.

这样的 $ f $ 称为从 $ (X,\mathscr{T}) $ 到 $ (Y,\mathscr{S}) $ 的**同胚映射**,简称**同胚**(homeomorphism).

- 普通函数的连续性与可微性可以用 $ C^r $ 表示, $ r $ 为非负整数:

1. $ C^0 $ 表示连续;
2. $ C^r $ 表示 $ r $ 阶导函数存在且连续;
3. $ C^\infty $ 表示任意阶导函数存在且连续,称为光滑.

- 任一开区间 $ (a,b)\subset\mathbb{R} $ 与 $ \mathbb{R} $ 同胚.
  
> 同胚映射 $ f:X\to Y $ 不仅在 $ X $ 和 $ Y $ 的点之间建立了一一对应关系,而且还在 $ X $ 的开子集与 $ Y $ 的开子集之间建立了一一对应关系.一切由拓扑决定的性质都可被 $ f $ 携带到 $ Y $ 中. 
{: .prompt-info }

#### 邻域、闭集、连通

- 集合 $ X $ 中一点 $ x $ 的**邻域**(neighborhood) $ N $ 是 $ X $ 的子集合,它含有点 $ x $ 所属的某开集 $ O $ ,即 $ \exists O \in \mathscr{T} $ 使得 $ x\in O\subset N $ .

> - 定义中并未要求 $ N $ 自身是开集,但是所有含 $ x $ 的开集都是 $ x $ 的邻域.自身为开集的邻域称为开邻域.
> - 在拓扑空间 $ [0,\infty)\subset \mathbb{R} $ 中 $ [0,1) $ 是0的开邻域, $ [0,1] $ 是0的邻域.
{: .prompt-info }

- 子集的邻域:
  - $ N\subset X $ 称为 $ A\subset X $ 的一个邻域,若 $ \exists \  O \in \mathscr{T} $ 使得 $ A\subset O\subset N $ .
  - $ A\subset X $ 是开集,当且仅当 $ \forall x\in A,A $ 是 $ x $ 的邻域.
  - $ C\subset X $ 叫做**闭集(closed set)**,若 $ -C\in \mathscr{T} $ .闭集具有如下性质:
    1. 任意两个闭集的交集是闭集;
    2. 有限个闭集的并集是闭集;
    3.  $ X $ 和 $ \emptyset $ 是闭集. 

- 设 $ O $ 是 $ X $ 的子集,点 $ x $ 的每个邻域若含有 $ O-\{x\} $ 中至少一点,则 $ x\in X $ 称为 $ O $ 的极限点或者聚点.

> - $ O $ 的极限点 $ x $ 不一定属于 $ O $ .
> - 闭集包含它的所有极限点(聚点).
{: .prompt-info }
- 拓扑空间 $ (X,\mathscr{T}) $ 称为**连通的(connected)**,若它除 $ X $ 和 $ \emptyset $ 以外没有既开又闭的子集. 

#### 闭包、内部和边界

 $ A $ 的**闭包(closure)** $ \bar{A} $ 是所有含 $ A $ 的闭集的交集,即 \$\$ \bar{A}:=\bigcap_{\alpha}C_\alpha,A\subset C_\alpha,\text{且}C_\alpha\text{为闭}. \$\$ 

> $ \bar{A} $ 是含 $ A $ 的最小闭集.

 $ A $ 的**内部(interior)** $ i(A) $ 是所有含于 $ A $ 的开集的并集,即 \$\$ i({A}):=\bigcup_{\alpha}O_\alpha,O_\alpha\subset A,O_\alpha \in \mathscr{T}. \$\$ 
或者集合 $ A $ 的内部 $ i(A) $ 是 $ A $ 的闭包 $ \bar{A} $ 的所有开子集的并集.

> $ i(A) $ 是 $ A $ 的最大开子集.

 $ A $ 的**边界(boundary)** $ \dot{A}:=\bar{A}-i(A),x\in \dot{A} $ 称为**边界点**, $ \dot{A} $ 也记作 $ \partial A $ ,
 
 $ \bar{A},i(A),\dot{A} $ 具有如下性质:
 
  1.  $ \bar{A} $ 为闭集;
  2.  $ A\subset \bar{A} $ ;
  3.  $ A=\bar{A} $ 当且仅当 $ A $ 为闭集;
  4.  $ i(A) $ 为开集;
  5.  $ i(A)\subset \bar{A} $ ;
  6.  $ i(A)=\bar{A} $ 当且仅当 $ A\in \mathscr{T} $ ;
  7.  $ \dot{A} $ 为闭集.

---

### 1.3 紧致性(选读)
 
#### 若干定义
 $ X $ 的开子集的集合 $ \{O_\alpha\} $ 叫做 $ A\subset X $ 的一个**开覆盖(open cover)**,若 $ A\subset\bigcup\limits_\alpha O_\alpha $ .也可以说 $ \{O_\alpha\} $ 覆盖 $ A $ .

设 $ \{O_\alpha\} $ 是 $ A\subset X $ 的开覆盖,若 $ \{O_\alpha\} $ 的有限个元素构成的子集 $ \{O_{\alpha_1},\cdots,O_{\alpha_n}\} $ 也覆盖 $ A $ ,就说 $ \{O_\alpha\} $ 有**有限子覆盖(finite subcover)**.

 $ A\subset X $ 叫做**紧致(compact)**的,若它的任一开覆盖都有有限子覆盖.

> 设 $ x\in X, $ 则单点集合 $ A\equiv\{x\} $ 必定紧致.\
>  $ \mathbb{R} $ 中任一开区间或者半开区间都非紧致.\
>  $ \mathbb{R} $ 的任一闭区间都紧致.

拓扑空间 $ (X,\mathscr{T}) $ 叫做 $ \mathbf{T}_2 $ 或者 **豪斯多夫空间(Hausdorff space)**,若 \$\$ \forall x,y\in X.x\neq y,\exists \ O_1,O_2\in \mathscr{T},s.t. x\in O_1,y\in O_2,O_1\cap O_2=\emptyset . \$\$ 
通俗来说就是, $ \mathbf{T}_2 $ 空间任两不同点有不相交的邻域.
豪斯多夫空间中的点都是闭子集.

 >常见的拓扑空间如 $ \mathbb{R}^n $ 为豪斯多夫空间,而凝聚拓扑空间为非豪斯多夫空间.

 $ A\subset\mathbb{R}^n $ 是**有界(bounded)**的,若 $ \exists $ 开球 $ B\subset \mathbb{R}^n s.t. A\subset B. $ 

#### 若干定理 
   
1. 若 $ (X,\mathscr{T}) $ 是 $ \mathbf{T}_2 $ 空间, $ A\subset X $ 为紧致,则 $ A $ 为闭集.
2. 若 $ (X,\mathscr{T}) $ 为紧致, $ A\subset X $ 为闭集,则 $ A $ 为紧致.
3.  $ A\subset \mathbb{R} $ 为紧致,当且仅当 $ A $ 为有界闭集.
4. 设 $ A\subset X $ 紧致, $ f:X\to Y $ 连续,则 $ f[A]\subset Y $ 紧致.

>在同胚映射下保持不变的性质称为拓扑性质或者拓扑不变性.同胚映射保持子集的紧致性,因此紧致性是拓扑性质.此外,连通性和 $ \mathbf{T}_2 $ 性都是拓扑性质.而有界性不是拓扑性质.
>
  >> 反例:开区间 $ (a,b) $ 同胚于 $ \mathbb{R} $ ,但前者有界后者无界.

- 设 $ X $ 紧致, $ f:X\to \mathbb{R} $ 连续,则 $ f[X]\subset\mathbb{R} $ 有界且取得其最大值与最小值.

5. 设 $ (X_1,\mathscr{T}_1) $ 和 $ (X_2,\mathscr{T}_2) $ 紧致,则 $ (X_1\times X_2,\mathscr{T}) $ 紧致,其中 $ \mathscr{T} $ 为 $ \mathscr{T}_1 $ 与 $ \mathscr{T}_2 $ 的乘积拓扑.

6.  $ A\subset \mathbb{R}^n $ 紧致当且仅当它是有界闭集.

#### 极限与序列

映射 $ S:\mathbb{N}\to X $ 叫做 $ X $ 中的**序列(sequence)**.

> 通常把序列记作 $ \{x_n\} $ ,其中 $ x_n\equiv S(n)\in X,n \in \mathbb{N}.\{x_n\} $ 其实就是 $ X $ 中编了次序的一串点.

 $ x\in X $ 叫做序列 $ \{x_n\} $ **的极限(limit)**,若对 $ x $ 的任一开邻域 $ O $ 存在 $ N\in \mathbb{N} $ 使得 $ x_n\in O,\forall n>N. $ 若 $ x $ 是 $ \{x_n\} $ 的极限,称 $ \{x_n\} $ 收敛于 $ x $ .
 
 $ x\in X $ 叫做序列 $ \{x_n\} $ 的**聚点(accumulation point)**,若 $ x $ 的任一开邻域都含有 $ \{x_n\} $ 的无限多点.

  $ x $ 为 $ \{x_n\} $ 的极限 $ \Rightarrow x $ 为 $ \{x_n\} $ 的聚点.反之不一定成立.

 元素个数有限的集合称为**有限集**,否则称为**无限集**.

 有限集一定可以将其元素编号一个个数,故有限集一定为**可数集(countable set)**.但无限集不一定就不可数.

 拓扑空间 $ (X,\mathscr{T}) $ 称为**第二可数(second countable)**的,若 $ \mathscr{T} $ 存在可数子集 $ \{O_1,\cdot,O_K\}\subset \mathscr{T} $ 或者 $ \{O_1,\cdots\}\subset \mathscr{T} $ 使得任一 $ O\in\mathscr{T} $ 可以被表示为 $ \{O_1,\cdots,O_K\} $ 或 $ \{O_1,\cdots\} $ 的元素之并.

若 $ A\subset X $ 紧致,则 $ A $ 中任一序列都有在 $ A $ 内的聚点.反之,若 $ X $ 为第二可数且 $ A\subset X $ 中任一序列都有在 $ A $ 内的聚点,则 $ A $ 紧致. 

#### Cauchy 系列与完备性

在度量空间 $ (S，\rho) $ 中的 $ Cauchy $ 序列是指存在这样一个无限多点系列 $ \{x,n=1,2,\cdots,\infty\} $ 满足条件: \$\$ \lim\limits_{n,m\to 0}d(x_m,x_n)=0 \$\$ 通俗来说就是对于预先给定的一个小正数 $ \varepsilon >0 $ ,总存在足够大的整数 $ N $ ,当 $ n,m>N $ 时,相应两点 $ x_n,x_m $ 距离 $ d(x_m,x_n)<\varepsilon $ .

度量空间 $ (S，\rho) $ 中若每个 $ Cauchy $ 序列都在空间 $ S $ 上具有收敛点,则称其为完备的.

>完备性不是拓扑性质.

 $ Frechet $ 空间:完备的可度规空间;

 $ Banach $ 空间:完备具模向量空间;

 $ Hilbert $ 空间:完备具内积空间.

---

## 第2章 流形和张量场
### 2.1 微分流形
  
拓扑空间 $ (M,\mathscr{T}) $ 称为** $ n $ 维微分流形(n-dimensional differentiable)**,简称 $ n $ 维流形,若 $ M $ 有开覆盖 $ \{O_\alpha\} $ ,即 $ M=\bigcup\limits_\alpha O_\alpha $ ,满足:

1.  $ \forall O_\alpha,\exists $ 同胚 $ \psi_\alpha:O_\alpha \to V_\alpha $ ,其中 $ V_\alpha $ 是 $ \mathbb{R}^n $ 用通常拓扑衡量的开子集;
2. (相容性条件):若 $ O_\alpha\cap O_\beta\neq \emptyset, $ 则复合映射 $ \psi_\beta\circ \psi_\alpha^{-1} $ 是光滑的.
 
>  $ \psi_\beta\circ\psi_\alpha^{-1} $ 提供了 $ n $ 个 $ n $ 元函数,这每一个 $ n $ 元函数都是光滑的.

作为流形, $ M $ 中的元素本没有坐标,但是位于 $ O_\alpha $ 内的元素(点)通过 $ \psi_\alpha $ 获得坐标,称 $ (O_\alpha,\psi_\alpha) $ 为一个**局域坐标系(coordinate system)**,其**坐标域(coordinate patch)**为 $ O_\alpha $ .
  
>坐标系 $ (O_\alpha,\psi_\alpha) $ 在数学上叫做**图(chart)**,满足条件1、2的全体图的集合 $ \{(O_\alpha,\psi_\alpha)\} $ 叫做**图册(atlas)**.
 
 设 $ M=(\mathbb{R}^2,\mathscr{T}_u) $ ,选定 $ O_1=\mathbb{R}^2,\psi_1 $ 为恒等映射,则 $ \{(O_1,\psi_1)\} $ 为只含一个图的图册,故 $ \mathbb{R}^2 $ 为2维流形,且只能用一个坐标域覆盖的流形,称为**平凡(trivial)流形**.

#### 微分同胚、标量场 

 $ f:M\to M^\prime $ 称为** $ C^r $ 类映射**,若 $ \forall p\in M $ ,映射 $ \psi_\beta^\prime \circ f\circ \psi_\alpha^{-1} $ 对应的 $ n^\prime $ 个 $ n $ 元函数都是 $ C^r $ 类.

微分流形 $ M,M^\prime $ 称为**互相微分同胚**(diffeomorphic to each other),若 $ \exists f:M\to M ^ \prime $ ,满足

1.  $ f $ 是一一到上的;
2.  $ f $ 和 $ f^{-1} $ 是 $ C^\infty $ 的.

这样的 $ f $ 称为从 $ M $ 到 $ M^\prime $ 的**微分同胚映射**,简称**微分同胚**(diffeomorphism).

> 微分同胚是对流形之间的映射可以提出的最高要求,互相微分同胚的流形可以视为相等.\
> 只有维数相等的流形才能微分同胚.


 $ f:M\to \mathbb{R} $ 称为 $ M $ 上的函数或 $ M $ 上的**标量场**(scalar field on M).

若 $ f $ 为 $ C^\infty $ 的,则称为** $ M $ 上的光滑函数**. $ M $ 上的全体光滑函数的集合记作 $ \mathscr{F}_M $ . 

>函数 $ f:M\to\mathbb{R} $ 与坐标系 $ (O,\psi) $ 结合可以得到一个 $ n $ 元函数 $ F(x^1,\cdots,x^n). $ 因为 $ n $ 个坐标决定 $ O $ 中唯一的点 $ p $ ,而由 $ f:M\to\mathbb{R} $ 可得唯一的实数 $ f(p) $ .

设 $ M,N $ 分别是维数为 $ m,n $ 的流形,则 $ M\times N $ 也是流形,且维数为 $ m+n. $ 

---

### 2.2 切矢和切矢场

#### 矢量

映射 $ v:\mathscr{F}_M\to\mathbb{R} $ 称为点 $ p\in M $ 的一个**矢量(vector)**,若 $ \forall f,g\in\mathscr{F}_M,\alpha,\beta\in \mathbb{R} $ 有

1. (线性性)  $ v(\alpha f+\beta g)=\alpha v(f)+\beta v(g) $ .
2. (莱布尼茨律)  $ v(fg)=f \mid _pv(g)+g \mid _pv(f) $ ,其中 $ f \mid _p $ 代表函数 $ f $ 在 $ p $ 点的值,亦可以记作 $ f(p) $ .

设 $ (O,\psi) $ 是坐标系,其坐标为 $ x^\mu $ ,则 $ M $ 上任一光滑函数 $ f\in \mathscr{F}_M $ 与
 $ (O,\psi) $ 结合得到 $ n $ 元函数 $ F(x^1,\cdots,x^n) $ ,借此可以给 $ O $ 中任一点 $ p $ 定义 $ n $ 个矢量,记作 $ X_\mu,\mu=1,\cdots,n $ ,它们作用于任一  $ f\in\mathscr{F}_M $ 定义为:
 \$\$ X_\mu(f):=\left.\dfrac{\partial F(x^1,\cdots,x^n)}{\partial x^\mu}\right \mid _p=\left.\dfrac{\partial f(x^1,\cdots,x^n)}{\partial x^\mu}\right \mid _p=\left.\dfrac{\partial f(x)}{\partial x^\mu}\right \mid _p,\forall f\in\mathscr{F}_M \$\$ 

设 $ M $ 的维数为 $ n $ ,以 $ V_p $ 代表 $ M $ 中 $ p $ 点所有矢量的集合,则 $ V_p $ 是 $ n $ 维向量空间.

坐标域内任一点 $ p $ 的 $ \{X_1,\cdots,X_n\} $ 称为 $ V_p $ 的一个**坐标基底(coordinate basis)**,每个 $ X_\mu $ 称为一个**坐标基矢(coordinate basis vector)**, $ v\in V_p $ 以 $ \{X_\mu\} $ 线性表出的系数 $ v^\mu $ 称为 $ v $ 的**坐标分量(coordinate components)**.

设 $ \{x^\mu\} $ 和 $ \{x^{\prime \nu}\} $ 为两个坐标系,其坐标域的交集非空, $ p $ 为交集中一点, $ v\in V_p,\{v^\mu\} $ 和 $ \{v^{\prime \nu}\} $ 是 $ v $ 在这两个系里面的坐标分量,则有 \$\$ v^{\prime\nu}=\left.\dfrac{\partial x^{\prime\nu}}{\partial x^\mu}\right \mid _p v^\mu, \$\$ 
其中 $ x^{\prime\nu} $ 是两坐标系间变换函数 $ x^{\prime\nu}(x^\sigma) $ 的简写.上式称为**矢量的分量变换式**.

#### 曲线

设 $ I $ 为 $ \mathbb{R} $ 的一个区间,则 $ C^r $ 类映射 $ C:I\to M $ 称为 $ M $ 上的一条 $ C^r $ 类的曲线(curve). $ \forall t \in I $ ,有唯一的点 $ C(t)\in M $ 与之对应, $ t $ 称为曲线的**参数(parameter)**.

曲线 $ C^\prime:I^\prime \to M $ 称为曲线 $ C:I\to M $ 的**重参数化(reparametrization)**,若存在到上映射 $ \alpha:I\to I^\prime $ ,满足:

1.  $ C=C^\prime\circ \alpha $ ;
2. 由 $ \alpha $ 诱导的函数 $ t^\prime=\alpha(t) $ 有处处非零的导数.

设 $ (O,\psi) $ 是坐标系, $ C[I]\subset O, $ 则 $ \psi\circ C $ 是从 $ I\subset\mathbb{R} $ 到 $ \mathbb{R}^n $ 的映射,相当于 $ n $ 个一元函数 $ x^\mu=x^\mu(t),\mu=1,\cdots,n. $ 这 $ n $ 个等式称为曲线的**参数方程**或者**参数表达式**或者**参数式**.

设 $ (O,\psi) $ 为坐标系, $ x^\mu $ 为坐标,则 $ O $ 的子集 $ \{p\in O \mid  x^2(p)=\text{常数},\cdots,x^n(p)=\text{常数}\} $ 可看成以 $ x^1 $ 为参数的一条曲线(的像),叫做** $ x^1 $ 坐标线(coordinate line)**.改变 $ x^2,\cdots,x^n $ 的常数值则得到另一曲线.

#### 切矢

设 $ C(t) $ 是流形 $ M $ 上的 $ C^1 $ 曲线,则线上 $ C(t_0) $ 点的切于 $ C(t) $ 点的**切矢(tangent vector)** $ T $ 是 $ C(t_0) $ 点的矢量,它对 $ f\in \mathscr{F}_M $ 的作用定义为:
 \$\$ \left.T(f):=\dfrac{d(f\circ C)}{dt}\right \mid _{t_0}=\left.\dfrac{\partial}{\partial t}\right \mid _{C(t_0)}(f)=\left.\dfrac{df(C(t))}{dt}\right \mid _{t_0},\forall f\in \mathscr{F}_M. \$\$ 

>  $ f:M\to\mathbb{R} $ 是 $ M $ 上的函数(标量场),不是什么一元函数,但与曲线 $ C:I\to M $ 的结合 $ f\circ M $ 则是以 $ t $ 为自变量的一元函数,也可记作 $ f(C(t)) $ .

设曲线 $ C(t) $ 在某坐标系中的参数式为 $ x^\mu=x^\mu(t) $ ,则线上任一点的切矢 $ \frac{\partial}{\partial t} $ 在该坐标基底的展开式为:
 \$\$ \dfrac{\partial }{\partial t}=\dfrac{d x^\mu(t)}{d t}\dfrac{\partial}{\partial x^\mu}, \$\$ 即曲线 $ C(t) $ 的切矢 $ \frac{\partial}{\partial t} $ 的坐标分量是 $ C(t) $ 在该系的参数式 $ x^\mu(t) $ 对 $ t $ 的导数.

非零矢量 $ v,u\in V_p $ 称为互相**平行(parallel)**的,若 $ \exists \alpha \in \mathbb{R}s.t.v=\alpha u. $ 

设曲线 $ C^\prime:I^\prime\to M $ 是 $ C:I\to M $ 的重参数化,则两者在任一像点的切矢 $ \frac{\partial }{\partial t} $ 和 $ \frac{\partial }{\partial t^\prime} $ 具有如下关系:
 \$\$ \dfrac{\partial }{\partial t}=\dfrac{d t^\prime(t)}{d t}\dfrac{\partial}{\partial t^\prime}, \$\$ 
其中 $ t^\prime(t) $ 是由映射 $ \alpha:I\to I^\prime $ 诱导而得到的一元函数 $ \alpha(t) $ .

 $ V_p $ 中任一元素可以视为过 $ p $ 的某曲线的切矢,因此 $ p $ 点的矢量亦称为**切矢量**, $ v $ 称为 $ p $ 点的**切空间**.

#### 流形上的矢量场

设 $ A $ 为 $ M $ 的子集,若给 $ A $ 中每点指定一个矢量,就得到一个定义在 $ A $ 上的**矢量场(vector field)**.

>设 $ v $ 是 $ M $ 上的矢量场, $ f $ 是 $ M $ 上的函数,则 $ v $ 在 $ M $ 的任一点 $ p $ 的值 $ v \mid _p $ 将把 $ f $ 映射
为一个实数 $ v \mid _{p}(f) $ ,它在 $ p $ 点遍历 $ M $ 时构成 $ M $ 上的一个函数 $ v(f) $ .因此,矢量场 $ v $ 可以视为函数 $ f $ 到函数 $ v(f) $ 的映射.

 $ M $ 上的矢量场 $ v $ 称为** $ C^\infty $ 类(光滑的)**,若 $ v $ 作用于 $ C^\infty $ 类函数的结果为 $ C^\infty $ 类函数,即 $ v(f)\in\mathscr{F}_M,\forall f\in \mathscr{F}_M. \$\$ v $ 称为** $ C^r $ 类**,若 $ v $ 作用于 $ C^r $ 类函数的结果为 $ C^r $ 类函数.

坐标基矢 $ \{X_\mu\equiv\dfrac{\partial}{\partial x^\mu}\} $ 构成坐标域上的 $ n $ 个光滑矢量场,叫做**坐标基矢场**.

 $ M $ 上矢量场 $ v $ 是 $ C^\infty(C^r) $ 类的充要条件是它在任一坐标基底的分量 $ v^\mu $ 为 $ C^\infty(C^r) $ 类函数.

两个光滑矢量场 $ u,v $ 的**对易子(commutator)**是一个光滑矢量场 $ [u,v] $ ,定义为:
 \$\$ [u,v] \mid _p(f):=u(v(f))-v(u(f)),\forall f \in\mathscr{F}_M. \$\$ 

>设 $ \{x^\mu\} $ 为任一坐标系,则 $ \left[\dfrac{\partial}{\partial x^\mu},\dfrac{\partial}{\partial x^\nu}\right]=0,\mu,\nu=1,\cdots,n. $ 

曲线 $ C(t) $ 叫做矢量场 $ v $ 的**积分曲线(integral curve)**,若其上每点的切矢等于该点的 $ v $ 值.

设 $ v $ 是 $ M $ 上的光滑矢量场,则 $ M $ 的任一点 $ p $ 必有 $ v $ 的局部唯一的积分曲线 $ C(t) $ 经过,即满足 $ C(0)=p. $ 

#### 单参微分同胚群

 $ C^\infty $ 映射 $ \phi:\mathbb{R}\times M\to M $ 称为 $ M $ 上的一个**单参微分同胚群(oneparameter group of diffeomorphisma)**,若

1.  $ \forall t \in \mathbb{R},\phi_t:M\to M $ 是微分同胚;
2.  $ \forall t,s \in \mathbb{R},\phi_t\circ \phi_s=\phi_{t+s} $ .

>设 $ \phi:\mathbb{R}\times M\to M $ ,则 $ \phi_t=\phi(t,\cdot):M\to M;\phi_p=\phi(\cdot,p):\mathbb{R}\to M. $ \
> $ \phi $ 为 $ M $ 上的一个单参微分同胚群,实际上指的是集合 $ \{\phi_t \mid t\mathbb{R}\} $ 是一个单参微分同胚群. 

设 $ \phi:\mathbb{R}\times M\to M $ 是单参微分同胚群,则 $ \forall p\in M,\phi_p:\mathbb{R}\to M $ 是过 $ p $ 点的一条光滑曲线,满足 $ \phi_p(0)=p $ ,叫做这个单参微分同胚群过 $ p $ 的**轨道(orbit)**.把这条曲线在 $ \phi_p(0) $ 的切矢记作 $ v \mid _p $ ,便得 $ M $ 上的一个光滑矢量场 $ v $ .可见 $ M $ 上的一个单参微分同胚群给出 $ M $ 上的一个光滑矢量场.

---

### 2.3 对偶矢量场

#### 对偶矢量与对偶空间

设 $ V $ 是 $ \mathbb{R} $ 上的有限维向量空间.线性映射 $ \omega:V\to \mathbb{R} $ 称为 $ V $ 上的**对偶矢量(dual vector)**. $ V $ 上全体对偶矢量的集合称为 $ V $ 的**对偶空间**,记作 $ V^*. $ 

 $ V^* $ 是矢量空间,且 $ dim V^*=dim V. $ 故 $ V^* $ 与 $ V $ 同构,二者之间不存在一个特殊的与众不同的同构映射.

> 两个矢量空间叫做**同构的(isomorphic)**,若两者间存在一一到上的线性映射(称为**同构映射**).两矢量空间同构的充要条件是维数相同.

定义 $ v^{**}(\omega):=\omega(v),\forall \omega \in V^* $ ,于是映射 $ V\to V^{**} $ 为同构映射,表明 $ V,V^{**} $ 可以视为同一空间.

若矢量空间 $ V $ 中有一个基底变换 $ e_\mu^\prime=A^\nu{}_\mu e_\nu,A^\nu{}_\mu $ 是新基矢 $ e^\prime_\mu $ 用原来基底展开的第 $ \nu $ 个分量.以 $ A^\nu{}_\mu $ 为元素排成的非退化方针记作 $ A $ ,则相应的基底变换为: \$\$ e^{\prime\mu*}=(\tilde{A}^{-1})_\nu{}^\mu e^{\nu*}, \$\$ 
其中 $ \tilde{A} $ 是 $ A $ 的转置矩阵, $ \tilde{A}^{-1} $ 是 $ \tilde{A} $ 之逆.

若在 $ M $ 或者 $ A\subset M $ 上每点指定一个对偶矢量,就得到 $ M $ 或者 $ A $ 上的一个**对偶矢量场**. $ M $ 上的对偶矢量场 $ \omega $ 称为**光滑的**,若 $ \forall \text{光滑矢量场}v,\omega(v)\in \mathscr{F}_M. $ 

设 $ f\in \mathscr{F}_M,f $ 自然诱导出 $ M $ 上的一个对偶矢量场,记作 $ df $ ,满足 \$\$ df \mid _p(v):=v(f),\forall v\in V_p. \$\$ 

---

### 2.4 张量场

#### 张量、张量积

矢量空间 $ V $ 上的一个** $ (k,l) $ 型张量**(tensor of type(k,l))是一个多重线性映射: \$\$ T:\underbrace{V^*\times \cdots \times V^*}_{k\text{个}}\times \underbrace{V\times \cdots \times V}_{l\text{个}}\to \mathbb{R}. \$\$ 

>  $ V $ 上的对偶矢量是 $ (0,1) $ 型张量,因为对偶矢量是 $ V\to\mathbb{R} $ 的映射.\
>  $ v\in V $ 可视为 $ V $ 上的(1,0)型张量,因为 $ v $ 可以视为 $ v^{**},而 $ v^{**} $ 是 $ V^*\to\mathbb{R} $ 的映射.

>**张量面面观**:对 $ T:V^*\times V\to\mathbb{R} $ 的理解,设 $ \omega\in V^*,v\in V. $ \
>
>> 1.  $ T(\omega;*) $ 将一个矢量线性映射为实数,表明它是一个对偶矢量;
   2.  $ T $ 将对偶矢量 $ \omega $ 线性映射为对偶矢量 $ T(\omega;*) $ ,即 $ T:V^*\to V^* $ ;
   3.  $ T $ 将矢量 $ v $ 线性映射为矢量 $ T(*;v) $ ,即 $ T:V\to V $ .

 $ V $ 上的 $ (k,l) $ 和 $ (k^\prime,l^\prime) $ 型张量 $ T $ 和 $ T^\prime $ 的**张量积**(tensor product) $ T\otimes T^\prime $ 是一个 $ (k+k^\prime,l+l^\prime) $ 型张量,定义为 \$\$ 
\begin{aligned}
&T\otimes T^\prime(\omega^1,\cdots,\omega^k,\omega^{k+1},\cdots,\omega^{k+k^\prime};v_1,\cdots,v_l,v_{l+1},\cdots,v_{l+l^\prime})\\
&:=T(\omega^1,\cdots,\omega^k;v_1,\cdots,v_l)T^\prime(\omega^{k+1},\cdots,\omega^{k+k^\prime};v_{l+1},\cdots,v_{l+l^\prime}).
\end{aligned} \$\$ 

>欧氏空间中的并矢 $ \mathbf{vu} $ 实际上是 $ \mathbf{v} $ 与 $ \mathbf{u} $ 的张量积,不满足交换律,即 $ \mathbf{vu}\neq\mathbf{uv} $ .一般而言,两个矢量或者两个对偶矢量的张量积都不满足交换律.\
> 量子力学中的 $  \mid {\psi}\rangle \mid {\phi}\rangle $ 也是 $  \mid {\psi}\rangle $ 与 $  \mid {\phi}\rangle $ 的张量积,只不过 $  \mid {\psi}\rangle $ 与 $  \mid {\phi}\rangle $ 所在的矢量空间是复数域上的无限维矢量空间.

 $ V $ 上全体 $ (k,l) $ 型张量的集合 $ \mathscr{T}_V(k,l) $ 是矢量空间, $ dim\mathscr{T}_V(k,l)=n^{k+l}. $ 

>  $ T^{\mu\nu}{}_\sigma $ 是张量 $ T $ 在基底 $ \{e_\mu\otimes e_\nu \otimes e^{\sigma*}\} $ 的分量,简称 $ T $ 在基底 $ \{e_\mu\} $ 的分量.
>
> 同一 $ T $ 在任意两个基底的分量对应的两个矩阵 $ (T^\mu{}_\nu),(T^{\prime \mu}{}_\nu) $ 互为相似矩阵.

同一(1,1)型张量 $ T $ 在不同基底的矩阵有相同的迹 $ T^\mu{}_\mu $ ,通常称为 $ T $ 的**缩并**(contraction),暂记作 $ CT $ ,即 \$\$ CT:=T^\mu{}_\mu=T(e^{\mu*};e_\mu). \$\$ 

 $ T\in \mathscr{T}_V(k,l) $ 的第 $ i $ 上标 $ (i\leqslant k) $ 与第 $ j $ 下标 $ (j\leqslant l) $ 的**缩并**定义为:
 \$\$ C_j^iT:=T(\cdot,\cdots,\underset{\text{第 $ i $ 上槽}}{e^{\mu*}},\cdot,\cdots;\cdot,\cdots,\underset{\text{第 $ j $ 下槽}}{e_\mu},\cdot,\cdots)\in\mathscr{T}_V(k-1,l-1)(\text{对 $ \mu $ 求和}). \$\$ 

>  $ C_j^iT $ 与基底选择无关.

张量积恒等式:

1.  $ C(v\otimes \omega)=\omega_\mu v^\mu=\omega(v)=v(\omega),\forall v\in V,\omega \in V^*. $ 
2.  $ C^1_2(T\otimes v)=T(\cdot,v),\forall v\in V,T\in \mathscr{T}_V(0,2). $ 
3.  $ C^2_2(T\otimes \omega)=T(\cdot,\omega;\cdot),\forall \omega \in V^*,T\in \mathscr{T}_V(2,1). $ 

>  $ T $ 对 $ \omega(v) $ 作用就是先求 $ T $ 与 $ \omega(v) $ 的张量积然后再缩并,简称“作用即缩并”.

#### 流形上的张量场

流形 $ M $ 中任一点 $ p $ 的切空间 $ V_p $ 的全体 $ (k,l) $ 型张量的集合记作 $ \mathscr{T}_{V_p}(k,l) $ .

若在流形 $ M $ 上每点指定一个 $ (k,l) $ 型张量,就得到 $ M $ 上的一个 $ (k,l) $ 型**张量场**, $ M $ 上的张量场 $ T $ 称为**光滑的**,若对于光滑对偶矢量场 $ \omega^1,\cdots,\omega^k $ 及光滑矢量场 $ v_1,\cdots,v_l $ 有 $ T(\omega^1,\cdots,\omega^k;v_1,\cdots,v_l)\in \mathscr{F}_M. $ 

 $ (k,l) $ 型张量在两个坐标系中的分量的变换关系为 \$\$ 
T^{\prime\mu_1\cdots\mu_k}{}_{\nu_1\cdots\nu_l}=\dfrac{\partial x^{\prime\mu_1}}{\partial x^{\rho_1}}\cdots\dfrac{\partial x^{\sigma_l}}{\partial x^{\prime \nu_l}}T^{\rho_1\cdots\rho_k}{}_{\sigma_1\cdots\sigma_l}. \$\$ 

---

### 2.5 度规张量场

#### 度规

矢量空间 $ V $ 上的一个**度规**(metric) $ g $ 是 $ V $ 上的一个对称、非退化的(0,2)型张量,即由 $ V\times V\to \mathbb{R} $ 的双重线性映射.

- 对称: $ g(v,u)=g(u,v),\forall u,v\in V. $ 
- 非退化: $ g(v,u)=0,\forall u\in V\Rightarrow v=0\in V. $ 

> 若 $ g $ 非退化,则它在 $ V $ 的任一基底 $ \{e_\mu\} $ 的分量 $ g_{\mu\nu}\equiv g(e_\mu,e_\nu) $ 排成的矩阵也非退化.反之,若 $ V $ 有基底使得 $ g $ 的分量矩阵非退化,则 $ g $ 非退化.

 > 给定 $ g $ 后再给定一个 $ v \in V $ ,得到  $ g(v,\cdot) \in V^* $ ,故 $ g:V \to V^* $ ,这是一个同构映射.很自然用这一个映射把 $ V $ 与 $ V^* $ 认同.从而无论有无度规, $ V $ 都与 $ V^{**} $ 认同,一旦有度规,则 $ V $ 与 $ V^\prime $ 也自然认同.
 

 $ v\in V $ 的**长度**或者**大小**定义为 $  \mid v \mid :=\sqrt{ \mid g(v,v) \mid } $ .

矢量 $ u,v\in V $ 称为**相互正交的**,若 $ g(v,u)=0 $ ;

 $ V $ 的基底 $ \{e_\mu\} $ 叫做**正交归一的**,若任两个基矢正交且每一基矢 $ e_\mu $ 满足 $ g(e_\mu,e_\mu)=\pm 1 $ (不对 $ \mu $ 求和).即度规 $ g $ 在正交归一基底的分量满足:
 \$\$ g_{\mu \nu}
=\left\{
\begin{aligned}
0,\mu\neq\nu\\
\pm 1,\mu=\nu
\end{aligned}
\right.
 \$\$ 
因此,度规在正交归一基底的分量排成的矩阵是对角阵,对角元为+1或者-1.

>度规 $ g $ 与一般内积的区别在于 $ g(v,v) $ 可以为负,且 $ g(v,v)=0 $ 并不意味着 $ v=0 $ .

任何带度规的矢量空间都有正交归一基底.度规写成对角矩阵时对角元中 $ \pm 1 $ 的个数与所选正交归一基底无关.

#### 若干定义

用正交归一基底写成对角矩阵后,

- 对角元全为 $ +1 $ 的度规叫做**正定的**(positive definite)或者**黎曼的**(Riemannian);
- 对角元全为 $ -1 $ 的度规叫做**负定的**(negative definite);
- 其他度规叫做**不定的**(indefinite),只有一个对角元为 $ -1 $ 的不定度规叫做**洛伦兹的**(Lorentzian).
- 对角元之和叫做度规的**号差**(signature).

> 默认采用号差为+2的四维洛伦兹度规,即度规对角元为 $ (-1,1,1,1) $ .

带洛伦兹度规 $ g $ 的矢量空间 $ V $ 的元素可以分为三类:

- 满足 $ g(v,v)>0 $ 的 $ v $ 称为**类空矢量**(spacelike vector);
- 满足 $ g(v,v)<0 $ 的 $ v $ 称为**类时矢量**(timelike vector);
- 满足 $ g(v,v)=0 $ 的 $ v $ 称为**类光矢量**(lightlike vector或者null vector).

#### 度规场及其分类

 $ M $ 上的对称的、处处非退化的(0,2)型张量场称为**度规张量场**.

设 $ C(t) $ 是带有正定度规场 $ g $ 的任意流形 $ M $ 上任一 $ C^1 $ 曲线, $ T $ 是其切矢.即 $ T\equiv \dfrac{\partial}{\partial t} $ ,则 $  \mid T \mid =\sqrt{g(T,T)} $ , $ C(t) $ 的线长自然定义为 \$\$ l:=\int\sqrt{g(T,T)}d t. \$\$ 

设流形 $ M $ 上有洛伦兹度规场 $ g $ ,则 $ M $ 上的类空、类光以及类时曲线 $ C(t) $ 的线长定义为 \$\$ l:=\sqrt{ \mid g(T,T) \mid }d t,T\equiv\dfrac{\partial}{\partial t}. \$\$ 

>曲线的线长与其参数化无关,曲线重参数化(保持映射的像不变而适当改变参数)不改变线长.

定义**线元**(line element) $ ds^2 $ 为 \$\$ ds^2\equiv g_{\mu\nu}dx^\mu dx^\nu \$\$ 

>  从线元表达式可以直接读出度规全体坐标分量,给定线元表达式相当于给定度规场.

设流形 $ M $ 上给定度规场 $ g $ ,则 $ (M,g) $ 叫做**广义黎曼空间**,

- 若 $ g $ 正定,叫做**黎曼空间**;

>欧氏空间是最简单的黎曼空间.设 $ \{x^\mu\} $ 是 $ \mathbb{R}^n $ 的自然坐标,在 $ \mathbb{R}^n $ 上定义度规张量场 $ \delta $ 为 \$\$ \delta:=\delta_{\mu \nu}dx^\mu\otimes dx^\nu, \$\$ 
则 $ (\mathbb{R},\delta) $ 称为**n维欧氏空间**(n-dimensional Euclidean space), $ \delta $ 为欧式度规.\
>  $ n $ 维欧氏空间中满足 \$\$ \delta\left(\dfrac{\partial}{\partial x^\alpha},\dfrac{\partial}{\partial x^\beta}\right)=\delta_{\alpha\beta} \$\$ 
> 的坐标系称为**笛卡尔坐标系**或者**直角坐标系**.即一个坐标系叫做笛卡尔坐标系,若其坐标基底以欧式度规 $ \delta $ 衡量为正交归一.

- 若 $ g $ 为洛伦兹,叫做**伪黎曼空间**,物理上叫做**时空**.

>闵氏空间是最简单的伪黎曼空间.设 $ \{x^\mu\} $ 是 $ \mathbb{R}^n $ 的自然坐标,在 $ \mathbb{R}^n $ 上定义度规场 $ \eta $ 为 \$\$ \eta:=\eta_{\mu\nu}dx^\mu \otimes dx^\nu, \$\$ 
则 $ (\mathbb{R}^4,\eta) $ 称为**n维闵氏(Minkowski)空间**, $ \eta $ 为**闵氏度规**.\
 $ n $ 维闵氏空间中满足 \$\$ \eta\left(\dfrac{\partial}{\partial x^\alpha} ,\dfrac{\partial}{\partial x^\beta}\right)=\eta_{\alpha\beta}, \$\$ 
的坐标系称为**洛伦兹坐标系**或者**伪笛卡尔坐标系**.

---

### 2.6 抽象指标记号

#### 表示张量的方法及其缺点

- 用不带指标的字母代表张量.
  -  看不出张量类型；
  -  不易表明哪一个上槽与哪一下槽做缩并,即使采用 $ C^i_jT $ 在运算中也有诸多不便. 
- 用分量代表张量,用分量服从的等式代表张量服从的等式
   - 有时由于选用某一个或者某一类特殊基底得到较为简单的分量等式,只对特殊基底成立,因而不代表张量等式.

#### 抽象指标记号(Penrose)要点
1. (k,l)型张量用带有 $ k $ 个上标和 $ l $ 个下标的字母表示,上下指标为小写拉丁字母,只表示张量类型;
2. 重复上下抽象指标表示对这两个指标求缩并;
3. 张量积记号省略,代表张量的字母带着自己的抽象指标可以交换;
4. 涉及张量的分量时,相应指标用小写希腊字母 $ \mu,\nu,\alpha,\beta $ 等具体指标表示,可以问及 $ \mu=1,\mu=2 $ 的问题;
5.  $ \delta^a{}_b $ 与任一张量缩并的结果是把该张量的上标 $ b $ 换为 $ a $ ,或把下标 $ a $ 换为 $ b $ .
6. 度规 $ g\in\mathscr{T}_V(0,2) $ 记为 $ g_{ab} $ .

#### 逆变、协变指标及张量的对称性

张量的上指标和下指标又称为**逆变指标**
(contravariant index)和**协变指标**(covariant index).相应地,矢量 $ v^a $ 和对偶矢量 $ \omega_a $ 分别称为**逆变矢量**与**协变矢量**.

 $ T\in \mathscr{T}_V(0,2) $ 
称为**对称的**(symmetric),若 $ T(u,v)=T(v,u),\forall u,v \in V. $ 

  (0,2)型张量 $ T_{ab} $ 的对称部分 $ T_{(ab)} $ 和反对称部分 $ T_{[ab]} $ 定义为 \$\$ 
  T_{(ab)}:=\dfrac{1}{2}(T_{ab}+T_{ba});  T_{[ab]}:=\dfrac{1}{2}(T_{ab}-T_{ba}).
   \$\$ 

一般地, $ (0,l) $ 型张量 $ T_{a_1\cdots a_l} $ 的对称和反对称部分定义为
 \$\$ 
\begin{aligned}
T_{(a_1\cdots a_l)}&:=\dfrac{1}{l!}\sum\limits_{\pi}T_{a_{\pi(1)}\cdots a_{\pi(l)}},\\
T_{[a_1\cdots a_l]}&:=\dfrac{1}{l!}\sum\limits_{\pi}\delta_\pi T_{a_{\pi(1)}\cdots a_{\pi(l)}},\\
\end{aligned}
 \$\$ 
其中 $ \pi $ 表示 $ (1,\cdots,l) $ 的一种排列, $ \pi(1) $ 代表该排列中的第一个数字, $ \sum\limits_\pi $ 表示对各种排列取和, $ \delta_\pi=\pm 1 $ ,偶排列取正,奇排列取负.


 $ T\in\mathscr{T}_V(0,l) $ 称为**全对称的**,若 $ T_{a_1\cdots a_l}=T_{(a_1\cdots a_l)} $ ; $ T $ 称为**全反对称的**,若 $ T_{a_1\cdots a_l}=T_{[a_1\cdots a_l]} $ .

> 任一(0，2)型张量可以表示为其对称和反对称部分之和,即 $ T_{ab}=T_{(ab)}+T_{[ab]} $ ,但对于 $ l>2 $ 
的 $ (0,l) $ 型张量不成立.



设 $ T_{a_1\cdots a_l}=T_{(a_1\cdots a_l)} $ 则 $ T_{a_1\cdots a_l}=T_{a_{\pi(1)}\cdots a_{\pi(l)}} $ ,即 $ T_{(a_1\cdots a_l)} $ 
展开式( $ l! $ 项)中的每一项都等于 $ T_{a_1\cdots a_l} $ .

设 $ T_{a_1\cdots a_l}=T_{[a_1\cdots a_l]} $ 则 $ T_{a_1\cdots a_l}=\delta_\pi T_{a_{\pi(1)}\cdots a_{\pi(l)}} $ ,即 $ T_{[a_1\cdots a_l]} $ 
展开式中的偶排列项等于 $ T_{a_1\cdots a_l} $ ,奇排列项等于 $ -T_{a_1\cdots a_l} $ .

#### 括号相关定理

1. 缩并时括号具有“传染性”;
2. 括号内的同种子括号可以随意删减;
3. 括号内加异种括号得到零;
4. 异种括号缩并为零.


---

## 第3章 黎曼(内禀)曲率张量

### 3.1 导数算符

#### (无挠)导数算符的定义

- 以 $ \mathscr{F}_M(k,l) $ 代表流形 $ M $ 上全体 $ C^\infty $ 的 $ (k,l) $ 型张量场的集合.映射 $ \nabla:\mathscr{F}_M(k,l)\to\mathscr{F}_M(k,l+1) $ 称为 $ M $ 上的**(无挠)导数算符**(derivative operator),若满足以下条件:

1. 具有线性性: \$\$ 
  \begin{aligned}
  &\nabla_a(\alpha T^{b_1,\cdots,b_k}{}_{c_1\cdots c_l}+\beta S^{b_1\cdots b_k}{}_{c_1\cdots c_l})=\alpha \nabla_\alpha T^{b_1\cdots b_k}{}_{c_1\cdots c_l}+\beta\nabla_a S^{b_1\cdots b_k}{}_{c_1\cdots c_l},\\
  & \forall T^{b_1,\cdots,b_k}{}_{c_1\cdots c_l}, S^{b_1\cdots b_k}{}_{c_1\cdots c_l}\in \mathscr{F}_M(k,l),\alpha,\beta \in \mathbb{R};
  \end{aligned}
   \$\$ 
2. 满足莱布尼茨律:
   \$\$ 
  \begin{aligned}
  & \nabla_a(T^{b_1\cdots b_k}{}_{c_1\cdots c_l}S^{d_1\cdots d_{k^\prime}}{}_{e_1\cdots e_{l^\prime}})=T^{b_1\cdots b_k}{}_{c_1\cdots c_l}\nabla_a S^{d_1\cdots d_{k^\prime}}{}_{e_1\cdots e_{l^\prime}}\\
  &+S^{d_1\cdots d_{k^\prime}}{}_{e_1\cdots e_{l^\prime}}\nabla_aT^{b_1\cdots b_k}{}_{c_1\cdots c_l},\\
  &\forall T^{b_1\cdots b_k}{}_{c_1\cdots c_l }\in \mathscr{F}_M(k,l) ,S^{d_1\cdots d_{k^\prime}}{}_{e_1\cdots e_{l^\prime}}\in\mathscr{F}_M(k^\prime,l^\prime);
  \end{aligned}
   \$\$ 
3. 与缩并可以交换顺序.设 $ C $ 表示缩并,则有 $ \nabla \circ C=C\circ \nabla. $ 

>等价为 $ \nabla_a\delta^b{}_c=0,\delta^b{}_c $ 视为 $ (1,1) $ 型张量场,其在每点 $ p\in M $ 定义为 $ \delta^b{}_cv^c=v^b,\forall v^c \in V_p. $ 


4.  $ v(f)=v^a\nabla_a f,\forall f\in \mathscr{F}_M,v\in \mathscr{F}_M(1,0); $ 

> 设 $ \nabla_a $ 是任一导数算符,则由条件4可知 $ \nabla_a f=(df)_a,\forall f\in \mathscr{F}_M, $ 其中 $ (df)_a $ 是函数 $ f $ 生成的对偶矢量场 $ df $ 的抽象指标表示.

5. 具有无挠(torsion free)性: $ \nabla_a\nabla_bf=\nabla_b\nabla_a f,\forall f\in \mathscr{F}_M. $ 
  
> 满足条件1-4但不满足条件5的导数算符称为**有挠导数算符**,广义相对论中只使用无挠导数算符.
>
> >条件5实际上是下式的抽象指标表述 \$\$ (\nabla\nabla f)(u,v)=(\nabla\nabla f)(v,u),\forall u,v\in \mathscr{F}(1,0), \$\$ 亦即 $ \nabla\nabla f $ 是一个对称的 $ (0,2) $ 型张量.

#### 若干定理

1. 设 $ p\in M,\omega_b,\omega_b^\prime \in \mathscr{F}(0,1) $ 满足 $ \omega^{\prime}_b \mid _p=\omega_b \mid _p, $ 则有 \$\$ [(\tilde{\nabla}_a-\nabla_a)\omega_b^\prime]_p=[(\tilde{\nabla}_a-\nabla_a)\omega_b]_p, \$\$ 
其中 $ (\tilde{\nabla}_a-\nabla_a)\omega_b $ 是 $ \tilde{\nabla}_a\omega_b-\nabla_a\omega_b $ 的简写.

> $ [(\tilde{\nabla}_a-\nabla_a)\omega_b]_p $ 只依赖于 $ \omega_b $ 在 $ p $ 点的值,这说明 $ (\tilde{\nabla}_a-\nabla_a) $ 是把 $ p $ 的对偶矢量 $ \omega_b \mid _p $ 变为 $ p $ 点的 $ (0,2) $ 型张量 $ [(\tilde{\nabla}_a-\nabla_a)\omega_b]_p $ 的线性映射.
>
>> 所以在 $ p $ 点 $ (\tilde{\nabla}_a-\nabla_b) $ 对应于一个 $ (1,2) $ 型张量 $ C^c{}_{ab} $ ,满足 \$\$ [(\tilde{\nabla}_a-\nabla_a)\omega_b]_p=C^c{}_{ab}\omega_c \mid _p\Rightarrow\nabla_a\omega_b=\tilde{\nabla}_a\omega_b-C^c{}_{ab}\omega_c,\forall \omega_b \in \mathscr{F}(0,1). \$\$ 

2.  $ \nabla_a $ 的无挠性将会导致张量 $ C^c{}_{ab} $ 具有如下的对称性 $ C^c{}_{ab}=C^c{}_{ba}. $ 

3.   $ \nabla_a v^b=\tilde{\nabla}_a v^b+C^b{}_{ac}v^c,\forall v^b\in \mathscr{F}_M(1,0) $ .

4. 一般地,对 $ \forall T\in \mathscr{F}_M(k,l) $ 有 \$\$ 
\begin{aligned}
\nabla_a T^{b_1\cdots b_k}{}_{c_1\cdots c_l}&=\tilde{\nabla}_a T^{b_1\cdots b_k}{}_{c_1\cdots c_l}+\sum\limits_i C^{b_i}{}_{ad}T^{b_1\cdots d\cdots b_k}{}_{c_1\cdots c_l}\\
&-\sum\limits_i C^d{}_{ac_j}T^{b_1\cdots b_k}{}_{c_1\cdots d\cdots c_l}.
\end{aligned}
 \$\$ 

> 上式表明,任意两个导数算符的差别仅仅体现在一个张量场 $ C^c{}_{ab} $ 上. 

#### 普通导数算符

设 $ \{x^\mu\} $ 是 $ M $ 的一个坐标系,其坐标基底和对偶基底分别是 $ \{\left(\frac{\partial}{\partial x^\mu}\right)^a\} $ 和 $ \{(d x^\mu)_a\} $ .在坐标域 $ O $ 上定义映射 $ \partial_a:\mathscr{F}_O(k,l)\to\mathscr{F}_O(k,l+1) $ 如下: \$\$ \partial_aT^b{}_c:=(dx^\mu)_a(\frac{\partial}{\partial x^\nu})^b(dx^\sigma)_c\partial_\mu T^\nu{}_\sigma, \$\$ 其中 $ T^\nu{}_\sigma $ 是 $ T^b{}_c $ 在该坐标系下的分量, $ \partial_\mu $ 是对坐标 $ x^\mu $ 求偏导数的符号 $ \frac{\partial}{\partial x^\mu} $ 的简写.以上定义了一个依赖于坐标系,且只在该坐标系的坐标域上面有定义的导数算符,称为该坐标系的**普通导数算符**(ordinary derivative).

>  $ \partial_a $ 亦可以定义为:张量场 $ T^{b_1\cdots b_k}{}_{c_1\cdots c_l} $ 的普通导数 $ \partial_a T^{b_1\cdots b_k}{}_{c_1\cdots c_l} $ 的坐标分量等于该张量场的坐标分量对坐标的偏导数 $ \frac{\partial(T^{\nu_1\cdots \nu_k}{}_{\sigma_1\cdots \sigma_l})}{\partial x^\mu} $ .
>
> > - 任一坐标系的 $ \partial_a $ 作用于该系的任一坐标基矢和任一对偶坐标基矢结果都为零,即 \$\$ \partial_a(\frac{\partial}{\partial x^\nu})^b=0=\partial_a(dx^\nu)_b. \$\$ 
> > -  $ \partial_a $ 满足导数算符定义中条件5强得多的条件,即
 \$\$ \partial_a\partial_b T^{\cdots}{}_{\cdots}=\partial_b\partial_a T^{\cdots}{}_{\cdots}, \$\$ 
>其中 $ T^{\cdots}{}_{\cdots} $ 是任意型张量.  
>- 称与坐标系无关的导数算符 $ \nabla_a $ 为**协变导数算符**(covariant derivative), $ \partial_a $ 则不在此列.

#### 克氏符

- 设 $ \partial_a $ 是 $ (M,\nabla_a) $ 上任给的坐标系的普通导数算符,则体现 $ \nabla_a $ 与 $ \partial_a $ 的差别的张量场 $ C^c{}_{ab} $ 称为 $ \nabla_a $ 在该坐标系的**克氏符**(Christoffel symbol),记作 $ \Gamma^c{}_{ab}, $ 即克氏符满足 \$\$ 
\Gamma^c{}_{ab}\omega_c=\partial_a\omega_b-\nabla_a\omega_b,\forall\omega_b \in \mathscr{F}(0,1).
 \$\$ 

- 设 $ v^\mu{}_{;\mu} $ 是与坐标系无关的张量 $ \nabla_a v^b $ 在坐标系中的分量, $ v^\nu{}_{,\mu}\equiv\partial_\mu v^\nu\equiv\frac{\partial v^\nu}{\partial x^\mu}, $ 则有
 \$\$ v^\nu{}_{;\mu}=v^\nu{}_{,\mu}+\Gamma^\nu{}_{\mu\sigma}v^\sigma,\omega_{\nu;\mu}=\omega_{\nu,\mu}-\Gamma^\sigma{}_{\mu\nu}\omega_\sigma,
 \$\$ 
其中 $ v^\nu,\omega_\nu $ 为任意矢量场和对偶矢量场在任一坐标基底的分量, $ \Gamma^\nu{}_{\mu\sigma} $ 是该系克氏符 $ \Gamma^b{}_{ac} $ 在该基底的分量. 

-  $ [u,v]^a=u^b\nabla_b v^a-v^b\nabla_bu^a, $ 其中 $ \nabla_b $ 是任一无挠导数算符. 

---

### 3.2 矢量场沿曲线的导数和平移

#### 矢量场沿曲线的平移

- 设 $ v^a $ 是沿曲线 $ C(t) $ 的矢量场, $ v^a $ 称为**沿 $ C(t) $ 平移的**,若 $ T^b \nabla_b v^a=0, $ 其中 $ T^a\equiv (\frac{\partial}{\partial t})^a $ 是曲线的切矢.

> $ T^b\nabla_b v^a $ 是矢量场 $ v^a $ 沿 $ T^b $ 的导数,于是上述定义也可以理解为: $ v^a $ 沿着 $ C(t) $ 平移的充要条件是它沿着 $ T^b $ 的导数为零.

- 设曲线 $ C(t) $ 位于坐标系 $ \{x^\mu\} $ 的坐标域内,曲线的参数式为 $ x^\mu(t) $ .令 $ T^a\equiv (\frac{\partial}{\partial t})^a $ ,则沿 $ C(t) $ 的矢量场 $ v^a $ 满足
 \$\$ 
T^b\nabla_b v^a=(\frac{\partial}{\partial x^\mu})^a(\frac{d\nu^\mu}{dt}+\Gamma^\mu{}_{\nu\sigma}T^\nu v^\sigma).
 \$\$ 

- 曲线上一点 $ C(t_0) $ 以及该点的一个矢量决定唯一的沿曲线平移的矢量场,

#### 与度规相适配的导数算符

- 流形 $ M $ 上选定度规场 $ g_{ab} $ 后,存在唯一的 $ \nabla_a $ 使得 $ \nabla_ag_{bc}=0, $ 称 $ \nabla_a $ 为**与 $ g_{bc} $ 适配的导数算符**.

> $ \nabla_a g_{bc}=0\Leftrightarrow \nabla_a g^{bc}=0. $ 

> 欧氏空间中与欧式度规 $ \delta_{ab} $ 相适配的导数算符只有一个,即笛卡尔坐标系 $ \{x^\mu\} $ 的普通导数算符 $ \partial_a, $ 亦是普通矢量场论中熟知的 $ \mathbf{\nabla} $ .

- 设 $ \nabla_a $ 与 $ g_{bc} $ 相适配,则 $ \nabla_a $ 在该坐标系的克氏符 $ \Gamma^c{}_{ab} $ 在该系的分量 $ \Gamma^\sigma{}_{\mu\nu} $ 满足:
 \$\$ \Gamma^\sigma{}_{\mu\nu}=\dfrac{1}{2}g^{\sigma\rho}(g_{\rho\mu,\nu}+g_{\nu\rho,\mu}-g_{\mu\nu,\rho}). \$\$ 

>  $ \Gamma^\sigma{}_{\mu\nu} $ 既依赖于 $ M $ 上选定的 $ \nabla_a $ 又依赖于坐标系.

- 设 $ g_ab $ 是流形 $ M $ 上的洛伦兹度规场, $ p,q\in M, $ 则 $ p,q $ 之间的光滑类空(类时)曲线为测地线当且仅当其线长取极值.


#### 矢量场沿曲线的导数与沿曲线的平移的关系

- 欧氏空间中 $ p $ 点的矢量 $ \tilde{\mathbf{v}} $ 称为 $ q $ 点的矢量 $ \mathbf{v} $ **平移**至 $ p $ 点的结果,若两者在同一笛卡尔系的分量相等.

- 欧氏空间中曲线 $ C(t) $ 上的矢量场 $ \mathbf{v} $ 沿线的导数 $ \dfrac{d\mathbf{v}}{dt} $ 定义为
 \$\$ 
\dfrac{d\mathbf{v}}{dt}:=\lim_{\Delta t\to 0}\dfrac{1}{\Delta t}(\tilde{\mathbf{v}} \mid _p-\mathbf{v}_p),\forall p\in C(t),
 \$\$ 
其中 $ \tilde{\mathbf{v}} \mid p $ 是把 $ \mathbf{v} \mid q $ ( $ q $ 为 $ p $ 在线上的邻点)平移至 $ p $ 点的结果, $ \Delta t\equiv t(q)-t(p). $ 

> 将 $ T^b\nabla_b v^a $ 称为 $ v^a $ 沿着 $ T^b $ 的导数,有时记作 $ \dfrac{D v^a}{dt}\equiv T^b\nabla_b v^a. $ 

- 设 $ v^a $ 是 $ (M,\nabla_a) $ 的曲线 $ C(t) $ 上的矢量场, $ T^b $ 是 $ C(t) $ 的切矢, $ p,q $ 是 $ C(t) $ 上的邻点
 \$\$ 
T^b\nabla_b v^a \mid _p=\lim_{\Delta t\to 0}\dfrac{1}{\Delta t}(\tilde{v}^a \mid _p-v^a \mid _p),
 \$\$ 
其中 $ \tilde{v}^a \mid _p $ 是 $ v^a \mid _q $ 沿 $ C(t) $ 平移至 $ p $ 点的结果, $ \Delta t\equiv t(q)-t(p). $ 

---

### 3.3 测地线

-  $ (M,\nabla_a) $ 上的曲线 $ \gamma(t) $ 教主**测地线**(geodesic),若其切矢 $ T^a $ 满足 $ T^b\nabla_b T^a=0. $ 

> 测地线的充要条件是其切矢沿线平移.
>欧氏(闵氏)空间中测地线方程的通解为 $ x^\mu(t)=a^\mu t+b^\mu,(a^\mu,b^\mu\text{为常数}) $ ,这是一条“直线”.

- 设 $ \gamma(t) $ 为测地线,则其重参数化 $ \gamma^\prime(t^\prime)=\gamma(t) $ 的切矢 $ T^{\prime a} $ 满足
 \$\$ T^{\prime b}\nabla_b T^{\prime a}=\alpha T^{\prime a}, \$\$  
其中 $ \alpha $ 为 $ \gamma(t) $ 上面某个函数.

- 设曲线 $ \gamma(t) $ 的切矢 $ T^a $ 满足 $ T^b\nabla_b T^a=\alpha T^a $ ,则存在 $ t^\prime=t^\prime(t) $ 使得 $ \gamma^\prime(t^\prime)=\gamma(t) $ 为测地线,能够使得曲线成为测地线的参数叫做曲线的**仿射参数**(affine parameter).

>满足 $ T^b\nabla_b T^a=\alpha T^a $ 的曲线叫做非仿射参数化的测地线.

- 若 $ t $ 是某测地线的仿射参数,则该线的任一参数 $ t^\prime $ 是仿射参数的充要条件为 $ t^\prime=at+b $ , $ a,b $ 为常数且 $ a\neq 0. $ 

- 流形 $ M $ 的一点 $ p $ 以及 $ p $ 点的一个矢量 $ v^a $ 决定(局部)唯一的测地线 $ \gamma(t) $ ,满足:

1.  $ \gamma(0)=p; $ 
2.  $ \gamma(t) $ 在 $ p $ 点的切矢等于 $ v^a $ .

- 测地线的线长参数必为仿射参数.

- 设 $ g_ab $ 是流形 $ M $ 上的洛伦兹度规场, $ p,q\in M, $ 则 $ p,q $ 之间的光滑类空(类时)曲线为测地线当且仅当其线长取极值.

> - 设 $ g_{ab} $ 正定, $ C $ 是 $ p,q $ 之间长度极小的一条曲线,则它必为测地线;但是 $ p,q $ 之间的测地线却未必长度极小.测地线长度取极小值的充要条件是线上不存在共轭点对.
> - 闵氏时空中两点之间(类时)直线段最长;两点之间的类时线为最长线的充要条件是它为测地线.
> - 对任意时空中有类时联系的两点:
>   - 两点间的最长线是类时测地线;
>   - 两点之间的类时测地线未必是最长线(对于闵氏时空一定是);
>   - 两点之间没有最短类时线.

---

### 3.4 黎曼曲率张量

#### 黎曼曲率的定义和性质 

- 称 $ (\nabla_a\nabla_b-\nabla_b\nabla_a) $ 为导数算符 $ \nabla_a $ 的**对易子**(commutator).导数算符 $ \nabla_a $ 的无挠性保证了其对函数的作用结果为零,但对其他型张量作用的结果未必为零.

- 定理
 
 1. 设 $ f\in \mathscr{F},\omega_a\in \mathscr{F}(0,1) $ ,则有
  \$\$ (\nabla_a\nabla_b-\nabla_b\nabla_a)(f\omega_c)=f(\nabla_a\nabla_b-\nabla_b\nabla_a)\omega_c. \$\$ 
 2. 设 $ \omega_c,\omega^\prime\in \mathscr{F}(0,1),\omega_c^\prime \mid _p=\omega_c \mid _p, $ 则有
  \$\$ [(\nabla_a\nabla_b-\nabla_b\nabla_a)\omega_c^\prime] \mid _p=[(\nabla_a\nabla_b-\nabla_b\nabla_a)\omega_c] \mid _p. \$\$  


>
  \$\$ (\nabla_a\nabla_b-\nabla_b\nabla_a):\underset{p\text{点的对偶矢量(0,1)}}{\underline{\omega_c \mid _p}}\xrightarrow{linear}\underset{p\text{点的(0,3)型张量}}{\underline{[(\nabla_a\nabla_b-\nabla_b\nabla_a)\omega_c] \mid _p}} \$\$ 
>这表明 $ (\nabla_a\nabla_b-\nabla_b\nabla_a) $ 对应于一个(1,3)型张量.

- 导数算符 $ \nabla_a $ 的**黎曼曲率张量场**(Riemann curvature tensor) $ R_{abc}{}^d $ 由下式定义:
 \$\$ (\nabla_a\nabla_b-\nabla_b\nabla_a)\omega_c=R_{abc}{}^d\omega_d,\forall \omega_c\in\mathscr{F}(0,1). \$\$ 

> 黎曼张量场反映导数算符的非对异性,是描述 $ (M,\nabla_a) $ 的内禀性质的张量场,反映流形 $ M $ 在指定联络 $ \nabla_a $ 后的“内禀弯曲性”.
>
黎曼张量为零的度规(如欧式、闵氏度规)称为**平直度规**(flat metric),相应的空间称为**平直时空**.\
> 
> > 证明见P77页

- 定理
1.  $ (\nabla_a\nabla_b-\nabla_b\nabla_a)v^c=-R_{abc}{}^dv^d,\forall v^c\in\mathscr{F}(1,0). $ 
2.  $ \forall T^{c_1\cdots c_k}{}_{d_1\cdots d_l}\in \mathscr{F}(k,l) $ ,有
 \$\$ 
\begin{aligned}
(\nabla_a\nabla_b&-\nabla_b\nabla_a)T^{c_1\cdots c_k}{}_{d_1\cdots d_l}\\&=-\sum\limits_{i=1}^kR_{abe}{}^{c_i}T^{c_1\cdots e\cdots c_k}{}_{d_1\cdots d_l}\\&+\sum\limits_{j=1}^lR_{abd_j}{}^{e}T^{c_1\cdots  c_k}{}_{d_1\cdots e\cdots d_l}
\end{aligned}
 \$\$ 

- 黎曼曲率张量满足的性质:
1.  $ R_{abc}{}^d=-R_{bac}{}^d $ ;
2. 循环恒等式: $ R_{[abc]}{}^d=0 $ ;
3. 比安基恒等式: $ \nabla_{[a}{R_{bc]}}_d{}^e=0 $ ;
4. 若 $ M $ 上有度规场 $ g_{ab} $ 且 $ \nabla_ag_{bc}=0 $ ,则可以定义 $ R_{abcd}\equiv g_{de}R_{abc}{}^e $ ,且 $ R_{abcd} $ 还满足 $ R_{abcd}=R_{cdab}=-R_{abdc} $ .

- 给定 $ (0,4) $ 型张量 $ R_{abcd} $ ,通过缩并可以得到(0,2)型张量 $ g^{bd}R_{abcd}=R_{abc}{}^b:=R_{ac} $ ,称为**里奇张量**(Ricci tensor),而
 $ g^{ac}R_{ac} :=R $ 称为**标量曲率**(scalar curvature).

- 对于维数 $ n \geqslant 3 $ 的广义黎曼空间,**外尔张量**(Weyl tensor) $ C_{abcd} $ 定义为
 \$\$ 
C_{abcd}:=R_{abcd}-\dfrac{2}{n-2}(g_{a[c}R_{d]b}-g_{b[c}R_{d]a}) +\dfrac{2}{(n-1)(n-2)}R g_{a[c}g_{d]b}. \$\$  

外尔张量具有如下性质:

1.  $ C_{abcd}=-C_{bacd}=-C_{abdc}=C_{cdab}; $ 
   
2.  $ C_{[abc]d}=0; $  
   
3.  $ C_{abcd} $ 的各种迹为零,即 $ g^{ac}C_{abcd}=0. $ 

- 广义黎曼空间的**爱因斯坦张量** $ G_{ab} $ 由下式定义:
 \$\$ G_{ab}:=R_{ab}-\dfrac{1}{2}Rg_{ab}, \$\$ 
爱因斯坦张量满足
 \$\$ \nabla^a G_{ab}\equiv g^{ac}\nabla_cG_{ab}=0. \$\$ 

#### 由度规计算黎曼曲率

1.任选坐标系后,度规分量 $ g_{\mu\nu} $ 便是已知量. 根据式 \$\$ \Gamma^\sigma{}_{\mu\nu}=\dfrac{1}{2}g^{\sigma\rho}(g_{\rho\mu,\nu}+g_{\nu\rho,\mu}-g_{\mu\nu,\rho}), \$\$ 
从已知的 $ g_{\mu\nu} $ 求出所有的非零 $ \Gamma^\sigma{}_{\mu\nu} $ ;

2. 代入下式得到黎曼张量的坐标分量:
 \$\$ R_{\mu\nu\sigma}{}^\rho=\Gamma^\rho{}_{\mu\sigma,\nu}-\Gamma^\rho{}_{\nu\sigma,\mu}+\Gamma^\lambda{}_{\sigma\mu}\Gamma^{\rho}{}_{\nu\lambda}-\Gamma^\lambda{}_{\sigma\nu}\Gamma^{\rho}{}_{\mu\lambda}. \$\$  
3. 代入下式得到里奇张量的坐标分量:
 \$\$ R_{\mu\sigma}=R_{\mu\nu\sigma}{}^\nu=\Gamma^\nu{}_{\mu\sigma,\nu}-\Gamma^\nu{}_{\nu\sigma,\mu}+\Gamma^\lambda{}_{\mu\sigma}\Gamma^{\nu}{}_{\lambda\nu}-\Gamma^\lambda{}_{\nu\sigma}\Gamma^{\nu}{}_{\lambda\mu}. \$\$  

---

### 3.5 内禀曲率和外曲率

- 把流形镶进高一维流形所定义的曲率叫做“外曲率”.
- “内禀弯曲性”的“弯曲”反映的是如下三个等价性质:
1. 导数算符的非对易性;
2. 矢量平移的曲线依赖性;
3. 存在初始平行后来不平行的测地线.

---

## 第4章 李导数、Killing场和超曲面

### 4.1 流形间的映射

#### 两种映射

- 设 $ M,N $ 为流形, $ \phi:M\to N $ 为光滑映射, $ \mathscr{F}_M,\mathscr{F}_N $ 分别代表 $ M,N $ 上光滑函数的集合, $ \mathscr{F}_M(k,l) $ 与 $ \mathscr{F}_N(k,l) $ 分别代表 $ M,N $ 上光滑 $ (k,l) $ 型张量场的集合.

1. **拉回映射**(pull back): $ \phi^*:\mathscr{F}_N\to\mathscr{F}_M $ 定义为
 \$\$ (\phi^*f) \mid _p:=f \mid _{\phi(p)},\forall f \in \mathscr{F}_N,p\in M, \$\$ 即 $ \phi^*f=f\circ \phi $ .

> $ \phi^*:\mathscr{F}_N\to\mathscr{F}_M $ 是线性映射,且有 $ \phi^* (fg)=\phi^*(f) \phi^*(g),\forall f,g \in\mathscr{F}_N. $ 

2.  $ \forall p\in M, $ 定义**推前映射**(push forward) $ \phi_{*}:V_p\to V_{\phi(p)} $ 如下: $ \forall v^a\in V_p, $  定义其像    $ \phi_{*}v^a\in V_{\phi(p)} $ 为
  \$\$ (\phi_*v)(f):=v(\phi^*f),\forall f \in \mathscr{F}_N. \$\$ 

>  $ \phi_* v^a $ 是 $ \phi(p) $ 点的矢量,也称为 $ \phi $ 的**切映射**.

#### 定理
1.  $ \phi_*:V_p\to V_{\phi(p)} $ 是线性映射.
2.  $ C(t) $ 是 $ M $ 中的曲线, $ T^a $ 为曲线在 $ C(t_0) $ 点的切矢,则 $ \phi_*T^a\in V_{\phi(C(t_0))} $ 是曲线 $ \phi (C(t_0)) $ 点的切矢,即曲线切矢的像是曲线像的切矢.

#### 两种映射的延拓

1. 拉回映射可以按照如下方式延拓至 $ \phi^*:\mathscr{F}_N(0,l)\to\mathscr{F}_M(0,l) $ :
 $ \forall T\in\mathscr{F}_N(0,l), $ 定义
 \$\$ \begin{aligned}
(\phi^*T)&_{a_1\cdots a_l} \mid _p(v_1)^{a_1}\cdots(v_l)^{a_l}
\\&:=T_{a_1\cdots a_l} \mid _{\phi(p)}(\phi_*v_1)^{a_1}\cdots(\phi_*v_l)^{a_l},\\
&\forall p \in M,v_1,\cdots,v_l\in V_p.
\end{aligned} \$\$   

> 拉回映射 $ \phi^* $ 能把 $ N $ 上的 $ (0,l) $ 型张量场变为 $ M $ 上的同型张量场,是场到场的映射.

2.  $ \forall p \in M, $ 推前映射 $ \phi_* $ 可以按如下方式延拓至 $ \phi_*:\mathscr{F}_{V_p}(k,0)\to \mathscr{F}_{V_{\phi(p)}}(k,0) $ ,即 $ \phi_* $ 是把 $ p $ 点的 $ (k,0) $ 型张量变为 $ \phi(p) $ 点的同型张量的映射: $ \forall T\in \mathscr{F}_{V_p}(k,0), $ 其像 $ \phi_*T\in\mathscr{F}_{V_{\phi(p)}}(k,0) $ 由下式定义:
 \$\$ 
\begin{aligned}
&(\phi_*T)^{a_1\dots a_k}(\omega^1)_{a_1}\cdots (\omega^k)_{a_k}\\
&:=T^{a_1\dots a_k}(\phi^*\omega^1)_{a_1}\cdots (\phi^*\omega^k)_{a_k},\\
&\forall \omega^1,\cdots,\omega^k\in V^*_{\phi(p)},
\end{aligned}
 \$\$ 
其中 $ (\phi^*\omega )_a $ 定义为 $ (\phi^* \omega)_a v^a:=\omega_a(\phi_*v)^a,\forall v^a \in V_p $ .

> 推前映射 $ \phi_* $ 只把 $ M $ 中一点 $ p $ 的 $ (k,0) $ 型张量变为其像点 $ \phi(p) $ 的同型张量.

**微分同胚映射 $ \phi:M\to N $ 存在两种观点:**

1. **主动观点**:认为 $ \phi $ 是点的变换以及由此导致的张量变换,即 \$\$ p\to\phi(p);T_p\to \phi_{*}T_{\phi(p)}; \$\$ 
2. **被动观点**,认为点 $ p $ 以及其上的所有张量 $ T $ 都没变, $ \phi:M\to N $ 的后果是坐标系有了变换,从 $ \{x^\mu\} $ 变为 $ \{x^{\prime\mu}\}. $  

-  $ (\phi_*^T)^{\mu_1\cdots\mu_k}{}_{\nu_1\cdots\nu_l} \mid _{\phi(p)}=T^{\prime\mu_1\cdots\mu_k}{}_{\nu_1\cdots\nu_l} \mid _p,\forall T\in\mathscr{F}_M(k,l), $ 式中左边是新点 $ \phi(p) $ 的新张量 $ \phi_*T $ 在老坐标系 $ \{y^\mu\} $ 的分量,右边是老点 $ p $ 的老张量 $ T $ 在新坐标系 $ \{ x^{\prime \mu}\} $ 
的分量.

---

### 4.2 李导数

#### 李导数的定义与性质

- 定义

 $ \mathscr{L}_vT^{a_1\cdots a_k}{}_{b_1\cdots b_l}:=\lim\limits_{t\to 0}\dfrac{1}{t}\left(\phi_t^*T^{a_1\cdots a_k}{}_{b_1\cdots b_l}-T^{a_1\cdots a_k}{}_{b_1\cdots b_l}\right) $ 
称为张量场 $ T^{a_1\cdots a_k}{}_{b_1\cdots b_l} $ 沿着矢量场 $ v^a $ 的**李导数**(Lie derivative).

> 李导数是由 $ \mathscr{F}_M(k,l) $ 到 $ \mathscr{F}_M(k,l) $ 的线性映射,而且 $ \mathscr{L}_v $ 同缩并可以交换顺序.

- 性质:
   $ \mathscr{L}_vf=v(f),\forall f \in \mathscr{F} $ . 

  #### 适配坐标系
- 定义:\
设 $ \{x^1,x^2\} $ 为坐标系,
  选定矢量场 $ v^a $ 的积分曲线为 $ x^1 $ 坐标线,再相当任意地选定另一组与这组曲线横截的曲线作为 $ x^2 $ 坐标线.如此得到的坐标系称为矢量场 $ v^a $ 的适配坐标系.

- 定理:
1. 张量场 $ T^{a_1\cdots a_k}{}_{b_1\cdots b_l} $ 沿 $ v^a $ 的李导数在 $ v^a $ 的适配坐标系的分量
   \$\$ (\mathscr{L}_vT)^{\mu_1\cdots\mu_k}{}_{\nu_1\cdots\nu_l}=\dfrac{\partial T^{\mu_1\cdots\mu_k}{}_{\nu_1\cdots\nu_l}}{\partial x^1}. \$\$ 

  > 上式左边在坐标变换时满足张量变换律而右边则否,故不能改写为张量等式.
 
2.  \$\$ \mathscr{L}_vu^a=[v,u]^a=v^b\nabla_bu^a-u^b\nabla_bv^a,\forall u^a,v^a\in\mathscr{F}(1,0), \$\$ 其中 $ \nabla_a $ 为任一无挠导数算符.
3.  \$\$ \mathscr{L}_v\omega_a=v^b\nabla_b\omega_a+\omega_b\nabla_av^b,\forall v^a\in\mathscr{F}(1,0),\omega_a\in\mathscr{F}(0,1), \$\$ 其中 $ \nabla_a $ 为任一无挠导数算符.

4. \$\$ 
\begin{aligned}
\mathscr{L}_vT^{a_1\cdots a_k}{}_{b_1\cdots b_l}&=v^c\nabla_cT^{a_1\cdots a_k}{}_{b_1\cdots b_l}\\
&-\sum\limits_{i=1}^kT^{a_1\cdots c \cdots a_k}{}_{b_1\cdots b_l}\nabla_c v^{a_i}\\
&+\sum\limits_{j=1}^lT^{a_1 \cdots a_k}{}_{b_1\cdots c\cdots b_l}\nabla_{b_j} v^{c}
,
\end{aligned}
 \$\$ 
 $ \forall T\in\mathscr{F}(k,l),v \in \mathscr{F}(1,0),\nabla_a $ 为任一导数算符.

---
### 4.3 Killing 矢量场

#### 等度规映射

微分同胚 $ \phi:M\to M $ 称为**等度规映射**,简称**等度规**(isometry),若 $ \phi^*g_{ab}=g_{ab} $ (保度规性).

>  $ \phi:M\to M $ 为等度规映射当且仅当 $ \phi^{-1}:M\to M $ 为等度规映射.

#### Killing场

- 定义:\
 $ \xi^a $ 为Killing矢量场的充要条件是 $ \xi^a $ 满足如下的Killing方程: \$\$ \nabla_a\xi_b+\nabla_b\xi_a=0, \$\$ 
  或者 $ \nabla_{(a}\xi_{b)}=0 $ 或者 $ \nabla_a\xi_b=\nabla_{[a}\xi_{b]} $ ,其中 $ \nabla_a $ 满足 $ \nabla_ag_{bc}=0 $ .

- 定理:
1. 若存在坐标系 $ \{x^\mu\} $ 使得 $ g_{ab} $ 的全部分量满足 $ \dfrac{\partial g_{\mu\nu}}{\partial x^1}=0 $ ,则 $ (\dfrac{\partial}{\partial x^1})^a $ 是坐标域上的Killing矢量场.
2. 设 $ \xi^a $ 是Killing矢量场, $ T^a $ 为测地线的切矢,则 $ T^a\nabla_a(T^b\xi_b)=0, $ 即 $ T^b\xi_b $ 在测地线上为常数.
3.  $ (M,g_{ab}) $ 上最多有 $ \frac{n(n+1)}{2} $ 个独立的Killing矢量场, $ n\equiv dim M $ .即 $ M $ 上所有Killing矢量场的集合作为矢量空间的维数小于等于 $ \frac{n(n+1)}{2} $ .
   
> 一个Killing矢量场代表 $ (M,g_{ab}) $ 的一个对称性,具有 $ \frac{n(n+1)}{2} $ 个独立Killing矢量场的广义黎曼空间称为最高对称空间.

4，设 $ \{x,t\} $ 是二维闵氏空间 $ (\mathbb{R}^2,\eta_{ab}) $ 的洛伦兹坐标系, $ \phi_\lambda:\mathbb{R}^2\to\mathbb{R}^2 $ 是伪转动Killing场 $ \xi^a\equiv t(\dfrac{\partial}{\partial x})^a+x(\dfrac{\partial}{\partial t})^a $ 对应的单参等度规群的一个群元(即以 $ \lambda\in \mathbb{R} $ 刻画的那个等度规映射),则由 $ \phi_\lambda $ 诱导的坐标变换 $ \{x,t\}\mapsto\{x^\prime,t^\prime\} $ 是洛伦兹变换.

5. 设 $ \{x^\mu\} $ 是 $ (\mathbb{R}^n,\eta_{ab}) $ 的洛伦兹坐标系,则 $ \{x^{\mu\prime} \} $ 也是洛伦兹坐标系的充要条件是它由 $ \{x^\mu\} $ 通过等度规映射 $ \phi:\mathbb{R}^n\to\mathbb{R}^n $ 诱导而成.

### 4.4 超曲面


   
   


   
   