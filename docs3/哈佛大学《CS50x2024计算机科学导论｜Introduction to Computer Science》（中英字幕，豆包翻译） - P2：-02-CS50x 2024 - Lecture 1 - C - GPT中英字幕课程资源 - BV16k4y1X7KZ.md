# 哈佛大学《CS50x2024计算机科学导论｜Introduction to Computer Science》（中英字幕，豆包翻译） - P2：-02-CS50x 2024 - Lecture 1 - C - GPT中英字幕课程资源 - BV16k4y1X7KZ

![](img/9b3478adcf58801ce6a8c57047480262_0.png)

🎼Yeah。

![](img/9b3478adcf58801ce6a8c57047480262_2.png)

![](img/9b3478adcf58801ce6a8c57047480262_3.png)

![](img/9b3478adcf58801ce6a8c57047480262_4.png)

All right， so this is CSs50 and this is week 10 index so to speak and it's not every day that you can say that you've learned a new language。

 but today is that day today we explore a more traditional and older language called C and rest assured that even if what you're about to see no pun intended looks very cryptic。

 very unusual particular if you're among those less comfortable cling to the ideas from last week week zero wherein we talked about some of those fundamentals of functions and loops and conditionals all of which are coming back today Indeed。

 whereas last week and with problem set zero， we focus on learning how to program with scratch。

 which again you might have played with as a younger student days back today we focus on C instead。

 but along the way， we're going focus as always， frankly on learning how to solve problems but among the goals for today and really on an entire class like this is just to give you week after week all the more tools for your toolkit so to speak via which to do exactly that So for instance today。

We'll learn how to solve problems all the more so with functions as per last week we'll do the same with variables。

 we'll do the same with conditionals with loops and with more。

 but we'll also learn at the end of today's class really how not to solve problems it turns out as powerful as max PCs。

 cell phones are nowadays there's actually certain things that they can't do very well and the information they can't represent very well and that actually leads to a lot of real real world problems。

 both past and surely future So more on what we're not going to be able to do with programming before long but beyond that。

 let's come back to this picture here so this was the very first program that I wrote that you wrote presumably in some form and all it does is say hello world but as promised today this puzzle piece or these puzzle pieces together are going very quickly start to look more like this and deliberately color coded in and a way so that the text on the screen now kind of resembles the puzzle piece so if I go back notice that we had this when green flag clicked puzzle piece mostly in yellow with the green flag。

That sort of kicks off the whole process once you actually click the button at top right of scratcht's user interface and then there's the purple block。

 which actually is the verb， the action， the function that does something so if I bring us back over to what we're about to see today there's going to be some boilerp so to speak some orange text here on the screen that for now you just kind of type and take for granted like you need to write your code like that but more interesting is going to be the purple and we're going to see today that the function previously called say in scratch is now called print F in this language called C but in white here you'll see similar text to our white oval last week whereby that's where user input like your input as the programmer can actually go so there's a lot of distraction and honestly it's these kinds of things that tend to distract and get frustrating early on when learning to code for the first time but the ideas most importantly are going to be the same so how are we going to go about using this while it turns out like last week you're going to start writing something called source code so code as we know it quote unquote is more technically called。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_6.png)

That's what you and I as humans actually write and indeed it might look a little something like we just saw。

 but unfortunately computers only speak this binary zeros in ones more properly known as machine code In other words those same patterns of zeros and ones last week someone guested print out hello world on the screen because one of those patterns is an H another pattern is an E an L and L and an O and so forth and then other patterns of those zeros in ones our commands or instructions to the computer that literally say show H ELLO comma world on the screen but machine code would not be nearly as much fun to write if it were indeed in zeros and ones entirely for us ideally you and I are going to write source code which conceptually sort of up high level but we're gonna to need a program to convert it to the lower level machine code so that we don't spend our lives actually having to read and write zeros and ones which back in the day kind of in yesteryear you kind of sort of did with things called punch cards and holes。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_8.png)

On physicals sheets of paper we're beyond that because after years and years of innovation folks have given us higher level languages instead so here's what we're gonna to need to do today at the end of the day you and I are writing source code but we want machine code as output we need something in the middle that's going to convert that source code to machine code you and I are not going to have to learn or talk about really anymore zeros and ones and the type of program we're going to start using today and introduce you to is called a compiler so a compiler is a program that translates one language to another and it could be any two languages but today and often we'll talk about it in the context of source code to machine code so this is Apple or Google or Microsoft or folks from other companies or even volunteers who have written software that do this conversion you and I are essentially going to download a free compiler and use it to actually get our computer to understand the source code that you and I write in these higher level languages so where are we going to do that what we could actually give you instructions and。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_10.png)

Could download the appropriate free open source software onto your own Mac or PC the reality is that creates so many technical support headaches because we all have slightly different computers。

 we all have slightly different versions of Windows or Mac OS or Linux or other operating systems and that too tends to be a distraction the beginning of any course like this or learning programming so we're going to use the cloud instead we're going to use a URL of the form https colon CS50。

 dev and what this will do for you is put inside of your browser window absolutely everything you need for the course but it's going to use software software called visual studio code otherwise known as VS code that's actually free itself it's very popular in industry it's what real programmers use every day but it's a cloudbased version thereof and so everything will just work for you out of the box but toward the end of CS50 the goal is going to be to get you off of CS50's infrastructure to get you to download this free freely available software onto your own Mac or PC if you so choose so that those training wheel。



![](img/9b3478adcf58801ce6a8c57047480262_12.png)

So to speak and come off and then even if you never take another class again。

 you don't need any classes' infrastructure moving forward。

 you'll have everything you want and need on your own Mac or PC but for now it'll save us a bit of time So in just a bit I'm going to go to that URL myself on my computer and I and you will see in user interface that looks a little something like this the colors might be different based on your settings fonts might be different and so forth but in general consists of a few different regions so over here at the top is where we are going to start writing code today so it's a tabbed interface like any number of programs nowadays and this is that same C code we saw a moment ago so this is where in a moment I'm going to start to type it over here at the bottom is what we're gonna to call a terminal window or a console and the terminal window is where we're gonna to type commands for compiling our code for running our code and we'll see today a contrast between a graphical user interface or Gui which has menus and icons and things you click and are very familiar with versus a command line interface or。

😡，I and so we're using both of these together and command line interface just means down here you only use your keyboard。

 you can click click click if you want me your mouse it's not gonna to generally do much because a command line interface takes commands at the keyboard so in a weird sense it's going to feel like taking a step backwards from the Mac the PCs the iPhones and Android phones we all have which are very graphical but it turns out once you become a computer person or a programmer。

 you can be a lot more productive， a lot more efficient I dare say by learning to harness the command line interface and using both types of interfaces for what each is good at so more on that in just a bit over here at left。

 you're gonna to see soon a folder interface like Mac OS or Windows where any of the files or folders we create in CS50 are going to end up as well so it gives you sort of the best of both worlds you can point and click on the left or you can type commands at the bottom as we'll soon see and then along here is the so-called activity bar where there's just VS code specific features but also CS50 specific features and if you're in your own version of CS50。

Click through in the dot dot dot menu or zoom out so you can see everything you'll see CS50's zone rubber duck virtually speaking that will be there throughout the course to answer any and all of your questions as well So more on that soon too So here's the code that I propose that we write first just like we wrote our very first scratch program to say hello world So let's go ahead and do exactly this I'm gonna switch over to this screen here where I've already logged into CS50 dev on my computer and just to keep the focus on the code I've hidden the activity bar I've hidden the file explore so to speak so you're seeing here the area where all of my tabs are about to go and the terminal window where all of my commands are going go but I've just simplified the UI to keep our focus on the interesting parts for now So how do I go about actually writing and compiling and running some code while the teaser is going be these three steps one of these is a command called aly code and code is just gonna to let me to open or create a new。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_14.png)

![](img/9b3478adcf58801ce6a8c57047480262_15.png)

File like a file called hellello do make is going be for now my compiler that allows me to make the program that is convert source code into machine code。

 So from C to zeros and ones and then weirdly but we'll soon see why do hello is going be the command to run my actual code So the textual equivalent of like double clicking on a Mac PC icon or tapping an icon on your phone So that's it。

 these three commands you're gonna allow me to write to compile and to run code ultimately so let's go ahead and do that I'm back in my VS code interface。

 I'm going go ahead and run code hello C and notice a couple of details here。

 So one there's this weird dollar sign which has nothing to do with currency but it's just a common convention in the programming world to represent your prompt。

 So if a Tf if I ever say go to your prompt we really mean go to your terminal window go to the dollar sign and the dollar sign is where you type the command。

 sometimes it's a different symbol but a dollar sign is conventional Now that Ive。😡。



![](img/9b3478adcf58801ce6a8c57047480262_17.png)

codeode space hello do C I'm gonna go ahead and enter and maybe not surprisingly this gives me a brand new tab。

 a new file， if you will called hello doc and just like word documents have their own file extension like do doc X and Excel files have Xlsx and Pfs have do pf and gs have do GF and so forth so do C files have a file extension by convention that is do C now a couple of minor points notice that by convention I'm almost always going name my files in lowercase by convention I'm never going use spaces in my file names and my file extension2 is going to be lowercase long story short accidentally hitting the space bar or using file names with spaces just tends to make life harder when you're in a command line environment so just beware silly stupid things like that So all lowercase no spaces for now so my cursor is literally blinking because the program wants me to write some code I'm going do this for memory it'll take you presumably some to acquire the same instincts but I'm going go ahead and type。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_19.png)

This first line here pronounced include standardIo do H more on that soon in main void with some parentheses thrown in notice what's about to happen here is a little interesting in the code I want to type I want what we'll call curly braces the sort of squiggles that you don't use often in English at least but are there on your keyboard somewhere but notice what VS code does and a lot of programming environments is it finishes part of my thought so I'm only going to type a left curly brace but notice I actually get two of them and if I hit enter notice that not only does it scooch one down a bit it also indentense my cursor because just like with pseudocode last week whenever you're doing something logically that should only happen if the thing above it happens similarly is indentation going be a thing when we actually write code So VS code and programs like it just try to save us keystrokes so I don't have to waste time like hitting the space bar or hitting tab or sort of wasting my human time like that All right So with that said I'm going go ahead and type the last of these lines print。

😡，F where the F is going to mean formatted and then a parenthesis and notice it gave me two。

 it gave me the second one for free， sometimes it will get confused and you can certainly override this。

 delete it and start over， and now unlike scratch in C。

 it turns out I'm going to need to use double quotes anytime I'm using an English word or phrase or any human language for that matter。

 hellello， comma world， and then at the very end of my line， much like English uses periods。

 I'm going to use a semicolon in C。😡，So that's a lot of talking， but it's not much coding。

 it's technically six lines of code， but honestly the only interesting one intellectually as we'll soon see is really line 5 like that is the equivalent of that say block now here's where I'll cross my fingers hoping that I didn't make any typographical errors it's going automatically save for me and I'm going go back to my terminal window where now I'm going to do that second command make space hello common mistake you do not say make hello do c because you already made that file you say make hello which is the name of the program that in this case I do want to create and make a smart。

 it's gonna look in my folder and if it sees a file called hello do c it's going to convert that source code to machine code and save the results in a simpler shorter name file just called hello like an icon on your desktop now hopefully nothing will happen and that is a good thing quite paradoxically if you do anything wrong when programming odds are you're going to see one or many more lines of errors sort of yelling at you that。

😡，made a mistake， seeing nothing happen is actually a good sign so the last command to run my code recalled our three steps here。

 we ran code to create the file， make to compile the file from source code to machine code so lastly is dot s hello so this now is the equivalent of my like double clicking on a Mac PC or single tapping on a phone。

😡，Pinter。So close all right， it's pretty good， I got the H ELLa space world。

 but there's something a little stupid about my output。

 what might rub some of you aesthetically the wrong way。😡，Yeah。Yeah。

 so the dollar sign looks like I was like hello world dollar sign in my output。

 but no that's just kind of a remnant of my prompt starting with a dollar sign and this is a little nitpicky but this just doesn't feel right doesn't look right it's not quite correct so how can I go about fixing this Well here's where at least initially it's gonna to take some introduction says like just new syntax and C to fix this like the simplest instinct might be to do this well let me just hit enter like that but this should soon if not already rub you the wrong way because in general we're gonna to see that programming and C and in Python in other languages tends to be linebased like you should really start and finish your thought on one line so if you're in the habit of hitting enter like this and sort of finishing your thought on the next line generally programming languages don't like that So this is in fact not going to do what we expect and just to show you as much I'm going do this let me go back to my terminal window here I'm going to rerun make hello after making that change enter and there we have it like the first of our erroneous。

😡，outputs and it's yelling at me， it's missing a terminating character and there's some red in here。

 some green drawing my attention to it sometimes these error messages will be straightforward。

 sometimes you're going to like rack your brain a bit to figure them out but for now I've kind of spoiled it obviously enter is not the right solution so let me clear my terminal window just to hide that error let me delete this。

😡，And let me propose now that I add this incantation here so backslash and it turns out is going to be the sort of magical way of ensuring that you actually get a new line at the end of your output so let me go ahead now and rerun make hello because I've changed my code I need to now reconvert recompile the source code to new machine code dot slash hello and now there is the canonical hello world program that I hoped to write in the first place so for now don't worry about the include don't worry about standard IO don't worry about int or main or void or the curly braces focus primarily on line5 here and over the course of today and next week we' start to tease apart the other characters that for now you should take at face value Que though on any of the steps。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_21.png)

We've just done， yeah。Sure， why is the backslash inside of the quotation marks if you will。

 so sort of answer is like that's just the where it needs to be because inside of the quote is the input that you want printf to output to the screen。

 so if you want printf this function to output a new line。

 it must be included in the quoted text that you give it。😡。

Exactly backslash n is a special pattern that print F no means okay。

 I should move the cursor to the next line， good question。

 other questions on any of these steps yeah。😡，A good question。

 So what if you actually want to print backslash and things get a little tricky there。

 Let me go ahead and propose that we do this。 So it turns out。

 and this is often the case in programming when you want a literal character to appear。

 You actually put another backslash in front of it。

 but this is not gonna to be something we do often， but there is， in fact， a solution to that。

 But let me propose that beyond that now， we sort of compare it against what we've actually done。

 So here is the first scratch program we wrote with the green flag there。 here recall。

 is the mental model that I proposed we have for almost everything we do whereby functions are just an implementation。

 say in code of algorithm， step by step instructions for solving problems。

 the inputs to functions recall from last week are called arguments or in some context parameters。

 and sometimes functions can have side effects like last time with scratch。

 there was the speech bubble that magically appeared next to the cat's mouth is a sort of side effect of using the say block。

 So just like this。 then we had。😡。

