# 哈佛大学《CS50x2024计算机科学导论｜Introduction to Computer Science》（中英字幕，豆包翻译） - P7：-07-CS50x 2024 - Lecture 6 - Python - GPT中英字幕课程资源 - BV16k4y1X7KZ

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_0.png)

🎼。

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_2.png)

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_3.png)

Alright， this is C S 50。 and this is finally week 6。

 and this is that week we promised wherein we finally transitioned from C this lower level older language via which we've explored memory and how really computers work underneath the hood to what's now called Python。

 which is a more modern， higher level language whereby we're still gonna be able to solve the same types of problems。

 But it's gonna suddenly start to get much， much easier because what Python offers as do higher level languages more generally。

 are what we might describe as like abstracts over the very lowle ideas that you've been implementing in sections and problem sets and so much more。

 But recall from week 0 where we began， this was our simplest of programs that just printed hello world。

 things escalated quickly thereafter in week one， where suddenly we had all of this new syntax。

 But the idea was still the same of just printing out hello world。 Well， as of today。

 a lot of that distraction， a lot of the visual distraction goes away entirely such that what used to be this in C will now be quite simply this。

😊，In Python。 And that's a bit of a head fake in that we're gonna see some other fancier features of Python。

 but you'll find that Python's popularity in large part derives from just how relatively readable it is and also is we ultimately see just how exciting and filled the ecosystem among Python programmers is。

 That is to say there's a lot more libraries。 There's a lot more problems that people have solved in Python that you can now incorporate into your own programs in order to stand on their shoulders and get real work done faster。

 But recall， though， from see that we had a few steps by which to actually compile that kind of code So we got into the habit of make to make our program called hello。

 And then we've been in the habit of running it with dotlash hello， the effect of which of course。

 is to like feed all of the zeros and ones that compose the hello program into the computer's memory and in turn the CPU。

 we revealed that what make is really doing is something a little more specific， namely running。

 clang the see language compiler specifically with some automatic command line argument so as to output。

The name that you want linkIn the library that you want and so forth。 But with Python wonderfully。

 we're gonna to get rid of those steps to and quite simply run it as follows。 henceforth。

 our programs will no longer be in files ending in do C suffice it to say or files starting today are going start ending with do p which is an indication to the computer Mac Windows Linux or anything else that this is a python program but unlike C wherein we've been in the habit of compiling our code and running it compiling our code and running it anytime you make a change with Python。

 those two steps sort of get reduced into one such that any time you make a change and want to rerun your code。

 you don't explicitly compile it anymore。 you instead just run a program called Python similar in spirit to clang。

 but whereas clang is a compiler， Python will see is not only the name of the language but the name of a program and the type of that program is that of interpreter an interpreter as a program that reads your code top to bottom left to right and really does what。

😡，Says without having this intermediate step of first having to compile it in zeros and ones。

 So with that said， let me do this， let me flip over here to Vs code。 And within Vs code。

 let me write my first python program。 And as always。

 I can create a new file with the code command within VS code。

 I'm gonna create this file called hello do pi， for instance。

 and quite quite simply I'm gonna go ahead and simply do print quote unquote hello world。

 And if I go down to my terminal window。 instead of compiling this。

 I'm instead going to interpret this program by running Python space in the name of the file。

 I want Python to interpret hitting enter and voila now you see hello world。

 But let me go ahead and compare this at left。 let me also go ahead and bring back briefly a file called hello do C。

 and I'm gonna do this as we did in the very first day of C， where I included standard I O do H。

 I did in main void I did inside of there printfquote hello comm world backlash and close semicol。



![](img/22c0c11fa31af64363e6a5cd04b7fe7c_5.png)

And let me go ahead and V S code。 And if you drag your file over to the right or the left。

 you can actually split screen things。 if of help。 And what I've done here is。

 and let me hide my terminal window。 I've now compared these two files left and right。

 So here's hello dot C from say week 1， Here's hello dot  pi from week 6 now， And the obvious。

 the differences are perhaps obvious。 But there's still some， there's a subtlety。

 at least one subtlety beyond getting rid of lots of syntax。

 What did I apparently omit from my Python version。

 even though it didn't appear to behave in any buggy way。 Yeah。



![](img/22c0c11fa31af64363e6a5cd04b7fe7c_7.png)

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_8.png)

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_9.png)

Sorry。不什么托。The library， So I didn't actually have to include any kind of library like the standard I O library。

 print， apparently in Python just works。So I don't need to use main anymore。

 So this main function to be clear， we was required in C。

 because that's what told the compiler what the main part of your program is。

 And you can't just start writing code otherwise。 What else do you see。

So there's no more semicolon wonderfully enough at the end of this line。

 even though there was here and things are getting a little more subtle now what else So the new line。

 So recall that in print F， if you wanted to move the cursor to the next line when you're done printing。

 you had to do it yourself。 So it seems as though Python because when I interpreted this program a moment ago。

 the cursor did move to the next line on its own they sort of reverse the default behavior。

 So those are just some of the salient differences here， one。

 you don't have to explicitly include standard library， so to speak like standard I O。

 you don't need to define a main function anymore， you can just start writing your code。

 you don't need these parentheses， these curly braces。

 print F is now called print it would seem and you don't need the backslash N。

 Now there is one thing that's also a little looser， even though I didn't do it here。

 even though in C， it was required to use double quotes。

 anytime anytime we want to use a string aka cha star in Python as with a lot of languages now。😡。

s you can actually get away with just using single quotes so long as you are consistent。

 generally speaking。 some people like this， because you don't have to hold shift and therefore you just hit one key instead of two。

 So there's an argument in terms of efficiency。 However。

 if you want to use an apostrophe in your string， then you have to escape it。

 And so in general stylistically， I'll use double quotes in this way。

 But with things are getting a little looser now with Python whereby that's not actually a requirement。

 But what's especially exciting with Python and really a lot of higher level languages is just how much real work you can get done relatively quickly。

 So you've just spent quite a bit of time， dare say implementing your spell checker and implementing your own dictionary of sorts。

 Well， let me propose that maybe we should have asked you to do that in Python instead of C。 why。

 let me go ahead and do this。 Let me close these two tabs and reopen my terminal window。

 let me go into a directory called Sper that I downloaded in advance for class。

 And if I type L S in here， you'll notice that it's very similar to。

What you spent time on with problem set5， but the file extensions are different。

 There's a dictionary dot pi instead of dictionary do C there's a speller dot pi instead of a speller do C and there's the exact same directories dictionaries and text that we gave you for problem set5 So let me just stipulate that I spent time implementing speller do C in Python and so I gave it a name of speller do pi but I didn't go about really implementing dictionary do pi yet And so why don't we go ahead and actually implement dictionary do pi together by doing this let me clear my terminal do code dictionary do pi and let me propose that we implement ultimately for functions and what are those functions going to be Well。

 they're going to be the check function， the load function。

 the size function and the unload function but recall that in problem set5。

 you use you implemented your own hash table and so while there isn't a hash table data type in Python I'm going to go ahead and do this I'm going create a variable。

 a global variable。diicctionary do pi called words。

 and I'm going to make it a set in the mathematical sense。

 a set is a collection of things that won't contain duplicates。 Any duplicates will be filtered out。

 So I'm going to now after that creating that one global variable。

 I'm going create a function called check just as you did and check takes as input a word。

 And if I want to check if a word is in that set of words， I can simply do word dot lower。😡，In words。

And that's it。 Let me now define another function called load， which recall， took an argument。

 which was the name of the dictionary you want to load into memory inside of my load function。

 I'm now going to do this。 I'm gonna to say with open dictionary as a variable called file and in there I'm going go ahead and update the set of words to be the updated version of whatever's in this file as a result of reading it and then splitting its lines whereby this file has a big long column of words。

 each of which is separated by a new line， split line is going to split all of those into one big collection。

 And then I'm just going go ahead and return turn true。

 I'm now going to go ahead and define a size function， just as you did， but in Python。

 I'm going to go ahead and just go ahead and return the length of that set of words where length or LN is a function itself in Python。

 and I'm going to do one last function， it turns out that in Python even though for this program。

 I'm going to go and implement a function called unload。

 there's not actually anything to unload in Python because Python will manage your memory for you。😡。

Maoc is gone。 free is gone。 Pointers are gone。 It handles all of that seemingly magically for now for you。

 So here then as I claim what you could have done with problemet5 if implementing it in Python instead。

 let me go ahead and open my terminal window。 Let me increase its size。

 Let me run Python of speller which is the name of the actual program not the dictionary per se that I implemented。

 let's run it on a file called homes text because that was a particularly big file and if I hit enter now。

 we'll see hopefully the same output that you saw and C flying across the screen and eventually we should see that same summary at the bottom as to how many words seemed to be misspelled how many words were in the dictionary and ultimately how fast this whole process was Now the total amount of time required was 1。

93 seconds which was actually longer than it seemed to take that's because we're doing this in the cloud and it was taking some amount of time to send all of the text to my screen but the code was only taking 1。

93 seconds total on。😡。

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_11.png)

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_12.png)

Actual server and hopefully these same kinds of numbers line up with your own the difference being what I did not have to implement for this spell checker is your own hash table is your own dictionary literally beyond what I've done using Python here with some of these built in features So why you see why not always use Python assuming that you prefer the idea of being able to whip up within seconds。

😡，The entirety of problem set 5。 How might you choose now between languages。

And I apologize if you're harboring resentment that this wasn't a week earlier。Why Python or YC。

Any instincts。Any thoughts， hopefully a reason。 Yeah， over here。Yeah。Really good conjecture。

 So you always thought that Python was slower than C and takes up more space than C。 odds are。

 that's in fact， correct。 So even though ultimately this 1。93 seconds is still pretty darn fast。

 odds are it's a little slower than the C version would have been it's possible too。

 that my version in Python actually does take up more Ram or memory underneath the hood。 why Well。

 because Python itself is managing memory for you。 And it doesn't necessarily know a priori how much memory you're going to need you the programmer might And you。

 the programmer writing in C allocated presumably exactly as much memory as you might have needed last week with problem set 5。

 but Python's got to maybe do its best effort for you and try to manage memory for you。

 and there's gonna be some overhead。 the fact that I have so many fewer lines of code。

 the fact that these lines of code sort solve problem set5 for me means that Python or whoever invented Python they wrote lines of code to sort of give me this functionality。

 And so if you think of Python as a middleman of。It's doing more work for me。

 It's doing more of the heavy lift。 So it might take me a bit more time。 but my gosh。

 look how much time it has saved in terms of writing this code more quickly and arguably this code is even more readable or at least will be after today。

 week 6， once you have an eye for the syntax and features of Python itself。 So beyond that。

 it turns out you can do other things pretty easily as well。 Let me go back into my terminal window。

😡，Let me close this dictionary dot pi。 Let me go into a folder called filter in which I have this same bridge that we've seen in the past across the river there。

 So here's a bridge。 This is the original version of this particular photograph。

 suppose I actually want to write a program that blurs this Well you might recall from problem set4 you could write that same code in C by manipulating all of the red the green。

 the blue pixels that are ultimately composing that file but let me go ahead and propose this instead。

 let me create a file called blur dot pi and in this file let me go ahead and just go ahead and import a library。

 So from the Python image library P， let me go ahead and import something called image capital I and image filter capital I capital F。

 So I'm going to do before equals image dot open quote unquote bridge do BM then let me go ahead and create another variable called after and set that equal to before dot filter and then in parentheses image filter。

😡。

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_14.png)

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_15.png)

spelllled as before dot box blur， and then we'll give it a value of 10。

 How much do I want to blur it。 For instance， After that， I'm going to literally call after dot save。

 And let's save it as a file called out dot BMP。And that's it。

 I propose that this is how you can now write code in Python to blur an image much like you might have for problem set4。

 Now let me go ahead in my terminal window and run Python of blur dot pi When I hit enter those four lines of code will run。

 it seems to have happened quite quickly， let me go ahead and open now out dot BP and whereas the previous image looked like this a moment ago。

 let me go ahead and open out dot BP。😡。

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_17.png)

And hopefully you can indeed see that it blurred it for me using that same code and if we want things to escalate a little more quickly。

 let me go ahead and do this instead， let me close blurd Bmp。

 let me go ahead and open a file called edges do pi and maybe an edges do pi we can use this same library so from the Python image library import image and import image filter。

 let me go ahead and create another variable called before set it equal to image do open quote unquote bridge Bmp just like before。

 let me create another variable called after set that equal to before dot filter image filter do find edges which comes with this library automatically and lastly the same thing。

 save this as a file called do Bmp So if you struggled perhaps with this one previously whereby you wrote for the more comfortable version of problem set for edge detection so to speak well you might have then created a file that given an input like this the original bridge B this newver。

