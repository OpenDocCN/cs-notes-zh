# CMU《函数式编程｜15-150 Functional Programming, Fall 2023》中英字幕（deepseek - P14：-14-14. Structures and Signatures _ - GPT中英字幕课程资源 - BV12VChY2EF4

We're gonna go go ahead and get started there's not a whole lot of people lecture but at this point I gotta go because otherwise we're at liable map to make it through all the way welcomel to lecture 14 we're talking about structures and signatures which is one part of a three part about modules we're gonna be learning about modules in three stages today structures and signatures next week funcctors and then next week again red black trees okay modules is not like the hardest topic it's difficult sometimes to get the point but most of the things we're gonna the third lecture is not really about modules to be honest it's a case study。

I have to say when I was taking this course， modules was probably my least favorite topic in the course just because I didn't really see the point。

 but the thing that you have to realize about modules is it's hard for me to motivate here because what we're talking about today is software composition we're talking about making software writing software because there's two aspects to a problem there's the actual computation aspect there's writing the functions and then there's two the humanoriented aspect。

 the organizing your software today that's what we're talking about so if any of you are interested in being software engineers this is really really important for you okay。

😡，And then the next thing I wanted to say was， oh， that was pretty much it yes， okay， cool。

 but otherwise we will get started so。We have five things to talk about today we're gonna be talking about this idea of structures or modules and namespaces we'll get into interfaces also known as signatures。

 a brief addendum on abstraction and information hiding and then we'll talk about kind of a result to come out of this thing called representation independence which is a really powerful way to think about your software and I realized that we're looking at this in ML we're looking at it in SML but these ideas are extremely extremely generalizable SML has probably one of the most sophisticated module systems out of any programming language in the world every other programming language wishes they have this module system and I'm so serious about this so let's go ahead and get into it shall we？

😡，Okay so so far we've looked at a fair amount of language features in SNL we've seen functions。

 we've seen data types， we've seen exceptions， which are all the bread and butter things you need to make a programming language and these help us solve type A problems I'll say type A meaning write the function okay but if you only solve type A problems no one's gonna want to work with you because you're like a hermit writing code by yourself in your cabin and no one can read it like who's the guy who wrote Tle O。

 you know Tle O， this is like guy who thought he had a vision from God to write an operating system so he locks himself in and writes this operating system by himself for like decades and it was actually really cool but was the point is that guy was crazy。

 don't be him right working with others is part of the name of the game so code is not meant to be just written。

 it's meant to be read， it's meant to be used， it's meant to be documented so what we're talking about today is how we can make that process of collaborating with others in software part of the language and how we can do it by how it is part of the language in standard。

あ。Okay， so。One particular thing that is a powerful idea for this is something called a namespace。

 Has anyone heard this before。 It's idea of a namespace。

 It's kind of a general sort of programming thing。 right。

 So one example of namespaces we've seen is in the structures you've been using。

 I'm sure that we've many of you have used the list library， right in S M L。

 I'm sure many of you have also used， I'm not sure if many of you have。

 Maybe the list one is pretty much the only one you've used。

 but I'm gonna tell you that there's another one called option。 actually no。

 strain string is another one。😊，And these are modules which i'll define for you in a second。

 but they're also namespaces， what does that mean， it means that for list there is a list dot compare right wait yes there's a list dot compare and then also there's a string dot compare right？

😡，I'm sure that many of you have run into this one。

 but the great thing about StrD Comp is that even though both of these are names compare。

 they don't get in the way of each other because if I wanted to access it。

 I would say list dot compare。😡，And I would say。String dot compare and they because they live in different modules。

 because they live in different namespaces， these are entirely different and they don't。😡。

Overrite each other they don't badly interact so this idea of namespaces is if I have related code if I have code that does different things。

 I should organize it in different ways in different namespaces so these are the namespaces in question and modules allow us to do that so that's what the namespace is。

😡。

![](img/09b6ec6e67293d66b339f20c32842774_1.png)

For instance it's also like list out length and string that size I guess。

 but there's a bunch of different functions that like come underneath each of these namespaces because it's a common grouping of functions of interest for the domain in question which is lists or strings it exhibits separation of concerns when I'm programming I want to separate my concerns okay。

😡，Okay， and actually， let me show you real fast an example because we can actually look at this within the SL interpreter ourselves。

 suppose I said this。😊。

![](img/09b6ec6e67293d66b339f20c32842774_3.png)

This is everything that exists within the list module all of these functions right here and so we can use any one of them you've probably seen a few in the documentation on the Sml andJ website I can similarly open string and now I can see everything that's inside of the string library but the point is that when I have a bunch of these functions it's not really good for me to just put it at the top level and then have is substr exists and also Re exists because guess what for string。

 rev there's also list do rev so it doesn't do for me to have both of the top level at the same time So if I put them into a module now I separate my concerns and I separate my problems okay。

😡，嗯。So these are things called modules and I'm going to show you an example really fast。

 will I write it on the board， I think I will。😡，Here's an example of a module， so I say module。😡。

I really mean structure， they're kind of called interchangeably in SML。

 so the keyword for declaring something like that is called literally structure。😡，And we say this。

 okay， it's worth noting this is entirely new syntax。

 This is one of the few times I will be teaching you something brand new that I've been trying to hide from you for the past several weeks so we can say for instance。

2。I's say data type T。Equals bar。Of int。I can put a data type declaration inside of my structure。

What's something else I could do， I could say Val。X equals bar of 5。Which should be of type T right。

 and then I might also say exception。E of T。And then I put I finish it up with an end。😡。

And this is a valid example of a structure in SL。 This one's a little weird like there's no real reason for us to define this as such。

 but you can throw whatever declarations you like in here。

 anything that can appear normally at the top level of an SML file that you've seen thus far in this semester can go inside of this structure so this is a nice way of separating our concerns。

 why because through is not just a structure， it is not just a drawing on the board。

 it is also a namespace， meaning that if I wanted to access the stuff inside of this module。

 I would do something like this in fact。😡。

![](img/09b6ec6e67293d66b339f20c32842774_5.png)

Wouldn't it be nice if Brandon had handily written out？This thing it's actually bar5。

 here's what we can do All right I can say Val X actually I'll do in the interpreter。

This will be a coding heavy lecture Okay， so you can see I have my module P。

 but I can say v y equals P dot x。😡，And now I have bound this thing by using Po as a prefix。

 by using P to open the namespace and then access the X thing inside， and we see it's a type P dot T。

 not of type T because the type T is inside of the structure P。😡。

And then if what if I wanted to raise this exception though， that we see over there， well。

 I could just do that， I could raise。😡，Why。😡，Oh wait， no， I cannot raise lie， sorry， I want to raise。



![](img/09b6ec6e67293d66b339f20c32842774_7.png)

B dot E of y， that was it。Right because remember sorry y is of type food。

