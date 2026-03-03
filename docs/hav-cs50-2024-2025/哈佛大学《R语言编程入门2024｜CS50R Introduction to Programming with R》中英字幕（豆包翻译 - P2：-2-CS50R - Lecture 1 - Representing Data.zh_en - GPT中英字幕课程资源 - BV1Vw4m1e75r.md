# 哈佛大学《R语言编程入门2024｜CS50R Introduction to Programming with R》中英字幕（豆包翻译 - P2：-2-CS50R - Lecture 1 - Representing Data.zh_en - GPT中英字幕课程资源 - BV1Vw4m1e75r

。

![](img/a850753e98eeda59c890c2c9b3736f91_1.png)

![](img/a850753e98eeda59c890c2c9b3736f91_2.png)

Well hello one and all and welcome to CSFT's introduction to programming with R。

 My name is Carterzenki， and I'm so excited to embark on this journey to learn this language called R with you。

 Now it's likely that you have never programmed before and if so that's okay but you might be asking what is a programming language actually anyway what turns out your programming language is something that we humans had created to actually talk to computers and have them solve problems for us and you might have heard of lines of code。

 things actually tell computers what to do and you may have heard of programs being lines and lines and lines of code telling computers step by step what it is we want them to do and you might have heard as well there are other languages you could learn like see like Python like R like jascript as you could be asking yourself why would I learn R Well R it turns out is this language built from the ground up to work with data and so if you are interested in data or some of these fields here like data science。

 data visualization research or statistics R could be。😊，A language for you。

 and although this course won't actually teach data science or statistics or the math behind them。

 you will emerge being able to use R for these disciplines Now actually， just recently。

 researchers used R to model how CoVd-19 was spread and this is a visualization built entirely in R to model how Co-19 was spread on a cruise ship you might have also heard of 538。

 these data journalists who actually write articles with data they use R to analyze data to write their articles and share visualizations like this one so we'd actually understand insights from data too。

😡。

![](img/a850753e98eeda59c890c2c9b3736f91_4.png)

![](img/a850753e98eeda59c890c2c9b3736f91_5.png)

So without further ado， let's actually begin by writing our very first R program and to do that we'll be what's called an integrated development environment or an IDE for short Now code at the end of the day is just text and you could use any text editor to write code but it turns out that when you actually want to write lots and lots of code it's helpful to have a tool to do that with and that's what this IDE will be doing for us Now let me introduce you over here to this IDE called R studio Now our studio is an IDE built exclusively and particularly for R and here it is you'll notice off the bat that I have this kind of greater than sign here with a blinking cursor and this indicates what we' going to call the R console It's a place I can actually type R statements and have them run kind of line by line by line It's a great place we to actually execute or to run one line of code at a time so that's actually type our very first line of R。

Our here to create this file called Hello。 R， which will write actual full fledged program。

So to create a file using this console in our studio。

 I can type file do create open parentheses and closed parentheses and then the name of the file I want to create so here I'm going to create in this case hello do R just like that Now notice that hello dot R ends in do R and that is actually very particular you might have heard of files ending in like dotjpg for images or maybe dot csv for data files in R we denote our R programs with this dot capital R here So let me run this R statement here by hitting enter and now I should see well I see true kind of yelling at me right here what this means that this file was created and we'll also see this kind of bracket one here which will have more parent as we go on but it turns out that because R works a lot with data and lists of data it's often handy when you have lots and lots of data to give us an indicator of where in。

That list we are so we'll see this come in handy a bit more later。

 but for now with this list of one value like true just says one for now Well where was this file created Like I claim it was created but where was it created So R studio has this file Exper that I can open on the side here and this file Exper shows me the contents of some particular folder on my computer even if don't know about about computers。

 you probably know about files and folders and so here it seems like I am inside of the users j Harvard folder and inside of that folder R studio and R created for me this file called hello do R Now R studio works by default in a single folder and that folder it turns out is called R working directory if I ask R to create a file for me it will create that file in the working directory or if I ask it to find some data file and read it into my R program it will first。

Search in that working directory for me here。So let's open up this R file and actually write our first R program I type I'll hit this hello。

 R file icon here let me close my file Explorer for now because it's not important at this point。

 but now introduced to this new component of R studio。

 in this case my file editor so as you saw before this R console down here is great for writing single R statement。

 single lines of R code， but this hello。 R file is great for writing more than one line of code。

 tens of lines， hundreds of lines， creating a fullfledged program here。

So I have this blinking cursor， which means I can actually just go ahead and type some text and let's type in some text that will be our very first our program。

 I'll type print， PRI N T followed by an opening parentheses and a closing one and inside those parentheses。

 let me type hello。😊，Coma space， world， just like this， and now I've typed in some text。

 my first line of R code， I can save this file by clicking on this little save icon here or on Mac I could do command U or in Windows I could do controlr S。

 let me hit the saveve button here and now this program is saved on my computer。

 I could run it if I wanted to。Now you may be used to running programs by double clicking on them or finding some icon and clicking on that to open the program and run it。

 but I don't see those icons here and that is intentional。

 This is a program we've made ourselves which will require a different way of running it for us and even if you don't know what how computers you probably know computer speak this language called binary or like ones and zeros and right now we just have PR I and T preheses quotes hello world like that doesn't look like ones and zeros to me so there has to be a way to translate or interpret。

 this R text we've written into ones and zeros， the computer actually understand So R is more than a language it's also an interpreter that takes this text we've written and convert it to the ones and zeros the computer understands。

Now to kick off that process， that interpretation process。

 I can actually click this button over here that says run。

 so let me go down to the console first and let me clear the console so it's very clear what's happening here I'll type Cl L to clear the console and now if I go to this line of code line1 and hit run。

😊，I should see my first R program saying hello to the world over here。

So let's take a step back first though and think about what it is we have just done。 So here in R。

 we have created our very first program and we've done so using something that's called a function。

 Now in languages like R and lots of others too you'll have access to these things called functions and functions let you tell the computer to take some action。

 do something to solve some particular problem In this case our problem was displaying some text and this function that we saw called print helped us do just that。

 So let's go back and show you this program again， they come back to R studio。

 we saw that this function is called print， you can probably guess that yourself here。

 and we know it's a function because I use these parentheses here。

 This is convention in R to de a function by its name。

 followed by parentheses followed by some particular input to that function Now print when R the art developers designed it It doesn't print some predetermined piece of。

Like doesn't always print hellello world， doesn't always print hello to somebody else。 Instead。

 it prints the text that I want it to print。 And so we'll see if we learn proing together that these functions can take inputs and more precisely。

 these inputs are called arguments to the function。

 Theyre inputs that change how the function actually runs。😊。

Now what is it that print did well down below on the console here I see that it printed hello comma world。

 and this is what's known as the side effect of the function， something visual that happened。

 side effects could also be something that happens via audio， something else I see。

 whatever happens as the function is running that is known as its side effect。

 and this is our first program in R so far， but let's pause here and ask what questions we have on R our studio or this first program we just wrote calledHello World。

So a question about why would would use R studio as opposed to VS code Well if you're familiar with VS code。

 you would know that it can work with a variety of languages like Python and C and others R studio though is Taylororm to work with R and as we'll see it later on in the course。

 there's a lot of features of R studio that make working with R much easier。

 particularly with visualizations and plotting so we'll see that later on in the course as well Also question about why would use R instead of Python Well Python tends to be this really big language that can use for lots and lots of things and you think of libraries in Python like NI。

 you can certainly do work like you would do in R with those libraries。

Our studio though is more of a precise tool it's built from the ground up to work with data。

 whereas Python is more of a general tool for something lots of different problems。

 R then comes with some optimizations that make working with data a little more efficiently。

 but in general you could use either Python with Ny or other libraries or R to work with data overall。

Now， a question from Louise。Could you show us how to change the working directory for the console。

 So a great question about actually changing the working directory we saw earlier that our studio default to having some kind of working directory。

 but you could change that if you wanted to in R there is a function dedicated to changing that working directory and I can show you what that looks like over here let me come back to my R studio environment and in particular my console So changing the working directory that only requires one line of R code so I could then clear my console down below here and execute that line of code in the console The function to do so is set WD just like this and then in parentheses you can then type the path or the folder you want to change your working directory So if you do want to do that you can do it using the set WD function here。

😊，Now， we've completed our very first hello world program。

 but oddz are things aren't always going to go as smoothly for you。

 If you're just beginning with programming。 And even if you're more experienced。

 you might encounter these things called bugs or these errors in your code。

 So let me reproduce kind of intentionally here a bug that could happen in my program。 Let's say。

 as I was typing， I didn't type print。 I instead typed print。😊。

