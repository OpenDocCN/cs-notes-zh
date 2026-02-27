# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p34 -34-COMP6080 - Javascript Async 🐟 Await _ Async.zh_en -BV17RXGYuEaM_p34-

Hi everyone， my name is Hayden today we're going to be talking about the await or asynch weight syntax in the context of asynchronous JavaScript this is an extension or an expansion on the topic promises and a big credit to Simon Hadad for being a key part in preparing this lecture。

 particularly some of the slides and the thoughts on it。😊，If you've looked at the promises lecture。

 it might be a bit early for you at this time。 but if you have been using promises for a while。

 you start to very quickly understand that they feel somewhat。

Frustrating in situations where you're definitely using things synchronously so。

Asynchronous code works really well with promises because you can kind of branch off。

 though synchronous code can start to feel a little bit clumsy。

 And the example that we saw in the previous lecture was。



![](img/6c35e162f79c1ddc68e0999a5c2b2b20_1.png)

This example with promises， and you look at this and you think， well， it's not super clumsy。

 but it's a lot of doc dens and function wrappings compared to say if you were doing something in Python because。

 you know， if you were doing something in Python， you'd be able to pretty easily just kind of be like。

 you know， print。呃。Open。Something。You know， dot read。 you know。

 you can kind of do that pretty easily。 You could just kind of write these things one after another。

 This is true for many languages。 So promises certainly can let us down when we're trying to do things synchronously。

 And to be honest， a lot of the time for simple applications。

 you will be using promises in a synchronous fashion because you're not trying to do anything concure or asynchronous or tricky。

 you're just trying to handle asynchronous actions or blocking actions synchronously。

 So in Es 2017 and the 2017 version of Emascript， there was a new syntax created called the asyn await syntax。

 which helped simplify the use of using promises or consuming promises。

 particularly in the context where you're consuming them synchronously and a really simple code example to compare here is that。



![](img/6c35e162f79c1ddc68e0999a5c2b2b20_3.png)

![](img/6c35e162f79c1ddc68e0999a5c2b2b20_4.png)

On the left we have the use of promises， which is you know we call read file。

 it returns as a promise we call dot then to consoles log the chapter out or we call dot couch to consoles log the error out。

 However， if we use the await async syntax or async await syntax。

 you'll see a couple of key differences， the main one is that the body of the code looks a little bit more like what you might be used to in other languages。

 which is that like Java again or Python， you simply call read file。Which gives you the data。

So instead of deferring it and catching， you're actually returning it。

 So a read file in this case is not giving you is not returning a promise。

 It's actually returning what the promise would resolve to and then you print it out and then you use the trycatch to deal with this through the kind of exception pattern or syntax rather than this kind of dot den and dot catch So this probably looks quite similar to what you might have expected this approach to be before you learned about callbacks and promises The two things to note though are that the promise function you call the function that returns a promise has to be prefixed with the await syntax。

 What the await syntax does is you got to think about it like it's essentially something that converts a promise into a synchronous value in the sense that it takes that promise it sits there。

 it waits and it resolves it and then stores it into the return value。

 So it's really the Da asynchronicity of something。That kind of makes sense。

 What's a little bit weirder is if you try and use this syntax， I'll show you what it does。



![](img/6c35e162f79c1ddc68e0999a5c2b2b20_6.png)

If you try and use this pretty simple syntax。Here， I'll just replace this for a second。

Just like this， well actually I'll show you if you do it like this first。

So this is kind of just using the Python solve， I'll say。嗯。If you do it like this。

 it says chapter 1 a promise。 That makes sense because if file system read file returns a promise。

 then if you try and print it instead of you know dot bending it， you're gonna get promise pending。

 However， if you the await syntax。 What you will find is that it complains and you might see this error sometimes a weight is only valid in an async function。

 Now， how you get around this is that your function， the function。

 the very next level above it needs to be prefixed with async。 The keyword。 What async does。

 which is a little bit subtle is async actually turns your entire。Function into a promise。

Wwhichhich kind of gets a little bit tricky and confusing so read files here previously was just a function that was called and processed immediately。

 whereas now it's an actual promise for all intents and purposes that's not going to affect you very much and it only kind of is a bit weird when you're doing the very first function call in your program because you know typically as this kind of chains downwards it becomes less of a problem。

But。Oops see， but you will see here。That this now works。 It now says， you know。

 on Monday I went to the park and。

![](img/6c35e162f79c1ddc68e0999a5c2b2b20_8.png)

That's all well。 and good。The syntax there immediately doesn't look much cleaner where the syntax starts to become a bit more cleaner as when you're doing many of these things one after another。

 or more specifically when you have you know synchronous code that you want to execute that everything after it really relies on and what we saw before was when we did the promise chaining back in the promises lecture。

 we you know we call dot then and then dot then and then dot then like this。

 whereas with the await async syntax， we can simply call a weight and then print it out。



