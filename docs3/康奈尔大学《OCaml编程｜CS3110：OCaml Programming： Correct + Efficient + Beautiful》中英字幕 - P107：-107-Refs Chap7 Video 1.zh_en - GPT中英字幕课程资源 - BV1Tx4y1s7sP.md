# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P107：-107-Refs Chap7 Video 1.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

![](img/96d5615d1e8b543b0dcabf10f01fcb40_0.png)

A reference in Ocael is appointed to a typed location in memory。



![](img/96d5615d1e8b543b0dcabf10f01fcb40_2.png)

Sometimes these are called just refs for short or a ref cell。



![](img/96d5615d1e8b543b0dcabf10f01fcb40_4.png)

Now we start getting mutability。😡，The binding of a variable name to a pointer is still going to be immutable。

😡。

![](img/96d5615d1e8b543b0dcabf10f01fcb40_6.png)

But the contents of the memory location that is pointed to are mutable with references。

 Let's recall what it looks like when we have immutable values in Ocal。



![](img/96d5615d1e8b543b0dcabf10f01fcb40_8.png)

![](img/96d5615d1e8b543b0dcabf10f01fcb40_9.png)

We can have integers， for example。31，10 is an int。 It's anonymous right now。 It's unnamed。

 We could bind it to a name。And now x is an int with the value 311。

And we know that we can't mutate X， although we can create other variables with the same name that shadow it in scope。

A ref is created with the standard Library of function Ref。You give it a value。

And that creates a pointer to a typed location and memory。

 its contents are initialized to whatever value you passed to ref。So now we have an int ref。

 which is to say a reference to an integer。It will always be a reference to an integer。

 The type can't change。But the contents of that。Location and memory can change。

In order to demonstrate that， we need to bind that ref to a name。Now we have a value Y。

 which is a reference to an integer whose current contents are 3110。

 but we can change those contents if we want。First， let's look at what's in Y。

It's an in ref whose contents are 3110。 And if you want the contents out。

 there's a de reference operator written exclamation point， often pronounced bangang， bang y。

That gets us back just the contents from that memory location， not the location itself。

 So note the change in type here， when we dereence why we get an int， not an int ref。

And that's important because if you want to actually do say arithmetic with that integer。

 you'll have to dereference it。X plus y doesn't type check because X is an int， but y is an int ref。

 Instead， we have to write x plus bang Y。And that allows us to add together those two integers。

We can change the contents of a memory location with the assignment offered。

Notice that the assignment operator simply gives us back unit。

Unit recall is the type that has only one value。So essentially what Ocama is saying is yes。

 I did the assignment， the location has been mutated。Now， if we look at why。It's an inch ref still。

 and you can't tell， but it's still pointing to the very same location of memory that it always did。

 It's just the contents of that memory location have changed They're now 21，10。

 So now if I add x plus bangang Y together， I get 5220 instead of 6220。

Let's review that a little bit。When we create a reference。

We're creating a pointer to a location in memory。

![](img/96d5615d1e8b543b0dcabf10f01fcb40_11.png)

That location and memory is typed。

![](img/96d5615d1e8b543b0dcabf10f01fcb40_13.png)

If you create an int ref， you will never be able to put a string into it。

And when we bind that location to a name， that binding as usual is immable。

 it's just the contents of the memory location that become mutable。



![](img/96d5615d1e8b543b0dcabf10f01fcb40_15.png)

![](img/96d5615d1e8b543b0dcabf10f01fcb40_16.png)

So when we say let x equal rep0， that standard library function rep is going off。

 creating a new location in memory to store integers。



![](img/96d5615d1e8b543b0dcabf10f01fcb40_18.png)

![](img/96d5615d1e8b543b0dcabf10f01fcb40_19.png)

And putting 0 in that is its initial contents。If you dereence X， you will get the contents back。



![](img/96d5615d1e8b543b0dcabf10f01fcb40_21.png)

If you assign to X， you get the unit value back simply to say yes， the assignment has occurred。



![](img/96d5615d1e8b543b0dcabf10f01fcb40_23.png)

And if you de reference x after that， the contents have changed， Theyre now one。



![](img/96d5615d1e8b543b0dcabf10f01fcb40_25.png)

X itself is always going to point to that same location and memory unless we shadow as usual。

 so it's not that the pointer changes， it's the contents pointed to that change。



![](img/96d5615d1e8b543b0dcabf10f01fcb40_27.png)

![](img/96d5615d1e8b543b0dcabf10f01fcb40_28.png)

![](img/96d5615d1e8b543b0dcabf10f01fcb40_29.png)