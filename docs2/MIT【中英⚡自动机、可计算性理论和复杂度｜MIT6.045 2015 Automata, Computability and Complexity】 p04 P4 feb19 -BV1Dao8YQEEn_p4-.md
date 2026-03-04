# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p04 P4 feb19 -BV1Dao8YQEEn_p4-

That's better。I can hear that now。Okay， so yes， let's。So， let's get to the equivalence of。

DFAs and regular expressions。So obviously there's two directions to showing two things equivalent。

And let's start with the easier direction that is， given a regular expression。

 you can construct a DFA。And instead of constructing a DFA， I'm going to construct an NFA。

 but we know that deterministic finite stateatmeter are as powerful and not as non deterterministic finite dataometer so this is okay。

So let's start with that。So。So this is the first part of it。Of proof。Given a regular expression。

I'm going to come up back。So by the way， just feel free to ask questions and interrupt me at any time。

Raise your hand， shouted my name， just call me Robin。You know， whatever。

 say something if you have questions。Okay， so we're going to show that given a regular expression。

 you can convert this to a non deterterministic finite state automata。

So there's really only three things you need to worry about when you're converting a regular expression to an NA。

 so you can have really simple regular expressions like you the regular expression， let's say。

Just some constant symbol says zero。So this is easy to make an NFL for， you know just。

you're a star state， star state accepts0。And goes to the accepting state so this kind of stuff is easy you know。

 so if your regular expression is just a zero or the regular expression is just the empty string or if your regular expression is empty。

 like it doesn't accept any strings whatsoever， that's easy to make as well。

So these are the easy things to do。And it's kind of straightforward。

The the more complicated operations that are allowed in regular expressions are。

Taking the union of two regular expressions。 So let's start with that。 That's something。

No trivialvial， so you have some regular expression R。Which is the union of two regular expressions。

Right。And so how do we do this？Let's assume that we have NFAs for both R1 and R2。

 and from this we want to construct something for the union of R1 and R2。Let me。

Let me get to any of that here。Let's say this is a NF orR1。And this is an N art too。

So it has some starch state。And has a bunch of accepting states， sure。

And maybe this one is three accepting states， maybe that one has two accepting states doesn't really matter。

 and what I want to do is I want to construct one NFA that accepts the union of these two languages。

So。Okay， does anyone have any ideas on how would we do this？

So how would we construct one NFA using these two NFAs that accepts either strings in R1 or strings in R2？

Yep。这个理。Right， so add a start state with a free transition to both of these。

 it's a no transition or an epsilon transition， this is our new start state， that's right。And。

 and that's it， right。Yeah yeah you don't need to do anything more。

 the accepting states remain the same and the reason this accepts the union of the two languages is of course。

 if the string is an r1， it could have gone here and done this whatever is here and reached one of the accept states。

 if it's an R2 it would have reached here， done whatever and reached one of these accept states。😊。

This whole thing is an NFA for。The regular expression R， which is the Indian of these two things。

Okay， so this shows that if you have。Two regular expressions， which you know how to construct NFs4。

 you can construct one for the union。There's two more operations you can do with regular expressions。

嗯。You can。You can do the star operation。So how do we do this， so now we have some。

Have some regular expression for R。And we want to construct a new BF sorry we have an NFA for R and we want to construct an NFA for R star。

 So how do you do that， you have some starch stick。You have some accept date。Okay。Okay， yeah。

 what do you guys think， How do you， How do you create a。Regular expression for our star。Any。

Any guesses？Because of yeah， good。So the accept states go back to star state。

 yep that's good with null transitions。Okay， that's good。 And does this work。Right。Right， okay。

 so your idea was。The star state should be an accept state because we need to accept themp string。

 we need to accept epsilon， but the problem is if you make the star state and accept state the star state could be an intermediate state in this NFA and you might make other states become accept states。

 this is not a big problem because。Right， so just add a new。Starch state。

 which is also an accept state and make an old transition here。 So now this guy really does accept。呃。

R star， if this box accepts R， this whole nA over here accepts R star。And。Lastly。

 what do we have left we have。The only other thing you can do with regular expressions is you can concatenate them。

C。Yeah， but regular expression R one， you have another regular expression R2。And you can just。

Keep this here。You can concatenate them in a sense。That。

You can accept strings where the first part is in R1 and the second part is in R2。感じでよ。Okay。

 and okay how do we do this？Anyway， so you want to extract strings that are or the first part of the string is in R1。

 the second part is an R2。Yep。That makes sense。Do this and then we don't want these guys to be accept states anymore of course。

 because otherwise， you would accept strings that are just in our one。

So get rid of the acceptance here， get rid of the acceptance。Stayed here。

And now what does this NA accept first you have to accept something in R1。

 then you get to go here and then you accept something in R2， these guys remain accept stage。

And that's pretty much it。They let me。です。There's only three interesting things you can do with regular expressions。

 union。Star and concatetnation。And using these properties。

 you can build up an NFA or any regular expression。And maybe let's just see a quick example。嗯。

And maybe you have the following regular expression。Something like this。

So if you break this up into smaller steps here， this is zero concatenated with this guy。

 concatenated with one， and this guy is just。0，1 or 10 stard。 So you create a machine for。

Start with the inside guy， let's say you want to create a machine for a01 or 10 star。

This is a machine that takes。This is01。1，0。We won their union， so you use the union rule over there。

 which is。New startt， epsilon transitions here， epsilon transitions here。

These guys remain accept steps。So this accepts 01 or 10， then we do the star operations。

 so wheres the proof of star。So over there we had。Epsilon transitions back to the star state。

 epsilon transitions back to the start state。At a new Star state， which is also an accepting state。

Epsilent transitions this way， so this is now 01 or 10 start。Now we need to accept a zero here。

She left some more room。This is a state that goes in here。Only have a zero， and this is a star state。

So that was the concatecnation operation。And。We need another one here。

So I'm going to concatenate again。So this is a DFA that accepts one。

We have epsilon transitions this way。Thisis guy is your final stay。And。You need。

You need epsilon transitions to the new guy from all the accepting states of the previous guy。

 so this was an accepting state， this was an accepting state。

 and this was an accepting state you need an epsilon transition here as well。Okay。

 so this should be NFA for this regular expression over here。嗯。

And the way to see that is so you come in， you have to accept a0。

 then you can skip all the way to the front and just accept a one and go ahead so that'll be like ignoring this guy over here。

And otherwise， you can loop around here as many times as you want and go through and that'll be。

Accepting some number of copies of 01 or 10。Okay， so that's an example of how you do this。

 any questions about？This example or just a general process of converting regular expressions to NAs。

No， kind of makes sense。Okay， okay， so this was。Easier direction of the proof。

 converting regular expressions to interfaces。Let's do the。The slightly harder correction。Which is。

