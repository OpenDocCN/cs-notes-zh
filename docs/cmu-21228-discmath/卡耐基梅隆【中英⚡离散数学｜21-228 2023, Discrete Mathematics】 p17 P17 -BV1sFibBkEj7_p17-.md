# 卡耐基梅隆【中英⚡离散数学｜21-228 2023, Discrete Mathematics】 p17 P17 -BV1sFibBkEj7_p17-

Recording in progress。

![](img/e1f757e643c3f9a93753fde730dd95c1_1.png)

Hello， everyone。 How are you。Good， let's do this。Okay， well， happy Friday。

 I guess it's already Friday。 And it's also we're getting close to halfway through the semester。

 My understanding is that next Friday is the day off。 Is that right。 I think so。 So that's。

 that's scary。 That means it's getting close to the end。 Also。

 I guess the other way I know it's getting close to the end is it's getting warm enough to wear short sleeve shirts。

 Although that seems to be also correlated with climate change， which is maybe not a good thing。

 Anyway， so we're going continue talking about interesting ways that we can go about trying to solve recurrences。

 although I'm going to take a little step， a little bit of field。

 And the first thing we're going to talk about， is's gonna look a little bit different。 Okay。

 so this is just a super cool fact that I want to talk about。😊。



![](img/e1f757e643c3f9a93753fde730dd95c1_3.png)

Does anyone know what happens if you take。1， divided by 89。Well。

 I guess I need a calculator for that。 Let's go and the calculator。 This is my nearest calculator。

1 divided by 89。 I wonder if Ill be able to get enough digits just a second。😊，开门。

My phone is too slow。Let's go。 So one divided by 89。Oh， okay， I found it。

 So let me tell you what it is as a decimal。 It's a point。0，1，1，2，3。5。Isn't this awesome，11235。No。

 you ruined it already， Chris， What did you say， Oh， the next one's a 9。 Oh， okay， I'm sorry。

 So it's not if， it's not。 It's not any good。 It's 5，9，5。5， and then what is that，0，6。 All right。

 All right， All right， So we were all excited for a moment that it might be something like Fibonacci numbers。

 but it's not。 It point。 It's 1，1，2，3，5。 And what did you really want。😊，You really wanted eight。

 didn't you。That would have made us happy。Okay， suppose I got it。 What would I want after it。Right。

13。H1 plus 8。It's9。That's satisfying。 What do I want after 13。8 plus 13 is 21。嗯。3 plus 2 is 5。

It works。 This is amazing。 So you see， there really was something going on here。 After all。

 it's actually just Fibonacches， but you had to like， you know， mash numbers together。

 Is everyone with me。 Do you all believe me at this point。😊，You know， I've。

 I've done the small cases。 I've done like up to 7 or something。 So it must be true。Bll， what's next。

13 plus 21 is 34。 Oh， oh。All right， it broke。I mean， it's too good to be true， right。

 so there's no way this thing could be true。Because you see， the problem is 1 plus 3 is not 5。

Actually， it gets even worse。 What's after 34，21 plus 34 is 55。4 plus 5 is not0 either。

 so it's like totally and utterly broken。Anyone know what's after 55。89。Wait a second。

 You know what's going happen when you add the five into the8。When you add the five and the8。

 there's going to be a carry。HaAnd then now that carry the one， the4 and the 5。 That's 10。 Oh。

 look at that。 That matches。😊，And furthermore，10 gives me another carry。😊，Bam， it all works。Okay。

 so at this point， hopefully you believe me that something very interesting is going on with this one over 89。

 And I mean， the reason， by the way， has nothing to do with the fact that that is 89。

 which is also a Fibonacci number。 That is a pure coincidence。

1 over a Fibonacci number does not just give you this Fibonacci decimal。 But this is super cool。

 And it actually works in the sense that if you just keep going and going and going。

 And you just like always carry in the right way， you're actually going to recover this decimal on top。

 which is unbelievable。😊，The first time I learned this， by the way。

 was when I was teaching a Putnam class at CMU， and one of the students said， hey， didn't you know。

 there's this like one over 89 thing you can use。And I was like。

 what do you mean this one over 89 thing， And they did it， And and it was like this。 And I was like。

 no， no， no， this can't possibly be true。But okay， so why is this， Why is this true。

 Let's go and attempt to prove this， Okay， what， but what does prove this mean。

 Prove this means we need to write down some formula about Fibonacches for which the answer comes out to1 over 89。

 Let's remember。 So， of course， now you see it's related to Fibonacches， as we should have expected。

 So Fibonacches。 remember we start with F 0 is equal to 0， F 1 is equal to 1。

 F 2 is equal to 2 and so on。That's the Fibonatches。Okay， so I guess a question I have is。

 can anyone try to rewrite the right hand side？What's the right hand side？In terms of Fs。

We might have to write things in terms of F's and how can I write all of this as an infinite sum。

 by the way， about Fs。Anyone have any ideas。 So let's get some different people here， Andrew。

You could like multiply each Fibonacci number by like a corresponding power of 10。 Okay， I'll do。

 I'll do a divide just because it's easier for me to write。 but it's the same as what you said。

 Can you help me out。 So is' F 0 divided by a power of 10 plus F1 divided by a power of 10。Okay。

 what are the power of 10 I should use So the first one would be just 10 and then you would want 10 squared。

