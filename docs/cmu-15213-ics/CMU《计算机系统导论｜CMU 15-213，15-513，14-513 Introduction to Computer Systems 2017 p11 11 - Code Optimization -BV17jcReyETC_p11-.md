# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p11 11 - Code Optimization -BV17jcReyETC_p11-

Today we're going to talk about code optimizationization。They to chapter 5 in the book。

So we get to cover an entire chapter in one lecture。是 be翻。嗯。

This is actually a topic that's near and dear to my heart because I teach the graduate level compile compile optimization class in the spring。

Obviously， you won't cover an entire semester's work。Yeah。This class。But I will use。

Example that I using thats not the first day of that class。IIncorrated in this lecture as well。

All right， so today we're going to give an overview， talk about some generally useful。

Optimizations that compiler does。Then we're going to look at some things that prevent the compiler from doing a better job。

The things to think about when you're programming。We're going to talk about exploiting instruction level perism。

This is the notion that the processor can actually do more than just one instruction at a time。

If we sort of set things up properly。And then sort of a blocker of that is conditional。

Expressions and how you deal with that。Okay， so。Again， white， you know。

 we're not having the write compilers right out much of these plastic。

But we're trying to get you to be a position where you can understand the performance bugs of your code。

Understand what the bottlenecks are and how to get around them。

And so part of that is sort of understanding what the compiler。The optimizer and the compiler。Can do。

 will do for you automatically。不关。which you hope it might do， but it doesn't do for whatever reasons。

 and lean again， you can adjust your code。嗯。Slightly to help it out。

 ways you can help the compiler along。Okay， we want to do all this improvements of performance without sort of destroying other nice properties of your programs like their modularity。

And your generality。Okay， so the we've seen some of the things that the pilots do already。

 things like register allocation。嗯。But they also do。

They'll find docsties and code and seek to eliminate it。Now。

 one of the reasons that we actually have you run GCC with basically almost no optimization whatsoever is so that you can see a more clear cut mapping of the code you wrote and the assembly code。

But in general， if you say do Op level three， it's free to pull things all over the place。

Do inlining all sorts of nice tricks that will speed up your code。ち回。So。

Code motion is a general useful optimization， so this is one where you take。

SomeSome aspect of the assembly code that's。That's done inside a loop。

 And you realize that it's loop invariant that basically is not changing the value this。

Especially the value of this thing that you're using iss not changing inside the loops。

 there's no reason to recalculate it every time you go through the loop。So here's an example here。

 kind of from a C code perspective。Right， if you。All right， if every time。

You're doing this multiply to sort of get you to the proper row in the set row function clear to that n times I is a multiplication that's happening inside your loop。

 if n is a not a power of two then you can't even do it using shifts so you actually have to use it and you multiply。

 it can be expensive operation， so instead you just want to pull it out。Search。

Pull it outside the loop， so inside the loop you're just referring to the result of that multiplication。

Okay， so that's how you do it in C code， but as you'll see the compiler will do that online。Okay。

 so here you can see that。Right there right here you computed N times n minus1 and it's basically outside。

Let see， okay， so we go into this loop， we do this moving client。We complete this address。是。Right。

 and then we're going to just go inside of it。 So you can see that that it's。Using the NI。

That's pulled out inside the loop。可以。And so that's， again。

 equivalent to having changed the C code as shown there。Okay。

 another thing that you've seen is the way it tries to take operations that are otherwise expensive。

Things like。Applying by powers of two and changing them into shifts。

or these interesting calculations with the LEA instruction。

 where you can multiply something by five just based on the adjust calculations。

Another thing that occurs a lot of time in code is a common sub expression。

 so let's suppose that you have this sort of stencil like program。Where you know are you？

From a position I J in your 2D scil， in your 2D grid。You want to look at sort of what's one up？

So if you're here in the grid。it's some 2D grid。You want to look at the one that's up。Down。

Left and right。Of the point of interest and so to do that it's this series of address calculations right so to go up you want to take the current keep the J but you know jump up by row down its the opposite you want to add a row and left and right you just want to。

Subtract one or add one。具的要这个个邮。可以。So if you do that。

 then what you end up with is these three different terms you're trying to compute。the i times n。

 I plus 1 times n and the I minus1 times n。Which would be three modifications。

But because they they're very closely related， you can do it with just one multiplication， right。

 if you compute the I。Times n up front， then the relationship between these four different。

Positions is easily calculated as shown here。whatever that position is。

 you just subtract n to get the up， you add end to get the down。

 you subtract one to get the left and you add one to get the right。Okay。

 and so if you look at the code it gets generated， you'll see that that's the shortcut that's made。

And yet it' just one not。And again， because N could be anything it's not necessarily a power to。

 this could be not a cheat multiplication， or it's the actual， say， three cycle multiplication。这款心上的。

All right， good。So now let's look at this example that we like to use to my class in the spring。

And so the simple bubbleword algorithm。Okay， you may have studied in an algorithmms class。

 kind of a naive way to sort， it consists of two nested loops。All right。

 and a comparison of elements side by side， so basically what happens is the first time through the outer loop。

 you sort of bubble the largest element to the top of the list by doing a bunch of pairwise swaps you so that sets and then you go down one from there and you bubble up the second to most expensive second and most large。

