# UNSW《高级C++编程｜Advanced C++ Programming COMP6771 21T2》中英字幕（claude-3.7-s - P5：-05-COMP6771 21T2 - 1.4 - Assignment 1.zh_en - GPT中英字幕课程资源 - BV1NGQcYLEiV

We're here to talk about assignment one， so we're going to talk about this for about 20 ish minutes because you'll probably have a bunch of questions。

😊，What is assignment1 assignment1 is an assignment where we're asking you to build a word letter in C++。

And what a word ladder is is， we'll get to it here。It is where you take a word。

And you try and get to another word by only modifying one letter at a time。

 But each intermediate word you have needs to be a valid word。 So say I say to you。

 Can you get from the word code to the word data。Code， will you change the O to an A。

 then you change the D to a T， then you change the C to a D， and then you change the E to an A。

 And all of these three words in the middle are valid words， right， They're real words。

If you can find a path from word A to word B via a series of valid words。

 then you have a word letter。Sometimes。There's multiple ways to get through it。 So， for instance。

If you go from work to play。There's many ways you can get there， lots of different paths if you will。

So that's what a word letter is and this assignment is asking you to essentially write the code that will find word letters between two different words。

Most of this assignment relies on knowledge that we teach you in week one and week two。

Though I honestly think you can easily start this， this weekend and。Yeah。

 I I don't think there's there's I think you can make reasonable headway and a lot of what we talk about in week two are just explaining concepts that you can easily Google as well like it just putting them in context so don't feel handicapped to finish this。

嗯。ちち。Blah blah blah blah， blah， bhlah， blah， we're going to expect you to use things like standard vector。

 standard Q， standard unordered set， which we just talked about。To build it。Which is good。

And essentially the core of it， this assignment is asking you to write a function。

 and that function is a function called generate， which will take in a starting word。

A finishing word and a lexicon。 And what's a lexicon。 It's like a bunch of words。

 It's a bunch of valid words。 It's like all the valid words in the English language， right。

 That's what it is。 And we want you to try and do a breathth first search， which you knowca 25。

2 ones a prere 251 ones a prere。CsC keeps changing everything。Anyway。

We want you to do a breathth first search， which is not a very complicated algorithm。

 and most of you would have been exposed to it if you haven't then， well。

 I don't want to say it's my fault， but it doesn't matter who fault it is。We'll help you out。

If you are you try and go from work to play with all these valid words。Doing a breath first search。

Now， this kind of gets into how to go about it， right， It's like， okay， well。

 a word ladder is the shortest path problem because like you can take an English like。Conceptually。

 you can take， I'll try and maybe do this one in paint。 I've still got paint open， great。You know。

 you might have a word here like dog。And then dog， it will say cog。And dag。And。Bg。

And these are all connected like in a graph。Oh， 252 ones a prere 2511 great， thank you， that's good。

I can't keep up， and I'm very thrilled to hear that。 And then from bog you might have。

 I mean Bog also goes to Calright Lake。Bg also goes to Cog。 And then you have another word like。Bo。

 bo， yeah， like that。 and you could actually build the entire kind of English set of words as a big graph with nodes and edges。

And then when I ask you。To give me a word letter from Cog to。Bow or bow。Is that a homoym。

 is what they call it homo anyway。 Bo bow。 It's actually just like searching a graph。

 So you're essentially just breath first searching a graph to get that， right。 You're like， oh。

 I've got to go to Cog and then I've got to go to dog and then bog and then I'm there or Cog and then bog and then I'm there。

 It's like， okay， that's the shortest path like here。So。Very simple search problem。Because， you know。

 there's all the， all the edges of the same weight。 It's just like a simple graph bread first search。

 You could make it faster by， you know。Doing some things。嗯。But yeah， it's a breath first search。

 you build the English language， you build the English language。

 You build all the English words or the lexicon， right， It's not。 It's whatever we give you。

 You build it all as a graph。 You search the graph。So starting point， ending point， search the graph。

 There's your word loud。 There might be multiple answers。 So conceptually， it's a very。

 very straightforward assignment。 It's a bit of a fun assignment because。

