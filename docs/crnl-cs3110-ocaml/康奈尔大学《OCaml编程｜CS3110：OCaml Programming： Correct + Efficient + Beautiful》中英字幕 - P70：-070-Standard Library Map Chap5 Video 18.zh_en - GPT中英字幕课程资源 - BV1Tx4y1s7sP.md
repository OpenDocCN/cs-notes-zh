# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P70：-070-Standard Library Map Chap5 Video 18.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

The standard library map module is a great example of how functors can be used in Ocal。

Map here means the same thing almost as TMap in Java you might remember more about hashmap。

The map abstraction is the key idea in both of those that were mapping from keys to values。HashMap。

 of course in Java was implemented with hash tables， we will eventually see those in OcaMel。

But TeMap in Java is implemented with balanced binary trees。

 and that's what the map module in Ocaml uses as well as the back end implementation。

 balanced binary T。The map module。Has a functer in it called make。

 which makes a map data structure based on an input， which is itself a structure。

That structure is called ordered type。So to create a map， you have to pass into the make Funter。

 a module that has two things in it。😡，The type for the keys and a comparison function for the keys。

The reason the map module needs a comparison function is because of that balanced binary tree implementation。

 it needs to be able to compare the keys that exist at each node in the tree。

So it's your job to tell the map module what the key type is and how to compare them。😡。

The output of that fluc is of type S。 Here's that output signature。

And this is going to have all of the usual functions that you might expect for a dictionary。

You can test whether there's a binding for a key in the dictionary with the Mem function。

 you can add a binding from a key to a value with the add function。



![](img/098348ad41cf4b736a062c38cb028634_1.png)

You can remove a binding and so forth。 There's even map and fold functions down here。 Here's fold。

Here's map。Let's create a map for days of the week， first let's write a type for days of the week。

And let's write a function that maps a day to an integer。

Now suppose I wanted to create a map whose keys were days。

 that I need to create a module that specifies what the key type is and how to compare them。😡。

How did I write that compare function Well it's based on the specification provided in the map module that specification says that the comparison should be zero if the keys are equal strictly negative if the first key is smaller。

 strictly positive， if the second key is the smaller one Now I can create a data structure for mapping days to whatever I want。

Da map。Now must have keys that are days， but it's allowed to map those keys to whatever type of values I like。

So for example， I could map days to strings that represent them。

This map M now maps the day Monday to the string Monday， the day Tuesday， to the string Tuesday。



![](img/098348ad41cf4b736a062c38cb028634_3.png)

Let's take a look at it in Utah。Note that M is abstract。

 We can't actually see the tree implementation inside of it。

But we can use the operations provided by dayMap to examine it。

Those operations all happened to be printed out up here when I created that module day mapap with a funter。

 so for example， there's now a MEm function to tell us whether a key is a member of a day map。

It will be easiest to do these examples if I just open the module right here。

So Monday is a key in that map， but we didn't put Sunday in there。

The find operation is what tells us the value bound to a key。The string Monday is bound in that map。

Tuesday。But Sunday was not。And that raises the exception not found The documentation for that is again in the standard library。

 you can look at the output signature of the funder。

And here's the find function F X M returns the current value of X and M or raises exception not found if no binding for x exists。

 If you take a close look at the type of find。It takes in a key and an alpha T。 What is alpha T here。

Let's go up to the top。Alpha T is the type of maps from type key to type alphapha。

So the key type is fixed at the time we apply the functer。

 that's because we need to fix how the comparison is going to be done for the tree nodes that are being ordered。

But it's okay to have a map from days to integers or days to strings or days to lists。

 whatever we want。 It's that value type ins strings lists that is the alpha here。

Don't worry about the plus syntax here that's getting into a feature of O Caml that we're never going to talk about this semester。



![](img/098348ad41cf4b736a062c38cb028634_5.png)

Finally， these maps are functional data structures， they don't get updated imperatively。

I added a binding to M to bind the day Sunday to the string Sunday。

I balanced that resulting new map to M prime。But M is unchanged。

 it still has the bindings for Monday and Tuesday， M prime has the new binding to Sunday。

The bindings function is another function that is from the map module that can be used to give you a list of pairs。

 The first element of each pair is the key。 the second element of each pair is the value。

 This is known as an association list。And there are functions for association lists in the list module in the standard library。

 as well。You are welcome to use maps as part of assignments， they are functional。

 they don't fall under the imperative features prohibithiion。



![](img/098348ad41cf4b736a062c38cb028634_7.png)