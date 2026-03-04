# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P119：-119-Association Lists_ Rep Type Chap8 Video 3.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

For our first implementation of the map ADT， let's just use association lists。

 we already know they work to represent maps， they seem like an easy place to start。

So I've already gone ahead here and created the kind of bones of an implementation of a map based on an association list。

 I've written a module associationist map。 It implements the map signature。

 and I've provided kind of placeholder implementations for all of the functions and values in here。

The only place I haven't said fail with unimplemented is for empty where I've written just the unit value。

 because to start off with making no commitments yet so far。

 I've just provided unit as the representation type。😡。

I've also created the bones of an O unit test suite for this implementation。😡。

I'm going to use test driven development to illustrate how we could implement this map ADT。



![](img/c9c4c16b0aa5963070bbb96905831b7f_1.png)

Because I have an O unitit test suite， I've also created a minimal make file for this just by copying it from another assignment。

 and that make file will allow me to run make Test。And I've got zero tests。

 but they do pass at this point。I'm going ahead and running this test suite in a separate terminal window rather than inside a VS code because I find it more ergonomic when I have to work at this point size in recordings to be able to flip back and forth between them just with alt tabab that makes it a little easier for me you might decide that you want to do it in it way that's fine too。



![](img/c9c4c16b0aa5963070bbb96905831b7f_3.png)

So let's start by choosing the representation type。😡，As we said。

 we're going to use association lists， so I need to write down that type。

 as well as document an abstraction function and perhaps a representation invariant for it。

Let's pause here。So far， I've said that the type constructor T is actually an association list of keys and values。

 and I had to fix the implementation of empty to make that type check at that point。

I've started writing down my abstraction function。So I've said that the association list that contains some pairs where the pairs are K1。

 V1， K2， V2， et cea， KN VN。Is the map。That binds K1 to V1， K2 to V2， et cetera。 K， N to V N。

So I'm using that abstract notation we invented for maps to write down the abstraction function。

Now there's a couple of things I need to make some decisions about at this point。

 and they have to do with duplicates。What do I want to do if the association list contains a duplicate？

Well， one possibility is I could define a representation imvari that says the list never contains a duplicate。

 that would be easy， it could just rule it out that way。

Another possibility is to allow duplicates and as I'm thinking ahead。

 that makes certain operations easier， like if I just want to add an element into the list。

 I'll just be able to con on the front that sounds attractive at least at first。

 so let's go ahead and not have a representation invariant。

But we'll also need to write down as part of the abstraction function for clarity。

 what duplicates will actually mean。If a list contains a duplicate key。

 then the actual binding that represents is whatever the leftmost binding in the list is For example。

 if we have a binding of K to V1 followed in the list by a binding of K to V2。

 that represents the map that binds K to V1 we don't care about the binding to V2。😡，For clarity。

 I should also write down what the empty list means。😡，Now I have an abstraction function。

Having thought through those decisions up front will make some of my implementation easier as I proceed。

😡。

![](img/c9c4c16b0aa5963070bbb96905831b7f_5.png)