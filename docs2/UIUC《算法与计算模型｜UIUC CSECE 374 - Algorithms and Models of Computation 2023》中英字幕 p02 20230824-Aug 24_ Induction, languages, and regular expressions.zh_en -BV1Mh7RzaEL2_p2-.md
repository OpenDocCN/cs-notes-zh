# UIUC《算法与计算模型｜UIUC CSECE 374 - Algorithms and Models of Computation 2023》中英字幕 p02 20230824-Aug 24_ Induction, languages, and regular expressions.zh_en -BV1Mh7RzaEL2_p2-

![](img/6e4b8784f21f2e1b7d6bd96804f995ee_0.png)

Okay。

![](img/6e4b8784f21f2e1b7d6bd96804f995ee_2.png)

![](img/6e4b8784f21f2e1b7d6bd96804f995ee_3.png)

。他。好。哎，哪。什么人话没有人话。对。对对再。哎。然后。对。啊是。好。好。Noello。不好。没有嗯。Yes。这这不错的。By。啥呀。好了。O拜拜拜拜拜。Okay。一。好的。Oh。All right。

 let's go ahead and get started。Everybody can take a seat， please。Welcome back。嗯。

It is brutally hot today， so I definitely appreciate that。

The extra effort you took to actually come here in person。

So lectures are always more interesting when there's other people in the room。

 remember take yourself。These are record high temperatures if you're not from you know New Mexico or Arizona or some parts of Southern California。

 you're probably not used to things being this hot so you know he can sneak up on you。

Take care of yourselves。Drink lots of water， stay in the shade as much as you can。

 stay indoors as much as you can。I want to make a couple of quick administrative announcements。😡。

Both this section of 374 and the B section of 374， which is taught in this room immediately after us have seats available and people are moving around。

😡，The seats available in the B section are all under the rubric ECE374 no。

 the CS department's not going to open up more CS374 seconds over there because that's just extra work for no point。

 yes， it means if you switch to the B section， it'll say ECE374 instead of CS374。

 no one's going to notice no one's going。😡，嗯。So。If you're still moving around or if you're visiting here from the B section and thinking of registering here。

 most of the open seats here under CS instead of ECE， same thing goes。

 all seats are open to everybody， no one's really going to care what the department name in front of the number is。

嗯。The first homework is do。On Tuesday， so just as a quick reminder。

 homework' is going to be submitted on grade scopepe。There's going to be one submission。Or group。And。

Her numbered problem。Which means each group is going to submit exactly two PDF files。

 one for problem one and one for problem two， in case it wasn't clear and in which case I apologize。

 your homework is problem one in problem two problem three is just a practice problem if you want something more to play with。

 happy to talk about that in office hours， problems after that are literally just examples of the kind of thing we want to see in your solution。

😡，They' they're just meant as extra sort of reference examples。

 those are not things that you need to turn in I do recommend that you don't just read those solutions but。

To put yourself in the mindset of how would I have come up with the solution myself。

 how would I have derived？Oops。This is not a class about memorization。In particular。

 having all of the old homework and solutions may not do because we come up with new homework and exam problems every semester。

Memorizing all 5，000 problems that。😡，It's going to pull up your brain and not that。啊。

The last thing is， I mentioned this briefly on Tuesday。We're having homework parties this semester。

 so these at least two of these a week are now officially scheduled the first one is going to be today。

😡，From 5 to 8 pm。In。Sivable210216。This's the large classroom in the basement。

And the others the other one's going to be this coming Saturday。This will be in。Sable 1404 this week。

And in ECL 1320。After that。We're looking into having another one of these on Monday morning。

If that happens， I will make an announcement on the coursese webpage and Discord and a discussion。

 but I can't commit right now to these being available。

So these are places where basically it's a big room with a bunch of tables where people can sit and work together homework。

 thell beTAs and CAs circulating around the room， that are available to answer questions。

 but the main thing is that students should be working with each other in particular。

 if you're worried about finding other people to form homework groups with， well look。

 there's a big room full of people who are there to work on the homework that might be a good opportunity to actually meet some new people and form some homework groups。

The one the two caveats I need to give about these， however。Which is。

Neither of these rooms is large enough to seat 425 people。😡，so this room has a capacity。

 I believe it's 93， these rooms have a capacity of 200。

That's kind of reflecting what we think the demand is likely to be。😡，嗯。

If we're wrong then we'll do better next semester and I don't think that this point we'll be able to get a bigger room during the week。

😡，But we might be able to get a smaller room on Saturday if not enough people show up。

But with all these homework parties and more generally with any kind of office hours。

We're not kind of have enough too。Everybody asked at one time， we've got office hours now set up。

Every day of the week， except every weekday， Monday through Friday， most days。

 there're like six or seven office hours。please spread yourselves out in time if everybody comes to the office hours Tuesday at 3 pm for the Tuesday at 9 p。

m homework deadline， nobody's going to get any help。Um。Same can goes for these。

If you arrive here and the room is crowded to a certain extent， we can let people sit in the aisles。

 but once it starts to get standing room only。We have to ask you to try something else。

