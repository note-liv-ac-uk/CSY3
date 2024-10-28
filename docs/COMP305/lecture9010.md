# Lecture 10
<font size="4">Hongye Qian</font> 
### Topic 4 Normalized Hebb’s Rule (Oja’s Rule)
#### 1. A Informal Explanation
在上一节课的例子中
Let the dataset $D = \{[1,0,1,0], [1,1,0,0]\}$,其中[1, 0, 1, 0]是t=0, t=1的输入，[1，1，0，0]是t=2时的输入。
By computing the “average value”： $\bar{a} = \frac{2 \times [1,0,1,0] + [1,1,0,0]}{3} = \left[1, \frac{1}{3}, \frac{2}{3}, 0 \right]$
从中我们可以看到第一个分量(1)是最重要的，第三个分量($\frac{2}{3}$)是第二重要的，依此类推。

#### 2. Normalized Hebb’s Rule (Oja’s rule)
- $w_i^{t+1} = w_i^t + \Delta w_i^t$   where $\Delta w_i^t = c a_i^t x^{t+1}$, 比hebb多了一个条件 Normalization: $\| w^t \| = 1$
- By normalization, the weights will not monotonously increase, but converge after, which reflects the predisposition to different inputs. It plays an important role in unsupervised learning or self organisation.  通过归一化，权重不会无限增加，而是趋于收敛，这反映了对不同输入的“适应性”或“倾向性”。该法则在无监督学习或自组织中扮演重要角色。
- 回顾Formulation of Hebb’s Rule for a single neuron，在lecture 8笔记的最后。

#### 3. Formulation of Normalized Hebb’s Rule (Oja’s rule)
![21b7ddc673e5d4365c6c24ee88af2b0.png](https://s2.loli.net/2024/10/27/3tLPJ7XyVloIbas.png)
- 比Hebb多出来一部Normalization
- Normalization:
  1. Compute the 2-norm of the vector $w^t$
   $\| w^t \|_2 = \sqrt{\sum_i (w_i^t)^2}$
  2. Normalize the weight of each connection $w_i^t$
   $w_i^t = \frac{1}{\| w^t \|_2} w_i^t$
  3. Check the following convergence criteria with a given small positive real $\max_i |w_i^t - w_i^{t-1}| \leq \delta$

#### 4. Alternative Version of Normalized Hebb’s Rule
![ff114a4e0361133c7c8f4a3dd318784.png](https://s2.loli.net/2024/10/27/Ltw2kRFDdcU8SWv.png)
- A running example, 看lecture 10 P25到结束讲的很清楚






