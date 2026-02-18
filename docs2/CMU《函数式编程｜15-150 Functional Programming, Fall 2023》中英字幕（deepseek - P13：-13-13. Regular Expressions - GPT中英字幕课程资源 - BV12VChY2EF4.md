# CMU《函数式编程｜15-150 Functional Programming, Fall 2023》中英字幕（deepseek - P13：-13-13. Regular Expressions - GPT中英字幕课程资源 - BV12VChY2EF4

喂い。Cool okayWecome to lecture 13 Today we're talking about regular expressions。

 which are a pretty cool thing that have a lot of both theoretical and practical applications。

 So what we're gonna to talk about here is that regular expressions are kind of a nice use case for functional programming and a really important thing in computer science this might be one of the most practical things you learn So all right we're gonna to talk first about this problem of text validation and the idea is that we want to validate user input This is something that happens all the time you read input from a user。

 you want to make sure that it's not dangerous because you might get an input。

 put it into your database and then run that and then later find out that someone gave you input that was specifically made to crash your system So we want to stop that from happening so we want to validate it。

😊，In particular， let's think about as if we want to find usernames web or email addresses rather。😡。

And the structure of an email address is going to look like this。 It'll be name， append or at。

Ex website。The name of the website。and then dot an extension okay and that's the structure of an email and we want to take that and then make a function called validate email that takes on a string and tells us whether or not it adheres to this specification if it's a valid email address and this is dependent on a few things which is we need to know what a valid name。

 website and extension are。😊，So I'm going to give the specification for that now。

 but let's assume that a name or rather an extension can only be org or calm okay so our email addresses can only end with。

org or。com Furthermore， assume that a website has to be only alpha numeric characters that is all of the alphabettic characters and all of the numerical characters。

😊，And then assume that aname has the same condition。

 it needs to be fully alphanumeric plus underscores and plus periods。

 so that they're kind of similar， but not exactly the same。😊，To fully implement this function。

 we're going to define some functions called consumer functions。

 and the idea behind consumer functions is if you give me an email。😊，if they give me my work email。

 then I want to take off。I want to turn this string into a character list。

 and I want to pop off characters that match my thing I'm trying to validate that thing I'm trying to consume。

 So if I'm trying to consume names， well names can be any sequence of alpha numeric characters so I would take off all of the B。

😊，We are A and D O N， until I get to this。Append at which point I would say， oh。

 that that's not a name。 So I's stop。 So we're going to define a function that does that。 Okay。

 so we're gonna to have two functions called consume name and consume website。

 Con name is going to evaluate the ss。 That is like， if I have my entire character list。

I can put a line in the middle， and this is my suffix that satisfies this。

 my suffix is anything that's not。😡，Part of the name， I take off the prefix。

 I take off characters until they no longer satisfy the name， and then for consumer website。

 I just take off characters that match the website okay。😡。

And I'm not gonna to write it on the board for you， but here's how we can implement it。

 If I consume name， I check it's a reclusive function if it's empty， I can't take anything off。

 so I return the empty list if it's C con C's if the C is alphanumeric I take it off and I continue to consume on the suffix otherwise if C is either dot or underscore I also do the same thing I take it off and I consume otherwise if it's none of those things well like if it's append if it's at then I stop in my tracks and I leave the whole thing because I can't consume anymore so once I've done that I'm done and then for consume website it's the exact same but now we don't allow dot or underscore so all we do is we consume all of the alphanumeric characters from the front until we see something separate okay。

😊，That's all we're doing。Finally， we're going to write our validate email function and I'm not going write it out again。

 but here's what it's doing recall the string explode function that takes the string and turns it into a character list so I take my string I turn it into a character list and I consume all of the characters that could be a name from the front so I take off BRA and DN and I'm left with this and I case on that if I have at and something else well I take the at off and I get Cs and then I consume website on it so I take this off。

😊，And then I take off S， EM GR， EP until I see a dot at which point I say， well， okay。😡。

I'm done do I have doorg on the front of what's left or do I have dotcom Well this is docom so we just pattern match on the first four characters of my character list that remains and then I get true and if any of those conditions were false then validate email fails because it doesn't look like an email okay。

😡，And that's how we validate an email， except there's a little bit of a problem here， okay。

This is not quite right， there is a bug because what if I put a bunch of random nonsense at the end。

 like I said， docom ASDF。Well， this is not a valid email according to our specification。😊。

This is not a valid email， but it will pattern match to this right we will get that this will match because the end is just a wild card。

 We want to make sure that'll be end with。org。com So we're going to make it just the list of。orgon。

com。😊，After we do that， now we're done， this is how we validate an email via this process of taking things off the front。

 okay so we make sure the extension is the last thing。😊，Well。

 okay this is what we call a hand rolled function as in I had to manually write this validate email function for you and while you're like relatively sure it works。

 we still had a bug， we had a bug we didn't know about right So what we want to do is we want to avoid that because this is tedious to write it was really manually constructed and it wasn't easy to do or rather it was easy to do but it was easy to get wrong so we don't want that to happen if we ever write code we have a potential for problems So the idea our mantra is more code more problems So let's try to have less code okay。

😊，And this， this model might be as similar because we might be interested in a bunch of problems that look like this。

 Suppose we're interested in。Phone numbers。 that's like something。

 three things and then four things or three things and then four things again， right。

 So like this is a kind of a similar problem where we need to consume input。

 But every one of these functions we write， it's ugly， it's tedious and it sucks to do。

 So let's not do it。 Okay， let's try to automate this process。😊。

