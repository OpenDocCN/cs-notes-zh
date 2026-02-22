# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p02 02 - Bits, Bytes, & Integers I.zh_en -BV17jcReyETC_p2-

![](img/5ffc94d5a0161a9656f496b1d7a0c3bf_0.png)

。

![](img/5ffc94d5a0161a9656f496b1d7a0c3bf_2.png)

Goodreetings， everyone。笑话。Last time we sort of the introduction to the course overview and some of the logistics today we'll get into the real contest。

In general， I'm not going to spend a lot of time in this course making announcements and things。

 but for the first few I want to just make sure people are queer。

 so as you know this coming Monday is Labor Day and so there's no classes so therefore you won't have recitation sections。

But we are scheduling what we call a Linux boot camp on Monday evening at 7 p。m。

 this is completely optional if you have experience in Linux。You know， command line。

Activities this sort of generic， how do you get code to run， how do you edit files。

 how do you move files around？Will be covered， we'll also cover someone Gi。

Because we're encouraging you to use a Gi server that's operated by ECE。And by the way。

People have various ways communicate us theyre having trouble with that and the honest truth is。

It's not all set up yet， my understanding is the person in ECE who runs that is at Burn Man。

And you go there every year and they have this same trouble every year。

 so hopefully you'll have a really great time there， come back， well rested， fix things up。

 you'll be ready to go。Hopefully by the time of this boot camp。啊。Like I said。

 I won't do over the course of this term， a few of these evening sessions， review sessions。

 none of these are mandatory at all， they're here to help you。

 we may or may not record them in video， we will in all cases post whatever materials were passed out or used。

If there were slides or code samples and something like that will be made available on our website。

Also to mention， as I mentioned last time there is a new lab for this course called Wb Ze。

 it's intended to be a walkthrough of basic C programming。

That hopefully you already are fairly comfortable with。

And so it really shouldn't take much time one to two hours potentially to do it。

 and we encourage you， this will be due a week from today at midnight， we encourage you to get。

Going on that right away， you don't need an autola account， you don't need a GiHub account。

 you don't need。Much of anything except access to the files which are on the website and to some type of machine that you can compile and execute。

啊，扣。I've tested it on my Mac。And on Linux。I don't think it would work directly。Windows。

 because it makes use to some Linux libraries， but you if you have a Windows machine and you want to set it up。

 there's a open source software called SigW。CY G， WIN。

That you can create a sort of unix like environment on a Windows machine。

And this is one we have this elaborate system of wake days and grace days and so forth。

 none of that applies for this first assignment， either get it done or you don't。It's intended to be。

More of a assessment for you to understand whether you've got this sort of programming background that we the sort of minimum programming background we expect to be。

The other is those of you who are officially in the course yet are perhaps on some waitlist。

 please don't contact us， the instructors about waitlist issues。

It'sI don't even know how weight risks work。We're working with Co administrators both in CS and ECE to deal with these。

 and they are much better equipped to deal with it every。Okay， that said。

 let's move on in and this be this material we're going to do in。

3 lectures cover all of chapter2 of the book， which if you open up your book and you count pages。

 you're going to see a lot of pages there， so it's a pretty fast move and these lectures will not。

Dupate or completely cover every bit of material there， the kind of thing。

None of this is super advanced math。But you have to get really comfortable with this is very foundational material you have to be very comfortable with to move on to other parts of the course。

So you've grown up in an era where bits are a sort of a fact of life。

It's interesting that the term bit was only actually first developed in 1948 or so by a felon named called Shannon。

We didn't invent the bit， but he invented information theory which defined the sort of most primitive piece of information as a bit。

And of course， you know that。That everything in your computer is。

Is sort organized and expressed in terms of ones and zeros。好。And that。

I don't know if you ever sat back and thought， well， I wonder why they do it that way。

And the answer is， well， there are reasons， but it's not the only way you could do it， for example。

 that first。A computer， sort of large scale computer is this machine called EnIAC。

And they use vacuum tubes to implement it with a very large， heavy， expensive machine。

And they encoded everything in decimal using one vacuum tube basically10 vacuum tubes for every digit。

if you think of them as on or off， it would represent which of values zero through nine is one of those vacuum tubes。

So。It wasn't always the case that powers of two were sort of the dominant way of thinking about even computers。

But nowadays， he is， of course。And there's a few good reasons from a sort of systems design perspective。

 one of them is that in terms of electronics， if you actually hook up in oscilloscope or some other meter two signals like going in and out of your chips or somewhere。

 you'll see that they're not these perfect smooth。Square lines， they have bounces， variants。

 and similarly the devices that we build circuits out of， as you know， are extremely small。いや。

Not that well engineered as far as nice。Queen responses and things。

The advantage of doing everything in Powers of two or bits is that you can deal with a lot of noise or uncertainty or imperfection in the system and still reliably extract from a signal of either zero or one。

 and especially for storing information。We won't go into too much in this course。

 but you can imagine there's some circuits that have feedback loops where you can either be feeding back a one or feeding back a zero。

 and that's a very stable。Vue， whereas if you try to discly represent。More values than that than。

De or noise or various other sources can throw up those signals。

