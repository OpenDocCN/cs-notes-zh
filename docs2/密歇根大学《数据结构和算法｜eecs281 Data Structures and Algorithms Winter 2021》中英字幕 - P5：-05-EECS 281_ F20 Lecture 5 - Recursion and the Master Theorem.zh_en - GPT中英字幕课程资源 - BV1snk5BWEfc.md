# 密歇根大学《数据结构和算法｜eecs281 Data Structures and Algorithms Winter 2021》中英字幕 - P5：-05-EECS 281_ F20 Lecture 5 - Recursion and the Master Theorem.zh_en - GPT中英字幕课程资源 - BV1snk5BWEfc

🤧嗯。Okay， sorry， I was almost a minute late there。 I got my slides。

 just the play button was completely missing on my slides and now。

It doesn't even have my inset for doing things。Okay， there we go， all right， I think I'm all set now。

 sorry about that。Okay， so before we get started today， just a few reminders so one。

 the project is due a week from today。Second reminder， when you come to Pro hours。

 it'll say PR Pro hours means professors are there。Go to the link on the calendar first。

The queue is for individual questions that we cannot answer in a one on many meeting The link on the calendar is a one on many meet I saw people yesterday。

 they sat in the queue for two， two and a half hours。

Only for me to answer three questions that they could have gotten answered two and a half hours before。

 if they had just come to the one on many Google Meet。

So please start there unless you know for a fact that it has to be a one on one things like my code won't compile Okay。

 well I've got to look at that code and I'm not going to have you share that with a big room full of students but when we've got 16 students in a one on many meet we can get a lot of questions answered。

 In fact， theres some people show up who never ask a question because。

Everything that they wanted to ask got asked and answered by when someone else had the question。

So you'll find in the one on many meat， you'll learn a lot that you may not have even realized you didn't quite understand yet until we talk about it。

 do an example， etc， so take advantage of those。Also check out post number or now I should look this up ahead of time。

 what's my post number。At 476。And we are。Pazza so look at post476 on piazza and it's got some tips on there I put a few in。

 I added one or two more， including how to read the autograder feedback when you click on the timestamp what to look for in there to look for things like the word hempt There are hints that the autograder will give you that we've put in there for specific test cases that we know why they are tricky so we know why you might get it wrong it's not the only reason but it's the most likely reason for that one and so check out those hints。

Okay， so today we're going to talk about recursion。And so you should remember from 280。

 recursive function is one that calls itself。And so when we're doing this。

We've got to have at least one base case， because if we don't， then the function has no way to end。

We've got to have at least one recursive case for it to be recursive， right。

 it could have more than one recursive case。Now， every time we make a call。So these up to this point。

 these are a requirement。Now it says each subsequent call has a simpler， smaller input。

 that's almost always true。It's， I can't think of a case where I've got a problem of size n。

 and therefore I solve the sub problemblem of the same size。

So this is not strictly required for every call， but at least some of the calls have to get smaller。

嗯。Oh， I can think of one the what is it the n over two if it's even and3 n plus one。

 if it's odd that mathematical problem， the and you give it a number and you want to know does it converge to one does it go down to one eventually And so far every number anyone has ever tried eventually becomes one but proving that that is a tough one to prove So there is a case where we could write it with recursion。

 sometimes it gets bigger sometimes it get smaller and we want to know does it。

Reach the base case of the value one。So generally， when we're writing a program to solve problems。

 generally it's smaller for each subsequent call single recursion， just for an example。

 these are not the only things it can solve， but single recursion。

 meaning there's one recursive call can be used on things like linked lists。

 multiple recursion where we've got multiple calls that get made one after another could be used on a tree on a binary tree。

So we had this question before of calculating x to the m power， we definitely want to stick with。

Non negative integer exponents to make it simpler and the integer base x isn't critical it just we just had to pick a type there。

So we could do this with n minus1 multiplications， we could do if n multiplications won't be even better as if we did it with a log n multiplications。

Okay， so here's our。Different recursive definitions。

 So here's our recursive definition if we want the end result to be big theta of n。

 we already did this one previously。If we wanted it to be log behavior。

 we've got to split it in half。So， we've got to。Calculate x to the n over two power。

 So if I want to calculate， say， x to the10th power， well I can calculate x to the fifth。

And I'm not going to in this one， we're not going to call it twice， we're going to call it once。

 and then we're going to multiply it by itself。And that works if n is even when M is odd。

 we do the same thing， and then we multiply by x。 So this gives us a recursive approach。 Now。

 it's important， like I said， we don't want to call the recursive call twice。

 We don't want to call this and call this。 We want to call it once。

 Take the value and then take that like temporary value and then take temp times temp。

Or temp time temp。Times x， if we're doing the odd one。

So that's critical that we only want to call at once because there are identical parameters。

 the results should be the same。Okay， so here's a solution。

 so we've got our on the left we've got our recursive solution that is linear on the right we've got our recurrence relationship that is。

 we would hope log， but we need to solve this。Now we've got a little bit of a difference here in that we've got。

 we've got two different cases， we've got， well， what is the complexity when N is odd。

 what is the complexity when n is even？You say， well， that's a different amount of work。Well。

 only slightly， it's a constant amount of work more when it's odd。

 there's just an extra multiplication。So we can just put that into the constant， and we say， oh。

 the constant is big enough to handle either the even case or the odd case。

 the constant takes care of the multiplication or the constant takes care of two multiplications。

It's a constant amount of work。So if we want to write a recurrence relationship for this。

 we get t of n equals t of n over 2 plus some constant amount of work。

 and we left off the base case on these because you know we know it's recursive。

 we know it's got a base case， the base case is always constant。

 so we just didn't write it down to save a little bit of space。Okay， so tail recursion。

 So before we get tail recursion， we want to go to basic recursion。 So when a function is called。

 it gets a stack frame on the call stack。And the stack frame stores local variables。

 It stores parameters。 It stores a bunch of things。 And if we have a recursive function。

 then a stack frame gets generated for each recursive call。 Now， if a function is tail recursive。

 tail recursive meaning， there's nothing pending after the recursive call。

 So as soon as the recursive call is done， I am done。

So the compilers are written to take advantage of this to make things more efficient。

So the compilers notice when a function is tail recursive and what they do is they generate code that reuses the current stack frame instead of creating a new one。

And so it's the compiler that makes tail recursion more efficient in terms of executable code and tail recursion and iteration are equivalent in that。

