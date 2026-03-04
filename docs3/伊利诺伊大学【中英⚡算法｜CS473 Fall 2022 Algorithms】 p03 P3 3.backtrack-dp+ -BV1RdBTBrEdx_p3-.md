# 伊利诺伊大学【中英⚡算法｜CS473 Fall 2022 Algorithms】 p03 P3 3.backtrack-dp+ -BV1RdBTBrEdx_p3-

![](img/2abbbcd824b04c6be0fdf6faf004339c_0.png)

对咩啲。Let's go ahead and get started， thank you all for coming back。😊。



![](img/2abbbcd824b04c6be0fdf6faf004339c_2.png)

![](img/2abbbcd824b04c6be0fdf6faf004339c_3.png)

Even though everything is recorded。U。So a couple of quick。Administrative announcements。

reminderminders。Homework zero is due tonight at 9 pm on Gr scopepe。

I'm pretty sure I've enrolled everybody who's asked me to enroll them at this point。

 but in case I missed you or you didn't get a chance to send me email。😡。

There's a self enrollment code， I also posted this on a discussion where you type it。

 you can just go to grade scopecope， type in the enrollment code yourself。

 and you should be good to go。U。If for some reason。😡，You've tried this and this doesn't work。😡。

Come talk to me immediately after class and I will stand here and put you into Gr scopepe。Likewise。

 I believe。Everyone has been able to get into a discussion again。

 if you haven't been able to do that， please come talk to me after class and I will stand here and get you in while we wait。

😡，系以。嗯。😊，A couple of。Quick comments about the homework。

 and this is a sort of general comment about the class。When we use the phrase describe an algorithm。

😡，There's two things that we want and one thing that we don't。

The first thing that we want is a clear description of the algorithm。😡，That could be pseudocode。

 that could be structured English， that could be a mixture of the two。嗯。

Whatever is the clearest way to convey the procedure that you want somebody else to code。

And the level of detail that we want is basically， I should be able to hand your description。😡。

To a bright 374 student。who doesn't know your favorite programming language and they don't know your you don't know their favorite programming language and they're not taking 473 so they don't know what the algorithm is trying to accomplish。

 nevertheless they can implement your algorithm in their whatever language they want。😡。

And it will be correct。So do not give us C+ plus code with C+ plus idioms in it because the person are going to hand your algorithm to programs in HaSkell。

😡，What we want is language agnostic things keep the language specific idioms out now generic idioms like for loops and function calls and arrays and standard data structures like binary search trees and so on。

 those are all fine because we've all seen those things in the prerequisite classes。😡，系。

But like don't use Python negative indexing just as one example。

 because then they plus plus people will get bus errors。😡，Okay。The second thing that we want。😡。

In addition to a description of the algorithm。😡，Is some justification for why the algorithm works？😡。

Now， what this does not mean is a complete formal proof。😡。

With horizontal style preconditions and post conditions and coat andvaris at every line。

What we want is a high level description of what the algorithm is doing in a way that justifies， oh。

 and this part we can implement with a whatever first search and that part we can implement using merge sort。

😡，嗯。And we break it into these three phases where phase one does x and phase two does y and phase three does z。

😡，That that high level description in that justification helps convince us that you didn't just hear the algorithm。

😡，On your bus ride to school and scribble it down。but that you actually understand why it works and that also helps convince the Bright 374 student in case there's some ambiguity in your description what you were trying to accomplish will help them implement it。

嗯。The word to watch out for whenever you describe things。Um。

The moment that you find yourself wanting to say the word just。That is a red flag。

The graders will look for that word。In your， in your submissions， what that word means is。😡。

Here is a detail that I don't want to think about。Because it's probably wrong。😡。

I don't know how many times。I have been bitten by this where Ive written papers where I write the word clearly。

And the referee comes back and says， no， actually that's wrong。😡。

so there are a couple of synonyms for this。嗯。Simply。😔，Clearly。Obviously。

all of these are immediate signals to us， and it should be immediately signals to you that you've probably made a mistake。

😡，If it really is simple， give the one sentence explanation。😡。

If it really is obvious then you don't need to point that out。😡，You're saying obvious。

 that's actually a signal of a bit of what's the right word？啊。Lack of confidence。

You're trying to bully us into believing you instead of just convincing us。

Same thing when we say analyzing algorithm。😡，嗯。We don't just want。😡，The running time。

So this is going to be especially important for some of the problems on homework one。

We want some justification for why the running time is what it is now if your algorithm consists of for I equals one to n for j equals one to n do something constant time。

 okay， that's n squared。😡，We know that you don't need any further justification。

But if you're doing something recursive。We'd like to see the recurrence。😡。

And then a couple of words about how you solved it。😡。

Or you know if you want to give an inductive proof， that's great。

But if you say I derive the answer using recursion trees。😡，Okay， that's fine。

 we can fill in the details from there provided that you get them right。Okay， so。Again。

 we don't necessarily want complete details， but we want to be convinced that if we asked you for complete details。

 hey， could you tell us exactly how you did this recursion three thing？😡。

We have some confidence that you've be able to answer us。嗯。U。

Any other questions about our expectations on the homework？Those of you took 374 from me。

 you might remember we had some fairly detailed standard rubrics with one point for this。

 one point for that。Probably not going to be that specific。In 473。

 because generally the main justification for those point by point rubrics was to give you a guide for exactly what we expect。