So it's become sort of a matter of course that everything we do is in terms of ones or zeros。And。

And it's important to understand that there's nothing in a bit or a bit representation that tells you。

 for example， this is a number or this is a string or this is a floating point number or this is a piece of code。

 the bits are just a bit so just value zero1 and it's what how we assign meaning to those bits that determines how we interpret them。

 and that's sort of a general abstract statement that will keep coming back to it multiple points in this course to make sure and really reinforce that idea。

是啊啊。So， for example， we could represent a number like 15213 as a string of。

Of ones and zeros and use a base two representation of it。啊。And we can think of oh。Numbers that are。

Deimal numbers。But we can represent a McGan base too。And in this case。

 we'll talk about this a week from today， we no longer call it the decimal point。

 though we call it the binary point， where the marcation is between values that have a weight of some positive power of two。

 like one， two， four， eight。And once it have a negative power of two weight， like a half。

A fourth and eighth and so forth。And so actually when we represent floating point numbers， we're。

Using a base two representation。The floating point number， 15213。0。Is represented as a binary number。

 but with a binary point。And then awaited by the two to the 13th， which is。啊。

WhatWhat it takes has nothing to do with 15，2，13， it has to do with what it takes to get a number that's somewhere between one and two。

Scaled up to be 15，000。So again， these are fairly straightforward ideas。

 but you just have to keep coming back to this all the time if I see a bit string I can't know in advance whether it's one number or another or what its representation is。

😔，啊。And I can interpret it in different ways。So。There's various ways that you can represent small or bit strings。

 you can write it all out in binary， but that gets to be kind of cumbersome when you have。

 say a 64 bit。Value to write out this string of ones and zeros and so what we'll typically do in this course and it's fairly commonplace is to pack them sort of group them into four bits at a time so that's some value between zero and 15 if you think of it numer。

And we'll represent that as a single digit and hexadecial notation。

 hexidadecimal meaning power of 16 representation。And。

Rather than suffixing numbers with what base we're using， we'll do it the way it's written in seen。

 which is to say that。We'll just prefix something with a zero x。It be an upper or lowercase x。

The letters in there could be。Lower uppercase it doesn't matter。

 but basically we'll use the digit 0 through9 plus a through f to encode these 16 possibilities。

And so one of the things skills you will acquire in this class， whether you want it or not。

 is the ability to fairly easily go between a bit pattern and one of these 16 characters。

Which sounds like a strange skill to acquire， but it's actually quite useful。So for example。

 the way we represent the。Instead of writing out 15，213 in binary， we would group that by saying。

 well， 011 is。Three on this table。And 1011 is D，011 is 06 and 1101 is。I'm sorry， B and。By the way。

 my trick on this is I've memorized0 through nine it's pretty straightforward。I know this is A。

 I know this is C， and I know this。And I kind of inter the other ones between us。

But I don't have a table here。If you have to if you stuck on a desert island。

 having to encode things。Interesting quandri HBn， right？

And so one of the things we'll keep coming back to this when you're looking at typical values on a machine。

 there is no standard， there's no uniform standard。

And so people will talk about well what's the word size of your machine and is it a 32 bit machine or a 64 bit machine。

 you'll hear all those terms thrown around and the truth is none of those are very meaningful。

 in particular like this Windows machine or my standard basically intel microprocessor。

It's actually the hardware in there is built to support 64 B operation。Interter operations。

 addresses and so forth。But it can also run in a。哎呀。Compatibility mode that goes back to。Actually。

 the the。Early 90s。Where the machine only supported 32 bit operations。

 and so we'll talk about a 64 bit machine and a 32 bit machine。

 but the truth is that this one machine is both and that's true probably for most of the machines of any sort that you'll encounter these days。

And so it's really a combination of the operating system， the compiler of what code it generates。

 and the hardware itself that determines what the machine type is。

And so you can actually configure when you compile code and we'll go into this。

 whether it should generate 64 bit code or 32 bit code on most of the machines you'll deal with。

So and you'll see the basic C data types。For most part。

 are independent of whether it's 64 or 32 bids， except for when you quit that。呃。

Saying something is a long， you'll see all of a sudden it flips from four to8 between。

And which execution model you have， and similarly the point is， and this is where it really counts。

Ford Bs。Is a standard address on a 32 bit machine， and it's enough to give you a range of about four gigabytes。

Of memory。Which when that came along， that was a lot of memory。But nowadays， of course。

A lot of machines have more than 4 gigabytes of DRAM in them。

So that's part of the reason why things have really shifted over to 64 bit。Where now the。

Rangs far greater。Again， we'll keep coming back to this。So down at the lowest level， then， as I said。

 we're operating on bits。And。The same guy who invented information theory called Shannon did a Massachusetts thesis。

In 1939。That or 38 or so that was like considered the greatest master's thesis ever。

Because he linked up。The idea of。Of a Boan algebra。

 which was been developed by this magician from in England in the late 19th century named George Boll。

How do you design digital circuits？And so the idea of a bull was trying to codify what we'd call propositional logic。

 reasoning about true and false things as an algebraic form， sort of making it。

More like math than like something that's sort of an abstract philosophical concept。

And so his ideas think of zero as like false and one like true。

