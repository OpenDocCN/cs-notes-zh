# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p04 04 - Floating Point -BV17jcReyETC_p4-

On there you go。比O。Today we're going to talk about floating point。😡，in particular。

 we're going to talk about the fraction binary numbers then the iy floating point standard。

 which is sort of the standard that。あ。三班。Some examples of properties。

Rorounding additional location and then look at what's done in the sea。Okay， so。有意思最近。

Of fraction numbers for。Numbers and basic that。But the principles of this thing。

 so if you look for phase two， if you look at this number here。What you see is you see 1011。

To the left of dec。Right， and that's just1 equal plus two。Plus a that's a lot。Okay。

So that's easy to figure out， but what about to the right investment？Well， in right the point。

In decimal， as we know， the first digits is like the10th digit and the next one is the10 digtits and then the thousands digit and so forth。

 while the principle is the same it's just it's factors is two， power are two。 so it's the half。

Quarter a 16。 So what this represents here is。しわ。That's a half。There's no quarters。N's8。as we said。

 this is 15。So it's 15 plus a half plus a eight。Okay， in general， as I said， it looks like this。

 you've got everything to the the this side of the point is powers of two right so the J bit is2 to minus J and everything to the left theesal point is。

Powers of positive eye is the eye position。And so there's a simple formula now it shouldn't look very familiar if you're used to having a ten there instead of a two。

Okay， if you're in dec。But otherwise， it's the exact same principle。All right。

 and so here's some more examples。If you look at the first one。

You see that five and three quarters can be represented as101， which is5。Right。

And then this again is a half， and that's a quarter。

 so as's shown here it's five plus a half plus a quarter， which is five to three quarters。

And similarly， we can represent two and78s and one and716s and it works out to be a shown。

And you'll notice that the three examples I've given are you divide by two to get from one to the other。

 so this is divided by two， this is divided by two。

 and what happens with the bits is they just all get shipped right it's the same bit pattern。

 one is0， one1 one， it just gets shifted by one position， shifted right by one position。Okay。😊。

And reverse is that if you want to multiply by two， you just shift the case the other way。

And notice that the。That have the number zero and the budget ones。Okay， that's。

That's really close to one。Okay， so because it's you know。

 half plus of quarter plus age plus 16th and so forth， and that almost makes it to one。

And so the limit is the number you increasing number of bits， you would get to one， but in general。

 it's going to be one minus whatever you've lost off the end， one minus。Okay， so。

So there's some limitations that arise immediately。

And the first limitation is that because that the base dictates what numbers you can represent。

Concisely。So for instance， when the base is two， I can easily represent half a quarter and so forth and three quarters and things like that。

 but if I wanted to represent something like a third，Then， you know， it has a thing。

Not divided evenly ever， so it ends up being this repeating sequence of 010101。And similarly。

 fifth ends a thing， the repeat sequence of 0011，0 011，0011。

 and a 1 is that same sequence just shifted over because you're divided by two。

And so you notice that whereas in base 10，110 was represented very simply as just 0。1。You know。

 in a fixed number of bits in phase  two and 1/10 actually cannot be represented a fixed number of bits。

 right， just a repeat repeating sequence。The second limitation is that there's only sort of one。

One binary point in amongst of the bits and so where you decide to。

If you wherever you put that binary point that sort of limits the range of numbers。

 so maybe you can get really with large numbers or very small numbers and we'll see how that plays out。

So anlig floating point standard。Was the。know established in 1985， really， if you don't provide it。

 it's considered a very black mark against your processor。

 okay and so pretty much everybody provides it even though it's really difficult to provide。

 it's a challenging standard to implement the hardware。

And it's actually kind of interesting because if you think about how processors were designed in many cases。

They were designed for what's easy to do with hardware， okay。

 the instruction sets you get and so forth， a lot of things the hardware designers want。

 say over software designers right， that things hit hard in software because the hardware designers just built what was easy and hardware。

This is one case where the opposite happened。even though it was a pain to do in hardware。

 the numerical numerical analysts said we have to have this， we have to have this。

 we have to have this， and so the hardware companies bit the bullet and implemented this。はい。

And the reason is that the standard has very you provides very nice standards for things at grounding overflow underflow。

 things work out really well。As well as can be， I guess。

 given you only have so many bits and with nice mathmatic properties that we'll see。

That if you didn't have those， if you had something that was easier to implement。

 but didn't have these nice properties， things would be really challenging for software writers in all sorts of ways。

O。So you've probably seen representations like this。So you start off with a signed bit。给。😊。

Then there' are going to be some of bitss that are devoted to what's called the expon of the EP field。

 and then some never bitss that are devoted to the fractions。

