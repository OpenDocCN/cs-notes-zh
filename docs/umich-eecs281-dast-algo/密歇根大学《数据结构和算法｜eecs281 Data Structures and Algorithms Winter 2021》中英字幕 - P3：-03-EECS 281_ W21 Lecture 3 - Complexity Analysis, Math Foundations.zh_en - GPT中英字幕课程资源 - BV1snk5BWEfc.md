# 密歇根大学《数据结构和算法｜eecs281 Data Structures and Algorithms Winter 2021》中英字幕 - P3：-03-EECS 281_ W21 Lecture 3 - Complexity Analysis, Math Foundations.zh_en - GPT中英字幕课程资源 - BV1snk5BWEfc

Okay， I started just a minute early today again， so you could see Yuuki。

 who doesn't want to sit still， of course， Yuuki is a purebed maine coon。 She is completely deaf。

 and she loves to eat corns。She's destroyed three HDMI cords and shoot on electrical cords。

 it's a wonder she's still alive。Okay， let's move along。

 Showca is overtime you move on to lecture stuff。So we're going to talk about not up catfer on my face。

 me。Okay， so we're going to move on to complexity analysis today。

So when we talk about complexity analysis， we want to talk about。Describing an algorithm。

For a given input size， how long does it take for this algorithm to run？How many steps are needed？

So in terms of a step， what we're going to talk about in a minute。

 each step we're going to assume takes a constant amount of time。

 and then we're going to look at how many steps it takes。

And what we want to really see is as the input size grows as M increases。

How does our number of steps change， what is the overall trend？When we measure complexity。

 we wanted to look at。The rate of growth as some sort of function。

 And we're going to use Big O notation to describe this trend。

And the reason this is important is that。Before we start implementing things。

 we can look at how well our proposed algorithm is going to scale to different size of inputs and we can make decisions before doing a lot of work。

Now one thing about this is that it's sometimes very useful to know what the complexity is before you spend time on it。

If your boss says， hey， the people down in advertising want to make a commercial。

 they want to make this claim and we want you to run the data to get the proof that yes。

 our product really is this good before we spend time and money on the commercial。

And then three weeks later， your boss asks what's going on and you say， well， it's still running。

 I think it's doing okay。It would have been a lot better if three weeks ago you had said， well。

 I can't answer this question， that's not just me nobody can't answer this question。

 the question is too complex， It would take too long to run it and。Maybe here's a good point。

 maybe if we weaken the claim just a little bit。We can get it done in a reasonable amount of time by solving a。

Very similar problem or maybe relaxing a constraint a little bit。

And we're going to come back to this big issue of how to make things run a lot faster by changing things near the end of the semester。

When we look at a。An algorithm we might want to consider what is the best case analysis。

 what's the worst case analysis， what's the average case analysis。

 So we've got here an array of and items， pretend you can't count them and there is， in fact。

 an of them in here。And if we said， hey， we're going to do a linear search of this。Well。

 your linear search complexity is going to depend upon。N， but remember， you can't control n。

 You have to avoid the urge to say， well， the best would be when n equals1。

 we're not allowed to control n。 So n is going to be some arbitrary， large number。

 What we're allowed to control is the arrangement of the data。

Or we could also control which one we're searching for。So I could be searching for。

One that just happens to be first。Or the one I'm pet going to be searching for。

 or the one I want to search for could happen to be first either way。哦。

Should I attend a different lab， sorry I don't normally take the time I usually have other staff answering those。

 I'm just going to go put a note in Slack real quick to get somebody else looking into that issue。

One second。O。All right， I got a message sent to my staff。

 so hopefully someone will take a look at that and fix it。Okay， we're worried， all right。

 so we we got the best case， so the best case would be what I'm looking for just happens to be first。

 the worst case would be what I'm looking for just happens to be last。

And it takes M comparisons to get there。Or another alternative worst case is I'm looking for the one that just isn't in there at all。

 and I have to check all of them。The average case， if I average it over all different possibilities。

 if this happened or that happened or that happened。

 we would get the average case would be about halfway through。And so it could be near the middle。

 it could be near the end。It could be。On average about in the middle。

 so that's our average case analysis。 so when we talk about analysis。

 we're going to usually try to be specific and point out what is going on here is what are we looking for。

 are we looking for the best case analysis are we looking for the average case analysis etcter。O。

Now what affects runtime， so of the things that we can do and what is going to affect the runtime？

So well， the algorithm itself， so we get to pick the algorithm， it's going to affect our runtime。

 the implementation details which really comes down to the skill of the programmer and also remember we've got Canvas files。

 resources optimization tips， lots of tips in there to help you start getting better at this part。

The CPU speed， the memory speed， so those things of how much you paid for your hardware basically can affect that。

The compiler options， if we are debugging G3G stands for debugging， if we do debugging build。

 then it's going to run slower than if we had an optimized build。

And the one thing to note is if you're， and I forgot to mention in this in the Project one video。

Which oh remember Project one video is up， so make sure you take a look at the project one video that's up。

 refer back to the documents I added some timestamps of important points within the video to help you out because I ended up a lot long as I love it。

Anyway。This is something I should have pointed out in the video is。

When we are running inside of our IDdeE。Most IDs default to debugging level build。And so。

That can affect the speed a great deal。 if you try to run the biggest input file that we gave you inside of your IDE。

 it's going to seem like it takes a really long time。

 and that's true because it's probably not an optimized built。

If you run it at the command line and you use our make file， our make file， when you just type make。

 it builds an optimized by default。So our make file by default builds the optimized build if you do make all。

It builds both。Actually it builds three， it builds a debug， and optimized and a profiling one。

So you can build。Different ways and there's also ways to change an IDE from a debug build to a release build。

 etcter I know how to do it in visual Studio， it's just a drop down menu near the top on Xcode I don't remember it's I think it's in the scheme product scheme menu probably。

But just be careful when you're inside of your IDE， you're not looking for it to be fast。

 you're looking for the ability to debug。Other things that can affect it is other programs running in parallel。

 so other programs running at the same time can take up some resources， even if you've got multiple。