t which is the input to this exception， so I can't raise the exception without doing also food。

 E so that really the thing you should remember is that to access anything inside this module I have to prefix it with fo because otherwise how am I supposed to get it all right so this illustrates a namespace that we are we're kind of defining and putting stuff inside of。

😡，And so everything inside that's local to that structure is one thing to remember as， okay？

So that is a module， but we're going to see a little bit more motivating use cases of modules because this is not quite super useful for us yet。

 okay。😡，So I've already done this so if I had a bunch of definitions basically I might want to put them in different modules because if I put them all in the same file now they're all going to live at the top level now I'm going to get confused now my software is not nicely organized。

 So do low spring cleaning on your code put it in modules Okay that's the idea domain specific logic should live in different domains。

😡，嗯。And a side note that。Yes。What type is of the structure it is not have a type structures are outside of the language of values and type structures live outside of them。

 yes。😡，Yes， yes， you can。Okay one other note， which is that you might be like okay。

 if I want to package together other bunch of values。

 why don't I use a tuple or something And yeah you could and the type will be gross because you would be like a million asterisks but the fact that structures can hold types is actually a really。

 really powerful aspect of it， which means that structures are strictly more powerful than tuples because you can put types inside of them and we're going to see next lecture with funs that this actually is really。

 really useful but this is I'm showing you something more powerful is basically the idea。嗯。Let's see。

 And then I wanted to also tell you kind of like how is this different from putting stuff in different files because I could put everything in the F module in file through Sml and everything else in a different file right But the difference is that if I load in files that have v x equals 2 and one and Val y equals3 and another right every one of those definitions of the top level is going to go into my top level which means that now x is going exist and y is going to exist And this is something that we call namespace clutter when when we clutter our namespace now X and y exist。

 I don't necessarily want to see everything I want to keep my namespace nice and small because otherwise when I'm programming。

 I'm gonna get confused at all the things that are lying around So putting stuff in modules kind of helps encapsulate some of the stuff so you don't have to think about it。



![](img/09b6ec6e67293d66b339f20c32842774_9.png)

Right okay， and then also I wanted to kind of go to this other example here。

 so remember the M sort function that we defined a little while ago， so if I have M sort to S oops。😊。

What I call it？Oh what， Okay， well， I thought I had it， but oh no exactly。No。

 and that's not that one。HOkay， we're going to do this， I thought I prepared it， but I did not。

Basically， what we're going to do。I just want to look at this and then I'm going to。Great， okay。

 now don't look at it anymore。 Okay， cool。 So this is our implementation of merge sort right that we saw in the previous lecture。

 at least now it is。 But the real thing that I wanted to tell you here is kind of like。

 if I have this all existing as one file， what happens if I go and I open up。

 open it up in the SM andJ interpreter。 So if I do SML and sort to SML。😊。

I'm going to get three things， I'm going to need to get split， merge and MLRT。😡。

But if you think about it， I shouldn't have to do that because split and merge are strictly helper functions that I use to define M。

 I don't really care about having access to split and merge once I'm done with M sort M sort is the only thing I care about within the file M sort to SML so you can imagine like if I had if I had all this stuff in a bunch of other files available and we're gonna simulate it by me writing sort SML a bunch of times okay if I did this。

 for instance， and I loaded M sort in like eight times。😡，Boom。

 look at all these things I'm getting if these had been different files。

 then I would be super spanned with a bunch of definitions that I don't want to see when really all I care about is this one。

😡，So let's try to figure out how we can kind of display this nicer and also make it less burdensome on the person that's programming so and let me make sure that yeah so okay。

 this was the thing I wanted to say about namespace clutter。😡。

So here's what we can do one thing that we can do is this there's something called a local declaration in SL。

 we say local， I indent all these guys， it's basically an end， but for declarations。😊。

So I made three changes there basically I put， I put local， I put in and I put end right。

 So like I put that local up there。 I put these declarations and these are local to this declaration。

 And what that means is that like a Latin end， these definitions do not escape the scope of this entire。

Block this entire declaration。Meaning that now， if I load。M sort to Sl。

 I'm only going to get M sort Okay， this is not super important to memorize。

 I just wanted to show you that it's something we can do。😡。

But I'm gonna to go ahead and play the gross card and tell you I don't really want to do that why because I had to change my source to do that when I'm up keepinging my documentation when I'm trying to make my code nicer to read。

 I've done the nicer to think about I've inadvertently made it not nice to read I'd like to be able to document and think about my code in a way where I do not sacrifice legibility or maintainability okay I don't want to have to think okay these are available here and then oh man but there's only so many locals like I don't want to think about that at all so let's try to do things slightly differently。

😡，And so I actually that okay， so here's what we could do， for instance。

 I could write at the top of the file this file contains oh here's another thing I want to say well which is a if I very quickly look at this file。

😡，This file， this file。It's not clear what's inside that I should be looking for right when you look at this right you see bunch a bunch of code and then you parse it a little bit and you see the locals are you're like oh。

 I only care about this， but just looking at this function now I have to read it。

 now I have to figure out what it's doing when at the end of the day all that matters is that it gives me M sort so what I might do is I might write this file contains。

😡，M sort of take endless to en list。And then I might write down here， ignore all this。Implementation。

And this is how C programme do things，😊，And by the way， that's not good。

 So I don't want to have to do this because now I have to maintain this documentation documentation。

 it's a comment， it's a comment in my source。 I need I want to teach I want to treat my documentation in a more firstclass way than this I want to be able to have maybe my language clued into the fact that I only want to expose certain things And so that's how we're going to do things。

 so。😡，I'll give you another difficulty of this。 All right， what if I go and I want and let's。

Take everything out of the local for now Okay what if furthermore I want to refactor to this code because this is M sort。

 which only sorts intless。 So if I want to do a little V magic， I would say。

And then I would do that again。And then almost boom and now it's all the CMP version right now I've extract refactored my code so that it has CMP everywhere I want it to。

This in a document now I' now I've refactored it so I put my CP function where I want to except for the fact that now this comment is out of date。

 that comment is wrong And if I am writing code and it's a Thursday night and I want to get home to my kids and my wife is mad at me and I slept on the couch last night like I want to make her happy and I want to make sure that I write my code fast and get home to my kids so I don't update this comment But the problem is now my code's wrong and are we in the business of producing wrong code。

 No， we're in the business of producing correct code So let's try to do better than this。



![](img/09b6ec6e67293d66b339f20c32842774_11.png)

So here's how we're going to do that， right？那么。Here's I' going to do，lah，lah，la，lah， blah what。

 here's the idea。What if our comments were checked by the compiler。

 what if we had an interface that the language was clued into such that if I made a mistake I automatically knew at trying to compile。

 what if my documentation was a part of the code I was writing okay and that's the idea。😡。

