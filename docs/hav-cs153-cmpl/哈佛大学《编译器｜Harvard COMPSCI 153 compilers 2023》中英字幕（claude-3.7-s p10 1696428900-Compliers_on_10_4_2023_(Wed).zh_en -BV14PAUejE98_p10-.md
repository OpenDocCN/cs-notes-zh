# 哈佛大学《编译器｜Harvard COMPSCI 153 compilers 2023》中英字幕（claude-3.7-s p10 1696428900-Compliers_on_10_4_2023_(Wed).zh_en -BV14PAUejE98_p10-

When you've gotten the right， you need to write the test cases and figure it out yourself。

So hopefully as all goes well， you there won't actually be any benefit to you of submitting your homework on grade scope until you've actually think you've finished it。

So hopefully Grcope will address this within the next。week or two until before the homework's ready。

Any questions on the admin side of things。Okay， so today we're gonna be continuing this section of the course looking at lexing and passingsing。

 I do w to say that。In pretty much unrelated news， this morning。

 I went on a field trip with my three year olds daycare class。 We went Apple picking。

 This involved driving， sitting on a school bus driving for an hour out to Honeypot Hill Orchard。

 which some of you may have been locally or in housetris And because we was so far out。

 I was an entirely short get back in time。 So Camm over here very kindly volunteered to step in and teach us lecture。

 So we actually got it all up to speed on the slides and everything for nothing。 But thank you。

 Camm really pretty。😊，U。And apologies that I didn't bring enough apples for everybody。

If attendance have been what it was on Monday， they would have been。

So thank you all for coming and meaning that I don't have enough apples。Anyway。

What we're going to do today is just very quickly wrap up something we missed at the end of last class。

 which is a handwritten Lea， and then we'll jump into the idea of pasing。

 the syntax analysis once we've got the tokens from the PAser， how to put that into a structure。

 figure out the structure of the program。Apparently， Massachusetts was testing their emergency。

Response signaling。Good to know it works。Yeah。What happened to mind？Okay。

 we'll seeing when Min stops to us。Okay。So let's jump and look at。This hand and Lexus。 So the idea。

 of course， is。Of Alexa is taking sequences of characters。The second wife。行。Wow， okay。

 so the idea of Leing is， of course， to take a sequence of characters。

 turn that into a sequence of tokens。 The most common way that people write Lexas is using a Lea generator。

 And we saw an example of Ocal's M L X Ocaml X tool。 But I did want to dig into writing aa by hand。

 And this is in part because the ideas we're going to see here。

 we're actually going generalize slightly and。😊，Consider 10 and Per later on in this lecture。

So let's just go through this file。 This is actually available on canvas。From last lecture。

A couple of utility functions to give a string， turn it into a list of characters， explode。

 and vice versa implode， give a list of characters， turn it into a string。Okay。

We're here to define a。Signature for a module that essentially describes what you can do with a regular expression。

 Sorry， it's going to set up lecture， which will then use a funter to add some additional features and then implement it。

In a straightforward way。So the idea is we have an abstract type here， tick alpha regular expression。

 The idea is that it's gonna， we're gonna to have a function。We down here。

 Lex that takes a tick alpha for regular expression and a string。

And using that regular expression returns a list of alpha。系。

We're going have constructors for regular expressions。 So given a char， we can get a char rex。

 So this would be。Essentially， a literal regular expression， a way to construct a literal。

 regular expression。嗯。It would match a string consisting just of their character and return a list containing only that character。

Epsilon matches the empty string。Void never matches anything at all， so it never returns anything。

We have concatednation。嗯。And this is going to be。Sorry， this is alternation。R 1 plus r2。

If r1 matches S and returns V， then it returns v， otherwise if R2 matches S， it returns V。

Concatednation with a doll sign， returning a pair。So if a string S can be broken up into two substrings。

 S1 and S2。I our want also an R two will match。Those substratestrs。

St operator returns zero or more occurrences of the regular expression it's passed in。

This function here， percent gives us way of taking an alpha regular expression。

So that is a regular expression of a consumer string， returner alpha。

And a function from alpha to beta。And this is going to give us a beta regular expression。

 That is a regular expression that's going to consume a string return elements of type beta。 Okay。

 so just like a map， but for regular expressions。Given an implementation of this of this Lexing interface。

 we can come up with extended。Regular expressions in a straightforward way。 So a plus operator。

 one or more occurrences of R， we can define simply in terms of。诶。Of R and star R。嗯。

Just ignoring a value， so if we take an alpha rig X。And a constant of type beta。

 and we return a beta ret。This will turn out to be useful for things like keywords where you want to consume a string and then just return the token for that keyword。

 regardless of the string that was passedd in。Optional match。

Lifting alternation to being over a list of possibilities instead of just a pair。

 same with concatednation。And then some handy。Regular expressions， matching a digit。

 matching a natural number， matching an integer， which is a natural number or a minus sign followed by a natural number。

And then actually providing this function。That will。

Make sure that we're returning the correct integer。Maching low case letters， uppercase letters。

 matching an identifier， which is a low case letter followed by。0 or more digits， low case letters。

 upcase letters or underscores。Finally， our token types here。And I' token regular expression。

Regular expressions， which are going to be things like pars and integer and then。诶。

So this will return。Anddent， take thatdentt and return a token containing thatdentt。Identifiers。呃。

Sorry， identifier is going to pause on a string beginning with。A lower case letter followed by。

