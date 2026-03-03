# 哈佛大学《CS50X 计算机科学导论 算法｜Harvard CS50 Fall 2024 - Lec3 - algorithms》中英（deepseek - P1 - GPT中英字幕课程资源 - BV1bKsaexEMD

是新的配。Al right， this is C S 50， and this is already week 3 or fourth。

 And this week's focus is going be pretty much entirely on algorithms。

 which is exactly where we started the course recall back in week 0。

 But one of those algorithms recall involved a certain phone book first physically and then virtually and indeed in a phone book。

 of course， you have all of these names and all of these numbers。

 presumably alphabetized by first name or last name。 And we looked for something someone back then。

 namely John Har， and some of you might have called or texted even perhaps that number at the time。

 But recalled it among the goals of having that whole conversation about finding John Harvard or anyone in a phone book digital or otherwise was to talk about just how good the algorithm was。

 It sort of went without saying in week0， that the algorithm has to be correct。

 Otherwise what's the point of writing it or implementing it in the first place。

 But we also talked about design。 And can you make a better algorithm by thinking a little harder about it。

 maybe harnessing some of your intuition and actually speeding things up as we discussed。

 So the first algorithm， recall in week 0， one page。Time was perfectly correct， but super slow。

 And we described its slope with this straight line here。 And if that phone book had。

 say n pages where n just means number， it was a one to one relationship。

 because if you add more pages， you need more steps。 The second algorithm recall。

 where I went two pages at a time was twice as fast， So surely better， potentially incorrect， though。

 if John Harvard got sandwich between two pages， but we proposed to solve that by just doubling back one page。

 if need be， if you pass the J section， maybe hit the K section and therefore need to go back at least one page。

 And that algorithm was fundamentally better， its line was fundamentally lower than the first algorithms1。

 because of course it takes half as much time to implement that second algorithm plus like one extra step just to double back。

 But the third and final algorithm in our very first week together。

 recall was that socalled divide and conquer And today we'll give it a name again binary search by implying two。

 because we were dividing in half in half in half again and again， and we got this fundamentally。

Different shape whereby even if we double the size of the phone book next year。

 I propose maybe Cambridge and Austin here in Massachusetts merging together。

 So you go from like 1000 pages to 2000 pages。 One of you observe that that's not a big deal because you need just one more tear of the phone book to actually take a big bite out of that problem and go from 2000 to 1000 then to 500 then to 250 and so forth pages in the phone book。

 So this week is really going to be about implementing algorithms。

 not only correctly but also efficiently and really focusing on design。

 There won't be much new syntax in C， we'll give you a couple of building blocks that solve concrete problems。

 but this week is really about taking a breather after the past two weeks， a fairly new。

 fairly intensive C code and just solve some new more sophisticated problems together。

 So let's consider how we can go about solving problems involving data。 like case in point。

 phone books are a good example。 And so far as they represent a decent sized data set that ideally is in fact。

 sorted alphabetically or otherwise。 And in the real world。We are searching for。

 We are sorting information all of the time。 like odds are within the past hour or so。

 All of us have used Google or some search engine in some form。

 How does Google get us search results like that， Well。

 they've probably use some kind of very clever layout in their server's memory to get us answers really quickly So we'll begin to think about especially when data gets big how we can use this kind of hardware。

 but on top of which we write software to solve actual problem。

 So here again is like a little black chip on top of what's otherwise called a circuit board or a logic board inside of our Mac piecesc and phones。

 if though we abstract this away and just assume that if this big chip here represents like 1 gig of memory 1 billion by or 8 billion B。

 surely we can just arbitrarily but consistently number them like this is byte 0。

 This is byte 1 byte2 do dot dot byte 1 billion all the way down here in the bottom。

 So we can address our memory in this way。 So let's forget about the actual hardware there。

 and now talk about what。Really is going on inside of the computers memory。

 borrowing ideas from last week。 So if this is just a canvas of memory。

 each of whose squares represents one B of memory， how can we go about laying out information。

 be it names or numbers or web pages or anything else。

 Well recall that we divvied this memory up into chunks last time。

 And we call this an array And what was key about an array was that it was just a bunch of values back to back to back in memory so calledled contiguous。

 And it wasn't a huge deal last week that these things were contiguous in memory back to back to back。

 But this week， it's actually gonna really matter because it's because of that layout。

 And because of last week's， week 2， that we can actually solve problems efficiently in this week3。

 So， for instance， here are a whole bunch of numbers and these numbers are stored in an array and this arrays of size 7。

 It would seem because there's 1，2，3，4，5，6，7 numbers in this here array。 And of course。

 you and I can see all of these numbers at a glance with sort of。😊，I view。

 But the catch is that computers technically can only look at one location in memory at a time。 Now。

 that's a bit of a white lie because computers are getting so darn sophisticated nowadays that different types。

 fancier computers can maybe do multiple things at a time。 But for our model today。

 we'll assume that a computer can indeed only look at one location at a time。 So， for instance。

 if you're searching for the number 50 among all of these values here。

 all of us in a split second can kind of spot it over there Third from the right。

 But a computer is going have to look for it a little more methodically， more algorithmically。

 if you will， step by step in order to solve that problem。

 So a good mental model to have when it comes to what's going on inside of your computer。

 is that these numbers are， yes in an array， but they might as well be locked up behind closed doors whereby in order to see each of those values and find one of them。

 the computer is metaphorically going have to open up each of those doors one at a time， looking。

 looking。😊，For the number that we actually care about。 Now。

 it turns out we can treat this array of closed doors， gym lockers， if you will， much like an array。

 So this might be location 0 location 1 location 2 dot dot dot location 6 to be clear。

 there' are  seven doors total。 But as always， if you start counting from 0， it's n-1。

 which refers to the right most or the last doors。 So 6 instead of 7。

 But there's indeed a total of 7 doors here， just for pary with the lockers。

 we were able to buy online。 You might as well think of these as red door behind which are all of those numbers。

 So if the goal at hand now is to sort of mimic what's going on inside of a computer。

 I bet we could figure out how to find information among these doors。

 And this is just a problem be solved in the world of computing， this is the problem of searching。

 not surprisingly。 And what does that really mean， Well， if we go back again to week 0。

 where this is computer science。 like this is problem solving。 What's the input to this problem。

 Well， we have an array of 7。

![](img/80f8485c3fcfba2e4a80e6525679ec92_1.png)

Doors that might as well be locked up behind these doors。

 And we want to get as output a boolean value， like true or false。 Yes， the number 50 is here or no。

 it is not。 So true or false respectively， we'll get the job done And inside of this， of course。

 is going to be as always some kind of algorithm， step bystep instructions for actually solving this problem。

 So how then would a computer concretely go about searching for numbers behind this door。

 Well maybe just for fun， we went ahead here and printed out some monopoly money。

 some large versions thereof。 and suppose we want to find very specifically the number。

 the dollar amount 50 behind one of these doors。 could we get maybe one maybe two volunteers to come on I saw your hand go up first second on the end there and let me look over here over here behind the camera number two。

 come on down。 Okay， come on over or maybe a round of applause to break the ice for these two。

Come on up。And we've got two algorithms ahead of you。

 but come on over here if you want to introduce yourself to the world。

Maybe I quick something about each of you。Hi， I'm Jonathan。

 I'm a sophomore in Caboot House studying economics。Wonderful， nice to meet you。 And I'm Claire。

 I'm a junior and Elliot studying economics and TDM。 All right， it's nice， wonderful。

 to have you both here。 So behind you are 7 doors。 And which of you would like to go first。 okay。

 so first， if you want to come come over here。 behind these seven doors are now dollar amounts。

 namely， all of the available monopoly dollar amounts。 And if you want。

 we want you to find the number 50。 You can go about this in a bunch of ways。

 Like you could go about just opening random doors。 but that's not necessarily very repeatable。

 That's not very algorithmic step by step。 So let me propose that you do something super simple。

 start at the left door and work your way to the right。 And just so everyone knows what's going on。

 go ahead and show the world what number you've pulled out of each of these lockers。😊。

And the first locker is。20。That is correct， not 50。500 is sue incorrect。10， not correct。Not correct。

100， not correct。One， not correct， hopefully last door and a round of applause if we could for finding the number。

Okay， so if you don't mind before we transition to a better algorithm because frankly。

 that was pretty bad， but it wasn't incorrect in the sense that he was doing anything wrong。

 He sort of just had some bad luck。 And frankly， if I hadn't sort of led him to that path from left to right。

 I could have proposed more cleverly that maybe start from the right and then boom。

 the problem would have been solved。 But in general。

 if data isn't necessarily cleanly laid out by us humans in this very manipulative approach。

 like maybe it's going to be at the beginning of the array。

 maybe it's going be at the end of the array， you really don't know。

 So you might as well have one methodical approach step by step and just do it again and again。

 So I think even though that felt increasingly awkward because you didn't find the 50 till the end。

 that was kind of as good as you could have done in general。

 and let me propose before we try a second algorithm， if we take a look at some pseudocode here。

 I dare say what you implemented with my sort of encouragement with something called linear search。

 literally walking in a line from left to right。 And if we kind of take the fun out of searching for money behind doors。

 we can make this more algorithmic with pseudocode Englishlike code。



![](img/80f8485c3fcfba2e4a80e6525679ec92_3.png)

In in very terse language he did for each door from left to right。 if 50 is behind the door， ideally。

 then you would have returned true。 And that's when everyone applauded， of course， else， if not。

 you might return false at the very end of this code。 So we got lucky 50 was there。

 But if you hadn't， you might have decreed， oh， no， there's no 50。 So I returned false。

 But notice the indentation here just to highlight a key detail。 I'm only returning false。

 once I'm done with that loop。 For instance， if I had poorly implemented this pseudocode like this。

 indenting that return false and only doing it conditionally， if 50 is not behind the door。

 I know we're putting them on the spot here。 But you want to conjecture why this would be bad if you spot the mistake。

If you put false right after else， that means once we search the first door and we don't find 50。

 it'll just return false and the program will finish exactlyactly so this code would indeed be a bad implementation incorrect because only if the 50 is behind the first door would it ever work correctly。

 we would otherwise bail out and return false prematurely so this version here is indeed correct。

 but can we do better Well the numbers that were behind the doors for you。

 were they in any particular order。No， so we kind of set you up for for failure in that sense。

 So if you don't mind， let's go ahead and pass the mic over。 And secretly behind me a moment ago。

 Julia was kindly sorting all of those same dollar amounts behind the doors。

 And the question at hand now for you is going be find the number 50。

 But let's do this a bit like the phone book in week 0。 where let's start in the middle。

 And if you recall from week 0， then let's go left or right accordingly。

 So what's behind the middle door。And we have it's 2020。 So not correct。 but what do we now know。

50 is in which direction to the right All right， So to the right。 So go to the middle of the right。

 So that leaves you with these three lockers。In that middle door now， it's 100，100。 so too big。

 So what do you now know， It's going to be to the left。 It has to be logically if it's there at all。

 in between those two。And now we get your round of applause much faster than before。All right。

So this， then if I can step over here before we give you a parting gift。

 this is where we left things off a moment ago and in binary in linear search line from left to right。

 we checked each door， but just to make things a little geeier now in a bit more quantitative in nature。

 that really is the same thing is slapping numbers on this problem whereby the first door。

 we're gonna call zero the last door we're gonna call n minus-1。

 if we start to treat these lockers not as physical objects， but as a rays instead。

 So in that same spirit， let me propose that when we found the number 50 this time。

 we took a fundamentally different approach just like week0 when we did divide and conquer aka binary search binary implying we split the problem in two and two and2 by going left or right each time。

 and the pseudocode that you might have arguably just implemented looks a little something like this。

 if 50 is behind the middle door Well we got lucky and we can simply return true right away。

 But if it's not if 50 is less than the value at the middle door， we could have gone left。

 even though you didn't need to else， if 50 is greater than that of the middle door。

 we could search right。And you did do that， but there's a fourth scenario here。

 and we talked a bit about this in week  zero， do spot what other scenario I might want to consider。

😡，If it's either in the middle or to the left or to the right， what else might happen？

It's not what else might happen， it was that fourth scenario， yeah。So it might not be there at all。

 right I could have really set you up for failure by not putting the 50 there。 And in code， though。

 we need to handle that because I conjectured in week 0 when you don't handle all possible scenarios。

 that's when the computer crashes or freezes or just something goes awry。

 So if there are no doors left， you sort of run out of possibilities logically。

 we had better make sure we return false。 So before we give you both maybe one final round of applause。

 wonderfully Monoly。😡，Makes its own Harvard edition for Cambridge so we have a nice parting gift for both of you today。

 thank you both for coming round up。All right。So just to now make that algorithm a bit more quantitative。

 instead of just saying middle middle middle， let's use a bit of array syntax here now too。

 so this is the same exact pseudocode for that algorithm binary search and so the first condition is the same if no doors left just return false。

 but if 50 is behind doors bracket middle and again I'm sort of stealing some syntax from last week where we introduced square brackets for arrays。

 but I'm still using pseudocode so this isn't C per se。

 but by doors I mean the array known as doors bracket middle I mean whatever the middle number the middle index is go there。

