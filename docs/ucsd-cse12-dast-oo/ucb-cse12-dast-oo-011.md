# 011：CSE 12 - Basic Data Struct & OO Design - LE -A00- - Lecture 11.zh_en - GPT中英字幕课程资源 - BV1zJQHYcE8g

![](img/1e0fac8121cdfb8504b2d95f682cfa0f_0.png)

Okay， let's， let's get started。 Sorry， a couple minutes late。There were a lot of questions from 11。

Now。What we're going to do this week is。Logistically， this week is the quiz 2。 right quiz 2。

 So please make sure you get ready for quiz 2。 quiz2 won't include runtime。 It won't include runtime。

 okay。We cover like a real linked list。 Those are the two major topics you'll see in the quiz。嗯。

And then。Did we have P3 released。I can't remember。 I think Casey should have done it， right， okay。

Good so you should be able to do everything for P 3。 And this week。

 I think our ambitious goal is to finish runtime and also try to finish hashing， which is。

 which is very ambitious but well see， Okay， but definitely I want everyone one of us to understand runtime。

 Okay， that's in my mind， one of the most important concepts we should learn from C S E 12。

So last time we were looking at runtime and saying， okay。

 if you have two different ideas or if you think about your given problem， right， your。

 your supervisor tells， tells you， hey， can you do this thing。

And then you come up with an idea and you do it。 And maybe your teammate say。

 maybe we should in the other way， right， So which way is better， Which way is better。

The easiest way is both you implement that idea and compare the runtime。 Okay。

 so that is called benchmarking， benchmarking。The the benefit of benchmarking is that's the real thing。

 right， So there's no way that you can say my， my idea benchmark better than yours。

 So we should use yours instead of mine。 right， That's normally the case。

 but benchmarking has many kind of。Variations， right。

 so what if you are just a better programmer than I am， although my idea is better。Right。

So for those kinds of situations， we， we， we sometimes resort to both benchmarking and the counting。

 In other words， I want to know how many operations my program would execute。

That is the second approach。 This is called asymptotic analysis。So it's called asympotic。

It's like you are trying to analyze。The number of operations your program would take using math。O。

The proof this approach is you don't have to code up anything。

 just look at the idea or layout to the idea and pursue the code。And you do the counting。Okay。

That's one thing。The problem with this approach is， is not real。 It's not real。 In other words。

 if you say our ideas are similar when we do the asymptootic analysis。

 we should resort to benchmarking。So when we do benchmarking， also sorry。

 when you have like a new idea， you should do both。Okay， so just in C S C 12。

 we don't have the luxury to do benchmarking as part of the P。 But I mean。

 you should always think about， okay， this， this， this thing takes like， for example。

 linear time to do something。 but another idea also take linear which idea is better。In general。

 there is always a small difference between those ideas when the input size is big enough okay。

So what we focus on in CS C12 is this thing。Okay， but I can tell you。This is probably。

Just as important， if not more important。O。So for those of who will be doing C S research。

Both of them are required， Tra CS research。So。This part， really， there's nothing I need to teach you。

 You cold it up，That's why as a C S majorator， it's important that we have the foundational coding skills。

Right，Because you must be able to write code to implement your idea。 Although C。

 S is not necessarily about。100% coding。But its an important skill。Let。

 let's look at some of the examples in here， okay。So imagine have a list of songs in here。 right。

 just， I don't care whether it's a readlist or linkedist。 let's say if this is a raylist。

 So this one is implemented as a ray and there are currently 20 songs in this place， playlist。

But you have no idea what they are。 And you just see this playlist。Just like if you have a playlist。

 you play on the car， you have no idea what the next song might be。 just says classical playlist。

You'll have no idea what the next song will be。 But you know， it there's this collection of songs。

 So if I want to know rip， this， this song。How many places do I have to look for before I can determine the location ripite or say it doesn't exist？

What's the best case scenario？Can we have a quick vote， the best case。Frequencies， A C， okay。

 frequencies， A C full participation records， our tutor Western。He， he manages the。

 the participation。 He should have uploaded the stuff from last week on canvas。

 If you have any questions， he I told him to post a piazza announcement， and then you follow up。

 and we， we'll look into that okay。Which one is the best case。

 I think this is pretty straightforward。1， right， So it's our lucky day。 say okay， that's the。

That's the thing。 The first song I'm looking at is rib。Right， that's， that's pretty straightforward。

 Now， how about the worst case， It's not necessarily my lucky day。Which one。

