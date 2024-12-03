# Lecture 25
<font size="4">Hongye Qian</font> 


## Topic 4 Similarity Templates . (Schema).
### Why do GAs work?
- Observation1: similar “looking” chromosomes do have similar fitness values, and therefore are taken for reproduction equally often. 类似“看起来”相似的染色体有相似的适应度值。
  在遗传算法中，染色体表示潜在的解，而**适应度值（fitness value)**用于衡量染色体的质量。这个观察指出，如果两条染色体非常相似，那么它们的适应度值也可能非常接近。
![281ed5eff8c1436adbcee9c065dd231.png](https://s2.loli.net/2024/12/03/tGARTYluHpef7Vn.png)
![a17bdc13c8a022ccd490961ff49a5c5.png](https://s2.loli.net/2024/12/03/YolmHpc3S8VOFsj.png)
<br></br>
- Observation2: A chromosome can be described by a set of “substrings”. Thus, Similar “looking” chromosomes  ⟺ Their “substrings” are similar. 一个染色体可以用一组“子串”来描述。因此，相似“看起来”相似的染色体对应它们的“子串”也相似。
  如果两条染色体“看起来相似”，这通常是因为它们的很多子串是相同的。这种相似性可以用于遗传算法的进化过程，例如在交叉操作中，保留那些表现良好的相似子串，以保持整体适应度较高的特性。
<br></br>
- Observation 1 leads to a fact：类似的染色体有相似的适应度值。
  也就是说，如果我们找到了一些表现良好的染色体，它们之间的相似性可以告诉我们未来的搜索方向，这些相似性通常指向更优的解。
- Combining with Observation 2：类似的染色体意味着它们的子串也相似。
  结合 Observation 2，我们可以得出这样的策略：在寻找最优解时，应该关注相似的子串，这些子串往往代表着有利于优化的特性。
### Similarity Template = Schema
- Holland introduced a
$$similarity \quad template = schema = building \quad block$$
 to describe subset of strings with similarities at certain positions. 
- Definition: A schema is a similarity template describing a subset of strings with similarities at certain string positions. 模式是一个相似性模板，描述在某些字符串位置具有相似性的字符串子集。
<br></br>
- To describe building blocks of binary chromosomes, the following three letter alphabet is used.  
  **为了描述二进制染色体的构建块，使用了以下三字母字母表。**

  $$\{0, 1, *\}$$  
  **这里的 $*$ 是一个通配符符号，即一种** **占位符**，可以解释为多个字面字符。**

- $*$ can be either $0$ or $1$  
  **$*$ 可以是 $0$ 或 $1$**

- **Example**:  
  $111**0$ is a schema of the chromosome $111100$  
  **示例**：  
  $111**0$ 是染色体 $111100$ 的模式。
![5c48641ab705e546136363c0c347a65.png](https://s2.loli.net/2024/12/04/uiVzpyZEWYH3UfS.png)
![266b6b4937516d32dccf89990c02719.png](https://s2.loli.net/2024/12/04/MUZu9DQXlxnwJoc.png)
<br></br>
- **Question**: How many building blocks are there in a particular chromosome of a fixed length $l$?  
  **问题**：在长度为 $l$ 的特定染色体中有多少个构建块？

- **Answer**:  
  **回答**：  
  To match a particular chromosome of a fixed length the schema must  
  **要匹配固定长度的特定染色体，模式必须：**  
  a) be of the same length,  
  **a) 长度相同，**  
  b) have either  
  **b) 并且具备以下两种可能之一：**  
  - the same symbol as the chromosome does or  
    **- 与染色体相同的符号，或者**  
  - an $*$ – placeholder symbol - at any particular locus  
    **- 一个 $*$（占位符符号）可以位于任何特定位置。**

- **Thus**, in a binary chromosome of a length $l$ there are $2^l$ building blocks, as a symbol at a particular locus in the chromosome must correspond to the same or the **placeholder** symbol in the corresponding locus in the schema.  
  **因此**，在长度为 $l$ 的二进制染色体中，有 $2^l$ 个构建块，因为染色体中特定位置的符号必须对应于模式中相应位置的相同符号或占位符符号。
![10a7ec5c57e71446c662094549bebf4.png](https://s2.loli.net/2024/12/04/tZF2BSQCq3fuO5H.png)
<br></br>
- **Definition**:  
  **定义**：  
  The **Order** of a schema $H$ is represented as $O(H)$, denoting the **number of defining symbols** (non-$*$ symbols) it contains.  
  **模式 $H$ 的阶**记为 $O(H)$，表示其中**定义符号**（非 $*$ 符号）的数量。

- **Example 5**: Order of the schema $10*00***$ is 4.  
  **例 5**：模式 $10*00***$ 的阶是 4。

- **Example 6**: Order of the schema $********$ is 0.  
  **例 6**：模式 $********$ 的阶是 0。

- **One might say** that the order of the schema $********$ is lower than the order of the schema $10*00***$.  
  **可以说**模式 $********$ 的阶低于模式 $10*00***$ 的阶。

<br></br>
- **Definition**:  
  **定义**：  
  The **defining length** of a schema $H$ is represented as $\delta(H)$, denoting the **maximum distance** between two **defining symbols**.  
  **模式 $H$ 的定义长度**记为 $\delta(H)$，表示两个**定义符号**之间的**最大距离**。

- **Example 7**: The defining length of the schema $H = 10*00***$ is 4.  
  **例 7**：模式 $H = 10*00***$ 的定义长度为 4。

  - Farthest defining (non-$*$) symbols: $10*00***$  
    最远的定义符号（非 $*$）：$10*00***$

  - Index 1 and Index 5  
    索引为 1 和 5

  - $\delta(H) = 5 - 1 = 4$  
### Schema Theorem.
- **Highly fit**, **short defining length**, **low order schemas** increase **exponentially** in frequency in successive generations.  
  **高度适应的**、**短定义长度的**、**低阶模式**在连续的世代中以**指数方式**增加其频率。