And the way that gets interpreted is that if you look at the number itself。The the sine bit0。

 then of course minus one of the0 is1 is 1 and so you get a positive， and if it's one。

 then you get a negative， so that's how that works。Now， what's interesting is that the。This x here。

hi represents what you want to raise the two of whatever power。啊。

Is not exactly what goes in these bits here and we'll see why in a few slides。

 so instead it's just some encoding of the expent and then there's a way of translating from these bits to what the intended exp is and then you can manipulate them accordingly。

Similarly， you have this significant M。Okay， that gets represented with some number of bits in the frac。

Okay， but it's not going to be exactly the same。And you'll see in a minute， how are they different？

but you can represent things like the course number 15。

 213 in base 10 as in this expression as minus one to the zero with a significant of the bit pad shown there and the export of 13。

One important point I should have mentioned is that the significant is always a fractional value that can be as low。

 sorry normally， and you'll see why that's upon a little bit。

 is normally a fractional value in the range between one inclusive and exclusive of two。All right。

 so you may have heard of single precision and double precision， floating point。

 a single precision is 32 bits， the way that's commonly divided is to allow eight bits for the exponent and 23 bits for the faction。

If you have double precision， you allow 11 bits for the export at 52 bits for the fraction。Okay。

 and again， this is sort of by convention right I mean， there's no fundamental reason why you。

Decide to put this many bits for the expon and this many bits for the fraction。Okay。

 except that it seemed like it could compromise over the range of numbers people wanted to use and the。

Because the exponent controls how big and how small numbers you can have and the fraction controls how precise can your numbers be？

If you have a lot of bits of fraction， then you can do more precise。はい。啊。

And then we're going to talk about that there's really three kinds of floating point numbers。

There's the typical kind， which are the normalized ones。The one in middle。

 and that's whenever this exponent is not all zeros。And it's not all want。

And then there's the two separated cases， one is where x is all zeros and that's called denormalize。

 and the other is where the X1 is all one， and those are special ones that we'll talk about minute。

But most you want to focus initially on these normalized ones， as they're the most。Com。Okay， so。啊。

So we have this exponent。Okay， so we have some number of bits for the X quantity。

And we want to be able to express both very large numbers and very small numbers。

 so we want to be able to have exponents that are both positive and negative。

OkayNow we could have said， oh， we'll just use you know our sort of sine number dimension。

 we'll have the first bit be the a bit and the。Be the actual the magnitude。

 but instead they do something slightly different with a of the bias。

And the bias is when you look at the bits that are actually there。

 you want to subtract off this bias。So the bits that are there are going to be interpreted as an unsigned number。

😡，They're going to range from because we're not in these two cases， they're going to range from one。

To sort of the。largearge number we can hold how many bits minus the fact that we can't。

 you know we're not allowing the 111， so it goes to one to 254。

As opposed to 0 to 255 becausere again， the normalized range trued software those to endpoints。

And so if those are the bits we care about， then we take those bits， that numbers。

 and we should track off this bias 127， and so what that allows us is to actually have exponents in the range between minus 126 and positive 127。

Okay。And with double precision that bias is computed differently， because you had 11 bits。

 it's basically two to the 10th minus1， which is 1023。 but it's a Saaxon principle。All right。

 so that's the sense in which what you see in those bits is actually not the actual expon it' thecoding。

Okay， because you want to subtract off that bias。All right。

 now let's look at the difference between the significant this M and the bits you actually show up in the fraction part。

So the first thing that happens is that there's an applied one。Okay。

So our anticipate would be one point belowla b， but because it's always one point belowla b。

 we don't need destroy the law， so it saves us a bit so it's really all the other bits up to that point。

And so it's minimized when this fraction is all zeros， right？And because of the implicit one。

 that corresponds to one point。And it's maximized when this fraction。Is once。And again。

 if you remember that was the 0。11111 case is the case it's almost up to the next number。

 in this case almost up to two， but just mine's a little epsil。

So that's what I meant when I said that the rage of these things。

At least in the normalized case always falls between one and slightly less than two once interpreted。

Okay， so let's look at an example and here's our little cheat sheet here。

 okay this is what the value is going to be， it's going to be minus1 to the sign and you'll have the significant times2 to the E but the E is going to be computed by taking what the bits that are there。

 this EXP and subtracting offer bias。So if we have this number here。Okay。

Then if we put it in the form where you have a one followed by dot。

 then the power you need for that is 13， so it's two to 13th。Okay。😊。

And so what you end up with is all the rest of bits become part of the fraction。Okay。

 and it turns out we have more bits than we need， okay， so we've had out to zero。

