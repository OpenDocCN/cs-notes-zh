# 伊利诺伊大学【中英⚡算法｜CS473 Fall 2022 Algorithms】 p16 P16 15. String matching via careful failure -BV1RdBTBrEdx_p16-

那你放。对，我是他这在要做。

![](img/46b08f8e3fa61ab45fabbb629dc1bce6_1.png)

3个。我的现在我这边就是清楚。是个。Like student， Its charge for。I work for。对的。然后你好。来。还几个。好，ちょっとて。对看。关这啥。啊好啊，拜拜。かし。

肯定唔系。怎么。喂操好了我过。哎，这个？哎什不得。我我手机死飞啊诶。你有电真呢。Okay，也个。Wch is think。I thought was just。Yeah。Yeah。

While you're ranYou can those。I guess。对。嗯你说这。Thank。北如。Yeah。Good service。Youre local language。

fine try again。DidI got to her hear then they never progress。So what。Yeah对。at kind of across。其实个啊。没了。

都关。什个设。好丑。下。So us lots of this。All right。对。Is this working no， this is not working。Yes。8。Yes。Okay。

 so the in room microphone isn't working the batteries are all dead。

 so I'm just going to have to speak loudly if at any point you have trouble hearing me。

 please raise your hand and let me know。U。Nothing new logistically or administrative reports。

Homework six is out， it's due next Tuesday。There will be one more homework。Before midterm 2。

 which is。10 or no， 11 days from now。I'll say more about midterm two as it gets closer。

 but the high level overview is essentially it'll cover the same material as homeworks four through seven。

Just like。The first midterm was supposed to cover homework zero through three， yeah。I'm sorry。No。

 smoke is not going to show up on any exam。系。All right， so。Unless there are any questions。

 we'll go ahead and get started。So last time。I introduced。Oh， was there a question， I'm sorry。Yeah。

Sorry。It should okay， I'll double check after class。

 but I thought everything was up to date at this point。It's a dead link。

Did you go directly to media space？Okay， probably just forgot to set some permissions so I'll fix that after class。

 thanks。嗯。Okay， so last time I introduced this text searching problem， so you're given two strings。

The longer one we'll call the text and the shorter one well call the pattern and you're interested in figuring out。

😡，Whether the pattern appears anywhere inside the text as a substream。😡，Now。

What we did last time was。We kind of riff on this idea of let's try to think of the pattern and windows on the text as numbers and do some arithmetic stuff。

And eventually you were led to something that's sometimes called a rolling or sliding hash function。

So we maintain a hash value for a window of the appropriate length on the text and we update that hash value in constant time as we slide the window。

😡，嗯。😊，If the hash values collide， then we have to do a brute force comparison。

 but if we engineer the hash function correctly。One。

 we can update the hash value in constant time and two。

 the probability of a false collision is only one over the length of the pattern。😡。

And so the expected amount of work we have to do at any position is only constant unless we have a real match。

So we get order and expected time， what I want to talk about today is how to do this deterministically。

😡，We're done with probability for the moment。嗯。And so。I want to go back to the idea of the。😡。

Sort of brute force algorithm。Where we try every possible starting position for the substring。

And we do comparisons until we discover that there's a mismatch。

And kind of point out that there's a sense in which this algorithm is wasteful。😡。

Not just that it runs in MN time in the worst case。

 but even when it can do better than the worst case running time it still can be wasteful。

 so let's imagine that we're trying to find this pattern abracadas inside this long text at the top。

Now what's going to happen at the beginning is we'll do comparisons and very quickly we'll say H doesn't equal a done。

 O doesn't equal a done， C doesn't equal a done， u doesn't equal a done。

 eventually we'll get up to this point。Where we'll see a map。

Between the first character of the pattern。And a corresponding character of the text。And okay。

 so we'll go， all right， these are equal and these are equal and these are equal and those are equal。

 and then suddenly we get a mismatch。Now what？The brute force algorithm。Would have us do。Is then try。

These positions。Okayy。😊，So we'll slide it forward one step。

And compare the first A in Abercadaricks to that B。😡，Now， I maintain that this is a little silly。

And the reason why I think this step can be skipped。😡。

Is we already know something about these four characters of the text。

 we know that they match the first four characters of the pattern。

 in particular we know that that B in the text matches the B in the pattern and therefore it does not match an A。

😡，We don't need in principle， at least。We don't need to do an explicit comparison of that first A in the pattern against the B。

 because we already know it's a B。😡，We've already rather。

 we already know that it matches the second character in the pattern。😡。

And that's different from the first character in the pattern。Similarly， at this next shift。

 this is also redundant because we know that the third character in that box is an R。

It matches the third character in the pattern， and therefore it does not match the first character in the pattern。

😡，So we shouldn't really need to do comparisons at those two offsets。😡。

We can skip directly to the point where it says， oh， all right。

 so I know the fourth character in the box is an A， where have I seen an A before in the pattern？😡。

