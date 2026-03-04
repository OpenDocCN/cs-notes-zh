# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P2：-002-Functional Programming - What Chap1 Video 2.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

![](img/357e975df1fdff38996d139480c3eec8_0.png)

What is a functional language？Well， it's really more of something that's on a spectrum than a precise definition。



![](img/357e975df1fdff38996d139480c3eec8_2.png)

But for now， let's say that a functional language is one that defines computations as mathematical functions。



![](img/357e975df1fdff38996d139480c3eec8_4.png)

And avoids mutable state。

![](img/357e975df1fdff38996d139480c3eec8_6.png)

What I mean by state is the information maintained by a computation。😡。



![](img/357e975df1fdff38996d139480c3eec8_8.png)

You are used to maintaining state， say， for example， when you build a linked list class in Java。

 it maintains information， perhaps about how many elements are in the linked lists or which nodes are at the very beginning and very end of the list。

 That's the state that's maintained。

![](img/357e975df1fdff38996d139480c3eec8_10.png)

![](img/357e975df1fdff38996d139480c3eec8_11.png)

![](img/357e975df1fdff38996d139480c3eec8_12.png)

![](img/357e975df1fdff38996d139480c3eec8_13.png)

Or perhaps you're implementing Dketra's algorithm， and you're exploring to find the nearest city。

 the shortest path to it。

![](img/357e975df1fdff38996d139480c3eec8_15.png)

There is state that is maintained in terms of a frontier set in that algorithm。



![](img/357e975df1fdff38996d139480c3eec8_17.png)

![](img/357e975df1fdff38996d139480c3eec8_18.png)

Mutable state is a state that can be changed。

![](img/357e975df1fdff38996d139480c3eec8_20.png)

One instant in a computation， the state is one thing and another instant in the computation。

 the state has evolved and changed。

![](img/357e975df1fdff38996d139480c3eec8_22.png)

![](img/357e975df1fdff38996d139480c3eec8_23.png)

That change is the essence of mutability。The antonym for mutable， by the way， is immutable。



![](img/357e975df1fdff38996d139480c3eec8_25.png)

So functional languages avoid mutable state。😡。

![](img/357e975df1fdff38996d139480c3eec8_27.png)

They embrace immutability。

![](img/357e975df1fdff38996d139480c3eec8_29.png)

And they do so by expressing computations as mathematical functions。



![](img/357e975df1fdff38996d139480c3eec8_31.png)

Mutability is something you've probably been taking for granted for a long time now。😡。



![](img/357e975df1fdff38996d139480c3eec8_33.png)

And it's a very seductive notion。

![](img/357e975df1fdff38996d139480c3eec8_35.png)

The fantasy of mutability is that it's easy to reason about。



![](img/357e975df1fdff38996d139480c3eec8_37.png)

Because you think， well。

![](img/357e975df1fdff38996d139480c3eec8_39.png)

It's not your fault。 You were taught to think this。The machine does this。

 and then it does this and this and so forth and so on。

 There's just this linear sequence of actions that's taking place。



![](img/357e975df1fdff38996d139480c3eec8_41.png)

![](img/357e975df1fdff38996d139480c3eec8_42.png)

The reality of mutability is twofold。

![](img/357e975df1fdff38996d139480c3eec8_44.png)

The first piece of it is that。

![](img/357e975df1fdff38996d139480c3eec8_46.png)

Machines are really good about complicated manipulations of state， but our brains are not。



![](img/357e975df1fdff38996d139480c3eec8_48.png)

Human brains are not good at this。😡。

![](img/357e975df1fdff38996d139480c3eec8_50.png)

But the machine is， that's what it was built to do。

 that's what the processor inside the machine actually makes possible。

 and you learn all about that in CS 3410。😡。

![](img/357e975df1fdff38996d139480c3eec8_52.png)

What's really a problem with mutability to use a fancy technical term now is that it breaks what's called referential transparency。



![](img/357e975df1fdff38996d139480c3eec8_54.png)

![](img/357e975df1fdff38996d139480c3eec8_55.png)

That means the ability to replace an expression with its value。



![](img/357e975df1fdff38996d139480c3eec8_57.png)

Without。

![](img/357e975df1fdff38996d139480c3eec8_59.png)

Changing the result of the computation。Referential transparency makes it easy for humans to reason about a computation because we can just substitute one thing with another。



![](img/357e975df1fdff38996d139480c3eec8_61.png)

![](img/357e975df1fdff38996d139480c3eec8_62.png)

Neable state breaks that。Because a variable can change its value from one time to another。



![](img/357e975df1fdff38996d139480c3eec8_64.png)

And that's exactly what happens with imperative programming。



![](img/357e975df1fdff38996d139480c3eec8_66.png)

![](img/357e975df1fdff38996d139480c3eec8_67.png)

Imperative is kind of the opposite end of the spectrum from functional。



![](img/357e975df1fdff38996d139480c3eec8_69.png)

Comparative programming is what you've come to love and know through your classes that had Python or Java。



