# 哈佛大学《计算机科学导论｜CS50 introduction to computer science 2025 Fall》 - P3：CS50 Fall 2025 - Lecture 2 - Arrays .cut.zh_en - GPT中英字幕课程资源 - BV1S8sFzFEt7

1 fish。2 fish。Red fish。Blue fish。Congratulations， today is your day。 You're off to great places。

 You're off in away。😊，It was a bright， cold day in April， and the clocks were striking 13。

 Winston Smith， his chin nuled into his breast in an effort to escape the vile wind。

 slipped quickly through the glass doors of victory mansions。

 though not quickly enough to prevent a swirl of grdy dust from entering along with him。Alright。

 this is C， S 15。 And this is week 2。 And if we could， after this dramatic reading。

 a round of applause for our volunteer。😊，So we can now take for granted from week1 that we now have a new way to express some of the ideas that we first explored in week 0。

 like functions and conditionals and variables and the like。

 And now we're doing in see what we used to do in scratch。 Today。

 where we're gonna start to focus on is some real world problems so that we can take for granted that we have that expressiveness。

 We have some tools in our toolkit and actually start to solve some real world problems if representative thereof in particular。

 the real world problem we're gonna start today and this week with is that of reading levels。

 odds are when growing up， you read at a certain level based on the age at which you were at maybe it was first grade level or fifth grade level or 10th grade level or the like。

 And that was a function of just how comfortable you were with the words in the book or words on the screen that you were reading what you've just heard thanks to our volunteers are three different reading levels that each of these three volunteers reads at。

 And in fact， why don't we go ahead and hear them again and be a little more thoughtful this time as to assess at what reading level your classmate is reading。

 So let's start with Le if you'd like to introduce yourself。😊，FirstH I'm Leah。

 I'm a first year in wholeworthy and here is my little thing。1 fish，2 fish， red fish， blue fish。

 So whats reading level would you say， Leah reads based on his recitation thereof。 Yeah。

 in the front。Kinergarten kindergarten， okay， so a fairly young age and what makes you say kindergarten。

Is speaking in very short phrases without much。Okay， very short phrases without much complexity。

 And indeed， according to one scientific measure that we'll explore in this week's problem that indeed。

 we would say that Leah reads before grade1。 So kindergarten would indeed be at。

 But welcome to the stage here。 Let's move on now to Maria。 if you'd like to introduce yourself。

 Yeah， hi， I'm Maria。 I'm in Stoughton thinking of applied math。 Congratulations。 Today is your day。

 You're off to great places， You're off and away。 Another familiar phrase。

 perhaps at what reading level would you say Maria is。😊，Yeah， over here。

And what makes you say second or third grade？O。So now we're starting to introduce complexities like rhyming in a bit more substance to the quote。

 And indeed， based on that reading that same measure that I described earlier。

 which will involve a mathematical function that somehow analyzes what it is Maria just said。 Indeed。

 we would conclude that she read at a third grade level or grade3。 Finally， Omar。

 if you'd like to introduce yourself and read once more yours。 Okay so hi， everyone。 I'm Omar。

 I'm a freshman at hurl， but thinking of doing compai。 And this is my reading。😊。

It was a bright cold day in April， and the clocks were striking 13。 Winston Smith。

 his chin nozzled into his breast and an effort to escape the vile wind。

 slipped quickly through the glass doors of victory mansions。

 though not quickly enough to prevent this swirl of gritty dust from entering along with him。

 So of escalated quickly。 What reading level is Omar at， would you say。Someone else。

What might you say or estimate？Yes， right here in the front。Okay， eighth grade。

 and what made you say that？More complex sentences， more complex words。 And indeed。

 according to that same measure， this full paragraph of text now。

 which indeed has even more grammar when you see it there are on the screen。

 would be said to be at grade 10 because of that added complexity。 So with that said。

 we're going to need to be able to somehow sort of crunch these numbers to determine given a body of text at what reading level someone is。

 But in order to do that and apply any metrics to a body of text。

 we're gonna need to represent that text in memory using something like strings from last week。

 But last week with strings， we could really just print them out or display them wholesale on the screen。

 But I think we're going need to break down these various text and others like it at a finer grain level。

 And indeed， among the goals for today is to explore exactly that and also to take the proverbial hood hood off of the car to take a look underneath。

 And how the computer is actually working， how these things like strings are actually functioning。

 So if you could join me one last time in a round of applause for our volunteers。

 Thank you so much for helping out。 Thank Thank you。😊，Thank you to Maria as well。

 So among the goals for today， beyond exploring a representative problem like this of reading levels。

 is going be another one， which is even more important and more omnipresent than reading levels namely cryptography。

 the art of scrambling information or specifically encrypting it。

 so you can send secure communications Now you sort of take this for granted increasingly nowadays。

 that when you send a text message or perhaps an email or check out online with a credit card that somehow or other your information is secure and over the coming weeks。

 we're going to explore to what extent that is actually true and why or why now Now。

 with cryptography， similarly too， if we want to be able to send messages securely such that if I want to send a message to you。

 I don't want anyone else in the room to be able to figure out what it is I have said。

 even if they physically intercept that message， which is all too possible in a digital world。

 we're going to need to come up with metrics and mechanisms for actually scrambling information in a reversible way。

So that I can write my message， somehow scramble it。

 you can receive that message even if after it's passed through many other hands and you can deccrable or decrypt that same message。

 So for instance， here on the screen is a message， a fairly simplistic one that has somehow been encrypted and we'll see by the end of today and by the end of this week that this encrypted message and there's a bit of a tell on the end there actually will be said to decrypt to this is CS 50 but why is going to be the underlying question and what additional tools do we need on our toolkit in order to do that。

😡，Another word on tool。 So up until now， you've probably experienced some bugs。

 whether it was in scratch or ever more so in C。 In fact。

 don't feel too bad if like the very first program you wrote in C like didn't even work。

 You couldn't even make it or compile it until you went back and fixed some of the code that you had written。

 Well， it turns out that bugs， mistakes in programs are ever so commonplace。

 And even though we've already provided you with tools like the virtual rubber duck at C50 AI also embedded into VS code at C50 of whom you can ask questions along the way among the goals today or is to give you some lifelong tools at how you can actually debug software yourself when you don't have a duck nearby when you don't have a T A nearby。

 let alone any humans at all。 So with debugging， there's gonna to be a number of techniques that we can use all toward an end of like finding and removing bugs or mistakes from our software and perhaps the person best known for having popularized this term of bugs is that of Dr Grace Hopper pictured here。

 who was a rear amiral in the Navy and was one of the original programmer。

Of the so-called Harvard Mark1， a very early mainframe computer that if you wander across the Charles River over to the science and engineering complex here at Harvard。

 you can actually see part of this on display still in the lobby。

 it was succeeded by the Harvard Mark 2 and on the Harvard Mark2， Dr。

 Hopper and her team We're known for having put this note in their log book after having done some number crunching on the system there。

 And if we zoom in theyve found a problem with the computer this one day。

 whereby there was literally a bug a moth inside of the circuitry of the computer And as was written here。

 First actual case of bug being found。 And ever since then do we say ever more so。

 the phrase bug in debugging when it comes to finding and eliminating problems in our code。

 So let's start with just that， In fact， let me go over to V S code and let's deliberately make some mistakes together that might very well be reminiscent of some of the mistakes you've accidentally made thus far。

 But along the way， give you all the more tools for solving those problems as opposed to sort of having to ask someone else。

Be it virtual or physical for help and actually find these mistakes in your own code。

 Let me go ahead and consciously in V S code， create a program known to be buggy called buggy dot C。

 And in this program， let's go ahead and do some fairly familiar code initially。

 I'm gonna go ahead and start just like we did last week with in main void more on that today before long inside of my curly braces。

 I'm gonna say printf。 Hello comma world。 That's it。

 Now I'm gonna go back to my terminal window here， I'm gonna go ahead and do make buggy to make a program from that source code。

 But before I do odds are even after just a week of this stuff， you can probably spot a few mistakes。

 I've made a few bugs。 What do you see wrong already。 yeah。😊，I didn't include standard I O dot H。

 That's so calledled header file， which is important because it tells the compiler that I plan to use functions therein like printf。

 which clearly I'm doing。 So let me go in and include standard I O dot H。

 What else seems to be wrong here， yeah。I'm missing a semico at the end of line 5 here。

 So I'm gonna go ahead and add that in。 And this is subtle and arguably not a bug。

 but maybe an aesthetic detail。 What else have I done arguably wrong， again， back。Yeah。

 I forgot my backslash and the new line character just to move the cursor to the next line so that when I get a new prompt。

 it's on a fresh line of its own。 again， more of an aesthetic。

 but certainly a pretty reasonable thing to do。 So let me go ahead now and actually in my terminal window run make buggy and it indeed compiled。

 But up until then had I not fix those mistakes。 I would have triggered a whole bunch of bugs。

 a whole bunch of error messages as a result。 In fact。

 let's rewind in time and undo the fixes I just made and go back to the original form here and try running again。

 make buggy enter。 and we'll see some scary looking messages up here。

 Let me scroll up to the top of the output here where we see buggy dot C colon 3， which means line 3。

 that's where the problem is right now。 error call to undeclared library function。

 printf with type and then it starts to get a little more complicated。

 But I do see clearly that it's calling my attention to printf。 So hopefully at some point。

 if not last week， hopefully this week onward， your instinct will be。

 I' I forgot the header file in which print。I actually declared。 It's not a huge deal。

 It's gonna come with practice。 So that's how I might know in more intuitively， what， in fact。

 the solution here might be。 Now， here's another common mistake that I've just gone in and fix。

 But I did do something wrong。 And hopefully none of you actually did this。

 because it's an annual FA AQ。 What did I just do accidentally wrong。So it's not studio dot H。

 It's standard I O dot H。 So do kind of ingrain that one for standard input output。

 The next though bug that I haven't yet fixed is that semicolon。

 So let me clear my screen and rerun make buggy。 I should no longer see that first error message anymore。

 But I now do see another error message online 5 expected semicolon after expression。

 that one's pretty explicit。 So I'm gonna go ahead and fix this。 But notice that up until now。

 my code hasn't even compiled。 if I type in L S。 although I had run it once before。

 up until now my code wouldn't have been able to compile because of those two error messages。

 It stopped showing me by showing me these error。 But at this point。

 if I run make buggy enter it did， in fact， compile。

 And yet it's arguably still buggy because when I run dot s buggy， I get my prompt on the wrong line。

 So this is a distinction now between a syntax error。

 something that or a programming error that outright stops my program from compiling。

 it's sort of a deal break。Versus something that's maybe more of a logical error。

 I actually meant to move the cursor to the next line。

 And so there's different types of errors in the world as we're seeing here。 Of course， if I rerun。

 make buggy again dot slash buggy。 Now we're back in business。

 Hopefully with the intention of having this display exactly that。 Allright， well。

 let's modify to look a little more like something else from last week。 recall that last week。

 I started to get someone's name more dynamically。 So I said something like name equals get string。

 And that was a function we introduced。 And I might have said something like this。

 What's your name question mark with a space just to move the cursor over。

 I know now I definitely need to end my thought with a semicolon。

 I could try and compile this make buggy now， And I'm seeing a different error message altogether that you might not have seen yet。

 So on buggy dot C line 5 error use of undeclared identifier name。

What now is the mistake that I've made。 Why does it not know。Yeah。

 I forgot to declare the type of this variable， which for those of you with the prior programming experience is not something you have to do in some languages like Python。

 for instance， but in languages like C， C plus plus Java and others， you do， in fact。

 need to explicitly tell the compiler that you want to instantiate a variable。

 create a variable in the computer's memory by telling it its type。

 And it's not gonna be an int because I don't want an integer， of course， in this case， I want text。

 which we now know to be called string instead。 Allright， I think this fixes that bug。

 So let me do make buggy again And hopefully a fatal error this time， again。

 indicating that my code did not recompile On line 5 still， I have an error。 But this time。

 it says use of undeclared identifier string。 did I mean standard in。

 So this is a bit of a red herring。 The compiler is trying to be helpful and saying did I mean standard in。

😊，But I don't think I actually do。 That just is the most similar looking word in the compiler's own memory。

 What's the actual mistake that I've made here， yeah。Yeah。

 I didn't include the CS50 header file because string recall is a feature of the C S 50 library。

 as is get string and get int and others。 So the solution here is indeed to go up here。

 and just to be nitpicky。 I tend to alphabetize my header files。

 It's not strictly required technically， but styllistically I find it nice to be able to skim the header files alphabetically to see if something is there or not。

 I can include C 50 H in addition to standard I O do H。 And it's in that file。

 C50 do H that not only is get string declared so that the compiler knows that it exists。

 it turns out so is the word string。 So this is a bit of a white lie。

 And this is something we do in the early weeks of the class。

 we dug up these old training wheels from a bicycle。

 The whole idea being to keep you up and avoid you having to do too much complexity early on。

 The point of these training wheels in the form of the C 50 library is to let us kind of ignore what a string really is for just another week or two。

 after which we will then peel back that layer。😊，Those training wheels and reveal to you what is actually going on。

 So for now， strings exist， but they exist because of the C 50 library in a couple of weeks。

 they're still gonna exist， but we're gonna call them by a different name， as we'll eventually see。

 But everyone in the real world， every software developer uses the phrase string。

 So this is a concept that exists， it is not C 50 specific at all。 It's just that in C。

 the word string doesn't typically exist， unless you make it so as we have。 Allright， so I think now。

 if I clear my terminal window。And rerun， make buggy。 Now， it should， in fact， compile。

 And if I run dot slash buggy enter， I should be able to type in my name。 And now，voila， hello。