So what we're going to do what we're going to do is we're going to write a function that takes in some type and then produces to us one of these validation functions。

 we're going to try and encode this validation problem in a value of some type and that type will be called the type of regular expressions okay。

😊，So we're looking for like the essence of a string validation problem。

 and we're going to turn it into something called a rex。😊，Okay so part two。

 this is where I tell you about what regular expressions are I always like to think about it in terms of these two xACDs。

 The idea is there's this one where basically these two people need to look through 200 MBn emails to find something that looks like an address and then Randaall Monroe swings in on a Tazan swing and then says he knows regular expression and he solves it and that's perfectly fine that's kind of that's kind of what you'll be able to do sort of after this lecture and the second thing is also a similar one where this guys got 99 problems so he uses regular expressions and then now he has 100 problems it's easy to use regular expressions raw but thankfully we're not gonna be using regular expressions we're going to be learning about how they work okay。

😊，So PC RE stands for pearl compatible regular expressions。

 it's an old library for regular expressions and a syntax for regular expressions and we're going to take that and we're going to drop the PC because we don't have time for it we're just interested in the regular expressions we're going to learn about the theory behind it which means that basically lecture after this lecture you're not going to know how to write regular expressions you're not going to know how to use them but you will know how they work and that's the most important part okay so that's the idea of this lecture okay。

😊，嗯。Here's the idea。 what it makes up a validator， what is a validator to be a validator for a particular thing。

 I want to be able to do a few things。 In particular。

 I should be able to concatenate two things I'm looking for together。

 Like how I say I want to name and then I want an a pen。 That's called concatetnation。

 I want to be able to do one thing and then put that nest to another。Alternation。

 which means I want one of two things， I want to be able to match either。org or docom。

 both of those need to be one of those needs to be true， I don't care which so one of either。😡。

And then finally iteration， I should be able to match a pattern。

 but as much as I possibly can because I need to match a website， for instance。

 I needed to be able to match an alpha numeric character any number of times so we iterated basically we said give me an alpha numeric character and take off consume an alpha numeric character any number of times so these three things are going to boil down the essence of what we want in a validator。

😡，And this should seem like a recursive definition because it is okay so let's describe what the mathematical definition of a regular expression is and here's the idea we're going to introduce a few key ideas but central to it is going to be this thing we're going to have alphabets。

😊，An alphabet。It is a type car list， it's a set of characters。

 we not it capital Sigma and capital Sigma might be。A comma B， for instance。

 and this is just the alphabet of characters that we're interested in strings over。😊。

And we're going to have strings。Which I have type string in SML。

 so a string over this particular alphabet might be A， it might be A B BA。It might be BBB。

 These are all valid strings。 We also have the empty string， which is possible。

 So we can't really draw that， so we notate it epsilon。Okay。

And these strings also need to be finite in length， okay。

 we're only interested in finite length strings。Furthermore。

Let's introduce a concept called Sigma star。If I have an alphabet sigma and I take the star of it。

 this is of type。😡，String list。And this is equal to all strings。Over sigma。

So if I wanted to take the star of the alphabet A comma B， which is our toy。

Alphabet of choice for today， I would get that this language。

 this or rather this sigma star is going to be the set of firstly the empty strain。😡，And then A。

 and then B， and then A， A， and then A， B， and then B， A， and then B，B， and so on and so forth。

 it'll be every finite length string that could be composed of A and B。

 which includes the empty string， that's what we called sigma star okay。😊，And finally。

 we have a notion of languages， a language。Is also of type string list。

 but a language is a particular subset， a collection of these things that we're interested in。😡。

So L is a subset of sigma star， and what I mean by that is we can highlight a certain number of these things in Sigma S that we're interested in。

And these formal language so our language might be epsilon and then B and then A B and BB and nothing else。

 but this is a subset of all possible strings， a language is just the strings over the alphabet in particular we're concerned with that we're interested in only these strings that were interested in this is a lot of basis in like formal language theory and computerutability。

 computerical computer science， but the point of having this is just that we're saying that certain strings we're interested in we want a validator that says true only if it's a string in the language so a particular one example of a language we might be interested in。

😊，And ignore this for a second， one example of a language we might be interested in in the context of our email matching problem。

We might be interested in。L。Well， where L is equal to all email addresses， this is a valid language。

 and it's a language because。The string。ABA。Is not in this language because it's not a valid email。

 So when we talk about validators and let me move forward a bit here。😡，When we talk about。

Validators were interested in a function F that checks for membership within the language。

 so a function F from string to blue is a validator if it returns true。

 only if if and only if the input it gets is in the language and otherwise it returns false。

 we usually require that these functions are total okay。😊，It turns out that via this specification。

 regular expressions are what lets us kind of achieve these validators。

 it's what lets us implement them very very neatly and very compactly succinctly write we can't match every language using regular expressions。

 but in practice a lot of them we can okay。😡，That's the point of this。

So let's define the structure of a regular expression。

So if I have the structure of regular expression， it's just going to be these things okay and I'm going to give you the mathematical notation。

 but it's not going to matter super much here， it'll look like math， but this is just notation okay。

😊，We say a regular expression。R。Is one of six things。It is zero， which is a symbol， it's not math。

 it's not zero the number， it's just a symbol， it's a special regular expression 1 or0。

 We also have the regular expression 1。😊，We also have the regular expression C。😡，Where' C。Well。

 rather for any C that's in our alphabet。Okay。And then finally。Where R1 and R2？

