# 哈佛大学《计算机科学导论｜CS50 introduction to computer science 2025 Fall》 - P7：CS50 Fall 2025 - Lecture 6 - Python .cut.zh_en - GPT中英字幕课程资源 - BV1S8sFzFEt7

Actually， before we begin， because this is such an intimate group today。

 we'll still do it as theatrically and as excitedly as we can。

 even though it's a more inmit since it's a conflict for so many people on Wednesdays， side effect。

 though， is that there's gonna be all the more snacks outside。 F by the foot is served today。😊。

Thank you。Right。All right， can we do the dramatic lights again？See you in a moment。Alright。

 this is C S 50。 and this is already week 6， Wherein we transition away from C to a programming language called Python。

 And that it's not to say that the past several weeks haven't been among the goals of the course。

 Indeed， in learning C。 I very much think that you'll have at the end of this class。

 so much more of a bottom up understanding of how computers work of how programming languages work。

 And in particular， you'll appreciate and understand better。

 how Python and Java and C plus plus and Swt and so many other languages are actually doing their thing nowadays。

 In fact， we're doing this roughly chronologically thus far in that。 well， that's not at all true。

 Scratch came out much more recently。 So Scratch that's let me say something else。😊。

But recall that we started with scratch some weeks ago and in scratch。

 what was nice was that the first program we wrote hellello world was just all too accessible。

 All you had to do was interlock two puzzle pieces in order to make the cat in that case。

 say hello world。 Well thereafter， of course， we transitioned to C and recall that in week1。

 we asked you to take on faith that you can sort of ignore that first line and a lot of these parentheses and the curly braces and really just focus on the essence of the program。

 which clearly is still about hello world and printing it albeit using a different function in a bit new syntax。

 Today， very excitingly all of that is truly going go away and be distilled into a single line of code when you indeed want to have the computer say something like hello world。

 And this is what we mean by Python being a higher level language。

 So humans over the decades learned from earlier designs， earlier programming languages。

 what worked well what did not computers got faster。

 computers had more memory and so you were able to start spending more of those resources in order to have the computer do more for you。

 And so you don't need to be aspedantic syntactically。😊，Anymore。

 you don't need to write as much code anymore。 and frankly you can just start solving problems of interest to you。

 building products of interest to you so much more readily by choosing the right tool for the job。

 And so in the real world if you continue coding after CS50 like sometimes C will be the right tool for the job sometimes Python will be the right tool for the job and sometimes it's going be a different language altogether that you'll never have studied in school and in fact what's compelling I think about this week6 much like when I took the class back in the day is that after CS50 you'll have a taste of one to maybe a few different programming languages and that's gonna to be enough to bootstrap yourself and teach yourself new languages because you're going start to recognize in the real world similarities with past languages that you've seen programming paradigms that are still sort of with us and the syntax。

 yeah， that's invariably going change but that's the stuff that you are going go or ask Chatt or some other AI about down the line so long as you know enough of it to sort of get real work done。

 you'll focus mostly ultimately on the ideas and the problems you want to solve unless。

The syntax And so among the goals for this week and this week's problem set and really the rest of the course is to get you more comfortable feeling uncomfortable in front of your keyboard because we're not going to give you and tell you everything you need to know for a language like Python。

 you're going to turn to the documentation。 You're going turn to the duck and you're going to learn to teach yourself ultimately a new language。

 So let's actually write our first program and compare and contrast with how we might do that in C。

 So recall that in C。 we were in the habit for the first couple of weeks and doing make hello and make this build utility just kind of magically new to look for a file called hello do C and magically to create a program called hello and then you could run it with do hello。

 and then in a week or so later， we revealed that make is really just automating compilation of your program with the actual compiler clang in this case and passing it command line arguments like O to get a specific output like the file name hello instead of the default。

 which recall was a do out passing in the name of the file you want to compile and turning on any libraries that you might want to compile。

Pile into your program link into your program beyond the standard ones。

 But then you could still run it in exactly the same way。 starting today。

 when you write Python code and then want to run it。

 you're simply going to run the Python program itself So just as clang is a C compilerython is itself not only a programming language but a program as well And with the Python program which understands the Python program language can you run code that you'll have written in a file called hellello do pi。

 And what this program is doing iss a little bit different from what Klang is doing but we'll see that difference before long。

 But first， let me go over to BS code and let's write our simplest our first of Python programs by doing code hellello dot pi and then in this file without any includes any int main voids。

 I'm simply going to say print quote unqu hellello comma world close All right now I'm not gonna to do make I'm instead just going to do Python of hello do pi across my fingers as always andvoila my first program。

PythonSo it's sort of obvious that we got rid of the hash and clue， we rid of the inmanin void。

 no curly braces， only a couple of parentheses here。

 but what else is different to your eyes that's a little more subtle here。😡，Versus C yeah。Yeah。

 so there's no F。 so the print function is a little more human friendly。

 It's print instead of print F where the F did mean formatted。

 but we'll see that we still have that functionality。😡，So no need for the line break。

 specifically the backslash N。 And yet， here's my cursor on the next line。

 So I dare say humans over the years realized we are more commonly wanting a new line than we don't want it。

 And so they made the default to actually give it to you automatically。 And there's one more detail。

 yeah。😡，都。So there's no semicolon。 So I finished my thought at the end of the line。

 but I didn't need to explicitly terminate it with a semicolon。 This is just with one program。

 all of these salient differences。 But I'd argue that we got rid of all of the annoying stuff thus far anyway。

 So we can really focus on what this program itself is doing。 But what's exciting with Python too。

 is just how quickly you can solve certain problems。 And this isn't true of just Python。

 It's really any higher level language than C。 In fact， just for fun。 let me go ahead and implement。

😊，Problem set5， which is in your hands right now I can't say that because we're pretending like this happened in the future。

 Let me go ahead and implement problem set5， where in your' challenge with implementing the fastest spell checker possible。

 So what I'm going to go ahead and do here in Python is in my terminal window。

 I'm going go into a folder。 I came with an advance called Python inside of which are some of the same files from problem set 5 but in here I'm going to go ahead and code up a file called dictionary dot5 and I'm going propose that if I want to implement a dictionary of like1000 plus words as you've done with problem set 5。

 I could do this in Python by saying something like words equal set to give me a variable called words and an empty set into which I can put actual words。

 I'm going to define a function called check that's going to take a word as its sole argument。

 and then I'm going simply return that word forced to lowercase and return true or false whether or not it's in words and below that I'm going find a load function that's going take。

As input， just like problem set5， the actual dictionary file with all of the English words that you want to load。

 and then I'm gonna to say with the opening of that dictionary as a variable called file。

 go ahead and call words do update file read do split lines open for and close and then just go ahead and return true because I claim that's enough to get the job done。

 And if I'm want to get the size of this dictionary that is how many words are actually in it。

 I'm going go ahead and just return the length of that word set。 And then lastly。

 I'm going go ahead and define in unload function whose purpose in life is simply to free up any memory。

 but as we'll see Python does all of that for us。 So I'm just going on faith return true。

 And that's it as problem set 5 in Python。 It is not going be the case in see that it's nearly as quick or as easy to write because I'm leveraging the fact that Python as a language comes with a lot more features。

 And I dare say if you were to see this code before implementing problem set5。

 it's not really going to help you out other than to emphasize that the ideas are still。

Same in Python and the problems we're solving are the same。

 But the code and the libraries to which we have access are markedly different。 But here's the catch。

 If I open up my terminal window now and I run a command like Python of speller。

 And I've also convert it in advance of class the speller program in C to an equivalent program in Python。

 I'm going specifically go ahead and spell check a file containing Grs fairy tales。

 which is the largest of the files distributed。 And I'm going go ahead and maximize my terminal window here。

 and hit enter。 And this is going to spell check that Grs fairy tales file using the default dictionary。

 And so what you're seeing on the screen or all of these seemingly misspelled words。

 but some of those are just possessives and so they didn't technically appear in the file。

 but that's okay and you'll see that it took point18 seconds in order to run that code。

 Well now let me go ahead and minimize my terminal window。

 Let me go ahead and create another terminal window to the righthand side here and go into a folder called C which contains a C。

Version of the spell checking program， which the staff wrote in advance。

 I'm gonna go ahead and compile that with make Sper。

 I'm gonna go ahead and run dot slash speller on that same file。 The Grs fairy tales。

 I'll maximize the window now。 hit enter on the right hand side of my terminal， and you'll damnm it。

😊，And it's slower， which was not the case a few minutes ago。

Let's pause for just a moment because you were supposed to be dramatically impressed by this。

Give me one second。It's a good thing。 your classmates aren't here to see this。Yeah。

 that's as expected。嗯嗯嗯。Thankang it。Okay， we're going to rewind and redo this。

So what I wanted to say pedagogically is that because C is a compiled language。

 what's typically going to be the case is that when you can the program down to zeros and ones。

 that's in the computer's native language and so it's supposed to run quite quickly as a result。

 but when you run an interpreted program like the Python version there as we'll discuss today。

 it does it line by line step by step and much like it's a lot slower to have a conversation between two humans if you need a third translator in between them。

 similarly does Python typically do this， I don't know what has changed since this morning when I fued with this so we're gonna to pretend like this worked and we'll deal with it later。

 but any questions before we pretend like the past minute didn't happen。

We disable caching of Python Btecode in CS50 do， but that's a good instinct。I don。No。

 the cache would be very local， you would see a PYC file。Other questions， though， before I。

Try to fix this。All right， my apologies。嗯。Is Wongshn still here？We're very casual today， all right。😊。

唉。Sorry， everyone。Okay， code， hello dopi。Okay。So let's do this over here。啊。

But what's especially fun about Python is how easy it is to solve certain problems。

 including some of the problems that you all have solved in past problem sets。 For instance。

 let me go into VS code here and close hello do pi and let me go ahead and whip up my own implementation of a program that maybe blurs an image as you might recall from problem set4 So what I'm going do is create a program called blur do pi instead of creating a program called filter。

 this program will only do one thing in life and then I'm gonna to say the following from P the Python image library。

 import something called image capital I and image filter。

 capital I capital F then below that create a variable we'll call it before to represent the before image then go ahead and open using image do open a file from problem set4 called bridge do BMP then let's create a second variable called after and set that equal to before dot filter passing in image filter do box blur and just。

A little more dramatic instead of passing in one here。

 which would technically be the same as problem set4 I'm going to put 10 just to add to the blur visually and then let's go ahead and save the file as say out dot BM then what I'm going to do is just grab from the problem set4 distribution code the actual bridge dot BM file that was distributed with it for for the problem set itself and then assuming that file is in。

😡，Damn it， sorry。And then I'm going to go ahead and run Python of instead of Ho dot Pi， blur dot Pi。

 crossing my fingers as always， hit enter。😡，Nothing seems to have gone wrong。

 which is usually a good sign。 So what I'm actually going to go ahead do now is open up out dot BM inside of VS code。

 And whereas the original， of course， was not at all blurry。 I dare say to the human eye。

 this now is quite a bit blurriier。 And in fact， if we want to take a look at the before and after。

 let me go ahead in a separate tab here。 go ahead and open up， say。😡，The bridge itself。

 bridge dot BM toggling between the two。 So this is before。This is now after before， after。 Now。

 those of you who might have tackled the more comfortable version of this problem set might have actually done something called edge detection。

 whereby you tried to find the edges of the bridge and make them much more pronounced。

 So let's do that。 Let me go ahead and close blur dot pi。 Let me go ahead and open up。

 say edges dot pi。 And then similarly， use this third part use this library called the Python image library A a pill。

 import again something called image， something called image filter then down below。

 let's go ahead and do before equals image dot open of again， bridge dot BM。

 then let's go ahead and create an after variable and set that equal to before dot filter inside of parentheses image filter。

 But this time， use find something called edges。 And then lastly， let's take that after variable。

 save it again as out dot B over writing whatever the previous version was。 So again。

 we have this bridge dot BM， which looks like this by default。 Now， though， if I open up if I run。

My edge detection program， nothing seems to happen。 but if I now open up out BmpP。

 we'll see in just four lines of Python code， what some of you might have spent quite a bit of time implementing instead in C and what's also exciting about programs like Python is something like problems at5。

 the spell checker program that challenge you to implement and C the fastest hash table that you can so that it can look up and spell check words as quickly as possible using as little memory as possible。

 I dare say we can dis that C code into just a dozen or so lines of C code as well。

 but the catch is when using Python or these other higherle languages in general。

 is that there is gonna be a price that we pay as always， there's gonna be some sort of tradeoff。

 And so thus far what we've seen of C is that you always have to compile it and then run it。

 but as claimed when you write Python code， you just need to run it， you don't need to compile。

 which is to say you don't need to go through that with step with make or with clang in the case of C to actually convert your source code into zeros and。

The so-called machine code。 you just leave the Python code as source code。

 and instead you use what's called an interpreter。 So that program called Python is not a compiler per se。

 It's more of an interpreter that essentially reads your code top to bottom left to right。

 much like a human translator with listen to one person and then translate those words verbally for another person who doesn't speak the same language the catch though with that whole process both in the real world than in the Python world is it's typically going to slow things down because there's just more work to be done Now that's not to say that Python across the board is slower than C。

 that's not to say that you shouldn't use Python or Java or C plus P or any number of other higher level languages if it's going to be more valuable to you to spend much less time much less code。

 put yourself at risk as many fewer bugs by using a lower level language like C。

 then you probably should reach for something like Python to get the work done more quickly And if it's not something that's doing maybe number crunching with massive amounts of data and looping over。

Maybe millions or tens of millions of rows of data such that the program doesn't need to run that long anyway。

 you can probably afford to spend more of the computer's resources on just interpreting the code that you've written and even this is a bit of an overstatement because increasingly Python isn't typically only interpreted it's also the fact that this Python program depending on the version that you're using technically and kind of secretly does compile your code and then it cachees your compiled code typically in a temporary file so that it doesn't need to do a interpretation step every single time and so humans computer scientists have been working for some time to speed up languages like Python such that performance is not generally the reason you should reach for one language or another unless you have a particularly well-defined use case for doing something much lower level with C something closer to the hardware where maybe you're really constrained by memory or CPU that is the brains of the computer by cost or you really just have to do a lot of something。

😡，Again and again and again， where every millisecond might add up。

 So what can we then learn from C still Well， C had， of course。

 functions and functions where those actions are verbs that simply got worked on。

 and let's go ahead and compare side by side。 much like we do with scratch and C the idea is that today onward are still gonna be the same。

 and how they could translate to Python。 So on the left here， we'll now have our friend scratch。

 this of course was one of the first puzzle pieces we saw it's a purple puzzle piece saying say and it was a function。

 In so far as it said the value of its argument， which in this case is hello world。

 What we've already seen in Python， what this looks like。 it looks similar to the version in C。

 but it's no longer printf。 There's no longer a semicolon and there's no longer an explicit new line。

 So in Python it's quite simply this。 Meanwhile， in Python。

 there are a whole bunch of libraries as well。 Now in C we had simply header files and those header files gave you access to the prototypes of that is the signatures of the functions that you want to use from those。

Python uses somewhat different vernacular whereby Python has what are called modules and packages and a package is just a collection of modules。

 but a module is just a library using Python speak so to speak So anytime you hear someone discussing a module or a package in Python they're just talking about using a library and that library might come with the language itself built in as standard or it might be a thirdpart library that you might download and install yourself much like I did a few weeks back when we installed the cow say program so that I could actually have a cow or other animals on the screen display text So in C recall we had something like this include CS50 H which was the header file pre-installed for you somewhere but we will have for at least this week a analog of the CS50 library in C also in Python just to make this transition from C to Python a bit easier these two though are meant to be training wheels that you can take off and should take off even within a week or so。

 it's just meant to smooth that transition and make clear what's the same and what's different So in the CS50。