And now we can algebraically introduce an operator like and。That gives you a true value only if。

Both inputs are true， so A and B means both A and B have to be true。

 and similar or well either A or B has to be true。So if bolts are false or zero， then you get a zero。

And same with negation， you just slip true and false。

And there's one called exclusive or that we distinguish between inclusive and exclusive。

 we say exclusive or means one or the other is true， but not both。It's interesting in English。

Informally， you can blur that distinction between inclusive andive， if I can say。

 would you like me to cut off your left hand or your right hand， right？

And there's sort of an implicit understanding that I'm not going to cut off both here。Yeah。啊。So。

If you think about how you use or in ordinary discourse。

 sometimes you mean inclusive and sometimes you mean ex。

But we'll distinguish those obviously as two different out。So back when Shannon did this， actually。

It was back when instead of transistors。They had relays， electromechanical relays。

 and they built these。of remarkably complex systems like whole telephone switching network out of these electromechanical relays。

 and he was the first to kind of come up with basic principles that you can take this network of relays and systematically derive an expression describing when you're going to get a connection from point A to point B through this series of relays。

Makes you wonder。How did they do this before he thought of this。

 So it's one of those interesting things that after the。The linkage had been made。

 it was so self evident that we can't imagine any other way of doing that。

So we can generalize then from just a simple zero or one true false value to basically a whole string of bits or what we call a bit vector。

 and if you think about a word on a computer， you have 32 or 64 bits。

We can think of those as not just representing a number， but just a string of zeros and ones。

 and when we can apply these same operations to strings of goods。

So we say and they apply now on a per dense basis， so if we have an and we have to have a one in both elements in the column in order to get a one as a result and simulate for our other operations。

Nice animation right the way。啊。不会会的跑。And so you can see again， more。

 you have to have one or the other。好。好テです。And the same kind of reasoning principles that the sort of simple 01 case。

Applies to mostly holds for the string of this case too。Now that。

One of the actual very practical uses of this。Is for thinking about set。

So imagine that you have a maximum of。32 things。And so you want to represent different sets or subsets of those 32 different things。

 well you can just use a bit string of length 32 and say it's a one if a given element is there and a zero if it's not。

And then use now when you think of Anne， that becomes like intersection of two sets。

Or becomes like union and exclusive or becomes what they call a symmetric difference between the head。

 So this is actually used a lot in real life in computers。

 And you'll come across this that will want to keep track of。How many different？Network connections。

 are we maintaining at any given time and be able to selectively say。

 I will accept an incoming message from any of this subset of the possible connection。

So there's actually a library that lets you。Create these sets and manipulate them。

But underlying it all， all they're doing is using these words of bits。

 one or multiple words to indicate them， and so this is sometimes called a mask。

When you have a string of ones and zeros， the ones are the positions that you're kind of interested in right now and the zeros are the ones that you're not interested in。

 and you use an and operation then to just only look at the items of interest。

So this is sort of a very practical thing， but it's also very important。啊From。

Mathematical sense and there's actually。Theorem。Called the Stone representation theorem， due to Mr。

 Stone。It that， there's a sort of。One to one mapping between an arbitrary set as accountable and a。

Basically a bit vector representation of that。So in C and in actually most contemporary programming languages。

 you can actually make use of those operations and well you're going to get some。

Serious heavy duty experience with this in lab one， which will be out next Tuesday， by the way。

 of learning how to。Love or hate， or at least make use of these bitwise joy and operations。

And so the symbols that were used earlier for and or and exclusive ore are exactly the ones it sees is for these bit level operations。

Until therefore enough as well。So for example， we can。Look at some one byte values。

 so one byte values can be represented by two x digits。And we can。Look at， well。

 what would these operations be？And unless you're like a real Hex wizard。

 you probably can't just do that。嗯。Straight away。Like what the complement of four is。呃，拜。

You could use the table in cheat。啊。But what you can really do is write out， you know。

 there is a binary expansion of four and one then you invert。Those bits。

 and then you go 1011 and you'll find that in the table with a feet。And similarly， 1110 is an E。

So heX is sort of a convenient way to write things out but not a very convenient way to reason about things。

Was there a question？Well， it's a care data type。Remember。

All computers nowadays can represent various different sizes。So the underlying data type care。CHAR。

 sometimes called chaR。Is a bit。 So yes， you have an a bit computer I can。

You have many of them in your lives， but they also often are 16， 32 bit and 64 the computers too。

Question。But just like some。じでしょ。Yes。Same thing if you think about that。

Subtraction of if you take all one。15 and subtract。That you don't have any carriess or bs。

 so it will be exactly the compliment， and that's a useful way to think about。Bit level operation。

And similarly， I can say the complement of all zeros is F， actually， I could do that one in my head。

Pretty easily and other ones again， you can drop down to bit level representation。

 map it into the result you're looking for into bits and then convert back to hex。

This class isn't really going to be about like some people can actually do addition and multiplication in base 16 and their head。

 I can't do that。I figure if computers can do it， why should I go？Now。

 one thing that's a common gotcu in C， both because people don't know the difference or they do and they forget。

 or they make stupid mistakes， or I do all the time。

 is that there's some other operations like another kind of and and kind of or and another kind of not in C。

