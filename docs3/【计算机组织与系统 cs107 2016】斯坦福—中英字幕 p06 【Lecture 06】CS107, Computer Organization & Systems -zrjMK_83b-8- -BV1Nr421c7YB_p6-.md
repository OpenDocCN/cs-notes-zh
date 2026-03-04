# 【计算机组织与系统 cs107 2016】斯坦福—中英字幕 p06 【Lecture 06】CS107, Computer Organization & Systems -zrjMK_83b-8- -BV1Nr421c7YB_p6-

Alright， good afternoon， everyone。 Welcome back to another exciting day in the world。 That is CS。

 107。😊，A couple announcements before we get into the material today。First and foremost。

 basically it's all assignments from announcement wise assignment one grades and feedback went out over the weekend。

 They went out on Saturday。 Hopefully you got a chance to take a look through that and got some useful comments that。

You could hopefully apply to your assignment2。 Also， you know。

 maybe this is the first time that many of you who have seen the automated testing process。

 the you know， the grading that we do here in 107 being。😊。

In terms of functionality being primarily based on the output of your program being automated。

 there are。There's information on the website that hopefully you've seen already about how we do the grading and that process。

Historically， maybe there are there are the occasional surprises as to what the automated grading was able to find that you were or were not able to find in your own code。

 so hopefully that gave you a bit of a sense of what testing is like and the kind of robustness and stress cases we're looking at。

You know how thoroughly we test your program？So moving forward。

 we have assignment two coming in tonight。And we've got assignment 3 going out shortly thereafter。哎。

Let's get into it。Before I start on the actual content for today's lecture。

 I do want to give you a bit of a sort of a roadmap for what。

We're where we've gotten to and where we're headed toward because we are going to be shifting gears pretty substantially today from what we've been doing and so It I want to put that into context and give you kind of the big picture of where we're trying to go。

Up until now， we've been talking a lot about the C language。 We've talked about pointers and memory。

 and we saw lots of interesting ways to use pointers to implement。😊。

Interesting things like strings and generics。 And you're working through some kind of cool problems with assignment 2。

 for example。Now， but until now， we've been drawing memory as these kind of abstract boxes。

 We've been saying， okay， I've got this pointer。 It's in this box。 There's。

 there's some address in this box。 and the int is represented as these four little boxes。

 which I threw the word by around a few times and said， oh， yeah， you know。

 memories stored in a bunch of bytes and ints are4 bytes and pointers are 8 bys。😊。

So now we'd like to actually look at what。What's going on in the memory。

 We want to understand what exactly it means to store a byte。

 how we can interpret that byte as characters， as integers and next time as floating point numbers as well。

😡，So this is the section on data representation。 And then next week， we will start on talking about。

 okay， well now we can represent our data。 We can represent， our variables and our， you know。

 our numbers。 We can think about how to do arithmetic on them。 Now， how do we represent our code。

 That will be next week。Okay。So let's get into our plan for today。😡，So the first。

 so the plan for today is going to be， we will be looking at。This data representation。

 these bits and bytes。 And we'll be thinking about them in。3 different ways。 We'll start by looking。

 We'll start by， of course， defining what bits and bytes really are。 And then we'll talk about。First。

 how we can interpret。Each bit kind of individually。

 we just think about them as actually these little like on off switches。

 sort of true true false values using a set of a new set of operators called the bitwise operators。

 And then we'll look at how these bits can be interpreted as。Signed and unsigned。Integers。

So let's start with just a few definitions。So the first one to get out of the way is what exactly is a bit？

😡，So the bit is which is short for binary digit is。Simply a one or a 0。

 So here you can see I've got this box with。Eight bits in it。So each of these zeros and ones。

 each of those is a bit。 So for now， as we think about interpreting bits individually。

 we can think of each of these as representing true or false，1 representing true。

0 representing false。 I may use the terms on and off or one is on to0 is off。 But so， yeah。And then。

 when we。So1 bit is， is fine。 And that's sort of the most basic unit of storage that we could。

 you know， get on a computer。 But when we， we can put them together into a byte， which is 8 Bs。

 So the picture there is the picture of a single byte。And。The reason that bytes are interesting。

 why theyre know Y 8， Why have we decided to put to pack bits in this particular grouping and not in the other is that bytes are the smallest unit that we can。

Really refer to in C。😡，So we learned already when we talked about Vo star that CAs are a1 B type。

 So this box of 8 Bs could be stored， for example， in a care variable。

And we saw that when we manipulate the addresses that we would be moving through memory。

 like if we did， you know， point arithmetic， we where the unit that we're moving through is in units of bytes。

 So we cannot refer in C to an individual bit。 We can't say， oh， I would like to read this。

This particular zero or this particular one。We have to refer to the entire。But with our operation。

So in order to actually think about bits as。True false， or as on off individual on off switches。

 we need to learn a new set of。We need to learn a new set of operators to work with them。Okay。

So let me set the stage for introducing these operators。Here I've declared two care variables。😡。

Care because not because I actually want to store characters or because I want to interpret them as characters。

 but because it cares a 1 byte value。 So you can see that I've written out these bit patterns for the1 B values。

And so， I have。The cares A and B。I'm declaring them unsigned just so that I don't have to deal with anything weird about positives and negatives。

And now we'd like to look at the set of operators that will allow us to work with。These bits。😡，嗯。

Okay， so the pattern that we're going to see for all of these operators is that。

These operators will work on。The corresponding bits of A And B。 So we'll start。 We could start。

 for example， on the left and。We'll look at the first bit or the so this is going to be called the most significant bit。

Of a and the most significant bit of B。 And so we see that they're both zeros。

 And the operator will will look at those two bits and produce some。

 some bit to go in that disposition。 And then it will look at these two。😊。

And it will produce a bit to go in these positions。

 And the difference between the bitwise operators will be what。

Combinations of these zeros and ones will produce a one or an on bit in the result。

 So let me just give you an example。The first bitwise operator we want to see is the and operator。😡。

Okay， so what and does notice single ampersand， not double ampersand。 So this is the。

 this is a column for what the actual C code would be。 This is the logical name on the left。

So single am percent， not not double am percent is our bit wise and。 And what we get from this is。

You'll notice that in the result， which is this box。The the resulting bit will be on。 It will be one。

 if and only if。Both A and B have a one in that corresponding bit。

 So here you can see that both A and B have a one。 So the result will have a one， but in。

These other three slots， even though A has a one here， because B does because B has a 0 here。

 the result will be 0。ok。And we follow that pattern。For the rest of these。Its。行。Okay。

So you can go to another operator。 This is the ore operator。 The names try to suggest what。

Is actually happening。 So you can think of and as being okay， if A and B are both one。

 then the result will be a one。Or is saying if A or B or both are one。Then the result will be one。

 So you can see that everywhere has a one， except for the two spaces where both A and B have a0。

