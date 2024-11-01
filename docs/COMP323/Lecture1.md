# Introduction
<font size="4">Kanwei He</font> 


**Game Theory**：

aims to help us understand situations in which decision-makers interact

帮助我们理解决策者相互作用的情境

is the study of mathematical models of conflict and cooperation

研究理性智能决策者之间冲突与合作的数学模型的学科。

**Game 博弈:**

models a situation where two or more individuals (players) have to take some **decisions** that will influence one another’s welfare. I.e., the **payoff** of each player depends not only on her own **decision**, but also on the decisions of (a subset of) the other players.

模拟了两个或多个个人（玩家）必须做出一些会影响彼此福利的**决定**的情况。也就是说，每个玩家的**收益**不仅取决于她自己的决定，还取决于其他玩家（子集）的决定。

a description of strategic interaction that includes the **constraints** on the **actions** that the players can take and the players’ **interests**, but does not specify the actions that the players do take.

游戏是对战略交互的描述，包括对玩家可以采取的**行动**和玩家**利益**的**约束**，但不指定玩家采取的行动。

Solution:

is a systematic description of the outcomes that may emerge in a family of games.

对一系列游戏可能出现的结果的系统描述

**Four game theoretical models:**

(noncooperative games).**strategic games** 策略性博弈

(noncooperative games).**extensive games with perfect information**; 完全信息的扩展式博弈

(noncooperative games) **extensive games without perfect information;** 不完全信息的扩展式博弈

(cooperative games). **coalitional games**合作博弈

**strategic games:**

 1. make decision once for all 只做一次决策

 2. players’ decision made simultaneously 所有玩家同时做出决策

 3. When choosing a plan of action, each player is not informed of the plan of action chosen by any other players. 不知道其他玩家的决策

比如说剪刀石头布

**Extensive Games with Perfect Information：**

 1. Each player can consider her plan of action not only at the beginning of the game but also whenever she has to make a decision.

每个玩家不仅可以在游戏开始时考虑她的行动计划，还可以在她必须做出决定时考虑她的行动计划。

 2. players are fully informed about each other’s moves.

玩家完全了解彼此的动作。

比如说象棋

**Extensive Games without Perfect Information**

 1. Each player can consider her plan of action not only at the beginning of the game but also whenever she has to make a decision.

每个玩家不仅可以在游戏开始时考虑她的行动计划，还可以在她必须做出决定时考虑她的行动计划。

 2. players may be imperfectly informed about each others’ moves. 

玩家可能不完全了解彼此的动作。

比如说扑克牌

**Coalitional Games：**

1: the sets of possible joint actions of groups of players are primitives (cooperative games).

玩家群体的可能联合行动集合是原始元素（即合作博弈）

In game theory, a player (decision-maker) is assumed to be 

 1. **Rational**: she makes decisions consistently in pursuit of her own, well-defined objectives. 

**理性**：她始终如一地做出决策，以追求自己明确的目标。

2. **Intelligent**: she knows everything about the game, can make any inferences about the situation, and takes into account this knowledge of other decision-makers’ behavior (she reasons strategically).

**聪明**：她了解游戏的一切，可以对情况做出任何推断，并考虑到其他决策者行为的知识（她会进行战略性推理）

A strategic game (or a game in normal form) is defined by 

 1. **N：player**集合，表示游戏中的所有博弈者。

 2. **S: actions**集合，每个player都有一个actions的集合

 3. **payoff funciton**: 每个player根据其他players的actions组合获得的回报或效用。收益通常由一个收益函数表示，决定了每个策略组合下的回报。

strategic game**没有Time元素**，因为：

 1. 所有玩家choose actions one for all

 2. 所有玩家choose actions simultaneously

