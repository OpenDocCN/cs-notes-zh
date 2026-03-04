# SAS【中英⚡SAS高级程序员 专项课程｜SAS Advanced Programmer Professional Certificate】 p79 P79 05_重新合并分组汇总统计量 -BV1Cfe3z3EoA_p79-

Previously， we use remerging to summarize a single value and remerge that with the data。

 we can also use remerging to summarize a single value and remerge data within groups。

Suppose we want to calculate the percentage of total population for each state inside each region。

 how can we use remerging summary statistics to accomplish this？

The PCT region column shows the percentage of estimated population for each state based on region。

We calculate this value by dividing the P estimate1 column for each state by the total estimated population for the specific region。

We want to determine this value for each state inside each corresponding region we can calculate the estimated population percentage by region by remerrgging summary statistics we use region in the group by clause and then use the sum function to sum the population by each region。



![](img/c5a013d1c8ef95dedbc00ad79aa14689_1.png)

![](img/c5a013d1c8ef95dedbc00ad79aa14689_2.png)

The sum of each region is then remerged with the non summarizeized data of name and P estimateimate 1。

 we can then calculate the percentage by dividing P estimate 1 by the total for that region。



![](img/c5a013d1c8ef95dedbc00ad79aa14689_4.png)

![](img/c5a013d1c8ef95dedbc00ad79aa14689_5.png)