I'll come back at another time。嗯。So we hope that this is going to be enough room knowing that not everybody is going to want to come to these。

 some people prefer， you know， I'm just going to work on my own RF homework groups。😡，Um， I， you know。

 I don't want to work in a big crap， big， noisy room。So I'm hoping this will be enough。嗯。

We'll find out。Does anybody have any other questions about administration logistics。

 things like that？Yes。But。You are allowed to work with anybody you want。

The Home group for purposes of submitting to gradecope is the list of three names。

 but if you work in a group of eight， that's fantastic， it's just every group of three， three。

 two needs to up their solutions themselves on their own。😡。

So working in larger groups to brainstorm and work out ideas， that we encourage that。😡。

Just every group needs to have its own writer。And you should probably cite each other。Just say， oh。

 we worked in this larger group。Give names if you remember them。

 just say it was a larger group than the homeworkmark party you don't remember that。Okay。Cool。U so。

I need to apologize。😡，For not pushing the record button。😡，On the lecture on Tuesday。

 I did upload another video but it didn't have all of the administrative information or overall coverage of the class if you do have questions about those things please don't hesitate to ask me。

 but I did try to include a fairly detailed count of a couple of induction proofs。

Because I'm sure not everybody have seen that video。

 I want to walk through one more induction proof right now and before I go on to newer course material。

😡，So there's a pretty usefullemma。This is actually already in the lab handouts that you saw in yesterday。

 but again， I think walking through the derivation is helpful。Okay so for all strings。U。W， Y and Z。

W Kca Y。Cat Z is the same as W and cat。Why concate Z， in other words， concatetnation is associative。

Well， of course it is。Because the intuition you have about concateation is pretty similar to the intuition you have about addition。

 if I put this thing of three and two together and then put this other thing of four。

 that's the same as putting these two and four together and then put it on to three。Um。

But let's go through the stages and actually deriving the proof。All right， so the first thing is。

I see。You know， a universal quantifier here。So。I'm going to start by declaring my variables。

Let WY Z be。Arbitrary strengths。And then at the bottom of the screen， I'm going to write。

The the theorem。WY Z equals WY Z。And you might wonder why I'm using WYZ instead of using the。

You know， variables that are consecutive in the alphabet。

 that's because'm'm I'm going to use another variable x in the middle of the proof and。

Aly figured that out。S see when it happens。Okay， so this is the first step great。

 I've written this down now the next step is to try to think about how I would argue about this when the strings are all very long。

So this is kind of an informal。😡，Gue， at this point。

 so I'm going to assume that Wx or sorry W Y and z are long and see what I can do with that assumption。

 basically try to stay away from boundary cases and see what I can argue。All right。

 so I'm going to start by writing the thing on the。Left。

 we'm going to end with writing the thing on the right。And let's see what we can do。Okay。

 so I want to expand something。The definition of string is in terms for long strings。

 as always in terms of the first symbol and everything else。😡。

So tend to want to expand things that are on the left。

So let me follow that intuition and just declare what W actually is。😡，This is AX。

So I'm going to assume here that W is equal to the string with first character A and the rest of string X。

Just to give those two components of W names。😡，U。Now， well， I want to like。

I don't have something I can apply the induction hypothesis to yet。

So I want to apply definitions of something and the only something that's on the screen here is the definition of concatenation。

 so the question is， do I want to expand this。Concatetnation here on the left or do I want to expand this concatenation here on the right？

嗯。The only one where I really have access， you know I know something simple about the arguments is the one on the left。

 the left argument is AX， I have direct access to the first character， the one on the right。

The left argument is complicated and I don't want to think about it yet。So I'm going to expand。This。

Concatenation by definition into the string made of a。

Followed by whatever the concateation of x and y is then concatenate Z。

So this is by the definition of concatenation。Now， while I still don't have something I can apply the induction hypothesis to。

 but now this concatenation operator on the right looks like I might be able to do something because the left argument to that operator is a string。

 it's a followed by something。If you're not comfortable with。Thinking of that whole expression。

 openPenx。Y closed Paren as a string， I could give that a separate name。you know I could call this。

 I could define u equal to x dot y， and this is now equal to a。 u。and this I can now write out。As。

Like this again， by the definition of dot this time expanding。嗯。

The definition of that second dot there。All right， let me substitute you back in。

 this was kind of a detour。Didn't need to take it， but it doesn't hurt to take it。There's you。Okay。嗯。

And that seems to be about as far as I can expand definitions。

These are just arbitrary strings I don't know anything about so i'm not going to be able to do any more expansions。

 so now instead what i'm going to do is switch to looking at the bottom and working my way up again I can。

😡，expandp。I can't really expand anything in this concatenation on the right Y dot Z because I don't know anything about Y and Z。

 but I've already assumed something about Ws， so I can use that to expand。AX。Y do Z。

Because W is equal to AX。And then the next thing I can do is apply the definition of concatenation。

Again， if you're not comfortable with thinking of this blob open print y。

z close peren as just something of type string， you could give that sub expressionpression a new name。

 I don't know， call it V， and then then the substitution might be more direct。😡。

