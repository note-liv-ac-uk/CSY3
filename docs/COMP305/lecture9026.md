# Lecture 26
<font size="4">Hongye Qian</font> 


## Topic 4 Similarity Templates . (Schema).
### Schema Theorem.
![dae3242864926105420ea5ba087bc1b.png](https://s2.loli.net/2024/12/04/TJjNP24AHRlneax.png)


### Schema Theorem: Proof.
证明请看lec 26 P14
### How Schema Theorem Works.
 ![45cc920119819b69de91a104b0793e4.png](https://s2.loli.net/2024/12/04/9Mu1mepwKd42Nfb.png)
 - It might be seen that the schema $H_1 = *****11*$ is matched by the first and the second strings.  
  可以看出模式 $H_1 = *****11*$ 被第一和第二个字符串匹配。

- The first string has the fitness of 2, and the second string has the fitness of 6.  
  第一个字符串的适应度为 2，第二个字符串的适应度为 6。

- This schema represents a subset of chromosomes with the average fitness of $4 = \frac{2+6}{2}$.  
  该模式表示一组染色体的子集，其平均适应度为 $4 = \frac{2+6}{2}$。
<br></br>
- It might be seen that the schema $H_2 = 000***10$ is only matched by the first string.  
  可以看出模式 $H_2 = 000***10$ 仅被第一个字符串匹配。

- The first string has the fitness of 2.  
  第一个字符串的适应度为 2。

- This schema represents a subset of chromosomes with the average fitness of 2.  
  该模式表示一组染色体的子集，其平均适应度为 2。 
-  𝐻 will be often chosen by the selection operator and tend to stay and reproduce in the population from generation to generation.
<br></br>

- The defining length of $H_1$ is $\delta(H_1) = 1$.  
  $H_1$ 的定义长度为 $\delta(H_1) = 1$。

- The defining length of $H_2$ is $\delta(H_2) = 7$.  
  $H_2$ 的定义长度为 $\delta(H_2) = 7$。

- Due to the long defining length, $H_2$ has more chances to be destroyed by crossover than the shorter schema $H_1$.  
  由于定义长度较长，$H_2$ 被交叉破坏的机会比较短的模式 $H_1$ 更多。
<br></br>
- The order of $H_1$ is $O(H_1) = 2$.  
  $H_1$ 的阶数为 $O(H_1) = 2$。

- The order of $H_2$ is $O(H_2) = 5$.  
  $H_2$ 的阶数为 $O(H_2) = 5$。

- Due to the high order, $H_2$ has more chances to be destroyed by mutation than the lower order schema $H_1$.  
  由于阶数较高，$H_2$ 被突变破坏的机会比阶数较低的模式 $H_1$ 更多。
- Based on the analysis, we may expect that schema $H_1$ will have more chromosomes to match in the next generation than schema $H_2$.  
  基于分析，我们可以预期模式 $H_1$ 在下一代中匹配的染色体会比模式 $H_2$ 更多。
### Example Implementation of a GA
![1b8346ee8f8f6714831d8470571a7d5.png](https://s2.loli.net/2024/12/04/Ee45dmrjkupRzI6.png)

### Schema Theorem
- **Highly fit**, **short defining length**, **low order** schemas **increase exponentially** in frequency in successive generations.  
  **高度适应性**、**短定义长度**、**低阶模式**在连续的世代中**指数增长**。

- Genetic algorithms can thus often provide high-quality (but not necessarily optimal), heuristic solutions to famously hard problems.  
  因此，遗传算法通常可以提供高质量（但不一定是最优的）的启发式解决方案来解决著名的难题。

- There are many criticisms of the Schema Theorem. For instance, the Schema Theorem cannot distinguish between problems in which genetic algorithms perform poorly, and problems for which genetic algorithms perform well (**Heuristic algorithm**). This is an interesting problem but out of the scope of this module.  
  关于模式定理有许多批评。例如，模式定理无法区分遗传算法表现不佳的问题与遗传算法表现良好的问题（**启发式算法**）。这是一个有趣的问题，但超出了本模块的范围。

## 终于整理完了！！！！！！！









