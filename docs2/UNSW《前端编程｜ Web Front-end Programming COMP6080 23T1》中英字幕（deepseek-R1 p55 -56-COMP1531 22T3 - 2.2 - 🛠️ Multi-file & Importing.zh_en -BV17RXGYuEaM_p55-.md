# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p55 -56-COMP1531 22T3 - 2.2 - 🛠️ Multi-file & Importing.zh_en -BV17RXGYuEaM_p55-

We're gonna to get stuck into the sixth lecture of the course， which is another lecture on。

Software development coding， right， learning how to code， code in Javascript， right？

 And it's called multi file and importing。 So essentially， how do we deal with。

How do we deal with code when there's many files and they're all trying to use each other Now you're familiar with the idea of multi filele projects in C because you would have I assume unless they've taken that out。

 I don't think have you know you write a C file here， you write a C file here。

 you Gcc DCC compile them together and they kind of work and you put a dot H file in the middle。

 things are a little bit different with most other programming languages。

 particularly non of C derivative languages。 There's a bit more of a structure at a code source code level about how these things combine rather than a compilation instruction we're just gonna be talking about that。

 And the reason it's important is because frankly， the number of times in your life。

 you probably write software that exists in one file。 it's less than 50% of the time。

 probably for some of you， it'll be a lot for most of you it will be not very much。

 So it just really matters。 And we're we're not just going talk about how to import libraries because we kind of touched on that a little bit in the last lecture where we talk about MPm but we're also going talk about how we import our own files。

 how we write code。And file A and import it into file B。So。😊，Firstly， a quick comparison in C。😊。

We have these built in libraries like Stud H。In Javascript， we also have similar libraries。

 What I might have given you the impression of in the NP PMM lecture is that everything has to be downloaded。

 but nodede JS has a bunch of stuff that doesn't need to be downloaded。

 And there's a list on the Internet。 There's actually things are 27。 How many is it。 I don't know。



![](img/85988d628516a6d841ace419e002d1b9_1.png)

1，2，3，5，6，7，8，9，10。57 that 28。 Oh no so close。 I du'tno。 Doesn't really matter。 That was stupid。

 So there are these， like， kind of 20。To 30 libraries that are actually built into node Js。

 When you install node Js， they just get installed with it。 So they're really easy。

 probably the most common ones that I use， honestly， like 99% of what I use from here。

 It's always the same。 It's always F S or path。 F S is about opening files。

 Pa is about getting file Pa These are really， really useful in many， many instances。

 So these are built in。 just like studio dot H is built in。

 You don't really have C typically without studio dot H。 It's just kind of there。

 So we can import them in our code， we just do it a bit differently in C we has include in jascript。

 we say import Fs from Fs。 Now， these differences are quite interesting because。



![](img/85988d628516a6d841ace419e002d1b9_3.png)

In C。When you hash include So dot H， you kind of just include the library magically。

 and then you can use keywords in your code like printf that just work and they just work because what's actually happening at a compilation level。

 if you were taught this or you read about it。Is that the studio library is literally during you know pre processing。

 just getting copy and pasted in， so therefore the printer function exists because it was copy and pasted into that file。

😡，Javascript and most other programming languages are a little bit different。

 They're a little bit more explicit。 Theyre a little bit more clear in the sense that what we're saying here is I would like to import。

 I would like to get an object called path。From this library。

 So this is the object that I use in my code。 And this is the library that I'm， you know。

Pulling from， and they just happen to be the same in this case。

 They don't always have to be the same in the last lecture you would have seen that it was like import is valid from date functions where date functions was。

 you know the library and is valid was the function or object。

 and you can see the way we use them a slightly different too， because in Javascript。

 when we want to use something from the path library， we often might have to go path dot resolve。

 So resolve is like the printf here。 It's the function that comes from the library。

 except we are representing the library by this path。Variable， if you want to think of it like that。

 So we we grab the library called Pa。 We wrap it up into a variable called Pa。

 and then we want to when when we want to use something from that library。

 we go path dot resolve in this case。 Now what this code actually does is it essentially just says dot resolve kind of just gives you the path on the computer of whatever path you give here。

 and I'll show you what I mean。 just so this is a little less。

 notice I won't have to NPpm install anything here。

 So I'm just gonna create a new file in this like a random test repository I have here。

 I'll call it like P dot js。

