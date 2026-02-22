# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p03 03 - Bits, Bytes, & Integers II -BV17jcReyETC_p3-

すごいです。我。开始。P better。Good afternoon， everyone。Yeah。お。So just a few announcements。

 as you know Web zero has been out there， it's due this Thursday， there are no wait days。

 no grace days， no excuses， so don't put it off to the last minute。哦。It should be everything set。

 you should be able to do it lab one became available sometime early this morning。

And for starting with Web one， the way we're going to release the information you need to do is through this website called the Project Zone。

 which will guide you through the write up and require you to answer some little simple questions along the way is our way of。

Of encouraging you to read the write up carefully and only once you get through that。

 you'll get a little code。Now you can actually start the web and do all the work of the web。哦。

Because you'll be able to get the files actually for it。Of Voab directly。

But to see the write up and to actually submit it to AutoAb。

 you'll have to have this little pass key that comes at the end of your completion of the write up through the project cell。

And then you'll put that in a file and submit that as part of your hand。So that's all described。

 but there's this sort of two phase part that there's the project zone and there's Autotwa both。

This particular web is。Well make use of what you learned last week and this week about bit spikes and numeric representations and so in particular。

 a good chunk of the problems are just bit level manipulation questions that，The material。

 the electric material for it will be from last week and from today。

 and then on Thursday we'll talk about floating point and that will cover all the information。

Then next Monday will be your first recitation class and it will talk about that quite a bit more。

 but I'd recommend you get started before next Monday on this way question over there。

So I did kind of vote by。拜拜。I inspire。你在补后。Yes， lab zero is not required to go。In La one， by the way。

 I'm not sure if AutoWb is working quite right yet on it started submission。

 so if you really out early and you want to submit it today。

 it might not work we're tracking that down。好。But you can certainly get started on the web。As it is。

This and also mention， and I'll say this in various other places。

 this particular lab has more kind of quirks and bumps and workss in the software than。

I feel good about。So you just put that one。啊。And the reason is because we've kind of patched together this odd mix of software to support how we do the checking of your code for its conformance to some programming rules and correctness and things that。

啊。It try mean might there's some sort of odd aspects of it that are all documented in the right up but。

It's easy to overlook that when you're first skimming through so this is one of these things before you run off to Piazza and ask what do you mean about this or what do you mean about that or I get the following weird error report please reread。

They're write up several times because a lot of times。

All of a sudden' jump out at you that you have to have。

Write curly Grace in the first column to finish your function definitions that aren't part of the normal C programming conventions。

So today we're going to continue talking about the representation of values in particular integert values as bits。

 and we started that last time and what we'll do is，Continue that today。

 talking about the different arithtic operations you want to perform on this。

We'll also cover some more general the sort of how information is stored in memory and how it's referenced。

So you recall from before that the two equations that you really have to know and understand and everything else follows from those two equations is given a set of bits。

What number does that represent and we can talk about that number as either an unsigned integer。

 meaning its value is either zero or greater。Or the other representation we'll look at in this class is chooses complement representation。

 which allows you to have numbers that are both negative and positive。

 and the way that works is by simply making the most significant that。

Have a negative value to it so that if it's set。Then it sort of makes the number very negative。

 and then you can add back some more bits， positive bits to bring it back closer to zero。

And so we looked at the example and here's the correct version of it that 10 is simply two plus eight。

But minus10 is minus 16 plus4 plus 2， so you start with minus 16。

 the add back4 that hit you minus 12， add back 2 that gives you minus 10。

I should also mention two's complement， there's nothing in the C standard， in fact。

 the C standard is very careful not to say， thou shalt use two's complement numbers。

But the X86 processors， which is what we use and really just about every processor that you're likely to come across does use tos compliment。

 so you can't always assume this when you're writing programs but。

For the platforms that we're interested in， this will be the case。

And so we talked about this idea that there's a sort of correspondence between unsigned and signed numbers。

That's based on this kind of odd idea that when you convert from one to the other。

 you actually don't do anything， you keep the bits in their whatever pattern they are。

And you just change your interpretation of what those bits mean。So far these are four bit values。

As an unsign number， it can range from  zero to 15， but as a two's complement number。

 it can range from minus8 to positive7。And you'll notice that。For the positive case。

 the place where these two representations overlap。啊嗯。They match， but for the cases where they don't。

 what is a very large number， a relatively large number is an unsigned becomes a negative number as a signed number。

But anytime a program in C。啊。Cas or for some reason sort of switches between unsigned and signed representations。

 that's what it's doing is nothing it's just changing what numeric value is assigned to a particular bit pattern。

And that has its sort of strange and quirky behaviors to it。

And the other that I mentioned last time and is especially peculiar is。If you have an operation。

 say addition or less than， and one of the opera is assigned and the other is unsigned。

 the rule in C is， and this is the C standard is there'll be an implicit conversion of that sine value to an unsigned value。

 and then whatever operation should be performed is performed。

Last time we also talked about this idea of sign extension。

 which is to take a smaller bit pattern and make it larger。

 you do it by copying the most significant bit into the new positions and what we saw with that is。

