# 哈佛大学《编译器｜Harvard COMPSCI 153 compilers 2023》中英字幕（claude-3.7-s p12 1697465700-Compliers_on_10_16_2023_(Mon).zh_en -BV14PAUejE98_p12-

呃。I just want to say please be aware of support resources feel free to reach out if you're being impacted in this class in particular please feel reach out feel free to reach out to me but there are of course a lot of others in the community you can share with with your resident de in your house being a very natural place to go。

Please take a look at you' been receiving emails with support resources， so please。

Look at those or feel free to reach out to me if there's anything we or anyone in the Harvard community can do to support you at this time。

So hard to move on from that， but returning to the reason we're all gathered here in the course。

 you should have seen an ed post that I made yesterday about the embedded ethics lecture that's coming up on Wednesday。

We're going to be looking at issues raised by open source compilers as we chatted about LLVM and indeed a lot of compiler and language technology infrastructure is open source developed often by volunteers and it's interesting to consider the ethical issues that are often that I think as technical users of infrastructure not things that spring to mind that we don't think of。

呃。If you're able to attend in person person， please do so。

 That's good both for your engagement in the material。

 a lot of which is going to be discussion based and also for just。Everyone else as well。

 like your participation will help you and everyone in the class to make that more interactive to get the most out of Wednesday's class。

 there's a couple of suggested pre readings。 One is watching a short video about 13 minutes and then also some readings。

I think there was 30 pages assigned， it's a law paper， so about half or more of each pages footnotes。

 you don't need to read the footnotes， so the reading is actually pretty short and interesting。

Any questions about anything on the s slide， support resources embedded better ethics。All right。

 homework three is out and due in one week。And we're also going to be releasing homework for today。

 and that's because。嗯。Just appreciating this as a busy time of the year。

 a lot of people have midterms that they're trying to coordinate。

 so we're giving you flexibility with homework 3 to be able to hand it in a week from today。

 but we're actually covering all the material we need for you to start on homework4 by the end of this lecture so we want to make that available to you and as I've been saying。

 please I encourage you to wrap up homework 3， don't work on it until the last minute。

 realize the point where you're getting diminishing returns stop working on to submit it and take a look at homework4。

When you can。For homework 4， you're going have three weeks to be implementing a simple C lake imperative language。

 So that is it's going to support 64 bit integers， arrays and strings。

 You're going to be able to have procedures at the top level that are going to be mutually recursive。

 It's not a functional programming language so they're not you can't pass around procedures or functions as values。

 but you can start to write some pretty sophisticated code。

 Once you're able to get these procedures in place。

 You're going to have scope local and imperative variables。

 and you're going to be compiling down to L VM light， the language that in homework 3。

 you're currently in the process of compiling down to X 86。嗯。When we release the code。

 you'll be able to take a look at the handout， but we have a lot of sample programs written in this language in O。

Specifically what you'll be doing is finishing the Leer in the PAs。

 we're going to be giving you some initial files， but they have some some things missing。

 so you'll be filling in the Leer in the PAsr。And then you'll be working on compiling this OT V1。

To LVM lights。In Home 5， we're going to be having Oat version2 with a few more features。

Because you're compiling to LLVM lights， which is compatible with LLVM。😡。

You can actually then use Kang to go from L of VM to X 86， or you can take your homework 3 solution。

 your backend MLl file that you are getting to know intimately well as you're working on it and actually just drop that into homework for and as a result you will have implemented something that takes you all the way from a high levell source language all the way to X86。

😊，but so you can do that for your own fund， you won't be any years you have in your backend dot Ml project will be should come out on the grading of homework 3 and it's for your own fun and enjoyment and satisfaction that you can use it in homework for。

 but we're not going to be grading backend do M on homework for。😊，Okay。

 any questions about the homeworks？Okay， so today we're going be continuing and wrapping up the section on parsing。

 looking at L R parsing。 Before I get， though I did to track down my parsing textbook。

 parsing techniques， a practical guide。 it is about 650 pages。 So right order of magnitude。

 I mentioned1 thousand0 pages。 And this， I think goes into a reasonable amount of detail on different parsing techniques。

😊，呃。In different ways of， of thinking about and implementing pausing。So as you can see。

 by devoting two lectures to it， looking at L L K passes and what we're looking at today。

 L R parsing， we are just scratching the surface of this。 It is a。An interesting field that I think。

 is。Mostly solved in the sense that。For many practical purposes。

 we are able to build paths quickly and relatively easily。 the work。 But that's it。

 There is still ongoing research in it and interesting research papers coming out。Occasionally。

 and indeed， I think。Over the last five years， I've had maybe。3。

Senior theses that have been around passingsing in some aspect making contributions with the most recent being on a technique called packrat parsing。

Wwhich uses essentially smart memorization of passing to try and get fast passing of grammars without needing to contort them a huge amount to make them fit into LLK or LK。

Grandmas。Okay， so we're going to be looking today at LK passinging。

So the first L here is standing for the left to right parsing， just like we had with L L K parsing。

The second letter R is referring to the right most derivation。 So that is， if you remember。

 when we have a derivation， we start with the start symbol。 And each step。

 we choose some non terminal and replace the non terminal with the right hand side of a production and the right most derivation。

 we're always choosing the right most non terminalmin to replace。Now。

 the way LR housing works is that we actually。End up constructing the derivation and reverse order。

 We're doing this bottom up derivation。 We'll see the， we might see the past tree that we do。

 but essentially the derivation is the rightmost one。

 but the order that we're actually doing it and turns out to be a reverse order derivation as we go from the bottom from the tokens up to the up to the top level。

The key here refers to the number of symbols， the number of tokens that we might be looking ahead in order to。

Figure out which rule we want to apply。And we're gonna be working through examples today and we'll actually be looking at L R 0。

Pasing， so not looking ahead at any tokens at all。 Once we have that idea down。

 we'll kind of see how we might extend it to the to have a non zero look ahead。Okay。

 the basic idea of L passing。Is。In some ways， similar to L L parsing。

 if you remember with L L parsing， we had this predictive parsing table that is we constructed this data structure。