This is really just by the definition of incnation。And now somehow we have to get from this to that。

And that looks like an invocation of the As law， which is the thing that we're trying to prove。

 so alarm bells might be going off， I'll wait I'm arguing in circles but。Remember。

 we've chosen the strings W Y and Z and we're trying to prove that concatenation is associated for those three strings we've gotten ourselves into a point into a state where we've got three strings。

 but the first string。😡，X is shorter than W。So we imagine making a recursive call at this point the first of the three arguments the recursive call is smaller than the first of the three arguments that I was given so make enough recursive calls it's going to bottom out and reach a base case at some point this is great this is a place where we can do recursive so this is going to be you know apply the induction hypothesis。

😡，And now we seem to have a complete argument。😡，Now I need to think a little bit about what assumptions did I make？

😡，About W Y and Z when I wrote down this argument， well， the one important one here is right here。

 I assume W Y and Z are long， but I really only invoke the fact that W is long。

I invoked the fact that W has a first character。😡，Which I'm going to call a。It's not always true。

 W is an arbitrary string， I don't know anything about the W in advance。

 so not all strings have a first character。😡，So this tells me that。You know what I need now。

Is to you know say this explicitly that。You know， here's a case two where W equals AX。For some。

A in Sigma and sum string X。And there'll be another case。Where W is empty。

 and I have to argue separately？And now what actually is the induction hypothesis that I invoked at this point。

 well， what I want to say is as long as the first string gets shorter， everything should work。

 so this is actually what I'll write down is my induction hypothesis。😡，So soon。For all strings。X。

Shorter。Then。W。That。X， Y， Z equals X。Yhy Z。The Y and the Z in the induction hypothesis are exactly the same Y and Z that I declared in the line above。

Because when I invoke the induction hypothesis， it's the same。It's not always going to be true。

 sometimes you have to write more carefully。嗯。And so at this point。

 the only thing I have left to do is to fill in the details for the only case where I haven't proved the theorem yet。

😡，So let me go ahead and do that。So then W doty。Dot Z is equal to Epsilon dot Y。Dot z。

This is equal to y dotz， equal to epsilon dot y。zs equal to w。 y。

z this is because w is equal to epsilon， this is by the definition of concatenation。

 this is by the definition of concatenation， and this is because W is equal to epsilon。The first。

 the line here。Where I go from。I've found out y to do Z。

 I'm applying the definition of concatenation here。😡。

And the second time I'm applying the definition of conion here。And even though I wrote it top down。

 the way I really thought about it was I got to the sort of state in the middle of Y do Z by going downwards from the beginning and upwards from the end。

But it was a short enough argument that I could just write it down。Um。

I couldn't do that for the inductive case。Uh，W whichch is why I didn't。😮，engng。

If you aren't comfortable just writing it all down again。

 just feel free to write bidirectally and then squeeze things together if you want to make it look a little bit neater。

Um。So one thing to notice about this proof that a couple of students have pointed out after class yesterday and again in office hours and again this morning。

 you'll notice that I do not declare which of these cases is the base case and which of these cases is the inductive case。

😡，Because those declarations don't matter， what matters is every string is considered in the case analysis。

😡，No matter what string W give me， I know by the definition string that W is either empty or it's not empty。

 and if it's not empty， I will name its first character A at rest of the string Act。😡。

Exhausive case analysis。A base case is just a case where I don't need the induction hypothesis。

 an inductive case is a case where I do need the induction hypothesis。

 but there's no point in writing the word inductive case before you write down the argument because you don't know before you write down the argument whether you're going to invoke the induction hypothesis。

😡，Right。Same notice I left the base case till the end。

 that's because until you write down the inductive argument。

 you don't know what your base cases are going to be， or for that matter。

 you don't know maybe you actually need to give， you know。

 you actually omitted like an infinite number of strings。😡。

And so you need to have another case that invokes the evolution hypothesis in a different way。

So don't yourself down at the beginning by saying， oh， I know what the cases are going to be。

Look at the induction argument。What assumptions that induction argument makes？And then。

Handle everything that that induction argument doesn't handle。Yes。And how more an example we have。Oh。

 a question about typing。Homework， you can write by hand， you can write in a text editor。

 you can type it using lawte， you can write it up in Word or Google Docs。

 whatever's easiest for you as long as it's clear to the graders。

Exams would be in a room like this with。We're kind of in your hand。Thanks。

The length of the fruit so that。meanSo this is a good question on exams。

 how do you predict how much space you need， give yourself more than you think you need？

There'll be extra sheets in the back of the examplelets that you can use for scratch work。😡。

So one strategy might be scribble on the scratch work until you see the shape of the proof and that'll give you some idea how much space you need and once you know what shape of the proof is you can actually write it directly。

But another way is just leave yourself lots of room for the different cases。

And if there are blank space is on the solution， that's fine。Yeah。U。up like the。For the formatting。

 I probably remove like the red brackets and I wouldn't bother with the step where I'm substituting for you。

That was just， oh， I was a little uncomfortable， okay， it's fine。Otherwise。

 this is pretty much what I would do。I'm sorry。Yeah have to say like the definition of。

