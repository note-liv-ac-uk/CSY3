# Lecture 10
<font size="4">Hongye Qian</font> 
### Topic 4 Normalized Hebb’s Rule (Oja’s Rule)
#### 1. Hebb's rule vs Normalized Hebb’s Rule
![082c334c5e41cb16ab540bd3befb2fa.png](https://s2.loli.net/2024/10/27/cfByhOLMTRxjWGA.png)
 - All the weights increase **monotonously**. Finally, each weight will become large enough such that any activated input can fire the neuron alone. 
![30dcf831841116c9c387b428c2cdd01.png](https://s2.loli.net/2024/10/27/Qka2D9Fh1N8UOWm.png)
- Intuition: Weights will NOT increase monotonously. The most frequent firing pattern will be remembered and finally dominate. 忘了normalized流程的看上一个笔记。

#### 2. Why does Normalized Hebb’s Rule Converge?
-  The exact dynamics of the Oja’s rule have been solved by Wyatt and Elfaldel 1995. Wyatt和Elfadel在1995年解决了Oja规则的具体动力学问题。Oja规则是Hebb规则的一种改进，通过对权重的更新过程进行归一化，使其具有更好的收敛特性。
-  It shows that the weight $w \rightarrow \delta^*$, where $\delta^*$ is the eigenvector of the largest eigenvalue $\alpha^*$ of the matrix based on average $\bar{a}$ **权重的收敛**：他们发现，使用Oja规则，权重向量$w$会趋向于$\delta^*$, 其中$\delta^*$ 是基于矩阵平均值 $\bar{a}$ 的最大特征值对应的特征向量。（忘了这个的去上一个笔记找）
- 无归一化的问题：如果没有归一化（即使用原始Hebb规则），每个连接的权重会以特征值$\alpha_i$ 指数级增长。这会导致权重失控，无法达到稳定的状态。
- 归一化的优势：在使用归一化（即Oja规则）的情况下，只有最大特征值$\alpha^*$ 对应的特征向量会最终“生存”下来，其余的特征值对应的权重会逐渐减弱。这样就保证了权重的稳定性和收敛性。
#### 3. Observations of the Running Example
- 数据集：给定的数据集只有一个样本 [1,0,1,0]。这意味着我们仅使用这一组数据来训练神经元。
- 神经元的权重：训练后，神经元的权重变成 $[0.71,0.04,0.71,0.04]$。这组权重反映了输入 $[1,0,1,0]$ 的特征。这意味着神经元对该输入样本的特性进行了“学习”。
- 矩阵计算：在训练过程中，通过公式 $C \bar{a}^T \bar{a} = 1 \cdot \begin{bmatrix} 1 \\ 0 \\ 1 \\ 0 \end{bmatrix} \cdot [1 \ 0 \ 1 \ 0] = \begin{bmatrix} 1 & 0 & 1 & 0 \\ 0 & 0 & 0 & 0 \\ 1 & 0 & 1 & 0 \\ 0 & 0 & 0 & 0 \end{bmatrix}$, 忘了这个的去看前面的笔记。这个矩阵反映了输入向量的特征关系。
- 特征值和特征向量：该矩阵的最大特征值为2，对应的特征向量为 $[0.7071,0,0.7071,0]$。特征向量的2-范数为1（即特征向量的长度为1），表示这个方向上的特征最重要。
- 忘了矩阵特征向量和特征值怎么求的，去看大一的线性代数，或者看下面这个网站 <u>https://zhuanlan.zhihu.com/p/104980382 </u>
- 权重不再单调增加，而是根据输入的重要性来调整。也就是说，输入越重要，**对应的权重就越接近1**。

#### 4. Hebb’s Rules and Associative Learning
![0fa160d7752f4c92ddd9eab9af48351.png](https://s2.loli.net/2024/10/28/dLIkXxqfZzY3W42.png)
-  Applying Hebb’s rules (including the original one and the normalized one) a neural network, we know that <u>the weight of connection increases between nodes having activated outputs simultaneously.</u> 当我们在神经网络中应用Hebb规则时，无论是原始规则还是归一化后的规则，连接权重会根据Hebb规则的定义进行调整。当两个节点（或神经元）在同一时间都被激活时，它们之间的连接会变得更强，从而增强它们之间的联系。
- 这种权重的调整和增强可以用于解决关联问题（association problems），即识别或记住不同输入之间的关系。例如，某些特定的输入模式会导致神经元的激活，神经网络可以“学习”到这些关联并记住它们。
![f70bd8fcd1a0146728b1f7c30b31a4d.png](https://s2.loli.net/2024/10/28/l5Mo7XAL3qx6ZnU.png)
- Input vector $a = (a_1, a_2, \dots, a_n)$, 权重向量为 $W = (w_1, w_2, \dots, w_n)$
- Then the instant state of the output neuron is defined as dot product: $S = W \cdot a^T = \sum_{i=1}^n w_i a_i$ 这个点积（或加权和）越大，表示输入和权重越“相似”，即两者越“接近”彼此。This weighted sum will be greater if the vectors 𝒂 and 𝑾 are similar, i.e., close to each other.
![27765b7603cf88a257fa457f368f012.png](https://s2.loli.net/2024/10/28/yrEJvaG5Ddl3XOQ.png)
![8c77d33ae5341d79d0115adfa4b0e54.png](https://s2.loli.net/2024/10/28/48L2IJUybi1kAZR.png) 
- Training of a neuron with normalised Hebb’s learning rule results in a vector of weights of connections similar to the training input vector. 如果输入向量 𝑎 和权重向量 𝑊 相似（即方向相同或接近），点积的值会更大，从而神经元的输出会更高。这意味着Hebb规则在更新权重时，会使权重向量朝输入向量的方向调整，使其更接近输入模式。
- The neuron “remembers” the training pattern via increasing weight of corresponding connections. 
- 如果训练好的神经网络接收到一个**类似于训练用的输入向量** $a$ 的新输入向量 $a'$, 那么这个新输入向量 $a'$ 也应该与网络的权重向量$W$ 相似，从而产生相似的神经元输出。

- One may say that , the network “recognises” the new input or “associates” it with the training one.
#### 5.  Associative Learning
![ea74ff792ae61236540c0d8997f0fcf.png](https://s2.loli.net/2024/10/28/YfrSiI29ROK5pWB.png)
-  This weighted sum 𝑆 will be greater if the vectors $a$ and $w$ are similar. i.e. close to each other
-  Definiton: Association is the task of mapping patterns to patterns. 关联学习是将一个模式映射到另一个模式的任务。它涉及记忆输入和输出之间的关系，而不是单纯的记忆输入本身。
-    An associative memory is to learn and remember the mapping between two unrelated pattens.  关联记忆的目的是学习和记住两个不相关的模式之间的映射。例如，通过学习，神经网络能够将输入和权重匹配，形成关联。
-    Example:  For instance, a person may learn a word and its meaning before (learn the mapping between word and meaning). When the person reads the word that is spelled incorrectly, she or he may know it has the same meaning with the correct word by association (remember the mapping). 一个人可能先学会一个单词及其含义（即“单词”和“含义”之间的映射），当他遇到拼写错误的单词时，仍然可以通过关联记忆识别出它的含义。这表明他通过“关联”记住了正确拼写和含义的关系。

#### 6. Unsupervised Learning
- We do not label any input in the data set during learning. The weight updating in each iteration only involves the input, the output and the current weight. 在学习过程中，数据集中的任何输入都不需要标记。权重的更新仅依赖于当前的输入、输出和当前的权重值。
-  We do not care what the output pattern means. We care which inputs are considered similar by the network. That is, unsupervised learning. 这意味着我们不需要提供“正确”或“错误”的标签，网络会自动学习输入的模式。
-  Unsupervised learning is a type of machine learning in which the algorithm is not provided with any pre-assigned labels or scores for the training data. As a result, unsupervised learning algorithms must first self-discover any naturally occurring patterns in that training data set.
-   It will be much clearer when we extend the network with single output to the network with multiple outputs.
#### 7. From Single Output to Multiple outputs
![aa46cb2bf974ea7ff27c2bd28062a0e.png](https://s2.loli.net/2024/10/28/VJunw74iC5RZLNI.png)
- When there are multiple outputs, weight vector becomes weight matrix.
- **For a single output network**, we can strengthen the link between an input pattern and an output by normalized Hebb’s rule. The network can therefore recognize other similar inputs;
- **For a multi-output network**, it is supposed to recognize multiple types of patterns. Each input could be recognized as either one type of pattern, or none of them. (Clustering)