😡。

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_19.png)

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_20.png)

An outdot B with just four lines of code now looks like this。 So again。

 if this is a little frustrating that we had you do all of this in C。

 that was sort of exactly the point to motivate that you now understand nonetheless。

 what's going on underneath the hood， but with Python。

 you can express these solutions to problems all the more efficiently all the more readily。

 and just one last one too， it's very common nowadays in the world of photography and social media and the like to do face detection for better or for worse。

 And it turns out that face detection， even if you want to integrate it into your own application。

 is something that lots of other people have integrated into their applications as well。 So Python。

 to my point earlier of having this very rich ecosystem of libraries that other people wrote。

 you can literally run a commands like。

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_22.png)

Pip， install， face underscore recognition。 If you want to add support to your code space or to your programming environment more generally for the notion of face recognition。

 In fact， this is going automatically install from some server elsewhere。

 a library that someone else wrote called F recognition。 and with this library。

 you can do something like this。 let me go into a directory that I came with in advance。

 let me go ahead and Ls in there， and you'll see four files， De dot Pi and recognize dot Pi。

 which are going detect faces and then recognize specific faces respectively。

 and then two files I brought from a popular TV show， for instance， So if I open office do Jpeg。

 here is one of the early cast photos from the TV series， the office。

 And here is a photograph of someone specific specific from the show Toby Now， this is， of course。

 Toby's face。 But what is it that makes Toby's face of face。😡，More generally。

 if I open up office do Jpeg， and I asked you， the human to identify all of the faces in this picture wouldn't be that hard with the market or sort of circle all of the faces。

 But how， why。How do you， as humans， detect faces， might you think， yeah。啊。Features， yeah， like eyes。

 nose， generally in a similar orientation， even though we all have different faces ultimately。

 but there's a pattern to the sort of to the shapes that you're seeing on the screen。 Well。

 turns out this face recognition library has been trained。

 perhaps my artificial intelligence over time to recognize faces。

 but any number of different faces perhaps among these folks here。

 So if I go back into my terminal window here。 let me go ahead and run say Python of detect dot pi。

 which I wrote in advance which uses that library。 And what that program is gonna do。

 it's gonna think do some thinking it's just found some face and let me go ahead now and open a file。

 it just created called detect do Jpeg， which I didn't have in my folder a moment ago。

 But when I open this here file， you'll now see all of the faces based on this library's detection thereof。

 But suppose that we're looking for a very specific face among them， maybe Toby's。 Well。

 maybe if we write a program that doesn't just take as input the office do Jpeg。 but a second。

Input Toby do Jpeg， maybe this library and code more generally can distinguish Toby's face from gyms from Pams from everyone else in the show。

 just based on this one piece of training data。 so to speak。 Well。

 let me instead run Python of recognize do pi and hit enter It's going do some thinking some thinking some thinking。

 and it is going to output now a file called recognized do Jpeg。

 which should show me his face ideally specifically。 And so what has it done。

 Well with sort of a green marker。 there is Toby among all of these faces。

 That's maybe a dozen or so lines of code。 but it's built on top of this ecosystem of libraries。

 and this is again just one of the reasons why Python is so popular undoubtedly some number of years from now。

 Python will be out and something else will be back in。

 but that's indeed among the goals of CS52 is not to teach you see not to teach you Python not in a couple of weeks to teach you jascript and other languages too。

 but to teach you how to program。

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_24.png)

all of the ideas we have explored and will' now explore more today。

 You'll see recurring for languages in the years to come。

 Any questions before we now dive into how it is this code is working and why I type the things that I did。

Before we forge ahead， any questions along these lines？Anything at all。No， all right， so。

How does Python itself work。 Well， let's do a quick review as we did when we transition from scratch to see this time。

 though， from scratch say to Python。 So in Python， as with many languages。

 there are these things called functions， the actions and verbs that actually get things done。

 So here on the left recall from week 0， was the simplest of functions we played with first the save block。

 which literally has the cat say something on the screen， we've seen in C， for instance。

 the equivalent line of code is arguably this here with printf with the parentheses。

 the quotation marks the backlash and the semicolon in Python now。

 it's going to indeed be a little simpler than that。

 But the idea is the same as it was back in week 0 libraries So we've seen already in C and now we've already seen in Python that these things exist too in the world of C recall that besides the standard ones like standard I O H that header file we very quickly introduced C50 H。

 which was like your entry point the header file for the C50 library。

 which gave you a bunch of functions as well。 Well we're gonna to give you a similar library for at least the next week or two training。

For Python specifically that again， will take off so that you can stand on your own even with C 50 behind you。

 But the syntax for using a library in Python is a little different。 You don't include a dot H file。

 you just import instead the name of the library。 All right what is that actually mean。

 if there are specific functions in that library you want to use in Python， you can be more precise。

 You don't just have to say， give me the whole library for efficiency purposes。 you can say。

 let me import the get string function from the C 50 library。

 So you have finer grain control in Python， which can actually speed things up if you're not loading things unnecessarily into memory if all you want is say one feature therein。

 So here， for instance， in scratch was an example of how we might use not only a builtin function like the save block or in see in the printf。

 but how we might similarly now do the same but achieve this in Python。 So how might we do this。

 Well， in Python。Or rather in C， this code looks a little something like this back in week1。

 we declared a variable of type string， even though later we revealed that to be cha star。

 I gave this a variable name of answer for parodity with scratch。

 than we you see a 50 zone get string function and ask for instance。

 the same question as in the white Oval here and then using this placeholder syntax。

 these format codes， which was printf specific we could plug in that answer to this premade string where the percent S is。

 And we saw percent I and percent F and a bunch of others as well。 So this is sort of how in C。

 you approximate the idea of concatenating two things together。

 joining two things just as we did here in scratch。 So in Python。

 it turns out it's not only gonna be a little easier but there's gonna to be even more ways to do this。

 And so even what might seem today like a lot of different syntax。

 it really is just different ways stylistically to achieve the same goals And over time is you get more comfortable with this you too will develop your own style or if working for a company or working with the team。

You might collectively decide which conventions you want to use。 But here， for instance。

 is one way you could implement this same idea in scratch， but in Python instead。

 So notice I'm going to still use a variable called answer。

 I'm going to use C 50's function called get string。 I'm still going to use quote unquote。

 What's your name， but down here is where we see the most difference。 It's again。

 not called printf in Python。 It's now called just print。

And what might you infer the plus operator is doing here， It's not addition， obviously。

 in a mathematical sense。But those of you who've perhaps programmed before。

 what does the plus represent in this context。It's indeed joining the two strings together。

 So this is indeed a concatenating the thing on the left with the thing on the right。

 So you don't use the placeholder in this particular scenario。

 You can instead a little more simply just use plus， but you want your grammar to line up。

 So I still have H E L O O comma space and then close quote， because I want to form a full phrase。

 Notice， too， there's also one other slightly more subtle difference on the first line。😊。

Besides the fact that we don't have a semi colonlon， what else is different。

I didn't declare the type of the variable。 So Python still has strings， as we'll see。

 but you don't have to tell the interpreter what type of variable it is。

 And this is gonna save up some keystrokes。 And it's just gonna be a little more user friendly over time。

 Meanwhile， you can do this also a little bit differently if you prefer。

 you can instead trust that the print function in Python can actually do even more for you automatically。

 The print function in Python can take multiple argument separated by commas in the usual way。

 And by default Python is going to insert for you， a single space between its first argument and its second argument。

 So notice what I've done here is my first argument is quote un hello with a comma。 but no space。

 then outside of the quotes， I'm putting a comma because that just means here comes my second argument。

 And then I put the same variable as before。 And I'm just gonna let Python figure out that it should。

 by default per its documentation can join these two variables putting single space in between them。

 can do this yet another way。And this way looks a little weirder。

 but this is actually probably the most common way nowadays in Python is to use what's called a format string or F string for short。

 and this looks weird to me still it looks weird but if you prefix a string in Python with an F literally you can then use curly braces inside of that string in Python and Python when not'll print out literally a curly brace and a closed curly brace。

 it will instead interpolate whatever is inside of those curly braces that is to say if answer is a variable that has some value like David or something like that saying F before the first quotation mark and then using these curly braces therein is going to do the exact same thing of creating a string that says hello comma space David so it's gonna plug in the value for you。

 so you can kind of think of this as percent S but without that second step of having to like keep track of what you want to plug back in for percent S instead of percent S。

 you literally put in curly braces， what do you want to put。😡。

Right there you format the string yourself。😡，So given all of those ways。😡。

How might we actually go about implementing this or using this ourselves， Well。

 let me propose that we do this here。 Let me propose that I go back to V S code。

 Let me go ahead and open up hello dot pi again。 And as before。

 instead of just printing out something like unquote hello world。

 let me actually print out something a little more interesting。

 So let me go ahead and from the C 50 library， import the function called get string。

 Then let me go ahead and create a variable called answer。

 Let me set that equal to the return value of get string with as an argument。

 quote unquote what's your name question mark。 And then no semicolon at the end of that line。

 But on the next line， frankly， here， I can pick any one of those potential solutions。

 So let me start with the first。 So hello comma space quote plus answer。

 And now if I go down to my terminal window and run python of hello dot pi， I'm prompted for my name。

 I can type。

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_26.png)

AndDVID andvoila that there then works。 or I can tweak this a little bit。

 I can trust that Python will concatenate its first and second argument for me。

 but this isn't quite right。 Let me go ahead and rerun Python of hellello dot Pi。

 hit enter and type in David， It's going to be ever so slightly buggy。

 sort of grammatically or visually， if you will。 What did I do wrong here。😡，Yeah。

 so I had I left the space in there， even though I'm getting one for free from print。

 So that's an easy solution here。 But let's do it one other way after running this to be sure D V I D。

 And okay， now it looks like I intended。 Well， let's go ahead and use what that placeholder syntax。

 So let's just pass in one bigger string is our argument。 do hello comma。

 and then in curly braces answer like this。 Well， let me go down to my terminal window and clear it。

 Let me run Python of hella up pi and enter， type in D V I D andvoil Okay， I made a mistake。😊。

What did I do wrong here， minoror， though it seems to be， yeah。

So the stupid little F that you have to put before the string to tell Python that this is a special string。

 It's a format string or F string that it should additionally format for you。

 So if I rerun this after adding that F。 I can do Python of hello do5。 What's your name， David。

 And now it looks the way I might intend。 But it turns out in Python。

 you don't actually need to use get string in C， recall that we introduced that because it's actually pretty annoying in C to get strings in particular to get strings safely。

 recall those short examples we did with scanf not too long ago in scanf scans what the user types at the keyboard and loads it into memory。

 but the fundamental danger with scanf。 when it comes to strings was what。😡。



![](img/22c0c11fa31af64363e6a5cd04b7fe7c_28.png)

Why was it dangerous to use Scf to get strings from a user。哇， yeah。Exactly。

 what if they give you a really long string that you didn't allocate space for because you're not gonna know as the programmer in advance how long of a string the human is gonna type in。

 So you might under you might undercut it and therefore have too much memory too many characters being put into that memory thereby getting you some kind of buffer overflow。

 which might crash the computer or minimally your program。

 So it turns out in see get string was especially useful in Python， it's not really that useful。

 All it does is use a function that does come with Python called input。 And in fact。

 the input function in Python for all intent purposes is the same as the get string function that we give to you。

 But just to ease the transition from C to Python， we implemented a python version of get string nonetheless。

 But this is to say if I go to V S code here and I just change， get string to input。 And in fact。

 I even get rid of the C 50 library at the top， this too should work fine。 if I rerun Python。



![](img/22c0c11fa31af64363e6a5cd04b7fe7c_30.png)

have a load dot Pi， type in my name， David andvoila， I have that now working as well。 All right。

 questions about this use of get string or input。

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_32.png)

Or any of our syntax thus far。😡，All right， Well what about variables。 We've used variables already。

 And we already identified the fact that you don't have to specify the type of your variables proactively。

 even though clearly Python supports strings thus far。 Well， in Python。

 here's how you might declare a variable that not necessarily is assigned like a string。

 but maybe an integer instead。 So in scratch， here's how you could create a variable called counter if you want to count things and set it equal to0 in C what we would have done is this int counter equals 0 semicolon。

 That's the exact same thing as in scratch。 But in Python as you might imagine。

 we can chip away at this and type out this same idea a little more easily1。

 we don't need to say int anymore。2， we don't need the semicolon anymore。

 And so you just do what you intend。 if you want a variable， just write it out。

 if you want to assign it a value， you use the equal sign。 if you want to specify that value。

 you put it on the right。 And just as in C， this is not the equality operator。

 it's the assignment operator from right to left。 recall that。In scratch。

 if you wanted to increment a variable by one or any value， you could use this puzzle piece here。

 Well， in C， you could do syntax like this， which again， is not equality。

 It's saying add one to counter。 And then assign it back to the counter variable in Python。

 you could do exactly the same thing minus the semicolon。

 So you don't need to use the semicolon here。 But you might recall that in C。

 there was some syntactic sugar for this idea because it was pretty popular。

 And so you could shorten this in C， as you can in Python to actually just this plus equals one。

 will'll add to the counter variableable， whatever that value is。