Are regular expressions themselves？We have the regular expression R1 plus R2。And again。

 these look like math， but I'm going to give you the meaning in a second here。

 I'm just going to define the syntax key right now， Okay， R1 plus r2 is one。😊，Then R1 R2。

 which is the concatenation， or rather the justtaupposition of R1 and R2。

 we just put them next to each other。😡，And finally， R star。

 which is called the Cly closure or the Clany star rather， the Clany star of R， okay。

 so we call it R star。😡，And this is just the syntax of a regular expression。

 these are the six things that a regular expression can be。😊。

And note that it's recursive because a regular expression might be composed of other regular expressions。

😊，If this looks to you look at data type declaration。

 that's because soon we're going to define it as such， okay。😊。



![](img/d6da4301e56d56b7be85322e5d149cc0_1.png)

![](img/d6da4301e56d56b7be85322e5d149cc0_2.png)

If you're thinking code， this should help。and then the language of the regular expression C is the language that has just the string C in it。

 because there could be a string that has exactly one character in it。😊，So it's going to be this。

 Remember， strings can be any length， but it can also in particular be length 1。 Okay。

 So this will be Fn。Well， this is harder to phrase in SM。

 we're going to say like like quotation marks C， but this would actually no。

 this is perfectly fine to say what we're talking about。😊，Okay。

Like as in the singleton string of containing just C， so like for instance。

 if this was literally L of C， the character of C。😊。

This would literally be the lambda that you write to validate the language。

 it would take in the singleington string C。😡，Answ there a question， yeah。我在。Mty string， No。

 this is just C。That's the regular expression and then R1 plus R2 is going to be。😊，R。

If R is in L of or sorry， S。If s is in L of r1 or。S is in L of R2。

I'm not going to write a lambda for this one。OkaySo r1 plus r2 means it can come from either regular expression what does that sound like alternation if I have one of two regular expressions I want to match I might have one regular expression for doorg。

 I might have one regular expression for docom if I plus them together now I have a regular expression for my extensions okay。

😡，And then you might have a guess for what these last two things are based on that。

R1 R2 is going to look the same actually， it's going to be S1。😡，S2 for S1 in L of R1。

And S2 and L of R2。And when I write S1 S2 I mean the concatenation of two strings like I could write string of concat2 here like S1 append S2 right or carrot but this is what it means it just means take two strings from either language and shove them the other so for instance。

 if I wanted to do this I might do this for my append regular expression and my name regular expression and I would get one regular expression that's the name and the append okay。

😊，And then finally， this one's a little harder to describe。But it's going look like this。

Let me think of the right quantification here。呃。S1， S2， d do SN。Where。From I plus equal to Nops。

S sub I is N L of R。N greater than equal to0。So what R star means is I take a string in R star。

 any string in Rar， any number of those strings， and I shove them together， I put them together。

 that means I repeat a string in R star any number of times it doesn't need to be the same string okay so that means that if I want for instance。

😡，Literally I a。Actually we'll get some examples in a second but the point is that I'm going to take some strings in R and then repeat them any number of times and I might do it zero times in particular so that means the empty string is always in this language it's okay if you don't get the findr points right now that's kind of like a harder thing to remember all right。

😊，Oh yeah， I can also just write that， but yeah， whatever。Yeah。

 another way to write this is that this is just the union of their languages okay。😊，Okay。

 any questions on this， this is just a mathematical definition we'll go through some examples right now。

😊，Okay。Oh yeah， and then in English in English please， so L of C is only C L of0 is nothing。

 L of1 is only the empty string。 L of R1 plus R2 is anything matched by either of my subreg expressions。

😊，L of R1 and R2 is any string S。That can be split。😡，Into two parts， a prefix and a suffix。

Such that the prefix comes from R1。😡，And the suffix comes from R2。😡，That's what it means。

 any string that looks like this。😡，And then LR star means any string that's something matched by R。

 but zero or more times， we also call it gllay closure。😡，After Stephen Planey。Stepeven Doulraney？

He was a lieutenant commander in the US Navy I learned。

 so he came first and now we are here to study him， so this is a regular fashion， okay？😊。

Now we're going to look at some examples，😊，So in this case。

 suppose that we're interested in just the alphabet a comma B。

If I have the regular expression A plus B， remember we can do that because A and B are both regular expressions。

My language is going to be literally just A and B right if I've A B A A where you know A B AA means concatenated a bunch of times regular expressions plus B A A。

 my language is again just those two things Okay if I have A B A A plus B A A the previous thing and then that whole thing parenthesize and then concatenated with B。

 then I get everything in the previous language， but also it has a B at the end。

 it has to have a B at the end。 that means that A B AA no longer appears in this language okay。😊。

If I have0 plus a， I get a。 If I have1 plus A， I get epsilon and a。And then if I have a star。

 that means epsilon， A A A， AAA， every string that might be something in this language one or more times or zero more times。

 Yeah， whats there a question？😊，These everything to the left and right of a plus is a regular expression。

 in fact， every fundamental unit here。😡，Except for the parentheses。

 all themselves regular expressions， that means that a is a regular expression。

 B is a regular expression in here， B A in the middle here is also a regular expression。

 we're just putting them together， we're jamming the together。😊，No， because this is concatetnation。

 When you concate something， you take something and you transform into something else。

 That means that， for instance， if I had a。L of a。Do you agree with this？

Then if I take this language and I。Put a B at the end。

 I take everything in here and I put a B at the end。So for instance。