Alpha numer underscore characters。 It's going to look it up in a list of keywords。 If it's a keyword。

 it's going to return the token for the keyword。Otherwise， it's going to return the identifier token。

And then for operators passing in these characters， returning these tokens。诶。

Token is simply going to be。An alternation of these token rigs。so any one of these？

White space defined based on one or more。 So There's the plus。

 one or more of these white space characters。We're going to pause it and we're simply going to return unit。

 we don't care what the white space is。We're just going to return unit。So then we can actually have。

A token list， regular expression。Call doc。 So what this is going to do is scan a document。

 a sequence of characters， and return。A list of tokens。Right so what it does is。Pause。

Optional white space， followed by。One or more tokens。Sorry。

 zero or more token separated by white space。Followed at the end by an optional token。

And essentially， it's。Passing the function to this。Sorry， passing that。The list of tokens to here。

And wherere simply。Folding up。The list of tokens that we're getting。 So casting out。

 ignoring the white space ones and so on。Okay， here's an implementation of that Lea。

So we're going to implement our abstract type Al rex as being a function from a list of characters to a list of an alpha and a list of characters。

Basic idea is that given a list of characters， the Al rig X is going to consume some of them。

And return an alpha。 And then we're going to have the remaining characters that are left。

Okay so the regular expressions consuming salmon， we're going to have the rest of the string。

To be used later。We're actually going to return a list of these things。

 That is we're going to return a list of all the possible ways。

That that regular expression could consume characters。Okay。

 so this is essentially going to give us a list of possible ways of leing a stream。

And here we have the constructors。 So given a character。

 a child re X is going to take in a list of characters。

 But the first character is the we're trying to match。Then we will actually match it。嗯。

Otherwise we'll fail， which is the empty list， right we didn't match anything。Epsilon， void。

straightforwardight。Alnation， we actually just try。Lexing with regular special R1。

We also tryexine with regular expression R2。These are going to give us back lists of the possible ways that those regular expressions could consume。

Initial parts of the string。 We just cancatenate them together。 Right。

 These are all the possibilities that R1 or R2 could consume some of the string。

The other constructors are also pretty straightforward。嗯。And finally， we have Lex。

 which takes in a regular expression a string and returns a list of。嗯。The pauses。

 the way it does that is。嗯。Essentially。Getting the list of all possible ways of lexing the stream of characters。

And returning one that actually successfully consumes the entire string。

That is the rest of the string to consume is empty。In the interest of time。

 I'm not actually going to run this， but take a look at the code。

 try running it Lex with that dock regular expression we saw of you know token separated by white space and you'll be able to run this and see that it correctly lexes this in this simple example。

 we are actually requiring white space between each token。So it'll pars this string。

 but if for example， you remove the weight space around the plus operator。

The addition operator would fail。Okay。Questions about this。

 the design of this handwritten and Lexa and this way that we're kind of explicitly encoding regular expressions。

They consume strings。And return the ways that they could possibly consume it。

MtWhat do you ways in which they can be concernedd？We just do it all at once。

Let's take a look at the star operator。We're going to take a string。We're going to find。

We're going to allow us to pause no copies of that of R。

Mean we're just going to return the empty string。We're also going to trypasing R followed by star R。

 so recursively trypasing it。And then just cons the results。Together。So the idea is that。If I had。

Our star， I'm actually going to return all the possibilities of consuming zero copies of it。

One copy of it， two of two copies of it， three copies of it， and so on。诶。

So let's suppose the regular expression I was trying to consume was just， you know， the character A。

And I've got。A string containing four as。 I'm actually going to hand back five possibilities。

 consuming 0，1，2，3 or four copies of that a。And this is going to let us essentially try all the possible ways。

Of their regular expression， matching the string。Because it might be included in a longer regular expression。

Let's say a star followed by a。And so in order， the A star would need to match exactly three of the A's in order for that entire regular expression to match the whole string。

But when we're passing a star， we don't know how many we need to consume。In order for。

The latter part of the regular expression successfully pass。Essentially。

 what's going on is we have an NFA， a non deterterministic finite autometerta。

 And this list is representing all of the possibilities。

 We're exploring all of the ways that this NFA could consume。A string， it's not very efficient。

It's exhaustively trying。I was just say this might introduce other problems。

 but would it make sense to like try parsing it backwards for that like make it any more efficient？

Depending on the regular expression， it might， but in general， no。系。In general。

 going backwards won't make anything easier。Okay。So we have 100 and Leer a way of taking the stream of characters。

 turning into a stream of tokens。Push that on stack。 Hol onto it for about 20 minutes。

 And we're going come back to this in a moment。Okay。Fantastic， so we。Revisited some of this process。

 Lxical analysis， turning the stream of characters into tokens。 Today， we're gonna be looking at。

Syntax analysis， taking this stream of tokens， turning it into an abstract syntax tree。

 So it's structured representation of the program。We're actually going to be spending about three lectures on it。

 looking at various ways of passinging。😊，嗯。Conceptualally， what's going on is really two things。

 We're trying to identify the sequences of tokens that are syntactically valid。 That is the just。

Fit the pattern of tokens that are allowed by the language。

But we're also trying to extract the meaning of。Of the program。嗯。So to make an analogy in English。

When we have a sequence of words。We can think about whether the words。Makes sense grammatically。

But there's also a meaning to the sentence， and we can ask questions about the sentence。

OD caught the ball， right， what is the subject of the sentence？