That's the idea of a signature， and there's two things we want to have in it。Or to tell someone， hey。

 I have certain declarations in this file I want you to see and then two the types of the things inside of the file why because remember types of the language of love types of the language of code so if I want to tell someone what my code does I want to tell them I have M sort but in particular I have M sort of type alpha star alpha to order blah blah blah。

 blah so the two things that we really want to have here are in our signature are these things okay and we're going to have be part of our language because of this stuff that we call signatures。

😡，Okay， are there any questions as far， by the way。

 because we're getting near to the and the first part？



![](img/09b6ec6e67293d66b339f20c32842774_13.png)

对。So let's go ahead and do it， I keep hittinging that， okay。And what we're going to do。

 actually I'll write on the board with you first。This is called a signature。

 so I'm going to use the keyword signature。😡，And I want a signature for my M sort module or file。

 Okay， Okay， so I'm going to write。Signature M sort and by convention。

 usually our signatures are all capitalized， but they do not need to be。

Signature M sort equals sig and so note the difference which is that for the structure example I had structure and then I hadstruct。

 but now we have signature and it's not too hard to remember I hope。😡，嗯。😊，And what do I put in here。

 Well， I'm not going to put a value， right， I'm not going to write fun Ms or do do Why。

 because this is a signature。 I'm trying to specify the interface to a file， not the implementation。

 So I'm going to write what I call a specification。 It's going to look like this。😡，Val。M sort。

Of tight。Alpha star alphapha to order。To alpha the list。To alpha lists。得。😊。

This is a specification because all I'm writing is the name of the identifier that I want to appear。

 so this is the thing I want to be in the file or in the module。

 and this is the type I want it to have。😡，And this is going to be checked by the compiler when we eventually try to mix and mash my structure with my signature。

 okay， but this is the idea of a signature， it's just this thing。😡。

One of the great things about this is here's another thing。So if we go back to our example of M sort。

 oh， I was actually just there shoot I don't know my key bindings， if I go back to M sort。

 here's what I could do as well。😡，I could put everything into a structure。

 I could just say structure MO equalsstruct。And then inject， everything by two。

And then put an end here。And this will be a valid way of doing things I could do this and then now I'd solve my problem of having all of myself at the top level。

 but what problem have I not solved？😡，Ensortt still has both split and merge inside of it because I didn't specify I didn't put a local。

 Everything inside of a module is by default visible from the module itself。

 if I do nothing okay so what I want to be able to do is again I want to hide the split and merge functions because I only am concerned with M sort because you can imagine also I realize this is a little bit of a dumb example。

 but if I was writing a really really long function， one that had like 20 helper functions。

 I want to make sure that only my entry point only the part of the code where outside consumers are meant to use is visible so this generalizes and this multiplies okay。

😡，So let's try it out well here's what I can do It would be really nice if someone had written the M sort signature out for us and the syntax highlight is going to be weird don't worry about it。

But this is the same signature that I put on the board。And here's what we can do。😡。

I'm going to write M to SL。😡，But instead of just writing structure here。

 I haven't clued this structure into that signature yet， so I'm going to write。😡，Colon。M sort。

And this is going to get， this is what we call transparent a， okay， and I'll go to the slide on it。😡。

here we go。h yeah， this is what we call a。 Okay so I just take my M sort module and I write this con M sort。

 This looks like a type annotation。 you can think of it about it as analogous to a type annotation。

 but it's not a type annotation。 Okay we are ascribing a structure to a signature we're saying that whatever sort the structure is。

 it should look like this to outside consumers of the library。

 And now if I try to load this into the Synj top level， What am I going to get。😡，Or no two， yes。

 the cool。Well， first let me wait do I do it， Yes I did。

 so I'm going to load both into Sml so I'm going to do m sort。 sig and then M sort Sml。😊。

And now I have the M sort structure， but the only thing inside is the M sort value。

 if I open the M sort structure， I'm going to get just this value M sort。😡，No merge。 No split。

Well that was just synax center， but whatever you get the point okay so by ascr we take away certain things that were not inside of the signature。

 so the way the real benefit of a signature we see right now is I get to limit the things available the things that you can see inside the view into the structure is kind of filtered by this signature you could also think of it as okay and that's really cool。

😡，And the next really cool thing about it is， well。

 if if what if my five year old gets a hold of my computer and then decides to change my M sort implementation such that now it's。

😡，2。😡，And sort of given CMP and the empty list gives me two all right， this is not of type。😡，That's。

 all right。So what can I do？Bm。😡，Value type and structure does not match signature spec if I refactor my code and I don't know about it。

 I don't realize that I'm not no longer fulfilling this contract。😡。

The compiler knows and the compiler complains and this is a contract I'm saying to the outside world。

 I'm presenting myself to the outside world in this way， in this way。

 and then this is what people get to see of me okay。😡，我生。反正。F fine。Yes， so。是的。

What kind of nutrition are you thinking of？indeed， well change okay when we get into imperative stuff in the very last lecture。

 we are going to see that you can change。Mutable fields。But。😡。

If if your structure contains purely immutable stuff then yes， you cannot change anything inside。

 Okay， it's a tricky conversation when you get into mutability as everything is， but yes。

 pretty much I'll give a hi you for that one not。😡，You I haven't get enough the high shoes recently。

 so who wants to high you？All right。Now I。Oh。🤢，I'm just giving a to random people that。I'm sorry。

All right。All right， that's it okay， fine， fine， fine， you still have your hand up， fine。😊，All right。

They want you on the inside， Okay， yeah yeah yeah。Al。I'm literally giving up for free。

 So I don't know why people aren't raising their hands。 But anyways。 Okay， all right， that's enough。

 that's enough。 No handouts cool。 Okay， now that I have your， now that I have your attention。

 let's talk about taxes。 I'm kidding。 Al right， so we're checking this with the type of the signature。

 All right， that's the main thing you should think about。 So if I wanted to write it out。

 I would say。

![](img/09b6ec6e67293d66b339f20c32842774_15.png)

Benefits of having。Signatures is one。Hiding declarations。

 hiding parts of the declarations that we don't care about， like helper functions and et cetera。

 and then two。Specifying types because if someone is using my library I want to have a contract that I'm upholding with them if I am providing a function that takes an ins and I go and I change it to taking in strings。

 I want people using this library to now have their code no longer compile why because otherwise if I give them if they give me a string。

😡，Bad things are going to happen。 So let's try to avoid that。 Okay， here are the benefits， allright。

But let's move on from that， shall we？ok。😊，And as I mentioned， yes。

 so this is all the stuff that happens， this is pretty much everything I said。😡，Okay。嗯。

Maybe we'll kind it Charlotte。Cool， all right， any questions on signatures and structures because I'm introducing something brand new。

 so if you have questions might as well。Oool， all right。

 abstraction is the next thing I wanted to talk about， so if I have my M sort signature。

 let' let's take a look and talk about this。😡，I'm going to take a little bit of a brief detour。

