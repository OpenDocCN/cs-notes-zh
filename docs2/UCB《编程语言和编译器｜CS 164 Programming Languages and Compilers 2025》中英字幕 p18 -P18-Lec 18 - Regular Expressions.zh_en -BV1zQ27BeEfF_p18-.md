# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p18 -P18-Lec 18 - Regular Expressions.zh_en -BV1zQ27BeEfF_p18-

![](img/0051c4dd32cce33b384944ce9be6a103_0.png)

All right， hello y'all， first of all， congratulations on being through the midterm。

So proud of everything you'all have learned so far。 And in fact。

 normally this would be the part of a class session where I have us have a little chat about any concepts where I felt we all were doing a little week。

 but honestly the midterm results looked really good we're really happy with how much understanding y'all have achieved of the topics that we have covered so far If you have questions about any of the course content。

 please please please do either come up during the five minute break。

 I'm gonna try to leave some section at the end of class if you want to ask any questions about what was covered also absolutely come chat with us in office hours。

 we are extremely available to chat through midterm questions。 regrade requests are open for a week。

 This is a good time to look at in case it was't clear。 Hopefully everyone got the email。

 the greats came out yesterday So those were all available to。

 you can already like see the feedback right there。

 So definitely encourage you to take a look at the feedback and to come to us with any。😊，Questions。啊。

I don't think there are going to be logistics questions about the midterm， but are there any？Yeah。

We do not。 This is a great question。 We do not release statistics。 This course is not curved。

 So you are not in competition with any of your peers。 You are merely classmates together。

 There is no curve， therefore。We don't release the distribution yeah。Any other。Questions about that。

 I will try。 I we have a pretty activity， heavy day。

 So it sort of depends on how many activities we end up getting through and sort of how much time we have。

 But if we have time at the end， I will also try to leave some like midterm content question time。

 So we'll see。Okay， with that， I'm gonna dial us back in on parsing S expressions。

 So I'm going to remind us of where we have been。

![](img/0051c4dd32cce33b384944ce9be6a103_2.png)

And then， we will。

![](img/0051c4dd32cce33b384944ce9be6a103_4.png)

Visit new territory as well。 So here's where we landed。

 So we started by introducing the idea of a grammar， right， a grammar。

 which is basically just expressing here are the things that you can write down。

 right that will be accepted by a given grammar。And so since we are using grammars to express what programs you can write down。

 we are saying something with this grammar about what programs will be accepted by our pars or by our programming language。

So that's what we did when we first saw this grammar。 we're like， okay。

 like we are gonna to use this to express not anything about the meaning of the programs。

 not anything about sort of what the constructs are。

 but simply what are the strings that the programme is allowed to write and then allowed to feed into our tools that we are making for that。

So that's sort of where we landed。 And we got introduced to a couple of ideas along the way。

 We learned about nonterals， which are things that are not actually going to appear in the text of the program。

 but we use them in these production rules， right， So a production rule is something where okay。

 we can say that if we start with the thing on the left， the nonteral on the left。

 we can go ahead and produce right production rule produce the thing on the right。

 So if I'm going through the process of building up a program by using these production rules because this does。

 in fact， tell me what programs I can build up， I could start say at this start production rule right。

 So we have the start symbol S。 I could start with that nonterminal。

 I could follow this first production rule。 I would land on a situation where we have none to。

 which would be equivalent to the program too。 But we also figured out。

That we could use this in sort of more complicated ways。

 So here we started from that same start symbol。 But then we said， okay。

 let's take the particular production rule that uses LPn list Rpren。 We can see that up here， right。

 LPn list Rpren。 This is one of the things that we can turn our start symbol into。

 And we sort of kept doing this process for all of the non terminals until we had landed on something that was all terminals at the leaves。

 And this we determined was called a parse street。And the thing that we had figured out right at the end of the class session on this was that the way that we can know if something is accepted by our grammar is if we can build a parsse tree that has that particular string sort of read off the leaves right if we can generate one of these artifacts。

 something that looks just like this is just following the production rules is just going through those production rules mechanically and at the leaves it has sort of the characters that would then form up into the program we are trying to submit to the parser fantastic that is a valid program。

Do we have questions。About that。Sort of the natural next question of like what if you can't form a parse tree。

 fantastic， you found a program that is not accepted by our grammar。

 and that should not be fed into our programming language implementation。

Are we on mostly the same page so far？Like how does it program？I am so happy。 You know， Okay。

 so this question is， how do we know， I think sort of。😊，2 related questions。

 How do we know something is not a completed parse tree。

 And also how do we know if a string is not accepted by the grammar。

 So these are two sort of separate but related questions。 So I'll answer both。

 So if we are going through starting from the top level， right eventually。

 we will probably want to also think about not starting at the top level。

 So we'll think about that in a moment。 But if we're going through starting from the top level。

 And we're following production rules， and we're using it to generate this tree。

 and we haven't land in a position where all of the leaves。

 all of the things at the very edges of the tree are terminals， that is not a complete parse tree。

 right， So that is sort of the answer to that first question。

 how do we know if it is not a complete parse tree， But the second question is。

 how do we know if we cannot construct a parse tree for a given input string。

And that's exactly what a parser does。 So that's the thing that we're gonna to be building today。

 Yeah， great question。Other yeah。Please。How did it know， like， say we had like two。Yes， that。不单纯资质。

Great question。😊，Yeah， so this is a question about the particular representation of programs that we've been using。

 The question is， what if we had instead of plus1，2， what if we had one plus2 down here。

 that looks like it would still be accepted by our grammar and that's absolutely right， right。

 because remember that the representation that we are using right now is just us expressions。

RightSo as long as we have this sort of structure where we've got， okay。

 we've got the LPn and then we've got a bunch of numbers of symbols and we keep going until that there RP。

That looks like an S expression， right， So that is okay according to the current representation we're using now。

We are now at the point of the class where we're ready to start saying， hey。

 I might like the parser to check more things for me。 So we're not going to get to it this session。

 this session we're just going keep thinking about S expressions， but in another couple sessions。

 maybe like one or two sessions we are absolutely going to start saying to ourselves， hey。

 I actually know more about the structure of programs that I'm allowing that is currently expressed with S expressions and maybe I would like to in fact have the parsar for some of that for me。