So this is now not a syntax error because I didn't screw up my code per se like it compiled。

 Everything is grammatically correct。 So to speak， but logically intellectually。

 this is not what I wanted， right， I wanted it presumably to say， hello， comma David。

 So let's fix one final bug here。 How do I fix this on what line。How do I get it to say， yeah， hello。

 David？Yeah， on line 7， I need to do the string placeholder， the format code。 So to speak percent S。

 And then one more thing， someone else， What do I do after this。Yeah， and back。Yeah， a comma。

 and then add the variable name that contains the value I want to substitute in there。

 which is indeed name， though I could have called it anything I want。 Allright。

 so now make buggy enter seems to have compiled again dot slash buggy Now I type in my name once more。

 And now we're back in business。 So over the course of these few exercises。

 clearly I meant to make most of all of these bugs， these mistakes。

 But they demonstrate not only syntax errors， which are just going stop the compiler in its tracks。

 like you won't even be able to compile your code until you fix those things。 But even after that。

 there could be these latent bugs that seem to not be there until you actually provide input and see what's actually happening at socalled runtime when you're running the actual code。

 And so here's where it's no longer as easy as just reading the error message and figuring out what it means。

 because there is no error message that appeared on the screen when it said hello comma world。

 We had to use our own human intellect and realize， okay， that's clearly not what I wanted。

 had you run C5's own check 50 programs。On something like that。

 we could have told you that that's not correct by automatically assessing the correctness of it。

 but the compiler has no idea what you are trying to achieve logically。

 It only knows about the language C itself and the requisite syntax for actually writing and compiling code。

 So how could we go about solving logical problems in code。

 So I would propose that we start to consider this here list whereby when you want to find a logical problem in your code and better understand what's going on or really what's going wrong。

 printf is going to be your friend up until now we've used printf to literally print on the screen。

 Hello， David， Hello， Kelly or anything else on the screen。

 But you can certainly use printf temporarily to just print stuff out inside of your program that you might want to better understand。

 And then once you understand it。 And once youve solve some problem。 fine。

 then you can delete those temporary lines of code， recompile and move on。

 So let's use printf as a debugging tool。In that sense。

 let me go back over to V S code here and let me in this same program。 Bugy dot C。

 sort of delete everything and start over with a different sort of bug。

 I'm going to include standard I O dot H at the top， I'm going do int main void after that。

 And inside main， I'm gonna do a simple four loop that just prints out like a stack of three bricks。

 like we saw in the world of Mario when Mario needed to。

 we claimed sort of jump over a stack of bricks。 We want to print out just three of those at the moment。

 So I'm going to go ahead and say4 int I equals 0。 I is less than or equal to three because I want three of these。

 I plus plus then inside of this for loop。 I'm gonna to go ahead and quite simply do printf hash symbol to represent the brick followed by a new line to move the cursor to the next line。

 semicolon to complete the thought。 Now， I've deliberately made a stupid mistake here。

 But in the context of a simple enough program that we can focus on the debugging technique on not on the obscurity of the bug in。

😊，Hopefully， you'll spot the bug in just a moment if not already。

 When I do make buggy now and do dot slash buggy。 I don't get three bricks。 I， of course， get1，2，3。

4 total。 So there's a logical bug in this program and odds are you can already spot what it is。

 But let me propose that this program is representative of a type of problem that you can solve a little more diagnostically by poking around and really asking the computer via printf to show you what's really going on。

 And I would propose that one of the most helpful techniques in a situation like this。

 if you're trying to wrap your mind around why are there four bricks instead of three。 Well。

 clearly this is related to the loop somehow。 So let's look a little more thoughtfully at what the value of I is before we print out each of those bricks。

 And I might literally do something like this temporarily printf quote unquote I is percent I backlash N close And then I could just print right here and now the value of I just so that I can actually。

See it。 Let me now go down into my terminal window， make buggy again。 dot slash buggy。

 And now and I'll full screen my terminal。 I'll get some diagnostic information at the same time。

 So when I is1， I get a brick when I sorry， when I is 0， I get a brick。 When I is 1。

 I get another brick。 When I is 2， I get another brick。 when I is 3， I get a fourth brick。

 So now I can kind of see that okay， my loop is working， but I'm going too far。 I'm going too long。

 Now I can do this even more succinctly for what it's worth。

 I don't need a whole new printf statement， I could just go into my existing printf。

 put my percent I there。 and then maybe to space just to scooch things over。

 and then print out I in that same line。 if I now do make buggy dot slash buggy。 Okay。

 now I'm seeing that I'm printing a hash a brick for each value of I from I equals 0，1 to and also 3。

 So the solution， of course， is that I shouldn't be starting at 0 and iterating less than or equal to 3。

 the solution is like。An an idiot， I should have said less than three。

 or if I prefer to count starting at one， like a normal person。

 I could have said I equal to one and then go up to and through three。 But as I claim last week。

 the canonical way， the most common way to do this is start counting at zero and go up to。

 but not through the total value that you have in mind。😡。

But there's gonna be another technique that's worth knowing here。

 Let me go ahead and sort of abstract this away by whipping up a slightly better variant of this as follows。

 Let me go ahead and delete this for loop。 Let me assume for the moment that inside of main。

 I'm going to ask the user now for the height of a pyramid。 And I'm going do something like this。

 Int H equals get int。 and let's prompt the user for the height value of this pyramid or this wall。

 And then let's go ahead and assume there exists a function called print column who takes as input a number H。

 which is how many bricks you want to print。 Now， this function does not exist yet print column get in does exist。

 but I don't have access to it。 So let me not make the same mistake twice。 What do I need to add。

At the top of this file， yeah。I need the C 50 header file because I'm using the get int function now。

 which again， comes from our library， not C。 So let me go ahead and include C 50 dot H。

 but now print column。 I can invent this function myself。

 So let me go ahead and say void print column int height in parentheses More on that in just a moment。

 And then I'm gonna recreate the loop from before for int I equals0。

 I is less than or equal to the height。 I'm gonna deliberately for now。

 make that same mistake as before I plus plus and then inside of this four loop。

 I'm gonna go ahead and print out a single hash and a new line to represent that there brick。

 So now main can use a function called print column It's gonna pass in the value of H。

 And then this four loop in the print column function is gonna take care of printing this thing for me。

 So let me do this again。 make buggy enter So far so good dot slash buggy。 Let's in a height。

 I'm gonna say manually height of3。 And I should see three bricks。 But of course， I'm still seeing。😊。

Now， before we move on， let me hide my terminal and propose that this is just kind of stylistically bad to put anything other than your main function at the top。

 But recall that if I move my helper function print column。

 and it's a helper function insofar as I made it to help me solve another problem。

 I can't recompile and run my code now， why。The compiler won't let me， yeah。Exactly。

 when the compiler gets to line 7 of my code， it's going to abort compilation because it doesn't know what print column is。

 Why， because I don't tell it what it is until line 10。

 And this was the only time I propose that copy paste is reasonable。

 is to highlight and copy the very first line of that function paste it above main with a semicolon。

 And that's a so-called function prototype。 It specifies what the name of it is what its inputs are。

 if any and what its output is， if any。 and more on these inputs and outputs later on。

 But now this is just a more complicated， but more modularized version of the same program。

 Let me do make buggy still compiles dot slash buggy type in3。 and I still have that same bug。

 But the catch now is that my code is gotten more complicated。

 And the point of my having abstracted away。 This idea of printing a column into a new function。

 is that there's just more code now to debug。 I could certainly go in there and start adding printfs。

 But at some point， printf is gonna be a very primitive。

And you're gonna waste more time adding printfs， recompiling your code， running your code。

 changing the printf， recompiling your code， running your code。

 It's gonna get very tedious quickly when you have lots of lines of code on the screen。

 So can I actually step through my code line by line。

 maybe like your T A would in a section or a small class line by line， walking through the code。

 you can， because another tool that you have access to。😊，Is that called debug 50。

 So this is a C S 50 command that will start an industry standard debugger and a debugger is a piece of software that is used in the real world that literally lets you do that。

 debug your code by letting you slow down or even pause execution and walk through execution of your code line by line。

 The only reason we call it debug 50 is because in V S code。

 it's a little annoying to start the debuer。 And so we automated the process of starting the debugger。

 but everything thereafter has nothing to do with C 50 and everything to do with real worldor software engineering techniques。

 So how do we use this。 Let me go back to V S code here。

 And let me propose that I want to step through this code line by line。

 just like we might at a whiteboard in a smaller class to figure out why I'm getting4 instead of three hashes。

 Well， in my terminal window。 What I'm going go ahead and do is this。 debug 50 space dot slash buggy。

 So debug 50 is the command。 It needs to know what program I want to debug。 So I'm。

Specifying dot slash buggy， which is the name of the program I just compiled。

 I'm gonna get an error though， the first time I run this as will you if you make this same mistake。

 I'm about to see this message here。 Look like you haven't set any break points。

 set at least one break point by clicking to the left of a line number and then rerun debug 50。

 So what is this really telling me， Well， the debugger has no idea when and where I want to pause execution。

 So is to start walking through my code line by line。 It wants me to tell it where to break。

 That is where to pause by clicking on a line number。 So let me hide my terminal for just a moment。

 And you've probably never done this intentionally。

 But if you hover over the space to the left of your program's line numbers。

 you'll see a little red dot， a little stop sign of sorts。 If you actually click on a line number。

 that red dot will stay there。 And you can see the hover here saying click to add breakpoint。

 What I'm gonna to go ahead and do is say click to add a break point at main。

 main is the entry point to my program。 It's the default function that gets called。

 let's break right away。 So I can step through this code line by line。



![](img/40cfbb95e7fe840f46b181fa68459398_1.png)

Alright， let me reopen my terminal window and clear it and then run debug 50 again with dot slash buggy enter。

 And now a whole bunch of stuff is gonna happen quickly on the screen。

 And then it's gonna clean itself up because once the debugger is running and ready to go。

 It's going to allow me to start stepping through my code line by line。 So what is going on。 Well。

 notice nothing has happened in the terminal yet。 Why。

 because my code has been paused inside of main。 in particular。

 it's been paused in the first real line of code。 So the curly brace is uninteresting。

 the first line is just the functions name， essentially。

 So line 8 is the first juicy line of code that could possibly do anything useful。

 It's been highlighted here in yellow。 and that the fact that this cursor is here means that we have broken execution on this line。

 but we have not yet executed this line， which is why in the terminal， I don't see anything yet。

 I definitely don't see height followed by colon。 Not what else has happened here。

 All of a sudden in the left hand side of the screen where your file Exper。😊。



![](img/40cfbb95e7fe840f46b181fa68459398_3.png)

Typically is or where the C 50 duck typically is。 we see mention of variables。

 You can actually see inside of the debugger what the value of any variable in the computer's memory happens to be。

 Now， I don't quite understand this right now。 will come back to this over time。

 but weirdly before line 8 even executes。 It seems that H has a default value of 32764 which seems to have come from nowhere as an aside。

 This is going be what's called a garbage value。 And this is actually why we have Oscar so omnipresently here。

 a garbage value tends to be a default value inside of a variable。

 That's the result of that memory having been used previously for something else。

 inside of your computer。 you've got all of this memory。

 random access memory or Ram more on that today。 And it stands to reason that my computer or whatever cloud server we're using has been running for some time。

 So the bits that H is going to use。 might already have some random switches on and off some random pattern of bits that happens to give me 32764。

😊，But the moment this line of code executes that value is gonna to get changed to what I actually want it to be。

 which is what the human is going to type in。 Meanwhile， at the bottom here。

 you'll see a socalled call stack more on this too in the weeks to come。

 but you'll see that we've paused on the function called main in the file called buggy dot C。

 So how do I do something useful。 Well at the very top of the debugger。

 you'll see a whole bunch of color coded icon。 One looks like a play button。 And if I click that。

 it's just gonna continue execution of my code as though I don't want to step through it anymore。

 So I'm not gonna click that just yet。 The second arrow。

 which is a little curved arrow over a dot is the so-called step over line。

 which will mean step over this line and execute it， but only one line at a time。

Let's go ahead and do exactly that。 So I'm gonna click the step over icon， the second one。

 which is the curved arrow with the dot under it。 Click。

 Now I see in my terminal window height being prompted。 Alright， let's go ahead and type in 3。

 just like I did before and hit enter。 Now notice what happens， execution has paused online line 9。

 instead of 8。 And you'll see that my variable， a socalled local variable has the value of 3 as intended。

 Allright， so far， this isn't all that enlightening other than demonstrative of the fact that I can pause execution of my program anytime I want。

 So let's now click that step over button again， so that we actually print this column。 click。

And there we have it。4 hashes at the bottom of the screen。 Now。

 execution is paused at the end of the function。 This is just my opportunity to either stop or restart or continue。

 I'm just gonna go ahead and click the play button and let it finish executing。 Unfortunately。

 that wasn't really at all enlightening except to confirm for me that I typed in3 and3 is what is in the computer's memory。

 Not that interesting though yet。 So let's do this， Let's leave the break point on line 6 as before。

 let's rerun the debugger by running debug 50 space dot slash buggy。 Let's let it do it start thing。

 which looks a little messy at first， But now we've highlighted line 8 again。

 I'm gonna go ahead and step over this line because I do want to get an int。

 I'm gonna type in3 again enter。 But this time， instead of stepping over line 9 and just letting print column happen。

 This is where the debugger gets powerful。 let me step into line 9。

 and walk through the print column function itself。 line by line。 So let me go ahead and click。😊。

NotThis button， which is the curved arrow over the dot， But the next one。

 which is the step into button click。And now you'll see that execution has jumped inside of print column and paused on line 14。

 at which point I can see at top left what the default value of I is。

 And this is some crazy garbage value， because whatever bits are being used to store Is value。

 have some random garbage from some previous use of that memory。

 But as soon as line 14 executes once， I bet I is gonna to take on a value of 0。 So let's do that。

 I'm gonna go ahead and click step over。😊，Becauseuse I don't need to step into this because there's no other functions there。

 Step over it。 And immediately at top left， I is now 0。 Now， line 16 is highlighted。

 Let's step over this。 Okay， and notice in the terminal window。 What do you see。

 The first of our hashes。 Let's step over， step over。 Second hash。 and I is now one。 step over。

 step over。 now we see a third hash and I is now 2。 step over， step over。 Okay。

 there's the symptom of the bug。4 hashes。 And yet， I is 3。 But wait a minute。

 this is gonna draw my attention now to line 14 before I continue on or wait a minute，3 is。

 of course， less than or equal to3， which is why I got that fourth hash on the screen。

 So at the end of the day， like， you still need to exercise some of your own human intellect to figure out and understand what's going on。

 But the value of this here debugger is that you can pause and work through things at your own pace and poke around inside of your own code and better understand what's happening as opposed to compiling the program running it and just now having to infer from the symptoms alone what the source of the problem might be。



![](img/40cfbb95e7fe840f46b181fa68459398_5.png)

So that was a lot。 Let me go ahead here and just let it continue to the end because I know what the problem is now。

 I need to change the less than to a or greater less than or equal to s to a simple less than instead。

Questions， though， on debu5if or any of these steps， yeah。是。😡，And then。Mmhm。😊，The second time。

Darment value。Correct， so in order of your questions， what again， are these breakpoint。

 the breakpoint or the little red stop sign here just tells the debugger where to pause execution。

 So frankly， I didn't have to pause execution at main。 if I really care about debugging print column。

 I could have clicked down here instead， and then it would have just run main automatically and only paused once print column gets called。

 So a break point is where your code will break the point at which it will break As for the garbage values。

 I I'm oversimplifying exactly what's going on inside of the computer's memory。

 And it's not necessarily using exactly the same memory as before。

 but the operating system will govern exactly how the memory is laid out。

 this is actually a significant problem， long story short and a lot of today's systems because it's not that interesting to me to know that there was 32000。

 whatever that number is or the negative number， but suppose that that revealed the password of someone。

 another programme or function。That had some information there。

 It seems all too easy with the debugger， let alone see to actually poke around the computer's memory。

 And we're going to come back to that in a couple of weeks。 But for now， it's a garbage value。

 Insofar as you didn't put the value there。 It somehow got there on its own for now， other questions。

