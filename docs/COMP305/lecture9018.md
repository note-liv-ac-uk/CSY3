# Lecture 18
<font size="4">Hongye Qian</font> 

## Topic 5 Multi-Layer Perceptron
### Gradient Decent and Activation Function Design
### Error Function for a Single Input
![5cbe1ddf049430aa8aea470ef1ea69a.png](https://s2.loli.net/2024/11/28/Xao7lLfQGqz9Mvx.png)
The output error of a multilayer perceptron for the $k$-th input pattern is **a half of the squared error**:  $E^k$ 表示多层感知器对第 $k$ 个输入样本的输出误差。误差采用**平方误差的一半**形式。

$$
E^k = \frac{1}{2} \sum_{j=1}^m \left(e_j^k\right)^2 = \frac{1}{2} \sum_{j=1}^m \left(t_j^k - X_j^k\right)^2
$$

The performance of multilayer perceptron= $\frac{1}{2}$the total squared error
$$
E = \sum_{k=1}^r E^k = \frac{1}{2} \sum_{k=1}^r \sum_{j=1}^m \left(e_j^k\right)^2 = \frac{1}{2} \sum_{k=1}^r \sum_{j=1}^m \left(t_j^k - X_j^k\right)^2
$$
- During the training stage, the input value $a$ to the network are the input vectors of the training set, which are **constant parameters** for the process.

- Therefore, the **MLP error function $E$** is a function of the weights of connections only:

$$
E = \sum_{k=1}^r E^k = \frac{1}{2} \sum_{k=1}^r \sum_{j=1}^m \left(e_j^k\right)^2 = \frac{1}{2} \sum_{k=1}^r \sum_{j=1}^m \left(t_j^k - F_j(w^l, w^{l-1}, \dots, w^1, a^k)\right)^2 = E(W)
$$
- 因为error仅仅受输入和权重影响，输入被视作是常数，所以它可以被视作为权重的一个函数。
- <u>The better the MLP performs, the smaller the MLP error function $E$is.</u>
- Thus MLP learning can be considered as the optimization problem: $
\min_W E(W)
$, 可以用梯度下降来实现（想必大家都很熟悉这个东西），比如SGD
### Gradient Decent
![0e4a61cf3ee82306b2e5ec4ce9ae4ed.png](https://s2.loli.net/2024/11/29/FXcJePuO4wxY3lv.png)
Gradient descent is based on the observation that if the multi-variable function $F(x)$ is defined and differentiable in a neighborhood of a point $a$, then $F(x)$ decreases fastest if one goes from $a$ in the direction of the negative gradient of $F$ at $a$, $-\nabla F(a)$. It follows that, if

$$
a' = a + \gamma(-\nabla F(a)) = a - \gamma \nabla F(a)
$$

For a $\gamma \in \mathbb{R}^+$ small enough, then $F(a) \geq F(a')$
***
解释：

- 梯度下降的依据：
- 如果一个多变量函数 $F(x)$ 在某点 $a$ 的邻域内定义并且可微，那么函数 $F(x)$ 在 $a$ 点的变化最快的方向是负梯度方向 $-\nabla F(a)$。

- 更新公式：
梯度下降法通过以下公式更新变量：
$$
a' = a + \gamma(-\nabla F(a)) = a - \gamma \nabla F(a)
$$
其中：
- $a$：当前点。
- $\nabla F(a)$：函数 $F(x)$ 在 $a$ 点的梯度。
- $\gamma$：学习率（一个正的小值，控制更新步长大小）。

    条件：
- 当 $\gamma$ 足够小时，新点 $a'$ 的函数值是小于或等于当前点的函数值：
$$
F(a) \geq F(a')
$$

这表示每次更新后，函数值都朝着最小值方向变化。
***
对应的等高线图：
![578777d4cee8aaaf3994a32f0fe3a68.png](https://s2.loli.net/2024/11/29/bMUT7CdEv3lDqgk.png)
#### Gradient Descent

Gradient descent is based on the observation that if the multi-variable function $F(x)$ is defined and differentiable in a neighborhood of a point $a$, then $F(x)$ decreases fastest if one goes from $a$ in the direction of the negative gradient of $F$ at $a$, $-\nabla F(a)$. It follows that, if

$$
a_{n+1} = a_n - \gamma \nabla F(a_n)
$$

For a $\gamma \in \mathbb{R}^+$ small enough, then $F(a_n) \geq F(a_{n+1})$.

---

With this observation, one starts with an initial guess $x_0$ for a local minimum of $F$, and considers the sequence $x_0, x_1, x_2, \cdots$ such that

$$
x_{n+1} = x_n - \gamma \nabla F(x_n).
$$

We can have monotonic sequence:
$$
F(x_0) \geq F(x_1) \geq F(x_2) \geq \cdots
$$

So hopefully, the sequence $\{x_n\}$ converges to the desired local minimum $x^*$, where:
$$
\nabla F(x^*) = 0
$$
- 解释：$$
x_{n+1} = x_n - \gamma \nabla F(x_n)
$$

- **$x_n$**：当前点。
- **$\nabla F(x_n)$**：当前点的梯度（导数）。
- **$\gamma$**：学习率，控制每次更新的步长。

---

单调性
如果学习率 $\gamma$ 选择得当，每次更新后目标函数的值单调减少：
$$F(x_0) \geq F(x_1) \geq F(x_2) \geq \cdots$$

---

收敛性
理想情况下，迭代点序列 $\{x_n\}$ 将会收敛到目标函数的局部最小值 $x^*$，满足：
$$\nabla F(x^*) = 0$$
***
### Learning of a Multilayer Perceptron
- Gradient descent method addresses the issue of how to update weights.
- One of the most popular techniques is called **error backpropagation**(反向传播),  
where the error of output neurons is propagated back to derive the weight adjustment of a given hidden neuron, based on how much the neuron contributes to the output error. 根据隐藏神经元对输出误差的贡献程度，将输出神经元的误差反向传播，以计算隐藏神经元的权重调整。


- The **backpropagation** algorithm updates the weights of connections $w$ **computationally efficiently** based on the method of **gradient descent**. 反向传播是深度学习中训练神经网络的核心算法，结合了梯度下降方法，能够高效优化网络权重，从而提升模型性能。
- Gradient descent method addresses the issue of how to update weights.
- The backpropagation algorithm makes the weight updating efficient.
- The backpropagation 𝑤,𝑤 ,⋯,𝑤 ,𝑎 algorithm looks for the minimum of the error function 𝐸 in the space of weights of connections 𝑤 using the method of gradient descent.
- The gradient of the multi-variable function $E$ is defined as:

$$ \nabla E = \left( \frac{\partial E}{\partial w_{11}^1}, \cdots, \frac{\partial E}{\partial w_{n_1 n_0}^1}, \frac{\partial E}{\partial w_{11}^2}, \cdots, \frac{\partial E}{\partial w_{n_2 n_1}^2}, \cdots, \frac{\partial E}{\partial w_{11}^l}, \cdots, \frac{\partial E}{\partial w_{n_l n_{l-1}}^l} \right) $$

$\frac{\partial E}{\partial w_{ji}^h}$ 表示误差函数 $E$ 对权重 $w_{ji}^h$ 的偏导数。这是 $E$ 相对于第 $h$ 层中第 $j$ 个神经元和前一层（第 $h-1$ 层）中第 $i$ 个神经元之间连接权重的偏导数。
-  Vector ∇𝐸 is called gradient of the error function 𝐸, and it points in the direction along which 𝐸 increases most rapidly.
-   **We would like to go in the opposite direction to most rapidly minimize 𝐸.**
- Therefore, during the **iterative process of gradient descent**, each weight of connection, including the hidden ones, is updated:

$$w_{ji}^h = w_{ji}^h + \Delta w_{ji}^h, \quad \text{where } \Delta w_{ji}^h = -C \frac{\partial E}{\partial w_{ji}^h}$$

Here $C$ represents the learning rate as before. 
-  Since calculus-based methods of minimization depends on the taking of derivatives, their application to network training requires the error function 𝑬 be a differentiable function (almost everywhere). 函数至少在绝大多数地方要求是可微的
### Generic sigmoidal activation function
The sigmoidal function is defined as:

$$f(S) = \frac{\alpha}{1 + e^{-\beta S + \gamma}} + \lambda$$
- It has four parameters: $\alpha$, $\beta$, $\gamma$, $\lambda$.
- It is monotonically increasing. 它是**单调递增**的。
- It has the shape of the s-curve, which is commonly used for learning processes. 其形状为 S 曲线，常用于学习过程的建模。
![0d4536d7c66595f6768b688763e7d8d.png](https://s2.loli.net/2024/11/29/gZjBpsXMoOhYn14.png)
- The parameter $\beta$ has the most significant effect on the slope of this curve:
  - A small value of $\beta$ corresponds to a gradual curve increase, while its large value corresponds to a steep increase. 较小的 $\beta$ 值对应曲线的逐渐增长。较大的 $\beta$ 值对应曲线的陡峭增长。
  - The case $\beta = \infty$ corresponds to a hard-limiting step function. 当 $\beta = \infty$ 时，曲线变为硬限制阶跃函数（hard-limiting step function）。
  - The product $\alpha\beta$ defines the **steepness** of the curve. 参数 $\alpha\beta$ 的乘积决定了曲线的**陡峭度**。

- The product $\alpha\beta$ defines the **steepness** of the curve.
- The parameter $\gamma$ causes a shifting along the horizontal axis and is usually equal to zero. 参数 $\gamma$ 控制曲线在横轴上的平移，通常为零。
- The parameters $\alpha$ and $\lambda$ define the range limits for scaling purposes. 参数 $\alpha$ 和 $\lambda$ 用于定义缩放范围的上下限。
- See some examples on lec.18 P38
### Learning of a Multilayer Perceptron
*Generic sigmoidal activation function:*
$$f(S) = \frac{\alpha}{1 + e^{-\beta S + \gamma}} + \lambda$$

*Its derivative:*
$$f'(S) = \frac{df}{dS} = \frac{\beta}{\alpha} \cdot (f(S) + \lambda)(\alpha + \lambda - f(S))$$

*Explanation:*
It is straightforward to compute the derivative at any particular value of variable $S$ without actual differentiation,  
if the value of the activation function itself is known for that value of $S$. 如果已知激活函数在某特定 $S$ 值处的值，可以直接计算该点的导数，而无需实际进行微分操作。
- This feature of the sigmoid function is used for back propagation of corrections to weights of hidden neurons during multiple layer perceptron training process. 
- If all activation functions $f(S)$ in the network are differentiable, then we can use the **chain rule** to calculate the partial derivative of the error function $E$ with respect to the weight of a specific connection.