And then you keep going。Over 10 cubed and so on。Okay。

 so I think my real goal is to attempt to prove that this sum of Fibonacches over powers of1s。

 I'd love to prove that that's one over 89。 Do I any hope of doing this。 Let's try。 Okay。

 so I'm going to rewrite onto the next screen。 Just this simple sum of F 0 over 10 to the 1 plus F。

 F something over 10 to the next thing is what I'm going to write。 Okay， I just need more space。

 So I do it on the next screen。😊，Your goal。Is to show。F 0 over 10 to the1。Plus， F1 over 10 squared。

 plus F2 over 10 cubed。Plus， all the way is equal to one over 89。Now， how could I do this？ Well。

 I don't know much about Fibonaccies。 I know that the small ones。 I know what they are。

 but I don't really know what the big ones are。 Like I can't tell you what is F 50 million。 I mean。

 I could， if I tried very hard， maybe with this nice formula we had found。

 But what I do know about Fibonacciches is I could make them out of the previous ones。 actually。

 there was a funny joke I saw online a few weeks ago， which said it was like it was a cafeteria。

 It was like some school cafeteria， and it said that today's menu。

 the special soup of the day is called Fibonacci soup。

 What we did is we took yesterday's soups leftovers。

 And day before yesterday's soups leftovers and we mixed them together。

 and that's called Fibonacci soup。 I thought that was quite funny。 actually where I went to college。

 sometimes when you went to eat dinner， it'd be like what did the chef just make。

 It looks like what was leftover from yesterday remixed。😊，Anyway， that's called the fried rice。Okay。

 let's， let's continue。 So， so so， now， now if you， if you， if you go on here。

 nothing against fried rice， by the way， fried rice is a fantastic dish。 Okay， continuing this thing。

 let's， lets， let's， let's go and say， suppose that this thing is called X。 Okay。

 let's just let the left hand side be called X。😊，Okay， let， oh， do I want to use yeah， Why not。

 Let's use x for now， Big capital x equals this sum。 That sum。 I just don't want to write it again。

 I's that sum， okay。But now I want to go and use， yeah。

 I want to go and use some idea of like what to do。 And what。 you had your hand up。

 Did you want to do something Yeah， so from F 2 onwards。 what if we use the recurrence and split it。

 Allright， let's try that。 So I' if we can， I don't know， recover some weird version of X。 Yes， yes。

 yes， yes， So again， as you can see， actually I was chatting with somebody about how I teach my classes and about notation。

 like guy was called black pan red pen。 I don't know if any of you guys watch this thing。

 So we did some random live stream earlier this week on Tuesday。

 And what I explained is I just don't do notation。 I just write dot dot dots and hunt for patterns preferably after7 terms。

 And so if you do this， then you can just like C stuff， right， So let's's split things apart。

 What's f2。 Well， I can break F2 F2 breaks into F 1 plus f 0， just like that Subbonacci soup thing。

 So it's gonna be an F 0 overops10 cubed。😊，I'm going to use columns to do this。

 And the second one is plus F1 over 10 cubed。Okay， and the next thing。

 I will use F1 over 10 to the fourth。And the second column I'll write plus F2 over 10 to the fourth。

 And I'm going to pause here just to take stock of what I've written because I want it all to make sense。

So what have I actually achieved， I just went。 And， I mean， there's dot， dot， dot。

 more stuff is being added。 But I just copied the first two。

 because I don't know how to take apart the first two Fibonacches。 On the other hand。

 I have this F 2， which I can take apart into F 0 plus F1， which is what I did。

 And I kept the same denominator， which was 10 cubed。 The next term would have been F 3。

 which I will take apart into F 1 plus F 2 over the same denominator。

 So I've aligned everything like vertically。😊，Is this okay so far。Yeah。

 and just to get a nice pattern， I'm just going emphasize the next one is going to be plus F 2 over 10 to the power 5。

 And then itll be plus an F 3。Over the 10 to the power 5。And we keep going。Okay。Now what。 Well。

 Advvi said it would be great if I could recognize some X stuff in there。

 The thing that's scary is dot， dot， dots。 dot dot dots。 I don't know what they are。

 but I know how to add like three things together。 You just add them。 Can anyone see a way till like。

 circle a bunch of stuff here and say， I see X， Bradden。😊，Well， the top row。

 we can see we have the F0， F1 and F2 in the terms that we have an x。

 except now we're divided by 10 to the power of 2 additionally， Yeah。

10 it's like the normal x divided by 10 to the power2。

 It's an extra210s right It's because what happened is I would normally have done x iss just f0 over 10 to the 1。

 and then F1 over 10 to the square 10 squared and then F2 over 10 cubed。

 And when you write out enough stuff you just see the pattern。

 it's like it's just off by two factors of 10。 So that's x over 10 squared。That actually is very。

 very exciting because then there's no more dot， dot dot。 I can just be like， forget， dot， dot。

 dot there。 What else Subbashi。 Oh， no， we can say that again。 What， what are you gonna say。😊，Oh。

 I just meant like that's only justified if we know that some converges。 I mean。

 I think we do because the top is like quadratic and the bottom is exponential。

 but it's I was just saying like dividing and using that in any algebra is justified only if the sum convers。

 Yeah yeah， yeah yeah。 So you actually jumped ahead to punch line。 I was gonna make in a little bit。

 which is cool。 I'm glad you said that So what we're gonna do in this class is like we' we don't know what convergence means。

 So actually what I'm gonna say is like I was okay using some ideas for matrices to talk about the previous section。

 if you want to do everything we're doing in this new section rigorously。

 you actually need to understand convergence。 And that's a class usually not taken until later in a college career。

 It's usually taught in a class called real analysis or complex analysis。

 And so what I will do for the rest of this section is we'll just do weird stuff。 and we'll be like。

 yeah， sometimes it convergs sometimes it doesn't。 but that's beyond the scope of this class。

 Okay And superbas yes， it's not。😊，dratic is actually exponential。

 but the base of the exponential is small enough。 That's why it's okay。 But in any cases， all right。

 we're just going to view like on this， on this level， alright。

