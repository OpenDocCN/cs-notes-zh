# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p33 -33-COMP6080 - Javascript Async 🐟 Promises.zh_en -BV17RXGYuEaM_p33-

Hi， everyone。 My name is Hayden。 Today we're going to be looking at the promises part of the asynchronous aspects of Javascript。

 This lecture was prepared partially by Simon Haddad。

 So a big thank you to him wouldn't be possible without it。

 So where we are at the moment and what we know at this point is the jascript。

 unlike languages like Python and C has asynchronicity built into it by default。

 We know this because we've already explored topics like callbacks and event listeners。

 which means that。Things in jascript do just tend to be concurrent in nature and they don't block all the time。

 You will remember that from examples when we looked at set timeout。

 how you can set a timeout and then something you know the program continues。

 but it will actually call something later。 So let's just really quickly revise that because it's going to help us understand what mot promises。

 So there are two key parts of callbacks we want to chat through the first one is the idea of just the most basic linear style callbacks that exist in jascript。

 and that's these callbacks here。 So here you can see that I've imported through nodejs。

 the file system module。 This is not something I've had to install with NPm because it is built into the kind of standard NPM you install。

 So I don't have to NPm install it。 And what I'm trying to do here is I'm trying to open five different files。

 The files are called chapter 1， Chapt 2， Chapt 3，4 and5。 Those files are all just a line of text。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_1.png)

Nothing particularly exciting about any of them。The way that the read file function works within the file system library is that。

You give it a file name， you then optionally give it an encoding， which in this case is just UTF8。

 which is just basically characters like text， and then you give it a callback here。

 which is a function that takes in an error。Well， you know。

 it takes in an error piece of information data and error is the information that is populated when when there's an error associated with opening the file and data is the information that's associated。

 If the file is actually opened， it's actually what you get out of the file。

 And you can see that the way this read file function works is that I give it this callback with the error in the data。

 And our function inside of it， the callback says if error。

 then we're going console log an error else， we're going console log chapter1 and then the data And I'm doing this five times。

 Now when I run this code here， the code's called chapters callback linear。

I know my face is in the way。 Maybe I'll just leave that up here for now。

When I call this particular piece of code， you'll see that it says Cha 1 on Monday。

 I went to the park， Cha 2 on Tuesday， I went to McDonald's， Chapt 3 and Wednesday。

 then it says chapter 5， then it says chapter 4。 Now that's obviously a little bit weird initially because we've written this code chapterpt 1。

2，3，4，5。 However， the reasoning for that comes back to what we learned again previously about Corbacks。

 And that is that the way JavaScriptscript runs this code is it goes it basically goes bam， bam bam。

Bm and then bam like in those in that order。 And it executes those things very quickly。

 And what actually happens is that five separate events are triggered to open five separate files。

 and that's essentially handled by the jascript event loop。

 And eventually those five things finish and as those five things finish you get the callbacks called。

 And we can again very quickly essentially verify this。 if I just put a console log here。 I if I say。

 you know， opening chapter 1 do Txt like this。 And we run it again， you can see。

 you know that this is not linear those all these lines about opening at all of the read files are triggered。

And then the callbacks are called right at the end。

 And you see that the results are quite unpredictable。

 They're unpredictable because any time you're dealing with essentially。

 I don't want to call it multi threadreaded because jascript is single threaded。

 but you can kind of model it like multi threadreading where you have essentially a random context switch happening。

 You're gonna get different results。 And sometimes it's gonna be totally okay。

 Sometimes I'm gonna run it。 And it's gonna give me like this。 Oh nearly， Yeah。

 that one worked right， But it's not always going to work now。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_3.png)

We also learned whilst doing this that if you would like to prevent this issue。

 then you can nest things。 You can do what we call coreback nesting， where you actually put。

