# UIUC《算法与计算模型｜UIUC CSECE 374 - Algorithms and Models of Computation 2023》中英字幕 p10 20230921-Sep 21_ Midterm 1 review (redo).zh_en -BV1Mh7RzaEL2_p10-

![](img/b0fba6a2d8682a66e78168505e9fd071_0.png)

Hi everybody this is Jeff unfortunately it looks like the microphone I was using to record the audio for the review session earlier today died about 20 minutes into class and so most of the video that I recorded is silent so I'm going to record this again this will be without the benefit of interactive questions from the audience。

But I'll try to remember things that people asked and bring those points up on the fly as we go through。

So I'm going to walk through a practice exam for midterm one， which is on Monday。

 this will have roughly the same format。As midterm， although the final。

 the actual midterm may have a slightly different balance of questions。

 one question on a topic instead of two or vice versa。

 there will be a very high level five questions with numbers each worth exactly the same number of points。

Namely 10， and one of those questions will be a true false question like this。

So the way the exam will work is I will pass out。A sheet of paper that has all the questions on it or the TAs will。

 depending on what room you're in。And we'll give you a chance。

 everybody a chance to read through the questions。And after three or four minutes， we will ask。

 does anybody have any questions about the exam problems？

And we'll answer those questions as best we can。And in particular。

 does anybody have questions about the last problem just to make sure that everybody's actually read all of the problems？

And then we will pass out an answer booklet。It looks like this。

 this is where you'll actually write your solutions and we do want everybody to write their name。

And their net I。Into these boxes， this is how grade scopepe will identify you when we scan the exam so it's important to write this fairly legibly。

Once you get the answer booklets， you will have exactly two hours。

 120 minutes to answer all the questions in the exam。

 just to finish the instructions on the first page here。

 you're allowed to bring a doublesided cheat sheet as advertised earlier in class with anything you want written on it by you by hand。

 but that's it everything else is off limits。There are also boxes at the top of every page where we ask you to print your name。

 this is just in case the staple falls out and for some reason we need to put a disassembled exam back together。

Just a second， okay。I'm not using the right microphone， Okay， let's try this again。

Zoom and microphones are not for some reason。呃。Don't behave nicely。

So then you also notice there are black boxes around the pages of the answer booklet。

 that's because the scanner that we're using doesn't actually scan the entire piece of paper so we want to make sure that what you write is actually going to be scanned。

 if you write outside the black boxes we may not see what you write so please stay within the lines。

嗯。嗯。There are。A couple of places， especially in this exam where we ask you to prove things。

 if we do not actually say that we want you to prove something。

 then we do not want you to write down a proof。You probably still need to step through a proof in your head because that way you can be sure that what you're writing down is correct。

 but we're not going to ask you to write that down just because it takes time。Um。

 and at the end of the exam， we're going to ask you to turn in all the all the paper that you've brought with you or that we've given you。

All right。So what I want to do is start by walking through the questions in the exam one by one。

 make sure that everybody has a chance to think about these and then we can walk through the exam。

 solving the problems one by one， not necessarily in order。So question one。

Let compress zeros of W be a function that takes the string W as input and returns the string form by compressing every run of zeros in W by half。

Specifically， every run of two n zeros is compressed to length n and every run of  two n plus 1 zeros is compressed to length n plus 1。

 so cut in half round up。For example， if I take this string。F zeros followed by two ones。

 followed by three zeros， followed by one， one， the run of five zeros gets compressed to link three。

Half of five is 2。5 round up to three， the run of length three zeros gets compressed to only two and the runs of ones get copied verbatim。

 similarly compressed zeros， two ones， four zeros，11，10 gets turned into two ones， two zeros 1110。

And there may not be any zeros in the string in which case compress zeros doesn't do anything。

 or another example is if compress zero， if the string only has a single isolated zero。

Compressor Osley Zillone。So this is a language transformation question。

 you're given an arbitrary regular language L。And you want to prove that two different related languages are regular。

The first is all strings in Sigma star or Sigma is 0 and1 where compressed zeros of W belongs to the language L that you're given。

The other is all strings。Formed by compressing a string in the language。

 so compress zeros of w where W is the string in them。

This is really similar to the stutter unstuutter questions that you did in homework for。Problem two。

For each of the following languages over the alphabet Sigma equals 01。

 describe a DFA that accepts cell and give a regular expression that represents L。

 you do not need to justify your answers。So I need to build the DFA for the set of strings in which at least one run has length to visible by three。

And all strings that do not contain either 100 or 011 as a substr。

And then once I've built a DFA for these things， I also need to write down regular expression for these things and when it says you do not need to justify your answers。

 that means just you know it's fine to just draw， I don't need to name the states。

U this is clarified in the standard rubrics that we posted on the homework page and the exam page on the course website。

Question 3。We define this recursive function bond which doubles the length of any run of zeros in the input string or replaces any zero with two zeros in a row。

 so this is defined recursively bond of w is empty if w itself is empty。

It's it'so do bond of x if w is o do x， and it's1 bond of x if w is 1。 x where x is some string。

So I need to prove two things， one that bond of W is at least as long as W for every string W。

And the second that bond of the concatenation of two strings is equal to bond of concatenated with bond of y for all strings。

 x and Y， and the directions emphasize that you're allowed to use any result that was proved in class that was proved in lecture notes that was proved in labs or it appears in lab solutions。

That you proved in the homework or that appears in the homework solutions。

 anything that you've used before you are allowed to that you've seen proof for。

 you are allowed to use that again in particular because we're proving something about concatenations some properties of concatenations might be useful here usually they're not that many of these sort of factoids that generally come up these are typically things like remember the definition of length。

 remember the recursive definition of concatenation。

 remember that concatenation is associative but not commutative the order matters。U。

Concatetnation plays well with length， concatetnation plays well with the reversal， things like that。