Given a DFA， you can convert it into a regular expression。Okay， so how do we do this？

The way we're going to do this is were going to introduce。An intermediate。Machine model。

 which I'm going to call a generalized non deterterministic finite state automaton。And。

We're going to convert a DFA to this more general object and this general object back to a regular expression。

 And this is going。Complete this part of the proof。 So so what is a GNFA， A GNF is， basically。

 it's an NFA with regular expressions on the edges。 So the transitions now are not just。

Sybols from your alphabet， but you're allowed to have just general regular expressions on the  errorss。

 so you know something like。This is your start state， this is another state。But usually in an NFA。

 you'd have something like zero or one over here， but now you're allowed to have。

A negative expression like this。And maybe this is another state。And this is， you know。1，0 or01。Yeah。

Yeah something like that， so it's more general than a DFA because now you're allowed to put in not just symbols from your alphabet。

 but also just full regular expressions on the errors。And。

But what we're going to show is that you can actually。

Reduce this object of a regular expression so that's going to complete our proof So this generalized non-deteristic finite at make sense。

 so the arrows just have regular expressions and you can get from here to here either by going through these arcs and then your string would have to look like 01 star 10 or 01 star01 or you can go this way and then your string wouldt have to be 0 star。

Deide。Any questions about what this GNFA object is now， okay， and for convenience。

 we also impose a couple of other things on this。This object。

 which is we asked there to be a unique accepting state so there's only one accepting state。

 this is not a big deal because you can always add one accepting state。

 make all the other accepting states point to this guy with no transitions and just make the other guys not be accepting state。

 so now you just have one。嗯。We also insisted。There's。There's no incoming edges to the state。

 so the start state must look like this。It must have errors going out only no incoming errors and the accept state。

 of course， and the accept state must only have incoming errors and no outgoing errors so we're going to impose these two things。

 but these things are easy to do， you just add an extra search state。

 add an extra exc state and ensure that it has this property。And。And the other thing， we're gonna。

Infor is that， I mean this is a trivial thing， but if you have two arrows going from this guy this node to this note。

 say I' no。0，1 star or0， you should combine them into only one arrow。Like this。

Because you can combine regular expression others。There's nothing deep going on here。

 it's just something we impose on this object just to make life easier。Okay， so this is what a。

Generalized non deterterministic finite state automaine is。Okay， any questions about that。

 just what is this thing？makes sense。Okay， yeah。Okay， so let's say I give you a GNFA。

With only two states， I'm going to write the GNFA2， what does that look like？

It has to have one star state and it has to have an accept state， as we said， and these guys。

 the start state can only have outgoing arrows。 the accept state can only have incoming arrows。

 and you can only have one arrow between two pairs of statess as we said so。

There's one arrow with some regular expression here。So this is a GNFA of two states。

And what language does this express， It expresses exactly the regular language。

Expressed by this regular expression R。So if you have a GNFA with just two states。

 the regular expression for the languages except is just R， so there's no work that you need to do。

 it's just written right over there。😊，So GNFA with two states is great because we're trying to convert a general GNFA to a regular expression。

 but if you know that you have two states then you're done like your jobs over。

 so what we're going to do is we're going to convert a GNFA with a larger number of states。😊，Do。

See a GFA with k stakes。Into a generalized NFA。With k minus-1 states。

And if we can show how to do this while preserving the property that of course they accept the same languages。

 not the same language， then you can go from k to K minus-1 and you can keep doing this till you get down to two once you get down to two。

 you just read off the regular expression from the arrow and then you're done。

So that's the sketch of the proof， so I just need to show you how you do this step。

 how do you go from a K state GNFA？To okay minus1 state G。

And the way to do this is how do you reduce the number of states？Well delete one of the nodes。

 or delete one of the states， like that's the obvious way to do it。Let's say。

This is a part of an NFA， I'm just showing you two states。Two arbitrary states the QI and QJ。

And this is some state that I'm going to delete， so let me call it Q delete。It a Kel。

So there's other states in the NA， but right now I'm just focusing on these three。

And this is the state I want to delete and what I want to do when I delete this state。

 of course you're going to break the NF and you want to repair the N the rest of the N so that everything still works out。

 so let's say， for example， there was some regular expression here or one there was some regular expression here or two。

😊，And our three。This guy itself。Ato， our four。Okay。嗯。Okay， let's say this is the thing。

 and now I want to rip this guy out of the machine。

And come with a new transition function between QI and QJ that still accepts the same set of languages。

So how do you do this so。Our one remains， of course。R1 is good。

 you can still reach Qj from QI with R1 and what about this guy so what about the paths that go through to QJ from QI。

 they had to pass through this loop and the only way to do that is if you first accept，A2。

Then you're here and you can loop around here as many times as you like。

 so copies of any number of copies of R4。That's our four star。And then R 3。That's this。 And then。

 of course， we had this constraint that you want to have a unique arrow。 So let's get rid of this。

 And then let's just do。R1 or this guy。So what this does is for these two states， QI and QJ。

 what I've showed you is that if you delete guy this state QL。

The languages that the strings that have were gone from QA to QJ still remain the same， so I haven't。

I haven't changed the functionality of the NFA with respect to these two states。

 but now you need to do this procedure for every pair of states that's once you delete QL。Question。

Yes， yes， yes。 So in my example， I didn't have any arrows going backwards， but yeah， you're right。

 So let's say if you had an arrow here。嗯。Our five。R six， right， so there's anarrow going this way。

And now there's a possibility of going that way， which is。呃。You could go this way。With our five。

 our four star， and our six。5。Our four star。R six， and if there was originally some presentationation like this。

 maybe it R 7。Then you'll get another guy over here。So。

So this is the process of ripping out one state from your GNFA and still preserving the language that the GNFA accepts。

Yeah does that make sense to people？Good。Yeah， question。UJ， you can go to you Dman back to。

Yes we can。Yes， yes， yes， yes， All right， yes。 once I added this。

 you have to take care of that as well。 So when I said you have to do this procedure for every pair of stitch。

 this includes the pair of stitch being the same guy。

 So we also have to do this for now that we added the back loops， you also have to think about。😊。

Things going from QI to QI and things going from QJ to QJ。 So how can you go from QI to QI？

You through this， you can go， well， this way， it's R2， R4 star R6， so you're going to have to add it。

A seventh flupi R2 our four star。A six and over there， same thing you're going have to。

Add a self loop for this path where you take R 5， R 4 star and R 3。 That's right。

 So when I say for every pair of states in here in the residual。

NF so the NFA that you're left with once you' killed this state for every pair of states you need to do this procedure and just check。

That is there a way I could have gone from this state to this other state through the state I just deleted and if there was a way to do that。

 you need to fix this problem because you just deleted that state and when I say every pair this includes just the pair being from a state to itself。

And so this remedies the situation where you' killed one day。

