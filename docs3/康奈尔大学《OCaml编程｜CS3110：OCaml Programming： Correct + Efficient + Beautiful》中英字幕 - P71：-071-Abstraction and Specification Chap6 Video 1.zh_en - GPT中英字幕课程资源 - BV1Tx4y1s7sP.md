# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P71：-071-Abstraction and Specification Chap6 Video 1.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

It's been said that computer science is the science of abstraction or perhaps efficient abstractions。

What is an abstraction？Well， as a verb to abstract here means to forget information。😡。

With the purpose of being able to treat related things as being the same。That is。

 you're forgetting about the details that aren't important and focusing on what is important。

 what the common pieces are。😡，As a noun， abstraction means the artifacts that result from that process。

Those artifacts might be functions or modules or classes or whatever your programming language uses to organize its code。

When we create those functions， say。One of the important pieces of abstraction is writing specifications。



![](img/6345dd65a54449d52d366cd1c9b971f8_1.png)

Specation here as a noun means the intended behavior of the abstraction。

We're communicating to other humans what the behavior is supposed to be。As a verb to specify。

 that's the act of creating such an artifact。

![](img/6345dd65a54449d52d366cd1c9b971f8_3.png)

Creating a specification。There's two different audiences for specifications。

And we write documentation for both audiences， though it's not the same documentation because they have different needs。



![](img/6345dd65a54449d52d366cd1c9b971f8_5.png)

![](img/6345dd65a54449d52d366cd1c9b971f8_6.png)

There are clients and implementers。 The clients are the people who are going to consume the specification。

 perhaps it's a standard library， for example， and you're the client because you're reading the documentation in the standard library。

😡，The implementers are the people who are going to be maintaining the code or perhaps writing it the first time。

These are the people who need to understand maybe more pieces。

 maybe lower level pieces of the specification than the clients do。To a client。

 a specification tells them what they must guarantee here I'm thinking of this particularly in terms of functions。

That is what the preconditions are。A client must arrange such that when they call a function。

 they have satisfied the precondition for that function。

The specification for a function also tells the client what they can assume。As a post condition。

They get to know what the output of the function is according to whatever the documentation tells them。

😡，For implementers， it's a bit opposite。

![](img/6345dd65a54449d52d366cd1c9b971f8_8.png)

The specification tells an implementer what they can assume as a precondition。



![](img/6345dd65a54449d52d366cd1c9b971f8_10.png)

Because the client had to satisfy that， so at that function boundary。

 whoever's implementing the function gets to say， all right。

 I am assured that that precondition holds because the client would never get to call me if it didn't。



![](img/6345dd65a54449d52d366cd1c9b971f8_12.png)

They might， of course。 but that's not the implementer's fault。 That's the client's fault。



![](img/6345dd65a54449d52d366cd1c9b971f8_14.png)

And the specification tells the implementer what they must guarantee as a post condition so now it's the implementer's responsibility to arrange for something to hold。

 not the clients。😡。

![](img/6345dd65a54449d52d366cd1c9b971f8_16.png)

So there's a kind of duality going on here between clients and implementers between preconditions and post conditionsditions。

 between assumptions and guarantees。

![](img/6345dd65a54449d52d366cd1c9b971f8_18.png)

![](img/6345dd65a54449d52d366cd1c9b971f8_19.png)

![](img/6345dd65a54449d52d366cd1c9b971f8_20.png)

Specificationations give us a lot of benefits in terms of the modular program。



![](img/6345dd65a54449d52d366cd1c9b971f8_22.png)

They help us with locality。We can understand an abstraction without needing to read the implementation of it when the specification gives enough information to the clients。

😡。

![](img/6345dd65a54449d52d366cd1c9b971f8_24.png)

Specificationations also help us with modifiability。

By clarifying exactly what it is the code is supposed to do。The implementer now。

 as they evolve the code later in time， gets to change that implementation。

Without breaking the client code， because it was clear what the client could rely on。And finally。

 specifications give us accountability。They clarify who is to blame when something goes wrong。

Is the client to blame because they violated a precondition or is the implementer to blame because they violated the post condition。



![](img/6345dd65a54449d52d366cd1c9b971f8_26.png)

We say that an implementation satisfies a specification if it provides the described behavior。



![](img/6345dd65a54449d52d366cd1c9b971f8_28.png)

Now， of course， there are many implementations that might satisfy a given specification。



![](img/6345dd65a54449d52d366cd1c9b971f8_30.png)

There's， again， a duality between the client and the implementary。😡。

The client can't make any particular assumption about which of those implementations the implementer chose。

But the implementer does get at the end of the day to pick which one they want。

That doesn't mean the implementer should be perverse or malicious。

 Both parties here should be acting in good faith in order to agree as to what the specification means。

But ambiguities can arise。 Let's think about this from the perspective of the implementer。



![](img/6345dd65a54449d52d366cd1c9b971f8_32.png)

Here are some factors that might create ambiguity。Maybe the client didn't really understand what they wanted you to implement。

😡，If the client had something in their head and they tried to ask for it。

 but they didn't quite manage to express it right。This happens all the time in software development。

Maybe the client genuinely didn't care like they left a piece of something unspecified because they were good with whatever you gave them as long as it meant the rest of the specification。

😡，Or maybe you as an implementer don't actually understand the meaning of some piece of a specification like there's a word in it you didn't actually understand the technical meaning of。

All of these can lead to what is perceived as or maybe actually is ambiguity and a specification。

So what strategies might you follow in the future when you encounter ambiguous specs？



![](img/6345dd65a54449d52d366cd1c9b971f8_34.png)

Well。First off， let's recognize that ambiguity is a fact of life。But let's also act in good faith。

As implementers， we should try to do the most reasonable thing we can。😡。

Now it's true that when a precondition is violated， you could do anything you want。

 like set the computer on fire。But probably setting the computer on fire is not the most reasonable thing to do。

So。Let's ask。Who wrote the specification？If you are the one who wrote the specification and you discover ambiguity。

 you can seek to improve it。Refine that specification into something that is clearer。

If the client provided the specification， then you can seek clarification from the client。

But you need to be a little careful about this。There's a difference between asking for a few clarifications and asking for 500 clarifications。

You do the latter， and the client might just not hire you again because you couldn't figure out how to resolve low level ambiguities yourself and only percolate up to them for the really important。

So this is a balancing act， it requires the development of some good common sense。As Voltaire wrote。

 common sense is not so common。

![](img/6345dd65a54449d52d366cd1c9b971f8_36.png)