You can get what you have to do like that。 And then it's hard to solve， right。

 And they're kind of more fun assignments than're just having to do a lot of work。Com。A very。

 very capable student。去。Is familiar with C plus plus could probably do this in。I don't know。

 like not long， it's like， you know， maybe an hour max。

Most of this is to get you familiar with the language， the C++ language。

The actual problem itself is kind of like it's easy enough if you do it every day。

 but you're probably like me like you're not very you know， you're not like a prodigy， so。You know。

 you'd be like， ohsh， what's a graph and then youve got to figure that out and then you try and code it。

 So it's for most of you， it's going to be like a nice little challenge。

 nothing like nothing earth shattering， but just a nice little challenge to warm you into the course。

There's some more content here that I won't go through in exceptional detail。Basically。

 they talk about。Cycle checking because that's like one hard thing about。

Searching is like you don't want to get caught in cycles in graphs right because you don't want to say oh Cog is dog and then dog is bug and then doggg is Cog and then Cogs dog and then dog is bug and then bogg is Cog and then Cogs dog。

That's definitely gonna be one of my top five。 I hope no one takes a snippet。

 five second snippet of that。 So you have to do some kind of cycle checking as well。

 So when you're searching， you will need to kind of store some sense of history。

 And I'm trying not to give away too muchca you know， that's part of what the assignment is， is。

 is to， to figure these things out。嗯。If there are multiple shortest paths。

 you must return all solutions and the solutions must be sorted in leographical order。

 So they actually need to be sorted and what that means is you notice see how f is before P。

 which is before W and then of all the ones that are P。

 it's like these are all alphabetically sorted so you have to return these alphabetically be careful of that because in the last term a lot of students lost at least one mark like。

Lost at least。5 to 8% just because they miss that part。 so be very careful of that。

 make sure they're sorted lexographically。

![](img/e29cd3966484e7d0141f10ba701a6da8_1.png)

Y， but we give you lots of hints about the particular C++ data structures to use。And。Yeah。

The the actual task itself， I mean， this stuff here is just more like this isn't like stages like stage1。

 stage2， stage3。 This is more like here's some helpful advice to go about it， which is probably like。

 you know。Do the week one shoot， design some tests。

 write the algorithms and stuff that's really pretty straightforward and I might jump down here because someone's asked do we need to write tests？

W do need the write tests。This assignment is worth 15% of the grade in the course。

 50% of those marks come from auto marking we mark the correctness of your code by running your code through an auto marker and seeing if you got the right outputs。

25 Biennio Mo comes from writing tests。Using catch2。

 and we want you to write these tests in the test directory， that's why we look for them。

We want you to write as many tests as you feel that you need to ensure that your code is correct。

We will mark your tests based on， are your tests correct， as in do they。

 do they actually test your code correctly， The tutor will look at them too and be like。

 does this make sense， We mark your test coverage， This is for those again who。

The problem is because at H 1，5，31 you hear me and you hear me say coverage and you think like pie coverage。

 but this is gonna to be your tutor just looking at your tests and being like。

 have they covered all the test cases， It's very visual brittleness。

 which is that we want you to make sure you aren't breaking abstraction as in your test should be black box tests。

 they should only be calling generate and stuff， they shouldn't be like。

Looking at the graph you generate or anything like that， that's nearly free marks honestly。

 And then clarity which is have you commented it correctly， have you explained it correctly。

 Is it laid out logically and all of that。嗯。And we do expect you to pass your own tests， as well。

20% of the marks come from C plus plus best practices。

 These are things like using con when you should。 These are things like using auto references。

Not using C style arrays， avoiding pointers， just all these little things that we talk about with lectures。

If if you've been going to the tus and going to the lectures and listening。

 then it's pretty easy to like do this because tutors will look for mistakes right they're not looking for perfect things they're just looking for mistakes like are you using four eye counter loops instead of four range loops which are better and cleaner and more obvious as to what's happening？