For the case of this is for a。Tos compliment number， what it does is it gives you a。

Larger number of bits represents the exact same number。Similarly， if you want to shrink a number。

What happens is they just chop off the high order bits and whatever if it's a sign number。

 whatever used to be in this what's the new most significant bit position that becomes a signed bit and that may or may not be a good idea in terms of preserving numeric values obviously if you're going to shrink the number of bits some values will be unrepresentable and。

That's a consequence of this， but that's just the way it works。

So now let's go into arithmetic operations and we'll see the same general ideas apply that and usually it's a little more intuitive to understand the unsigned case than the sign case so the idea with unsigned addition is in principle。

 if you want to add two numbers each say of n bits that to fully represent the sum of those two numbers you might need n plus one bits and it's a little hard if you keep adding numbers to go get more bits and so what happens is we just chop it off and say whatever the extra bit was I'm going to ignore the so-called overflow bit。

Whether it was a zero or1， I'm not going to do it and the effect of that is sort of a modular arithmetic。

That。The addition sort of just wraps around and continues on。So， for example。

 this example shows if I add the numbers of decimal 223 to 213。If I had enough bits。

 I'd get the number 446。But I don't， I'm going to keep it at eight bits。

 and so I'm going to just chop off。That most significant bit and the result I'll get is 190。

What you might notice is exactly 256 smaller than 446。

 and that's the effect because you can think of。Here。That where。

Dropping up that bit there that we're dropping has weight or value 256。

 and so by eliminating that bit， what we're doing is decreasing the result by 256。And so actually。

 and this is part of the C guarantees that all edition will be performed as modular additions。

 so even when it overflows， the program has completely well specified behavior of what it's supposed to do。

So if I think of the possible range of values that these numbers could have along the x and y axes and then the sum of the values on the Z。

 then this sort of normal addition would give you，Plan， diagonal plane because well。

 it's sort of the definition of a linear function。But if I go to twos complement edition。

 I'm sorry to unsigned edition， what you see is it sort of splits into these two regions。

 each of which has a plane and the first the left hand part shows where it's。嗯。

Although I am going try this， Earl old Diad to day。This part here。

Shows where it's the true sum of the numbers， but over on the right here。嗯。

I don't know it's technology。Where it would have kept going up instead what I've done is I've chopped off that most significant bit。

 this is four bit addition here， so I've chopped off the value of 16 and now what's left is the original sum minus 16 and so that will climb up in this case。

Up as high as 14。So as the picture on the left shows。

 you can think of when you do the overflow then you're。啊。Shifting the sun。

Back down into the range of the original set of numbers。So for two complement in addition。

 part of the reason why it's the commonly used technique is the hardware is the same the actual。

Low level addition operation is exactly the same for it。

 we simply add the two numbers and throw away any extra bits that might overflow and call that result the sum。

And so as you and this is an important thing to understand is that。

Whether you say it's a sum of two ints or a sum of two unsigns。

 the actual bit level of behavior is the same。And again。

 you can see that here with the same set of bit patterns as before。

 but now since this is a two complement number that if you look on the right。

You'll see that these bit patterns represent the numbers minus 23 and minus 43。Repectively。

If you were to just add those numbers， you'd get。As just bits， you'd get 446。

 which doesn't seem to make much sense， but if you chop off that most significant bit。

 you'll see that what you have left is the bit pattern for minus 66。

 which is exactly what you'd expect。Turns out if you really want to do two compliment edition and add the extra bits。

 I should have sign， extended it to be a nine bit numbers and then done the addition and then it would have come back here so this is a little bit of a peculiar example。

But you see that the result is this idea that now the remaining eight bit number represents minus 66。

So again， you can think of what happens。Is。然我就觉。Let me jump to this picture no I'll jump。

 I'll go through this picture， so now there's actually two overflow cases。

What can happen is if you take two numbers and add them。And each of them is W bit。

Then if you look at the actual what I'll call the true sum。

 the sort of mathematical sum of those two numbers， you have three different cases。

One is that result is within the representable range of O W bit2s compent number。

 in which case that's the result you'll get， but if the number is too big。

 then it's called a positive overflow， and what we'll see is it will convert it into a negative result。

And then the other is if the number is too small， meaning too negative。

 then you'll have what's called a negative overflowrow。

 and the resulting number will end up having a positive value。

So we can visualize it using the same ideas before that this center region are the sort of non overflow cases。

 they're the ones where some of these two numbers was within the range I could represent。

As a four bit cheese compliment number。And the numbers that。

That sum would have been too negative or on the left， they'd become positive。

And the numbers that were too large， too positive on the right become negative numbers。

 so that shows those two cases。This is all， by the way， you know， if you look at the formulas。

 it all makes sense。And once you get used to this idea， it becomes very routine。

 but if it's the first time you've ever been confronted with this。

 it might be fairly non intuitivetu and the only way I can advise you is look at exact little examples of four bit numbers。

 try adding them together， see what you get。Compare that to the various formulas。

 check it out that you have to kind of let this stuff bake inside of you to really fully appreciate it。