es if I had no pluses and no stars involved， it would just be everything in there， okay？All right。

 these are the examples that you're supposed to understand now， hopefully。

 so if you don't any questions。😊，Or I can do a more involved example if you'd like。Yeah。Yes。

 of course， okay， AB， sorry， that's a good one。😊，ABAB Preenser or AB。AAPn B star。Like。This or this。

These are two different regular expressions。 Actually， let's do both。

's let me illustrate the difference here because that'll help Okay。

 so these two regular expressions I claim to you。😊，Are different。 Here's why。AB star means， okay。

 so first of all， what is the language of AB？😡，Just a遍。I just answered it for you。

The language of AB is just the string AB， right so that means that the language of this thing stard means I take anything in that language that is AB。

 and I repeat it zero or more times。😡，So the zero case is epsilon， the empty string， right。

 the one case is A B。But my question you is then can I put A B in this language， Well。

 A B is in the language， but A is not so this is not something in there zero more times。

 so in fact AB is not in this language it will be。😡，ABAB。And then A， B， A， B， A B。

 it'll be finite repetitions of the string A B， Okay so it will always be even in length Okay All right。

 is that there， but this one down here is different。 So what is the string in the language of A。

 it's a， the string A。😊，But what's the language of B star。

 the language of B star is going to be anything in B repeated zero or more times。

 so let me make it very explicit。😡，L of a is equal to the set A。L of B star？

Is equal to epsilon if I repeat B0 times。And then one time， and then two times， and then three times。

 so on and so forth。So if I concatet these together。

 I take every string in here and I put A in front of it。😡，So my result。Is going to be？AB啊 sorryA。AB。

A， BB。ABBB。Dot do do。Yes。The full sigma star over yes， over A and B， yes。Yeah嗯。

I will move on from this shortly because this stuff doesn't matter super much， but yeah。

 that's a good question so。Well。Oh my god， how did they get it for there？Cool， yeah， you said zero。

 who said that， zero， what？Yes。So in this case， what we do is we take every string in here and we cancateate it to every string in here。

 but how many strings are in here？Z， so this is going to be the empty string。sorry， it empty。

 but this is a。And now we've come across why they're called plus in times because it zero is a multiplicative。

😡，Killer。And then one is the multiplicative identity。

And then zero is the additive identity and so forth。

 it doesn't really matter there's a cool midterm review problem I made about this at one point。

 I don't know if we're still running it。😊，Yes， this is examples okay if everyone gets kind of what's going on here。

 we're going to move on just to get a flavor of intuition for a yes。😊，Language for A B star， A。

 which one the。Yeah， this one。So yes this language is AB repeated any number of times。😡，Oh yes。

 the language for the subregular question here is just AB。For this。Thatll be this， actually。一。Yeah。

 so as a recursive definition， we rely on what the language of the thing immediately prior is， yep。

 yep， good question。😊，I was gonna Okay， let's move on。

 These are I realize you've had enough fun of hearing me say A B A A A BBB over number again。

 but we're gonna move that。 hopefully it'll get better。 Allright。

 I just stuffed a bunch of math in your brains。 Why are we here。 What's going on。

 What are we doing this for The reason why we're doing this is because this formalism here is going to be a very useful thing for really specifying any language that we're almost every language we're interested in these regular expressions are composable。

 that means that if I have a regular expression I'm interested in。

 I can just take it and shove something in front of it。

 And now I have a new regular expression that does something moderately similar。

 Okay and composibility is really cool because now I can upgrade my email rees to emails that maybe have like an H TTPS at the front。

 So and so forth right So this is gonna be really useful for reuse and for kind of just conceptually understanding what these do。

😊，So if I wanted to write a regular expression for the email thing I was talking about。😊。

Let a of A N be the regular expression that matches all alphaianmer characters。

 You could write it as a plus B plus dot do dot plus z plus 1 plus 2 plus dot do dot plus 0。

 you could literally manually write it out that way。😊，Then an email would be。😡。

Alpha numeric character plus dot plus underscore and remember that plus means or here。

 so alpha numeric or plus or sorry or dot or underscore and that any number of times hence I have my clany closure here。

 my star and then I must see in a pen so I can count it and then I must see an alpha numeric character any number of times again。

😡，Then I must see a dot。😡，And then I can see either work or come。😡，Okay。

worth noting this definition also permits empty names and emails， but it's whatever。

 it would be a lot of pain to rectify that。ok。You would just repeat it and then put it to the left of it。

Yeah， except without the start。Yeah， does everyone see why this is a regular expression for the email example I gave at the beginning of a lecture？

😊，Just any number of these characters， append any number of these characters， and then doorg。

com okay。😊，Okay。Okay， I think we're going to move on that。Oh shoot， that was not the end。

 Okay another interesting fact is that we can use radio expressions with these things called finite sa machines and I'm going to skip over all this。

 but basically if I have a regular expression A B plus B， I can represent it with a graph like this。

's a it's a machine that reads input basically means that you start here。😊，And if I read an A。

 I go to here and then if I read a B， I go to here and then this circle around here means it's an accepting state。

 it means that if I ever end up here and I'm out of input I'm good I'm done and correspondingly if I'm in the starting state and I read B and then I read A I'm in the accepting state okay this is just a way of reading some input and then trying to teach see whether or not it's accepted and there's a correspondence here where you can always find one of these DfaA as we call them for any regular expression okay。

😡，O。Yeah， so I'm just going to run you through the example of fast。

 which is that if I wanted to put AB into this，😊，I start here。😡。

And my remaining input is just the string AB， I haven't read anything yet， I just started。