And then， the last thing。5% is for playingang format， basically style。

 But what's cool about this course。 And I'll show you this。 This will be sick is that。

What we actually have given you？Is。A you can run this on CSE machines。Where。

If you get one of your C++ files。Right。And you go clang format。11。

 and then you give it the file name， which in this case is demo 110。

What this program does is it actually takes your program。

 and it essentially like linkss it and reformats it to the correct style。 And if you do the dash I。

It will not just print it out， I'll actually update the file。So in this case here。

 you can see there's a tab there。 So for instance， if I do something like this and I save it and then I run it。

 it will automatically style my code。 So we give you 5% because it's so easy。

 We don't want to give you much for it。 But essentially， we will run clang format on your files。

And if we see cl format pick up on any problems， then you'll lose that 5%， so it's totally automated。

But yeah， that's it。 that's where the style comes from。 So people ask me like， oh。

 you're gonna mark like indentation and like， you know。Stuff like that。 And it's like。No。

 we're not gonna mark indentation because we're gonna run clang format on it， which'll do it for us。

 So as long as your code like kind of passes clang format， you're suite。So back to the spec。

Don't plagiarize， we'll run plagiarism and checking on everything。

 there's always someone who does it， there's always someone who does it。

 don't be that person who gets zero。嗯。The assignment is due on Friday of week 3 at 8 PM。

 I get this all the time。 Someone's like， oh， blah， bh， bh， why is it not due on。

Like we don't want it to be joining later because we we can't we could always make a due in week 10。

 but we're given you two and a half weeks with this。

ItIt's really hard to support the farm on the weekend。

 And whenever you make things due on a Sunday night or a Monday morning， you guys don't start it。

 frankly， like those of you who will submit this late and and really want another week are the ones who won't start it until you absolutely can't not anymore。

 And they're the ones who need all the help on the weekend。

 So we like things being due on a Friday which which still gives you two whole weekends， by the way。

 two entire weekends because we can actually then help you in the lead up to it being due。

 So that's why it's due on a Friday。 it's due at 8 PM。 you can always submit it before that。

 The late penalties 2% off the max every hour。2% off the max so that means if you submit it at midnight。

 the max is 92%。And。Yeah， Jin says， well， we have some auto tests。No， you don't。

 You don't really need auto tests because you have your own tests， like auto tests wouldn't。

Achieve anything。Becauseuse you can just run your own tests。

It's not we're not like this is a level 6 course。 This isn't 1511 where we we give you a dry run or something like that。

 you know， we we expect you to be able to test your own code and read a specification。

 You're all big adults now， and I I believe in you to rise to the occasion of being， you know。

 not not children。A couple of other notes here。🤢，You're going to want to use an unordered set to keep track of lexicons yes。

 the English dictionary will be provided， you're going to want to use unored map or some you're going to want to use some of these data structures we've talked through today。

 right。You won't have using anything。Super crazy。 Yeah。

 you can use clang format 11 for your assignment。 absolutelysolute。 Yeah， yeah， totally。

Most of this is pretty selfexplanatory or we've explained it before。

 I guess a couple of notes here that you can add more tests so you can make more test files。

 We give you instructions about how to add more test files。 I'll usually get the question。

 should we add everything in one test file or should we create many test files。

 The answer to that is。What do you think makes more sense， We're giving you marks for clarity。

 not the number of files， so maybe you think one file makes a lot more sense。

 maybe you think 30 files makes a lot more sense。We just expect you to apply common sense。

And if you get that wrong， we'll tell you。The most important thing here is。

Measuring your not the most important， another important thing here is measuring your performance。

Each time we run a test on your code， each word ladder we run。

 we'll put a 15 second time limit on it。That means we expect on the CSE machines that every single test。

 every single generate function call can pass within 15 seconds。This will not impact you much。

Because most word letterss are trivial to generate。The harder word letters take longer。

