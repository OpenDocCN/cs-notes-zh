# 哈佛大学《商业的计算机科学｜CS50's Computer Science for Business 2025》中英字幕 p01 CS50 Business - Lecture 0 - Interpreting Information .cut.zh_en -BV1ArsFzQECJ_p1-

In CS 50 X itself。 But we welcome your questions and comments in the chat along the way。 And in fact。

 if any come up， my colleague Colton will be in back to relay some of them as needed to me In the meantime。

 this course will not go live oned X and elsewhere until later this year。

 along with the new and improved assignments。 So stay tuned for more。 And thank you for joining us。

 our next live stream after this afternoon here in Massachusetts。

 United States will be tomorrow morning with C 50's own Colton Ogden。

 Check out C50 do L slash zoom for that URL。😊，Okay。🤧。This is an introduction world。Hello。哇，不。Right。

Oh， but I guess。Hello world。 My name is David Main， and this is an introduction to computer science。

 for business， for law， for medicine， really for anyone working in the real world who wants to better understand this increasingly technological world of ours and ultimately and dare say。

 most importantly， be able to make more informed， better decisions as it relates to technology Now computer science itself is all about information。

 indeed， the focus of today's lecture is going to be on interpreting information。

 And even if you're not a computer person per se odds are at some point。

 you've heard the computers really only speak a certain language， zeros in ones。

 the so-called binary system by implying two because they only have two outletters in their alphabet。

 the zero and the one Now by the end of today's lecture。

 you yourself will be able to speak and read binary if a little slowly and with some practice。

 but the hope there is to take the first of the layers off of this field of computer science。

 So you better understand what so permeates today's society， today's tools today's。



![](img/dcaa1408b263172f0268af819d18ac12_1.png)

Technologies now， what really is computer science beyond information。 Well。

 it's really the study of that information， How do you represent it， How do you process it。

 And with computer science， Of course， there's this association with code programming that so many of you know of。

 if not have a bit of experience with yourself。 But in this course will focus far more than on code and on first principles instead underlying germs of ideas that underlyinglie today's technologies that today's code。

 today's systems and more so that ultimately after this class。

 you can not only better understand the technology you're using。 But for instance。

 if something goes wrong， you can much more effectively deduce through logic and reason what might explain that issue。

 and， of course， how you can then solve that problem， because at the end of the day， too。

 computer science really is about solving problems， sometimes with code， sometimes with paper pencil。

 sometimes with other techniques as well。 Now， code is really the translation of a lot of the ideas will focus on in this course。

 too， a language that a computer can understand。 And a lot of。



![](img/dcaa1408b263172f0268af819d18ac12_3.png)

![](img/dcaa1408b263172f0268af819d18ac12_4.png)

![](img/dcaa1408b263172f0268af819d18ac12_5.png)

Computer scientists certainly write a lot of code。 but increasingly。

 we're entering this world of sort of no code。 so to speak。

 whereby you can still tell a computer what to do， but you might use so-called natural language。

 your own English words， your own spoken words in any human language because someone else has written code to understand that human language and to convert it into eventually those underlying zeros and ones。

 And so we' really focus at all different layers of complexity in this course。

 not only the zeros and ones， which frankly will quickly leave behind us。

 but will also quickly abstract on top of those zeros and ones and solve problems at a much higher level。

 Indeed， among the takeaways of computer science as a field， this course in particular。

 is to equip you with techniques， namely abstraction being among them via which you can solve problems in the real world。

 and take a step back at what seems to be a very large problems。

 perhaps decompose it into smaller problems， but at different levels of complexity。

 such that sometimes you might need to drop down to a fairly low level implementation detail to implement something。



![](img/dcaa1408b263172f0268af819d18ac12_7.png)

To solve something。 But often， we can reason about problems at a much higher level instead。

 So let's go。Scr it up already。 Not supposed to re reveal this picture。

 So if you're playing along at home， let's pick this up。 Why don't I start here。

 And I'll go back to this the lectern so that I can then talk about this picture。All right。In fact。

 if you will， let's go ahead and play a little game。 odds are right now， you're watching this online。

 but hopefully within reach， you have a sheet of paper。

 maybe a ruled paper or printer paper or just scrap paper。

 So if you could reach for a sheet of paper and a pen or pencil and see if I can't program you as our first exercise together to draw something on that sheet of paper and among the goals here beyond drawing a pretty picture that you can put on the fringe later today is to ultimately think about how we might approach problems at a high level or at a low level。

 So in fact， what I'm going propose first， assuming you've now gotten that sheet of paper and if not。

 you can certainly pause and then come back， but assuming you have that piece of paper now in a pen or pencil。

 go ahead now and draw a circle on that sheet of paper。



![](img/dcaa1408b263172f0268af819d18ac12_9.png)

Below that circle， go ahead and draw a square。On that sheet of paper。And then lastly。

 on that sheet of paper， draw a triangle。

![](img/dcaa1408b263172f0268af819d18ac12_11.png)

Fairly straightforward， not all that difficult， but I dare say because I presented to you those instructions at a fairly high level。

 And even if you know what a circle in a square and a triangle are sort of intuitively。

 you might not necessarily have drawn this very picture。 Now， if you did great。

 You're on you're on track already。 But there's many different ways you could have interpreted what I proposed。

 like maybe you started with the circle in the middle of the page， a reasonable starting point。

 I probably should have clarified where I wanted you to start， maybe more to the top。

 so you could actually fit everything， I probably should have clarified that the square is touching the circle。

 not just below it and similarly that the triangle is touching the square below that。 And even then。

 I probably should have clarified that the tip of the triangle is touching the square。

 not the base of the triangle。 So even with these three simple shapes。

 because I spoke at such a high level of abstraction。

 just talking to in terms of circles and squares and triangles。

 There's a lot of ambiguity and therefore。

![](img/dcaa1408b263172f0268af819d18ac12_13.png)

precisioncision and the funny thing is about computer science and in turn programming。

 when you try to apply those ideas to a language that a computer understands。

 you ideally need to be as precise as possible so that there's no ambiguity so that the machine ultimately does what it is you want it to do。

 Well let's go ahead and try one more now， let's go ahead and do the following， if you will。

 on the other side of that sheet of paper， on some other piece of paper again。

 pause if you need to go grab another， but using that same pen or pencil go ahead now and do this put the point of your pen or pencil near the top middle of the page and then draw a diagonal line down to the southwe。

😡，If you will， think to yourself for a moment， which way is west， Which way is east。

 So you do this right。 But starting from that middle point near the top of the page。

 go ahead and draw a straight angled line。To the southwest。Then from that point。

 draw a similar length line straight down south。And then draw another line to the southeast such that the end of that line perfectly lines up from where you first began。

Then from that point， which is probably near the bottom of your sheet of paper right now。

 draw a line straight up。 that's the same length as before。

 It's not going to touch that first original point accordingly And then from the end of that line。

 draw another line to the northwest so that you intersect the second point that you made with your pen or pencil。

😡，Now go ahead and pick up your pen and pencil， put it back on the very first dot at the top middle of your sheet of paper and draw to the southeast this time。

 yet another straight angled line。😡，That's the same length as all the others。

Then draw a straight line down to the south。That's the same length。

Then draw another angled straight line to the southwest。

 which should ideally intersect that bottommost point that you drew earlier Now you can either trace the line vertically above that to the north or you can just pick up your pen or pencil and put it on the point that's immediately above。

😡，The one you just led to， and lastly， draw a final straight angle line to the northeast so that you intersect the second point that you made this time around after picking up your pen or pencil for the second time or for that one and only time。

All right。Now， if you got this picture completely wrong， fine it's on me。

 but wouldn't it have been nice if I just told you to draw a cube on the sheet of paper。

 therefore giving you an abstraction that's many high many layers above the low level detail that I just dragged you through verbally by giving you directions north。

 south， east west and diagonals therein， I could have just told you to draw a cube abstracting away all of those lower level implementation details。

 Of course， if I asked you to just draw a cube， you might draw this。

 some of you indeed might very well have。 but your positioning of the cube might not have been the same。

 you might have rotated it somewhat， you might have drawn lines in such a way that the aspect ratio isn't quite the same。

 So your cube could have ended up very different for mine。

 even if you were following my directions as stated draw a cube， but we need more detail。

 We need more precision and therefore less ambiguity。 So these two simple pictures。 the circle。😡。



![](img/dcaa1408b263172f0268af819d18ac12_15.png)

![](img/dcaa1408b263172f0268af819d18ac12_16.png)

