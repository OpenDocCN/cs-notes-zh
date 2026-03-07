# 卡耐基梅隆【中英⚡离散数学｜21-228 2023, Discrete Mathematics】 p06 P6 -BV1sFibBkEj7_p6-

Hey guys， hey guys， how are you， Sorry about that。 I pressed the wrong button as I was trying to get in。

Next thing you know， I'm going to turn into a cat or something。Or turn upside down。

 But good to see everyone again， okay。Let's do this。Great。

 so let's continue from where we were last time。 We were talking about this Erish Secharish theorem。

 And what we had just gotten to is we had gotten to some fact that's apparently true。

 And that fact that's apparently true is about whether or not if you take a sequence of a lot of distinct numbers。

 whether or not there's always increasing or a decreasing subequence within it。

 which is a monoone it's a monottonone subequence。 That's what we called it。😊，One second。

 Let's put these here。

![](img/148dd50384abdf2fa84fd08aeb7daa83_1.png)

Cs on。Done， here we go， okay。So specifically， what did we have。 Oh。

 I see there's a chat just a second。 I want to make sure I can see this。Great。

 so but we what we were talking about is that there's this theorem called the E Seish theorem。😊。

And what this says is if you just have any n numbers， distinct numbers。For any N， distinct numbers。

There is， always。AMootone subence， either increasing or decreasing。Of。

I'll write at least square root of N numbers。Okay， so now how might we try to do this， Oh。

 I see somebody said， I think we're okay。Hopefully， we're okay。Right。

 so how how are we going to do this proof， Well， actually。

 there is an interesting way to do this proof， which turns out to be even related to an algorithm for how you might find the longest increasing or decreasing sub sequenceequence。

😊，So you see， I'm going to， I'm going to write down some numbers。

 just like the numbers we're going play with。 Here's an example。If。🤢，For example。

What you have is like this bunch of numbers。3，1，4，1。 Oh， no， they have to be different。5，9，2，6。

 If I've followed these numbers， I can try to do something where if you remember when we were trying to find out the number of paths through a grid where you either went down and to the left or down and to the right。

 we kind of built up our answer using what we had found before。 So let's try to do that again。

 In fact， we're going to try to build up。 By underneath these numbers。

 I'm going to write two more numbers。😊，So， I have this。And under those two。

 I'm going to write one number， which is the length of the longest increasing sub sequenceequence that ends at that number there。

So I'll write a one。 and let me explain what these mean， the yellow。That's equal to the length。

Of the longest。Increasing。Subsequence。Ending。There。So。For example。

 the longest increasing sub sequenceequence that just ends at that three is just one is just like just the three。

 That's it。And I'll also write a red。 It's going to be the length of the longest decreasing sub sequenceequence。

 Well， I guess I'll call it pink。The pink is the same thing， but for decreasing。Okay。

 why am I doing this， Well， let's just start doing it for a while。

 So what's the length of the longest increasing sub sequenceequence that ends at the one。

Not much you can do。 Just what， right， Just the length of the longest increasing sub sequenceence that ends at the one。

 That's one。 Let's just do the increasing thing first。 Okay。

 so what's the length of the longest increasing subequence that ends at the four。

I can get there by going from one to the 4， and I can get there by going from the three to the 4。

 So that's 2， okay。How about for the five。 Well， the longest increasing sub sequenceequence that ends at the 5。

 I guess it's like 1，4，5。 That's， that's 3。 I see 1，4，5 makes you a 3。

And then the longest increasing sub sequenceequence that ends at the9 is well，1，4，5，9。

 So there's four of them， four in that length。The length of the longest increasing subequence that ends at the two。

 Here's where it becomes interesting。 How long is the longest increasing subequence that ends at the two。

It's only two。 You have to end at the two。 The important thing is it ends at that number。Right。

 because the yellow thing says it has to be ending there。 That's why it's only two。

 It's not another4。And then how about the6。You know what。

 it's a little bit painful to kind of manually go through and see how long of a sequence ends at the6。

 So let's see we can do this in a more clever way。 Is there a way I could use things that I've calculated before。

Well， the way to think of that is， how could you end at the 6。

Which numbers could you have ended at and then go to the 6。Does that question make sense， I'm like。

 I want the longest sub sequenceequ ending at the6， which is increasing。