The then， as we were pausing。As we were passing in particular input。

 that predictive pa structure told us what we should do。

With our passingling was about which rule we should apply。With LR parsing， same high level idea。

 we're going to do some pre work to produce some data structures。

 and then we're going to use that data structure while we passse the input。

What's different about L housing， though， is that we're going to have a stack。Okay。

 and then we're also going to have our input that we're going through。

The basic idea is that our Paza。At any step。Can I。Shift a token from the input and push it on top of the stack。

Okay， so that's a shift action。Or it can do what's called a reduce action。

 It can take some sequence of things at the top of the stack。

Which is going to be a sequence of tokens and non tokens。Pop them off。

And replace it with a non terminal。So essentially reduce some segment at the top of the stack that matches the right hand side of a production。

Pop it off and replace it with a non terminal。So， for example， if we had a production， X goes to ABC。

 and at the top of our stack was in order from the top CB， A。

 we could pop off all those three things and replace it with X。Okay。

 so to give you an idea of this shift reduce thing。嗯。And then ultimately。

 we get to the data structure that will， of course， tell us。Whether we want to do a shift or reduce。

 But first of all， to talk through this idea of shift or reduce。 Suppose that this is our grammar。

 It's a greatly simplified expression grammar。 So an expression is either an integer。😊。

Or it's a parentthesized expression， or it's an addition。 Okay。

 so getting kind of the key things about an expression grammar。We're gonna be maintaining a stack。

And an input。 And let's suppose that the input we're trying to pass is the following open peren 3 plus4 close peren plus open peren。

5 plus 6 close peren。Okay， so remember at each step。

 our options are either shift a token onto the stack or reduce from the top of the stack。Clearly。

 at the beginning， we can't reduce。 We have nothing on the stack。 So we're gonna to do a shift。

 We shift that open print symbol from the input。Onto the top of the stack。Next step。

 we're also gonna do a。Shift。嗯。We have here， of course， the symbol the token 3。

 the token type would be int。You could。Our options here would either be to reduce。

 according to this E arrow in rule， since int， the token type matches the top of the stack。

 or we could shift， shift that plus token onto the top of the stack。We're going to reduce。

And we'll see later about how we end up choosing a reduce or a shift。 But let's， for the moment。

 just suppose we magically know what to do。 So we're going to reduce using the rule。E arrow int。

 that is we replace that3 with an E。Next step， we're going to shift。Next up。

 we're going to shift the four again。Next up， we're again going to reduce。嗯。

Using the rule Earrow int， popping the four off。Pishing on the E。At this stage。

 you'll note that at the top of our stack is E plus E。

 which matches the right hand side of this production。And indeed。

 what we're gonna do is our next step is reduce using that production。 That is we're gonna pop off。

E plus E。The right hand side of the production and replace it with E。Next step。

 we're going to shift the next token close pernne onto the stack。Now， at this stage， we can reduce。

We shift。And we keep on going Okay， so that is at each step we're either shifting a token on or we're reducing according to some production。

And so without going through the pain of it， I can tell you that we are magically able to do some shifts。

 do some reductions。And eventually end up。Deriving in our stack， the start symbol E。

whereupon given that we have the SA symbol on the stack。And we have an empty input。

It means we were able to successfully pause。All over the input。Any questions about this example。

 this idea of shifting or reducing using a production？Yeah。

 so the rightmost part and the right part in rightmost variationvation mainly just comes from the fence that the sta is like。

到最候。First and first， yeah。Let me， let me actually just show you this Q animation。 So as I mentioned。

 L powers produce a remotemost derivation。 So that is， if we think about doing a derivation。

 starting from E。You can imagine replacing E with the production E plus E。

The right most non terminalal is this one over here。So you can imagine a derivation that expands it。

 continues to expand the rightmost derivation at all times。And essentially， what's going on is。嗯。

We were producing this derivation。This derivation that would find by always expanding the Raos non terminalal。

 but we happen to do it in reverse order。So that is the order that we did it in was the first thing we did was reduce the endt to a。

 The second thing was reduce this end to a。The next reduction we did was。E plus E to E。

 The next reduction was the parentheized D and so on。

These numbers here that I've put on are the order that we did reductions in。

And you can check to see that the order that we did， the reductions and are the reverse order of。

Right most erivation， the thing we would expand when doing a rightmost derivation Are。I'm going say。

 for the moment。Let's， we're imagining that we magically know what action to take。

 shift or reduce according to a production。 You're right。 We might have a grammar that。

Is ambiguous that there's multiple past trees， multiple derate。Yeah。

 multiple pars trees that correspond to the same input。嗯。Or for any， in a particular situation。

 it might be unclear which production you want to reduce。

 And we're gonna dig into the details of that soon。Does that help it non abiuous？

Will satisfy the property that there's exactly one rule that matches the subjects。

 because isn't it possible that like multiple rulers match the topics。

 but one of them causes problems later Right， So is it， is it the case that。嗯。

Is every non ambguuous grammar have a deterministic way of figuring out which actions to take？

 The short answer is no。As。诶。We're going to go through and sketch the construction for an LR PAser and essentially get to showing you kind of what conditions need to be met for us to successfully construct an LR PAser。

And any grammar for which we can successfully construct an LR PAsa is known as an LR grammar。

And so there are grammars that are not ambiguous， but they are not they are not LK for any K。

 for example。嗯。Yes， but。Let me see if。Someummer in here in this。

Puzzling book is a very handy diagram。It kind of shows the inclusion relation of all these different classes of grammars。

But I will。Can I remember which page it is on off the top of my head。

 So feel free to come up after class or post on Ed and I will try and show you the。

Hierarchy of gramas。Yeah， how are you。没意。That's a great question。

 we haven't really dug into the efficiency of PAs。But an LR PAza is linear in the size of the input。

呃。I would triple check that， but I'm pretty sure it's linear in the size of the input。

诶 you can't get。There are pauses and paing techniques that will be。

Cubic in the size of the input for any grammar， including ambiguous grammars。

 whether it's nice properties that if you have， for example， an unambiguous grammar。

 itll be worsecase in squared and for various unambiguous sorry。

 unambiguous deterministic grammars will be linear but might end up taking up more space in memory。