Is the right answer in here。Allright， so I think we have a very strong consensus， no need to discuss。

20， right。 So when does the worst case happen。When does the worst case happen？问。

That song is the last song or what。It doesn't exist， right， So that's it's not my lucky day。

 I was scanning through with the whole list。Now， in computer science， which one do I care。

 Do we count unlock luck。Probably not， right， You， you can't just pray no pedestrian in front of me。

 please， I'm driving。 You can't。 you can't say that， right， You can't rely on luck。

 So you should focus on the worst case scenario。 That's what we focus on， okay。

So one part of figuring out how long a program takes is the three cases in general。

There is the best case。 basically thats the， the situation based on the input is like it's gonna take the least amount of time possible。

 That's the best case。 now the worst case is the most amount。 You can always think about on average。

 the average case， okay， in fact， both the worst case， average case and best case。 They are useful。

 when you propose the new algorithm。 you should talk about all three cases。But in C 12， by default。

 we're gonna say we care about the worst case。Unless we say， it's。

Look at the average case or look at the best case。 If I say， what's the runtime of this thing。

 we are looking at the worst case by default。So why do we care about the worst case。

 The worst case is like the upper bound of how bad your program can be。Right， just imagine， if。

 if someone tells you， you say， I have。嗯。For example， I don't know。 So someone say you， you have a。

 you have the fix your car。And the mechanic can tell you， okay， how much does it， is it gonna cost。

The mechanic say， at most 200。You know， this upper cap。 That's the worst case。200。

Even we can tell you at least 200， you probably is gonna say it's gonna be 2000 or 20000， right。

 because even we can at least 200， that's the best case scenario。 So you， as the user of idea。

 probably would prefer the worst case estimate。Right， in the， in the context of computing， we say。

 how long would it take for your program to give me the result， I can tell you， at most2 seconds。

You can budget2 seconds。Then do something else。 If I tell you at least two seconds。

 there's no upper limit。Maybe two years。 Who knows。Right，So as， as kind of a common sense thing。

 we in general would prefer the worst case scenario。Okay， and that's what we analyze。

So what is worst case， It means given the input， you are looking at when does the worst case like。

When would it take the most amount of time for this program to finish， Because given different input。

 like what we look at that list， example， right， given different input different things you are looking for some you may maybe be lucky。

 Sometimes you will be very unlucky。 We are looking at the situation where we are very， very。

 very unlucky。 The most unlucky situation。That's the worst case。O。So。Any questions。Now， when。

 when we say we have this idea， for example， I say， look for something in this list。

Look with something in this list。When we try to kind of count the number of steps or the number of instructions that this program would execute in general after today。

 you can I， you can count ballpark estimate。But in the beginning， what we do will count every step。

 We count every step。 Okay， so if n represent the length of the list。

 and I want to look for this thing in the list， I run a for loop。And I will return to a return false。

When do I have the worst case scenario and how many steps， How many instruction is gonna run。

 So what is an instruction like this assignment is an instruction。

 This comparison is the instruction。 This I plus plus is an instruction。

 return true is the instruction， return false is an instruction。

 And then this equals call potentially can be an instruction。So overall。

 if I say the worst case runtime， can you do some math to say。Under the worst case situation。

 what's the total number of instructions we have to run before we can encounter a conclusion。 Okay。

 Ill give you some time。 Can you do this yourself or do it， do it with a neighbor。 like。

 how do you count't。Remember， we are looking at the worst case。

 assuming there are own things in this list at， at this moment。So work on the math a little bit。

If any of us need a handout， you can always come to the front and grab it。

To account your number should be the same as your neighbor's number。Should be exactly the same。Okay。

Don't tell me it's just N。 Its it's not just N。Alright， let's do the counting。 right。

 When does the worst case happen。It doesn't exist。That's the worst case。 right。

 So I know if it doesn't exist， this is。One operation， one return force will definitely be executed。

And then I'm gonna go into detail in here。 So I have to go through the whole thing。

This is one operation。 And this i 0 is only done once， right， in the for。 What's the next thing。

What's the next thing we do。Compared to n， right， this compare to the length。 So this。

Another operation was the next thing。We'll do this equals， call。And we return false。

 because by assuming it doesn't exist in the list。 What's the next thing。In Chris I。

