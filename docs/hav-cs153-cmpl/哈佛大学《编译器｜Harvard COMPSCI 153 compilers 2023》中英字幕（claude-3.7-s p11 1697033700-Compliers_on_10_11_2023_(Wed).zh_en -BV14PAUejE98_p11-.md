# 哈佛大学《编译器｜Harvard COMPSCI 153 compilers 2023》中英字幕（claude-3.7-s p11 1697033700-Compliers_on_10_11_2023_(Wed).zh_en -BV14PAUejE98_p11-

Who look forward is coming out。Monday， October 16， so on Monday。

Homework 3 is of course allowed and not due for a week later。 so there is this week overlap。

 I will be matching up study groups for homework 4 over the weekend。

You've had hopefully had a chance to participate in。At least two study groups。

 I appreciate that the study groups have been of varying levels of engagement。

What I'd like you to do is if your availability or your desire to take part in study group has changed。

 please fill in that same study group survey by the end of Friday and over the weekend I will announce。

I will announce study groups for homework4， hopefully with availability it allows you all to meet。😊。

Homework 4 is the last homework that I'll be actively doing the study group matching。

 and hopefully it's given everyone a chance to meet a few new people in the class and to maybe figure out what works and doesn't work for them for study groups。

 there are two more assignments， two more homeworks homework 5 and homework six， but I'll。

Either allow you to form your own study groups or let you opt in for another matching round。

So of them blathering so you had a chance to。

![](img/d73b5033a85de535920e9a4ef1e84ad7_1.png)

Give the QR code for those who want to update their availability。Change there。

We change whetherer they often。Any questions at the moment about the homeworks into the admin side。

 study groups。 What will homework 4 be focused on， We'll touch on it more Monday when we hand it out。

 but you'll be compiling from a C like language down into L O VM。

And so part of what's going to be you'll be doing is parsing。

 rather setting up the lecture and the PAer generator to pass things in。

 that's what we're in the middle of at the moment。And that's Monday。 that's when it gets handed out。

 And then the other stuff about compiling from a C like language into LLVM。

 we've actually covered a lot of it， you know， compiling of data structures， you know。

 how to think about those representation of data structures， how to think about functions and so on。

😊，So yeah the language is untypeped， and then in homework 5 we'll be essentially extending that high level language to include types。

Yeah。By the end of the course， you will have covered pretty much all parts of the compiler pipeline。

Any other questions of the moment？Okay。So。Last class we look we started looking at the syntactic analysis phase of pasing。

And we looked at。Recursive descent passes。诶。Today， we're going to be looking at another kind of top down paring approach。

To get there though， let me。Talk a little bit about the。Handwritten PAser that we used。

 This was a recursive descent PAser written in a higher orderal language， written a no camel。

 And essentially， the approach taken is known as PAsa combinators。

The idea is that we would have these PAser objects。

 something that would recognize a non terminalal grammar， and we were able to compose them together。

 so for example， the out constructor said recognizeogni a string using either P1 or P2。

Now you can go and look at the code for that， but one of the high level ideas was that our PAser essentially exhaustively tried all possibilities。

 So given out P1 P2， it would take in the sequence of tokens， it would attempt PAse that using P1。

 this would produce the PAser it was able to do plus any remaining tokens it wasn't able to do。

Then it would try using P2 on that same sequence of tokens。

So what we were doing was building up all possible pars。 And then at the end of it。

 we were going to take the pars that were able to consume all of the tokens。

 that is that had no tokens left。So this is clearly inefficient， it's not great。Ideally。

 what we'd like to do is somehow。Magically know which production to use。 So if we had an alternation。

 P1 or P2， we would somehow know， for this input， I want to use P1 to successfully passse it on another string and another sequence of tokens magically know that we wanted to use P2。

😊，This is the core idea。Of LLK passingsing。What's going happen is we're gonna look at the next K symbols。

 the next K tokens in our input stream。And based on that。

 we're going to predict whether we want to use。P1 or P2。

 That is which production we want to use to pars。诶。To pause this。The string。

So really the key question then is how do we do this？How do we predict。

Which production we're going to use？What we're going to be doing for the rest of the class is essentially working through the concepts。

And an extended example。This shows how given a grammar。We can。Analyze that grammar。

And come up with what's called a passingsing prediction table。

And essentially what that piesing prediction tables say is given the next K tokens。

And given that I'm trying to par this non terminalal。Which production should I use？Okay。

 so that's where we're going to by the end of the class to get there。

 I'm going to have to introduce a few concepts the way。

 and we'll see how these concepts fit together to let us build this passings prediction table。

Any questions at the moment。On where we are and where we're going。O。

So the first notion I want to introduce is the idea of first sets。

 So if we have gamma being a string of terminal and non terminal symbols。

 so that is the thing on the right hand side of a production。

First of gamma is going to be the set of all terminal symbols。

They can start a string derived from gamma。So let's make this clear with an example。呃。

Here's the grammar。For arithmetic expressions。This was factored or organized in a way to get the right precedentnce of operators。

So that multiplication and division would bind tighter than addition and subtraction。

And this was also the result of factoring the grammar so that we didn't have any left recursion。

Which， if you remember， was problematic for our recursive descent PAza。Okay， so let's take a look at。

诶。The right hand side of this production， F T prime。 So this is our gamma。

 a sequence of terminals and non terminals。 In this case， two non terminals， F and T prime。

And the idea is， what are the。Terminal symbols。That could be produced。

There could be the first terminal symbol produced by this。Well， clearly it's going to be。

The first terminal symbol produced by F。A factor， which is going to be either an identifier。

 a number or an open parentthesis。 Okay， and that's what we have here。

 First of F T prime is I D nu left parent。The， the high level idea。

Is that we can use these first sets to determine which production to use。Okay。

 so if we have a non terminal X and we have all of its productions。

All the productions with X on the left hand side， gamma 1， gamma 2 up to gamma in。

Let's take a look at first of gamma 1， first of gamma 2， first of。All of these things up to gamma in。

Now， if those sets are disjoint。What that means is。Looking at the next。

Terminal symbol that we want to pause。Would tell us exactly which production to use。That is。

 if the production gamma 1。If the first sample for that is ID。