![](img/6c35e162f79c1ddc68e0999a5c2b2b20_10.png)

So instead of this kind of confusing chaining， we can actually keep it even simpler。



![](img/6c35e162f79c1ddc68e0999a5c2b2b20_12.png)

Actually， just to， just to bring this on parody， I might， I might add the。The chapter because。

 you know， to be fair， the other one did have。The chapter to it。Like that， right。

 And now when we actually run this， it will do what we expect。

 but the syntax has been a little bit cleaner。And in fact。

 obviously you know you could make this even simpler if you well I wouldn't call it simpler。

 you could make this even more concise just by taking this and putting it directly inside the console lock。

😊，That works totally fine。 and these things are equivalent。

 So like using the await syntax here is equivalent to promise chaining So it's super super convenient。

 super great， particularly when you don't want to do things concurrently specifically again it's for situations where you are calling a promise but you are very happy for the rest of the code following to just stop and wait until it's done because that's actually what happens because the await it blocks like it does in you know a C or a Python it literally blocks and sits there and waits and。

😊，Once it's done， it will then keep executing and once it's done， it will then keep executing。

 So that' that's the kind of practical basics of asynle weight syntax。 But if we kind ofops see。



![](img/6c35e162f79c1ddc68e0999a5c2b2b20_14.png)

If if we think about the theory of this a little bit more。What is kind of like。

 what are the downsides and the positives of this， Well， the positives is all readability。

 mainly right you can go into this list quite extensively。

 but the main positives is usability and readability。

The downsides of the asy weight syntax is probably two main things。

 One is that it doesn't totally eradicate the need to understand promises。

 It's not like a total evolution away from promises because you still need to understand promises to be able to write promises。

 for instance， and then secondly， await async。Does not really hold up very well when you're trying to do things concurrently。



![](img/6c35e162f79c1ddc68e0999a5c2b2b20_16.png)

And what I mean by that is that while this program there's an equivalent。

 whilst the Pro chaining program has an equivalent with the asyca weight syntax。

 what it does not have is it does not have an equivalent for the branching code。



![](img/6c35e162f79c1ddc68e0999a5c2b2b20_18.png)

So here we have our Pro branching。It doesn't have an equivalent for that because the very nature of asyer weight is that when you call it。

 it totally blocks。So that's just something to keep in mind。

 So usually you can pretty much use it everywhere unless you want to start doing promise branching or unless you need to write your own promises。

 which is where you need to think about things a little bit more。 But besides that， it's actually。

 it's actually quite literally that simple。 There's honestly not a lot else to it。



![](img/6c35e162f79c1ddc68e0999a5c2b2b20_20.png)

啊。Some last kind of quick notes on this。Would be that。Async， as I said， always returns a promise I。



![](img/6c35e162f79c1ddc68e0999a5c2b2b20_22.png)

To think about that syntactically， how you can imagine that if I go and grab the the really simple lecture code here。



![](img/6c35e162f79c1ddc68e0999a5c2b2b20_24.png)

![](img/6c35e162f79c1ddc68e0999a5c2b2b20_25.png)

Is that when you have code like this， what is really happening here is that you're saying constant read files equals something return you promise。

Resolve， reject。And then， you know， all of this kind of code。 Now。

 I don't want to equate this literally because。There's actually some trickier stuff that goes on here in terms of。

 you know， obviously a weight doesn't make sense here。

 And the jascript interpreter is very good at figuring out how to restructure this in a sense。

 But the point is that a await just has to exist within a promise itself。 So and you might think。

 what's the point of the asyncs into student jascript just see a await and immediately make my function async。

 I don't have good answers for that。 Often answers to questions like that have a lot to do with language design and compiler design。

 But you will see， as I did before again， that read files is a promise。

 So I need to dot then if I want the result of that。 There is no result of that， though。

 But if I was to return something from this。 I was to return 7， I would still need to。Dot Bent。

So that's just something to keep in mind here is that your async functions themselves are promises and you need to handle them like that。

 And again， yes， you could handle them with a weight。

 but what that wraps itself in also needs to be async。

 What this essentially means is that if you do have programs that use the async or weight syntax。

At the very， very top of your program， you will still need to actually call dot then somewhere probably like we're doing here。

 but everything inside of that doesn't need to be。 Hopefully that's been a very simple overview of weight asnc asy weight。

 I know I say them the weird way around check it out。

 use it where you can sometimes we won't allow you to use it in the course， but。



![](img/6c35e162f79c1ddc68e0999a5c2b2b20_27.png)

Where you can use it， it's gonna help you save a lot of time and make and make things a lot clearer。

 So thanks very much。😊。

![](img/6c35e162f79c1ddc68e0999a5c2b2b20_29.png)