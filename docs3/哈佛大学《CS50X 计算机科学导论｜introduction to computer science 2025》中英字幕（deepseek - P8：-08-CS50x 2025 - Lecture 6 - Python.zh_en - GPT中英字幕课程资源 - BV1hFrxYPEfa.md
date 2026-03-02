# 哈佛大学《CS50X 计算机科学导论｜introduction to computer science 2025》中英字幕（deepseek - P8：-08-CS50x 2025 - Lecture 6 - Python.zh_en - GPT中英字幕课程资源 - BV1hFrxYPEfa

![](img/bbd185be7f30ef08483a327402859508_0.png)

![](img/bbd185be7f30ef08483a327402859508_1.png)

🎼Yeah。

![](img/bbd185be7f30ef08483a327402859508_3.png)

Allright， this is C S 50 and this is week 6 wherein we transition away from that programming language called C to another programming language called Python and whereas a language like C is you probably come to appreciate for better for worse。

 is like very low level like if you want the computer to do something you have to do at everything yourself including asking for memory giving memory back Python is actually representative of a type of programming language that's generally referred to as a higher level language which does a lot of that lower level stuff for you。

 In other words， you don't have to manage your own memory。

 you can iterate over things much more quickly than using a traditional for loop as in C。

 And so in short a language like Python is just easier and more pleasant。

 dare're more fun to use Moreover， it has even more of an ecosystem of libraries libraries being code that other people wrote that you can use and as we'll see today。

 it's so much easier to get real work done and really focus on the problems that are of interest to you What today is also going to be about is teaching yourself a。

Lguage and indeed， the way we're gonna approach this lecture and the coming weeks' problem set and beyond is to give you all of the right tools and techniques by which to learn a new language in the confines of CS50 initially but after this course on your own because even if you don't go off and major in computer science odds are you'll have some occasion for programming in the future be academically professionally or for fun and so odds are a lot of the languages we're talking about today are not going to be nearly as useful in a few years and few years out but the fundamentals。

 the ideas underlying them will be the same and so the goal today is to pick up new ideas and syntax along the way so recall that where we began with this in week0 like hello world everything was so cute and easy to do it's sort of escalated quickly when we got to see where all of a sudden hello world became a little something like this but to my point about Python being higher level and just doing more work for you today in Python if you want to implement hello world it's going to be reduced to a single one line and we'll see this in all sorts of context。



![](img/bbd185be7f30ef08483a327402859508_5.png)

So is that if you want to run Python programs， that process today is going to change a little bit。

 recall that in C。 we've had this technique for a while now where you have to make your program and then you can run it with dot whatever the name of the program is technically we reveal that that's short for a longer form command where clang is the actual compiler but today the command is going to be simpler and fewer in quantity and that this is the command henceforth via which will run a program in a language like Python in particular there's a few things that have changed here obviously the file extension is different instead of dot C it's going to be dot py or pi for Python but notice too it's only one step instead of two and that's because as we'll see Python is generally described as an interpreted language whereas C is generally described as a compiled language and that's not a characteristic that's intrinsic to the language just by convention most everyone in the world when writing C code compiles it thereafter from source code to machine code the zeros and ones your computer。

 your CPU ultimately understands。Python in other languages like it are a little more user friendly and that you don't need to write your code。

 compile your code， run your code， change your code， compile your code， run your code。

 you can actually skip the compilation step and just use a program that coincidentally is called Python itself but whereas Kang for instance was a compiler that converted source code to machine code Python in this case is an interpreter which for now you can think of as just running your code top to bottom left to right and looking at each line of code and figuring out what to do with it without actually compiling it to zeros and ones first So it's a little more user friendlyendly half as many steps and so that too is a good thing Well let's actually see this in context for a moment in VS code let me go over to the very first program we wrote in C which was this one here in a file called hello do C or in this case hello zero C and what I want to do here is create a new program that's the distillation of this in Python So let me do code of hello pi in this case notice that it's open to second tab as。

😡。

![](img/bbd185be7f30ef08483a327402859508_7.png)

But what I'm going to do a bit of today is open two files side by side just so we can see exactly what's going on。

 So if I drag this tab over here， you'll see that it'll split the screen in this nice convenient way。

 So now I have two files open but in this file I'm just going do print quote unquote hello comma world and that's it what am my next gonna do in order to run this code at right I don't need to compile it I just need to interpret it by running a program called Python on a file called hello do pi crossing my fingers as alwaysvoil now I have written my first program in Python So of in so far as at least it's now one line of code instead of six there's no curly braces。

 there's no includes there's no int main and void there's a lot there's a lot less clutter in there but the idea is ultimately the same But what's exciting about Python and just to kind motivate why we're introducing a higher level language here on out you can just get a lot more interesting work done quickly So for instance。

 let me go ahead and do this。Let me go ahead and open up in my own PSet 5 directory files that I brought in advance。

 which was a solution to problem set 5's spell checker。

 whereby recall that you made a program called speller。

 But that compiled a file along with it called dictionary do C。

 which you had to implement the functions within。 So if I go ahead and run this program recall on maybe one of the bigger files like the Sherlock Holmes text and hit enter。

 that's gonna churn through all of the seeming misspellings therein and tell me that time in total took 1。

17 seconds to spell check that whole file。 Well， that's pretty darn fast。

 But consider how many hours， days week， it took to actually implement that spell checker。

 the contents of dictionary do C。 Let me propose that what I'm gonna to do here is open up a new file called dictionary dot pi。

 And I'm going propose to implement four functions， But in Python， instead of in C。

 and those functions are gonna be check load size and unload。 And let's see how quickly I can。

Now problem set5 using a language like Python instead of C I'm gonna to go ahead and open a file called dictionary dot pi。

 and in the first line of code I'm going to give myself a variable called words and I'm gonna set that equal to a function called set。

 which just like in math gives me a container for a set of value。

 So no duplicates for instance you can think of it like sort of like an array sort of like a list but less well definedfined in this case。

 it's just going to be a set of words Now I'm going go ahead and define a function in Python called check just like in C it's going take one word as input and the way I'm going implement this check function in Python is quite simply as this return word do lower in words Allright that's it for the check function in Python Now I'm going go ahead and define another function called load。

 which just like in C takes a dictionary as input and then I'm going implement that as follows with open dictionary as file call in and then below that Word update file do read do split lines and that's it for that。

😡，And then I'm going go ahead and return true capital T。 below that。

 I'm going to define a size function whose purpose in life is just like in C to return the size of this here dictionary。

 So I'm going return the length of that words variable that I created on my first line。

 And then down here， I'm going define lastly， a function called unload。 but as I mentioned earlier。

 because Python manages your memory for you， you don't need to go in free anything like that。

 So you know what I'm just gonna to say return true。

 and I'm done This then is problems set five written in Python So a bit of a flex to be fair because I had the cheat sheet in front of me with all the answers and might have taken me a few minutes to actually implement this instead of indeed a few hours or again。

 a few days。 And what' in here should not necessarily be obvious these are some somewhat cryptic lines of code means you what we've been doing in C。

 but by the end of today by the end of this week by the end of the course after you've seen more python you'll be able to read and understand what's going on here And in fact。

 the way I myself wrote this code some time ago was I open。😊，up in one file， dictionary C。

 and then I opened up another file， dictionary pi。 and essentially translated the left to the right by Googling as needed。

 the syntax and Python or looking back at my own notes。

 but that too is going be how we today in this coming week introduce you to this new language by showing you how it is similar to and sometimes different from a language you already know。

 And so kind of the hard part is done now that you know a fairly low level and challenging language like C。

 even though it's been just a few weeks， you can really bootstrap yourself to knowing understanding new languages present in future by just recognizing similarities and patterns。

 And along the way， there's undoubtedly going to be new features that you encounter in Python in future languages。

 but no big deal， you're just going to be filling in some gaps in your knowledge at that point instead of starting from scratch。

 I guess pun intended。 Well， let's do one other sort of revelation here recall that in problem set4。

 you had to implement a few filters like that of blurring and maybe you we're feeling more comfortable and you did a bit of edge detection。

Let me propose that I could do exactly that in some Python code tube。

 So let me go ahead and open up a new file。 for instance， called blur do pi。

 Let me go ahead and use a library that comes with python that we've already installed。

 It's called theython image library。 So from PL import image comma image filter。

 And on my next line I'm gonna to create a variable called before。

 I'm going to set that equal to the return value a function called image do open and I'm going to open a file that you've seen before bridge do BM My next line of code I'm going create a variable called after to represent the after the filtration of this image and set that equal to the before variable dot filter passing in as an argument image filter box blur open parenthesis1 close per end。

 And then lastly I'm going to do after save。 I'm gonna save this file as out do BM。 Now of course。

 I'm relying on the fact that there is a file called bridge do BM。 So I'm gonna grab。

A copy of that from problem set4， and that file is going to be a nice。

 pretty picture of the weak bridge down by the river。 And in fact。

 if I open that up with code of bridge do Bmp this here is the original version of that there bridge。

 So let's run my four lines of blur dot pi code on this and just to make it a little more obvious on the screen here。

 instead of just looking at one pixel around every pixel to blur things。

 I'm gonna be a little dramatic and use 10 pixels just to make it even blurri or to appear nicely on the screen。

 I'm gonna go ahead and run Python of blur dot pi and when I hit enter those four lines of code will be interpreted so to speak top to bottom left to right。

 Nothing seems to happen。 But if I type LS now I should see indeed a file called out dot BM as well。

 let me go ahead and open that out do Bmp。 and whereas the before version was this the after version is now this in just four lines of code。

For those of you who were indeed feeling more comfortable this past with that same problem set。

 let me propose to implement the edge detection algorithm that you might recall。

 and let me create a different file for that。 So code of edge dot pi and inside of edge dot pi。

 I'm going go ahead and do the same thing as before from the Python image library import an image feature and an image filter feature。

 then give myself a variable again before equals image do open quote unquote bridge do BM。

 then I'm a variable called after as before equals before do filter passing in this time image filter do find edges。

 which is a feature that just comes with this library。

 and then I'm going to go ahead and do after do save and again out do BM I'm going very quickly then run Python the name of the interpreter on edge dot pi。

 which is going to use as input bridge do BM again， which is the original version。

 But if I now open up out do BM and hit。😊。

![](img/bbd185be7f30ef08483a327402859508_9.png)

Sure。Instead of looking like this now， after four lines of Python， it looks like this。

 So if you've been feeling a little frustrated by just how much time， how much energy。

 how many lines of code it takes to solve problems that ultimately may very well be interesting visually or otherwise。

 it's now going to get a lot easier to do some of those same features。 But of course。

 will give you the capability to do some more things as well。 But before we do that。

 let's actually take a tour of what some of the features are that we're gonna to get now with a language called Python sort of evoking memories of week one when we transition from scratch to C。

 So in the world of Python， there's absolutely functions。 You just saw a whole bunch of them。

 And again， the syntax looks new and different and perhaps a little weird versus C。

 But the course of today in this week， everything I just typed will become more familiar。

 Here' is gonna be a side by side comparison now of scratch。

 just like from week 0 to this week in Python。 but we'll compare it along the way to some C code as well。

 So this was， of course， the simplest function we use back in scratch to just say hello world on the screen in C。

😊，It looked a little something like this， but I've claimed already today in Python。

 it's going to instead look like this。 And just as a little bit of a comparison。What's different？😡。

我子呀。So there's no semicolon， amazingly Python largely gets rid of the semicolon so when your thought is done。

 that's it， Python will figure out that it's done， you don't need to terminate your thought with a semicolon。

 what else is different here in yeah。😡，Yeah， so backslash n is missing。

 which in C we needed to tell the computer to add a new line。 so to speak。

 move the cursor to the next line， turns out that after years of experience。

 humans decided that gosh， we are so often using backlash n in our print statements。

 Let's just make it the default instead of vice versa that does invite the question。

 well how do you undo that， but we'll come back to that before long。

 but indeed you don't need the backslash n the third and final difference perhaps obvious now is that it's print instead of print F that doesn't mean you can't format strings。

 but the word print is just so much easier to remember it's a little less arcane。

 So the Python community decided in their language to call this print instead。

 And what you're seeing already it's the slightest hint of the reality that after years pass and different programmers start using languages。

 they come up with opinions。 what they like， what they don't like。

 they eventually decide we're gonna invent our own language that's better than everything before it And so what you'll see is that a lot of the frustrations。

 confusions you might have encountered。 You're in good company because some of those now。

Will go away the catch is， of course sometimes people will disagree as to what the right outcome is。

 the right design， and this is why there's actually hundreds。

 maybe thousands of programming languages in the real world thankfully there's probably only a few dozen that are actually very popular and commonly used in practice All right so in the real world too we of course have libraries and we saw some of those libraries in the world of C we're also going to see them in the world of Python even more powerfully so like the filtration we just did of images being able to very quickly implement a spell checker with with the code that I wrote in the world of Python just know libraries are generally called modules and packages and there's some slight difference between those two but for now modules packages are just Python terminology for what we already know to be libraries CS50 has its own library and in fact in C we use this atop any program that we wanted to use get string get in and strings themselves in Python there's still going to be a CS50 library but very brief training wheels that。