Other questions。Cool， okay。In that case。We have。A couple of different representations of programs in our language that we've been thinking about at this point。

 So over here， we have the grammar we just met， right， grammar。Grammar of S expressions。

 And then over here， we have this sort of Sx type that we have been using。

Inside some of our Oak Hamel programs。And when I look at these， I'm seeing some commonalities， right？

 So it certainly seems like， you know， this thing seems to relate to this thing。

 It looks like that thing kind of relates to that thing。

 We do seem to have sort of lists appearing multiple places。

 we can maybe imagine drawing connections between there。

 Maybe even this also sort of looking like that list， right。

 So it looks like there are some parallel structures going on。

 But there are also some things missing from this S X representation that we have been thinking about for so long。

 So in particular， one thing I'm thinking about as I'm looking at this， right。

 the thing that lists and scheme are famous for is all those parents right。

 If we just look at this S X type we've been manipulating this entire time。 Like， yeah。

 we see the list structure that's being built up。😊，But we don't actually see any of those brands。

 any of the particular strings that the programmer would have to write down in order to get a program to run。

 And so this is sort of getting at the difference between the intermediate representation that weve been using up to this point and the idea of what the grammar is expressing for us。

 Again， the grammar isn't expressing anything about the structure of programs that is you know。

 plausible to use necessarily。 But it is telling us something about the strings we're allowed to write down。

Feed into the parser。 right So this has that information about what do these programs actually look like。

There's all kinds of different things that we could have written down that we could eventually translate into a representation that looks like this。

 The only way that we know sort of what is allowable to actually put in the string that we are calling our program is by looking at the grammar。

And in fact， later on today， we'll see that there's even some more information hidden inside these things。

 because right now this is not telling us what exactly gets to count as a number。

Are there questions about this about either the connections between these two or the differences between these two？

Okay， cool。 In that case， I'm gonna sort of pause again to talk about the connections to these two。

 because what we're gonna want to get out the other side of our parser， right。

 What we're gonna get in is， if you remember back here， we had sort of this idea of a list of。Tokens。

 so what we're going to get into our parser is something that looks like this right It's just going to be a token representing one of the terminals or nonterminals。

 In fact， we're only going to see tokens representing terminals。

 right those are the only things that are allowed at the leaves of the tree。

 so we're only going to see terminals So we'll see a list a sequence of those terminals and we'll have to turn it into something that looks like this。

 which if we take a look， obviously looks like the Sx that we have been dealing with so far。

And so it's important for us to actually notice the connections between these two because what we are going to be in charge of doing as the parser is saying okay。

 I want to take my knowledge about the grammar about the strings that the user is allowed to write down and I want to use that to actually create something that has type S expression and I'm going to sort of give us the way that we should be thinking about this。

 which is for each of these non-terminals right the lefthand side of these production rules。

 we're going to have one helper function that is going to be in charge of producing things that have basically that type。

 So the Sx type or the list of Sx type and then within those helper functions。

 we're going to have one match case for each of these production rules。

And so we can see again the connections between。 We can see why those would be connected。

 And so this is going to give us basically a mechanical way of going from this grammar to a parser that is going to give us things of the output type that we。

So that's the overall structure we should bear in mind as we started on this。So far， so good。

Fantastic， okay， let's see if there's anything else we want to highlight there yet。 Nope， okay。

 let's build this so。

![](img/0051c4dd32cce33b384944ce9be6a103_6.png)

We have。Oops， we're not plug in， so we don't have it， but we have a。



![](img/0051c4dd32cce33b384944ce9be6a103_8.png)

Hand parser file。I'm going to talk us through what's in there。



![](img/0051c4dd32cce33b384944ce9be6a103_10.png)

![](img/0051c4dd32cce33b384944ce9be6a103_11.png)

Okay， so this is our new little file， hand parser dot M L。

 It is the only what you see right here is the only code that we are going to be building on today。

 There's nothing hidden。 There's no secrets。 This is the only thing that is going to appear inside this hand parser。

I'm providing our grammar over here on the side because as we said。

 we are going to be taking advantage of knowledge about the grammar in order to actually structure our parser。

So let's hide this。 This is the only code that we are thinking about today and I'm going to just quickly talk through what we've got here。

 So we've got this idea of while we have our normal Sx the thing that we're normally used to thinking about when we're thinking about how we are structuring the programs that we're operating on。

 and we have this token type which is basically exactly what we were seeing as the things that we're coming into the parser in our little illustration and we can also see how we have generated those now this is not a great tokenizer this is a pretty bad tokenizer。

 in fact， because you can see that what we actually doing in order to tokenize is just splitting on spaces so let me demonstrate why this is not a particularly good tokenizer。

So， let's go ahead and。Try it on something。Oh， sorry。Let's do tokenize。And let's do。Well。

 that's not very satisfying。 That is not the S X representation I would expect to get just based on looking at that。

 And that's because I didn't leave spaces in the various places。 So okay， this is a bad tokenizer。

 But for the purposes of today in order to keep it simple， is actually fine。

 right as long as we leave the spaces between everything we can get out the kinds of representations that we want our par to be playing with。

 So bad tokenizer， but that's okay， because we're just thinking about。Okay。

 any questions about what's in our little hand parsel where we feel okay with what's in there。So far。

 right this is just looking for a left parentn and then it's making that L parentntoken。

 it's looking for a right Bn， it's making the R Parntoken。

 it's going ahead and making numbers and symbols out of everything else。We feel good so far。

Fantastic in that case。Lets go ahead and start in on how we actually turn this into a parser。

 So the first thing that we want to do is recalling our sort of hint about how we're going do this。

 We want to make a helper function that is just going to be in charge of parsing one S expression。

 right， That's sort of one of the things we said was for every nonteral。

 We're gonna have one helper expression that's involved with parsing things related to that nonterminal。

 So let's go ahead and start doing that down here。 say。Pse S， X， right。

 We're really just doing exactly what we say on the tin。

 And we're gonna go ahead and have a list of tokens coming in。

And what we want to have coming out the other side is an SX。 and we will also。

 because of how we are going to structure this process。

 we are also going to have something else coming out as part of this pair。

 which is just a list of the tokens remaining to be parsed right so if we have additional tokens left over。

 we're going to go ahead and provide those as the other item inside this pair。