That is what is the entity that is doing the verb Boing， what is the verb praise court。

 what is the object， the ball， so on and so forth。U。When we're looking at the meaning of a sentence。

 it may actually be ambiguous。 It may be grammatically correct。

 It may be a valid sentence in the language。But the meaning might be ambiguous。

 So one of my favorite examples is。那s quite yeah。Time flies， like an arrow。Fruit flies。

 like a banana。So of course， what's going on there is both of them are valid sentences， but。

Fs and like are being treated in very different ways in those sentences。Okay， as nouns。

Flays as a verb here， flies as a noun over here。RightSo in some ways。

 figuring out the meaning of the sentence is intimately connected with。How will why that sentence？

Is syntactically valid。Annaegously， two times3 plus4。Is this equal to two times 3，6 plus4？

Or is it equal to two times？3 plus 4。Both of them would perhaps be valid readings。

Valid sentences in the language of earth arithmetic expressions， they have very different meanings。

So it's worth all thinking about these things separately。

The idea that there's a set of valid sentences， and then there's meaning associated with sentences。

But it turns out that we typically are doing both of these things at the same time。

While we're passing， while we're trying to figure out if a sentence is synactfully valid。

 we're also figuring out what it means。 That is what the exact structure of that sentence is。Okay。

So a language is。Just a set of strings。Set of strings that are valid in that language。

 We need some way of specifying what that set is。The set is typically infinite。 So， of course。

 we need some finite way of describing the set。And we encountered this problem last lecture。

 right when we were doing lexing。How do we take this infinite set of。Of tokens， of words。

And figure out which tokens， what token type they have。So a natural question to ask is。

 can we use the same solution， Can we use regular expressions to express。

The set of strings in a given language。So we， of course， saw how we did that in MX。

 where we used regular expressions with names on them and that was able to so here， for example。

We could use regular expressions to define。The language of sums of natural numbers。Okay， so that is。

What more digits followed by a plus。Zero or more occurrences of that。Finally。With an natural number。

 that is one or more digits at the end。So this makes sense， right。

 if our language was simply sums of natural numbers， we'd be able to use a regular expression for it。

What would happen， though， if we wanted to add parentheses to this language。

ick to this language of sums of natural numbers。Okay， so let's have an attempt。

We're trying to use regular expressions here to define。Sums of natural numbers with parentheses。

 So digits is the same， one or more digits。Some we're gonna express that as an expression followed by a plus symbol。

 followed by an expression， an ex。Expression is going to be either a natural number。

 one or more digits， or。Open parenthesis， some close parenthesis。So this looks pretty good。

RightThis is kind of capturing an very very natural way。

What we would want this language of natural numbers with parent sorry sums over natural numbers with parentheses to look like。

Problem is。This is not actually a valid regular expression。

 And if we tried to come up with a finite automaton to recognize the language。

Would'd end up running its difficulties。So what's actually going on when we use ML LX to give a name to a regular expression。

All it's really doing is treating that name as an abbreviation for the regular expression。

So there will we define digits as being。呃。One or more digits。

All that's really happening is MLX is expanding that name with the regular expression。

So let's see what would happen。😡，嗯。In our， in our example， if we did that。

 if we replaced the definition。Of these regular expressions with。呃。

Replace the name of a regular expression with its definition。 Okay， so replacing。Some here。

We would end up with。At least in one of the cases。Some being an expression followed by a plus followed by an expression。

The problem here is that now。Expression is meant to be an abbreviation。Right， which means that if we。

Expand expression again。We're going to get。A biggerre expression。

 but it's still mentioning expression。So we'd keep on expanding it， expanding it。

 expanding it would never actually finish getting down to。Our basic regular expression。Right。

So it turns out that regular expressions are not enough。For us to。

Express a language with balance parentheses where the number of open parentheses is the same as the number of closed parentheses。

Now， one of the really cool things。Is that we can extend regular expressions to give us the expressive power we need。

And essentially， what we need is recursion。And that。Brings us to context free grammars。C， FGs。

 C FGs are really at the core of it， just regular expressions with recursion。

And this ends up being a very powerful way to declare。To declare the specification。

Of the syntactic structure of a language。So， the way that。We express a CFG， a context free grammar。

Is as a set of what are called productions。Productionions have。

A symbol on the left hand side of an arrow。Followed by the arrow。

 followed by zero more symbols on the right。Symbol is either terminal or non terminal。It's。Terminal。

 essentially， if it's a token。From our Lea， right， So a token that appears in our stream of output。

From the Lea。对。Terminal symbols can't appear on the left hand side of a production。

 They can only appear on the right hand side。Non terminals。Are all of the other symbols。

And they have to appear on the left hand side of at least one production。That is they need to。

 if you will， be defined。Let's walk through an example of a simple programming language。

Give you the the productions for it。To develop some intuition。So。

This is a context free grammar for a language with。

A sequence of assignment statements and print statements。And it contains。Listists。And addition。

 identifiers， numbers and。呃。嗯。And a parentheized expression。In this grammar。

 I'm using this typewriter font。To indicate the terminal symbols， so the terminal is are ID。Print。

Nam。诶。The colon equals， left parentesis， right parentesis， comma plus。Smicolon。Did I miss any？

Think I go the mo。The non terminals in this language are written than capital italics， S， E and L。

Now， by convention， S is the start symbol。Of。Of the context 3 grammar， that is。诶。

S is going to be the non terminal that defines what the set of strings are in the language。

