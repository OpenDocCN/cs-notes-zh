# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P120：-120-Association Lists_ Bindings Chap8 Video 4.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

The next thing I should do with test driven development is pick some test case involving in an operation and implement a test for it that fails。

We already have the empty value。Maybe that's a good place to start as something simple。For example。

 we know what the bindings from that empty list ought to be， there ought to be none。😡。

So let's write a test case for that。All right， I've implemented my first test case to assert that the bindings of the empty association list map is just the empty list。

 Let's confirm that that test fails。Indeed， it does yay。

 that means we have something to fix now the problem， of course。

 is that we haven't yet implemented bindings Now how are we going to get the bindings of a list？

One very simple thing we could do first is just return the list itself。Now。

 I don't know that that necessarily meets the whole specification， but it compiles。

And it passes the test。This is test driven development。

 we don't necessarily get it right the first time， but we keep making progress， we keep compiling。

 we keep adding tests。Now， if I think about the specification for what bindings was supposed to do。

 I know that there's going to be a problem bindingds says there's no duplicate keys in the list。

But we didn't define a representation andvari to prevent duplicate keys in our actual representation type for association lists。

That means we need to do some work in our bindings function to eliminate any duplicates。

 Let's just get a list of all the keys。Get rid of any duplicates from that list of keys and then transform that list of non duplicateuplicd keys into their bindings。



![](img/4b70172843df87e33010f1eb5f493cbd_1.png)

I've made a little bit of progress now。I've implemented that algorithmic idea that I had of taking all the keys in the map。

And producing a list of those， that's what my keys function is going to be doing without any duplicates。

And then I will transform each of those keys into the pair。

 which represents the binding for that key， so that's what applying list do map to the function binding M will do。

I've partially applied binding here to the map。😡，What that means is each of the keys that is passed in from that input list is now going to be mapped to the binding for that key。

😡，At this point， I could run my test again to make sure it's still failing and importantly still compiling。

It is still failing， but with a different failure I got to do now instead of unimplemented。

 because now I'm calling one of these other functions that I still need to do。

Let's implement keys first。I'm following back on my old friend here， list。

st unique to get rid of any duplicates， taking all of the pairs from the association list。

 mapping them through the function first， which just gets the key component out of each of those pairs。

 and then making all of those unique by passing it through list。 sortt。😡。

Let's pause here to think about the efficiency of this function。It takes linear time。

To map through a list with the function first。 So the first part of this here is。Big O of n。

 where in is the number of elements in the list。But listist do sort unique。

 as you will remember from the library documentation， requires n log N time。

 again where n is the number of elements in the list。So the efficiency of keys is Big O and log n。

Now what about binding， how do I get a binding out of the list？😡，That's actually easy。

 and I can even do it in terms of a standard library function。

 which already exists to look up the binding of the leftmost key in an association list。

That's all there is to it。Now let's try running our test suite。Yay， success。

 we were able to correctly determine what the bindings are in the empty map。



![](img/4b70172843df87e33010f1eb5f493cbd_3.png)