So。Question four。Let L be the language zero to the A1 to the B0 to the C。

 so A zeros in a row followed by b ones in a row， followed by C zeros in a row。

Where two of these exponents are equal， but I don't care which two so a equals B or a equals C or b equals C。

The first part here is to prove that this language is not regular。

Probably we're going to be using the fooling set argument。

And the second step is to describe a context free grammar for this language。

It's similar to what you did in again， in homework4 and in the most recent labs last week's lab。

And finally， question five， for each statement check true if the statement is always true。

 that means no exceptions， no ambiguities， and false under any other circumstances。

And give a very brief explanation of your answer and there's a warning here to read the statements very carefully because there are some small details that actually matter so in the actual answer booklet you'll see that for problem five there are blanks that come after the individual statements and the yes no boxes so you'll check one of the boxes and fill in your reason and we do expect reasons that fit on this one line。

Okay， so that's the entire exam。At this point， having read through everything we would ask。Hey。

 you did everything make sense and one question that that might come up is you know。

 we use this word run over and over again， so a run。Is a maximal。Non empty。Substring。

With all symbols of the same。So here in the argument to compress zeros。

 these five zeros in a row define a run and that entire string inside the argument for compressed zeros consists of exactly four runs。

One with five zeros， one with two ones， one with three zeros， and one with one one。

The empty string has no runs。For example。嗯。And so at this point， we would ask， you know。

 does anybody else have any questions， everything makes sense？

And it's possible that there are questions that you would want to ask where we really feel like you should already know the answer like what's the definition of concatenation or what's the definition of。

Of length， in which case we'll say we can't answer that。

 but feel free to ask any question at all during the exam。嗯。

So we'll pass out the answer booklet and now the clock actually starts。

And what I would recommend at this point is to look through the exam and see which questions you feel most comfortable making progress on first。

 so find something that you think you can do or that that seems relatively easy and work on that first。

 partly just to make progress and partly to you know give yourself a confidence boost that you can actually do this stuff everybody's nervous going into exams。

 including the author of the exam so it's you know be nice to yourself at the beginning especially。

So we could do something about language transformations。

 we could do something with DFAs and regular expressions， we could do something with induction。

We could do something with fooling sets and context remarrs。

 or we could do something with these true false statements。

And this is in the actual review session on Thursday。

 most people or the plurality of people seem to want to do the true false statements first。

 so we'll start there。Okay， so for the first statement is if two plus two equals5， then zero is odd。

Even though two plus two equals five itself is a false statement， this implication is true。

one argument you could write here is vacuous or and could say false implies anything。I true。

From a false premise， you can conclude anything you want。Okay， next question， zero to the n1。

 where n is greater than0 is the only infinite fooling set for the language0 to the n1，0 to the n。

 where n is greater than0。So first of all， it is a fooling set， so given two strings of the form。

 some number of zeros followed by a1， I can distinguish them by using the right number of zeros as a suffix。

But it's not the only way I could do that， because I could also use。嗯。呃。

I could take the one out of the strings in the fooling set and add that one to the beginning of my distinguishing suffixes。

More generally， in fact， for any non regular language。

 there are an infinite number of infinite fooling sets。Um，Uh。

 so it's never the case that there's only one infinite holding set for a given non regular language。

Pt scene。Z to the n1，0 to the n is a context free language。This one。

 you kind of imagine as I walk through the string。Okay。

 I can kind of push something onto the stack because I see the zeros at the beginning。

 counting up to n and I can pop those back off as I read the zeros at the end。

 so this seems to be the kind of thing that would fit into a context free grammar and in fact I can write a context free grammar for this by saying well and the smallest string that n could have sorry the smallest string in this language is010 because you'll notice that it says。

S is greater than zero， not greater than or equal to。

But then it can have any number of zeros beyond that。

So I can construct string an arbitrary string in this language by putting down a zero at the beginning。

 zero at the end and recursing in the middle， or by just writing down zero and0。

And I want to emphasize here this says something you know in the instructions。

 please read these things very carefully， this is a greater than if you had written down S goes to1 or S0。

 you'd still get the half point for writing for checking the yes box。

 but you would not get the half point writing down the context for grammar because that's the grammar a slightly different language。

I also want to emphasize here， each of the yes nos is worth half a point and each of the explanations is worth half a point。

If you mark the correct box， you get the half a point。

 if you mark the wrong box that's exactly the same as leaving the answer blank。

 so there's no negative scores for guessing incorrectly。Okay， Part D。

The context tree grammar S goes to 00 s or S11 or01。Generates the language 0 to the N，1 to the N。

And here there are a couple of reasons to think that the answer is likely to be no。

 one of them is every string generated by this language has an odd number of zeros。

An odd number of ones， so it can't。Generate。The string 0，0，1，1。On the other hand。

 it can generate strings that have more zeros than one so I can apply the first production rule and then in recursively apply the third conduction rule。

 but it does generate。000 one， which you know the first string is in the language the second string is not in the language。

 so it's just the wrong。Grammar， it has it's neither exclusive nor exhaustive， it's not。

 it doesn't cover the language and it doesn't stay within the boundaries of the language。

You only need to write down one of these two justifications by way。Part E。

 every language recognized by a DFA is every regular language is recognized by a DFA with exactly one accepting state。

Now if this had said NFA， then the answer would be yes because I can put down a new isolated accept state。

Add Epsilon transitions from the existing accepting states to the new accepting state。

And then make all the old accepting states back be normal again so I can just。

Epsilon transition all of the accepting states together， but for a DfaA。

This is not always possible and one piece of intuition about this is when we were talking about product constructions。

 we got you know these large DFAs with lots of things and we minimized them， they didn't all。

 it's not necessarily all going to collapse。But I think the simpler explanation is just imagine the regular language。

Strings whose length is not divisible by three。So I can accept this with a DFA。

 this language with a DFA that has three states， one where I get length divisible by three。

 one where the length of mod three is equal to1 and one where the length mod three is equal to 2。