![](img/9b3478adcf58801ce6a8c57047480262_23.png)

![](img/9b3478adcf58801ce6a8c57047480262_24.png)

White oval as input the say block was the function last week and then we had this here side effect Well what how do we compare these things left to right well here's the say block at left let's compare now to the C code at right notice a couple of things to sort of adapt from scratch to C print is almost the name of the function it is technically print F for reasons we'll eventually see notice the parentheses in C are kind of evocative of the oval in scratch and that's probably why MIT chose oval because a lot of languages use parentheses in this way you still write hello world just as we did last week in scratch but per our demo thus far you do need the double quotes and double quotes not single quotes double quotes on the left and right and in order to get that new line you need the backslash and and one more thing is missing。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_26.png)

Yeah the semicolon to finish your thoughts so all of these sort of stupid things now that honestly you will forget initially if you've never programmed before but you'll soon within days within weeks develop the muscle memory where all of that stuff just jumps off the page right at you all right so these escape this backslash in is generally known just so you know as an escape sequence and so backslash in allows us to specify a character that might otherwise be hard to type but let's tease apart some of the other things atop that function already so include standard IO H it turns out that in C a lot of the functionality that comes with the language is tucked away in separate files so if you want to use certain functions you have to tell the compiler hey I want to do some standard input and output like I want to print some things on the screen and that's because for now you can think of printf as living in this file standard Io H that's a bit of a white live for now but in。

😡，Io。h is essentially a declaration for printf that will teach the compiler how to print things to the screen。

 so hash include here simply tells the compiler before it does anything else。

 essentially go ahead and find on the local hard drive a file called standardIo。

h and kind of copy paste it there so I know now about printf。😡，So this thing。

 this do H file is what we'll technically call a header file and if you've ever heard this word。

 especially if you have program before， it represents essentially what we'll start calling a library so a library in the world of programming it's just code that someone else wrote that you can use it's usually free and open source which means you can literally see the code that someone else wrote or sometimes you pay for it sometimes it's closed source which maybe Microsoft wrote it they won't show you the code but they will let you use the zeros in ones so libraries are super useful because honestly even I don't really know how printf works。

 I've taken for granted for 25 years that if I use printntf stuff prints on the screen but someone smarter than me how to actually write the code and C that figures out how to get the H the E。

 the LLO and so forth onto the Mac screen， the PC screen the phone screen or someone else so libraries allows us to sort of stand on each other's shoulders and so that someone else can do the hard work and we can now solve problems that are more interesting to us。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_28.png)

Not the basic commodity stuff that everyone might want in their code so again library code that someone else wrote a header file in C is just a file ending in do H that gives you access to the same and so for instance if you want to learn more about these there are what are called in the world of programming manual pages and these are textual files like documentation of sorts via which you can just learn how a function works and how you can use its inputs or arguments the reality is they're written for folks who aren't in CSs50 they're written for folks who aren't just learning how to program they're written for and by folks who have been programming for years and so frankly they're a little hard to understand and so CS50 has its own version thereof at this URL manual cs50。

o where you'll see not only the official documentation for C the language but also staff written simplifications in layperssons terms what all of the various popular functions are what their inputs and what their outputs are so for instance under。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_30.png)

Standardio H you can actually go to that website you can go to a URL like this where standardioh is in there and you can actually see the documentation there so let me go ahead and do this I'm going to go ahead in my browser here I'm going to go to manual cs50o and let me go ahead here and select those functions that are frequently used in CS50 and under standardIo H you'll see a bunch of functions only one of which we've even discussed called printf I'm going click on printf there and you'll see an interface that at first glance might be a little overwhelming but it's going to start to look more and more familiar so first of all you'll see that if you want to use printf under synopsis you need to include this header file like you literally copy and paste that line into your own code you'll also see this which for now is a bit arcane but this is kind of a hint as to what the function is going to look like but more on that soon but more importantly you can read a description about it and because these descriptions when you're in less comfortable mode。



![](img/9b3478adcf58801ce6a8c57047480262_32.png)

A written by me in the courses teaching fellows teaching assistant and course assistants。

 you'll find them to be much more in laypersons terms and so long story short rely on this site once you want to learn how to use some function and also what other functions exist in fact if I go back to the main page here you'll see that there are all of these functions like are frequently used in CS50 and there's hundreds more that come with C but learning a programming language is not about learning all of those but rather just getting a sense of where you find answers to questions when you do want to try something new but what is important to know for CS50 today is that we have our own header file called CS50。

 H which has functions that we have written just to make life easier in the first few weeks of the class these are training wheels that will eventually take off but it turns out in C especially a few program before。

 it's actually really hard and annoying just to get input from users to get them to type a word or a number or something else like C does not make this easy in part。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_34.png)

![](img/9b3478adcf58801ce6a8c57047480262_35.png)

Because it's one of the earliest languages that wasn't zeros in ones so you have to do a lot of the heavy lifting yourself but we'll put on these training wheels today and for a few weeks so that we can focus really on the intellectually interesting ideas of C and programming without getting bogged down in certain weeds that we will come back to before long so for instance CS50's own documentation is there at that URL but within the library A are these functions a function called get string to get a string of text string is a synonym for just text and a programming language so get string will prompt the human for a string of text get int is shorthand for get integer if you want to get a number from the user get float is a little more arcane get a floating point number like a real number with a decimal point in it and dot dot dot there are others as well so this is to say within CS50 we've got some user friendlyly functions via which we can actually get some input and let's go ahead and use one of these for instance get string because recall that last week。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_37.png)

second program in Sc was this one here where we didn't just say hello world。

 we said hello David or hello Carter， hello Yulia whoever it was typing their name in。

 but to do that we needed this ask block in scratch and then we use the save block and then we use the join block to kind of make all of this work so let's translate this program now into C because it's a little more interesting in representative of the kind of code will start to write but we need a slightly different mental model still have a function here which is the implementation in code of an algorithm we still have some inputs called arguments but previously I said that the save block and in turn printf have side effects which is just something visually typically that happens on the screen other functions actually have what we called last week。

😡，Return values and this is kind of analogous to a function， maybe doing something for you。

 writing down the answer on a slip of paper and then handing you the program or the slip of paper to do whatever you want with it without just broadcasting it to the world with like a speech bubble on the screen so a return value is germae for a program like this because recall when we use the ask block and I typed in my name where did my name end up initially。

😡，It didn't go on on the screen yet， where did it end up？

In an answer puzzle piece and that special oval puzzle piece I claimed at the time represents a return value so the sort of metaphorical piece of paper that the answer is written down on so that I can then use it later so that's what we want to get to now in C a return value that I can then do anything I want whether it's printed to the screen change it in some way save it in a database or anything else so here for instance is what we did with scratch the input to the save block or the ask block was what's your name quote unquote the function of course is the ask function and the return value was answer if we now consider how we might translate this to C it's going to look a little weird at first but it's gonna to follow a pattern today next week the week after anytime we do code like this so get string I claim is going to be the most analogous function in C to the ask block and to be clear this is a CS50 specific thing training wheels of sorts but we'll show you in a few weeks what this function is doing and how you cannot use it moving forward once。

😡，Comfortable with the language itself notice Ive put parentheses left and right as sort of a placeholder for user input and that user input is going to be what's your name。

😡，But I can't just put what's your name in parentheses， what do I minimally need to add in there to？

😡，Yeah， so the double quotes left and right， so let me go ahead and add those in。

 I left a space here， not for a new line， I could move the cursor to the next line。

 but I minimally at least want to move the cursor at least one space over just so it looks pretty so that when I'm prompted for my name。

 there's a space between the question and my answer but it could also be backslash n that's just an aesthetic choice on my part。

😡，But what do I do with the answer that comes back from Getstr。

 this is where the text is going to look different today in C you start to use an equal sign from left to right respectively。

 and on the left you put the name of the variable in which you want to store that return value So a return value is kind of a conceptual thing you can do with it what you want。

 and if I want to store it longer term in a variable like x or y or Z in math class。

 I can just give it a name here， X or y or Z or more reasonably answer or any other English word。

 no spaces generally lowercase， same heuristics as before， but this means now。😡，Ask the user。

 what's their name， whatever they type in， go ahead and store it from right to left in this variable called answer。

 but C's not done with us yet if you've learned Python or certain other languages you'd kind of be done writing code at this point and C though you additionally have to tell the compiler what type of variable you want to use so if it's a string of text you say string if it's an integer。

 a number you say int， as we might have seen before， so it's a little more pedantic。

 it's more annoying frankly the more onus on you and me the programmers。

 but this just helps the compiler know how to store it in the computer's memory。😡。

And I'm so close to being done with this line of code， but what's missing？😡。

So semicolon and mark my words， if you've never programmed before sometime this week this semester。

 you will forget a semicolon， you will like raise your hand。

 you'll get frustrated because you can't understand why your codes not working。

 you will run into stupid issues like that but do take faith it they are stupid issues。

 It doesn't mean it's not clicking for you or you're not a programmer it just takes time to see these things if it's a new language to you So there now is my semilon。

 All right let's go ahead then and do something with that return value using the second of the big puzzle pieces in scratch。

 So when I wanted to say hello comma David or whatever the human name is。

 I kind of stack my puzzle pieces like this。 this is actually similar to Python and maybe some other languages some of you have learned but C is a little bit different and the closest analog to this scratch solution is going to look like this。

 I still use printf because printf is the equivalent of say inside of my parentheses。

 I'm going to go ahead and say weirdly hello comm。😡。

Pcent S so there's no real analogancy of join instead there's a way to specially format text using printf hence the F in print F and what you do in print F is you type whatever English word or human words that you want you then use percent S as a placeholder if you want a string of text to be added to your own text you literally write percent S and let me anticipate a question from the crowd。

 how do you print out percent S， there's a solution to that too if you literally ever want to print out percent S but it's deliberately a weird choice of characters so that the probability that we ever need to type this ourselves is just low that no one really worries too much about it All right but that's not quite enough in addition to saying hello comma space placeholder。

 percent S and just for vocabularys sake that's a format code again， format being the F in printf。

 I still need my double quotes around the whole thing。😡。



![](img/9b3478adcf58801ce6a8c57047480262_39.png)

this case， to match my previous program， I am going to go ahead and add the backslash n to move the cursor to the next line。

😡，And now I've left a crazy amount of room here， but that's deliberate。

 Does anyone have an instinct for what I'm probably going to want to add after the quotes。

But still inside of the parentheses。So answer itself。

 I need to somehow tell printf with a second input otherwise known as an argument what I want to substitute for that percent S and so I put a comma and then the name of the variable that I want printf to figure out how to plug in here so honestly it's a little annoying and this is kind of a dated approach like newer more modern languages like we'll see later in the course Python in JavaScript actually have much more user- friendlyly ways of doing it。

 but once you wrap your mind around the heuristics， the rules here。

 it's just formatting a string by plugging in whatever you want into this format string so to speak and Ken the comma here is important。

 this signifies that it takes one input at left and a second input at right but notice this comma there's technically two commas but I'm not claiming that this function takes three inputs。

😡，Why this comm I'm pointing out doesn't mean the same。😡，Votation marks and。

Exactly this comma that I'm pointing to is part of the quotation marks and therefore part of my string of English text。

 so this is just English grammar， this is sort of C syntax and again these are the sort of knowing little details that we're using different the same symbol for different things but context matter so just stare at your code look carefully left to right and generally the answer will pop out nope pun intended okay questions now on this syntax before we actually write it and run it yeah。

😡，Why is the backslash n not after the answer so the way functions work including printf is that you pass to them one argument inside of the parentheses and then if you have a second argument you put it after this comma here。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_41.png)

But the way Prif works is that its first argument is always a string that you want to be formatted for you。

 So anything you want printed on the screen has to go in those quotes。

And you can perhaps extrapolate from this if I actually wanted to say multiple things in this sentence。

 so hello， maybe first name， last name， I could actually do hello comma， percent S， space， percent S。

 if I had two variables， one called first name， one called last name。

 but then I would need another comma for a third input to the function。

 and so it's very general purpose in that sense。😡。

![](img/9b3478adcf58801ce6a8c57047480262_43.png)

Questions， yeah。Okay so can you abstract away the format string itself， hello comma answer。

 short answer yes， but not nearly as easily and C as you can in other languages so that's why we're keeping it simple for now。

 but you're going to love something like Python or JavaScript where a lot of this complexity goes away。

 but you'll see also in Python in JavaScript and other languages。

 they still are inspired by syntax like this， so just understanding it now will be useful for multiple languages down the line。

😡，All right so let's actually do something with this code rather than just talk about what it might be doing for us。

 let me go over to， for instance， VS code again， and I'm going to go ahead now and remove this middle line of print F I'm still in my same file called hello C I'm going clear my terminal window just to eliminate distraction and to do that I can literally type clear but this is just for aesthetic sake that's not functionally that useful or you can hit control L to achieve the same on your keyboard。

 but I'm going to go back to line 5 here where I previously just said hello comma world。

 and I'm going to do this instead， I I'm going to give myself a variable called string sorry I'm going to give myself a variable called answer the type of which is string I'm going to set it equal to whatever the return value is of get string asking an English question what's your name question mark with just a single space just to move the cursor over followed by a semicolon then I'm going to go ahead and say print F quote unquote。

😡，Hello， comma placeholder， backslash N， close quote。😡，Coma， and then what goes here again？😡。

This is where answer goes and then I need to semicolon on the right of that。

 but I think now that I'm done， but let me point out a couple of details。

 this got very colorful very pretty quickly and it's not like the black and white code I had on the screen a moment ago This is because what programs like Vs code do for us is it pretty print rather syntax highlights our code for us So syntax highlighting means just add some colors to the code so that different ideas pop out so you'll notice for instance that printf here get string here or in purple because they represent functions just like the save block here what's your name quote unquote in Vs code is a light blue instead of white。

 but it's still gonna to be consistent if I use strings of text elsewhere as well so I didn't type anything special this isn't like Microsoft word or Google Docs where I'm highlighting and changing colors of things this is all happening automatically but it's just uncode text it's just being interpreted automatically and having these colors applied so that things pop out more usefully visually。