😡，Available if only to ease the transaction from C to Python。

 but the syntax for using CS50's library henceforth is going to be more simply import CSs 50 very similar to what we saw a moment ago with that Python imaging library Python image library There's alternative syntax you might see over time where if you only want to import one or specific things you don't have to import the whole library you can import from CS 50 a specific function or symbol more generally like this So you'll see two different techniques like that Well let's go ahead now and actually build on the program we wrote already by doing something just like we did in week0 as well as in week1 where we actually got input from the user So in scratch here was how we prompted the user what's your name we got back a socalled return value and then we joined hello comma space with that their return value in C this didn't translate nearly as cleanly we had to introduce of course。

 not only get string for the same function。

![](img/bbd185be7f30ef08483a327402859508_11.png)

![](img/bbd185be7f30ef08483a327402859508_12.png)

But we also had to introduce in the context of Prif these placeholders like percent S for better for worse。

 what you're about to see is several different ways to solve the same problem in Python。

 some of which are a little more similar to scratch。

 some of which are a little different from scratch as well。

 don't have to absorb them all from the get- go， but here's how we might do this in Python instead。😡。

One， we can declare a variable called answer。 We can then set it equal to the return value of getstr。

 which for now is in the CS50 library for Python。 You don't need it per se in the real world。

 but for now for parody would see we've given you this getstr function。

 It like and see takes an argument like quote unquote， what's your name。

 but no semicolon at the end of this line。 Second line of code。

 noticeice that we're again using print and Python， not printf。

 we're saying quote unquote hello comma space。 And then a little weirdly。

 we're using what looks like the addition operator to add so to speak。

 the answer to that end of that phrase， but those familiar or not。

 what might the plus really represent here。 It's not addition in a mathematical sense。 Yeah。😡。

So it's what we would call concatenation to take one string on the left。

 one string on the right and join them that is concatenate them together。

 which is why I need not only the comma grammatically here。

 but also a space so that we actually have a string that looks the way we intend。

 So this is one way then to implement this here program that we already implement in scratch as follows。

 but there's other ways as well。 I can also change this a little weirdly to be a comma separated list of arguments。

 So it turns out unlike in C inython if you pass one，2。

3 or more arguments to the print function by default， they will just all be printed 1，2。

3 but with a single space in between them。 So that's just the way the print function works per its documentation。

 which we'll see before long。 So here I've gotten rid of that space。

 and I've just said my first argument is hello comma and my second argument is answer。

 and I just leave it to print to effectively concatenate them together on the screen by printing one followed by the other。

 So that's the second way we might do this inython。😡。

Here's a weird looking third that for better for worse is probably the most common way to do things nowadays。

 even though it's more of a visual mouthful， so I'm still using the print function。

 but theres that f again， but in a weird place it turns out if you want Python's print function to format a string for you by plugging in one or more values the way you do that is you tell Python not next to the print function but to the left of the string itself that hey Python here comes a format string。

 aka and F string and then inside of those quote marks nicely enough。

 you can actually use literal placeholders， these curly braces that say put the value of the answer variable there so it's sort of a new and improved version of print f in C。

 which annoyingly always had us using percent S， percent I percent f and so forth now you just put curly braces and the name of the actual thing you want to plug in to that location this is called variable interpolation whereby the variables value answer in this。

😡，Case will be substituted without the curly braces appearing in the final output。

 So that's then how we might implement exactly that same feature using this thing called a format string。

 So how might I go about doing this。 Well， let me actually go back to V S code in just a moment here。

 and let's go ahead and open up my same file called hello do pi。 So code of hello do pi。

 let's go ahead and implement this variance thereof。 So and in hello do pi。

 I previously had just this single line of code。

![](img/bbd185be7f30ef08483a327402859508_14.png)

这个啊。Oh， it was making noises。 Sorry， Okay， that was Anne。 Thank you， An。Oh， thank you， thank you。

 Ian。So here， let me go ahead and open a file called Ho1 do C。

 which I brought back from week1 itself。 And let's go ahead and open up hello dot pi here again。

 just so we can see these things side by side， I'm going drag this one over to top right so we can see hello do C on the left。

 albeit somewhat cut off and hello dot pi on the right。

 And let's now change hello dot pi to actually get some user input。 So from C50's library。

 I'm going to import a function called get string。 And then inside of this actual program。

 I'm going to create a variable called answer。 I'm going set it equal to the return value of get string。

 I'm going pass prompt like what's your name question mark space and then close quote and close parenthesis。

 And then lastly， I'm going use one of those F strings and print out quote unqu or rather F quote unqu hello comma answer close quotes and it's a little weird now with the F in the quotes and the curly braces and the parentheses。

 But if you just follow them from inside out。Are all nicely symmetric and balanced。

 If now in my prompt， I go back down and run Python of hello dot Pi enter。 instead of seeing。

 of course， hello comma world immediately， I can type in my name and hit enter。

 And now I see exactly that。 But there's a few things I could do wrong here。 For instance。

 if I forget this here， format string and just do quote， unquote， Curly Bra answer。

 And then I go back and run Python of hello dot Pi。

 I'm still gonna be prompted for my name like David。 But what's gonna go wrong now， intuitively。😊。

What am I going to say， yeah。Perfect， because I haven't told Python that this is a special formatted string with that little F。

 It's indeed going to print out Ho， comma， Curly Bra answer， just as we see here。 So a subtle bug。

 but one that's very easily fixed with that there。 F。 But there's something else worth noting here。

 Let me go back over to highlight this code。😊，This varies from C in another way， too。

 There's indeed no semicoons on lines 3 or 4。 But what else is different Vi V。

 the C version here still at left。What's different？How about here。 So there's no main。

 So there's none of this， There's none of this and there's no curly braces。 Yeah， what else。

I didn't have to declare the type of the variable。 So this too， for better for worse。

 is a feature of Python。 we'll see that Python has data types。 There are strings。 There are ints。

 there are floats， but you don't need to tell the interpreter what your variables are rather Python as an interpreter will just figure it out from context。

 So if you're assigning a variable called answer to what clearly is going to be a string。

 the type of that variable answer will be a string。 if though you used get int or something similar。

 the type of that variable might be an int instead。 So here too。

 a lot of the things that what isn't the computer just figure it out are baked into Python as features。

 So if I go back over here after now having implemented this version of hello。

 we can revisit perhaps something that I glossed over earlier， whereby in Python。

 the default seems to be to give you a new line at the end of any print statement。

 that does kind of invite the question， well how do you actually get those get rid of that if you indeed do。

 Well， this gives us a。😡，Brief opportunity to talk about one piece of jargon in the world of Python and certain other languages。

 which is that all of these parameters or arguments we've been using for weeks where you just put a comma separated list of arguments or values inside of parentheses。

 when calling a function to give those functions input those have all this time been called positional parameters because the order has always matter the first thing。

 the second thing， the third thing influences what the function does with those arguments。

 but inyth and certain other languages， there's also what we're gonna call named parameters。

 whereby you can actually specify not just a generic comma separated list of values for which the order matters。

 you can instead provide the name of a variable and its value， the name of a variable and its value。

 specifically the name of a parameter and its value as a comma separated list。

 the upside of which is that it's a little clearer to you the reader， you the programmer。

 what does what and it's also not nearly as vulnerable to you just screwing up the order and getting them slightly out of order and constantly having to check the document。



![](img/bbd185be7f30ef08483a327402859508_16.png)

![](img/bbd185be7f30ef08483a327402859508_17.png)

As to what goes in what order。 if you recall using F read or Fright， for instance。

 which takes a few arguments， I mean， those two are particularly annoying。

 And even I always forget like which comes first， if I could just use the names of those parameters。

 it might have eliminated some ambiguity So how can we use in Python named parameters。

 let's just do a relatively simple example that's actually pretty commonly commonly leverage。

 which is this if I， for whatever reason， let me get rid of my C version now， and in fact。

 let me simplify this and just go back to printing out in hello do pi hello comma world this as before。

 will print out hello comm world with a new line。 if I want to get rid of this though。

 I can do that by consulting the documentation for Python And in fact。

 the official documentation for Python lives at this URL docs Python org the upside of this documentation existing is that unlike C。

 which doesn't really have an official place to go for documentation other than the manual pages。

That we recall at manual cs5。 have given you studentfend versions thereof like everyone in the world goes to this URL when looking up things for Python officially in its own documentation。

 for instance， at this particular URL there is a list of all of the functions that come built into Python itself and if we poke around further there there's one indeed called print which is really the only one I've been using thus far that comes with the language。

 and in that documentation， you'll see a somewhat cryptic line like this。

 this is the so-called signature or prototype for the print function。

 the syntax where this is a little different from what we saw and C。

 but what I see here in the documentation if you go to that same URL is that there's a function called print that takes potentially1。

2，3，4，5 or more arguments for five or more arguments or parameters。

 but what are they Well over here is some new syntax and trust me this is not mean pointers。

 there's a star， but nothing to do with memory or star or memory。



![](img/bbd185be7f30ef08483a327402859508_19.png)

Pointers， this just means that there's gonna be zero or more objects that can come as a comma separated list。

 And we've used that feature already when I printed hello plus name when I printed hello comma name I got back I passed in one or two arguments。

 This just means you can pass in zero or more just by their position。

 The rest of these are so calledled named parameter whereby the print function comes with one named parameter called Sep for separator whose default value is a single space per the unquote The print function also comes with an end named parameter whose default value。

 and here's going to be the answer to that question earlier is backslash n。

 So this is why every line ending from the print function has a backlash n automatically given There's something called file。

 there's something called flesh more on those perhaps another time。

 But this is why I automatically got a free space When I passed in two arguments。

 This is why I keep seeing my cursor move to。

![](img/bbd185be7f30ef08483a327402859508_21.png)

![](img/bbd185be7f30ef08483a327402859508_22.png)

Next line。 But the fact that these things have names。

 SP and E N D means I can use these named parameters。

 if I so choose to override their default arguments。 So for instance。

 if I want to override the separator， I can use quote unquote something else in between words。

 if I want to override the new line， I can change the backlash n to something else as well。

 So if I go back to V S code here and for whatever reason。

 I do want to get rid of that new line ending， I can pass a second argument into print specified that the name of this parameter is E D and set it equal to not backslash n。

 but really anything I want。 So just to be dramatic， let's use an exclamation point。

 So sort of excitedly say hello world。 And if I now rerun this program as such。

 now I see hello world but then my prompt is immediately on the same line。

 I can get rid of that too if I really want， I can do backlash N after the exclamation point and rerun this again and now we back to the usual。

 but I do get。

![](img/bbd185be7f30ef08483a327402859508_24.png)

That exclamation point now for free as default functionality。

 So it's a little weird because I'm mixing sort of apples and oranges。

 So to speak whereby this is positional and this is named。

 But so long as you put your positional arguments first and any things that have explicit names after those。

 Python can distinguish one from the other。

![](img/bbd185be7f30ef08483a327402859508_26.png)

Questions then on any of this， just yet。快神价。A really good question。

 Can you change the type of a variable once it's there。 Can you change， for instance。

 a string to an integer or maybe vice versa short answer， Yes。

 And we're gonna trip over that with an example in just a bit。

 And let me call that one other thing that's worth noting here in the documentation for Python。

 And even in your own code， it turns out that you can use single quotes in ways we have not thus far。

 recall that and C double quotes meant it was a string。 So typically a phrase， a sentence。

 a paragraph， whatever。 But single quotes and C represented what。

So a single character like that is the definition in Python。

 This seems to suggest single characters too， but I clearly just did an exclamation point and then backslash n。

 So two characters。 and that's in fact allowedlo in Python。

 There's no difference between single quotes and double quote stylistically in Cs 50 in style 50。

 will actually nudge you toward using double quotes just for parity with C。

 but it is perfectly reasonable to use single quotes instead in python。 but styyllistically。

 you should be consistent。 Why are they both tolerated。 Well， you know all these weeks。

 you've been holding the darn shift key and then hitting the quote marked to get double quote now you don't have to hit the shift key anymore if you don't want to just speed up your code even more。

 And that frankly， is probably part of the motivation for even little syntactic differences like that。

 All right， how about some other features that we might want to bring into the mix。

 We've seen variables already like answer， let's make this a little let's do this side by side with scratch and with C as well。

 So in scratch， this is how we。

![](img/bbd185be7f30ef08483a327402859508_28.png)

Created a variable called counter and initialized it to 0。 In C。

 we achieved that by doing int counter equals 0 semicolon。 All right， in Python。

 we've already seen something reminiscent of this， albeit with strings instead of integers。

 but probably not a logical leap to assume that this in Python is how you could create a variable called counter assign an integer。

 namely0， No semicolon， No data type， and this will simply be an int。

 because it's pretty obvious to the interpreter that0 is an int， not a string。 So of course。

 underneath the hood， This is going to be an int。 What else could we do in scratch。

 we could change the counter by one by incrementing it adding one to it in C。

 we saw a few different ways to do this。 we can do counter equals counter plus one。

 which seems like a paradox that how could that possibly be but recall we do the addition at right。

 we copy the value from right to left when using the assignment operator in Python。 Meanwhile。

 we would do this。 counter equals counter plus one， same exact thing except for， of course。

 the semicolon no longer being necessary， But in C， we could also do this。😊。



![](img/bbd185be7f30ef08483a327402859508_30.png)

