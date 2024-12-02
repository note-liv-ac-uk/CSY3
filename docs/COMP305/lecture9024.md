# Lecture 24
<font size="4">Hongye Qian</font> 

## topic 4  Basic Genetic Algorithms
### Basic Structure of a Genetic Algorithm
1. Randomly generate initial population of $n$ bit strings ("chromosomes").  
   随机生成由 $n$ 个比特串（“染色体”）组成的初始种群。

2. **Evaluate** the fitness of each string in the population.  
   **评估**种群中每个串的适应度。

3. Repeat the following steps until next generation of $n$ individual produced.  
   重复以下步骤，直到生成 $n$ 个个体的新一代。
   - a. **Select** pair of parent chromosomes from current population according to their fitness, *i.e.* chromosomes with higher fitness are selected more often.  
     根据适应度从当前种群中**选择**一对父代染色体，*即*适应度较高的染色体被更频繁地选择。
   - b. Apply **crossover** (with probability).  
     应用**交叉**（以一定概率）。
   - c. Apply **mutation** (with probability of occurrence).  
     应用**变异**（以一定发生概率）。

4. Apply generational **replacement**.  
   应用代际**替换**。

5. Go to 2 or terminate if termination condition is met.  
   转至步骤 2 或在满足终止条件时终止。

![e593392256f25c1e35a9b13ff4b25da.png](https://s2.loli.net/2024/12/03/NxzDBq5Kh4y283C.png)
### Example Implementation of a GA
- Let length of each chromosome (binary string) $l = 8$.  
  每条染色体（二进制字符串）的长度设为 $l = 8$。

- And the number of chromosomes in the population (population size) $n = 4$.  
  种群中的染色体数量（种群大小）设为 $n = 4$。

- Fitness function $f(x)$ is equal to **the number of ones in the bit string $x$**.  
  适应度函数 $f(x)$ 等于比特串 $x$ 中**1 的个数**。

- Selection operator. Fitness-proportionate selection, that is, the number of times an individual expected to be selected is equal to its fitness $f_i$ divided by the average fitness of the population $\bar{f}$ (also known as **Roulette Wheel Selection**):  
  选择算子。适应度比例选择，即个体被选择的期望次数等于其适应度 $f_i$ 除以种群的平均适应度 $\bar{f}$（也称为**轮盘赌选择**）：
  $$N_i = \frac{f_i}{\bar{f}}.$$

- **Crossover probability**. $p_c = 0.7$.  
  **交叉概率**：$p_c = 0.7$。

- **Mutation probability**. $p_m = 0.001$.  
  **变异概率**：$p_m = 0.001$。

- Make a run of **three generations**.  
  执行**三代**运行。

> **Note**: No specific purpose. Only used to show the effect of a GA.  
> **注意**：无特定目的。仅用于展示遗传算法的效果。
<br></br>

![da4e0bb772f768dc2116c3539f8b875.png](https://s2.loli.net/2024/12/03/co7QlqhA4SZPYHi.png)
<br></br>
![38015ef6661929393e86f0c5bee4358.png](https://s2.loli.net/2024/12/03/LYDnAIwdlFJS2z7.png)
<br></br>
![54ee4d1359a048b488d3430d2638e5c.png](https://s2.loli.net/2024/12/03/d8IS3cXbHpQD6KB.png)
- Thus, chromosome number 1 shall be selected **one time**,  
    因此，染色体编号 1 将被选择 **一次**，  

    chromosome number 2 shall be selected **two times**,  
    染色体编号 2 将被选择 **两次**，  

    chromosome number 3 shall **not be selected at all**,  
    染色体编号 3 将**完全不被选择**，  

    chromosome number 4 shall be selected **one time**.  
    染色体编号 4 将被选择 **一次**。
- **Forming pairs of "parents" for crossover:**  
    **形成用于交叉的“父母”对：**

    1ˢᵗ pair: strings **2** and **1**,  
    **第一对**：字符串 **2** 和 **1**，  

    2ⁿᵈ pair: strings **2** and **4**.  
    **第二对**：字符串 **2** 和 **4**。

<br></br>
### Example Implementation of a GA (crossover)
![9c17cdc09ed5753a3dd18a8e49f176c.png](https://s2.loli.net/2024/12/03/zRtYkXgI7hiQWv4.png)
![39c0f6bf30cd3962235991f2dd53cf6.png](https://s2.loli.net/2024/12/03/sAwL7qFKjWB1kMn.png)

### Example Implementation of a GA (mutation)
![d42b4b360c9c126cc1c0e548659f5e8.png](https://s2.loli.net/2024/12/03/UXC4Dl9HJpnoy32.png)
![e5e655fa4120bb891040d0392d3a7ef.png](https://s2.loli.net/2024/12/03/o3IjKlxad5Ak4Sp.png)

### ### Example Implementation of a GA (replacement)
![b692a067619bbb18a12b5f83f3b994c.png](https://s2.loli.net/2024/12/03/ahKkFqneROJoHXC.png)
![699ca314137f729253202e77eedf0b6.png](https://s2.loli.net/2024/12/03/EarMyqG1XegdQ2t.png)
- 怀疑这里写的有点问题，那个式子7

- All the operations on Generation 0 have been done.Run for the second generation.
***
然后开启下一轮，下一轮就不叙述了，想看的人可以看lec 24 P25
直到终止条件
![8ed0e24c828c35721c830d2110132a4.png](https://s2.loli.net/2024/12/03/J8rKjWikHYG7Znd.png)
- The average fitness in the population of possible solutions increases with every generation