We will assume in this context that if you wrote。DEF， you mean definition。

You should say definition of what an IH stands for induction hypothesis， especially on exams。

We're not going to make you write out the letters in induction hypothesis。So like I said， this。

I would。I would give full credit， but comments you should probably take out the brackets in this step here。

 it's a little distracting。Yes。Which line are you looking at here？From here to here。Okay。

 so remember the definition of dot， the sorry， that's not what I wanted。The definition actually says。

W dot y equals y if W equals epsilon。And a dot。X， Y。If w is equal to AX。This。

 if you're doing homework is in the lecture notes， this， if you're at an exam。

 you have written on your cheat sheet。Which you can bring into the exam。

But if you've been playing with this often enough， you can probably just remember it。

You will be allowed to bring in one sheet of paper， anything you want written on both sides。

 teacheach midterm， two sheets of paper for the final。Um。

 we ask you to handwrite the cheat sheets because then what happens for most people is the active handwriting。

 the cheat sheet puts the stuff that is on the cheat sheet into their brains。

And then they never look at people， never look at the cheat sheet。

But if you're worried about memorizing things， just write it under your cheat sheet。

 it's there in case you want to look it up。Okay， so this is a good question。

 I'm trying to be a little bit careful to distinguish between two different kinds of dots。

The little dot is a function that takes a symbol in a string and assembles a string out of it that's really just syntactic sugar for the definition of the string。

The big dot is this other function that I define call concatenation that takes a string and a string and glues them together a larger string。

So the difference is in the type signature of the two functions。Once we get into things。

 you don't even need to write down the dots at all。And because we know in particular。

 now that we know that concatenation is associative， we wouldn't write down the parentheses either。

 we just write down WYZ and that would be enough。Yeah。

Senate definition movement as directional like it's like a single name that's brilliant access the other end。

😊，So。Okay， so this again。One question。Sometimes it's more convenient to reason about the last character in the string instead of the first character。

😡，That's completely fine。So you can prove that every string either is or it has a last curve。

 and then you can define it at big dot a。😡，And least。

If you want to pick up breaks that way and you're approved。That's okay。

 but just to make sure that you call out explicitly that're doing something non standard。

Don't just do it blindly because then we'll think， oh you've've forgotten how we define things similarly。

And actually do this in the notes as a second proof of this particular theorem。

 you can also break strings up by saying every strings either empty。

A simple character or the concatenation of two nine。

And then you get a threeway case analysis in the recursive proof where in the last case you say。

 well， W is the cnation of W1 and W2， and then you argue by the induction hypothesis that can shuffle the parentheses around。

Whichever is most convenient， that's fine， just if you do something that's not standard。

 point out that you're doing something that's nonstandard so that we know you're doing it on purpose and not making a mistake。

Yeah呃。But AX and guidelinestline subsequent A， Bill got X big guidelinesline that W AX which case course。

I'm not sure I understand what you're asking， so I substitute for W here。

And then here I'm substituting for this expression。

 I'm substituting his definition I could do two steps at the same time。

 but then I would need to write down two explanations。And one step at a time。

Is a little clearer again， we need to be able to distinguish between your skipping steps because you're you know what you're doing and you're skipping just because you forgot that you needed to take a step。

One more question and I need to move on to more。You need to ask the state that you're calling different boxes。

Well， I want to give every every equals， I need to give a reason。

And the induction hypothesis is the reason there。Again。

 it's just a question of distinguishing between， we want you to declare the reason for everything because we want to make sure you know what the reason is。

Once you get more fluid this stuff and we built up a bit more trust。

UmYou can just write down the statements and it's sort of clear each step， oh。

 that's that's the definition and oh， that's the hypothesis and so on。And if you're really。

 really fluent， if you're a professional mathematician。

 the way a professional mathematician would prove thelemma is they would write proof colon induction slug。

😡，And when you're a professional mathematician， you can do that too。嗯。So like I said。

 I do need to move on to some new material here， just as a reminder in the scribbles you'll see this boilerplate that I stole out of the notes。

 this is what almost every induction proof about strings looks like。

 it doesn't matter what the words perfectly crmulent mean。

 this is the boilerplate that should almost fall out of your pen before you started thinking。😡，Right。

Okay。So。So much for individual strings。But when we want to talk about how。

Different kinds of machines， different kinds of algorithms interact with strings。

We want to ask questions like which strings will this？😡。

Algorithm except for which the strings with this algorithm return true and which I wanted to return false。

And so I need to think about sets of strings。😡，And so we need to develop a little bit of notation for this。

The term that we use。😡，In this class。For a set of strings is a language。In particular， again。

 we're kind of fixing an alphabet。A set of symbols， sigma。We say a language over the alphabet sigma。

 this means a set of strings in which every character comes from this alphabet。😡，U so。呃。

What is the simplest language that you can think of？Yeah。Okay， so all buy on your restraints。ま。

Andact up。So the way that we would normally write this。Is using this star。

So if I want to declare my alphabet explicitly， I would write you know the set zero comma1 and then I put a star that just means all strings。