Couner plus equals one semicolon turns out you can do the exact same thing in Python without the semicolon。

 But there's one thing you can't do。 Who knows why， But what can you probably not do。😡，Yeah。

 so counter plus plus if you've been in using plus plus and minus minus for better for worse Python does not have those。

 So we're back to the slightly more verbose version here。

 So we get two out of the three possibilities。 but just a minor difference that will be ingrained over time。

 Well， what about the actual data types that Python supports。 Well， we've used strings already。

 I just showed some integers there。 Python does have its own list of data types。

 which is actually at a glance shorter than C's when it comes to the most primitive ones in C。

 we saw at one point pretty much this list and then we created some of our own in Python。

 this list indeed gets a bit shorter such that we have bulls still for true false values。

 but as you might have glimpsed earlier， it's capital true and capital false T and f respectively just because there are still floats in the world of Python。

 there are still ints in the world of Python and there are strings but there are called starss STR for short。

 and there are indeed some other ones as well。 But there are no doubles per se， there are no。

LsRather， Python generally uses a bit more memory。 So you， as the programmer。

 don't need to worry about how many bits are being used， particularly for something like integers。

 So more on that before long。Good question。 Are there no characters， short answer correct。

 There are no characters， There are only strings， which can be single characters and even zero characters。

 because heck， that seems sufficient rather than distinguishing between one or the other。

 So if you want a character in Pyon， you really the best you can do is a string with a single character instead。

 Now， it turns out in Python， there's gonna to be other features as well， data structures。

 So just a week ago， we spent on week fives material when looking at trees and tries and hash tables and more Python just gives you those and other data structures built in no longer do implement your own spell checker with your own dictionary。

 you can use， as we did earlier， a set， turns out there are dictionaries or died objects that come with Python that you can yourself use。

 There are topples， which are like X comma Y values or like latitude， comma longitudes。

 So short lists of values。 There's actually lists which are similar in spirit to seeize arrays。

 But recall that the headache of。😊，TheseAs as of week 5 was it's not very easy to grow them or strengthen them because of all of the darn memory management。

 Python。 if you use a list essentially gives you a linked list automatically。

 you don't have to think or use any memory management or pointers at all。 And range。

 we're gonna say just gives you a range of values。 If you know you want to count from one on up to something else。

 range is actually a function that can give us some of that same functionality as well。

 So let's perhaps take some of these out for a spin here。 Let me go back to V code。

 Let me close up hello do pi。 And let's focus on maybe implementing a simple calculator as we did a few weeks ago。

 In fact， let me go ahead and open up from my distribution code from lecture today。

 wherein I brought in advance。 And these are on CSs5s website a whole bunch of examples from earlier weeks that we already implemented together。

 So， for instance， in week1。 We actually implemented a calculator that prompted the user for two ins X and Y。

 and then simply added them together using printf in this way with percent I as the placeholder。



![](img/bbd185be7f30ef08483a327402859508_32.png)

And a second argument， which was the sum thereof。 Well， if I want to implement this in Python。

 it's actually going to be pretty similar。 So let me also run code of calculator dot pi that's going open a second tab。

 for the sake of comparison。 Let me drag this over to the right。

 So we can see these things side by side。 And now let me do this from C50's library import the get int function。

 which I claim exists in that library。 Then let's go ahead and create a variable called x set it equal to get int and pass in a value prompt of x colon space just so the user knows what we're asking for。

 Then let's do y equals get int and prompt the user for a y value。 And then down here。

 let's go ahead and print out X plus Y。 I think it's pretty straightforward as written there。

 We don't mention the semicolonons。 We don't mention the data types。 But for the most part。

 the logic is exactly the same。 Let me run Python of calculator dot pi type in one， type in2。

 And I do get back in fact3。 So that calculator seems actually to work。

But let's get rid of CS50's library。 So just as quickly as we put these training wheels on today。

 let's take them back off so that the end of the week。 at the end of the course， certainly。

 you're not relying on any of these training wheels anymore。 So let me get rid of this line of code。

At the very top， no longer using get in。 And let's do this using Python's own built in functionality。

 So Python itself supports this here function called input。

 which similar to get string and get in and get flow takes a prompt as input。

 So I'm gonna say x colon as before， I'm gonna go ahead and say input Y colon as before。

 And then I'm just gonna print these both out。 using Python's own input function。

 instead of C 50 is get int。 Let's run Python of calculator dot pi again， enter type in one。

 type in2。 And the answer， of course， should be。Not 12。So what just happened here？😡。

Should still be three， yeah。Yeah， so it seems that X and Y came back as strings。

 And so what's happening with the plus operator here。

 It's actually being interpreted as concateation。 So I'm really saying not 12 per se。

 but  one2 join together。 because the variable that apparently the return value that comes back from Python's own input function appears to be a string that is a stir by default。

 Now， there are ways to fix this in python。 And in C。

 recall that we were able to cast some values from one to another。

 like int to chars and back and forth。 It's not quite as easy as that in Python。

 because technically a string as we know underneath the hood has one or more characters。

 maybe there's a backslash 0 somewhere in there。 who knows how Python is doing it。

 But there is a function in Python called int， which takes as input a string。

 and it will do its best to convert that string to the actual int that resembles it。

 So if it's quote unquote，1， it's gonna give me the actual int known as one and so forth。

 So let me do that here as well as。let me again run Python of calculator pi enter1 again，2 again。

 And this time one plus 2 equals3。 So similar in spirit。

 But now I just need a new tool in my toolkit， this int function， which does that conversion for me。

 Now， what actually is in this library C50's zone that you may or may not want to use。 So in C。

 we had these functions， as well as some other stuff。

 including the actual definition of string in Python。

 there are indeed strings that come with the language they're simply called StRS SR in C50's library for Python though。

 we kept it simpler and consistent with Python， the language itself。

 So C50's library for Python has get string， it has get int， it has get float。

 these we'll see are still useful， because just like in C。

 recall that the user types in like cat or dog when you're actually asking them for an integer are functions prompt the user again and again and again。

 So these functions will do that as well。 We'll soon see that the input function in Python is's quite similar to get string。



![](img/bbd185be7f30ef08483a327402859508_34.png)

![](img/bbd185be7f30ef08483a327402859508_35.png)

But it's not as tolerant of invalid input， like cat or dog。

 if you're actually trying to get an int or float， you're just gonna to see a scary error message instead on the screen。

 which we'll come back to before long。 But this is to say the library is there to get you started。

 but not strictly necessary ultimately。 But if you want to use those functions。

 you can do as before from CS50， import the name of the function and you can do this three times if for whatever reason in a program you're using all three of these。

 you can just separate them by commas in this way and import all three of them here at once。

 or as you might recall earlier， you can just import the name of the library。

 So what something like import C50， though the syntax thereafter changes a bit。😡。



![](img/bbd185be7f30ef08483a327402859508_37.png)

![](img/bbd185be7f30ef08483a327402859508_38.png)

Before we forge ahead to canal conditionals， just comparing something side by side。

 and then we'll build up some more interesting programs。😡，Questions， for the most part。

 it's just syntactic differences and not really fundamentally different intellectual ideas under the hood just yet。

 So here we are with conditionals in scratch， if you wanted to compare X and y as variables and say conditionally。

 X is less than y。 We converted that to C as follows。 The curly braces are about to go away。

 The semicolons is about to go away。 And there's gonna to be one new piece of syntax here in Python。

 the same idea looks like this。What is the one piece of syntax that did get added， though。

 in this case。Feel free to shout it out。There's a colon suddenly which we did not have in C。

 It turns out in Python， though， this is both a plus and a minus depending on your religion when it comes to white space and programs。

 So in C， if you were not in the habit of clicking style 50 and letting it guide you toward better formatted code frankly。

 you could just left the line everything in your C programs and even though it would be mess to read difficult to grade。

 it would still work， it would still be correct， but just stylistically bad in Python。

 it seems that humans over the years were just so darn frustrated by students and presumably colleagues alike formatting their code poorly that in Python indentation matters。

 So if you want to execute print conditional on X being less than y。

 you can't just put print right below if and expect the reader and the interpreter to figure things out。

 you must indent by convention 4 spaces instead。 you can override that and you can adopt different paradigms within your own company or school before is the。

😡，Style 50 would now expect。 So this is to say the colon means execute conditionally everything that's indented below that as though there were curly braces instead。

 All right， how about something else in scratch， if you wanted to do an if else。

 it look like this in C it looked like this which is identical except for the else block here in Python you can probably predict how this is gonna get a little more succinct no more semicolonons。

 no more curly braces， no more backslash ends for that matter but a colon here and a colon here and again。

 indentation matters and must be consistent for spaces in this case for both Finally。

 if else if else， we did in scratch， you can do that same thing in C almost identical except we've got this elseif。

 this is the only one that's weird and even I forget how to spell this all of the time in Python。

 the semicolonons are about to go away， the new line is going go away。

 the curly braces are going go away and we're gonna misspell else if as such。

 so it's L if in Python colon which is how you would。Implement if L if， L， if。

 L if else for conditional like this。 Some languages very confusingly use elses， if were E， L， S I。

 F， but no E， and probably shouldn't even said that because now you'll be as confused as I have been for years。

 But let's move on to what we can actually do now with these here strings。

 So we know what we can use these conditionals in this way。

 Let's go ahead now and revisit some programs from C。

 But this time using some new syntax and features。 So let me go back to here V S code。

 let me open up in one window here。😊。

![](img/bbd185be7f30ef08483a327402859508_40.png)

How about compare 3 dot C。 So this was from today's distribution code， a file called Compare 3 dot C。

 which we looked at some time ago。 And what this program did quite simply is exactly what we just saw on the screen。

 But with a fullfledged main function and the header files and the like。

 But all this program does is tell us whether X is less than y or not。 Alright。

 how could we go about implementing this in Python pretty straightforward， Let me open my terminal。

 let me do code of compare do pi for this version。 let me drag it over to the right。

 So I can see these things side by side and hide my terminal again。

 let's go ahead and import from C S 50， the get int function。

 just to make our lives a little easier for now， Let's use X equals get int and prompt the user for what's x question mark just like I did it right left。

 Let's do y equals get int passing in what's y question mark just like get left。

 Then let's just do if X is less than y colon， enter。 and notice V S code。😊。



![](img/bbd185be7f30ef08483a327402859508_42.png)

![](img/bbd185be7f30ef08483a327402859508_43.png)

Is not only smart enough， but deliberately configured by us to know something about Python。

 So it automatically indented for me， just like C very often has two。

 Let's print out X is less than y quote unquote L if x greater than y colon。

 then let's print out X is greater than y， close quote else colon， print out X is equal to y。

 So nothing different versus the slides。 But you can kind of see visually just how much more compact the code is like 11 actual lines instead of 21。

 So it's just elimining a lot of distraction and clutter and tightening things up if nothing else。

 Let's go ahead and run Python of compare do pi enter Let's type in1， type in 2。

 and let me just wave my hand at the reality that I'm pretty sure the code is correct and would work a correctly if we typed in2 and1 or1 in12 and2 and so forth。

 So this is to say that comparing integers in Python logically works exactly the same way as in C。

 But things recall。In Python got a little weirder when we actually tried comparing， say。

 strings instead。 And recall that when we compared strings in Python。

We had to solve a problem we encountered the very first time we compared two strings in C， S and T。

 as I think I called them weeks ago。They were never the same。

 according to my first version of my code， why？😡，Like whyhy is it harder to compare strings in。C。

We would be point to the wrong。Exactly， so recall from week 4。

 where we really looked underneath the hood and we realized that， oh， a string is really a cha star。

 which is the address of the first character in the string。

 So whenever you compare two strings with equals equals and C。

 you're really comparing the memory addresses。 And those probably are not gonna be the same。

 So even if the strings look the same， They're always different。 That was a pain in the neck。

 We had to add in the string library and the stir compare function。 Stir comp SC。

 It was just a lot of work to do something so darn common。

 It is super common to want to compare strings in Python wonderfully。

 let me close the intbased version from C here， let me propose here。😊，That in Python。

 if you want to manipulate strings， you could use C S 50's on get string function。

 but I don't even need that。 I can use the input function。 As we saw earlier。

 So if I want to prompt the user for S equals the return value of input and just prompt them for a string like S T equals the input function。

 Pro them for a string called T in Python wonderfully， it works the way you would hope。

 If S equals equals T， then print out quote unquote， Sam else， print out quote unquote different。

 So here again， it just works the way you would hope and you don't have to pull out your textbook or your old examples to figure out how to do something relatively straightforward conceptually is comparing to strings。

😊，Let's do one other example that evokes a past example as well。

 Let me open up a program that in week1， we called agree dot C。

 So at left here was a program that we wrote several weeks ago now that use the C 50 library。

 the standard I O library， It use the get cha function to ask the user。

 Do you agree with some terms and conditions or whatever。 and then we used this syntax。

 which was very new in week1， because not only we we' were using equals equals。

 we used the vertical bars， which meant what logically So or so we used or to detect if someone typed in uppercase or lowercase for either y big y little y or big n little n as well。

 So in Python， let's do this instead code of agree dot pi I'll hide my terminal window。

 but I'll drag this here over at left。 And in the python version of this。

 turns out I can do something similar as follows。 let's do S equals input and prompt the user Do you agree。



![](img/bbd185be7f30ef08483a327402859508_45.png)

![](img/bbd185be7f30ef08483a327402859508_46.png)

，Then let's say if S equals equals quote unquote y or S equals quote unquote little y。

 then print out quote unquote， agreed， just like in the C version。

