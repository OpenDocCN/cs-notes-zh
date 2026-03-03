# 哈佛大学《CS50X 计算机科学导论 C语言｜Harvard CS50 Fall 2024 - Lecture 1 - C》中英字幕（deepseek翻译 - P1：CS50 Fall 2024 - Lecture 1 - C (live, .zh_en - GPT中英字幕课程资源 - BV1mqpsePEmz

Alright， this is C S 50。 This is week 1 because of course， last week was week 0。

 and this is the week where we'll actually start programming in a much more traditional way。

 that programming language we promised called C。 Of course， we started with this。

 and hopefully by now with problem set 1， you've had a little bit of fun even if you played with it before and the goals of scratch beyond sort of making things feel very accessible in user friendly is really to elucidate some of the fundamental concepts that we'll see again today and really every week subsequently like functions and conditionals and loops and variables and so much more and in fact。

 among the goals of scratch is again， to kind of plant these visuals in your mind。

 So even as today onward feels all the more like a fire hose。

 especially when it comes to really weird cryptic textual syntax。

 the ideas are still going to be the same。 So today， this program。

 hellello world becomes this instead。 And in fact， just a color code things temporarily。

 I dare say that what I've color coded here in orange， which looks probably to those of you。😊。

Program pretty cryptic is the equivalent of the when green flag clicked orange puzzle piece like this。

 What remains is just one line in purple with a bit of white。

 which is what ultimately is going to get the screen today to say， hello world on the screen。 And。

 of course， we had a name for something in purple。 In fact， if we rewind to week 0。

 this block in purple represented。 what type of functionality。A。I function itself。

 an action a verb that gets the computer to do something。

 So what looked like this last week is about to look like this。

 Let's take away the color coding and focus really on what we're gonna now start calling source code。

 So this is what programmers do in the real world。 This is what software developer。

 software engineers do in the real world。 They write code that looks like this。 And clearly。

 it's a little English like， but it's not English in the way you would compose an essay or an email。

Clearly， there's some patterns and some special syntax to it that will highlight ultimately today。

 The problem is， though that computers， of course， don't understand source code。

 They only per last week Under like zeros and ones。 That is it the so-called binary system。

 So somehow we've got to get what already looks cryptic into something that looks at a glance。

 even more cryptic。 The zeros and ones。 the computers do understand。 And for today's purposes。

 just know that built into your Mac， PCs and phones。

 There is a built in understanding of what these patterns mean。 Maybe it means a number。

 maybe it means a letter But today， maybe it means an instruction。

Like print something on the screen or save something or load something。

 That is to say computers use patterns of bits。 not only to represent all the stuff we talked about last week。

 numbers， letters， colors， images， sounds and all of that。

 They also use patterns of bits to represent fundamental functionality， print things。

 play things much like those same scratch blocks。 But no computer scientist really。

 unless they take out a paper pencil or write a programr use a website to convert this can sort of read this and know what's going on。

 That's why we humans are actually going to use not machine code。

 as it is called the zeros and ones that computers understand。

 we are gonna start writing source code。 And last week， you already wrote source code。

 but in the form of dragging and dropping those puzzle pieces。

 So this too is gonna to be the paradigm that sort of guides us through the entire semester。

 Proble solving programming is really about input becoming output。

 and we'll focus today then on a certain type of input becoming output because somehow someone has to get that machine code。

 the zeros and ones to look like sorry， someone has to get the。



![](img/dd24156253db04e74fc14922ba497b1f_1.png)

Soce code that's written in a language like C into the machine code。

 the zeros and ones that the computer actually understands。

 So source code today is gonna be our input。 Ma code is going be our output and we're gonna give you today。

 a special program called a compiler whose purpose in life is to translate one to the other。

 And there's compilers for different languages in the world we're gonna to focus on one that supports today's language known as C。

 And here， as promised， is the programming environment were going to use。 It's tailored to CS 50。

 which is to say we've preinstalled certain software that you might find useful during the term。

 but for all intents and purposes， the tool you will use for C 50's problem sets henceforth。

 is a very popular industry standard tool called visual studio code or Vs code for short。

 We are using a cloud based version of it that lives literally this URL C50 you can sign into that So long as you have a free Github account with which for which you signed up presumably already。

 And that will give you access to not only an industry standard programming environment。 But again。

 environment that has some C50。😊，Specific things preinstalled。

 And at the end of the semester or even in the middle， if you you're so inclined。

 you can actually download for free VS code onto your Mac PC。

 you can disconnect from the internet and you can actually program on your own computer caveat though is that you tend to hit technical support headaches in the very beginning of the term。

 So we suggest you do that later in the term once you're already comfortable with this cloudbased environment here。

 And here it is。 this is what programming shall look like whether we're using C now or Python in a few weeks or jascript or SQL thereafter。

 So here is what what is VS code configured as follows at the top right。

 you'll generally have one or more tabs for code， much like tabs in a browser。

 And this is where you'll write code that looks a little something like this。 And in fact。

 this is exactly the code that you saw a moment ago。

 What VS code does among other things is it actually highlights your code for you。

 It colorizes in what's generally in an illuminating way。 So I did not choose to make this red。

 I did not choose to make this blue in this purple。 the computer sort of automatically。😊。

Does that for you， as we'll soon see， to sort of draw your attention to different ideas in the program itself that all happens automatically at the bottom here。

 you're gonna use a more advanced interface today onward known as a command line interface in the form of a terminal window。

 So you can still use your mouse or trackpad and click and drag and do things like that in this environment。

 but you'll find and many programmers prefer that it's much more efficient ultimately to use your keyboard more often than the mouse or the trackpad。

 So we'll introduce you to that textbased terminal window there appear at top left。

 you'll have a file Expr。 So what's nice about VS code is that not only will you have textual commands with which you'll get comfy。

 you also have like a normal Mac or PC or phone nowadays。

 like literally files and folders will visually appear to you so you can play with or manipulate them there。

 And then lastly， this is sort of like the menu。 the so-called activity bar that just has icons for various features including C 50's duck。

 So in fact， if you poke around， you'll see ultimately a duck icon when you。😊，Again。

 which is your own CSs50 specific chatbot of which you can ask questions throughout the process。

 So now that we've got VS code here， let's go ahead and actually consider what it represents。

 So this is generally for jargons sake， a graphical user interface。

 which means buttons and icons and menus and all of that we all take that for granted almost any device nowadays that's abbreviated just so you know as Gui Gi but built into VS code again is what's not only the terminal window by name but conceptually this is a command line interface So not a graphical user interface。

 but a command line interface whereby there aren't icons to click on or double click on rather if you want to run a program you use the command line interface or CI to type the name of the program that you want to run And so this will feel like a step backwards initially today because we all sort sort of tap and point and double click of things nowadays but again it's gonna give us more power。

 more efficiency ultimately beyond this。 So with that。

Sa let's go ahead and actually use it for just a moment。 during class。

 you're welcome to follow along。 but suffice it to say， well generally go somewhat quickly。 Really。

 you're going to learn how to program by way of the problem sets each week。

 I'm all introduce and focus on the concepts， the ideas。

 the sort of primitives that will get you started， but only through actually doing the problem sets is the muscle memory and practice going to come。

 So not to worry if it doesn't all sort code down easily the first time around。

 So here is the code that I claim is equivalent to last week's hello world program。

 Let's actually go ahead and do this in the programming environment。

 So I'm gonna go ahead and switch over to Vs code itself， which is now running on my Mac here。

 It's not just a screenshot。 And I'm going go ahead and do the following to get started with programming。

 I'm going write literally in my terminal window The word code。

 and I might have to give it focus by clicking down in that quadrant of the screen。

 And then I'm gonna give the name of the file that I want to code。 in this case。

 I'm going propose that we call it hello do C in the world of scratch。 when you downloaded it。

 you might have noticed the files are all。llLike S B3 or some such file extension。

 when writing code in C， you literally name the file something dot C by convention。

 But notice some other details， especially if I zoom in everything I've typed as far as lowercase。

 There's no spaces。 And so this is going be important。 And unfortunately。

 computers are not forgiving。 And odds are one of the first stupid mistakes you'll do is misscapize something misspell something add too many spaces or the like not to worry。

 like in time， that kind of muscle memory will come with practice。 So let me zoom out。

 let me now just hit enter。 and you'll see it top right， the code tab that I promised。

 So I'm gonna go ahead and type out this program pretty quickly because I've done it before。

 include standard I O do H in main void and then some curly braces as they're called and then print unqu hello。

 comm world backlash and close semi。 All right。 So that's a lot。

 But that too will come in time with practice。 But this is the exact same code that we saw just a moment ago。

 Indeed if I zoom in。 It's color。😊，d just as in the screenshot。 and thus。

 I have written my first program。 VS code will automatically save for you。

 but you can also hit control or command S to ensure that it's safe。

 But notice what's happened at top left。 Not only do you see my code over here。

 you see a visual icon just like on a Mac or PC that yes， this file now exists in your account。

 And that too is what you're getting with VS code for C 50。

 you're getting your own sort of server in the cloud， it's called a container nowadays。

 So there's some virtual disk space somewhere in the cloud。

 i cloudud or Google Drive that's going to store all of your files。 And at the moment。

 because I refreshed my account before class。 I only have one file in my own account。 What's this。

 what's this。 Well， this is like my I D number for Github。

 not really a big deal that's just randomly generated by Github U adventure is the name of my programming environment today。

 otherwise known as a code space。 This is just a Github thing， which is again。

 one of these cloud companies。 instead of choosing like random letters and numbers to uniquely all of our。

😊，It's popular in the tech industry nowadays to just put together random English words that sometimes sound kind of cool。

 but it's just by coincidence， not something I chose。 yours will be different。😊，Alright。

 so like I've written some code。 I've created hello dot C。 I typed in all of that code。

 I confirmed visually at left that it was created。 I'm gonna hide my file Explorer hencefor just so we can focus on the code。

 How do I actually run this program。 Well， on a Mac or PC。

 we would be in the habit of like opening the folder and double clicking on it or in your phone。

 you would take it out and tap on an icon， but not here here。

 we're focusing primarily on the command line interface within this whole environment。

 So I'm actually gonna have to introduce a few commands。 You saw already the code command。

 which for our purposes is VS code specific， that just creates a new file called hello doty in this case。

 But I need two other commands to actually run this program。 The first nicely is called make。

 and then I specify what program I want to make。 And then a little weirdly。

 I have to type dot slash hello。 But just to take a step back， make hello。

 if this is about to be my second command that I type。 What does that step represent， perhaps。😊。

Given what I said just a minute or so ago， that's gonna translate your source code into one0 perfectect。

 So make represents the compiler。 So to speak， the program that converts source code to machine code。

 I have to do that for now manually by running， make hello。 Now， make is kind of smart。

 And even though I'm saying make hellello， not make hello dot C， make is smart。 And it's gonna say。

 oh， if you want to make a program called hello。 I'm gonna assume that there is somewhere in this folder。

 a file called hello dot C。 So you should not type make hello dot C， you just type make hello。

 And then this third command even more cryptic。 What might it do。😊，If this is step 3 or 3。

That's going to run the machine code。 It's going to tell the computer in this folder。

 sort of the dot implies this current folder。 and dot slash just means something in this current folder。

 run the program called tellello。 So that's it。 Like there's three steps to writing a program and C。

 you create the file as with the code command， But there are other ways to do that too。

 And you don't even have to use VS code。 You can use dozens of other alternative program in the world。

 You run the compiler， which in this case is called make little white lie make not actually the compiler。

 but more on that next week， but make is going to trigger compilation of this code。

 And the last step3 is to execute or run the program called Tello。 So let me go back to VS code here。

And you'll see that my code is still at the top。 My terminal windows at the bottom。

 I hid my file Explorr just because it's not that interesting anymore。

 And I'm going to do what you proposed， which was M A K E space。 Ho， all lowercase。😡。

Enter and ironically， thankfully， nothing happened。

 And that's actually a good thing in this environment。 If nothing seems to happen。

 like you probably did good。 if anything does seem to happen on the screen。

 you probably screwed up and you've made some mistake。 So seeing nothing is generally a good thing。

 But what has happened。 Well， let me actually go back and open up My file Expr。

 and notice there's not only hello dot C， but there's a second file now， hello。

 which is the name of the program。 So hello is the program I want to run。

 I'm gonna go back to my terminal here and to run this program。 I'm gonna do dot slash H E L O。

 I'm gonna cross my fingers。 that's all often now do。 Andvoila， my very first program in C。😊。

How else can we see this file。 Well， down here in my terminal window。 Let me zoom in。

 You keep seeing a dollar sign。 That has nothing to do with currency。

 It's just a weird geeky convention that you're prompt at a terminal window like where you type commands generally starts with a dollar sign。

 Sometimes it's a hash symbol。 Sometimes it's an angled bracket depends on the system you're on。

 But dollar sign is very common。 It just means type your commands here。

 I've typed code I've typed make and I've type dotlash hello。

 but I can type other things too and more on these later。

 like L S which doesn't actually spell something but as short for list L I T programmers tend to just be as succct as they can。

 So most commands are not full words， they're often abbreviations。 if I hit enter now。

 you'll see also two things。 you'll see hello do C。

 and you'll see in green just to draw attention to it hello as well。

 The asterisk here just means in the programming environment。 This program is executable。

 you can actually run this by doing dotlash hello。 The fact that this is just white here that just means it's some text file。

 It's in fact。So in other words， L S lists the file in my current folder。

 or you can use your human eyes and the file Exper at top left and just look at what files exist。

 These are one and the same。 One is a guI， One is a CI， graphical command line and so forth。

 And we'll start to take these kinds of these kinds of paradigm soon for granted。😡。



![](img/dd24156253db04e74fc14922ba497b1f_3.png)

But let me pause here and see thus far now that we've written our first of many C programs。

 any questions。😡，Or confusion， we can clear up。So O。

 if you don't understand most of the lines of code， that's what today is about。 Yeah。

 I don' understand the difference between hello。What's the difference between hello and hello doty。

 So hello doty is literally my source code。 It is a file that exists somewhere in the cloud that contains all of the code I myself wrote。

 The hello file is the file that the compiler created for me by converting the source code to the machine code。

 So inside of hello， theoretically as a whole bunch of zeros in ones。

 We can't quite see them but if I do this， let me zoom out， let me click on hello。

 and notice that VS code is gonna yell at me。 This file the file is not displayed in the text editor because it is either binary that is zeros and ones or uses an unsupported text andcoding。

 whatever that means if I do open it anyway。 But I don't recommend this like heed these warnings。

 you won't see zeros in ones， but you will see sort of nonsense。

 And this is because VS code is trying to interpret those zeros and ones incorrectly as ASI text like English text。

 but it's not their instructions for the computer。 So as soon as you see scary red stuff like this。

 like undo close whatever tab you open because odds are， you can only。