Element and so forth， until you finally get done and the whole thing is sorted。All right。

 now this is a little artificial， but it makes for you know， more interesting example。

 I'm assuming here that the。That the programmer was resistant to the C notion that array started zero and so they wrote their program insisting that they wanted to keep their values in A1 through AN as opposed to A0 through AN minus1。

 and they're perfectly acceptable to do that， maybe that helped them with conceptualizing later indexing into the array and so forth。

All right。And so what that means is that the address for a sub J is computed the starting address of A。

 and we're assuming that the elements are four bytes， but you have to subtract one off in the J。

 so take this array from 1 to n and for C， for allocationocs purposes。

 we actually move shifted it over to zero to n minus1。Okay， so and this is just a swap， right。

 so you just if the one if they're in the wrong order in terms of large and smallest。

 you just swap them。Okay。So inside the compiler， it's going to start off and it's going to take this code see COVID and produce。

So sort of intermediate representation。Notion of the code that it's used to。

 this is not necessarily anything that ever gets exposed。To you。As a programmer。Right啊。

If you play around with any use of pilotrs like LLVM。

 you have to learn what its internal representation is。

 and then you can get very fast with it and start to understand it is it just a pseudo internal。

But you can see what's happened here is sort of a straightforward translit of this code right so you know we wanted to start by setting I equals n minus1。

 so that's what we did。And then we need to do this test， right， and so we flip it。

 we say that you know as we've seen in other classes。We say that instead of during the while。

 we do the exception， so if I drops to less than one， then we're done。

 so we're going to jump all the way to the end when we're done。系い。Otherwise。

 we're going to enter the center loop。I'm going say J go to one right there and again。

 if j is greater than I， then you're going to be done with the inner loop and go to the next step of the at loop。

 which is here， which again， you decrement I and so forth Okay， then the rest is sort of setting up。

The value a sub J by the addressing mode and H sub J plus1。

 and then once you have the value of those two things， you compare them。

And if they're in the proper order， then you move on to the next J。Else you do swap。

 so this is all the swapping literally you know you're going to have a sub J so you compute that and put it in some temp and then you compute a sub J plus1。

 and then you do the first assignment and the second assignment and then you're done。

So it's just a mechanical translation of the code。Okay and when we do that。

 we get you know 29 instructions in the ater loop， so 30 instructions at all。

 but we don't I mean this one' executed once， that's no big deal so addta loopop has 29 instructions。

 including that there are 25 in the inter loop。Okay。So that's sort of the starting point。Al right。

 so the first thing we observe is that there's there's interesting redundancy in dress calculation。

 right， So we wanted to compute a sub J plus1。So the first thing we said is， okay， what's J plus1？

And then we remembered， oh， but wait， our addressing mode is， the address of A。Plus， four times。

J minus1， right？So just literally， you know， just a direct transliteration。

 we have to we subtract one off that， and then we multiply by four。

 and then we retrieve that address。Okay。And so。So this is the this code。

 but then the first thing the compiler realizes now is that okay。

 I've taken something I've added one in the mean that's subtracted one okay。

 so that's kind of redundant and similarly here we've added one it's subtracted one。嗯。Okay。

 so here we basically recomputed an address。呃。That we already have some sense because we've already had to compute both these values。

And again， here we add one and use subtract one。All right。

 so the first step you can do is you can take all these four sequences and you can just locally decide that you can place them each with one instruction。

Okay， so you know， there's no more adding is subtracting one。And so forth here。

 there's no recomputing address because just we already have it。And so forth。Okay。So how are we done。

 So now we're done down at 20 in the outer loop and 16 in the inter loop。

 right was what was it before it was。29 and 25。All right。

 so now we look and we see something like this where。knowAgain。

 we were doing the swap so we' were sort of reusing these addresses。

 but the first time through we just blindly recomputing each address right so there's redundancy here so we can take all this instruction here which was just used to do the swap。

And we can just replace it with these things， right？So back up a second。

 we already had a sub Js hanging out in temporary three and a sub J plus1 hanging out on temporary 7。

 so doing all this work to compute their justice and retrieve their values is not needed。

 we can just use the temporaries that we have stored。Okay， so an now we're down to 15 and 11。So。

 good。Another thing again I mentioned it looks at closely at loops。

 so what's done inside of loop and what we avoid doing inside of the loop。

So if you call in this loop， so this is the inner loop， we said J or1， we do this test。

 and then we start this address calculation based on J。哎。And then later we do J plus1。Well。

 the interesting thing here is that the。Because this address calculation is sort of going lock step with incrementing of J right every time you increment J。

 this address calculation ups by four。So there's actually no reason in this code to do both。Okay。

And since we need the four version of it for the rest of the code to work。

 we're just going to use that instead okay。So now all references of J are gone。

 and instead we just initialized the starting points of。J and J plus1。

And compare those right in this equivalent I can compare four times J。