売りたい。我ま。The next time。Correct， so the question is about the order of operations for a for loop。

 So the first time you go through a for loop， the initialization happens。

 the stuff before the first semicolon and the condition is actually checked， the Boolean expression。

 Then everything inside of the curly braces is executed。 Then the incration or update happens。

 which in this case is I plus plus And then the condition is again checked。 The Boolean expression。

 The code is executed。 The update happens。 The condition again， the code is updated。

 And so it starts to loop like this。 The debuggerss graphics are fairly simplistic。

 And it just highlights the whole line without making super clear what's happening。

 But that's just the definition of a for loop。😊，Good question。 Others about debug 50 or print de。

All呀。Can you change the position of I plus plus and height。 short answer no。

 The first thing is the initialization。 The variable you want to create and initialize。

 The second thing is the actual condition。 The so-called boolean expression。

 the third thing is always the update。 So it must come in this order。

 What you're not seeing is that you can actually have multiple Boolean expressions。

 You can have multiple initializations， you can have multiple updates。

 but we're keeping it simple for now。 And this is canonical。 Allright， so to make clear。

 assuming that either printf or debug 50 helped me figure out where the elog was in my thoughts。

 I now know that the fix here is to just go and change the less than or equal to to a simple less then。

 And if I run the program again， of course， it's gonna give me the three bricks that I always want instead。

 But there's other techniques we can use。 So besides printf and debug。

 you might wonder why we have a 7 foot duck behind me here。

 All of these little rubber ducks on the floor。 So rubber duck debugging per week 0 is actually thing。

 this was popularizing in a book some years ago。 And the idea is that when you are facing some bug some mistakes。

😊，In your program or you're just confused on some concept。

 There is anecdotal evidence to suggest that just talking out the problem with an inanimate object like a rubber duck on your desk is enough often for that proverbial like light bulb to go off over your head Because you hear in your own words。

 what confusion you're having what illogical thoughts you're having。

 and you don't even need another human or T A or AI in the room to answer the problem for you。

 So in fact， on the way out today at the end of class。

 we've got hundreds of ducks and enough for everyone to take home with you。

 if you'd like to use that as another debugging technique， whether in CS 50 or something else。

 But of course， now in the age of AI， you also have the AI powered virtual duck at C50 AI and also in VS code at C50 do。

 which really is a mechanism for asking questions that you don't think you can solve on your own。

 So it might be reasonable to ask the duck。 what does this error message mean if you're having trouble wrapping your mind around it。

 but it's less reasonable to say copy paste your code into the duck and say what's wrong with my code。

You should really be meeting the AI halfway。 After all。

 what's the point of actually doing this or any other class is to develop that muscle memory。

 develop those mental models， get some practical skills。

 So try hard to walk that line between asking the duck too much versus deploying some of these same tools yourself。

 print Fbug 50， even a physical rubber duck on your desk before you resort to sort of escalating it to human like or duck help。

Allright， so with those tools added to one's toolkit。

 let's actually consider and reveal what's been going on underneath the hood since last week。

 So this was the mental modelt we proposed for last week。

 whereby when you write source code in a language like C。

 It's not something that the computer itself understands natively because computers we saw only understand zeros and ones。

 Aka machine code so the compiler is the program that we use to convert your source code to the machines code from C to zeros in one in this case。

 More generally， a compiler is just a program that translates one language to another。

 And in this case， we're going from source code to machine code。

 So let's consider what's really happening。 And indeed。

 this is among the goals of this week is to take a look at a lower level so that when you encounter more interesting。

 more challenging problems。 you'll understand from so-called first principles。

 what the computer is actually doing and supposed to do so you can deductively figure things out for yourself and generally not view computers is like magic or I don't know。

😊，This works。 You'll have a fairly bottom up sense of how everything works by terms end inside of any computer。

 laptop， desktop phone or the like these days。 So here's the simplest of programs that we wrote last week。

 even though there's a lot of syntactic complexity as we've seen the goal is to get it to machine code these here zeros and ones。

 So how has that been happening when you just run make since last week。 Well。

 these are the two commands that we typically run after creating a file like hello do。

 we then compile with make hello， And then we run it with dot hello。

 So let's give ourselves this starting point real quick。

 just so that we have an example in mind of exactly what it is we're compiling。

 So let me go back to V S code here。 close out buggy dot C。

 And let's create a new file just like last week called hello do C inside of which is our old friend standard I O do H in main void。

 and then inside of this will keep it simple， just printing out hello comm world， which again。

 is my source code in C。 How do I now。😊，Actually compile that。 Well， of course。

 I can go down to my terminal window， make hello dot slash hello， and we're often running。😊。

So it was a bit of a white lie for me to let you think， though， that last week。

 the compiler itself is called make。 make is a command that literally makes your program。

 It makes it by compiling it， but make is not technically the compiler。

 we really want to get nitpicky。 the compiler you've been using is actually called clang for C language。

 And this is a very popular compiler freely available open source， so to speak。

 you can even look at the code other humans wrote to create the compiler online。

 And what make is really doing for us is essentially automating this command。

 So all this time I could have just run clang space。 hello do C。

 but the default file name from Kang the compiler weirdly and for historical reasons is not going be hello。

 as you would hope it's gonna be a dot out for asmbr output and we don't do this in the first in week one of the class because this just makes things unnecessarily complex that we're adding some random name that you just have to know to type。

 However， we can do this now as follows。Let me go back to VS code here。

Let me clear my terminal and type L S and we'll see everything we've created thus far。 buggy dot C。

 which when I compiled it， I got buggy and hello dot C， which I just wrote， and when I compiled it。

 I got hello， let's do this command now manually。 though let's use clang on hello dot C and hit enter That too seems to work。

 But if I now type L S， you'll see a third program specifically called a dot out。

 which happens to be the same as hello， it just is using the default name instead of my custom name hello。

 But if I do dot slash a dot out， indeed， that two will work。 But the reason we don't do that。

 certainly in the first week of the course， is that things get a little annoying or sort of escalate quickly thereafter。

 So let me go ahead and change this program as we've done a few times already。

 let me include see 50 do H so that we get access to like get string。

 let me do string name equals get string quote unquote what's your name。

 question mark close and then down here， just like before， let me add my percent S。😊，AddIn my name。

 So I did that super quickly。 But it's the same program we wrote a few minutes ago。

 and it's the same one we wrote last week。 What happens now， though， is as follows。

 If I now try to do clang hellello dot C enter， I actually get an error message。 This one。

 perhaps more cryptic than most。 somehow or other， I have this error。

 Lier command failed with exit code 1 because of an undefined reference to get string。 Now。

 in the past， when we've seen undefined or really undeclared mentions of get string。

 the problem was just with missing this line。 this line is clearly here。

 But the catch is I'm getting this error message now， because when I run clang of hello dot C。

 I'm just assuming that clang knows where to find the C S 50 version of get string。

 And that is not the case。 technically， if I want the compiler to compile this code for me。

 what I'm actually gonna have to do is this。 Let me go back to my terminal window here。

 And I'm gonna。😊，Say clang。Hello dot C， But I'm then going to specify dash L C S 50。

 which is cryptic at first glance。 But this is telling the compiler to link in the Cs 50 library so that it knows what the zeros and ones are that belong to the get string function。

 Long story short。 if I hit enter now， the error message gone away。 if I type L S。

 I've still got a dot out， but it's a new version thereof。 And if I do dot slash a dot out。

 now I see the new behavior where I can type in my name and see hello comma David。 Now。

 this is getting a little stupid that I keep using a dot out， we can change that as well。 In fact。

 these commands， as we're starting to see support what are called command line arguments。

 And a lot of the programs we've run already， take command line arguments。

 When we run code space hello dot C， the socalled command line argument to code is hello dot C。

 When I run make hello， the command line argument to make is hello。 In other words。

 the command line arguments to a program， are all of the words you're typing。😊，In your terminal。

 after the name of the program itself， whether it's make or whether it's code or anything else。

 So this is to say what I just ran clang of hello dot C dash L C S 50。

 I was passing in two command line arguments。 Hello dot C， which is the code I want to compile。

 and dash L C S 50， which means use the C S 50 library， please， but I can add another to the mix。

 I can actually do something like this， whereby I do clang dash O， hello， then I can do hello dot C。

 And then dash L C S 50 enter。 Now that two seems to work。 And if I type L S。

 I've got all the same programs as before。 So let's go ahead and get rid of those to make clear what's going on。

 I'm gonna remove a dot out。 I'm gonna remove hello， And just for good measure。

 I'll remove buggy as well。 so that all I have left in this folder is source code。 So if I type L S。

 there's my two files。 let's do this again。 Kang dash O， hello， hello dot C， dash L C S 50。😊。

Enter now if I type L S， I don't see hell a dot out anymore， because apparently。

 according to the documentation for clang， the actual compiler。

 if you pass dash O as a command line argument followed by another word of your choice you can name the program anything you want without having to resort to M V or clicking on it and typing a new name in manually。

 So if I now do dot slash hello， I see the exact same version which is asking me for my name and then printing it out。

 But long story short， the whole point of this exercise is that like running commands like this。

 quickly gets very tedious。 you have to remember like the order in which to do it with the command line argument。

 I mean， this is just stupid waste of time， typically， certainly in week one of the course。

 I have to memorize these kinds of magical commands to get things working。 But for now。

 know that when you run make， it's essentially automating all of that for you and making it as simple。

 semantically as make hello or make buggy。 But what's really happening is the make command。

 because of the way we've configured Cs50 dot dev for you。😊，Is doing all of this behind the scenes。

 And it's not that magical。 This just means change the file name to hello。 When you compile it。

 this just means compile this code。 And this just means use the C S 50 library。😊，Like that's all。

But that message about linking something in。 theres。

 there's something juicy going on there such that make is， in fact。

 helping us sort of solve a whole bunch of problems when we compile。 And in fact。

 let me propose that if we take a step back and look at some of the actual code that we're compiling。

 let's consider like what we actually mean by compiling。 Yes。

 it's the case that to compile your code means to go from source code， to machine code。

 But technically， there's a few more steps involved， technically， when you compile your code。

 that sort of become the industry term of art that really is referring to four separate processes。

 all of which are happening in succession automatically。

 But each of which is doing a different thing。 So just once。

 let's walk through these these several steps， pre preprocessing first。

 So when you have code like this， which is a somewhat familiar function from last week。

 whereby I'm including standard I O do H， because I want to use printf。

 I've got the prototype for some function I ended up writing to get the cat to meow。

 That function does this。 It takes snow。put， it produces no output or return value。

 but it does print out meow。 And that's it。 Meanwhile。

 my main function has a four loop that iterates three times correctly。

That each time calls the Miow function。 So that's it。 So what does it mean to compile this code。

 Well， technically four steps。 preproces is the first。 What does that mean。

 Anything that starts with a hash symbol like this hash include gets preprocessed。

 That hash is special meaning。 and it says to the compiler do something with this line first up until now。

 we've sort of taken for granted that standard I O dot H is where printf is declared like that's where someone wrote the the prototype for printf。

 So what's really happening during the preprocessing step is that the compiler clang is going into this file wherever it is on the server's hard drive。

 It's finding the relevant lines。 And。sorry， one second。I told the wrong story。 Okay， I'm apologize。

 let me rewind。So what is this preprocessing step。 So consider this program here。

 which we wrote in brief last week。 We've got include standard I O dot H。

 which is there because we want to be able to use printf ultimately。

 We've then got a prototype for this Miow function。 and the Miow function does this。

 All it does is print out。 quote unquote Miow followed by a new line takes no input returns。

 no return values。 The main function now has a for loop iterates three times each time calling the Miow function。

 And we saw this already earlier today。 This line of code here。 the so-called prototype is necessary。

 because we need to tell the compiler that Miow exists before we actually use it here。

 especially if I don't get around implementing it until later。

 So this copy paste of that first line of code， a socalled prototype solve that problem。

 This is what the header files are essentially doing for us。 before I use printf down here。

 the compiler needs to know what it is what its inputs are， what its outputs are。

 turns out the prototype for printf。😊，Is going to be in standard Io do H。

 And that's what that line of code has been doing for us all this time。 In fact。

 let's take a simpler example that we keep using here。

 whereby I'm including Cs 50 do H and standard Io do H。

 and I'm using the C50 getstr function to get someone's name and put it in a variable called name and then I'm printing out hello comma such and such。

 What's going on now when I preprocess this file by running make， which in turn runs clang。 Well。

 the compiler finds on the server's hard drive。 the file called Cs 50 do H goes inside and essentially copies and paste its content into my own code。

 Meanwhile， such that we get the prototype there for getstr， and we haven't seen this yet。

 but it stands to reason that all this time using printf。

 we've been passing in a prompt like what's your name and we've been getting back a string。

 What's inside the parentheses recall as the input， What's before the function name is the output。

 the so-called return value。 What about standard Io do H。

 It's in that file that printf's prototype is。So essentially。

 what the compiler does when preprocessing this file is it finds standard A dot H somewhere on the server's hard drive。

 goes inside and copy and pastes those relevant lines of code into my code as well。

 It's to avoid me having to do all of that myself， find the file。

 copy paste it or manually type out the prototype， these preprocessor directives。

 just automate all of that TDM。 So what this effectively has at the top of my code after the file has been preprocessed is all of those hash symbols。

Followed by include our changed to contain the actual contents of those header files。 Now。

 the compiler knows what Gi string is all about and what printf is all about。

 That then is the preprocessing step。 What is compiling technically mean compiling means taking that preprocessed code。

 which again looks a little something like this。 and converted into something called assembly code。

 And we won't spend much time in this class on assembly code。

 But this is how programmers used to write code before there was C before there was Python and Java and all of these other modern languages。

 programmers were writing code like this。 before this existed。

 they were programming zeros and ones into the earliest of mainframe computers using punch cards and other technologies like literally sheets of paper with holes in them。

 not very fun， very tedious。 So the world invented this。 Also not very fun， very tedious。

 So the world invented C。 not that much fun。 So the world invented Python and so forth。

 we continue to sort of evolve as a species with code。 But the compiler。😊，Technically。

 takes your preprocessed source code and converts it into something that looks like this cryptic。

 and that's to be expected。 But there are some familiar phrases。 There's mention of main。

 There's mention of getstring。 There's mention of printf。 And there's a bunch of other things。

 move and push and X or and call and these other commands here。 These are the assembly instructions。

 Those are the lowest level instructions that the CPU inside of a computer understands CPU is the central processing unit。

 The thing by Intel or AMD or Apple or other companies。

 those are the lowest level commands that the actual hardware inside of the computer understand。

 it's just nice to be able to write words like main and4 and printf。

 then it would be to run these much more arcane commands that you have to look up in a manual。

 So compiling just take C code and makes it a lower level type of code called assembly。

 When I said a dot out means asler output。 That's why inside of that file is essentially the output of an assemblyseler。

 All right， we're almost there。😊，What does it mean to assemble a program。

 which is step 3 of the compilation process。 That means converting assembly code to the actual zeros and ones we keep talking about。

 So if the file is called hello dot C， when that file is assembled the assembly code becomes the zeros and ones for your code in hello dot C。

 but your code is not everything that composes your final program。

 your code from hello do C has to be combined with code from Cs 50 library from the standard I O library that other humans wrote I and the team wrote the C50 code。

 other humans in the world wrote the printf code in standard I O。

 So essentially the fourth and final step is to link all of those zeros and ones together。

 somewhere on the server there is not just the header file， C 50 dot H and standard I O dot H。

 but your code hello dot C， our code， C 50 do C， and the code that contains printf's own implementation。

 bit of a white lie， It's technically not called standard I O do。😊。