![](img/85988d628516a6d841ace419e002d1b9_5.png)

And when I go node P dotjs。It prints that out。 So basically what it what it does here is it it says take this path and turn it into the the big path。

 the whole thing。 And， you know， you can kind of， you can kind of be cheeky with this。

 You can actually say like oh I actually want to go back a folder into M1。

 and it will kind of like imagine it's a comma。Is that a comma。 looks like a comma。

 It'll kind of like C， and then go into that。 And then it'll get you the full path。 So it's a very。

 very powerful little function you can call。 But that's what it does。 It。

 It's like it like CDD's there and then gives you the whole path。

 It's kind of like it's kind of like C and PW combined。 if that makes sense。

 Like it's like C into this folder， then PWD it。

![](img/85988d628516a6d841ace419e002d1b9_7.png)

Its a way to think about it。But there's tons and tons of stuff in that library。

 The point is that how we import them and interact with them is a bit different。

When we want to import our own files， we can follow relatively simple principles as well。 Now。

 for this， I'm just gonna navigate back into。

![](img/85988d628516a6d841ace419e002d1b9_9.png)

![](img/85988d628516a6d841ace419e002d1b9_10.png)

Our kind of folder with all our source code。

![](img/85988d628516a6d841ace419e002d1b9_12.png)

And I'm going to open up a particular file here。Which is。



![](img/85988d628516a6d841ace419e002d1b9_14.png)

![](img/85988d628516a6d841ace419e002d1b9_15.png)

2。2 split before。 And you'll see that what we have is as a function written here called many string。

 And what many string does is it takes in a number of times to repeat something。

And then it takes in a string that's going to get repeated。And it repeats that many times。

 So you can see at the bottom on line9 here。 we actually call this function with like  nine。

 we say actually I'd like to nine times repeat hello。

 So I actually console log the many string call by giving it5 and then hello with a space which will print you know hello hello hello hello。

 hello hello， hello， hello hello，😊，And the way the function works is it creates an empty string。

It loops through for the number of repeats。 each repeat it like， kind of。Itends。

 copy and paste a string to the end， And then it returns that string we created at the start。

So I could run it。Like this。 Ho， hello， hello， hello。Easy enough。



![](img/85988d628516a6d841ace419e002d1b9_17.png)

But here's the interesting thing。 What happens if we actually want to use that I gotta stop in this thing。

 What happens if we want to use that in another file。

RightWhat happens if I actually don't just want to。

 if I want my function that I've made to kind of exist over here， not do a console log。

 but I want to be able to maybe use it in a few of my other pieces of code by like importing it by using it。

 So we do in that case is instead of console logging something， you know， we get rid of that。

 but we actually include this line here with two keywords export default。😡。



![](img/85988d628516a6d841ace419e002d1b9_19.png)

And then we give it what we're actually exporting。 Now， exporting and importing makes sense。

 This file has code that I want to use in other files。 So I export that code。 I'm like。

 ready to send it somewhere else。嗯。The default we'll come back to in a bit。But for now。

 it's like we're gonna export many strings。 It's really simple。 Now， how we use that。

On the other side is we go to another。File。The control shift or shift all8。

We go to another file here， which is called。Split after main。 we simply import it like this。

 So we say import many string from this file。 Now， obviously， this file is in the same folder here。

 I don't think you need the Js。 Sorry， that's probably a typo。 And then you just console log it。

 And now what happens is that when I run node， source s 2。2 split after main。

 which is the bottom file here。

![](img/85988d628516a6d841ace419e002d1b9_21.png)

Or maybe you do need the JS， sorry。There's little bit。 Everything's a bit weird， sometimes。

There's there's a downside of jascript that like jascripts a really exceptional language to have this course in。

 but there are some downsides， which I'll chat to at a later time。 Matthew says。

 what if the source file was in a different directory， It's a great question。

 You just import it differently。 So like， let's imagine just for argument's sake， I'm going move 2。