I've already kind of harped on to you about abstraction。

 but I want you to really feel the abstraction today。

 I want you to feel like a carpet burn like this is really important for what we're talking about today because abstraction is how we view software and when we work on software。

 you can't just think about what the code is doing all the time。

 you have to have high levelvel like notions of oh this code goes and mute and like changes this thing or like delivers the request to where rather than thinking about the very nty gritty details of what's happening。

😡，And whenever I think about this， I'm reminded of。Our slogan in this course。

 which is functions our values and I'm not wearing the jacket for you。 but as a bit of a side note。

 I was at a security conference like a few months ago and I was wearing my functions our values jacket and then this guy like comes up to me and he's like。

 he like looks at me and he like of walks around and he's like don't you know that functions are just or just X86 assembly and and then I go。

😊，Actually， I went to CM so yes， I know that thank you。

 but one of the things I think about when I think about that is is that there's a particular kind of person that thinks it is a big gotcha to go functions are pointers or oh computers are just bits and bytes and it's so ludicrous because people say for one thing ignorance is bliss。

 well I'll modify that of it， I'll say that selective ignorance is a gift if you're able to do it then you should here's the point。

Do I know deep down that computers running in the real world And there's。

 there's real hardware that is running all of our code。 Yes。

 but that doesn't change the way that I view my code。

 The way that I think about it when I want to use it efficiently， It's kind of like， you know。

 if I go to someone goes up to me and I say， oh， yeah， I've got some。

 I got some of my favorite fruits。 You know， I got strawberries and I got apples and they're like。

You just say that apples are fruit， don't you know the apples are made of atoms？And I look at them。

 I'm kind of like。Yeah， thanks。 anyways。 And I go to talk to my friends because I don't know what this person is doing。

 But the point is that something being something else。

 if you go down deep and you really take out your magnifying glass。

 does not change how you should think about it in your everyday life。

 am I am I going to rock in anyone's world if I tell you， hi， you're all made of atoms。

 Does that mean I can I can not treat you as human beings。 In fact， no， okay so。

It doesn't matter what something really is。 It doesn't matter what something is。

 It matters what something should be kind of in a sense。

 The other thing I I also have have an image of is someone going to the grocery grocery store I mean like。

😡，Excuse me， manager， you have tomatoes here under the vegetable section。

 don' you know that tomatoes are botanically fruits？😡。

The manager is not paid enough to deal with you okay this is what I think about whenever someone comes up to me is like don't you know the functions are really pointers yes。

 I do， but I choose not to think of them that way it's not a comment on my my knowledge it's a comment on how I choose to interact with the world okay。

😡，I tee you 213 I know this thing trust me So abstraction is what I want to really care about here。

 I want to be able to have higher level models of things than they really are because at the end of the day。

 that's kind of what we do in real life right if I want to understand anything my little human brain okay I have to put it in little human terms which are humans and functions and big you know like like little routines that go and they anthropomorphically go and they trade information Okay Alice and Bob so。

😡，That's why we choose to think about evaluation of expressions， not bit flipping in hardware。

 okay one of these things is nicer than the other。😡，To bring all this around。

Same thing at the software level， I want to think about only the things that are relevant to me if it felt like kind of trivial to you that I hid and merge and and。

 oh how interesting it's really important because I only want to care about the limited things that can fit in my little human brain If anyone here thinks like you're like a tennis engineer and it's not going to matter to you you're gonna be able to wade through the garbage I salute you and I wish you luck in life okay but。

😡，I prefer to think about things in ways that are easy for me Okay， and I think most engineers do so。

That's my diet tribe to you， okay？All right， so the point of specification is ignore the parts that are not relevant to you。

 okay？😡，And signatures and structures is not gonna to get us there all of this is to say really that this。

 this signature I gave you is actually kind of terrible in that regard。

 why because I said my signature is M sort and my value is M sort What is the one value you expect that is going to be put in the structure reasonably probably the function merge sort。

 it would be pretty weird if I like implemented a function I gave you always the empty list for instance。

 okay that's the only sensible thing， but I'mtraining my implementation here。

 what I mean is is if I give you a function or I give you structure and I tell you I'm giving you a sorting function。

😡，I should be able to leave it at that， I don't care what the sorting function is。

 I care that it is a sorting function because what am I going to do when I use the sorting function am I going to go and run through the MOR algorithm in my head and like divide and conquerd and then make sure that it makes sense in my head no because sorting is a very clear specification。

😡，So what I'm trying to say is。Let's。Erase two letters。This is a better signature。😡。

Because this is a signature that could be ascribed to you by multiple implementations。

 it's a signature that's useful to me as a programmer because why I look at it and I don't care what the sort is。

 I just care that it is a sort and it's fast enough and I want to sort， I don't want to write it。😡。

That's it， okay。So that's all to say this。oh yeah， there's also a comment。 Yeah， Okay。

 something you're gonna be like， oh， but Amazon store is log again。 Yeah， so is quick sort。

 So is probably other sort， I don't know。 The point is that it doesn't matter as long as it runs fast enough。

 which you should be assured of。And we are not yet at a point where we are our specification can type check cost bounds。

 actually that's impossible， but that would be pretty nice。So here's an updated signature。

Because I want to be able to remove as much irrelevant details as I can。

 I don't care that it's em sortt。 I just want to think about my code。

 I don't care about your code in the library。 Okay， and that's the sad truth， by the way， so。



![](img/09b6ec6e67293d66b339f20c32842774_17.png)

If I wanted to do this out in code， whether did I put it in， Oh yeah， M sort， we know， Oh yeah。

 I have an Ms insert I defined here。 Ive defined insertion sort for you and you don't to think about what it does。

 But first section， let me do this。And then let me go back to my M sort signature and let me latently lie。

😡，By changing it to sort。And if I do M sortta SIG， and then I do in SL。

I'm going to get a type error because I mess something up os。Okay。

 the point is here forgot I forgot the CMP function， but if I had not forgotten the CM function。

 this would have worked， in fact， do you care enough of I okay？😊，I don't care enough。I I got time。Oh。

 whoops。Oh， loves。No， I I did。 this is why it's more important to have things than text replaced。

 Okay， does this look good to everyone， Yeah， okay。😊，Yeah。Thank you。 Thank you。There we go。

 all right。So okay， let's go back。So the point is that what I did is I made it so that in actually takes in a comparison function too。

As you can imagine， like if I had in like you wrote it earlier in this course。

 I had wrote it specifically to Intel compare， but I don't need to I can make it as general as my M sort and now this value sort here。

 I use partial application if you want， I can write it out more explicitly。

 I can write fun sort CML is equal to in CL if that makes you feel better This is the same type as the M sort that I've defined。

😡，冇。This is the same type as this。😡，呃。Yes。These two things have the same type。

 okay so I should be able to do this。😡，嗯。140。M sort NL。Excuse。