😡，If you found it behind the doors， bracket middle return true else， as we enacted a moment ago。

 if 50 is less than the middle door， then go ahead and search what Well instead of saying search to the left and search to the right。

 let's make this again more precise today， search the array of doors from location0 all the way through location middle minus-1 So what do I mean by that here was the middle door and even though this is not what we did a moment ago。

 if we were to go left here's bracket0， the first door， here is middle-1， because if this is middle。

-1 is immediately to the left and this is why this algorithm would indeed have a searching the left half equivalently equivalently if 50 is greater than doors bracket middle。

 then search doors middle plus one through doors n-1。

 Well the end of an array if0 indexed that is you start counting at 0。

 this is always n minus-1 if this is middle middle plus1 is here and this is exactly what you just。

searching the right half of those doors。 So we have this translation then from sort of the intuitive pseudocode from week 0 into now the more technical expression of arrays and array syntax here this week。

 And that's something now we'll begin to build on over the course of writing and implementing some of these problems here today。

😡，So if we now have algorithms。😡，That both solve the same problem， just like in week 0。

 which of those algorithms was better。 The first one。

 which we called linear search or the second one， which we called binary search。They're both correct。

 I would claim。So which is better， which is better design？😡，Two， and why do you say that？😡，Okay。

 so two is more efficient insofar as the second algorithm if my thinking back only took three steps。

 She only had to open up three of the doors， whereas the first algorithm linear search actually took as many as seven steps。

 And in fact， we'll see some math underlying this， but it would be nice now if we could really compare the design of the efficiency of algorithms a little more rigorously than just saying one is better than the other。

 Let's see if we can slap not some numbers on it。 but maybe just some very simple arithmetic or algebraic formulas that allows us to compare two algorithms。

 So that in the real world and in problem sets and in projects in the future。

 you can sort of make a more quantitative claim as to which approach is indeed better。

 So when we talk about running time， we literally mean that like how much time does it take for a program to run。

 but we don't necessarily count in terms of seconds or ticks of a clock more generally instead we'll try to count the number of operations that an algorithm takes。

 So， for instance， this was a way of analyzing the running。

Time of three algorithms way back in week 0。 And I did introduce a bit of jargon。

 whereby I was using expressions like n to represent n pages or n divided by two to represent half as many pages。

 and even though I wave my hand at week 0。 log based  two of n is mathematically how you would represent the idea of dividing something in half in half in half。

 if you start with N pages。 So those are three formulas。

 But it turns out that at least two of these algorithms from week 0。

 they're pretty darn similar to one another。 Indeed， literally two of these are straight lines。

 even though the slope is slightly different， the other one is fundamentally curved and therefore different and indeed we saw better。

 but let's get out of the business of worrying about like maybe like constant values。

 like dividing by two， we really want to care about when algorithms are sort of fundamentally better than one or the other。

 So case in point， here are those same two algorithms from week 0。

 this was turning one page at a time。 This was turning two pages at a time， honestly。

I wanted to speed things up by a factor of two， why don't I just use a faster Mac。

 a faster PC right nowadays， I could literally wait like one year and next year's computer will be practically twice as fast。

 it would seem then the first。 And so if we start to try to compare the efficiency of algorithms。

 it would be nice if they're sort of resilient those comparisons to what computer you use to run the code。

 we want to take a step back and sort of approach things a little more mathematically but fairly lightweight nonetheless And so the way a computer scientist typically describes the running time of an algorithm is by using a capital O as in a letter and using it to imply on the order of this many steps and I actually keep saying as a turn of phrase wave my hand at a problem。

 this is sort of the mathematical equivalent of like I don't really care about the very precise mathematical formula it is roughly on the order of this fast or this slow。

 So what this means is that if you want to describe the running time of this algorithm。

 this one or this one syntactically you literally write on a piece of paper。

an essay or the like big O， and then in parentheses。

 a little mathematical formula that describes how the running time relates to the size of the problem。

 just like this Xy grid。 But it turns out and I'll claim we rarely care about denominators if they're just constants like two or three or4。

 all we care about really is the highest order term So whatever the biggest mathematical component is in the expression。

 the one that really matters is n gets big that's the one we care about because frankly。

 if n is like 2 billion pages，2 billion in size， well。

1 billion still feels pretty darn slow if it's going to take that many steps。

 they might as well be just as slow as each other。 But this one here， similarly。

 if you remember your logarithms， even the base doesn't matter because you can actually multiply one logarithm by a constant it sort of change the base。

 And so here too， we're going to get rid of the specific constant like two And here then is how we would describe the running time。

 And in fact， if you zoom out in your mind's eye and assume that the y axis is bigger and the x axis is bigger。

If you keep zooming out， zooming out， zooming out， these two lines are actually going pretty much look the same once you've zoomed out far enough。

 And that's what I mean by they're essentially themselves algorithmically the same as N gets big。

 big， big， big these might as well be the same algorithms。 But this one is clearly not。

 And we claimed in week 0 that this one was better。 I claim again today that this one is better。

 and now will begin to slap some formulas on the evaluation of these algorithms so that we have a better sense of what algorithm is better than someone else's and indeed in the real world when you talk about what makes someone a good programmer。

 what makes someone a good engineer is sort of having an intuitive sense with practice and with time of how you should write your code so that it maybe has a better running time than some other algorithm because when you start working at Google or Microsoft or working in medical data sets or financial data sets and the data is really big and is really big you probably want to be as efficient as possible。

 So this cure capital O is generally called big O notation not particularly technical。

But that's indeed what it's called。 And here， for instance。

 is a little chart of very common runtimes。 You can have any mathematical expression。

 but almost always in the context of computing， at least introductory type algorithms。

 This is kind of the list of possibilities， even though there's infinitely many more。

 So among the algorithm So we've considered thus far， what is the running time of linear search。

 what's on the order of n， because if there's end doors like those behind me in the worst case consider how many steps might it take me or take you like it will take n steps specifically 7。

 but N in the general case。 And so Big O is very commonly used when you do want to think about the worst case。

 because honestly， who really cares if you got lucky and the first door you opened had the number you're looking for。

 That doesn't really generalize。 And you know that's not a good argument within Google， hey。

 once in a while， someone will get lucky and will really return them a search result quickly。

 you want the general case to be fast。 And so linear search really in the worst case。

 Like which customer is going be。Leas happy with our Google code。

 Linear search sort of describes that in upper bound。 So to speak on how many steps it might take。

 What about the best case running times or lower bounds on how fast an algorithm might be。 sorry。

 I should have not spoiled this。 What's the running time of binary search if the running time of linear search is big O of n Well。

 the running time of binary search by contrast is going to be log based two of or more generally log event。

 she could have gotten lucky our volunteer by just opening the middle door and voil。

 maybe 50 was there。 It wasn't。 But in the worst case she only had to look at big O of log n doors in total And that gave us roughly three doors in this case。

 All right， what if we want to talk about best case running times just because it would be nice that in certain situations。

 how fast can our code actually run how good is our algorithm， Well， in computing。

 computer scientists use a capital omega symbol to represent a lower bound。 So big O is upper bound。

Big omega is lower bound。 And you can use the same kind of mathematical formula。

 So here's that little cheat sheet again。 But with an omega prefix。

 which again means lower bound and same question in linear search where you look at the doors left to right。

 In the best case， how few steps might it take。To find a number。

I'm seeing just one because we could get lucky。 And because we go from left to right could be that we find the number right away。

 So that's in big omega of one in this case， one step。 Otherwise， how about binary search。

 What's the lower bound on how quickly we might find。A value。Same thing。

 right because we could just get lucky because by starting in the middle。

 it might happen to be right there。 So the lower bound on binary search2 also happens to be in big o of1。

 because we just simply get lucky。 All right， what if those two are one in the same one last piece of Greek symbology here。

 capital theta here is used when big O and omega are exactly the same thing which won't always apply。

 but sometimes an algorithm performs at this rate as well as at this rate and they're one and the same。

 depending on the algorithm itself。 So here's a little cheat sheet here。 And how about linear search。

 So linear search in the best case takes only one step in the worst case takes as many as n steps。

 So those are not really one and the same。 So theta is really inapplicable here。 And binary search2。

 this is sort of inapplicable， because in the best case， it might take me one step。

 hence the big omega of one， but in the worst case。

 and it's not even that bad might take me big O of log n。 So theta doesn't apply here。

 but we'll keep an eye out。

![](img/80f8485c3fcfba2e4a80e6525679ec92_5.png)

TodayAnd see if there aren't certain algorithms that we'll look at that might actually have those values being one and the same。

 And all of this symbology。 And that's it really for definitions for now。

 is what's generally called asymptotic notation， Its notation that you use when talking about the running time of algorithms over time like as the input gets larger and larger and larger。

 How do these algorithms perform。 How can you measure their efficiency。Okay， any questions on big O。

 mega？😡，Or anything prior， we'll come back to theta before long。Any questions yet on front？Sorry。

 say again。Is binary search efficient with respect to？😡，Oh， is Buck really good question。

 Is binary search efficient when searching random data， as was the case with our first set of doors。

 And indeed， those numbers were all over the place。

 They were not sorted from smallest to largest or largest to smaller。

 So what is the answer to that Is binary search efficient when the data is random。

It doesn't work at all。 And so that was sort of the hidden cost of the two algorithms that we acted out。

 And literally， I had Julialia come up and help me。

 She did more work to enable us to use binary search。

 because only for the second exercise with the lockers with the data actually sorted。

 So binary search just does not work if the data is random because you would open a door。

 see a number like the number 20。 and now you would make a decision whether to go left or right based on this randomly being here。

 So who knows if it's less than or greater then based on the number you've seen So you simply cannot use binary search when the data is unsorted。

 Aka random。 In that case， then， how do you sort the data。

 that's going to be one of the problems we solve ultimately today， get the data sorted。

 help Googles of the world sort their data first so that we can find web pages and other things more quickly。

 Yeah， and back。 Oh， any questions。No all right， so let's actually translate some of this to a little bit of code here。

 How could we go about implementing something like linear search。 Well， let me do this。

 Let me go over to VS code here。 Let me propose to create a new program called search do C。

 So I'm going to do code search do C。 And in here， I'm gonna use the CS 50 library at the top So I can get input。

 I'm gonna use standard I O do H so I can print stuff out on the screen。

 I'm going use in main void because for today， I don't really care about command line arguments for this particular program。

 and let me start with an array of values。 supposeupp I want to implement in code the idea of these lockers containing those random values initially and implement in C the very first algorithm we enacted with our volunteers。

 which was searching from left to right。 Well， it turns out in C。

 I can create an array recall by saying I want integers。

 I want the array to be called numbers and then inside of square brackets。

 I can specify how many elements I want Maybe I want three like last week。 But in this case。

 I think I want。😊，7 this week to represent each of these lockers。

 but turns out you can initialize an array without even using get int or the like。

 you can just specify in empty square brackets that that whole array should equal the following inside of curly braces。

 So this is one new use of curly braces。 but it's a handy trick when you want to create an array that has specific values like 250010。

5，1001 and 50， which just happens to be the exact order in which the dollar amounts previously were behind those lockers。

 So what does this line 6 do at the moment， it creates for me an array of size 7 and initializes it to that sequence of values from left to right。

 it is not strictly necessary to bother putting7 there and it's probably best not to because the computer specifically the compiler will figure out how big the array should be based on what you typed inside of those curly braces and you're just inviting a mistake if you put a number over here。

supposed to match the total over here at some point you're probably going to error All right so if that gives me an array of size7。

 let me go ahead and ask the user what number do you want to search for much like I verbalized before so int n equals get int and I'll prompt the human for a number as with this kind of prompt how do I now implement linear search Well based on the constructs we explored in week zero and week1 we had conditionals and loops and variables and Boolean expressions and the like what is probably like the feature of the programming language that we're going to need to search from left to right。

😡，To implement linear search。A four loop probably or a while loop。

 but a loop in general why because I could use like seven conditionals and I could say if the numbers bracket0 equals equals this value。

 then return true else if numbers bracket1 equals equals this number then return true。

 but that's not very general purpose if we're gonna to have all of these conditionals let's just have one that asks the same question by just changing some variable and a four loop is often the paradigm So for int I equals0 I is less than7 I plus plus and this code alone sort of sets me up to implement what our first volunteer did from left to right with the lockers what's the question I want to ask well does the array of numbers at the current location I equal equal the number n that we're actually looking for so does the number behind the first door second door。

 third door actually equal 50 for instance or whatevers typed in and if so。😡。

Let's go ahead and print out something clear like Fo backslash n。😡，Else。

