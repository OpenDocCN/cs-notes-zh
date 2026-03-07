# 卡耐基梅隆【中英⚡离散数学｜21-228 2023, Discrete Mathematics】 p10 P10 -BV1sFibBkEj7_p10-

嗯空空。

![](img/ae5805c6cadbec8a1a5c15be61346eba_1.png)

Hello everyone。 sorry about that。 Nice to see you all again。 Let's go ahead。 Okay， great。

 everyone can hear me， right？😊，We're good。 Okay， so we're going to talk about some some things today which are moving in away from the previous。

 the previous topic， were're done with inclusion exclusion。

 And now let's talk a little bit about binomial coefficients。 For that。

 I actually want to start with a famous class of questions。

 which is important to talk about just to make sure everyone has these tools。 Now。

 this is something which I understand that in some classes and concepts。

 you guys already talked about this。😊。

![](img/ae5805c6cadbec8a1a5c15be61346eba_3.png)

But just to make sure everyone's on the same page， I want to make sure that we talk about this too。

And so this 1， I often call something like pirates and gold。 It's like， if you have N pirates。

And if you have K gold coins。And those K gold coins are indistinguishable。The classic question is。

 how many ways are there to distribute these coins among the pirates？How many。Ws。To distribute。Coins。

To pirates。Now with these kinds of questions， there's usually two variants。

 I mean one kind of it is where you say that we have no constraintss on how many coins anyone gets。

 one version is where it's okay to have zero coins。😊。

And the other one is where everyone needs at least one。But this one is the first version。 It's okay。

To give。0， coins。To a pirate。Now， with these kinds of questions。

 it's also important to emphasize that you can't give half a coin。 This Otherwise。

 the answer would be infinitely many ways because you could just cut the coins up in all kinds of funny ways。

 But it's just that some， some non negative literature。 So again， this。

 this kind of question is well known。 And let's just bring everybody onto the same page to make sure that we all have this tool。

 Anyone。Have a sense of how you approach these kinds of questions。Okay。Ven Katsh。Okay， just a second。

Pirates， X 1， x2 up to X N， aha。Tell how many coins yep。Yeah。

And you're counting the number of solutions to this。

 And you're saying that's like a classic problem that you've learned before。 Is that the idea。

How to solve。Okay， and there was another thing some people have said stars and bars。

 sometimes it's called stars and bars， sometimes it's called sticks and stones。

 effectively the way you think of this， again， since this is often taughtd in other classes。😊。

The way that I often think of it is I actually use the original version， the pirates and the gold。

 I find that actually easier than the x1 to X n。And if I'm using the original version。

 then what Im talking about is I can actually think of drawing a diagram， right， I can say。

 for example， if I draw something like this。😊，Some things here。

 I'm going to put two of these vertical barss there。 I'm just drawing something。Okay。

 and what I've just drawn is a situation where I have six gold coins and four pirates。

So this corresponds to six coins。And four pirates。And it's a very particular distribution。

 the way that these coins got distributed is that the first pirate got three。

 the second pirate got zero， the third pirate got two， and the last pirate got one。

Is that clear like the way you can read this diagram is you just read it as if those vertical bars are the separators between the different kinds of pirates。

Between the different pirates themselves。 And then these dots， these are just the dots。

 which are how many coins there are in each batch。So if I did something like this。

 every one of these diagrams corresponds to a different way to separate six coins among four pirates。

 For example， I could also do this。I could put all six of the coins in front。

And then I could put all three of the barriers， and that means that the first pirate got six。

 then the second pirate got0， third got zero， and the fourth got zero。

And it's also important to note。That another way to do this would be all the bars first and then the six coins。

And that would be saying that the first pirate got 0。 second got 0， third got 0。

 and the fourth got 6。But I'm emphasizing that each of these last two counts differently。

 And the reason is because the pirates have feelings， and the coins don't。

So somehow like that that's just how it is coins are coins， right。

 and so this first pairrorate got six。 and then later the first pairrorate got zero。

 So that's a different distribution。😊，Does this make sense。

 I'm basically saying that every rearrangement of this kind of a drawing gives you exactly one of the ways to distribute these coins among these pirates。

Okay， and this is a classic hard problem because if you don't think of drawing these kinds of diagrams。

 it's actually really hard to do。We'll see another way to come up with the formula soon， though。

 after， after we get one formula for this， I want to do another， another way to get the same problem。

