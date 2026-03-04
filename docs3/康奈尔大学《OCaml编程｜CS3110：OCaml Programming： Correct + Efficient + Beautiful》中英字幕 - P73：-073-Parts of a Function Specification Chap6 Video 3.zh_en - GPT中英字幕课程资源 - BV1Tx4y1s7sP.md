# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P73：-073-Parts of a Function Specification Chap6 Video 3.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's look at the pieces of that template in more detail。 We'll start with the requiresqui clauses。

The requires clause is the precondition。😡，In fact， if you wanted to write precondition colon instead of requires colon。

 that would be perfectly fine。Here's a hypothetical specification for the list standard library's head function。

 which gives you the head element of a list if there is one。

We could write requires that the list is non empty。

This would be a precondition that clarifies who to blame if the list happens to be empty。

 That would be the client's fault。Because the specification said you're not allowed to pass in a list that is empty。

If the client did pass in a list that's empty， then the implementer would be free to do whatever they wanted。

 One thing to watch out for here。 And Python programmers should particularly take note。



![](img/17509664a7d0f34757f5173253677f48_1.png)

The type is already part of the function declaration。

 There is no reason to state the type inside of the precondition here。😡。

This is different than Python because the two languages approach typing differently。

There is no static typing in Python。😡，So you're forced to document these kinds of preconditions。

 There's just no other choice。In OCl， type checking is done at compile time。

 it's impossible to pass in a value of the wrong type to a function。😡。

That's why we don't write those kinds of clauses in the precondition in a statically typed language。

 whether that's Ocael or Java。

![](img/17509664a7d0f34757f5173253677f48_3.png)

And what about the common question of should I assert the precondition？Well。

 you may have taken 1110 here or an intro programming class somewhere else and been taught， yes。

 you must always assert the precondition。Well， as we told you in 2110。

 and I'm telling you again now in 3110。The training wheels are now off。

You don't always have to assert the precondition。This is a subtle thing。

 so let me try to explain it in more detail。😡，In the mathematical theory of program correctness。😡。

A precondition must be satisfied。Before a function can be invoked。Nothing is guaranteed。

If that precondition is violated。If you want to learn more about that。

 take an upper level PL course like 4110 or 4160。But there's a difference between mathematical theory。

And good programming。Asserting the precondition is a great defensive programming technique。

And all jokes aside about setting the computer on fire。 It's more helpful to everyone。

If an assertion gets raised， right at the point at which a precondition fails rather than something more destructive。

A problem。Is that not all code is as simple as CS 1110 code。In real life。

 preconditions get so complicated sometimes that just checking them would make your code unacceptably inefficient。

For example， maybe checking a precondition about a data structure requires looking at every single value contained within that data structure。

Now， all of a sudden， you invoke an operation that was supposed to be constant time。

 and it turns into linear time because you asserted the precondition。For that reason。

 we often omit checking all the pieces of a precondition。

Maybe you only check some computationally cheap pieces of it。

Maybe only check what it takes constant time to check and don't check the rest。



![](img/17509664a7d0f34757f5173253677f48_5.png)

Or maybe you say it's on the client if they violate the precondition。😡，Next。

 let's look at the returns clause。In our OCMl code。

 we typically leave off the returns colon and just write the returns clause as the first sentence of the specification。

 but as we saw with list。 sortt， there are other ways of approaching this as well。

Here's a hypothetical specification for a sort function that is for int lists。

 So list contains the same elements as list， but sorted in ascending order。

So this is stating a post condition， it's telling us who to blame， in this case， the implementer。

If the output is bad。So if this function returned a list that was not sorted。

 that would be the implementer's fault。Unless， of course。

 there had been a precondition and the client and violated the precondition。

Say with the standard library function， if the client passed in a bad compare function。

But here there is no preconditions， so it's all the implementer's job。



![](img/17509664a7d0f34757f5173253677f48_7.png)

Another piece of a specification can be an examples clause。

 This gives examples of input and output so that someone reading the specification has a concrete idea to latch onto in case the more abstract words that are in the specification aren't helping them。

This is especially helpful at clarifying boundary cases， extreme all kinds of inputs。

Here for the sorting function， I've written two examples。

 one of which has duplications in the list to show what happens with those they are preserved。

And one of which is for the empty list， which shows that the sort of the empty list is。

This can be super helpful for our human brains to understand specifications。

 even if the spread of the specification is mathematically precise and clear， examples are still。

The raises clause tells us about exceptions that might be raised by an oaml function。

Going back to our hypothetical specification for head。

We could add a raises clause that says what happens if the client violates the precondition。

It raises failure with a string head。This is what the standard library function happens to do。

That makes the exception actually part of the post condition。

Because it's stating a behavior of the function， and it's on the implementer to ensure that that behavior actually occurs。

If head failed to raise this exception when the input list was empty。

 that would be the implementer's fault。The client， in fact， might be relying on this behavior。😡。

And so the implementer has to make sure that it app。



![](img/17509664a7d0f34757f5173253677f48_9.png)