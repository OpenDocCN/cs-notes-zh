# UCB《Linux系统管理实践课程｜UCB Linux System Administration Decal 2025》中英字幕（deepseek - P2：Lecture 2.zh_en - GPT中英字幕课程资源 - BV1wj59zGEMq

Okay guys， can everybody hear me？Okay下。On Zoom， theres something in the chat if you can。Okay。

 and then can you guys see the screen share you're good。For the slides。



![](img/90c65581321e0efa29e6fee4e58972bc_1.png)

Okay， perfect。I want to make sure okay。啊。Hello everybody， our TV broke like a week ago。

 really unfortunately， so you guys are going to have to go on the website to follow along with the slides。

They should already be posted decalboocCF。Iio。嗯。Yeah。

 and today's lecture first half is going to be done by me， second half done by Albert。Yeah。

 let's get started。

![](img/90c65581321e0efa29e6fee4e58972bc_3.png)

Okay。So Lab two and vitamin two should be already released and they're going to be due this Saturday on the topic contained in today's lecture on lab or yeah。

 Le lab period， lab one and vitaminmin one have been graded。

So you should have your scores back for those if you submitted them， hopefully you did。and yeah。

 like I said， the TV is broken， if you're having trouble point up the slides， let one of us know。

Or finding them。U。And then yeah， the recording for this lecture will be posted on the website as usual if everything goes according to plan。

Does anybody have any logistical questions about the course complaints？I don't know， woes。No。Okay。

 we're going to move right into the content for tonight， which is on She scripting。

And of course oh wait no also we have the course resources on your facilitators most of us can be seeing in the corner the rest of tonight the next hour。

 ask us if you need help with anything at all。With the decal but also don't forget about the Ed and the grade scope needs to be added to either please let us know at this point just in case you aren't and you can also contact us on Slack in the decalL channel and Discboard it's called decal general materials are available again everything you ever need is on the website and yeah we'll be around for an hour afterwards。

And perpetuity for the rest of the semester after lecture， so need help， stick around。Okay。

If you want to follow along with what I'm doing in lecture to make sure that I'm not pulling some strange witchcraft and that this is real。

 you can SSH。Into。Our public login server， which is your OCF username at SSocCf。Io or brickletedduu。

 or you can just open your own terminal locally， whatever you did to complete last week's lap you can just do that again it's not going to be much more complicated in terms of what it requires。

And yeah， feel free to ask any questions in the chat or just raise your hand if you're here in person。

Okay。嗯。Yeah， so today we're going to cover what bash is and then several aspects。

 most important aspects of。Fsh and back scripting。So。Why should I bother learning to scripts？

As a ci admin。Well， number one， let's say you are a cis admin for the sake of this class。

 maybe you're not， maybe you're just your software engineer brain。

But say you're doing someaddmin tasks and there's particular commands that you've learned hopefully so far。

 envy copy all these different things and you have to run them pretty frequently or you find that you have particular tasks。

 you need to repeat weekly， you need to take a backup， move files， rename things， etc。

It's pain in the butt to like open up the terminal。

 manually type that out or like copy paste the commands from something and run them yourself and you don't want to do that。

Instead， you can。Write a ba script by step by step set of instructions so that。

They will get executed for you as soon as you run the script and you don't have to run。

All of these individual tedious commands， basically， same reason you learned it。



![](img/90c65581321e0efa29e6fee4e58972bc_5.png)

嗯。So yeah， next up we've got like a little here yeah， next slide， a little diagram of like。

XKCD comic of。In theory， how writing a ba script should work， which is like， oh。

You spent a little bit of time writing it and then automation takes over and you never spend any time doing the thing again。

 but in reality usually you write the thing and then you're constantly developing it and tweaking it and it ends up taking more time than you thought it would hopefully this is not the case but that's the joke and。



![](img/90c65581321e0efa29e6fee4e58972bc_7.png)

Often the case so。Yeah。Let's get into what bash is。So bash is a shell。

What does that mean it's an expanded version of another type of show called the Bnegan show。

 which itself is based on。I believe me， I've had it written down。Like Thompson show。Yeah， anyway。

 one of the first Lake Uni。呃。I think it was the first Uni shell and that one。

 the original one had like no scripting features， it was very bare bones again you could run like the most basic of basic commands at pithping and things。

 but that was about it and then someone built on that created the B shell and then someone built on that shell created the ba born again shell。

嗯。And the nice thing about bash is not only can you run commands， you know。

 manually typing it in with your fingers， but you can also use it for scripting taskss。Okay。So。