😡，With the alphabet。More generally， if I just know that my alphabet is Sigma。

 then I would write Sigma star， that means all strings over the alphabet Sigma。😡，Okay， that's。

Pretty simple。So this one is all strings。Over stigma。

But it's not the simplest language I can think of。You going think of another one that's even simpler。

Yeah， back over there。Yeah， you， yeah。So the empty set。

This is the empty set of all strings over the alphabet 01， this is the set the empty set。😡。

In which every string is a protein over the 22 amino acid alphabet。

 this is the empty set of illegal scrabble words。Um。The empty set works over every alphabet。

U this letter here， this symbol is not。😡，A Greek letter。

Andre Vial in the 1930s was a member of the mathematical collective， Nicholas Brbchkey。

They named themselves after Napoleon general for some reason。U。

But they wrote this incredible series of treatises about the foundations of mathematics。

 starting with set theory and logic and building up to arithmetic number theory， algebra analysis。

Tology and they needed a symbol for the empty set that kind of reminded people of the number zero。

 but what is it the number zero？😡，And so Andre Vial chose this letter from the Norwegian and Danish alphabet。

 which is an O with a slash through it。It's pronounceder。So it's the same as。You know。

 the vowel in the French word for beef， booth。It's the same as the vowel in the German word for stupidbuza。

It's the same， in fact， it's actually the same letter as the vowel in the Danish word for beerooh。😡。

It is not pronounced fee， and dear God， it is not pronounced phi。😡。

That's probably the golden ratio or something else Okay my preferred pronunciation for this symbol is nothing。

Or null or empty。嗯。But it's not a Greek letter。Dive that from your brain。Okay。

There's another language that's very similar。To nothing。

 which is the set containing the empty string。This is a set that contains one string and that one string happens to be empty。

😡，These are not the same thing that the set containing Epsilon is not the same as the empty set because it contains Epsilon。

😡，Likewise。The empty string itself is not。😡，A set， it is a string。Theyre different types。

 so I've got three symbols that kind of remind you of nothing。😡，But the right way to say this is。嗯。

You know， empty， nothing really is just an empty cardboard box。😡。

The set containing the empty string is a cardboard box that contains an empty paper bag。😡。

And the empty string itself is a paper bag， which is not a box bag， so you can't call it a language。

 yes。Yes。At this point， star means all strings over that alphabet。

I'll define the star operator more generally in a few minutes。St literally means all strings。Okay。U。

But there are other examples， so I could write all strings W over the binary alphabet。

Such that the number of ones。啊。In W is equal to the number of zeros。MW。That's a language。

The set containing the string 00101， you know， a single string， that's that's a language， the string。

The set containing the four strings， Jake Finn， Fiona， and Cape， that's a language。

 not over the binary alphabet， but over the English alphabet。嗯。The set of all Python programs。

Is a language。The set of all Python programs。That。Infinite loop。Is a language。

Thinking of a Python program， I mean， this is a sequence of Unicode characters that you would feed to a Python interpreter and it doesn't complain about syntax。

Um， this is just as the additional property that if you run the Python program， it never returns。嗯。

So these are all languages。😡，Some of these languages are a bit simpler than others。

I guess another well I'll。可。But。Fundamentally languages are sets。

 And so we can manipulate them the same way we manipulate sets。 So if A and B are languages。

 then A union B is a language and。A intersect B is a language and a minus b。

 this is all strings that belong to A except the ones that also belong to B。

Does its remove subtract B out of a or the symmetric difference of B， this is exclusive or。

 these are all strings that belong to A or B， but not both。These are all。languageanguages as well。

 you can also like look at the complement of l this is you know sma star minus l， so if I take。

 for example， L is this language here。All strings of zeros and ones with the number of zeros and ones are the same。

 the complement would be all strings of zeros and ones with the number of zeros and ones are different。

系。So I can do set things with languages because they're just sets。😡。

But there are a couple of other things that we can do with languages as well， that're useful。

One possibility， I'mll put this in a different color just for some emphasis。Um。

 is I could say I could define a new language L to be the concatenation of a。

 language A and language B。So this is defined as the concatenation of all strings x and y。

 where x is in a and y is in B。So， for example。First。Last。Thought。Actually， let me erase this。

Sp the example I have there。First， second。Third。Incatenated with。Placed。And base。U。This language。

Contains the strings first place。First base， second place， second base， third place， and third base。

So all pairs。You concatenate one string from the set on the left and one string from the set on the right and all such ways of combining those things that gives you your concatenated language。

嗯对。UThe the。This has a few rules。What is the empty string concateated with El？It's empty。

It doesn't matter what L is。😡，If I say all pairs were I picked the first string out of the empty set and the second string out of L。

😡，But。I'm done。😡，I've already done it， I've picked all possible strings out of the empty set。

 none of them say there are no pairs where the first string comes out of the empty set， likewise。

 you know，You know， in general， concatenations not reflexive， not commutative。

 but in this case with the empty set， you can concatenate in either direction。

Here's a more subtle one。What do you get？If you concatenate。