Then I gave it A， so I go here。😡，And now I have B left now I read B so I go here and I'm out of input。

 so now I end up here， this is my final destination。

 so I accept that means that A B is in the string of this machine guy if I given it A B A。

 that means that I would have done A。😡，B。And if there are no arrows。

 it means that you fall off the edge of the world， you fall off the map。

 and that means you die so if I gave it ABA， I would have nowhere to go。

 I fall off the map and I die and then I don't accept。😡，Fair enough for brevity。

 we usually don't write that okay so this is an automaton that accepts literally only just ABA or sorry。

 A B and BA。😡，And A itself， if I just gave A， that is if I ended up here。😊。

This would not be accepting because it's not circled。Okay， all right。

 this is just to give you some intuition and then hopefully if you get that intuition。

 I'm going to tell you that this is a regular expression， a automaton for this regular expression。

 meaning that any number of A's， because if I read an A I go back， so I go A A A A A。😊。

And then precisely two B's and then any number of A's。

 so the things in this language might be like I don't' enough space to write down。

 but basically this would accept any string that's A's and then two b's in the middle。

 and that's it okay。😊，And you can read over this on your own。

 but I'm going to let you go to the quiz。All right， get up。Okay。

We're going to move on to implementing this， I gave you all the math， we're going to put it in code。

 I promise you 10 to 12 lines generous white space it's going to be pretty simple al right but all all this notation。

 all this mathematical stuff is just to cement your understanding of what the hell the code is actually doing so now we're going to talk about matching regular expressions。

😡，So we saw that if we have this DFA we can kind of already match it if we have the DFA we just like go through the DFA and then until we reach and or we run out of input。

 it turns out it's actually pretty involved to produce a DFA from a regular expression but that is what people do we're not going to go that route instead what we're going to do is we're going to straight up decompose on the regular expression sorry the other thing I want to say to you is there's this guy called Russ Cox I think he works at Google。

 basically he implemented Google's R2 library which is like one of the best like most standard regular expression libraries out there and he kind of commented this thing I thought was super great about how regular expressions are like where theory meets practice it's one of the best examples of where good theory leads a good practice everything I told you about this theory is what they actually do it's what actually happens because this theory if not for it people would be solving regular expressions in a really dumb way。

😊，That goes from 900 milliseconds to 90 microseconds。

 I believe the figure was in terms of matching length。

 Okay so I that's kind of my motivation for you here， which is that like good theory。

 good practice programmatic thinking is mathematical thinking okay so let's get into it。😊。

We are interested in this data type， which I will write up for you in SML。

 okay I gave it to you in terms of math， but now we're going to do it in SM okay so if I have a regular expression。

 it's either zero。😡，Or it's one。Or it's a construct car。Given an actual SML character。

 or it's going to be plus。😡，Of two regular expressions， which means a tuple。

Of of those two regular expressions。Or it's times， which means like concatetnation。😡，Of again。

 two regular expressions。Or it's going to be the plainy closure， it's going to be the star。😡。

Of a single regular expression。😡，Okay， so。What胳们。That is all you need to know to do regular expressions。

 okay， it's these six variants and we are going to define a recursive function that goes over all six of these variants and then matches whatever language we want okay。

😡，And I realized it looks scary。 you already saw it。

 but this is gonna it turns out that regular expression matching is an extremely good use case for CP and I'm telling you like I sat there and to motivate like before when I was playing this lecture I sat there and I tried to implement this without continuations for like two hours I like sat there and I thought for like a long time and every other implementation I got was either equivalent to this or worse than this so like very smart people that thought about it and this is how we're going to solve it and you're going to see why but but one reason for this lecture is that both regular expressions are useful and we get to use CP for real。

😊，This continuation looks a little bit different because it returns a bo。

 We we're going to drop the requirement that our function needs to be CP。

 CP design an idea that benefits us when we need to but we can drop it if it's not necessary。

 so we're not gonna to be super stringent about the CP we just have a continuation and now we have this specification the idea is that if I give you a regular expression I give you a character list。

 we're going to do the same thing that we did at the beginning of lecture which is that if I give you a list of characters which is like this I take off things from the front of the list as bitfits me until eventually I want to finish with the rest what I mean by that is。

😊，Match R given。S really CSs， and the continuation should evaluate to true only if you can split your input into two halves。

The prefifs and the suffix and the match thing should only succeed。If the prefix is matched by R。

And the suffix is satisfied by K。 that means that the prefixes in the language of the regular expression R。

😡，And the stics succeeds with the continuation this is don't ask why this is we're just going to do it and then it's going to work out really well okay I really can't motivate to this you other than telling you this is what it does and to give you kind of a picture again。

😊，Oop， sorry。the pictures on the next next slide， the point is I'll be split it up。😊。

Basically what I want to tell you is that this continuation specifies a condition。

 a condition on all of the suffixes I might choose。

 the regular expression denotes all of the possible prefixes I might choose。

 we want to strike a balance where the prefixes matched by the regular expression and the continuation takes care of the rest and we will the way we'll do it is we'll backtrack we're just going to take stuff off the front until we find something matching this and then hope that it satisfies our continuation。

😊，So for instance， if I had match RCs and I had this Lada， which specifies at the length of this。😊。

Suffix must be three。 This means that I would enforce a condition that all possible suffixes you might choose the only ones that succeed are the ones of length3。

 which is precisely the suffix actually that is one way we might use this。

 so it's kind of an idea of if I give a different continuation I give I get slightly different behavior。