If one is solution exists， the other solution exists， it may be easier to see one than the other。

 and as you get more comfortable with recursion， you might see the tail recursive solution more readily。

And when you're not used to it， it's not the obvious one， you go straight for the iteration。

 but if you can do it with iteration， you could do it with tail recursion and vice versa。Okay。

 so if we had this。Main function here and a factorial。 and we make some recursive calls。

 What happens is， well， main。Goes on the call stack。

So mainine goes out on the call stack and then we want to know， is this function tail recursive？

So before the recursion， we check the base case， we do the subtraction。

But after the recursive the call is done， we've got multiplication to do。 So it's not tail recursive。

 So when I call factorial of5， I'm just going to write fact of5 to save some writing here。

 fact of 5 goes on the call stack。It says in my base case， no， let's call fact of  four。

Then let's call fact of three。Let's call fact of  two。Let's call fact of one。

And we're still out of base case， we call factorial of zero。And that is a base case。

 So it returns one。 So one gets returned here。 This one's not on the call stack。

 and then we can finish。 We multiply one times1， and we return one to there。Now。

 could we have made a different base case and said， hey， when n is equal to one return one？Sure。

 that would have worked， would have made it just slightly constant and factor， faster faster。

 So we return a one。 We multiply one times 2。 We return a two to there。

 We get that one off the calls stack， multiply  two times 3，6 gets returned to there。

 That one goes off the calls stack。24 gets past to there。

 That one's off1 hundred and 20 gets passed to Maine。 That one's off the call stack。 and then Maine。

 Oh， I suppose Maine should have done a sea out there。 That seems a little silly。 C out。Okay。

 let's see out that so can display it and actually do something useful after it calls the function。

So that's what the call stack looks like along the way and if you run this inside of a debugger visual Studio by default。

 it's in the bottom right， I think Xcode is in the bottom left。

 it displays the call stack and you can see what's on it at each stage and you can look at the variables in the current running version but you can see what is on the call stack from main up to fact of zero。

So the program stack， what goes in there， what goes into these stack frames。

 So when a function call is made， all the local variables of the current function have to be saved。

And the reason is that。The variables that I'm using right now in architecture terms。

 and this is the explanation that you don't need to know for the exam。

 but I keep giving half of an explanation。So， the。For the CPU to run a calculation， the variables。

 the values that it wants to do an operation on， have to be inside of the CPU。

 and they're inside of a CPU in a place called registers。

But the compiler writes a function assuming it can use all of the registers。

 So what we have to do is when I am about to call another function。

 I've got to save my registers onto the stack。Then I can put what I want to pass that function onto the stack。

 and then I can call that function。We transfer control to the function。

 so when that function call is received， meaning when the function starts running， it says， oh。

 I've got to get my function arguments have to come off of the stack。

 where do they go they go into register。And then it starts using the registers for the arguments。

 It uses the registers for any other local variables。 It does its calculations， and it has to then。

Issue a return。 How does it know where to return to？

Because one of the other things that get saved on the call stack is what's called the return address。

So the return address goes on to the stack， Local variables go on to the stack。

 the arguments go on the stack， the ordered could depend slightly on the architecture and and the operating system and the compiler。

 but all of those things have to go on to the stack so then when the function is done it says I would like to return。

Okay， all of the arguments are off the stack。 It's got to put the return value on the stack。

 It's got to get the return address from the stack。 It's got to return to that function。

 So control goes back to the original function。 That original function takes the return value puts it into its。

Register somewhere， it takes all the other local variables。

 puts those in the registers they came from。Takes the return address off the stack and then starts running。

 So all of these things have to happen。At every time a new call stack is used。 but when a。

So if we have six nest calls， there has to be six sets of local variables， six return addresses。

 six sets of arguments on there as the calls get made。

 those all get pushed un poppedpped and pushed them。

So there's six call stacks deep and then as they return start happening。

 those call stacks start getting removed from the stack。Now。We talk about a B call stack。

 really there's more than one call stack if you have a multi threaded program。

But we don't do multi threadreaded programming in 281， that's for other classes to do。

So things like 42 OS 494 game design will make use of it 42 will really tell you the ins and outs of how to make it happen 494 is more like hey we've got a library that does sound and video and graphics and controller input and all that stuff in different threads we just have to know how to make it run in code 42 is more about the details behind it。

So we view it as the call stack， but really there's one per thread if you have more than one thread。

 and this is separate from the heap where news and deletes are in a different area that's the heap。

 the call stack is somewhere else， and the call stack is limited。

It's limited by the operating system and the image created by the compiler and。

The number of nested calls， therefore， is limited， and the number of nested calls depends on how much memory is allocated to the program stack and。

How many things go into each recursive call so how many local variables get saved。

 how many parameters get passed and need to be saved， etc ce。

 so you'll see that like a function that passes one parameter will get be able to do more recursive calls than a function that passes two or three parameters。

And so if you can't control the depth of recursion either because it's buggy and it doesn't reach the base case or just you've got too big of a problem。

 I've got a linked list with 40，000 things and I wrote it all nontail recursedively。

 I could run out of call stack even though there's no real bug。

 it's just that it's not tail recursive and the linked list just happens to be bigger than the call stack will allow。

So in recursive function， we get O of N time and O of n space。

 and the space here is including the stack fs。In the tail recursive。

 we don't change the time complexity， but we change the space complexity。

 The compiler notices that this is being done and it reuses the sac frame。 Now。

 the there's something in here you may not have seen before。

Instead of because it didn't fit in one slide， we could have done the tail recursive version with two functions。

 We could have had a starter function that accepts n and we could call a helper that accepts two parameters。

 The current result and M。 So that's what we're seeing here is M and the current result。

 But you see there's an equals1 there。What this is is it's called a default。Argument。So rest。

 which stands for result here， we are a little bit cramped for space。

 so result is an intermediate result。 What we did was we made the multiplication before the recursive call so that after the recursive call is done。

 we can immediately return。 We've got tail recursion。So to do that。

 we had to pass the result of the multiplication to the function。 So like I said。

 we could have had a base function that accepts n and a helper that accepts n and the intermediate result didn't fit on the slide。

 So we made a。1 function version that accepts two parameters and rest are yes。

 says it defaults to one。 So what happens is if I call the bottom version， if I call。Factorial。

