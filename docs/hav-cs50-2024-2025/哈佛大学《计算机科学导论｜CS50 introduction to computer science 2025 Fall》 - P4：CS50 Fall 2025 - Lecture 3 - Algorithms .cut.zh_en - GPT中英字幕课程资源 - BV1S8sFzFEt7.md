# 哈佛大学《计算机科学导论｜CS50 introduction to computer science 2025 Fall》 - P4：CS50 Fall 2025 - Lecture 3 - Algorithms .cut.zh_en - GPT中英字幕课程资源 - BV1S8sFzFEt7

🎼。

![](img/8aeeb4ffa4b647567df757f10b8cf92c_1.png)

Alright， this is C S 50。 This is week 3。 And this was an artist rendition of what various sorting algorithms look and sound like。

 recall from week 0， that an algorithms， just step by step instructions for solving some problem to sort information as in the real world just means to order it from like smallest to largest or alphabetically or some other heuristic。

 And it's among the algorithms that we're gonna focus on today。 in addition to searching。

 which of course， is looking for information as we did in week0， too。

 among the goals for today are to give you a sense of certain computer science building blocks。

 like there's a lot of canonical algorithms out there that most anyone who studied computer science would know。

 anyone who leads a tech interview would ask， But more importantly。

 the goal is to give you different mental models for and methodologies for actually solving problems by giving you a sense of how these realwor algorithms can be translated to actual computers that you and I can control。

 We thought we begin today with an actual algorithm for sort of taking attendance。 We， of course。

 do this with scanners outside。 But we can do it old school， whereby。😊。

Just use my hand or my mind and start doing 1，2，3，4，5，6，7，8，9，10，11，12。 and so forth。

 I's gonna take quite a few steps because I've got to point at and recite a number for everyone in the room。

 So I could kind of do what my like grade school teachers taught me， which is count by2s。

 which would seem to be faster。 So like 2，4，6，8，101214，16，1820。 and clearly。

 that sounds and is actually faster。 But I think with a little more intuition and a little more thought back to week 0。

 I dare say we could actually do much better than that。 So if you won't mind。

 I'd like you to humor us by all standing up in place and think of the number one if you could and join us in this here algorithm。

😊，So stand up。In place and think of the number one。 So at this point in the story。

 everyone should be thinking of the number one Step  two of this algorithm for you is going to be this。

 pair off with someone standing。 Add their number to yours and remember the sum。Go。Okay。

 at this point in the story， everyone， except maybe one lone person。

 If we've got an odd number of people in the room， is thinking what number。2， okay， so next step。

 one of you in each pair should sit down。Okay。Good， never seen some people sit down so fast。

 So those of you who are still standing， the algorithm still going。

 So the next step for those of you still standing is this， if still standing， go back to step 2。

E go repeat or loop if you could。And notice if you've gone back to step two。

 that leads you to step three， that leads some of you to step four， which leads you back to step two。

😡，So this is a loop。😡，Alright。Keep going， if still standing， pair off with someone else。

 still standing， add together。 and then one of you sit down。So with each passing second。

 more and more people should be sitting down。And fewer and fewer standing。Okay。

 almost everyone is sitting down。 You're getting farther and farther away from each other。

 That's okay。I can help with some of the math at the end here。Alright。

 I see a few of you still standing。 So I'll help out and I'll， I'll join you together。

 So I see you in the middle here。 What's your number。32， Okay， go ahead and sit down。

 and I'll pair you off with what's your number。20， okay， you can go ahead and sit down who still。

You're still standing。27， okay， you can sit down。😡。

You guys are still adding together who's going to stay standing。 Okay， what's your number。

The worst part is doing like arithmetic across the crowded room， but。27 also。47， okay。

 you can sit down。 Is anyone still standing， yeah。Nice，15。 Okay， you can sit down。

 Anyone still standing。Okay， so all I've done is sort of automate the process of pairing people up at the end here。

 When I hit enter， we should hopefully see， oh， the numbers are a little。 what's going on there。

 There we go。 When I hit enter， we'll add together， all of the numbers that were left。

 And if you think about the algorithm that we just executed each of you started with the number one。

 And then half of you handed off your number。 Then half of you handed off your number。

 then half of you handed off your number。 So theoretically。

 all of these ones with which we started should be aggregated into the final count。

 which if this room weren't so big， would just be in one person's mind and they would have declared what the total number of people in the room is。

 I'm gonna speed that up by hitting enter on the keyboard。

 And if your execution of this algorithm is correct， there should be。



![](img/8aeeb4ffa4b647567df757f10b8cf92c_3.png)

141 people in the room， according to our old school human， though， Kelly， who did this manually。

 one at a time， the total number of people in the room， according to Kelly。

 if you want to come on up and。

![](img/8aeeb4ffa4b647567df757f10b8cf92c_5.png)

Shouted into the microphone is， of course， going to be something around 160， I think， 160。

 so not quite the same， okay， but that's pretty good。 Okay， round of applause for your your accuracy。

Okay， so ideally， counting one at a time would have been perfectly correct。

 So we're only off by a little bit。 Now， presumably。

 that's just because of some bugs in execution of the algorithm。

 maybe some mental math didn't quite go according to plan。

 But theoretically your third and final algorithm， wherein you all participated should have been much faster than my algorithm or Kelly's algorithm。

 whether or not we were counting one at a time or two at a time。 Why Well think back to week 0。

 when we did the whole phone book example， which was especially fast in its final form。

 because we were dividing and conquering， tearing half of the problem away， half of the problem away。

 And even though it's hard to see in a room like this。

 it stands to reason that when all of you were standing up。

 we took a big bite out of the first problem and half of you SAT down half of you SAT down half of you SAT down and theoretically。

 there would have been， if you were closer in space， one single person with the final count。

 So let's see if we can't analyze this just a little bit by considering what we did。

 So here's that same algorithm。 here recall is how we motivated week  zeros demonstration of the phone book in either digital form。

As you might see in an iPhone or Android device looking for someone， for instance。

 like John Harvard who might be at the beginning middle end of saidphone book。

 but we analyze that algorithm just as we can now this one。

 So in my very first verbalized algorithm 1，2，34 you could draw that as a straight line because the relationship between the number of people in the room and the amount of time it takes is linear it's a straight line with each additional person in the room。

 it takes me one more step。 So if you think to sort of high school math。

 there's sort of a slope of one there And so this end number denoting number of people in the room is indeed a straight line and on the x axis as in week 0。

 we have the size of the problem in people and the time to solve in steps or seconds or whatever your unit of measure is if and when I started counting two at a time。

24，68，10 and so forth， that still is a straight line because I'm taking two bys consistently out of the problem until maybe the very end where there's just one person left but it's still a straight line but it's strictly faster no matter the size of the problem if you sort draw a line vertically。

 you'll see that you hit the yellow。Line well， before you hit the red line because it's moving essentially twice as fast。

 But that third and final algorithm， even though in reality， it felt like it took a while。

 and I had to kind of bring us to the exciting conclusion by doing some of the math。

 that looked much more like our third and final phone book example。

 because if you think about it from an opposite perspective。

 suppose there were twice as many people in the room。 Well。

 it would have taken you all theoretically just one more step。 granted one more loop。

 and there might be some substep in there， if you will。

 but it's really just fundamentally one more step。 if the number of people in the room quadruple。

 four times as many people。 Well， that's two more steps。 equivalently。

 the amount of time it takes to solve the attendance problem using that third and final algorithm grows very slowly because it takes a huge number of more people in the room before you even begin to feel the impacts of that growth。

 And so today， indeed， as we talk about not only the correctness of algorithms。

 we're gonna talk about the design of algorithms as well， just as we have code because。😊。

The smarter you are with your design， the more efficient your algorithms ultimately are going to be。

 and the slower their cost is going to grow。 And by cost， I mean time like here， maybe it's money。

 maybe it's the amount of storage space that you need any limited resources。

 something that we can ultimately measure。 and we're not going to do it very precisely， indeed。

 we're gonna to use some broad strokes and some standard mechanisms for describing ultimately the running time。

 the amount of time it takes for in algorithm or in turn code to actually run。 So how can we do this。

 Well， last week we called， we set the stage for talking about something called arrays。

 which were the simplest of data structures inside of a computer。

 where you just take the memory in your computer， and you break it up into chunks and you can store a bunch of integers。

 a bunch of strings， whatever back to back to back to back。

 And that's the key characteristic for an array， it is a chunk of memory wherein all of the values therein are back to back to back。

 So right next to each other in memory。 So we drew this fairly abstractly by drawing a grid like this。

 And I said， well， maybe this is by zero。This is by 1 billion。

 whatever the total number amount of memory is that you have。

 We zoomed in and looked at a little something like this。 a canvas of memory。

 We talked about what and where you can put things。 But today， let's just assume that we want 1，2，3。

4，5，6，7 chunks of memory for the moment。 And inside of them。

 we might put something like these numbers here。 Well。

 the interesting thing about computers is that even though if I were to ask you all find the number 50 in this array。

 I mean， our eyes quickly see where it is because we sort of have this bird's eye view of the whole screen and it's obvious where 50 is。

 But the catch with computers。 And with code that we write， is that really these arrays。

 these chunks of memory are equivalent to a whole bunch of closed doors。

 And the computer can't just have this bird's eye view of everything。

 if the computer wants to see what value is that a certain location。

 it has to do the metaphorical equivalent of going to that location opening the door and looking。

 then closing it and moving on to the next。 That is to say a computer can only look at or access one。

alue at a time。 Now that's in the simplest form。 you can build fancier computers that theoretically can do more than that。

 But all of the code we write generally is going to assume that model。

 You can't just see everything at once。 You have to go to each location in these here。 lockers。

 if you will， starting today， too。 when we talk about the locations in memory。

 we're gonna use our old zero indexing vernacular。 That is to say we start counting from0。

 instead of one。 So this will be locker 0 locker1 locker2 dot dot dot all the way up to locker 6。

 So just ingrained in your mind that if you hear something like location 6。

 that's actually implying that there's at least seven total locations because we started counting at zero。

 So that's intentional。 We don't have in the real worldor， yellow lockers。

 So we're gonna make this metaphor red instead， we do have these lockers here。

 and suppose that within these7 lockers physically on stage。

 We've put a whole bunch of money Monopoly money if you will。

 But the goal initially here is going be to search for some specific denomination of interest and use these physical lockers as a metaphor for what your computer is gonna do And。

😊，Your code ultimately is going do if we're searching for the solution to a problem like this。

 The input to the problem at hand is 7 lockers， All of whose doors are metaphorically closed。

 The output of which we want to be a bull true or false answer。 Yes or no。

 that number is there or no， it is not。 So inside of this black box today is gonna be the first of our algorithm。

 Step by step instructions for solving some problem。

 where the problem here is defined among all of these dollar bills specifically the $50 bill。

 If we could get two volunteers to come on up。 We're ideally really good at monopoly。 Okay。

 how about over here in front。 And how about let me look a little farther and back。 Okay。

 over here there and back， come on down。 Allright， as these volunteers kindly come down to the stage。

 We're going to ask them in turn to search for specifically the $50 bill that we've hidden in advance。

 And if my colleague Kelly could come on up too， because we're gonna do this twice。

 once searching in one with one algorithm and a second time with another。

 let me go ahead and say hello。If you'd like to introduce yourselves to the group， A'm Jose Garcio。

Hi， I'm Caitlin C。 Allright，'s Jose and Caitlin， nice to meet you both。

 Come on over and let me go ahead and propose that Jose。

 the first algorithm that I'd like you to do is to find the number 50。 And let's keep it simple。

 Just start from the left and work your way to the right。 And with each time you open the door。

 Stan over to the side so people can see what's inside and just hold the dollar amount up for the world to see。

 Allright。😊，The floor is yours。 Find us the $50 bill。20。 No， that's good。 That's good acting。 too。

 Thank you。 No， you can shut it just like the computer， alright。Nope， very clear， thank you。still no。

$10 bill。Next locker。$5 bill。 not going well。$100 dollar bill， but not the one we want。This one。

$1 bill， still no 50。 Of course， you've been sort of set up to fail。 But here。

 amazing a round of applause So they found the $50 bill。😊，All right， so let me ask you， Jose。

 you found the $50 bill。 It clearly took you a long time。 Just describe in your own words。

 what was your algorithm， even though I nudged you along。 Yeah。

 so my algorithm was basically walk up to the first door available。

 open it check if the dollar bill was the dollar bill that I was looking for and then put it back and then go to the next one。

 Okay， so it's very reasonable， because if the $50 bill were there。

 Jose was absolutely gonna find it eventually， if slowly， in the meantime。

 Kelly's going kind reshuffle the numbers behind these doors here。

 And even though Jose took a long time here， I mean。

 what if Jose wouldn't have been smart to start from the other end instead。

 do you think not necessarily， because we don't know if the 50 is going be at that end exactly。

 So he could have gotten lucky if he sort of flaunted my advice and didn't start on the left。

 but instead started on the right boom， he would have solve this in one step。 But in general。

 that's not really gonna work out。 maybe half the time it will。

 you'll get lucky half the time it won't， But that's not really a fundamental change in the algorithm。

 whether you go left to right， right to left to Jose's point。 if you don't。