In that space。Okay。Next operator is the X or or exclusive or operator。Represented with this， the。

 the the carrot here。 So this is like or in the sense that。If A or B is one。

 then the result will be one。 So you can see that here and here。 But if A and B together。

If A and B are both one at the same time。Then x over will be 0。So you can think of Xelor as being。

 are the bits。is the bit in A different from the bit in B， And if it is， then we'll have a one。

 If it's not， then we'll a0。对啊。Okay， few more Bill wise operators。

 And then we can actually see how to use them Here。

 I've just repeated the value for a because the last three operators do not count on。Do not。

 do not depend on B at all。 So I'll just repeat A。 The next operator the not operator。 This is Tilde。

 This is different from， for example， exclamation point。 This is different from negative。

 The Tilda operator simply says， okay， take every bit in a and just flip it。 So if it was a 0。

 put a 1， it's a 1， put a 0。没有。And then the last two operators， which I'm introducing together。

 are the shift operators。 So these let me take。The value for a and they and theyll so they take all the bits in a and they'll move them over。

 So with the left shift， you see here， I， I'm left shifting by2。

 which means that I take this one over here and I move it two spaces to the left。

 I take the 0 and move it two spaces to the left and so on。Now， two things you might notice。😡。

Right away。 So the right shift， same thing。 we move this 0，3 spaces to the right and so on。

 Two things that you'll notice right away with bit shifts， first of all。We。

 a couple of bits kind of fell off。Right， so in the case of the left shift， these leading zeroes。

 these two zeros。Aren't in the result anymore。 We don't have enough space to write those two zeros。

 because were only。Using 1 B。Values。So they， they， they go away。 They。

 you can think of them as kind of falling off the end。 And likewise， for the right shift， the 1，0。

1 at the end here， these last  three Bs fall off the right end。ok。The other thing to notice is。

We have to fill in。The sort of the holes that we've created。

 this empty space that we've created with something。Right， so what do we fill them with， Well。

 for now， because yeah， so for now， we can say they'll basically get filled in with zeros。

 And we'll see that there is one exception to this。We'll see that later。 But for now。

 we can just say that when do we shift。Either left or right。

 the space that gets created gets filled in with zeros。Yeahep， why do you need the XO operator。

 you can just make that out of abandoned order。 Yeah， So the question is。

 why do we need Xor if we could， we could probably get this from and andor， we can。 We don't。

 So you can think about。 So maybe if you're from like kind of a math background like a logic background。

 you can think about what sort of the minimal set of operators is， this is not a minimal set。

 However， it's just useful。 And we'll see why， like， so yeah。

 part the next thing I need to show you is so， okay， great。

 I showed you all these bid rise operators。 Why are we using them， Why do we care。😊。

There's so we don't need a separate operator， but it turns out it's actually just really useful to have。

 So， so it's just a convenience。Yeahや。Unsigned， yeah。

 so this will come up a lot more later in the lecture。

 But for sort of the one sentence is that unsigned means that A And B will not hold negative numbers。

 It means that we should interpret A And B is is always as always as a positive number and。

What that means in terms of when manipulating bits。

 So the reason we use unsigned when talking about bits is that we don't want any of these bits to be special。

 We want to think of each of these bits individually。

 and we don't want to interpret them as numbers at all。

 So it's conventional to use unsigned when actually working with the， the raw bits of a number。

Anything else？ok。すぐでたパ。What happens to them， What happens is the bits that fall off。 They just。

 they don't get represented anymore。 So if you think about like the right shift of three here。

 there was a 1，0 and a1， and they're just， they're just gone。So this is your new number。Right。

5 zeros。1，1，0。啊啊。Okay， so we've seen these operators。And， you know， they kind of like， all right。

 sure， here， here's the definitions。 But， but who cares。 What are we actually going to do with this。

To show you。An example of how we're going to actually use。These operators， to actually make。

To represent these kind of on off switches that I was alluding to。Let me switch over to the code。

Okay， so here， I' got to introduce a couple of new things。First。I need to tell you what an， I。

 I'll say briefly what an Eum is。 This isn't super important for the actual bits part。

 But what I'm doing here is I'm defining a set of。 you can think of these each as constants。

And I'm kind of grouping them together。So here I have a data type that I'm trying to represent。😡。

The different sort of so I'm calling these font traits。

 So you can think of bold italics and underline as sort of things like properties of， of a font。

 You can think of mixing mixing and matching them So you could have some text that is both bold and underline。

 for example。So I'm using an ennoome here to say that these four constants are related to each other。

😡，O。And but instead of defining these constants as just sort of arbitrary numbers， you know，1，2。

 and 3。I wanted to define them。As each corresponding to a single bit。In my。

 so I'm only writing out 3 Bs。 You can imagine there being another 5 to fill out the whole by。

 But I didn't want to write。 I didn't want to write them to to save space， so。

You think so what I'm trying to do here is I've got， I want to represent whether my fontta is bold。😡。

Using the least significant bit， using the rightmost bit。

I want to represent whether the font that I'm using is italics using the middle bit and whether it's underlined using the。

 the leftmost bit of these three。Okay， and I'm generating these constants using bit shifts。

 because that seems。Because I want to be explicit that。

I want about what the bit patterns I'm getting。哎。So here's some code。

 rather than actually walk through the code， kind of。In person。

 I want to actually walk through it in G so that I can print some stuff out as we go。

So I'll switch over to another terminal， and I I'll G this。Its。

And I'll put a breakpoint on the trades program。 I'll try to be oops， put break on trades。

Ts function。 I'll run。 I'll try to be explicit about what exactly which line is executing。

 I'll try to。Do that for the line's that's about to be executed。

 So I have to go next once to indicate that this line has gotten executed。 Okay。

 so what I'm doing is I'm declaring a variable called。Nittrates。Which holds。

 which is going to start out being。Bold， so the， the thought that I'm looking at right now starts out being bold。

 That's the bit pattern。Right， and so now how do we use。

How do we use these bitwise operators to turn on and off the bits of my trades。 Okay， well。

 here's the first example。Here I could， let's say I want to turn on a bit。

 I want to turn on the underlyingline bit。So here I'm using a bit of a shorthand。

 I'm using the or equals operator。 So this is the bitwise or that we saw on the on the slide。

 But I'm combining it with the assignment statement。

 So this is saying this is equivalent to my traits。😊，I'll write it real quick。

 But this equivalent to my traits equals my traits or with underlyingline。Right。

 these two lines are equivalent。Okay， I， I don't know how to actually do it。All right， so。