But the point remains ultimately the same。 So these files have already been compiled for you in advance。

 This is your code。 What the assembly process does is it combines all of that into zeros and ones。

 And then all three chunks of zeros and ones are linked together。

 So if you think back to when I tried compiling the code without dash L Cs 50。

 there was some mention of linker linking just means the computer did not know how to link your code with Cs 50s code。

 because we were missing dash L Cs 50， which tells the compiler to go find it somewhere on the hard drive。

 And the final step then of linking is to combine all of those zeros and ones into one bigger blob of zeros and ones。

 And that's what's inside your hello program that you can execute。 So long story short。

 these four steps are what's been happening ever since the start of last week preprocessing compiling assembly and linking。

 But thankfully， the world of programmers。😊，Just treats all four of these steps as what we know now as。

Compiling， it's just a lot of users say compile and not worry about those lower level details。

 but that might reveal better to you what all these error messages mean when you see hints of this kind of terminology。

Questions。On any and all of that。From here on out， we're going to go higher level than lower。

I don't get the part with the like when we're talking about。지금。

Assembly process basically convert disease。doesn't like across the multiple like three different ones。

 thoseer zeros and1 signify different things like one can signify text and the other signify something else。

No， like what part， what？Responsible。Really good question。

 How does the computer know which of those zeros and ones corresponds to data like numbers or strings of text or actual commands。

 We're gonna come back to that in week 4 of the class。 But long story short。

 what we just saw on the screen is a big blob of zeros and ones actually follow some pattern where the bits up top or represent a certain functionality。

 The bits on the bottom represent something else， and they're organized into patterns。

 So long story short will come back to that， but they follow conventions。

 It's not just a hot mess of like zeros and ones。😊，Other questions。Correct。

 the pre processing step goes into the header file and essentially copies and paste the contents of it into your own code。

 so you don't have to waste time doing that manually yourself。Other questions。How it convert。Mmhmm。

No， so when you compile your code， you're going from the assembly code to the zeros and ones。 sorry。

 when you compile， let me pull up the， the chart again。When you compile your code。

 you're going from the C code to the assembly code and the patterns you get when you see the assembly code are specific to a certain CPU。

 So long story short， if you're designing software for iPhones or for Android devices or Macs or PCs。

 you're going to necessarily use a different compiler because given the same C code。

 you will get different assembly instructions in the output。

 And this is why you can't just take back in the day。

 like a Cd containing a program from a Mac and run it on a PC or vice versa because it's the wrong patterns of instructions。

 But the reason why we have all of these annoying layers of complexity is because one。

 four different people can now implement the notion of compileiling。

 someone can implement the preprocessor， someone can implement the compiler the assemblyr the linker and you can actually collaborate by breaking things down into these quantized steps。

 But also you can do this step this step and then two different people can write compilers to actually write to output assembly code for like iPhones over here and Android devices over here。

All of us can still enjoy using the same language up here。

 So there's a lot of reasons for this complexity。 Just understanding it is useful。

 but you're not gonna need to use this sort of knowledge day today。

 But it's what enables so much of today's complexity nonetheless。 All right。

 So a bit of a flourish now as to what we've been doing with compiling Well。

 compiling is going ultimately from source code to machine code。

 Could't you just kind of reverse the process。 if someone wrote really interesting software。

 like Microsoft word or Excel or something like that。 Well， when I buy it or download it。

 Like I literally have a copy of all of those zeros and ones。

 Could't I just kind of reverse this process and reverse engineer someone else's code by decompiling it。

 And this is genuinely a threat and this comes up in matters of law and intellectual property。

 because the zeros and ones have to be accessible to you and to your computer。

 So it's not a great feeling if someone with enough time and enough savvy could sort of reinvent Microsoft word by just figuring out what all those zeros and ones mean。

 However， it's sort of easier said than done。😊。

![](img/40cfbb95e7fe840f46b181fa68459398_7.png)

To reverse engineer code from these zeros and ones。 For instance。

 this pattern of bits on the screen here did what did we say last week。Soilly quit。

 No normal person should be able to answer this， but I did say it before。

These zeros and ones print what。It just prints out hello world。

 And I cannot glance at that and figure it out like off the top of my head。

 But if I know what architecture， what CPU this code has been compiled into。

 and I pay attention in week4 and know what the various layout of the zeros and ones are。

 I could painstakingly figure out what each of those patterns of zeros and 1 means by breaking them into chunks of 8 or 16 or 32 or 64 which are common units of measure that I alluded to last week。

 Now， that's gonna take a crazy amount of time。 And the sort of presumption is that if you are smart enough and capable enough and have enough free time to do that。

 it would probably take you less time to just implement Microsoft word the normal way and just rebuild the software。

 It's gonna take you more time to go in reverse than it would in the so-called forward direction。

 But there's other subtleties as well。 inside of this code is not only commands like print functions like print。

 but suppose that it contained a loop， for instance， to print meowowow。 Well。

 we know already that you can use a four loop sometimes or you can use a while loop。

 but they're functionally equivalent。 It's sort of a stylistic decision which。One you use。

 whichever one you're more comfortable with or maybe feels a little better design。

 but you can't figure out from the zeros and ones， whether or not it was a while loop or a for loop。

 because it just results in the same pattern of zeros and ones。 It's just a programmer's choice。

 which is to say you can't even perfectly reverse engineer everything because it's not going be obvious from the zeros and ones。

 what the source code originally look like。 But again。

 the bigger deal breaker is if you have that much time and energy and savvy。

 just like reimplement micro word itself， don't try to reverse the whole process。

 which is going be much more painstaking and time consuming instead。

 Now this is not true for all languages and just as a teaser in a few weeks time when we talk about web programming and another language called jascript。

 it turns out that jascript source code is actually sent from web servers to web browsers and you can look at the source code of any website on the Internet。

 Harvard Facebook do com Gmail do com it's going to be there。

 So not all languages it turns out are even compiled typically sometimes the source code。

It is just executed by the underlying computer。 So we're just scratching the surface of some of the implications of all this in a little bit time。

 Let's take a look further under the hood at the actual memory， solve some other problems。

 but I think it's now time for cheeseit。 So let's go ahead and take a 10 minute break。

 Ss are now served。 See you in 10。Alright， we are back。 And up until now。

 when we've been writing code， recall that we have to specify like what type of value you want to put in a variable。

 Like that's why I had to go in and add string before the word name in my first bug today。

 But it turns out as we've kind seen already has a whole bunch of these data types。

 I rattled these off last week。 Bull in long double char string。 but we consider for a moment。

 just how much space， each of these things takes up and see if we can't help you see what the debugger was seeing earlier。

 that is what is where in memory。 So a bull， it turns out actually takes up 1 by。

 which is kind of stupid because technically a bull true or false， really only needs 1 B。

 it just turns out that it's more efficient and easier to just use a whole by 8 B。

 even though7 of them are effectively unused。 So a bull will take up 1 by。

 even though it's just true and false。 And in recall uses 4 B。

 So if you want to count really high with an int。 the highest， you can go is roughly 4 billion。

 we've claimed。 And unless you want to represent negative numbers in which case the highest is like 2 billion because if you want to be able to count all the way down to negative。

😊，BYou got to kind split the difference along， meanwhile， is twice that， it uses 8 bytes。

 which is roughly 9 quadrillion possibilities， which is quite a few more than 4 billion。

 That is if you want to include negative numbers as well then we had floats which were real numbers with decimal points which speak to just how precise you can be with significant digits。

 a float is four bytes by default， but a double gives you twice as money bits to play with which lets you be more precise。

 even though at the end of the day， whether're using floats or doubles floating point impreci as we've seen is a fundamental problem for scientific financial and other types of computing where precision is ever so important。

 a char meanwhile， at least as we've seen it is a single bys using ASII characters specifically。

 and then string I'll put as a question mark because a string totally depends on its length。

 if you're storing high。 that's like one2 bys if storing hello That's like five bys and so forth。

 So strings depend on how many characters you actually want to store inside of them。

Where does this go。 Well， here is a picture of a stick of memory， a dim， so to speak。

 whereby on this stick of memory， which is slid into your computer， your laptop。

 your desktop or some other device， there's all these little black chips that essentially contain lots of room for zeros and ones。

 It's somehow electronic。 But inside of there all of the zeros and ones that we can store data in。

 So if we kind of zoom in on this， it stands for reason， that for the sake of discussion。

 if this one chip represents like 1 GB，1 billion B。

 it stands to reason that we could slap some addresses on these by。

 whereby we could say this is the first by。 And this is the last by or more precisely。

 this is byte 0，1，2，3 dot dot dot by 1 billion。 And it doesn't matter if it's top down left right。

 or any other order。 We're just talking about this conceptually at the moment。 So， in fact。

 let's go ahead and draw this really is a grid of memory。

 a sort of canvas that we can just use to store types of data like bos and ints and jars and floats and everything else。

 If we are gonna to use one by to。😊，Like a char。 Well， you might use just these 8 Bs up here。

1 B up here。 If you want to store an int。 Well that's four， you might use all four of these bytes。

 necessarily contiguous。 You can't just choose random bits all over the place when you have a4 by value like an int。

 they're all gonna be contiguous back to back to back in memory like this。

 But if youve got a long or double， you might use 8 by instead。 So truly。

 when you store a value in memory where it's a little number or a big number。

 All you're doing is using some of the zeros and ones physically in the computers hardware somewhere and letting it permute them turn them on and off to represent that value you're trying to store。

 Allright， so let's go ahead and abstract away from the hardware。

 And let's just start to think of this grid of memory sort in zoomed in form and consider at a lower level。

 what is actually being stored inside of here。 for instance。

 supposeose that we've got some code like this containing three scores problem sets。

 you got a 72 on one of them a 73 and another and a 33 on the third。 I've deliberately。

In our old friends，72，73，33， which recall spell high。

 or together in the context of colors is like a shade of yellow。

 just so that we're not adding some new random numbers to the mix。 These are our old friends。

3 integers。 let's use these in a program。 Let me go over to B S code here。

 and let me create with code a program called scores C that's just gonna let me quickly calculate my average score on my problem sets。

 I'm going go ahead and include， as we often do standard I O do H at the top。

 I'm gonna do int main void after that。 And then inside of my curly braces。

 I'm gonna to do exactly those sample lines of code。 My first score was let's say a 72。

 My second score was 73 and my third score was 33。 So I've declared three variables one for each of my problem set scores。

 Now let's calculate the average。 So printf quote unquote average colon。 so I know what I'm printing。

 And now I'm gonna go ahead and use maybe percent I backlash N。😊。

Then what I'm gonna to pass in is a bit of math。 So to compute an average is just score 1 plus score 2 plus score 3 divided by3。

 And I put the scores， the numerator in parentheses， just like in grade school。

 Like I need to do that operation first before doing the division。 So just like math class。

 semicolon at the end to finish my thought。 Let's see how this goes。

 make scores enter dots slash scores。 And it would seem that my average across these three problem sets is 72。

 which I which is great， but I don't think that's actually what I want here。 What have I done wrong。

😊，It's unintentional。Yeah， I mean kind of being a little generous with myself here。

 I didn't really factor in my worst score。 So that was accidental。 So now let me do this correctly。

 make scores， dots slash scores。 And now， okay， my average is 59。 But I， I beg to differ。

 I'd like to quibble。 My score technically， I think mathematically should really be 59 and a third。

 I'm kind of being cheated those that third of a point。 So what's going on here。

 Why am I only seeing 59 and not my full grade。😊，Perfect。

 because I'm using integers when I divide by three。

 it's gonna truncate everything after the decimal point。

 which we touched on at the very end of week1， which is an issue with just truncation in general。

 So one approach to fix this。 I could change my percent I to percent F， which is the format code。

 It turns out for a float。 And that is what I want to print。

 So let's see if that fix alone is enough。 make scores。 oops， it's not。

 I got ahead of myself there And let me scroll up to the error format specifies double。

 but the argument has type n。 turns out you can use percent F for doubles as well。

 So that's why I'm seeing double， even though I intended a float in this case。

 So there's a problem here。 I the argument has type nt， even though I'm passing in percent F。

 You're seeing mention of percent D here， which is an alternative to percent I。

 we typically encourage you to use percent I because I for integer。

 But there is that is not the solution to this problem because I want my third of a point back。

 So how could I go about fixing this。 Well， the fundamental problem here。

 is that I'm trying to format an integer as a float or even as a double。

I need to convert these scores to floats instead。 So I could go in and change this to float。

 this to float， this to float and heck， just to be super precise。

 I could add a  point0 on the end of each of them just to make super clear the user floats。

 But there's another way I could， for instance。Simply convert my denominator to 3。

0 because it turns out so long as you involve like one float in your math。

 the whole thing is gonna get promoted， so to speak to floating point values instead of integers。

 I don't have to convert all of them。 So I think now if I do make scores， dot slash scores now。

 there's my third of a percent the third of a point back。

 There's another way to do this just as an aside and we'll see this again down the line。

 if you really want to stick with three because it's a little weird just semantically to divide by 3。

0。 like that's an implementation detail。 But you're truly computing an average of three things。

 you can technically cast the3 to a float in parentheses。

 you can specify the data type that you want to convert another data type2。

 And this two should make the compiler happy dot s scores。 I get roughly the same answer。

 We're seeing some floating point imp precisionci though。 nonetheless。

 But that too would achieve the goal here。 But short。

That's all just a function of floating point arithmetic there。 So what's going on now。

 actually in the computer's memory。 Let me revert back to the simpler one with just 0。0 there。

 And let me propose that we consider where these three things are in memory。 Well。

 if we treat this as my grid or canvas of memory。 Who knows where they're going to end up。

 But for the sake of discussion， let's assume that 72 ended up in the top left of my computer's memory。

 I've drawn it to scale， so to speak。 in that this score 1 variable is clearly taking up4 B of memory。

 and it's an int。 And that's typically how many bys are used on systems technically depends on the exact system you're using。

 but nowadays， it's pretty reasonable to assume that an integer will be 32 B on most modern systems。

 Score 2 is probably over there。 Score 3 is probably over there。

 So I'm using 12 B total4 B for each of these values。 All right。

 So that's really all that's going on underneath the hood。 I don't have to worry about this。

 The compiler essentially figured out for me where to put all of these things in memory。

 But what really。😊。

![](img/40cfbb95e7fe840f46b181fa68459398_9.png)

![](img/40cfbb95e7fe840f46b181fa68459398_10.png)