Know anything a priori about the numbers。 The best you can probably do is just go through linearly left to right or right to left。

 So long as you're consistent。 Now， could you have jumped around randomly。I guess I could have。

 But if again， if they weren't in any like specified order。

 I don't think it would have helped either。 Yeah， So in additional。

 if you just jumped around to random order， they might get lucky and it might be in the very first one。

 might have taken fewer steps ultimately， But presumably you're gonna have to then keep track of like which locker doors have you open。

 So that's gonna take some memory or space， not a big deal with 7 lockers。

 but if it's 70 lockers 700 lockers。 even random probably isn't gonna be the best job。

 So let me go ahead and take the mic away and handed over to Caitlin。

 you can stay on the stage with us。 Caitlin， what I'd like you to do is approach this a little more intelligently by dividing and conquering the problem。

 but we're gonna give you an advantage over Jose。 Kelly has kindly sorted the numbers from smallest to largest from left to right。

 So accordingly， what's your strategy gonna be start in the middle。 Okay， please。😊。

And go ahead as before and reveal to the audience what you found not the 50， the 20。

 But what do you know， Caitlin at this point。 It'll be on the left correct。

 So the 20 is gonna be to the left。 So where might you go next with this three locker problem。

 Let me propose that you maybe go to the middle of the three There we go。 The middle of the middle。

 Like that would have been good。 But let's Oh no， Oh， no， it's up 100 instead， You failed。

 But what do you now know， It's in the middle。 that I should have just let you， but。

Now we have a big round of applause for Kalin for having found the 50 as well。

So one catch with this particular demo is that because they know presumably what monopoly money denominations are because we just did this exercise。

 And we had the whole cheat sheet on the board， you probably had some intuition as to like where the 50 was gonna be。

 even though I was trying to get you to play along。 But in the general case。

 if you don't know what the numbers are and that there are the specific denominations。

 But you do know that they're going from smallest to largest going to the middle。

 then the middle of the middle， then the middle of the middle again and again would have the effect of starting with a big problem and having it having it having it just like the phone book as well。

 So thanks to you both， we have these wonderful parting gifts that we found in Harvard Square。

 if you like Monoppoly， you' love the Cambridge edition filled with Harvard Square name spots。

 So thank you to you both in a round of applause for our volunteers here。😊，Alright。

 so let's see if we can't formalize a little bit these two algorithms known as linear search insofar as Jose was searching essentially along a line left to right。

 and binary search by implying2， because we were having that problem in2 again and again and again。

 So， for instance， with linear search from left to right or equivalently right to left。

 we could document our pseudocode as follows for each door from left to right。

 if the 50 is behind the door。 Well， then we're done just return true。 That's the boolean value。

 which was the goal of this exercise to say yes， here is the 50。 Otherwise。

 at the very bottom of this pseudocode， we could just say return false。

 because if you get all the way through the lockers and you have never once declared true by finding the 50。

 you might as well default at the very end to saying false， I did not find it。 But notice here。

 just like in week 0， when we talked about pseudocode for searching the phone book。

 my indentation of all things is actually very intentional。 this version of this code would be wrong。

I instead used our old friend if else and made this conditional decision。

 Why is this code now in red wrong in terms of correctness， yeah。Exactly。

 because if the number 50 is not behind the first door， the else is telling you right then and there。

 return false。 But as we've seen in C code， whenever you return a value。

 like that's it for the function， it is done doing its work。 And so if you return false right away。

 not having looked at the other six lockers， you may very well get the answer wrong。

 So the first version of the code where there wasn't an else。

 but rather this implicit line of code at this explicit line of code at the very end。

 that just says if you reach this line of code return false that addresses that problem。

 And to be clear， even though it's right after in indented return true。

 when you return a value as in C， that's it， like execution stops at that point。

 at least for the function， or in this case， the pseudocode in question。 Allright。

 so here's a more computer scienceency way of describing the same algorithm。

 And even though it starts to look a little more a And the reality is when you start using variables and sort of standard notation。

 you can actually express yourself much more clearly and precisely。

 even though it might take a little bit of practice to get used to Here is how a computer scientist would express that exact。

Idea instead of saying for each door from left to right， we might throw some numbers on the table。

 So for I， a variable， apparently from the value 0 on up through the value n-1 is what this shorthand notation means if 50 is behind doors bracket I。

 so to speak。 So now I'm sort of treating the notion of doors as an array using our notation from last week。

 if 50 is behind doors bracket I return true， Otherwise。

 if you get through the entirety of that array of doors， you can still return false。 Now。

 notice here， n-1 seems a little weird， because aren't there n doors。

 Why do I want to go from 0 to n-1 instead of 0 to N。 yeah。な。Exactly。

 if you start counting at 0 and you have n elements， the last one is gonna be addressed as n-1。

 not n because if it were n， then you actually have n plus one elements。

 which is not what we're talking about。 So again， just a standard notation。

 and it's a little Tser this way， it's a little more succinct。 And frankly。

 it's a little more adaptable to code。 And so what you're going find is that as our problem sets and programming challenges that we assign。

 of get a little more involved。 It's often helpful to write out pseudocode like this。

 using an amalgam of English and C and eventually Python code because then it's way easier after to just translate your pseudocode into actual code if you're operating at this level of detail。

 Allright， So in the second algorithm， where Caitlin kindly search for 50 again。

 But Kelly gave her the advantage of sorting the numbers in advance。

 now she doesn't have to just resort to brute4， so to speak。

 trying all possible doors from left to right。 She can be a little more intelligent about it and pick and choose the locker she opens。

 And so with binary search， as we call that， we could implement the。😊。

we could implement pseudocode for it as follows。 We might say if 50 is behind the middle door。

 then go ahead and return true。 else if it's not behind the middle door。

 but 50 is less than that number behind the middle door。 We want to go and search the left half。

 So that didn't happen in Caitlin sense， because we ended up going right。

 So that's just another branch here， El if 50 is greater than what was at the middle door。

 we want to search the right half。But there's going to be one other condition here that we should probably consider。

 which is what。Is it here， is it to the left， or is it to the right？😡。

But there's another a corner case that would better。Keep track of what else could happen。

If it's not in the array or really like we're out of doors。

 so we can implement this in a different way。 I left myself some space at the top because I shouldn't do any of this if there are no doors to search for。

 So I should have this sort of sanity check whereby if there's no doors left or no doors is it to begin with let's just immediately return false。

 And why is that will notice that when I say search left half and search right half this is implicitly telling me just do this again。

 just do this again， but with fewer and fewer doors。

 And this is a technique for solving problems and implementing algorithms that we're gonna end today's discussion on because what seems very colloquial and very straightforward。

 search the left half search the right half is actually a very powerful programming technique that's gonna enable us to write more elegant code。

 sometimes less code to solve problems such as this and more on that in just a little bit。

 But how can we now formalize this using some of our array notation。

 it looks a little more complicated。 but it isn't really instead of asking questions in English alone。

 I might say a 50 is behind doors bracket middle。 this。

Psupposes that I did some math and figured out what the numeric address。

 the numeric index is of the middle element。 And how can I do that？ Well。

 if I've got 7 doors and I divide by 2， what's that，7 divide by 2。3 and a half。

3 and a half makes no sense if I'm using integers to address this。 So maybe we just round down。 So 3。

 So that would be locker number 0，1，2，3， which indeed。

 if you look at the 7 lockers is in fact the middle。

 So this is to say using some relatively simple orrithmetic。

 I can figure out what the address is the index is of the middle door。

 if I know how many there are and I divide by2 and round down。 Meanwhile。

 if I don't find 50 behind the middle door， let's ask the question。

 if 50 is less than the value at the middle door， then let's search not the left half per se in the general sense more specifically search doors bracket 0 through doors bracket middle-1。

 Otherwise， if 50 is greater than the value at the middle door。

 go ahead and search doors bracket middle plus1 through doors bracket and-1。 Now。

 let's consider these in turn。 So searching the left half， as we described this earlier。

 seems to line up with this idea。Like start searching from doors bracket0， the very first one。

 but why are we searching doors？😡，Brarackt middle minus-1 instead of doors bracket middle。Yeah。Yeah。

 exactly。 we already checked the middle door by asking this previous question。

 So you're just wasting everyone's time。 if you divide the half and still consider that door as checkable again。

 and same thing here。 we check middle plus one through the end of the lockers array because we already checked the middle one。

 So same reason， even though it just kind of complicates the look of the math。

 But it's really just using variables in arithmetic to describe the locations of the same lockers。

 But let's consider now what we mean by running time。

 The amount of time it takes for an algorithm to run and consider which and why one of these algorithms is better than the other。

 So in general， when talking about running time， we can actually use pictures like this。

 This is not gonna be some like very low level mathematical analysis where we count up lots of values。

 It's gonna be broad strokes so that we can communicate to colleagues to other humans generally whether an algorithm is better than another and how you might compare the two。

 So here， for instance， is a pictorial analysis of two different algorithms。

 The phone book from week 0 and then the attendance。Taking from today itself。 And let's generally。

 as we've done before， sort of label these things。 So the very first algorithm took n steps in the very worst case。

 if I had to search the whole phone book or if I had count everyone in the room。

 So the first algorithm took indeed N steps。 The second algorithm took half as many plus one， maybe。

 but we'll keep it simple。 So we'll call that n over2。

 and the third and final algorithm both in week 0 with the phone book and today with attendance is technically log base2 of n。

 And if you're a little rusty in your algorithms， that's fine。

 just take on faith that log base 2 alludes to taking a problem of size n and dividing it in half and half and half as many times as you can until you're left with one person standing or one page in the phone book。

 That's how many times you can divide in half a problem of size N。 Well。

 it turns out that we're getting a little more detailed than most computer scientists care to get when describing the efficiency of algorithm。

 So in fact， we're gonna to start to use some notation。

 instead of worrying precisely mathematically about how many steps today。😊。

And the futures algorithms take we're going to talk in broader strokes about how many steps there on the order of and we're going to use what's called big O notation。

 which literally is like a big O and then some parentheses。

 And you pronounce it big O of such and such。 So the first algorithm seems to be in big O of n。

 which means it's on the order of n steps give or take some This algorithm here。

 you might be inclined to do something similar it's on the order of n divided by two steps。

 And this one's on the order of log based two of n steps。

 But it turns out what we really care about with algorithms is how the time grows as the problem itself grows in size。

 So the bigger n gets the more concerned we are over how efficient R algorithm is if only because today's computers are so darn fast。

 whether you're crunching a thousand numbers or 200 numbers。

 like it's going to take like a split second， no matter what。

 But if you're crunching 10 numbers versus a million numbers versus a billion numbers。

 like that's where things start to actually be。Pable by us humans。

 and we really start to care about these values。 So in general， when using big O notation like this。

 you ignore lower order terms or equivalently， you only worry about the dominant term in whatever mathematical expression is in question。

 So big O n remains big O of n。 big O of n over 2。 it's the same thing really is like big O over n。

 Like it's not really， but they're both linear in nature。 One grows at this rate。

 one grows at this rate instead， but it's for all intents and purposes is the same。

 They're both growing at a constant rate。 This one to acts on the order of log of n。 where the basis。

 who cares。 In short。 What does this really mean Well， imagine in your mind's I。

 that we were about to zoom out on this graph。 such that instead of going from0 to like a million。

 maybe now the x axis is 0 to a billion and same thing for the y axis 0 to a million。 Let's zoom out。

 So you're seeing 0 to a billion。 Well， in your mind's I， you might imagine that as you zoom out。

 essentially， things just get more and more compressed visually。

Because you're zooming out and out and out。 But these things still look like straight lines。

 This thing still looks like curve lines， which is to say as n gets large， Clearly。

 this green algorithm， whatever it is， is more appealing， it would seem。

 than either of these two algorithms。 And if we keep zooming out like at some point。

 the ink is gonna be so close together that they all are for all intent purposes。

 pretty much the same algorithms。 So this is to say computer scientists don't care about lower order terms like divide by two or base2 or anything like that。

 we look at the most dominant term that really matters is n gets bigger and bigger。

 So that then is big O notation。 And it's something will start to use pretty much recurring any time we analyze or speak to how good or how bad some algorithm is。

 So here's a little cheat sheet of common running time。 So， for instance。

 here's our friend big O of N， which means the algorithm takes on the order of n steps。

 Here is one that takes on the order of log n steps。 Here's some others we haven't seen yet。

 Some algorithms take n times log n steps。 Some algorithms take n squared steps and some。

