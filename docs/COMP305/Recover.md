# Review concepts
<font size="4">Hongye Qian</font> 

#### 1. What characteristics of a biological neuron inspire the discrete-time modeling ofa MP neuron?
For the discrete-time modeling, **discretization**: Comparable to a refractory period (不应期)(assumed to be same for each neuron). **Fixed time step**: The wave travels with a nearly uniform velocity in a biological neural system.

#### 2. What values can a MP neuron's inputsand output take and what is the biological motivation of such setting?
The input and output are binary, which is comparable to the fact that only spikes are propagated (传播) in biological neural networks. Then the types of the input and the output of a MP neuron are unified (一致性的).

#### 3. What values can an input connection weight of a MP neuron take and what isthe biological motivation of such setting?
+1 for the excitatory and -1 for inhibitory

#### 4.How does the inhibitory connection influence the computation of a MP neuron?
The activated input via an inhibitory connection prevents excitation of the neuron at that instant.

***
#### 5.  What is a learning rule of an artificial neural network and what can it be used for?
A rule define how to adjust the weights of connections in the network.

#### 6. What is Hebb's postulate (假设) that motivates the Hebb's rule?
When an axon of cell A is near enough to excite a cell B and repeatly and persistently takes part in firing it, some growth process or metabolic (新陈代谢的) change takes place in one or both cells, such that A's efficiency as one of the cells firing B, is increased.

#### 7. Explain the difference between this model and the MP neuron.
1. The weight $w_i^t$ now is the parameters to be learnt and will change over time.
2. we do not have the type restriction on the weight.
3. We do not check the inhibitory input while calculating the output of the neuron.

#### 8. Does the original Hebb's learning rule converge (集中)?
Hebb's original learning rule can only monotonously increase synaptic(突触的) weights, thus it does not converge.

***
#### 9. What does the training set for a self-organizing network consist of?
A set of training inouts only.

#### 10. What problems can be solved by a Kohonen Self- organizing Map?
Kohonen SOM can be used as a feature detector for the new input patterns.

#### 11. Why are Hebb's rule, Oja's rule and Kohonen Self-Organizing Map unsurpervies learning?
![f070b4cbd16d5cd8d591eb8035ed1d7.png](https://s2.loli.net/2024/10/31/TByQGJvYdcN6mps.png)
