# 哈佛大学《编译器｜Harvard COMPSCI 153 compilers 2023》中英字幕（claude-3.7-s p09 1696256100-Compliers_on_10_2_2023_(Mon).zh_en -BV14PAUejE98_p9-

Yesestions as we move into homework for set up study groups for that and later， or you know。

 providing things like prompts and things for。For study groups to help get the most out of it。

 please fill it uncertain rather than later as homework2 remains fresh in your memory。

Because I'm sure that homework 3 is crowding that out as you're all jumping into it starting early。

 it's due I appreciate Monday， October the 23rd is you know unimaginably far away at this moment。

 It will come up quickly so I encourage you to start start started early。

 It is a challenging assignment compiling from L of VM into assembly code。And moreover。

 homework4 is actually going to be released in two weeks。On the 16th。So。I'd encourage you to。

 if possible， finish。Finish homework three before the deadline。

Any questions on the ebb side of things or otherwise？Okay。

 so today marks the start of a new part of the course。😊。

We were going to be starting to look at Lexing。Dig into this。 But， first of all， taking a step back。

 this is。The compiler architecture view that we saw very on at the beginning of class。

 And we've been spending a lot of time。Down here。In particular。

We've been looking at understanding X 86 and the most recently， codegen。

 So how to get from this slow level representation of code。

 this intermediate level representation into assembly。

 So what we covered in the last few lectures and what homework 3 is really going to be focused on。

We're now going to be jumping。All the way back to。The beginning。Of this compiler pipeline。

 And start looking at pasing。So parsing is the process of taking source code。

 taking this human readable text of programs， and turning it into data structures that the compiler that the machine can start manipulating and using。

Where。I can't remember I mentioned this， but pasing is really broken up into a couple of pieces。

 Leing。And  Lxical analysis and syntax analysis。So to clarify what I mean by this。

 when we take on a source program， it's a collection of characters， a sequence of characters。Right。

 if price greater than 500， then tax equals 0。0 weight。

What Lexing does is break up the sequence of characters as to what are known as tokens。

And to essentially units that make sense with respect to the grammar of the language， So here。

 for example， one token would be the keyword F， another would be the variable name price。

Another is the symbol greater than。As a binary operator and so on。

Syntax analysis takes the sequence of tokens。And convert it into a data structure。

 So into typically a tree abstracts syn text tree showing that， well。

 this is actually an if expression or a statement。It consists of two parts， the comparison。

 the then branch。So what we're going to be focusing on today is the first part， lexical analysis。

How do we go about turning the sequence of characters？Into these tokens。

Any questions about this high level picture？Okay。Right， so。

A given language is going to classify these different lexical items into what are known as token types。

 So think here about identifiers。These might be the names of variables， functions。

 other entities within your program， F， last in 14th。Number， nu is another common token type。

 maybe representing integer constants。73， zero。0，8，2。Depending on your language。

 there might be anocal representation dealing with a zero or maybe be decimal。Real numbers。嗯。

Often in a variety of formats。Keywords。Such as if。And then various syntactic elements， sorry。

 punctuation and operators， comma not equals LPn and so on。

So Leing is kind of putting these different combinations， these different sequences of characters。

Into these tokens。Each of which belongs to some token type。

We use the terminology reserved words for tokens that can't be used as identifiers。So for example。

 in C。Java， C plus， plus， we have the tokens。The woods， if void return。And various others while。嗯。

And so on。Can't be used as identifiers， right They're key words that are treated in a special way。

 both with respect to lexing， that is the token the token that they're going to be turned into as well as later on in passingsing。

Okay。So Leing taking this sequence of characters， turning into these tokens。

 each of which belongs in a token type。As the Lea goes through the sequence of characters。

 there are actually some things within the sequence。

 within the stream of characters that are not tokens。That essentially get discarded by the Lea。

 Any thoughts for what they might be。Hereer。Any kind of white。White space， good。

 White space is often very important for the Lea。 White space is used to separate tokens。

But typically depending on， depending on the language。It's actually not something that the。

 the Lexa will end up。Representing as a token type。 can interesting。 You know。

 what's what's really interesting is we've talked about this idea of abstract syntax trees where。

Various with a structure of the representation of the data structure。

 sorry the structure of the data indicates the grouping and the nesting。

 and as a result in the abstract syntax tree， we don't need things like parentheses to tell us the order of operations or curly braces to tell us how we're nesting statements grouping them together。

 So you're right there that the end result of passings doesn't need things like curly braces。

 But those are actually really critical。For the paing step。

So we do actually want to treat parentheses， curly braces as tokens because that turns out to be really interesting。

And really central to the pasing， like how we actually take the sequence of tokens and turn it into the structured representation。

Thanks， Abe Ben Mety。Comments， great。 So typically comments are just。Thrown out by Alexa Me。

Oo semi Collon， they're actually in a similar situation to braces and parentheses。 You're right。

 We don't need them once we've got it into that abstract。

 It's syntaxtry because they typically denote the end of a statement。

But they are actually important in the concrete syntax that when we look at a program and try to figure out。

The structure of the program， Sal and me Collins end up being important。eかさダ。Indentense， yeah。

 classify that as white space， so tabs and spaces， it does depend on the language。

 but languages like C and Java do not use white space to help understand the structure of a program。