And they're really， really， really different from the single Ampersan version。So in this logic。

 which is a different logic， there's only two values， something is either false or it's true。

Fals is only way to represent as the value zero。But anything that's non zero is considered true in this context。

And so when I say。Something is and if they're both nonze。Then they're both true。

 and I'll generate the value true， but the value I generate will always be one。下午。啊。

This is actually a useful， we do it all the time， but keep in mind underneath it's kind of a funky way to think about things。

So if we negate the value 41， we get zero because 41 is and by the way。

 don't make the mistake we call it 41 because it' not， it's41 because it's basics2 anyways。好。哦。

41 is non zero， and so its complement is false in this logic， it's a different thing。

 and that means zero。And on the other hand， zero， it's not negation in this。

Sense is just the value one。And so in fact， one of the tricks you'll use in your first web is if you do two knots。

 by the way， I always just say bangang here， bang， bang。Of a value。

 it's a way to convert it if it's0 will stay zero， if it's anything nonzero will convert it to one。

The other thing that's important about。These operations， both and in the orar is that they are。

They have a sort of early termination trick， and so you can say， for example。This bottom one says。

 if I have a pointer called P。嗯。I can safely say PM percent M percent star P。

 and what will happen is what will this return if P as an null pointer？0。

And it will know that result is going to be zero because zero and anything is zero。

 so it won't actually evaluate the star peak。And that's good because if P were at null pointer。

 then star P would give you an error。So you'll think about if and you probably know this already that if you have a long sequence and use ampers sands to。

Or very bars。2。To note， it will only evaluate as much of the expression it has to from left to right in order to determine whether it's true or false。

Anyways， you've probably heard this before。And I make this mistake even now not because I don't know the difference。

 but because I'm not very good type。So another class of operations that you probably haven't spent a lot of time using yet。

Unless your very experience is shift operations。And you can say shift something left or shift it right。

 but the curious thing is there sort of two different standard conventions for right shifts。

We'll make a lot of sense later today or first thing of the lecture next time。

 but they don't make any sense at all in total them。But I'll go over the rules anyhow， so in general。

 what happens when you shift something left？I you just slide the bits over that many positions and you fill the right hand side in with zeros。

嗯。And whatever if there were， you'll basically shift off the end， whatever。

Was in the first three positions on the left before， now willll just disappear into knowing it。

Shifting right， there's sort of two different conventions。

 The one that sort of the natural one is what's called a logical shift， meaningan I do the same idea。

 I shift some bits over。 I I discard the ones that have。Are no longer。Needed。

 and I fill it in with zeros。But there's another kind of shift called an arithmetic shift。

And what it does is it replicates the leftmost bit of the opera argument。

 and that's why in this example it's shown in red。And so as long as it's zero there。

Then arithmetic and logical shift will be the same。But this example shows in this second case。

Where there's a one in that most significant point。Now when I do an arithmetic shift， I will fill in。

With one， which is not an non， that's a useful or good idea。

 but it turns out when these are representing potentially negative values as we'll get into later。

 that's actually a very useful operation， it's a way to divide something by a power of two。

Roughly speaking， so we'll see。In just a little while why there's a distinction。Now， one day。

And as you know and C， you can represent those shifts with。有冇会啊。Double less than your double。

And whether a。Whether a given expression will evaluate using a。

Arithmetic orological shift is a little bit tricky， we'll talk about it later。

 there's only one way to do it left。The other thing that's just a general warning is。好。

There's no sort of strict interpretation in C of what it would mean to shift something by a negative number。

 like you might think that shifting left by minus1 should be the same as shifting right by plus one。

😔，There's no that's unlikely your machine will do that。Assembly， if you say shift number left by 32。

Or by say 100， you'd expect maybe you should get all zeros。

 but that may or may not happen and C as a language makes no particular statement about how it should be。

And that's， by the way， one thing we're going to see with C as a language is that there's huge parts of it that are undefined。

 meaning that basically the compiler writer can choose，How something that is implemented。

 and it may not do the same thing from one machine to another to another。And that's so。

Kind of a disturbing feature。When you're try to write programs that are designed to run across multiple machines and compilers。

 that was one of the design goals of Java。In fact， was to make sure that everything was defined so that programs would be completely portable。

But we're not using Java in this course， so we're going to be stuck with C and its quirks。So。

Now consider rolling along。There's two main。utClas of the numbers of integer numbers we're going to want to make use of in this course。

And one is unsigned numbers， meaning value centerter。Between zero or positive。

And so we'll call those unsigned because they。They don't need a sign to say whether it's negative or public。

And then another question number that we refer to as sign numbers。And。

There's many different ways you could imagine representing numbers that may be negative or positive。

But the most common by far and the way we'll most of it consider。

I's what's called a twos complement representation。And the idea of that is if you look at it from us。

Fip representation。An unsign number is just the familiar binary representation that you have a series of bits。

Each is weight by a power of two。The tweetweeds complement it's the same idea except the most significant debt has a negative value associated with it。

嗯。So we'll show some specific examples。So let's look at two complement is the less intuitive one。