😊，Okay I'm gonna to skip of that here's the picture okay if I am my entire character list Cs I'm looking for a way to push this boundary such that the prefix is still matched by R the prefix must be matched by R but the suffix everything I didn't choose must satisfy k and because k is an arbitrary function we have no idea what that looks like the only thing we can do is use the function K and then see if this succeeds or not but that's the picture is that we're pushing this boundary forward okay we're trying to push it to the limit。

😊，Does this picture make sense to people， all right？

We're going to see the implementation in the second here。And I will implement it for you。

 and then we may not have time for the proof， but that's okay。All right。

 and actually I should have written this out， but whatever。This is what our codes will look like。

 six cases， six cases， three slides， maybe all right。😊，Let's do it。

If I'm going with this prefix notation。😡，I want a prefix that satisfies R， right？😡。

So let's case on just our regular expression to see what prefixes match this。

 so remind me again what strings are in the regular expression of zero。😡，None。

 so that means there are literally no prefixes I can pick。😡。

So that means that what I'm going to do is I'm going to say。Bss。

I can literally never satisfy my regular expression with this。

 It doesn't matter what what my sloex is there are no prefixes。

 I don't get to move okay so boss always okay。😡，And then we're going to see one。

 what's the string in the language of one？Empty string。

 that means that my suffix must be the entirety of this string， right。

 That means my prefix must be the empty string。😡，So if my suffix is everything and my prefix is。

 you know。😊，It's kind of e vaccuuous over here。The only thing I can do is check that my suffix condition is true。

 I must have that this suffix， whatever suffix I choose， satisfies K。😡。

So this is true if and only if。Cs， that is the entire suffix。

 the entire character list is or satisfies this K。😡，Does that make sense to everyone？Okay。

 so I'm just checking that this one six I can choose satisfies K。😊，Cool， all right。

The next case I have is car。😡，And this is the case where we actually start to make moves， okay？

Because what's the one string in the language of C？It's C， right。

 so that means that the only prefix I can ever choose is this。If it's C， if it's that character。

 if it's not， I have no prefixes， that means I can't do anything right。

 so here's what we're going to do。😊，I need a case on my car list because I don't know whether or not it's going to satisfy。

I have two cases， either it's nil or it's conns， right？Or its C prime cons Cs。Okay。Well。

 if my thing is empty， if this is empty， I cannot take a prefix。

 there are no prefixes because it's empty， right， There are no characters。

 I want there to be a C on top of this。 So what I'm going to do is I'm going to say false。😡。

Right car C represents I'm trying to take a C off of the front， but I can't take anything。

 so this is unsatisfiable， I'm at the end， end of the line。😡。

But if this C prime is the same as that C， then I want to take it off。😡，Let's move forward， actually。

So if c is equal- actually sorry， it's more brief to say this。😊。

I want it both to be the case that C prime is equal to C。And then what do I do from there。

 well I have taken my prefix， my prefix is just this guy。

 and I need to make sure that my suffix is again satisfied by K， so I just give the rest of it to K。

😡，Let's write on this line。K C is prime， okay， this one's kind of confusing any questions on this？

Yeah。This is not CP like full CP。 we're alignlighting that。 It has a continuation， which helps。

 but we're not gonna say it has to be CP。 CP serves us when we need to Okay Any questions on this。

 the entire point of this is I take a C off if I can find it if I can't find it if this is not true。

 this whole thing is false if I can't take a C off no Bueno donezo right I cannot make progress Otherwise。

 but also I need to make sure the suffix is true I'm taking care of two things。 prefix and suffix。

 that is all we're doing。😊，Otherwise。R1， R2。If I have the plus case， here's what I want to say。

 I want to say I find a prefix that is matched by either R1 or R2。😡。

And the suffix can be whatever as long as it satisfies K。

I'm going to tell you that right now the way I do it is just this。

 and we'll talk about it in a second。啊。I ore both of them together。😡，If I find one with R1， cool。

 it's Scott free， I'm done。But if this fails， then I'll try it with R2， why not？

These are basically remember you remember the rehecursive leap of faith。

 our precondition is this will find us the match if it can find a prefix matching R1 that satisfies K。

 or if we can find a prefix satisfying R2 that such that this suffix satisfies K。😡。

Is it not the case that if I can find a suffix or a prefix for either R1 or R2。

 that's definitelyly what plus of R1 or r2 needs to do right so if I can produce a match for R1 or R2。

 I don't care plus just says give me either， sounds good。😡，Okay。

 so that's why this is the right thing to do here I just or else their conditions together。

 and I can use the result because this is not quite CP。😊，Okay。Any questions on this？All right。

 the Time case。Is a little more involved。Here's the idea。 The idea is I want to find。A prefix here。

Which satisfies R1。And then my suppix should then satisfy this condition。

 which means that the suffix。😡，Should itself be able to find？Its own prefix that is satisfied by R2。

And then finally， this suffix。Is satisfied by K。 I do two matches。

 right doesnn't that make sense if I have R1 R2， I take off a string for R and then a string for R2。

 and then I continue with my continuation。😡， so what we're going to do is we're going to make use of that continuation that we packed along for the ride。

😊，And I'm going to actually give you the picture so you can look at it while I'm drawing this up but this is the idea Okay match by R1 and this is expanding。

 but this one also is expanding matched by R2， and then we get the suffix to suffix which needs to satisfy K。

 So the implementation is a look like this。😊，I want to first find a match。For R1 on Cs， and if I do。

 I continue。With C's prime， which is this entire thing。That's Cs prime after I find this thing。

 then of C's prime， I want to find a prefix for it。😡，Matching R2。😡， such that。Well' just that。

 actually。Such that given this K， I satisfy whatever's left。😡，it's like I'm taking two big bytes。

 I take a big byte for R1， and then I take whatever is left， I take a big by out of that for R2。😊。