So that's what we've got going on to start。Okay， and I said that the way that we were going to actually construct the helper function for each non terminal is that we're going to go to heaven and have a match case for each of the production rules。

 So let's start that match。I think these first not tos talk。Let's do it with。

Right so the first token in our list that we're seeing is just that nu N and then after that we've got some other tokens。

 tokens 2， if we are in that situation fantastic， let's go ahead and make the appropriate S expression right remember we're just using our S expression。

 the same old standard nu we'll go ahead and make our nu N and then we are ready to have the other item in the pair be tokens 2 which is just to say all the other tokens that we haven't messed with yet。

I think we'll also find the symbol situation relatively straightforward。So let's go ahead， oops。

So that's me making a pretty bad mistake because remember that what we've got coming in are these tokens。

 right， so I can't be using these S X。Constructors， I have to be using the token constructors。

 because that's what we're actually trying to parse here。 So nu N。

 And then what we get as output is an S expression paired with the remaining tokens left to be parsed。

 And if we get a symbol S in again， with tokens left to parse， we can go ahead and make symbol。

And we can have the remaining tokens available。 Okay， so far so good。Now。

 it's starting to be a little bit harder， right， So looking at numbs， sort of all right。

 we've made something that has the appropriate as expression type。 I'm looking at Sim， same deal。

 I'm thinking we probably want to match a left parenten first。 So that feels pretty good。😊。

But after that， it's not totally clear what to do here， right。

 So I want you to go ahead and with whoever is nearby， talk about what should we do inside this case。

Chat for about 30 seconds。Our goal is just to sort of deal with this production role。

 right that's what we're trying to do。Alright， so hopefully we've all come up with some variant of a strategy that reflects on the hint that we mentioned earlier。

 which is that we are planning to have one helper function for each of our nonterminals in this case for S expressions。

 we have these two non-terminals available。 We are expecting to have some kind of helper function right I've started drawing it out down here。

 We're expecting to have some kind of helper function that is going to actually handle finding things that match this right we know that we're gonna to have some kind of a parse LST function available at some point。

 and that is already doing the work that is going to take in order to do this right in order to figure out okay what's coming out the other side of an LST So let's go ahead and just assume for a moment that we have that thing。

 and then let's wrap up here。So assuming that we have that。

 we were going to want to make a call to it。 So let's do let Xs 3。

 and I'm explicitly naming it Xs instead of X to highlight the fact that this is going to be giving us back a list of S expressions。

 we're going to get back multiple， right， So let's go ahead and have that B along with tos 3， right。

 So the lingering tokens that are still yet to be parsed parse LST。

 We're going to apply that to our tokens that we have remaining， right。

 we've already handled below left parent。And we'll go ahead and use that to make up something that has our S expression type because remember we're only returning a single S expression from this particular function。

 So let's go ahead and make something that has that list constructor and we'll go ahead and use x3 as the contents of that list and then we will go ahead and provide totes 3 as the tokens that are still remaining to be parsed So okay。

Looking pretty O so far。 What if we get， Oh， sorry， I've got to spell that right。

 What if we get anything other than a number， a symbol or a left parent first。

 Any guesses about what we should do。Yeah。I'm hearing various murmurs of of raising errors。

 absolutelysolly。 Yeah， so this is a situation where this is， in fact。

 exactly the situation that we were talking about of how do we know if something doesn't match our grammar。

 right， We only have these three production rules for Sx。

 If we see something else starting out the the input that is not one of these three things。

 That's it， we're done for， right， that is not going to work for us。 And so if we get anything else。

 fantastic， let's raise， I think we made this little parse error exception。 So let's raise that。😊，O。

We are now done with our helper function related to these production rules。

 So now is a good time for any questions about how we have done those。 Otherwise。

 we'll move us on to the next helper function。I love this question。 So this question is， hey。

 I'm seeing this Lparen。 I'm not seeing an Rparn。 and that actually relates to what we're going do down here。

 So if we think about what's going to happen down here， right。

 this first case that we're thinking about is the empty string。

 So let's go ahead and start our match right， So match tos with Okay， what do we do in here。😊。

So it doesn't probably make sense to have。That be the thing that we're matching， right。

 Our tokenizer is never going to just give us the empty string。

 even though what we see over here is the empty string。Right。

 the tokenizer could presumably put empty strings anywhere in the input。 So it's。

 it's not going be just sticking those in randomly。

 I think it probably also doesn't make sense for us to put this。In here。

 do folks want to chat for maybe just 20 seconds。 Why do we not want to see this as the first thing we're matching to correspond to empty string。

Sorry。So hopefully we're thinking about a situation that's。

Something like this right If we just have that left parentn says fantastic。

 we can go ahead and go down here。 our tokens list is gonna to be empty。 We go down here。

 we match this。 if we say yep， looks good That's a list。 Oh。

 we pop back out here suddenly we've got this list that's only based on having the Lparn。

 we actually didn't find the RP The thing that for us is actually signaling being done with our list is RP。

😊，Is Rparn， right， That's actually how we know that we have reached the end of our list。 right。

 So if we see an Rparn， followed by whatever other tokens。

 that's the situation where we know that the empty list is the thing we're actually going to want to produce。

So this was a great question。 Yeah， the RP is showing up， but it's showing up elsewhere。

Other questions about this before we finish up， ParceelsD。

 there's actually not that much more to do for us。Okay。

 so let's go ahead and handle the other lingering case。 So say we get anything other than。Oops。

 sorry， this is going to have to be。The pair as always， so we have to pair it with what's lingering。

 which is to say tos2。Okay， great。 So now if we get anything else， what do we want to do well。

I'm looking at this， our only remaining match case。 And it is starting with an S expression。 Now。

 one thing we could do is we could say， okay， look for if it's a numb。 Look for if it's a Sim。

 Look for if it's an L parent。We don't need to do that。

 We've already got something that handles this， right。

 We have our helper function that handles parsing S expressions。

 So let's go ahead and instead of sort of reiming all of that infrastructure again。 Let's use that。

 So let's do let。Ex2。Talks to。Pse。Sx。Great， we're going to go ahead and pass in the toques。And。