Then some techniques like LR housing。We're going to get through Ella。The idea of L our passing。

 most practical。For compilers。Most languages will fit with an L R1。And even within that。

 a slightly more restrictive subset called LAALR， which is similar to LR， but well。

 remind me and ask me that question at the end of the lecture。

 and I'll explain what LALR is once we have some more of the concept。Yeah。

What else would you use pars besides compiles？呃。So many places。

 Let's see your browser renders H TM L。 you read it。 so it receives H TL from a server。

 It passes that in order to figure out what's going to do with it。That arguably some sort of。Yeah。

 there's pattern of natural language as well。 So you can anyone doing a joint or a double or a secondary in linguistics。

Really， it's actually a really good match。 programming languages，'s computer science and linguistics。

 We have a lot of joint concentrators in it。 But par and natural language actually typically。😊。

Grammars for natural language are often written as context free grammars。Indeed， this。

This concept of context three grammars and various other grammars actually was developed by Nom Chomsky。

 a linguist， really with respect to the study of natural language。These days。

 natural languages often passed using different techniques， known as statistical parsing。

That doesn't make a whole lot of sense for programming languages。

But definitely for some things using these kinds of techniques for natural language passing。Thankshs。

嗯。What else。I will say most of the things I'm familiar with。

 even if they're not within a compiler pipeline， they're somehow related to computer languages。

 But so， for example， syntax highlighting in an editor is can be done by， for example。

 regular expressions。 A lot of syntax highlighters are implemented that way。

 but that limits the expressiveness of your syntax highlighting。 So if you wanted。

Different colored parentheses to show the nesting levels。There are hacks to get away with it。

 but sometimes context free grammars are actually what you want。

 and some of the passing that you need is relying on these techniques and others。嗯。Oh gosh。

 The number of times we actually take a sequence of。Symbols a need to do something with it。

 say network level packet processing。Is a form of pa。Right， and interestingly， it's。

You could argue that it turns out to be a non context free gramar because one of the things you might do is read in a value。

Let's say an integer in whatever format， binary or hex or something。

 and that tells you the number of bytes that you're then meant to read right It's actually a grammar。

 but it turns out to not be context free， It's something called context sensitive grammar。

But some of the techniques of passing apply in those situations as well。 And in some ways。

 a lot of the trade off is really about。What's the expressiveness of the language that I'm doing。

 And in particular， if you can design the language， say the packet layout。

 how do you strike a balance between the expressiveness of that language versus the techniques for passings。

All right。So when I mentioned that actually a lot of programming languages fit within what I'm going to show you。

 LALR1 parsing。It's actually not quite true。 A lot of passing is actually context sensitive。

 so even in something like the C programming language。呃。Figuring out whether you're using。嗯。

Your AST structure。You're not actually going to be able to do just by looking at the symbols alone and using these context free grammar parsing techniques。

 So， for example。You might need to disambiguate an identifier and figure out whether it's a type。

 whether it's an identifier in languages other than see。

 maybe it's something referring to a namespace like a package。

 And you actually need that information and sort of。To figure out the syntax。

 the correct AST structure of your program。So this is all to say that。

Part of this idea of trading off the expressiveness versus the practicality or the efficiency of passings something that's pretty common in programming languages is to。

Have a grammar that can be pard pretty efficiently。

 So on linear time and often with low with low overheads， low constants。But nonetheless。

 it requires a subsequent pass to actually disambiguate and figure out the actual semantic structure of the program。

It was a bit of a diversion， but does that sort of address some of the questions of where do we see passing and。

Is this enough。Okay， any other questions at the moment？O。

So we went through this example where we magically knew whether we were going to shift。

Or reduce according to some production。So the question is， how do we know which action to take？Now。

 just like with LLK parsing， we have this idea of the predictive parsing table。

This data structure that allowed us to figure out which action to take。

 We're going to do something similar here for L passing。But what we're going to do is use a DFA。

 a deterministic finite autometerta。Cool， right。 So this came up。

 We saw DFs when were looking at Lexing when we were looking at taking a sequence of symbols and breaking it up into tokens。

😊，We're going to be using a DFA differently here。Same formalism， same concepts。

But the way we're gonna to use this DFA here is edit every step。Of Al Paza。What we're going to do is。

Take a look at our symbols on the stack from the bottom of the stack to the top。

That's going to be our input to our DFA。So that as we're going to take the sequence of terminals and non terminals that are on the stack。

 feed it through the DFA， that's going to get us to a particular state of the DFA。

And then that state of the DFA is going to tell us which action we want to take。If we're doing a。

LRK positiveer for K greater than zero。Then in the the state of the DFA that we're in。

We might at that point use K tokens of look ahead to figure out which action to take。

But the key idea is that we're going to be。Building a DFA ahead of time。And at each step。

 when we're actually passing， we're going to use that DFA。To take the symbols on the stack as input。

 get to what state of the DFA that's going to tell us what action we want to take。Yeah。

 why don't you just always。来。Can you design your prizes to that life？

You always want to let our specialist。Thing， and then we just like always。嗯。Maybe。

But you can definitely come up with grammars where your intention。

 that is the semantic structure you might be intending。

In order to successfully power would require you to do a shift instead of a reduce at a particular stage。

Even if you did end up saying like， hey， I prefer reducing to shifting。

The construction we're going to see will still be helpful to understand how do we know？

Whether we want to reduce or not。All，How do we know which production to use to reduce？

So what I'm going to do is walk through an example of building this TFA for LR passing。

And we're actually going to be doing LR0 passing。 So zero tokens of look ahead afterwards。

Wave my hands about how to extend it。For nonze K。Alright。

 so we're going to need to introduce some additional concepts。In order for us to build up。

This DFA and to use it。So one of the first things， first concepts I want to talk about is an item。

 So the states of a DFA are going to be sets of items。An item is going to be a production。With。

An indication of the current position of the PAsza。So， for example， here is an item。

E goes to E dot plus E。😡，So for the production， E goes to E plus E。We're adding in this indication。

