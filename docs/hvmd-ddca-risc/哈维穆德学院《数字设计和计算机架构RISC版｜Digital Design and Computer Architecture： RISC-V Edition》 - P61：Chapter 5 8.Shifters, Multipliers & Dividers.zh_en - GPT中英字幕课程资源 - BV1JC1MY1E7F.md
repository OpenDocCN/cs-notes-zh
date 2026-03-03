# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P61：Chapter 5 8.Shifters, Multipliers & Dividers.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/538f172a673e7f161c4c9d9a784ac07b_0.png)

Let's talk about shifters， multipliers and dividers Shiers come in two forms。

 either logical shift or arithmetic shift。So logical shifters shift values to the left or right and they fill the empty spaces with zeros so for example here is a logical shift right by two bits so we start with this number and we shift off these bits to the right so that bit shifts thatll be a one bit right shift but we also want to shift off the second bit so we're shifting by two bits。

😊，And what shifts in on the left。Or zeros。And so we get zero zero， these two zeros。

 so that got shifted in， these two bits got shifted off to the right。And we get 0，0，1，1，0。

Logical left shift is similar。But we're shifting to the left by in this case。

 the same number of bits。 And so we shift off one，2 Bs to the left。And we shift in。

Zeroes on the right， because we're doing a logical。Left shift。Logical left or right shift。

 so we get001， these twobits got shifted off。And we get zero， two zeros shifted in。On the right。Okay。

 so left shift， we shift off bits on the left side。 And for logical shifters。

 we shift in zeros into the empty spaces。Arithmetic shifters differ only in right shifts。

 so in right shifts。😊，Instead of shifting in just zeros。

We're going to shift in whatever the most significant bit is。So in this case。

 the most significant bit is one， so a lot our arithmetic right shift by  two bits willll still shift off our two bits off to the right instead of shifting in zeros。

 we're going to shift in。😊，Ones， we're going to get 1，1，1，1，0。 So now we shift in。

Ones or whatever the most significant bit is， not always ones， right。

 if the most significant bit were zero， we'd also shift in zeros。So in this case。

 the most significant bit is one， we shift in ones。And in logical right shift。

 no matter what that doesn't look at the sign bit， what doesn't look at that most significant bit。

 just shifts in zeros。Either way。Okay， for left shifts， well。

 left shifts don't differ from these are the same。Logical and arithmetic left shifts are the same we shift off。

Are 2 bits。Off of the left。And we shift in zeros on the right。So we got 0，0，1，0，0。 and you can see。

These are the same。So logical and arithmetic left shift is the same， but right shift。May differ。

We differ in the method in arithmetic right shift， we're going to shift in the sign bit。

In logical right shift， we always shift in zeros。Okay。

 so we have to look at what that sign or that most significant bit is。

To know what we're going to shift in。Rotators are similar to shifters。

 but instead of just dropping the bits off to the edge， we rotate them around。

 So this is a rotate right shift。 R O R rotate right。 We're going to rotate right by 2 Bs as this。

But this one falls off and shifts to the right， actually rotates and comes back around to the front。

And so we get that one here。And then。At0。Rotates around next instead of just falling off。

 it rotates around to the front。 So we get 0，1。 they're no longer on the end。

 they've rotated around to the front，0，1，1，1，0。And left shift is similar。A rotate left is similar。

 these are this one is going to rotate around。So just falling off the left， it rotates。

And then land on the right。And then this one rotates。And lands on the right。And so we get。

They're no longer on the left here， they've rotated around to the right， we get 00111。

We've done another instead of rotate， write two bits， if we'd rotate right three bits。

Then would' get this zero。Not just falling off the left， but then rotating。

Around and coming to the right， that would be rotate left。By three bits， I'm going to go0，1，1，1，0。

 fall off the left。And land rotate around to the right。

