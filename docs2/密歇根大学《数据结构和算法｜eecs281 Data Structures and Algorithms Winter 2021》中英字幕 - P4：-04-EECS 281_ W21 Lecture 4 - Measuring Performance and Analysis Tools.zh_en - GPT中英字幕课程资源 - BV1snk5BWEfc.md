# 密歇根大学《数据结构和算法｜eecs281 Data Structures and Algorithms Winter 2021》中英字幕 - P4：-04-EECS 281_ W21 Lecture 4 - Measuring Performance and Analysis Tools.zh_en - GPT中英字幕课程资源 - BV1snk5BWEfc

Hello everyone， I'm just starting a minute early so you can say hello to Jen today she is our last cat to be introduced。

 Yes， she was named after the character in the Witcher series long before it was a TV series。

 and she's not big on being held right now， so she's going take off。Okay。

 we'll get started in just a second as soon as we hit in here。Oh favorite Mountain Dew flavor。

 I just drink the normal one and yes you've probably seen me doing this。

I often I used to get the one with natural sugar or with king sugar。

 and I haven't been able to find that lately， so yeah， I just drink normal one。Okay。

 one thing I want to mention and I'm going to have to put this on the piazza somewhere when I put in the video about Project one and the note on piazza。

 there's one thing that I forgot that you're going to find useful， which is。Is digit。You give it。

A char。Not a char point or just a char， you give it a char and it will return something that can be tested for truth or falseness。

So this is going to be really useful in project one when you want to say。

Am I standing on a pipe or is this thing that I read in as the tile a valid character？

So little bonus for you now， I'll get that posted to Piazza at some point today for everybody。Okay。

 so today we're going to look at measuring runtime performance and hey。

 good reason to show you is digit because。If you do an or like is the character equal equal to zero or is it equal equal to one or is it equal equal to two。

 that's a lot slower than is digit， is digit is really basically does。

 I think they manage it with one comparison。At worst you could do it with two comparisons。

 you could say， is it like greater than or equal to quote  zero quote and the less than or equal to quote 9 quote。

 would be faster than is it zero or is it wrong or is it two， et。

 and this might even be slightly faster than that。And there's also you might find not for project one。

 but in the future， you might find there's other functions like。Is lower。Is upper。Is space。

Is L known。So is Alum is it an alpha numeric， is it a letter， a upper or lowercase or a number？Is。

Pked。Is it punctuation， is it something other than a space or a letter or a digit， et cetera？

So these you don't really need for project one， they might become useful in the future。

 but is digit definitely useful for this project？Okay， so we talked about complexity last time。

 we talked about devising our driving our complexity formula and getting the big O Now what we want to talk about today is different ways to measure complexity。

So one of them is， hey， I can do what we've been doing since the last lecture or so， which is。

Look at the algorithm or look at the code。Look at the patterns and the loops， et。

 and we can write down the recurrence relationship， which we're going to talk about more next time。

 I believe we're going to talk about recurrence relations next time。

We could also look at time empirically， meaning by taking measurements。

And that's what we're going to predominantly talk about today is how can we measure runtime within the program。

 how can we measure the runtime using external tools， and looking at， you know。

 once we've got this ability in place， testing it on a bunch of different inputs of different sizes。

 etc。Okay， so programmatically， what I mean by that is we could add code inside of the program to do some runtime measurements。

And this varies depending on what language you're using， if we're doing it in C。

 we'd have one way to do it in C+ plus we've got another way， which is on the slide coming up。

Excuse me， and if we are in a different language， we'd have to see what facilities that language would have for it。

So for example here， we got this from American Mill who wrote it for 280， I believe， is a class。

 so we could put all this in a like timer doth and include it and we've got the basically we've got a class if we don't say otherwise。

 remember by default。Everything in a class is whoops not double colons。

I'm still used to doing scope resolution for classes。So。So if we don't say private by default。

 things in a class are private。If we create astruct。

 if we don't say otherwise things in astruct by default are public。

That's the only difference between a class and a struct in terms of language now in terms of how we use them。

 we usually tend to think of if it's just going to be some data that sits there and I look at it。

 it's astruct， but if it's going to have member functions， we'll make a class。

 but really thats there's no requirement that you do it that way。

 that's just a convention to make it more understandable。Okay。

 so this class has some private data it's got the。Current time well really the time at which you hit the start button and it's got an elapsed time。

And it's got some some variables from the Chrono class。 and then we've got the。Timer constructor。

 it says when you make a constructor， set the current time to whatever the default is and set the eapse time to special value 0。

 Okay， so we've got a0 there。 We got start says set the current time to now。

 So start the timer at some point later， we can say stop the timer。

 and it says increase the eapse time by。 Remember， plus equals is the same as saying。

ELAP equals ELAP plus this other thing， so you've got to get used to seeing these combined assignment operators where they do addition and assignment at the same time。

 we often use these in C++ to make the code a little bit more concise。Also。

 sometimes we use it in this class just to get things to fit on slide better。Okay。

 so it says add to the eapse time and there could be parentheses around there that doesn't have to be。

 so take whatever now is right now， take minus the start time and put that add that to the eappsse time。

 reset， set the eappsse time to zero and seconds just returns us that count as a double。

And then there's an example over here on the right of using it， we say create me a timer object。

 start it， do some stuff。And then we display the how long task one took。

 Then we reset the timer to say your lapse time is now zero， start the timer， do stuff two。

 stop the timer， printed out and。That displays separately how long each of those tasks took。

So with this one， the downside to using timers inside of your program is that it takes a bit of time itself。

So adding these like a constant number of these calls is not a too big of a deal because we're adding a constant amount of overhead。

 things that are not our program accomplishing work。

 but are in fact our program timing itself and you don't want to。Add code like this inside a loop。

 like do stuff one might have multiple loops in it。

 but we're going to do the timer before the loop start， we do the timer after the loop start。

 If we put it inside the loop and keep turning it on and off。

 it would be like taking an exam and going。119 minutes left。119 minutes left， 118 minutes left。