Once one read file is done at the end of what you deal with it。

 you then put the other read file inside of it。 So it's kind of like a ripple effect or what we might call chaining here where it's like you open one file as soon as that's done。

 you then make the next request to open another file。

 And you're pretty much just putting functions in functions and functions here。

 It's a series of nested callbacks。 We can see that one work by calling callback nested。

 And you'll see that the results for this one are substantially more predictable because it's actually executing in order。

 So now the nature of our code and how we've structured the callbacks means that。

Even though these are asynchronous calls because of how we're controlling them， we can。

 we can channel them synchronously so that they come one after another。

 And just a reminder that synchronously means in order。

 one after another asynchronously means all at the same time。 So words like concurrency。

 asynchronicity are essentially the same。And synchronicity， serialization。

 these are all on the other side， which means doing things in a particular order。

 So that's callbacks。 Now， we also very quickly picked up on。

 And this is with two space indentations。 So it could look worse that we refer to this as callback hell。

 where essentially just nesting and nesting。 And it makes code really difficult to read and also sometimes very difficult to reason with。

 So that's all the background。And this is what really brings us into promises as a topic。Put me down。

Promises is a topic because promises were essentially an evolution of callbacks that were at might have been an E S6。

 you know， sometime in the last 10 years。 and their aim like callbacks was to assist us to manage delayed completion of blocking code。

 So the reason that you know， we have these async functions。

 it's typically on things that have to do these long life processes that aren't done very quickly。

 because with things like that， you don't want them to block。

 You don't want them to stop the entire program。 The most common use cases you'll see are either file input and output。

 either opening and closing a file or reading to and from a database on disk or network input and output。

 such as requesting information from a URL in the Internet or calling an API on the network。

 So promises。As a concept compared to callbacks， they do also provide us with the same underlying problem solving environment that a callback does。

 So essentially what a callback helps you solve promises will also help you solve。 However。

 promises are both more powerful in what they can do。

 and they also have a syntax that enables us to write cleaner code。

 So what I really like to do now is give you a comparison of essentially what solving a problem with promises looks like and then solving a problem with our old callbacks。

 So if I open up our callback here。😊。

![](img/8cd194b9334d8a22b1e7df0aa29617dd_5.png)

![](img/8cd194b9334d8a22b1e7df0aa29617dd_6.png)

And then next to it， I'll open up our A。Promise version。

What you can see is that in the promise version， instead of passing a third argument to the read file。

 which is a callback， what we actually do is we take the return of the read file function call。

And we， we call members on it essentially。 So we call a dot then on it or a dot catch。 If this。

 if you want this to be a little bit quicker， I could also write it out like this。

Where we we call read file and what read file actually returns here is is what we call a promise。

This very strange word we're using that probably doesn't have a very clear meaning。

 But what a promise enables us to do is call a dot then in the case where things succeed and a dot catch in the case where things fail。

 So you compare these two one by one。 They look very similar。

 The difference appears to be mainly syntactical。 in some ways you might think it looks slightly more complicated and that's okay。

 will explain how these things differ a little bit。 But the fundamental concepts are the same。

 Every promise has a notion of succeeding and failing。

 The ways that old school jascript dot with this was like this。

 Because if you didn't have this error variable， How would you communicate to someone whether the reading of the file failed。

 There's no syntactic mechanism to deal with that。 So you need to pass some extra information in In this case。

 we can separate those two concepts out and say this is my success handler。

 and this is my error handler。 And then we can can reuse things like that now。

In terms of how promises can be structured， it's very flexible because a dot then an a dot catch just has to be called on this promise object。

 So you can do things a few ways。 you can do it， ignore the stuff below these lines。

 You can do it like this where you basically call read file， which returns you a promise。 In fact。

 I can show you that if I console log this out， And then we simply run this code on the terminal。

 which is chapters。Promises linear。 You see it。 It actually says that it's returned to promise that's pending。

 which essentially means that files 1 is a promise。

 It's a delayed piece of execution that hasn't finished yet。