And this is in general how you go from a K state GNFA to a k minus1 state GNFA。

 and you keep repeating this process until you come down to a two state GNFA。

So this is basically the idea。Okay， any other questions about this？Any。

Any questions in general about the equivalentvalence of regular languages and finite state Atmeterta？

Makes sense。Okay， one nice thing to observe in this proof is。

What properties of regular languages did we use when we this when we do this proof。

 so the characteristics of regular expressions that we used are we use the ability to do the union。

When we combine two errors。We needed the ability to do the star。

 that's when you had self loops here and we needed to concatenate things because when you take an edge this way。

 you take a path from here to here and come here， you need to concatenate two different regular expressions。

And these are exactly the properties of regular expressions。

 like regular expressions are exactly those things you can get by doing these three operations。

 As we saw in the other half of the proof that these were the only。

These are the only complicated things。 the other things that regular expressions can do is they can be consed。

 but that somehow， that's clear。😊，So。I mean， this proof shows you in both directions that。

You know GNFAs are exactly capturing the power of regular expressions。

 we haven't missed out on any properties like that would be bad if you didn't use all the properties of regular expressions because then you know something's haywi or maybe you had too many properties and some of them were not needed or something。

 so I mean it's nice to observe that we used all three non-trivial properties of regular expressions in this proof。

O呃。Okay， any questions about that。Nope。Alright。Okay。

 maybe before moving on to context relay grammars， heres。Here's a question。

So say r is a regular expression。😊，And so my question is is？

Our complement regular so what I mean by this is。R describes a language over some string let's say zero comma1 star so it's over the set of all binary strings and our complement is the language of all things that are not in our so it's just the complement of that language now is that language regular so notice that we did not allow the complement operation this bar operation in our definition of regular expression so this thing as I've written is not a regular expression。

But the question is， yeah， is this language regular or not？So， does anyone have a guess？Fucks。Or。

Beliefs。Just random ideas， anything go， good， maybe you could just take all your exact date。

That states and take your。Right， so that's something you can do with the DFA， so that's right。呃。

So you started with a regular expression。And so one thing you to do is following your strategy。

 take the regular expression， go through this proof， so from the regular expression。

 I mean go through that proof， construct an NFA from the NA construct a DFA and then swap。

All the states that are not accepting column them accepting states。

 all the states that were accepting call them not accepting states so that's going to complement the language for the DFA and then from the DfaA if we come back to a regular language okay if you just want to show it's regular then that's fine。

 but if you wanted to actually construct a regular expression for our compliment。

 you'd have go through this whole loop of reductions that we just did today and then you would indeed come up with a regular expression for this language but that might be pretty complicated because you went through a whole bunch of reductions but the answer to this question is yes。

 if you have a regular expression R itss complement is also regular that is a regular expression expressing the complement of this language but it's not easy you can't just。

You know just get it out of this somehow you have to。

 or at least the only way I know how is to go through this long procedure。And。

And there's some way to show that， I mean， something like this is necessary because this procedure actually blows up the size of your expression and some blow up in size is necessary。

😊，Something that you can show anyway， so this machinery gave us something interesting that it was not clear a priori that the complement of a regular expression is also something that can be expressed by regular expressions if I just shown this to you before giving this proof。

 you would probably have no idea of how would you ever construct a regular expression for our complement。

 but now this proof gives us some payoff that you can do this。This proof also gives us other payoffs。

 like showing you this way of expressing languages is completely equivalent to this machine model。

 which is nice。😊，So yeah， of course。The自で。This G event is something there。A string。

Then in the ending my end。Right。But how， how does it read like from a note。

 you have many regular expressions of how do you know which。It's non deterministic。

 so you just say that this G accepts a string。If you can write the string as。

Having gone through this GNFA so you even though there's two arrows coming out here。

 it it's not like a DFA where it needs to make a decision its just you can think of it as making all possible decisions at the same time and then as long as there's some way to reach an accept state it's accepted。

Or in other words， you can say that at the end of the day after you look at the string。

 if there's some way to fit the string so that it looked like this。Expressions， then then it's fine。

 you accept So just like in an NFA， you had these， you could have something like this。

With a zero transition here。And a zero transition to another state。

And you know and something so on and then you might say where does it go and well one way to think of it is it goes everywhere simultaneously。

 but at the end of the string， if any of the branches。

 you know if any of these worlds were you've gone somewhere are an accepted， then you've accepted。

Yeah， yeah， yeah。 That's true。 So when youre at different parts。

 you could have used it used up a different number of symbols。 but， but that's okay， you know。

 it's like。It's like， saying， what are all possible things that can get you from？Here to here。

It's either just zero or it's 01 or 01 star。And that's fine like all you need to do is to show how to get here using some path in this NFA like it's okay that the lengths are different like it's not easy to visualize this。

 but if you write down a formal definition with transition functions and so on。

 you'll see that I mean all you really needed was to be able to express the string in terms of just a concatenation of these regular expressions it works out even though it kind of seems non- intuitivetu why you're able to accept different lengths of things。

Does that someone answer your question？什么O。We can talk more reference class if you like。Okay。

 let me move on to context free languages unless there are more questions。Any more questions？O。

So context free languages or context free grammars。So this ends our。Section on regular expressions。

 DFAs， so on。And we can now more too。So context free grammars。Okay。

 so this is a concept that's probably easier to explain with the help of an example。

And let's start with this language。The set of all strings such that。X is a Bain room。

So I think we saw this last week， a palindrome is a string that's the same when you reverse it。

And this language is not regular， think。I think Scott proved this last name。so you cannot。

There's no DFA that accepts this language， and you can show this using the argument that Scott gave last time。

 or you can use this pumping dilemma for regular languages。Okay。So let me。

Let me describe to you the following way of generating strings。Like。A strange way of doing this。

Let's just look at this example， so I have some variable A。It's just available。

And there are a set of things that I'm allowed to do with this variable， so this variable。

 you're always allowed to replace it。With。You're allowed to make。

Substitutions of the following front whenever you see this variable a。

 you're allowed to replace it with 0 a0。Or you're allowed to replace it with。1， a one。

Or you can replace it with。嗯。Just one of the constants， a zero a1。Or just a null string。

 the empty string。Okay， what does this mean？So what I mean by this set of rules is you have to start with A。

And so these are five rules that are stated for rules of substitution for A。

So you start by just writing down a and now you're allowed to invoke any of these rules and make a substitution。

 so say say I invoke this rule over here， the third rule。And what happens is say。

This is simple for making a substitution according to these rules。From a you sub the a with a0。

 and now you're left for the string in your alphabet to 0 comma 1 star， and then that's it。

We say that this is the string。Generated by this sequence of。Substitutions。

 so let me do something more complicated。 So you start with a。We make a substitution。

 let's say we use this rule over here。And now we have1 a。One。And now this A again。

 we can substitute using any of these rules， maybe we use the first one over here。So。