How do I run the script I wrote I haven't written anything yet。

 but let's say I wanted to run something when you have written something。You can do it two ways。

 you can type out bash and then put in the path to your bash script as an argument the same way you would when running other commands。

Usually your ba scripts end in the file extension dotsh。嗯。Or you can also。

Make the file executable by running this command CH modD。Sag plus H and then the pass to the file。

However， doing this will require a shouldang up start your file， which we'll get into in a second。

Does anybody have any questions so far on making the difference between these two methods？嗯。Yeah。

They're essentially the same thing except like the former does not require you to have a shaang at the start of your file。

 the second one does， and the second one is like a more general way of executing any type of script regardless of file extension。

 but the former will actually run specifically the bash interpreter to interpret your script or say Python and then your file name that would specifically execute your script with the Python interpreter do s will just execute it based on what your script tells it。

Thanks you it away。Hopefully that makes sense。

![](img/90c65581321e0efa29e6fee4e58972bc_9.png)

嗯。Yeah。Okay， so the Shaang thing i've been talking about a really fun word to say that is a little thing that goes at top of your file and it specifies that this file is not a text file or a PDF of your homework。

 it is a script of some kind whether that's python ba regular。What is it， I don't know。

Regular born shell， whatever that may be。啊。Yeah， it's very important to include this otherwise。

The terminal is not you's not going to know what。Do in order to run script。Yeah。

 comments in bash are done with。A pound sign without the exclamation point。



![](img/90c65581321e0efa29e6fee4e58972bc_11.png)

It's pretty straightforward next slide。Yeah。What like essentially what it does is it just takes the comment at the top and then just do dot slash that thing then the following Is that what it what it does are you asking about what the Shiang does。



![](img/90c65581321e0efa29e6fee4e58972bc_13.png)

呃。Sbang is looking at like， it's giving like a particular file path of like。

Where your interpreter is and it's calling that interpreter on the file itself that makes sense so you can see like bin bash that's where your bash interpreter is。

On your system。你说して我的把的人。Oh。Not that I've ever used but。Yeah， I think it's mostly just for this。

Sp comment that tells you what interpreter to call。P this file。Yeah。

 I think does I answer your question does it make sense okay。

 maybe there are other special uses for it I haven't done like extensive research into the chaang but。



![](img/90c65581321e0efa29e6fee4e58972bc_15.png)

This is just yeah。Maybed be fun to look into why it exists。



![](img/90c65581321e0efa29e6fee4e58972bc_17.png)

Yeah， okay， next up like any good scripting language。

 sometimes you need variables in order to not repeat yourself because that's the whole point of。



![](img/90c65581321e0efa29e6fee4e58972bc_19.png)

That's your thing。Okay， so shell variables are a little funky you have to be very careful just in general when writing batchsh about white space a lot of errors people make in labs are usually because of。

Just like little syntax issues so if you do end up running into something with your script for this lab and you're not sure what's wrong be really careful take like fine tooth combe over your syntax。

 make sure that all the spaces of where they're supposed to be quotes， etc。U。And yeah。

 as you can see here on this slide， the shell variable slide， you can also go on zoom if you're like。

Want to see exactly which slide I'm on。Let mes see。诶。

We set the variable name to the string value and then we echo。The value of name， which is value。

And then ECcho will display。Whatever text you tell it to。

Another very useful command you could even run echo outside of a batchsh scripts just in your terminal so any of these commands that you see in the scripts again if you ever want to test something real quick because you're curious about what it does feel free to just open up a shell and just run it real fast and see what happens and then you can put it in your。

File。嗯嗯。Yeah， variables in bash are untyped， you just have to know what you're doing operations areual。

Yeah， adding something together like this food variable。

 which is equal to one with the number one will result in an error because everything is as strange and fashion。

嗯。Yeah， you can use the expression command to evaluate expressions pretty much on every system part of coreuttails。

 there's some things you have to import that might not be installed by default but。This is yeah。

 as you can see here on this particular slide， a little hard to see。We set some variable through。

And then we evaluate food plus one， and then that gives us our correct answer up two。

So on the previous slide。The whoops。You can kind of notice the difference between。

Straight trying to add the variables versus evaluating an expression， what you should do。Yeah。

 and finally you can take in user input using the read command dashP is to prompt the user。

 so they're not just like sitting there staring blankly。

At the terminal and like unsure of what to do， it'll like tell you input a number or something or you can help user it to input a number。