And then when we call this dot then and dot catch on it on a promise where're saying。

 go and do this when it's done， go and do this if it fails。 Now， will both of these be called。 No。

 only one of them will be called， and sometimes neither of them will be called if the promise runs forever。

 for instance， we can also rewrite it like this， we can。Come down here。

 and we can put a read file like that。 And then we can put a catch like。This。

 and I'm just showing you a few different syntaxes here to help you get your head around the syntax because read file gives us that promise。

Dot then。Is called when it is successful， but dot then itself also returns a promise that dot catch works on。

 So this is kind of like a standard chaining programming pattern。

 And you've probably seen something similar to this when you've maybe been editing a string。

 like you say you know let name equals input know from the command line。

 This isn't valid jascript and then you'll say you know name equals name dot replace remove all of the forward slashes and then you know remove all of the that and remove all of the that。

 This is essentially a form of chaining where you're just returning the same thing。

 promises follow a very similar pattern， which is what allows us to do something like this。

 So how you break it up is kind of up to you。 I would just suggest starting with where you feel most comfortable。

 So I'm just gonna to move this back to where we started。

Which was also kind of where we ended in a way。 In this case。

 we could also just replace this like that。That works perfectly fine。

 but this can be somewhat clearer。 You can also， again， just to really nail it in， have it like that。

 except I ruined a line there， sorry。You can also have it like that。

 And you're probably asking questions about the indentation as well。Essential， I don't。

 I don't know if there's a hard and fast rule here。

 But things you'll either to see someone calling a dot then immediately after a promise。

 Sometimes you'll see them indenting it。 Sometimes it'll be on the line immediately following it。

 It doesn't really matter。 And this will start to make more sense once we get to chaining promises and how that works。

 So that's the linear case。 This is the case where we want these five things to execute at the same time。

 because we're not doing any nesting here。Javascript will try and open all five files at the same time。

 and they will finish in whatever order the disc。 Lets them finish in in general。

 they're more likely to finish in the relative order just because there's obviously like millisecond or I don't know。

 microseconds of difference between when they are all requested to be open。

 but it's still somewhat unpredictable。 So let's have a look at the nesting case for both callbacks and promises。

 so。These two things are equivalent now you might look at this and think this doesn't really look a lot better and that's probably quite true。

In fact， this one probably looks a little bit worse if you think about it。

 And what we're doing here is we're saying， well， let's go and try and open this file。

 This file read gives us a promise。 This promise here， we will call a dot then on。

Where we will get the data， right？ So again， it's kind of mapping。 We'll console log it。

 And then when that's done， we will call a promise on Cha 2 to open that and kind of nest it in。

 So it's the same flow。 And then you can see down here。

 we have all these kind of lingering catches because this catch here for this error is associated with this。

 So this whole block here。Is one block。Where I've got my like files for FS dot read file。

 I then get that promise。 I use the dot then for when it succeeds， I do stuff inside of it。

 which consists of calling another promise。 And then I have the dot catch。So， you know， immediately。

This is not how you use it， but hopefully that's giving you kind of a comparison about how we'd move from callbacks to promises。

 But there's a question I want to dig into before we get further。

 which is really the question of how a promise is written because you look at these things and you think。

 well。

![](img/8cd194b9334d8a22b1e7df0aa29617dd_8.png)

They do seem quite interesting， but I have no idea how they work。

 And if you've been paying attention to the code， you'll also notice up here that in this case have've actually included file system dot promises。

 That's because the normal file system library doesn't use promises。

 but they added essentially kind of like a subset to it。

 which does the same stuff but has promises like enabled for it。So that's very interesting。

 How would you write a promise， though， So if I've got a read file function。

 how would I turn that into a promise， We've actually got an example here for you， right here。

So and let me just copy a tiny bit of code。So this is the normal read file function。

All it does is it takes in file name， encoding， and then a callback。

How promises work in the really verbo way。

![](img/8cd194b9334d8a22b1e7df0aa29617dd_10.png)

Is that。

![](img/8cd194b9334d8a22b1e7df0aa29617dd_12.png)

Somethingumming is a promise if it's the return of a new promise。

 So just like how you create objects from classes， you can think of a promise as a new object so you can create a promise anytime you want。

