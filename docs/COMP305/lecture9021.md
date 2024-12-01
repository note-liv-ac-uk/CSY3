# Lecture 21
<font size="4">Hongye Qian</font> 

## Genetic Algorithms
### Biological Motivation
### Darwinian Theory of Evolution (Macroscope)


- **Species adapt to the environment via natural selection.**  
  物种通过自然选择适应环境。

- **The selection favours those species for survival and further evolution that are best adapted to the environmental condition – "survival of the fittest".**  
  自然选择青睐那些最能适应环境条件的物种，以保证其生存和进一步进化——“适者生存”。

- **Phenotype is the manner of response and physical embodiment of an individual.**  
  表型是个体响应和物质体现的方式。  
  **There occur small, apparently random and undirected variations between the phenotypes of parents and their offspring.**  
  父母和子代的表型之间会出现细微的、表面上随机且无方向性的变异。

- **These mutations prevail through selection, if they prove their worth in the current environment; otherwise they perish.**  
  如果这些突变能在当前环境中证明其价值，就会通过选择而保留下来；否则就会消亡。
  <br>
- **Production of offspring is the basic driving force for selection.**  
  繁殖后代是选择的基本驱动力。

- **In a favourable environment, population grows exponentially. This growth is generally limited by finite resources.**  
  在有利的环境中，种群呈指数增长。然而，这种增长通常受到有限资源的限制。

- **When resources are no longer sufficient to support all individuals in a population, only the fittest, i.e., those most effectively utilizing the resources, survive and produce offspring.**  
  当资源不足以支持种群中所有个体时，只有最适者，即最有效利用资源的个体，能够生存并繁殖后代。  
  *In an unkind environment, organisms in a population are at a selective advantage to utilize resources most effectively.*  
  在恶劣的环境中，种群中的生物因最有效地利用资源而具有选择优势。
### Neo-Darwinism Theory of Evolution (Microscope)
![3821b0f2a85c9a423e7ba0dca41e550.png](https://s2.loli.net/2024/12/02/G6PNQlV3pKAarSv.png)
- **All living organisms consist of _cells_**  
  **所有的生物都由细胞组成。**

- **Each cell in an organism contains the same set of one or more _chromosomes_ –**  
  **一个生物体中的每个细胞都包含一组相同的一个或多个染色体。**

- **Chromosomes are strings of _DNA_ that serve as a _blueprint_ for the organism.**  
  **染色体是由 DNA 构成的链，它为生物体提供了蓝图。**

### DNA Structure
 A chromosome can be conceptually divided into genes --Gene is a functional block of DNA coding a particular protein. 从概念上讲，染色体可以分为基因——基因是编码特定蛋白质的DNA的功能块。

### DNA Code
自己看lec21 P12,高中选生物的，这里应该都不需要怎么看。
### DNA Code. Crossing-Over (Recombination)
- **Organisms with unpaired sets of chromosomes are called _haploid_.**  
  **具有不成对染色体组的生物被称为单倍体。**

- **Organisms, whose chromosomes are arranged in pairs are called _diploid_. Most sexually reproducing organisms are diploid.**  
  **染色体成对排列的生物被称为二倍体。大多数有性繁殖的生物是二倍体。**

- **During sexual reproduction, _crossing-over_ or _recombination_ of genes in parent chromosomes occurs. In each parent cell, a pair of chromosomes first doubles, then the chromosomes exchange genes,**  
  **在有性繁殖过程中，亲代染色体中的基因会发生交叉或重组。在每个亲代细胞中，一对染色体首先加倍，然后染色体交换基因，**

  **and finally produce four _gametes_, single chromosomes, ready to couple with the other parent gametes to form a new diploid cell.**  
  **最终产生四个配子（单条染色体），准备与另一亲代的配子结合形成一个新的二倍体细胞。**

  **_Formation of gametes (Meiosis)._**  
  **配子的形成（减数分裂）。**
![de891dc3278422e42e8b4cda91861c3.png](https://s2.loli.net/2024/12/02/Htp5Vrnc74eYPiq.png)
- **Mutation** is a random change of a "letter", single nucleotide in a chromosome.  
  **突变**是染色体中单个核苷酸（“字母”）的随机变化。

- **Mutations usually result from copying errors in parent chromosomes and then are reproduced in offspring.**  
  **突变通常源于亲代染色体复制错误，并在后代中重现。**

### Neo-Darwinism Theory of Evolution (Microscope)
![d517b8a439a9226efffa51bbfc42a26.png](https://s2.loli.net/2024/12/02/ufZpJtH5M2QXVak.png)
- **Gene** is a functional block of DNA *coding* a particular protein, see "gene encodes *a trait*, e.g. eye colour".  
  **基因**是DNA的功能模块，用于**编码**特定的蛋白质，例如“基因编码**一种特征**，如眼睛颜色”。

- **Different possible settings for a trait**, e.g. blue, brown, black eye colour, are called **alleles**.  
  **特征的不同可能设置**，例如蓝色、棕色、黑色眼睛颜色，称为**等位基因**。

- **Each gene is located at a particular locus** (position) on the chromosome.  
  **每个基因位于染色体上的特定**位置**（位点）。
- The complete collection of all genetic material, that is all chromosomes taken together, is called the organism’s genome or genotype.
- Genes are transfer units of heredity. Genes are occasionally changed by mutations. 基因有可能会被突变改变
- **Phenotype** expresses complex interaction within the genotype as well as its interaction with environment. 
- Selection acts on an individual, thus an individual <u>is a selection unit.</u>
- **Population** is the **evolving unit**. Population as a unit confines a common gene pool including genotypes of all individuals. 人口是进化的单位。人口作为一个单位限制了一个共同的基因库包括所有个体的基因型。
### Natural Evolution. What Is the Fitness?


- **Individual fitness** is measured *indirectly* as the individual growth rate in comparison to others.  
  **个体适应性**通过与他人比较的个体增长率*间接*衡量。

  The fitness **is the individual propensity to survive and reproduce in a particular environment**.  
  适应性是**个体在特定环境中生存和繁殖的倾向**。

- Thus, **Natural Selection** according to the individual fitness  
  因此，根据个体适应性的**自然选择**：
  - **is NOT** an active driving force,  
    **不是**一种主动驱动的力量，
  - **is differential survival and reproduction within a population**.  
    是种群内的**差异性生存和繁殖**。


