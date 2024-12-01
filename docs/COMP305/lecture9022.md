# Lecture 22
<font size="4">Hongye Qian</font> 

### Natural Evolution. Computational Appeal?
![01e1691caba2feb9daa022a846d91a6.png](https://s2.loli.net/2024/12/02/PMgZETCfe3UFXrR.png)
1. **Parallelism**. Every individual in the population is tested independently in parallel with the others, and that speeds up evolution of the population.  
   **并行性**：种群中的每个个体都与其他个体并行独立测试，这加速了种群的进化。

2. **Adaptation to a changing environment**. Due to the natural selection, only those individuals best fitted for the current environment do survive. The selection results in the population as a whole best adapted to the environment. 
由于自然选择，只有那些最适合当前环境的个体才能生存下来。这种选择使种群作为一个整体最能适应环境。

3. **Optimization**.  
Due to the natural selection, only individuals best fitted or “optimal” for the current environment do survive and reproduce. Thus, the selection also performs optimization on an individual level.
由于自然选择，只有最适合当前环境或“最优”的个体才能生存和繁殖。因此，选择也在单个级别上执行优化。

### Genetic Algorithms. Historical Introduction
- **if** a solution of a computational problem might be formulated, *i.e.*, coded, in a form of string of “characters”,  
  **如果**一个计算问题的解可以被表示为一串“字符”的形式，即编码形式
- **then** the optimal solution to the problem might be searched for using the natural selection technique among a “population”, *i.e.*, set of candidate solutions.  
  **那么**问题的最优解可以通过自然选择技术在一个“种群”（即候选解的集合）中进行搜索。
- 1950s-1960s-- several computer scientists independently studied evolutionary systems with the idea to use the algorithm to solve optimisation problems in engineering. 20世纪50年代至60年代，几位计算机科学家独立研究了进化系统，他们的想法是使用该算法来解决工程中的优化问题
- 1960s Rechenberg introduced “evolutionary strategies” as a method to optimize real valued parameters for airfoils.1960年代 Rechenberg 介绍了“进化策略”作为优化翼型实值参数的方法
- 1966–Fogel, Owens, and Walsh developed “evolutionary programming”. They represented candidate solutions to a problem as a finite-state machines evolving by randomly mutating their state-transition diagrams and selecting the fittest. 1966年的今天，福格尔、欧文斯和沃尔什 发展“进化编程”。他们将一个问题的候选解决方案表示为一个有限状态机，通过随机改变它们的状态转换图并选择最适合的来进化。
<br></br>
- **1960s** -- **Genetic Algorithms (GAs)** were invented by **John Holland** of Michigan University and further developed by his students, colleagues, and himself in the 1960s and 1970s.  
  **20世纪60年代** -- **遗传算法 (GAs)** 由密歇根大学的**约翰·霍兰德 (John Holland)** 发明，并在20世纪60年代和70年代由他的学生、同事以及他本人进一步发展。  

  In contrast with “evolutionary strategies” and “evolutionary programming”, Holland was not interested in finding solutions to particular problems, but rather formally studied the phenomenon of adaptation as it occurs in nature and how the algorithm might be used in the computer systems.  
  与“进化策略”和“进化编程”不同，霍兰德并不关注寻找特定问题的解决方案，而是正式研究了自然界中出现的适应现象以及如何在计算机系统中使用该算法。  

- **1975** – Holland’s book *“Adaptation in Natural and Artificial Systems”* presented the genetic algorithm as an abstraction of natural evolution and gave a theoretical framework for adaptation under GA.  
  **1975年** – 霍兰德的著作 *《自然和人工系统中的适应》(Adaptation in Natural and Artificial Systems)* 将遗传算法作为自然进化的抽象，提供了遗传算法下适应性的理论框架。


### GAs by John Holland.
Holland introduced  


- a “population” of **binary strings** which he called **“chromosomes”**.  
  一种**二进制字符串**的“种群”，他称之为**“染色体”**。  

- The “population” evolves using kind of “natural selection” together with the genetics-inspired operators of **crossover, mutation, and inversion**.  
  该“种群”通过类似“自然选择”的方法进化，并结合了基因学启发的操作符：**交叉、突变和倒置**。  

- Bits in a “chromosome” represent genes, and each “gene” is an instance of a particular **“allele”, 0 or 1**.  
  染色体中的比特表示基因，每个“基因”是特定**“等位基因”**的实例，取值为**0 或 1**。  

- The **selection operator** chooses those chromosomes in the population that will be allowed to reproduce, and on average the fitter chromosomes produce more offspring than the less fit ones.  
  **选择操作符**选择种群中允许繁殖的染色体，平均而言，更适应的染色体会比不适应的染色体产生更多的后代。  

- **Crossover** exchanges subparts of two chromosomes.  
  **交叉**是交换两条染色体的部分片段。  

- **Mutation** randomly changes the allele values at some locations in the chromosome.  
  **突变**是随机更改染色体中某些位置的等位基因值。  

- **Inversion** reverses the order of a continuous section of the chromosome rearranging the genes order.  
  **倒置**是反转染色体中某一连续部分的顺序，从而重新排列基因的顺序。

### Coding for Genetic Algorithms
- In contrast with Nature,  
  与自然相比，  

  - there is **no universal code** in GAs,  
    在遗传算法（GAs）中，**没有通用代码**，  

  - every coding is **problem dependent**.  
    每种编码都是**依赖于具体问题**的。  

- The art of coding, though left beyond the scope, is very important in Genetic Algorithms, as from the very beginning the approach depends on whether the problem can be coded as a string of characters at all.  
  编码的艺术虽然超出了范围，但在遗传算法中非常重要，因为从一开始，这种方法就取决于问题是否能完全被编码为一个字符字符串。  

- The above implies serious restrictions on the class of problems capable of solving by GAs.  
  上述内容表明，遗传算法能够解决的问题类别受到严重限制。