What do we want to do next？We want to go ahead and parse a list next。 Now。

 do we have something that lets us do that？ Do we already have something for that。Hopefully。

 we're starting to recognize some parallel structure， right。

 when we wanted to get something that has this， we use the helper related to this。

 We want to get something that looks like this。 We're gonna use the helper related to this。

 So let's just call ourselves。 right， We can do that recursive call to parse LST in order to get something that is a sequence of an S expression followed by an LST。

 So let's go ahead and do let X 3。😊，Tks 3。Pse。L he talks to in， what do we want to actually get back。

 Oh， man， I really can't spell some days。 Parse， great。 What do we want to get back。Well。

We're knowing that we're going to have to actually sort of patch together X 2， right。

 the thing that's at the head of our list with X3， the thing that represents the entire rest of the list。

 So let's do that first。 Let's do a little coning。Fantastic。

 that's going to give us our list of S expressions。

 And then we've got the tokens that still remain to be parsed。And I misspelled again。

 because that should just be one expression。 Fant。 Okay， so that is。😊。

How we have represented our grammar， pretty much just going through mechanically and converting every non terminal into helper function and every production rule into one of our match cases。

 Now is an awesome time for questions about that。😊，对啊。Say in the numb case。

 why don't we recurse on tos too？I think I understand the question， but we， in fact， do。

 So if we take a look down here， right， we're getting back this。

Tokens list of tokens that remain to be parsed right We're at the head of the list right We're down here And we know that there's other tokens that we haven't dealt with yet。

 And so then we're ready to actually go ahead and use those to represent the rest of the list So we call parse LST is that the question like if you look at sort of how this grammar is structure。

 This doesn't say numb N S X right we are really trying to match the structure of the grammar really closely。

 we should only try to find a next S expression at a place where we're expecting to find an X S expression。

 We should only try to find a next LST at a place where we're expecting to find an next LST。

 So this is sort of encoding for us the recursive structure that we should use。Does that make sense。

Other questions about this？By the end of。Return。Amazing question。 So we our return。

 the the type that we are returning for each of these is an S expression paired with the tokens remaining to be parsed。

 or in this case， an S expression list with the tokens remaining to be parsed。 Now。

 the S expression is， of course， our start symbol。 So this is the one that we're going to call to start。

 And So what we're expecting to get back is a single S expression followed by the tokens remaining to be parsed。

 And the question was， should that list be empty。😊，Absolutely。

 so let's go ahead and make our little wrappper that does that check for us。 So here we go。

 Let's go ahead and do let parse。We're just getting in the string here。

 We're going to have to call our tokenizer。 We're going to give。S expression out the other side。

 And what are we getting at oops， can't spell。 Then we're going to get out the other side。

 like totes。Peoples。Tokenize， we'll call that on S。 and then。Here， L。

 just for list the remaining things， parse S X。Tokes in。What next Well。

 we want to go ahead and if list that length。Is one list that length applied to L is 0， sorry， then。

We want to get our expression back。Otherwise。We have a parse error。 Did I misspell parse S X。Ors x。

Oh， thank you。 Yeah， I forgot the equals。 There we go， okay， fantastic。😊，Great。

 so we're going ahead and checking if it's 0。 Now， why is that， right？ Like。

 why would this actually be a problem， So let's， let's take a look at a program that maybe we're like somewhat happy with。

 but not totally happy with。I would argue that I want this to get rejected， right？

 But if we went ahead and actually put this program through our parser without this last line。

 it would say， okay， well， I have matched this。 This is all sort of this part has parsed Well。

 We've got an S expression out the other side。 And yeah， there's this extra token off to the end。

 but actually， we do want to prevent that right， We need to have parsed everything or else we're gonna go ahead and say。

 okay， there's this trailing stuff。 This is not a valid program。 reject rejected。

So that's exactly why we had this last line， awesome question。Okay。Questions。

About this before we take our five minute break， we're finally getting back to taking our five minute break early。

Sorry， I know we've been doing late。每次好。Good question yeah this question was is this and just for mutual recursion。

 Yes， that is exactly what it's for you can see based on sort of the structure of our grammar that we're going to have to use LST inside SX and then inside LST we're going to have to use SX but we're also going to have to use LST itself and so this and is just so we can recursively mutually recurse。

In these two。Okay， cool。 I will see you again at 418。 Take your stretch break， take your water。

 and I'll see you soon。Oh， if you want to come up and ask any questions about midterm content。

 you should also feel free to do that right now。Hello there。A what you're recording from。

I saw it was it not posted？ird although I'll check with the GSs。 it should be。 Yeah， yeah。

 sorry about that。Alright， let's go ahead and start back up。

 I don't think it's gonna be too surprising how our parser actually behaves。

 but we can see that we've gone ahead and we've parsed plus 1，2。 It like that。

 We've tried parsing parent plus 1，2。 No， right， Par。 It says， no， no， no， no， no。

 As long as we sort of stay within what we are expecting to see。And as long as you know。

 because we are still using the bad tokenizer， as long as we keep our spaces between everything。

 everything looks okay。 But what if we don't want to keep using our bad tokenizer， right。

 Maybe we want to do something a little bit smarter。 Turn out we do have the technology for that。

 So let's swap over。To our slides。We are now going to move into tokenization land。

And it turns out we're going be focusing on one of the things that is going to make tokenization honestly。

 really easy。 It turns out that if we use regular expressions。

 hopefully a familiar concept for many of us， but it's okay， if not， if we use regular expressions。

 we can get ourselves a really， really fast way to figure out if something fits within。

The the sort of definition of our token types， right， So whether this is a number。

 whether this is an appropriate symbol， whether this is a left or， although that one's pretty boring。

 right， So we can go ahead and check with only a linear scan of the characters。

 And that's gonna be really important because assume we have a lot of different token types that we might care about if we are doing a bunch of backtracking in order to。

 you know， and we're trying it on all our different token types。 And for all of them。

' having to do a bunch of backtracking in order to figure out。

 is this actually the particular kind of token we're looking for here， That's gonna be a problem。

 right， we really need this to run。idAnd so we are going to be able to take advantage of regular expressions in order to get ourselves a way to figure out if something matches a token definition really very quickly。

So let's go ahead and dive in on that。And remember。

 tokenization is just this process of going from the raw string to the list。

 It's still a flat representation， the list of the tokens， right。

 So the things that we were seeing going into our parser。

A there questions about sort of that overall structure first before we actually dive in on regular expression？

Cool， all right。So。I think probably a lot of us have seen regular expressions before。

