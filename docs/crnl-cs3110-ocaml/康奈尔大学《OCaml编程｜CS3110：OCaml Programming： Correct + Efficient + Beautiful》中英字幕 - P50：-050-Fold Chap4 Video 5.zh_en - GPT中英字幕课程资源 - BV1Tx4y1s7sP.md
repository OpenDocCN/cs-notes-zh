# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P50：-050-Fold Chap4 Video 5.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

The idea of fold right is that it folds in values of the list from the right to the left。

 kind of incorporating them as it goes， combining them in as it goes。

So think of this as like accumulating an answer。Foldrightite is accumulating an answer by repeatedly applying a function F。

To an element of a list。And what it has as the answer so far， what's been accumulated？

And it does this by folding in from the right。So it takes the initial value， folds in C。

 if C is the right most elements of the list， then folds in B if B' is the next element going to the left in the list。

 and then finally folds in A if a is the first element of the list。



![](img/008e387a5dad0b37fe9365895ed73312_1.png)

We could code that idea of ourselves。Fold， right。Needs to match against a list。

If it's the empty list， it needs to return that initial value。

We will now start calling that the accumulator， so this is the result that's being accumulated as we go along and Fulbright will need to take in that initial accumulator as an argument here。

And after pattern matching against the empty list， we could pattern match against a list that is not empty。

We want to take a function that's going to combine elements together。

So we're going to function to do that this is our what we called an op up there before。

 this is the operator that's being used to combine elements You can take that function。

 apply it to the head elements of the list and continue folding in on the right。With that function。

 the tail and the a。Now we do need to have some consistency about where we passed in the list here here I made it the second argument up here。

 it's implicitly the third argument。Honestly， you could code it either way as long as you were consistent。

 it turns out the standard library puts the list argument for fold right here。

 so I can't actually immediately pattern match using the function keyword， I need to do it this way。

And of course， I need the wreck keyword。So that's the implementation of Ftright。

Do you see why this is folding in from the right？We don't fold in the left element of the list here the head until we're done with the result of the recursive call on all of the elements to the right。

So that's what ends up making this fall from。

![](img/008e387a5dad0b37fe9365895ed73312_3.png)

As you might have suspected， there is another list library function。It folds from the left。

So the idea with fold left is that。First， the leftmost element of the list is incorporated into the initial value。

 it's accumulated as part of the answer so far。So first we use F to combine and knit with A and then with B and then with C。

 so we're moving from the left to the right in the list from the beginning of the list that head。



![](img/008e387a5dad0b37fe9365895ed73312_5.png)

Let's code that up ourselves。If we're going to fold left。With a function F。

And here actually it turns out the standard library takes in the arguments and the other order takes in the accumulator first and then the list。

 there is a mneummonic to remember this， although I tend to forget the mneummonic myself too。

 it's that the accumulator goes on the side of the list argument which is named here in the fold function。

 so for fold right the accumulators to the right of the list。For fold left。

 the accumulator is to the left of the list。Maybe that will好。So we can match against that list。

If it's empty， we return the accumulator。But if it's not empty， we need to accumulate， remember。

 from the left。And that means we're going to。Take the function that's using to combine。Eleence。

Combine the accumulator。With the head element。So we're folding in the left thing first because the left thing here is the head。

 not the tail。That gets us a new value for the accumulator。

 but I could even make that clear by saying this is the new accumulator at Prime here。

And then what do we need to do with that， we need to continue folding。

 so we need to make a recursive call fold left of the function with that accumulator and the tail So do you see why this is folding from the left？

Anytime we apply the a function F， which does the accumulation。

 which does that combination operation， we're applying it first to the head。

Along with whatever we've accumulated so far and only then moving on to use that result in continuing to fold with the rest of the tail。

Now I didn't need to actually factor this out as Act Prime here， I could replace it。



![](img/008e387a5dad0b37fe9365895ed73312_7.png)

And that gives us a little shorter of an。You might wonder why have both a fold left and a fold right。

 does it really make a difference？After all， if you think about， say folding the list 1，2，3。

 together with the initial value0 and the operation plus。What do you get if you go left to right？

Well， you add them all up and you get six what you get if you go right to left。

 you add them all up and you get six， so like there's no difference there。Why bother。Well， of course。

 not all operators work the way that plus does。If you tried to fold one， two。

 three with the initial value zero and the operator minus。

Then folding from the left to the right will get you negative6。

 folding from right to left will get you two。So in general。

 when the operator isn't associative and commutative。

You are going to get different answers doing it from the left versus the right。

And so for whatever computation you're trying to code up， sometimes you may want to go from the left。

 sometimes you may want to go from the right， and sometimes it just might not。

There's another distinction between F left and F right。

 one of them is tail recursive and the other is not。Can you spot which one is？In fold left。

There's no work remaining to be done。After the recursive call。

Whatever the right hand side of that pattern match is。

 we're just going to return the result of the recursive call。

 not do anything further to it in the body of full left。So that makes this function tail recursive。

 and therefore it will require only constant stackspace。On the other hand， fold right。

It's not tail recursive。There is some work remaining to be done there after the recurive call。

 in particular， function F needs to be applied。So fold right is going to take stackspace that is linear in the size of the list argument。

That might also drive your choice as to which one of these you want to use。

What if you wanted a tail recursive fold from the right？

You can generally get that by reversing the list first， then doing a fold from the left。Yes。

 that does require traversing the list in extra time。

 but that generally doesn't increase the asymptotic complexity of the algorithm。

And it does give you an implementation that's not going to overflow the stack。



![](img/008e387a5dad0b37fe9365895ed73312_9.png)