![](img/22c0c11fa31af64363e6a5cd04b7fe7c_34.png)

But it's not all steps forward。 You might be in the habit of using plus plus or minus minus。 Sorry。

 those are not available in Python Y。 It's because the designers of Python decided that you don't need them because this is。

Gets the job done anyway。 But there's a question down here in front unless it was about the same。

 Allright， so that's one feature we're taking away。

 but it's not such a big deal to do plus equal in this case。 Well。

 what about the actual types involved here。 beyond actually being able to define variables。

 We recall that in the world of C。 we had at least these data types。

 those that came with the language in particular。 And we played with quite a few of these over time。

 In Python， we're going to take a bunch of those away in Python。

 you're only going to have access to a bull true or false a float。

 which is a real number with a decimal point， typically an int or an integer and a string now known as stir。

 So Python here sort of cut some corners feels like it's too long to write out string。

 So a string in Python is called stir STR。 but it's the exact same idea。 notice， though。

 that missing from this now in particular are double and long， which。



![](img/22c0c11fa31af64363e6a5cd04b7fe7c_36.png)

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_37.png)

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_38.png)

Call actually used more bits in order to store information。

 We'll see that that might not necessarily be a bad thing。 In fact。

 Python just simplifies the world and to do different types of variables。

 but gets out of the business of you having to decide you want like a small ant or a large ant or something along those lines。

 Well， let me go ahead and do this。 Let me switch back over to V S code here。😡。

And why don't we actually try to play around with some calculations using these data types and more。

 Let me go ahead and propose that we implement like we did way back in week1， a simple calculator。

 So let me do this code of calculator do C。 So I'm indeed going do this in C first just so that we have a similar example at hand。

 So I'm going include standard I O dot H here at the top。

 I'm going go ahead and do int main void inside of main。

 I'm going go ahead and declare a variable called x and set that equal to get int。

 and I'm gonna prompt the user for that value X。 But if I'm using get in recall that actually is from the C 50 library。

 So in C， I'm going need C50 dot H still for this example。 But back in week1。

 I then did something else。 I then said， give me another variable called Y set that equal to get int and set that equal to that pass in that prompt there。

 And then lastly， let's just do something super simple like add。Two numbers together。 So in C。

 I'll use printf， I'm gonna go ahead and do percent I backslash n as a placeholder。

 And then I'm just gonna plug in x plus y。 So all of that was in C。

 So was a decent number of lines of code to accomplish that task。

 only three of which are really the logical part of my program。

 like these are the three that we're really interested in。

 So let me instead now do this code of calculator do pi， which is going give me a new tab。

 Let me just drag it over to the right so I can view these side by side and in calculator do pi。

 let's do this from the C 50 library import the get int function。😊，Which is also available。

 Then let's go ahead and create a variable called X and set it equal to the return value of get int passing in the same prompt。

 No semicolon， no mention of int。 Let's then create a second variable y said it equal to get in prompt the user for y as before。

 No int explicitly no semicolon。 And now let's just go ahead and print out X plus y。

 So it turns out that the print function in python is further flexible that you don't need these format strings。

 If you want to print out an integer， just pass it in integer。

 Even if that integer is the sum of two other integer。 So it just sort of works as you might expect。

 So let me go down into my terminal here。 let me run python of calculator dot pi。

 And when I hit enter， I'm prompted for X， let's do one， I'm prompted for y， let's do2。

 andvoila I should see3 as the result。 So no actual surprises there。

 But let me go ahead and you know what， let's take away this training wheel。

 We don't want to keep introducing C 50。ific thingsSo suppose we didn't give you get int。 Well。

 it turns out that get int is still doing a bit of help for you。

 even though get string was kind of a throwaway and we could replace get stringing with input。

 So let's try the same idea。 Let's go ahead and prompt the user for input for both X and Y using the input function in Python。

 instead of get int from C S 50。 Let me go ahead and rerun Python of calculator pi and hit enter So far so good。

 Let me type in one。 Let me type in2。 And what answer should we see。Hopefully， still three， but nope。

Now， the answer is 12。Or is it。Why am I seeing 12 and not3。Yeah。

 so where it's actually concatenating what seemed to be too string。

 So if we actually read the documentation for the input function。

 it's behaving exactly as it's supposed to。 It is getting input from the user from their keyboard。

 But anything you type at the keyboard is effectively a string。

 even if some of the symbols happen to look like or actually be decimal numbers。

 they're still gonna come to you as strings And so x is a string， A stir， Y is a stir。

 And we've already seen that if you use plus in between two strings or stirs。

 you're gonna get concatetnation， not addition。 So you're not seeing 12 as much as you're seeing1。

2 not 12。 So how can we fix this。 Well， in C， we had this technique where we could cast one thing to another by just putting like int and parentheses。

 for instance， in Python things are a little higher level such that you can't quite get away with just casting one thing to another because a string recall is not is not the same thing as a char。

 a string has one a0 or more characters a。R always has one。 And in C。

 there was a perfect mapping between single characters and single numbers in decimal。

 like 65 for capital A。 But in Python， we can do something somewhat similar。 And not so much cast。

 but convert this input to an int and convert this input to an in。 So just like in C。

 you can nest function。 you can call one function and pass its output as the input to another function。

 And this now will convert X and Y to integers。 And so now plus is going to behave as you should as you would expect。

 Let me rerun Python of calculator dot pi， type in one， type in2。

 and now we're back to seeing3 as the result。 If this is a little unclear this nesting。

 Let me do this one other way。Instead of just passing inputs output into int。

 I could also more pedantically do this。 X should actually equal int of X。

 Y should actually equal int of y。 This would be the exact same effect。

 It's just like two extra lines where it's not really necessary。 but that would work fine。

 if you don't like that approach， we could even do an in line。

 We could actually convert X to an int and y to an int y。 Well。

 int I T in the context of Python itself is a function。 And it takes as input here。

 a string or stir and returns to you the numeric。 the integral equivalent。

 So similar idea but it's actually a function。 So all of the syntax that I've been tinkering with here。

 is sort of fundamentally the same as it would be in C。 but in this case。

 we're not casting but converting more specifically。 Well， let me go back to these data types。

 These are some of the data types that are available to us in Python。

 turns out there's a bunch of others as well。

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_40.png)

That will start to dabble with today you can get a range of values， a list of values。

 which is gonna to be like an array but better tuples。

 which are kind of like x comma y often combinations of values that don't change dit for dictionary it turns out that in Python you get dictionaries you get hash tables for free they're built into the language and we already saw that Python also gives you a data type known as a set which is just a collection of values that gives you gets rid of any duplicates for you and as we saw briefly in speller and we'll play more with these ideas soon it's going to actually be pretty darn easy to get values or check for values in those their data types so that in C we were able to get input easily。

 we had all of these functions in the CS50 library for Python we're only gonna give you these instead they're going to be the same name so it's still get string not get stir because we wanted the functions to remain named the same but get float get int get string all exist but again get string is not all that useful but get int and get。

😡。

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_42.png)

Float actually R。 why。 well， let me go back to V S code here。

 and let me go back to the second version of this program whereby I proactively converted each of these return values to integers。

 So recall that this is the solution to the one2 problem。

 And to be clear if I run Python of calculator pi and input one and2。

 I get back now three as expected。 But what I'm not showing you is that there's still potentially a bug here。

 let me run python of calculator do pi。 And let me just not cooperate。

 instead of typing what looks like a number。 let me actually type something that's clearly a string like cat。

 And unfortunately， we're gonna see the first of our errors， the first of our runtime errors。

 And this like and C is going to look cryptic at first。

 but this is generally known as a trace back where it's gonna trace back for you。

 everything your program just did， even though this one's relatively short。

 And you'll see that calculator do pi line1， I didn't even get very far before there's an error。



![](img/22c0c11fa31af64363e6a5cd04b7fe7c_44.png)

AndWith all of these carrot symbols here， like this is a problem。

 Why invalid literal for int function with base 10， quote unquote cat。 Again。

 just like see it's very arcane。 It's hard to understand this the first time you read it。

 But what it's trying to tell is that cat is not an integer。 And therefore。

 the int function cannot convert it to an integer for you。

 We're gonna leave this problem alone for now， But this is why， again。

 get ins looking kind of good and get floats looking kind of good。

 because those functions from C50's library will deal with these kinds of problems for you。 Now。

 just so you've seen it， there's another way to import functions from these things。

 If you were to use， for instance， in a program， get float get in and get string。

 you don't need to do three separate lines like this。

 you can actually separate them a little more cleanly with commas。 And， in fact。

 if I go back to a version of this program here in V S code whereby I actually do use the get int function。

 So let me actually get rid of all this and use get int as。😊。



![](img/22c0c11fa31af64363e6a5cd04b7fe7c_46.png)

Let me get rid of all this and use get int as before previously the way I did this was by saying from CS 50 import get int。

 if you know in advance what function you want to use。

 But suppose for whatever reason you already have your own function name get int。

 and therefore it would collide with C50 zone。 you can avoid that issue too by just using that first statement we saw earlier。

 just import the library itself， Don't specify explicitly which functions you're gonna use but thereafter。

 and you could not do this in C。 you could specify C 50 dot get int C50 dot get int in order to go into the library access its get in function and therefore it doesn't matter if you or any number of other people wrote an identically named function called get int。

 you're using here clearly C 50 zone。 So this is again。

 just a more ways to achieve the same solution but with different syntax。



![](img/22c0c11fa31af64363e6a5cd04b7fe7c_48.png)

Alright， any questions about any of this syntax or features。



![](img/22c0c11fa31af64363e6a5cd04b7fe7c_50.png)

Thus far。Now， all right。 Well， how about maybe another example here whereby we revisit conditionals。

 which was the way of implementing do this thing or this thing。

 sort of proverbial forks in the road in scratch recall。

 we might use building blocks like these to just check is X less than y。 And if so， say so in C。

 this code looked like this。 and notice that we had parentheses around the X and the Y。

 We had curly braces， even though I did thisclaim that for single lines of code。

 you can actually omit the curly braces， but stylistically， we always include them in Cs 50s code。

 But you have the backslash N and the semicolon。 In a moment。

 you're about to see the python equivalent of this， which is almost the same。

 It's just a little nicer。 this then is the python equivalent thereof。

So what's different at a glance here， just to be clear。😡，What's different， yeah。

So the conditional is not in parentheses。 You can use parentheses。

 especially if logically you need to group things， But if you don't need them。

 don't use them is Python's mindset。 What else has changed here， yeah。No curly braces。 Yes。

 so no curly braces around this。 And even though it's one line of code。

 you just don't use curly braces at all。 why， Because in Python， indentation is actually really。

 really important。 And we know from office hours and problem sets occasionally that if you forgot to run style 50 or you didn't manually format your code beautifully。

 C is not actually going care if everything is aligned on the left。

 if you never once hit the tab character or the space bar C or specifically clang isn't really going care but your teaching fellow。

 your T is going to care or your colleague in the real world because your codes just a mess and hard to read Python。

 though， because you are not the only ones in the world that might be might have bad habits when it comes to style。

 Python as a language decided That's it like everyone has to indent in order for their code to even work。

 So the convention is Python is to use four spaces So 1，2，3。

4 or hit tab and let it automatically convert to the same and use a colon And of the curly braces。

 for instance，Cl what is associated with this particular conditional。 We can omit though。

 the backslash n for per before。 we can omit the semicolon。

 but this is essentially the Python version thereof here in C in scratch。

 if you wanted to do an if else like we did back in week 0 in C， it's very similar to the if。

 except you add the else clause and write out an additional printf like this in Python。

 we can tighten this up if X less than y colon， that's exactly the same first lines the same。

 all we're doing now is adding an else and the second print line here， How about in scratch。

 if we had a threeway fork in the road。 If else， if else in C， it looked pretty much like that。

 if else， if else， in Python， we can tighten this up。



![](img/22c0c11fa31af64363e6a5cd04b7fe7c_52.png)

And this is not a typo。What jumps out at you is weird， but you gotta just get used to it。



![](img/22c0c11fa31af64363e6a5cd04b7fe7c_54.png)