Let's execute this line。 So now that we've gone next， we can look at the value and we can ask， O。

 so what exactly is。The value of my traits now。So I'll print out my traits。

 And GDP is smart enough here to say， okay， I see that you have this Eum。

 and I see that your Eum is being used to represent these kind of。Bit patterns。

 these on off switches。 So I can actually tell you that。

My traits is currently bold and underlined together。

 It's even using the bitwise or to indicate that the bits that bold and underlined have been ordered together。

Now you might say， okay， well， I want to see what the actual bit pattern looks like， though。

 I want to verify this line that I have up here。😡，Right， I want to verify this。

 this math that I'm doing over here。 I'm not actually go through all the maths， But， you know， So I。

 I put it on the side in case you wanna walk through it yourselves。

 So I can actually ask you to be for that using this P slash T， the T standing for two， like T W O。😊。

And I can say， okay， tell me what the bit pattern is for my traits。And sure enough。

 it comes out to be 1，0，1， which makes sense because this。This bit。Represents bold。

 and this bit represents underlyingline。They actually stored in only 3 bit or isn't like by default。

8。 Yeah， so it's gonna be stored by。 So a care is by default 8 B。

 And then an inch would be more than that。 So the question is。

 are they actually being stored as exactly 3 Bs。 No they're not。

 They're being stored as something bigger than that。

 G is just not gonna show me the leading zeros because therere not that meaningful It's like if I printed out。

 know， if I have the number 12， then I could put a few zeros in front。

 But I'm not gonna So but that's a good question there are actually more bits going on behind the scenes。

 we could even， I could even tell you how many bits are。 I can ask for size of。😊。

So there are four bytes。Being stored for my traits， which means that there are 32 Bs。

But it's only gonna show me three because these are only three I'm turning on。Anything else？Okay。

 so now let's talk about how to turn off a bit。 And so here we can combine a couple of the operators we saw。

 We can combine the not operator with and。And so， this。I won't walk through the math。

 but and not is going to be kind of the pattern that we use for turning off bold on my trains。嗯。

So I go next。And I print out nitrates， again。We'll see that now。

 instead of being bold and underlined together like it was before， now it is just underline。

And we can pe slash T it。To see the bit pattern and sure enough。That one。This one got turned off。

So and not is how we're going turn off these bits。So then。

 so here's an example of where exor comes in。 So I'll speed up a little bit。 But okay。

 now the next one is if we can， we could flip a bit。 So Xor is useful here。 You know， yeah。

 we could kind of simulate it with the other bitwise operators。 But it's very convenient just to say。

 well， if I just want to。😊，Toggle or flip the italics you know， on or off。 Then I can just。

 I can use Xor。Right， so now italics is on because it was off before。And lastly。

 the last example I want to show you is this idea of a bit mask。Which is， okay， so I can。

 I can I've shown you how to set these bits。 I've shown you how to turn them on and off。

 how to flip them。 But how do we actually know if the bits are on。

 So because we can't address into the bits， we need to use the bitwise operators just to check whether or not the bit is on。

😡，And so here I'm creating a mask。 And what a mask is it's gonna be， a couple of， you know。

 it's a bit pattern that I'm gonna， that I want to test against。 So I have this mask。

 which is bold or underline。 I guess， you know， and or or I'm gonna probably use them interchangeably。

 And here I'm gonna， I'm gonna ask。😊，I'm taking my traits and with mask。

And what that's going to do is it's going to test whether or not。😡，Either bold or underline。

Is on in my trades。And if， and if either one is on。Then this value will not be 0。

 And if neither is on， then this。This value will be 0， and the if statement will not happen。Yeah。

 so we can see that this is italics or this mitrates is italics and underline。

 So this should enter the if statement。 Sure enough， it does。

 And it can tell us that bold or underline is on。Right。Sourrk。我 the。Any of that example？

You'll get lots of practice with bitwise operators and creating bit masks in lab。

 So I just want to give you an overview of what that looks like just to give you a sense for。

 you know， how our bits。How are bits useful as these individual auto switches。

 So rather than storing， you know， for example，3 Booles。

 one for is bowl on one for is italics on one for is underline on。

 I can put them into these into a single variable， and I can。😊。

Turn on and off these bits using these， these operators。 And when we start doing some kind of later。

 later work with， with numbers and stuff， we'll have other reasons that we want to be turning on and off individual bits。

 And the way we're gonna do that is through these bitwise ops。哎。Questions about。That part。Okay。

So now we've talked about bits as individual kind of units， as individual bulloles， if you will。

 like a true true false and on off。But now I want to look at interpreting。These bit patterns as。

As actually， as numbers。And so I'll start by thinking about them purely as unsigned numbers。

 I'll think of them as just all non negative。 And then I'll go on to sign numbers later。

So to kind of introduce how exactly we're going to interpret。😡，Bit patterns as numbers。

 I'll use an analogy from sort of the decimal world。So if I have the number 567。

You may recall from grade school when we talked about。

 when you talked about place value that we can think of。

 we think of the7 as being in the one's place。 We think of the6 as being in the10's place and the five as being in the hundreds place。

😊，And instead of writing 10，10 and 1， I can write them out as 10 to the 0 or powers of 1010 to the 0。

10 to the 1，10 to the two。And so if I want to get the number 567， we can think of that as five times。

100 or 5 times cents is 2 plus 6 times 10 to the one。Plus 7 times 1 to0。Right。

What we think of the same process as applying for binary numbers， for our bit pattern。

So here I've got this bit pattern。Right，0，1，1，0，1，0，1，1。And I've written in powers of two。😡。

Since we are in binary， we only have 0 and one。 So we're going to use powers of 2 rather than powers of 10。

And I've written in the powers， of 2 from 0 all the way out to 7 because there're 8 B。

 that's how many powers we get。And we can use the same。

Method of thinking about place value in thinking about these。This bid pattern。

So we can say that this bit pattern represents the number。

0 times 2 to the 7 plus1 times 2 to the 6 plus one times 2 to the fifth and so on。

And if I do the math and I， you know so the multiplication is a little bit easier now because we only got 0 and1。

 if it's 0， then that power goes away， the hard part here， I guess， is knowing powers of two。

 This is something something that that that'll happen。And so I gotten rid of the， the zero ones。

 And you can see that what I have left are a 64， a 32 and 8 of 2 and a1。

 So that corresponds to  two to the 6。To the face。重。And then if we add them all up。

 we get the number 107。 So we could say that this bit pattern，0，1，1，0，1，1。Or1，0，1。

1 represents the number 1，0，7。Yes。question到た。Yeah。All right。So that's all fine。 And we could。

 we sure could keep doing this。 But let me point out a， a key issue here。

You'll notice that the number 1，0，7， really， like the decimal value，10。