So let's talk about how we design these shifters。So well。

 we let's take an example of a four bit shifter，4 bit。 we'll start with a left shifter。

 remember that arithmetic and logical left shift is the same。

 so it's called a left shifter shift left and we'll start with a four bit number， the input is a3 A2。

 A1， a0， so a4 bit input and we'll have four bit output。Well。

 what how how much could we shift this by Well， we could not shift it at all， So 0 bits。

 we're could shift it by 1 B，2 Bs or 3 bits。Right， okay， at that point， we just， if we shifted by 4。

 now we get to 0。 So that would be silly。 Okay， well， this。

 this looks like a good place for a multiplexer。😊，So。Let's see what happens。

 So we have a select line， we want to make it have four options， so we need two bits。

We'll put a shift amount signal。Shift amount， S H AMT signal to select how much we're shifting by。

 So if we shift by 0。Bits， well， we feed A N this 4 B signal and。We just get。二。Going to Y。

 and that's what we want， right we want no shift of FA。Okay， well。

 what happens if we wanted to shift left by  one bit？Well， let's see， so we have。Ourre。

Input A3828180， this A3 would shift off。That would shift left and then I'm going get it to zero here。

Okay， so we can take our。A input and we could even， you know。Write at something like this。

 And we want a2。To0。And a0。On that right most bit。Okay， what about if we shifted by two bits？

Well now both of these bits would shift off and we'll at two zeros on the right。

So if we were shifting by two bits， would' want。诶。1 to0。And 2 bits of0。On the right。

And what about our last option？Is3 bits， well then。

All three of the most significant bits shift off to the left， and we get three zeros on the right。

 and so we' get。嗯。So0。And now3 bits of0。On the left。Okay。

 so shifter not to be confused with shift register， which we'll talk about later。

 Shiters are purely combinational。 right， We tell how much we want to shift it by。

Using the shift amount and then so say we want to shift by three bits to the left。

Then we select that input and feed that to our output y。

And so we can think about the same thing for a logical right shift， similar idea。

 and arithmetic right shift。😊，So here I've drawn it out with the different bits， A3， A2， A1， a0。

And so you can see， for example， that Y3。Is if we if we shift by zero bits this top。

Input is the zero input for our multiplexer。 if our shift amount is 00， we just get a3， A2。

 A1 and A0， we don't shift a at all。We send it to our output Y。But if we shift by。One bit。

Now instead of a3， everything gets shifted。Right shift the left by one bit。 so we get a2。A one。A0。

And then we get to zero。On but zero of y。And so forth right so we've just shown it with the bits here delineated。

And so when we shift by three bits， for example， now the only bit we have left， we shifted left by。

 you know， a3。2， a1， a0。 All of these bits got shifted off to the left。

And we have a zero followed by。I have3 zeros。And so we get a0。Followed by0，0，0。

Logical shift right is is very similar， but now what's getting right， we have a3。8，2。A1， a0。

 so as we shift right。Bits are falling off to the right， and we're getting zeros。

 So we'll see the only case where we don't get zero on that top bit of y is in when there's no shift right when shift amount is 0。

 otherwise。Those zeros are shifting in。Onto the left。So here in all those cases。

 either shift right by one， two or three bits where're get zeros in that most significant bit。

And so forth， right， only that bottom bit gets。You know。First is a。A zero。

And then once it shifts right by1， get a1。And then by two， A2， and by three， we get A3。

So the difference between arithmetic and logical shift is instead of shifting in zeros onto to the left。

 we're going to shift in the most significant bit， so instead of shifting in these zeros。😊。

Those are tied to ACid 3， the most significant bit of the input。8 bit 3。And same thing。

For these ones。And same thing for。All of these options here。

So we can use shifters as multipliers and dividers。 So just like in in decimal。

 if we shift a value less， let's say we have some number 53 and we shift it left by two digits。😊。

We're going to get 53，0，0。And that's the same as multiplying 53 times the base 10 to the number of。

Digits that we shifted it。 So in this case，53 times 100。Yep， that's what it gives us。

And so it's the same in binary if we shift a number left by n bits， binary digits。

 it's the same as multiplying。The number by two the base to the n power。So let's take an example。

 let's suppose we have some number。Three or something。And we shift it left by two bits。

She's still left by two bits。So。These two bits are going to fall off。