So the number 10。For example。Is just。Positive numbers， so the first bit。

 the signed bit will be zero and you see that the weighting of those。

Values is according to that formula I showed you before。

 that everything but the leftmost fit has a positive weight and the left bit。1 has a。诶啊。

A negative value。 negative。The power of to value essentially。

And the other thing you'll notice is that negative value is。It's more negative。It's a heavy weight。

Its magnitude is large， it's2 to the W， the word size here is phi。So two to the W minus1。

5 minus1 is4， so minus two to the four is。So we'd represent negative 10 then by saying。

 well you start with minus 16。And whoops that sort of a little more negative than I want。

 So I'll add back form two to that。In order to get it to be minus 10。

And that's the general scheme of things that we。A negative number。

 we start by making it very negative， and then we add back positive powers of two to bring it back to zero to the value we。

And so for example， this table shows。If you want to represent。

15213 or negative 15213 as 16 bit numbers。Then what you rely on is the fact that you can set this most significant。

To eitherith one or zero。 and it has a weight in this case of。Two to the 15th or 32768。So just。

Using that very simple set of ideas， we can actually explore a lot about what numbers can be represented and what the representations look like。

So for example， let's look at the unsigned case， the smallest number we can represent is obviously zero because。

呃。We can't represent any negative numbers。But the largest one we can get is if we pile in all the ones we can into that number。

 So you already saw it with。A4 bit number is F1111 has value 15， which is2 to the fourth， minus1。

 not two the four minus1， two to the fourth。怖です。And so in general， a bunch of ones will be the。

Something that's of almost a power of two， but not quite。Similarly， we can think about。

To complement numbers， we can have just that negative bit be our only value。

 that's the most negative value we can possibly have。

And the most positive value is if we turn off that negative disc and pile in all the positive virusers of two we can。

And it will be。啊。In this case，2 to the w minus1 minus1。And we can also。

 if we turn on the negative bit and all the positive bits， we'll end up with minus one。

 those'll sort of almost cancel each other out， but not quite。And in general。

 if you're seeing a hex number， it's a number it goes。SSSF不不不不不。

Most likely what it is is a negative number。You know。

 you're looking at that whole string of ones that are sort of。The very negative value。

 a bunch of ones to sort of bring it closer to zero and then it's whatever is left over。So。

 for example， to be more concrete if we have 16 beds。It's largest value， it's a decimal number。

Is two to the 16th 91。It has a unsed number or as a。Sign number it's2 to the。15 night。And similar。

 a negative number， and it's a zero fault I bunch once。Minus one is always a bunch of ones。

And zero is always a bunch of zero。So what are the curious properties of this？

And you'll see that there's this asymmetry。In the representation that I can represent a bigger and absolute value number。

Is a negative value？Then I can as a positive value。So anyway， one。

 figure out why there's sort of a missing positive number in there。Yes。😊，Yeah。

 we need space for zero，Anything with a one in its first digit。

 first bit is going to be a negative number。Anything within zero at its first bit？

Will be either all zeros， value zero or a positive one。 So that's why there's to say symmetry。

 and it's one of those things that。Does doesnn't really matter most of the time， but when it does。

 it's really an annoying thing。And as I mentioned on。Pretty much any computer you encounter。Nowadays。

 you can have sort of words， you can operate on values that are either eight bits or a byte， 16 bits。

 32 bits or 64 bits are all supported。As data types in the language。啊。And you can see now that。啊。

If it's 32， as I mentioned before，2 to the 32 is around 4 billion。By weather的。Standly。あ。Which is。

 can you see this？1024 is about the same as the council。It sounds like a kind of stupid thing。

When I see a number like 2302nd and I wonder， I wonder how big that is。Well。

 I see that it's two to the 30th， which is the same man。Around 10 of the night。不。Two more。

 that's a four。 And so it's around 4 billion。 Of course， not exactly as you can see。

 but if somebody is sort of。Once you throw around numbers and you want to get some order magnitude sense of it。

 this is actually fairly useful。So some people say that Microsoft switched to 64 its machines because they couldn't represent Bill Gates's net worth as a 32 billion。

And the good news is we' got a long ways to go with 64 bit numbers before that we cover from。

So in general， as I mentioned， there's a sort of asymmetry in the range。

 and of course you also notice that。On the unsigned side。

 we can represent a number that because we can use all the bits。positive sense。

We can get roughly twice the value ons。So if you're being careful in C。

Or any language to that matter？It she not？You be too casual about assuming this range of numbers。N。

 there's never a guarantee that all machines out there that might ever want to program use this two complement representation。

So there's Bill Kim to see there's a special include library file calledlim。h。

That define the maximum minimum values of standard data types。

And those should be correct for the particular machine or compile that you're working with。That said。

 a lot of people cheat and assume that it has these certain particular values。オ。So， one of the。呃。

More curious ideas that we'll look at。And we'll exploring in various ways is。啊。

What simulation then how do we if we look at a given bit pattern like what's shown on the left？

And in some cases， we might think of it as an unsigned number and others as a twos complement number。

 how do those two numbers relate to each other。And one property we'll see。

 as it shown in green here is if they're non zero numbers， then they have the same。