We actually thought about what is the grammar of regular expressions。

 So in the same way that a moment ago we saw the grammar for S expressions and we were like， okay。

 how are we allowed to actually write down program such that were gonna get a proper S expression out the other side。

 We can now use that same representation， right， This grammar that we see over here to represent the things that we are allowed to write down to be regular expressions。

 And I'm going take us through each of these production rules in turn。

 And I want us to sort of use this as an opportunity to think about what we can express with regular expressions。

 So this one is sort of the most straightforward， right， say we've just got a string。

 Here's an example of such a regular expression。 Does anyone want to shout out a string that this will accept。

😊，呵。😊，Let's go for this one。There's going to be one。It's the string A。 I love it。 Yeah。

 that looks like that can accept the string A to me。 We can get a little bit more complicated。

 Now we can go ahead and mash together too， right so we can have this regular expression A。

 we can have another one of these regular expressions B， if we mash together these two。

 What is the string that this is going to accept。😊，I'm hearing AB， I totally agree。

That's gonna be the exciting string that we can accept with that extremely boring regular expression。

 Fantastic。 Now we start to get a little more complicated， right， So now we're seeing this bar right。

 And that's representing essentially or So that's saying we can go ahead and produce either the thing that appears on the left。

 or the thing that appears on the right。 So perhaps shockingly， we could get the string A。

 we could get the string B。 either of these would be accepted。

 or I will also interchangeably used the word recognized by the regular expression A or B， right。

 So we will use accept and recognized interchangeably。😊，Okay。

 hopefully we're feeling good about those ones so far。

 Are there any questions about the the portions of the grammar we've seen so far we've seen up through here。

We like it so far。 Fantastic。 Okay， so the next one is exciting enough that it got a special name。

 So this is the clean star。😊，Right， that's what we've got going there。

 And this is basically just saying we can have as many copies of this thing as we want。 right。

 So we've got a star here。 That means that we could have。The empty string，0 copies。 We could have。A。

 we could have AA。We could have A A a。On and on on on。

 So you can see how we can start to get infinite things here。 That's feeling good。 That's nice。

 We like that。 Okay， what about this following thing， Well， this is saying， okay。

 we can do some grouping， right？ So it turns out that if we have this onen right here。 Well。

 clean star that actually binds tightly。 And so that is going to allow us to accept。😊，A or A， B or A。

 B， B， or A， B， B， B， right on and on and on。 If we instead want to have sort of a recurring sequence of A。

 B， A， B， A B， A B， I might want to add in some pars。 So as soon as I add in these pars right here。

 I can get the empty string。 Sorry， the empty string， or I can get A B， or I can get A， B， A B。啊这な。

So far， so good on what we are allowed to express。Is this grammar notation starting to feel a little more familiar where we're sort of writing down the things that we're allowed to write down in this formal way。

So far， so good， it's still a little unfamiliar， maybe it's okay。

 we're going to get more practice with it。Yeah， okay， cool。

 So these are sort of the building blocks that we get to use here。

 We're gonna go ahead and sort of use these in order to get to things that are maybe a little bit more complicated。

 So here are some extra things， you can see them down at the bottom here。

 that we can build on top of these sort of core components。 None of these are super wacky。

 But let's go ahead and just talk them through anyway。 So here we're basically saying， okay。

 if I have this plus after this is saying I want at least one copy of X， right。

 And so you can see how you can build that together by concatenating， right。

 This was just concatetnation。 We can concatenate1 x with one x star。

 And that's gonna give us x plus。 And so if we went ahead and wrote a plus that would mean that we were allowed to have a。

😊，A， A on and on and on。 But what is no longer allowed。

 What we have knocked out of contention is the empty string， right， so that is not allowed anymore。

 If we are putting the plus instead of the clean star。

What else do we have that we can sort of mash together here？ Well。

 we can go ahead and have sort of a shorthand for doing the or between X and the empty string。

 That is just X question mark。 So if we went ahead and said a question mark。

 we would have the option to have the empty string or the string A。

That's what would be accepted or recognized by a question mark。

And then we have the one that's sort of probably the most boring。

 which is just we sort of in our grammar。 we only have the option to order together two things。

 right， binary or， but we might actually be interested in having the option between all of these things。

 in which case， we can just sort of reconstruct it by doing the last two and then the that or the other one。

 we can just sort of build it up with the the nesting and the parentheses。 So if we did。呃。

A or B or C。 We could go ahead and have the strings A or the string B or the string C。So far。

 so good。Fabulous， in that case， it's time to test our understanding so。Oh， first。

 why are we doing this， right？ So the reason that we care about this right now is because we are gonna use this for tokenization So here we can see that were。

 we are sort of hiding before where were we actually getting these tokens for。

 say the num or the symbol。 This is an example of the kind of regular expression that we might write for numb。

 You might notice there are some things we might want to refine about this。

 We can write one that is more careful like right now is actually allowing us to say negative 0。

 we might not like that。 So we could get a little fancier。 But basically。

 you can see how this is expressing， okay， we have to have you know，0 or more。

 actually one or more of these digits。 And we can have a negative sign at the beginning if we want。

 And those are sort of the components of the regular expression that's gonna grab us out a number。

So far so good。Fabulous， okay。In that case。You want us to go ahead and think about which of these match。

 Please turn to the person next to you and start thinking through。Alright。

 let's go ahead and start talking it through。 So I'm seeing sort of two components here。

 We've got our A。 we've got our C。 I can see we're expecting an A。 we're expecting a C。

 It seems like this is going to be optional because of the clean star allowing zero copies。

 So I'm looking that I'm thinking， yup， good to go。 Let's give that a little check mark。

 What do folks think for that next one。What about ABC？I'm seeing some shaking heads。 I have to agree。

 I don't see how we could get there， right， So if we're sort of going through looking at that， A。

 okay， so far so good， where would we get just a plane B。

 And if we tried to use this A B path through our clean star。

 then we would have to have had an extra A at the beginning。 This looks like a no to me。

 So let's give that an X。 What about A A C， Hu， if you think yes。Hm， if you think no。I agree。

 That looks fine to me， right， We can take the path where we say， All right， one of those A。

 and then we can take that egg， and then we can take that seed It all looks pretty okay to me。

 I'm feeling comfy。 What about that next line。 What do we think， Commfy， yes。😊，Home for no。Yep。

 I think we're all on the same page。 That looks like a yes。 Again。

 we can sort of figure out that path through the regular expression。 What about that last one， A， A。