😡，嗯。will be。The grading will probably be on a little bit coarser level than that also because we're a little bit shorts staffed。

嗯。But we'll announce the rubrics when we post the solutions and you'll see the Bgrade Sc。嗯。Oh。

 I guess one thing that some of you got the email you might be noticing that I'm wearing a mask。

 we did get an email from the chanceancellor on Monday。

 community transmission rates for COVID are quite high with the return of everybody to campus so the current recommendation of the university administration is that everybody wear masks when you're in the classroom。

This is a recommendation， this is not a requirement。😡。

I can't force and wouldn't want to force people to wear masks if'm not comfortable doing so。

But please do be aware that transmission rates are high。😡，And you can get CoviId。

Even if you've had COVID before。And you can give other people COVID even if you don't realize you have it。

Okay。嗯。I think that is all of the。Administrative logistical question comments I have。

 does anybody have any questions？嗯。ok。So let's。Talk about。Laatton。So。The space。

A little white blank space that we。Put。In between words。Was invented in Ireland in the9th century。😡。

Yes， question。Or Sp。Oh， this is a good question。I talking about like describing an algorithm。嗯。

Even whether or not we actually give you a target running time in the problem statement in the homework。

 we have a target time in mind。😡，In order to get full credit。

 your algorithm needs to run in that target time。😡。

If you have an algorithm that's a little bit slower。😡，Well， there'll be some deduction。

 typically it's on the order of two or three points per factor of n。

So if we want an n squared algorithm and you give us an n cubed algorithm。

 that might only be worth seven out of 10。Um， if it's just a raw brute force。

 no thought at all algorithm， it might only be worth five。😡，On the other hand。😡。

If you the target running time that we have in mind。😡。

Is not always the best running time that we know we can achieve。It's just the best。

Striing time that we think is reasonable to expect you to achieve given the tools that you have。

So if you turn in an hour and it's faster than that， then it goes the other way。

 if we expect n squared and you give us n， that might be worth 13 or even 15 out of 10。😡。

So generally we don't give you those target running times， we will for some problems in homework one。

 and the reason for that is often when we give the target running times。

 we get a lot of algorithms that run in that time and don't work。😡，And should always aim first。😡。

For a correct algorithm。And then make for a faster correct algorithm and then for a faster correct algorithm and so on。

So don't aim for the running time first。😡，Aiming for something correct first。

That'll actually show up in the lecture on talking about today as well。That answer your question？

Awesome。Okay， so spaces， so for a long time， this is the way Latin was written。😡。

The words are just sort of strung together into what was referred to as。Scripto continua， I believe。

 probably getting the Latin endings a bit wrong。嗯。And。😡。

The structure of Latin is such that if you kind of know。

 like downs tend to have fairly common endings。Um， sortr of like Spanish。

 a lot of nouns end with O or A。That's because Spanish is derived from Latin where a lot of nouns and in U orum。

And likewise， you can kind of look common endings for adjectives and so someone who reads Latin like a native could just read this sentence without any trouble。

U。But I'm guessing most of us in the room aren't like that。UmLike I said。

 spaces were invented by monks in the ninthth century because their eyes tired。😡。

They also invented lowercase， they also invented now they didn't invent beer。

 that was the Egyptians but they invented certain kinds of beer。

So the three best inventions that come out of Ireland。Nothing， small things and beer。

So when we write English， we put spaces between the words and so there's no ambiguing。😡。

But Latin wasn't like that and so someone in the modern age reading something like this。😡。

Is faced with the problem， how do I divide this string up？😡，In two words。Now。

I'm going to simplify the problem here and just say， let's imagine that。😡。

I've got either a dictionary or I've got some algorithm that will decide whether a given string is a word。

😡，There's no underlying grammar or any you semantics or anything like that I just want to take the string of letters。

😡，And split it into words。Can I do it？At all。😡，Or is this this just nonsense？

So this is the problem that I want to solve。So， given。The string。Can we。Split it。Into。可。Sequence。

Of words。Where words is really defined。By some boolean function that takes a string and returns true or false。

That function is just given to us。This particular sentence， by the way。Is from a famous speech by。

Cicero。So Cicero was。Involved in resolving a disputed election。My how times have changed。Um where。

Cicero's。Oit was accused of bribery and that he won the election by means of giving people money。

And Cicero's job was to defend that person against。

The person's opponent who happened to be Cicero's friend。Before the trial。

And what this basically says is he's attacking his friends。Expertise as a lawyer。😡，sing。First of all。

Premmus。Dignity in such matters is impossible， this is concerned with trivial stuff like individual words putting points between letters。

😡，Because the way that some Latin people did this。m， is they would put a little dot。真。

Tens the Ana known protest。 they put a little dot called an interpunct。In between the letters to。是。

Represent what we would now call a space。And this is considered， you know。Yeah， trivial work。

 you know， just like learning spelling is or learning to type is now not you know unbefitting of anyone who would call themselves a legal scholar。

So all he's doing is segmenting the string into words。That's trivial stuff。So。😡，How do we do this？

How do we solve this problem？Well。😮，Yeah。去。对。被告。是。So， so。嗯。If I pass the word。嗯。Manslaughter。