So one stay now the a is going to get replaced by 0 a 0。 so you get 10 a 0。 and this one。

Its just here。 So now we get that string over there。 And now again。

 maybe I want to use one of these rules， Maybe I use this rule over here。And。I get to10。

 and I'm going to substitute a with the 1 using this rule， and I get say this string over here。

So this is a sequence of substitutions from this list of substitutions that I was allowed to do。

 and at the end of the day I got a string over0 comma 1 star。

So we're going to say that this string is also a string。Generated by this set of rules。

And so this is a set of rules， and the set of strings it generates is all the strings you can get using this procedure。

And this defines a language， right， So the language is the set of all strengths that you can get。

Using these rules。And。嗯。And， what do you think this language is？And you know， well。

 I've kind of written the answer here， so it's not a very interesting question。

 but this is the language of all palindromes， so this is a palindrome。This is also a palindrome。嗯。

Okay， yeah， why is this happening and well one way to view this is。

you can view this as building up palindros using smaller palindromes。

 so these three rules essentially say that。The empty string is a palindrome， well。

 you know there's nothing in it， one is a palindme and zero is a palindrome。

 these are the three things that we know are palindromes， and then given a palindrome。

A way to construct a palindrome is putting by zeros on both sides of the palindrome or by putting one on both sides of the palinrome。

 this preserves palindromeness。Paenro Mesi。Whatever the word should be。And。

So what this set of rules is saying that think of all the strings you can construct using only these rules。

 like you start with something that is a pallonrome， one of these simple ones。

 and then add zeros on both sides or add ones on both sides。

And what I'm saying is that this set of roles actually captures the language of palyinros like you can exactly only express palyindros with this and you cannot express any other language。

 So this is a procedure for generating languages and this kind of procedure is what we call a context free grammar。

😊，So。Okay， does this example kind of make sense？Like so more formally。

 what's happening is you have three steps and you have some steps， which is。

So once you're given a context programme grammar like this， you're also given a start variable。

 which is always。By convention the first variable in your list of rules。

So you write down the start variable。So that's what we did， we wrote down the start variable。

And then。Now you're allowed to substitute any variables that。Any variables that appear？

Using the rules。And yeah。And you keep doing this repeat too。嗯。Until no variables remain。

So this is the procedure that I was following informally。

 so I wrote down the start variable and then I'm allowed to use any set of rules I like。

 any substitutions for me that I like。Only from this list， of course。

 until all the variables are gone like at this point the variables are not all gone。

 so that's not a string accepted in the language， that's not even in0 comma 1 start。

 so you have to end up with a string that's in Europe。😊，Like in your alphabet。

And so you keep applying these rules as many times as you like until you left with the string that has no more variables in it。

 and that's a string that's accepted by this grammar。Okay。

 so this object is called a context programmemar。There are some names for things like this is called a start variable。

This is called the start variable。 There's only one start variable， and traditionally。

 it's always the first variable in your set of rules。 These are called。Substitution rules。嗯。

These things are called variables， like in this example， the only variable is a。

These guys zero and one。They're the alphabet， they're sometimes called terminals because that's when your thing ends。

 your computation ends when you're left with the string of only terminals。

 so it's like the computation is terminated， so that's where they call terminals。Yeah。Yes， yes， yes。

 yeah， you can have more variables。 Yeah yeah， so I'm going to give you another example of a more complicated finite of a more complicated context for gammer。

 but maybe five variables and you know and know a couple of variables appear on the right hand side of each thing So only one variable can appear on the left because this is a rule that's telling you how you substitute a variable。

 but on the right hand side you can have more than one variable appearing like this rule could have been 0 a0 a。

😊，A curvebin 0 is0 BCD and for other variables， BCD that I haven't introduced。嗯。

I'll get to a more interesting context for gammer in just a minute。But。Yeah。

 this is just a very simple example。 and what I wanted to say is that this procedure。

 where you start with the start variable and the keep making substitutions。

 this whole thing is called，😊，A derivation。And you're said to have derived this string from this context programmer。

Yeah。Right so this context for as I explained accepts only palindros。Right， okay， so is the。

In this simple case where there's only one kind of variable A。You know。

 I haven't given you any more a complicated example。

 is it kind of clear what kind of strings you're allowed to generate？

You knowYou're allowed to use these rules as many times as you like and end up with a string that has no variables in it。

 and that's a string in the language。Any questions about this？This concert makes sense。

You'reCon about something though。Okay， let me。Let me do another example。

Let's move here from last say。嗯。Okay。Actually， instead of doing another example， let's。嗯。

Let me just define a certain a couple of things more formally。

 like we don't really need to use these formal names too much，Just so you know， as I said。There's。

There's usually a couple of things that define a context programme and there's four things。And so。

 it's usually。A tuple like this。对。So this is a set of variables。So this example。

 just the set of variables was just。There's only one variable a。This is your。This is your alphabet。

 this was just  zero comma1。This is a set of rules， so this was this whole block of rules over here。

 and this is the start stay。Which is some variable from the set of variables。Formerly。

 we'll define a。A context figure like this。I'm just writing this。

 so this is the terminology we're going to use。Variables， alphabet， set of rules， start state。Okay。

 let me give you a。Another example of a finance aid of a context gra gramar。 Let's say you have。Okay。

This is an example of a context programmemar。So what it says is if you see the variable E。

 you can replace it with E plus E， so okay let's again write on what is the set of variables here。

 there's only one variable E。What is the alphabet？So what are your terminal symbols？It's0，1 plus。

 and x。So these are all terminal symbols as well， you don't substitute them any further。

 they're not variables。And this is your set of rules， and your star symbol is E。

So what kind of strings can you generate using this rule？So。Okay。

 maybe some someone give me an example of a kind of string that you can generate using these rules。

Maybe let's go that way。Just a very simple example。Doesn't， sorry。One plus one， Okay， that's great。

 So you can generate one plus one。 Okay， How do you do that， You start with E。

YouUse the rule E plus E。And then you substitute use this rule for， say the first E。

And you get one plus E。Then you use the same rule on the second E， and you get one plus one。Okay。

 yeah， that was easy。嗯。Okay， similarly， you can get other strings。

 maybe you can get you can get one plus one times one。You can think about how to do that。

 I'll show you how to do that in a minute。Okay， what about this string， Can you get one plus。Plus。

 one。What do you think can you get the string or can you not get the string？No。

I see some shape heads nodding， right。 That's right。 You cannot get this string。

 if you stare at this expression for a while， you'll see that。It's not possible to get something out。

Anyway， so this language generates some kind of set of arimeical expressions。嗯。

And these kinds of expressions are not generated by this language， some are。So look。

 let's take this guy again and let's do this in。Let's look at how to derive that string over there。

