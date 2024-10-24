# Lecture 7
<font size="4">Hongye Qian</font> 

### Topic 2 The McCulloch-Pitts Neuron (1943)
#### 1. Propositional Logic
- It deals with propositions (which can be true or false) and relations between propositions, including the construction of arguments based on them. 可以是真或假的语句。
- Compound propositions are formed by connecting propositions by logical connectives. 复合命题：由逻辑联结词连接的命题。
- Propositions that contain no logical connectives are called atomic propositions. 原子命题：不含任何逻辑联结词的基本命题。
- Unlike first-order logic, propositional logic does NOT non-logical objects, predicates about them, or quantifiers. 与一阶逻辑不同，命题逻辑不处理非逻辑对象、关于它们的谓词或量词。
- Operations: AND, OR, NOT, Implies (→)
- The McCulloch-Pitts Neuron可以表示AND, OR, NOT。之前的笔记有写。
- An MP neural network ***can implement*** any ***multivariable propositional logic function***, with the thresholds and weights being appropriately selected.
- Furthermore, the discrete time, or unity delay property of the model makes iteven possible to build a sequential digital circuitry. 这俩之前笔记有
  ![ae4c8feedb7e44aa9639e851786ddd1.png](https://s2.loli.net/2024/10/24/bWVDIE5M8BJ6nTy.png)

#### 2. An Example
$X = a_1 \land a_2 \lor \neg a_3$
![329a2d054b6320138f258a5c99adfd6.png](https://s2.loli.net/2024/10/24/7arNXY5BgnjDtdL.png)
- step1: $X = a_1 \land a_2$
- step2: $\neg a_3$

![cb2ffa98497b46f244fcca08c019525.png](https://s2.loli.net/2024/10/24/Bc8OdlxDHvMotk9.png)
- step3: $X = a_1 \land a_2 \lor \neg a_3$

#### 2. MP Neuron Conclusion
- The McCulloch and Pitts neuron model included all necessary
 elements to perform logic operations, and thus MP-neuron could function as an ***arithmetic-logic computing element to compute any computable function***.
-  Though the threshold elements are, from the combinatorial point of view, more versatile than conventional logic gates, there was a problem with assumed unlimited fan-in (number of inputs of a logic gate): ***the implementation of the compact electronic model was not feasible in the 
days of bulky vacuum tubes.*** 人话：尽管理论上这些阈值元件比传统逻辑门有优势，但在当时由于技术限制（真空管的体积和复杂度），无法实现它们的实际应用。
-  Now-days a possible way of overcoming the hardware difficulties could be the use of ***optical computing elements*** capable of providing unlimited fan-in by changing the angle of lens.
-  1. The network must be completely specified before its using. 网络必须在使用之前完全指定：这意味着模型的结构和所有参数必须在开始之前明确设定好，不能动态调整。
-  2. There were no free parameters to suit different problems. 没有自由参数（no free parameters）：模型中没有可根据不同问题进行调整的参数，缺少灵活性来适应各种不同的问题。
-   Learning can only be implemented by modifying the connection pattern of the network, which is necessarily more complex than just adjusting numerical parameters. 因此，模型的学习过程只能通过修改网络的连接模式来实现，这比简单地调整数值参数复杂得多。
  





