L if S equals equals capital and or S equals equals lowercase and then print out not agreed。

 just like in the C version。 And here again， we're sort of seeing just how much this condenses our code。

 It's working logically the same。 But what are some of the differences visually。 Well。

 there's no curly braces， There's no semicolonons。 There's new new lines。 But what is there。

 like this is why Python2 is considered more user friendlyendly。

 If you want to express the idea of or。 we' like literally write or instead of vertical bars and double ampersands and the like。

 So I'm using or here as well as or here。 Not there's no parentheses either around these conditional。

 So we' we didn't see those on the slides， we don't see them here。

 what Python does with parentheses is that if you don't need them logically to combine Boolean expressions。

 just don't use them at all。 You could use them here and here and here and here。

 But if it's not necessary， Why bother further cluttering your code。 You simply do not need to do it。

 But let's see if there's a way to improve。Let me first run this and make sure it works as intended。

 Python of agree dot pi。 Do I agree in emphatic， Yes， Okay。

 let's do in a lowercase N and agreed and not agreed are indeed the answers I get back。

But this feels a little redundant， I would say， Notice that my code here is really just asking the same question twice。

 albeit for lowercase。 and it's asking the same question twice here。

 albeit for lowercase for the N as well。 Well， turns out in Python。 I can actually tighten this up。

 Let me get rid of my C version and focus on this one。

 And let me go ahead and condensed this further as follows。 If S is in the following list of values。

 quote， unquote， why。Qu unquote little Y colon。 And then down here。

 I'm gonna do the exact same thing。 logically。 L if S is in this list of comma separated values。

 capital N lowercase N。 this now would achieve the same results。

 It's a little tighter because I'm not using or I'm not using equals equals four times。

 I'm using it not at all， in fact， I'm using a new keyword。

 which in Python exists in as a preposition is a Python keyword does not exist in C。

 But this here would be a little tighter as well。 So let me go ahead and run Python of do pi enter。

 do I agree， capital Y， it still works。 Or if I do lowercase Y， it still works。

 But this isnt as featureful as would be ideal。 because what if the user types in for instance。

 an emphatic yes， in all caps。 Well， now it just ignores me all。 Now you could go in and of course。

 address that， I could do capital yes， and lowercase， yes， but wait a minute。

 What if they just capitalize the first letter。 So I should really have Y E S。

 And then what if they like caps lock is not working as intended and maybe we do something like this。

And now we've got to do this。 I mean， these are all like spelled the same。

 even if they're miscapitalized。 So this just feels like it's becoming a mess pretty quickly。

 So logically， whether it's in C now or in Python， what would ideally be a better logical solution to this。



![](img/bbd185be7f30ef08483a327402859508_48.png)

Then enumerating all possible values that we care about， yeah。Yeah。

 why don't we just change the user's input to lowercase or equivalently。

 just change it to uppercase to canonicalize it， like make it the way I expect it to be and then compare it against a much shorter finite list of values。

 So how do we do this。 Well， in C in the C type library， we had a two lower function。

 which was handy and we had two upper， but in Python， what's nice。

 is that Python actually has not only stirs or strings as first class objects that come with the language itself。

 Python itself as a language is known as an object oriented language。

 and it has other features as well。 And some of you in high school if you ever studied Java or the like you might already know about object oriented programming。

 otherwise known as O P， And what this is sort of referring to is a new and improved version of Cstructs。

 recall that in C， we hadstructs whereby we could create our own data types for like persons or nodes。

 for instance， by creating our own data types that have one or more other values inside of。Well。

 what C doesn't offer you， at least not easily is to associate functionality with those structures as well。

 For instance， for a person object， wouldnn't it be nice if there were a function。

 especially if you're running the code on your phone that was a call function that would just automatically call that person or an email function that would just automatically email that person if we're keeping track of their email address as well。

 Well， you could implement a call function and pass the person in as input you could implement a call function and pass the person in as input and then it would work but wouldn't it be nice to sort of associate more tightly and encapsulate related function。

 just like we've been encapsulating related data， And this is what objectoriented programming allows you to do instead of having what are calledstructs in C。

 you have what are called objects in Python and certain other languages as well And those objects are typically define what's called a class when a class is really just like a blueprint or a template out of which multiple objects can be made and specifically。



![](img/bbd185be7f30ef08483a327402859508_50.png)

The context of this here example， we could consult the documentation for the functions that come with the stir object。

 the string object。 And technically， whenever functional is associated with the specific data type。

 It's incapulated inside。 It's still a function。 but you technically call it a method in that case instead。

 So a function is what all we've been discussing in C and in scratch in Python。

 you still have functions。 But if those functions are associated with a data type tucked away inside of them。

 then they're just also called methods。 It's a minor nuance there。 And among the functions。

 among the methods rather that comes with stirs or strings is a little something called lower。

 And there's different ways to go about doing this。 So let me go ahead in one。

 simplify this list to just be the list of values that I actually care about。

 So let's suppose that I want to support quote unquote， why and quote unquote， yes。

 But I don't care about the capitalization thereof。 So I could do this， I could take the S variable。

And I could actually actually let's do this。 I can create another variable T set it equal to S dot lower open perend close per end。

 So notice the dot operator， just like in C， goes inside of the object。 same thing in Python。

 But here， I'm not going inside of it to get the person's name or their number or their email address。

 I'm going inside of it to call a method that just comes with that type of value。 So in C。

 just to be super clear， we would have done to lower and pass in S Python in an object oriented programming more generally。

 just kind of flips that paradigm and says start with the variable in question and call its own lowercase method as such。

 And now if I change this code to T down here and here。 and I go in here。

And I search for lowercase N or lowercase N O。 And I run this version of a agreed dot pi enter。

 I can now type in y for yes capitalized y for yes lowercase。 Y E S all capitalized for yes。

 Y lowercase capital S like that。 Any of those variants that exist。

 And I only have to enumerate canonical versions thereof Even better。

 I can kind of tighten this up further。 I don't really need a t variable。 In fact。

 I could just do s equals s dot lower and change the value of s to be the lowercase version thereof。

 What's nice about Python2 is you can chain method calls together。

 So if you know that input as a function already returns a string。

 You don't need to tuck it in a variable before you call that strings lower method and you can just chain them together in this way。

 And you could do this sort of again， And again， this is not a real function。

 but you could keep chaining these things together one or more times at some point。

 it's gonna look stupid because this is gonna be too long of a line of code。 And then we。

Into discussions of style。 But for now， having two function calls like this is pretty reasonable。

 I would argue。 And so this just tightens up the code further。😡，Alright。

 so that is perhaps the newest feature that we've now seen of Python， this notion of methods。

 which derives from this feature of object oriented programming。

 But any questions before we take a quick tour of a few other features as well。 now okay。

 how about a couple more examples then introduce some loops and we'll skate our way toward some snacks and just a few。

 All right， so let me propose that we look at one other problem from our week 4。

 where in memory And the fact that it exists and has to be management by us was creating some underlying problem。

 So let me open up a program from week 4， that was called copy 5 dot C。

 at least that was our several iterations in。 And that program looked a little something like this。

 And I'll just skim it for a second。 like this was getting kind of annoying just to copy one string into another。

 So I had to use all of these libraries and C， I use C 50s get string function still。

 but this is when we took the training wheels of strings off。

 quote unquote and started talking about them as cha stars。😊，I check to make sure that S is not null。

 just in case we're out of memory。 for some reason。

 I use malloc ultimately to create more memory to get more memory for the copy。

 but still checking if it's null。 I then copy the string from one to the other using stir copy。

 I then made sure the string was long enough。 And then I uppercase the first letter in it。

 Then I printed them out。 Then I freed the string and so forth。

 Like it was a lot of work just to make a copy of a string， which in programming in general。

 youd be it'd be nice。 if you could just do it more simply。 So in Python here， too。

 it's as simple as that。 let me go into V S code， open up a new file called copy dot pi。

 Then let me put these two side by side。😊，And in the right hand version in Python， let's do this。

 S equals input and prompt the user as before for a string like S， quote unquote。

 Then let's go ahead and create a second variable called T。 set it equal to the S variables。

Capitalize methods， return value and then print out down here。 How about S， and then print out T。

 Let me open my terminal。 Let me run python of copy dot pi recall that last time when I did H I exclamation point。

 it capitalize the whole thing as I recall， as opposed to capitalizing just the first letter。

 enter this time， it works as expected。 Now， the print is technically a little different down here。

 I use these format strings。 So if I really want to make this identical。

 I can do F quote unquote S colon， and then plug in the value of S with curly braces。

 F quote unquote t colon T。 This looks uglier， but it's just now printing out prefixes here。

 S and T respectively。 So if I run this again and do high in all lowercase。

 it capitalizes it correctly for T and only for T。 So here more so than ever。

33 lines of code at the left6 lines。Of which are blank。At right， in Python。Questions。About this here。

 example。啊，呀。Those blank lines， do you mean， get rid of the blank lines。 Oh you absolutely could。

 I have been doing this visually just to kind of make related chunks of codes stand out。 So I got S。

 Then I capitalized T。 and then I printed them both。 But， yes。

 you could totally format this in different ways。 Just as I did at left as well。 Other questions。

About what we've done here。No， all right。 How about this， Let me propose that in C。

 we also at one point， tried to just uppercase everything in a string。

 So let me open up what was a program called from week to uppercase dot C， really。

 version 2 thereof here。 And this was a program that looks a little cryptic。

 but all it does was ask the user for a string the before version。

 it then print it out after colon as just a placeholder for in uppercase version thereof。

 we then use Stling and this four loop to iterate over all of the characters in the string。

 and then one at a time， we use the C type libraries two upper function to capitalize them again and again。

 So you can probably imagine where this is going。 We don't need two upper anymore。

 we can just use dot upper in some way。 But we do need to have the ability to do things with loops。

 So in Python， we still have loops。 but the syntax is gonna be a little different and frankly。

 a little easier ultimately。 So in scratch， if you wanted to repeat something three times like this。

 you could implement it in C very。😊。

![](img/bbd185be7f30ef08483a327402859508_52.png)

![](img/bbd185be7f30ef08483a327402859508_53.png)

ically， so to speak like this， create a variable I incremented with plus plus again and again and again。

 So long as it's less than three printing Yaow each time in Python。

 you could do the exact same thing if you really want by saying variable equals value。

 but no semicolon， no data type while I less than three colon。 So just like conditionals。

 You don't need parentheses if they're not logically necessary。

 but you do need the colon and you do need indentation。 you don't have the plus plus。

 So we have to do the slightly more verbose Python version here。

 but that's exactly the same idea to implement meowing three times supposeose， though。

 that we wanted to take a different approach here。 we could in C use not a while loop。

 but a four loop。 And maybe you're nowadays in the habit of using these a bit more。

 They're a little more succinct without all of the vertical clutter。

 but this is how we could implement the same in C。 in Python。

 it's not quite as obvious how to do this， but we could do it this way。

 We could say for I in the following list of values。

 And literally in square brackets as I did earlier。umerate one after the other。

 the things I want to check for。 instead of why and yes and no and N。

 I can iterate over three values。 This is fine， but just allow your mind to kind of wander if it hasn't already into thinking how this could get us in trouble。

 Like， why is this approach of just enumerating0，1 and 2。

 Probably not the best way long term to do this。What do you think，Yeah， you really gonna go。

 what if you need a lot of values。 like 100 of them， are you really gonna do0， comma 1。

 comma 2 comma 3 dot dot dot to comma 999。 like that's got to be a better。

 There's got to be a better way than that。 If only because it's gonna wrap around the screen。

 I'm gonna mis and screw something up。 So indeed， there is you can alternatively use a function in Python called range。

 which does as I said earlier， give you a range of values。

 And if you want a range of three values starting it0 by default and going up to。

 but not through this value， you literally call the range function and say how many values do you want。

 And essentially what the range function does is it hands you out one value at a time more efficiently than the hardcoded list。

 which puts them all in memory at once。 range is a little smarter and it knows how to give you just one value at a time。

 But notice here， I'm using four I in range of three。

 which is similar in spirit to C because I have this variable I。

 But I'm not actually using I anywhere。 Like I'm not incrementing it。

 I'm not comparing it against a value， So strictly speaking in Python。 This。rrect，But stylistically。

 some people would actually， by convention， change the eye to just an underscore character。

 which is a valid character for a variable。 but it's just kind of this visual indicator that yes。

 this is variable because the loop requires it in Python。

 But who cares what it's called because I'm never actually going to use it。

 So you'll see this convention sometimes but perfectly reasonable to also use I by convention because I means integer。

 and that's really what's happening anyway。 But just FYi， a convention there in Python。

 So how can we now use these loops in some actual code will let me propose that what we could do here is the following。

 let me go back to B code here in my uppercase version and let me quickly whip up a python version that achieves something quite similar。

 Let me go ahead and run code of uppercase stop I at top left after dragging this over。

 Let's go ahead and implement the following a variable called before said it equal to the return。



![](img/bbd185be7f30ef08483a327402859508_55.png)