And that's actually why I went and showed the algebra， the linear algebra part first。

 Because that part is like absolutely rigorous。 Nobody has any questions about dot dot dots。

 We didn't have any。 We just had to do like multiplying matrices。 Here we have dot dot dots。

 And that's more mathematically sophisticated。 How about the second one。

 Can anyone help me fix the the blue stuff。 I still have dot dot dots here。

 I would love to be able to rewrite this blue line。 in something that has X involved。😊，Anyone else？

 I w， I want to make sure a lot of people are understanding this。

 because this is what we're doing here is the heart of the next part of the section that we're talking about。

 just with like some very explicit numbers。😊，It's sort of like X， but not really。it saying。

I'm not sure about this， but it's like x minus like f0 over1 squared。Okay， yes， so you said it X。

Minus。You lost the first term。 Okay， F 0 over 10 to the 1。 That's there。 We lost that term。

 But then we need to do more division。Is10 Yeah， over 10 square。 Yeah， here， I will actually say。

 I'm not sure I want 10 squared。 I'm looking at this carefully。 I'm like。😊。

Look at the powers I've got normally with the x， the F2 divides by 10 cubed。

 And here my F2 divides by 10 to the fourth。So I only， yeah， it's okay。

 It's just like it's a pattern thing， right， So it's like， I'm only off by one factor of 10。

 except I also lost the first time。Okay。By the way， what's app 0。F 0 is 0。 Okay。

 that's very convenient。 Okay right， F 0 just happens to be 0。

 This is is not what this is not what always happens。 But in this particular case with Fibonacches。

 F 0 equals 0。For Fibonacci。Okay， so since F 0 equals 0 for Fibonacci。 now I have。

 I have an equation I can write dot X equals。 Okay。

 so what I just found out is that x equals x over 10 squared。 Oh let's use the colors。

 Let's match the colors。😊，Alright， so I have X。Equals。Yellow x over 10 squared。

 I'm just gonna call x over 100。And then， plus。It's just plain blue X over 10。Wait。

 what just happened。Oh， no， I Im， I forgot some terms because otherwise I got x equals 0。

 That's really bad。 Okay， so， so there's some terms in front。 There's actually some stuff in front。

 I forgot， I'm gonna erase this and write some green F 0 over 10 to the 1。 That was 0 over 10。😊，Plus。

 F1 is1 over 100。Okay， and then I write the yellow part plus x over 100。

And then I have plus x over 10。Hey， I know how to solve this equation。 There's only x。

 There's no dot dot dots， right？ So what happens。 How do I do this， Put all the x's on one side。

 So how much x is on the left side。 Well， it's1-1 over 100-1 over 10。 Many x's is equal to1 over 100。

 Sounds like a good idea to scale up by 100 on both。 So multiply both by 100。

 That's 100-1-10 x equals 1。 Look at that 89 x equals 1。 So I get that x equals 1 over 89。

 And it works。😊，So that's cool。 So this actually works。 Alright， so this is， this is very nice。

 It it's actually showing that if I ever were to write something out like this。

 I could actually go and find this， I could go and find this， this， this fraction that that is it。😊。

Okay， one thing I wanted to say that Subbashi jumped on。

 which I want to make sure we know this is slightly wonky math because we replace some dot。

 dot dot stuff。 And I'm gonna show you something that should make us very worried。 Watch， I。

 I can prove for you something。 Let。😊，Let X， here's something else。 Oh， let's call it Y。

 Y equal1 plus 2 plus 4 plus 8 plus 16 plus dot dot dot。 Okay， it's true。 And， oh， by the way。

 you know。I can rewrite this， in terms of why。Sort of like what we did last time。

 We were like that X thing that was x over 100， right？ What's that in terms of y。

Y is  one plus 2 plus 4 plus 8。 This is like， what is this， this。2 plus 4 plus 8。

 What does that have to do with why raise hand as， you already got it。 What did you want to say。Oh。

 it's just two times y。 It's2 y。 Obviously， it's2 y。 It just doubled everything， right。

 So what I just found out is that y equals1 plus 2 y， which if I solve， y equals negative  one。

 So we have just found out that the whole sum is negative 1。😊，Satisfied， actually。

 we just had this error。 know， you know， I'm working on this Novid app。

 So we're doing a lot of programming with our algorithms。 We have a lot of C plus plus code。

 And late last night， somebody was like， why are we getting all of these numbers in the output。

 which are like these massive numbers with about this many digits。

 And they're always the same number。 And I was like， I have a guess of what they were。 And you know。

 you Googled the number。 And the number that we kept getting， turned out to be2 to the power 64-1。😊。

That's because that's what happens if you have a negative one and you in C plus plus have negative one and you type cast it to an unsigned unsigned 64 B integer。

 then-1， actually， the way if you take any computer science classes。

 the way that you encode -1 in the computer is you have a binary string， which is all once。😊，Anyway。

 okay， so so in a computer， actually， if you take the sum of all of these and you do it in the wrong way。

 it is actually -1。 if that's the overflow error you get， except that when're not computers。

 the problem of why this broke is because this whole thing was infinity。 So actually， you know。

 there's two solutions to y equals 1 plus 2 y。 One of the solutions is -1。

 The other solutions is positive infinity。😊，Infinity is also one plus 2 infinity。

If you could do arithmetic with infinity， actually， so is negative infinity， that。

 that's why actually you can't do arithmetic with infinity。 That's why infinity is not a real number。

 Okay， but the bottom line of why the whole thing broke is like， it's because the thing was infinite。

 That's why Subbaishsh said， does it converge or not。 So this is just like， this is。 so you need。