Threaded CPUs or even multiple CPUs， those things can still affect your runtime because you're competing for resources in getting from the processor to the memory。

 getting getting data from a hard drive or an SSD drive。

And that is one thing that we do on the autograder when we do final grading on the autograr。

Don't let other submissions run and we force the final grading to run one student at a time。

So even though both of our auto graders have eight physical CPUs and when students are submitting themselves。

 it's allowed to run six at a time， which should leave two other CPUs for you know keeping the web page requests going。

 etc， it still slows down a bit， so when we do final grading， we limit it to one at a time。嗯。

The last thing is obviously the input size， which we were talking about before this。Now。

 for any given program， we can fix all of those。So we can fix all of those。

 we can try to minimize the other programs running at the same time。You know。

 if we're running on our own computer， we could close our browser。

 close other things to get a really the most accurate possible。

 it won't be exactly the same every time， but it'll be closer。So， if we eliminate everything else。

 then what we're left with is runtime is the thing that we can。啊。

Sometimes control and sometimes we can't control。So sometimes we just have to run a larger input。

So the if we assume that the rate of growth is independent of things like the CPU speed。

 the memory compiler， et ceter， then。What does， what effect does changing the input size have on the runtime。

 So if I double the input size， does that mean the runtime should double。 Well， that depends。

 It looks like in our graph here。 it looks like this。I'm going to say blue blue1 looks like O of n。

 So that one we would expect if the input size doubles the time should double， but the other one。

 which is， I should check these colors， the darker one to me。

 this one looks like it might be O of n squared Master Mark。That one。

 if I doubled the size of the input， I would expect to take maybe four times longer。

So we've got an idea， again， we've got a little chicken and egg problem here we're going to look at the Big O in a minute。

 but how do we measure the input size first？Okay， we could look at number of bits。 Now。

 number of bits is getting a little too low level。 What about the number of。

Integers or the number of doubles。Which could be 32 bits，64 bits， et cetera。

 What about the number of items， I say， okay， well， there's ems that has to run on。 Well。

 then what constitutes an item， one integer an array of integers， a digit。

A character within a string， the entire string， etc。So we have to pick for a particular problem。

 what is our input sorry what is our unit of iT， so what is the item that we are measuring。

 what does n represent？And then after we've chosen what an item is， we can say， okay。

 well there's n items and I could pick some F of n。

 some maximum number of steps taken by an algorithm running on this size n， so that's an equation。

And then a little bit better than the equation is the complexity class， the big O of F of F。

 Now let's look at a little bit more about。Complexity classes， so here's。Common ones。

 these aren't the only ones， but these are some of the ones that we would most commonly see。

 so all of one constant time， so things like adding two numbers together is constant time。Now。

 just because it's constant time doesn't mean it's not useful， adding things together is useful。

 also taking the maximum of two values。Constant time， I have to look at two values。

 but finding the maximum two values is often a very useful thing to do。The next one， log n time。

 logarithmic time happens when we do things like binary search。O of N， a linear time。

 very common when we say， hey， I've got to print out everything in this data structure， well。

 if there's n things in the data structure， then it takes O of n time to print them out。

 the time to do a linear search。The worst case and average case time is all event。N log N。

 I've heard it called log linearier， I've heard it called linearmic。

I just generally say and well again。I is the simplest way and nobody gets confused about what you mean when you say end law again。

And log M time we'll see with some more advanced sorts when we look at sorting in a few weeks。

O n squared quadratic time。Is very common for different algorithms and we're actually going to look at one today later on。

Things beyond that polynomial， yes， quadratic is a subset of polynomial。

 but it also has its own special name， so yes quadratic is polynomial。

 but we often refer to it as quadratic and it doesn't seem like it's a big deal but it turns out when you get up to like a thousand items and to the fourth gets really painful to wait for。

I've done it。 I didn't like it。So things beyond that， exponential time， some constant to the n。

 factorial time， so n factorial things like n to the n is also exponential time。

 there are things beyond this doubly exponential time two to the two to the n if we look at the。

Number of binary functions on two Em bit integers like how many different operations are there on two embit integers。

 well there's addition subtract multiplication， ettera， eta， et cetera。

 there's two to the two to the M different operations on two nbit integers that's why it's so hard to be sure that a CPU works perfectly because it's hard to test every operation on every possible set of inputs。

And there's other things besides these， these are some these are common ones。

 I would say the last one is not exactly very common。

 but it does happen a lot of the others are common。We've got a quick graph of them。

Not too surprising， things like the linear is easy to see。

The logarithmic goes faster than that the constantsonant time， very easy。

 exponentials are going off the top of the chart by the time we get up to n equals4。Now。

 when we get a little further along in the semester。

 we might have a graph that consists of some vertices and edges and。

When we look at different graph algorithms， again， this is going to be in like the last three weeks of the class or so。

 we might have complexities that depend on two variables like E log v or E times v or v squared log E。

So for the most part， we're going to try to stick to one variable for a while。

 but eventually when we get up to some of the graph algorithms。

 we're going to have to consider complexity with two different variables。Now。

 as we go from analyzing a problem to implementing it。

We would like to do some sort of algorithmic comparison。

Before we worry about implementing it just to predict。

 is this algorithm that I'm considering going to be fast enough for the input size that I expect to have？

And if we can get a better time complexity and if we can't control n as much as we'd like。

 then it's really important to have that faster algorithm。The constants。

 which we're going to look at in a minute。In the big O complexity， constants don't really matter。

When N becomes really large， we want to look at the trend。When n is really small。

 the constants could have a big effect。 So we got an example here of 20 times n when n equals1。

20 times then takes longer than 10 to the n。But when n becomes2。All of a sudden。

 the linear is a lot faster， so we don't really worry about consonants too much because we don't worry about the small and you're mostly concerned with large M。

So we're going to look at in just a minute why we can get rid of those constants。O。

So when we look at operations in a program， here is an incomplete list of primitive operations。

 so things that we might like to do that happen a lot very often is things like variable assignment。

 changing a value。Takes one operation， changing， doing arithmetic， like plus minus times divide。

Doing a comparison is I less than the size， doing an array index or a pointer D reference。