Yeah。L if。 and honestly， like years later， I still can't remember if it's L if or else if because other languages actually do E L S I F。

 So， and now I probably now biased all YouTube now questioning this， But it's L if in Python。

 E L I F is not a  typepo。 It's in the spirit of， let's just save ourselves some keystroke。

 So L if is identical to else if， but it's a little tighter to type it this way。 Alright。

 so if we now have this ability to express conditionals， what can we actually do with them， well。

 let me go over to V S code here。😊，And let me propose that we revisit maybe another program from before where we just compare two integers in particular。

 So I'm in VS code。 Let me open up a file called say compare dot pi and then compare dot pi we'll use the CS50 library just so we don't risk any errors like if the human doesn't type in integer。

 So we're going to go ahead and say from CS 50 import， get in and then compare dot pi。

 let's get two variables。 X equals get int and prompt the user for X So what's x question mark to be a bit more verbose y equals get int quote unquote what's y question mark and then let's go ahead and just compare these two values。

 So if x is less than y then go ahead and print out with print X is less than y close quote L if X is greater than y。

 go ahead and print out X is greater than y close quote else go ahead and print out X is equal to y So the exact same program but。

😡，Added to the mix， getting a value of x and Y。 Let me run Python of compare dot pi enter St in one for x 2 for y。

 X is less than y。 Let's run it once more。 X is2， Y is one X is greater than y。

 and just for good measure， Let's run it a third time。 X is one。 Y is one。 X is equal to Y。

 So the code dare say works exactly as you would expect。 as you would hope。

 But it turns out that in the world of python， we're actually going get some other behavior that might actually have been what you expected weeks ago。

 even though C did not behave this way。 in the world of python and in the world of strings。

 Aka stirs， strings actually behave more like you would expect。 So by that， I mean， this。

 let me actually go back to this code。 And instead of using integers。 let me go ahead and get rid of。

 I could do get string， but we said that that's not really necessary。

 So let's just go ahead and change this to input。 And actually， you know this start fresh。

 Let's give myself a string。Called S and use the input function and ask the user for S。

 Let's use another variable called T。 just because it comes after S and use the input function to get T。

 Then let's compare if S and T are the same。 Now， a couple weeks ago， this backfired。

 And if I tried to compare two strings for equality， it did not work。

 But if I do if S equals equals T print quote unquote same。 else， let's go ahead and print different。

 I dare say in Python， I think this is gonna work as you would expect。 So Python of compared do pi。

 let's type in cat and cat， And indeed， those are the same。

 let me run it again and type in cat and dog respectively， And those are now different。 But in C。

 we always got different， different， different。 even if I type the exact same word。

 be it cat or dog or high or anything else。 why in C。

 were S and T always different a couple weeks ago， yeah。😡。

Because it was preparing the value of the chart。Me addressExactly in C string is the same thing as char star。

 which is a memory address。 And because we had called get string twice。

 even if you human type the same things。 that was two different chunks of memory at two different addresses。

 So those two char stars were just naturally always different。

 even if the characters at those addresses were the same。 Python is meant to be higher level。

 it's meant to be a little more intuitive， it's meant to be more accessible to folks who might not necessarily know or want to understand those lower level details。

 So in Python equals equals even for strings just works the way that you might expect。 But in Python。

 we can do some other things to even more easily than we could in C， let me go back to Vs code here。

 Let me close compared dot pi。 and let's reimplement a program from C called agree which allowed us to prompt the user for like a yes no question。

 like do agree to these terms and conditions or something like that。

 So let's do code of agree dot pi。 And with agree dot pi， let me go ahead and。

 let's go ahead and do this。 Let me also open up a file that I came with in advance。

 And this is called a agree dot C。 And this is what we did some weeks ago。

 when we wanted to check whether or not the user had agreed to something or not。

 So we use the C 50 library， the standard I O library。 We had a main function。 We used get cha。

 And then we used equals equals a lot。 And we used the two vertical bars。

 which meant logical or is this thing true or is this thing true。

 And if so printf agreed or not agreed。 So this worked。 And this is relatively simple。

 It's like the right way to do it in C。 But notice it was a little verbose because we wanted to handle uppercase and lowercase。

 uppercase and lowercase， So that did start to blo the code admittedly。

 So let's try to do the same thing in Python and see what we can do the same or different。

 No pun intended。 So let me do this in a agreed dot pi。

 Why don't we try to get input from the user as before。And I will use， I could use get string。

 but I'll go ahead and use input。 So S equals input。 Do you agree question mark in double quotes。

 And then let's go ahead and check if S equals equals capital Y。 And it's not vertical bar now。

 it's actually more readable more English like or S equals equals lowercase Y。

 then go ahead and print out agreed as before L if say I did it there。

 L if S equals equals capital n， or S equals equals lowercase N， go ahead and print out not agreed。

 So it's almost the same as the C version， except that I'm using literally O R instead of two vertical bars。

 So let's run this So Python of agreed dot pi enter do I agree， Yes， for little y， let's do it again。

 Python of agreed dot pi capital Y。 Yes， that works there。 And if I do it again with lowercase N。

 And if I do it with capital N， this program。2 seems to work。 But what if I do this。

 Let me rerun Python of a agreed dot pi。 Let me type in yes， Okay， just ignores me。

 Let me run it again。 Let me type in no， Just ignores me。 Let me try it very emphatically。

 yes in all caps， It just ignores me。 So there's some explosion of possibilities that ideally。

 we should handle， this is bad user interface design， if I the user has to type Y or N。

 even if yes and no in English are perfectly reasonable and logical too。 So how could we handle that。

 Well， it turns out in Python， we can use something like an array。

 technically call the list to maybe check a bunch of things at once。 So let me do this。

 Let me instead say not equality。 But let me use the in keyword in Python and check if it's in a collection of possible values。

 Let me say if S is in。 And here comes in square brackets just like。In square brackets。

 quote unquote why， comma， quote unquote， yes， then we can go ahead and print out agreed。 L。

 if S is in this list of values， lowercase N or lowercase。 No， then we can print out， for instance。

 not agreed。 But this is a bit of a step backwards， because now I'm only handling lower case。

 So let me go into the mix and maybe add capital Y， wait a minute， then maybe capital。 yes。

 than maybe yes， also， I mean， weird， but we should probably support this and like yes， I mean。

 there's like a lot of combination。 So this is not gonna end well。

 or it's just gonna bloat my code unnecessarily。 And eventually for longer words。

 I'm surely gonna miss capitalization。 So logically， whether it's in Python or C or any language。

 What might be a better design for this problem。 of handling why and yes。

 but who cares about the capitalization。So don't， okay， so don't use capitals。

 You could only support a lowercase。 That's fine。 That's kind of a cop out， right， because now。

 like the program's usability is worse。Oh， we could convert it to lowercase。 Yeah。

 though I did hear you say we could just check the first letter。

 I bet that's gonna get us into trouble。 and we probably don't want to allow any word starting with y。

 any word starting with n just because logically， especially you want like the lawyers happy。

 presumably you should probably get an explicit， semantically correct word like why or N or yes or no。

 But yeah， we can actually go about converting this to something maybe be smaller。

 But how do we go about converting this in C， that alone was gonna be pretty darn annoying because we'd have to sort of use the two lower function on each on every character and compare it for equality。

 just feels like that's a bit of work。 But in Python， you're gonna get more functionality for free。

 So there might very well be a function like and C called too lower or two upper。

 But the weird thing about C， perhaps in retrospect。

 is that those functions just kind of worked on the honor system too lower and too upper。

 just trusted that you would pass them in input in argument that is， in fact。

A char in Python and in a lot of other higherle languages。

 they introduced this notion of objectoriented programming。

 which is commonly described as OOP And in the world of objectoriented programming。

 your values can not only your variables for instance。

 and your data types can not only have values that can also have functionality built into them。

 So if you have a data type like a string， frankly。

 it just makes good sense that strings should be uppercaseable， lowercaseable。

 capitalizable and any number of other operations on strings。

 So in the world of objectoriented programming， functions like too upper and too lower and is upper and is lower are not just in some random library that you can use。

 they're built into the strings themselves And what this means is that and the world of strings in Python here。

 for instance， is the URL of the documentation for all of the functions otherwise known as methods that come with strings So you don't go check for like a C type library like we didn't see。

You check the actual data type， the documentation therefore。

 and you will see in Python's own documentation what functions aka methods come with strings。

 So a method is just a function， but it's a function that comes with some data type like a string。

 So let me propose that we do this in the world of object oriented programming。

 we can come back to a dot pi and we can actually improve the program by getting rid of this crazy long list。

 which I wasn't even done with and just canonicalize everything as lowercase。

 So let's just check for lowercase y and lowercase yes， lowercase n lowercase no， and that's it。

 but to your suggestion， let's force everything that the user types in lowercase。

 not because we want to permanently change their input， we can throw the value A thereafter。

 but because we want to more easily logically compare it for membership in this list of values。

 So one way to do this would be to literally do S equals S。😡。

LerSo here's the difference in the world of C， we would have done this to lower and pass in the value S。

 But in the world of Python。 and in general， object oriented programming。

 Java is another language that does this。 if S is a string， Aka stir， therefore。

 S is actually what's known in Python as an object and object can not only have values or attributes inside of them。

 but also functionality built in。 And just like in C with astruct。

 if you want to go inside of something， you use the dot operator。

 And inside of this string I claim is a function aka method called lower long story short。

 the only takeaway if this is a bit abstract is that instead of doing lower and then in parentheses S in the world of object oriented programming。

 you kind of flip that and you do S dot name of the method。 And then open print and close print。

 if you don't need to pass in any arguments。 So this actually achieves the same。

 So let me go ahead and rerun a dot pi， And let me type in lower。Why that works。 Let me run it again。

 type in lowercase。 Yes， that works。 Let me run it again。 type in capital Y that works。

 Let me type in capital。 Yes， all capital all uppercase。 yes， that two works。

 Let me try no let me try no in lowercase and all of these permutations now actually work。

 because I'm forcing it to lowercase。 But even more interestingly in Python。

 if you're sort of becoming a languages person， if you have a variable S that is being set the return value of input function。

 And then you're immediately going about changing it to lowercase you can also chain method calls together in something like Python by doing this。

 we can get rid of this line altogether， and then I can just do this dot lower。

 And so whatever the return value of input is， it's gonna to be a stir whatever the human types in。

 you can then immediately force it to lowercase and then assign the whole value to this variable called S。

 you don't actually have to wait around and do it on a separate line。Alltoge。Questions， then。

On any of this。All right， let me do one other that's reminiscent of something we did in the past。

 Let me go into VS code here。 clear my terminal。 Let's close both the C and the Python version of agree。

 and let's create a program called uppercase do pi whose purpose in is to actually uppercase a whole string in the world of C we had to do this character by character by character and that's fine。

 I'm going go ahead and do it similarly here in Python whereby I want to convert it character by character。

 But unfortunately before I can do that I actually need like some way of looping in Python。

 which we actually haven't seen yet。 so we need one more set of building blocks， and in fact。

 if we were to consult the python documentation， we'd see this and much more So in fact。

 here is a list of all of the functions that come with Python。

 it's actually not that long of a list because so much of the functionality of Python is built into data types like strings and integers and floats and more here is the canonical source of truth for python documentation。

 So as opposed to using like the C 50 manual for C， which is。



![](img/22c0c11fa31af64363e6a5cd04b7fe7c_56.png)

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_57.png)

To be a simplified version of a publicly available documentation will generally。

 for Python point you to the official docs。 I will disclaim they're not really written for like introductory students and they'll generally leave some detail off and use arcane language。

 But at this point in the term， even if it might be a little frustrating at first。

 it's good to see documentation in the real world because that's what you're gonna have after the course。

 And so you'll get used to it through practice over time。 But with loops。

 let's introduce one other feature that we can compare to scratch here， for instance。

 in scratch is how we might have repeated something three times like meowing on the screen in C。

 there are a bunch of ways to do this。 and the clunkest was maybe to do it with a while loop where we declare a variable called I said it equal to0 and then iteratively increment I again and again。

 until it exceeds until it equals3 each time printing out meow In Python。

 we can do this in a few different ways as well。 the nearest translation of C into Python is perhaps。

😊，ThisIt's almost the same and logically， it really is the same。

 but you don't specify int and you don't have a semicolon。 You don't have curly braces。

 but you do have a colon。 You don't use printf。 You use print and you can't use i plus plus。

 but you still can use I plus equals 1。 So logically exactly the same idea as in C。

 It's just a little tighter。 I mean， it's a little easier to read， even though it's very mechanical。

 if you will， You're defining all of these， you're defining this variable and changing it incrementally。

 Well， recall that in C， we could also use a four loop。

 which at first glance was probably more cryptic than a while loop， but odds are by now。

 you're more comfortable or more in the habit of using loop， same exact idea in Python， though。

 we might do it like this。 We've seen how in square brackets， you can have lists of values like why。

 yes， and so forth。 Well， let's just do the same thing with numbers。

 So if you want Python to do something three times。 give it a list of three values like 0，12。

 And then print out hello world that many times。😊，Now， this is correct， but it's bad design。