The square and the triangle Vi V this cube sort of alone give us an opportunity to talk about abstraction。

 talking at a fairly high level， but with that comes not only understanding。

 but potential misunderstanding at a lower level though you might have greater understanding because if you just follow the step by step instructions I mean how really can you go wrong but you start to lose sight of the forest for the trees so to speak whereby it's not at all obvious what you're drawing until maybe the final stroke of the pen or pencil at which point oh it was a cube。

 why didn't you just tell me a cube the whole time So among the things will do in this course in computer science more broadly is get you more comfortable thinking at different levels of abstraction。

 high level low level and everything in between and indeed when the worlds software developers set out to implement some new tools。

 some new product what they're often doing first is sort of verbalizing what it is they want to build as that product may be rattling off the feature list but it's only later that they go lower level and start talking about the implementation detail step by step how are they going to achieve。



![](img/dcaa1408b263172f0268af819d18ac12_18.png)

![](img/dcaa1408b263172f0268af819d18ac12_19.png)

That very task and indeed increasingly nowadays， thankfully we have techniques like AI where we can talk to the AI again at that higher level abstraction and ideally it will output those lower level details。

 but even with our pictorial design here and you are all actually intelligent。

 not artificially intelligent， even then there's going to be potential ambiguities and room for error and that really speaks to what we can and can't do perhaps with AI。

 at least when it comes to verbalizing our instructions thus far。😡。



![](img/dcaa1408b263172f0268af819d18ac12_21.png)

So without further ado， let's start to solve some problems。 And in fact。

 let's give you a pictorial mental model via which to approach really any problem in general。

 This picture， in fact， is perhaps the simplest way to describe computer science and in turn。

 problem solving any problem in the world by definition has some input like the actual problem you want to solve the whole point of problem solving is to solve that problem。

 and that therefore we'll call the output。 and the secret sauce in the middle。

 the proverbial black box is where all of the interesting hard work gets done。

 the step by step process that takes that input and turns it into output。

 And this is true really of any piece of software， any problem in life。

 you could simplify it into this mental model。 And so even if some of the topics in this course become a little more complex feels a little more sophisticated。

 rest assured that we could map it to this relatively simple model here。 So I think， though。

 we need to agree first on how we're going to represent those inputs and outputs and the spoiler of。

😡。

![](img/dcaa1408b263172f0268af819d18ac12_23.png)

![](img/dcaa1408b263172f0268af819d18ac12_24.png)

From the top of the hour is that we are just going to use binary ultimately zeros and ones。 Well。

 why is that Well， let's first rewind one step further from binary to unary。

 which is an even simpler system， a mechanism for representing information In fact。

 the simplest way I could count maybe the people in this room here would be1，2，3，4。

5 simply using my fingers， my digits， if you will， to count the number of people in the room that's uninary notation because each of my fingers in this model represents one person in the room more mathematically unary is also called base one because you only have one symbol in your alphabet。

1 digit if you will a finger and a finger and a finger a finger however many fingers you have is how high you can count in that system。

 but of course we know we're already headed to a world where computers use not not unary but binary and so in fact。

 mathematically the base system we're about to talk about is actually base2 and indeed instead of just having fingers at their disposal computers actually have zeros。



![](img/dcaa1408b263172f0268af819d18ac12_26.png)

![](img/dcaa1408b263172f0268af819d18ac12_27.png)

In ones by convention， otherwise known， of course， as binary。

 Now there's probably another term you've maybe heard of over time。 maybe not binary digit。

 but a binary digit is just literally zero or one。 you've probably heard a simplified version of that phrase bit which is binary digit for short。

 a bit is just literally a zero or one So what computers are really storing inside their memory somehow is a whole bunch of zeros and ones aka bits they're storing these bits to represent information Now what is a bit it might be a zero。

 how does a computer store a zero。 Well in any number of ways， but at the end of the day。

 how do these devices work。 Well， I go home with my laptop or phone at some point I have to charge it or plug it into the wall in order to use it that's because there's gonna to be therefore some flow of electrons that we could maybe capture or hold on to and in fact。

 maybe the simplest way to store information in binary using zeros and ones is just to leverage that very electricity So for instance。

 if there's no electricity and I'm。😡。

![](img/dcaa1408b263172f0268af819d18ac12_29.png)

![](img/dcaa1408b263172f0268af819d18ac12_30.png)

![](img/dcaa1408b263172f0268af819d18ac12_31.png)

![](img/dcaa1408b263172f0268af819d18ac12_32.png)

Not holding on to any of that electrical current。 Well， maybe we can just say， well。

 that's how we represent a zero。 We don't hang on any electricity at all as a result。

 if we were to connect this device to like a light bulb。

 the light bulb would stay off in that scenario。 So you might say in the physical world。

 you could use one light bulb to represent a zero by just keeping it off with a switch or otherwise。

 Meanwhile， though， if we want to store some piece of information besides a zero， like a one。

 why don't we just grab some of that electricity， let it flow and hang on to it。

 So in order to represent a one， we can use the metaphor of a light bulb that is on by switching it on。

 So in short， just by toggling switches in a device that's connected to some source of electricity。

 we can represent a0 or one just by turning that thing off or on。 In fact， in this room。

 I could turn all of the lights off and just claim now this room is representing a zero or if I turn all of the lights back on。

 now this room is representing a one。 It's not the best use of space。

 But maybe we could use multiple switches。And not just one main switch in order to count more higher than just 0 to 1。

 And in fact， I think that's what we might try to do here。

 Suppose that we have not just a single light bulb and in turn switch。 Or if you prefer a single bit。

 a single0 over one。 What if we have three of them at here， let me fix that， sorry。



![](img/dcaa1408b263172f0268af819d18ac12_34.png)

In fact， let's go ahead and do that。 Suppose that we want to count higher than one。 Well。

 I do think we're gonna need more light bulbs。 We're gonna need more switches。

 We're gonna need more bits， zeros and ones。 So suppose I give us as many as three。 Now。

 it would seem that I could still represent the number 0。

 by just leaving all three of these light bulbs off。 But if I want to represent now the number one。

 I could very reasonably just turn on one of those light bulbs。

 if I want to represent the number of two。 Well， I go ahead and flip the switch and turn on two of those light bulbs。

 And if I want to count to3， I can just turn on a third switch and turn on the third of those light bulbs。

 Now this is great because I can count higher。 but this isn't really the most scalable system for representing information。

 because if I want to count to4， I need a fourth bit。 if I want to count to5， I need a fifth bit，6。

 a sixth bit and so forth， that doesn't feel very efficient。 And in fact。

 when I look at this screen here， having studied computer science in the past。

 I can actually claim that I can count even with three light bulbs。



![](img/dcaa1408b263172f0268af819d18ac12_36.png)

![](img/dcaa1408b263172f0268af819d18ac12_37.png)

Much higher than 3 alone。 In fact， I could count as high as I'll claim 7，0，1，2，3，4，5，6，7。

 using these exact same three light bulbs。 But I think what I need to do is not just turn them on in any order and count the total number of bulbs on。

 I need to permute them in some way， Take into account that is which of the light bulbs is on and when。

 So what do I mean by that。 Well， let's start over let's turn all of the light bulbs off。

 And I'll claim again that in this scenario， we are now representing the number you and I know as 0。

 Now， if I turn on one light bulb。 I'll claim that this is how a computer would represent one。

Fairly intuitive and no different from what I've done before。

 Let me go ahead and claim that I could turn on this light bulb。

 But now I'm gonna claim that this is the number two， even though only one light bulb is on。 Well。

 let me turn on a second light bulb。 Now， I'm gonna claim that this is how a computer would represent 3。

Not two。 Let me go ahead and turn on this and only this light bulb and claim this is how a computer would represent four。

😡，5，6。 and here now is 7。 So I can represent， in fact， a total of 8 different numbers，0，1，2，3，4，5，6。

7， simply by using these three light bulbs。 Now， how in the world did I come up with those patterns。

 Well， you and I are familiar with actually a similar system。

 even though we probably don't think about it day to day in form of light bulbs。

 you and I actually use everyday base 10， where you actually have 10 digits in your vocabulary，0，1，2。

3，4，5，6，7，8，9， so much higher， of course， than just 0 or 1。

 And there's 10 of those total 0 through 9。 That， of course， is the socalled decimal system。

 Dec implying 10， because again， you have 0 through 9 at your disposal。 Well。

 how do we represent numbers in our normal everyday lives using the decimal system。 Well。

 let me put forth3 digits on the screen here。 Here are three digits，3 symbols 1，2，3。

 But all of us at glancing at these probably immediately think to ourselves。