So if I look sort of a bird's eye view from the top of that。This picture here。

You can see that there's sort of three regions。If I。For consideration， the white region here。

Is the case where the。嗯。There's no overflow so that the sum of the two numbers is representable within the range of the result。

And so that's the value I get and then the two pink ones are the overflow cases and you can see that。

First of all。呃。If you're adding numbers of opposite signs。

 you see you can never get an overflow because you'll take a negative number and a positive number and you'll end up somewhere in between。

 so it's guaranteed to be representable， so the danger is by adding two positive numbers that becomes too big。

Or two negative numbers that become too small。 Those are the two possible overflow cases。

 And as it shows， they should to represent these little triangularal regions。

And also as the formula shows here what you do。Have negative overflow。

Then it becomes a positive number and it has the effect of adding the value2 to the W to the sum。

 and similar if it's a positive overflow， it becomes a negative number that you can think of as subtracting2 to the W from that number。

So I think the only example here was one that didn't overflowrow。啊。🤧哼。

So if you wanted to do it at the bit level， you'd have to take some other examples。Okay。

 so that's addition。And I should mention， by the way， again。

 if we just go strictly by the C programming standards。

They don't guarantee that unsigned arithmetic is always modular。

 but they don't guarantee what happens if you overflow。

Either positive or negative with signed addition， so if you're really really strict and careful about how you do see programming。

 you should guard against any case like that。Again， in practice。

It's this choose complement representation， so there's a very predictable behavior of overflow or underflow overflow either positive or negative。

But it might not be what you want， but you can at least predict what it is。So multiplication is。

A little bit messier。Again， in this big pile of stuff。

 what it basically shows is if I have two numbers that are each W bits and I multiply them。

Then I should need twice as many bits if I want to safely represent the product and that result holds for both the unsigned case and for the tooth calculator sign case。

 and basically you can take the largest number you represent the square that and that will require two times w bits to represent。

嗯。But again， we don't have arbitrary， we can't just keep adding bits to our numbers in general to do this。

 and so what happens is we just truncate a result。So for example， with unsigned。

If you had two operas U and V and you multiply them。

 you might need twice the number of bits to represent the true product， the sort of mathematical。

Product of those two numbers， but we'll just drop off those upper bits and just leave the result within this W bit range and again。

 you can see that this is exactly an implementation of modular arithmetic。And。

Mdule arithmetic is something that's。Maybe not the standard multiplication。

 but it's one that people know and understand very well。So again， if I took my two numbers。

 226 and 213 and multiplied them。I'd get 47，499。Which is too big to represent the eight bits。

 so I just chop off those upper bits。And I get 221。

 which is the modD 256 product of these two numbers。Sign multiplication is a little bit trickier。

 actually， it turns out。嗯。It turns out that to actually when you do two complement multiplication。

 again， you should use your product will be twice at number of bits。And if you look at the bits。

 they'll actually be different。Then they were for the unshed case， so look at the example here。

You'll see that to multiply these two numbers。Two negative numbers。

 you get the positive result 989 and its bit level representation looks like so zero。

And if I go back and look at the same bit pattern being multiplied as an unsign number。

 you'll see a different bit pattern for these upper eight bits。On the other hand。

 if you look at the lower eight bits。1101 and 1101。You'll see that's the same。

For both the signed and the unsigned case， 1101- 1101。And so。

 and this is actually an important rule is that the。The lower part of the product。

 which is typically the only part that you keep。Is the same。

 whether it's a trees complement multiplication or an unsine multiplication。

The upper bits can differ， but it's relatively seldom that you actually want the full sort of twice the size of product of two numbers。

 so for example， a X86 through some special instructions you have to do to get that product。

 the normal multip instructions only gives you the lower 32 or 64 bits。

 and it takes a special instruction to get a full 64 bit product of 232 bit numbers or 128 bit product of two64 bit numbers。

And so。啊。So most of the time， then the fact that the lower parts of the bits are the same is good enough to say。

 okay， I'm going to use the same multi instruction for both cases。And。And we'll see with X86。

 actually have two different instructions for doing the larger version of multiplication when you need the full representation。

So。One of the things you'll see， one of the things we do in this course that's kind of unusual。

Is that we look at when you will write C code and then look at what a compiler spits out when it compiles that code。

And one of the realities that you have to deal with in doing that is looking at code that the compiler has done some optimizations that。

You have to learn what those optimizations really mean so an example of that is anytime in C。

 you have an expression that involves multiplying by a constant。

And especially if that con produce the power of two。Then it would actually。

 the compile would actually stick a multiply instruction in there or stick in a shift。

And the reason is that if you want to multiply by a power of two。

 you can do that by just shifting the number left， the appropriate number of bit positions。

 So if I want to multiply a number by two to the K。

But then all I have to do is shift that number left by K or positions and you remember the shift always has the effect of filling in on the right with the zeros and dropping off any bits that fall off the end so both of those cases even when it sort of overflows as a result。

 it's still preserving the same arithmetic behavior as a multiple instruction。