Where could I have been right before the6。Well， the place is， raise hand， Brad。今回。Okay。So you see。

 I just highlighted all of the numbers that are。Less than 6。

 Those are all legitimate points that I could have gotten to right before going to the 6。

 And this should feel a lot like these paths through the grid that we were talking about， right。

 We did something about paths through a grid where we said， well。

 how could you have gotten to that that that point， That intersection point。

 You could have come from here or you could come from there， Okay， how。

 how many ways could you have gotten to each of those， That was the flavour。😊，And over there。

 we added together because we were like， if I have this many ways to get to this square this。

 this this intersection and this many ways to get to that intersection， Well。

 the number of ways to get to this one is the sum of those two。But here。

 we're not asking for the number of ways。 Here， we're asking for the longest， increasing subequence。

 So now what we can say is we can look at those numbers， which are right underneath。

Does yellow and yellow work。 Oh， it does。 Okay， sort of。

These are all of the lengths that I could have gotten to right before 6。

 And so what I want is I want to take the longest of those and add one to find out what's the longest sub sequenceequ that ends at the6。

And the longest of those is a three。So I'm going to put here a 4。

 But just note that the four was the  three plus  one。 Just remembering that's where it came from。

 Thatll be useful。Does my logic make sense。This is how you avoid doing very painful work。

 Because if you imagine， if you were actually trying to， on each of those do like a， oh my gosh。

 can I go and build another long， increasing subequ。

 you could imagine that if some day you had a line that went across to like 100 things。

 you would just not feel like doing the hundred and first because you'd say， oh， goodness。

 I've got to go and find all these increasing things。😊，But actually， if instead。

 you just wrote down the longest increasing one on everything before to get the next one。

 All you have to do is you have to just look over the numbers corresponding to numbers that are less than you。

😊，Take the biggest one， and add one。Okay， I just wanted to dwell on that。

 Give enough time for that to sink in。That's actually getting to the direction of a topic called efficiency and algorithms。

 If we were taking 251 computer science class， actually。

 there would be a lot of discussion about this。So we will actually make a few comments about this。

 I think in this class as well。 but that's not the main purpose。Okay， we're still going for proof。

Why did we do this， We did this For two reasons。 One is like。

 if I'm trying to find out that there's a long increasing path or a long decreasing path。

 it's pretty， pretty useful if I could somehow know that this table had some big numbers in it。Right。

 because look at that。 That's exciting。 There's a four here。

 I actually can't see which number I'm pointing to。 but I think it's one of these。 there's a four。

 If， if you have a four here， there exists an increasing sub sequence of length 4 and also here， too。

😊，Okay， how do you do the decreasing Oh， oh， question question。Yes， Andrew， could you say that again。

 But you've said because I can't read very clearly， but I see interesting stuff。He just O again。

And squared。Ha ha， so you are talking about this O of anbigo notation。

 We'll talk a little bit about that as we keep going。 But effectively。

 what you' are noticing is that if I need to do the next thing， how much work do I have to do。

 I have to do like amount of work proportional to how much stuff there is before。Which is nice。Okay。

 we'll get to that soon。 Meanwhile， let's go and do the decreasing。 Honestly。

 when the numbers are small at the beginning， it's easier just to look at it。

 It's really only later on that it's useful to look at this algorithm。 But let's， let's do this。

 So what's the longest decreasing subequence ending at the one。I'm going to remove these highlights。

 Oh， boy。That would be harder than I thought We'll do it this way。No。

 that is far harder than I thought。I will remove the highlights with the undo。

And I'll rewrite the four equals 3 plus one。Okay， and the longest decreasing people already saw is is。

 it's 2 because you can go with the three and then the 1。 Okay。

 what's the longest decreasing thing with the four is's easy to look at that。

 That's just like longest decreasing thing。 There's just one， Just the4。 Actually， 5。 the。

 the longest decreasing thing ending at the five is just， just just the 5。 So that's one。

 longest decreasing thing ending at the 9。 Now， that's just the 9。 So that's also a 1。😊。

It becomes a bit more interesting at this thing。 What's the longest decreasing ending at 2。

But now we can already remember how we're doing this。 This is really， really convenient， just to say。

😊，Well， if I want decreasing things ending at the two， let's go and highlight all the numbers。

 which are bigger than two。It's four of them there。

And then let's go and take the biggest thing that's under any of those。An add。