That promise always has exactly two arguments that it takes in。

 which is essentially a resolve callback and a reject callback。

 So promises are built on top of callbacks， right， It's not like a whole totally different concept。

 it's actually just essentially a nice syntactic wrapper for us that allows us to scale it。 So this。

 my promise here is an actual promise。 And what the promise does is it executes code。

 and itll it can do all of this asynchronously within the code。

 And when it feels like it's executed code successfully， it will call the resolve callback。

And if it fails， it will call the reject callback。So when you actually trace this through the code。

You go and create a promise like this as soon as the promise is created， it starts executing。

Actually， I don't know if it starts executing immediately， you might have to call dot then on it。

 I think you have to call dot then on it。And dot then。

 what's given to dot then is actually the resolve function。So if the promise calls resolve。

That's the equivalent of calling the function that's given to dot 10。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_14.png)

So if we look at this particular piece of code and I think this one's a little bit of a doozy。

 I've written it in kind of the old school function style so that there's no JavaScript syntax。

 you're trying to get your head around。😊，But rather， just to， just to make it super clear。

 this is my function here that returns a promise。 So read file  one returns a promise。

If I comment this out， you'll see that what it returns is simply a new promise。

 So it just creates a promise and returns it。That promise it gives is that what we give the promise is a function。

 So when we create a promise， that promise takes in a function。

 and that function is the thing with two arguments， the resolve reject function。

 So when I said before that it takes a promise takes into arguments more specifically。

 it takes in a function that takes in two arguments。

 So my promise handler up here needs two arguments。

 And those arguments are going to be resolved and reject。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_16.png)

![](img/8cd194b9334d8a22b1e7df0aa29617dd_17.png)

So resolve and reject here R。the coalbacks。And I can kind of show you what I mean if I just comment out some more of this code and we we start something simple down here。

 I've got my usage of a promise。 like we said before， I go and call， read file Pro1。

Which is this function。 I give a Cha 1 and UTF 8。 I store that promise here。

 and then I call dot then and dot catch on it。 dot then deals with the success case。

 Dot catch deals with the error case。And I can show you how this works。

 because if all my promise handler does is immediately resolved， yay。😊，Then when I run my code。

 the promise is going to essentially execute immediately。 So if I。If I run file promise。

 you see it just does yaea immediately。So。New promise。Great。

 my promise is now a promise if I console log that。We can see what it is。

My promise is just a promise。Yep。Even though it did resolve immediately， though。

 in this particular case， normally it says pending。

 it says pending of something is happening and it hasn't finished yet。

 So a classic case of where something might not happen immediately as if we do a set timeout。

So if I do a set timeout and all that set timeout is going to do itself is actually a resolved。 yaea。

 and it's going to take say two seconds。 Now you'll see what the code does。

Now it says my promise is pending， and then after two seconds it actually prints out yaea。

So it's kind of still using callbacks in the sense because you can kind of see we're actually executing code and then calling a callback because the resolve is just a callback。

You know， and I could， I could do reject as well if I do reject it。Well， in this case。

 it'll print out error， but I'll show you the difference right if I print data here and that error here。

And we call resolve。Resolve will。If I call resolves。

 it will call the function that dot then is given because this is a function， right。

 It's a function that takes in data。So I get that and it says data yea， and if I call reject。

 I will get error。 I should change yaea， but you know， it says like error Sa or something。

 right error Yea。 And in fact， jascript， the actual node interpreter here is not very happy because it's like。

 hey， you threw something and it was uncoaught unhandled Pro rejection warning in this case。

 it was just a warning。You don't need to worry about that right now。

So what we're going to do instead of call that set timeout is we're actually going to。Open a file。

We've done this before。 I call file system dot read file。 I've imported it。

 and I give it a file name and encoding and a callback because remember。

 this callback is what happens when the file succeeds。

 And what do we know about that callback from the previous code， Well。

 that callback is a function that takes in an error variable and a data variable。

 And if there's an error。Then we're gonna call reject。 And if there's， if it successfully opens， it。

 we're gonna call resolve。 So you can actually see how these pieces now fit together。

 And we've actually created here a promise wrappper that deals with this as a promise。