Languages like Python， Haskell， whitespace is important。

 typically just in terms of the amount of indentation so that sort when things look visually like they are subordinate to something。

 the passing will actually reflect that。Yeah， you've got pretty much all of them。😊，Comments。

 new lines。嗯。Some languages have preproors， most notably C。And C plus plus。

 And the idea here is that。Before passingsing actually starts。

 it goes through a separate program that will have some instructions to it， including a files。

 defining files， macros that might end up being replaced with other sequences of characters。嗯。

These are typically not。Regarded as tokens， the processing that's done by the preprocessor。

Before the Lea ever gets to the file。And of course。

 preprocessing might use its own form of typically simple form of leing and interpreting of the file in order to define constants。

 include files， expand macros， and so on。Okay。Let's work through。An example。嗯。To see。

You get an idea of what the desired output of Lexing is。

So here we have the same program we had before， if open parentesis price greater than 500 close parentesis。

 then tax equals 0。0 weight。So electrical analysis is going to take this sequence of characters and return。

The following sequence of tokens。For this toy language that I'm。Hypothesizing。

That is the token F for the keyword。Left Per in and identifier a token。

 and the identifier token actually has additional information associated with it。

 What is the identifier that we wanted to use The symbol greater than and number， 500， again。

 a token with data associated with it。R per in， then another identifier attacks。

The equal symbol and then another token type real， again with data associated with it。

 per floating point， 0。0 weight。Okay。We're going to see in possibly excruciating detail。

 like how we actually implement this， how we can go from， specify the tokens that we want。

 how we go from a sequence of characters to this， but I am going to belabor the point of making sure we understand what the desired functionality of Alexa is。

😊，Okay。There are going to be sequence of characters that do not result in a。

In a successful stream of tokens here。😊，For example。There's nowhere way to tokenize this。

 right this is not a valid token，1 X A B。In our hypothetical lecturea is not an identifier。

 it's not a number， it's not a real number， we just end up with an error。Yeah。

 it could be based on the design of a language。What's common in many languages that identifiers have to start with an alphabettic character and might then contain。

Alpha all numeric characters。But in many languages。You can't have an identifier standing with a one。

And one X A B is not a valid。Number。Yeah， it just fails to be a token。Yeah。

 but I do want to emphasize this is all specific to a language。

 it's when we you know when you're implementing a language you wouldn't be needing to figure out what are the token types。

 what is an appropriate Lexa to produce those tokens appropriately。

So this is a hypothetical thing that I'm very hand w on。

 but we're going to dig into details for how to actually specify this。嗯。Okay。For practical purposes。

 you want your Lexa to do more than simply say I got an error。

 you would typically want you know if you wrote a program and you passed through the compile and it found something wrong with it。

You actually want some more useful information than simply。

 I don't know what to do with this file you gave me。

So typically it'll be doing things like reporting which line the input occurred on that。

That failed to be converted into a token。And so what that means is the Lea is typically going to be keeping track of this information。

 counting the number of new lanes， counting the number of characters within the lane that have been processed or can provide accurate information。

U。呃。Here is a variant of the program。The programr made a typo。And wrote T H N。

So what do you think would happen here？Is the Lea going to say？This makes no sense。

Or is it going to succeed？Because we know that this is not a good program， right？诶。

I guess it depends again on your definition of what idents community。

I feel like most like why fight with this。And then you're compiled her like parcs。Some troubles。Yeah。

 so most likely in my completely hypothetical hand wavy toy language， Yeah， T HN is a valid token。

 right， It would be an identifier。And as a result， would' actually electricalxical analysis would succeed。

 it would return。A sequence of tokens。So it's not an error in terms of lexical analysis。

But it's not a valid program。So the issue would actually come in the next stage of the pipeline。

 the synctic syntax analysis that we would fail to turn this into。

 this would fail to be in a statement or any other kind of valid statement within the language。

 but the Leing works out fine。O。Questions at the moment。Yeah。

 wasn currently we're not thinking about， let's say， the then has to go with an if or like。

Can't have to ident your own。 I don't know。 We're just like directly translating from text to。 Yeah。

 right， So at the moment， we're doing， you're right， we're doing something really simple。

 really straightforward， at least conceptually straightforward。

 just taking the sequence of characters and chunking it。😊，Into tokens。The next stage of analysis。

Of pasing， which we'll look at next class。Actually。

 for a few lectures is how you take the sequence of tokens and then figure out is it a valid program？

At least a syntactically valid program。 So， yes， there would want to do things like， well。

 if I have an if。There should maybe be a matching of then which comes after an expression。That is。

 I want to see an F followed by an expression followed by the keyword then followed by。

 and so on that's all part of the syntax analysis。But right now we're just wanting to take a sequence of characters to into the sequence of tokens。

Okay。So。We think about lexing as a black box。Hopefully the idea is clear that we take in a string。

Sequence of characters。And we're kind of asking for reach。

As we go through the sequence of characters asking。

 is it what kind of token is it and identify a number real spitting out the appropriate token？Let's。

Start with something even simpler， let's just think about。Trying to figure out if we have a number。

Okay， so that as we're taking in some sequence of characters， is it a number or not？In many ways。

 what's going on is that this is boiling down to a set membership question。When I talk about。

