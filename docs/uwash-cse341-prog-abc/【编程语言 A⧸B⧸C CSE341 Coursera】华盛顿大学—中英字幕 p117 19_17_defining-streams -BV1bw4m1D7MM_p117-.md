# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p117 19_17_defining-streams -BV1bw4m1D7MM_p117-

So now that we know how to use streams， I want to show you how you can define your own。

 which is usually what you need to do first before you can use them。

 but I put it off in order to present things in the other order。

 remember that what we are calling a stream is a thunk that when you call it returns a pair of the first element of the stream and then a stream for the rest of the other elements。

 the infinitely many that follow。 So now what we want to do is make our own。



![](img/5aec2579d8df64abcc62ab557ed5ae57_1.png)

I admit this is a little mindbending， but it just uses things we already know。

 So just understand where we're using recursion， where we're using thing。

 and it's all just going to work out surprisingly easily。

 It's one of those things where the code is so short， you think it's simpler than it actually is。

 and that will be fine。 Okay， so let's just do this。 And for the first stream I want to generate。

 Let's do the simplest thing in the world。 It's a stream that no matter how many times you call it。

 it just returns one forever。 It's the infinite sequence of ones。

 So I'll just define a variable to hold my stream。 and I'll call it ones。



![](img/5aec2579d8df64abcc62ab557ed5ae57_3.png)

So every stream is a thunk。 So this is what my funk is going to be。So when I call this thunk。

 I need to return a pair， do that with cons。The first thing should be one。

And now what I need here is a stream。That。Returns all once。 So what you could think is， oh well。

 that needs to be a thunk。Right， and that's going to have to return a pair。

 And then that's going to need another thunk。 And that's going to have to return a pair。

 And we're going to be here， literally， forever。If you try to define your stream that way。

But we can do something better。Right here， where I was。I need to put right here。Something。

That is a thk that， when called。Returns a pair of one， and then a thunkk with more one。

And I actually have just the thing I need。Right。So this looks like I'm defining ones in terms of ones。

 And I am。 Every recursive function is on some level defined in terms of itself。

 And this makes perfect sense。 Ones will be bound to a thunk that when you call it。

Returns a pair of one， and then the procedure itself。

It's just recursion just in a different way than you've seen it before。

 and this really does produce the stream that let me show you if I call ones and take the car of that。

Excuse me here。Car of that， I will get a one。 And if I take the cutter of it。And。

Call that to get a pair back and take the car of that。 I get another one and so on forever。



![](img/5aec2579d8df64abcc62ab557ed5ae57_5.png)

， so that's ones。 Now let's do a more interesting one。 slightly more interesting。 we're building up。

 of course，1，2，3，4，5， something that is the stream of the natural numbers。The positive integers。

 Okay， so let's just define， let me do something here。

 They're going to define a function F that's going to take one argument and we' return the stream that starts at X。

 Allright， the stream。 So it'll do x x plus1， x plus 2 forever。

So what I do for that one is I just need to return。Let's see a pair。 Well。

 the way I'm going to do it is I'm going to say if you give me X， I'll give you back a pair of X。

 So I'm not returning a stream here。 I'm returning the pair。But then the thing in the cutter will be。

The infinite sequence that starts at x plus1 and goes on forever。 And again。

 we see recursion that if you call F with a number x。

 you get back a pair of x and a thunk that when you call it will give back a pair of x plus1 and a thk that when you call it and so on。

 and now all I need fornats is a lambda， a thunk that when you call it because every stream is a thk。

 so the stream of natural numbers is just a thk that then just calls f with1。



![](img/5aec2579d8df64abcc62ab557ed5ae57_7.png)

Okay， so this works fine。 The way I would prefer to do it。

 Let me just make a copy real fast is since F is really a helper function， I'd rather。

 I'd define it as such。😊，Cons。Cons， X， lambmbda。Tunk F plus x1。And then lambda F1。

 and that's just slightly better style。

![](img/5aec2579d8df64abcc62ab557ed5ae57_9.png)

So that's all fine。 we could test that one out as well。

 How about the one I showed you in the previous segment， powers of two that goes2，4，8。

16 and so on and we saw it grew very fast It turns out it's a whole lot like nets。

It's so much like thats that I'm just gonna copy and paste it and then say power of two powers of two。

 right。 And all I need to do is instead of adding 1， I need to multiply。By2。And get over there。