So in that case， let's finish this up。 Suppose I have like， you know， N coins and K sorry。

 An pirates and K gold coins。Can someone help me translate this interpretation into some kind of a formula。

 You can tell me the formula in terms of a choose or you can use factorials。 either is okay。

 and you can just type RH or raise hand if you want to say it instead of typing it。Andrew， And。

 address。It something like。Okay， so the way that came about is you said how many of each kind of thing are there？

Well， what I see here。Is that in all of these， the number of these solid things or the number of dots is。

The number of coins， so K。Of these。And then， there are n-1。Oh， no。

Let me use some colors because otherwise， it looks like those are ones。

 So these and n minus one of these golden bars。Does does this make sense。

 I'm just emphasizing I'm using the colors just to split the two different kinds。

 So it's not like it's n -1 once。And that's how many of these things I have。

 And I'm just trying to rearrange them。 And we've seen that if we're ever trying to rearrange a bunch of symbols where I have like a bunch of R's and a bunch of Ls。

 We saw this thing。 The answer is like。😊，Take all of the symbols that you've got。

All all the positions that you've got and choose where you put。 I don't know your favorite one。

 You said， did you， did you say choose N-1 or choose K。 Which one did you say。Choose and -1， okay。

So the number of rearrangements。Is equal to it's altogether how many of these things are there。

 K plus n minus1 slots for putting things， choosing n minus1 of where I put those vertical bars。

But by the way， I asked you that question because there's two answers to this。 Well。

 there's lots of answers， but there's another way to write the same thing because it could also be K plus n-1。

Choose K， because you could also decide， where am I putting those golden coins， right。

 I have to put K of them down。So this is the formula that comes out of this kind of a problem。

If you haven't seen this idea before， these are famous hard problems。

But now I want to go and do it a different way。The other way comes from saying， you know。

 let's just try to do a small version of this。 Let， let's do some small versions of this problem。

 and we'll notice some really， really nifty patterns。Okay。

So the first one is if I wanted to ask a question with just like two pirates。Suppose I have 8 coins。

And two pirates。How many ways。And here， the number of ways I'm allowing a pirate to get0。

 And I'm also saying for this one， you don't need to use a really fancy formula。

 Can anyone tell me how you do this。😊，Breden。You the you mean some。Yes。😊，9 since the first。Pirate。

Gets。0。Up to 8。 and then the second pirate gets the rest。Okay。

 so what I've just found out is if I have8 coins two pirates。

 then the answer is going to be 8 plus one， which is 9。 That's kind of nice。

 But if I have three pirates。😊，Suppose I had8 coins。3 pirates。Number of ways。Equals now。

 what I want to do here is there was someone who came to office hours today who had an idea on how to do these kinds of questions where the person said。

 you know， what if we just kind of branch off based on what happens to the first pirate。

You could do that， right， The first pirate， that's what we did before。

 The first pirate is going to get anywhere from 0 tonight。Okay， so it's like the first pirate gets 0。

First， pirate could get 0 or 1， or all the way， not up to 9， all the way up to 8。Is that okay。

 So these are all， I'm going to draw a giant tree diagram。 So if the first one gets 0 up to 8。 Now。

 this person had a clever idea， they said， in that case， if I've already given to the first。

What's left over。Here， the second and third。They have to split。8ight。

Does that make sense Because if you give zero to the first one， the second and third， they split 8。

 How many ways are there for the second and third pirate to split 8？Well。

 we have sort of seen that already。Right， we just did that。 We。

 we know that if you have two pirates splitting some number of coins。

 the answer is just number of coins plus one。Okay。So this is telling you the number of things。

 number of ways。Here is 9。But how about the second row， Well， if the first pirate gets one。

 how much do the second and third have to split？7even。😊，And then the number of ways would be。

7 plus one， again， because of the way that the logic works for just two pirates。

 you can just give the first one anything from 0 to the total number。

 and that's like the total number plus one options。8， and it will go all the way down。

To the last one。Split 0。And here's where we can see that our conventions make sense。

How many ways are there for two people to split nothing？There's actually one way， not zero phase。

The one way is like this。There's nothing。And that is actually one way。