And then this thing， this thing， this thing， and go on。 right。

 So I know there are two plus something。Right， so this operation， this operation。

 And how many times would these things run。 Is this 3 N。Is it3 N。I exactly 3 n。有。3M plus 1。

 Why is the3 n plus 1。大表の。Alright， so initially， I am just imizing， well I， I maybe off my one here。

 How do I do it， I just imagine this list has like five things。Right， so I would suffer from 0。

 And how many times do I do this comparison。 Why 0 does's a compare。Is 1， eyes 2， I 3， I 4， eyes 5。

I would have to increase to5 before I know this thing is false。Right， so。0，1，2，3，4，5。

 That's 6 comparisons。6 comparisons。 Does that make sense， So this one would run n plus one times。

Right， now how about this I plus plus。Imagine when I 0 is， is done to make it one， right。

 So 0 to one， that's one step 1，2，2，2，2，3，3，2，4，4， to 5。 So it's gonna run five times。

This thing is gonna run n times。How about this equals。Every time I is legitimate is gonna run it。

 So this is gonna be run n times。So in other words， this comparison is done。Like additional time。

 in the very end， to break you out from the for loop。嗯。3M plus  one。 So it's 3 m plus 3。

That's the total number of our patients。Right， so。Am I missing anything。Am I missing anything。

Is there anything that is missing here。Yeah。啊。this one， this takes constant time， right， So you can。

 you can look for the I element in the array very quickly。 There's a constant time。

But there is something that is missing in this line。 What is missing。嗯。How do I compare two strings？

 How do you compare two strings。Yeah， how does echos work？How do you know ABC is the same as ABC。

I need to check character by character， character by character。 compared to first letter。

 second letter， third letter， fourth letter and go on。 So the ideas， for example， if。

 if were really being peaking here， this equals is not one operation。Right。

Because imagine if I ask you to implement equals， what are gonna do。Is' the of a loop。

We implement equals。Right， unless there are other ways that you can say I， I。

 I will do something in here to， for example， hash。 but still。

 it is gonna be some sort of linear operation with respect to the size of two find。

In here we're gonna ignore it， right， But this too fine。

 if this string is like a million letter long。Good luck。Right。

 because this thing is gonna take a long time to， to to call equals。

 If every string is extremely long， others is gonna only take 3 and plus 3。

 but each equal call would take a meaning operation。Does this make sense。

 So we are ignoring this detail that is hidden in the equals call。

So there are a lot of time when you call function， as you try to run the look at the run time。

 you have to be very， very careful。 Okay， But in here， let's assume this is a nice string。

 We can ignore。😊，The length in here， then is 3 and plus 3。 We call this function。We call this linear。

So it's like a linear function with respect to M， so。The longer the list is。

 the longer it's gonna take for this thing to run， but it is proportional by a constant with respect to a。

That's a linear time。 Obviously， as you can see， there may be quadratic time。

Is caogenictic time better worse than in their time。I it going to be better or worse。Worse， right。

 It's gonna be worse because as n gets bigger and bigger， quadratic， would increase faster。

 especially this is the cost， right。 So this is the cost。Normally， this is what we do。

 You say you have the idea。 We'll count the number of patients come up with this idea and then classify。

 then classify it。 This is a linear that is a quaretic。 that is a noin andex。Any questions。有。でフに。

Why do we have to ignore。 we don't have to ignore。 Like in a real application case。

 you should think about this， right， So how long does it take， This thing probably is gonna take。

 assuming that this two find is about the same size as each of the element in the list。

 So this thing is probably is not gonna be n， but n times the length of to find。 for example。

So depending on how。How long to find this。RightSo there is a constant factor a surgery data。

 But in this example， we assume is。Neegligable here， just。So we don't complicate things too much。

 But in reality， we should。O， okay。嗯。And， this kind of。Story is， I mean it's very common。

 It's very common in practice。 One of my tutors。 remember when we try to do some research on like how cars drive。

 We got some data from the insurance company， They say， like。

 can you classify the driving patterns for different people like during the weather。

 the weather event， the zip code and the， I think also as the age of the the driver as well as the gender of the the driver。

 So you know， a lot of demographic information of the driver say， can you classify them。

 And that's what we were doing。 And what thing we need to know is the weather。