So to give you an idea of an example sentence in the language。Here's one， right。

 ID colon equals numb， semicolon， ID colon equals。Open parenthesis， ID colon equals nu plus nu comma。

 ID plus ID closed parenthesis。So this is a sequence of token or rather token types。

You could imagine the source code before the Lea looked something more like a program。Right。

A sequenceence of assignments where an expression could itself be a list or rather a of statements followed by an expression。

Oh， the non terminals， by the way， S E and L， S for the start symbol， which is。Yes。

 also is the ht letter of statement。Which does something。E for expression， all the lists。

A list of expressions。Okay。So the moment we have。The set of productions。

Which I'm somehow hand wavingly telling you defines the set of。

A set of valid sentences in our language。 And I've given you an example sentence in the language。

What I need to do is actually tell you how we get from this list of productions。

To actually defining the set of strengths。And the key concept that we need here。

To get from this list of productions to an actual set of strings is the notion of a derivation。Okay。

 so。To show that a given sentence is in the set defined by this language。So we're going to start。

With the start symbol S。And what we're going to do is。Repeatedly。

 we're going to look at the sentence we currently have consisting of terminals and non terminals。

We're going to pick one of the non terminals。Initially， that has to be yes。

We're going to look at our list of productions。Find a production where that non terminal is on the left。

And replace that non terminal。😡，With everything that's on the right of the production。

We're going to keep on doing this until we have a string that consists only of terminals。

So here's an example。 starting with S， we choose S。We're going to choose one of the productions。

 this first one。And we're going to replace S with S semicolon S。

That gives us the second line of the derivation。Okay。

 now we're going to repeat in the second line of the derivation。We'll pick one of the non terminals。

 the first S。We're going to pick one of the productions。Let's say the second one。

And we're going to replace S with IDd colon equals E。Okay， so now we have 8 colon equals E。

 that's replacing this first S， semicolon S。We repeat， we're going to take one of the non terminals。

In this latest line of the derivation。That last S。Replace it with the right hand side of one of the productions。

And we repeat。Let's take this first E。And we're going to replace it with。

Let's look at this production。 E arrow nu。 We're going replace the E with the right hand side of the production。

Noumb。Okay， there's one more non terminal left， this E。So we're going to choose another production。

And continue。So you can imagine this process continuing。诶。

And you keep on going until there's no more non terminals left。Here's an example。

Where we've made the choices such that we ended up deriving this string。

 this sequence of terminal tokens。And this is the sequence that we saw on the previous slide。

Rightright。So in some ways， what's going on here is that this derivation。The sequence of。

Sequences of symbols。Where to get from one lane to the next， we picked one terminal。

 replaced it with the right hand side of production。

This is a proof that this string down here is in the language。And indeed。

 a string is in the language， if and only if。There is a derivation for it。From the start， symbol S。

Well yeah so in this case we sort of。We're starting from nothing like I might expect us to want to go backwards we're given the sentence and we want to。

Somehow far way back to the meeting and that' how do you start from the idea？Great question。

How do we actually use these derivations， So what what I've done at the moment is really just。

Toefine for you the set of strings that are in a language。 right。

 We've got a notion of a derivation and have said a string is in the language。

 if and only if there exists a derivation for it。Of course。

The thing that we're actually interested in doing is given a particular string。We want to know。

 is it in the language？And that is essentially the question of passing。And you're right。

 there's a number of different ways you can do it。You could start from the top S and work your way down。

Or you could start from the bottom， a sequence of symbols and try and work your way out。

 We're going to get there in just a second。Let me。Qu digression。 CF Gs。

 they really are more expressive than regular expressions。 One of the ways to show that is。

As we'll be digging into in lots of detail， at some point。

 we can come up with languages that have balanced parentheses。

 So that's something that you can't express in a regular expression。But any regular expression。

Can be expressed as a CFG。So that's a problem for you to work through。

If you were given a regular expression。How would you convert it into an equivalent context free grammar？

That is a set of these productions。I'll live there for you if anyone wants to post on Ed with a question or a solution。

 go for it。Okay。I want to introduce， an additional concept。Of a pauses tree。

The de of a pass tree is it's essentially showing you a derivation。

Except it's actually explicitly showing which。How we took a non terminal。

And replaced it with the right hand side of a production。So here， for example， is a PAs tree。Where。

Can imagine we started off with the symbol S。We replaced that symbol S with the right hand side of production。

 S， semicol and S。We replace that first S with ID colon equals E。

 we replace that E with nu and so on。So that is given a derivation。

You can imagine drawing up this poitory showing。For any given non terminal。

 how you replaced it with the right hand side of a production？In essence。

 a derivation is really a way of constructing a pars tree。We start off with the root of the tree。

 a single non terminal S。And at each stage， what we're doing is choosing something from the fringe of the tree。

That is a non- term of the fringe of the tree and putting as its children in the right hand side of one of the productions。

 And you kind of keep on doing this until the fringe of your tree consists entirely of terminal symbols。

はい。Now， what this means is that two different derivations。Might have the same past tree。

Becauseuse the derivation is kind of explicitly telling you the order in which you chose an on terminal symbol and replaced it。

And kind of the pastry doesn't really capture that。Okay， so we're getting closer to the idea of。

What we're actually interested in with a compiler， given a sequence of tokens。

How do we construct a po tree？Right， constructing a pasttry will both。