And so you slide the pattern over three steps， the A's line up。

 and now we can start doing comparisons getting。😡，Okay。Similarly。

 when we get to the very end and we see this X。We can go， all right。

 this didn't work because the last characters didn't line up。But it doesn't make sense to。Sorry。

It doesn't make sense to line this up here。😡，Because that B up at the top doesn't line up with the A。

 it doesn't even make sense to line it up here， even though the first A lines up with the character in the text。

 the next character C doesn't line up with the B in the pattern。😡。

So just based on information I've already learned。😡，Based on comparisons I've already done。😡。

I really should be able to slide the pattern all the way over to here。😡，😡。

When I'm looking at the why， I already know something about the previous characters in the text。

 I already know that those four characters are A BRA。😡，And so I can say， oh， well。

 it makes sense to line it up here because then those match a prefix of the pattern and I can go on from that point。

😡，Comparing a Y against sea。Any other shift in between。

 I'm going to have a mismatch between a character in the pattern and a character that I've already matched to a different character in the pattern。

😡，8。So。This vague idea。😡，Is。Basically。Once we've matched。Say the symbol TI in the text。

To some pattern。Some symbol in the pattern， Pj。U。We don't。Need。To explicitly compare。TI。

To anything else。We've in some sense， learned。What symbol that is？

And if we could somehow remember that， then instead of doing a comparison， we can just skip over。

Okay。U。Now。The way I just said that is a little bit weird。

 what do I mean if somehow I could remember what characters in the text？😡。

Then I could skip over that character in the text， I do know what characters in the text。

 it's right there that T sub I。😡，Right what I'm。The only thing I'm really trying to say is'd be really nice。

 it'd be really lovely if somehow in that first example。

 I could skip over those two points because in some sense I should already know that there're going to be a mismatch just by noticing that the A doesn't match the corresponding character in the text。

 and I already knew that without doing the comparison explicitly。😡。

Commun has some problem of trying to search for ARA in the remainder industry。嗯。

And then that's where we start Well， but if you think about like I could say， okay。

 I matched the prefix ABRA of the pattern， let's look for places where that prefix matches。

If I think of it that way， I'm still going to try to match ABRA against BRAB。😡。

And I'm still going to do a comparison that A against that B。

 what I want to do is somehow engineer the algorithm so that it just skips directly from there to there。

The moment I notice that the second A，m sorry， moment I notice that that C in the pattern doesn't match the B in the text。

😡，I immediately compare the be in the text against the second be in the pattern。😡，Right。

So I avoid places that parts of the pattern and parts of the text that I've already looked at。😡。

I would somehow avoid doing comparisons and just skip over them。系。U。So I mean， one question is。

 you know， what's the next reasonable position for the pattern？That I don't have this。嗯。

I haven't already looked at that part of the text and matched it against some part of the pattern that's different and the the。

😡，One way to phrase this。Um。Is's at the smallest value of s？Such bat。Um。

The text starting at S and going up to I minus1 where I is the character that we last in the text where we last got a mismatch。

 so we've previously matched character T of I minus1 to something in the pattern。😡，Um。

so this is the rule that I'm。Kind of moving towards。The reason I shifted over by three。UIs that。

This part of the text。Is a prefix of the pattern。That's shorter than the prefix that's inside the box。

So I've already matched some substring of the text to a prefix of the pattern。😡。

And I couldn't extend that prefix。😡，So then I want to say， okay。

 so imagine that I when I start comparing again， I need to know that everything to the left。😡。

Of that of this position in the text。Everything to the left of this line。

Needs to match a prefix of the pattern。And I want to shift as little as possible。

 so I want that prefix to be as long as possible。😡，讲。Okay。So。

I'm right now trying to compare this character B， this is what I'm calling T sub I。😡。

I'm trying to match that against the next character in the pattern。Now。

 the way this works is I would only do this if I already know。😡。

That the previous sub numberumber of characters in the text match the previous sub numberumb of characters in the pattern。

😡，In other words。Some prefix of the pattern。A BRA has already matched the corresponding characters in the text。

Okay。And so what I'm trying to do is find longer and longer prefixes of the pattern that match chunks of the text。

Now at this point where I see B and do a comparison between B and C。

 I can't extend the prefix that I'm trying to extend， I can't extend a BRA。😡。

To be because the next character isn't to be to see。

But I still want to be able to know when I shift the pattern forward。😡。

That everything to the left of that line。Is a prefix of the pattern that matches the corresponding characters in the text。

😡，All so this example over here， I'll draw this with a blue line。😡，Um， there。

When I start looking at the character Y in the text。

 I've already matched the prefix Abracadabra of the pattern to the corresponding characters in the text。

😡，So the next shift where that statement is true is the one I've written on the bottom line。

 where only the first four characters that pattern have matched the previous four characters in the text。

😡，And so at this point， I would compare y against C， and I would say， oh， that's also a mismatch。😡。

U so。Just to see if your intuition matches what I'm trying to say here。嗯。Where would the next？Shift。

对。For this。Pattern。嗯。Right。So ABRA in the pattern matches ABRA in the text。

 but the Y doesn't match the C。😡，Okay， where is the next reasonable place that I can put the pattern and start compare？