118 minutes left I spend all my time looking at the clock instead of doing work。

 so we want to make sure if we do this inside of a program， we don't want it to do it too often。

 we want to start and stop those timers accounts a number of times。Now。

 we've got a program that we built and I've got in here the。Link and there's a command in units。

 which is on King called W get， it saysGo out on the World wideide Web and get me something from this link and。

Output it to the file name search。cP。 All right， so I got to change my sharing。

 which will probably give us's。It might give us in for recursion or I might be able to just give it over to my。

Sll second。Make sure It help。More than one shell open。Okay， there we go。

 so I've got already logged into Cae and I've already got the command typed in here。

So I sayW get that link at G， capital O capital N V capital C，0 and then output'll put it to search。

cppP and it should if it works and you can try this later yourself or you can pause the video if you're watching from home later and it should say about 3831 bytes it put it in a file name search。

 cP and all of this is all the feedback about how it grabbed it from the web and Google Docs。

 etc so if I do an LS here and a long listing I gave it a long listing so we can see what they are I've got my make file I already put this in place。

 I got that ready ahead of time actually I got it ready last semester。

So I've got this ready and I've got my search。cvP so we can do， hey， let's。Make this program。

 let's do dot slash search and see what it says， Okay， and it says hey。

 you didn't give me a command line so what you're supposed to do is。B or L for the type of search。

 sounds like binary or linear type of search and the number of items that we should be searching。

 Okay， alright， so dot slash search。 let's do a， let's do linear first。 linearar search of。100。

000 items。And okay， that didn't take very long， so it tells me how long it took to fill the vector。

 so that was task1， and then task2 was go search for values and you're going to see it's going to find them about 50% of the time。

Because it's basically it's doing random odd even type stuff， Okay， so that was 100，000。

 How about a million。Okay， so it took about 10 times as long to fill the vector。

 It took over 10 times as long to do the search。 Let's move this up another 0。 There's 10 million。

Okay， so it took about 10 times as long to fill the vector， it took about 10。

 it took like almost 40 times as long to do the search。

So it seems like the fill of vectors seems to be what we'd expect。

 it goes up by a factor of 10 every time， but the searching seems to be going up by more than 10。

 okay， let's try binary searching。Okay， so let's start binary searching back at 100，000。

And it took about the same amount of time， 00，035，0004 to fill it。And it took the searching。

 the very first searching took 0，0，4，6。 This one took 0，0，1，8， so it took a little less time。 Okay。

 let's increase the size by a factor of 10。 Now what we would expect to see if the size goes up by 10。

 remember， binary search is a log。Time， so we would expect it to go up in factor。

 So if I increase it， if I doubled it， I would expect it。Not to take twice as long。

 I expect to take a little bit longer。 if I go by a factor of。10。

I would expect it to take about log base  two of 10， I to take about three times longer。So。

If I do that it。Didn't take。Three times longer it took out。う。Six times longer。

AllLet's go by another factor of 10。Now， wait a minute， that searching took。3。485 linear took 3。8。

 okay， there's a problem in the code and the code if you look at it even says there's bugs in here。

Edit the search do CPP。 And oops， let's go back to the top。 Okay。

 and Professor Jewtt wrote this back when we taught together in the spring semester when Professor Gar was off first semester。

 because his wife had their child。 So let's see， let's see what's in here。

 So this is the time or class。 So this is just copied from the slides。 This is fine。

 Let's go to the end of the timer class。 Okay， says performs a straightforward linear search through the input factor for the given value should theoretically have all and complexity。

 note this code contains an intentional bug。 Okay， so there's a bug in linear search。Okay。

 so linear search says you give me a vector。And a value， I will loop through the vector。

 look at everything in the vector， if I find the value I'm looking for。

 I will immediately return I as an integer because I here， because I was doing a vector dot size。

 I don't want the compiler to complain about like if I make this an int。For I。

 it'll complain about me comparing a signed integer to an unsigned integer。

 So instead I just made it a size T for looping for using as an index。

 but then when I need it as an integer to return it。

 I static cast it and then if we ever get out of the loop so if I look through the entire vector。

 I return a negative one to say I didn't find okay so it says there's a bug in here。

 let's look at the binary search。Okay binaryary search also says there's a bug in here。Okay。

 same thing， you give me a vector and a value， oh， I will figure out the inclusive beginning。

 the inclusive ending， and as long as high is greater than or equal low。

 this is basically the code from the slides from a day or two ago。So if it's。The middle point。

 if the value at the middle。Is the one I'm looking for， return the index， otherwise， if it's less。

 move the high end， else move the low end。All right， not's some binary search。

 but why is it doing so badly？The problem is not inside the function， the problem is the parameters。

We're passing this vector by value， so it doesn't matter that we're doing a binary search。

 It takes O of n time just to reach this line of code before we even start running the binary search。

 Alright， so let's put an ampersand in there。 Let's say， hey， let's pass that by reference。

 Let's go check the linear search。 Oh yeah， that one， too。 let's put an ampersand in there。

 We'll save it。 We'll make。And we've got a compiler error it says okay， we got a binding problem。

 I'm trying to bind a constant vector events。To a reference vector。 And the problem is in line 102。

 when I call binary search。 Okay， let's go to line 102。

Let's turn the line numbers on so we can see it。Okay， so we go to line 102。

 this is in the test search function， says， hey， when you call binary search。

You made a promise up here。 This vector was passed by reference， and you promise not to modify it。

 Now， what many students would say is， oh， yeah， we got to get rid of this con here， Ra。

Our problem is not that we need less cons， we need more cons。

So this function has already made a promise。 I'm going to test searching。

 and I will look at your vector by reference， but I won't change it because I'm just searching。

So what we need to do is we need to go back up to our binary search and linear search。

 and instead of a reference， these should make the same promise， it is a con reference。

I will look at your original copy of the actor， but I promise I won't change it。

So our problem is not that we need less con， we need more con。

And this is something that students often do is that when they run into problems with cont。

 they want to take the cont out， but a better choice is more cont， usually if you need to modify it。

 then yeah， you've got to pass it by reference。But if you。Don't need to modify it。

 it should either be if it's small， like an integer or a boolean or something like that it should be passed by value。

 but if it's large and you don't need to modify it， it should be a cos reference。Okay。

 so let's save that， make again， there we go。 so that works。 So now let's go back do search linear。

 let's try。Let's start at a million， and I'm just going to clear the screen here。Well。

 it's a new starting point， okay， so there's a million and here's 10 million and it took。

 we can see it took about 10 times longer to fill the array and it took a little bit more than 10 times longer to search it。