2 split。I'm going to move 2。2。Split。After lib。Opa folder。 So now it's like。Oh， shit。Now。

 instead of it being in source， it's in this folder， right？ So like 2。2 split off main。

 which is this one。 that's in the source folder， whereas the other module here is hiding in the folder above it。

 Well， I would just， if I ran this now， it wouldn't work， right， it would， it would fail。Like this。

 So I would just need to change the import。 I didn't need to say， you know。

 go to the previous folder like that。And now it will work， right。So some questions。

 sometimes there are things that I don't realise that we may maybe we need to talk about from another course if they weren't taught。

 but generally dot slash is referring to like the current directory and dot dot slash refers to the previous directory like upper level。

 right。So when I say C D dot s， it's like saying C D to my current directory。

 And if I say C D dot dot slash， it's like the previous directory， which I'm sure most of you know。

 Nuurran says if you push this code to Gitlab， you'd have to upload the file you're importing from as well。

 right。😊，Yeah， exactly， like you'd need to upload both of these to Gitlab， both of these files。

 you couldn't just upload one otherwise it wouldn't work。

But the point is that we have exported it from one file and imported it into another。You know。

 pretty， pretty simple stuff。They're the two lines， like， obviously， they kinda match， right。

 We export many string。 We import many string like this。

Where things get more interesting is if we want to start importing multiple things。

 What happens if we have many functions that we're writing that we want to import， right。

 And if we want to do that， we need to take a slightly different approach。We could。Right。If you take。

You get rid of this if you take。This example， let's say you have two functions。

 many string and ad brackets。 If you want to export them both。What might you do， You could do this。

You， or， I mean， you could， you could try and do something funky where you。

 you export default like an object that contains multiple things。 You could try and do that。

 But there's some problems with that。 The way you actually do it is if you wantan to export multiple things。

 not just one， you drop the default。And you just kind of return it as if it was an object。

So in this case here， instead of saying export default one thing， I'm now saying export braces。

 many things。 And I've already gotten the question right， what does the default do。

 The default signals to ja that you're going to export。Wan thing。

This file is going to export a single thing。 That's not the exact answer， but like let's start there。

 just as a starting point， whereasas if you just say export and then you give some braces。

 it's like your way of saying， actually， we'd like to export a few things。Right。So。We can。

Try and do something like this。 And this is how we export multiple stuff。 So， yeah。

 bear with me if you're a little bit confused。 we'll go through some examples together。

 But why this is interesting is because now。

![](img/85988d628516a6d841ace419e002d1b9_23.png)

Right， now I've kind of exported two things， and I can actually use those two things。

So you'll see here in this file，2。2 multi export main P2。 Sorry for the stupid names。

 What I'm actually doing here， And I'm gonna go move this on。

 I'll move this on let me make it full screen。 Perhaps I'll just word， let's go full screen。

 You'll see that what I'm actually doing is I' am importing from this file。 export multilib P2。

 This file。

![](img/85988d628516a6d841ace419e002d1b9_25.png)

I am importing brackets and many string。 Actually， there is a typo there， too。

 How did that one not get picked up on last term。2。2 multi export Lib P2。There is a tight yeah。

 So like what we would have to do here is actually import ad brackets。 They need to be the same name。

 by the way。 That's why that wouldn't work。 And you can see that I can import a brackets and import many string from this module。

 and it will actually function correctly， right， I can now go and say， you know， node source 2。

2 multi export。

![](img/85988d628516a6d841ace419e002d1b9_27.png)

Main P2 like that。 And it will do what I want。 It will。



![](img/85988d628516a6d841ace419e002d1b9_29.png)

Take it will make a variable B， which will add brackets to Hallo。

 and then it will take it will create a variable many， which is the many string of B。

 which is hello with the brackets。 And then I can console log that。

 So now I've imported two different functions and used them in my file here。So some questions。嗯。

So if I take a step back， Goats asked a question， many string import is basically importing a function of the file。

 You can't import a file in Javascript。 That's the easiest way to think about it。

 You can import things from a file that were exported from another file。

 Many of you have had some experience with Python。It's not like Python。

 where you can just kind of import anything。 You can only import what is exported as it as a general rule。

 right。Cerril says， so could we instead do export。Many string。Yes， we could。

 We could here do a few things。 We could export many string like this。

 and then we could also export ad brackets。Like this。Right。



![](img/85988d628516a6d841ace419e002d1b9_31.png)

There。

![](img/85988d628516a6d841ace419e002d1b9_33.png)

That works as well。So a few more questions， could you export default twice？No。

 you'll see we'll get an error。 So if I go and try and run the previous code we were running and I have two export defaults。