So now when I run this。I get on promise pending。 that makes sense because at the time I tried to print it。

 nothing had happened， but let's see what happens when I print it at the end。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_19.png)

No， it's still pending here， which actually makes a lot of sense， right。

 because this line's executed。 This line's executed。

 The dot then is called at this point is when the， the promise actually starts to execute。

 I believe I'm actually not 100% sure。 I double checked that， but。If you just if you。

Like we can actually test this really quickly， I'll show you。

 we can check if the promise is executed by putting a console log here。Right。

 it says running promise。And now when I run my code， you'll see it says running promise。

 Let's see what happens when we get rid of the dot down and the dot catch。

 We get rid of those two things。 It still says running。Promise。So that promise is actually running。

 it's actually executing that code regardless of whether we call the dot then or not in this particular case。

 So that's quite interesting and the point here is like you know I don't keep this information on the top of my head。

 but it's so easy to try this out yourself you know and you shouldn't feel afraid to feel like there are barriers for these things because you can go and learn as quickly as we did just then。

So that's how a promise is created。Now。That is a little bit verebbose and a little bit hard to read The more likely way you are to see Pros written is actually like this。

 where I've got my read file Pro too， which takes in my file name and encoding and what it does is it just immediately returns and your promise and then we pass in an anonymous function with resolve and reject and then our read file also takes in an anonymous function with error and data So this is a kind of programming pattern you should be more expectatious in terms of what you see and you'll see this will work exactly the same because these two files do do exactly the same thing。

😊，Right， on Monday， I went to the park。 So that's how we can create a promise。

 You can take this concept further。 This works really well with any kind of asynchronous code。

 So essentially in in this course， you won't have a lot to do with writing promises because often you're just kind of using promises。

 however。Anytime you come across asynchronous code that relies on callbacks。

 you can turn it into a promise yourself。 So keep that in mind now。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_21.png)

What we've seen here is that。The promise constructor again accepts a callback that takes resolve and reject。

 It either fulfills or rejects， calls， resolve or reject。 The dot then executes the next action。

 That's kind of obvious。 though， some quick points， a promise can exist in a few different states。

 The first ones pending， which you saw， which is when the promise is still executing。

 and it has yet to actually resolve or reject。 Once it either resolves or reject。

 it's in what we call a settled state。And then in that settled state it's typically either fulfilled or rejected。

 they're the kind of two states that it can be in。Now， one thing that's particularly cool。😊。

Is the idea of promise chaining So what we explored before is if you want five things to happen in parallel。

 right？

![](img/8cd194b9334d8a22b1e7df0aa29617dd_23.png)

For instance， this， what's the what was the first one we did promises linear。

 This thing will open all five files in parallel because it will start the opening process for all five at the same time。

If you want to do it linearly， we kind of did what we did with callbacks where you nest them。

 but now we're getting into the real benefits of promises because you can actually do what's called promise chaining and that idea is that the dot then function takes in some kind of callback here。

But。It actually can also itself take in another promise as the return value。

 which you can then use to chain it to another thing。 So you can see here that inside files1。

When I call dot then， I process the data， and then my dot then function returns my new promise。

 which is then passed to the next dot then。 So you can essentially put all these dot dens one after another one at a time and have these things execute linearly。

 So it's a very powerful way to deal with code that you want to execute linearly。

 that is based on promises， right， So you'll see these will。 this will always execute。This whole lot。

Sorry。Interesting chapters， promises。Nested， clean。This will always execute in the right order。Now。

 again， you could， you could probably clean this up a little bit further if you want to。 I mean。

 you could you could make this code even more concise if you were trying to be。 you could say。

 you know， like。Print and read file or something where it takes in。Oh， you know。