7 really has nothing to do with the bit pattern。 It's pretty hard to go from this bit pattern and get to this decimal number。

 And you can imagine going the other way， which I won't make a do because it's just kind of a pain。

 You can do it。 there's a formula。 There's a process。 But it's kind of annoying。 And。In general。

 it's it's frustrating to have to look at a decimal number and say， okay， well。

 what was the big pattern for this， Like what， you know， which bits are on if we actually， you know。

 cared about that。And so you say， okay， well， that's what binary is for， right。

 So we just write out the number in binary， But that's not great either because it's pretty long。

 And I'm already at， I'm at 8 B and I'm already running out of space on my slide， right， So I wantna。

 we want a more compact representation of。These numbers。 but one。

 which can still allow us to think about what。The bit patterns。

 what the underlying bit pattern actually is。So。For that， we need to introduce hexadecimal。So here。

 hexadecimal， which means base 16。Shorten to hex。嗯。😊，It's kind of like decimal in the sense that。

 you know， we've got some， some digits， except instead of having 10 digits。

We're actually going to assign。The numbers， we're gonna assign the values 0 through 15。

 a unique digit。So from 0 to 9， it'， it's the same as in decimal。

 You can see that the decimal and hex columns match for 0 through 9。But once we get to 10。

 we're going to use the letters A through F。😡，Case doesn't matter。

 I'll be probably writing most of things in lower case。 But be。

 will you assign the values A through F。And what this means。AndAnd the nice thing about hex。

 I'll show you how to， how to use it in a second。 but essentially。We can look at， So for a value。

 So if I have the number 15， then I would represent that as F。And then if I have the number 16。

 then I would represent that as 10。 So you can think of this second。

Position here as not the10th place like it is in decimal， but actually as the 16s place。

This0 x part that I'm introducing here is a prefix。 This is something that you can use in C。

 and it's something that I'll try to stick to in my slides to indicate that the number I'm showing you is in hex just so that we don't confuse it with something in binary or in decimal。

 if we put 0 x， that means that this value is in he。All right。

And so this is nice because it's a compact representation just like decimal。

 it's not using any more digits than the decimal number was。😡，But。Okay， so what， why bother？

Let's go back to the bit pattern for 107 again。So here we've got the bit pattern，0，1，1，0， and then 1。

0，1，1。And the nice thing about hex， the nice thing about base 16 is that because we are because。

 you know，16 is a nice power of two， we can group the bits in this way。

 We can think of this our sort of our8 bit value as being two groups of four。

And we could look at each of these groups。😊，Separately。

 and we can either think of looking them up in the table or we can convert this value to decimal。

 So we can think of， so0，1，1，0。 that's going to be a2 and a 4。So then the decimal value is 6。

 And if we look that up in the table， we see that that' that's true that the decimal value is 6。

 and we can represent this group of four bits using one hex digit。And likewise， for this group of4，1。

0，1，1， looked that up in the table。That happens to correspond to the number 11。

Which is represented as a single character， B。So now if I want to write this bit pattern in Hex。

I can just write 6。B。And there you have it。So very convenient to convert to and from binary when to convert hex to and from binary。

Which is why。And and since it's so much more compact。

 we're pretty much gonna be representing every kind of bit relevant constant in Hex。 So if I。

 if I want a， some kind of constant where certain bits are on， I could。

 I you saw already one way of doing that using bit shifts and some bitwise operators。

 another way of doing that would be using Hex。We're very much not gonna write out the actual binary because once you get past a few bits。

 it's， it's unwieldy。一。对。Yeah， so why is they 16 special， It's a power of two and the power of two。

 which is so4，6，16 is2 to the four。 And the nice thing about that is that it's all4 is then divides into 8。

 so then we can take this one B and we can split it into two groups of four。😊，So that's really nice。

 There are other representations that you might run into。 There's like ocal， which is base 8。

 That's cool because it's also a power of two， but then it doesn't split evenly。

 It doesn't split our bite evenly。So that's why V X， yep， anything else？Y。

Could you explain to go house 60？Yeah so if you think about 16， I can't。I don't have the bit pattern。

 here， let me do this。Okay， I'm just gonna to do a quick kind of almost whiteboard thing。

 So if I want 16 and I want to represent it in binary。Right， that's。One times two to the four。Right。

 and then nothing else。So， that's going to be。I I shouldn't have decided to do this， but okay。

 should have that's going to be1 and then four zeros。😊，Right， so this is 2 to the 0，2 to the 1。

2 to the0， sorry，2 to the 1，2 to the2，2 to the 3， and then  two to the four over here。

 So then we can do exactly what we did with the other number。😊，Where we。

So we think about each of these as having a a single hex digit。 So this one corresponds to  one。

 and then this one corresponds to 0。嗯。是rry， so that。I think I that went kind of fast。 But yeah。

 so you can think of now that we've written out the。The bit pattern。

 we can take each group of four map it to a single hex digit。 We see that 0，0，0，0 maps to0。

 and we see that。Well， there's an implicit。3 zeros here。 maps to1。 So then we get 0 x 10。

Right kind of make sense。Yeah， and bit ever non0 is the leading bit ever non0 for which that like 0 x It's never like Oh0 asking me like is the。

 so that no， So the， so the convention here is actually just 0 x is the thing that you use to say this is x。

Yeah， so you're not going to get like a1 x or a 2 x that's not going to happen。Yes。Anything else？

Our pointers and hes。 So the question is， are pointers in Hex。

 This is actually kind of an interesting question to， to sort of。

 there's kind of a deeper question here， which is that。

It is not the case that 0 x6 v is really a different number than 107。😡，They're the same number。

 They're just represented in different ways。 So 10，7， if I look at， if I look at the number 1，0。

7 in binary is this。And if I looked at 10，7 in hex， it's this。 But it is the same number。 If I write。

 you know， int I equals 1，0，7 and I write int I equals 0 x 6 B。I'm storing the same thing in memory。

 I'm getting the same number。So。When we print out pointers， when we look at pointers。

It's conventional to use hex。😡，Because。Poiners are pretty long。 And thinking about pointers in。

 in terms of decimal would be pretty， pretty messy。

 So you'll probably consistently see pointers written in Hex。

But that doesn't actually mean anything special about how they're being stored。

So there's kind of a yes。Anything else？So， one。Hex bit patterns。 that's just always good to know is。

What the hex value for all ones is for a a single， a single byte。So here I've got 1111 and 1111。

And so each of these， you can see in the table， maps to F。And so 0 X， FF is going to be the largest。

The largest number I can represent using two hex digits or equivalently using one byte。😡。

And that maps to the number 255， just something you you know， So， so if I have one by。

 then what this means is that that bite can represent。Any number from 0， you know。

 if all of these were 0 up to 255。 So you get 256 possible bit patterns in a byte。O。😊，All right。

 so I'm going to take a， okay， let's take a little brief digression here。 So I've talked about。