Even if you've never seen Python before， like extrapolate mentally from this。

 Why is this probably not the right way or the best way to do this looping。Yeah。

 if you want to do it four times  five times，50 times 100 times。 I mean。

 surely there's a better way than enumerating all of these values。 and there is， in fact， in Python。

 there's a function called range that actually returns to you very efficiently a range of values and by default。

 it hands you the number 0 and then one and then two。 and if you want more than that。

 you just change the argument to range to be how many values do you want。

 So if you pass in range of 50， you would get back0 through 49。

 which effectively allows you to do something 50 times in total。

 So this is perhaps the most pythonic way。 So to speak， and this is actually a term of art。

 Pythonic isn't necessarily the only way to do something。

 but it's the way to do something based on sort of consensus in the Python community。

 So it's pretty common to do this。 But there's some curiosity here。

 notice I'm declaring a variable I， but I'm never actually using it。 In fact。

 I don't even increment it because that's sort of happening automatically。

 what's really happening here is automatic。ically in Python on every iteration of this loop。

 Python is assigning I to the next value。 So initially I is 0， then it goes through an iteration。

 then I is one。 then I is 2。 And then that's it。 if you only asked for three values。

 But there's this other technique in Python。 just so you know， whereby if you're the programmer。

 And you know， you don't actually care about the name of this variable。

 you can actually change it to an underscore， which has no functional effect per se。

 It just signals to the reader， your colleague， you're teaching fellow， that it's a variable。

 and you need it in order to achieve a for loop， but you don't care about the name of the variable because you're not gonna to use it explicitly anywhere。

 So that might be an even more pythonic way of doing things。

 But if you're more comfortable seeing the I and using the variable more explicitly， that's fine。

 underscore does not mean anything special。 It's just a valid character for a variable name。

 So this is convention， Nothing more technical than that。 What about a forever loop in scratch。

 Like literally meow forever。Well， over here， we can just use in see while true print F Miow again and again and again。

 in Python， it's almost the same。 You still get rid of the curly braces。 You add the colon。

 You get rid of the semicolon， but there's a subtlety。



![](img/22c0c11fa31af64363e6a5cd04b7fe7c_59.png)

What else is different here， yeah。So true is uppercase。

 Why who knows like the world decided that in Python。

 true is capitalized and false is capitalized in many other languages， they're say most they are not。

 It's just a difference that you have to keep in mind or remember。 Allright。

 so now that we have looping constructs。 Let me go back to my code here and recall that I propose that we reimplement a program like uppercase。

 force an entire string to uppercase。 And in C， we would have done this with like a for loop。

 iterating from left to right。 But what's nice in Python， frankly。

 is that it's a lot easier to loop in Python then it is in C because you can loop over anything that is iterable。

 Like a string is iterable in the sense that you can iterate over it from left to right。

 So what do I mean by this。 Well let me go ahead and in uppercase。

 Let's first prompt the user for a variable called before and set that equal to the return value of input。

G them a prompt of before colon， then let's go ahead as we did weeks ago and print out just the word after just to make clear to the user what is actually going to be printed then let me go ahead and specify the following loop for and previously you saw me use I。

 but because I'm dealing with characters， I'm actually going to do this instead for C in before colon。

 print out C dot upper。😡，And that's it。 Now， this is a little flawed。 I will concede。

 but let me run this。 Python of uppercase dot pi。 Let's type in something like cat， C。

 A T in all lowercase。 enter。 Al right， well， you see after。

 and I did get it right in the sense that it is capital like C， capital A， capital T。

 but it looks a little stupid。 And in order to fix this。

 we actually need to introduce something that's called named parameters。

 So let me actually go ahead and。

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_61.png)

Proposed that We can fix this problem。By actually passing in another argument to the print function。

 And this is a little different syntactically from C。 But if I go back to VS code here。

 it turns out that there's two aesthetic problems here。1， I did not want the new line。

 automatically insert it after after y because just like in week 1。

 I want them to line up nicely or in week 2 and I don't want a new line after C。

 So even though at first glance a moment a bit ago。

 it might have seen nice that Python just does the backslash end for you can backfire。

 if you don't actually want a new line every time。 So the syntax is gonna look a little weird。

 but in Python with the print function， if you want to change the character that's automatically used at the end of every line。

 you can literally pass in a second argument。😡，Called end and set it equal to something else。

 So if you want to set it equal to something else。 and that something else is nothing， quote unquote。

 then that's fine。 you can actually specify end equals quote unquote down here too。

 If you want to specify that the end at the end of every one of these characters should be nothing I can specify end equals quote unquote。

 what this implies is that by default in Python， the default value of this end parameter is actually always backlash n。

 So if you want to override it and take that away， you just literally change it to quote unquote instead。

 And now if I clear if I rerun this program。 uppercase stop I type in cat in all lowercase now you'll see two minor bugs here。

 One was just stupid。 I had one too many spaces here。

 but you'll notice that I didn't move the cursor to the next line after cat was printed in all uppercase。

 and that we can fix by just printing nothing。 it turns out。

When you don't pass print an argument at all， it automatically gives you just the line ending。

 nothing else。 So I think this will move the cursor as expected。 So let me clear it now。

 run Python of uppercase do high and hit enter， type in cat and all lowercase。

 cross my fingers this time。 And now I have indeed capitalized this character by character by character。

 just like we did。😡，In sea。But honestly， this too， not really necessary。

 turns out I don't need to loop over a whole string because strings themselves come with methods。

 And if you were to visit the documentation for strings， you would see that indeed。

 upper is a method that comes with every string and you don't need to call it on every character individually。

 I could instead get rid of all of this。 and just print out， For instance， I can just print out。😡。

Before dot upper and the upper function that comes with strings will automatically apply to every character therein。

 And I think achieve the same result。 So let me go ahead and try this again。

 Python of uppercase dot I type in C A enter and indeed， it works exactly the same way。

 Let me take this one step further。 let me go ahead and combine a couple of ideas now here。

 let me go ahead and for instance， let me get rid of this last print line。

 let me change my logic to be after equals the return value of this。

 And now I can use one of those F strings and plug this in maybe here after and I can get rid of the new line ending。

 I can specify this is an F string。 So I'm just changing this around a little bit logically so that now I have a variable called after that is the uppercase version of before。

 And now if I do python of uppercase do type in C that now works。

 And if I actually let me add a space there。 if I run Python of uppercase dot I type in C that two now works。

 and last。HereIf you don't want to bother to creating another variable like this。

 you can even put short bits of code inside of these format strings。 So I， for instance。

 could go in here into these curly braces and not just put a variable name。

 I can actually put Python code inside of the curly braces inside of my string。

 And so now if I run Python of uppercase pi type in cat even that too now works Now which one is the best this is kind of reasonable to put the bit of code inside of the string。

 I would not start writing long lines of code inside of curly braces that start to wrap no less because then it's just gonna to be matter of bad style。

 but this again is to say that there's a bunch of different ways to solve each of these problems。

 And so up until now， we've generally seen not named parameters and is the first parameter we've ever seen that has a name literally end up until now in C and up until a moment of ago in Python。

 we've always been assuming that our parameter or positional What matters is the。



![](img/22c0c11fa31af64363e6a5cd04b7fe7c_63.png)

Ororder in which you specify them， not necessarily something else。Okay， that was a lot。

 Any questions？About any of this here。No， all right。 feels like a lot。

 Let's take our 10 minute break here。 Fit Roups are now served。 We'll be back in 10。All right。

 we are back。And recall that as we left off， we had just introduced loops and we'd seen a different a bunch of different different ways by which we could get。

 say a cat to Mio。 Let's actually translate that to some code and start to make sense of some of the programs with which we began。

 like creating our own functions as we did for the speller example at the very beginning and actually do this a little more methodically。

 So let me go over to V S code here， let me go ahead and create a program called Mio dot pi instead of Miow do C in the past。

 and suffice it to say if you want to implement the idea of a cat。

 we can do better than just saying print Mio print Mio print Mio。 This， of course， would work。

 this is correct。 If the goal is to get the thing to Mio three times。

 But when I run Python of Mio do pi， it's going to work as expected。

 But this is just not good design we should minimally be using a loop。

 So let me propose that we improve this per the building blocks we've seen。

 And I could say something like4 I in range of three go ahead and print out。😊。



![](img/22c0c11fa31af64363e6a5cd04b7fe7c_65.png)

Now quote unquote miow。 So this is better in the sense that it's still print meo Mio Miow。

 But if I want to change this to like a dog and change meow to aof or something like that。

 I can change it in one place and not three different places。 So just in general， better design。

 But what if now much like in scratch and in see， I wanted to create my own mio function。

 which did not come with either of those languages as well。 Well， as a teaser at the start of class。

 we saw that you can define your own functions with this keyword de。

 which is a little bit different from how C does it。

 But let me go ahead and do this indeed in Python and define my own function Miow。

 So let me go ahead and do de space Miow open per end close per n。 And then inside of that function。

 I'm just gonna literally do for now， quote unote miow with print。 And now down here notice。

 I can actually go ahead and just call Miow。 And I can go ahead and call miaow。 and I can call Miow。

 And this is not the best design at the moment。 But。

Python does not constrain me to have to implement a main function as we've seen thus far。

 but I can define my own helper functions， if you will， like a helper function called Miow。

 So let me go ahead and just run this for demonstration's sake and run Python of meot pi that does seem to work。

 but this is not good design and let me go ahead and actually do this for I in range of three now let me call the meow function and this two should work if I do Python of meow pi there we have meow meow meow but I very deliberately did something clever here。

 I defined meow at the top of my file。 but that's not the best practice because as in C when someone opens the file for the first time whether it's you a T A T。

 a colleague， you'd like to see the main part of the program at the top of the file just because it's easier mentally to dive right in and know what this file is doing。

 So let me go ahead and practice what I'm preaching and put the main part of my code。

 even if there's no main function per se at the top of this file So now I have the loop。😡，The top。

 I'm calling meo on line 2。 and I'm defining meow on lines 5 and 6。 Well， instinctively。

 you can perhaps see where this is going。 If I run Python of Mio dot Pi and hit enter。

 there's one of those tracebacks that's tracing my error。 And here。

 my error is apparently online line 2 in Miow dot5 And you'll notice that the name Mio is not defined。

 And so previously， we saw a different type of error。 a value error。 Here。

 we're seeing a name error in the sense that Python does not recognize the name of this function。

 And intuitively， why might that be。😊，Even if the error is a little cryptic， yeah。Yeah。

 Python 2 is as fancier as it seems to be than C。 It still take things pretty literally top to bottom left to right。

 So if you define meow on line 5。 Yeah can't use it on line too。 Okay， so I could undo this。

 and I could flip the order。 But let me just stipulate that as soon as we have a bunch of functions。

 It's probably naive to assume I can just keep putting my functions above above above above。

 And honestly， that's gonna move all of my know main code， so to speak to the bottom of the file。

 which is sort of counterproductive or less obvious。 So it turns out in Python。

 even though you don't need a main function， it's actually quite common to define one nonetheless So what I could do to solve this problem is this let me go ahead and define a function called main that takes no arguments。

 in this case， let me indent that same code beneath it。

 And now let me keep meow defined at the bottom of my file。 So if we read this literally on line 1。

 I'm defining a function called main。 And it will do what is prescribed on lines 2 and3 On line 6。

 I'm defining a function called。And it will do what's prescribed on line 7。

 So it's fairly straightforward， even though the keyword de is， of course， new today。 If I run。

 though Python of Mao do Pi， you'd like to think I'll see three miless， but。I see nothing。😡。

I don't see an error， but I see nothing why intuitively。 What explains the lack of behavior。

I didn't call main。 So this is the thing， even though it's not required in Python to have a main function。

 but it is conventional in Python to have a main function， you have to call the function yourself。

 It doesn't get magically called as it does in C。 So this might seem a little stupid。

 and that's fine。 but it is the convention in Python generally。

 the very last line of your file might just be literally this call main。

 because this satisfies the constraint that main is defined on line 1。 Mio is defined on line 6。

 but we don't call anything until line 10。 So line 10 says call main。

 So that means execute this code。 Line3 says call meow， which means execute this code。

 So now it all works because the last thing I'm doing is called main is called main。

 you can think of C is just kind of secretly having this line there for you the whole time。

 But now that we have our own function。 notice that we can enhance this implementation of Miow to maybe be parameterized and take actually an argument itself。