And length mode3 is one and length mod3 is two， those are accepting states。

 but I have to distinguish them because if I add one more symbol。

 length mod three is equal to one would transition to length mod three is equal to two。

 which is an accepting state。But the other the other accepting state length modb three is equal to two。

 if I add one more character， now the length is divisible by3。

 but then that's not accepting so the minimal DfaA in this case。Looks like this。And actually。

 there's their start state。And there's absolutely no way to collapse this。Or F。

Any language that can be decided by an NFA with epsilon transitions can also be decided by an NFA without epsilon transitions。

And the answer is yes， and one way to justify this is that I actually described exactly how to simulate an NFA with epsilon transitions by by an NFA without。

In class by adding a new start state and or using multiple start states and just replacing。So。

 you know。Could do something like。This。so anytime I see a pair of transitions。

 one that's an epsilon transition and the other is a real transition。

 I can replace them by a direct real transition。Another way I could say it is I can。

Anything that could be decided by an NFA with Epsilon transitions can be decided by a DFA through the subset construction and every DFA is an NFA without epsilon transitions。

Pery。If L is a regular language over the alphabet 01。

 then then the set of all strings have the form x y to the C， where x and y and L is also regular。Um。

Where did I define why， oh， there， there's why the see？So the language that we're interested in。

Is to find up here this is the the bitwise compliment or earlier we referred to this as。

Flip of W and one of the lectures， so this is replace every zero with the one and vice versa。

And we argued that the flip of any regular language is regular。

And so that means that this language that we're looking at in part G is also regular。

 this is equal to L dot flip of L。And。If you really want to be。Is。Regular。Swamp。0 and。

Want transition， you know， so the way you prove that the flip of a language。

 meaning the set of all strings。Whose flip is in the language？Why do the sea where why is and hell？

To argue that that's regular， you take your DFA for L and everywhere you see a zero transition。

 replace it with a one transition vice versa， just just swap the transition functions。U。Part H。

If L is a regular language over the alphabet 01。Then the set of all strings of the form W followed by the flip of W。

 where W is an L is also regular。Now this one doesn't seem this one's not a concatenation of L with flip L because the two halves of the string have to be the same。

Now in order to show that this it's not clear whether this is true。

 so let's aim for trying to show that it's not and the thing that we we need to find is just we need to find a regular language。

 a specific regular language where this derived language isn't regular and usually try simple things like try the simple language hell is equal to zero star。

Then in that case， WWC。Where W is an L。Well， any string W in the language zero star。

Is a string of the form0 to the n where n is some non negative integer。

And then the flip of that string， I replace every zero with a 1， is one to the n。Right， same， right。

 it's the the same number of ones that I just had a number of zeros because I'm flipping the。

The zeros prefix。And we know that this latter language is not regular and this is the canonical。

 not regular language， so this is no。嗯。Part I， the regular expression 00 plus 11 all starred represents the language of all strings over 01 of even length。

Well， every string generated by this regular expression has even length。

 but not every even length string can be generated this way， so in particular the string 01。

 which has even length is not captured by this regular expression。

 doesn't match the regular expression。U what the regular expression describes is the language of all strings where every run has even length。

U not those the whole string has he blink。And finally， let L1 and L2 be2 regular languages。

The language L1 plus L2 altogether starred is also regular。

This is yes by the definition of regular languages， so the definition of regular languages says。

The union of two regular languages is regular and the Clany star of a regular language is regular。

And this is all I need to write down， so you'll notice I was very sort of sketchy。

 very telegraphic here right I wrote down01 for part I。

 I didn't even bother to say01 isn't matched by the regular expression。

This is the level of detail that we're looking for。

 we want to know that we want evidence that you understand why your solution is correct。

But we do want to be careful that you write down evidence for the right thing。

 so just be careful if you're worried， write in a few more words， but as a general rule。

 you know the explanations we're looking for are very short。Okay。

So that is all for part problem five。We've got four more problems。

Foling sets and context for grammars。Or induction。Or。DFAs and regular expressions or transformations。

And I think just to I think because this is likely to be relatively straightforward。

 I'm going to go for the DfaA regular expression thing again I need to。

Write my name here to make sure that。If the staple falls out， then I get credit。

So I've got part A and part B here， I might might as well draw a line here and say。

 you know part A is going to be on one side and part B is going to be on the other。You know what。

 I'll just be careful about using space。Okay， all strings in which at least one run has length to visible by three。

Okay， so remember， a run is a substring that has all characters the same and there's at least one such character so can't empty string is not a run。

And this is it's as long as possible。Okay， so there are two kinds of runs。

 there are runs of length runs of zeros and there are runs of ones。

 so I'm just going to write down regular expression。First。

 that means this is a run of zeros whose length is divisible by three。

And then next 111 followed by 111 group star。Um， that is a run of ones whose length system is by three。

Now， this is just a part of the strings that I'm looking for。

There could be more characters before the run of zeros。

 it could be more after the run of zeros or run of ones。

But if there's something before the run of zeros。Maybe there's nothing before that run of zeros。

 but if there is something before the run of zeros that something has to end with a one。

 I can't have this run of zeros whose length is divisible by three。

Preceeded by a zero because then that would that extra zero would get folded into the run and now the div visibilityibility goes away。

So in order for the subexpression。To actually match a run。

Any character that comes immediately before it must be a zero。But。

Before that zero can have anything at all。Symsymmetrically， I can have。

A one followed by anything at all or nothing。After the run of Zes。

And then I need to write down symmetric stuff for the possibility of run of liness。

And in the background there， you can hear my dog being frantic。I' paying just say。Okay。

 and so here is my regular expression for part A。嗯。

So now let's let's let's try for the for the DFA Okay， so I'll start off in some state now。

