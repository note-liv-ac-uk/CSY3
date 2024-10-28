# Lecture 04
<font size="4">Hongye Qian</font> 

### Topic 2 The McCulloch-Pitts Neuron (1943)



- a binary, discrete-time input 神经元以二进制、离散时间输入为模型。这意味着神经元接收的输入是0或1（二进制）并且是在离散的时间间隔内。
- with **excitatory** and **inhibitory** connections and an **excitation threshold**.

Ps: The network of such elements was **the first model** to tie the study of neural networks to **the idea of computation in its modern sense**.

![93c996aec27a44292d0863cbf6c39ee.png](https://s2.loli.net/2024/10/23/flhtKsWxXg4pG7M.png)

- **Discretization**: Comparable to a refractory period (assumed to be the same for each neuron). **No Zeno executions!** 这里指的是神经元处理信号的时间是离散的，类似于生物神经元的不应期，每个神经元假定具有相同的不应期。这防止了所谓的“Zeno行为”，即在极短的时间内执行无限次操作的情况。
- **Fixed time stepsize:** The impulse travels with a nearly uniform velocity in a biological neural system. 神经脉冲以近乎均匀的速度传播，这意味着在模型中信号传递的时间间隔是固定的，与生物神经系统中的信号传播类似。
- Thus, the McCulloch-Pitts neuron operates on a discrete time scale, t= 0, 1, 2, 3, …


#### 1.Why use binary input?

- Comparable to the fact that **only spikes are propagated** in biological neural networks.
- The types of the input and the output of a MP neuron are thus **unified**.

#### 2.Why +1 for excitatory and -1 for inhibitory type connection?

- +1 for excitatory type connection 兴奋性突触会释放神经递质，使得接收神经元的膜电位向阈值移动，增加发放动作电位的可能性。因此，模型中将兴奋性连接的权重设置为正值（+1），以反映这种增加激活概率的效果。(Cerebral pyramidal cell) Lecture4 P20
- -1 for inhibitory type connection. 抑制性突触通过释放不同的神经递质，使得接收神经元的膜电位远离阈值，减少发放动作电位的可能性。在模型中，抑制性连接的权重设为负值（-1），模拟这种抑制效果。(Stellate cell ) Lecture4 P21

#### 3.Threshold

- There is an excitation threshold *θ* associated with the neuron. 每个神经元都设有一个兴奋阈值 *θ*，这是神经元开始产生输出信号之前所需达到的最小输入信号的总和。只有当所有输入信号的加权总和iwiai​​超过这个阈值时，神经元才会激活并输出信号 $X^t$。
- Similar to the basic abstract neuron, *θ* is comparable to the potential threshold in a biological neuron. 这个阈值概念与生物神经元的行为类似。在生物神经元中，只有当细胞体收到足够的电信号，使得膜电位达到某个特定阈值时，神经元才会发放动作电位（信号）。这个阈值确保了神经元不会对低强度的随机信号反应，从而在神经系统中引入了一定程度的噪声抑制。

#### 4. MP Neuron: Computation

- $x^t=1$ if and only if $s^{t-1}=\sum_{i}{w_ia_i^{t-1}}\geq\theta$
- $w_i\geq0$, $\forall a_i^{t-1}>0$指的是所有激活的输入（即输入值大于0）都与非负权重相连接。这意味着，只有当输入是积极的（即存在输入），并且这些输入的权重也是积极的，才可能导致神经元的激活。
- $S^{t-1}$:  **instant state** of the neuron
- The stateSt-1of the MP neuron does not depend on the previous state of the neuron itself, but is simply computed by $\sum_{i}{w_ia_i^{t-1}=\ f(t-1)}$


#### 5.Activation Function

- **神经元的输出**Xt：神经元的输出是其内部状态 st-1的函数，可以表述为一个离散时间函数。这里$X^t=X\left(t\right)=g\left(S^{t-1}\right)=g\left(f\left(t-1\right)\right)$，其中 g 是阈值激活函数。
- **阈值激活函数 g**：阈值函数 g定义为：

$g(S^{t-1}) = H(S^{t-1} - \theta) = 
\begin{cases} 
1 & \text{if } S^{t-1} \geq \theta \\
0 & \text{if } S^{t-1} < \theta 
\end{cases}
$


Other functions see lecture 4 P28

Comparison with Different Models
![310df0cfb7159c3e6199e44038033fc.png](https://s2.loli.net/2024/10/23/cFDlrKHxXZCEvIu.png)