😡，So let me make a tweak here， just like in C and just like in scratch。

 I can actually let meow Miow a specific number of times。 So let me do this。 Wouldn't it be nice。

 instead of having my loop in main to instead just distill main into a single line of code and just pass in the number of times you want the thing to meow。

 What I could do in Miow here is I have to give it a parameter， and I could call it anything I want。

 I'm going call it n for number， which seems fine。 And then in the meow function。

 I could do this for I in range of not3， but n now。

 I can tell range give me a range that is a variable length based on what n is。

 And then I indent the print below the loop now， And this should now do what I expect2。

 let me run Python of meow dot pi enter and there's3。

 But if I change the three to a5 and rerun this Python of meow dot pi。 Now I'm getting five meos。

 So we've just seen a third way how in Python now we can implement the idea of。

Mowing as its own abstracted function。 And I can assume now that meow exists。

 I can now sort of treat it as out of sight out of mind。 It's an abstraction。 And frankly。

 I could even put it into a library， import it from a file like we've done with C50。

 and sort of make it usable by other people as well。 So the takeaway here really， though。

 is that in Python， you can similarly to C， define your own functions。

 But you should understand the slight differences as to what gets called automatically for you。

 Allright， other differences are similarities with C。 Well， recall that in C truncation was an issue。

 truncation is whereby if you， for instance， divide an int by an int， and it's a fractional answer。

 everything after the decimal point gets truncated by default。

 because an in divided by an int in C gives you an int。

 And if you can't fit the remainder in that integer， everything at the decimal gets cut off。

 So what does this mean。 Well， let me actually go back to V S code here， let me go ahead and open。

 say。Calculator dot pi again。 And let's change up what the calculator now does。 Let me do this。

 Let me define a variable called X。 set it equal to the input function， prompting the user for X。

 Let me ask the user for y。 let me not repeat past mistakes。

 and let me proactively convert both of these to ins。

 and I'll do it in one pretty one liner here so that I definitely get x and y and on the honor system。

 I just won't type cat。 I won't type dog even though this program is not really complete without error checking。

 Now， let me go ahead and declare third variable。 Z equals x divided by y。

 And now let's just go ahead and print out Z。 I don't need a format code。 I don't need an f string。

 if all you want to do is print a variable。 print is very flexible。

 You can just say print Z in parentheses。 Let me run Python of calculator do pi。

 hit enter Let's type in 1，4 x 3，4 Y。 I left out a space there。 And oh， interesting。

What seems to have happened here， Let me fix my spacing and breathe around this again。

 Python of calculator dot pi。 So 1，3， what did not happen。Yeah， so it did in trunccate。

 So Python's a little smarter when it comes to converting one value to another。

 So an integer divided by an integer， if it ends up giving you this fractional component not to worry now。

 you'll get back what is effectively aloat in Python here。 Well。

 what else do we want to be mindful of in say Python。 Well， recall that in C。

 we had this issue of floating point in precision whereby if you want to represent a number like one third and on a piece of paper。

 it's like 0。3 with a line over it because the three infinitely repeats。

 but we saw a problem in C last time when we actually play it around with some value。

 So for instance， let me go back to V S code here。 And this is gonna be the ugliest syntax。

 I do think we see today。 But there was a way in C using percent F to show more than the default number of digits after the decimal point to see more significant digits。

 in Python， there's something similar。 It just looks very weird。

 And the way you do it in Python is this You specify that you want an F string， a format string。

And I'm just gonna start and finish my thought first。

 F before quote unquote If you want to print out Z， you could literally just do this。

 And so this is just an f string， but you're interpolating Z。

 So it doesn't do anything more than it did a moment ago when I literally just passed in Z。

 But as soon as you have an F string， you can configure the variable to print out to a specific number of digits。

 So if you actually want to print out Z to say 50 decimal points just to see a lot。

 you can use crazy syntax like this。 So it's just using the curly braces as I introduced before。

 but you then use a dot after a colon， and then you specify the number of digits that you want。

 and then F to make clear it's a float。 Honestly， I Google this all the time。

 when I don't remember the syntax。 But the point is the functionality exists。 Allright。

 let me go down here， and rerun Python of calculator dot pi。 And unfortunately， if I divide one by3。

 not all of my problems are solved floating point precision is still a thing。

Mindful of the fact that there are these limitations in the world of Python Flo point precision remains。

 If you want to do even better than that， though， there exist a lot more libraries。

 third party libraries that can give you much greater precision for scientific purposes。

 financial purposes or the like。 But what about another problem from C integer overflow。

 Like if you just count too high， recall that you might accidentally overflow the capacity of an integer and end up going back to0 or worse going negative altogether in Python。

 this problem does not exist in Python when you have an integer a int。

 even though we haven't needed to use the keyword int。

 it will grow and grow and grow and Python will reserve more and more memory for that integer to fit it。

 So it is not a fixed number of bits。 So floating point in precision， still a problem。

 integer overflow， not a problem in the latest versions of Python。 So a difference worth knowing。

 But what about other features of Python that we didn't have。Well。

 let's actually revisit one of those tracebacks， one of those errors I ran into earlier to see how we might actually solve it。

 So let me go back to VS code here。😡，And just for fun， let me go ahead and do this。

 Let me clear my terminal and let me change my calculator to actually have a get in function。

 We've seen how to define our own functions。 Let me not bother with the C 50 library。

 Let me just invent my own get int function as follows。 So def get int。

 and just like the C S 50 function。 I'm gonna have get int。

 take a prompt a string to show the user to ask them for an integer。

 And now I'm gonna go ahead and return the return value of input passing that same prompt to input because input just like get string shows the user a string of text。

 But I do want to convert this thing here to an int。

 So this is just a one line or really of an implementation of get in。

 So this is kind of like what C 50 did in its Python library。 but not quite Y。

 because there's a problem with it。 So let me do this。

 Let me define a main function just by convention。 Let me use this implementation of get in to ask the user for X。

 Let me use this get in function to prompt the user for y。 And then let me do something simple。

 like print out X plus y。😊，And then very last thing I have to call main。 And this is a minor point。

 but I'm deliberately putting multiple blank lines between my functions。 This two is pythonic。

 It's a matter of style。 Style 50 will help you with this。

 It's just meant for larger files to really make your functions stand out and be a little more separated visually from others。

 Allright， let me go ahead and run Python of calculator dot pi enter。 Let me type in one。

 Let me type in3。 And that actually works。1 plus 3 is 4。 Let me do the more obvious。

1 plus 2 gives me3。 So the calculator is， in fact， working until such time as I。

 the human don't cooperate and type in something like cat for x。

 Then we get that same trace back as before。 But I'm seeing it now in this file。

 and let me zoom in on my terminal just to make clear。

 We don't need to see the the old history there。😊。

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_67.png)

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_68.png)

Let me let me type in cat enter。 and you'll see the same trace back。 And you'll see that， okay。

 here's where now there's multiple functions involved。 So what's going on。

 The first problems that line 12 in main， But that's not actually the problem because main calls might get in functions。

 So on line 6 of calculated pi。 This is really the issue。 So again。

 it's tracing everything that just happen from top to bottom here。

 and value error in literal4 inch with base 10 cat， which is to say like before。

 it just cat is not an integer in base 10 or any other base。

 it just cannot be converted to an integer。 So how do you fix this or really。

 how does the C 50 library fix this。 You won't have to write much code like this。

 But it turns out that pythonic support what are called exceptions。 And generally。

 an exception is a better way of handling certain types of errors Because in C。

 recall that the only way we could really handle errors is by having functions returns。

Spec values like Maloc could return null， which means it ran out of memory。 Something went wrong。

 Some functions we wrote and C could return one， could return2， could return negative one。

 recallre called that we could write our own functions that return values to indicate something went wrong。

 But the problem in C is that if you're stealing certain values， be it null or one or two or three。

 your function can never return null or one or two or three as actual values。 Y。

 because other people are going interpret them as errors。

 So you kind of have to use up some of your possible return values in a language like C and treat them specially as errors in Python and other languages。

 Java and others， you don't have to do that， you can instead have more out of band error handling known as exceptions。

 And that's what's happening here。 When I run calculator pi， and I type in cat。

 What I'm seeing here is actually an exception。 It's something exceptional。

 but not in a good way like。Exception means this was not supposed to happen。

 The type of exception happens to be called a value error。 And within the world of Python。

 there's this whole taxonomy。 That is to say a whole list of possible exceptions。

 Val error is one of the most common。 We saw another one before name error when I said Miow when Python didn't know what Miow meant。

 So this is just an example of an exception。 But what this means is that there is a way for me to try to handle this myself。

 So I'm actually going go ahead and do this。 instead of get int simply blindly returning the integer conversion of whatever input the user gives me。

 I'm gonna instead literally try to do this instead， So it's kind of an aptly named phrase。

 It literally means that please try to do this except if something goes wrong。

 except if there is a value error in which case I want Python to do something else。 for instance。

 quote unquote not an integer。 So what does this mean， it's a little weird the syntax。

 But in the get in function。Python will first try to do the following。

 It will try to get an input from the user。 It will try to convert it to an integer and it will try to return it。

 But if one of those operations fails， namely the integer step in this case。

 then an exception could happen and you might get what's called a value error why because the documentation tells you that might happen or in my case。

 I experienced it firsthand and now I want to catch this kind of exception in my own code。

 So if there is a value error， I'm not going to see that crazy trace back anymore。

 I'm instead going to see quote unquote not an integer。

 But what the CS50 library does for you technically is it lets you try again and again and again。

 recall in the past if I dip in cat and dog and bird。

 it's just going keep asking me again and again until I actually give it an int So that kind of implies that we really need a loop inside of this function。

 and the easiest way to do something forever is to loop while true just like in C but a capital T in Python。

 and what I'm going to do now is implement a better version of get in here。😡。

Because what's it going to do？It is going to try。 It's going to do this forever。

 It's going to try to get an input， convert it to an in and return it。 And just like break。

Breaks you out of a loop。 Re， Also breaks you out of a loop as well， because once you've returned。

 there's no more need for this function to execute。 So long story short。

 you won't have to write much code like this yourself。

 but this is essentially what the Cs 50 library is doing when it implements the Python version of get in。

 So what happens now， if I run Python of calculator dot pi， and I type in cat。 I get yelled at。

 but I'm prompted again because of the loop。 I type in dog， I'm yelled at， but I'm prompted again。

 I type in bird yelled at， but I'm prompted again。 if I type in one， then I type in two。

 now it proceeds because it tried and succeeded this time as opposed to trying and failing last time。

 And technically， the C 50 library doesn't actually yell at you with like not an integer。

 So technically， if you want to handle the error that is to say catch the exception。

 you can actually just say oh pass and it will just silently try again。 and again。

 So let me go ahead and run this， Python of calculator pi works almost。The same。

 But notice now it works just like the C version。 It doesn't yell at you。

 but it does prompt you again and again and again。 But I'll do one and two。

 And that now is satisfied。 So that then is exceptions which you'll encounter。

 but you yourself won't have to write much code along those lines。 Well， what else can we now do。

 Well， let's revisit something like this for Mario recall whereby we had this twodimensional world with things in the way for Mario like this column of three bricks。

 Let me actually play around now for a moment with some loops just to see how there's different ways that might actually resonate with you just in terms of the simplicity of some of these things。

 let me go ahead and create a program called Mario do pi and suppose that I want to print a column of three bricks kind of doesn't get any easier than this in Python。

 So for I in range3 just go ahead and print out a single hash done。

 like that then is what we took took us more lines of code in the past。

 But if I run Mario that there gets the job done。 I could change the eye to an underscore。

 but it's not bad。To remind myself that I is what's really doing my counting。 Well。

 what else could we do beyond this。 Well， recall that in the world of Mario。

 We prompted the user actually for a specific height。 We didn't just always hard code 3。

 So I could actually do something like this。 Let me actually open up from today's code that I came with in advance。

 and pull up this C version of Mario。 So this was from some time ago in week one。

 And this is how we implemented a loop that ensures that we get a positive integer from the user by just doing while and is not positive。

 And then we use this for loop to actually print out that many hashes。 Now， in Python。

 it's actually gonna be pretty similar， except for the fact that in Python， there is no dowhile loop。

 But recall that a do while loop was useful because it means you can get the user to try something and then maybe try again。

 maybe try again， maybe try again。 So it's really good for user input。 So let's actually do this。

 Let me borrow the C5s library。

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_70.png)

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_71.png)