For Python， we also have a function called getstr， whose purpose in life is to get a string to access it though。

 You don't use hash include cs50 do H。 That's a C thing。 And Python。

 you would say from CSs 50 import get string。 It's a little more verbose。

 but it's also a little more precise as to what you want from the library。

 especially if you don't want the whole thing loaded into memory。 So here， for instance。

 is now a scratch program that was a little more interesting。 Then just printing out hello world。

 This was the first program we wrote that actually got some user input。 So in fact。

 let me go back to VS code。 And let's see if we can't resurrect this C program real quickly in the form of a new hello do C。

 So I'm going run code of hello do C。😊，And then in my in my code tab。

 I'm gonna do include Cs50 dot H include standard io dot H And then below that。

 I'm gonna go ahead and whip up our familiar version of this it may avoid and then inside the curly braces we'll bring back string。

 even though we now know it's char star we'll call our variable answer， said it equal to get string。

 ask the user quote unquote what's your name with a space just to move the cursor over still need my semicollon in C。

 and then after that recall back in week1 we did hello comma percent S backlash n and then plugged in the variable answer so as to see hello David hello Kelly or something else。

 just to be safe。 let me do make hello all is well so far dot slash hello type my name and this version in C seems to be working okay So in C。

 these lines of code here， translate pretty literally to what we just saw although we got the answer variable in scratch for free。

 that blue puzzle piece just existed without our having to create it。😊。



![](img/d7777e514be9901928364ebea51b7b57_1.png)

It's a decent number of hoops to jump through in order to just get user input and print out。 Well。

 in Python， this is going to get a little more succinct in that the Python version of this code is now going to look like this。

 printntf is now print， The semicoons are gone and what else seems a little bit different。Yeah。

I don't need any placeholders。 Yeah， so we don't need the percent S anymore。 In fact。

 I'm curiously using a plus， which if some of you studied Java or some other language you might have actually seen this before。

 even if you've never seen Python before， you've only seen C in CS50。

 you can probably guess what the plus is doing， even if you don't know the technical vocab。

 What is the plus probably doing here。😡，Yeah， so it's concatenating or joining together the thing on the left with the thing on the right and we actually had that vernacular in the world of scratch。

 we had the join puzzle piece that joins hello comma space and the value inside of answer。

 a plus in Python can do exactly the same thing。 so it's a little more user friendlyend than having to anticipate。

 let's put the placeholder here and then come back later and plug in the variable humans over time。

 just realize that it's a lot easier to sort of do this in this way then bother with placeholders。

 though you can still use placeholders for other purposes。

 another subtle difference between the C and Python version of these two lines。😡，More subtle。真等。

What's missing？Yeah， I'm back。So the backslash n is again gone for Python。

 so that sort of happens for free， indeed， and one more difference。Yeah。

 we don't need to declare the type of answer。 recall that if we rewind in the C version。

 you needed to tell the compiler that this is a string。

 and last week we could have changed string to charge star。

 but we still had you tell the compiler what data type we're putting into that variable in Python we can now get rid of that data type and Python will just figure it out from context If get string returns a string well then obviously the variable should store a string if a function returns an int then obviously the variable should store an int and the language is just doing more of that decision making for you just to save you time and save you thought There's a subtle D here though where we can make this program a little bit different。

 In fact， let's whip it up first in Python。 let me go back to VS code here clear my terminal and let's go ahead and create a program again called hello do pi thatll open up my previous version thereof And just so we can see these things side by side。

 I'm gonna drag that tab over to the right of VS code and let go and now you can see the C version still on the left and the Python version at the right What I'm going do here now in my Python version is changing。



![](img/d7777e514be9901928364ebea51b7b57_3.png)

To be quite like the version in C now at left so as promised I'm going to do from CS50 import get string then below that I'm going to say simply answer equals get string quote unquote what's your name。

 question mark space no semicolon but then on the next lineop but parenthesis then on the next line。

 I'm going to do print quote unquote hello comma space close quote plus answer down here I'm going to go ahead and run Python if hello do pi again。

 no compilation step I'm just gonna interpret it line by line what's my name David and it seems now to work exactly the same Now turns out in Python there's even more ways to solve problems like this。

 even trivial problems like this So here we're using the plus sign not as addition per se。

 but as the concatenation operator， the joint operation if you want though you can take advantage of the fact that print in Python can take more than one argument it can take two or three or four even zero by simply。

Changing the plus to a comma， getting rid of that seemingly superfluous space and just give print two things to print because it turns out per the documentation of print。

 which we'll eventually see it knows that if it takes one two arguments by default。

 separate them for you by a single space。 And that's something we can override as well。

 Which one is better I don't know like they're sort of equivalent。 It's such a trivial difference。

 but it speaks to the flexibility that you'll start to have whereby the language is a little less rigid than C was certainly when it comes to printing strings。

 So in fact， if I go back to Vs code here。 and I go ahead and change that plus to a comma and get rid of the space inside of the quotes。

 I can rerun Python of hellello do pi type in my name and we see exactly the same result there。

 But we can take this one step further， even though it's gonna to look a little cryptic。

 this is sort of the more pythonic way to do things And that too is actually a term of art to do something Pythically is to do it the way that most python programmers would do。

It's not the only way it's not necessarily the right way。

 but it's sort of the recommended way in the community So here we have that latest version where I'm passing two arguments to print。

 the first is quote unquote hello comma and then the second of which is the value of answer I could similarly right this same program with this crazy syntax takes a little getting used to。

 but it turns out it's actually kind of nice overall what's obviously different well one there's these weird curly braces or back they're not part of the logic of the program they're literally inside of the double quotes but you can probably guess how what this does for me because there's one other crucial difference。

What else has changed between。Before and after。Yeah， there's this weird F。

 which is not part of print F。 It's actually inside of the parenthesis。

 And next to the double quotes。 and even this one this came out was a little weird looking to people。

 but this is how you get this thing to be a formatted string Aka and F string as opposed to it being just a literal string of text。

 Now you can probably guess what it means to put the variables name inside of the curly braces。

 it means the value of that variable is going to be substituted right there。

 similar in spirit to the percent S in C but a little more explicit with the percent S。

 you had to remember that that percent S corresponds to this variable value or something like that。

 which was just annoying if anything else， if anything。

 but this time you have a placeholder in curly braces that just says what you want there。

 that particular value and what this means more technically is that the answer variable will be interpolated by the interpreter。

 which means its value will be plugged in right there。 So let's try this。

 let me go back over to be S code and quite simple。On my last line of code here。

Let's change the input to print to be quote unquote， hello， comma， and then curly brace answer。

Then close curly brace， close quote。 And I've done this this is intentional。 But let's see。

 let me go ahead and rerun Python of hello dot Pi D A V I D。 What are we about to see， Hello， comma。

Answer， so this is a bug， but just to demonstrate like what is going on and what's therefore missing。

 what did I forget，Yeah， I didn't declare that this is a so calledled F string or format string。

 And the fix for this weirdly is just to put an F right there。 And now。

 if I rerun Python of hello up high， type in my name again， cross my fingers。 Now。

 I see that the variable has indeed been interpolated and its value plugged in where I wanted it。

All right， it out we can take off one of these training wheels already。

 I propose that getstring just exists in the library just to smooth the transition， but honestly。

 it's not really doing anything all that interesting。 So let's take this first training wheel off。

 It turns out that Python comes with a function appropriately named input such that if you want to get input from the human via their keyboard。

 you can just use the input function。 So we can already for this program。

 get rid of the C50 library because input essentially behaves just like the getstring function。

 So if I go back to my Python version here， I can change getstring to input and I can even go and delete this training wheel up there。

 rerun Python of hellello pi in my terminal D Vd enter and we're still in business as well。

 So input is generally gonna to be the way you go about getting input now from the user。 All right。

 let me pause here and see if there's any questions as we try to bridge these two worlds from C to Python。

Yeah。So你开上 with don。Good question。 in Python， why don't we need the main function anymore because clearly that's been omnipresent in like every program we've written thus far。

 And here we have it in all of our Python programs thus far absent。

 It turns out that humans realize it's just so common that you want the file you' editing to be the main part of your program Like why bother adding the additional syntax of saying main void or something analogous。

 it's just easier if you want to write two lines of code to get some work done。

 Why do you have to waste my time adding all of this boilerplate code which we've been doing up until now Now that said。

 we're gonna bring back main in a little bit because it will solve a problem。

 but generally speaking what I'm doing here is indeed a program。

 but people in the real world would also call these scripts where a script is like a lightweight program that pretty much just reads top to bottom left to write it might be fairly lightweight。

 It's really synonymous with writing a program， but this is again one of the appeals of a language like Python you can just get right in and get out and get the job done。

Even Java has moved to this in recent years where you don't have to put everything in a class。

 public static void main for those familiar， you can just write system。

 outt printline and get some work done。😡，对。And put only import。

Good question is input only for a string， yes， right now it will get input from the user via their keyboard and you'll get back a string just like getSting。

 and we'll come back to why that's maybe not a good thing。😡，Allright。

 so what's more what we want to do at this point。 Well。

 let's tease apart some differences now with C。 So up until now。

 every argument we've ever passed into a function in C and scratch for that matter is a so-called positional parameter and a parameter is the same thing as an argument but generally when you're looking at the function from the functions perspective。

 it's a parameter that it accepts but when you're calling the function and passing in an input you call it typically an argument。

 but they refer to essentially the same thing and all of the parameters we've been passing into functions thus far have been positional in the sense that the order matters。

 the first thing， then the second thing， then the third thing and so forth。 for instance。

 with printf， the first thing has to be the quoted string， maybe with a placeholder。

 and then if there's another argument after the comma that can be the second argument。

 the third argument and so forth。 but it turns outython additionally supports what are called named parameter whereby you don't have to rely only on the order in which you're enumerating。

😡，Arguments to a function and that's helpful because some functions。

 especially in the real world when you start using other people's libraries that have lots of functionality。

 they might not take just one or two arguments。 they might take four arguments，10 arguments。

 maybe even more and it can just be unwieldy to have to remember the precise order of all those arguments you're just asking for trouble if you're going to screw up or a colleague is going to get the order out of out of whack。

 So with name parameters you can actually be explicit with Python and tell it what argument you are trying to pass in by giving it an actual name So let me go over to BS code here and propose that we use this for really the simplest of programs in order to。

Override that default new line that we seem to be getting for free just by calling print。

 In other words， let me go ahead here and clear my terminal window。

 Let me close hello dot C and focus only on hello dot pi for just a moment。

 And let's make it much simpler like the very first version and just print out using Python's print function。

 not print F quote unquote， hello world close quote。 And now here。

 I'm gonna do Python of hello dot pi enter， and we sue see that the cursor moves to the next line。

 The dollar sign moves to the next line Because I'm automatically getting a new line。 Well。

 what if you don't want that， How can you override that behavior。 Well。

 you can actually use a named parameter in Python。 And I can go up here and add a second argument。😊。

That if it were just something like this， that would literally print out the word this。

 because it's just another string， but if I give it a name like end equals quote unquote。

 I can override the default behavior of the Python print function by changing the value of its end parameter to be the so-called empty string。

 quote unquote， which means literally there's nothing there。😡。

Watch what happens now if I run Python of hellello da Pi and hit enter。

The dollar sign is weirdly and sort of in the ugly way on the same line。

 just like it was when I made the mistake in C in week1 of omitting the backslash n。

 That is to say what the default value of this end parameter really is is quote unquote backlash n。

 and I can make it explicit by changing my code as such。

 I'm gonna go ahead and rerun Python of hell up pi。 And now the cursors back on the next line。

 and not that this is that useful， other than overriding that default。

 But you could do fun things like exclamation point， exclamation point， exclamation point。

 If you really want print to be excited to print some things for you。

 And if I now run Python of hello up pi a third time now you see that it's ending with exclamation point。

 exclamation point， exclamation point looks a little stupid with the dollar sign。

 So you could even toss in a new line there run it yet again。

 and now we sort of get both of those there。 But I would say the common case is to use that end named parameter simply to override it。

 So how do you learn more about these kinds of things。 Well， if you go to the official documentation。

😊，For Python， which is a thing more so than with C like if you want to learn more about Python and the functions it offers and the arguments it takes。

 you go to the official documentation docs。pyython。

org this is essentially analogous to the so-called manual pages or man pages that C50 has a version of but there is no one de facto source for those man pages several different versions of them exists in the while whereas Python itself as a community maintains its own official documentation so for instance if you go to a specific URL like this ending in functions htl you'll see an exhaustive list of all of the functions that come with Python besides just the print function and we'll see a bunch of more today specifically you scroll down to the print documentation you'll see something that's a little arcane that looks like this but this is representative of a python prototype if you will also socalled a signature that just tells you the name of a function and then how many and what type of arguments it takes so how to read this well the print function takes。

Some number of objects。 So in Python specifically， this syntax of star objects just means zero or more objects。

 whatever that is like a number or a string or something else。

 the stuff you want to print out after that， if you start using named parameters。

 you can specify what the default separator is The separator between arguments to print。

 So recall that when I did quote unquote hello， comma or quoteote hello comma answer。

 it was separated automatically for us by a single space。

 even without my hitting the space bar inside of my quotes that's because the default value here is in fact。

 a single space。 the default value for end as promised is indeed backslash and and then there's some other stuff related to file Io that print can also deal with。

 but more on that perhaps another time。 There's one curiosity here in Python。

 it turns out that you can use double quotes or single quotes around strings。

 where in C it was much more regimented， double quotes are for strings and single quotes are for。

Chars characters only single characters， it doesn't matter in Python which one you use so long as you're consistent and stylistically you should really pick one and go with it。

 and the only time you should really alternate between the two is maybe if you want to put like an apostrophe for some human's name inside of double inside of single quotes or something like that。

 but generally you have a little more flexibility in Python and you'll see in different languages。

 Python community tends to use single quotes， at least in the documentation。

 the JavaScriptscript world tends to use single quotes we in CS50 often use double quotes just for consistency with what we do and C。

 but any community or company would typically have its own style guide that dictates which one you should use if only for consistency。

😡，Questions。Then。On this year print function。As just representative of all of the docks。That。

 you'll say。All right， let's take a quick look at variables。 We've used these a few times already。

 but let's focus in a little more detail on what's actually different in scratch。

 if you wanted to create a variable called counter and set it equal to0。

 you would use this orange puzzle piece here in C， you would do something like this。

 The type of the variable， the name of the variable and then set it equal to the initial value semicolon In Python。

 it's going to be a little similar， but you can probably guess where we're going with this。

 How is this line of code probably about to change。😡，Yeah。Good。

 we're not going to bother with int or the data type more generally。

 we're just going to say counter because obviously like a smart interpreter can just figure it out from context that you're putting a zero in there。

 it's obviously an integer and what else is about to go away。😡，The semicolon。

 So this is the C version andvoila。 This now is the Python version。

 and this is as silly as this example is it's kind of representative of how languages like Python just tend to be a little more programmer friendly because you just type this and get the same work done。

 All right， so if we wanted to do something now and scratch like increment， the counter by one。

 you would use this puzzle piece here in C， we could do something like this or we could do。😊。