This dot that this is where the parser is up to。 And this would be suitable for an item where with pars the first expression。

B。And we're yet to read a plus and an E。For the rest of the production。So it's kind of saying。

If we have an item， it's sort of saying this is a production that might be the one we're using。

 and here's how far we've successfully gotten in consuming tokens and performing reductions that would match this production。

In general， if we have an item， x goes to gamma。 Delta。

It means that gamma is at the top of the stack。And at the beginning of the input。

 or in the remainder of the input， there's a string that's going to be derivable from Delta。

That is assuming that this is a the item that is successfully used to pass right。

 So it's describing something about what's on the stack。 What we've seen so far。

 plus what is still remaining in the input。Okay， so let's take go through an L zero example。

Here is the grammar we're gonna to use for the example， it's。Prenthetized lists。

 essentially S expressions for those who are familiar with S expressions from LspP or scheme or otherwise。

I've added here a。Essentially， a new start symbol S prime。

That we can explicitly put in the end of file token so that we know just having something a bit more explicit to be able to tell us when we've successfully passedd the input。

But otherwise， an S expression is a parentheized list。Or it's a token， let's say。An identifier。

 And for simplicity， we'll just say an ident X。Or a list consists of either。

 a list consists of one or more elements。 Okay， so whether here's the base case one element。

 or there's a list followed by a comma， followed by an S expression。Okay。

 any questions about the grammar？Okay， so we're going to start off with our construction of the DFA。

 deterministic phostate automaton。We're going start off with our entry state to be automaton of of created state here of labeled at one。

The first item of the first state。Is we take。This the start symbol。Yes， prime。

Here's the production for it。 We have just a single production for our start symbol。

 and we're going to create an item that indicates the pars at the beginning。Of this production。

 So the item we're adding is S prime goes to dot。Iスイオフ。There's nothing on the stack。

And remaining on the input is something that's deable from S。Followed by the Inde file。Now， what we。

What we're going to do is we construct this DFA。Is for each state。

 we're going to take what's called the closure of it。We're going to say， hey， look， we're just at。

The PAer is just at a point where we're ready to parse a non terminal S。

So what we're going to do is take all of the productions for S。And add those to the state。

So we're going to take these one。Two productions for S。Add them to the state。

With the indication that we're at the beginning of the production。

so the dot is there at the beginning of the production。So that is the。The closure of the state。

 following that rule， the idea that if we have any item where the dot is just before a non terminal。

 we want to add in all the productions for that non terminal。We've done。

 we've finished that at this point。 We added in all the productions for S。

 The remaining items that start is just before the token open print。

 This one is just before the token X。Okay。So what we're going to do is from every state。

We're going to look where that dot is。And think about， well， what's the next thing in the production。

 Be it a terminal or a non terminal symbol。And we're going to add that as an outgoing edge to a new state。

So let's start with this last item， S goes to dot X。So we could consume an X。Right。

 the next thing in that production is an X。 So we're gonna take that to a new state。

 And in this new state， we're going add。From this， it came from this item here。

We're now going to add an item where the parsr。Which was previously before the X has now taken the X。

And so the current point of the PAsza is after the X。Let me give you another couple of examples。

 also from state one， according to this item。We could take in an open paren。

 So we're going to construct a new state。State number three that we can get to by following an open parent。

We're going to initially put in this item where it's the same as this item。

Except now we've also the pr is also consumed。The open peren。 So we're right here。

Just before that hour。So what that means is that the in state3。

 the positor is just about to consume an L。 So we're going to take this closure。

 We're going to take all of the productions for L。These last two productions in the grammar。

And we're going to add them。Into our state number 3。Okay， so we added the productions for L with the。

The paths are indicating we're just about to start pasing the right hand side。Okay。

 this item that we added， L goes to dot S。Well， here we're just about to start passings an S。

So we're going to do the same thing。 We're going take all of the productions for an S and add them into the state。

With turning them into items with a。The P indicator indicating that we're at the beginning of that production。

Our third item that we added L goes to dot L comma S。

 This also says we're about to start passing an L。But we've already added in appropriate items for that non terminalal for L right So this idea that we just kind of keep on adding in appropriate items until we can't add anymore is a idea of closing the state。

With the items。 so we're done with that state。Nothing more to do at the moment。

Any questions so far as we're kind of working through building up this DFA？Yeah。

 so we don't really care when the dot is。In front of， like。Something that's aitarily。

Like that doesn't it does。 We're。 We're still in the process of building up the DFA。

 but when the dot is in front of a non terminal。We're going to be having an outgoing edge from that state。

To say that， hey， if my parer is right here and is expecting a dot。

I have a dot that'll take me to this state， where I'm now going to be ready to pause an L。

And if I'm ready to pass an L， then I have to be ready to pass an S。Yeah， maybe I didn't mean Oh。

 sorry， I was using non terminal。 sorry， I was saying non terminalal and meaning terminal policiespologies。

 Sos like the open print， sorry is a terminal symbol。 only It does， in fact。

 still still constructing the DFA。 So here from this production from this item。

 S prime goes to dot S E OF。We are also going to add an outgoing edge with that non terminalal S。

And we're going to add the item。😊，诶。The updated item where the P is now after an S。He。嗯。

It turns out that this state I just created， state 4 is going to be an accepting state。 So that is。

 if we get to this point here and we've reach the end of the input。

 that is the next thing is the end of file， then we've successfully passed。

Successfully posit the input。Okay。嗯。We're going to keep on going。

 adding states based on the next symbol in an item。Okay， I'm not going to deal with EOF。

 You can imagine actually doing so if you wanted， but we're just going to instead treat this as a final state。

State number two， there's nothing in particular to do right， there's no next symbol after that item。

 but in state  three。There's actually quite a few outgoing。Edgeges that we want to add。Let's see。

From the bottom。It goes is。It goes to dot X。Well， we could consume an X。

 so we're going to add an outgoing edge with x to the item S goes to x dot。

So that's this age that we added right here。Outgoing edge with an X。

 It turns out that we already had that state， a state that was seated with the item S goes to X dot。

so we didn't need to create a new state， we just needed to add an edge from three to two。