Or the word you know nowhere，s a bit even better example， if I pass the word nowhere is word。

 it says yes， nowhere is a word if I pass the word now it says now is a word I pass the word here。

 it says here is a word。😡，His word doesn't know anything about whether they're sub wordss。

 it just says if the whole string is word。😡，So yes， manslaughter is a word and man's。

 if you imagine an apostpostrophe is a word and slaughter laughter is a word。嗯。啊。

So that ambiguity is part of what makes the problem interesting in reality。😡，Because in reality。

 I don't just want any old decomposition of the words。

 but I want something that's semantically meaningful。There's。I think it's。

At a higher level of granularity。I think it's St。 Thomas Aquinas， who like writes a whole chapter。

About。Decomposing。嗯。Text in the Bible into sentences。Because at that point， they'd invented spaces。

 but they hadn't invented commas。And you get different interpretations depending on whether you where you'dve described the decide to split up the list of words into different sentences or not。

So in reality， the semantics matter， we're going to completely ignore that the only question here is is it possible at all to split it up into words？

😡，And then you could layer something on top of that where different decompositions into words might have different scores and you want the highest scoring decomposition。

Or maybe you want to count the number of different decompositions or the most likely decomposition or something like that。

 let's start with the simple problem and we can work our way up later。Okay。So。嗯。

We're trying to decompose。啊。Sequence of letters。Into a sequence of words。Okay， so。

Faced with any problem where I'm trying to construct。😡。

Some kind of structure in this case is sequenced。The first thing I always think is。

What's the definition of that structure？Say what is the definition of。A sequence of words。

What kind of thing are we actually trying to build？Okay， that's a synonym list。

But what's the definition？王建伟。We're trying to write code here。😡。

I want want to type that I can put in here。Basically， a type declaration。Okay。

Here's what the sequence of word is， there are two cases。😡，Case one， nothing。The empty sequence。

 no text at all， that is a sequence of words， it contains zero words。😡。

The other possibility it is a word followed by a sequence of words。😡，诶。😊，So。This is。Either nothing。

Or。Word。Follow by。A sequence of words。Yeah， it's a recursive definition。

A sequence of integers is either nothing or it's an integer followed by a sequence of integers。😡。

A sequence of giraffes is either nothing or to giraffe followed by a sequence of giraffes。

The sequence of sequences of integers is either nothing or it's a sequence of integers followed by a sequence of sequences of integers。

😡，Okay， so。This sequence is a template that you would apply to any other type。😡，U this is also。

 if you remember from 374， the definition of a string， a string is either nothing。

 the empty string usually written by epsilon or to single character followed by a string。😡，系。So。

When we want to build this kind of recursive structure， very， very simple recursion。😡。

The way that I want to think about it is。I need to try to build the parts of it that are not recursive。

😡，And I need to figure out a way to convince the recursion fairy to build the parts of it that are recursive。

😡，嗯。I want to if if I can say。There's nothing to build here that I'm done。

 but the only case where that would be the correct sequence of words is if my input string were empty。

😡，So if I'm given the empty string， I can immediately return true， yes。

 you can decompose the empty string into a sequence of words of length zero， namely zero of them。😡。

OkayThe empty string decomposes into the empty sequence of words。Otherwise。My question is。

 what is the first word？😡，And then the recursion fair's question is。

 once I figured out what the first word is， can you split up the rest？系。😊，So。These。

Handling this is my job。Handling this is the recursion ferries job。

So the question that I need to ask is。What is？The first。wordord。

I can just get an answer to that question， everything else can be done recursively。

 somebody else's problem， not mine。Okay， so。There are lots of places where I could end the first word。

😡，Let me get rid of the correct answer here。So I mean I could split the first word after P。

 I could split the first word after PR， I could split the first word after PRI。嗯。

How do I tell which one of those is the right one？当。Okay， so I can use Iword。😡，That's okay。

I'm going to sort of try all prefixes。I need to。Pass that prefixction to his word and have it returned true。

But that's not necessarily sufficient。Because there might。B multiple prefixes that are words。😡。

How do I know which one of those？Is the right one。是。Right， so let' me say that again。😡。

Whatever word I choose in this case， the Latin word premisemus， which means。😡，First。U。

In order for that to be the right choice for the first word。😡。

The recursion ferry has to say yes to the rest of the strait。

The rest of the string has to be decomposable into words as well。😡，Now。

 for some choices of first word， the recursion fairry might say yes。

 and for some choices of the first word， the recursion fairry might say no。

 and that's independently of whether I pass this is word chat。So the only thing。

 because I have no idea what the recursion theory is going to say。The only choice I have。

Is actually just to use brute force。For every possibility for the first word， I need to ask。😡。

Is word true？啊。And。Is the rest。Sputable。Into。Orts。Right。

So I have a string of length and there are a linear number of prefixes。

 I'm going to get a for loop here for all possible prefix lengths。😡，If I see a prefix。😡。

For each prefix I'm going to test if it's a word， if I get no。

 I'm done with that iteration as a loop。😡，But then I'm going to pass the rest of the string the recursion fairy and if word of the prefix is true and the suffix is recursively sable。

 at that point I can just return true。😡，And so if I turn this into code。Here it is。This is my。

