# Lecture 23
<font size="4">Hongye Qian</font> 


## Topic 3 Genetic Algorithms Terminology
### GAs by John Holland: Chromosomes.
 **Definition**:  General Genetic Algorithm’s Chromosome is a string of characters, coding a candidate solution for a particular problem.
- Often the GA chromosome is defined as a Fixed length binary string, e.g. "1100001001010101111"
- The same as nature blindly operates on real chromosomes and does not know or care what information is actually coded in the chromosomes, Holland had left behind the question of what particular information and in what way was coded in the strings of the Genetic Algorithms chromosomes. 就像大自然盲目地作用于真实的染色体，并不知道或关心染色体中编码了什么信息一样，霍兰德留下了一个问题，即遗传算法的染色体串中编码了哪些特定的信息，以及以何种方式编码了哪些信息。
-  Haploid organisms, i.e., the organisms with on-paired chromosomes are considered in the Genetic Algorithms for some operators, e.g., crossover. 单倍体生物，即染色体配对的生物，在遗传算法中考虑了一些算子，如交叉。
-  GAs chromosome coincides with genotype, that is the genotype consists of a single chromosome. GAs染色体与基因型一致，即基因型由一条染色体组成。
-  For simplicity, there is no phenotype concept in Genetic Algorithms either, and therefore we do not distinguish the following concepts:
$$GAs \quad chromosome  =  GAs \quad genotype  =  GAs \quad organism $$
- For example: “1001001100001101”, “1001111100001101”, “1001100000001101”, “1001101100001101”, …  它也被称为 **候选解的种群 (population of candidate solutions)**。
- A GA chromosome“1100001001010101111”, 
  - In a GAs chromosome, a character represents a gene.
  - **Possible settings for a gene are called alleles**, e.g., in the example above the alleles are 0s and 1s, and if a gene codes a trait then an allele is the trait instance.  
  For binary chromosomes, the alleles "alphabet" consists of just two characters, 0 and 1. There might be bigger "alphabets" to represent a bigger number of alleles.  
  **基因可能的设置被称为等位基因 (alleles)**，例如，在上面的例子中，等位基因是0和1，如果一个基因编码一个特征，那么一个等位基因就是特征的实例。  
  对于二进制染色体，等位基因的“字母表”仅由两个字符0和1组成。可能存在更大的“字母表”来表示更多的等位基因。
  - **Position of a gene in the string is called locus of the gene**.  
  **基因在字符串中的位置被称为基因的位点 (locus)**。