And if I do m sort as SIig and then m sort as sG。And sort to SL。

 this will also type check okay does everyone get the idea of what I'm saying here that I can have two different implementations of sorting doesn't matter if it's merge sort or insertion sort。

 but both are visible or both are decribable。😡，By this signature right here。

 okay the same signature that's on the board okay so it doesn't matter what my implementation is if my only view into it is this description。

 I abstracted it away， yes。😡，Sadly no， sadly no yeah。

 so remember that one of the things about a comparison valid comparison function is that it's a total order。

 which I defined for you as meaning that you can put it on a number line like I can put my values on a line and then if they're less according to this number line they'll be less and then otherwise equal blah。

 blah and the question was， can wea， can we verify that this thing is truly a comparison function like in the specification and we cannot do that that is that is a hard thing to do。

In certain programming languages that are very， very wildly different than programming languages you've seen。

 you can， but that is at the cost of making type checking essentially the same thing as running an arbitrary program basically you run a program on your on your type anyways that's an aside side very much an aside。

😡，But yes， any other questions on structures， signatures， anything like that？

Does everyone get the idea of like why it's better to have this in the M sort signature？😡。

G give me a temperature check， thumbs up， thumbs down， thumbs sides。cool， all right， ya， stand up。

 nope， not today。

![](img/09b6ec6e67293d66b339f20c32842774_19.png)

Not any day。All right。嗯。All right， go take your quizzes。Get up， little here， thumbs of any kind。

 cool。All right， well， we're going to move on。 You're never going to guess， by the way。

Why the password was what it was， but'm anyways。The next thing that comes with this， okay。

 so let let me rephrase that。😡，What we saw already with structures and signatures is pretty cool。

 and I showed you two different forms of kind of lessening your cognitive load。

 which is kind of a big theme in software systems when you're architecting any kind of project。

 you want to think about the best way to present it to yourself to your collaborators here let me use let me use a tech buzz for you to your stakeholders but you want to think about the best way to structure your code such that it's very easy to think about so to that end。

 the way that you think about things is by thinking about less things we're going to keep with with that mantra here。

 which is that we get power through selective ignorance by hiding more things from consumers of our code and that's the idea of what's literally called information hiding information hiding is how we're going to make our libraries more palatable。

So recall that structures can contain types we haven't looked at any that have that yet really except for the one silly example I gave you。

 but we can have types inside of a signature So an structure。

 so let's consider a signature which describes a library for sets of integers and when I say library I mean this code will be shipped off to someone else in like Cambodia and they will load up the etl interpreter and then they'll get the code and then use it okay I mean thirdpart code code that you might write that somebody else in the world is going to use maybe it's you again。

 or maybe it's someone else entirely okay so we're dealing with two different problems here。😡。

And this is the signature I might write for that okay and' let's work through it a bit but the signature says that we have a type T and this inset do T type should be my type of integer sets I haven't said what it is I haven't told you what the type definition is。

 but this is fine syntactically because I'm saying that anything ascribing to this type T or to this signature inset needs to give me such a type。

😡，I don't know what it is。 I don't care what it is。

 I care that whatever implements this knows what it is Okay so the idea is that the interface just has this type and then I have four values。

 I have the empty set。 I have a function that takes an int in a set and gives me another set by inserting I have a function that removes an integer from a set and I have a function that checks for membership of an integer in the set okay and this should seem like a reasonable interface for a set。

 you know there are a few other helper functions we could put in there but this is pretty much all we need to get rocking okay and so the real point here is that。

😊，I don't really care who implements this， but the structure that ascribes to the signature needs to have these methods of this type it has to and granted a valid way to fulfill this type is to like write nonsense okay to like write raise fail unimplemented that's true but this is the best guarantee I can give you which is that at least these functions have these methods or sorry these functions have these types okay so let's take a look at that in code。

😡。

![](img/09b6ec6e67293d66b339f20c32842774_21.png)

So all right， if I were to open up my set do S here。

 this is my signature for sets and it's all green because I didn't bother to set up my syntax highlight lightinging。

😡，And then I'm going to tell you that this， in fact。😡，Is such an implementation。 All right。

 And let's walk through it。 Okay， so this inset， I haven't ascribed it yet， Okay， but I will。😡。

It implements the signature we see on the left here how well first I need to define the type T so I say that the type T is going to be in list we're going to represent sets using lists that's an easy way to do it okay and then I've got an insertion function。

😡，When I use my insertion function on Neil， I get the single ten， if I do an X and Xes。

 I check if it's equal to the first thing， if so then I don't do anything。

 otherwise I put it in and then Ioo， I rehearseop。😡，Wow。Wait。Cez， okay， this is just wrong。

 If I should check that if it's equal to the first thing that I put it in。 and then otherwise。

 if it's not， that I need to。I need to， I'm not re， oops。We know。Okay， you know what？

Shoot or anything present。Sure， okay， I'm trying to do two things which should put in there。 Okay。

 yeah， you know， actually none this is fine。I know what to do。There we go。

Yeah so otherwise I is forcur and I put it in and then eventually I'll reach the end of the list and then this will be put in I was top between wanting to do the comparison and the insertion at the same time。

 but they should happen in two cases So otherwise I just check whether or not' the same and then if so I don't keep this V otherwise I do put the V into the rest and then I keep the thing on the front and the same thing should happen here actually you see that actually by analogy it's exactly the same thing where I'm going to say that if V equals X here in the remove case I take off the X otherwise I keep the X and I remove V from the rest and that should be fair enough。

And then for membership， if it's the emptythe list， it's false。

 and then if I want to check membership of V inside of xon x's。😡。

It's either the first thing or it's a member of the rest。

Okay is this fairly clear as like a simple implementation of a set library？😊。

Do people think it works？Okay， that was not a gotcha， this one does work。😡。

I could have been in gotcha， but well it was a gotcha for me。 anyways。

 So this implements the inset signature in a nice way。 In fact， what we can do is we can then say。

Let me ascribe it。To inset， right？😡，So let me try to do that if I do this I'm going to get。😡。

These things which don't matter， but I'm going to get that indeed inset as a structure ascribes to inset the signature。

 So if I open and I didn't really mention this before。

 but you know open lets you take everything in a structure and then dump it out into the top level。😡。

I get all this stuff。😡，Okay， but the real important thing to see here is this。😡。

The type of inset dot T is in list now that should make sense to you。

 I said that to you literally like 20 seconds ago， but if somebody is using this library。

 if I'm this programmer in Cambodia， okay I should not be privy to the details of how the library is implemented why because here's what I'm going to do。

😡，One， two， three is a type inta T or sorry， that's fine 111 is a type inta T。

A valid set is the list 111。

![](img/09b6ec6e67293d66b339f20c32842774_23.png)