Of five。What the compiler does is it looks at this and says， hey。

 you didn't provide me with two values， but I noticed the second one has a default。

 therefore I will pretend that you meant that。And that's the code that it produces。

 So it has a default in there。 and there are rules about default parameters。

 The default parameters must be written， must be coded from right to left。

 the parameters must be provided from left to right and if if it can complete it with defaults。

 it does。 So if there were like three parameters if there was like X Y and Z had a default if I call it with one parameter。

 that doesn't work because I'm giving an x， Z can default， but there's no version for y。

 you can't put comms like you can't say， oh， the first and the third have defaults， that's illegal。

You can't say all three default， and I want to call it with comma comma5hi。

So you can't leave out things at the start of the list when you call it。

 you can't leave gaps in the defaults when you make it， so we're not going to put this on the exam。

 it was just a matter of showing you something that you didn't know。

 explain it a little bit you can look into it more。Okay， so what about our tail recursor？Larithmic。

 okay， so here's our tail recursive logarithmic using thus the definition that we had before。

 So if n is0， we've got a base case， we return the result。Otherwise， we。Take what we've got。

If it's even， so if n is an even number， we take the。X times x to the n over two power。 So this one。

 we didn't actually call it and then multiply the result by itself。

 What we said is that let's just do an example。 Let's say I want to calculate2 to the fourth power。

 What we're saying is， while that's equivalent。To。Two times 2， which is 4 to the。Second power。

So that's the property that we took advantage of here and it looks like my tablet doesn't want to draw that okay。

So that's what we did was we said， okay， two to the fourth would really be。

Two times2 to the two power。 So we've used a property of logarithms to reduce the power and increase the base。

So we increase the base， we decrease the power and we give it the intermediate result。

And the intermediate result is the result we've got so far or the result we've got so far times x if x was odd。

 so let's do an example of this， let to get rid of those markings。

 let's say I wanted to calculate x is equal to5 or sorry to x is equal to and n is equal to。

 let's say 10。Okay， so I call it with2 and1。 and I say is it a base case， no。

 And actually let's just put it on the call stack here。 So I call it with two。

10 and the default is what。 So that's the first version that gets called。 We say as n equal to 0。

 No is an even。 yes， and is even。 So I return。I've got to make a recursive call with x times x。

 so that would be4。To the fifth power with the result is still what。Okay。

 we get into the recursive call。 iss this a base case， no is an even no。

So what we've got to do is we've got to make a call with。Four times4 is 16 to the second power。Oh。

 and the result is。4。Okay， I think 10 was a little ambitious here， but we'll live with it。 Okay。

 so is this a base case n0， No， it's not， okay， so is an even， yes， it is。

 So we need x times x of 16 squared 256。Got to learn your powers are two。

 so 256 to the first power with an intermediate result of four。Okay， we go to recursive call。

 Is this a base case， No， All right， is an even no。

 So we need to make a recursive call with 256 squared would that to Ty。

 It turns out 256 squared is 64 k。So that's 64 k 65536。To the zero of power。

 but the intermediate result is the current result， which is 4 times x， which is 1024。Allright。

 so that's our recursive call。 Is this a base case， Yes， it is and is equal to0。

 so I return my current result， We didn't actually need the 65，536。

It just came along as part of the getting to the base case， so 1024 gets returned。 and really。

 I drew this in a sort of un mistaken way。 there never was more than one call stack。Really。

 what happened is 2101 got overwritten with 451。And 4，5，1 got overwritten with 162 4。

 And those just kept over writing each other。 There was only one stack frame the whole time。

 It just kept getting overwritten。 But I was kind of lacking room。

 I guess I should have start in the bottom left and worked my way sideways。

 So there was really only one stack frame that whole time。 And when the final call is done。

 there is only one return address on the call stack。 see， we never， with a tailrycur call。

 you never replaced the return address。 It still has the one return dress from Maine。

 all that got put on was the different parameters each time。

So 1024 gets returned from the one stack frame and we're back in name with2 to the 10th is 1024。

 which is the right answer。Okay， so like we said before。

 the program stack size is limited if we have。Something that is。

Not tail recursive and ends and thus end space， it can go badly for us， even if we do something like。

 hey， I'm doing a tree traversal if my tree instead of being very branchy is very sticklike。

I could run that stackspace。For a large data set， non tail recursion is a bad idea。 So if we。

 if we don't know what the upper limit on the size of the data is going to be， we don't want to use。

Nontail recursion。In project one， don't use recursion。

 use the deck to make things happen if you find yourself wanting to use recursion in project one。

 you're going the wrong way。So this doesn't mean that everything has to be tail recursive。So。

If I'm doing a tree veral where I want to print out every node in a binary tree。

Well I have to either be nontail recursive， make a recursive call left。

 print the current one recursive call to the right， or I would have to use。

 if I don't use the call stack， I would have to make my own variable that was a stack to make it happen。

 and the program would be a bit trickier。Okay， so that's done with tail recursion， all right。

 recurrence relations， So we did this slide last time with writing a recurrence relationship for a value。

 for time for memory。And we looked at solving them。And we looked at solving a linear tail recursion。

 a logarithmic tail recursion。 And we looked at for like the calculation of our。

Just the one we did today， the recursive version of the x to the n power is logarithmic。And。

This same。Recurrence relationship also describes it says fits describes binary search。

 So once we solve this recurrence relationship， we don't have to solve the same one again if a different algorithm has the same recurrence relationship and we don't make a mistake in that step of saying。

 hey， here's the algorithm， here's the recurrence relationship for it as long as we don't make a mistake there then we should get the same。

Complexity by the recurrence relationship。We've got a slide here with just a couple of common recurrence relations。

 we're not going to ask you these on the exam， but just to give you some idea of when you might see something like this。

 so we've got binary search which we already did comes out logMM， linear search。

 we solved that same recurrence relationship， I don't even remember if it was linear search or something else。

 but we already solved that second recurrence relationship and got O ofM T traversal。

Would be two times t of n over two， assuming that my tree traversal is。Branie。

It turns out even if it's not， even if it's a big stick。

 the number the amount of time to print every node in a binary tree is。Over费。

We print every node once now we could have some more complex equations which we haven't solved yet。

 such as the equation for a something like selection sort。

T of n is t of n minus 1 plus c1 times n plus c2， if we go to the substitution method and solve that out。

 we get n squared。The next one， recurrence relationship form， for example， merge sort and Quick sort。

T of n is 2 T of n over 2 plus c1 times n plus C2， if we solve that using substitution method we can get。

And log in， however， we don't want to do the substitution method if we don't have to。