嗯。Yeah， I'll slow down for a second， does anybody have any questions about a couple of commands that have been covered so far？

嗯。Again， you can always come back to these slides for reference when you're working on your lab。

 we're just rapid firing some stuff at you that's probably going to be useful。嗯。有边好能讲唔条嚟先。

expressionOh core u I think that's for alluding tonu core us right yeah so Linux is like technically news slash Linux so it's like Linux is like the kernel and Gnu is like。

The set of。Commands that we're using here， like like read the common ones。

 I don't know how to like describe it well。Thank。And it was like all the extra stuff that was built around Linux to make it work。

 including。I believe a lot of。Fash commands are part of Benco u's。Yeah， I don't know。

 core utility that uses。When。Andtertracting struggle。Yeah， again。

 if you remember the guy Richard Staman， it was him。Who created that， just the library？

But you'll find it install on pretty much everything。Does that answer your question okay。

 any other questions for keep moving through variables？And user input。No， okay。Okay， finally。

 we have the subshelf， which means that like okay。Say I want to evaluate some expression one plus one。

 which is too difficult to do in my head and then I want to take the result of that expression and feed it into something else the way you do that is visible on the slide。

You put fronts around it。Dollar sign。呃。Becomes that variable， echo value variable。嗯Yeah。



![](img/90c65581321e0efa29e6fee4e58972bc_21.png)

Just substitute size。嗯。And then finally， we have conditionals。



![](img/90c65581321e0efa29e6fee4e58972bc_23.png)

嗯。So。Conditionals are similar to conditionals in any other programming language language you use。

 however bash is again， kind of old kind of idiosyncratic has a fewqui that you'll want to be mindful of。

So you have a。Additionalitional checks， which evaluate an expression。

 you can do test and then the expression in order to。

Run this you can also do like brackets in order to do so and then yeah the exit status of something that's true is going to be zero and false is going to be one so please keep that in mind it's kind of confusing and backwards。

Yeah， that's like number one thing you might get trip up on。

Here if you like arguments you can supply the test command with。Before your expression that you're。

Evaluating。You know， equal， not equal to。Less and greater than stuff you're hopefully already familiar with or if not。

Again。Iton't be hard to wrap your head around。嗯。So here's an example on the next slide of。

Do ways you can run the test command so here you're testing if zero is equal to zero and then echo color sign question mark basically just means like echo the exit status of the command you just ramp。

So in this case， it's testing of zero is equal to zero， which is true， output zero。

Test of zero equals one echoes one because that's false。U。

Does anybody have any questions so far about tests and conditional checks okay， we'll keep moving。

And nothing in the chat either， so we're good。我明白。Okay， now we have Boolean operations。

 hopefully familiar to you， if not， today's going to be a lot of learning。

Essentially you have two ampers sands。For the end operation， which means like both。

Things have to be true， for example。In the example on the slide。

 you want the left expression and the right expression to be true for the entire thing to evaluate to true and then to。

Long lines， I forget get the exact name for the character。呃。Is the or operator？Yeah。

 either one of the two expressions has to be true。And you can also use these as arguments rather than。

Um。The symbols given。一。If you're using pest or brackets。Yeah， and then of course。

 it wouldn't be a good scripting language without if statements， pretty necessary， pretty vital。

You start an if statement， you have the condition like it's evaluated。

And then you have the what it does if that condition evaluates is true。

 and then you end the statement with FI， which is if backwards。啊。Yeah。

 hopefully just being able to review these slides give you an idea of how to structure your own code there's only so much I could say about these commands and if you ever。

而且可以。Doar one。So right。I believe。holdold on。

![](img/90c65581321e0efa29e6fee4e58972bc_25.png)

Let's check。But It want to say something wrong。Do I have a terminal？Excellent。Let's see。

The one gives you the first argument。All right， okay， it gives you with one more。Wait wait。

 gives you the first argument from。Right， right， right， okay， that answers your question， hopefully。

嗯。是。Yeah， so if I were to run like。Dash。My test do S if that's the name of my script and then the users to some argument like eight as a number。

 it's going to test if eight is equal to 79 dollar sign two would the second argument and so on。Okay。

And you'll need to know this because again what you're doing in the lab is going to require you taking in arguments from user。

Yeah， arguments or parameters are just like stuff that follow。The initial commands。

 and you can always do men commands。Okay。See what those are。Yeah。

 of course you've not just got if statements， you've got F statements。Say if。

The condition evaluates a C， so in this case， if the user input is equal to 79， it'll echo nice else。

 it'll echo the word bararn。Yeah。嗯。Elsse gets even more complicated， like I something。