Break the program you just created。 It's not a huge deal。 You can recreate it。

 but that's what's inside of those files。Yeah。Really good question。

 What if we don't type dot slash hello， we just type hello。 Well， let me do this。

 Let me hide my file explorer again because it's not that interesting here on out。

 I'm gonna clear my terminal window by hitting control L just to be neat and tidy in class or you can literally type clear and it will clear it。

 But again， that's just to keep things tidy。 your Tfs might do that in section 2。

 if I just type hello enter。 I'm gonna get this weirdly bash hello command not found。

 So more on bash down the line。 but this just means literally the command hello is not found because you need to tell the computer where it is。

 So dot slash hello means run the hello program that is in fact， right here。 By contrast。

 You don't run dot slash for code for make or other commands that will soon see like L S。

 because why those are installed in the system for everyone not just in your individual folder。

 So that's the difference。 Any programs we write， itll be dotlash something。 Allright。

 So let's tease apart what is actually going on here and see if we can lean heavily today on scratch。

 especially as the syntax gets weird。

![](img/dd24156253db04e74fc14922ba497b1f_5.png)

Perhaps a little overwhelming。 Still the same idea。 So this last time， of course。

 was our scratch program that just said hello world。

 I claim today that this is the nearest equivalent that any programmer could convert scratch into C if we color coded accordingly indeed this sort of lines up with when green flag clicked is the orange and then the purple is just the equivalent of the say block。

 So the say block we said earlier was a function。 So let's compare these things side by side because there's actually some rhyme and reason to what MIt did with scratch as to why these shapes look like they do and so forth。

 So in scratch， there's a function called say recall that it takes an input otherwise known as an argument or a parameter is another name。

 and that's always provided in these white ovals a0 or more white ovals in C。 we've already seen。

 but let's do it a little more pedantically。 the equivalent of say is essentially the word print Why did MIT say you say just because it's a little more kid friendly。

 but print is the idea in our environment。 It's actually not print。

 It's print F because we're going be able。😊，mat our text in interesting ways more on that in a moment。

 But notice the opening parentheses and closing parentheses here sort of conjure up the idea of that white oval。

 So that's kind of intentional on an MIts part。 What， though in C goes between these parentheses。

 Well， literally the input or the argument you want to pass to the function like hello world But in C。

 you have to be a little more pedantic because you don't have a nice little graphic like this purple block with the white oval。

 you have to surround everything in double quotes。 Those of you with prior programming experience in C。

 you need double quotes， not single quotes in this context。 And then there's this arcane detail here。

 backlash n， which will come back to in just a moment。

 But that's essentially what's going on line by line from scratch to C。

 there's kind of inequ between those two， even though they of course look a little bit different。

 Well， let's see what that backlash n is doing just to highlight some details here。

 So let me actually zoom in a little bit here。 and let me go up to my code。

 and let me just sort of recklessly delete。

![](img/dd24156253db04e74fc14922ba497b1f_7.png)

The back slash N， I'm going let it auto save。 I'll zoom out in my terminal window。 Now。

 I'm going to run make hello to recompile the code from source code to machine code because I changed the source code。

 Nothing seems to happen。 That's good。 Now I'm gonna to type dot slash hello En。

 And there's a subtle bug。Since I made that change， what looks wrong to your eye now？找。Yeah。

 the dollar sign are so called prompt is at the end of the line instead of on its new line。 I mean。

 this isn't really a deal breaker， like the code works， and you can still type a new command。

 but it just looks a little stupid。 Like this was not the intent of the program。

 it's sort of good practice to move the prompt to the next line。

 And that's because the backslash end is what we're gonna to call an escape sequence。

 So it turns out in programming， don' you have to tell the computer exactly what you want it to do。

 So if you want a new line。 The equivalent of hitting enter on the screen。

 you have to tell the computer to put a new line there。 What you do not do is this。

 if I zoom out and I go into my code here and I'll zoom in on the code。

 If you want to put a new line， you don't do this。Why it's just confusing for the computer。

 Like wait a minute。 Is that a typo。 Did your lines just wrap。 Do you want to put a new line there。

 It just looks stupid。 And it makes it less linebased the code itself。 So humans decided years ago。

 if you want an actual line break， don't just naively hit the enter key。

 literally tell the computer put a new line here。 if you want to move two lines down。

 just do two of those if you want three， just do three of those。 Well， why the backslash again。

 these are what are called escape sequences。 And you don't literally want an n， let alone N and N。

 what you want is a new line， which is represented in code as simply backlash N。 Now。

 for the mathematicians among you like what we're doing now by writing using functions like printf is just sort of like f of x notation。

 if we recall that from high school or prior， where F is a function。

 X is an argument or an input there too， and we're using parentheses in code just like mathematicians would to write functions like these。

 and the types of functions we're using right now， still follow this model。 You've got input。

You want output in this case， the input to printf， for instance just like the say block is what's called an argument。

 The output， though， of the function， printf is what we call a side effect。

 and the easiest way to think about that is a side effect。

 It's just something that sort of like happens on the screen visually aly， it just sort of happens。

 and there's that effect on the screen and will contrast this with other types of outputs from functions。

 But for now， we're focusing on just this， which is reminiscent， of course， of what we did last week。

 which is if you type hello world into the white oval， use the say puzzle piece。

 you get out the side effect of the cat appearing to have said hello world。 Now。

 as for those escape sequences in C， there's bunches of them。

 but very few of them what we actually use in practice backslash and is a new line。

 backlash R is a little more subtle and it's kind of a feature of yesterear。

 it moves the cursor not to the new line。 but to the beginning of the line kind of like an oldtimey typewriter。

 if you've seen how those work。 Sometimes though， you might want to。Print out an actual double quote。

 but there's a problem， of course， if this is my code here。

 and I'm already using double quotes as sort of special symbols to surround the text I want printf to say。

 it would probably be a little like if you wanted to say， hello world with sort of finger quotes。

 why might this not be a good idea。If you think about this from the computer's perspective。

Like whyhy is this probably not the right way to do this？😡，嗯哼。😊，Yeah， exactly。

 the computer is indeed gonna read your code top to bottom left to right。

 And when it sees the first open quote。 Okay， that's fine。 it understands that。

 But when it gets to the second quote， it's gonna to assume oh wait a minute。

 maybe you only want me to say hello comma， And then it's gonna keep reading and be like wait a minute。

 Why is there the word world here。 And then wait a minute。

 Now there's two more quotes It's just confusing。 It's ambiguous And computers need you to be again very precise。

 So if you want a quotation mark to literally be displayed on the screen。

 you would escape it so to speak， which looks a little weird and take some getting into the habit of But this just solves that kind of problem And similarly might you use single quotes in other context more on that soon。

 And if you really want to bend your mind， how do you actually print a literal backslash if you ever care to it's not that common a character to type But if you ever want it on the screen。

 it seems that we're using backslash as a special character that says hey。

 give me a new line or give me a carriage return or give me a double weirdly in programming if you want to type a literal backslash on the screen。

They do backslash， backslash。 But that's it for sort of weirdness for now。 But this is to say。

 humans tripped over the same problems years ago， They came up with solutions。

 And now we indeed have these conventions in code。Allright。

 so let's tease apart some other features of this in every program we're going to write。

 namely what's at the top of this file。 So at the very top of this file。

 there is this cryptic looking hash include or pound include standard I O dot H in angle bracket。

 So this is a little weird， we'll talk more about this next week too。

 but this is what's called a header file。 any file that ends in dot H is not a source well any file that ends in dot H is what we're gonna call a header file。

 and inside of that header file is functionality that maybe came with the system came with the programming language itself。

 So for instance， I'm going to do this。 I'm going go back to my code here。

 and I'm gonna make a very common mistake that you yourselves might make in the coming days where I just forget that line because I don't even understand it in the first place。

 So I certainly didn't think to type it here。 Now， if I go back to my terminal window after clearing it and I run make hello because I want to recompile it because I've changed the source code。

 I'm going see a fairly cryptic error。s。More error on the screen than there is code up here。

 But you'll get the hang of sort of reading it to try to figure out what's going on。

 And I'm seeing this。 Ho dot C line 3 character 5。 So that just means line 3 colon character 5 from left to right。

 It's sort of a visual cu as to where the problem is called to undeclared library function printf with type dot dot dot。

 And then the rest overwhelms me visually at this point。 But that's a hint。

 If you do not include that header file at the top of the code you've written。

 you do not have access to what's generally called a library。

 A library is a collection of code that someone else wrote for you。 Maybe it was M T。

 maybe it was the authors of the C language itself years ago， maybe it was Cs 50。

 if we wrote some code for you， a library is a collection of code that someone else wrote for you。

 and you access it again， by including header files that those same people wrote for you。

 So if I go back to my code now， let me clear my terminal window just be。Overwhelmed。

 let me undo what I just did and put that file back。

 Can you perhaps infer just functionally what is inside of standard I O dot H that， again。

 someone else wrote， what must be inside。Printf， So some whoever invented printf decades ago。

 probably put that code in this file。 And so by including it。 so to speak in my code。

 I now have access to printf functionality。 So that's all。 And again。

 C is lower level than scratchch。 It's obviously textspace。

 which means you have to be a little more pedantic yourself as to what you want the computer to do for you。

 And if you want to use someone else's code， you indeed have to include it。

 Scratch didn't bother with this。 But we do need to do this in the context of C。😡，As an aside。

 just to preempt some unnecessary headaches， this word is not studio do H every year。

 a nonzero number of people can't understand why their code's not working because studio do H is not found。

 It's standard I O D I O do H。 That's one of the first frequently made mistakes otherwise。right。

 So remember that。 let me undo now， the unnecessary quotes I added here。

 And let me propose that we show you where you can learn more。

 So all of these libraries generally are documented like people wrote instructions for how to use them。

 So you don't just have to listen and pay attention only in class。 you don't have to pull up a book。

 there tends to be online documentation as well。 for instance， for the standard I O header file。

 And the documentation in the world of programming for C specifically are called manual pages or man pages for short。

 Unfortunately， they're really written decades ago for like the more comfortable among you。

 those who have an eye already for programming。 And so what C 50 has done at this URL manual do。😊。

is we essentially have more user friendly versions of the documentation for this header file and others。

 So for instance， if I pull up manual do cs 50 do， you'll see a webage like this。

 And if I just scroll quickly， you'll see a whole bunch of header files do H files and a whole bunch of functions beneath them。

 And there's only a couple of dozen or so here。 And indeed per this checkbox at the top frequently used in Cs 50。

 we have sort of highlighted the functions that odds are over the next month you will probably want to use if I turn off that less comfortable mode。

 there's actually hundreds of functions that come with see and like no programmer knows all of these functions。

 What they do is they read the manual when they want to find some new piece of functionality。

 So I'm going simplify this， I'm going scroll down to standard I do H。 for instance， here。

 and you'll see more functions that will eventually get to。 But if I click on printf。

 you'll see hopefully some fairly user friendly instructions for how this thing works。😊。



![](img/dd24156253db04e74fc14922ba497b1f_9.png)

Under synopsis， you'll see that we tell you what header file you should include in order to use it below that is something called a prototype。

 more on that later。 but below that is a description。 And here is where we。

 the CS50 staff have written in laypersons terms， explanations of how this function works how to use it and so forth。

 But if you'd rather see what the real worldor uses， you can turn off that mode。

 and you'll see much more arcanely， the original language。 So in short。

 these are sort of like training wheels that you can turn on and off at your leisure。

 but ultimately this is real worldor documentation as well。 So if we want to see something else。

 for instance， let me go back to the main menu。 And as we'll see today。

 there are actually functions in a header file called C50 H。 that for a few weeks。

 we're gonna lean on heavily Long story short， it's actually kind of hard。

 it's annoying and see to get user input ironically to like get the human to type in a word or a number like you have to kind of jump through some technical hoops to make that happen。

 And we'll show you how to。like the real way in a few weeks。 But for now。

 among the first training wheels is a C 50 library code that we wrote that will just make your life easier。

 And indeed， we're gonna give you access to functions that simplify the process of actually getting input from the user。

 So case in point， we're gonna give you access to functions like get string when you want to get a string of text from the user。

 string is just text。 So if you want to get one character， one word， one sentence， one paragraph。

 you can call a function called get string。 We're gonna give you another one called get int。

 when you want to get an integer from the user like one or0 or negative one or anything else。

 you can use that function as well。 and we'll see today too。

 there's other functions you can use from C50's library in a few weeks time we'll take these away once you sort of don't need them anymore。

 and you'll see what those library functions have been doing all along for you。 But for now。

 let's focus on this。 perhaps the most useful of them。

 get string and solve a problem that we did already pretty easily in scratch。

 So recall call in scratch。

![](img/dd24156253db04e74fc14922ba497b1f_11.png)

This was a program that used two functions。3， in fact， ask to ask a question of the user。

 say to actually display something on the screen and join to combine the default of Apple banana。

 or in this case， hello and whatever the humans answer was。

 So this made our hello program a little more interactive last time。

 How can we actually translate this into a similar paradigm now。

 So input and output as the story as always， in this case。

 we have arguments going into those functions。 But now we're going introduce not side effects。

 which is stuff that happens visually。 we're going to revisit that blue circle called answer or the blue oval called answer that represented last week what we call a return value。

 And this is what many functions will actually do for us。

 They're not just going to display something presumptuously on the screen or play a sound or video or something like that。

 They're gonna hand you back virtually of value text or integers or sounds or images that you can then do with what you see fit。

 So the paradigm will。😊，Have is much like in scratch。

 if the input is what's your name and the function is ask and you get back a return value of answer。

 we want to actually do this now in C。 So side by side。

 what code like this in scratch is going to look like today onward is this。

 Instead of using the ask block。 You literally use C50's function called get string， It takes input。

 So we put the parentheses on the left and the right to kind of conjure the idea of this white oval inside of that string。

 you can put a prompt， so to speak， like what do you want the human to be asked in this case。

 And I'm missing something still per the placeholders here。 What's missing。



![](img/dd24156253db04e74fc14922ba497b1f_13.png)

![](img/dd24156253db04e74fc14922ba497b1f_14.png)

So quotation marks。 so literally quotation marks on the left and the right。

 And I'm gonna be a little anal here。 I'm gonna put a space at the end because I don't want to。

 I could， but I don't want the cursor to go to the next line。 hence no backlash end。

 If I want the cursor just to sit there kind blinking， waiting for the user after the question mark。

 I'm just gonna put a space。 So it will stay there for me。

 But this is just an aesthetic detail using the same idea as before。

 So that is the analog of this block。 But how do I get access to the so-called return value。

 MT just plopped it on the screen for us automatically in C。

 we have to write a little more code to get access to that return value。

 And the way we do this is on the left hand side of this line of code。

 we come up with a name for for the return value， you can call it anything you want but answer is a nice equivalent to what MIT did。

 You could more generically call it X or Y or Z， but that's not really useful。

 And so computer scientists on like mathematicians will tend to use variables that are a little more verbose like the word answer。

 But in C， it's again， a little lower level， you have to tell the。Computer。

 what type of variable this is going to be。 So I'm kind of conflating variable and return value。

 but they're being used in an intertwined way。 The get string function。

 just like this ask block returns a value。 If you want to do something with it。

 you need to put it in something called a variable， which is denoted in text here。 But again。

 per last week， the computer doesn't know if it's looking at numbers or characters or images or sounds。

 you have to tell it as the programmer that the zeros and ones that are somehow involved here underneath the computer's hood are。

 in fact， to be treated as text， Aka string。Now， there's one stupid subtlety still missing from this line of code。

 Does anyone know， especially if you program， Okay， all of youve programmed before， yes。Semicolon。

 So one of the headaches of C in a lot of languages is you actually have to finish your thought explicitly。

 so the computer knows that that line of code is done。 And it's not a period like in English。 it's。

 in fact， a semicolon。 Now you don't use these everywhere。 we'll see where you use them。

 But that too is a very common mistake to overlook something simple。 But again， in the coming weeks。

 even though this might look very cryptic with muscle memory and practice。

 you'll start to see these things instantly， even if for a few days。

 you sort of bang your head against the screen。 So to speak。

 not seeing what the Tf and I much more readily C。 So let's go ahead and do this。

 let me go back over to BS code here。 Let me zoom in just a little bit。

 And let me go ahead and do this。 I'm gonna get rid of my single use of printf。

 And I'm gonna say the exact same thing。 Str answer。😊。