Whether it's an unsigned or a juice compliment number。

But you'll see there's a sort of curious mapping。Between the。

The unsigned numbers as they get bigger when they have a one in their what position。And。

And the correspondingent2s complement number that there actually there's a delta there of exactly 16。

啊。And so there's some kind of curious properties of that mapping。That we'll talk about。

But now as part of our experiment in。Making progress in education。I'd like to try this。And we'll see。

 I know you're going to groan and we might all go。

![](img/5ffc94d5a0161a9656f496b1d7a0c3bf_4.png)

是。If you go to the course webpage。I hope you know already。And this is。I' really。

 I'll be amazed if this works。But there's a link on the left。To canvas， which as you know is。

Is the new version of Blackboard。And you probably have used it more than I have。

Because I never use Blackboard。But if you go to that page for this course， which。能说是频。

you go there in the with。HB外。Day two binding。気事なだけ。And I have an inive view of this tonight。こいデ感です。

诶 people down。A会。Are you finding some little problems that involve little bit problems？

That's one paper。There should be three problems each involving some fifth things。

And there should be some way I can watch you。Ho you can't do it。我觉 well。哦。

This is more of an experiment。I don't think you' able you have to be enrolled in the course。

If you're not enrolled in the course， just sit and relax。

 look over the shoulder of somebody it's not cheating if you do。So the good news is。good news is。

You guys are right and the quiz answer is wrong。Basically， everyone's。And I can also say。

I can also see you guys all for the most part， is really well。



![](img/5ffc94d5a0161a9656f496b1d7a0c3bf_6.png)

![](img/5ffc94d5a0161a9656f496b1d7a0c3bf_7.png)

So I'm pleased to see that this stuff is， for the most part you guys have seen it and I assume that。

Anyone who got the wrong answer is more just sort of mis bit somewhere。Yes。

And so we'll keep this is an experiment， I know that people use as technology successfully in classes。

So I want to give it a chance to sort of let it shake out。

So getting back to the matters at hand then。There's a sort of quirky question like and see。

If I have sub number。到。And see。呃。It's possible， when you just say int。It's a sign number， can be。

 potentially can be negative。On most machines， but not all， not guaranteed。

 it would be represented as a two complement number。And you can also declare。A data type。

 an unsigned data type， implicitly it will be an int， it's redundant。

 but you can also say unsigned int。So I can use casting。to convert from。

A too complement number to a unsigned number。And you can imagine various conventions like one of the way you might imagine this would be implemented as same。

Well， minus1 is a negative number， and I can't wait to present that as an unsigned number。

But I could give me a zero and it's only off by one。Should be good enough for partial。

So you might think that's what it would do， but it doesn't。

Does anyone know up what on most machines this value will be， what you will end up being？Yes。😊。

Almost two to the 31 myths。It's actually two to a 30 second minus one。It's like。

 if you imagine an unsigned number of all ones。Which is what minus1 looks like。

That's the numbers that it will be， so that's the right idea。So yes， exactly。

 that's the main idea and it's kind of a weird idea。To think about， but。In general。

 what happens when you cast？And C between signed and unsigned。Is nothing。The bits。Just stay the same。

 it's just all of a sudden I think of that high bit as either positive or negative weight。

Depending on whether I'm thinking about it， it is signed or unsigned， but nothing changes。

And so that's like really a way different idea than if I say。

And we'll cover a voting point a week from today， if I say something's a voting point number。

And then I convert it to an in。Then something really happens， the bits really change。

And that's actually a fairly important concept， but for now we'll just we'll keep track of these。

This special case of between unsigned and signed， this is true in C and in both southern languages it support an unsigned data type。

So the idea is。logically， what we can think of it is。We're going to。あello。

Take a number that's potentially negative and morph it into one that's。And definitely not negative。

But the rule we're going to do is basically to keep the bits the same and really just change the numerical value associated with that。

And the same is true in the reverse direction。So if we look at our widow table。嗯。Going left to right。

Or right to wealth。If they're both in the range where higher order bid is zero， then。

The numeric value is said the same。But if we're。Going in the range where the higher bit is a one。

 then we're either increasing or decreasing the number by 16 or two to the。The W。あIn thisす case。

And what that means from a sort of pictoral point of view is we're taking the green range of numbers。

Yeah。Smaller order magnitude numbers。And where。We're keeping them the same。

 but the numbers that were very negative before become very positive now。And then the same is。

And there reverse direction in the other way， and then this actually can have some kind of strange behaviors as a result of it。

And in fact， it can lead to some really unpleasant。

Results if you're not aware of it or prepared for it。And in fact。

 you'll find in some languages like Java does not even have an unsign data type because there's so many perils of that type。

So as I've been showing with my notation， you can explicitly do casting and convert。

 but there's also what's called implicit casting， for example， if I have Ia in the bottom，被啊。

If I just say you add some unsigned value and I assign it to a signed int。It will do this。

 it's implicit casting， and of course， in this case nothing really happens because the bits stayed the same。

But logically， I'm converting in some way between an unsigned number and a signed number here without anything being obvious that that's going on。

Similarly， you can have a function。That takes an unsigned argument and pass it assigned value。