So， you have E。So maybe I the rule， maybe I use the multiplication rule。Any time see。

Then maybe I substitute the first E with the plus rule E plus E times C。

And then maybe I said you the first guy with a one。

There maybe I substitute the second guy with a one， so one plus one times E。And then the third row。

ok。And this is how I got the string。 Okay， does this derivation make sense。

 this is how you get the string。Okay so there's another way of viewing these devations that's a little more interesting than writing it out like this because this is kind of annoying。

You know， painful。Which is you think of it as a tree。So you have some E here。

This is your start variable， and then I use this rule， the E times E rule。

You draw a tree and you say E。Times E。And then this E， I expanded using the E plus E rule。

So this is E。Plus， e。And then this EI replaced with a one。

This E I also replaced with the one and this E I also replaced with the one。

And then given this thing， what you do is just。Yeah。Drag these guys down here。

 so I take this guy down here， you get it。just move everything to the bottom line。

 so you get to see the string that you accepted， you accepted one plus one times1。So。

This is a nicer visual representation of how the derivation was done。We started with E。

 We first used this rule， Let me use that rule。 And then this is a string we obtained at the end。

 So these things are called。Paarse trees。And。They're a nice way of showing a visual representation of how you did the derivation。

Okay。Yeah， okay， any question about this par tree， Like does this this concert make sense。

 All you do is。Start right， you start variable at the top。 That's the root of the tree。

 And then you keep applying the rows in this way。And at the end of the day， just for convenience。

 you write these symbols down at the bottom so you see what's the string you've accepted。

 you can also see the string you've accepted like this unit ss， it's one plus one times one。

It's nicer to write them down at the bottom， so you just see at a glance what you've accepted。Okay。

 does this notion of a parts stream make sense？And you can come up with parts trees for this string over here as well。

 maybe I'll do that。I have some space over here。So this devation over here。😊。

I can show you a pary for that。So we started with the video A。We use the rule that a can go to 1， a1。

So 18 one。Then we use the rule that。A can be replaced by 0 a0。Zero is zero。

And then we use the rule that A can be replaced by 1， and so the string U。Accepted is。

So this is a string you accepted。1，0，1，0，1。So this is a par stray for that sequence of derivations all that。

Okay， yeah， so this concept makes sense。It's nothing too deep going on here。

 it's just a way of representing this generation。Okay， no questions about this one。Okay， that's good。

So actually， the reason that context free。Grammars， context free languages were invented。

Is to model natural languages like English so on， as opposed to programming languages。

And it was actually invented by a linguist， Noam Chomsky， who was a professor here at MIT。And。

The reason he came up with this。Was that natural languages have this behavior of。

Of context free languages。 And let me give you an example。So。

And what I'm going to show you is that an English sentence has some kind of behavior like this。

So so what is a sentence So a sentence is something like， you know。

 a very simple kind of sentence would be you have some kind of。Let's see。But。I'm going to call it a。

A complex noun。Let me me yeah let me call it a complex noun phrase。

 a word phrase and a complex noun phrase。 Okay， so you know， it's like。You know。

Jim likes basketball or something。 So， you know， there's a noun， noun like object。 There's a verb。

 There's a noun like object。 And then you have some rules or what kind of things are allowed to be complex noun phrases。

 so。I have some example over here。 So what you're allowed for example。

 is you're just allowed to say a noun phrase or maybe allowed。

A noun phrase with a prepositional phrase， a prepositional phrase is something like， is it？

Insteads of saying you know， gym likes basketball。Jim。With a hat or with the hat likes basketball。

 I don't know， you can modify your noun with the preposition here or Jim on the mountain likes basketball。

So oh， I haven't introduced this or notation。Let's just look at this。Think over here。

 This is a very cumbersome thing to write。 If I I write down my rules like this is kind of annoying。

 It's nice to just combine all of these into one rule， which is just E can go to E times E。😊。

Or it can go to E plus E。Or it can go to zero， or it can go to1。

So this is a very condensed way of writing down this system of equation。

 they're completely equivalent， but this is just a nice way of writing it。So， you know， in English。

 so you might say that the subject of this sentence could either just be a noun phrase。

 and maybe we're going to say that a noun phrase is just an article times a noun。So article is。

 you know。对了。And nouns are like， you know。Whatever。Boy girl。You know？Things like this。

 so you can come up with a set of rules like this to describe simple sentences in the English language that maybe you have to have a noun。

 you have to have a verb， you have to have a noun， but these nouns and verbs can have more things going on。

 the verb phrase can be a combination of a verb with some kind of。

 again a prepositional phrase that says something like you know。

Somehow describes the verb happening and so on。Anyway， I mean。

 I don't want to write down an actual context for even for a subset of the English language because it's really complicated。

 And of course， the set of nouns is like， you know， there's like 10000 words there。

 But this was some of the idea。 This is why。Linguists came up with this idea。

 Ro expressed natural languages。 and while this hasn't really worked out that well， I mean。

 you know natural language is are really complicated。😊。

But context freemars are really nice to describe programming languages because programming languages really are very very structured and you can actually describe them like this。

 They're nice to describe。Many kinds of things。And。HtM， for example。

 if you've seen an HTML page source code the valid HTML programs are also a context free language。

It's a whole bunch of nice things you can express with context free languages because regular expressions and regular languages are are just not powerful enough。

 So we need a little more power， and then you can express a whole bunch of useful things。😊，So。嗯。

I'll give you another example of something from the English language a little later。

 but this would be cubersome to write down a full grammar for， but there's a nice example in。

In the Spsster book。Where he actually sketches out a whole bunch of things here with a limited vocabulary。

 obviously not in all words in the English language that would be crazy。

 but just with a couple of nouns， a couple of verbs， couple of articles。

 a couple of prepositions and so on， and you can see that all the sentence you construct are actually meaningful sentences。

😊，You knowIt's a nice way to think about context for grammars。So。Okay， so let me just。

Let me ask you guys a question just to see if somehow things are making sense。

 So let's say our alphabet is。Aby。And now I have the context programmer。As is the start state。

The start variable。It's ASB。Or。S， S。Apsilon。Okay， so can anyone describe in words to me what？

This context programmer is expressing， but just。Let's just throw out some ideas and tell me what。

Give me some examples of things that the context programmer accepts or what is it trying to do。

 or what kind of strings can you generate with this。Thirdhor an example， third an explanation。

Half picked idea。Random thoughts，ep good。Right， kind of looks like open and close parentheses。

 That's right。 So if we think of A as you know open parentheses and B as close parentheses。

This is saying that。If you have an expression， you can replace it with so I'm just going to replace the envy with open en closed parentheses。

So what is it saying？So S gives Epsilon means just the MP string is accepted by this language。