![](img/dd24156253db04e74fc14922ba497b1f_16.png)

Equals get string。 quote unquote what's your name question mark space。 close quote semicolon。

 And now I want to print out that answer。 Well， let me do this incorrectly deliberately for the moment。

 Let me just say print F quote unquote， hello answer。 if I want to plug in answer。

 and I want to add a new line at the end semicolon。 So let me try this。

 But there's multiple mistakes now in my code。 Let's trip over them deliberately。

 Let me go down to my terminal window by clicking at the bottom of the screen。

 Let me run make hello again， enter。 and oh my God。

 there's even more errors now than there were before。 but not a problem。

 Let me click on this little triangle here， which is just gonna zoom in on the terminal window So it takes up my full screen。

 And just generally， all you have to do is find a few keywords visually。

 They give you a clue as to what's going on。 Or as before you can always ask the C50 duck。

 So here's the command I ran， make hello。 somehow that induced all of these errors。

 always read them top to bottom， not bottom up。 So from top to bottom， there's a problem on。5。

 character 5 use of undeclared identifier string。 Did I mean standard in。 No， no， no， I didn't there。

 And then also like two errors generated。 too many errors are madeted。 What did I do wrong， Well。

 it turns out what I do need to do at the top of this file。

 Let me click the triangle to zoom back out。 If I want to use the get string function to get a string。

 I actually need to include another header file， which is probably called。😡，Include C S 50 dot H。

 technically， any order is fine。 I tend to alphabetize because I just know therefore where to look alphabetically for a certain header file。

 Now that that's in place， let me again run make hello enter And now we're back in business。

 No error message。 So even though you might have more errors than you have code。

 odds are it's just the computer is confused and it could be something simple and an easy fix like that。

 So just to be clear， standard I O do H because I'm including it， I can use printf C 50 do H。

 I can use get string because the people who invented C and the people who invented C 50 wrote those two files so to speak respectively Allright。

 unfortunately， even though the program compiles that doesn't mean it's correct。

 It just means it's syntactically valid。 It's valid C code。

 if I go ahead and run do hello and hit enter now， I'm going to be prompted for my name。

 So I'll type it D V I notice there's a space to the right of the question mark as promised， enter。

It just says hello answer， which of course is not the intent。 I wanted to say hello David。

 So how can we do this。 Well， in scratch， it took a couple of puzzle pieces。

 but it was pretty straightforward。 if I wanted to say the combination of two phrases hello and something else I joined those two and then pass that output to the input of say in C it's gonna be a little different here。

 just because it's an old language and this is how it's done。

 still use printf because that's the same thing as say I got myheses， I got my semicolon good to go。

 But inside of that， this is where printf is different if you want to say something followed by something else in the world of C。

 you tend to use placeholders So you don't just join things together。

 as we will do in python and other languages， you say to the program you say to the compiler give me the word hello comma and then something else。

 and the percent S means put another string here。 Its sort of like leaving a placeholder in your code or a template where you'll actually plug in some values。

 Now if this is what I want to。

![](img/dd24156253db04e74fc14922ba497b1f_18.png)

Display I still use my quotes as before， and I might in fact have a backslash n if I want to move the cursor to the next line。

 but this is where printf is a little different。 say unlike say， which took one input。

 printf is kind of like join。 It can take two or more inputs if you so choose。

 you just have to separate them with a comma。 So much like the join block has two ovals here that are initially white。

 Apple and banana until we dragged and dropped answer on top of it。

 printf and really any function in C。 if you want to pass in multiple inputs that's fine。

 if they're supported， just separate them with commas。 There's no multiple parentheses。

 there's no multiple ovals， just separate them with commas。

And now notice a potential point of confusion。 What's different about this comma and this one。

 just instinctively。

![](img/dd24156253db04e74fc14922ba497b1f_20.png)

Sort of minor detail， but important， yeah。So one is inside， one is outside。

 So the one that's inside the quotes is literally the English grammatical comma that you want the human to see。

 The one out here is a C thing that's separating the first input to this function printf from the second strictlyly speaking you don't need a space there。

 but it's a good practice stylistically to separate your arguments with single spaces just as I've done there。

 So let me go ahead and now do something with this， let me go back to my C code here。

 I'm going to clear my terminal window just to get rid of that distraction。

 and now I'm going to change answer to percent S。 and then outside of the double quotes on line 7。

 I'm going to do comma answer and then after it auto saves。

 I'm going go back to my terminal window and just to make another deliberate mistake dot slash hello enter what's your name。

 David enter it's still broken。😡。

![](img/dd24156253db04e74fc14922ba497b1f_22.png)

But why。Still have to recompile it。 So again， you just get into the habit。 when you change your code。

 you have to recompile。 So you get new machine code in the file。 hellello。 So let's do it again。

 make hello， No errors is good。 dot slash hello， enter what's your name again， D V I D。

 And now hello， comma David。 So again， slot of this is still cryptic。

 but it's going to start to follow patterns like this functions like in math class F of X are written function name。

 parentheses， input comma input comma input。 however many you have they're going follow these patterns。

 But notice 2， On line 6 and 7， I have finished each of my thoughts with a semilon。All right。

 that was a lot all at once。 Que on what we have done conceptually， syntactically here。



![](img/dd24156253db04e74fc14922ba497b1f_24.png)

Or otherwise。Yes， over here。Like say。Yeah， a really good question。

 If we had something other than a string of text。 we had an integer， would you still use percent S。

 No， you would use something else。 And indeed， percent I is what we're gonna use。

 and we're gonna actually do that perfect segue to other types that C actually has。 So up until now。

 we've been calling a string of text， literally a string。

 And this is common in many programming languages including Python in jascript strings in the programming world just mean text。

 whether it's zero or more characters thereof。 But C does have other data types。

 just a few of which will dabble with today， but you'll use more over time。

 we've already seen string for instance， which is indeed a string of text。

 but let's focus as well on like in integer。 As in the aside， there's other types too。

 there's Boolean values， like true or false， there's chas which are single characters instead of full phrases or sentences。

 there's doubles and floats， which are real numbers， something with a decimal point。

 the equivalent of fractions， and there's longs， which are integers but like longer integers。

 even bigger integers than you might type by default。 So let's focus on an int。



![](img/dd24156253db04e74fc14922ba497b1f_26.png)

So many of so many computer programs， of course， manipulate numbers in some way。

 So what can we do with this。 Well， if we want to be able to get an integer， lucky enough。

 C50's library comes not just with get string， but also get int So that's going to be a third function we now use and C。

 and we need to know what were generally called format code So that placeholder I called before percent S is indeed for a string if we want to place a integer inside of something we're printing to the screen。

 we are in fact， going to use percent I instead So let's now actually use these building blocks。

 get int and percent I to actually get numbers in some way to sort solve a problem。

 Well what problem could we solve。 let's introduce another concept from scratch and programming more generally known as conditionals like those proverbial forks in the road。

 if something is true， do this else maybe do this other thing。 So in scratch。

 we might have had a set of puzzle pieces that look like this。

 if X is less than y then say or have the cat say X is less than y。



![](img/dd24156253db04e74fc14922ba497b1f_28.png)

Stup program。 but it just demonstrates if how we have two variables。

 X and Y in the context of scratch。 we're comparing them with a Boolean expression。

 We're using a conditional to then conditionally say or not say this phrase here depending on whether this question has answer of true or false Yes or no in C doesn't look all that different。

 It's a little more cryptic， but you say literally if you use parentheses similar to functions。

 but confusingly by convention， you put a space after the word if so you don't put spaces after function names。

 you do put spaces after words like if and you use the parentheses to conjure up this weird trapezoidal like shape。

 So there's no real keys that kind conjure that So C uses parentheses like most languages。

 And then there's these weird curly braces， which at least in English， we don't use all that often。

 but they're there on your keyboard English or otherwise。

 and they essentially allow us to create this sort of hugging shape to the puzzle piece。

 Anything inside of those curly braces is going be equivalent to anything。

Inside of this yellow hug that's sort of grabbing one or more pieces inside。

 So what do we put inside， Well， this part is straightforward。

 printf quote unquote x is less than y backlash n semicolon So nothing new here。

 the only bit of new code is this if construct instead。 What if you have an if else。

 So two way fork in the road。 This is what that looked like in scratch。 same question。

 if x is less than y then say x is less than y else。

 say x is not less than y in C the code is gonna to be set up initially like this。

 So two sets of curly braces to represent this pair of yellow bars and this pair of yellow bars and what's inside of them indented no less。

 just like our pseudocode last week is two printfs X is less than y X is not less than y。

 So that's it。 So the only new stuff here really is now the else keyword。

 which does not need parentheses because you're just saying else do this other thing。

 But what if it's a threeway fork in the road and we'll stop after that。

 Here's a threeway fork in the road in scratch。 If x is less than y。Then sayy this else。

 if x is greater than y， say this。 else， if x equals y， then say this。

 So this is a little more precise because now we're handling equality。

 not just greater than or the opposite。 in C， it's going to look similar to before。

 But we're adding this element here。 And at first glance。

 especially if we've never programmed before。 It looks like I'm an idiot。 and I'm made a typo。

 What looks wrong。😊，There's like two equal signs， like not a typo。 So it turns out。

 recall from earlier， when we used the equal sign the first time around。

 we used it in the context of getting a return value back from a function like the get string function handed me back the user's answer。

 So unfortunately， because humans decades ago decided， hey。

 let's use the equal sign to assign a return value from the right hand side of a line of code to the left hand side。

 We sort of painted ourselves into a corner and like oh shoot。

 what do we do when we actually want to test for equality of two values on the left and right。

 So what most languages， including C do is use double equal signs。

 So you can say double equals or equals equals or whatever。 But it is， in fact。

 syntactically correct。 What's inside of these three sets of curly braces， same idea， printf。

 printf printf based on what English phrase you want to print out。So this code。

 both in scratch and see， I'll claim is correct。 It won't run because we still need like the other stuff。

 the equivalent of the when green flag clicked， but out of context， this code is correct。

 But there's a subtle weakness in design。 And we'll talk a lot about this this week and beyond correctness just means the code does what it's supposed to do。

 Design is more subjective。 Like how well have you written your argument in an English paper。

 How well have you written your code is design。This code is not designed as well as it could be。

 because I'm doing more work than I need to。 Yeah， and back。有你。Yeah。

 I don't need the x equals equals y but y logically。😡，Exactly。

 that's just a math thing like either x is less than y or it's greater than y or the third and final option is they must be equal。

 So it's subtle。 but why would you bother wasting time writing a line of code and expecting the computer to run a line of code that is just going to answer a question that logically you could have concluded already because if x is not less than y and x is not greater than y。

 then my God， just print out x is equal to Y because you know at that point logically it's true。

 you don't need to waste your time or the computers asking a third question unnecessarily And reality it's not a huge deal no one's gonna to notice in the real world on a Mac PC that there's this extra line of code。

 but it's a bad habits， keep it simple， don't write code that doesn't need to be there if logically you can conclude otherwise。

 So in fact， let's clean this up both in scratching and C I can tighten this up so to speak。

 use less code here it's less code here and honestly。

 if only statistically the less code I write the less likely I am going to make mistakes。

 So that too is。😡，Probably a net positive overall， the less writing less code is generally better than writing more code。

 not unlike English essays 2， perhaps。 All right， questions about this feature of C conditionals。

And this syntax。Yeah呀。关键。He。Oh， a really good question。 And yes， jumping the gun。

 There are alternative ways to solve problems like these。 And the question was to summarize when。

 when to use if else if else versus what's called a switch statement more on this another time。

 But this is gonna be true in general in programming， not just see not just in scratch。

 but every language， there are going to be several dozens。

 hundreds in infinite number of ways to solve problems among the things we're gonna to teach you。

 though， is indeed， how to do things well or better than you might otherwise。

 and we're gonna introduce you eventually to another feature of the language that can even simplify this code。

 too。😊，So for now， let's actually use this then。 So let me go over to V S code again。

 I'm going to go ahead now and clear my terminal window。



![](img/dd24156253db04e74fc14922ba497b1f_30.png)

Down here， I'm gonna go ahead and close the hello do C tab just so that it we' gonna create a new program。

 And let's just do something a little simple using some operator so to speak。

 And I haven't used this word by name， but it turns out that there's lots of operators that come with C。

 just like a lot of operators that came with scratch for doing assignment or less than or less than or equal to greater than greater than or equal to actually equal to not equal to Now some of these are a little cryptic。

 but there's no easily found key on your US English keyboard at least where you can do less than or equals or greater than or equals。

 So what most programming languages do is you don't use a special symbol where there's like an angled bracket and then a line below it。

 you actually just use two character。 So greater than or equal is literally this this less than or equals literally this this we already saw that equals is this this and not equals is to use an exclamation point。

 So this too is a thing in programming using exclamation point pronounced bang is how you invert logically certain。

😊，So bang equals or not equals is how you would express exactly that idea。

 It's just a symbol on the keyboard that some human decided let's use this one to invert the idea。

 but we're gonna to need one other thing for this program。 specifically variables。

 which we've used already sort of because in scratch， we got one for free。

 We had that answer variable that stored the return value of the ask block。

 But let's consider in general， how you can and probably did for problem set0。

 use a variable of your own like keeping track of a counter or score or the like in scratch。

 if you want to create a variable called counter， you can set it equal to some initial value like0 in C。

 that code's going look similar。 you literally just write whatever name you want to give the variable。

 then an equal sign。 and then the value you want to give that variable。

 And because the equal sign is the assignment operator。

 it will behave essentially right to left and copy the zero into counter。

 But this isn't enough for C。 Remember that you the programmer have to tell the computer is this indeed。

😊，Is it a letter， Is it an image， Is it a sound， You have to tell the computer that this is an integer。

 otherwise written as int for short in C。 But there's one other stupid detail that's missing。

 which is now。Semicolon to finish the thought here。 But this then is equivalent to this in scratch。

 Let's do another in scratch。 if you wanted to increment the counter that is add one to it。

 you could literally use this puzzle piece here and specify you want to add one。 in C。

 it's gonna look like this。 counter equals counter plus one semicolon。 Now， at a glance。

 this seems like a paradox of sorts。 like how can counter equal counter plus one。

 Like I can't make that math expression true。 but it's not math in this case。

 the single equal sign is assignment So this means take the current value of counter whatever it is add one to it and then copy that value from right to left in two。

 the same variable thereby changing it from one to2，2 to3 and so forth。 This， though。

 is so common in programming to be able to increment or even decrement numbers by one or two or more。

 is that you can tighten it like this。 This is the exact same thing a little faster to type。

 saves you keystrokes。 maybe less chance error。 counter plus equals one semicolon is the exact same idea。