IIn memory。 Well， technically， each of these variables。

 if it's it's composed of 32 B is really just a pattern of literally 32 zeros and ones。

 And I figured out the pattern here。 I cram them all into the space there。 But you see here。

 three patterns of 32 Bs， which collectively compose those numbers there。

 But let's consider design now。 in terms of my code， this gets the job done。

 it's not that bad or big of a deal for just calculating the average of three scores。

 But this should also start to rub you the wrong way this week onward。 when it comes to design。

 like this is correct， especially now that I clamored back my third of a point。



![](img/40cfbb95e7fe840f46b181fa68459398_12.png)

But this is bad design using the variables in this way。 Why might you think。Yeah。Yeah。

 I'm gonna have to type in each score manually with each passing week when I get the fourth problem set in the fifth。

 I mean， surely people who came before us came up with a better way to solve this problem than like manually create 10 variables。

20 variables， whatever it is by the end of the semester。 It just feels a little sloppy。 And indeed。

 that's often the way to think about the quality of something is designed， think about the extreme。

 if you don't have three scores， but 30 or 300 is this really gonna be the best way to do it。

 And if you feel like there's gotta be a better way odds are there are。

 certainly if the language itself is well designed。

 So let's consider how else we might go about solving this。 Well。

 it turns out we can treat our canvas of memory， that grid of bytes。

 into chunks of memory known as arrays an array is a chunk of contiguous memory back to back to back whereby if you want to store three things。

 you ask the computer for a chunk of memory  for3 things。 if you want 30。

 you ask for one chunk of size 30。 if you want even more， you ask for a chunk of size300 chunk。

a term of art， I'm just using it to colloquily explain what an array actually is。

 It's a chunk or a block of memory that is back to back to back to back。

 So what does this mean in practice， Well， it means that we can introduce a little bit of new syntax and C。

 if I want to create one variable instead of three。 and certainly one variable instead of 30。

 I can use syntax like this。 Hey compiler， give me a variable called scores plural。

 give me room for three integers there in。 So it's a little bit of a weird syntax。

 but you specify the type of all of the values in the array。

 you specify the name of the array scores in this case。

 and I pluralized it just semantically because it makes more sense than calling it score now。

 and then in square bracket， so to speak， you specify how many integers you want to put into that chunk of memory。

 So this one line of code now will essentially give me 12 bys automatically。

 but they'll all be referable by the name， scores plural。 So let's go ahead and。😊。



![](img/40cfbb95e7fe840f46b181fa68459398_14.png)

this into some code as follows。 Let me go back to V。 S code here， clear my terminal。

 And now let's just whip up the same kind of program。

 but get rid of these three independent variables。 and instead。



![](img/40cfbb95e7fe840f46b181fa68459398_16.png)

And instead， let's go ahead and just say int scores plural bracket 3 Now I need a way to initialize the three values。

 But this I can do， too。 It turns out that if I want to put three values in this。

 I just need slightly new syntax I can say scores bracket 0 equals 272 scores bracket1 equals 73 scores bracket 2 equals 33。

 So it's not all that different from having three variables。 But now I technically have one variable。

 And I am indexing into it at different locations， Lo 0，1 and 2。

 and it's0 because we always in computing start counting from0。 So I do scores。

 bracket 0 is gonna be my 72 problem set scores bracket 1 is my 73 problem set and scores bracket 2 was my weakest。

 my 33 pet。 Now my syntax down here has to change because there are no more score 1 score2 score 3 variables。

 but there are scores bracket 0 plus scores， bracket 1 plus。

 and notice what V S code is trying to do for me。 It's saving me some keystrokes as I type in。

And type one single bracket。 noticeice it finishes my thought for me and magically puts the cursor where I want it so I can put the two right there and generally save on keystrokes。

 But that has nothing to do with C， it just has to do with V code trying to be now helpful。

 So I think now if I go down here and do make scores， scores， we get the same answer。

 But it's arguably better designed because I now have one variable instead of three。

 let alone many more。 And in fact， if I wanted to change the total number of scores。

 I can just change what's in that initial square bracket。 So if we consider what's going on now。

 if we look at the computer's memory， it's the same exact layout。

 but there's no more three variable names， there's one scores bracket 0 scores bracket 1 and scores bracket 2 and notice here ever more important in array values are indeed contiguous back to back to back。

 Now， the screen is only so wide。 So they kind of wrap around to the next row of bys。

 but the computer has no notion of up down left right。 I mean， it's just a piece of hard。

Where that's got lots of bytes available that can be addressed from the first byte all the way down to the last byte。

 The wrapping is just a visual artifact on this here screen。Alright， so if I've done this now。

 maybe we can make this program a little more dynamic than just hard coding in my scores。

 Let me go in and add the Cs 50 header library so that we could also use， for instance。

 like get in and start getting these scores dynamically。 So I could do get int。

 and I could prompt the user for a score。 I could use get int again。

 and I can prompt the user for another p set score。

 I can use get int a third time and prompt the user for third such score。

 And then pretty much the rest of my code can stay the same。 Let's do make scores again。

 dot slash scores 72，73，33。 And now my program's a little more interactive。

 Like this doesn't work for just my three scores。 It can work for any one scores in the class。 Now。

 this two hints of bad design。 I like my introduction of the array because I now have one variable instead of three。

 But what now might rub you the wrong way among lines 7，8 and 9。😊，Yeah。It's repetitive。 I mean。

 I typed it manually， but it might as well have just copied and pasted like literally the same thing。

 So what's a candidate for fixing this， like what programming and construct might clean this up。

 yeah。Yeah， we could use a for loop or a while loop or whatever。

 But a for loop would get the job done。 And that's often my go to。 So let's do that instead。

 Let's go under my declaration of the array and do 4 int I equals 0 I less than 3 I plus plus。

 which we keep seeing again and again。 Now， how do I index into the array at the right location。

 Well， here's where the square brackets are kind of powerful。

 I can just say my scores array at the location。 I should get an int。😊，From the user as follows。

 So now I'm using get in once inside of a loop。 But because I keeps getting incremented as we've done many a time now for meowing and other goals。

 I'm putting the first one at location 0。 Y， because I is initialized to 0。

 I'm putting the second one at location 1， why because I'm going to plus plus or increment I on the next iteration。

 then the next iteration。 So this has the ultimate effect of putting these three scores at location 0。

1 and 2。 instead of me having to type all of that out manually。 Now。

 I don't love how I've done this still， if we really want to nitpicick。

 this solves the problem correctly。 But it's kind of。😊，Got a poor design decision still。

 It's got a magic number， as people say， what is the magic number here and why is it bad。Yeah。

 over here。Yeah， it was a little soft， but I think the number 3 is hardcoded in two places。

 We've got it on line 6， which is the size of the array。 And then again， on line 7。

 which is how many times I want to intererate。 But those are the exact same concepts。

 But it's on the honor system that I type the number three correctly both times。

 So I think we can fix this a little better。 I could do something like n equals3。

 And then I could use n here。 And then I could use n here so that now I only change it in one place。

 if your eyes are wandering to the bottom of the program。

 there's still a problem here because I've still hard coded 0，1 and 2， but we'll come back to that。

 But this is arguably a little better。 but let's talk a little bit about style。

 typically when you have typically when you've got a variable that should not change its value。

 we saw last week that we should declare it as constant and the trick there。

 is's to literally just write con for short in front of the type of the variable。

 And now it should not be changeable by you by a colleague a collaborator or the like。

 But typically by convention。😊，Sylistically， to make visually clear to another programmer that this is a constant。

 its convention also to capitalize constant。 So to actually use like a capital N here in all places just to make clear visually that there's something interesting about this variable。

 And indeed， it is a constant that cannot be changed。Allright， with that refinement。

 I don't think we've really improved the program fundamentally。

 I think we're gonna need to do a bit more work to do this really well。

 So I'm gonna to do this a little quickly， but mostly to make the point that we can make this indeed more dynamic。

 So let me hide my terminal window there。 Let me go ahead now and get the scores as I already am as follows here。

😊，And let me go ahead， and。Assum， for the sake of。Time that we have a function that exists already called average。

 And I simply want to pass in to that average function， the scores。

 whose average I want to calculate。 So average does not exist off the shelf。

 Like I can't just use an existing library for it。 I'm gonna to have to implement this thing myself。

 But how， All right， Well， let's go ahead and do this at the top of my file。

 I'm going go ahead and compute a function called average that takes in what an array of numbers。

 So this syntax is gonna be a bit new。 But the way I do this is int， say array bracket0。

 or array sounds a little too generic。 Let's just call it numbers for instance here。

 So that says my average function is going to take as an argument an array of numbers。

 This average function， though should return a value to。

 and it should return what type of value from what we've seen thus far。

A number of float specifically。 It could be int， but then I'm gonna get shortchan my third of a point。

 potentially。 So I think I want it to return a float。 Or if you really want precision。

 you could return a double just to be really nitpicky， but that seems excessive here。 Allright， well。

 now inside of my average function。 How can I calculate the average。 Well。

 this is just kind of like a math thing。 So I could declare a variable called sum and set it equal to 0。

 I could then have a four loop inside of this function for int I get 0。

 I less than I'm gonna come back to this。 the number of numbers in the array。

 And then I'm going do I plus plus， and then on each iteration。

 I'm going do sum equals whatever the current sum is plus whatever is in the numbers array at that location。

So I'm going a little quickly。 But again， I'm just applying the same lesson learned。

 Numbers is my array。 Numbers bracket I means go to the Ih location in there。

 But if my loop starts at0， that means go to location 0 and then one and then two。

 and heck if there's more scores in this array， It's just going keep going on up from there because of the plus plus But I hesitated here for a couple of reasons。

 So I put it to do here， which is not a thing that's note to self， how far do I iterate。 Well。

 if you come into CS5 with programming before， you can usually just ask an array， Aka of vector。

 what its length is in Java and in Python and the like， you can't do that in C。

 So if I want to know what the length is of this array， I've got to have the function。 tell me。

 So I'm going to additionally propose that this average function can't just take the array。

 it's also gonna have to take another argument， a second input for instance。

 called length that tells me how long it is。 And then down here。

 which is where we started this story。 when I use this so-called average function。

have to tell the average function by passing in N how many numbers are in that array。

 just because this is annoying that you have to pass in not only the array。

 but also its size separately。 That's the way it's done in C。

 more recent languages have improved upon this。 So you can just figure out what the length of the array is。

 As we'll see in a few weeks in Python。 All right， back to the average function at hand。

 I think we're almost there。 This is a little unnecessarily reverseverpose。

 recall that we can tighten this up by just doing plus equals whatever is in numbers， bracket I。

 that's just tightening it up。 It's syntactic sugar。 So to speak。

 And then the last thing I'm going to do in my average function is what actually calculate the average。

 So what is the average。 It's just the numerator。 like the sum of all of the scores divided by the total number of all of the scores。

 Well， I've got the sum So I think I just want to do sum divided by what to get the actual average now。

Yeah。Exactly， sum divided by length will give me the average because the sum is the numerator effectively。

 All of the scores added together and the denominator is the length。

 How many numbers were there actually。 Now， I can't just write this math expression here。

 If this is gonna be my functions return value。 And we've done this once or twice before。

 I literally say， in my average function， return this value。 So it hands back the work。

 I could use printf and just print it on the screen。 but I don't want that visual side effect。

 I want to hand it back So that online line 23。 I can simply calculate the average of those n scores and let printf use it as the value of that format code percent F。

😊，Alright， unfortunately I think we are in reasonably good shape。

 Let me cross my fingers now and hope I didn't screw this up， make scores。 Okay， dotslash scores。

 How many do we want to do， So we'll do 72，73，33 enter。 And there is so close average。

I've had a regression。 I've made the same mistake again， just in a different way。

I think I saw your hand go up。 Why am I getting 59， And I'm not getting my third of a point。Yeah。

 in this return line on line 11 right now， I'm again， stupidly doing integer divided by integer。

 That will make us suffer from integer truncation because if you're returning an integer。

 there's no room for the decimal point or any numbers thereafter。 So how do we fix this。 Well。

 I could change the sum to float like that would be reasonable。

 So then I do a float divided by the length I could do my casting trick like convert the the length to a float just for the sake of floating point arithmetic。

 There's a bunch of ways to solve this。 But I think I'll go with this one now。

 let me now do make scores again dot scores，72，73，33。 And now I've got albeit with some imprecision。

 I think enough precision certainly for like a college grade in this case，59。333 and so forth。 Okay。

 so what are the things to actually care about here。 So there's a decent amount of code here。

 most of it is sort of stuff we've seen before。 But the interesting parts I would propose are this when you create your own function that takes an array as input。



![](img/40cfbb95e7fe840f46b181fa68459398_18.png)

![](img/40cfbb95e7fe840f46b181fa68459398_19.png)

You have to take as input the length of the array。 You're not gonna to be able to figure it out correctly as in mod newer languages。

 You also need， of course， to pass in the array itself。 How do you pass in an array， Well。

 when you're defining the function， you specify the type of values in the array。

 whatever you want to name the array inside of this function。

 and then you use empty square brackets like this。 You don't have to put n or some other number there。

 all you need to tell the compiler is that my average function is going to take some array of values。

 specifically this many， you don't put it inside the square brackets there。

 Then when I use it now it's just now familiar syntax。

 when you want to index into your array that is go to location0 or one or two。

 you just use square bracket notation here。 But the array itself recall was actually created in main when I did this line of code here where I said。

 give me an array called scores。 each of whose values is going to be an int。

 and I want this many of them。 And so maybe the final flourish that'll add here just to be sort of nitpicky is。

I keep saying that main should really go at the top。 fine。 no big deal。

 Let me highlight my average function。 move it to the bottom of my file just because and then and only then I'll copy and paste that first line。

 the so-called prototype so that cllang doesn't freak out by not knowing what the average function is。

 So in short， there's seemingly a bunch of complexity here。

 But were the only thing that's really new in this one example is this is how you pass to a function in array that already exists elsewhere。

 not by its name， but by the square brackets there。😊，Okay。Questions。

On arrays or any of this new syntax， yeah。OK。So that we could。Or other。嗯哼。😊，0 is a vote。Just said。

How does it know it's not a double？Oh， how does it know it's not a double。 So by default。

 if you just type a number like 3。0 into your code。

 it will be assumed to be a double just because raw values。

 literal numbers with a decimal point will be treated by the compiler as doubles and be allocated 64 B。

just because like the world did not need to create a new format code， like percent D is not double。

 percent D is decimal integer， but don't worry about that。

 We tend not to talk about it too much in class。 Percent I is integer。 Percent F is float。

 but percent F is also double。And this is not consistent because what's a long percent L L I。

 What did I say last week， A percent L L I gives you a long integer。 It's just a mess。

There's no good reason for this other than historical baggage。Sure。

 I'm not sure if that's reassuring。Allright， so。Okay， let's use these。

 this knowledge for like something useful now and actually tease apart what is how we can use these。

 these skills for good and to better understand what's going on inside of the computer as follows。

 Let me go over to our grid memory。 And this time， let's not store some numbers。

 but let's store like these three lines of code， these three variables。 So three chas。

 even though we you know where this is going。 like this is not good design because I got three stupidly named variables。

 C 1， C2， C 3， But let's make a point first。 The first variables value is quote unquote H。

 second is I third is exclamation point。 Why， though， am I using single quotes， suddenly。

 instead of double quotes。😊，It's a character。 Chars are single quotes， strings are double quotes。

 And we'll see the distinction Y in a moment。 So， for instance。

 if this is my grid of memory and this program contains just three variables， each of them are char。