Tell us whether or not that sequence of tokens is valid， whether it's in the language。

 That is whether there exists a derivation for it。But it also helps us extract the meaning of。

 of that sentence。 That is the structure of this pastory is telling us things like。

I D is assigned nu plus nu。 This is telling us， okay。

 I'm going to want to be doing an assignment of this expression into that identifier。

So the meaning of a program is essentially related to the structure。Of， of the sentence。Yeah。

 the sequence have like。Multiple isomorphic bars trees like I mean like the hold that question。

 it's a really good question。Short answer is yes。 There might be grammars that where there's more than one parse tree that's possible。

For a， for a given sentence。We'll talk about what that means in just a moment。Okay。

So we've boiled this down to really the question of。How do we build a pass tree， right。

 How do we find a derivation。And in short， there's two possible answers。

 which William alluded to earlier。We can start from the top， start from a start symbol。

 choose a non terminal and expand it until we reach the sentence we're interested in。

 essentially magically knowing when we replace a non terminalal with the right hand side of a production。

 magically knowing which production we want to choose。Right， so， for example。

 give an S replacing it with。The non terminals。Well， it's a long derivation。

We can boot up that po tree。The lieuteant approach。Is。Really to start from the terminals。That is。

 given the terminals that we have， the string that we have。

 build the pass through from the bottom up， that is。Identify。

Something that matches the right hand side of production。And replace it。

With the left hand side of the production， so here we took ID。

Replace it with E or rather we started building this tree from the bottom up。

So this idea replace it with E now you might notice that E plus E matches the right hand side of another production for E and so on。

 so we're able to build up。嗯。Boot up this tree from the bottom up。Eventually。Driving。

Producing an entire pastry， getting to a tree。With the root S that covers all of the tokens。Okay。

 so essentially， top down or bottom up。呃，是。Yes， question reason why you prefer one direction。

We're actually going to be spending next lecture looking at one form and the next lecture looking at the others。

 so we kind of have a clear idea at the end of next week。

Which is preferred why you might prefer one over the other and why？Thanks for the question。嗯。

So Hill brought up the question of， could you have a single sentence？With two different pars trees。

 So not。Two different derivations。 right？ Remember that the same。

 the two different derivations might give rise to the same pass tree。 That is the same meaning to a。

 to a sentence。 But could you actually have two different。Pas trees。So the answer is yes， you can。

 And if you have a grammar that allows that， the grammar is known as an ambiguous grammar。

So let's see an example of that。This is a grammar for arithmetic expressions with parentheses over identifiers and numbers。

So。Let's think about the expression6 minus7 minus8。Here's one possible past through for it。

Essentially，6 minus-7。Negative one。Minus8。Right so that would be。Yeah。

 assuming arithmetic expressions have the natural meaning。

 they would be equivalent to negative9 or evaluate to negative 9。😊，Here's another pause tree。

For the same sentence。6，-7，-8。But here， the structure of the Pa tree is indicating that， you know。

 this arithmetic expression is 6 minus。7even minus8。All， so6 minus negative one。7。

 so very different meanings to these past trees。And as you might imagine。

Given that the same sequence of tokens。Can have these two different po trees and very different meanings。

 denoting very different integers。In general， ambiguity is bad。

What it means is the one sentence might mean different things。And well。

 this might be wonderful for politicians， lecturers who are trying to wave their hands about things。

 It's really not great for computer programs。 where typically we want a program to unambiguously indicate what it is that we're wanting to compute。

😊，It's usually possible。😡，For us to eliminate ambiguity by transforming the grammar。 And by that。

 I mean。We're going to use a different grammar that emits the same set of strings。

RightSo any string that was valid in the previous language is valid in the sorry。

 that was valid and the old grammar is valid in the new grammar。But the new grammar is unambiguous。

 There's only one way that a given sentence can be passed。

So let's take a look at some examples of fixing ambiguity。um。

One of the things that we would like to do in arithmetic。Expressions in general。Is to do。

But how do they teach it in the US and middle school， what's your order of operations？Pms， right。

 It's ingrained， embedded better than you all， right， parentheses， exponiation， multiplication。

 division， addition subtraction， right， So you want multiplication。😊，To bind higher。Then addition。

We also say that as modificationplication should have higher precedence。

 So given them a sequence  one plus two times 3。We want that to mean。1 plus two times 3。Right。

 as opposed to。The other way of passing it one plus two times 3。は。So。In addition to pem dust。

 like the order of operations。We typically like each operator to be life associative。

So when we see six minus7 minus8。We interpret this as 6-7。-8。That is。

We associate the operations to the left。嗯。Instead of the other way。So。

Here is an equivalent grammar of arithmetic expressions over identifiers and numbers。

That achieves this。Right， we're going to bind multiplication and division higher than addition and subtraction。

 And we're going to be left assos。 We're going to do that by actually introducing。

More non terminalals。E for expression， T for term F for factor。The way we do it is an expression E。

Is going to be either an expression plus a term or an expression minus a term or a term。

So in some ways you can think about this at the top level， the last thing we're going to do。

If we're going from the bottom up is do addition and subtraction。A term。

Is going to capture multiplication and division。A term is either a term times a factor or a term divided by a factor or a factor。

And a factor is going to be。An identifier， a number or a parentheized expression。So， this is。

Hopefully in somewhat intuitive way， capturing this idea of the grammars and forcing that we're binding。

嗯。Parrenheses first。We don't have exponentiation in our language， multiplication and division next。

 and then addition and subtraction。It's also enforcing left associivity。