Let me save this program here and let me run it to see what happens， I'll hit run。😡，And。

Well now I see down on my console error in print parentthees hello world could not find function print in this case。

 so this error is hopefully telling me like look there is no function called print and hopefully by seeing this I should then actually know well I didn't mean to type print。

 I meant to type print instead so I can go back and fix it and this process that actually going back and fixing our programs is known as debu finding those bugs in our code and getting rid of them by looking through these errors and talking to a colleague or trying to fix them overall so here let me go back and clear my terminal。

 my console down below I'll run this line of our code or run this line of this program here again and I'll see once again hello world。

😊，So this is a pretty good program but I argue we could do a little bit better with it。

 like we don't just have to say hello to everyone， we could try to say hello to a particular user and so our next step here will be to actually asksh the user for their name and then say hello to that particular user now to get user input there is a function and R for that it's not print it's instead called read line so let's use the read line function here。

😡，I'll type READ， read line， this is all one word， and then prenes， open A and closing。

 and it turns out that Read line takes an argument to。

 this argument will then be the prompt it prompts the user with。

 so I'll ask the user what's your name just like this and I'll save the file here。

So let me go down and clear my console。 I'll then run this line of our code。

 and I'll see what's your name。 I could type in this case。 My name is Carter， hit enter。

I see Carter so it's not so much a greeting as much it is just kind of saying my name back to me I think it could still do better than that as well let me clear my console and ideally I want to say something like this。

 I want to say hellello Carter so I could use print again maybe on line2 now I choose to say print and then hello comma Carter and I'll save this file again well now I have not just one line of R code but two and when R goes to interpret this program it will read these lines of code top to bottom left to right executing each function along the way。

😡，But it turns out that this run button over here， it says run。

 but what it really does is it only runs one line of R code at a time。 For example。

 I could run just line1 or I could run just line2， but what we have here is really a fullfledged program it's more than one line of code it's two so to run the entire program。

 I need to use a different approach， a different button in this case and that button is this source button up top here source in this case means to run the entire source file here So me go ahead and source and let me say what's my name。

 my name is Carter and I see Ho Carter。But there might still be a bug in this program。

 let's try it one more time， let me clear the console， I'll source again。

 and what if my name was like Mario from the Nintendo universe， I could type， well， my name is Mario。

Hello， Carter。 Okay， let's try it again。 I'll do source and I'll do maybe my name is Princess Peach。

 So Princess Peach here and。Well's still hellello Carterter so it seems to me like we need to do something more dynamic than just printing out Hello Carter。

 we need to actually print what the user has given us at the console so for that we'll actually need this new concept in programming called a return value functionss don't just have arguments and side effects they also have return values and in this case。

 read line will return to us as it return value the user input you could think of it a bit like a metaphor of asking your friend to go out and ask somebody for their name and they might write it down and turn it back to you the programmer so you can use it later on in your code that's kind of what return values are in this case。

But if I have a return value， I'm going to need some place to store it。

 some place to reuse it later on in my code， and for that we'll need something called a variable or an object。

 a variable is some name for a value that could change。

 so let's see how we could use both return values and object in R to make this program more dynamic。

😡，Let me go to line1 here and let me try to give this return value of Readline a name I could reuse later on Well if the user types in Carter。

 I want to refer to that value via sum name and maybe the right name it's just simply name so I'll type name here and now if I want to store the return value of Readline that is whatever the user typed in inside this object called name I could use this syntax。

These particular characters here， the less than sign and a dash。

 and notice if we read this kind of right to left first Read line will run as a function。

 it will prompt the user for their input， the user will type that input in and then read line will come back to us and give us back whatever the value is that the user typed in。

 and then these lines of code over here， name space less than this dash here will store it underneath this name called name。

This arrow， this leftward arrow is called the assignment operator。

 we're assigning whatever return value from Readline to this new object called name。

So let me just for now get rid of this line too and just focus on this particular piece right now let me source this file and now let me say my name is Mario I'll hit enter and I see nothing yet because there's no print but now if I open up this new pane in our studio let me go ahead and go to my environment pane I'll actually see what the value is for this object we created called name so it seems like our studio is telling me that I have this object called name and its value now is Mario。

 this is part of our environment， the environment is the place we actually store our object while our program is running so we can then reuse them later on in our code。

So I've kind of captured this user input and stored it in this object called name。

 but let's see how we could use it now。'll come back to our studio。

And let me go back to line two and let me now print in this case。

 let me print hello comma name just like this， I'll kind of close my environment over here。

 and now let me source this particular file， I'll type Mario， it's my name and now enter。

I see hello name， so this isn't exactly what we wanted。

 I actually print out literally hello common name， so I think we'll need to find some other solution here。

 we solved one problem which was getting the user input and storing it somewhere。

 but I mean how do we reuse that later on？If I'm being observant。

 I might notice that what I'm really trying to do is combine some pieces of text like this text here is hello comma space and the text I'm trying to combine is whatever the user typed in or has whatever is being stored in this name object I have over here。

 So I'm trying to combine hello comma space。 and this text from the user Mario。

 Now this is a common problem in programming， trying to combine pieces of text。

 so common that it actually has its own particular name。

 This is called string concatenation where concatenation means combining together。

 these various pieces of text or these strings。 So let's break it down。 and here。

 of course we have the very first part of our greeting。

 This is some piece of text or from here on out called a string a string because it's kind of characters strung together into one piece of text strings begin and end with these double quotes here。

 So I have hello comma space。😊。

![](img/a850753e98eeda59c890c2c9b3736f91_7.png)

And that is one particular string， but then the user comes in and they type in their own string。

 let's say like Carter， and now my task is to combine these together into a single string and print that back out to the user。

 so my goal here is to effectively this turn these two separate strings into one individual string。

Now R handling enough comes with a function to do just this。 So let's explore that function here。

 This function is actually called paste paste is in PA S T E and paste allows me to concatenate various strings so let's try this one here if I want to use paste。

 I use it the same way I would any other function。 I could use the function name and then open and closing parentheses and then paste will take as input any number of strings I want to concatenate or paste together in this case。

 So let's say the first string we said is hello comma space Now the next string is something new it's actually going to be whatever is stored in this name object over here。



![](img/a850753e98eeda59c890c2c9b3736f91_9.png)

So if I want to provide another input to paste， I should actually separate it now with a comma。

 so after the first input to paste， the first argument。

 I'll then give it a second input or a second argument and this one will be literally name in this case。

 this object restored that has that value the user themselves typed in。

And now paste its return value will be the combined version of these two strings， so let's try it。

 maybe I'll store the return value inside its own object called greeting。

 I'll use the left arrow it's assignment operator to store the return value of paste in this object called greeting and then down in print here。

 I won't print hellello name literally Altlin's dead print。

 whatever is stored in the object called greeting。So as I run this， let me open up my environment。

 we can see how these values change over time。 let me go ahead and click source here。

 my name in this case is Carter， I'll hit enter。😊，And I see hellello Carter。

 so if I go back to my environment here， I see I not only have this object called name。

 storing Carter， I also have this object called greeting。

 storing the concatenated versions of in this case， the string hello comma space。

 and then the string Carter itself。😊，But if you're being particularly observant here。

What do you notice as a bug in this program， Let me ask our audience here。

What do you notice as a bug in this program？There are two spaces。Yeah， there are two spaces。

 So I only wanted one space， but it seems I have somehow gotten two。

 Like greeting here has hello comma space space Carter。 So why is that， Well。

 I could spend a lot of time kind of bang my head wondering why is this not working or I could look at something called documentation。

 So programmers when they write functions like paste。

 they also write documentation that tells me exactly how to use paste and what effective output of paste might be So let's look then at the documentation for paste。

 I can actually access documentation if I use this special character in R called the question mark。

 And if you want to remember this， I trying to think of like just being confused。 Like what do I do。

 The question mark is that symbol。 Then I follow with the function name in this case paste。😊。

So now over in the right hand side， let me make this bigger for us over here。

 I'll actually see the documentation for paste， whoever created this function called paste helpfully wrote this documentation to guide me on how to use paste itself So I'll see up top the goal of paste is to concatenate strings like we just talked about that much is pretty obvious but down below I think is the helpful part。

 This down below will tell me what kinds of inputs。

 paste could potentially take and I'll see the same thing we saw before Pae followed some parentheses with various what we'll call parameters here So these are still inputs to paste。

 but they're potential inputs， and because they're potential ones well call them parameters argumentsguments are the actual values we pass to paste parameters are the potential ones here。