And the exponent again， the goal is 13， but we want that to be the goal after we subtract off the valley。

 so we have to add the bias to get the proper number of bids to put in there。

And so that's 140 was' going to be represented as shown， and so the end result looked like that。

And you can see how you could take a number like that and reverse it right so you say okay the sign of these deposit number。

 that expon which is， know if you fits that's 140 I subtract it from my bias。

 so I get 13 and the fraction part， I interpret it as putting a one dot in front of it and I get exactly the value that I desire。

Okay， because so that。All right， so that was the normalized case。ok啊。

So that can cover a large range of values。But you're sort of。

Limited to how close to zero you can get。Okay。If you call， like for the single precision。

 we could get down to。back up。Right， we could get all the way down to。You know。

 exponent of minus 126， so I get a two to minus 126。Okay。

 what you might think is really tiny and we'd be happy。

 but it turns out that you know you often want to even get closer as zero。

And so to allow for that to sort of pack in more bits even pack in more representative values close to zero。

 we have this special set of the x point。Where we look at the values in a different way。

 and those are called normalized values。And so a couple of things are different here。

 One is that the exponent instead of being。The E instead of being the bits minus this bias。

 like the 127。We're going to interpret that as one minus device。Okay。And then the significant is。

 instead of beingd with a leading one is going to be encoded with a leading zero。

So why might that make sense？And the idea， why is the combination of those two things？

And the range of the normalized guidance。Makes sense for why you start to to normalize onces there。

it is。涉拉危机。Significantly smaller。できくでくる。そそ来週。It's your fact。C you。

You can also represent zero that's good Yeah， I was talking more about the the transition between these two regions right so in the one case I was able to get to two to the you know minus。

啊。Sorry，120。6ix。It was right。And then you know one point。The smallest number I could represent was 1。

0 times 2 and minus 126， right？Well what's the largest number I can represent here。

 right it's basically。You know。1 minus 127， so it's 126 again。Okay。So you think， oh， well。

 that's kind of redoneundant， but now notice because the mans start to zero。

 I actually start at things that are strictly smaller， right the large number I we represent。

Is this one， right？So it's a perfectly smooth transition。

 I've gone from one times two to the minus one to a second to something just slightly less than that。

Okay。So that's， for instance， why this is a one and not separate。ok， so。Good， special cases。

 as was mentioned， you have all zero key。It turns out that because this doesn't account for the same bit。

 we can have a positive zero and a negativega zero。啊我 to个三点。And in all the other cases。

 we get numbers that are。Equal space and closer to zero than anything we could represent with normal ice bucket。

Okay， so that was the denormalized case and we'll look at some pictures of that in a second。

 but before we get to that I want to talk about yes。You saying that the。No。

 they're just absolutely apart。Okay， so。All right。Okay。

 so now in the exponents or on the other extreme where they're all one。

 we interpret that differently as well， if the。Fraction of part is all zeros。

 then that's going to represent infinity if the sine bit is zero and negativefinity if the sine bit is。

Okay， so this is representative two overflowed cases。And there's some examples shown here。

 if you do one divided by zero， you get positivity。

you can distinguish that from you say one divided by negative zero。

 which would be negative to Europe or negative one divided。And any other case where the fraction。

 except for the case where the fraction is zero， is not a number， okay。

 a special thing called any andN not a number。And that represents the cases where you know cephonum Merco died。

 so if you try to take the you know skirt of fine squ then you imagine your number， if you try to do。

Inproer arithmetic with afinity is not a number and so forth。Okay， so that's the two special values。

Okay， so let's look at this。So suppose in C， you had this hexscimal number。

And there's our hexadecial cheatiqin。You should actually be getting really good at this by now if you've been doing the assignments。

啊。And this our translation keeps you。就啊。In this case， this is the normalized case。

 so with it you get the x mice device。As opposed opposed to say one nice twice in the genome one less case。

 and let's consider the case of the single precision where the bias is 127。Okay。

So this is the division between sine and export point and fraction。Okay。

 and these are things we want to be able to compute。And then when we computed those。

 then we're going to be able to figure out the value by just plugging our format。

OkayNow if we take that sequence that hex us to the sequence and you map it to binary。

 then c is this0 a looks like that and so forth， okay so that's just the bit spelled out。

And then if you interpret those as the first bit being assigned it。

 the next eight bits which is the red ones being the EP part and the reing fraction part。

It looks like that。And remember that our significant M starts with one。Okay。So。

So how do we get E while we take that X on it？Which if you look at that bit sequence。

 it's 128 plus1 so get 129。We subtracted upper our bi 27， and we ended with two。

Because that first sign is one， we want a mega number。