of the input function with quote unquote before as the prompt。

 Then let's just do a placeholder of quote unquote after colon space space。

 So they lined up in terms of numbers of letters。 close comma。

 But let me do end equals unquote because I don't want a new line to move the word below the word after。

 So this is just a silly aesthetic detail。 But that overrides the default new line to being no new line。

 Now let's do this in Python。 instead of using this convoluted for loop。

 and the semicoons therein in this constant checking of a conditional。 I can actually just do this。

 for every character， call it C， in the before string。

 go ahead and print out that character uppercase like that。 But don't print out a new line yet。

 until we get to the very end， go ahead and print a new line by printing nothing。 But by default。

 I'm gonna get a new line。 So passing nothing in gives me one new line。 and that's it。

 So let me open let me open my terminal， run Python of uppercase do pi H。

IExlamation point in lowercase， enter。And I've messed something up。Not intentional， but so be it。

Notice the error here。 So this is， I can make this work。

 So there's these things in Python called tracebacks。

 which kind of trace backwards what you did wrong。 And in this case， what I did wrong。

 as per all of these carrot symbols is C dot uppercase is bad。

 But you probably already know that from earlier。 Which I should have typed。So dot upper。

 So there's a lot of distraction here。 but much like clang's output。

 there is some helpful information  One。 the file in question is uppercase dot pi line 4 is where I made the mistake。

 So even though the output is different from clangs， it is similar in spirit specifically。

 I messed up an attribute error because some string object doesn't have an attribute that is a method called uppercase。

 Allright， well， that's an easy fix， as you noted， I should have written C dot upper。

 delete delete delete。 And now let's clear my screen。

 rerun Python of uppercase dot pi enter H exclamation point。

 and there we have the after version thereof。 But even here， note that in Python。

 I'm doing even more work than I need to。 This is indeed how in Python。

 I can enumerate all of the I can iterate over all of the characters in a string like there's no eyes。

 There's no there's no conditionals。 Python will just on every iteration。

 update the variable C to contain one letter than the next than the next than the next。

 It just sort of works。The way you would hope。 But in Python 2。

 recall that you don't have individual characters anyway。 So technically。

 I'm kind of wasting my time by doing this one string of size 1 at a time。 again and again and again。

 I can tighten all of this up here。 And I can just， for instance， do this。

 I can go ahead and print out。For instance， before dot upper and just uppercase the whole thing all at once。

 And then I could technically get rid of the new line。 But now I'm just wasting my time， too。

 Let me get rid of all of this。 Let me go over here and let me output， for instance。Let me output。

 let me create a variable called after equals before。Dot upper。

 that's gonna store in the after variable exactly what I want all at once without even using a four loop。

 And now I can print out as before a for an F string， saying after cone space space。

 and then value of the after variable。 So this， if I run it again。

 Python of uppercase dot pi enter high in all lowercase， enter that too now works。

 And one final flourish Str speaking， you can interpolate the value of what's returned from a function as follows。

 instead of even bothering with a variable here， I could put a modest amount of code inside of the curly braces。

 And I say modest because if this gets too long， it's just gonna confuse everyone， yourself included。

 But in this case here， I can run this one more time type in high in all lowercase and that too now works。

 because I'm formatting it as an F string。 So in short。

 I'm just getting more and more features at my disposal that I can now use to solve some of these same problems。

 So that there was a lot， let's go ahead and take a 10 minute break with some fruit by the。😊。



![](img/bbd185be7f30ef08483a327402859508_57.png)

And we'll be back with more complicated problems。 Alright， we are back。

 So let's go and use some of this new syntax to actually make a meowing cat albeit textually in Python。

 So back here in V S code， I'm gonna go ahead and create a program called Miow dot pi。

 And let's first do it the super simple way。 If we want the cat to meow three times like let's literally just do that in code。

 So print quote unquote Miow。 And we get the new line for free。

 And then I'm just gonna copy paste this again。 And again， it's just gonna give me three such lines。

 Python of Mio Pi enter。 And there we have it。 A cat that Miaow is three times。 Of course。

 this is correct， but not well designed because what should I obviously be using instead as a feature of any language。

😊。

![](img/bbd185be7f30ef08483a327402859508_59.png)

Instead of three copy pastted statements， probably like a loop of some sort。

 So let's borrow some of the inspiration from those previous slides。

 Let's go into Miowa pi and change this to use maybe a while loop initially。 So how about I equals 0。

 Then while I is less than3。 go ahead and print out Miow。

 And then let's go ahead and do I plus equals1， which is the quick relatively quick way to do that in Python。

 but not without not like Cs plus plus Python of Miow pi enter okay。

 so correct and better designs now， how else could I do that， Well。

 we saw earlier that I could do4 I in 0，1，2 colon， And then I can do print quote unquote miow。

 that two would work if I rerun python of Mio pi that works， but notice I'm not using I and indeed。

 I'm not using0 or1 and 2。 So technically， I could do something like quote unquote cat dog bird。

 I just need three things to enumerate over。 And that too is gonna give。😊，3 meow。 So to be clear。

 the square brackets， much like in C are giving me a list of values， but it's not an array。

 it's indeed a Python list。 And as we'll see over time。

 a list in Python is nice versus an array in C because list in Python can grow and shrink automatically for you。

 So not only are they linked lists of some sort underneath the hood。

 you do not need to worry about resizing them anymore。 But of course， as we saw before the break。

 we should probably just do this more dynamically。 So for I in the range of three values and let Python generate those for me。

 if I rerun Python of meow up I still get three values， but here too stylistically recall。

 we said that you don't really need the name of the variable if you're just gonna do something three times without ever touching that value。

 So we could just use an underscore by convention， which just kind of looks like there's no variable there。

 even though there， in fact， is。 but let's build on this and actually now introduce and really revisit the ability to define our own functions。

 which we've seen in scratch， we've seen in C。 And I technically。😊。

Ar of class used that to implement my own spell checker in dictionary dot pi。 I use death。

 which stands for define。 And that's how I defined four functions identically named to problem set 5s。

 Well， let me go ahead and do this and implement an abstraction for Yaowing。

 much like we did in scratch， much like we did in C。 Let me go ahead and define a。F called Miow。

 whose purpose in life is simply for now to print out， quote unquote Miow。 And now let me use that。

 Let me go ahead and do something like before。 So for I in range of three。

 go ahead and call Miow like this。 I think that's gonna get the job done。

 Python of meow pi enter And indeed， it's still working exactly as I expected。

 But recall from our discussion of C， we generally stylistically encourage you to put your main code at the top of the file。

 if only because that's the entry points of the program。

 If you want to wrap your mind around the code in there。

 it makes sense to start with main instead of random functions like Miow at the top of the file。

 So let me actually kind of practice what we preached in C。 let me move this Miow function。

 just to the bottom of my file so that it's sort of out of sight out of mind because now that it's implemented。

 It just exists。 Let me go back to V S code at my terminal in V S code run Python of Miow again。

 and hit enter。 And there's one of those trace backs a different one this time。 This time it's。😊。



![](img/bbd185be7f30ef08483a327402859508_61.png)

Name error instead of an attribute error。 But where did I go wrong， Apparently， M。

 E OW no longer exists by nature of having moved it from top to bottom。 So intuitively。

 even if you're new to Python， why might that be。Yeah。Deine it。Yeah， exactly。

 I need to define it before I call it very similar to C whereby at least in C。

 we have that little trick of just copy pastsing the prototype of the function。

 just to borrowing its very first line。 Python actually doesn't use that mechanism instead。

 Python has a different convention instead technically in Python。

 you do not need a main function clearly from all of the programs I've written。

 it just works without a main function。 But if you get yourself into a situation where you're defining your own function。

 but the order in which you define them and then use them clearly matters。

 you might as well go ahead and implement a main function after all。

 and the convention would be to do this literally defined with the de keyword。

 a function called main that doesn't need to take any argument。

 And then inside of that main function put your actual code indentation in Python matters。

 And so I've hit tab to indent everything all at once。 and now I have a main function。

 So it would seem that maybe now the problem is solved by just introducing main。 So Python。



![](img/bbd185be7f30ef08483a327402859508_63.png)

Out up high， enter。O， it's solved in the sense that I'm not seeing an error message anymore。

 but explain to me intuitively why I'm not seeing anything at all， yeah。I didn't call main。

 So it's sort of like we're taking a step forward， but then another step backwards here in the sense that Python doesn't come with a main function support for a main function by default。

 So if you invent it yourself the onus is on you to call that function。

 So this is gonna look a little stupid。 but the convention in Python is indeed at the very bottom of your program if it's contained in a single file is literally call main at the very bottom。

 So now I'm gonna go back to VS code， I'm gonna rerun Miow do pi。

 and now I get back the functionality。 but I don't get an error message either。 Why Well。

 in this case， on line 1， I'm defining the main function as follows On line 6。

 I'm defining the meow function as follows。 I am not using either of those functions for in actuality until line 10 calls main。

 which then calls meow。 So I fixed my sort of order of operations。

 So it's fine for main to be defined above it。 So long as I don't actually call Miow until I've defined it as well。



![](img/bbd185be7f30ef08483a327402859508_65.png)

![](img/bbd185be7f30ef08483a327402859508_66.png)

So this defines main， defines meow and then actually calls main。

 So this is a nice way in Python to sort of avoid what could be a very complicated design problem by just defining our own functions。

 including one called main strictly speaking， it doesn't even have to be called main。

 but it would be frowned upon as a matter of design as a matter of style to call it anything other than main。

 even though that has no special meaning beyond convention。 Well， let's make one tweak here。

 just ast see just is in scratch。 It would be nice if Miow actually took an argument。

 which is the number of times I want to meow。 So let's assume that that functionality exists by calling nowow of three。

 as the input to that function。 But how do I now change the definition of meow。 Well。

 just like and C， you put inside of the parentheses when defining the function a comma separated list of one or more of0 or more parameters。

 and I can call it anything I want， I'll call it n for number of times。

 I don't have to specify int because we know that already。 But in now this loop。

 I can do4 I in range。😊，Of n， it doesn't have to be 3。 It can be n as a variables value。

 then indent this line so that it indeed iterates n times printing out Miow in this case。

 If I run it again as Python of meo up pi enter now I see Mio Mio Miow。

 But this is arguably the best designed of my versions thus far because it is indeed parameterizing how many times I'm meowing。

 Now， as an aside， especially those of you who might have used Python before。

 or might go on and look at tutorials in such for Python itself as a language technically the conventional way to call main is with this weird syntax。

 if underscore， underscore name， underscore underscore equals equals quote unquil， underscore。

 underscore main， underscore underscore Col tab。 we don't bother doing this in most of our class examples because it doesn't actually solve a problem that we ourselves will encounter and is just really hard to remember in confusing to read。

 but you will see this in the wild in the real world and long story short， this syntax。

Line 10 being added solves problems where you're implementing not your own program per se。

 but your own library We your own library that may very well have its own main function。 But for now。

 I'm going to wave my hand and make that go away and keep it simple because this is the juicy idea for now。

😡，As an aside， there's other ways to have loops in Python that's worth noting。 So， for instance。

 in scratchra， we had this forever block saying meow again and again and again without ever stopping and C。

 maybe one way to do this was like this like while true， because true is always true。

 So this conditional is always true。 So it's just gonna print endlessly in Python。

 the syntax is roughly the same while true， but capital T and capital F for false。

 this too would achieve the same result。 And so just to demonstrate though a very common mistake might be to have some kind of infinite loop in your code。

 that might happen just the same in Python。 So if I go back to Mio up pi。 And just for kicks。

 I simplify this too literally just while capital true call in print quote unquote miow。

 you could get yourself into some trouble here by running that code。

 And it just seems to meow endlessly how do I get out of this situation。

 besides like reloading my browser and closing the terminal。 What's more elegant way。Yeah， control C。

 So control C for interrupt will cancel what's going on there。 just like and C， this， though。

 does not mean there's an error in your code。 C did not do this。

 Python does show a keyboard interrupt error， if you will。

 but that's because you literally interrupted the program while it was running。

 this doesn't mean there's a problem in your code if you simply interrupted it because you lost control over the thing。

😡。

![](img/bbd185be7f30ef08483a327402859508_68.png)

![](img/bbd185be7f30ef08483a327402859508_69.png)

Alright， so what are some other issues we can perhaps now revisit together。 So in the world of C。

 recall that we ran into issues of truncation。 whereby if we did integer math。

 Its like one divided by3， that would give me ideally in the real world 0。3333333 forever。

 But it ended up coming out as 0 in C as well。 So let's see what happens in the world of Python now。

 And I'm gonna move away from showing left and right C and Python for now。

 Let's go ahead and just focus on the Python code。 So let's try this。

 Let me go and create a new program。😊，After closing the out pi called， say calculator dot pi again。

 let me throw away the relatively simple code earlier that simply attitude numbers together and let's do some division now。

 So let's do x equals int passing in the input asking for an x value like this。

 Let's do Y equals int input passing in a Y prompt like that。

 Then let's do a variable called Z equals x divided by y。 And then let's print out Z。

 So this is actually very similar to something we did weeks ago。

 in C when we first tripped over this issue。 Let me run python of calculator do pi type in one for x3 for y。

 And it would seem as though truncation is not an issue in Python by simply using the slash symbol for division。

 turns out there's another symbol you can use in Python。 If you want to get back truncation。

 You can do slash slash， which is not a comment。 It actually means do division like the way C used to do it。

 But in Python probably for the benefit of all of us。A globalloly division works as you would expect。

 and you get back， in fact， this here value instead。

 What about another issue we saw in C that a floating point in precision。

 whereby even though somethings supposed to be 0。3333333 infinitely many times it seemed like remember like grade school was lying to us because there were weird numbers in even a fraction like one third。

 Well， let's try this out in Python， let's go back to my here calculator。

 and I only need to make a slight tweak here， for instance。

 though the syntax is gonna be a little weird here。

 And instead of just printing out Z to some default number of significant digits。

 let's actually format the string as follows。 And this is not syntax， you'll need frequently。

 but in Python， you can use an f string by doing f quote unquote something。

 and inside the double quotes this time。 instead of just doing Z to print out and interpolate the value of z inside of those curly braces。

 let's specify that yes， I want the value of Z。 but I want to print it to like 50 decimal places as a floating。