And you can think of it again if you think about how these numbers， remember if it's a。好。

We'll just think of unsigned for now。All when we shift that number up。

 what we're doing is each bit now has a weight that's two to the K greater than it would have。

If it had stayed in its original position。And so we're giving all these bits sort of an extra boost。

 and that has the effect of multiplying the whole number by two to a cap。And again。

 the rule says whether it's signed or unsigned， we can just drop those any bits that get shifted out and we'll get the same effect as if we've done the sort of regular bit level multiplication operation。

So for example， if we shift a number left by three， it's the same as multiplyier it by eight。

And you can put together various combinations of these。 Like if you shift a number left by 5。

 that's the same as multi by 32。And then you subtract off shifting that same number left by3。

 that's like multi y by 8， so since 32 minus8 is 24。

 that's the same effect as as multiplying the original number by 24 and you can see it can mix and match these because addition multiplication distributes over addition it has even in this sort of strange world of twos complement numbers and unsigned numbers and modular arithmetic。

It has that same set of arithmetic properties and so even if there's overflows or funny things that happen this。

This equality is still the exact same， and that's why the compiler can safely replace a multipplly by two shifts in an ad。

And be sure that no matter what the number is， it will have the same result。And it depends， actually。

 it depends on the hardware， whether that's a good idea or not is three edition two shifts in it。

Subtraction。Faster or slower than a multiplication that actually depends on how fast you multiply is and how fast it can perform the other instructions。

And in a， I think the processor you'll find today， it's about a。About a dead heat on those two。

They're pretty close to each other， and the compiler doesn't actually know much about your real hardware。

 it's just making it a guess， but it will typically do these kind of substitutions。Questions。

When you multiply and。Is that undefin。Yes， if it's well， if it's unsigned。

Unsigned arithmetic is guaranteed to be like modular arithmetic， both multiplication and addition。

Sign numbers。Right， just like addition， there's no。

The standard does not specify has to have a certain behavior。

I have to kind of keep reminding myself of this because I've gotten a bit sloppy at times so say，h。

 it's just too scled， I know how that works。嗯。So here's another trick that's kind of an interesting one。

And。If you like this kind of stuff。That actually is very useful too。

 is if you want to divide by a power of two， you can do that by shifting as well。

 and for the unsigned case， it's very straightforward if you want to divide by two of the K。

 you just shift the number right by K bits。And this can be pretty useful if you want to scale like you want to ask。

How many bys， how many？Given some number bitetes， how many？Double precision numbers。

 can I stick in there， you want to divide it by eight。Well。

 you just take that original number and shift it right by three positions and that gives you the answer。

So。In unsigned， we can do this using the。Logical shift， which he recall fills in with zeroes。And。

Again， the pseudo logic behind this is， as I mentioned， I think。On last lecture。

 we can't think of that。Of a bit level representation， even including fractional numbers。

But no longer do we have a decimal point， what we have is a binary point。

 and the numbers to the right of the binary point have fractional values， 1 half， 14， 18， 116。

So if we shift a number by k， it's like moving the first the least significant k bits to the right of the binary point。

 which now has fractional value and sums to something less than one。

So if I just now throw those bits away， what I'm doing is rounding that number down to the nearest integer。

 which is exactly what you want for division。😔，So just to illustrate that。With some examples。

 you see that if。I' take the number 152 13 if I were to divide that by two。

I'd get a fractional number， 7606。5， but I want to round toward zero in this case。

And so if I just drop off that 0。5， I'll get 7606， which is what I want。And similarly。

 if I take 15 to 13 and divide it by 16， I end up with a number that 950。8125。

Which I want around towards zero to 950 and so you can see that that shifting is discarding any extra bits。

Has the desired behavior of rounding towards zero。For two complement numbers。

 you almost get the same result by。Shifting using an arithmetic shift。

 and that's why the arithmetic shift is there。呃。The only problem is it doesn't quite do the right thing with negative numbers。

So let's see if I can give an example， so the idea is the same that we remember arithmetic shift we fill in with by copying the most significant bit over and over again。

嗯。So you can imagine for positive numbers， it's just the same as what we saw before for negative numbers you see that it doesn't quite do the right thing。

So for example， if I take minus 15 to 13 and I divide it by two。Again get minus 7606。5。Now。

 if I just throw away these。ItsHere。The problem is those bits had a positive value。

And so what I'm actually doing is decreasing this number or what they call round it toward minus infinity。

 I'm rounding it to a more negative number， which in this case was minus 7607。

And similar you see this minus 950。8125， gets rounded to minus 951 if I just do the shift。On its own。

 I don't do anything else。So it's not quite right。It's off by one， basically。

 for all these negative cases。I wander around to zero， so I wander around positive numbers down。

 negative numbers up。So the trick is， and what you'll see the compiler does is to basically take the case of a negative number and bias it by adding a little bit to it。

Before it performs a shift and that little bit that it adds will be just enough to kind of tip it and make it round in the right direction。

And the way it does that then is。By adding this bias of。嗯。Let'sSee if I can show it。