Doing a function call， not counting the data， a function return， not counting what was returned。

 We count all of these as。Constant amount of time。So these are some of our most common basic operations。

 so we would say each of these takes about one step。Over one time。Now。

 when we look at counting something like a for loop， remember the for loop has three parts。

 it's got initialization， which gets performed once。It's got the test to say。

 should the loop keep running， that is going to get tested n plus one times。

 It's going to be tested once for every time the loop runs and once more when the loop ends。

 So if I was saying like something like4。I is equal to0， I is less than 5 plus plus I。

The eye less than5 is going to be tested six times。 The body of the loop runs five times。

 the increment happens five times， but the test happens six times 0，1，2，3，4。

5 test happens six times the last time it's false。So the update is going to run。

Every time the body of the loop runs and in the most common case， these are going to be。

 we're going to say a。So the whole time to run this is basically。

We can say2 n plus 2 or two times n plus1。没有。We've got some code here。

 and we could argue a little bit about the constants。

But we're not worried about those because we want to get rid of them in the in the long term。

 So we've got here a。Loop in the first one， so we've got sorry before the loop。

 we've got the one step for the initialization setting sum to zero。We've got the loop。

 which is one plus 1 plus 2 n。 I guess I didn't list the right version over here。

 So 2 n plus 2 is the same as  one plus 1 plus 2 m。So that's our loop。

And then notice that the line 4， the one step is indented。 But remember。

 if this loop is happening n times， then line 4 is going to happen。 It's one step。

 but it's inside a loop that's going to happen n times。And then there's the return。

 and I didn't count the function call， but I did count the return。

 We got to be a little bit careful if we count someone calling the function and we also count the function being called we would count line one twice。

 so I really wanted to count for this example just the code that's inside of the function between the curly braces。

So we've got。One step for for the initialization of sum1 plus 1 plus 2 n for the line 3。

 and then it says one step for line 4。 Now you could say wait a minute。

 let's go back a slide sorry two slides if I go back two slides I could say well wait a minute。

 isn't that sum plus equals I isn't that an。Arithmetic and an assignment。

 shouldn't this be not one steps， but two steps。Okay， we could do that and then this would become。

4 plus 4 n instead of 4 plus 3 n。That's okay。We can argue about these constants all day。

 but what we really want to do is we want to get rid of the constants。

So we tend not to give problems like this on the exam， because it's too easy to be off by one。

But still have the right complexity class when you give us the big O。

 So we don't like to give problems like this so much on the exam。

 we want to stick to the big O complexity of this one， which would be O of。嗯。

And then we can do the same sort of analysis with the function 2。Addd everything up。

Remember this one， this is happening inside of two loops。And this is happening inside of one loop。

So we've got to take that into account when we add up all the steps and when we did this。

 we got 3 n squared plus 7 n plus 6， which when we're done。With the complexity class。

 this one should be。Or then squared。Now that's what we want to do， how can we do that， how can we。

 oh wait， sorry， we got another example first， I'm slightly out of order here。

So what about if we said I've got something that's logarithmic。 Well。

 we couldn't quite fit a binary search and the breakdown at the bottom into one slide。

 We've got one here。 So we start out line  two is one step。Line three。

 so the initialization is going to happen。The test is going to happen one time plus the number of times the loop runss。

So that's why it's so we said it's approximately login is's how many times this loop is going to run and we'll get to that in just a minute and then there's two steps involved if the loop runs about log n times then the test happens to happen and the update has to happen That's where the two comes from and then line4 again。

 one step two steps doesn't really matter， line 6 is one step and so we get log in how did we get approximately log in there。

Well， what if I started out， what if I said I had n items and n just happened to be equal to2 to the K？

So what if M just happened to be a power of two？Well， then。The loop would run。 I would start out。

 These are basically， these here are the values of I。

 These are the values that I is going to take up。 I starts out at M。And the loop runs。

 I then becomes M n divided by2， the loop runs， I becomes n divided by 4， the loop runs。

 And eventually when I becomes one， the loop stops running。 and that's our last value of I is one。

Now， if， again， if we started out with。N was exactly a power of  two。

 well then the power of  two would be K。And the body of the loop would run exactly k times。

Now what if it was and let's do an example first， let's say n was 16。

 the loop would run when I is 16， then 8。Four and two。 so it would run those four times。

 I would become one and it would stop。Oh， look， it ran four times。 That's exactly true。

 the fourth is 16。 So if n is exactly a power of2， it will run exactly log n times。

 What if it's not a power of two， What if n started out being， let's say， 20。If n was 20。

 we would run when n is equals 20， 10。Then five， then it would become two because of integer division。

And then it would become one and we wouldn't run。 It would still run So the log base2 of 20 is 4 point。

 something I would guess about 4 point。3 is 4。4ish， so it's 4。 something is it's approximately log n。

 It looks like it's maybe floor of log n is what is the number of times this loop is going to run is about the floor of log n。

 but still that's approximately log n， and that gives us the right complexity class log n complexity。

4啊。There's another two examples here of loggan time。The bottom right is a binary search。

And a little bit different than you're used to because it's all pointers。

 so we return a null pointer if we don't find it， we've got a low high pointers and it says well high is greater than or equal to low it looks like these are inclusive inclusive these two pointers look like it's an inclusive range as long as high is greater than or equal to low so even when they're equal we keep looking so when they are equal that would mean there's one element there。

Okay， so that's inclusive， inclusive sense of pointers and a value to search for。

And while there are still places to look， we figure out the midpoint。

 we check if the value at the midpoint is what we're looking for， if it is we return that pointer。

 if what we see is bigger than what we're looking for， we move the high down to mid-1。

 Otherwise we move the low up to mid plus1。And if we ever get out of the loop。

 if we ever run out of place' look， we return null pointer。The other one。

 log B says right there in the comment， it finds the binary log of the number n and it rounds up and does that by basically repeated division line5 is doing a repeated division and line 6 says。

Count up how many times I had to divide before I got down to one。So that gives us the binary lock。

So there's a couple other examples of log time for you。Okay， here's our。

Alrithm from last time from lecture one， lecture two， sorry， lecture two， I guess。Yeah。

 so here's our example from lecture or was it lecture one， Yeah， it was lecture one I think。