And four times I just as I compare I times J to I。And then instead of bumping up by one。

 we bump these things up by four。Okay。And so。That's again， useful because now in this final code。

 we only have nine in the ennu。As opposed to 11 and still 15 in the out。

 So we basically cut things by know roughly about half for both the outer and thes。All right。

 so any questions on that？Yes， how do you re this changing cycle。じも行し。So this is inside the compiler。

 so what would happen is that when it was done doing all its optimizations in its intermediate representation。

 then it would have a instruction selection phase where would then spit out the spit out the or sp out the machine code so theyre all the same but。

Yes，So it doesn't go back and fix your seat code for you。I the question。Okay。

 and you can imagine you know， that there's a lot of analysis that the pilot has to do to get this right。

 because it has to make sure that things that you've defined in this little segment of code here aren't somehow used later and so forth that。

They your'。A big part of the compiler is making sure that the transformations it does are safe。

 right they're not going to mess up the。O。So what are some of the limitations of optimizing pilots？

Again， they have to be safe， so they have to take the information they know about your program and make changes that don't break it。

Okay， now there's this one caveat， which is kind of fun。嗯。

If you happen to write a program that uses some non standard language feature or something。

 then the compiler is often allowed to do whatever。嗯。So why is that。

 it's basically because you don't want to force the compiler writer to have to。

Accommodate all these non standard features。 and so it's going to just。

Do whatever's convenient for programs that use the standard features。

 and if they happen to do some weird stuff for nonstand features， then so be it。You know。Byier。

 beware。Okay。And the other thing is that， you know。

 and we're going to talk about this in this class are there's like things where you look into your code and say。

 like this is a why ist with the pilot f this out？And again。

 part of it is that there's information in the programrs had or in other parts of the code that the compiler just doesn't see。

That basically， you may define a variable that has a fairly wide range， but you know。

 as a programmer， there's only some number of possible data values you're going to use in your program。

And， you know， so because that's in your head， you think， oh， you know look Po you know that too。

 but it doesn't。Okay。The other thing is that。Tilers。I mean。

 there's the reason we have different optimization levels of compilers is because there's this tradeoff。

 the longer the compiler spends running analysis on your program。

 then potentially the faster you can make it run。But there's diminishing returns， right and so one。

Common thing is separate compilation right so if I compile a file that's part of a larger program。

 C file is part of a larger program， the compiler may not have visibility to those other files。

RightAnd even if it does， the analysis gets more and more expensive depending on how many pieces you bring it。

 if you have 10，000 lines of code and you're asking the compiler to do some analysis across 1000 lines of code in order to do some optimization。

 that's as you can imagine incredibly expensive。嗯。Okay。

 and so typically things motion analysiss form only within procedures。

Okay so you just locally located at it inside a procedure。

Because otherwise you have to figure out all the possible ways this procedure can be called and the relationship between all the arguments。

 there's all sorts of variations on this that people look at but。嗯。You know， it's not in general。

 it's considered too expensive or it would be too expensive to do sort of a full blown interprocedural analysis where I decide how to optimize particular function based on all the different ways it's called in all the different contexts it's called。

啊。So traditionally， and the compile you're used to using- it's all based on static information and pass the code that you're handing it。

 it doesn't know the inputs， for instance， right？呃。And so because of that。

 it has to make conservative assumptions about what might the inputs be。

Now I qualified that a little bit because we have sort of just in time compilation techniques and so forth that will try to make use of information it learns about。

 say the arguments to a procedure as things are running and re optimizetimize on the fl。

 but that's the standard approach particularly for language like C。

 is strictly based on static information it's what the code is。

On the page without executing anything。and again， when in doubt， the pilot must be coned。

CanCan't make these wrong。Okay， so。This is interesting example。

So it's a simple thing you're just trying to take a string。And convert to lowercase。Okay， so the。

The basic operation is。That。If I have a。嗯。Right if I have a character that's basically in the capital A to capital Z range。

 then I want to。Converted to lower KC to lower K C。

 and since the letters are at sort of the capital letters in the。

TheThe lower case letters are at a fixed offset from one another。

 I can do this simple arithmetic if I just subtract off the difference between the start and the two alphabets。

Then no matter what character I have， I'm going to jump it from uppercase to lowerrkeys。对。

And so the programme says， okay， this is what I want to do。

 I want to go through my string for however long it is and do the simple conversion， right？

So youd think， okay， I look at this， it's got to run through a string。

 it's going to take time that's basically the length of the string， some constant length string。

So let's look what happens。Okay， when you run this？

And this is time on the y axis and the string length and the x axis。So if we really were linear。

 you'd see a straight line here， instead， we're seeing。quadratic。Okay。So why is that even our guess？

Yes。😊，The offset。The。嗯。Well， it's just。It's just doing an increment each time to do the offset so that's a sort of a constant operation time to look at it's calling Stling for luus。

Right， so the thing is it's this function call， right？And sterling。

 what it does is it marches to the string until the seasonal， and then's how you know how long it is。

All right。So if you see how this code gets converted into sort of the go to form that we talked about in the previous class。

You'll see again that the sterling is inside every variation。And you know it's calculated by。

 you know。Incrementing until you see that null character that eliminates the。Okay。

 so that means that you know， it's called it。It takes end time the first time through since you're shifting off the looking at less and less of the stringage time。

 it's n minus1 and minus2 down to one， but that's still quadratic fine， summarize does a lot。Okay。

 so a very simple fix that you say， well， why can't the compile figure this out is， you know。

 just pull that string like calculation out of the。The loop self， right， do it up front。Right here。