At the beginning， I might get a zero and I might get a one and this is going to lead me into I'm in the middle of a run of zeros state above and I'm in the middle of a run of ones in the state below。

 but mean both cases， the run that I' read I've read so far， has linked one month three。

And so then I will add。Another state。This will be， again。

 now I have runs of whose length mod three is equal to two。And then finally here。

I'll have runs whose length is divisible by three。Now if I'm in the accepting state on top and I get another zero。

 I will loop back to a case where the length is1 month3。And similarly。

 if I get another one in this accepting state。Though that just means the run isn't over。

 so I need to keep reading until I get to the end of the run。

 which could happen at the end of the string， so if the input string ends with me in this state。

 then my run of length zero run of zeros whose length is visible by3 is at the end of my input string。

 and I should accept。But it's also possible that I'll get a one or symmetrically down here a zero and this is what happens when I end the run in the middle of the string。

 so up here。Um I go into this run and then I see a one and anything after that is fine。Okay。

 so we're almost done。So this handles everything that happens if I start with a run of zeros that could be have length divisible by three。

 followed by a one and anything else。Uh， or I could start withum a run of ones whose's like speeches by three。

 followed by a zero and anything else。But if I'm in one of these intermediate states。

In the zero cycle and I read a one， then I need to say， oh。

 I haven't seen the run that I'm looking for yet， jump over to the cycle for ones and to the right place。

So here I would go。Like this。So no matter where I am in the cycle you know， if I have a run of zeros。

 if its length is one or two month three and I read a one。

 I'm now starting a new run of ones and that run of ones so far has length one month three。

Symsymmetrically， I will。Branch， you know， from the cycle that keeps track of the length of the one runs。

 if I see a zero and my current length isn't divisible by three， then I say， okay。

 this was a garbage run of ones， let me jump back to the zero side because I'm now reading a run of zeros so far。

 I've only read one zero。And at this point， we have a DFA。

Every state has exactly one zero arrow coming out of it and exactly one one arrow coming out of it。

And this is all I need to write down， so notice I do not need to name the states。

 as I mentioned earlier， I do not need to give further explanation for my regular expression。

 as I mentioned earlier， what I've written down here is sufficient for 100% full credit。

So now let's look at B all strings that do not contain either 100 or 011 as a substring。

And here I'm going to advocate for a strategy of let's try to write down a long string that is in the language。

And if we write down something long enough， maybe we'll see some patterns that are useful so all right。

I'm going to start by writing down some number of zeros。Okay， then I'm going to switch to ones。

But at this point。If there is a character after that one。

It can't be a one because then I would have the forbidden substrate。

So if there is a character after this， it has to be a zero。And now again。

 if there is another symbol after the  one0， it can't be a zero because then I would have one of the forbidden some strings。

 so it must be a one。0，1，0，1 so。I can start out with as many zeroes as I want。

But then once I say one， the rest of the string has to alternate between zeros and one。诶。Now。

 obviously there's also the symmetric case where I have a bunch of ones and then I alternate between zeros and ones the other way。

Here's another example。And I don't have to have the long run of zeros and I don't have to have the alternating part。

 that could just be zeros。Um， but we'll well we'll try to capture， you know。

What I'm going to try to do is write down a regular expression that captures what can happen on the left。

And a separate regular expression for what can happen on the right。But I've got two cases。

The initial run is zeros or the initial run is ones。Um， and so the initial run of zeros。

 I could have any number of zeros I want。Then I have to alternate between ones and zeros。So one0。

 one0， one0， one0，1，0，10。But I might。😡，Want to end on a one and I might want to end on a zero and the way I make that work is I write one plus epsilon here。

So if I have， for example， the string 010， that would be 10 from this plus110 from that。

And then I would pick the epsilon from the third part。可以。

The complementary thing is just the flip of the part I've already written down。

And there's my regular expression as a sanity check， let me look at some short strings。

 the empty string doesn't have either of those forbidden substrs in it。

 so the empty string is in my language and the empty string is captured by this regular expression I can take zero zeros here and zero1 zeros that nothing from this star。

 nothing from this star and epsilent from that star and get the empty string。

I can also get the empty string from the part on the right， but that redundancy I don't care about。

 the pieces of the regular expression that I put together with a plus don't need to be destroyed。

 they can overlap。UmHow about just a bunch of zeros in a row and nothing else， well。

 I could capture as many zeros as I want here and then nothing and then epsilon。

A bunch of ones in a row there and then。Um，h， you know， nothing from this and then eps on。

A bunch of ones followed by a zero， here's all the ones。

 I ignore this part and I take a zero from here。So， you know。

 this seems to be hitting all the boundary cases where。

Just alternating zeros and ones I take nothing from here and。

Either I start with a one or I take nothing from here and I start with a zero。

So it seems to be capturing all the cases， I think this is a good。A good regular expression。

So now let's think about DFs。So I'm going to start in some state and if I start out reading a zero。

 I can read that zero as many times as I like。So if I start out with a one。

 I can read that one as many times as I like。But I'm still in the mode of reading the prefix。

And then there'll be a transition where。Now I'm reading the suffix part。

So if I read a bunch of zeros and then I read a one now I'm in the place where I need to alternate between zeros and ones。

 so the top state on the right is going to be I'm in the alternating part and the last bit I read was a one the bottom state is going to be I'm in the alternate new part in the last bit I read was a zero so I need to have a zero transition that way and a one transition this way。

All of these states are actually accepting states。U so it looks like I'm accepting everything。

 but I haven't actually specified a DFA yet right so if I'm in the top right state and I read a one。

Or we're in the bottom left bottom right state and I read a zero。

 then I can go to rejecting this fail state。But the other way I could do this is just to write。

Um all missing。Transitions。Go to a hidden。Fail state。