Looking at the。Second to bottom item， S goes to dot dot open peren L close Peren。

 We're going to add an outgoing edge for the peren。The open parade。

So the item that we're going to want to see the state with theres S goes to openparen。l close Peren。

But that is， that state already exists， right， It's state number  three。So in fact。

 going to add an edge for open printen from state 3 to state 3。Okay， what next？

Going up from the bottom， what's the next outgoing edge we're going to add？た。An L， right。

 So from this。Production right here， L goes to dot L comma S。 we can add an outgoing edge from L。

 And what's the item that we should see that state with。Yeah， just scroll it out appreciate。

L dot Comce， right， And that's。That is a new state。

L goes to L dot co S skipping over things a little。 it turns out that if we。诶。

That outgoing edge following an L， because we're a deterministic finite automaton。

 we could have also taken an L from here in this first production。

So we're actually setting it with these two items。 The one Rihi that you mentioned here。

 and also this one S goes to openparen L dot close print coming up here from this first item in the state。

From say number 5。We could read a closed print。So we're going to have an outgoing edge with a closed print。

 We need a new state 6 for this item。S goes to OpenPl Closepre。t。

 the parser is finished with that production。What else？Jumping back to state number three。

 there's one more outgoing edge we need to add what's on that outgoing edge？S， right。

 we still haven't dealt with。诶。This item right here， L goes to dot S。

 We can have an outgoing edge with an S， and our new item will be L goes to S dot。It's a new state。嗯。

All right。Have we finished with the DFA？We kind of found all these possibilities of items and the next。

Adding in outgoing edges for the next terminal or non terminal。In the item， mar。

We're going to ignore that EOF EOF is going to special just。You could treat it appropriately。

 but thanks for pointing that one out， Maddie five and five， what is missing in five？Well。

 I mean the S is okay， but the where it goes out to out dot。Great。

 so we actually have a couple of outgoing productions， right， We could read a comma。

 We could read the closed brand。 So we do need to add those in。 If we read a comma。

 our item is L goes to L comma dot S。 We then need to close it。 We need to add the productions for S。

 which we've done right here。😊，呃。Great， and now that takes care of state 5。

 I think we've got all the outgoing edges for state 5。 But now in state number 8。

 we still need to add some more edges。 We need to add outgoing edges for。😊，H。X。

For close pern and for S。嗯。If we adding in one step， the edges for。Sorry for open print。

 that takes us back to state 3。The x takes us to state 2。And。Finally， we need an outgoing edge for S。

 which will take us to a new state， L goes to。No。L goes to L comma S dot。That is our DFA。 Okay。

 we've kind of exhaustively gone through。 We've made sure that。For each state that we have。

 we've considered all the outgoing edges that is labeled by terminals or non terminals。

 We've created new states as needed， taking the closure of them and repeated this process until we can't create any more states。

 any more edges。What we're ready to do now is build the action table。嗯。

So our action table is going to be。For each of our states， we're going to have an action。嗯。

First of all， just as a special case， if the state essentially contains an item of this form。

We're going to accept right So this is kind of indicating that we've successfully pared the start expression。

😊，X， sorry is meant to be the start symbol here。We've successfully passed the start symbol。

 and we're at the。 we've done everything except。The end of file we're going to accept。

 so that corresponds to state 4。That I talked about， this says we've successfully pars。The do symbol。

If a state contains an item of the form， X goes to gamma dot。Well。

 what that means is that the PAza has successfully。Consumed and put on the stack。

All of the terminals and non terminals in gamma。😡，So the action we're going to put on is to reduce using that production。

 that is to pop gamma off the top of the stack and push exxon。

So if we take a look through at our states， that's going to be states2。State 6。State 7。And state 9。

Those are all and only the states that have an item of that form where the parser is at the very end of the right hand side of the production。

Okay。If a state。I has an edge to J。That's labeled by a terminal。

Then we're going to want to add a shift action。So that is state1。Not state 2。State 3， yes。

Not state 4， yes， state 5， yes， state 8。Okay， so it turns out all of the remaining。

States have their property。 right， It has an outgoing edge labeled with a terminal。

So this is our action table。😡，Now， to remind you what we're going to do at each step。

We're going to take the symbols on the stack as input。And starting from the bottom。

We're going to treat those as input to our DFA so that as we're going to go from the bottom out stack。

Through the DFA， and that's going to get us to a state。So in particular。

 what that means is if we get to a state such as state 9。

It's going to turn out that that means at the top of the stack is L comma S。Right。

 so that's why reducing is a good action。 right， It means that at the top of the stack is the right hand side of the expression of the production。

We can pop it off。Replace it with a non terminal L。Alternativelyly， if we get to a state where。

Wherere in the middle。Of a production。And we've got an outgoing edge with a terminal。Then next。

 the next action will be a shift。That is attempting to move on another symbol。Onto the stack。

 which next time will allow us to。Get to that same state and then follow an edge based on the terminal that's now at the top of the stack。

 taking us to a different state。So is that intuition clear？This idea that we have a DFA。

On which we're going to be taking his input， the stack from the bottom to the top。

When we get to the top of the stack， we look up in the action table and that tells us an action。

The reduce actions are going to work out， because。In a reduced action。

 the righthand side of the production is the thing at the top of the stack and a shift state it's going to work out because when we shift another terminal on。

 the next time we go through， we'll get to that same state and then we'll follow some edge for the non-teral we just shifted on sorry for the terminal symbol。

 we just shifted to the top of the stack， taking us to a different state。Okay。

 so is that intuition clear？About this DFA and the actions。Yeah， every state has to be。

And one of these three。Like is it not possible versus yeah。

So it turns out that as we are constructing this table。

 it's a problem if we end up with more than than one action。In there， I'll get to that in a moment。

 but。Let's work through this example first to see it in action。

 and then we'll think about how things can go wrong when we're constructing the action table。Okay。

 so is just what I said in words that。We run through the DFA using the symbols on the stack as input and so on。

And the current state of the DFA in the action table will tell us the next thing to do。

 either shift or reduce using an action。Thanks for the question。 we will get there。

 Any other questions at the moment about this example about any of the concepts。😊，Okay。

 so let's see it in action。Here is our gramar。Again。

