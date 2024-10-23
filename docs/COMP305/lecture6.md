# Lecture 6
<font size="4">Hongye Qian</font> 

### Topic 2 The McCulloch-Pitts Neuron (1943)
#### 1. Geometric Interpretation: 2D “OR”
![a4a8bce569682935f90bf3b542c835e.png](https://s2.loli.net/2024/10/23/scIom43iPSWOELg.png)
- 虚线分割了输入空间，展示了输出 1 和 0 的区域
- 分割线是$\sum_{i=1}^{2} a_i - 1=0$
- In other words, all inputs firing the neuron will be one side of the line, while all inputs inhibiting the neuron lie on the other side. 激发神经元的在一边，抑制神经元的在另一边。
#### 2. Geometric Interpretation: 2D “AND”
![440668862369074dd7b129e17d37e78.png](https://s2.loli.net/2024/10/23/gQIH8UEnYiyPjbf.png)
- For “AND” operation, the MP neuron above represents a decision maker separating the input space linearly with $\sum_{i=1}^{2} a_i - 2=0$

#### 3. Geometric Interpretation: Multiple Inputs Case
![5f190996d01a647e86a98ec7225e656.png](https://s2.loli.net/2024/10/23/Xoj1WefIMhSKumP.png)
- we have a plane.

#### 4. Representation Power of a single MP Neuron
- A single MP neuron can be used to represent some Boolean functions which are linearly separable.单个MP神经元可以表示一些线性可分的布尔函数。
- Linear separability (for Boolean functions): There exists a line (plane) such that all inputs which produce a 1 for the function lie on one side of the line (plane) and all inputs which produce a 0 lie on other side of the line (plane). 线性可分性是指存在一条直线（二维情况下）或一个平面（更高维度）可以将输出为1的所有输入和输出为0的所有输入分隔开。
- Plus, 布尔函数中的例子是逻辑“AND”和“OR”，它们是线性可分的。然而，像XOR（异或）这样复杂的逻辑则不是线性可分的。
- A counter example
  ![78f0738dd3105f554b9a59f140b5385.png](https://s2.loli.net/2024/10/23/Hz8cFytwGo4an5i.png)
某些情况下单个麦卡洛克-皮茨（MP）神经元无法实现特定的线性可分布尔函数。

#### 5. inhibitory connections
- 如图所示，只有输入 (0,1) 会激活神经元，而其他三种输入组合都不会激活。这种情况下，无法找到一条直线或平面能够将输出为1的点与输出为0的点线性分开。因此，此时神经元不再表现出线性分割的特性。

#### 6. Revisit definition
- 回顾一下之前的定义，下面的定义会有点绕
  Assume that $w_1=-1$, 定义如下:
  $S^{t-1} =
\begin{cases} 
-1, & a_1 = 1 \\
\sum_{i=2}^{n} w_i a_i^{t-1}, & a_1 = 0
\end{cases}
$
- 假如 $w_1$是-1的时候，$a_1=1$，神经元不会被激活，因为这时候$X^t=0$，所以把$S_{t-1}$定义为-1，这是一种抑制神经元的激活
- 当$a_1=0$时， $S_{t-1}$ 是从 i=2到n的其他输入的加权和。换句话说，其他输入决定了神经元是否会被激活。这时获得了线性边界时。
- 当我们获得了线性边界以后，我们就要考虑$a_1=1$，需要移除它对激活神经元。 人话：把$a_1=1$的点全去掉。
  
- Example
  以下存在inhibitory connections
  ![2367a2c184d9f8346ebfde4e7c8c7b4.png](https://s2.loli.net/2024/10/23/rGqjgteCPIyapfw.png)
  1. We first consider the revised neuron as above. 人话：把那个-1当成1
   ![cec081658585b18413e9e0c1515b8b7.png](https://s2.loli.net/2024/10/23/tX3kfhc9smr68eG.png)
  2. 找到了一个平面可以切割，$(a_1+a_2+a_3)=1$
  ![e678ec9de4ac205ddf1a88a5fdea3bb.png](https://s2.loli.net/2024/10/23/MWkaLuRv7xUsPQD.png)
  3. 把$a_1$的点全去掉，就得到了结果
  4. The inputs that fire the neuron are (0,1,1) , (0,0,1) , (0,1,0) .

- Another Example 看Lecture6 P36

#### 7. Summary
![169e169ad576208c2f0a8600595a20f.png](https://s2.loli.net/2024/10/24/eGvtTDsUS3ZbOjV.png)
  