Gos just take one step， maybe， or maybe two steps or four steps or 10。

 but a constant number of steps。 So let me ask of the algorithms we've looked at thus far。

 For instance， linear search being the very first today。

 What is the running time of linear search in big O notation。That is to say if there's people。

 if there's N lockers on the stage。How many steps might it take us to find a number among those n。

Lockers， they O of， yeah。Big O of n， in fact， is exactly where I would put linear search。 Why。 Well。

 if you're using linear search in the very worst case， for instance。

 the number you're looking for as with Jose might be all the way at the end。 So you might get lucky。

 it might not be at the very end。 But generally， it's useful to use this big O notation in the context of worst case scenarios。

 because that really gives you a sense of how badly this algorithm could perform。

 if you just get really unlucky with your data set。

 So even though big O really just refers to an upper bound， like how many steps might it take。

 it's generally useful to think about it in the context of like the worst case scenario。

 like the number I care about is actually way over here。 But what about binary search。

Even in the worst case， so long as the data issorted。

 how many steps might binary search take by contrast。Big O of log n。

 So binary search we're gonna put here， which is to say that in general。

 and especially as n gets large， binary search is much faster。 It takes much less time。 Why。

 because assuming the numbers are sorted， you will be dividing in half and half and half just like with the phone book in week 0。

 that problem and you will get to your solution much faster。 Why should you not use binary search。

 though， on an unsorted array of lockers。Like a random set of numbers， yeah。Because you don't know。

Exactly， you're making these decisions based on inequalities less than or greater than。

 but based on like no rhyme or reason， you're going left going right。

 But there's no reason to believe that smaller numbers are this way and bigger numbers are that way。

 So you're just making incorrect decision after incorrect decision。

 So you're probably gonna miss the number altogether。

 So binary search on an unsorted array is's just incorrect， incorrect usage of the algorithm。

 But like Kelly did， if you sort the data in advance or your handed sorted data。 Well， then you can。

 in fact， apply binary search perfectly and much more efficiently。是。Absolutely。

 is linear search sometimes more efficient if it's going take you more time to sort the data and then use binary search absolutely。

 And that's gonna be one of the design decisions that underlies any implementation of an algorithm。

 because if it's gonna take you some crazy long time， not to sort like 7 numbers， but 7700。

77 million， but you only need to search the data once。 Then what the heck are you doing。

 Like why are wasting time sorting the data。 if you only care about getting an answer once。

 you might as well just use linear search or heck， do it even randomly and hope you get lucky if you don't care about reproducing the same result。

 Now， in general， that's not how much of the world works。 For instance。

 Google's working really hard to make faster and faster algorithms because we are not searching Google once and then never again doing it。

 We're doing it again and again and again， So they can amortize So to speak the cost of sorting data over lots and lots of searches。

 but sometimes it's gonna to be the opposite。 And I think back to graduate school。

 where I was often writing code to analyze large sets of data。

 And I could have done it the right way。It sort of the CS 50 way by fine tuning my algorithm and thinking really hard about my code。

 But honestly sometimes it was easier to just write really bad， but correct code。

 go to sleep for seven hours。 And then my computer would have the answer by morning。

 the downside as admittedly happen more than once is if you have a bug in your code and you go to sleep and then seven hours later。

 you find out that there was a bug， you've just wasted the entire evening。

 So there too a tradeoff sometimes when making those resource decisions。

 but that's entirely what today is about making informed decisions and sometimes maybe it's smarter and wiser to make the more expensive decision。

 but not unknowingly at least knowingly All right， so there we have our first two algorithms。

 But let's consider another way of describing the efficiency of an algorithm。

 Big O is an upper bound， of how bad can it get in these cases where maybe the data is really not working to our advantage。

omega a capitalomega symbol here is used for lower bound。

 So maybe how lucky might we get in the best case， if you will。

 how few steps might an algorithm take。In this case here。

 here's just a cheat sheet of common runtime， even though there's an infinite number of others。

 but we'll generally focus on functions like these， let's consider those same algorithms。

 So with linear search from left to right， how few steps might that algorithm take。For instance。

 in like the best case scenario。Yeah， is this a hand about to go up？Yeah， so one step why。

 because maybe Jose could have gotten lucky and opened the door in voilah。 that was the 50。

 It didn't play out that way， but it could have in the general case。

 the number you're looking for could very well be at the beginning。

 So we're gonna put linear search at omega of one。 So one step。

 And maybe it's technically a few more than that， but it's a fixed number of steps that has nothing to do with the number of lockers。

 case in point， if I give you not 7 but 70 lockers。

 You could still get lucky and still take just one step。 So omega is our lower bound。

 Big O is our upper bound。 spoiler。 What is binary an search is lower bound。 Well， apparently。

 it's also omega of one， but why。That is in fact， correct， yeah。

Same reason you could get lucky in the best case。 and it's just Smackdb in the middle of all of the data。

 So the fewest number of steps binary search might take is also actually one。

 So this is why we talk about upper bound and lower bound because a sense of the range of performance。

 Sometimes it's going to be super fast， which is great。 but something tells me in the general case。

 we're not gonna get lucky every time we use an algorithm。

 So it's probably going be closer to those upper bounds， the big O。 Now， as an aside。

 there's a third and final symbol that we use in computer science to describe algorithms that of a capital theta capital theta is jargon you can use when big O and omega happen to be the same。

 And we'll see that today。 not always， But here's a similar cheat sheet。

 none of the algorithms thus far can be described in this way with theta notation because they are not all the same with their big O and omega。

 They differed in both of our analyses。 But we'll see at least one example of one。

 where it's like okay， we can describe this in theta。

 And that's like saying twice as much information with your words to another computer scientists。😊。

Rather than giving them both the upper and the lower bounds。

 the fancy way of describing all of what we're talking about here， Big O。

 omega and theta is asymptotic notation and asymptotic notation refer asymptotic Lee refers to a value getting bigger and bigger and bigger and bigger。

 but not necessarily ever hitting some boundary as N gets very large in short is what we mean when we deploy this here。

 asymptotic notation。 Alright， so with the first of these things like linear search。

 let's actually kind of make this a bit more real。 Let me actually go over to in just a moment。

 my other screen here。 let's pull up our friend V S code。

 and let's go ahead and implement some version of linear search。

 just to make this a little more concrete， especially since we've used linear search in metaphorical form only。

 I'm gonna go ahead and create a program called search dot C， and inside of this program。

 I'm gonna go ahead and do the following here。 Let me go ahead and。😊，So， give me one second。

And reload， our line numbers are strangely small。There we go。That was what we'd call a bug， come on。

One second。Close this again。And this， okay， apologies。 Let's go ahead and do this once more。Okay。

 in V S code， let me go ahead and create a program called search dot C。 And in search dot C。

 Let's go ahead and implement a fairly simple version of linear search initially。

 So let me go ahead and include， for instance， Cs 50 do H。

 let me go ahead and include standard I O do H。 Then let me go ahead and do main void。

 So we're not gonna bother with any command line arguments for now。

 And then let me go ahead and just give myself an array of numbers to play with。

 And we did this briefly last week and answer to a question。

 but I'm gonna do it now concretely rather than use something more manual to get all of these numbers into the array。

 I'm gonna say give me an array called numbers and the numbers。

 I want to put in this array initially are gonna be the exact same denominations we've been playing with250105。

101 and 50。 Again， this is notation that I alluded to an answer to a question last week。

 whereby if you want to statically initialize an array that is give it all of your values upfront without having the human type them all and manually。

 you can use curly braces like this。 and the compiler。😊，Itsret smart。

 You don't have to bother telling the compiler how many numbers you want 1，2，3，4，5，6，7。

 because it can obviously just count how many numbers are in the curly braces。

 But you could explicitly say 7 there So long as you're counting is， in fact， correct。 So on line 6。

 excuse me an array of 7 numbers initialized to precisely that list of numbers from left to right。

 Allright， let's ask the human now， what number they want to search for just as I did are two volunteers and say int N equals get in then let's just ask the user for the number that they want to search for。

 Then let's implement linear search。 And if I want to implement linear search in terms of the programming constructs we've seen thus far。

 Like what type， what keyword and C should I use what programming technique yeah。Yeah。

 so maybe a for loop or a while loop， but for loop is kind of my go to lately。 So let's do four int。

 I equals0 because we'll start counting from the left。 I is less than7。

 which isn't great to hard code。 but I'm not gonna to use the7 again。

 So I think it's okay in one place for this demo， then I plus plus then inside of this array let's go ahead and ask a question just like Jose was by opening each of the doors by saying if numbers bracket I equals equals the number we asked about n。

 Well then let's go ahead and print out some informative message like found backlash n and then for good measure like last week。

 let's return0 to signify success。 It's sort of equivalent to returning true， but in main recall。

 you have to return an int。 That's why we revealed at the end of week2 the return type of main is an int because that is what gives the computer。

 It's socalled exit status which is0 if all as well or anything other than zero。

 if something went wrong。 But I think finding the number。Cocounts as all as well。

 But if we get through that whole loop。 and we still haven't printed， found or return0。

 I think we can go ahead and safely say not found backlash n。

 and then let's just return one as our exit status to indicate that we didn't find the actual number。

 So in short， I think and see this is linear search。 Let me open up my terminal window again。

 Let me make search， enter Let me do dot slash search， enter， and I'll search for， as I ask Jose。

 the number 50 and we indeed found it at the end。 Let me go ahead and rerun dot slash search。

 and let's search for the other number at the beginning，20 that then works。 And just to get crazy。

 let's search for a number， we know not to be there like 1000。 and that， in fact， is not found。

 So I think we have an implementation then of linear search。

 But let me pause here and ask if there's any questions。

With this here code and the translation of algorithm 2。See， yeah， in the back。

Why I did not specify the length of the array。 So it is not necessary when declaring an array and setting it equal to some known values in advance to specify in the square brackets how many you have。

 because like the compiler is not an idiot。 It can literally count the numbers inside of the curly braces and just infer that value。

 You could put it there。 But arguably， you're opening up the possibility that you're gonna miss count and you're gonna put 7 here。

 But 8 numbers over there or six numbers there。 So it's best not to  temp  fate。

 and just let the compiler do its thing instead。 a good question。 Other questions。

On this code so far。Alright， if none， let's go ahead and maybe convert this linear search to one that's maybe a little more interesting that involves like searching for strings of text。

 After all， we started the class in week 0 by searching for names in a phone book like John Harvard。

 let's see if we can't adapt our code for searching for strings instead of integer。

 So in my code here， let's go ahead and delete everything inside of main just to give myself a clean canvas。

 let me go ahead and give me another array。 This one called let's just call it strings because that's the goal of this exercise and set them equal to some familiar pieces from the game of monopoly if you might have played。

 So there's like a battleship piece in there There's a boot in there。 There's a canon in there。

 an iron， a thimble and a top hat。 though it does vary nowadays based on the edition that you have。

 So kind of a long array， but I have1，2，3，4，5，6 total values in this array of strings。

 Now let's ask the user for a string。 we'll call it S for short and say。😊，With getstring。

 what string are you looking for among those six then I think we can do a for loop again for int i equals0 i less than6 i plus plus。

 and then inside of this loop， let's do the same thing。😡，If。Let's say strings。

 bracket I equals equals the string S that the human typed in。 I think we can go ahead and say。

 print found backslash n。 And then as before return。0 to signify success。 And if we don't。

 after that a whole four loop， let's print， printf not found back slash and down here and return one to signify error。

 So it's really the same thing at the moment， except that I'm actually using strings instead of integers。

 Allright， let me go ahead and open up my terminal window again and clear it。

 Let me go ahead and recompile this code。 make search dot C seems to compile。 Okay。

 let me do dot slash search。 And let's go ahead and search for the first one。

 How about battle ship enter。😊，not found。 Alright， well， let's maybe typo。

 maybe let me search for something easier to spell， Bo。Not found。 That's weird。

 Both of those are at the very start of the array。 Let's dot slash search again and search for top hat enter。