But in C， we could do something like this in Python。

 it's going to be almost exactly the same except of course， no semicolon in C。

 we could alternatively do this and you can also do this in Python in C though。😡。

You could also do what other technique？Plus plus I'm sorry， but Python has taken that away from us。

 So if you got into the habit of using plus plus or minus minus that's great。

 use them in C all you want in Python， they just don't exist。

 So you'll see this more commonly instead as the heuristic All right what about the various types that exist in Python because even though you don't have to specify the types when declaring your variables they do in fact actually exist underneath the hood and it's worth knowing a little something about them because not knowing will lead often to some form of bug So in C we had types like this bull char double float in long and string。

 the last of which was thanks to the CS50 library but last week we would have start calling a string char star instead which it still is a data type the address of some char in Python we're gonna to whittle this list down to a subset of those essentially whereby we still have bulls。

 we still have floats， we still have ints and we do have strings。

 but they're literally called Sts ST。 So is's not a CS50 thing。

 The Python community called strings STrs but absent from this list is any。

Of star not to mention char star there are no pointers in Python and indeed as powerful as I'd hope you found weeks4 and five2 be。

 I dare say you also found them incredibly frustrating and challenging and want to yield bugs in your code because with that power of memory management comes a whole slew of potential mistakes that you can make and that's true not just for Cs50 students but for programmers。

 adult programmers， full-time programmers around the world and so among the other features of languages like Python is they try to take away certain features of languages like C that we're just too dangerous in the first place might be wonderful powerful might help you solve problems more quickly more precisely but if they tend to do more damage than they're worth sometimes it's worth just abstracting those details away。

 Similarlyly Java has references as some of you might know but does not have pointers per se you can't go poking around arbitrary locations in memory in the same way that you can with C。

 So let's take some of these data types out for a spin and see。What's the same And what's different。

 Let me go back to V S code here。 And let me propose that we bring back one of our old calculators from a while back。

 So let me clear my terminal。 close hello dot pi。 and let me go ahead and open up a version of this program that I brought in advance。

 which was our calculator version 0 from back then。

 So just to remind you one of the first versions of our calculator had the C 50 library。

 as well as the standard I O library。 And then we simply got an int using get int in week1。

 We got another int in week 1 using get int。 And then we simply perform some additions。

 It was a very trivial calculator that we did very early on just to demonstrate some of the operators and syntax of C。

 Well， let's go ahead and try converting this to Python by creating our own program calculator dot pi。

 So in my terminal window， I'm gonna write code of calculator dot pi。 It's going open another tab。

 which I'm just gonna drag over to the right just so we can see both side by side。

 I won't bother with say。😊。

![](img/d7777e514be9901928364ebea51b7b57_5.png)

![](img/d7777e514be9901928364ebea51b7b57_6.png)

Well， let's do it for parity here。 Let me copy the C code into the Python file。

 even though this will not work in the same way。 but let's keep what we need and get rid of what we don't。

 So instead of the slash slash for comments in python turns out the convention is to use a single hash symbol like this。

 So it's a minor difference。 It's half as many keystrokes。 So that's nice。

 but we're not going to include anything like this。 but we are going to do from Cs50。

 let's import a function that I promised would exist called get int。

 but we'll soon get rid of that training wheel as well。 We don't need main or this curly brace。

 we don't need this curly brace and we don't need all this indentation as a result。

 I'm going to move all of that over to the left。 I'm going to fix all of the comments to be python comments by changing the slash slash to hash symbols。

 And now I'm going to change each of these three lines of code as you might expect to the Python version。

 So you probably can guess already we can get rid of the int there and the int there。

 we can get rid of the semicolon here and the semicolon here。 we can get rid of the。

F in print F here。 And we can get rid of the semicolon here。

 And there's a few different ways we could do this。

 But I dare say the simplest is going be to get rid of the format code altogether。

 And that first argument and just tell Python to print X plus Y。

 So there's a few different ways we can do this。 But that's probably the most literal translation of the program at left to the program at right。

 Let's reopen the terminal window and run Python of calculator do pi and hit enter let's do something like x is one。

 Y is 2。 And hopefully we do， in fact， get3。 Allright， so that's all fine and good。

 But let's take off one of our training wheels now。

 So let me get rid of our C version here and focus just for the moment on Python。

 Let's take away this C code And what was the function we can use to get user input。😊，Maybe。

 it was called low Laer。It's just called input。 So let's get rid of C S 50s。

 get in already and use input。 instead。 Allright， so this program is much simpler already。

 So let's go ahead and reopen the terminal window， run Python of calculatedc up pi。

 do1 again for x 2 again for y and of course，1 plus2 equals。12。So what's going on here。

 because clearly this is a step backwards yeah。🤢，Yeah， so in the context of strings。

 plus represents concatenation， the joining of two arguments on the left and the right here。

 that seems to be what's happening because it's not 12 per se， it's more literally one。

2 concatenated together。 But why is that， Well， apparently the input function indeed returns a string。

 is those are the keystrokes that came back from the user might look like numbers and Arabic numerals to us 1 and two。

 but it's being treated as a string more technically like underneath the hood。

 there is some char star stuff going on there， even though we're not using that same terminology。

 So intuitively， what's going to be the solution。Without just reverting to using the training wheel。

 that is the get int function from CS 50。 put another way， how did CS 50 probably implement Get int。

 might you think， yeah。😡，Yeah， so recall that in C。

 we could cast some data types to other data types， typically int to chars or cha to ins。

 It's not quite as simple as casting in this case because underneath the hood thanks to our knowledge of C。

 there's a bunch of stuff going on。 There's probably a one and there's a null character。

 there's a two and there's a null character。 So it's not quite as literal as a cha to an int or an in to a char。

 So we're gonna more properly convert the et string or the stir to an int。

 we're not casting but converting and converting just implies that there's a little more work that has to be done。

 But thankfully， Python can do this for us。 In fact。

 let me go up to line4 here and say pass the well actually let's do it this a couple ways。

 Let's first convert the x value to an integer。 Let's convert the y value to an integer as well。

 So funny enough， it's very similar syntactically to casting but in C when you cast something you actually wrote the data type in parentheses。

 now the data type itself。I a function that takes an argument which is the stir or string that you want to convert。

 So let me go back to my terminal。 Do Python of calculator do pi enter type in one， type in2。

 And now I get back my three answer。 Now， as you might imagine， just like and see。

 we can kind of play around with where we're performing some of these operations。 and this looks。

 know， arguably a little less obvious now as to what is being added。

 So I really like the simplicity of x plus y just does what it says。

 So I could convert these in other ways， I could say after line 4， you know what。

 re change x to be the int version of x。 But generally speaking。

 that's kind of wasting a line of code by just doing something you could do on a single line。

 So let me delete that。 And instead just say that， well。

 if I know the return value of the input function is a stir。

 let's just pass that output as the input to the int function。

 and it'd be a little more pythonic So to speak， to just pass the input functions output as the input to。

Which is really hard to say， but we've done this in C。 just nesting function calls like this。

 All right， so if I run this one more time， Python of calculator I type in one， type in2。

 we're back now in business。 Now， what I won't trip over just yet is a subtlety that whereby I'm deliberately typing an actual numbers like one and two。

 but if you are following along at home or on your laptop if you were to type in cat and dog like bad things will happen。

 but we'll come back to that。Before long。Our questions， though。

 on any of this conversion of our strings to our。Integers in this case。All right， well。

 what more does Python offer to us。 Well， in addition to these data types。

 there's actually going to be a bunch of others， a few of which we willll actually use today。

 In fact， we'll see ranges of numbers like that's a thing built into Python。

 We'll see lists of numbers， which is gonna be like a new and improved version of an array that solves like all of last week's problems when we talked about the downsides of using arrays。

 There's gonna to be tuples for things like x comma Y coordinates or GPS coordinates or anything where we have collections of values。

 There's gonna be dis or dictionaries whereby you can have key value pairs provided to you without having to write a whole hash table yourself。

 and you can have sets which you can use to just contain unique sets of values that you just want to check for membership and there's bunches of other data types as well。

 And this is where languages like Python start to get really powerful because all of the。

Data structures we talked about in C。 we really only got from the language itself in array。

 everything else we had to build， or at least talk about building in class these now and more come with the language。

 Meanwhile， in the C 50 library for Python just so you know， there are a whole bunch of functions。

 these though were the C versions in Python， it stands to reason that we don't need as many because there's fewer data types in Python。

 but get flow get in and get string do all exist in the CS50 library for Python。

 you're welcome and encouraged to use it because indeed。

 among the goals for problem set 6 are going to be to redo some of your C problem set problems in Python where you can look at your own C code。

 and hopefully you like that solution and figure out how to convert it line by line essentially to the corresponding Python version。

 But clearly we've seen ways of taking these training wheels off quite quickly as well。 And in fact。

 if you wanted to import all three of those functions for a larger program， you could do this。

 just following the approach that I took so already。

But you can also just separate them by commas like this。

 or it turns out you can also import the whole CS50 library as you'll see in some code and then just access the functions within with slightly different syntax as well。

 All right， how about another construct from scratch and from C now in fact。

 in Python So scratch if we wanted to do a comparison like is x less than y where each of those are variables then say as much here in C it looked like this and nicely enough。

 you can probably guess already which what's going to change here like the F is about to go away the backslash n is about to go away the semicolon is about to go away。

 but some other stuff's about to go away as well， focus your attention on the syntax like parentheses and curly braces because in Python it's just that So we got rid of the parentheses because they didn't really add all that much logically we got rid of the curly braces。

 which technically we could do in C anytime there's a single line of code inside of a conditional but for consistency styyllistically we always use them as well Python though does not have you。

Any of those curly braces at all， but Python requires that you indent your code properly。

 So if you've ever been among those who are writing out your program and everything is just crazily like left aligned and just a big mess until style 50 swoops in and cleans it up for you you're not going to be able to write Python code like that anymore that's been such a societal problem among programmers。

 newbies and professionals alike that the language itself requires logically that if you want this line of code to execute if this Boolean expression is true。

 you've got to indent this line by convention for spaces。

 you can't be lazy and leave it all left aligned and sort of fix it up later this is made python code arguably more readable because of these languagebased requirements mean let's look at if else construct in scratch which looked a little something like this and see it looked like this which is kind of a lot of lines just to express a simple idea all of those same things are going to go away whereby in Python it looks like this instead and the only other difference worth calling out is that because you don't have the curly braces。

You do have a colon which precedes the subsequent indentation as well Meanwhile if we've got an if else if else in scratch in C。

 of course， it looked like this， a lot of this is going to go away in the flash of a screen。

 but there's going to be a curiosity which is not in fact a typo。😡。

Notice what happens with the elseif。 It's abbreviated L if。

 And honestly to this day all these years later， I can never remember if it's L if or elseif because different languages use different shorthand spellings of this phrase。

 It's L if in Python because that's maybe the most succinct you can make the two words themselves。

 But everything else is effectively the same， including the additional colon this time。

 But recall that okay， questions on。Any of those conditionals and syntax， yeah。What a good question。

 what language did they code Python in the interpreter we are using within VS code is itself written in C aka C Python。

 however you can implement a Python interpreter really in any language including machine code like raw zeros and ones if you have that much free time in assembly language which we saw briefly weeks ago。

 you could write an interpreter for Python in Python if you really want to be meta about it or in C++ or in Java this is the thing about programming language is you can use any language to create a compiler for or interpreter for another language what's going to vary is just how easy or difficult it is and how much time it therefore takes you。

😡，Good question， other questions。On any of these here features。Now，All right， well。

 let's do something a little bit different in Python Vi V C by opening up maybe a comparison program that we looked at some time ago。

 So let me go back to VS code here。 I'm going to close my calculator。

 And I'm going open up now from my distribution code today。

 a version of our comparison program from a while back， which was essentially the version 3。

0 index thereof。 So this one has comments， which is the very first one in week1 did not。

 but notice as a refresher what this comparison program was doing。

 It was including C50 do H and standard O dot H。 It was prompting the user for two integers by get int X and y。

 It was then doing a very simple comparison comparing x against y to determine if it's less than greater than or dot dot dot the same as。

😊，X the same or equal to the same。 So just so that we can go through the motions of converting one of these to the other。

 Let's do that side by side。 Let me code a program called compare do pi。 Let me close my terminal。

 drag the python version over to the right here。 And without comments this time。

 Let's just do from Cs 50 import， get in。 Then below that。

 that's do x equals get int and ask the user for what's X question mark。

 Then let's ask the user for y using get int。 quote unquote what's y question mark。 then below that。

 let's do if x less than y colon。 Go ahead and print quote unquote X is less than y。

 close quote L if X greater than y， go ahead and print， quote unquote X is greater than y else colon。

 let's go ahead and print out unote X is equal to Y。 So I dare say these are now equivalents。

 It's clearly fewer lines because a lot of the lines at left。Admittedly comments。

 but also some curly braces。 and there's more syntax like parentheses that we got rid of too。

 Let me open my terminal window。 Let me run Python of compare dot pi。 We'll type in one and2。

1 is less than X is less than y。 Let's do it again， using2 and1 X is greater than Y。

 Let's do it one last time。1 and1。 And of course， those two now are equal to。Each other。Allright。

 But why go down this road again because that was kind of a simple exercise。

 But recall that we introduced this comparison of int because it was so sort of stupidly simple。

 even if the syntax that that week was completely new。

 But we ran into an issue pretty fast when we started comparing strings。 And that was a problem。

 we really only fixed in week 4 when we finally revealed what a string actually is。

 So if we focus a bit more on Python strings， it turns out that。😊。

If we focus a bit more on Python strings， it turns out that we can solve that problem much more easily in the world of Python。

 In fact， let me go back to VS code here。 Let me close these two versions of int comparison。

 let me open up at left a version of my program that I brought with me here that contains a version from week2。

 wherein we finally reveal that a string is just a cha star， but recall that the solution in week 4。

 as well as in week1 when we first encountered this problem was to use stir comp。

 a function whose purpose in life is to compare two strings。

 character by character by character using a for loop or something like that。

 but they have knowledge therefore， of how to navigate pointers， how to look for the null character。

 the backlash0 at the end。 and all of that came from our friend string do H。 Well。

 how can we go about implementing the same idea in python。 Well。

 let's open up Vs codes terminal window， open up a new program called compare do pi。 But this time。

 let's get rid of the integer。😊，Version thereof let's get two ins from the user and I won't even use any c50 training wheels。

 Let's just use the input function to get S and ask the user for a value of s。

 So S colon close with a space T equals input as the user for a variable T and then let's just ask the question if S equals equals T then print out quote unquote same else go ahead and print out quote unquote different Let me move these side by side just you can see the difference notice how much code we have to write and how much we needed to understand in order to compare something is trivial is two strings in C。

 but in Python， we're literally just using equals equals and let's see if it actually works So Python of compared dot pi enter let's type in maybe cat for S and dog for T。

 and those are in fact different。 but we would have gotten the same answer in C let's rerun Python of compare do pi and type in cat type in cat again and now it's detecting them the same。



![](img/d7777e514be9901928364ebea51b7b57_8.png)

![](img/d7777e514be9901928364ebea51b7b57_9.png)