Get in function just so we don't have to reimple that ourselves again and again。 Let me in Python。

 do this the pythonic way。 In Python， if you want to prompt the user to do something again and again and again。

 potentially you deliberately by convention， induce an infinite loop。

 You just get yourself into an infinite loop。 But the goal is going to be try something。

 try something， try something And as soon as you have what you want， break out of the loop instead。

 So we're like implementing the idea of a do while loop ourselves。

 So I'm going do this N for number equals get int。 and let's ask the user for a height。

 then let's just check if n is greater than0， you know what， break， we've got the value we need。

 And if not， it's just gonna implicitly keep looping again and again and again。 So in Python。

 this is to say super common to deliberately induce an infinite loop and break out of it when you have what you want。

 Allright now I can just do the same kind of code as before for I in range。

 not of rage sometimes I in range。3， but N， now I can go ahead and print out oops， a hash like this。

 If I open my terminal window， it's gonna to work almost the same。

 But now Mario is gonna prompt me for the height。 So I could type in 3 or I could type in4 or I could be uncooperative and type in0 or negative one or even cat and because I'm using the C50 library cat is ignored。

 because I'm using my while loop and breaking out of it only when n is positive。

 I'm also ignoring the0 and the negative one。 So again。

 this would be a pythonic way of implementing this particular idea。

 if I want to maybe enhance this a bit further， let me propose that for instance。

 we consider something like the two dimensional version of the horizontal version of this instead。

 So recall that some time ago， we print it out like four question marks in the sky that might have looked a little something like this。

 Now the。😊，Me way to do this would be as follows。 Let me close my C code。

 let me clear my terminal and let me just delete my old Mario version here。

 and let's just do this for I in range of4 let's go ahead and print out a question mark Allright。

 Now I'm gonna to run Python of Mario do I enter and it's still a column instead of a row。

 but what's the fix here， perhaps。😡，What's the p here？Yeah。

 we can use that named parameter and say end equals quote unquote to just suppress the default backslash and。

 but let's give ourselves one at the very end of the loop just to move the cursor correctly。

 So now if we run python of myd now it looks like what it might have in the sky here。

 But it turns out Python has some neat features to more syntactic sugar。

 if you will for doing things a little more easily。 It turns out in python， you could also do this。

 you could just say print quote unquote question mark times4 And just like plus means concatenation。

 star here means really multiply the string by itself that many times。

 So sort of automatically concatenate it with itself。 So if I run Python of myd up this two work。

 So again， just some features of python that make it a little more pleasant to use So you don't always have to like slog through implementing a loop or something along those lines。

 Well， what about something more twodimensional like in the world of this brick here。 Well。

 in the context of this sort of grid of bricks， we might do something like this。😊，In V S code。

 Let me go back to Mario pi。 and let me do a three by three grid for that block like we did in week1。

 So for I in range of three， I can nest loops just like in C 4J in range of three。

 I can then print out a hash here。 And then let's leave this alone。

 even though it's not quite right yet， let's do Python of Mario pi。 Okay。

 it's like 9 bricks all in a column， which so your mind might wander to the end parameter again。

 So yeah， let's fix this end equals unqu， but at the end of that loop。

 let's just print out a new line。 So this logically is the same as it was in C。 But in this case。

 I'm now doing it in Python just a little more easily without i plus plus without a conditional。

 I'm just relying on this 4 I in syntax using range。 I can tighten this up further， frankly。

 if I already have the outer loop， I could do something like this。

 I could print out a single hash times 3。 And now if I run Python of Mario like that works。

So I can combine these ideas in interesting ways as well。

 The goal is simply to sege you with some of these building blocks。 Allright。

 how about code that was maybe a little more logical in nature， Well， in Python。

 we indeed have some other features as well， namely like lists and lists are denoted by those square brackets。

 Reminiscent of the world of arrays but in Python， what's really nice about lists is that their memory is automatically handled for you。

 In array is about having values contiguously in memory in Python a list is more like a linked list like you can it will allocate memory for you and grow and shrink these things and you do not have to know about pointers。

 you do not have to know about nodes， you do not have to implement linked lists yourself。

 you just get list as a data type in Python itself here， for instance。

 in some of the documentation for lists specifically and in particular。

 lists also like strings or stirs have methods， functions that come with them that just make it easy to do certain things。

 So for instance， if I want to。😊。

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_73.png)

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_74.png)

Maybe do something like taking averages of scores like we did some time ago。

 We can do that using a combination of lists and the function called Lang。

 which I alluded to earlier， which will tell you the length of a list。 Now， how might we do this。

 Well， if we read the documentation for L。 It turns out there's other functions there too that might be helpful。

 So let me go back to V code here。 Let me close Mario do pi。

 and let me open a file called scores pi reminiscent of something we did weeks ago， too。

 let me go ahead and just for demonstrations， sake。

 give me myself a variable called scores that has my three test scores or what not from weeks ago。

 So I'm using square brackets， not curly braces as and see。

 this is a linked list or a list in Python。 And let me get like the average of these values。

 Well I could do this average equals And it turns out in Python。

 you just get a lot of functionality for free。 And those functions sometimes take not single arguments but lists as their arguments。

 So， for instance， I can use Pythons built in some function and pass in those scores。

 I can then divide that。😊，By the length of the scores list as well。

 So length of a list just tells you how many things are in it。

 So this is like doing magically 72 plus 73 plus 33 all divided by3 in total。

 if I want to now do the math out， I can print the result。 So I can print out using an F string。

 and maybe like some prefixed text here。 Let's print out that average here。

 So let me do Python of scores pi enter。 and there is the average slightly imprecisely。

 but at that point， I'm not doing so well anyway。 So that's fine。 So at this point。

 we've seen that we have sort of more functionality than C。

 like and see how would we have computed the average weeks ago。 I mean。

 we literally created a variable。 We then had a loop。 we iterated over the array。

 we added things together。 There was just so much more work。

 It's nice when you have a language that comes with functions among them L among them some that just does more of this for you。

 So suppose you actually want to get the scores from the user。We C we used an array and in C。

 we used get int。 we can do something a little similar here。

 Let me propose that instead of hard coding those three values。 let me do this from Cs 50。

 import get int。 Now let me give myself an empty list by just saying scores equals open bracket closed bracket。

 And unlike C where you just can't do this。 you can't say give me an array。

 and I'll figure out the length later。 unless you resort to pointers and memory management or the like in Python。

 you can absolutely give yourself an initially empty list Now let's do this for I in range of three。

 let's prompt the human 43s test scores。 So the first score will be the return value of get int prompting the user for their score。

 And now if I want to add this score to that otherwise empty list。

 here's where methods come into play functions that come with objects like lists。

 I can do scores plural because that's the name of my variable from line 3 dot append and I can append that score。

So if we read the documentation for lists in Python， you'll see that lists come with a function。

 a method called append， which literally just tax a value onto the end， tax a value onto the end。

 like all of that annoying code， we would have written in C to like iterate with pointer in pointer and pointer to the end of the list append it malloc a new node Python does all of that for us。

 And so once you've done that now I can do something similar to before the average equals the sum of those scores divided by the length of that list of scores and I can again print out with an F string the average value in that variable like this。

 So again， you just have more building blocks at your disposal when it comes to something like this。

 you can also do this so you've seen other syntax， it turns out that instead of doing scores append you could also do this。

 you could concatenate scores with itself by adding two lists together like this。

 This looks a little。But on the left is my variable scores。 On the right here。

 I I am taking whatever is in that list， and I'm adding the current score by adding it to its own list。

 And this will update the value as we go。 But it does， in fact， change the value of score。

 as opposed to app pending to the initial list。Alright， how about some other building blocks here。

 Let me propose this。 Let me let me close out scores dot Pi。

 Let me open up a file called phonebook dot Pi to reminiscent of what we did weeks ago in C。

 And let me give myself a list of names。 We won't bother with numbers just yet。

 Let's just play with list for another moment。 So here's a variable called names。

 It has maybe three names in it。 maybe Carter and David and John Har as in past weeks。

 And now let me go ahead and ask the user。To input a name because this is gonna be like a phone book。

 I want to ask the user for a name and then look up that person's name in the phone book。

 even though I'm not bothering by having any phone numbers just yet。

 How could I search for linear search someone's name。 Well， in Python。

 I could do this for name rather for N in names If the current name equals what the human typed in。

 then go ahead and print out found。 then break out of this loop。 Otherwise。

 we'll print out not found at the bottom。 Allright， so let's try this。 Python of phone book dot I。

 Let's search for。 maybe Carter。 That's easy。 He's a beginning。 Oh Well， he was found。

 but then I printed not found。 So that's not quite what I want。 How about David D V I D。Found。

 not found。 All right， not very correct。 How about this， Let's search for Eli， not in the list。 Okay。

 so at least someone noting in the list is working， but logically for Carter for David and even John。

 why are we seeing found and then not found。W is it not found， yeah。Okay。

 I don't have seem to have indented the print。 but let me to try this。

 If I just go with the elses here。 Let me go up here and indent this and say else。

 I'm not sure logically this is what we want。 because what I think this is gonna do if I search for maybe Carter。

 Okay， that worked。 So it's partially fix the problem。 But let me try searching for maybe David。

 Now we're sort of the opposite problem， not found found。 why， Well。

 I don't think we want to immediately conclude that someone's not found just because they don't equal the current name in the list。

 So it turns out we could fix this in a couple of different ways。

 but there's kind of a neat features of Python in Python。 even four loops can have an else clause。

 And this is weird。 but the way this works is as follows in Python。 if you break out of a loop。

 that's it for the for loop。If though you get all the way through the list that you're looping over and you never once call line 8。

 you never break out of the loop。 Python is smart enough to realize， okay。

 you just went through lines 5 through 8， you never actually logically called break。

 Here's an else clause to be associated with it。 semantically， this is weird。

 We've only ever seen if and else associated with each other but four loops in Python actually can have else as well。

 And in this case now， if I do Python a phone book do pi type in Carter。 now we get only one answer。

 If I do it again and type in David now we get only one answer。

 do it again with John now we get only one answer， do it with Eli now we get only one answer。

 So again， you just get a few more tools in your toolkit when it comes to a language like Python that might very well make solving problems。

 a little more pleasant。 But this is kind of stupid in Python。 This is correct。

 but it's not well designed because I don't need to iterate over lists like this so pedantically like we've been doing for weeks in C。

 I can actually this up。 and I can just do this。 I can get rid of。

loop and I can say if name in names then print out quote unquote found like that's it in Python。

 If you want Python to search a whole list of values for you， just let Python do the work。

 and you can literally just say if the name that the human inputted is in names。

 which is this list here。 Python will use linear search for you。

 search automatically from left to right， presumably looking for the value and if it doesn't find it。

 then in only then will this else clause execute instead。 So again。

 Python is just starting to save us some time， because this too will find Carter。

 but it will not find， for instance， Eli Allright， so we get that functionality for free。

 But what more can we perhaps do here， Well， it turns out that Python has yet other features we might want to explore namely dictionary。

 shortened dead diic and a dictionary in Python is just like it was in C and really in computer science in general。

 dictionary was an abstract data type and it's a collection of key value pair。

It looks a little something like this。 If in C， if in Python。 if in any language。

 you want to associate something with something like a name with a number。

 you had to in problem set5， implement the darn thing yourself by implementing an entire spell checker with an array and linked list to sort of store all of those words in your dictionary in Python。

 as we saw earlier， you can use a set or you can use more simply a dictionary that implements for you all of problem sets five's ideas。

 but Python does the heavy lifting for you in Python is essentially a hash table。

 a collection of key value pairs。 So what does this mean for me in Python。

 It means that I can do some pretty handy things pretty easily。 So for instance。

 let me go back here to V S code and let me change my phone book altogether together to be this。

 Let me give myself a list of dictionaries。 So people is now gonna be a global list and I'm going demarcate it here with。

Open square bracket and closed square bracket。 And just to be nice in the entiredy。

 I'm going to have these people no longer just be Carter and David and John。

 as in the previous example。 But I want each of the elements of this list to be a key value pair。

 like a name and a number。 So how can I do this in Python， you can use this syntax。 And this is。

 I think the last of the weird looking syntax today， you can define a dictionary。

That is something like this by using two curly braces like this。 And inside of your curly braces。

 you get to invent the name the keys and the values。 So if you want one key to be the person's name。

 you can do quote unquote name and then quote unquote Carterter if you want another key to be number you can do quote unquote number and then quote unquote something like last time16。

1，74，95，1000， for instance， for Carterter's number there。

 and collectively everything here online too represents a dictionary。 it's as though on a chalkboard。

 I row down name Carterter number plus 161，7，4951000 row by row by row in this table。

 This is simply the code equivalent thereof if you want to be really nitpic key or tidy。

 you could style your code to look like this， which makes it a little more clear perhaps as to what's going on it's just starting to add a lot of white space to the screen。

 but it's just a collection of key value pairs again akin to a two column table like this。