B，BC， Hmed if you think that one's going to work。How if you think that was not going to work？

Same page， right， That is looking like a no。 I cannot find us a way through that that gets us A， A。

 B，BC。It's okay。Thiss kind of interesting。 We're sort we're。

 we're clearly doing some reasoning in our heads that's sort of something about walking a pathway through this regular expression。

 We're kind of sort of thinking through some ideas around that。

 We can do these tests on ourselves later。 if we feel like， but okay， the。

 the reason that we're caring about this is because we can do tokenization with it。

 So here's sort of the particular representations that we're using for numsum and LPn and RPn right now。

And here's how we are going to use it。 So what we are going to do is we're going to say， okay。

 I'm going to go ahead and tokenize。I'm going to try to draw on here to make it clear what we're doing。

 this particular string that is coming in。And I'm going to go ahead and have our tokens that we have figured out so far。

Fantastic， so if we go ahead and we see that string is matching with them， then fantastic。

 We're ready to go ahead and make one of these， right， So here's the tokens we've matched so far。

 Let's mash in our new one that we have just found。

 and then let's go ahead and tokenize what is actually remaining。😊，Now， because remember。

 we can see that as right there。 And then we do the exact same thing for symbol。

 I don't think this is super surprising。 This is really just going through the process of let's try it for number。

 If it doesn't work for number。 fantasticantastic， let's try for symbol。

 If it doesn't work for symbol， let's try it for the next。And again， we just have these four。

So in this instance， we actually don't have that many tokens to actually try it on token types to try it on。

 but in other situations we might have many。 And so it becomes very important for us to be fast。

 right， This match check has to be really， really fast。So let's bring this。To this slide。

 So the reasoning that we were doing a moment ago， when we were deciding whether particular strings were going to be accepted by particular regular expressions。

 Again， I have this idea of， okay， we're sort of thinking about the path。 We could take through it。

 We're going to go ahead and look at that first component of the regular expression。

 Can we match that。 Oh， what if we do this， right， There is a formal way for us to think about this problem。

 And that is with finite automata。So we're going to briefly， briefly。

 briefly step into theory of computation territory here。

So if you have ever heard of deterministic finite automina。

 if you have heard of non deterministic finiteatmaa， if you've heard of finite state machines。

All of these have the same equivalent computational power to regular expressions。

 which means if we have a representation of one of these things。We can go ahead and transform it。

Into another。RightAnd so if we think about， okay， the regular expressions that we were working with。

 we can sort of see already how those characters might be sort of moving us between states。

 but let's take a moment to actually talk through what a finite autoin actually is and then we'll think more about how we might actually transform from a regular expression into a finite autoin and why that might make it fast for us to check if a particular string is going to match a particular token kind。

So let's go ahead and the highlights and componentss here。

 So first let let's note that we've got a finite set of states。

 These are all represented with these little circles that we see right here。 In fact。

 in some places you'll see them written out with little names so you might see S1 and S2。

 maybe SF or S final So we have our set of states。 those are all represented with those circles。

 Let's go ahead and also represent the finite set of input symbols and it is important。

 but this is finite So we can go ahead and see A or B or C or D。

 and that will move us between states right if we're reading from a string and we see a next character fantastic that might move us from one of these circles to another right so say that I'm here to start the next character in my string is an a fantastic I am now an S2 instead。

And now。We can go ahead and notice that the thing that I just showed us following is a transition right It maps a given state and an input symbol to another state。

 So if we see an A， we move between S1 and S2， if we're S2 and we see a B。

 we move to SF and we can see that all of these are transitions that are available。

We also have a start state。 So if you see right here。

 this little arrow pointing in that is representing that that is the start state。

 So let's go ahead and circle that。 And we also have an accepteding state。 So here again。

 let's focus on one of these sort of smaller marks， we can see there's this double circle around SF。

 that indicates that it is the accepting state， meaningan if we land there。

 we have accepted or recognized the input。 If we land anywhere else， we have not。

Are there questions right now about how to read a finite automaton。

 it's okay if we don't yet see how it is equivalent to a regular expression。してられ。exact。

I think I understand this question。 I'm gonna try to explain it with an example。

 So this question was， what do you mean by landing in something other than an accepting state。

 So let me go ahead and give an example of a string that would land us in an accepting straight accepting state and then the opposite。

 So if we have A， B， D， D D， Let's sort of trace through what would happen right。

 We start at S1 because that's our start state right， we can see that little arrow。 We start at S1。

 We see an A fantastic。 We move to S2 from S2。 we can see a B fantastic。

 We move to S F And now we've got these3 Ds。 That's fine。 we can keep going through。

 And then we land at this circle that has the double circle。 fantastic。

 This is a string that we are going to accept。 On the other hand， say I see the string C， B。

Right so at first， things are kind of looking good， right I jump straight to SF。

 that's an accepting state。 Things are looking good so far。 but now suddenly I've got a be right。

 I can't go anywhere right so implicitly I'm moving off to some rejection state。

 And so that means that this string would be rejected。 So let me go ahead and mark that as nope。

Does that make sense yeah？I'm so glad you asked， well。

 it turns out because we are so interested in figuring out very rapidly whether a given regular expression can be matched with a given string the right way for us to do this is to go ahead and develop the finite automaton that corresponds to our target regular expression and I'm going to sort of quickly talk through the intuition for y and then we'll talk more about this correspondence So the intuition for y is basically exactly the process we just followed when we were checking these strings at every step we know exactly what to do and if at any point we hit this case like we hit right here where there is no edge out。

 we know we're done and we can just quit at that point So this is a linear scan of the string we never sort of move backwards in here。

 we never tried backtracking we just move forwards all the way。 And so in fact。

 something I didn't highlight earlier when we were talking about regular expressions is you might have seen some sort of libraries that called themselves regular expression libraries that allow you to do things。

😊，Other than the things that I talked us through right so there's sort of these things that are the core and then there are these other things that you can build on top of those with only these implemented。

 you can always get a linear scan。If people start doing things that sort of allow backtracking and all that kind of thing。

 you might see that in libraries that call themselves regular expression libraries。

 but if they give up backtracking， we lose this property that we care about for the purposes of tokenization。

 and it actually goes outside a regular expression to something called re Xs。

