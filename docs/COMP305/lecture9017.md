# Lecture 17
<font size="4">Hongye Qian</font> 

## Topic 5 Multi-Layer Perceptron
-  the perceptron learning algorithm can finally converge for the data set that is linearly separable.

### A example that is not linearly separable : The XOR problem
![e6f26a131e487430234e76132cbb9cf.png](https://s2.loli.net/2024/11/28/PtTuq4fvIFRSjy1.png)
***
Proof:
XOR is **NOT** Linearly Separable

Assume there is a line defined as:
$$
w_0 + w_1 a_1 + w_2 a_2 = 0
$$
such that the points satisfy the following conditions:

#### Conditions:
1. Two **red points** satisfy:
   $$
   \begin{cases}
   w_0 + w_1 \times 0 + w_2 \times 1 > 0 \\
   w_0 + w_1 \times 1 + w_2 \times 0 > 0
   \end{cases}
   $$

2. Two **purple points** satisfy:
   $$
   \begin{cases}
   w_0 + w_1 \times 0 + w_2 \times 0 < 0 \\
   w_0 + w_1 \times 1 + w_2 \times 1 < 0
   \end{cases}
   $$

#### Implications:
Simplifying the above inequalities:
1. From the red points:
   $$
   w_2 > -w_0 \quad \text{and} \quad w_1 > -w_0 \quad \implies \quad w_1 + w_2 > -2w_0
   $$

2. From the purple points:
   $$
   w_0 < 0 \quad \text{and} \quad w_1 + w_2 < -w_0
   $$

#### Contradiction:
These conditions cannot all be true simultaneously, hence proving that **XOR is not linearly separable**
***
- 所以MP和感知学习都不适用，因为这俩都是基于binary的

### Hidden Neurons
- 隐藏神经元是指那些中间层的神经元，其输出不可直接对外部可见，但它们的存在可以：
    - 通过非线性转换，将原始数据映射到一个新的空间中。
    - 在新的空间中，使问题变得线性可分。


![162f7e2dbcc7b8ebba6f72d67b7edfd.png](https://s2.loli.net/2024/11/28/5wm7FgIDQTueUsG.png)
![a9cb806c68e949e5b1a605ba3952d7f.png](https://s2.loli.net/2024/11/28/3FxVSTK2LjYBEJa.png)
This  example introduces the idea of *Multilayer Perceptron*.

### Multilayer Perceptron
![d186fb938ee7b8f580bb06376e6f737.png](https://s2.loli.net/2024/11/28/spmVjIyiA65UeGP.png)`
- A multilayer perceptron (**MLP**) is a layered architecture of neurons, where:
  - All the neurons are divided into $l$ subsets, each set is called a layer. 所有的神经元被分成 $l$ 个子集，每个子集称为一层。
  - There are only connections between two adjacent layers. 仅相邻两层之间有连接。
- Usually, **the neurons within a layer are not connected to each other**, though some neural models make use of this kind of architecture.  通常情况下，**同一层内的神经元彼此没有连接**，但有些神经网络模型会利用这种架构。
- The first layer is **the input layer** *(We don’t usually count it)*;
- The last layer is **the output layer**.
- All other layers with no direct connections from or to the outside are called **hidden layers**.
- We consider the fully-connected architectures in this module, that is, every neuron from one layer is connected to all neurons in the following layer.
- Each connection is associated with a real weight and a real bias.
- Inputs are real. Outputs are real.
- The input is processed and propagated from one layer to the next, until the final result is computed.  
  输入被处理并从一层传播到下一层，直到计算出最终结果。
  
- This process represents the **forward propagation**.  
  这个过程称为**前向传播**。
  
- For simplicity, from now we assume **the biases in the network are all zero**.  
  为了简化起见，从现在起我们假设**网络中的所有偏置都为零**。

### Forward Propagation
![5cbe1ddf049430aa8aea470ef1ea69a.png](https://s2.loli.net/2024/11/28/Xao7lLfQGqz9Mvx.png)
- The difference of the multilayer perceptron, compared to the single layer one, is that the output value $X^1$ of the first layer is **not** the output value of the multilayer perceptron any more.  
  多层感知器与单层感知器的区别在于，第一层的输出值 $X^1$ **不再**是多层感知器的输出值。

- The output value $X^1$ of the first layer is the *input* to the next layer.  
  第一层的输出值 $X^1$ 是下一层的*输入*。
- Example: First neuron in the first hidden layer
$$
S_1 = \sum_{i=1}^{n^0} w_{1i}^1 x_i^0 + \underbrace{b_1^1}_{=0} = \sum_{i=1}^{n^0} w_{1i}^1 x_i^0
$$

$$
X_1^1 = f_1^1(S_1) = f_1^1\left( \sum_{i=1}^{n^0} w_{1i}^1 x_i^0 \right)
$$
1. **加权和 $S_1$**：
   - $S_1$ 是第一层神经元的加权和，计算时考虑每个输入 $x_i^0$ 的权重 $w_{1i}^1$，并加上偏置 $b_1^1$。 Ps:上一层的输出是下一层的输入。
   - 在这里，假设偏置 $b_1^1 = 0$，因此公式被简化。

2. **输出 $X_1^1$**：
   - 第一层神经元的输出 $X_1^1$ 是通过激活函数 $f_1^1$ 对加权和 $S_1$ 进行非线性变换得到的。
   - 激活函数 $f_1^1$ 通常用于引入非线性能力。

We start from **the first hidden layer**. The output of the $j$-th neuron in the first layer is:

$$
X_j^1 = f_j^1(S_j^1) = f_j^1\left(\sum_{i=0}^{n^0} w_{ji}^1 x_i^0\right) \triangleq F_j^1(w_j^1, x_i^0), \quad j = 1, \cdots, n^1
$$

We can then describe the above relation in a vector form:

$$
X^1 = F^1(w^1, X^0)
$$
依此类推：
### Formula

The computation for each layer in a neural network can be represented as:

$$
X^1 = F^1(w^1, X^0)
$$

$$
X^2 = F^2(w^2, X^1)
$$

$$
X^3 = F^3(w^3, X^2)
$$

$$
\vdots
$$

$$
X^l = F^l(w^l, X^{l-1})
$$
The output of the neural network can be expressed as:

$$
X^l = F^l\left(w^l, F^{l-1}\left(w^{l-1}, \dots, F^1\left(w^1, X^0\right)\right)\right)
$$

$$
X = X^l = F(w^l, w^{l-1}, \dots, w^1, X^0) = F(w^l, w^{l-1}, \dots, w^1, a)
$$
逐层嵌套
### A Running Example
See lecture 17 P32 