Better still， this is so common in C and C plus plus and Java that there's a third way to do this to my comment earlier about solving problems in different ways。

 The most canonical， the most popular way is probably just to say counter plus plus semicolon。

 which literally automatically adds one to that value， only works for one。

 If you want to do two or three or some other increment。 You have to use one of the other approaches。

 but this simply does the same thing as this。 And if you want to invert it to negative one。

 you change the plus plus to a minus minus instead。 So again。

 just little things that well see and pick up over time invariably。

 you'll have to look them up or check the notes or look back at the lecture slides。 but in time。

 this will get familiar if you are not already familiar。 So let's consider just logically。

 how we might implement this in code。 Let's go back to V S code here。

 and let me propose that we create a program called compare do C whose purpose in life is just to compare a couple of values。

 I'm gonna go ahead and proactively based on the previous chats include C 50s。From the get。

 I'm going to include standard I O do H from the getgo。 so I can use get int and printf respectively。

 I'm gonna just on faithith type int main void。 And today we won't explain what that does more on that to come for now。

 just assume it's like when green flag clicked。 But in this program， let's do a couple of things。

 Let's declare an integer called X and assign it。 the return value of get int。

 And let's just keep it simple。 Let's ask the user， not what's their name。

 but what's x question mark。 semicolon。 Now， so that we have something to compare。 let's do it again。

 but with y int y equals get int unqu what's y question mark。

 And I'm leaving again a space just visually。 So the cursor nudges over a bit。

 followed by a semicolon at this point in the story。

 my users will be prompted for X and y respectively。 Let's do something with those values。

 How about if X is less than y， then go ahead and print out unquote X is less than Y backlash。😊。

Close quote semicolon All right， and let me hide my terminal window for just a moment。

 This is a 13 line program at the moment。 but really it's like five or six interesting lines。

 The rest has been copy paste from previous programs。

 notice a few details One I've indeed used my curly braces here and notice if you highlight lines。

 you'll actually see little dots that can help you make sure there are indeed four spaces there。

 I've been indenting just like we did last week with pseudocode strictly speaking。

 it's not necessary。 but it's gonna be way easier to read your code。

 if you do at all of this white space。 so to speak。

 than if you write and then submit to us as homework。

 a program that looks sort of got awful like this， which is to make it much。

 much harder for the human to read it for you to read it。

 your colleagues in the real world to read it。 but the computer is actually not gonna care。 In fact。

 as an aside。 One of the tools we have built into VS code for C50 is this button at top called styleyle 50。

 This is a program that we indeed wrote that will give you。

Suggestions on how to improve the style of your code。

 So it looks like the right way that programmers would generally write it。 As an aside。

 the computer world is fraught with like religious debate。

 so to speak as to like what code should look like。

 and people in the real world will have really stupid arguments over how many spaces to use for indentation and what lines code should go on and so forth。

 generally in the real world or in a class， there's an official style guide that someone sort of autocratically。

 this is how everyone should write their code so that just everyone's code in the company or course looks the same。

 but you'll find in the real world， reasonable people will disagree。 when you click style 50。

 it will be formatted， as we ourselves recommend in Cs50。 And in fact， let me zoom out here。

 And this looks a little cryptic at first glance。 But on the left is the code that I just wrote and made a mess of by deleting all that white space on the right is the way the code should look if it is well styled。

 So whereas correctness is all about does the code work the way it's supposed to Design is about。

How well have you written that code， Is it efficient， Did you make good decisions。

 St is purely aesthetic。 Is it readable， Does it follow a standard。

 Can another human sort of easily skim it top to bottom left to right and understand what's going on。

 So these green highlights are saying please add white space there。

 And so I can actually change my code to match on the lefthand side here if I realize oh my code's looking pretty ugly。

 watch on line 6 at left as I hit the space bar to sorry， on the left1，2，3，4。

 notice that the right hand side is starting to be happier with my code by getting rid of the green indicators and I can do1。

2，3，4 that fix that over here， I can do 1，2，3，4 I can move this onto its own line by hitting enter and you know what if it's taking too long once you get into the habit of things。

 you can just apply changes it will give you the suggestions automatically and we're done and on our way。

 But for practice's sake， I would get into the habit of doing。

Things manually until it gets boring and tedious。 And at which point you might as well automate the process with a single click。

 Allright， so let's actually run this code。 I'm going to go ahead and open my terminal window again。

And clear it for clarity。 I'm gonna run make。Compare and hope that I didn't make any mistakes。

 I don't seem to have yet。 dot slash compare。 And now notice I'm prompted for X。 Let's type1 for y。

 let's type2 enter and X is less than y， let's do a little sanity check。 so to speak， let's rerun it。

 dot slash compare。 What's X， let's do2 this time。1 for y。 And this time it said nothing。

 So that's to be expected， because I didn't have a two way or a threeway fork in the road。

 the only time this code should say anything is if indeed X is less than y。

 So for those of you who might be more visual when it comes to a learning。

 here's a flow chart that represents this same exact program。 If you read it top to bottom。

 you start the program with dot slash compare。 you are then prompted for X and y。

 And you're asked this is x less than y。 And the fact that this is a diamond means this is a boolean expression。

 a question that the computer is asking itself。 If the answer to that question is true。

 then quote unquote X is less than y gets printed and the program stops L。If x is not less than y。

 as in the second scenario， the answer is， of course， false and nothing more happens。

 But we can build out this tree。 so to speak by adding a bit more code。

 So let's make it look like the second scratch example。 If I go back here。

 It's not hard to just say else。 if X is not less than y。

 Let's say that X is not less than y backlash n close quote semicolon。 let me now go ahead and rerun。

 make compare， enter dot slash compare， enter， and again， I'll do the second example2。

 which is bigger and one， which is smaller in this time， I will see x is not less than y。

 If then we were to look not at this flow chart， but a slightly bigger one。

 you can sort of visualize it this way。 everything in the left hand side of this picture is the same。

 But if it's not true that x is less than y， the answer is thus false。

 this time we say quote unquote X is not less than y。 and we can do this obviously one final time。

 just to bring the point home， if I go back to my code。 and。Even more pedantically。

 compare these three values。 Let me go ahead and do this So else。I don't want an else actually。

 So let's go ahead and do this。 else。 if X is greater than y。

 let's then say x is greater than y in English。 and then finally have an else that says print F X is equal to y close quote or rather back slash n close quote semicolon。

 So just to show this all on the screen at once。 This is identical now to that scratch version。

 it's well designed because I'm not asking the equals equals question unnecessarily。

 If I go back to my terminal window here。 clear the screen， run make compare。

 enter and then dot slash compare again， enter what's x， Let's do one。 let's do two。

 x is less than y。 Let's run it again。 dot slash compare。 What's 2 and1。😊，X is greater than y。

 One more time。 dot slash compare。 What's x1， What's Y 1。 And now X is equal to Y。 As an aside。

 if I seem to be typing fairly fast， you can actually kind of cheat with your keyboard。

 if you go up or down， you can scroll through all of the past commands that you've typed。

 So it's actually excuse me very useful。 If you just hit up。

 itll it will prerite the previous command for you at which point you can just say enter。

 or there's other fancy features built into this programming environment。

 if you do dot slash CM and then get kind of bored with typing out the whole English word。

 you can hit tab for tab completion like in a web browser and it will autocomplete。

 if it finds a file that starts with those letters。 little efficiencies here。😊，Questions， then。

On the code here， yeah。是。A good question。 Is there any downside you're just putting in all of the libraries like we saw in the manual pages a moment ago。

 performance。 So generally speaking C is meant to be a very efficient language。

 so much so that even though it's decades old， still used omnipresently nowadays because it's so fast。

 it therefore minimizes time。 It minimizes energy use。 So it's still being used heavily。

 you would slow things down， if you told the compiler， by the way。

 give me all of these other functions that I'm never going to use。 So in short。

 just don't do that because it's unnecessary。 But a good question。

 Other questions on what we've done。Here。Yeah， in front。What is it a Y is C faster。

 A Y is C faster than other languages。 Let me answer that in more detail in week 6。

 when you'll see how much easier it is to write code in other languages。

 because someone else is doing a lot of the work for you。 So as an introductory course。

 we're sort of teaching you bottom up， like， how do you write code has the computer understand code。

 eventually， this kind of stuff， certainly after like 5，6 weeks of this。

 It's gonna get tedious doing some of these things。

 we're gonna switch to another language that takes away the tedium and allows us to really focus on the problems to be solved once we've sort of graduated to that point。

 Yeah。😊，Sure to repeat the keyboard shortcuts， you can just go up up up up up and that will go through all of your previous commands at which point you can just hit enter。

 or you can use tab completion so you can start typing a word like code and COD tab will finish the thought or dot/ COM tab will finish that thought just to save yourself some keystrokes and clearing the screen is control L。

😡，Which has no functional purpose other than keeping things neat and tidy in class。

 So a design question。 So this code， I dare say is correct。 Let me zoom in a little bit here。

 Let me change the code to just do this。 even though we already saw from scratch。

 that we probably shouldn't do this。 Why should we not do this。

 if especially I'm just more comfortable asking three separate questions， like if X is less than y。

 if x is greater than why if x equals Y， do this。 Like it's a nice world to live in。

 just ask your questions。 You don't have to worry about if else if forks in the road。

 you can just ask three questions。 but let's。Put a finger on， why is this correct， Yes。

 but not well designed。Yeah， in backingham。Okay， there could be cases that are potentially outside of these three because this is relatively simple math comparing numbers。

 Like we don't have to worry about that here。 But yes， in general。

 you might miss a scenario without using a catch all like else。😡，Yeah。

 so maybe more than one of them could be evaluated as true， not going to happen here， but yes。

 you could accidentally create a situation where two things print or three things print because you didn't really think about the boundaries among these questions that you're asking。

 again， not applicable here， but in general， a good concern。😡，You're forcing to compete。就し在。

Really good。 really， what's concerning here in this example is you're slowing the computer down by wasting its time。

 having it do work that is logically unnecessary even more so than the scratch in the first C example。

 Y， suppose that I type in one for X and one for Y。 because I wrote this code top to bottom。

 this question is gonna be asked no matter what the answer is gonna be false。

 This question is going be asked no matter what the answer is going to be false。

 This question is going to be asked， and no matter what the answer is going to be true。

 We're okay there， because we had to ask all three questions。 But suppose I did the first thing。

 X is one， Y is2。 Then this first question is going to be true because x is less than y 1 is less than two。

 So this is going to print。 And yet then I'm wasting everyone's time asking is x greater than y。

 even though it obviously isn't is x equal to y it obviously isn't。

 you're adding you're doing three times as much work in that particular case。

 it's just not good design。 And again， for those of you who think a little more visually。😡。

We can actually make this picture to match。 Here is a final flow chart for bad code， bad design， why。

 because no matter what when you start the program and you want to stop the program。

 you're going through all three of those darn questions no matter what whereas the previous flow charts got us to the stop bubble faster by taking alternative arrows based on true or false answers so in short。

 still correct but bad design， and so again， even for problem set one when we start writing C code。

 consider not just getting the job done but how you might get the job done better than you might otherwise。

😡，Alright， let's add a few other features into the mix。

 Here we have those same data types that are supported by C。

 Let's focus for a moment on something a little simpler。 just chas， single characters。 unfortunately。

 for better for worse than C， the language makes a distinction between strings of text。

 which are generally words， phrases they can confusingly。

 be single characters or even zero characters if you don't type anything in between the quotes。

 but more on that another time。 But when you know from the get go that you only want to get a single characters back from the user like why for yes and for no。

 for instance， which is super common in programs， you can get that using a char and Cs50's own function。

 get char。 So how might we use this。 Well， let's go back to VS code here。

 I'm gonna to close compare dot C and let's write a third program altogether。

 Let's call this one agree do C。 And this is meant to represent like terms and conditions where you have to check a box yes or no or something like that。

 In this program。 I'm going go ahead and do the following。 I'm going go ahead and。

includelude CSs50 so we've got it， include standard Io do H so that we've got it in main void because we have to do that for now more on that another time。

 And now let's ask the user a question， do they agree So I'm going call get cha and then passing a prompt of do you agree question mark with a space semicolon。

 But as before with get string and get in those functions return a value So I want to assign that value from right to left to a variable。

 which I could call answer again， but honestly this program so short。

 I'm just going to use the letter C which is conventional So C for cha I for int or n for number are very common。

 But one more thing， what's still missing。For my variable here， the type。

 I need to say this shall be a char， not an int， not a string， a single char。 Al right， now。

 what do I want to do， I can ask a question if C equals equals lowercase Y。

 then go ahead and print out just so we see something on the screen agreed period backlash N as though they agreed to the terms and conditions else。

 if C equals equals lowercase N go ahead and print out， for instance， not agreed。

 just so we see something on the screen。 So let me hide my terminal window and focus on the code。

 there's a couple of details here that are a little interesting。 So one。

 what did I do online line 7 and 11 that is not consistent with what I've done before。三楼。

So I'm using apostrophees or single quotes now instead of double quotes。 why it's a C thing。

 when you're using strings， you use double quotes。 when you use single chas， you use single quotes。

 So the argument to get cha。 That's still a string。 It's a whole sentence that I'm passing in。

 So that is just like get in just like get string。 But when I get the answer back the return value and put it in this variable。

 And I want to check what is that one char。 I have to surround the cha I'm comparing against in single quotes or apostrophees both through the y and for the n。

 So this programs not super well designed because it's not gonna handle upper case。

 it's not gonna handle weird inputs very well。 but let me open my terminal window。 make agree enter。

 the code compiles okay dot slash agree， do I agree， Let's try it。 Why for yes。

 Okay let's try it again， dot slash agree and for no， not agreed。

 Let's do it one more time let's very enthusiastically。 say yes in all caps。

 and it just kind of ignores me。But why？ Well， this is a feature of C S 50's get char function。

 If you tell us you want to get a char， we're not going to tolerate a whole string of text from the user。

 We're gonna prompt them again and again and again until they give us just one cha。 So what， yes。

 is three times too long。 So let's actually just do a single capital Y and see what happens。 Re。

The program ignores me all。 So， allright， this is kind of a poorly designed program。

 It's a little annoying that we'll just ignore humans。

 even if they type in Y or N that just happens to be uppercase。 So let's improve this。

 Let me go ahead and add a couple more conditions。 else， if C equals equals uppercase Y。

 then go ahead and print out agreed， same as before， and then down here。

 else if C equals equals capital and then let's go ahead and print out again， not agreed。

 So this is now more correct， it's still going to ignore bogus input that makes no sense。

 if it's just like the word if it's a different letter altogether。 But this two code。 while correct。

 in some sense， is still poorly designed。 Even if you've never programmed before。

 what rubs you the wrong way。About this code now。Be critical， yeah。Yeah。

 it'd be nice to's merge the lowercase and the uppercase Y together the same thing for the lowercase and the uppercase and why。

 if only because like literally lines 9 and 12 are identical lines 17 and 21 are identical。

 And while not a huge deal， know if I go in and I change this sentence。

 odds are over the course of my lifetime programming， I'm going forget to change this one。

 even though I change this one， or I'm going forget to change this one in this one。

 So you don't want the code to get out of sync potentially。

 and you certainly don't want to repeat yourself。 So don't repeat yourself as a ten of programming too if you can avoid that by somehow factoring out some commonality。

 you should do so similar in spirit to math when you factor out variables or the like。

 So let me tighten this up so to speak。 let me get rid of what we just did so that it's a little shorter as before。

 And let me express myself with two conditions using the following syntax。

 I want to check if C equals equals lowercase y， or C equals equals uppercase Y。😊。

