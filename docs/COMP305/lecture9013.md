# Lecture 13
<font size="4">Hongye Qian</font> 

### Unsupervised learning
- **无监督学习**是一种机器学习类型，其中算法**不会被提供任何预先分配的标签或训练数据的评分**。  
  因此，无监督学习算法必须首先**自我发现训练数据集中任何自然存在的模式**。**Unsupervised learning** is a type of machine learning in which the algorithm **is not provided with any pre-assigned labels or scores for the training data**.  
  As a result, unsupervised learning algorithms must first **self-discover any naturally occurring patterns** in that training data set.

- **Hebb规则**、**Oja规则**、**Kohonen规则**都是无监督学习规则。 **Hebb’s rule**, **Oja’s rule**, and **Kohonen rule** are all unsupervised learning rules.

## Topic6 Perceptron
- **Rosenblatt (1958)** explicitly considered the **problem of pattern recognition**, where a **“teacher”** is essential. (Consider the difference with unsupervised learning) 

- **A Perceptron** is a neural network that changes with **“experience”** using an **error-correction rule**. **感知机（Perceptron）**是一种神经网络，通过使用**误差校正规则**随着“经验”而变化。

- According to the rule, **weight of a neuron changes when it makes error response to the input presented to the network**. 根据该规则，**当神经元对输入的反应出错时，其权重会发生变化**。

#### Perceptron (1958)
![8f5dc364a9fbf7500f0a9f151c66cbb.png](https://s2.loli.net/2024/11/22/FPLoxGnbXI49jl6.png)

The simplest architecture of perceptron comprises one layer of idealised “neurons”, which we also sometimes call “units” of the network. 

- Syntax and Structure
  - One layer of inputs
  - One layer of output neurons in the perceptron.
  - The two layers are fully interconnected, i.e. every input neuron is connected to every output neuron. 
  - Semantically, a **perceptron** can be considered as a vector-valued function that maps the input:

  $$
  a = \{a_0, a_1, \cdots, a_n\}
  $$

    to the output:

    $$
  X = \{X_1, X_2, \cdots, X_m\}
  $$
  - Allows real inputs
![1d68057e0de3116c019849aed9d254a.png](https://s2.loli.net/2024/11/22/eCIDGSKEdYoNjB9.png)
  - Each output neuron has the **same inputs**, that is, the total input layer.  
  But individual outputs are with **individual connections and therefore have different weights** of connections.  Thus, we can consider each output independently.  For instance, let us consider the **j-th output neuron**. 每个输出神经元都有**相同的输入**，即整个输入层。但是，每个输出都有**独立的连接，因此具有不同的权重**。因此，我们可以独立地考虑每个输出。例如，让我们考虑**第 j 个输出神经元**。
  - The weighted input to the **j-th output neuron** is:

  $$
  S_j = \sum_{i=0}^{n} w_{ji} a_i,
  $$
  
  -  where **a₀** is a special input neuron with a fixed input value of **+1**.If we rename the weight of **$w_{j0}$** for the **$j-th$ output** as **$−θ_j$**, ...
  - The formula for the weighted input to the **j-th output neuron** can be expressed as:

  $$
  S_j = w_{j0}a_0 + \sum_{i=1}^{n} w_{ji}a_i
  $$

  - which can be rewritten as:

  $$
  S_j = -\theta_j + \sum_{i=1}^{n} w_{ji}a_i
  $$
  -  **a₀** is a special input neuron with a fixe input value of **+1**.  
  
  - With this trick, we have no need to set a threshold manually.  
  Now we can **train the threshold like weights**. 使用这一技巧，我们不需要手动设置阈值。现在我们可以像**训练权重一样训练阈值**。
  - The value **Xₖ** of the **j-th output neuron** depends on whether the weighted input is greater than **0**.

  $$
  X_j = f(S_j) = 
  \begin{cases} 
  1, & S_j \geq 0 \\
  0, & S_j < 0 
  \end{cases}
  $$

  - We call **f** the **activation function**.

### MP Neuron vs. Perceptron (Syntax and Semantics)
![54ea2c72ee893b8dd500ab646d35f28.png](https://s2.loli.net/2024/11/22/gTBAkLaphVWiEsQ.png)


- **感知机**包含一个特殊输入 $a_0 = 1$，通过可学习的权重和激活函数$f$ 间接管理阈值。  
- **MP神经元**直接使用阈值 $\theta$，无需特殊输入，根据输入总和是否超过 $\theta$ 来确定输出。  
- 感知机更灵活，可用于训练；MP神经元更简单，但适应性较差。
-  <u>MP neuron can only “describe”, but not “learn”. </u>

### Neuron Model in Hebb’s Rule vs. Perceptron
![a24f9d6b25d4fc10b8082167ebdbbd5.png](https://s2.loli.net/2024/11/22/Crjm2ci4DJIalbt.png)
- **感知机**：
  - 包含一个特殊输入 $a_0 = 1$，用于简化阈值管理。
  - 权重 $w_{j0}$ 被重定义为 $-\theta_j$，并通过激活函数 $f$ 计算输出：
  
    $$
    S_j = w_{j0}a_0 + \sum_{i=1}^{n} w_{ji}a_i
    $$

- **Hebb规则的神经元模型**：
  - 无特殊输入 $a_0$，直接使用阈值 $\theta$ 来决定输出 $X_j$。
  - 通过以下公式计算输入总和：
  
    $$
    S_j = \sum_{i=1}^{n} w_{ji}a_i
    $$

- **对比**：
  - 感知机更灵活，可学习权重和间接管理阈值。
  - Hebb规则模型更简单，直接依赖阈值 $\theta$。

### Recall Unsupervised Learning
![0bf64f9c33c7de51d114656ee39b334.png](https://s2.loli.net/2024/11/22/fMyi2neh7U6AFob.png)

### What can a Perceptron be used for?
- Similar to Hebb’s rule, we adjust **weights** (training) between two layers to learn knowledge from a given data set.  类似于Hebb规则，我们通过调整**权重**（训练）在两层之间从给定的数据集中学习知识。
- If the data set is unlabeled, we can train the perceptron network to cluster the inputs to different groups (**unsupervised learning**).如果数据集是未标记的，我们可以训练感知机网络将输入聚类到不同的组中（**无监督学习**）。

- If the data set is labeled, we can train the perceptron network to produce the **desired** output in response to certain inputs (**supervised learning**).


