Let's take that to its logical conclusion， shall we？And so this is the， oh yeah yeah。

 that's also wrong， I'll fix it later。😊，So anyways。

 something else I should also to say is like this kind of description that I do here with the colon is called transparent ascription and you should think about it that should as a hint that I'm going to tell you about a different kind of description real soon。



![](img/09b6ec6e67293d66b339f20c32842774_25.png)

![](img/09b6ec6e67293d66b339f20c32842774_26.png)

诶。O pay description。 So here's my code brief Allright， I say that a set of type in T is equal to 1，1。

1，1 in a list a bunch of times。 And then I tell you， hey。

 this is a set without one I promise and it's by removing one from the set and then I run this code if one is a member of set without one I promise then I destroy the universe Otherwise I don't okay。

😡，This code。Detroys the universe。Okay， all because you couldn't keep your invariance in line。

 you couldn't keep your  ducks in a row。If I'm the consumer of this library and I can just go in and meddle with the internals of the implementation。

 however I like I'm perfectly free to do stuff like say that this is a valid inset T it's a valid list but if you think about like or invari that we have here。

 you cannot produce this value from any sequence or rather does anyone think you can produce this value from any sequence of operations that were in the inset library。

 you cannot because I will always you know maintain that there's exactly one of every element inside of the in list okay so this is a list to the compiler but really it's not。

😡，So let's do better。The idea behind opaque description is I shouldn't be able to ever see what this type is。

 I don't care， right？😡。

![](img/09b6ec6e67293d66b339f20c32842774_28.png)

嗯。So if we do this， here's what we're going to do。😡，This is called opaque a。

 opaque description is just where you put a greater than symbol after the colon and what it means now is that if I write SML set the SML。

😡，I get the same thing， but now if I open inset。😡，Type T is unknown。I have no idea what type T is。

 and that means if I try the same trick。😡，I get a type error， the compiler is going to tell me hey。

 what is this nonsense， you're saying that a list in list is of type in It， no it's not。😡。

And it's kind of an interesting thing where it's it's sort of like a parent keeping you inside the little playpen and they're like。

 no no no， you know like Santa real， Santa real great I I'm gonna spoil this for you Santais's not real Okay。

 same way that this list is not an inset All right。

 the compiler knows very well that this list is in fact of type inset。😡，But to you， the consumer。

 the person writing the code， you shouldn't know。 So it doesn't let you do it。 Okay。

 I'm going to show you an example of how we program with such an interface。 So first。

 let me clean up。I don't need to open it。😊，What this means is now。

 if this is what I call an abstract type and that is a vocabulary， by the way。

 So I will write it down in the word。The type T is called an abstract type。😡。

Whi is also the name of Robert Harper's blog， but actually it's existential type sorry but an abstract type is a type that I have no idea what it is all right it is implemented by somebody but then they took away my toys by using opaque description all right so I have no idea。

😡，And this means that the only way to get a value type inset。 T， how can I do it。

 the only way is to this library。😡，I'm only permitted to interface with sets through this library。

 okay？😡，And that means I can do stuff like this， so let's say that v S is equal to ins on empty。😡。

And then Val S。 And here's what it's gonna to do。 SML and J will print out to a hyphen。

 Why because it doesn't， it can't use the printer for ins。 You know， or in list。

 You don't know that it's an in list。 Okay， so it's， it's very hard to see when it's inside。 Okay。

 you usually have to write a separate helper functions， like show it。But let's do another thing。

 let's do v S is equal to。😡，Insteadset or insert。Let's see three into the list or into the set。

Oh my god， I should have did an R run， okay， and then let's insert two。Into S。

And now if I do inset on M2 of S， I'm going to get true， if I do inset on M1 of S。

 I'm going to get falses。😡，And if I do inset。m3 ofs， I'm going to also get through， okay。

 it behaves like a set。😡，And you should be assured of that because we just implemented it and you were assured that it was correct。

 So this means like like put yourself in the position of the programmer in Cambodia who doesn't know how it's implemented。

 This means that now this is all I see。 I don't get to meddle with things。

 And also I don't have to think about how it's implemented， I don't know how it's implemented。

 So even though we implemented this literally like five minutes ago together。😡。

I'm going to do a little men in black don't worry about it memoryory white okay is that a dated pop culture reference the point is that you forget how it's implemented because when you're working on code even to yourself。

 you shouldn't have to remember literally everything that's going on in your code base you should be able to think at the high level okay。

😡。

![](img/09b6ec6e67293d66b339f20c32842774_30.png)

So let's go back to the slides real fast so in particular what this lets us do is we can maintain invariance if nobody can interact with my library except for my functions。

 I make sure that my invaris are always respected namely the set invariant which is that I should only have at maximum one of each distinct integer in my set okay。

😡。

![](img/09b6ec6e67293d66b339f20c32842774_32.png)

All right， so anyways， I showed you this a P description self already， okay。😊，All right。

And this means now we can never destroy the universe， by the way。

 we can never destroy the universe with the code that I had previously because any value of inset doche truly should never have that one is a member of it if you literally just removed one from it。

😡，嗯。

![](img/09b6ec6e67293d66b339f20c32842774_34.png)

And this is just a bunch of code that I already did with you。 blah， blah， blah， blah blah， blah。

 Okay， here's the thing I wanted to say， I think one comment I kind of wanted to have here is like。

As a programmer， you are producing code for yourself and others， I've said this a lot of times。

 but this really shines through here where I'm going to tell you like with the opaque description you have no idea what the Inset is。

 even though the part of your brain and the half of your brain that implemented it five minutes ago does。

 but your working brain， the one that's like actually using this library when you act as the consumer of the library。

 you know as little as anyone else。😡，So it's a Chinese stance where you are both the consumer and the producer of this library。

 meaning that you should be able to produce a clean API that leaks no inside information and also use the API in a way such that you can maintain your conceptual knowledge。

😡，Moddules are not perfect for this， remember there's a lot of ways that we can satisfy the signature of inset that don't behave as a set should。

😡，But like， that's not on us。 That's on the program。 Okay， the best we can do is give you a type。

 al right。啊，O。So close your eyes， think like a user is the mantra for today。

 but here's a couple of reasons why you should care about it again， and I kind of said some of this。

 but again， it lightens your conceptual load because what would you rather think about。

 would you rather think about the code that's like being through or do you rather think about the high level set。

😡。

![](img/09b6ec6e67293d66b339f20c32842774_36.png)

And then two you can't break your own invariance， remember self defense against yourself。

 if I write this to destroy the universe code， I want to make sure that I can't break my own invariance and produce an invalid set。

😡，And you can't if you use the pay description。😡，And then three it helps you maintain your code because if you refactor your code for suppose like I got tired of insetss。

 okay， in lists for inss and so I went into my code base， right？😊，嗯。I went into my code base。

 and I literally like。诶爸爸爸。I went into S set to SML and I changed this in type to like in tree。

 and then I refactored all of this code okay， say like I did that if I did that。😡。

