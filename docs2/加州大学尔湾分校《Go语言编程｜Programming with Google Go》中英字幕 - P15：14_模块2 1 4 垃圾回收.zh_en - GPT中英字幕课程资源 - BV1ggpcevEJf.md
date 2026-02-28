# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P15：14_模块2 1 4 垃圾回收.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

🎼。

![](img/9fac2a06ce2302325496c081628a12a5_1.png)

🎼う。🎼Yeah。So we've been talking about delocation， delocating memory。

 and it can be hard to determine when it is appropriate to delocate a variable。

Reason is because you can only delocate a variable when you know the variable is no longer in use。

 right， you don't want to delocate a variable and then later need that variable that you deated because then it's basically gone right So it's hard sometimes to figure that out。

 For out when。It's when it's not in use or when it is in use and so on。 So here's an example。

A go example， which this is legal and go， but because this is a pain。

 this is not legal in certain other languages， but in go， this is legal thing。

 If you look at the first function fo。Inside there， we declare this variable X。

 so it's a local variable to this function fo。And what's returned， though， is the address of x。

 ampersite x， a pointer to x。Now， then in the main function down below， the main function callsF。

And then the main function， what happens is since it calls F and it uses it gets a the return value of F actually gets assigned to a variable in the main function。

So the trick here， the confusion here is that this program fo。

 normally if you declare a local variable x when the function ends。

 that variable x should be delocated right you're done with it because the function is done with it。

 but in this case is not the case because it's returning a pointer to x。

 So now the main since the main now has that pointed to x since that's getting returned to the main。

 the main might still use that pointer to x。 So you can't just say， oh well fo is now done。

 I can get rid of its local variable x because maybe main is going to use that local variable because now main has appointed to it So this is actually a legal thing to do in go。

So this is just one example of how pointers especially make it difficult to tell when dealation is legal and when it's not。

So dealation is a complicated thing。So what people do one way of dealing with that is to have garbage collection。

 so garbage collection is basically automatic an automatic tool that deals with deallocation。😡。

So this is part of interpreted languages and it's done by the interpreter。

 So if it's say Java you the Java virtual machine or in Python。

 it's a Python interpreter or something like that。😡。

And it keeps track of these pointers and it determines when a variable is not in use anymore and when it is。

 and once it determines that a variable is definitely not in use， there are no more pointers。

 no more references to that variable， then the garbage collector delos it only when all references are gone。

😡，So this is this is nice。 garbagebage collection is a nice thing。 It's easy for the programmer。

 right， programmer doesn't have to worry about exactly when delocation， when to do it。

 when not to do it。 Belve me， delocating memory is a big headache in other say C or something like that。

😊，But it requires an interpreter so generally compiled languages like C++， they can't do it。

But go is different。 Okay， go is different and better in this sense。 So go is a compiled language。

 which has garbage collection built into it。 So that is a unique feature。 go， which is really nice。

 So as a result， the go go compiler can figure out it can figure out when like it can follow these pointers to some extent。

 and figure out when this point are still in use。 And it basically keeps track。

 we're not going to go into go garbage collection because that is a complicated thing。

 There are many ways of doing it。 But generally， you have to keep track of the pointers to a particular object。

 And once all the pointers are gone。 Then you know that the object can be delocated。 And so。😊。



![](img/9fac2a06ce2302325496c081628a12a5_3.png)

Garbage collection and go allows two things。 One thing is it'll actually allocate stuff on the hat heap and the stack。

Itself， so you as a programmer don't have to determine I want to put this on the heap。

 I want to put this on the stack。 The go compiler， it'll put code in there at compile time。

 it'll figure out this needs to go heap。 This needs to go to the stack。

 and it'll garbage collection appropriately。 So if it's on the heap。

 it will garbage collected appropriately， it'll see when all the pointers are gone and it'll determine when it can be garbage collected when it can be delocated。

 and this is a really helpful thing。 Now there is a downside because the garbage collection。

 the active garbage collection does take some some time So there's a performance hit。

 but it's a pretty efficient implementation and garbage collection is so darn useful。

 it is probably worth it to put it in go。 So that's a tradeoff that go makes it slows things down a little bit。

 but it is to great advantage because it makes programming a lot easier and you don't have to go as far as using a full on interpreter like you would in an interpreted language。



![](img/9fac2a06ce2302325496c081628a12a5_5.png)