Now I've unfortunately made a mistake but I'm going to deliberately induce this one because you too will probably make this mistake。

 I'm gonna to go ahead and run make hello again because I've changed my code。

 so I have to regenerate the machine code from the new source code but unfortunately when I hit enter now My the errors don't even fit on the screen。

 So let me make this bigger。 I'm gonna click the little carrot symbol here just to make my terminal bigger for just a moment。

 and you'll see that there's like more lines of errors than there are of code that I actually wrote often which is written pretty arcanely again for programmers who've been writing code for 1020 years。

 but there are some details that pop out。 so notice the problem is definitely with hello do C So great it is my fault。

 this syntax here means that line 5 is the problem and this next five means character 5。

 So you can literally like triangulate your bug your mistake by going to line 5 and then over 5 and it's somewhere in that area。

 specifically the area is use of undeclared identifier string。 did you mean standard in。😡。

I don't think I did， like I do want string and then there's some other complexity here。😡。

But what's important here is not the specifics of this error。

 but really the implication that it doesn't recognize the word string or get string。😡，Now。

 why might this be， yeah？😡，Exactly because we are using get string。

 which I claim is the CS 50 thing that we' use for a few weeks。

 C does not know about it out of the box so to speak I have to teach the compiler that get string exists just like I taught the compiler that printf exists by including the appropriate header file and in this case。

 quite simply it's called include CS 50 do H that now teaches the compiler oh someone else wrote this function already get string and with it this type of variable called string so now if I go back to my terminal window and rerun the exact same command may hello maybe crossing my fingers now nothing in fact goes wrong because the compiler' has been brought up to speed with all of the functionality it needs。

 and now if I do dot slash hello enter there it is。

 what's my name and notice the cursor's one space over just because I thought that'd look prettier then having the cursor right next to the question mark D VId as my input and enter and hello comma David。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_45.png)

My questions on any of this code thus far。Questions。Any of the code。No， all right。

 so let's introduce some other functionality into the mix。

 It turns out that there are other types of data， other types of variables in the world。

 not just strings， but indeed per before we have things called integers， int for short。

 floating point values float for short and a few others as well so rather than only focus on string。

 let's get a little more interesting with numbers here and see what we can do with something like integers again int for short。

 by taking a look at not get string as before， but now how about get int and for this。

 I'm gonna give us a few other tools in our toolkit， those format codes to which I alluded earlier。

 like percent S fortunately are pretty straightforward and here is a list of most of the popular format codes that you might ever care about with printf in particular we saw percent S for string and you can perhaps guess which one we're going use for integers。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_47.png)

Yeah so percent I is what we're going to use for integers and this is the kind of thing that you can consult in the manual pages or a slide like this。

 there's only a few of them that you might frequently use。

 but let's go ahead and use integers in a more interesting context not just using functions but let's revisit this idea of conditionals and conditionals in scratch we like these proverbial forks in the road like do you want to do this thing or this thing or this other thing it's a way of making decisions in a program which is going to be super useful and pretty much omnipresent in any problems that we try to solve so let me give you a few more building blocks in C by doing the side by side comparison again so here in scratch is how we might say if two variables X and y are one is less than the other then go ahead and say quote unquote x is less than y so kind of a stupid program but just to show you the basic syntax for scratch this is how you would ask the question if x is less than y then say this so say is the function if is the conditional and the green thing here we called what？

😡。

![](img/9b3478adcf58801ce6a8c57047480262_49.png)

What do we call it， yeah。A boolean or a boolean expression。

 which is just a fancy way of saying a question whose answer is true or false， yes or no，1 or0。

 however you want to think about it in C the code is going to look like this。

 so to take a little bit of muscle memory to develop， but you're going to say if then in parentheses。

 you're going to say x less than y assuming x and y are variables。

 you're then going to use these curly braces and then if you want to say quote unquote x is less than y in C what function should we use here。

😡，Presumably。So printf so printf quote unquote X is less than y so it's a bit of a mouthful but again notice the pattern name of the function is printf in the parentheses left and right is the argument to printf which is quote unquote X is less than y and again just for aesthetics to move the cursor to the next line which you don't have to worry about in scratch because everything's in speech bubbles we're adding a backslash n as well so notice that these curly braces as they're called much like the orange puzzle piece here are kind of like hugging the code like this and I'll note that technically speaking in C if you only have one line of code inside of your conditional you can actually omit the curly braces altogether and the code will still work if you have one single line of code Y just saves people some keystrokes if you have two lines three lines or more in there you need the curly braces but I'll always draw it with the curly braces in class so it resemble scratch as closely as possible as an aside too some of you who have programmed before you might be cringing now because like you really like your curly brace。

😡，Be over here instead of here， like that too is a stylistic choice and we'll talk too about this in the class aesthetically。

 stylistically there's certain decisions we can make， but generally in a class， in a company。

 you as an student or an employee would simply standardize on one set of rules so to speak。

 so we'll use these rules for formatting our code in class consistently。😡，All right。

 any questions on this snippet of C code？😡，All right。

 a couple of others then so here is how in scratch we might have a two way fork in the road if x is less than y。

 say x is less than y else， say x is not less than y in C it's going to look pretty much the same but notice I'm adding an else's keyword here with another set of curly braces I'm going have a couple of more printfs but in C even though it's clearly keyboard based it's just text no more puzzle pieces it's kind of the same shape so to speak and it's definitely the same idea so it's following a pattern what about a threeway fork in the road if x is less than y then say x is less than y else if x is greater than y。

 say x is greater than y else if x equals y then say x is equal to y well you can probably see where this is going on the right-hand side。

 it looks almost the same In fact if I add in the printfs， it's really almost the same。😡。

At least logically， but there is one。At least one curiosity。😡，Seemingly a typo。

 but it's not this time， yeah。😡，Yeah， the double equal signs does not match scratch。

 but it's not in fact a bug or mistake in C。 Anyone have an intuition for why I did use two equal signs instead of one here。

Exact well otherwise it would be a mistaken for a variable specifically assignment of a variable so recall that in previous code when we used the get string function。

 we used an equal sign to assign from right to left the value of a variable and that's a reasonable decision equal kind of means that the two should ultimately be equal even though you think about it from going right to left unfortunately the authors of C kind of patent themselves into a corner and presumably decades go when they realized oh shoot we've already used a single equal sign how do we represent equality of two values。

 the answer they came up with was we'll just use two instead and thus was born this decision is it the best one who knows crazy enough in other languages like JavaScript you have not just one but two but also three equal signs in a row to solve yet another problem so reasonable people will disagree as to how good or bad these decisions are but in C this is what you must do。

😡，But there's an。Bad design decision here too。 it's still correct the code left and right。

 but I bet I could critique the quality of the design of both the scratch code and the C code for reasons what？

😡，Okay no in really good intuition do we have to ask this third question else if x equals y so short answer no logically just based on arithmetic either x is less than y or x is greater than y or what's the only other possible answer。

 they must be equal logically so technically you're just kind of wasting the computer's time by asking this question because it already knows at that point the answer and you're wasting your time as the programmer bothering to type out more code or more puzzle pieces than you need because logically one stems from the other so I can tighten this up get rid of the elses if just using else。

 and I can do the same thing over here and C there by avoiding the double equal sign altogether but not because it's wrong but because you're wasting time because now you're potentially asking only two questions。

 two Boolean expressions instead of 50% more by asking a total of three questions at most Other questions then on this kind of code。

😡，Logly or otherwise。All right， so if we have these puzzle pieces so to speak at our disposal how can we go about actually using these。

 we'll suppose that we actually want to do something with values。

 let's introduce variables and C as well we saw an example using a string a moment ago but what about with something like integers well you might not have used this in scratch but here's the orange puzzle piece in scratch via which you can create a variable called counter to count things and you can set it equal to some value like zero now you can perhaps guess where we're going with this if I want in C a variable called counter and I want to set it equal to zero I use a single equal sign because logically you read it from right to left or technically it's executed from right to left but that's not enough and see what's missing from the screen。

😡，I need a what？So we need a data type。 and if it's going to be an integer， Indeed。

 I'm going to use int。 And now the other mistake I keep making is。😡。

So a semicolon at the end of the line， so it's a little more verbose than some languages。

 but if you read it left to right， this is how you tell C to give you a variable called counter of type int and initialize it to a value of zero that's all all right how about in scratch if you want to change that variable by one by adding one to it in scratch it's super simple you just change it by one or even negative one if you want to go up or down respectively in C turns out you have a few different ways to do this and this looks like it's not mathematically possible but that's because equals his assignment recall so this line of code is not saying that counter equals counter plus1 because that's just not possible using typical numbers but this means take counters value。

 add one to it and assign it back to the counter variable so it's like incrementing counter in this way but this is such a common thing in C and in programming to increase or decrease the values of variables there's a more succinct syntax。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_51.png)

![](img/9b3478adcf58801ce6a8c57047480262_52.png)

This is identical and it might take a little practice to get used to it but it just saves you some keystrokes。

 but it similarly adds one or whatever number you use there and this is such a common operation in C especially that there's an even tighter way of executing the same idea and you can literally just say counter plus plus and then semicolon in this case。

 all three are exactly the same all three are perfectly correct。

 but you'll learn over time that typing less on the screen is probably going save you some time meanwhile。

 if we wanted to do the opposite and do something like minus1 in scratch。

 we could similarly do minus minus in C or we could do yeah we could do minus minus in C here at right All right so just some additional building blocks translating from scratch to C。

 why don't we go ahead and try using this perhaps in the following way。

 let me go ahead and go back to VS code and let me propose that we do something like this。😡。



![](img/9b3478adcf58801ce6a8c57047480262_54.png)

In VS code， I'm gonna to go ahead and clear my terminal window。

 I'm gonna close hello do C by just clicking the X。

 I'm gonna go ahead and create a new file called compare do c because my the purpose in life of this program is going be to compare integers on the screen this time I'm not gonna mess up。

 I'm gonna preemptively include Cs 50 H I'm going preemptively include standard Io do H and here too is a very common mistake in learning C。

 it is not studio do H。 So when you email us asking why studio H is not working because that is not the word it is standard Io do H meaning standard input and output stuff involving the screen in the keyboard then I'm going go ahead and just as before main void but we'll come back to that eventually as to what it means And now inside of main。

 which is just where the main part of my program goes again。

 you can think of this as being analogous to when green flag clicked this just kicks everything off。

 I'm going go ahead and do two things。 I'm going go ahead and get in integer called X。 and I'm gonna。

The user for that int and just say something like what's x question mark space。

 Then I'm going to do int y equals get int quote unquote what's y question mark space。

 and then let's just do something simple like if X is less than y then go ahead and print out quote unquote X is less than y backlash and close quote semicolon So it's not a very deep program it's just gonna to do what most any human brain could do pretty quickly。

 but it's at least demonstrating how we might use now something like a conditional in code。

 So let me go ahead and let me compile this code for the first time make compare enter nothing bad happens。

 which is good dot slash compare is how I run the program and just to tease this apart。

 dot as we'll soon see essentially means that the file is in your current folder。

 So dot means in your current folder and will eventually see that dot dot means your parent folder like the one that's contains wherever I am on my computer's hard drive。

All right， dot slash compareare， what's x1？😡，2 for y and hopefully it should say that x is less than y。

 so pretty straightforward proof by example and hopefully this would work in other cases too。

 but if I flip that around and I rerun it dot slash compareare and I do two and1。😡。

Nothing's going to happen， but you would expect that because there's only one Boolean expression just deciding whether or not I should actually type this out So what's going on well。

 if this helps you， you might find it useful to think about the logic of any program be it in scratch or C is kind of a flow chart of sorts and we'll put up a few of these over time just in case you're a particularly visual thinker and this represents what it is I just did so here in this picture is where the program starts conceptually and anytime you see a diamond think of that as a Boolean expression a question that's being asked and the question being asked is is x less than y that has two possible answers true or false yes or no respectively so let me propose per the arrow that if the answer is true then print out per this rectangle X is less than y just quote unquote and then stop that's it for the program but logically if x is not less than y that is that question's answer is false we'll just skip right to the end and stop so this is a control flow diagram it's just a pictorial way。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_56.png)

![](img/9b3478adcf58801ce6a8c57047480262_57.png)

You could write on a piece of paper that just represents what it is the program is doing and this gets a little more interesting if now we do something else with the code。

 for instance， instead of just concluding that it's less than x less than one or the other。

 let's go back to the code here， let me clear my terminal window and let me add an else。

 So else go ahead and print out。😡，X， I don't think I want to say this greater than y。😡。

It's not quite right， what would be reasonable to say here？😡，Yeah， subtle。

 but x is not less than y because it could be equal。

 We don't know if we're only checking two scenarios here。 So if I recompile this。

 make compare dot slash compare。 Now， if I do one comma 2， I still get the same answer。

 if I rerun dot slash compare2 comma 1。😡，I now get the opposite answer。

 It's not as good as might be ideal。 It'd be nice to know if it's equal to or greater than。

 but at least that's all of the code that we have here。 And just to now paint a picture。

 if I go back to my control flow diagram， my flow chart here， this is what it looked like before。

 logically， now that I've added in a second a second branch so to speak， now， if the answer is false。

 I first print out X is not less than y。 and then I stop the program。 So same idea。

 but the decision tree， if you will， if you've taken an X 10 or the like is getting a little bit bigger now conceptually。

 All right， what if we do something more than this， let's actually have that third condition。

 let me go back into my code here。I'm going hide the terminal window just to make room for more code。

 and I'm gonna gonna say else if x is greater than y， then go ahead and say not x is not less than y。

 but rather x is greater than y。 And then down here， I'll do an else if x equals equals y。

 then I can go ahead and say print f X is equal to y back slash n。 close quote。 All right。

 so now if I run it。 let me open my terminal window again。 let me rerun， make compare。

 Let me rerun dot slash compare1 and 2 are the same。😊，Let me rerun it， two and one are the same。😡。

Let me rerun it a third time one and one are now in fact equal。

 so this works correctly but why did I make a point of using these elsets ifs， put another way。

 could't I just make my life a little simpler and just say if this then that。

 if this then that if this than that， just ask all three questions， keep the code simple。

 don't boggler with these elses。😡。

![](img/9b3478adcf58801ce6a8c57047480262_59.png)