And zeros are going to come in from the right。And so we get0，0。0，0，1，1，0，0。

 So we expect this to be while our original number was three shifted left by two。

Should be three times two to the two。This is the number of bits we shifted。

So three times four should be 12。Check。That's what we got。And here's another example。

 Suppose we have the value 1。 We shift it left by 3 Bs。

 We expect the result to be the original number a。1 times 2 to the。

Number of bits that we shifted it three。And in fact， that's true。 right， We shift that。One。

 left by three bits， those fall off。We put zeros in the front， and we get eight。

And this works for positive and negative numbers。 So let's suppose we started with minus-3。

And we shift it left by two。 We expect that to be minus three times2 to the two minus three times4。

We get minus-12。Shift this left by two， those fall off， put zeros。On the right， we get 10100。

 and in fact this is minus 12， we could take the cheese complement to make sure the magnitude is 2。

 you know what's negative。And so inroid the bits。Add one。Y， the magnitude is 12 and it was negative。

 so in fact， we get our minus 12。Right shift is is the opposite right when we right shift and specifically use arithmetic right shift。

 that's a symbol for arithmetic right shift by end bits。 It's the same as dividing by T to the N。

 And we can do our decimal analogy again， let's say we had some number。😊，37，000 or something。

And we shift it right by three digits。That would be the same。

 So let's see we shift it right by three digits。 those three fall off and we get。37，000 becomes 37。

that's the same as the original number of 37，000。Divided by the base10 to the number of digits we we shifted。

 we shifted right。 So divided by 10 to the3。 So 37000 divided by 1000。 yep， that's 37。

So the same principle here。Let's suppose we start with some number in this case， eight。

We it right by we arithmetic right shift it by one。In case， it， you know。

Arithmetic or logical shift would have been the same， but it's important for sign numbers。

So arithmetic right shift by one bit， we expect it to divide eight by two to the one。And in fact。

 we shift this right by one bit。 Arithmetic right shift this。By one bit。

 we take this sign bit and that's what gets shifted in and we get 0，0，1，0，0。In fact， we get four。

Eight divided by the number of bits divided by two to the number of bits that we shifted。

 arithmetic right shifted。We get8 divided by two is in fact four。

And this can work for our negative numbers two， so here we have -16。

 we want to arithmetic write shift it by two bits so these two fall off and remember we shift in the most significant bit or the sign bit。

So we shift into ones up here and we get 11，1，0，0。And in fact， that is minus four。So get 16 minus-16。

arithmetic right shift by 2 is the same as dividing it by two to the。

Whatever number of bits we've right shifted by to the two。So the minus 16 divided by  two， the two。

 yep， we get minus4， check。And so shifters are it turns out a lot cheaper than kind of general purpose multipliers。

 so if we can ever get away with doing multiplication or division as a shifter instead of using a multiplier divider。

It's going to be a lot cheaper， less hardware， lower power， et cetera。

 So it's a simple way of doing multiplication division by powers of two。

So let's talk about multipliers and dividers and see how to build them。So multiplplayers， you know。

 we've done multiplication long hand in in decimal before。 And it's， you know。

 similar process in binary， but actually a little bit simpler。 We're going to perform。

Our multiplication by。Creating these partial products。And then adding them together。 So， right。

 we two times。This entire multican。So two times zero， zero， two times three， six， two times two。

 four。And then we're going to shift over because right we want to be actually in one place over because this four has is in the1 place。

 not the one's place， and we do four times zero， write four times this entire multican again。

Four times zero，0， four times  three， 12， carry the one， four times2，8 plus one， nine。

And then we add them together。We add those partial products。

 partial products together and we get the result。😊，Okay， so in binary。

 it's going to be the same except。A little bit easier in that， while multiplying。The multiplier。

By the multiplcan， well， these bits down here。I'm still going to multiply that one times that entire multican。

 or if there's a zero， it's most significant but as a zero。It's going to just be all zeros。

So it's either my partial product will either be the multiplecan。If the multiplier bit is one。

Or all zeros。 if the multiplier bit is 0。And so these partial products we can see are the multil canned。