Brote force recursive algorithm for deciding whether a string of letters is splittable into words。

And passing in an array， again， there's the vac space case。

The empty string is splitable into the empty sequence。😡，Otherwise， I try all possible prefixes。

 I here's the length of the prefix。If that prefix is a word。

 if the recursion Terry tells me that the corresponding suffix is splitable。

 then I immediately return true。If I get through all the prefixes， then I never find one that's good。

😡，Then I know the answer is no。And I return false。Okay。

So the fundamental process that I'm going through here is。

I think about the structure that I'm trying to build as a recursive structure。😡。

I essentially try all possibilities for the non recursive part of that structure， in this case。

 the first word， and I let the recursion fair think about everything else。😡，And as usual。

 withren recurrent recursion。😡，It's really tempting to try to open up the black box and try to imagine what's going on ins sable but it's really not any of our business。

 let the recursion ferry do that it's good to at its job， it's fine。

 just like it's also really none of our business what's going on inside isword that some library call we have no control over。

😡，哎。So delegate the things that you have to delegate。😡，And then let them be delegated。Now。

There's a slight inefficiency to this algorithm。Which will very quickly chew up any significant CPU time in practice and probably drain your memory as well。

You really don't want to be passing around a raise。You don't want to take a one terabyte string。

 pull off three characters and take a one terabyte minus three characters string under the stack。

Okay， so what I really want to do is to figure out， you know。

 the standard C process here would be to pass around to pointer。

 the way we normally abstract this in this class is I'm going to treat。😡，The input string。

For the moment。As a global variable。I know that's a sin。But we're going to。嗯。Yeah。

We're going to absolve ourselves of that sin momentarily。And then I'm going to define a function。😡。

Splittable of。Let's call it， I。This is。True。If and only if。The suffix from I to N。Is sable。

Into words。So。This is a just an English specification of the function that I wanted I want to evaluate it's always really。

 really crucial to actually write that again two things write that specification down you'll notice in particular that。

😡，The function has an argument over here on the left。

 and the output of that function depends on that argument in some explicit way。😡。

This is a remarkably easy mistake。😡，make to not have that connection。

 to define some recursive function where the parameters that you define on the left don't actually show up in the definition on the right。

one of the things that we explicitly look for。And now if I if I do it this way。

 I can think of this as a specification for an algorithm。

 I'm just going to pass in an integer instead of a whole array， I can easily now take。😡。

The earlier array based algorithm and rewrite it in this index formulation。😡，嗯。

And now the empty string is indicated by， well， the start of your suffix ran off the end of the string。

I'm like looking at the suffix of this string like then starting at character n plus one。

 there are no characters out there， I hit the end， I hit my base case。

So I can just immediately return true。Otherwise， my question that is where does the first word end。

 it starts at index I， so I'm only interested in segmenting that suffix。

 the first word in that suffix。😡，Ends at some character J， I don't know what that index is。

 so I try all possibilities。😡，I check it。Whether that substring is a word， and if it is。

 I pass the reigning suffix to the recursion ferry。😡。

I've changed the syntax of is word slightly here， but hopefully it's clear what's going on。

Um now up above。You'll see this collection of symbols。That's exactly the same algorithm。

 but written in math instead of pseudocode。😡，In particular。That that brace thing over there。

's and if then that's a case statement。😡，That upside down， that large V， thats Sibuolean or。

 but because it's large and it has indices above it and below it， it's pronounced for loop。😡，U。

And again， that upside down v is just the logical end。😡，So these two。

Descriptions of the recursive algorithm。😡，Are identical。

If you're more comfortable writing it that way， write it that way。

 if you're more comfortable writing it this way， write it this way。😡，It。嗯。OkayAnd now this algorithm。

 hopefully it's clear that it's equivalent of the earlier array based algorithm。

 and hopefully it's also clear that I'm not suffering from this problem of passing as around and filling up my stack。

Okay， is there any questions？Good。Okay， now。嗯。It's the running time of this algorithm。

Anyone care to guess？Sorry。这好。Yeah， it's actually going to be。嗯。On the order of two to the U。

It's exponential。嗯。Now I can give you a recurrence for this， right。😡，嗯。

Let's say it's a little bit awkward because I've done this in terms of suffixes instead of prefixes。

But essentially it's going to be for the whole string。I need to figure out。

For all possibilities of for the prefix。This be links i from one to n。I'm going to call his word。

 let's just for the moment， say that's a constantantine operation just because we'll count those。

Right， so I need to constant。Plus T of n minus I。And there。Ways of unrolling。

This recurrence and turning into something that looks a lot more like the tires of an oil recurrence。

 and it ends up presolving to begove to to the end。

But another way that you can think about why this running time is exponential。😡。

Is I'm essentially enumerating all possible ways in the worst case。

 I'm enumerating all possible ways of splitting the input string into words。😡。

There n-1 places where I can。Draw a word boundary where I can put an inner point。

The non recursive part of the algorithm decides where the first one is。

 the recursion ferry decides where the rest of them are。😡，By the induction hypothesis。

 the recursion ferry is trying all possibilities for where the rest of them could be。

So that means the algorithm as a whole is trying every possible subset of those n minus one places I can put a point。

😡，And there are two to the n minus one such subsets。So this is very much in the same spirit as the。