Like we saw before we're going to have a stack and an input。

 we're going to be parsing this input open peren， X， comma X， close Peren。

So we're going be doing this thing about shifting and reducing。 But， of course， this time。

 instead of magically annoying what we're going do， we're going to use our DFA。😊。

And our action table。So that at each step， the DFA plus the action table is going to tell us whether it shift or reduce。

So。We start off。Would take from the stack。 We go to the bottom to the top， run it through the DFA。

 Of course， there's nothing on the stack at the moment。

 So we start off in state 1 and we end up in state1 and state1， we are into shift。

 So we shift the first symbol， the open paren。Onto the stack。Fantastic。Now we repeat。

So we start off with our DFA。And we start off in state one。

 we go from the stack from the bottom to the top。That is we follow this edge for open Par。

 and now we're in state  three。That's the end of the input。Of the， of， the of the stack。 So state 3。

 the action is。Shift， so we're going to shift ex to the stack。Fantastic。Now we repeat。

 We start it off in state 1。 We go from the stack from the bottom to the top。 So we do open peren X。

 And now we're in state 2。 State 2 says reduce using the production S arrow X。

 So that is we're gonna pop X off the stack。And replace it with S。Fantastic。Now， we repeat。

So we start off state one of the DFA。 We go through the stack from the bottom to the top。

 which is open peren and S。 And that takes us into state number 7。We look up in the action table。

 state number seven， we reduce using the production L arrow S。 So that is we pop the S off the stack。

 replace it with an L。Awesome。😊，Now we do it again， we start often state one of the DFA。

 we go from the stack to the bottom the top， open par L， now we're in state number five。😊。

State number5 says shift。So we're going to shift the next symbol。

 the comma onto the top of the stack。Great。Now we do it again。So we start from state one。

Follow the input， open per L。Coma。And now this takes us to state 8 and state 8， we're told to shift。

 so we shift the x onto the top of the stack。Excellent。Now we start again。 state number one。

 we go from the stack bottom to the top。 That is we read the open paren， the L。

 the comma and the X taking us to state 2。Look up state 2 that tells us to reduce using the production S goes to X。

 so we pop X off the stack。Replace it with S。Great。😊，O。And we do it again。 So I often state  one。

We follow open parenten。Comma。S， and that takes us to state 9。 State 9 tells us to reduce。

So we're going to pop off。L comma S from the top of the stack and replace it with L。Like， so。Awesome。

Now we repeat starting from state number one。 we follow the comma and the L that puts us into state number 5。

 We look up state number 5 that tells us to do a shift。 So we're going to shift。

The clothes per in onto the stack。Wonderful。And we start all over again。Stay number one。

We have an open par， an L and a closed par that takes us to state number six。

 We look up the action table， State number six， reduce according to S。

Reducs production S goes to open print our closed brand。

 that is we pop off open print our closed brand， replace it with S。Wonderful。Now we do it again。

 We start from state number one。And on the stack， we have an S。It takes us to stain number  four。

 We look up stain number 4。嗯。And we also check to make sure the input is empty， fantastic。

 we are ready to accept。😊，So again， an excruciatingly painful walkthrough of how to use this。

 Thank goodness， we have computers to do this for us instead of doing it by hand。

 but I really did want to emphasize this idea that we're using the DFA from the beginning at each step of the way。

 starting from the beginning of the input on the stack the bottom of the stack going through。😊。

And also， hopefully that idea that we're starting at the bottom and going through gives you some intuition for why this stack is pretty good。

Right？When we were constructing this DFA。If we got to a point， we were about to pass an on terminal。

Well， then we added in all the productions for the non terminal。

 And so what that allowed us to do was when we saw that first open paren。And we know， hey。

 I want to read an Nellnex， that actually broke it down into batting in these items。

 kind of gave us the next steps。It allowed us to figure out。嗯。Is it going to be the case that？

There's always going to be some non terminal that let us make progress and we were able to construct。

 okay， we do the shift。 We move it on。 I know I'm trying to read。 and， for example， N。

If I saw another open parent， you know that's allowing me to know that I'm trying to read an S。

 for example， so what we're kind of doing here in these states is it's telling us。

 when I see a non terminalal， that's allowing me to make progress on the production of which non terminalal or non terminalals。

Right， when we。Got to a state where the Psar Rmper was at the far right of the production。

 What that meant was at the top of the stack， we have that exact production so we can We're ready to do a reduction。

So you'll note that when we did， for example， a reduction from an L to an S。Right， that meant that。

Sorry， from an S to an L。That meant that。When we saw the open Per and we followed other terminals to take us into other states。

 when we eventually reduced it。To， let's say an L。We started moving to a new state。

 a state that was telling us， hey， you made progress on the production S goes to open Par L。

Close print right， So the construction of this DFA。Combined with a stack was allowing us to track。

 well， which productions am I in the middle of making progress on？

Any questions about the intuition of。This algorithm。Yeah。

 why don't we just follow D until we get to a state where the action is reduced and we' start at the beginning to save。

So this maybe leads us on to optimizations。 You know， I wanted to get clear this idea that each time。

 each step through， we start from the beginning of the DFA and figure out what we're going to do。

 But of course， a lot of the time with that DFA。Because we're only ever pushing something on top of the stack or popping something off and replacing with something else。

A lot of the time， particularly if you're deep in a past tree。😊。

The common prefix of the stackers are going to be the same from step to step。So clearly。

 one of the optimizations you can do is you don't need to run the DA from start each time。

RightYou can use the stack to also record information about which DA state you're in and then something like。

 if you do a shift， you know that you're just going to be following one more edge based on the terminal symbol。

 the token that was just red， If you do a shift and reduced， you're popping off。And that means。

 you know， you're going to be moving back to some state in the DFA reducing and you're going to be reading that non。

Going on an edge for the non terminal。 So I think that gets to what you were talking about。

 Why don' I just use the DFA until you know， you know。

 keep on shifting until you know which reduction you want to make more generally， though。

 this idea that。Yeah， just I want you to conceptually think of it as going from the beginning of the stack through the DFA each time。

 but implementation ways we do something a bit smarter。Another optimization is of course。

 to combine the DFA in the action table into a single lookup table。Would let you。Figure things out。U。