You can actually use what's called a logical operator， two vertical bars。

 which means or and we can do this down here or C equals equals capital N。

 So same exact functionality， but to your point， we've now eliminated what like another one。

 It was like what14， It's like 8 lines of code now are gone。

 which is eight fewer lines that I might screw up in this program。

 less opportunity for mistakes or bugs， Probably a good thing。 So now if I run this。

 let me open my terminal window。Let me run， make， agree， enter， dot slash agree， enter。

 Do I agree capital Y。 Now， it seems to be handling both of those situations。

 So just a little tighter。 as an aside， we won't use it here。

 But if you want to say and which would be nonsensical。

 it a little confusingly is too ampers sand means a logical and whereby the left thing has to be true and the right thing has to be true。

 So it's too bullolean expressions at once， this one makes no logical sense， though。

 because a character cannot be simultaneously lowercase and uppercase。

 it's got to be one or the other。 So two vertical bars is logically correct。

 that represents our notion here of or。Question。No。Yeah。You could not write or。

 so I'm saying or just because that's a little more normal， but this is incorrect。 However。

 sneak preview in the language of Python， you actually will literally say or among other things。

 which gets a little more user friendly。😡，Other questions on this here。Other questions and back。

 no where's the hands？Searching， yes and back。Is there an easier way to handle case sensitivity。 Yes。

 and we'll show you that next week In fact。 so we can combine this code to be even tighter。 Allright。

 let's do one final set of examples before taking a cookie break if we could。

 but let's go ahead and close a agree do C here。 let me open my terminal window and let's go ahead and implement a sort of virtual cat as we did last week。

 I'm going code up a file called cat do。 and I'm gonna implement this in a few different ways。

 the first of them pretty foolish。 So here I'm going include standard I O do H。

 no need for cs5 just yet in main void inside of these curly braces。

 let's go ahead and do printf Miow to get the cat to meow and then to save time。

 I'm gonna copy paste that two more times。 So this cat shallow three times in total。

 I'm going go ahead and make the cat So to speak。 all good dolash cat enter and meow three times just like our scratch cat last time I'll stipulate This is correct is a really well implemented cat correctness wise。

 But why is it bad design。😊，just like last week。Sorry。I sorry。I keep repeating the code。 I mean。

 I literally copied and pasted， which is sort of your first obvious sign。

 I'm probably doing something wrong If I'm copying and pasting because I'm literally repeating myself。

 So to spoil it。 like odds are a loop is probably gonna be our friend here。 And so in fact， in C。

 we have those features as well。 So in the world of C。

 we can implement some of last week's same ideas and a few different ways。

 These are a little more mechanical。 But suppose we want to repeat something literally three times Sctch gives us a repeat block with an input so easy。

 C and a lot of languages is's gonna be a little more mechanical。 and it's gonna look ugly at first。

 it will take some getting used to， but it is a paradigm you will use again and again and again。

 this will become very rot memory before long。 Here is how we might do this in code the lines of code on the screen are how you would implement the single yellow puzzle piece here in C。

 So there's a lot more work going on。 But why in C， we've got variables。

 we've got operators So we can do things like counting math incrementing， decrementing so。

To implement the idea of repeating something three times， we need to do the equivalent of like。

 all right， start with three， print something。 Then we have two， print something。 Then we have one。

 print something all done。 when we get to0。 We just need to very pedantically count from like3 on down or from 0 on up。

 So here are some lines of code。 Give me a variable called I I for integer。

 but we could call it anything we want set it equal to3。 We've seen code like that before。

 We haven't seen a while loop before。 But just like the preposition implies while I is greater than0。

 do this thing。 What thing the thing in between curly braces。 And this is fortunately。

 a typo because I change one thing， but not the other。

 So let me remind and pretend that never happened。😊，Okay。Didn't see that。

 let me start this over real fast。So first line， we have int I equals3， which is a variable。

 assigned the value of 3 from right to left。 We've seen that before。

 What is new is this preposition while， which is saying while I is greater than 0。

 do the following And the following is what's inside of these curly braces。

 And at the end of the curly braces， but still inside。

 we're doing I minus minus which just subtracts one from I。

 So I sort of have the framework here for starting at3 going to2 going to1 and hopefully going to0。

 at which point this Boolean expression， which is part of the while loop。

 not just ifs and else ifs and elses kicks in2。 So what am I going do inside of these curly damn it。

😊，What am I going to do？Inside of these curly braces。Spoiler， okay。

So what am I gonna do inside of these curly braces。 I want to actually go ahead and print out meow。

 but just once。 and I'm gonna let the loop handle the mechanics of doing it again and again。

 So how do we actually implement this then in code and get it running。 Well。

 it's gonna be pretty much the same idea。 Let me go back to V S code here。

 I'm gonna get rid of all of this copy paste and inside of my main function。

 I'm gonna do exactly what we saw In I equals3 semicolon while I is greater than0。

 then go ahead and print out with printf Miow backlash n and then be sure you decrement I and notice that lines 8 and9 are not only indented。

 they are inside of that while loop， so to speak， which means they will both happen again and again and again。

 because what's happening in code here is those curly braces are kind of like the yellow pieces that are hugging the other puzzle pieces in scratch。

 It will keep doing this， But every time through that loop or cycle。😊。

expression will be checked again and again and again until the answer is false。

 at which point the computer is going to jump to the last line。 And if there's nothing left。

 that's it for the program。 No more to be done。So same exact idea in scratch。

 even though it's a little more mechanical。 So that's how we might implement this。

 And you can think of it。Sort of these variables。 This is perhaps a little gratuitous。

 but let's do this。 So if you have a variable inside of a computer's memory。

 And that's the detail we'll get to in more detail before long。

 you can really think of it just as like a container that stores values。 So for instance。

 this clear plastic bowl。 It can be thought of as a variable。 It just stores values。 And right now。

 there's obviously three stress balls in it。 So it represents the number 3。

 So what's really happening in code like this is we've initialized I to 3， which is this bowl。

 We're then checking the question on line 6 is I greater than 0。 obviously。

 So we proceed inside of the curly braces and we print out meow。 We then decrement I。

 So for the sake of unnecessary drama。 like that's decrementing the variable。

 So what's being stored in this this container now is one less。 We do it again， check the count Nope。

 two is greater than0。 So we keep going nowow。 decrement I Check the variable。 one is greater than 0。

 So we print meow decrement I。 we check the condition again。 I。😊。

Is not greater than 0 because 0 is not greater than 0。 And so the rest of the code stops executing。

 I'm not sure if that was any more effective than fingers on my hand， but we had the ball。

 We had the ball。 So same exact idea。 Vas are just storing some value and incrementing and decrementing would just be adding or subtracting stress balls in this case。

 But there's other ways we could do this。 In fact， let me zoom in on my code here。

And it's not really conventional in programming to count down。 like nothing wrong with it。

 It's just not really a thing。 We would typically count up。

 So we could alternatively do this set I equal to 1 initially。 So we count 1，2，3。

 like a normal person。 And we can change our condition if I'm gonna count from one，2，3。

 What should my comparison be in my Boolean expression here。I is less than three。

Less than or equal to3， I think。 So if I is initialized to one。

 we're going to go through this one times， two times three times I is going to eventually get incremented to 4。

 But at that point，4 is not less than or equal to 3。

 So it's only going to execute a total of three times。 But there's still a bug in this code。

 What other line needs to change。Yeah， so line 9 needs to become plus plus。

 so this code is just as correct。 and honestly， you could reasonable people will disagree。

 Your TF might say do it this way and not this way。 but like this is still correct。

 but it's not the most conventional way as per last week。

 computer scientists and programmers generally actually start counting from0 by convention for reasons willll soon see So the better way。

 the more conventional way， arguably would be always start counting from 0。 count up to。

 but not through the number you care about。 And so this form of the code is probably the most popular way to do it。

 Start at0 count up23 but not through3 as with less than or equals that。

 All three are correct can't really do counting up as easily with the bowl without picking up the balls。

 but the exact same logic applies。 And in fact， this version of the code is so commonly done that there's a different way to implement it all。

 there's a similar way to implement it all。 In fact， this code here， same exact。



![](img/dd24156253db04e74fc14922ba497b1f_32.png)

T repeatpeing three times because it's so commonly done that you want to initialize something to0 and keep doing something until like the value 3。

 you can actually use a different preposition 4， which is another keyword in C。

 and it looks a little more cryptic， but it just tightens things up。

 this is what's called a four loop。 previous is what's called a while loop。 And honestly。

 even though it probably to the newbie still looks just as cryptic。 It's just a little tighter。

 because you're expressing all of these ideas on one line。

 You specify the variable you want to create and initialize you specify the Boolean expression。

 you want to check again and again， you specify what increment or decrements you want to happen。

 and confusingly， you do use semicoons here， not commas。 you do not put semicolon here。

 you of course， don't put them after these things。 you generally only put them after functions thus far。

 So we do have one semicolon here。 But in short， this you'll get more comfortable with。

 this is how I， for instance， almost always write a loop， but it's doing the exact。

Same thing mechanically as this。 Sam thing is counting on your fingers。

 Sam thing as counting the stress balls。 There's just different ways to express the exact same idea。

But there are ways to screw up。 So， in fact， let me go ahead and do this。 Suppose that the cat。

 we'd like the cat to live as long as as possible。 and we don't want it to stop meowing after just three or a finite number of times。

 How can you do something forever again and again and again， Well， let me go back into V S code here。

 let me delete all of the code from earlier， and let me go ahead and say while something is true。

 I'll come back to that， let's just go ahead and print out meow backlash n ideally forever。

 But what do I want to put in here。 Well， if I want to do something forever。

 I could do something kind of stupid like while one is less than two。

 which is always going be the case。 or while 50 is less than 51， which is always gonna be。

 I could just ask an arbitrary question but arbitrary not good in general。

 you should have meaning behind your code。 So if you want the expression to be true all of the time。

 just say while true because true is not changing anytime soon。 if it's literally true。

 It's always gonna be true。 the only caveat is to use this trick for now。

 you will need to include the C50 library， which for today's。



![](img/dd24156253db04e74fc14922ba497b1f_34.png)

urMake that possible。 But there's a problem。 of course， if the cat's going to live forever。

 if I do make cat dot slash cat enter。Like you can very quickly lose control over your terminal window and you can see like the meowos are flying across the screen。

 at least based on the bottom from what we're seeing。 like this cat will never stop meowing。

 And this is either a feature or a bug so to speak。

 depending on how long the cat here should live virtually but how do you terminate a program that is out of control like this infinitely So one of the takeaways for today is control C is your friend for cancel or interrupt the program。

 if you ever sort of lose control over our program because you've got intentionally or unintentionally an infinite loop。

 you can go into your terminal window， hit control C。

 sometimes multiple times if it's ignoring you and that will break out of the program and just essentially forcequi it like in Max or PCs。

 But let's make one improvement here still， the last thing we did with our cat in scratch before now we take a break in a moment was we defined our own functions and recall that we did that to abstract away the idea of Miowi because scratch didn't come with a Miow puzzle piece。

 C definitely does not come with a meow。Function we have to implement it ourselves。

 So quickly toward the end of week 0。 we did this。 define a function called Miow that just plays the meow sound。

 And now we have a meow puzzle piece we can use and reuse in C， we're about to do this。

 And this is gonna look a little cryptic， but it's gonna lay the foundation for future weeks when we do this even more。

 I've got a meow function weird mentions a void。 that just means there's no input and there's no output for this function。

 It just does one thing simply and that one thing is printf Miow。

 So how do I use this here code here in scratches how we used it last week。

 when the green flag is clicked repeat three times the meow function in C， it's gonna look like this。

 It made void and all of that。 And I can use a four loop a while loop。

 I'm copying and pasting the four loop version of the code said I equal 0。

 make sure it stays below three incremented on each iteration or cycle and just call meow。

 So what's nice here is that we have fairly simply away in C to create our own function called meow or anything else that lines up perfect。

😊，With what we did in scratch， we'll take some time to get comfy with the syntax and remember it。

 have to look it up frequently for reference。 But let's go ahead and actually do this。

 If I go back to V。 S code， clear my screen， Let me hide my terminal window temporarily。

 Let me go ahead and invent this meow function per the code earlier。😊，I'm gonna go ahead and do this。

 void meow void。 And again， the two voids mean no input， no output。 It just does one thing。 Well。

 printf quote unquote meow back slash n。 And now down here， I can use a for loop。 So4。

 and I know this for memory I equals0 I less than3 I plus plus and then inside of curly braces。

 I'm gonna go ahead and call the meow function。 notice when I'm creating the function up here。

 I explicitly pedantically say void void， no input， no output。

 When I use the function online line 13， you just say open parenthesis close parenthesis。

 That's the equivalent of a scratch puzzle piece without a white oval。 You just put nothing there。

 You don't put the word void。 So that's it。 Let me open my terminal window。

 let me run make cat to rerun to recompile dot slash cat。 And I think I have a working cat。

 Now this is correct。 the only thing I don't love about this version。

 If I hide my terminal window is that when。😊，Start writing bigger and bigger programs。

 It'd be nice if my main function， which I told told you to sort of take on faith for today。

 is at the top of the file， if only because like literally the name main means this is the main part of my program。

 It'd be nice if it's the first thing I see， which is to say just to be pedantic。

 It's very common to put any functions you write at the bottom of your file。

 maybe alphabetically maybe organized some other way。 but you put main first by convention。

 just like the when the green flag click。 It was the first thing you always started with last week。

 But watch what happens now。 if I go into my terminal window and command or control J is hiding and showing it if you are curious。

 but probably you'll just leave it open on your own all the time。 Let me do makeca again。😊。

And I've screwed up somehow。 All I did was move the meow function from top to bottom。

 and I'm getting call to undeclared function Miow， something something something。 Well。

 what's going on。 Well C is pretty naive and simplistic。 It's only gonna do what you tell it to do。

 And it's only gonna do things top to bottom left to right。 And unfortunately on line 8。

 you are telling C call a function called meow。 but that does not exist in C 50's header file that does not exist in standard I O header file。

 It exists at the bottom of my file at which point it's too late because I'm trying to use it before it exists。

 So I could just undo that and put this me function at the top of the file。

 But you're gonna eventually get into a perverse scenario where you can't put all of your functions above all of your functions like you got to pick a lane at some point。

 So the solution to this albeit a little weird。 And the one time and Cs50 in programming that it is encouraged and necessary to copy paste is what you can do at the top of your code be above main is just copy paste the first。

Line of your own function。 This is the socalled prototype of the function。

 and it simply describes how to use the function。 and funny enough， we actually saw this earlier。

 but I sort of kind of swept it under the rug a moment ago or bit ago when we looked at standard Io do H and we looked at the printf function in the manual pages。

 I highlighted the header file。 but I also glossed over the so-called prototype。

 which is sorry the first line of the printf function just as this is the first line of my Miow function。

 This is like a little clue。 This is like saying to say， hey。

 there's going to be a function called meow that takes no input has no input， takes no input。

 has no output， just know that it exists eventually and that will satisfy the compiler because if I go back to my terminal rerun make cat it now knows on faith per line4。

 this function will eventually exist。 And indeed once it gets to the bottom of my code line 14 onward。