😊。

![](img/a850753e98eeda59c890c2c9b3736f91_11.png)

Now I see if I go down here somet dot dots， these dot dot dots mean that paste could take really any particular number of arguments。

 that could be any number of strings I want to concatenate in this case I then have over here though this named parameter called Sep and it says Sep equals quote unquote with a space in the middle Now this is what's called a named parameter it has a given name because has a special use case in this case of paste Now the equal sign means the default value for this parameter is going to be this value here。

 the quote space unquote so it seems like this parameter called sep might be what's making this extra space actually happen in my output and if I go back to the documentation over here let me scroll down a little bit so we can see I'll go down the arguments and you can see that Sep is in fact a character string to separate the term。

Ys。So my job now is to think about what would I change the value of SP to be to remove that extra space Well I can go back to my program and ideally I don't want anything any character to default。

 separate the strings， I just want to have them put together with no spaces in between so to use this named parameter called SP I can then have another input to paste I could follow it with a comma just like this and then use that named parameter SP in this case。

 and set it equal to some new kind of value in this case。

 quote unquote or really no spaces at all So let's try this now I'll clear my console I'll run source and I'll type Carterter again。



![](img/a850753e98eeda59c890c2c9b3736f91_13.png)

And now I'll see hello， comma space， only one space， Carter。Now if you're like me。

 you might think I'm going to often want to concatenate strings that don't have any spaces in between them and it's gonna to be a lot of typing to always type comma SP equals quote unquote if you're writing many lines of code。

 you don't want to do this over and over and over again and in fact。

 some R users got tired of just this and they wrote their own function where the default is SP equals unquote nothing this function is called simply paste0 paste0 zero means there's nothing between these concatenated strings。

😡，I now don't need to supply the input S because the default will always be no particular space at all now I'll rerun this program source and say Carter and I'll get that same output Now one other way to do this because there's always more than one way to do something is I could maybe just omit the space altogether like I could say hello comma and make that my string and I could then assume that paste will go ahead and actually add the space in for me。

 I could run source just like this type in Carter and now I'll see hello Carter again completing our program here。



![](img/a850753e98eeda59c890c2c9b3736f91_15.png)

So let me pause and ask what questions we have on pacee， during combinationtonnation。

 or our program so far。So what's the difference between the pace function and the cap function。

 because I think both of them are used for string connation？



![](img/a850753e98eeda59c890c2c9b3736f91_17.png)

Yeah， good。 So if you are familiar familiar with R。

 you might have also heard of this function called cat and cat itself stands for concatenation Cat and paste have two similar use cases they both involve combining strings together。

 but they have slightly different outputs so cat has the side effect of printing whatever you've concatenated to the console paste on the other hand does not paste only returns to you kind of silently the concatenated version therein and you can then use that later on in your code Cat I believe does not actually return to you the result just kind of prints it to the screen as a side effect so two very different use cases but the same kind of goal here。

😊，Allright， let's continue and let's keep improving our program here So one thing you might notice is that I have this object called greeting and I'm just on the next line using that very same object and this seems just a little bit redundant because I'm just storing this value from paste in greeting and immediately giving it back to this function called print Well to have this same result and actually reduce some number of lines of code。

 I could do the following I could actually remove the idea of storing the result of paste in any given object and I could simply run paste and immediately pass the value or the return value from paste as the input to print。

Now this is arguably the most complicated line of code we've seen so far so let's break it down just a little bit this what we're doing right here is known as function composition I'm making one function run and then immediately passing the output of that function as input to the next so this is our line of R code and we said before that R runs lines of code kind of line by line top to bottom left to right and that's mostly true but in this case we see there's more than one function to run or action to take on this particular line of code so what is R to do。

Well， what R will always do is look first for the function is innermost in the parentheses。

 so in this case that is the paste zero function， this concateatorator combining hello comma space and the name over here。

😊，Now what this will do is make the return value of hello comma let's say space Carter and then pass that immediately as input into print just like this and once that's done print can then do its job and of course just print out something like hellello Carter so always think about the innermost function running first and passing its return value as the input to the next innermost function and so on and so forth so let's go ahead and try this out I'll come back to our studio here and here I have paste as opposed to paste zero but kind of the same thing as we saw before。

 let me go ahead and source here I'll type Carter and we'll see that I get the very same result without storing in this case in additional object。

😊，Now an extension of this might be the following， I could take read line。

 I could take read line and notice how it's just simply storing the value and name。

 which I immediately pass as input to paste， I could do this。

 I could take read line and put this right there， and now I have three functions nested inside of each other。

😊，But let me actually ask you why might this not be a good idea。

 let's think about other people who might read this code or think about working together on projects like why might I not want to do this or go this far with the design of my code here？



![](img/a850753e98eeda59c890c2c9b3736f91_19.png)

I think because it doesn't explain the code perfectly to the user。



![](img/a850753e98eeda59c890c2c9b3736f91_21.png)

Yeah， it's kind of hard to read Like if I saw this line of code here。

 I would have to kind of think to myself， okay， which function is happening first。

 Well it looks like it might be readline and then what happens next， Okay Pae happens next。

 So it's a lot for me to think of as I'm reading this program And even though it is shorter。

 I would say it's not necessarily better。 So these are questions about the design of programs。

 which way to write the code is better。 we have the same result， So they're both correct。

 but there are still different ways to design it and tradeoffs to consider in terms of readability as well。

😊，So let's come back and let's try to fix up this program a little bit。

 I would argue that it's probably cleaner。 if we instead have readline on a separate line of code。

 I'll put this first on line1， and I'll go back to storing this object called name and I'll pass it in as input to paste here just like this Now we just talked about the idea of making our code more readable and it turns out that R comes with a feature that can let me do just that。

 I can actually leave myself some notes to self called comments that will help me understand my code using the English language So if I want to write a comment or a note to myself in my code。

 I can do sotyping this hashtag here followed by a space and I can then type the comment I want to type I could say maybe this line asks user this line asks user。

For ask is your first name just like this and the next line。

 Well what does this line of code do This line of code says hello to user just like that Now comments by convention go on the line above the line of code they are talking about。

 So in this case I know this comment on line1 refers to the code on line 2 and this comment on line4 refers to the line of code on line 5。

 but comments are very helpful when you actually are working on a larger project。

 you come back later， don't know what you did。 comments can then help you understand exactly what to do and what you had done prior as well。

So this was our hello world program we said hello to the world。

 we said hello to some users let's get working with some data now and in one case we might want to work with data in terms of let's say counting votes for an election so let's go ahead and try to simulate an election between some fictional character from the Nintendo universe in this case Mario Peach and Bowser so to create this new program I go to my console again and I'll type file do create and in this case I want to count some votes so I'll call this program count do R just like this I'll hit enter and I'll see that this file was created so now if I open up open up my window over here and go to files I should now see that count R is available to me as a file to write this program in I'll open up count R and now I have a blank slate of a program to write so we have three candidates to keep track of votes for Mario Peach and Bowser。

So let's let the user actually type in those votes and return to them or print out the total number of votes that happened in this election。

 so maybe I will ask the user using Readline to enter votes for Mario just like this。

 and I'll also ask the user to enter votes for Peach， just like this Princess Peach。

 and I'll also use Readline to ask the user to enter votes for Bowser just like this。

Now it's likely I want to use whatever the user types in later on in my code。

 so why don't I store the return value of readline in an object I could reuse later on maybe I'll call this one Mario and this one peach and this one let's go for Bowser just like this So I'll save it and again the goal was to kind of add up these total number of votes Well maybe I'll make a new object called total to store the total number of votes and I'll have something that will assign that total number here。

Well it turns out that to actually add data together I can use in R this plus sign。

 this plus operator， so I'll say Mario plus peach plus Bowser。

 and that should return to me the total number of votes the user actually entered in the console and if I want to then print that back out to the user。

 I could use print and paste again， so I'll use print paste and then total votes。

 no space paste will actually add it for me and then total itself down below here。