All the possible numbers we have。We intuitively know what this is， right？0，1，2，3，974， or 1086。

 whatever it is， right。 We know the sequence of characters that represent numbers。 We can definitely。

 we'll see soon figure out how to specify it。But the real。Thing that we're doing in the lexing。

Is given a sequence of characters deciding if it belongs to a particular set。Of course。

 the set of possible numbers is infinite。So how do we end up implementing this， right do we end up？

Deciding if a string belongs to a given set。We're going to do what we always do in computer science。

 mathematics to represent an infinite set。 We want some finite representation of it。

So the finite representation that we're going to be using is known as regular expressions。

And we're going to dig more into regular expressions。

 But one of the cool things about regular expressions is that we actually have。😊，啊。

An efficient way of determining whether a string belongs to the set represented by a regular expression。

嗯。Through a technique called or through a mechanism called deterministic finite state。我tmata。

Who has encountered regular expressions。Okay， in what context in a class and the programming you've encountered。

1，21， yeah，121，1，21。In 121， did you also covered？What timemato tell。Dear face， any face。Okay。

 who has not taken 121？A number of people。 And it's not a prere for the class。 So。

 so I don't have any expectation that you're going to know this。For those who have taken 121。

 some of what you're about to see is likely to be more refresher For those who haven't taken 121。

 this is one of the places where I。One of the aspects of programming languages that I really enjoy。

 this place where there's some really elegant theory。That meets。Practical engineering purposes。

So I don't know in 121， if you thought about regular suppressions， finite automata。

 when is that going to be useful to me？I think in programming languages and compilers and type systems。

 many aspects of the design and implementation of programming languages。

 we get this opportunity to take。This beautiful theory and actually use it to build real practical。

 pragmatic tools and systems。Okay， so let's taken， please don't be shy about asking questions。

 I think there's a lot of people in this room and also the students who are watching this video。

That haven't encountered regular expressions before， let alone finite automata。

 So if anything is' unclear， please chime in with a question。Okay。So。A regular expression。Represents。

A set of strings。this is the key idea。呃。Here are some examples。

 We will go into the details of the definition of a regular expression and how to think of it。嗯。

This regular expression has is over strings of0 and 1， So binary numbers，0 and 1。嗯。

The parentheses are part of the。The parentheses， the bar。

 and the star are all part of a fuel the meta syntax of a regular expression。

They're not talking about the characters would' see in a string。

 they're talking about what the regular expression is。This regular expression means。

I have zero or more occurrences。 That's what the star means， zero or more occurrences of。

Either a0 or a  one。 That's what the bar means。alternation， disjunction or either a zero or a one。

Followed by。 So there's kind of an implicit concatednation here after the after this star regular expression。

 followed by the character 0。So how would you succinctly describe this set of strings？In Englishlish。

William binary strings that end in zero， binary strings that end in zero， great。嗯。

Which are the ones that are multiples of two？呃。Here's another example。

 this is over the characters A and B。So to go through this regular expression and explain it。

 it starts with zero or more Bs。Again， that's the star。Followed by。Z or more occurrences of。

 is this outer star。An A followed by a B， followed by zero or more Bs。

So the star here is referring just to the B。0 or more base。The end of the string。Is either。

The character A。Or。This is a special character， Epsilon representing the empty string。

So it's kind of like a or nothing。呃。Any don't want to venture a succinct description or the strings of A's and B's。

 Is that a question Max well， Lord， do you have a description， that As can be next to each other。

 Great， Yes， this is a string。😊，This is the string of all possible combinations of A's and B's。

 except。呃。Those where that has consecutive As， right。嗯。Any occurrence of a。

Has at least1 B before the next day。last example。So。I'm not going to describe it。

 I believe I've given enough。Examples that you can hopefully generalize and try and figure out the set of strings represented by this。

 but who can come up with a succinct English？Description of it。W， has too days in the room。Right。

 so again， it's strings consisting only of A's and Bs。

But this string is strings of A's and B's that has at least two consecutive A's。

So what we're seeing here is zero or more occurrences of either an A or a B。

So an arbitrary string over A's and B's， followed by AA is is the consecutive A's followed by zero or more occurrences of an A or a B。

 so's an arbitrary string over A's and B's。Great。Okay。

 so having given you some examples and'll talk through this。

 let's actually see the syntax of regular expressions， the grammar for them。嗯。

We have the empty sit symbol， which represents。The empty set of strings， it matches no strengths。

We have epsilon， which matches the empty string。It's important to realize that these are different things。

The empty set of strings， no strings at all。Versus the singleton set containing the empty string。

We can have literals drawn from some alphabet of characters。 So A B 0，1， like we saw。

To the plus symbol and so on。Given two regular expressions。We can concatenate them together。Okay。

 so R1 followed by R2。Is the concatenation operation。 We don't have an explicit operator for it。

 It's kind of implicit。 putting these regular expressions next to each other。嗯。Onation。

R1 or R2 represents。Either a string in the set represented by r1 or a string in the set represented by R2。

The cleaningy star operator intuitively is if you have a regular expression R。

 the star ats zero or more occurrences of R。Okay， so this is the grammar of regular expressions。

 The basic grammar of it。 Typically， there'll be some additional operators for convenience。

 but really they're just。Convenient shorthand for combinations of these basic operators。