To be careful。About。Convergence。Okay， and that's the reason why this whole subject that we're about to talk about is going to be a little bit weird。

 It's like， do things converge or not and。In this。Class in combinators。

 we're just going to kind of assume you can mess around with things as if they converge。

 There are theorems later that you can use to go and get that things converge。

 But I've learned that that's not worth putting into this particular course。

If you the fun part is like， if you actually get a formula at the end。

 you can always prove the formula by induction。 So in some sense。

 what we're using is when we are coming up with mechanisms to guess formulas for we were using this to solvecur recursions。

 But after you get the formulas， if you wanted to just like do it by induction at the end。

 you could for this course and for the exams is okay to just do all this stuff as if the stuff converges。

😊，The ends justify the means。 Yes， yes。 And in， in some sense。

 it's more satisfying than some of those classes which say。

 here's how you solve the differential equation。 You guess the answer。 Look， it works。😊。

This way is like， you're not really guessing the answer。 we we're doing educated guesses of like。

 if only this stuff converged。 And by the way， that's how some。

 you know maybe a few hundred years ago before mathematicians really had a good understanding of convergence。

 That's how they were coming up with crazy true formulas with like pi squared over 6 is like one over  one plus1 over 4 plus1 over 9 and and one over 16 and so on。

 Allright， Well， why did I talk about all this。 I just showed this thing to say， yes。

 so we have to be careful。 And what you saw some people murmuring in the chat is like， yes。

 you could be careful because it actually does converge。 blah， blah， blah。

 don't worry about that for this class。 Okay， instead， let's worry about， well， okay， that was nice。

 But。😊，You see， we just had the numbers run together。

 It would be really nice if we could space out the numbers more。 You know， like。

 what if instead I could try to find a way to write all of these where I have two。😊。

Place the values for each spot。So maybe I would want to write not this point 01，1，2，3，5，9。

 but I could give some more space。 I could go and say， like point 0，0，0，101，020，3，0，5，0，9，1，3。

 do you know what I mean， I could give more spaces， you could imagine that that would be reasonable。

 Hey， if I wanted to do that。 If I wanted to give myself two place values for each thing。

 What's the only thing I' would have to change。😊，If I wanted to find out what is that fraction。

 if I just want like two place values， powers of 10 a。 say again。

 So so what what would I change the powers of 10 into2。

Youd double a of bit like10 to the  two and then 10 to the 4， then 10 to the 6。 so and so forth。

 You'd use powers of 100， really。 Actually， what I've just talked about is what if we decided that we were tired of base 10 and we just felt like using base 100。

Really， the reason why this is screwing up is because we're writing all our numbers in base 10。

 And the moment the numbers get bigger than 10， they overflow the place value。

 That's why you're carrying。 And so what I'm going to do next is I'm going to say， hey。

 what if I just wanted to know in base N。 If I wanted the same thing in base N。

 what would that look like。😊，Okay， so the next question is， we got tired of base 10。

 We went to a foreign alien planet where they all work in hexadeadeimmal or something like that。

 And so what would it like what。Is the fibonnaci thing。In base。And， well， we just answered that。

 So I'm just going to write， oh， I saw a question here。 Could you like。

 adaptively increase the place value， okay， adaptively increasing the place value。

 Now that gets hard in that I actually don't think that would be rational。😊，Let， let me。

 let me go on that because that's cool。 You know， when you go back to this thing。

 we just found out that the Fibonacci thing is a rational number。

 Every rational number is a repeating decimal。😊，Isn't it cool that if you just laid out the Fibonacches like this and you did all the carrying forever。

 it repeats。😊，Like。What you you know what I mean， Like， why。

 Why would you think that writing down all the Fibonacches， doing all the carrying。

 Why on earth would it repeat， But it does， Because every fraction， if you just do the division out。

 eventually， as you divide out any rational number， it becomes a repeating decimal。

 So that's just like amazing， okay。😊，Yeah， and it got like recursive log 10 edition， perhaps。

 but it's not going to be as nice because I can't just like do this shift。

 The reason this whole thing worked is I just said， look at that yellow thing。

 That's just the old thing shifted over by two spots， but it wouldn't shift in the same nice way。

 You'd shift by different amounts of stuff。😊，Wait， is that true。Oh， yeah， yeah。 That's totally true。

 That's because that's because the problem is that the carrying even screws up。

 So the reason why this thing worked is because we were able to take the original thing and then break each Fibonacci into two parts where they were all divided by the same power of 10 on these two pieces。

 So that's how I could see shifts。 But just to， oh， raise hand， Eric。😊。

Well if you try like the matrix method from。I guess last week or like this week。

I can't exactly hear you， could you get closer？呃。We're about using like the matrix method that we werere doing this week。

The matrix method。 So these are related like this， this thing is actually related to the matrix method。

 But what do you mean by using the matrix method。😊，Okay， if you have like。

F I times like 10 to the negative I。And then like 10 to the negative i plus one， F I plus one。

And then you can multiply up by like a matrix。 and it would give you like。

10 to the negative y plus 1， F plus 1， and 10 negative y plus 2 F plus 2。Yes。

 so what you're saying is that you could actually go and write the matrices where the numbers in the matrices。

 Sorry， you， are you， oops， are you saying something where you get these kind of vector things。

 But your vector things are no longer just F and。😊，Plus1 and F N。

 But like F n plus one over a power of 10， F n over a power of 10。 Yeah Yes， that one will also work。

 And that's that because this thing happens to have all of these nice nice properties。

 So that's true。 But I'm gonna go on with this thread because I want to。

 I want to finish up this piece。 I pressed undo。 Did anything disappear。 Hopefully not。 anyway。

 Let's keep going。 So I just want to do this because we had just said this over here。

 What's the Fibonacci thing on base N。 Well， let's do it again fast。

 So it is the we have this x equals。 It would have been F 0 over n to the power 1。

 because remember the base was 10 before。 And now the base just happens to be N。😊，Plus。

 F1 over the base squared。 plus dot， dot， dot。 If you remember what's happening。

 I'm just like reviewing this thing fast。 Well， what we ended up getting is we got an x over n squared。