So a few things we've seen before and a few new things。 What's new is this arithmetic。

 We've seen now we just used this plus operator to add together some numbers and R has more than just the plus operator has several others as well。

 It has additions we just saw with a plus sign subtraction with this minus sign or a dash multiplication with this star or asterisk operator and division just like this with the forward slash here。

 There are other operators too that we'll talk about later on in the course， but for now。

 these four will help you do some basic arithmetic they can help us solve some really interesting problems in this case。

 So let's come back let's run our program。 I'll come back to our studio and I think this should work。

 I'll go ahead and run source and I'll enter votes in this case for Mario。

 maybe y'll say Mario has 100 votes and Peach has 150 and Bowser has 120 and now I should see the total number of votes that were cast in。



![](img/a850753e98eeda59c890c2c9b3736f91_23.png)

![](img/a850753e98eeda59c890c2c9b3736f91_24.png)

This election， I'll hit enter。And I'll see one other error that says error in Mario plus Pach。

 nonnumeric argument to binary operator。The other error element was easier to understand this one's less easy。

 so at least it tells me what the error happened it happened in Mario plus peach so it seems like maybe on line5 here when I tried to add the user's input for Mario to the user's input for peach and it says the reason a nonnumeric argument to the binary operator so the binary operator I'll tell you is this plus sign here but the nonnumeric argument。

 it seems like it's telling us that Mario and peach those aren't numbers at all。

 so let's take a peek at our environment where we stored those actual object let me take a peak over here and what will we see if I go to environment maybe remove this down below here I see some old some old things here like reading and name that I didn't get rid of before but I also see Bser Mario peach and what do you notice？

Well， it seems like before we had， let's say greeting that was a character string。

 and we knew it was a character string because I had quotes around it， right？

But we see the same thing now for Bowser and for Mario and for Peach。

 which implies to me that these are still character strings。

 they're not so much numbers Now I think R is now telling me that it needs numbers to be able to add these things together。

 it can't add a character 120 with the character 100 these need to be actual numbers。

So let's see what we can do about that let's come back to our studio here and let's actually introduce this new idea of a data type or a storage mode in R we have various ways of storing data we've seen one so far called a character string but there are lots of others too among them are these character we just saw and then double and integer these are both numbers double refers to a decimal number like a 1。

5 for instance， integer refers to a whole number like just one plane and simple and there are more two but these are the ones that matter here。



![](img/a850753e98eeda59c890c2c9b3736f91_26.png)

So it seems to me like Readline， when it returns us the input from the user。

 it returned a data type of character or a storage mode of character。

 but what I really need to addem to the other is a double or an integer。

 these numeric storage modes down here。So let's see if we aret functions that could help us actually are。

 so there among them are this idea of as dot character as dot double and as dot integer。

 these are functions and actually take some particular object and convert them to the storage mode we want so I could give as input to as dot integer some object it will return to me then that same object but now as integer and this is known as coercion changing the storage mode of an object using a function like this to convert it to some particular new storage mode So let's try these out。

 I'll come to our studio again。😊。

![](img/a850753e98eeda59c890c2c9b3736f91_28.png)

And I will then try to convert this data to an integer before I actually add it together let's on line5 and below。

 let me go ahead and use as dot integer， I'll type as dot integer Mario and as dot integer peach and as dot integer Bowser well in this case。

 hopefully that should work， let me go and hit source again and I'll enter let me click my terminal first。

 I'll enter 100 votes for Mario 150 for peach and 120 for Bser。

AndI still see that they're not numeric。 so one common mistake is that simply running the function here is not enough to change this particular object。

 I need to then reassign the return value of of this function to the object itself So for instance。

 if I want to update the value of Mario， I need to reassign it as the return value of as integer or I need to update the value of peach by reassigning it as the return value of this function here and same with Bowser as well。

 and now I think if I run this fingers crossed， I'll make my console again run source and I'll choose 100 for Mario 150 for peach 120 for Bser。

And I'll see the total votes was 370。Now this is a bit of a longer program that we've seen before。

 this is like 11 lines total。 there's probably a way to actually clean this up a little bit though。

 one way would be to immediately try to convert the input from the user2 and integer so I could use function composition and I could instead immediately pass the return value of read line as the input of as integer and same for P and same for Bser let me actually clean this up。

 have a pre there and a privacy here and now I can get rid of lines5 through7 and now it's just a little bit shorter and I'd argue that this is actually a good use of this particular function composition because now I'm immediately seeing that okay I want an integer from the user。

Let me go ahead and try this again， I'll click source， and now I'll see 100， 150，120。

 and I still see 370。Now， this is pretty good， but let's think of a co case or some other scenario where there are more than three candidates。

 Well， in this case， I don't want to be stuck， always typing plus you know plus plus some new candidate。

What I want to use instead is likely a function called sum Now R because it works so often that data has this function called sum that can take as input any number of numeric arguments and sum them up for me。

 So let's use sum instead in total here。 I actually want to return the result of calling sum with three arguments。

3 inputs。 The first is Mario second is peach and the third is Bser。

 So now sum will look at all three of these numbers add them up and store them now in total。

 So I'll clear the console run source and I'll type in 100 votes for Mario。

 150 for peach and 120 for Bowser， and now I'll see total votes with 370 as well。

 So we've improved our program so far。 And we've seen how to use these storage modes to add data together。

 Now what questions do we have on this program here or storage modes。😊。



![](img/a850753e98eeda59c890c2c9b3736f91_30.png)

In general。Can we enter an argument like an array to this same function？



![](img/a850753e98eeda59c890c2c9b3736f91_32.png)

Yeah， so I heard you mention this idea of an array and if you're familiar with other programming language。

 you might have heard this idea of an array， like some list of data。 And the question is。

 could we give some not these three separate values， but actually an array or some list of data。

 In fact， we can。 And I' if we actually take like a five minute break and come back to learn more about these structures we can use to represent data just like that。

 See you in five。😊，Well we're back and so we've seen so far how to write programs that take user input。

 but odds are as you write more our programs， you won't rely so much on the user to actually enter data for you for you you'll instead read data from a file like a CSV file。

 for instance， so let's take a look at ways you can actually represent data and how to use those representations now in R Well you often find data is stored in these things called tables and here is an example table I'm trying to represent here candidates like Mario。

 Peach and Bowser and the number of votes they received at the poll so this is actual physical polling location and via mail from mailin ballots。

 let's say。😡。

![](img/a850753e98eeda59c890c2c9b3736f91_34.png)

So notice how this table has both rows， this kind of horizontal orientation and columns。

 this vertical orientation in particular there are three columns with names。

 so one is candidate where I have the names of my candidates in this case Mario Peach and Bowser over here I have this column called poll are presenting the number of ballots or votes that Mario Peach and Bowser received at the actual physical polling location。

 so let's say Mario got 37 votes， Peach 43 and Bowser 84 now。

WellFor the mail column there's also going to be some numbers here as well。

 let's say Mario got 63 mailin votes Peach got 107 mailin votes and Bowser 36 so this then is our table of rows and columns and one kind of analysis we might want to do on this table is called a tabulation that is figuring out how many votes we received by poll or by mail and also how many votes each candidate received so we could ask the question how many votes did Mariio receive overall that would be a tabulation along these rows here we could also ask how many votes we receive at the actual physical polling location that would be a tabulation along this column here so there are two questions we actually answer using R。

But R at least immediately doesn't give us a way to represent a table exactly like this。

 If you want to store this data kind of long term， you need to do so in a file and one popular way of representing data like this inside of a file is to use a CSV file or a comma separated values file so here is these same representation of that data。

 but now as a CSV file notice here I have those same column names。

 candidate poll and mail and I still have those same column values， Mario Peach Bowser， 37。

 4384 and so on but what you might notice is that the columns are now separated using these comms and that makes sense this is a comma separated values file or a CSV file Every row is still on its own row in the file but now these columns are presented now with these commas So let's see how we could use R to read in this CSV file。

And give us an actual table of data to work with I'll come to our studio here and one of the first things I actually might want to do is clean up my working space if I want to see what's currently in my environment I can type this function LS at the console and hit enterter and now I'll see all the objects that I still have in my environment from some prior programs Now I probably want to get rid of these as I'm writing some brand new program so to do that I could use this function called RM which stands for remove whereas LS stands for list I could use RM and it turns out that RM takes a named argument called list that is the list of values I want to remove from my environment and I'll say that this list is what was the result of calling LS that is it will include Bowser reading Mariio name。

 peach and total， all of these prior object I no longer want anymore so I'll enter。



![](img/a850753e98eeda59c890c2c9b3736f91_36.png)

