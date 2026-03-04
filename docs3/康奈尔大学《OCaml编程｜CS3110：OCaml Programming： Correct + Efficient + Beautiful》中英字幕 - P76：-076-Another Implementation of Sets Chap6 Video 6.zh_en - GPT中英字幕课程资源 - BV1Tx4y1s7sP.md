# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P76：-076-Another Implementation of Sets Chap6 Video 6.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's return to the notion of the efficiency of some of these operations。Obviously。

 we could have a more efficient implementation of a if we didn't have to check whether the element was already in the list。

But that violated the invariant we wrote for the representation type。Let's revisit that invariant。

Let's try making a different decision and allowing the list to contain duplicates。Of course。

 we get a constant time operation for a now。But size is incorrect。

Since the list could contain duplicates， it may be overcounting how many elements are in the set。

 so we need to fix that implementation。To compute the size of a list。

 we have to check and see whether each element of it is already a member of the tail。

That's not particularly efficient。In fact， we're going to be traversing the tail many， many。

 many times。 This turns out to be a quadratic time implementation of size。

 That's much worse than the linear implementation we had before。Could we do better？Well。

 what if we could remove all the duplicate elements of the list？

Then it would be back to just taking the length of the list。Let's try that。

I'm using a library function called sort uniqueique。

That in addition to sorting a list also removes duplicate elements at the same time。

 the documentation for that function says it runs in linear aic time that is in log N。

That's much better than quadratic time， still not quite as good as linear。By the way。

 I could clean up the code for addd as well。Finally。

 suppose I wanted to add a union operation to take the union of twoet。

Now that I've added union to the signature， I get a type checking error because my modules don't actually provide that operation yet。

 so I'll need to add it to both of them。😡，Let's pause here。

 It's tempting to implement union just as list append。

Because we could just take the two lists and push them together and say that's the resulting set。

But that violates the invariant that we documented， the list may not contain duplicates。

So we need to do a little more work to get this implementation to be correct。

 we need to discard those duplicates S unique could be helpful here again。Now， we've removed all the。

し。Of course， with this implementation of sets as lists that may contain duplicates。

 append is perfectly fine as the operation， it doesn't matter whether there are any duplicates。

 size will take care of that for us later。Indeed， we could even clean this coat up a little。

That concludes our implementation of two data structures。

Both of them use lists to implement the set data abstraction。

And there are some similarities and differences between these data structures。

Those are most clearly exhibited in the documentation comments we wrote。

 and in particular the invariance that we chose for each representation。



![](img/ac56f1ff5e79afa161c16fa75665097a_1.png)

![](img/ac56f1ff5e79afa161c16fa75665097a_2.png)

![](img/ac56f1ff5e79afa161c16fa75665097a_3.png)