And ID isn't in the first set of any of the other productions。

Then we know that if the next symbol is an ID。We get to use this first production， X goes to gamma1。

Does this high level idea make sense？Any concerns？Abe。What if what's right？

If they're not all disjoin。Then the next character won't tell us。

Which production we need to use It might tell us a smaller set。

 but it won't tell us here's the exact production you need to use。

And we're going to go into more detail on this。 but it turns out that if that is not justjoint。

 then the grammar is not plaable using this LLK technique。So not all grammars will actually work。

Using this technique。Thanks for the question。How didt find is that first set？

We are going to go through in detail about how we compute these first sets。 Well。

 not really in detail。 We're going to wave our hands a bit。

So just double checking are the T or the T prime some here that works they are terminals。

So in this grammar， E， T， F， E prime， T prime， those are all non terminals。

This was a result of factoring arithmetic， sorry。Putting a arithmetic expressions in a form that the non terminals enforce the precedentnce of operators。

 E stands expression T for term F for factor。 So the star and slashs terminal Yeah。

 so the the terminals are the terminal symbols up。Plus。マイナ。Star slash， ID， nu， open Peren。

 closed Peren。Yeah， because most of them punctuation。

 it's kind of hard to see the font that I'm using there。

 but it is typewriter a font for all the terminal symbols and。

Those arealicized capital letters for non terminals。Thanks。Yes， for example。

 would the first corresponding to that be the multiplication and division？I'm sorry。

 Could you repeat the question first example， prime So what is the first set of T prime？ Yes。

 first of T prime would be。Well， this production here， and it starts with。A terminal star。

This production starts with a terminal slash， this one is null。

 so first of T prime is star and slash。We're actually going work through an example to see this's。

Think about how we compute these first sets。And we see it。How it plays out。

 you can check the appel textbook for the actual algorithm。But hopefully， the intuition is。

Going to be clear。Suppose that we have a sequence of non terminals， X， Y， Z。



![](img/d73b5033a85de535920e9a4ef1e84ad7_3.png)

How do we compute first to x Y Z？嗯。Do we does it work if we just know first of x， right？ So clearly。

 first of X， a terminal that can start。Tminal symbol whether that can be at the string produced by X derived from X。

 that's clearly going to be part of first X， Y Z。But could it include other things？Nods。

 what are the cases where？Or it might include more than just first X。Effx can produce no， right。

 effectsx can derive the empty string。If that's the case， then。We might also need to consider。

 first of why。Right， if X produce the empty string。

 then the first terminal symbol that we can produce is also going to be。

The first terminal symbol that X， Y， Z can produce。Right。

 so affecting the derive of the empty string， first of way is going to be。A subset of first XY Z。

And similarly， if Y can derive the empty string， then first of Z is going to be a subset of first of xY Z。

Okay， so what this means is that in order to compute these first sets。

 we're also gonna need to be able to compute whether or not a non terminal can produce null。

 That's whether a non terminal is nullable。Okay。It turns out that we're also going need to compute something called the follow set。

And we'll see how that plays out。 But the follow set of X is。

The set of terminals that can immediately follow。A string produced by X。So to be more precise。

 a terminal T is in follow X。 if there's a derivation that contains X T。

RightSo remember a derivation is a sequence where we'd start with S， the start symbol of the grammar。

 At each step， we replace a non terminal with the right hand side of one of the productions for that non terminalal。

ItDoesn't matter which order we do those replacements。

 And so if there is some derivation that contains X T， that means that T is going to be a symbol。

 a terminal symbol following whatever X can derive。Okay。

So the way that our algorithm works is we're going to。Start building up these sets。 first。

 nullable and follow。Adding in。Terminals into each of these， and。Keep on iterating。

If we add something into。A first set we that might propagate into some other first sets as well。

 We keep on going until we can't make any more changes until a fixed point is reached as the terminology。

嗯。And as I mentioned，The basic idea is that we need to know。

Nllable of X and first of X for all non terminals。 If we know that。

 then we can easily compute nullable of gamma and first of gamma for any string gamma of terminals and non terminals。

Okay， so let's work through an example computing these things nullable first and follow。

 We're going to do it for the grammar that we saw previously for ametic expressions。

 here we have a start symbol S， which is going to consist of an expression followed by the terminal symbol。

 EOF end of feed or end of file， and that's just kind of there this is sometimes used to explicitly indicate the said that we've consumed all over the input。

Right， so EOF will be a terminal that's inserted at the end of the file。Okay。

 so let's start off with。Nllable。 And just to remind you， a non terminalminal X is nullable。

 if there's a production。X arrow gamma， will either gamma is empty。

Or gamma consists of non terminals， all of which are nullable。去。So呃。Which non terminals are nullable？

Feel free to yell him out。结婚。T prime。Yep， T prime here。

 we have a production that produces the empty strings， so T prime is definitely nullable。S。

Yes is actually not。S is not， we don't know about E yet， whether E is noable， but S。

 the only production has this terminal symbol in here， EOF。



![](img/d73b5033a85de535920e9a4ef1e84ad7_5.png)

So what that means is anything we can produce by yes is going to include that EOF terminal symbol。

So yeah， so it turns out S is not going to be nullable。It takes a while to wrap your head around。

 I think， why I'm walking through it in slow steps。 So T prime and E prime are nullable。

I'm indicating that with this top symbol。嗯。That looks like a capital T。嗯。

And it turns out that after that， we are actually done。There are。No more。Nullable non terminalals。

Right。嗯。We can convince ourselves that this is true。

By say looking at F and realizing K of the productions for F are going to produce at least one terminal。

That means that T is going to produce at least one terminal。Because it contains an F。

 which means that E is always going to produce at least one terminal because the only production for it contains a T and so on。

😊，But really all we needed to do was just iterate。

![](img/d73b5033a85de535920e9a4ef1e84ad7_7.png)

诶。Until we can't make any more changes。 So that is non terminal is nullable if。There a reduction。

X goes to gamma where gamma is the empty string。Or if there's a string where it consistently of nonterminals that are nullable。

 we kind of just keep on going following those two rules until we can't make any more changes and anything left is going to be not nullable。

 which I've indicated using the bottom symbol， which is sometimes used as an abbreviation for false。