I either need to explicitly write the fail state in into the drawing or I need to write the sentences if I leave the DFA with just these five states and know nothing about a fail state。

 the greater is not going to know。Whether I don't know that a DFA needs to have transitions with from every state with every possible symbol。

 or maybe I thought I was writing down an NFA， or maybe I thought it was obvious that there was a failed state I didn't need to write it down so there's no way for the greater to understand my intentions。

 whether it was a mistake or whether it was intentional so I need to write this sentence to emphasized to the greater that I am intentionally leaving some things out and this is what it means。

没。Again， I don't need any further explanation of the regular expression or of the DFA。

What I've written here is completely sufficient for 100% full credit。All right。

 so let's look for another problem。There's a language transformation problem。

There's an induction problem。Or there's a tooling set and context for grammar problem。Now。

 in the in the review session earlier today， I think at this point people were aiming you know mostly interested in the。

The language transformation problem， so let's imagine， let's do this next。

And remember what the compressed zeros function does。So given any sequence of zeros。

 it removes half of them。Or any run of zeroes。It removes half of them， but it rounds up。

So six zeros gets turned into three and five zeros also gets turned into three。嗯。呃。So this is really。

I think equivalent。To saying let's remove。Sorry， I meant put a different color。

Let's remove the second and the fourth and the sixth and so on， every other zero。From each run。

 right？So the zeros that are left over， those are the ones that I'm going to keep。Right。

 so when I'm looking at。You know， the solution for part A。All right。

What do I need to remember when I'm scanning through a large input string。

 so I'll just I'll just write another。Sort of large example here。10，1， zero， zero， zero， zero， one。

 one， one， zero， zero， zero， okay。So what compress is going to do is remove。Every other one。

But resetting what every other means each time it gets to a different run。Okay。

 the second zero in every run of length， at least two。

 the fourth zero in every run of length and at least four and so on。Okay。So for part A。

 I am given an arbitrary string。And I want to。The scent I want to。

Simulate the given machine and the DFAM that accepts this arbitrary language L on the compressed version of that string。

Right。So when I'm reading through the string， trying to decide what to do， every string。

 every bit that is not xed out， I'm going to pass to my simulation of M and every bit that is crossed out。

 I'm just going to throw on the floor， I'm not going to pass to my simulation。

So I need to I need to know when I'm going through a run of zeros。

 I need to know whether I'm at an even position in that run or in an odd position in that run。

So the new states of this NFA that I'm building， I need to remember where the simulation of M is。

 I need to remember the state of my DFA。But I also need to remember this pary bit。

Or when I'm in zeroerbins。Now at this point， I could also say I need to know whether I am in the middle of a zero run or a one run and I could add another pair。

 another component to my NFA states here， but I think it's actually simpler if I if I interpret this as the parity。

Of the number of zeroes。Go。Red。So what this means is I look at how many of the the the how many of the last consecutive bits that I read were zeros if I just read a one。

For example， if I'm at this position in the input string。

I have not read any zeros previously previous bit was a one， there are no zeros in my immediate past。

 so this is an even state， similarly if I'm here it's I just read that one。

 so I'm now in an even state， even if I was all in an even state one bit ago within in the zeros。

I'm now in an even state again。系。So when I start， I'm in my machine is in its start state and the number of zeroes that I've just read is zero。

 I have not read any bits at all and zero is even。So the accepting states of my NfaA well my。

DFA needs to be in an accepting state， but I don't really care whether the NFA is an even mode or odd mode。

The bits that I've sent to the DFA。Put to the DfaA into an accepting state and that's good enough for me so I can write this as。

A cross even odd。Or if I want to be more。explicitplit about it can write this as all all NfaA states to DFA state Q and a parity bit P where Q is either so is a state。

And P is in， even more odd。And of course， that should be an accepting state。Like this is enough。

 I don't need to write down both of those definitions。

And now I have a couple of different things I need to write down for the transition function。

I have exactly four things that I need to write down。

 assuming that I don't use any epsilon transitions。

So I could be in even mode and I could be in odd mode。I mean， me， M prime。

 this new NA that I'm building could be an even mode and it could be an odd mode and the bit that I'm reading could be a zero or could be a one。

So in the case where。嗯。I am。啊。You know， in。Even mode and I read a zero， so this for example。

 is when I'm reading the very first zero， I am going to pass that zero to my simulation of M so I'm going to change the state of my machine。

By by feeding it a zero， and then I'm going to switch to odd mode。嗯。

If I'm in odd mode and I read a zero， I'm just this is like。

If I'm looking at the second bit the number of bits I've read so far that are all consecutive zeros is one that's odd。

 so at this point I'm looking at a zero bit that I should fall on the floor so I don't change the state of my DFAM and but I switch to even mode。

When I see a one。Regardless of whether the current parity bit is 0 or1。I pass that one to my。

Simulation of M and at this point after reading a one。

 the number of zeros that I've just read is zero， the consecutive zeros leading to the most recent bit。

 there are none because the most recent bit was a zero so in both of these cases I'm going to go into even mode。

And at this point I actually appear to be done now I do want to be a little bit careful here。

 I haven't specified whether this is a DFA or an NFA。When I'm designing these things。

 I'm always in my mind aiming for an NFA， I didn't use any epsilon transitions。

 but I'm always allowing myself the possibility of using Epsilon transitions。But in this case。

I never needed to use non determinism at all， so I need to write that this is a DFA。Alternatively。

I could say， actually this is an NFA， I just decided that at the beginning， but if I do that。

 I also need to write these braces down。One or the other。Okay， so if you leave the braces off。

 you need to explicitly declare this is a DFA。If you need to use the braces or if you just decide。

 I'm going to write down the braces at the beginning because I think I'm building an NFA I don't want to decide yet。

When you get to this point， you just say， okay， it's an NFA， I can stop。诶。Again。

 this is a point about distinguishing for the greater。

 whether what you mean when you write something like if you left off the word DFA and you left off the braces。

 then I don't know whether you think it's obvious that this is a DFA and so you didn't bother to write it。

 or actually you think this is an NFA and you just forgot that the output of its transition function for an NFA is a set。