If a string is accepted by the language， then you can put those two strings right next to each other。

 that's also fine， or you can put parentheses around that string that's also fine。

 So this exactly describes a set of languages that have properly nested parentheses。

 so you know things like。You know。This is fine。This is fine。呃。This is not fine。

So this is not in the language。Because app parentheses are wrong。嗯。You can。This is also fine。

 this is a correct way to nest parentheses， however， I don't know。This is wrong。And this。

This grammar that' described over here only generates the things that have correctly nested parentheses and does not accept objects like this that are wrong。

Okay， that' that。Does that make sense？So why do we build the rules like this。

 because this describes what is a valid expression？The empty string is a valid expression。

 If you have two valid expressions， you can put them side by side。

 That's also a valid wave correctly。Nesting parentheses。

 and if you have an expression you can always put parentheses around that， that's legitimate。

 of course。And。And that's it， this is a way to describe this language。Yeah。

 and incidently this language is also not regular， you can prove that。诶。Yeah， okay。

 any questions about that？Why is this not regular？What's going on， what is this language？No。

 very good， okay。So。Okay， so。I've described context free languages to you context programmes。 sorry。

 maybe I didn't define the term context free language。

 So a language that is generated by context programmemar is a context free language。Yeah that's。呃。🤢。

Straightforward definition。So if you can come up with a grammar that expresses a language。

 then that language is said to be context free。You just like a regular language is one that can be accepted by DFA。

Contractt free language is one or context free grammar。Okay， so。

We can ask some of the basic properties of context free languages。嗯。Like。

So these are the same kinds of questions that we asked about regular languages。So for example。Cl。

 closer under union。Which means。呃。You know， given two context free languages。

 L1 and L2 is the union of L1 and N2 also a context freer， a context free language。嗯。Okay， yeah。Okay。

 any guesses or any thoughts on this？Do you think the set of all strings that either are in L1 or an L2 are context free language？

Mpon for gramer。Yes， no， I see some， y， going。Right， that's exactly right。

 So let's say L1's program looked like this。 The grammar looked like this。

 say start one goes to something and then。A whole bunch of rules， I don't know。

And this guy ahead some。Some other start variable， and you can create a new thing that just says S goes to either S1 or S2。

And then you copy down this set of。This set of rules。Copy them both down here。

And what you've done is said you start with S， and either you can substitute S1 or you can substitute S2。

 and then you would just follow one of the derivations of these two guys to get a string that's either an e or royal2。

😊，So this shows you the context programmes are indeed closed gender unions。hich is a nice property。

まです。Right， so what you should do first yeah， so that's a good point So if this has any variables that are same as variables over there。

 you should change the names of all the variables so make sure that none of the variable names here。

😊，Coincir with any of the variable names here and then what that'll ensure is if you make substitutions if you started with S1 like if your first substitution was S1。

 you will only have a bunch of variable names that are from this block and you cannot get any variables from this block so you will never use the rule from this block and similarly if your first substitution was S2 you'll only have variables from this block and you cannot have variables from this block so that's a very good point you need to make sure that your variable names are different otherwise you'll start and you'll use rules for this guy here and you'll mix up the two languages and then。

You'll probably create string that are not in the language。O。That's good， Okay。

 here's another question。Is the set of regular languages。

Contained in a set of context free languages。So we saw an example of a language that was context free but not regular。

 know， for example， this one or just palindromes。But。

Is context free languages a super set of regular languages or are they just like incomparable。

 like there are some regular languages that are not context free and so on？So yeah。

 do you guys have any thoughts on that， Why is this true？嗯。I mean。Kind of the way I've set things up。

 it kind of seems clear that context programmers are a more powerful model of computation。

 so you should be able to cover regular languages， so it is true。😊，Okay， so let me。

Let me give you an example of how you would do that。So say you have a DFA like this。

 you a Q0 goes to。I don't know。It accepts indo stickkia1。Maybe the except B and stay here。

Q2 is the exception day。This is available to see。Okay。

 how do we come up with a context parameter gramar to express this。

 so we're going to come over with one symbol for every state of the  finitex state machine。😊。

So say we have a symbol Q0， this variable  Q0 which corresponds to this guy over here。

 so this is a stark variable which corresponds to the fact that you start at the star state over here。

 this is the star state。And what the substitution rule tells us is you can go from Q0 to say Q1。

 but you have to accept an A before it。So this is a variable Q1 that corresponds to this node over here。

That we have another rule from Q1 which says that from Q1， you can stay at Q1 if you like。

 but you need to have a beam up front。Or you can go to Q2 if you like。

 but you need to get a C upfront。And Q2， which is the accept state。呃Just。Goes to the Nell string。

 so this is like we terminate。So if you stare at this context for grammar long enough。

 you'll kind of see that this exactly accepts the strings accepted by the TFA over there and no more。

That shows you the regular languages are part of context for。Other part of context free languages。

Okay。诶。Okay， that's probably okay， maybe here's a fun question， what about？呃。

So what about complement？So if I have a set of languages， L， that's a context free language。

 and if I complement this， a set of all languages that are not set of all strings that are not part of this language。

 is that a context free language？2你。Any thoughts on that？Yeah。

 this is not clear right even for regular languages。

 we had to go through this whole rigorole of converting between machines and here it's not clear and in fact turns out it's not true at all。

 like this is not true。😊，Their set of languages is not closed under the implementation operation。

Yeah， that's an interesting fact。Okay， so here are some。

Some interesting properties of context free languages。

That you might use that are also useful in constructing contextory languages。

So if you have a context free language for L1 and L2 and you want to get one for the union。

 you can just use this idea if you have a regular language you can always convert that。

Here are some properties that help you to construct stuff。Okay。Okay。

 maybe let's come back to this example over here。Okay。Okay， so this was our。

This is a par tree for a particular expression in the language。That's not here。Right。So yeah。

 we had the set of rules somewhere here。Ego st。E times Z or a plus D。Pci seat number one。Okay。

 and what we did is we gave a derivation for this string over here， this was this sparse tree。

 and now let me show you a different derivation for the same string。So we first use the times rule。

 and then we use the plus rule， that we got this string here。

 What you can do is reverse the order of using these rules。

 You can first use the plus rule so you can get。E plus E。And now this E can expand as。E times Z。

And then。This is a one， this is a one。This is a one。 And so the string you've accepted is。1 plus。

Times， so。This is the same string as this。So you've accepted the same string。

 but we use two different delevations or two different parse trees。

 So what's important is the tree structure of these two things is really different right was。呃。You。

 this tree is slaned this way， this trees is that way， I mean。

 you can see that these are two different trees。嗯。And this is something called ambiguity。

And it's not a good thing。So， it's called。So this is called an ambiguous grammar。