Let me just show in the picture。By adding the number that's actually two to the k minus1。

 which is the number that has all ones。For the these。Lowest K bits。

And what that has the effect of doing。Is。What I add at is I will。

If this original number is all zeros。Which is what's shown here。 And I add a bunch of ones to there。

 Nothing's going to happen。 I mean， it'll' end up with all ones。

 but this yellow part will stay the same as before。And when I shift that。And drop off。

Anything to the right the binary point？Then。呃。Then I'll get back just the original shift in number and you'll see I'm doing an arithmetic shift I'm filling it with once。

So for the case where no rounding is required， then it。

What this shows is this biasing has no real effect。

But for the case where I needed to do that little bit of rounding。

What happens is by adding this bias in here， if there are any one bits at all to the right of the binary point。

 what will become the binary point。😔，Then。Then this value will cause。

An increment value in the yellow course。嗯。And then when I shift that to the right。

What I'll get is effectively incrementing by one。This number which gets my bias right。

This is probably easiest understood by example。No， this is not an example。

This is best understood by example and I don't have one handy。

So this is a pretty quick march for the book covers this with some actual examples and I recommend you look at those。

But this is again， so it turns out that this is always a good idea for the compiler。

 if it can get away with a shift instead of divide。

 that's a big savings because divide is a relatively expensive operation even on a modern processor。

On the other hand， whereas I could mix and match these。

 I could divide multiply by 24 using two shifts in a subtraction。You see。

 it doesn't really work when you want to divide by something other than a power of two。

 you can't sort of break that up into a bunch of separate power of two cases。

So this is really only useful for the special case you're dividing by a power of two。

But you'll see this in in real life code。So just a few other tricks of the trade。

 one is when I took a course in logic design many years ago。

 I learned this trick for computing the negation of a number in two complement form they call complement plus increment。

So。Let'sSee if we've got examples。这样。So for example， if I want to complement the number 15，213。

Or increment negate it。 you see that's its binary representation。 So if I complement that。

 if I take all the bits and just bit by bit， put the opposite value in， that's complementing it。

 And you see numerically， that represents the value。

Minus 15214 and the intuition of why that's true is if you add X and its complement。

You'll get a number that's all ones。Which of course you recall is the representation of negative one。

 and so we can see that the number x plus。Complement is。

Is minus1 and therefore if I now add a one back to this complemented number， I'll get minus S。

So if I now increment that。In this case， it was an even number， so I do said that bit to。One。

 then this will be the value of minus 1523。So that's a pretty handy trick。 and again， all of these。

It really。You there's not some magic new knowledge here。

 it's they all stem back to that original formula showing what the numeric value is of a choose complement number。

And so some special cases like for zero， if I compliment it。I'll get all once。Which is minus1。

 so if I add back a1 to that， I'll come back to zero。

And one of the interesting numbers is if I compliment it。Is T men， if I compliment it。

 I should get T Max。And if I add one to T Maxax， what do I get？I get team in back。

 so I took the most。Positive number and I added one to it and I got the most igant number。

 that's what they call positive overflow。And so what you can see is actually。

If you give compute the expression minus x and x is T min， you'll get back T min。

Just like if you minus zero is zero， minus team min is team min two's complement in the world of two's complement。

Which， by the way， whenever any question comes up， is this behavior always true or false？

Usually you want to test the special cases of zero and team in to see because they're often the counterexample to any general rules。

So just to summarize that part then。Actually， what I'm going to summarize it。

 but we're about to do our quiz and so if you want to start working your way into Canvas，多一下。

Because I know it takes some time with all your。Oeneation。Yeah。嗯。自己。

I'm trying to figure out how to get to Canvas。で際？啊。Are you guys checking this quiz。

 you're probably ahead of me out I can' a stupid。Yeah。Yeah。错。Books。然后。はす。のしよ。Okay。

 let's see how we've done， sorry， it took me so long。Okay。

 so I'd say people generally did pretty well here， so actually the answer to the first problem was already stated in lecture。

When you have two numbers with opposite signs， it can never overflow。 Remember， I said if it's a。

Positive number and a negative number， you're adding them together。

 you'll end up somewhere in between most people got that。

Everyone basically got the idea that shifting left by four is the same as multiplying by 16。

Remember it's a left shift， not a right shift。And how many values does C have for faults。

 it's sort of a trick question in that。呃。Remember， fault has one value， which is zero。

 true is anything that's non zero。This one actually was。I can see that people。

Didn't necessarily guess the answer on this。And so we'll actually cover that in just a second。

But this is good， I think this is very useful information。

So I think a lot of people recalled from last time this example of a loop with a。

An unsigned loop index I。And the problem with this is that if I is。Since I at least strictly this。



![](img/0717e64d682481aa772c7c19ba3aa315_1.png)

![](img/0717e64d682481aa772c7c19ba3aa315_2.png)

Since I is unsigned， it will always be greater than or equal to zero。

And so this group test is useless。And it can be a little more subtle， as people saw。

 if deelta is size of int， Dlta is defined to be。An unsigned number， and so by the rules we had。

