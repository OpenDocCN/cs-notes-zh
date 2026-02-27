# UIUC《算法与计算模型｜UIUC CSECE 374 - Algorithms and Models of Computation 2023》中英字幕 p08 20230914-Sep 14_ Context-free grammars.zh_en -BV1Mh7RzaEL2_p8-

![](img/87897f3e87fb15dffac1e435762db4ab_0.png)

O。😊。

![](img/87897f3e87fb15dffac1e435762db4ab_2.png)

You为。

![](img/87897f3e87fb15dffac1e435762db4ab_4.png)

嗯，有一先好老。Whatt mean。😀Yeah。は在。我的。Okay， let's go ahead and get started， thanks everyone。

Just some quick reminders。嗯。We have a midterm coming up in a week and a half。Today。Yes。

A is the last material that is going to appear in the midterm， so Tuesday and Thursday next week。

Thursday definitely will be just a review and I will literally walk。Affect mid term。

And to solve everything。Tuesday is still a little bit up in the air whether to talk about turning your means so that you turn before you graduate or whether to maybe step back and go through some of the earlier group。

Oh。Giving more examples in practice。Opinions about。To。Or a discussion。

I've been going the other direction。This does mean since we've got a term， we do have a。发回。

If you need to take conflict exam for some reason， there's a registration form that you need to fill out by the end of next week。

So that we know how big a room to get and so on obviously we understand that like if Sunday you。

The shower and break your arm， yes， this has happened you won't be able。regular exam。

So if something happens over the weekend after the conflicts form is supposedly due。

 we can still work on it。But the other aspect of this。You。Have an accommodation like for Dr。

That allows you extra time on exams generally or low distraction environment for others like that。

 generally easier for everybody for you to take the exam at the Test accommodations center。

That's not a requirement， but it's just going to be easier for more schedule flexibility。

Better low distraction environments than we might be able to provide。

If you do want to take your exam。Sen， they recommend making a reservation at least one week in advance。

That means。It's kind of your deadline， it's a soft deadline。

 but it's pretty strongly recommended if you need to take an exam as。And then please don't forget。

There is a homework due Tuesday。start working on it the office hours yesterday were pretty sparse my guess is because there was a career fair。

But you know it's always a little bit worrying nobody show up to ask questions about the the next the next homework。

 please do start on it， it's going to be important to look at this stuff really。哦，O。

Partly because some pieces of it are going to show up on the exam。Okay。

I'll say more about the logistics and the coverage of the exam on Tuesday。

 but for now are there any other administrative or logistical questions？Yes。Thanksて。That is correct。

 the solutions for yesterday's labs still haven't been posted yet。

 I'm revising the solutions in response to some feedback that we got from the students。

So thatll be posted this afternoon。Okay。So today。嗯。I'm going to。Introducuce， reintroducuce。

 talk about。啊嗯。MyMy favorite。Repect。Recursion。And you know。

 this is something that we've seen in advisorises for。

 but today specifically I want to talk about recursion in the context of formal languages so in the past。

😡，Eaves。Its。Some level encapsulate what one can do purely easily。😡，So you have。Sequencing。When you。

 you know can cattic things one after another， you have branching， which is well。

 either I'm going to do A or I'm going to do B。But if then else statements in your code。

 sequencing just means you've got lines of code and they're going to be executed in order or blocks of code and you put one after the other。

 that means stuff later one's going to be executed after the former one。And you've got。Repetition。

Or looping。This is the cleaning star operator， this is a while loop。And at some level。

 we're all regular budgets。Regular expressions， DFAs， NFAs。

 these weird transformations that we started to do earlier in the week。All have to do with。

The universe of language we can build using these three simple components out of individual strings。

Or if you prefer out of individual characters。But there are lots of languages that you can't build this way。

😡，so the canonical example is。All strings containing some number of zeros followed by exactly the same number of ones。

 this cannot be represented。By a regular expression。

 this cannot be accepted by a finite state machine， but nevertheless， its structure is simple enough。

That you can recognize things that have this form。If I give you to zeros and ones。

 I ask you whether it belongs to this language。😡，Well， it's a simple strategy。

Count up as you hear the zero and then we start hearing once you count down。

And when you get to the end of the string， if your count is equal to zero， you say yes。

I counted down for zero， I ended with my counter equal to zero。So I heard just as many ones as those。