So what we found out now is that this big sum is from 9 down to 1， or 1 plus 2 plus 3 up to 9。

 What's the formula for one plus 2 plus 3 up to 9。We've got a formula for that。

 but we've already learned that by this point in the math for everyone that you guys have been doing。

 It's like。Anyone want to do a raise hand on this。Okay， I see something。 This is from Thomas。

9 times 10 over 2。9 times 10 over 2。 Hey， can I write that as a truth。That is a tru。

9 times 10 over 2 happens to be a choose。That happens to be。Aha people are saying this is n plus1。

 chooseose 2。 I think this is 10 choose2。So it looks like what we just found out is in general。

 it's going to be like， I think it's n plus 2， choose 2 is what we're going get。 right， if I have。

 if I have n， if I replace with the8 becomes an n， it's like n coins 3 pirates ends up being n plus 2。

 choose 2， which is actually consistent with what we've proven before。So over here。

 if I had in general， if this was N coins。3 pirates。That's gonna give me N plus 2。 Cho two ways。Now。

 why am I doing this？ I'm going to do it one more step。

 And the reason is because there was an old exam problem that somebody was looking at。

 And that's why the person came to the office hours。

 And the old exam question had like splitting among four pirates。But what else could happen。

 Suppose I have， now let's just use N。 Okay， Supp I have N pirates。No。

 it's end quiteins and quitetes。And coin's four pirorates。I've just flipped the n and the K。 Okay。

 but we we when in math， you can use a letter to represent whatever you want。 N coins， for pirates。

Number of ways。Equals， well， what you can do is you can still say the first pirate。

 How many are you going to get。From 0。To one。All the way down to N。 Okay， but now we can recurse。

 This is actually what people wanted to do。oo， There's a comment。

Can we also write the first one as n plus one choose 1。 Yes， of course。

 there's nice pattern where the what happened here。 Yeah， so the first one is n plus 1。

 and that is n plus 1， choose1。 absolutelyly。 So there's a pattern。 n plus1 choose 1 over there。

 N plus 2， chooseose 2 over there？ Well we probably are gonna get n plus 3， chooseose 3。

 But why that's what we want to figure out。 So if I look at this like 0，1 up to n。 How do I continue。

 Can someone help me out here。 I want to continue the logic I did previously。

 And I want to find something nifty。😊，Bdon。えさんが。2。第一。前です。Okay。So I， unfortunately。

 was not so clever as to write an X。 Oh， I still have space。 Here's an X for you。So。

 that's like sharing。Sharing。Share n minus x， okay。And the number of ways we know。

 we know how to do that。 yeah， sharing among wait， what do you mean， second to and I wrote it wrong。

 Second to fourth， second， third and fourth， there's no end pirate， second。Third and fourth。Okay。

 so between those second， third and fourth is， that's three pirates and we know the answer there。

 that's the number you're sharing plus two， choose2。😊，So we have n plus 2。 Choose two ways。

 This is going to be n -1 plus 2 is n plus 1， choose 2。This is n minus x and n plus a 2， choose 2。

And this is 0 plus 2。 Choose 2。 Oh， how nice。 That's one。 That's nice。

 I do expect it to be one at the end。嗯。No。We actually already proved it another way， that somehow。

The sum of all of these things magically is supposed to be n plus 3 choose 3。

 We know that from this like Sts and stones argument。 But what we've just discovered is that's neat。

 It looks like if you add up these things。😊，The answer is always going to be n plus 3， chooseose 3。

By the way， we already have a proof of that。 That proof is called the other thing we did。

 The other thing we did， this is called counting in two ways。

 We found one way to count how many ways can you distribute n coins among four pirates。

 And we know from the previous thing is n plus 3， chooseose 3。 Therefore。

 I now have a proof that this whole sum is equal to n plus 3。 chooseose 3。😊，Okay， that's neat。

 but in that， we're all about finding lots of different ways to prove the same thing。

And turns out that we're onto something， what did you want to say？あ取。Just white。the name。The话。哈奇。

Hockey stick。 What hockey stick。 I don't see any hockey。

 although it is pretty cold in some parts of the country。 So if you want to say hockey stick。

 I need to draw Pascal's triangle。 I think that's what you're getting at。

 Let's go and draw Pascal's triangle。 And where are all these， like choose 2 things。 Well。

 I'm going to use some color coding。 Okay， in Pascal's triangle。 Here's what it looks like。

 I have a0， choose 0。😊，That's the top。 I have a。1， choose 0。 I have one， choose 1。I have a 2， choose。

