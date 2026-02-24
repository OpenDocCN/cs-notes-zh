# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P47：46_方法解析顺序.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

Up to this point， you've explored class relationships that were relatively straightforward。

But what happens when things get complex， how will you know which classes inherit from which？



![](img/6d7fa6b500c092fb49d58af6063e528d_1.png)

Fortunately， method resolution order or MRO provides rules that can help make sense of that by the end of this video you'll know how to explain the basic rules of method order resolution and how they apply to inheritance classes。

 explain the concept of code linearization with respect to multiple inheritance and deploy method order resolution functions in Python。



![](img/6d7fa6b500c092fb49d58af6063e528d_3.png)

You've likely encountered some examples of single inheritance where a child class only inherits from a single parent class。

But it's important to know that Python has many types of inheritance。

The categorization types are based on the number of parent and child classes。

 as well as the hierarchical order。Including simple inheritance。

 there are broadly four types of inheritance。😊，The first type is called a simple inheritance。

 which you've already dealt with。There is also multiple inheritance。

 which involves a child class inheriting from more than one parent。



![](img/6d7fa6b500c092fb49d58af6063e528d_5.png)

![](img/6d7fa6b500c092fb49d58af6063e528d_6.png)

Next is multi level inheritance， which is inheritance taking place on several levels。



![](img/6d7fa6b500c092fb49d58af6063e528d_8.png)

Then you have hierarchical inheritance， which concerns how several subclasses inherit from a common parent。



![](img/6d7fa6b500c092fb49d58af6063e528d_10.png)

And finally， you could say that there is a fifth type called hybrid inheritance。

 which mixes characteristics of the others。😊。

![](img/6d7fa6b500c092fb49d58af6063e528d_12.png)

![](img/6d7fa6b500c092fb49d58af6063e528d_13.png)

As these inheritance types demonstrate， inheritance becomes increasingly complex as the number of classes in a project grow and become more interdependent。

So how do developers solve this issue？😊，With the use of MO。

MRO determines the order in which a given method or attribute is passed through in a search of the hierarchy of classes for its resolution。

Or in other words， from where it belongs。The order of the resolution is called linearization of a class。

 and MO defines the rules it follows。

![](img/6d7fa6b500c092fb49d58af6063e528d_15.png)

The default order in Python is bottom to top and left to right when imagining the inheritance of these Python classes in a tree structure。



![](img/6d7fa6b500c092fb49d58af6063e528d_17.png)

Let's take the simplest example of single inheritance。

The object is first searched in the class of that object and then in its superclass。😊。



![](img/6d7fa6b500c092fb49d58af6063e528d_19.png)

What about in an example where Class Z is inheriting from two classes？

Let's say Z is inheriting from classes X and Y。In this instance。

 the MO will be Z y and then x In other words， the MO works its way bottom to top and then from left to right。

😡。

![](img/6d7fa6b500c092fb49d58af6063e528d_21.png)

![](img/6d7fa6b500c092fb49d58af6063e528d_22.png)

But things become much more complicated when more levels are added to the hierarchy。

 so developers rely on algorithms to build MOs。😊，Old style classes used in depth。

 first search algorithm or DFS。

![](img/6d7fa6b500c092fb49d58af6063e528d_24.png)

From Python version3 onwards， Python versions have moved to the new style of classes that rely on the C3 linearization algorithm。



![](img/6d7fa6b500c092fb49d58af6063e528d_26.png)

The implementation of the C3 linearization algorithm is complex and beyond the scope of this lesson。

 but for now has an overview of a few rules that it follows。😊，The algorithm follows monotonicity。

 which broadly means that an inherited property cannot skip over direct parent classes。😊。

It also follows the inheritance graph of the class and the superclass is visited only after visiting the methods of the local classes this logic will make more sense later when you explore more complex class relationships in the future lesson。



![](img/6d7fa6b500c092fb49d58af6063e528d_28.png)

Next， let's take a moment to explore some methods of finding the MRO of a class。First。

 I'll begin with a demonstration of the MRO attributes or function。

Let's take a multi level inheritance example comprised of three classes， class A， class B。

 and class C。Class A is the parent class with B and C the respective child classes， In other words。

 B inherits from A and C inherits from B。 When I print the return for calling the MRO function over class C。

 the output indeed confirms that this is the order that is followed。



![](img/6d7fa6b500c092fb49d58af6063e528d_30.png)

So why is this important， well imagine that class A has a variable nu with value of five。😡。

And then Class B also has a nu variable with a value of9 here the MR of function tells you quickly that class C will inherit the nine value from class B。



![](img/6d7fa6b500c092fb49d58af6063e528d_32.png)

Finally， let's examine one more function， which is the help function。😡。

If I take the code from earlier and replace the MO function in the print statement with a help function。

 it provides a much more detailed output with MO information at the top。



![](img/6d7fa6b500c092fb49d58af6063e528d_34.png)

It also contains information about the data descriptors and types used inside the code。😊。



![](img/6d7fa6b500c092fb49d58af6063e528d_36.png)

In this video， you received a brief introduction to method resolution order and how it affects inheritance in different scenarios。

😊，These are both very broad topics， but hopefully it helps you understand the complexity of code that is possible in Python。

😊。