Right， well， maybe， maybe I should do that slowly because this is important enough that we want to。

 Well， no， no， we，'ll see that again。 So alright， this was F。 sorry， this was x over n squared。

And then there was this blue thing， which was， plus it ended up being just x over n。

Is this familiar with people。 Like， that's what we got， right， This is what we got。

 This is just like it was the， the reason why one of them is over n squared is because we ended up shifting all of the powers of 10 by two more pieces。

 We got this。 Let's put everything together。😊，And what I have here is that， you know。

 if I move everything together， I get this1 minus-1 over n squared minus-1 over n。

Times x is equal to F 0 over 0 is just  one over n squared。And what I found out is， okay。

 that's nice。 It's like one over。 If I could do this right， I'm just like simplifying everything now。

 It's n squared- n， -1。😊，That's just algebra。 I think this books。Okay。

 we don't actually need factorials here。 I'm looking。Oh factorctorial base system。

So that might be the case。 I actually， I don't know enough about these things that you're suggesting to be able to give you an answer on this spot。

 Quite possible。 I'm just， I'm just trying to raise the time to get to get to this this punch line because I want to use this to do something else before we finish today's class。

 But I'm like， okay， here， this will work。 And if you put this thing in with n equals 10。

 that's exactly one over 89。 And if you wanted to get this Fibonacci decimal thing with every two spots。

 then you just use base 100 and you just put 100 in for n。😊，But this is motivating something else。

 This， this is actually saying， you know， look at what we're actually making。

 We're making some interesting polynomials。😊，Not really polynomials， but over here。

 but I don't really mean polynomials。 I mean， it's like。

 it's F something and a power of this 10 or a power of this n， whatever that's supposed to do， right。

 I'm basically saying I've got， I've got some F's and I've got some powers of N。

 But why do we have the ends in the denominator。 It's actually better， oops。

Do you get anything interesting for base 5 possible。 Well Oh， let's， let's go and find out。

 We're gonna get some power series here。 Okay， it's like what we were doing is we were basically taking F's。

 and we were also having some。😊，Some denominators that kept getting bigger and bigger。

 But if you think about cculus and Taylor series， you usually don't put the X in the bottom。

 You put it on the same line。 So what I want to do here is I actually want to say， hey。

 let's just define something。Let， I'm gonna call it。This that looks like a funny F。

 That looks like an integral sign。 It's not an integral sign。 F of Z。 I'm using Z as my variable。

 Okay， F of Z is just going to be， it's going to be the F 0 times Z to the 0。Plus F1。

 these are all capital Fibonacches。 Z is the1 plus F2， Z squared plus F 3。Z cubed。Plus， so on。

What if I did that？This seems like a reasonable thing to do。 It looks nice， at least this looks nice。

😊，Okay。Where the digit of the I see。 Yes， yes， yes。 So let's， let's keep going here， right， So， so I。

 let's just define this， this thing。 This thing actually has。This has a nice name。

 This thing is called the generating function of the Fibonacches。This is called the generating。

Function。Okay， generating function of the Fibonacci sequence， that F， F sequence。Actually。

 what does this generating function have to do with that X？There' is a way to write X。 You know。

 this， this X thing， which is the Fibonacci number and base N。

 There is a way to rewrite this whole thing as something involving F。

Something involving with with this actually as the generating function， add。

But looks like you plugged in one over n into F and then also divided by an additional factor of N。

 Good， Okay， so let's do that slowly so。Maybe I shouldn't have written the equal sign is actually that this is equal to the top thing。

This is supposed to be an equal sign， right？ And what's going on is， you see。

 if I plug in one over n into this generating function， I will get F 0。

Over1 plus F 1 over n to the1 plus F 2 over n squared plus F 3 over n cubed。

 which is awfully like what I wanted for base N， except that what I wanted for base N is divided by another n。

 So I actually need another one over n。😊，Is that okay。

I'm basically motivating why this particular generating function is actually useful。 Actually。

 when I first learned about generating functions， people just said， hey， just do this。

 cool stuff will happen。 And then at some point， I realized you can actually explain if somebody wanted to know what does like Fibonacci decimal look like in base 572。

 it's easy。 You just put 572 into this thing。 And the generating functions is actually useful。

 And so I usually use this one over 89 to introduce the whole notion of generating functions so that I don't start by writing this thing。

 But instead of we start by solving a real curiosity，1 over 89。 And then now we discover， hey。

 this thing might be useful。 This kind of a function might be useful。😊，Well， you see。

There' is a way to get a general form for F。 What if we want to solve for this little F。

 Let's get a form for it。Can I write little F equals something a function of Z where there's no dot dot dot。

Well， I'll just do the things I've just done。 Okay， so let's try it to do again。

 what we've just done。 That's why this is like practicingrac it the moves quite a few times。

 So we get used to the moves。 Well， F of Z。Is equal to。Let's leave the first two terms。

 We don't break those apart because I don't know how to。

 I don't see any use in breaking apart F 0 or F 1。 So I'm going to have the F 0。Z to the0。Plus， F1。

Z to the one plus， now we bust this apart into two things。F 2 becomes F0 plus F1。F 0。