Any other questions at this point？Okay。Some of the limitations， this LR0 machine only works。

With reduce actions， if there's a single reduce action。So。That is the way we phrased it。

 each action is going to have a single。 each state can have a most one action， right， either shift。

Or reduce， according to a particular production。You might have more complicated grammars where when you're constructing the DFA。

 you can end up with what are known as conflicts。Conflict might either be a shift， reduce conflict。

Or a reduced， reduced conflict。 And The idea is that as you're building up the action table。

If you end up with wanting to both shift and reduce。In the same action。

 that's a shift to reduce conflict。 that can arise if you have an item where the PAser is at the end of the production。

 So there you'd want to do a reduce。But also， there's an outgoing edge with a terminal symbol in which case you want to do a shift。

You can also have reduced， reduced conflicts where you've got more than one production。嗯。呃。

More than one production that's in a reduced state。

So if we have a state that has just a single production and reduced state， fantastic。

 that means we're going to be clear on the action。😊，If you。

 if we ended up with a state where one item was saying you want to reduce。

 but another one was ending up saying you want to shift because remember。

 we'll end up adding in the productions for L， which。诶。嗯。We'll end up having a。

Having some outgoing edges with terminals leading to a shift reduced conflict。

Reduce reduces when you have multiple items where the parser input is at the far right of the production。

Some of these conflicts can be resolved if we started looking ahead。

 So the example we went through was an L0 grammar。Or rather an L0 PAza。

 we didn't have any tokens of look ahead。But。Most programming languages would actually use an L R 1 P。

 So that is， it's okay to have states。呃。It's okay to have states like this with a shift reduce conflict or reduce reduced conflict。

 And what you end up doing is。In particular， through a reduced， reduced conflict。

 you will look K symbols ahead。And this is essentially on the idea of using the follow set。

So if you remember from last class， we looked at using computing first and follow and nullable sets。

啊。And。In an LK parer， an item is both a production with a PAser point and the next K tokens。

That are going to be on the input after you've finished passing that item。

And what that means is when you get to a reduced state。

 you can look to see what the symbols coming up might be。And look ahead。

 and that might be able to tell you which production you want to reduce with。

Based on what's coming after it。Right， so this will help you have fewer， reduced， reduced conflicts。

 But say if we're doing L R 1。It may not be enough to actually completely figure out which reduction I'm meant to be using。

Okay， so even with LR1 or LK for any K。We able。Figure out which action we want to do in a particular state。

In more cases， but we mightt still end up with conflicts that we can't end up resolving。

So that was my very big hand wave about how we extend to LK。

The items end up with K tokens of look ahead and use it to disambiguate， reduce， reduce。

Conflicts often it doesn't really help you。 It might help you with a shift to reduce conflict if you can look ahead and see whether this reduction makes sense。

 given the next K tokens。 And if it does， maybe you。Lean towards the reduction。

 otherwise you do the shift， that might be one way of resolving。嗯。So in general。

 LR1 is actually used instead of LR 0 or LR 2，3，4 and so on。

I sketched out what an item is now it's a pair of our item and the K tokens。嗯。Right。

 and you can imagine that the action table now has。Columns based on the K tokens of look ahead。

 similar to the passingsing predicting prediction table。

 the LLK tables we were constructing last class。Okay。嗯。Let's dig a little more into conflicts。

 Let's suppose we're doing L R 0 again for simplicity。 So no tokens of look ahead。嗯。

And let's take a look here at。Two different grammars for the same language。

So this is simplified expression grammar。They're identical。

 except for this first production in both the grammars。One， production is left associative。

That is the plus symbol we're recursing on the left。

So if you think about the powers tree for addition。

 where treating that binary operation is left associative， you do the operations。From left to right。

And this one they right associative。Now， one of these grammars is L0 and the other one isn't。

So that is， if we did the El construction。LR0 parsa construction with one of the grammars with an action table that was all completely fine。

In the other grammar would end up with the conflict。So what do you think it is？Which。

Grmmar has the conflict， which grammar has the problem。Yeah。

 associated because once you get to it in E， you don't know whether to reduce the S right away versus。

Keep going to get aless。 right， That's that's great intuition。 So you're right。

 the grammar on the right， the right Assoative of grammar gives us conflicts。😊，Particularly。

 it gives us a shift to reduce conflict。 You can imagine that you've just passed an E。

So some are other at the top of your stack is an E。😊，So。Will it。

We won't know whether we want to do a shift to shift the plus on and start and keep on going with that item or if we want to reduce。

And replace the EU with an S。So it's often the case that。

The ambiguity that arises from associivity and precedence。

Of operators gives rise to shift reduce conflicts。Right。

 one of the most famous kinders known as the dangling else problem。

 So this is because a lot of languages have productions that look something like this， right， F E。

 then S 1 else， S2。RightSo an if then statement where the else is optional。

 you might have both the then and the else statements。

 or sometimes you just want to write if E then S。So this gives rise to a shift reduce conflict。

 If you've read if E then S， you're typically not going to know where you want to reduce。

Using this production or shift they're else on。And really。

 what's going on here is it's about associivity。 right， If you ended up with multiple。

 if you had nested if statements。Then， you know， F A， then F B， then S 1 L， S 2。

 The problem is that it could be。The ambiguity is really whether or not this else should belong to the innermostif or the outermostif。

And that decision。Intmost stuff or outermost stuff is really about when should you do a shift versus a reduce？

If I'm in the middle of pausing。です。If expression， should I shift the L on and and bind the L to the innermost F。

 or should I do the reduction。嗯。U。So how do we deal with these shifts to reduce conflicts。

One of the things you could do is actually try and rewrite your grammar so change your grammar so that we avoid it and so in the case of the dangling else problem。

 here's one way of rewwriting the grammar that you can do it。Essentially。

 we have this new non terminal O， which contains statements， and we O goes to if E then O。

