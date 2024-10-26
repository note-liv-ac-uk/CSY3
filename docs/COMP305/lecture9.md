# Lecture 8
<font size="4">Hongye Qian</font> 

### Topic 3 Hebb’s Rules
#### 1. ANN Learning Rules
![845cc26dece61888d5f6e9e8aa41255.png](https://s2.loli.net/2024/10/26/Dn25vJqdhI1W4pA.png)

#### 2. Running example
![e508c5112e3a0127668bae844b4e6d5.png](https://s2.loli.net/2024/10/26/3CzILQokTANaBSe.png)
- Round 0:
  ![51e766199f437b8e2212e2d42046d1c.png](https://s2.loli.net/2024/10/26/D4GP8nLpmOwRbij.png)
  1. Beginning: $C=1,t=0, w_1^0=1, w_2^0=1, w_3^0=1, w_4^0=1$, we suppose $a_1^0=1, a_2^0=0, a_3^0=1, a_4^0=0$
$S^0 = \sum_{i=1}^{4} w_i^0 a_i^0 \\
= w_1^0 \times a_1^0 + w_2^0 \times a_2^0 + w_3^0 \times a_3^0 + w_4^0 \times a_4^0 \\
= 1 \times 1 + 1 \times 0 + 1 \times 1 + 1 \times 0 = 2 \geq \theta
$ so the $X^1=1$
  1.  代入下面的公式：
   $\Delta w_i^0 = C a_i^0 X^1 \\w_i^1 = w_i^0+ \Delta w_i^0$
  $\Delta w_1^0 = 1 \times 1 \times 1 = 1, \quad w_1^1 = w_1^0 + \Delta w_1^0 = 1 + 1 = 2; \\
\Delta w_2^0 = 1 \times 0 \times 1 = 0, \quad w_2^1 = w_2^0 + \Delta w_2^0 = 1 + 0 = 1; \\
\Delta w_3^0 = 1 \times 1 \times 1 = 1, \quad w_3^1 = w_3^0 + \Delta w_3^0 = 1 + 1 = 2; \\
\Delta w_4^0 = 1 \times 0 \times 1 = 0, \quad w_4^1 = w_4^0 + \Delta w_4^0 = 1 + 0 = 1;
$
注意上面的权重已经发生变换了。The weights have been changed.
- Round 1: $t=1$
  ![4328cf0c614efde7a0656a44101ac78.png](https://s2.loli.net/2024/10/26/AixqcGrCO7EayMe.png)
  1. $S^1 = \sum_{i=1}^{4} w_i^1 a_i^1 \\
= w_1^1 \times a_1^1 + w_2^1 \times a_2^1 + w_3^1 \times a_3^1 + w_4^1 \times a_4^1 \\
= 2 \times 1 + 1 \times 0 + 2 \times 1 + 1 \times 0 = 4 \geq \theta
$ so the $X^2=1$
  1. 代入下面的公式:
  $\Delta w_i^1 = C a_i^1 X^2 \\
w_i^2 = w_i^1 + \Delta w_i^1
$
$\Delta w_1^1 = 1 \times 1 \times 1 = 1, \quad w_1^2 = w_1^1 + \Delta w_1^1 = 2 + 1 = 3; \\
\Delta w_2^1 = 1 \times 0 \times 1 = 0, \quad w_2^2 = w_2^1 + \Delta w_2^1 = 1 + 0 = 1; \\
\Delta w_3^1 = 1 \times 1 \times 1 = 1, \quad w_3^2 = w_3^1 + \Delta w_3^1 = 2 + 1 = 3; \\
\Delta w_4^1 = 1 \times 0 \times 1 = 0, \quad w_4^2 = w_4^1 + \Delta w_4^1 = 1 + 0 = 1;
$
注意权重的变化。 Please note the changes of weights.
- Round 2: $t=2$,这时候注意一下输入的四个$a_i^2$是$1, 0, 1, 0$,这个输入时随机的，不是固定不变的，ppt上在t=2的时候的输入就是1, 0, 1, 0
![94c5299932ded228fb3d3932581929c.png](https://s2.loli.net/2024/10/26/RkiCeMmXwaY5rAp.png)
  1. $S^2 = \sum_{i=1}^{4} w_i^2 a_i^2 \\
= w_1^2 \times a_1^2 + w_2^2 \times a_2^2 + w_3^2 \times a_3^2 + w_4^2 \times a_4^2 \\
= 3 \times 1 + 1 \times 1 + 2 \times 0 + 1 \times 0 = 4 \geq \theta$ so the $X^3=1$
  1. 代入以下公式：
   $\Delta w_i^2 = C a_i^2 X^3 \\
w_i^3 = w_i^2 + \Delta w_i^2$
$\Delta w_1^2 = 1 \times 1 \times 1 = 1, \quad w_1^3 = w_1^2 + \Delta w_1^2 = 3 + 1 = 4; \\
\Delta w_2^2 = 1 \times 1 \times 1 = 1, \quad w_2^3 = w_2^2 + \Delta w_2^2 = 1 + 1 = 2; \\
\Delta w_3^2 = 1 \times 0 \times 1 = 0, \quad w_3^3 = w_3^2 + \Delta w_3^2 = 3 + 0 = 3; \\
\Delta w_4^2 = 1 \times 0 \times 1 = 0, \quad w_4^3 = w_4^2 + \Delta w_4^2 = 1 + 0 = 1;
$
- **我这里写的有点快了，要是看不懂上lecture9 P13开始看**

#### 3. Meaning behind Hebb’s Rule
![d7131b0a5bc4e98c24bbff0fcb3e056.png](https://s2.loli.net/2024/10/26/OQnqVYIfpLolwi2.png)
-  **Intuition**: If two adjacent neurons always fire together, they should have strong relation (large weight)这其实就是一个例子解释了Lecture 8里的第3点的第二小点（笔记里）。

#### 4. Theory behind Hebb’s Rule
- Assumption 1: 
  $X^{t+1} = g(S^t) = H(S^t - \theta) = 
\begin{cases} 
1, & S^t \geq \theta; \\
0, & S^t < \theta.
\end{cases}
\quad \Rightarrow \quad
X^{t+1} = g(S^t) = \sum_i w_i^t a_i^t$
这个之前的笔记中有，激活函数被定义为越阶函数(Heaviside 函数)
- Assumption 2: All the inputs $a^t$ are from a given finite data set $D$ with the cardinality $N$. In each epoch, we train the neuron with all the inputs within the data set. We have infinite epochs. 所有输入$a^t$ 都来自一个有限数据集 $D$, 其基数为 $N$。也就是说，数据集 $D$由$N$个输入组成。在每个周期中，神经元会用数据集中所有的输入进行训练。我们有无限的训练周期，这意味着神经网络不断进行学习和调整。这也反映了Hebb的名言:"Cells that fire together, wire together"
- discrete form to the continuous form：
  discrete form : $\Delta w_i^t = C a_i^t X^{t+1}
$ 我们将$\Delta w_i^t$取极限，时间趋向于无穷小，左边写成$\frac{dw_i}{dt}$, 右边代入激活函数$X^{t+1} = g(S^t) = \sum_i w_i^t a_i^t$，因为现在t无限小，它时一种连续的概念, $X = \sum_i w_i a_i
$, 所以我们得到 $\frac{dw}{dt} = C a \left( \sum_i w_i a_i \right)$
- 为了更方便地进行向量化操作，可以将上面的公式转化为矩阵形式。将标量的加权和表示为矩阵乘法：
  输入向量 𝑎 可以写成： $[a_1, a_2, \ldots, a_n]^T$
  权重向量 𝑤 可以写成：$[w_1, w_2, \ldots, w_n]^T$
  所以我们得到: $\frac{dw}{dt} = C a a^T w$
- In each epoch, all the $N$ inputs within the data set are considered, thus we can use the average $\bar{a}$ over the data set as the increase rate, represented as $\bar{a} \bar{a}^T$ 这是从 Hebb 法则的连续矩阵形式进一步推导出来的。在每个训练周期中，使用数据集上的平均值来代替单个输入的外积，从而得到了这个更新的形式。
我们得到 $\frac{dw}{dt} = C \bar{a} \bar{a}^T w = \alpha w, \quad \text{with} \quad \alpha = C \bar{a} \bar{a}^T$
- Plus, The average $\bar{a}$ always exists, but we don’t know what it is. The “<u>average</u>” is the feature of the data set $D$  that is learnt by the Hebb’s rule.
- 此常微方程(ODE)的唯一解可以表示为：
  $W(t) = k_1 e^{\alpha_1 t} \delta_1 + k_2 e^{\alpha_2 t} \delta_2 + \cdots + k_m e^{\alpha_m t} \delta_m$
  其中$k_i$是初始条件决定的系数, $\delta_i$是矩阵$\alpha$的第$i$个特征向量, $\alpha_i$是矩阵$\alpha$的第$i$个特征值
  When the sufficient time has passed, that is, 𝑡 is large enough, 可以近似为: $W(t) \approx k^* e^{\alpha^* t} \delta^*$
  其中$\alpha^*$是矩阵的最大特征值， $\delta^*$是与最大特征值对应的特征向量。
  这表示当经过足够长时间后，系统的行为将主要由最大特征值对应的项来主导，其他项相对来说会变得不那么重要。这种现象被称为由最大特征值主导，也就是特征值的指数增长决定了整个系统的最终演化。
  输出的近似值为：$X(t) \approx k^* e^{\alpha^* t} \delta^* a$

- **PCA and Hebb**
  PCA（Principal Component Analysis，主成分分析），这与 Hebb 法则有很强的关联。通过最大特征值主导的概念可以看出，Hebb 法则实际上与寻找数据集中最大方差方向（即主成分）是相关的。这意味着通过 Hebb 学习规则，网络可以学习到数据的主要特征，这和 PCA 的目标是类似的。
- ![d7131b0a5bc4e98c24bbff0fcb3e056.png](https://s2.loli.net/2024/10/26/OQnqVYIfpLolwi2.png)
  **All the weights increase monotonously**: 这意味着所有的权重都会单调增加，即每次更新时权重的值都会增加，不会减少。这是 Hebb 学习规则的结果，因为每当输入和输出同时激活时，权重都会增加。
  **Finally, each weight will become large enough such that any activated input can fire the neuron alone** 最终，每个权重都会变得足够大，以至于单独一个被激活的输入就可以触发神经元的输出。这意味着当系统经过足够长的时间训练后，只要某个输入被激活（即输入为 1），就足以激活神经元，这也是 Hebb 学习规则的一种效果——它让网络学会强化激活路径，使得某些输入对输出的影响变得更加显著.













