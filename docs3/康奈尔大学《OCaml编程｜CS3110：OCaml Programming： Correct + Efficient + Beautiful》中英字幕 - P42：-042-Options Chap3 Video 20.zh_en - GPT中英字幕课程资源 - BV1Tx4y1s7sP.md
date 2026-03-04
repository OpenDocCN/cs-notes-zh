# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P42：-042-Options Chap3 Video 20.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's take a look at another built invari in the OAML Standard Library called Options。

They're not going to seem very familiar at first。Definitely not from Java。

 but they solve a problem that Java has trouble solving and they do it in a particularly nice way。

Options are defined very simply。Type alphapha option is either none。Or sum of alpha。

I like to think of an option as being like a box。That box is either empty or there's something in it。

So the emptiness is represented by the nun constructor。Or。

There's something in it that's represented by the sum constructor。

And that alpha carried along by the Sun constructor is the thing inside the box。



![](img/b27112933d504f5f78ba8c3b0a6bab2b_1.png)

So for example， I could have none。This is a type alpha option similarly to how an empty list has type alpha list。

 there's nothing in it so that type variable alpha could be replaced with anything at this point。

If I have something like say one， I've put that into the box， then I have an int option。

 or if you wanted to think of that right to left， you could think of it optionally this is an int。

 he optionally is in the sense of there might be one there or maybe there's nothing there at all。

 which would be represented by none。I could have much more complicated kinds of data in here as well。

 like I could have a list， so that's an int list option， or if I read that type right to left。

 optionally this is a list of integers。How do you get a value out of a box or out of an option？

Well options are just variants so we can do it with pattern matching Let's write a function that just gets the value outside of an option。

 takes something out of a box as it work。

![](img/b27112933d504f5f78ba8c3b0a6bab2b_3.png)

Okay， we've written the function get Val， its type is alpha option arrow alphapha。

 it's going to try to get the alpha out of an alpha option to do that it matches the O that was passed in with either none or some in the case that there's something inside the box。

 get Valal can return that something。But what are you going to do in the case where there's nothing inside the box。

 I don't really know what to return there。There's nothing reasonable to return。

 we don't know what alpha is so we can't return some kind of default value of type alpha。Really。

 all we could do is ask the programmer who's calling this function to tell us what default value they want if there was nothing inside the box。

And now we can return that default value， get Val now has type alpha， arrow alpha option。

 arrow alpha， it's going to always be able to give us back a value of type alpha。Of course。

 I could have used the function keyword here。To improve that just a little bit。

Just having boxes and trying to get values out of them is not very interesting。

 nor is it especially idiomatic。What options are really useful for is as a return value from a computation that might not return something meaningful。

Let me give you an example， S you wanted to take the maximum of a list。

So X could be the maximum of the list  one， two， three。

 I'm imagining that we have a function list max here， we haven't written that yet。Well。

 for List Max 123， we probably should get three as a result。

But what should list max of the empty list be？Well。

 you might decide that it should be some extremeal value for an integer。

 you might decide to raise an exception。But a more principled way of handlinglines this is to return an option。

Return none for the empty list。Return sum three for the list  one，2，3。

So really what we run right here is a function list max。That takes in a list。And gives us back。

An alpha option， it optionally gives us back an element of that list as the idea。

I can quickly cut up the body to function。

![](img/b27112933d504f5f78ba8c3b0a6bab2b_5.png)

OkayI'm almost done coding it up if the list is empty I return none， the kind of empty box。

 if the list has a head in a tail， then I return a box。

 that's the sub constructor in front and what am I going to put into that box I'm going to put the maximum of two values either the head of the list or the max of its tail。



![](img/b27112933d504f5f78ba8c3b0a6bab2b_7.png)

![](img/b27112933d504f5f78ba8c3b0a6bab2b_8.png)

But I'm still getting a compilation error here， and that's because when I take list Max recursively here。

 that has type alpha option。

![](img/b27112933d504f5f78ba8c3b0a6bab2b_10.png)

![](img/b27112933d504f5f78ba8c3b0a6bab2b_11.png)

But the head has type alpha， so I'm trying to compare an alpha to an alpha option that polymorphic comparison is getting an error message there because those two things don't really have the same type。

So instead， what I need to do is get the value out of that box from the recursive call to list Max。

Okay， so after writing a little bit more code there， what am I doing？

I'm matching the result of calling list Max on the tail that gives me an alpha option。

That option might or might not have something in it。 remember the tail might be empty。

 so in the case of the tail was empty， I got none back from the recursive call。In that case。

 I'm just going to return some H， I'm going to return the head of the list inside the box because it's the only elements in the list。

 so that's got to be its maximum。On the other hand。

 if I did get some maximum element back inside that option from the recursive Calist max。



![](img/b27112933d504f5f78ba8c3b0a6bab2b_13.png)

Then I want to return an option， so I start with sum。

 and then I want to take the max of the head element from the list that I'm looking at with the max of its tail。



![](img/b27112933d504f5f78ba8c3b0a6bab2b_15.png)

![](img/b27112933d504f5f78ba8c3b0a6bab2b_16.png)

Stylistically， one thing I want to point out is that you really should write begin and end around a nested pattern match like this。

 there's a good reason for that it's to help Ocael and humans make sure they're parsing the code correctly。

Begin and end are really just the same thing as parentheses stylistically we tend to use beging and end around these nested pattern matches because they're a little bigger and they help us see the grouping a little bit better。

Now why do you need it， Well， let's suppose we hadn't had them in there。Okay， so I've moved。😡。

The first branch from the outerered pattern match below。Rather than having it above。

 now watch what happens when I save and Merlin reformats my code。It has moved that pattern branch。

Into the inner match expression there， because that's how Ocael is actually parsing it as the nearest match expression。

So really what I should have done is I should have kind of put it begin here。And an end here。

 and now OK will parse it correctly and now that it can parse it correctly。

 all of the type errors go away as well because they were actually coming from the miss parse。



![](img/b27112933d504f5f78ba8c3b0a6bab2b_18.png)

I mentioned before that options give you a way of solving a problem that Java struggles with。

That problem is no pointer exceptions。Don't take my word for it， take Tony Hor's word for it。

If you were in 2110 last semester， you got treated to a final lecture in which Tony Howard made an appearance。

 he won the Tring Award in 1980 for his fundamental contributions to the definition and design of programming languages。

 as you know， he's the inventor of Quicksortt。He writes that he calls no his billion dollar mistake。

He was designing the type system for an object oriented language。

 and he couldn't resist the temptation to put in a null reference。This has led to innumerable errors。

 vulnerabilities， and system crashes， which have probably caused a billion dollars of pain and damage in the last 40 years。

Options are a principled alternative to know。Instead of letting every reference in Java be either null。

Or a pointer。Instead， the Java type system could have had options in it。

And now every reference could have been an option and you could have had to pattern match against it to see whether it's none or whether there's something in it。

Forcing the programmer to do that kind of pattern match would make sure that they consider the possibility of a null pointer error anywhere they do a D referenceence。



![](img/b27112933d504f5f78ba8c3b0a6bab2b_20.png)

So the moral of that story， as Drake would say， avoid noll pointer exceptions。

 instead pattern match against none。

![](img/b27112933d504f5f78ba8c3b0a6bab2b_22.png)

![](img/b27112933d504f5f78ba8c3b0a6bab2b_23.png)