There we go。 All right。 And of course， I should have spelled lambmbda correctly。 And， of course。

 the code posted with the segment will be absolutely correct in case I'm making any typos here。

 And now I have my stream powers of two。 And of course， you just saw that sort of copy and paste。

 I really shouldn't do that sort of thing。 Instead， I should have helper functions。 right。

 So maybe a helper function could be called streammakerr。

 and it could take in a function for combining things and the argument that is the previous one。

 And I'm going leave this to you if you're curious to look up in the。😊。



![](img/5aec2579d8df64abcc62ab557ed5ae57_11.png)

![](img/5aec2579d8df64abcc62ab557ed5ae57_12.png)

Code that I'll post with this lecture。 how to define this。

 It's really just abstracting over the fact that I have a plus one here and at times to there。

 And then I define a version of Nas where I just call streammaker with the addition function in one and a version of powers of two。

 where I call streammaker with multiply and 2。But instead of showing the details of that。

 I'd rather emphasize the basic idea of what these streams are doing， that in every case。

 a stream is a thk that when you call it returns a pair。

And the way it knows the hard part of that pair is the cutter。

 the next thunk and the body of that thunk。Ends up being something that uses recursion。So innats。

 the body of that thk， which we don't call right away， just calls f again with x plus1。

In the ones case， we just got to use the function itself。 It would look more like the other ones。

 if we said lambda。No arguments call ones。Allright， and that's totally correct。

 It's just unnecessary function wrapping。 What's the point of having a thunk that when you call it calls ones with no arguments。

 ones is just as good。Okay。So the other thing I want to emphasize for you。

 because it is mind bendending and difficult to define your own streams is some mistakes you might make。

 So let's do that in terms of once。 So here's a couple of things that if you understand why these don't work。

 you may be in a better position to understand why the version above does work。

So here's one that's just really bad。It just returns cons of one and one's really bad。

So first of all， it's not returning a thk at all， it's returning a pair。And。To evaluate a pair。

 we need to look up one's really bad， but we're not even done defining it。

 All This doesn't work in a language like racket because it's an eager language when you go to evaluate this binding for one's really bad。

 We need to evaluate this pair and evaluate this pair。

 We need to look up this variable that we're not done defining it。 That really is circular。

 Something like this does work in Haskell。 If you've seen it exactly because the semantics of function call for cons is different in Haskell。

 But it definitely does not work in a language like racket or Ml or Java or any of the other languages with eager semantics for function calls。

 So that one definitely doesn't work。This one might frustrate you a little bit more if you do something like this。

 So I return a thunk。 That's great。 right。 And now I think， oh， well。

 I need to cons one onto something。😊，And now what I want to do is call this thk one's bat。

So I can do that because now my recursion is inside this function。

 so it is a recursive function call。But what this does is it does not put a thk in the cutter。

It puts the result of calling that thunk。And in its cutter will be the result of calling that thk and in its cutter will be the result of calling that thunk。

 and this is an infinite loop。 This is something that if you evaluate one's bad。

 So if I click run here， can't define things multiple times in a module。

 so let's delete all this down here and then come back up here and try it again。



![](img/5aec2579d8df64abcc62ab557ed5ae57_14.png)

So everything works fine， one's bad is a thk。😡，It's a procedure， but as soon as I call it。

 it's going to generate a list that is infinitely long， and that's not what streams are。

 I'm going to have to click stop up here。Streams are not things that are infinitely long。

 They are things that when you keep applying the thks in the couldter。

 you can keep getting additional values。 That's why the version above is correct。

 And the version bad just creates an infinite loop。



![](img/5aec2579d8df64abcc62ab557ed5ae57_16.png)

![](img/5aec2579d8df64abcc62ab557ed5ae57_17.png)

So that's defining streams on your homework， you'll get to define a stream。

 you'll also define a function that takes a stream and returns a new stream。

 that's something I didn't show you， it'll be a challenge for you。

 even though you need to do it to just take the steps we've seen。

 get the idea of right of where you have a thunk where you need to call a thunk。

 and then you can program with streams， you'll be able to test them out by using streams and you've learned a powerful and subtle programming idiom。



![](img/5aec2579d8df64abcc62ab557ed5ae57_19.png)