As I was talking through it， I was alluding to this idea that a regular expression we can think of as representing a set of strings。

We can actually make that quite explicit。And precise。

 we can think about the interpretation of a regular expression as a set of strengths。So in that case。

 the empty set， the interpretation is the empty set。Epsilon， the interpretation is。

A set containing one element， the empty string。For literal。

It's a set containing the single element of that literal。

And then the other operators are interesting， more interesting。For concatednation。

 R1 cancatedated with R2。Well， this represents the set of strings。They consist of。A string alpha。

And the set to by r1。Concatedninated with a string beta chosen from the set。Denoted by R2。

People comfortable with this notation。Its clear the idea of how we're taking。

 we're in the process of defining the meaning of a regular expression as a set of strings。

When we're showing how r1 cancatenate with R2， the meaning of this can be expressed in terms of the meaning of R1 and the meaning of R2。

How yeah。サービス。Wy， what's right， the end？Oh， I'm just happening to use this as the concatednation symbol。

 You， I'm just being explicit。 This is the concatednation of two strings。

 one from the set to node by R 1， the other from the set to node by R2。Alnation， R1 bar R 2。

It's the set of strings S， where S is either from R1 or from R2。 equivalently the union of the sets。

Our one。And are too。Cliny star operator， R star。呃。We can take of it in a few ways。

We can think of it as being equivalent to the regular expression， either the empty string。Or。

A concatenated with our star。That is。The empty string， or it's one or more copies of R。

One of the most strings drawn from the set doneed by R in set notation。Putting it here explicitly。

 either it the empty string or it's the concatenation of alpha and beta where alpha is in the set node by R and beta is in the set noted by R star。

Anyone see any issues with this definition？William right。Not really a definition， right。

 It's kind of defining the set R star in terms of the set R star。 Turn out what it really is is。

Like a constraint， like an equation。And the set of strings that satisfy this。

 the smallest possible set of strings that satisfy this equation is the denotation of R star。

But from a practical and pragmatic point of view， you can think about it as simply zero or more occurrences of the string R。

Okay， any questions at the moment about。About the denotation of regular expressions。Okay。

I mentioned that。呃。For practical purposes， we do actually have。

Extended notation for regular expressions。 So， for example， what's common is to see。

Notation like this， square brackets indicating a character class， set of characters where。

 for example， 0-9 means all of the characters from 0 through9 inclusive，01，2，3，45，6，7，89。嗯。

We might have。Question mark operator。Our question mark means that optionally R。

The denotation of our question mark is either the empty string or a string from R。

OurPlus is shorthand for one or more occurrences of R。So it's equivalent to our。

Concatenated with our star。Okay。So。The key idea is that we're going to be using regular expressions to specify the token types。

嗯。So， for example， the regular expression IF。I's going to correspond to that token we have the keyword F。

so this is simply。The condation of of two literals， I and F。

 their regular expression denotes a singleton set， the string F。

And that's the appropriate token type。For identifiers， as is common in many languages。

 as I mentioned， it's a string that starts with a alphabetta character and then is then followed by zero more alphanumeric characters。

So the token type there would be8。One or more。Digits。Would be suitable for a number。呃。

Real numbers are actually。Often surprisingly difficult to lickx。嗯。

Let me give you the regular expression for it， and I'll let somebody。Explain it to me。

Whats this succinct explanation of this regular expression for real numbers？不 name。

Like it has a period。Exactly one period。エジ。Close， but there are strings that。

 but the string consisting of a single period is not a real number wouldn't be in there。 Max well。

 a and then digs side， but there has to be at least one dig。There has to be at least one digit。

 and there has to be a period， but it could be。One or more digits followed by a period。

 followed by zero or more digits， or it could be。Zero or more digits followed by a period。

 followed by one or more digits。嗯。Right。嗯。Okay， enough state about that。

Suppose we had this sequence of characters IFFY。What token do you think itll be？Or tokens。

 do you think it should be。What's your intuition as programmers telling you？嗯。不行。It's an identifier。

Yeah， if you wrote， this would be a totally reasonable identifier name you to writer in C in Python。

 Java， all of which have。If as a keyword。So typically， what's going on is。In general。

 we want the longest possible match。So that is， given the regular expressions that are identifying token types。

In general， you're going to want the longest to consume the longest possible of string of characters to give you a token。

嗯。Okay。Yeah， Nilas， why are we concerned with using the longest possible match。

 there would be multiple matches for the same。It's extreme。

 but if we feels like white spaces to teamwork them， whether won't that just simply be a match？Yeah。

 we can often use white space。To help us。诶。Divide up tokens， divideiv up， you know。

 the sequence of characters into token streams。 So one point to note is if I had IFFY。

What we're saying we wouldn't want to do is read I and then F and say， aha I've got a keyword。

 you know the if token type， there we go and then you know admit the token and then keep on going with the token string That is this should not be the keyword if followed by an identifier FY。

😊，Instead， we want to match up into one token， the longest possible identifier。

 White space is often used to explicitly separate tokens。

 but we also often have sequences of distinct tokens that are not separated by white space。

 So think here about 7 less than X， right。Might be good programming practice to insert white space around the operator。

But in most languages， you don't have to。 You could actually write it compactly。

 Then you've got a sequence of characters，7， less than x， none of which have white space。

 Yet somehow what your lecture is doing is deciding that that is three tokens。 a number。