Yes， and if you ever hear a one， you know， zero after one， you just say no， that's the fabulous part。

😡，You had to keep this counter in your head。嗯。Now， let me give you another version。

Of exactly the same language。Instead of my alphabet being zeros and ones。

 my alphabets going to be left。This is a very， very narrow simplification of something more interesting。

Essentially， I want to pronounce that left bracket symbol hook。Right， right。And you're asking now。

Is given a sequence of pushes and pops。At。First of all。Pro。We without any。At the。Of the sequence。

And moreover nevertract。Never left anything behind them on the stack。嗯。So these kinds of。Patterns。

Our。Absstered by。A larger set of languages。Which are called context free languages。

And the missing ingredient that's added but context free。Is recursion。

And the kind of recursion that I'm talking about here。

 if I want to recognize whether I have a sequence of pushes and pops。

All cops that leave the stack cleanly empty。I can think of it as the thought。Oh。Thank you。

Listen to the sequence of fishes and pops until you sta。Oh you're done， thank you。Pop， yes。

 the stack is empty。😡，Hey。😊，So。They actually the versions。

I call some function recursively that involves recurs onto my recursion stack。

 I get the results by popping the back off the recursion stack。

So this pattern is sort of mirroring something about the way。😡。

Recursion works is a very simple example because all the pushes conversed。😡。

And all the pops come after， but it's enough。Of need for recursion that it can't be captured by regular language and it's enough for need recursion that anthropologists and languageuists have put this forward。

😡，St check。From others。We can use that language recursively。😡，I could。

How we discuss the bylaws for the？Of。Cls， which is likely to be spun up。We get the donor。

Being negotiating overpaying rates， I give lots and lots relative clauses after this and you can follow along and you're not getting lost。

Hopefully。You know， with the right context， if I you。

 I could say a similar sentence with lots of relative clauses about you know。

 adventure time and maybe more you would follow a little。But we're used。And it don't。

Sentnates can have nested clauses inside the them。And we understand though。嗯。

German has a different sentence structure than。English so in German。

 the verb always comes at the end of the sentence， and so it's not terribly common。

 but it's certainly plausible for a German sentence just to end with nine words。

And herman don't get lost。Because they deal with this recursive structure in their mind natively。

 it seems to be something built in human brains and it's not only in language it's also in there's this is a paper that describes patterns in。

😡，嗯。that。We think。There。sortrt of arbitrarily far back in the past in order to continue the pattern and that required more complicated than a memoryless procedure that could be modeled by a DFA。

Now of course， the moment that anyone theres to stand up and suggest that humans have some quality that other animals don't。

 very quickly there is evidence to the contrary。So there's。That the theories。三度。Also。Oh。

They're things like people have claimed humans are the only species that build tools for building tools。

But this isn't true， we've seen other primates， we've seen ravens and crows。Very。

 very complicated sequences of coding and tool use so no。

You might be better at it than other animals。But as usual， this is just part of having the brain。

So this is really cool stuff and it's also arguably the thing that unlocked。😡，If not civilization。

 at least。😡，Computer science。So at least we can point to recursion as probably the single most fundamental fundamental intellectual idea。

Created computing in the early 20th century。And context free is really where we first start seeing it now in the context of languages。

😡，好吗。Linguists。Since about the 1940s。Have tried to use recursive structures。对。So， this is a。

Context free grammar。嗯。Things aren that you see here on the left。

What we will refer to later is non terminals you sort of。😡，Tll units are set。あるほど。

Noun adjective phrase， verb phrase， and then simpler things like nouns and verbs and adjectives。

Possessives， that's a special kind of adjective either is a possessive form of a noun phrase or a possessed pronoun and you can。

Build these， build sentences。By expanding these tokens， so say every sentence in this very。

 very simple model consistent noun phrase followed by a ver phrase。

And so this noun phrase could consist an ajut phrase and a noun， and you expand it out enough。

And you eventually get the sense which is utterly meaningless， but programmmatically correct。

 your furious green time Lord barely mangled my dog's trousers。😡，AtGT， this is what it does。嗯。

Only it tries to make the sentences look more like the sentences thats on the internet。

linguists use this to model。How sentences are built。😮。

And so our language models use much more complicated grammars。😡。

Sentences recursively into smaller and smaller pieces。

And put weights on how likely certain ways of expandingning these tokens are to generate text。