😡，Not found。What is going on。 Well， this isn't actually that obvious as to what I'm doing wrong。

 But it turns out that when we actually compare strings instead of integers and C。

 we're actually going have to use this other library。

 at least today that we saw briefly last week Last week we introduced it because of a function called Stling。

 which gives us the length of a string turns out that string dot H also comes per its documentation with another useful function called stir comp for string compare。

 And its purpose in life is to actually compare two strings left and right to make sure they are。

 in fact， the same。 So for today's purpose， is suffice it to say you cannot use equals equals。

 apparently to compare two strings intuitivetuly， why is that Well， for a computer。

 it's super easy to compare two integers because they're either there or they're not in memory。

 But with a string， it's not just a character and another character。

 it's like a few characters over here and a few characters over here。

 maybe it' a few maybe it's more， you have to compare each and every character in a string to make sure。

They're in fact the same So stir compare does exactly that。

 Probably in the implementation of stir comp from like years ago。

 someone wrote a while loop or a four loop that looks at each string left to right and compares each and every one of the characters they're in and then gives us back an answer So how do we go about using this Well to use stir compare what I can actually do in VS code here is go and change my code as follows。

 instead of using equals equals。 I'm going to actually use this function per its documentation。

 I'm going to call stir compare， then I'm going to pass in one of the strings。

 which is in strings bracket I then I'm going to pass in the second string， which is S。 However。

 having read the documentation and this is a little nonobvious it turns out that stir comp will return zero if the strings are equal otherwise it's going return a positive number or a negative number So what I care about for now is does the return value of stir comp when given those two strings Give me back zero。

If so， they are equal and I'm going to say quote unquote found。

 so let's go ahead and open the terminal again， let me go ahead and clear it and do make search to recompile my code。

 And I've done something wrong。 Let's see， let me scroll up to the very first line in line 11 error。

 call to undeclared library function St comp with type in and something something which gets more complicated after that。

😡，Why is line 11 not working despite what I just preached？Yeah。Yeah， I just did something stupid。

 I didn't include the string dot H header library。 So all clang our compiler is doing when invoked by make is it's encountering literally the word stir comp and not knowing what it is because we haven't taught it what it is by simply saying include string dot H at the top。

 let me reopen my terminal window， clear that message away。 do make search again。

 now it's compiling dotlash search enter。 Now I'm gonna go ahead and search as I did before for battleship。

 now it's finding it。 Let me run dot search again。 search for boot。 that's found。

 Let me go ahead and search for top hat that too is in there。

 Let me go ahead and search for something that's not there like the number 50。 not in fact， found。

 So I think we've actually fix that there problem。 But if we go back to this code for a moment。

 It's indeed the case。 per the documentation that equals equals0 is what I want to do。

 Why in the world stir comp be designed to return a positive or a negative number2。

 It's not returning true or false， It's returning one of three possible values。Negative or positive。

Why might it be useful， yeah。いば。Yeah， super clever。 So if you're passing into strings。

 it's great to know if they're equal。 but wouldn't it be nice if this same function could also help us sort these strings ultimately and tell me which one comes first alphabetically。

 and technically， it's not gonna be alphabetically。

 it's gonna be an phrase askibetically because it's actually gonna look at the ASI values of the characters and do some quick arithmetic and tell you which one comes first and which one comes later。

 which is enough as we'll eventually see for actually sorting these strings as well。 So in short。

 the documentation will tell me that I should check not only for0， if I care about equality。

 but if I care about inequality， that's checking if one comes first or last。

 I should check whether something is less than 0 or greater than， but for this demonstration。

 I linear search， I don't care about comparing them for inequality。

 All I care about is that they are， in fact， the same or not in this case。 All right， well。

 let's go ahead and do one other example of sort of linear search。

 But let's make the problem more like that actually in week 0 of searching a phone book。 so。😊。

Let me go back to VS code here。 close search do C。 and let's make an actual phone book。

 I'm gonna to say code of phonebook do C。 and then inside of phone book do C。

 let's use our same header file。 So include CS50 do H include standard Io H。

 and let's include an advance string H。 then let's as before do in main void。

 no command line arguments today。 then inside of here， let me give myself first an array of strings。

 How about some names in the phone book。 I'm gonna say string names， equals。

 and then three names just to make a demonstration， Kelly and David and say John Harvard here。

 But if it's a phone book， I need more than just names。

 So let me go ahead and give myself another array， string of numbers。

 open bracket closed bracket equals and now the same phone numbers we used in week 0 for the three of us plus 1。

6，1，7，4，9，5，1000 same for both Kelly and me So plus1，6，1，7，4，9，5。1000 And then as before。

 if you'd like to text or call John directly， you can do so at plus 1，9，4，9，4，6，8，2，7，5，0。

 and semicolon。 So one question first， I obviously declared our names to be an array of strings。

 Because that's what text is， why have I also declared phone numbers to be strings and not integers because a phone number is like literally a number in the name of it。

 yeah。Yeah， so even though we have phone numbers in the US。

 even though we have social security numbers and a bunch of other things that we call numbers。

 if you have other nondits in those in those values。

 you have to actually use strings because if it's not an actual integer。

 But it does have things like pluses or dashes or parentheses or any other form of punctuation as as common in the US and other countries for phone numbers in particular。

 you're going to actually want to use strings and not numbers， as well as for corner cases。

 like if if you're in the habit back home， if you're not from say the US and you actually have to dial zero first to make like a local regional call。

 you don't want to have a leading zero in a integer because mathematically。

 as we know from grade school， like leading zeros number zeros。

 they come first have no mathematical meaning， they're going to disappear effectively from the computer's memory unless we store them。

 in fact， as characters in strings in this way。 Okay， with that said。

 let's go ahead and ask the human now， after having declared those two arrays for the name。

 they want to look。The number of so let's say string name equals get string and let's go ahead and ask the human for the name for which to search then let's use a for loop as before for n to I equals0 I less than3 which again for demonstration purposes I'm just hard codingding today I plus plus and then in the four loop I'm gonna to use our new friend stir comp if the return value of stir compareare passing in names bracket I and the name the human typed in equals equals0 signifying that they are in fact the same well that means we found the location I where the person's name is so let's go ahead and print out found but just to be fun let's print out whom we found So percent S backslash n and then output there the number which is going to be in the corresponding numbers array at that same location I we'll return zero and at the very end of this program let's go ahead and print out not found if we get that far and return one。

Alright， so a little more complexity this time。 But notice I'm comparing the names just like a normal person would in your ios app or your Android app when looking for someone's name。

 But what I care about is getting back the number。 So that's why two lines later。

 I'm printing out the number that I found at location I。

 not the name because I already know the name。 Allright， in my terminal window。

 Let's go ahead and make this phone book。😊，Dot slash phone book。 Let's go ahead and search for John。

 whose number is hopefully indeed exactly that number。 So suffice it to say this code2 does work。

 This is a linear search because I'm searching left to right。

 these aren't actually sorted alphabetically by name or let alone number。

 So I think we're doing well here， but I don't necessarily love this implementation。

 Even if you're new to programming。 What might you not like about how I've implemented a phone book in the computer's memory。

Why is this maybe not the best design， yeah。Of course。Okay， yeah。

 I would say so you're pointing out that we have this duality。 We've got two arrays。

 They're the exact same length。 and it just so happens that location zero's name lines up with location  zeros number and location 1 and location 2。

 but we're kind of on the honor system here whereby the onus is on us to make sure we don't screw this up。

 And we make sure we always have the same number of names and the same number of numbers and better and moreover。

 that we make get the order exactly right。 We are just trusting that when we print out the number。

 so to speak， that it lines up with the I name。 So that's fine and honestly。

 for three people who really cares。 it's fine。 But if you think about 30 people，300，3 million。 Well。

 we're not gonna hardcode them all here。 But even in some database that will store them in later in the course。

 feels like just trusting that we're not gonna screw this up is asking for trouble。 And indeed。

 a lot of programming is just that like not trusting yourself and definitely not trusting your colleague not to mess something up but programming a bit more defensively and trying to encapsulate related information a little more tight。

😊，Together and not just assume， as on the honor system that these two independent arrays will line up。

 But at this point， we have no means of solving this problem unless we give ourselves just a bit new functionality in syntax。

 So I use this phrase earlier to kick things off data structures。

 It's like how you structure your data in the computer's memory arrays are the simplest of data structures。

 They just store data back to back to back from left to right contiguously in memory。

 but they all have to be， as we've seen the same kinds of values in int int or string string string。

 there's no mechanism yet for storing an int and a string together。

 And then another int and another string together or let alone two strings， two strings。

 two strings that are somehow a little bit different。

 But it would be nice if C gave us an actual data type to store people in a phone book。

 such that we could create an array called people inside of which is gonna to be a whole bunch of persons。

 if you will， back to back to back。 And I want two of them。

 So wouldn't it be nice if I could literally use this code in C。 Well， decades ago when C。😊。

They didn't give us a person data type。 All we have is int and float and char and bull and string and so forth。

Person was not among the available data types， but we can invent our own data types。 It turns out。

 So in C what we can do if we want persons to exist and every person in the world shall have a name and a phone number for now。

 we can do this。 string name， string number。 Now， that's a decent start。

 but it's gonna be kind of a stupid implementation。 If I then just do name string name one。

 string name2， string name 3， string name4。 We've already started down that road last week and decided array were a better solution。

 But here's an alternative when you want to just store related data together。

 I can use these two keywords in C type def struck。

 which albeiterse just means to a new type that is a data structure。 So multiple things together。

 inside the curly braces。 you literally put the two things you want to relate together， string name。

 string number， and then outside the curly braces， you specify the name you want to give to this brand new custom type that you have invented。

 technically styyllistically， you'll see that style。

preferfers that the name actually be on the same line as the last curly brace。

 which looks a little weird to me。 But that's what industry tends to do。 So so be it。

 But these several lines together tell C invent for me a new data type called person and assume that every person in the world has a string called name and a string called number。

 And now I can use this new data type in my own code to solve this problem a little bit better。

 So in fact， let me go ahead and do this as follows。 I'm going go back to V code here。

 And at the very top of my code above main just to make this available to not only main。

 but maybe any future functions I write。 I'm going say type defstruct as we saw on the screen inside of my curly braces。

 I'm gonna say string name and string number。 And then I'm gonna name this thing person。

 now I'm going go about using this。 And I'm going go ahead and delete my previous honor system approach of having names and numbers in separate arrays。

 And I'm instead going give myself in。😊，Of people we could call it persons。

 but I'm trying to be somewhat grammatically correct。

 So I'm gonna say people bracket 3 to give myself an array called people inside of which is room for three persons inside of which is room for a name and number each。

 So how do I now initialize these values。 I'm gonna to hard code them that is type them manually。

 But you can imagine using get string or get or some other function to get this data from the human themselves。

 I'm gonna say go to the people array at location 0 and access the name field。 And this is syntax。

 we haven't seen yet， but it's not that hard。 you literally use a dot a single period to say go inside of that structure and access the name field。

 the name attribute。 So to speak， and let's set that equal to Kelly。

 Then let's go into that same array location， people bracket 0 and set the number for the zeroth person to B plus 1。

6，1，7，4，9，5，1000。 Then let's go ahead and do the same thing for people bracket 1。

Set that person's name to， for instance， mine， David。

 then let's do people bracket1 dot number equals quote unquote same as Kelly because we're both in the directory So plus 1。

6，17，49，5，1000 and then lastly， people bracket2 dot name equals quote unquote John for John Harvard people bracket2 dot number equals plus19。

4，94，6，82，7，5，0 in this case。 And now the rest of the code is almost the same。

 I'm going now on the new line 24， still ask the user what name they want。

 I'm going still iterate from 0 to 3 because there's still three elements in this array。

 even though each has two values within and I'm going compare now not names。

 but people bracket I dot name to go access the name of that Ih person and compare it to the name that the human has typed in。

 And when I find that person， I'm going go into the people array at location I but print。

The number instead。 So all we've done here is add this dot notation。

 which allows you to access the inside of a data structure and all we've done is introduce up here some new C keywords that let you invent your own data types inside of which you can put most anything you want。

 I have chosen a string name and a string number。😡，Alright。

 let me go ahead and open my terminal window and clear it from before。

 Let me do make phone book to make this version。 So far so good。 make phone book enter。

 I'm gonna go ahead now and search for say John， And I have again， found his number。

 So this is still correct。 But even though this took more minutes in terms of the voice over。

 And it took more lines of code。 it's arguably better design now because at people bracket 0 is an actual person in everything about them at people bracket1 is another person and everything about them and so forth。

 This is what we mean by encapsulate。 You can think of these curly braces as sort of hugging these data types inside of the data structure together So as to keep them together in the computer's memory as well。

😊，Any questions？On this here technique and this building block of inventing your own types。



![](img/8aeeb4ffa4b647567df757f10b8cf92c_7.png)