![](img/85988d628516a6d841ace419e002d1b9_35.png)

We will get an error， says our identified default has already been declared。

 so you can't export default twice。

![](img/85988d628516a6d841ace419e002d1b9_37.png)

um。Bill says if you put a function in export， it's equivalent to making it static and C，I。

 I don't know if I want to make that comparison。 I I， I can see what you're saying。

 and like probably might be a short answer， but I I feel like that's just。Sometimestime。

 sometimes I get worried about saying two things are alike，cause when they're very unallike。

 but maybe they feel similar。 So maybe。

![](img/85988d628516a6d841ace419e002d1b9_39.png)

Okay， now let's get into the default thing，cause this is the most confusing part of it。

There are two ways to export。 The first one is to get a thing， to go export， default the thing。

The second one is when you want to export multiple things where you go export。Multiple things。Right。

When you import multiple things， you import them with the braces。

 When you don't import multiple things like a default export， you just import the thing。

 Like these are two patterns， two different ways of doing it。 And it's always the same on each side。

You know， pretty simple。 But there's an interesting question， which is like， why。You just read ahead。

 why would you default export now。There's generally not a good reason to actually， as a general rule。

 it's a good idea to try and export things as what we call named exports。

 So if it's not a default export， it's a named export。

 the benefits of a named export are that you typically don't pigeonhole your code to only be able to export one thing。

😡，You know，cause like， if you imagine you move from a default export to a named export。

 you have to go and change how everyone consumes your code。 you know。

 so it's like a little less scalable， if you will。 The other benefit of a named export is that。

You actually have to use the same syntax。 So， for instance。

 in this case here where I exported ad brackets。

![](img/85988d628516a6d841ace419e002d1b9_41.png)

See watch， watch， watch here if I change this to a brackets too， like this， right。



![](img/85988d628516a6d841ace419e002d1b9_43.png)

What will happen is that my courage simply won't work。 It's like。Add brackets to。

 No one exported that， whereas with default exports， it's a little bit more lenient。

 If I go back to like an earlier example。

![](img/85988d628516a6d841ace419e002d1b9_45.png)

Here。Os， no， sorry。啊。Blit after Lib。 Oh， I move the file。 Sorry， if I go back here。

 this one's actually really interesting because the way the language is structured is because you've said。

 like， export a thing when you're importing it， it doesn't really matter what it's called because there's just the thing there。

 So therefore， when you import it， you can actually call it anything you want， like a lady beetle。



![](img/85988d628516a6d841ace419e002d1b9_47.png)

You know， you can call it that。 Like watch this split after domain。 This code just works。Works fine。

 And I think this is like， this can be a good and a bad thing about default exportscause like now no one knows what lady Beaetle is。

 whereas previously someone actually had to。

![](img/85988d628516a6d841ace419e002d1b9_49.png)

To change that。 Now， there's already a question， what's the benefit of renaming an imported thing。

 That's a good question。 Well， maybe you already have something called that thing。

 Like maybe in this file here， you are also going to have a function called many string that you define for some other reason。

 sorry。Right， you'll have something like this。 And it's just gonna return， you know。That will sum me。

So how do you get around that， maybe you don't wantanna rename your function。

 You could actually just rename this and call it something like。You know， split live mini string。

 You know that you give it like a slightly oops， change the wrong one。

You can give it like a slightly more interesting name like that。

 And that's how you can like avoid name conflicts。 Aing name conflicts happen。

 Sometimes Sometimes you do it to make it clearer。 Sometimes libraries or functions might have really boring names。

 like with date functions， how it says is valid。 So if we jump way back to the date functions one。

 like is valid here。 Sometimes you might just look at that and think oh， that's a horrible name。 so。

You wan to rename it。 Now， I said that you can't rename named exports before I think。

 but that's not quite true。 The point is that it has to be imported by name。

 but you can do what we call aliasing it， which is where I give it a different name if I want to。

 So that's actually， if just just double check this code works。 So slash bh。



![](img/85988d628516a6d841ace419e002d1b9_51.png)

Got it， gotta MPM install date functions。Now when I run it。That should work， yeah works true。



![](img/85988d628516a6d841ace419e002d1b9_53.png)