Les than operator and an identifier。 Oh What about they can both match with it I。

So what I'm saying on。Oh， so。We'll get into it， but。Kind of what's going on here is that。

This regular expression is kind of a little generous， right？

This regular expression for identifiers includes strings that aren't actually valid identifiers。😊。

Right， includes the string IF， exactly like you said。

So it is going to turn out that we are going to want to be careful as we specify Alexa。That。

The string IF is interpreted as the keyword if token type of rather than as an identifier。Yeah。

So yeah， keep that in mind as we kind of dig into more of the details。Okay。So。Remember。

 what we want to be doing is breaking up the sequence of characters into tokens。

And so our lexical analysis needs to for a given sequence of characters， figure out what token it is。

 what the token type is。We kind of changed it from this question of like， is it a number？

To actually saying， does it belong to the set expressed by a particular regular expression？

What's known as matching， so does the string match the regular expression？

One or more occurrences of a character zero through nine， one or more digits。

One of the cool things about regular expressions is we actually have an effective way。

Of answering this question， does a string belong？To the set denoted by a regular expression。

The mechanism we're going to use for that is known as deterministic， finite states automata。DFA。

 so a DFA。Terministic Vanistide automaton。Can be used to decide whether an input matches a regular expression。

Again， I'm going to。Explain DFAs mainly by hand waving and examples。

 there is more detail in 121 and also in the textbook， the Appel textbook。

But let me give a very hand wy explanation of what goes on。 This is a finite state automaton。

 Every circle here refers to a state。There's only a finite number of them。Two， in this case。

 there are edges between the states， and they indicate what characters can be consumed to transition from one state to the next。

In a DFA， we always start off in a distinguished state， which I've conveniently labeled start here。

So the idea would be that as we're passings a string。As we're leing a string rudder。

We are always in some state， initially the start state， and we look at the next character。

Depending on what the next character is， it tells us which edge to follow from that state。

 So if we saw a digit， let's say four。We would transition from start to the state here。

If we then saw another digit， let's say a two。 we would transition on this edge。

Bringing us back to the state。诶。At that point， we're not。

If that was the end of our sequence of characters， let's say maybe because the next one was white space with the end of file。

We would be in the state here and the state is labeled as an accept state。That is。

 if we finish passing the sequence of characters when we're in the state， it is a valid number。

By contrast， if we finish the sequence of characters and we are not。In an accepting state。

Then we do not belong to the set expressed by the regular expression。Here's another example。

From the start to say we can consume an eye。We can consume an if。 and we're in an accept state。

 giving us the token type if for a keyword。Suppose that we had the characters's IDd。Instead， right？

So then we'd start in the start state， would' consume an eye。The next character would be a D。Now。

 there's actually no outgoing edge here in this automaton。Label D。

So we wouldn't be able to consume any more input。We would stop in this state。

 and this is not an accepting state。That is ID。The sequence of characters' ID would not allow us to produce the token type。

For the if keyword。呃。Here's a DFA for identifiers right from the start state。

 we consume one alphabetta character。Whereupon we can consume zero or more alphanumeric characters。

 a through z or 0 through9。Here's the DFA for real numbers。S that we had。

Either we start off with a digit。Followed by zero or more digits， followed by a period。

 followed by zero or more digits。Or we start off with a period。Followed by a digit。

 followed by zero or more digits。So each of these DFAs that I'm showing up there is for one of the regular expressions for a token type。

Right， the FK word identify real numbers。What we're actually going to do， though， is in Alexexa。

 we're actually going to combine。All of these deterministic finite autometerta into a single DFA。

So that as we consume a sequence of characters。It'll tell us what token we have。Right。

 so here we start off from the start state。 we can read a sequence of characters。

 and at the end of that sequence， it will tell us。Not only should we accept it as a token。

 but what the token type is。So let's take a moment to look at this， right， So we have here。

Parts of the DFA for a real number。Will we start off with a period？Interestingly。

 if we start off with a digit through 019。We could tag zero or more more digits。

 And if that's the end of the input， that's okay。 We accept it as a numb token。

But if we see a period。We move into the state where we could take zero or more digits and if that's what we end up with。

 we'll accept it as a real token。Here we see。The top of this graph of this DFA rather。

We see this issue we had with the keyword if versus an identifier。And you'll note that this。

The DFA is deterministic and what that means is from any state。

There's at most one outgoing edge for any given character。So what that means is from the start state。

 if we see an I， we have to transition to this state。We can't transition along this edge。

 which only accepts the characters A through H and J through Z， so every letter accept an I。

You see that if we have a I followed by an F and nothing else we'll accept it as as the token F。

But if we have more。Characters， alpha numeric characters will end up being in a state where we can accept an identifier。

Okay， so this combined DA is actually。Showing us。Exactly how to that if we see IF。

 it's going to be the keyword if， not an identifier， but other strings would be identifiers。

So in the example we had earlier with it was like one X。Just with the if statement。

 we had an identified story with one。Some word。According to this。

 it would get power as nu1 and then ID， FXA， something。Rather than throwing it there。Right。

So if we had one Xi。So from the start state， we wouldd see a one。There's only a single edge。

That accepts a one。 That's because it's a deterministic。 So it would be in the state here。

 from the state， we can either take a digit or a period。