And then by my recursive call， by my recursive leap of faith， whatever's left needs to satisfy K。😊。

Does that make sense to everyone？Again， if you don't see how this code works in your head by like stepping it through that's okay。

 think about it in terms of recursive leap of faith。

 like big picture of what the code should be doing。I just take something out for R1。

 and then whatever's left， I take something out for R2。 If you could understand the high level。

 you can convince itself why it works。Any questions on this， because this is complicated？系。

And the starcase is also a little complicated， but here's the idea。😊，If I want to match。

A stringless or a character list for S R， I can match with0 or1 times。Of R for my prefix。

 this means r 0 or1 or more。😡，Well， how can I do that， that means either it's empty。😡。

Or if I take off R。😡，I can keep using star R right basically what I'm going to do is I'm going to take off R and then I'm going to say okay。

 well I could still take more R's off， so let me do star R again so I take a byte of R and I continue with star R。

😡，So here's what the。Continuue this thing looks like the basically the observation is that the language of R star is the same as language of either empty。

Or I get1 R， and then I get zero more R's again。😡，Because if you do the math that adds up。

 either I have nothing or I take off1 r and then r0 or more times。

 that's the same thing as r0 or more times， so this will be the same as that implementation up there。

😊，So I say either I succeed with the suffix right now that's equivalent to the one case because I don't take anything。

 I take nothing， but my suffix is the whole thing， or I take a bte of Rlf， I take off R。😡。

And then I succeed with star R again。😡，Because then I can keep taking ours off。

 that will ensure that we do it zero or more times。Does this make sense for everyone？Well， sadly。

 there's a bug in it。Because no， no， no， in intention it makes sense， almost correct。

But this implementation actually loops forever sometimes。In general。

 you should be very scared of whenever you see anything that gives the same arguments to the function twice。

 okay。In particular， we gave it star R again， which is the same， we didn't decompose it。

 which means that if I gave it star R and we're rehearsing on R， maybe we loop forever。

 in fact this might loop forever why because what would be the really bad case。

 the really bad case would be if this was the same and this was the same that is neither changed。😡。

Is it possible for my suffix to be the same as my entire character list？😡。

It's true because I showed you an example one。So if this were to be C's。

 that is if the regular expression R had the empty string in its language。

 this would loop forever because it would just call match star RCs。

 which would call matchch star RRCs， which would so on and so forth so this implementation loops forever because we haven't taken care of that case。

😡，So here's what we're going to do。Because the prefix might be empty there's two things we can do which I'm going to call weakening the sorryening the what preconditions。

 yeah weakening the specification or strengthening the implementation and here's a particular example for what would loop forever if we had match star1 given the string of a well we're doing a star where1 has nothing in it so we take off the empty string basically what happens is that if we had match star1 we take off the empty string and we get the same thing and then we continue with star of1 and this whole thing and when we take off the empty string which means we get the same thing and when we continue with star1 and we take off the empty string and we loop forever that's the concrete example。

😊，And this is not super important， but the point is basically by analogy。

 if I wanted to weaken the specification on fact。😊，I can do one thing。

 you know how fast loops forever are negative inputs， I can fix it in two ways。

 One is I weaken the specification by saying， hey， if you give me a negative input。

 that's not allowed， you can't do that。 So I say precondition negative inputs are not allowed。😊。

Or two， I strengthen the implementation by making it give me an option if I get a negative result。

 either I can forbid you from giving me bad inputs or I can work your bad input into my implementation。

😡，By analogy， we're going to do something here， that's the same thing。

So for the regular expression matcher， here's what we're going to do。😊，Either we can be like。

 you can't give me something like star1， you can't give me a star where the empty string is in this。

 and that's actually perfectly legal to do。😡，It would be a wimpy way of getting out。

 but you could do it like when youre implementing any function。

 you can always say that bad input you wanted to give me actually， by precondition。

 I don't care about it。 Don't worry about it。 That's allowed。

 It's kind of a wimpy way of getting out of it。😊，The next thing we can do is we can make sure in our implementation that the suffix that was chosen by R is never the same as the original list。

 the prefix was never empty。😡，Okay， and here's what we're going to do。 Okay。

 I'm going to write it up for you and talk about what it's doing as I write it。😊。

The modification was simply， I write。😡，KC。KCs is true， which is to say that we pick the empty prefix。

Or here's what happens I can write。😡，呃。Or wait， yes， I write match of R。So， I take。Or off。

And then when I get my C's prime。I want to make sure that this C's prime is different than that Cs。

 because if it's the same， I looped forever， I took a prefix that was empty and then I might loop forever。

 so I want to make sure that C's is not equal to C's prime。😡，But also。

 I want to continue with my thing， right。I do match。R2 C is prime k。啊， sorry 。St star R。Okay。

 so I've only added this。😊，The only thing I'm doing is I'm doing the same thing right say。

 if I want to match R zero or more times， either I match it zero times or I match it once and then match it zero or more times again with the added provision I can't have taken nothing off。

😡，So I don't live forever。And this will be the same thing where it will work。

 it will perfectly well match this language that I want to， but it's going to not loop forever now。😡。

So we lose nothing for this， this is what I call strengthening the implementation， okay？😊。

That is the entire implementation。It's a lot， but also it's not because it kind of just relies on your intuition on what this is doing at the end of the day I to。

😡，Yeah， so that's the entire implementation countered up， I don't know。😊。