The language containing only the empty string with another language o。Yeah。You get out。Likewise。

 if I concatenate in the other direction。so I pick out one string from the left and one string from the right and I glued them together that gives me one string in the concatenated language。

 so the string on the left is epsilon， the string on the right is x。😡，I can copy epsilon x， I get x。

Right， so。First second， third dot epsilon is first dot epsilon， second dot epsilon。

 third dot epsilon， that's just for second third。嗯。The last operation that is like， oh yeah， sorry。

 there's a question。对。A and does。Say alphabet。Generally， when we're talking about languages。

 we fixed the alphabet in the background and say， okay。

 all strings we're just assuming are going to be over the alphabet。Os。You could also， though， say。

 you know， if a is a set of strings over the zero through nine and B is a set of strings over the Latin alphabe。

Then you can so contain them and now you set of strings of a larger alpha。So if I say you know。

0027 is out of this set of numbers and CIF is out of this set of strings， then I can。Incatenation。

 I get a larger set that includes zero027 CIF。Okay， so the last one is a bit weird。嗯。

This was an operation defined by the logician， Stephen Pole Kleney。U。嗯。Those of you who。

now any German， is this name， K LEENE is of German origin。In German， it would be pronounced KA。

And his kids probably， I think， pronounced at Clalama。

 in English youd probably be tempted to pronounce this clean。We' cleaning。

Lney himself pronounced it Cy。Even though that is not the correct pronunciation in any language on earth。

不是。嗯。A， back B， save the table basically。Yes， backslash is just more standard notation for subtracting sets。

It means a without， you should really pronounce it without。A without B， that's this line right here。

Okay， so the Cy star。Now， start。This is all strings that you can get by concatenating strings in L。

Okay， so this is。In cat nationations。Of。Any number of strings？In L， so this is defined。Union L。

 unionL。l， union。l。l， unionL。l。l。l and so on。So this the second containing epsilon。

 that's all strings that are obtained by concatenating zero strings in L L is the set of all strings obtained by concatenating one string and L L dot L is the set of all strings obtained by concatenating two strings in L those two strings might be the same。

L do L do do do L is what you get when you take four strings out of L。

Or you could define this recursively as the set containing the empty string union L。l star。

You have to be a little bit careful with this because it's not actually。

 this is not actually a recursive definition， it's literally a circular definition。

So you shouldn't think of it as a definition， but rather as a sort of useful mnemonic。嗯。啊。

So another way of saying this。W is L star， if and only F。W is empty or W is equal to x dot y。

For some string x in L and Y in L star。So it's a concatetnation of a sequence of strings。

All of which come out of home。This is the same star。That we saw up here。😡。

When I define the notation Sigma star。It's just there。

 I'm thinking of sigma as not a set of characters， a set of strings of length one。😡。

So any string is the c of one character strings。Which are。

Morally the same as the characters in the alphabet。嗯。So even if we're working over the。

Just give another example here。I don't want this one。Let's take the string。

 the language containing only the string01 and。Start that。

This will give you the infinite language that contains the empty string， the string 01， string 0101。

 string 01，01，01， and so on。嗯。嗯。Now。嗯。So a couple of questions here， if you look at this， you might。

Ask。Um， if I start with a language L that has at least one non empty string in it。

Then the claim star of that language is going to be infinite's going to contain in particular。😡。

Strings that are built by an infinite arbitrarily many copies of that one string。

So it's tempting you know to think， oh， right， L Star is always this infinite infinite language and in fact。

 starting with single characters， and this is really the only operation we have right now to build infinite languages。

 but is L Star infinite for every language L？😡，Whenever I ask a question like this for all language。

 is this true of every language， there's one language in particular that you should go。

 I wonder if this is true for。What is that？What's the one weird exceptional language you should always the sanity check against？

Oh no， I stepped in some dog poop。Yeah。The empty set。俾。So what is the star？Yeah。Conceptating。Ohb。

 very good。What about the set containing the empty string， the set containing the empty string star？

😡，Is the language containing strings you get by concatenating as many empty strings as？😡。

So what strings is that， what language do you get？Just the empty string。

I'm concatenating a bunch of strings of length zero。

I'm only going to get the string of length zero and there's only one string of length zero。

But what about what about what about？What about stupid beef？What about the onset set？

What do you get when you started the whole set？Yeah。Sorry。Close。

 so that the question the answer was theul set。It's true that you don't get any non empty strings。😡。

But notice。From the definition here。Or from this characterization of L Star。

That L star always contains the empty strain。So the answer is。

This is also the set containing the empty string。I get the empty string by concatenating zero strings together。

And luckily， I can， in fact， pull zero strings out of the empty set。Every other language L。

 you get an infinite L star。Alright。So。Every kind of。啊。Get a feel， I mean。

 there are these weird boundary cases， but for most languages。嗯。

The star is just sort of like unbounded。And over and over again。

 she used a string and a language and glue it together to build a larger string。系。嗯。

Now there are a bunch of rules that you can apply about these languages about how these various operators interact。

 some of them just look like step theory， some of them are about concatenation and how it interacts with other things again。

These are things that will come up and chances are they'll be kind of obvious in context if they come up if you care you can put these on your cheat sheet。

 there's this cool thing called Arden's rule， we're not actually going to ever use it。