And if you look at the fractional part headed to one。 one dot。

 then you get zero halves in one quarter。It's one plus quarter to get 125 and so this number。

 this 40 point number， when actually value it is minus5 because it's the sign hit times 125 times two to the two which is four。

And one of the quarter times score is fine。来。Is that clear？So here's a little bit of visualization。

 you can see that as I've sort of touched on this， you've got all the normalized numbers。

That are bounded on the one side by the negative affinity。

And the positive ones that are bounded by positive fittingty。You've got the denormalized ones。

 the closest ones to zero， and then your special case of that you actually have the minus is zero the plus zero。

And clearly this isn't drawn to scale， okay because。The deorized numbers are。

Our tiny pack around there。Okay， so just to look at some examples， we're going to actually。View。

 very short。40 point numbers， so it's on tiny 4 point numbers。

So let's suppose you have one that you're trying to represent an eight bit。

Representation of floating point numbers， and so we're going to allocate four bits for the EXP and three bits for the fraction。

And based on the size that EXP， and the fact the bias is always to that number of bits minus1。Minus1。

 then you add it with seven and okay。And but everything else is going to be the same as what we talked about。

 there's going to the notion of normal， do normalize and zero， not a number in infinity。Okay。

 so what does it look like so to keep this slide simply we're going to show the examples where the sign bit is zero。

 okay so just the positive ones， including positive zero。So I mean， you can stare at this later。

 but the main thing to remember or to note is that case so we have zero here right。

 when everything' is zero。And then in the dennormalized range。

 which are all these ones here in the white background。

You have all the possible choices for the fraction。But for each of these， the X one。

 because when the de normalist case is going to be one minus our bias。

 and since our bias in this case was seven， they're all minus6， you can see they're all minus6。😔。

All right， now the values are going to be， you know this the represented here。

 so it's half a quarter and eighth， so that's one eighth。

This one's you half a quarter that's two8s and so forth， this last one here is one one that's78。

That gets multiplied by two to the minus6， which is 164。

And so here are the actual fractional numbers you would get in each of these cases。Okay。

 and you can see in blue， we've actually plugged in the numbers， right the one fourth。Two minus6。

And that's what you did， okay。And the top one is close to zero。

 the next one is the largest deized number。Now， as soon as the exponent flips to being non zero。

 but before it gets solve once， then we have the whole normalized range and you can see that the。

So now we see a bit pattern like 000， but we have to remember that there's impitly a one in front of that。

Okay， so that's why this is。8 days。Because it's basically 1。000。Okay， and now we add one more。

 we get it to nine8 and so forth。Okay。but otherwise you're just plugging into a form that looks like that。

 and you're showing what the numbers are。Eventually you get closest to one below。

 then you get one and then closest to one to above。

 and then eventually you get to the largest normalized value you can represent。And then after that。

 you get the x one is 111 and it's。Either not a number or infinity if the fraction alls。Okay。

 so again， that's another way of thinking about how or using example to figure out how these numbers play off。

 sort of if you think about， well， what kind of numbers can I represent， what do they look like？

And here's another way of what we have done。So here just to make it simple。

 we've even done a much smaller example of six bit format where you have three bits exploring two bits for the fraction。

And what we've done is we've plotted the denormalized ones。

 which are that middle slice there showing of black or eight values， the normalizedized ones。

 so you can see how they sort of。Also， concentrate closer to zero and then the positive negative 50。

And if you zoom in just on that middle part， you can see that。

there's certain values that include the positive negative zero， three values on each side of that。

And mean thats so forth three up。So you can see from the figure that indeed the deormalized one are a space in your。

 whereas the normalized ones are sort of expanding out to the。Decide a bigger and bigger jumps。

Okay questions on that。嗯。So some properties of this the。嗯。So if you call if every bit is zero。

 that's interpreted as zero。Okay， and so that's nice because that means it's the same bid sequence as。

 say a zero on integers， so having choose complement or unssononic， right？嗯。

So that's great the positive zero is the same。啊。The other thing that's interesting is that if you want to compare two floating point numbers。

 you can almost get away with just looking at their bits as unsigned numbers and prepared。Okay。

And you can sort of look at that if you go back to this thing here， right？

So this was the numbers were listed from smallest and largest。

 and if you just look at the actual bit patterns。You know， ignoring everything else。

You can see that they do increase，So， and you know， you can sit down and argue for yourself why that。

True in general， not just for this example。Just just as an situation， you can see that。

If I just interpret those numbers not as one， four and three， meaning different things。

 but just as a single unssteinigned integer， they do increase as the numbers increase。啊。