Divide and conquer algorithm for integer multiplication where I do all four partial products。

 I get this recursion tree that eventually boils down to n squared。

 if you look closely you end up comparing every pair of digits， same thing here。

 this is just a fancy way of saying try all possible ways of splitting it and if one of them is good return true。

😡，Shouldn't think of it that way when you're designing it， but that's what's going on into the hood。

Now。Yeah。You could be pretty sure。That Cicero is not about to run an exponential time algorithm。嗯。So。

We're doing something here that's a little bit stupid。And anybody。Suggest what that might be。Yeah。

What do you mean？Okay。Yeah， yes， I think so， but can you explain what you mean？😡，Okay。

 so that was the key word recalculating。😡，So， I mean， let's imagine that my input string starts。😡。

Like this。I don't know what the rest of it is。Now， one at the top level。

 the algorithm is going to say， oh， maybe I can split here and then one level deeper in the recurrence。

 I'll say， hey， maybe I can split here， and then I'll recurse on everything starting at X。😡，So。

In that sequence of recursive calls， among other things。

 I'll know whether the suffix starting at X is splittable or not。

But now if I go back up to the top level。😡，I'm also。Going to say， oh， nowhere， that's a word。

 Let me chop that off and now ask the recursion fairry。

 is this suffix starting at x exploitable or not， the recursion fairies already figured this out。😡。

But one of the frustrating things about the recursion fair is they don't remember anything。

You say is this splitable and he goes， oh， let me find out。

And then later you say to the same question， is this splitable， I don't know。

 I'll go find out and do the work again。😡，In this example， I'm just evaluating the same suffix twice。

 but if you imagine that the input string is now here， now here， now here， now here， now here。😡。

The deeper you go， the more things have to repeat。系。So。Where're。嗯。There's a lot。

Let me see if I can spell。There's a lot。Of。Redundant calculation here。So。

How do we avoid that redundant computation？We do the thing that recursion Ferry doesn't do。

We remember things。So the first time I ask。😡，Hey， is this suffix starting at index8？😡，Splable。

You ask the recursion fairy， thecursion fairry comes back and says no。Then you write that down。

And the next time you need to know whether the suffix starting in index 8 is splitable。

 you don't ask the recruitcursion variable first you check your notes， oh wait。

 I asked the recruit variable， he said no， done。😡，请。😊，So。

I can avoid that by using something called memorization。

I have no idea why the word memorization doesn't have an R in it。😡，But it doesn't。

Even though that's what it means。😡，嗯。Whenever you make a recursive call。You remember its result。

Before you make a recursive call， you check， have I done this recursive call before？And if you have。

 you look the result up in your memorization， something。😡，List table。Structure。

And check you before you call。Okay。So if I want to memorize this particular function， splitable。😡。

I need to think， oh， what sort of data structure am I going to need。

 so I needed a data structure where I pass in an integer I。😡，And I get back as a result， either。Yes。

 it's splitable， no it's not splitable， or I haven't seen that before。😡。

What might be an appropriate data structure for that？😡，Good。

Three out of four times when I asked this question， the first thing people say is a hash mapap。😡。

And then I say， great， what hash function would you use？Your keys are integers between one and n。😡。

A hash map where the hash function is the identity function is called an array。😡。

So I'm going to store。😡，嗯。Answers。In。An array。We might as well call that。Split table。From one to n。

Because it's a table。嗯。And so there's some slight modifications that I would need to make to the code just right there before it says it's splitable J+1。

 I would say， oh， if split table of J+1 has a value in it。

 then I just just look up that value otherwise I make the recursive call and then at the end before I return to a false。

 I can write into the table or maybe it'd be even easier when I'm at the very， very top。😡。

Of the splitable algorithm， I look in the table and if the answer's already there， I just return it。

 otherwise I compute it， put it in the table and then return it。😡，So not much difference in the code。

But now。The running time drops to。What。😡，Well。There are n entries in this table。

 each one corresponding to a possible input to the splitable function。😡，For each。Entry in that table。

I run for loop。Right N。And inside that for loop。If I don't count the recursive calls。

I'm making one call to his word and one look up in the table。U。So。

What this is going to end up being is。N squared in fact， I should really say n squared calls。😡。

To his word。Plus， n squared additional time。There are in different calls that can be made where I actually have to do some work。

😡，For each of those calls， I need to do a linear amount。😡，Of calls is word。

Linear times n is quadratic。that's memorization， you save the time。

 you don't need to do much to the code。😡，If you're writing your code in Python。

 you can actually just put a decorator in front of the recursive function， say memmoize。

It'll put it into a hash mapap instead of an array， but you know。It's Python。Um now u。

That's great for getting efficiency。But it's a little bit fragile。

 It's a little bit hard to understand the。The analysis。

And it's actually still a little bit inefficient in practice。

Because I still occasionally have to recurse and that's still going to involve pushing things onto the stock frame and that's still going to take time and it's still going to eat up space。

So instead， I want to imagine。Now think about the following question。Here is my array。Split table。

Indexed from one to n。How is this array going to fill up？I mean， if I run that recursive algorithm。

 except anytime I get an answer to a recursive call。

 I'm going to write it into my table and never call that again。😡，I'm going to。Stillill up the table。