And then we're fine， right， so then the code looks like that。Okay， you can it's。

I didn't even see the slope， but it's basicallys。linearar in the length of the string。

The lower two is the version where it was pulled out。Okay， so。

So why couldn't the compiler pull that out because it was a function right and it has to worry about the various kinds of side effects。

That that procedure sterling may have， right？嗯。It could。It could depend on other things going on。

 Maybe the string is being updated behind the scenes every time。

 maybe there's some other procedure that's actually， and we'll see an example of this in a minute。

That's sort of later adjusting the string。So it doesn't know that Sterling is going to return the same value every time。

And so that's why it has be sir。嗯。So because of some of these issues with the procedure calls and some of the overheads of procedure calls。

 one things you can do for shorter procedures is the compiler can inline the procedure itself。可嗯。

And then。Therefore， it。Because if it could see the entire content of the procedure and knows that there's no way that anything else can mess it up。

 then it can actually。Realize that this value isn't changing do the analysis and go from there。嗯。

And the other thing would be， of course， do your own code motion。

 which is what pulling the length out of the stream was。Okay， so this is an interesting example。

 so here we have we want to sum up the rows， we have a two dimensional matrix。

And we want to sum up the rows and store it in the Spec B。

 so we pass it a pointer to the matrix and a pointer to the row we want to populate and the length。

可以。And so what it does， it goes through and it says。Well。

 initially I'm going to look at one row at a time。And initially that the sum of that row is going to be zero。

 so the I row would be zero， and then I just run through the elements of the array。

And accumulate the sum。And then when I'm done with that row。

 I do the aer loop and I go to the next row and so forth。Okay。啊。

So if you look at what's going on here， this is the inner loop。You'll see that it's doing a。

It floating point load and then an ad and then a floating point store。Okay。

 so it's updating basically this B subI。Every time through。

SoBut to think about how you're using that， you're just using that until the very end。

 it's just accumulator， you're just accumulating the sum as you go through。た。So。呃。So the programmer。

 as we'll see in a second， could actually do that， can say， oh， well， let's not confuse the compiler。

 let's actually create a temporary that we accumulate in。

 and then only at the very end that we store into memory what the output temporary is。

But youd look at this， you think， oh why can't the compiler figure this out， I mean。

 it's what we're doing， right， it's just in a keen relation here。

You know why is it botherling distort every time and then the very next time for the loop。

 it loads it up back up again。It seems very wasteful I mean at the very least maybe it's， you know。

 if I've got it sitting in this register， why do I need to load it again， it's this there？Great。

Let me see what the issue is here。Why is that compile pilot actually？Correct in not。

During these simple optimizations I just discussed。Yes。That you're on the right track。

 we have two arguments。A point to A， according to B。Okay。What if those overlap？一回。

What if every time you update B， you're actually changing part of it？All right。

 and we have an example of that here。Okay。So let's suppose that just a simple three by three matrix。

Okay， and so with these values， and we're just trying to sum these different roads。

But then we happen to find B。As being this。The slice of a。Okay。

So initially B is what would expect it's 4，8 and 16。

But now we start to run this code and we' going to see what happens。Okay。

The first thing that happens is we're going to set。Beast of I。呃。To 0。Okay。

So that means that there's a zero here。Which then， of course means it's a 0 and 8 version 2， right。

 because they're referring to xing justice。So by setting by doing this assignment of zero here。

I actually set that to zero there。Okay。Now。Okay， so now I do。I start to do the sum。

So I want to sum the first row， so I sum I sum the zero。Okay。

 and I'm going to add that to the zero and I get zero。

And now I moved to the next element and I got a1， and I want to add that to my running sum。

But so that's why this becomes a one because it's a one over here。And then I'm going to add this two。

 and it's going to be a three here， which is sort of what I expect。

 but then there's also a three there。喂。So this is correct， this is the sum， you know。

 this B vector has the sum of the first row as it' supposed to。But as a side effect。

 it's actually changed the contents of A。So now when we go on to the next row， you know。呃。

This second row of a is。You know， it's interesting， right， it's changed。Okay。

And as we go through and we add up the oh and so the first thing we do is we set this thing to zero。

 which we meant to do over here， but because of this airiley thing。

 it actually also sets that to zero there。and then we start to accumulate so we add this three。

 and then we add three to itself and we have a six and now we add the 16 and we get a 22。Okay。

 so it makes sense from the beefs perspective because。

22 was the sort of the values in that row as we saw them， we march through them。

 but they were changing on the fly I it's no longer even the sum of this row。Okay。

So because this is possible。The compiler has to。You know dutifully store back。

The result in the BI and read it back out to see if it's changed。Okay， because in this case， it has。

他这一款是在哪里这。so forth。Just same thing continue to run，O。So， but now。

 if what we do is we just say we're just accumulating as temporary， so let's define a temporary。

That has nothing to do with A or B。Then now I can do the accumulation and then just sign at the end。

 right and I don't have to worry about this a submission。And you can see from the inner loop。

 it's very simple， we're no longer doing a store and a load to store and a load to store load every every simple time。