![](img/dcaa1408b263172f0268af819d18ac12_39.png)

![](img/dcaa1408b263172f0268af819d18ac12_40.png)

![](img/dcaa1408b263172f0268af819d18ac12_41.png)

123 it's just completely intuitive after all these years of schooling。

 But why is this pattern of three symbols left or right，1，2。

3 actually representing information like 123 Well， all of us even though we probably don't think about numbers in this way since grade school know or recall that this rightmost column is generally known as the one's place or the one's column the1s place。

 the hundreds place and therefore the position of each of these symbols impliesly some sort of magnitude because this is 100 times1。

 this is 10 times2， this is1 times3 which gives me now， of course， 100 plus 20 plus3 oh。

 that's why we get back to 123， and that's why we don't say 1，2，3。

 we say 123 because the positions of each of these symbols means a little something to us。Alright。

 so that's hopefully quite familiar。 whether you use 1，2，3，4，5，6 or any other set of digits。

 But how though， is a computer getting away with just zeros and ones and no twos，3s，4s，5，6 is，7s。

8 or 9s。 Well， it turns out it uses a very similar approach ever so slightly tweaked。

 So here's just some generic placeholders for three digits。

Per the number signs here in the ones column， the1s column and the hundreds column here， that。

 though， notice mathematically， just so happens to work out to be 10 to the zeroth power。

 10 to the 1，10 to the  two。😡，Okay， and notice the 10 now we're in the decimal system still deck implying 10。

 So the base here is indeed base 10。 but the exponent varies by the position or column that you're in。

 Meanwhile， the binary system by implying two because it only uses zeros and ones simply has a different base。

 Thus， base 2， but those exponents are the same2 to the 0，2 to the1，2 to the two。

 if you do out that math。 you， of course， get one's column， two's column and four's column。

 Meanwhile， I could keep going。 I could get the eighths column 16s，32，64，128。

 and I could go on infinite。

![](img/dcaa1408b263172f0268af819d18ac12_43.png)

![](img/dcaa1408b263172f0268af819d18ac12_44.png)

But we'll keep it simple now with just these three placeholders for now。 So this then 0，0，0， or off。

 off， off， if you will， is how a computer would represent the number you and I know as 0。 Meanwhile。

 if I go ahead and turn on one of these light bulbs。 Which heck。

 why don't I go ahead and do for real here I have one light bulb here， I have two more。

Let me go ahead and start with them all off as we have on the screen here。

 Here now are three physical objects that are representing the number you and I know as0。

 How do I represent the number one， Well， I dare say all I have to do is flip on one of these light bulbs as by flipping a switch holding on to a bit of electricity and voila。

 now I'm storing0，0，1 from your left to your right0，0，1。 Now， the one， of course。

 the light bulb that's on is in the one's place。 So if we do out the math。

4 times 0 plus2 times 0 plus1 times 1 gives us the number you and I know as one。

 How about now what pattern should I use to represent the number2。

 I don't want to just turn on this light bulb here。 I want to， in fact。

 turn off this light bulb here， because I'm using base 2。

 Now I have equivalently a one only in the middle column。

 So I have four times 0 plus2 times 1 plus1 times 0。 Of course that gives me2。

This pattern of light bulbs， this pattern of bits， zeros and ones， if you will。

 represents the number you and I know as 2。 And we can continue to do this either by flipping light switches or pictorially here。

0，1，1， which is indeed pronounced on rare occasion when you have to pronounce binary 0，1。

1 and not 11， as we would in our human world。 This is4 times 0 plus 2 times 1 plus 1 times 1。

 which gives me 3。This， meanwhile， is4。

![](img/dcaa1408b263172f0268af819d18ac12_46.png)

This， meanwhile， is 5。 This， meanwhile， is 6。 And then lastly， how do I represent 7？ Well。

 in that case， all three light bulbs would be on。All three bits would be。All three bits would be one。

 in which case， four times1 plus two times1 plus1 times1 That's where I get the7。 So in this case。

 simply by using three light bulbs or three bits， simply by turning them on in some order。

 therefore representing some pattern， I can represent any number of numbers。

 at least up to a certain point。 and then a certain point when you're using just three bits here is 8 possibilities for the mathematically curious that happens to be two to the third power。

 but I can't represent with just three bits， the number 8 I can only represent8 total patterns。

 the largest one being 7， if I start counting from0。 But how could I represent the number 8。 Well。

 if I kept drawing on the board here， I'd have eventually in8 place。 and in fact。

 if I give myself another bit a little bit more hardware， more light bulb more switch， I can。

 in fact， count to the number 8。 Now as a curious side effect。

 if you don't have four bits at your disposal。 and maybe this is a really old computer。



![](img/dcaa1408b263172f0268af819d18ac12_48.png)

![](img/dcaa1408b263172f0268af819d18ac12_49.png)

![](img/dcaa1408b263172f0268af819d18ac12_50.png)

that could only store three bits worth of information。

 you might actually accidentally when counting from0 to8。

 wrap back around to zero because if you don't have that third bit and it's supposed to be there。

 you might actually confuse what you're storing in the computer's memory by just storing those last three bits instead and we've seen this multiple times over the years。

 more on this down the line in this course and beyond the Y2k problem for those familiar。

 there's another one on the horizon in the year 2038， but more on that， I think another time。😡。



![](img/dcaa1408b263172f0268af819d18ac12_52.png)

Now it is not。Can we stop you hereSure？Sure。We'll take a short break and be back。Re。2。Now。

 having just three bits is not all that useful。 And in fact。

 it tends to be more useful to use bits in increments of8。 And in fact。

 if you've ever heard the phrase byte， perhaps in the context of kilobyte mebyte， gigabbyte。

 even terabte， you're actually referring to units of 8 Bs。 So one byte is 8 bit。 Now。

 among the upsides of talking in terms of bytes instead of bits alone is that we can solve another problem。

 In fact， already。 For instance， here are 8 bits， all 0。

 And I've included for now the column values just so that if you're so inclined。

 you can do a bit of quick math。 Now， nicely enough，0，0，0，0，0，0，0。

0 represents the number you and I know in the real world as 0 because no matter how many of those columns you multiply out。

 you're still going end up with 0。 Meanwhile， if we flip all of those bits to ones。

 as by turning on 8 light bulbs， then that's going be a little more complicated math。 In fact。

 just as intellectual exercise does anyone。

![](img/dcaa1408b263172f0268af819d18ac12_54.png)

Want to conjecture just how high you can count using 8 B once you flip them all to one like this。

You don't have to just kind of guess you could do the math like 1。

28 times 1 plus 64 times 1 plus 32 times 1。 Well， if you do what the math， you're gonna get。Spoiler。

255。 Now， why is that， Well， you could actually cheat a little bit and do two to the eighth power similar to how I propose we do two to the third power earlier。

 which gave us eight possibilities。 If you do two to the eighth power that gives you 256 possibilities。

 But again as before， if we start counting from 0， then we can only count as high as in this case。

255。 Now， in this course and really in computer science in general。

 we're not going to dwell on arithmetic like this， These numbers are useful only inofar as they tend to occur a lot in different context and different areas of computer science as well as technology more generally。

 So for now， know that increments of bytes tend to be quite useful。 So， in fact。

 let's consider how we might solve a problem beyond numbers alone。

 How might a computer represent information like letters of the alphabet。

 say the English alphabet for the sake of discussion。 Well， at the end of the day。

 all a computer has is zeros and ones， whether implemented in light bulbs like these here or maybe。

More realistically， using tiny little switches known as transistors。 In fact。

 today's computers have millions of transistors， which means they can store millions of bit and in turn。

 lots of bytes underneath the hood。 so to speak。 But that only would seem thus far to give us the ability to express numbers by just permuting those bits on and off and counting from 0 to 1 to 2 to 3 on all the way up。



![](img/dcaa1408b263172f0268af819d18ac12_56.png)

![](img/dcaa1408b263172f0268af819d18ac12_57.png)

To 255 or even beyond。But if that's all we have at our disposal。

 it turns out this is where I dare say computer science actually starts to feel maybe more accessible。

 maybe a little simpler than you might have thought， because at the end of the day。

 If all you have is this vocabulary of numbers。 Well。

 that's gonna be the solution to like every problem。 In fact。

 why don't we just agree to represent the letter a in English with who knows some pattern of zeros and ones that if you do out the math represents。

 say this pattern here，0，1，0，0，0，0，0，1。 Why， we'll see why in just a moment。

 But this pattern of 8 Bs， that is1 by could represent if we want the letter a in uppercase。 Now。

 what is this number， we can do some quicker math。 Now，1，28 times0。

 I don't need to do the multiplication of the zeros。 In fact， 64 times 1 plus 1 times1 gives me。

 of course，65。 And this is indeed how decades ago， a bunch of humans sitting in a room essentially decided to represent the capital letter a in English。