0， a 2， chooses 1。 And now the two chooses 2， I'm going to use yellow just because that's what I used over there。

 This is2， choose，2。Next， let's go to the three row。3，2，0。3， choose 1，3， choose，2 is yellow。

And then there's this three， choose three。Okay， and then there's42 0。4， choose 1。

 I'm going to be lazy。 So I'm going to stop this row。 Im I'm not going to write the fifth row。 Well。

 actually， I will for a different reason。4， choose 3 and 4， choose 4。

 but I won't write the fifth row。 the row for the5 chooses quite yet。 So I've written all of this。

 And I've gotten like this sum， these things。 But magically， magically， I mean。

 we somehow know that if I add these stuff， choose 2，2， choose 2，3， choose 2，4。

 choose 2 all the way up until n plus 2， choose 2。😊，Somehow， the answer is supposed to be n plus 3。

 choose 3。So， the sum。What's a good color for this。The sun。Of all of these things。

Where is that supposed to be in Pascal's Triangle？I've drawn Pascal's triangle。

 The sum of this particular diagonal is supposed to be a very specific number。

 a specific position inside this triangle。 Where is it。I've got some 2， choose 2，3， choose2，4。

 choose 2。 It's supposed to add up to what choose 3。Bdon。Yeah。That's right here。5， choose，3 is here。

That's why this is called a hockey stick identity because it looks like a hockey stick。

If you go down。A stripe， a diagonal， a diagonal stripe in Pascal's triangle。

 where your slope of your diagonal is the same as the slope of the left edge。 If you just add， add。

 add， add， add。Your answer is always the thing down there。This is called the hockey St identity。

Or theorem， or whatever。Let's go and prove this thing。Okay， let's let's， let's go and prove this。

 By the way， we could have said， well， we already proved something with this counting in two ways。

 but there's a more direct way to prove the hockey stick identity of why if I just go and add up all of these。

 then I'll get that next one。Oh， question。 And the other way， yes， I， you're right。

 because because Pascal's triangle is symmetric。If I went and went the other way and took the other kind of diagonal。

 then the sum would be， you know the hockey stick， but pointing the other way。Okay。

 so that you could put the hockey stick in either way。Okay。So now， yes， yes， yes， exactly。 Sean。

 Thanks by symmetry。 So now let's go about proving this this particular hockey stick identity。

To get to that， the easiest way to do it is to actually first say， I didn't really give you a， Well。

 actually， I did give you a proof of why in Pascal's triangle。 When I add two of these chooses。

 Then I get the choose， which is right under them。 I told you that was because we we could think of all these like paths through a diagonal grid。

 That was a legitimate proof。😊，But there's another very simple proof of that。

 where you don't even need to think about paths。 You can think of these as counting the number of ways to pick a subset of a particular size from a bunch of stuff。

 Okay， so let's start let's start talking about all of these binomial Pascal's triangle identities。😊。

The first is one， which is the simplest fact。Which is that if I take and choose K。Plus。

And choose K plus 1。What is that， Well， think about where they are in Pascal's triangle。

And choose K and choose K plus  one。 They should。 We want them to add to the thing right underneath it。

 right， And the thing right underneath it is going to be n plus one。

 choose something because that's the next row down。And every time I do these things。

 I always have to ask myself， n plus one， choose what I it choose k or is it choose k plus 1。

 or is it K plus 2 or k-1。 And the way I always think of it is， look， when I take Pascal's triangle。

 If I go one row down， it kind of goes across the aagonally this way。 Do you know what I mean。

 Like if that was choose ks， choose Ks will be there。

 It's like the choose zeros are here and I'm just going along on that edge。

 And then the choose ones are going this way。 So the thing that they should add up to is choose K plus  one。

😊，Okay， let's prove this。 It turns out that we can prove this just by even another accounting in two ways。

 which is even easier， which is just like， what does it mean anyway。

It means the number of ways to pick a subset of k plus one things from n plus one things。

 So I'll call it the right hand side。Is equal to the number of ways。To pick。K plus1 things。

From n plus  one。Total， things。Okay， that's legit。Now， if I'm supposed to pick K plus1 things。

 I can break into two cases and whenever you break into cases。

 you just make sure they are mutually exclusive and they cover everything。We've got two types。

 Let's just throw it this way， actually。Two types。One type is where you pick。The n plus first thing。