This would be。Cas to unsigned and therefore always be greater or equal to zero。

So the particular quiz problem。See if this works。What it was doing is。Instead of using a size of int。

 it had a particular。Yeah。Heex number， I think it was4，8， right？Ford， okay。I'm going to try this。

It's the way I can change this。I'm just going to do this。And so I think some of you said， whoa。

 hex numbers， that looks kind of unsigned to me， and so you guessed that that would also be an unsigned number。

Which is not a bad guess， but it's wrong。In this case， since four。

 there's actually a pretty complicated set of rules that when you write some digits out。

What data type does that imply？And in fact， if you really want to get into this， there's a web aside。

For the book。That you can get to off of the book's web page that says， how do I write team Min？

And it goes through the whole conversion rules， which are really in arc can。

 and it actually depends on which version of C you use。So this could be a very complicated。Answer。

 but the simple version is。If the number can be represented as an int。

And there's no little U next to it， it will be treated as an int。

 and so hex4 is the same as decimal4 in this case， it will be an a sign number and so since I in this example the example is very similar to this one。

Will be。嗯。All this will be done using sign arithmetic so the people got that wrong it wasn't like a fundamental misunderstanding。

 it's just there's this one kind of corner of the C rules that we didn't even cover and aren't often covered in any standard presentation。

Good。😊，So I used to counsel people， I'd say， well， if you're going to count down then don't use unsigned arithmetic because it will get you in trouble and there's a fellow that I don't think he's there anymore but used to work at the Software Engineering Institute who sent me email saying。

 by the way， you gave really bad advice so this guy named Robert Seaort has written a set of books about what he calls secure coding。

And if you really want to be a super careful programmer。

 it's a pretty interesting collection of books， he has it in C， C++。

His ones in Java and so forth and he's especially he's a computer security person and so he's trying to say。

 how can you write code that on any compiler， on any system is less prone to being attacked or vulnerable have bug。

And so what he claims is that。The best way to do counting down then is to use a unsigned value as your loop index。

 but then rather than checking is it greater than or equal to zero。

 you actually check is it less than your starting value？Because the logic behind that。

 you keep going until that happens， because what happens is once I goes。To zero。

Then the next thing it will become is it will wrap around and become U Max because it's unsigned arithmetic is guaranteed to be modular on any machine on any compiler。

 So you're guaranteed once it goes below 0 or。Apparently belowsier。

 what it's really going to go is up to a really big number。

And so that's a very non intuitive looking。嗯。Loop writing scheme is to put instead of greater than or equal to zero you say less than count and I've started using this in my own programming and once you kind of get used to it。

 it looks reasonable， but at first it seemed like a very strange thing and he even recommends instead of decing it as an unsign that you declared it as this data type size T。

 which is depending on the machine pattern it's always sort of a big enough number to handle the。

The full word size of your machine， 32 or 64 bits。So that's。

Just one piece of advice I'll pass along to you from Richard Robert Seort。So other uses of unsigned。

As I mentioned， if you really， really want to be careful。

 the good news about Uninign is it does have a complete specification of what to do even in overflow cases。

And often module arithmetic is actually fairly useful if you want to do multipre arithmetic。

You saw when you were doing set operations， it's sort of natural just to think of the bits as bit flags and no sort of negative numbers involved。

And you'll find in systems programming， when you talk about addresses or masks， you know。

 collections of bits and things， unsigned is a fairly sort of。A reasonable thing too。Conceptually。

 so。It's interesting like Java does not have unsigned numbers， but it has。

Because they didn't want to get into all these quirks。But in C。

 unsigned numbers are kind of built in and they're very useful。Okay， just to finish it up then。

 let's talk about how we can lay out collections of bytes in memory。

AndWhen we look at the actual machine code， assembly code。

 you'll see that it's issuing all these addresses。啊。People ask well。

 where's the memory and the answer is， well conceptually the memory just exists。

 it's called virtual memory， and it's just you can think of it conceptually as just a big array of bitetes。

From over a wide range of addresses。Physically， what happens is the combination of hardware and operating system software makes that virtual memory real by using some combination of caches of actual DRA on typical machine or in even on the disks or solid state drives that。

Built into your machine and moving over the network potentially。

So sort of provide you that memory and swapping it in and trying to make it look like it's all really there。

 even if it isn't。So anyways， but from a machine level programming we don't think about all that memory hierarchy。

 we just think of it as in terms of virtual memory。

 so you can just think of it as a big array of guidance。And in fact。

 when you're running multiple programs on the same machine。

 they each have their own separate collection range of virtual addresses。

 and what that means is if you're running multiple programs，An action by one won't directly affect。

The behavior of another and that's a good thing because if one program misbehaves， it's got a bug。

 it can't make the rest of the programs crash by just doing a right to some memory location。

So that's sometimes referred to as a process when you have the process the execution of a program on a machine。

 and you can have one program that's，That of which there's multiple processes running that same program。

So each process and each executing program has its own virtual address space。

And you'll often hear people talk about word size， as I mentioned in the first class。

 there's no real solid definition of what a word is on a machine We talk about 32 bit machines and 64 bit machines。