But the almost part includes things like， well， we've got a negative zero as well as a positive zero。

 and we've got all these names， right？啊。But otherwise it's okay。

 the normalized ones are indeed can be properly compared to normalized ones， the normalized ones。

 properly compared to infinity and so forth。はい， good。All right， Campson。不是这什么事。あ能。

people pretty much stand。主要的么。All right， it looks like people have done pretty well。The first。

First question was know a bit of a review where we're going to try to throw in like one review question just to。

Keep you on your toes basically if you're。If you're shifting by eight。

 that means you're moving the CA。Ability to the left of the F&E。

 and so it ends up being cafe is the correct answer。嗯。

So question two goes back to the example I gave earlier in the actual beginning class。

 where I talked about how representing one/10th。Can be done in a finite number of bits。In base 10。

 but requires。It's a repeating sequence， it's an infinite number of bits to get exactly right in say base two。

So the answer for that is false and most have got it right。And。Normalize。

 it means a lot of different things， but one of the things that does imply is that there's an implicit 1。

0。One dot in front of the fractional part。Whereas with a denormalized ones， it's an implicit zero。

Right， good。Any questions on there please。

![](img/2953939c9ffbff37de34bd72d4addb52_1.png)

![](img/2953939c9ffbff37de34bd72d4addb52_2.png)

觉呢。2043。

![](img/2953939c9ffbff37de34bd72d4addb52_4.png)

Okay， so now let's move on and talk about rounding， addition and what。いや、。嗯。I mean。

 you can certainly compare the。The bits， right and they would be the same。呃。Yeah。

 I guess for infinity， you can say they're equal， but like two ns are not equalensus。

But for instance， as I had in the early example， if you take infinity， you attract infinity。

That's not a number right so you don't get zero， so in that sense they're not equals。一有。

A little bit complicated。Okay， so we want to be able to do arithmetic on 3 point numbers。

 and we're going to talk about addition and multiplication。

But because we only have so many bits on our representation。

 we're going to often need to do some amount of rounding。

Okay so we'm going to take an answer that's a result of an addition or motivation say and round it to fit within our representation。

行。So you can think about different kinds of rounding modes。

And we use this example here where we want around these five different prices， $ $4060。

50 and so forth， so then here's round at the dollar。交了让。

So in the first line me show you that if you round towards zero。Then $1， $40，$60。

50 all get rounded down to a dollar。250 gets rounded down to $2。

But maybe what's a little interesting is that negative the $150 since we're rounding towards zero。

 we'll get it rounded into negative dollar。可以。啊。Then there's rounding down。

 which says no matter what you always round towards negative affinity， so $140 rounds a dollar。

 $250 rounds a $2， and in this case a negative $150 rounds down to negative2。

The flip side of that is always rounding up， so in that case。

 say negative 150 would round up to negative a dollar and $250 would round up to $3。

But often sort of an intuitiveitive thing to do is to round the closest。

So if I do that to the nearest， then for the first two cases it's obvious what to do sorry first two cases。

 so for $140， the nearest dollar to that is $1 I ended up browning down for $160。

The nearest dollar of that is $2 as I end grounding up。But now I've got this $150。

 and that's like halfway in between。You know what should I do？嗯。So the， the policy of nearest even。

Says that， if you're halfway in between。Okay， then you want to round in the seat。

It doesn't say always round an even number， it says only in the case you've got this tie。

 you've got to breathe。😡，Then you went around in the year or。Okay， so $50。It's halfway in between。

 50 cents， halfway in between。So the choices were either round up to $2 or down to $1 since $2 is even。

 you round up to $2。250， you round down to $2 to get to an even number and 150 you you round down to negative2 again。

 to get an even number。And that's the default rounding scene that exists。

That's why it's important to understand。Okay， so。And this were actually kind of challenging to get the system do anything else。

 right？嗯。You have to do the manipulation yourself， to some said。

 what the hardware supports is this round。啊。Now。Okay， that was the nearest dollar。

 but let's suppose you want to round to the nearest100 in this example here。Soveniir hundred。

Of course is you want to round？I'll but the two beds off， right？

So how you do this if you you know the obvious thing to do again is to look at these the digits that are to the right of where you're trunc gettingating and if that's and then round to whichever direction is closest so in this case you know you're going to round down because that's less than halfway。

In the next case you're going to run up because that's great halfway。

And now you have this tide case that we talked about last time， and so if you round even。

 then in this case， the choices were round just 7。89 or 7。90。

 and even in this case means sort the last bit is  zero。Okay， and so you'd grounded9 zero。

but in this case， the choice is between 0。89 and 0。88。And 0。89， the last bit of that is a 1， 088。

 the last bit of that is 0， so in that sense， 0。88 is even。