Point value。 I have to Google this syntax all the time to remember what it is。

 But this is saying exactly that。 Show me 50 significant digits in this here number。

So let's go back to my terminal。 Python of calculator do pi enter13 should get 0。

33 repeating forever。 But of course， we do not。 So unfortunately。

 Python does not solve all of our problems。 Flo point in precision is still an issue。

 Does that mean you shouldn't use it for scientific computing for financial computing and go like。

 no， there are libraries that you can use thirdpart code that sort of addresses this kind of concern。

 but you still need to be mindful of the fact that these problems still exist。

 And either you or someone else still needs to handle something like this。

 What about something like integer overflow。 Well， wonderfully。

 in Python integer overflow is not a thing recall that in Python and C， if you use an int of 32 Bs。

 It's eventually gonna overflow and go negative or go back to 0 once you count beyond like 2 billion or 4 billion。

 depending on if you're doing negatives or not。 You could use along and C， which gave you 64 B。

 which means it's still gonna overflow， but probably after we're all debt。

Because the number is going to count up much， much， much higher。 unfortunately， well， fortunate。

 in Python， you don't have to worry about in， you don't have to worry about long。

 it will just allocate more and more bits for you automatically secretly underneath the hood。

 so you can just iterate from zero on up toward infinity and the program will run theoretically forever without ever actually overflowing the int。

 So at least integer overflow not a problem。 But there are problems that might still happen。

 And let's explore how there are new mechanisms in Python and languages like it that we didn't have in C。

 So in particular， let's introduce something called exceptions。

 which is sort of a concept and a feature that's worth understanding so that you'll encounter it not only in Python。

 but also likely in the real world。 And let's do it as follows。 Let me go back to VS code。

After closing my calculator and let me go ahead and open up a new program called integer dot Pi just to play around with integers。

 And let me go ahead and do this。 Let me first prompt the user for number N。

 set it equal to the return value of input by just asking them。 whoops in between quotes。

 a prompt of input。 Like， I really just want them to type a number。 but maybe they won't。

 So let's see what happens。There are ways now to detect if the human has typed in not only a string。

 but a numeric string like one or three or something else。

 I can simply use a conditional in Python pretty easily in C。

 I would have to do this pretty much character by character by character in Python。

 I can do it the whole string at once。 If N dot is numeric open per end close per n there using a method that comes with all strings in Python that will just tell me true or false。

 This whole thing is numeric or not。 Then I can go ahead and print out。 for instance， integer。

 just concluding that this the here thing is an integer else， if it is not all numeric。

 I'm gonna go ahead and print out not integer， quote unquote， Let's try this out。

 Let me run Python of inte droprop pi。 I'll type in one。 That's an integer。 Let's run it again。

 type in3。 That's an integer。 Let's run it again。 type in cat that is not an integer。

 So it seems to work at a glance。 But how else might we go about doing this。

Especially if so that we don't have to litter our code with all of these darn conditionals every time。

 I'm just trying to get an int。 I don't want to resort to the CS50 library ideally。

 I don't want training wheels， but I want to do this。 The Python way。

 and there's a word for that The pythonic way。 So that too is a term of art。

 which means there might be different ways to do it。

 but do it the way where a majority of people out there would probably agree with you Pythically。

 Allright， so let's do this。 Let's just instead of bothering with the conditional。

 because this is kind of annoying that one line of code really becomes4 all of a sudden。

 Let's just go ahead and proactively convert what the human types in to an int as I did before to fix the 12 problem。

 Let's run Python of integer pi enter。 Let's do one enter seems to not make any errors。

 Nothing bad happened。 Let's type in3 that there works。

 Let's type in cat and that throws one of those tracebacks where the trace back itself is not the error。

 but it's diagnostic information。 that's trying to help me figure out where I screwed up。 A。

Icred up somewhere in this whole thing。 And this is a little cryptic， but this is a value error。

 something I screwed up a value here。 In literal for int with base 10 cat。

 So that's a very verse way of saying by default。 the int function assumes base 10 Aka decimal。

 and doesn't understand cat。 So it's just not working on cat。 So how do I solve this。 Well。

 notice what's happening here。 simply trying to convert cat to an integer is not just returning some special value like 0 or negative1。

 Like it's literally terminating my whole program。 And this is different from C。 recall that and C。

 the only way you could signal errors that we've seen is that you have to return a sententinel value like 0 or negative1 or positive1 or null or whatever Like you have to know in advance what special value is going to come back。

 But there's a problem with integers in particular。

 S that the int function was defined in its documentation as printing out as returning0 if anything goes wrong。

You could check for0。 So if n equals equals 0， then you could say print not integer because according to the documentation。

 I'm pretending exists。 that is an invalid value。 Of course， where does this get me into trouble。

 If I run Python of integer pi， type in one， We're good。 typey in 2 were good， type in 0。

0 is not an integer。 But I'm pretty sure it is。 So there's a problem whereby if you're relying on return values to signal that something went wrong。

 you have to sacrifice a potentially valid value。 And that's fine。

 But you're gonna have to pick a number， It's got to return 0， negative 1 positive 1。

4 billion negative 4 billion like you've gotta pick a lane。

 and that's unfortunate because you're sacrificing some value unnecessarily。 So what Python does。

 And with other languages do is instead of returning some sentinel value that means something went wrong。

 they just throw up their hands。 So to speak， they throw an exception。 and an exception by default。

 Just terminates the program。 because something un happen。 something。Or in this case。

 exceptional is a bad thing。 Something exceptional happened。 So how can we handle this。

 How can we actually detect that something has gone wrong？ Well。

 turns out this is sort of kind of encouraging。 you can try to do something instead in Python。

 as opposed to just blindly doing it。 So if I go back into V S code here， and I try to do that。

 let's do the following。Ideally， I want the end result to look like this。 print integer。

 if this thing works。 And so to be clear， let me run this once more。

 Python of integer dot pi 1 is an integer。2 is an integer。 Cat， not an integer。

 but I'd like to see not integer and not some crazy message on the screen。 So how can I fix this。

 Well， let's do this instead。 Please try to do all of this。

 except if there's a value error as I know can happen because I just experienced it。

 then go ahead and print out not integer， quote unquote。

 So let me just give my grammar the same Python of integer dot pi enter one works。

Python of integer 3 works。 Python of integer Cat doesn't work per se。

 but it doesn't throw an error message anymore。 And that's scary traceback。

 I'm somehow catching the exception or handling the exception。 so to speak。 Now， as an aside。

 there's slightly better way to do this would also be as follows。 General speaking。

 It's considered a bit lazy and bad design to put more lines of code in a try statement than you strictly need。

 because imagine a program has like 30 lines of code。 Maybe it's your whole pieceet problem。

 And you know， you're occasionally getting those traceback errors on the screen。 You know。

 sort of a bad student， for instance， would just put everything in the try block and like literally just try to do your homework。

 And if there's an exception， then you just catch it at the very bottom。

 Like that's frowned upon because there's just bad design。 when you're trying to do something。

 you should really only wrap the one or more lines that will actually throw raise an exception inside of it。

 So technically。Print is not gonna fail。 Like， you can't screw up print when you're just printing out quote unquote integer。

 So weirdly， the try accept statement in Python also supports an else。

 whereby if there's not an exception， you can then do this statement instead。

 It's a little weird because we've only seen elses and conditionals。

 but you'll see this in the real world。 This， though， would achieve the exact same thing。

 but it's a little better because now the only line of code I'm wrapping is the one that can actually raise this exception in the first place。

 So Python of indt pi  one works。3 works。 Oh， wait。Oh， wait， that's completely logical。Does not work。

This is supposed to say integer， if it is not， in fact， an exception。 Sorry， user error。

 Python of intedrop pi 1 works。3 works。 Cat is caught， but therefore not an integer in this case。

 So long story short。 Why do we introduce this。 Well， one。

 these exceptions are actually omnipresent in higher level languages。

 And this is the way that many languages actually raise exceptions signal that errors has happened as opposed to reserving arbitrarily some special return value that you must check for。

 but you need to now try to do certain things except if errors happen。

 in which case you can catch them， So to speak in this way。 As an aside。

 how to C 50's get in function in our library work。

 We essentially are using try and accept inside of a loop that just keeps prompting and prompting and prompting the user for an actual integer until you oblige。

 And then we return that value in C 50's Python version of get ins。

 So we're using the same fundamental in there。Alright。

 let's try now a few familiar things here on stage inmage to the Python crawling on Mario's bricks here。

 So recall that a few weeks ago， we played around with something super simple like this in C。

 which wasn't syntactically as simple， But the idea was to print out a column of for instance。

3 bricks。 How might I go about doing this in code。 Well。

 let's see let me open up a new file called Mariio pi today。

 And let's just do it the simplest way possible， if I want to print three bricks I could do for I in range of three。

 and then I could print out a single hash mark to represent exactly that。

 I'm gonna get the new line for free， because that's the automatic default behavior for print。

 So if I run this， I get something that's a little underwhelm。

 but pretty close to the spirit of what I just hit here on the screen。

 What if though I want to prompt the user for the height of this thing just as we did in problem set one with the Mario problems。

 How can I make sure the user actually gives me a number I want。 Well let's go back to V code here。

 And just so that I。😊。

![](img/bbd185be7f30ef08483a327402859508_71.png)

![](img/bbd185be7f30ef08483a327402859508_72.png)

Have to implement all the try except stuff myself。 Let's go ahead and from C50's library。

 import the get in function that I've claimed exists。 And then let's do this while true。

 It turns out in Python especially It's actually pretty common to deliberately induce infinite loops。

 if only because Python does not have do while loops。

 recall that do while loops and C were super useful。

 because they guarantee that you do something while a condition is still true。

 And that allowed us to get user input at least once and maybe again and again and again and again。

 Python does not have a do while， but you can implement the idea of it by just saying start an infinite loop。

 that I'm gonna plan to break out of when I am ready， and I can do something like this。

 n equals gets int prompting the user for height here as a prompt。

 then if N is what I want it to be a value greater than zero as in problem set one。

 go ahead and break out of this loop。 So even though I don't have a do while。

 I can certainly deliberate。😊，get myself into an infinite loop and break out of it when I'm logically ready to do so。

 And now here I can do 4 I in range of n， which is just gonna iterate from 0 on up to that value and then print out a hash mark as follows。

 Let me go ahead and run Python of Mari pi。 typey in a height of3， and it still works。

 typey in a height of， say 5。 It two works。😊，By iterating five times instead of three as an aside。

 what are some modifications that might be germane here。 Well。

 if I want to import the entirety of C 50's library， I can indeed， as I said earlier。

 just import the library itself。But notice what happens now。 Python of mar up pi enter a traceback。

 specifically a name error。 get int is not defined。

 This is because Python actually solves a problem that C does not in C。

 we didn't actually encounter this because our programs haven't been too big。 But in C。

 if you include this library and this one in this one in this one。

 you will get into trouble if two people out there have named a function， the same thing。

 If they've typed up something the same thing。 There's no notion of scope when it comes to importing libraries and C。

 you will get name collisions And the solution is just don't do that。

 Don't use that library that conflicts with one you're using The human humans realize eventually this is probably not the best design。

 So they introduce the notion of name spacing whereby you can scope certain symbols to specific files in effect。

 And so there is a solution to this。 If you import the entirety of C 50。 That's fine。

 But you have to say that you want the function called get int that's inside of the C 50 library。

 So if I do C S 50 dot get int and rerun this now。Now， I no longer see that error。

 and I'm on my way again with the code。 And this just allows me to keep all of my get underscore something functions scoped to the C S 50 symbol。

 as opposed to importing them all into like the top level namespace where they're just essentially global instead。

All right， questions。About this， the new ideas here really being now infinitely looping deliberately until you're ready to break out。

See none all right How about this。 So we had these four like coins， question marks in the sky here。

 different in that they were horizontal instead of vertical。

 How we might we implement this in code instead。 Well， let's go back to Mario pi。

 Let's delete the vertical version we just did。 And there's a bunch of ways I can do this。

 But let's do it in a way that lets us play around with some new features of Python as well。

 for I in the4 I in range of， let's say4， though I could use a variable I want。 print out quote。

 unquote question mark。 And let's try this Python of Mario do pi enter。 This is， of course。

 buggy because they're coming out vertical instead of horizontal。

 So what's the fix there intuitively。😊。

![](img/bbd185be7f30ef08483a327402859508_74.png)

![](img/bbd185be7f30ef08483a327402859508_75.png)