So we'd like to avoid doing those recurrence relationships if possible。

 and so we listed out what we can do last time， we can do the substitution method where we write it out。

 we substitute in， we substitute in， we see a pattern once we see the pattern。

 we skip to the base case and get a summation of what are all the things that got added up along the way to get from like my third substitution to the base case。

 how much work was in。We can also use the master theorem which we're going to look at in a little bit。

 and there's another method that you can look at called the recursion tree method。

 I find it's a little bit harder than either of these。Okay， so for example。

 what if I had a recursion where I cut it into two sub problems and I have to do both of them。

 So that would be something like the tree traveral like。T of sorry， this would be like。T of M。

Is equal to and both subproms2 T of n over 2。Plus， some other amount of work。So if that's the case。

 then we can。We'd have to solve that。 What if there is three sub problems and I process one of them or two of them or three of them。

 I'd get different recurrence relationships free in each of these。

 and I really don't want to solve all of those。 What if there's additional non constant work after the recursion。

 what if there' is an n over here， what if there's what if what if there's a constant work is a little bit easier。

 what if it's non constant。So a lot of these， if they involve。Cutting and dividing it into pieces。

 we can start looking at the master theorem。So。The master theorem sets。

We have to have a T of N that is monotonically increasing。

So what that means is it goes up in complexity and it keeps going up， it doesn't go up for a while。

 go down and go back up， it doesn't go up， flatten out and keep going up， it's always increasing。

So if M gets bigger。The time gets bigger。 The time never goes down at or stays the same as then goes up。

Okay， so we've got to have a T of n that's monotonically increasing。

 it has to satisfy a certain set of conditions， so the second one is easy。

 you've got to have a base case。Either T of1 is a constant， T of  zero is a constant。

 it really doesn't matter。 It could even be that T of2 is a base case。

 but you've got to have a base case。And generally， base cases are when。 n is 1 or n is 0。

 So we've got to have a base case， and we've got to have a function that is of the form that says。

I've got some constant A times T of n divided by B。Plus， sum F of M。

So some amount of work besides the recursion， so there's a few requirements。

A has to be greater than or equal to one。B has to be greater than one。

 We have to divide it into pieces。 and then F n has to be of a form。 F n has to be an element of。

パ워ド没有。So if all of these things are true。And I think。I think we've got a slight typo here。

 It seems like in the past， we had a change to this slide where we said that。

A has to be greater than0。It's not common for a to be like two/3， but it can happen so a should be。

Greater than zero here。So theres there's some odd cases where you can come out with a fraction there。

 it just must be greater than zero。 Okay， so if those things are true。

 then what we do is we look at what is the relationship， How is a related to B to the C power。

So if a is greater than B to the C power， we have this first case。

 big theta of n to the log base B of a。 If a is equal to B to the C power。

 we get the form big theta of N to the C power log of N and if a is less than B to the C power。

 then it's N to the C power， where C is not the constant， C is the。Degreee of the polynomial there。

 So we've got A out front， B is what it's divided by。

 and C is the degree of the polynomial for F of x。All right， so。

We've got a couple of cases here and yes， my slides are animated。 yours are not。

 so let's step through this together。 Okay， so what are the parameters for this， Okay。

 so a is the one out front， So that's got to be a。B is what we divide by。 So that's got to be B。

And then C has got to be the。 this has to be an element of whatops element of big theta of n to the C power。

 In this case， C would be。What。So we've got 3，2，1。 So A is 3。 B is 2。 C is1。

 So then what we what we've got to determine is how is3 related to。Two to the first power。 Okay。

 that's greater than。 All right， so if it's greater than， then we've got this form。

So we've got this form， it's got to be big theta of M to the log base two of three。Oops。

I guess' I guess I didn't have the answer in the slide， okay， Professor Dargan got these ready。

 he changed the slides just a little bit， so we've got big theta of N to the log base B B is 2。

 log base 2 of three。And we don't want to。We don't want to say， oh。

 what is the log base two of three because， well that's a constant， but it's not a simple number。

 it's a non repeating decimal。So we could look at that。

 we say well what is the log base two of three， we could say this is approximately equal to big theta of n to the。

 I think if I remember correctly 1。58 should have had this in the notes on the slide。

 so it's approximately equal to that， but this is the answer， that is the answer。

 it's not n to the 1。58 because that's an approximation。

So it is exactly equal to m to the log base two of three， but if we approximate that。

 we can just get a general idea of， oh， it's bigger than linear， but it's not as big as quadratic。

Just to give us an idea， it falls between linear and quadratic。Oh whoops there's oh okay。

 I didn't realize there was a okay， like I said Professor Darin readid the slides a little bit and I didn't know with the form of it here Okay。

 so there's the answer slide and we've got is this should not say equals。

 that should be approximately equal。So that's approximately equal to n to the 1。58， et cetera。

 et cetera。Okay， so we've got another example。So we got to determine what's A， B， and C。 Okay。

 so A is what's out front， that's A， B is what we divide by， that's4。

This polynomial is an element of。Big theta of M to the。Square root would be the one half power。

 so C is1 half， so we've got A is 2， B is4， C is1 half。So then we've got to say， okay。

 how is a related to B to the C power？2 related to。Let's grow to four， it's equal。Okay。

 so those are equal。 We must be in。The second case there。So if we're in that second case。

 we just need to substitute in see， so we've got。Big theta of square root of M log n unusual1。

 I will grant you。 It's unusual to have a square root here。

 It does happen in some really rare algorithms。 We won't see any in 281。But this one can happen。

And so we end up with M to the or sorry screwd then log n。No。Last one here。 Now。

 if you've seeing a theme that we got the first case， second case and you think。

 maybe this one might be the third case， that's a good intuition。 Let's see if it holds out。

 So we got to say a is what's out front there。 Well， a。Well。

 unless a must be equal to1 if there's nothing multiplied out there， the A's got to be 1。

 then B is got to be the what we divide by C has got to be the element of big theta of n to the C power。

 so C is 2。Okay， so we've got A is 1。 B is 2。 C is 2。 How is a。Related to。B to the C power。

 All right， that's less than。Okay， so if it's less them。Then， we've got。Big theta n squared。 Okay。

 so that's how to do them。What the slides don't show unless Professor Garen add it to there。あ，没事。

Okay， no he went the straight and one so what we need is we want to get some intuition about this。

 what do these three cases mean？So when we got this third case here。We saw that。See。

The exponent up here ended up being the final answer for our complexity。