And the other type is where you don't。And it's pretty clear that if you're going to pick K plus one things。

 you're either gonna pick the n plus first thing or you're not。Okay。

 so that's very clear that this has split into two disjoint things and like between them you've covered every possibility。

Well， how many ways can I do this？ Suppose I've picked the n plus first thing。

How many ways can I pick K plus one total things from end things。

If I've actually already picked the n plus first thing。How do I think about this one。And住。

Left hand side。Yep， pick K from the first and things。And that's equal to just N choose k。

And the other one is where you don't， so you better pick K plus1 from the first end things。

Pick K plus one。From the first end。Which is equal to and choose K plus one。Okay。

 so this like very basic identity， which is the， the heart of how you make Pascal's triangle at all。

 It's like you take these two things。 You add them together， you get the thing underneath it。

 That's like easy to prove with this way of counting the number of ways to get a subset。

Now I want to use that to get this hockey stick identity。How could I do that？Well。

 now I I'm gonna make a Pascals triangle。That's Pascal's triangle。 And suppose I'm going to do a sum。

 which is going along here。 doesnn't even need to be the choose to sum。

 I'm just taking this sum going down。My goal is to show that the sum。Ad's up there。Okay。

What might be a good way to do this？ Well， let's go and try to use induction。

If I wanted to use induction to prove this picture， what would a base case look like。

There are actually lots of different base cases that I have to worry about because I could be talking about going down this particular diagonal。

 or I could be going down this other parallel diagonal。

 Can someone help me out and give me a simple base case， Eric。Right。

What I heard you say is like N choose n。 So what you're saying is a base case to prove this would be。

 book， just that one。 And those are all one anyway。 So the sum of that， which is just one， is this。

 which is also one。 Is that clear， for the base case， The base case of proving this kind of a thing。

 The base case， there's the infinite family of base cases。

 Those are just where I grab the thing on the very edge。 I say that's my diagonal I'm stopping there。

 And the sum is just this one down here because they're all ones， anyway。😊，Is that clear to people。

That's the base cases。 There's like all these base cases。

So what I'll write is maybe I'll write over here。These are all the base cases。Okay。

 so if those are all the base cases， now I need to know what does what does the induction step look like。

Induction step means I have something like this。 In fact， this is going to be my picture。

For this kind of induction step， it's like， suppose I already know that the sum of all of this happens to be there。

For the induction step， which I'm going to label on the left picture now。Induction step。

What I've gotten is I know that the sum of all of this is equal to that。But I'm greedy。

 I want to do more。 I also want one more。How do I know that the sum of all of this。Is there。Jack。

I do we know that we're gonna to go to that。那照。There's a number in that。

It agrees about3 gap right now。Check it。Yeah， great， great， great。 So what you're saying is like。

 okay， look， I know that the sum of this part is there。 Okay， so I'm going call it the sum of the。😊。

Induction hypothesis。 Yeah， induction hypothesis。 That's what it's called。

 This is the sum from induction hypothesis。Allright。

 But now what I'm trying to do for my induction step is I get one more thing。 Allright。

 so now I need to know， why is it that if I take all of the green highlighted thing plus the blue spot。

 Why does it land there。😊，And。Pascal's identity， The thing we just saw， is's because， look。

 the new thing is that blue spot。 I already know that all that green stuff added to that。

 So I already know by that Pascal triangle identity that the sum of these two。😊，Is there。

That's why it works。Like， that's the entire proof of the hockey stick。 Okay。

 so now what I know is this thing here is the new one。Maybe let me use white to stand out more。

 This is the new one。Right。And so if I have a new one plus the sum of all the old ones。 Well。

 that's here。 That's the， that's the new sum， the new sum of everything。😊，So， this thing。

I'll draw two arrows。 This is the new sum。Of everything。Bang， you're done。

 So that means that the sum of this new thing， this induction step is exactly what you expected it to be。

And you can just crawl your way through Pascal's triangle that way。

It's actually that Pascal's identity， that's what I call it。

 but but the Pascal identity of like adding two things above gives you the thing below。

 that's like the tool you get to use for these induction type proofs。Okay， so that's。

 that's actually why this hockey stick identity is true。 Hockey stick theorem is true。