I don't think I want to do this。 printf， not found。😡，So let me， for a moment。

 sort of poorly implement this。 What have I done wrong with this code。Yeah， in the back。Yeah。

 I don't want if I want the if inside the for loop。

 but not the else inside the for loop Y because that would be the equivalent of starting at I equals0 opening the door。

 and then concluding I have found or not found the number without even allowing us a chance to keep going because we're gonna spit out sort of unilaterally not found。

 even though we just haven't found it yet。 So I don't think I want to do that but I think what I can do for instance。

 is as per the slide a bit ago if I at the end of my loop get all this way。

 then I think I can print not found。 but I think logically even this might be imperfect。

 So let me go ahead here and do make search enter seems to have compiled so new syntax errors dot s search enter what number do I want to search for。

 I'm gonna go ahead and type 50 and hit enter。😡，And still， I have a logical bug， it's saying found。

But also， not found。Why， even though I move that line of code outside the loop， which is correct。

 But there's still something wrong here， yeah。Yeah。

 the iteration still ends up leading us to this final line why because we're gonna go all the way from 0 to the end of the array again and again and again。

 hopefully printing out found when we find it， but there's nothing stopping us from then executing line 16 before the program actually ends。

 But recall last week， we had a solution to this。 even main can return a value。

 And even though in week1， it was sort of secretly returning the number 0 unbeknownst to us。

 it turns out we now had the ability as of week two to explicitly return a value anywhere in main that we want。

 And the convention a little paradoxically is to return0 upon success because that means all is well。

 and then return anything other than0， like a positive integer。 if anything has gone wrong。

 And we use positive integers because it could be this thing that goes wrong， this thing。

 this other thing lots more can go wrong than can go right when writing code。

 So I think what I could do here is after printing found， I could return 0 to signal success。

 even though the humans not gonna to see anything different and down。

Here I could actually return one to signify failure and recall with the little command trick。

 I could do dollar sign question mark and actually see what that value is。 But for our purposes。

 what we really care about is that Maine returns when we are done solving this problem。

 either inside of the loop or ultimately outside。 So let me try this again。 make search。

Dot slash search。 Let's search for again the number 50 enter。 and indeed it is found and only found。

 Let's do this again。 dot slash search。 Let's search for the number two， which is not in that array。

 and I should see and only see。😡，Not found in this case。

 So this then would be the code for linear search。😡，Any questions on what we just did here， yeah。

A really good question。 What if we don't initialize the array Well， honestly in programming。

 a very good answer to that question is just try it out and see what happens。

 So let me create an array of size 7 with no values inside of it。

 let me reopen my terminal window do make search and the compiler doesn't seem to mind that if I go ahead and now do dot slash search enter I'll be prompted for a number I'm going presume to search for 50 even though I don't know what's in there enter。

😡，And at least it was not found here。 Let me go ahead and try again。

 Let me search for the number two， not actually found。 search for the number one， not actually found。

 And I could poke around all day long。 But it turns out I'm probably just getting lucky here。

 Why Well， this loop， no matter what is going check 7 locations。

 But I have not put anything in any of those seven locations。 But recall from last week。

 we sometimes saw those garbage values， sort of remnants of memory that of course exist。

 but maybe had been used for some other value previously。 at the moment。

 I think I'm just getting lucky that among the first7 locations in the computer's memory。

 I just didn't end up with a garbage value 50 or two or one。 But if we played this game for a while。

 I bet I could come up with a number that actually works。 And let's see at the risk of a demo。

 not going according to plan。 let me do dotslash search， Let's search for0。 still not there。

 Let's search for3， we're gonna have to do this all day long to actually find the values。

 there's 4 billion possibilities。 But at some point， we would get。😊，Lucky， and it would say found。

 but only by chance。 So in short， do not do that since it is wrong。All right。

 other questions on the code。That we've just written。Alright。

 so let's transition to maybe a better version of this。 What if the numbers are actually sorted。

 And frankly， what if they're not actually numbers at all， let me go back into this code。

 let me throw away the contents of main， and let's do something maybe now with strings instead just so it's more like searching an actual phone book。

 So I'm gonna create an array of strings called strings for lack of a better name and much like a certain game with which you might now be familiar we might have a string for battleship and boot and canon and iron and thimble and top hat。

 though this does vary by country based on which version of monopoly you actually have。

 then let's go ahead and prompt the user for a string S using get string and ask them for a string to search for and then let's do a four loop again for int I equals 0 I less than1。

2，34，5，6 values。 I'm hard codingd6。 and I don't like that。

 but we come back to that idea in general of figuring out what the length of。ThatAray might be。

 but for now， I'm just going to hardcode it， but that's not indeed good practice。

 I plus plus inside of the four loop。 Now， let me go ahead and do this。 If the I whoops。

 if the Ih string or the strings that location I equals equals S then let me go ahead and print out as before。

 found， let me not make the same mistake as before。 So let me immediately return0 to signal success。

 But if we don't find it anywhere in that array。 let's go ahead and print out not found。

 and then let's go ahead and return one just as before。

 So the only thing that's different now is I'm using strings instead of integers。

 But I'm otherwise looking for the Ih string that might very well have the same value as S。

 what I have typed in。 Allright， let me go ahead and open my terminal again， run， make search again。

 so far so good dot slash search， let's search for maybe the thimble enter。 it's not found。

 All right， maybe it's too far away。 Let's search for again， battle ship， enter。Not found。

 How about the top hat En， Not found。 And I could do this three more times。

 but I'll claim that it's never going to find any of these strings。

 Does anyone have a suspicion as to why。Or how we might solve。Why is this not working yeah？Yeah。

 well said。 So it turns out， and this is super subtle。

 equals equals is not how you can compare strings。 And we'll see why， in fact。

 in greater detail next week。 But for now， equals equals works fine for integers for longs for chars and a bunch of other data types as well。

 but it doesn't actually work for strings and for today's purposes。

 it's really because strings can be different lengths。

 and equals equals is only going to compare two values， but a string might be three characters。

4 characters，5 characters depending on how many characters I have typed in equals equals is not powerful enough or wise enough to actually solve that problem。

 However， this is such a common thing to do like in our phones and on Google and the like to compare strings that humans have typed in that there is。

 in fact， a solution for this。 And so， in fact， well introduce today。

 another function from the string do H header file that we introduce last time。

 recall that inside of string do H was the declaration for Stling SR LN。

 which would figure out the length of a string。Based on the null character and everything we talked about last week。

 but within the same library as per CS50's documentation。

 there's another function called stirR Compare or STC for short and if you were to pull up the documentation for that particular function。

 you will see that its prototype actually takes two strings as input called S1 and S2 we could call those any two things but what's noteworthy about this function is that it's return value。

 is sort of turnernary it can return one of three different things to us。

 the function can return an int less than0 if S2 comes before sorry if S1 comes before S2 it will return0 if S1 is the same as S2 and it will return an inch greater than0 if S1 comes after S2 so stirR compare is more powerful than just saying yes or no these strings are equal。

 it can actually be used to alphabetized strings as well because what it's essentially saying is alphabetically S1 comes before S2。

😡。

![](img/80f8485c3fcfba2e4a80e6525679ec92_7.png)

![](img/80f8485c3fcfba2e4a80e6525679ec92_8.png)

Or S1 and S2 are the same or S1 comes after S2 alphabetically and alphabetically is a bit of a white lie。

 It's technically ASibetically because what's being used is the ASI values so lowercase characters are going to be treated different from uppercase characters so we say askibetically because it's literally comparing the ASI codes but for now I'm going to avoid that problem by just using lowercase everywhere。

 but if I want to use this function， let me go back over to my code here and instead of doing equals equals。

 I have to use a function here called stir compare passing in one string like S like strings bracket I and then the second argument AKS2 is going to be the string I want to compare against but I want to check the return value of that function and again。

 what value should I check for if I want these things to be equal。😡。

So0 was the operative return value。 So what I want to do is this。

 So this looks at a glance like way more complicated than it really needs to be。

 but all it's doing is calling a function called stir compare。

 passing in two strings as input generally known as S1 and S2 comparing them and if they are exactly the same character for character left to right St compare per its documentation will return zero I don't care about less than0 or greater than0 because I'm not trying to sort anything I'm just trying to return true or false yes or no。

 we have found this string So to use that function just like stirling I need to include string do H at the top。

 let me open my terminal window let me rerun make search so far so good dot search now let me search for thimble in the exact same array crossing my fingers andvoah now we have found thimble and just for kicks I'll do it twice more battleship which failed previously but this time not top hat failed previously but not this time。

😡，I'll search for something like a car， which is not in the array。 En， and that is， in fact。

 not found。 So a subtlety， because strings， as we'll soon see all the more。

 are indeed a bit different from just comparing simple values like integers， chars and the like。

Questions on what we just did with stirir Compare。Or searching for this thing linearly in this way。

No all right。 Well， why don't we graduate to like more of an actual phone book right now。

 I'm just kind of searching for arbitrary strings。 Let's make something that's a little more involved。

 but uses these exact same ideas。 Let me go ahead and code up a file called phonebook do C at the top of the file。

 I'm going include those exact same file。 So include C S 50 do H include standard I O do H include proactively this time string do H。

 I'm going create my main function， no need for command line arguments today。 inside of main。

 I'm gonna give myself now two arrays just so we actually have both names and numbers。

 So for instance， I'm gonna do this an array of string called names And in that array。

 I'm gonna have three of us。 So inside of curly breaks， I'll have Ulia。

 who kindly volunteered earlier as well。 me and how about John Harvard as always。

 whose numbers will search whose number we search for。

 Then let me go ahead and keep track of not just the names in this phone book。

 but also the numbers So string。😊，Numbers and then equals and then the numbers I'm going put here are going to be。

 for instance， about plus161，7，4951000 Julia and I will have the same Harvard directory numbers of plus 1。

6，1，7，4，9，5，1000 and then John Harvard will have his old number plus 1，9，4，924，682，7，5。

0 which just for Easter egg， you're welcome to text or call some time。 Allright。

 so now I have two parallel arrays， if you will from left to right that are both mapping names in one array to numbers in the second array。

 And actually， if I want to keep this thing sorted。

 that's kind of on me and I don't really care about that for now。

 but if I wanted to sort this notice that I'm actually going need to move Julia's name there and move Julia's number to the end here。

 But otherwise we still have an array of size 3 for each of names and numbers。

 let's go ahead now and search for someone's name and therefore find their number So let's prompt the use。

For a string called name using get string and ask them what name do you want to search for in this phone book just like before。

 let's use linear search to keep it simple for int I equals0 I less than3 this time because there's three people involved I plus plus then inside of this for loop。

 let's do the same correct technique is before if the return value of stirR compare passing in two values What are the two values I want to pass into stirR compare here in order to check if we have found a person's name。

😡，What could the first one be。Feel free to shout it out。What am I searching for。

 the user's typed in name？But I want to compare it against。Yeah。

 I think names bracket I so like if the I name is the same thing as the name the human typed in and I know that because stir compare will return zero for me then I can go ahead and say just as before found and just for kicks now let's go ahead and actually print out what that person's number is rather than just say found quote unquote by outputting numbers bracket I so this is to say if we find in names bracket I the person's name that we're searching for。

 then go ahead and print out that same person I number and so that we don't accidentally say not found later。

 let's return zero immediately otherwise down here let's say not found with no number of course and then return one to signify error so if I hide my terminal window this is sort of a simple implementation of a phone book on like an iPhone or on an Android phone when you're searching for your context top to bottom or left to right so let me go ahead and run this in my terminal I'll do make phone book enter。

😡，So far so good dot/book， and if I search for John by his name properly capitalized， enter。

 I indeed found John Har's number to be plus 1-9494682750。😡，This then is correct。😡。

What though is arguably poorly designed about this program。

 even if you yourself are still newish to programming。What's bad about this design here。

