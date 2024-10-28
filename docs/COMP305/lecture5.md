# Lecture 05
<font size="4">Hongye Qian</font> 

#### 1. MP Neuron Computation Algorithm
![b63bfc41da394786dbee1c8ddedbda0.png](https://s2.loli.net/2024/10/23/AUpBucFNdxHEZQ9.png)

- Explanation
  1. 首先，系统检查所有来自抑制性连接的输入。如果从抑制性连接中的任何一个输入不为0（意味着有抑制信号存在），则神经元的输出$X^t$将被设为0，因为抑制信号阻止了神经元的激活.
  2. 如果所有抑制性连接的输入都为0（没有抑制信号），算法继续计算神经元的瞬时状态$S^{t-1}$，这通过将所有输入$a_i^{t-1}$与它们对应的权重 $w_i$相乘并求和来完成。
  3. 计算得到的瞬时状态$S^{t-1}$与神经元的阈值𝜃进行比较,
   如果$S^{t-1}$大于或等于阈值𝜃, 则输出$X^{t-1}$为1，
   如果$S^{t-1}$小于阈值𝜃, 则输出$X^{t-1}$为0。

- Example1:
  ![625f3627a362e8907611acc995bc664.png](https://s2.loli.net/2024/10/23/rsg2udnxoINVtPq.png)

- Example2:
  ![c988b86771973ab0d1a9e93fd98b472.png](https://s2.loli.net/2024/10/23/7fAiKnuoXqNvtWD.png)

  #### 2. MP-Neuron as a Binary Unit
- ***Simple logical functions*** can be implemented directly with a single McCulloch-Pitts unit. 简单的逻辑函数（如 AND、OR 和 NOT）可以直接通过单个麦卡洛克-皮茨神经元实现。这种神经元可以模拟基础的二元逻辑操作。
-  The output value 1 can be associated with the logical value true and 0 with the logical value **false**. 输出值1和0分别与逻辑真（true）和逻辑假（false）相关联。

#### 3. MP-Neuron Logic: Two Inputs
- $a_1 \land a_2$
  ![d2a9022fcd7fade52e01b590a7a9a80.png](https://s2.loli.net/2024/10/23/DTf4YVX8IFCmWJq.png)
  **the output fires if $a_1$ and $a_2$ both fire.
<u>Provement see lecture5 P21. </u>
- $a_1 \lor a_2$
![d1170e3559c3070626cb923b7c33437.png](https://s2.loli.net/2024/10/23/U5e8rvEuI1WaO7g.png)
**the output fires if $a_1$ fires or $a_2$ fires or both fire.**
- $\neg a$
![e06c5876d884587cae82b8c10a714a7.png](https://s2.loli.net/2024/10/23/ZJ7SI6upnktRHWF.png)
**the output fires if $a_1$ does NOT fire and vice versa.

#### 4. MP-Neuron Logic: Multiple Inputs
![62e2c35109f58c7b650582f73e23f59.png](https://s2.loli.net/2024/10/23/l6nyTmrBfg4Fvkw.png)
**证明用旁边的逻辑门证明就行**
- In general, the same kind of computation requires several conventional logic gates with two inputs. 传统的逻辑门（如普通的AND和OR门，通常设计有两个输入）在处理多个输入时需要多个门级联使用，而单个麦卡洛克-皮茨神经元可以更直接地处理多个输入。
- The threshold logic elements reduce the complexity of the circuit used to implement a given logical function. 阈值逻辑元件可以减少实现给定逻辑功能所需电路的复杂性。

#### 5. MP-Neuron as a Register Cell
![a94a3fa0b5af142cc03371088792227.png](https://s2.loli.net/2024/10/23/gtEiZvHP3pQmL4I.png)
A single neuron with a single input a and with the weight 
and threshold values both of unity, computes the output.
**$X^t= a^{t-1}$**
- 1. 神经元有一个输入 𝑎在这个示例中，输入值$a_1$可以是1或0,输入 𝑎的权重设置为1.
  2. 神经元的阈值也设置为1。这意味着，当输入$a_1$为1时， 由于加权输入等于阈值（1 × 1 = 1），神经元的输出$X^t$也为1。
  3. 0的时候自己想下就知道了。


#### 6. (Extended) MP-Neuron as a Memory Cell
![99f990f98366fea46ed74e20857b326.png](https://s2.loli.net/2024/10/23/2qX45swvHPjZ6ug.png)
- 这种设置使神经元的当前状态能够影响其未来的行为，形成一个内部的状态保持机制，即一个记忆单元。
- 当 $a_1^{t-1}$（可能是外部输入）激活时，它通过正权重增加神经元的内部和。
- 同时，反馈输入$a_2^{t-1}$通过负权重尝试降低这个和，这样的配置可以用来维持或改变当前的状态，依据$a_1^{t-1}$和先前状态 $X^{t-1}$的值。
- **Logic**:
  1. 如果没有外部输入 ($a_1^{t-1}=0$), 神经元的输出将依赖于其之前的状态 $X^{t-1}$，通过负反馈来逐步减少其活性，直至状态翻转。
  2. 如果没有外部输入 ($a_1^{t-1}=1$), 它将与先前的输出一起决定当前的输出。例如，如果反馈力量不足以抵消输入$a_1^{t-1}$的影响，输出$X^{t-1}$可能保持为1。