Which means that the next character of an X would not be accepted。嗯。诶。You're right。

 there's a subtlety here that we would actually want to reject 1x0a。

But we would want to allow something like one less than x， right。

One of the things I'm not quite showing you here is。啊。

How many characters do we consider and do we consider stopping something in the middle？You know。

Without white space， how do we deal with that， I'm actually not going to dig into that directly。呃。

A lot of the examples I'm going to be showing you， we're just going to be requiring weight space to separate tokens。

 But you're right。 You do actually want to allow some。

Tokens to appear next to each other and not others。8。So we see it just a single eye。

It should not also be accepted。That is a good point。Yes， if we see a single eye。

It should be an identifier。有。Great。Okay。Take a step back from this example。The key idea is that。

Essentially。Alexa is really one of these deterministic finance data automata right if we can have some implementation。

Of this DFA， we've essentially got Alexa， right， a way of converting the characters。

 a stream of characters into a stream of tokens is， you know， some subtleties involved。

Tracking the line numbers， reporting useful error messages， figuring out how to deal with non tokens。

 such as white space in characters， a few more things。 But this is the key idea。Right。Now。

 it turns out that。We can。Represent one of these DFAs pretty efficiently。

 typically as a table that kind of says the records the transition function as an array indexed by the state。

 what state am I currently in。What's the next character I see and then that tells you what state you should move into。

All right。So。We've got this idea of regular expressions。To express sets of strings。

We've got this idea of DFAs that hand wave， hand wave， hand wave allows us to implement Lexes。

Pretty easily。So the question is， how do we get from a regular expression to a DFA？

This can actually be done mechanically and pretty efficiently。

The idea is that we're going to take a regular expression。

Convert it to something that's called a non deterministic finite state automaton。That is。

 it's going to be look very similar to the fine automato we've seen previously。

 except it's non deterministic in the sense that on our outgoing edges。

 you might have more than one outgoing edge with the same character。

And we might also have some outgoing edges labeled by epsilon。

Meaning without consuming any additional characters， they could move from one state to another。诶。

We'll talk a little more about NFAs。But once we have an NFA， a non deterministic finite automaton。

 we want to convert it into a deterministic finite automaton。And once we have that DFA。

We essentially have Alexexa。Any questions about this process？

Ca I'm just about to jump to the idea of。Converting a regular expression into an NfaA。Okay。

So let's go through and think about the different regular expressions we have。First of all。

 for the empty string， Epsilon。嗯。We can turn it into an NFA with a single start state。

A transition that accepts the empty string， that is it doesn't consume any characters and an accept state。

Similarly， for the for a given literal， say a start state。

 transition on on that literal to an accept state。What's more interesting is these operators that combine regular expressions together。

Becauseuse what we're going to be able to do is。Think about combining the NFs for the regular expressions。

 So， for example， for concatednation， R1 followed by R2。 The key idea is that there is an NFA。

That corresponds to the regular re R1。There's an n that corresponds to the regular expression r2。

Based on the way we're going to construct them， each of these interfaces has a distinguished start state。

And a distinguished， accept state。So what we're going to do is take。The NFA for R1。

Take the NfaA for R2。And add an edge from the accept state of R1。To the start state of R2。

Laborable by epsilon， the empty string。So the idea here is that if we start off。

AtThe start side of R1。Go through this NFA， accept a string that's recognize a string that's accepted by R1。

 then we could follow this epsilon transition。And consumer string that's recognized by R2。

 And get to this。This success state。 and that would accept all and only the strings。

Represented by the set， R1 concateated with R2。Any questions about that construction？

So dear of taking the interfaces from I1 and02 and putting them together。Ipe。

And if they're going to have a single。Yes， we are going to make things so that every NA has a single accept state。

 making it very easy for us to compose them together。Yeah。Soれ questionオ。Okay， so for alternation。

 we can do something similar。 R1 or R2， we again take the interfacephase for R1。And for R2。

We introduce a new start state and a new accept state， from the start state。

 we add epsilon transitions to the start of R1 and the start of R2。

 and we add epsilon transitions from the accept of R1 to our new accept state。

 from the accept of R2 to our new accept state。会题。Cley style。

 the idea is similar in the sense of we take the N for。The regular expression are。

We had a new start state and a new accept state， and we had epsilon transitions and the start。

To the start of our。From the accept state of R back to our start state and an epsilon transition from our start state to our accept state。

Okay， to take a look at this， but you should be able to convince yourself that this NFA is going to accept all and only zero or more occurrences of R。

Any questions about this construction。From regular expressions to NFAs。Yeah， Maxwell。Sure。

 let me go back a slide。嗯。This is a construction for alternation。 We have the NFA for R1。

 the NFA for R2。And from here our start state， we can transition either to accept an R1 or to accept an R2。

And then from the accept state of both， we have an epsilon transition to the accept state of this regular expression。

Okay。So we can construct the NFA of a regular expression pretty easily from the NAs of the sub expressionions。

嗯。A string is accepted by an NA if there is a sequence of states。

Where we transition between the states， either epsilon transitions or consuming the next character and the input that takes us to an accepting state。

So the problem is that。There exists a sequence of states。

 the nondeminism of choosing which edge you should transition on when you have a choice。

