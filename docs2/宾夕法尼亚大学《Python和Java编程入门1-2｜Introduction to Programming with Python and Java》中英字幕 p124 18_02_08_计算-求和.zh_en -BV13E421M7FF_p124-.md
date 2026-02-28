# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p124 18_02_08_计算-求和.zh_en -BV13E421M7FF_p124-

To get the total or sum of numeric values across rows of data， we can use the sum function。



![](img/5be52f304900c3b2e5c517b6112944d8_1.png)

Let's calculate the total number of reviews for nail salons and Henderson。



![](img/5be52f304900c3b2e5c517b6112944d8_3.png)

First， we need to query our data and select all of the nail salons in the city of Henderson。



![](img/5be52f304900c3b2e5c517b6112944d8_5.png)

We start by creating a condition that tests if the category0 string value contains the string nail salon。



![](img/5be52f304900c3b2e5c517b6112944d8_7.png)

![](img/5be52f304900c3b2e5c517b6112944d8_8.png)

Then we create another condition that tests if the category one string value contains the string nail salon。



![](img/5be52f304900c3b2e5c517b6112944d8_10.png)

Note， in our data， a user could have assigned the nail salon business category to either category zero or category 1。

 so we'll consider both。

![](img/5be52f304900c3b2e5c517b6112944d8_12.png)

![](img/5be52f304900c3b2e5c517b6112944d8_13.png)

We create a third condition that looks for rows where the city is equal to Henderson。Finally。

 we put all three conditions together and get the sum of the review count column。😡。



![](img/5be52f304900c3b2e5c517b6112944d8_15.png)

This returns the total review count value for the rows where Cat zero is true， or Cat1 is true。

 and Henderson is true。

![](img/5be52f304900c3b2e5c517b6112944d8_17.png)

![](img/5be52f304900c3b2e5c517b6112944d8_18.png)

![](img/5be52f304900c3b2e5c517b6112944d8_19.png)