So in this case， it's checking if someone's equal to 79 Yeah， it's for the decal you can take a seat。

So I'll break down this piece of code line by line， which is again checking if the。

User input is equal 79， then it's going to echo。Nice into the terminal else it's going to check that equal 42。

 echo the answer and if it's neither of those two numbers。It's going to echo what are numbers。

And then don't forget the F at the bottom。嗯。And then finally， you have case statements。

Are you guys ready to be run through one more script and then we're going to move on to next topic Okay in this case it's going to again use the read command we saw earliers the。

Prompt are you 21 and then。The user input is going to get stored in the variable answer。

It's going to evaluate answer。See if it is equal to yes， if it is will echo I give you cookie。

 if you're not 21 it'll echo that's illegal。The answer is are you it'll echo let's not and if it's anything else it'll echo please answer and again asterisk stands for wild card value it could be anything so if you put that at the beginning before the rest of the cases。

It would be evaluated1% of the time。嗯。Yeah。Hopefully the syntax of this makes sense and again you spell case backwards at the end to signal that you are done in writing your cases。

Does anybody have any questions on case statements or the content covered up to this point？Nobody。

 yeah。No。Okay。At this point。My co facilitator Albert is going to take over and explain loops。Yeah。

Yes。All right， so now let's move on to talk about loops。

I guess this is sort of similar to the conditionals except your sort of is kind of like if if anyone if anyone here has done like 6218 before。

 essentially you're just like looping through like。Something it's the same logic here。

And the syntax slightly differs。Although not really， like if you have like a list over here。Then a。

You can do like sheep is like one dose tray， and then 4 S in sheep。 You can like echo。

Dollar sign S cheap so essentially here you're just like creating a variable S and using it like you would use a variable I in a for loop。

嗯。We also support ranges， but it's a bit different than in Python。And a lot simpler。

 you just have like a bracket than one than like two dots。 the two dots are important。

 you cannot have like more or fewer than two dots。 It has to be exactly two dots and then like。

So it's like L dot dot R specifically inside the brackets， they curly braces。

 and then you just evaluate something in there and we should be good。Next， while loopops。

So for example， for this example， we have like wild true so what do you think this would？This play。

Yeah， nightmare yes， it print out a nightmare infinitely because the nightmare never ends。And。

I think Ive forgot to go over this one， so for four loops， what do you think this is going to output？

嗯。啊，听到没问题。Yes， but what is the number exactly 5， yes， that is correct。Now it's time to exercise。

 let's write a script that copies our files in our copies files in our current directory into new files with new propended to the constant。

Prepened to the contents。Okay。So first， I think we should start by writing， okay。

 or should I give you some time to think about this？Okay， it was's probably just in。

Kind of just the starting thing is in the next slide where essentially we are copying files in our current directory。

So。Essentially， we copy the file to。Some new file called like new underscore and then the same file name。

 we just iterate through all the files。In the files list， which we get through our LS command， right？

Yeah， actually， how does this a suchhe thing work。 Like I Im so questioned。

 So one does it onewn like another shell process and two， like。

 how do how do they know that this is supposed to return done on this。No。

 because it's like dynamically typed， so basically if there is if it's not a list。

Then the thing is just going to complain very loudly and then your thing just errors there it doesn't compile really it just runs like every single thing and expects something else as like the result so it's just known that Yeah and it's also LS so usually that shouldn't fail。

Wait， then what about my first question， Like does the。If you put dollar sign something。

 does it for another shell or does it just evaluate that thing know I believe it's like you just run like a process inside and then like wait for it to finish and get the result。

对对的。It doesn't like do like any multi threading because that would kind of like。

Break the linear order， right？Because like so you just exit as the function code is yeah， okay。嗯。

Next topic we're going to do is going to be functions。So for this one， we。

Let me just show you the syntax here so you have like。Essentially， just function your function name。

 this is kind of like Python except you don't have like。

A given return value over here and you can put anything inside。Now， after this。

 we can just call the function with。Sort of like a command almost。😡，And it'll print out， hey。

 there's this ad。Moreover， notice the dollar sign one here this does not mean you have to pay basha $1 to use a function。

 this means you have like the dollar sign essentially creates like a new argument and the first argument that you pass in in this case is cis admin decal so。

The R sign 1 is going to refer to the first argument of ciss admin decal。

 which basically just stands in。I guess as a variable。So then the result is going to be， hey。

 there's this admin decal。Moreover， notice that script arguments are stored the same way as with functions。