Bits as individual units。 I've， I've talked about looking them at， at them as numbers。

And now that I've introduced。How to look at them as numbers。

I can actually do something quickly before I go back to talking more about numbers。

 which is how to represent。Characters。So theres a， so you might have， you know。

 if you've ever tried to print out a single character in GDP， you may have seen。GDB give you a。

Some number followed by the actual character in single quotes。 And you might have wondered， okay。

 so how exactly is the character being stored if it's， if everything as， you know， as we claim。

 if everything is being stored as。These binary， you know， these zeros and ones in memory， then what？

Then what exactly is the letter A？Or， you know， the， the character A or the， the digit 9。

 And so here is a quick kind of。Summary of a little bit of， of a few， you know。

 of the most important kind of ASI。 So， so that the。

 the system that we're using to store characters is called ASI。 It was standardized a while ago。 It。

 it basically covers the English alphabet。The digits， some punctuation， and that's kind of it。

 It goes from  zero through 127。 and then everything past that is kind of open open season for people to interpret as they will。

 There are a few newer standards to represent various other languages and stuff。

 but it's all kind of a mess and we're not going there。So。So here's just。

 a quick summary of kind of like what the ask you looks like。 So I can show you。

 I can show you what this means in， in GDP， for example。So if I just do G。

 I don't have to use a program。 I can just run GD and ask G to print me some stuff。

So if I asked GDPDB to print me the letter， M。For example。And we can see that maps too。The number 10。

9， I not my slide， but。Even。Add it up if you want。 And we can ask GDPB。

 Here's another cool GDPB trick。 If I want GDP to print the value in hex rather than in decimal or in binary。

I can use P slash X。And we can see what the actual。You know， the， the bit pattern or the， the hex。

 which is equivalent to the bit pattern， would be for the letter lowercase M。So。

Certainly not expected to memorize the ASI table。 Nobody does。 That's silly。 But just a quick little。

 we kind of mention just a nod to， okay， here's how characters work。 So when we say in memory。

 there are the characters Stanford followed by a back slash 0。😊，That's what we mean。 You've got。

 you know， the， the character for S。 we can look it up in this table and we write。

 write down that bit pattern and then for T and so on。

 And then the bit pattern for backslash0 is all zeros。これ。Go。All right， so back back to numbers。

All right， back to thinking about。Binary， back to thinking about how we're going to use。

How we're going to use these bits to represent still entirely positive numbers。

And as part of explaining， okay， how do I， how do we represent numbers。

 I should probably just tell you， I I need to kind of tell you， all right， well。You know。

 how do we do。 So sure， I， I， we could do the binary We can do the binary polynomial。

 We can think about the， the powers of two and the conversion from binary to decimal or to hex。😊。

But how do we do math then if computers are really this into storing everything as zeroro and ones。

 how does the computer do math？😡，So here I've got a sort of simple kind of worked out example of the numbers 1。

0，7 and 58。 I'm going to add them together。Hopefully that is the correct number。

 And here you can see I'm showing the carry。Right， I'm showing that there's。

 there's a carry on the one。There's a carry of a one to the， to the 1th place。

And what I want to do is go through what this looks like in binary as well。😡，So here is the。

 here are the bit patterns for 107 and 58， the 10 7 bit pattern you've already seen before， the 58。

 You may just take my word for it that that's 58。You know， the conversions are not interesting。

 So we're just gonna。You know， can you plug them into G and ask it for for the bit pattern if you wanted to you know。

Okay， so let's， let's walk through。 So the what I'm hoping to show you is that the addition in binary is actually kind of the same as it was in decimal。

 It's just that there's a lot more carrying。 It's just kind of。😊，You know。

 it's a little bit more work for us as humans to do。 Turn out the computer logic is simpler so。

So let's how this looks。 Okay， well， you do exactly what you do when you normally do。You know。

 create cool edition。 Take  one plus 0。 Okay， what's1 plus 0。 It's one。 cool， nice。 Allright。

 now we go to the next slot。 We've got one plus1。 What's one plus1。 If you said two。

 that's not correct。😊，At least not in this world， because we can't write a two here。So， yeah。

 it's too in decimal。 But if I can only write zeros and ones。Then I have to represent two in binary。

 which is 1，0。Right， so I'll write the 0 here。And I'll carry you the one。Okay。

 and then one plus 0 plus 0 is one。 And then one plus 1 is， again， two， carry the。one。

And then we can keep doing it。So lots more caring。 You can see that。But process is the same。

Hopefully， the answer is the same。We can。Very quickly， kind of just do the math here。

 We can see that this is， So this is two to the7。 This is two to the fifth。不是。

2 to the second and 2 to the zeroth。Don't expect you to do this in your head or anything。

 I worked it all out ahead of time。啊。But you can， you can play with the conversions if you want to。

Feel better about the binary。The binary deimal conversions。 But here you go。

 It does turn out to work。O。😊，Questions about this。So addition， just kind of works out we can just。

Do the normal thing。You know， I could show you multiplication， but boy， that's just gonna be more。

 more numbers。 But hopefully you believe， at least at this point that， yes， we can represent。

 we can represent numbers in base 2。 We can do math on base 2 numbers on binary numbers。

 Everything's gonna be fine。 the computer can implement this logic。

 and the hardware takes care of it。 and we're all good。😊，呀。Okay。오물 제법！Of addition。

 which is a little interesting。So here I've got 255， which recall。

 is the maximum value we could store in a single byte， all one， and I tried to add one to it。

So what's going happen。Well， we can go through the same process。1 plus 1 is 0。 Car。 One plus1 is 0。

 We're gonna keep carrying like crazy。And then we get this one。O on the end here。Which。

Its coffee down here。 So okay。Seems reasonable， right， Answers 2，56。 Are we done。Well。

We only had space for  one B， or so far， I'm doing everything in terms of1 B numbers， right。

 So we only have space for one B。And one bite。Stace for 8 B。 So this last one here。

Cannot fit in my bite。So what happens to it。Well， it falls off。 This is what is called overflow。

Because what happened is we went over the maximum possible value of a byte。😡。

The one that kind of that was supposed to get copied over here got thrown away because it didn't fit。

 We're not gonna get a warning。 We're not gonna get any kind of indication that this happened。

 All we will see is that if we took。An unsigned care， because that's a1 by number， set it to 2，55。

 took another unsigned care， set it to one， add them together， get 0。All。

So most of math kind of works。😡，It mostly works kind of the same way。 And everything is O。

 except for this edge case， which is we only have so many slots to put in。To fill our bits。

And when we run out。The system will silently throw away the bits that don't fit。So's 2。