Would this work for me， yeah？Yeah， so it saves a little bit of time because in this case。

 just like in English， this is like asking three separate questions and it's not harnessing any information from previous questions in order to decide whether you should bother asking that other question。

 In other words， if x is less than y and you already figured that out because it's1 and2 respectively。

 you're going print this。 why would you waste time asking this question when it's not going to be true。

 why would you waste time asking this question when it's not going to be true。

 And so the point I wanted to make here， which is that if we visualize that particular design what the flow chart looks like is actually this and let me zoom in at the top。

 if you ask the question is x less than y。 Well， you're going to go ahead and say x less than y。

 then if you go down to the next question， you're still going to ask is x greater than Y。

 And then below that， you're still going ask is x equal equal to y。 So no matter what x and y R。

 you're asking one2 three questions all of the time。 But if we actually go in and do what we。



![](img/9b3478adcf58801ce6a8c57047480262_61.png)

![](img/9b3478adcf58801ce6a8c57047480262_62.png)

The first time where if I go back to my code and I undo this edit and add back the elses ifs and now let me go back to the flowchart。

 which I claim is bad because it's one， two， three questions。

 one or two of which might not be necessary now if I visualize what I just did the flowchar gets a little more complicated looking but it's going to be better designed more efficient y well because if I start at the top here I ask one question is x less than y if the answer is true okay I say x less than y and then boom I sort of cheat and go all the way to the end of the program and stop having asked only one question if though x is not less than y okay fine I'll ask you a second question but if the answer is true boom I print out x is greater than y and then I stop and only in a perverse case where x actually equals y which I'm going to claim is very unlikely or infrequent only then am I going ask one to three question to figure out whether or not to print something at all。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_64.png)

![](img/9b3478adcf58801ce6a8c57047480262_65.png)

So this is what we mean by distinguished between correctness of code because it's still correct。

 but this version is better designed because hopefully you're going to go down this branch or this branch rather than the longest one frequently。

😡，Any questions now？About this code or this visualization thereof。Yeah。

A perfect segue why did I bother though even asking this question。

 don't need to because when I hit this button hopefully I have the right slide in place this would be even better than that design so thank you for teeing that up。

 this is the same picture it sort of got bigger because there's fewer nodes。

 fewer shapes in the picture notice that if x less than y boom we say as much and we stop if x is not less than y but it's greater than y boom we stop or if it's not greater than we immediately conclude x indeed is equal to y and again we stop so this picture is about as efficient and as well designed as we can make our logic that's about as good as we can solve this problem so if I go back to my code now to make my C code match that the only thing I need to do is stop wasting the computers time don't ask that third question just logically mathematically conclude that of course it's going to be equal at that point in the story。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_67.png)

All right， any other questions on it？Sorry， a little louder。

Really good question what if I put in something that's not a number so here too is where the CS50 library and the implementation of getint will be your friend so for instance if I run do s compareare and I want to compare cats and dogs I could type in cats enter it's just going to prompt me again and again it's not going let me type in dogs either it's going to force me to give it in integer C does not do that by default and in fact we'll soon see over the course of CS50 C is actually a very dangerous language at the end of the day because it just trusts that the human is doing what it wants and as such a lot of today's software that is hacked in some ways if it's using C or another language called C+ plus are actually very vulnerable to certain types of hacking whereas other languages that we'll get to in the class or less so for reasons like this。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_69.png)

All right so besides this， let's consider just one other data type how about so besides strings besides chas。

 there's some others on this list here beside strings besides integers there's this other data type here in C known as a char for a single character so here let me just tease this apart a string is indeed a string of text it is zero or more characters together a char is always precisely one character not all languages bother distinguishing between like a single character and a string of characters but in C a string is typically multiple characters but technically could be zero coincidentally it could be one but it's capable of being more but a char is literally as the word implies a single character All right given that notice that in the CS50 library besides get string besides get int we also have get cha so another handy function for just getting a single character from the user now why would it be useful to get a single character from the user well what if you're just doing something that you and I do。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_71.png)

Prety frequently when you install a new software or fill out some form。

 you agree to some form of terms and conditions。 So in fact。

 let me go back over to VS code here and let me propose that I create a new program called agree dot C。

 So something akin to asking for the user' agreement。 So in VS code。

 I'm gonna type code agree do C and I'm gonna do some quick boilerplate。

 So include C 50 do H includes standard I O do H int main void and then inside of main。

 which is like the green flag clicked， I'm going do this go ahead and get a character from the user and ask them something simple like do you agree expecting a yes no response。

 But at the beginning of this line， I need to put the return value somewhere。

 So I'm gonna to put it in a variable called C and in programming if you're just getting a single value。

 It's okay， sometimes to use X and y or C when you're using larger programs you'll benefit from using actual words like answer like we did from the get go。

But C has to be a specific type。 So I'm going to literally say char。

 And then I'm going to finish my thought with a semicolon。

 And here's now how I could check if the user agrees or not。

 I could do something like this if the value of C equals equals quote unquote lowercase Y。

 then go ahead and print out agreed backslash n。Else if the variable C has a value equal to lowercase n。

 let's go ahead and print out， say not agreed， as though I'm agreeing or not to some terms and conditions。

 but notice these are not typos， what did I do ever so subtly different from last time I used text。😡。

Yeah。Single quotes instead of double quotes。 So here's the heuristic when using strings。

 which are generally multiple characters， have to use double quotes。 When using a single character。

 you should use single quotes around the single character。 So let me go ahead now and make agree。😡。

Nothing went wrong， which is good。 Dot slash agree。 En。 and let me go ahead and type in why for yes。

 It seems to work。 Let me run it again。 dot slash agree n for no， And it seems to work。

 And just if I type in something random like question mark， I don't know。 It doesn't crash。

 It just ignores me because I only had two bullolean expressions there。

 But notice that it's actually a little buggy arguably， let me run it again， dot slash agree， enter。

 how about capital Y， because like my caps lock is down。 Okay， it just ignores me。

 Let me do it again， dot slash agree capital n because oops because my caps lock is down， Okay。

 it just ignores me， But this should make sense because I'm literally checking for lowercase。

 So how could I fix this。How could I fix this？Without just changing lowercase to uppercase because that would then break it in the other direction。

 yeah。😡，Yeah， let's just add another branch here so to speak。

 So if variable C equals equals capital Y， then I can go ahead here and say printf agreed。

 and then let me close my terminal to make more room。

 otherwise down here else if C equals equals capital n。

 let's go ahead and again say printf not agreed。 and I claim that this would actually now work。

 it's four way fork in the road。 But I'm at least checking for lowercase， uppercase， lowercase。

 uppercase for y and n respectively。 I claim that this is correct。 but this too。

 even if you've never programmed before should start today to rub you the wrong way like。😡。

We can do better。 This isn't the best design。 Why might that be， yeah。

ACl so could we change the variable C to just be forced to uppercase or maybe forced to lowercase。

 no matter what the human types， we just do that ourselves so that way we can just simplify this again to two possible scenarios I love that。

 but we haven't seen any functions yet in C that would let me change things to uppercase or lowercase so we'll get there but a good instinct and correct other thoughts。

😡，So we could use or in some sense， like a logical or like what I don't like about this to be clear is that it's repeating itself。

 and like there's this principle in programming and in life in general。

 like don't repeat yourself unnecessarily and by that I mean I literally have the same line 10 as 14 I have the same line 18 as 22 and if anything one I literally wasted twice as much time as I needed to put another way per our discussion of scratch。

 what if I go in and just change something like I want to be more excited like agreed well I might forget to change it in the other place and let's just claim for today's purposes that that looks stupid it's a bug because I want them to be consistent so don't invite situations where you might change something in one place but not another just only write it in one place total So I like this idea of oring things together So let me go ahead and delete what I just did and just to be clear too while this is on the screen when you highlight code in VS code based on how we've configured it these dots just show you how much I've indented because in C stylistically。

😡，I generally to indent four spaces and maybe four more spaces。

 so those dots just help you count without having to manually eyeball things yourself。

 but let me delete those lines， let me delete these lines， and this is going to look a little weird。

 but the way you can or to thoughts together so to speak like or them together is you don't say or but you use two vertical bars。

 which syntactically means the English word or and you can just ask the other question if C equals quote unquote capital Y and then down here I can say or C equals equals capital n。

😡，So it adds a little more code to each of those lines。

 but it doesn't add redundancy because I've not duplicated my printf。

 I've not added more curly braces unnecessarily。 Now， as an aside。

 there's the opposite of or logically is the word and just so you've seen it I could do this。

 Ampersand ampersand in C is how you express that the thing on the left must be true and the thing on the right must be true。

 but why would this make no sense in this context of line 8。😡，Yeah， like at least to my knowledge。

 like a character can't be both lowercase and uppercase that just makes no logical sense， so indeed。

 or is what we want in this case， other questions。😡，A good question via CS50。

 H is there a way to compare strings， short answer no， but C is going to give us that capability。

 and in fact， next week， among the things we'll do is actually compare strings and if you've programmed before you'll see and see that it actually doesn't work the way that you might expect。

 that's a problem to that we will solve， but that transcends CS50 that's a question for C Other questions on this kind of logic。

😡，Just to make this real then like anytime you like click one of those eulas or like terms into conditions on a form in a piece of software。

 like odds are there is code as simple as this underneath the hood， maybe it's graphical。

 maybe it's checking for you clicking this button or maybe hitting the enter key but underneath the hood is presumably some kind of conditional checking for those kinds of outputs。

 All right， how about another building block from last time which will now translate to see namely loops。

 things that happen again and again in these two are everywhere in code So in scratch。

 here's how we might now three times super simple in C it's going to look a little weird but you will get used to this over time if you've never programmed before looks like a mouthful。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_73.png)

Okay but let's tease it apart line by line and you'll see that you won't have that reaction frequently because it's all going to start to look very similar to itself but what are we doing here in C。

 you don't have the luxury of these cute and fun puzzle pieces that just kind of do the work for you repeat three times in fact in C and programming in general。

 sometimes the work is on us to actually figure out okay how can I use functions， variables。

 conditionals and loops and implement some idea like repetition like looping and in C here's how this might work how can I go about doing something like printing meow three times well I know about variables now we're about to see loops and I've seen how I can update variables by plusing or minus like some value to them let's combine those ideas so first I'm doing what with this highlighted line in English。

😡，If a friend cared to ask you like， what is this line of code doing later today， what would you say？

😡，Good， it's creating a variable called counter and setting it equal to3。

 I'll use slightly new jargon。 I'm defining a variable would be the term of R called counter and setting it equal to3。

 so I'll use my hand to represent the counter， and that's all very boys。

 it's like storage in some case that I'm representing information using my hand in this case or the computer's memory here。

 Now what happens when using a loop in C There's a different types of loops。

 one of which is called a four loop， one of which is called a while loop spoiler a while loop works like this inside of parentheses is a boolean expression just like inside of a conditional that asks a question。

 but this time the question is going to determine do you keep going through the loop again and again and again。

 so it's not a one time thing potentially it is checked again and again and again to decide when it is time to stop looping to stop cycling。

 All right so it's asking this question first is counter greater than0。😡。

OkayObviously the answer is true because I'm still holding up three fingers so what happens C goes inside of the curly braces per the indentation and executes printup of meow which prints out a meow on the screen the next line of code executes which recall is the same as just subtracting one from counter so I think I take down one finger so I left with two and what happens next well this you just kind of have to memorize once you get to the end of the inside of a loop you go back to the beginning of a loop here and ask the same question the same boolean expression so is two greater than zero obviously so so you go into it you print a meow you go into it and decrement counter further by one so now my hand is holding up one now we wrap back around to the Boolean expression is one greater than zero obviously we print out a third meow we then decrement counter again and my hand goes to zero we go back around once more is0 greater than zero。

😡，No， and now the program just terminates or if there were more code here。

 it would just jump outside of the curly braces and keep going lower on the screen。

 so that's all that's happening and so this is what MIT has the luxury of doing with pictures but at MIT someone probably essentially wrote code that looks like this to give us the alu the abstraction of this so what we're learning today is sort of how they invented these puzzle pieces by just using lower levell plumbing if you will。

😡，Like this here。Yeah。A really good question。 What would happen if you created the variable inside of the curly braces。

 short answer， it just wouldn't work in C because if I were to try with my slide here for instance。

 to move this line of code here down inside of this for instance。

 now the very top line is trying to use counter before it even exists， so C is very literal。

 it reads top to bottom left to right and if it hasn't seen you define or create a variable yet。

 you're going to get some scary error message on the screen instead。😡。



![](img/9b3478adcf58801ce6a8c57047480262_75.png)

AllOther questions on this here code。NowAll right so if we want to then maybe tighten this up a bit。

 let me propose that we could do this instead， so besides this version of the code。

 let me just do something more canonical， more conventional。

 so you're totally fine with using a variable like counter it's what Scra uses by default it's very verse it does what it says frankly once you get comfy with programme like most typical programmers whenever they have a single integer in a program whose sole purpose in life is to count they'll just use I for integer just like I use C for character when you have larger programs you don't want to start using A and B and C and D and E and F and so forth for variables because nothing's gonna to make any sense。

 but when you're doing something super simple like counting with an integer using a shortnamed variable is totally stylistically reasonable but I can tighten this up further not just renaming counter to I what else can I do if you recall over here。

😡，Yeah哎 sure。Okay， four loop， yes， that was my spoiler， but while in the wild loop。

 I can tighten this up slightly more over here。😡，Yeah， instead of I equals I minus1。

 I can actually tighten this up this way and we didn't see the minus before， but it's the same idea。

 I minus equals1 or even more succinctly I minus minus so when you get comfortable with programming any of these approaches are correct this would be more conventional at this point so if you want to write code like most other people write code adopt ultimately these kinds of conventions all right so that just does the exact same thing though but let's now put this into practice let me go back to Vs code here。

 let me go ahead and clear my terminal and close a agree do C from before and let me go ahead and create a file called Miow so code Miow do C and let me do this the sort of wrong way let me include standardIo H at the top in main void thereafter inside of there。

 let me do printf Miow。😡。

![](img/9b3478adcf58801ce6a8c57047480262_77.png)

And then you know what， I't want to keep typing that。

 Let me just go ahead and copy paste two more times。 So I claim this is correct。

 make Miow dot slash meow done。 I've got code that prints meow three times。

 but this again should already rub you the wrong way。 why。😡，Yeah。😊，Because what？