Um but these are in the notes if you care。The one thing I really want to talk about though is you know what languagegos can we get using just the operators that we've seen before and this is what Clney actually introduced。

This is the concept of a。Regular language。Thanks。So regular languages according to Clanney。

Are languages that are defined？😡，As follows， so L is regular。Means。One of the following。

L is the empty set。L is a set containing。A single string。L is a。

Union B for regular languages L and B or sorry regular languages A and B。L is a connate B。

For regular languages。A and B。Or L is a star。For some regular language。系。One of the five cases。

So you can build languages up into larger and larger structures。

 starting at the base with either the empty set， which in practice you'll never actually need to use or sets containing individual strengths。

😡，系。嗯。Now。The reason Klaney was interested in this collection of languages is he was actually trying to study sequences of events。

In the thing that we should think about。😡，In terms of programming is an event happens when a line of code is executed。

ok。Now， if you've got a well structured。😡，Heace of code without any go tos in it。

The modern languages still have go tos。Probably not。

 so I just say you know anything that you write in Python is probably fine。

 anything you write in Java is probably fine。U。The kinds of things。That you're doing here is well。

You're looking at。What your sequences of events that you might observe when you're observing the behavior of some program。

 one possibility the doesn't do anything。😡，You don't see any events at all one possibility is that the behavior of the program is completely determined you run the executes line one two。

 three， four five， six， seven the end。 that's the case for a single string。Right。A single string is。

You know， just I've got lines of code， there's no branching or anything。😡。

Union means I have a possibility of branching， so this is like saying well。

 there's an if and some lines and there's an else and some lines。😡。

Now there are two different sequences of events that I could observe。

 one that I get when I take the if branch and the other I take when I see when I take the else branch。

嗯。Concatenation is really just sequencing。Take two programs and I run one and then I run the other。

I get the events that are omitted by the first program and then I get the events that are omted by the second program。

And then finally， the Cly star。Is a。Unbounded repetition。

I know I'm going to repeat this block of codes some number of times each time I pass through this block of code。

 there's some set of events that I could observe instead of sequences of events that I could observe。

 but I don't know in advance how many times I'm going to repeat。

 so I'm going to allow myself to repeat however much I like。😡，so this is sort of sequencing。

This is branching。And this is repetition。Now the actual events that he at were the kinds of things you get from of what people now call neural nets。

And the 1950s we were still figuring out the basics of these things。So maybe this is， you know。

 what kinds of things will your brain do over one second。

 well you're going to think about dogs and then you're going to think about dogs again and then you're going to think about cats and then you're going to think about dogs again。

And I don't know how many times you're going to think about dogs before you think about cats once。

 and then I don't know how many times you're going to think about dogs。For example。

 but one thing to observe about this is not every language is regular。😡。

They are languages that cannot be constructed using this kind of alphabet。Um。Now。The way that we。Um。

 normally talk about these things is not by using set notation。

 but using a slightly more compact notation called regular expressions。😡，So a regular expression。

Is again， this is sort of a five way thing， it's either nothing or it's a single string or it's a plus B or it's A B or it's a star。

So in regular expression syntax， we normally use plus instead of you forun。

 we can put the dot in there for concatenation if you want， but generally we leave it out。

And these things have some precedence rules。So。If I write this regular expression zero plus10 star。😡。

Think of this exactly the same way you would think of writing down a polynomial where instead of symbols here you have variables。

 this is x plus Yz squared。The the same kinds of precedentnce rules apply that star only applies to the single character language zero not to the single stream language 10。

 so this is an abbreviation for the language containing zero union。With the language containing one。

Daunt。The language containing zero starred。系。This is all strings。Thatre right。

A zero or a1 followed by an arbitrary number of zeros。系。

This is a really convenient notation for looking at structured sets of strings。😡，Um。

 when you have any kind of interpreter， any kind of compiler。

 any kind of parser for like web pages or URLs or IP addresses under the hood。

 there's a description of this form that describes what words。

 what small pieces in that text are legal。😡，So there's a regular expression that corresponds to legal floating point numbers。

 writing out an explicit floating point number in Java， for example。

 theres you can have a zero before you can have some digits and then a period and then some more digits and then an E and then some more digits。

😡，嗯。So some digits that's digit star and then a period and then some more digits that's digit star and then an E and then the E is optional so you have some pluses in there。

 so there there are regular expressions that describe。

The sort of low level patterns in the kinds of strings that you would want to look at。

Regular expressions can't do everything， don't try。Yeah， question。Plus is a synonym for union。啊。

I don't know why。So in formal language theory， there are at least five different symbols that you use for union。

You can use you that means sex which plus he's like' specifically thinking of things as regular expressions。

If you use a bar like this， I'm explicitly thinking of things as context for grammars。

Just used to it after a while。All right， so。This is a really useful thing to think about。

Because it describes lots of sets that have simple patterns in them that look like sequencing and branching and repetition。

So let me just try one here。The set of all strings that alternate between zeros and ones。

So alternating zeros and ones or equivalently。Never zero， zero or 11。