So memory air listening。I when two different memory references saying like C code actually specify the same location。

 a single location。A version of this would be if they're somehow overlapping locations， right。

 so if one reference。One memory reference is to a bitete that's in the middle of a word of another memory reference right then there's aing quote there。

And because of that。You know， the compiler gets blocked from doing various kinds of accusations。

 even though in your head， maybe you know， you'd never be dumb enough to pass it the A and B argument that I just showed you before。

可。So the way to get around it is to introduce these local variables like we did for this accumulator valve and just accumulate separately within loops。

那你小伙。可以 so关系上呢。All right， then it'quiz time。

![](img/650fa1a3a59a819adf5f5c536691f11c_1.png)

All right， when this of time， we're going to move on ahead。嗯。

You can do these more at your leisure later， if you want to think about them some more。Okay。

 so the first question was a stack of question。People are pretty well in that it's just capturinging the notion that just because you move the sack pointer doesn't mean the thing that was there before has disappeared it's still there right so this example we pushed。

15 to 13 onto the stack， and then we popped。From the stack， but that just moved the stack point。

 it didn't actually erase any values， so you would still see that value on there。嗯。

This second one is a variation of the uppercase to lowercase， one that I had in class。

 which tries to avoid the sterling altogether。嗯。Again， it's just a little bit of a review on your。

Facility with， with。You know， theip issues of pointers and so forth。

It turnsns out this is that correct code， nothing wrong that code。And good。

 the last question a little bit tricky as well， so one makes a listing hard。

Is not the case where the compiler can tell that they're always aliens okay。

 it's really when it doesn't know， I mean， there are many cases in your program where the compiler knows full well that these two things refer to the same thing。

And if it knows that and it knows that for， they always do。

Then it's able to act accordingly it's not fool at all right。

 it knows that there's multiple ways to reference something off relative to stack pointer and so forth。

So it's it's not that it's。It's not that the aing itself is a problem。

 it's the uncertainty about the ason， that's the problem。

Because then the compileilr has to be conservative and say， oh。

 I'm going to assume that these might alias。When in fact， know maybe they never do。

 and I have to do something really conservative。Any questions on that the one？

Tamp look like that would cause me。Isn't uneocated member defined as anything below RSV？三个。最ほ。嗯。下个。嗯。

So in this case， I don't know how， I mean， so the cases that we've shown in class where you get sa faults is when you sort of access past。

You know， sort of legitimate regions of the stack or of memory that you're allowed， right？

So you know we had that example where the， you know。

 you created a buffer that was too small and you kind of wrote way past it right。

 and then at some point you wrote something that caused the system to crash。

So it's like so for instance， if you corrupted the return address。On the stack。

 right and then you try to branch that。是吧。这边。嗯。Yeah， but in general， I don't know。

Ass how you would get a se out。I'll just push him up。Yes。我宣れ。嗯。Well。

 if you give it a string with not a no character， then it's going to。Correctly。

Just keep going things crash， right？Well what's true of any of the string operations， right。

 that's how you get。C does not protect you against。Sort of passing inval arguments， right。

 so there's no different from。The sterling。safer version of here。嗯。Yes， you can you can well。

 there's。There's I mean， there's safer versions all the string manipulation things。

 we actually specify lengths of things， so you don't go past the boundaries。

But you don't have to use those， you can use the other ones in any。Me。 okay， good。Good question。

 sorry。Yeah。So， in personally。先去找些。So what happens is that the。That that you're。所是说。说 this is。Okay。

 so yeah， there's subtions here， I mean it's just a quiz right。

 keep a simple so this this is sort of single threaded code， there's only one thing going on。Okay。

 and so。The state of the stack is as you left it。But you're right。

 if you had multi threaded code and so forth。Other things should be happen。Yeah。

 and there's a balance to try to keep quiz questions。

It's the same over here right keep them simple and yet。Not worry about all the corner pieces，Good。



![](img/650fa1a3a59a819adf5f5c536691f11c_3.png)

啥。

![](img/650fa1a3a59a819adf5f5c536691f11c_5.png)

Okay， so let's talk about instruction level perism。Okay。So。Some jump to。All right。

 so this is sort of the modern CPU design under the covers， right？

Cash was just holding recent instructions。And so spec any of it to touch more instructions。

From that extraction cash you have。So the stream of distraction is being fed in the code。

That the code is determining。So for each instruction that gets decod。

 there's going to be some values to registers you're going to need and there's going to be some potentially。

 unless it's just like a move， there's going to be some operations register as you move。

 there's going to be some operations that be performed。Right， and so。

But there's sort of a pipeline of this going on， right。

 So you why you decode an instruction and you fire it off to。You know， say do an ad or something。

 The next instruction is being decoded and so forth， right so there's this whole。Pipline of things。

 this whole collection of things that could be happening in parallel。And the limits。

 there's a number of limits to this parallelism， and one of them is how many of these functional units you have and what type are they。

Okay， so in this diagram here， we're showing an architecture processor where you have one load unit and one store unit and three your arithmetic units and a branch unit。

And so what that means is that there's an opportunity here to do three arithmetic operations at the same time。

And as one another， as well as the same time you're firing off a load of memory and a stored of memory。