Because I have duplication I mean， I literally copied and paste it。

 and that's kind of a good rule of thumb。 If you in the future start finding yourself copying and pasting code within the same program。

 you're probably doing something wrong。 There's a better way to design it， even if it's correct。

 So this is clearly a candidate for a loop。 So let me go ahead and actually do that。

 Let me just go ahead and remove all of this duplication。

 let me give myself a variable called I set it equal to3。

 let me go ahead and give myself a y loop and check that I is greater than zero inside of this loop。

 let me print out just meow once， but I'll reuse that code again and again。

 because here I'm gonna do I minus minus So that's the exact same code the tight version of it that we saw a moment ago let me go ahead and make meow again dot slash meow and it still works。

 Why is this version better because if you want the cat to meow five times you change it in one place。

 if you want to make the cat a dog you change the meow to a wof in one place。

 albeit changing the file name eventually。But changing it in one place。

 not worrying about changing it again and again and again。😡，But there are other ways to do this。

 for instance。

![](img/9b3478adcf58801ce6a8c57047480262_79.png)

Let me propose that。 And actually， let's see。 Let me propose that instead of just doing it this way。

 just to be clear。Yeah， let's go ahead and propose that instead of doing this。

 we can actually count in different directions right I'm kind of forcing this idea of starting at three going down to zero。

 but when normal humans in this room， if you ever count something， you probably do one，2。

3 and done like that's how we would count in the real world Well we can do that two here codewise We could initialize I to one we could check that I is less than or equal to three and we've not seen this syntax before but there's no easy way on a typical keyboard to type a less than or equal sign like in a mathbook so we use two characters a less than sign and then an equal sign back to back and that means less than or equal to and this is the same idea so long as I plus plus I inside of it because that'll start at one then two but it won't stop then it will go up to until I is equal to three once I becomes four then that Boolean expression isn't going to be true so it stops after three meos total but there's another way too and this is probably the most conventional and the way you should。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_81.png)

Do it， even though it's just as correct in CSs if you've seen already last week。

 we almost always start counting from zero why like just because so we're not wasting a pattern of bits。

 so generally when you start writing code that counts。

 you should quote unquote almost always start at zero。

 count up to but not through the total you care about so you don't get one extra by accident and so this would be the most conventional way of doing what we just described。

 but they're all correct， you can make an argument that all of them are equally good。

 this is what most people quote unquote would do。😡。



![](img/9b3478adcf58801ce6a8c57047480262_83.png)

Okay， other questions。On this here。Syntax or logic。😡，No， all right， how about？😮。

We got some cookies on the horizon， but before we get there， let's me out a few more times if we may。

 So how about doing a little bit differently versus the while loop。

 and I think we heard it over here， turns out there's another type of loop altogether So this one here and this one if you can believe it is probably even more conventional than the other way and this is gonna to be thematic and programming like there's rarely one way。

 one right way to do things， you're gonna to have bunches of different tools in your toolkit and your code might look different from someone else's because each of you tends to reach for a different tool in that toolkit and here's another tool and as you proposed earlier。

 a for loop。 a for loop is just another way of achieving the exact same idea using slightly different syntax and it's appealing frankly in general。

 because it's a little more succinct it just saves some keystrokes even though you have to memorize the order in which it works This code is identical to this code here functionally but aesthetically of course it looks different How does it work。

😡，In a four loop notice that in the parentheses is not a single simple boolean expression。

 there are three things one before semicolon is a place to initialize a variable to do your counting typically second is the boolean expression so it's still there it's just surrounded on the left and the right by two other things Lastly is the update what do you want to do at the end of every loop through this block of code so you can probably imagine where we're going with this。

 how does this work The first thing that happens is that a variable called I is defined and initialized to the value of0 that happens once and only once then we check the condition is0 less than three。

😡，Obviously yes， so now we don't do the plus plus yet。

 we go into the loop and this is where the for loops a little confusing at first we print out meow。

 then what happens there's no more lines so we go back to the for loop and we increment I at that point。

 so now I is1。😡，Then we check the condition I is less than three yes because one is less than3。

 we go back into the loop and print meow now we go back to the plus plus so I is now two。

 we check the condition2 is less than 3 obviously so we go back into the loop and print meow then we do the increment I is now three is three less than three。

😡，No， so we exit the loop and we're done or we keep going down here if there's more code。

 but how many times did I say meow， like1， two，3， total when my hand was0，1， and2？😡。

Questions on this alternative syntax， it takes some getting used to。

 but most people would write loops using a for loop， I would say。😡，Yes。

 if you really want to be cool and save syntax， yes。

 it is correct and common to eliminate the curly braces。 If you only have one line of code therein。

 we in class will always put the curly braces there because this is the kind of thing where if you get forgetful。

 you go in later and add a second line like darn it， like you forgot the curly braces。

 things will not work as expected。 So in general， use the curly braces。

 but you do not have to strictly。😡。

![](img/9b3478adcf58801ce6a8c57047480262_85.png)

![](img/9b3478adcf58801ce6a8c57047480262_86.png)

Other questions。😡，On six， yes。Can' it be used without what？😡。

Oh could you do it without the condition Yes， there are very fancy things you can do that we won't focus on today。

 but yes， if you want to get rid of the condition， you could get rid of this here。

 and that would actually make the loop go forever， which may be a good thing if it's like a clock that you want to tick forever。

 but often not a good thing in code， good question though。😡。



![](img/9b3478adcf58801ce6a8c57047480262_88.png)

![](img/9b3478adcf58801ce6a8c57047480262_89.png)

All right so beyond that， let's just go ahead and put this into context just in case it helps you to think about this。

 this is just another flowchar if you're more of a visual thinker that represents what it is this loop is now doing previously all of our arrows went from top to bottom and stopped but now there's an arrow going back up and around because of this loop this cycle So when we start this program we said I equal to zero we then check is I less than3 obviously it is so we print meow。

 we increment I and then we go back to that same condition we check the condition we print meow I plus plus go back go back now if I equals 33 is not less than three so the answer is false and we stop so again it's just another way of thinking about how the code in scratch how the code in C might alternatively work in each of these context。

 but there's this one other puzzle piece in scratch recall that's not the repeat block。

 which is for finite numbers of repetitions。😡。

![](img/9b3478adcf58801ce6a8c57047480262_91.png)

![](img/9b3478adcf58801ce6a8c57047480262_92.png)

And in C， there is a way to do this， but it's a little weird looking。

 There's no forever keyword but you can use the while loop or as you induced infer you can actually use the for loop without a condition in the middle so here I can actually say this if I want to do something forever I want to make sure that the answer to my question。

 the Boolean expression it was always true， always true， always true。

 the easiest way to achieve that goal is just like literally right true there because true is true。

 no matter what， and it's a trick for making the loop forever go around and around as you might if you want the cat to live forever and meow incessantly or if it is a clock that you want to tick forever or the like so here for instance。

 is how we might have a cat meow endlessly using this so-called for loop instead but recall that in scratch we also had this ability to create some of our own puzzle pieces and this too is something that we're gonna be able to do here in C and let me propose that we do exactly。

ly that。By introducing the C analog of this。 So here， for instance， is。In scratch。

 our definition of a function called Miow whose sole purpose in life was to just play the sound Miow until it's done。

 This is gonna look a little weird at first， but you'll notice some similarities with main。

 So recall the thing I keep typing with main in main void in main void that's just the when green flag clicked equivalent for today。

 But if you want to create your own puzzle piece or your own function in C。 you for now。

 literally do this。 you say void the name of the function you want to create and then void in parentheses。

 And technically what this means is that this function has no return value。

 It doesn't hand you anything back like get string or get int and the void in parentheses mean it takes no inputs。

 It's only meow， you don't have to tell it how to meow it's just going to meow。 So no arguments。

 so to speak。

![](img/9b3478adcf58801ce6a8c57047480262_94.png)

This literally just prints out meow， but what this does for me is it abstracts away the idea of Maing。

 I don't know you need to know how to use printf or that you're using printf to make the cap meow。

 I now have a function in life called Miow， because in scratch recall I used it like this when the green flag is clicked I could repeat three times this new custom puzzle piece but in C I could now do this in my main program I can use a for loop just like we saw a moment ago。

 copy pastted from earlier， but now I can call my own C function called Miow。😡。



![](img/9b3478adcf58801ce6a8c57047480262_96.png)

And let me go ahead now and do this if I go over to my C code here。😡，Back in VS code。

 let me go ahead and delete everything inside main。

 Let me go ahead and do four int I equals0 I is less than3 i plus plus inside of my curly braces。

 let me go ahead and say Miow， but I now need this meow function to exist because if I do make meow again notice error implicit declaration of function Miow is invalid in C 99。

 the 1999 version of C What does that mean Well it doesn't know what the the meow function is and the meow function is not in cs50 dot H it's not in standard Io dot H。

 I have to create it so let me type out or really copy paste what I had on the screen a moment ago。

 void me meow void Miow void printf quote unquote meow。😡，Close quote， semicolon。But here too。

 let me scooch this down a bit so you can see all the code at once。

 let me now do make Miow and unfortunately I still have an error if I scroll up still on line 7 of Miow。

 C my compiler thinks that Miow does isn't valid that it does not exist this too is a common mistake and as simple as this code might be in spirit。

 where did I screw up。😡。

![](img/9b3478adcf58801ce6a8c57047480262_98.png)

Yeah， in the middle。你没认的还。Yeah， I need to define the function before I use it。

 so again C is going take you literally if you try to call Miow On line 7。

 you better not define it on line 11， you better define it higher up so the simplest fix is going to be just to do this let me clear my terminal let me highlight and just delete the Miow function and let me just paste it up here and this will actually solve the problem。

 make meow now works and if I do dot meow that too works but this isn't really the best solution because if your solution is constantly oh we'll just put it up there。

 put it up there， put it up there I bet we could contrive a situation where one function needs to be above the other but it needs to be above the and it's just not going work in general and more importantly it just pushes main lower and lower and lower in your file but the whole point of your main function is like that's the entry point like that is what happens when the green flag is clicked and so just in terms of user conventions it's just useful for main to always be at the top of a file because then you can find it fast your friends can your TF。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_100.png)

![](img/9b3478adcf58801ce6a8c57047480262_101.png)

Can find it quickly if it's at the top。 So the other solution here would be to leave me out at the bottom and leave main at the top。

 But this is the only time if I may that copy paste is okay。

 What I've highlighted here in line 11 is what's called the function prototype。

 It is enough information to give you the return type。

 the name of the function and the return value and any arguments。And so if you just copy。

 paste that one line and end it with a semicolon up there。😡。

That's enough of a hint to the compiler that okay it doesn't exist yet。

 but it will and it will look like that。 That's the only time it's okay to copy paste the very first line of a function you've written to the top of the file with a semicolon so that you can makeang you can make the compiler happy so if I do make meow now。

 still no errors dot s meow and it now works。😡。

![](img/9b3478adcf58801ce6a8c57047480262_103.png)

But let me add one final feature coming back to scratch here。 and then it's time for snack。

 So here recall was sort of the last fancy thing we did in Sc where we created not only our own custom puzzle piece。

 but it took an input so that we didn't need to keep using the loop ourselveslf。

 we could just let the me function be told how many times do you want the cat to meow。 So in C。

 we don't have to make that many changes except this。

 we change the prototype to take an argument inside of parentheses。 and this is the syntax for that。

 if you want your own function in C to take one or more argument。

 you give the argument a name n or whatever you want to call it。

 but you have to tell C what the type of that input is。

 So it's an int n So it knows it's a number and then you can just use n in your program So instead of hard coding typing manually。

 the number three， I'm just using n here。 So this is equivalent to what I did with scratch by just dragging and dropping the n variable there。

 and then nowow we'll get printed that many times。

![](img/9b3478adcf58801ce6a8c57047480262_105.png)

If I want to then use this， notice this is the last version of the cat that we did last week。

 you just say Miow this many times。 So in C this is where now the code gets very succinct because all the main part of the program does is Miow three times。

 so this again is an abstraction。 I don't need to know care or remember how Mio is implemented。

 I just need to know what its return value， its name and any arguments there too are So if I make this change。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_107.png)

I think we can get the cat to meow any number of times。 Let me go back over to my C code here。

 Let me go back into the file and change void here to be int n where n just means number I could use I but n tends to be a quantity instead of a counter。

 I then inside of this function I'm gonna do a four loop 4 int I get0 I less than n instead of3 I plus plus and then inside of here。

 I'll paste that meow again。 I need to change my prototype to be identical。

 So another copy paste or just manually edit it but now notice what's cool about main is that now I can meow maybe three times。

😡，Make meow enter dot/ slash meow OK or if I really want to be cool， I can change this to like 30。

000 times， go back here， make meow increase the size of my terminal window for a dramatic pre break flourish。

😡，And there are that was a fast cat。 There are 30000 yaows。 I think now let's go ahead and take。

 That's a lot。 a 10 minute break。 We'll see you in 10。 cookiesies are now served outside。right。

 so we are back。 and I realize this has been a lot so far So there's a lot of new syntax。

 There's a lot of translation of scratch over to C。

 but among the goals of having spent last week in scratch and having spent problems zero in scratch is that none of today's ideas are really all that new。

 It's just a lot of syntax that will get more comfortable and more in your muscle memory as time passes up until now though we focused largely on these side effects like things happening on the screen and that was akin to like the speech bubble appearing in the world of scratch。

 but let's focus for just a bit before we then explore things we can't do very well in code return values instead in C。

 we've seen them already， like get string returns of value get returns of value of string and an inch respectively。

😊。

![](img/9b3478adcf58801ce6a8c57047480262_109.png)

What if we want to make our own functions that don't just meow and visually have this side effect of meowing on the screen but actually hand us back some value Well I bet we can do this in C as well Well let me propose that to go that routes let me go back to VS code here and let's make our very simple calculator that just like add some numbers together but the same calculator we'll soon see is going to get us into trouble if you don't understand what the computer is doing underneath the hood let me go ahead and run code of say calculator do C。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_111.png)

![](img/9b3478adcf58801ce6a8c57047480262_112.png)

And in here， let me go ahead and give myself access to the CS50 library with CS50 do H。

 the standard Io library with standard Io do H inmain void。

 which again will just take for granted today that we have to include a top any of these programs and let's just add two numbers together。

 super simple calculator So give me a variable called x assign it the return value of get int and I'll ask the user to give us X give me another variable called y。

 assign it the return value of get int again， but this time ask the user for y。

 and then lastly let's just go ahead and print out the value of x plus y。

 but I don't think I can get away with something like this x plus y semico in because if I do this based on what we've seen before what's actually going to get printed out。