What's the weather on that day， right They give us the time。 And， you know that online。

 there are many better servers。 You， you， you， you carry them with a date。

 and then they will tell you the weather。 And that's what that student did。

 I would carry on that server And then come back。 And her code was very clean， very nice。

 And there was just a function call to that server。😊，And it take us so long。

 We can't get any result at all。 After running it on the superconmunal center for a few days。

 we don't get anything back。 And obviously， there is something wrong。

 And we were timing the code and was one of that function cause to the server。 that server cat。

 How many things you can do per second And we have just have to wait。

 We count waiting for that server to give us the weather data。 in the end。

 we just decide to grab all the data from that server and do it locally。 and then it is very quick。

 So when you do a function call， you have to be very careful。

You can't assume that function call just one。You can't assume that。Are we good。第二。This one。Yeah。

 you don't have this too fine。This is I。 This is a， this is like， how do I get it。

 The I element of ray。It takes a con amount of time。As for how。

 how many is a multiplication and addition。 that's about it。So the question is， like。

 should I count the access to this thing as like maybe it takes two times right。

 take two operations to do it instead of one。 technically， you can think I plus plus。

 you have to go to that about increase by one， then save the result back in in here。This。

 we treat this whole thing as one operation。 one operation。 So if I want to treat that too， fine。

 there， there's no big deal I want to look at it in more in fine detail。 That's fine， too， okay。嗯。

And that's why sometimes we will say do plus plus I instead I plus plus plus plus I is slightly faster。

 than I plus plus。 So you， you， you are looking at more details in here。As you can say， well。

 I'm treating this as one operation， Maybe I'm ignoring this constant。

 But whether you put in this thing as a constant factor or this thing。

 we are mostly looking at this idea of linear。 This thing is linear。 maybe 3 n plus 3。

 maybe it's 20 n plus 3。Maybe it's 30 m plus 3。 I don't know， but it is a linear function。

 It is a linear function。 Okay， does that make sense。

 And what asymptootic analysis really does is look at the class of this function。

 Instead of being bogged down by the constant factor。 Con factor are important， too。

 But we gonna mostly ignore them in this class。Any other questions， comments。All right。

Let's look at these two things。Okay， so we want to。

Try to find a relationship between benchmarking and asymptotic analysis。 Okay， so I have two methods。

 One is called find。 That's what we did。This is mystery find。And this is what we are doing here。

The question is。Are both them linear。 both them are linear。 If I do benchmarking。

 which one would be potentially faster。So can we have a vote on this one。

Which one would potentially be faster。We are looking at benchmarking。 We are looking at benchmarking。

All right。嗯。The popular choices are these to A And C。 More people are saying fine will be better。

 Can someone explain to us， why do you think this find is better than this one。

Any idea why you would say A is better。Yeah。Right， so the， I agree， right， So the answer is， well。

 I think fine will be better。If we benchmark， if we benchmark。

 we just have this count equal count plus1。 This really doesn't do anything。

RightIt's now part of my calculation。 And this part would introduce。Another N operations。

Another impar。 So if this thing is 3 M plus 3， this thing will probably be 4 M plus 3。A phone plus 4。

 because I have this assignment in there， too。So the constant factor， this is 3 n plus 3，4 n plus 4。

 This one is better。No doubt about it。O。But when we do asymettology notation。

 like right after this exercise， we're gonna say， oh， this is linear。So is this one。

So asymptotic analysis ignores the constant。So both of the man， they are the same。

 but they are not the same because of the constant factor。 right， So energy is like our USC。

 C IC majors。 We are on par with each other， right。

 But there is a difference between some of us are just more driven than the others。 So it just。

There is a human difference。 There is a human difference， right， but we on par with each other。

So we all linear near， but some， some of us are better than the others。 That's just a fact。Okay。

So in here， any questions。So AC method analysis ignores the constant factor。Now。

 let's look at the definition of asymptotic analysis。嗯。

So we say a function F is big O of another function G if。We can write this expression。

 So this is more like a calculus。 You look at。 So F N is a big O of G。

 We write F N belongs a big O of G， N。 If there are positive constant C and n not such that F N is less than C times G N for all N bigger than equal a not。

That's a definition。 That's a definition。 What does it mean， basically means when a is big。

 we assume that a constant times G would be above F。For all big values of N。So。In other words。

 we only care about。The big input sizes for small input size， that have 20 data points。 Who cares。

 You can do anything you want to。You're not gonna be in trouble， but there are 20 million things。

 Then that's gonna make a difference， okay。So most of the things that you will be dealing with when you are working in a company。

 you're gonna look at big amount of data。 It's not gonna be 1000 or 2000。 It' gonna be like。At least。

 starting in the order of millions。So， if you write。Bad code is gonna slow down the whole thing。

 We got to be very careful in here。 Okay， So when n is big， we want to know is F below G。

 And you allow G to have a constant factor of a constant factor。