Okay。And trying to figure out some sort of brain， so there's this parallelism hidden inside these machines that you're trying to take advantage of。

Okay， so let's go back。Okay，Certainly the compiler itself needs to understand the number of function units and the restrictions on the function units。

On the process running on。And so and then do optimizations accordingly， but also you know as a user。

 you could be thinking about what's going to speed up your code based on knowing what things can happen at once。

And again， there are cases where。I mean， if the compile could do it for you。It's fabulous。

 you don't have to worry about it， it's actually more portable because the compiler can recompile for different architectures and so forth。

But if you're in one of these optimization blocker settings where there's something about your code that's preventing the pilot from figuring it out。

Then you can often help by doing simple transformations your code。

And we'll see a running example here。O。So let's suppose that we have this sort of a generic data structure for vectors that exists of a length and the data itself。

 so here's what it looks like。And you want to use it to hold integer vectors and lungs and floats and doubles。

 right？And now you have another function。That's going to take as an argument。

 one of these vectors and then an index into that vector。

 and it's going to store into this where the value of that。Vor at that index into this。

Into this location， okay， so again， if you give it an index off that's too high。

 it's going to return zero， otherwise it's going to return one and the value at that position。

Is put into that location for you。So given that we have that， so that's called get vector element。

Okay， so we have this type， we have Get Beck your own。Now we have this combined operation。

 which you want to use as sort of a generic way to compute both either a sum or a product of vectors of any of these different types。

ok。So in order to do that， what you do is you have sort of an identity。So for instance。

 if the operation I'm passing is a plus。The identity is zero。

 you start from zero when you're aumulating at it。On the other hand， if the operations at times。

Then I'm going to start from one， right， because then one times what， it all works out。All right。

 and then I just wanted to the elements， I get each element one at a time。

And then I add it into this running。Accumulation is the sum of the book。Okay， now when I'm done。

 the actual thing is in the right place。So now we're going to run this and we're going to account for the number of cycles that it takes to。

To perform so have the notion of a CPU cycles relevant for for each element of the vector。

Each operation when I perform， we want to know how many cycles of this。

 and then the sort of the time is just the。How much time you're spending per element。

 how much the number of elements， plus some fixed overheads for starting and stock and wrapping up？

And so another way to think about that is that the CPU is the slope of the line。So here。

 if I'm spending nine operations。For element。Then the slope is going to be nine， but if on the other。

 they only spend six， the slope is going to be six right。

And the x axis here is the number of elements in the vector。这就全晰的。All right。

 so we'll see how it does。So again， this is our code。

 and now we look at the four different data types。We have integer or four the possible data two possible data types in both operations。

 so we have the integers and the double precision floating point。

 and we do both the add and the multiplly in each case。If we just do this。

 if we just time this procedure unoptimize。Then thecyclists per element are in the 20s range， right？

If we run optimization level one， then they cut in half and if we run optimization level three。

 then they sort of cut in some in half again。Okay。So the。

 the types of optimizations are some of the ones we've seen before， right， so we don't want to store。

Every time through the loop， so we want to use a temporary to accumulate as we did in our earlier example。

Right， earlier in the class。All right， and so anything else in the length。Again。

 we want to pull that out once a all。And I'll not have to recalculate that。Okay。

And sort of the address calculation， well what we care about is where does that vector start and then we're just able to do calculations that are offsets of that。

Okay， so it moves things out of loop you don't need and avoids sort of the bound check on every single cycle and it does accumulate in temperature。

So if we do that and we compare that to say that just the opposite is one that we had before。Then。

You can see that's significantly faster， right？And it's even faster than the opposition level three of the old procedure。

Right， sorry I already涉 you that。嗯。So again， this whole use of this parallelism。

The instruction of app parallelism。Is。In this case， mostly hidden from the C programmer。

 but if you know about it， then you can sort of set up your code to help the compiler take use。Okay。

 so continuing along this same example， the other thing that happens is pipeline。

I mentioned there was sort of pipelining of decoding structures， executing structures， and so forth。

But if you have an expensive operation like integer multiply。Or floating point multiplly。

 and it's going to take some number of cycles to get it through。Then again。

 that's broken up into itself a pipeline。Okay， I'll say very stages。

And then if you have something like this code here where you're multiplying a by times B and a times C。

Then you can get a times B into stage one of your multiplier， and then when it moves on to stage two。

 you actually can start up a times C。可以， and so forth。So these two things can happen lock said。

 if you had a times D， you could have started here and you could get this nice perfect pipeline right So why the laency of a multiplication would still be three cycles。

Because of the three stages， the throughput could be one。

 right because you'd be starting a new multiplication every single second。Now。

 here's the example though， where we stall and we couldn't start that until cycle 5。 So why was that？

Yes。All right， yep， this is the result of this one and this is the result of this one， okay？So the。

 the， the。So the pilotlor has to take in your account as well。应开始。

It has to determine where the dependencies are， and it can't start scheduling。An operation of its。

It's。The things it depends on are also。So in particular， the Haswell CPU has eight functional units。

Two loads， one store， four integer， two floating point multiply。

 one floating point add and one floating point double。It it has this。啊。Latencies， so for instance。

 a loader store could take four。Intergen multiply  three as we've seen。

 but because you could pipeline those energyergen multiplies as we've seen at the throughput。