From right to left the first thing I'm going to notice actually if I extend this to n plus one is the last entry table is going to be true that's the base case it's written directly into into the algorithm The next thing I'm going to check is the suffix of length one。

😡，Either that one character is a word and I put T in there or it isn't and I put F in there。😡。

Then suffix of length too。Now。The way the recursive algorithm works， I start with the whole string。

And I make a recursive call on some suffix and make another recursive call on some suffix。

Pushed shorter and shorter suffixes onto the stack。And then when I get an answer。

 I start popping things off。😡，So the recursive calls are being made。In order from left to right。

But the answers are coming back。😡，From those recursive calls。In order from right to left。

Just because when I call things， I call a recursive function， I'm pushing something onto the stack。

When I get the answer， I'm popping things back off the stack。

See this reversal again in other contexts。Okay， so。The array。Pills。From right to left。Now。嗯。

Where am I here？One question then is。If I know the array is filling from right to left。😡。

He wanted to design an algorithm。That would fill an array from right to left。

 according to the output of this function。 This is not how you would do it。If you look at this。

Recursive thing， if you yeah， think deeply about recursion。

 you can figure out that it's going to fill in the array from right to left。😡。

But if that's your intention， that's what you want to do， just do that。😡。

And so this is the part that turns this into dynamic programming。Do that。On purpose。

Instead of doing it accidentally。So a sort of dynamic programming version of splittable。Again。

 now I'm going to be given the entire array。Sorry。😔，I'm going to build an array called split table。

I'm going to fill in。The啊。The base case right off the bat。And I'm going to say， well。😡。

What order does the table get filled in？ Well， it gets filled in from right to left。

 So I'm going to write that for I goes from N down。To one。And then in this part here。

 inside that for loop。I'll copy the code that evaluates splitable of I。😡，Now。

 occasionally sable of eye will make a recursive call。

 but it always makes a recursive call with a larger argument。

Which means that the value of that recursive call is already in the table。😡，Okay。

 so I'm going to replace this。😡，Function call with an array lookup。

 and otherwise I'm not going to change anything。😡，So。I'll go ahead and write that in。

Or J goes from I to N。If。Is word。I J。And。If。Split。Table of J plus1。Then。

Instead of returning a function， a value， I'll write this into the。This one's true。

And then I think I should initialize。The table up here。

I'm going to assume it's false into proved otherwise。And then in the end。

The only thing I actually care about。Is split table of one。

That's the answer to the function called splitable one。Here's my dynamic programming algorithm。😡。

I build this memorization structure， I figure out what order I need to fill it in。

 and I fill it in in that order。😡，UHope it's really clear now that。

This is two nested for loops with a constant amount of stuff inside。So the running times n squared。

Is very little wasted anything going on。 There's no pushing stack frames。

 there's no computing hash functions its just。😡，Two nested four loops。

 a function call and an array lookup。Thank。This is what we're aiming for。

Now when I say this is what we're aiming for。😡，嗯。That's not the first step。😡，The first step is to go。

huh。What kind of thing are we building？😡，How do I do that well it's a sequence。

 so I need to think about the what's the you know， what question am I asking to start off？😡。

That I can let the recursion fair you do other things。

Then I need to come up with some sort of recursive formulation。

Where I define a recursive function and then figure out a way to evaluate it recursively。😡。

Once I've got the recursive formulation， then I can figure out what data structure to use to memorize。

😡，And what order to fill that structure？But it's really important。 it's really easy when。You know。

 especially for simple problems after you've had some practice to just sort of jump into the nested for loop stage and you might even get it right。

But when things start to get complicated， if you jump into the nested for loop stage first。

 you will get lost。😡，Because you haven't figured out yet what you're trying to do。😡。

So this is why states start with the recursion and then make it iterative。嗯，Right。So I want to do。

I'm happy to take more questions on this。😡，I want to run quickly through one more example in the 20 minutes that we have left。

It。你个有。Yeah， we could have a break。That would change the running time for order n squared to order n squared。

系。嗯。😊，So little。Optimizations like that。Those are really important when you're doing this in practice。

 but that's sort of the next stage after you leave this class。😡。

So things that have only a constant difference in the running time or that don't actually happen all the time。

 and so you can kind of ignore them for purposes of worst case analysis or don't even worry about it。

Again， similarly， instead of just filling in split split table of n plus one in my recursive formulation I could have said。

😡，If the length is less than a Google， brute force。Constant time。

Because in the analysis of algorithms， it's always this function length parameter。

 and we're not interested in small values of N。😡，Like Google。

 we're interested in the behavior of the running time as that parameter goes to infinity。😡。

That's what the Big O actually means is how fast as this end grows。

 how fast does the running time grow？Small values， specific values aren't really interesting in this room。

😡，Obviously in practice is you can get your code。😡，To run at all。

 when the length of the string is a Google， you've broken the laws of physics。You'll win some。嗯。😊。

But in here， Google is just a constant。嗯。Okay。So let's try another。Fairly。Hopefully。

Maybe even familiar， but a relatively simple example。O。So。Ignore the coloring at the moment。

Here's the problem I'm given， I have an array of integers。😡，In this case， the digits of pie。

I want to find the longest sub sequenceequence。Of those integers that's in increasing order。

Right so this is the。Longest。Increasing。ASubsequence problem。