What this is telling us is the stuff。Outside of the recursion is the bulk of the work。

So when B to the C power is greater than A， what that's telling us is that most of the work occurs outside of recursion。

All right， well， if that's true， then what about case1？

When we had A is greater than B to the C and we ended up with an N to the log base 2 of3。

What that's telling us is that the recursive portion is the biggest factor is the greatest amount of work was in the recursion and the linear that followed it was not as big。

 The recursion was bigger than the linear portion。Okay。

 so if a greater than B to the C means the recursion is bigger and a less than B to the C means the non recursive is bigger。

 then case2。Hast to mean。That。They were both important。See， we've got。2 T of n over 4。

 which2 T of n over 4 is is kind of similar to T of n over2， right？ There's four regions。

 I only have to visit half of them。 So that's this portion here is basically describing the log。

 and this portion here is what we multiply by。The two portions were equally necessarily equally。

 but they were both。Contributing to the total amount of work。

 one was not totally overshadowing the other so that you didn't even see it。

So when B to the C is greater。The non recursive is predominant amount of work。

A is less than B or when A is greater than B to the C。

 the recursion is the most the bulk of the work， and when they are equal。

 they both contribute some amount to the total work。So that's what these are telling us。

About these three cases now。When can we not use it， Okay。

 so if T of n is not monotomically increasing， For instance， s， the work goes up， the work goes down。

 you can't use the master theorem。 If F of n is not a polynomial， you like it's an exponent。

 So I did some recursion， but then I had an exponential amount of work， well。

 I'm betting the exponential law of work is probably going to be predominant。

 but we still can't use the master theorem。 if we can't express B as a constant， if I can't say it's。

 you know， if I have to say like T of square root of x。 So if I say like。

T of n is equal to T of the square root of n。Plus C。

 that doesn't quite fit the form because I'm not dividing n by something。And is getting smaller。

 sure， but it's not being divided by a constant each time。 So if you can't do those。

 you can't use the master theorem。 Now， there is a fourth condition， which we're going to show you。

 The fourth condition is one that we might put on a lab， but we won't put on the exam。

 The first three exam。 This would be a good point to say， hey， you know what。

 I should start making a list。 If I haven't already of what's going to go on my cheat sheet for the exam。

 But wait a minute， isn't the exam going to be online in an open notes。 Yes， it is， but。

You don't want to have to remember， oh yeah， the master theorem was in lecture4， no， lecture 6， no。

 lecture5， what slide is on let the page through there to find。

So start making a list of what you're going to put on cheat sheet now and when you get close to the exam。

Make that cheat sheet。Physically write it by hand will make it easier for you to remember what's on it than any other way。

Pandwriting makes better long term memory connections than typing。

 so I would say like right now be just typing out a list here's what's going to go on my cheat sheet and then when you get closer to the exam write it out my hand。

Okay， so the master theorem， the first three cases definitely fair game for the exam。

 the fourth case we'll talk about， you might see it in a lab。

 but we won't put the fourth case on the exam。So we've still got another when not to use if there's subtraction involved。

 you can't use the master thin， you have to go do substitution。

So master theorem basically is not applicable when it's not of this form and FM。

Is an element of big theta of M to the C。Now there is a fourth condition。

 let's look at that fourth condition。If F of n is of the form M to the log base B of A。

 and those are the B and the A that come out of the T of N is equal to A T of n over B。Plus， blah。

 bh。 So these are the same A And B here。 These are the same A And B that go in there。

 So if we've got F of n is of the form N to the log base B of a times the log of n to some power。

 And this is a typo this should be。F then it should be Fn equals， I believe just second。

 I'm going to open up my slides it looks like we've got a PDF translation problem here。

We're going to have to save a new version of these two。Okay， probably。Okay。

 actually this is supposed to be element of， so this is an element of that。

 then this is an element of that and k greater than or equal to zero。O。

So we've got to have n to the log base B of a times log of n to some power。

 When we say log to the case power of n， this is， so log K N。Is equivalent to saying。Log of n。

To the case power。So that's a that's equivalent。 So if that's true。

 then what we have to do is we basically have to increase K。 and that's our complexity。

 is basically the polynomial is。Part of the work。The polynomial increases in complexity。

 but it has to be related to the B and theA in the original one。So let's do an example here。

I've got T of M is equal to。Let me see if it is everything translate。 Okay。 Yeah， So every。

 everything came out in the slide in this one。 Okay。

 so T of n is equal to 2 T of n over 2 plus n log n。 Allright， so A is equal to 2。 B is equal 2。

 That's obvious。 F of N is not a polynomial， but is it in the form that。Meets the case four。

So we've got F of n is of the form， big theta of n log n。Now， obviously。

 k is equal to1 because there's no exponent there。 So that's equal to one。

 And but what we needed was we needed out here， we needed M to the log base B of a。But。Remember。

 we've got。N to the log base2 of2 is equivalent2。N。

 so that n right here really is n to the log base B of A。 It's the log base two of2。

So we really do have this form。 So then the overall complexity is big theta of M times。

Log of n the quantity squared。 So we could just say this is a equivalent to big theta of n。

Log of n squared and there's our complexity。So let's loggo then square that multiply by n。

So like I said， this is a fairly limited case， we might see it on a lab。

 but we're not going to put that one on the exam。Now we've got。嗯。A side here of。

 let's say that you've got a friend who maybe is taking 280 right now。And they say， hey。

 we got to binary search。 This thing is so cool， splitting things in half makes everything simpler。😊。

Alright， so what we're going to do is I've defined。

 I don't know why no computer scientist has ever found this before， but I， your 280 friend。

 have discovered that you can do the maximum element of。An array。In better than linear time。

So what I'm going to do is I'm going to use the power of this dividing into two into halves and say。

 hey， let's find the maximum of the first half。 Let's find the maximum of the second half。

 and whichever of those is bigger。 That's the overall max。

 And we keep doing this binary partitioning into smaller and smaller halves。 now。

Does it sound too good to be true that your friend has discovered something that no one else discovered in the last。

 you know，70 years of computer science， possibly。Unlikely on this one。But we've got to have a why。

Okay， so an intuitive y would be like， well， if you don't look at every element。

 how do you know which one is the biggest？Because it's not sorted。If it's not sorted。

 how can you look at？Log of an items and know which one is the biggest。

 that sounds too good to be true。But what we can do is we can say let's use the master theorem。

All right， so if we use the master theorem， I've got T of M。Is equal to。T of n over two。