![](img/dd24156253db04e74fc14922ba497b1f_36.png)

![](img/dd24156253db04e74fc14922ba497b1f_37.png)

In fact is。 So you just copy the one and only first line of your functions code to the top called the prototype。

 And now if I do dot slash cat， I get finally， meow， meow， meow， yet again in this case。

Questions on these here， cats。No， all right， then the last flourish before I keep promising cookies that I promise they exist。

 So last flourish， like just as we did in scratch。 So in scratch。

 recall that we parameterized our meow function by letting us tell Miow how many times to meow so that we didn't need to use our loop inside of our when green flag clicked block。

 In other words， if I want to actually have the cat Miow a specific number of times。

 I can actually go ahead and do that proactively with some of my own code such as this here in scratch。

 When I edited my meow function last week in scratch。

 I specified that I want it now to take an input called N which represents some number of times。

 And I change my repeat block not to be three perpetually。

 but to actually have n generally baked in there instead or actually instead of just saying place on meow。

 I had a repeat block using N as the placeholder instead of a hard coded3。

 So how can I now use this in C in C， it's almost the same。😊。



![](img/dd24156253db04e74fc14922ba497b1f_39.png)

It's still void at the beginning of my function name， which means no output still。

 It only has side effects。 But what did change， Visa V， the previous version of Mio。What has changed？

Exactly， instead of saying void a second time in parentheses。

 it literally says int N inside of those parentheses， which means in C， this function called meow。

 takes input。 It means the exact same thing as the pink on the left。 And again。

 this is why we keep emphasizing the scratch box。 like no new ideas with a lot of these features。

 It's just different syntax that you'll get used to over time。 So if I go back into V S code here。

 And I change this function， let's do that。 Let's change my prototype to be int N where n represent some number of times。

 Let's change the actual function on line 14 to also have int N here。

 And let's actually move the for loop from main into the meow function such that I now have my curly braces here。

😊。

![](img/dd24156253db04e74fc14922ba497b1f_41.png)

I have my print statement inside of those curly braces and now in Maine。

 I can get rid of all of that code， just say Miow any number of times like three。

 and just like I did with scratcht， let me hit enter an arbitrary number of times sort of out of sight out of mind。

 now the essence of my program is like one real line of code。

 Miow three times because I've abstracted away the idea of Miowing and told the cat instead exactly how many times to Miow by way of that function。

😡，O， I can't keep stringing long cookie so long。 Let's go ahead and take a 10 minute break here。

 And when we come back， more cats， more code。All right。So we are back。

And w to add one final flourish to this program because now more so than a lot of the examples。

 like now the programs are starting to grow in length and indeed soon there'll be a few dozen lines of code。

 which is not uncommon。 but let's suppose that we want to stop hard coding 3 everywhere and actually prompt the user for some number of meos here。

 Well let me do this in V S code。 I'm gonna go ahead and get rid of this one line for now。

 and let's do something like this。 let's ask the user for an integer。

 So in maybe n for number equals get in and we'll say something like just number to give a number of meos。

 And then we'll go ahead and actually call meow passing in not3 this time but passing in n。

 So we are using the return value of get in to store it in a variable called n on line 8。

 And then we are passing n as the input or argument to the function called meow On line 9。 And again。

 the actual implementation of meow online 22 onward like who cares out of sight out of mind once it。

We can sort of abstract it away mentally， but I'll keep it up tightight here anyway。 Allright。

 so let me go ahead and open my terminal window。 make cat dot slash cat number。

 I can still type in3 and it works， or I can go ahead and type in5。 meow me maow。

 but it's not actually meing five times why。😡，I didn't realize this either， but there's a bug。Yeah。

 exactly。 so the four loop， when I copy pasted it before before break。

 I actually kind of got lazy and I forgot to change the three to an n so that it matches the name of the argument that's being passed into meow。

 So that was a bug unintentional on my part， but we have now fixed it here。

 and now we are passing this n from main to meow。 So if I make cat dot slash cat and type 5 this time I indeed get five meos。

 but it's worth noting there's some subtleties here in my code in that I've used n a couple of times。

 So this is actually deliberate that I've used n twice in this way to induce a bit of confusion。

 but it turns out this n is's actually not the same as this n nor this one。 So what's going on here。

 Well it turns out in programming， there's often this idea of scope。 and long storyory short。

 generally speaking variables only exist in the scope in which you create them more down to earth。

 variables。Only exist inside of the curly braces in which you defined them。 So， for instance。

 suppose I got a little sloppy and suppose I didn't bother giving me meow an input。

 and I didn't bother giving its prototype and input。

 And I just used n on line 14 because why well I already defined n on line 8。

 So this is just an alternate universe in which I'm not changing meo to take input。

 I'm just using n in two different functions in main On line 8 and 9， actually。

 I don't even need that On line 8 and 9， And also， again， On line 14。 This code will not work。

 like the compiler will not like this。 Y because N does not exist inside of Miow。

 Y per the heuristic I offered n exists only inside of the curly braces in which it was defined namely these curly braces here。

 So N is in scope in main， So to speak， but it is not in scope in Miow。

 And that's why we kind of have to jump through these hoops and use inputs and。

Outputs and inputs and outputs and pass things around among functions without sort of sharing things across functions instead。

 Now， I could clarify this and maybe change my argument here from n to like times。

 if I want to make clear that oh， this is the number of times I want nowo to be said。

 I don't have to use n for both， but just realize that if you do it's just a coincidence。

 they are not usable in two different scopes。 All right， let's do one other thing though。

 let's not keep let's not only prompt the user for the number here。

 let's make sure that it makes sense what number they give。

 So if I do make cat just to clean things up cat。 suppose I type 0， Okay， I suppose that's correct。

 if I say meow zero times and it doesn't meow at all， that's arguably correct。

 But if I type in something like negative5， it ignores me。

 which I guess is better than crashing or freezing or something。 but ideally。

 it might be nice to handle this situation。 And if they give me a negative number prompt them again for a positive number。

 prompt。Again， for a positive number。 Like make the program make sense。 So how could we do that。

 Well， a couple of ways， if I go back into my code here， I could do this。

 I could maybe do something like a loop or let's see。 So if I get N。 So if N is less than one。

 then it makes no sense。 So what do I want to do if n is less than one。 Well。

 I could just prompt the user again。 And I say， okay， let's get n again。

 And then I can say if n is less than one。 What do I want to do， I guess we could ask the user again。

 And then if n is less than one。 like could just again， like I can give them like three tries。

4 tries to get this right。 Like this is obviously stupid。 Like I'm copying and pasting。

 I'm repeating myself， there's no end in sight。 Like I can't do this forever， Sure。

 So this just feels like the wrong solution。 So there are different ways to solve this problem。

 and funny enough， like a while loop is not really the best way a do while loop is a while loop is not the best way。

 A four loop is not the best way。 It turns out there's one other type of loop。

That we want to introduce that's super useful for getting user input potentially again and again and again。

 so that the user cooperates。 specifically what I'm gonna do is this。

 I'm gonna literally say do the following while something is true。 So it's more of a mouthful。

 I'm spreading it out over multiple lines。 But what am I gonna put inside of the do block here。

 I'm gonna say int and equals get int and ask for that number as before， close semicolon。

 and I'm gonna keep asking while sorry， accidental enter while n is less than one semicolon。

 So notice the semantics of this， even though it's a little weird looking， it does read in English。

 do the following， okay， get in int stored in n and keep doing that while n is less than one。

 But this code as in is not quite going to work yet。 Let me try opening my terminal window。

 make cat enter。 damn like use of undeclared id。NWell， here's where the line number is helpful。

 The line number is indicated here，12， and it's repeated here 12。 So it clearly screw up at line 12。

 but there's not that much going on at line 12。 Y is N undeclared。😡，In line 12。

 even though I literally just declared it in line 10。

Exactly because I declared an inside the scope of the do block。

 so to speak inside the curly braces on lines  line and 11。

 that variable n no longer exists by the time we get to line 12。 It'd be great if it did。

 but it doesn't because it violates that heuristic， I propose。

 which is that variables only exist in the scope of the curly braces in which they were defined。

 So how do I fix this。 Well， it turns out you can declare a variable in advance outside of one scope。

 but then define it。 that is initialize it elsewhere。

 So the solution here is actually this inside of the loop。

 just set n equal to the return value of get n， but per the heuristic。 you've got to declare n。

 make it exists inside of the outermost scope of this function。 So it's a little weird。

 and we're kind of breaking this down into two steps， but this is valid， recommended correct C code。

 you declare a variable without giving it any value initially， And then in line 11。

 you proceed to give it a value， potentially。Again and again and again。 Now。

 what's useful about a do while loop。 So a do while loop as the name implies。

 we'll do something no matter what， but it will potentially do it again and again and again。

 while some question is true， like N being less than one in this case。All right， as an aside。

 why did we not do a while loop。 Well， let's think about that。 while n is less than one。

 but wait a minute， N doesn't have a value。 Okay， so I guess we have to go back to doing get int number colon semicolon。

 but while n is less than one。 We're back to the same problem where we have to repeat ourselves again。

 So this is why four loops， while loops。 not the right solution when you want to do something at least once but potentially again and again。

 So the right solution here again， is this new and final looping construct。

 I'm just hitting control Z a lot whereby we've done it as follows。 All right。

 let's try this clear the screen。 make cat enter dot slash cat， let's type in5 still works。

 let's type in negative5 and notice it doesn't just ignore me it prompts me again and again and again。

 even if I type in 0， I've got to at least give it a positive integer。 Well。

 this actually seems like kind of a common paradigm。

 Like what if we want to prompt the user for a positive number in other programs too， know。

 we're nearing。Point already， even after just week1。

 it would be nice to like write our own reusable functions that solve common problems。

 And eventually eventually， maybe we can put them in header files as well。 But for now。

 let's go ahead and do this。 I'm gonna actually copy all of this code。

 and I'm gonna create one more function in this file below main called get positive int for integer。

 And I'm gonna specify that it doesn't need any inputs。

 because the only thing this function is going do is that exact same thing。

 So notice that I've just moved my code for main into a function thats name describes what it does get positive int。

 I'm declaring n here。 I'm doing this again and again and I'm doing that while n is less than one。

 And what am I going to do up here。 I can do something like this。

 Give me a variable called times for how many times do you want to meow。

 and just call get positive int semicollon。 So now again。

 we've abstracted things away and just like in scratch。 our final example。

 which looked a little something like this where we just called a function to meow3。😊。



![](img/dd24156253db04e74fc14922ba497b1f_43.png)

![](img/dd24156253db04e74fc14922ba497b1f_44.png)

Now we're calling a function to get text。 If I hit enter an arbitrary。

 dramatic number of times out of sight out of mind。 I now have two functions in this world。

 Get positive int and Miow that are collectively implementing this entire program。

 but it's not quite correct。😡，There's one mistake here。 still。

 Notice that get positive int is written slightly differently from the Miow function。

 And just to be clear， too， let me copy its prototype to the top of the file just so we don't make that same mistake I made earlier where I didn't put the prototype at top。

 So C didn't know what it was。What is different about these two prototypes at a glance。Yeah。Okay。

 so get positive in apparently， and we've not talked much about this。

 apparently does have an output of type integer。 It's supposed to return and it hand me back and in。

 It doesn't have any input。 That's what the void and parentheses meant。

 No input but yes output and meow funny enough is the opposite。 Yes input。

 No output why because it has a side effect， the visual thing where it prints something to the screen。

 but doesn't hand me any useful value back like the ask function or the ask puzzle piece did。

 So these are sort of opposite and functionality， which means I actually need to return an integer from this function to whatever function wants to use it。

😡，So if I want the assignment operator to work here on line9。

 I need to do what all this time get int， get string and other CS50 functions have been doing。

 I need to in my own function， return that value， literally with a new keyword called return。

 and this is why I keep sticking out my hand when you want to function to hand you back a value。

 you literally use return and then that value， that's why we have return value as a term of art。

 literally the return keyword。😡，So if I open my terminal window now， make cat enter。😡。

 I did screw up accidentally。How， yeah。Yeah， so on lines 9 and 10， I made a quick change。

 I changed my variable to times， but I stupidly didn't change this。 So that's fine。

 That's why n was undeclared in that context。 Let me clear my terminal。 make cat once more。 Okay。

 that worked dot cat。 Let's type in5 and it's still working。 So again。

 even though the code feels like it sorry， Even though the code is kind of growing and growing and growing。

 It's the exact same program。 We wrote super simply before break。

 But now we're sort of modularizing it。 We're creating reusable functions。

 And this is why functions like get string exists， Get int exists。 like C50 wrote those years ago。

 And we realized why are we copying and pasting these functions in all of these different Cs 50 programs。

 Let's factor out that functionality into a function of our own get int。

 get string just like here I'm proposing to factor out this functionality。

 get a positive integer that gives you even more precise functionality。 So theoretically。

 you could use and reuse it in other programs too by not even just putting it here。

 We could go put it in a file of your own name and include。😊。



![](img/dd24156253db04e74fc14922ba497b1f_46.png)

It in future programs as well。 Like that's all a library is。 Someone realized geez， other people。

 including myself， might find this function useful again and again。

 let's package it up and our own custom functions， just like our custom Yaow puzzle piece last week。

 So we can indeed use it again and again。 And the takeaways for now is that unlike scratch。

 which was a little more user friendly in C， you have to specify if you want your functions to have inputs and you must specify if you want them to have outputs as well。

 But more on that syntax to come。 So where does that bring us。 So after all this discussion of code。

 like at the end of the day， like this is what's important in the world of programming。

 not surprisingly， it's like what's important when it comes to grading and evaluating the quality of code。

 one and first and foremost， is correctness。 like if the code does not do what it's supposed to do。

 what was the point of writing the code。 So correctness sort of goes without saying design again is much more qualitative。

 It's like getting feedback again on English say reasonable people might disagree。

 you can make your argument better， you can structure the paper better。😊。



![](img/dd24156253db04e74fc14922ba497b1f_48.png)

You can structure the code better in the case of programming and style is purely aesthetic。

 Does it look good。 Is it pretty printed， so to speak， Can other people。

 colleagues future and classmates present actually read and understand it That's what we mean by style。

 Nicely enough within CS 50's programming environment。

 you will have tools to evaluate the quality of all three of these axes so to speak。

 So in problem set one onward you'll be introduced to a command line tool that you type its name at the prompt called check 50 that will check for you the correctness of your code。

 not necessarily exhaustively like there might be mistakes you've made that we don't catch。

 which doesn't make your code correct， but it is a tool for finding many of the mistakes in your code in the real world。

 you would have colleagues or yourself would write tests for code you wrote or someone else wrote。

 So like testing code is not just a grading thing。 It is a realword thing to ensure that systems are designed correctly。

 We saw the style 50 tool in V S code already， you click the style 50 button。

 There is now thanks to the duck。 a design 50 button。😊，Also in that top right hand corner。

 whereby once your code is correct and working， like several of my programs have been。

 you can click design 50 and the duck will not just quack。

 but give you qualitative advice if it can on how you can make that code even better even before you submit。

 And of course， there's all of us humans in the room and online that you can ask these same questions of as well。

 So let's now solve some sort of real world， but still simple problems as opposed to emphasizing small bite size as we have thus far。

 So the first of these programs falls into this category if having side effects。

 So let's implement one or more functions that takes an arguments inputs and as its output produces these visual side effects。

 will'll draw inspiration from super Mario Brothers， not surprisingly perhaps here， the original one。

 which was very twodimensional side scroller left to right。

 Mario or Luigi move from left to right and generally have to jump over things like pyramids or other shapes on the screen。

 So how might we go about implementing some of the screens from Super Mario brothers all be a textually。

 we'll make it a little black。😊。