Okay， what about if we move up again？Okay， again， the time to fill it is about 10 times bigger and we got about。

 oh not quite 10 times longer， so it looks like that one is a little bit of an aberration。

 these times are being reported to us by the operating system。It changes a little bit。

 there could be other people on the server here。Now。It says now this。

 this is funny cane lies to you when you do the W command to say who's on the machine。

 it lies about who's on it， I know it's lying because it doesn't show me。

But we can see the load averages， this is the most recent one minute interval load average。

 so if this was higher I would say yeah， I should expect a little bit more variability。

 but I'm not seeing a big workload there so I should get reasonably consistent results。

But we saw about a factor of 10 in the linear search All right， let's try binary search now。Okay。

 let's start the same thing， binary search of a million， and it took about the same time to fill it 。

004。But the time to search it， it was so small， it had to go down to scientific notation。Okay。

 let's add， okay instead of million，10 million。 Okay， we're out of scientific notation 。00017。

 which is even faster than 10 times less elements。With a linear search。

So this does look let's go bigger。 so there's 100 million。 Okay， so see how we're going up in time。

 it went from 0。00017 to 0。00025。So we got 10 times bigger。

 but it didn't even take twice as long to search it， let's go bigger。Eventually this might fail。

 we're probably going to run out of memory at some point。Okay， so that worked， so again。

 it it took about 20 times longer to fill it， but not that much longer to do the searching。

And I think if we go any bigger than that， if we try to go 10 billion， I think that's 10 billion，1，2。

3， or a6，78。yeah， so we're up to 10 billion， this should probably crash because it shouldn't be able to fill it an array that big or vector。

Probably is not going to get us 10 gigabytes I it'd be 40 gigabytes worth of integers。

 and it would take 60 seconds just to fill it anyway， it's probably going to die， yep， seg fault。

Okay， so that's that's that test， so we saw that the binary search is really a binary search now and we saw a way to test it from inside of the code now got changed back to my。

Nope shit here， there we go。All right， so that's， I've got a bunch of commands here on how to use it we already did all of that。

 I had the make file in place， so I didn't have to type the G+ plus command by myself。Okay。

 so if I did some plots of some data， not this program， this is just made up plots。

So I might do some made up plots and I test it for size 5， 10， 15， 20， I plot the points， and I say。

 oh yeah， that looks like a line there。But it looks like the problem is I didn't test it with large enough input。

So these four points。Are the same four points right there。But I also added more 25，30，35，40。

 And now we can see this is starting to look more like maybe。And then squared where this looked。

Like maybe linear。So the point here is that you've got to run it with a big enough input to actually see some behavior and see if it does match what you predicted when we ran the search program。

 we didn't get the results we predicted， it was taking way too long to binary search。

So we had to look at what's the problem in the code that we're not getting results like we expected。

And we did go out big enough with like 10 million， 100 million。

 We were going out far enough a big enough size N。 The problem was that there was a bug in the code。

Okay， so what if I run a program and I get experimental results that are worse than I predict？Okay。

 like it says here， results are exponential when the analysis is linear or what we just did。

 the results are looking kind of linear when we expected log。

So there could have been an error or complexity analysis。

 we could have done something wrong with our Big O。

 but hey this was binary search so as long as it really was a binary search。

 it should have been log in in， but it could have been an error encoding。

 we could have an extra loop unintended operations like copying an entire vector when we should have been passing it by count reference。

Okay， what if we get experimental results that are better than what we predicted they should be？

All right， so we get something like say quadratic when we expected linear。

Oh sorry opposite we expected quadratic and we got linear so I expected quadratic， I got linear。

 I got something better than I predicted， well， I may not have had a worst case scenario maybe I did a worst case analysis and I wasn't doing a good job of stuff and so I had not really random behavior maybe I was just you know the dozen times I did the search。

 maybe I was getting something that was。Excuse me， Maybe I was getting something that was。

Not quite random and I was getting lucky in finding what I was looking for near the beginning of the array time or the vector。

So maybe I just happened to not make it random enough and I was searching for you values that were near the beginning every time。

Okay， so I might not hit a worst case scenario， I may have made an error in my complexity analysis。

 so same thing I could have done wrong here， I could have done wrong there。

 I could have had an error in my measurements like maybe I didn't make a big enough M to see that what it was really happening that was in the previous slide。

Maybe I didn't finish implementing it， maybe I got excited about having like output。

 but I forgot to there was one other thing I was supposed to do that was the bulk of the work and so yeah I've got output but it's not done yet I'm not done coding。

So maybe I just didn't finish implementing it。And the last one here is maybe you planned on using。

 let's say bubble sort and then as you were coding it you went hey。

 I've got that merge sort in my folder from last semester。

 let's just go grab that merge sort and all of a sudden you're getting n log n from merge sort instead of the n squared you were expecting from you planned on bubble sort and then halfway through implementation。

 you changed what you decided to do。Okay， what if the experimental data matches our prediction。

 but it's just taking too long to get results？Well， there could be some sort of performance bug。

 we could be you know doing extra operations like， hey。

 I'm passing something by value to a function that's O then anyway。

But that's a big extra constant and I basically doubling the amount of work there。

It could be my compile options， maybe I forgot to use03。

 and if you look back at the earlier in the video， the make file does produce an optimized build by default when we type make。

This is one thing to watch for in Project one if you run on the big inputs and you run inside of your IDE。

If you're running inside of an IDE， most IDEs by default build a debug executable and not a speed optimized executable。

 so be careful with that。And you can look and see like， hey， I'm getting the right。

Complexity class of behavior， but it's just taking too long。Um， you know， like onm the auto grader。

 say all of my tests are either， you know， the really small ones are fine。

 but the big ones are over by a factor of like one and a half。And it's not like the bigger it is。

 the longer it is， it's not like this one's over by one and a half and that one's over by two and a half and that one's over by 10 and a half but they're all over by about one and a half。

 maybe it's just a bunch of constant factors， maybe you just did some small things inefficiently repeatedly and the thing to look for there things like the is digit where you're doing a constant factor more work than you need to。