Multiple can。The multiple can。And then finally。Zeroes。So it's easier in that way in that。

And that the multiplication is easy， it's basically an and gate。

Of the multican with the multiplier bit。That bet is 0。We want it to be zero， but if it's one。

 we want it to be whatever the multican is。And then we add those partial products together。And。

Get the result。 in this case， we have five times 7， and we get 35， which is in fact what we get 32。

Plus 3。So how do we build this well？We build it by looking at how we perform those or calculated those partial products。

So here's a 4 by four multiplier。 We have four bit opera brands， and we could get up to。

8 bits as the product as the result。And so when we do， unlike addition， if we have four bit operas。

 we get four bit result with a multiplier， four bit opera gives us eight bit results， 16 bit operas。

 we get 32 bit。Result。And so we can see。Like I said before in words。

These partial products are going to be。Multipliier。Ended with。Eat bed。Of。The multican。So B0 and a0。

 B0 and A1， B0 and A2， B0 and A3。AndNow we should move over a spot。

And then we get B1 and all of those bits。B1， and A0， B1 and A1， B1 and A2， B1 and A3。And same thing。

 B2 and。All of those multicanned bits。And finally， B3。And all of those multiple ca bits。

 and then we add them together to get those the final product。Okay。

 and so we can see here on our circuit。We have these adders here to start with and the carrys have zero。

And we perform。A0。And what we start with。B0 ended with all the。All of the multiple ca， the A bits。

B 0 and A0， B0 and A1。嗯。And then we add that to B1。Maybe we're going this one we just。

Goes directly down to。Product bit0。 and then we're going to add these two together。

And that's performed here。And then， we're going to add。These three together。Right， one， two。

 added to the third one。And so forth and so。What we notice about this is this circuit， well。

 it's a four bit4 by four multiplier。It's quite a bit of logic。 A bunch of adders。

And some a gates to perform that multiplication， so multiplication is actually pretty expensive and some very simple processors。

 microprocessors don't have that multiplier or divider because of the expense of the hardware。😊。

And so instead of having that hardware， that multiplication or that division will be done in software。

So let's talk about dividers。 And here's an example of one that we've done， you know。

 the small division，25，84 divided by 15 ends up being 172 remainder 4。 So we have our。

our operas that we're going to operate on a divided by B， and we're at quotient。Plus， our remainder。

Divided by B。And so here's the long hand， which you know we've all done before， 15 goes into 25。

 well， if it's in there once。Subtract。15， and we get that。What's left is 10。

 bring down the next digit。And we have 108， how many times does 15 fit in there， fits seven times。

7 times 15 is 105。So subtract 105。We get a three。Bring down our last digit， 34。

 how many times does 15 fit into that2？Two times 15 is 30。We subtract that and we get four。

And that's our remainder。So we have 172。Remainder of four。

And so I'm going to show a slightly different way of doing this because this is how we're going to do it in hardware when we do binary division。

 And so we could think of this。 we're trying to see。

Wwhichhich of these numbers you know you're shifting it in basically from the right。

 we're doing a left shift and seeing which at what point does that number fit into or does 15 fit into it？

And so we start with two， we try to see well， this 15 go into two no。

 in our heads we skip that part because you know we obviously know 15 doesn't go into two。

 but we didn't go to 258 we stopped when we got to 25 because we said， oh yeah。

 15 does fit into 25 so。But generally， we'll start with that most significant digit and say， okay。

 does that fit Nope2 minus15 is negative， it doesn't fit in there so shift it again shift that。

That number to the left again。And so we get 25 now。And we say， does that fit 25 minus 15， yep。

 it fit。And so we can see that。That it fit and it fit once。Into there。 And so now we say， okay， well。

 great， this is what we had left over， 25 minus-15 is the 10。 So now instead of using this 25。

 we say we're going to use whatever is left here。😊，As the amount that we're going to now shift over。

And bring down the next digit。We're going to say， well。

 how many times does 15 fit into that fits in seven times？And now we see three again。

 instead of the 105 because this is positive and not negative， it did fit。