So I want to describe this set of all strings that have this property that you never have the same symbol twice in a row。

so it's useful when you're thinking about this for the first time to write down a couple examples of good strings and bad strings。

 and there's always one string you should think about first， that's the empty string。

 it's the empty string good or bad。Does the empty string ever have two symbols in the same symbol twice in a row？

Which symbol。The empty string is a dis symbol。Again。

 it's important to keep types in mind the empty language is not the same as the empty string。

 the empty string is not the same as a symbol， so the string is actually good because it doesn't have two zeros in a row and it doesn't have two ones in a row。

😡，Similarly， the string。The strings of length1 are both good。1 zero is good， zero one is good。

 but zero， zero is bad， one one is bad and zero0 zero0 zero is bad and one100 one is bad。

 one101 zero1 one is bad。0，1，0，1，0 is good and10，1，0，10，1，0 is good。Right。嗯。

And so what I'd like to do is find a regular expression that kind of expresses。

What patterns are actually allowed in here？系。ThankU。So。Is there something？In the set of good strings。

That you see。Repeating。Some arbitrary number of times。知道。Okay， good， so somewhere in this。

In the middle of this regular expression， I mean， I'm not done as there's going to be some other stuff surrounding it。

 I'm probably going to see zero1 star。哎。Now let's look at the good strings that I've written down and kind of。

😡，Go a box around substrs that are described by01 star。

And see what's kind of left over so i've got such stream that looks like that， there's one。

 there's one and there's one。And those are the only ones and the examples I saw。So。

Zero1 close print start that doesn't describe all strings that alternate zeros and ones。

Describes a lot of them but。It doesn't describe the string 10， for example。😡。

It doesn't describe the string 0， it doesn't describe actually this is the01 is the only string on the screen that expression describes。

But it covers most of。Every strength。The only thing that it potentially leaves out。

Is I might start the string with the one。Or I might start the string with the red box。

So at the beginning， before I get to this repeating pattern。

 I have the option of starting with a one。😡，The way that I write that down。

 so I write one plus empty string。Maybe this component of the regular expression will expand to the string one。

 maybe this component of this the component in the expression will expand to the empty string。

Similarly， there's something at the end。Good， zero or empty string。A。

So the way I developed a very expression is kind of this similar strategy to thinking about inductive proofs。

 look for the big stuff first。😡，It's always， you know there are different strategies here that work。

 but this is the one that I find really useful a lot of the time。

 look for patterns that cover as wide as much stuff as possible and then look for exceptions to those patterns。

Now there's another way I could have done this。嗯。Just a second。嗯。This out of the way。Okay。嗯。

I could have said。Well， let's just start at the beginning of strings that never repeat themselves and look at options。

😡，Right， so it could start with the strain could just be empty or it could start with a zero or it could start with a one。

The empty strings I'm completely done， I just write down epsilon plus and I okay that that part of the regular expression is completely taking care of the empty strings。

 but now I'm going to have a need a regular expression for。

Strings that never repeat that start with a zero。😡。

And I need a regular expression for strings that never repeat that start with a one。Now， the next。

 if I look at what strings that start with the zero。😡，What can happen after the zero？Either。

The string ends。Or you have to say one。Okay， so maybe the string ends。

Or maybe you say one and you have to keep going。系。嗯。啊。Well。See， where am I going with this？嗯。

And then after that one， either you're going to end。

Or you say zero and you keep going and after that zero。

 you either either end and you say one or you keep going。

But if I sort of expand this a little bit more。I can。Say， well。

 either zero I say after the zero I do nothing or after the zero。

 I put a one and stop or after the zero， I put a sorry。I put a10 and then maybe I keep going。诶。

The things that I can put after that zero inside the parentheses。The stuff that I can put。Sure。

Is the same as the stuff？That I could put here。I've kind of reached the same state in my choices for what I can do next。

😡，I wrote down to zero and then I have the option of ending the string immediately。

 writing in a one and ending to strain immediately or writing down one0 and maybe continuing。😡。

But continuing after that zero again， I have the same options， I can write down nothing and stop。

 I can write down one and stop parking down 10 and maybe keep covering。

So here is where I'm seeing my repetition。😡，What we're going to talk about on Tuesday。Is。

A graphical representation。What's really going on is。I'm bouncing back and forth between two states。

 one of which is my next character could be a zero and the other one is my next character could be a one。

This is really the foundations of where we get DFAs。All right， thanks everybody。

 I'll see you next week。😡，申请。他忙。Sorry。Yeah。Over the trouble here with is not part of the vocabulary in regular languages。

Oh。So you can't just exclude00 and that's your vocabulary。

So it turns out that the difference between two regular languages is a regular language。

 but that's a theorem that you need to prove it's not part of the definition。

What is the language tests offering？やさ。嗯。All strings that have the same number zeros and same number of ones。

I can't treat that with the sets of properly nested parentheses。Oh。Thanks thing， Frank。嗯，这个。还。

Why is it regular nerve？

![](img/6e4b8784f21f2e1b7d6bd96804f995ee_5.png)

Okay， thats regular。W to find that。他是么。