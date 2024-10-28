# Lecture 08
<font size="4">Hongye Qian</font> 

### Topic 3 Hebb’s Rules
#### 1. MP neuron vs. Brain Function
-  storing information -> to store knowledge
-   producing logical and arithmetical operations on it -> to apply the knowledge stored to solve problems

#### 2. ANN Learning Rules
- Objective: We need a new model, of which the parameters are easily changeable (to be learnt).
![0223bd00d3e52e10dd10d7c3a19ab09.png](https://s2.loli.net/2024/10/25/rlQGnFdP72vDjZe.png)
- The ideal free parameters to adjust, and so to resolve learning, are the weights of connections 𝒘. “理想的可调自由参数” 是这些连接的权重，即 𝑤，调整这些权重的值就是神经网络学习的核心内容。
- From now, we do ***NOT*** have the restriction on the weight. That is, the weight can be any real value.
- We do ***NOT*** check the inhibitory input.
- the reason for the above two things:  The motivation is different! We do not consider the propositional logic here.Instead, we think about learning! ***Motivations are different. Thus, the models are different.***
- **ANN learning rule**: <u>***the rule how to adjust the weights of connections to get desirable output.***</u>
-  Much work in Artificial Neural Networks focuses on the learning rules that define how to connections change the weights of between neurons to better adapt a network to serve some overall function.
-  Background: 第一次提出在1940s， from psychological studies of **Donald Hebb** and **Frank Rosenblatt**.

### 3. Hebb’s Rule (1949)
- Hebb proposed that a particular type of use-dependent modification of the connection strength of synapses might underlie  learning in the nervous system.
- 我查的资料：
  1. **赫布规则**提出了一个关于神经系统学习的假设，认为通过使用依赖性修改突触连接的强度，可能是神经系统中学习的基础。
  2. 简单来说，**“用进废退”** 的原则是赫布规则的核心，即突触连接的强度会随着使用频率的增加而增强。这意味着如果两个神经元经常一起激活，它们之间的连接就会变得更强，从而实现学习。 
- A neurophysiological postulate : When an axon of cell A  is near enough to excite a cell B and repeatedly and persistently takes part in firing it, some growth process or metabolic(新陈代谢的) change takes place in one or both cells, such that A’s efficiency as one of the cells firing B, is increased. 
- In another word: Cells that fire together, wire(n.金属丝 v.接通，连接) together.
- History:  An experimental confirmation to Hebb’s hypothesis came much later: in **1970s**, physiologists **Tim Bliss** and **Terje Lomo** discovered  ***the long-term potentiation, a sustained state of increased synaptic efficacy consequent to intense synaptic activity***.
- The conditions that Hebb predicted would lead to changes in synaptic strength have now been found to cause **the long-term potentiation** in some neurons of **hippocampus** and other brain areas. 
![b4aa614a2e7fa93e94778e4922cafdd.png](https://s2.loli.net/2024/10/26/QmtGvW3Ajqgc1Mo.png)
-  the weight $w_i^t$ is what we want to learn. 权重$w_i^t$是我们要学习的内容。通过调整权重，神经元可以根据输入的变化来优化输出。
-  Again, here we allow $w_i^t$ could be other than -1 or 1, and we do not check inhibitory inputs. It is **NOT an MP neuron**. 权重$w_i^t$ 的取值可以不是简单的 -1 或 1，这与某些特定神经元模型不同，比如 MP神经元（McCulloch-Pitts神经元），后者只有 -1 和 1 的离散权重选择。在这个模型中，不考虑抑制性输入，因此不是 MP 神经元。
-  The simplest formulation of the rule:  Increase weight 
of connection at every next instant in the way. 赫布规则的基本思想是，每当神经元同时激活时，连接权重就会增加。
- $w_i^{t+1} = w_i^t + \Delta w_i^t$ where $\Delta w_i^t = C a_i^t X^{t+1}$ 
- 1. $w_i^{t+1} = w_i^t + \Delta w_i^t$ 表示权重$w_i$ 在 $t+1$ 时刻的值等于上一时刻 𝑡 的值加上一个变化量 $\Delta w_i^t$
  2. $\Delta w_i^t = C a_i^t X^{t+1}$ 表示权重的变化量，取决于输入 $a_i$ ,输出$X^{t+1}$, learning rate $C$
- 1. $w_i^t$  is the weight of connection at instant $t$
  2. $w_i^{t+1}$ is the weight of connection at the next instant $t+1$
  3. $\Delta w_i^t$  is the increment by which the weight of connection is enlarged
  4. $C$  is positive coefficient which determines learning rate.
  5. $a_i^t$  is input value from the presynaptic neuron at instant $t$
  6. $X^{t+1}$  is outputof the postsynaptic neuron at the instant $t+1$.
- Thus, the weight of connection changes at the next instant only if both preceding input via this connection and the resulting output simultaneously are not equal to 0.
-  1. Input is not equal to 0. -> Excitatory input
   2.  Output is not equal to 0. -> Neuron is fired.
-  The second equation emphasizes the synapse correlation nature of a Hebbian. 人话：第二个公式（也就是之前展示的权重更新公式）强调了**Hebbian突触的相关性性质**，即突触的强度变化是基于输入和输出的相关性。换句话说，如果两个神经元经常一起激活，那么它们之间的连接就会加强。
- Sometimes the Hebb’s rule is referred to as activity product rule.
- Hebb’s original learning rule referred exclusively to excitatory synapses。

### 4. Algorithm of Hebb’s Rule for a Single Neuron (NOT MP)
![bd37c7bc68406b599f9dacc4e3795d1.png](https://s2.loli.net/2024/10/26/HR9NXjw2VzEmLhF.png)





 