So the biggest thing under any of those， Oh， that's no fun。 I don't get to use the two。

 They're all ones。 So since they're all ones， I'll do one plus one。 And that's what's going go here。

😊，Yeah。So one plus one gives me a two。That's kind of interesting。 And for the six。

 what's the longest decreasing that ends at the6。 Well。

 let's go and find the numbers bigger than the6。Oh， there's only one of them。Okay， well。

 then that's not very exciting。 You just take that the number under it， which is one and plus one。

That will give you a two。Okay。Well， the theorem here is trying to say， if I have n equals 7。

 I should be able to get at least square root of 7 numbers。 Square root of 7 is like 2。 something。😊。

So if I can always find something at least2 point something。

 that means there has to be something which is at least three。 Well， it's true。 I see numbers here。

 which are at least three。 So the theorem is true for this one example。

But I drew out the whole example because that gives you a way to get a general proof。

And the way to do that is to look at this。Table and observe an interesting pattern。Let's look at。

The columns。11。Does one one ever appear again。Actually， no。Hey， look at all of the columns。

I'm just randomly picking some 31。2，2。Isn't that neat， they're all different。

When I say they're different， they might share the same number。

 They like the one and the bottom is the same as that one in the bottom。

 But the way I'm saying they're different is as pairs。 You never see the same pair twice。

Could that be a coincidence。Well， obviously not or else I wouldn't have asked the question。

 but somehow there has to be something going on here。 There's a really interesting observation。

The pears。Never。Occur。Again。H。Why might that be Chris。a one one。The next number。Or greater。greaterer。

啊，也。What。An increase。実は。At the bottom。The on increase。So。Iither。Or like。い的。Yes。

 so that's the heart of the argument。 You see， there was something I wrote here。

 which is that these are all distinct numbers。😊，That was useful。They're all distinct numbers。

 And since they're all distinct numbers， If you look at any two of these columns。

 any two of these pairs， the numbers that are above them。Well， they， they're coming。

 They come in some order。 It's either that the first one is less。 And then therefore。

 it's growing from one to the next， or the first one's more。

 And then it's shrinking from the first one to the next。Okay， and in this particular example。

 I have growth。 It's increasing from the first one to the next。 Now。

 if you think about how we were actually doing this algorithm， that's why。

 that's why I talked through this algorithm。 The way we were doing this algorithm。

The way you can find this number， this three is by looking over all of the previous things。

Seeing if anything has a number which is smaller than the five。 yep， it's there。

And then we would look over all of those， take the biggest one， and then get even bigger。

Does that make sense， So the important thing is because we have a growth from that column to the next to to this like jumping over to this column。

 because there's a growth for sure， the yellow number will be bigger。 In this case。

 it's not even just bigger by plus1。 It's bigger by even more。

 But that makes sense because the way you figured out the yellow number here。

 you looked back and you looked over all the things which were less than 5。

 which actually includes that guy， too。 And then you took the maximum of all of those things。

 And then you max you ramped it up。Therefore， when you were taking the maximum。

 you did consider this one。We ended up finding a better candidate， and then bumping it up。Okay。

 so let me just briefly write down the idea here。Since。If。The， if the number。If the numbers。

I'm calling these the numbers。 Okay， the numbers are like the numbers on top。 Oh， I'll use green。

 I've colors。 I'm used to teaching and like normal chalk。 So I。

 I just don't think of the fact that I've got colors to play with， but I'll say if the numbers。😊。

Are increasing。Are going up。 And I use the green for the numbers just because that's what I have here。

 They're green。 So if the numbers are increasing between the pairs。Going up between the pairs。

Between the pairs。 Yeah， between those pairs。Then， the yellow number。Must。Go up。And otherwise。

 the numbers are decreasing， right， Otherwise， the green numbers are decreasing。

 And if they're decreasing， the same logic tells you that the pink number should go up。Right。

 because if they're decreasing， then it's like， well， I could have used as an option to end there。

That that thing's telling me the longest decreasing that ends there。 And then， you know。

 I should get longer。And I exactly one of these things is gonna hold。

 Either the green things are gonna go up or the green things are gonna go down。Else。If。

The green numbers。Go。😔，downown。😊，Then， the pink。Then the pink number。Must。Go。Don。Okay。

 why am I going through all this trouble？ So I've now proved that these these blue pairs。

 they never repeat， never getting you the same thing again。How is this relevant。