Okay any questions about computing nullable of the non terminals in the grammar？O。

So let's start building up the first sets。So given a production。

X goes to T gamma where t is a terminal symbol。Then T is going to be in the first set of gamma。

 sorry， in the first set of X。So。Let's take a look at starting from the top。

The first production we have that has a terminal is the first symbol is this E prime goes to plus TE prime。

E prime goes to minus T E prime， so plus and minus are in the first set of E prime。

What's in the first set of T prime？不了。It's just times and slash Time and slash。 fantastic。

 What about if， feel free to just scroll it out。😊，I d。Thank you，80 N open Paren， right。

 the first terminal symbol of each of these three productions， awesomewe。Okay。

 so that's kind of the first case。 If we have a production that begins with a non terminal。

Sorry with a terminal symbol that terminal symbolism first。

Here's another pattern for us if X has a production。😡，Gmma Y sigma。If gamma is nullable。

Then the first of Y has to be included in the first of x。So what's the situation。

 What's the production that would match that。

![](img/d73b5033a85de535920e9a4ef1e84ad7_9.png)

I should add that。This includes gamma being the empty sequence。Right。

 so if camera is the empty sequence of。Tminals and non terminals then it iselllible。不 name。Sorry。

 I'm not sure if I understand。We're saying that when you。Write this D Y Sigma。

We're trying to say that。In this case， sta would have to be incredibly cheaper。

So what we're trying to do is we're going to go look at this list of productions in our grammar。

And we're going to see if。It matches this pattern。That is。Can we instantiate x。

 gamma Y and sigma so that x and Y are non terminals。

Yamma is some possibly empty sequence of terminals and non terminals。

And Sigma is also some possibly empty sequence of terminals and non terminals。Let me。

I think I saw a hand Turk did you raise。嗯。Did that answer help， or do you have another question。

 I'm just trying to find the answers yes， okay。Let's。Let's tell you what。

 let's take a look at this production。For， for a terminal。Sorry， this production T goes to F T prime。

So this actually matches the pattern。Where for x， we're gonna use T。Gmma。

We're going to use the empty sequence。喂。Is going to be if。

And Sigma is going to be the sequence consisting of this。Single non terminalminal T prime。

So what this is is。If。Gamma， the empty sequence of non terminalminals is nullable。 Yes， it is。Then。

 first of。If is a subset of first of T。So first of F is8 nu open printen。

And that means we're going to copy。First of that。We add everything in first of F into first of T。

So that is another way to think about it without thinking about this pattern。Is。Hey， if I have an F。

 then the first terminal that could be produced is A， nu or open Preen。Hey， look。

This production for T starts off with the non termm left。

 So anything that F can derive can be at the beginning of whatever T can derive。

And so since the first symbol of F is 8 numb open print， that's going be。

A subset of the first symbols of tea。In a similar way。Let's take a look at the production。For。E。

E goes to T E prime。In that case。Anything in first of tea。It's also going to be in first of E。Right。

 since the first terminal symbol that a tea can produce。

It's also going to be going to be the first terminal symbol that an E can produce。

 So we're going to copy first of T。ID numb， open print。Into first of V。In a similar way。

 if we look at this production for S， S goes to E。Into file。Well。

 anything in first of V is going to be contained in first of S。So we're also going to copy ID nu。

With Perin。The idea， sorry， Nicholas know。How do we know the order This good question turns out that the order doesn't actually matter's what you can really be thinking of this as is we are going over every production we're trying all possible ways of matching this pattern of choosing X gamma Y and sigma so that it matches one of these productions。

😊，And then checking， hey， if gam is nullable， then the first set of Y has to be included in the first set of X。

And we just keep on going over and over and over。Until we can't make any more changes。

So what that mean is the order doesn't matter。All right。

 we're actually going to reach the same answer。No matter what。Yeah。

 we might be able to reach it more efficiently on some orders， but for our purposes。

The key idea of the algorithm is just keep on going until you can't make any more changes。

Until we reach out the terminal。terminals。嗯。I'm not sure to describe it as a depth first search because I'm not sure what the。

Graphs that you're exploring， but a reasonable way to implement this would be to go over every production。

And then start with gamma being the empty sequence。 then the first element of。嗯。

The first element of the right hand side of production， then the first two。

 the first three and so on until you reach a point where gamma can't be nullable。

 if gamma can't be nullable， then anything you add onto it can't be nullable。

So that would be a way to make sure that you're covering all the possible cases。

Any other questions for the moment？Okay。At this point。We've computed nullable。

 and we've computed first。What we need to do is compute follow。And the yeah， William question。

 how do we know when we were done with race？We're done with first when we can't make any more changes。

 So remember， we had kind of these two。Rules， if you will， The one about。Hey， if x goes to T gamma。

 then T is in the first of x。 And then this one of x goes to yamma Y sigma。And gamma is nullable。

 then first of Y is a subset of first of X。With those two rules。

 we just kind of look at all the ways we could match those rules to the productions and they kind of tell us what elements we should add into the first sets。

 We keep on doing that until we can't add anything new。Right。Co。And once we have done that。

 we know that the first set is。We found the smallest possible solution。

 the least fixed point for those who are taken 152 more advanced mathematics courses。Okay。

 so the next thing we're going to do is compute the follow sets。So remember。诶。

The idea of a follow set was。诶。A terminal is in the follow set of a non terminal。If there's。

 if that terminal can。Occur immediately after a string produced by the non terminal。So for example。

As we're going to end up seeing， E OF is going to be in the follow。Set of E。

Because whatever E can drive？Any EOF can come immediately after it。In a similar way。Look here。

 we've got an E prime。Can produce a plus。Right， so E prime could end up producing a string that begins with a plus。

 And that comes immediately after a T。 So plus is going to be in the follow set of T。

And that's the key idea for our rule for computing， follow sets。What we're going to do is。

Try and find。A production。嗯。Of the form X goes to gamma， Z， Delta Sigma。O， okay。