Now we briefly。In the context of regular expressions， saw something similar。😡。

This is usually referred to in compiler land。Ass an abstract impact tree。So。This is a tree that。

The recursive structure that should pop into。When you see your exception。嗯嗯我。ok。

Your eyes should eventually grab towards this plus near the beginning as sort of the task operation that top。

😡，And then it breaks it into two subexs。W which I then recursively decompose。

Using nodes here that represent either an ore or a concatenation or a clean closure。

The coolr thing when you see any sort of algebraic formula。You learned。W right。Edma。

 for what order you should do， prioritize things。Really teaching you is how to translate and experiment an algebra into one of these trees。

😡，Where you。Look into recursive sub formulas， which are。You。

With pluses and pines and exponents and things like that。In your compiler in every every compiler。

 every interpreter， whenever you write a regular expression that's being parsed by some regular expression library when you write。

😡，Interpreer compiler is building a structure that's like。Following the rules。

That looks like that only instead of sentence down phrasese， adjective phrase。

 it has things like regular action factor term。😡，U。You know。

 other things that mnemonically refer to different kinds of structures inside the expression that you're trying to represent。

So。And these are things that you can't do with regular expressions。😡，Because if you'll notice。

 you've got， you know， aject to phrase nested inside aject to phrase。

You've got concatenation nested inside concatenation， nested inside concatenation。Um。

You're reading the formula like this。😡，Do it really print like this cat？Just a raw string。Over the。

Look at your left structure。😡，We build out that。Then。First。U。So I would read the structure。

UmAs zero star concatenate zero plus cacatenation of zero star with concatetnation of one with。

 et cetera。A DFA cannot recognize。😡，YouWhen you scan through。I'm out。

Because you need to know that you go down and up exactly the same number。In order to make this work。

York。How。At a minimum， you're in the tree。How many you've gone？

U you'll know when you get back to the route。And this is exactly the unwanted to the un pattern that can't captured by DFAs。

🤢，So we。AMore general structure in more general way of representing languages in order to capture this。

Useful， sort of arbitrarily deep。Structure that we want to capture and。U。Great。B。

So that's kind of the motivation。But let me give you a。

We stop and first ask if there are any questions， yes。Every。

Can be composed to one of these regular question trees。

I remember following the definition of regular expression， it's one of these five things。

 The empty set that's a leaf， a single string that's a leaf。A or B。

 that's a or node with A or B subtrees， A dot B， that's an dot node with A or B subtes。

 a star that's a star node with an A subree。啊嗯。And all。Let me to make sure I understand the question。

 can all the BfaAs that match this regular expression be turned into？synyntaxt tree。Sort of。

We have a mechanism for turning regular expressions into NFAs。Called Thompson's algorithm。

Johnson's algorithm morally。😡，Building this tree。And then instead of just making it look like a tree。

 able to。And thated parts of an NFA。And so then。With DFA and then complete the circle convert a DFA regular compression round and round。

 but one of them。Sm。This tree。Okay。So I'm going to write down an example。

In the form that we would normally write it down。Sorry， that should be zero， not a big big。诶。

So this is。Untex free。Describes a set of strings。Called a context free language。So grammars are like。

expressions there're a compact description of the set of strains。So。Is the language？系。Um。

So what are the components of this thing？Actual characters that I want to output。

 so make sure that I emphasize those。I'm going to。But you know。You highlight them in red here。Second。

Alphabet。Which。We're called the none。Non terminals。In this case， S ABC。He represents。

Intermediate structures Senates noun phrase。Oh。These are。These represent structure。Compposed。

You think these rules。Okay， so I have production rules。嗯。The union of these two alphabets。

 so here I see the production rule B goes to C1。😡，C1 is a string that。Is an terminal。

 the second character is a terminal， it's fine。Down your bottom。

 C goes to0 C1 is sort of a these very like。I always have only one non terminal on the left side of the arrow。

 but I can have an arbitrary mixture of things on side of the arrow。嗯。And the spec starting nonal。

Which traditional is is called apps。This is the top level structure stood in。Okay so。

Those pieces of my contextory grammar now this is just syn。What this actually means。

 so I want you to imagine that these things that I've written down rules。

 these are substitution rules which I can apply in it。😡，Many times I like。Sting with。Single symbol F。

And。Well I can substitute S， I can substitute A。It's the very first production rule。