So make it clear， write that， you know， which one it is。By just being explicit。Again。

 I don't need any other details， the stuff that I've written in red here and the stuff that all this example。

 this is just scratchwork it doesn't need to be there in order to get full credit。

 this is a complete description of the new NFA in terms of the old DFA4 L and notice I didn't write down the boiler platelate that says let M equals Q comma S comma A comma delta be an DfaA that accepts L because we know that that's how this proof is going to start。

Okay。嗯。Let's look at。The other direction。So for part B， I'm given a compressed string。😡。

And then what I need to do is uncompress it and feed the uncompressed version of the string to my DFAM。

Now the problem with this is that uncompressing is kind of ambiguous if I look up here at the top example here。

If I see in the compressed string three zeros， a run of length three。

Maybe that means the original uncompressed string had six zeros in a row。

 and maybe it means it only had five zeros in a row。

And so I'm I need to guess which of those two it is。And in particular， you know。

 I sort of have two ways that I could do this and both of them can be made to work。

 but one of them is a little bit simpler than the other。The idea is when I look at the first bit。

 I'm going to decide。But guessing whether that first bit corresponds to a single one。

A single zero or two zeros。And for every other bit。

 I'm just going to assume it always gets expanded to two。鸡。I don't know which one of these it is。

Okay。So somewhere it's kind of like the stutter function that we looked at in the homework。

 we're applying the stutter function， we're proving that stutter of L is regular。

We get the stuttered string and we or maybe it's unstuutter where you're given the shorter string and every zero gets turned into two zeros。

 right？The one exception here is when I guess that the run length is odd。

 I need to pick a0 that is not going to get doubled before I pass it to the simulation the two most convenient places to do that are at the beginning of the run and at the end of the run。

the beginning of the run is easier to detect sorry the beginning of the run I noticed that I at the beginning of the run of zeros because either the previous bit was a1 or I'm at the start of the string。

And so I can remember the past and that tells me what that that allows me to figure out whether I'm at the first zero in a run if I wanted to detect the last zero in a run。

Then I have to wait and not do anything until I get the next bit。

 and if that next bit is zero is a one， then I go back and go， okay， this zero was。

 in fact the last zero and now I need to do something weird。

And this just gets really complicated and it screws up you know makes the accepting conditions more complicated so I think in general it's easier to use the information you've already learned about the past of instead of trying to in some sense predict the future。

系。So what am I going to need to remember in my NFA besides my DFA state？Well， there's sort of。

Three modes that I could be in， one is I'm just reading ones， I don't care。🤢，Another is I am。呃。Well。

 I meanve've I've read at least one zero right I guess that's the the right way to put it just instead of looking at the parity the numbers of zero is just red。

 I'm really just going to remember。The previous bit that I've read and in fact。

 I think what I really want to remember is either I'm inside a run of zeros or I'm not inside a run of zeros。

I think this is the right way to say it。Because when I'm in my start state。

Then I haven't actually read anything at all， and therefore I didn't just read a zero as far as I know I'm not in a run of zeros。

If I see a zero in this state， I know it's the first zero in his run。嗯。Accepting states， again。

 as long as the DFA that I'm simulating is happy， I don't really care whether I'm in run zero mode or in not run zero mode。

So I just need to now write down the。嗯。Or possibilities。Or。The transition function。Okay。

 now some of these are relatively easy。Whenever I read a one bit。

 I know I'm just going to send that one bit to the。To the machine。

And I'm going to enter not mode because I'm I just wrote a one。

 that means I'm not in the middle of a run of zero。Okay。

And it doesn't matter whether I was in run mode or not mode before。

Im now I'm going to pass the one to my simulation of M and go into not。Okay。

 that's that's determined。If I'm in the middle of a run of zeroes。And I read a zero， so one of these。

 let I say， you know， I'm here。I'm reading my third zero in the run， so okay， then in this case。

I know exactly what to do。 I need to feed two zeros。To my simulation of M。

 so one way of writing that is this。And now it' stolen runs your remote mode。So remember。

 Delta star is what you use to transition on a string instead of on a single character。

If I want to be more explicit about this， I could write it out as deelta of delta of Q comm0 comm0。

 that's exactly the same thing。But whatever whatever whatever， however I write it down。

 it's completely determined， I'm passing the zero to my machine M and then I'm passing another zero to my machine M while I'm consuming only one zero bit from the original input。

The interesting case happens when I am in not mode in our meta zero so this is the first zero in a run in this case I have a non deterministic choice I can either pass a single zero。

And enter run mode。Or I can pass two zeros。And enter run mode。

And here I'm using nondeminism in an explicit and necessary way。

 I don't know whether the run that I'm just now starting in the uncompressed version has even length or odd length。

If I guess that it's odd length， then I'm going to only feed 10 to my machine M。

For later zeros on'll feed two。If I'm guessing that the run I'm about to start is even has even length in the uncompressed string。

 then I'm going to pass two zeros to my machine M and then two zeros for any input zeros as I read later in the same run。

But now this is definitely an NFA because I just did something non deterministic。

 which means I need to write in these braces。Um， to make sure that I tell the greater that yes。

 I know the output of the transition function is always a set when I have an N。And now this is again。

 enough for 100% full credit。We've written down the states， the start state， the accepting state。

 and a complete description of the NFA。Now there may be cases where you want to use Epsilon transitions。

 if you do， you need to write down every possibility for the Epsilon transition。Unless you decide。

 I don't want to write down transitions where the output is the empty set in which case you need to write the sentence。

All missing transitions go to empty set。Right so if we see things that are missing， you know。

 I don't know whether you left those off because you didn't know you had to write them down or because you're there's some hidden dump state or you're branching to the empty set or something else maybe you made a mistake。

 maybe you thought it was obvious and just didn't think you could write it down。

 please write it down， please make your your answer is as explicit as possible so that we know that you know why your answer is correct and what your answer is。