Wonderfully， Python has solved that seemingly annoying problem of not taking us literally。

 like don't compare the pointer against the pointer。

 compareare what a reasonable programmer probably really cares about the values of those strings。

 So the equal equals is doing all the four loop or the while loop iterating over those things character by character and actually giving us the answer we want。

 What else gets easy。 Well， let me close these two files。

 let me open up a program we wrote a while back that asked for the users agreement。

 So if I go in today's distribution code and grab agree to dot C here。

 we had a program that used get char at the time just to get a single character。

 yes or no from the user and then recall that after a bit of iteration here on line 12。

 we ended up checking fairly elegantly for both capital Y or lowercase y all in one expression。

 So it's sort of a combined Boolean expression using the vertical bars。

 the or operator to logically check if one is true or the other Otherwise we decided that the user did not。

agreegree because they didn't provide either of those their answers。 Well。

 how can we implement this in Python。 You can probably guess where this is going。

 but maybe not quite with the same syntax。 Let me open up a agree do pi and create a new program after dragging it over to the right。

 that's going to do S equals get let's just use the input function this time。

 Well use input quote unquote do you agree question mark。

 note that not on the list of data types in Python was any mention of char。

 Python does not have chars per se。 but that's fine because you can just use a string that has one character like and we could have been doing that all that time in Python。

 they just kept it simple and did exactly that。 Now I can say if S equals equals capital Y。

 And you might be inclined to do this But Python made things a little more readable in English and you literally use the English word or and just ask the same question。

 Does S equal equal little y If so go ahead and。Print out quote unquote， same else。

 if that's not the case。Go ahead and just print out quote unquote different。 So here， too。

 is a pythonic way of doing this。 And people tend to find Python therefore more readable because you can kind of read the code top to bottom left to right。

 And even though it's a little arcane and certainly not a human language。

 It does borrow inspiration more so therefrom。 So now we me need to run Python of a agreed enter。

 Do I agree。 Let's try big y first， that worked， let's try little y next。 that worked。

 Let's try n for no， that does not work。 and let's just try Y E S， which you might think should work。

 but doesn't， but that， of course， follows logically from what we've just done。

 But maybe there is a way to get a little more versatility here。 So it turns out in Python。

 besides stirs And besides ins and floats in a few other data types among them are lists。

 which again， are like the new and improved version of an arrays。

 recall that arrays and see we're just chunks of memory back to back to back that could store values of the same type。

 But you couldn't really。😊。

![](img/d7777e514be9901928364ebea51b7b57_11.png)

Resize them without jumping through some hoops， like copying everything over or asking reallog to give you more space。

 They were very limited in that sense。 And there were all sorts of tradeoffs there。

 as we saw in week 5， when it came to the efficiency of using arrays lists are essentially linked lists in Python whereby you get all the functionality we wished existed with arrays but built into the language itself。

 the ability to append data prepen data， search through data and generally perform operations without writing much code yourself。

 So with lists， we can actually solve even a problem like this， a little more elegantly。

 Let me propose that we go into if you were to go into its documentation。

 And here's the long URL therefore in the official docs python org site。

 you would find that you could do something like this。 let me go back into VS code here。

 clear my terminal。 And in this python version of this program。

 Let me go ahead and change this expression up here， to be a little more compact and。



![](img/d7777e514be9901928364ebea51b7b57_13.png)

Say， if S。Is in literally this list of values， why or let's do why or yes， literally。

 And then inside of that， if that's the case， let's go ahead and print out whoops。

 I forgot a double quote。 then if that's the case。 as before， let's do quote unquote， same else。

 If it's not the case， let's go ahead and print out as before different。 Now。

 this isn't quite what I want this program to do yet。 But let me run Python of agreed dot pi。

 and let's test little Y， that works。 little yes， that works。 But what's not going work yet。

 is capital Y， which did used to work in capital Yes， which did used to work。But logically。

 how might we solve this， Well， I do think we could certainly do like this and just keep adding to the list。

But think a little harder， what would be a better design than this， yeah。Yes。

 there a way to convert everything to the same case。 I mean in C。

 there definitely was recall that we could use the two lower or the two upper function to toggle between cases。

 but recall in C that was a little annoying because you could only do it one char at a time you can just pass in a whole string and let the function do its thing because there was no loop built into two upper or two lower。

 you would have to write that code yourself。 So totally solvable。

 but just kind of annoying like that is not an intellectually interesting program after like week1 or week two of a class like this。

 it just becomes a little too mundane， but if we just list all of the unique values in this list。

 whether in lowercase or uppercase， we can just canonicalize so to speak the user's input to be whatever we want。

 So for instance， if we want to force the userss input ultimately to be lowercase。

 no matter what they typed in， you can actually in Python do this S dot lower and we haven't quite seen syntax like this。

 we've seen the dot before， but in C recall that's how we got inside ofstructs and that's actually what's kind of going。

On here with Python。 It turns out that Python is， among other things。

 in object oriented programming language。 And those of you who took high school Java or other languages might have been encountered this phrase before object oriented programming or OOP for short。

 This generally means that。Data inside of a program isn't just raw data。

 It's very often an object that has attributes associated with it。

 as well as functionality associated with it， which is to say that these stir variables。

 STR for sure， they're more properly stir objects and they contain not only H E LLO or D VID or other such strings。

 they've also got functions built into them because the programmers who implemented to stir object gave them not only the ability to store actual data like the chars in those strings。

 but also a bunch of functions that can manipulate data in the world of C。

 you had string related functions but in separate libraries like the string library via string H。

 there was the C type H header file as well so you could do similar things but they weren't encapsulated within the data itself rather in C。

 you would take your variable and pass it to a function that someone else wrote in Python and in objectoriented programming languages。

More generally， you don't pass your variables to some other function。

 You use a function inside of your variables inside of those objects。

 So it's just a different way of thinking about it。

 was it's very similar in spirit to saying lower S。 but in this case。

 there's a tighter coupling between the piece of data。

 the string S and the functionality that it supports。

 So instead you write something similar as S dot lower and the way you know what functions exist is you would look up the documentation。

 for instance， for the string library and you would see on Python's website that oh string support lower and upper and capitalization and a whole bunch of other useful functionality that invariably involves loops and casting things to rather converting things from uppercase to lowercase or vice versa。

 but you don't have to write any of that code yourself。 So in fact， if we go back into VS code here。

 I think now we've made this program work better。 Let me do Python of a agree dot pi。

 let me say little y that worked， let me do big Y。That worked Let me do little yes， that worked。

 big yes。 That worked。 and even crazy things like big， little big yes。

 that too is tolerated because we're forcing everything to lowercase in the user's input。

 we can tweak this a little bit。 like if that's a little inelegant to have this extra line of code doing this。

 I would argue that you don't need a new line instead。

 just like you can nest function in the language like C and also in Python。

 you can also chain function calls together like this。

 If you know that the input function returns a string。 Well。

 there's no reason to wait until the next line to do something with that string。

 you can simply on this same line， say dot lower and chain one function call together with the next。

 because technically， the input function is returning to you a stir object。

 that stir object by definition of the documentation has a lower function associated with it。

 So you can certainly in one breath just use the dot operator there。😊，And technically。

 just to give you a bit more vocabulary， when a function is associated with an object in this way。

 such that you use the dot notation to call it， it's called a method instead of function。

 So those of you who did study Java or some other language， you've ever heard the phrase。

 method in Java is's just a function。 But it's one that's inside of or comes with an object。

 just a different way of viewing the world。Questions on terminology， syntax。Or concepts themselves。

Yes。Sure。对对对。A really good question。 If you're using a library。

 does it tend to slow your computer down if you're only using some of it。

 So short answer is it depends how well the library is implemented。

 So when you do something like from C50 import， get in Python。

 the interpreter is reading the entire C50 library。

 a file literally called C50 do pi that's installed somewhere on in the computer and it's only exposing the get int function for you in that case。

 So it's using the least amount of memory， but it is taking some amount of time。

 And if there are global variables defined in that file。

 they too will be potentially taking up space to in short， though。

 you can do intelligent things with libraries such that you're only loading certain resources on demand to minimize that impact。

 But at this point in the story when writing Python code for presumably the very first time。

 don't worry about those kinds of optimizations just yet。 until they're an actual problem。All right。

 other questions。On lists or on O， O， P in this way。Yeah， over here， sorry。On内。Absolutely。

 could we move the to the dot lower elsewhere？ Yeah， you could actually put it here。 dot lower。

 the upside of which is that you're only temporarily changing S now instead of permanently changing what S is。

 So arguably that's a probably better design here， too。And by changing it， I mean。

 what we were assigning to S in the previous version of this code was that S itself was going to be lowercase。

 And so in some sense， we've lost some information because no matter how the human typed it in。

 we have now forcibly change their input to lowercase。

 even though I might want to maybe print for them later on what it is they typed out or maybe populate some form on a web page or something like that。

 So I do like your approach of actually moving the lower here so that it's only changing it what's being compared and not actually assigning it to S in this case。

 All right， let me do one other example involving some similar concepts here。

 let me open up from a previous week， our version here of of copying。

A two variables from one to the other in C。 This was a longer program。

 especially once we started adding all of the input， all of the error checking。

 recall that this example some time ago was simply to copy one string into the other。

 And the very first time we tried copying a string by saying T equals S semicolon is we copied the pointers perfectly。

 But then we messed things up because we then tried capitalizing T。

 but that had the effect of capitalizing S also， but that's because literally S and T were pointing to the same characters in memory。

 And so we had to jump through hoops to using malloc and stir copy to solve this problem。

 So just to refresh you。 if you wanted to write a program in and C that copies two strings。

 you would first maybe get a string from the user and check for errors。

 you would get another string from sorry， you would then allocate memory for the copy by using malloc checking the length of the S and then adding one for the null character and still checking for errors。

 and then you would use stir copy to copy the characters of S into T's memory。😊。

AndThen you would go through after checking the string length and capitalize the first letter。

 and then you would finally print everything out and free。 Like this is such a simple idea。

 Like I want a program that just copies two strings。 It took 41 lines of code to achieve that N C。

 Now， again， in fairness I being hyperbolic because some of those are comments and curly braces and stupid stuff。

 But that's still a decent amount of code not to mention explanation just to solve something simple。

 So let's do this differently。 Let me open up a program called copy do pi。

 And in the Python version of this， which I'll put it side by side。

 let's try to do the exact same idea， create a copy of S and capitalize the first letter in the copy。

 So let's do S equals input and prompt the user for S as we've done before。

 Then let's go ahead and create a variable T and set it equal to S dot capitalizeize open print and close print。

 which is another function per the documentation that comes with stir objects。

 Then let's go ahead and print out。😊，Using print， let's see S colon。

 and then we'll print out the value of S。 and then let's print out t colon and print out the value of T。

 However， let's do this a little more cleanly。 It turns out even though this is the simplest looking way of printing this。

 F strings are kind of the go to approach these days。

 So I would say let's add some visual complexity， turn both of those inputs into F strings only to put the placeholders literally inside of the string we want to print。

 But again， there's nothing too juicy there。 Its just printing out S and T。

 if I open up my terminal window now and run python of copied do pi。

 I'll type in how about a high exclamation point in lowercase， hit enter。

 And now S is the same but T is changed。 So we've whittled down from 41 lines to like6 lines and technically four lines what I actually wanted to do here。

 So a subtle T。 It turns out， and this is worth knowing in general。 strings in Python are。

ally different from strings in C， because we saw in week 4 that you can change strings in C。

 like you can go to that address and force it to uppercase or even overwrite it with something else。

 in Python strings or what we call immutable。 you may not mutate existing strings。

 You can't go there and change any of the characters。

 They are meant to be constant once they are created in memory。

 So what's really happening here is this。 The input function is returning a new string or stir and assigning it to S。

 When I do S dot capital per the documentation， it's literally capitalizing the first letter in S。

 but not using S's own memory。 It's automatically creating a copy of S behind the scenes。

 capitalizing the copys first letter。 and then returning that copy and setting it equal to T。

 All of the stuff that I had to do manually with malloc and stir length and stir copy just automatically happening for free because this is such a reasonably useful use case。

😊，Questions， then。On this。Anything at all。Now， allright。 Well。

 let's do one final set of examples before。 I think it's time for some fruit by the foot。

 So recall that we've had cats meowing quite a bit over time。

 whereby it's worth introducing those again in the context of say loops。 So in scratch。

 we had loops in C， we had loops， let's see what kinds of parody we have with loops here in C。

 So in in Python。 So whoops，😊，So in scratch， recall that we implemented a loop with something like this。

 If I wanted a meow three times on the screen， I would literally use a repeat block in C。

 it was a little clunkier to mimic that same idea。 Like we could implement a variable called I and set it equal to 0。

 Then we could ask a Boolean expression is I less than3。 If so。

 print meow and then increment I using our old plus plus friend。

 which in Python is now gone in Python， we can do this almost the same except I don't think we need the data type。

 I don't think we need the semicolon。 We don't need the parentheses while still exist。

 We don't need the curly braces， and we can't use the plus plus we don't need the F。 I mean。

 we're mostly just trimming clutter from this here implementation。 So this is the C version。

 This now is the python version a little tighter a little easier to read。

 It's pretty much the minimal syntax available to get the job done。

 So how can we actually have a cat meow in this case。 Well， let me go into V S code。

 And I'll stop doing everything side by side and just stipulate that we've done most of these examples previously in C and。

In my first cat， Well， I could certainly do it the easy way。

 And let me go ahead and create cattop pi。 And like we always started in the past with。

 I could just do Miow。 And then our old friend copy paste。 And this， of course。

 was bad for bunches of reasons。 But it gets the job done in Python。 if I want to do this。 Well。

 I can just borrow that same inspiration。 And I could say， said I equal to 0。

 then do while I is less than3 colon， then go ahead and print out Miow。

 And then go ahead and do I equal rather， I plus equals one is maybe the most succinct way to express that same idea。

 All right， just to confirm that this works。 Python of cat pi enter Yaow meow， meow。😊，Alright。

 so how else can we do this and how can we do this more Pythonically， This is perfectly correct。

Many people might implement it this way， but it's not quite as succinct as we could alternatively do in Python。

😡，Yeah， so we could maybe use a four loop。 and in fact。

 let's go there because we don't quite have the same types of for loops in Python as we didn't C。

 while loops are essentially the same。 but four loops are actually a little bit different and actually a little bit better。

 So let me go into my code here to lead all four of these lines and literally just say four I in this list of values。

01 and2 colon print meow In other words， in four loops in python， you don't have the parentheses。

 you don't have the two semicolonons， you don't have the initialization and the Boolean expression and the update。

 you just say a little more English like for each I in the following list or for each value of I in the following list。

 And what python will do for us is automatically on the first iteration set I equal to0 on the second iteration set I to1 on the third iteration set I to2。

 And there's only three things in the list。 So that's it。

 And so just as before with the y and the yes example where I use square brackets similar to arrays and C。

 I was using。Python list of strings in that case here， I'm using a Python list of integers，0，1 and 2。

 and they're integers in the sense that they have no quotes around them。

 So they're obviously not strings。 And I'm printing out Mio this many times。 And indeed。

 if I do Python of cattop pi again， I get meow， meow， meow。 This is correct， this is arguably better。

 at least in the sense that it's two lines of code instead of4。

 and it's arguably more readable as well。 But what do you not like about this perhaps。

 Even if you're only seeing it for the first time。Yeah。

 it's gonna to be a lot more difficult to do things more than three times because recall in Python and scratch at least and in C。

 we had the ability to either express ourselves literally， or at least in C。

 we could just change that3 to any number we want 30300 no big deal It's a super simple change even though it was kind of annoying to type all of this out Well in Python yeah。

 I could do this and say for I and 0，1 and2 just to mimic the numbers that we'd be setting I equal to in the C version and frankly this can be any list it could be 123。

