# Lecture 14
<font size="4">Hongye Qian</font> 

## Topic 6 Perceptron
![8f5dc364a9fbf7500f0a9f151c66cbb.png](https://s2.loli.net/2024/11/22/FPLoxGnbXI49jl6.png)
- **Weights** $w_{ji}$ of connections between two layers **are changed** according to the **perceptron learning rule**, so the network is more likely to produce the **desired** output in response to certain inputs. 两层之间连接的**权重** $w_{ji}$ **根据感知机学习规则进行调整**，因此网络更可能对特定输入产生**期望的输出**。
- *The process of weights adjustment is called perceptron “learning” or “training”.* *权重调整的过程称为感知机的“学习”或“训练”。*
- The perceptron is trained by using a **training set** with **target outputs (labels)**.
  - **Training set**: a set of input patterns **repeatedly** presented to the network during training. **训练集**：在训练期间**反复**向网络提供的一组输入模式。
  - **Target/desired output (label)**: the pre-defined correct output of an input pattern in the training set. **目标/期望输出（标签）**：训练集中输入模式的预定义正确输出。
  - Every input pattern is used multiple times for training.
  - Input pattern in the set is **n-dimensional**! Note $a_0 = 1$.
  -  In unsupervised learning, no label is needed.
- In training, the output neuron first computes an output as:

  $$
  X_j = f(S_j) = 
  \begin{cases} 
  1, & S_j \geq 0 \\
  0, & S_j < 0 
  \end{cases}
  $$
  - The network outputs $X_j$ are then **compared to the desired outputs** specified in the training set and obtain the **error**.
- error of an output neuron:
$$
e_j = (t_j - X_j)
$$

- **The weights readjustment is done in such a way that the network is – on the whole – more likely to give the desired response next time.** 权重调整的方式使得网络整体上更有可能在下次给出期望的输出。
- **The goal of the training is to arrive at a single set of weights that allow each input in the training set to be mapped to the correct output by the network.** 训练的目标是找到一组权重，使训练集中的每个输入都能通过网络映射到正确的输出。

### Some details about Perceptron (from GPT)
- 感知机由三个部分组成：
  1. **输入层**：包含多个输入节点（例如 $a_1, a_2, \dots, a_n$），这些输入通过权重 $w_{ji}$ 连接到输出节点。
  2. **偏置节点**：$a_0=1$，通过权重 $w_{j0}$ 影响输出，作用是调整决策边界的位置。
  3. **输出层**：激活函数 $f$ 接收加权和的结果，输出最终的分类结果。
- 偏置项 $a_0=1$ 用于调节模型的输出，使其能够拟合具有非零偏移的数据。
- 训练过程：
1. **前向传播（Forward Propagation）**：
   - 输入节点的值通过权重和激活函数 $f$ 计算出输出 $X_j$。

2. **权重调整（Weight Adjustment）**：
   - 如果模型输出与目标输出不一致，则通过调整权重 $w_{ji}$ 来减少误差。
   - 更新公式为：
     $$
     w_{ji} \gets w_{ji} + \Delta w_{ji}
     $$
     其中，
     $$
     \Delta w_{ji} = \eta \cdot (y - \hat{y}) \cdot a_i
     $$
     - $\eta$ 是学习率，
     - $y$ 是目标输出，
     - $\hat{y}$ 是模型的实际输出。

3. **训练目标**：
   - 寻找一组权重，使所有训练集样本的输入映射到正确的输出。

### Weight updates
- step1: Compute the **"error"** of every connection for every output neuron:
   $$
   e_j^k = \left(t_j^k - X_j^k\right)
   $$

   where:
   - $t_j^k$: the target value for the $j$-th output neuron for the $k$-th input pattern in the data set. $t_j^k$：数据集中第 $k$ 个输入模式对应第 $j$ 个输出神经元的目标值。
   - $X_j^k$: the instant value for the $j$-th output neuron for the $k$-th input pattern. $X_j^k$：数据集中第 $k$ 个输入模式对应第 $j$ 个输出神经元的即时值。
- step2: **Update the weights**:
   $$
   w_{ji}^k = w_{ji}^k + \Delta w_{ji}^k
   $$

   where:
   $$
   \Delta w_{ji}^k = C \cdot e_j^k \cdot a_i^k
   $$

   **Perceptron Learning Rule!**

   According to the learning rule, a weight of connection changes **if and only if** both the input value and the error of the output are not equal to 0. 根据学习规则，只有当输入值和输出的误差都不为 0 时，连接的权重才会发生变化。
   - 看不懂的看等会例子吧
- **Perceptron Learning Rule**:
$$
\Delta w_{ji}^k = C \cdot e_j^k \cdot a_i^k
$$

As outputs and target values are binary:
$$
e_j^k = t_j^k - X_j^k =
\begin{cases}
1, & t_j^k = 1, X_j^k = 0 \\
0, & t_j^k = X_j^k \\
-1, & t_j^k = 0, X_j^k = 1
\end{cases}
$$

- The value of the **"learning rate"** $C$:
      - is usually set below 1.
      - determines the amount of correction made in a single iteration. 决定了单次迭代中的修正量。
- **网络的整体学习时间**受学习率 $C$ 的值影响：
  - **学习率较小时**，学习速度较慢； 
  - **学习率较大时**，学习速度较快。

### Network performance
- 使用**均方根误差 (Root-Mean-Square, RMS)** 衡量训练过程中网络的性能：
  $$
  \text{RMS} = \sqrt{\frac{\sum_{k=1}^r \sum_{j=1}^m \left(e_j^k\right)^2}{rm}}
  $$
  其中：
  - $r$: 数据集中样本的数量 (patterns)。
  - $m$: 输出神经元的数量。
  - $e_j^k$: 第 $k$ 个样本中第 $j$ 个输出神经元的误差，定义为：
    $$
    e_j^k = t_j^k - X_j^k
    $$
    - $t_j^k$: 第 $k$ 个样本中第 $j$ 个神经元的目标输出 (target value)。
    - $X_j^k$: 第 $k$ 个样本中第 $j$ 个神经元的实际输出 (instant value)。
  - RMS 误差反映了网络输出与目标输出之间的整体误差。
  - RMS 越小，说明网络性能越好，模型在训练集中拟合效果越佳
  - When RMS is closed to zero, we stop the training.
  - 外层（第一个）求和：计算整个训练集的误差。
  - 内层（第二个）求和：计算每个样本中所有输出神经元的误差。
  - As the target output values $t_j^k$ and the numbers $r$ and $m$ are constants, **the RMS error is a function of the instant outputs $X_j^k$ only.** 由于目标输出值 $t_j^k$ 以及数量 $r$ 和 $m$ 是常量，**RMS 误差仅仅是即时输出 $X_j^k$ 的函数。**
  - In turn, the **instant outputs** $X_j^k$ are also functions of the input values $a_i^k$, which are constants, and the weights $w_{ji}^k$: 进一步来说，**即时输出** $X_j^k$ 也是输入值 $a_i^k$（为常量）和权重 $w_{ji}^k$ 的函数
$$
X_j^k = f\left(\sum_{i=0}^n w_{ji}^k a_i^k\right) = \bar{f}_{a_k}\left(w_{ji}^k\right)
$$
  - Thus, RMS error can be represented as:
$$
\text{RMS} = F_D(w)
$$
where $w$ is the network weight and $D$ is the data set.
  - 公式推导：

1. RMS 定义公式:
$$
\text{RMS} = \sqrt{\frac{1}{r \cdot m} \sum_{k=1}^{r} \sum_{j=1}^{m} (t_j^k - X_j^k)^2}
$$

1. 即时输出的加权求和:
$$
S_j^k = \sum_{i=0}^{n} w_{ji} \cdot a_i^k
$$

1. 激活函数输出:
$$
X_j^k = f(S_j^k)
$$

1. 将即时输出代入 RMS 公式:
$$
\text{RMS} = \sqrt{\frac{1}{r \cdot m} \sum_{k=1}^{r} \sum_{j=1}^{m} \left(t_j^k - f\left(\sum_{i=0}^{n} w_{ji} \cdot a_i^k\right)\right)^2}
$$

1. RMS 表示为权重的函数:
$$
\text{RMS} = F_D(w)
$$
- The **best performance of the network** over a given data set $D$ corresponds to the **minimum of the RMS error**, and we adjust the weight of connections $w$ in order to reach the minimum **看步骤4那个式子。**
### Perceptron Learning Algorithm
![025afa471fee37a7e970ab7b4b5816e.png](https://s2.loli.net/2024/11/25/K37SHnx9d6vsECU.png)

### Network Performance
![379113e335b2fb06675f3036f83166e.png](https://s2.loli.net/2024/11/25/MDZd3S7WKBhOvLJ.png)
- Thus, RMS error can be represented as:
$$
\text{RMS} = F_D(w)
$$
where $w$ is the network weight, and $D$ is the data set.

**Learning curve**: dependency of the RMS error on the number of iterations.
- **Initially**, the adaptable weights are all set to small random values, and the network does not perform very well;
- **Performance improves during training**;
- **Finally**, the error gets close to zero, and training stops. We say the network has **converged**（收敛）.

 