So we're going be we're going to set those aside and we're just going to think about the things that we can。

 in fact， convert into these finite automaa。And basically。

 the process that we're going to end up using is the process that we followed right here where we're just sort of saying。

 okay， let me mechanically check whether each string is bringing me to a good state or a bad state。

 If I've gone to a bad state， that's it。 I'm going to go on and try for the next token tank。

So hopefully that makes sense of why， yeah， Okay， great。 So fantastic。

 Now we know why we are interested in getting these finite automata。

 It is because we are interested in being able to do that linear scan in order to figure out if something is appropriate for a given kind of token。

 And now we have to figure out how can we actually make the appropriate finite automata。😊，So， here。

We're going go ahead and talk through how we can do this process again completely mechanically。

 right， We don't have to use any creativity to do this process。

 We can just apply these steps that we see here。 And then we're to turn any regular expression into a finiteatma。

 So let's talk it through real quick。 This one is pretty boring。 right。

 This is basically just saying， Okay， if we have the expression M。

 And that's what we're looking to get。 fantastic， let's have M sort of be the thing that we're expecting to see。

 And the thing that should come out the other end is you know， if we have seen M。

 we get to go ahead to that accepting state。 we'll start at the start。😊。

If we are looking to have this will be relevant for later。

 if we are looking to have a nondeterministic finiteatma。

 that's what NFA stands for for the empty string， fantastic。

 we'll just expect expect the empty string to appear on that transition。

 If we want to see the literal character A fantastic。

 we're going to have the character A marked there So this is sort of just telling us sort of syntax about how we're going to write things。

 and this is going ahead and telling us how were going to construct a concrete nondeterministic finite automa。

😊，And now we get into the interesting stuff， right， So here we're seeing for concatenation。

 how can we mechanically produce the NA that is going to actually correspond to a followed by B。

 right And so it's just whatever was the end state for a。

 the accepting state for a right right there。 We're going go ahead and use an epsilon transition。

 Right， So an empty string transition to the start state of B， right。

 And then we're going to go ahead and expect that the original or sorry。

 the original accepting state for B is going to be our accepting state for A B combined together。

 This is a great point for questions because I know this is sort of wacky to think about。

Are we feeling pretty comfortable so far about sort of the。Structure we're using。非常大。

I think this question might be twofold。 So one part of this question seems to be。

 say we're given a regular expression。 Are we expected to be able to construct a finite automaa。

 And yes， right， like that is why we are covering this thing right here is to be able to do that？

 But I think there was maybe another part of your question， which was， hey。

 are we gonna be expected to be able to construct a deterministic finiteatmaa because you can see that what we're actually building here is nondeministic finiteatmata。

 So the epsilon， for example， is。Not totally sure I understand the question。

 I think it's if I give you a regular expression， are you going to be expected to be able to apply these rules to construct a fine autoa。

 And the answer to that is yes。Regular language。Yes， NFs。

 DFAs and regular expressions can all express regular languages。

 That is the category of things that they can express。Yes， yes。

 So this part of this particular direction of the conversion is what we're expecting you to be able to do。

 right， We want you to be able to go from a regular expression to a nondeterministic finiteatmata。

 We used to have a version of this lecture that also covered convertoring from a determin sorry。

 a nondeterministic phatmata into a deterministic automata。

 But it turns out it's actually pretty straightforward once you get the core insight going from an NFA to a DfaA is basically just okay。

 say I'm in state 1。 And I have one node S2。 And if I follow this character。

 I could go to either S2 or S3。 Then you basically just make in the new nondeterministic。

In the new deterministic finite automata， you make S1， go to a new state that represents S2 or S3。

 And you just keep going through that process for all of them。

 So once you sort of get that core insight， it's not that exciting to think about going from a nondeterministic finite automaa to a deterministic finite automata。

So the version that we are going to expect you to think about is this one that's on the slide。Ts up。

Yeah， but we do expect you to sort of be able to think through， okay。

 here's how we would apply these rules in order to transform a regular expression into finer。

And in fact， we're going to practice that in just a moment。So， okay。

Let's now talk through the one for or。 again， I don't think once you sort of see it。

 it's going to be super surprising how we do this， right， we go ahead。

 we have our sort of enter state， our start state， and we can go either to the B route or to the A route。

 Again， this is getting at how this is nondeterministic right So up here what we showed was okay。

 we're always going know which one to follow if we see an A will' go there if we see a C will go there。

 if we see anything else we're in the error state。 But here。Or me。If we see here。

 it's actually not so clear， we can't just read off the character and know whether to go this way or that way because we're allowing this empty string。

 so that's one of the reasons why we might then want to have that later step of going ahead and making it deterministic plan at a time time。

Okay， great。 So if we've got the regular expression for B， fantastic that can be up here。

 if we got the one for a， fantastic that can be down here。

 and then we sort of have to bind them back together again， we have our empty string transition。

 another empty string transition and we get the accepting state at the end。

 And then I think the clean star1 is actually the most interesting here。

 So it's basically just saying， okay we'll have our start state being this epsilon thing or sorry being this sort of outside of the thing and then we'll connect it with an epsilon transition into a the accepting state for a should turn into an nonaccepting state and put us back here and then we should go ahead and have our epsilon transition going all the way to the start state so that we are allowed to go back at any if we never go through a it's still okay for us to jump straight to the accept。

😊，So far， so good。You'll notice that some of this stuff looks a little bit extra when we're just looking at it here。

 like why did we have to have this be separate from this。

 but once we actually get to the point of having large， complicated regular expressions inside this。

 you will see why we want that。And this actually covers all of the things that we talked about when we talked about the grammar of regular expression。

 so here's concatenation， here's oing， here's clean star。So hopefully we're feeling good about that。

Are we ready to practice doing this process？Yeah。The higher level。Ex not。

The epsilon transitions are so confusing because it means that it is nondeterministic。

 right So all of a sudden say we're here， right， we can go this path or we can go this path。

 And so if we just implemented this as nondeterministic finiteata in order to do our tokenization。

 we would potentially have to do backtracking this is exactly what we want to avoid。

 And so in practice， when we were actually using this kind of technology in order to do tokenization。

 we would go through that process of converting from a nondeterministic finiteat into a deterministic finitea so we could just read off each character。