I claim we are now very， very close to proving Er Se there。

Erder Seist theorem was something about We need to find there's always a monotone sub of at least square root of N。

 And what I know now is that over here， all of these pairs are different out of it。 What do you see。

😊，So， we can。一瞬で。Right， so if we assume for sake of contradict。That there is not。での出る。

And then you can count the number。It's going to be less than any。で感。The那。Yeah。

 so what's going on here is like it is actually a pigeonhole principle problem。 In fact。

 this is one of the classic， first hard pigeonhole principle problems when you。

 when you play with pigeonhole principle， Because somehow who would think of doing things this way of like writing down these longest。

 increasing， longest， decreasing paths。 But if you do。

 then look at the numbers that you're writing here。 What a set is， you know， intuitively。

 if the only numbers that are allowed to be here are smaller than that square root n。😊。

Then I can't get n of these columns。Does that make sense， I have N columns。 And like。

 what's the best I could do if I want to。Have n columns。

 and I want my numbers to be as small as possible， but I can't repeat。 I'd like pack them all in。

Let me make that， Let me say that in a slightly different way。 out of it。 You're right。

 But let me say that in a slightly different way。The slightly different way is， you know。

 let's suppose that inside this table， the biggest thing I see。Is L。

 L stands for the length of the longest monotone sub sequenceequence， okay。So， no。Sai。😔。

That L is equal to the largest number。Largest， yellow。Or pink。Number。

Here is an inequality that I can write down。How does。N， which is the number。

 N is the number of green numbers， right， N is the number of green numbers。

How does N compare to something in terms of L。I want to write an inequality。

 It's like N compared to something about L。Well， out of it。 How about you again。

 How do you translate， But you just said it between N and L。And say。Yeah。

 so now I know that n is less than or equal to L squared。😊。

That's the important punchline that we're getting now。I'm finding out that this， my name。

 Pohen Lo seems to be covering what I'm pointing out。 Is that true for everyone else。

 Is my name covering it。No， okay。 then that's good。 So， so basically。

 I have an n less than or equal to L squared。 Okay。

 and the reason why that's true is that's actually from pigeonhole。 You know what。 I want to。

 I want to write the word pigeonhole just so you have the whole thing。😊，Let me put some more space。

Pigeonhole implies this。 And why is it pigeonhole。 It's pigeonhole， because you know。

I said the Pional principle is just about too much stuff in too little space。

 And if I look at these numbers。 Each of these pairs， if L is the biggest thing I can have。

 then the most number of pairs you can have is L squared。 Does that make sense。

 Like L squared is all all all the possibilities you can make if L was the biggest thing。

 So now why I know it's n is less than or equal to L squared is because n's the number of them。

 So I better have。😊，Enough possibilities in order to have of these， end of these pairs。

Does that make sense to people。This is a key point that otherwise I just can't。 I can't have enough。

 The most I can have is L squared because each one's only allowed to appear once and the numbers that appear on top and bottom are one to L。

 So there's at most L squared of them。 Oh， but they're supposed to be n numbers altogether。Okay。

But why is this interesting， Well， this immediately gives you the answer。

 If n is less than or equal to L squared， what does that say about L。So， Brad it。Yep。

Then that's exactly what we wanted it。L is bigger， equal rootda。And。

 and that's just like if n was less than or equal to L squared， take the square root of both sides。

 you got square root n less than or equal to L。Okay， now I want to say a few things about this。

 First of all， we've proved this already。 That's the entire proof。 If it's here。

 It's nice to think of it in terms of this， this patient whole principle idea。

 That's actually the cleanest proof that I I I often use。😊，And now we also know it's， you know。

 basically best possible because of somehow this square root n was we had some construction last time。

 construction means like a way of writing down the sequence of numbers where the longest monotonone increasing or decreasing was only up to square root n issue。

But it turns out you can be even more precise。 So it turns out that there's another version of this theorem where you don't always ask for。

 you know， monotone subequence of at least some particular length。 In fact。

 there's another version of this theorem where you say。

Suppose I care about monotone increasing subequences of length S or monotone decreasing subequences of length T。