![](img/9b3478adcf58801ce6a8c57047480262_114.png)

![](img/9b3478adcf58801ce6a8c57047480262_115.png)

Right literallyter like x plus y， so I think this is where I need the F in printf for formatting。

 what I think I really want to do is print out the value of some placeholder because what do I want to substitute for percent I maybe as a second argument to print F intuitively。

😡，Maybe just x plus y。 So indeed， I can get away with this because it turns out and see there's a bunch of arithmetic operators。

 all of the ones that you might expect， including addition subtraction， multiplication。

 division and even this one， so-called modular operator。

 which generally gives us the ability to calculate a remainder when you divide one number by another。

 but I'll keep it simple with addition。 and indeed with printf。

 if I want to print out the value of x plus y， I can do that。

 but I have to tell printf what kind of value to expect an integer thus the percent I instead of percent S for string。

 and I think this should do the job。 So let me go back to my terminal， make calculator。

 enter all as well so far dot slash calculator， and let's keep it simple one for x2 for y and indeed I get three as the output。

 It's not very dynamic， it can't do a subtraction or multiplication or much more。

 but it does at least do those kinds of calculations。

 but let me propose now that we maybe make a reusable addition function right。



![](img/9b3478adcf58801ce6a8c57047480262_117.png)

![](img/9b3478adcf58801ce6a8c57047480262_118.png)

Addition is something I'm going to do a lot and maybe it should be abstracted away with a function just like meowing was abstracted away a moment ago。

 so let me go ahead and instead of doing this， let me go ahead and give myself a function called add but instead of last time where I had a meow function I'm obviously going to call this add instead and instead of last time taking in no arguments I think I want addd to work a little differently I don't want add necessarily to take an argument yet but I do want add to return some type of value and just intuitively like what type of value should an addition function return。

😡，An integer， so an int， so I'm going change void， which means the absence of a return value。

 nothing's coming back to literally int， but I'm not going to change the thing inside parentheses yet。

 I'm going to go ahead and copy my prototype up here and I'm going to make this change。

 return x plus y and then here instead of printing out x plus y， let's go ahead and do this。

 let me give myself a third variable just for now Z equals the return value of this brand new addd function that's going to add x plus y for me and then let me print out the value of Z。

 instead of x plus y I'm outsourcing now to this addd function。

 so it will do the addition of x plus y。😡，So similar in spirit to Miowing， but the return values。

 I claim， are about to create an issue。 So let me make calculator again。

And there's definitely some error。 So here we have use of undeclared identifier X。

 and that's on line 17。 So that's pretty far down in the file。 So specifically。

 my compiler does not like my use of X on line 17。 But wait a minute。 X is clearly defined on line 8。

😡，What intuitively might explain this issue， even if you've never programmed before， yeah？Make words。

Yeah， because x and y are defined in the main function， not in the add function。

 so the term of R here that we're about to introduce is something called scope。

 so scope just refers to the context in which variables exist。

 the context in which variables exist so by that I mean this on line8。

 I've declared X on line y I've declared on line9 I've declared Y。

 but the catches and here's where the curly braces are helpful。😡。

Those variables only exist in the context of the outer curly braces that are nearest to them like this。

 So I can use x and y on lines 10，11，12 and even up to 13， but not thereafter。

 So I certainly can't use X down here on line 7。 But this is a problem。

 Because if add's purpose in life is to add x and y。 but a can't access x plus y。 Well。

 we have an issue of scope like x and y are not in scope for this ad function， But that's okay。

 because remember that every function we've seen thus far。

 can have maybe a return value or side effect。 but it can also take 0 or 1 or2 or more inputs known as arguments。

 So what if I instead do this， let me clear my terminal window。

 And let me update add to not take nothing as input， but maybe two integers。

 And I'll call them arbitrarily A and B。 But I have to tell the compiler what type of arguments they are to integers。

1 after the other。 And now what I can do is this。Let me change this up here to， int A。

 int B just so that the prototype is exactly the same。

 and the only purpose of this prototype is just to avoid the previous error where the compiler didn't realize ad was going to exist because it came later in the file。

😡，So here on line 11 now， if I want to add two values X and Y， this is now the syntax。

 We saw syntax in scratch we're passing in inputs to tell it to how many times to Yao。

 So this is just telling add what two numbers。😡，To add together。

 So now I have to change this to a plus B。 for reasons we'll soon see。

 And let me see if this is right。 Make calculator。 So far so good。 dot slash calculator。

 Let's do one and 2 for x and y respectively。 and hopefully， we should again， see 3。😊。

Now what's going on So here again， if I zoom in on my ad function。

 this int here on the left on line 15 means what about ad。😡。

This means that it has a return value that it's an in。 So it's gonna hand me back metaphorically。

 a slip of paper with an answer on it that is of type integer。 It's not a word like my name。

 it's a number instead。 These mentions of int here and here are inside the inside the parentheses。

 which means this function ad takes two inputs the first is an int。 the second is an int。

 and just so we have something to call them， I call them a and B respectively So what happens essentially when I call the addd function now online line 11 I'm kind of passing in X I'm passing in y but the ad function is gonna think of them as a and B respectively it could call them anything I want I could change this to the word first and second and then I could literally change this to first plus second those are perfectly acceptable as argument or variable names。

 but who really cares like A and B for such a simple function is perfectly reasonable to technically if your mind is going there。

 I could even call them the。😡，Exact same thing， but let me propose for today。

 certainly don't do that because it just confuse this thing if you've got x's and y's here。

 x' is and y' is here， but they're clearly different， just don't do that。

 Try to come up with different variables just to keep yourself sane。

 But here I have a function that takes now two integers A and B respectively。

 it just returns the sum of them so that I can now store the return value of add in a variable called Z and then quite simply。

😡，Print it out。But there's one other thing I can do here。 Now， if we think about design。😡。

Even if you've never programmed before， do I really need the variable Z？😡。

Becauseuse I'm defining it on line 11。 and then I'm quickly using it on line 12。 and that's it。

 Like sometimes you don't need variables。 And they might make your code more readable。

 but strictly speaking。 And this is just kind of like substitution in math。

 If Z is the same thing is add x comma Y。 Well， let me go ahead and just delete line 11 altogether。

 let me get rid of mention of Z。 you can actually get away with doing this。

 and much like the join block in scratch where I kind of overla it on the say block。

 like kind stacking them， you can stack functions in C or nest them really mathematically honestly it makes it a little harder to read because your mind has to kind dive in conceptually deeper and deeper into this second argument。

 But it's perfectly acceptable too。 And just to connect the dots to maybe something from high school。

 This is kind of analogous to a function in math class being like F of x where F is some function name。

 X is some arbitrary input to that function。 And when you start to put functions inside of functions。

 so that the output of one becomes the input to the next。

 it's like using this syntax F of G of x and so forth。 If you've never seen that before。😊。

OrDon't worry， but if you have， it's a way to connect some of these dots。😡。

Any questions though on just this idea of now having a function that doesn't just have a side effect。

 but instead has a return。😡，Value。

![](img/9b3478adcf58801ce6a8c57047480262_120.png)

Yeah， and back。In our， in our definition of mainine， what did I do what。Oh。

 a really good question that I was trying to sweep under the rug for today。

 but in every one of our programs thus far I have indeed said int Ma void technically speaking whenever you write a program and it finishes running。

 it actually returns a value somewhat secretly it returns the number zero by convention which means all as well and it can return any other integer if something goes wrong in fact on your Mac PC or even phone if you've ever gotten like a weird message on the screen like something went wrong and it's like a weird numeric code like error negative 129 or something arbitrary like that that tends to mean that some program running on your Mac PC or phone had something go wrong with the main function and that is the number that was returned but that's more than we want to talk about today but will come back to this。

 but Maine always returns a number by default it is zero。😡。



![](img/9b3478adcf58801ce6a8c57047480262_122.png)

More on that soon。All right so with that said， let's actually tease apart what it is we've been using underneath the hood here a little bit by returning to VS code's interface itself。

 It turns out that all this time even though I keep alluding to MacOS and Windows which like 99% of us are probably running on our laptops or desktops there's actually other very popular operating systems in the world among which is Linux so Linux is a very popular operating system。

 the thing that turns on the thing that boots up when you first turn on a computer and it's very commonly used for servers。

 nowadays all of CS5's own servers run some version of Linux those students more comfortable。

 sometimes run Linux on their own Mac or PCs even so Linux is a very popular operating system and it's particularly characterized by its textual interface。

 it's commandline interface even though it also comes with graphical ones as well So again this term we started today with the graphical user interface is a thing with menus and buttons it's literally what you and I use every day on our devices otherwise known。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_124.png)

goI but today onward you'll get more comfortable with and more practice with this terminal window down here which represents a command line interface or CLI and just so you have a mental model of what's going on in the cloud here when you access CS50 you are accessing this version of VS code in the cloud。

 a piece of software just running in a browser but that piece of software is automatically connected to your very own personal server in the cloud so to speak technically speaking it's a Docker container but it means that you have you're essentially your own mini server in the cloud that only you have access to and thatserv or container is running an operating system called Linux and in fact every time I've been running a command down here whether it's code or make or dot hello or anything else I've been running commands from here in Sanders Theat on a server somewhere in the cloud my own Linux container or server and you'll have the same yourself。

I the thing that we have preconfigured for you by installing the compiler in so many other pieces of software you'll soon see in the class。

 but underneath the hood then of Linux is soon to be familiar environment that allows you to run different types of commands and those commands include things like this and this is something you'll develop muscle memory for over time。

 but I wanted to give you a sense of some of the most popular textual commands because we're essentially about to take away muscle memory you have from a Gui worldl and have you type out words that represent double clicking on things dragging on other things and other such commands that you and I take for granted it'll be a little painful at first in the first days or weeks but it will make you far more productive longter so that even after CS50 if you start using your programming skills in some other domain class or realworld job you'll just be a lot faster at the keyboard and able to do more work more quickly So with that said。

 let me go back to VS code over here。

![](img/9b3478adcf58801ce6a8c57047480262_126.png)

![](img/9b3478adcf58801ce6a8c57047480262_127.png)

I'm gonna go ahead and open up my file Expr over here and you'll see at left all of the files that I've created thus far in class and all of the programs that I've compiled thus far in class。

 I also have this source one directory， which you can download from the course's website。

 which has all of today's code prewritten in advance。

 So you don't have to type everything that I literally type。

 But all of these files are things that I've created。

 and you'll see that in white or the C files and grayed out are actually the binary files。

 the machine code that I created that I was running。

 So you can click on any of these files in Vs code to open them for instance。

 here is hello do C andvoila， it opens in the text editor。 But if I try to open hello。

 that's not gonna work because that's zeros and ones。 And frankly。

 the computer could show me all those zeros and ones。

 but it's just not going be useful and honestly it's too easy to make one mistake and break the whole thing。

 So instead， Vs code says that it can't display the text because it's binary or maybe unsupported more generally。

 So know that。😊。

![](img/9b3478adcf58801ce6a8c57047480262_129.png)

You want to only click on the dot C files when writing C code。

 But let me go ahead and do something else。 Suppose that I decide that wait a minute。 you know。

 we're nearing the end of class。 and we're not done yet。

 but what if I want to change hello dot C to goodbye dot C。

 Or if I want to change meow do C toof dot C and turn it into a dog。 Well， let's actually do that。

 I could go over here， and right click or control click on the file just like on a Mac PC。

 I can find the rename option and I can do it all via the Gui。

 but you should get more comfortable using commands like these here。

 And among the commands on this list or M V for move aka rename。 So， for instance。

 if I want to change meow dot C to beof dot C instead。

 I literally type M V space the original file name， space and the new file name。

 So this is very similar to what I've already been doing with the code program or the make program。

 I not only type the name of the command， but also the thing that I want to code or the thing that I want to make。



![](img/9b3478adcf58801ce6a8c57047480262_131.png)

![](img/9b3478adcf58801ce6a8c57047480262_132.png)

In this case， I typed the thing that I want to move from old to new。 Now， if I hit enter in a moment。

 watch on the left hand side， Mio dot C in the GuI should automatically changed。

 even though I'm doing this all via the command line keyboard interface。😡。

And now it becomes Wolf dotsi。 right I mean it's not all that exciting。

 but this is just to say that they are one and the same。 One is a gooei。 one is a Cli。

 but it's the same exact thing。 Moreover， let me go ahead and close now the goi at left。

 the so-called Exper and in my terminal window alone now I'm kind of out of my element like wait a minute。

 what was the file I created earlier well， there's other commands as well on this list is coincidentally Ls which lists lists the file in your current folder。

 and as you might have gleaned here Mv for move Ls for list like Cs people like to be succinct terse and type the minimal number of keystrokes。

 that's why these are all abbreviated commands and instead of full words。

 but if I go back to my terminal window and type Lsvoila there is exactly the same content of my server but displayed textually and there's some curistics here in green with a asterisk is all of the programs that I made with make that are executable So the asterisk just means this is executable with dot。



![](img/9b3478adcf58801ce6a8c57047480262_134.png)

Meanwhile， the source one directory， which only I have because I download it in advance has a slash to indicate that it's a folder instead of a file。

 but all of these white files ending in dot C we created together here today。

 Now what if I really am embarrassed by my very first program hello do C Well。

 I can very destructively go and use the RM command for remove and R hellello do C is gonna prompt me a little cryptically remove regular file。

 hellello do C and amazingly， this R program has code just like we wrote earlier for agree do C where I can type y to delete it。

 I can type n not to delete it， but let's delete it let's go ahead and hit why enter Nothing seems to happen。

 but in general， that's a good thing。 But if I type L again， notice what is now missing and in fact。

 the list is a little shorter。 So it's one line instead of two hellello do C is now gone。

 Now if you do that， there are not easy ways to get the file。😊。



![](img/9b3478adcf58801ce6a8c57047480262_136.png)

Back so don't do that unless you really want to but there are backups maintained of these files as well。

 Well what else is there too， Well there's all of these other commands and you'll experience them over time like Cp is copy Mder is make directory or M is removed directory and for instance let me just show you one folder if I type Ls there's that source one folder that I claimed I downloaded in advance if you want to see what's there you can type Cd for change directory source one enter and whilea notice that your prompt has now changed and let me clear the screen just as a visual reminder of where you are you can see before the dollar sign now the name of the folder that you're inside of So in Mac windows you'd see obviously a graphical folder here you just see a little textual reminder of where you now are and if I type Ls you'll see that I wrote a crazy number of files before class and each of these represents different versions of the files that we've been coding here in real time that I usually have printout of just to go through things in series so you have copies。