So there's a lot of letters in here。 But the basic idea is that we'll go through each production and see if we can pick X。

 gamma， Z， Delta and sigma。😊，Instantiate those meta variables so that they match the actual production。

And then。The first set of Delta。Is going to be contained in the follow set of Z。

Because there could be a derivation where Z is going to produce something followed by Delta。

 So whatever is in the first set of Delta。Could could immediately follow whatever string we produce from Z。

So。To see an example of that。Like we saw previously， here we have the production S goes to E EOF。

So here we're instantiating。X to be the non terminalminal S。Gamma is the empty string。

Z is going to be the non terminal E。😡，And then Delta is going to be this。Terminal symbol， E OF。

Sga is going to be empty。So what that means is。EOF。Is going to be in the follow set of E。

In a similar way。Like we talked about。In the follow set of T is going to be the first symbols of E prime。

Right， so plus and minus。Are the first symbols of E prime。

 and they're going to be in the follow set of T because of this production， Es to T E prime。

And what about what's in the follow set of F？Let's look at this production。

And tell me what's going to be in the follow set of F。Marriio。And start。TheSt on the slash， right。

We have this F。Immediately followed by a T prime and the first set of T prime is star and slash。



![](img/d73b5033a85de535920e9a4ef1e84ad7_11.png)

So that's going to be in the follow set of F。Let's see。Using this instantiation， are there any other。

And just like before， what we're going to do is keep on iterating until we can't make any more changes。

But can you see another instantiation of this rule？That would allow us to add。

Increase the followsit of something Abe。Final derivation for。UseGma。Right。Right。

 so down here this last production F goes to open print E closed print。Right， so we could。

 as Abe said， we could instantiate gamma to be open print。

The non terminal that we're interested in is E。And then sigma can be instantiateated to be closed parent。

Right，And so what that means is， yeah， that's right。 Close per can follow a derivation of E。

The first of closed peran has to be included in the follow set of E。So we can add that right there。

Close printer is in the follow set of E。You can and you should look at this a little while longer。

But there's no more。Instances of this first rule that。

Will let us add anything else to the follow set。We do， however。Need to consider some other cases。So。

If we can find an instantiation where deelta is nullable。

Then we need to think about the first set of。Of sigma。Turns out that we don't actually have any。

Incentiations of that in this grammar。So we can move on to this last case。

If everything following are non terminalal Z， so Delta sigma is nullable。Then what that means is。

Anything that is in the follow set of x。Has to be in the follow set of Z。

Theres any symbol that could come immediately after。

A string derived from X might appear immediately after。The string derive， a string derived from Z。

 because sigma。Sorry， because deelin and Sigma might end up producing the empty string。

Does that intuitively make sense。To people。Okay， so what's an instantiation of it？Bden。

Since E prime is nullable， everything that follows E should also follow T Great。

 since E prime is nullable。Anything that follows E might also follow T。嗯。Butプ。So one might follow E？

E with。Close per end， we need to add that to the follow set of T。So we do that。

 we add EOW and close print to the follow set of T。嗯。What else？要我什么呃限定7分。

Same thing with T prime F T prime T prime。Let me see what I actually ended up doing。

Let's take a look at this production first。 you are correct。

 but just because the I can't dynamically change the order of my animations。

Let's take a look at this production。So， this is。Here we're actually instantiating。

 Let's think about E prime in here。诶。呃。Whatever' is in the follow set of E。

Also has to be in the follow set of E prime。Okay， so the follow set of E。

EOF closed print also has to be the follow set of E prime。



![](img/d73b5033a85de535920e9a4ef1e84ad7_13.png)

So copy that over。Let's see。Let's look at。This rule， this production T goes to FT prime。呃。

Here T prime is。Nllable。All right， we know that from our。Computing the nuable set。

So that means anything in the follow set of T。Has to be in the follow set of F。

So the follow set of t is plus minus EF close per n。We're going to add that to the follow set of F。

Foler set of efforts now includes all of this。let's see what else？

I feel like I should have added more animations， currently looking at my next slide and trying to figure out reverse the engineer what production we're actually looking at。

Okay。

![](img/d73b5033a85de535920e9a4ef1e84ad7_15.png)

Take a look at this production， and tell me。How we should modify。Out table。Yeah。系。

Nothing follows key prime， so everything in。Great， thanks， Maxwell， so。

Everything in the follow set of T has to be in the follow set of T prime。Great。

 follow set of t plus minus EOF closed pren that's going to be in the follow set of T prime plus minus EF closed pren。



![](img/d73b5033a85de535920e9a4ef1e84ad7_17.png)

Great。

![](img/d73b5033a85de535920e9a4ef1e84ad7_19.png)

Again， we can keep on going over this table。Looking for instants。

 versus looking to see ways that we could increase the follow sets of any of these non terminals。

But it turns out that this is the fixed point， right， It turns out that these are。



![](img/d73b5033a85de535920e9a4ef1e84ad7_21.png)

This is stable， right， There's no more terminal new terminal symbols to add to the follow set。



![](img/d73b5033a85de535920e9a4ef1e84ad7_23.png)

Once we have this。Yeah， so I think this is questions。

Why can't you flip the subset in this commission in the sense of the intuitive explanation that？

RightIf Delta sigma could be the empty strain， anything you can put after x。

 you can also put after Z， why can't you do the opposite anything you put after Z you can also put after？

You may have a production。That on the right hand side， let's say。

 has Z followed by a terminal symbol。嗯。Foo。Okay。So there， who will be in the follow set of Z。

It appears that is there is a derivation where you can have Z followed by food。However。

 that Z may not be occurring。In the derivation of an x。 so what that means is that。

There might be things in the follow set of Z that we know cannot be in the follow set of X。Okay。

 now it's going to be。Sound to add it in。To add that rule。

 And it's just that it's not going to be very。You， you will lose precision。

 So your set might be bigger than it has to be。 And I would say that these sets are approximations。

 right， They're kind of well what could follow。Right。Oh。

 so these are not all the things that can bother them。Let me think about this a little more。

These are precise。 there will be a derivation。嗯。That satisfies these things。

So this computation is precise。 It turns out the way we're going to use them。

 it's okay if they're over approximate。嗯。But we don't want to introduce that unless we have to。K。ok。