And these are times z squared， right？Plus， F1。And the next thing， F 3 breaks into F1 plus F2。

 So I get F1， Z cubed。And here， I get F 2。Is he cubed。Do do do。Now。

 can anyone help me use generating function stuff to go and replace the dot dot， dot stuff。I mean。

 when I say use generating function stuff， I just mean in terms of this like F thing。

 I'm going leave the F 0， Z to the0 plus the leave the F 1， Z to the1。 And now help me out。

 What's the green thing。I want to get more people involved， if possible。What's the green thing。

You can do the green thing in terms of the little F。Yes， And， And。

It should be z squared F of Z right。Yep， Z squared times F of Z。 Let's put it that way。

 That was the green thing。 How about the blue thing， Can anyone else help me with the blue thing。

 Preferably new people， if possible。said。You subtract out the first F 0 term and then divide by another Z。

 Okay， let's do this。 F of z minus the F 0 z to the0。

 I'll make a slight correction to what you did just like times only because we're doing times here instead of divide。

 but doesn't matter。 It doesn't matter。 That's the same idea， right。

 Because that's how I go and get an extra Z factor2 on everything。 Okay， well。

 now let's use the fact that for Fibonacches。 I have， I know what these are。 F 0 is 0， right。

 So for Fibonacches， I happen to know F 0 is 0。 So those are gone。And I happen to know that F1 is1。

Okay， so this thing here。Is what。Let's just write a button of it。Okay。

 so then I can write down an expression for F of Z。I know that。 F of Z。Is equal to。Just plainsy。Plus。

 z squared F of z。Plus， Z， F of Z。Now， how do you find out an expression just for F of Z。

 I have this nice equation。 F of z equals z squared z plus z squared F Z plus Z of Z。

But I want to know what is just plain F Z。How would I find out what is just plain up Z if I have this kind of an equation。

I fit。You just solve for it， move all the F of Z's away， and then divide by whatever you have to。

Yeah， so the important thing is many people aren't used to like solving an equation for F of Z as a big blob。

 which is why I wrote it inside this box。 It's a very， it'， it's an unknown。 What I mean。

 what I mean is that whatever Z happens to be。F of Z satisfies this， right？ So what if。

 if Z happened to be， for example，110th， because that's something we would care about。

110th was this thing for the Fibonacci decimal。 And so if z was110th。

 I would get that box equals 110th plus one over 100 times box plus110th times box。

 which is actually what we solved last time。 B was X。 I'm just emphasizing that box。

 you can solve for box because all the boxes are the same。

 So if I continue all the way on the on the top up here。

 What I actually have is I have something times box。 In fact， it's one minus z minus z squared。😊。

Multiped by this box。 And the box is just F of Z。 Okay， F of Z。's that's box， but that's okay。

 And that's just equal to Z。 This is true for all values of Z。 If Z is 110th， that's true。

 If z is1 over 10th， that's the I grow。I think it's okay。 Yeah， yeah， this is， this is right。 Oh。

 yeah， okay， yeah， yeah。 So so no matter what is， no matter what is the Z。

 this equation is true because down here， all I did is I just factored it out。 The。

 the one is from the one times F of Z。 And I moved everything to the left hand side。😊，Okay， well。

 if that's the case， now I have a formula， F of Z。Is equal to Z over1 minus z minus z squared。Oh。

 how nice。So now I actually can say if I wanted to know this Fibonacci decimal for base 10。

 I would just put1 10th into this thing。 I can do it。 and I just divide the answer by 10。

 Very satisfy。😊，But I want to do more than that。 I want to now use this fact。

 This is the Fibonacci generating function。 Okay， we have just found out the generating function for the Fibonacci numbers。

😊，That's the generating function for Fibonacci numbers。

 Gene function just means I take the coefficients of this big Taylor series thing。

 and every coefficient is the corresponding Fibonacci。 then that's that thing。 Now。

 why would that be useful， That'd be useful because now I can actually look at that thing and try to solve it in a different way。

 You know what， Tayloror series， If I just took the tailor series of this thing。

 I would get all of the apps， right？ And you know how to take Taylor series。

 You just take this thing。 And you differentiate and differentiate and differentiate like 50 million times。

 Who wants to differentiate this 50 million times。😊，Nobody， nobody is Its horrible。 It's horrible。

 Like whether you get like quotient rule and like big old power is absolutely terrible。 Nope。

 we are not going to do that， but we're going to do it a slightly different way。

 So what we're going to say is， hey， if I could find some other way to write this thing down。

 I could get a formula for the Fibonacches。 I wonder if there's any other way I could write this down。

 So now let me copy this thing。 and I'm going to write this as this Z over 1 minus z minus Z squared thing。

 okay。So that's like this Z over1 minus z minus z squared。Option A is to go and tailor series it。

 which we have scrapped。 That's going to be horrible。

 Option B is to look for something else we can do。I'm going to do it one way here。

 And then in some of the subsequent lectures， we'll find more and more clean ways to deal with this。

 One way is， I don't like denominators where the power of the biggest power of Z has a negative side。

 That looks weird。 So let's like the top and the bottom， multiply top and bottom by negative， okay。

 minus Z over z squared plus Z-1。 okay。😊，Hey， in cculus。

 have you ever come across like when you have something which is like a quadratic in the denominator。

 and there's like some particular tool you use， there's a certain area at one point in cculus B C in America。

 you're going to see things where you're dealing with stuff like this。

 and usually there's an integral sign or something。😊，What am I getting at。

 There's an entire area of a A thing that you might do if you have like polynomials in the denominator。

 Ray had lots of people， Nick。Partial fraction de fractions。 Yes。

 let's partial fraction decomposition thing。 I promise you'll be fun。 So what。

 what does partial fraction well you're not really sure if it' will be fun， do you。

 But let's just see why this is gonna be useful。 Okay。

 so let let's partial fraction decomposition things this thing for fun。 Well。

 it's going be something over Z minus。 Oh， I need some letters now。 Let's just call them R and S。

 Okay， Z minus R plus something over Z minus S。 But can anyone tell me。

 how would I find out what are R and S。😊，I need to put some stuff on top， too， right。

 I need to put some A and some B on top。Right， it's going be this thing。 This is partial fractions。

