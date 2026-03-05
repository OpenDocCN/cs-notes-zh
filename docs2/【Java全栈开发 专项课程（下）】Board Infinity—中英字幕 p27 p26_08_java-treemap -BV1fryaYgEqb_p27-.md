# 【Java全栈开发 专项课程（下）】Board Infinity—中英字幕 p27 p26_08_java-treemap -BV1fryaYgEqb_p27-

Today in this session we will talk about Java 3 map class。

 we have already discussed about it in the case of different map implementations。

 but it has its own operations so let's get understand。



![](img/0252f3b2871144e417311037d748639d_1.png)

![](img/0252f3b2871144e417311037d748639d_2.png)

Java3 mapap class of the Java collection framework provides the key data structure implementation。

It provides an efficient means of storing the key value pairs in a sorted order。 This provides a。

The implementation where the values are based on the key gets stored into the tree map。

 If we talk about its hiery， the map extends to the sorted map。

 sorted map extends to the navigable map， and then that implements the tree map class itself。

It cannot have a null key， but can have multiple null values and maintains the ascending order。

 that's how the tree map gets created。So TMap， as I said。

 extends the navigable map interface that extends the sorted map and sorted map extends the map interface。

These are the specific features of the tree map。 this class is a member of Java collection F。

 as I told you what the tree hierarchy is。3 map in Java does not allow the null keys。

 but allows the null values。 so if you will try to insert the null key。

 it will give you the null pointer exception。Multiple null values can be associated with different keys and entry pairs returned by the methods in this class and its views present the snapshot of mapping at the time they were produced。

They do not support the entry dot set dot value method。

 so you need to iterate with the helper for each loop。

And these are the specific methods available in the streamMap class that you can impartpe along with the whatever methods being abstracted and overri into the subclasses gets implemented in the streamMap class as well。

So let's get started with a couple of examples。Here， I'm going to create a tree map。

From the u package。Where the key is string and the value is integer。Again。

 taking up the numbers equals to new tree map。Using a put method， number， start put。1。Numbers start。

Do。Numbers taught birth。3。Using putif present， just like I told you， putif present。Sorry， if absent。

 so trying to insert3 and4， so you will see only three will be ignored and the four will be put into the tree map。

W is that if you would like to print the numbers， you can print with the help purposes out。

Moreover methods that you can nitrate， if you would like to get the keyet。

 just simply go for the numbers。Dot keyet。Numbers， do values。Well go for the entry set。

 then say numbers dot entry set。That's how you can nitrate with the tree set。T map。

 so these are the values being iterated。The complete three only keys， only values。 and then。

Entire keyet， you can see that here the dlicacy is coming right away so what you can do is just after putting putif present。

 you can execute the system dot GC。And just after that， just try executing it。

So you can see that the improvement is happening。So that's how the reset works。

See you in the next session until next time stay tuned， Thank you。



![](img/0252f3b2871144e417311037d748639d_4.png)

。

![](img/0252f3b2871144e417311037d748639d_6.png)

![](img/0252f3b2871144e417311037d748639d_7.png)