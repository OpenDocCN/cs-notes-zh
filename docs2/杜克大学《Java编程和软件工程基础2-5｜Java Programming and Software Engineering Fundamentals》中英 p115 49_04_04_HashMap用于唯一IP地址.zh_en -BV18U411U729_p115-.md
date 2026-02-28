# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p115 49_04_04_HashMap用于唯一IP地址.zh_en -BV18U411U729_p115-

![](img/897a6a7ccd0d3fa53e7a204fd05f6813_0.png)

Think back to the problem where you found how many unique IP addresses there were in a web server log。

That problem was essentially finding out how many different strings there were。

If you look at what you just did finding how many times each string occurred。

 you may realize that you have solved a larger problem。

 The solution to the problem of counting unique strings is already here。

You have each unique string in this hash mapap as a key。And we just need。

Away to turn it into the answer you want。 Your counting algorithm has already done the hard work。

 You would just need to be able to extract the answer from the hash map。

This situation is common in programming。You may write code to solve a more complex problem and then be able to solve a simpler problem easily by using the more complex algorithm to do the hard work。

Recognizing such situations can be quite helpful to becoming a highly productive programmer。

In this case， using the hashm from the second problem to solve the first problem is easy。

Hash maps have a dot size method。Which tells how many key value pairs the hashmap has。

As each key appears once in the hash mapap， the result from dot size tells you exactly how many unique keys there were in the input。



![](img/897a6a7ccd0d3fa53e7a204fd05f6813_2.png)

If you had written count visits per IP first。You could have written count unique IPs with just these two lines of code。

The first line uses count visits per IP to solve a larger problem。

And the second line uses the dot size method in hashmap to turn the answer from that problem into the answer to this problem。

The size of the hash map is exactly the number of unique keys， which is the answer to this problem。

Whenever you are programming， try to think of ways to use code you have already written and tested。



![](img/897a6a7ccd0d3fa53e7a204fd05f6813_4.png)

Thank you。😊。