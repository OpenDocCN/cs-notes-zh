# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p114 08_01_04_编码演示-计算最大值与最小值.zh_en -BV13E421M7FF_p114-

![](img/bd3dd9ab1065413be30b8e246c91c1c0_0.png)

What's the album， artist and release year for the most recent album in the data？

Since we're going to be looking at the release year。

 we should ignore albums that don't have a valid year。So first。

 let's extract the albums with a valid year。 We'll call them valid albums。 That'll be set to a list。

 We'll use list comprehension for each row。In albums， if。Is valid year， given the year of the album。

If it's valid， let's go ahead and append it to the list。

Let's look at the most recent album by getting the max year。Album max equals the max function。

 We'll give it the list of valid albums， and then we can pass a lambda function to the key parameter。

 key equals lambda。 That means a functions coming for a given X。 Let's look at the。Year column。

This will give you the max of the list of valid albums by looking at the year column。



![](img/bd3dd9ab1065413be30b8e246c91c1c0_2.png)

Now let's print the album title， Art， and year for the most recent album。Print。For album。Max。

 let's print the title。Let's also print the。Artist。And let's print the。Ye。



![](img/bd3dd9ab1065413be30b8e246c91c1c0_4.png)

So in our code， the latest album and our data set is the Sile Session by the Beach Boys released in 2011。



![](img/bd3dd9ab1065413be30b8e246c91c1c0_6.png)

![](img/bd3dd9ab1065413be30b8e246c91c1c0_7.png)