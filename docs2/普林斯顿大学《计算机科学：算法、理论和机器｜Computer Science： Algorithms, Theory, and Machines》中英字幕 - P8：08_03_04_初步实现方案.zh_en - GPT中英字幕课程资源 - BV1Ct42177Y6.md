# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P8：08_03_04_初步实现方案.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

We'll start with the strawman implementation that's extremely simple and was actually used often in the early days of computing because it's so simple。

 but it points out the challenge of actually implementing the API that we've set down。

So this is a warm up let's call a straw man we're going to simplify the specification a little bit first of all。

 we're going going to implement it for one type of item。

 say strings and the other thing we're going to do is to have the client provide a stack capacity in the constructor and a rationale for doing this is that we can just use an array of strings to represent the values。

So let's take a look at how the API that we' changing a little bit， so first of all。

 in the constructor we're specifying the capacity of the stack。

And then when we push we'll push a string and we we pop a string。

 this is just to get started to look at how simple the code can be in a specific situation like this。

 so it's a little different API than the one that we specify。

 but it'll get us looking at implementation code right away。And the whole idea is that with this。

 we can represent the collection with an array of strings and once we have that decision that we're going to use that data structure。

 an array， then these implementation of these methods becomes extremely simple。

So what we're going to do is keep the items in the stack in order in the array。

 and then n is going to be the index of the next open position in the array。

 and that's also the size of the stack。So it's kind of an upside down representation of the stack the top of the stack is like later on in the array。

 but if you do this then we start with what's our data type。

 our values are an array and then an int which is the size of the array and then our constructor is just。

Create a new if we the client gives us a capacity， we create a new array of that size。

 Those are the first two parts that we need to do to implement the data type。

The instance variables are an array and the size n， and then the constructor just creates that array。

And then given that， now to implement the operations， well， let's do the test client first。

And this is a test client that is like the performs like the examples that I showed right at the beginning。

 what we're going to do is read strings off standard input while it's not empty we' going take an item if the item is a minus sign then we pop and print the result of popping just like we did in our examples otherwise we push and that's the test client so that's the example we gave at the beginning to be or not to pop be pop pop that pop pop pop is。

 gives that result。Just as the example that we went through， so that's a test client。

 you can see the constructor provides a maximum size that's taken。From the command line in this case。

So if we ran this with max too small， then there'd be an error and that indicates the kind of problem they have when we start talking about capacity even with a simple test client。

So that's what we expect the thing to do。Even it's worthwhile before going further just to think about an amusing question。

So this is the way our test client works， so if we do6，5，4，3，2，1， pop， pop， pop， pop， pop。

 it comes out one， two，3，4，5，6。Or if we do one pop2， pop 3， pop4， pop5， pop6 cop comes out in order。

 or this more complicated4，1， pop brings out the one，3，2， pop pop pop brings out two，3，4，5， six。

 pop pop brings out five， six。Comes out in sorted order。 That's interesting question。

 Can you always put the pot so that you can get them to come out in sorted order。

The answer to that question is no。For example， if you have five， six， one。

 there's no way that the five can be pop before the six and after the one。People。

 mathematicians study how many different ways are there to create strings like this where the atoms come out so order and so forth。

 even such a simple data structure can lead to fascinating mathematical questions。On a queue。

 this is a boring question because they always come out in the order they came in。

 so if they're in sorted order， it doesn't matter where the DQs are。

So to complete our implementation， we have to do the methods， the data type operations。

 and with this data structure and the restrictions that we made， these are extremely simple。

 They're one liners。 So what' as empty， that's just is N0。What about push？Well。

 all we do is we take our new item， we put it in A of N， and then increment N。

 that's accomplished with one line of code in Java。After the push， the items， new items there。

 and it's been incrementmented by one。And for P， we do the reverse。

 we decrement N and then return the item that's in that position。嗯，好。

And then what's the size is just N。 They're all one liners， extremely simple to implement。

 and that's a full implementation of that strawman API that we gave。

Constant time one liners and even in the simplest kind of machine language these things are going to be only a few instructions。

 and so the very first computer systems that needed to use stacks to do things like evaluate arithmetic expressions and function calls would use implementations like this。

That's the complete implementation， the instance variables， the constructor。

 the methods and the test client。And it produces the desired result。So now。Oh。

 here's a trace of what happens， so this is in an array of size 20。

And it's following the example that we gave， but the stack is upside down。

 so a very simple computation， really。But the thing to notice about this simulation。

 you can see immediately why capacity is kind of a situation。

 there's a lot of space when the stack size is not near the capacity， and that's actually typical。

 a lot of times when you're processing data， you have to reserve for the worst case。

 the biggest capacity， but most of the time you're operating it way under capacity。

And in a typical computing application， you might have a large number of stacks in all that wasted space。

That's the reason that we want to have that performance requirement that the space should be linear in the number of elements actually in the stack。

So let's do a quick benchmark what this thing implements the strawman stack is not really a stack。

 it's a fixed capacity collection that behaves like a stack if the data fits and that's a lot of restrictions。

 it does not implement the stack API number one because it requires the client to give capacity and number two。

 it doesn't meet the performance specs。So the API says it shouldn't be an argument to the constructor。

 but Strt requires a capacity。It only works for strings， so it doesn't do the generic thing。

 so that's okay， we know how to do that。It does get all operations done in constant time。

 but it does not meet the requirement that memory use should be linear in the size of a collection。

And there are limits within the code on the collection size that's the use of Mac there。

 so Strt is not a stack， it does not meet the performance specs and so we're going to have to look at some other way to meet the performance specs and what we need is a new data structure and that's what we're going to talk about next。



![](img/e18ed87b090eba9a4d0a76251866b162_1.png)

![](img/e18ed87b090eba9a4d0a76251866b162_2.png)