So there's a trade off between maybe I could， maybe I care more about the increasing ones than the decreasing ones。

 I could do the same thing where I'm allowing different amounts of length。So let me。

 let me write down like another thing you often see El Se there and written as。

So we're going to prove this next。Edish。Scorish。And honestly。

 you'll actually often see in a book It's written this way。 Okay， but I'm gonna， I'm gonna。

 we're gonna get， we're gonna get this statement together。

 And what this is gonna say is that every sequence。😊，Oh， now I'm going to put a blank。

We're going to fill in the blank here now。 this many distinct numbers。Always。Contains。A monoton。

Increasing。Subsequence。Of length。That's supposed to say length。U。Or。A monotone decreasing。I write M。

 O， N， O from Monone。Decreasing。Of length。Qi。Okay， so now I want to get a different version of this。

 I want to go and say， you know。Now I'm going to put the S and the T as fixed。

 and I want to put the number up there。This is actually how combinatoric sometimes feels。The。

 the statement we said at the beginning was something about if you have a long enough sequence。

 then there are pretty long sub sequenceequences in it that behave well。

And what this is saying is it sort of flips the problem instead of talking about how long of a sub sequence that behaves。

 well， we just go and put that。I'm gonna say， I want to have these particular subsequent length。

And that will happen as soon as I have some number of numbers。Okay。

 so now we want to fill in this top thing。How might I do that。

 I claim that we're going to do something that uses really the same proof。

Is there someone else I want， I want to see if we can get more people involved in this。

I want to write down something here for which it's true。

 And the proof is supposed to look very similar。 So I'm just going to already write proof。Right。

 proof is going to be similar。And we're going to be thinking about like， you know。

 looking at my numbers。Looking at， well， you know what， This is actually how I usually do it。

 I don't usually write that down first。 Usually， I go and say let's，'s do this proof again。

 And let's go and see how it changes。 Okay， so far， I don't know how many numbers I have。

 But let's just say the number of numbers is N。Say， there are。Capital N numbers。Okay， and that and。

 by the way， is just gonna be whatever that blank says。Now we're going to do the same thing。

 You write all the numbers， you write them。In order， in a sequence。And again。

 let's write this thing about the longest increasing ending there and the longest decreasing ending there。

Oh， yes， Thanks。 Thanks for asking the question。 What was the word before monotone contains。

 I just can't write。😊，Yikes， that says contains any other questions like on handwriting， please。

 please ask。 I'm sorry， I will try to do a better job。Okay， so。

 so write them in sequence and then like under。Each wen。Right。leength。Of longest。Increasing。

Or decreasing。Subsequences。Ending。There。Okay， so if I do this， what's gonna happen here。

 I don't know that they are called 3，1，4，5，9， whatever。 So I have some numbers， numbers。

 These are numbers。 They're blobs。 So I've got all these numbers。Don't ask me what those say。

 Those are intentionally not visible。 But I've got all these numbers。 And then underneath it。

 I've got like some pes， right， I've got some pes。Actually， for the sake of argument。

 I want to emphasize the pe doesn't have to be the first  one。 I've got stuff going on with pears。

 Can anyone start to tell me stuff that's true。 I want to have everyone be like on the。

 on the same page as we go and beat our way through this theorem。 What's true。

I'm doing the same thing as before， tell me a bunch of true statements。Jack。you want to。80门。Yep。

 yup y。 so so what you're saying is that there's something about the S in the top row and the T in the bottom row。

 let me translate what you said。Sometimes it's helpful to say something like。

Proofed by contradiction。 Let's suppose we don't have them。Is that okay， Let's try that。 Let's。

 let's do a proof by contradiction。 So I've got all this stuff here。 Let's make some observations。

 We wrote all of this thing。 Let's assume for contradiction。

That exactly the opposite of what you just said is true。 Okay。

 because what you just said is valuable。 I just want to flip it。

 Asum for contradiction the top row has nothing from S or above。 That means。

 assume for contradiction that the top row。Top row that there's like。

 is it okay if I call it top row and bottom row， even though it's the middle row。This。

's the top number。 Okay， so the top numbers。嗯。Anyway， I'm just gonna say it。 Top numbers。

Are less than or equal。To S-1。Okay， and the bottom numbers are less than or equal to t -1。