But if I want a partial fraction this， how do I find the R and the S Chris？

I'm just gonna go out on a limb here and say that they're fee and little fee。

 you're hoping they're gonna be fee a little fee。 Okay， that that you'， you're actually very close。

 But why how would you get them， if you， if you had to partial fraction， some nonsense like this。

 What are you supposed to， Oh， they're the solutions to that， They're the solutions to that。 Okay。

 You got to find the roots。 So how do you partial fractions this thing， Let's get the roots。

Of z squared plus z-1 equals 0。 quadratic formula tells us negative1 plus or minus the square root of B squared。

 Okay， plus so sorry，-4 A。 That becomes plus 4 all over to。

 I just threw the quadratic formula at it really quick。😊。

And I get something not quite exactly what you said， Chris。

 I get -1 plus or  the square root of 5 over 2。Now， that's not quite the same。

 it's slightly different。Slightly different this， this， like the， the the。

The phi and this like what what p -1， this， this golden ratio stuff that comes from 1 plus the square root of 5。

 This is a -1。 But we'll see soon why that y that is the case。 Okay， so I've got these other two。

 And so I should let one of them be R and one of them be S。 Okay。

 so what I'll say is like let R be-1 plus the square root of 5 over 2。

 and let S be-1 the square root of 5 over 2。😊，Okay， so now that I've gotten this。

 what should I do to get the A and the B。Oh， you know what。I think I'm gonna be， I'm gonna play lazy。

 I just can't bear。 I can't bear to find those。 Okay， that thatll be too， too too much trouble。

 There would be some A， and there would be some B。 Alright， and we could find them if we wanted to。

 And if this was actually an A P exam， you would find them out。 But they they are numbers。 A And B。

 you could find out in theory， okay。😊，Yeah， just like the， just like the matrix blob math。

 That's what we're about to do。 A And B are like some blobs。 Okay， but why is that important。

 The reason that's important is because。You know， I could maybe find the Taylor series for this A over z minus R。

 Maybe maybe that's a nice tail series。 But here's how to make it even nicer。

 The way to make that tail series even nicer is I'll continue。😊。

I'm not going to call it A And now you're going to see why I'm doing blog math。I would prefer。

To divide the top and bottom by minus R。A over minus R。Over， that's， that's eligible。 A over minus R。

Divideed by what happens if you divide the bottom by minus R。Why is this interesting。

 What happens if we divide the bottom by minus R。Bed。You get one minus z over R。

 and I think that might look like a geometric series。Yes， so I， I。

 I know how to tailor series that thing。Because the top is a blob。 Okay。

 that's why it I didn't care about the a， because I was like， oh。

 if I go through all the trouble to find a， Oh， sorry， if anyone's wondering。

 there's gonna be a plus sign。 Okay， we're not done yet。

 but I didn't bother to calculate the a because actually。

 the a is gonna end up divided by a minus R anyway。 Okay。

 so it's gonna be like blob is some number that doesn't depend on n， but。

It's nice because the bottom is gonna look like some geometric series thing。😊，Okay。

 because the geometric series thing means I'm just gonna take like。

1 plus Z over R plus the square of Z over R。 You know what I mean， is's like。

 this is the formula for an infinite infinitefin geometric series iss one plus that ratio plus the ratio squared plus the ratio cubed and so on。

 of course， multiplied by the thing on on top in front。😊，Can someone help me simplify the be。

 the beer。It's not going to be over minus R。 Tell me what to write for the B term is same。

Should it be like B over minus S。B over minus S over， Yes，1 minus。呃V Z over S。Yes，1 minus Z over S。

 okay。So now， this is interesting because。This is telling me that if I wanted to write this whole thing out。

 here's what the answer would look like。The answer would look like。If I split the two。

 I'm going to say， I'm split the two because I've got these two things added together。

 I'll write them as two different rows。 I have this thing here， which is the a over minus R。

That a looks funny。 A over minus R。Times， it's one plus。Z over R。I， actually。

 I'm gonna write it a slightly different way， One plus one over R。

Times Z plus1 over r squared times z squared plus dot dot dot。And then there's this B part。

 It's like plus B over negative S。Times 1 plus1 over S Z。Plus one over S squared Z squared plus dot。

 dot， dot。Why did I do this？I did this because。My goal was to find a nice formula for the an coefficient of that big tail series。

😊，Can anyone tell me what the n coefficient of blah， blah， blah is。 Is it nice。

 Does the n coefficient have like dot dot dots in it。

 or could I actually conceivably write down a formula for the nth coefficient。

 What's the n coefficient， and coefficient means coefficient of Z to the power N。It's nice， says a。

 Can anyone else see what that would be if I have all of this， What I get is the coefficient。😊。

Of Z to the N。What is that？Remember， on the one hand。

 the coefficient of Z to the n is n Fibonacci number。 That's why this is exciting。

 That's why the That's why this generating function is awesome。

 It's going to be the nfibonacci number。 But how do I read off from this thing to find out what's the coefficient of Z to the power。

 And I see。 we have Brandon。😊，It's gonna be like a over a negative R to the N plus one plus B over negative S to the N plus 1。

 Okay， I see what you did。 So you did a over negative R。 I'm just gonna break it apart。 Alright。

 A over negative R times one over R to the N。Actually。

 I'm going to take the one over R and then put the n here， Okay， plus。