Okay。And let's see we've only got two problems left。

 we've got a fooling set and context regrammar question and we've got an induction question。

Inuction I think that's pretty mechanical so let's look at the more interesting problem and this is the one that we actually got to before the last before the review session ran out。

Let L be the language zeros followed by ones followed by zeros where two of those exponents are equal。

 but I don't care which to。Prove that L is not a regular language it should be an A and that should be a B。

嗯。Okay。So whenever we've got a language like this that's got multiple possibilities。

 multiple different exponents。It's really useful to think about special cases where。

You make one or you know all but say one or two of those exponents be as small as possible or have some simple relationship like they must be equal so in this case I think what i'm going to try is i'm going to consider the the the special case。

UmWhere the the the third。Exponent is always zero。系。So now this。Really looks like okay。

 zero to the A1 to the B， nothing。Where either a and B are equal or a is equal to zero or B is equal to zero。

 so it's not quite the canonical non regular set， but it's close enough that we might be able to。

Design a fooling set。Now because they've got this sort of a is equal to C。

 which in this case means a is equal to zero。Condition up there。

 I kind of want to make sure my fulling avoids the value zero for A A and B， so I'm going to let F。

B0，0 star。 This is zero to the a where a is at least one。嗯。Um so。Pick X。Let's say distinct。

X and y from F。And then just to make sure that the greater understands that I understand these sort of supposed to be arbitrary。

I'll write the word arbitrary， okay， so then x is zero to the I and y equals zero to the J。

Where I is some integer greater than month， or equal J is some positive integer and I is not equal to J。

Then let Z。Be well， the complementary string of ones that would work here being this is not the only possibility。

 but let me just try one to the eye。Then xz is0 to the i1 to the I。

This is I can write it differently zero to the I one to the I0 to zero。

This belongs to L because these two exponents are equal。But yz equals zero to the J1 to the I。

This is0 to the J1 to the I0 to the 0。 This is not an L because。

I is not equal to J and I is not equal to zero and J is not equal to zero。

And at this point I can stop， I mean there there's a couple of boilerplate lines of so F is a full set for L F is infinite so L can't be regular。

 you don't need to write this down because they're the same in every proof。对。

This place right here where I said consider the special Kc equals zero。

 that was just a note to myself。The stuff that I've written below that line。

 that is all I needed to write。Now， there's another way of actually doing this。

 which is to like use what we call reduction argument。

So I would say let L prime be L intersect00 star1，1 star。This so far。

Is strength that form zero to the n1 to the n where n is greater than or equal to1。

So let's union that with the language containing the empty string。Right。

This is zero to the n one to the n where n is greater than or equal to zero。Right。Um。

If animal were regular。Then。E Prime would。Be regular。But。That's crazy talk。

that's impossible because we know this is the canonical non regular language。

The the first example of a non regular language that we encountered in class so we we know that that language all prime is not regular and so。

Assuming L is regular gives us contradiction。Toil is not regular。

The stuff in blue is worthful credit， the stuff in red is worthful credit。嗯。

So the the the next thing we need to write is a context for grammar for L Now again。

 you don't need to justify the answer by writing down what each non terminalminal corresponds to although it might help to like write down some notes for herself to just to think out loudud so notice in the definition of the language I've got three conditions connected by an or。

 that means when I'm designing my grammar， the simplest thing to do is just to give myself。

Three conditions and now A is going to be strings where the exponents A and B are equal and B is strings where the exponents A and C are equal and C is strings where the exponents B and C are equal。

系。So a， this is。0 to the a1 to the a，0 to the C， just to remind myself。

 this is the first two things are equal B is zero to the a 1 to the B，0 to the a。

And C is zero to the I1 to the B， zero to the B。Okay。U。Okay。

So I think what I'm going to do here is I'm going to split。

The the the string into the part that you know I kind of know how to do because it's canonical zero to something one to the same thing fall by a bunch of zeros so the canonical thing I'll call that a prime and the the zero to the C that that's just zero star so I can just write that。

Like this。RightThis is zero star again， I don't need to write this explanation down for full credit。

 this is just a reminder for myself。喂。And then a prime is going to go to either。

0 a prime one or it's going to go to epsilon， so this is building up。

The string of the form zero to the something， one to the same thing。By， well。

 it's either empty because that exponent both of those exponents are equal to zero。

 or there's a zero at the beginning and a one at the end that I can strip off and then I'm left with a shorter string of the same form。

Okay。Great， what about B well。B I've got the matching things already on the outside。

 so I'm going to actually use that， so B is either going to be zero B0。

That takes care of the possibility that my string actually starts and ends with a zero。

 meaning that exponent little A is positive。Or I end up in one star， well， let's call that why。

This is one star。Okay so I recursively get rid of matching zeros at the beginning and into of the string until I can't anymore and then what I'm left with is con only of ones。

And then finally， if I look at this language C， I've got a mismatch part and a match part on the left and a match part on the right。

 so I'm going to split that into well I've already got a context free grammar for zero star for the left part and I just need to build a context free grammar for the right part。

And so C prime， that's going to be， this is all strings of the form one to the something zero to the same thing。

 so it's just sort of the mirror image。Of a star， so its just zero to the A1 to the a。

 this is one to the being zero to the B。And so there is my context free grammar again。

 all this stuff that I've written over here。This is convenience notes to myself。

 but I didn't need it for full credit。Okay。Now we are left。With the induction proofs。I'm not really。

 I don't really feel the need to kind of explain what's going on here because the induction proof as a general tend to be relatively mechanical。

 but I am， I'm going to， I'm going to step， you know。

 just step through the thing starting from the beginning。