Plus t of n over2。Plus， some constant amount of work， so I make recursor call on the left half。

 recursive call in the right half。The C represents things like figuring out where the middle is after the two recursed calls are done。

 I've got to take the maximum of those two values。 Okay， so this is the same as2 T of n over 2。Plus。

 accounts and amount of work。All right， we've got a master theorem here， right。

 we've got a is equal to to。 B is equal to2。 C is equal to。Oh， see， well， this is。

 let's call this C1， C1， that's not our constant。We need， hey。

 this non recursive portion is an element of big theta of n to the C power。

 that's the C we need here。And that C is。0ero。So we've got how is。A。Related to B to the C power。

 So we've got two is。Greater than2 to the zero。 Okay， if that's true。

 then we must have the first form， which the first form would be。M to the log base B of A。

So that's of the form big theta of n to the log base B of a。

 butve got that's big theta of M n to the log base 2 of2， which is big theta of n to the first。

So it's still linear， yes， you did divide it into two halves， yes， you did solve it with recursion。

 but you still ended up having to look at every element eventually。

So you can find the maximum in big theta of n time， but you can't do it in long time。Okay。

 now we've got a problem here that we're going to show you a bunch of different solutions to。So。

 this is。Previous。Job interview question that one of our staff staffs saw a number of years ago。

 it's probably been studied enough by now that you wouldn't see it again， but it's always possible。是。

You go to a job interview and they tell you that they've got this n times M table。

 This is the number of rows。And columns。So we've got this number of rows and columns and we tell you it's sorted along the rows and columns。

So the first one is saying， hey， anything in table sub I sub J is less than or equal to anything to the right of it in a higher column。

 So this one is telling you the first one tells you the rows are all sorted。

 The second one tells you table I J is less than or equal to table I plus 1 J。

 You're always less than something that is lower down in a different row。

 So this one makes a claim about the columns。 It says， hey， every column is sorted。Now。

 it doesn't mean there can't be repeats， the less than are equal to， so something like。1，1。

7 would be perfectly valid。But 10，7 would break the rules。So we've got this form。

 we know it's sorted along the rows and columns and we want to find a particular value。

 so we want to search for a particular value， I give you the value you search for it。We could do。

A linear search of every row。 that would be M times L。

We could do a linear search of every column that would still be m times n。I could do a。

Linear search of sorry a binary search of every row which would be M log M。

 I could do a binary search of every column， which would be M log M。

So I could do a binary search of every column。And I'm claiming these are still too slow we can do better Okay。

 so we don't want to linear search everything。 we don't even want to binary search everything we can do better。

 So let's look at a couple different ways to do better。Okay。

 the first one is we're going to split it into four quadrants。

And we're going to eliminate one of them。So for example。Let's say I was searching for the value。13。

I look at the middle。Well， I didn't get lucky。 That's not 13。I know that 13 cannot be。

In one of these quadrants， where can't it be？It can't be in the upper left because everything to the left of 9 is smaller。

 Everything above 9 is， well， none， not bigger。 So everything to the left of 9 is 9 or smaller。

 Everything above 9 is 9 or smaller。 Everything in the upper left region is 9 or smaller。

 So 13 can't be hiding in there， but it could be in any one of the others。

We can see visually it's in the bottom left， but it could be here that this 12 could be a 13。

 It could go 10111213。 So though that would be that。 So it could be in the bottom left。

 could be in the bottom right， could be in the upper right。 It just can't be in the upper left。

So we can eliminate one region and we can go recursively into the other three regions。Now remember。

 we're going to simplify this a little bit。We're going to say n is the size of one side。

 We're basically going to assume n and M are equal because， you know， if it's just one column， well。

 then I could binary search one column if it was run row。

 I could binary search one row So we're making the assumption that n is equal and。It's not true。

 right because even though M and the M were equal on the first one， this quadrant here。

 this rectangle here， it's not3 by 3。 It's 3 by 2， but it's still bounded by a rectangle that's no bigger than。

Three by three。so that's we're going to say that n is the size of one side and we're going to make the simplification that we'll just cut it into things that are squares or just a little bit smaller than a square。

It'll keep us in one variable for our complexity rather than two。不知。Okay。

 so I say here's my recurrence relationship， it says T of n is equal to3 t of n over2。

 so if n is the size of one side， so let's say I started out at say 16 by 16。N is equal to 16。

 but each of the sub regions is 8 by 8。 There's 4，8 by 8 regions and a 16 by 16。 So n。

 the size of one side has decreased by 2， but I've got to do three recursive calls。

 So I've got3 T of n over2 plus accounts in an amount of work。

Consant amount of work is figuring out where the middle is。

 checking if the middle is equal to 13 greater or less and determine which either the upper left I can remove or if I was searching for。

 let's say I was searching for the value。0ero， I would say， well， hey， this isn't zero。

 but zero can't be there， can't possibly be there。I could go up a row and I could have you know。

 900 that could be zeros right above me。So it could be to the left of me。

 It could be in the bottom left， just because there's a9 here doesn't mean the first column isn't 0。

00，0， that would still be valid。 So if it's smaller， I can still eliminate one of those。

 either the upper left or the lower right。Okay， so that one will come back and solve the recurrence relationship in a little bit。

Now， here's another idea。So I'm going to split it into four quadrants。

 And what I'm going to do is I'm going to look at the middle column， and I want to find。

Where the value should be。All right。I could get lucky， I could find it。

 but I'm looking for where it should be。So once I find where it should be what I can do if I just look on either side of that。

 I can eliminate two regions， let's do an example again。

 let's say I'm looking for the value is 13 again。All right。

 so I look at the middle column and I see that， hey， 13 should be here。 It should be， whoops。

 that was really messy。Anyway I'm going to clean my tablet screen Okay， so 13 should be here。

 which is basically it's between those two so I look at the ones on either side of where 13 should be 9 and 14。

Okay， because I'm looking for 13， it can't be。And and because it's not in the middle column I you're lucky。

 it can't be up here because everything up there is。Nine or smaller。

It can't be down here because everything down here is 14 or larger。

So everything in the top left is too small， everything in the bottom right is too big。

 I've got a search in these two regions。So if we write a recurrence relationship。

 I could say it's2 t of n over2， so n goes down by half。

 I search two of the regions instead of three， but I've got to do more work in that middle column。

 I've got to do C times n work。If I linearly search that middle column。But what if instead？