But what happens if I don't like that namecause I don't think it's clear。

 I can actually add after that as and then give it another name， like date functions is valid， right。

 Maybe that's a bit easier for like programmers to read So they know that that's like a library coming from date functions。

I'm not saying that's always a good idea。 It seems very intuitive to do。

 but this is where like programming gets complicated because part of your brain could be like， oh。

 that seems clearer what it does'ca I know where it's from。 But the other part is like。

 what happens if you're working with a developer who has used date functions for years。

 They know what is valid means they have a good editor where they can just like hover over something and it tells them where it came from。

 you know。Like， why would you rename it， It could be more confusing becauseuse there's this idea I'm going to keep coming back to in later weeks。

 which is that one of the most common tropes of bad programming is。

You trying to make your code more readable by changing accepted norms。😡。

Because every time that you redefine what something is， someone who's experience with that。

Doesn't know what it is。 A really good example， right， is I see this all the time。

 Sometimes someone might come along。 This is not the best example。

 but some people make shortcuts in their computer to like rename Git as like G。

 So G like runs the git command。 You can kind of do this yourself。 I think I could do it here。

 I'll show you。 I'm gonna make a new file in this is unrelated to anything。 has nothing do with on 5。

31。 I'm gonna make a new file called bin slash G。 And I can't remember how to write bash。

 but I'll write Git。 There's there's better ways to do this。

 There's courses you can go and learn about this。 And I'll bugger off。



![](img/85988d628516a6d841ace419e002d1b9_55.png)

If I was more proficient and bash， I would。Go and do more。 But the point is now， when I run the。Now。

 when I run the G command， it runs git for me like this。 So G means git。 And it's like。

 this seems cute'cause you're like oh， less keys， less typing， less effort， but。Now。

 someone who uses my computer has no idea。 Someone who's used Git for years is just like。

 what the hell is G。You know。But the hell is G。I think， I think there's a way， like。

 if anyone's curious， I think there's a way you can get that to work by。 I can't remember。

 what is it， Is it at hash。Oh， God， let me just quickly bash all variables or something。

 Some or know。All a。See if someone beats me to it。Oh， dollar app。s that it。 Doll。 There we go。

 think that might be it。 Maybe that'll work now。G commit。耶。Yeah， that worked。 It's not a git repo。

 I don't think is the problem。But you know， G and N。Yeah， yeah。 worked， worked fine。 Yeah。

 so that's unrelated。 bit of fun。 Sometimes you guys like fun。😊，um。Okay， some questions。

William says with named exports， can we export functions under another name， I think I answered that。

 What's the benefit of renaming answered that can you do a thing in Python where you import date functions and then doing something like date dot is valid。



![](img/85988d628516a6d841ace419e002d1b9_57.png)

Yeah， I believe so。 Yes， is the answer。 I'm 100% sure。But it's a great question， actually，cause like。

 what you can do is instead of having to， I'm 99% sure。

 instead of having to like manually import everything like that， you can actually just like， go。

 you know， multi export or something。 And then when you call it， just do multi export dot that。

Unless I'm really just confusing myself with Python， and this actually doesn't work。



![](img/85988d628516a6d841ace419e002d1b9_59.png)

![](img/85988d628516a6d841ace419e002d1b9_60.png)

Normally， normally I try and avoid this。Okay， it works fine。

Normally one of the reasons that I think this is good to avoid is depends on the scenario。

 but generally named exports are really good。 There is an actual downside of this。

 God software is confusing。 like a historical problem is that when you import that。

 you import everything。 But then like modern interpret as and modern compilers get much。

 much smarter。And therefore， what they actually will do is sometimes they'll do things。

I don't know a lot about it， right， But I know that it's always trending in that direction。

 This is like a problem you get in computing is that often you'll get told not to do something because it's like inefficient。

 You know， like this used to be the case about declaring a variable in a full loop instead of before a full loop。

 And everyone was like， oh you you can speed up your code。

 But then computers and compilers and stuff just got smarter because people were like hey。

 everyone's doing this And it's really slow， So then they improve it And then a lot of the things you learn to be better。

 don't really matter， which is why it's always really good to focus on code readability as the primary thing because people generally。

 like humans don't really read code better now than they did five years ago。

 But computers are much smarter at doing things more efficiently behind the scenes than they were five years ago。

 So the question to always ask with this stuff is is this clearer。

 I this more understandable for a programmer or is this more understandable for a programmer。Right。