Look back at the I'm going to say this all the time Can files。

 resources optimization tips document there's a section in there on。

Input and output to make sure you're reading things correctly and using the right files for your operating system。

There's a section on optimizing for memory， optimizing for speed。

 there's another section about reading input and just how to deal with different types of input and there's a section at the end on optimizing exam grades。

 make sure you read the exam grades soon and start doing what it says now to be preparing all through the semester。

Okay， there breaks， there's an example of here from Perf that you are going to use in lab1。

One of the things that people have been doing in lab one is they go straight to the Perf command and they get no samples。

 and that's because they forgot to do the。Module load。GCC 6。2。0。

 and it doesn't even actually run their executable。

So make sure you can always check it with G plus plus minus minus version。

And it'll tell you what version of G plus plus is being。Is active and what it will be executed with。

Perf， the one thing I want to warn you about Perrf is Perf is not good for you to say。

I'm in office hours and here's my perf， tell me to wrong。

I have no idea what your PEf means unless I know how your code is structured。

 and then I've got to look through all of your code。To see the structure。

 and if I'm going to look through all of your code。

That's where I'm going to look I don't care about a per report personally for your code。

 I don't want to see a per report because I don't know your code to know what it means a Perf report is great for you in that like in lab one when you run the performance part of lab one。

 you'll see that like the sorting。It says insertion sort。

 the insertion sort takes a certain percentage of time， and I'm not going to give you the answer。

 but it takes a certain percentage of time。 let's say it's x percent。And you say， wow。

 that's a pretty sizable chunk， maybe I can make it faster if I changed it to merge sort。

And then you implement it and you see instead of like the sort being x percent， it's x over 4%。

That you've reured it by like three quarters of the time less is spent sorting。Hey。

 that's a great improvement。But if you implemented。

 say merge sort and it was still x percent and it didn't change。

 then either you got too small of a task or you didn't really implement merge sort， maybe。

 there's a bug in there that's that's making an n squared time。But it's really good for per。

 really good for。Here's what how long was spent in this task， I improved the code。

 here's how long it spends in this task now， and if percentage wise that drops。

 then you've made an improvement in the code。And if it doesn't drop then。

 you didn't make a significant enough improvement to notice。

 And Perf is no good if the input is really small。 Like Perf with 10 items on this search that we just ran wouldn't tell you anything。

 wouldn't get enough samples to really tell you where the work is where the time is being spent。

 Where if you did it with like。10 million it might take an hour a run。

 so we got to kind of find that happy medium of， you know。

 if it takes like five or 10 seconds to run Perf， then you're probably at the right size file to give you meaningful data。

Now when we're on Linux， we can Linux， Uni， whatever we can run our program。

 We can also there's a time program。 There's user bin time and there's just time。

 They give it the same information in slightly different formats。

 and you would run like here's an example down the bottom I'd run user bin time。

 and then I give my normal command line dot slash， my excutable name， my options， whatever arguments。

 So I just do my normal command line after user bin time and it will give me some data。

 it'll tell me user time system time Elappsse time and a percentage。

 So let's see what those mean Oh wait I've got you another example first I did time instead user bin time I just did time but I did the time command with Dd means disk dump D is a program that copies anything to anything。

 And I said hey your input file is dev0 Dev is the device folder on Uniix Dev0。

An infinite source of zeros， you can read zeros from Dev Ze forever。

And I said your output file is Dev null。 Devv null is referred to as the bit bucket。

 It is an infinite sink。 You can send an infinite amount of information to Devnoll and it will just disappear。

So I said， basically read infinite data， write it to an infinite throw away and let it run。

 and this would have run forever if I hadn't stopped it with control C and have run into this in office hours when I say control C。

 I mean control C， if you're on a Mac， I don't mean command C， I mean control C。

Now if I'm saying copy， I might goof and say copy and say control C。

 but when we're at the Uni prompt， we really do mean control C not command Okay。

 so control C stops this and it says it was about 0。92 seconds of elase time。Of that time 0。

26 was user 0。65 was system， and that's not quite all of it。 We'll talk about that in a minute。

 And the rest of it， like this is the output from the disk dump command。

 and the bold line is the output of the time。So what do those numbers mean？

So user time is time spent by your program， your actual code spent this much time。

 and this also includes things like if you send stuff to。

See out the the time spent in sea out is charged against you， but。

For that output to go somewhere like be redirected to the file， that system time。

 So when your program sends tough stuff to see out， you pay the cost of the sea out code。

 but the time spent getting it from the end of the sea out code to say。

 a hard drive with a greater than it， that system time time spent by the operating system on your behalf。

There's the eappsse time and that's like our kind of like our timer program that we used except it's not in the code。

 it's at the operating system so the eappsse time is basically from the moment that you hit En to start the program running until the program was done that's the eappsse time and we also refer to that as wall time。

The CPU percentage is user plus system。Divided by alapsed。

 and that's not necessarily going to be 100%。 We saw it was 99。The reason is。

From your program's view， it started running。It did work and it finished。But from a real world view。

 what happened was the operating system said， here program， here's a CPU start running。

And a certain amount of time later that's called a quanta。A quant of time later。

 the operating system said， yoike， that's my CP， don't stop using it。

And then it might have made some other things run or it might have just done some bookkeeping and said。

 okay， there's nobody that needs a CPU， okay， you can have this CPU back for one quant yank。My CPU。

 and then it might say， hey， start up again on this different CPU。

And so that is neither user nor system time， it's time that your program is not running is between the yank and the giving back of ACU。

So you can look at time for man time for more information man is a great command。

 man means look it up in the manual。So man time， man LS， man make。

 it gives you information about that command。Okay， Val grind， great program Val grind。

 we're going to go back and and do something to get our Val grind report。

 So what we're going to do is we're going to go back to our program。

 We're going to modify it to force a leak in our code， and then we're going to run the。😊，Valgri on。