Is actually one， okay， I mean， the cycle ratio is actually one。

So if you have three energy multiplies you could do at the same time。

 then you know in a continued pipeline fashion， then it actually。

 there's no sort of loss in performance。Okay， it same things with loads， for instance， right。

 So even though it might take you four cycles to load something from the cash。

The hardware is equipped。With a way to sort of queuee up these loads and pipeline it all through。

 so you actually get return load。If you have 400 loads， you can get them back in。Well， three cycles。

 the four cycles get the first one， but then the ones after that come fifth。

 sixth seventh cycle after that right so again， the sort of throughput is very good。

And then you have things like integer or long divide， basically the divides that are just costly。

 know， they're not pipelineable， they're just costly。Okay。

So you unless you get away with with shifts by powers of two， you do your division tends to be。

Very expensive。Okay， so。Getting back to our combined four。What we see here is that the。

We had these numbers here from the previous slide。And if you just look at the la seabound。

 you see we're actually doing very well in terms of。The multiultiply add and integer multiply。

 but not quite so well in terms of inger add。Okay。And one of the issues here is that the way we're accumulating right so remember we're in each of these whether's out or whatever。

We're one by one sort of accumulating in the next element in the vector。Okay。

 and so this is a whole bunch of zero dependencies and that's why we don't see this pipeline right。

 we're saying oh，' it's like the the case of the。That third instruction we had to wait for right so because we have to wait。

Because this is one of the inputs。Here， it one of the inputs this multiply。

 We have to wait for this to finish。Okay。But。You know， if this is a sort of integer， for instance。

 we know that multiplication is soci， so we don't have to do it this way。はい。So in particular。

 if we do what's called loop unrolling。Where you step through a loop。Not one at a time。

 but two at a time。 and of course， if it ends up being an odd number。

 you have to do that last odd case here。 so that's what that is the if limit is an odd number。

And you have to do sorry， then you have to do that one last case。Or length all， but in general。

 you'll be doing two at a time。Now。And so what you're going to do is you're going accumulate the first one in the second one。

So that's not that much helpful because you still have this serialro dependency。

And if you look at it， it didn't really help at all。It helped in the ad。Okay， you got down from 1。

27 to 1。01， but you're still serializing。Okay。So the trick here is to just associate it the other way。

 right？Okay， so now I can start to compute。You know， this value without having to， I could start。

So here I had this operation dependented on it waiting for this to finish。

Here I can do this operation first and then accumulate the results。When I do that I。

And I realized I have these extra。呃，放ction院。Then' you know my laency hasn't approved。

 but now if I look at my throughput， like how many of them are getting cranked through it at a time。

It's better， right， so it's gone from five to two and a half。Okay， so it's cut in half。

Because I have these two functions， I'm able to run them both in parallel。And I get it that。

Now the goal would be this green fill here right because that would say。

 let's see how many function units I have。 And if I could keep them all cranked up full steam。

 then I could achieve this bound here。 So we're still pretty far from that right we're factor five here。

One and a half。And清楚 okay。嗯。Yeah， so this is just showing how you've reduced the serial dependencies。

So that there's only n over two of them， the length of this long has changed over n over two。

And so that cuts it down。嗯。So the next trick is to instead of trying to。

Accumulated into this one running sound。Okay。Since we' sort of let's accumulate all the odd ones and accumulate all the even ones separately。

Okay， so that's what this is you。 So this is sort of the。

And one has the even ones and one has the odd ones。in their own little tempers。

 and then only at the end do multiply the accumulateative result of the odd versus the cuative result of n of the even。

 So the answer ends up being exactly the same。But when we do that。We see that。

There's some further advantage that we got。And the ad， but not the other ones。Okay。

 and it's because the ad has。The energy plus is able to make use of the two load units。Okay。

So what can we do now？So in general， you have this trade off space right so do you can unroll the loop to n degree L。

 we were just unrolling it two， right I could do unroll three or four or whatever。

And you can also accumulate some number of results in parallel。And if you do that。

 then you see interesting things like this， that there's basically some sweet spots。

So if you look at floating pole multiply， you see unrolling by 10。

Andccumulating intent leads to the fastest result。Okay， so up here。

 we were looking at this number two and two。And you can do better by。But in this case， choose a tent。

对。So there's no reason to know， maybe offhand。Without steering a lot of the architecture。

 which would be the best， but you could certainly try out different combinations in your code and see what works the。

哎 questions在哪？Okay， energy addition is a slightly different choice。

 it's eight and eight is the optimal。Okay。And you can see that in the end， when we do this。

We're actually very darn close to the。Through pre in all cases。系。

So we've managed to milk out of the machine all the performance that was there to be obtained and this again。

 these were limited。These two numbers are derived basically by the function units you have and the properties open。

And there's just  up to 42 x improvement over the digital code。OK， so any question系上来。嗨。

So in a previous class， we talked about these。Longer red shoes that we have for doing。

See instructions。Okay。嗯。So the earlier versions were there were the XMM registers。

 these are the YMM registers。There are with more recent versions of the Intel architecture。