So a sub sequenceence means basically a subset， but you remember what order the elements are in。

 so one， four， five， six。😡，There bold red numbers there。

 that is a sub sequence of the first 20 digits of pi。It's not a substring。

 substrings are always contiguous。😡，So words in the previous problem are sub strings。

 sub sequenceequences can have gaps， but the order matters。😡。

Increasing means that each number of that sequence is larger than the one before it。😡。

It's in sorted order。Hey。So。This is another one of these subsequent problems。

I'm given a sequence of numbers， so I want to pull out a sub sequenceence of it。😡。

Definition of a sequence of integers。嗯。It's either an integer followed by a sequence of integers or。

Nothing。😡，Okay， so。U。So I want to try to think about doing the longest increasing subence problem in a way that fits with that recursive definition。

😡，Okay when is the longest increasing sub sequenceequence empty， when the input string is empty？😡。

I think that seems fairly clear otherwise。The question that I should ask is。What is。The first。

Element。Of the longest increasing subsequentence。Well， that's one way that I can ask。

The other possibility I could ask is。Is the first element in the input array。

In the longest increasing subsequent。So I could either say。

 I want to pick out a sub sequence of the elements。😡。

And that are in increasing order and I get as many elements as I can。

 there's two ways that I could approach this， one is to go from left to right to each element and go is this one in or out。

 is this one in or out， is this one in or out？😡，The other way I could do it is what's the first number in the output。

 what's the second number in the output， what's the third number in the output， so on。😡，So one。

 I'm kind of。Walking through the input。😡，And the other one， I'm kind of walking through the output。😡。

Both of these approaches lead to efficient algorithms。😡，I'm asking for trouble here。😡。

But I'm going to ask the question。Do you want me to go to left or right？😡。

Do you want me to develop the algorithm where the question we're asking is。

 what's the first element of the output？😡，Or do you want me to develop the algorithm where the question is。

 is the first element of the input in the output？😡，So。Look at first element in the output。😡。

Raise your hand。Look at first settlement in the input， raise your hand。They don't have a coin。

can I can flip my phone here， I can flip this is just a case， okay。So。Dead guy。Input， blank output。

So。Input。Oh。😮，It's not just a case。Now it's a case with a loose caps lock key。

Which way did I say to do it？Input， okay， let's try this one。We're going to go this way。All right。

 so。I'm playing a little bit f and loose because I'm trying to develop intuition。

 but I should imagine that what I'm going to do is I'm going to walk from left to right through the input sequence I'm going to ask do I want the three do I want the one do I want the four do I want the one do I want the five and so on and the bold things that have wrote in read up there those are the ones where I said yes。

😡，And the gray ones are the ones where I said no。Okay， so I want to know。Do do I want the five？Now。

Do I want the five。No。😡，No， this is an instance where I actually know the answer without doing any other。

😡，Recursive， anything， Why don't I want the five？Is it smaller than the six？😡，Now。

This is a subtlety year。My recursive subprom isn't see that suffix。

Find me the longest increasing subequence。😡，There's an extra condition。😡。

Their decisions that I made in the past。That I need to remember something about so that decisions I make in the future lead to a consistent result。

😡，So I need to remember something extra about the things that I've already done。😡。

Before I look at the suffix。😡，With the word segmentation problem。

 I don't care how I got to the suffix starting with X。😡。

The answer is either the suffix is splittable or it isn't。😡。

Here there's a little bit more information that I need to carry。Specifically。

 I need to remember the last number that actually chose to be part of my increasing subsequentence。😡。

And this is the trick。I said， you know。But。And I said， go back to the definition。

We recited the definition of a sequence of integers。

We didn't recite the definition of an increasing sequence of integers。Right， so we really。

When we say increasing， actually what you would want to say is its either nothing， that's fine。

 or it's an integer followed by an increasing s of integer that's bigger than that first integer。😡。

Except that's not recursion。What you really want to say is。An increasing sequence。Bigger。Then x。

Is either。Empty or。It's an integer y bigger than X。Followed by。An increasing sequence。

Bigger than why。So the real recursive definition of the thing we're looking for has to have this extra parameter in it。

😡，I need a lower bound on the things that I'm allowed to include when I see a five there。😡，Well。

 I know the last thing I included was a six and I know that everything I need to include is bigger than that。

I can definitely say no to the five。So then the next thing I need to look at is the eight。And。

Do I want the eight？Yeah， question。So what I'm imagining is somehow a little bird landed on my shoulder and said。

The longest increasing sub sequence starts one， four， or five eggs。

Now I've already ruled out for whatever reason， the five and the three。😡，What's next。

 what's going to be the next thing？But when I think about that question。

 that's not just a question about the stuff to the right of the black line。😡。

I also need to remember one piece of information about the stuff to the left of the black line。

 namely that largest number。No， when I look at this eight。😡，Do I want to include the eight or not？

Good answer。Cect answer is I don't know。Maybe you do， maybe you don't。

 how do you figure out whether you want it or not？You check recursively and say there are two options。

 either eight is in my longest increasing sub or it isn't。😡，Well， if it is。

 then I want the recursive call is。Find me the longest increasing subsences of everything after the eight that's bigger than eight。

😡，If the answer is no， I don't want it， then my recursive call is find the longest increasing sub sequenceence to the right of the eight。

 it's bigger than six。😡，I have two recursive calls。They're going to return different values。😡。