So let's go back to our shell， okay， so I want to addtic。

Memory leak to here what I'm going to do is I'm going to replace my return zero。With exit at zero。

Okay， so do that， we do a make I'm going make call because I want a debug executable。

 so now Valalgrind do/lashsearch underscore debug， we want to do let's say a binary search of  a thousand。

 I don't want it to take super long because debug executable takes longer running it with Val grind takes longer because。

It's not actually running with Valalgrind Valalgrind simulates the execution of your program and watches everything it does Okay。

 so to try that， let's see what it says。Okay， so we've got anything that starts with this equal equal number equal equal is the Val grind output。

 This is what's called your process ID number。 It's the number that is associated with the run program So it says here's the Val grind output。

 here's your output and then here's some more Valal grind output。

 Oh in you said exit 4000 bytes in one blocks of memory。 there were some some things allocated。

 some things freed， okay， and it says rerun it with leak check equals full to see the details。

 Okay I'm just going to up arrow I don't like retype in commands。

 I'll arrow back here and then what I'm going do is I'm just going copy this leak check equals full is an option that I'm going to pass to Val grind I need to space it there So it says Val grind you run with this flag and then here's the command line I want you to simulate。

O。So we've got more output， leak check， definitely lost， indirectly lost， possibly lost。

 and still reachable。Now still reachable is a little bit better than like definitely loss。

 but it's still a memory league。Okay， so we got to add another flag， show leak kinds equals all。

Arrow back here and we'll put this flag in there， shall kinds equals all。Copy paste。

 put space in there。Okay， let's try that again。here we go。Now we've got， it says so this is。

 so here's an error， here's a loss record。And it says， here's a loss record and here is。

 this is basically this is the call stack。So what we want to do is we want to look in the call stack from bottom to top。

 so this is my code search。cP line 128 of mainine。And then it went into the vector TCC。

 that's an include file I don't want to look there。

 I look upward until I get to the highest line number that's mine。

Now there's one thing we could have done the I forgot to do it wrong。

 what if we did this without a debug executable？If I do without a debug executable， all it gives me。

Is a memory address。And a memory address does not tell me what happened。

 That's why we want to use make all and run it with our debug executable。

 So the debug executable instead of a memory address。

 it will give me a memory address and a line number。 Okay， so it says search do CPP line 128。

 fliping my code line 1 28。 Oh， that's the line that。Did the reserve。Okay， so it can't tell you。

Which line should？Have cleaned up after it， but it tells you which line did the allocation that never got delocated。

So the real problem here is the exit。You don't want a program to exit zero to exit anything if it could instead have main returnturn zero or returnturn one。

Exit says stop this program right now。And deors don't run。

 memory doesn't get cleaned up and we leak memory So now if we go down here and let's change this back。

To return 0。那 go。And we'll just rerun the Val grind command the most recent one。And it says， hey。

 all heat blocks were freed， no leaks are possible， you're asking me for for leak data。

 but I've got nothing to give you。So there were things allocated and freed。

 but everything was given back eventually in USA at exit， there was nothing in use。Okay。

 so that's a little bit more about Valgra。So。Learn to use Valbriine， learn to look at its output。

 Let me see if I can add。I'm adding a bug in here。O。I change windows here。

 I was just seeing if I could get。I think this is going to be a problem。Oh， actually。

 let's do G3 and search underscore Depot。And here's another command。

Exclamation point saysReat the last command that started with Valgriide。Okay， that one didn't。

That one didn't die the way I thought it would。 Okay， I was trying to make a different error there。

 I'll have to think about that for the future， sorry， I was trying to make up an error on the fly。



![](img/6e3a28ec7416e19204f8c3ad5b4ee11a_1.png)

But there's other things that Valgriin can do， it can tell you about unititialized values if it says something like conditional jump or move depends on unititialized value。

 it means you're looking at a variable that you never initialized and that's bad。

 and it can tell you that。Okay， run time analysis tool。Job question here。

 So interview question someone says， hey， I want you to do this。

 I want you to write a power function that returns x to the n power and we're not going to make it super hard。

 we're not going to do like you know 3。87 to the 0。

13 power we're just going to make it the power the exponent must be an unsigned integer So the exponent has to be an unsigned integer and the x has to be an integer。

So we could easily write this with either n or n minus1 multiplications。

Less obvious would be let's get it done with logged multiplications。And we could write this solution。

 we could write the obvious solution either iteratively using loops or recursively。

 we could write the multiplication， the log in multiplications。

 I find that one's easier to do recursively so we're going to look at some of these today。

 so here's a really straightforward one。So we say if the n is equal to0， just return one。Otherwise。

 set the result equal to x and then do M-1。Mulipplications。

 so I started out with x and then I multiply it inops I lean down way。Tablet there， so we did。

 we started out with X， we multiply it by itself。N-1 times。And times x。

 and then we end up with x to the n power， so that's a straightforward O of M implementation。Really。

 we could say it's big theta of n because there's no difference between best， worst， et cetera。

 so we've got a big theta of n。And。Here's an iterative one。

 here's a slightly different iterative one instead of x and n minus1， I started out with one。

 and I multiply it。N times。 So I do n multiplications。 And if n was 0， the loop doesn't run。

 And I just return one for the result。 So this is still big theta of n。

But it doesn't need a special if or if n is zero， it just uses the result starts out at one。

And that's a little bit easier to see how the recursive one works， the recursive one work says， hey。

 if I'm going to be recursive， I got to have a base case。If n is0， return1， I'm done。

 otherwise return x times recursive call same x。But decrement the power of n by one。

 And as soon as that。Power function is done， we do the multiplication we return。

Now this one's a little bit harder to see the complexity。One thing about this is it is recursive。

 is it。Taale recursive。Well， the last thing it does is recursive call and return。

After the recursive call， there's a pending multiplication。 So this is not tail recursive。

 It is recursive， but it's not tail recursive。 Now， we need a tool。To do that one。

 we need tool called a recurrennce relation， like I said， we're going to get to that soon。

So recursive recurrence relations， so I can write a recurrence relationship for a computation。

 like I can say， hey， here's how you calculate x to the n of power。

 it's one when n is equal equals 0 or it's x times x to the n minus1 when n is greater than0。