Might you say。Any instincts？What's bad。Yeah。Good， so I don't like that。

 The fact that I'm using this socalled magic number。

 which means just hard coding a value that you're trusting is not going to change or that you'll remember to change it。

 I don't like this。 So that's a really good observation。 What else might you not like instinctively。

 even if。Again， these concepts are new。And often， yeah。Yeah。

 we're again on sort of the honor system here that we have these two arrays and the onus is on me。

 the programmer to make sure that they line up。 And case in point。

 when I manually went back a moment ago and moved Ulia to the end of the names array。

 I had to remember to move her number to the end of the numbers array。

 And that just strikes me as very fragile。 So to speak。

 It's just too easy for me or a colleague to screw up this code by forgetting that sort of lower level detail。

 We're just trusting that names and numbers do stay aligned and they have the exact same number of people in them and the exact same numbers exact same number of numbers in them as well。

 So we have an opportunity now to sort of do better than this And besides arrays。

 which we've already seen， do solve a lot of problems by letting us use one variable to store bunches of things。

 wouldn't it be nice if there was another type of variable that's not that's not string that's not charr that's not float or any of those that we've seen already。

 wouldn't it be nice if there's like a person data type in C。

 where I can actually create a person in my code。And a person in this world shall have a name and a number。

 Heck， if we were implementing students， maybe a student could have a name， a number。

 an email address， a Harvard I number or Yale I number of the like， you could imagine encapsulating。

 so to speak a bunch bunch of different types of data instead of one larger data type。

 And generally when we talk about data structures， we mean exactly that some kind of container for multiple types of data。

 So a custom data type， if you will。 So for instance。

 if I wanted to create an array of people wouldn't it be nice if there's a data type called person。

 So I could use code like this， give me an array of people and I don't know how many yet。

 but give me an array of people， each of which is of type person So instead of string instead of I'm saying person and an English。

 I'm pluralizing the name of the array as obviously people instead。 but that doesn't exist with C。

 like there are no student data types， there are no people data types。

 there are no professor data types。of these things that you might imagine in the real world don't come with C。

 All you get are strings and ins and floats in those lower level features。

 But if we know a person for art purposes， will have a name and a number。

 why don't we just give them a name and a number but somehow concapsulate this name and number in a bit of new syntax。

 And so the new syntax， we will introduce today is that of creating your own type that is a structure specifically。

 And we'll see more of these over the course of the term。 And even though this looks a bit cryptic。

 what this chunk of code here as saying is define a type that is itself a structure inside of which is both a name and a number。

 which are both strings in this case and call that whole new structure person。

 So as soon as the compiler gets to the semicolon a person data type does now exist and inside of that data type is two things a name and a number。

 Now， as an aside， I deliberately use string here for both name and number。

 I use string in my code a moment ago。 for those。Phone numbersumbers。

 Why did I use a string instead of an int or even a long for my phone numbers。

wasn't actually a mistake，Yeah， like the hyphen， the country code， maybe parentheses。

 if you format your number differently。 And so a good rule of thumb actually。

 is that even though you and I in the real world might call certain thing numbers like Social Security number in the United States or phone number or Id number if there might potentially be other punctuation or symbols in that number。

 And frankly， more generally， if it would make no intuitive sense to perform math on something you call a number。

 and I can't think of a scenario where you'd want to perform math on a phone number。

 you probably should store it instead as a string instead and use actual integers。

 actual longs for things that mathematically or computationally make sense to be treated as literal numbers instead。

 So if I now have this new feature whereby I can define a custom data type in my for my phone book。

 I think I can implement a brand new version of this program that's gonna be a bit more for both。

 but it's going to allow me to solve this problem better。 So let me go back to V S code here。😊。

You'll see in this code where we left off， I'm going to go ahead and delete all of this just for now。

 and I'm going to whip up a slightly better version I will claim outside of my main function。

 I'm going to do exactly what we just saw on the slide。

 I'm going to define a structure inside of which is a name of type string and a number of type string and I'm going call that whole thing a person turns out style 50 and particularly the program we're using underneath the hood prefers weirdly that you put person on the same line is the curly brace so just Fyi if you run styleyle 50 and you see that it moves as such inside of main I'm going now give myself an array of type person called people of size 3。

 So still I'm not going to solve all of today's problems。

 I still don't like the fact that I'm hard coding a3。

 but I just want to demonstrate for today's purposes how we can use this here feature。

 So I now have an array of three people and each of those people is by definition a person and a person we now know contains a name and a number。

So how do I initialize this array。 It's not as simple as just using like getstr once。

 I clearly need to use it twice， but I won't even do that。

 I'll just hardcode the values for demonstration's sake now。

 let us update the first person in the people array。

 So this is week2 syntax and set the name of that first person equal to quote unquote David semicolon then in that same person structure go into their number field and set that equal to plus 16。

17，4，9，51000 semicolon So what here is new。 Well， of course。

 people bracket 0 isn't really new like we did that last week。

 if the array is called people and you want the first element you use bracket 0。

 but what is new today is this dot operator once you've created a structure inside of the computer's memory if you want to go inside it and access the things that compose it like name and number you just use a dot like this and that means go inside the first person and access their name。

 set it equal to quote unquote David。😡，And do the same thing now for their number。

 So even though yes， this stuff is new here， the only new operator。

 So to speak today is really that same dot。 All right。

 let's go ahead and initialize the other two people。 just so we have an array completely defined。

 People bracket1 dot name will be John as before。 People bracket 1 dot number will be John's number。

 which is a little different。 plus 1，9，4，9，4，6，8，2，7，5，0。 And then lastly， people bracket 2。

Dot name equals quote unquotes Ulia and then people bracket2 dot number equals the same as mine plus 1。

61，7，4，95，1000。 So now even though this is more of a mouthful and let your mind wander to the reality that like we could just use a loop to do this a little more cleanly and use get string and make it interactive。

 but I really just want to demonstrate the type def and thestruct and this new dot operator。

 let's now search for someone's number。 So let's ask the user for a string called name using get string as before prompting for that name。

 then inside of a four loop for int I equals0 I less than three again， don't love that。

 but we're focusing on one problem at a time， not this other one I plus plus inside of the four loop now same as before if the return value of stir compare passing in the current persons name and the name that the human just typed in returns a value of0。

 then inside of that let's go ahead and print out。Found percent S back slash N and plug in people bracket I。

 but I want to see their number。 so I do dot number instead。

 now I can return zero for success down here， I can print out not found to indicate failure and down here。

 I will return one。 So the only new stuff in this program really is the fact that I have now invented a new data type called person that we can now use in our code。

 and I'm accessing the individual fields or attributes of that new structure by using this new dot operator。

 which goes inside of that custom structure。 Allright， if I didn't screw up。

 let me go ahead and make this phone book So far so good dot slash phone book enter。

 And now if I type in John enter I have in fact， found John's number。

 And if I go ahead and search for someone else， for instance， like Brian。

 who's not in the phone book， he in fact， is not found。

Questions then on any of this feature by which we've now implemented really something closer to the phone book。

 albeit using linear search and not binary search。Question， yeah， in front。

You say that a little loud？What if two people have the same name， a corner case， if you will。

 This code will not work necessarily correctly because it will return to me or print for me whose number only the first one that it actually finds。

 So that would be a mistake。 And I think we'd need to address that with a bit more complicated code。

 So solvable， but not for now， a good observation， other questions。On this hair code。Now， all right。

 Well let's then tee up an actual solution to this problem。 namely， if I want to use binary search。

 like I can't yet if， unless I manually sort those arrays。

 just as Julialia came up earlier and kindly sorted the dollar amounts that were inside of these lockers。

 Now she and I kind of coordinated in advance。 So she knew exactly what to put in what。

 But if she were just handed a list of numbers or a stack of papers。

 each of which was a different denomination of bill。

 like there's not necessarily obvious how we go to about solving this problem sorting the values。

 And after all， even though the phone book that I tore in half in week 0 and the phone book I keep referring to on my phone and yours is presumably sorted by first name or last name so you can find names and numbers quickly。

 well， how much effort is required in sorting those names and numbers。 So case in point。

 if for instance， I handed you all of these sheets of paper on which are these different dollar amounts。

 and they weren't necessarily in any particular order and said， I simply hand you a stack of 7。



![](img/80f8485c3fcfba2e4a80e6525679ec92_10.png)

Dollars of various denominations like this。And say find me the number like 50 and they're sort of randomly organized。

 What's the algorithm for finding the number 50。 Well。

 you could just kind of sift through them one at a time， Aka linear search。

 and you'd eventually find it correctly， or you could take a moment sort them all and then much more quickly get me the answer I'm looking for。

 but would anyone in this room realistically， whether it's  seven pieces of paper or 700 pieces of paper。

 Would you bother sorting them only then define me the answer。😡，Yes。Yes， no。 Would anyone sort them。

 I mean， I'm kind of setting you up for。Contradiction like no， to be stupid to sort them。 Why。

 because if you're only being asked one question， find me the 50。

 Why are you wasting time sorting those values in order to find a number that you might as well just sift through quickly and find it by big and running time the first place。

 But suppose I hand you those bills or suppose I hand you a big database of names and numbers。

 And I expect that you're gonna want to search for someone again and again and again。

 like your phone， Apple or Google probably are sorting all of those names and numbers Y。

 because you're not going look up one person's number in the lifetime of your phone。

 you're probably going to maintain the thing sorted the whole time so that every time you look up someone's name and number。

 that operation is in fact quite fast。 And so that invites the question then just how efficiently can we actually sort values and what does it then mean to actually sort these values。

 Well， the problem of sorting of looks like this。 if our input and output paradigm is to be believed the input to the problem would be unsorted data。

 So like randomly ordered bills or randomly ordered names and numbers。

we want to be sorted specifically。 then if we deal with like an array。

 Here's an array of numbers from 0 through 7 completely unsorted。 So same idea as the dollar bills。

 but I use smaller numbers because it's a bit easier。

 The goal at hand is to get them from 0 to 7 in increasing order。 But for that。

 we need some algorithm to actually do the sorting the step by step instructions。

 And it turns out there's gonna be bunches of ways we can do that。

 but maybe just to set the stage before we take a break and have the most delicious hello panda chocolate biscuits today。

 we get8 volunteers to come on up。 And I can offer you an extra snack in the form of these little Mario mushrooms。

 How about one2。😊，Okay， three， four。Five， how about six。Yes， you， who would just put your hand down。

 seven on the end there， and let me find some about eight in the Harvard sweatshir。😡，All right。

 come on down， come on down。And if you ate volunteers before we do hellos。

 if you want to grab a number from Julialia on the side of the stage， those of you with numbers。

 come on over to the middle of the stage here。😡，And line yourself up in this order from left to right。

 So hopefully we have 1，2，3，4，5，6，7，8 volunteers。 Good line yourselves up from left to right in the order you see above you。

😊，And Julialia has your numbers for you。All right。Line up here。Okay， line up over here。

 fo number five， you're over here。Okay，7，2，5，4，1，603。 Okay。

 how about some quick introductions from right to left？Hi， I'm Becca。嗯。待会儿聊。Hi， I'm Becca。

 I'm studying electrical engineering and I live in Wiigglesworth。Hi， I'm the P。

 and I just getd from Northeastern in masters and information systems。Okay， hi， I'm Erin。

 I live in Staoughton Hall， and I want to study CS S， nice。Hi， I'm Bahara。

 I live in there and I'm planning to study biomedical engineering。 Nice Hi， my name is At。

 I'm in Wisworth and I'm planning to study economics in CS。😊，Hello， I'm Zorif， I'm from India。

 I'm studying computer Science s Clark University。Hi， I'm Jasmine。 I'm from Shanghai。

 I live in Thaer， and I plan on studying C， S and Econ。 nice and Hi， I'm laying Im from China。

 Shenzhen。 I live in Dein。 wonderfulnderful， let's3。

 we have three attempts here to sort these numbers。 Go ahead， sort yourselves from 0 to 7， go。😊。

Money， we had it easy。All right， correct， what was their algorithm？What was the algorithm？

Could someone explain step by step。 Yes， what they just did。Okay。Okay。

 so to summarize those of you who had small numbers generally came this way。

 those of you with big numbers generally came that way。 And step 3 was。

 and then they generally figured it out。 Okay， so that's correct。

 And that seems to have been a fairly organic process。

 But let's take a more of a methodical approach here。

 Can you reset yourselves to match that same order。 So unsort yourselves again。

 And let me propose that we try a couple of different approaches step by step。

 So here we have some data that is unsorted。 And there's a few different ways I think I could sort of wrap my mind around this。

 If I want to get the smallest numbers on the left， the biggest numbers on the right。

 What I think I want to do is maybe do exactly that， like let me find the smallest number。

 So7 at the moment is the smallest number， but wait a minute，2 is now the smallest。

 So I'm gonna remember that not 5， not1 is now the smallest number。 I'm going remember that6，0。

0 is now the smallest number and 3， So I think so long as I'm using at least one variable in my mind to keep track of what the smallest number is that I have seen。

 I can select number 0。 And if you don't mind following me here。😊。