Because of opaque description， as long as I maintain my invariance inside my internal representation。

 I don't have to change any code anywhere else in the world， why because if I have an opaque type。

 one thing to know also about opaque types is if I have Val S equals inetta empty。😡。

If I want to do case S of Neil goes through one， I can't。 It doesn't type check。

 so I can make outside of the outside of the interface。

 I can make no assumptions about what's inside。 So that means I can refactor my code here for free。

 because I can never。I can never violate a type assumption if I change just what's inside。

 Does everyone understand what I'm saying here， like I don't have an example handy。

 but like because of this opaque description， if I change my internal library。

 it changes nothing anywhere else。😡，Does that make sense to everyone own？咁湿咁伤咁细逼。Okay， all right。

 and that's a real advantage for working in the big code base， okay okay。



![](img/09b6ec6e67293d66b339f20c32842774_38.png)

Yes。The fact that SNL modules can enforce this abstraction layer is really freaking powerful。

 although I realize like this stuff about like signatures and types is not necessarily super super new okay there are other languages that can do something similar but this idea of abstract types is really powerful because not a whole lot of languages can enforce that you can literally never break your invariance I can never produce well-typed code such that my set has two entries in it that are the same okay。

😊，All right。Any questions on that before we work in representation independence for the last 20 minutes？

Klor Savan。Either I'm motivating this well or all of you are thinking why do I care about this and you're not saying it okay。

 don't be polite all right， feedback is a gift。All right。

The last thing we're going to talk about today is something called representation independence and this is going to show up on your homework I'm pretty sure is there's a proof that has to do with this I'm just going to give you the high level conceptual idea okay。

😊，So I've said a couple times before， but this class I've trained you。

 I have conditioned your brains to be miniature EynL interpreters and some interpreters。

 you know like I don't expect you to know everything。

 but so far all of you have pretty good ENL interpreters in your brains， okay。😡。

But it's ultimately inefficient。 I've said this couple times this lecture。

 It's inefficient for me to literally run mold in in my head and then step step because I'm not gonna to be able to remember。

 Okay， I can't even， I can't even compute the sixth factorial in my head。 All right， Like。

 how am I supposed to step like the factorial implementation or the set implementation so。

One thing I've tried to dec clue you into is using invariance instead of thinking about what your code's doing instead of instead of if I wanted to do like。

😡，Fact of six。Like， yes， okay， you could very well set this to five times fact。😡，Six times past five。

And then do the whole chain of equivalences all the way down。But why when you can say， hey。

 host condition， fact 5 is equal to。😡，The factorial of five in math， and then if I do six times that。

Obviously I should get six factorial。Why do the evaluation trace when you can think about your code at the level of your invari？

😡，I'm going to do even better for you this lecture， we're not going to think about invariance。

 we're going to think about pictures。😡，so。The idea is this， right？Take this code All right。

 if I ran this code， I say insert insert， I should have used pipes。

 I would have rather used pipes and you should have rather that use pipes， by the way。

 but I I insert one inch of the set， the empty set。

 then I insert two into that and then I insert three into that okay。😡。

Your conception is you should probably end up with the set 1，2，3， and in fact。

 because of our representation， the fact that our code is correct， we do。

But which is easier to think about？

![](img/09b6ec6e67293d66b339f20c32842774_40.png)

And oh wait， Ar Well you。Which is easier to think about。Inet insert3， Inet insert， two， Inet insert。

1 in setta empty。Which is easier to think about this。Oh， shoot， okay oh wait， I think so。No。

 I think I I pushed， I pushed a patch last night， and I think I forgot to recompile。 Okay， well。

 anyways， the point is that， actually， we can we shouldn do this。 Here's what we can do。



![](img/09b6ec6e67293d66b339f20c32842774_42.png)

![](img/09b6ec6e67293d66b339f20c32842774_43.png)

We can watch the one I recorded last night。So would I rather think about this？😡，Which is by the way。

 like a wholemous board of nonsense is look at all those pre cases and okay。

 eventually we end up with3 two， one that's true Oh。

 it was because of the description that's why I forgot about that。



![](img/09b6ec6e67293d66b339f20c32842774_45.png)

Would I rather think about that， or would I rather think about this？😡，The picture。

 the picture in your head， which is that inet are empty。 You have no idea what it is。 Hey。

 but remember concepts， I'm gonna give you a little bit of trauma。

 We're going back to it because that's the notation for the empty set。 I insert 1。 I go to the set 1。

 I insert 2。 I get the set 1， comma 2。 I insert3， I get the set 1， comma 2， comma 3。

 Instead of thinking about the code， Think about the picture。

 Think about what the set is at the high level。That's what representation independence is going to do for us independently of our representation we can think about our code。

😡，It doesn't matter how the structure is implemented so long as it behaves the way I should some of you may have heard of the duck test。

 it walks like a duck， sometimes like a duck， pays taxes like a duck。

 it's probably a duck okay same thing with your sets if it behaves like a set inserts like a set removes like a set。

😡，It might as well be this picture， this picture of a set right here Okay so just think of the picture all right。

 so I'm going to define to you representation independence is where I can use a library independent of how it's represented And ideally if I have any library that's exporting an abstract type it should be representationally independent It shouldn't matter if it's lists or trees as long as it gets the job done Okay I don't care what your code's doing。

 I don't care what the data structure is I care that it's implemented in a relatively efficient way and then it's correct okay but。

😡。

![](img/09b6ec6e67293d66b339f20c32842774_47.png)

Correctness comes first。All right， so for instance。

 let's think about the difference between these two code fragments。 Okay， yeah。

 that's what I was also going to do。 So let me just do it in a here。😊。

I'm going to make it a little bit more。Simple， and I'm going to do this。

Let's think about the difference between these two pieces of code and the let's not opaquely ascribe。

 let's make it transparent。😡，What do you expect to see out of a SML when I load this into the interpreter？

Any guesses？Actually， so you shouldn't see anything because I' I didn't bind it anything。

What should you expect to see at a SMML？😡。

![](img/09b6ec6e67293d66b339f20c32842774_49.png)

I think it actually opposite， but那么。Yeah， anyways， so the point is that these are different values。😡。

Right， like these lists are different， I think that we're far enough in the course so we know that。

So what gives why do I have two different values here。

 which should be mathematically if we look at like wait well it's gone。

 but if we look at what I just did because they're representationally independent like they fall into the same。

😡，Now here's another math term for you sorry， equivalence class of values under this inset library。

 Okay， what I mean by that is these both denote the same set， they're different values。

 but why do I care Because if I'm if this were opaque right if this were opaque and these were hyphens I would literally not be able to tell which one was one comma two and which one was two comma one。

 In fact， I wouldn't even know that it's a list， it doesn't matter to me at all so。😡。