I can also use a recurrence relationship to。Represent the time taken。

So the time taken is a constant amount of time。 C0 is a constant some constant amount of time when m is equal equal 0 and。

Time T of n -1。 That's basically saying the time to compute N is the time to compute a smaller N plus。

Some constant amount of time。So if we look back at this code。In this code， where is C0？

It looks like this， he， it looks like that's C0， that's the base case。So when n is equal equal to 0。

 that's the base case， that's what's got to run and when n is not equal to zero。

I have some constant amount of work C1， So this is right here， this is T of n minus1。Well。

 sort of before I can do that recursive call， I've got to do a subtraction。

 that subtractions part of C1。The multiplication is part of C1。 The return is part of C1。And really。

 this if， this if is also part of C1。So C1 comprises all the things except for the actual time spent in the recursive call。

Now we could also use a recurrence relationship to represent memory。

I really don't often see a need for that。 Usually we can do that by observation or by the fact that we've got when we've got recursion。

 how much memory do we need for the recursion we need the stack frames。If it's not tail recursive。

If it's tail recursive， there's one stack frame， if it's not tail recursive there is。

 whatever the depth of recursion is， that's how many stack frames。O。

So what do we do to solve this recurrence relationship， Allright， so we can start out。

 we can write out t of n， and then we can write it out in terms of t of n minus1 t of n 2， etter。

 and we can substitute in to this equation。So we want to substitute in and get a pattern and write a summation formula that doesn't involve recursion。

And we're going to do an example in just a minute there's another way to do it is the master method or the master theorem。

 there's also something called the recursion tree method which I don't I've never really used I generally I would use the master theorem when it's applicable and I would use substitution when it's not and master theorem is going to be next lecture like five。

Okay， so solving a recurrennce relationship， so here's our recurrence relationship and here's our code。

 so how do we solve this？Okay， so here's an example for a linear recurrence。

 Why is it linear well because it goes down by n minus1。If it went to n divided by two。

 then it wouldn't be linear to be hopefully logarithmic we'd have to do the math。All right。

 so let's do an example with this one。So what I'm going to do is I'm going to ignore the base case。

 I just want to worry about the recursive portion of it。 So T of M。Is equal to T of n -1。Plus。s我。

Now what I want to do is I want to get rid of that T of n minus1 on the right。To do that。

 I've got to use this equation。 So let's write down over on the right here。

 Let's write a equation with a different variable。 I can say T of x is equal to t of x -1 plus C1。

 So now what I want to do is I want to substitute using this equation。

I want to use this equation to substitute for that。And in this case， what is in parentheses？X。

 what is x， x is n minus1？So if this was t of x， T of x is n minus1。Is equal to T of。

N minus1 minus1 plus C1。All right， so that's what we're going to substitute in for t of n minus1。

 So this is equal to T of。N-1-1 is t of n-2。Plus C1， and I'm going to change colors。

 I think that's purple。 I go back to red for the original。C one。

So I substituted in and T of n minus1。Was substituted into the T of x formula。

And minus1 replaces x everywhere in that formula。So I've got t of n minus2 plus c1 plus the original C1。

Well the problem is I've still got a t of n minus1 in here。

 so I want to substitute in for this T of I've still got a T of n minus something。

 I want to substitute in for t of n minus2。So I use the same thing over here where act。

Is equal to and minus2。So that's going to be t of， so n minus2 goes in place of x。

N -2 the one right there。 This was already there。 So that's T of n-2-1 is T of n -3。Plus， C1。Plus。

 the purple see you on。Plus the original red C you want。Now we're starting to see a pattern here。

Here's where we want to。Skip ahead because I can't do this。

 I can't write this down M times because remember， M is arbitrarily large。

So if end's arbitrary large， I've got to make a leap of faith here。I've got to say， hey。

 if I keep doing this enough times。I've got to get down to a point where I can say it's equal to T of what？

O T of zero would be a base case， so if I do this enough times。I'm going to get down to T of zero。

Now。When I started out with n minus-1。Or actually， let me undo this one second。

 Let's make this a little bit clear。 If I do this enough times， I should end up at T of M minus M。

 I think I will make it a little bit clear。 So I would have T of n minus M。

Plus C1 plus C1 plus da plus Cワ。Now， how many C ones am I going to have？Well， when I subtracted1。

 I had1 C1。 When I subtracted2， I had two of them。 when I subtracted3， I had three of them。

 and when I subtract n。Oops， stop too soon when I subtracted N， I had N of them。Okay。

 so this is equal to t of0。Plus。C1 times M。Oh， wait。 But t of 0， I already know what t of 0 is。

 T of 0 is my base case。 So it's equal to C 0 plus C 1 times M。

 which is equal to C 1 times N plus C 0。Just rearrange it。And that tells me。Big sta。Of them。

 because I can ignore the lower order term。 I can cross out the。

Constant factor on the highest order term， and I'm left with big theta then。

So there's how we solve that recurrence relationship and we're going to be doing more like this。

 you can go back to the video and watch it again， you can come to office hours and ask questions。

 it's probably a little bit of a hard one to answer everything you can think of in the chat window because we can't quite draw it out but it's a good one you know if you can get it answered now great but if you can't。

Rewatch the video， come to office hours with more questions。But we're going to do more after this。

 Oh whoops， I got the recurrence relationship， sorry。

 I wrote the recurrence relationship in there and the complexity big theta then forgot I was writing over the top of it。

 Okay， here's another one。 here's a logarithmic。So let's solve another one， right。

 we want practice doing these。Okay， so when we。Solve this one again。

 we want to worry about the recursive portion。 Okay， so I've got let oops。

 chain back to my original color scheme。 Allright， so T of M。Is equal to T of n over2。Plus， see what。

Now， I've still got a T of n minus2。Or sorry， T of n divide by2 on the right。

 I want to substitute in for that。 but remember T of x。Is equal to t of x divided by 2 plus c1。

