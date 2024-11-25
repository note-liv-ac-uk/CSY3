# Lecture 15
<font size="4">Hongye Qian</font> 

## Topic 6 Perceptron
### Perceptron Learning Algorithm
![a7329fcdb68ffd14a4f2f1f9ae2293d.png](https://s2.loli.net/2024/11/25/SngAslXupU3WJKL.png)
- 通常的做法是按顺序遍历数据集中的所有样本，这样每个 epoch 会用到所有数据。(红框注释)
- RMS 收敛检查通常在一个训练周期（epoch）后进行，而不是每次样本更新后立即检查。（蓝框注释）
- 如果网络输出$X_j$与目标值$t_j$不同，则调整权重$w_j$以减小误差。

### A running example
![9df06ef8fa7b3d9891a7684271b8ef0.png](https://s2.loli.net/2024/11/26/pqxSoGRQYXECLt5.png)

![e2aa0729f249d72c718db37d10aab72.png](https://s2.loli.net/2024/11/26/X6OwsQPC9Bodxfu.png)
$$
S_1^1 = \sum_{i=0}^4 w_{1i}^1 a_i^1 = 0.5 \times 1 + 0.5 \times 1 + (-0.5) \times 1 + 0.5 \times 0 + (-0.5) \times 0 = 0.5 \geq 0
$$
$$
X_1^1 = 1
$$

$$
S_2^1 = \sum_{i=0}^4 w_{2i}^1 a_i^1 = 0.5 \times 1 + 0.5 \times 1 + (-0.5) \times 1 + 0.5 \times 0 + (-0.5) \times 0 = 0.5 \geq 0
$$

$$
X_2^1 = 1
$$
计算error和$\Delta$
$$
e_1^1 = (t_1^1 - X_1^1) = (1 - 1) = 0
$$

$$
\Delta w_{1i}^1 = C e_1^1 a_i^1
$$

$$
\Delta w_{10}^1 = C e_1^1 a_0^1 = 0.25 \times 0 \times 1 = 0
$$
$$
\Delta w_{11}^1 = C e_1^1 a_1^1 = 0.25 \times 0 \times 1 = 0
$$
$$
\Delta w_{12}^1 = C e_1^1 a_2^1 = 0.25 \times 0 \times 1 = 0
$$
$$
\Delta w_{13}^1 = C e_1^1 a_3^1 = 0.25 \times 0 \times 0 = 0
$$
$$
\Delta w_{14}^1 = C e_1^1 a_4^1 = 0.25 \times 0 \times 0 = 0
$$
***
$$
e_2^1 = (t_2^1 - X_2^1) = (0 - 1) = -1
$$

$$
\Delta w_{2i}^1 = C e_2^1 a_i^1
$$

$$
\Delta w_{20}^1 = C e_2^1 a_0^1 = 0.25 \times (-1) \times 1 = -0.25
$$
$$
\Delta w_{21}^1 = C e_2^1 a_1^1 = 0.25 \times (-1) \times 1 = -0.25
$$
$$
\Delta w_{22}^1 = C e_2^1 a_2^1 = 0.25 \times (-1) \times 1 = -0.25
$$
$$
\Delta w_{23}^1 = C e_2^1 a_3^1 = 0.25 \times (-1) \times 0 = 0
$$
$$
\Delta w_{24}^1 = C e_2^1 a_4^1 = 0.25 \times (-1) \times 0 = 0
$$
***
更新权重
$$
w_{20}^1 = w_{20}^1 + \Delta w_{20}^1 = 0.25
$$

$$
w_{21}^1 = w_{21}^1 + \Delta w_{21}^1 = 0.25
$$

$$
w_{22}^1 = w_{22}^1 + \Delta w_{22}^1 = -0.75
$$
![02d63fc6b4035fccd7dcccf509f4291.png](https://s2.loli.net/2024/11/26/pYQGNJ3e8wqiRAm.png)
***
处理第二组一样，懒得写了。（lec15 p25)
***
$$
\text{RMS} = \sqrt{\frac{\sum_{k=1}^{r} \sum_{j=1}^{m} (e_j^k)^2}{rm}} = \sqrt{\frac{\sum_{k=1}^2 \sum_{j=1}^2 (e_j^k)^2}{2 \times 2}}
$$

$$
= \sqrt{\frac{(e_1^1)^2 + (e_2^1)^2 + (e_1^2)^2 + (e_2^2)^2}{2 \times 2}}  = \frac{\sqrt{2}}{2} > \delta = 0.01
$$
根据开头那个算法，继续算，因为RMS大于$\delta$
***
后面不写了，就是何epoch1一样直到算到RMS比$\delta$小停止 （Lec15 p36）










