# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p23 22_12_let-and-efficiency -BV1bw4m1D7MM_p23-

In this segment， I want to demonstrate why it's important to avoid doing recursive computations repeatedly。

 and I want to show you that lead expressions are the natural way to avoid that problem。



![](img/e851d224e77557dd7ff59df220ee3350_1.png)

So to do this， I'm gonna to use a small example here。 So let me show you what this code is doing。

 it's a bad example。 It's not going to work well。 So I've called it bad max。

 and the idea is to take a list of integers and return the maximum number in the list。 Now。

 that doesn't make any sense that the list is empty， So in that case。

 I really ought to do something like raise an exception or in the next segment。

 I'll show you another option for how to deal with that。 But since that's not my point here。

 if the list is empty， I'll just return0。 Now this is terrible style。

 but it's not my point and it's not what's bad about this function that I'm emphasizing here。

 so ignore that case， otherwise if the element， if the list has just one element。

 So the tail is null， then return that one element， the head of the one element list。

 that's the maximum of one element list。 otherwise。

 if the head is greater than the max of the rest of the list， return the head。

 otherwise turn return the max of the tail of the list。So this actually ignoring the empty list case。

 does work correctly。Okay， and yet， it's still a horrible algorithm。

 And to show you that I'm going to use a couple helper functions I wrote。 count up and count down。

 So here they are in the file。 We don't need to go through them。

 They just will basically include all the numbers from from to to inclusive。

 either from smaller to larger or from larger to smaller。

 So just know that when I come here and test out bad Maxs here。So here I am in my Reple。

And let's get everything loaded up here。 I also already have it fixed。

 So you're gonna to see a good max here as well that also has type int list arrow int。

 But we're still working on bad max。 So suppose I do bad max count down。

 let's say from 30 to 1 so it turns out the maximum of that is 30。 And sure enough。

 if I said 30 to 2， It would still be 30。 And of course， this is a perfectly good function。

 I could make a 30000 element list and ask the max of it。 computeruters are fast these days。

 I get 30000。 No trouble。 Okay Now， what if I tried counting up instead。 So， you know。

 if I want to count up from one to 10。 That's fine。 The max is 10。1 to 20， It's fine。

 I did test this out ahead of time。 watch this 25。Do you see a little delay there。

 just a little bit of one， How about 28。A little bit more of one。 If you tried 30000。

 you would be here for a very， very long time， In fact， even at 30。It seems to have quite a delay。

 In fact， I don't even want to wait for it to finish， although we'll finish here in a few seconds。

So what's going on here， Let's look back at our code。It's that count up case that isn't going well。

 so let's think about what happens when the bigger numbers are near the end of the list。

So we come in here。 We have like our 30 element list。 It's not empty。 So we don't do this then 0。

 It's not almost empty。 So we don't do this。 So what we end up doing is computing。

 what's the maximum of a 29 element list。Well， that's no problem。

 That'll eventually come back and say 29。 And then we'll say， oh， oh， it's sorry。

30 because we have two through 30。 So then when we come back and we have that 30。

 we'll end up computing baddmax again。So naively， you might think oh。

 so the count up version is gonna to be twice as slow as the countdown version。 Well。

 no that's not the case because in that recursive call where we have a 29 element list we're going to end up calling bad Maxs twice on 28 element lists but if we call it twice on a 29 element list and each of those calls it twice on the 28 element list and each of those call it twice on the 27 element list you can see this is actually doubling at each level so it's not twice as many calls it's actually exponentially more calls and that is a huge difference So let me try to make this point a little better with a couple slides here is our code here。

 and don't worry about the calls to null and head and tail。

 it turns out those all do just a little bit of work。

 they take the beginning of the list and they either just say whether it's empty or not or return the first element or just return a reference to the rest of the list so those are all fast。



![](img/e851d224e77557dd7ff59df220ee3350_3.png)

Those recursive calls the bad Max we have to be careful about。

