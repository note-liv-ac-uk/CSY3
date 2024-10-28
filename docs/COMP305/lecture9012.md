# Lecture 12
<font size="4">Hongye Qian</font> 

### Topic 5 Kohonen’s Rule (Competitive Learning)
#### 1. Kohonen Rule: Competitive Learning
- We consider a one-layer neural network with multiple outputs.
- In competitive learning, as the name implies, an output neuron of a network compete among all the outputs to be updated (regarding the weights). 在竞争学习中，输出层的神经元之间相互竞争，以决定哪个神经元的权重需要更新。即，输出神经元会竞争，只有一个获胜的神经元会被更新
- Whereas in a neural network based on Hebbian learning several output neurons may be updated simultaneously, in competitive learning **only a single output neuron is updated at any instant**.  不同于Hebbian学习方法（可以同时更新多个输出神经元的权重），竞争学习中一次只更新一个获胜的输出神经元。
- This makes competitive learning highly suited to discover statistically important features that may be used to classify a set of input patterns. 竞争学习能够帮助神经网络发现重要的统计特征，用于对输入模式进行分类。
- Teuvo Kohonen suggested a network in which the output neurons compete for the right to respond to an input. Teuvo Kohonen suggested a network in which the output neurons compete for the right to respond to an input. Teuvo Kohonen提出了一种网络结构，在这种网络中，输出神经元之间会竞争，以获得对输入的响应权利。
- arning rule first assumes that one of the output neurons, say the 𝑗-th, has maximum value of the instant state $S_j$ at that instant.  学习规则假设某个输出神经元（比如第 𝑗 个神经元）在某一时刻具有最大值$S_j$，也就是说，这个神经元的激活状态最高。
-  neuron is declared to be the winner, and only the weights of the winner’s connections $w_j = (w_{j1}, w_{j2}, \cdots, w_{jn})$   这个具有最大激活状态的神经元被称为“胜者”，只有胜者神经元的权重$w_j = (w_{j1}, w_{j2}, \cdots, w_{jn})$会得到更新。
![b33bf6d3dcfac8ca28a7b4cf9a0947e.png](https://s2.loli.net/2024/10/29/zgcvQ8Gy5CalFM9.png)
- We further relax the restriction on the input type, i.e., we allow real inputs in the competitive learning. 在这个竞争学习模型中，输入类型的限制被放宽了，允许输入为实数（real inputs）。这意味着输入数据可以是连续的数值，而不仅限于离散的数值。
- Only the winner outputs a 1, while others output 0. 在竞争学习中，只有胜出的神经元（胜者）会输出1，其他神经元则输出0。也就是说，只有一个神经元会激活输出1，其他神经元在当前输入下都被抑制，输出为0。
- The learning rule first assumes that one of the output neurons, say the $j$-th, has maximum value state 𝑆 at that instant. 学习规则假设在某一时刻，输出神经元中某一个（例如第 𝑗 个神经元）状态值最大，即 $S_j = \max(S_1, \cdots, S_m)$
- That neuron is declared the winner, and only its vector of connections weights. $w_j = (w_{j1}, w_{j2}, \cdots, w_{jn})$该状态值最大的神经元被称为“胜者”。在竞争学习中，只有这个“胜者”神经元的连接权重向量 $w_j = (w_{j1}, w_{j2}, \cdots, w_{jn})$ 会被更新，其他神经元的权重不会变化。
- 这种方式确保了每次训练中只有一个输出神经元的权重会更新，从而逐渐增强该神经元对特定输入模式的响应能力。
- Assume that the 𝑗-th output neuron has maximum weighted input at that instant 𝑡. 
$S_j^t = \max(S_1^t, \cdots, S_m^t)$ 假设在某一时刻 𝑡，第 𝑗 个输出神经元具有最大的加权输入为前面这个式子
- Then its weight is updated as $w_{ji}^{t+1} = w_{ji}^t + \Delta w_{ji}^t$ where 𝑖 = 1,⋯,𝑛.
- The incremental term $\Delta w_{ji}^t = C(a_i^t - w_{ji}^t)$
- Having the maximum weighted input, means that the winning output neuron has the vector of connection weights most similar to the input vector.
- The winner-takes-it-all learning rule modifies the winner’s (only) connection weights by a fraction (learning rate) of the difference between the current input vector and the current weight vector of the winner neuron. “胜者全得”（Winner-takes-it-all）学习规则是一种用于神经网络的权重更新方法。在这种规则下，只有当前输入下的“胜者”神经元的连接权重会被更新，其他神经元的权重不变。具体来说，这个更新过程是通过调整“胜者”神经元的权重向量，使它更接近输入向量。
- Q & A About Kohonen Learning Rule: Please see the lecture12 P21. The writer's battery is low. 
![1682513697fc84471b6aa1dfa48f36d.png](https://s2.loli.net/2024/10/29/9nsdqjtTU3LYIkH.png)
- Example:
![57df276bcda322db94c0017f1b816b7.png](https://s2.loli.net/2024/10/29/paEytQDHjJLlc7A.png)
- Round 1: 
  Consider the input (2,1). Learning rate is 0.5.
  $S_1 = 4 \times 2 + 1 \times 1 = 9$
  $S_2 = 2 \times 2 + 4 \times 1 = 8$
  thus we update the weights of the 1st output.
  $w_{11} = w_{11} + \Delta w_{11} = 4 + 0.5 \times (2 - 4) = 3$
  $w_{21} = w_{21} + \Delta w_{21} = 1 + 0.5 \times (1 - 1) = 1$
![63eff53984347c92bd2c0270ad4c4a1.png](https://s2.loli.net/2024/10/29/gtpH4q9iCFGuEJR.png)
- Round 2:
  Consider the input (2,1). Learning rate is 0.5.
  $S_1 = 3 \times 2 + 1 \times 1 = 7$
  $S_2 = 2 \times 2 + 4 \times 1 = 8$
  thus we update the weights of the 2nd output.
  $w_{12} = w_{12} + \Delta w_{12} = 2 + 0.5 \times (2 - 2) = 2$
  $w_{22} = w_{22} + \Delta w_{22} = 4 + 0.5 \times (1 - 4) = 2.5$
![e970c58479cdd98cf2d63707206c7a6.png](https://s2.loli.net/2024/10/29/76jQhWzkde2aFK5.png)
- Round 3:
  Consider the input (2,1). Learning rate is 0.5.
  $S_1 = 3 \times 2 + 1 \times 1 = 7$
  $S_2 = 2 \times 2 + 4 \times 1 = 8$
   thus we update the weights of the 2nd output
  $w_{12} = w_{12} + \Delta w_{12} = 2 + 0.5 \times (2 - 2) = 2$
  $w_{22} = w_{22} + \Delta w_{22} = 4 + 0.5 \times (1 - 4) = 2.5$
  ![e970c58479cdd98cf2d63707206c7a6.png](https://s2.loli.net/2024/10/29/76jQhWzkde2aFK5.png)

#### 2. Self-Organizing Map (SOM)
![5cc2f433d21b61a6f13616ba96c8709.png](https://s2.loli.net/2024/10/29/roGLh7HyNVD3dnb.png)
- We are interested in a specific application of Kohonen learning rule (competitive learning), self-organizing map (SOM).  SOM是一种神经网络模型，利用竞争学习规则来实现高维数据的降维，同时保持数据的拓扑结构。它是一种无监督学习方法，常用于数据的聚类和可视化。
- SOM is used to produce a lowdimensional (typically two-dimensional) representation of a higher dimensional data set while preserving the topological structure of the data. For instance, in left 
figure, a SOM maps a 𝑛-dimensional input to a 2-dimensional space. It can be used for clustering or visualization. SOM可以将高维数据（例如 𝑛 维输入）映射到低维（通常是二维）空间。这样可以在保持数据的拓扑结构的同时，以图形化的方式展示复杂的数据分布。
- The training of such specific networks is based on Kohonen learning rule (competitive learning). 训练就用上面那个rule的公式。
![2e2eb9efaae58680885e7248b3fa7be.png](https://s2.loli.net/2024/10/29/S1Y4nb3Foz9N5Uv.png)
- Sometimes, the winning neighbourhood is extended beyond the single neuron winner, so that it includes the neighbouring neurons, for which some corrections to the connection weights may also be done. 有时，更新范围会扩大到胜者神经元的邻近神经元，而不仅仅是胜者自身。这种扩展有助于调整连接权重，从而在网络中更好地捕捉数据的拓扑结构。
- Inaddition, 𝐶 may sometimes decrease along with the time, for convergence purpose, i.e., 𝐶(𝑡) ⟶0, 𝑡⟶0  为了确保算法的收敛，即逐步接近稳定状态，学习率 𝐶 有时会随着时间 𝑡 的增加而逐渐减小。具体而言，当 𝑡 →0 时间趋向无穷）时，学习率 𝐶(𝑡) 会趋近于 0。
- In the map, location of the most strongly excited 
neurons (winner) is correlated with the certain input signals. 
- Neighbouring excited neurons correspond to inputs with similar features.
- Because in the training phase weights of the whole neighbourhood are moved in the same direction, similar items tend to excite adjacent neurons. Therefore, SOM forms a semantic map where similar samples are mapped close together and dissimilar ones apart. 
- Example 参考 lecture11 P33


