喂。I could just line up the eyes。With this。And now I notice that the Y and the B don't match。😡。

So where is the next reasonable place？😡，U to put the next reasonable shift to put the pattern。Yeah。

Well， no， I mean， I need to keep searching。😡，Yeah， so I line it up here。😡，And the idea is。Now。

 the largest。Shorter prefix of the pattern that matches the text so far is the empty prefix。😡。

I haven't matched anything， so at that point I know that I should start over。😡，Yeah。喂就是 why。

Then you can see to the right of the y what sorry okay。

 then the prefix is empty and then we have a why yeah。Right， so the。😡，Even in this last。嗯。

This last row。There's a prefix of the pattern。That matches。

A suffix of the string up to that blue line。It's the empty prefix。

The empty prefix of this string matches is also a suffix of this string。艾特。😔，So sometimes。😡。

This word shorter。U。This prefix that matches sorry。

 this substream that matches the prefix of the pattern， that might be the empty substream。😡。

Matching an empty prefix。And in fact， that is what happened way back over at the beginning when we're trying to match with Hocus focuscus。

All right。So。This is the。Main design idea behind the Kluuth Morrisris Pratt string matching algorithm。

😡，Is somehow I want to encode。A function。That tells me。

What this next reasonable shift is now the way that I've phrased it is I've looked for a value。😡。

In the pattern that lines up with the first character， sorry。

 an index into the text that lines up with the first symbol of the pattern。

Another way that I can phrase this is。😡，When I'm doing my comparison。And I see here。😡，Failure。

What is the next character in the pattern that I should compare this character in the text to？😡。

So if I get a mismatch comparing to the fifth fifth letter in the pattern。

 what is the next letter in the pattern that I should compare that same text character to？😡。

That is what is encoded in this。What's what I'll call a failure function。Okay， so。嗯。😊，The idea。

 for example， is。If the text matches A， B or A， and the next character is something else。Okay。

Then the next character in the pattern， I'm going to compare this Y2 is character2 to B。😡。

That's what that's essentially doing is sliding the pattern over so that this A in the text lines up with the first A in the pattern。

没。So。I have not told you how this function is actually computed， we'll get to that eventually。😡。

But for now， I just want to get across the idea of how this function might be useful。Okay。

One way that you can think what this about how this so called failure function。😡，Behaves。

Is you can think about building a kind of non standard finite state machine。😡。

So normally a finite state machine of the kind you would see in 374。

You have a finite number of states for each state and each symbol in your alphabet。

 you have a transition going to a new state。😡，You read the symbols in some string one at a time。

 and for each symbol you read， you make exactly one transition。😡。

Okay that's a standard finite state machine I'm going to do something a little bit non standard here in part because I don't want to assume that my alphabet is small。

😡，Standard finance state machines work great if what you're searching for is bits in a binary string or maybe even like base pairs in a string of DNA。

 but I don't want to build a pattern by length of alphabet transition table。

That would be too big and it would take too long， so instead what I have is every state is assigned one of the symbols in the pattern and I have exactly two kinds of transitions。

 success and failure。😡，Success means。I'm in that state and I read that symbol。

 I'm in state A and I read an A， I'm in state B， and I read a B， I'm in state R and I read an R。😡。

Those are the blue arrows in the picture up here。😡，And when that happens。

 I will consume that character in the text。I have matched the character in the text to something in the pattern。

😡，The red arrows are the failure arrows。 So what this means and this is the non standard bit is。Ah。

I'm in state A， but I read a Q。Now， really it's I'm in state A。

 but I read some symbol that is not an A。Follow the red arrow back to an earlier state。😡。

But don't consume the text character， you're not done yet。😡，Okay， so if， you know， for example。

Let's see what's a good example if I'm here？And I read an A。

What will happen is I'll fail back to this state。Now I'm still reading an A。

 so I will fail back to this state， now I'm reading an A， I've succeeded， I'm done with that text A。

 and I'll move on to the next character in the text and follow the success plan。😡，系。

Here it is in code。This is KmpP。Yes。Oh。So the question was， why did this？

State machine have an arrow from a to A and then another arrow from A to A。

And the answer is because I used that definition in green to define the failure function。

 and that's what it gave me。😡，Now it's possible to optimize the failure function further to say。😡。

If I compare myself against the pattern character A。😡，And it's wrong。

The next thing I compared to shouldn't be an A。😡，So I should circuit this chain of failures。

Directly to the symbol I call dollar sign that that's the I hit the beginning of the。

The pattern and I need to start over。Right。So there's some optimization that you can do after the fact that will in practice improve the performance of the algorithm。

😡，I'm not going to do that for now， I do talk about it in the notes。

 but I'm not going to talk about it in class unless we have time at the very end。嗯。Yeah。I mean。

 another way to answer this is this failure here， in some sense， isn it really about the A。

 it's really about acadaver。😡，And the fact that ABR matches ABR at the beginning is why the failure function points here。

All right， so here is。The algorithm。So I somehow magically compute this fail function。😡。