55 plus2 equal。So 2，55 is 255 plus 2。 So if we added  two， then this would be 1，0。

 So you could work it out。 Yeah， you'd actually get 0，0，0，1。Itll the math will do exactly the math。

 There's no special cases here， It'll do exactly the math and you throw away the one in front。

 throw away the one out here。That's it。Anything else。是是是个问拿出。Yeah， so the question is。

 is this equivalent to maing by 2，56， Yes， essentially， So if we take， yeah， you can think of。

You can think of， all right。 we've done the math。 We， we， we work out the addition， and then we do a。

 a mod by 2，56， because that's sort of the。That's two to the eighth。Right。

 and then that's our answer， yeah。And so when we try to generalize this for larger int types。

 then we'll see that that。That generalizes， too。Okay看。Alright， so in light of this overflow idea。Now。

 you may recall from grade school that you learn about a number line。 You thought about。

 you you thought about numbers as starting kind of in one， you know。

 at some position on the line like 0。 and then kind of the line extending infinitely outward in one direction or maybe both directions。

 If we're doing negative numbers to represent larger and larger and larger numbers。

That is not what we actually have。In our system。We start。 So we only have so many bit patterns。

We can't go infinitely out in one direction。So。I put all of the big patterns on this circle。

And the reason it's going to be a circle will be， will become clear later。In like， two minutes。

But I've got this bit pattern 0，0，0 here。And， you know， that represents 0。 And we've got one。

 We've got two。And we can keep going clockwise to get larger and larger numbers。

But then when we get to all ones。And we go one more。 Then we get this discontinuity。

 So it is a circle in the sense that， So yeah， I guess if you're。

 if you're familiar with math and you think about and you， you， you may have seen this already。

 you may have seen modular arithmetic as a circle。 You may have used some fun， fun。

 happy math terms for that。 but I'm not gonna assume that most of you have。 So。😊。

Here you can see that when I get up to this all ones。And I。

 so adding one on this circle means going clockwise。 So if we start 0 and we add one。

 we go clockwise 1。 we add another one， we go here， and we can add， say， you know，60 something。

 get here。 We can add another or whatever。😊，To keep moving around the circle。 But when we add  one。

 add 2，55， we basically jump off the kind of like sort of this， this little discontinuity point。

 we get back to 0。So it's not。 It's a circle， and we can go around the circle kind of as many times as we want。

 but we're not getting a number bigger than 255。Okay。Questions about unsigned。

So that's pretty much all there is to it for representing unsign numbers。 It's not， you know。

 It's not terrible。 There's a binary polynomial。 You map the， you map each bit to a power of two。

 and then。Kind of come day。诶。Okay， so now。We need to talk about something much more interesting and something much more sort of complicated in。

 in a way， which is。Okay， now we want to， all right， so we can represent positive numbers。

 We can represent 0 up to 2，55。 That's nice， but。Now， I want to represent sign numbers。

 I want to represent negatives 2。Now， going back to this circle really quickly。

Just to kind of hammer home the point， We can't。Just add numbers。 We can't just say， okay， well。

 here's your 256 positive numbers here。 Have another 256 negative ones。We don't have space for that。

 We're only， we're only using one B， and that byte has 256 possible。Bit patterns。That can fit in it。

 And so if we want to use any of those bit patterns to represent negative numbers。

 then we have to give up something on the circle。We have to not be able to represent some of these numbers if we want to represent negative  one。

For example。Okay， well， so which number should we give up， Probably don't wantan to give up 0。

 Probably don't want to give up1 or 2。 So you'll see that we'll decide we're just gonna give up this left half。

 We're gonna give up the， the bigger numbers since 2，55 is a pretty arbitrary number anyway。

 in terms of， you know， that being our maximum， We'll just say that。

Everything kind of on the left hand side of our， of our circle is gonna be used for negative numbers。

O。So the idea， right， So we're going to use half the circle for negatives。

And here's a first attempt at it。So this attempt is known as sign and magnitude。

 And here's sort of the first thing you might think of if you， if I told you， okay。

 I need you to go represent me some negative numbers using these 8，8 B8 B by。You might say， okay。

 sure， well， I'll throw away the left hand side of the circle。Well。

 notice that the left hand side of the circle。Has。Has a one。In the most significant bit。

In all of these positions。Right。So'll say， okay， how about this？😊，I'll use the most significant bit。

To represent the sign。So， if the。If the bit is。1。Then I represent a negative。

And then I'm talking about a negative number。 If the bit is 0。

 then I'm talking about a non negative number。And then I've got 7 bit to go。

 and I'll use those to represent the。Actual， the， the absolute value。So in this example。

 if I have negative 1， then you know the seven bits here represent one， and then the MSB。😡。

The leftmost bit is going be one。Indicating a negative。And so here's like negative 20， for example。😊。

These seven bits represent the number 20。And then there's a one in the signed bit。Representing。

That is a negative。喂。So we can do this。 It sure is a， it's a valid representation。 We could。

 you know， get some negative。 We can get some negative numbers out of it and stuff， but。

There are a couple problems with it。 So this is not how computers actually represent numbers。

The first problem is， maybe。You know， somewhat that's a little more obvious in the second is that there are actually two zeroes。

In our， in this representation。So the bit pattern all zeros， sure represents  zero。

 just like I did before。 But now if I flip the signine bit， if I flip the most significant bit。

 now I get what looks like a negative0。Right， I get 7 B that are 0。

 So that's the absolute value is 0。 And then I have the one on saying， I'm a negative。 So okay。

 this is negative 0。But， I mean， negative 0 is the same as 0。

 kind of annoying to have two different zeroes， especially becauseuse now， when I do comparisons。

 for example， if I have to say a number is equal to 0。 Now。

 I gotta check for both of these or something。That's okay。The other problem。

 which is maybe a little bit more subtle that will， willll look at more closely。

We'll look at more closely when we talk about what the actual solution is。

 is that the arithmetic here is actually。Challenging is。It's not。Outrageously hard。

 it just requires special cases for negative。The math。Doesn't just work out。

 And I need to define what that means， but suffice it to say for now that。

The logic to make signine and magnitude work is。A lot is， is much more than we want。

So we're going to explore a different solution instead。Any questions about。

At at least the the sign bit。 So we're gonna to keep with the sign bit stuff， so。

Anything about the kind of basics here。Okay。So let's， let's。

 so the solution is gonna be what's called tos complement。 And let me。

 let me introduce that on the circle。 So I'm not gonna to do any bit patterns。 I want to do any math。

 I'm just gonna， I'm gonna stick to the circle because I think that's sort of the best motivation for it。

 okay。😊，So we've already decided that we aren't going to。Represent the。Larger numbers of our。

 you know， we're not gonna represent the numbers from beyond。 let's just say for now， beyond 1，27。

 So we're not gonna represent the 255 and the 254 anymore。Okay。

 we're going to reserve them for negative numbers。 And we kind of need to figure out， well。

 how do we put the negatives onto this circle。Well， let's。Go over again。

 the intuition for how we do addition in terms of looking at this circle。😡。