My point is you could generalize this function here， right。

 because when you look at what this function does， because this is just a function you're passing into the dot。

 then you could call this like handler。And just literally paste that there。

 And then instead of just taking in data。Well， actually it has to take in data。

 I won't get into that， but you can make this more complicated if you want pretty easily and the code can still retain quite a lot of its conciseness。

I do actually think we might add Li here and show you how you could clean this up a little bit because you might be thinking。

 oh， I'm noticing that this code is just data。 And then the previous chapter in the next chapter。

 So what I'm gonna do is I'm gonna say data。 and then I'll put index here。 And you think。

 oh I'm very smart。Great， I'll go do this。 and then I'll put index here。

 and then I'll put index plus one here because， you know， if it's chapter 1， then it's chapter 2。

 right， And you think cool。 now I've got my nice little sneaky function。

 So what I'll do is instead of instead of passing this in here， I'll pass the handle。😊。

Now here's the problem。 Dot then always expects a function。 Well I don't know if it's one parameter。

 but it gives you all the information you want in a single parameter。Which is data。

 So if I give handler here， the problem is that it won't actually succeed because index is not passed in。

 And you might think， well， how do I pass an index， Why I can't really say data index because。

That doesn't make a lot of sense， though you could say data handle a data index because around everything inside dot then needs to be a function。

 And a really common mistake you see students make all the time is that they pass the return of a function call somewhere that's expecting a function as opposed to a function itself。

 So this doesn't work。 It doesn't even make sense because data is not defined。

 But if you say the dot then takes in a function。That takes data and simply calls handler with data and index。

 except in this case index might be1。Now we can actually generalize our code very， very quickly。

Though obviously in this case， it's a little bit weird because in the fifth case here you still have to write it manually。

 but immediately you can see that that that will have cleaned up our code quite a bit。

 assuming that there's not a grave mistake here。Is this clean code debatable。

 but the point is that this kind of consolidation becomes a lot harder with callbacks because callbacks inherently are recursive in a sense。

Right， whereas this， you can， you can kind of linearise。

 You could wrap this in a full loop if you really wanted to。 So that's just sum keep in mind。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_25.png)

Now。Da's promise chaining。 It's about executing asynchronous code synchronously one after another。

 There's some examples that Simon put together where it's like you can just， you know。

 it's chaining is when you want to say all these steps have to happen in a certain order。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_27.png)

The good thing about chaining 2 is you only need one dot catch at the end。

 so you can essentially have a catch all that if at any point in this promise chain an error is thrown。

 it immediately skips all the remaining dot thens and it goes straight to the couch。

Is that a good thing， Well， if you want different catches for different scenarios。

 then maybe it's not appropriate， but again， that kind of depends on what you're doing。

 but it still creates very clean syntax。

![](img/8cd194b9334d8a22b1e7df0aa29617dd_29.png)

Another thing you can do with promises is called Pro branching。

It's not really like a technique as much as it's just a concept to understand that what is happening here。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_31.png)

Is what you would call promise。Branching。Where we're trying to branch off and do five things at the same time。

 It's kind of like you know， it is asynchronous execution。

 whereasas what we're doing here is promise chaining。

 and you can be smart if you want to if you have this long series of promises。

 to actually do some things asynchronously in some things not asynchronously。

 So really good example is let's imagine that you've got you've got all these books that exist。

 So I've got say five books and each book has five chapters。 Now。

 obviously when you print out the contents of a book like we did here。

 you want those five chapters to be printed in order。

 But maybe you don't actually care what order the books are printed in。

 right because books don't have a sense of order between them， you know， depending on the book。

 right， don't think of it like a book series， but more just a series of random books。

 So what you could actually do is you could actually trigger the opening of all five books。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_33.png)

Asynchronously， I promise branching， but each of those books once you once all those five things go off asynchronously。

 you can make sure that the opening of individual chapters happen synchronously So all you're really trying to take away here is the idea that if you put promises one after another like this。

 they're all going to start executing at the same time and branching out but if you chain them together with a dot then then they're going to happen sequentially within that particular order。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_35.png)