So this our example from that lecture of finding the multiplication of everything except the value at index I。

 and this is the straightforward one。 It doesn't have any problem with zeros， but。It takes about。Hey。

 this loop is going to run around n times， this loop is going to run n times inside of it。

 this multiplication is therefore， so the multiplication is going to happen。Not every time。

 but it's going to happen n minus1 times。And this n minus1 is inside of a loop that's running n times。

 so we've got n times n minus1 is how many multiplications are going to happen。Which tells me？

Cool n squared。And then our。Better one that as long as we don't have any zeros， it's faster。

 we're going to do n multiplications and divisions。Which gives us n plus n， which tells me。欧问。Okay。

 so big O notation。We've got a definition here。It says a function F of n。

Is big O of G of then if and only if there are constants。C is greater than zero。

N0 is greater than equal to0， such that。F of n is less than or equal to c times g of n whenever n is greater than or equal to n0。

So what we're trying to say here is that。G of N is an upper bound of F of n。G of N。

Times possibly some constant is greater than or equal to F of n beyond some fixed point。

 So as as soon as we've reached this。Point where N is not tiny anymore。

Then G of n is always going to be greater than or equal to f of n。Well， times are count。

So for example， here， the question is， is M？Big O of and squared。So to prove this。

 what we have to do is we have to find those constants。So we have to find a constant n0。Beyond which。

Some constant times and squared is bigger than now。Now。

 if we can find exactly where the two lines cross。That n0 works Now we don't have to find the point where they cross。

 we could say， I could say， hey， n0 is equal to2。And beyond that point， I could pick， oh。

 what's my see here， it doesn't say anywhere in the slide。And I can pick a C equal to1。

So be from n0 equals to and on。And squared is greater than or equal to n。Well， sorry。

 one times n squared is greater than or equal to n。At two and beyond， it's true。

 it's also true at one and beyond。But if I pick a constant equal to one。I can't say n0 is zero。

 or I'd need a bigger constant， but a constant would exist。So we just have to find a pair that works。

 We don't have to find the perfect pair。 We just have to find any pair it's sufficient to find any pair of these constants that makes it work。

Now， there is another way to do this and。It looks like we have failed on our formatting oh。

 I have to apologize to Professor Garen on the previous slides when I had that Yen symbol。

 it was my fault， I had updated my OS， but I hadn't updated PowerPoint on my iPad。This one。

 I think this is a I'm not sure whose fault this is。

 but we've got a little bit of problems in our formulas here。Let me， I've got them handy on my。

Computer here。I'm going to pull it up on my computer just so I can tell you what it's supposed to look like。

I I want to make sure it looks right on mine。Yep， yep， this looks fine on mine here， Okay。

 so this is supposed to be the limit as n goes to infinity F n over g of n。

Is equal to D and D is less than infinity is what it's supposed to say。So then we've got all right。

 So that's the condition。 So this is a。Sufficient but not necessary condition。

What this means is that if these things work， those people limit of n as n goes to infinity。

 then there n goes to infinity of1 over2 n。Yep， and says zero is equal to D。

 which is less than infinity， so therefore it works， and this is infinity divided by infin。

fin by infinity。All right， I think I've filled， I mean just I'm just going to fill in stuff here on the bottom and then we'll get to this。

Okay， there we go。All right， so let's go through this。

So the first point is that if we take F of n divided by G of n。

 we take the limit of that as n goes to infinity， if that limit is equal to some constant。

If some constant thats less than infinity then F of n is bigger of G of n。So for example， here。

 we've got， we say is log base two of them bounded above by O of 2M？

So I've got F of n is log n G of n is equal to 2 n。

 I take the limit as n goes to infinity and I get infinity over infinity。 Well， if we remember our。

Math calcus stuff， we can do low patal's rule， we can apply that to it， and we get1 over2 n。

1 over 2 n as n goes to infinity is0， so we do have a constant d equal to0 that's less than infinity。

 and so we have proved it by this method。The next one says， is s of n over 100 bounded above by 100。

Now we try doing this with using this sufficient but not necessary condition and。

The condition does not hold。 So when we get to this point。We get no answer。

 this approach doesn't provide an answer。But it is true。 It says at the bottom。

 but it is true that it is。is this case， basically， I'm saying if I take a。

Sine wave way down here and I bound it above by the value 100。 Yeah， that is true。

 So the graphical method works。 I can take n0 equal to0， C is equal to 1。

 and this thing works using that approach So that approach always works。This approach。

 sometimes it works， sometimes it just fails to give you an answer。

 so if this approach fails to give you an answer。You've learned nothing。If the limit doesn't exist。

 you haven't learned anything。Now the next slide here is lacking in limits is equal D less than infinity。

And these are all supposed to be as n goes to infinity。Okay。

 so we want to take the equation here that was came from our function2 a bunch of slides ago。

 F of n is 3 n squared plus 7 n plus 42， we want to know is this thing big O of n squared。

 is this F of n bounded above by n squared？So what we've got to do is we've got to either use the limits approach and the limits approach does work。

 This limit is equal to three， that's less than infinity。

So the limits approach on the right does work。However。The graphic approach works also。

So in the graphic approach， there is a crossing point of these two graphs。

 but I don't know exactly what it is I can see from my graphics somewhere between3 and 4。

 it looks like it's maybe around 3。7 and something。Who cares。

 I can take a constant and I can just say， hey， what about n equals？呃。What about n 0。

 I could say what about with just n0 is equal to 4 would be good enough for me。

 I don't have to know exactly where they cross。 I've just got to have a point beyond which some constant times G of N。

Is always greater than F of them。So if I pick the n0 equals4， I pick a constant C equals5。

 so then5 n squared is greater than or equal to 3 n squared plus 7 n plus 42 at any point n equals 4 and beyond。

So I've found an N0 and a C that works。If I've found an n0 and want to see that work。

 then I've proved that yes。3 n squared plus 7 n plus 42 is big O of n squared and。

