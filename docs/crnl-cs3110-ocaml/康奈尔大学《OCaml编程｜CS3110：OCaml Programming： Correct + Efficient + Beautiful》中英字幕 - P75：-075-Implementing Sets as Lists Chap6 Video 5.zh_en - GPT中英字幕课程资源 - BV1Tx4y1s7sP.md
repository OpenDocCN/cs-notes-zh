# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P75：-075-Implementing Sets as Lists Chap6 Video 5.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's implement this with a data structure based on lists。



![](img/621cd7ba96bacb0d4d64736659b6366f_1.png)

![](img/621cd7ba96bacb0d4d64736659b6366f_2.png)

We should pause here to clarify how we're going to represent a set as a list。



![](img/621cd7ba96bacb0d4d64736659b6366f_4.png)

![](img/621cd7ba96bacb0d4d64736659b6366f_5.png)

There are several choices we could make。Maybe the simplest one is just to say that the list directly represents a set。



![](img/621cd7ba96bacb0d4d64736659b6366f_7.png)

![](img/621cd7ba96bacb0d4d64736659b6366f_8.png)

So I've written down a comment above the type。

![](img/621cd7ba96bacb0d4d64736659b6366f_10.png)

To say how the list will represent the set。It's not a perfect comment yet， but I'm getting there。



![](img/621cd7ba96bacb0d4d64736659b6366f_12.png)

The list A1 through A N represents the set， A1 through A N。



![](img/621cd7ba96bacb0d4d64736659b6366f_14.png)

The empty list represents the empty。

![](img/621cd7ba96bacb0d4d64736659b6366f_16.png)

Now， what I haven't said anything about here yet is what if that list contains duplicate elements？



![](img/621cd7ba96bacb0d4d64736659b6366f_18.png)

After all， that's one of the key distinctions between the abstraction of a list and the abstraction of a set。

Listists can have duplicates。 Se don't really have duplicates。



![](img/621cd7ba96bacb0d4d64736659b6366f_20.png)

Let's keep that in mind going forward and see how it impacts the operations that we。



![](img/621cd7ba96bacb0d4d64736659b6366f_22.png)

![](img/621cd7ba96bacb0d4d64736659b6366f_23.png)

Here duplicates become relevant。

![](img/621cd7ba96bacb0d4d64736659b6366f_25.png)

If I want to compute the size of a set。😡，I could take the length of the list that represents it。



![](img/621cd7ba96bacb0d4d64736659b6366f_27.png)

But that works only if that list contains no duplicates。 If it did。

 I'd get the wrong answer by using the invitation。

![](img/621cd7ba96bacb0d4d64736659b6366f_29.png)

![](img/621cd7ba96bacb0d4d64736659b6366f_30.png)

Now， maybe this is a good way to implement size， maybe it's not。

 let's stick with it and go back to our documentation for the representation type。😡。



![](img/621cd7ba96bacb0d4d64736659b6366f_32.png)

And add to it the restriction that lists can't contain。



![](img/621cd7ba96bacb0d4d64736659b6366f_34.png)

![](img/621cd7ba96bacb0d4d64736659b6366f_35.png)

This ensures that my implementation of size is correct。



![](img/621cd7ba96bacb0d4d64736659b6366f_37.png)

![](img/621cd7ba96bacb0d4d64736659b6366f_38.png)

Let's pause again， I've implemented add simply as cons。

 just cons the elements onto the beginning of the list。😡。



![](img/621cd7ba96bacb0d4d64736659b6366f_40.png)

![](img/621cd7ba96bacb0d4d64736659b6366f_41.png)

This is a simple implementation， but it's incorrect。



![](img/621cd7ba96bacb0d4d64736659b6366f_43.png)

Because what if x is already an element of that list？😡。



![](img/621cd7ba96bacb0d4d64736659b6366f_45.png)

Then I've violated this invariant up here that the list must not contain duplicates。



![](img/621cd7ba96bacb0d4d64736659b6366f_47.png)

So these two implementations， size and add。😡。

![](img/621cd7ba96bacb0d4d64736659b6366f_49.png)

Can't coexist nicely。We can either have one of them or the other， but not both。😡。



![](img/621cd7ba96bacb0d4d64736659b6366f_51.png)

For now， let's keep the implementation of size and change the implementation of add to make it。



![](img/621cd7ba96bacb0d4d64736659b6366f_53.png)

Now I am checking to see whether an element is a member of the list already。 If it is。

 I'm not adding it in。 Therefore， Therefore， I'm not creating any duplicates。

If it's not already an element of the list， then I can concept。



![](img/621cd7ba96bacb0d4d64736659b6366f_55.png)

Let's think about the efficiency of these two operations。



![](img/621cd7ba96bacb0d4d64736659b6366f_57.png)

What's the efficiency of size？It's linear time。

![](img/621cd7ba96bacb0d4d64736659b6366f_59.png)

Because list dot length requires linear time in the length of the list。



![](img/621cd7ba96bacb0d4d64736659b6366f_61.png)

What about a。Well， now every time I want to add an element to the list。

 I actually have to check the entire list to see if it's there yet or not。



![](img/621cd7ba96bacb0d4d64736659b6366f_63.png)

![](img/621cd7ba96bacb0d4d64736659b6366f_64.png)

That means that the implementation of a is also linear time。



![](img/621cd7ba96bacb0d4d64736659b6366f_66.png)

So I don't have a particularly efficient implementation of sets here yet， that's okay。

 we'll live with it for now。

![](img/621cd7ba96bacb0d4d64736659b6366f_68.png)

![](img/621cd7ba96bacb0d4d64736659b6366f_69.png)

To check that， we could even put in the module type annotation to cause OKA to check and see whether list set really does match the set module。



![](img/621cd7ba96bacb0d4d64736659b6366f_71.png)

![](img/621cd7ba96bacb0d4d64736659b6366f_72.png)

![](img/621cd7ba96bacb0d4d64736659b6366f_73.png)

And if indeed， it does， I don't get any compilation errors there。



![](img/621cd7ba96bacb0d4d64736659b6366f_75.png)

A fair amount of this code could actually be cleaned up and simplified。



![](img/621cd7ba96bacb0d4d64736659b6366f_77.png)

A fair amount of this code could be cleaned up and simple。



![](img/621cd7ba96bacb0d4d64736659b6366f_79.png)

We didn't need to actually take in arguments and apply the functions。

 we could just directly say that size is list stop length and that MEM is list dot。



![](img/621cd7ba96bacb0d4d64736659b6366f_81.png)

![](img/621cd7ba96bacb0d4d64736659b6366f_82.png)