### 2498.Frog-Jump-II

本题可以看成两只青蛙从起点到终点，除了两处端点外，不能有重合的点。问任何青蛙最大跨度距离的最小值是多少。

我们考察当前的石头i，此时的两者青蛙必然一个在前a，一个在后b，记做a->b->i->c。显然，我们应该让a处的青蛙先落地休息得到跨度a->i，而另一只青蛙则需要再跳至少b->c。相反，另外一种方案，让b处的青蛙先落地的话，那么a处的青蛙之后必然至少要跳跃一个更大的跨度a->c。显然这个方案是不及前者优秀的。所以得到一个结论，任何时候，都让离得更远的青蛙先落地。

这个结论的推论就非常有趣，该方案必然导致了两个青蛙轮流落地。所以，最优解法就是找全局最大的`stones[i+2]-stones[i]`.