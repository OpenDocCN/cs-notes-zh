# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p63 62_13_closure-idiom-combining-functions -BV1bw4m1D7MM_p63-

This is the first of several segments where we're going to take what we've already learned about function closures and discover additional powerful programming idioms that that semantics will let us use。

 So we know the semantics， we know lexicalco。 We know function closures。

 and we've already done one of the key idioms that is passing functions to iterators。

We're now going to do several more。 You see the list here。 And in this segment。

 we're going to focus on this combining functions。 This is going to be writing things like function composition。

 So without further ado， how about I just go over to Eax here and write function composition for you。

 So what I want to do is write a function compose that's going to take in two other functions。

 F and G and return a function that when you call it just cause returns F of G of X And we can do that。



![](img/085fdafdcd16946117af13981a7dbfb0_1.png)

Alright， so F of G of X。 And if you call compose with two functions and get a function back。

 that function you get back is absolutely using the semantics foreclosures so that when you call it。

 it can look up F and G in the environment that was present back when we defined this function。😊。

function composition is a fundamental idea in mathematics and in computer science。

 So let's take a minute just to study it a little bit。

 I like to think of its type as something that takes。These two arguments。

 so a function from alpha to beta or A to B， if you will， that's the G and a function from B to C。

 that's the F and returns a function from A to C。And once you look at the type like that。

 it's almost painfully clear what the function does。

 it pretty much has to call F of G on its argument A here to eventually return this argument of type C。

Now just to warn you， if you try this out in ML， you get the repple。

 which has no idea that a is the first letter of the alphabet and B the second or anything。

 returns this type here， it's missing a couple parentheses and it's used different type variables for different parts of the type。

 but I promise you that it's an absolutely equivalent type。Alright， now。

 it turns out that function composition is nice enough that it's been provided by Ml。

 It's been provided as an infi operator。 The same way Plus is a function that takes two arguments。

 but we happen to write it between the arguments。 in Ml。

 They took the lowercase O0 like the O like this。 not 0。

 O and said that's the function composition argument。 So you can write F composed with G。

 And that's exactly the function we wrote up here。 So let me show you an example of using it。

 I'll start with the old boring way that doesn't use this。

 Let's write a function square root of absolute value。 So it's going to take an integer。

 It's actually going have type int arrow realel real is Ml's floating points。

 And all I want to do is take the absolute value of I。😊，And then convert that to a real number。

 because that is what this other library function math square root requires。 All right。

 so this will work absolutely fine。 But now let's write a version that instead uses function composition So here's a second version where I can better express。

 better indicate to the person reading my code that what I really am doing is composing。

Three functions， we could put more parentheses in here。

 but the order won't actually matter function composition is associative。

 and I'm just now taking the function return from this higher order function call and applying it to I。

And now you might notice that this has our standard pattern of unnecessary function wrapping so we could express even more clearly and directly what we're doing by just saying that square root of abs is variable the value you get by composing math that square root with real dot from it and the absolute value function。

So that's using function composition， we see that we need closures for this to work out correctly。

What I thought I might do now is point out that as nice as function composition and that order is in math。

 we end up kind of having to read this right to left。



![](img/085fdafdcd16946117af13981a7dbfb0_3.png)

Take the absolute value， convert to a reel， then take the square root。

Which is a little bit backwards， especially if you're reading your code in English。

 where most programmers are used to reading left to right。😡，So in more recent years。

 a different operator has become more popular。 This is used a lot in F sharpharp。

 which is a dialect of M and functional program is just like to use this a bit as well。

 and I've defined it here on the slide but I think I'll just go back to the code and redefine it for you here。

 Now on the slide and in F sharpp this operator is usually written with the pipe character and then the angle bracket。

 I discovered that in the current version of SMml mode for emax that I'm using using that pipe character snarls it up and makes it think I'm using a different language feature。

 So instead I'm just going to use exclamation point angle bracket。 But in either case。

 we can make up our own infi operator the same way plus is something that takes its argument on either side I'm going to use this keyword that's kind of fancy and special M that says I want my own infi operator that I want to be written that way。

 And once I've done this which tells it this is always going to be written between the two arguments。

 I can。

![](img/085fdafdcd16946117af13981a7dbfb0_5.png)

defineefine it as a function。 Now， this is a rather simple looking function that takes another function。

 All it does is take an argument X and then a function F and then calls F with x。

 This is really not very interesting。 semantically。

 It's just taking a function and argument and calling the function with the argument。

 But by putting the argument on the left。It lets us write our square root of abs in a way that many programmers find quite easy to read and pleasant。

 and it's nothing more than a programming idiom， just say， all right。

 use our new operator with I and abs that'll return abs of I。

And then that result can go to real dot from it。 so that will get me the real number that is the absolute value of I。

 and then math dot square root。 We call this a pipeline because it almost looks like we're setting up a pipe where we start with our number I pass it through a sequence of functions combining all that to get the answer we want。

So that's kind of neat。 That's the pipeline operator。 A lot of people like it。

 It's not doing anything fancy。 It's just programming Once we've defined it with a very simple high order function。

So I've shown you function composition and pipelines。

 There are certainly more interesting things you can do with combining functions。

 So those are probably the most common。 but let's let's do some others that we just think might be useful。

 So I'm going to define a couple functions here。 I'm going to call backup functions。

 So suppose you took in a function F and G。 And what you wanted to do is run F。

 But if F wasn't the right thing， then return the result of G。 So we're combining functions。

 I want to return a new function that takes X。 And what it does is it turns out F of x the way this is written。

 returns an option。 And if that option is none， then I want to call G of x。 Otherwise， if it's sum。😊。

Let me reformat things here for you， some of some argument Y， then just return that y。

So that kind of makes sense kind of as a backup， let me show you what that looks like in terms of its type。

 because that will be nice and revealing of what's going on。And sure enough， if you look up back1。

 it says F has to be an alphaarrow beta option。 You can pass it any type you want。

 but the thing back has to be an option because we pattern match on it with none and sum。

 The second argument G has to take the same thing that F does because we might call G with the same X we called F with The result type has to not have the option on it because that's the result of our entire function just like in the other branch of the case expression。

 we return a beta。 So in general， if you pass an f as an alphaarrow beta option and G as an alphaarrow beta。

 you will get back the parentheses just aren't printed here and alphaarrow beta。

 So it's like function composition， except we don't compose them。

 we either return the result of F with the option stripped off or we return the result of G。



![](img/085fdafdcd16946117af13981a7dbfb0_7.png)

You might prefer a version that worked with exceptions instead。

 so let me just show you that I won't try it out or anything。

 so this F and G will both just be alphaarrow betas。

 but if F when called with x raises any exception using a little pattern matching here in my handle expression。

 then called G of X instead。All right， and if I show you the type of that one。

 we'll see that F no longer has to return an option。

So those are a few examples of combining functions。

That's our next closure idiom after passing data to iterators。

 functions to iterators with private data， and we'll move on to our next idiom in the next segment。