On this， and I'll type Ls again。 And now I'll see character parentheses 0。

 which basically says there's nothing here right now。 There's an empty string。

 nothing at all in my environment。So now my environment is clean， there are no objects here。

 let me actually create a new program one called tabulate so I'll do file。cre tabulate。

 R to represent how we're going to tabulate this table of data and find the number of votes for each candidate and each voting method let me do enter here and I'll see that file was created for me I'll go to my file Expr and open up tabulate R So actually notice here in my file Expr I do have this file named votes。

 csv if I click on it I can actually see if I click view file here。

 what's inside this file and notice here I have the same exact thing we saw on the slides candidate comma poll comma mail and then one row for every row in my dataset。

So our goal then is to read this CSV and store it in R so we can actually get back a table of data to work with now entirely in R what one function I could use to read data from a file like this is actually called read do table read do table and I can give read dot table。

 the name of the file I want to read or to open to load inside of R so that file name was votes。

csv and because votes。csv is in that working directory I can just refer to it by as plain and simple name。

So readout table has return value， it's going to give me back a table of data。

 so I'm going actually store that， let's say in this table called votes。

 and now let me run just this line of our code， I can do that hitting run over here or on Mac I could type command enter on Windows I could type Control En。

 I'll do command enter on Mac， and now I see according to the console。

 I have now read the votes data table here。So if I want to see what it looks like。

 there are a few ways to do that， I could actually look at my environment， let's try that first。

 I'll go to environment and I'll see the following that votes seems to have four observations of one variable so observations actually refers to the number of rows in this table I've gotten back and variable refers to the number of columns I've gotten back and you might already be thinking。

😊，This doesn't seem right because I thought I had at least three rows and I thought I had at least three columns。

 and I seem to have four rows in one column， so something might be wrong here。

 if we want to see exactly what happened， I can use this function called view capital V and I can pass as input the object I want to view in this case。

 if I run this line of R code， I should now see a separate tab that shows me exactly what is stored in this object and I would say these results are not good。

 This is not what I want to look like because again。

 we only have one column that R seems to have named V1 and instead of three rows there are four where one row is actually the names of the columns that I wanted to be the case。

This is just not all we want so it seems like read dot table needs more information on how to read this particular file and one thing it might need to know is what is the separator between each of my columns well because this is a CSV file that separator is other than a comma so read dot table like paste takes a named argument called SEP and this will set to B an actual comma so now read dot table knows to look for these commas and use those to identify what is a column inside of this data file so let me then rerun this line of code and now view it。

And I' we're getting better so here I have three columns although one is called V1。

 one is called V2 theres called V3 and I still have four rows so it's not quite there but we're getting close one other argument to read dot table is in fact this one called header header so header can be either true or false yes or no do the column names exist in this file in this case they do so I'll say header equals true I'm essentially saying that yes。

 the column names are inside this file you should look for them and you should use them so let me rerun this I'll rerun line1 and now line two and now I think we're in a pretty good place So R actually has stored inside its environment this table for me to use I see three columns candidate poll and mail and now three rows I could do something to make this little more readable often we have lots of arguments to these functions It's better to put them on separate lines。

According to the style guide for R that kind of tells me how I should be structuring my file。

 I should do something a bit like this， I should put each argument on a new line in my code and then make sure that this closing parenttheesis is all the way against the lefthand side。

 so this allows me to more quickly see what arguments I have supplied to read dot table。

 but the result is exactly the same， of course。😊，Now CSV files are pretty popular and it doesn't make sense to me to always be writing Sep equals comma。

 header equals true， and in fact， people who work with R。

 they come up with their own function called read dot CSv to make this much easier for us as programmers so instead of read dot table which can work on a variety of actual data files。

 I might instead use read dot CSv because of course I have simply a CSV here。😡，So let's try this。

 All' run。 just read dot CS SV。 given the file name。 hit enter here， enter here and。

It's the same result， but now with much less typing， much fewer arguments。

 read dot CSV just seems to know more naturally how to read these files called CSV files。O。

So we've successfully read this CSV file。But the next question is what exactly has it given back to us like certainly it's a table。

 but in R this table has a special name and this special name is a data frame Now a data frame so we're going to call a data structure。

 some way of organizing our data that allows us to do things with it much more quickly and those things for data frame might involve accessing the columns or accessing the rows or performing things like tabulations as we'll see in just a little bit。

 So here again， is our data frame， but now it's called boats just like this and let's say I want to access some particular columns or some particular rows of this data frame。

😊，Well because it is data frame， R gives me some special syntax some special actual characters I could type to access those columns and those rows。

 Now， one way is to use what we call bracket notation where I could take the name of this data frame use brackets and then supply the number of the row and the number of the column that I want to see So for instance。

 let's say I wanted to access this particular value Mario in the first column and the first row well in that case。

 I could type votes bracket one comma space one for the first value in the first row and the first column but more often you'll actually want to you want to access not just one particular value but all the values in a column or all the values in a row and to do that you can simply omit one or the other the row or the column value。

 so here to access all the candidates I could type votes bracket comma space one omitting the row number but only supply the。

The first column here that will give me this list of Mario Peach and Bowser。

What I wanted the poll numbers I could do boats comma to and that would give me 37。

 4384 and same for mail but now with number3 so let's try it in R I'll come back over to our studio and go back to my program and our goal again was to sum up。

 let's say the number of boats we got at the polls so I could at least see those values if I do boats bracket and then comma2 just like this let me clear my console and run this line and now I see those same values 374384 same thing here。

 37，4384 even though in my console they're kind of turned on their side like this these are in fact the same values I've seen in my table。

But what could go wrong here。 Well， if we think about this。

 whats to stop me from rearranging these columns from maybe making mail second column and poll the third if my program can't update based on that kind of rearrangement it's not a very good program So there is another way to actually access columns in this case using their name。

 So instead of the number of the column I want to access I can use its name which is much more robust。

 if I change the oring of the columns， I can still access the column I want to access Now the syntax for this looks a bit as follows。

 I would use the data frames name votes followed by a dollar sign and then I would get back in this case I would actually type the name of the column I want to access and I would then get access to that particular column So votes dollar sign candidate that give me access to this column of candidates same thing with poll votes dollar sign。

Poll and same thing with mail votes， dollar sign mail This dollar sign has nothing to do with currency is just a way to actually access a column by a particular name that it has。

So let's come back to our studio and try that out now， let's say I want to access the poll column。

 well instead of using the bracket notation with the comma 2。

 I could use votes dollar sign poll and now let me clear my terminal， my console down below。

 let me run source， and oops let me actually instead run this particular line here， I'll get 37。

 4384 just as we saw before。

![](img/a850753e98eeda59c890c2c9b3736f91_38.png)

So let me pause here and ask what questions we have about these data frames so far and I ask if I can get some particular value from some particular row by accessing the votes or is the main column votes bracket or sign is the column assign the value Yeah great questions so we saw earlier theres some syntax can get us access to some particular value in this data frame let's see that in action a little bit here too so I'll come back to our studio and let's say we want to access Mari's number of votes they received at the polls so this would be the second column and the first row and in R we tend to index things is start counting from one so the second column and the first row So here let me go ahead and try to access that particular value I could say votes like we saw before open and close brackets and I know again this is the。



![](img/a850753e98eeda59c890c2c9b3736f91_40.png)

First rowSo I'll put that as the one here and then the column number。

 which in this case was the second column counting from1， so two。

 this should if I hit enter on this line of code or command enter should show me that in fact Mariio has 37 votes at the polls。

I could do the same for peach， let's say？Peach has 43。Bowser， Bowser has 84。

So that is a way to actually access individual values in our data frame。

One other way to do this though is take advantage of another data structure so it turns out that when we access the columns of data frame。

 what we're getting back is no longer a data frame。

 or we're getting back instead is what R calls a vector。

 a vector simply a list of data that is all of the same storage mode。

 if you've heard of as in Cs and C or lists in Python， a vector is a similar idea。

 but it's simply a list of values all of the same storage mode。



![](img/a850753e98eeda59c890c2c9b3736f91_42.png)

So to visualize this， let's go back to our data frame here and let's say I want to access this particular column of votes。

 I could access it using votes， dollar sign， candidate， and when I do that。

 what I really get back is this separate structure that is just the values from that particular column。

And now because this is a new structure， I could actually use that same bracket notation to ask for particular values from this list of data。

 Now again， we start counting from one in R。 So this is our first value， second and third。

 if I want the first value， the first candidate， I could use votes dollar time candidate and then bracket1 that will give me Mario I could use votes dollar time candidate and then bracket2 that would give be peach and same thing with Bser here。

 So we're kind of taking out or extracting this new vector and we're able to access individual values in it。

 Now one example I like to use is example of building blocks here。

 So here we have our very own data frame composed of nine individual pieces of data。😊。