Okay sort of this way of thinking about even and so you round that to that。谁？Is that clear。All right。

 so with binary numbers， it's actually in some sense simpler。

 right because there's only ones of zeros to consider。So if you want to around。

So what does halfway look like？You know， is one followed by bunch of zeros。

So if we look at these numbers。Here， and we say， okay。

The digits in red are the parting considering when I'm deciding whether it's less than halfway。

 greater than halfway and so forth， and so since 011 is less than halfway which is。

10 zero you round that one down conversely the next one you round up because you're above。1，0，0。Now。

 the last two cases are two cases where you're exactly at 100。Okay。

 and so now you want to round it to the even。Okay， so in this first case。

The choices were to either round up to 11。00 or round down to 10。11。And clearly。

 the former one is the one that's even。 It's the one with a zero the last bit。

 And so that's what's shown right Conversely， this latter example。

 the choices were between rounding to。10。11 or 10。10 and the latter one is even one and so you're round down to that。

Okay。Ex对。So how is this done inside the processor itself， right？Well， it's given that rule。

 it's actually pretty simple。So if here is。嗯。If they're trying to round to the nearest eighth in this space。

 the three binary digits。We'll call the the， the lastit digit is called the guard bit。

 which is represents G。The first digit removed， first bit removed。Is called the roundund bit。

And then all the other bits are the sticky bits。And if you're recall the only pattern we really care about。

Is distinguished between a one。And it's a bunch of zeros and a one and something where there's not a bunch of zeros right。

 and a zero and something， right？And so if you look at all we care about in all these extra bits。

 all these exp bits。Is there a one and there or not？Okay， so that's just doing it all。

So the machine will do an or over all these other bits， and so it will take any given fraction。

And represent those as okay， what was the guard， what was the round， what was the sticky？

And so theys down to three bits， and so then you can build a little state machine if figure out what to do with the three bits and you know if you look at the rules。

 you'd see that you don't want to increment in these three cases and you do in these cases and you get these rounded up。

Okay， so the actual way it plays out is exactly the way I described in the previous slide。

 it's just if you're wanting like well， how's this done in the hardware in a nice， convenient way。

 this is how it's done。嗯。啊。So now we know about rounding。

 now we can start to do operations where we're going to the experiment。

And we're going to consider modification and addition。So multiplication。

 so in this case we're trying to multiply。You know， this number versus the。Okay。

 so each of those numbers has。You know， when we look at the bit representation and we translate that back to an actual value。

 we know it has a sign and a significant and a。Exex point。Okay， and。

And we know the exact result if we were to full precision lu。

 would be that you take the product of the two significance。You take the sum of the exponents， right？

2 to the E1 times 2 to e2 is2 to the。Prenheesis U1 plus C2。And then for the sign。

 you want to take the。symmetric difference， right to if you have if both the signs are the same。

 then you know you're going to up with a positive number。

 if ones zero and ones and the others are one， then it should be a negative one。Okay。

So that's what would happen if you computed the exactly。Okay。

 but that form is not going to be in the right form， necessarily。So we have to fix it up all right。

 so for instance， if now we have a mantsa a significant that's no longer one point something right it's bigger than greater equal to 2。

 then we fix that up by simply shifting the whole thing to the right and incrementing the x point。嗯。

Because it's by shifting the right or dividing by two and to maintain the same number by increment E or multiplying by two。

 so it's the same number。Now， if the exp is out of range， then we just have to do an overflow。

Positive or negative infinity， and then the fractional part。

 which is the translation of this after the shifting， I guess。Um。

 we want to truncate the right number bits and we want to do that in a way that respects our rounding rules。

对。So let's look at a quick example， if our original number is， it looks like this。Okay。

 and we want to multiply by this。Then， again， the the。The啊。

We got two to the two and two to the three， so we add those two exports。

 and we get two to the five right there。OkayAnd we take the product of 1。010 and 1。110。

 and you could do that quickly。If you wanted， but and you confirm that this is the answer by 1。0 10。

0011。Okay， so that's the exact result。Now we have to fix it up。

 so we fix it up by since this is bigger than since M is now bigger than two。

 we shift this thing to the right， so that's why this。It's just shifted to the right。

 and we add one of that x point。Okay。So all we've left to do now is to round。

We want to be able to round this to say， three。Three bits。Here。Okay， but we have five bits。

And so we look at the bits we're truncating and we see we're actually much closer to rounding up than to rounding down。

 and so that's why we round it and you get a one more。那 question that。Now， what about addition。

So addition。You know， as you learned in elementary school， you've got to get the。

The decimal points there， in this case， the binary points lined up in order to add you to put them in the right column。