And data structure。Allright， well， just to set the stage literally。

 as we'll strike the lockers and put something else up。The efficiency of binary search。

 as implemented by Caitlin， was predicated on Kelly having in advance， sorted the values upfront。

 But， of course， we've only considered now the running time of searching for information。

 using two algorithms， and there can be many others in the real world。

 But those are two of the most canonical。 We found that binary search was faster。 Then linear search。

 but it required that we sort the data。 So to your question earlier。

 maybe we should consider just how expensive it is in terms of time， money。

 space humans to sort data， especially a lot of data。

 and then decide whether or not it's worth using something like binary search or perhaps even something else。

 So the next problem will solve today ultimately is given generic input and output。

 the input to our next problem is going to be unsorted data。 So like numbers out of order。

 the output of which should be sorted data。 So for instance， if we pass in 7，2，5，41，6，0，3。

 I want whatever black box is implementing my sorting algorithm to spit out 0，1，2，3，4，5，6，7。

 So that's gonna be the question we answer。 But first， I think it's time for some。Delightful。

 hello pandas， chocolate biscuits。 Let's take a 10 minute break and snacks are now served。Alright。

 we are back and recall that the cliffhanger on which we left was that how do we go about sorting numbers。

 Well， here are some numbers，8 of them， in fact， from 0 to 7， but currently unsorted。

 We don't quite have enough monopoly boards for everyone。

 But we do have some delightful Super Mario Brothers Pez dispensers。

 If I could get 8 volunteers for this final demo up here。 Oh not lie a lot of hands。 Okay， Allright。

1，2，3，4，5，6。 And let's go farther back 7 and 8。 How about。 I come on up。😊。

Hopefully I counted properly， come on over。Upon arrival at the stage。

 go ahead and grab your favorite illuminated number。

And stand in that same order at the front of the stage， if you all could。Welcome to the stage。

 all right， grab your favorite number， stand in that same order。All right。Good， and 1，2，3，4，5，6。

 I definitely said 1 through 8。 Who is the number 8。 then Okay， we need 8。 come on down。 Alright。

 well， technically we need  four， but come on down。 Yeah， Allright。

 grab the four and let me start from this end first。

 If you want to give a quick hello and a little something about you。 Hi， my name is Cameron。

 I'm a first year。 and I want to study mechanical engineering。😊，Welcome， hi， I'm Charlotte。

 I'm also first year， and I'm in Canada F。Welcome。Hi， I'm Ella。

 I'm also a first year and I'm in Thaer。Hi， I'm Pre。 I'm also first yearmy there。😊，Hi， I'm Michael。

 I'm just an Even bright guest。Hi， I'm Marie， I'm a first year and I'm in Canada。Hi， I'm Rick。

 I'm a first year， and I'm in wholeworthy。I'm Jaden， I'm a first year at Howorthy。

 and I really like free stuff。well， let's see then if we can't award all these supermarket but there's Pes dispensers。

 the first notice of course， that all eight of our volunteers are completely out of order。

 but in an ideal world we would have the smallest number over here。Don't go over there， number0。

Wait a minute。7even， take over here。2， okay， okay， make yourselves look like that。No pes， Allright。

 so 7，2，5，4，1，6，0，3。 Okay， we won't do the introductions again。

 But now we have a list of numbers completely out of order。

 And wouldn't it be nice if 0 were eventually over here。

7 were all the way over there and everything else was sorted from smallest to largest。 Well。

 if you all could go ahead and sort yourselves from smallest to largest， go。😊，Allright， And Jaden。

 what was your algorithm for doing that。I。I I know that I have the least number because I don't think anybody has a number less than  zero。

 So I put myself at the last bottom line。 Okay， and I assume precious what was your algorithm。

 I you had the largest numbers。 So I just had to be at the end of the Okay， fair。

 So you guys got the easy ones。 number four。 How about。I knew3 was before me and5 was after me。 Nice。

 The number 4 didn't actually have to move coincidentally， but as for 5 and 3 and 2 and 1 in 6。

 they probably had to take into account some additional information。 Who's to their left。

 who's to the right， And it kind of worked， but it didn't look very algorithmic， if you will。

 It looked very organic and obviously correct。 but I'm not sure that same approach would work well if we not 8 but 80 or 800 or 8000 pieces of data。

 So let's see if we can't formalize this a little bit， Let me take the 。

 if you guys could reset yourselves to those same original positions from 7 on the left to 3 on the right。

 let me propose a couple of algorithms， Canonical ones， if you will。

 But see if maybe we can't formalize step by step， what to do。

 So the first one I'm gonna do given all of these numbers is just try to select the smallest number why to Jaden's earlier。

 I just want to put the smallest number over here， least that's a problem I can solve very well defined It's a nice out of the problem。

 So smallest so far2 that smaller。 I'm gonna remember that two is the now smallest number I've seen not5。

 not for one。Even smaller。 So I'm gonna remember  one， not 6，0。 That's pretty good。

 but I'm gonna check the whole list。 Maybe there's negative one or something like that。 but no 3。

 So I'm gonna remember that 0 was the smallest element I found。

 let's select Jaden and put Jaden over here。 but before precious or anyone else moves。

 We don't really have room for you。 like precious is in the way。

 because if this is an array of 8 values for integers。

 we can't just kind make room over here because if you think back to last week。

 we might have some garbage values there or something else is going on。

 we don't want to change data that doesn't belong to us。 So what to do with Well maybe precious。

 maybe you can go over there。 So you just take Jadens spots and we'll swap these two values accordingly。

 now though Jaden is in the right space， which is good because now I can move on to the second problem。

 What's the next smallest element that's presumably greater than 0。 Well， at the moment。

2 is the next smallest element， not 5， not for1 is the next smallest element。

 I'm gonna remember that， not 6， not 7， not 3。 Okay， so number one。

 if you could go to the right location。 But I'm afraid we're gonna have to evict number 2。😊。

To make room。 All right， let's do this again。0 and1 are in good shape。

 So now I think I can ignore them as complete。5 is the current smallest。 Nope，4 now is nope。

2 now is6， No 7， No 3， No， okay， so2 is the next smallest。 So let's swap 2 and 5。

 And now I've solved 3 out of the eight problems。 Let's do this again。4 is at the moment。

 the smallest， not 5， not 6， oh3 is the now smallest。 So let's swap 3，4 and 3。

 which unfortunately is making the four problem a little worse。 Like he belongs there。 it seems。

 but I think we can fix that later。 So now half of the list is sorted。5 is the next smallest 6 and 7。

 now we've got to fix the4。 So4 goes back there。 now I messed up the5。 but it will come back to that。

 All right，6，7， Okay，5， let's put you where 6 is。 And now one more mistake to fix。 So 7。

 okay 6 and 7 need to swap。 And now I've solved 8 problems in the aggregate。 So it's complete。

 Now to be fair。 My approach is clearly way slower than your approach。

You all were working in parallel， whereas I was doing it more methodically step by step。

 And I dare say my algorithm is probably gonna be more translatable to code。 And indeed。

 what I just acted out is what the world would call selection sort， whereby on each iteration。

 each pass in front of the humans。 I was selecting the smallest element I could find。 Alright， what。

 how else could I do this， though， let's do something that's maybe a little more organic like your approach where you were actually comparing who is next to you。

 go ahead and reset yourselves one final time to this arrangement，7 on the left，3 on the right。

 and let me propose again to walk through the list again and again。

 But let me focus more narrowly on the problem right in front of me。

 because I felt like I was taking a lot of steps back and forth back and forth。

 Maybe we can ship away at some of that wasted time。 Let's compare 7 and2。

 They're obviously out of order。 So let's just immediately swap you to， if we could。 Allright， now。

7 and 5，Clearly out of order。 Let's swap these two，7 and 4 out of order。 Let's swap these two。

7 and1 out of order。 Let's swap these two。😊，7 and 6 out of order。 Let's swap these two。

7 and 0 out of order。 swap these two，7 and 3 out of order。 swap these two。

 So a lot of work for precious there。 But I've now indeed solved one of the8 problems。 Moreover。

 I don't need to keep addressing the seven problem because notice that Pre has essentially bubbled her way up to the end of the list。

 And indeed， that's gonna be the operative term here。

 Another algorithm that computer scientists everywhere。 No is called bubble sort。

 whereby the goal is to get the biggest elements to just bubble their way up to the top of or the end of the list 1 at a time。

 Now， am I done no， clearly not， there's still stuff out of order， except for precious。 Indeed。

 I have solved one of these eight problems。 And now， fine， I'll go back。

 And I'm just gonna try the same logic again，2 and5， good5 and 4， Nope swap those，5 and1。

 Nope swap those。😊。

![](img/8aeeb4ffa4b647567df757f10b8cf92c_9.png)

5 and 6 are good。6 and 0。 no swap those，6 and 3。 nope swap those。

 And I already know that Pre is where she needs to be。

 So I think I'm done with the second of8 problems。 And I'll do this a little faster now，2 and 4。

4 and1。 swap，4 and 5 are good，5 and 0， swap 5 and 3， swap。 And now we solve three problems。

 Let me reset2 and 1， swap 2 and 4 are good，4 and 0。 swap，4 and 3 swap。

 And now I've solved half of the problems，4 out of 8， we're almost done。1 and2 are good，2 and 0。

 swap，2 and 3 are good。 Okay， and now we're done with 5 out of the8 problems，1 and 0。 swap。😊。

1 and two are good。 Those are all good。 And let me just do a final sanity check。

 Everything now is sorted。 So now I'm done solving all eight of those problems。

 So you all were wonderful。 We need the numbers back。

 But Kelly has some delightful Pez dispensers for you on the way out。 If you want to head that way。

 Just leave the numbers on the shelves and a round of applause for our eight volunteers for helping to act this out。

😊，Thank you。So let's see if we can't formalize what these volunteers kindly just did with us starting with the first of those algorithms。

 Thank you， namely selection sort。 Let's see if we can't slap some pseudocode on this thinking of our humans now as more generically in array。

 So we had the first person at location 0。 and we had the last person at location n-1。

 And just for clarity so that you've kind of seen the symbology。

 this obviously is going to be location n-2， this is location n -3 and so forth until sort of dot dot dot。

 you hit the other N that we've already written now。

 So that's just how we refer to all of our eight volunteers locations。 or in this case，1，2，3，4，56。

7 locations。 but dot dot dot in the middle connoting that this can be a much， much larger array。

 So here's some pseudocode for the first algorithm selection sort for I from 0 to n-1。

 So from the first element to the last element。 find the smallest number between the numbers。

 bracket I and numbers bracket n -1。😊，If you're starting I at 0。

 look at specifically every lighted number between location 0 and location n-1。

 When you have found that smallest element， swap it with the number at location I。

 which starts again at 0。 That's how we got， I think jaden into place at the very beginning。 Then I。

 by nature of how four loops work gets updated from 0 to 1。 So that we do the same thing。

 find the smallest number between numbers bracket 1。

 So the second element through the eighth element because this number unchanged。

 and is the total number of value。 So the end point there is not changing。

 Once we found the second smallest person， we swap them with location I aka1。

 And that's how we got the number one into position。 And then number two。

 and then the number3 and number 4。 So this then was selection sort in pseudocode form。

 And that allowed us to actually go through this list， again and again and again。

 in order to find the next smallest element。 So it was happening a little more methodically。

 if it helps just to map。symbology of the bracket notation in the eyes。

 If this is where we started with location I。 and we did everything between location n-1。

 essentially， I traversed this whole list from left to right。

 literally walking in front of our volunteers looking at each element。

 And the first element I saw was 7 at the moment that was the smallest element I had found and who knows in a different list。

 maybe 7 would be the smallest element。 So I kind of stored it in a variable in my mind。

 But I checked then two and remember no no，2 is clearly less than now I'm gonna remember2。

 Okay now I'm gonna remember one when I find it。 and then I'm gonna remember0 when I find it。

 And then what I did once I found jade in it with the value of 0。 light it up。

 I moved that location to here and then evicted precious recall and moved precious over to that location that we had freed up。

 Why why all this sort of back and forth。 Well， you have to assume with an array that you're not entitled to the memory over here。

 you're not entitled to the memory over here。 if you've already decided that you have 7 lockers or 8 people you have to commit the。

