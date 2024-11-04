# Lecture 2
<font size="4">Hongye Qian</font> 

#### 1. Vector
![acada88cdd4764aa556df02f8c782df.png](https://s2.loli.net/2024/11/04/blErutigjL9fcDI.png)
![60f7e2b69dec000f35dc5051ba19f63.png](https://s2.loli.net/2024/11/04/ABGxKf9thC1bOLm.png)
1. **数乘（Scalar Multiplication）**：对于一个 \( k \) 维向量 \( \mathbf{y} \) 和一个标量（数值） \( c \)，数乘定义为一个新的 \( k \) 维向量 \( \mathbf{z} \)，记作 \( \mathbf{z} = c \mathbf{y} \) 或 \( \mathbf{z} = \mathbf{y} c \)。其中每个分量 \( z_j \) 的值是 \( \mathbf{y} \) 的对应分量乘以标量 \( c \)，即$$z_j = c y_j$$
2. **向量加法（Vector Addition）**：对于两个 \( k \) 维向量 \( \mathbf{x} \) 和 \( \mathbf{y} \)，向量加法定义为一个新的 \( k \) 维向量 \( \mathbf{z} \)，记作 \( \mathbf{z} = \mathbf{x} + \mathbf{y} \)。其中 \( \mathbf{z} \) 的每个分量是 \( \mathbf{x} \) 和 \( \mathbf{y} \) 的对应分量之和，即
   $$
   z_j = x_j + y_j
   $$
<u>y and x must have the same dimensions for vector addition. </u>

#### 2. Matrices
1. **矩阵的定义**：矩阵是一个由数字组成的矩形阵列，表示为
   $$
   A = \begin{bmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ a_{m1} & a_{m2} & \cdots & a_{mn} \end{bmatrix}
   $$
   其中，矩阵 \( A \) 的 **维度(dimension)** 是 \( m \times n \)，表示为 \( m \) 行 \( n \) 列。

2. **方阵（Square Matrix)**：如果 \( m = n \)，即行数和列数相等，则称矩阵 \( A \) 为方阵。

3. **矩阵元素（Elements of a Matrix）**：矩阵中的每个数 \( a_{ij} \) 被称为矩阵 \( A \) 的元素。

4. **矩阵相等（Matrix Equality）**：如果两个矩阵 \( A \) 和 \( B \) 具有相同的维度，并且对应的元素相等，即对于所有的 \( i \) 和 \( j \)，都有 \( a_{ij} = b_{ij} \)，则称 \( A = B \)。

- **Vectors as special cases of matrices**
1. **列向量（Column Vector）**：一个 \( k \times 1 \) 的矩阵称为列向量。

2. **行向量（Row Vector）**：一个 \( 1 \times k \) 的矩阵称为行向量。

3. **行向量的定义**：矩阵 \( A \) 中第 \( i \) 行的元素构成一个行向量，表示为
   $$
   A^i = \begin{bmatrix} a_{i1} & a_{i2} & \cdots & a_{in} \end{bmatrix}
   $$

4. **列向量的定义**：矩阵 \( A \) 中第 \( j \) 列的元素构成一个列向量，表示为
   $$
   A_j = \begin{bmatrix} a_{1j} \\ a_{2j} \\ \vdots \\ a_{mj} \end{bmatrix}
   $$

1. **矩阵的数乘（Scalar Multiplication）**：对于矩阵 \( A \) 和实数 \( c \)，矩阵的数乘定义为一个新矩阵 \( B \)，记作 \( B = cA \) 或 \( B = Ac \)，其元素 \( b_{ij} \) 表示为 \( b_{ij} = c a_{ij} \)。
   **示例**：
   $$
   3 \begin{bmatrix} 0 & 1 & -2 \\ 4 & -1 & 3 \end{bmatrix} = \begin{bmatrix} 0 & 3 & -6 \\ 12 & -3 & 9 \end{bmatrix}
   $$

2. **矩阵的加法（Addition of Matrices）**：对于两个维度相同的矩阵 \( A \) 和 \( B \)，矩阵加法定义为一个新矩阵 \( C \)，记作 \( C = A + B \)，其元素 \( c_{ij} \) 表示为 \( c_{ij} = a_{ij} + b_{ij} \)。
   **示例**：
   $$
   \begin{bmatrix} 7 & -1 & 12 \\ 0 & 6 & -3 \end{bmatrix} + \begin{bmatrix} 2 & 1 & -8 \\ 4 & 6 & 0 \end{bmatrix} = \begin{bmatrix} 9 & 0 & 4 \\ 4 & 12 & -3 \end{bmatrix}
   $$

3. **注意**：如果矩阵 \( A \) 和 \( B \) 的维度不同，则 \( A + B \) 是未定义的。

-  **Product of matrices**
1. **矩阵乘法定义**：对于一个 \( m \times p \) 的矩阵 \( A \) 和一个 \( p \times n \) 的矩阵 \( B \)，它们的乘积定义为一个新的 \( m \times n \) 的矩阵 \( C \)，记作 \( C = AB \)，其中矩阵 \( C \) 的元素 \( c_{ij} \) 表示为
   $$
   c_{ij} = \sum_{k=1}^{p} a_{ik} b_{kj}
   $$

2. **示例**：
   $$
   \begin{bmatrix} 2 & 6 & -3 \\ 1 & 4 & 0 \end{bmatrix} \begin{bmatrix} 1 & 2 \\ 0 & -3 \\ 3 & 1 \end{bmatrix} = \begin{bmatrix} 2 \cdot 1 + 6 \cdot 0 - 3 \cdot 3 & 2 \cdot 2 + 6 \cdot -3 - 3 \cdot 1 \\ 1 \cdot 1 + 4 \cdot 0 + 0 \cdot 3 & 1 \cdot 2 + 4 \cdot -3 + 0 \cdot 1 \end{bmatrix}
   $$
   $$
   = \begin{bmatrix} -7 & -17 \\ 1 & -10 \end{bmatrix}
   $$

- **Inner product**
1. **矩阵乘法的条件**：如果矩阵 \( A \) 的列数不等于矩阵 \( B \) 的行数，那么 \( AB \) 是未定义的。

2. **内积**：如果 \( \mathbf{x} \) 是一个 \( m \) 维的行向量，\( \mathbf{y} \) 是一个 \( m \) 维的列向量，那么特殊情况
   $$
   \mathbf{x} \mathbf{y} = \sum_{i=1}^{m} x_i y_i
   $$
   称为向量 \( \mathbf{x} \) 和 \( \mathbf{y} \) 的**内积（Inner Product）**。

3. **矩阵元素的计算**：在这种情况下，矩阵 \( C = AB \) 的元素 \( c_{ij} \) 可以通过将矩阵 \( A \) 的第 \( i \) 行和矩阵 \( B \) 的第 \( j \) 列的内积求得。

- Transpose of a matrix
1. **矩阵的转置定义**：一个 \( m \times n \) 的矩阵 \( A \) 的转置，记作 \( A^T \)，是通过将 \( A \) 的行和列互换得到的 \( n \times m \) 矩阵。

   **示例 1**：
   $$
   \begin{bmatrix} 2 & 6 & -3 \\ 1 & 4 & 0 \end{bmatrix}^T = \begin{bmatrix} 2 & 1 \\ 6 & 4 \\ -3 & 0 \end{bmatrix}
   $$

2. **示例 2**：列向量的转置是一个行向量（反之亦然）：
   $$
   \begin{bmatrix} 1 \\ -3 \\ 5 \end{bmatrix}^T = \begin{bmatrix} 1 & -3 & 5 \end{bmatrix}
   $$

- Properties
1. **加法的交换律**：
   $$
   A + B = B + A
   $$

2. **加法的结合律**：
   $$
   (A + B) + C = A + (B + C)
   $$

3. **乘法的结合律**：
   $$
   A(BC) = (AB)C
   $$

4. **分配律**：
   $$
   A(B + C) = AB + AC
   $$

5. **转置的性质 1**：
   $$
   (A^T)^T = A
   $$

6. **转置的性质 2**：
   $$
   (AB)^T = B^T A^T
   $$

7. **对称矩阵（Symmetric Matrix）**：一个 \( n \times n \) 的方阵 \( A \) 是对称的，当且仅当 \( A = A^T \)，或等价地，对于所有的 \( i \) 和 \( j \)，满足 \( a_{ij} = a_{ji} \)。
   
   **示例**：
   $$
   \begin{bmatrix} 1 & 2 \\ 2 & 1 \end{bmatrix}, \quad \begin{bmatrix} 1 & -3 & 5 \\ -3 & 0 & 7 \\ 5 & 7 & 4 \end{bmatrix}
   $$

- **Example**
令
$$
\mathbf{x} = \begin{bmatrix} 2 \\ 1 \end{bmatrix}, \quad \mathbf{y} = \begin{bmatrix} -1 \\ 0 \\ 3 \end{bmatrix}, \quad A = \begin{bmatrix} 4 & 0 & 1 \\ 1 & 2 & -2 \end{bmatrix}
$$

1. **计算 \( \mathbf{x}^T A \)**：
   $$
   \mathbf{x}^T A = \begin{bmatrix} 2 & 1 \end{bmatrix} \begin{bmatrix} 4 & 0 & 1 \\ 1 & 2 & -2 \end{bmatrix} = \begin{bmatrix} 9 & 2 & 0 \end{bmatrix}
   $$

2. **计算 \( A \mathbf{y} \)**：
   $$
   A \mathbf{y} = \begin{bmatrix} 4 & 0 & 1 \\ 1 & 2 & -2 \end{bmatrix} \begin{bmatrix} -1 \\ 0 \\ 3 \end{bmatrix} = \begin{bmatrix} -1 \\ -7 \end{bmatrix}
   $$

3. **计算 \( \mathbf{x}^T A \mathbf{y} \)**：
   - 使用 \((\mathbf{x}^T A) \mathbf{y}\)：
     $$
     \mathbf{x}^T A \mathbf{y} = \begin{bmatrix} 9 & 2 & 0 \end{bmatrix} \begin{bmatrix} -1 \\ 0 \\ 3 \end{bmatrix} = -9
     $$
   - 或者使用 \(\mathbf{x}^T (A \mathbf{y})\)：
     $$
     \mathbf{x}^T A \mathbf{y} = \begin{bmatrix} 2 & 1 \end{bmatrix} \begin{bmatrix} -1 \\ -7 \end{bmatrix} = -9
     $$

- 令 \( \mathbf{x} \) 为 \( m \) 维向量，\( \mathbf{y} \) 为 \( n \) 维向量。
- 令 \( A \) 为 \( m \times n \) 的矩阵。
- 则 \( A \mathbf{y} \) 是一个 \( m \) 维向量，且 \( A^T \mathbf{x} \) 是一个 \( n \) 维向量。
- 我们用 \( (A \mathbf{y})_i \) 表示 \( A \mathbf{y} \) 的第 \( i \) 个分量（\( A^T \mathbf{x} \) 的分量表示类似）。

由此我们有：

1. \( A \mathbf{y} \) 的第 \( i \) 个分量：
   $$
   (A \mathbf{y})_i = \sum_{j=1}^{n} a_{ij} y_j
   $$

2. \( A^T \mathbf{x} \) 的第 \( j \) 个分量：
   $$
   (A^T \mathbf{x})_j = \sum_{i=1}^{m} a_{ij} x_i
   $$

3. \( \mathbf{x}^T A \mathbf{y} \) 的计算：
   $$
   \mathbf{x}^T A \mathbf{y} = \sum_{i=1}^{m} x_i (A \mathbf{y})_i = \sum_{i=1}^{m} \sum_{j=1}^{n} a_{ij} x_i y_j
   $$

- 请注意，\( \mathbf{x}^T A \mathbf{y} \) 是一个标量，因此：

  $$
  \mathbf{x}^T A \mathbf{y} = (\mathbf{x}^T A \mathbf{y})^T = (\mathbf{A} \mathbf{y})^T (\mathbf{x}^T)^T = \mathbf{y}^T A^T \mathbf{x} = \sum_{j=1}^{n} \sum_{i=1}^{m} a_{ij} x_i y_j
  $$

- 同样地：

  $$
  \mathbf{x}^T A \mathbf{y} = (A^T \mathbf{x})^T \mathbf{y} = (\mathbf{y}^T A^T \mathbf{x}) = \mathbf{y}^T A^T \mathbf{x} = \sum_{j=1}^{n} \sum_{i=1}^{m} a_{ij} x_i y_j
  $$

- 此外，还可以写成：

  $$
  \mathbf{y}^T A^T \mathbf{x} = \sum_{j=1}^{n} y_j (A^T \mathbf{x})_j = \sum_{j=1}^{n} \sum_{i=1}^{m} a_{ij} x_i y_j
  $$

#### 3. Bimatrix games
- 回顾一下，一个有限的、非合作性策略博弈 \( \Gamma = \langle N, (S_i)_{i \in N}, (u_i)_{i \in N} \rangle \) 包含以下组成部分：
  1. 一个有限的玩家集合 \( N \)，
  2. 每个玩家 \( i \in N \) 的纯策略（pure strategies）集合 \( S_i \)，其中 \( S_i \) 是非空有限集，
  3. 每个玩家 \( i \in N \) 的收益函数（payoff function）\( u_i : \times_{i \in N} S_i \rightarrow \mathbb{R} \)，将每种策略组合（每个玩家选择一种策略）映射到一个实数。

- **双矩阵博弈**是一类特殊的两人博弈：
  - 玩家数量 \( |N| = 2 \)。
  - 收益函数可以用两个 \( m \times n \) 的实矩阵 \( A \) 和 \( B \) 描述，其中 \( m = |S_1| \) 和 \( n = |S_2| \)。
- **Example**
- 考虑“石头-剪刀-布”游戏：
  - 两个孩子同时选择三个选项之一：石头、剪刀或布。
  - 石头胜剪刀，剪刀胜布，布胜石头。
  - 如果两人选择相同选项，游戏平局。

- 我们将此游戏表示为一个双矩阵博弈：
  - 用 \( R \)、\( S \)、\( P \) 分别表示石头、剪刀、布的选项。
  - 胜利的得分为 +1，失败的得分为 -1，平局得分为 0。
该游戏的收益可以通过以下收益表来描述：

|     | R   | S     | P     |
|-----|-----|-------|-------|
| **R** | 0, 0 | 1, -1 | -1, 1 |
| **S** | -1, 1 | 0, 0  | 1, -1 |
| **P** | 1, -1 | -1, 1 | 0, 0  |

- 行表示第一位玩家的选择。
- 列表示第二位玩家的选择。
- 在每个单元格中，第一个数字表示第一位玩家的得分，第二个数字表示第二位玩家的得分。

例如：
- 当第一位玩家选择石头 $R$ ，第二位玩家选择布 $P$ 时，第一位玩家得分为 -1，第二位玩家得分为 1。

- 该博弈称为双矩阵博弈，因为收益表实际上是由两个矩阵组合而成的：
  $$
  A = \begin{bmatrix} 0 & 1 & -1 \\ -1 & 0 & 1 \\ 1 & -1 & 0 \end{bmatrix} \quad B = \begin{bmatrix} 0 & -1 & 1 \\ 1 & 0 & -1 \\ -1 & 1 & 0 \end{bmatrix}
  $$

- 每个矩阵的每一行对应第一位玩家的一种纯策略（选择）。
- 每个矩阵的每一列对应第二位玩家的一种纯策略。
- 矩阵 \( A \) 的元素 \( a_{ij} \) 表示当第一位玩家选择第 \( i \) 个策略，且对手选择第 \( j \) 个策略时，第一位玩家的得分。
- 矩阵 \( B \) 的元素 \( b_{ij} \) 表示当第二位玩家选择第 \( j \) 个策略，且对手选择第 \( i \) 个策略时，第二位玩家的得分。

- ***Definition***: 
- 双矩阵博弈由一对矩阵表示，即 \( \Gamma = (A, B) \)，其中：
  - 矩阵 \( A \) 和 \( B \) 的 \( m \) 行代表第一位玩家（行玩家）的纯策略。
  - 矩阵 \( A \) 和 \( B \) 的 \( n \) 列代表第二位玩家（列玩家）的纯策略。
  - 当行玩家选择第 \( i \) 个策略，列玩家选择第 \( j \) 个策略时，行玩家得到的收益是 \( a_{ij} \)，列玩家得到的收益是 \( b_{ij} \)。

#### 4. (Mixed) strategies
- 回顾一下，混合策略是玩家在所有可用纯策略上的概率分布。
- 给定一个带有收益矩阵 \( A \) 和 \( B \) 的双矩阵博弈 \( (A, B) \)，其中 \( A \) 是 \( m \times n \) 矩阵。

- **行玩家的混合策略**：行玩家的混合策略（或简称策略）是一个 \( m \) 维向量 \( \mathbf{x} \)，其分量非负并且总和为 1：
  $$
  \mathbf{x} = \begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_m \end{bmatrix}, \quad \sum_{i=1}^{m} x_i = 1, \quad x_i \geq 0 \ \forall i = 1, \dots, m
  $$

- **列玩家的混合策略**：列玩家的混合策略是一个 \( n \) 维向量 \( \mathbf{y} \)，其分量非负并且总和为 1：
  $$
  \mathbf{y} = \begin{bmatrix} y_1 \\ y_2 \\ \vdots \\ y_n \end{bmatrix}, \quad \sum_{j=1}^{n} y_j = 1, \quad y_j \geq 0 \ \forall j = 1, \dots, n
  $$

#### 5. Pure strategies
- 行玩家的纯策略可以看作是一种特殊的混合策略，其中概率 1 分配给单一行。
- 列玩家的纯策略可以看作是一种特殊的混合策略，其中概率 1 分配给单一列。
- 因此，纯策略配置 \( (i, j) \) 可以用向量 \( (\mathbf{x}, \mathbf{y}) \) 表示，其中：
  $$
  x_i = y_j = 1, \quad x_t = 0 \ \forall t \neq i, \quad y_k = 0 \ \forall k \neq j
  $$ 就是只有一个1

#### 6. Support of a strategy
- 混合策略的支持是被赋予正概率的纯策略集合。
- 因此，对于 \( m \times n \) 的双矩阵博弈 \( \Gamma = (A, B) \)，行玩家策略 \( \mathbf{x} \) 的支持为：
  $$
  \text{Support}_1(\mathbf{x}) = \{ i \in \{1, 2, \dots, m\} : x_i > 0 \}
  $$
- 列玩家策略 \( \mathbf{y} \) 的支持为：
  $$
  \text{Support}_2(\mathbf{y}) = \{ j \in \{1, 2, \dots, n\} : y_j > 0 \}
  $$

#### 7. Strategies inbimatrixgames: anexample
- 假设行玩家以 \( \frac{1}{4} \) 的概率选择“石头”，以 \( \frac{3}{4} \) 的概率选择“布”，而列玩家仅选择“布”。
- 行玩家和列玩家的策略分别为：
  $$
  \mathbf{x} = \begin{bmatrix} \frac{1}{4} \\ 0 \\ \frac{3}{4} \end{bmatrix}, \quad \mathbf{y} = \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}
  $$
- 行玩家的支持为 \( \{1, 3\} \)（即对应于“石头”和“布”的第 1 行和第 3 行），而列玩家的支持是单元素集合 \( \{3\} \)。

#### 8. Expected off
- 当行玩家选择混合策略 \( \mathbf{x} \)，列玩家选择混合策略 \( \mathbf{y} \) 时：
  - 行玩家的期望收益为：
    $$
    \sum_{i=1}^{m} \sum_{j=1}^{n} x_i y_j a_{ij} = \mathbf{x}^T A \mathbf{y}
    $$
  - 列玩家的期望收益为：
    $$
    \sum_{i=1}^{m} \sum_{j=1}^{n} x_i y_j b_{ij} = \mathbf{x}^T B \mathbf{y}
    $$

#### 9.  Expected payoffs: an example
- 假设行玩家以 \( \frac{1}{4} \) 的概率选择“石头”，以 \( \frac{3}{4} \) 的概率选择“布”，而列玩家以 \( \frac{1}{6} \) 的概率选择“石头”，以 \( \frac{1}{3} \) 的概率选择“剪刀”，以 \( \frac{1}{2} \) 的概率选择“布”。
- 因此，行玩家和列玩家的策略分别为：
  $$
  \mathbf{x} = \begin{bmatrix} \frac{1}{4} \\ 0 \\ \frac{3}{4} \end{bmatrix}, \quad \mathbf{y} = \begin{bmatrix} \frac{1}{6} \\ \frac{1}{3} \\ \frac{1}{2} \end{bmatrix}
  $$

在给定的策略组合 \((\mathbf{x}, \mathbf{y})\) 下，行玩家的期望收益计算如下：

- 行玩家的策略向量为：
  $$
  \mathbf{x} = \begin{bmatrix} \frac{1}{4} & 0 & \frac{3}{4} \end{bmatrix}
  $$
- 列玩家的策略向量为：
  $$
  \mathbf{y} = \begin{bmatrix} \frac{1}{6} \\ \frac{1}{3} \\ \frac{1}{2} \end{bmatrix}
  $$
- 双矩阵博弈的收益表为：

  |   | R    | S    | P    |
  |---|------|------|------|
  | R | 0, 0 | 1, -1| -1, 1|
  | S | -1, 1| 0, 0 | 1, -1|
  | P | 1, -1| -1, 1| 0, 0 |

- **行玩家**的期望收益为：
  $$
  \mathbf{x}^T A \mathbf{y} = \begin{bmatrix} \frac{1}{4} & 0 & \frac{3}{4} \end{bmatrix} \begin{bmatrix} 0 & 1 & -1 \\ -1 & 0 & 1 \\ 1 & -1 & 0 \end{bmatrix} \begin{bmatrix} \frac{1}{6} \\ \frac{1}{3} \\ \frac{1}{2} \end{bmatrix}
  $$
  计算过程如下：
  $$
  = \sum_{i=1}^{3} \sum_{j=1}^{3} a_{ij} x_i y_j
  $$
  展开每一项：
  $$
  = \frac{1}{4} \cdot \frac{1}{6} \cdot 0 + \frac{1}{4} \cdot \frac{1}{3} \cdot 1 + \frac{1}{4} \cdot \frac{1}{2} \cdot (-1) + \frac{3}{4} \cdot \frac{1}{6} \cdot 1 + \frac{3}{4} \cdot \frac{1}{3} \cdot (-1) + \frac{3}{4} \cdot \frac{1}{2} \cdot 0
  $$
  得到结果：
  $$
  = -\frac{1}{6}
  $$

因此，行玩家的期望收益为 \(-\frac{1}{6}\)。  

对于策略组合 \((\mathbf{x}, \mathbf{y})\)，列玩家的期望收益计算如下：

**列玩家**的期望收益为：
$$
\mathbf{x}^T B \mathbf{y} = \begin{bmatrix} \frac{1}{4} & 0 & \frac{3}{4} \end{bmatrix} \begin{bmatrix} 0 & -1 & 1 \\ 1 & 0 & -1 \\ -1 & 1 & 0 \end{bmatrix} \begin{bmatrix} \frac{1}{6} \\ \frac{1}{3} \\ \frac{1}{2} \end{bmatrix}
$$
展开后：
$$
= \sum_{i=1}^{3} \sum_{j=1}^{3} a_{ij} x_i y_j
$$
逐项计算：
$$
= \frac{1}{4} \cdot \frac{1}{6} \cdot 0 + \frac{1}{4} \cdot \frac{1}{3} \cdot (-1) + \frac{1}{4} \cdot \frac{1}{2} \cdot 1 + \frac{3}{4} \cdot \frac{1}{6} \cdot (-1) + \frac{3}{4} \cdot \frac{1}{3} \cdot 1 + \frac{3}{4} \cdot \frac{1}{2} \cdot 0
$$
结果为：
$$
= \frac{1}{6}
$$

因此，列玩家的期望收益为 \(\frac{1}{6}\)。

- 若行玩家选择第 2 行（剪刀），而列玩家选择策略 \(\mathbf{y}\)，则行玩家的期望收益为：
  $$
  (A^T \mathbf{y})_2 = \sum_{k=1}^{3} a_{2k} y_k = (-1) \cdot \frac{1}{6} + 0 \cdot \frac{1}{3} + 1 \cdot \frac{1}{2} = \frac{1}{3}.
  $$

- 若列玩家选择第 1 列（石头），而行玩家选择策略 \(\mathbf{x}\)，则列玩家的期望收益为：
  $$
  (B^T \mathbf{x})_1 = \sum_{t=1}^{3} b_{1t} x_t = 0 \cdot \frac{3}{4} + 1 \cdot 0 + (-1) \cdot \frac{1}{4} = -\frac{1}{4}.
  $$

#### 10.  Symmetric bimatrix games
A 2-player strategic game is **symmetric** if:

1. The players' sets of pure strategies are the **same** and
2. The players' payoff functions \( u_1 \) and \( u_2 \) are such that
   $$
   u_1(s_1, s_2) = u_2(s_2, s_1).
   $$

That is, a symmetric game does not change when the players change roles. Using the notation of bimatrix games, an \( m \times n \) bimatrix game \( \Gamma = (A, B) \) is symmetric if:

1. \( m = n \) and
2. \( a_{ij} = b_{ji} \) for all \( i, j \in \{1, \ldots, n\} \), or equivalently \( B = A^T \).

#### 11. Nash equilibrium
**纳什均衡**（Nash Equilibrium）是博弈论中的一个重要概念。对于一个游戏来说，纳什均衡是一组策略的组合，使得任何一个玩家在其他玩家的策略不变的情况下都没有动机单方面改变自己的策略，因为那样做并不会带来更高的收益。

具体来说，对于一个双矩阵游戏 \( \Gamma = (A, B) \)，一对策略 \( (\tilde{x}, \tilde{y}) \) 是纳什均衡，当且仅当以下条件满足：

1. **对行玩家的条件**：对于行玩家的任意策略 \( x \)，行玩家通过选择策略 \( x \) 所得到的收益 \( x^T A \tilde{y} \) 不会超过选择策略 \( \tilde{x} \) 所得到的收益 \( \tilde{x}^T A \tilde{y} \)。即，行玩家没有动机从 \( \tilde{x} \) 转向其他策略。
   
   数学表示为：
   $$
   x^T A \tilde{y} \leq \tilde{x}^T A \tilde{y}
   $$

2. **对列玩家的条件**：对于列玩家的任意策略 \( y \)，列玩家通过选择策略 \( y \) 所得到的收益 \( \tilde{x}^T B y \) 不会超过选择策略 \( \tilde{y} \) 所得到的收益 \( \tilde{x}^T B \tilde{y} \)。即，列玩家没有动机从 \( \tilde{y} \) 转向其他策略。
   
   数学表示为：
   $$
   \tilde{x}^T B y \leq \tilde{x}^T B \tilde{y}
   $$

这些条件意味着：在纳什均衡点上，没有任何一个玩家可以通过单方面改变自己的策略来获得更高的收益。这种稳定的策略组合就是纳什均衡。

#### 12. Best response
对于一个**双矩阵博弈** \( \Gamma = (A, B) \) 和给定的策略组合 \( (\mathbf{x}, \mathbf{y}) \)：

- **如果**策略 \( \tilde{\mathbf{x}} \) 是行玩家（row player）的最佳回应，那么对于任意其他策略 \( \mathbf{x}' \) 都有：
  $$
  \tilde{\mathbf{x}}^T A \mathbf{y} \geq \mathbf{x}'^T A \mathbf{y}
  $$
  这表示行玩家选择策略 \( \tilde{\mathbf{x}} \) 能够使其收益最大化。

- **如果**策略 \( \tilde{\mathbf{y}} \) 是列玩家（column player）的最佳回应，那么对于任意其他策略 \( \mathbf{y}' \) 都有：
  $$
  \mathbf{x}^T B \tilde{\mathbf{y}} \geq \mathbf{x}^T B \mathbf{y}'
  $$
  这表示列玩家选择策略 \( \tilde{\mathbf{y}} \) 能够使其收益最大化。

因此，可以定义**纳什均衡（Nash Equilibrium）**如下：

- 一个策略组合 \( (\mathbf{x}, \mathbf{y}) \) 是纳什均衡，当且仅当：
  - \( \mathbf{x} \) 是对 \( \mathbf{y} \) 的最佳回应
  - \( \mathbf{y} \) 是对 \( \mathbf{x} \) 的最佳回应

换句话说，在纳什均衡下，每个玩家的策略都是对方策略的最佳回应，因此没有任何玩家有动机单方面改变自己的策略。

#### 12. Nash equilibrium
**Definition**  
The strategy profile \((\mathbf{x}, \mathbf{y})\) is a Nash equilibrium for the \( m \times n \) bimatrix game \(\Gamma = (A, B)\) if  
\[
\mathbf{x}^T A \mathbf{y} = \max_{i=1, \dots, m} (A \mathbf{y})_i \quad \text{and} \quad \mathbf{x}^T B \mathbf{y} = \max_{j=1, \dots, n} (B^T \mathbf{x})_j
\]

And equivalently:

**Definition**  
The strategy profile \((\mathbf{x}, \mathbf{y})\) is a Nash equilibrium for the \( m \times n \) bimatrix game \(\Gamma = (A, B)\) if  
\[
x_i > 0 \implies (A \mathbf{y})_i = \max_{t=1, \dots, m} (A \mathbf{y})_t \quad \forall i = 1, \dots, m
\]
and  
\[
y_j > 0 \implies (B^T \mathbf{x})_j = \max_{k=1, \dots, n} (B^T \mathbf{y})_k \quad \forall j = 1, \dots, n.
\]

#### 13. Computing Nash equilibria
在双矩阵游戏中，可以高效地检查是否存在纯粹的纳什均衡。以下是计算纯纳什均衡的步骤：

1. 假设列玩家选择了一个特定的列，行玩家应该选择一个使自己收益最大化的行，从而避免改变策略的动机。
2. 同样地，假设行玩家选择了一个特定的行，列玩家应该选择一个使自己收益最大化的列。

具体步骤如下：

- 对于每个行 \( i = 1, \ldots, m \) 和每个列 \( j = 1, \ldots, n \)，检查以下条件是否成立：
  - \( a_{ij} = \max_t a_{tj} \)：即在列 \( j \) 固定的情况下，行 \( i \) 的收益 \( a_{ij} \) 是否是行玩家在该列上的最大收益。
  - \( b_{ij} = \max_k b_{ik} \)：即在行 \( i \) 固定的情况下，列 \( j \) 的收益 \( b_{ij} \) 是否是列玩家在该行上的最大收益。

- 如果上述两个条件都成立，那么 \((i, j)\) 就是一个纯纳什均衡。
- 总共有 \( m \cdot n \) 个纯策略组合需要检查。

该过程的目标是找到一种策略组合，使得双方在既定策略下都没有偏离的动机，即达成纯粹的纳什均衡。

#### 14.  Mixed Nash equilibria
##### 定义
对于双矩阵游戏 \((A, B)\)，策略组合 \((x, y)\) 是一个纳什均衡，如果满足以下条件：

1. **对于行玩家的策略**：
   - 如果行玩家在某个策略 \( i \) 上分配了正的概率 \( (x_i > 0) \)，那么该策略的收益 \( (Ay)_i \) 必须等于行玩家在所有其他策略上可能得到的最大收益：
     \[
     (Ay)_i = \max_{t=1, \dots, m} (Ay)_t \quad \forall i = 1, \dots, m
     \]
   - 也就是说，行玩家只会在能够为自己提供最大收益的策略上分配正的概率。

2. **对于列玩家的策略**：
   - 如果列玩家在某个策略 \( j \) 上分配了正的概率 \( (y_j > 0) \)，那么该策略的收益 \( (B^T x)_j \) 必须等于列玩家在所有其他策略上可能得到的最大收益：
     \[
     (B^T x)_j = \max_{k=1, \dots, n} (B^T y)_k \quad \forall j = 1, \dots, n
     \]
   - 同样地，列玩家只会在能为自己提供最大收益的策略上分配正的概率。

##### 解释
- **此定义意味着**：在纳什均衡中，玩家只会在能为自己带来最大收益的纯策略上分配正的概率。其他策略要么是零概率，要么收益较低，因此不会被选择。
  
- **总结**：每个玩家在自己混合策略的支持集合（即那些分配了正概率的策略）中的期望收益必须是相等且最大的。这也确保了双方都没有动机通过调整策略的概率分布来增加收益。

要找到所有混合纳什均衡，我们可以按以下步骤进行：

- **步骤 1**：对于每一个可能的玩家 1 的支持集（支持的策略集合）以及每一个可能的玩家 2 的支持集，检查是否存在满足定义中方程组的解。

- **步骤 2**：如果找到的解对应的是概率分布（即，所有 \( x_k \) 都是非负的且总和为 1，同时所有 \( y_k \) 也满足非负且总和为 1 的条件），则说明找到了一个均衡。

- **步骤 3**：因为对于玩家 1 来说有 \( 2^m - 1 \) 种可能的支持集，对于玩家 2 来说有 \( 2^n - 1 \) 种可能的支持集，因此我们需要考虑的组合总数是 \( (2^m - 1)(2^n - 1) \) 个。

这个方法允许我们系统性地遍历所有可能的支持组合，确保没有遗漏任何可能的纳什均衡。

#### 15.  Existence of Nash equilibrium
##### 纳什定理
- **内容**：纳什定理表明，对于任何具有有限数量的玩家和每个玩家有限的纯策略的游戏，至少存在一个纳什均衡（该均衡可以是纯策略也可以是混合策略的组合）。

##### 纳什定理的证明概述
- **方法**：纳什定理的证明通常依赖于**不动点定理**，如布劳威尔（Brouwer）或加藤（Kakutani）的不动点定理。

  1. **不动点定理的条件**：对于某个紧致集合 \( S \) 和映射 \( f: S \rightarrow S \)，如果映射满足某些条件，则该映射存在一个不动点 \( p \in S \)，即 \( f(p) = p \)。
  
  2. **在纳什定理中的应用**：纳什定理的证明表明**最佳响应映射**满足不动点定理的条件，从而保证了至少存在一个不动点。这一不动点对应于游戏的纳什均衡。

这个不动点的存在性正是纳什均衡存在性的理论基础。
- Example
##### Existence of Nash Equilibrium in 2x2 Bimatrix Games

This slide provides a self-contained proof of **Nash's theorem** for 2x2 bimatrix games. Consider a 2x2 bimatrix game with arbitrary payoffs as follows:

|     | L       | R       |
|-----|---------|---------|
| U   | \( a, b \) | \( c, d \) |
| D   | \( e, f \) | \( g, h \) |

- **L** and **R** are the column player's strategy choices.
- **U** and **D** are the row player's strategy choices.
- Each cell contains two values, representing the payoffs for the row player and the column player, respectively.

##### Pure Strategy Nash Equilibria Conditions

To determine if there exists a Nash equilibrium in pure strategies, we consider the following conditions:

1. If \( a \geq e \) and \( b \geq d \), then \( (U, L) \) is a Nash equilibrium. This means the row player chooses **U**, and the column player chooses **L**.
  
2. If \( e \geq a \) and \( f \geq h \), then \( (D, L) \) is a Nash equilibrium. This means the row player chooses **D**, and the column player chooses **L**.
  
3. If \( c \geq g \) and \( d \geq b \), then \( (U, R) \) is a Nash equilibrium. This means the row player chooses **U**, and the column player chooses **R**.
  
4. If \( g \geq c \) and \( h \geq f \), then \( (D, R) \) is a Nash equilibrium. This means the row player chooses **D**, and the column player chooses **R**.

These conditions indicate that, under specific payoff relationships, the strategy choices of the row and column players can form a Nash equilibrium. In a Nash equilibrium, each player has no incentive to unilaterally deviate from their chosen strategy, as any change would not increase their payoff.

在没有纯策略纳什均衡的情况下，可能存在混合策略纳什均衡。考虑下表的 2x2 双矩阵游戏：

|     | L       | R       |
|-----|---------|---------|
| U   | \( a, b \) | \( c, d \) |
| D   | \( e, f \) | \( g, h \) |

---

##### 混合策略的设定

- 行玩家的策略为 \( \mathbf{x} = \begin{bmatrix} p \\ 1 - p \end{bmatrix} \)
- 列玩家的策略为 \( \mathbf{y} = \begin{bmatrix} q \\ 1 - q \end{bmatrix} \)

##### 均衡条件

混合策略 \( (\mathbf{x}, \mathbf{y}) \) 是纳什均衡，当且仅当以下方程成立：

\[
A\mathbf{y} = \begin{bmatrix} aq + c(1 - q) \\ eq + g(1 - q) \end{bmatrix}
\]
\[
B^T\mathbf{x} = \begin{bmatrix} bp + f(1 - p) \\ dp + h(1 - p) \end{bmatrix}
\]

并且满足：

1. \( aq + c(1 - q) = eq + g(1 - q) \)
2. \( bp + f(1 - p) = dp + h(1 - p) \)

这两个方程表示行玩家和列玩家在选择混合策略时，必须在收益上达到平衡，从而无法通过改变策略来提高收益。
  
在 2x2 双矩阵游戏中，当存在混合纳什均衡时，混合策略的概率可以表示为：

\[
q = \frac{c - g}{c - g + e - a}
\]
\[
p = \frac{h - f}{h - f + b - d}
\]

##### 纯策略纳什均衡不存在的两种情况

回顾没有纯策略纳什均衡的两种情形：

1. \( a < e \) 且 \( f < h \) 且 \( g < c \) 且 \( d < b \)
2. \( a > e \) 且 \( f > h \) 且 \( g > c \) 且 \( d > b \)

在这两种情况下，满足 \( 0 < p, q < 1 \)，因此可以得到一个混合策略的纳什均衡。