We can put number zero at the beginning of this array， but but but before you move。

 we couldn't have everyone scootch to the left right， by taking a step， but that's kind of wasteful。

 I think right that means like a lot of work for a lot of people just to make room for number0。

 what would be smarter。😡，If I want to put0 on the left here。Yeah。

 maybe I can just swap with number 7。 like you're in the wrong place anyway。

 So could you please go over there instead where number 0 was and number 0 come on over here。

 And now we have begun to sort the list。 I haven't solved the problem entirely。

 but to use the vernacular of week 0。 I have taken a bite out of the problem。 And frankly。

 the problem is now smaller because if 0 is in the right place。

 Now I have only6 problems remaining instead of 7。 So maybe I can do the same algorithm again。

 Allah are familiar loops。 and select the next smallest number。 So2 at the moment is the smallest。

 So I'm going remember that5，1 is now the smallest。 I'm gonna remember that6，7，3。 Okay。

 so1 is now the smallest。 So if you don't mind joining me here。 we're not gonna move you all。

 but I think we're gonna evict number  two now and have you go over there instead thereby swapping the values。

 let's do this once more。 So I can ignore 0 and1。 So the problem is now size 5。 Sorry。

 I'm off by one。 The problem is now size 6 because we have8 volunteers and not 7。

 my apologies5 is now the smallest4 is now the smallest2。Now the smallest。

 I'm going to remember that， but I am still going to keep going， because at least for the moment。

 I'm assuming sort of small brain here。 I only have one variable with which I'm keeping track of numbers。

 And even though everyone in the audience with your bird's eye view remembers that two is obviously now the smallest number。

 The only way I would remember if two is now the smallest。

 is if I were using one to like multiple variables， but I'm keeping it simple。

 So I'm only using one variable in this story to keep track of the then smallest value。

 Now that I know it's2， let's pull you back out。 even though we're undoing something here 5。

 let's you move you here。 so that you two effectively swap。 Now I'm going do it a little faster。

 So3 come on out and swap with4。😊，Now， let's go ahead and do four。 Let's go ahead and swap you with5。

 selecting the now smallest element。 Let's now go ahead and select 5 and swap you with 6。

 And even though I'm kind of making a bit of a mess here。

 I'm doing the exact same thing again and again， I just got a little unlucky here。 And now 6 and 7。

 let's go ahead and swap you。 And now7， I'm all done。 So I think now they are sorted。

 And that clearly took way longer。 But I think if we just did it like this like this like this。

 it would be not only correct， it would be step by step and replicable。

 and there would be no more sort of magical figured it out at the end。

 But let's take one final stab at this before we break。

 if you could go ahead and unsort yourselves to look exactly like that。 One final time。😊，And。

As you do this here， we now have the exact same order as before。

 So why don't I take different types of bytes out of this problem。

 Because maybe I just think about the problem a little differently。 And as we've said since week 0。

 there are often multiple ways to solve the same problem。 And you might think differently for me。

 So here's maybe how you would think about it。 Instead of going back and forth and back and forth。

 looking for the next smallest element， let's just solve the problem in front of me literally。

7 and2 are the first two elements of this list。 but they are clearly out of order。

 So what could I do， Let's just swap 7 and 2。I have fixed at least one problem now。 Now。

 let's look at 7 and 5。 They are out of order。 so let's swap those two。7even and four。

 you are out of order， let's swap u2，7 and1， you are out of order， let's swap you2。

 7 and6 out of order， swap you2。😡，7 and 0 out of order。 swap U 2，7 and 3 out of order。 swap U 2。 Now。

 I have improved the situation。 Why， what's the most glaring improvement， Who is in the right place。

😊，Like 7 is in the right place。 So even though my algorithm was fundamentally different。

 I looked at pairs of people adjacently， and I swap them if and only if they were out of order。

 I did take a bite out of this problem。 I have solved the problem of 7。 And so now。

 if I do this again， I can essentially ignore everyone at this end of the list because the biggest number thus far has sort of bubbled up to the top。

 So I bet I can do the same exact thing by just taking these small bites out of the problem。

2 and five you're good，5 and4 swap 45 and1 swap。F and6 good，6 and0 swap。

6 and three out of order swap， I don't have to even look at 7 because I already solved that problem。

 Now I've taken a second bite out of the problem。 Now， even though I'm going back and forth。

 back and forth in a different way， I'm focusing more locally on pairs of problems，2 and4 are good。

4 and one swap，4 and five good，5 and0 swap，5 and 3 swap。😡，Don't have to touch 6 or 7 anymore。

 So I'm nearing the end here，2 in one swap。2 and four， stay to a 4 and0 swap，4 and3 swap。

 don't have to look at 5，6，7 anymore。 Now back here，1， two， you're good，2，0 swap，2，3， stay the same。

 Don't have to look at 4，5，6 or 7 anymore down over here， one0 swap。😡，Now， I could just stop。

 but again， I don't have as the computer this luxury of this bird's eye view。

 I only know if I'm done by going through the full algorithms，1 and two good，2 and 3， good，3 and4。

 good，4 and 5， good，5 and 6 good，6 and 7 good。 But I'm gonna do one last pass because I previously made a swap And I think what I could do is stop if and only if I make no further swap。

 So let's do this again，01，12，2，3，3，4，4，5，56，6，7。 Now。

 I would be crazy to repeat that process because why bother going back and forth across the list if I've done no work So I think I can conclude that the list are now sorted So it turns out that what we have just done is implement two different algorithms to of many different algorithms via which you can actually sort values on the screen after our 10 minute break。

 complete with cookies will come back， translate this to code and something more algorithmic。

 But finally a big round of applause for our volunteers come on over this way。😊，See you in 10。

Alright， we are back。 So let's slap some names on the two algorithms that we just did with our volunteers。

 the second and the third algorithm in particular that were're much more formulaic。

 The first of which we're gonna call selection sort。

 And I very deliberately was using language like let me select the smallest element and select the next smallest element。

 Select sort does exactly that。 And let's make it a little more rigorous now。

 in the context of these same doors。 So recall that any time we've talked about the lockers for searching for information。

 the leftmost door is gonna be bracket 0， the rightmost door is gonna be bracket n-1， where again。

 n is the number of doors。 And if we start counting at 0 is always n-1 is the n。

 which means mathematically， this is n-2 and so forth from right to left。 So those numbers。

0 and n-1 should generally stick in your mind anytime we talk about arrays So how might we implement in pseudocode。

 what I walked our volunteers through more methodically for that second algorithm。 Well。

 one way would be this for I from 0 to n-1。 In other words， initially。😊，A variable or a finger。

 if you will， and point at the first person first and then generally work your way through the list from left to right in order to get it sorted。

 What do I want to do on each of those passes。 Well。

 I want to do exactly what I did with our volunteers find the smallest number between numbers。

 bracket I starting at 0 and numbers bracket n-1。 So in other words。

 if you start counting I at 0 like any old four loop and C。

 you're going compare everything between bracket 0 and bracket n-1。

 Then the next time around you're gonna compare everything in bracket 1 through n-1 then bracket 2 through n-1。

 and that's why in the first algorithm， I was able to ignore everyone I had sorted behind me already。

 I was constantly shrinking the problem。 And as soon as I found the smallest element recall with our volunteers I swapped that smallest number that I was remembering in my mental variable with numbers。

 bracket I And again， if you start0， that's why we evicted the。



![](img/80f8485c3fcfba2e4a80e6525679ec92_12.png)

First person than the second person to sort of make room instead of creating a whole bunch of work for ourselves and all of our volunteers by like having everyone shift over each time。

 We try to at least do a little more efficiently than that。 Allright。

 so what really was happening maybe at a slower pace with selection sort。

 if we had numbers like this。 Well， if we consider this leftmost element initially to be bracket I in general。

 But of course it's still 0 and then one and then two。 And the end of this list is n-1。

 What did I do on my first pass with that first algorithm that we're now calling selection sort。

 Well， I first kept track in my mind of the smallest element I have yet seen from left to right。

 And the first element is going to be by definition。

 the smallest element if I've looked at no others。 So I'm gonna highlight 7 as being equivalent to remembering 7 in my mind。

 then I found2。 So I updated the variable。5 is not smaller。4 is not smaller。 I eventually found one。

 which is smaller。 So I remembered that number instead，6 is not smaller，0 is smaller。

 So I remembered that instead。😊，3 is not smaller。 And then that's why the next step recall was to ask 7 to move。

 move the0 to the leftmost place and then put 7 back where0 once was。 We could shift everyone over。

 but I was trying to make the point， especially with our array that we only have a fixed amount of space。

 So you can't just kind of like make room for someone。 We only had eight locations in total on stage。

 However， we could have shifted everyone， but it felt like undo work。

 The reality is it's not gonna make a huge difference to the analysis of the running time of this algorithm。

 but it did feel like unnecessary work at the time。 after I've done one path of selection sort。

 I've really only taken one big by out of it。 I still had another 7 and then 6 and then 5 bys to go So the next iteration of this algorithm would indeed update I so that now we're looking at I through n-1 here。

 and we would do the exact same thing again and again and again until we're all done with that problem。

 So see this a little more visually give me just a moment here to pull up a。Animation thereof。

 I'll flip over to this screen in just a moment。 But for selection sort。

 let me propose that we visualize this as follows。 I'm going to go ahead and pull up。

On my screen here， the following comparison sorting algorithms。

 which is a nice visualization that some friends of ours at another university made。

 And this array here represents number。 small bar small number， big bar is big number。

 It just gives us more of a graphical representation of the same。 So ultimately。

 I want all the small bars over here。 All the big bars over there and notice that there's clearly more than eight of these。

 and they happen to be randomly sorted。 What I'm going to do at the bottom of my screen here。

 There's some little playback controls。 I'm going go ahead and speed up the animation a little bit。

 And I'm going to go ahead on the top now and click selection sort。

 And what's gonna happen iteratively from left to right is that they are using pink。

 just as I was using sort of my mind to remember which is the then smallest element。

 And you'll see that it sort of fixates in pink， which the then smallest is and then moves it to the left。

😊。

![](img/80f8485c3fcfba2e4a80e6525679ec92_14.png)

Moves it to the left， movesve it to the left。 And this just goes on and on again and again。

 But you can really see perhaps visually now， how much time we're wasting。 I mean。

 just like I was going back and forth and back and forth across all of our volunteers look at how many times the same bars go from blue to pink from blue to pink。

 because we're touching that is we're looking at the same elements again and again and again。

 until we're finally done。 So selection sort as algorithms go， It's actually not very efficient。

 It's not very efficient， it doesn't have a very fast running time。

 really because of all of those extra comparisons。 So in fact， we can sort of generalize this here。

 If I go back to where we left things off and we originally had this array of numbers， Well。

 if I've got eight numbers to begin with each pass is going take like the first pass is going take n-1 steps if I've got n elements。

 but I want to compare looking for the then smallest elements。

 I have to compare one against n-1 other elements。 So if I want to do some back of the envelope。😊。



![](img/80f8485c3fcfba2e4a80e6525679ec92_16.png)

Calculations here as to how many steps or more specifically。

 how many comparisons selection sort has me make， I would say that on the first pass from left to right。

 I did n1 comparisons。 Why because I started over here whether humans and I looked for the smallest。

 smallest， smallest element and I did so by comparing them n elements。

 a total of n1 times to compare them ultimately， So that's n1 steps the first time。

 but that got me to having zero in the right place。

 So then I had seven steps and then six steps and then five steps and so forth。

 So if I generalize this with n instead of worrying about the specific number of human volunteers we had that's like saying n-1 steps the first time plus n- two steps the second time plus n- three steps the third time plus dot dot dot plus finally one step when I'm all done solving the problem。

 So how can I sort of work this out。 well， if you remember like the cheat sheet at the back of your math book。

 a series like this， actually sums to n times n-1 all divided by two and sort of trust me or take that on faith。

 But that's what it equals。

![](img/80f8485c3fcfba2e4a80e6525679ec92_18.png)

We can sort of apply some high school style multiplication so we've got like n squared minus n by distributing the n all divided by 2 and if multi or if I divide that out I've got n squared divided by 2 minus n over 2 but here's where asymptotic notation is our friend I don't really care at the end of the day precisely how many steps selection sort takes。

 I want to know on the order of how many steps it takes y because again。

 I might have a fast computer or slow computer what I really care about is when n gets really big。

 what really impacts the performance of this algorithm。

 and I dare say that if you take a really big number and square it that's a way bigger deal then just dividing by  two or dividing by  two In other words。

 the highest ordered mathematical term here is the n squared。

 That's the one that's really going to matter when we're talking n equals a million a billion a trillion。

 that's going dominate all of the other characters So if I use my asymptotic notation to describe the upper bound on the running time of selection sort It's on the order of n squared。

Don't really care about the precision when it comes to describing running times。 So n squared。

 it's a lot。 And you can see it visually with that visualization， all of the pink， all of the pink。

 all of the pink is because we were doing so many darn comparisons again and again。

 So is there a categorization we can do here Well with selection sort。

 it would seem that in the worst case， that algorithm might take us as many as indeed n squared steps。

😡，But what about the best case， What about the best case here， when it comes to selection sort， Well。

 could it be omega of1， Could we get away and just get lucky with one step to sort the thing。

 Would it have to be more using the same code？ Well， consider then these doors here as being， again。

 representative of exactly what's been sorted。Could we get away with omega of1 or would it have to be something more。

 Well， here's that same cheat sheet as before。 Does anyone want a conjecture other than the person with whom I had a chat during the break with as to what the lower bound on the running time of selection sort might be。

Maybe n squared， why do you say that？Yeah色。Yeah， really well said。

 even in the best case where the numbers just happen to start sorted。

 which could happen in some perverse scenario， the source code doesn't take into account that being possible in my pseudocode here。

 there' is no allowance for hey， by the way， if or is already sorted， exit or quit early。

 instead it is gonna blindly do this n minus1 times and then do this and then do this blindly。

 So literally if I had eight volunteers come up and they sorted themselves in advance 0 through 7。

 I would have taken the same number of steps， even though nothing interesting would have been happening。

 at least according to this source code。 we could clearly come up with better source code that is written in pseudocode to solve that problem better。

 but at least as written， it does not do any better than that。

 So we would say that selection sort is in big omega of n squared。

 and now just to bring in the other Greek term， the capital theta。

 if we have upper bound of n squared and lower bound of n squared。

 you can also now conveniently say that selection sort is in theta of n。😡。

