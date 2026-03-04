# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P118：-118-Map ADT_ Bindings, Of List Chap8 Video 2.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We are going to need a way to construct maps。 So let's provide two easy ways to construct a map。

 First， an empty map。The value empty is just the empty map that。

Another convenient way to create maps would be from an association loop。

We saw association lists back when we first studied lists， there are just lists that contain pairs。

 the first element of each compare is the key， the second element of each pair is the value。

So ofList is going to take in an association list of the appropriate key and value types and then give us back a map containing the same binding。

Now the question is what to do if that list contains duplicate bindings of keys？For example。

 suppose that list had a binding from 31，10 to fun， as well as a binding from 31，10 to。FP。

That would be a duplicate binding of the key 3110。Then ofli would have to make a decision about what to do。

Here， let me just state a precondition to rule out that case so that implementations of of L don't have to worry about it。

This is maybe a little less nice for the clients of this ADT。

 but it's nicer for the implementers of the ADT。Finally。

It would be nice to have a kind of convenience function in here to give us a representation of the map。

 whatever that underlying type T might be as an association list。In a way。

 you could think of this as implementing a version of the abstraction function。

 whatever that underlying representation T is by converting it to an association list。

 we can get another abstract understanding of what the bindings in the map are。

So bindings of a mapM is just an association list containing the same bindings as him。

I'm going to promise that Biings returns an association list in which there are no duplicate keys in the list。

You might have noticed that I had a little syntax error just as I finished that。

 it's worth looking at that syntax error。I originally had a comma here between K and V。

When we're writing two type variables on which a type constructor is parameterized。

 those go to the left of the type constructor and there's a comma between them。

 it as if there's kind of a pair going on there。But when we have a list that's parameterized on a type。

 we need to actually give a type there and two type variables with a comm between them is not a type。

However， the tubal type in which the first component is of type tick K and the second component of is of type tick V。

 that is a valid type， so there's a difference in the syntax between these two usages。

The main reason that difference exists is in the definition of those two type constructors T constructor T is parameterized on two type variables。

We see that up here。Of course， you'll recall that the type constructor list is parameterized on only one type variable。

 effectively， list is defined as type alpha list， and you know the rest。

So that's why in one place we have to use the comma for two type variables and the other place we have to not use the comma because there's only one type。

That finishes up our ADT for maps。 Of course， there are many other functions we could add to this。

 but this will serve for now for us to investigate how to implement this ADT。

 What we'll do next is take a look at three different data structures for implementing the map ADT。



![](img/25d2340113a23a3dacf4085e44484e22_1.png)

And for each implementation， we're going to focus on these four questions。



![](img/25d2340113a23a3dacf4085e44484e22_3.png)

What is the representation type？😡，What is the abstraction function？



![](img/25d2340113a23a3dacf4085e44484e22_5.png)

For the representation and variance， we'll of course document those as part of the comment for the representation type T。



![](img/25d2340113a23a3dacf4085e44484e22_7.png)

And we're going to add a new question this week as we look at these data structures。

 what is the efficiency of each operation？

![](img/25d2340113a23a3dacf4085e44484e22_9.png)

![](img/25d2340113a23a3dacf4085e44484e22_10.png)

![](img/25d2340113a23a3dacf4085e44484e22_11.png)