So for example。If in the terminal， you have like LS dot， then you would get everything over here。

 like let's say B dot text， A dot text， C dot text。Then let's say we want to pipe sort。😡。

Pype the result of LS。Doar sign one。Into the sort function。In this case。

 our script essentially itself function acts like a function and turns the。Okay。TTs like。

the argument in the console？For example， dot in this case into its first argument and essentially and essentially runs with。

Dot as like。A callable argument， I guess， does that make sense？五分钟。For the previous side。

 the grade function the screen not accept parameters。 like can we like arguments to it。

The arguments are going to be you don't need to add anything in here， you just need like。

These are going to be how you call the arguments， I guess， Okay， so there's really no need arguments。

You don't need to like define like new variables to use arguments， for example。

And then here essentially。If we were to do the same thing。

 we would have the result of this passed in。And then output it as the output for script。sh。

Does anyone don have any questions so far？I give this one index。zero indices are one index。

 but you can also think of this as the first argument as it is zero index。

 but the first argument is the command itself。喂。Final topic is going to be about streams so essentially。

Basically， the way this works is。You have like up。We were sort of like trying to append or like。

Get results from like files， for example and。The way we can edit files with commands is through is through streams。

 so there are three main。We're not three， four main。Important。Operators。

 so the first one is going to be redirection， which。Outputs the result of the file echo hello。

 for example。Basically， out was the result of the command。Into a file。The next one。

 append is going to append the output to a file。And if the file is empty。I's the same as redirection。

The difference between these two commands is essentially if you use one greater than sign。😡，Then。

You essentially get rid of the entire。Existing data in that file。

 but if you use two greater than science， then the new data essentially gets appended to the oil data。

 so the old data never goes away。Does this make sense to everyone？All right， and then。

We can also redirect the other way with like less than sign， which takes input from a file。

 so if our command， let's say sort takes input then of。😡。

We would want to essentially get that in and we want to pass the input in somehow we could essentially use some input file as like。

A stand for our。So as as a stand in for like compared to like typing everything into the。

Into the terminal so。Essentially， you have a。File that you are redirecting to the input。And finally。

You can essentially do the same thing as before， but with the output of an existing command。

So for example， in this case。You would run command1。

Take its output and use that as the input for command2 so you're essentially。

Running these two commands sort of like。In relation to each other， I guess。If that makes sense。

Are there any questions about like streams？导人。我不是。No， okay。Then if this all makes sense。

 there's this final slide about additional notes。First off， for。For Python？You can use。

Like arc parts to get easy CI fabric to get easy deployment， salt to get。

 I don't think I need to go over all of this。😡，There are just a couple of important like or important to know like Python She tools。

You can also you should also use Bsh when the functionality you want is easily expressed as like a composition of command line tools。

 so if you don't need any like advanced functions， then Bsh works fine。😡。

You should use Python when you need heavy lifting， so more complex control structures。Messier states。

 recursions and objects once you get to like。Anything more than like just the basic like typing things in the command line and you want to automate that。

 then you should start using languages like Python or even more complex languages。😡，And finally。

 I'd just like to make a note about other shells。What we were talking about。

In batchash has been in batchsh so far， but a lot of this also carries over to other shells like Zhell。

 fish and corn shellll。But there are some like subtle differences between。Between these shells。

 as they're all like different derivations。Of the same shell， which is S H。

So fish is known to be like extremely devviiant and it has like a couple of like。For example。

 subshells in fish just do not use like the same notation as in most other languages or as in most other shells。

So if you're using fish as your primary shell， you should be careful about what you're running to make sure you're not like using the incorrect syntax。

 generally for the basic commands I've stated above here， the other shells should be a bit similar。

 but there's other like trivial things that may screw it up。



![](img/90c65581321e0efa29e6fee4e58972bc_27.png)

For the purpose of our labs and et cetera。We will be using like our solutions will all be using bash。

But you can feel free to try another shell if you think that's fun。And finally， just some resources。

Maybe a varying use。 The most useful one is Google。The second most useful one is the man page。So。

Yeah。嗯。I think that's all for this week， are there any questions？About anything that we talked about。

do有部嘅批登第五 on嚟。Which one would you comment， I guess。I think that a lot of these are just like。

 I'm not totally sure why this slide's Oscar， but just it's just sort of to begin you to know that there are other tools that like in Python that are also useful for like command line tasks。

对。All right， and it's almost eight， so feel free to start working on your lab for this week。