So I want to substitute in。And over two in place of x。So that gives me。That's equal to T of。Well。

 n divided by 2。Dived by 2 again would be T of n。Divided by4。Do we have。Okay。

 I haven't been paying attention to chat， but I don't recognize I shouldn't have been doing this。

 I assumed that we had someone here。Helping out on the chat window and I don't。

It's hard to I've got so many staff members now I get 37 staff members。

 and I don't remember everybody's name。But， I don't see。

Any you want in there that I recognize aha okay， sorry I didn't notice that earlier。

 I'm going to send out the bat signal。Sorry， sorry， I didn't notice that earlier。

 I just assumed that someone on faculty or someone on staff was with it while I was lecturing。Okay。

 so hopefully someone will show up soon and sorry about that。O。

So I'm going to work on the solution here because if I try to answer every question that hasn't been answered yet。

 we'll spend forever trying to catch up there and we won't get done today。Okay。

 so we've got n over4 plus。A purpleur see you on。Plus。An original Red Sea one。Well， we should。

 but that's next lecture， we haven't had the master theorem yet。

So we got to do substitution what we got today and it's also extra practice。Okay。

 I've still got an T of n ish on the right。 I've still got T of n in terms of T of n。

 So I want to substitute in for this n over4 into the equation。

 So I get T of n over4 divided by two is T of n over 8。Plus， C1。Plus， a purple see you on。

Plus the original red C1。Well， if I do this enough， let's assume that。N was exactly a power of two。

If n was exactly a power of 2， I would get down to T of n divided by n。

 and then I would get from t of n divided by n， which is t of 1。

 then I would get to if I divide by2 again， I'd get down to c of 0。So if I do this enough times。

I'm going to get down to t of zero。And then I'm going to have a bunch of CUs。

Now how many of those are there， well， how many times did it take me to get down to t of zero？

It took me。About log n times。 And again， this would be a little bit off if it was a if it was an exactly a power of two。

 if it wasn't exactly a power of two。 So if it was 16， we'd divide by 2， we'd get 8， so we'd do 16，8。

4，2，1， and we'd get to 0。 that's basically。There's going to be about log of M of these。

So this is equal to c0 plus。C1 times log n。Gives us。Big theta of log gap。

So we're eventually down to the point。How did we get to T 0？ So we remember， eventually。

 if I do this， I would get to T of。N over M plus a bunch of C ones。

And then if I divide by n again sorry if I divide by 2 again， see if I divide that by 2。

 I'd have T of n divide by2 n plus a bunch of C ones。

And t of n divided by 2 m is t of0 because into your arithmetic。So I sort it。

 sorry if I skipped ahead there a little bit too much。 So eventually we'll get to t of n divide by n。

 And if we divide once more， we'll get to t of 0。It's how many times did this have to happen？

Let's say that's K。I have to do that k times what is k？Well。To get from n down to0。If I say， hey。

 if 2 to the K is equal to n， then K is equal to the log base 2 of M。So if I'm dividing， I should be。

Cutting it in half every time we should be getting a long behavior。Okay。

 and then I've got the recurrence relationship over the top of that and the complexity you came up with。

Now， if we look at。This logarithmic recurrence relationship。Let's say we had a log version of power。

So if I had a log。Version of power。Then we would have， or if we had binary search。

 we divide it by two every time it's the same recurrence relation。

 If we have the same recurrence relationship。Then we've got to have the same big theta。

So if we start with the same recurrence， we'd solve it the same， we'd get the same recurrent。

 we'd get the same complexity class。So as we look at other things。

 whenever we see this T of n divided by2， we'll get a long behavior。

And I think I come up in another slide or two。O。Now， what if I had something like I split it in half？

here， so if I split it in half。Os， split in half and I recursed twice。All I recursing to both。

So if I split something in half and recurse into both， I would expect to see。Something like。

 what's similar to this， what algorithm is similar to this。

 something like an in order traversal of a binary tree。If I have a binary tree I。

Print out what I've got。Or actually， in order would be I recur into the left。

 I print what I have here。 I recurse into the right。 I should see about。我问。Or big data that。

So if I split it in half and I recur into both halves， I should see about。In operations。

 what if I split it into three pieces？Okay， if I split into three pieces and I recurse into one。Oops。

 that's a terrible sea。So if I recurse into one。Or I recurse into two， or I recurse into all three。

So I should see some sort of。 So if this one should be。Big theta M。This 1。

 I should expect to see some big theta of log base 3 of n。And then this one。

 we'd have to go solve it。So I can， I can see this one pretty easily I。

 if I break into three and I visit all three， I've got to get them， but。

If we've got other equations like this， this is where we want to get the master theorem that we're going to do next time。

So it makes it a lot easier to solve these than writing out the whole equation every time。Whoops， oh。

 I didn't realize I forgot this was an animated slide。Sir。Ettera， so that was already in there。

What if there was non constant work after recursion， What if I had something like。

T of n is equal to t of n over 2 plus M， something like that。

Then I'd have to solve the equation again。There's another one here as an example that is recursive and is not very efficient。

 We're going to come back to this one at the end of the semester。

 so you don't have to worry about this one now。 It's just showing you another thing that we could do with factorials and choose K。

 et cetera， but we're going to come back to this one in the last。

Couple lectures when we talk about algorithm families， etc。Okay， when we look at， whoops， sorry。

 that is the end， okay。

![](img/6e3a28ec7416e19204f8c3ad5b4ee11a_3.png)

I thought I thought there was like one more slide after that one。 Okay， so we're at the end here。

 we actually got done a bit early today。So I can do， since we've got a little bit of time。

 I can take a look at some of the questions。And we can look at some of the。

Other things like doing another example。How do you use G++ without paying。

 well that depends on your operating system。If you've got windows， I would install。

 I would install the WSL， or you， you can also find it as like the。Uubuntu shell。For Windows。

So that's what I would use is get the Uuntu shell for windows。

We've got a bit of time here so we may as well answer a few questions。

 so without Kane I would get the Uuntu shelf windows if you're on a Mac， you just open a terminal。