And then for an A， I can substitute using the third production rule0 a， and then again。

 I can substitute A for0 a。And then I can substitute A for0 c。

 and then I can substitute C for0 c1 and then01 again。And then finally。

 I could just substitute C to the empty stream。In each of these steps， example， I'm taking。😡。

Single non terminalminal。And I'm substituting。The right side of some production rule for that rule appears on the left。

In this example and in this example， every single one of these strings that I'm playing with had only one non termlet。

 but that was just an artifact of the example primer if somehow I had managed to find myself，In this。

Weird。State。Then the production rules would allow me。To。Substitute for the sea。F in。1。

So that one application production rule， but I didn't I just chose to see non deterterministically。😡。

I decided that was the right one to expand， but I could have also expanded A， could have expanded B。

 it could have expanded the second A， doesn't matter。

If it's possible to get from S to a string by applying these production rules。

 we say that the grammar generates。😡，So。Again， back in sort of intuition here。

I have a grammar like this that captures some interesting fragment of anglek。😡。

Then a sentence is grammatically correct within the tract of English。

 if I can generate it by doing these kinds of substitutions。ing tokens。

 these things in brackets with。Of tokens and raw English words have on the。Okay。

 so that's what it means dramatically。Is that the grammar can generate that sentence。😡，Here。

 instead of sequences of words， I'm generally looking at。But what just happened？Sequences of symbols。

They're the single characters， but the idea is exactly the same。So。Let's take that。Well。That right。

Also。Yes。Okay。Ex simple。不知道。That starts at us。Ands at W。And maybe I should spell that word correctly。

哎。😊，嗯。Now I've written each of these。😡，Prodion rules each of these production rules on its own line。

Normally we like to compress things so the way we do this is。Geneerically right。成如。Oh look。

On one line。So the way it would write this same grammar more compactly。

 so write S goes to A or B A goes to0 A or0 C， B goes to B1 or C1 C goes to empty string or0 C1。

This vertical bar means or。😡，Yes， that means we now have four symbols that mean or。😡。

We're talking about sets。I'm in one set or the other if I'm talking about formulas。That little deep。

If I'm talking about regular expressions。I'm talking about context for grammars。Or Missouri sorryari。

I don't make the rules。We stop this one。This is just what we're given。This is really called。嗯。

Back this an hour。哦，说了。Is this the name of the tus？Okay。嗯。So we I've got a grammar got。啊你。

But I will talk about life。This is。A packed description of some kind of language。

 some kind of strings， namely the set of all strings that this grammar could possibly generate。

So let's see if we can figure out。😡，What that language is。Okay。

 now generally we don't want to figure these things out starting at the top and working our way down because the you know I can't figure out what S is because it's going to depend on A and B I can't figure out what language A represents because it's going to A and B so I'm going to start down here at the bottom。

😡，And see if we can recognize a pattern。not starting with S but just starting with C。不知道。Just try。嗯。

Expanding some things。So here are some。Springs that can be generated with sea。

I can apply the more complicated rule， I could apply the more complicated rule again。

 I could apply the more complicated rule again。And then I could stop。By generating that。So that is a。

Typical string。That I get to by starting with the non terminalminal C and applying production rules。

At page you'll notice I only have。Right。And so。I substitute C for0 c1。😡，And therefore。

 I need to continue。Or do I substitute C for epsilon and therefore I'm done？

So the only choice I really。😡，How many times am I going to apply the？The rule。

So if I applied the rule， the expansion rule， the more complicated rule three times one， two， three。

 I get threearrows followed by three ones， and then I pull the out by substituting in the empty strain。

Yeah， wouldn't this speak non regular？Yes。So what language is this？

What strings can I generate starting from C？系。什么。an equal number one after。That's exactly right。

This is the canonical non regular language。😡，Schome number of theories is followed by exactly that same。

And exactly。Intuition， I sort of tried to watching your brain at the beginning。

 pronouncing the zero push and pronouncing one pop。😡，The event is。You've got to stack。

You can either be done。not do anything with it， Or you can push。But。Let the。

Veryrry play with the stack and then pop that thing back off。

And as long as you can know the recursion fair， between nice and empty。

 except for the thing you've done。You're cleaning him。So。

The non terminal C generates this canonical nonran language zero to the n to the n for all non negative n。