And this constant factor times G is basically the idea of ignore the constants when you look at F。

That's the meaning of it。Okay， so。Any questions about the definition。Let's look at this one。 Okay。

 so we have F1， this is a slow。Is this a linear or is this a concept。

 Let's say it doesn't look like a horizontal line。 So this is a slow rising function。

 a function like this。 And then you have a。Linear function， F 2。This is like preler F 3。开。

So is this true of us， F 2 is。A member of B O F1。Is this true or false。冇田。

Some of them can be confusing。F 2 is。linear line。 F1 is a linear line， but F1 rises much slower。

 F3 is a parameter。F 2 is Sp O of F1。The two functions。We disagree with each other a to on this one。

 half， half half voted for A， half voted for B，1 and voted for C。

At least I know there is only one person who is just voting randomly。 So can we have a discussion。

 please， what did you vote for and why half， half split in here。What is the right answering here？

Talk to each other， talk to each other。Reach out to a neighbor。 Just ask。对。F1 is a slow， rising。

 linear function。就是 linear function。That's F 2。This is the current vote as of now。 Okay。

 so Lua A is winning a little bit now。 So F2 is big O of F1， in other words。

It say F 2 is less than equal to a constant times F 1， when n is large。Right。

 you can pick this constant。 You can pick any constant。 you want to。How。

 how do I pick a constant that what's， what's the impact of multiplying a constant to a linear function。

We should know this from high school。Linear function， y equals x and multiply a constant to， to x。

What does it do。Canna increase the slope。 right， That's what it does。

 So it's gonna rotate this thing up。And I can just。I can just say whatever the slope of F to is， I。

 I add one to it。Multiply it to whatever F1 is。 In other words， this thing can be true。

 This thing can be true， so。It is true。So in essence， what does that mean。

 It basically means you can think about F belongs to big O of G means。F is less than equal to G。

Less than equal to。So cheese is like the upper bound。In other words。

 F would never get above G if you allow a constant。To mouse for2 G。Does and this constant can be。

 it must be a positive constant， but it can be a decimal。 It can be My third can be 3。

 can be a million。 You can pick。Any of constant。Okay。Are we good。The next one。F1 is big O of F 2。

 F1 is big O of F2。Is that true of us。Oh， this one is even worse。 This one is even worse。

At least no is voting for C as three。嗯。And now， there's1 C。That for the final bit。

Can you have a discussion what， what， what do you do both for more likely than now your your neighbor's answers are different。

嗯。Is this true。All right， so look at the vote is almost identical as the first one。What's the answer？

The answer is， this is also true。 This is also true。 Okay， Why is this true。

Just imagine we say F1 is less than equal to F2。Right this less than equal to it means when n is big。

F 2 is always above F1。 So what should I multiply with F 2。Can be any constant。 can be any constant。

 Just one。Right so F 2 is guaranteed to be above F1。 So did we just say F2 is less than equal to F1。

 We also say F1 is less than equal to F2。What does that mean， A is less than。 A is less equal to B。

 and B is less than to A。What can you say about A and B。有。对呀。They are equivalent。 They are the same。

 They are the same。 So basically， what this one really says， F I F two they are both linear。

We are saying all DNA functions are the same。That's basically what we are saying。Okay。Any questions？

Any， yeah。Did I say I find curve， I say F1 is a very slow rising。Function。

 very slow re linear function。WellI'm assuming it doesn't corrupt， it doesn't corrupt。

Not all curve functions are。Raising fast， for example。This is a curve。What function is this。

On the function can give you this curve。Log， right， log function， so。This is log。 And。

 and this function rise extremely slow。 So not all curves rise fast。嗯哈。嗯。Are we good。The first two。

 Now how about this one， F1 is big O of F3。 F1 is part of big O of F 3。And we have a boat。Hopefully。

 we are doing better on this one。 It's less confusing。I don't know。 The vote is now coming in。

Sometimes there is a delay。Did you see that you you have both it in on your clicker。A do。Okay。

 now it's coming in。F1 is less than equal to F3， when it is big。F find is less than equal to F3。

 My n is big。Is this good or bad。Were doing slightly better on this one。All right， stop the vote。