So let's take a look at the rule for subtraction。E produces E minus ET。

Right so if we think about pa6 minus7 minus8。诶。There's no way we can actually pass this as E being replaced by 6 and this t being replaced by 7 minus8。

Okay， we have to pass it the other way。E can end up being expanded to 6 minus7。

 and the T can be expanded to8， but not the other way around。

 so this is worthwhile playing with right actually building up an intuition for this by trying to write out derivations or pasts trees for this and understand how this refactoring of the grammar enforces both the precedents。

And the associivity that we want。So help you。Can you prove a grammar is not ambiguous， Yes， you can。

We'll look into some of this later。嗯。随便。I'm not actually sure what the characterization of the computational question is。

 but in practice， we will have techniques to say， is a grammar is a grammar unambiguous。

 if we can show that it's unambiguous， fantastic。 we'll go with it。😊。

But I can't remember off the top of my head how precise that is ca。 do you remember。

 I believe it's undecidable to determine whether Thank you。Great， so it's undecidable。

 but we have conservative approximations that what we use in practice。Thanks。

I had had a feeling it was， but。It's。Okay。All right。

Now we're getting to the idea of how do we actually pass？Given a sequence of tokens。

 how do we construct a po tree？There's a few possibilities。You as a compiler writer。

 sitting down to write that first part of the compiler。Pasing， well， taken part。

 You've already rid yourixa。First way is actually to do it manually。Just write。Recursive functions。

R a recursive function that tries to pausese。An expression。And it might do that by， first of all。

 trainer pars。A tomb。Something like that or trying to pause a parenthesis first。Right。

 so we're going to see some examples of this。 It turns out that writing it manually processing known as recursive descent because you're essentially recursively through recursive functions。

 descending your way down the Pas tree。 turns out to be pretty easy to write。

It turns out to be that you can write pretty good error messages like if something goes wrong， hey。

 I was able to successfully pausese an expression followed by a plus。

 but I wasn't able to parse the next thing。 You were actually able to produce pretty good error messages that would give the user of your compiler pretty good information。

The downside is that it's pretty tedious to write， you can go and you can try it and writing a function per non terminal。

 D they end up getting pretty painful。And also， it's hard to maintain。 just like a lot of things。

 grammars change over time。 Maybe you need to refactor it for a variety of reasons。

 and then modifying your recursive descent paa is annoying。嗯。

Another approach is known as parsing combinators This is actually relatively popular in higher order programming languages like Ocal and Haskell The basic idea is that you're encoding grammars as higher order functions really what's going on here is you're actually using higher order patterns。

 higher order functional programming patterns。To generate a recursive descent PAs for you。

 it works pretty well。 we'll see some examples of it later。There are， of course。

 as you might imagine， a whole lot of PA generator tools。That is you give。The PAser generator。

 a grammar。 So essentially a list of these productions with some additional information like。

 you know， what to do with if if it successfully parss without production and it will automatically generate code that will implement the PAser。

So this includes tools like antler， which I believe is。Pretty much state of the art。

 at least an easily accessible par generators Yak stands for yet another compiler compiler。

 This was developed， I think in the late 70s and that stage even then。

 people were clearly exhausted by the number of par generators that had been written and in fact。

 Yak and various descendants of it have been ported to pretty much every platform in every language。

That you might choose to write a compiler on。We can split these techniques into either top down。

Or bottom up。 That is whether or not they essentially start at the start symbol and try and expand things in a。

In a very smart way to know which production to use。Or whether they're bottom up。

 whether they're taking the tokens and then figuring out how to replace the right hand side of productions with the left hand side。

Okay， what we're going to be doing in the rest of this lecture is really looking at recursive descent passes。

In next lecture， we'll be looking at。Some other top down。

Approaches and the lecture afterwards will look at bottom up approaches。So with that， let me。Jump。

To some code。Okay。Recursive descent A， this is a recursive descent paer for a simple lead expression language。

 It's going to be our first attempt。 It's not gonna to do great。嗯。Okay。

 we're going to start off with essentially something that looks very similar to our handwritten and Lexa that we saw at the beginning of this class。

 The key thing is that。Instead of just working over characters。

 it's going to work over an arbitrary token type。So。Tns out we can also use it for leing。

 if we inate it on characters and get it to produce tokens， a list of tokens， essentially。

 it'll work that way。 but we're also going to be able to express our recursive rules。so诶。TikTookk。

Is going to be the abstract type， the input type to the grammar， either characters or tokens。嗯。

The basic idea of a grammar。Is that just going to take a list of our token type？

And it's going to return。Like we did with our Leing。

 it's going to return a list of the possible passes。Right。Alpha is going to be the result of passing。

That might be the tree。With a list of the remaining tokens that weren't passed。Okay， so this is。

Pretty direct generalization of the Lexa that we saw。A function parse is going to take a grammar。

It's going to take a list of tokens。It's。Going to be。Exploring all possible paths。

And returning the parers that successfully consume all of the input。Okay， so that is。

 it's going to be filtering out the results that have。

Anything other than an empty list in the second place。

The next part of the code is exactly what we saw at the beginning of the class。

 It's essentially just constructors for the grammars。 right。

 So a grammar that consumes a single character。A a grama that consumes。The empty string， no tokens。诶。

Map for our grammars so that it's a grammar that returns an alpha and a function from alpha to beta。

 going to be we can produce a grammar that returns a beta。Alnation。Concatednation。Star。