What that's telling us is， yeah， we can drop that constant。Not only can we drop the constant。

 we can drop the lower order terms。So if I had something like n squared plus n plus1。

 I can drop the lower order terms， I can drop the n， I can drop the one。

 the highest order term is the one that tells me what the complexity class is。Also。

 we've seen that we can。Drop the constant out front so I can get rid of not only in the bottom 13 n squared plus 7 n plus 42。

 I can get rid of not only can I get rid of the 7 n and the 42。

 I can get rid of the three out front of the largest term。And that gives me the complexity class。

So that's another simple way of getting at the complexity class rather than finding N0 and C is now that we know why it works。

We know that we can provide this approach， we can sort of take a shortcut here and eliminate the order order terms。

 eliminate the constant on the highest order term。And then we've got our complexity class。

Now on the slide here， we've got a bunch of identities of different。Properties of log grants。

 Now some of these are going to be really useful。 and oh gosh， it looks like it is again。

 there's like。This thing， our slides don't like equal signs。Like in the， in the。

Next to the last ones equals is missing。O。So this one right here。

 the one that was missing the equal signs， this one is really， really useful， it turns out。

What it says is that the log base a of x。Is equal to the log of x divided by the log of a。

 which is equal to the natural log of x divided by the natural log A。

 When you see log without a base， you could read it as basically any base。 So， for example。

 let's say I want the log base 2 of 1000。But I look at my calculator。

And it doesn't have a log base2 button Well then what I could do is I could say， hey。

 let's take the log。Base 10 of 1000。Divide by the log。Base 10 of。2。

And that's equivalent to the natural log， natural log of 1000， divided by the natural log of  two。

And this is going to be， this is going to be approximately 9 point。Probably 9。9 is something。

It's approximately equal to 10。So2 to the 10th is 1024， the log base 2 of 1024 is equal to 10。

 the log base2 of 1000， thousands a little bit less than 1024 the log base 2 of 10 should be a little less than 10。

So that ones， that relationship is really useful if you don't have a certain log button on your calculator。

The another one here that's really useful is。The log base a of x to the R is equal to r times log base A of x。

 So if we've got the log， say the log of n squared。

So I just say what's the log of n squared is equal to2 times the log of M。

So I'm allowed to take the exponent of M out of the log， put it out front。Okay。

 so on the next slide here， there's a couple of properties up at the top。

And a bunch of questions for you to answer。Now， pretend you didn't already go to the next slide。

 right？I'm going to take a pause here for just a minute， you can look at these questions on the left。

 the true of falses and then there's a find question。

 find F of n and G events such that neither one is an upper limit on the other so if you have pretend you haven't looked at the next slide take one minute to think about this and we'll come back and talk about it。

Okay。So for these relationships， that true or false。 Okay。

 so 10 to the 100th is bounded above by a constant。Well， sure。

 if I pick n0 equals0 and I pick some constant bigger than that， like 10 to the 1 hundred01 power。

 Sure that works。 Okay， so that one's true。 whoops， didn't mean to go to the next slide。

 So that one's true。3 n to the fourth plus 45 n cube is bounded above by0 of n to the fourth Sure we got rid of the lower order term。

 we got rid of the constant on the higher order term that was true。

Is3 to the n bounded above by 2 to the n？Okay， so three to the end。

 so I had like three squared is bounded above constant times2 squared。 Sure。

 so three squared is bounded above by 10 times2 squared。And then if it was cubed。

 like if it was 3 to the third，3 the third is 27，2 to the third would be 8。 But if I multiply by 10。

 that's still fine。 But if I pick a bigger n like。10 for n equals 10。

 I'm going to need a constant bigger than 10。 And if I pick n equals 20。

 I'm going to need a bigger constant still。 So every time I make n bigger here。

 I might need a bigger constant to make it true。If increasing n requires a bigger constant。

Then it's not a constantant anymore， so this one's false。Okay。

 what about2 to the n is bounded above by3 to the n？

So this one is true as long as I've got like n0 equals1 beyond n0 equals1。At that point or beyond。

3 to the N is always bigger than two to the n。So that one's true。

 I just needed to find an n0 equal to1 and a constant is equal to  one also， so that one works。Okay。

 45 log n plus 45 n is big O of log n。Well， this one is a matter of。

It's not you can get rid of all but the first term。

 you've got to get rid of all but the highest order term and if someone writes them out of order。

 you can't be taken by that trickery so we cross out the lower order term。

Is 45 n bounded above by a logarithm， no， how it's false。Okay。

 is log of and squared bounded above by log N？Aha， that's why the， the rules are up there。

 So that one's the， the rule that says we can take the exponent outside of。Loarithm。

 and so log of n squared， this would be a quote saying2 log n is equal to big O of log n。

Yeah I'm allowed to get rid of the constant on the highest order term， and that one's true。O。

How about log of n， the whole thing squared is bounded above by log n。I feel like that's a no。

But how can we get there？Tools up at the top， the formulas up at the top aren't a good solution for this。

 What we really need is just a simple substitution。 If I were to say， hey， let's let。X equal to。

Log in。Then what I'm asking is is x squared。Equal to big O of x is x squared bounded above by x。 No。

 that's obviously false。So a simple variable substitution make that a little clearer。Okay。

 and then the last question over here， find me an F n and a G of n such that neither one can be an upper bound of the other。

So this is one just to make you think what can I get as a counter example？

If one increases more than the other， then it's going to be an upper bound。

So I've got to have something that。Doesn't isn't monotonomically increasing。

So the example we gave here on the slide would be cosine andsine。

Neither one of them is an upper bound on the other because at any given point， they're either equal。

In this region， sine is higher in that region cosine is higher， they keep toggling back and forth。

I've seen people solve this one with what was it like arc tangent。

 I think arc tangent and almost anything because arc tangent I think it's arc tangent does something like this。

I'mterraatt drawing N engines。Okay， sooctangent keeps repeating that sort of vertical wiggle over and over。

 nothing bounds it because in some regions it's lower and some it's higher。

 some it goes basically up to infinity。So things like trigoometric functions are a good counter example there。

Okay， we've got another slide here with some。Graphal formula errors in the PDF。

 so we're going to have to reave this apparently。Oops， that's not right。