Based on those values， I will figure out whether I want the eight or not。😡，Now。

One of the things that it's。Really， really tempting to do when faced with this。

 do I want this or not， is to come up with some ad hoc reasoning for why you might or might not want it。

😡，This is called the greedy algorithm。嗯。It's wrong。There are cases where greedy algorithms work。😡。

But。Greedy algorithms are like guns。You have to assume they don't work。

Unless you've unloaded it yourself， I mean， you have to assume that they're loaded until you prove them correct yourself。

 I mean sorry。😡，Until you write down a proof。You have to assume they don't work。Just like a gun。

 if you haven't unloaded it yourself， it's loaded。😡。

Don't point it at anything you don't intend to kill。Um，Okay， so don't don't do that， first of all。

 it's too much work。😡，To say， look， there are two cases， yes or no， try， yes， try no。

 see which one gives you the better answer。Just simple brute force。Okay， so I'm going to define。

Let's let's set up a。Global variable。For my input。Again。

 I'll call it a from 1 to n because a is the first letter of array。

Then I'm going to define a function again， I'm going to use indices rather than arrays as my arguments because I don't want to pass arrays around in any real code and because eventually thinking in terms of indices will make the eventual dynamic programming algorithm faster or easier to think about。

😡，So this is the length。Of the longest。Inc。Subsequence。Of the suffix， AJ through N。

Where every element is bigger。Then。A sub I。So in this example here。

Where I've already picked out  one，4， or  five， six， them looking at eight。

 I think that's at index 12 in the array。And the six is at index9。

 so the question I'm trying to answer here is LIS of9 comma 12。😡，嗯。Now I can write this out。

There's always going to be a base case， and it's usually going to be。Dealing with the empty string。

So if the suffix I'm looking at and sort of fallen off the right end of the string。

 the longest increasing sub sequenceequence of the empty sequence is empty。In fact。

 the only sub of the empty sequence is empty。嗯。If J's less than n， then I have two possibilities。

One is。That I can't include A J， because it's。AJ is to。Big， sorry。In that case。

I'll say ignore AJ and move on to J+1。That was the case with the five earlier， five is less than six。

 so just ignore it and move。Your index finger down the array by one。Otherwise。

 it's the maximum of two values。It's either LAS of I J plus1 because you decided not to use the number at position J。

Exactly its in the previous case。Or it's one plus。L A S of J J plus1。

You did decide to use a sub J that adds one element to the sequence your computing。

 that's the one plus。You're still recursing on the suffix。😡，It starts at index J plus1。

 but now everything needs to be bigger than ace sub J。😡，So I decided here。I want the eight。😡。

If I decide that I want the eight， then' to recurse， I have to say， okay。

 now everything needs to be bigger than that eight。😡，I can forget about six。Okay。

 there's my recursive function。What sort of data structure should I use to memorize this function？😡。

The input is going to be two integers。Each between1 and n。The output is going to be a number。

The 2D array。Okay， here's how I spelled 2D array。This is to be clear。

I'm going to index the rows by I and the columns by J。

Now the question is what order should I fill the array well。

 let's look at a particular value of I and J and ask。😡，Before I fill in that entry in the table。

 what other entries might I have to look at？😡，Well。If I'm filling in IJ。

 I might have to look at IJ plus1。😡，Same row， next column。😡，And I might have to look at JJ plus1。

Lower row， same column this will be。Just above the main diagonal。

So I need to fill in this array or actually just the top half of the array in some order so that the red stuff gets filled in before that white square。

😡，What order should I use？So。It's a two dimensional thing。

 so I'm probably going to use two nested loops。😡，So I need to specify the order for the outer loop。😡。

And I need to specify the order for the inner loop。So what are we going to do in the outer loop？😡。

Yeah。Okay， so in the outer loop。Let's decrease J starting from in。

That means the double arrow means outer loop。The battle loops going from right to left。

And then in each iteration of the outer loop I'm considering the column， so in the inner loop。

 I need to go through that column in some order。😡，What order should I use？嗯。Right。

 I don't care either。😡，Doesn't matter。😡，There are no dependencies between things in the same column。

😡，So it doesn't matter what order you traverse the column。😡，So I'll just， you know。

 write a double error here that means， you know， I don't care， maybe you go up top down。

 maybe you go bottom up， whatever is easiest for you think about。

So outer loop goes from J from n under one， inner loop goes， say I from1 up to J。😡。

What's the running time of the algorithm？等一下说。Jake has what？J is an index。Fromwhere between1 and n。

 it's not a digit。I didn't， I mean， in the illustration。

 I said the integers we were given were just single digits。The real problem， they're just in。

So it's two nested for loops with a constant amount of stuff in it。So the running time is un squared。

And there is your dynamic programming algorithm。And that， by the way。

 is literally everything you need to write for full credit。😡，Ingos description， recurrence。

 cartoon for the evaluation order running time。Last question before we run on time。丧失问。Starting yes。

 that is the other way。So the other way of formulating the question leads to a one parameter recurrence。

 use a one dimensional array， but it's still the N up and implementation runs an n squared time。😡。

All right， we're a couple minutes over， so I'll let you go， I'm happy to answer questions up front。你。