456 cat dog bird or any three things whatsoever， but I'm just using 01 and2 for consistency with the way C would have done it。

 but slightly better than this is to use one of those other data types that was briefly on the screen earlier。

 we have not just floats and ints and stirs and lists and tuples we also have what are called ranges and range is not only a data type in Python but more literally a function that you can call to get a range of values from0 on up So I can change。

This list of three values to a function call to a function called range passing how many things I want and by default per the documentation。

 I'll get back a list of numbers 0，1 and 2。 And nicely， Python's pretty smart about this。

 it technically doesn't hand you back all of the numbers at once。

 whether it's 3 or 30 or 300 or 3 million， its sort of hands them back to you one at a time。

 So you're not using more memory just because you're doing more iterations。

 So now if I do want to iterate four times five times 30 times 300 times。

 I again can just change this single value。 And if you want to be fancy too， you can skip numbers。

 you can go all the way through odd numbers or even numbers， you can change the incration factor。

 but the default and the most canonical is indeed just to count up like that。

 So if I go back to Vs code here and improve this， I can change that hardcoded list to just range of three。

 clear my terminal， run this cat one more time。 and now I'm back in business as well。 In fact。

 this is so common。 let me throw up one alternative to this。

 you'll notice that in the previous example。

![](img/d7777e514be9901928364ebea51b7b57_15.png)

Within B， S code and on the screen， I am not actually using I in any way。 In fact。

 if you look back at how we converted the scratch to Python code。

I'm using I because when you use a for loop in Python。

 you have to give it a variable in some list or range of values。 That's just the way it is。

 but I'm technically not using or printing I anywhere。 And that's fine。

 And so it's arguably pythonic too。 if you have a variable out of necessity。

 but you're not actually going to use it for anything useful， just call it an underscore instead。

 And even though this is weird looking an underscore is a valid symbol for a variable name in Python。

 So it is pythonic to just use this just a signal to yourself later and to colleagues that yeah。

 I'm using a variable because I have to， but it's not one I'm actually going to use elsewhere。

 It's a minor subtlety and not strictly necessary， but。Perhaps commonly done。All right。

 how about a couple final versions of cats then。 So recall that if we wanted to do something in scratch forever。

 we had a forever block， which literally did that。 Well， in C。

 we couldn't quite translate that literally。 So the closest approximation was probably this while true。

 whereby you have a boolean expression that by definition is always true。

 So the loop is never going stop there infinite， if you wanted to print out meo meow on the screen add nausea。

 in Python， you can do it almost the same。 but the curly braces are about to go。

 the F is about to go， the backslash and the semicolon in the parentheses。 but for whatever reason。

 in C， we lowercase true and false in Python， we capitalize true and false。 So a minor subtle T。

 but it's now indeed capital T。 But the indentation has to be the same And the colon has to be there as well。

 So with that， we can of course， induce intentionally or otherwise some infinite loops as with C。

 you can break out of them if need be with control C to interrupt the process。 But let's just see。

Lastly， with this cat， how we can make it a little more abstract。

 like the final versions of our cat in scratch and C。 So let me propose to open up here。



![](img/d7777e514be9901928364ebea51b7b57_17.png)

In a version of cat that we looked at that we wrote in the past， it was version 12 at the time。

 which looked a little something like this。 This was one of the final versions of our cat and C that simply allowed me in main to call meow function that took an argument。

 which is the number of times I wanted it to meow。 This in C is how we implemented that helper function。

 So to speak， that return nothing。 So its return type was void。

 But it did take an integer called n as its input。 and then there was a for loop inside of there that printed meow that many times。

 So long story short， this was how both in scratch and and C we invented our own functions。 Well。

 how can we do this now in Python。 Well， let me bring this version of cat over to the right here。

 delete that previous version and let me propose that we do this for I in range of three let's go ahead and assume for the moment that there is a meow function in scratch whose purpose in life is to just meow on the screen。

 Well， that， of course， does not exist。So in Python。

 I'm gonna use a trick that allows me to define my own function。

 And the keyword for this is literally deaf for define the name of the function。

 and then parentheses。 if it takes no arguments。 You don't need the void keyword even if it takes no inputs。

 So let's do a simpler version of the cat first that takes no arguments and then we add back that argument。

 how how does a cat meow， it literally just says meow on the screen。

 So already we seem to be an improvement， I've got like four lines of actual code here versus like 20 or so on the lefthand side。

 let's go ahead and run Python of cat dot pi enter。 and we see the first of our errors。

 which is remarkable because usually I would have messed up by now。

 So here we have in Python the equivalent of like a compiler error message。

 The program has not run It's tried to run。 It's tried to be interpreted。

 but it encountered some error。 These are generally called tracebacks in the sense that you see a trace back in time of everything the program was trying to do just before it failed。

 So if you call it the function， which called the function， which called。

You'd see all of those function calls on the screen。 I've just tried to call one function。

 So it's a relatively short error。 This is clearly a problem。 And here's the type of problem。 Name。

 error。 The name Yao is not defined。So intuitively， even if you're seeing Python for the first time。

 why iso Mio not defined， even though it's literally defined。Right there。Yeah。Yeah。

 as smart as Python is Vi V C still kind of naive in that Miow doesn't exist until line 4。

 So if you try to use it online too too soon。 Alright， so in C。

 we fix this problem by initially just kind of hacking things together by just all right， well。

 let's just define it up here and then move that down there。 And that's totally reasonable。

 And in fact， if I clear my terminal and rerun Python of cat do pi， we're back in business。

 But I'd argue you can only do that so many times， especially once you've got a bunch of functions。

 you don't want to relegate like the main part of your program。

 which really this loop is to the very bottom of the screen。

 if only because like that's the first thing you care about， I want to see at the top of the screen。

 That's the whole point of putting main at the very top。 So what was the solution in C。

 the solution in C was to put the prototype for the function at the top of the file。

 that though is not a thing in Python。 You don't just copy that first line of code put it at the top of the file at a semicolon and then it works。

Instead， the pythonic way to solve this problem for better or worse is to actually put your code in a main function。

 main and Python has no special significance in this sense。

 it's just convention to borrow the name that so many other languages use as the main function in those languages。

 but you just wrap your function in a function main so that you're defining main。

 then you're defining meow before you're actually using the meow function per se。

 But I have made a mistake。 If I run Python of catta pi now， cross my fingers for good measure and。

Now， the program does nothing。Why is that？Yeah， why is that。Oh， sorry， God ahead。Yeah， curiously。

 I never called the main function。 So whereas in C and in Java in C plus plus in a bunch of other languages。

 main is special。 Like main is the function by definition that is automatically called Python has no such special magic。

 It's not gonna call main for you just because you created。 In fact。

 I didn't even even can call that main function， main， it's just a convention。

 But the solution is exactly that。 Well， if the problem is that main wasn't called at the bottom of this file。

 What I can do is just literally call main， which we would never have done in C。

 But this is conventional to do in Python so that after you've defined main up here。

 And then define meo down here。 Now you can call main， which in turn will call meow。

 But at that point in the story， both of those functions functions exist。

 So if I go down here and run cat do pi again， now I see my meowowow。 Now。

 let me add one final flourish， because this version of the code in C recall。

 actually let me specify how many times I want to meow。😊。

Whereas here I actually have my four loop in main at the right and I'm calling now that many times。

 Well， what if I want to get rid of this loop over here and deindent meow here and pass in literally the number three here。

 Well， in Python you can just say inside of the definition of a function that it takes an argument like N you don't have to specify the data type Python smart enough to figure it out then in your function。

 you can use that as with for I in range of n go ahead and print meow。

 So now the righthand version of this program is pretty much equivalent to the lefthand version of this program as always using fewer lines of code。

 let me go ahead and run Python of cat up pi meowowow we're good and then let me make one final change if only because most every documentation you see online or website tutorials on Python will actually have you not just literally call main at the bottom。

 but you'll do this crazy syntax that is solves a problem that we won't trip over in this class but typically。

Pythonic to actually call Ma after asking the question if name underscore underscore equals equals quote unquote。

 underscore underscore main， underscore underscore colon Ma。

 this is a stupid mouthful of code that even I had to think about when I was typing it out if I got all the underscores correct。

 but long story short，😡，This convention of using a conditional before you call mainine allows you to write more modular code in Python so that some of your files don't actually do anything other than defined。

 defined， defined， defined functions that you can then import into other files you write。

 So in short， this is the right way to do it， even though in CS 50。

 it is unlikely that we are to trip over this bug。Questions now on that last piece of how we define functions in。

Python， yeah。Good question。 and good eye。 Why do I have two lines between my functions in Python。

 As you will see via style 50， It is Pythonic。 that is Python convention to separate functions in your code by two lines。

 whereas there is no such convention in C， So I'm trying to be consistent with what the world does yeah。

😊，If you want to count backwards in a loop， can you do that， Abutely。

 you could use the range function in a different way。

 start start with a much larger value and count down how but you could alternatively do that with a while loop。

 I would say that， yeah， you can make that work， but you shouldn't。

 It just people don't do that unless it does actually solve a problem for you。

Other questions on this？Al right， Well， when we looked at seat， recall。

 there was a bunch of things that ultimately like we couldn't do well。

 We had rannot issues of like photo loading point precision and integer overflow and truncation and like all of these world's problems。

 Theres still going to be some of those。 But first， let's take a fruit by the foot break。

 and we'll be back in 10。 Help yourself the seconds today。Alright， we are back。

 And let's consider our remaining time。 not only what Python can and can't do V B。

 but also some of the more powerful features that will let us solve much more interesting problems before long。

 So recall this example from like week one of C S 50。

 wherein we implemented a simple calculator that didn't just add numbers together in this version。

 it divided and recall that we ran into this weird issue early on in the class whereby。

 if I opened my terminal window here and compile this with make and then do damn it。 sorry。😊。

Not good at starting class， it seems today， why did we do that？嗯。Okay， let's start that over， sorry。

All right， we are back。 So before we dive into some specific examples。

 let's consider some of the I didn't want to say that either， sorry。All right。Third times the charm。

 All right， so we're back。 And let's use our remaining time together to focus not only on some of the problems that Python can solve more readily than C。

 but also some of the problems that remain。 So here was a program early on in our discussion of C that had this weird bug whereby when we implemented a relatively simple calculator to divide two numbers。

 x divided by y we experienced what we called truncation at the time。

 whereby one divided by3 was curiously0。 and like something like four divided by3 was curiously one。

 and we were losing everything after the decimal point。 And this was true。

 even if we tried using floats because with truncation recall。

 everything after the decimal point with integer math is simply discarded。

 So if you do int divided by int， you're going to lose what is after the decimal point。

 So let's take a look in Python， whether this is still actually a problem。

 So let me go back into B S code here， we'll close out the C version thereof and let's。😊。

ahead and create our own program called calculator dot pi。 And in this version。

 let's modify the original， which just did some addition and instead have it do some division instead。

 I'll get rid of my outdated comments and perform now division instead of addition by doing x divided by y Python of calculator pi。

 let's try one and let's try3 and oh， our fractions are actually back。 So it turns out in Python。

 even when you're manipulating integers。 if you divide one by the other。

 And the result logically should actually be a floating point value。 that's what， in fact。

 you're going to get back。 and you don't have to jump through the same hoops that we did before to actually force things to floats and then do floating point arithmetic and so forth。

 In fact， if you want the old behavior。 It's still actually there。

 and you can use two slashes in Python to use the old integer division as opposed to what we're seeing here。

 But a typical programmer， I dare say nowadays would want to behave in exactly the same way。

 So truncation seems to be less。Therefore of an issue for us。 All right， Well。

 what other problems did we encounter at the time。 Well'll recall。

 we had issues of floating point imp precision whereby even when we divided something simple。

 like one divided by3 and in grade school， we learned that was like 0。

3333333 repeating infinitely many times。 we started seeing weird numbers that we're not3 at the end of that value back in the day and C。

 unfortunately， that's a problem that's still with us。 In fact， if I use this same program here。

 let me go into VS code， And instead of printing out just x divided by y。

 let's go ahead and do this temporarily， let me give myself a variable called Z and said it equal to x divided by y。

 only because it'll be a little easier to see the formatting trick I'm gonna use。

 let's go ahead and print out a format string that prints out Z。 And for the moment。

 let me just claim that this is going to do the exact same thing。

 It's just completely gratuitous that I'm using an f string now as opposed to just printing out Z。

 But if I do one divided by 3， we're still seeing 0。333。 But we're only seeing just over。

10 or so digits here。 What if we want to see like 50 digits and really start poking around at what's being represented。

 Well， the syntax is a little weird。 But in Python using an f string。

 you can do tricks similar to what we did with the percent F with print f and C And if after my variabless name in this set of curly braces。

 I do a colon and then a dot because I want to see numbers after the decimal point and say something arbitrary like show me 50 digits after the decimal point and treat this as a float。

 This is a crazy incantation， I do think of a format string。

 even I am sort of cheating off of the paper in front of me。

 But this is how you format strings if you want to see them with a little more precision。

 or so I think if I rerun Python of calculator pi and do one divided by three darnnet。

 we're still in the same mess that we were before。 Now， why is this。 Well。

 it's still the case that I'm running the code on the same kinds of computers that I did before。

 It's still the case that this computers only have a finite amount of memory。

 And so even though I'm manipulating clearly floating point values， Python is only。

Allocating say 64 bits to those float variables。 And so there's only so much precision that's possible。

 And so what we're seeing is essentially the closest representation to an infinite number of threes that we can represent using binary using a floating point representation therein so still a problem but I do think in Python you'll find that there's so many more libraries out there。

 thirdparty software that comes not just with the language itself but from others whereby you can use libraries for more precise scientific computing that essentially implement their own versions of floating point value so that you can use not 64 but 128 or more bits than that when it really matters to some level of precision Thankly though one problem is at least solve for us namely integer overflow。

 So recall that this was another problem we ran into whereby if you try counting higher than say 4 billion or even higher than 2 billion if you representing negative numbers which have the total range that you have available to in the positive range we ran into the situation where somehow。

Wpped around， became negative and then even ended up being zero as a result。 Well。

 Python wonderfully nowadays just gives you more and more bits as needed。

 if your integers are getting larger and larger。 So this is a wonderful feature and that we've at least addressed one fundamental limitation we ran into in C。

 And this time the language itself provides us a solution。

 Python2 has some pretty handy features as well。 One of them is what are called exceptions。

 And so an exception in Python is a way of handling error conditions。

 without relying on return values alone。 So recall that in C。

 if you ever wanted to signify that something went wrong。

 you have to return like most recently like null N， which was a special sentinel value， technically。

 it's just a zero address。 and by checking for that you can make sure that you know if you're getting back a valid pointer or not。

 And in other functions。 if something went wrong， you might similarly have to check the return value。

 maybe checking for0 or negative one or one or something like that。😊。