quaBecause they're one and the same。 It's just a third term we can whip out。

 What about the second algorithm now。 Like clearly， if it was the second algorithm I proposed。

 maybe it is， in fact better in some way， and not just because it might be a different way of thinking about the problem。

 maybe it's better design。 Well， bubble sort similarly treated our humans as this array from size from element 0 on up to n-1。

 here is one way to write that pseudocode。 Again， reasonable people will come up with different pseudocode。

 here's how I might propose doing this。 repeat the following n times just like scratch for I from0 to n-2 So in other words。

 if you think of our human volunteers， I might be my left hand pointing at location0 first。

 And then I want to compare each pairwise person。 So I want to compare person I to person I plus1。

 and that's what's really going on here。 if numbers bracket I and numbers bracket I plus1。

 So if the person my left hand is pointing at and the person my right hand is pointing at are out of order then go ahead。

Swaap them。But I do this a whole bunch of times。 It would seem。 I repeat this n times。

 and then inside of this loop， I also iterate from 0 to n-2。 Well， why is that， Well， n -2。

 We don't normally talk about n -2。 But if I'm comparing my  eight humans and sort of walking down the array。

 like I was， I want to make sure that my left hand does not go to n-1。

 Because n -1 is always the last person， So where would my right hand be pointing at sort of empty space。

 So I need to be careful。 And if I'm comparing things side by side， I want I。

 my left hand to go up to n -2， the second to last person。Or second to last element of the array。

 So my right hand doesn't go over the end of the array itself。 So subtlety。

 but that's why I tried to call it earlier， the n-1 n-2， just to give you a mental model for that。

 Allright， so technically speaking， we can optimize this a little bit。

 And if we really get into the weeds， I only have to repeat this n-1 times y because once I get to the last the end of it。

 like the last person is sort of naturally sorted already。

 I don't have to worry about fixing one person。 They will have bubbled to the right location。

 Allright， so if we have this list of numbers， just as we had our array of volunteers。

 what how can we think about this visually。 Well， left hand is I in the story。

 right hand is I plus 1。 And what did I do again and again and again， I compared them。

 And if 7 and2 are out of order， I swap them 7 and 5， swap them 7 and 4。

 swap them 7 and 1 swap them 7 and 6， swap them7 and 0， swap them。7 and3。

 swap them and notice just as with our humans，7 bubbled their way up all the way to the end。

 leaving me with seven more problems to solve。 but at least I took a byte out of the problem。

 And in fact， on the next iteration， we would sort of come back and start over。

 but strictly speaking， we don't have to go all the way to the end this time。

 So bubble sort fundamentally sorts the array， But does it do it any faster。 Well， here is how again。

 we might write pseudocode like this。 and let me propose two ways of thinking about the bubble sort running time。

 It turns out when you have pseudocode in front of you or in the future。

 actual C code or actual python code。 once you have an eye for it。

 you can literally look at your code or someone else's and reason through how many steps each line of code should take So for instance。

 how many steps will this first line take where you're repeating something n1 times like this one's kind of give me it literally will take n-1 steps because it's just saying what it is。

 All right， what about the loop inside of this loop。Technically， and C， you could use two4 loops。

 You could use two while loops。 I'm just using English vernacular that is kind of simple as possible here。

 But what about this for I from 0 to n-2。 Well， this is technically a total of n-1 steps because if you started 0 and then one and then  two and then three dot dot dot all the way to n-2。

 you have counted a total of n-1 times。 So the outer loop。 by this analysis is gonna take n-1 steps。

 But every one of those interior steps is gonna take n-1 steps。

 So there's some multiplication going on here。 do this inner loop， this many times。 but do that。

 this many times2。 And now how many steps does it take to check if two numbers are out of order。

 Well， that's just like comparing two numbers left hand and right hand。 So that's like one step。

 And sometimes I swap them and all right， swapping them means like this person has to come out。

 this person has to come out， then they have to swap。 So that's like another three steps。

 So maybe this is like one step。 if we just kind keep things simple。Maybe it's four steps。

 I don't really care。 It's a constant number of steps。 no matter how big this array is。

 I'll claim that you can swap people in constant time might be one step might be four steps。

 but it has nothing to do with the length of the array。

 It's only going take the same number of steps to do that kind of swapping So now you can multiply this out n-1 times n-1 times to keep it simple1 or4。

 whatever I'm going ignore that factor。 we can then figure out how many steps this whole algorithm takes In fact。

 if I sort of write this out as before n-1 steps times n-1 times that gives me if I sort of do foil or what not n squared-1 n-1 n plus1 combine like terms n squared-2 n plus1 and here too like I don't really care about this level of precision if I wave my hand out the details this is on the order of n squared also So to be clear。

 if we compared selection sort n bubble sort， technically they're gonna be slightly different numbers of steps。

 but the reality is if you run。algorithmgoms long enough with big enough values of n。

 They're both going be super darn slow because the dominating factor is still n squared。

 Now I can do one optimization。 In fact， but let's first consider what the upper bound is in bubble sort。

 the upper bound apparently is on the order of n squared steps But as written to。

 it would seem that this algorithm as written， also is going be omega of n squared。

 because it's never taking into account， hey， wait a minute is the array already sorted in which case stop sooner。

 we don't have any language for that here， but what if I add a super simple conditional here。

 I could after every iteration from left to right， just ask myself。

 did I make any swaps on that pass through the volunteers If so there might still be work to be done。

 But if not， why am I going crazily repeat myself， because if I didn't make any swaps one time。

 I'm definitely not gonna make any swaps the next time， It's going to be stuck in some loop。

 So I can sort of short circuit， my logic， by just saying hey。

 if no swaps on one of those passes quit。You are done。 And if I do this now。

 such that now I do maximally one pass if the list is already sorted to notice that the list is sorted。

 what could you say bubble sort slower bound is using omega notation。😡，Omega of n。

 It has to take you at least n steps logically to figure out if the array is sorted。

 It cannot be omega of 1。 Like if you're looking at8 elements， let alone n elements。

 there is no way logically to take one step and conclude that all n elements are sorted。

 That makes sort of no sense。But it is indeed an omega of n because you just need one pass to conclude that everything is indeed in order。

 So it seems that bubble sort is actually a little bit better。

 Let's see how it actually plays out visually， Let me go ahead and go back to my visualization from before。

 I've reranized it。 And I'm gonna click this time， bubble sort。

 And you'll see that it's gonna solve the problem and fundamentally。

 with the fundamentally the same outcome。 But notice that the work it's doing is a little different。

 The pink indicates now which two pairs of elements are being compared again and again。

 it's sort of non- obvious what's happening over here。 But clearly。

 the biggest numbers are bubbling their way up to the end of the array， just as our human volunteers。

 We had number 7 and then 6 and then 5 and then4。😊。



![](img/80f8485c3fcfba2e4a80e6525679ec92_20.png)

But again， here， too， you can see visually how many times we are retracing our steps to ask a different question。

 But again， touching or looking at the same elements in memory again and again。And again。

 and this isn't even this many elements。 What are there like 100 or so elements here。 Like my God。

 this is taking forever to sort this many elements。

 Maybe this is why then if you just need to answer a question once， you just sift through the papers。

 Find me the number 50 and don't bother sorting all together。 But if you sort it once。

 and then you have millions of customers like Google searching and searching and searching。

 maybe it's worth spending that time up front and then amortizing it。

 So to speak over the lifetime of the data itself。 Okay。

 I don't have to keep stalling because now that algorithm has concluded。

 So to be clear with that optimization in bubble sort。

 we can make it sort of better than selection sort。 But ultimately， it's going to。

Be still on the order of n squared steps。😡，Questions on selection or bubble sort。😡。

Or sorting more generally yeah。Oh， good question。 What happens if I press bubble sort now knowing that is already sorted。

 let's see if this visualizations implementation is the smart version with that additional conditional or if it just goes back and forth and back and forth。

😡，O， not well implemented。 Notice that they are just blindly doing the first version of my code where there's no additional check。

 Did I do any swaps， Because even though you're seeing pairs of pink。

 none of those bars are actually moving。 So this is both big O of n squared and omega of n squared。

 A K， A theta of n squared， A K， A poorly implemented。 In this case。

 missed opportunity for them to have done this。I don't know if you need to be convinced that it's not gonna do anything。

 But allright， it'd be like holding in a sneeze if we don't go to the end。Almost done。 Almost done。

 Almost done， and。No useful work was done。 But it's now indeed sorted。 All right。

 Can we do better than selection sort， Can we do better than bubble sort， Yes， and there are dozens。

 hundreds。 I mean， maybe thousands of different sorting algorithms out there。 And in fact。

 bubble sort and selection sort can be useful in the real world。 I mean。

 I have actually in like research projects quickly whipped up in code and implementation of one or the other because it's just so relatively easy。

 like first time through it like you're gonna to make mistakes， you're gonna have buggy code。

 but they're relatively easy algorithms that you don't have to think hard about。 And in fact。

 sometimes it's faster to whip up a bad algorithm and just let the code run than spend more time writing a better algorithm。

 only for it to be done like this， It's kind of a wash sometimes in the real world。 But in practice。

 what we're gonna to find is you and I， except for something like a homework assignment are not going be in the habit of writing sorting algorithms anyway。

 we're going to use a library， like a lot of those other functions。

 but you'll understand what algorithms are actually doing for you underneath the hood。 So what is a。



![](img/80f8485c3fcfba2e4a80e6525679ec92_22.png)

Technique， we can bring to bear on this problem that might help us think about the problem a little bit differently。

 And maybe help us solve the problem better。 And by better， I mean。

 let's stop repeating ourselves by touching those elements again and again and again。

 let's really try to minimize the number of comparisons we're doing because that's what was getting computationally expensive in terms of time。

 So here， for instance， is an algorithm we've seen before， namely searching for things behind door。

 So this was binary search， same as before， whereby instead of looking for 50。

 I'm more generally looking for a number behind the middle door or to the left of the middle door or to the right of the middle door。

 even though I didn't call it this earlier， It turns out that this algorithm as we used earlier today is an example of what's called a recursive algorithm。

 A recursive algorithm is one that calls itself or put more plainly， in the world of C。 and frankly。

 in the world of mathematics， a function is recursive if it called。

Itself now we've used main in C code and we've called get in。

 we've used main and we've called get string。 What if main called main， for instance。

 that would be an example of recursion， but generally frowned upon to have main called main。

 But we could certainly have another function that we write that maybe does call itself toward a useful end。

 So why is that Well notice that in this algorithm from earlier binary search。

 it's already implicit that this search algorithm is using a search algorithm。

 because I left it unstated。 well， what does it mean to search the left half。 Well。

 implicitly to search the left half means shorten the list by half。

 and then do all this again logically， just apply the same logic to a smaller data set。

 And because when we went left or right or left or right， both this weekend and week 0。

 because we kept shrinking the problem， it's okay if you keep doing the same algorithm again and again。

 the problem getting smaller。 So eventually you're gonna have no doors left。

 or eventually you're going to find the number you're looking for。

 So these cases here where you have very specific cases like。There are zero doors left。

 or if I'm found the number I'm looking for， those are generally what they're called base cases where the thing sort of bottoms out logically and you get back an answer at that point。

 no matter what these two lines that I've highlighted or generally called recursive cases whereby you don't get an answer yet。

 you have to do more work by generally shrinking the size of the problem and doing the same logic again。

 So a recursive algorithm or recursive function is one that calls itself that uses itself but hopefully on a smaller and smaller size problem。

 All right， so with that said， here is the same pseudocode from week 0。

 when I was searching the physical phone book looking for John Harvard， for instance。

 trying to call them if the number is there。 notice that in week 0。

 I actually used very deliberately a loop。 It was not called that per se until we slap some terminology on this algorithm。

 but I literally said go back to line 3， go back to line 3。

 and then we said you can call these things loops and it means sort of visually you're going。

Back and back and back。 But this could be rewritten this algorithm from week 0。

 we could do something like this。 instead of saying open to the middle of the left half of the book and then go back to line3。

 which really just means search the left half or search the right half。 Why don't we just say that。

 So let's collapse these two pairs of lines from week 0 and just say search the left half of the book。

 search the right half of the book。 I can now get rid of the blank lines and kind of tighten the algorithm up。

 And now it's a shorter chunk of pseudocode。 even though it's sort of left unsaid。

 what do you mean search the left half。 What do you mean search the right half。 Well， who cares。

 I don't need to tell you how to search half of a book。 I've told you how to search a whole book。

 So just use the same logic to search half as many pages， half as many pages， half as many pages。

 So whereas the previous version of this code here is an iterative version of our code in so far as it uses loops。

 This version now is a recursive version of that same algorithm。

 So sometimes you can solve problems with iteration that is loop。Or with recursion。

 and sometimes one problem is just better suited for one or the other。

 And among our goals in the coming weeks is to help you identify when you might want to use one technique technique or another。

 but generally iteration tends to be the more comfortable approach。 But let's see this in context。😡。