That's what makes it non deterministic。 and that's what makes it。

Difficult or inefficient to use an NFA to match your regular expression。Thing as， though。

 we can actually convert an NFA to a DFA。In a straightforward way。诶。

I'm going to sketch out very quickly the algorithm for converting it。Basically， the idea is that。

Given an NFA， we're going to construct a DFA where each state in the DFA。

Represents a set of states of the NA。To do this， through example， here we have an NFA that accepts。B。

 followed by。Either C or D。It's non deterministic because after consuming a bee。

We somehow need to choose which of these epsilon transitions we're going to take before we consume the next character。

We're going to convert this into a DFA。嗯。By。Gradually constructing a DFA。

 We're going to start with the start state。Of the DFA。And that's going to correspond to。

The start state of the NFA， plus everything I can reach with an epsilon transition。

Which is to be honest。Just the start state， state number one。So in our DFA。

The start state represents。Singleton set of state one from the NFA。Looking at state 1。

 we see there's an outgoing edge for a B， And that's the only outgoing edge。

 So we're going to add an outgoing edge in our DFA。From B。And if we followed that。

 B E we'd be in state 2。In RA。But we could also from state 2。

 without consuming any additional characters， transition to either state 3 or state 5 on those epsilon edges。

So in our DFA。The state we transition to is going to represent the set 2，3，5。

That is from the state to every week we could get to by following only epsilon transitions。Now。

 from these states，2，3，5， let's look for the outgoing edges。We see that from state three。

We have an outgoing edge of a sea。From state 5， we have an outgoing edge of a D。

So we're going to add outgoing edges for C And D in our from our new NFA state。So let's start with C。

Okay， we are now going edge from C。The set of states that this DFA state corresponds to is。Four。

 where we got two from problem a C edge， plus anywhere we could get to from an epsilon edge。seven。

So this represents the set 4，7。And this is an accept state because one of those states。

7 is an accept state。In a similar way， we are going add a D edge from this 2，3，5 state。And again。

 we're going to take the epsilon closure of the states。 So we get to state 6。

 And by following epsilon edges， we could get to state 7。 So the set here is the set 6，7。

It represents that set of states。 And because7 is an accept state。Se 67 is an accept state。So yeah。

 So first question is， the only nondeminism we have at the top will always only be great。

Like we won't ever have El scenario case， two characters coming out of the same note。呃。Yeah。

 as long as you're careful with the。You know， I glossed over the bit about how we actually combine。

Keyword and identifiers， but assuming you combine those in an appropriate way so that you don't have non determinism on those character edges。

诶。Then， yeah， it'll only be on Epsilon edges。 same idea holds true， though。

 It's like when you can consume a character， if you could go to multiple states。

 you add both of those states into。The set of states you represent plus anywhere you could get from epsilon transitions on them。

In a sense， on the bottom， we've taste worked on if we're in node3 right we can take a C。

 if we're in node5， we can take a D That's right so technical if we're in node2 in that set。

 we can take an epsilon to get to set three5 but we're basically just packedd that time Yeah in looking at health in the textbook for the details of the algorithm。

 but essentially。We。You're kind of constructing this the FAA gradually。

 and it turns out that we don't need a state representing 35。

There's no time that we could be in either state or state in either state three or state five without also possibly being in state two。

Okay。This is a deterministic finite aid automaton that is from any state。

 there's only one outgoing edge we could follow and there are no epsilon transitions。And indeed。

 the construction I hand waved on will always produce deterministic。U。Find out automa time。All right。

So lexical analysis， we're going to have a whole bunch of regular expressions to satisfy to specify strings for each token type。

 We're going to compose them together。Essentially by taking the alternation of them。

 although we do need some care with。诶。For identifiers to make sure that we。

 you AF is accepted only as a keyword and not as an identifier。嗯。From that NFA。

 we can construct a DFA from that DFA， you can imagine having an efficient compact representation of the transition table。

 which will essentially。Give us a way of executing that F state of tomaton。

 and then in general we want to take the longest possible match。I love string。

 and so that's way we can produce the appropriate token token type for sequence of characters。Okay。

Having said all that。You'll probably never actually do that by hand。

 what you'll instead do is use Alexa generator。🤢，That is。

 you're going to have a tool that lets you follow that first step。

 specifying the regular expressions for the token types。

But then you'll throw them into Alexa generator， which will take care of the remaining steps for you。

 combining them together， coming up with the DFA， coming up with a program that implements longest match using that DFA。

There are many Lea generators in this class you'll be using Lea generator for ML。O Camel Lex。呃。

The suffix for an Ocal Lex file。Is MLL。And then you simply pass it into the OcaMlX program。

 and it's going to produce an ML file for you。嗯。Let me very quickly give you the structure of an Ocaml Le file and we'll see an example quickly。

嗯。An nocoml X file takes a header。In curly braces and a trailer， in curly braces。

 these are just arbitrary ocal code。 So you can define useful functions here。

 They're just going to be copied to the output file verbatim。The main part of an Ocal X file though。

 is you're able to specify useful identifiers for regular expressions。

 so if you have regular expressions that you end up wanting to reuse in your various rules。

 you can come up with nice succinct names for them。And then we end up with。