嗯。Now。😡，Starting from here。What do you think B generates？So start with a pe。

I have a choice of either。Writing one onto the end。Or writing a C。And the one onto the end。

I know what he expected。See he's bringing to its fans to。So。What does big gives me？

So instead of zero to the n1 to the n， I could say it is zero to the n one to the n and play a。

And is anything in K is positive， but the more。Right， so these are traits that model。

I do a bunch of pushes and then a bunch of pops。But I must try to pop from the like at least one。😡。

I'm flowing this deck。Okay， so what about， what about A？Here my decision is basically。

How many zeros do I write at the beginning of this price？And so the language did nonly describe。Yes。

Yeah。Once again where。Yes。So this is push， push， push， push， push， pop， pop。

I don't underflow the stack， but I also don't clear it， I do more pushes than pops。

And then following。So how would I describe the language generated by us？Okay。

 and0 to the M1 to the n。Where。Either M is less than n。Or M is bigger than N。

So how to write that with only three symbols。It's not。Okay。So。

Another way of writing is you know s is zero star one star minus C。

 so c is zero zero is in one the number s is zero is followed by ones V。诶。嗯。

So does I need to stop here and make sure that。If people have questions。About this example。

I had a chance to answer。Whats sorryrry， what is the question？How do I get the middle too？

So let's look at this one。So。Every time I apply the rule B goes to be1。😡。

I'm explicitly writing a one into my office strength。Not negative number of times。

Then I apply the rule B goes to C1。😡，So at this point。BIt generates。You know。

 it's sort of the intermediate stage。Is。When I switched from playing with B is to playing with C。

At that moment， there was at least one about some arbitrary policies number of ones at the end of the string。

And now C， I know generates strings because the sum number zeros fall complete that number of ones。

zero is followed by example ones following more。And I've just written that more compactly up there as the number of ones and is bigger than the number of zeros am。

That。Being generated these various con terminals。Are non regular。So on。Languid。So here is an example。

And would you might recognise？S goes to zero S or S1 or epsilon。Okay， so I have a choice。

I start with the asks。Essentially I have a choice as I'm generating。

 what is zero to the left of the S or one on the right side of the S and I can either one of those。

Pt that I play。And so what this is going to generate is the regular language zero star1 star。Yeah。

It can be context free grant。Terminals。Triic。Production。B。Need one more production rule。

IfAt us to all of the accepting states so it's。It's fairly mechanical proof， enlightening。

 but it's worth remembering that regular。Languages。Or。All。Context free。On the other hand。

You've seen examples of language the not。😡，And the one canonical examples zero to the n one to the end。

 that turns out to be context free。😡，All are context free。So not all languages。Are context free？

And the two canonical examples of this。Or。Z to the n and one to the end， zero to the n。😡。

So now I have got three different runs that all have to be the same way。

Tuition you should apply here is。嗯。Push the stop。And so I could imagine using stack to match the zeros at the beginning of the string to the zeros at the end。

 but I have no way of。M break accept the stack， so I have no way of checking that。It number of zero。

Good。Here is。And。Remember what end is？Another way， another one。嗯。

Stngs that consist of the same string twice a row。😡，So the string AC Act， for example。

 is in this language。The string of。010010 is in this language。It's not pal。

 I'm not reversing the time， so it's followed by exactly that same string again and here the intuition is。

😡，Stacks reverse thing。When I push things onto the stack in one order。

 I pop them off in the opposite order。And so。To access， you know。

 I can non deterministically maybe guess where the boundary between the two copies of the strings are。

 but when I need to compare。First character。Because it's buried deep inside the step。嗯。Unfortunately。

 there are no。Har enough。T of the language。No such algorithm， there are some rules of thumb。啊，对。Yes。

 if you no， its the thing。It's not as nice as regular。What is。So麻没点。哎。对。

The reason that call contact free。Is what this substitution rule？Sorry， that's not the one I wanted。

😔，So the subst rule says anytime I want。I can replace。A single non terminal。嗯。

I have a production role。It doesn't matter what's near。😡，Should we get rules of the？

Here's a substr substitute for this other substr。So you have to look at larger pieces of the pattern。

Wwhich might include non terminals and might not， and then you you do the so you need more context to decide whether you can substitute or not。