😊，Ods are， they'll end up like this in memory。 C1， C2， C3， H I exclamation point。

 assuming there's nothing else going on in my program。

 they're just gonna end up being back to back to back in this way。

 even though it might not in this way。 So what does this really mean is going on。 Well。

 let's go ahead and poke around。 Let me go back to B S code here。

 Let's close scores dot C reopen my terminal。 And let's create a new program called high dot C and just do something playful。

 So let me include standard I O dot H at the top。 let me do in main void after that。

 And inside of my curly braces， let's just repeat this C1 equals H in caps cha C2 equals I in caps and then cha C 3 equals exclamation point in in exclamation point。

 That's all。 Now， let's actually poke around and see what's inside the computer's memory。

 So I could do something like this。 I could print F。 For instance。

 percent C percent C percent C back slash N and percent C， turns out。😊，Character。

 So what do I want to plug in， C1， C 2 and C 3， semicolon。 So let's go ahead and do this。

 make high enter dot s high and voila。 There's my H exclamation point。 There's no magic here。

 Like I'm literally just printing out three char variables。 I can I don't need the spaces。

 if I want to get rid of those spaces between the word。 I can remake this make high dot slash high。

 And now we're back in business。 H I exclamation point。

 But here's where an understanding of types can give you a bit of power in sort of satiate some curiosity。

 What if I change my percent C to percent I percent I percent I So in in int。 Well。

 turns out that a char is really just a number because it's an ASi value from 0 to 255。

 So there's nothing stopping me from telling the compiler。 Don't print these as chas。

 print them as integers。 So let's do make high dot slash high enter， And that's a little cryptic。

 It looks like it's saying 727333，😊，Let me add those spaces back in between each of those placeholders。

 make high again。Dot slash H。 there are our old friends，72，73，33。

 It is not necessary in this case to say int int int because the compiler is smart enough and printf is smart enough that if you hand it a value that happens to be a char。

 It knows already， it's gonna to be an integer  essentially。

 So you don't even need to bother explicitly casting it this way。

 We're essentially implicitly casting it to an integer by using those format codes as such。Alright。

 so that just proves that what I've claimed is the case that there is this equivalence between characters and numbers is actually the case inside of the computer's memory。

 So even though you're storing H exclamation point， technically。

 you're storing three patterns of 8 bit each that give you these decimal numbers，72。

73 and 33 or specifically these patterns here。 Alright， then what is a string。

 And this is where things get a little more interesting。

 a string as we've used it is like a whole word or a phrase or when you started class today。

 like a whole paragraph of text。 So that's multiple values。 Now。

 why is that interesting for us potentially， Well， let's go ahead and write one line of code as a string。

 So here， for instance， is one line of code with a string。

 Let's go ahead and put that into my program。 So I'm gonna go back to the S code here and clear my terminal。

 And I'm gonna go ahead and delete all of this code。😊，Here for a moment。

And I'm gonna do something like this。 Str S equals quote unquote， high with with double quotes now。

 And now， just like in week 1， I'm going to print out percent S backslash N and print out the value of S per earlier because string is technically one of our training wheels for just a few weeks。

 I'm going to additionally include C S 50 dot H at the top so that the compiler knows about what this word is string。

😊，Alright， let's go into the terminal。 make high dot slash high， enter。 And we're back in business。

 printing that out now as an entire string。 Well， what's going on inside of the computer's memory this time。

 Well， I still have H exclamation point。 But it's a string now。 Well。

 it turns out the way that's gonna be laid out in the computer's memory is exactly like before。

 There's no mention of C 1， C 2 C 3， because those variables don't exist。

 There's just one variable S。 but it's referring to3 B of memory。

 It would seem H I exclamation point。 And you can kind of see where this is going。

 Like a string as a spoiler turns out it actually just what。😊。

It's just gonna be an array of characters。 Hence the dots we're trying to connect today。

 So at the moment， though， this is a single variable as a string。

 the value of which is H exclamation point。 But you know what， if it is， in fact， an array。

 I bet we can start playing around with our new square bracket notation and see as much in our actual code。

 So in fact， let me go ahead and do this in V S code now， let's not use percent S。

 let's use percent C percent C， and percent C 3 times Then instead of just S。

 let's print it out like it is an array S bracket 0 S bracket 1 S bracket 2。

 let's go back to V code my terminal and V S code make high dots slash high and nothing has changed。

 but I'm printing it out now， one character at a time because I understand what's going on underneath the hood in this case。

 I can actually see these values now， let's go ahead and change the percent C to percent I and at a space just so it's easier to read percent I space percent I。

😊，Space， I don't need my casts in parentheses because printf is smart enough to do this for me。

 make high again， dot slash high。 There again， is my 72，73，33。 However。

 that came from the mere fact that I put in double quotes H I exclamation point。

 So what's really happening here is it seems that a string is indeed just an array of characters。

But how does the computer know when doing percent S know what to actually print？ In other words。

 it stands to reason that eventually， if I've got more variables， more code。

 there's gonna be other stuff in the computer's memory。

 why does printf know when using percent S to stop here and not just keep printing characters that are over here。

 especially if I did have more variables and more stuff in memory。 Well。

 let's take a look at what's just past the end of this array， let's go back to Vs code。

 And now let's get a little crazy and add in a fourth percent I。

 And even though this shouldn't exist， let's do S bracket 3， which even though it's the number3。

 it's the fourth location， but H exclamation point is only three value。

 So let's look one location past the end of this array。 make high dot slash high interesting。

It seems。 and maybe it's just luck good or bad that the fourth byte in the computer's memory seems to be a0。

 Well， that's actually very much by design。 It turns out if we look a little further by convention。

 what the compiler will do for us automatically is terminate that is end any string we put in double quotes with a pattern of 8。

0 bits more succinctly， it's just the number 0 because if you do out the math where we've got 80s。

 it gives you0 and decimal or more technically the way it's typically written is this because it's not like the number 0 that we want to see on the screen backlash 0 similar to back slash n is sort of a special escape character。

 this just means literally 80 bits， not the number 0 that you might see in a phone number or something like that。

 So even though we said string S equals quote unquote high with an exclamation point seemingly three characters。

 how many bytes does a string。

![](img/40cfbb95e7fe840f46b181fa68459398_21.png)

Lth 3 actually seemed to take up in memory。It's actually gonna be 4。 And this happens automatically。

 That's what the double quotes are doing for you。 They're telling the compiler this is not just a single characters。

 This is a sequence of characters。 Please be sure to terminate it for me automatically with a special pattern of 8。

0 bit。 And that special pattern of 8，0 B actually has a name。

 It's the so-called null character or Nops， N U L for short。

 the null character is just a by of 0 bits。 And it represents the end of a string。

 You've actually seen it before。 if super briefly two weeks ago。 Here was our ASI chart。

 And we focus mostly on like this column here。 And this column here。

 And then we looked at the exclamation point over here。 But all this time over here。

 ASi character 0 is null N U L， which just means that's how you pronounce all 8，0 Bs。

 It's been there this whole time。😊。

![](img/40cfbb95e7fe840f46b181fa68459398_23.png)

![](img/40cfbb95e7fe840f46b181fa68459398_24.png)

So why is it done this way？ Well， how is the computer actually printing something out in memory？

 Well， it needs to know where to stop printf is pretty stupid。 odds are inside of printf。

 There's just a loop that starts printing the first character。 the next character， next character。

 and it's looking for the end of the string。 Why will consider what might happen。

 Suppose you've got a program that has not just one string but two， for instance。

 two strings like this。 So in fact， let me go back to the S code here， clear my terminal。

 And let's just make this program a little more interesting for a moment。

 string T equals quote unquote by， for instance， And then down here， let's do two printfs。

 Pre S backslash n and print out S printf percent S backlash n print out T。 Now to be clear。

 percent S means string placeholder T and S are just also the names of the variables there's no percent T that we want to use here。

 All right， let me go down to my terminal， make high dot slash high and voa。

 I get high and by just like you would have expected last week。

 But what's going on inside of the computer's memory。 Well in so far。



![](img/40cfbb95e7fe840f46b181fa68459398_26.png)

I asked Ive asked it to create two variables。 S and T like this。

 odds are what's happening in the computer's memory is high is ending up here。 A K A S T。

 because there's nothing else in this program is probably going end up here。 B Y E exclamation point。

 but it wraps on this particular screen。 T is taking up1，2，3，4，5 by total。

 just as high is taking up 4 by total， because the compiler is automatically adding for me。

 The backslash 0。 the null character to make clear to other functions where this string ends。😊。

So what does this mean in real terms and why is it 0， why is it 0。

 Like just because like at the end of the day， all we have is bits。

 We've got 8 bits to work with for chars。 You got to pick some pattern。

 We could have chosen all ones。 We could have chosen all zeros。

 We could have chosen something arbitrary。 A bunch of humans in a room years ago decided。

8 zeros will mean the null character。 That's the special character we will use to terminate strings in this way。

 Well， what does that mean with our new syntax。 Well。

 it means we could poke around with strings as well。

 So even though that first variable is S and that second one is T。

 You could technically poke around and access S bracket 0， and 1， and 2 and 3， T bracket 0，1，2，3。

 and 4， and so forth。 So in fact， if I wanted to dive in deeply there。 and actually see that。 Well。

 let me go ahead and do this back in V S code here。 let me make a refinement here。

 I've now got my two strings here。 I could go and for instance， down here just like before。

 percent C， percent C， percent C， percent C。😊。

![](img/40cfbb95e7fe840f46b181fa68459398_28.png)

![](img/40cfbb95e7fe840f46b181fa68459398_29.png)

Perscent C， percent C， percent C。 And if I then do S bracket 0， S bracket 1， S bracket 2， oops2。

 and then down here， t bracket0， T bracket 1 T bracket 2， T bracket 3。

 and I'm doing that only because the word by is longer than the word high。

 if I do make high dot slash high same principles work even in this context here。

 But let's add an interesting twist just because if I have these values in memory here， as follows。

 Well， its kind if I've got two words in memory， I could use them in an array2。

 instead of having like S and T or word1 in word2， I can actually put strings in an array too。

 So let's go ahead and do this。 let me go back to the S code， and just for fun now。

 let's go ahead and do this。 give me an array called words that's gonna fit two strings。

 then in the first words words bracket 0， put high， then in words bracket1， put by。😊。



![](img/40cfbb95e7fe840f46b181fa68459398_31.png)

![](img/40cfbb95e7fe840f46b181fa68459398_32.png)

Only thing new here is that I'm making an array of strings now instead of an array of ints。

 but all of the syntax is exactly the same。 How can I go about printing these things， Well。

 just as before， I can do printf percent S backslash N and print out words bracket 0。

 Then I can do print F， quote unquote S。Backslash N words bracket1。 Again。

 I'm just sort of applying the same simple syntax that we saw before。 Thoughlash again。

 of the sixth version of this program， right， I'm just sort of jumping through syntactically to demonstrate that these are just different lenses through which to look at the exact same idea。

 And while a normal person would not do this， We could think about what's really going on in memory with arrays of words when those words themselves ares of characters because a word is just a string。

 So this code here gives us something like this in memory。 And that program a moment ago。

 This is words bracket 0。 This is words bracket1。 The only thing that's different is I'm not calling them S and T。

 I've given them one name with two locations，0 and one。 Well。

 if each of these values is itself a string， Well， you said earlier that a string is just an array。

 So we can actually think of these two strings， even though the syntax is getting a little crazy using two sets of。

😊。

![](img/40cfbb95e7fe840f46b181fa68459398_34.png)

Square bracket notation where I can index into my array of words and then index into the individual letters of that word by just using more square brackets。

 And again， this is just to demonstrate a point， not because a normal person would do this。

 But if I go back to V S code， instead of printing out these two strings。

 Why don't I do something like this， printf。

![](img/40cfbb95e7fe840f46b181fa68459398_36.png)

Quote unquote， percent C， percent C， percent C， backslash N。 Then let's print out the first word。

 but the first character therein。 Let's print out the first word。

 But the second character they're in， the first word， But the third character there in。

 And even though I'm saying third and second and first， it's 2，1 and 0。

 respectively because we start counting it 0。 And then lastly here， we can print out the second word。

 percent C， Per C， percent C， percent C back slash N， then words bracket。

 How do I get to the second word in this array。Words bracket1， the first character they're in。

 Word bracket 1， the second character they're in。 Word bracket 1。

 the third character they're in Word bracket 1， the last character they're in。 And again。

 I this is just to demonstrate a point。 But if I do make high now dot slash high。

 we have full control over everything that's going on。

 If you now do agree and understand that's an array can be indexed into two but square bracket notation as kind of string because a string is itself just an array。



![](img/40cfbb95e7fe840f46b181fa68459398_38.png)

![](img/40cfbb95e7fe840f46b181fa68459398_39.png)

![](img/40cfbb95e7fe840f46b181fa68459398_40.png)

Strings are arrays for today's purposes， then。Questions on any and all of these tricks。No， all right。

 yeah， in front。Okay。

![](img/40cfbb95e7fe840f46b181fa68459398_42.png)

How do you establish or create an array？ Well， in the context of this program。

 if I go back to V S code， line 6 here gives me an array of size 2。An array of two strings。

 if you will。 The previous example we were playing with， which was my scores。 whoops， wrong program。

Wrong file。 If I open up scores dot C as before， this line here。

 line 9 gives me an array of n integers。So that is what establishes or creates the array in memory。

 You specify a name， the size and the type。That's all。 And the only thing that's new today， again。

 is the square bracket notation， which in this context， creates an array of that size。

 But once it exists， you can then access that chunk of memory by using square brackets as well。😊。

Other questions on raise， yeah， in front。Good question。

 Do you need to go index by index to put things inside of an array。 Short answer。 No。

 So let me open up again scores dot C from before。 And what I could have done in an earlier version of my program would be something like this。

 I could have done 72，73，33。 and deliberately didn't show this because I didn't want to add too much complexity。

 but you can use curly braces in this new way and initialize the array in one line。 And in that case。

 you don't even need to specify the size because the compiler is not an idiot。

 it can figure out that if you've got three numbers on the right。

 it knows that needs three elements on the left to put them into。

 But let me undo that and leave it just as I did， but short answer， Yes。

 you can statically initialize an array。 if you know all of the values up front and not when using get int in that case。



![](img/40cfbb95e7fe840f46b181fa68459398_44.png)

All right， so if you're on board with the idea that all a string is is an array and that array is always null terminated。

 we can now。

![](img/40cfbb95e7fe840f46b181fa68459398_46.png)