我对我呀。Yeah， so add end equals quote unquote to turn off the new line by default。 That's close now。

 So if I run Mario do pi again， I get four horizontally， but I don't get the prompt on the new line。

 So I think I just need one extra print at the end， which does give me a default new line。

 So if I now run this one more time。 there we go。 Now we're back in business。

 So pretty straightforward pretty much the same as in C， albeit with Pyths more succinc syntax。

 but this is kind of cool。 What you could alternatively do in python， which we've not seen before。

 if you want to print something four times or some number of times。

 you can literally say print out a question mark four times。

 So multiplication is now used in the way that plus kind of is for concatenation。

 but this does something again and again。 Python of Mario pi。 And that too now works。

 doesn't really save us a huge amount of time， but it's kind of cool now that you can do these one liners so to speak that achieve a lot more functionality as well。

 What about this final example， we had from the world of Mario underground。

 which is like a three by three grid。 How could I do this in。😊。



![](img/bbd185be7f30ef08483a327402859508_77.png)

![](img/bbd185be7f30ef08483a327402859508_78.png)

Python instead。 Well， let's go back here and delete the version of code I had there。

 Just like and see， we can have nested loops。 So I could do something like4 I in range of three and then maybe4J in range of three using different variables deliberately here。

 let me go ahead and print out a hash mark with no line ending until we're at the end of that row at which point I do want a line ending the new line character there。

 So if I run python of Mario pi， I get a three by three grid。

 which roughly resembles what this thing here looks like。 Now， you don't strictly need all of that。

 because we can combine these ideas for better or for worse， if I go back to my code here。

 if I want to just print out three things， I could just do。

 let's say print quote unquote hash mark times 3 and allow me to have a new line there And if I run this version。

 which is a little tighter， I get the same exact thing too。 So where is the line。

 like which way do you do it， whatever is most comfortable to you。 And in fact， when I said earlier。

 that I was doing。😊，ingWhen I implemented dictionary dot pi using the fewest lines of code possible。

 that was just because I really wanted to distill it into the essence of the minimal number of lines of code。

 but I could absolutely have used some loops。 and dictionary dot pi。

 I could have used a little more verboseness。 But as we're seeing here， it's not strictly necessary。

 Python has even more syntactic sugar， if you will， that lets you achieve more stuff more succinctly。

Alright， how about now， some more on lists and dictionaries。

 just to dovetail with what we did last week。 We'll touch on some final features。

 too when it comes to command line arguments and using exit command。

 and then well end with a couple of fun examples that kind of ties this all together。 So in Python。

 we indeed have list， which are like arrays， but they dynamically resize themselves。

 So they're effectively link list that you don't need to manage yourself。

 It turns out the documentation for those or at this URL here。

 But that's discoverable via do Python org itself in particular。

 there's functions you can use on list like L L E N for short。

 which gives you the length of a list And C， it was up to you to keep track of the length of an array in Python。

 like in Java like in Javascript。 if you're familiar。

 you can just ask the list how long it is at any moment in time。

 So that's gonna make our lives a little easier as well。 In particular。

 here's some documentation for that length function。

 And let me take it out for spin by recreating some of our prior examples and code。

 Let me go back to V S code here。😊，And let me go ahead and create a program called scores do5。

 which just like our example in week2 sort of iterates over quiz scores or homework scores or however you want to think about scores in Python。

 I'm gonna give myself just in a list of three scores， same as in week 2。

 So scores equals square brackets，72，73，33。 So this is different from C in C。

 if you were initializing an array with values like these。

 you would actually use curly braces and a semicolon and the data type in Python。

 you use square brackets， no data type， no semicolon。 Okay as before， now。

 let's compute like the average of my scores。 So average。

Equals and here's another function that actually exists in Python's documentation。

 You can actually call a function called sum Pass in most anything that you can iterate over like a list passing in scores。

 and then divide by how many of those things there are like laying passing in scores there。

 And now if I want to print out the average， I can print out for instance。

 a format string that says average colon and then plugs in that value there。 I can try running this。

 Python of scores do pi。 and there's my average， as we've seen before weeks ago，59。

33333 with a little bit of imprecision thrown in for a good measure as before。

 But what's nice is that notice some just comes with the language。

 length just comes with the language， you don't need some knowing4 loop or a while loop just to figure out the average of these values by doing all of that math yourself。

 So that seems to be nice at a glance。 What else can we do with these here scores。 Well。

 let me propose that we could get them one at a time from the user instead of hard coding them。

 So let me do this。 Let me go ahead and from C。😊，Library。

 import get int just so you don't throw any of those exceptions by typing in cat or dog or anything not an integer。

 Let's give myself an empty list by just using two square brackets like that。

 And now let's go ahead and put things in that list as follows for I in range of three。

 if I want to prompt the user still for three scores for the sake of discussion。

 Let's prompt the user first score， putting it in a variable called score。

 setting it equal to the get in function， prompting them for the first score。

 But then let's put that score in the list in C this was a pan in the neck and C this was like what you had to do in problem set5 and build the darn length list yourself by iterating over the chains and appendending it to the end or to the beginning or something like that in Python。

 if you want to append a value to an existing list you do whatever that list is called scores in this case。

 you use a method that comes with it called append and you append that score andvoil like Python takes care of it for you putting。

At the end of the list。 Now， outside of that loop， let me calculate the average， just as before。

 the sum of those scores divided by the length of those scores。

 Then let's go ahead and print out an F string that says average colon。

 and then interpolates the value of that variable。 Now， if I didn't screw up， let's try this again。

 Python of scores do pi 72，7333， which are now per that four looping added to the list and then the logic is exactly the same。

 So way easier than it would have been in seed to navigate or manage all of that stuff for me。

 There's another way to see this syntactic sugar， if you will， if you don't like this syntax。

 whereby you are adding to the scores variable， a new score by app pending it using the built in aend function or method that comes with any list in Python。

 you can also do this。 you can set scores equal to。😊。

The existing scores list plus another mini list containing just that score。

 Or I can con this a little further and say plus equals score。

 So it turns out plus is overloaded in Python in the sense that it's not a concatenation per se。

 like for strings， but it's append。 you can append more and more things to a list by concatenating two lists together in this way。

 So again， achieves the exact same thing， but maybe you prefer the syntax。

 if only because it's a little more concise。 So in short。

 like lists are wonderfully useful in this way。😊，Questions then。On this here feature as well。

We're essentially just like solving past problems more easily is the theme， hopefully。😡，Okay。

 how about one other problem When we implemented like a phone book back in week 3。

 Let me go ahead and do this in V S code。 Let me clear my terminal and close out scores do pi。

 and let me go ahead and create a new program called phone book dot pi。 and in this。

 let's write a program that just iterates over some names looking for one that I want。

 So maybe I have an list called names set it equal to three of us as in week3。

 So Ulia and David and maybe John Harvard like this， all three strings。

 Then let's go ahead and prompt the user for specific name using Python's input function or our get string method function。

 prompting them for specific name。 And now let's do this old school with a four loop for each name in names。

 and I'm just keeping it short and for names and for each name。

 if the current if the name I'm looking for equals the current name that I'm iterating over then print out found as we did weeks ago and then break out of this loop because I'm done。

😊，And let's see what happens here。 So Python， a phone book do pi。

 let's search for my own name D VD enter and David's name is found。 So that's kind of handy。

 Let's do this once more。 search for John John is now found。 Let's search for say another name。

 but let me mistype it maybe like Uah in all caps I'm not handling any of the capitalization here。

 So I don't think she will be found and indeed we see no mention of found。

 Now this is a feature of Python that's kind of handy too。

 and it's a little weird because in C and in scratch。

 the only time you could use elses was with conditionals but we've seen in Python。

 you can also use elses with exceptions。 Those special errors that can be triggered you can even use elsets is in Python with four loops by saying else print not found and what happens in Python is if Python realizes you never actually break out of this loop yourself it will then print out this only if you've not broken out the logic me。

Being that okay， you clearly didn't find you you were looking for。 So else， let's just say as much。

 So if I now run this again， typing in Yu's name all capitalized。 So miscapized here enter。

 I do now see that she's not found。 So it's just a nice little trick because it's so common to iterate through things fail to find a value。

 And then you just want to say some default you want to execute some default line of code as well。

 But turns out let's tighten this up to Python does not need you to do all of this work by iterating over every name in the list。

 checking if each name is in there， rather， we can tighten this up even more。

 let me get rid of this entire for loop。 and just say this， if the name you're looking for。

 is in the list of names， then print found else in this conditional print not found。 In other words。

 I can literally just ask Python， you search over the darn list for me。 And if it's in there。

 wherever it is， return true in that Boolean expression。if conditional， the Boolean expression。

 in effect。 so I can print out found or not found。 So this tube will just work。

 Let me go ahead and run this again at the bottom。 Python a phone book do high search for myself。

 David， and I'm indeed found， but I don't need to implement the searching for it left to right。

 It's still using linear search under the hood， but someone else has now written that code for me built into the language itself。



![](img/bbd185be7f30ef08483a327402859508_80.png)

Allright， so what more do we get， So it turns out that in the world of programming。

 like maybe the most useful， one of the most useful data structures is indeed a hash table。

 which gave us the abstract data type last time known as a dictionary。

 which is just a set of key value pairs。 What's wonderful about Python unlike PSet 5 and C is that you actually get a data type called dit for short for dictionary。

 which gives you exactly that key value pairs， but you don't have to implement any of the darn logic of problem set 5。

 It still gives you in effect something that looks a little something like this in memory， key value。

 key value key value， but you don't have to worry about the array。

 you don't have to worry about the chains of link list。

 you don't have to worry about the hash function even Python takes care of all of that for you。

 Now this will be a bit of a mouthful to set up， but let me go ahead and do this back in VS code。

 I'm gonna go ahead and create another version of phonebook pi here by first creating a dictionary of people instead of just a list because up until now we've had no phone numbers involved。

😊。

![](img/bbd185be7f30ef08483a327402859508_82.png)

I do actually want to have a bunch of names and phone numbers。

 And the way I'm going to do this is as follows at the top of this file。

I'm gonna go ahead and create a list called people rather， I'm gonna create a list called people。

 And a list， of course， uses square brackets。 But every person now I want to have some keys and values like a name and a number。

 So how can I do this。 Well， I'm gonna make some room for this。 This is not incorrect。

 I'm moving this close square bracket to a new line because I want every element of this list to be very clearly a dictionary。

 a set of key value pairs。 And you couldn't do this in C， but you can do this in Python in Python。

 you can use curly braces to represent a dictionary of key value pairs。 How do you define the keys。

 you put the first key in quotes， you then put a colon， and then you specify the value for that key。

 if you want another one， you do a comma， you then do quotes and you do another keys another key colon。

 and then its value。 And if I think back to week 1，3， rather we use plus 1，6，1，7，4，9，😊。

51000 for Yulia's number then。 And that's it。 It's a little cryptic because it's all on just one line。

 but it's like having two rows in this visualization here。 name Julialia number plus 1，6，1，7，4，9，5。

1000 in that their chart。 So if I want a second one of these。

 I'm gonna put a comma at the end of Ulia's dictionary。 I'm gonna put myself on the second line。

 So open curly brace， quote unquote， name， Col， and then David in quotes， then comma number。

Close quote， colon plus 1，6，1，7，4，9，5，1000 as well。 And then lastly， a second comma。

 so that we'll put John Harvard in here。 So his name is name is quote unquote， John。

 his number is plus 1，9，4，9，4，6，8，2，7，5，0。 And now we have a list of three dictionaries。

 Each of those dictionaries has two keys and two values respectively。 syntically。

 this is a pain in the neck。 And we would probably just store all of this information in a CV or a database or something like that。

 But for now， I typed it all up manually。 So we have a working example。 Now。

 let's actually search this dictionary。 This list of dictionaries for the people I want。

 Let's set a variable called name equal to the return value of input prompting as before the name we care about。

 Then let's do this 4 each person。😊，In that list of people。

 let's check if the current person's name equals equals the name the user typed in。

 then get their number by looking at that person's number field。

And then go ahead and print out with an F string， something like found。

 And then I'll just print out that number in curly braces。

 And then I will break out of all this or as before else， let's go ahead and print out not found。

 So this is a mouse but let's consider what's happening here。 First on line 8。

 I'm iterating over every person in people。 What is people， it is a list of three dictionary。

 So on the first iteration， person is this person。 Second iteration。 This person， Third iteration。

 this person in Python just takes care of that for me。 like we've seen with our four loops already。

 If that person's name field has this name， then I found the person I'm looking for。

 get their number stored in a variable called number。

 If only so that I can print it out with this F string。 else go ahead and print out， not found。

 if I never actually break out having found someone Notice then that just like can see when we use square brackets to index into an array in Python。

 you can index into a dictionary by literally using the。😊，amSquare bracket notation。

 So instead of saying bracket 0， bracket1， bracket2。

 you can say bracket name quote unquote and that will look up the value for that key。 So again。

 it's like going into this chart that we see here visually looking for name in the left column。

 finding that person's name， looking for the number value in the left column and looking for its corresponding value at right。

 It's all sort of happening for us automatically。 Now it turns out we can do this more simply if we instead restructure our variable called people。

 So let me go ahead and do this。 Let me go ahead and delete all of the code we just wrote。

 including that for loop and let me redefine people as follows。

 And I'm gonna leave the first version up there so we can see before and after。

 let's redefine this variable as equaling people。 But instead of people being a list of dictionaries let's just make people one big dictionary whereby it has two columns key and value but where the key this time is going to be the person's name and the value is going to be their number。