We're going to bring that three。And that's what we shift over。And bring in our last digit for。Okay。

 so another way to think about it， because that's what we're going to do in our binary。😊。

So we're going to perform division binary division in a similar way。

 So this is unsigned binary division。 So we have our a here is 13 divided by 2。We expect to get six。

Remainder one， six times two is 12， and then we have a remainder of one。Okay。

 so let's take a look at that。 So we have our。A here。A3， A 2， A 1， a0。

 And the first thing we're do is going to take that most significant bit of a。And bring it in。

 Shi it in from the right。 So we have A 3。 And we're going to see if our B。

Our divider fits into that。So we perform one minus two and it doesn't right it's negative。So we say。

 okay， well。So with a negative result， that means that two didn't fit into that。

And that means we put a zero into that quotient bit。Okay， so that's fine。 So we take a3， this value。

 this entire thing， we shift it left by one bit， so A3 is still here now。And we take our next bit。

Ace of2 and shift it in。On the right。And now we check again and we say， hey。

 does our divider fit into that， So 3 minus-2。Yes， it does。 So it's positive。 Now。

 the result is positive。3-2 is1。 And so because it's positive。

 we put a one in our quotient bit there and say， yeah， that fit。 it fit。

 That's one nice thing that binary is gonna to fit or not。 It's not gonna be a multiple of it。

 So it's gonna either be a one。 It fits or it's negative result and or it's a 0 doesn't fit。😊，Okay。

 so that fit three minus two is1， and we take this value our one。And that's that remainder。

Is what we're going to shift？Now， left。And then bring down the next。

Most significant bit are a sub one。And do that least significant bit。Okay， and now we say， okay。😊。

Let's see does two fit into two， Y 2 minus2 is positive。We got a positive result。 to minus2 is0。

 right zero is。Consider a positive。 So 2 minus-2 is0 and so。That's positive， it's not negative。

And so we get a one。In the next most significant bit of the quotient。And then。We take that result。

 Well， it's all zero。 So almost like you can't see it。

 but shift that left by 1 bit and finally bring in。2。Last。Bit of our。系啊。Or of a。So a sub zero。

A some0。And we check and we say， okay， does two fit into that？1 minus2 is negative1， oh。

 it's negative。So。That last bit。s zero。And。This is our remainder。It didn't fit it。 It didn't fit。

And so our quotient is six。This is actually that last， but was that last step of。

The division process and our remainder is one。And so we can write this in algorithm form。

 so we have this。Its R prime， this remainder。Value。

 and we want to perform a divided by B equals Q plus R over B。Where are。Is that remainder？

And so we're going to do this for I equals n minus1 to0 for starting at this most significant bit。

Of of the dividend。The thing we're dividing of A。And we're going to say， okay。

 we're going to initialize this remainder to zero， so we have， let's do our four bit example。

 so we start with it as00，0，0。😊，And then we shift in， shift this left by one bit。

 so that bit falls off and we shift in。A sub I or a is that the first iteration is the most significant bit of of a。

 So now we have 0，0，0。A sub 3， that most significant bit。 And that's the step right here。

And now we're going to perform this difference R minus B。 We're going to check if B fits in there。

So this is our。Minus B。And we're going to say， well， if that difference is less than 0。

 So if it's negative， then it didn't fit。 And we're going to keep that。That remainder。

And we're going to say， hey， it didn't fit。 So that quotient bit is is 0。Okay。

 so that's our first step or first iteration。And so we didn't do the Lt step in this case。

 We'll see what happens on the next step， and it's now going to repeat because we're in this four loop for I equals n minus1 to 0。

And so now we're in the second iteration of this。 So now n is equal to n minus2。We our prime。

 So our prime。This case was00，0， a sub 3， which was one， so we'll just leave it like that。

And now we're going to shift this。Our prime left by one bit。Now we're going to get0，0， ace of  three。

 right the zero falls off。And we shift in the next most significant bit。A sub 2。