I wanted to improve that。 What could I do to improve that， I could say， hey。

 let's do a binary search on the middle column。 When I scan the middle column。

 let's do a binary search。If I do a binary search on the middle column。

 I get a better outside of the recursion fact。So my non recursive work is log work instead of linear work。

So I've got two different。Recurrence relationships here that I still have to solve。

 We're going to get all of recurrence relationships and then we'll show you the answers。Okay。

 so we've got the quad partitioning。 that was the first one where we split it into four and we eliminate one。

 So the quad partition is the。Eliminate what。Okay， so that's 3 T of N over 2 plus C。 Oh， hey。

 remember our good old friend approximately and the 1。58 power。

That's a real example of that algorithm or that complexity， that recurrence relationship happening。

Okay， the binary partition is when we linear。We linearly searched the middle。

And we showed it with linear searching and binary searching the middle column。

 we could do the same thing on the middle row instead。Okay。

 so we linear search the middle column or row， and that gives us。2 T of n over 2 plus c times M。

 we solve that one with the master theorem and we get big theta n log again。

The improved binary partitioning is when we binary。Search the middle。

So if we binary search the middle， we get this recurrence relationship。2 T of n over 2 plus C log n。

 That one can't be done with the master theorem。 That one we had to go and solve it by hand with substitution。

 It didn't quite fit the master theorem。 If it doesn't even fit the case 4 of the master theorem to fit the case 4 of the master theorem。

 It have to be N to the log base B of a log base2 of2 is 1。

 we would have to have N log n instead of C log n。 So this one didn't even fit the fourth condition。

 we had to solve this by hand。 We got a big theta of N。And so that one looks like the best so far。

 binary partition or binary searching the middle row or the middle column works better than the others。

 It's better than N log N， it's better than n to the 1。58 power。Now there's another approach here。

That we could do This one is called stepwise linear。

So let's take a look at this code and see what it's doing so it says you give me a matrix。

 you give me M and you give me I already know and you have to give me M。

 you give me the target that's the value I'm searching for and've got I want to return a row and a column number。

 where do you find it。But I can't return two values easily， so I'm going to return a boolean to say。

 did I find it or not？And if it says yes， I did find it。

 then what we do is we look in the row and column variables。So if it returns false。

 we can't look at the wrong column， they don't mean anything。But if we did find it。

 if the function returns true， then whoever called it can look at the row column to know where it was found。

Okay， so with the first line here， line two says。If the target value is less than 0，0。

 So if it's less than that or it's greater than that。I can return false。 Okay。

 so what we're saying is if I was searching for negative 3。It can't be in there。

 It's smaller than the smallest value。It's just not in there。

 I'm not going to do any searching if it's。Bigger than the biggest value。

I'm not going to do any searching。All right，Right there。

 it's not really a base case because it's not recursive， but it's just checking。

 it does search even matter， so if I can't search at all。

 I'll just return false because it's just not in there。Okay， then it says。

 let's start out with row0 column M minus1。 Okay， row0 column n minus1 says we're starting here。Okay。

 so we start there at 15 and I'm looking for， let's say again， let's say my value。Its 13。Okay。

 so I'm looking for 13， I don't find it there。 So let's follow through the code。 Okay。

 while the row is still a valid row and the column is still a valid column。 Okay。

 so as long as I haven't gone off the edge。If。The place that I'm looking is less than the target increase the row。

 Okay， so I look here I say， is that less than the target value？No， it's not。So I get to the else。

 is it is what I found there greater than the target now U yes， it is， so change the column。

So I look there I'm saying， he， I found a 15。 I'm looking for 13。 It can't be below this。

It's got to be。Let's move over there。 I've got a move left by one position。To see where it might be。

O。Go back through the lip is 11。Less than what I'm looking for。 Yes， it is。 so it cannot be here。

 It can't be there because everything to the left of 11 is。1even or less。

So everything to the left of 11 is the same or smaller， 13 can't be hiding there。

 let's move down a row。All right， move down a row， go back through the loop。

 Is that smaller than what I'm looking for， Yes， so I can eliminate all of that and I move down row。

Is that value there smaller than what I'm looking for， no。Is it greater than what I'm looking for。

 yes， so I can eliminate all the bigger values below it and I can move over here。Okay。

 back through the loop， is that what I'm looking for， no， it's too small。

 so I eliminate those and look down， is that what I'm looking for， no it's too big。

 eliminate that and move over。Is it less than no， is it greater than no？Else， it must be equal。

 I can return true， I found it。Okay， so I found it。 It works。 If we were looking for。

 let's say we were searching for 0。 We'd start at 15。 We'd go， oh， smaller move left， left， left。

 left。 I fall off the edge。 The wild loop stops， and I return false。Okay。

 so what's the complexity of this one？Well， let's get an upper lift。We could get lucky。

 I could be searching for 15。 And hey， I just found it there。 So really。

 all of our analysis so far has been worst case in the worst case。I could move。Basically。

M minus-1 times down。 I could move。N-1 times sideways。And I could find it there。

 or I could have to move one more。 So it's basically M minus-1。Plus， n -1。划蒜。Because I could go。

 I could go something like down， left， down， left， down， left， down， left。

 And eventually I go off the edge。 so I can move down M-1 times。 I can move left M1 M-1 times。

 and I can move one more time。 and I move off the edge。 So this complexity is。Basically， M plus n。

And if there was only one variable， it would be big theta of n if they were both the same size。

 it would be big theta of n。So that's our worst case complexity。It's really。

 it's approximately2 n' basically。M plus n minus1， which is 2 n minus1， which is 2 n， which is n。

So it's， it's approximately big theta M。 Now the， we've got a source here that analyzed， oops。

 and there's an example of running through that before we get to the to the how these all compare。

 can we change this search， I'm going to get rid of all my markings here。

 Could we change this search， And instead of going from the。Upper right to find it。

 could I start from the bottom left？If I change the code， could I start here and say， hey。

 I'm looking for 13。It can't be these， I've got to move the row， I've got to minus minus the row。

 and then that's not what I'm looking for， I can eliminate those and I can plus plus the column and oh look I found it。

So yeah， if I change the code around a bit， I could start in the bottom left and I could change my rows get decremented columns get incrementmented to move up and left。

So with a few changes to the code， we could make this work starting from the bottom left。Could I。

Start searching for the value 13。In that corner。Well I look at that and I go， okay， that's not 13。

 so 13 can't be here， do I go right or do I go down？I don't know， could be either one of them。

