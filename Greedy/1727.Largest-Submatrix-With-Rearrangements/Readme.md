### 1727.Largest-Submatrix-With-Rearrangements

此题和```085.Maximal-Rectangle```的框架很相似，就是枚举一个维度，然后将问题划归为另一个以为问题来求解。

我们遍历每行row，考虑如果以i-th row为底边，我们所能构建的最大矩形是什么？此时我们眼中所看到的就是以i-th row为底边的一个histogram，和LC85不同的是，我们可以调整histogram中各条bar的顺序，来拼凑最大的矩形。为了更高效地构建矩形，我们显然会贪心地将高度相近的bar放在一起，也就是将这些bar按照高度从大到小排序。随着矩形的底边越长，代价就是高度越矮。我们横向遍历一遍后，就可以找到最大的矩形面积（宽乘以高）。

本题的答案就是遍历所有底边后，全局最大的矩形。