![](img/dcaa1408b263172f0268af819d18ac12_59.png)

![](img/dcaa1408b263172f0268af819d18ac12_60.png)

ing the decimal number 65 or equivalently the pattern of 8 or technically 7 early on， but nowadays。

8 bits that ultimately gives you the number 65。 Now， thankfully。

 they did something pretty reasonable and decided that you know what。

 let's go ahead and represent the letter B in uppercase as 66， the letter C as 67。 And in fact。

 they came up with a whole system known as ASI。 the American standard code for information interchange。

 which is a big which is a mouthful to say， but really just represents a mapping of numbers to letters。

65 to a 66 to B 67 to C and so forth。 In fact， here is a whole ASI chart， if you will。

 of the original mapping。 And if we focus on maybe the middle column over here。 Sure enough。

65 is a 66 is B 67 is C72 is H 73 is I。 and then there's a bunch of others as well for punctuation and other symbols as well as some weird things that are really control characters so to speak that the computer understands。

 even if we humans， most of us。

![](img/dcaa1408b263172f0268af819d18ac12_62.png)

![](img/dcaa1408b263172f0268af819d18ac12_63.png)

![](img/dcaa1408b263172f0268af819d18ac12_64.png)

Don't need to know or worry about those。 So let's try a little exercise here。

 Here is a pattern of three Bs on the screen。Each of which if we did out the math。

 could be said to represent a specific number in decimal， for instance。

 if I do out the math and I sort of do it mentally and I kind of know where this is going。

 but I could do out the math here。 This is the 128th place， the 64's place。

 the 32's place and so forth。 you two could do out the math。

 I dare say that this pattern of three bys， or in this case。

24 total bits is going to give me the decimal number 72。😡，73 and 33。Hopefully。

 that lines up with whatever mental math or paper pencil math you were about to do。

 because now the question is， if you indeed receive a text message an email。

 a letter using this encoding somehow， some pattern of zeros and ones that got that text message or email or document to you what was the message you received。

 It would seem to be a three letter message or three character message more generally。

 and let's take a look at that cheat sheet。 Well， I got 72。 So that's H。 I got a 73。

 So that's I okay I think I know where this is going。 H， but what's the third character。 Well。

 we got a look to the left here this is a very excited。

 hi H exclamation point in all caps is indeed what message I seem to have received。 So indeed。

 literally right now。 if you text your best friend or family member Hi H exclamation point。

 your phone somehow is sending 72，73，33 as some pattern that we just saw of zeros and ones wireless。



![](img/dcaa1408b263172f0268af819d18ac12_66.png)

![](img/dcaa1408b263172f0268af819d18ac12_67.png)

Or otherwise to the recipient's device。 And because your device and their device supports ASI。

 this original mapping from letters to numbers， they see the exact same message that you have sent on your end。

 Now， of course。This only gives us the ability to express so many characters， the Hs， the I。

 There's a bit of an English bias， certainly in the American standard code for information interchange。

 And it turns out that8 Bs or 1 B and technically early on。

 only 7 B was not really nearly enough possible patterns to represent all human languages in the world。

 Indeed， I can think of accented characters， various Asian characters that you just don't have enough room to represent。

 if you only give me 7 or 8 Bs total to permute in some way。 In fact。

256 total possibilities is not that high for all of the human languages in the world。

 So I dare say if we want to represent not just what you'd see on a US English keyboard。

 but accented characters like these or heck emoji like these that are omnipresent nowadays。

 we're going need more patterns of  zeros and ones than just 256 total more than single bys and frankly。

 more than ASci was designed to support。 And so thus was born。Different mapping known as Uniicode。

 where a different group of people got into a room and decided ASI is no longer sufficient because we have all of these other humans in the world who would like to be able to communicate digitally as well。

 I think we're going to need to build upon the ASci system and make what turned out to be Uniicode a superet thereof。

 So it turns out in the world of Uniicode， the end of the day。

 it's still just a mapping of numbers to letters， but using more bits as needed。 In fact。

 in Uniiccode， rather than only use， say，8 bits per character。

 you might instead use 16 bits for some characters。 you might use 24 B。

 you might use as many as 32 Bs for some characters， which gives you many， many。

 many more possible patterns of zeros and ones。 Now， thankfully。

 the folks who designed Uniiccode did indeed make it a super set of ASciI so that a is still 65。

 B is still 66 and so forth。 Now， though we just have more bits at our disposal to represent even more characters。

 So， for instance， as a fun at home exercise。😊，Any want to guess？In their mind。

 what this pattern of zeros and ones is trying to say。It's quite a few zeros in ones。

 There's no gaps in between them。 So this isn't three or four different characters。

 This now is one big character， if you will。 I'll save us some time and do out the math。

 If you were to multiply all of the column placeholders by the zeros and ones in there。

 You'd actually get 4 million3， sorry。You'd actually get 436991106。 Now。

 what the heck is that when we started counting originally at 65。 Well。

 it turns out that this is the pattern of zeros and ones。 And in turn。

 number that a bunch of humans decided shall represent a face。Damn it。



![](img/dcaa1408b263172f0268af819d18ac12_69.png)

How do I fix this？Now， what does this number represent？ Well。

 this is the number that a bunch of humans decided shall represent a face with tears of joy。

 And in fact， what we know as emojis， which are certainly pictures on the screen。

 are technically characters， even though we see them as pictures， We're seeing this picture。

 for instance， on an iPhone or a Mac， because Apple has designed their software in such a way that when they see that pattern of zeros and ones。

 they show you this picture。 By contrast， if you send that same message to someone who has an Android device。

 for instance， Well， Google， the designers of Android have decided to represent a face with tearsers of Jo ever so slightly differently。

 So whereas this is the ios and Mac O version in that world， this is the Google version instead。

 And some companies nowadays， have decided to take subit of liberty when it comes to interpreting what the formal definitions are of some of these UniIode characters for emoji in particular。

 such that on telegram， for instance， you might actually get an animated face with tears of joy。😊。



![](img/dcaa1408b263172f0268af819d18ac12_71.png)

But what's being sent to you in that text message， for instance。

 is just that pattern of zeros and ones and the display of it is actually up to the recipient。

 And so as an aside， this has actually caused potential problems over the years because if two different companies。

 two different organizations interpret the definition of these emoji characters differently。

 Well it might not only just look different， it might convey a different meaning。 In fact， years ago。

 it was decided by one company then more and then more to change the implementation of the pistol emoji from being a proper gun to a water pistol instead。

 and you can imagine the dichotomy between sender and recipient if they're on different platforms interpreting that same pattern of zeros and ones differently。

 the image itself might not actually appear the same。

 and there's other examples of this since there will certainly be more examples of this in time。

 but emoji and Unicode more broadly are particularly striking insofar as the aspiration of Uniode itself as an organization。

A consortium is to be able to represent digitally all current， past and future human languages。

 And indeed， these emoji playfully as they might seem at a glance are a wonderfully interesting way of transcending specific human languages and representing people。

 places， things， emotions in a way that doesn't require even understanding one particular human language as well。

 Well， as he continues to laugh at me here， let's move on to now how else we might solve another problem at this point in time。

 we've been able to represent zeros and ones with our light bulbs or switches。

 we've been able to transition from there to represent letters of the alphabet。

 And so how now might we solve yet another problem。 And that is。

 how do you know if don't want to do that。😊。

![](img/dcaa1408b263172f0268af819d18ac12_73.png)

Let me fix that one here。嗯。Okay。Let's transition to now。Still laughing at me I was over here。

Let's transition now to solving another problem with these same zeros in ones when it comes to images and pictures and colors。

 because thus far， we've seen how we can represent zeros and ones using those bits。

 using those light bulbs using those switches， if we abstract on top of those zeros in ones。

 we can just agree on a system like ASI or more recently Uniicode that allows us to interpret those same patterns of zeros and ones。

 not as numbers per se， but as letters of an alphabe， be it English or something else。

 Well what if we want to paint a picture with a computer and store an image。

 whether it's a gif or ping or Jpeg or other graphical format with which you might be familiar。

 well we need to decide using the same zeros in oneands， how to store every color of the rainbow。

 if you will， so that the computer can store that pattern in its memory to represent some colors。

 And in fact， one of the most common ways for storing colors inside of a computer like some of the yellow that composes that there emoji is something called RGB red。

 green blue because。