I'm going to give another proof of it， too。 If you can tell today。

 we're basically talking about all these like nifty things about Pascal's triangle and different ways that you can prove things which have already related to this pirates and gold thing。

 Oh， yeah。 And now we know why that pirates and gold thing works。 If I pull back。 It's like， well。

 that's just the hockey stick identity。 Add up， add up all of these things。 That's n plus 3。

 chooseose 3。 That's why this works。😊，So， this is some。And plus 3， choose 3。

 And then the person who came to me in office hours and said， you know。

 what if I try to do this splitting thing， What I told the person is， is's a little bit complicated。

 It can be done。 And this is how you do it。 You could actually conceivably do this with five pirates。

 Also。 Do you see what would end up happening。If you did it with five pirates。

 then I get all this stuff and it's all choose three。Which by the hockey stick identity。

 gives me the thing choose is for。So you can actually use this way of thinking to go and prove the whole sticks and stones。

 stars and bars dividing pirates into gold， No， dividing gold into pirates。 anyway。

 these kinds of things， they all actually are interconnected in that way。😊。

I'm going to pause here and ask， Does everything here make sense so far。

 Because we just intertwine two key parts， which is this Pascal triangle。

 as well as this pirates and gold。 I want to give you one more thing about the pirates and gold before we continue to fly off into into Pascal's triangle。

 And it's that twist。 Remember， I said at the beginning that。😊。

We said it's okay to give  zero coins to a pirate。Well， what if。

 what if the pirates don't want to be paid nothing。 So suppose we put some rule。

 Supp everyone needs at least one coin。 That's like the standard variant of this。

 because these things like x 1 plus x 2 up to X n equals K。

 One version of this is where they're all non negative integers。

 The other version of this is where they're all positive integers。

 Let's just deal with that right now。Let's just throw some actual numbers so that I can do it easier。

 Suppose I have seven coins。And I have four pirates。How many ways to distribute。To give。

Where every pirate。Gets。At least one。Oh no， everything broke。

 we have need to go back to the drawing board， well not really shot。Can give every。And then。Yes， yes。

 yes。 We love this。 We love to reduce problems to old problems。 First， give every pirate one。😊。

1 gold。Okay， then we have the old problem because it's like， great， you're happy。

 Now you got your pay。 Let's go back to the old thing where we're allowed to give you nothing more。

 So if you do this， then what you have is you have three coins left。😊，4 pirates。

And now it's the old problem。The number of additional coins you get is just a bigger equals 0。

 And so what's the answer to this It's like。Actually I'm always slow with this。

 I always actually just draw what I'm dealing with three coins。

 three separators for the pirates because I'm very bad at forgetting which one's supposed to be minus1 or whatever。

 but this is the general picture， three gold coins to split among three vertical bars because I only need three vertical bars to separate four things。

And so that looks like a 6， choose3。And some people sometimes write this in terms of the n and the K。

 and there's some formula。 It's like gotta n minus K or whatever。

 I don't actually usually think about things that way。 Oh， I guess I could。

 It's like n -1 choose K -1 or something。 maybe， maybe， but I always just draw it。

 and Ive figured it out。Okay， so that finishes this whole pirates and gold thing。

 This is a classic hard problem in the early stage of combinatorics counting things where you wouldn't think of doing like these like dots and bars。

 But now we also see that if you understand Pascal's triangle， even if you didn't know this。

 you could force it out by expecting that Pascal's triangle is full of surprises。😊，Along those lines。

 I want to give you another surprise， which is in Pascal's Triangle。And。

This particular statement is one which has a complicated name。

I remember the first time I saw this statement's name。

 I said that sounds very must be a very hard statement because it's so long。 it's called Vander。Md。

Vandandermans。Convolution。Okay， Vandermont's convolution。

 And what this statement says is it I'll give it with some numbers。 It， well， maybe not numbers。

 I'll use letters。 So if I have like， no， I will use numbers。 If I have something like 7，2 0。Times。

 let's choose some other number， like。10， no，10 test，2 digits， too long，9， choose。5。Okay。

 what I'm going to do is I'm going keep 7 choose stuff and keep 9 choose stuff。

 But I'm going to let those things on the bottom move。 Oh， let's use some colors。 That'll be better。

 So let's go and use 0 and 5。Te  one and 4。And then。7， choose something times 9。 Choose something。

 but those will be。2 and 3。Plus，7， choose something，9， choose something。And then， it becomes 3 and 2。