I somehow magically compute this non standard finite state machine for matching the text。😡。

I have two indices， I and J， I is an index into the text， it is always moving forward。😡。

So it's just a simple for loop。And I have an index J into the pattern。😡，Now。

 when you decide to sit down and execute this code on an actual example on paper or on a whiteboard。

 and I do mean when。😡，Not if。Please actually do this。

What I want you to do is write the letter I on your right index finger and put it on the text and write the character J on your left index finger and put it on the pattern。

😡，So at the beginning of time， I and J are both equal to one。😡，系。Then。This while loop。

Is basically saying if the characters match move on， if the characters don't match。😡，Fail。

 which means。Jy。Your left index finger pointing at the pattern will move backwards to an earlier position in the pattern。

And then as long as there are mismatches， it'll keep moving back until maybe the one way that the while loop can stop is you find a pair of characters that match。

😡，One way the wild can stop is if you fall off the beginning of the pattern。😡，Either way。

 at that point， you move both characters forward。😡，Now。

 if you just scanned past your left finger is past the end of the pattern。

 you have found the pattern in the text and you say，y， I'm done。

 we report the index where the pattern starts， the game is over， otherwise you keep going。😡。

OkaySo here is the move the left finger forward and the for loop automatically moves the right finger forward。

If your right finger falls off the right end of the text。

 you didn't find the pattern and so you return a failure code， you return no， it's not there。😡，Okay。

 so。If I actually do this。Right， and there's my text。And there's my pattern。

So I will start with I here。And J there。I'm going to move these side by side。系。嗯。These both match。

So I will move them both forward。These both match， so I' will move them both forward。

 these both match。I'll move them both forward again at this point， these don't match。

 so I will follow the failure function。😡，What is fail of five， it's two， okay。

 so I'll move this back to two。These both match， so I'll move this forward。And so on。

Please actually do this。Right。嗯。This is one of these， I mean。

 this is actually I think generally true that it's really beneficial to execute the algorithm by hand to understand what's going on。

 it's also useful to actually implement this and then watch it go， but I know for my own sake。

 I didn't understand this algorithm until I executed it with my own fingers。😡，哎。嗯。Okay。So。

Does everybody understand modulo how we compute this fail function。

 right that's still magic at this point。😡，Does everybody at least have kind of an intuitive idea？

Of how the algorithm works。Okay。So。U without talking about the fair function in more detail。

 can't really convince you that it's correct， but let's assume that is。😡。

What's the running time of the algorithm？😡，So I claim that the running time is actually dominated。😡。

Here， ignore the cost of computing failure function， okay。😡。

The running time inside the main part of the algorithm is dominated by the number of comparisons between characters。

😡，Everything else is constant time bookkeeping stuff。Okay。So there are two types of comparisons。😡。

And so let's count each of these separately。There's comparisons where TI is equal to Pj。

And there are comparisons where TI is not equal to PJ。All right。So。

Let's think about what happens when we get a match， a successful equality test。😡，So in this case。

 we increase I。And we increase J。So how many times can this happen？😡，At most end。😡，Actually， most。

N minus1， I starts out as one and it gets to end and then the game is over。But you know， let's just。

Just crudely， let's just say it's the most end times because if I did this more than end times。

 I would have fallen off the end of the text and we know that the algorithm ends before that happens。

😡，Yeah。Okay。😊，Now look at the other thing， what happens。😡，I stays the same。And J decreases。

How many times can that happen？So sometimes J goes up and sometimes J goes down。So。

Jake can't go down more times than it goes up。Because whenever it goes up it goes by the minimum amount possible it's an integer。

 it goes up only by one， so the history of J is like1，2， three，4，2，3，4，5，3，4，5，6，0，1，2，3，2，3，4，5，4，5。

5，2，3，4，5，6，7。😡，Every time it goes up， it goes up by one， every time it goes down， I don't know。

 maybe it goes down by at least one。If it went down more times then it went up。

That means at some point， J would be negative。And that can't happen。So again。😡。

This happens at most end times。If you remember anything at all from CS225 about the magic word amortized。

😡，What I'm doing is I'm amortizing the mismatches against earlier matches。😡。

Every time I get a mismatch i'm charging that mismatch to an earlier match now my matches get get charged two units of work and my mismatches have。

😡，Other people paid for them。So the total number of comparisons I do in this algorithm is at most2 n。

😡，Okay so。And in fact， yeah， it moves two in comparisons。Now。

 last time I think I may have mention this。Chances are pretty good。

That the search function inside your web browser just does brutefor。😡。

Chances are pretty good that the search function inside EMX or VIM。

 depending on your religion just uses brute force。😡，And the reason is。That for English text。😡。

Brote force does slightly more than n comparisons。The number of comparess usually is the first characters don't match。

 I move on， the first characters don't match I move on。😡，So for normal text or code。

 chances are pretty good that you're going to get a mismatch very， very early on。

 and so the number of comparisons you do is only n。😡，That factor2。

If you're writing a word processor in assembly on a 16 bit Apple。😡。