It might return a sign value and you could assign it to an unsigned value and those are CAasks that get applied automatically。

From one PM。And so again， that can cause some confusion。

And just to give you a sort of illustration of。Of why this can matter。

One of the quirks of the language。That I don't know why they came up with this convention。

 but they did is if you're doing any operation where one argument is assigned。

 if the other is unsigned。Then。The rule is you automatically convert that sign number to an unsigned one and then continue the operation。

And that applies to addition， multiplication and things， but also to comparison operations。

 like less than greater than。So just to illustrate what I'm talking about。

 these examples show some what might be surprising results。And I'll mention and see again。

 that anything you write。As a decimal number。Is by default signed。Unless he put a u。

 that could be their upper or lowercase U at the end of it。So for example， if I'm comparing。Z。

 the sign number。To zero， the unsigned number。What would the relative values of those be？

Well they're equal。Because they're both， if you think of it， think of their bit patterns。

 they're all zeros and anytime for all the numbers reasonably close to zero。

 there's no difference between the unsigned and twocomps。🤧啊。And you'll see on the right hand side。

 it's key to understand how is this expression evaluated？

And so what's really happening is since this right hand argument is expressed explicitly as an unsigned number。

I'm implicitly going to cast this。To an unsigned number do the comparison。

So if I compare minus1 to zero。Well it being less greater or equal。That's right， obviously。

But what if now I put a little u on that zero？我我呀。I didn't change the bits， remember？

It's going to flip there。What's going on？It's flipping because remember。

 if I turn a minus one into an unsigned number， which I will for this comparison because there's an unsigned number on the other argument。

All of a sudden that minus one becomes a really big number。

And so it will become a very large number compared to zero that will be greater。啊。What if I compare？

This you' recognize as。体面。And this。Re I'm sorry， this is T Max。Complement number and this is。T men。

 the most negative cheese compliment。What the relation will be。Between them。Greater。

 right is a positive number is greater than。好。But what if I put to you？あで。やス、びます。So in this case。はです。

Technology。はい。稍等。It's going to try it。See if this works。

 I don't really have like a blank sheet of paper though。So anyways。Let's see what we can do。



![](img/5ffc94d5a0161a9656f496b1d7a0c3bf_9.png)

It got to get out it' for fun。🎼Technology doesn't really always do what you want。

I'm giving away all the cool stuff。高。But this one's pretty important， I want to show。Remember that。

That's what I wanted to do。It's funny。I'm not as incomp as you might think， I really that。

We line there to say that fit pattern is a zero followed by a bunch at one。And this one。

The bit pattern is a one。It' followeded by a bunch of zeros。And so if it's an unsigned comparison。

Then the left one is smaller than the right one。But if it's a signed comparison。

 then the west one is a positive number。The right one is a negative number。

And so the positive is greater。

![](img/5ffc94d5a0161a9656f496b1d7a0c3bf_11.png)

![](img/5ffc94d5a0161a9656f496b1d7a0c3bf_12.png)

Good派人呢。啊。嗯。And so goes， you can see these other examples are all instances of that。还问。

So this hall is sort of an abstract thing。So mean it's actually a really good source of。

Exam questions but。I won't let you worry about it quite yet。But it actually is a risk that。

Happens in real life programs that when you start using unsigns。

 there are certain things that you might be accustomed to that you no longer can do。So for example。

 imagine and I have an unsigned loop variable I。And I want to do a countdown。 I want to keep。

Basically， what's called。修れば。I call it a post fixed sum I want to take the。

Values of an array and keep adding backward back to a of zero。呃ello。

And keep accumulating the values backward， so what's wrong with this program？

It's like seriously wrong。Okay， never。It's an infinite loop， right？

Logically it's an infinite loop because I is always going to be greater or equal to zero， I is unsed。

So what happens is I will hit zero。And then you'll decrement it。

And what number will you get when you go， what will dectrimenting zero give you an unsigned number？

Yeah you mess， exactly， give me a bunch of ones。So all of a sudden， A of I is going to be edge。

An address that actually doesn't exist on any。Machine that's been built as of yet。

 because there are no true 64 wells。No， it would exist on some machines。

But it's a really big number and chances are it's an out of bound of your valid memory region and it will hit what's called a segmentation fault。

But so it' will probably just crash as opposed to running an infinite loop。But in any case。

 it won't do what was intended。 So you look at that you go Yaha， you're kind of what do you expect？

You should never say I greater equal to zero because anyone can tell it's never going to happen。

It can be much more subtle than that， though。Like way more so， here's an example。

Suppose somewhere I have this。A number I've defined somewhere as。

Because I don't want to keep using size of all。So I just call it Delta。

And I want to do the same general countdown trick something。In this same way。

 I want to keep working this down until I'm within some range。Close to zero。

 but Dlta is a positive number， so I'm not actually going to ever。啊。

Let I go below zero and I was the sign number in the first place， so that should be fine。So。

Did anyone want to guess what happens with this code？啊。And。さ。天生。Right， very good。

There's a couple things going on here if you think about it。The NC。The。Hope I don't have this。

Of size of。Operator， which is a pretty important operator， returns a value of type。Size underscore T。

And that's defined on all machines to be an unsigned number。

