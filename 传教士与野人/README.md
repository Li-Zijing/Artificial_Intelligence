# 传教士与野人问题

##### **问题描述**

> 有三个传教士和三个野人一起来到河边准备渡河，河边有一条空船，且传教士和野人都会划船，但每次最多可供两人乘渡。河的任何一岸以及船上一旦出现野人人数超过传教士人数，野人就会把传教士吃掉。为安全 地渡河，传教士应该如何规划渡河方案？

##### **解题思路**

 M 为传教士总人数，C 为野人总人数，K 为每条船乘坐人数，船的状态表示为 b。

用(m, c, b)表示左岸的传教士人数，野人人数，船的状态（b=1船在左岸，b=0船在右岸）

则初始状态为(M, C, 1), 目标状态为(0, 0, 0)

启发函数：放宽约束条件（假设野人人数可以超过传教士人数），在宽约束条件下得到一个估计值：

船在左岸时至少需要的摆渡次数：
$$
([\frac{m+c-K}{K-1}]+1)*2+1
$$
船在右岸时至少需要的摆渡次数：
$$
([\frac{m+c+1-K}{K-1}]+1)*2+2
$$