This is a searching problem， which means it is an MP complete problem。

 which means that it is an exponential problem。It's not like so the hard word ladder is。

 you will have to think smarter about your code。 you will have to think about your algorithms。

 You will have to think about references。 you'll have to think about if you can use more data structures to speed it up。

 right。嗯。There is no memory limit because generally speaking15 seconds will。

Like there is no memory limit except for the server itself like so I don't want I don't want to have someone be like you didn't impose a memory limit and maybe be like your program tried to use2 gigaby of Ram like I don't know what I don't know what you want me to tell you。

Your program should use less than a gigabyte of RA， okay， that's like。

 you know if you're using that much RA， you've done something terrible。

So there is no like hard memory limit except what the server will tolerate。

 which is the the size of the server。 you can benchmark your own。

Code by following these instructions here， I added this myself。

Your code will run slower when it's into bug mode， we will test it in release mode。

 so you can change this on VS code， you can build build Tt that's meant to be target I'm sorry。

 and then you can just say follow these instructions to actually see how long it takes。

Right and you can do that on the CSE machines to benchmark we don't care how long it takes on your computer。

 we care how long it takes on the CSE machine。嗯。5 minutes。

 the only other thing I think I want to just show you is cloning up and running it。

 So let's clone it quickly into Vlab。 and then we we can look at it together。

 I'm just going to close this。So you can clone your own reaper here。Ask one。Go inside it。

Open up the S code。Should configure。 O， I think， yep， you can pick 6，7，7，1。B'am。Does it configuring？

Cool。Now a couple of key files to notice， you'll notice that all of your tests are inside this word letter folder here。

 let me just make this slightly bigger。嗯。So there's actually a test we've written here called benchmarkchmark。

 which is the hardest。Word ladder。 so you can actually run this test just to see what the hardest word ladder out there is。

 So if you can， if you can do this one in 15 seconds， then you're fine with all the test cases。

 This one's hard， though， like。80% of you probably won't， I don't know。 I'm just making up a number。

 but like more probably more than half of you won't get this under 15 seconds。

 And that's totally okay because it's like the very hardest one。

 I remember MP complete problems like rocket it up So like literally the problem that's like one character less than this will be like 10 times quicker。

 So don't don't beat yourself up about it。 and you can write more test here。

 like we've written a sample test for you from app to it。

 just to get you started pretty straightforward。The actual source folder contains a few things。

 It contains your word ladder file， which you have to implement。

 This is where you're going to do most of your work。 It contains a lexicon file。

 which you will use in your word ladder。 This one is written for you。 It basically takes a file path。

 and it opens a le。 It opens the file， and it returns a unaudered set of strings。

 So you see here how it。It。去。Yep， it's a function that。

Takes in a file path and it returns an unordered set of strings。

 so it basically turns a dictionary file， which is here English dotTXT。

And it turns it into an unordered set of strings for you， so that's something you don't have to do。

 which is super helpful。And then we also have this other file here called thebugging main。

I added this for everyone last year because I think one thing I learned is just students at the start of this course don't feel comfortable testing stuff early on with tests Like you just want to feel it like you just want to play with it。

 So this is how this is where you can play around with it。 I've written some comments here as well。

 So you open the lexicon。You generate the word， you get the outputs like so the environment's quite set up for you to go。

The only thing probably to really take note of it is's different is。In this course。

 the way we've set up the environment is dot H files actually exist inside this include folder here。

嗯。Like this。So。This is where the dot H file basically is。

 its insight includes s Com 6771 s wordla dot CPP。一。That's， that's really it。

 So word ladder includes word ladder 8。 And， you know， that's， that's the dot H file。

 We all know what dot H files are。Kyle says， we're going to cover namespaces。

We will cover name spaces next week。There's， they're pretty quick to learn yourself too。 And like。

 you know， again， as as I've said， you know， this is a level 6 course， so。