That' sort of big enough to hold an arbitrary range of values for a。For a data type。

 so it would be either2 to the 32 when you're running 32 bits or2 to the 64。range。

 but the point is it's an unsigned note， it's always an unsigned note。And so Delta is unsigned。

 and now as you just said， so when I s Dlta from I， I do this implicit casting trick。

And so the result will be unsigned。Even though it started with a sign number and I subtracted a constant from it。

 all of a sudden it magically in the eyes of the C language becomes an unsigned number。

 and so it's the same problem as before it's never less than zero and so it gets into the same problem as before so my point being that。

These kind of。And it's the kind of bug that you can stare at this。For hours。

 because mentally it's hard to remember this particular quirk of the language。

And so these are especially difficult types of bugs to deal with。Okay。

We'll keep on looking at these sort of different bit representations than what they mean。

So as I've mentioned before we see already cases where we have some things are eight bits。

 some things are 16， some are 32 and some are 64 and so there's quite a few operations that for one reason or another have to。

I'll go between those different sizes。And so the general rule for。啊。

At least for the sign numbers from going from a smaller representation to a larger one。

Is to do what's called sign extension。Which， again。Offhand might not seem like a very useful thing。

 but the idea of sign extension when you're going from a smaller word size to a larger one。

Is that you keep replicating that left or signed bit。

And the reason for doing that is with this two's complement representation。

What it will do is it will preserve。Nummeric values。 so just as an example。

 if I'm taking a five bit number。And expand it to a 6 bit number。If that number is positive。

I just want to stick a zero in because I'm just。And you can obviously that would make a difference。

 but the point is that's actually a form of a extent。I'm taking the West most bit and I'm copying it。

Which makes no real。Obvi difference for the positive case。

 but you see it's also the right thing to do on the negative case。That if I replicate that one。せよ。

Minus 16 is not1110。这番。Minus 16 should be 10。就。关一。調し。



![](img/5ffc94d5a0161a9656f496b1d7a0c3bf_14.png)

ここいす。Yeah，Let's fix this。What do people think？The floor。Right。Yeah。I want minus 16 plus4 plus two。

Its latest。あ先。Better。

![](img/5ffc94d5a0161a9656f496b1d7a0c3bf_16.png)

![](img/5ffc94d5a0161a9656f496b1d7a0c3bf_17.png)

こが。So。I didn't make up this way。你。Its that kind of kind of this example is actually pretty interesting to think about the logic。

So I wanted to make sure that the details are right。もケつ。的。This case here。You see what happened is。

In this five bit number， the most significant debt had a weight of minus 16。In when it becomes。

Six bit number that minus 16 foots to be positive at 16。

But I'm adding another bit here with weight minus 32。And so both of those are ones。

You see it kind of cancels out there。It cancels out with a net result of minus 16。

And you think about， oh， yeah。Actually， the general principle。I didた。

And this sign extension can work it out。That you can sign extend as far left as you want。

 and you'll get the same result that you're introducing a string of bits。

Those total weight sum together is equal to the weight the single of。

And they're throwing your number。And so that's the logic between sine extension of how you go from a sign number to a larger signine number without changing the numeric values。

And that's what happens when you cast， say， from a care to an int。

 it will do that sign extension in order to preserve the value。

There's other times when we want to kind of squish things down。

 we want to take a bigger number and reduce the number of goods。

One thing you'll think about is first is， wait a minute， you can't do that。

That's what caught Shannon's information theory told me is。You know。

 there's a certain amount of information and you can't go any smaller。And that's right。

 so what happens is somehow we're going to potentially lose information here。

It can be even worse than that， we can not only lose something。

 but we can come up with something that seems to have nothing to do with the earlier value。

But that's what happens when we go from a larger number to a smaller one in general。So for example。

 if we're going from a five bit number down to four。嗯。

And it's a sign number what we're doing is we're taking that sign bit that was before and we're basically tossing that away and whatever happens to be and。

Now the new a most significant position， all of a sudden will go from having a positive weight to a negative weight。

And if the numbers are close enough to zero。You'll see that that actually is defined。

 whether it's negative or positive。I can basically afford to lose that most significant debt。

And still maintain my numeric value。Just。That's sort of the inverse of the signine extension operation。

On other hand if。If I。If though the number I'm dropping。

Is not the same bit value as the new sign bit。 Then I'm actually going to sort of do strange changes。

 So for example， this is。嗯。10。That one's correct。But if I make this a four bit number。Mysteror。

 so it's going to become -6， right， It's going to decrease by 16。And similarly， if I take。

A negative number。Which is minus10， they got this one， right？And I drop off that bit。

 it's going to become six， and the reason of course， is I can't represent minus 10。

As a four bit two complement number， my range is between minus8 and positive seven in this representation。

And so what I did was basically。Squiip it， so the point being that。When you lose information。

 you're just going to change how you think about these bits。

And it may or may not be the right thing to do unless the number is already fairly close to zero。

Okay， that' will do us for today。

![](img/5ffc94d5a0161a9656f496b1d7a0c3bf_19.png)

![](img/5ffc94d5a0161a9656f496b1d7a0c3bf_20.png)