Prove that bond of w is longer than w for all strings W so I'm going to do the thing that I do every proof a universally quantified statement about strings。

 I'm going to say let W be an arbitrary string。And you can guess that we're going to be doing induction on W so I'm going to go ahead and write down the induction hypothesis。

 which is assumed that the length of。Bond of X。Is less than or equal to the length of x。

For all strings。X shorter。Shorter than。都 you。Right。

Now the definition of the function bond had three cases in it。

 the definition of length has two cases in it， the definition of string has two cases in it。

 so chances are pretty good that my proof is going to have cases that mirror the largest number of cases I see among the various components of the objects I'm looking at。

So I'm at least tentently going to identify three cases。Case one is W is empty。

Case two is W is zero followed by something。In case three is W is one followed by something。

And I'm going to leave myself lots of room and I'm going to write down the proof。

In each of these cases。The length of bond of W。Well。

 that's the length of bond of epsilon because W is empty。

 that's the length of epsilon because that's the definition of bond。

 but that's of W because W is empty。Notice I I'm not writing down the justifications over on the right。

 we're asking for less detail in the exams。Just it needs to be every step actually needs to be a single step when we're doing this。

W is zero followed by another string x， well in this case， the length of bond of W。

 I can write as the length of bond0 x。And again， I can write as0，0。Bond of x。

 that's by the definition of bond。 that's2 plus。The length of bond of x。嗯。Now at the bottom。

 I want to go and I want to get somehow to the length。Of W， this is equal to the length of0 x。

 which is the length of。1 plus。Going to X。I didn't leave myself quite enough room him。

 forgive me for cheating。And somehow I need a less than or equal to in between these two parts。

Complete the proof。So this is less than or equal to one plus the length of bond of x because one is less than or equal to two。

And here is where I'm using the induction hypothesis。And that's the one thing that I will ask you。

 you， if possible to actually mark explicitly。And then the proof for string starting with one is similar。

 so bond of W is the length of that is the length of bond of 1 x。That's the one dot bond of x。

That's equal to one plus the length of。Bond of x。This is less than or equal to 1 plus the length of x by the induction hypothesis。

This is equal to the length of。Oh sorryrry， not a。This is length of 1 x。嗯。By definition of length。

 which is equal to length to W。So in every case。I start with the thing on the left and by a sequence of equalities and inequalities。

 I prove that it's less than equal to the thing on the right。In the case where it's empty。

 I actually get equals， but that implies let's it are equal。So。That's what I need for。系y。

Part B is relatively similar。It'sThe same kind of structure and and it's going to look like a lot of proofs that we use when we like show that concatenation plays well with other functions so you saw this earlier in the homework with the function grow homework one so we're going to just mirror the structure of that proof so let X and Y be arbitrary strings。

You we can guess because we've seen these proofs before that we're going to be doing induction on x and only on x y is going to stay fixed。

 so i'm going to assume that。Bond of Z Y equals。Bond of Z dots bond。Of why。Or all Z shorter than x。

There are three cases again。But something's in the same reason as that word earlier。

 this W is empty theres。W is zero。I'm sorryrry， there's x is empty。

 x is W is as the form zero z and later there's you know x has the form 1 z。嗯。嗯。In this case。Okay。

 we write you know bond of X Z this is。Bond of epsilon do Z， this is bond of。Z。

 this is Epsilon dot bond。Of Z， this is。Bond of epsilon thought。我不知。Which is the same as。Bond of。X。

 dot。B。3。When x is equal to zero z。Then the of X Z， or sorry x Y， sorry。

 this should be Y is all the way through。再碎再碎。Bond of x Y， this is the same as bond of0 z Y。

 which is00 dot bond。Of Z Y， which is00 dot bond。Z dot bond。

Of why this is where I'm using the induction hypothesis。

I'mW it on the left because there isn't room on the right， but myness is clear。

This is the same as bond of0 z do bond of y by definition of bond。Which is bond of。X dot of y。嗯。

And then finally， win is1 z。This is going to give me a some waterproof， so Voda that's y。Is fond of。

1 Z Y。Which is one dot bond。Of Z， Y。Which is one。Its bound of z times bound of y。

This is by the induction hypothesis。This is the same as bond of1 z。I found the way。

Which is the same as。All one does X。Dot。FOf why so in every case。

I start with bond of x y on the left， and I end with bond of x do bond of y on the right。

And each one of these steps is justified by either the definition of bond or the definition of concatenation。

嗯。Now you'll notice that I'm kind of implicitly using in a couple of these places。

 specifically right around here。goinging from here to there to there。

 I'm implicitly using the fact that string con contaminatnation is associative。

So if I really wanted to be careful， I would write out。Actually。

 even just going on to the second stop。It's bond of0 z dot y is the same as bond of 0 dot Zy by associtivity。

We know that strings are associative， I think it's actually okay not to make that step explicit。

 in fact we I don't think we even really counted that off on the homeworks either。

So what I've written down here is sufficiently detailed again。

 without the justifications for each step， as long as it's clear that each step is going， you know。

 really one step at a time。嗯。呃。And even this may be more。

 is probably more detailed than you would actually really need for full credit。And at this point。

 we appear to be done with the exam we have。I answered to every every question， excuse me。

 you answered every question and I need to make sure that my name is on every page so。

We go ahead and do that there's a proof A and B， there's my。

Language proof got two proof straight and one answer for B。

 and then finally here's the true false with reasons。At this point， if there's time。

 go over the questions again， go over the answers again。

 do a sanity check to make sure that I actually believe everything that I've written down。

If everything looks good， then I take all of my paper。

 I stick it inside my answer booklet and I go turn it in at the front of the room and I leave。

And that's the whole exam。Thanks everybody for listening。

 I will do this again for the other practice exam later and post that video along with the solutions to practice exam to on Saturday all right。

 thanks everybody。

![](img/b0fba6a2d8682a66e78168505e9fd071_2.png)