😡，Online as well。 So in short， all of these commands， if you've never used them before。

 they will soon become like muscle memory and they do the most basic of operations。

 but there will be other commands that we'll see over time that do even much more than that。

 but let's go ahead now and solve some actual problems and it's no coincidence that we keep showing or alluding to Super Mario brothers in some form an older game from the Nintendo entertainment system that allows you ultimately to have this twodimensional world where Mario moves up and down and side scrolls from left to right。

 but you'll see we can dist even some aspects of Mario into some fairly representative programming problems and in fact。

 let me propose that we consider this screen from the original super Mario brothers So there's these four bricks blocks in the sky each with a question mark and if you click on one of the if you jump if Mario jumps up underneath each of these question marks he gets like a coin or something else that pops out let's distill this though into its essence and consider and see how can we make not a blue sky。

😡。

![](img/9b3478adcf58801ce6a8c57047480262_138.png)

![](img/9b3478adcf58801ce6a8c57047480262_139.png)

not a green grassy hill and so forth， but how can we just make four question marks in a row because I dare say that we do have the building blocks bio which to do this Well。

 the simplest way might be to go over here and run code of Mariio。c。😡，And then in Mario dot C。

 let's include some standard I O dot H。 So we have printf。

 Let's do int main void as we keep doing and inside of main。 let's keep it super simple，1，2，3，4。

 back slash n doesn't get much simpler than that。 This is not going be the prettiest of games。

 but if I make Mario now， dot slash Mario。 I get my four question marks in the sky。 Allright。

 so it's not all that interesting。 But this is clearly a candidate for what type of programming feature。

😊，ItNot not to scratch。 though scratch would make it more interesting。 Yeah， So some kind of loop。

 right， So print the thing out iteratively instead。 So let me do that。

 instead of just printing this out all at once， let me go ahead and remove this and do four int I get 0。

 I less than 4 I plus plus。 And then in here， let me go ahead and print out just one question mark instead。

 And now let's run this。 So make Mario to recompile it dot slash Mario。

 And does anyone not want me to hit enter yet。 why。哦は。Yeah。

 it's gonna print out a new line every time。 So notice it's four question marks。

 but they're on each on its own line。 All right， well， let me fix this。

 It's obviously because of the backslash n。 So let me remove that。

 let me rerun make Mario dot slash Mario。 And it's better in one way， but worse in another。 So wait。

 But now the dollar sign is doing that thing where it's on the same line， which just looks stupid。

 if nothing else。 So how can I fix that， Yeah。Yeah， so logically。

 we don't have that many building blocks today。 It's a lot of new syntax。

 but it's not that many new ideas。 Let's just use printf to print out literally one and only one of these backlash ends。

 but outside of the loop， So it happens after all four of those have been printed。 All right。

 let me do make Mario again dot slash Mariio。 okay now we're back in business。

 So sort of silly syntactical details， but if you reduce the problem to its essence。

 it should hopefully logically become clear over time。 All right， well。

 how about not just something that but vertical。 Well， we've done something vertical already。

 And so I imagine we could change the program to very simply print out three bricks instead of four question marks。

 But what if we consider a twodimensional world。 And later on in this game if you go underground everything looks like this with lots of bricks。

 And let me propose for the sake of discussion that this big wall here is like a three by three grid of bricks。

 So it's not just a single brick， it's like three by three or9 total。 now things get interesting。

 And let me go back to Mario。

![](img/9b3478adcf58801ce6a8c57047480262_141.png)

![](img/9b3478adcf58801ce6a8c57047480262_142.png)

See， I could kind of take the easy road out and just say， all right， Well。

 let's print out or print F about 1，2，3。 back slash n。 close quote。 And then， okay。

 let me just copy paste。 And I'm using hashes instead of the actual bricks， but aesthetically。

 it's pretty close。 Let me now go ahead and make Mario again。 dot slash Mario。

 And it doesn't quite look like a square。 but that's just because the hashes are a little taller than the R wide。

 but it is correct。😊，But not well designed。 So here， too。

 what would be better designed than just hard coding， typing literally。All of these hashes。Yeah。

Interesting two loops and y two loops instead of one。Okay， it's the right instinct。

 So one for vertical， one for horizontal。 And even though these predate。

 most of us like old school typewriters， you might know or might recall that if you feed a piece of paper into it。

 you can sort of print like line， then it scrolls line then it scrolls line than it scrolls。

 This is kind of how the terminal window works too。

 you can print rows and columns but you have to print one row at a time， one row at a time。

 one row at a time。 it's not easy， but it is possible to like go backwards and sort of go up and down。

 but just going row by row by row is more typical。 So how can I do this Well I could use at least one and maybe even indeed two loops。

 and this is where we're just now composing different ideas from today and even last week。

 So let me go ahead and say four int I gets0 I less than three for three by three grid I plus plus And now let me cheat slightly。

 let me print out just three of these here。😡，And that's it。 So I'm kind of cheating。

 I'm printing out rows dynamically， but I'm still printing three columns all in one breath。

 but let's see what happens。 Make Mario dot slash Mario。 And it does work。 But what if you said， no。

 I want4 by4 or 5 by5 or 6 by 6。 Now I have to change like the three to a 6。

 and I have to add another three hashes here， like things get messy if we don't do this mathematically。

 So let me now do this instead。 Why don't I go ahead and print out every row at a time。

 But for each row， let me use another loop to decide like rat ta from left to right。

 How many do I want to print So to do this， I could do another four loop。

 I could call this variable something different。 J is pretty common。 We started I， we go to J。

 If you go past K， maybe L， you're probably doing something wrong。 You don't want nested， nested。

 nested loops。 but two is okay。 J equals 0。 J is less than three， J plus plus And then here。

 I can print out a single one。One of these。And no new line。

 I don't want to screw up like I did before。 So I'll just do one。

 Let me go ahead and do make Mario Now。 dot slash Mario。 But when I hit enter。

 this is not correct yet。 What's it going to look like。😡，A single line of nine hashes， I think。

 because I never used a single backslash n。 so that looks wrong。

 So on what between what line number should I insert。😡，A print F， a backslash N。

 let me look a little farther back if I can have it over here。Yeah。Between 10 and 11。

 So I'm going to go in here。 I'm going to add print F quote unquote backslash and semicolon。

 Let me go back and recompile Mario， dot slash Mariio and crossing fingers。voila， perfect。

 I printed out now3 by three。 Now， it's correct。 It's not if we want to be really nitpicky。

 Maybe still not the best design。 Where am I perhaps repeating myself。Where yeah。Yeah， I mean。

 it's not a huge deal。 But now I have two people would call these magic numbers。

 Mag in the sense that where did that come from。 You just randomly put it in the middle of your code and you also put the same thing here。

 Now I have to make sure I don't screw up and make one change， but not the other。

 So it turns out we can factor these out。 I can actually do something like this。 In N equals 3。

 And then I can just change this to n and this to n。

 which is marginally better because now I only have to change n in one place。

 if I want to make this thing bigger or smaller。 It's still gonna work the same。

 So make Mario dot slash Mario， there's our three by3。 but if I want to make a5 by5。

 let me change the n to5 rerun， make Mario， dot slash Mario。 And now it's a bigger grid，5 by5。

 But this is a little fragile。 And it turns out there's another trick， we should introduce。

 It turns out that C supports what are called constant。

 whereby if you have a variable that you want to exist because it's useful。

 but you don't want to accidentally change it。 Or if you're working with a partner in class or colleague it work。

 you don't want partner or colleague。Accidentally change that value with their own code。

 You can go into your code and tell C this is actually a constant integer， a constant。 so to speak。

 And this will just prevent you or someone else from doing something stupid by accidentally changing it elsewhere。

 The code is still gonna work。 the same dot slash Mariio。

 but you won't be accidentally able to change it very easily to something else。 And honestly。

 what we've now done too is set ourselves up to make this more dynamic。 Let me go up here。

 Let me add the C50 library so that we have access to get in because now we could do something fancy like ask the get in function for the size of this brick wall。

 And then we can use n dynamically。 So， for instance， let me increase the size of my terminal。

 Make Mario dot slash Mariio。 size3 gives me a3 by3 dot slash Mario。

 size 5 gives me a5 by5 dolash Mariio。 How about 50 gives me a crazy big one。 but it's all dynamic。

 And now I don't have to even change the。😊，ode， it just now works。 as an aside。

 if you're wondering how I type so darn fast。 sometimes it's justca I'm hitting the up arrow。

 It turns out that Linux will remember if you configure it this way， all of your previous command。

 So if you hit up， up up， I can go through the past like couple of hours of commands that I've typed。

 which is useful sometimes not for hours of commands。

 But the past few just to save yourself some keystrokes and another trick in a terminal window is to do this。

 if I do dot slash M A and I get bored and I don't want to type out R I O。

 I can also just hit tab and it will autocomplete based on the characters that do match。

 So those kinds of tricks too， will save you time。😊，Over time。 But let's do this。

 it's kind of broken， aguably if I do this， how about cat， All right， Well that works。

 that prevents me from doing something stupid。 because get in only accepts integers。

 but it will accept 0， which does nothing， it will accept negative one， which does nothing。

 And that's not bad。 It's not doing something weird。

 but it would be nice to catch that and force the user to give us a positive integer instead。

 So we at least see something on the screen。 So let me go back into my code and let me propose that now that we have the C 50 library。

 why don't we do something like this。 I'm gonna change this。 I'm gonna get rid of the constant。

 just in case the user needs to type it again。 And what if I do this while n is less than one。

 So if it's0， negative1 negative2 or whatever， let's go ahead and again。

 ask the user for an int and ask them for the size again。 And therefore。

 only once n is not less than one， Will this loop break out and will proceed with。

The rest of the code。 So now let me try this。 Make Mario。Dot slash Mario0， didn't like that。

 negative 1， didn't like that。 negative 2， didn't like that。3， It did like that。 So using a loop now。

 I can sort of ensure that the human is providing me with input that I actually want。

 So this is correct， But I dare say6 through 10 could be done better。 Why is this poorly designed。😡。

Instinctively。Yeah。what's the repetition to be clear， what lines？😡，6 and 9。 like okay。

 so they're literally the same。 And that's generally not a good thing。

 And maybe I could change this one to remind the user like hey， that's not a positive number。

 So you might want to customize the message。 but just having copy paste here for the most part。

 is not a good thing。 So it turns out and there's just one feature of C。

 We want to introduce you to today。 It turns out there's one other way that will actually help us eliminate this redundancy of using get in twice and particularly asking literally the same question size twice in duplicate。

 So I'm actually going go into my code here。 and I'm going to delete the loop as we've written it thus far。

 And instead of using a while loop， I'm going introduce instead something that we typically call a do while loop。

 which is a little bit different。 indeed， we begin with the keyword do。

 And then inside of the curly braces， what I'm going to do here is that thing I might want to do once and more times thereafter。

 So for instance， I'm gonna to say n equals get underscore int quote unquote size。

 And then at the bottom of this block of code。😡，Then I'm going to use the keyword while。

 as well as parentheses as always for a Boolean expression， and here I'm going to ask the question。

 do this while n is less than1， but there's one fix I still need to do here because notice on the current line8。

 I actually haven't given n a type， I haven't declared n yet。

 but it would not be correct to declare n here inside of that do block。😡，But why might that be。

 Why would it not be a good thing to declare an inside of？😡，These curly braces。 Yeah。

 so recall that this is an issue of scope。 recall that the scope of a variable is generally confined to the most recently open curly braces in which that variable is declared。

 And so if I declare this variable on line 8， I'm not going to be able to use it on line 10。

 but there is a fix， even though it might look a little strange， I'm going go above my do block here。

 And before I go into this loop， I'm actually going to declare n to be an integer。

 but semicolon end of thought， I'm not going to bother giving it a value because I know logically。

 I'm going end up giving it a value anyway， now on line 9。

 And so it's different about this version of the code is that the do while loop ensures that we prompt the user for input at least once And then while that input is not what we expect。

 for instance， less than one then it's going execute again again， again。

 and indeed the semantics are just that do the following while this Boolean expression is true。

 So if I go ahead now and rerun make Mario compiles okay。😡，Dot slash Mario。

 and now I'll go ahead and input something that's not correct like zero， but I'm prompted again。

 I'll input something like negative one and I'm prompted again。

 but if I go ahead and input for instance， 10 now because that's a positive integer。

 I indeed get a 10 by 10 grid of bricks。😡，And there's one other thing we should introduce here to in C2 C supports comments。

 And a couple of you have asked about this。 if you come from other programming languages。

 suppose I want to remember what it is I just did with this program let me go in between lines 5 and6 here。

 and do slash prompt user for positive integer。 This is what's known as a comment and it's grayed out only in the sense that the compiler is not going to care about this。

 The computer is not going to care about this。 This is a note to self like a sticky note in the context of scratch and it starts with slash slash which essentially tells the compiler ignore this。

 This is for the human not for the computer but this comment so to speak is a way of just reminding yourself reminding your colleague reminding your TF what it is a few lines of code are meant to do and now this comment might be print and how about n by n grid of bricks。

 and what's nice about comments is that theoretically you can get away with or someone else can get away with just reading this comment and then not even have to look at。

The rest of the code， they can look at this comment and not have to look at the rest of the code because you've described for them what it's meant to do。

 yeah。是。Correct， the hash sign in Python is a comment is not the same thing in C。 In C。

 hash include means to include the library's header files in that way。

Other questions on these hair tricks。No， all right。 So as promised， what is maybe C。

 not actually good at。 Well， let me propose that we consider what's actually inside of your computer at the end of the day。

 whether it's a Mac PC iPhone， Android phone or some other computer device。

 There's something that looks like this。 And this is memory。

 otherwise known as Ram or random access memory for reasons we'll get to in a few weeks。

 But this is where data is stored。 This is where hello world is stored。

 This is where one and2 and all of those numbers are stored。

 any data in your program is stored ultimately in the computer's memory。

 And the most important takeaway for today， is that all of us only have a finite amount of memory in our device。

 you might have a highend device， which has a lot of memory， but it's still finite。

 which means you can only count so high with that device。

 you can only store so many files with that device， There are fundamental physical limitations。

 even though mathematically theoretically， we should be able to count toward infinity。

 So what are the implications for this。 Well， consider this。



![](img/9b3478adcf58801ce6a8c57047480262_144.png)