But most machines。That your laptops， your phones and。

Most desktop machines nowadays are actually can run code either compiled for 32 bit execution or for 64 bit execution。

 so it's really a combination of the hardware and the compiled。Code that defines what word size is。

But in general， for a machine to sort of。Broadest concept of a word is how big are the addresses in that machine so and as I mentioned。

 that can actually depend on the mode program the machine is executing。

 so a 32 B machine means that its largest addresses to the 31 is 32 minus-1。

 and that's roughly 4 gigabytes。The machines that even phones nowadays are mostly running 64 bit processors and what that means is in principle。

 an address can be as many 64 bits， and that would give you an address range of something bigger like 10 to the 19th bytes。

 which is a lot of bytes， by the way。An exabte。 So you think of the biggest disk drive you can buy nowadays is。

I don't know， eight terabytes or maybe bigger。But that's still。

1 thousand0 times smaller than a addressable range。 So to really support a full 64 B memory space。

 youd need a machine with， say，1000 disk drives， just to even have that many bits of memory somewhere。

So what happens is on the machines that they actually built today， the hardware。

 it's not only 64 bit addresses， but they only let you use the first 48 of those。

So they don't really support true 64 bit execution。Anyways。

 the point being that depending on how big your words are。

 that defines how many bytes of memory you can address。

And the general rule then is if I have a multibyte quantity， what's its address。

 what's defined to be the lowest numbered byte in its collection of。so we'll represent a。

A 32 bit quantity is four bytes， and the address of that 32 bit quantity will be the least significant or not the least significant。

 the byte with the lowest number it address。And similar way for other sense。

And as I mentioned last or some previous lecture， we've seen this slide before that depending on whether you're executing a 32 bit program or a 64 bit program。

 some of the data types will change， and particularly a pointer an address will change between being a four byte quantity or an eight byte quantity。

So there's one thing that's left here。Is if I have multiple bitetes。Representing a value。

What order should they be in relative to the addresses and there's two obvious conventions one is。

You put them in from least significant to both， and the other is from most to least。

 And as you can imagine， in any case where there's。A choice。

Where then some people choose one way and some people choose the other。

And so that's sometimes referred to as the byte ordering。

And it's commonly called big Indian versus w Indian bite ordering。

 and that's a term that goes back to。The book go over his travels。

Even though that was written long before there were bytes store in a computer。

And there's a fellow who wrote a kind of amusing tale about how people were fighting about this bite ordering。

 the way the characters in this book had fought over which end of an egg should you open。Anyways。

 nowadays it turns out that you're going to live in a little Indian world if it's an X86 hardware and that remember that applies to Windows。

 OSX and to。呃。Linuxux。It's going to be little India， an arm processor。

Like as in most of your phones can actually run the hardware can run with either byte ordering。

 but when you're running any of the common operating systems， it will be little Indian ordering。

 so little Indian means that the least significant bytes come first。

And there's a few machines that you're less likely to encounter that。Our big Indian。

 but one of the annoying things， some reason when they're designing the internet protocols。

 they said。Whoever was in charge said， I want big Indian and they did it。

So when you send packets over the internet， what has to happen and you'll see that when you write this code。

 you have to use special functions to convert the byte ordering going out to the network and coming back in。

So what do I mean by this， So again， assume we had a value that we wrote in Hex a。One， two， three。

 four byte value。Which we'd write when we write it of course。Like up above。

 we put the most significant bite on the left and the really significant bite on the right。

But now when we go that into memory， we'll see that in big in in order。

 if we read from left to right， it looks the same。Because the least significant bite is at the highest address。

 the most significant is it the lowest address。But if we write it in little Indiay in ordering。

 it appears to be reversed。I mean， remember these conventions of how you read things list things left to right is just a convention。

 it's not really。The point being the address， the lowest numbered address has either the。

Most significant bite or the least significant bite。

But we'll find in the real world since we're going to live in a little Indian world most of the time。

That we're often looking at things written backwards with the bite ordering reversed。

So there used to be machines actually on campus made by a company called Sun Microsystems。

Which was later acquired by Oracle， and they're still making these machines。They're not very common。

 at least sort of。Outside of the world of database machines。But。

So I could actually run these experiments and see。verify what order you'd get when you enlisted various numbers in a single by order。

If 15213 has a he representation 3B60。On an X8 6 machine， you'll see the we significant byte is 6D。

 and then the next one is 3B and then it's two zeros。

 and on one of the sun machines you'd see it reversed order。

And on a 64 bit machine would be an little Indian machine but an eight byte。For a long。

And you can actually write code and this code actually included in the。

Code for today's lecture that lets you sort of print out the byte representation of different data types。

By just sort of walking through them one bite at a time and printing out each bitete value。And。

You can run it on various different things。Get numbers like this is 15213 printed on a Linux machine。

And you'll see it's a little Indian machine Unfortunately I don't know any machines on campus that at least I have the count on that it's a big Indian machine there might be somewhere in the accountinging department but not otherwise。

 and I don't think even there。And another point that this slide makes is pointers are simply。