![](img/357e975df1fdff38996d139480c3eec8_71.png)

![](img/357e975df1fdff38996d139480c3eec8_72.png)

In an imperative program， we have commands。Which specify how to compute。



![](img/357e975df1fdff38996d139480c3eec8_74.png)

By destructively changing the state。Here are three examples of such commands。X becomes x plus1。



![](img/357e975df1fdff38996d139480c3eec8_76.png)

Now， no self respecting mathematician is ever going to write x equals x plus1。

 that's an equation that can't possibly hold， but programmers write it all the time。



![](img/357e975df1fdff38996d139480c3eec8_78.png)

![](img/357e975df1fdff38996d139480c3eec8_79.png)

It's a destructive change to the state。

![](img/357e975df1fdff38996d139480c3eec8_81.png)

We're actually taking some bits in memory and replacing them with other bits that change the meaning of this name X。



![](img/357e975df1fdff38996d139480c3eec8_83.png)

![](img/357e975df1fdff38996d139480c3eec8_84.png)

From one instant in computation to another。An array update like a sub I becomes 42 or a pointer change。

 like P dot next becomes P dot next dot next。Those are also examples of commands that change the state。



![](img/357e975df1fdff38996d139480c3eec8_86.png)

They're saying how to compute。What I want the computer to do with each of those is to update some bits in memory that I've given a name to。



![](img/357e975df1fdff38996d139480c3eec8_88.png)

![](img/357e975df1fdff38996d139480c3eec8_89.png)

Another phenomenon that occurs with imperative programming is what's called a side effect。



![](img/357e975df1fdff38996d139480c3eec8_91.png)

There are many definitions of what a side effect could be， but let's go with a simple one for here。



![](img/357e975df1fdff38996d139480c3eec8_93.png)

Here is a function or a method you could think of it as either。

 let's think of it as a method for now that has a side effect。



![](img/357e975df1fdff38996d139480c3eec8_95.png)

![](img/357e975df1fdff38996d139480c3eec8_96.png)

By modifying a variable that was declared outside of it。



![](img/357e975df1fdff38996d139480c3eec8_98.png)

You call this method in X， and it's going to add1 to X and return it。



![](img/357e975df1fdff38996d139480c3eec8_100.png)

That's the side effect when it adds one to this variable that was declared outside。



![](img/357e975df1fdff38996d139480c3eec8_102.png)

In addition to returning a value， it changes something in the state。

 It's that change that really is the side of it。

![](img/357e975df1fdff38996d139480c3eec8_104.png)

![](img/357e975df1fdff38996d139480c3eec8_105.png)

In functional programs， we don't have commands so much as expressions。



![](img/357e975df1fdff38996d139480c3eec8_107.png)

![](img/357e975df1fdff38996d139480c3eec8_108.png)

And expressions don't say how to compute， they say what to compute。



![](img/357e975df1fdff38996d139480c3eec8_110.png)

So in a functional program。

![](img/357e975df1fdff38996d139480c3eec8_112.png)

Variables never change value。That makes the very notion of calling them variables kind of suspect。

 but it's a word you've come to know and love from other programming classes。

 so I'm not going to attempt to change that at this point。

 we could maybe better call them identifiers。

![](img/357e975df1fdff38996d139480c3eec8_114.png)

![](img/357e975df1fdff38996d139480c3eec8_115.png)

![](img/357e975df1fdff38996d139480c3eec8_116.png)

But anyway， in a functional language， variables never change values。😡。



![](img/357e975df1fdff38996d139480c3eec8_118.png)

![](img/357e975df1fdff38996d139480c3eec8_119.png)

They just aren't variable in a functional program Once a variable has a value。

 it's not going to a change and functions are never going to have side effect。



![](img/357e975df1fdff38996d139480c3eec8_121.png)

![](img/357e975df1fdff38996d139480c3eec8_122.png)

The reality of immutability is that it frees you as a programmer。



![](img/357e975df1fdff38996d139480c3eec8_124.png)

It makes your job easier because you no longer have to think about state and how it changes。



![](img/357e975df1fdff38996d139480c3eec8_126.png)

If you've ever had to debug a program with pointers， you know the pain I'm talking about。😡。



![](img/357e975df1fdff38996d139480c3eec8_128.png)

![](img/357e975df1fdff38996d139480c3eec8_129.png)

No more in the functional world。So this gives you very powerful ways of writing and building correct programs。



![](img/357e975df1fdff38996d139480c3eec8_131.png)

![](img/357e975df1fdff38996d139480c3eec8_132.png)

And for that reason， concepts from functional programming have really taken hold in some areas of the programming world where you might not have expected to see them。

 like in web programming， or in building concurrent programs that run on machines that have many processors。

😡。

![](img/357e975df1fdff38996d139480c3eec8_134.png)

![](img/357e975df1fdff38996d139480c3eec8_135.png)

![](img/357e975df1fdff38996d139480c3eec8_136.png)

![](img/357e975df1fdff38996d139480c3eec8_137.png)