Yep， on a Mac， you just use the terminal。So the terminal app opens up a terminal and then you should。

 by default， it should be installed。Okay， well， then I don't have a Mac。

 Professor Darin would be a better person to answer that。I don't know the。哦。Module command， oh。

 you don't need module on Mac， you don't need the module command on a Mac。So yeah， B install。

 that's the one I can't think of it。Brew installed G plus+ should get you the G plus+。

 just do G plus plus minus minus version。And as long， as long as it's。5。1 or better， you're fine。

So as long as your G++ version is 5。1 or better， you'll be fine， and also yeah E280。

org has more stuff like kind of since we impose 280 as a prere。

 we expect people in 281 to have that stuff already done most of the time。But yeah。

 you don't have to worry about the module command as long as you've got version 5。1 or better。

 you're all set。But you just don't need the module command。I would Adam， I'd say use our make file。

If you use our make file， you'll be ready to run in your terminal。

 you'll be ready to submit to the auto grader， you'll be ready to create the tar ball this full submitmit。

t。gZ。If your make file doesn't have sync to cane， Oliver get the latest one。So if you go to。Just。不し。

I'm going to grab the link here。So I don't miss sayy it。Okay， I'll just put it in the chat here。

So there's our latest version of our， there's a link to our latest version of our make file on Git。

So if you just go grab the latest version， it's there。Another thing you can do。

 which I don't think it's the best choice， but it can work is if you just go to Uish。

 eduu and search。For M file。Search for M fileile is a web interface for dropping files onto the server。

So you can drop files onto。Like Cae with that。It's not perfect because the ownership is a little messed up and the Unix to Dos command won't work properly。

 but I would， I would use the。I would just use the latest make file and use the sync to cane in there。

You can also remember if you're on Canne。Like if you're already in uncane。

 you can say like get clone。And then like a st on that like you can do a git clone to grab the lab one code。

You can just go to a phylon cane and do gi clone。The link that's in the lab right up。Yeah。

 for the time analysis to Hill， that's I did that with someone in office hours where they just did a get clone on cane and grabbed the entire lab one repository。

Oh okay， Adam， which make target should you use for working on speed and memory。

 that's just make when you do make all you want to use the one with no underscore。

 like it would be Super Marco， not Superco underscore debug， not superco underscore profile。

 just the one that's super Marco。Oh we forgot to delete that part of the spec， Aden。

 Professor Noble thought that the scoreboard made some people like either too depressed or too competitive。

 so we disabled the scoreboard and we forgot to remove that from we forgot to remove that from the spec。

Well， then hello， I would say start now。So you， I would target like I would try to get done like a couple days early。

 like even a week early so that you would still have like。

You still are like on the order of two weeksishh， two weeks minus two days。

 so you've still got about 12 days left。But look at the also not just the lab one slides。

 it's in the Project one tutorial video has a breakdown of what pieces to work on in what order and start getting those done and so to get you want to get to the point where you're stuck quickly。

So the command line options。You should be able to get if you've done project zero。

 the command line options shouldn't be too hard， maybe one or two questions， reading the input。

 you should be able to get one of the input modes read with maybe a question about the comments。

And then you'll get into the searching and implementing the searching and the implementing output。

 and go back to the video， it'll help a lot。Get some questions answered in office hours and office hours。

And make progress， make some progress every day。If you make some progress every day。

 you should be able to get it done on time。Yeah， I never use pairs or tuples unless I have to。

I generally use structures and classes。I would say， yeah， like two。

 three hours a day for like two hours a day for 10 days， for most people that might be enough。

 it's really hard to say I don't know how your programming skills stack up against other people。

 but it's definitely going to take more time than your 280 projects did。

I'm not going to do demos of like hey， let's run mine and let's run yours I want to answer questions that get people working if you're getting the points on the auto grader。

 then you're doing fine。It doesn't matter， Frankie。

 you can either make it because you've got to put something in the deck that is a room row column。

 The start location could be one variable of that type that goes in the deck or the start location could be three variables。

 It doesn't matter much。It might be easier if they were the same。

 like if the start was the same type as what goes in the deck， before you start the loop。

 you could say hey， deck， push， start location， one line of code instead of having to make a structure that contains the three separate variables and then push it。

So in price save a little bit of time if you did it with。A location goes in the deck。

 the start location is a location。Yeah， planning is good。

 so do some planning come to Pro hours Pro hours has a one on many meat and I'm going to go I'm going to grab the link for that right now so I can remind you of it。

Oh wait， no I'm not going to put that link in here， sorry。

 I'm not going to put that link in here because then it'll be public and then people from all over the world will grab our public meat。

 but if you look at，If you look at the Google Calendar。

 the Google Calendar Pro hours has the link for our public meetet for Pro hours， so come to that one。

So the Pro hours public Meet， the Google Meet there， we answer one on many questions。And also。

 when you come to the Pro hours one on many meet， be logged on to U of M。

I've had two people now tell me they couldn't get onto the one on many meet because they weren't on their UMi and we never got a notification saying someone wants entry。

It's supposed to give a pop up to ask if we want to admit them and it hasn't been doing that。

 so make sure you're on your U account when you go to the Pro hours meet。Yeah， Pa in28。

 I thought that was a typo shift。Well， Frankie， part of it is too many member variables is not a big deal。

 Frankie。If I've got two variables or seven， I don't care for memory。

 what I care about is the thing that I put in a data structure that grows。Like my 3D vector。

 if I put 10 things in the 3D vector and the 3D vector is rooms time size， time size。

 that's going to be a problem。But whether my。3D vector has like。Two bytes versus three bytes。

 it doesn't matter。So don't worry about three variables versus five variables in a class。

 that's not a big deal， worry about three variables versus five variables in a data structure that there's millions of。

Like the what goes in the 3D vector， the size of that is important。What goes in the deck。

 the size of that is important。But the stuff that you have only one of。

 I don't care if you have five of them or seven of them， not a big deal when there's five or seven。

 it's when there's five or seven times m that we worry about it。And also Frankie， the other thing。

 look at the Canvas files resources optimization tips。

 the optimization tips document has a section about memory and also watch the video in the video I told you like what types of variables are going to be useful for the different data structures in Project1。

Okay， seems like the comments have kind or questions have kind of slowed down here。

 I'm going to end the video。Get a catfed and head over to Pross in a few minutes。

 I'll see people there。