😊，Comp in advance。 That's why we put the number typically in the square brackets or the compiler infers from the curly brackets how big the array actually is。

 All right， and suffice it to say when I went through this again and again and again。

 I did the same thing over and over。 Now you might have thought me sort of dumb for having asked the same questions again and again。

 like I was surprised to discover the number one。 I was surprised to discover the number to two。

 even though on my very first pass， I literally looked at all eight of those numbers。

 But you have to think about what memory I'm actually using。

 Now I certainly could have memorized all of the numbers and where they are。

 But I proposed that just very simply， I was using like a single variable in my brain。

 just to keep track of the then smallest element。 And once I'm done finding that and solving that problem。

 I moved on to do it again and again。 but that's gonna be a trade off。

 and this is gonna be thematic in the coming weeks， whereby。

 sure you could use more memory and I could have been smarter about it。

 and maybe that would have improved or hurt the running time of the algorithm。

 there's often going be a tradeoff between how much memory or how much time。😊，You actually use。

 So we'll discover that over time。 So how fast or slow is selection sort。

 Well'll consider when I had8 humans on stage， I first went through all n of them。

 But how many comparisons did I make really， I was doing n-1 comparisons because if I've got n people。

 I've got to compare the smallest number I found against everyone else。

 and you compare n people left to write n-1 times total。 So the first pass， I was making。

 I was asking n-1 questions。 I this the smallest is this the smallest。

 is this the smallest n-1 times Once I solved one problem when we got Jaden into Jaden's right place。

 then I had one fewer problem。 Then one fewer， fewer problem and so forth。

 So it was like n-1 steps plus n-2 steps plus n-3 steps plus dot dot dot1 final step once I got to the final of the eight problems。

 Now， if you remember of the cheat sheet at the back of your math books say growing up。

 you'll note that this series here can be more simply n is n times n-1 all divided by  two。😊。

And if you've not seen that before， just take on faith that this is identical to this series of numbers up here。

 So now we can just kind of multiply this out。 So that's technically n squared minus n all divided by2。

 which is great。 if we multiply that out， that's n squared over 2， minus n over 2。

 We're getting  two into the weeds。 Let's whip out our big O notation。 Now。

 whereby we can wave our hands at the lower order terms。

 only care about the biggest most dominant term， which mathematically in this expression。

 If you plug in a really big value of n， which is gonna to matter more， the n squared the two。

 the n or the two。😊，Like the n squared， like the others absolutely contribute to the total value。

 But if you plug in a really big value， the dominant force is going to be this n squared because that's really going blow up the total value。

 So we can say that selection sort when analyzed in this way。

 it's on the order of n squared steps because I'm doing so many comparisons so many times。

 So if that's the case， the question then is。What is indeed not just its upper bound。

 but maybe it's lower bound， as we'll eventually see。 So for selection sort for now。

 let's stipulate that it's indeed in big O of n squared。

 And that's actually the worst of the algorithms we've seen like that's way slower than linear search because at least linear search was big O of n selection sort is n squared。

 which of course is n times n， which is and will feel much， much slower than that。

 So what if though we consider the lower bound of selection sort。 maybe it's bad in the worst case。

 but maybe it's really good when the numbers are mostly sorted unfortunately。

 this is the same pseudocode for selection sort， we make no allowance for checking the list to make sure it's already sorted。

 And in fact， that's kind of a perverse case to consider for any algorithm。

 What if the problems already solved How's your algorithm can perform。

 Like if all of my volunteers is they kind of almost did accidentally。

 they started lining up roughly in order。 suppose they literally have been in order from 0 to 7。

 Well， my stupid algorithm， would still have me walking back and forth back and forth back and forth why。

 because the code literally tells me。Do this this many times。 And every time I do that。

 find the smallest element。 So it's gonna be sort of a stupid output because the list is not gonna be any change it at all changed。

 but my code is not taking into account in any way， the original order of the number。

 So no matter what this is to say that if we consider whether the lockers of the humans。

 the omega notation for this algorithm。 Even in the best case where the data is already sorted is crazily also n squared。

 Now， I could certainly change the pseudocode。 But selection sort as the world knows it is more of a demonstrative algorithm or sort of a quick and dirty one Its running time is going to be in omega of n squared。

 And now we can actually deploy our theta notation because the big O notation is n squared。

 And the omega notation is n squared one in the same。

 we can also say that selection sort is in theta of n squared。

 which is not great because that's annoyingly slow。 So maybe the solution here is don't do that。

 let's use bubble sort。 instead， the second algorithm where I just compared everyone side by side again。

Again， well， heres some pseudocode for bubble sort。

 which you can assume applies to the same kind of array from 0 on up to n -1。

 Here's one way to write bubble sort。 Repeat the following n times for I from 0 to n -2。

If the number at location I and the number at location I plus one are out of order。Swap them。

And there's kind of an elegance to this algorithm。 And that， like， that's it。

 And you just assume that when you go through the list， this is how from I from 0 to n -2。

 this is how I was effectively comparing elements 0 and 1，1 and 2。2 and 3，3 and 4， dot， dot， dot 7。

6 and 7。 But notice， I didn't say 8， there were8 total people。

 Why do we go from 0 to n-2 instead of from 0 to n-1。Yeah。呀。Not quite。

 So it's not that we've already checked the last 1。 I'm saying with this line of code here。

 we never even go to n -1 technically if we。Exactly， because we're doing this simple arithmetic here。

 We're checking current location I plus one， you can think of these as my left and right hand。

 Left hand is pointing at 0。 right hand is pointing at1。

 I don't want to do something stupid and have my left hand point at n-1。

 because then our right hand arithmetically when you add one， is's going point at N。

 which does not exist。 That's beyond the boundary of the array because the array goes from 0 to n-1。

 So just a little bit of a safety check there to make sure we don't walk right off the end of the array。

 But we do this n times， because recall that precious ended up being where 7 needed to be at the very end of the list。

 but that didn't mean there weren't 77 more problems still to solve0 through 6。 So I did it again。

 And I did it again And per its name bubble sort。 the biggest element bubbled up first than the next biggest than the next biggest than the next biggest that is 7 and 6 then 5 and4 and we got lucky on some of them。

 But eventually we finished with 0。 So how do we analyze this thing。

 Well we could also technically do this n-1 times as an aside if。

Thinking through that I'm wasting some time because we get one for free。

 Once we get to solving seven problems， you get the eighth one for free because that person is obviously where they need to go。

 So when we had these numbers initially， and we were comparing them with bubble sort， again。

 Left hand right hand， It's like treat this as I。 This is I plus1。

 And we just kept swapping pairwise numbers， If in fact， they were out of order。

 So all this is saying is what are humans were doing for us organically。

 So how do we actually analyze the running time of this Last time I just kind of spitball that it was n plus-1 steps plus n-2 steps。

 Well you can actually look at pseudocode sometimes。 And if it's neatly written。

 you can actually infer from the pseudocode， how many steps each line is going to take。 For instance。

 how many steps does this first line take。😊，I mean， like literally n-1。

 The answer is right there because it's saying to the computer or to me acting it out。

 repeat the following n-1 times。 Allright， so that's helpful。 How many line。

 how many steps does this inner loop induce。 Well， you're going from I to n -2。

 So that's actually n-1 total steps not N。 And then this question here。

 if numbers bracket I and numbers I are out of order。 It's a single question。

 It's like our Boolean expression， We'll call it one。 I mean。

 maybe you need to do a bit of more work than that。

 But it's a constant number of steps doesn't matter how big the list is comparing two numbers is always gonna take the same amount of time。

 And then swapping them， Oh， I don't know it's gonna take like one or two or three steps。

 but constant doesn't matter which the numbers are takes the same amount of work。 So let's stipulate。

 let me rewind stipulate that the real things that matter are the loops。

 these constant number of steps， who really cares。 But the loops or what are gonna add up is n gets large。

 So this really then is if this is the outer loop。 And this is the inner loop。

 Think about our two dimensional。Mario Square from week1。

 we did something on the outside and then something on the inside to get our rows and columns。

 This is equivalent to n -1 times n -1。 If we do our little foil method。

 n squared minus n minus n plus1， combined like terms， n squared minus2 n plus1。 Who cares。

This is ultimately going be on the order of big O of。N squared only because again。

 if you ask yourself， when I plug in a really big value for n。

 which of these is really gonna contribute most to the answer。

 it's obviously gonna be n squared again， and we can ignore the lower order terms。

 So this doesn't seem to have made any progress。 like selection sort was on the order of big O n was on the order of n squared。

 bubble sort based on this analysis is also on the order of n squared。

 maybe we're getting lucky in the lower bound。 So on the upper bound for bubble sort。

 It's indeed n squared as was selection sort。 But with this pseudocode for bubble sort。

 unfortunately， rather， unfortunately， we were not doing anything clever to catch that perverse case where maybe the list was already sorted。

 After all， consider if the list was sorted from 0 to 7。

 I was still asking all the same darn questions， even if I did no work。

 I was gonna repeat that n-1 times back and forth， making no swaps。

 but making all of those comparisons。 But here's an enhancement to bubble sort that we can add that selection sort didn't really have room for。

 I can say after one pass。Of this inner loop， walking from left to right， If I made no swaps， quit。

 because otherwise， it's like being a crazy person。

 if I just go back and forth and back and forth without doing any work， Like。

 what's the point of all of that， Let me just stop and actually quit， if indeed。

 I've done no work at all。 So put another way， if I traverse the list from left to right。

 I make no swaps。 I might as well just terminate the algorithm then because there's no more work clearly to be done。

 Alright， so based on that modification， the lower bound of bubble sorts running time would be said to be an omega than of。

N， because I'm minimally going need to make one pass through the list。

 You can't possibly claim that the list is sorted unless you actually check it once。

 And if there's n elements， you're gonna have to look at all n of them to make sure that it's an order。

 But after that， if you've done no work and made no swaps。

 no reason to traverse the list again and again and again。

 So a bubble sort can be said to be in omega of N， because indeed。

 we can just terminate after that single pass。 If we've done no work。

 We can't say anything about theta， because they're not one in the same big O and omega。

 but that does seem to have given us some savings。 Unfortunately。

 it really only saves us time when the list is already or mostly sorted。

 But in the average case and in the worst case， odds are。

 they're both going to perform just as bad on the order of n square。 In fact。

 let's take a look at a visualization that'll make this a little clear than our own humans and voices might have。



![](img/8aeeb4ffa4b647567df757f10b8cf92c_11.png)

Explained here is a bunch of vertical purple bars made by a friend of ours in the real world。

 And this is an animation that has a bunch of buttons that lets us execute certain algorithms。

 A small bar represents a small number， a big bar represents a big number and the goal is to get them from small numbers or small bars to big numbers or big bars left to right。

 So I'm gonna go ahead and click on selection sort initially。

 And what you'll see from left to right is in pink。

 the current smallest element that's been discovered。 but also in pink。

 the equivalent of my walking across the stage left to right again and again and again。

 trying to find the next smallest element。 And you'll see clearly。

 just like when we put jaden at the far left， the smallest element ended up over here。

 But it might take some time for precious， for instance。

 or number 7 to end up all the way over on the right， because with each pass。

 we're really just fixing one problem at a time。 And theres n problems total。

 which is giving us on the order of those n squared steps。 And now though this is getting shorter。

 So at least doing some work that you don't have to keep touching the。😊，You already sorted。

 which just like I was。 So now selection sort is complete。 Let's visualize instead bubble sort。

 So let me rerandomize the array。 just so we're starting with a random order。

 Now let's click on bubble sort。 and you'll see the pink bars work a little differently。

 It connotes which two numbers are being compared at that moment in time。

 just like my left hand and right hand going left to right。

 And you'll see that even though it's not quite as pretty as selection sort where I was getting at least the smallest elements all the way to the left here。

 we're just fixing pairwise problems。 But the biggest elements like precious is number 7 are indeed bubbling their way up to the top one after the other。

 But as you can see， and this is where n squared is sort visual visualizable。

 We're touching these elements or looking at them so many times again and again。

 we are making so many darn comparisons。 this is taking frustratingly long。

 And this is only what a few dozen bars or numbers you can imagine how long this might take with hundreds。

 thousands or millions of values。 I dare say we're gonna have to do better。Then bubble sort and。

Selection sort， because we're not stunned even yet。

Just trying to give the satisfaction of getting to the end。 And now we are。

 But neither of those algorithms seems incredibly performant because it's still taking us quite a bit of time to actually get to that their solution。

 So how can we actually do better than that。 Well， we can try taking a fundamentally different approach。

 And this is one technique that you might have encountered in math or even in the real world。

 even if you haven't sort of applied this name to it。

 recursion is a technique in mathematics and in programming that allows you to take sort of a fundamentally different approach to a problem。

 And in short， a recursive function is one that's defined in terms of itself。

 So if you had like F of x equals something on the right hand side of a mathematical expression that would be recursive in that the function is dependent on itself。

 more practically in the world of programming， a recursive function is a function that calls itself。

 So if you are writing some function in C and in that function， you call yourself。

 You actually have a line of code that says call that。😊。



![](img/8aeeb4ffa4b647567df757f10b8cf92c_13.png)