But return values were the only way in C that functions could communicate back to the programmer that something went wrong。

 And this is problematic because if you imagine implementing a function that's supposed to return maybe an integer。

 whether positive， negative or zero， it's kind of unfortunate sometimes if you have to steal one of those values and say you can't use this value。

 It's fine in the world of pointers because the world decided years ago。

 we're never going to use the actual address Ox0， these zero address。

 but that's still technically costing us one or more bytes of space。 But in general。

 it's a bit annoying if your function can't truly return all possible values。

 Think about a function like get string if something went wrong in get stringing。

 what do you want to return。 Well， we saw in the Cs50 library， we do。

 in fact return null once we introduced that but in general。

 wouldn't it be nice if functions could somehow signal out of band。

 so to speak that's something went wrong。 So by that。

 I mean this let's go into new program that's inspired by one of our programs today。And in V S code。

 I'm going go ahead and close my calculator。 open my terminal window and create a new program called integer dot pi。

 So in integer do pi， let's just play around with some integers and see what we can break。

 So here I'll define a variable called n and set it equal to the input function。

 which comes with Python just asking the human for some input。

 Then I'm going go ahead and ask a question。 I the user's input numeric。

 and it turns out if you read the documentation for strings in Python。

 they come with not just an upper function a lower function。 A a methods。

 but also it is numeric function or method that tells you whether or not the string itself happens to be numeric。

 that is looks like a number。 Allright， so I think if I do that I could then do something like this。

 if n is numeric， I'm going to go ahead and claim that in fact， it is an integer。 else。

 if it's not numeric， I'm going to claim that it's not an integer。 I have no idea what it is。

 maybe it's cat， maybe it's dog， maybe's a mix of numbers and letters。

 but it's definitely not an integer as defined by a sequence of decimal digits in this case。😊。

All right， so let's try this out， Python。Of integer dot pi enter。 We'll type in  one。

 That's an integer。 We'll type in 2。 That's an integer。 We'll type in 0。 That's an integer。

 type in cat， not an integer。 So that seems to， in fact， work。

But what if I wanted to immediately convert this to an int as we did in the past。

 And so let me modify this a little bit here and say instead this n equals not just input past the user for an integer。

 or rather， let's just ask them more generally for input。

 But let's assume that we want to convert this input to an int。 And actually。

 we can go ahead and say integer here。All right， well。

 here I'm going to go ahead and just print out the claim that yep。

 this is an integer because if we get to line2， well。

 clearly we've handled the user's input correctly。 In other words。

 how can I get rid of constantly checking the return valid sorry。

 how can I get away from constantly checking the return values of functions to make sure it is what I expect。

Alright， well， let's go ahead and run Python of integer pi now。 enter， type in one。

 tells me it's an integer。 type in 2 tells me it's an integer 0 tells me it's an integer。

 type in cat。 Notice this time what goes wrong。 whereas last time we saw this kind of traceback error message。

 It was a name error because I was using the meow function name too early。

 now I'm getting a value error， which is a different type of error that relates to invalid literal for int with base 10 cat。

 Now that's a mouthful。 So unfortunately， Python's error messages aren't all that much better than clang's error messages。

 but clearly， the interpreter does not like the fact that I'm passing something to int related to base 10。

 but that's quote unquote cat。 And really the best you can do with this kind of error is realize like okay。

 it's clearly the case that cat is not an integer， So it's having trouble converting cat to an integer。

 It makes no logical sense。 Allright， so what's the gist of the problem。 Well。

 I'm just blindly converting the user's input to an integer。 even if。It's not input。

 even if it's not an integer。 Well， all right， Well。

 I could rewind to the previous version of my function。

 use the isnumeric function and then conditionally convert it。

 but I'm trying to move away from constantly checking return values of error messages。

 And wouldn't it be nice if I could somehow catch this value error and just deal with it if it happens。

 and in fact， you can with Python exceptions which exist in other languages as well。 Java among them。

 you have the ability to sort of listen for errors happening inside of functions without having to rely on return values alone。

 So let me go back to VS code here， clear my terminal。

 just to simplify things a bit and let me literally say to the interpreter。

 please try to execute the following two lines of code。

 except if something goes wrong like a value error in which case。

 go ahead and print out something like not integer。

So wouldnn't it be nice if you could just wrap all of the code you've written in CSs50 thus hard with try and sort of ask the computer politely like please try to execute this code。

 but that really is the semantics behind it。 Try to execute these lines of code except if there's an error then do this other thing instead and therefore you don't have to check any return values。

 you can just blindly pass the output of the input function as the input to the int function knowing that if something goes wrong inside of there。

 Python is going to execute this code instead except when something goes wrong。

 So let me go ahead and run Python of integert pi now。

 I'll type in one and that works because it's trying to execute line2 and succeeding。

 Its trying to execute line 3 and succeeding。 So lines 4 and4 never actually kick in But if I try again here with cat line 2 is going to fail line 3 is never going to get reached because Python is immediately going to jump to this exception handler so to speak。

By catching the error or the exception and printing not integer instead。

 So it's a little bit of a weird convention。 It's different from what C offers。

 but a lot of newer languages nowadays do offer this because it's a better way of just writing code that。

 you know should work 99% of the time。 But if something does go wrong out of memory， the human type。

 something wrong in or something like that， you can handle all of those exceptional cases。

 Except in a bad sense using this except keyword instead。Questions on。Any of this here technique。

Yeah。A really good question。 In this case， I used a value error。

 Do I need to define every possible thing that can go wrong。 short answer。 Yes。

 now there aren't terribly many。 There's some standard ones， and they're all capitalized in this way。

 capital letter， capital letter， something error typically you can even invent your own and it's good practice to enumerate the kinds of things that you think can go wrong。

 value error is pretty generic， but there could be memory related errors there could be file not found related errors。

 there's a bunch of different exceptions that are all documented in Python that you can listen for。

 That said as nice as Python's documentation is overall。

 It is not good at documenting for specific functions。 What exceptions they can throw。

 And I've never understood this after all of these years that no human has gone into the documentation and painstakingly enumerated all of the possible things that can go wrong。

 What's too often the case in the real world with some of my own code included is if you encounter an exception that you didn't think was gonna happen。

 You go in and improve your code and add to this list of except clauses。 What else might go wrong。

 shouldn't be that。And different libraries are better about documenting these things。All right， well。

 with that in mind， let me propose that in the C 50 library for Python get int and get float。

 They work just like the C library。 whereby if you type in cat or dog or bird into those functions。

 they just reprompt you。 They just reprompt you and long story short。

 this is the kind of code we wrote in Python， try to get input from the user except if something goes wrong。

 Pro them again， prompt them again。 So we too are using precisely these features even though it wasn't something that was available to us in C。

 All right， but something else that we did't see was play around with Mario in a few different forms。

 And in lecture recall a few weeks back， we experimented like using some ASI arts some very simple text to print out something like this pyramid of height3。

 Well， how can we go about printing something like this。 Well。

 I would propose that if I go back to BS code here， let's close out my integer examples。

 code up a new version of Mario in Mariio pi。 This one's kind of simple。

 I can say something like for I in range of three， go ahead and print out quote unquote a hash down in my terminal window。

 Python of Mariio。😊，I've got really the closest analog to three bricks stacked on top of each other in this way。

 But in C， and eventually our implementation of Mario started to get a little fancy。

 And we started to prompt the user for the height of the of the wall。

 And therefore we could have not just three， but maybe4 or even more bricks being printed。

 So let me actually open up that version from a few weeks back。 whereby from week1。

 we had a version of Mario that looked like this。😊，Whereby we。

 after including some header files declared in main a variable called n。

 Then we saw a new construct at the time， a do while loop that just keeps using get in get in get in。

 so long as n is not one or greater equivalently so long as n is less than one and kept prompting the user again and again。

 The reason for having n up here recall was issues of scope。 therefore。

 it's accessible lower in the function as opposed to it being confined to those curly braces。

 And then down here， we use the four loop to actually print out that many hashes。 So in short。

 the do while loop solve the problem and C， whereby you want to get user input at least once And maybe again and again and again。

 if they don't cooperate the first time。 And that's where do while loops really shine。

 do something at least once， and maybe again again and again。 Otherwise。

 it's a little more annoying to do it with while loops or four loops。 Unfortunately。

 Python does not offer a do while loop。 And so here too。

 we have an opportunity to introduce you to the world would call Pythonic。😊。

What is Python solution there， too， Well， on the right hand side here in Mario dot pi。

 let's change this a little bit。 And let's do from let's go ahead and do while， whoops。

 while true capital T。 Go ahead and use a variable n， set it equal to int input。

Height asking the human for the height of the wall。

 And I'm gonna just cross my fingers that they're not gonna type in cat or dog or something that's not an int in this case。

 I'm gonna say if n is greater than 0， that is a positive number， that's useful。 we can proceed。

 I'm gonna now break out of this loop。 and then lower in the file。

 I'm gonna say for I in range of N go ahead and print out the hashes。

 So we still have that same lesson as before。 like the Python version seems to be shorter。

 more concise， even if you ignore the comments on the lefthand side。

 And I've completely avoided using a do while loop。

 But there are a few things that are different nonetheless。

 that feel like versus C shouldn't even work。 Like what's weird about this solution。

 even though I think it's actually correct。😊，Yeah。I have to。Okay， so it's not correct。

 That's one of the first things to point out。 So too many prepositions for this was supposed to say for I in range。

 Okay， so now that this program's correct， what looks weird to you and probably could break it， yeah。

Yeah， so the n variable should be。 it seems to be scoped to the while loop at least inofar as it's indented inside the while loop。

 which feels analogous to being inside of curly braces in C。

 And so it seems weird that I'm presuming to use n online 6。

 even though it was only defined online too it turns out this is possible in Python the issue of scope that we encountered in C is not as rigorously enforced。

 we'll say for today such that when you define n up here you can actually use it down here。

 And you can think of this as being a little reasonable because if there's no more specification of what data type n is and no more semicolon just imagine it would look kind of stupid if you just put a blank n there and hit enter just so it kind of there's no way to express the idea of create this variable in advance without actually assigning it a value。

 whereas in C we could do that。 So this is， in fact， okay and correct。 What else is going on here。

 Well instead of a do while， we're kind of just implementing the idea of it。 I'm just blindly。

Inducing deliberately an infinite loop， like do the following forever。

 but then as soon as I have the answer I want， like a positive integer from the human。

 break out of this loop， and this is indeed the pythonic way to say get user input because this will minimally ask the user for a height once and maybe more and more times。

😡，So no do while loops， only while loops and four loops and only while loops are really the same as in C。

 even four loops we've seen are a bit different。 Alright， well。

 how about instead of just that Mario example， recall this one where we wanted to print like four question marks in the sky side by side。

 Well， we can do this in a few different ways。 Let me go back to V S code。

 Let me close the C ver whos。Let me go back to V S code， close the C version。

 and let's just completely change Mario do P to implement this now。

 I want four question marks in the sky。 So I think I can do something like for I in range of four。

 Go ahead and just print out quote unquote， question mark。Do you like this， Python。Of Mario dot pi。

 Should I run it。 No why。This is how I did it in C， yeah。Yeah， I got to edit the end value。

 the named parameter for the print function， because otherwise if I hit enter。

 they're all on different lines， which is not the effect I want when all four question marks are meant to be side by side。

 All right， well， that's an easy fix， I can pass the named parameter called end geek into the print function set it equal to quote unquote with double quotes or with single quotes as always stylistically。

 I would be consistent。 So I'm gonna to use double quotes。

 even though the documentation is consistent with its single quotes。

 now I'm gonna rerun Mario of Python Mario pi。 And I'm so close， now they're on the same line。

 but the stupid cursor didn't move to the next line。 that's fine。 how to fix this。 Well。

 just logically， I can put a blank print statement below。

 And even though I'm not passing anything in， you get a new line for free when calling print。

 So even though I'm not passing in in the arguments I am getting the aesthetic effect that I want。

 So that is a perfectly reasonable way to do it。 Now， if you feel yourself becoming a bit of a geek。

 though in learning about Python and previously see。 you can even solve。😊。

This problem even more pythonically by saying print quote unquote question mark times4 using multiplication similar in spirit to the plus operator for concatetnation。

 and now multiply the exclamation point by itself four times。

 So now if I go down here and run Python of Mario pi。

 I get a very elegant solution to exactly that same problem even more concisely than my previous version。

 What if I want to do something in two dimensions。 Well recall that we move to the underground of Mario brothers here。

 And we had like a three by three grid of bricks。 How can we do that one and see we had nested four loops using I and J back in the day。

 And I can do the same thing in Python。 let me go back into V S code here。

 and let me do one outer loop for I in range of three。

 Then let me do an inner loop for J in range of three。 then let me go ahead and print out a hash。

 but let me learn from my past mistakes， I don't want to print out a new line every time。

 So let's override that default。😊。

![](img/d7777e514be9901928364ebea51b7b57_19.png)

![](img/d7777e514be9901928364ebea51b7b57_20.png)

But after each row， let's print a new line so that down here， I can go in Mario do pi run it。

 and I've got my three by three grid of bricks。 I could change this a little bit and call this row and column even though here to even more。

 So I'm not literally using row and column anywhere explicitly。

 but semantically it kind of explains maybe a little clear to the reader what's actually going on。

 So that might help。 but we can tighten this up too if I just want to print a three by three grid。

 well， I know that the top thing here will iterate three times and I know how to very elegantly print things out with a one liner。

 so I could just print out a hash times three in this case。 and then down here。

 I can go to Python of Mariio pi and voa I'm back in business to。

 So it's just sort of easier to do these kinds of things and express yourself all the more succinctly。

 Well， what else can we do。 Well， it turns out in Python that unlike as。

 you can ask lists how long they are。 So you don't have to keep around a variable of how。😊。

array is you can just add stuff to a list and then ask Python how long is this list。

 How many elements are in it。 case in point， let me go back to BS code and clear out Mariio pi。

 and let's reimplement from a few weeks back， the notion of calculating like in the average quiz score that you might have in a class。

 So in score do pi let's go ahead and create a program that's got a list called scores of three scores that we've seen before。

72，73 and 33 and recall that we tried a few weeks back and see to average these together。

 And to do that we had to add them all together。 we had divide by the total number of elements in the list wasn't that hard。

 it was sort of like grade score arithmetic to calculate an average。

 but Python has more functions available to us not just length but even summation。

 So let me go ahead and do this。 let me say that my average variable shall be the sum of those scores divided by the length of those scores。

 And indeed per the documentation。 Python has a length function LN for short a sum function which take。

which adds together all of the elements in that list。 And so down here now。

 I can say something like print with an F string or format string that the average is whatever that value is。

 and I don't have to do any loops or math myself。 I can just call the function like I could in Excel or Google sheets or Apple numbers Python of score do enter and my average is in fact。

59。3333 and then some weird imprecision at the end there。 And in fact。

 just for consistency with our C code， let me rename this。 I'm going rename score to scores plural。

 that's gonna close the window， but now at least you'll see online that we have a program indeed called scores。

 Well， this is not that interesting because I've just hard coded my 72 my 73 and 33。

 What if we want the human to be able to type that in。 Well。

 I think we can do that too So let me actually open up that version of the file now pluralized let me go ahead and not initialize the list for the human but let me set it equal to an empty list just using an open square bracket and close square bracket like an。