### GAs by John Holland: Crossover
![77feec7e6f1016ddb27cf1b6a630784.png](https://s2.loli.net/2024/12/03/2EGWN1z4ua7QiZk.png)

我觉得高中选生物的这个地方应该都不需要咋看了。

- The crossover cutting point is chosen randomly. 
- One-point crossover is considered most often. 

### GAs by John Holland: Mutation
![3373a81295087db05a45de29a5aa2c0.png](https://s2.loli.net/2024/12/03/D7ouaJGOLgSHpnb.png)

### GAs by John Holland: Inversion and Translocation
![57c085062b0f28c726d04b6a3081175.png](https://s2.loli.net/2024/12/03/9eoGaUMh8VmqC2P.png)

### GAs by John Holland: Fitness Function.
![0e557b3b77c40baf87c3d1b5990992c.png](https://s2.loli.net/2024/12/03/GmIcoYKERr7DjP5.png)
-  To evaluate a chromosome fitness, that is how good the candidate solution solves the problem, a Genetic Algorithm uses fitness function. 
   遗传算法使用适应度函数来评估染色体的适应度，即候选解对问题的解决程度。
- The fitness function
  - Takes a chromosome as an input;
  - Produces its quantitative fitness evaluation as an output.
  - The same as thata particular code to be used for coding a problem solution in a form of GAs chromosomes depends on the problem itself, a particular form of the fitness function also depends on the problem to be solved. 就像在GAs染色体的形式中用于编码问题解决方案的特定代码取决于问题本身一样，适应度函数的特定形式也取决于要解决的问题。
  

  - **Example**: maximize the real-valued function  
    $$f(y) = y + |\sin(32y)|, \quad 0 < y < \pi$$  
    here the candidate solutions are values of $y$.  
    **示例**: 最大化实值函数  
    $$f(y) = y + |\sin(32y)|, \quad 0 < y < \pi$$  
    这里候选解是 $y$ 的值。

  - **Fitness function**: $$f(x) = x + |\sin(32x)|$$,  
    $x$ is the binary chromosome that codes $y$.  
    **适应度函数**: $$f(x) = x + |\sin(32x)|$$，  
    $x$ 是编码 $y$ 的二进制染色体。
    ![fa96e9f10a17123129083468e0c5e07.png](https://s2.loli.net/2024/12/03/FwfJqOZCg5W9GVA.png)


  - Specifically, we may use approximate fitness function when:  
    具体来说，当以下情况时，我们可以使用近似适应度函数：  

    - Precise fitness function is extremely time-consuming;  
    精确适应度函数极其耗时；  

    - Precise fitness function is missing or hardly obtained;  
    精确适应度函数缺失或难以获取；  

    - Precise fitness function model itself contains uncertainties.  
    精确适应度函数模型本身包含不确定性。
<br></br>
  - The same as in nature, in GAs **Population** of chromosomes is the *evolving unit*.  
  与自然界相同，在遗传算法（GAs）中，**种群（Population）** 是进化的单位。  

  - The GAs population evolves from one **generation** of chromosomes to the next generation and so on.  
    遗传算法中的种群从一代染色体进化到下一代，如此循环。
    ![763ae6d74652310288b70a6d2658e08.png](https://s2.loli.net/2024/12/03/fRVlNPACJupG26a.png)

### GAs by John Holland: Selection Operator.
- To simulate natural evolution of population of chromosomes, there must be a **rule how to choose which chromosome is more likely to produce offspring for the next generation**.  
  为了模拟染色体种群的自然进化，必须有一个**规则来选择哪条染色体更可能为下一代产生后代**。  

- We shall call that rule a **selection operator**.  
  我们将这种规则称为**选择算子（selection operator）**。  

- Usually, a selection operator is defined in a way that better fitted chromosome is selected for reproduction more often and therefore will produce more offspring.  
  通常，选择算子以一种方式定义，使得更适应的染色体被更频繁地选择用于繁殖，因此会产生更多的后代。
### GAs by John Holland: Search Space.

- As Genetic Algorithms are to search for the best possible solution to a problem, it was natural to introduce the concept of a Search Space for the algorithms.  
  由于遗传算法旨在为问题寻找最佳可能解，因此引入搜索空间的概念是很自然的。  

  **Definition:**  
  **Set of all possible solutions to a problem in consideration is called a Genetic Algorithm search space.**  
  **考虑中的问题的所有可能解决方案的集合被称为遗传算法搜索空间（Genetic Algorithm search space）。**

- Thus, we search through the search space of possible solutions for the best solution to the problem.  
  因此，我们在可能解决方案的搜索空间中寻找问题的最佳解决方案。
### GAs by John Holland: Fitness Landscape.
![c48f6c706c2f47e77f205626da0a640.png](https://s2.loli.net/2024/12/03/NLt5AYjGZvuUdWT.png)


- A fitness landscape is a representation of all possible solutions along with their fitness.  
  适应度景观是所有可能解决方案及其适应度的表示。

- The candidate solutions are represented by points in the coordinate plane, *i.e.* the search space, and corresponding fitness is measured along an additional dimension.  
  候选解决方案用坐标平面上的点表示，即搜索空间，相应的适应度沿额外维度测量。
- There will be "peaks", "hills", and "valleys" resembling features of physical landscapes.  
  会有类似于物理景观特征的“山峰”、“山丘”和“山谷”。

- **Evolution causes populations move towards the peaks of the fitness landscape.**  
  **进化使种群朝着适应度景观的峰顶移动。**