Strangeo computer that doesn't have a compiler。That runs at something or something kilohertz。

That factor of two actually matters。And it， you， you really。

 you don't want to go through this effort to do this thing instead of just reforcing it。

But if you really care about worst case efficiency。

 if you're like searching through potato genomes or something， then this actually does matter。😡。

Questions。Yeah， so the case takes close to N， wouldn't this also be very close to n in that case they're not going back too much Yeah I think if you do the analysis more carefully if most of the time you get of this match on the first character。

 this this while loop will only do one comparison inside each iteration of the for loop。

 but still you're maintaining you know multiple pointers in doing comparisons and the overhead is noticeable。

嗯。啊嗯。The other way to avoid that extra factor of two is to build a real honest to goodness DFA。😡。

So a real honest to goodness DFA， you read the character in the text。

 you look at your state transition table and you go to the next thing。😡，But as I said。

 the problem with that is then you need to somehow encode all possible transitions out of this state。

😡，🤧Yeah。And you don't want to explicitly do that for every character because then you have a。

 you're using UTF8 and not being intelligent about it， you've got a pattern length by 256。

State transition table that you have to build。😡，And now suddenly that too is 256。嗯。😊。

You can do some things that are a little smarter like。😡，Okay。

 the most likely two characters to come out of here of the states and then fail for something else。

 all sorts of weird stuff that you can do beyond that， it doesn't really help， right？😡，So really。

 I want to stick with this non standard DFA if I don't want to make assumptions about the alphabet science。

All right， so everybody reasonably okay with how the algorithm works。😡。

Modullo this fail function and why it runs in linear time。But the linear time analysis， by the way。

 doesn't depend on the value in the fail function， I could stick any numbers in there at all as long as fail of J is less than J。

 the analysis would still work。So let's think a little bit about how we want the fail function to work。

So this statement that I have here in this box。😡，It's just。

Formalizing what I said earlier about the next reasonable shift for the pattern。😡，Okay。

 so I want to choose the value fail of J。😡，So that the prefix of the pattern ending just before fail of J。

Is the longest proper prefix of。😡，The pattern ending just before Pj。

Theres also a suffix of the text ending just before TI。Now。In a lot of presentations of KMP。

 for example， in CLRS or in Wikipedia， they define this function without all the minus one sprinkled in here。

😡，The reason that I put the minus ones here is so that I don't have to put them here。😡。

I want to keep the code as simple as possible， so I'm doing that at a little bit of an expense of making the definitions slightly more complicated。

Okay， so if you notice an off by one discrepancy。Just make sure if you fix it。

 you fix it both in the definition of this function and in your KMP code。😡，系。So。

Now let's think about in the running of the algorithm。I have already。

Scan what I'm looking for is I'm trying to compare TI to some reasonable next character in the pattern。

😡，I've already matched T1 through T minus1 through earlier characters in the pattern。

When I shift the pattern over， I want to know that TI through T minus1 still match corresponding characters in the pattern。

 at least if the pattern overlaps with it。😡，So。嗯。What that means is that I can modify this definition。

Instead of talking about the text。I can talk about the pattern。

So any suffix of the text that would work in here is also a suffix of the portion of the pattern that I've already matched。

😡，So this means。P1 through fail J minus1 is the longest proper prefix of P through J minus1 that is also a suffix of P1 through J minus1。

😡，So this is。What'sAnother way of saying this is a border of a string。Is a proper prefix。

That is also a suffix。And so what this says is。P1 through fail J minus1 is the longest border of P1 through J minus1。

😡，The the string aca debra。The largest border is ABRA。

Because it appears both at the front and at the back。So here's the same。Failure pattern again。😡。

That I showed you before。Okay， so just to give another specific example， let's look here。

So this is piece of J。嗯。So what I'm going to look at is。This string。Yellow。

 that's P1 through J minus1。And I'm looking for the largest border of this string。

 the longest prefix that is also a suffix the word proper in there just means yeah。

 the whole string is technically a prefix of the string let's rule that out so I want some prefix of this string that I've highlighted in yellow that's not the whole string highlighted in yellow。

 but it's also a suffix of this string highlighted in yellow。😡，And well。

 in the end if I look carefully， I can see there's a B。So that has length too。

And then because of the minus one in the definition， that's the reason why I write a three here。Okay。

 so I find the longest border。Of all the stuff before， PJ。

Take the length of that longest border and add one and that's fail of J。All right。So。

If I wanted to follow this definition， I could compute this function more or less by brute force N cube time。

😡，And say， okay。For every prefix， see if it's a suffix。So。

There are n prefixes for each prefix I'm spending order n time to see if it's a suffix and I need to do that once for every value of Js so that that comes out and cubed if I'm a little bit smarter。

嗯。I can use dynamic programming to reduce this to n squared。Essentially， I could find， you know。😡。

Let's see for any prefix link。And in any starting index later。

 what's the longest prefix that is also the substr starting there？😡，Okay， so。嗯。

Something along those lines。嗯。Is the prefix of length I？😡，Also a substring that starts at index J。

 that would be the way I phrased the dynamic program。Um。