There are 16 of them in total， they each have 32 bys， they're 30 bytes long。Now， if you remember。

 the thing we said about from this that either you can treat them as a bunch of smaller registers and then apply sort of data parallel vector kind of operations on them。

Okay， so again， for instance， view them as。As consisting of 8，32 bit integers。

 and then if I apply one of these S operations on them， I could do eight things in parallel。

OkayOr I can eight single precision floats， I can do eight things in parallel。

Or if I went down with precision， I could go for court and pay and so forth。Okay。

 and so the Sdi operations again work。Just within each of the segments。

And the way the suffix of the instruction。It indicatesates which version you're using。

 are you thinking these as you know。Is 8， 32 things or 16，1616 by the 165 things and so forth？系 okay。

So。Again， we're not going to deal with the Cindy instructions in this class。

 but just to let you know that it allows you to beat things like this throughput down because now you know it's still a single。

Multiply or whatever， but it's now across a whole bunch of these things at once and the same instructions。

And so the actual bound you can get is even better。

 that you can get a throughput bound of another factor of  eight。Here。

 because I could do this operations on8 integers at once。 who's in these S regiistries， right。

So there's all sorts of tricks that can be played。他是个的。Okay， so the last topic is about branches。嗯。

So in order to get all this perilism and keep all these pipelines full and so forth。

The instruction decode。Needs to sort of run ahead of what everything else is doing and so you want to be speculating on what instructions are going to be executed by the program。

Well in advance of when you execute them so you can start to fill all these pipelines。嗯。

So the problem is conditional branches right so I'm when I get to a branch that I'm not sure which path it's going to take。

Then I don't know where to keep fetching， I mean do I like in this one here， I have two choices。

 one is I can assume the branch won't be taken and then I can just start fetching all these guys。

 or I can assume it will be taken and I can fetch from here。Great。And again。

 the point is I'm trying to make this decision long before this instruction is even executed。

So I don't know which way that breach is going to go。All right， so seen that already。

I sure that so so they's sort of always going to be sort of the branch's not taking path and the branch's taking path。

So what do processors do well they try to predict？😡，Okay， and they have some。

Ruleles of strength for how they predict。And if they get it wrong， then they have to。

 have the ability to squash all the computation thats in flight。啊，在对价过。

And then we'll back and start again right from that point。

So it's not- it doesn't lead to incorrectness because the processors build all this additional hardware circuitry in it to handle the speculation of the state and the squashing of the state and the rollback and so forth。

But it' it's a it's。The program slows up because instead of having this nice stream of things you're doing because you're running way ahead。

 you not only wasted all this work， now you've got to jump back and cold start this whole pipeline again。

So it's very noticeably painful in the phmacy case。So a good example is always a loop。So here。

 if you think about it， if I have a move。Then， if I loop through something。You know， end times。

And then I drop out of do。If I always predict that I'm going to loop back， I'm going to be right。

You know， all at one time。So that's what they do。Okay。

 so by predicting that the loop will always continue to execute， then you're only wrong once。

 which is good， and so this is an example where you're showing okay。

 you're correct correct correct and eventuallyre going to be wrong。

And you're going to have to squash and all that code and squash its effects and restart。成。

Any questions on？Branchches and branches。 So that's the loops。 like if， if， if， then else。

 kinds of things。啊。generaleneral， it's Harry， the processor has tables inside it where it tries to keep track。

They're called branch prediction tables， we trying to keep track of。

For every single place in the code where there's a branch， what was the most common thing it did。

 you， did the branch or not， and then use those to predict。

So it kind of learns as the program is executing。How things are are。

What's the better choice then of the outring？And so as a result。

 you get at least 95% accuracy in these things。So that's good， but you will see the hiccups at。

If you have code that doesn't allow for good branch prediction， in particular。

 in combination with these big wide semi instructions， so you're actually wasting a lot of work。

Yes are there ways to explicitly structure the st code to make？诶。我要一。

So this gives you a clue so before。The default that will be assumed before the processor has any history of this branch is that。

Is， is that。All， so is when you have an if。Then you predict that you don't take it。

 that you actually fall through。So， so if it's often like， you know， if the pointer is null。

 I'm going to do something else， the normal cases is， you know， if the pointer not null。

So if you have a choice of deciding whether to say， you know if pointer is null。

then do this else do that we saying if pointers not no。

 then you can help the system by making sure that the common case is the fall through。

 not the braintking。对。Okay， so sort of to summarize the you want to watch out for this hidden algorithm that inefencies？

That。Like the the stir L， which is doing this。Calculation， this n squared calculation。

 we didn't think about it doing that。You want to watch out for opposition blockers。

 try to do things that arere going to。嗯。Help the compiler like use temporary and they don't worry about a。

You know， we spent a lot of time optimizing this innermost loop。Of this function。

That's where most of the work is done， so that's where a lot of effort is often spent。Where else。

Yeah， instruction level parallelism。Knowing the number of。Fction is again。

 the compiler will try to do this for you， but if you do things that aren't。

You compiler friendly to make it stuck。And oh and we'll talk later about making code。

 writing code that's CPU cash friendly， so get more cash。OK， that's basically。



![](img/650fa1a3a59a819adf5f5c536691f11c_7.png)

![](img/650fa1a3a59a819adf5f5c536691f11c_8.png)