![](img/dcaa1408b263172f0268af819d18ac12_75.png)

ur out we can， in fact， represent every color of the rainbow by mixing together a bit of red。

 a bit of green， a bit of blue in different amount。

 And that can give me everything from black to white and every color in between。 Now。

 how might this work， Well， suppose that we wanted to watch a movie back when I was growing up in a classroom。

 you might actually have SAT behind or in front of this year type of projector。 In fact。

 all these years later， I can still remember in a classroom in grade school sort leaning up against the projector feeling the warmth of the air coming out of it。

 because this was a behemoth of a device that was projecting some amount of red。

 some amount of green and some amount of blue color onto the screen And so long as those lenses were perfectly aligned so that every one of those circles lines up perfectly on the wall or projector screen。

 you would see a TV show or movie whatever it was the teacher was displaying by mixing together in appropriate quantities。

 some amount of red green and blue in turn。 Well， it turns out this is very commonly how computers too。

😊。

![](img/dcaa1408b263172f0268af819d18ac12_77.png)

informationformation digitally nowadays， even if they're not projecting it out with something as old school as this。

 In fact， if we were to take those same three numbers as before，72，73 and 33。

 which recall were bys worth of information，8 bit。 So 24 in total， we could instead interpret them。

 not as numbers， not even as letters like H exclamation point。

 we could reinterpret those 3 bys as simply representing some amount of red， some amount of green。

 some amount of blue。 Now， how much of each of those。 Well。

 if each of these values is represented with a byte or 8 Bs and two to the  eighth power， I said。

 is 256， which means we can count from 0 to 255， it would seem that like 72 is kind of in the middle of that range。

73 is kind of in the middle of that range，33 is toward the lower end of that range。

 So I feel like this is a medium amount of red， medium amount of green and a little bit of blue mixed together。

 So if I indeed try to view these bits using not。

![](img/dcaa1408b263172f0268af819d18ac12_79.png)

![](img/dcaa1408b263172f0268af819d18ac12_80.png)

Not a text messaging program， but Photoshop or some graphical program。 You know what。

 I'm gonna see combined into one dot on the screen， this amount of red， this amount of green。

 this amount of blue， such as if you combine those all， in this particular case。

 I'm going get a single dot on the screen that is roughly this shade of yellow。 And in fact。

 you probably seen at some point， be it on your phone or computer screen or even TV， tiny。

 tiny little dots called pixels。 And each of those pixels or dots takes on a specific color。

 And whenever you see an image of photograph， a TV show， a film on the screen。

 what you're seeing are thousands， if not millions of tiny little dots。

 each taking on a certain color， maybe for a split second。

 which is painting that picture on the screen。 In fact， later today， if you'd like。

 you can try looking up close at your phone or some other device。

 and you may very well see the tiny little dots or squares they compose that screen。 Nowadays。

 in fairness hardware is getting so good and so advanced and so expensive that those dots are so。😊。



![](img/dcaa1408b263172f0268af819d18ac12_82.png)

![](img/dcaa1408b263172f0268af819d18ac12_83.png)

Aarn close together。 it's increasingly hard to see them。 But they are， in fact， there。 So， in fact。

 when we consider an image like this emoji， which again。

 underneath the hood is just a pattern of bits， zeros and ones that Google and Apple and others are displaying to you pictorially because they support Uniicode that mapping from numbers to characters。

 Well， let's zoom in on this， let's zoom on this once more。 And in fact。

 if you do this in most any program that supports graphics。

 you'll eventually see the dots on the screen， because I've zoom zoom zoomed in in this case。

 which is to say that every one of these dots， be it a solid yellow or a closer shade of orange or brown here is storing or rather is being represented as a color using typically3 Bs。

 some amount of red， some amount of green， some amount of blue。 So using 24 Bs per dot。 In fact。

 what people describe this is therefore， is 24 B color and using 24 bits。

 you can actually represent millions of different colors。



![](img/dcaa1408b263172f0268af819d18ac12_85.png)

For each of these bits， which gives you much more precision and much finer control over the colors。

 Now I keep saying bits of course， each of these three bytes now is 24 bits。 and of course。

 if you've ever downloaded a file， taken a photograph uploaded an image。

 you probably know that nowadays we typically calculate the size of image in megaytes and the size of videos and gigabytes。

 well that just speaks to how many millions or even billions of bytes and in turn bits compose the image or the movie that you're in fact looking at。

 So this image might very well have megabytes in total of pixels and in turn color information just to store something like a smiley face or in the real world。

 maybe something like a photograph from outdoors。 Now how do represent a video。 Well。

 if you think back also to your childhood and at least mine。

 you might recall flipbooks like these and these flip bookss or tiny little books that you use your thumbs to sort flip through the pages。

Pretty quickly， like one page per second or even faster than that。

 And because your eyes were seeing a whole bunch of pictures quickly。

 it was creating the illusion of motion。 And in fact。

 the picture book would sort of tell a story almost in video form。 That's， in fact。

 how today's modern videos work and really films back in the day。

 whereby you're just seeing a whole bunch of frames a whole bunch of pictures again and again。

 maybe 24 of them per second， maybe 30 of them per second， nowadays。

 maybe 60 of those frames per second， which is technically still just a sequence of images。

 But you and I and our eyes and brains perceive it really as fluid motion and back in the day。

 these things were indeed called motion pictures。 They're still just pictures flying across the screen。

 but creating， of course， the illusion of motion to our own eyes。 And so indeed。

 you might think in simplest form of a video as just being 30 images，60 images， thousands of images。

 each on the screen for a split second， but each of those images。😊，To thousands。

 if not millions of pixels。 and therefore， amounts of red， green and blue。 Now， as an aside。

 there are many different ways to represent images and videos。

 there are different formats that use different mathematics to gain efficiency。

 So you don't have to literally store every frame from a movie as an outright picture。

 But for in simplest form。 And for some file formats， this is literally how it's implemented。

 And indeed， at the end of the day， like I proposed before， if we only have zeros and ones。

 this is the only possible way， really， that we can represent even more sophisticated things because our vocabulary ultimately consists solely of those zeros and ones。



![](img/dcaa1408b263172f0268af819d18ac12_87.png)

Now， videos often have music and music certainly can stand alone。

 How might we represent musical notes。 Well， here too。

 there's a bunch of different ways in the real world， but in simplest form。

 I think we just try and need to agree as a society。

 what number represents the musical note A and B and C， what number represents a sharp or a flat。

 Now the pitch of the note is maybe not sufficient。 So maybe we don't just need one number per note。

 we should probably use a second number， maybe a second bite to represent the volume of a note。

 like how hard you're hitting the physical keyboard in order to make that sound。

 and maybe just the pitch and the volume aren't quite enough to express music。

 Certainly the most melodic of music， maybe we instead also need a third number to represent the duration of each note。

 like how long my finger is on the key on the keyboard。 So with those three numbers， I dare say。

 we could probably play a little tune like this， simply by teaching the computer programming it。

what pitch to play based on the numbers it's seeing inside of the file or the music that you've somehow downloaded。

😡。

![](img/dcaa1408b263172f0268af819d18ac12_89.png)

So at this point， allow me to stipulate that we clearly have ways of representing information at the end of the day today's computers typically use binary zeros and ones。

 and at the end of the day， we're leveraging electricity and tiny little switches to turn things on and off and to store patterns of zeros and ones in simplest form to recap those zeros and ones can represent numbers that was pretty straightforward once at least you knew what base you were using we can even represent letters so long as the world sort of comes together in an agreement as to what numbers represent what letters and we can represent colors。

 if we do the same， we can represent videos， if we do the same， we can represent music。

 if we do the same， but there too， to my comment earlier about file formats among the reasons we have so many different file formats for documents for images for videos for music is because reasonable people will disagree and different people。

 different companies different organizations will decide， no。

 our representation of this information is better than someone else's。

 therefore you should use our file form。And not someone else's nowadays， of course。

 most any program you use can often when you go to the file menu in open。

 can often open different file format。 and that's in the interest of compatibility。

 But at the end of the day， what a file is on your computer or you're on your phone is just a whole bunch of zeros and ones stored somehow electronically。

 and inside of those zeros and ones are patterns that represent maybe numbers， maybe letters。

 maybe colors， maybe images， maybe music， maybe video。

 But what depending on what program you're using those same patterns might be interpreted differently and in fact。

 as per our example with 72，73，33， you might perceive that as numbers。

 if you open a file containing those 24 bits in a spreadsheet program like Microsoft Excel。

 you might see letters of the alphabet though if you try to open that same pattern of 24 bits using something like Microsoft Word you might see something different。

 if you open that same pattern of 24 bits using Photoshop。

