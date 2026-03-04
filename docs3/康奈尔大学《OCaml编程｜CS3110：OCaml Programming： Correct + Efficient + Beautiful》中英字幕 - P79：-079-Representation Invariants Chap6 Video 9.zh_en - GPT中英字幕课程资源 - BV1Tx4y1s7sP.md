# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P79：-079-Representation Invariants Chap6 Video 9.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Some values of the concrete type simply don't make sense as values of the abstract type。

That is the abstraction function is not meaningful when applied to them。

In our implementation of sets that prohibited duplicates。

We never wanted any operations of that module to take in a list that had duplicates in it。

 It would get the wrong answer。 Our size function， for example。

 would return a number that was too big if the list had duplicates。

The job of the representation invariant is to identify which values of the concrete type are allowable and which are not。

😡，So you can think of the representation invariant as being a kind of big。

 thick red line in the set of concrete values， and it separates the meaningful concrete values from the unmeaningful concrete values。

 the valid concrete values are those that satisfy the representation invariant or repinvariant for short。

 the invalid concrete values are the ones that don't satisfy。

So the rapid variant is what distinguishes valid concrete values from invalid concrete values。

 thus identifying which concrete values we actually want to use as part of computations and which we want to avoid。

To document the repin variances， as we've seen， you write a comment above the representation type in the file。

😡，You can write that as RI colon， you could write it as invariant colon。

 you could write representation invariant colon if you wanted to be verbose。

 it doesn't really matter which of those you use， the important thing is that you identify what it is。

Once more， it's the sort of thing you should write first before implementing operations。

 Of course that's because this forces you to think through the design of the representation type and get it right from the beginning。

From time to time， of course， you may end up having to revisit it。

The representation invari is implicitly part of every precondition and post condition in the abstraction。

 So every operation in lists set no dus implicitly has this rein variant that the list must not contain duplicates as part of its precondition and part of its post condition。



![](img/fc8c6af6286f2e7e4c0539fba15be869_1.png)

No one is allowed to pass in a value that has duplicates and no operation of this data structure is ever allowed to return a list that does have duplicates。

Now that invariant is hidden from the client， we don't actually document it in a client facing place。

 we wouldn't write it， for example， in the module type set up here。😡。



![](img/fc8c6af6286f2e7e4c0539fba15be869_3.png)

Implicitly， if the client is a programmer， they should note that if there's a representation invariant。

 it's being maintained behind that abstraction barrier。😡，Much like a loop variant。

A representation invariant is something that holds in some places， but not others。

A representation invariant may temporarily be violated inside of the body of an operation as part of making progress towards completing that operation。

 but maybe not getting there fully yet。😡，That's just like how in the body of a loop。

 a loop invariant might temporarily not hold， but eventually by the end of the loop body。

 it's restored。So think about this in terms of the input and the output to a concrete operation。

 there's a concrete input and a concrete output。We are guaranteed that the weaponin variant holds for the concrete input and that it holds for the concrete output。

That's the precondition and the post condition nature of the weapon there。

But during the middle of a of that concrete operation。

 the weaponin variant might temporarily be violate。



![](img/fc8c6af6286f2e7e4c0539fba15be869_5.png)

A great example of this is in our implementation of union inside of Lisetno Dus。

The rapid variant here says that the list must not contain duplicates。

 but we do temporarily construct a list that contains duplicates or might contain duplicates when we take S1 append S2。

We restore that invariant， though by deduplicating before we return from the function。



![](img/fc8c6af6286f2e7e4c0539fba15be869_7.png)

![](img/fc8c6af6286f2e7e4c0539fba15be869_8.png)