All right。So， we have。At this point， we've computed nullable first and follow for all of the non terminals。

Great。Remember， though， that our goal。Is to be able to automatically figure out。

Which production we want to use based on the next symbol that we see？So to get that。

 what we're gonna do is make a predictive parsing table。

The idea of this table is we're going to have。The rows of the table are going to be non terminals。

And the columns are going to be terminals。The entries in the table are going to be production。

And the basic idea， the way we're going to use this predictive passings table is if we're wanting to parse the non terminalminal X。

And the next token is tea。😡，We're going to look up row X and column T。

And that's going to tell us which production we want to use。So let's see an example of this。

 Let's go through with。The grammar we know very well now。

And we're going to be using the results of our nullable first and follow analysis we've put up there in the right hand。

 top right hand corner of the screen。And we're gonna fill in。This。Pasing prediction table。

 So you see that the rows are all of the non terminals。The columns。A role of the terminal symbols。

We're going to start filling this table in。And the key idea is if we have a production。

 X goes to gamma。We're going to add that production X to Gamma。To row x for any column T。

Where tea is in the first set of gamma。So what that means is， hey， I'm trying to pass an X。

 and the first symbol is T。😊，Whoa， that first symbol could have been produced by gamma。

So this seems like a good production to use。Okay， let's side on that。Let's take a look at S。Okay。

 so the first set here a production S goes to E EOF。And。The first set of。

EEOF is going to be ID nu open peren。So we're going to add that production into ID。Into numb。

And into open Peren。Okay， so what this is going to tell us is， hey。

 if you're trying to pass an S and the first thing you see is an I D。You should use this production。

Okay， what about for E， the seconder row of the table？



![](img/d73b5033a85de535920e9a4ef1e84ad7_25.png)

So let's take a look， we have a production， just one production for egos to TE prime。

We want to look at the first of TE prime。

![](img/d73b5033a85de535920e9a4ef1e84ad7_27.png)

That is the first of T。Which is going to be ID nu。Open print。

So what that means is we're going to add this production， e goes to TE prime for ID。Nan。Open per in。



![](img/d73b5033a85de535920e9a4ef1e84ad7_29.png)

All right。What about。This production E prime goes to plus T E prime。



![](img/d73b5033a85de535920e9a4ef1e84ad7_31.png)

What's the first set of plus TE prime？

![](img/d73b5033a85de535920e9a4ef1e84ad7_33.png)

![](img/d73b5033a85de535920e9a4ef1e84ad7_34.png)

Just call it out。Plus， right， the first terminal that can be produced by the sequence plus T E prime is plus。

 So we're going to add that production into this column right here。Row E prime column plus。

Similarly for the next production。E prime goes to minus T E prime。

First of minus T E prime is the minus symbol。So we add in that production there。

Let's go on to the next row， T。

![](img/d73b5033a85de535920e9a4ef1e84ad7_36.png)

There's only one production。 T goes to F T prime。 first of F T prime is。First of F。AD nu open print。

 so we're going to add in that production into AD nu Open print。



![](img/d73b5033a85de535920e9a4ef1e84ad7_38.png)

Let's go through the three productions。For T prime。嗯。First of star F T prime is star。

 So into this column into this column for star for the R T prime， we're going to add that production。



![](img/d73b5033a85de535920e9a4ef1e84ad7_40.png)

![](img/d73b5033a85de535920e9a4ef1e84ad7_41.png)

And similarly， for the next production， for the slash， the division symbol。

The next production T prime goes to empty string。嗯。Doesn't actually apply。



![](img/d73b5033a85de535920e9a4ef1e84ad7_43.png)

For this rule， we'll see what happens for that rule later。



![](img/d73b5033a85de535920e9a4ef1e84ad7_45.png)

All right， so F。Tell me what I should do for this production if goes to I D。I see you hand， William。

 thank you。See if anyone else wants to call it up。

![](img/d73b5033a85de535920e9a4ef1e84ad7_47.png)

It's just that to ID。Right， so what， what row， which column， row Great Last row first column。

 So the row for F column for a D， I'm going to add that production。



![](img/d73b5033a85de535920e9a4ef1e84ad7_49.png)

Hey， and that kind of makes sense， right， If I'm trying to pass an F and the next terminal symbol is an I D。

 let's use the F goes to I D production。 Same for F goes to nu。



![](img/d73b5033a85de535920e9a4ef1e84ad7_51.png)

The first of none is numb。 So we use that production。 And same for the last one。

 the first of open print E close print as open print。 So we're going add。

That production and that column。

![](img/d73b5033a85de535920e9a4ef1e84ad7_53.png)

Awesome。We're not quite done。This was kind of the easiest case， right。

 If the we look at the first symbols on the right hand side of the production and use that to fill in。

The table。There's actually。The interesting case for a production where gamma is nullable。 So。

 for example， Epre goes to the empty string。E prime is nullable。嗯。Oh， sorry。

 this right hand side is nullable。We want to take a look and what's in the follow set for X。

And if we see。For any terminal in the follow set， we want to add this production into that column。So。

 for example， E prime goes to。Epsilon goes to the empty string， is that right hand side is nullable。

So let's take a look at the follow set for E prime。It's EOF and close per in。

So what that means is in the column for EOF and close per in。



![](img/d73b5033a85de535920e9a4ef1e84ad7_55.png)

Right here， I want to add that production。So here's the way to think about it。

If we're trying to pause an E prime。Which intuitively is either adding or subtracting another term。

 plus or minus。And I see either the end of file or a close per in。

Then I know that there's no more plus and minus terms to pause。So I want to use this。

 E prime goes to empty string production。 I haven't got an E prime to pass。

Or any tokens to consume for this E prime？

![](img/d73b5033a85de535920e9a4ef1e84ad7_57.png)

What else do we have？Oh similar production for T prime， right？So T prime can go to the empty string。



![](img/d73b5033a85de535920e9a4ef1e84ad7_59.png)

So anything in the follow set of T prime， we want to add to that production follow set of T prime plus minus EOF closed pre。

 so down here in the row for T prime。In the appropriate columns， we're going to add。