So that's the first process， right， is just try to line up those binary points。

So you shift this over by E1 minus e2。And then you can actually do all the addition of the bits。

And you get some sort of exact result。Okay。And the。Okay， and then then。

We're going to take the x want it to be the larger of the two。

 because that's what we're kind of doing when we line up where match it to the larger of the two。

And then we have to do this fixing right so again if n is greater than equal to two。

 we want to shift to the right。Increment this excellent。And so for I should have said。

 actually in multiplication。嗯。The。So maybe we're okay。

I was a little worried that we might have to repeat the shifting more than once if it's like say bigger than four。

 but I guess you can't get it to be。That big because both these numbers are less than two， okay。

 number one。We're good， all right， you just have to do that at most once and similar with the addition。

 you just have to do that most once。But we have this other situation with addition that maybe we've ended up with a really small number。

And so you know's after we did this attraction it's 0。

0000la before we're getting in ones and now it's not in the canonical form of a one followed by a bunch of zeros。

 and so we fix that by shifting the other way， you know we shift this number if is the first one。

 we shift number over here so one is that side of the deal point。

And then to keep the exact same value， we have to decrement。Excellent by how many positions we ship。

We're going to overflow if the expon is out of range and we' again have to do rounding with a fractional part to make it fit。

Roround these thenippym to make it fit。So a sample here。Okay， so we have our two numbers。

And the first thing we do is we line at the decal points。

 we do that by making them represent them both in as times two to three， so for the larger one。

 the bit pattern is the same right？But for this one， we shifted over by one because 1。

01 times2 to the two is the same as 0。101 times 2 to3。

 so now we've got them lined up and now we can do the addition right zero plus zero zero， 0 get to 1。

One， you get carry and you end up with 10， 0，110。Okay， and notice that's bigger than two。

 so we do the trick of shifting。So left and incrementing from two to three to two to four。Okay。

 so now everything's good except for what we have to do around me。

 so let's suppose that we have just three bits。To represent the fraction。

So that's where we're looking around and so here it's 10。So you know that's the tie。

 that's the halfway between and so we want it round to the nearest even。

 which is this right and the choices were either round at 1。001 or 1。

010 and the latter is the unit one。你可始算要要开始。ok so诶。So with that in mind， so we just did a disher。

Okay， so the question then is。You know。How well does this work in terms of preserving the properties that we'd like to have in addition？

And the answer is pretty well with some exceptions。可以。So。

Is our way of doing floating Ily standard for floating point edition？Way of doing addition。

Cled under edition。Okay， and the answer is yes， although you make get like an inity or not a number。

Is it commutative is x plus y equals y plus x？啊。Again， you can check for yourself。But that's true。嗯。

Is zero the add identity if we add any  floating0 point number and zero。

 and we get back to the floating0 point number？The answer is yes， that one's good。Okay。

 does every element have an additive inverse so for every element is there a sort of a minus of that element so that we add them together you get zero again that's almost true the only issues are with infinity negative infinity plus afinity and the nine in numbers so as long as you're staying out of that range we're good there as well。

好。Montogeniconicity says that if a is less than equal a B is greater than equal of B。

 and we add something to it。The same point in both sides， is it still greater？あ、いこで。

The first size so did we go to the sex side。And again， that turns out to be true。

 except for the special cases of inffinities and namess。

So you can see that basically five of these six properties that we'd like to see in any representation of numbers。

Holds just fine， and so that's one of the very nice things about the standard and so forth。

So the catch and this is a big catch。If you ever doing any sort of numerical computation。

 and this was touched on in the very first lecture over to your lecture， is that you lose associate。

Okay， that basically because of the overflow and the fact you have do some rounding means that you know you can take。

Two， the same three numbers and just associated differently and you get very different answers。

So in the second case you have two small numbers， they're represented exactly， you can subtract them。

 you get actually get zero， and then you add it， you get the right number， but over here this。

Sos number this very large number。Dwarfs the 3。14。And so it just gets truncated away。

 it's as if you never added it， and so that when you subtract off this same very large number。

 you're actually going to end up with zero。Okay， so this is a serious problem in numerical computation is how do you design these things to so that Ronnie doesn't kill you。

 how do you set up the problems？Your huge mathematical simulations and so forth。

Of weather patterns and things like that so that rounding doesn't kill you。Or if you're the the。

A man spacecraft right then Roic it literally killed。Okay。

 what about multiplication here the news is pretty good as well， all right。

 it's closed under multiplication。あ、しみるです。One times anything is still that value。And。

So the multiclant monity says that if a is greater than equal to B and you have a non negative C。

 then if you multiply that C by both sides， then the。The sense that the inequality doesn't change。