There's some extra details here about error handling with promises。 This isn't super critical。

 but worth paying attention to。You can kind of see that if in if you have a dot catch and that dot catch itself throws another error because throw is valid syntax in Javascript。

 If you think about exceptions， it will actually fall to the next catch as well。

 Most of what you deal with in the course doesn't。Really need super complex error handling。

 though there is definitely a lot to this。 And it's kind of true for everything in this lecture。

 to be honest， is that there's quite a lot of depth to promises。

 There's quite a lot that you can go and learn。 This is just touching the surface。

 And most of the information you， you might want is really just sitting on。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_37.png)

A bunch of websites such as the MDN Javascript， right and MDM for promises for Javascript。

 And it will go through things in extremely thorough detail in a very technical detail。

 It'll show you all the different methods that exist。 Some examples。

 I find that documents like this are much better。Once you really have a more tactile understanding of things because otherwise it seems very theoretical。

 But you will also note that all browsers pretty much support this as well。

 Internet Explorer has since been defunct And in most， in most scenarios， too。

 if browsers didn't support this because they haven't always supported it。

 there's a lot of translation that happens because most promises can just be reduced in some way to a series of callback。

 So you need to think of promises as a as a method and approach。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_39.png)

Through syntax more than a technology， they are， they are a method of they are a syntactic method of dealing with the asynchronous callback hell nature of Javascript。

 Now， the last thing we want to touch on on this basics of promises because you'll be dealing a lot with these throughout other parts of the course is promise orchestration。

 What we've seen so far is often about。嗯。Just dealing with a single promise at a time。

 And Or or what I mean by that is that either we're trying to run everything sequentially or we're trying to run things in a。

Just do them all and who cares when they're done。There's a whole series of static methods on the Pro object dot all dot all settle。

anning。 race。reject。resolve。 And I want to give you an example of the most popular one almost popular makes it sound like it's a choice。

 the most commonly used one which is Pro do all。Promised not all is a function on the promised object that returns a promise that resolves。

 If all the promises pass to it resolve。 So it is a function that takes in a list of promises。

 And you might be thinking， well， what's the use of that， Well。

 let's modify one of our previous examples， One of our branching examples， which was our。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_41.png)

Proises linearar。 When I say the linear， I'm mean。These are just written out linear。

 even though this is ourard here， this is like。Promise branching。And。And by the way。

 the files might change。 if you see the file names changed down the line， obviously。

 the video has been recorded。 so just go look for the different files。

But here we've got our promise branching and you think that's all well and good we want to open all five files in any particular order。

 maybe you don't care about what order the chapters are opened with。So when I run my chapters。

 promises。Lar。You know， I get chapter 1， three， four， two， and five。If I said to you。

 I want you to print。All chapters opened once all the files have been opened。

 that's really hard to do because you might be thinking you're like， oh， well， how do I do that well。

If I didn't know about some of the promise orchestration， I'd do something terrible。

 Like I'd have like a like a let counter equals 0。 And I would literally say， well， after every。

 you know。After every time we successfully open a file， I' going to increase the counter by one。

Now the problem is you can't at the bottom say if counter is equal to5。Then console log。

 all files open because this if statement is going to get executed nearly immediately long before any of the files are returns。

 So then you come up with all these stupid ideas， you know， like set interval。

 So we'll check after maybe a second if all the files are opened。But it's like， what's。

 what's the point of even doing this， And it doesn't even make sense。 What if your files take longer。

You know。And now it's I set interval， so I meant set time out。That that's not going to help us。

 right， That's just not going to help us All files opened。 So what we're going to do instead。

Is we are going to use Prom all。Promise do all takes in promises。

 So when I call Pro do all and I give it files1， files2。Fles 3， files 4。And files 5。

And then I capture that。 I say all promises， right？If I then console log what all promises is。

 you will see that at the time of console logging it， it is also a promise。Pending， o， sorry。

 Let me get rid of this counter。It is also promised pending because it executes before all of them finish。

 as we expect， however， I can call。All promises dot then。And， obviously， it doesn't。

