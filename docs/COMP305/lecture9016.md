# Lecture 16
<font size="4">Hongye Qian</font> 

## Topic 6 Perceptron
### Convergence of Perceptron Learning Algorithm
- For Boolean functions: Linear Separability (Informal Definition)  
  - There exists a line (plane) such that:  
    - All inputs producing a **1** for the function lie on one side of the line (plane).  
    - All inputs producing a **0** lie on the other side of the line (plane).  

- **Definition**: Two sets $P$ and $N$ of points in an $n$-dimensional space are called **(absolutely) linearly separable** if:  
  - There exists a real vector $w = (w_1, \cdots, w_n)$ such that:  
    - For every point $a' = (a_1, \cdots, a_n) \in P$, $w^T a' > 0$.  
    - For every point $a' = (a_1, \cdots, a_n) \in N$, $w^T a' < 0$.  

![22a4c3267eac737f76baf98809f9c57.png](https://s2.loli.net/2024/11/28/lBDy3P26SmoWgQ8.png)  
like this picture.  

If in the data set $D$, 1-label subset and 0-label subset are linearly separable, we say $D$ is (absolutely) **linearly separable**.

### $D$ is linearly separable, try to find $D'$is also that case
![9524a0e5cfc3732daf357632f485865.png](https://s2.loli.net/2024/11/28/nYJXVphLyEiQN3r.png)
1. 原始数据集 $D$ 中的每个样本 $a'$ 被扩展为 $[1, a_1, a_2, \dots, a_n]$，即在 $a'$ 的开头加上了偏置项 $a_0 = 1$，形成新的数据集 $D'$：
   $$
   D' = \{[1, a_1, a_2, \dots, a_n] \mid a' \in D\}
   $$

2. 原假设是 **原始数据集 $D$ 是线性可分的**，即存在一个超平面：
   $$
   w^T a' > 0, \forall a' \in P \quad \text{(正类)}
   $$
   $$
   w^T a' < 0, \forall a' \in N \quad \text{(负类)}
   $$
   在扩展数据集中：
   - 正类样本 $P$ 的扩展点 $[1, a']$ 仍然满足 $w^T a > 0$；
   - 负类样本 $N$ 的扩展点 $[1, a']$ 仍然满足 $w^T a < 0$；
   - 如果这个成立，就是线性可分的。

3. 算法如何找到的：
   - 初始权重 $w = [w_0, w_1, \dots, w_n]$，其中 $w_0$ 对应扩展数据集的偏置项。
   - 针对 $D'$ 中每个扩展样本 $a = [1, a_1, a_2, \dots, a_n]$，判断当前权重 $w$ 是否能够正确分类：
   - **正类样本**：如果 $w^T a < 0$，则权重更新为：
    $$
    w = w + a
    $$
   - **负类样本**：如果 $w^T a \geq 0$，则权重更新为：
    $$
    w = w - a
    $$
   - 为什么这么更新？因为error那个公式对于二分任务：
$$
e_j^k = t_j^k - X_j^k =
\begin{cases}
1, & t_j^k = 1, X_j^k = 0 \\
0, & t_j^k = X_j^k \\
-1, & t_j^k = 0, X_j^k = 1
\end{cases}
$$
$$
   \Delta w_{ji}^k = C \cdot e_j^k \cdot a_i^k
$$


    - 每次更新权重后，模型逐渐将正类和负类的扩展样本推向正确的分类区域。看代码中那个地方的公式。

### Geometric Interpretation
![aa34cd87c732cb37c5758826cd9065e.png](https://s2.loli.net/2024/11/28/8JoxpGb9PRdAtBE.png)
- **We plot all the input patterns $a$.**
  - **Red arrows** denote the points in $P$,
  - **Blue arrows** denote the points in $N$,
  - **Thick black line** denotes the barrier of $w^{*T} a = 0$.
- <u>We can do this, due to the definition of absolutely linear separability. </u>

markdown
复制代码
- Meanwhile, $w^{*T} a = 0$ means that the vector $w^*$ and the barrier are *orthogonal*.   同时，$w^{*T} a = 0$ 表明向量 $w^*$ 和该分隔边界是*正交*的。
- Questions: There are two orthogonal vectors. Why don’t we choose the dashed one?
  For all $a \in P$, $w^{*T} a > 0$ means that the angle between the vector $w^*$ and every input pattern in $P$ is *less than 90°*. 对于所有 $a \in P$，$w^{*T} a > 0$ 意味着向量 $w^*$ 与 $P$ 中每个输入模式之间的夹角 *小于 90°*。对于N大于*90°*。我的理解是这里和向量的乘法刚好对上了$P$是正的，$N$是负的。
  $$
  a \cdot b = \|a\|\|b\| \cos\langle a, b \rangle
  $$
![9c1d1b0ef48f535d5a4550bfdfdb7de.png](https://s2.loli.net/2024/11/28/ktpAiBaPDeLsudU.png)
- **This algorithm means that**  
  - In each iteration, we *"pull"* the weight vector $w$ closer to $P$, *"push"* the weight vector $w$ farther to $N$, if misclassified.  
  - Until the angle between $w$ and each pattern in $P$ is **less than 90°**, and the angle between $w$ and each pattern in $N$ is **greater than 90°**.  
  - In both cases, $w$ gets closer to $w^*$.  


### Convergence Analysis
- 我们假设扩展数据集 $D'$ 仅由正类集合 $P$ 组成。这一假设通过如下方式实现：
  - 将负类集合 $N$ 的所有点取负，定义一个新的集合 $P'$：  
  $P' = -N, \quad P = P \cup P'$
  - Why?
    通过这一操作，可以将数据集中所有点统一到正类集合 $P$ 的框架下，这样可以：
    - 简化问题为仅处理正类集合 $P$；
    - 消除对负类 $N$ 的直接处理，方便分析。
- 我们假设扩展点 $a' \in D'$ 的范数满足：
$\|a'\| = 1$
    - Why?
    通过对数据集中的点进行归一化处理（即将每个点除以其自身的范数），可以确保：
        - 每个扩展点 $a'$ 的大小统一，这样只需要关注点的方向；
        - 对于原始点 $a$，归一化后的范数满足：
  $\|a\| = \sqrt{2}$
- Proof 请看lec16 P36，懒得写了。