Same function by the same name。 That function is recursive。 Now。

 this might feel a little weird because if a function is calling itself。

 It feels like this is the easiest way to get into an infinite loop。

 because why would it ever stop if the function is calling itself calling itself calling itself calling itself。

 we're gonna have to actually address that kind of problem。 But in the real world。

 we've or rather in this class already， we've actually seen implicitly an example of this。

 including today， as well as in week 0。 So heres that algorithm for searching the doors of the lockers and recall that after we did this check at the very top。

 if there are any doors left， return false not， we did these conditions。

 we said if the numbers behind the middle door return true because we found it。

 But things got interesting here where I said else if the number is less than the middle door。

 then search the left half if the number is greater than the middle door， then search the right half。

 Well， at that point in time， you should be asking me or yourself， how do I search the left half。

 How do I search the right half。 Well， here you go。 like on the。😊。

Screen right now is a search algorithm。 And even though it says down here。

 search the left half or search the right half， which is like， well， how do I do that。

 We'll just use the same algorithm again。 And this is how in terms of my voiceover。

 you end up searching the left half of the left half or the right half of the left half or any such combination。

 This line here， search left half， This line here， search right half is representative of a recursive call。

 This is an algorithm or a function that calls itself。 But why does it not induce an infinite loop。

Like， why is it important that this line and this line are written exactly as they are So as to avoid this thing just forever searching。

Aimlessly， yeah。We do have this condition at which it stops。 But more importantly。

 what is happening before I make these recursive calls。Exactly， I'm recursing that is calling myself。

 but I'm handing myself a smaller problem， a smaller problem， a smaller problem。

 It would be bad if I just handed myself the exact same number of doors and just kept say。

 search these， search these， search these because you would never make any progress。

 But just like our volunteers earlier so long as we did divide and conquer and we search smaller and smaller numbers of doors。

 eventually indeed， we're gonna bottom out and either find the number we're looking for or were not。

 So generally， we're gonna call these kinds of conditions that sort of just ask a very obvious question in one in immediate answer。

 base cases， base cases are generally conditionals that ask a question to which the answer is gonna be yes or no right then and there。

 a recursive case by contrast。 these two down here is when you actually need to do a bit more work to get to your final answer。

 You call yourself。 But with a smaller version of the problem。 So we could have， in fact。

 in week 0 have written this sort of similarly， if you go back in your mind to week 0。 we。



![](img/8aeeb4ffa4b647567df757f10b8cf92c_15.png)

More of a procedural approach。 so to speak， when we were searching the phone book。

 I propose that this induced what we called loops on line 8 and line 11， which is literally said。

 go back to line 3。 And that was more of a mechanical way of sort of inducing a loop structure。

 But if I really want to be elegant。 I could have said， well， you know what 7 and 8 together。

 really just mean search the left half。 And 10 and 11 together。

 really mean just search the right half。 So let's condense these pairs of lines into shorter instructions search the left half of the book。

 search the right half of the book。 I can then delete two blank lines。

 And now I have a recursive algorithm for searching a phone book。

 It's a little less obvious because you have to ask yourself when you get to line 7 or 9。

 Wait a minute， how do I search the left half or the right half。

 And that's when you need to realize you start the same algorithm again。

 But with a problem that's half as large。 in week 0。

 we do the procedural approach where we literally tell you what line of code to go to But today。

 we're offering a different formulation， a recursive approach where it's more implicit what you to do。

 And we'll see now a couple of。😊。

![](img/8aeeb4ffa4b647567df757f10b8cf92c_17.png)

amples from the real world。 so to speak。 So here's a screenshot from Super Mario Brothers1 on the original Nintendo entertainment system。

 Let me go ahead and get rid of some of the distraction like the ground and the mountains there and here we have a sort of half pyramid。

 not unlike that you implemented in a problem set one。

 But this is an interesting real world physical structure and that you can define it recursively like what is a pyramid of height4。

 if you will， Well， just to be a little little difficult。

 ayramid of height is really just a pyramid of height 3 plus one more row。 Okay well。

 what is a pyramid of height 3。 Well， pyramid of height3 is really just a pyramid of height 2 plus one more row。

 Well， what's pyramid of height2， Well pyramid of2 is really just a pyramid of height 1 plus one more row。

 Well， what's a pyramid of height 1 a single brick on the screen。

 And I sort of change my tone with that last remark to convey that this could then be our base case。

 whereby I just tell you what the thing is without。😊。

Sor of kicking the can and inviting you to think through what a smaller structure is plus one more row。

 whereas every other definition I gave you， then of a pyramid of some height was defined in terms of that same structure。

 albeit a smaller version thereof。 So we can actually see this in the real world。

 Let me go ahead and pull up one thing here。 I'm gonna go to give me one sec before I flip over。

 here I am on Google dot com。 If you'd like a little computer science humor here。

 If you ever Google search for recursion and hit enter。



![](img/8aeeb4ffa4b647567df757f10b8cf92c_19.png)

![](img/8aeeb4ffa4b647567df757f10b8cf92c_20.png)

You'll see。A joke that computer scientists at Google find funny。Ha ha，1，2， laughs。

 Does anyone see the joke。 I did not make a typo， but Google's asking me， did I mean recursion。

 And if I click on that， I just get the same haha page。Okay， all right。

 that didn't go over well Anyhow。 So there are these Easter eggs in the wild everywhere because computer scientists are the ones that implement these things。

 But let's go ahead and actually implement， for instance， a version of this encode。

 Let me go back over here in a moment to V S code。 And in V。 S code。

 let me propose that in my terminal window。 Let me create one of two final programs。

 This one is gonna be called iteration dot C just to make clear that this is the iterative that is loopbased version of a program whose purpose in life is to print out a simple Mario pyramid。

 I'm gonna go ahead and include C50 dot H at the top as well as standard I O dot H。

 I'm not gonna need string dot H。 I don't need any command line arguments today。

 So this is going to start off with main void。 And now I'm gonna go ahead and ask a question like give me a variable called height of type integer。

 and ask the human for the height of this Mario like pyramid。

 And then let's assume for the moment that I've already implement a function called draw whose purpose in life is to draw a pyramid of that height semicolon。

😊。

![](img/8aeeb4ffa4b647567df757f10b8cf92c_22.png)

abstracttracted away for the moment， the notion of drawing that pyramid。

 Now let's actually implement draw whose purpose in life again is to print out a pyramid akin to the one we saw a moment ago like this here on the screen。

 Well， in order to print out a pyram of a given height。

 I think I need to say void draw int n for instance because I'm not gonna bother returning a value。

 I just want this thing to print something on the screen。 So void is the return type。

 but I do want to take as input an integer like the height of the thing I want to print。

 I can call this argument or or anything I want， I'll call it n for number。

 So how can I print out a pyramid that again looks like this。 Well。

 I'll do this quicker than you might have in problem set1， but seems obvious that on the first row。

 I want one brick on the second row I want to on the third I want3 on the fourth I want4。

 So it's actually a little easier than problem set1 in that it's sloped in a different direction。

 So let me go ahead and do exactly this in code。 let me say int I equals 0 I less than n the height I plus plus。

So this is going be really for each row of the pyramid pyramid。

 Let me go ahead now And in an inner loop for int J equals 0。 Let's do J less than。

I plus one for reasons we'll see in a moment。 And then J plus plus。 and then inside of this loop。

 let's just print out a single hash， no new line。 But at the end of the row。

 let's print out a single new line to move the cursor to the next line。 Now， why am I doing this。

 Well， this represents for each column of pyramid。 And if you think about it on the first row。

 which is row 0， I actually want to print not0 bricks， but one brick。

 So that's why I want to go ahead here and go from 0 to I plus 1。 because if I is 0， I plus1 is1。

 So my inner loop is going go from 0 to 1， which is gonna give me one brick。

 It's a little annoying to think about the math。 But this just make sure that I'm actually getting bricks in the order I want them。

 And then it's gonna give me two bricks and then 3 and then 4。 And between each of those rows。

 it's gonna print a new line。 So let's go ahead and do make iteration to compile this code。

 I messed up。😊，Why do I have a mistake online。8 of this code。

 Let me hide my terminal and scroll back up。 It seems clang。

 My compiler does not like my draw function。Yeah。Yeah， I forgot the prototype。

 So this is the one and only time where it seems reasonable to copy paste。

 Let's grab the prototype of that function up here and go ahead and teach the compiler from the get go what this function is gonna look like。

 even though I'm not defining it now until line 13 onward。

 Allright let's go ahead and make iteration again。 dot s iteration enter。

 Let's do height of say4 and vo Now I've got that there pyramid。

 So I did it a little quickly and it's certainly to be expected if it took you hours on problem set1 to get the other type of pyramid printed。

 But the point for today is really to demonstrate how we can print a pyramid like this。

 using indeed what I'd call iteration iteration just means using loops to solve some problem。

 but we can alternatively use recursion by reimplementing our draw function in a way that's defined in terms of itself。

 So let me go into my code here。 And I'm actually gonna leave the prototype the same。

 I'm gonna leave main the same。 But what I'm gonna go ahead and do is delete all of this iterative code。

 that's doing things very procedures。

![](img/8aeeb4ffa4b647567df757f10b8cf92c_24.png)

![](img/8aeeb4ffa4b647567df757f10b8cf92c_25.png)

Step by step by step with loops。 And I'm instead going do something like this。 Well。

 if I want to print a pyramid of height N。

![](img/8aeeb4ffa4b647567df757f10b8cf92c_27.png)

What did I say earlier， Well， a pyramid of height n is really just a pyramid of height n-1 plus one more row。

 So how do I implement and code that idea， Well， let me go back and code here and say， well。

 if a pyramid of height n first requires drawing a pyramid of height n-1。

 I think I can just write this， which is kind of crazy to look at。

 But because you're calling yourself in yourself But let's see where this takes us。

 once I have drawn a pyramid of height n-1。 That is a height 3， for instance。

 what remains for me to do is to myself， print one more row。 And so to print one more row。

 I think I can do that really easily with fewer loops， I can do4 int I equals 0。

 I less than n I plus plus， and then very simply in this loop。

 I can print out a single hash1 at a time at the end of this loop， I can print out a new line。

 But no more nesting of loops。 What I've done is print one more row and here I've done print。



![](img/8aeeb4ffa4b647567df757f10b8cf92c_29.png)

![](img/8aeeb4ffa4b647567df757f10b8cf92c_30.png)

![](img/8aeeb4ffa4b647567df757f10b8cf92c_31.png)

![](img/8aeeb4ffa4b647567df757f10b8cf92c_32.png)

A pyramid of height and  -1。I'm not quite done yet。

 but I think this is consistent with my verbal definition that a pym of height 3 is a pyramid sorry。

 A pyramid of height 4 is a pyramid of height 3， which I can implement per line 16。

 Just draw me a pyramid of height and -1。 And then I myself will take the trouble to print the fourth and final row。



![](img/8aeeb4ffa4b647567df757f10b8cf92c_34.png)

![](img/8aeeb4ffa4b647567df757f10b8cf92c_35.png)

![](img/8aeeb4ffa4b647567df757f10b8cf92c_36.png)

But something's missing in this code。Let me go ahead and try running it。 Let's see what happens。

 Make， oh， darn it。I meant to call this something else。 So I'm going to do this。

 I'm going to close this version here。 I'm going rename iteration dot C to recursion dot C to make clear that this version is completely different。

 Let me now go ahead and make the recursion version。

And Klang is noticing that I have screwed up on line 14。 It says error。

 all paths through this function will call itself。 And Klang doesn't even want to let me compile this code because that would mean literally。

 just forever。Loop effectively by calling yourself。

 So what am I missing in my code here if I open up what we're now calling recursion dot C。

In my editor。What's missing here over here。Yeah， I'm missing a base case。

 And I can express this in a few different ways。 but I would propose that before I do any drawing of anything at all。

 let's just ask ourselves if there is anything to draw。 So how about if n equals equals0。

 Well then don't do anything， just return。 You don't return a value when your return value is void。

 It means you don't return anything。 So you just return period or return semicolon or just to be super safe。

 I could actually do something like this， which is arguably better practice。

 just in case I get into this perverse scenario where someone hands me a negative number。

 I want to be able to handle that and not print anything either。 So just to be safe。

 I might say less than or equal to0。 I'm not doing one， because if I did do one。

 then I would want to at least myself print out one brick， which is fine。

 but I have to change all of my code a little bit。 So I think it's safer if my base case is just if n is less than or equal to0。

 you're done， don't do anything。 And this then ensures that even though thereafter。

 I keep calling draw again。 And again。And again， and the problem getting smaller and smaller from four to three to two to1。

 as soon as I hit zero， the function will finally return。😡，So let's go ahead and open up my terminal。

 rerun， make recursion to make this version did compile this time。 dot slash recursion。 enter。

 Let's type in 4， cross my fingers。And this， too， prints the exact same thing。

 And even though it doesn't look like fewer lines of code。

 I would offer that there is an elegance to what I've just done。

 whereas with the iterative version with all the loops， it was very clunky like step by step。

 just print this and print that and have a nested loop inside of another。 But with this。

 especially if we distill it into its essence by getting rid of my comments like this。 And frankly。

 I can get rid of the unnecessary curly braces， only because for single lines in conditionals。

 you don't need them。 like this is arguably like a very beautiful implementation of drawing Mario's pyramid。

 even though it's calling itself and arguably because it is calling itself。😊。