![](img/a850753e98eeda59c890c2c9b3736f91_44.png)

Now when I ask for some particular column from this data frame。

 what I'm effectively doing is taking out one column and treating as a separate object I can use in my program Now again。

 if I want the first value in this vector， I would simply take the one from the top， the second。

 the second one down， the third one， the third one down。😊，Now in R。

 we also see that when we print out vector Zeta in our console。

 they aren't always kind of vertically arranged like this。

 often there'll be a bit more like this where I might take in this case。

 kind of put it on its side a bit like this or I would now get A。

 B and C kind of left to right like this， even though in our data frame it was top to bottom。

 we might get it represented， kind of side by side a bit like this。

 so same thing ultimately and there's this idea of kind of extracting this vector from our data frame。

So let's try that now in R I'll come back to our studio and let's go ahead and try to access maybe the first value of the poll column now we saw before I could simply use bracket1 on this new vector that I've created by accessing the poll column of votes let me hit command enter and I'll see 37 let me do the second value and I'll see 43 so I think with this we could start to answer one question we had which was how many votes do we get at the polls in total Well one way to answer this is to say let's sum up votes dollar sign poll the first value in that poll vector。



![](img/a850753e98eeda59c890c2c9b3736f91_46.png)

Then let's find that second value as well， then let's find that third value just like this。

 and sum all of those up， and if I hit command enter here， I'll see I have 164 votes at the polls。

But just like we saw before， there's probably something that could be better designed about this particular line of code here。

 and that is， if I had more than three candidates， like I'd be having a really。

 really long line of code here。So what I could instead do is this。

 I could give some to our earlier question， the vector itself。

Simply votes dollar sign poll which we know is a list of values of vector。

 I could give that entire vector to sum that will then know what to do with it and return to me。

 in fact， the sum of each of those elements of the vector。So we call some here vectorized。

 some knows what to do when it gets not just a single value as input， but an entire vector。

 and R is usually built from the ground up with these vectorized functions that can take whole lists of data and operate on them very。

 very efficiently in this case。So here we've answered that question of how many votes we get at the poll。

 let's think that next one which was how many votes we get in the mail。

 well I could do now sum sum and then give the mail column which is in fact a vector and have that summed up and we'll see we've got 206 votes now in the mail。

😊，Okay。So we've seen vectors and we've seen data frames。

 but we still have one other question to answer， which was how many votes did each candidate get Now to do that we have some values across columns here。

 37 plus 63 is Mario's votes， 43 plus 107 is peach's votes and 84 plus 36 that's Bowsers's votes so let's try it I could maybe find treat two separate columns here I could do votes in what's that one poll okay votes poll get the first value for Mario and add up。

 let's say the first value in mail a bit like this and that I would argue is Mario's total number of votes。

What if we did maybe the second value in poll for peach。

 and let's say the second value in male also for peach？150。

 so that's pe's total number of votes Let's do votes and the third element in the poll column and the third element in the mail column and that would then be Bowsers' votes。

 and I hope you can tell by me being kind of bored while I'm doing this this is like not the best way to do this。

There is actually a better way that takes advantage of a feature of vectors in R。

 which is vector arithmetic， so not only a vector candidate representing lists of data。

 we can use them to efficiently perform math as well。

 so if I wanted to sum up all of these vectors and find out how many votes each candidate got。

 I could simplify this and simply type the following votes， dollar sign poll plus in this case votes。

 dollar sign mail， and that would be it。But let's visualize this and see why exactly this works so we said we had this idea of vector arithmetic and here again is our data frame so I want to effectively sum up these two columns and return to myself a new total for each candidate for every row in fact that I have well to do that I can take out these two vectors pole and mail and think of them separately now。

😊，Now I want to add these together like we said， 37 plus 63， that's Mario's votes， 43。

 107 that's P of votes。 well to add these I could use the plus sign just like this。

 but if you're new it's not quite obvious what's going to happen here， I mean。

 how could I add up these three numbers and these three numbers and what is the structure of what I get back in the end？

Well it turns out that R uses a new vector as the result of this。

 and it actually computes the new values element Y's。

 element y is meaning it goes top to bottom in each vector and adds those two corresponding elements together。

 so first it looks at the first element in each of each column here。

 the pole column and the male column 37 plus 63 is 100。Then it goes to the next one。

 43 plus 107 is 150， then it goes to the next one here， 84 plus 36 is now 120。

 and we now have a brand new vector by adding up or summing together these two distinct vectors overall。

To go back to our visualization here of these blocks so you could think of me taking a data frame just like this and kind of extracting these two vectors here。

 let's say this one and let's say this one and I put this one to the side for now and I want to do some math with these so in this case I'll look at the first element in each vector in this case4 and in this case1 or4 and1 what is the addition here or4 plus1 is5 so the first element to my new vector would be5 then I go to the next of two elements here in this case I have5 and2 what's5 plus2 that 7 so the second element my new vector would be 7 and then later on what do I have I have six and3 those added together would be9 my third element in my new vector would in fact be9 so vector arithmetic gives us in the end a new vector by actually adding or in this case adding these element together kind of element wise in the end。

So let's go back and see how this looks in ourSt， I'll come back to our studio here。

 and I will then hit enter on this line of code and we'll see that I get back a vector of three elements。

 100， 150 and 120。😊。

![](img/a850753e98eeda59c890c2c9b3736f91_48.png)

So let's pause here and ask， what questions do we have on these vectors or vector arithmetic？

How this form is being printed printed on the terminal and I will be out using the print function。

Good question so you've noticed that when I press command enter， for instance。

 I'm seeing the results， whatever is stored in this object in my console without using print and that in fact is a feature of R and R studio that when I run some particular line of code I can then see the return value of that particular line or whatever it computes for me down in my console it's kind of a handy feature of these things called IDE so let me actually understand what's going on in my code all the more clearly。

😊，Good question I have a question in data frames So when we in the dollar notation it returns a vector what about in the bracket notation suppose suppose we are taking for a row1 comma does it also return a vector a great question so we just saw with dollar notation we get back a vector does do the same thing then with bracket notation so in fact it does let me show you how it works in our studio I'll come back over here。



![](img/a850753e98eeda59c890c2c9b3736f91_50.png)

And let's say I wanted to sum up these two columns still。

 but don't want to use their names for whatever reason。

 I'll instead use their bracket kind of representations here。

 so I'll take the second column of my table here。Using comma2， and I'll add together in this case。

 the third column， just like this， I'll hit enter， oops。Hit enter。 and I'll see。

 I get back the same result。 So these， each one of these is， in fact， a vector。

 where you should be careful， though， is that there is some notation looks a bit like this votes。

In this case， bracket one， notice how' I'm not actually asking for a row and a column。

 I'm only asking for some number one， this will give me back in this case， the data frame。But now。

 only the first column of that data frame。 So this to be clear， is not a vector。

 This is the same data frame， but now it's only that single column of that data frame。

 So be careful here。 You won't often use this notation。

 but that you could get back a data frame if you use that kind of notation overall。Okay。

 a good question and let's now keep going towards solving our problem of tabulating this data so we saw before that simply adding the mail the poll column in votes。

 and the mail column in votes would give us the total number of votes for each candidate but I would argue that if I run line3 here。

 and I just get back some numbers， it's not super clear which candidate these votes belong to so I can actually go ahead and add a new column to my data frame that includes these particular values here。

 one for Mario， one for peach and one for Bowser and as long as my vector is of the number is of the same length as my number of rows in my data frame。

 I should be able to actually add this as a new column to my data frame。

Now to create this new column I could simply kind of wish it into existence a bit like this。

 I could say votes dollar sign total， and I know there is no column called total。

 but I can kind of make one I could say let's assign this vector to B the new column total in the votes data frame if I run this line。

 I'll see， I don't get a result， but I do at least in vote C。

 there is a new column called total that now includes those same elements in my vector top to bottom。

O。So we've solved that problem and our next step might be to now save this file again to keep track of it later on to share it with a friend and to do that I could use the write docsv function we saw read。

csv but we also have write docsv to actually save this file as a CSsv let me try it I'll say write。

csv and I'll call this one let's say totals。csv for the total number of votes。