This is super useful in this case because I only have keys and values， names and numbers。

 This will not work if I also want to keep track of their email address。

 their student I D and multiple values as well。 In this case。

 it suffices to keep track of names and numbers。 If only so that I can remove some of this redundancy of saying name。

 name， name number number number， let's do it as follows。

 So people equals open curly brace closed curly brace。 And let's add a key of Ju。

 whose number is exactly this one here。 I'll copy paste to save time。 let's add another key。

 whose name is David， whose value happens to be the same number， let's add a third key。

 whose name whose value is John and set that equal to this number。

 so that now at the end of these lines of code。 we have Julia。

 as a key David is a key John is a key and their numbers respectively as values effectively implementing this chart for everyone。

 instead of one of these charts for each person。 So if I go back to V S code。

 let's get rid of the old more verbose version。 let's go back here and instead of。

Using any kind of loop now because there's no list involved。 Let's just do this。

 Promp the user using the input function for the name， whose number whose number they want。

 Then let's just say if the name you're looking for is in that people dictionary。 Well， great。

 go ahead and print out a format string that says that person's number is whatever is in the people dictionary at that name's location else。

 let's go ahead and print out。 for instance， not found。 So the only weird thing here。

 I dare say is this。If name and people works just like searching a list。

 but you can search a dictionary by key。 And if you find a key like Julia or David or John。

 it's going to allow you to use people as well， index into that chart at the name location with the appropriate row。

 and that's going to give us implicitly that person's number because even though we don't mention name。

 we don't mention number， this is what a dictionary is a collection of key value pairs and the key can be any string you want。

 and the value can be anything you want as well。😡，So that was a lot。

 But you'll see then in the real world， these dictionaries。

 really these hash tables underneath the hood are so useful because you can constantly associate one thing with another。

Questions on any of this。To date。Okay， few final examples。 I feel like。

 it's a tough crowd because we're teaching the entire language in a week。

 but we're almost at the finish line here。 And then everything else is gonna be icing on the cake。

 How do we go about implementing now from in Python。

 some of the features we eventually introduced in C， namely things like。😊，Command line arguments。

 which we've not used thus far in Python。 I've gotten all of my input using get input get stringing and Python's own input function。

 but I've never typed any words after the prompt when running Python and the name of a file。 Well。

 how can I go about doing this in Python。 Well， let me open up my terminal window here。

 Let's open up a program like dot pi reminiscent of week2's do C program。

 and let's do this from a feature of Python called cis import Rrg V， which is very different from C。

 But the same idea at the end of the day。 If the length of that Rrg V variable happens to equal to。

 let's go ahead and print out a format string that says hello comma R V bracket1 close else。

 go ahead and print out the default from week 2， which was just hello comma world。 Allright。

 what has just happened。 Well， first， let's run it and try to infer。 So Python of dot pi enter。😊。

How didn't write any other words after the prompt。 So I literally see the default。 hello comma world。

 What if though I write Python of Greek do pi and then David， well。

 what's gonna happen here is Python via this cis library is going automatically put every word I typed at the prompt after the name Python into a list called Rrg V by by definition。

 I can then check how many words are in Rrgv。 And if it's two。

 that means that the human typed in not only the name of the file to execute but also something after that as well。

 So if I now run this by hitting enter。 now I see hello comma David because there's two things in that list。

 Greek do pi and David， there's no mention of Python because that's the interpreter and without the interpreter。

 none of this would work anyway， you get the name of the file and the word you typed after that。

 It's not going work though， just like in week2， if I do David Main。

 because now Rrgv's length will be three instead of two。 So I'm again going to get the default。

This is to say there is still ArgV， there's no Arc C。

 because you can just use the length function LEN to find out what the length of ArgV now is。😡。

What more can we now do， Well， let me go ahead and propose that。 We introduce how about。So。

Exit statuses as well。 Whereby recall that in C， we had the ability to actually exit with some value like 0 on success or one or anything else upon failure。

 turns out that that feature is also tucked away inside of this cis library。

 Let me go ahead and create another program called say exit do pi just to demonstrate this one。

 let me go ahead and import cis， so is to have access not only to Rrgv。

 but also a function in there called exit， which just worked in C。

 but in Python will see that we want to use the version tucked away in cis。

 let's do something like this after importing cis， let's check if the length of Rrgv does not equal two things。

 let's go ahead and yell at the user quote unquote， missing command line argument。

 And we didn't spend long on this and C。 but we did something like this a few weeks back。

 And then let's go ahead and call exit of one。 Otherwise， if we get down here。

 let's go ahead and say， as always， a format string of hello comma cis do Rrgv bracket1 just as before。

 So as to greet the user。And then we'll say exit zero。

 but I do want to use argv that's inside of cis。 and I wouldn use exit that's inside of cis because according to the documentation。

 that's where these symbols are。 So I can now do cis do orrgv and I can do cis exit and cis exit。

 which just makes super clear that those two symbols Rrgv and an exit are inside of that cis library and we did this earlier when I played around with the CS50 library or importing specific things or the whole library itself。

 the idea here is ultimately the same So let me run Python of exit do pi with no command line argument。

 So enter and I indeed get an error message and this is probably not something you've needed to run since I lasted。

 but if you do dollar sign question mark after E， you can quickly see what was the actual secret exit status if I run this again with my actual name。

 David enter， I actually get greeted and if I do that dollar sign question mark again after echo I see now the secret exit status。

So again， not something we've used often， but by convention， we can still do in Python。

 what we've been doing in C， namely signaling that something was successful or a failure。

 Let's do one last set of examples that are reminiscent of past ones and we conclude with two new ones altogether。

 recall that we've had this phone book that previously took input just from a hardcoded list of dictionaries or one dictionary。

 let's actually reintroduce the idea of CV files， comma separated values whereby we can actually save this information to disk so that we can add and add and a and even remove names and numbers eventually In Python。

 One of the things that's wonderful is that you have built in support for CV files。

 You don't have to worry about the comms， the quotes or anything like that as follows。

 So let me run code of phone book to reopen that same file from earlier。

 but let's delete everything therein and let me now do this Let me import Python's own CV library。

 which is against comma separated value。And we use this briefly for my last phone book a few weeks back。

 Let's now open a file using the open function that comes with Python。 It turns out。

 opening a file called phonebook dot C SV in append mode。 So we can add to it。

 as we didn't done in the past line by line。 Let me then go ahead and。😊。

Ask the user for a name using input。 And then let's ask the user for a number， using input。

And then let's actually put those that name and number into the file。 How can I do this in Python。

 And again， the goal here is not to not to absorb exactly how to do this in Pyon。

 It certainly reasonable to look this up。 But just to show you how relatively easy it is。

 I'm gonna create a variable called writer， though we could call it anything I want。

 And I'm gonna set that equal to the Cv librariess writer function that just comes with it。

 And I'm gonna pass to it。 the name of that file。 This is a feature that says open this file and be ready to write to it hereafter。

 How do I do that。 I can do writer do write row。 And I can pass in a list of the things I want to write to it。

 So I can say name comma number in square brackets。 So that prints out a new line to the file。

 And then at the very end of this， Let's do file do close to close the whole thing。 Now。

 let's see what just happen。 Let me go ahead and open up phone book do cv enter。

 which is empty initially because nothing's in there。 Let me show it at write continually。

 Let me now run Python of phone book do pi enter。😊，And let's do Julialia's name。 Yulia enter。

 and then her number， plus 1，6，1，7，4，9，5，1000 And watch what happens at top right when I hit enter。

 because that row will be written。Alright， she's now in the file。

 Let me run it once more with my name。 and plus 1，6，1，7，4，9，5。

1000 enter And now I am written to that file。 And if I want to do this for John Harvard or anyone else。

 I can do that then as well。 So what's nice is that notice that the writer the right row function is actually outputting the commas for me。

 And if there were weird characters or commas， it would actually escape them by using quotes as well。

 as withython in general， I can tighten this up further。 In fact， it turns out that inython。

 you don't need to be so pedantic as to open the file， then do some stuff， then close the file。

 There's this weird other preposition in Python namely with that allows you to do multiple things at once。

 So let me do this， let me get rid of the close line。

 And let me instead do this with open as file colon。 and then let me indent all of this here。

 that now is going to have the effect of actually doing all of that but automatically closing the file form。

😊，So I don't run the risk of forgetting maybe leaking some memory somehow and so forth。

 And there's one final flourish I can do here too。 Right now， I'm using this basic writer function。

 which essentially just writes a list， writes a list， writes a list。

 There's one other way where I can write dictionary after dictionary after dictionary。

 which is handy， especially if I don't just have names and numbers。

 but maybe email addresses and I I D numbers in other types of values as well。

 and I can do it as follows。 Let me go ahead and let me sayops， and actually just to be clear。

 this code can be outside of that width， because I can ask for this once without the file actually being open yet。

 So let's change these two lines here。 I can create a writer， But this time use a dictionary writer。

 which allows me again to write dictionaries， key value pairs instead of just lists of values lists。

 I can say use this file for my dictionaries。 Let's use field names of quote unquote name comma number。

 And then。Go ahead after that and do writer dot write row。

 And I can now pass in any dictionary I want that I want written to that file so I can do name。

 colon， name。 And then， for instance， number， colon number。

 And let me go ahead and reopen phone book dot CS SV enter。 Let me move it right here。

Let me delete all of that and notice what happens this time more like your real worldd of using Excel and Google sheetets and Apple numbers。

 Notice now when I run Python， a phone book pi enter， and I type in Yulia and plus 1，61，7，4，9，5。

1000 enter。 Notice that it too works as well。 And if I wanted to as well using a dictionary writer。

 I can additionally tell this writer to include the names of these columns in that file so that when I open it up in Excel or Apple numbers your Google sheetets。

 Also the data is described in that first row of headers that you're probably familiar with from having just use spreadsheets in the real world。

 So long story short， this is not to ingrain in you exactly how you read and write Cvs or write in this case。

 but rather just a few lines of code like six lines of code。

 you can do a lot more in Python than you can and So now to end on a lighter note， let's do this。

 It turns out in Python， there's not only all of these libraries that come with the language。

 but there's also third。😊，Party ones that you can install as well。 And there's a program。

 you can run in a Linux environment like your own code space called Pip。

 which allows you to install additional packages。 That is to say thirdpart libraries that other people have written What this means is that in advance of your using C 50。

 we essentially ran Pip install Cs50 to make sure that I default。

 you just have access to C 50's own library It does not come with Python。

 but it's out there in the cloud somewhere And Pip knows how to install it。

 But suppose I want to do something fun like from a few weeks back where we did cow and we had a cow M on the screen。

 and we had a dragon and other things too。 Well， turns out there's a package called cow that I can for install for Python with Pip install cow enter。

 You'll see on the screen a bunch of stuff happening because it's downloading it and it's installing it into the appropriate location。

 But now this means there is a library called cow say in my own code space。

 So if I go ahead and create a program called like Mo pi In this file， I can now import ca。😊。

Will give me access to any functions and symbols therein。

 And I can do something like this Pers documentation。

 cow library do cow because this is gonna print a cow on the screen。 And I can say this is C S 50。

 And down here， I can do Python of Mo pi enter。 let's make the terminal window bigger。

 Let's do this again。 Python of Mo enter， and I get a cow saying this is C S 50 in a little speech bubble like that。

 I can make it more interesting now in code， though， as follows。 if I'm shrink my terminal window。

 And I use something like Python's input function。 I can ask the user for their name。

 like what's your name as we did way back with scratch and then see。

 And then I can use one of these F strings in here。 And instead of saying this in C S 50。

 I can say something like hello comma name and curly braces。 Then down here。

 I'll make my terminal window bigger。 run Python of Mo enter What's my name， David enter。

 And now the cow iswing muwing dynamically based on what I've just actually typed in。

 We can do things even fancier than。😊，Yes lastly， let me see if I can type this out correctly in my terminal window。

 Let me go ahead and install Pip install Q R code， these twodial barcodes nowadays that are seemingly everywhere。

 This is gonna install library that's gonna know how to automatically create a 2D bar code for me based on any text that I give it。

 including a URL。 because someone else wrote the code that figured out how to do all of that and output a two dimensionmenal code。

 So let me go into a program called Q R dot pi that I myself will right。

 but I'm gonna stand on that person's shoulders。 And I'm gonna import a Python O S library。

 which gives me access to the file system， so I can read and write files。

 and I'm gonna import that person's library Q R code。 I'm gonna now create a variable called image。

 said it equal to Q R code dot make because I want to make a Q R code。

 And I'm gonna type in like the URL of one of C50's lecture。

 So H T T P S colon slashlash you slash X V F Z J。😊，5 P G G0。

 And hopefully I made no typographical errors there。 Then on my next line， I'm gonna to call image。

 which is the name of that variable dot save。 I'm gonna save this as a file called Q R dot ping。

 Turn out this library supports different file formats like Ping P， N G for portable network graphic。

 So I'm gonna say， give me that type of file。 Then I'm gonna go ahead and run this program as follows。

 Python of Q R dot pi。😊。

![](img/bbd185be7f30ef08483a327402859508_84.png)

Enter no errors。 I'm gonna now open up Q， R R dot P， N G。 En， hide my terminal window。

 give you all a chance to open your phone and open the URL that's secretly embedded in this Q。

 R code。 And at the risk of incurring your Ire。

![](img/bbd185be7f30ef08483a327402859508_86.png)

There we go， This was CS50。 we'll see you next time。



![](img/bbd185be7f30ef08483a327402859508_88.png)