At least the difference is bigger now。The answer is true， right。So F 3 is rising very fast。

 F1 is rising pretty slow。 So the constant factor I can pick is just one。

 F 3 is always gonna be above F1。How about the last one， F 3 is big O of F1。How about the last one。

Right， we are doing much better， much better on this one。 We stop the vote。AndThe answer is B。Right。

 so we can see that F 3， there's no way。 even if you multip this F M with a big constant。

 It's not gonna break。 It's not gonna hold this F 3。

 It's gonna rise just so much more faster than F1。Okay， yeah。Okay， so you are looking at this point。

 this region in here， that's a good， good question。 Right， Why is this true。

 even if F1 is above F 3 when a is small， we only care about when in big。Based on the definition。

 right， I can pick a knot。That would basically bound myself to be only big and。That's a good point。

 right， We don't care about any is small， but any is big。 We are looking at the trend。

It's like limit N approach infinity。That's how we can realize it。In the audio preference。All right。

So there may be some common confusions about。These like big O notations， okay。

So there are a few of them。So we say F2 is bigger of F1。

 What if I multip F 2 by a large constant so that such as C times F 2 is bigger than F 1。

Where do you I have this argument。We say， I to。Is。Big O of F1。 If you look at the notation in here。

This means a number of， in other words， people F is a class of functions。It includes many。

 many functions。 F 2 is just one of them。That's the meaning of this notation。

 So one if the argument a student may say is if I multiply C with F 2 and I pick a big C。

And this thing will be bigger than F1。Wouldn't that break the， the rule in here。

What's the counter argumentment？That's a confusion。

Anyone can tell us why this student's argument is wrong。You can multipleulate a concern to F 2。

 wouldn't that make I， I， I can make sure that C times F 2 is bigger than F1。These are his was。

You can only multiply the consent to this term。 You can only multiply the consent to F 1。

 You can't multiply consent to this。Based on the definition。So， ked。Multiply to F 2。You have to F1。

 That's fine。You cannot multiply constant to this function。You和麻 to function inside big。

The second part is like， what about when A is less than 10。 So this was a question that was raised。

For small ends， we don't care。 So we only care about large ends。That's what we have。有。嗯。

Why don't we multiply to F 2， Basically， what we want to know is is F 2 less than equal to F1 when we ignore the constants。

 when we ignore the constants， you can just imagine this， we are gonna basically say。

 ignore all the constant terms of F and F 2。 and then we do it mathematically proven way is you multip the constant to F1。

 So you can bond it。 You can bound it。 You can also say I will divide this thing by constant。

 That's fine。 But we are looking at F1 is always about F 2 by varying a constant factor。

So this is more like just to ignore the constant， ignore the constant。Mathematically。

 you shouldn apply to iPhone。Any the other questions。Alright。

 so a few things before we stop here today。So how do we calculate the asymptotic bonds on the code or algorithm。

I'll just talk about it。 Then well， well look at the exercise。 Number one。

 you're gonna do the counting。 You're gonna do the counting like what we did。

 How many operations are we gonna do， right， So as precisely as possible as a function of N when you in general。

 N is the size of input。You make sure you know that you are counting the best case， worstors case。

 the average case。 Okay， so in general， by default， we are counting for the worst case。

Where is the worst case。 We are calling for the worst case， okay。

And then you simplify your F to find a simple G N such that the async down the notation is found。

 In general， it is the dominant term。Dominant term means。

 you say I my F X equals to n square times log n。Plus， N cube， for example， said。

 which one is the dominant term， The dominant term is this one。

That actually is the biggest when an is large。That's the dominant term。

Because when a is large enough。The value of this term is going to be way bigger than the value of this term。

O。So you other way you can think for the， for the mathematicians in here is when an approach infinity。

 which term is gonna be bigger。That's the dominant term。And you just think all this dominant term。

 if say iPhone is a cube。Function， so we say F N belongs to big O， N cube。 That's how we realize it。

系。So you're ignoring the constants。 You're ignoring the less dominant terms。

 Just look for the most dominant term。Are we good。Allright， so we are done today。

I'll see you all on Wednesday。 See you all on Wednesday。



![](img/1e0fac8121cdfb8504b2d95f682cfa0f_2.png)

入了。や。No， no。It will only cover linkless and thes。