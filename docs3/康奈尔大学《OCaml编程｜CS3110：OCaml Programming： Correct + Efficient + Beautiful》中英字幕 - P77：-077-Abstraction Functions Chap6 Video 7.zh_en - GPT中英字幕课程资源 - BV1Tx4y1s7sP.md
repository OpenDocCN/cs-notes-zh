# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P77：-077-Abstraction Functions Chap6 Video 7.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

As we were implementing our two data structures for the set data abstraction。

 there were two questions that we had to answer for each implementation。

How to interpret the representation type as the data abstraction。

And how to determine which values of the representation type are meaningful。

There is a technical term for each of these。😡，The first is called the abstraction function。

 it tells us how to interpret the representation type。

The second is called the representation invariant， it tells us which values are meaningful。



![](img/01c86b36ef658bc3ff3cee2a4a9c13ad_1.png)

Going back to our code， you can see that we've already documented each of these。😡。

For lists set no dupes， the abstraction function was the first piece of it here that said how to interpret the list as a set。

The representation invariant is what told us which values of that representation were actually meaningful。

The list must not contain duplicates， so any list that does contain duplicates is meaningless in this representation。

For list set dupes， the abstraction function is again， the first piece that we documented。

But looking back at that abstraction function， I'm not completely happy with it because it doesn't deal with the notion of duplicates very successfully。

It says that the list A1 through AN represents the set A1 through AN。What if we had， say， the list1。

1，2，3？Does that represent the set1，1，2，3？That's not a very nice looking set， in fact。

 maybe that's a bag。So let's improve this abstraction function to remove any unclarity about how to interpret values of that representation type。

Now I have made it clear how duplicates are hand。The list A1 through AN represents the set B1 through BM。

Where the list B1 through BM is the same list as A1 through AN， but with any duplicates removed。

That's a better abstraction function。The representation invariant， of course。

 is that the list may contain duplicates。 Since in general。

 lists can always contain duplicates in Ocael anyway。

 we wouldn't necessarily need to even document that representation invariant。 It's helpful。

 but technically speaking， we could just eliminate it and say that there is no representation invariant。

None。Or just delete that comment entirely from。The latter makes it maybe questionable whether we forgot to document a representation invariant or not。

 so maybe the best choice was in fact。The original。

 but we could clarify that it really has no effect。 There's none。



![](img/01c86b36ef658bc3ff3cee2a4a9c13ad_3.png)

The list may contain duplicates。One of the reasons that the abstraction function is so important is that it tells us how to understand the data abstraction from the client's point of view。

Think back to our sets from the client's point of view， these are just sets。

 the client doesn't know anything about the list implementation underneath the hood。

So it just looks like the set 12 or the set7 to the client。But from the implementer's point of view。

 these are lists。And there are many possible lists that could represent each of these sets。

For example， the set 1，2 could be represented by the list 12 or by the list21。

So there's a difference here between the abstract values as they're understood by the client and the concrete values as they're understood by the implementer。

The abstraction function， the black arrows here。Are what tell us how to interpret the values that are concrete as values that are abstract。

They map from the list representation to the set representation。😡，Now， of course。

 when I use the word function here， I'm using it in the mathematical sense， not in the Ocal sense。😡。

We haven't written any kind of Oaml function that takes a list and gives you a set。

 That's a chicken and egg problem We don't actually have a set abstraction yet。

 so we can't write a function to map from a list to a set we're in the middle of writing that already when we write list set dupes or list set no dupes So the abstraction function is something that mostly just exists in our own head。

It's a many to one function。 you can see that here because it can potentially map many lists to one set。

And it can be a partial function that is there might be values of the concrete type that aren't meaningful as values of the abstract type。

That's for the representation invariant to decide。 We'll get to that soon enough。

There's a boundary here between the client's view and the implementer's view。😡。

We call that the abstraction barrier。😡，Think of it as like a line of police tape that says。

 don't cross into this crime scene。😡，The client doesn't get to cross that barrier。

They don't get to look at the internals of the data abstraction。Now I'm speaking hypothetically here。

 of course maybe a client can get a hold of the source code and see it。😡，But in their mind。

 they should not be thinking about the concrete values。

All that's guaranteed to the client is what the specification reveals。

 Anything more than that is dangerous knowledge that should not， in general， be exploited by the。

That's why we have mechanisms built into the language like abstract types and ceiling to prevent that kind of information from leaking to the client。

The abstraction barrier， in other words， is part of encapsulation。

So we say that the abstraction function maps valid concrete values to abstract values。

 and the word valid there is important because maybe there are some concrete values that we just can't meaningfully map。

As in our implementation that did not allow duplicate。To document the abstraction function。

 we write it in a comment above the representation type as you've already seen me do。😡。

It's important to write the abstraction function first before you begin implementing operations。😡。

I developed some abstraction functions as we went along and improved them with you。

 but to the extent that you can get them correct the first time around。

The less you're going to have to go back and reimplement some of your operations when you discover maybe you messed up something with that abstraction function。

You don't technically have to write AF colon in front of it。

 you could also write abstraction function if you wanted to be more verbose and maybe sometimes you just won't write AF at all。

 but the important thing is that the decision is documented there next to the representation type。😡。

Why do you do it first， because it's the number one decision that you have to make in implementing a data abstraction？

It gives meaning to the representation。It also dictates what fields are going to be necessary if it's a record or what constructors are going to be necessary if it's a variant。

😡。

![](img/01c86b36ef658bc3ff3cee2a4a9c13ad_5.png)