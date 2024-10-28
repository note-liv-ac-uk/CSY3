# Lecture 03
<font size="4">Hongye Qian</font> 

### Topic2 A basic abstract model for a biological neuron
#### 1. Weights of Connections
- Neuron gets **fired** if it has received from the presynaptic neurons a **summary impulse**, which **is above a certain threshold**.  
**神经元的激活**：当神经元从前突触神经元接收到超过特定阈值的综合脉冲时，它会被激活。
-  Signal from a single synapse may sometime overcome the threshold and push a neuron to fire an action potential, but other synapses can achieve this only by simultaneously delivering their signals: **Some inputs are more important!**  
**信号的重要性**：虽然来自单个突触的信号有时可以使神经元达到激活阈值并产生动作电位，但其他突触可能需要同时传递信号才能达到这一效果。这表明某些输入比其他输入更重要。
-  Therefore, input from every synapse, or “connection”, to the neuron in the abstract model must be assigned with some value w, called connection strength or weight of connection, to describe the importance of a connection.  
**权重的分配**：每个突触或“连接”到神经元的输入都必须被赋予一个权重值（w），这个值被称为连接强度或连接权重，用以描述连接的重要性。
#### 2. Abstract Model of a Neuron 
![d2f073e2af8a1384f497694d411d17c.png](https://s2.loli.net/2024/10/14/LI18jp5FyvZAqu3.png)
- Shown is an abstract neuron j with n+1 inputs.
  **神经元结构**：展示了一个具有 n+1 个输入的抽象神经元 j。这里 "+1" 通常表示偏置项（bias），它是一个常数输入（通常为1），通过权重$w_{j0}$与神经元输出相连。
- Each input i transmits a real value $a_i$.
   **输入信号**：每个输入𝑖传输一个实数值$a_i$。
- Each connection is assigned with the weight $w_{ji}$.
   **输入总和与阈值比较**：所有输入信号与相应权重的乘积之和 \( $S_j = \sum_i w_{ji} a_i$ \)（\( $i$ \) 表示输入序号）进行比较。如果 \( $S_j$ \) 大于阈值，输出 \( $x_j$ \) 为 $1$；否则为 $0$。

***偏置量***：在神经网络中，偏置量（bias）是一个非常重要的概念。它作为一个可调整的参数，添加到输入的加权和中去影响神经元的激活状态。具体来说，偏置量是一个独立的输入，通常与权重一起在神经网络的训练过程中进行优化，以帮助模型更好地拟合数据。它可以用来调整激活阈值、避免对称性和模型退化等问题。

#### 3. Abstract Neuron vs. Biological Neuron: Components
- $a_0$, ..., $a_n$ vs. dendrites树突
- neuron body神经元细胞体the circle vs. soma体细胞
- OutputX vs. Axon轴突
- threshold阈值 vs. The excitation potential threshold激发电位阈值  
- Weights of input connections vs. presynaptic neurons突触前神经元
-  The abstract neuron is excited when weighted sum is above the threshold 0 vs. The biological neuron is excited when the signal density (spatial or temporal summation) is above the excitation potential threshold.
-  Output is either 1 or 0 vs. Only the spikes动作电位 are remembered.

#### 4. Summary
![119e5f19a15ccba7b84788570223e42.png](https://s2.loli.net/2024/10/14/59SXEwFQf4HOuJm.png)
![6b48b5fcbe6a372a740ede7a7d13414.png](https://s2.loli.net/2024/10/14/7WParcLhVOZNeCK.png)
















