# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P55：-055-Functional Stacks Chap5 Video 3.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Remember the stack data structure。It's like a stack of trays in the cafeteria。

Items get pushed onto the top and popped off。Let's code up stacks in OAO。

So far I've created a module named my stack， I named it my stack because there's already a stack module in the standard library。

 and I don't want to get any confusing error messages because of that。



![](img/4c2b3bb90540eb7f6d975a4602255c7f_1.png)

It's a structure inside that structure， there's a tight alpha stack。An alpha stack is either empty。

Or there's an entry on the stack， which is a pair。 The first component of that pair is the actual value on the stack at that point。

And the second component of the pair is the rest of the stack。



![](img/4c2b3bb90540eb7f6d975a4602255c7f_3.png)

Now I can cut up all the usual stack operations。

![](img/4c2b3bb90540eb7f6d975a4602255c7f_5.png)

Let's talk about those operations。I've created a value called empty inside of the MyStack module just to produce the empty stack。

This is for convenience for now， obviously I could write capital of the as the constructor as well。

 but we're going to code up a lot of data structures and it's helpful just to remember that the name of the empty value of the data structure is just empty no matter what the internal implementation of the data structure might be。

To push a value X onto a stack。I create a new entry with X at the top of the stack and the rest of the stack below it。

Now I have two functions， peak and pump。The idea of peak is that it tells me what the top value of the stack is。

The idea of pop is that it removes the top value of the stack。

Now sometimes some stack data structures combine those two operations together。

 they give you just a single operation that gets you the top element and removes it。

 we're going to decouple them for now。Peak here therefore。

 takes in a stack and gives us back the top value of it。 You can see that in the type， Alpha stack。

 arrow Alpha。Pump takes in an alpha stack and gives us back an alpha stack。

 It's not giving us back of value from the stack。 it's giving us back another stack。

Pe and pop P are implemented quite similarly， they both just pattern match。If the stack is empty。

 they raise an exception to say that the stack was empty。If the stack is not empty。

 then they return the appropriate components of the pair inside of the entry。Now。

 if you've been looking at this implementation and thinking that the tight alpha stack looks awfully familiar。

 you're right。It's basically the same as the definition of lists。Instead of stack。

 I could have written list， instead of empty， I could have written nil。

 and instead of entry I could have written cons， and we would have our my list type that we've seen before。

So why not just directly implement a stack as a list， let's do that。

Type Al stack is just a synonym here for alpha list。

 They mean the same thing inside this body of code。 The empty S is just the empty list。

 pushes just a cons operation， and Pe and pop correspond to just doing pattern matching to get the correct value out of the stack。



![](img/4c2b3bb90540eb7f6d975a4602255c7f_7.png)

To use a stack， I could create an empty stack。I could push another value onto the stack。

And I could peek at the top value of the stack。Let's look at that in U top。

So you can see that I had a stack S that was empty， another stack S prime that contained one。

 and when I peaked at S prime， I got the value one out。Now。

 notice that peaking the stack does not change what's in it。Still has one。

And notice that pushing created a new stack S prime。But it left the old stack unchanged。

I could even pop S prime。Which gets me back the empty stack， but as prime is unchanged。

Let's compare the syntax for some similar stack operations in Java and Ocael。In Java。

 you might have a stack class that you could instantiate to get a new object S。

And then you could push one onto that stack。In OCMel。

 a similar series of operations would be to create a stack with maybe my stack。

t empty or list stack dot empty。To bind that empty stack value to a variable S。

And then if you wanted to push onto that stack， you could say push one onto it。

So notice that when you create the stack， we don't use the new keyword instead we just refer to that empty value that was defined inside of the module。



![](img/4c2b3bb90540eb7f6d975a4602255c7f_9.png)

And when you go to push onto the stack， instead of writing。Stack dot push。

You instead write pushush and the stack becomes an argument to the push function。



![](img/4c2b3bb90540eb7f6d975a4602255c7f_11.png)

It might feel like this is a little backwards in Ocal compared to Java because of where the dot goes and where the arguments go。

As it turns out， if you take the compilers's course and learn about how OO languages are implemented。

 or even if you've took Python and happen to remember the self parameter to methods。

Java actually compiles that S dot push one down to a version which is push with S supplied as an argument to it。

😡，So in reality， thinking of the object as another parameter to a method is the right way to think about it in OO languages in some sense。

So by the time you get down to the implementation in Java。

 it's really not so different from OcaMl at all。

![](img/4c2b3bb90540eb7f6d975a4602255c7f_13.png)