Questions then on this idea of recursion or this implementation of Mario， yeah。Good question。

 Are there any scope issues involved， short answer， No， However， the current value of I。

 for instance， will not be visible to the next time the function is called。

 It will have its own copy of I。 If that's what you mean。

 And we'll next week talk in more detail about what's going on here。 And in fact。

 I probably can't break this in class， very easily。

 But it turns out if I use a very large version for heights。

 let's just take a lot of zeros and see what happens。 that was too many。 let's see what happens。

 that's also too many， let's see what happens there。

That's the first time at least I in class have encountered this error。

 You might have encountered this weird bug in office hours or in your problem set。

 And that's fine if you did。 We'll talk about what this means next week， too。 But this is bad。

 Like this clearly hints at a problem in my code， However。

 the iterative version of this program would not have that same error。

 So this relates to something involving memory because it turns out as a little teaser for next week。

 each time I call draw， I'm using a little more memory， a little more memory， a little more memory。

 a little more memory in my computer only has so much memory。

 This program in its current form is using too much memory。 There are workarounds to this。

 but that is a tradeoff to the elegance we're gaining in this solution。

 So what's the point of all this And how do we gettracked by Mario。

 there's another sorting algorithm。 The third and final one that will consider today that actually uses recursion to solve the problem。

 not only elegantly arguably， but also way faster somehow than bubble sort and selection sort。

 In in essence， it does so by making far fewer comparisons and wasting a lot less work。😊。

It doesn't keep comparing the same numbers again and again。 Here， in its essence。

 is the pseudocode for merge sort。Sort the left half of the numbers。

 sort the right half of the numbers， then merge the sorted havealves。

 And this is kind of a weird implementation of an algorithm because I'm not really telling you anything。

 It seems like you're asking me how do I sort numbers。 And I say， we sort the left half。

 sort the right half。 It's like someone being difficult。 And yet。

 implicit in this third line is apparently some magic。

 This notion of merging haves that are somehow already sorted is actually gonna yield a successful result。

 as in aside， we're actually gonna need one base case here， too。 So if you're only given one number。

 you might as well quit right away， because there's nothing to do。

 So we'll toss that in there as well。 And base cases are often for 0 or one or some small sized problem in this case。

 it's a little easier to express it as one because if you have one element。

 it's indeed already sorted。 So what does it mean to merge two sorted haves。 Well。

 let's actually consider this。 I'm gonna reuse some of these same numbers here。

 I'm gonna put my one my three my 4 and my6 on the left。

 And these together represent a list that is indeed sorted。Of size 4。

 And then I'm gonna put four other numbers on the right there that are similarly sorted as well。

 And by merging these two lists， I mean， start at the left end of this list。

 start at the left end of this list。 And just decide one step at a time。

 which number is the next smallest。 And then I'm gonna put it on the top shelf to make clear what is sorted。

 So if my left hand's pointing at this list， My right hand's pointing it there。

 which hand is obviously pointing to the smaller element， left or right。Like the right。

 So I'm gonna grab this。 And I'm gonna use a little more space up top here and put the zero in place。

 And then I'm going point to the next element there。 So my left hand has not moved it。

 It's still pointing at the one。 My right hand is pointing at the two。

 which number comes next clearly。Left， so I'm gonna grab the one and put it up there and update where my left hand is pointing。

 So now I'm pointing at the three here and the two there。 What comes next。 Obviously， the two。

What comes next， Obviously， the three。What comes next， obviously the four。What comes next。 Obviously。

 the five。 But notice my hands are not going back and forth， back and forth， back and forth。

 like any of the algorithms thus far。 I'm just taking baby steps，  moving them only to the right。

 effectively pointing at for a final time each number once and only once What comes next 6。

 And now my left hand is done， what comes last the number 7。

 So what I just did is what I mean by merge the sorted haves。

 if you can somehow get into a scenario where you've got a small list sorted and another small list sorted。

 it's super easy now to merge them together using that left right approach。

 which I'll claim only takes n steps。 Why， because every time I asked you a question。

 I was taking one by out of the problem。 There's 8 by total。

 I asked you 8 questions or I would have if I verbalize them all So it's n steps total to merge lists of that size。

 So what then is merge sort merge sort is really all three of these steps together。

 only one of which we backed out two of which are sort of cyclical in nature。cursive by design。

 So what does this mean， Well， let's start with this list of8 numbers， which is clearly out of order。

6，3，4，1，5，2，7，0。 And let's apply merge sort to this set of numbers。

 And I'll do it digitally here because it'll take forever to keep moving the numbers up and down physically。

 So let's move it to the top just to give ourselves a little bit more room。

 And let me propose that we apply merge sort。 What was the very first step in merge sort。

 at least that we highlighted the juicy steps。😊，What's the first step in merge sort？

Sort the left half。 Yeah， and then the second step was gonna to be sort the right half。

 And then the third step was gonna be merge the sorted half。

 So let's see what this means by actually acting it out on these numbers。 So here's my8 numbers。

 Let's go ahead and sort the left half。 Well， the left half is obviously going be the four numbers on the left。

 And I'm just going pull them out just to draw our attention to them over here。

 Now I have a list of size 4。 And the goal is to sort the left half。 How do I sort a list of size 4。

B what was yes， but just be more pedantic。 Like， how do I sort any list using merge sort。

Sort the left half。 So let's do just that。 So of the list of size 4， how do I sort this， Well。

 I'm gonna sort the left half。 How do I sort a list of size 2。Sort the left half。 Allright， well。

 I'm just gonna write the six here。 How do I sort a list of size 1。I just don't。 I'm done。

 That was the so-cal base case where I just said return。 like I'm done sorting the list。 Okay。

 so here I， here's the story recap， sort the left half， sort the left half， sort the left half。

 and I just finished sorting this。 So what comes next。😡，Sort the right half。😡，Which is this。

 And now I've sorted the left half of the left half of the left half， which is a big mouthful。

 But what do I do as a third and final step when sorting this list of size 2。Merge them。

 This part we know how to do。 I point left and right， and I now take the smallest element first。

 which is the three。 Then I take the 6。 And now this list of size 2 is sorted。

 So if you remind in your mind's eye， what step are we on， Well。

 we have now sorted the left half of the left half。 So what comes after。The left half is sorted。

We sort the right half。 So we're sort of rewinding in time， but that's okay。

 I'm keeping track of the steps in my mind。 I want to now sort this list of size 2。

 How do you sort a list of size 2， Well， you divide it into a list of size 1， How do you sort this。

 You're done， You then take the other right half and you sort it done Now you merge the two sorted half。

 So I point at the four and the one。 Obviously， the one comes first。 then the four。

 Now I have sorted the right half of the the right half of the left half of the original numbers。

 What's the next step now that I have the left and right halves of this list of4 sorted。Merge those。

 So same idea。 but fewer elements。 I'm pointing at the three and the one。 Obviously。

 the one comes now I'm pointing at the three and the four。 Obviously， the three comes next。

 pointing at the six and the four， the four comes next。 and now the six comes last。

 Now I have sorted the left half， and it's intentional that 1，3，4。

6 is the original arrangement of the lighted numbers I had on the shelves a moment ago。 All right。

 a long story it seems， But what comes after you sorting the left half of the original list。

 you sort the right half， So let's put some put those numbers over here。

 How do I sort a list of size 4， Well， you sort the left half。 How do you sort this thing of size 2。

 you sort the left half， you sort the right half And now you merge those together。

 How do I now sort the right half of the right half。 Well， I sort the left half。

 I sort the right half。 and then I merge those together。

 Now I have sorted the left half and the right half。Of the right half of the original elements。

 What's next， the merging 0，2，5 and 7。 Now we're exactly we were were originally with the lighted numbers。

 I've got 1，3，4，6。 The left half sorted 0，2，5，7。 The right half sorted。

 What's the third and final step。 merge。 those two halves。 Of course，0，1，2，3，4，5，6。😊，And 7。

 And hopefully， even though there's a lot of words that come out of my mouth is acting this out。

 there wasn't a lot of back and forth。 Like I definitely wasn't like walking back and forth physically。

 And I also wasn't comparing the same numbers again and again。

 I was doing sort of different work at different conceptual levels。

 But that was like only three levels total， It wasn't N levels on the board visually。

 So where does this get us with merge sort。 Well， with merge sort。

 It would seem that we have an algorithm that I claim is doing a lot less work。

 But how much less work is that。 Well， let's consider sort of the analysis of the original list and how we might describe it its running time in terms of this big O notation。

 Hopefully it's not gonna be as bad as n squared ultimately。

 So here are some like redcrumbs that if I hadn't updating the screen and deleting numbers once we moved them around。

 here sort of like traces of every bit of work that we did， We started up here。 we did the left half。

 the left half of the left half， the right half of the right half and then everything else in between。

 and。See that essentially， I took a list of size 8。

 and I did three different passes through it at this conceptual level。

 at this conceptual level and at this one。 And each time I did that。

 I had to merge elements together。 And if you kind of think about it here。

 I pointed at four elements here and four elements here。 And in total， I pointed at 8 elements。

 So there was n steps here for merging。 And if you trust me。

 I'll claim that on this level conceptually， there were also8 steps。

 I wasn't merging lists of size 4。 But I was merging two lists of size 2 over here and two more list of size 2 over there。

 So if you had those up， those are n total steps or or merges， if you will。 And then down here。

 this was kind of silly。 I was， but I was merging ultimately8 single lists all into the higher level of conceptually。

 So from a list of size 8， we sort of had three levels of work。😊，And on each level， we did n steps。

 the merg。 So whereas is three。 Well， it turns out if you have8 elements up here。

 the relationship between 8 and 3 is actually something formulaic。

 and we can describe it as log based 2 of n。 Y， because if n is 8。

 if you don't mind doing some logarithms here。 log base2 of8 is the same thing as log base 2 of2 to the third power。

 the log 2 and the two cancel itself out， which gives you exactly the number 3 that I sort of visualized with those traces on the screen。

 which is to say irrespective of the specific value of n， the big O running time of merge sort。

 is apparently not n squared， but it's log n。Times N or more conventionally n times log n。

 because you're doing n things log n times technically based2。

 but we don't care about that generally for big O notation。 And indeed， in big O notation。

 we would say that merge sort is on the order of n log N。 That's its big O running time。

 sort of the upper bound， what about the lower order bound。 Well。

 there's no clever optimization in our current implementation， as there was for bubble sort。

 And so it turns out the lower bound would be in omega of n log n and in theta， therefore。

 n log n as well， because big O and omega are， in fact， in this case， one and the same。

 And if we actually go back to our visualization from earlier。

 Give me just a moment to pull that up here in our earlier implementation or an earlier demonstration of these algorithms。

 we had。

![](img/8aeeb4ffa4b647567df757f10b8cf92c_38.png)

![](img/8aeeb4ffa4b647567df757f10b8cf92c_39.png)

A side by side comparison of all the comparisons。 But here。

 if I go ahead and randomize it and click merge sort。

 you'll see a very different and clearly faster algorithm。

 even though the computer speed has not changed。😡，But it's touching these elements so many fewer times。

 It's wasting a lot less time because of this cleverness。

 where it's instead dividing and conquering the problem into smaller and smaller and smaller pieces。

 And to give this a final flourish Since that was yes， faster。

 but not necessarily obviously faster than other things that we've done。

 how might we actually compare these things side by side by side。 on our final moments together。

 let's go ahead and dramatically。 and for no real reason， just dim the lights。

 so that I'll hit play on a visualization that at the top is going to show you selection sort with a bunch of random data on the bottom is going show you show you bubble sort with a bunch of random data。

 And in the middle is going to show you merge sort。

 And the takeaway ultimately for today is the appreciable feel of difference between big O of n squared and now。

 big O of n log N。😊，嗯。🎼，🎼。

![](img/8aeeb4ffa4b647567df757f10b8cf92c_41.png)

All right， the music just makes sorting more fun， but that's it for today， we will see you next time。