Or Quick time player or any number of other pieces of software。 And in practice。

 you're not going to open such tiny files that they only contain 24 bits。

 oddds are they'll contain thousands of bits， millions of bits， billion of bits。

 But the context matters when viewing those zeros and ones。 And indeed， at the end of the day。

 it's all zeros and ones。 But you see and perceive and hear differently based on what software you're using。

 And some humans， some company has written that software to support those particular patterns of zeros and ones。

Alright， so again， let me stipulate that we have a way to represent information as per the low levell details that we've talked about here to a higher level from bits all the way up to now video and music。

 Let's now focus on this proverbial black box when it comes to solving problems and computer science more broadly。

 we can now represent our inputs in some way using binary or whatever。

 we can represent our outputs in that same way， how do we actually convert our inputs to outputs。

 Well for this in the world of computer science and problem solving more broadly。

 We need what would call algorithms。 algorithmrims is a phrase that sort of everywhere these days in computing。

 It's really just stepbystep instructions for solving some problem。

 And those stepbystep instructions can be in English or any human language。

 it could be implemented in code instead， whether it's in languages like C， C plus plus Java。

 Javascript or any number of other programming languages that will touch on in some detail later in the course。

 and indeed， code is just an implementation。😊。

![](img/dcaa1408b263172f0268af819d18ac12_91.png)

Of an algorithm in a way that a computer can understand。

 And one such algorithm might be looking someone up in a phone book。 In fact。

 here is an icon that I might have on my phone。 And if I tap on that icon， I see all of my contacts。

 my address book， all of my family and friends and colleagues， names， numbers， nowadays。

 email addresses and home addresses and other information as well。

 But it's really just a collection of minimally names and say numbers for the sake of discussion。

 In fact， it's really just a modern incarnation of this here old technology， namely a phone book。

 And in fact， I tried to find the biggest phone book I could。

 but they're getting smaller and they're getting a lot harder to find。

 But back in the day around the time I was sitting under the warmth of that RGB projector。

 This was the technology we had for looking up names and in turn numbers。

 We had the people whose names started with a at the beginning of this here phone book。

 people whose names started with Z at the end of this phone book。

 which is sort of obvious as that might be now， it's exactly how our phones are implemented as well。

 But the numbers。😊。

![](img/dcaa1408b263172f0268af819d18ac12_93.png)

![](img/dcaa1408b263172f0268af819d18ac12_94.png)

Names are stored instead using zeros and ones underneath the computer or the hood of the phone？

 Allright， so with that said， how might we look someone up， For instance， John Harvard。

 if I were to tap on his name in my phone or search via autocomp。

 I might see something like this like for your phone number。 In fact。

 you're welcome to call or even text message， John at this here number。

 If though I wanted to find John Harvard in this phone book， how would I go about that， And in turn。

 how does my phone actually go about finding John Harvard the same Because it's so darn fast in a phone nowadays。

 whether you have tens of friends and family or hundreds or thousands。

 it's pretty darn fast today's autocomplete， But it turns out it's probably not doing it in the most obvious simplistic way。

 You could certainly imagine starting at the a names looking at the B's， the Cs。

 the D' all the way down to the Js for John Harvard。

 if at least it's sorted by first name instead of last for the sake of discussion。

 And I could actually take that approach with this here physical phone book。 Here's my algorithm。



![](img/dcaa1408b263172f0268af819d18ac12_96.png)

step by step， I'm gonna look at the first page。 Look for John Harvard。 if I don't see him。

 I'm gonna turn the page。 I'm gonna repeat。 I'm gonna repeat。 I'm gonna repeat。

 So if this phone book here has maybe like 1000 very thin pages， it might take me in the worst case。

1000 page turns to find John Harvard。 But I do dare say that this algorithm。

 this step by step process for solving this problem is indeed correct。

 it's sort of stupidly slow because I'm nowhere close to John Harvard yet。

 even though I've turned all of these pages， but it is correct。

 because so long as I pay attention and look for John Harvard on each page， if he's here。

 I will find him if slowly。 right， well， what can I do that's a little more intelligent and a little more efficient than that。

 Well， I could start the same way。 But I might go 2，4，6，8，1012 and so forth。

 I could go two pages at a time。 Now is that algorithm step by step， correct。Not really。

 because I could get unlucky。 And at some point， John Harvard might very well be sandwiched between two pages。

 And I'm just gonna blow past that and miss some。 Now。

 do I have to throw out that algorithm because I was kind of liking the sound of it， it's 2，4，6，8。

 I mean， it literally is and sounds twice as fast。 But I don't have to throw out that algorithm entirely。

 Why don't I just look down。 And if I ever get past the J section。

 thus having passed John Harvard alphabetically sorted by first name in this story。

 I can just go back one page， because if he was， in fact， sandwich between okay， fine。

 it's twice as fast plus one extra step。 And if this phone book has 1000 pages。

 That first algorithm could take me as many as 1000 steps。

 this second algorithm might take me 500 steps。 Okay， maybe 501 steps。

 if I have to double back as soon as I pass him。 That's pretty darn good。 That second algorithm。

 That's twice as fast， give or take。 But that's probably not what our phone is doing to search larger and larger sets of data。

 That's not even what you and I probably。Did back in the day or mom and dad or grandpa and grandma or beyond what instead we probably did was open the phone book roughly to the middle here。

 And， of course， if I'm looking down at the middle of the phone book。

 I'm not gonna to see John Harvard most likely， I'm gonna to see like the M section at which point I realized darn it。

 I've gone too far。 But what do I know about John Harvard's position in this here phone book。 Well。

 here's what I'm seeing。 And John Harvard at this point is where to the left or to the right。

 John starting with J。 It's clearly to the left， if I've open to the M section。

 And so what I can do here is actually literally and figuratively tear this problem in half throw half of the problem away。

 that does not contain John Harvard， because I know that the J names are in this half。 Now。

 what's compelling about this if unnecessarily dramatic。

 is that I've whhitled down1000 page problem in just one step to 500 pages。 Now。

 I might open roughly to the middle of this remaining phone book。 And I went too far。

 Now I'm in say the E section of names。But I now know that John Harvard， if these are the eases。

 is to the right。 so I can again tear this problem partially away。 And again。

 in half throwing now this half away a through E because I know John Harvard starting with J must be in this portion of the book。

 and I can do that again。 I can do that again， I can do that again。

 dividing and conquering so to speak until John Harvard is hopefully on the one and final page that I've torn that phone book into。

 Now， this is not actually how we used phone books back in the day。 And in fact。

 this is why they're so hard to find because we keep doing this with them。

 But this phone book does represent how we might solve a problem more efficiently by using the third and final algorithm instead of those first two。

 Why Well， in the first case， again， if we're searching for someone。

 maybe their name doesn't start with J， it starts with Z at the end of the English alphabet might take as many as1000 steps to get to the thousand0th page in the book。

 Well， the second algorithm might take 500 steps。 plus one 500 and1 steps。is much faster。

 But what about this third and final algorithm where I divided and conquerd again and again and again。

 there's actually a binary aspect to that in that in that I'm tearing the phone book in half in half and half。

 that is to say， how many times can you tear 1000 page phone book in half Well if you do it once you go from 1000 to 500。

 if you do it again， you go to 250， again，125 again， you have to start rounding。

 but we can come up with a solution to that problem。

 How many times until you get to just one page remaining starting with 1000 pages。

 it's roughly 10 steps total。 depending on how you round along the way。10 steps。 instead of 5001。

 instead of 1000， that is an order of magnitude faster。 so to speak。

 than either of those first two algorithms。 And that's， in fact。

 exactly what Google and Apple and others have implemented in your phones and our laptops in our desktops to search not just address books like these。

 but large amounts of information more generally。 And in fact。



![](img/dcaa1408b263172f0268af819d18ac12_98.png)

are even more sophisticated algorithms out there， step by step instructions for solving other problems that are even faster and more sophisticated than these perhaps。

😡。

![](img/dcaa1408b263172f0268af819d18ac12_100.png)

So once we have John Harvard， and quite quickly， too。

 how can we think about how much faster that was。 I rattled off some numbers here。

 but let's see if we can't appreciate the implications of this longer term。

 So here's a very abstract picture of math， if you will。

 where I've got an X Y plane where on the X axis， I've got the size of the problem。

 So over here would mean small problem over here would mean big problem， So to speak。

 down here on the y axis would be little time to solve up here on the y axis would be a lot of time to solve。

 So how could we plot the relationship between the size of the problem and the time required to solve that problem in the context of this year phone book。

 Well， here is a slope of N， if you will， N just representing a number。 And in fact。

 that's the goto variable name， if you will， for many computer scientists when they just need a number like N here And so that's a one to one relationship。

 Why， because if someone moves to town next year， that phone book is gonna have one more name in it。