And the bottom numbers less than or equal to t-1。 You see。

 I wrote the -1s because these are integers。 S and T， I should have said are are whole numbers。

 right， So I have these whole numbers。 And if I， if I want to assume for sake of contradiction。

 then I only go up to the number -1。 Okay， tell me more true stuff。Sir。Oh wait。啊。这他说。是哪意。Yeah。

 so I'm actually writing down something that is going to give you what you just said。S-1 times t-1。

 And then I did， I did a plus 1。 Okay， because what you're saying is somehow， you know。

 if I have too many green numbers， then it's not possible， I'm gonna get a contradiction， right？

 And in fact， let's continue this。 As for contradiction。

 If the top numbers are all less than or equal to S-1。

 and the bottom numbers are all less than equal to t -1。 How many pairs are there。

 Like how many green numbers are there。😊，Zen。The number。Oh， no， I was gonna write number of numbers。

 then the number。Of the green numbers。Has to be less than or equal to S-1 times t-1。Is that okay。

 It's just because they're all different， right， just like before， we know they're different。 Oh。

 Andrew， did you want to ask or say something。Cool。This thing。

 So what you were going to say is what was just written。

 So the number of pairs is this S -1 times t -1。 Okay， but we were going to assume for contradiction。

 That's why it's really convenient now to have said， yeah， yeah， let's， let。

 let's try to do this with number of numbers being S -1 times t -1 plus 1。

 Now you're in trouble because it's too many。 The number of green numbers is like more than that。

 right， It's like this thing that you just got with the combinations。 plus1 oops， too many。😊。

I guess we didn't need the value of n， but that's okay。Oops。You have。S，-1 times T-1 plus one of them。

Too many。And that's a contradiction。Did this logic make sense。

And so this is being a bit more cautious。 We're actually using this S and a T。

 and we get an S -1 and a t -1。If you think about how this compares to what we just proved before。

Well， what did we prove before， Let'， let's put them into context before we had something where we wrote square root of n and square root of N。

😊，Right， we didn't write S and T。 We wrote square root N and square root event because they were referring to the same thing。

And so before， well， actually， what's， what's the consequence with this theorem that we have just proven。

 we actually can derive a consequence about， you know。

 if I write square root n -1 and square root n -1。😊，Up there。 And then plus one。

I have a true statement， also。Okay， so I'm going to actually write that down in the next screen。

Will I write that in next screen。 Yeah， I guess I will。So， a corollary or consequence。

Is that every sequence。Of。Square root of n。-1 squared plus 1。Distinct numbers。

Has a monotone substance。Of length。Square root event。

Let's put a when square root dependence is is an integer。

The only reason I'm adding this extra thing about square root of n being an integer is because with S and T。

 like those are obviously always integers。 If I use S and an integer and T an integer。

 but square root of n is not obviously always an integer unless you choose the n carefully。

 Why did I write this， I wrote this because didn't we prove something else。

 I thought we prove something is like， where we wrote n up there。

 And now we have a different theorem with something that's not n。 Is this a contradiction in math。😊。

How do I reconcile this， Sydney。快速。Yes。Plus one company。

The plus one comes because I want to write the word contradiction。

That's actually how you think about how this whole proof came together。

 I didn't tell you what I was going to prove。We wanted to know。

 what number can you write there so that when the proof has assumed for contradiction。

 you can end with contradiction。So the point is， we were trying to figure out what theorem can we write。

 and we have the freedom to write whatever we want up in that blank。

 We will choose the smallest number to write in that blank that contradicts this。

If I wrote plus 50 million， I would still get a contradiction。

Because it's like you can have at most S -1 times T-1。But you have 50 million more。 Nope。

 contradiction。Did that make sense。So。😊，And actually， please ask questions。

 We were getting into this theoretical side。 And when it's in the theoretical side。

 not everyone is super used to always thinking about like these kinds of theorems。And actually。

 what you're seeing is how even research works in research， you're trying to say。

 what's the best I can write there， What's the best fact I can prove。

And that's why the way I went about this is I said。

 let's try to copy what we did before and then see what what's the least I can get away with that lets me write the word contradiction。

😊，And now the question is， have we messed up mathematics Because we have this statement now。