And that is also true except for infinities and for the means， okay。

 so this is pretty good as long as you still out of a range of infinities and dance。Mification。

 however， has the same problem with sosocitivity。Okay， you get weird rounding effects。And similarly。

 we all know that notifications distributes over addition。know。

 in real numbers in general and in certainly things like integers。

But because of overflow and inexive surrounding， you can come up with examples where it doesn't work。

That a times。B plus C is not equal to a times B plus。えタス。だけ。は，也个。Yes。

 do we take over that into consideration？You take one take one do we take。Consideration。喂 you been。

They't always go true。诶，这不说。Yes， so you're saying even under like integer addition， integer Mo。

 we have these exceptions。Because the overflow is correct。We don't take over consideration when need。

在 say啊。可是。啊。Well， I think you have to understand。嗯。You have to you。Well， I mean， the it's。

The overflow in this case will generate infinity， so that's perfectly fine。啊。If you recall， like say。

 for unsigned integers， the way to think about the result was always modulo。You know。

 two to the whatever number bits you have， right？And so under that。嗯。You know， that's。

Field the finite field wrapped around mod arithmetic， then all these properties have。

Because it sort of took an overflow out of the picture by saying， oh。

 well what we really argue is that when viewed as modular arithmetic， it all holds。

I' property school。Here we're sort of taking it down the picture by saying， well。

 we have this affinity symbol。And so that's going to catch it。That's really a nice subtle point。

 Ka you brought that up。Okay。All right， so what about in C。

 so C has you can declare something to float， which is a single precision or a double。

 which is double precision。啊。And now let's look at casting。

 so if you take a doubler float and you cast it in your miniteger。Now what happens Well。

 it will just truncate the fractional part， there just drop all fractional part。

 you get the inger and so that's equivalent to rounding towards zero and you just got rid of all the。

あよ。And it's not defined when you're out of range。Not a number。Generally。

 it was set it to team men in those cases。嗯。Like for instance。

 of a double could have many more bits than a。the in hole， right。

It's not defined if you're out a range。啊。Into double。

 as long as the int has word size such that you can actually represent all the bits in the double。

 so in this particular case it's a 53 bit word size。Or less， so like they third two bit images。

Then you don't lose any precision converting double。

 okay there's enough bits there in representation to cover all the measures。嗯。

And for float where you often don't have enough bits， it will just do the rounding move。Okay。

 so given that in mind， let's do a few puzzles。Okay， so is this true？

If I take an integer X and I cast it to a float and then back to an integer。

Do I get back the original X？Right， they get rounded。对，对对。Okay。

 what out for a double or does it save on doubles？Or that just fine， right？Because there's not bits。

As long as the end is less than 53%。嗯。What about this one？

I start off with something that's a float a cas are double back to float。小文。行。

Good about the other round， take a double。Now， there's a lot of thiss there， right？て么？

This is going a bit here in a few C programs in your past。

So two divided by three without the de point。It's interpreted as integer division。

 so it would be zero。Once you put the dec point in there。

It's going to be interpret as a floating pointer。You get the。66。If I have a double， that's。

Negative and multiply by two。Is still negative。So it multiplying by two， it's done theregan。

That's fine， right even if I。Even if I end up overflowing。

It doesn't change the assignment never change the assignment。So I get negative。谁？

If I have a double that's bigger than a float is the negative float。这就刚才那个。OkayNo issues there。

If I square a number？It's not negative。I'm sorry， if the square numbers is always notmnized。

 that's what that's asking。Can somebodybody tell me why？It number give。Well， okay。

 so we're assuming here sorry should point out。So of these examples。えです呢。The why。

It doesnn't change the same。I'm sorry， the sign is always going to be。

The scientists is computed independently of any overflow work， so they're both。If D is positive。

 it'll be assigned to observe。Semetic difference with the s goes to zero， and if it's1。

The fourth one is we get signed that exert amount。All right。

 what if I take a double and add to floatingem then I subtract back off that double？

I get back the flow。What佢 wrong。It's surrounding it。Okay， good， so in summary。

 we have this I tripE floating point standard that has you know。

Real pain typically blend the hardware exactly right。

 but the vendors were forced to do it and they've done it。 And so we have this scanner that has。

Very nice mathematical properties， well understood mathematical properties。

You represent numbers of the form assigned bit times the submit。Times the2 the。

The there is about the operations is independent of any implementation because it's the standard。

AndWe show you how to do that with perfect precision and then round。

It's pretty close to realrithmetic， but there's some gotchas， especially in terms of so。哎。还是不在。



![](img/2953939c9ffbff37de34bd72d4addb52_6.png)