![](img/dcaa1408b263172f0268af819d18ac12_102.png)

![](img/dcaa1408b263172f0268af819d18ac12_103.png)

W of people move to town。 It's gonna have one more page， one more page， one more page。

 So there's a one to one relationship， if you will。

 between the size of the problem and the amount of time it might take to solve。

 because one more page means I might have to turn one more page using that first algorithm step by step by step。

 one page at a time。 The second algorithm was， in fact， faster。

 but it's still actually a straight line， because it might take me roughly n divided by two steps。

 It might not be exactly and divided by two in the worst case。

 but because I might have to double back that one page， at least， but it's still a straight line。

 because if the phone book maybe doubles in size next year。

 it's gonna take me not twice as many steps， but 50% more steps。That's not the right way to say that。

 damn it。Sorry， it's still a straight。 Let's do it from here。It's still a straight line。

 but the slope is now n divided by two because I was going two pages at a time。 Now。

 it might not be precisely n divided by two because I might have to double back that one page。

 but it's indeed still a straight line because there's a one to two relationship now between the number of pages there' in。

 And how quickly I'm going， I don't like that either， sorry。stop and。Okay。Now， this oh， did。

 did I say the slope of the line is N。Alright， I don't think so。 So。

 but I was coming dangerously close to that with the yellow line。Now。

 the second algorithm might be represented with this yellow line here。

 which is still a straight line， but it does capture the fact that that algorithm was faster。 Why。

 well， let's consider some specific size of problem。 So if we have 1000 pages。

 maybe represent here with this dotted line。 The first algorithm in red is going take this much time over here。

 The second algorithm， though， because I was going two pages at a time， does strictly take less time。

 it's going to take this much time， half as much time， give or take for that doubling back。

 But the third and final algorithm whereby I was dividing the phone book in half。

 and then the half and half， and then half of the half in half is fundamentally faster。

 And if we were to draw a picture of it， it would look a little something like this。

Let me fix that again， I forgot about this line here， sorry。Now。

 the second algorithm is still a straight line， but it is ultimately faster than the first algorithm as follows。

 noticeice here that if we pick a size of the problem， for instance。

 if this line here represents1000 pages here in dots。 Well， the first algorithm。

 wherein I was going one page at a time would take this much time be it in pages or seconds or minutes or whatever our unit of measure is。

 But the second algorithm might only take this many steps。

 roughly half give or take based on whether we have to double back or not。

 And so the yellow line here， the second algorithm。

 where I went two pages at a time is definitely faster。 But the third and final algorithm。

 whereby I was dividing the phone book in half。 and then the half and half and the half of the half in half is fundamentally faster。

 And in fact， if we were to draw the same relationship between size and time。

 we would actually see this green line represented here is a logarith and log based two of is the way that mathematically could capture the fact that that problem is decaying exponentially。

 It's going from big。To have to have to have to have。 That's a much faster solution there， too。

 And what's powerful about this third and final algorithm is that notice。

 even if that phone book gets twice as big。 For instance。

 maybe the towns of Cambridge and Al in Massachusetts。

 which Harvard has buildings in both were to combine their phone books such that one year。

 the phone book has 1000 pages。 And the next year， the phone book has 2000 pages for both towns。

 Well， that's going put the size of the problem like way out here。

 but based on the apparent slope of this line， which is no longer a straight line。

 it's not going to take that much more time， even if the problem is way out here， why。

 because no big deal， if the phone book suddenly has 2000 pages using that third algorithm， fine。

 I tear it in half one more time。 not 500 more times。 and certainly not 1000 more times。

 And so in computer science and in the study of algorithms in particular is thought processes like this。

 How can we solve our problem， not just correctly， but more efficiently。

 and what makes one companies or one persons。m better than another might very well be that that a person's algorithm takes less time or as we'll see maybe uses less space or maybe uses some less of some other resource and in fact。

 algorithms not only solve problems but can be compared in this way。

 even without getting into the weeds of specific numbers but with broad strokes， if you will。

 and in fact， this notation which hintset something called asymptotic notation。

 is how theoreticians would typically argue that one algorithm is better than or worse then or about the same as other algorithm by really trying to capture how that algorithm behaves not for small little problems like phone books like these。

 but when you have millions of pages in the problem， billions。

 trillions when n gets large is when algorithms really get interesting。😡，Okay， let me。

We're almost done。Now， what's the connection between these algorithms and maybe the code that software engineers And sorry。

Now， what's the connection between these algorithms and the programs that software engineers write。

 Well， last time， falling off the horseair。

![](img/dcaa1408b263172f0268af819d18ac12_105.png)

![](img/dcaa1408b263172f0268af819d18ac12_106.png)

Now， what's the connection between algorithms in this theoretical sense and the very practical work that a programmer does will code be it written in C。

 C plus plus Java， jascript or any number of other languages in the real world。

 is just a translation of algorithms again， to code or in turn language that the computer itself understand。

 because until we had AI， computers didn't really understand English per se。

 certainly not to the extent that they suddenly seem to let's not do thats getting to current。😡。



![](img/dcaa1408b263172f0268af819d18ac12_108.png)

One more time。Now， what's the connection between these algorithms and the programs that people write well。

Sorry。Okay。Now why is computer science and with it algorithm so intertwined with programming and software engineering in the real world。

 well code that programmers write is really just in translation of algorithms into a language that a computer itself understands and that language might be C or C++ Java。

 Javascript or any number of other languages as well。

 but for today let's give you a taste of code in the sense of pseudocode。

 which has no formal definition but which is just a terse succinct way of expressing your thoughts step by step in the form of an algorithm using English or whatever your human language is。

 that is to say when writing pseudocode， there's no one way to write it。

 but it's meant to be succinct and terse but ideally as precise as possible nonetheless。

 so for instance， what might have been the pseudocode via which I was searching for John Harvard in that phone book using the third and final algorithm put another way if I wanted to tell someone else how to do exactly that algorithm。

😡，Or tell a robot to do just that。 Or to write software that my phone could understand like Google and Apple。

 How could I translate my idea， that algorithm into step by step instructions。 Well。

 I could do this any number of ways。 But let me propose that the first thing I did with that phone book was I picked it up。



![](img/dcaa1408b263172f0268af819d18ac12_110.png)

The second thing I did was I opened to the middle of the phone book。

 The next thing I did was looked at a page。 and then I asked myself a question。

 If the person I'm looking for， John Harvard， for instance， is on the page。

 then I did something specific。 I would have called that person。 Of course， in my exercise。

 I didn't find John Harvard first， I kept looking。 So I might have asked myself another question。

 else， if person is earlier in the book to the left。 so to speak。

 then I didn't try to calling them yet。 Instead， I opened to the middle of the left half of the book。

But if that wasn't the case either， and oh， damn it。嗯。好吗。And then how can we fix this？Just look up。

 okay。O I would open to the middle of the left half of the phone book。

 and then I could go back to step 3。😡，Sorry。Open to the middle of the left half of the book。

 And then I could go back to line 3。 Why， because in line 3。

 Im already have instructions via which to look for John now that I have opened to the middle of the left half of the book but suppose that John weren't in fact to the left but the person I'm looking for is to the right later in the book Well then I would do almost the same。

 I would open to the middle of the right half of the book， and then I would go back to line3。

 because line3 would get me ready to look for John or anyone else step by step again but there's a fourth and final scenario to consider if John is not on the page or earlier or later。

 because maybe I've divided the thing in half so many times that I'm at the last page and he's not there。

 there's a fourth and final scenario which I dare say should be else just go ahead and quit because if he's not there or to the left or to the right。

 logically it must be the case that John Harbert is not there so Id better handle that situation。😡。

step by step2。 And this is actually a key detail。 Even though this is pseudocode for a very real world algorithm or process。

 it turns out that forgetting about or not realizing that some other scenario could happen is a common source for today's problems in software。

 In fact， if your own Mac or PC or phone has ever frozen or maybe a spinning beach ball persists forever or maybe it reboots or turns off entirely。

 it's possible that that is the result of some human at whatever company wrote that software。

 having forgotten， oh my gosh， what if the person is not even in the phone book。

 we'd better tell the device what to do in that case because if you don't tell the device what to do step by step。

 maybe the behavior is just undetermined。 And so it freezes， it hangs。

 it reboots because it doesn't know what else to do because you have not told it the correct step。