Exactly right。Yeah， we should think of it as basically a two stage process。

 This is our sort of mechanical way of going from a regular expression to a nondeterministic finite automaa。

 Once we have a nondeterministic finite automaa representation。

 we can do that process that I talked about before of building up new nodes that represent sort of sets of nodes that we could have reached with the same character。

 And that's going to go ahead and be how we do that transition from non-deterministic finitemaa to deterministic。

So right now we're only thinking about that first stage in that row。咁。All right。

 if you have notebook paper， if you have an iPad， now is your time to take it out。

 what we're gonna try to do is build up。The nondeterministic finite an automata for this regular expression。

I know it's gonna feel really annoying to actually follow these rules mechanically of doing sort of the epsilon transition in between。

 It's gonna to feel like， oh， okay， like I know I don't need that。 But for this time。

 go ahead and try to just do it in that mechanical way because we want to have the automatic process of generating this。

 We don't want to have to think about it。 be creative about it。 We want this to be automatic。

Do feel free to work together with folkss nearby。Feel free to call me over with any questions。

Home if you feel ready。Home if you want more time。Okay， let's go ahead and see it。So here we go。

 I think really it gets exciting around this portion right we can see that for the most part。

 what we're doing all the way through here is just we've got our little start。

 we've got one of the characters， we have our little epsilon transition to B right just our empty string。

 And so if we go ahead and we have you know O blood D going in。

 we can go follow way in and then we get to the interesting part so we either have the option to go the I branch or the a branch and then we have an epsilon transition out the end until we get to that last character if we follow that last character。

 we get to the accepting state。😊，Are there questions about this or does this more or less look like what you wrote？

Why are we using the extra epsilon for the exclamation mark， And I think， in fact。

 you could ask that anywhere here， right， Why do we need this epsilon here， Why do we need that here。

 Why do we need that here， There's all these places where we're adding it。

 And it's just because we are mechanically following this rule for how to implement concatenation。

 And yes， absolutely， we could use our sort of human knowledge of this problem and look at this particular setting and say。

 okay， I'm looking at this。 and I know I don't need this epsilon transition， I could get rid of that。

 But because we want to be able to construct this purely automatically with no need for us to reason。

 We're just sort of following these rules in a purely automatic way。Yeah great question。外。

Why isn't there an epsilon between the D and the or， Should there be， Maybe there should be。

 So it looks like right here， we're expecting that whatever our original start say is。

 we're going go ahead and have empty string， empty string transition for both。And right now。

 this was the start sorry， this was the accepting condition for D。

 So our next step would be to have that E or E。 That looks okay to me。Does that answer the question？

Oh， maybe you're right。 I might have missed one。 Let me draw myself a note， and I'll take a look。

 reasona through more closely， should。Be extra。Alright。

 so I'm gonna have us go through one more of these before。 Oh， sorry。

 were there other questions before we move on。Okay， great。 So let's think through one more。

 The first thing we're gonna do is we're gonna actually test our understanding of this one because this one's a little more complicated。

 We've got some clean stars coming in， and then we will again go through that process of writing out the nondeterministic finite automaa for this。

 So here we go。 We've got our sort of Hadjued lyrics  one。 So let's try it out on this one。

 at the end， I'm going to ask you to hum for whether this is actually accepted。😊。

Discuss for 20 seconds。All right， how if we think accepted。How if we think rejected？Unsure yet。

 keep chatting。It's okay to be wrong， but we do have to commit。All right， how if we think yes。

If we think no。AndThat looks like okay I think that looks like a yes right so if we take a look through what was happening right we can see we've got sort of a no that looks like that this is optional we can have zero at the end of there right it's okay for that to be zero and then we have the option to have either an empty string or a space so we're seeing some spaces there and then we do that however many times we want and then we have the string Had you。

😊，Looks good to me。 What about this next one。20 seconds。Hum for accept。Hum for reject。Fantastic。

 I'm on the same page that looks fine to me。 what about the next one hum for except？Home for reject。

Yeah， as not was it to reject， right， What about this one。Hum for accept。Hum for reject？Yeah。

 I agree， right， We're expecting to have that。 There's not appearing there。 fantastic。

 That is going to be a reject。 How about this one， discuss for 10 seconds。😊，Hum for accept。

Hum for reject。All right， same page。 This one's a little bit interesting。Home for accept。Yeah， okay。

 same page right， This is gonna go ahead。 It doesn't require that we have any of those。

 we don't have the plus。 we just have the star。 so that looks totally fine。

 What about this discuss for 10 seconds。Hum for accept。H for reject。I agree。

 This looks like right we can go ahead and take that no space。

 And so this is totally fine to get those mashed together。 So okay， we've gotten that together。

 let's go ahead and spend our last two minutes。 It probably won't be enough to quite make the NFA for this。

 but that's okay。 I'll show the completed version at the beginning of next class and we'll go on from there If you want to just work on drawing this right now fantasticantastic if you have questions。

 feel free to raise your hand。😊，Ex on or。上にえまし。For this， can you give me that again？や。It's this one。

 I think。Oh， if we replace this with a space with a clean start， it would be okay。

 except we'd be allowed to have more than one space。Now。Is that okay with us。

 maybe that's okay with us？We need any。Oh， you're thinking。

 what if we then sort of we went through this and we could use that in order to get multiple spaces anyway。

 We actually can't because we're always going to have at least that N。Yeah， no， great question。包我嚟嘅。

Are there any forbidden characters so。In regular expressions， the concept， no。

 in particular library implementations， Yes， absolutely right。

 So like it's sort of up to us how we might choose to implement this。

 like maybe we choose to not even write it out this way。

 like we don't have to write it out the way we've been writing it out with our grammar。

 like there's all kinds of options for what a given implementation is going to do。Yeah。

 it sort of depends on what rule you are using， we're actually next session we're going to play around with using just the regular expression matchcher in VS code。

 so bring your laptops next time and we'll play around with that。Yeah。おスペー。Oh yeah。

 so if you remember the way we actually sort of defined question mark。

 remember question mark we can just build， right， this is sort of in our allowable。

 this is actually still a regular expression because it's all still the same。And a more。那你放一点。

You can。P的 was。Yeah， so this is basically this is showing us how we would use the things that are in the core in order to implement these right so we could just replace this with that。

 we could go the other way around as well， we've been writing everything out in the core grammar。



![](img/0051c4dd32cce33b384944ce9be6a103_13.png)