B over negative S times1 over S to the power N。Okay， and by the way， by the way。

 that's supposed to be the N Sclebonacci number。 Okay， and this is equal to F N。Is the n coefficient。

 Sorry， F N is the coefficient of C to the N。 This is amazing。

 So that means I've just found out that for every n in the world。

 F N is whatever that a was some actual legit number。

 A over whatever that R thing is that some other legit number。😊。

What does this have to do with blog math。Does this look familiar to people？

This is totally like its blob times something to the N plus blob times something else to the N。

 And this is why when Chris was saying， Chris was saying like， you know。

 Phi and like the other thing。 And that's why I said you're really close。😊，Because actually。

 I don't want R to that。 And I won't want over R to that。What is one over R to that。 now， I need to。

 I need to reciprocal these things。 Oh， no， how do you do that， You have to reciprocal them。

 So let's see。 Well it fit here。 Let's try。 So if， if R equals this， what's。My heads in the way。

 Let's do it on the next screen。 Okay， so -1 plus root 5 over 2。 Okay。

 so R is equal to -1 plus the root of 5 over 2。 Okay， that's fine。

 Then what's1 over R 1 over R as you flip it 2 over-1 plus root 5。 That's not  phi。😊，Well。

 you rationalize the denominator。 Okay， so so whenever you have these radicals in the denominator。

 you multiply by how you rationalize this thing。 It's like  one plus root 5， right。

1 plus root 5 over one plus root 5。 And the reason you do this is because the denominator becomes a difference of squares。

 The denominator is like something minus something and then something plus something。

 And that's the difference of the squares。 So the， the answer of one over R is just two times  one plus the root of 5。

Over， well， the difference of squares is root 5 squared。 That's 5-1 squared， oh。😊，Bam， we got our。

 we got our phi。 This is the thing that Chris wanted。

 This is the root 5 plus 1 over 2 or  one plus root 5 over 2。 That's often called the phi。

 which is the golden。😊，Radio that should look very familiar。

 That's what we had last time in this Fibonacci formula。How about the other guy， S？S was-1。

- the root 5 over 2。If that's the case，1 over S is equal to2 over -1- root 5。Okay。

 now we have the times by rationalizing this guy。I don't know。Help， maybe I can do it for。啊，所以看。😊。

Negative four， negative four。Yeah， yeah。 I just w to know what to write。 Like。

 what should I multiply by like some minus we have to decide where to put the minus。 Oh。

 whatever let's just do this。 I know this will it might it might be ugly。 We might get。

 we might have put the minus in the wrong place。 Okay， I'm multiplying by one。

 But once I multiply by 1。 Then what I got on the top is twice1- root 5。

 And the bottom gives me difference of squares， which is like， yeah。

 it's negative root 5 plus1 and negative root 5-1。 That's what's going on here。😊。

A negative root 5 happens to square to 5。And I'm just writing it like this。

 Just to show you what I've done。 I have a difference of squares where I have negative root 5 plus or -1 multiplied by each other。

 And that is exactly twice 1- root 5， all over 4， which is 1 root 5， all over 2。

 which is what we had last time。😊，That's the other thing we had last time，1 minus root5 for2。

So what we have just found out， if you put everything together。

 is we just found out that the n coefficient is going to be some blob times this one plus root 5 over 2 to the power n plus some blob times 1 minus root 5 over 2 to the power n。

😊，That's what we got over there。And then you just finish the same way as before。

 If you remember before we did some matrix multiplication and when we did some matrix multiplication。

 we eventually got to this thing with a blob math。 And we said， just stick in n equals 0。

 stick in n equals 1。 And after you stick those in， you can figure out what the blobs are。😊。

So we have just found another way to derive the entire formula for the Anfibonacci number。Ed。

 do you have a question。Or comment。Oh no， I was just gonna mention the roots of that equation look really similar to that equation that we solve for those for those eigenvalues for the lambdas from the matrixes。

 Yeah， so this equation looks a lot like the one we solved for these like lambdas。

 And that's why next next class。 what I'm going to do is I'm going to show you exactly why is' actually the same equation。

 But over here to minimize the amount of times we have the twist things in our head。

 I just first took it into the partial fractions which we're used to saw some ugly things and said。

 oh， I wanted to turn those into geometric series。 those I know how to find infinite sums for。

 once you're an infinite geometric series land。 Then you realize that， oh。

 they're just going to be like blobs times powers of certain things。

 and those certain things are the reciprocals of the roots。 Bam。

 And then you just get the whole thing。 might you might wonder， what this was so fast。

 Why I didn't we just do it this way last time。 The reason is because there are certain things we did in this one where there are dot dot dots。

 And there's these like murmurs of conversionvers and like does it really work。

 And so I wanted to at least show you another one before， which yeah。😊，Definitely really works。

 This thing here is like a little bit of， yeah， if it works that way。 it looks right。

 And this is how a lot of physicists discovered a lot of good physics。 And actually， generally right。

 And so that's， that's what we're seeing here。 This is a bit more analogous to if things behave well。

 which they probably do， then we'll be able to get some heuristic and understand， you know。

 why are these the powers， Why are these the， why is this the Fibonacci number。 Alright， Well。

 welcome to generating functions。 This is what we're gonna do for the next two weeks。😊，That finishes。

than you yeah。

![](img/e1f757e643c3f9a93753fde730dd95c1_5.png)