So if we assume now that this is complete， let's see if we can't glean some first principles here in some terminology as well。

 via which we can solve not just this problem， but others as well。

 there are some key characteristics of how I've written my pseudocode here。 and in fact。

 in English specifically that will guide our solutions to future problems as well。

 whether it's an English or actual code。 For instance， notice that in some of these lines here。

 there are verbs or a calls to action， if you will。 Pick up open to look at call。

 open to open to and quit。 Well， those verbs in the world of computing have a term of art associated with them。

 namely functions borrowed by from mathematics， whereby a function is an action or verb that tells you or the robot or the computer to do something specific。

 So any of these actions can be now described in the world of computing as functions herein。😡。

These terms here， if elsetif， elsetzif elset represent what a computer scientist and any programmer would call a conditional。

 These are forks in the road， so to speak， that you take only based on the answer to some question。

 you either go this way or this way or this way or this way。

 if it's a multiple directions you can go based on the answer to some question。😡，For instance。

 if the person is on the page or the person is earlier in the book or the person is later in the book。

 you will decide whether to go here， here， here or here instead。 else。

 as is the semantics means sort of a catch all。 If none of the answers to those questions are yes or true。

 so to speak， at least there's that fourth and final catch all that just says quit。

 But these highlighted expressions， these questions to which the answers must be yes or no。

 or true or false or heck 1 or0， if you will， are generally known as Boolean expressions named after mathematician bull and a boolean expression has just that an answer that is either true or false。

 yes or no， or the like。 And so using these building blocks， can we capture my stepby step logic。

 but recall that I also had some savings whereby this algorithm didn't keep looking for John。

 Keep looking for John， Keep looking for John by having dozens or hundreds of lines， Rather。

 I told my。Solf in some cases， to go back to go back to another line so that I could reuse code that I had already written。

 And this too is a key principle of computing is to not repeat yourself。

 Idely keeping things simple so that you don't have to enumerate again and again and again。

 Turn the page。 Turn the page， Go left， go right， you can say at once and then reuse。

 so to speak the code that you've already written。 And so highlighted here or what we might call in computing loops。

 a way of inducing some kind of cycle that hopefully is not infinite。 Hopefully eventually。

 we stop doing this， Otherwise， you might get the equivalent of a spinning beach ball。

 But rather in this case， I don't think we will， because on every iteration of this loop。

 if you will。 I am presumably calling the person or quitting or。Dividing the problem in half。

 So even though I might do this again and again and again。

 and each of those iterations up till the last， I'm making the problem smaller and smaller and smaller。

 and ultimately， that persons either gonna be on the page or I can simply quit。 Now， as an aside。

 Sometimes infinite loops are good。 your phone， your computer typically has a clock that you can look at the current time。

 Hopefully the clock is implemented with some kind of infinite loop so that it always tells you the time and doesn't just stop when the clock strikes midnight。

 It loops back around and does it again。 So infinite loops can be good can be bad。

 but loops are one construct that we can leverage when translating algorithms into actual code。

 or in this case， pseudocode functions are the actions we can take conditionals can guide which direction we go in the Boolean expressions is how we might decide which path to take when we encounter that fork in the road。

So along this path， then we've come up with a way to represent information， along this path。

 we've come up with a way of processing information， looking up John Harvard。 and indeed。

 in the lectures to come we'll begin to build upon these building blocks， these first principles。

 if you will， spending not much time at all on binary and zeros are ones anymore， because in fact。

 after today， we can really abstract on top of that lowlevel detail。

 we can assume that all of us know that even if we get rusty eventually and how it's done。

 that computers can represent not just numbers， but letters and colors and images and videos and music and more。

 And so as we proceed in the course will build upon this knowledge so that in the real world。

 can you encounter not only problems like these， but yet others using the same first principles to solve the very new。

We'll see you next time。So we now have a way to represent information。

 We've seen ways bio which we can process information。

 But these are techniques now that will mostly take for granted。 Indeed， per the top of the class。

 willll begin to abstract。 let's fix that again， sorry。So we now have ways to represent information。

 We now have ways to process information。 And I dare say we can now take for granted that we can do both of those。

 In fact， here on out， in the lectures to come， we're gonna take for granted that we can represent letters and we can represent images and videos and music and more。

 simply by abstracting on top of these underlying implementation details。 And indeed。

 among our goals for the coming weeks， using first principles as to how systems work We'll be able to reason through new problems that we encounter that might very well be similar to past problems。

 but themselves new so that we can apply these lessons learned to all problems。

 technical and non using such。Pri this is just words now。One sec。 might have to stick with the first。

OK。So we now have ways to represent information。 We now have ways to process information and moving forward。

 I dare say we can take for granted that we can do both of those。 In fact， after this lecture。

 we're not going to talk about binary all that much。

 we're going take for granted that computers do store information using zeros and ones。

 we're going to take for granted that we can agree on a system to represent letters and colors and images and videos and music and more but we can abstract away from those implementation details so that we can solve problems of greater interest to us。

 In fact， among the goals for studying these first principles of computing。

 is that when we encounter problem in the real world， be it in or outside of computer science。

 we can apply some of these lessons learned to and unfamiliar problems alike and indeed at the end of the day I dare say that's the value of computer science is the applicability of these ideas and these skills to other domains so that even if you are not a computer person yourself。

 you can bring to bear lessons learned from classes like these to the world。Do the sciences so close？

Last time。Should have just stuck the landing and kept。Here we go。Okay， Max。So we now have a way to。

Okay。Ad to the next slide。Take a step forward。One more。

Just as well that none of the other takes were good。So we now have a way to represent information。

 We now have a way to process information。 But here on out。

 I think we're gonna take for granted that we can do both of those。 In fact。

 we're not going talk very frequently about how we can store information in binary。

 We're gonna take for granted that computers can do so。

 And we're gonna abstract away from that implementation detail。 We're， okay。

 let's go with the first take， which was much better。Okay， yes， was it the first time， okay。

I mean you。Actually， yeah， let's try this once morecause there's one point。 Sorry that I think say。

Yeah， alright， let's try once more。Ready， Max？So we now have ways to represent information。

 We now have ways to process information。 But I dare say here on out。

 we can sort of take for granted that we can store information and process information in these ways。

 In fact， we'll take for granted。😡，I lost my。Flow。And one last time。On you。

So we now have ways to represent information。 We now have ways to process information。

 And I think we're now going to abstract on top of those primitives。 In fact。

 we'll take for granted that the computers can store information in binary。 And on top of that。

 we can represent letters and colors and images and videos and music and more so that we can begin to solve quite quickly。

 higher level problems， if you will。 And those problems themselves won't always be in computer science itself。

 In fact， I dare say the value of computer science is its applicability to fields beyond。

 So whether you intend to bring to bear the lessons learned of this class， to the arts， Humanities。

 social sciences， physical sciences， Natural sciences are beyond， you'll have an opportunity。I know。

 that was good。Okay， I gotta keep it shorter。Okay， here we go。

So we now have ways to represent information。 We have ways to process information。

 So I think we can take for granted that we can do both。 In fact。

 we're not going to talk about the lower level details of binary here on out， all that often。

 We're just going stipulate that computers can do so。

 And we're gonna take for granted that we can abstract way on top of those zeros and ones to represent things like letters and colors and images and videos and music and more。

 And ultimately， use some of these first principles to solve higher level problems of interest to us。

 and those problems don't have to be within computer science。 Indeed。

 odds are you yourself come from the arts， Humanities， social sciences， natural sciences are beyond。

 and what's nice about computer science。 I it sheer applicability to those and other fields。 In fact。

 the lessons learned from classes like these should empower you to bring to bear the principles of and the skills from computer science to solve problems of interest to you in your own domain。

 So all that and more。 We'll see you next time。That was good。

 Can we make note to keep that one or the first one。Thank you all。Oh， yes。

 for those of you still with us。 Thank you so much。 And especially。

 thank you for bearing with me as I went off the rails there at the end。

 This was the first of our live streams again for the new and improved version of C S50 business to be retitled。

 We'll be back tomorrow at 9 AM Eastern time for Colton's third lecture for C S 52D。

 the two dimensional gaming course。 If you'd like to find the Zoom and YouTube URLs for those head to C S 50 dot L Y slash Zoom。

 Hope we you can join us for those as well as next week's lectures as well。 See you soon。😊。



![](img/dcaa1408b263172f0268af819d18ac12_112.png)

![](img/dcaa1408b263172f0268af819d18ac12_113.png)