Okay， yes。We are not going to see context。ふ。I actually anyone who really careed about context programmers anymore。

 sort of an intermediate state between。You know there's regular languages which are really useful for simple pattern matching。

 there's free languages which are really useful for more complicated structural pattern matching and the next about thats interesting。

Recursive languages， decidable languages。You can write code about。😡，And in between。

 like there is an algorithm to decide what is in the language。

Then you say that the language is decidable。嗯。The context sensitive is this weird middle ground。

Where it's work and context。在。You can capture all things that can happen。

But not the way that anyone seems to find particularly interesting these days。

The person who came up with this hierarchy。😡，By the way。Called the Chomky Hierarchy。嗯。

I'm pretty sure Nom Chomsky would prefer to be known for something other than this。

He's a pretty pretty vocal about his left wing politics。

And I think that's really how he identifies himself。

 but this is where his name creeps into our cricket。After。哦欢迎。

Onto another example of a context gra gramar。Yeah。I'm sorry， could you ask the。

The zeros are generated by nonfiminal C。So in third rule。I goB2B one and then not to be。But。

I have to switch to B toC1。And at that point， I've got a C in my string。

Now it is possible one of the strings that you can generate with from non terminal B is just a string of one。

That is history。We want together where is people。0。嗯'。Think if that fits that pattern。

Did't go to eon then wouldn it be impossible to create a this is a good point thank you I didn't have this production rule C goes to epsilon。

Technically， this would not qualify。Eventually。Right now here I get to decide when I'm doing the generation how many times and I can go。

 you know， I want to。Spans C into0 C1， a Google P P that's fine， but Google Ps is still finite。

Just at some point I have to make the decision to go to Epsil。Yes。

 it could go to some literal or some literal string。It wouldn't have to be just the empty。Okay。So。あ。

呃。We've gotten from。😡，Grammar to language， let's see if we can go the other direction。

But balanced strings of brackets or parentheses or braces or but let's just go with that since that started that way。

A balancing of bucket could look like this。You can also start happen you morning。Of pushes and pops。

Right， so。Let's string brackets。Is balanced if I interpret them as instructions。😡，不。Second and。

Quickly， okay pay for。No我。U。So。Let's see if we can come up with a grammar。That represents。

All possible that generates。Aactly the strings over the alphabet。Okay。That are balanced。

And I want to。 a sequence of balanced brackets。And。😊，Getit up and color。

Prackets and maybe with some little characters。Yeah。Cracktets， left and right and then。Okay。So add。

Okay that piece for the。Of para ofras。Well， I want to be a little bit careful here so this suggestions。

 I started with a pair of brackets and then I could add stuff in the middle on left on the right and it's true in the middle I can stick any other sequence balance string of brackets。

我's。Things are a little bit more complicated because I could put this on the left and that on the right。

And。Perkely balanced string of brackets。But the piece that I put on the left isn't。There's something。

啊灰。Again， this is exactly what distinguishes context for from。

In create with us just starting with Cal Ras。So this is the suggestion is can we start with the outermost brackets and this is actually the right。

With the big。Get smaller。InPro。The ways generate。Is sort of top down， not bottom up。Next slide。啊不吧。

一是。The first version of self or image。I so。Whatant to be。Or in the syntax of complex programmemmars。

Yes。As go to。You have work。嗯啊。Okay， so the suggestion is S should either go to two ss in a row。

Or it should go to a left bracket followed by an S followed by right bracket。

If you figure that out and look it up。Okay， so where did this come from so look at the example up here。

 I think I've drawn this example correctly。😡，The stack is empty here。😡，Before I start and here。

And here。So one possibility for a string of balanced practice。😡，De。不知道。Comsable for point。

Depenent string about。And the ps go that。It's own independent stream Dallas practice。

So this is the first rule。That could go a sequence of balance brackets could be。😡，Thanks correct。

Get back。Around some intermediate point where the stack is in。

The other possibility now if I look at the left side of that is。String that I have heat， no。

 that's not what I wanted。This string that I have here。Assuming I've got this right。

 there's no intermediate point。In this， when I read through these instructions sh and popping。

 where the stack is empty， starts that empty at the beginning。だからね。pushush， pop。

 push push push push pop。And this the sex sent again。Back。3 last。可以。This push。

And this pop mapped each other。It's the same item。AndNow if I ignore that push that。Or right what。

It's what I have。That lead。So it's sort of like I put one。😡，还没有。