They fall into what I call representationally equivalent classes。

 these two values are the same modulo equivalentvalence under this structure。😡，好的。Yeah。

 that's why it's not in blue or that's why it's not colored yeah。

 I call it a representationally equivalent class。Yeah， thank you all right， so here's the picture。

 right？These equivalentvalence classes are themselves these big circles here。

 and I can go in between them by doing certain operations that are labeled with the edges and the mathematical set that these are meant to represent is at the top。

 so the list of singleington1 is meant to represent the singleington set of one and then one comma2 or two comma1 could represent theton or the set of one comma2 either as possible。

😡，And then same with this right and there's a few more but they can't they don't fit right but all that matters is that if you are in any one of these buckets and I take one of these edges。

 I do an insert or a remover or whatever I will go between the classes I don't care what specific value I have as long as it's between these classes。

😡，And that's kind of the conceptual idea， which is that we are partitioning our values into classes of what I'll call like like observable behavior。

 right？😡，Do does everyone understand what I mean when I say like everything in this bucket。

 all these values？😡，Behave the same。If they were to be opaquely ascribed like behind the curtain behind the wizard right all these behave the same right so it doesn't matter at all I'm just going between classes that are the same and then I can also get out concrete things that are not just sets I can get out false and true if I did like inet M2 on the singleton list of one or the singleton set of one or so on and so forth all these examples you can read through okay does this diagram make sense for everyone。

😡，And there's like infinitely many nodes and edges are missing， okay。

 but I didn't have space for that and they didn't have time。😡，Okay。

 so theyre equivalence classes of observable behavior when I okay and another thing I wanted to say is like this kind of means that you can define a relation。

 you can define like a mathematical relation like relating to values like takes them into lists and that gives out a true false okay and all of these things in here are related because they must behave the same。

😡，The point I'm trying to get across here is that representation independence is good for your conceptual thinking。

 it's also good because you can prove that these classes exist， you can prove that we can never。

 ever ever get two values like this that are behaved differently。😡，嘅。嗯 ok。

But we can generalize this idea It's not specific to sets or in lists What if I had represented an in with trees。

 well let's do it， Okay， so I'm going to write up the trees and remember that trees is long and nonsense。

 so I'm going to abbreviate node as n and then empty as E okay。😡，But the diagram looks the same。

Doesn't it so instead of if I had implemented in set with trees， I would have that。😡。

This is the singleton set of one， and then these are the possible singleton sets of one comma 2。

 and then the possible sets of one comma 2 comma 3 in this tree representation。😡。

But if I go between using the arrows which are not labeled anymore。

 but the same as what they used to be， because I didn't have space。😡，It's the same idea。

 So what I'm trying to say is think up here。😡，Not down here。And when we use our type system。

 when we use aPque description， people are forced to think up here。😡。

It doesnn't matter what your representation is。😡，I can give so far as to say， well。

 if these diagrams are the same， here's the real cool thing。😡。

The most important idea is that we can use representational equivalent classes to prove that two different implementations。

😡，A mathematically equivalent as an I can prove to you that if I implemented ins sets with lists and I implemented ins set with trees。

 I can prove to you that no sequence of operations can ever produce differing behavior I can never I don't ever get a divergence in behavior because I maintain my imvariance and if I had the code for both I can prove it to you and you will prove this about something also sets I think yeah also sets probably with a different representation。

😡，So it doesn't matter whether or not the values came from the same structure。

 but we can think of the picture as still having these equivalent classes and here's why I'm going to use a bunch of pictures or a bunch of colors again。

 boom。😡，So I can have the picture but up here in the green I've got the trees and down here in the blue I've got the lists and the idea is that I can relate values from this implementation。

 the trees to this implementation the lists and I can relate them in a way that I can prove that I only ever end up in these buckets and all observable behavior from like mem or other functions must must be consistent with that I always get the picture okay。

😡，And that's kind of the ultimate way of proving that like something is correct because I can start from my inset with lists and I can make it even more efficient or hard to understand implementation。

 but as long as I have my representational independence proof。

 as long as I prove that they go into the same buckets，😡。

Then it doesn't matter they work it works as it should okay and that's the proof that you're going to do on your homework a little bit so formally let me say that the relation is R that takes into S1 and S2 in green and blue such that S1 is of type inset list do T assume that I had inset list and inset tree as like two structures where I implemented the same signature and then S2 is a value of inset tree do T。

😡，And I want to prove that the relation is preserved by all operations in the signature if I start from the empty case。

 okay， no matter what I do， I'm always going to preserve the signature。😡。

And so to give you an example， for instance， if I had one comea two。And then I had。Note。Of node。

Of empty， I'm going to write this out time。Don't have anything else better to do with my time。

To come empty， if I write out these two values。😡，I can show that these are related by R。Oops。

These are related by R。😡，And I can show that no matter what I do， if I insert to both。

 if I do an insertion of three。😡，To both。three and these would be different insert functions it would be the list insert function here and the tree insert function here I can prove that the outputs are still related。

Whateverever the result would be。And then I can prove that no matter what happens。

 I always get the relation preserving and because the relation preserving is preserved Mem whoops mem is going to give the same output no matter what I do as long as they're related so like mem of two is going to give me true here it's going to be true here and it's also going to give me false if I do mem of three on both okay that's the idea of the representational representation independence proof。

😡，睇。😊，If you don't think this is important to know， it will be when it shows up on your homework。

 I'm just trying to give you like kind of a conceptual idea of what you're going to be proven。

Any questions about representation independence which is。

Not strictly to do with like the software part， but it has to do with how we are assured that our code is correct。

No questions， okay。I have to go here because I don't have a pointer anymore。so。

I want to finish off the lecture by saying like it might seem like this is not necessarily practical。

 I understand you want to get back to the hops and the CP I know you love CP and you want to write some code。

 you don't want to organize your code organizing code is for suckers okay I write the cool functions I don't have to maintain it if you're a software engineer by the way。

 that's not true okay you're gonna remember I spend 99% of my I spend 95% of my day at my desk thinking I spend5% of it coding okay。

This is an extremely essential part and it has a lot of practical applications。

 even though in other languages， they don't have modules because they have stuff that's similar and they have interfaces。

 this idea of interface and implementation is global。

 no matter what language you go to no matter what software you're working with。

 it's going to be a thing。😡。

![](img/09b6ec6e67293d66b339f20c32842774_51.png)

And then abstract types are really cool like this this idea of having representation independence and opaque types that you have no idea what they are is really powerful because it stops you from ever breaking your own invariance in two lectures we're going to see a really powerful use case where we can write an abstract type of self-balancing binary trees that we can never。

 ever， ever mess up。😡，And it is impossible to produce the value of that self balancing binary tree that is not balanced and not a BSG okay it's going going to be called red black trees all right so again。

😡，Seft defense against yourself， maintain your invariance for yourself so you can maintain your invariance for people using your code for your manager。

 Okay， in like three years。 right， That's all you need。 We finished early。Thank you so much。

