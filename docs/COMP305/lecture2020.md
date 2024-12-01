# Lecture 20
<font size="4">Hongye Qian</font> 

### Backpropagation
![8a9bf744ea25cd03480b2bd4748fcf3.png](https://s2.loli.net/2024/12/01/QnM6XVCwptIcGT9.png)
- The closer the connection is to the output, the simpler the formula of the partial derivative of its weight is. 
-  There are some overlap between two formulas, indicating it is possible to store the overlap to avoid duplicate computation.

### Formula simplification
我感觉ppt上的公式推导就是两眼一黑，就是推。以下是我尝试解释清楚的推导。
- 原公式：
$$\frac{\partial E}{\partial w_{j_0 i_0}^l} = \begin{cases} \left(X_{j_0}^{l_0} - t_{j_0}\right) \cdot \left(f_{j_0}^{l_0}\right)'(S_{j_0}^{l_0}) \cdot X_{i_0}^{l_0-1}, & \text{When } l = l_0 \\ \sum_{j=1}^{n^l} \left(X_j^l - t_j\right) \cdot \left(f_j^l\right)'(S_j^l) \cdot \sum_{i=1}^{n^{l-1}} w_{ji}^{l-1} \cdot \left(... \cdot \left(f_{j_0}^{l_0}\right)'(S_{j_0}^{l_0}) \cdot X_{i_0}^{l_0-1}\right), & \text{When } l \neq l_0 \end{cases}$$

-咱们先看这个公式：
$$\left(X_{j_0}^{l_0} - t_{j_0}\right) \cdot \left(f_{j_0}^{l_0}\right)'(S_{j_0}^{l_0}) \cdot X_{i_0}^{l_0-1}$$
- $\left(X_{j_0}^{l_0} - t_{j_0}\right)$这个表示的是这个节点的误差
- $\left(f_{j_0}^{l_0}\right)'(S_{j_0}^{l_0})$这个表示的是这个节点的激活函数的导数
- $X_{i_0}^{l_0-1}$这个表示的是前一个节点的输出值
- 这一部分的公式就是对一个特定节点的误差对某个权重的影响。但是，这只考虑了这个特定节点。
***
然后是老师进行rewrite的公式：
- 改成了以下形式（刚刚那个公式）:
$$\sum_{j'=1}^{n^{l_0}} \left(X_{j'}^{l_0} - t_{j'}\right) \cdot \left(f_{j'}^{l_0}\right)' \left(S_{j'}^{l_0}\right) \cdot \frac{\partial S_{j'}^{l_0}}{\partial w_{j_0i_0}^{l_0}}$$
- $\sum_{j'=1}^{n^{l_0}}$ 表示现在是对这一层的每一个节点进行考虑
- 对于每个节点来说，误差对权重的依赖关系需要拆解出来。因为误差来自于最后的输出，而每个权重的影响是通过层与层之间的输入来间接影响的。为了更清楚地描述这种影响，我们使用了链式法则来把每一部分的变化明确地表达出来。
就是这玩意$\frac{\partial S_{j'}^{l_0}}{\partial w_{j_0i_0}^{l_0}}$
节点的输入是权重和前一层的输出的乘积，因此对这个权重求偏导时，结果就是前一层的输出（因为其他部分是常数）。
**简而言之，第二种就是在考虑整层所有节点的误差**
$$\frac{\partial E}{\partial w_{j_0i_0}^{l_0}} = \begin{cases} \sum_{j'=1}^{n^{l_0}} \left(X_{j'}^{l_0} - t_{j'}\right) \cdot \left(f_{j'}^{l_0}\right)' \left(S_{j'}^{l_0}\right) \cdot \frac{\partial S_{j'}^{l_0}}{\partial w_{j_0i_0}^{l_0}}, & \text{if } l = l_0, \\ \sum_{j=1}^{n^l}\left(X_j^l - t_j\right) \cdot \left(f_j^l\right)' \left(S_j^l\right) \cdot \sum_{i=1}^{n^{l-1}}w_{ji}^{l-1} \cdot\left( \dots \cdot \left(f_{j'}^{l_0}\right)' \left(S_{j'}^{l_0}\right) \cdot \frac{\partial S_{j'}^{l_0}}{\partial w_{j_0i_0}^{l_0}} \right), & \text{if }l \neq l_0.\end{cases}$$
- 然后可以归并成以下公式：
$$\frac{\partial E}{\partial w_{j_0i_0}^{l_0}} = \sum_{j=1}^{n^l} \left(X_j^l - t_j\right) \cdot \left(f_j^l\right)' \left(S_j^l\right) \cdot \sum_{i=1}^{n^{l-1}} w_{ji}^{l-1} \cdot \left( \dots \cdot \left(f_{j'}^{l_0}\right)' \left(S_{j'}^{l_0}\right) \cdot \frac{\partial S_{j'}^{l_0}}{\partial w_{j_0i_0}^{l_0}} \right)$$
***
Step2: Rewrite the formula in a matrix form
![b2b1df5650e5d94ef2cb3b5ac679e6e.png](https://s2.loli.net/2024/12/01/sVnUQlK9hqkIHxw.png)
The objective of this step is to derive the relation between the partial derivatives between two layers.
***
1. $$\nabla_{X^l} E \triangleq \left( \frac{\partial E}{\partial X_1^l} \cdots \frac{\partial E}{\partial X_{n^l}^l} \right) = \left( X_1^l - t_1 \cdots X_{n^l}^l - t_{n^l} \right)$$
This is the gradient of the 𝑙-th layer.

- 然后我们来替换$\left(f_{j_0}^{l_0}\right)'(S_{j_0}^{l_0})$
2. $$\frac{d X^l}{d S^l} = \frac{d f^l(S^l)}{d S^l} \triangleq \mathcal{J}_{S^l} f^l = \begin{pmatrix} \frac{d f_1^l}{d S_1^l} & \cdots & \frac{d f_1^l}{d S_{n^l}^l} \\ \vdots & \ddots & \vdots \\ \frac{d f_{n^l}^l}{d S_1^l} & \cdots & \frac{d f_{n^l}^l}{d S_{n^l}^l} \end{pmatrix} = \begin{pmatrix} \left(f_1^l\right)' \left(S_1^l\right) & \cdots & 0 \\ \vdots & \ddots & \vdots \\ 0 & \cdots & \left(f_{n^l}^l\right)' \left(S_{n^l}^l\right) \end{pmatrix}$$
每个神经元的激活函数导数会形成一个对角矩阵
***
![fcf915fdc1929d1ceda7808339ea39d.png](https://s2.loli.net/2024/12/01/aXtVCYEfHwsSFKu.png)
3. $$ \frac{dS^l}{dX^{l-1}} = \begin{pmatrix} \frac{\partial S_1^l}{\partial X_1^{l-1}} & \cdots & \frac{\partial S_1^l}{\partial X_{n^{l-1}}^{l-1}} \\ \vdots & \ddots & \vdots \\ \frac{\partial S_{n^l}^l}{\partial X_1^{l-1}} & \cdots & \frac{\partial S_{n^l}^l}{\partial X_{n^{l-1}}^{l-1}} \end{pmatrix} = \begin{pmatrix} w_{11}^l & \cdots & w_{1n^{l-1}}^l \\ \vdots & \ddots & \vdots \\ w_{n^l1}^l & \cdots & w_{n^ln^{l-1}}^l \end{pmatrix} \triangleq W^l. $$
4. $$ \frac{\partial S^{l_0}}{\partial w_{j_0i_0}^{l_0}} \triangleq \begin{pmatrix} \frac{\partial S_1^{l_0}}{\partial w_{j_0i_0}^{l_0}} & \cdots & \frac{\partial S_{n^{l_0}}^{l_0}}{\partial w_{j_0i_0}^{l_0}} \end{pmatrix}^T = \begin{pmatrix} 0 & \cdots & \frac{\partial S_{j_0}^{l_0}}{\partial w_{j_0i_0}^{l_0}} & \cdots & 0 \end{pmatrix}^T = \begin{pmatrix} 0 & \cdots & X_{i_0}^{l_0-1} & \cdots & 0 \end{pmatrix}^T, $$
where $ S^{l_0} = \begin{pmatrix} S_1^{l_0} & \cdots & S_{n^{l_0}}^{l_0} \end{pmatrix}^T. $
在计算偏导数时，我们只关心这个输入如何变化。因此，对于特定的权重$w_{j_0i_0}^{l_0}$,只有与这个权重直接相连的前一层节点的输出才对输入产生影响，其它不相关的节点对输入的偏导数是 0。
- 根据之前的1，2，3，4 ， 公式能表达成以下形式：
$$ \frac{\partial E}{\partial w_{j_0i_0}^{l_0}} = \frac{dE}{dX^l} \cdot \frac{dX^l}{dS^l} \cdot \frac{dS^l}{dX^{l-1}} \cdot \frac{dX^{l-1}}{dS^{l-1}} \cdots \frac{\partial S^{l_0}}{\partial w_{j_0i_0}^{l_0}} = \nabla_{X^l}E \cdot J_{S^l}f^l \cdot w^l \cdot J_{S^{l-1}}f^{l-1} \cdots \frac{\partial S^{l_0}}{\partial w_{j_0i_0}^{l_0}}. $$
- let $$\delta^h = \nabla_{X^l}E \cdot J_{S^l}f^l \cdot w^l \cdot J_{S^{l-1}}f^{l-1} \cdot \ldots \cdot J_{S^h}f^h$$
- Then we have:

$$\frac{\partial E}{\partial w_{j_0i_0}^{l_0}} = \delta^{l_0} \cdot \frac{\partial S^{l_0}}{\partial w_{j_0i_0}^{l_0}} = \delta^{l_0} \cdot \left(0 \, \cdots \, X_{i_0}^{l_0-1} \, \cdots \, 0\right)^T$$
我们还能得到：$$\delta^{h-1} = \delta^h \cdot w^h \cdot J_{S^{h-1}}f^{h-1}$$
这样我们就能递归的计算。
### Comparing to the Naïve Computation


- Computing** $\delta^{h-1}$ **in terms of** $\delta^h$ **avoids obvious duplicate computation, more specifically multiplication, of layers** $h$ and beyond. 计算 $\delta^{h-1}$ 基于 $\delta^h$ 可以避免显而易见的重复计算，特别是层 $h$ 及其之后的乘法操作。
- **Multiplying starting from the output layer – propagating the error** *backwards* – **means that each step simply multiplies a vector** $\delta^h$ **and a weight matrix** $w^{h-1}$, **which makes matrix operations so important in neural network forward/backpropagation.** 从输出层开始乘法计算——即误差的反向传播——意味着每一步只需将一个向量 $\delta^h$ 和一个权重矩阵 $w^{h-1}$ 相乘，这使得矩阵操作在神经网络的前向传播和反向传播中尤为重要。
### Learning Algorithm
![13fa547093114eb17b99ca87c9e7e05.png](https://s2.loli.net/2024/12/02/E5qOZt38kQK1AUW.png)