So if we start at the number one， let's say， and we add。You know，63。

Then that represents going clockwise around the circle， starting here， moving down around here。So if。

 and then subtraction would then be going counterclockwise around the circle。

 So imagine if I' were at 1，27。And I wanted to subtract 63。

 then I would go count aclockwise back down here。Right， so in here， you know，3。

4 all the way up to 63， and then。So on， right？And。Recall that of the big problem with sign and magnitude that I didn't like was that I needed a special case。

 I needed to do addition and subtraction differently。

So what would it take to not do addition and subtraction differently？😡，With the negatives， well。

 it would mean。That if I started at zero。And I subtracted one。That I would want。

To get to negative one。 And I would want that to be equivalent to moving counterclockwise around my circle by one space。

I would want negative one here。Right， started zero。Subtract 1 means move counterclockwise 1。

 I would want negative one here。By subtract one again。Well， then I would want negative 2 here。

And then if I keep subtracting， then I could fill in all the way down。

 This happens to be negative 64。 I could fill all the way down to negative to 1，27。

So what we've gotten from this。Circle。Is that。Let's worry about this middle part here later。

 Let's worry about the 6 o'clock space in a second。

 But if we're staying in the range from negative 127 to positive 127。

Addition and subtraction continue to work to work exactly the way they used to。

If I start at negative 127 and I add 60， well， then that's just moving clockwise around the circle by about 60。

😡，If I start at negative 60 and I add 100， well， that's just moving clockwise around the circle。

 Pass the 0。Over here。哎。How does see know whether it's signed or unsigned。

 because they look the same。 I you read the bits。 So the question is， how would C know whether the。

 the bits represent assigned or unsigned， that's going to depend on the type。Right， so up until now。

 I've declared， I declared the two cars when I showed you the that part as unsigned care。

 If I declared them as signed care， then it will。So， so you're noticing that， yeah。

 the bit patterns look the same。 And that's part of what we want here。

 We want that the arithmetic for the bits。You know， the arithmetic will work。

 We want the arithmetic to work， regardless of whether we're in signed or unsigned mode。

But the interpretation will be different。 And how C knows whether to interpret the value as a signed number or as an unsigned number will depend on how I declare the variable。

 But the bits are the same。 The logic for doing the math is the same。

 The hardware for doing the math is the same。 That's nice。What is this start the tech data though。

That's a good question。 It's stored in the code， which we'll talk about next week。😀。

Why am I using care instead of an int Because care is a 1 B data type。And so。

I only want to write 8 bits。 We will generalize to inch， probably next， probably next lecture。

 probably the beginning of next lecture， Also a little bit during your lab。 So the， so the。

 I guess quick， quick overview of C types。 So cares， shorts， ints and longs are all。

In what we call the integer family， they all kind of follow the same rule of using， you know。

 the signed and unsigned conventions， the binary polynomial that we talked about already。

They all kind of work the same way。 So whether I use a care or a short or an int will just depend on whether on how big I want the value to be。

 Do I want it to be 1 by。 Do I want it to be 2。For for ints and so on。Anyth else。O。One more piece。

That we need for this circle to be complete， which is what do we put at 6 o'clock。Down here。

If you come from the right and we move clockwise by one more。

 you would think that this should be the number of positive 128。 If you come from the left。

And you move。Counerclockwise， then you would expect this to be negative 128。

And so we kind of just have to pick one。Well， our convention has so far been that if the most significant bit。

 if this， you know， the leftmost bit is a one， then we want that to be a negative number， so。

Seems consistent to put negative 1，28 here。However。

 what this means is that there is now a discontinuity， just like there was in the unsigned circle。

But it's at a different place now。 It was， it was up there。Now， it's down here。Where if I take 1。

27 and I add one， I'm going jump back around to negative 1，28。

And so we actually already saw an example of overflow in the very beginning of the first lecture where we saw that if I take a number and I make it large enough。

 then it starts going negative。 So that was in the case of multiplication。

 But the same would happened for addition。 And here we know exactly where it happens now。

 it's at the exact place where0， all ones flips over to1， all zeros。So if I take 1，27， add one。

 we're gonna to go negative。Alright， question about this。O。So let me walk through an example。

 So I already alluded to the the circle showing me that addition and other arithmetic hopefully work the same way。

 I should probably， you know， let me actually do the math out for one example just to convince you a little bit that the addition does work out the same way。

 So here I've got the。I've got the five。So that's a bit pattern for5，1，0，1，4 plus1。

And then this is the bit pattern for negative 2。 For now。

 we could see that by looking at this circle。That's a big pattern for negative2。And。You， so， so。

 but I'll tell you how to actually get the bit patterns in a second。

So let's do the math and let's see if 5 plus negative 2 actually does come out to3。

 which is what I sure hope it does。😡，Okay， well，1 plus 1，0 is1，0 plus 1 is1。 That all。

 that all is good， right。Then we got one plus1 is0， carry the one。1 plus 0 plus 1 is 0。

 Carry the one。And we keep carrying the one， and we get。

To what looks like what was before a bad situation， We got to the point where we had this extra one。

That doesn't fit in our one by。But now， so just like before， we're going to throw it away。

But as it turns out， by throwing it away， we are left with actually the correct answer。So here。

 this overflow behavior of taking that ninth bit and just dropping it on the floor and leaving us with whatever eight bits we had left。

Will actually work。Using the same。Arithmetic logic that we were doing before。

 the same process for adding up the two numbers。I can get to the number 3。That's nice。

Same process doesn't matter if it's signed or unsigned。 We can just。对 it。Okay， any questions about。

嗯 face。Okay。So back to the number circle for a second。Now， I want to talk about， okay， so great。

 We' got the circle。 And that's all nice， except， I mean。

 I don't wantna have to look up the circle every single time。 I want to do， I want to convert。

 you know， a number to its negative。 So let's say I was looking at number 2。😊，Or let's say， you know。

 let's I was looking at， yeah， So let's say I was looking at2。

 And I wanted to figure out what the bit pattern was for negative 2。

 So I have the bit pattern for 2 is this。 And I want to know what the bit pattern is for negative2。

 We can see it that on the circle。Negative 2 is just the reflection of two across the Y axis。

 you know， drawing a line straight down the middle。 if we just kind of reflect。Over y。

 that's where negative2 is going to be。But what is the relationship。In terms of the bit patterns。

You'll notice that。2 and negative 2 are kind of。They're almost like in verses of each other。😡，Right。

 it's almost like I took all the bits in。2， and I flipped them。But not quite。In fact。

 if I flipped them。Starting here， starting with this bib pattern。 If I flipped them。

 I would have ended up over here。 I'd have ended up at negative 3， actually， You can see that it's。