Now right docsv actually needs two arguments， one is the file name， like we just said here。

 but even before that it needs to know what data frame to write to the file。

 so in this case it's our votes data frame。Now by convention， in its documentation。

 we see the first argument to write docsv is that data frame。

 the second is the name of the file itself。😊，So let me clear my console， let me run write。csv。

 and now if I go to my file Explorer， I should see down below， oops， totals。csv。

And now let me view file。😊，And I should see something a bit like my data frame。

There's a few other features here though I see that there's like these numbers here， one，2。

3 and this empty number up this empty value up here。

 these are in fact the row names of this data frame so not only do data frames have column names like we saw here they also have row names and by default they start counting at one and going to two then three then4 and so on and I can actually tell write do csv whether or not I want those row names printed in my CSsv you often won't because it kind of makes a wacky format we have this empty value up here and it's probably not not worth it for you so you could specify the following you could say row dot names row dot names equals false meaning that write dot CSsv should not write any row names to the CSv even though they exist in data frame So let me go ahead and clear my console。

 I'll do command enter here and now I should see if I go back。

To total CSv I now have a much cleaner CSv without those particular row names If I did though want to access those in R。

 I could use these functions， I could say call names。

 votes which will return to me the columns I have inside of my votes data frame or row names， votes。

 which gives me access to the row names of this particular data frame as well。



![](img/a850753e98eeda59c890c2c9b3736f91_52.png)

Allright， so we've seen here how we've been able to save this data frame。

 how to read data from a file and save it back to a file as well what we'll do next is actually take advantage of online data sets other folks have written for us and use those to explore data in R as well see you all in five Well we're back and so we've seen a few examples of how to use R so far we've seen how to take user input and actually deal with that in our own programs。

 we've also found how to use data we put in our own file for ourselves but often when you use R we work with not your own data。

 but somebody else's and so we'll do exactly that here for the rest of lecture Now you may have heard 538' mentioned earlier in lecture。

 they work a lot with data and they often put that data online for others to use and analyze themselves In fact they worked on a poll that asked people in the US about their voting habits do they plan to vote how often do they vote。

What encourages them or motivates them to vote or what are the reasons they actually don't vote in the first place So here I have the URL that actually includes this data file online on the internet somewhere else and if you look at the end here you'll see the file name nonvoters underscore data csv so this tells me that this data even though it is online is still stored in that same familiar file format called a CSv and now on the second line of code I can still use read CSV All I'm doing now though is telling read CSv where to look where to go find this data file on the internet and bring it down for me here in my own R environment and I'm storing the result now that data frame as a data frame called votersters。

So let's take a peek and see what's inside I'll come to our studio over here and let me do the function view view and I'll view voters and whoops actually let me first run of these lines of code so let me run line1 to create a new object called URL let me run line two to actually load that data and now once I have those objects loaded。

 let me go ahead and view Voters。😊，And this is the data frame。It is a big one。

 if we scroll all the way to the side， you'll see lots of numbers， lots of columns。

 if you scroll down， you'll see lots and lots of rows， and one question you might have is。

 well just how many rows and columns are there in this data frame。😊，One way to answer that。

 at least in our code itself is to use these functions N row and N call which stands for number of rows or a number of columns respectively。

 so let me try n row to get a sense of how many rows we have in this data frame I'll do N row voters and it seems like down my console here。

 there are 5836 rows of data now each row of data represents a particular voter or maybe a nonvor。

 somebody who lives in the US and was asked to fill out this poll where they talk about why they vote or why they don't vote。

 but in the end each row is its own voter。Now let's see how many columns we have and call voters。

 it seems like we have 119 columns which is a lot of columns。

 each column in this case represents a question asked to that voter and if I go back to the votersr's view here I might see like Q1 for instance。

 it seems like the voter who has given the ID 47 420。

00001 answered1 to question1 and so it's a little arcane right now but thankfully 538 has given us a tool we can use to interpret some of this data。

In fact， that tool is called a codebook and you might often use the same in your own work with data analysis where a codebook tells you exactly what questions or columns mean in some particular context so in this case I do see Q1 or Q2 underscore1 or Q2 underscore 2 and if I'm new to the data I don't know what the heck that means but I could look in the codebook that 538 gave me in which case they say Q1 asked participants this Q2 asked participants this and so on and so forth for all questions we have inside our data set So let's actually take a peek at one particular column I know this column exists because I looked in the codebook to find it out there's a column called voter underscore category that actually tells us how each voter represented themselves in terms of their voting habits so to access that columns you saw before。

 I could use voters， the name of data frame followed by a dollar sign。

Followed by the name of the column， voter category and if I hit command enter here。

 well I'll see at least some of the results from that column。

 some of the elements here and now you'll actually see why that bracket one that we saw initially is kind of useful now as we work with bigger and bigger data sets notice that that bracket notation tells us is actually where in our list or our vector we are notice how this one here means this always that is the first element in our vector of all of these responses this always。

 well that's the seventh element in our vector of all these responses and same thing for this rarely slash never。

 that is the 13th element and so on and so forth all the way down now there's more than what looks to be 900 or about 100 entries in our vector here we just can't print all of them because it would be really really long output to our console。

Now I'm curious。 I saw a lot of values here， but I want to know exactly what ways voters could have categorized themselves like out of all of these responses。

 what are the unique ones and turns out R has a function called unique that I can use to actually figure out what are those unique values in this vector。

 So let me give this vector called a voter category or the column voter category from voters to this function called unique just like this。

 I'll do command enter to run this line。 And now I'll see I only get back three elements always sporadic or rarely slash never。

 So it seems like voters could have categorized themselves in one of three categories。

 they always vote they sporadically or occasionally vote or they rarely slash never vote at all。

 So interesting data here。 There's another actual column I'm interested in two which is。

happens to be question 22。 so if I look at that here， I'll type voters。

 question 22 and hit command enter and here I'll see all the responses for this particular question and it seems to me like I'm seeing some numbers but also these N As and before we dive into that。

 let's take a peek at what this question is actually asking users So it turns out this question 22 is asking users this you previously indicated that you are not registered to vote which of the following reasons best describes why you are not registered to vote and user are given several responses one through seven。

 I believe where one was I don't have time， two was I don't trust the political system3 was I don't know and so on and so forth。



![](img/a850753e98eeda59c890c2c9b3736f91_54.png)

And it seems to me like when we saw this data set， we had some numbers here， one through seven。

But we also had a lot of these N As， and I'm curious。If you have a sense of what those Ns might be。

 there's certainly not any of these options， what do you think those NAs might represent in this particular column of data here？

Not answered or not aated to be enists。 a great guess。

 So maybe it means something like not answered or there's just no data there。 And in fact。

 if we look at the context of this question， they would actually figure it out like you did。

 It says you previously indicated that you are not registered to vote。

 So in the US we often have to register ourselves to be able to vote。

 but some people have done that and some people haven't。

 It seems like this question was asked to only those participants who did not register to vote or who were not currently registered to vote。

 So it would make sense then people who actually are registered couldn't have answered that question。

 And in which case we don't want to have like an empty string or some social number there。

 we could instead use one of our special values。 Now R comes with these special values to indicate something very special In this case。

 NA means not available。 there could be data here。 but there isn't。

 That's what NA in particular means。

![](img/a850753e98eeda59c890c2c9b3736f91_56.png)

Others too， you might see inth and negative inf， these mean infinity or negative infinity numbers that are so big R can't represent them appropriately well we saw NA here for not available。

 we also have n lowercase AN， which stands for not a number。

 you could think of if I tried to ask you well what is infinity divided by infinity。😊。

And you probably look at me confused you would say that's not a number and I would say yes。

 that's exactly correct R says NAN is that result in this particular case。

 and we also have this value called null capital N ULL。

 which is similar in spirit to NA but slightly different NA， as we said before。

 stands for not available There could be data here but there isn't null is simply a special value。

 meaning absolutely nothing。 I can have a vector of NAs。

 meaning that maybe I have five nas in this vector， there are five places data could be。

 but I can't have a vector of null null is literally nothing， it means absolutely nothing at all。

 So different slightly from NA in this case。😊，So let's go back to our studio here and let's take a peek at this particular this particular column so it seems like I have a lot of NAs and one thing I'm interested in is what kinds of unique values are we seeing inside of this particular column so I could use unique again and hit command enter。

 and now I'll see if I clear my terminal run it again。

 I'll see clearly that I have several different possible values here I have NA，7，6，2 negative one，1。

4，5 and 3 and this makes sense like we saw earlier that people were given several options。😊。

One through seven， and we have people who didn't respond either with NA or one through seven for those other responses there。