Most of the time， it's probably going to be this。I would say。And generally。

 it's rare that you're importing more than， you know。



![](img/85988d628516a6d841ace419e002d1b9_62.png)

1 to5 things from a library。Okay， so we're getting towards the end here。Generally。

 if you're importing many things， we'll break it up over the multiple lines like this。

 We'll go and say， like， you know， import and then like 1，2，3，4 like that over multiple lines。

 We usually don't kind of just have a really long line。

 We'll talk more about good code style next week。 I think on Wednesday。

 So we'll come back to that for sure， which will be good。 Oh， we're at the end。 That's cool。

 That's good。😊，Let's answer a few more questions before we wrap up。

 I told you I'd get you out of here as quick as I could。William says funny joke。

 if nodede module is so big， Why won't it fight me？ It's probably scared of you。

 Bbline says moral of the story， not all shortcuts are worth it。 slash a good thing。 Yeah。

 I would go so far as to say most shortcuts in programming are not worth it or a good thing。

 And I feel like what happened。 It's really quite interesting as you get older as a programmer。

 you basically just stop trying to be smart。And I see this all the time， even in my company。

 like the older programmers in their early 30s， you know， ones that are older than me。

 they're always constantly just being like， you're over complicating it， you're over complicating it。

 you're trying to be too smart， you're trying to you know this and that whereas like the younger ones。

 Well， I think I have very good ones in my company。

 but you know' they'll be overthinking things a lot and you know sometimes thinking that's a very big generalization。

 I'm not talking about specific people， but it's something you see a lot。

 Jad says do we have any NPpm not permit not permit to use。

I think what Jed's asking there is there any libraries that we could install with NPM that we're not allowed to install with NPM generally speaking。

 no， if you're unsure， just post on the forum， but。嗯。No， I don't believe so。Like。No。Like。

 I'll be like his， his， let me explain。 So if someone was to like， take their 1，5，3，1 assignment。

And like publish it to NP PM， which is already a very serious plagiarism thing。 And you are like。

 I can download any library。 I will just go and download the 1，5，3，1 library。That someone else wrote。

 which is obviously plagiarism too。 Like， obviously， that's not okay。 Like， you know， there's。

 there's some really obvious weird edge cases。 But generally speaking， you can use whatever you want。

嗯。Derpe says， why is it that Javascript requires you to install libraries， but C doesn't。 Well。

 I think what's important to understand is that Cs are really simple language。

 and most of the libraries that you had prein were really basic。

 And most of the things that C can do that are preinled like Javascript just does out of the box。

 And then those 28。Built in libraries help you do even more stuff。 So I don't really think about it。

 like C has everything whereas jascript makes you install it。 I'd more go like C is really basic。

 And that's kind of most of it。 Javascript core is quite basic， too。

 But then it has all this rich stuff that you can download and expand what you can do。

 Bubline says a question Feration 0。 How many， how detailed should I meet it。

 Minute for our group meetings be。 not， not extensive。Itd be like 50 hundred words。

 half a dozen dot points。Don't， don't write it like you'， Don't write it like you're trying to。

You know， impress someone， write notes about meetings。For you to jog your memory in six months。

 That's like the way to think about it。 That's what I， that's what we do every day， like， you know。

It's for you。 It's for you。 It's for you in the forgetful future。 That's like the right way。

 So that doesn't have to be super detailed。 It's just enough to reconstruct what happened。 Yeah。

 that's， that's probably the best answer I can give。嗯。I think that's the end of the questions。

We're finishing 14 minutes，10， you know，10 to 15 minutes early， but that's okay。

 We ran a bit late last Monday。 I'm going wrap up there。 if you could leave some feedback for 2。2。

 That would be great。 Again， we have our lecture on Wednesday。 for those of you who I see live。

 I'll see you there。 For those of you who I don't see live。 You know， you watch a pre recording。😊。

And yeah。Good luck this week。 Keep it up。 Iteration 0 be easy。 This week will be pretty easy。

 and we'll chat Wednesday。Cool。Okay， thank you， everyone。 Have a great evening。

 Enjoy your dinner for those having dinner。😊。

![](img/85988d628516a6d841ace419e002d1b9_64.png)