But turns out that I can build this in linear time。😡，Yeah。of R1Oh， okay， why is this fail of R1？Okay。

 what is the longest border of AB？It's the empty string。It has length zero。Z plus1 is one。

In other words， if I get a mismatch when I'm reading against this R。

 the next character I should try is the beginning of the pattern。😡。

It should just start at the beginning of the pattern。

If I get a mismatch at the beginning of the pattern。

 this is one case where the definition I've written in the box doesn't hold。

 so it's essentially the base case， if the beginning of the pattern doesn't match the current value in the text。

 undone with this position in the text， I should just start over completely。

 that's what that zero means。😡，You still look a little confused。Okay， yeah。So。嗯。This， by the way， I。

We ignore the first line there， this is eight lines of code。Right。啊啊。

This is the second most confusing eight lines of code。😡，That I know of。

NowYou may be wondering what's the most confusing eight lines of code that I know of？Is this。

Eight lines of code。嗯。This is how you compute the failure function in linear time。

 So now one thing that you can take from this and probably one thing that at some level you should take away from this first is。

😡，The failure function could be computed in linear time。😡，Back away。

Yeah I don't put my hand in the tiger trap。Just okay， linear time， I believe you。嗯。😊。

And you I can figure out that this runs in linear time essentially using the same analysis that I did for Kenneuth Morris Pratt。

Sometimes J goes up， it always goes up by one and only when I find a matching pair of characters。

 sometimes J goes down， but it can't go down more than it went up。Okay， that's linear time。

But why does it compute the right function？😡，The other thing about this。That makes this weird。

This is really quite bizarre is you'll notice。That。It's the same algorithm。Yeah。

Literally what I'm doing to compute the failure function。

I I'm using older values of the failure function to run KmpP on the pattern itself。😡。

To learn the next value of failure function。😡，Okay。Um， iss this， this is， you know。嗯。

His bizarre sort of self referential stuff。😡，Now what's going on here is something about the structure of prefixes and suffixes in strings。

 so let me throw up a slightly different example that'll show this off a little bit better。😡。

Anybody recognize this string？What is that string？It's the abucaa sequence。Yeah。

 but you've seen it before。In this class。These are the instructions for the five disk tar of anoid problem。

😡，A is the smallest disk， B is the second smallest disk and so on。Oh okay。

 so here I move disk five right， so borders of what borders of this string look like， well。

 the longest border of this string is Hanoi on four disks。😡，I do it at the beginning。

 and then I do it again at the end。But that's not the only border， so I could also take this border。

But so there's an interesting kind of nesting property here。So。A border。Of P is either。

The longest border。Or。A border。Of。A border。Of P。So any shorter string。

That is a prefix of this whole mess。And a suffix of this whole mess。Is a prefix of this first border。

 this longest border and a suffix of this longest border， but the borders of the same string。

 so it must be a prefix of the border and a suffix of the border。😡，Right， maybe you know。

 another even another example will make this。Let's see if I can do this correctly。A B， A， A B。AB a B。

This is what's called the Fibonacci string。The first Fibonacci string is a。

 the second Fibonacci string is B， the nth Fibonacci string is the n minus1 Fibonacci string followed by the n minus2 Fibonacci string。

And yes， n minus is tooth， not n minus second。U so。I see。You know， I'm I'm。

This is too big for me to make sense of， so I'm going to stop。At。Here。So this is， I think。

 like the sixth Fibonacci string or something。So here is a prefix that's also a suffix and then here is another prefix that's also a suffix。

 but it's a prefix that's also a suffix a prefix that's also a suffix。嗯。

So that the border things are kind of nested， another trivial example。😡，Is。

The adversarial national anthem。So。Here is a prefix that is also a suffix。Any other。

Prefix that is also a suffix is actually also a suffix of that first border。So essentially。

 what we're saying is the entire failure function is dependented only on the pattern once you put on the pattern。

 you can do it for any text。That's exactly right。RightSo I compute the failure function for the pattern once。

 and then I can use the same failure function to search for that pattern in any text that I want in linear time。

😡，In the length of that text。There's another question over here。Maybe， yeah。Yes。

 it is valid for the prefixes and suffixes to overlap so in particular one homework six problem two。

It's asking about a prefix that shows up somewhere else， but they don't overlap。

You can't just throw this at it and go I'm done。对。You find a bit more work。

So this is without going into too much technical detail。

 this weird nesting pattern of prefixes and suffixes is the reason why computing the failure function display way works。

😡，Yeah。关的。where like the pattern is both the pattern and the text。

 but it's not returning anything so that it like exhaust all the possibility yes。

 that's exactly what's going on。The compute failure function is using the parts of the failure function it's already computed to run KMP with the pattern against the pattern。

😡，So it's。It's literally building the plane in the air。😡。

Let's take off and use the parts of the plane that are in the air to help design the parts of the plane that are still on the ground。

😡，It。Okay。USo。One way that another way that you can think about。

 if you're at least willing to believe this claim about borders is this is a dynamic programming algorithm。