![](img/d73b5033a85de535920e9a4ef1e84ad7_61.png)

Their production T prime goes to M string for plus。For minus。Close brand。



![](img/d73b5033a85de535920e9a4ef1e84ad7_63.png)

E with。呃。Have we got it all？

![](img/d73b5033a85de535920e9a4ef1e84ad7_65.png)

I believe we have it all。O。Great。So we built the predictive passing table by following those two rules by looking at the first sets and the follow sets。

 adding productions in here。Is at the end of that process。

Every cell on this table contains at most one production。This is awesome， right。

 That means that this predictive passing table will tell us exactly which production we want to use。

😊，that is pausing is going to be predictive right simply by looking at the next symbol。

 it tells us which production we want to use。😊。

![](img/d73b5033a85de535920e9a4ef1e84ad7_67.png)

![](img/d73b5033a85de535920e9a4ef1e84ad7_68.png)

Let's see how that actually works。Okay， so let's suppose that we have our sequence that we want to par。

 This is an expression， open pre2 plus 7 closed pre followed by the end of file。

 This is the entire thing we want to par。I'm going to use this arrow to indicate what is the next token。

 right， the next terminal symbol that we want to par in our sequence。

 So we're starting off wanting to pass that open parent。On the left hand side。

 I'm going to show the derivation。That we're going to be using。 So we're going start off with。S。

 the start symbol for the grammar。Okay， so we want to pass an S。The next token is open Preen。

So we look up our table。 I'm wanting to pass an S。 The token is open pren。 So the pars。

Prouction table tells us that we want to use this production S goes to EEOF。Awesome。

So in our derivation， we're going to replace S with EEOF。Fantastic。Now。

 what we're want to do is PARS and E。And。The next symbol is still this。Open peren。

So we look up in the table， row E column open peren。 Here's the production we want to use。

 Es to T E prime。

![](img/d73b5033a85de535920e9a4ef1e84ad7_70.png)

So in our derivation， we're going to replace E。

![](img/d73b5033a85de535920e9a4ef1e84ad7_72.png)

With the right hand side of the production， T E prime。Right， we replaced E。With a TE prime。Awesome。

Next step。We're wanting to pass a T。 The next symbol is open per N。 We look it up in the table。

Here's the production we want to use。 T goes to FT prime。So we replace T with FT prime。



![](img/d73b5033a85de535920e9a4ef1e84ad7_74.png)

Okay， we're doing a lot of work， we haven't actually passed into token yet， don't worry。

 we'll get there。😊，What we're trying to do at the moment is pars and F。



![](img/d73b5033a85de535920e9a4ef1e84ad7_76.png)

And the next symbol is open printen。We go to the table， we look up row F， symbol open Peren。

 this tells us use the production， F goes to OpenPen E close Peren。😊，Awesome。😊。

So we replaced that in the derivation。Now you see in our derivation。

This leftmost symbol is open printen。

![](img/d73b5033a85de535920e9a4ef1e84ad7_78.png)

And the next symbolble in the token input is open peren， awesome。So we consume that terminal。

 I'm going to move the arrow。 And now the next terminal we want to consume。

 The next token is the identifier fo。

![](img/d73b5033a85de535920e9a4ef1e84ad7_80.png)

All right。So at the moment， what we're trying to do is pass an E。

 this leftmost non terminal E and the next symbol is an ID。So we look up。Row E， column Id。

And this tells us that we want to use the production。 E goes to T E prime。So we replace E。

With TE prime。Awesome。😊，Now we want to pause a T。The next token is AD。The power of T， token as ID。

 we want to use this production。 T goes to F T prime。So we replace if， we replace。This tea。

With FT prime。

![](img/d73b5033a85de535920e9a4ef1e84ad7_82.png)

Okay， now we're trying to pass an F， the next token is an ID。😊。



![](img/d73b5033a85de535920e9a4ef1e84ad7_84.png)

Look up row F。

![](img/d73b5033a85de535920e9a4ef1e84ad7_86.png)

Colllum ID。Okay， we want to use the production if goes to Y D。Fantastic。呃。So let's replace if。

With I D。Now。AD matches the next token。Or other the token type， I D matches food。 So we advance。

We consume that token， and now the next token is plus。And what we're trying to do is pause a。T prime。

We've consumed open print and ID。We're trying to consume powers of T prime。

 the next symbol is a plus， so we again look up our table， T prime。Symbol is plus。Oh。

 this is interesting， right， It tells us to use the。

Their production T prime goes to the empty string。はい。嗯。It's essentially telling us， hey。

 we don't have any multiplication or division terms。😊。



![](img/d73b5033a85de535920e9a4ef1e84ad7_88.png)

![](img/d73b5033a85de535920e9a4ef1e84ad7_89.png)

To pause。Okay， so we replace T prime with the empty string。 Now we're trying to pause an E prime。

 The next symbol is plus， we look it up E prime plus here's the production to use。



![](img/d73b5033a85de535920e9a4ef1e84ad7_91.png)

Okay， so we replace C prime with that production plus T E prime。Now， the next symbol is。A。



![](img/d73b5033a85de535920e9a4ef1e84ad7_93.png)

Plus。Next example of the token stream is a plus， so we consume it。 We go on to the next token。

 the seven token type is of coursear， a nu。So now we are trying to pause a。



![](img/d73b5033a85de535920e9a4ef1e84ad7_95.png)

t。And the token is a nu， so we want to use this production。



![](img/d73b5033a85de535920e9a4ef1e84ad7_97.png)

So we replace the T with if T prime。Now we're trying to pass an F。 The next symbol is a nu。

 We use the production F goes to nu。 So that is we replace F with nu。Who。Great。😊。

And we consume the seven。Now， we're trying to pass a。T prime。The next symbol is close print。

We look it up。T prime， close brand。Use the production T prime goes to empty string。

 so we replace T prime with the empty string。Now we want to pause an E prime。Hoose per。

We use the production E prime empty string， so we replace E prime with the empty string， great。

Now the next thing in our derivation is closed print， which matches the token we're trying to pass。

So we advance， we consume that。W。All right。Wanting to pass a T prime， the next symbol is a OF。

 Let's look it up in the table， says use T prime empty string。