![](img/80f8485c3fcfba2e4a80e6525679ec92_24.png)

There is， I've claimed recursive algorithms， recursive code as in here。

 there's also recursive physical structures in the world like here's that pyramid from Mario。

 this one being pretty short and of height4， let me get rid of like the distractions of the background This physical structure is recursive in some sense why Well this pyramid of height4 is really just a pyramid of height 3 plus one more layer of bricks Well what's a pyramid of height 3。

 a pyramid of height3 is really a pyramid of height2 with one more layer of bricks。

 what's a pyramid of height2 It's really just a pyramid of height 1 with one more layer of bricks。

 what's a pyramid of height1 just a single brick。😡，So that last statement is sort of a base case。

 at some point， I can't just keep like dragging things out and telling you。

 telling you how one is based on the other。 At some point。

 I just have to say parayid I1 is's just a single brick stop。

 but everything else can be recursively defined in terms of a pyramid of a smaller size。

 So if actually， I want to do this implementation。 Let me actually whip this up in two different ways。

 Let me go back to V S code here in just a moment。😡。



![](img/80f8485c3fcfba2e4a80e6525679ec92_26.png)

And in V S code here， let's go ahead and make something called say iteration do C。

 just to make clear what kind of technique it is。 So in V S code。

 I'm gonna go ahead and say iteration do C。 And in this program。

 I'm gonna write code that prints out a pyramid like this of height4， for instance， or anything else。

 So let me go ahead and at the top of this file include C50 H So I can ask the user how big it should be include standard I O do H。

 So I can actually use printf。 Let me go ahead and in int main void just tee up the beginning of a program that's going to ask the user for a height of a pyramid using our friend get int And then I'm gonna assume for the moment that there is a function called draw whose purpose in life is to draw a pyramid and' going pass in that height done。

 So this now invites the question how do you implement the draw function。 Well。

 couple of different ways， let me do it iteratively with a loop。

 So let me go ahead and define a function that doesn't return anything because I just need to have side effects printing on the screen。

 I'll call it draw It takes as input a value。😊。

![](img/80f8485c3fcfba2e4a80e6525679ec92_28.png)

![](img/80f8485c3fcfba2e4a80e6525679ec92_29.png)

Like n for the height that I wanted to draw。 And then inside of draw， what am I gonna to do。 Well。

 this is easier than problem set 1 was because of the direction that the pyramid is heading。

 So this I can do fairly quickly as4 int I is 0 I is less than n I plus plus and then inside of that loop。

 So that's gonna give me row row row row。 I want to now print out I want to print out the number of bricks for a given row。

 I claim with a quick glance。 int J equals0 j is less than I plus1 J plus plus and then in here。

 I'm going to go ahead and print out a single hash。 Then out here。

 I'm going to go ahead and print a new line。 So I did this super quick。

 but let me convince you that it probably is correct here I'm iterating from0 up2， but not through n。

 So if I want a pyramid of height4， this is like giving me the first row， the second row。

 the third row and the fourth from top to bottom because that's how the screen scrolls but then inside of。

Of those rows， how many bricks do I want Well on the very first topmost row of a pyramid。

 no matter its height， how many bricks do I want there。The very top。

 I just want one like the single brick。 Well， if I start counting I at0。

 I don't want to print zero brick。 so I need to do a bit of arithmetic here。 I need to do I plus one。

 So0 plus one ensures that this inner loop J gives me one brick and then two bricks and then three bricks and then four。

 So I just need to be a little clever and think about the arithmetic。

 but I think that gets the job done。 that prints out hash has1 at a time。 but at the end of each row。

 I move the cursor to the next line。 So even though I did this pretty quickly。

 and it might have taken you much longer to do problem set1 is expected。

 I think this will give me what I want so long as I avoid making the past mistake。

 I need to put the prototype of this helper function at the top。 So let me open my terminal window。

 make iteration enter so far so good dot s iteration enter， let's do a pyramid of height4。

 and it seems to in fact work。 And I can do this even bigger。 Let me do a pyramid， for instance。

 of heights， maybe 12 enter and it seems to be work。Indeed， with iteration。 Well。

 what if I instead want to use recursion as a technique instead， I bet I can actually do that。

 because again， what is a pyramid of height 4， Well。

 it's like saying print a pyramid of height 3 and then add one more row。 Well。

 what's a pyramid of height 3。 Well， print a pyramid of height2， and then add one more row。

 What's a pyramid of height 1， a2。 Well， print a pyramid of height 1 and then add one more row。

 The only problem that's interesting is how do you print a pyramid of height 1。

 Wellll just print a single brick。

![](img/80f8485c3fcfba2e4a80e6525679ec92_31.png)

So curiously， that kind of thinking will actually give us a fundamentally different solution。

 So let me do this。 Let me shrink my terminal window and close iteration dot C。

 Let me open a file called recursion dot C just to make clear what technique I'm using。

 Let me include C 50 dot H at the top。 Let me include standard I O dot H at the top。

 int main void again。

![](img/80f8485c3fcfba2e4a80e6525679ec92_33.png)

And in here， again， int height equals get int and then ask the human for the height。

 then go ahead and call an imaginary draw function passing in that height， which doesn't yet exist。

 But now let's make it exist。 This function will again return no value because it's just going print some side effects to the screen。

 It's called draw and it takes in the height， Call it n or whatever you'd like。 In of this function。

 Let's go ahead and。Consider what our base case is。 And I could say， if the pyramid is of height 1。

 go ahead and print one brick。 But you know what， even easier。

 how do you print a pyramid of height 0。You do nothing。

 So I bet I can be even more clever here and just say if n equals equals 0 oops equals equals 0。

 then go ahead and just return。 Don't return a value because it's void， don't print anything。

 if you want a pyramid of height 0， you got it， I don't have to do any work whatsoever。

 If I really want to be careful， I can say， if you somehow do something crazy。

 Like give me a negative number。 I'm also not gonna to do anything because that makes no logical sense。

 But that's just more of a finer detail。 How now do I print a pyramid of height N。

 According to my logic from earlier。

![](img/80f8485c3fcfba2e4a80e6525679ec92_35.png)

What would you have me print first as a pyramid of height。N。



![](img/80f8485c3fcfba2e4a80e6525679ec92_37.png)

Against kind of circular logic， but。How can I print a pyramid of height N？

I think I can draw a pyramid of height n minus1 which doesn't even seem logical because I haven't even solved the problem yet it would seem。

 but if again you believe me that a pyramid of height4 is really just a pyramid of height3 plus one more row that is what I've expressed thus far。

 print a pyramid of height3 but now I have to print one more row Well the one more row is actually trivial Y because when I have a pyramid of height4 what should the width be of themost row4 So it's nice n equals n like it's exactly what we want So I can do this pretty mindlessly in code for int I equals0 I less than n I plus plus and then in this four loop。

 I think whoop in this four loop I can just print out a single hash mark and then at the bottom of that I can print out a new line So weirdly and let me add my prototype up here void draw int n semicolon Let's focus on the draw function here。

 I feel like I haven't even solved the problem that you asked me to。



![](img/80f8485c3fcfba2e4a80e6525679ec92_39.png)

![](img/80f8485c3fcfba2e4a80e6525679ec92_40.png)

![](img/80f8485c3fcfba2e4a80e6525679ec92_41.png)

![](img/80f8485c3fcfba2e4a80e6525679ec92_42.png)

Solve like one， I pled off this arbitrary problem。 Like if you want no pyramid fine。

 no pyramid It is return without doing anything。 Then I'm sort of cyclically saying， well。

 if you want a pyramid of height n， we'll just go draw it yourself as a pyramid of height n-1。

 But then the last thing I'm doing。 And this is where the magic actually happens。

 I am also saying once you're done doing that other thing recursively， give me one final row。

 and where this works out logically， if you sort of reason through this in your mind。

 suppose you want to print a pyramid of height 4 initially， Well。

 this does not apply because4 is bigger than 0。 this does apply。 So you print a pyramid of height 3。

 that puts you logically back in this function。 How do you print a pramid of height 3。

 not applicable。 Well， you print a pyramid of height 2， then we get back here， doesn't apply。

 How do you print a pyramid of height 2。 Well， you print a pyramid of height1。 Okay。

 let's go back here。 doesn't apply。 How do you print a pyram of height 1， Well。

 you print a pyramid of height 0， that gets us back into here。 Now this applies。 and I do nothing。

So it rewinds logically in your mind if following along。

 And I just said to print a pyramid of height 1， I first print a pyramid of height 0。

 did that didn't require much effort。 What do I then do then draw one more row。

 And if N at this point in the story is indeed one this four loop is designed to print one hash。

 then the function will end。 And if you rewind in your mind's eye。

 how did we get there while I ask to print a pyramid of height2。

 but I first ask to print a pyramid of height1。 But all I have on the screen is a single hash。

 But I add another row to that。 And if n equals two now that gives me two hashes。 this finishes。

 Now we rewind again now I print another row，3 hashes。

 Now this finishes and rewinds now I the fourth row。

 So sort in this weird mind bendending way But not answering the question。

 but sort of kicking the can down the road by saying no。

 you go do this So long as you take one by out of the problem。 One row。

 it logically all just kind of works out in the end。 So if I haven't made any typo， let me open。

My terminal window here， make recursion， dot slash recursion。 Let's do height4。

 It actually does work。 Let me make my terminal window even bigger and do it again。

 dot slash recursion 12， it does actually work。😡。

![](img/80f8485c3fcfba2e4a80e6525679ec92_44.png)

So which is better。 Well， in some cases of solving problems。

 it just helps to write code recursively when what you were trying to do itself is recursive in nature。

 And even though you probably haven't thought about any of the pyramids in Mario is being recursive。

 they actually now are because again， a pyramid of height 4 is's just a pyramid of height3。

 It's just a pyramid of height2， It's just a pyramid of height 1 is's just a pyramid of height 0 plus one more row。

 plus one more row， plus one more row plus one more row。

 we'll see future problems where in the data structures we're using in the computer's memory or sort of laid out two dimensionally。

 those kinds of problems too may very well lend themselves to recursion。

 even if you can also use iteration or four loops as well。 recursion is such a common technique。

 but a challenging technique in the real world that there's even little Easter eggs out there。

 In fact， let me go ahead and。😡，Give me just a moment to pull up a browser。

 and then I'll switch screens。 If I pull up， say， Google here。



![](img/80f8485c3fcfba2e4a80e6525679ec92_46.png)

Any old Google window。 And you want to learn more about recursion。 So recursion enter。

 you'll notice this little Easter egg that the geeks at Google have had latent in Google do com for years。



![](img/80f8485c3fcfba2e4a80e6525679ec92_48.png)

Does anyone see the C， S joke at hand。Yeah。呃。我在。Yes， it's asking you， did you mean recursion。 Well。

 I'm pretty sure that's what I type。 So， let's click recursion。 now we're night mode for some reason。

 but did you mean recursion。 I mean，'s's maybe the kind of laughter it warrants。 But this is a joke。

 Like it's recursion in the sense that Google is telling you to Google recursion again and again。

 But of course， the second and third results or whatnot or actually real results。

 but you can try that at home by simply searching for recursion。 So again。

 all it means for a function or an algorithm to be recursive is that if it uses or calls itself。

 but so that you don't get into some infinite loop like Google。

 which ironically is sort of buggy in it will never stop。

 you have a base case where you just pluck off the easiest of the problems。 He  zero1。

 whatever it is so that the interesting work is left to the recursive calls where you call yourself again and again。

😊。

![](img/80f8485c3fcfba2e4a80e6525679ec92_50.png)

![](img/80f8485c3fcfba2e4a80e6525679ec92_51.png)

All right， any questions though on recursion？Versus iteration。ho。Okay。

 we've got one algorithm to go because I don't like selection sort or bubble sort yet。

 even though bubble sorts seem to be a little better with that optimization。 my God。

 even just to sort 100 elements， that code felt very slow on the screen when visualized。

 Well let's introduce one other algorithm for sorting， even though there's many more out there。

 But merge sort is an algorithm that I claim is gonna be faster。

 even though it too will probably by design bend your mind a little bit it's a little hard to wrap your mind around at first glance。

 but among its ingredients are going to be recursion。

 So the algorithm for merge sort is essentially this three lines of pseudocode。

 which in and of itself sort of hints at the sort of mind bending sort the left half of the numbers。

 then sort the right half of numbers， then merge the sorted halves。

 So like that is literally merge sort。 if you are handed a whole bunch of numbers like an array of numbers like we were earlier before the break。

 how do I go about sorting all of them Well， first sort the left half。 then sort the right half。

 then merge the sorted haveves And the first two lines here field kind of obnoxious。