😡， so I can describe。The failure function。Recursively。So。In order so fail of I。

 I'm looking for the longest border of the substring P1 through I in order for something to be a border。

😡，All but the last character has to be a border of all but the last character。

And those last characters have to match。😡，But recursively。

 the failure function records the largest border。 So what this is doing is saying， well。

 I want to find places where the。U。诶。Let's see， let me。So do this as an example here。All right。

I want to compute the failure function for this character。Okay。So what this number is encoding。

The exponent C means how many times you evaluate， fail。

 So fail or fail of fail or fail of fail of fail。 Okay， So， but if I just set sq to one。

 I'm evaluating failure function once， this is the length of the longest。嗯。Oh。Border？

And then I add one that that's the value that I would write there provided these last characters actually line up。

😡，But they don't line up。😡，So then I compute the failure function of。😡，Now。

 I would have failed to hear to this A， but that didn't work。 So I now want the largest border of。

AAA， because that's going to be the second largest border of this whole thing。Right and so well。

 that's this。And so now I'll compare against this a and that still won't work。

 So now I'll look for the largest border of。ABAB that has length。😡，Zero。

 so I will then try to match against this character。😡，And that didn't work。And so this max。

Eventually this falls out， this max is over the empty set and I just define the max of the empty set to be。

Zero because this is a max of a set of positive integers。P。So。

What the algorithm is doing is observing。😡，As I increase， these values are going down。😡。

So if I want to max， I should try them in increasing order。

 failed and fail to failed and fail to fail to fail， as soon as I find something that works。

 I can stop。😡，Because any value that I find later on is going to be even smaller so it's not going to be the max。

U。i。Personally， don't find any of these explanations enlightenment。Okay， for me。

 these are things that I know about Canuth Morrisris Pratt。

But the only way that I've ever been able to convince myself that it's correct。Is to do this。

Literally say， okay。I J， same straight。And execute the algorithm so what you see in。😡。

What you see here in red with the little eye on top of it。

 that's the position of my right index finger。😡，It has an eye written on it。

What you see in blue with the J， that's the position of my left index finger。With the J on it。

And this is how I move my fingers。My left finger is on a dollar sign。

 so I write down zero and I move forward。I write down one A and B don't match Okay。

 I'm back to the beginning of the pattern I write down one RNA don't match go back。

 I write down one A and A match， I write down two。😡，B and C don't match so I fail， CA don't match。

 so I fail and back at the beginning。I write down one A's match。

 I write down to B and the D don't match， so I'm literally just。

Executing the algorithm with my hands。And so what you'll notice。

When you do this is every time you fail， you're considering a shorter border。

Of the part of the pattern that you've processed so far。And if you fail all the way to the beginning。

 you actually consider every border of the pattern that you've seen so far。

 so this thing that I've written here in black。😡，This is a complete characterization of the borders。

It's either the longest border or it's the longest border of the longest border。

 or it's the longest border of the longest border of the longest border。

Or at some point you'll fall off the end because something is empty。Okay。

 so what the algorithm is doing is trying each of those possibilities one at a time in decreasing order of length until it finds something that works。

Okay。So。Everybody stare。At the code。U。A little bit maybe about the history of this algorithm。嗯。

So it's called toothmorese pret。Morris and Pratt discovered this algorithm in 1970。

Nuth also discovered this algorithm in 1970， but by his own mission a few weeks later than Morrison Pratt。

It is standard in theoretical computer science， like in math for authors to be ordered alphabetically。

 nobody fought over this， so that's the reason K' name is on there first。

 even though he was slightly later。They eventually published their algorithm in 1977。😡，At this point。

 Kaneuth had already written Vole1。Kratt was well on his way to winning his Tring award。

 everybody had Tring awards in the 1970s。m so they didn't feel the need to rush。

There was an earlier algorithm by a Russian cybernetist， Mattiesvich。

That described how to build a standard DFA to do pattern matching for binary strings in linear time in like 1968。

 1969。😡，That if you read it with the right glasses on kind of has all of the ideas in it。

So some people refer to this as Mattiassovicch， toothmore's Prat。But he really。

 his algorithm really is specific to binary strings。

 and unfortunately it's written in two dimensional Tring machine。😡，嗯。So okay， fine。Around 1972， 1973。

 Canuth and Pratt and Morris had been giving talks about this。

 there was a technical report that had been kind of flying around over the usual technical report networks。

 which means an envelope shows up in your mailbox that has a paper in it from Canuth， you read it。😡。

There's a generalization of this by Ajo and Corick that you can pre process a set of strings。😡。

Into a similar kind of DFA。😡，So that you can search a text and it will tell you the first time any of those strings appears in the text。

Around 1973， there's an algorithm by Moniker MANACHER that finds the longest palindrome substring。😡。

In a string， in linear time， not sub sequence， that was your homework。Substring。And essentially。

 that algorithm is running。😡，KMP on the string against its reversal。Sort of。

But it's built on similar ideas about the nesting properties of borders of strings and therefore the nesting properties of palindromes。

If a palindrome has a non trivial border that overlaps itself。