Or it goes to F E then C else O。Right， and then we end up。It turns out that we can avoid the。

The shift reduced conflicts。The arrays I'll let you kind of walk through that or even better try running this through a Pas generator tool and see the results of what's going on of way this turns out to work。

So refactoring the grammar is one thing that you can do to avoid shift reduced conflicts。

Another thing that works in various common cases is actually just tolerate the conflict。

 but give your PAer generator， your PAser some indication of whether to prefer a shift or a reduce or a reduce of which production。

So， for example， for a dangling else， you might say， I prefer a shift to a reduce。

 That is the else should bind tightly to the innermost de， right， If you end up with a conflict。

 you should prefer to shift the else onto the stack。

So preferring this structure instead of the other one。嗯。And in general， for past generators。

 most or many programming languages contain expressions and because of the issues about precedents of operators and associivity。

 you can actually express operator precedence you whether you should with a multiplication should bind tighter than addition。

 for example， simply as resolving conflicts by preferring a shift to a reduce based on the next token。

Right and so what that means is most par generators have some nice handy shorthand for you to talk about associivity of operators and precedents of operators so that you don't need to refactor your grammar to let it work out。

 but instead you just say， you know， the times has a higher precedence than a plus。

 and then what that translates into。The L R grammar。LR power of production tool， just preferring。

 for example， a shift versus a reduced depending on the next look ahead。

 the next token that's in the input。嗯。😊，You can in general。

 in a positive generator go in and quite possibly tweak it to tell it whether to prefer a shift to reduce or vice versa。

 But in general， you only want to do this very sparingly in well understood cases。

 So things like a dangling dangling else， things like expressions。

 arithmetic expressions or operators and describe operator precedence。 a lot of the time。

 if you have a conflict in your positive generation， it's because you've got。

Something that isn't quite right about the grammar。 Maybe there's actually an ambiguity in there。

 maybe there's something that isn't clear。Okay， I've been alluding to these par generators。 and。

 in fact， there are。A number of parer generators that produce these kind of bottom up LR PAss， Yk。

was developed in the early 70s and even by that stage， there were a lot of par generators。

 yet another compiler compiler， so a technique for you know。

Compiling a tool to help you build a compiler。 Yak has essentially been re implementedment for a huge number of different platforms and languages。

Berkeley Yak bison， the Ocaml version is Ocamel Yak。It produces。

Jk actually produces an L A LR1 PAser。 L ALR1 pasing is very similar to LR1 pasing except it's reduced the size of the DFA by merging some states together。

 It does lose a little bit of expressiveness in this。

 So there are some grammars that are LR1 that are not LA ALR1 but for the examples we see in programming languages。

 LLR1 is typically okay。Min here is an ocal variant of yk。

That in their words is 90% compatible with Ocal yak。

But it adds a few additional features to be better at explaining conflicts。So we're gonna just。

In the next 30 seconds， take a look at an example。 The structure of a in here file is a header。

 which is some arbitrarycal code， some declarations， for example。

 of operators and their precedentnce and associivity rules。 So these are the productions。

 and then the trailer。Which is again， arbitrary Ocal code that's just directly copied to the output。

The declarations I mentioned is tokens， dart symbols， associivity precedents。

 the rules are productions for the non terminals， they also include semantic actions。

 so essentially oaml expressions that are the result of parsing that are used to construct the Pas tree。

嗯。I'll let you look at the slide by yourself。Part because I just want to very quickly。

Here's an example， Pas of file which is doing declaring the tokens that are going to be produced by the Lexa。

 declaring operators with their associivity and the order that they're listed in actually describes the precedentnce。

 so this is essentially times and division is going to be tighter than plus minus。

The start symbol is the program non terminalminal and the result of passing a program should be an AST expression。

 the result of passing an expression or a binary expression should be a value of this type。

 AST expression。And then here's the grammar。嗯。These doacine symbols refer to the result of passing the first or the second。

 third， fourth。Elements in the expression and so on。嗯。

One thing I want to show you just super quickly， here's another grammar file。

 It turns out to have conflicts。So I just want to show you that when you run min here。



![](img/597212da6b0bac2813040de28b7cf9c8_1.png)

嗯。You pass and explain and dump。Prameterters， what it will do is it's going to dump the DFA。

 so you can actually take a look at the DFA to see。What is the thing that's being produced。

 How's it working， This is kind of describing what's going on。 You can。

 so you see here the parer items that are appearing。 this is like I said an LA LR1。

 So these are also showing the K tokens of look ahead。嗯。But then this one actually had conflicts。

 So it's showing you the conflicts that are involved。

And it's also showing you example programs that might demonstrate the conflict。

 so demonstrate what might go wrong。So that's why we're using men here。 essentially。

 it's explanatory capabilities。 And you'll be using men here in homework。

F that we'll be releasing today when you flesh out the PAs for this language out。

Apologies for going over。 Thank you all very much。 Good luck finishing up homework 3。

 Good luck with homework 4。 Keep well。 Keep safe。😊，は今です。と个わ了。そか。嗯。さゃ。それではわさしたいです。あのこぞます。

I feel it was biking。new bike。Thats similar。Well I admit。

 I almost made it like I count like the title。あるま。You don't need to check that。呃。Yeah。

 you're going to need to。ははいさははい。the L on is not well time。my。

where otherwise should have you can assume that your line will be given wealth and if you haven't。



![](img/597212da6b0bac2813040de28b7cf9c8_3.png)

。小吧就是。嗱。let's go back to the most。Its name don too。啊。I was just wondering whether about that。Yes。

 the out。I'll。八。Yes， it will always be the case。I'm want you。Sorry。いま。最まに？

I assume so because all the pieces in our case， in a well formed。Is not technique given。M my。

otherwise shouldnt you can assume that your line will be given well homell be and if you haven't。

我年会得有。吃饭就。once your。s go back to the。哪个意思 don't say。So' here。I was just wondering。Yes， the out。I'll。

还是。Yes， it will always be the case you have。I'm everyone watching you guys。Sorry，いま。

I assume so because all the cases in our case， in a well form。



![](img/597212da6b0bac2813040de28b7cf9c8_5.png)

。