![1. Introduction.001.png](https://s2.loli.net/2024/11/01/1pK7gI2S5nqmCHX.png)






**囚徒困境Prisoner’s Dilemma:**

两名重罪嫌疑人被关押在不同的牢房中。有足够的证据判定他们每人犯有轻罪，但没有足够的证据判定他们任何一人犯有重罪，除非其中一人是告密者（fink）。

如果他们两人都保持沉默（quiet），每人都会被判犯有轻罪，并在监狱服刑一年。

如果他们中只有一人告密，他将被释放并作为另一人的证人，另一人将在监狱服刑四年。

如果他们两人都告密，每人将在监狱服刑三年。

这符合**strategic game**条件:

The players are the two suspects: **N = {1, 2}**. 

The actions available to each player are to stay quiet or to fink: **S1 = S2 = {Quiet, Fink}**.

对于每个player，有 four action profiles

(Quiet, Quiet),(Quiet, Fink),(Fink, Quiet),(Fink, Fink). 

**数字越大,收益（payoff）越高，这里的函数逻辑应该是3 - player坐牢的时间**

对于player1: u1(Fink, Quiet) = 3, u1(Quiet, Quiet) = 2, u1(Fink, Fink) = 1, u1(Quiet, Fink) = 0 

对于player2: u2(Quiet, Fink) = 3, u2(Quiet, Quiet) = 2, u2(Fink, Fink) = 1, u2(Fink, Quiet) = 0

可以用table表示：

![1. Introduction.002.png](https://s2.loli.net/2024/11/01/e4HyRtmFbzXBfNu.png)

囚徒困境模拟了一种情况：

 1. there are gains from cooperation：相互合作能获得更好的结果（每个玩家都希望两个玩家都选择quite，而不是都选择fink），

 2. but each player has an incentive to choose Fink：但出于各自的利益考虑，他们可能选择背叛选择fink导致整体结果变得更差。

**我的理解：**

如果选择合作：player1:(quite,quite) = 2  player2:(quite,quite) = 2 总体分数为4.

但是对于player1来说：背叛是占优策略。背叛可能带来的回报是最优的——如果对方保持沉默，自己可以获释（0年）；即使对方也背叛，自己只会被判2年，而不是3年。

囚徒困境（Prisoner's Dilemma）揭示了在一些情况下，个体之间即使相互合作能获得更好的结果，但出于各自的利益考虑，他们可能选择背叛，导致整体结果变得更差。








**Example: Games equivalent to the Prisoner’s Dilemma**

![1. Introduction.003.png](https://s2.loli.net/2024/11/01/BudtFwN1zSsRGm5.png)

左边的表格中：合作：(X,X) = (X,Y) = (Y,X) = 6
`              `player1自私：(Y,X) = 5+1 = 6
`              `player2自私：(X,Y) = 1+5 = 6

这不符合囚徒困境，即相互合作能获得更好的结果

右边表格中：  合作： (X,Y) = 0+5 = 5

player1自私：(Y,X) = 3+(-2) = 1

player2自私：(X,Y) = 0+5=5

符合囚徒困境

**Matching Pennies**

Two people choose, simultaneously, whether to show the head or the tail of a coin. 

If they show the same side, person 2 pays person 1 $1.

If they show different sides, person 1 pays person 2 $1.

这是一个**Strategic game**，同时也是**strictly competitive**

In each action profile, each player wins as much as the other player loses. The players’ interests are diametrically opposed: player 1 wants to take the same action as the other player, whereas player 2 wants to take the opposite action.

在严格竞争的博弈中，一个参与者的收益越高，另一个参与者的收益就越低，也就意味着无法通过合作双赢

可以画出一个payoff表格：其中收益等于所涉及的金钱数额

![1. Introduction.004.png](https://s2.loli.net/2024/11/02/xsDLvOPZGlH4Kn5.png)




**Bach or Stravinsky?**

Two people wish to go out together. 

两个人想一起出去。

Two concerts are available: one of music by Bach, and one of music by Stravinsky. 

有两场音乐会可供选择：一场是巴赫的音乐，一场是斯特拉文斯基的音乐。

One person prefers Bach and one person prefers Stravinsky. 

一个人喜欢巴赫，另一个人喜欢斯特拉文斯基。

If they go to different concerts, each of them is equally unhappy listening to the music of either composer. 

如果他们去听不同的音乐会，那么每个人听两位作曲家的音乐都会同样不开心。

This game is also referred to as the Battle of Sexes.

这个游戏也被称为性别之战。

![1. Introduction.005.png](https://s2.loli.net/2024/11/02/vlrHNw5e8QZph9f.png)





**Symmetric games 对称游戏**

如果一个n-person的**Strategic game**是symmetric

 1. each player has the same set of actions 

每个玩家都有相同的行动集

 2. each player’s payoff depends only on her action and that of her opponents, not on 	 whether she is player 1, 2, . . ., or n

每个玩家的收益仅取决于她自己的行动和对手的行动，而不取决于她是玩家 1、2、……还是 n

![1. Introduction.006.png](https://s2.loli.net/2024/11/02/yjeZoM6mYbdaUKl.png)

比如说囚徒困境（Prisoner’s Dilemma）就是2人的对称战略游戏

两个囚徒可以互换位置而不影响博弈的结果，如果我们交换他们的身份，收益矩阵的结构不会改变。

Matching Pennies 是非对称的：

玩家A想让硬币匹配（追求相同）。

玩家B想让硬币不匹配（追求不同）。

即便他们都有相同的actions空间（正面或反面），但他们的payoff目标不同，因此这是一个非对称博弈。

Bach or Stravinsky 是非对称的：

在这个博弈中，策略空间是对称的（都可以选择Bach或Stravinsky）

玩家A偏向巴赫，希望博弈结果为（Bach, Bach）。

玩家B偏向斯特拉文斯基，希望博弈结果为（Stravinsky, Stravinsky）。

两者的偏好和收益结构不同，因此这是一个非对称博弈。



