![](img/dd24156253db04e74fc14922ba497b1f_50.png)

In white and ASi art。 so to speak here using just our keyboard。

 But suppose we want to write a program called Mariio do C that just prints out four question marks。

 It's not gonna be nearly as pretty as what's on the screen here。

 but the logic is gonna be the exact same as what Nintendo presumably did years ago。

 So let me open V S code。 My terminal window。 let's code a program called Mario do C in Mario C。

 I'm gonna start with some boilerp。 I know I want to print。

 So even if I don't know how to do this yet， I'm going to include standard I O do H for today's purposes I'm gonna copy paste or type out that same line again and again in main void And inside of my main function akin to the green flag being clicked。

 I want to go ahead and print out four question marks。 Well， honestly。

 the simplest way I can think of doing this is with printf question mark mark question more question mark maybe backlash and to move the cursor and that's it。

 So that is arguably correct。 So let's do make Mario in the terminal do slash Mario。

 And it's not quite as pretty as the game version of it。 but it is， in fact，😊。



![](img/dd24156253db04e74fc14922ba497b1f_52.png)

![](img/dd24156253db04e74fc14922ba497b1f_53.png)

![](img/dd24156253db04e74fc14922ba497b1f_54.png)

Exact same idea。 But here's sort of an opportunity。

 stepping stone to do better design like this game changes over time。

 And not all of the screens have just four question marks。 It might be 5，6 or even more。

 So what's the right programming construct with which we could generalize how many question marks are printing here。

Like what feature of C do we want？Like a loop， like a for loop， a while loop or something like that。

 And there's different ways to do this。 but honestly I've proposed earlier that we get into the habit of reaching for four loops as just very conventional。

 So let's do that for int I equals 0， I less than4 because that's how many I want for the moment。

 I plus plus and then inside of my curly braces there， let's go ahead and print out， quote unquote。

 a single question mark， but no new line。😡，Let me now go ahead and make Mario。

 And can you anticipate a arguably aesthetic bug when I hit enter。

 It's not going to move the cursor to the next line。 But the solution here is a little non obvious。

 I don't think this helps me If I put the back slash end there。

 And I do make Mario again in dot slash Mario。 What is this output gonna look like instead。Yeah。

 like a vertical column of question marks， which while nice enough is not the goal at hand。

 The goal is these horizontal ones。 So someone else。

 what's the fix here if clearly putting the backslash and inside of line 7 is wrong。Yeah。

 so put it after the loop and not after the printf line specifically after and thus outside of the loop。

 so that after that loop is finished executing three total times。

 it's totally fine to just print nothing other than a backlash n。

 So long as we now recompile the code。 make Mario do slash Mario and voila。

 Now we have four in a row。 It's a little generalized。 Okay。

 so we've sort of plucked off a fairly easy problem。 Well。

 let's go back to the world of Mario and try something that is， in fact， vertical like this。

 So this is another scene with like three bricks here。 instead of using question marks。

 We'll use hash symbols to represent bricks。 This actually is the incarnation of my mistake a moment ago。

 So let me undo this by getting rid of that printf。😊。



![](img/dd24156253db04e74fc14922ba497b1f_56.png)

![](img/dd24156253db04e74fc14922ba497b1f_57.png)

Let me change the inside one from a question mark to a hash symbol。

 which looks the most similar in ASI to a brick。 And let's go ahead and put in backlash n after that。

 if I do go ahead and do make Mariio。 dotlash Mariio， it's not that interesting。

 but and it's actually not that correct because I want three So no big deal I can of course go back to my code and change the four to a three or better yet I could use get int or my new get positive int function and just generalize this further so that I can print out any number of them。

 But for now dot slash Mariio gives me three All right so we plucked off the second of two problems。

 let's now let things escalate a bit。 So it turns out once you get to like world2 and beyond there's some underground parts of Mario where you actually have bigger。

 more solid bricks like these here and just by eyeballing it。

 This is like a three by three grid of bricks like9 of them total conjecture So how can I go about implementing this now is where the program gets a little more interesting and the sort of not Well the。



![](img/dd24156253db04e74fc14922ba497b1f_59.png)

![](img/dd24156253db04e74fc14922ba497b1f_60.png)

![](img/dd24156253db04e74fc14922ba497b1f_61.png)

![](img/dd24156253db04e74fc14922ba497b1f_62.png)

![](img/dd24156253db04e74fc14922ba497b1f_63.png)

Designed way to do this would be like printf， hash hash， hash back slash N semicolon。

 and then maybe printf printf。 like that's kind of like correct， but not well designed。

 So make Mario dot slash Mario。 know， it doesn't look like a square just because these hashes are more vertical than they are horizontal。

 but it is correct。 this example， but it's not very generalizable。

 And this is like literally hard coding， I copy paste。

 And I'm just doing a lot of bad practices here。 So what could I do instead。 Well。

 it turns out we can combine today's ideas， including loops to do things again and again。

 So what is this grid of bricks。 It's a three by three。 So that's like。

 know it's like a row and a row and a row And then within each row。

 there's like column column column。 So it too is like an oldtimey typewriter that sort of prints one line than the next line then the next line and so forth。

 So how can we conjure that in code。 Well， let me go ahead and do this。😊。



![](img/dd24156253db04e74fc14922ba497b1f_65.png)

![](img/dd24156253db04e74fc14922ba497b1f_66.png)

Think a print approach would work is like this for int I equals 0。

 I less than3 I plus plus because I know I want to do something three times。

 but what do I want to do three times This loop kind of represents in my mind's I， row， row， row。 So。

 in fact， I could be more pedantic。 if I want my I to mean something beyond int。

 I could say row equals 0 row less than3 row plus plus just to help me think about it。

 And then what do I want to do on each row。 What do I want to print。



![](img/dd24156253db04e74fc14922ba497b1f_68.png)

Like column column columns， or brick brick brick。 So how do I print three bricks or any number of bricks。

 Well， I could kind of cheat and just do printf hash hash hash back slash n。 but again。

 I can't generalize， I can't take an input from the user and print4 or 5 or six bricks。

 So that's gonna get me into trouble eventually So maybe I could use a loop。

 So I could do like for int I equals 0 I less than3 I plus plus inside of my loop。 And then in here。

 I could print out one hash。 And that's kind of on the right direction。

 the right path because now I'm just using the simple building block or brick but reusing it again and again。

 And it's totally fine to have nested these columns in this way。 I used I out of habit。

 but what would a better name be well maybe column or maybe just COL call for short。

 so that my code is sort of saying what it does for me。

 And I don't have to use row or column explicitly。 I don't need to print them。

 But I am using them as counters 1 after the other。 So let me go ahead and run make Mario。



![](img/dd24156253db04e74fc14922ba497b1f_70.png)

Dt slash Mario。 And I'm feeling good about this， but。Damn it， there's nine bricks。

 but they're not really laid outright。Why， what's the fix？Yeah， I never went to a new line。

 And let me do what I think you're not gonna to suggest。 I do。 Let me just go to the obvious place。

 Allright， well， let's put one right after the brick。 But， of course。

 if I do make Mario dot slash Mario， I'm making the same mistake as before。

 I'm printing out too many new lines。 So in between。

 what lines do I actually want to print a new line。Between yeah。Yeah， so 10 and 11。

 So outside of the inner loop， but inside of the outer loop。 So it happens again and again。

 So let's just print out as before a single backslash n semicolon。

 Now let's do make Mario dot slash Mario enter now it's generalized as I see fit。

 And if I really wanted to dwell on this I could go in and I could prompt the user with get in or with get positive in。

 figure out what row and or column should be。 we can make any size brick that we want。

 But now we have sort of a nice starting point。 But there's another way to think about this because I dare say especially for like your first C 50 problem set if you're trying to print bricks And the world of Mario in this way。

 it's probably not gonna be obvious to come up with loops like this and just magically get it working after like 45 seconds in total。

 itll be a struggle at first。 But there are some patterns to follow。 So one。

 it's pretty conventional。 nonetheless， to use just I and then J and then K and then L and if you've got nested nested nested。

 nested4 loops at some point nesting， you're probably。Bad code。 It's not well designed。

 but one or two or maybe three nestings could be an okay thing。

 but you cannot use and reuse I again and again， why， Because if you're counting I here。

 but then you're changing I here to do your columns left to right。

 You're gonna get all of your math out of sync。 So you need two separate variables。

 I and J or conventional or row and column would work too。

 But if we go back to this idea of rows and columns， Well， let me actually factor something out here。

 And this might help you instead， suppose that you set out on this problem。

 you know you want to do something like three times。

 but you don't quite understand how to print those rows。 Well take a baby step。

 a bite out of the problem， and maybe do this create a function with no output just a side effect。

 whose purpose in life is to print a row。 and how many rows Well maybe N for some number of row for some number of bricks rather。

 how do you print a row of bricks。 Well， let me just think about this in isolation。

 How do I print a single row of bricks。 That's easy。Or int I equals0， I is less than n。

 If I'm generalizing I plus plus and then whoops I plus plus and then inside of my curly braces。

 go ahead and just print out a single hash。 And at the end， as you suggested。

 print out a single new line。 In other words， abstract away the idea of printing a single row。

 And in fact， at this point in the story， especially if you're struggling to get started。

 you don't even need to start with main。 like take a bite out of the problem that makes sense to you that's smaller than the whole problem printing a single row。

 because then you can come in and iterate。 Then you can go in and say， okay。

 now let's write my actual main function。 So in main void as always。 And now what do I want to do。

 I want to print out a whole bunch of rows。 How do I print out a whole bunch of rows。 Oh my God。

 it's like the same idea  for int I equals 0， I is less than let's call it three for now。

 But we can generalize that I plus plus And what do I want to do on each iteration of this loop。

 My gosh， Just print row。With three bricks and then we're sort of done right again。

 out of sight out of mind， this function can go away and never be seen before because once print row exists。

 that's what it， in fact， does for me。 Now this isn't100% correct。

 I still need my prototype because if I've made my own function。

 I need to tell C in advance that it shall exist。 or I need to copy and paste that one line of code。

 if I were really being pedantic， this is bad design， in general。

 when you have the same number in multiple places in a program。

 a programmer would call this a magic number， like how is that working。

 like you're just honor system that you're using the same number again and again。

 So a better solution here。 even if you're not gonna to take user input would be to do this in and equals3 and then use n here and then use n here or you could call it anything you want。

 But now youve specified3 in one and only one place。 And we can go one step further。

 It turns out in C and in another languages， you can protect yourself against yourself。 if you know。

That a variable should never change its value。 It should always stay three in this case。

 You can use what's called a constant where you can specifically say。

 I don't want just end to be an int。 I want it to be a con int， Cons for short for constant。

 And this means even if I try to change n in my code， the compiler will not let me。

 So I can protect myself from myself or in the real world。

 you can use a variable that none of your colleagues can foolishly change on you without you realizing that it has happened。

 So a lot of programming honestly is just you know not trusting yourself the next morning when you've forgotten what code you wrote。

 let alone the next month， the next year when you're writing code in the real world。

 So constant just give us a feature to defend against ourselves。

There's another feature that's useful too， especially when you wake up the next day you're like oh my God。

 like how does this code work， What does it do Well， there's comments in code。

 And some of you might have used this in scratch， you could add little yellow sticky notes in scratch for comment in code。

 you can do something like this。 you can if you want to put in English reminder to yourself。

 or if you speak some other human language a comment in Spanish or any other human language。

 you can write it with a slash slash at the start of the line。

 and then you can say something like print N rows。 And then this tells you in a comment what those subsequent lines of code are doing。

 it's sort of a note to self。 It has no functionality for the computers sake。

 It just is a note to yourself。 or you can say something like this。

 like never change n because you're making clear that it's indeed constant。

 but that too is a little pedantic since con says the same。

 But comments are notes to self to help you remember what is something is doing or why you did it this way。

Questions now on any of these Mario。Problems that we have solved。No。Al right。

 so one final set of examples that push the limit of like what computers can actually do thus far we've solved like every problem I proposed。

 that's because I've kind of been skirting some of the underlying challenges。

 So it turns out that we have not only functions that give us side effects like visually on the screen。

 We again have functions that have return values。 So let's focus on those and where things that where things can go wrong。

 and let's use a bunch of other operators as well。 suffice it to say computers got their start by being really good calculators。

 So computer support addition subtraction multiplication division remainder operators represented by the percent sign here。

 which says take the remainder of something over something else。

 And there's even more operators than this。 So let's go ahead and implement our own calculator of sorts that actually has some bugs along the way。

 Let me go back over to BS code here。 I'll close Mario do C。

Open my terminal and code up one final file called calculator dot C。 And in this calculator file。

 let's go ahead and do something super simple。 initially， Let's go ahead and include C S 50 dot H。

 Let's include standard I O dot H。 Let's do int main void， as always， all boiler platelate thus far。

 And now let's do something more interesting。 int X equals get int。😊。

And we'll prompt the user for an x value。 int Y prompt the user for a y value。

 As we've done previously for comparing numbers。 And let's just do something super simple。

 Let's give myself another variable。 int z equals x plus y。 and then let's print out the sum。

 So print F quote unquote and I don't want percent S here。 If I want to print out a number。

 Someone said it earlier。 we want percent S for string， but percent I for integer。

Back slash n and print out the value of Z。 So it's a little silly。 This calculator。

 it just adds two numbers together， but it's going demonstrate some points。 So make calculator。

 enter。So far， so good。 dot slash calculator。 Let's just say X is1。 Y is 2。 Z is going to be 3。

 This code is correct， Simple， though it is。 Is there an opportunity for marginally better design。😊。

Could we tighten this up， make it shorter， fewer lines means less lower probability of bugs。

 probably yeah。😡，Yeah， we don't really need a separate variable Z。 I mean。

 it's fine if it's clearer to you。 if it's clearer to your TF。 if it's clearer to your colleagues。

 But honestly， this is so relatively simple， I think we just get rid of Z and just say something like x plus y here。

 which is totally reasonable as well。 But you don't want to take this to an extreme Heck if we don't need Z。

 do we really need x and y。 Well， we could do something like this。

 Let me actually whoop let me actually delete these lines of code and claim we can do this all in one very pretty one liner we could do say get int X plus get in y。

 and notice now kind of like the join example last time。

 I'm calling get int once get in twice both of them return of value。

 which is like gonna be one and two respectively based on what I typed earlier。

 then I'm doing one plus2， that's going into printf as the second argument like this is actually correct and will work。

 It's just just stupid。 Like don't do this。 Like we've crossed some ill。😊。