So we replace T prime with empty string。 Now we want to pass an E prime。 The next symbol is an EOF。😊。

嗯。呃。So we use E primeme goes to empty string。And replace Eprone with empty string。 And finally。EF。

That's the next token， EOF， Awe。 And， in fact， our derivation now consists entirely of terminal symbols。

😊，So。Thank you for sitting through that long and painful derivation。 This is why we have computers。

 so that we don't have to do this by hand。 However。

 it is really useful to actually go through an example and see that this predictive parsing table really worked。

😊，We were able to take this from dering an S and looking at the next symbol。

 this predictive passing table taught us exactly which production to use。

 There was no guessing involved。😊，We were able to just use the correct production。

 and the sequence of tokens was a valid string， was a valid sequence in our language。 We were。

 in fact， able to pass it。😊，E it was invalid。Then。We would have got to the case where， let's say。

 the next。Terminal symbol in our production。Would not match the next token in the token stream。 So。

 for example。That might be either we don't have something to look up。Or， we didn't。

Or we didn't match the correct expected token versus the real token。

 in that case we would report an error message。Right。Any questions about this example， William first？

This still felt a little inefficient。maybe like things I might point out are。

Like when we had an expression and we saw an identifier， we had to go down three levels of。

Proeductions， right， we had to go from E to T E guy。T to F and then finally go from F to ID。

 so there has to be a way， especially because all of these have at least one production。

 you need to be able to condense the table there， right？没天。Is you or is it just not necessary？

Like possibly replace T to SD prime to like T to ID the IDs。Right， so that's interesting。

 So sometimes based on， let's say the follow set， you might know。诶。So for example。

 if I am trying to pass a。If and。嗯， let me。Let me get an example of that。Like tea with ID or。听。Maybe。

It might be possible。I don't think it'll always be possible in this example we happen to have a couple of situations where we ended up having a T prime followed by an E prime and we ended up wanting to use kind of a T prime goes to the empty production and E prime goes to the empty production。

I need more thought about whether in this particular grammar。Knowing some。

 if I'm trying to power something and I see a particular production used。

 So if I use some particular row of the type with that tells me about what the next production I'm going to use is。

 it might would require more analysis。 I don't think it'll always be true。

But this question of are there more efficient ways of passing？Yes， absolutely。

There are many different kinds of passess。I'll talk a little bit more about some of them in just a moment。

Sorry， William's question， if F is moable， then it might not be possible。这个。Right。

 so it's going depend on the grammar as a whole about， you know。

 we use the grammar as a whole to compute the。First sets， the follow sets and so on。

 And so these questions about， hey， if I look up some particular cell of this table。

Tes me which productions are used， does that give me any information about the next production or the next two productions that I'm going to be using？

I don't know， maybe in some situations。And so thanks for pointing that out， Joy。

 that it happens that maybe is a peculiarity of this grammar in the way if is was written。Sorry。

 wouldn't have the you head your hand Yeah， let me pose that question to the next slide。

 but I'll answer and just see if there are any more at the moment。I think for each entry the table。

 you could keep going with the derivation until you stop at something which starts with a non terminalmin。

 so instead of S E to E EOF。You could keep tracing it down into it about sorry for the like very first open prees。

Okay， I think for the S to E EF， you could just keep tracing that down until you get。

 I think itll be like S to parentheses， the closed parentes actually T prime E prime E right。

 So this is the idea that you're saying that in this row for S。Open peren。

We actually know that we're going to be needing to derive， he needs to derive an open parent。

So I know I have to be using E to derive an open print。

 which means I have to be using T to derive an open print。

 which means I have to be using F to derive an open print。

 So maybe we could just jump straight to that in some ways。 That might be possible。

 Thanks for pointing that out， Maxwell。One of the things I'm glossing over a little。

 And you'll see this when you start implementing a generator using a par generator is。

In addition to the productions， right， just the idea of recognizing a string and saying，ha， Yes。

 this is a valid string。 We're often wanting to build up。Something。

 a data structure that represents the result of passings。嗯。

And so what that means is that when you actually write the grammar。

You'll be including these productions kind of the action to take or the expression to use。

To compute the result of it。So。You could do it， you could end up like saying。

 I know I'm going to combine these productions， but you'll also end up needing to combine or compose the computations associated with them。

And so the question of the complexity of your PA generator and doing that correctly versus。

The overhead of going through each step。Is something to sort of way up。 And there is more to say。

 you know， we're going through this example as really about recognizing a string。

 But for the purposes of a compiler， it actually produces。



![](img/d73b5033a85de535920e9a4ef1e84ad7_99.png)

A nice structure， so。So that， that's something that's kind of going on implicitly。

 that would need to think about。 I will say， though， that I， I should have brought it in。

 I'll try and do it on Monday。 I have a textbook。It's about  a000 pages， I think。

 on passings techniques that I'm happy to bring in and show you。😊。

Scratching the surface of passing took an idea of some of the key approaches。

 but there's a whole lot of interesting techniques behind this。And maybe interestingly。

 but for a problem that has kind of been being studied since at least the 60s。

There are still advances happening in the field of passing。So they。

Let me jump and tell you a bit more about。About different kinds of passess。嗯。

The grandmother we just saw is what's known as an L L1。Grmmar。

 so that is we can produce a predictive passings table。Where。Each cell contains at least sorry。

 at most one production。That means the grammar。Fits within L。 L1。And by the way。

 the first L here means a left to right pars。That is what we're doing is going through the token stream from left to right。

 Almost all parers do this。Okay， you know， read a file from beginning to end。

The second L stands for leftmost derivation。So that is， when you think about the derivation。

 you know， you start with this。 you're replacing a non terminal each time。

 The non terminal that is being replaced is always the leftmost non terminal。Heep。嗯。The one here。

Is means one simple look ahead。And so essentially， what that meant was in the predictive parsling table we came up with。

 the columns we had。We're sequences of one token。one terminal。

So you can actually generalize this and if you wanted to do LLK。Orre L L2。3，4， and so on。

 The columns would have。Two symbols， right， The next two symbols， the next K symbols。

 that would be the columns of your predictive passingsing table。Now， as you might imagine。