Use that knowledge to like， solve some simple problems and problems that others have already solved before us。

 So let me go ahead and close that file in V S code。

 Let me go ahead and open up another program here called length dot C。

 And let's just play around with the length of strings as follows。

 Let me include the C 50 library at the top。 Let me include standard I O after that。

 Let me do in main void after that。 And then inside of main。 Let's prompt the user for their name。

By using get string and just say name colon today。 And then after that。

 let's go ahead and figure out the length of the person's name like D A V I D。

 I should get the answer of 5 and K E， L L Y， we should get the answer of5。

 and hopefully for a longer or shorter name will get the correct answer as well。

 So how can I go about counting the number of characters in a string。

 Well the string is just an array。 and that array ends with the null character。

 There's a bunch of ways we can do this。 but let me go ahead and do this。

 Let me create a variable called n， which eventually will contain the length of the name。

 And I'm gonna set it equal to 0 because I don't know anything yet about the length。😊。

Then I can do this with a four loop， but I prefer this time to use a while loop。

 I'm gonna say the following while the person's name。At that location does not equal back slash 0。

 Go ahead and add one to the value of n。And then after all of this。

 go ahead and print out with percent I backslash n。 the value of n。 So what's going on here。

 This is easier said when you know already where you want to go with it。

 but with practice you2 can bang this out pretty quickly。

 N is going contain the length of my string I have in my loop here。

 A Boolean expression that's just asking the question does name at the current value of n not equal the null character。

 In other words， you're asking yourself， is this character null， is this character null。

 is this character null， is this character null。 And if not， you keep going， you keep going。

 And this is kind of a clever trick because I'm using N and incrementing it inside the loop。

 So when I look at D， that's not equal to backslash 0， So I increment N Now。

 N is one So I look at name bracket 1。 What's it name bracket1。 if it's my name A。

 A does not equal backslash 0， So it increments N。 What's at location 2 in D A V I D V V does not equal backslash n。

 So we repeat with I， we repeat with D。And then we get to the end of my name。

 which is the null character， because the get string function and C put it there automatically for me。

 the null character。Does equal backslash 0 and does not get incremented any more time。

 So at this point in the story on line 13， n is still 5。

 because I have not counted the new the null character。 So I hope I will see 5 on the screen。

 This is just kind of a very mechanical way of checking， checking， checking， checking。

 trying to figure out through inference how long the string is because it's as long as it takes to get to that back slash0。

 The null character。 So let's do make length enter dot slash length， type in my name， David。

 and I indeed get 5， let's go ahead and do dot slash length。 Kelly， I indeed get 5。

 and hopefully for shorter and longer names， I'm gonna get the exact same thing too。 In fact。

 we can try a corner case。 dot slash length， enter。 let's not give it a name at all。

 If I just hit enter here。 what should the length of the person's name be。Zero。

 which is not incorrect。 It's literally true， but that's because we're going get back essentially quote unquote。

 But even though it's quote unquote in the computer's memory。

 it's still going to take up one B because the get string function will still put null at the end of the string。

 even if it's got no characters therein。So it turns out this is not something you need to do frequently。

 like initializing a variable， using a loop like this。

 It turns out there are better solutions to this problem。

 You do not need to reinvent this wheel yourself。 because it turns out。

 in addition to standard I O dot H and C50 do H。 and as you probably saw in problems at one math do H and perhaps others there are other libraries out there。

 namely the string library itself。 In fact， if you go into the C 50 manual。

 you can look up the documentation for a header file called string dot H。

 which contains declarations for that is prototypes for a whole bunch of helpful functions。 In fact。

 the manual pages for it or at this URL here。 The most important function。

 and the one we're gonna use so often for the next few weeks is wonderfully called stir length for string length。

 Someone else literally decades ago wrote the code that essentially looks quite like this but packaged it up in a function that you and I can use so we don't have to jump through the stupid hoops。

 just to count the length of a string， we can just ask the stirring length function。😊。



![](img/40cfbb95e7fe840f46b181fa68459398_48.png)

What the length of a string is。 But odds are。 if we looked at the C code that someone wrote decades ago。

 it would look indeed quite like this。 So how can I simplify this program？ Well。

 I can get rid of all of this code here。 I can include string dot H at the top of my file。

 And then I quite simply could do something like this。 int length equals St length of name。

 That's gonna put in the variable length。 Actually， let's be consistent。

 int M equals stir length of name， And then on line 9， let's print it out。 Let's try this。

 make length， dot slash length。 David Okay， Kelly。😊，Okay， and no one and 0。

 it seems to now be working。 So this is a wheel we do not need to in reinvent。 And frankly， now。

 in a matter of design， I don't really need the variable n anymore。

 recall that we can nest our functions just like we did with average before。

 So let me get rid of that line and just say Sterling of name is actually perfectly reasonable here。

Alright， well， what more can we do with this， Well， let's consider some other matters of design。

 Let me close out length dot C。 And let's create another program of our own called string dot C。

 in which we'll play around now with this library and others。

 Let me go ahead and include here 50 dot H。😊，Let me go ahead and include standard I O dot H。

 Let me go ahead and include also string dot H。 Alright， what do I want to now do， Well。

 in main void and inside of main， let's go ahead and write a program that prints a string character by character just to demonstrate these mechanics。

 So string S equals get string。 And I'm gonna ask the user for some input because I just want to play around with any old string。

 I'm gonna go ahead and proactively say output here。

 And I'm going to go ahead and not use a new line character there deliberately below this now。

 I'm gonna have a for loop， though I could use a while loop that says int I equals 0。

 I is less than stirlang。😊，Of S， the string I just got from the human and increment I on each iteration and on each iteration。

 print out just one character in that string， specifically at S location I。

 And then at the very bottom of this program， Let's just print a single back slash and to move the character onto a new line。

 Long story short。 What have I done。 I wrote a stupid little program that prompts the user for a string。

 print the word output thereafter。 and then it print the word that they typed in character by character by character by character until it reaches the end of the string based on the length。

 Re by stirling。😊，So let's go ahead and run this in my terminal window。

 I'm gonna do make string dots last string。 And I'll type in my own name it before。

 This was the subtlety。 I deliberately wrote two spaces here because I just to be nitpicky。

 I wanted input and output to line up perfectly。 So you can see what's happening。 Indeed。

 if I do enter here。 Now I see input is David。 The output is David as well。

 So that was just a formatting trick that I foresaw。😊，Why is this program correct。

 but not arguably well designed。It's pretty good。 And that it's using the sterling function。

 I didn't reinvent a wheel unnecessarily， but there's an inefficiency that's kind of subtle。

And it relates to how a for loop works。Any thoughts？ This program， I claim。

 is doing unnecessary work somewhere。Yeah。Okay， that's definitely stupid。

 You don't have to output a character by character。 That's just my pedagogical decision here。

 So correct， but not the question we're fishing for。There's a second stupid thing， yeah。Yes。

 every time through this loop。 and this isn't so much my conscious choice， but my mistake。

 I'm checking the length of S again and again。 why， because recall how a for loop works。

 The initialization happens once at the very beginning。 then you check the Boolean expression。

 then if it's true， you do the code。 Then you do the update， Then you check the Boolean expression。

 Then you do the code update Boolean expression， you do the code。

 But every time you evaluate this Boolean expression。

 You're asking does is I less than the stir length of S。 But this is a function call。

 Like you are literally using stirling again and again and again， And like a crazy person。

 you're asking the computer， what's the length of S。 What's the length of S。 What's the length of S。

 It's not going to change， It's going to be the same no matter what So how can we fix this。 Well。

 I could solve this in a couple of ways。 Like I could， for instance。

 down here do int n equals stir length of S and stored in a variable N。 and just do that。

 I think that eliminates the inefficiency， because now I calculate this length。😊。

Once it's not gonna change， nor is my variable。 So I can now use and reuse that variable。

 It's just saving me a little bit of time。 You know， microseconds， maybe。

 but when you're writing bigger programs and you're doing things in loops。

 If that loop is running not three times or five， but a millions times millions of times all of those microseconds。

 milliseconds might very well add up。 But it turns out there's some syntactic tricks we can do 2。

 I'm alluded to this earlier， if you want to initialize not one variable but two。

 you can actually do it all before the first semicolon like that。 So now on line 9。

 I'm declaring a variable called I and setting equal to 0。

 and I'm declaring a second variable called n， also the same type int and setting it equal to the length of S。

 And now I can use that again and again。 Now， as an aside。

 this is a little bit of a white lie because smart compilers nowadays are so advanced that they will notice that youre calling Sterling again and again inside of a loop。

 and they will just fix this for you unbeknownst to you。 but it's representative of a class。😊。

The problems that you should be able to spot with your own human eyes and avoid altogether so that you don't waste more time and more compute and more money in some sense than you might otherwise need to in this case。

😡，Any questions on that there？Optimization， yeah。You do not say int again。

 The constraint is that you have to use the same data type for all of your initialization。

 So you better hope that you only want ints in this case。 Otherwise。

 you got to pull it out and do what I did earlier。 Good question。Others on this。Yeah。

When does it account for spaces， a space is just character， ask character number 32。

 So there's nothing special about it。 It's sort of invisible， but it is there。

 It is treated like any other character。 There's no special accounting whatsoever。

 The null character， which is also invisible is special because printf and Sterling no to look for the end of that variable。

 the end of that value as such。Alright， let's try one other demonstration of some of these ideas here。

 Let me go into another file that will create called how about uppercase dot C。

 Let's write a super simple program that like uppercase is a string that the human types in and see how we can do this sort of good。

 better and best。 So I'm gonna call this file uppercase dot C inside of this file。

 Let's use our now friends include C 50 dot H。 Let's do include standard I O dot H。

 Let's then include lastly， How about string dot H。

 And the goal here inside of mainine is going to be2。😊，Get a string from the user。

 So string S equals get string。 And we're gonna ask the user for a before string representing what it is they typed before we uppercase everything。

 Then I'm gonna go ahead after that and print out just as a placeholder after and two spaces just to be nitpicy so that the text lines up vertically on the screen。

 Now I'm going to do the following int I equals0 n equals stir length of s semicolon I less than n。

 just like before I plus plus。 So I'm just kicking off a loop that's gonna iterate over the string the human typed in。

 Now， if my goal in life is to change the user's input from lowercase。

 if indeed in lowercase to uppercase， let's just express that literally。

 If the current character in the string。 So S bracket I is greater than or equal to quote unquote A and S bracket I is less than or equal to quote unquote Z using single。

😊，QuThis is arguably a very clever way of expressing the question。 is it lower case。

 We know from our ASI chart from week 0， that。The ASCI chart has not only numbers representing all the uppercase letters。

 but also numbers representing all the lowercase letters。 Lowcase A， for instance， is 97。

 and they are all contiguous thereafter。 so we can actually treat just like we did before。

 Chars is and in is chars and sort of ask mathematical questions about these chars and say is S bracket I between a and Z inclusive。

 So if it is lowercase。 and I'll add a comment here for clarity。 if S bracket I is lowercase。

 what do we want to do， we want to force it to uppercase。

 So this is a little trick I can do as follows printf， the current character。

 but let's do some math on it， let's change S bracket I by subtracting some value。 Well。

 what might that value B， will recall from week 0， our ASI chart here and let's focus， for instance。

 on the lowercase letters here and the uppercase letters here。

 What's the distance between all upper and lowercase letters。It's 32， right。

 And the lowercase letters are bigger。 So it stands to reason if I just subtract 32 from the lowercase letter。

 it's gonna immediately get me to the uppercase version thereof。 So this is kind of cool。

 So I can actually go back to V S code， and I can literally subtract the number 32 in this case。

 because ASI is a standard， It's not going to change else。 if the letter is not lowercase。

 I'm just gonna go ahead and print it out unchanged。😊，Without doing。Any mathematics at all to it。

 And I'll make clear with the comment else， if not lowercase makes clear what's going on there。

 Alright， let me go ahead and make uppercase in my terminal window dot slash uppercase。

 Let's type in my name， All lowercase。 And I get back， David， Oh minor bug。Couple bugs， actually。

 Let me fix my spacing。 I think I want another space after the word after。

 And at the very bottom of my program， I think I want a backslash N。 Now， let's rerun。

 make an uppercase， dot slash uppercase， enter D A V I D。 And now it's forcing it all to uppercase。

 Meanwhile， if I do it once more and type in name capitalized。

 it's still going to force everything else to uppercase questions。😊，Oh， I'm a nitty。 Okay， thank you。

Yes， I misspelled after otherwise my liing， my alignment would have worked。 So let's do this again。

 make uppercase， if only so that we can prove it's the same D A V I D and all lowercase。

 And there we go。 That was， thank you。 the intent。😊，Alright， so it's kind of a little trick。

 But this is kind of tedious， right， Like Microsoft Word Google Docs all have the ability to toggle case from uppercase to lowercase or lowercase uppercase。

 It's kind of annoying that you have to write this much code to achieve something so simple。

 seemingly in so commonplace。 Well， it turns out there's a better approach here too。

 in addition to there being the string library。 there's also the C type library in C type dot H。

 another header file， there's a whole bunch of other functions that are useful that relate to characters characters in ASi。

 So for instance， if we go ahead and use this。 as follows。

 I'm gonna go ahead at the top of my file here and include now C type do H。

 It turns out there's gonna be functions via which I can actually ask these questions myself。

 For instance， in this next version of the program。 I don't need to do any of this clever。

 but pretty verbose math， I can just say if the is lower function。

 which comes from the C type library passing in S bracket I returns。😊。

True will then convert the letter to lower uppercase by subtracting 32。 But you know。

 I don't even need to do this mental math or math and code。 I can also from the C type library。

 use a function called2 upper， which takes as input。

 a character like S bracket I and let someone else's function do the work for me。

 So let me go back down to my terminal window here。 let me make uppercase now。

 dot slash uppercase enter before D V I D。 This now works too。

 But if I really dig into the documentation for the C type library。

 you'll see that you can just use the is lower function on any character and it will very intelligently only uppercase if it is actually lowercase。

 So someone else years ago， wrote the conditional code that checks if it's between little A and little Z。

 So knowing this， And you would see that indeed in the documentation。 I don't even need this else。

 I can instead just get rid of this whole conditional。

 tighten my code up significantly here and simply say。😊，Printf using percent C。

 the two upper version of that same letter and let the function itself realize if it's uppercase pass it through unchanged。

 if it's lowercase， change it first。 and then return it。

 So now if I open my terminal window again and clear it， make uppercase dot slash uppercase。

 enter D V I D and we're back in business。 So again。

 demonstrative of how if you find thats coding is becoming tedious or you're solving a problem that like surely someone else is solved。

 odds are， there is， in fact， a library function for。

 whether it's from C 50 or from the standard library that you yourselves can use。

 And unlike the C 50 library， which is indeed C S 50 specific。

 which is why Kang needed to know about L C S 50， many of these libraries just automatically work。

 you don't need to link in the C type library， you don't need to link in other libraries。

 But nonstandard libraries like C 50's training wheels for the first few weeks。

 we do need to do that。 But make is configured to do all of that automatically。For you。Allright。

 in our final minutes together， let's go ahead now and reveal some of the details we've been rub sweeping under the rug about main。

 I asked on week1， that you just sort of take on faith that you got to do the void。

 You got to do the int， you got to do the void and all of that。 Well， let's see why that actually is。

 So main is special。 insofar is in C。 It is the function that will be called automatically after you've compiled and then run your code just because not all languages standardize the name of the function。

 but C and C plus plus and Java and certain other ones do in this case。

 Here is the most canonical simple form of main， we know that including standard I O dot H just gives us access to the prototypes for functions like printf。

 but what's going on with int and what's going on with void。 Well。

 void and parentheses here just means that main。 And in turn。

 all of the programs we've written up until this moment， do not take command line arguments。

 Li every program we've written dot slash a dot out dot slash hello。😊。