but we wanted to not give this continuation right we wanted to accept the whole string and it turns out that we can write this function except that accepts the whole string really easily because we just have the continuation be this function called list null which checks for whether or not a list is empty that's what list null does it takes a nil and returns true and returns false on everything else and do you believe me that if our regular expression matches the entire prefix and the six is empty then our regular expression must have matched the entire string okay。

😊，That is all that's happening here， that's the accept function， okay。😊，This is really scary。

 but also it's。It's kind of just flyinging on your ability to trust the fact that this prefix and suffix thing is doing what it says。

 I realized like when I was writing this function， I only talked about prefixes and suffixes with you。

 I didn't talk about like the code really because that's what I wanted the high level to be if I think about my invariance I can program with my invariance rather than programming with the code if that makes sense I want to program by thinking about the high level because if I get lost in this if you think about the pure symbols that are going on here you're gonna to get confused and if you focus too much hard on what it's saying rather than what it's doing。

 you're going to get lost so that's another application of this there's a proof we're not gonna have time to get to the proof but I'm going to talk you through it。

😊，And we do have a few minutes。The point here is basically we want to prove that match is correct。

 and I know I have to move on from this。 Okay it's the dozy of a lecturer，😊。

Basically basicallysically basically， what I want you to think about is this， okay？

How do I assure myself that this match function actually works I want to be sure that if match RCs K ever gives me true。

 it must be the case that I had to be able to split it into a prefix and suffix such that the prefix was in the language of my regular expression。

😊，And k that is the suffix given the continuation or the continuation given the suffix is true I just want to be assured that that is true and in fact if you're dubious about whether or not this works I can prove to you that it's correct and we are going to be able to prove it and this will be on your homework by the way so we're going to talk through this and I need you on your own time to look through these slides because we're not going have time to discuss in next lecture but if you are having trouble doing this proof on the homework literally just look at this and the copy and paste okay。

😊，All right， not exactly， not exactly， but copy paste your understanding， okay。

 that I'm trying to stress you this is important， okay？😡，All right， so。

We're going to prove the plus case， and I'm going to talk through it to you， okay， really high level。

 we're going to go break that speed because I don't a whole lot of time， but here's the idea。😡。

I want to prove that match RRC's K is true if and only if I can split it into these parts。

 we're going call this the pact okay I'm going to stop saying out loud okay the pact is that I need to split it into a prefix and suffix such that the prefix satisfies the regular expression and the suffix satisfies the continuation that's the pact okay。

😡，How do we prove an if and on the if， we prove it twice， we go once this way and once that way。

 we call that soundness and completeness going from right to left。😡，That is right left here。

 it will be called soundness， left or right will be called completeness， doesn't matter okay。😊。

Let's do the soundness proof for only the plus case， okay， here's the idea。

And I've nicely colored it here so that hopefully can follow up。

I want to show that actually the left to right was the on this I want to show that if I get true。

 then I must have been able to fulfill the pact Okay so first to prove it。

 we're going to assume the antecedent， we're going to assume that I could get true from plus， right？

😊，And then assume as your IH that we could get that soundness was true for R1 and R2 in particular。

 if I look at my IH for R1， that is p of r1， it says this if I could get true for matching R1。

 then I must be able to fulfill the pact on R1 okay that means that I could find a suffix that was true。

😡，And I can find a prefix that satisfied R1， okay？And let's step through this if I have true。

 I well I know that match of plus is true， why because I assume to appear。

 so this is essentially equivalent， that's our assumption， the blue assumption。😡。

But I also know that this by our code by here。😡，Is equivalent to match R1 C's K or else match R2C's K。

 isn't that true， by definition？😡，But by definition of or else， it must mean one of these is true。😡。

Without loss of generality， which means I don't care about the other case。

 let's assume that this one is true。😡，If this is true。

 then we can use this guy because these two are red。😡，Both of these are red。

 meaning that I can use this if and obtain this。😡，And if I can obtain this。😊，Then I have that。

 by definition of the language of plus， if I have a prefix in the language of R1。

 I have a prefix in the language of the plus because it's in either and then so if p is in L of R1。

 it's in l of plus R1 R2。😡，And then if I have that P， the prefix is satisfies plus。😡。

And the suffix satisfies the suffix or the continuation， that's the theorem。😊，Okay， real fast okay。

 if you don't get it and then real fast， we're going to do completeness as well， all right。

 we want to do the reverse direction if I have the pact， then I get true for match。😊。

Assume that the pact is true， then assume that the pact is true for your R1 and R2， the IHs， okay？😡。

If I have the pact for R1， that is I have the IH and R1。

 then I must have that this implication holds， okay。😡，If I have this yellow assumption here。

 which is that p is in the language of plus in R1 r2， by the definition of languages。

 that means the prefix must be in either of these languages。

 it must be in R1 or R2 to be in the plus。😡，We'll log again， assuming that it's in R1。😡。

Then if I have this purple thing， I can feed the purple thing in here and this green thing I already have。

 and I get this red thing。😡，Okay， so then I have that match must be true for R1。😡，But again。

 by definition， match of+ is match of the or else of Rwin and R2。😡，And because I just got this。

 match of R1 must be true， therefore the or else is true。

 therefore match of this whole thing plus is true，😡，That is just me talking you through it。

 Please look this over on your own time， I'll probably record something and then or come to my office hours。

 that's it for the lecture。 I know it was a lot， okay but。😡。

That's kind of how it is sometimes things。Dunk。

![](img/d6da4301e56d56b7be85322e5d149cc0_4.png)