Plus。7， choose something，9， choose something。 You can hopefully see the pattern of what's going on。

And this will be four and one。And the last one is going to be 7， choose something，9。

 choose something。And those will be 5 and 0。This turns out to equal something nice。First。

 before we say what it equals。I， I mean， most of the time you'll see this with like big sigma notations。

 like summation notations and ends and Ks and I's。 I'd like to just do this because you can see the pattern。

 Can anyone tell me what pattern you observe me doing just so that we're all saying that we're looking at the same thing。

What's going on， How did I choose to write this stuff down。it same。Okay， good。

 So the the bottom stuff。 it always adds up to 5。 And I found all the different ways to add up to 5 on the bottom。

 Okay， and on the top， I stuck something on 7， and I stuck the other thing on 9。

 And Vanandermont's convolution says， well， if you stick the first one at 7 and the second one at 9。

 And the works with other numbers， not just 7 and 9。

 And you kind of let the bottom thing move over all the different ways to add up to 5。

 What are we actually counting。😊，Well。Here let's write the proof without telling you what we're proving。

 but as we write it down， you'll be clear of what we're counting。I'm going to think of this， as。

A lump of seven things。Let's use squares。 Okay， or rectangles。 So here's a lump of 7 things。1，2，3，4。

5，6，7。 So there's  seven things in there。 I'll just draw once the seven just to indicate there's seven things there。

 And then I have a lump of9 things should be a bit longer，1，2，3，4，5，6，7，8，9，9 things。

The first part is telling me， I'm going to find out how many ways I pick nothing from here and pick five things from there。

😊，So the first part is pick 0 from here。Multiply by p。5 things from there。Okay。

 then we're going to add to the number of ways where I picked one thing from the first one。

 multiplied by picking。4 things from the second one， adding all the way down until I pick。

5 things from the first one。 And I pick。0 things from the last one。What's going on here？

Is there a more nice way or more compact way to explain what's going on。

 Can you see that we're doing some picking Thomass。😊，嗯。Partitioning the different ways to pick five。

So you。Hereさ。ない。系。Okay， so， so I think I want to， I don't want to use the stars in Paris thing because I don't see how to use that immediately。

 but I want to use the rest of what you said， which is I'm picking five things from how much from 7 plus 9 things。

So the answer is just 7 plus 9。Shoose 5。Right， because if I add all of this together， it's just。

呃 picking。Pick five things from anywhere。Pick five things。Fng。The7 plus 9。

Did that make sense to people。 It's like， look， if you just look at it。 I got 7 things here。

 I got 9 things there。 How do you pick five things， Well， you gotta not you got to。

 but you can think of the five things as being split across how many in the first batch。

 How many in the second batch。And that is， by the way， why， as Issein observed。

 these things that I'm choosing。 they always add up to 5。

 and they're kind of moving in opposite directions because I'm just trying to say。

 how many are you picking from the first batch and how many from the second。

So that's just this vandermon's convolution。 It's a really fancy word， but it just talks about。😊，I。

 I have a big set， which is 7 plus 9，16。 And from that set， I'm picking some stuff。

 And it happens to be the case that if I decide how I split the set。

 then I couldn't go and I can say that adding up all of these different possibilities gives me that last one。

Okay， question， Andrew。Does that hold for a higher number of chooses。 Yeah， it does。 I mean， you。

 you see the beautiful thing about all of this combinatorial arguments is I don't want you to memorize a particular argument。

 It's it's more of like trying to open the mind that there are lots of these different ways that you can count things。

😊，Okay， and what we have just seen is we've， we've seen different ways of approving these identities。

 One of them was where I went back and I said， look。

 you could count something and break it into two possibilities。

 whether the last one was in or whether the last one is out。Or over here。

 we can do something where I've got the 7 plus 9 stuff。

 and I kind of arbitrarily cut it into two pieces。 And you see how your set of five things overlaps with those。

And then over here， we actually used induction to go and prove one of these binomial coefficient identities。

 that's what they're called， but I used induction to prove。😊，And maybe to finish up for today。

 I want to say this last one that we just used induction to prove。

 You can also write that as a story of counting things in two ways without using any induction at all。

Let's go back to the hockey stick。The goal， of course。

 is if you've seen all these different ways then hopefully if you're thinking about something。

 you can also creatively come up with your own way to count something in two ways。