And that's what's happening here。And now we're going to say， okay。

 we're going to perform that difference again and say。R minus B， does that fit。

 Does B fit into that value， In fact， it does this time。And it says it's D less than  zero。 No。

 that's not the case。In this case， it's greater than or equal to 0。 it's one。

 And so we now we make our quotient sub I。So Q of two in this case is equal to one and now we。

 instead of passing this forward， we pass the difference forward。

 which is our 0001 into our our prime or remainder prime。Okay， and now we say， okay。

 remainder prime equals D to 0001， that gets shifted left by one bit， so 0001 gets shifted left。

 drop that bit and the next most significant bit comes in。InThis case， a sub one。

Which in our cases a0， so now we're at this step。And now we check and say， does beef fit into that？

We perform that difference again， R minus B。Yes， it does。D less than zero， nope。

 it's not less than zero， so we're in the else case。And we say， okay， well Q is1。I's this one。

And we make our prime equal to that difference。Okay， and now we go to our last iteration。

 our prime was 00，0，0， that difference。And we shift it left by one。We lose that bit。

 and we shifted in the last。bit of a， which is a sub0。This case， it's a one。And we get 0，0，01。Again。

 we're now at this stage 0001 and we perform that difference。1 minus2， is it less than zero？Yes。

 it is。 Our last quotient bit is 0。C of zero is0， and then r prime is equal to R。

Let's just equal to that。And so now we're at the end of the iterations。

 we've gone from to I equals n minus1 to zero。And now we're done with that for loop。

And we say r equals R prime。So。😔，Remainder equals。Is our prime value。And we get our result。

 which is six。0，1，1，0。This value here star quotient and our remainder。Is one。Okay。

 so how do we build this？Here's a。Here's how we build it。 We have a box here。

 each of these boxes is shown here because of space。

 we didn't write all of the names on those little boxes in this big figure。But inside this box is。

This circuit。And this circuit is basically performing this adder is performing subtraction。

 as you can see that we're feeding in。The inverse of B。Plus， one into the carion。

 So that's doing whatever this is， right，0，0，0， a of 3。This is that first iteration，0，0。

0 A sub I in the first iteration is A sub3。So each of these is performing an iteration。

This is the n minus first iteration。This is the n minus2 iteration。This is the n-3 iteration。嗯。

And this is the。And minus4 iterations。 in this case， N is 4。 And so we have the。Right the。Bit 3。

 bit2， bit1， and bit 0 of a3 of a being shifted in。Okay， so this is performing that difference。

Of our。Right， this is 0，0，0， a of 3 to start with。R minus B， because we have。The inverse of B。

Coming in and one on the carry。 So this is performing subtraction。

 and then we get our difference out of it。 we want to know， well。

 we're either going to feed that at difference forward as our prime。That's in the else case。

Or we're going to feed on just this。This this remainder， if it's if the result was negative。

 if B didn't fit。Okay， and they carry out， this is， you know just a ripple carry adder。

It's obedient to these other。These other boxes。And the key here is that we want to look at what is the result of that difference。

And so what we want to look at is this most significant bit of the difference， piece of three。

This is that most significant bit of the difference， and that will determine。What we we choose。

 right if it's negative。Then key sub I， in this case， key of 3。If this is negative， this is a 1。

 soq sub 3 is the inverse of that， it be0。And if it's negative， our prime is equal to R。

 So if it's negative here， we want to feed。R into our prime， it didn't fit。And so this is an output。

This is the difference of the most significant bit that tells us whether the result was negative。

And then we feed that into our。These are inputs。In each of those N。Inputs the selected multiplexer。

Okay， so each of these is performing one iteration。

 each of these kind of rows is performing one iteration of the algorithm。

And then you can see we take either， so whatever our prime is， we take it， shift it left。By one bit。

And then shift in the next。The next most significant bit of A。Same thing。 Next row。Take that R prime。

And then shift in the next most significant bit。And for the final row。Okay。

 so as you can see this divider also quite expensive， just like the multiplier adders， multiplexers。

 it's going to cost us quite a bit to build just this four by four divider。😊。



![](img/538f172a673e7f161c4c9d9a784ac07b_2.png)