That means it's actually a bunch of shorter pelindromes just copied several times in a row。

 that's how Monikica's algorithm speeds things up。And so the literature is kind of weird because there are these generalizations of KMP that were published several years before KMP。

😡，Because Monica doesn't have a Tring award。So he had to rush his paper out。U。

Aho didn't have his yet。You guys later。So there are lots and lots of generalizations of this algorithm that do more general kinds of pattern matching。

Oh。So。One thing I do want to mention about this because it might be useful in some task that you might want to do before next Tuesday at 9 pm。

Is u。嗯。To think a little bit about how the failure function works。😡，So it is true。嗯。

That the main function makes a linear number of comparisons。嗯。Once the failure function is computed。

But。It's not constant。At。Each position in the text。嗯。Okay， so if I look at this algorithm here。😡。

It's true that the total number of iterations of that while loop over the entire algorithm。😡。

Is it most2 n， but for a specific value of I。There is no upper bound on the number of iterations except every time I iterate the while loop J goes down。

😡，And J is always an integer between 1 and M。So for a specific position in the character。

 I might actually spend order M comparisons。😡，Okay， so it's actually order M。At each。Value of I。Now。

Someone pointed out earlier that if you look at this failure function。😡。

The fail of A points to another A and that points to another A， and that's a little bit redundant。😡。

So one thing that you can do is with a small modification to the compute failure right here you do a comparison against fail J versus P of J versus P of failed J and chase the pointers twice if they're equal。

 it's explained in the text， you get， let's see。😡，嗯。This would become。Zero， this would become。One。

 this would become one， this would become zero。I think that's right。

I think the rest the rest of the same。So if the failure function of a symbol in the pattern points back to the same symbol in the pattern。

 you just chase the pointer again。😡，Okay this is not going to influence the correctness of the algorithm。

 you're just skipping over things that are redundant for different reasons。

 but the algorithm will still work。😡，Um， so if you。Optimize。The failure function。Then。

It's possible to prove。That for each value of I， you can only fail a logarithmic number of funds。

So instead of there being a linear number of failures possible at one spot。

You'll basically be doing it's like doubling。You can do it most logM failures at each spot。😡。

The worst case site I remember correctly is Subbonacci strings that'll give you logM photos where A will fail to be。

 which will fail to a， which will fail to B， which will fail to A。

 and then you can't optimize that anymore。So it's important to remember。

When you're doing the analysis， you have to really think of the analysis over the entire text。

 not just individually each position in the text， if you want that linear time。😡。

Why the J thing is not n squared because the little left index will keeps coming back。

 but it will never have like a summation from one to Okay， so at each position in the text。

J can go down M times， okay？嗯。So。After that， it can go up。

 but it can only go up once in each value of value。

So it takes several values of I to build up a large J， and then it can tumble down all at once。

So it could be so if the pattern is all A's and the text is a bunch of A's， a B， a bunch of A's， a B。

 a bunch of A's， a B， what happens is J will climb the stairs and down and climb up then down and climb up and then down。

That's in fact doing exactly two n comparisons， but the walking up。

 it's doing one upward climb at every value of I。And when it fails。

 it's doing M fails in a row to get back down to zero。This is how amortized analysis works。

 is there can be expensive operations， but they have to be spread out。

That's exactly what's happening here， you can fail several times in a row。

 but only if earlier you've gone up the stairs one at a time fairly high。😡，Yeah。

The final overall runtime is still order M to compute the optimized failure function plus order N to do searches。

😡，Yeah。嗯。If I look at this。😡，Code for computing it now。There。

I may just be pushing the question off to why does that work？😡。

But if I accept for the moment that this works。😡，It's relatively easy to see why it runs in linear time。

In everyiteration of the for loop。😡，Jay goes up。You can't go up， well， I sorry， I goes up。

And Jay goes up and I goes up at most M times。So every time I find a character that matches。

 I andJ go up， so that can only happen M times。When I find characters that don't match。

 Jay goes down。But the total number of times it goes down can't be more than the number of times it goes up because it goes up slowly。

So I go up at most stem times and I go down at most stem times。Linear time。

Now the harder question is。😡，Why does that work？Yeah。Right。

 the natural dynamic programming algorithm that mere mortals like me would come up with。😡。

Runs in quadratic。Yeah， or rather that's the good algorithm this is。😡，Yes。

 I am freely willing to admit that Donald Kath and von Pratt are smarter than I am。不是。嗯。

A lot of things you can kind of figure out where they came from。

And I can kind of see with the person， the right person with the right kind of brain， yeah。

 maybe somehow you could have eventually gotten here， I am not that person。U， so。U。

 but I think once now that it's sort of down on paper。😡。

It's interesting to like understand what's going on， at least at the level of being able to use it。

All right， we are out of time， I'm happy to answer questions up front。

 hopefully I'll see some of you in office hours tomorrow， if not have a good weekend。

I'll see you on Tuesday。嗯。家呢个情况。

![](img/46b08f8e3fa61ab45fabbb629dc1bce6_3.png)