So alternative proof。Of the hockey stick。Well， what was the theorem， The theorem was。

 Let's write it now。 Then theorem is， I could think of it as K choose K。Plus， k plus 1， choose K。

Plus， K plus 2， choose K。 Remember it was choose 2 before， but it's true of anything。

 plus up to n choose K。The answer was supposed to be the n plus 1， choose the K plus1。まですです。

I'm not taking that Okay， so this is this is supposed to add up like this。😊。

And now here's another way to prove it。Now， let's think of counting things。 So what are we counting。

 N plus  one choose K plus1。 That's the number of ways to pick K plus one things from n plus one things。

 Okay， so on the one hand， let's call it the RHS。The right hand side is equal to the number of ways。

To pick。K plus one things。 And now I'm going to name the nplus one things。From。1。2。3。

All the way up until n plus one。Alright， they all have names now，1，2，3， up 10， plus one。Now。

 here's a way you could split this。 Oh， ait， are you gonna。 do you have the idea。What's your idea。

In case I'm the biggest members。Yes， that's why I wanted to give these names。 Okay。

 so whenever you use the word case on， whenever I want to split spread all this apart into all of these mutually exclusive disjoint but covering all cases。

😊，I need to think about something that I could iterate over。

 And there is going to be a biggest thing that I've picked because all these numbers。

 they're called 1，2 up to n plus 1。 One of them is the biggest。

So what you can do is you can say this is equal to the number of ways。Where the biggest。

Is equal to and plus one。 Oh， no， there's a equals and equals。 So let's put parentheses， okay。

English language should have been invented with an ability to put arbitrary nesting app parentheses。

Actually， itll be terrible。 Then， then， then， then you'd have to in your text editor。

 you need the match per command all the time。 Never mind。 Okay。

 and plus the number of ways where the biggest is equal to n plus the number of ways。

 where the biggest is equal to n -1 plus dot dot dot plus the number of ways where your biggest is equal to1。

We're going to get some of these to be 0， by the way， Because， for example， if K was 50。

 there's no ways to make the biggest equal to one。 but we'll see how to deal with that soon。Now。

 let's do them one at a time。Suppose I want to know how many ways can I pick K plus  one things from n plus 1。

 but from 1，2，3 up to n plus 1， where the biggest one is that one。

 Can anyone tell me how many ways I could do this。And why。Bd。This point you've already chosen at。一て。

Yep， one up until N。Which is just equal to N choose K。All right。

 and that that was the last thing I've got there。Remember if I've cased on the largest thing。

 Now it's done。 I got it。 I I need to pick K plus one things。 That's one of them。

 And the rest all have to be picked from the， the stuff before it。And if you see where this is going。

 the second one is going to be pick。K things。 But now from1 up until n-1。Horay， that's n-1。 choose K。

Because I've n -1 stuff from which I pick K。 So if you see what's going to happen。

 I added all the way down。 The next one's going to be n-1， choose K，-1。 No， it's not。

 It's going to be n -2 choose K。And it goes all the way down to zero choose k。So apparently。

 what I've proven is something more。 I've proven that if I take 0 choose k plus 1 choose k all the way up to n choose K。

 then it's the right hand side。 How do I reconcile this and finish。😊。

I'm supposed to do it from K choose K。 What's up with the0 choose K， Sydney。Yes， so it important。

 Okay， that's one way to put it。 It's like， oh， come on， you're picking K things。 Stop there， right。

 Stop at the K。Because there's no more。 The rest are all 0。 That's one nice way to do it。

 If I do that， I'm gonna write this as wait a second。 No， no， last one， K plus 1， K plus 1。

 I'm picking K plus one thinks okay， if I have a K plus one there， that goes to a K choose K。

 And then what the rest is is the rest are all 0， since no way。😊，The largest。Is。Any of 1。

2 up until K。Yeah， because I'm picking K plus one things。

 So there's no way I can have that as largest。 Another way to say the same thing is that。Like 5。

 choose 200 is 0。There's no way to choose 200 things from 5 things。Both of those finish it。

 And so this is now giving you the proof of this identity because I've added all these things。

 and I got the right hand side。 And that's the principle of counting things in two ways。

 And now we have just found out that this pascal triangle is full of all these nifty coincidences that you can prove in all kinds of ways。

That finishes the class。对。

![](img/ae5805c6cadbec8a1a5c15be61346eba_5.png)

Thank you。