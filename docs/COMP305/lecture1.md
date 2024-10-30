# Lecture 1
<font size="4">Weiran Cui</font> 
[TOC]

## Intro of Biological Neuron



- Artificial Neural Networks (ANNs) 人工神经网络

- Information propagation mechanism of neurons 神经元信息传播机制

  - **Neurons** are specialized cells that generate and propagate **characteristic electrical pulses** called **action potentials** (or **spikes**) that can travel down nerve fibers in response to chemical and other inputs, rapidly transmitting information over large distances by firing **sequences of spikes** (or **spike train**) in various **temporal patterns**.

  - ```python
    neurons传播的是spikes，information的传播是在不同时序模式下通过传播一系列spikes完成的，即多个neurons传播。
    
    #neurons 神经元
    #propagate 传播
    #characteristic electrical pulses 特征电脉冲，pulses脉冲为广义信号术语
    #action potentials 动作电位 / spikes 脉冲，但特指动作电位
    #nerve fibers 神经纤维
    #sequences of spikes / spike train 脉冲序列
    #temporal patterns 时序模式
    ```

  ![1d2ea84598c20a7db31c1b3aa973617.png](https://s2.loli.net/2024/10/30/9GBzdrZj8TpYu7t.png)

- Ion Channels and Signal Transmission 离子通道和讯号传输

  - **Ion channels** control the flow of ions across the cell membrane by **opening and closing** in response to **voltage changes** and both **internal** and **external signals**, playing a crucial role in regulating membrane potential and neuron excitability.

  - ```python
    #ion channels 离子通道
    #cell membrane 细胞膜
    #voltage changes 电压变化
    #regulating membrane potential 调节电位差
    #neuron excitability 神经元兴奋性
    ```

- Resting Membrane Potential and Excitability 静息膜电位和兴奋性

  - Under **resting conditions**, the neuron membrane potential ranges from **-30 mV to -90 mV** relative to the surrounding (0 mV), making the cell **polarized**.

  - Neurons transmit information through **changes in membrane potential**, which can be triggered by electrical perturbations from other neurons. If these perturbations exceed a **threshold** in intensity and duration, a large electrical wave propagates through the tissue.

  - ```python
    超过阈值则产生电波，神经元产生动作电位开始传播信息。
    
    #resting conditions 静止状态
    #mV = millivolt 毫伏，电势差单位
    #polarized 极化
    #electrical perturbations 电扰动
    #threshold 阈值
    ```

- Biological Excitation and Wave Propagation 生物学激发和波传播

  - The wave travels at a **uniform velocity** and follows an **all-or-none** principle, meaning the strength of the excitation doesn't vary.
  - After excitation, the neuron experiences an **absolute refractory period** (completely unexcitable), followed by a **relative refractory period** (reduced excitability).
  - ```python
    all：一旦刺激强度达到了阈值，神经元会产生一个完整的动作电位，并以相同的方式将其传播给下一个神经元或肌肉纤维，神经信号不会在传递过程中由于刺激强弱而发生衰减或增强。
    none：如果刺激强度没有达到阈值，神经元不会产生任何动作电位，信号也不会传递。
    refractory period：每一次激发之后存在冷却。
    
    #uniform velocity 匀速
    #all-or-none 全或无
    #strength of the excitation 刺激强度
    #absolute refractory period 绝对沉静期，无论刺激多么强都不会激发神经元。
    #relative refractory period 相对沉静期，神经元兴奋性降低，但刺激足够强仍有可能再次激发神经元。
    ```

 ![2c4269a26a400fd233cc77f19efc7f3.jpg](https://s2.loli.net/2024/10/30/fSiG6PVnKzx45ca.jpg)

- The components of a neuron that enable the propagation 促使神经元传播的组成部分

  - **Neurons** have specialized structures for communication: the **dendrites** and **soma** serve as the input surface, receiving signals from other neurons and/or receptors, while the **axon** transmits signals to other neurons and/or effectors such as muscle fibers or glands. The branching **dendritic tree** enables the neuron to receive inputs from many other neurons via **synaptic connections**.

  - ```python
    #dendite 树突
    #soma 细胞体
    #receptor 受体
    #axon 轴突
    #effector 效应体
    #synaptic connections 突触连接
    #synapse 突触
    ```

![ddb3c7754c52e40b9dbdd927075c669.png](https://s2.loli.net/2024/10/30/nGjozuE6eNargdi.png)

- Biological excitation is Internal mechanism 生物学激发是**内部机制**

  - 这张图片展示了典型的**突触（synapse）**结构，突触是神经元之间传递信息的连接点。图片中的关键要素包括：
    1. **突触前神经元（presynaptic neuron）的轴突末端（axon terminal/bouton）**，其中装满了**突触小泡（synaptic vesicles）**，小泡内含有神经递质 (neurotransmitter)。
    2. 当**动作电位（spike）到达突触前神经元的末端时，神经递质从小泡中释放，进入突触间隙（synaptic cleft）**。
    3. **突触间隙**是两个神经元之间的空隙，神经递质通过这个空隙传递信号。
    4. **突触后神经元（postsynaptic neuron）**的**树突棘（dendritic spine）**上有受体，这些受体与释放的神经递质结合，从而引发下一个神经元的反应。
  - 整个突触过程展示了信息如何从一个神经元传递到另一个神经元。重要的机制包括：
    - **突触前**：动作电位到达突触前神经元的轴突末端，触发神经递质释放。
    - **突触后**：神经递质穿过突触间隙，与突触后神经元的受体结合，导致神经信号的进一步传播。

- Trans-synaptic stimulation – External Mechanism 跨突触刺激是**外部机制**

  - **External mechanisms** refer to **trans-synaptic stimulation** induced by **external sources**, such as electrical or chemical stimulation. This involves triggering the activity of neurons through **external interventions**. The stimulation works by causing **repeated or amplified impulses** in the **presynaptic neuron**, which results in the release of sufficient **neurotransmitters** that stimulate the **postsynaptic neuron**.

  - External mechanisms include:

    - **Temporal summation**: A repetition of impulses in time at the same synapse. 在同一个突触上快速重复的脉冲，导致足够大的刺激。
    - **Spatial summation**: The simultaneous arrival of impulses at a sufficient number of adjacent synapses. 多个相邻突触同时受到刺激，产生足够高的兴奋密度来激发神经元。

  - ```python
    #trans-synaptic stimulation 跨突触刺激
    #electrical or chemical stimulation 电刺激或化学刺激
    #interventions 外界干预
    #repeated or amplified impulses 重复或加强刺激（使触发一系列动作电位）
    #presynaptic neuron 突触前神经元
    #neurotransmitters 神经递质
    #postsynaptic neuron 突触后神经元
    #Temporal summation 时间性加和
    #spatial summation 空间性加和
    ```

  

![1eeea1f98b338e3bc6f9a0961ec26a7.png](https://s2.loli.net/2024/10/30/2a85QRIXyxhFvD6.png)

```python
*图片展示了神经元内部和外部电位记录的差异，并与神经元激发过程相关联：
1.顶部曲线：从神经元的胞体soma内部记录到的电位变化。可以看到动作电位spikes叠加在较为缓慢变化的阈下电位subthreshold potential之上。ps：动作电位的高度被截断，以便更清楚地观察到阈下电位。
2.中间曲线：这是一个模拟的细胞外记录，显示动作电位的双相波形，其振幅约为0.1 mV，远小于细胞内记录的动作电位（约0.1 V）。
3.底部曲线：这是从距离胞体较远的轴突axon内部记录的电位。可以看到完整的动作电位，但阈下电位完全消失，因为它在沿着轴突传播的过程中被衰减掉了。

**从这些曲线中可以看出，动作电位能够在神经元的轴突axon中传播，而阈下电位则无法传播至轴突。
**Action potentials are able to propagate in the axon of a neuron, whereas subthreshold potentials are not able to propagate to the axon.

#subthreshold potential 阈下电位
```

- Neural Propagation 神经传播(的实质)
  - **Spikes**, but not subthreshold  potentials, propagate regeneratively down the axons.
  - **动作电位能够在轴突**中**再生性地传播**，但**阈下电位**在传播时会逐渐衰减，无法沿着轴突远距离传播。



## Abstract Model of a Neuron

![cc96a067812d7fbc33a604e7910c6f3.png](https://s2.loli.net/2024/10/30/6MNDqlKk2P3Lnmx.png)

**Neuron** **j** with n+1 inputs.
Each **input** **i** transmits a real **value** **a~i~**.
Each **connection** is assigned with the  **weight w~ji~**.
**Total input S** = sum of each (weight × value).
**Output X~j~**. (<u>Only 0 未激活 or 1 激活 in Abstract Neuron. Only the spikes are remembered in Biological Neuron.</u>)
**0 is threshold**.

------

![f8d0b41b501ddce02a0d148f1ef21af.png](https://s2.loli.net/2024/10/30/c67eskPOtZdMHE3.png)



## ⭐COMP305 Homework

| 1. Describe the biological computation and the relation with biology. |
| ------------------------------------------------------------ |
| **Biology** is the **motivation** for **biological computation algorithms**, and biological computation algorithms **validate and explore** Biology. Biology includes **natural, experimental, and computational** approaches, while biological computation algorithms include **artificial neural networks** (ANNs), **evolutionary algorithms** and so on. |

| 2. Briefly introduce the neuron signal processing.           |
| ------------------------------------------------------------ |
| **Input Stage**: Neurons receive electrical or chemical signals through their **dendrites** and **soma**. These signals are passed from **presynaptic neurons** via synaptic connections, often involving **neurotransmitter release**. |
| **Integration Stage**: The received signals are integrated in the **soma**. If the total input **exceeds a specific threshold**, the neuron will generate an **action potential**. |
| **Output Stage**: Once the action potential is triggered, it travels down the **axon** to the axon terminals. These neurotransmitters then pass on the signal to the next neurons in the network, continuing the information processing. |

![7241130b377b8559e9ce94a8edc340e.png](https://s2.loli.net/2024/10/30/aGTnes9kY2jiES1.png)

| 3. Briefly describe the relation between a biological neuron and the abstract model shown above. |
| ------------------------------------------------------------ |
| The **input** in the abstract neuron (AN) is similar to the **dendrites** in the biological neuron (BN). |
| The **neuron body** (the circle) in the AN is similar to the **soma** in the BN. |
| The **output** of the AN is similar to the **axon** in the BN. |
| The **threshold** in the AN is similar to the **excitation potential threshold** in the BN. |
| The **weights of input connections** in the AN is similar to the **importance of presynaptic neurons** in the BN. |
| The output of the AN is **either 0 or 1**, but in BN only **spikes** are propagated. |
