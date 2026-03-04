# mycodeschool【中英⚡数据结构｜Data Structures】 p22 p21 Data structures： Introduction to Queues -BV1ckrLYREn2_p22-

Hello everyone， we have been talking about data structures for some time now as we know data structures are ways to store and organize data and computers。

 so far in this series we have discussed some of the data structures like arrays linked lists and in last couple of lessons we have talked about stack。



![](img/627617deb2be122c0ae3b5d6df290bc3_1.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_2.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_3.png)

In this lesson， we are going to introduce you to Qes。

We are going to talk about Q ADT just the way we did it for stacks。

 first we are going to talk about Q as abstract data type or ADT。

 as we know when we talk about a data structure as abstract data type。

 we define only the features or operations available with the data structure and to not go into implementation details。



![](img/627617deb2be122c0ae3b5d6df290bc3_5.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_6.png)

We will see possible implementations in later lessons。

In this lesson we are only going to discuss logical view of Q data structure， so let's get started。



![](img/627617deb2be122c0ae3b5d6df290bc3_8.png)

Q data structure is exactly what we mean when we say Q in real world。

 a Q is a structure in which whatever goes in first comes out first。



![](img/627617deb2be122c0ae3b5d6df290bc3_10.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_11.png)

In short， we call Q of P4 structure。

![](img/627617deb2be122c0ae3b5d6df290bc3_13.png)

Earlier we had seen stack， which is a last in first out structure。

 which is called a last in first out structure， or in short LeO。



![](img/627617deb2be122c0ae3b5d6df290bc3_15.png)

A stack is a collection in which both insertion and removal happen from the same end。



![](img/627617deb2be122c0ae3b5d6df290bc3_17.png)

That we call the top of stack。

![](img/627617deb2be122c0ae3b5d6df290bc3_19.png)

In Q， however， an insertion must happen from one end that we call rear or tail of the Q and any removal must happen from the other end。



![](img/627617deb2be122c0ae3b5d6df290bc3_21.png)

That we can call。Front or。

![](img/627617deb2be122c0ae3b5d6df290bc3_23.png)

Head of the queue。If I have to define Q formally as an abstract data type。



![](img/627617deb2be122c0ae3b5d6df290bc3_25.png)

Then a queue is a list or collection with the restriction or constraint that insertion can be and must be performed at one end that we call the rear of Q or the tail of Q and diletion can be performed at other end that we can call the front of Q or head of Q let's now define the interface or operations available with Q just like stack we have two fundamental operations here and insertion is called Nq operation some people also like to name this operation push in queue operations should insert an element at tail or rear end of Q deletion is called Dq operation in some implementations people。



![](img/627617deb2be122c0ae3b5d6df290bc3_27.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_28.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_29.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_30.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_31.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_32.png)

Call this operation pop also。Push and pop are more famous in context of stack and Q and the Q are more famous in context of Qs。



![](img/627617deb2be122c0ae3b5d6df290bc3_34.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_35.png)

While implementing， you can choose any of these names in your interface。



![](img/627617deb2be122c0ae3b5d6df290bc3_37.png)

DQ should remove an element from front or head of the Q and theq typically also returns this element that it removes from the head。



![](img/627617deb2be122c0ae3b5d6df290bc3_39.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_40.png)

The signatures of Nq and theq for a Q of integers can be something like this。



![](img/627617deb2be122c0ae3b5d6df290bc3_42.png)

And Q is his returning void here。While Dq is returning an integer。

 this integer should be the removed element from the Q， you can design theq also to return void。

 typically a third operation front or peak is kept just to look at the element at the head。

 just like the top operation that we had kept in stack。



![](img/627617deb2be122c0ae3b5d6df290bc3_44.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_45.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_46.png)

This operation should just return the element at front and should not delete anything okay we can have few more operations。

 we can have one operation to check whether Q is empty or not。



![](img/627617deb2be122c0ae3b5d6df290bc3_48.png)

If Q has a limited size， then we can have one operation to check whether Q is full or not。



![](img/627617deb2be122c0ae3b5d6df290bc3_50.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_51.png)

Why I am calling out these alternate names for operations is also because most of the time we do not write our own implementation of a data structure。

 we use inbuilt implementations available with language labor interface can be different in different language labor for example if you would use the inbuilt queue in C++ the function to insert is push while in C sharps N Q so we should not confuse。