I've got no information， so I can't start in the upper left。 I can't start in the lower right。

 I'd say， well， that's not 13。 It's not in the bottom right， most corner， but should I go up。

 Should I go left， I don't know。 So this one， we can start in the upper right。

 We can start in the lower left if we change the code a bit。

 but we can't start with the biggest or in the smallest because it doesn't give us any information。

Okay， so we've got analysis here of running these different ones。So the binary search。

 so he didn't even do linear search of every row， this is binary search of every row。

Diaagonal binary search。 This is searching along the diagonal。That's not very good。

So then the stepwise linear is the one we just did。

The quad partitioning the first one the quaditioning is the first one of four quadrants eliminate one。

And then the binary perition is linear search the middle。

And the last one is basically binary search the middle。Now we got the best two here are。

The step wise linear and the improved binary part。 Both of those were big theta of M。Why is this one？

Not much more than half the time。I would say probably。Cash locality of reference。

And we're going to talk about what that means coming up some La see how we are on slides and on time。

 okay， we got time Okay， so let's talk about what it means this is something that is good to know to understand how things work。

 but we are not going to put this on topic on the exam。So we've got to understand how computers work。

 So remember I said a little while ago， also not on the exam that for the CPU to do any operations。

 the value got to be in the CPU。The problem is we've got a CPU sitting up here。And the CPU is fast。

 we're talking like five gigahertz。Down here we've got our DrRA。

And then below that is things like you know our。Flash memory are hard drive and stuff like that are even slower。

 So it's got to be in Ram before we can do anything with it。

 and then it's got to get to the CPU before we can really make use of it。

The problem is the DRAM is much， much slower， we're talking orders of magnitude faster than the5 gigahertz of the CPU。

So we're talking orders of magnitude faster where like if the value isn't in the CPU going out to get it is like wasting 500 operations。

And that's really， really slow。 So as computers got faster。 see when computers started out。

 the difference wasn't too big and CPUs have gotten faster。

 faster than more quickly than memory has increased in speed。

So what computer designers started doing is they started adding something in between here。

Called a cash。Comes from the French cachet to。And what it means is the cache memory is。

Close to the CPU in speed， like maybe just as fast as the CPU or maybe just。Half as fast。But much。

 much faster than the D D Ram， But the cache can't be as big as the D Ram。

 It's limited in size because the cache might live inside of the CPU and making stuff that fast inside of the CPU takes up a lot of space。

 So the cache is limited in size。 Maybe this might be like one mete。

 And this down here is like 16 GBs。 So we can't fit everything in the cache。

 What do we put in the cache。 Well。The things that we've used recently。

And there's a whole set of algorithms about what to put in the cache， what to get rid of。

 when the cash is full and new things are needed， what should you get rid of。

 there's a whole study of this area and the how do they do it。

 well they aren't telling like arm and Intel and AMD and now Apple is producing their own chips nobody will tell you exactly how their cash works。

 but there are good ideas， take a computer organization course you'll get some ideas of how the cache works but the exact details are proprietary。

 but we got a pretty good idea how this works， but we don't need to go into that。

The idea here is that。If we have to go from the CPU to the cache， we don't waste much time。

 but if we have to go from the cache to the DRAM， we waste lots of time。

But there's a slight thing that can save us， which is。

When we go to the cache from the cache to the DRAM， instead of wasting like， let's say。

 200 cycles to get one piece of information， we could go like 207 cycles to get eight pieces of information if it's all adjacent。

So we could go get one thing in 200 cycles and then later on we could go get another thing in 200 cycles or when I go to get one thing。

 I could get it， so I say， hey， I want this value from the RA chip。Well。

 let's not just grab that one。 Let's grab that one and。The seven others。

 let's grab eight things total。In a row， consecutively。Why。😮，Because of what's called。Loality。

Of reference。Because we notice from analyzing how programs operate that if you look at this place in memory。

 what is the most likely place you're going to look next in memory， the one right next to it？

If you looked at X， you're very likely to look at y in the future， it's not a guarantee。

 but it's a pretty safe bet。If we are wrong。We've only wasted like seven cycles。

 so 200 cycles to get x， 207 cycles to get X， Y， Z， PDQ， whatever these other six bytes are called。

 or six words or whatever the size is， to get those eight things， I've only wasted seven cycles。

 but if I guess right。I've saved myself。Like 200 times seven cycles。So I've saved almost 1。

400 cycles by grabbing eight things at a time。If locality of reference holds and it holds pretty off。

So if if you go back and look at how each of these algorithms work， the improved binary partitioning。

 because it changes rows just as often as it changes columns。It breaks locality of reference。

 you like if every row is contiguous in memory。When I stay in the same row， if I move right or left。

 I get another block of size 8， and if I stay in the same row I'm good， but when I change rows。

 I need a whole new block。Every time I change rows， I need a whole new block。

 so the less often that I change rows， the more locality of reference comes to my rescue and saves me time。

So like I said， this topic is not going to be on the exam。

 but it explains lots of things how these are why these two are very different in time。

 even though they're both big theta of n。 Now， it could be one is big theta of5 n and the other is big theta of。

12， but I think bigger issue is the locality of reference and the use of the cash。

This also explains why in Project1， we told you your 3D vector。

 you've got to say something like Castle。Square bracket room。Square bracket row。

Square bracket column。If you reverse the rows and columns， you will be slower。T you should be。

Because reading in will be slower， producing output will be slower。

 the searching might or might not be slower because you'd go north and south just as often as east and west。

 but it would make the reading in slower and make the output slower。

So this idea of locality of reference。In forms of why we do other things the way we do them。Okay。

 so that's the end of the lecture there's a few study questions here。

 oh and this is slightly outdated， I didn't think to go back and edit these we used to。

 we used to recommend not require， we used to recommend a textbook called CLRS。

 which stands for Corman Lyer andve and Stein are the names of the authors。

 it is the book on algorithms， but we stopped recommending it because it really we give you everything you need in the slides。

 and this is even a terrible suggestion because the master theorem in CLRS。

 although it is equivalent in power， it is much harder to apply it。So I would say， yeah。

 just ignore this outside。At least everything about CRS ignore that。And this is good， though。

 like take an equation， solve it with the master theorem， solve it with substitution。

 that would be good， just as practice to get ready for， hey， when it's exam time。

 you might have to do a substitution on an n minus one sort of problem。Okay， so we're done for today。

 I'll end the stream here and I'll see you in the office hours in about 10 minutes。