we do expect you to be able to like do some basic googling and figure some things out like we're not gonna tell you everything。

 So in the meantime， like don' don't sit around being like。

 oh I don't know what a namespace is can't do anything's like just go go it and you'll find the answer and we'll try and teach you where we can the very nature of this and try masters as we kind of have to like have you teach yourself a couple things early on maybe but you can definitely start this assignment。

 I would definitely try and start it this weekend because then at least you'll know what you don't know for next week and then you can finish it the following weekend。



![](img/e29cd3966484e7d0141f10ba701a6da8_3.png)

I think that's it，754， any other questions， otherwise we'll wrap up。I mean。

 I know you'll have more questions about this and we can talk about it next week in week  three。

 It's not due for two and a half weeks， but this is kind of the overview to get you started。

Do you have access to the CSE labs， Oh， I don't know。Probably， I guess so。

There's probably some time limits on them though I don't know。 You could probably。I mean， Kai。

 Kai probably knows he's in the chat。I mean， I know your Ka is not in the country。

 but I'm sure you know， oh you know who to email， sure someone knows。No discard， What does that do？🤢。

This is in week four lectures and my brain's just forgotten off the top of my head。

I I can just Google it， but it。I should know this off the top of my head。It doesn't mean anything。

 really。Is called from a discoted value expression。My brain's shuting down。I'm on edge。 I'm on edge。

I'm not sure。 I mean， I do know。 I just， I just think this is in a lecture that I haven't thought about for a year。

 So I'm sure someone else knows。Yeah， so the assignment is getting released right after I'll deploy it。

I'll deploy it。Immediately after the lecture。I was going to do before the lecture。

 but my Tuesday is a bit cooked， so。Anyway， let's not get caught up on that。

 We'll talk about that in week4。 It's really not important。 Actually。

 it's just a really small detail。 But in general， you're gonna have to modify word ladder dot CPP and some test files。



![](img/e29cd3966484e7d0141f10ba701a6da8_5.png)

![](img/e29cd3966484e7d0141f10ba701a6da8_6.png)

If you're not sure where to start。You can just literally copy and paste this。Paste it in here。

And then implement the functions because， you know， dot H files are just prototypes。

 So there's one function there。 Read Lexicon。 And here's another function here。

 generate and get going。 That's it。 Start writing some code。没生活。嗯。Cool， okay， well， thanks everyone。

 I hope you have a great night。 I'll talk to you next week。

 I'll send you a notice later in the week around the weekend with a bit of some updates and some reminders。

😊，Andll push the Simon out now。Have a great night。Oh wait， wait， wait wait， sorry， sorry， sorry。

 sorry， Okay， oh my God。 Before you leave。 I mean， no one's left。 Maybe someone's left。

 but I forgot to do this on Monday， and I was hitting myself， but。There's a QR code here。

 which I would love for you to scan with your phone if you get a chance。

 because every lecture I do and it'll be great if you could fill this out。Once or twice。

 But every lecture I do， I'm going to try and put this up at the end so that I can get some feedback from you so that like next term and stuff when I look at。

When I look at these lectures， I can actually like figure out， you know which ones people like。

 which ones people didn't like， etc cetera。 So if you're feeling really lazy。

 just do the one for the C plus plus basic lecture， which was today。

 don't worry about the previous ones。 That's just my mistake。 But yeah。

 just it's really quick survey。 It's like like bam bam。 you don't even have to leave comments。

 I don't really care if you leave comments。 Just like give it a rating and。

I don't actually know what the link is。Sorry， I do。 I'm sorry。 I don't know why I said that。

I'll send the link in the chat it's a QR code because if I send the link in the chat people watching the recording。

嗯。Kant access it。Et cetera。 So， and I know most of you are millennials with phones in your hands all the time。

 The funny thing is some of you are such millennials that you have your guard damn phone in your hand while you're watching this somehow。

 you maniacs。But that's okay。 We don't need。 I don't need everyone to fill it out。

 It's not compulsory。 I just， it helps if like 10% of people fill it outcause it gives me a general。

 general sense anyway。Thank you again， I'll say bye for the second time。Have a great。

 have a great evening。