And then some convenient ones plus， so that is one or more occurrences of our。嗯。

We are going to introduce a new operator。 This is going to turn out to be really useful for us。嗯。

This is very similar to alternation， like R1 or R2。Except it's going to be biased。On R 1。

 So that is given R 1。Or R2， we're going to first try parsing according to R1。

If we're able to successfully pass with R1， fantastic， we're going to go with that。

If we fail to par with R1， there's no way R1 can pass within we tray pars in with R2。Okay。

So instead of trying all possibilities， R1 or R2， we're going to try R1 and if R1 succeeds。

 fantastic。😊，This is going to be useful for us to do things like greedy matching。

So that is matched the longest possible string。So greedy star， for example。

 was going to be similar to star except we are using。嗯。

We are always trying to pass R followed by R star， and if we succeed in doing that。

 we never bother pars the empty string。So this means we're going to keep on parsing copies of R until we can't。

 wherereupon we'll consume the empty string， so this essentially means we're implementing the longest possible match with star。

Okay， greedy plus。This is all the same。Great， here's our token grammar， which。

So we're using our grammar on characters essentially to implement our Lea。And now here is our。嗯。呃。

Here is alexa， which is passing according to the Scmmar， the doc grammar。

 zero or more white space followed by。Zero or more tokens。Optionally followed by white space。

Now we're defining the PAser。 This is going to be the result of our PAser。 So essentially。

 a nice A S T representation of expressions。 So this thing here。

This looks like stuff that you've already been using。Right，The AS T representation of an expression。

 What we're doing is we're going to be defining the PAser that takes the sequence of tokens and produces the structured expression that you can imagine being used later on in the compiler。

We have the notion of a generalization of the C H constructor， it accepts。Any input token？For which。

This function returns something。And the output is。Whatever the thing is that was returned。So。

 for example， we could define the。Int grammar。Which as long as it's given any int token type。

It's going to return some I， the integer value。嗯。That means that the grammar will produce an integer。

Whereupon we'll pass it into this integer， the integer I enter here and return。This constructor。

 so a returner and expression， an inte lital。 So this is how we're going from。

The token type of I into an expression。Using the IA lowercase NT data constructor。Is that clear。

 I know， there's a lot of。Similar sounding words being thrown around。Okay。For a variable。

Accepting and identify a token， returning the string。呃。The talk constructor consumes exactly a token。

 So this would be the construct would want to use， say， I'm expecting an open parenthesis。

 for example。All right， here is our grammar。So， note that it's recursive。

So this is essentially where there are regular expressions plus recursion is coming in。

 it's because our grammar is itself recursive。诶。Essentially， we're going to have a whole lot of。

The options are we can either pass an integer， so an expression is either going to be an integer or a variable。

Or。Let， followed by a variable， followed by equals。Followed by an expression， followed by N。

 followed by an expression。And you see that we can essentially taking。The result of。

Successfully matching that sequence of tokens， extracting the things we want and turning it into a let expression。

Here's a parenttheized expression。 Con the left parenthesis token， consume the expression。

 consume the right parenthesis token。诶。This line doesn't actually quite work。嗯。Let's。

Let's try using this。So we can use it to to have a handy。Ass。Okay， let's try this one first。Great。

 so。We're able to pass let x equals 3 in x， this passes it into a lead expression， fantastic。

We course had disabled。诶。We hadn't disabled that this is passing it。Okay， sorry， this failed to pass。

 We paused a lid expression， and then these were the remaining tokens plus 4。

 And those was because in our grammar， we had。Commented out the part of pasing。So。

Let's try that again。We've got a stack overflow。So what happened there， let's look at our code。

That was when we uncommented this line， which。Sid。In our recursive function， to。Ps an expression。

 One of the possibilities is that you can passse an expression followed by the plus symbol。

 followed by an expression。 And if you do that， you end up。You know。

 constructing the a binary operation expression。It's what happened？Yeah， neckcholas。Yeah。

 so what ended up happening is as we tried to do all possible pars。We ended up recursing here。

So trying to passse an expression。And our alternation。We are trying all possibilities。

 And so they end up coming back to here where we train parsan expression。

 So what happened is we're doing this left recursion。

 That is we're recursing into the pars and expression function， X X underscoresco P。

Without making any progress， without consuming any characters， consuming any tokens。Right。

 so we ended up recursing， recursing， keeping on adding stack frames， we ran out of space。

 So that's not good。嗯。So we can fix this by。嗯。We're going to fix this。You know。

 due to the field trip， I actually failed to print out the list of things that I was actually meant to highlight on each of these recursive descent passess。

What I should have pointed out on recursive descent A。Is that we。

And not quite associating things correctly， I believe。

So what we're able to do is more directly implement the grammar， the refactoring that we saw to get。

Expressions， tombs， in fact， is done appropriately。Let me just jump to the code。

Quickly to show you that。Recursive descent B。This is similar to the file we saw previously。

 except now we explicitly have factors。Terms and expressions。

 let me scroll down in the file to show you that。Okay， so here we have mutually recursive functions。

 so this function is pars a factor。Which is either an int。

 a verbal name or a parenthetized expression。This function is paing a term。

That is multiplication or division。Enter an expression is either a term。

Or an ex expression followed by a plus， followed by a term or expression followed by a minus followed by a term。

Okay。呃。So this essentially。Get rid of the ambiguity that I should have highlighted to you with the first file。

In the same way that we saw on the slides， refactoring to remove the ambiguity。