Our statement here says that if I have a sequence of this many distinct integers。

 there's a monotton sub sequenceequence where discovered a n is an integer。 Is this a contradiction。

 I mean。I thought that we were supposed to have end up there。And we have something else。

 Do these work together， Andrew。Please， let's go。到あ。そかそ。This place。Okay， so the thing is I should。

 I should never have written say there are n numbers because the proof never used it。 Okay。

 so this say there are n numbers is actually not really useful。You know。

 as we were writing this proof， we were like， say there are N numbers。 Where is N appearing here。

 It doesn't。 If N doesn't appear anywhere else， you didn't need it。 You didn't need it。

All that you needed is that you write the sequence of these numbers that you started with。

And under each one of them， you wrote this， like blue pair。That's what's going on。

And then the point was， if you did all of that， then the number of blue pairs is going to be at most S -1 times t -1。

Yes， and that is less than N。 if we said this guy is at。Right。Okay， okay， okay。

 So what you're saying is this is a better result。 And that is the truth。 So you see。

 because over here， I wrote this， which says if you have a sequence of this many numbers。

 you will already find the monotone subsequence of length square root n。😊。

The important thing is that this thing here is actually less than n。So this is a better result。

 I I want to emphasize this is not contradicting what we proved earlier。 Earlier。

 we proved we have a real proof that says if you have n distinct numbers， this is true。

But now we actually have proven that if you even have a few less。

 it's already true that you have this monotone sub。Okay。So， a note。Oh， I'm still in the highlighter。

 okay。Note。How does square root of n-1 squared-1。 How does that compare a plus 1。

 How does that compare with n。 Well， it is just if you expand the brackets。

 It's n-2 square root of n。😊，Plus。1 plus  one。Okay， plus 2。Oh。

 I was hoping for something more obvious。 But I'll say， when n is like， you know， bigger。Like， if an。

 if an is like reasonably big， well， reasonably big meaning at least one， which it certainly is。

 I'll say that this guy is actually always less than or equal to n。For all positive vintages that。

Yeah， and that's just because if I took any， if you look at what's going on here， why is that true。

 The reason it's true is because if I'm comparing the left hand side and the right hand side。

 I -2 root n and then I plus a 2， so。I will minus more than I plus as long as the square root of N。

Is at least what。Which happens for all the positive villages at。

So the way to think of this is what we have just proved here is。You don't even need an in。

 and distinct numbers。You can get away with less and get the same conclusion。

 So we have not contradicted math。Oops。Have not contradicted。Math。This。Is what is called stronger。

Result。Stronger result means I can get away with less numbers。Can get the same。Result。Using。Fewer。

Numbers。Okay。Oh，sbaish。 Oh， yeah， you were just commenting under un equalal spot， okay。

So why did I do this， I did this， Because I want to show that this other version is actually extremely sharp。

 It's somehow really best possible。Before I change off of this。

 does anyone have any questions about this particular screen。

It's just trying to show that even though we prove something that looks different。

 it's just stronger。 This is just better。And I'm going to go back here。 This S -1 T-1 plus1。

 What would it mean to be best possible to be a best possible result。

 I need to go and like invert the logic here。 Okay， so I need to say somehow。

If I didn't have the plus1。It's not true。So I'm going to write that logic。

 We're gonna experiment with flipping the logic in the next screen。So what we know we proved。

It's like， every。Sequence。Of。S，-1， T-1 plus one numbers。Has an increasing of length。

S or a decreasing of length。T， okay， that is true。 And here's a fact。

Which we're gonna prove and finish today。The fact is。Without。The plus 1。It's。False。

So it's what we call best possible。Okay， I just wanted to emphasize what this means。

 And so best possible would mean I， I really need that plus one。

 So can someone help me translate this。 So what does this fact mean。Equivalently。

How do you translate this English statement of without the plus one， it's false。Well。

 I guess I have to say something about sequences of。S -1 T -1。 No plus1 numbers。

 But how do you invert all the logic， This is like concepts of math。

 I just wanted to have some practice like inverting the logic。

 Can someone help me tell me a statement that is equivalent that looks more like English or something that I could try to prove that's equivalent to this thing。

 which says without the plus 1， it's false。😊，And your statement should include something about。S。

-1 T，-1 numbers。What am I supposed to prove or get。I。

 I would like like to see if anyone else wants to jump in because this， I want to。

 I wantan to make sure everyone's following along。 We're doing a lot of theoretical math here。Andrew。