The less than equal signs are fine is equal to that intersection of that。Okay， so we're not actually。

 we're not missing that that many signss。Those looks like that's the only thing missing。 Okay。

 so we've got big O big theta big omega。 So big O is our asymptotic upper bound。

 The definition is the same thing we just gave you。And then mathematically。

 we could say that these constants exist， They are a subset of some subset of countable numbers or real numbers。

 etcter。And。For all n greater than or equal to n 0， F of n is less than or equal to c times G of n。

 And then we've got some examples down at the bottom。 I say F of n or sorry。

 F1 of n is equal to to n plus1。 And we want to know， what is a big O of that。 Well， big O of n。

 big O of n squared， big O of n cubed。 What's another one that is an upper bound on。

 It would be something like O of。And law again。Would be an upper bound 2 n plus one。And then F2。

 it says F2 is n squared plus n plus5。So upper bound down that would be n squared and cubed。

Et cetera， and factorial。Would be another example for either one of those， okay。

 let's move to the other end to big omega。So big omega is an asymptotic lower bound。

 So our definition says F of n is equal to big omega of G of n。 If and only if there still exists。

 the integer n 0 n 0 doesn't have to be an integer。 It could be a real number。

 but it's easiest to pick。Visually to pick integers， so an integer n0 and real number C。

 such that for all n greater than or equal to n0。F of n is greater than or equal to c times G of n。

 so this is a lower bound， so we say for there exists in n0 and C such that for all n greater than or equal to n0。

 f of n is greater than or equal to c times G of n。

So an asymptotic lower bound means as long as we're out past some n0。This function is a lower bound。

太覆败了。So for example， if I said F1 of M is equal to 2 n plus1。

 then examples of big omega are big omega of M， big omega of 1。

 and we could add one more to that list， big omega of log n。

Would be a lower bound on 2 n plus1 because it is smaller， asymptotically beyond some n zero。

For f of2 of n， n squared plus n plus 5， so n squared， so big omega of n squared， big omega of n。

 big omega of 1， big omega of log n。Bigger omega of N log n。

That's all the ones there are out of our list of common complexity classes。Okay， what about big The？

So big theta in the middle says it's the asymptotic tight bound。

So this says f of n is equal to big theta of g of n if and only if。

 there exists in integer n0 and real constants。Plural C1 and C2。

 such that for all n greater than or equal to n0， C1 times G of n is less than or equal to F of M is less than or equal to C2 times G of n。

So we have only one function G of M。But one constant times g of n makes it greater than equal to f of n。

 the other constant times G of n makes it less than or equal to F of n。

So it is simultaneously an upper and a lower bound just depending on the constant。

So we've got at the bottom here if F1 of n is equal to。I'm sorry。

 if everyone of n is equal to 2 n plus1， then the only complexity class that works is big theta of M。

If if 2 of n is n squared plus 2 n plus 5， then big theta of n squared is the only one that is a asymptically tight bound。

Now， one thing about the big O and big omega is。We don't want to be lazy about them。

When I ask you what is the big omega of this code， you don't want to just say， oh， well。

 it's big omega of 1 because that's true， it can't be faster than constant or what's the big O， well。

 it's probably big O of n to the n to the n power because I can't think of anything bigger so it's probably true。

While technically true， those answers are a bit lazy and were not going to let get away with it。

 So on the exams， we'll generally will ask you for a big theta。Or we will ask you for。

 say the tightest possible big O。Now it's still reasonable to talk about Big O because if I said。

Lar search。And I want linear searches complexity。If I say I want big Theta。

You can't just give me one big theta for linear search because it's different for worst case versus best case。

 See if I ask you for linear searches worst case big theta。It's worst case。Is。Big theta of M。

 but it's best case。Is big theta of what？But it's always big O of M is the tightest possible upper bound。

So I don't care， so if I say that linear search is big O of M。

 then I don't have to get specific out about best worst average。

 but if I'm talking about big theta I have to be careful to talk about like what am I asking for big theta of is it big theta of worst big theta of best so on the labs in the exams we'll try to be very specific about what we're asking for and we're either going to be asking for like a big theta of the worst case or big theta of average case or we'll say what's the tightest possible big O。

Okay， changing sections here， all right， so amortize complexity， which we talked about last time。

We mentioned this last time。また。We mentioned this last Thursday。

 so am complexity is a type of worst case complexity。

And what it means is it's used when the work versus time profile has spikes in it。

 and I'm going to draw this on the next slide。And what's。Oh actually we've got it。

 sorry we've got an example coming up after this， okay， yeah。

 we've got an example coming up in just a few minutes。

So the advertise complexity is when the time profile varies widely between different places。

 so sometimes it's very expensive， but most of the times it's a small， usually constant expense。

And what we do with an amortized complexity is we do an average over a sequence of operations。

 If this happens and then this and then this and then this and then this， if these all happened。

 one after another， what is the average of that sequence。

 Now this is difference from average case in the average case we look at， well。

 what if this happened or that happened or the other happened。

 which one would be the most common average of all of those， if only one of them happened。

 which one of them would represent the average。So average case is which one example is a good average example of all of the others。

Amortized is what if these happened one after another。

What would be the average of that sequence of events。

 and that's why we call it the amortized cost because it is it is a cost。

Averged over time and over a sequence。So this is going to be important when we talk about the STL vector。

 how the vector grows and how hash tables grow， etcter。Now an example of this。

 let's talk about an example of an amortized complexity。

 let's say that you have a cell phone bill and you pay for unlimited calls and texts and to make the math easy。

 let's assume you pay $100 a month。And then each call and text has no added cost to it。 So you。

 you pay your flat fee once a month， and then you get to make your calls in tax。 Let's say you made。

 for instance，1000 calls and tax this month。 Then each of them。Has an average cost of 10 cents。

 that's the average cost of one of them。But the rate at which money leaves your pocket is very spiky。

 See if we look at a graph of this it'd say hey， it's what day of the month is it so it's day one of the month。

So itop that instead day one， let's say January 1 January1。So let's say so January 1st。

A lot of money leaves in my pocket， $100 leaves in my pocket。But I then on January 2nd，3， fourth，5th。

0ero leaves in my pocket， So there's a lot of days here with no cost and then February 1st rolls around。

