## 53.1 数量积
##### **定理**： #向量代数的数量积
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>
> $$1\text{)几何表示: }\mathbf{a}\cdot\mathbf{b}=\mid\mathbf{a}\mid\mid\mathbf{b}\mid\cos\alpha $$
> $$2\text{)代数表示:}\quad\mathbf{a}\cdot\mathbf{b}=\mathbf{a}_xb_x+\mathbf{a}_yb_y+\mathbf{a}_zb_z$$
> $$3\text{)运算规律:}\quad 交换律：\mathbf{a}\cdot\mathbf{b}=\mathbf{b}\cdot\mathbf{a} \quad \text{分配律: }\mathbf{a\cdot(b+c)=a\cdot b+a\cdot c}$$
> $$4\text{)几何应用:}\quad 求模：|\mathbf{a}|=\sqrt{\mathbf{a}\cdot\mathbf{a}}\cdot\mathbf{a} \quad \text{求夹角: }\cos\alpha=\frac{\mathbf{a}\cdot\mathbf{b}}{|\mathbf{a}||\mathbf{b}|}\quad \text{判定两向量垂直:}\mathbf{a\perp b\Leftrightarrow a\cdot b=0}$$

## 53.2 向量积
##### **定理**： #向量代数的向量积
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>
> $1. \text{几何表示:}\quad\mathbf{a}\times\mathbf{b}\text{ 是一向量}.\quad\text{模}:\mid\mathbf{a}\times\mathbf{b}\mid=\mid\mathbf{a}\mid\mid\mathbf{b}\mid\sin\alpha$
> $2. \text{代数表示:}\quad{\mathbf{a}\times\mathbf{b}}=\begin{vmatrix}\mathbf{i}&\mathbf{j}&\mathbf{k}\\a_x&a_y&a_z\\b_x&b_y&b_z\end{vmatrix}$
> $3. i) a\times b= - ( b\times a) \quad ii)分配律：a\times(b+c)=a\times b+a\times c$
> $4. 运算规律：i)求同时垂直于 a 和 b 的向量: a×b\quad ii)求以 a 和 b 为邻边的平行四边形面积:S=|a×b|\quad iii)判断两向量平行：\mathbf{a//b}\Leftrightarrow\mathbf{a\times b}=0$

**解释**
+ 几何表示 `->` 右手法则 `->` 垂直于 $a,b$ 向量的一个直线；
+ 注意：
	+ 数量积满足交换律，向量积不满足交换律； 

## 53.3 混合积
##### **定理**： #向量代数的混合积
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> 
> 基本表述：$\left[ abc \right] = (a \times b) \cdot c$
> 定义： $$\ a = a_xi + a_yj + a_zk \\ b = b_xi + b_yj + b_zk \\ c = c_xi + c_yj + c_zk$$
> 性质：
> （1）$$(a\times b)\cdot c = a\cdot(b\times c) = b \cdot (c\times a)$$
> $$轮换对称性：(abc)=(bca)=(cab)\quad 交换变号：(\mathbf{abc})=-(\mathbf{acb})$$
> （2）$$\begin{aligned}(a\times b)\cdot c=-(b\times a)\cdot c\\(a\times b)\cdot c=-(c\times b)\cdot a\\(a\times b)\cdot c=-(a\times c)\cdot b\end{aligned}$$
> （3）$$a\text{、}b\text{、}c\text{三向量共面}\Leftrightarrow[abc]=0$$
> 几何意义：
> 1. 向量的混合积 $[abc]=(a\times b)\cdot c$ 的绝对值在数值上等于以向量 a、b、c 为棱的平行六面体的体积
> 2. $V_\text{平行六面体}=|\mathrm{(abc)}|$
