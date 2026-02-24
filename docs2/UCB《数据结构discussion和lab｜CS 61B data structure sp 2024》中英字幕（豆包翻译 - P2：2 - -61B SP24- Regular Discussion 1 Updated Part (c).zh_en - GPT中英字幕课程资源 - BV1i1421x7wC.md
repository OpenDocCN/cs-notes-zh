# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P2：2 - -61B SP24- Regular Discussion 1 Updated Part (c).zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

Hello， in this video， I'm going to go over。The updated version of spring 2024 regular discussion one。

So the effective parts is the watch lecture method in the student class and the make Students Watch lecturecture in the CS61 B class。



![](img/f80bd986f377148fc8ae19f94e24ca56_1.png)

So in this version， watch lecture is going to return a Booleion and it's going to return whether the student actually watch the lecture。

 this is to better illustrate how it can use return values of other functions。



![](img/f80bd986f377148fc8ae19f94e24ca56_3.png)

![](img/f80bd986f377148fc8ae19f94e24ca56_4.png)

So in part， see you。Sub part 1， this is the effective part。

We're still asked to make every CS6 UMB student enroll in this semester watch lecture。

But we also need to return to total number of students who actually watch the lecture。

So now let's think about the method header。As for the methods。

 if we want them to be accessible to users from the other classes， we'll need to set them as public。

So I'm going to write public。Now we need to think whether it's static or not。

It turns out in this case， it's better to use them as an instance variable because make student watch lectures should be something that's associated with individual CS61 V classes。

 not the whole class。So that means this method should be called by individual class object。

Furthermore， it uses the instance variable students。

 which is not really possible if we're using the static method， so let's just keep it as instance。



![](img/f80bd986f377148fc8ae19f94e24ca56_6.png)

The return value in this case is an integer because it'll return the number of students who actually watch the lecture。

So I'm going to write public int。Make student。Watch。Lecture。And it's going to take no arguments。

 because we don't need any。

![](img/f80bd986f377148fc8ae19f94e24ca56_8.png)

Now， because we want to keep track of this number， makes sense to create an in variableable。



![](img/f80bd986f377148fc8ae19f94e24ca56_10.png)

That is the total count we've seen so far。Now we can just iterate over every C6 U MB student。



![](img/f80bd986f377148fc8ae19f94e24ca56_12.png)

So we're going to access the student array。

![](img/f80bd986f377148fc8ae19f94e24ca56_14.png)

And then， we're going to call。The watch lecture method。Now。

 notice I put a if here because we want to make use of the return value of the watch lecture function。



![](img/f80bd986f377148fc8ae19f94e24ca56_16.png)

![](img/f80bd986f377148fc8ae19f94e24ca56_17.png)

![](img/f80bd986f377148fc8ae19f94e24ca56_18.png)

So if the launch lecture returns true， then we want to increment our total by one。



![](img/f80bd986f377148fc8ae19f94e24ca56_20.png)

You can also do it by setting another boolean variable and then checking if on that boolean variable。

 But here on using this allows us to use fewer lines。



![](img/f80bd986f377148fc8ae19f94e24ca56_22.png)

But， they're equivalent。Not that we have tallied the total number of students who watch the lecture。

 we can just return it。

![](img/f80bd986f377148fc8ae19f94e24ca56_24.png)