Addresses， they're just， you can think of it as an index into this array of virtual memory。

But where they're located， where a particular address is located depends on the machine。

 the operating system， the compiler， a bunch of different things。

 and so from one machine one execution to another，Pointers might change values。

 if they don't have any sort of uniform representation。And then another important part is strings。

At least in C are always represented by just a sequence of。

Single byte values in the socalled ASI format where the final byte then is a zero and that's completely independent of byte ordering because it's on a byte by byte basis so in fact when you're writing software that has to be compatible across machines。

 it's one thing people often do。Is。Instead of encoding numbers in binary and worrying about bite ordering。

 they encode them。As。You know， nuummerics as strings， send the string and convert back to。

A numeric representation。So for example， one of the things you'll start doing in the next wave is look staring at a lot of。

Of disassembled code。It's it's really machine code written in a somewhat human readable format and you'll see in a。

On X86 machine that all the numbers are written。Apparently backwards and it's annoying because it's not really backwards。

It's sort of a backward sign of with pairs of text digits， so 12 AB becomes AV12。Okay。

 let's just finish up with a not online quiz。With just some questions and again， these are。

 first of all， really great exam problems， but also good ways to kind of make you think through the implications of some of these ideas。

And I'm glad of this we we've sort of looked at in various forms。

So the answer to these is either yes， it's true or no， theres at least one case。

 one value of x for which this is not true。In the latter case。

 it's good to be able to give an example。So if x is less than zero is2 x less than zero。No。

 not x squared is x times 2。好。And by the way， as I mentioned。

 team men is always a good counter example generator， yes。呃。Yes。

 so if it depends then the answer is no。That' trueRight。And can you give me an example， let's go。

That's a great example， right？😊，Cause T men， if it's 1，0，0，0。Remember。

 multiplying by two is the same as shifting at left。And so I'm just going to。Throw away that one。And。

You have to do my handwriting recognition that he said， but it became zero， so yes， you're right。

How about an unsigned number， UX？Is and assume these sort of arbitrary numbers。

 is it always greater to equal to zero？Yeah， sun。Okay， this is getting more obscure if I。

 and this is a 32 bit number assume。So if I。Take the and of x and7 and I see that it's  seven。

 and then I shift that number left by 30， is it going to be negative？Go what？So。What this means。

You remember seven as bit representation？なんですね。So。Seven looks like one， one， one， right？So x and7。

 if I get seven out of that， it means all the low three bits of x are one。

And so if I shift it left by 30。I'm guaranteed that。

These two bits will become the most significant bits of that shifted result， right？And so this bit。

In particular。Is a one and so the result will be negative， so the answer to that is yes。

The reason why it involves。very specific parts of that question。Right。Is U x greater than -1？嗯。😊。

So the answer is no， but it's not for the obvious reason， right？

So what's a counter examplele to this？So what first of all。

 what will be anything that is not the right answer， that's the non intuitive part。TMax won't work。

But you're getting closer。You will remember UX is an unsign number。So what is。First of all。

 when I do this comparison， you remember from the last lecture what will。

What will be the comparison type will be a signed comparison or an answer？Unsign。

 very good I to say that when you're preparing an unsign。

Bness to an un signign and negative one is just。1，0，0，0，0。Yeah， well， no， native one is all ones。

AndNative one is all ones， which becomes U Max。And so。

This is almost never this is actually never true for any value that's UX。

But that's the thing to remember is。Oh， an unsigned to sign， convert them both to unsigned。

If x is greater than y is minus x less than minus y。What would be an example？Of where this is wrong。

It's actually almost true， so you have to think of the sort of less the common case where it's wrong。

And what did I say about good counter examplesamples， yes？Yes， when why is T men very good。

Because when y is T min， then minus y will also be T min。Right and no number is less than that。

 so anything where wise is T men will false， very good。Is x squared always greater or equal to zero。

 actually I showed that in the first lecture， no 40，000 squared is not greater or equal to zero。

In general， you can have overflow。If x and y are both positive， will x plus y be positive？No， right。

 overflow case。Ifff X is。Greatter equal to 0 will minus x be less than or equal to0。Actually。

 this one's true， right？But if x is less than or equal to0， will minus x be greater or equal to0？

You guys are catching on。Just use your friend teamman and you'll keep going here， right？If I。

This is really obscure。If I look at x and minus x and I or those together and shift it right by 31。

 will that equal minus1， this is arithmetic shift。What works for GMM？嗯。

This actually almost works Can you give me one example where it doesn't work zero yes？

This might be a useful hint in one of your puzzles coming up。

Is shifting an unsigned number right by three， the same as dividing it by eight。Yeah， right。

 It's unsigned， remember。That was the point unsigned， you can just shift it。For a number。Well。

 I think the shaking heads from before were for this one， no。

 because it might round the wrong direction。Okay， so that's。

And the other one is sort of obscure So anyways， very good。

 I think you're catching on this quite well we'll see you next time。Yeah。そ定は？



![](img/0717e64d682481aa772c7c19ba3aa315_4.png)