That has nothing in it。 But this one is literally of size 0 at the moment。

 And now let me do for I in range of， let's just for now， ask the user for three scores。

 even though we could certainly ask the user how many scores do they want to input。

 and then use that number instead So in each of these iterations。

 let's ask the user for a score using something like int input score。

 I'm going set aside the reality that if the user types in cat or dog。

 the whole things gonna break and therefore I should really add my try and my accept。

 But I'm gonna discard that error checking and focus only on the essence of this program for now。

 now after line3， if I have in a score variable， the users quiz score。

 how do I put it into that array。 Well in in that list， Well， with an array。

 I had to use the square bracket notation， keep track of how big it is and use like bracket I or something like that。

 no longer in Python because a。List is an object that has not only data， but functions。

 A K A methods associated with it。 I can just call a method that comes with every python list called a pen and pass in that score using that same dot notation as before。

 The rest of my code can stay exactly the same。 If I now run Python of scores do pi。

 and I type in 72，73，33 manually， though， I still get that same average。

 And notice I did not need to decide in advance how big that list of scores was going to be sorry。

 let me fix one thing。😊，I did not have to decide in advance how big that list is going to be。

 Que on what we've just done with lists。No， all right。

 Even cooler for some definition of cool is that we can now implement hash tables or more generically dictionary sets of key value pairs by just using a data type that comes with Python。

 I claim last week that like that dictionaries are in hash tables in particular or sort of the Swiss army knives of data structures in that they just let you associate some piece of data with others with Python。

 you do not need to jump through the hoops that you needed to with problem set 5。

 implementing your own spell checker in your own hash table。 You just create a diic object in Python。

 a dictionary that gives you the ability to associate keys with values。 So case in point。

 let's do this。 Let me go back into Vs code and close out scores do pi。

 And let's create a new and improved version of our phone book in phone book pi。

 Let's go ahead and come up with a list of names just to demonstrate how we could store a bunch of names in the phone book。

 irrespective of numbers and set those equal to say Kelly's name and my name and John Har's name just by putting for quoted。

Strings or stirs inside of this list。 Now let's ask the human using the input function for the name that they want to search for in this list。

 and now let's implement linear search using Python。 I can do this in a bunch of ways。

 but one way is to say for each name we'll call it n in names go ahead and ask the question if the name I'm looking for equals the current name in the list that I'm iterating over。

 go ahead and print out just something generic like found and then break out of this loop。

And let's see if we can find Kelly or David or John or someone else。

 Python of phonebook do Pi enter searching for the name， say David enter。 and it was in fact， found。

 Let me go ahead and search for someone else's name that's not in there， Brian。

 And now it's not in fact， found。 Although it's not all that enlightening to just ignore the question altogether。

 it would be nice to say not found。 And here， where is where and C。

 it would be kind of nonobvious to do this And see if you wanted to print out found or if you get through the whole list and you still haven't found the user print。

 not found。 You'd have to like keep track with the variable of whether or not you found the person or you'd have to return from the code prematurely just to get out of it logically。

 turns out somewhat weirdly， but wonderfully usefully for loops in Python can have else clauses associated with them whereby I can say down here。

 print not found。 if I run this version of the program and search for someone who's not in the phone book like Brian。

 now I actually seen。😊，Not found semantically， it's a little weird。

 but essentially what's happening is if you get through this whole loop and you never call break。

Then you've not actually broken out of the loop so you're going to hit the alt and in that case you're going to print out not found and this is such a common thing to like do this kind of bookkeeping and keep track of whether or not something has happening inside of a for loop。

 and if so do this elses do that else literally handles that scenario in Python and this is the most see unlike thing that we've perhaps seen in terms of features with regard to at least loops。

😡，Allright， well， this is great that I've kind of implemented linear search。

 but like we did that in C and it's getting a little tedious。 Can't we do better。 We actually can。

 let me clear my terminal and tighten this up And instead of iterating over every name in names just like we keep iterating over integers in ranges and checking for each name if it equals the thing we're looking at you can actually do something much more clever。

 you can just literally ask Python if the name you're looking for is in the names list。

 then go ahead and print out found else print not found。

 And so this is where Python 2 gets kind of cool in line 5。

 you have just a simple if condition with a boolean expression name in names。

 how does Python know if name is in names， it uses linear search presumably to search over the whole list of names looking for what you care about and then tells you true or false if it found it。

 you don't have to write the code to iterate over it with a y looper for looper or whatnot。

 you just say what you mean。😊，And so here too， it's a little more English like if name in names。

 question mark than print found much more so than it would be pronounceable in C。

 So that's one other cool feature that we now have at our disposal。 What's yet another。 Well。

 when it comes to dictionary objects in C rather in Python。

 a object really just gives you a set of key value pairs。 And we've seen this kind of chart before。

 whereby we might have name and number and name and number and name and number。

 how do we translate this to code because in C， as with problem set5。

 it was gonna be quite an undertaking to be able to store a whole bunch of things in memory in the form of something like a hash table。

 Well， in Python， we can actually define a dictionary ourselves。

 So these square brackets represent a list， But I can alternatively use curly braces for a very new purpose。

 I'm going to go ahead and hit enter just to move the second curly brace to a new line。

 And I am going to now enumerate a bunch of key value pairs。

 namely quote unquote Kelly for the first key colon。😊，Then we'll do plus 1，6，1，7，4，9，5。

1000 as the number。 Then I'm gonna to go ahead and do quote unquote David， for the second key。

 And since we both work here， I'm going go ahead and just use that same number as we've done in before。

 Then a third key for John Harvard Col。 And for John will use plus 1，9，4，94，6， a 2，7，5，0。

 which is fun to call or text。 This now， even though it's syntactically a little different。

 gives me the equivalent of this chart here。 key value pairs where the keys are the staff names and the values are the staff numbers。

 that implements all of that， a hash table， if you will， in Python's own syntax。

 So how do I now use this。Turns out I can actually use it in exactly the same way。

 I'm gonna go ahead and generalize this now to people because it contains not just names。

 but names and numbers。 So I'm gonna to change this variable down here to people too。

 but notice the syntax Now， I can still ask the human for a name they want to look up。

 I can now still say if the name is in the people dictionary。 And by definition。

 Python is going interpret that preposition in as meaning is the following key in the dictionary。

 And if so， it's going to return true。 But what's cool about this is that besides just making this work as follows Python of phone book high。

 and let's type in David， and there's my number that's not my number just as found。

 let's run it again and type in， say Brian not found。 that's as expected。

 But I'd like to know what my number is or Kelly's number or John's number。 Well。

 that's an easy fix too。 inside of this conditional。

 I can say something like this number equals people bracket name And we've not seen this before。

 but we have seen square。😊，Bets in C， when we had arrays。

 this square bracket notation is how you indexed into an array to get a specific value，0，1，2，3。

 fourth。 What's amazing about dictionaries， not just in Python， but in other languages as well。

 you can now index into a dictionary， just as you can index into an array。

 but whereas an array you use numeric indices。😊，In dictionaries， you use string indices。

 You can use strings to look up their corresponding value。 So to be clear。

 name at this point is given to us by the human input。 So if I typed in D V ID name equals David。

 So this is like saying people square bracket， quote unquote David， find David's number。

 that stores the answer from this two column chart in the variable called number。

 And all that remains is for me to print it out， which I can do using an old F string Now。

 let me go down into my print statement， change this to an F string， add a colon。

 add the number variable to be interpolated， rerun this program as Python a phone book do I type in my name and there's my number as found。

And this is incredibly powerful and why again。hasash tables， and in turn， more generally。

 dictionaries are sort of the Swiss Army knife。 Being able just to look up data with such simple syntax is wonderfully useful and powerful。

 And in fact， we can even do more than this， for instance。

 let me propose that if you think about other incarnations of key value pairs。

 you see them all the time。 for instance， in like spreadsheets。

 like here's a screenshot of Google sheetets whereby I've got the beginnings of a spreadsheet with names and numbers。

 But in this model， I want to actually associate some metadata with my data。

 So the data I care about is the actual names and numbers。

 But you could imagine having a third column like email address and maybe home address or any number of other pieces of data associated with these three people。

 For now， I've just got two columns or two attributes， names and numbers。

 Each of the rows in a spreadsheet as most anyone knows who's used a spreadsheet before represents different records or different pieces of data like this is Kelly。

 this is David， this is John and so forth。 We can implement this idea， using dictionaries and lists。

😊，So the syntax is gonna be a little strange at first。 But let me go back to V S code here。

 and let me change my people dictionary to be a people list between square brackets。

 And the elements of this list now are going to be。dictionaries themselves。

 I'm gonna use some curly braces inside of these square brackets and say that the name of one person is quote unquote Kelly。

 And the number for that person is quote un plus 1，6，1，7，4，9，5，1000。

 close then comma on the outside of the curly braces。 Then I'm gonna have another quote unquote name。

 D V I D comma， then another number， I'm gonna borrow the same phone number because we both work here。

 then lastly， comma。 And finally， quote unquote name， unquote John， and then lastly。

 a quote unquote number for John plus 1，9，4，9，4，6，8，2，7，5，0。😊，All right， so what's going on here now。

 Our people variable is now not just a simple dictionary with just individual key value pairs， name。

 number， name number， name number。 We now have a more generalized way of storing not just a name or a number but an email address or a home address or any number of other values。

 How Well the commas just separate the key value pairs now。 So if I do have email addresses for us。

 I can put commaquote email like mailinhar do Eddu and I can just keep adding these key value pairs to each of the dictionaries。

 because a dictionary is a collection of key value pairs。

 So it stands for reason that I can associate name with David number with the number。

 email with mail Edu and so forth。 effectively implementing this idea now in the computers memory。

 and at the risk of significantly oversimplifying this is what Google and Microsoft and Apple are doing with their spreadsheet software they have written code that presents to you a nice table with a graphical user interface on the screen。

 but underneath the hood， what they effectively have is list。😊。



![](img/d7777e514be9901928364ebea51b7b57_22.png)

![](img/d7777e514be9901928364ebea51b7b57_23.png)

Of dictionaries representing each of those rows。 And we're gonna come back to this when we start experimenting before long with our own databases。

 back rows of data from databases， we are going to store that data in lists of dictionaries for the same reason as well。

 So how can we use this。 Well， let me hide my terminal for a second and tweak the program just a little bit。

 I'm still going get the name of a person to look up their number。

 I'm still going to how about iterate over this， because I've lost the ability at least for now to just ask a question like is this name in the structure。

 because it's a list， I do now need to iterate a little bit differently。

 So I'm going to do for each person in the people list go ahead and check is the current person's name。

Equal to the name I'm looking for。 And if so， go ahead and create a variable called number。

 set it equal to that person's number。 and then go ahead and print out， for instance， found colon。

 then in my curly braces， that specific number。 And then after all， that break out of this。

 So this is a mouthful。 but recall that it's all the same syntax we've seen before in smaller parts。

 Square brackets and square brackets means here comes a list。 what are the elements of this list。

 di di di three dictionaries back to back to back， each of which has a key and a value and a key in a value called name and number respectively。

 that second one temporarily has name and number and email as keys plus three values。

 And the third one has keys of name and number as well with their corresponding value。

 So when I iterate over each person in the people list。

 that means on each iteration person is going to be set to this dictionary。 then this。😊。

Then this dictionary on each iteration， I'm asking this question is that current person's name key is rather is the value of that person's name key equal to the name I'm looking for。

 And if so， grab a variable called number， set it equal to the value of that person's number key。

 and then just print it out。 And if we wanted email instead， I tweak the word number to email。

 If I want to look up anything else， you can tweak that code there。

 But being able to index into dictionaries using strings is sort of the fundamentally powerful new technique。

😊，That we have here。Question now。On any of this， yeah。Good question。

 If you wanted both name and number on the screen。 do concatenate。

 Sure you could do that or print them out by passing a comma into the print function and printing one out each way。

 Abute， however you want to format it。 And actually， just as an aside to。

 even though this becomes a little less readable。 This is a little silly that on line 11。

 I'm declaring a variable called number only to use it one line later and then never again。

 technically with those curly braces and format strings， I could just take this code on the right。

 plug it into those curly braces and get rid of this variable altogether， just at some point。

 though F strings start to get a little too hard to read with quotes inside of quotes。

 And so like I kind of prefer being a little more pedantic about it and explicitly putting it in a variable and then interpolating just that variable。

 But you could do it in different ways still。😊，Allright。

 couple final features of Python thatll get us on our way with doing other things。

 Turns out there's a whole bunch of libraries that come with the language itself that you nonetheless have to import。

 even though they're not thirdpart， you didn't have to install them。

 you just need to add them to your code by importing them， one of them is cis。

 and among the things that the cis library has in Python is the ability to give you access to command line arguments。

 After all， we've lost access to command line arguments because there's no more main。

 at least by convention。 There's no main void。 There's no main argv Arg C stuff going on in our code but all of that functionality is still available in a library called cis。

 So how do we use this。 Well， let me go back to Vs code here now。

 let me create a relatively simple program called greet dot pi similar to a few weeks back。

 that's just gonna greet the user using command line arguments instead of get string or the input function。

 I'm going do this by saying from the cis library I argv In this case。

 Argv is essentially just the list。 It is a list。Of the command line arguments that the human is typed。

 It's a list， which means you can just ask the length function。 L N what it length in。

 So there's no need for Arg C anymore。 You can just literally ask Argv how long it is。

 which is kind of nice。 So I'm going to say this。 if the length of Arg V。Equals equals2。

 which means the human type two words at the prompt。 Okay， let's go ahead and greet them。

 assuming that's their name and say hello comma， and then whatever their name is。

 let me make this a format string and to be pedantic。

 Let me create a variable called name and set it equal to R V bracket1。

 which is gonna be the second word that the human typed in as has been our convention in the past。

 else， if they didn't type exactly to command line arguments。

 let's just go ahead and print out something like hello world as generic。

 Let me run Python of Greektop pi enter。 And you see hello world。

 because I apparently did not type in exactly two words。 And yet I did。

 So let's see where this is going。 Let me rerun Python of greettop pi。

 but type in my name David at the command line enter。 and I screwed up unintentionally。

 What did I do wrong。All right， printntf is not a thing。 So that's an easy fix。 Let's delete it。

 Let me clear my terminal window。 rerun Python of greet pi space， David enter。 And now I get hello。

 David。 The only thing that's weird here is that I typed in three words at the prompt。 And yet。

 I'm checking for2。 And it's a bit subtle。 But with Python and Rv， it ignores the Python interpreter。

 it goes without saying that you're using the Python interpreter to run a Python program。

 So the only things that are being counted are the words after the Python interpreter itself。

 So when I type Greek do pi。 And David that's2。 when I only typed Greek pi， that's one。Instead。

Alright， so now that I've done that， I have access to my command line arguments Again。

 What about my exit statuses， This was getting a little low level， But in recent C programs。

 we've had you all returning 0 on success， returning one on error。 Can we still do that？ Well， yes。

 And in fact， the cis library is used for that as well。

 So if I want to actually add some exit statuses to a program to facilitate check 50 and automated tests in the real world。

 I can do that with a program called let's call this exit dot pi。 And in exitt。

 I'm similarly going to import cis， but in a different way， I'm gonna give myself access to。😊，Well。

 yes， let's go ahead and import the whole library just to demonstrate how you can access things inside of it without explicitly saying from sis。

 import such and such。 As before， if the length of cis dot R V。 So this is a little bit different。

 But I'm asking the same kind of question， does not equal to。

 I want to go ahead and print out to the user missing command line argument。

 which is something we did a while back as well。 And then I want to exit with code 1 cis dot exit1 else。

 if I don't run into that issue。 I'm gonna go ahead。 actually， let's not even bother with an notes。

 let's for parodity with our C version， let's do this。 Pri F quote unquote hello。😊。