So this is a bad thing。 we don't want。One string to have two different ways of dering it。

 This uniqueness will make it make make your life easier for in many applications。

 especially when you designing compilers to。You know，Re your programming language and so on。

 you want there to be only one way to get to a string and you know that's nice。

 and that'll make your life easier。 but this grammar doesn't have the property in fact。

 there's two different ways of getting to the string。Does this make sense。

 just a notion of what is an ambiguous grammar？Just if there's any strength for which there's two different ways to get to it。

 or more precisely， if there's two different parse trees for it， then that's an ambiguous grammar。😊。

But this ambiguity is the property of the grammar， not of the language， so this same language。

 the set of all strings that look like that， can be expressed by a different grammar that's not ambiguous。

Hopefully I haven't written done here。So this was the grammar we use， let's not use that。

Let's use this other grammar， which has the e equals。E plus T。So now I'm inventing more variables。

That not equals gives。T can be t times F。All right。And F can be0 or1。Okay。

So what is the set of rules really doing， So E stands for expression。

 T stands for term and F stands for factor。 So what it's saying is an expression。

Is a sum of expressions and terms。And so at the end of the day。

 when you finish doing the substitutions， an expression will just be a sum of terms。

 A term is a product of factors， and a factor is either 0 or one。😊，So this is telling you。

 this is forcing you。To derive the string in a particular way， which is。That one over there。

 and this one is not going to be fine。Because you first have to use the plus rule。

There's no way to use the product rule and then come back to using the plus rule because you've lost that kind of variable。

 So this grammar will force you to derive that string in exactly one way， which is。

E first gives E plus E。And then。This team is going to break up us。T times F。Or rather sorry。

What do we want， yeah， that's exactly what want， so we want t times F。This F is going to be a one。

This T is going to be a F， which is also a one。And this e is going to be a T， T is going to be a F。

All this going to be one。 Okay， so this is a one。Plus。One times。This it one。So。We got one+1 times1。

 which is same as the string here， but I in fact claim that this grammar is not ambiguous。

 that there's exactly one way of dering the string and it's the way that I drew here。😊，So yeah。

 so what this shows is that。Context free languages for which some grammars are ambiguous。

 like this one。And some grammars are not ambiguous like this one。 So this is a better grammar。

 If you're writing a compilers and you want to actually use this to do something。

 You want to use a grammar that's unambiguous。And。And as we saw， this is a property of the grammar。

 not of the language itself， because the same language can have two different grammars。

 one is ambiguous， one iss not ambiguous。Okay， yeah， any questions about this concept of ambiguity？

Nope， nothing。Okay。And。Yeah， all right。And this is something that happens in natural language as well。

 ambiguity。And somehow of the derivation or the parry is what gives things meaning。And。

Maybe I won't get into too many examples， but maybe I'll give you one example。

 so this was an actual newspaper headline from a couple of days ago。Okay。

 so cops kill man with knife。Okay this was a newspaper headline so what is the ambiguity here so the ambiguity is it's not clear if this with knife。

 what is it modifying， is it modifying did the man have a knife or did the cops kill him with a knife like did the cops kill a man with a knife you know like yeah a man with knife or did the cops kill a man with a knife so if you write down a grammar this for the English language you can see this in Ssters book with this verbs and nouns and so on you can construct two different parse trees for this and then you'll see that the parsry encode the meaning it tells you which like how this was like what does this prepositional phrase attach itself to is it going with the verb is it going with a subject？

😊，And。So that's why linguists still use this context for gram or structure because it's a nice way of expressing meaning for sentences。

 but if you just write down English sentences like this， they're often ambiguous。

 like it's not clear what the sentence means。😊，嗯。Yeah。

 I hope it doesn't mean that they killed him with a knife， that's kind of brutal。

 that you just shoot him down， right？So， okay。O。Right， so we talked about。Context formmars。

 we've talked about it quite a bit。And what we have not talked about so far is， let me。

It is this portion about regular languages。We've just talked about a way of generating these strings using this grammar。

 but we haven't talked about any kind of machine model like any。Like。

For finite seometer we had this model which is the finite seatmata which accepted exactly the regular languages and it's nice to have a machine model because then machines are easier to play around with。

 you can do stuff with them， proofs are more intuitive with these grammars。

 it's not as intuitive to come up with something and in fact there is a machine model。😊。

Which exactly captures。嗯。Cont free languages。 And they're called pushdown automa。Also called。PDA。

 which does not stand for。Public displays of affection， which stands for Pdown automata。So。Right。

It's always nice to come up with the machine modeler， so now you can reason about this object。

So what， what is。What is a push down at timeta？So it's basically， let me just write you in one word。

 so this is going to be the theme for what the question ofdometer is， it's an N with a stack。

What's a stack？So a stack is some kind of thing like this。It's literally a stack。

 this is an empty stack， and you can put stuff into it。You can put symbols into it。

 so maybe you first put a zero into it。Maybe you put another zero， but a one。

the feature of the stack is you can only access it in this way， so if you throw stuff onto the stack。

 you can only pick up the topmost object first， you cannot go in and access this guy over here。

 so it's like a stack of dishes you stack up the dishes and the first dish you remove is the last one you put in it's this one over here。

So this is an additional power that we're going to give to our NFA。

 we're going to allow our NFA to use a stack。And I'll show you exactly what that means。

 But why is the stack useful as stack is and this stack is of infinite。Deps。

 like you can push as many things as you want under， there's no limit on the length of the stack。

And what's nice about this is the fact that now we can recognize languages。That are not regular。

 and one of the examples of a language that was not regular was thised， zero to the n and1 to the n。

And how does a stack help the reason the stack helps is what the DF can do is when it keeps seeing zeros it can keep pushing zeros onto the stack。

 once it starts seeing once it can start popping out things from the stack and making sure that they're all zeros and if total at the end of the day if the stack is empty and we've kept seeing one so far then you accept the string so that'll exactly accept zero to the end one to the end so this adding this power of an infinite stack。

😊，Exactly allows you to capture things like this or well parenthesized brackets。

 So how do you deal with these parentheses。Push these objects under the stack when you see the one that's the opposite of this guy。

 you pull that one out， delete it。And keep doing that if you see something that's incorrect。

 then of course， you reject。So this stack gives you。

Intuitively the stack is giving you exactly the power that you were missing in DFs the DFAs is the one thing you didn't have was the ability to store information like this。

 this is a very limited form of storage like you're not allowed to access random bits that you feel like but this is still good enough and this is exactly what you need for。

To capture context programmemar， so push on a tomaton is exactly an NFA with a stack。

So let me give you an example。This one。Clear things out。Okay。

 so we need some kind of notation to describe what's happening on the stack and how do you。嗯。

How do you push objects onto the stack and how do you get objects from the stack。

 also something's called popping objects on the stack。So let me just describe。