undo the white space just to kind of tighten things up because I want to cram two other people in here。

 So I'm gonna go ahead and do another set of curly braces with quote unquote name And David。

 quote unquote number and will have the same number， So plus 1，6，1，7，4，9，5，1000。 And then lastly。

 let's do another set of curly braces for name of say， John。

 and John Harvard's number unquote number will be plus 1 plus 1 let's say9，4，94，6 a 2，7。

50 is always John Harvard's number。 And then by convention。

 you typically and even this element with a comma， but it's not strictly necessary syntactically。

 but stylistically that's often added for you。 So what is people。

 people is now a list of dictionaries， a list of dictionary。

 So what does that mean It means I can now do code like this。

 I can prompt the user with the input function for someone's name if the goal now is to look up that person's number。

 How can I look up。numberumber well， for each person in the list of people。

 let's go ahead and do this。 If the current person's name equals equals whatever name the human typed in。

 then get that person's number by going into that person and doing quote unquote。

 number and then go ahead and print out something like this F string found that person's number。

 And then since we found them， let's just break out altogether。

 And if we get through that whole thing， let's just at the very end， print out not found。😡。

So what's weird here。 If I focus on this code here， this syntax obviously is new。

 The square brackets， though， just means hey， Python here comes a list。 Hey， Python。

 that's it for the list。 inside of this list are three dictionaries， the curly braces mean， Hey。

 Python here comes a dictionary。 Hey， Python， that's it for the dictionary。

 Each of these dictionaries has two key value pairs， name and its value number and its value。

 So you can kind of think of each of these lines as being like a Cstruct like with type def instruct。

 but I don't have to decide in advance what the keys and the values are going be。

 I can just on the fly， create a dictionary like this。 again。

 reminiscent of this kind of chalkboard design。 Allright， so what am I actually doing in code。

 a dictionary in Python lets you index into it's similar to an array with numbers in C。 So in C。

 this is a little bit different in C， you might have been in the habit of doing person dot name。

 but because it's a dictionary， the syntax and Python is you actually use square。

Brackets with strings as being inside the square brackets rather than numbers。

 But all this is now doing is it's creating a variable on line 11。

 setting that number equal to that same person's number。 why because we're inside of this loop。

 I'm iterating over each person one at a time。 And that's what for， that's what in does。

 it assigns the person variable to this dictionary。 then this dictionary。

 then this dictionary automatically for me， no need for I and i plus plus and all of that。

 So this is just saying if the current person's name equals the name we're looking for。

 get a variable called number and assign it that person's number and then print out that person's number。

 So whereas last time we were just printing found and not found。

 Now I'm gonna to print an actual number。 So if I run Python a phone book and I search for Carter there then is his number。

 if I run Python a phone book do I run type in John there then is John's number and if I search for someone who's not there。

 I instead just get not found。What's interesting and compelling about dictionaries is they're kind of known as like the Swiss army knives of data structures and programming。

 because you can just use them in so many interesting， clever ways。

 Like if you ever want to associate something with something else。 like a dictionary is your friend。

 And you no longer have to write dozens of lines of code as in P at 5。

 you can write single lines of code to achieve this same idea。 So for instance。

 if I too want to tighten this up， I actually don't need this loop altogether and even better version of this code would be this。

 I don't need this variable technically， even though this will look a little uglier。

 notice that I'm only creating a variable called number because I want to set it equal to this person's number。

 but strictly speaking， anytime you've declared a variable and then use it the next line。

 you don't really need it， So I could do this。 I could get rid of that line。

 And instead of printing number in my curly braces。

 I could actually do person square brackets and you might be inclined to do this。

 but this is gonna confuse Python because you're mixing double quotes on the inside。In the outside。

 But you can use single quotes here compellingly。 So you don't have to do it this way。

 But this is just to show you syntactically， you can put most anything you want in these curly braces so long as you don't confuse Python by using。

The same syntax。 But let me do one other thing here。 This is even more powerful。

 Let me propose that if all you're storing is names and numbers， names and numbers。

 I can actually simplify this dictionary significantly。 Let me actually redeccl this people。

 data structure， to be not a list of dictionaries。 But how about just one big dictionary。

 Because if I'm only associatesociating names with numbers。

 I don't technically need to create special keys called name and number。

 Why don't I just associate Carter with his number plus 1，6，1，7，4，9，5，1000。

 Why don't I just associate， quote unquote， David with his number plus 1，6，1，7，4，9，5，1000。

 And then lastly， let's just associate John with his number plus 1，9，4，9，9，4，9，4，6，8，2，7，5，0。😊。

And that， too， would work。 But notice that I'm gonna get rid of my list of people。

 And instead just have one dictionary of people。 The downside of which is that you can only have one key。

 one value， one key， one value， you can't have a name key and a number key and an email key and an address key and any number of other pieces of data that might be compelling。

 But if you've only got key value pairs like this， we can tighten up this code significantly so that now down here。

 I can actually do this。 if the name I'm looking for is somewhere in that people dictionary then go ahead and get the person's number by going into the people dictionary indexing into it at that person's name and then printing out found。

 for instance。That here number， making this an F string else。

 you can go ahead and print out not found in this case here。 So again。

 the difference is that the previous version created a list of dictionaries。

 And I very manually methodically iterated over it， looking for the person。

 But what's nice again about dictionaries is that Python gives you a lot of support for just looking into them easily。

 And this syntax， just like you can use it for lists， you can use it for dictionaries as well。

 And Python will look for that name among the keys in the dictionary And if it finds it。

 you use this syntax to get at that person's number。😊，Okay， a lot all at once。

 But are there any questions on this here， syntax。 We'll then introduce a couple final features with a final flourish。

Yes。In this case， I do not need to use brake because I don't have any loop involved。

 So brake is only used as we've seen it in the context of like looping over something when you want to terminate the loop early。

 But here， Python is doing the searching for you。 So Python' is taking care of that automatically。

Allright， just a couple final features so that you have a couple of more building blocks。

 Here is the documentation for dictionaries themselves in case you want to poke around as to what more you can do with them。

 But it turns out that there are other libraries that come with Python。

 not even third party and one of them is thes the cis library whereby you have system related functionality and here's its official documentation for instance。

 But what this means is that certain functionality that was just immediately available in C is sometimes tucked away now into libraries in Python。

 So for instance， let me go over to BScode here。 and let me just create a program called dot pi。

 which is reminiscent of an old C program that just greets the user using command line arguments。

 but in C recall that we got access to command line arguments with main and in Argy and Argv but none of those have we seen it all today。

 And in fact， main itself is no longer required。 So if you want to do command line arguments in Python we actually do this from the ciss library。

😡，You can import something called Rrgv。 So Argv still exists is just tucked away inside of this library。

 otherwise known as a module。 And I can then do this if the length of Rrgv for instance。

 does not equal to。 Well， then we're gonna go ahead and do what we did rather， let's do this。

 If the length of Rrgv does equal to we're gonna go ahead and do what we did a couple of weeks ago。

 whereby I'm gonna print out hellello comma， and then Rrgv bracket1， for instance。

 So whatever is in location one of that list。 else， if the length of Rrgv is not equal to2。

 that is the human did not type two words at the prompt。

 let's go ahead and print out hello world by default。 So we did the exact same thing in C。

 the only difference here is that this now is how you get access to Rrgv。

 So let me run this Python of Greek pi and hit enter Ho world is all I get。

 And actually I got an extra line break because out of habit， I included backslash n。

 but I don't need that in Python。 So let me fix that Python of Greek top pi hello。World。

But if I do Python of Greek dot pi D V I D， now notice that Rrgv equals2。

 if I instead do something like Carter Rrgv now equals 2， but there is a difference。 technically。

 I'm typing three words at the prompt， three words at the prompt。

 But Rv still only equals2 because the command Python is ignored from Rrgv。

 It's only the name of your profile and the thing you type after it。

 So that's then how we might print out arguments in Python using Rv。 Well。

 what else might we do using some of these here features。

 What it turns out that you can exit from programs using the same cis library。

 So let me close Greek do pi。 Let me open up exit dot pi just for demonstration sake。

 And let's do something like this， Let's import cis And if the length of cis dot Rrg V。

 So here's just another way of doing this And actually。

 I'll do it the same first from cis import Rrg V。 if the length of。Arg V does not equal  to。 Well。

 let's actually yell at the user with something like missing command line argument。

 And then what we can do is exit out of the program entirely using cis do exit。

 which is a function therein。 But notice that exit is a function in cis。 So you know what。

 it's actually more convenient in this case， let's just import all of cis。

 But because that has not given me direct access to Rrgv。

 let me do cis dot Rrgv here and cis dot exit here。 Otherwise， if all is well。

 let's just go ahead and print out something like hello， commas do Rrgv bracket1 close quote。

 and that will print out hello， so and so。 And when I'm ready to exit with a nonze non with a zero exit status。

 I can actually start to specify these things here。 So just like and see。

 if you want to exit from a program with one or two or anything else， you can use do exit。

 And if you want to exit with a0， you can do this here instead。 So we have this。😊，Same capabilities。

 as in C， just accessed a little bit differently。 Let me propose that。 let's see。Let me propose that。

How about this。How about this， If we want to go ahead and create something a little more interactive。

 recall that there was that command a while back， namely Pip。

 whereby I ran Pip install face recognition。 That's one of the examples with which we began。

 And that allows me to install more functionality from a third party into my own code space or my programming environment more generally。

 Well we can have a little fun with this。 In fact， let me go back to B S code here。

 And just like there's a command in Linux called cow say。

 whereby you can get the cow to say something。 you can also use this kind of thing in Python。

 So if I do Pip install cow say， this if it's not installed already。

 we'll install a library called cow say。 And what this means is that if I actually want to code up a program called like mu dot pi。

 I can import the ca say library， and I can do something simple like cow say do cow。

 because there's a function in this library called cow。

 and I can say something like this is C S 50 unquote How do I run this program。

 I can run Python of Mo dot pi。😊，And underwhelming if I increase the size of my terminal window。

 run Python of M dot pi。 we have that same adorable cow as before。

 but I now have programmatic capabilities with which to manipulate it。 And so in fact。

 I could make this program a little more interesting。

 I could do something like name equals rather name equals input。

 What's your name and combine some of today's ideas。 And now I can say not this is CS 50。

 but something like quote unquote， hello comma persons name。

 And now if I increase the size of my terminal， rerun Python of Mu dot pi。

 It's not gonna actually mu or say this is C50， It's gonna say something like hello David and so forth。

 and suffice it to say through other functions， you can do not only counts but dragons and other fancy things too。

 But even in Python 2， can you generate not just aski art but actual art and actual images。

 And the note I thought we'd end on is doing one other library。 I'm gonna go back into Vs code here。

 I'm gonna close mu dot pi， I'm gonna do Pip install Q。😊，code。

 which is the name of a library that I might want to install to generate QR codes automatically and QR codes or these two dimensional barcodes。

 If you want to generate these things yourself， you don't have to go to a website and type in a URL。

 You can actually write this kind of code yourself。 So how might I do this。 Well。

 let me go into a new file called say Q R dot Pi and let me do this Let me go ahead and。

Import this library called Q， R code。 Let me go ahead and create a variable called image or anything else。

 Let me set it equal to this library's Q R code's function called make。 No relationship to C。

 It's just called make because you want to make a Q R code。

 Let me type in maybe the URL of a lecture video here on YouTube。 So like YouTube slash X， V， F， Z。

 J， O，5 P G G0。😊，Quote unquote and then I can go ahead and do image do save because inside of this image variable。

 which is a different data type that this library gave me， doesn't come with Python per se。

 I can save a file like QR do P and G and I can save it in the ping format。

 the portable network graphic。 And so just to be clear。

 what this should hopefully do for me is create a QR code containing that particular URL。

 but not as text， but rather as an actual image that I can send I can post online or in our case generate into my code space and then open。

 And so with all that said， we've seen a bunch of new syntax today， a bunch of new features。

 but the ideas underlying python or exactly the same as they've been in C。

 it's just that you don't have to do nearly as much heavy lifting yourself。 And here， for instance。

 in just three lines of code， can you generate a massive QR code that people can scan as you can in a moment with your phones and actually link to something like a Cs 50 class。

 So let me go ahead。And run Python of Qr。pi seems to have run， let me run code of  Qr。pG。

 which is the file I created， I'll close my terminal window。

 allow you an opportunity to scan this here very CS50 lecture。😡。



![](img/22c0c11fa31af64363e6a5cd04b7fe7c_76.png)

![](img/22c0c11fa31af64363e6a5cd04b7fe7c_77.png)

And。And。Is someone's volume up？There we go， what a perfect ending all right， that was CSs 50。

 we'll see you next time。