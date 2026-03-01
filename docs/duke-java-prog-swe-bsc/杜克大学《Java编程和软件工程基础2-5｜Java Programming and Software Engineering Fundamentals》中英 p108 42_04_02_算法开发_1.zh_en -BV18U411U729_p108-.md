# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p108 42_04_02_算法开发_1.zh_en -BV18U411U729_p108-

![](img/1cd9c78c60db598af68761f7304ff650_0.png)

You have already written code to read in the entire contents of a web server log and now you want to find out how many unique IP addresses it contains。

 as always， you're going to want to approach this problem with the seven steps you use for every problem we're going to walk through this problem starting at step1 but we're going to use color names instead of IP addresses this problem is really the same problem you're finding out how many unique values there are in an array list of strings but color names are easier to say and to see which ones we're talking about。



![](img/1cd9c78c60db598af68761f7304ff650_2.png)

不的。So when we look at this list of 10 values， you might be able to tell just by looking at it that there are only four unique values。

 But if this list had a million elements in it， we'd like to develop a method that would still work。

There are many ways of solving problems in general。 And in this case。

 there are a couple that I'll mention and one that will realize in code。

 One method that we won't do is to， as we look down the list。

 cross out values that we've seen before。Crossing out values in a list。

Is a problem in Java programming， Because if we replace the values in our parameter with other values。

 we've caused a side effect， something we've spoken about before as a thing to avoid， if you can。

So instead， we'll use an idea of visiting every value in the list in turn。

 which is typical for array problems。 And if we haven't seen a value before。

 we'll copy it into a new list。 So first， I'm copying the value pink because I haven't seen it before in my new list。

Then I'm going to visit green。 I haven't seen it before， so I'll copy it over into my new list。Now。

 I'm going to visit pink。 I've already seen it， so I don't copy it。 Then green。 haven't。

 I have seen it。 so I don't copy it。 Pi， pink， pink。 I've seen them all。Orange。

 I haven't seen before。 so I'll copy that into my new list。The next value is blue。I haven't seen。

So I'm copying it into my list。Finally， I get to pink the last value in my original list。

 I have seen it before， so I don't copy it over。Now， I look at my list that I've created。

 It has four values。 And so I'm going to return the value 4 from my method that I'm writing that determines the number of unique values in the array parameter。



![](img/1cd9c78c60db598af68761f7304ff650_4.png)

Developing this algorithm follows a lot of the same patterns you've seen before。

 you'll see that sometimes you add an element to the copy and sometimes you do not。

 and you'll want to think through the conditions under which you add。Once you've done that。

 you can express the main portion of the algorithm in terms of steps to do for each element of the input。

We'll let you work through steps two and three。

![](img/1cd9c78c60db598af68761f7304ff650_6.png)

Hopefully， you came up with pseudocode that looks like this。Now， for this particular problem。

 you want to do things just a little bit differently。

 Remember that you have log entries in the field records and you want to use the get IP address method to get the string out of the log entry object。

 There are a couple of ways to deal with this difference。

 The simplest is to just use the same algorithm。 but adjust it slightly to reflect to reflect the fact that you want to use records。

 the fields in the class。 and you want to get the IP address out of each element of records。

 check to see if that IP address is in copy and if not， add the IP address to copy。At this point。

 you'd want to test out your pseudocode， then you're ready to turn it into Java code。



![](img/1cd9c78c60db598af68761f7304ff650_8.png)