Kd of these mutually recursive lexing rules。 So rule is a key word。Followed by。A name。

 possibly with arguments。Followed by PAs and then the sultanation of regular expressions。

Action in here is Ocal code。And。诶。Essentially， these rules， these entry points。

 get converted into functions。The take arguments。And the result of the function is going to be the result of these action expressions。

 So within a single entry point， the type of the yocaml expression in action get to be the same because that's going to be the return type of the function。

Each of these functions can take， you can define them to take various arguments。And then。

 the Ocal Lexa will。Also add a Lexbuff argument， which is essentially a record that contains information about where you are in the Lexing how many new lane characters you've seen。

 how many characters from the last new lane character you've you've consumed and so on。

Essential enough information to give meaningful error messages when something goes wrong。

And also enough information to track where tokens came from in the source file that'll be helpful in parsing if you get a PA error or later。

 you want to know where in the file things went wrong and so that information is also recorded by the Lea。

Let's take a look at an example。啊。So this is， you can download this file and take a look。An example。

 Ocaml D file， Note suffix MLL。Here is the header section， so arbitrary ocal code。

 what we're doing here while defining Alex error exception。

Defining the token types that we're going to have just a simple account algebraic data type。

 int is going to carry with it， the integer value that we passed for the integer。

're going to have a string， token type that passes the string and we're going to have end of file。嗯。

We are going to explicitly keep track of line numbers。 So here's a handy little。

Function that increments the line number。 Lebuff is a record。 And all we do is essentially。

Update the record with the new line number。And。This is just the beginning of line position。

 which is the number of。But不不。The number of characters。

 I think since the beginning of the file is what it's meant to be。

We may not be implementing that correctly。呃。Just some handy things defining。

Carage return and new line regular expressions。An end of line is either a carriage return followed by a new line or a new line by itself or a carriage return by itself。

White space。We're finding is tab spaces。呃，我。The control L。L， yes， the control L character， digit。

Z through nine。That is the。うふ。End of the definition section。 Now we have rules。

 We are defining two mutually recursive rules， Lexa and string。This is pretty common， actually。

 that you kind of have different modes that your Alexa can be in。

This first one is when we're just passing end of line， white space。numbersumbers。

In the file and so on。 So what you see here is if we。Have zero one or more digits。

 What we're going to do is return the token type int。

This is saying we're going to take that sequence of characters， that string call it in。

And so given that string in， we're going to convert it to an int using Ocals into string。

Return that as the argument event。If we see one or more white space characters。

 we're simply going to recurse and return whatever the next invocation of Lea calls。诶。

If we see an open quote mark， what we realize that this is the beginning of a string。

What we're actually going to do is change our leing mode。We're actually going to start passing。

Lxing a string。So we're going to return the token type string with whatever string this string rule。

Ends up pausing。The reason why we do that is strings have various escaped characters right we can't simply say read all the characters until you see a quote because that string literal might have some escaped quotes in there。

 so when we're leing that string literal， we need to be a little careful with escaped characters。

Escapeed。呃。Yeah。Escapeed quotes， escaped new lane and so on。 But if we see a close quote。

 what we end up doing is returning the string literal that we've passed so far。And then of course。

 we have code for raising lexing errors in。if we're not able to pass the next token。

Our trailer section here， we just have a little bit of code， which says。

We're going to invoke our Lea。And we're going to pass in this string。不得得。Oh yeah。

 And the way we use this Lea is to just repeatedly call it。

To get the next token until we read the end of file。

So here we see what we're doing is getting the next token from our Lea。

 repeating that to our list of tokens， if the token was into fail， then we're done。

 otherwise we recurse。To get the next token。So诶。It's Ocal Lex。sorry。on file。Let's run O Caml X。

 the output here is just telling us the result of the DFA that was produced， it has 14 states。

 267 transitions and the table that represents the transition matrix is expressible in a kilobyte or 1000 bytes。

Here is the ML file that's produced。嗯。Allright， so here's the code from the header copied verbatim。

 Here is the representation of the table。 not intended to be human readable。嗯。

And then there's some library code。The Ocaml X Lexa that essentially uses this transition tables appropriately and based on the state that we're in。

We'll end up executing some of the action code， for example。All right。嗯。So using that。

 it's going to execute the code。At the bottom， which was。Just doing this example， Lexing。嗯。

And you can see that it produced。Certainergeon type int with value 3，4，2。

The token type string with Hello World。And the end of file， end of feed token。

Any questions about Ocaml X。Come homework4。 you'll be getting tonight。

 You can take a look at the Ocal X files that are in homework 3。 We are using Ocal X to be leing the。

LOVM light files， so you can take a look at what we're doing there。

 but you'll be working with them directly on homework 4。I did want to show you a handwritten Leer。

 We might do that at the beginning of next class more just to see some of the design ideas in there because it's going to be end up being relevant for passingsing。

A style of pa later on。We're out of time today。呃。Enjoy working on homework three don't forget to start when you have a moment。

And I'll catch you all on Wednesday。信方。い好。代。Yeah， sort of leaving your thank you for questioning and I'm bit kind understanding about the being called should say。

YeahThe current invention is。あい。For say if you need to use them。then you have to。



![](img/b0ec6a7ec3a17b04355e3be2897e9a7a_1.png)

![](img/b0ec6a7ec3a17b04355e3be2897e9a7a_2.png)