One counterclockwise of。Of negative 2。Right， so。This one would turn into a 0。

 Everything else turns into a one。That's actually negative3。

So what we need to do in order to adjust for this。Is we need。2。Actually， add one back in。

 so we can flip all the bits and get down here。But then we add one so that we move counterclockwise to get back over here。

So this is the formula。For computing negative X， it's a pretty handy formula because you don't want to be writing out the circle every time。

If I want to get to the arithmetic inverse is one way to call this the negative of a number。

Then I flip all the bits。But then I also have to remember to add one。

And if you can't remember the formula， but you feel like you can remember， you know。

 one fact about two's complement， It's also pretty much good enough to know that negative one is represented as all ones。

So 0 x FF， because if negative 1 is represented as all Es。😡，I could flip all the bits， get zero。

 and then add one。And so you can reerive the formula by just starting at negative1 and thinking about what it would take to get to。

1， flip all the bits， add one。Questions about this。Okay， let's try to apply it。So。You know。

 it be a good time for little audience participation here。

Which is the question I would like you to answer is， what do we get when we take negative 1，28。

 which recall was， I'll switch a couple things。 So recall negative 1。

28 was at the 6 o'clock position down here。What do we get when we take the negative of that using the formula。

What do we end up with？Oh， just take it。30 seconds to a minute to work it out。

 If you want to work with a person next to you or something。Talk it out。你。理见。Yes。

 the title of the slide give away a little bit。は。Put the formula on。会ては。やだけ。こせ。It just corrupt。No。

What oh， sorry， thanks。やぱで。这。So。終りさった。Yeah， so you can do it with the circle。

 you can do with the formula。We try both。我す。Take another 45 seconds。都给演。还是点。比我的毛。第。は罪したい。は。

That's like adding one。正上的。just get all money。いあり。0。あそは。Yeah。Okay， let's， let's。

 let's let's just take a look here。 I'll put up the answer， and then I'll take questions。

 but I'll walk through it。 So we're gonna do the formula。 We're gonna apply the formula。 So we start。

😊，Negative 128， I'm writing in a hex and in binary range so we get a comfort for what that looks like。

 Here's the number straight off of the circle。Will apply the formula for negative。

Which is we're gonna flip all the bits。So， then we get。0， followed by all ones。

Then we're going to add one to it， which means that we， you know，1 plus1 is 0， carry the 1。

 We're going to keep carrying the one until it gets carried over here。😡，We said。

 we actually said a little bit already that 1，27 plus 1， if I go back to the circle， we said that 1。

27 plus 1， there's a discontinuity。 We end up back at negative 1，28。 We overflow。



![](img/5a057c732d83d946a8aae99456e5a343_1.png)

![](img/5a057c732d83d946a8aae99456e5a343_2.png)

So， sure enough。We end up back where we started。 We end up at negative 1，28。So if I， so negative 1。

28 is its own inverse。Theres， and this is what I mean by an asymmetry there that。There。Isn't。Enough。

 there aren't enough bit patterns to represent positive 128。So， we kind of just picked。Somewhat。

 you know， just sort of to be consistent that the 6 o'clock position would represent negative 1，28。

 And that just means that there is， it has no negative。

 If you think about negative as reflecting over the y。



![](img/5a057c732d83d946a8aae99456e5a343_4.png)

Over the y axis。 So you think about here， we've got， you know，0 is its own reflection across Y。

 Neative 1，28 is its own reflection across Y as well。



![](img/5a057c732d83d946a8aae99456e5a343_6.png)

So it is its own inverse。Questions about that。O。So let me talk a little bit about。

Signed and unsigned， some of the things that are， are nice。

 but then a couple of things that may catch you off guard with them。🤧嗯。

Our goal in designing this signed representation and designing tos complement was to。

Make the arithmetic process the same。 We wanted that， for example， when I do plus and minus the same。

Hardware could do both signed and unsigned。Oh， I forgot to change the slide， O。

And so in addition to that， sign and unsigned work the same way when asking for whether things are。

 are equal。 So if I have， if I ask whether two numbers are equal。

 that's just going compare the actual roll bit patterns。 I don't have to deal with any。

 like double0 or anything like that。 So equality is pretty simple， too。However。

 there are a few things that are different about。Between signed and unsigned。

One of them is that you'll notice discontinuity is in a different location。

 We already saw that on the circle that in one case， in the sign， in the unsigned case。

 we went from 2，55 over to 0。Whereas in the signed case， we went from positive 127 to negative 128。

So the discount news are in different places。啊。So， two other things that。

You'll spend a little bit of time in in lab and the next assignment。

 just a quick nod to the fact that right shift is actually different between signed and unsigned。

 So I， I know actually saw somebody asked about this on Piazza like two or three weeks ago。

 I guess I think it is mentioned in， in the textbook and all that， but。Remember。

 when we talked about。shifts filling， always filling in with zeroes。

That is not the case for signed numbers。 If I have a signed number。

Then the right shift operator will fill in with a copy of the most significant bit。

 So if I have a negative number and I writeshift it。

Then I just get copies of the one to Then it ends up filling in with one。

 If I have a positive number and I write shift。 I'll always fill with zeros。 You'll see this in lab。

 You'll see why this is interesting。In lab。 So don't worry if that went too quickly。

 It's also in the book。 And then just kind of a nod of that。Here。

 I'll show actually show this example， which is that the relational operators， when comparing。

Signed in unsigned numbers。Work a little differently。

 not only because their logic needs to be a little different。But actually， because the kind of。

The outcome is actually quite， can be somewhat surprisingly different。So last example of the day。

We've got assigned int， which is negative one。 and we've got an unsigned int， which is positive 130。

 And I'm just， I just wantan to check is。The signant is negative one less than the unsignedant。

Positive 1，30。Nath says yes。Right。Oops， where am I oh。Oops， you。能。Oh， well， that's something else。

 What did I do。呃。However， there we go。 So C says no。So he says that negative one is not， is， in fact。

 not less than 1，30。And the reason， which is， again。

 you'll see more in lab is that when I compare an assigned and an unsigned number。

 we kind of just have to pick one， right， We kind of just have to pick a system to kind of。

 to dominate。 We have to pick one of the number circles to use and see if picks unsigned。 Why。

 because it just pick one。Okay。So you'll get lots of practice with sign and unsigned integers and also working with bit wise operators this week in lab。

 When we come back on Friday， we will generalize our discussion to。😊。



![](img/5a057c732d83d946a8aae99456e5a343_8.png)

Not just one by numbers， and then we'll move on to floatinging point。All right。



![](img/5a057c732d83d946a8aae99456e5a343_10.png)