Constructions and at the end of those instructions that。Is back at the top of the staff。Those。

Are the。About spray。I'm a little。对不。For this language。Okay。The only ever language。If not。No。就是。

There's one way to think about these things。I'll actually show you。In the second。对。If in the middle。

 the sacks ever emptyied。Thatch is the last。Okay。Another。It's I could nothing at all。Yeah want。No。

 that's you can't pop before you push。😡，So the way brackets are you。

Left bracket on the left and the right bracket on the right。So， I mean， the the。

What about a string that looks like this that's balanced？L。great question。

 can we use the grammar to construct this example string up here and I think the way that I'm going to do that is by I'm going to show the parse tree。

So S， I've got a split， that goes to S and S。嗯。This string that I have over here on the left。

The stack is never empty in the middle of that string， so in that case。😡。

I want to expand this into left bracket S and the right bracket and now in the middle there that S goes to the empty strength。

Great。Part left， I'm going to go to。This。I think I'm going to run out of Britain here so。

Actually just be on the side side。We togetherther。Then I need to。Look at。Just。This string。

I think the。The see the the。The stack is empty in these two places。So。

This S here in the middle is going to expand to S S and that's going to expand to SS。

So I've expanded1 S into three Ss。And now。This piece is going to attach there。哦。

This piece is going to touch here。And this piece is going to attack here。

And then we've already seen how to generate just。Open bracket closed bracket。

 that's open bracket mess closed bracket， that's an epsilon。Here that's going to be。Okay。嗯。

That's not still on that。And then I think at this point， about the rest。Okay， so the way that I。D。Oh。

About spring。He。Is that I follow the intuitive rules that I set。

Strange looking for places where this stack would be empty。

One when to expand according to the first production rule。If I don't find one。

 that means I can expand according to the second product。😡。

Unless the string is just completely empty and then I have the third production rule。

 which is one of my base cases。哎。Now one feature that this particular grammar has， which may be on。嗯。

Appeaing。Or distracting。Is at this point in the tree when I expanded on us into。对。は。我这次改。

There are multiple ways of gender。This name。Of。It's the same string。

 but this takes the grammarous of ambquituous。And ambiguous grammars are harder to parse。😡。

Unambiguous grammars， you've got choices and maybe you'll take the wrong choice。to explore。

 so let me give you another grammar for exactly the same language。

Maybe we'll satisfy your question of why do we have to do that way？And。

Another grammar that generates exactly the same language of bounce， strings of bounce bracketets。

 open bracket S， close bracketet S。So here's the。A my string string of string of open brackets。

 string of balance brackets all with the left back。😡，That pushes some item onto the stack。

Somewhere in that string， there's going to be a matching right bracket that pops that item off the stack。

Okay， those are the two brackets that I've got here in my production role。And then between the。Pa。Oh。

Oh。Bring the book out。Sreet them here。Brackt is identified as the first character of my string that post bracket。

The closed bracket that makes the stack empty。From the first one， so everything' is completely。Pmer。

It' got something simple like open， open， open close closed close。

 that second S in the production rule is immediately going to expand to the empty straight。Which。

 close close open close。the first stats in between the brackets is all proposed。

contexttex free grammar。We just want something that is systematic enough。

That you can go back explain， hey， if you use more than one non terminalmin。

 what language does each of those non terminals represent？😡，And even if it only has one non terminal。

 you can explain what the production rules mean here sort of the stack is empty。In the middle。

And this one is， it isn't。m， but then beyond that。You've got lots of choices of how to do things。嗯。

Different people are going to come up with different sort of ways of decomposing things and booking that workers vary。

Don't care which one it is。😡，I would recommend， however。

 that if you find yourself using about three or four non terminals。

 you might have gone down a rabb hole。😡，You should step back and for。Yes。你不知道。不是。

It's fine number about professional schools。弱是这的不会思。Or movement。

If you really want to have all the good。はい。Again， there are simple algorithmic questions about。

Pect free like。Frustrate。It。The complement of a context free language is not necessarily context free。

Regular or closer to complement。Worse if I give you a context free grammar and ask。

 is the component of this？😡，Basic questions about。How good is this， are these things gl？

Their he risk in practice， but very algorithms are。All right。Thank you。Sorry。

 let me turn off my recording hand。

![](img/87897f3e87fb15dffac1e435762db4ab_6.png)