ADFA for the following language。The zero， the n one to the n thing that we were just talking about。

 let me describe a pushdown automaton for this。So you coming。嗯。So the language。

 the alphabet of the stack doesn't have to be the same as your input alphabet。

 you can have a bigger alphabet like some of the stack and input are unrelated things。

 so you can have whatever alphabet you want。 So I'm going to have a slightly larger alphabet for my stack。

 which is going to be。The dollar symbols 0 and1。And。Now this is a slightly technical thing。

 but in our definition of push down on timema time we're not going to give the machine the ability to test whether we've reached the end of the stack and this is important because at the end you want to know if you've reached the end have you exactly got the same number of zeros and one but this is not something this is not a big deal because you can always start by putting a special symbol under the stack so you can always start your stack by pushing on the dollar symbol and then while you're reading it when you reached the dollar symbol you know you've reached the end of the stack so that's just a simple fix so you always start with。

Push the dollar symbol onto the stack and the way we're going to define。Like this is first。

 so what is the input that you accept so you don't accept any input at all right now we just want to push something under the stack So what we say is you accept the input you know empty string。

And then our notation is going to be the following。Epsilon goes to Do。This is。

Abspsilon goes to dollar。 So what this means is。You did not accept anything in the input on the stack。

 you did not pull anything out of the stack， you just left the stack alone。

 but you pushed something onto the stack and you pushed a dollar onto the stack。

 So if your stack was originally empty，After following this。

 you're going to have the dollar symbol at the bottom。That's what this is going to do。

And here what you want to do is。If you see a zero on the inquiry。You don't want to。

You don't want to read anything from the stack， you just want to push a zero onto the stack。

Because now we want to count the number of zeros。And。And this is going to be。An epsilon transition。

I'll describe this in a minute。What this is is just， well well nothing's happening really。

 it's just nu transition to the state over here。And this is a state that does the。

The backwards counting， checking if the total number of0 is equal to the total number1。

 so now if it sees a one in the input。It deletes a zero from the stack。

 so that means it reads zero from the stack。And it replaces it with nothing。

And at the end of the day， if you。If you see the dollar symbol。

Then you know you've reached the end of your stack and whatever you can replace this with anything。

 it doesn't matter。And this is the acceptance thing。So。Maybe this was not very clear。

So let me just give an example。That just say0，0，1。1。So let's follow this input。

 so what's going to happen with the stack is first you start off with just。

Just a dollar symbol of the stack and nothing here。That's when you go from here to here。

Then every time you see  zero， you're going to push a zero onto the stack and you're going to have。

Dollar zero here， at this point you're can see dollar is0 or0。Okay。

 and what's happening here so this is a non deterterministic machine so it can choose to nondeterministically jump here on this epsilon transition goes here and now starts popping zeros off so now there's only $0 left。

 only $10 left and finally it's going to read this and you going to replace it with the empty stack。

On this epsilon transition。And this is a way of pictorially representing this intuitive idea that if you had a stack。

 you can just push the number of push all the zeros you see onto it and when youre start seeing ones you。

You know， start deleting them。Okay， this just kind of make sense。What's happening。

 so it's exactly an NFA which has access to a stack。Okay， any questions about this so far？Y， y。

 that's a great question， so we don't actually need this what you could have done is you could have done the one transition。

 is that what you're proposing， yeah， yeah， that's totally fine。呃。

I left her like this because I wanted to go with a more complicated example。

 but I decided to switch to a simple example doing this， but you're right。

 so this is also valid if you have one here ands it goes to Epsilon。This is also legit。

 so the first time you see a one， you switch over to this state over here and now you're in this counting backwards situation and you come here。

srry。Oh， I see。That's true， you don't get the nail string。

 so well maybe I didn't want the nail string anyway anyway， but yeah， sure， that's right。

 you don't get the nail string， but you know。嗯。Oh， I see。 I see。Okay， well。

 maybe that's why I had the epsilon transition over that。好， yeah。I guess。Sometimes I would do myself。

 okay， yeah， I don't know。I came up with this one。Yeah。So that's right。

 then you won't have accepted an else string， so maybe it's good to have that over there。嗯。

So one thing you can ask and okay， in the last。Two minutes I just wanted so just so you know we did not get to this part so I'm going to finish push on timematon I did not get to this。

 and so Scott will cover this next time and he'll show you the existence of a language that's not even a context programmemar so。

It's a mystery you can think about it if you want， try to think about why a language wouldn't be expressible by context gra grammar。

 but there's an interesting thing about push down automatons。

 which is that I said a push down automaton is an NFA with a stack but。😊。

What if you define a DFA with a stack， so it determineing machine。

But it has this stack it's a deterministic machine， so this machine over here。

 it has a couple of epsilon transitions， but there's somewhere way to define a deterministic machine with a stack that accepts this language and it's clear that there's basically a deterministic algorithm where you just look at all the zeros you keep pushing them on when you see a1 you start popping them off and then at the end of the day you've accepted this string zero to the end1 to the end。

😊，So this language is indeed acceptable by a deterministic push downmaran， let me call it DPDA。😊。

But there's the question of is this equal to just。A full blown PA， which is an NFA with a stack。

 So this is like a baby version of the P versus N question。

 know the P versus N question is the question for tuuring machines do polynom time tuuring machines equal nondeteristic polyno time tuuring machines。

 So we saw this for regular languages。 So we saw this question is NFA equal to DFA。😊。

And this was true。NFs are indeed equal to DF， so for this version of this model of the P versus NP question。

 this very， very baby model of the question， it was true， nondeterminism does not help you at all。😊。

Here it turns out that nondeminism does help you， so in fact， they're not equal。

So PDAs are actually stronger than DPDs， So now you've seen two different models of computation。

fininite state machines and push down automaton one way nondeterminism helps and one way it doesn't so this kind of gives you some idea of why the P versus NP question is so difficult because it's not obviously you couldn't have guessed this a priori that nondeterminism is not going to help you here but it's going to help you here like you might have after saw this you might have guessed that well maybe nondeterminism just doesn't help it's just just a stupid ability you can always replace it with determinism but that's not true there are some languages that you cannot accept with a push down automaton and maybe I won't。

I want to give you an example of that。嗯。But。Or maybe it's actually I will give you an example it's easy。

 it's the palindromes language we just saw， so the palindrome language is an example of something that's a push down tomaton。

 but not a deterministic pushdownma。Okay， that's the end of the lecture。 If you have any questions。

 please feel free to ask me afterwards。Thanks。Is there anything special about IIFfo。

 like if you gave an NFA a cu instead of a stack？Recognize the same languages。No。

 I think you would recognize a different set of languages。 So it is importants out Yeah。

 like if you think of this palindromes， for example。

 you really need to push them out in the same order that the pop in because you want to match them。

 you know from inside out's not。But I'm not sure if you would get something more powerful or less powerful。

て。際い。You're not Scott。something cool。