# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p130 10_02_03_深入理解接口.zh_en -BV18U411U729_p130-

![](img/108b9fd15562f110fcea6c412647ab58_0.png)

Now that you have seen interfaces in action， you may be wondering how does Java know which dot satisfies method to call here The answer is that when you create an object with new。

 Java always notes the type of the object that was created inside the object then whenever you call a method on an object Java looks into where it noted the actual type and uses that to figure out what method to call this process of using the actual type to figure out what method to call is known as dynamic dispatch let's see an example。



![](img/108b9fd15562f110fcea6c412647ab58_2.png)

Here you see some code that declares two variables of type filter， F1 and F2。

 these are each initialized with objects of two different types that implement filter。

 minm filter and depth filter， the dot dot dots indicate some other code that we don't care about。

 but what we do care about are the calls to F1 dot satisfies and F2 dot satisfies and how Java knows which method to call it each place。

When Java executes the first line of code， it makes F1 refer to a newly created minM filter object with the value 4。

0 stored inside of it， This object also contains some data saying that it is really a minM filter object no matter what type of variable is used to refer to it。

 Java always knows its actual type is MinM filter。Likewise。

 when Java executes the second line of this code， it makes F2 refer to a newly created depth filter object。

 this object not only has some instance variables which store the minimum and maximum depth specified。

 but also remembers that it is actually a depth filter object。Now we have reached the call to F1。

sisfies When Java goes to execute this call， it looks at the actual object referenced by F1 here you can see as Java would that F1 is actually a minmag filter object。

 so this call refers to the dot satisfies method inside of the MinMag filter class Java would then call this method just as you are used to。

 this method would then execute exactly as you would expect it。



![](img/108b9fd15562f110fcea6c412647ab58_4.png)

It would check the past in quake's magnitude against its magmin fields value。

 the method that would then return the appropriate value true or false back to the collar。

 where execution continues。

![](img/108b9fd15562f110fcea6c412647ab58_6.png)

When we reach the F2 dot satisfies call， a similar process happens this time when Java looks at the actual type of the F2 object。

 it finds that it is a depth filter object， so it calls the dot satisfies method inside of the depth filter class This method checks if the depth is between the min and max depth stored in the objects fields and returns true or false to its color。

 and then execution would continue as normal。

![](img/108b9fd15562f110fcea6c412647ab58_8.png)

So now you have learned that Java remembers the actual type of each object you make at the time you do new and that this type is used to figure out which method to call。

 which is known as dynamic dispatch。

![](img/108b9fd15562f110fcea6c412647ab58_10.png)