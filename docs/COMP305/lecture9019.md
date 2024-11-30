# Lecture 19
<font size="4">Hongye Qian</font> 

## Calculation of the partial derivative of the error function with respective to a specific weight.
- **Batch Gradient Descent** 使用整个数据集计算梯度，适合小型数据集，通常需要更长的时间。
- **Stochastic Gradient Descent** 通过单个样本更新权重，训练速度更快，但可能引入噪声。




### Partial Derivative
- 有以下两种情况：
  1. **Output Layer**: $l = l_0$  
   - This case refers to the output layer where $l$ is equal to the output layer index $l_0$.

    2. **Otherwise**: $l \neq l_0$  
    - This case refers to any other layer except the output layer, where $l$ is not equal to $l_0$.
***
当 $l = l_0$
1. Expand the summation into two parts:
   $$\frac{\partial}{\partial w_{j_0 i_0}^{l_0}} \frac{1}{2} \left( (t_{j_0} - X_{j_0}^{l_0})^2 + \sum_{j \neq j_0} (t_j - X_j^l)^2 \right)$$

2. Focus on the term involving $t_{j_0}$ since other terms do not depend on $w_{j_0 i_0}^{l_0}$:
   $$\frac{\partial}{\partial w_{j_0 i_0}^{l_0}} \frac{1}{2} (t_{j_0} - X_{j_0}^{l_0})^2$$

3. Final result:

$$\frac{\partial}{\partial w_{j_0 i_0}^{l_0}} \frac{1}{2} \left(t_{j_0} - X_{j_0}^{l_0}\right)^2 = \frac{\partial}{\partial X_{j_0}^{l_0}} \frac{1}{2} \left(t_{j_0} - X_{j_0}^{l_0}\right)^2 \cdot \frac{\partial X_{j_0}^{l_0}}{\partial S_{j_0}^{l_0}} \cdot \frac{\partial S_{j_0}^{l_0}}{\partial w_{j_0 i_0}^{l_0}}$$
我的理解是：决定$w_{j_0 i_0}^{l_0}$就只有$t_{j_0}$，其他参数在求导的时候当作常数。
Final Result用了链式法则。
最终结果：
$$\frac{\partial E}{\partial w_{j_0 i_0}^{l_0}} = \left(X_{j_0}^{l_0} - t_{j_0}\right) \cdot \left(f_{j_0}^{l_0}\right)'(S_{j_0}^{l_0}) \cdot X_{i_0}^{l_0-1}$$
看不懂可以看下老师的lec19 P20-25，证明的还挺清楚的
![c43205c89a2f0c8da08c1dadc741fb3.png](https://s2.loli.net/2024/12/01/Cak6P5JjEBs82Wh.png)
***
当$l \neq l_0$时：
这个证明下次再更，我没看懂哈哈哈。
***
### Partial Derivative: Conclusion
$$\frac{\partial E}{\partial w_{j_0 i_0}^l} = \begin{cases} \left(X_{j_0}^{l_0} - t_{j_0}\right) \cdot \left(f_{j_0}^{l_0}\right)'(S_{j_0}^{l_0}) \cdot X_{i_0}^{l_0-1}, & \text{When } l = l_0 \\ \sum_{j=1}^{n^l} \left(X_j^l - t_j\right) \cdot \left(f_j^l\right)'(S_j^l) \cdot \sum_{i=1}^{n^{l-1}} w_{ji}^{l-1} \cdot \left(... \cdot \left(f_{j_0}^{l_0}\right)'(S_{j_0}^{l_0}) \cdot X_{i_0}^{l_0-1}\right), & \text{When } l \neq l_0 \end{cases}$$

### A running example
![813f4e8c4bdf8c30cbde4c55005b317.png](https://s2.loli.net/2024/12/01/Dq853G1XC6ZKO7r.png)
$$E = \frac{1}{2} \left(t_1 - X_1^3\right)^2 = 0.01805$$
$$\frac{\partial E}{\partial w_{11}^3} = \left(X_1^3 - t_1\right) \cdot \left(\text{sig}'(S_1^3)\right) \cdot X_1^2 = 0.02763= 0.19\cdot0.69\cdot(1-0.69)\cdot0.68$$
Sigmoid上个lec讲过，这里有涉及对它的求导。这是一个$l = l_0$  的例子
***
![b47e01fe149e39e316e2e072ddfd1c0.png](https://s2.loli.net/2024/12/01/Ez5ZSDpHxucsAnF.png)

$$\frac{\partial E}{\partial w_{11}^2} = \left(X_1^3 - t_1\right) \cdot \left(\text{sig}'(S_1^3)\right) \cdot w_{11}^3 \cdot \left(\text{sig}'(S_1^2)\right) \cdot X_1^1 = 0.0009= 0.19\cdot0.69\cdot(1-0.69)\cdot0.3\cdot0.68\cdot(1-0.68)\cdot0.35$$

这个lec19就纯推导，看例子吧，别看公式了。