t slash scores dot slash everything else。 I have never once typed another word after the name of our programs that we've written in class。

 That is because every program has void inside of these parentheses telling the computer this program does not take command line arguments。

 Word after the program's name。 That is different from make and code and C D and other commands that you've typed with words after them their names at the prompt。

 But it turns out the other supported syntax for the main function and C can look like this too。

 which at a glance looks like kind of a mouthful， but it just means that main can take zero arguments or it can take two if it takes to the first。

😊，Is an integer。 And the second is an array of strings by convention。

 those inputs are called Arg C and Arg V。 Arg C is the count of arguments that are typed after the after the program's name。

 Arg V is the argument vector， Aka array of actual words。 In other words。

 now that we have the ability to use arrays， we can get0 or one or two or three or more words from users at the prompt when they run our own programs。

 So what do I mean by this。 We can now write programs that actually have command line arguments as follows。

 Let me go into V S code here and close our old program uppercase。

 Let's write a new simpler program here In my terminal called greet do C and just greet the user in a couple of different ways。

 So I'm going include initially Cs 50 do H， And then I'm going to include standard I O dot H here。

 Then I'm gonna say in main void without introducing anything new just yet。

 I'm gonna ask the user like we did last week for。😊，Return value from get string， asking them。

 what's your name。 As we've done so many times。 Then I'm gonna to say print F， hello。

 comma percent S back slash N spitting out their answer as follows。 same program as last week again。

 I'm gonna make greet。 I'm gonna say dot slash greet。 And I'm prompted now for my name。 I hit enter。

Notice that I did not take any command line arguments。 The only command I ran was dot slash greet。

 No other words。 Let's now use this new trick and actually let the user type their name when they're running my program rather than waste their time by using get string and prompting them。

 Let me go into my editor here。 Let's get rid of the C 50 library。

 Let's get rid of my use of getstring。And let's simply change void to int Arg C。

 then string Arg V open open bracket closed bracket。 That's all down here。

 Let's simply print out Arg V bracket 1 for reasons well soon see。

 The only change that I'm making really is changing the prototype for main from the first version。

 which we've been using for like a week in a bit now to the second version。

 which is the only other version supported。 I'm gonna go back to my terminal window now。

 make greet and darn it。 I shouldn't so close。😊，Why did I make。

 how do I fix the mistake I accidentally made。Yeah， and back。Oh， no， in front。Yes。

 I should have kept the C50 library because it's in the C 50 library that string is defined。

 So include C 50 do H in week 4， we will delete that line for real and actually show you what string actually is。

 I promise it to be start class。 that string is a term of art， but it's not a keyword in C。

 but it will see what it means in a couple of weeks time。 Okay， let me fix this。

 make greet dot slash greet。 But now I'm gonna type before I even hit enter my actual name。

 And when I hit enter now， I see hello comma David， if I instead do dot slash greet Kelly enter。

 now I see hello comma Kelly。 if I do nothing like greet enter， I just see hello null。

 which is not the same null as before N U L， this is N U LL for reasons will' come back to before long。

 but clearly printfno somethings going on， there's no actual word there。 Why though。

 did I do R v bracket1。 Well， it turns out that just as a feature of C。

 if I recompile this program and do dot slash greet。😊，And type in nothing else。

I'm going to see something kind of curious。Hello dot slash greet。

 because automatically the zero location in the Argv art variable will automatically contain the program's own name。

 Why is this useful， if you ever want to do something selfreential。

 Like thanks for running my program or you want to show documentation for your program and the name of your program that it depends on whatever the file itself is called。

 you can use Argv bracket 0， which will always contain the program's name。

 no matter what the file has been named or rename to。

 But we can fix that null issue now in a couple of ways。

 So Arg C is the other input that I said now can exist。

 which is the count of arguments at the prompt。 So if I want to check if the user actually type their name。

 I could say something like if arg C equals equals2。 Well。

 then and only then go ahead and print out their name else。

 let's just do some clever default like print F quote unquote hello world or heck nothing at all。

 This version of the program now is a little smarter。

 Because when I run make greet and do dot slash greet of my name works exactly as intended。

 But if I forget。😊，And only do dot slash greed， it's going to say hello world。 Moreover。

 if I don't quite cooperate and I say David Main enter。

 it similarly just ignores me because Arg count is not two anymore。 It's now three。

 So Arg C contains the total numbers of words at the prompt。

 But the first one is always the program's name。Question。Sorry。

 can you say that once a little louder。Why is it information that we just have or？Oh。

 so the short answer is just because like the definition of C。

 if you look up the documentation for C， you can either define main as taking no arguments with the word void。

 or you can specify that main can take two arguments and the compiler and the operating system will just ensure that if you provide two。

 those two variables。 A C and R V will be filled with those two value values automatically。

Someone else decided that， though， that's just the way it works。 You can't come up。

 You can't put three there。 You can't put four there。 You can change the names of those variables。

 but not the types。Because of this convention。 Allright， so with that said。

 we seem now to have teased apart what the words between parentheses next to Maine do。

 the socalled command line arguments。 What about the， oh， Oh and actually。

 yeah we'll come back to that。 So what about the words to the left of Maine's actual declaration。

 So here we have。 sorry。Oh， yeah。 So it， it。So there's one last feature of main Then It's the actual value It returns up until now every program I've written starts with int main something。

 int main， something。 What is that int。 we have yet to use it technically。

 the value that main returns is going to be called a socalled exit status。

 which is a numeric status that indicates success or failure。

 Numb are everywhere in the world of computing。 So for instance， here's a screenshot from Zoom。

 whereby if something goes wrong with Zoom， like you have bad internet connectivity or something like that。

 you might see an error code like 1，1，32。 That means nothing to normal people unless you Google it。

 look up the documentation， but it means something very much to the software engineers who wrote this code。

 because they know oh shoot 1132 means this error they probably have a spreadsheet or a cheat sheet somewhere that converts those codes to actually useful error messages。

 And frankly， in a better world， they would just tell you what the problem is rather than just say report the problem and mention this number。

 That said on the web。 odds are you're familiar with this number 404。

 which is also a weird thing for so many normal people to know。

 But this generally means file not found。 It's a numeric code that signifies that。

Something has gone wrong。 Exit status isn't quite this， but it's similar in spirit in mainine。

 you can return a value like 0 or1 or2 or something else to indicate whether something was successful or not by convention program a function like main return0 on success。

 if all is well。 And that leaves you then with like several hundred possible things that can go wrong because you could return one to signify one thing2 to return another。

3 to signify another。 And so long as you have a spreadsheet or cheat sheet or something。

 you can just keep track as the programmer as to what error means what So what does this mean in real terms。

 So if I go over to VS code here， let me implement a relatively simple program our last called status do C。

 So in status do C， I'm going go ahead and use the Cs 50 library at the top。

 the standard I O library at the top And then inside of int main and with our new format in A C string R V square。

ets insideside of main， I'm gonna now do the following。 If A C does not equal to。

 then I'm going to go ahead and print out this time a warning。 I'm not gonna have some silly default。

 like hello world。 Let's tell the user that they didn't use my program correct。

 And I'm gonna say printf missing command line argument。And we'll assume they know what that means。

 Then to signify an error。 I'm gonna say return one。 It could be two。 It could be3。

 but this is the first possible error。 So I'm gonna start simple with one。 Otherwise。

 if Ay does equal to。 And I get to this part of my code。

 I'm gonna say hello comma S backlash n and pass in A V bracket1 just like before。

 and just to be super specific， I'm gonna to return0 to tell the computer。

 the operating system that this is success，0 signifies success。 any other value signifies error。

 which is a little demoralizing because means there's sort of only one way to get things right and like hundreds。

 thousands of ways to get things wrong based on the size of the integer you're returning。

 Let's make status now， let's do dot slash status。 and this is a little magical。

 but let me go ahead and cooperate initially， I'm gonna type in my name， David。

 And I'm gonna see hello comma David Most people wouldn't know this。

 But among the commands you can type at your terminal are this one here and。



![](img/40cfbb95e7fe840f46b181fa68459398_50.png)

F and I， the Ts and I would do something like this。 We， after running your code。

 can do echo space dollar sign question mark， and we can see secretly the return value that your program returned。

0 in this case。 Meanwhile， if we do this again， dot slash status， do slash status。

 and let me not type my name this time。😊，When I do this， I see missing command line argument。

 What value should the code have returned then。One， so let's see echo dollar sign question mark。

 there's the one。 So even after just one week of CS S 50。

 if you've ever wondered how check 50 knows if your code was correct or not among the ways we check for that is by checking this semi secrett status code。

 this exit status， which isn't really a secret。 it's just not displayed to normal people because it's not all that enlightening unless you're the software developer who wrote the code in question。

 But this means we could return one in some cases or two in other cases or three or four and yet others。

 And these command line arguments are sort of everywhere。 And in fact。

 a program I skipped over a moment ago was gonna be this。

 there is no academic value to what you're about to see。

 But another program that takes command line arguments is known as cow say。

 And this is sort of very famous in computing circles because it's been on systems for many years。

 cow say is a program that allows you to type in a word after the prompt like Mo and it will print out what's called AskI art an adorable little cow with a speech bubble that says mu So kind of evocative of like scratch。

 but it takes。😊，Other command line arguments， not just the words that you want to come out of its mouth。

 but even the appearance that you want it to have。 So， for instance。

 I can say dash F duck and run it again enter。 And now I have a little cute duck saying move。

 which is a bit of a bug。 So let me change that to quack。 for instance， instead again。

 no academic value here。 it's just fun to now play with the various options。

 but we really want to have fun with this。 we can do another one。

 So cow say dash F dragon and we can say something like Ra。

 And now we have this crazy dragon appearing on the screen， which is to say again， no value here。

 It's just fun to play with command line arguments sometimes And how is cow say doing this Well。

 someone wrote code， maybe in C or some other language using Arg C and Rrg v and poking around at their values and maybe a conditional that says if dash F value is dragon then print this graphic。

 else if the value is duck， then print this other one。

 it all boils down to the same fundamentals of week0 of functions and conditionals and loops and bullolean expressions and the like。

 it's just。

![](img/40cfbb95e7fe840f46b181fa68459398_52.png)

Being composed into more and more interesting things。 And indeed。

 in closing among the other interesting things we'll play with this week to come full circle is that of cryptography。

 the art of scrambling information so as to have secure communication。

 so important nowadays with passwords and credit card numbers and personal messages that you might want to send and we'll have you explore through code。

 some of the algorithms via which you yourselves can encrypt information。

 And there's a number of ways we can do this form of encryption and they all boil down to this mental model。

 you've got some input like the message you want to send。

 and you want to encipher it somehow encrypt it somehow so that no one knows what message you've sent。

 So you want your plain text， which is the human readable version in English or any other language to become cipher text ultimately。

 So the code you'll be writing this week is inside of this black box。

 some kind of cipher in algorithm that encrypts information so that you can do exactly this。 Now。

 the catches that you can't just give it plain text and run it through an algorithm and get cipher text because you need to somehow have a secret。

 typically for encryption。😊，To work like if I'm gonna send a message to someone in back。 Well。

 I could just randomize the letters that I'm writing down。

 But how would they know how to reverse that process。

 Probably what we need to do is agree in advance that you know what。

 I'm going change every a to a B and every B to a C and a C to a D and a Z to an A。

 I'll wrap back around at the end of the the alphabet。 It's not very sophisticated。

 but who no middle school teacher， if they intercept to kids passing notes in class。

 are going waste time trying to figure out this cipher。

 but it does presuppose that there's a secret between them。

 the number one in that case because I'm changing every letter by one place。

 So how might this work Well， if I want to encrypt the word high H exclamation point and my secret key with someone that I've come up with in advance is one。

 I should send the cipher text， I J exclamation point。 Now this is a simple cipher。

 So I'm not really encrypting the punctuation， which may or may not be a good thing。

 but I am encrypting at least the alphabetical letters。

 But what does the recipient then have to do to decrypt this message when they see on paper。 I J。

Exlamation point。 How do they know what I said。 Well， they use that same key， rather。

 they use that same key， but subtract。 So B becomes A。 C becomes B。 A becomes Z and so forth。

Essential inverting the key from positive one to negative one。 Of course。

 slightly more secure than cipher of one a key of one would be 13， and in fact， in computing circles。

13 has special significance。 Ro 13 R O T 13 is an algorithm that's been used for many years online just to sort of avoid spoilers like Reddit might do this or other websites where they want you to have to do some effort to see what the message says。

 but it's not all that hard。 You just have to click a button or write the code that actually does this。

 But if you use 13 instead， you wouldn't get you wouldn't get I J。

 you'd get U V because you and V are 13 places away from H and I respectively。 But again。

 we're not touching the punctuation。 twice as secure as Ro 13， arguably should be rot 26。 Oh sorry。

That was the setup to a stupid joke。 But or we could send something more personal。 Like， I love you。

 And the message comes out like that。 slightly more secure than that would be Ro 26， no。😊，No。

 why because it's the same thing。 It literally rotates all the way around A becomes A B becomes B。

 So there's a limit to this。 But more seriously that speaks to just how strong this encryption is or is not because if you think about this now from an adversary's perspective。

 like the teacher in the room intercepting the slip of paper。 how much work do they need to do Well。

 they just try all possibilities， key of one key of2 key of3 do dot dot key of 25， and at some point。

 they will see clearly that they guessed the key， which means that cipher is not very secure。

Nonetheless， what we're talking about is historically known as the Caesar cipher because back in the day。

 when Caesar was communicating by legend with his generals。

 if you're the first human on earth to come up with encryption or come up with this specific cipher。

 it doesn't really matter how not complex it is if no one else knows what's going on nowadays。

 it's not hard at all to write some C code or any other language。

 they could just brute force their way through this。 So there are much more sophisticated algorithm。

Nowadays， then simple rotations of letters of the alphabet， as we'll soon see。

 But when it comes to decryption， it really is just a matter of reversing that process。

 So this message here， if we rotate all the letters in the opposite direction by subtracting one will be our final flurs for today。

 There's a bit of a hint there， which will reveal that this message and our final words for us as the clock strikes 4。

15 is going to be the you becomes。T and the I becomes H。 I'm the only one this is amusing。 H， I I S。

 W。A S， C， S 50， and this was C， S 50。 We'll see you next time。