Find line where this is just harder now to read。 And so even though the variables aren't strictly necessary。

 I would argue。 And I think most programmers would argue this is just much more readable。

 Each line is doing a little bit less work。 There's less chance for error。

 It just makes a little more sense。 But reasonable people will disagree。 So therefore。

 this will this is to say over time， too， like you and your TF might disagree。

 You and your colleagues might disagree。 And at that point。

 is when the sort of religious debates kick in as to which way is the right way。Alright。

 so that's one calculator。 Let's do something else that maybe just like doubles a number here。

 So let me change this to just get one integer from the user。 Let's just call it X。

 And let's just double it quite simply。 So printf percent I back slash n X times 2。

 will quite simply double it。 The star operator is indeed multiplication in this case。

 So that's going to go ahead and double my number。 So make calculator again。 dot slash calculator。

Enter， and let's go ahead and type in one， and I get back two。 Let's run it again。 type in2。

 I get back four。 type it again。 Let's type in3。 I get back 6 and so forth。 Alright。

 so that's not bad in this case here。 but what if we actually want to write a proper program here。

 In fact， Yeah， let's see this is sort of a meme that comes and goes。

 Let me see if you recognize this。 I'm gonna go ahead and say another variable net X。

 let's be more specific。 like dollars equals1。 And then let me deliberately induce an infinite loop。

 Sometimes it is useful to induce an infinite loop So long as you eventually break out of it somehow。

 if you don't want the program to run forever。 I'm going ask the user question asking them for a cha C using get cha。

 and I'm gonna ask them quote unquote， here's percent I period， double it。

 and give it to the next person question mark。 This is ringing a bell。

 And then we can pass in to get cha the dollars value there。 So actually。

This looks a little cryptic already。 I'm gonna put a dollar sign in front of it as though we're actually dealing with US currency。

 And what do we want to do， How about if the user says why for yes。

 double it and give it to the next person， then let's go ahead and do dollars and let's double dollars So I can do dollars equals dollars times 2 or recall the trick for plus and minus。

 I can also do times equals2， which just doubles it in one line as well。

 Just little syntactic sugar as programmers call it that just tighten up your code even though it's the exact same thing。

 But what if the user does not type why and they want to keep the money。 Well。

 we have an else condition， at that point， you don't want to keep asking asking asking asking them with getchar。

 let's just break out of this loop instead， So break is another keyword that if you're inside of a four loop。

 a while loop， a do while loop， you can forcibly break out of the loop early。

 if and when you want to。 And so this sort of satisfies the goal of making sure that this doesn't run forever。

 But it is gonna run again and again and。while we keep prompting the user with this question。

 So let's see now what happens， except at the end， let's go ahead and make sure the user knows like how much money they're walking away with。

 Here's dollar sign percent I backslash n。 So we will see at the end of this。

 whatever dollar amount the personar ends up with。 Make calculator enter dot slash calculator。

 And let me increase my terminal window size。 So here we go。 Here's 1 dollar。

 double it and give it to the next person。 Yes， here's2， double it and give it to the next person。

 Yes， yes， yes， yes， yes， So you know， the Instagram reels aren't that long。

 But if like you keep doubling it again and again， this is called exponentiation。

 which will make you quite wealthy quite quickly， because notice。

 we're already in the thousands of dollars by just saying yes and yes and yes。

 it's an interesting sort of societal question as to what dollar amount you would keep the money and no longer double it and pass it on。

 But for now， we'll just keep doubling it because this is just getting bigger and bigger。

 Seeing the infinitely large in the C program。 But oh my God。Like apparently。

The Instagram reels cut off the meme too short because eventually it goes negative and then 0。 like。

 what's actually。Going on here。 like the code is actually correct。

 but we're bumping up against a different kind of problem。

 Any instinct for what is actually going wrong here。 It's not doubling forever。Yeah。😊，Yeah。

 there's not enough bits to store bigger and bigger numbers。 recall with 32 Bs。

 which happens to be how big most ins are。 you can count as high as 4 billion。

 if you start at 0 or roughly as high as 2 billion， if you want to handle negative numbers as well。

 negative $2 billion to positive 2 billion。 So eventually once it get to like $2 billion or $1 billion。

 it goes negative。 and then it just goes to 0 altogether。

 This is because of something called integer overflow whereby if you only have a finite number of bits and you keep incrementing them。

 incrementing them， incrementing them。 eventually you can't just carry the one because there's no 33rd bit。

 So all of the other bits wrap around from ones to zeros， and it looks like all 32 of your bits are0。

 because the 33rd bit was supposed to be the one。 but it's not there。 they don't have enough memory。

 So this is a fundamental problem with computers whereby if you count high enough。

 things will just start to break。 at least if you're using C or c plus plus or certain other languages that don't anticipate this。

 And there's。Very real implication of this。 So here's here's a photograph of something we'll look at more in time to come like of memory inside of your computer or phone or any electronic device。

 Suffice it to say there's only a finite amount of memory。

 And if you're only using 32 Bs then or heck even 3 B。 you will eventually overflow。

 We use 3 bits last week。 So here's an example in binary。

 if you're only using 3 bits per the white digits here。 I've put in gray the fourth。

 just to show you what carry we might want to have here's 0，1，2，3，4，5，6，7， just like last week。

 And just like last week， someone said， how do we get to 8， we need another bit。

 But if that bit is grayed out because it doesn't exist。

 we've just overflowed this tiny integer and gotten back to 0， just like my money went to 0 instead。

 So how do we actually avoid that know， one way to do this is this。

 Let me hit control C to break out of the program。 or I could just type no。

 Let me shrink my terminal window。😊，And clear it here。 I could actually do this。

 It turns out that ints use 32 B， typically， but there's another data type that was on the slide before called long。

 which is a longer version of an int， which is 64 B， which is crazy big。

 There's not that many dollars in the world， but it's still finite。

 even though I can't pronounce the number that big。 But if we change all of our ins to long。

 And we change our placeholder from percent I to percent L I for long int。

 I can actually count higher and higher。 So case in point， let me actually go back to my terminal。

 make calculator enter。😊，Make it larger again。 dot slash calculator。

 And I'm just gonna keep saying yes， but faster this time。 The sequence is exactly the same。

 But recall that once we got into the billions， it started to wrap to negative and then 0。

 This is a lot of money now。 Like longs are indeed longer。 And I could do this probably all day long。

 Oh， interesting。 No， okay， I shouldn't have said that。

 can't do this all day long because eventually， a long too will overflow。

 I just didn't think it was gonna happen that。😊，So a long two will overflow because we'll need a 65th bit。

 but the computer has not allocated it。 So that too becomes an issue of overflow to read an excerpt。

 like these are very real world issues。 And in fact。

 here's a photograph of a Boeing 787 years ago that actually had issues beyond the most recent issues with Boeing airplanes。

 whereby after 248 days。 the Boeing 787 years ago can lose all of its electrical power due to the generator control units simultaneously going into failsafe mode。

 whatever that means。 But if you dig into this。 It turns out that there was a software counter in these airplanes years ago that would overflow after 248 days of continuous power。

248 days， Well Boeing was using a 32 bit integer。 and they were using it to count1s of seconds And it turns out if you do the math after 248 days。

 you have used too many1s such that you overflow the size of a 32。Bit integer。

 the plane would essentially have this integer， this tiny， stupid little variable overflow。

 but generally speaking when your numbers suddenly go negative or0， bad things happen。

 the plane could literally lose its power， midflight or on the ground and if you can believe it anyone want to guess what Boeing's workaround was till they fix the actual software。

😡，我在。Not even reboot the plane。 like they were told every few days， Certainly every 248 days。

 turn the power off， turn it back on， which stupidly is what all of us have been told for years with our Mac and PCs and phones。

 Why， because sometimes because of bugs and software， computers get into funky states。

 which is a colloquial way of saying like some programmer made a mistake and some counter overflowed or some condition wasn't handled and just weird unexpected things happen So rebooting just resets all of your variables back to their original values and sort of gives you more time。

 more runway in this case， no pun intended。 There are others， In fact。

 one of the most famous ones from like the 1980s was the original pman game only had support for 255 levels。

 Why they were using 8 Bs recall that 8 Bs gives you 256。 when if you start counting at0。

 you can only go to 255。 So the crazy kids who were so good at packman that they got to level 256。

 The makers of PAman did not anticipate that anyone was going to win that many levels and just weird stuff。

Happened on the screen。 All of the fruits sort of started overwriting everything because they didn't have enough memory allocated to the level。

 nor did they have a condition that says if level equals equals 255， you win。

 like there was just nothing handling that corner case。 so to speak。

 So these things abound even these days， thankfully， in some languages。

 there are better solutions where you can use big integerors。 And you'll just use 64， maybe 128。

 maybe 256 B。 but you need to use a language or a library that allows you to grow and shrink the amount of memory being used。

 and many， if not most languages do not do that for us。

 So there's a few final problems to see that we've been taking for granted thus far。

 And they also involve numbers and memory。 So let's go back into our calculator。

 Let's throw away all of this meme code here。 And instead。

 let's go ahead and do something simple again。 int X equals get int and prompt the user for variable Xt y equals get int。

 prompt the user for a variable。IAnd this time， instead of addition， instead of doubling。

 let's do division。 So print F， quote unquote， percent I back slash n。

 and then plug in x divided by y。 So use a single forward slash for division。

 Let me go ahead and make calculator down here。 dot slash calculator。

 And let's go ahead and do one divided by three， which should， in fact， be。😊，It's not really 0。

 right， is's like 0。333。 Let's try this again。 How about dot slash calculator 3 divided by 2 should be 1。

5。 Nope computer thinks it's 1。Well， what's happening here。 Well。

 it turns out when you're using integers in a program。

 you are vulnerable to what's called truncation。 an integer plus an integer gives you an integer。

 In integer divided by an integer， funny enough， gives you an integer。

 So even if the answer is supposed to be 0333 or 1。5。

 everything in the world of integers throws away the decimal point onward。

 and you only get the integer part of the value。 So it's not even rounding。

 It's truncating everything after the decimal。 So this program is just not correct。

 but there are solutions potentially， for instance， if I go back into my code here。

 And I use a different format code we haven't used yet。 We had s for string I for int。

 There's also F for float and a float was a real number。

 something with a decimal point in it by definition， we just haven't used it yet。

 I could tell the computer to print this as a float。 So let me do make calculator again。

 And now it's specifying type double。 There's an error here。 The problem。

Is that I can't just tell the computer to format this number as a float。

 I need to convert the number x divided by y to a float。 And I can do this in a couple of ways。1。

 I can literally change all of this to floats and just avoid the problem altogether。 use float。

 use get float， use percent F and I'm done。 But if I want to use ints for whatever reason because I want the user to type in integers。

 but I want to show them real numbers with decimal points for correct math。

 I can do what's called casting a value。 I can in parentheses。

 which is a weird new use of parentheses， I can say， hey， computer。

 please treat the following integer as a float instead， thereby avoiding truncation。

 do not trunnccate for me。 So if I now run， make calculator again。Dot slash calculator and type in。

 for instance，1 for x，3 for y。 Now I get an actual floating point value。 I'm formatting it as such。

 and I'm telling the computer to actually arithmetically calculate it as such as well。But here， too。

 I'm kind of cheating you of a reality。 It turns out， let me clear this screen here。

And it turns out that there are fancy ways in printf to tell it how many digits to show you。

 how many significant digits。 And the syntax is very weird， I have to look it up constantly。

 But instead of just saying percent F， you literally put some numbers in between there。

 And you say point5。 And that will say it's weird syntax， hey。

 print F format this to 5 digits instead。 So let me go ahead and do make calculator again。

dot slash calculator。And let's do one divided by3。 And indeed， I get five significant digits there。

 But suppose I get a little crazy。 and I want 50 significant digits。 Well， according to grade school。

 I should just see more like  threes， But watch this make calculator， dot slash calculator。

 And it turns out that whoever taught you grade school math was kind of telling you some white lies because if you really do it with a powerful Mac or PC or phone。

 one third is actually 。3333333343267，44079 who's right。😊，Mr。 Mrs。

 so and so from grade school or like。The Internet。What's going on here？What explains this。

 It all comes down somehow to weak  zeros， zeros and ones。

Why is this floating point number imprecise， so to speak。What's the intuition？Yes， similar in spirit。

 just as ints only use 32 bits， floats also use only 32 bits if you want more， just as int has long。

 floats have something called double， so I could kind of avoid some of the problem by switching to double。

 but that's still going to be finite and if you think about this intuitively。

 if you're using a finite number of bits be it 32 or 64。

 you can only represent literally so many patterns and thus so many floating point values。

 so many real numbers， but how many real numbers are there in the world。😡。

Like literally infinitely many is the challenge of real numbers。

 you can just keep adding numbers after the digit。 So how could a computer。

 Mac PC or otherwise possibly represent every floating point value super precisely if there's not enough patterns to represent every number in the world Moreoverover。

 the way the computers used to represent numbers sometimes do not allow them to represent numbers so precisely we can get more significant digits maybe but not 100% perfection or precision So floating point precision too is a fundamental problem with computers today and unless again。

 you're using a specialized language or library that understands for scientific computing。

 the implications of overflow or imprecision， your code will have mistakes much like Boeing discovered。

 much like PAacman discovered as well and in fact， just to end on a gloom and doom node。

 it turns out there's another problem like this on the horizon already。 So back in my day。

 everyone was really worried about the Y2k problem the year 2000 problem why because for decades when computers were invented。

Most systems were using just two digits， independent of bits， two digits to represent years。

 Why computers came out a few decades ago， who'd think that a computer is still going to be running decades later。

 turns out they were， especially in government and corporations and the like。

 but if you're only using two digits to represent years and the millennium comes around and it's 1999 about to roll over about to roll over what comes after 1999。

 Well if you're only using two digits ideally 2000 but if you're only using two digits。

 the year 0 comes after the year 1999 and the whole world truly look it up nowadays on Wikipedia was freaking out because there were so much old software in the world that could have had this mistake and who knows planes falling out of the sky computers rebooting freezing like no one really knew because this was an unhandled situation and code So thankfully the world actually got its act together。

 the world did not end in the year 2000 and most systems were updated in time without crazy horror stories。

 but we're gonna have this happen again because it turns。Just a few years from now， at this point。

 computers for years have been using 32 B integers to keep track of time in the sense of like what time of day it is。

 And the point in time they decided years ago was hey， like hey， everyone。

 let's just keep track of how many seconds have passed。 since January 1，1970。

 And we can relatively compute time any time thereafter。 So that's great。

 That gets us a lot of decades worth。 But 32 bits eventually maxes out at like 4 billion positive or 2 billion if you want negative and positive。

 And it turns out if you count the number of seconds between 1970 on up on the day January 19，2038。

 the world might again end because all of these clocks are going to overflow。

 And we're gonna to end up in the year 0 or negative something。 Now what's the solution there。

 I mean， my God， it's the exact same thing。 like stop using so few bits use more bits。

 but bits and memory and computers used to be expensive。 Nowadays， storage is so much more available。

 But among the。😊。

![](img/dd24156253db04e74fc14922ba497b1f_72.png)

We'll discuss then is how you can throw both hardware and software at this problem。 But for now。

 if set a Google calendar reminder for January 19，2038， and hopefully we'll see you next week。