And here's what it looks like in the countdown case， bad max of 504948 calls bad max of 4948。

 which calls badd max of 48 and so on， and if we had a 50 element list。

 we would end up doing about 50 calls。But in the count upcase。We end up with we start with our list。

 making two calls。RightOnce for in between the if and the then and once in the else and each of those recursively makes two calls and each of those recursively makes two calls。

 So it looks like1，2，4，8。 if you've ever doubled the number 150 times you get an enormous number。

 which is why even for 30， we saw a noticeable pause before we finished。

I also want to point out that counting up here is not just the only case that has this problem if you just have the biggest number。

More than 50 elements from the beginning of your list， it's going to take forever to compute。

 So if you had a 3000 element list， a yes， countdown is very fast。

 but even if those numbers were randomly shuffled， chances are the maximum element is not going to be close enough to the beginning of the list for it to compute efficiently。



![](img/e851d224e77557dd7ff59df220ee3350_5.png)

Okay， so it looks like ML has a problem， right， It looks like recursion is terrible。

 We should have used a for loop or something。 Of course， that's not how I feel。

 What we just need to do is avoid doing these repeated computations。

 And we know how to avoid doing a repeated computation。

 What we can do is do that computation and store the result in a variable。

 And this is the last use I'm showing in this section of the course of lead expressions and why they're so important。

 So all I want to do is avoid computing bad maxs twice by remembering its answer。😊，In a variable。

 So that's what good Max does。 So I really shouldn't call it good Max because it's still doing the empty list case completely wrong。

 But ignoring that for nonempty list， it does the right thing。 So if the tail of the list is empty。

 then just return the head of the list。In the else case。

 compute the maximum of the rest of the list and remember it Here。

 I've just stored a variable tail ants just to remember what it is。 And now let's use that。

To say if the head of the list is greater than tail ans than return head。 Otherwise。

 don't call good Max again。 Just return tail ans。 And this will work absolutely fine。

 So if I just try good max。 Oh， look， my answer for 30 did finish。 Good Max。 I get 30 right away。

 And I can even count up to 3000， it'll work just fine。 Countdown still works。 correctly as well。

 it didn't actually need this because in the countdown case， Well it's taking a minute here。

 I think just because I've created such a large list， We'll look into that later。

 and I'll fix the code up for you。 Let's go back to the slides。😊，嗯。Oh， did I oh。

 I know what's going on here， I did figure it out。By the way， control C。

 control C to break an infinite loop。 When you call countdown。

 you're supposed to put the larger number first。 If you do it the other way。

 countdown itself is going into an infinite loop because of how I wrote it。

 Good Max never got called。There we go。 all fixed。 Okay， back to the slides。

 Always fun to mess up on the fly。

![](img/e851d224e77557dd7ff59df220ee3350_7.png)

All right， so why is that happening？ Why is badm taking so much longer？ Well。

 you can just work out the arithmetic， Suppose that the amount of work badmax does ignoring the recursion is say takes one。

10 millionth of a second。 I have no idea if that's anywhere close to right。

 but 110 millionth of a second seems pretty fast。 right Well。

 then in the case where we made 50 recursive calls， it's going to finish in 51 million。

10 millionth of a second right， or half a millionth of a second， faster than humans can tell。

But if we do it in the countup order， we have to multiply that  one in 10 million by 2 to the 50th and if you work out the arithmetic。

 that answer for a 50 element list is going to take about three and a half years and for a 55 element list it would take over a century。

 so I always like to emphasize that it's not about computers getting faster if you don't write your code in an efficient way and in a language that encourages recursive functions。

 you need to avoid doing unnecessary recursion that leads to this exponential blowup where you go 1。

2，4，816 okay。Once we fixed our code like you see here。

 then everything works great because we only ever call good Max once on the whole list。

 then the tail of the list， then the tail of that list and so on thanks to our lead expression So in both the countup case and the countdown case and in fact。

 any other case， any order of elements in any list we will just have 50 calls So if we guess that it takes 110 millionth of a second to do one of these calls。

 it's going to take 5010 millionth of a second  one10 millionth of a second to do all of them okay so that is how to use lead expressions combined with recursion to avoid pathological cases where you're extremely inefficient and that concludes our discussion of lead expressions for now。



![](img/e851d224e77557dd7ff59df220ee3350_9.png)