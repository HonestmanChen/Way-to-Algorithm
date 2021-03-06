<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>

# Bash Game - 巴什博弈

--------

#### 问题

$$ A $$和$$ B $$两人轮流从$$ n $$个物品中取出物品，每次取的物品数限定为$$ (1 - p) $$（至少取$$ 1 $$个，至多取$$ p $$个。$$ n, p $$都是正整数且$$ p \lt n $$，显然若$$ p \ge n $$则第一个取的人一次就可以把所有物品取走从而获胜）个，最后一个把物品取光的人获胜。

给定$$ n $$和$$ p $$，当我方先手，我方和对方都是高手（在能赢的情况下一定能赢），求我方是否能赢。

巴什博弈还可以描述为：$$ A $$和$$ B $$两人轮流向一个篮子中放入物品，篮子最多能放$$ n $$个物品。每次放的物品数量限定为$$ (1 - p) $$，最后一个把篮子填满的人获胜。

上面两个问题其实是相同的，只是放和取的过程相反。本章中其他的博弈问题都可以像这样用相反的过程进行颠倒。

#### 解法

若$$ n = p + 1 $$，$$ A $$取$$ (1 - p) $$个物品，剩下$$ (1 - p) $$个物品。下一次$$ B $$总能一次取光，$$ B $$获胜。

介绍博弈论中的概念“局势”，当一方做选择时，剩余的物品数量为$$ x $$时，称这一方面对的局势为$$ (x) $$。对于$$ n = 50, p = 4 $$的情况：

$$ (1) $$ 当我方面临$$ (1 - 4) $$局势时，我方必赢，因为我方可以将剩余物品都拿光；

$$ (2) $$ 当我方面临$$ (5) $$局势时，我方必输，因为我方取物品后，必然留给对方$$ (0 - 4) $$局势，对方必赢；

$$ (3) $$ 当我方面临$$ (6 - 9) $$局势时，我方必赢，因为我方可以留给对方$$ (5) $$局势，对方必输；

$$
\cdots
$$

可以看出，当留给对方$$ p + 1 $$个物品时，下一轮对方必然会输，因为对方必然取$$ (1 - p) $$个物品，留给我方$$ (1 - p) $$个物品。称这样的物品数量为必赢数量$$ w = p + 1 $$。

当我方取物品时面对$$ w $$的倍数个物品时，我方必输，即$$ n \mod (p + 1) = 0 $$。否则对方必输。

该算法的时间复杂度为$$ O(1) $$。

--------

#### 源码

[BashGame.h](https://github.com/linrongbin16/Way-to-Algorithm/blob/master/src/GameTheory/BashGame.h)

[BashGame.cpp](https://github.com/linrongbin16/Way-to-Algorithm/blob/master/src/GameTheory/BashGame.cpp)

#### 测试

[BashGameTest.cpp](https://github.com/linrongbin16/Way-to-Algorithm/blob/master/src/GameTheory/BashGameTest.cpp)