One number。Yes， thank you。 There exists a sequence of S-1 times t-1 numbers。😊，Distinct numbers。

 Let me just， let me emphasizee these were distinct。 I forgot it before。

 Let's write the word distinct again。 So it's complete。Distinct， it was distinct up there， too。

 and it's distinct down here， too， distinct。Numbers。

So that now what you said is like there is no increasing sequence of length S and there is no decreasing sequence of length T。

So， that theres。No， increasing。Sequence of length。S。And。There's no decreasing。Of lengthy。

 I'm just gonna。Say， say shorter there。 its the same words。

And this is like these exercises and flipping a statement， right in concepts of math。

 you have to change the when you negate things， you like change the every into there exists and you invert everything else so you somehow have nose in front and if you had an or before it becomes an and after。

 right。😊，So， I mean， even if you didn't take concepts， I hope this is， this makes sense to you。

 It's just like these， that's exactly what it means to be false。 You have to invert everything。

 If something was promising something to happen for everything， The opposite is， well。

 there's one thing or at least one thing where it doesn't happen。 That's what happened here。ok。

So that's， that's this inversion of the， of the， of the logic。不。

I'm pretty sure concepts is a prerequisite for class。 I think technically， I don't know。

 I thought it was。 but the way I am is， I know there are people from other majors who are taking this because they think is interesting。

 And unfortunately， not every major takes concepts right away。 So my style is， you know。

 I think almost everyone here has taken concepts。 If you haven't。 I'll say a few comments like this。

 Okay， let's finish this。 So now how do you do this。 So I need to go and find one。😊。

Is there a great way to make a sequence。Here it is。Here it is。Well， we graph it somehow。Remember。

 I was graphing them before。 And I was like， you just look at how high it is。

 And that's your sequence。 This is not quite straight。

Can anyone tell me an interesting graph I could make of numbers。 So this's like dots。 Remember。

 we did some dots before。 And I want some like。😊，Dots。

 dots in a pattern for which the longest decreasing， sorry。

 where there's no increasing sequence of S and there's no decreasing sequence of T。

 How might you try to make the dots on this。 This is almost like a review of what we had last time。

Briden。us one downward。Yes， so let's go and make T-1 long downward diagonals。

 So there's t-1 dots there。😊，And then， you know， this is supposed to be kind of split up like this。

And the next thing is， there's another T -1。Dropping down。Okay， and then there's the next one。

And so on。All the way onto the last one。Okay， so what we've just drawn here are。S，-1。Many。

Downward diagonals。Of length。T-1。And if you look at this， remember。

 the way to think of these as numbers is if you really wanted to know what it is。

 like it's a sequence of numbers。 you read them from the left to the right。

 and you just read off the y coordinates。 So for example， this looks like it's like 4，3，2，1，8，7，6，5。

 Does that make sense。 I'm just like reading the heights，8，7，6，5，12， if I could do math，121。

109 so on。 just keep going。😊，And if you look at this。

 why is there no increasing sequence of length S for the same reason as before。

 How do you make an increasing sequence， You gotta take only one from each of these。Strings。

And there's only S-1 of them。And why is there no decreasing sequence of length T。

 Because your longest decreasing sequence was just like one of these strips。So that's it。

 And that's actually why this is best possible。 That's this。

 This is what you'll see if actually you go and Google around for Ed Seish theorem。

 you will almost definitely see it in the form S -1 times t -1 and then plus 1， Bradon。😊，Oh， no。

That was the same one。 Okay， that's good， That's good。 Yeah， So， so so basically。

 if you go and search on Google， you'll probably see this thing。

 But I wanted to walk through it from all these other angles because I personally find it impossible to remember this kind of a formula。

 I always am wrong on the minus or the plus。 but it's easier for me to think of that there's like a square square root relationship。

 And it all just comes from the fact that you look at these these pairs。

 And I guess that finishes this。 that finishes the pigeonhole principle that we were going talk about in this class。

 there are a lot more problems that use the pigeonhole principle。 And we'll see that a lot later。

 later in this class in graph theory as well。 In recitation。

 I think there will be a problem that involves some pigeonhole principle type argument。

 And that's why there's a problem on the homework that says in recitation。 something was covered。

 So that will be on Tuesday。😊，Ku。Well， that's， that's everything。 So have a great weekend， everyone。

😊。

![](img/148dd50384abdf2fa84fd08aeb7daa83_3.png)

Thank you。