Ss dot orrg v bracket 1 close quote cis dot exit 0。 All right， that's a whole mouthful。

 but what's really going on。 So I could have done from sis， import argv。

 but I don't need to enumerate every single variable or every single function that I want from a library。

 I can also just more generally say import the whole library， give me access to everything。

 and then I'll tell you what I want from it later。 Therefore， on line 3， I can still access Rrgv。

 I just have to scope it to the cis library so that I say cis dot orrgv means go inside of that library and find me Argv。

 instead of elevating it to a variable unto itself in my own code。 why am I saying not equal to to。

 Well， if they don't give me two words after the interpreter's name。

 I want to yell at them and say missing command line argument and then exit 1。

 I'm not gonna give them a default hello world anymore。 I want them to give me their name。 Meanwhile。

 if I get this far， and I haven't exited from the program。 I can print out cis do orrgv bracket1。

 which is gonna。Be David in the example I type before。 And this means success。

 So cis dot exit0 signifies success。 It's more syntax than before than it was in C。

 but we have the exact same functionality available to us as we have in the past。

How about one other example that we've had in the past。 Let's convert it to Python as well。

 So you have a few more tools in your toolkit。 How about implementing a version of this phone book that actually persists。

 So instead of hard coding into it， Kelly and David and John in this way。

 let's actually let the user type in a name in a number。

 just like on your iPhone or Android phone and add it to a text file like a CV file as we did before using comma separated values。

 Well， it turns out that Python comes with a library to handle CV files。

 We don't need to hackishly implement our own CV support by printing the commas ourselves instead we can import the CV library。

 we can then create say a variable called file set it equal to open and open a file called phonebook do cV in append mode。

 So this is almost the same as C except it's open instead of F open。

 which we saw a couple of weeks back。 Now， let's ask the user via the input function for the name they want to add to their contacts。

 and the number that they want to add to their contacts。 And then after that。😊。

Let's go ahead and do this， which is a bit of muscle memory to remember。

 but I'm going to create a variable called writer， but I could call it anything I want。

 set it equal to Cv dot writer， which means there's a function called writer in the Cv library that I'm simply accessing it because I didn't import it explicitly by name and I'm gonna pass it that file。

 This tells Python turn that file into a Cv that can be written to The next line of code。

 I'm going literally say writer dot write row， write row is a method aka function associated with this writer object。

 And I know that only because I did actually read the documentation。 for the Cv library。

 What do I want to write well， I want to write a list of values， namely a name and a number。

 and I'm using square brackets to tell the right row function that here you go。

 here's a list of values， two of them a name and a number。 After all that。

 I'm going to do file do close and。Close the whole file。 Allright。

 so where does this actually get me， Well， let me go ahead and open up phone book dot C SV。

 which is initially empty。 And I'll move this over to the right hand side。 But whoops。

 I'll move this over to the right hand side。But when I now run this program with Python of phonebook do pi enter。

 I'll type in， say， Kelly's name， enter plus 1，6，1，7，4，9，5，1000。 enter and voil。

 It ends up in the CB using little bit less code。 than we had to last time with C。

 Let's run it once more。 and I'll type in my name and I'll again use plus 1，61，7，4，9，5，1000 enter。

 It's being appended to that file as well。 And one last time for John plus 1，9，4，9，4，6，8，2，7，5，0。

 entervo。 So it's pretty easy that is to say in Python to start creating files like this。

 But this isn't really pythonic。 Let me， in fact， close the CV file。

 hide my terminal and propose that we can tighten up this code a bit too。

 I don't need to open up the file way up here。 I can go ahead and get my variables values this way first。

 And in In fact， I could have done that code a little later anyway。 But I can do this in Python。

 I can say with the following file open phone。😊，t cv in a pen mode and refer to it as a variable called file。

 do this stuff and close the file yourself。 So this program is suddenly significantly shorter because this one line has the effect of opening the file for me in a pen mode。

 assign it to a variable， do this stuff。 And then as soon as the program's indentation ends。

 and there's code over here or no code whatsoever， the file gets closed for me automatically。

 this just helps us avoid like memory leaks and like stupid mistakes we've made and C because you forget to close a file that you have to open and you don't necessarily notice unless you run Valgri or something on it。

 Python tries to avoid this by giving you a new keyword with that doesn't really make sense semantically except with the following file open and it will close the file for you。

 So that's too among the features that you sort of get with Python。 the catch， though。

 with what we just did is that this is a pretty simplistic Cv file。 There are no column heading。

 So if I go ahead and open this file again， phone book do cv。 it looks just like this。 If I try open。



![](img/d7777e514be9901928364ebea51b7b57_25.png)

That in Google sheetets， Microsoft Excel， Apple numbers， it's not gonna look like this。

 It's gonna have three rows， not 4。 it's gonna to say Kelly。

 David and John from top to bottom and our numbers。

 But it's generally nice in the real world When you open a CV file in an actual spreadsheet program。

 See the column names， name， number， email and whatever those are。 Well。

 we can actually do this in Python pretty readily。 Let me actually go into my phone book dot pi example again。

😊。

![](img/d7777e514be9901928364ebea51b7b57_27.png)

After closing the CSV and in the phone book dot pie file。

 I'll still go ahead and ask the user for their name and number。

 I'm still gonna open the file in the same way。 But instead of using a CV writer。

 I'm gonna use a CV dictionary writer or di writer for short。

 which per the documentation is gonna let me pass in not only the file that I want to use for a CV。

 It's gonna let me specify a bunch of field names。 That is what are the words you want to put at the very top of the spreadsheet。

 Well， I want those words to be name， comma number unquote And now down here。

 I can still just write the row。 But I need to tell the dictionary writer that it's not just a list of values anymore。

 It's an actual dictionary。 So the name that I'd like you to please write is the name that the human typed in。

 and the number that I'd like you to write is the number that the human typed in。

 So if now let's go ahead and remove the original phone book do CSV file just delete it。 Let's rerun。

😊，Coode of phone book dot C SV to open up the now empty version of the same。

 Let's now do Python of phonebook dot Pi。 enter， type in。 we'll start with Kelly again。 enter whoops。

Oh， I had a typo there， too。 graramatically。 Let's fix that。 Let's fix this again。

 Let me go ahead and run Python of phone book dot Pi enter， type in Kelly enter。 And now plus 1，6，1。

7，4，9，5，1000。 And notice at top right now where the empty CSV file is when I hit enter。

 We're gonna store not only Kelly and her number， but also。😊，That didn't work。啊。Field names。

Dt writer。What did I do wrong。Feedback， welcome。Name number。Found book。Why did that not work？ Okay。

 stand by。CV enter。Let's run this again， Python of phonebook dot Pi， Kelly， plus 1，6，1，7，4，9，5。

1000 enter code of phonebook dot C S。Sorry， Se again。Oh， writerer do right header。Right or do。

Is that the function。

![](img/d7777e514be9901928364ebea51b7b57_29.png)

Here we go。ちち。Why is this code not。Storing the field names in the CSV file。



![](img/d7777e514be9901928364ebea51b7b57_31.png)

嗯。Cros your fingers。

![](img/d7777e514be9901928364ebea51b7b57_33.png)

嗯。How about this Let me get rid of that thing。 Alright， this is horrifying。 But let's do this。

 We're going down this road already。

![](img/d7777e514be9901928364ebea51b7b57_35.png)

Okay。😀。😊，Infuriating， okay。Duck's not very helpful。So' want the answer。 Alright。

 which is the whole point of the duck。 I know。 Alright， right header。😊。



![](img/d7777e514be9901928364ebea51b7b57_37.png)

Wow。The dictator。Python。Feel names。Standby。I'm only doing this because there's only like 10 of us here。

 So all right。D。A writer。Right wrong。Oh， is that it。



![](img/d7777e514be9901928364ebea51b7b57_39.png)

Oho。Maybe it is as simple as that field names。Okay， I think let's try this。

 and then I'll rewind and do this better。 Is it really that stupid。Okay， here we go。

Python of phone book dot Pi enter Kelly plus 1，6，1，7，4，9，5，10。Wow， that's annoying。

Why does it do that？I don't know why it does that。 That's weird。 But W means right。 A means a pen。

 It doesn't like， I assume this means that the way the dictionary writer works is even though I'm calling it right row。

 right row， right row， it's probably waiting until the end of the loop and the file is closed to actually dump all of the data at once and writing the whole thing。

 including the header file unless you have a different conjecture。No， like， if we run it here。

 I'll try my name。 No， it's not gonna Well， let's say。Of。4，9，5，1000。Ops。Yeah。

That's a good question that didn't work， as we intended。Okay， let's figure out。Do we need to。Okay。

 we're gonna pretend like this didn't happen for our friends watching at home。

And I'll fix this later。Okay，hu。All right。Thank you for humoring me。This CSV file though。

 is fairly simplistic though in that it only shows the three names that I tried to print out to the file。

 Kelly and David and John in this case， but what it's lacking， of course。

 if we look back at the Google Sheets version is the actual header row。

 which is all too common in in actual spreadsheet software when using Google sheetets or Apple numbers or Microsoft Excel and it would be nice if we could actually include that well it turns out using not a CSv writer but a dit writer or dictionary writer in Python can you actually output some field names as well and let the library do the heavy lift of actually giving you that header row as well as all of the data rows you care about thereafter。

 All right， how about now some final flourishes using some other features of Python that we did see a glimpse of some time ago。

 namely the ability to install libraries of our own choice So up until now in CS50 we CSs50 have preinstalled most of what you need including back in the earliest weeks of the class when we had that cow say program that I wrote that was using a thirdpart library that it installed into my codespace in advance。

Well， you can use a program called Pip to install Python packages into your own codespace。

 And if using your own Mac and PC onto your own Mac and PCs as well。

 if those libraries are freely available as open source online in the repository from which the Python Pip program actually draws。

 So to remind you， let me go back to Vs code here and let's recreate our cow program by opening up say code of cow dot pi。

 and in cow dot pi， let's import that library， cow say， which I did already install in advance。

 let me then use cow say do cow， which at the time looked quite cryptic。

 but now you'll see the library called cow say inside of which is a function called cow and I can go ahead and print out something like this is C 50 in quotes。

 Now if I go back to my terminal window and run Python of cow dot pi， we gets back interesting。Sorry。

 can we humor me one last time， and let's just redo this part。

Let me go back to VS code and let me go ahead and create a new program called cow dot pi And with this program。

 I'm going go ahead and import that library cow say。

 And after that I'm gonna to call cow say do cow quote unquote。

 say this is CSs 50 to have a cute little cow on the screen say exactly that Now in a previous lecture。

 I had preinstall this library。 but suppose I had forgotten to do so today。

 let's see what other type of error we'll see on the screen。 Well。

 let me go ahead and run Python of cow pi enter。 and there's another one of those tracebacks。

 This one's a little more straightforward than the name error and the value error we saw in the past。

 This is literally module not found error No module named cow say。 Well。

 this is where the Pip command comes in。 if something hasn't been preinstalled for you in CS50 dev or in the real world on whatever system you're using。

 you can use Pip install cow say and assuming you've spelled it correctly and assuming the library is publicly available hitting enter。

 will result in Pip automatically downloading the latest version。

 installing it in this case into your code space。 And。😊，Solving hopefully that problem。

 Let me clear my terminal window， run Python of cow pi again。 definitely cross my fingers。

 And theres the most adorable cow。 And if we full screen the terminal。

 we'll see that he's indeed saying this is Cs 50。 Now that's just one of the things we can install with cow say I could also install libraries onto my own Mac and PC。

 In fact， in just a moment， I'm gonna switch over to another computer here。

 where I have a terminal window open on my own actual Mac。

 And I'm doing this because I'd like to play around with some speech some text to speech library functionality。

 which can't really do in C50 dev because it's browser based And when you run code in the cloud。

 it's not gonna to pass the audio along to your speakers on your laptop or desktop。

 But if I'm running Python and my own code on my own computer。

 a Mac in this case or PC in someone else's case， I can install that kind of library speech to textex and have my own code on my own computer use my own speakers to verbalize some string quite like that。

 So how can I go about doing this。 Well I'。😊，Docuation， I'm going to go ahead and install with Pip。

 a library called P Y， T T， S X 3， version 3 of the Python Text to Spch Library。

I'm going to install Pip， install P， Y， T， T， X S。I'm going to use Pip to install a library called pi to text text2 speech version3。

 hitting enter goes in finds and downloads as needed the library if it's not already installed and then brings me back to my terminal。

 and I'm going to use an older school program here called Vim or V to actually implement a Cal program on this computer whereby I'm going go ahead and write some code using this library without VS code but with just another text editor instead to do this at the very top of my file。

 I'm going to import this library called Python text to speech。 So P Y T T S X3 for version 3。

 and then I'm going to use only three lines of code to synthesize some voice I'm going to say a variable called engine set it equal to pi T T S X3 do in it because the documentation taught me that I need to initialize the library the first time I use it I can then use this variable called engine to actually say something quite like scratch。

 albeit verbally instead of pictorially like this is C S 50 quote。And then lastly。

 I can use engine dot run end weight similar to some scratch block so that the whole expression is actually verbalized before my program actually quits。

 Now， the first time I run this it might take a moment for the library indeed to initialize itself。

 But on my own Mac here， I'm gonna run Python of cow dot pi。

 if we could raise the volume just a little bit， hopefully we'll not see。 But here。

 this cow's greeting。😊，This is CS50。It was very much in a rush to say it after initializing for that long。

 and if we ran it again and again and added some optimizations。

 we could get it talking much more quickly than that。

 but we now have a version of the program that indeed verbalizes what string or stir it is that I've passed into it This is CS50。

It's really in a rush to finish there。 Allright， let's try one final flourish of another library that's fun to play around with。

 if only because it'll motivate some of the things you can now do in Python yourself。

 let me go into Vs code in my code space， because this one does not require my speakers。

 I'll close that first version of the cow。 And I'm gonna go ahead and create a Q R code generator after installing with Pip a library called Q R code。

 which I read about online。 And now it's installed in my code space。

 I'm gonna now go ahead and create a file called Q R do pi， So let's go ahead and code up Q R do pi。

 And I want to generate my own Q R code。 Most of you in are in the habit。

 if you've ever generated QR code before， you probably just Google around for some generator online for which someone else wrote code to generate the Q R code。

 But I can do that for myself and actually generate my own images to do so。

 I'm gonna import a library called O， which comes with Python。

 even though we haven't had occasion to need it just yet。 actually。😊，Let's not do that。

 I'm gonna go ahead and import the library that I just installed。 importm Q R code。

 And then below that， I'm gonna create a variable called。 for instance， image。

 and set that equal to this library's Q R code dot make function。

 No relation to the make that we use for C。 And I'm gonna make a Q R code containing a URL。

 Maybe of one of the lecture videos。 So let's do H T， T， P， S， Col slash slash YouTube dot com。

 the short version。 And then X， V F Z， J， O，5 P G。😊，G G0。 if I got that just right。 then after that。

 I'm gonna go ahead and call image dot save to save that URL as a file called Q R dot PN G quote unquote。

 and then P And G will be the format， which is portable network graphic。

 which is akin to a Jpeg or g but with different features。

 I'm just gonna double check my writing here。 So we go to the right lecture video。

 And I think we are indeed good。 And what that should do after running my code is leave me with today's final flourish a ping file in my code space that went open is gonna be  Q R code that you can scan with your phone。

 So if you'd like to get ready for this final flourish。

 I'm gonna go ahead and run Python of Q R dot pi and hit enter thankfully， it worked。

 I'm gonna now open up Q R dot PN G and close my terminal window。

 And for our final moments together this here in week 6 after which will ultimately transition to yet more languages and problems to be solved here is a final code for you to scan of today is here lecture。

😊。

![](img/d7777e514be9901928364ebea51b7b57_41.png)

All right， that's it for today， we'll see you next time。