What we don't have actually is negative one and I actually tried kind of hard to figure out why negative one is here and I couldn't so sometimes data is just messy。

 there are values you don't know it can't deal with。

 so to keep that in mind as you work with data sets， other people have given you。

Now one more column that I found interesting was this one， so it was voters question 21， question 21。

 and the question 21 asked this， it said there will be an election for president。

 members of USS Senate， House ofpresents and other state and local offices。

 do you plan to vote in that election and it gave people a few response。

 a few potential options here， one meant yes， two meant no， three meant unsure or undecided。

 I don't know if I'll vote in that election？So let's see what we actually got back at responses for this particular question。

 I'll come back to our studio here and why don't we take a peek at Voters question 21。

 I'll hit command enter and here is the first 1000 or so entries to this particular question so we see a lot of ones which could mean yeses I see some twos which could mean no three unsure undecided I just see a negative one down here which seems to showing up for some unknown reason。

But we could get a better sense if I used unique， so I use unique voters question 21。

 and now I'll see again， my unique responses are1， two，3， or negative1。😊，So at this point。

 I'm kind of getting tired of looking at my vector here and trying to convert in my head between these ones。

 twos， threes， negative ones，2， the actual response participants gave and it turns out there is a way in R can make it much easier for myself to work with data that's exactly like this this data has some set number of categories of responses as we saw with unique here the categories are in this case one。

2，3 or negative one， those are the only possible values that could be stored in this vector and we also know that one。

2， and three correspond to some real life actual phrase that pitch actually responded to in this poll so to help us represent this kind of data we can use something that R calls a factor a factor and I can create a factor using the factor function and a factor function takes a vector like the one I just have。

But when I just had here and converts it into a factor， so let's try that， I'll say factor voters。

 Q21， just like this， and I'll hit enter again Command enter。

 and I'll see a very similar thing if I scroll up， I have all the same data。

 everything is just as it was， but now down below， I see levels。

Levels and what does that look like to you or we just saw before we have several unique categories of data inside this vector。

 negative 1，1， 2， and3， and it seems like this factor took those unique values and made it this factors level。

 so the unique possible categories of data inside of this factor here。

So factors are great for representing this categor called data。

 data that can actually be in one category or another。😊。

Now one thing I could do is try to make it easier to read these categories as English phrases and to do that I could pass factor another argument。

 this one called labelbels， so not only do I give it my vector that has certain categories of data。

 I also give it some labels to apply to each of those categories one after the other。

So here let me use labels as the argument and let me give it a vector itself so we saw before down below that we have a set of levels。

 number of categories in this data， negative 1，1，2 and3。

 but now I could actually give those levels those categories some particular name so I'll give it a vector itself and I'll make a vector in R using this C functional transfer combined I'll create this vector where negative one。

 let's say maps two or corresponds to this value as a question mark I don't know what the heck it is。

 maybe one though we saw was yes and two was no and three was unsure or undecided exactly like this。

So now notice that when I look at my levels， negative one， that corresponds to the first label。

 question mark， what the heck is it， I don't know， then yes， that corresponds to the level1。

 then level 2 corresponds to no， level 3 corresponds to unsure or undecided and now if I clear my console and run this particular line of code。

Well now I have something much more user friendly， I can actually see not ones， twos and threes。

 but now labels for those ones， twos and threes。 and I here I see yes， unsure'm sure un decided， no。

 let me see I can find a question mark here。 Yep， there's one so 517 seems to be a question mark。

 So now I've converted this vector into my own factor。

Now it's also not a good idea to have data we don't know what to do with， like I said。

 this negative one， I really don't know where it came from and in that case I could tell this factor when it's being created to exclude that value altogether I could use the exclude parameter。

 the argument here and say I want to exclude some vector of given value that are part of this vector I want to take out altogether so I'll say negative one is the value I want to exclude this is a vector of length1 but the value I want to exclude in this case is negative one and now I can actually remove this label here because my only categories will now be yes。

 no unsure undecided or underneath the hood， that one，2 or three。Let me clear my console again。

 let me rerun factor here and now let me see， well now my head is getting much cleaner， I have yes。

 no unsure undecided and if I go back to that 517 that we saw a question mark in up here。

 let me see if I can find it again， 517 almost there。

 I see now it's an NA which stands for of course， not available。

 we excluded it altogether from this particular factor。😊。



![](img/a850753e98eeda59c890c2c9b3736f91_58.png)

So what questions do we have now on taking vectors and converting into these factors that involve categories of data and labeling those categories of data？

Why have we used factor instead of as factor like before So we've just seen here this function called factor。

 but there is a function called as dot factor similar to what we saw before as dot character or as dot integer or as dot double we could use I think either one to get the same result in general though let me look at documentation let me go back to our studio here let me pull up the documentation for factor let me clear my console let me do question mark factor so this is here how we're supposed to use that factor function we can see here some of the arguments the actual parameters I gave like the labels here as well let's now try to find the documentation for as dot factor as dot factor and me go back over here。

😊。

![](img/a850753e98eeda59c890c2c9b3736f91_60.png)

Type as dot factor， and now I'll actually see。I'll see the same documentation page。

 and so to me this is symbolizing that these are very closely related， if I were to scroll down here。

 I could see， I think I see it here is dot factor as dot factor are the membership and coercion function for these classes。

😊。

![](img/a850753e98eeda59c890c2c9b3736f91_62.png)

Essentially， if you want to make a new factor from a vector， you would use factor。

 if you have something that you want to convert to a factor that is already something else entirely。

 like maybe not even a vector， you might be able to use as dot factor。

 so I hope that at least gives you some idea of the difference between as dot factor and factor as the function itself。



![](img/a850753e98eeda59c890c2c9b3736f91_64.png)

![](img/a850753e98eeda59c890c2c9b3736f91_65.png)

All right， what other questions do we have？Let's take a few more。

How is a factor different from a table？Good question So we saw that a table has rows and columns in it。

 A factor， though， is simply a list of data， a bit like a vector。 it's one dimensional。

 And let me show you some slides it could hopefully actually help you visualize factors in general。

 So I come back over here， let me find the right slide to go to。😊。

Here in general is this idea of a factor so we had of course this vector that was previously only ones。

 twos， threes and twos and one's negative one， but when we convert it to a factor we did the following we found the unique categories of data in this vector just like this one2。

3 and negative one what we then did is we sought out those categories and called them essentially levels the categories of our data are the levels here and we applied some label to each of those levels。

 basically saying negative one becomes question mark， one becomes yes。

 two becomes no3 becomes unsure slash undecided。

![](img/a850753e98eeda59c890c2c9b3736f91_67.png)

Now notice that this factor here is still。A vector。 Well， still kind of one dimensional。

 It's a list of data It's not two dimensional like a data frame was， or a table was。

 it's only one dimensional。 And when we apply these labels， we convert these ones， twos， threes。

 negative ones instead to yes， no， unsure and question mark。

 And if we exclude something like we did with negative one。

 we would then get NA instead of negative one in the end。

So I hope that helps least a little bit answering that question， let's say one more here。

 I wanted to understand whether just I you showed how to exclude a negative value。



![](img/a850753e98eeda59c890c2c9b3736f91_69.png)

![](img/a850753e98eeda59c890c2c9b3736f91_70.png)

What if I wanted there are number of negative values on the data free and I want to exclude all of the negative values。



![](img/a850753e98eeda59c890c2c9b3736f91_72.png)

Good question。 So the first part is you want to represent any negative values and how do you do that And the second part is how do we exclude those negative values。

 let's say another kind of similar case is let's say we have lots of NA values。

 How do we get rid of them。 So let me answer your first one and actually tee up that second question for next lecture。

 So come back to our studio and let's try presenting some negative values here。

 we saw before that I had this idea of negative one。

 if I want to have some negative value in our studio。

 I can simply put a negative or a dash in front of any particular value。

 So here let's say is negative one。😊，But to your question then of how we could exclude these values we don't want。

 that's a problem of filtering or subsetting our data which we actually learn about next lecture。

 so we've seen so far how to represent data in R， how to take all kinds of data like votes tables of votes and represent them in R to manipulate them and so on。

 what we'll see next time is how to actually transform that data。

 removing values we don't want adding data we do and for that we'll see you all next time。😊。



![](img/a850753e98eeda59c890c2c9b3736f91_74.png)

![](img/a850753e98eeda59c890c2c9b3736f91_75.png)

![](img/a850753e98eeda59c890c2c9b3736f91_76.png)