And 100 dollars leaves my pocket。So this is the place where we need an amortized analysis。

The rate at which money leaves my pocket is very spiky， but we can treat it as if the if I average。

The amount of money， if I take， sorry， if I take the total amount of money that left my pocket in that month。

 $100。I divide it by。The number of calls and text I made。

 the amortized cost of each of those texts and calls is constant。But that in another view。

 that very first text costed me $100 and all the others were freed。I don't feel like that。

 I don't feel like that I feel like， hey I spent about 10 cents each that's an amortized cost。

 so we're going to come back to this again when we look at the vector push。

So when we push into a vector， remember， we said， if needed。

 we allocate a bigger array and we copy the data over to it and then we add new elements。

Or so would we add the new element？So let's look at our analysis here。

 so what I'm going to do is I'm going to say I'm going to say I'm going to tell you upfront the amortized cost is all one。

 but let's look at how it happens， let's how to see how we got there so we say。

Let's assume the vector right now is filled with n elements， right now it's at n out of n。

If it's at N out of end right now and I want to push one thing into it， I've got to grow it。

Then once I finish growing it， I can finish that push and do a bunch more so I can really for one time doubling the size I can do。

I can complete M pushes。So I've got to。I've got a little bit of accounts cost。

 I've got to allocate the new block of memory。Then I copy everything over so that's my constant here is is this doubling the cost of vector size。

There's a constant， I allocate the new block of memory， then I copy the n elements over。

 that's big theta n， and then I have another small constant cost of change the pointer from old block of memory to new block of memory。

 delete old block of memory that's constant， so that's all in this one here。

 the new the change the pointer and the delete are all constant。

 the big theta of n is copying the n existing elements over。And now that the size has doubled。

 I can complete。N pushes each of those n pushes have a constant cost。Now。

 if I look at the graph of this， I'm at basically I'm at M out of M。And I pay a big cost。

 I pay a cost event。And then I pay a cost of one to finish a bunch of pushes。

 how many do I get to finish， I get to finish N pushes。

Then now I've reached the point where I'm at 2M out of 2M。

So I do an amortized analysis over just before I have to double it。

Until just before I have to double it again。 now， granted， when I reach 2 n out of 2 n。

 then I've got another big constant cost of 2 n。But then I get to do。2N at a cost of one each。

So if I analyze the next window， it would be 2 n plus 2N divided by 2N。Is bigicator of one。

So whether I do it over the window from。N over n up to just before 2 n out of 2 n。

 or I do it from just before 2 n out of 2 n to just before4 n out of 4 n。 The amount of work is。

Big theta of。N， but I did N operations， therefore the amortized cost of the pushes is big theta of y。

So one of the pushes was really expensive。 The very first one。

 a bunch of the ones after that were cheap。 But if I， if I look at the fact that he。

 I'm going to do a bunch of pushes， then the。Amortized cost of a push is constant。And if you look at。

 if you go and look at the documentation on like CPP reference or C++， go look up standard vector。

 look up the push operation， look at the complexity， it'll say amortized。

All of one or amortize big theta of one。So that's why we grow by doubling what would happen if we grew by a constant size？

Let's say I grew， let's say oh， let's make it 10 bigger than it used to be， okay， so I'm full。

 so I increase the size by a constant amount。I have to copy and the elements over。

I copy n elements over， and then I get to do a constant number of pushes。

I take n plus a constant divided by a constant is big theta of M。

 That's why the vector doesn't grow by adding to the size。 It grows by multiplying the size。

 If I grow by multiplying the size， the amorized cost is big theta of one。

 If I grow by adding to the size。I get a big theta of at。

Now there's one little trick here when the size is0 out of0， I've got to go to1。

 I can't go to double when I'm at  zero out of0， so there's one point at which it's empty and I go to one where we sort of grow by increasing the size by one。

 but once we get up to anything greater than zero， it just always grows by doubling and I've looked at lots of implementations of the STL vector。

 I've seen lots of implementations that double， I saw one version multiplied the size by one and half。

I think they were trying to save a little bit of memory by growing by a factor of one and a half。

 It still gives you a big theta of one for your amortized cost。 It's just。

 I think they were trying to save a little bit of memory instead of， if you accidentally。

 if you don't resize or reserve and， you know you grow up to like 1024 out of 1024 and then you push one more thing。

 you'd have almost 50% wasted。 You'd be at 10，25 out of 2048。 You'd be at like 49% wasted space。

 whereasas if you'd grow by one and a half。 you'll never have more than。啊。

A third of the total space wasted instead of a half。But generally。

 most implementations I've seen of the STL vector grow by doubling。Okay。

So now we've got a thinking exercise here at the end and again。

Pretend you haven't gone on and read all these。So we've got a bunch of billiard balls。

 so we assume that this is not CoVID era and we can go to a bar and play pool and we're playing cool and it feels like I shoot and I don't know which I don't remember which one but one of those balls I hit it and it just did not seem to move as far as I expect。

And I played a lot of pool。 And I think that one of those balls is heavier than the others。 Now。

 I didn't bring a scale with me to the bar， but I steal a tray from the waitress or waiter。

So I steal a tray from my weight person， I put a pencil underneath the end of it。

 I put a big ball in each end of it， and I get it centered exactly。

 and now I can put a couple balls in one and a couple balls in the other and I can weigh them。

And that's what I have I got a balance。So I can weigh a group of balls against another group of balls or one against one or whatever I want。

 and I can find which way。Either it balances or it's out of balance。

So I'm going to do that and I want you to describe for me， take a few minutes， think about this。

 describe an n squared algorithm， The n squared algorithm was a hard one for me。

 it was just too complex， it seemed like a lot of waste of time。

It does have an advantage we'll talk about in a minute， so figure out an n squared algorithm。

Figure out an O of an algorithm。Figure out a login algorithm and a different login algorithm。

So take a few minutes to think about that also feel free to use the chat window。

 type things up in there and we'll come back in a minute。Okay。

 so we are going to go through these in order， the order that I listed on on that slide。