But we still have this problem of left recursion。 We would also get a stack overflow if we tried passing。



![](img/b486466ab652e9e937f47d69e876304a_1.png)

Inappropriately。So in general， recursive descent passing。

 where the way you kind of say it is in order to pass。This non terminal。

 let me try out by parsing the possible right hand sides of the production。

That isn't going to work well if one of the productions is left recursive。

 If the non terminal is the first symbol on the right hand side of a production。嗯。

It turns out that we can often。Refactoror the grammar to avoid left recursion。So， for example。

 here's the grammar with expressions， terms and factors。 and it's left recursive。

 Expresss are left recursive。Terms are left recursive。Right， that is on the right hand side of。

A definition term， we have a term as the first symbol。We can refactor it。But it's a little annoying。

Okay， so。Here， what we're going to do is say an expression。Kin be is a term followed by E prime。

E prime is either going to be。

![](img/b486466ab652e9e937f47d69e876304a_3.png)

Plus。T followed by E prime。Minus t followed by u prime or nothing。



![](img/b486466ab652e9e937f47d69e876304a_5.png)

We can do something similar for factors。 sorry， for， for terms。

And factors remain unchanged since factors weren't left recursive。So。诶。This works。

You can go through and you can see that what's going on here is that it's actually。嗯。

Because an expression always has to start with the term。Means that we will always start with。

At times。诶。Or divides。Or a factor。Or nothing， or we'll just consume it too empty。嗯。

It requires post processing though。 That is the thing that we get back， the pars tree。

Does not have a structure that maps as directly into our expression A S T。 So were。

 we're going to get back the power truth from this。

 and it's going to require a little more manipulation to produce the appropriate。诶。

To produce the appropriate expression。嗯。You can take a look at the recursive descent C file。

 this is the same as recursive descent B， except we've reffactored the grammar to avoid left recursion。

Right， so。嗯。Here we have passingsing of factors， here we have passingsing of terms with term prime。

Here we have passing of expressions with expression prime。嗯。So you can play around with this and。

And see what ends up happening。 We do have。This function here is essentially the thing that is taking the result of the PAs tree and needing to do a little bit of manipulation on it to produce an appropriate AST expression。

I'll let you play around with that code yourself。

![](img/b486466ab652e9e937f47d69e876304a_7.png)

Finally， say parer combbinator， as I mentioned， a kind of a higher order approach to building recursive descent parrs。

嗯。Basic idea is that they。Take a PAer's input and return a new PA'ous output。

This is essentially what the recursive disscent code we wrote is。 So， for example。

The constructors for grammars that would take a grammar R and return something equivalent to R star that consumes zero or more copies of R。

It's essentially Pser combinators are essentially the natural way to rate recursive descent Pas in a higher order language。

 If you wrote it in a language like C or C plus plus or Java， you tend to be much more。

There's maybe more boilerplate code that you end up seeing of youd declare one function for each non terminalal。

 implement that function by calling the other functions to power non terminalminals as appropriate。

 maybe throw exceptions or something to indicate you fail to pass and catch them appropriately。Okay。

 so that's manually writing pauses next class。 we're gonna look at。



![](img/b486466ab652e9e937f47d69e876304a_9.png)

Using PAser generators and the technology that's behind the PAser generators and how they can pass more relatively efficiently in certain cases。

Thanks very much， good luck with the rest of the week and have a good weekend。

 I'll catch you all on Monday。😊，ま。他れじ。你什么。思ますら。啊，没白法是。没什。No pass on Monday。

 I'll send out an email about it it's university holiday， thank you。冇用。そな。Okay。what youThat's what。

对你南。I love night。所。My brother you work with like。系。私もやど。



![](img/b486466ab652e9e937f47d69e876304a_11.png)

I呀。

![](img/b486466ab652e9e937f47d69e876304a_13.png)

I。没关系。清楚。知道。Even yeah。して。新生は。然ち。啊，我讲。て。や。我去。不。あしない。かいです。再开。是认为。Yeahい。实清。Yeahや。一る。おいま。Yes。

 can be updated， take， like I said， prioritize your。I can heard that in discussion。但按会清。

You can do if you're feeling。F enough like catching on the thing。You know。

 maybe just a little bit amount of time。It再。I don't want like to what you don much but it's going to be。

just hang touch that thiss up affecting it。You know， your timing on。好啊。す。这么し哎。おてま。不跟你说。難かししな。

I think it's mixed opinions。First much just。たり。Yeah，I'll see you next speak。'll email， thank you。

应该张不做过去。我看的很。个那个多少。实先啊。Are we going to。That's really interesting。我的。this kind of。

Concurrency the program that has been compiled， and how do you make the of it？昨日。

taking advantage of the concur。Ohpe we're not going dig into current。ten of course。

 just hang touch about listen's up affecting。You know， get timing on。好饿。Theres。这下。あそう。都要为。可思。顔しま。

かしもしな。I think it's mixed opinions。First much like just。他なしいたり。Yeah， so，啊 see you。

And'll email thank you。应该张门说我钱。我我看下。呃那是什么。This is。Are we going to that。That's really interesting。我的。

this kind of。Concurrtency in the program that's being compiled and how do you make of it？You know。那个。

all taking advantage of the concurrency。we're not going dig into concurrenrt scale or so but there's maybe two ways to think that one is like concurrency in the program。



![](img/b486466ab652e9e937f47d69e876304a_15.png)