But does take some data， but let's just assume it doesn't need to take anything。

 Now I can say all files open。 So what promises do all will resolve， you know。

 it is a function that will resolve once all the underlying promises themselves have resolved。

 And that's how we get this nice little all files open down here。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_43.png)

There are other methods of promise orchestration that you can go and read about Dot n is an interesting one。

 It kind of it's when any of the promises resolve。 So you'll see if I do that one。

 it will essentially console log immediately after the first promise resolves。

 I put that in the wrong spot。 Sorry I wasn't looking。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_45.png)

Dot any。

![](img/8cd194b9334d8a22b1e7df0aa29617dd_47.png)

Like that， promise that any is enough。Have I done wrong？I don't know。Very strange。

 That's not super important。 but there's gonna be something small done。

 But you can see there that that will they will return the first promise You see dot race returns of promise。

 which resolves as soon as one of the promise passed to it resolve So dot any as if my bad dot any as if at least one of the promises it passed two resolves dot races as soon as one of the promises passed to it resolves and dot all settled make sure that they all settled at least because you can see the nuances here that promise dot all only works if they all succeed because remember how we said settled can either be rejected or resolved。

 So promise dot all as if they're all resolved。Promised dot settle all settled as if they're all resolved or rejected。

 It can be either of them。嗯。And you might be looking at these bottom two here。

 which don't take in a list， which is promise， dot reject or promise dot resolve。

 These are very strange functions that I don't think I'm going go into because。

It's honestly mainly like kind of useful with， with Typescript， which we don't really cover much。

 but essentially promised dot resolve takes an object and immediately returns a resolved promise。

 And what that kind of means in reality is if I have a。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_49.png)

If I say like Kant's name equals Hayden。Name is a string。

 If I say constant name promise equals promise dot resolve Hayden。

What name promise becomes iss it's actually the equivalent I'm pretty sure of saying name promise is new promise that takes in resolve and reject and the first thing it's going to do is just resolve Hayden。

So it's essentially a promise that resolves immediately and you might be thinking like what's the point of that？

Because if I already know what it is， then I could just。Just I don't need a promise。 And and again。

 most of the instances I've seen this happen with are when you've written a system that expects promises。

 but sometimes you give it something that doesn't need to be asynchronous。

 So it doesn't need to block， but you still kind of need to wrap it into this promise infrastructure。

 if you will。But yeah， that that's essentially， that's essentially some of the promise orchestration that you'll see。

 A really common use case of the Pro dot all is pretty much just weight like it's pretty much a form of saying I want a branch and then I want to wait。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_51.png)

You know， so I want to go and do if we go back to the previous slide like this。You say， okay。

 I want to start preparing dinner， but I don't want to serve it， right。

 I don't actually give people food well。As you can see a light barbecue cook steak start music。

 watch sunset and reflect， you could imagine like you don't want to clean up until all of this is done。

So， you know， you could put like the light barbecue， the start music。

 the watch sunset in a kind of promise dot all so that you wait till all of those asynchronous activities are finished and then you can go on to the next thing。

You can usually draw these things out。So that's pretty much it on promises。

 Do have a look at the code examples if they're meant to be very simple so that you can kind of relate it to callbacks and a few other things。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_53.png)

Most of how you're going to come across promises is often going to be network requests which you'll learn about in later lectures after you learn a bit more about AJs but don't feel scared of promises because they are a mile deep you will always be learning things about them there's a lot to learn about them and if you just feel like you can use them basically and keep reading up on things as you go bit by bit then you're going to be fine so hopefully that helps。



![](img/8cd194b9334d8a22b1e7df0aa29617dd_55.png)

![](img/8cd194b9334d8a22b1e7df0aa29617dd_56.png)

![](img/8cd194b9334d8a22b1e7df0aa29617dd_57.png)

![](img/8cd194b9334d8a22b1e7df0aa29617dd_58.png)