What about an n squared algorithm？So if I were to take one and oh it looks like so I just put up an example of that one and you have to remember I'm about five to six seconds ahead of you。

 so if we were to take all possible pairs， so I take one I weigh it against the other n minus1。

 I take the second one I weigh against the other n minus2， etc。

So that would be basically n choose K or really n choose 2 here。 If I do n choose 2。

 this is how many weighings I would have to do n times n -1 over 2。 That's if we don't repeat。

 So I don't compare 1 to 3 and then 3 to1。So I don't compare any balls twice。

 and I don't compare anyone to themselves， obviously。

 so I get n times then minus1 over2 is n squared。Now， that really。

 I would even if I get an imbalance， I keep going。 I'm like writing these down， you know。

 like1 and two were equal，1 and  three were equal，1 and4，4 was heavier，1 and 5 were equal。

 I do all of them， and then I look back at my tabulation and decide what was wrong。 Now。

 the the slight advantage of the n squared algorithm。 It if I wasn't quite right。

If there's two of them that weigh different， this would find both of the ones that weigh differently。

So if there were two balls that weighed differently or three balls that weighed differently。

 this would find them all， whereas my other approach might stop early。

 another approach might stop early when I find one that weighs differently。Okay。

 so that's my n squared algorithm。 All right， what about with O of n So we can do the O of n we can do kind of similar to that is I'm just going to pick one ball。

 I'm going to leave it on the left， and I'm going to put all other n minus1 on the other side one at a time。

 So one versus 2，1 versus 3，1 versus 4， but I never go on to5 versus 7 or8 versus 9。

So I just leave one ball there and compare it to each of the others one at a time。

 I do n minus one comparisons， and if there's one that weighs differently， I will find it。O。落掉这了。

So log algorithm， I saw a lot of typing in there， I think I saw the log one。

 so if I just weigh half of them。So I put half in each side。If one side goes down， oh。

 that's got the heavier one， so I take the one that went down and I split that into two piles and I split that into two piles。

 split that into two piles， etc。So I just go dividing it in half until I get the one with a single one。

 Now， there is a slight problem with this one。Most games of pool involve an odd number of balls to begin with like nine or 15。

So I'm going to have to leave one out sometimes。 So if I start with 15， I go okay。

 set one aside seven and7。If the 7 and 7 weigh the same。It must be the one I left out is the odd one。

 so it still works。 I've just got to keep track of hey， if these are both equal。

 then the odd one is the one that I left out。Now， if there's two that weigh differently。

 this technique could fail， right if I do like。1 through 7 to 8 through 14。

 And each of them has a heavy ball。 We go， okay， well， both of these are equal。

 It must be ball number 15 when it's not。 It's ball number 2 and 13。 So this only works。

 if I was right， and there really was only one that was heavier than all the others。

So if those if those。If one goes down， I say， okay， this one， the one through seven is heavier。

 Now I split one through 7 into one through3，2 through6， set number seven aside。

 weigh them if they're equal， it must be the1 I left out。O。So what about。

A different log and algorithm。I want it to be log in， but I want a different algorithm。

What if I were to take all of those？Say 15 balls on a standard billiard rack。

 I take 15 and I divide it into three piles。So if I divide it into three equal groups and I weigh two of them。

If those two groups weigh the same， it must be in the one I left out and I divide that one left out by three。

Yes。These weigh differently than I know which one is heavier。

 I take that group and I divide it into thirds。Okay， that worked。 What about？

So if log 2 works and log 3 works， what about log 4， can I divide it into four piles？Well。

 the problem now is that with four piles， one weighing might not tell me anything。

One weighing tells me these two are the same。 it's got to be one of the two piles that I left out。Oh。

 and what if there was an odd one， What if I divided into。F piles of three。

 and I have three left over。Now I've really learned nothing。

 It's either in I learned it's not in these two piles of three。

 It's one of the other three piles of three。 the first pile three。

 second pile of three and the leftovers。 So dividing it into four or five or six piles with a balance doesn't work。

 So dividing two piles works three piles works for four or more piles does not。O。

Last thing here before we go， I think this is pretty close to end yeah is。

Are these two log n solutions？Are they upper bounds。On one or the other。

 are is one of these algorithms faster in its asymptotic complexity？

So is log base 2 bound above thy log base 3 is log base 3 bound above thy log base 2。Yes or no。So。

We can go back to one of our relationships。 remember we had the log base a of x is equal to the log。

 any base of x divided by log， any base of a。So then what I can say is that。Lard base X is equal to。

Lg of a。Times。Lgged base a of x。 So having to change from one base to another。

Is different by a constant amount。So having to change from one base to another base。

Is different by a constant amount because a， the base is a constant。So。

We can use that rule to see that。All log categories are theoretically as emmptically。

 they are the same， they are all a log category。 Now if I did a real implementation when we do real implementations。

 constants can matter。So I would expect if n was really， really large here。

 I would expect the log base 3 to run a little bit faster。

 a constant factor faster than the log base 2 approach。But。

Does that constantsmate factor isn't enough to matter， sometimes yes， sometimes no。

 if n is large enough it could be？So this is one of the things you can run into in the project is you might have the right complexity class。

 but you've done some operations that you didn't need to do and there's an example of this in the lecture video for Project one。

I said when we process the command line， we've got to know if the command line said stack or Q。

But I don't want to save that as a string。I don't want to later on be checking a million times。

 I my container type equal to the string stack。Because then if if my category or if my container type is the is the word string to contain or sorry。

 is the word stack to compare stack to stack。 It actually what it does is it first check the length。

 It says， oh， they are equal lengths。 So they could be equal。 So I check the length。

 Then I check the first characters with a comparison。 Then I increment increment。

 Then I check the next character with a comparison， increment increment， check the next character。

 increment increment， check a character， increment increment， check a character， increment increment。

 check I think Im and then discover I'm at the end at the end。 I've done like。18 operations there。

Instead of one， and that constant could make a difference。

That's why when we process the command line， we have to deal with the options， et ceter。

 but we want to save it as like a booley is stack mode true or false and later on I don't want to do an if else if else because later on I know it's one or the other。

 I don't mean if else if else。At the time that I'm running my search， if else。Okay。

 so we're done for today to save this feed Yuuki and get out off hourss。