The table gets bigger if I'm looking at， you know，2。诶。Two symbols or three symbols or four symbols。

But looking that much further ahead in the token stream is maybe going to give me more information。

About。What the string is that I'm trying to pass And thus which production I should use。

 So that is a grammar that may not be L L 1。RightIf I tried to do an L1 predictive passing table and end up with more than one production in a cell。

 maybe it's an LL2 grammar。 if I looked two tokens ahead in the stream。

 there would be enough information for me to figure out which production to use。不了。

Do L K grammars have。And most K productions per cell or and most one production per cell。 Yes， yeah。

 the K is referring to the number of tokens we're looking ahead。 The idea is that。

Let's say we look ahead at the next five tokens。 That just tells us which column of our table to look up。

 I'm trying to pass this non terminal。 Hey， here are the next five tokens。

 That tells me exactly which product production to use。M what happens if。Cllction。

If there's more than one production per cell， then the grammar is not LLK for whatever K is that we're trying to produce the predictive parsing table。

Normally， this means that we just reject the grammar。 your parser generator will say， I'm sorry this。

 I can't produce a parser for this。 You could imagine trying to do something like oh。

 I can still do this backtracking on my pars， let me try using that production， if it works great。

 if it doesn't work I backtrack， but generally PAser generators don't do that if it't if it doesn't fall with an LL K for the whatever K they're using。

 it will just reject it。There were more questions from this side of the room， Tak。 just a follow up。

 Yeah， So feel like more than one production person。 does that mean like if you add more letters。

similar。可过ち了。Great par sir。So what's interesting is。This idea of like an LLK grammar。嗯。

There will still be grammars that are not LLK for any K。

RightSo there are still going to be grammars that we can't use this technique to produce a pass。

 is that the get to the question you're asking？Okay。

 let me just do one more questionca I'm almost out of time， who who are the hands。I yeah。

 can you always like rewrite the grammar for language to make it hell of one。

 I'm thinking about like the La recursive thing you did。呃。

That is a good question that I don't know the answer to off the top of my head。

 but I'm happy to consult my PAsA technology tunnel and tell you， let me just say quickly。

 beyond LLK， we can have LL Star。😊，Where the idea is that it can determine the next production by looking at some finite。

But perhaps， unbounded。Number of tokens。 So there， the columns of your table。

 of your predictive passing table might be， say， a regular expression。It's kind of like， hey。

 if the input coming up matches this regular expression， then this is the production you want to use。

Right， I just want to point out that an ambiguous grammar is not going to be L L K for any K or even L L star。

 I'll let you think about way that is。Think about what the definition of an ambiguous grammar is。

 Think about why that means we can't be LOK。Next class。On Monday， we're going look at L R grammars。

 If grammar is unambiguous， it might still not be LL K， but we have this more powerful technique。

 L R， which turns out to be a bottom up parsing technique。😊，And even less intuitive。Then Alo， okay。

 have a good weekend， good luck with the homework for you working on you all on Monday。😊，どし。你没买过啊。好。

De。いですが。Yeah。有有稳定。有你系。In the sense that if I look in one token head。

 I know exactly which productions used， then looking two token head， two token here。So increasing k。

 so more and more grammars are going to be LLK as you increase K。

 but there are grammars that aren't going to be LLK。这。いああ。

I'm probably going to be what's actually interesting is。

We're going to most the positive generators actually produce。our premises。Maybe。

We need to check maybe allow one。Is what？啊。Tractical programming managers。

Can be relatively easy refed to the NLR。

![](img/d73b5033a85de535920e9a4ef1e84ad7_101.png)

An now our grandma。So again， this idea that you might have a grammar that recognizes a language。

But the grammar may not be in a form that's easy for you to pause so you would refactor the grammar。

So that recognize that the same language that in a way that's satisfies but you need it and we'll see。

In Monday's class。The requirements fill are LR， grama。

 and most positiveit generators are actually LR。Po it generates close enough。

A lot of the common compiler pilot are generated。FirstI'll see last question really。

Bringing down LK to like a board。We just to do that with like more numbers。嗯。

It's like I said of like star。ます。More symbols。So you combination， maybe you know that's changing。

Thiss changing the language you recognize。Formin misunderstanding your suggestion。Yeah。

maybe changes like the structure I'm thinking like， you seriously what's going on？And that。

 no one wouldn't have been L1 right。Brenent doing expression or actual plot。

 is that one of these stuff。The plus stuff into like a new set of terms that would same thing。

Oh assuming mean if a language isn't say L of1， could I refactor it to be an L of1？

I'm going to say in general， not， in general， that's my guess， but。

It feels like there's a chance to some sort budget。Yeah。So this， this kind of。

There's a huge range of。Grammars， like sets of grammars， essentially based on。Can we produce a per？

For a gra， so LO1。In many ways， you know， L1， LLK， whatever this is。

You can argue it putting the cut before the horse right and saying， hey， I've got a technique。

That in some situations really works really well for a grar。

So I'm going to define all of the grammas that I can actually use this technique on as being。

LLK right a grammar is LLK if I can use this technique to puzzle。

And so then there's a question of like through a given language。

 can does there exist an L K grammar for it？嗯。And people have studied these questions in depth。

 and I have the kind of mind that does not remember that。Oh you mean if a language isn't say L of1。

 could I refactor it to get L of1？I'm going to say， in general， not。In general， that's my guess， but。

It feels like there's a chance for some。Yes， yeah。So this， this kind of。There's a huge range of。

Grmmars， like sets of grammars essentially based on。Can we produce a PAer？For a gra on this， so LO1。

In many ways， you know， L1， LLK， whatever this is。You can argue as putting the car before the horse rate and saying。

 hey， I've got a technique。That in some situations really works really well for a grar。

So I'm going to define all of the grammas that I can actually use this technique on as being。

LLK right a grammar is LLK if I can use this technique to puzzle。

And so then there's a question of like through a given language。

 can does there exist an analog K grammar for it？嗯。

And people have studied these questions in depth and I have the kind of mind that does not remember these results。



![](img/d73b5033a85de535920e9a4ef1e84ad7_103.png)