In the world of numbers as per week zero， if you're only using three digits and I've grayed out the fourth one just to make the point。

 if you're only using three digits， we can count from0 to one in decimal to2 to 3 to 4 to 5 to 6 to 7。

 and as soon as you count to 8， you technically per last week， need a fourth bit。

 but if you don't have it。😡，The number 7 might seem to be followed by what number instead。0。

 this sort of number overflows， so to speak， right you carry the one。

 But if there's no place to put the one because there's no fourth light bulb。

 if there's no fourth transistor， if there's no fourth bit， the lower bits。

 the zeros are going to be mistaken for the number you and I know is0。

 So integer overflow is a thing in computers whereby if you don't have enough memory if you count high enough。

 the number will wrap around back to0， or sometimes it will wrap around to a negative number。

 depending on whether the code supports negative and positive numbers and 0 alike。

 So that has some very real worlds implications integer overflow that sort of a fundamental limitation of how numbers are typically stored。

 Now， thankfully， we typically don't store things based on number of digits but number of bits and a bit is just a0 or one and recall from last week。

 that a common unit of measure is minimally 8 bits or a byte， but even more commonly is 32。

 So for instance， here are 32 Bs all zeros and if you do out the math。

 this is the number you and I know in decimal as， of course，0。



![](img/9b3478adcf58801ce6a8c57047480262_146.png)

Change all 32 zeros to ones。 This is a really big number。 Now， if we're only using positive numbers。

 not negatives， what number roughly is this，32 ones。It'sRough 4 billion in total。

 roughly 4 billion in total Y。 Well， if you've got 32 B， each can be two possible values，0 or1。

 That's 2 to the 32 power， which is roughly I'll stipulate 30 roughly 4 billion total。

 The problem is， what if you want to count to 4 billion and1， That's a bit of a white lie。

 It' not precisely that。 But what if you want to count just higher than that， you need a 33rd bit。

 because all of the others are going go to 0 at that point。

 And you might count from 1 to 2 to 3 to 4 billion back to 0 or worse if you're dealing with negative numbers 2。

 So the fact that there are finitely many bits used in computers is a problem。

 And negative numbers do add a complexity， because this is specifically the 4 billion in question。

4 billion，294968295， That is as high as you can count with 32 B。If you don't bother with negatives。

 but if you want negative numbers， you got to have that because you've got to save half of them for negative。

 half of them for positive give or take。 And so if you're supporting negative numbers。

 as you probably should， for a calculator for Microsoft Excel， Google spreadsheets。

 you can only count as high up as 2 billion， roughly or negative 2 billion， roughly instead。

 So it turns out that when you are using。😡，Data types in C。

 you have some control over how many bits are actually used。

 And this list is longer than we've covered today。 but we did talk about integers for a while。

 Those are by the convention nowadays 32 B。 if that's not enough。

 you can upgrade your variables too long， which tend to be 64 Bs instead。

 which isn't just twice as big as an integer， it's actually 64 B， which is exponentially more。

 it's an unpronounceable number， at least for me， that's a crazy big number。

 but it's available to you。 Moreover， we can see this。

 if we actually are a little reckless with how we're using code。 And just so you know， too。

 though there are functions even in C50's library that let you use these larger values get long。

 of course， we'll get you along。 And this one's a little nonob。

 but percent L is the format code for printf just so you know。

 for printing a long integer and not just an integer。 So it's two characters instead of one。

 suppose though we actually want to use code involving some large numbers。 It turns out。

That certain bad things can happen。 So let me go ahead and do this。

 I'm going go back over to V S code here。 And I'm going modify my calculator to do something that a glance should be perfectly reasonable。

 Let me go ahead and open up calculator do C as before。 And where we left off。

 We had this add function。 And you know what， I'm gonna simplify it back to its very original version。

 I'm going to go ahead and get rid of the add function and just distill it to its essence。

 which is not to add anymore， but let's just do division。 I want to print out this time。

 maybe x divided by y。 So here we go。 X divided by y is a nice simple program in my calculator。

 let me do make calculator again， dot slash calculator。

 and let's divide something like one divided by3， which should。😊，Okay， weird。

 It gave me 0 instead of probably 03，3，3，3，333， as you might have expected for one third。

So what might the takeaway there be， Why am I seeing zero， perhaps yeah。Yeah， so zero is an integer。

 And indeed， that's what I'm telling the thing to print。 And in fact。

 if we go over to my little cheat sheet here a format codes， I'm currently using percent I。

 I should actually， when I do division of numbers that might have floating point values。

 a decimal point that floats left to right。 otherwise known as a real number。

 I want to use percent f for float instead。 So I'm actually going go back to my code here。

 and let's try this， percent f instead of percent I， and let me go ahead and make calculator。

 allright， well， this didn't work then format specifies type double， but the argument has type int。

 All right， so that too is is not quite working。 So I think I actually need to make a change here further let me actually go ahead and do this。

 It turns out that besides integers， there are these things called floats。

 and also double a float uses 32 B and double uses 64 B。

 And that doesn't necessarily mean you can count higher as much as it means you can have more numbers after the decimal point。

 So if you want more precise value。 You throw。Memory at it by using a double and 64 B instead of a float。

 But we'll keep it simple。 And let me go ahead and do this。

 Let me just do the math using the type of variable that I should be here。 Let me do not int。

 but float Z equals x divided by y。 And now let me go ahead and print out the value of Z。

 Strly speaking， I don't need the variable， but I'm trying to be pedantic and actually use a float explicitly this time。

 So we see a real number。 Allright， let me go ahead and do make calculator。

Dot slash calculator one divided by three equals damn Now。 it's just showing me more zeros。

 which clearly isn't the case。 Well， this is because of an issue that well generally call truncation。

 So truncation is just a term of art， that means if you take an integer and you divide it by an integer。

 even if you get a fractional value， the fraction just gets thrown away。

 because you're only doing integer based math。 So if there's anything after the decimal point。

 it just gets truncet and literally discarded。 So what should one divided by 3b， obviously0 point，33。

3，3，3，3，3，3 ad nauseum。 Unfortunately， you throw away everything after the decimal point。

 which leaves you still with just0。 And even though I'm seeing more zeros。

 that's because we throw away all of the threes， that is just what happens when you use integers and do any kind of division like that。

 But there is a solution。 we can actually convert or cast integers to floating point values。

 we can tell see， I know this is an integer now。😊，But go ahead and treat it as though it has a decimal point。

 even if it's 00 at the end of the number。 So I can go into this and I can use parentheses and literally write float and parentheses。

 And over here for why I can literally use parentheses and convert y to a float。

 The term of art here is type casting。 You're converting one type to another effectively or technically treating one type as though it's another。

 even if it doesn't necessarily have a mathematical impact。

 But what it means now is that Z will be used will be defined by dividing one float by another or so truncation will not now happen。

 So let me do make calculator dot calculator。 And now one divided by three there it is now the math is actually correct。

 But my God， we had to sort of jump through hoops just to get this to work。 So to be clear。

 the two issues the issue we encountered with truncation。 if you divide an int by an in。

 you will get an int， no matter what it should be mathematically。 But if you instead typecast。

the variables to a floating point value or a double for that matter。

 then a float divided by a float will give you a float and preserve all of those threes。😡。

But here's another catch， or at least a limitation， potentially with computers。

 What if I go ahead here and do， let me do this， let me show you one trick here。

 even though the syntax is a bit weird， instead of printing out percent F alone。

 Let me print out percent dot maybe5 F。 So this is weird syntax， and it's only specific to print F。

Percent dot 5 F means， show me 5 decimal places specifically。 So if I do make calculator。

 dot slash calculator 1，3，voila， I get5 decimal places。 If I want 6， let's do this。

 I'll change the code to 6 make calculator， dot slash calculator 1，3。 And now I get 6，3s instead。

 All right， Well， wouldn't it be nice to be even more precise。

 Let's give me 20 significant digits after the decimal points。

 So make calculator dot slash calculator 1 divided by3 and。😊，不。

So your middle school teacher seems to have lied to you at this point。

One divided by 3 is apparently not 03，3，3，3，3 with a line over it， or just infinite number of threes。

Okay， that's not quite the right conclusion， though。 Oops。

 why might I be seeing these weird numbers instead of just lots of threes。Intuitively。

Why this rounding error， yeah。Exactly， the computer only has limited memory， finite memory。

 So it just can't represent every possible number in the universe because we know from grade school。

 there are infinitely many of those numbers。 So what you're essentially seeing is the closest。

 it can actually get。 It's rounding to the nearest floating point value， if you will。

 And it also relates to how the numbers themselves are represent in memory underneath the hood。

 I can do a little better， though， let me zoom out and let me upgrade。

 so to speak from 32 Bs to 64 bits and use doubles instead， I can still use percent F。

 there's not you don't use percent D for double。 let me do make calculator again。

 dots s calculator 13， I get more threes， but still some rounding。 It's more precise。

 but it's not 100% accurate because that's just not gonna to be possible in terms of the computer's memory。

 So this is a whole other issue known as floating point in precisioncision。

 which is another type of limitation。 we saw integer overflow。

 if integers can only count so high before you sort of run out of bits and things wrap around。



![](img/9b3478adcf58801ce6a8c57047480262_148.png)

Floating point and precisionsion means that you can't possibly represent the infinite number of real numbers that exist in the universe if you only have a finite amount of memory。

 you wouldn't need an infinite number of bits it would seem。

 So these are two issues that actually fundamentally can influence the correctness not only of your code。

 but code in the real world and case in point back in my day， I graduated in 1999。

 And a lot of the world thought the world was going to end around then because around the time the years rolled over from 1999 to 2000。

 there was a lot of old software still running in the world。 And in fact， that old software。

 reasonably so only use two digits to represent years。 why memory was very expensive early on。

 And if you could use half as much memory to store a year that was a win that saved you money that saved you memory。

 The problem though， of course， is that a lot of old software from the 70s and prior was still running in 1999。

 and unless companies or individuals updated that software 1999 might be mistaken for the year 1900。

Instead of 2000， because all of the code just assumed that， of course， we're talking about the 1900s。

 this code is not gonna be running 50 years later， but it was still in that case。

 So people had to scramble and they essentially had to solve this by using more digits So upgrading from2 to4 nowadays and really since the 70s2 we've used 32 B integers to keep track of time specifically keeping track of the number of seconds using an integer from January 1。

1970， the so-called epic whereby that's just an arbitrary date early on where we just started counting time So all of the clocks in your max PCcs and phones pretty much just have a single integer that gets updated every second。

 but it's just keeping track not of absolute time per se。

 but how many seconds have passed since January 1，1970 just because that's the date humans chose The problem is you can only count as high as 4 billion give or take with 32 B and actually 2 billion give or take if you support negative numbers as well And the problem with that is that we're about to trip over the same issue again。

And not too long from now， this is the 2038 problem because in the year 2038 on that date。

 Mark my words， things could break again why， because that 32 bit value is gonna to accidentally wrap around back to a zero or a negative value So we're gonna to go through the wholedarn process again。

 Now thankfully， the solution as you might expect is kind of just to kick the can even further down the road and use 64 bit。

 which I think will get us another 290 million years of runway。 It's more than twice。

 So it's not our problem anymore at that point。 but that's fundamentally going to be the solution。

 but it will still be finite。 So we're just deferring to our descendants to actually deal with the issue some millions of years from now。

 these things are still running。 So if that does happen。 here's the specific date that in 2038。

 all of a sudden our clocks will still think because negative number will get subtracted to the current epoch time So we'll think we're back in 1901。

 So this has had some fun and very real worldorld implicationsplication。



![](img/9b3478adcf58801ce6a8c57047480262_150.png)

So for instance， this is the game PAman， which you might have played。

 kind of came out around my day back in time。 And if you get to the 256th level。

 this unfortunately is what happens because they don't really expect that players would spend all this much time playing packman apparently and they didn't really have a condition saying you win if you get to the 255th or 266th level And so what happens here essentially is that the whole screen gets very garbled because there's an integer in the original pman that counts to 256。

 but that's too big so it wraps back around to0 and it doesn't sort of know when to stop printing fruits on the screen as in this case to collect Another example of this is actually from the original donkey Kong game。

 which looks something like this in my day too whereby in the donkey Kong。

 there was this mathematical formula whereby the number of seconds you have to solve the game was a function of 10 times your current level number plus the number four that dictated how many seconds you get。

 So of course， the higher the level。

![](img/9b3478adcf58801ce6a8c57047480262_152.png)

get more and more time as the level climbs。 Unfortunately， once you hit level 22。

 the math ends up being 10 times 22 plus4， which gives you the number 260 and they too。

 were using 8 bit values， a single by to represent numbers， which means 260 is bigger than 256。

 and the way that math worked out was 260-256 if it wraps back around。

 gave people four seconds to solve level 22， which is just impossible。

 like Mario can't even get up a couple of levels or so from where he actually was So that too was sort of a wellknown bug as well。

 since that works out to be there。 Lastly， and this one is all the more real in 2015 Boeing 787 was documented as having not a hardware bug but a software bug in the following sense。

 a model 7，87 airplane that has been powered continuously for 248 days can lose。

All of its power due to the control units simultaneously going into failsafe mode。

 This condition was caused by a software counter that will overflow after 248 days of tenuous power Boeing at the time was in the process of developing a CPU software upgrade that will remedy the unsafe condition and people did the math。

 it turns out that Boeing was probably using an integer that was 32 B and they were keeping track of time。

 not in seconds but hundredths of seconds because if you do out the math after a 32 B value has reached 4 billion or 2 billion1 hundredths of a second。

 the number wraps around back to 0 or negative 2 billion and the implications was literally the plane's power would stop。

 And if you can believe it if you grew up with Windows Mac OS or whatnot。

 anyone want to conjecture what the solution was until Boeing updated their software。😡。

Turn the plane off and turn it back on because that has the effect of resetting its memory。

 and therefore， all of its variables back to 0。 So this is ultimately to say。

 as you dive into problem set 1， you're first in C。

 you too will make quite a few mistakes when it comes to correctness。

 You will encounter opportunities for better design and better style in the real world。

 there are very much these issues。 So even if you struggle， know that for better for worse。

 you're in very good company。 But some three months from now。

 you won't be in much better shape because this was week1。 And this is C S 50。😊。



![](img/9b3478adcf58801ce6a8c57047480262_154.png)

![](img/9b3478adcf58801ce6a8c57047480262_155.png)