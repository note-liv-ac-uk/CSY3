# Lecture 02 
<font size="4">Hongye Qian</font>  

## Part1 Artificial Neural Networks
- ANNs are based on **neuroscience ideas** and represent a form of computing technology.  
### Topic1 Historical/Biological Introduction
#### 1. NeurAons & Information Propagation
- Overview: Nerve fibers. Trains of Spikes (see lecture2, slide10-11)
- Neurons propagate information via **action potentials** or **spikes**, which are electrical impulses that travel down nerve fibers.

#### 2. Biological Excitability
![p1.png](https://s2.loli.net/2024/10/03/9fBTnRhzyIDcxbw.png)
- Virtually all living cells maintain an electrical potential difference between their ***interiors*** and the ***environment (exteriors)***.
-  The ***membrane potential*** is one of the factors determining the energy barriers encountered by charged substances (ions) entering or leaving the cell.
-  Ion channal (10nm): ***proteins*** with the central pore through which ions can cross the membrane.
  Allow ions, predominantly Na<sup>+</sup>, K<sup>+</sup>, Ca<sup>2+</sup>, to move in and out of the cell.
-  section of the ***lipid bilayer***(3-4nm): two ion channels embedded in it.
-  ***Resting condition***: defined to be 0mV (potential inside neuron membrane is from -30 mV to -90 mV relative to that of the surrounding bath), we say it ***polarized***.
-   The ***electrical signal*** of a living cell is change of the membrane potential (may change in response to electrical perturbation from other neurons).
-   If the perturbation is sufficiently large, above a ***threshold*** in ***intensity and duration***, the response is a large amplitude electrical wave, propagating from the stimulated points to the rest of the tissue.
  1. Wave travel: uniform velocity
  2.  The excitation and transmission are ***all-or-none***(1 or 0) and do not allow varying degree of strength.
  3.   Excitation is followed by an unexcitable period of definite duration, called the ***absolute refractory period***; which is followed in turn by a relative refractory period when the cell has subnormal excitability.
   #### 3. Neuron Components
   ![p2.png](https://s2.loli.net/2024/10/03/W7BNuAFId2Pfwet.png)
   - ***Dendrites*** and ***soma***: Receive inputs from other neurons or receptor.
   - ***Soma***: The cell body.
   - ***Axon***: Carries output signals to other neurons or effectors (muscles, glands).
   - the dendritic tree allows a neuron to receive inputs from many other neurons through synaptic connections
   - exmples: see lecture2 slides 21-22
   #### 4. Trans-synaptic stimulation – External Mechanism
   ![p4.png](https://s2.loli.net/2024/10/03/WZIk7OupsFqwyzK.png)
   
   - ***cleft***: connect two neurons.
   -  The axon terminal or bouton is filled with synaptic vesicles containing ***neurotransmitter***.
   -   The neurotransmitter is released when a ***spike*** arrives from the presynaptic neuron.
   -    Transmitter crosses the synaptic cleft and binds to ***receptors*** on the ***dendritic spine***.
   -    There is ***no physiological continuity from neuron to neuron***.
   -   ***When an impulse (perturbation) reaches a synapse, it does not necessarily stimulate the following neuron.***
   -   two ways of  Trans-synaptic stimulation:
       1. ***temporal summation***:either a repetition of impulses in time at the same synapse. 这是指在相同的突触处，连续多次的神经冲动重复发生，从而累积到达足够的激活水平，使得神经元产生响应。
       2. ***Spatial Summation***: the simultaneous arrival of impulses at a sufficient number of adjacent synapses. 这是指几个相邻的突触几乎同时收到冲动，合力使得某区域的激活密度足够高，从而引发神经元的活动。
- ***inhibition***: The arrival of impulses at synapses may 
have opposite to excitation effect, i.e., it may render the element less excitable to other stimuli. 在某些情况下，突触处的神经冲动到达可能不是导致神经元激活，而是使神经元变得不易被其他刺激激活。这种减少的可激活性被称为抑制。
#### 5. Neuronal Excitation
![p5.png](https://s2.loli.net/2024/10/03/TWe8HsoiurVYDb4.png)
-  The excitatory or inhibitory effect of the transmitter generally causes a ***potential change*** in the postsynaptic membrane. ***兴奋性或抑制性的传递物质***：当神经递质（一种化学物质）从突触前神经元释放到突触后神经元时，它会对突触后神经元的膜电位产生影响，这种影响可能是兴奋性的（使神经元更容易发放电信号）或抑制性的（使神经元更难发放电信号）。***电位变化***：神经递质的作用会引起突触后膜的电位变化，这种变化可能是局部的电位上升（去极化）或下降（超极化）。
-   The ***cooperative effect*** of many potential 
changes may yield a synthesized potential change in the soma that ***exceeds the threshold*** – and if this occurs at a time when the neuron has passed the refractory period of its previous firing, then a new impulse is fired down the axon.
人话：***协同效应***：多个电位变化可以在细胞体（soma）中相互作用和合成，如果这些电位变化累积超过了一个阈值，神经元就会产生一个新的动作电位（神经冲动），这个动作电位会沿着轴突传递。
人话2：***动作电位的发生***：如果在神经元通过其前一个动作电位的不应期（一个短暂的时间段，在此期间神经元不能或难以再次被激活）之后，累积的电位变化超过了激发阈值，那么神经元会在轴突上发放一个新的动作电位。
- Records from a Neuron -- Cortical Pyramidal Neuron  
  1. See slides lecture2 32-33

5. Summary
   ![p6.png](https://s2.loli.net/2024/10/03/BOYMZdPLFCJsgSm.png)
 
  



