![](img/627617deb2be122c0ae3b5d6df290bc3_53.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_54.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_55.png)

I'll just keep more famous names here okay so these are the operations that I have defined with Q ADT and Q the Q front and is empty。



![](img/627617deb2be122c0ae3b5d6df290bc3_57.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_58.png)

We can insert or remove one element at a time from the Q using N Q and the Q front is only to look at the element at head is empty。

 is only to verify whether Q is empty or not。

![](img/627617deb2be122c0ae3b5d6df290bc3_60.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_61.png)

All these operations that have written here must take constant time or in other words。



![](img/627617deb2be122c0ae3b5d6df290bc3_63.png)

Their time complexity should be big o of1。

![](img/627617deb2be122c0ae3b5d6df290bc3_65.png)

Logically a queue can be shown as a figure or container open from two sides。

 so an element can be inserted or in queueed from one side and an element can be removed or deed from other side if you remember stack we show a stack as a container open from one side so an insertion or what we call push in context of stack and removal or pop both must happen from the same site in queue insertion and removal should happen from different sides。



![](img/627617deb2be122c0ae3b5d6df290bc3_67.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_68.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_69.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_70.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_71.png)

Let's say I want to create a queue of integers。

![](img/627617deb2be122c0ae3b5d6df290bc3_73.png)

Let's say initially we have an empty Q。 I will first write down one of the operations and then show you the simulation in logical view。

 Let's say I first want to N Q number 2。This figure that I'm showing here right now is an emptyQ of integers and I am saying that I am performing an N queue operation here in a program I would be calling an Nq function passing it number two as argument。



![](img/627617deb2be122c0ae3b5d6df290bc3_75.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_76.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_77.png)

After this n Q， we have one element in the Q， we have one integer in the Q because we have only one element in the queue right now。

 front and rear of the are same。

![](img/627617deb2be122c0ae3b5d6df290bc3_79.png)

Let's encu one more integer。Now I want to insert number5。5 will be inserted at rear or tail of the Q。

 let's send Q1 more。And now I want to call theq operation。

 so we will pick2 from head of the Q and it will go out if theq is supposed to return this removed integer then we will get integer 2 as return and Q and Dq are the fundamental operations available with Q in our design we can have some more for our convenience like we have front and is empty here a call to front at this stage。

 we get us number 5 integer 5 as return no integer will be removed from the Q calling S is empty at this stage can return us a Boolean falls。



![](img/627617deb2be122c0ae3b5d6df290bc3_81.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_82.png)

Or a zero for false and one for true。So this pretty much is how queue works Now one obvious question can be What are the real scenarios where we can use Q What are the use cases of Q data structure Q is most often used in a scenario where there is a shared resource that supposed to serve some requests but the resource can handle only one request at a time it can serve only one request at a time in such a scenario it makes most sense to queue up the requests the request that comes first gets served first let's say we have a printer shared in a network Any machine in the network can send a print request to this printer printer can serve only one request at a time it can print only one document at a time。

 so if a request comes when it's busy it can't be like I'm busy request later that will be really rude of the printer。



![](img/627617deb2be122c0ae3b5d6df290bc3_84.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_85.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_86.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_87.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_88.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_89.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_90.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_91.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_92.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_93.png)

What really happens is that the program that manages the printer puts the print request in a queue。

 as long as there is something in the queue， printer keeps picking up a request from the front of the queue and serves it。



![](img/627617deb2be122c0ae3b5d6df290bc3_95.png)

Processor on your computer is also a shared resource a lot of running programs or processor need time of the processor。

 but the processor can attend to only one processor at a time Processor is the guy who has to execute all the instructions who has to perform all the arithmetic and logical operations so the processes are put in a queue。



![](img/627617deb2be122c0ae3b5d6df290bc3_97.png)

Qes in general can be used to simulate weight in a number of scenarios。

 we will discuss some of these applications of Q in detail while solving some problems in later lessons。



![](img/627617deb2be122c0ae3b5d6df290bc3_99.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_100.png)

This is good for an introduction in next lesson we will see how we can implement Q。



![](img/627617deb2be122c0ae3b5d6df290bc3_102.png)

This is it for this lesson。 Thanks for watching。