Like I ask you to sort and numbers and you say， well。

 you go sort these numbers and then sort these numbers。

 Like I haven't actually given you a solution to the problem。

 but there's some magic in this last step。 merge the sorted haves。 So what do I mean by that。 Well。

 first， let's consider the base case。 if I give you nothing to sort。

 you can pluck that one off trivially。 Just quit。 if there's only one number or heck 0 numbers you're done。

 And so that case is easy。 But the recursion is clearly manifest in these two lines because this is an algorithm called merge sort。

 And if I'm telling you to sort the left and sort the right， well。

 you're probably going to use the merge sort algorithm to do that。

 But the problem is gonna get smaller and smaller。 So what's focused on what it means to merge to sorted have。

 So wonderfully during the break， we replace the lockers with these here shelves and on these shelves are two sorted lists of size 4。

 The whole list is not sorted because notice I got 1，3，4，6， but I've got 0，25，7 over here。 suppose。

 though， I want to merge these two sorted lists。😊，Tother each of size 4 into one bigger list of size 8。

 How can I go about doing that？ Well， this is what it means to sort two lists。

 You point at the first element of the first list。 maybe with your left hand。

 you point at the first element of the right list， maybe with your right hand。

 and you compare those two values。 And obviously， if I'm pointing1 over here， and0 over here。

 which is the smaller of the two， Well， of course，0。 So what do I do， I take it physically here。

 I'll light it up for dramatic sake。 and I'm gonna put it into its appropriate location up here。

 Now my left hand is still pointing at the one on this list。

 My right hand is gonna move to the right and point at the two。 same thing。

 How do I merge these two sorted lists， one of size 4，1 of size 3。

 Well I compare when I'm pointing at the one and the two。 let me go ahead now。

 and pluck the one off and put the one at the very top there。

 Now my left hand and right hand are pointing at3 and 2 respectively， I compare2， of course。

 is smaller， So I grab this light it up and put it up there。 Now I'm putting it three。And5，3。

 of course， comes next。 I turn its light on， and I put it in its right spot up here。

 Now I'm pointing at 3，4 and 5。4 comes next。 So I do this。 Now I'm pointing at 6 and 5。

5 coordinates next。 So I turn this on and pop it up here，6 and 7。

 Not I'm down to one element in each list。 I'm almost done merging。 I pluck off 6。

 Now I don't have to do any more work to do with my left hand， my right hand finishes here。

 and I have merged the two lists together。 How many steps did that take。 Well。

 there's8 elements total 0 through 7。 And every time I made a comparison。

 I moved my left hand or the right hand。 So ultimately。

 I moved each of the eight elements once and only once。

 So that's n steps to merge two lists of size n over 2 plus size n over 2。And that's it。

 So that's what I mean to smge to sorted lists。 But there is something subtle about what I did here。

 That was pretty straightforward。 seems pretty easy to merge to already sorted lists。

 But why am I using shelves all of a sudden， This is very intentional。

I didn't just use a single table like where we had the lockers a moment ago， yeah。😡，呃，Yes。

 I'm not shuffling the numbers around。 I'm not swapping things around in the same memory as our humans were。

 I'm kind of cheating and using some extra space， if you will， literally twice as much space。

 I started here， and then I used sort a separate array that was blank for me sort of allocated but not used to store that。

 And this speaks to a fundamental tradeoff we're gonna to start to see almost always in computing if you want to improve the running time of something。

 you got to spend some resource。 you have to increase the amount of space。

 maybe that your algorithm uses。 You have to increase the amount of time that you。

 the human developer put into figuring out the problem。 case in point， when I said earlier。

 sometimes I take shortcuts， and I'll whip up a very stupid， simple sorting algorithm。

 Why because my time， I'd argue is valuable when I'm trying to solve a problem。

 and I'd rather spend time on other things。 So I don't spend much developer time。

 but that means my code is going to be slower as a result。 So space time development time， money。

 any kind of physical resource energy nowadays is something that you can either increase or decrease and have an impact on these。

Other measures as well。 So that's only how we go about merging two lists。

 How do we go about sorting left and right。 Well， for this， let me ask Julialia。

 to join us up here on stage so that all things out digitally on the screen very cleanly will also mimic what we just did here physically with with the physical numbers in order to sort an actual list of values that starts off completely unsorted。

 So the list we're gonna to do is this arbitrarily 6，3，4，1，5，27，0。

 we're gonna start with them all on the top shelf ultimately， and we'll see by acting this out。

 how we can go about sorting 8 elements that start off completely unsorted。

 And the three steps we're going to use are these sort the left half sort the right half and then merge the sorted hves together。

 So those numbers， again， that Ulia is putting in place are 6，3，4，1。😊，Then 5，2，7，0。

 We have not rehearseed this。 So we will see how well we both do together at this。 Allright。

 so here is the array of numbers at top physically represented here。

 You can look at whichever demonstration you prefer。 Let me make clear that this is really an array。

 And indeed， there's only so much shelf space。 Like Julia can't just kind of steal space over here to the right or over to the left。

 like we are limited in space。 But she does have extra space here and technically here and here if she really wants it。

😊，Alright， how do I go about sorting a list of size 8。 Well， what was step 1， sort the left half。

 step 2， sort the right half。 step 3， merge the sorted halfs。 That's all you have to remember。

 So here is the original list。 How do I go about sorting the left half。 Sorry。

 How do I go about sorting the original list。 I go ahead， and I sort the left half。

 So Ju is kind gonna act this out by just using some additional space。 I'll do it digitally here。

 This now is a list of size 4， How do I sort a list of size4。 Well， I've got an algorithm for that。

 So left half， sort right half。 merge the sorted half。 So let's do this。

 Let's go ahead and sort the left half of this list of size 4。😊，And now， how do I sort this thing？

 Well， this is now a list of size 2， How do I sort a list of size 2， sort the left half。

 sort the right half， merge the two hves。 This is where things get kind of stupid temporarily。 Okay。

 done sorting the left half。😡，Done sorting the right half。 But what's the magical third step。

 merge the two together。 How do I do that Left hand， right hand trick。

6 and three are the being compared，3， of course， comes first， and then 6。

 So I have merged those two together。 And so now we have a sorted list of size， too。

 But this is still unsorted。 That's so unsorted。 So what came next。 How did I get to this point。

 I sorted the left half。 I sorted the left half。 I sorted the left half， right half。 I merged。😊。

So what step？Comes next。Sort the right half of that original half。

 This is where it's hard to sort of keep track of。 But if you take on faith。 now。

 I'm gonna sort the right half。 How do I do that， sort the left half of that right half， done， easy。

 sort the right half of that right half。 done。 That was easy。 Let's now merge together。

 Left hand right hand， which comes first， one， obviously， So I sort the one， I merge in the one。

 Now I merge in the four。 Now， at this point in the story， I've got a sorted left half。

 I've got a sorted right half。 What comes next， merge the sorted half。 How do I do that Left hand。

 right hand，1 comes first， So I merge that in。3 and 4，3 comes first。 I merge that in。6 and 4。

4 comes first。 Now I no more right hand。 So I merge in the6。 And now not coincidentally。

 you see that we have sorted the left half just like the short demo I did earlier。

 That was a lot of work， a lot of talking。 We still have another half to go。

 But I'll do it more quickly， let's see how quickly we can do this。

 How do I sort now the right half of the original list after sorting the left half。 Well。

 what do I do， I go ahead and sort the right half。 Alright， Well。

 what does it mean to sort the right half。😊，I'm going go ahead and sort the left half of the right half。

 Alright， what does that then mean， So the left half， done， sort the right half， done。

 merge the two halves，2， and then。2。😊，Two。Okay， good， and then five。Okay， good。

 and now the left half of the right half is sorted。 Now I sort the right half of the right half。

 so I got the 70 and I sort the 7。😡，Done，0， done。 Now I got to do the merge step。

 pointing at left hand and right hand。 the 0 comes first。😡，Then the7。

 Now I have sorted the right half of the right half。 What's the third step。 merge those two hals。

 So I point left and right。0 comes first。Then two。Then five。Then7。And now I've sorted the right half。

 This is like a really difficult prices right kind of thing here。 All right。

 so now we've got the sorted， we've sorted the left half。 We've sorted the right half。

 What's the final， final step。Smerge the two hves， and this is exactly what I did before。

 so dramatically as the lights come on with each of them， pointing at left and right，0 comes first。😡。

then one。Okay， okay， what comes next， two comes next。Then， three。Then 4。Then，5。

Then six and a huge round of applause for youli， if we can once we hit and7。😀Yeah。😊，Thank you。Okay。

So she and I will debrief as to whether we need both of these visuals moving forward。

 But hopefully it makes clear that all we're doing is like this mindless。

 fairly bitesized problem solving of sort left half sort right half merge the two hves。

 And if we now consider just how much faster or slower that is like than an algorithm like selection sort or bubble sort。

 let's see if we can't analyze this just a little bit。 we ended up having an entirely sorted array。

 But how did we actually get there， Well， if we consider what the possible buckets are for asymptotic running times here。

 let's consider the sort of breadcrumbs we might have left along the way。

 If I didn't keep the leading things as I went。 So we started with these numbers up here。

 And at one point or another， we did all of this work that's pictured on the screen。

 even though it only was up on the screen briefly。 So in other words， we started with one list。

 And then how many times did we divide in half one time two times three times。

 So sort we did this dividing and conquering of the entire list three different times So we could get to this。

😊，These leaves， if you will。 And even though we we'll talk about this more in future weeks。

 if you've ever drawn like a family tree where you might have like grandma and。

 grandpa and then parents and then children and so forth。

 it's sort of like an upside down tree whose branches grow downward where the leaves， so to speak。

 like the descendants are at the very bottom of the tree。

 that's terminology will come back to in the coming weeks。

 But how many times could we chop up this original array into smaller and smaller pieces three times for each of these elements here。

 Moreover， how do we how many steps did it take to merge those lists back together。 Well。

 that's gonna be the operative question。 It turns out that the number of times we were able to divide the original list in half and half and half to get to those very single stupid problems of single numbers was log based two of N。

 you can do a bit of a sanity check here， whereby if you just do the mental me if we had eight elements originally。

 and the answer to this question is three， Well， that actually kind of works out Because log based two of8 actually is three。

 which describes exactly。How many times we chopped the problem up into smaller and smaller pieces。

 But again， there was some merging going on whereby we actually wanted to merge those then sorted lists together。

 So how did we go about doing that， Well， every time we merged。

 we only looked at or physically touched the number once before putting it into its place。

 So my hands were constantly working their way through this list。

 such that when we had the singletons done，1，2，3，4，5，6，7，8 work was done。 when we did this work。

 it was1，2， and then 3，4， and then 5，6 and then 7，8 steps as well， to merge those together。

 then it was 1，2，3，4，5，6，7，8， In other words， no matter what conceptual layer of this tree。

 we are in， it was taking the n steps or 8 specifically to do that merging。

 So what that then invites is what's the total amount of running time involved here。 Well。

 if you're doing n things， log based to n times， the total math works out to be n times log of n。

is to say merge sort， unlike selection sort， unlike bubble sort is in big O of n log n。

 which even if you vague remember your logarithms log n is smaller than n。

 So n times log n is definitely better that is smaller than n squared。

 So if we consider our sort of cheat sheet here of the possible running times that are common。

 merge sort is in big O of log n。 However， nothing I or Ulia did took into account whether the list was already sorted or not。

 So it's fair to say that the lower bound on merge sorts running time。

 even if the darn thing is already sorted is also n log n。 Now that's not as good as n。

 but at least in general， it's way better than n squared。 but here again is a tradeoff。

 if you want to have this nice recursive solution using merge sort。

 you might not get a lower bound running time unless we go and add more pseudocode that maybe does something silly。

 like check the list first if already sorted quit。 and you just kind of special case with a conditional but that's sort of a lower level refinement that we won't bother with today。

But merge sort then is an n log n as are， frankly， a lot of sorting algorithms that you would use in the real world or use in a library。

 And so as our final flourish today， what we thought we would do is compare these three algorithms that we focused on。

 selection sort， bubble sort and merge sort in particular。

 what you're about to see is a visualization of some random data three different times。

 the top chunk of data is going to be sorted with selection sort。

 the bottom data is going to be sorted with bubble sort and the middle data is going to be sorted with mergege sort and the goal here will be to actually assess and feel and hear what the difference is when you put a little more time。

 a little more thought， a little more effort into designing your code not only correctly but well and thus efficiently in order to solve problems more efficiently。

 So if we could dramatically dim the lights。

![](img/80f8485c3fcfba2e4a80e6525679ec92_53.png)

We will hit play on this final flourish。

![](img/80f8485c3fcfba2e4a80e6525679ec92_55.png)

All right， the music just makes sorting fun， but that's it for CS50， we'll see you next time。



![](img/80f8485c3fcfba2e4a80e6525679ec92_57.png)