# 哈佛大学《商业的计算机科学｜CS50's Computer Science for Business 2025》中英字幕 p04 CS50 Business - Lecture 3 - Practicing Programming .cut.zh_en -BV1ArsFzQECJ_p4-

Oh。It's okay that we're like， Colton， do you mind grabbing the print out that I sent to the printer。

 there's one sheet。All right， hello world。 My name is David Main。

 This is our second of two live streams for today。 This one is on CSs 50 B CSs 50s computer science for business。

 a new and improved version thereof this course will go live onedx and other platforms later this year。

 So attending now offers a bit of a preview my apologies for starting so much later。

 although it is by interesting chance 1，3，37 right now。 So the will know what I mean by that。

 but we are 37 minutes behind schedule， my apologies for the curious we were having audio difficulties whereby the audio coming out the HDmi port of my laptop just fine。

 however， when I try to send sound from a terminal program like Mac Os say command also exists。

 I believe on Linux as well as from Python code that's using a text to speech synthesizer it's not coming out。

 So we finally got it to come out the 8 inch mini stereo connector， which seems now to be working。

 So T LDR we're back feel free to come on up with this。 So in just a moment。😊。

start the actual lecture this is going to be about practicing programming odds are if you're watching this live stream thank you and are familiar with CS50's past courses。

 you might be familiar with a lot of this already but it's meant to be introductory for an audience of less technical folks who might want to get a sense of what you programmers out there Ill actually do So with that said we'll begin in just a moment。

😡，Thanks， Su。Hello， world。 My name is David Main， and today we'll be practicing programming。 Now。

 we're not going aspire in just one lecture to turn you into programmers。 Indeed。

 this is something that takes more than just a few hours。

 at least to get good at and comfortable with。 However。

 our goals for today are to give you a sense of what programmers do and to give you a sense of how a lot of the ideas in the course thus far translate to actual code。

 the stuff that programmers write。Ultimately， you'll be a little more conversant in the ideas that underlie a lot of today's code and software。

 and frankly， you'll be prepared to learn all the more about programming if that's a direction you would like to head in。

 Now， I claim that we're gonna to be practicing programming today。

 because we actually did a little bit of it already in the course's first lecture。

 albeit in something little man。That was a really good intro until then。Can we start over。

Hello world。 My name is David Main and today we'll be practicing programming Now we're not going to aspire in just a few hours together to turn you into programmers indeed that's something that can take quite some time。

 but we will familiarize you with some of the underlying principles of and skills related to programming itself so that you're more conversant in what programmers do you can ask more informed questions and frankly you'll have a better understanding of how software around us ultimately works Now ultimately this might very well we your appetite to learn all the more about programming and indeed you'll get some of the fundamentals today so a foundation on which you can build Now I say we'll be practicing programming because we kind of sort of did a bit of this already in the course's first lecture recall that I acted out this algorithm of finding someone like John Harvard in the phone book and then we translated what I did sort of intuitively that third and final algorithm to this so-called pseudocode which were terse English instructions that really captured step by step the algorithm that I was reporting to implement。

😡，We did this because there were a few salient ideas within this pseudocode alone。 And to be clear。

 pseudocode is not some formal language， it's just my own inclination to use short English phrases to state what I was doing。

 you might have used slightly different words you might have used a language other than English。

 but pseudocode is a nice way of just expressing your thoughts akin to how a computer might expect step by step algorithms more generally and recall that we highlighted a few of the key phrases here So pick up open to look at call open to open to and quit We're all actions calls to action verbs。

 if you will， and we called those the other day functions。

 And today we're gonna to see all the more functions in actual code as well。

 We then took a look at if else if elseif and else。

 which were representative of conditional forks in the road via which you can decide to go this way or this way or this other way metaphorically inside of a computer but how do you decide which direction to go Well those were the Boolean expressions named after a mathematician bull whereby the answer to a。

an expression must be true or false。 Or if you prefer yes or no。 So person is on page。

 person is earlier in book。 person is later in book where all questions that I might have asked myself in order to determine should I be searching to the left or to the right or maybe right there in front of me already。

 Lastly， we saw this phrase， go back to go back to which was representative of what we're again going to call a loop。

 some kind of cyclical structure that makes me do something again and again and again。

 probably not forever， but until some condition is true。

 like one of those Boolean expressions a moment ago。

 So these functions and conditionals and boolean expressions and loops and more are going to underlie most all of today's programs and indeed in what's called procedural programming。

 you see these kinds of ideas everywhere， whether it's in pseudocode like this or as we'll see today where we'll spend much of our time a language a popular language called Python。

 Now， of course， pseudocode is not one。

![](img/f4dde6592256d1f95c23cf86a105feca_1.png)

Standard， but when it comes to actually programming computers themselves。

 we do tend to need to standardize how we're expressing ourselves Now this is already beginning to evolve with AI and natural language processing where increasingly you can in fact。

 just use your English words not unlike pseudocode to command a computer to do something but somehow or other the computer is then translating what you have said into the underlying building blocks that we will spend our time on today。

 so these ideas， these fundamentals aren't going anywhere and indeed among the values of learning how to program is that you do learn to think I dare say more methodically you can break down problems into smaller problems and ultimately be a better problem solver and if and when those processes get boring too easy for you I mean that's a good time at which to outsource it so to speak to the AIs of the world and let them do those tasks for you but for now we're going to focus on exactly these fundamentals and really talk about code the instructions that humans write in order。

😡。

![](img/f4dde6592256d1f95c23cf86a105feca_3.png)

To instruct a computer to do something step by step。 So it's a translation into text。

 typically an algorithm， which could be expressed as we've already seen in other ways。

 like pseudocode。 Unfortunately， computers， as you might recall， only understand zeros and ones。

 the so-called binary system and inside of the computers， memory or Ram。

 there's so many of these zeros and ones and some of those zeros and ones might represent numbers。

 as we've seen， or letters or maybe colors or images or videos or sound or really anything else。

 but those zeros in ones ultimately need to be understood by the underlying computer。

 the so-called CPU， the central processing unit or brain。 And in fact。

 not all of those zeros and ones are just data files， for instance。

 some of those zeros and ones might actually be instructions so to speak and very simple instructions typically like add two numbers together or subtract two numbers or load something from memory into the CPU or store something from the CPU。

To memory that is to say when you have a CPU inside of the computer among the things it does is these very low levell instructions and those instructions have been standardized by companies like Intel and Apple and AMD and others。

 So each computer has a so-called instruction set a set of commands represented in zeros and ones that it and it alone understands。

 So unfortunately， this is not gonna to be very fun for us to write if practicing programming is going to be practicing a whole bunch of zeros and ones。

 And I'd claim that by looking at these zeros and ones。

 you probably can't glean what this program does。 If a computer were to read these zeros and ones top to bottom left to right。

 what does it do。Of course， it prints out hello world， a very friendly greeting to the human user。

 Now， no normal person can actually gck what's on the screen here。

 It would be painstaking to go through all of these zeros and ones and look up what they mean。

 But computers of course， can understand this right away。

 But I think it would be nicer for you and me at least。

 if we don't have to bother writing what we're gonna to start calling machine code。

 the zeros and ones。 the computers ultimately understand。

 It's going be a lot more pleasant and a lot more productive for you and I to write what the world called source code。

 So when people say code， they generally means source code specifically。 And this means the code。

 the text that the humans write and then feed into the computer somehow to get it converted at the end of the day to zeros and ones。

 So for instance， here is one form of source code。 This is a language broadly known as assembly language。

 if it looks a bit cryptic to you。 It does and always has for decades， In fact。

 I had to write this in school myself a different。

![](img/f4dde6592256d1f95c23cf86a105feca_5.png)

![](img/f4dde6592256d1f95c23cf86a105feca_6.png)

thereof and I've forgotten most of the specifics。 but this is how people program for quite some time just beyond the days of punch cards for those of you familiar with those。

 once we had a keyboard in front of us that we could store data in digitally。

 we were essentially storing instructions and data like this。

 But there are some insights we can glean like push queue seems to sound like push move Q。

 probably move， maybe moving things around in memory calling。

 which is a vernacular that we'll soon see popping。

 which is a phrase that we've actually seen in the context of data structures and stacks。

 and then perhaps some familiar words most important of which is this phrase down here。

 hellello comma world， which is going to be exactly the phrase。

 I claim that those zeros and ones output。 So even though you might not believe me it is a lot easier to implement hello world a program that just prints that on the screen in assembly language。

 certainly than it would have been to implement it by hand using zeros and ones A machine code。

 But even this decades ago， humans realized。Yeah， we can do it， especially with a lot of practice。

 but this isn't very pleasant to write in。 and frankly。

 it's not very readable by others unless they too are very learned in the language。 So over time。

 humans began to abstract on top of these lower level languages on top of the machine code on top of the assembly code until we had more modern languages like this one here。

 This is a popular omnipresent still language known as C that similarly just prints out hello world。

 and it too is a bit cryptic like I don't know what hash includes standard Io in angled brackets and then these parentheses and curly braces like there's a lot of syntax going on here。

 a lot of text， a lot of punctuation， if you will。 But at the end of the day。

 this program too is going to just print the screen hello world but with a lot less effort than it would have taken me to implement that same program in assembly language and way less effort than it would have taken for me to implement it in zeros and ones that is machine code but there's other variants。



![](img/f4dde6592256d1f95c23cf86a105feca_8.png)

![](img/f4dde6592256d1f95c23cf86a105feca_9.png)

![](img/f4dde6592256d1f95c23cf86a105feca_10.png)

Of this same program。 In fact， hello world is written can be written in most any programming language here。

 for instance， is a inspired language called C plus plus， which came a bit later。

 Here is a language called Java that similarly is quite popular。 But here too。

 the key detail is that that same phrase is in there。 But here too， both with C plus us and Java。

 there's a lot of overhead， syntactically， And so what's nice about the language that we're going spend a lot of our time with today in particular。

 is that Python， a very popular language nowadays， not just for writing code more generally。

 but specifically for crunching numbers， analyzing data。

 cleaning up data implementing web applications and more Python really tends to be simpler then a lot of programming languages。

 And that's one of the reasons behind its popularity。 case in point。

 if you wanted to implement a program in Python that prints to the screen， quite simply hello world。

 Well， you just write this print open parentheses， quote unquote hello world。 Now to be fair。



![](img/f4dde6592256d1f95c23cf86a105feca_12.png)

![](img/f4dde6592256d1f95c23cf86a105feca_13.png)

Some syntax there。 there's parentheses。 there's double quotes。

 but I dare say this is the easiest of the versions to write。

 but Python itself is nonetheless very powerful。 It's just the humans that invented it and have evolved it over time have tried to make it read as much like English as is possible with one of these programming languages So if you're curious to see what other programming languages exist in the wild。

 you can actually go to Wikipedia to such URLl is this and you'll see dozens。

 hundreds even thousands of programming languages via which you can write not just hello world but any other program and in fact。

 if you're curious to see hello world specifically at this website here is a massive list of implementations of hello world in bunches of languages In fact。

 it's kind of a fun way to get a quick sense of what other languages look like albeit for implementing something relatively simple like printing to the screen。



![](img/f4dde6592256d1f95c23cf86a105feca_15.png)

![](img/f4dde6592256d1f95c23cf86a105feca_16.png)

![](img/f4dde6592256d1f95c23cf86a105feca_17.png)

Alright， so if we now have source code at our disposal in any of these languages。

 but soon we'll focus indeed on Python， how do we actually get the computers to understand that source code。

 If again， all they understand at the end of the day is machine code。 the underlying zeros and ones。

 Well， there's a few different paradigms that the world has had over the years to achieve precisely that goal。

 for instance， if we draw an abstract drawing here with the CPU。

 the computer's brain or central processing unit all along the bottom here。

 I got three columns ready to go here， because I'm going to propose that we consider three different ways of getting source code to be understood by computers Why。

 Well， again， it's a lot more fun and pleasant for you and I to write code in Python it would seem then in machine code。

 zeros in ones。 So how can we get from one to the other。 Well， one common paradigm is to do this。

 you need to get to machine code at the end of the day。

 because that is what under is understood by the underlying CPU， But you and I again， would like to。



![](img/f4dde6592256d1f95c23cf86a105feca_19.png)

![](img/f4dde6592256d1f95c23cf86a105feca_20.png)

![](img/f4dde6592256d1f95c23cf86a105feca_21.png)

Focus on writing source code。 So how do we get from source code to machine code？ Well， years ago。

 humans invented， if you will， wrote software， called a compiler。

 and there's many compilers in the world。 but at one point there was one first compiler and its purpose in life was simply to translate one language into another In this case。

 it might have translated the source code， for instance。

 written in C into the underlying machine code zeros in ones and compilers really more broadly just convert one language to another so we can convert among all of the languages we've discussed thus far down to assembly language down to those zeros in ones。

 their purpose in life really， is to make your life and mind easier。

 allowing you and I to think at and write code at a fairly high level of abstraction if you will。

 give me print hellello world on the screen without having to worry about the underlying zeros and ones。

 someone else smarter than me， put in the time to write code that implemented a compiler so that I can just run。



![](img/f4dde6592256d1f95c23cf86a105feca_23.png)

![](img/f4dde6592256d1f95c23cf86a105feca_24.png)

Compilr by like double clicking an icon or typing some command in my computer to convert my source code into machine code。

 And the upside of this is that even though it might take a moment， a second， few seconds。

 maybe a few minutes for massively large projects to convert source code to machine code once it's stad as zeros and ones。

 It's gonna be really fast on my Mac， my PC or my phone。 And in fact。

 this is the paradigm that C still follows and see。

 even though it's an older language now by decades still incredibly omnipresent。

 because it fits in nicely to this model of compileiling down to very fast zeros and ones。 Moreover。

 you can leave it to the computer scientists of the world and the softwareer developers to write really good code for the compiler itself so that the compiler turns even your messy code。

 your inefficient code into something even faster underneath the hood。 Now that's not the only way。

 because I'll claim that it's a little annoying to have to write your code， compile your code。

 run your code， make a change to your code， recompile your。run your code and repeat and repeat。

 It's just another step。 And indeed if it takes a few seconds， it just gets annoying over time。

 So there's other models that some languages tend to follow whereby you and I can write source code but we don't bother converting it to machine code per se。

 We just feed it into an interpreter。 And an interpreter is just another piece of software that's been designed to understand a language。

 top to bottom， left to right， if you will， and understand and interpret what it wants you to do So if it sees print。

 it's going to print on the screen。 if it see move， it's going move something around in memory。

 if it save it's going to save a file to disk In other words。

 the interpreter just going translate much like a human interpreter translating between two spoken human languages converts one input to a corresponding output。

 and long story short， this model just tends to be convenient if nothing else because you can write your code and then interpret your code。

 that is run it straight away。

![](img/f4dde6592256d1f95c23cf86a105feca_26.png)

change your code。 You can reinterpret it。 That is rerun it。

 So you eliminate this sort of middle step。 but there's gonna be a tradeoff， as is always the case。

 Interpreing a program tends to be slower than actually compiling a program and then running it。

 So it indeed might depend on your goals， which you want to optimize for。

 and yet increasingly we have this third model that we' look at here。

 whereby you and I get to write source code， we run it through a compiler。

 and that compiler converts the source code into what we generally call bytecode。

 and bytecode is just an intermediate representation。 It's not really zeros and ones。

 but it's closer to zeros and ones， if you will， which just means it's even easier to take it that final mile and get it into the zeros and ones that the machine expects。

 but what you do is you actually feed that by code not directly into the CPU but into what's generally called a virtual machine。

 A virtual machine might be something you're familiar with in the corporate world。 for instance。

 whereby you might have familiarity with。

![](img/f4dde6592256d1f95c23cf86a105feca_28.png)

s like VMware and similar where you can run windows on a Mac or you can run multiple operating systems on the same computer。

 or you can connect to a remote desktop somehow or other。

 but virtual machines are very commonly used even on laptops and desktops and phones and other devices to take as input bytecode code that someone else output it in an intermediate representation。

 not quite zeros in ones and those zeros and ones are understood by the virtual machine and the virtual machine is just always running in this case on the CPU and so it's effectively interpreting the bytecode And here's where we won't get too lost in the weeds because all of these models do have some overlap。

 I'm saying I'm using interpreted and compiling sort both in this middle column but what's nice about this middle column which is increasingly common is a lot of these steps are automated。

 So you don't actually have to manually compile your source code into bytecode you just run your code with some command or some click of a button and all of this just kind of happens automatically。



![](img/f4dde6592256d1f95c23cf86a105feca_30.png)

![](img/f4dde6592256d1f95c23cf86a105feca_31.png)

Moreover， what often happens too is the Btecode is cached that is saved somewhere on your hard drive or maybe in the cloud so that the compilation step doesn't have to happen again if you haven't actually changed the source code so in short what you're really seeing in this simple picture alone is the evolution of programming paradigms over the years where humans and businesses have realized hey。

 how can we speed up our code when it's running and how can we speed up the writing of the code before we even run it and so you're seeing an evolution of how these all work and indeed AI is just one other level of abstraction on top of this whereby you don't even write the source code you just say the English or some other human language and then somehow or other all of these other steps would seem to happen automatically underneath the hood for you。

😡。

![](img/f4dde6592256d1f95c23cf86a105feca_33.png)

So today we're going to focus primarily on Python， a very popular and relatively simple programming language。

 The goal is again， not to make you completely comfortable with the language。

 but with the ideas that it implements because the ideas that Python implements and offers to you and me as programmers is generally representative of features you would see in many other programming languages as well and indeed this is the case in general for software engineers you might take a course in learning some programming language。

 you might study a particular programming language and then another and then another but at some point you just start to teach yourself new languages as by reading documentation or asking some AI or asking some colleague or looking at other examples because once you've seen a range of programming languages。

 maybe Python among them， you'll start to notice patterns， similar paradigm。

 similar features and even though the syntax， the text that you type looks a little different。

 most of that is not intellectually interesting， it's the ideas underlying it。😡。



![](img/f4dde6592256d1f95c23cf86a105feca_35.png)

![](img/f4dde6592256d1f95c23cf86a105feca_36.png)

![](img/f4dde6592256d1f95c23cf86a105feca_37.png)

![](img/f4dde6592256d1f95c23cf86a105feca_38.png)

And indeed we'll focus today primarily on the ideas while still having some fun with the code itself along the way So this is what I want to write as my very first program in printing out hello world to the screen is sort of every programmers first program canonically but how can I actually make that happen Well of course I've just typed it on the screen here in a slide and that's fine but I should really be typing it in a better place a program that's designed to actually understand what it is I'm typing not just display and a very popular tool for just that nowadays is called visual studio code it's largely open source software backed by Microsoft that is increasingly popular。

 not just to develop for Windows computers but Max for Linux devices for phones it's a very popular text editor so to speak that shares features that are generally called integrated development environments or IDs because if you add in lots of plugins and lots of other features this program in particular can do a lot for you and there are many alternatives and you can certainly use any number of the alternatives but we for this course。



![](img/f4dde6592256d1f95c23cf86a105feca_40.png)

![](img/f4dde6592256d1f95c23cf86a105feca_41.png)

Well provide you with a cloudbased version thereof if only so that you don't have to deal with the inevitable technical support headaches of trying to install something。

 configure it， getting it to work on your computer and your version of an operating system which often tends to get in the way of actually learning the interesting stuff so we'll get you started as in the courses assignments with a cloudbased version that just works but you can also download for free tools like visual studio code onto your own Mac or PC and actually get it up and running locally without any need for internet or the course's own infrastructure and this is what we're about to see a screenshot thereof this is visual studio code as it might look if you have created a file called by convention hello pi pi py indicates that this is a file that's just text but that's written in a language called Python and other languages like C might use a do C file extension languages like Java might use Java and the like so do pi is for Python。



![](img/f4dde6592256d1f95c23cf86a105feca_43.png)

![](img/f4dde6592256d1f95c23cf86a105feca_44.png)

![](img/f4dde6592256d1f95c23cf86a105feca_45.png)

Essentially1，2，3，4 main components of the screen here。 So at the left is the so-called activity bar。

 which is essentially the menu where you have bunches of icons。

 this one being the file Exper that let you access different features of the software I'll generally hide that on my computer just to free up some space。

 but you'll see it by default over here is the so-called Expr which shows you all of the files in your account Now when I took this screenshot I had already created one such file called hellello do pi and that's why we see it right here when you first fire up Vs code for short visual studio code you might not see anything in that window or you might see even more depending on how you start the software Now up here is the actual file I created it has a tabbed interface just like today's browsers do and you have print hello world there in that file a single line of code online one Now notice it's color coded this is purple this is blue and then the rest of it is black that's not something I did manually this isn't a word processing program like Microsoft word or Google docs。



![](img/f4dde6592256d1f95c23cf86a105feca_47.png)

![](img/f4dde6592256d1f95c23cf86a105feca_48.png)

The like where I highlighted things and then chose a color from a menu。

 This is what's called syntax highlighting。 and this is one of the features of software like VS code again。

 visual studio code whereby it knows this is a python file because I told it in the file name and because programming languages are standardized with certain keywords and certain punctuation or syntax it knows that print is going be soon what we're going call a function and the blue parentheses are pure syntax that may clear what it is we want to print to the screen So more on that and more colors to come Now down here lastly is the most esoteric feature of Vs code and really programming environments in general known as a terminal window This gives you a prompt here represented as a dollar sign sometimes it looks like a hash symbol。

 or it can be anything else， but we'll standardize on a dollar sign here and this is essentially where your cursor will just be waiting and blinking waiting for you to type a command because what you're seeing down here is generally what's known as a command。

😊。

![](img/f4dde6592256d1f95c23cf86a105feca_50.png)

![](img/f4dde6592256d1f95c23cf86a105feca_51.png)

Line interface or Ci。 And even though this might seem a step backwards。

 maybe reminiscent for some of you of the old dos days before there was windows。

 it turns out that it's wonderfully useful and wonderfully efficient to be able to type commands to get worked done quickly as opposed to clicking on menus and dragging icons。

 which is fine， which is certainly much more user friendly。

 but doing things at the keyboard for many， dares say most programmers just tends to be faster and more productive by spending a lot more of your time in a command line interface or Ci。

 So the terminal gives you just that A Ci。 this whole thing， though， of course。

 as graphical in nature。 a graphical user interface or Gui for short。 So you'll see here。

 I haven't actually hit enter yet。 but I've typed out at my prompt Python space hello do pi。

 and I'm about to hit enter before I took this screenshot。 Now what have I typed here and why well。

 this is clearly the same name as the file hellello do。

 And here I am saying the word Python explicit。😊，Well。

 it turns out by design and a little confusingly， the program you use to run a program written in Python is also called Python itself。

 So if you think back to that mental model from a moment ago。

 Python is the name of the interpreter that we are using in order to run my code ultimately Now that too is a bit of a simplification。

 because there's still going to be a virtual machine involved。

 typically when you install Python on a system， but I think that's the simplest way to think about it。

 Python is the interpreter that's going to read my code top to bottom。

 left to right and interpret what I mean and what the computer should do in response。😡。



![](img/f4dde6592256d1f95c23cf86a105feca_53.png)

Allright， so let's go about doing this。 instead of a screenshot。

 I'm gonna to open up the cloudbased version thereof。

 and I'm going put it into dark mode just so that the code pops a little bit more on the screen。

 And the only thing that's different about my interface right now is that in advance。

 I've downloaded some code for this lecture specifically in a source3 folder A directory at top left。

 So in my file Expr I have source3。 and then the name of my unique code space here is these things tend to be called。

 but your number or your codespace might be somewhat differently named。 But for the most part。

 your interface will look largely the same。 you might have some more icon， some more button。

 some more features。 I've actually turned off as much as I can to actually simplify things。

 And in fact， I'm going to go ahead and hide my so-called activity bar。

 and I'm going to go ahead and hide my explorer so as to really distill our screen here into the absolute minimum room for the code I'm gonna write in those tabs and my terminal window at the bottom so I can run it。

 And sometimes at least if my code gets long， I might even hide the terminal。



![](img/f4dde6592256d1f95c23cf86a105feca_55.png)

![](img/f4dde6592256d1f95c23cf86a105feca_56.png)

![](img/f4dde6592256d1f95c23cf86a105feca_57.png)

Just so we can focus on the code alone， but with a keyboard shortcut I'll pull it back up just as you might at home ultimately too So how can I go about writing my first program Well what I'm going to do here at the bottom of the screen is run code space hello dot pi now I'm going to go ahead and hit enter and。

😡，What I'm going to see here is a blinking prompt next to the line number one。 Now。

 that number is not actually in the file。 That's just VS code being helpful and numbering my lines for me automatically。

 Now， we saw already multiple times what this program should look like。 So let me repeat that print。

 parenthesis， quote unqu hello， comma world。😡。

![](img/f4dde6592256d1f95c23cf86a105feca_59.png)

![](img/f4dde6592256d1f95c23cf86a105feca_60.png)

Close quote there at the end to be clear。 Now VS code's trying to be helpful。

 It's starting a second line for me even though I haven't moved the cursor there。 And that's fine。

 You'll find that these text editors and IDs or integrated development environments more generally。

 not only give you features like syntax highlighting color coding things for you。

 they also sometimes try to anticipate what it is you're about to type and in fact。

 what I've done is also in advance， try to disable as many of those features as possible。

 really to focus on developing today some muscle memory and some instinct for what you should type not just let the computer or AI type for you longer term once you actually have your footing with Python or any programming language。

 I think it's good to actually enable features that you to be all the more productive。

 be it AI or otherwise。 but for now we're gonna focus indeed on these fundamentals。 So that's it。

 the file has saved itself by design automatically because that's how we've configured Vs code here。

 And now it's time to run the program。 Now there's different ways to run programs。

 Sometimes you can click a little play icon。If you want or you can actually do it in a command line interface and again。

 to develop some muscle memory today and to really emphasize the steps that are happening。

 writing code and running code， I'm gonna tend to use my Ci command line interface or terminal window down here So I just ran a moment ago a code command followed by the name of the file that I wanted to code that is right that specific to VS code has nothing to do with Python per se but again I've standardized on the file name ending in dot pi If I want to now interpret this program and have it say hello world to me。

 I can do this Python space hello do pi enter andvoila I've just written and run or executed my very first python program。

 Of course， it's only ever going to say hello world So if I run Python of hello dot pi again it's going do exactly's do that again If I run Python of hello dot pi again it's going to give。



![](img/f4dde6592256d1f95c23cf86a105feca_62.png)

Exactly the same output。 Now it's fun the first time， sort of mildly interesting the second time。

 diminishing returns thereafter， not all that interesting to continue to run this most canonical of programs。

 So let's actually introduce another feature of code that's representative here of what we're going to call more generally sorry。

 did that wrong。😡。

![](img/f4dde6592256d1f95c23cf86a105feca_64.png)

![](img/f4dde6592256d1f95c23cf86a105feca_65.png)

A little overtime。Make it more interesting。

![](img/f4dde6592256d1f95c23cf86a105feca_67.png)

![](img/f4dde6592256d1f95c23cf86a105feca_68.png)

Let's make this program more interesting by introducing another function there， too。

 because we've seen already that print is apparently a function。 Indeed， it's a call to action。

 It's a verb that apparently the Python interpreter understands because that's how it printed out hello world on the screen。

 But it'd be nice if you could do more than just print out hellello world hellello world again and again。

 Well， let's introduce another function that comes with Python itself。

 And you would only know this by taking a class reading a book。

 reading up on some online resource on what functions come with a language。

 I'm going go back over to my terminal window here。

 I'm going clear my terminal just to keep things a little clean。

 but that's just erasing the commands I previously wrote。

 Now I'm gonna go ahead and introduce another feature to this same program。

 I'm going go ahead and first delete what I wrote earlier just because I think we're past that。

 I'm going zoom in a bit more just you can see this a little more clearly。

 And what I'm gonna do now is go ahead and type input。

 which is gonna be the name of a function that indeed comes with Python。

 I'm going use quotes inside of these parentheses。😊。



![](img/f4dde6592256d1f95c23cf86a105feca_70.png)

![](img/f4dde6592256d1f95c23cf86a105feca_71.png)

To then prompt the user with a question。 For instance， if I want to prompt the user。

 say for their name， I could say what's your name question mark。

 I'm going to leave a space at the end so that the cursor moves over ever so slightly。

 then I'm going to go ahead and print out quote unquote hello comma。😡。

Then I'm going to go ahead and print out at the bottom。😡，What do I print？ Well。

 maybe it's David who's gonna to run this program， So maybe I could print out quote unquote David as the answer to that question。

 but that doesn't really make sense。 The whole point of this program I claim is to make it more dynamic and more interesting than just hello world and certainly more interesting than hello David。

 hello David and the like。 So what I'd like to propose is that this input function。

 which I claim is going to ask the user that question。

 I'm going to make sure that I save the answer to that question somewhere。

 and I'm gonna type something like this name equals input parentheses quote unquote what's your name。

 And this equal sign， is actually something you shouldn't think of as equality as much as you should assign in programming languages like Python。

 This equal sign means do whatever is on the right-hand side first。

 and then copy that value from right to left and store it in this thing here。

 Now what's this thing I came up with this word myself。

 but it makes sense because I'm prompting the user for their name。



![](img/f4dde6592256d1f95c23cf86a105feca_73.png)

![](img/f4dde6592256d1f95c23cf86a105feca_74.png)

![](img/f4dde6592256d1f95c23cf86a105feca_75.png)

have called this thing anything I want because it's a variable。

 a variable is a storage container for a value。 be it a piece of text or something else。

 I could indeed call it anything I want mathematicians like X's and Y's and Z's。

 But it would be a little less clear to the reader and to me tomorrow or a few days from now。

 what it is that's in that variable， if I just call it X or Y or Z。 So by convention stylistically。

 it's good practice when programming to give your variables good names。

 And that just makes it clearer to you， the writer and to future people， the readers thereof。

 Now online line2， I've gotten ready to say hello comma。

 So I've got my English grammar set up Now what I can do down here is call print again and pass to it another input。

 which is going to be。

![](img/f4dde6592256d1f95c23cf86a105feca_77.png)

The variable itself named however I saw fit。 What's going to happen now at the end。

 If I go ahead and run Python of hellello D Pi again and hit enter。

 Now I'm not going to see hellello world。 I'm going to see what's your name and a space。

 and then my cursor where I can type my name。 So now I'm going to go ahead and type in， for instance。

 David， enter and I'll be greeted with dynamically hello comma David。

 If someone else were to walk up to the keyboard and run this program again。 Python of Hello D pi。

 perhaps it's our old friend John Harvard。 while John might type in his name。 and then hit enter。

 And now we see hello John。 So what we've seen as an example here are not only variables。

 but what we're also going call parameter。

![](img/f4dde6592256d1f95c23cf86a105feca_79.png)

Let me see， give me one second to fix this。Yeah， that's what' going to be part of the exercise next。

So what we've seen here are not only variables， but what we're going to call argument。

 do I want to do that arguments。Yeah， let me fix this。

So what we've seen here are not only variables but what we're going to call arguments。

 arguments are inputs to functions that alter their behavior and syntactically the way you provide an argument to a function is just as we have now several times inside of those parentheses after the functions name you provide the input there too quote unquote hello world quote unquote what's your name or no quotes and the name of a variable indeed those quotes are clearly now important when you just want to use English or some other human language and have that display on the screen。

 you need to encase it in quotes， double quotes as I did。

 you can also use single quotes if you prefer， so long as you don't have any apostrophees or things that might confuse Python thereafter。

 but if you provide those inputs in quotes that makes clear to Python that oh you want me to print out this whole thing and it won't confuse that input for what could actually be a variable instead In fact I did not use the quotes around name because again name is a storage container for the value the user previously typed in。

😡，So I want print to print out the value of that variable， not quote unquote name per se。

 but I do think， and I admit the aesthetics here aren't the prettiest。

 In fact you can see hello comma John on two separate lines which isn't all that elegant let me go ahead and propose that we kind of clean this up sort of visually on the screen and we can do this in a few ways and let me propose one of the simplest first if I want to keep the hello comma John and the hello comma David on the same line。

 let me change my code a bit just for clarity， I'm going to clear my terminal window just to hide the previous command。

 I'm going to get rid of line3 altogether and then up here inside of the parentheses on line2。

 I'm going to use the plus operator so to speak the plus sign as we know it for math and then I'm going go ahead and type the variable name there。

😡。

![](img/f4dde6592256d1f95c23cf86a105feca_81.png)

Now， my program's a little shorter， but it's actually a little better as follows。

 Let me go ahead and now and run Python of hello do Pi and hit enter。

 I'll be prompted again for my name。 So I'll type in David enter。

 And I think I should see on one line， so close。 hello comma David without a grammatical space in there。

 So I think that's an easy fix。 And in fact， it stands to reason that it stands to reason that the space is missing because I didn't tell the computer what to do。

 And here is just the simplest stupidest example of why precision is so important in programming。

 The computer is meant to do exactly what you tell it to do。 And unlike pseudocode。

 and unlike humans who might read that pseudocode， who might read between the line so to speak and make certain assumptions about what you mean because you're they're just a reasonable person。

 the computer is only supposed to do and is only designed to do exactly what you tell it to do。

 So if you oit the spaces I did it's not going give you a space。 So that's fine。

 I'm going go ahead and hit the space bar now inside of the quotes no other。



![](img/f4dde6592256d1f95c23cf86a105feca_83.png)

![](img/f4dde6592256d1f95c23cf86a105feca_84.png)

Changes I'm going to rerun Python。Of hellello Dpa and hit En。

 type in my name again and now we're back in business。 Hello， comma David。

 exactly as I intended it all this time。😡。

![](img/f4dde6592256d1f95c23cf86a105feca_86.png)

Well， what more could I do here Well， it turns out that some functions take multiple arguments and print is one of them。

 We've seen that we can pass print one argument， and that was true of the input function2 but what's nice about print is that you can pass in two arguments3。

4 more even zero if you really want。 So let me go ahead and do just that let me go back to VS code here and point out that what's been happening thus far is this plus operator is doing something for which we have a term of art。

 it's doing concatetnation。 concatetnation is the joining of two pieces of text， one on the left。

 one on the right and the one on the left is clearly text because it's in quote the one on the right is the value of the variable which we know is going to be text like D VID or JOHN for either of our names and so this concatenation operator is doing this。

 it's taking hello， it's taking the name， joining them together that is concatenating them together and that is the argument。

😡。

![](img/f4dde6592256d1f95c23cf86a105feca_88.png)

That print is receiving as input and therefore displaying on the screen。

 But because I've read the documentation， I can actually change this to pass print two arguments。

 and maybe just kind of clean this up a little bit。 let me go down to my terminal here。

 run Python of hellello do pi now， noticeice there's no plus operator。

 But there is another comma hit enter。 what's your name D I and so close， now again。

 the computers taking me very literally。 why Well I still have the space here。

 but it turns out if you dig into the documentation for the print function。

 you'll see actually that when you pass in not one but two arguments to the print function。

 you'll get a space for free。 it is designed when you pass in two or more arguments to separate them by default with a single space。

 I would only know that from having been told it reading the documentation or the like。

 So that's fine。 I can fix this by reverting to the original version because now I'm getting the space automatically by nature of how the function works。

 So if I run this one more。

![](img/f4dde6592256d1f95c23cf86a105feca_90.png)

Python of Hello D Pi enter， type in my name David， now it looks exactly as I intend。

 and all we're doing now is demonstrating that you can have not just one but two or three。

 or it turns out as we'll eventually see even zero arguments as well。😡。



![](img/f4dde6592256d1f95c23cf86a105feca_92.png)

Allright， so how would you know any of that， I keep referring to the documentation。 Well。

 among the nice things about Python is that it is actually very thoroughly documented。

 And if you go to this URL here， you can see the official documentation for Python。

 which actually evolves over time as the language itself evolves and gains new features and therefore newer version numbers as well。

 And I took a look at that documentation at some point。 I'm like， oh。

 the print function does take multiple arguments if I so choose， and that's how I knew to do that。

 In fact， I also know as a result， that I can do this too。 If I want to move the。😊。



![](img/f4dde6592256d1f95c23cf86a105feca_94.png)

![](img/f4dde6592256d1f95c23cf86a105feca_95.png)

![](img/f4dde6592256d1f95c23cf86a105feca_96.png)

Pnting of the name to its own line。 I can do that。 I didn't have to abort altogether what was my line3。

 If I would really like to pass in name as the variable to as the argument to my function print。

 that's fine。 but recall that previously this did not work out well for us where I simply had the space and then nothing after it because it put hello comma here and then the name David or John on the second line。

 But if I read the documentation， I'll actually see that I can pass in another type of argument。😡。

To the print function2。 I can use my comma again。 I can say end equals and for instance。

 quote unquote because it turns out again， per the documentation。

 the print function will end every line of text automatically with a new line。

 And we actually glimpsed this ever so briefly in the assembly code earlier。

 it turns out in programming。 the way you express a new line。

 the hitting of the enter key or the return key on your keyboard is you sometimes don't have to hit it。

 you can textually write a backslash and then a lowercase n。

 and Python and other languages know that oh， the human wants me to move the cursor to the new line。

 the next line below it。 by default， the documentation for print says exactly this that the line will end by default with backslash and。

 that's why the cursor gots move and made hello comma David and hello comma John kind of messy。

 But if I override that and say no no no no， end each line with nothing。

 unqu with nothing in between， I can change that behavior too。

Let me go ahead and run Python of hello pi again， type in my name and it's not going to be that exciting an outcome。

 It's still going to look the same way， but it's going to achieve the exact same result yet another way and this too is thematic in programming whereby simply by writing code in different ways you can in fact achieve the same outcome not unlike in English where you can express the same idea in different ways using different nouns and verbs and the like some of them better some of them worse but in code here we can indeed achieve and solve the same problem in many different ways now over time and if you study programming and aspire to be a software engineer you'll learn that there are in fact better ways to write some code because not only is code evaluated typically on the quality of its style like your choice of variable names and whether or not it's pretty to read and you've used whitespace that is spacebar characters in appropriate places well it stands to reason that it's got to be correct。

 otherwise what's the point of writing it if you're not actually solving the problem correctly but design。

😡。

![](img/f4dde6592256d1f95c23cf86a105feca_98.png)

![](img/f4dde6592256d1f95c23cf86a105feca_99.png)

![](img/f4dde6592256d1f95c23cf86a105feca_100.png)

Another seemingly subjective measure of code quality。 And in fact。

 this is why a lot of companies in the real world actually have what are called code reviews。

 whereby when you write code that you want your company to use in its product。

 typically therell be another human or nowadays in AI that at least gives you some qualitative feedback on it and says you could maybe do this a little better。

 it will give you suggestions it might approve or even deny the submission of your code to the system。

 So writing good code is not only correct but a matter of design as well。

 And so what we're seeing here， sorry， let me add one more slide on the fly here。Now。

 what we're seeing here in my code is a use of arguments indeed。

 but the first of these arguments is what we're going to now refer to as a positional parameter。

 It is an argument that has meaning because it came first in this case， if you will。

 This argument though is what we're going to generally call a named parameter。

 the word end exists because the human who invented the print function in Python decided that there will be a parameter whose name is E and D。

 the value of which by default is backs slash N， the new lung character。

 but that we can change in this way， so this is a long way of saying that Python supports。

 whoop can't flip over from over here。😡，How can I fix this？

So this is a long way of saying that Python supports not only what we'll call positional parameters。

 but also named parameters as well。 And this is a bit of a subtlety。

 but when you know a function takes inputs， it is said to take parameters。

 When you actually use those parameters by passing in values， you're passing in arguments。

 So when you invent the function， they're called parameters， but when you use the function。

 they're called arguments。 But for the most part， they refer to one in the same thing and humans will often slip and use them interchangeably as well。

 Now， let me go back to my code here and propose that we can solve this yet， another way， in fact。

 maybe the best way， if you will， or the most conventional way。 let me clear my terminal here。

 and let me go back up to this line of code and 93 and get rid of both and propose that we actually do all of this in one elegant line。

 I'm going go ahead and print quote unquote hello comma and then let me just print out the person's name like this。

😡。

![](img/f4dde6592256d1f95c23cf86a105feca_102.png)

I like this because it's keeping everything on one line。 I've got the hello comma。

 I've got the variables name。 Let's go ahead and run it。 Pyon of hello dot pi enter D VId。

 some of you might see already where this is going and even if not think for just a moment about what I might have done wrong online too you're about to see the first probably many bugs mistakes in software intentional or otherwise。

 because when I hit enter now I'm not going to see hello comma David。

 I'm going to see literally hello comma name Now that stands to reason because I literally put an AME inside of those quotes。

 but there is a way to fix this it turns out and this is a newer feature of Python。

 I can put in curly braces as they're called the name of that variable which coincidentally is name。

 but again I could have called it X or Y or Z that just would have been bad style。

 but I now need to make one other change because if I run this version of the program and type my name。

 Pyth's still gonna take me literally and this time weirdly print out hello comma name in curly braces。

😡，I need to tell Python that this text is actually a little bit special。

 and I want it to format the text for me。 I want to go ahead and specify it before the double quote here a letter F notice that the curly braces actually changed color because VS code knows what I'm up to So now I'm gonna run this a third time Python if hell pi type in my name and now I get hello comma David So this is a very subtle detail this F that I'm putting before the string and frankly after programming all these years。

 I think this is a weird looking feature， it still feels very unnatural to me to squeeze a letter F in between the parenthesis and the quote but this is a feature that's been adopted for some time and is the way that you can use what are called format strings in Python Now what more can we do with this program。

 we can actually now that we have some of these basics in mind we can actually kind of add more feature still let me clear my terminal window here and let me propose that if I run this a bit lazily maybe with my caps lock keyon I might do something silly like this。

kind of know someone in our lives that tends to write in all caps。 This just looks bad。 And in fact。

 if this isn't a silly little program， but it maybe a form on a web page from which I'm collecting data from users like I don't want some users names。

 capitalize properly， some all uppercase， some all lowercase。

 it would be nice to maybe canonicalize standardize what the capitalization of these texts are So I can actually do that in a few ways and also solve other problems。

 For instance， suppose I'm really difficult。 And when I run this program。

 I weirdly type the space bar three times and then I type in my name and then I hit the spacebar again in mailin。

 So not that I would do this， but you'd be surprised we collect a lot of data for this course in others。

 so many people weirdly hit the space bar before they start typing or after and what this is going to do in this case is kind of mess up the appearance of this when you spit it back out with the print function。

 So I can clean up some of these mistakes pretty easily。 let me actually go up to my code here。

 Let me actually specify the。

![](img/f4dde6592256d1f95c23cf86a105feca_104.png)

![](img/f4dde6592256d1f95c23cf86a105feca_105.png)

Following let me go ahead and give myself another variable。 We'll call it new name。

 but I'm going to clean this up further too。 I'm going to set this equal to the name function the name variable。

 But I'm going to go ahead and use a dot and the word strip and then to parentheses。

 This is another function called strip that weirdly for now。

 you call that is invoke or use by using a dot on whatever value you want to strip white space from and by white space。

 I mean， the space bar， the tab key or certain other characters as well。

 But this is going get rid of spaces to the left and to the right of what the human typed in。

 because this is gonna partially clean up that mess。

 If I run Python of hello do pi type in space space space。

 David space space space mail and enter notice that。H， nothing happened here。

But this too stands to reason， and I didn't intend to make this mistake。 This stands to reason why。

 because the name variable I'm printing is still called name。

 If I want to print out the new variable name， I want to change what's in the curly braces to new name。

 And to be clear what's happening online line2 is a little new， but not entirely new。

 The strip function here is new and it's operating on this variable called name。

 but the equal sign is not new。 that's the assignment operator， that means copy from the right。

 the stripped version of the name over to the left。

 And the thing on the left now is another variable whose name I invented。

 I could have called it X or Y Z， but I gave it a slightly better name than that。 And now on line3。

 I'm using that variable value。 let me go ahead now and run Python of hello dot pi enter type in spacespacespace David Spacespacespace mailin。

 And at least now solved the problem partially。 But suppose the user is a little difficult and runs that program again。

 and in fact， it's getting a little tedious to keep running Python of hello dot pi。

 So you can actually use your。Up arrow on money aboards。

 whereby you'll scroll back in time through your history of commands。

 So if you ever see me typing seemingly instantly， I'm just using the up arrow。

 maybe the down arrow or some other tricks to rerun some past commands more quickly。

 So now I'm going go ahead and enter。 I'm going do spacespace space。

 I'm going yell David mailin enter and that too looks pretty stupid。 How can I go about fixing this。

 Well， there's another command another function I can use。

 let me do this and well clean this up soon newer name equals the new name dot title open parenthesis closed parenthesis。

 That is to say it turns out that Python also comes with a title function that you can use on variables like this。

 such that if their text， you're gonna to get title case back instead and title case is like on the cover of a book where the first letter of every word is capitalized automatically for you and everything else is forced to lowercase if only the standardized capitalization in your system。

This now look， well， let me go ahead and rerun using the up arrow trick enter。

Type in spacespacespace， all caps， David Main enter。 and now darnnet， I did it again。

 How am I getting the same thing。 Well， I need to print out newer name。

 let me now go back down to my terminal run Python of hello uppa yet again。

 Spacespaceb David Main enter。 And now it's getting more interesting。

 I haven't fixed all of the problems。 and we'll leave one is maybe an at home exercise。

 but I've at least standardized what the name looks like。

 So if I'm storing this in a database or in some server somewhere。

 it's at least going to be cleaner than the all capitalized version or even if the user typed no uppercase characters。

 it would automatically capitalize the D and the M again。

 Now I can clean this up and this is not good practice what I'm doing， creating a new variable。

 a new variable every time I change something， I can actually do a little bit better than this in a few different ways。

 but the simplest is to notice this。 If you sort of draw some inspiration from transitivity or certain mathematical operations。

 you'll see that name is going contain as a variable this whole time。 the value that。

Tyd in and that name already has a strip function associated with it。

 but so does the text that the human typed in。 So instead of calling strip down here on line2。

 let me actually go and delete all of line2 and at the end of line1 let me put the dot there。

 then run strip open parenthesis closed parenthesis and notice you still need the parenthses because I'm calling that is using a function but strip it seems doesn't take any input in those parentheses。

 it takes no parameters if you will but it knows what to strip whitespace from because of that dot operator which is referring to the value right before it and I can do one better than this I can get rid of this line and go back to line1 and add dot title and I can kind of chain functions together in this way。

 which is just if nothing else tightening up my code。

 it's getting rid of like those stupidly named additional variables that weren't really adding much intellectually to my program and I'd argue that line1 is still pretty short。

 it certainly fits on my screen roughly half of the screen So I haven't really made my code harder。



![](img/f4dde6592256d1f95c23cf86a105feca_107.png)

![](img/f4dde6592256d1f95c23cf86a105feca_108.png)

for other people in the future to read and understand。

 so I kind of like this and now I can go back into line two and tighten this up。

 just print out the name so that down here， if I clear my terminal and rerun Python of hellello do pi。

 type in if I want Spacespacespace， David， Spacespacespace， mailin and all caps。

 it's at least going to improve some of those problems here。😡，But here's the catch with programming。

 Sometimes good intentions might not yield the best result。 And in fact。

 I can probably contrive an input for which this is not going be the intended behavior。

 let me go ahead and clear my terminal again， run it here。

 and maybe let's type in a character like Ronald McDonald All interesting only inofar as its name has three capital letters here。

 which is fine。 Ronald McDonald typed his name correctly， I'd argue in this case。

 but as soon as Ronald hits enter， notice what this program does。

 So so close but there's gonna to be this tradeoff sometimes you might have fixed one problem。

 but you've introduced another kind of the wackham old game if familiar。

 I've sort of fixed it over here。 but Darnet now there's a new problem over here。

 And there's absolutely ways to fix this。 but I would encourage you as you exit this lecture ultimately to keep an eye out in the real world for weird behavior like that。

 because it just means that some human like me made a mistake and introduced a bug into their code that didn't actually work。



![](img/f4dde6592256d1f95c23cf86a105feca_110.png)

![](img/f4dde6592256d1f95c23cf86a105feca_111.png)

![](img/f4dde6592256d1f95c23cf86a105feca_112.png)

As they intended Now， how do you know about strip and title and all of this。 Well。

 it turns out in that same documentation， you can look up all of the documentation for functions related to text and henceforth。

 I'm gonna to start calling text by its term of art strings or STR for short and in fact。

 that's why you see STR in this particular URL。 if you go to that URL。

 you'll see all of the functions that are associated with strings in Python strings of text。

 if you will， strip and title among them。 But just for fun。

 let me go back to V S code here and just show you a couple of other things that we might do。

 for instance， if we wanted to not only strip out the white space。 at least from the ends。

 I still haven't figured out how to get rid of the white space between David and mein Str does not do that for me。

 let me go ahead down here after clearing my terminal and propose that I'd really like to greet people very familiarly by their first name only even if they type in their full name。

 Well， I can do that online here， let me insert a blank line and do this let me go ahead and say give me a。



![](img/f4dde6592256d1f95c23cf86a105feca_114.png)

![](img/f4dde6592256d1f95c23cf86a105feca_115.png)

called first， Give me a variable called last， Separating them by commas and Python and set both of those equal at the same time。

 which Python can do for me， too， to name dot split and split the human' name on a single white space。

 So for now， the human's gonna to have to cooperate no more hitting lots of space bars and weird areas。

 But now what I'm going to do is instead of printing out the whole name。

 I'm going to print out just the first by grabbing this variables value， but ignoring this one。

 and split。 if we read its documentation in Python's own docs。 you'll see that it will split。

 of course， on a single space and give me， hopefully in this case， two variables， values back。

 Python of hello do Pi enter David Main， I'll cooperate and just capitalize everything with good spacing。

 Hello David， isn't that nice that it's treating me as as a friend already。 So here too。

 a lot of things can go wrong， your mind is probably wandering to friends of yours。

 maybe your own name that has three words in it or more。



![](img/f4dde6592256d1f95c23cf86a105feca_117.png)

Might not necessarily work as we intend， but at least we've got things going with additional features now as well。

 And in fact， as a teaser turns out that Python doesn't support just these strings of text or STR for short Python and a lot of languages support different types of data as well So here for instance。

 is a brief list of just some STR which stir for string but python and other languages also support what we're going to see as ints or integers。

 bos for boolean values， not Boolean expressions in this context， but boolean values。

 namely true and false， and that's it floats which refers to what are called floating point values。

 which are real numbers that have a decimal point in them and possibly digits after the decimal point。

 and then there's a bunch of others as well。 In fact。

 among the others as we're going to see is not just boolean values， floating point values。

 integers and strings， but also ranges which is going to give me back a range of numbers from one to another number lists of numbers。

 tuples， tuples might be like x comma。😡。

![](img/f4dde6592256d1f95c23cf86a105feca_119.png)

![](img/f4dde6592256d1f95c23cf86a105feca_120.png)

I or latitude comm longitude combinations， dis or dictionary objects。

 which associate keys with values， as you might recall。

 from our discussion of data structures and sets like in math。

 we'll contain a whole bunch of values but no duplicates by default。

 So Python supports all of these different types of values。

 Let's actually start to play with some of them here。 Let me go back to VS code。

 and let's transition to a new program altogether。 I'm going to close my hello hello do pi tab。

 I'm going to clear my terminal window and let's go ahead and code up a brand new file instead。

 I'm going code up a file called calculator pi。 and let's make our own mini calculator just to play around this time not with strings or stirs but ins or integers。

 Allright here we go。 This time I think it's appropriate to use simple variable names like X and I'll set it equal to one for the sake of discussion。

 Y set it equal to2 for the sake of discussion。 Let me give a third variable called Z。

 I'll set it equal to x plus Y。 and then I'm going print。



![](img/f4dde6592256d1f95c23cf86a105feca_122.png)

Out the value of Z。 So it's a super simple calculator。

 All it does is add these two numbers together and then print them out。

 but it's going illustrate how we can manipulate integers indeed as well。

 noticeice that in this case， the plus is hopefully going to do math in the intended way and indeed you have plus you have minus you have division。

 you have multiplication in other mathematical operator supported in Python。

 Let me go down here now and run Python of calculator dot pi this time。 My new file hit enter。

 and my first calculator seems to work。 I dare say3 is the correct answer to that problem。

 Now this calculator doesn't do all that much of interest yet。 It's only ever gonna to add one and2。

 let's get some input from the user and make things more interesting。 So up here。

 instead of the one instead of the two， let's use our old friend。

 the input function and ask the user What's X question mark space。

 And down here use the input function and say what's y that is to say let's make a very user friendlyly calculator that。



![](img/f4dde6592256d1f95c23cf86a105feca_124.png)

![](img/f4dde6592256d1f95c23cf86a105feca_125.png)

The Hu in what input they want。 Then down here， I can still add x plus y and set it equal to z。

 I can still go ahead and print Z。 So let's run Python of calculator do pi again。

 This time I'm prompted for x。 And just to prove that it still works， let's type in one for x。

 And now two for y。 And when I hit enter Z will get the value， presumably the hurry。



![](img/f4dde6592256d1f95c23cf86a105feca_127.png)

what's going on here， I seem to have yet another one of these bugs， mistakes in my code。

 like suffice it to say1 plus 2 is not 12 and never has been。So what's happening？ Well。

 it's no accident that we're getting。12 because it's not really 12， It's really 1，2。 In fact。

 if you go back up here and you think about what we did in hellello dot pi when we used the input function。

 we were asking the human for text。 That is to say a string and storing it in a variable。 previously。

 the variable was called name。 Now it's called X。 But that doesn't change the fact that it still came from the keyboard。

 And therefore it is text。 Sam for Y。 Sam for Z as a result。

 This plus is not going to be the arithmetic plus operator from grade school math。 it's going to be。

 again， that concatenation operator。 It's the right symbol。

 But in the context of having a string to the left and a string to the right X and Y respectively。

 it's going to join them together。 instead of actually adding them together。



![](img/f4dde6592256d1f95c23cf86a105feca_129.png)

So how do we fix this Well， we can do this in a few different ways but we need another function and it turns out Python also comes with an int function named after the data type。

 which will allow me to pass in an argument that is a string and get back the corresponding number So if you will per our discussion in the very first lecture it's gonna convert a uncode text to the corresponding number that you see。

 not necessarily a to 65， but rather the number that you're seeing on the screen or that the human has typed in So let me go ahead and write int open parenthesis closed parenthesis around the x int open parenthesis closed parenthesis around the y Now let me go down here。

 rerun Python of calculator do pi I'll again type in one。

 I'll again type in two and this time I get the intended value of three here too let's tighten in this up let's make this a little better because frankly I don't really need to do this on line4 if I'm trying to store in x a numeric value。

Why don't I go ahead and do this， Let me revert this change I just leave this as x plus y because that's arithmetic but up here let's do this for the first time。

 let's pass as input to one function， the output of another function by nesting them in this way let me do the same online to and let me call your attention now to the additional parentheses inside of the parentheses is first and foremost what's x question mark quote unquote that's the input no pun intended。

 the input function。 However， the input function we've seen returns whatever the human typed in at the keyboard that value instead of immediately getting copied from right to left is going to immediately be passed in as the input to this input function。

 so that it can convert it per its documentation to the corresponding actual integer same is going to happen down here for y so what's now in x and y respectively are two ins not two stirs so to speak they look the same。

😡。

![](img/f4dde6592256d1f95c23cf86a105feca_131.png)

![](img/f4dde6592256d1f95c23cf86a105feca_132.png)

But they're going to be treated in a way that lends themselves now to correct math。 Now。

 all I've done here is really tighten things up by not using int Online 4。

 but if I again run Python of cculator pi typing in one and then two， I'm still going to get three。😡。

And I still have the same result Now， what if I want to add other numbers together。

 Well I can actually do this with floats as well， if I want to add numbers with decimal points。

 I can change int up here to floats， I can change int up here to float。

 And now after clearing my terminal， let me rerun Python of calculatedculator up high and let's do 1。

1 plus 2。2， now I'm going to get back 3。3。😡。

![](img/f4dde6592256d1f95c23cf86a105feca_134.png)

![](img/f4dde6592256d1f95c23cf86a105feca_135.png)

And that looks correct， too。Or does it？The astute might have just noticed that wait a minute。3。

3 is correct。 And I see a lot of zeros。 but then way over here， there's this weird anomaly。

 which I did not learn in grade school math that 1 plus1 plus2 plus 2 should equal。 I would think 3。

3， and that's it。 But we seem to have a curiosity there。 That's happening。

 And let let's see if we can't dig into that。 In fact， let me go back to my code up here。

 let me go ahead now and maybe we can ignore the problem。

 let's go ahead and just round this result first。 So it turns out that Python comes with a round function。

 you can find it in its documentation such that now if I run Python of calculator pi with 1。1 and 2。

2 should be 3。3， but if round it， it's3。 All right。

 so I'm kind of like ignoring the problem by just rounding away from it。

 but that's not really legitimate。 It is an opportunity to tighten this code a little bit more。

 I don't really need frankly Z anymore。 if I already know what the value is x plus Y round it or not。

 Let's tighten this up。 And let's just pass。

![](img/f4dde6592256d1f95c23cf86a105feca_137.png)

To print as before the output of one function round as the input to the print function。

 It doesn't change the behavior， but it gets rid of a third and seemingly unnecessary variable that was Z a moment ago。

 let's rerun this down in my terminal again run it as 1。12。

2 and we're still got R 3 but the program's a little tighter this time around but let's now do this。

 let's actually format it with some commas in a useful way。 for instance。

 if I run this program as is and let's go ahead and run like 999 this time plus one I'm going get back 1000。

 but in the U it's comm to separate triples of digits with commas in other countries you might use dots instead。

 but in this case it's going to use whatever the default is on my system if I make this change instead of rounding here as before let's give me back my z just so I can see this more clearly then I'm going to go ahead this time and print out quote unquote and this is。



![](img/f4dde6592256d1f95c23cf86a105feca_139.png)

Look weird The value of Z inside of curly braces。 and I'm going to specify a Python that I want you to format this variables value with the little f aka format string。

 let's rerun thisython of calculatedc up pi 9，9，9 and 1 still working as intended。

 So I really just made it look uglier and weirder for no good reason yet turns out if you read the documentation。

 you'd know that you can actually include a bit not obviously， a colon after your variables name。

 And then a comma， if you want the print function to format it beautifully for you with those commas。

 for instance。 So let me go ahead and rerun this now，9，9。

9 and  one now I get a formatted integer 1000 with a comma。 And again。

 whether you get a comma or some other symbol will simply depend on how your systems configured。

 All right， let's now dig into not just addition but another operator。

 I claim that we can do multiplication subtraction and also。



![](img/f4dde6592256d1f95c23cf86a105feca_141.png)

![](img/f4dde6592256d1f95c23cf86a105feca_142.png)

Division， let me clear my terminal window here。 Let me go ahead and simplify this just for the moment to say print。

😡，To say print of Z itself。 But instead of rounding x plus y。

 let's just do something simple like x divided by y。 Make sure that division indeed works。

 as I claim。 Run Python of calculatedc up pi。 let's do one third。 So  one divided by 3。

 That's looking pretty good。 All right， I don't know what was going on with that errant 3 a moment ago when we added 1。

1 plus 2。2。 But problem seems to have gone away。That's not really the best approach to programming。

 like if something happened once， probably eventually going to happen again。

 but we're going to have to poke around further to see what's going on。 So for instance。

 let's do this just as before。 let's really dig into what is being calculated when I do one divided by3。

 Let's not just print the Z。 Let's print out a formatted version of the Z as before。

 and as of now that hasn't changed anything， let me do the colon。

 but instead of doing the comma thing now because I don't really care about big numbers for now。

 let me specify that I want to see only two decimal digits，2 F。 Now this is cryptic and frankly。

 I still to this day， have to look up the syntax for formatting numbers to a specific number of decimal places。

 and it actually does vary a bit by language。 but this is telling the print function to format Z to two floating point values。

 So two significant digits after the decimal。 Let me go ahead and run Python of calculated up pi。

 Let's do one。 let's do3。 I should get zero point。

![](img/f4dde6592256d1f95c23cf86a105feca_144.png)

3，3。it didn't。 Sorry， let me fix this。In Po。

![](img/f4dde6592256d1f95c23cf86a105feca_146.png)

It's not going to look any different just yet。 but let me go in here and use a colon rather than use a comma now because I don't care for now about large numbers anymore。

 Let me do a dot2 F， which is syntax that's going to tell Python to format the value of z using a decimal point and two digits thereafter。

 and the F in this context confusingly means it's a floating point value。

 The F out here before the double quotes recall just means hey Python here comes a formatted string。

 Allright， if I go down to my terminal here and rerun Python of calculator dot pi 1 divided by3。

 This time I only see the two decimal points。 But I did this because I wanted to kind of poke around further and see more digits by default。

 we got a few without using this formatting trick。 Supp I want to see a lot of digits like 50 digits after the decimal point。

 Let's really dig into what one third actually is。 if I do one， I do3。😡。



![](img/f4dde6592256d1f95c23cf86a105feca_148.png)

Oh my God。 So what has just happened here。0。3333333。 I'm on board at this point。

 Like this feels like one third and how I was taught in grade school。

 What the heck is this going on at the latter half of the digits。 It's just random noise。 Well。

 this is actually a fundamental problem with many programming languages， if not most。

 whereby they' vulnerable to what we'll call floating point imprecision。

 whereby even if you're doing a relatively simple arithmetic operation like one divided by three that we all know is 0 point3 with a line over it。

 which means an infinite number of threes， Well， there's part of the problem。

 we can't really represent an infinite number of digits。

 if we only have a finite number of bits inside of the computer。 In fact。

 if you think back on that chip of memory， no matter how many bits are in there。

 theres certainly finite。 there's only so many bits。

 So we certainly can't use an infinite number of bits to give us an infinite number of threes。

 But this doesn't just happen to。

![](img/f4dde6592256d1f95c23cf86a105feca_150.png)

![](img/f4dde6592256d1f95c23cf86a105feca_151.png)

![](img/f4dde6592256d1f95c23cf86a105feca_152.png)

Numbs that recur infinitely many times in this way。

 This really happens to an infinite number of numbers。 And if you think about it。

 if you only have a finite amount of memory， but in the real world。

 there's an infinite number of numbers。 Certainly real numbers that have decimal points because you can always add another digit。

 another digit to come up with more。 it just stands to reason that if you have a device with finite memory。

 you cannot represent infinitely many values。 at some point。

 you have to decide I cannot represent data to that level of precision。

 And that's what you're seeing here。 Python in this particular case。

 it give us a whole bunch of significant digits， but it cant give us as many as 50。

 it would seem at that point， it essentially starts rounding to the nearest value that it can represent。

 And that's because of the underlying representation of binary digits using indeed zeros and ones e here as a fraction as we see it here。

So what does this mean， It means that computers are inherently vulnerable to imprecise math。

 They can and will make mathematical mistakes unless you somehow defend against this。 In fact。

 there's many examples and popular culture of movies of digits being rounded incorrect correctly yielding lots of payoff for the characters。

 There's lots of examples in the real world of sometimes very perilous implications of mathematical operations。

 meaning that devices， misbehave or operate incorrectly。

 this is simply the nature of the beast when it comes to representing information at the end of the day。

 with just a finite number。😡。

![](img/f4dde6592256d1f95c23cf86a105feca_154.png)

![](img/f4dde6592256d1f95c23cf86a105feca_155.png)

Of zeros and ones。 So best to use some piece of software that gives you enough precision。

 best to use as many bits as you can， but not to expect an infinite number。

 This is not a bug with Python。 This is a limitation of computers with finite resources like these and how we are representing in binary the underlying numbers。

All right， before we transition to some of those other building blocks beyond functions。

 let's play with just a few other features by going back to my terminal window here and clearing it。

 Let's actually go back to hello do pi。 and I can do that by using that same code command as before or to be clear。

 if I reopen my explorer， notice I have not only the folder I came with today。 source 3。

 I also have hello do pi， which we made earlier as well as calculated pi。

 So instead of using the code command again， I can also just click on this like any Mac or PC。

 But let me go ahead and close my Expr again。 let me delete the command I was about to run。

 and let me propose that we can actually implement our own functions to。

 and that'll put a cherry on top of this discussion of functions。

 I'm not limited to only those functions that Python has given us themselves。

 rather I can invent my own。 For instance， if I'm running a program like this。 name equals input。

 quote unquote what's your name。

![](img/f4dde6592256d1f95c23cf86a105feca_157.png)

Question mark。 Well， I can go ahead and maybe say hello to the user like this。

Then I can go ahead and print out their name。 So wouldn't it be nice if Python came with a hello function that just said hello comma。

 or however I want to format it。 Unfortunately， if I run this Python of hello do pi。

 it's gonna give me an error And I'd like to avoid that error because in this case When I type in my name。

 David， I'm gonna get back this name， error name hello is not define。 Did you mean help。 I mean。

 ironically， I kind of do mean help now， but hello does not exist。

 doesn't come with Python but that's okay because I can define this function myself。 In fact。

 let me move my cursor to the top of the file。 and at the very top of the file。

 let's go ahead and use a new keyword that comes with Python called def for define。

 let me define a function called hello by saying the name I want to invent to empty parentheses in this case。

 and then a colon。 and then on the next line， indented four spaces by convention and notice I didn't have to hit the spacebar VS code is smart enough and we've configured it to know that I want to indent automatically for spaces that whenever you call hello。

I want you to say。Print quote unquote， hello， and I can toss the comma in there。

 but I'm just gonna yeah I'll tos the comma in there as before。

 If I now go down to my terminal again and run Python of hello do pi because I've defined on lines one and 2。

 a hello function。 I can now use it on line 6 as before。 I can type in my name David。

 and now I will see if less than beautifully hello comma David。 So I've invented my own function。

 And what's nice about programming is that if you were really enamored with what I just did。

 you could borrow this code and use it in your own programs。

 I could save the hello function in a separate file， share it with you。

 maybe install it on some shared system and you could stand on my shoulders and never have to worry about inventing that function again。

 And that's true of all of the functions that come with Python。

 You and I don't have to figure out how to print things to the screen or get user input from the keyboard。

 someone else smarter than us years ago， did that already。

 just as I've now invented this socalled hello function。 But this is cool， too。

 I can write my own functions that take argument。

![](img/f4dde6592256d1f95c23cf86a105feca_159.png)

![](img/f4dde6592256d1f95c23cf86a105feca_160.png)

That take inputs as follows if I want my hello function to say hello to a specific person。

 well in these parentheses， instead of leaving them empty。

 I can come up with any variable name that I want like two because who do you want to say hello to and then down here that value can simply be passed in for instance。

 as before and then down here what I can do is when I call the hello function。

 let's pass in as input the name variable and get rid of my own print on line 7 if I now rerun Python of hello do pi I do have a mistake here。

😡，What have I done wrong here。 notice syntax error。 My first。 Also not intended， but what's missing。

 I forgot that if I want to pass in two arguments to print， I need another comma and to be clear。

 This is a different type of comma。 Everything in between the quotes here is a string inython and that comma in white is a grammatically appropriate comma because you say hello comma so and so in English。

 this comma outside of the quotes， though means something special to Python recall， it means hey。

 Python here comes the second input to the to the print function。 Allright。

 so with that accidental bug fixed。 And in fact， this time， Pyths got me spot on。

 perhaps I forgot a comma。 I did。 let's go ahead and clear my terminal。

 rerun Python followed up type in my name。 And now hello comma David， we're back in business。

 So with this relatively simple feature。 de。 and the syntax I just typed。

 I can actually give myself the ability to pass in inputs to my own。



![](img/f4dde6592256d1f95c23cf86a105feca_162.png)

![](img/f4dde6592256d1f95c23cf86a105feca_163.png)

![](img/f4dde6592256d1f95c23cf86a105feca_164.png)

Function in this case， one， but I couldn't have even done more if appropriate。 Moreover。

 I can even give these functions default arguments， which is a powerful feature of Python。

 If someone uses the hello function but forgets to pass in a name or doesn't care to， that's fine。

 On line 1， I can say that the default value of 2。

![](img/f4dde6592256d1f95c23cf86a105feca_166.png)

Is going to be how about world。 And that doesn't mean it's always going to say hello comma world。

 But only if I don't pass in a name。 So let me run this again and type in my name， David， enter。

 And it says indeed， hello comma David。 But notice if I change my code and don't bother asking the human anymore for a name。

 Therefore I need no variable。 Let's go ahead and rerun it again hit enter。

 and we get hello world by default。 It just works。 So here， too。

 you're seeing how other humans implemented probably the print function， the print function。

 the input function and bunches of others as well。😡。



![](img/f4dde6592256d1f95c23cf86a105feca_168.png)

![](img/f4dde6592256d1f95c23cf86a105feca_169.png)

So one last detail now when it comes to defining functions， this is getting a little messy。

 even though this is a tiny little program because the main part of my program is arguably down here。

 The point of this program is to say hello。 I don't really care about defining the function。

 Like that's not the first thing I want to see when I open this file。

 I want to see what the code is doing at the end of the day。 and it's calling the hello function。

 So you know what， just to be neat and tidy， I want to put this function sort of out of sight out of mind。

 I'm gonna to arbitrarily hit enter a whole bunch of times， paste it way down below in my file。

 then scroll up just so I can make the point unnecessarily dramatically that this program only exists to say hello problem is I introduce a new bug Python of hello do pi enter。

 I get another one of these tracebacks， which is sort of tracing back in time what I did wrong。

 This time it's a different type of error。 It's a name error And again。

 Python's a little mistaken it says it's not defined。 Did I mean help。😡，Sort of。

 but not in this case。 Why is that。 Well， if you think about it now， methodically。

 line 1 tells the computer to call a hello function。

 But line  what 42 tells the computer what hello even means's happening way too late。

 You got to define the function first， and then use it just like I did previously。

 But then I'm gonna get into this messy situation where every time I want to invent a function。

 it's got to go at the top of my file。 and then the actual code I'm writing。

 That's of interest is at the bottom of my file。 It's stylistically， it's just a little annoying。

 if nothing else。 But that's okay， because it's actually conventional and Python to do this。

When you define your functions， sure， put them lower down in the file， thoughre not 42 lines down。

 which was unnecessarily extreme， but go ahead and define also a main function inside of which is all the stuff you care about in this case。

 calling hello then at the bottom of this file call the main function。

 Now this feels like we've added a lot of complexity for not much upside。

 but it's actually indeed conventional to do this because now anyone reading your code。

 whether it's you tomorrow or a colleague down the line， they'll say okay。

 what's the main part of this program， I got it， it's calling a hello function only if they care to understand how hello works。

 do they need to bother looking at this code， and by convention。

 they're not going to care what the very last line of code is if it just calls main because it just kickstart the whole process But why is it in this order because On line 1 you're defining main On line 5。

 you're defining hello， but you're not using either of those until On line 9 you call main which in turn。

 On line2 calls hello。😡。

![](img/f4dde6592256d1f95c23cf86a105feca_171.png)

![](img/f4dde6592256d1f95c23cf86a105feca_172.png)

Which in turn， prints out hello， so and so。So again， a whirlwind tour。

 but just demonstrating how it would be conventional now to write our own programs here。

 And it doesn't have to be for just strings。 In fact， let's do one last one with our calculator。

 Let me close this tab， let me run code of calculator pi to reopen my most recent version of the calculator。

 and let's actually do this。 Let's completely change what I did here so as to do the following。

 Let's go ahead and define a function called square whose purpose in life is to take an integer call it n for number as input and then just return n times n。

 So this is yet another keyword， but it reads pretty straightforwardly。

 The purpose in life of this function that I've defined to be called square。

 takes an input n and returns an output of n times n。 So what is this return keyword。

 We haven't used it， but it's been used by like the input function。

 The input function gets input from the humanss keyboard。

 and then it allows us to copy it from right to left into a variable。

 That's because the input function is returning a value to me the programmer。



![](img/f4dde6592256d1f95c23cf86a105feca_174.png)

As the print function typically just as a side effect。

 so to speak it visually prints something on the screen。

 the input functions is arguably more powerful in that it hands me back something that I can use and maybe even reuse if I store indeed in a variable So there's a turn keyword just says return to me whatever the value is of n times n that is to say n squared using this syntax here and those of you with some prior programming experience might know there's other ways to implement this I'm keeping it simple with just the multiplication operator Now let me practice what I've preached and define also a main function at the very top here inside of that。

 let's finally use our friend x equals let's get the input from the human asking them what x question mark Wait a minute。

 let's not mess this up again， let's proactively convert their input to an integer because the whole point of this exercise is math and then let's go ahead and print out something like print x squared is and then after that let's call the square function passing N X and lets print。



![](img/f4dde6592256d1f95c23cf86a105feca_176.png)

Automatically， spit out。X squared is then a space， as we've seen by default and the square of x itself。

 So let's give this a try。 Python of calculatedalculator do pi enter Oh， darn。Another bug。

 also not intentional。 What did I do wrong here， though， Nothing seemed to happen。 And indeed。

 if I run it again， enter， still nothing happens， it's because I'm defining two functions main and square respectively。

 but I'm never actually kick starting the process by calling one of them。

 So let me go back down to my terminal here。 Rerun it again。 there we go。 What's X。

 Let's go ahead and do2， the square of which should hopefully indeed before。



![](img/f4dde6592256d1f95c23cf86a105feca_178.png)

Those then were functions， we've still got some conditionals and loops ahead。

 let's go ahead and take a break and we'll be back with that and more。😡，Allright， we are back。

 So those then are functions， some of which come with the language itself。

 some of which I have now invented myself。 And while the names of functions might differ across languages。

 most any of the languages you'll encounter in the wild。 We'll have this underlying functionality。

 this ability to use these calls to action to achieve functionality that someone else implemented for you。

 and we'll see more hints of that down the line today。

 But let's turn our attention now to another one of the constructs in that there pseudocode that we did in our first lecture。

 namely conditional those proverbial forks in the road that allow me to do something conditionally based on the answer to a boolean expression。

 So how might we do this。 Well let me go over to VS code here。

 and let me go ahead and create a file called say conditionals dot pi just to make clear what we're focusing on this time around So conditionals dot pi is gonna give me an empty tab up top。

 and let's go ahead and do some quick math， but not to the extent we did earlier。

 let's do x equals int of input quote unquote what's x。



![](img/f4dde6592256d1f95c23cf86a105feca_180.png)

![](img/f4dde6592256d1f95c23cf86a105feca_181.png)

![](img/f4dde6592256d1f95c23cf86a105feca_182.png)

Then on the next line， let's do y equals int。Input quote unquote， what's y。 question mark。

 And then below that， let's now tell the user whether x is greater than or less than or equal to y。

 In other words， let's decide with a conditional what to say。 Well。

 the way I can express this in Python is as follows。 Liter， I can say if。

I can then say x is less than y using familiar mathematical syntax。

 then I put a colon and then below that indented， as we've seen before， four spaces by convention。

 I'm going to go ahead and print out sort of a statement of the obvious X is less than y close quotes。

😡，Else if sorry， cut that out in post。Else， if x is greater than y colon。

 let's go ahead and print out the obvious。 Now。 X is greater than y。Else， if x is equal to y。

 go ahead and print out that same statement， unquote x is equal。



![](img/f4dde6592256d1f95c23cf86a105feca_184.png)

![](img/f4dde6592256d1f95c23cf86a105feca_185.png)

To whyi。Alright， pretty straightforward。 It seems to be a program that not only gets input from the user X and Y respectively。

 it and does something with X and Y by asking these questions。 I've got one，2。

 three Boolean expressions here that's going to determine what gets printed out to the screen。

But I'm not going to run it yet because I kind of see a bug on the horizon。

 This one's a little subtle， but perhaps you see it， too。I don't love line 8 at the moment。

Because thus far， even though in the real world， the equal sign means equals the equality of say two values。

 we've already seen that in programming， at least in Python and a lot of languages。

 it means assignment copypy from the right to the left this value and that's not what I intend here。

 In fact， if I did run this， Python's not going to like or let me do this。

 So I think I need another operator for testing equality And this is going to look a little weird。

 but what humans came up with years ago， including for Python is equals equals。

 So we sort of painted ourselves into a corner by using equals for assignment because at some point someone then realized oh my gosh。

 how do we compare two values for equality So someone proposed well。

 let's use two equal signs and crazy enough there's some languages that use three equal signs for something more。



![](img/f4dde6592256d1f95c23cf86a105feca_187.png)

![](img/f4dde6592256d1f95c23cf86a105feca_188.png)

This is where we'll stop for Python just at the tube。 So now I'm gonna to go ahead and run this。

 and we'll see if it works。 Python of conditionals do pi enter。 Let's type in a number like1。

 and then a number like 2， the former of which is less than the latter。 And indeed。

 that's what I got。 Let's rerun it。 and let's reverse it。 X for2， Y for one。

 And x is indeed greater than y。 Let's run it one more time。 Let's type in one。 Let's type in one。

 And in fact， x is equal to y in this case。 So pretty good， pretty straightforward。

 And here's a perfect example of where。😊。

![](img/f4dde6592256d1f95c23cf86a105feca_190.png)

Python reads like English。 and this is among the reasons that people like it。

 So this code is correct。 I'll claim。 But it's not very well designed。 Again。

 making the distinction between the style of your code。

 the correctness of your code and the design of your code is sort of among the characteristics of what makes code good or bad ultimately。

I don't like this at the moment。 And I think I can I think I and perhaps even you can infer why this isn't the best design because if it does read like English。

 it's clear that I'm asking myself three questions。

 but is that really necessary because logically if x and y are integers。

 which they're going to be based on lines1 and 2 Well。

 x is either going be less than y or greater than y or equal to y that's the three options here。

 but notice this subtlety， if x is less than y， if that's true。 if that Boolean expression is true。

 I'm going to print out x is less than y， but if that's true， why am I wasting everyone's time。

 also asking if x is greater than y， and if x is equal to y because I already know it line 4。

 that no， it's less than y， So it would seem that this code is arguably poorly designed。

 because I'm wasting time， maybe my own because I wrote all this code。

 but really the computers because I'm asking it to answer three questions when sometimes the first answer suffices for the whole problem So I can。



![](img/f4dde6592256d1f95c23cf86a105feca_192.png)

Actually clean this up a little bit。Improve the design using slightly strange syntax。

 but let me go up to my code here after clearing my terminal and let me change this this if to an L if。

 which is short for in English else if it's a little weird， honestly。

 I always forget if it's L if or else if because it varies by language， but it's indeed L if here。

 which is short for the logical notion of else if， and I'm going to do this down here。

 which now has the logical upside of short circuiting this whole conditional if the first condition is the first Boolean expression is true。

 or even if the second Boolean expression is true。 we're only going bother asking this question if the first and even the second questions have false answers。

😡，So why to be clear， we're only going to execute this if we got back false answers for the first two Boolean expressions。

 and we're all going execute this line。 If we got back a false for the first。

 So we're saving a little bit of time。 Now， the astute might notice， too， that。

Still poorly designed because if it's not less than x。

 if x isn't less than y and x isn't greater than y， Well， obviously it's equal to y。

 So why are you wasting the computer's time still asking that third question。

 So I can tighten this up further。 let me get rid of this L if entirely and use a slightly different keyword literally else colon。

 And now I essentially have conditions that are， if you will mutually exclusive。 Sorry。

 don't want to say that。😡。

![](img/f4dde6592256d1f95c23cf86a105feca_194.png)

Now， what I effectively have is a tighter block of code that's only going to。再一趟。Now。

 what I effectively have is a program that checks if x is less than y， and if so。

 it prints out as much and that's it because it wouldn't make sense to even ask yourself the question else if because we already have a true answer to our question。

 However， if we do get down here， and x is not greater than y still， sorry。😡，However。

 if we do get down here and x is greater than y， then I will print out x is greater than y。

 but if that two is not true， then and only then why bother executing this third and final line。

 So it's a subtle difference， but certainly if you're executing this code a lot again and again。

 saving those milliseconds， those nanoseconds can certainly add up over time。

 certainly for much larger programs than these。 So still correct but better designed this time around。

😡。

![](img/f4dde6592256d1f95c23cf86a105feca_196.png)

![](img/f4dde6592256d1f95c23cf86a105feca_197.png)

Allright， Well， what else can I do， Well， if I don't really care about greater than or less than I just care about equal to or not equal to。

 I can express this program a little bit differently。 Let me introduce the following syntax if。😡。



![](img/f4dde6592256d1f95c23cf86a105feca_199.png)

X is less than y， or x is greater than y。 Well， let's just go ahead and say。

Print out X is not equal to y close else。 if that expression is not true。

 then go ahead and okay X is equal to y。 So I'm joining these two Boolean expressions together to give me one larger boolean expression。

 if you will， because I'm asking in one breath in one line if x is less than y or x is greater than y that means necessarily that they're not equal else it's going to be the case that they are。

 There's another way to do this， though。 I don't have to check for greater than n less than what I can actually do is just this。

 I can use not equals。 Now that's not a key that's easily accessible on most keyboards。

 And so what most programming languages do。 Python among them is you use an exclamation point in this context pronouncedun bang and then in equal sign。

 So bang equals means not equals And so you're asking yourself if x does not equal y。

 then print out x is not equal to y。 Otherwise print out x is equal to y。 Of course we。



![](img/f4dde6592256d1f95c23cf86a105feca_201.png)

![](img/f4dde6592256d1f95c23cf86a105feca_202.png)

Can invert this， as we've seen already， we can go ahead and change it to if x equals equals y。

 then say x is equal to y else is x is not equal to y。 You can invert the logic， which is better。

 It really depends on what you think is going to be the common case or however your brain works。

 whatever you think reads best， but we can express both of those comparisons in that same way。



![](img/f4dde6592256d1f95c23cf86a105feca_204.png)

Allright， not all that interesting just to compare numbers that people are typing in。

 This isn't like a very real world problem， but more real worldor would be checking a user's answer to some question。

 maybe prompting them whether or not they agree to some terms and conditions。

 which is something we constantly do in software it seems。 So let me go ahead and close this one。

 Let's create another file to keep this code separate called agree dot pi to implement our own little agreement form。

 Let's go ahead and do this。 Let's go ahead and declare in advance a variable called answer。

 I can call it anything I want， said it equal to the return value of the input function again。

 functions like input and even my own function for squaring can return a value by design And so I can say something like do you agree question mark。

 and I can prompt the user to give me a yes or no answer。 if they type yes。

 well let's check for that if they answer they give me equals equals yes。

 then print out for instance， quote unquote agreed else。



![](img/f4dde6592256d1f95c23cf86a105feca_206.png)

and print out， say quote unquote， not agree just to make clear。 Now， in practice。

 checking or not checking a box or saying yes or no is probably going to have a more interesting effect on the software。

 like you can use it or not。 In this case， we're just going to print visually to the screen whether or not they've agreed down in my terminal window。

 Let me run Python of a agreed dot pi enter Do I agree Sure， yes。seems to work。

 Let me go ahead and run it。 Do I agree。 No， Okay， no， not agreed。 Let me run it again。 Do I agree。

 Sure， but sure is okay。 And I bet I could have expressed myself differently。 In fact， all fine。

 maybe it needs a literal yes， So let's run it again。 Do you agree， Yes。

 emphatically still not agree。 Do I agree。 Yes， still not agree。 Okay。

 maybe I just want to be a little lazy why， All right， so this program while correct。

 if the user must type in y E S in all lowercase is not very user friendly。

 It certainly not allowing the user to type in a few reasonable instincts。

 although sure is probably pushing the line。 Well， how can I go about changing this a little bit。

 plus make it a little more robust against user input。 Well， we can do a couple of things。

 Let me go up to line1， and drawing some inspiration from our name example earlier for saying hello。

 let me at least strip off whitespace， because if the user accidentally as sometimes happens。

 its in the spacebar， let's at least avoid that problem even though I。exhibit that behavior here。

 And you know what， instead of title casing things， which seems weird for a response like yes。

 let's go ahead and force everything to lowercase。 And indeed。

 if we check the documentation for string functions in Python， there is， in fact。

 a function called lower that forces the string to lowercase。

 The upside of this now is the following。 if I clear my terminal and rerun this program。

 I can obviously still type in yes， agreed if I run it again in emphatically say yes in all caps that also now is recognized as agreed。

 Why because the value I'm storing in my answer variable has not only been stripped of white space on the left and the right。

 it's also been forced to lowercase。 no matter how the user typed it in and then I'm very deliberately checking for lowercase。

 because I know it's going to be lowercase at this point because of what I did on line1。

 So that's better than before， and let's make it even better， we've seen how we can use or。

 So why don't I at least tolerate a more。

![](img/f4dde6592256d1f95c23cf86a105feca_208.png)

![](img/f4dde6592256d1f95c23cf86a105feca_209.png)

First answer or the answer equals equals Y lowercase because it too would be forced to lowercase。

 Now I at least have some more flexibility。 Now， if I really want to go to town。

 I could also check for quote unquote， Sure， or other English expressions。

 but that seems like it's a little ridiculous。 I could be even a little laziier。

 instead of checking for yes or why， it'd be nice， maybe to support。 for instance， Yeah。

 even though maybe being unreasonable， we can check for that too， maybe a little more lazily。

 I can do if the answer starts with a why， I don't care what the user says。

 go ahead and assume agreement。 Let me clear my terminal， rerun this again。 I can type in yes。

 clear my terminal， run this again。 I can type in why。 run sorry， didn't bother clear my terminal。

 let me go ahead and rerun a agreed up pi again， type in yeah。Agreed， But， of course。

 there's weird corner cases like， yeah， no， still， that's gonna be misinterpreted now as agreement。

 So not to say you should tolerate even weird inputs like this。

 but how to do so really boils down to these basic building blocks of now functions coupled with conditionals。



![](img/f4dde6592256d1f95c23cf86a105feca_211.png)

![](img/f4dde6592256d1f95c23cf86a105feca_212.png)

![](img/f4dde6592256d1f95c23cf86a105feca_213.png)

Alright， well what if we want to do something again and again。

 And we saw this in the example of searching a phone book。

 I might want to check to the left or to the right。 And then I again and again and again。

 want to divide and conquer that problem。 So it certainly stands to reason that in general。

 might be valuable to implement code that loops that cycles again and again and again。

 So I don't have to write so many lines of code。 I can write a few lines and effectively just reuse them again and again。

 Well， how might we take advantage of this concept of looping。 Well， with it。

 we can actually solve some different sorts of problems。 Let me go ahead and propose this。

 Let me go back to my terminal window here， clear it and close a agreed up high。

 and let's create a new program， Let's implement our own virtual cat， if you will。

 Let me go ahead and do code me out pi， Let's back up actually to loops before we go to code。 Yeah。



![](img/f4dde6592256d1f95c23cf86a105feca_215.png)

No， too soon。It comes at the end of the loops。

![](img/f4dde6592256d1f95c23cf86a105feca_217.png)

No， toward the end of loops。 That's fine。 Let me。Cheat let's see how to back this up。Let's say。Loops。

All right。

![](img/f4dde6592256d1f95c23cf86a105feca_219.png)

I think I came over here， we'll pretend to do this。Alright， let me go back to V。 S code。

 clear my terminal and close a agreed dot pi so that now I can go ahead and run code of let's call it Miow dot pi。

 Let's go about implementing a virtual cat whose purpose in life is to Miow。 Well。

 how might I do this。 Well， if we want the cat to Miow three times， pretty straightforward。

 I got my print function。 So let's just print Miow。 And then， you know， what's a safe time。

 I'm gonna highlight that copy and paste it three times。

 And this is gonna give me a very happy cat that Miow's textually three times。 Indeed。

 if I run Python。 I called it the wrong thing。😊。

![](img/f4dde6592256d1f95c23cf86a105feca_221.png)

Okay， it was just as well that you interrupted。Okay， sorry y'all。um。Alright。

 suppose we want to implement a virtual cat who simply meows on the screen。 Well， how can we do this？

 Well， let's go oh， sorry， I was in the wrong。Source。Hi。

Suppose that we want to implement like a virtual cat who's designed to meow on the screen。 Well。

 let me go back to VS code， clear my terminal and close a agreed do pi。

 and let's go ahead this time and create， say cat dot pi in cat do pi I can get it to meo pretty easily。

 I think let's go ahead and just print out Miow And if I want to implement a very happy cat that meows like three times。

 let me copy and paste that two more times and there's my cat meowing three times Indeed。

 if I run python of cat do pi， I've got meow meow meow。 If that's my goal， this code is correct。

 it's reasonably well styled because it's hard to go wrong when I've just got three lines there。

 But here too， it's arguably not well designed。 Why Well。

 I literally resorted to copy paste And while that was convenient and a little faster than typing it out three times suggests usually that you're doing something wrong。

 ideally when writing code， you should be keeping it simple and not repeating yourself After all。

 that's why functions were invented， as we've seen and it turns out why loops。



![](img/f4dde6592256d1f95c23cf86a105feca_223.png)

![](img/f4dde6592256d1f95c23cf86a105feca_224.png)

vented so that you could repeat yourself in code as opposed to typing it all out manually yourself。

 So what's bad about this。 Well， it does indeed meow three times。

 But why do I have the same darn line three identical times。

 This is going to be fraught eventually with possible bugs。 Not now。

 it's kind of hard to screw this up。 But if you consider these three lines representative of down the line more sophisticated lines of code。

 what if I misspell one of those meow or I go in and change this program to a dog and it saysof instead of meow。

 but I forget one of the meow， and it still says forget one of the meow。

 And so it's a dog that's meowing like a cat like bad things， I'll be a contrived， could go wrong。

 And that's gonna happen ever more frequently when you code bases much longer and not just three lines of code。

 So in general， you never want to write the same line of code twice if you can avoid it or unless you have a good reason too。

 So why don't I just write this line of code once， and then you some kind of loop。

 Now there's a bunch of ways I can do this。 We saw in our pseudocode for the phone book。

 we can just say go。

![](img/f4dde6592256d1f95c23cf86a105feca_226.png)

Back to a specific line。 That's not something I can really do in Python。 And in general。

 that's not the best technique nowadays， we have better building blocks in code and languages like Python to do so。

 even though the first examples， I dare say willll look a little cryptic。

 Let me go back up to my cat here， delete all that code and let me decide in advance that I want to do this three times。

 So I'm going to give myself a variable。 I'll call it I for integer and set it equal to 3。

 just so that I can sort of keep track in my computer's memory in this variable how many times I want it to meow。

 Now I can do this while I does not equal0， go ahead and print out quote unquote miow。

 So this seems logical。 I set the variable value to3， I check so long as it doesn't equal 0。

 And while it's not equal to 0， I do the following。

 So this while keyword is the first example in Python code of inducing a loop。

 It's a special keyword to find in the language you could read that documentation that tells you if you provide a boolean expression。

😊。

![](img/f4dde6592256d1f95c23cf86a105feca_228.png)

After the word while similar in spirit to a conditional。

 which just checks the bullolean expression once a loop is going to check it again and again and again on each pass through or iteration so to speak on each iteration of that there loop but I don't want to just do this as is because something had better be keeping track of how many fingers I still want to have up I want to go from3 to2 to1 and then0 so I need to do this programmatically and one way to do this would be on line4 after I'm now。

 change the value of I to equal whatever the current value of I is minus1 that is to say decrement I Now this looks a little weird at first glance because it's saying like I equals I minus1 like how is that mathematically possible but again a single equal sign is the assignment operator copy the value I minus1 and store it into the lefthand side which happens to be I itself So if I is33 minus-1 is2 So I now becomes on line4 the value。

😡。

![](img/f4dde6592256d1f95c23cf86a105feca_230.png)

![](img/f4dde6592256d1f95c23cf86a105feca_231.png)

And then what happens is Python knows automatically to go back up to line2。

 if only because everything here is indented。 So it's pretty clear that this is inside the loop。

 and this is the beginning of the loop itself。2 does not equal 0。 So it's gonna meow again。

 then we're gonna decrement I again。 So now I is going equal1。1 does not equal 0。

 So we're gonna meow again， and we're then going decrement I。 So it's now 0，0 is equal to0。

 So this loop now terminates， there's no more lines of code to execute。 So that's it。 I've meow 12。

3 times simply by using a variable to kind of very mechanically， if you will。

 keep track of what it is I want to do。 Now I don't have to do it this way。

 if you prefer not to count down， but you prefer to count up， I could do it as follows I equals1。

 And then while I is heck less than or equal to3， There's no easy less than or equal to s on a typical keyboard。

 So in many languages， Python among them。 do。

![](img/f4dde6592256d1f95c23cf86a105feca_233.png)

Les than signine and then an equal sign to express that or the opposite if you prefer。😡。

For greater than then I can go ahead in Miow just as before。

 but this time I have to be a little careful。 I have to say I equals I plus one an increment I。

 So I'm starting at one。 I'm going to two， I'm going to three，3 equals 3。

 So that's it at that point Indeed， if I go back to my terminal here and run either version。

 I'm going now get a cat that meows as before three times。 there's a little trick though here。

 that's worth noting。 I don't have to start counting it one， like us humans in the real world。

 In fact， it's conventional as we've seen already for computers and in turn。

 computer scientists to start counting from zero。 After all， that's the smallest value。

 other than negatives that you can represent with some number of bits。

 So even though it might be a little against your instincts tends to be more conventional to start counting at  zero。

 And then while you could change this to less than or equal to2。

 I don't like the semantics of that because three is the goal。 why are we talking about2。

 So a better way。

![](img/f4dde6592256d1f95c23cf86a105feca_235.png)

![](img/f4dde6592256d1f95c23cf86a105feca_236.png)

ToEx this is if you start counting at zero， count up2，3， but not through3。

 change your Boolean expression to be I less than3 so that if you start at0。

 go to1 go to2 once you hit33 is not less than3 so you'll stop at that point so we've just shifted our range if you will from one indexed starting at one to zero indexed starting at zero We can actually tighten this up a little bit it's so common in programming to add numbers like this to increment numbers that shorthand notation for line 4 is actually this I plus equals1 has the exact same effect but it's slightly fewer keystrokes and it's a little quicker to read and therefore pretty conventional to use instead of the more verbose I equals I plus1。

😡。

![](img/f4dde6592256d1f95c23cf86a105feca_238.png)

![](img/f4dde6592256d1f95c23cf86a105feca_239.png)

This is correct。 This is well designed。 It's conventional。 It's hard to find fault。

 but it's not the only way to implement a loop in Python。 In fact。

 it's conventional to use not just the wild keyword。

 but if you prefer another keyword called4 So how might I do this。

 The four keyword works a little differently。 And it's a little tighter。

 fewer lines of code as a result。 you can say the following4 I in the following list of values，0。

1 and 2， for instance， go ahead and print yeahow， to be clear if I go down to my terminal and rerun this works exactly the same。

 but what's going on。 Well， here we have an example， of not just integers，0，1 and 2。

 but the square brackets around them， imply that this is a different type of data altogether。

 This is a so-called list in Python of integers。 which was one of the other data types that I alluded to earlier when we talked about ins floats in more。

 So this is saying very tersely。 I'll admit。

![](img/f4dde6592256d1f95c23cf86a105feca_241.png)

4 I in the following list of three values do the following。

 So what essentially is happening here automatically without you having to do as much work as with the while loop on the first iteration through this loop。

 I will be automatically set to0 On the second iteration of this loop。

 I will be automatically set to one on the third iteration of this loop。

 I will be automatically set to2。 Now that's not that useful because I'm not actually using I anywhere。

 but this is indeed the conventional way to do something with a four loop to iterate over some number of values。

😡。

![](img/f4dde6592256d1f95c23cf86a105feca_243.png)

But correct as this is works exactly the same as the while loop's not well designed。

 I would claim at the moment。 Now， why is that？ Well， imagine the extreme scenario。

 you don't want to meow three times。 maybe the cat's like really hungry。

 and so it mouths 30 times or 300 times。 Are you really going to enumerate3，4，5，6，7，8。

9 not to mention 300 in that box there， probably not， there's got to be a better way。

 And there is another one of the types in Python that we alluded to briefly earlier is that you can have a range of values very easily。

 In fact， if you want a range of three values， you can literally say range of three values。

 range open parentheses 3， and that will essentially hand you back a list of three values by convention。

 the list is actually going to be 0，1 and 2， even if you don't care about the values。

 but it's going to do some more efficiently by handing you back1 number at a time on each iteration of this loop。

 And what's nice is if you do want 30 such values or 300。You just change a number。

 You don't crazily enumerate all 300 or 30 of those values there。

 So I think we're on track now for an even better example。 And here just to make clear。

 if it's rubbing you the wrong way that we're declaring a variable I， but we're not really using it。

 we're sort of using the side effect of it doing this thing again and again。

 a minor subtlety and Python is that when you don't care about the value of a variable。

 you can actually name it something like underscore， which isn't really a special character。

 it's a valid character to use in the name of a variable。

 but it's just a visual clue to you down the line and any colleagues who might look at this code。

 okay he's got a variable there， but doesn't care about its value just its functionality。

 the fact that this gives me the result of iterating three times I don't always do this myself。

 many programmers would still just use I for integer。

 which is a very common name for a variable for which you are incrementing in this way with an index value so to speak。

 but either approach would work well。😡。

![](img/f4dde6592256d1f95c23cf86a105feca_245.png)

![](img/f4dde6592256d1f95c23cf86a105feca_246.png)

![](img/f4dde6592256d1f95c23cf86a105feca_247.png)

![](img/f4dde6592256d1f95c23cf86a105feca_248.png)

But as with all code， there's other ways to do this， too。 And in fact。

 a very neat one liner would actually be this print quote unquote meow。

 and then similar to how we used plus in a curious way before to do concatenation on strings。

 you can actually use the multiplication operator to do concatenation multiple times。

 If I want to concatennate that is joined together the word meow three times I could do something like this。

 Now this isn't quite what I want yet。 Python of cat up pi now。

 this is a bit of a step backward wheres maow maybe the cat's very hungry or whatever。

 But that's not really what I wanted。 It's missing new lines and missing spaces。

 So how or it's missing the new lines alone， which represent some form of space。 Let me fix that。

 So it's missing the new lines alone。 How might I fix this。

 Well recall that you can represent a new line with backslash n。

 It would not be correct to just go up there and hit enter because the code kind of looks weird。

 Now something went wrong like no， it's conventional to just do。

Backslash n inside of the double quotes。 Then I can multiply that by3。 And let's see what happens。

 Python of cat dot pi again。 There we have it。 Miow meow meow， but but subtlety。

 there's this weird blank line。 Well， why is that， Well。

 you're getting three copies of meow and a new line。

 But then recall what print does automatically print itself always gives you a new line at the end unless you tell it that you don't want it。

 So I can use another lesson learned and use that name parameter and set it equal to the empty string。

 quote unquote So so to speak， rerun cat dot pi。 And now we're back in business。

 So now I'm not even using a loop per se， I'm just using another feature of python to do this a little more cleverly。

 a little more succinctly， which is fine if it reads well to you at the same time。

 this looks more cryptic， So it might be better arguably to go with either of the former designs。

 the four loop or the while loop， which might just be more explicit and readable to the user。

 and that is a reasonable metric for code quality。

![](img/f4dde6592256d1f95c23cf86a105feca_250.png)

![](img/f4dde6592256d1f95c23cf86a105feca_251.png)

Is it readable， Yes or no， is maybe more important is does it use this as few lines as possible。

 which verges sometimes on being too arcane to be helpful。 Alright。

 what if I don't want the user to just assume that the cat's gonna meow three times。

 And that's it for the cat meowwing。 Let's go ahead and let the user tell us how many times the cat will meow。

 So how might I do this， A very conventional way to ask the human。For a number is the following。

 I can do something like n equals int input。 quote unquote。

 what's n and just ask the user for this value。 And then I can go ahead and as before， do like 4。

I in range of not three， but n passing in that variables value as the input to the range function。

 And then I can go ahead and print Miow。 I'm gonna go down here and run Python of cat op pi enter what's n 3 still works as intended。

 But if I run it again and type in 4， Now I get4 Mios。 Now， if I go ahead and run it again。

 maybe I'll be a little weird and type in 0。 Okay， that's correct。 if strange， let me run it again。

 type in negative one。 Okay， that's a little weird。 But also， I got no Miowos。

 But wouldn't it be nice if I could prompt the user again。For a number。

 if they don't give me one that makes sense。 if they give me 0。

 Why are you wasting my time even playing this game， If they give me an negative number。

 that makes no logical sense。 So let's actually use a loop to force the user to give me a correct value。

 So let me go ahead and propose this。 I could。Do something like this。 If n is less than one。

 which is not what I want， then I can prompt the user again。 But wait a minute。

 if n is still less than one， Okay， fine， ask the user again。 What if they're still not obliging。

 Okay， if n is less than one， Well， you can see that this will never end logically。 Or if it does。

 you're only going prompt them 3， four times， and that's it。

 What if I want to prompt them again and again， add nauseum until they finally cooperate and give me a number。

 Well， let's not do what I'm doing there and copy pasting， Let's do this。

While true is a common way to do this in Python。 So this is a little weird at first glance。

 because true is always true。 So you're saying while true is true， do the following。

 I'm deliberately inducing what we'll call an infinite loop。

 But I'm going break out of it as soon as I can inside of this loop。

 The first thing I'm going to do is set n equal to int passing in the input return value of what's end question mark。

 And then。😡，If n is less than one or logically， if you prefer， if n is less than or equal to 0。

 which is the same thing when we're dealing with integers， go ahead and okay， just continue。

 do that loop again else。😡，If n is not less than or equal to 0， go ahead and break out of this loop。

 So these two keywords related specifically to loops allow me to break out of the loop prematurely。

 if you will， because the condition here， the Boolean expression is never going to change。

 So on the one hand， I'm deliberately and this is conventional， Inducing an infinite loop。

 but I'm using a Boolean expression elsewhere to decide when it's time to break out of this thing or continue on again。

 So to be clear， continue does not mean go down the line 8。 It means continue in this loop。

 continue in this loop because the user in this case is not given me what I want。 Now。

 this is a little silly， though， to use four lines of code to express this。

 It is not necessary to explicitly use the word continue。 So rather。

 what would be better is to flip the logic and say this。 if and only if n is greater than0。

 go ahead and break。 same exact functionality， just as correct to fewer lines， arguably。

more readable because again， continue is not explicitly necessary。

 It's implicit that you'll just keep looping again and again and again until such time as you actually do break out。

 So now if I run this version，😡，In my terminal with Python of cat do pi。

 type in three for n still works， type in 4 for N。😡，Still works as well。

 So some languages have other constructs that allow you to do this。 And Python。

 this is canonical to actually induce an infinite loop like this and then break out of it if and when you are ready。



![](img/f4dde6592256d1f95c23cf86a105feca_253.png)

Unfortunately， you can get yourself into a little bit of trouble with these here Infinite loops。

 supposeuppose， for instance， that I do something intentional or foolish like this。

 Let me go ahead and close out my cat， open up my calculator from before。

 and let's reinvent this calculator just to count up。 I'm going set I equal to0。

 I'm going then say while true because I just learn this trick。

 I'm going to print out the value of I， and then I'm going to increment the value of I by one。

 Allright， so what does this do。 This is sort of counting up from 0 on up toward infinity。

 But because there's no break。 There's no conditional or boolean expression inside of the loop。

 It's never going stop incrementing。 So let's see what happens。

 I'm going actually increase the size of my terminal window by clicking this little carrot symbol and then run Python of calculator up pi here。

 hit enter。

![](img/f4dde6592256d1f95c23cf86a105feca_255.png)

And you'll see that Python's counting up pretty darn fast。

 We're in the hundreds of thousands already Before long we'll be in the millions。

 if we really run down the clock， well eventually reach the billions， the trillions and so forth。

 this loop is going to run forever。 and interestingly enough， in some languages。

 this loop would weirdly stop on its own， because many programming languages are vulnerable to another fundamental problem with computing of integer overflow。

 which is similar in spirit to floating point in precision， which recall， refer to real numbers。

 potentially being infinitely many， And so it's not really possible to represent perfectly precisely all of those numbers。

 if you only have a finite number of bits。 and indeed。

 the artifacts we were seeing of the weird digits after the threes， for instance。

 were a symptom of how the numbers are ultimately stored in binary in the system。 integer overflow。

 obviously relates to integers specifically because if you only have a finite number of。



![](img/f4dde6592256d1f95c23cf86a105feca_257.png)

![](img/f4dde6592256d1f95c23cf86a105feca_258.png)

![](img/f4dde6592256d1f95c23cf86a105feca_259.png)

Bits， but you keep incrementing the number incrementing the number， incrementing the number。

 if you think back to lecture0's discussion of binary。

 eventually you're going to carry the one and all of the other digits are going to be0。

 but if you don't have another bit if you don't have another light bulb if you don't have another switch if you don't have more memory。

 somehow or other， you might actually come all the way around to 0 or heck if you support negative numbers。

 you might end up in the negative range instead。 Now， nicely。

 the latest versions of Python do not suffer from this problem。

 And while this might make the lecture all too long。

 this should never stop unless something else goes wrong。

 I will not be vulnerable in this version of Python to integer overflow， but it is， in fact。

 a problem that plagues other languages in particular。

 and we can rather see it if we revert back to some of our earliest examples of 1，2，3 on the screen。

 For instance， if I start incrementing 123， I of course， go to 124，125，6。



![](img/f4dde6592256d1f95c23cf86a105feca_261.png)

![](img/f4dde6592256d1f95c23cf86a105feca_262.png)

7even and onward。 eventually I will carry the one so to speak because I can't write 10 for a single digit。

 So I carry the one and I put down a zero there。 and then the middle digit， of course。

 becomes a three。 But once I get up to like 999 and add one more there incrementing this number。

 it carry the one。 carry the one carry the one。 But if there is no fourth bit。

 no fourth light bulb or memory， well， I'm going to accidentally go from 999 to the number 0。

 So it would seem this is， in fact， what effectively happened with some systems。

 though not as many as the world feared in y2。 when our clocks rolled over from the year 1999 to 2000。

 because at the time， so many systems in the world were using just two digits。

 the last two digits of years to keep track of years and so 99 rolled over not to 100。

 let alone2000 but to0，0 instead。 So this is a fundamental issue with again。

 finiteness and what Python nicely does as do libraries in other languages， is it just gives you。

Another bit if you need it， another bit if you need it， another bit if you need it。

 and hopefully you're never gonna need such big numbers that the computer itself runs out of memory。

 Otherwise there's probably a different or better way to tackle that problem。

 So this is never going to stop at which point I've kind of lost control over my keyboard。

 it is not uncommon to accidentally induce infinite loops， especially while learning programming。

 know that control C is your friend to interrupt processes like this。 Indeed。

 on my keyboard if I control C。 sometimes multiple times I will send a keyboard interrupt。

 at which point I see a cryptic trace back。 but it's not an error with my code。

 It's because I interrupted Python itself。 but now I'm back at my prompt and can do something more here as well。

😡。

![](img/f4dde6592256d1f95c23cf86a105feca_264.png)

Alright， well， how else might I use loops， not just for printing things and doing things like this。

 Let me go ahead and shrink my terminal window again。

 Let me close my calculator and let's do a little something with the names of some schools。

 So let me go into my terminal and do Python or rather code of schools do pi and let's go ahead and give myself a list of three schools similar to how I gave myself a list of three numbers。

 but now it makes more sense because I do care about these specific values。

 So I'm gonna create a variable called schools。 I'm going create a python list using those square brackets and inside of those square brackets。

 I'm gonna put three values。 I could put012 but those are obviously not schools。

 So I'm gonna put let's say Harvard quote unquote MIt quote unquote and Oxford So three values in this here list I can now print out each of those three schools as follows here's the bit of new syntax I can use print I can use the name of the variable And if I want to print out the first element of that list。

 I can again use square brackets， but in a slightly different way。 I can put the number。

0ro there because again， computers and programmers tend to start counting from or thinking from zero on up。

 So the first element of the list in Python here is indeed the zero element。

 not the one element so I'm deliberately using zero then I can go about printing out schools bracket1 then I can go about printing out schools bracket2 if I go down to my terminal run Python of schools pi and hit enter it's not an interesting program but it does show me how I can one online line one store the names of three schools as strings and on lines 3。

4 and5 print out the first of those the second of those the third of those Now even though lines3。

4 and5 aren't really copy paste because they ever so slightly differ there's obviously a pattern here I'm going from zero to one to2 so there's some synergy with the looping we did earlier with I and incrementing it so we can actually be a little smarter here and in fact Python gives us a way to do this even without worrying about I。

I can actually use a for loop like this。😡，For school in schools。

 so much like range handed me back a bunch of values。 schools is already a bunch of values。

 So using this T syntax in Python for school in schools， though I could call this anything I want。

 I could say for X in schools， for I in schools， but semantically in English at least kind of make sense to iterate over in a list called schools one at a time。

 So the singular of schools is of course school， I just kind of like how this sounds and indeed I'd argue this reads like English more so than I or something arbitrary would inside of this loop that's then go print out not zero or one or two because who cares about those numbers here。

 I can just print out school And so as before what Python's doing for me is it's automatically setting this variable school to the first value。

😡。

![](img/f4dde6592256d1f95c23cf86a105feca_266.png)

Then to the second value， then to the third value， and Python knows how many values there are because there it is。

 and I put it in the computer's memory。 It's going to automatically terminate this loop after those three iterations without any need for arithmetic or numbers or variables like I。

😡。

![](img/f4dde6592256d1f95c23cf86a105feca_268.png)

So that's a Python list。 What more might I want to do Well I could go about doing something like this let me go ahead and erase all this code clear my terminal here and let me propose to store my schools with a bit more information be kind of nice to associate the schools with the cities in which they live and so for that it's kind of like on the board as in the first lecture。

 maybe we draw a table with two columns maybe the school's name on the left and the city on the right Well we can achieve that recall in our discussion of data structures with what we generally call a dictionary a dictionary is a collection of key value pairs。

 maybe names and numbers， words and definitions or something else in this case it could be school in city so how might I give myself a dictionary well recall that in Python there are other data types。

 not just ins and floats and lists there are diic objects or dictionaries whereby I can use syntax like this I can reinvent my school。

😡。

![](img/f4dde6592256d1f95c23cf86a105feca_270.png)

![](img/f4dde6592256d1f95c23cf86a105feca_271.png)

Variable to equal not using square brackets because it's not a list per se。

 Now it's going be a dictionary。 and the syntax is a little weird， but the convention is to do this。

 A curly brace。 And then just to make room for these schools。

 I'm going to move the other curly brace to another line。 then inside of these curly braces。

 I'm gonna to say the first school's name。 then a colon then the city it is in which is Cambridge。

 Then a comma then hit enter。 and Vs code is nicely indenting for me。

 Now I'm going to go ahead and put MIt， then a colon， then Mit is down the road also in Cambridge。

 then I'm going to go ahead put a comma and in this one。 Oxford。

 which a little musingly Oxford is in Oxford。 so we can keep that one simple as well。

 So we've got two schools in Cambridge one in Oxford and just for parallelism， I'll put a comma here。

 it's not strictly necessary but stylistically programmers nowadays。

 tend to like the uniformity of ending lines like these with commas。

 even though nothing's coming after it。 It's just a stylistic convention。 So how now can I print out。

Not the names of these schools because they're still right there on the screen for me。

 How do I print out where each of these schools is， Well， the syntax is similar to before。

 But instead of numbers， I'm going to use words。 So I'm going to say， for instance， that。

The first city is whatever the value is of the school's variable at the Harvard location。

 The second city is going to be the schools' variable at the MIt location and the third value is going to be schools at the Oxford location down here。

 I'm going to run in my terminal schools do high again enter and I'll see Cambridge Cambridge Oxford。

 So I've seen each of the values of those corresponding keys。 Now at the moment。

 this is a very simple program is's just storing three schools in this way。

 But dictionaries are a wonderfully versatile way of associating data with more data Keys with values。

 names with numbers， words with dictionaries， it goes on and on the list of possibilities。

 So this is syntactically how you can implement that idea in Python of what we already explored as a data structure on the board or in the real world。

 the physical concept of phone bookss， dictionaries themselves and beyond。

 How can I make this a little more user friendly and maybe even loop over all of these things。 Well。

 even without numbers。😊。

![](img/f4dde6592256d1f95c23cf86a105feca_273.png)

![](img/f4dde6592256d1f95c23cf86a105feca_274.png)

volveI can use a four loop as follows for each school in that school's variable。

 Go ahead and print out how about the school name first。

 Then let's use the print functions feature of accepting multiple arguments。

 Let me go ahead and print out， for instance， let's say。I。In with quotes around it。

 then let me go ahead and print out schools bracket school， which is a little weird。 But again。

 schools is the variable that has everything。 I'm using square brackets to access the value of a specific key in list。

 we did something similar。 we use square brackets to access the value at a certain numeric index。

0 or one or two here a dictionary is sort of a generalization of that idea where now your keys are strings instead of me integers like they were in a list。

 So if I did this right， let me try running python of schools do pi again。

 and I should have full full-fledged sentences。 a little longer than I want。

 there's some weird spacing in there。 Why is that Well。

 I didn't need to put the space here or the space here because I get those for free。

 recall that there's a default separator in python that gives me a space。 we can also override that。

 there is a named parameter for the print function that lets you change that too， but I'm just going。

Get rid of the superfluous white space。 Let me go ahead and clear my terminal to run this cleanly as Python ofchos do pi。

 and there we have it， three phrases that state the truth。 Harvard is in Cambridge。

 MIT is in Cambridge， and Oxford is in Oxford， again。

 demonstrative of how we might simply store a whole bunch of key value pairs。



![](img/f4dde6592256d1f95c23cf86a105feca_276.png)

Now thus far， we've had a lot of examples， simply for example's sake。

 but I think it's time to transition to maybe some real worldor examples and then build on top of the code that others have written still by introducing yet other features of Python。

 but first， let's take a short break and we'll be back with some real world applications thereof。😡。

Alright， how about we now implement the teeny， tiniest version of Super Mario Brothers。

 One of the games with which I grew up。 Whereby you had screens like this。

 where you had some obstacles， some coins and some other goals。

 And this board is sort of composed of some repeating patterns。 For instance。

 here is a brick wall that seems to be composed of three bricks。 top to bottom。

 Let's use some ASI art， if you will， Just pure text to implement at least this wall。 Now。

 having completely lets you down as to how interesting this game would be。

 Let's go ahead and do this in V S code， as follows。 I don't like that statement。

 Let's do this again。😊。

![](img/f4dde6592256d1f95c23cf86a105feca_278.png)

Okay。奥三。Al right， let's now translate some of these building blocks to a real worldorl problem such as the game of Super Mario Brothers。

 One of my favorites growing up。 And this is a game that's composed of some obstacles。

 some coins and some other features。 for instance， this here seems to be a brick wall composed of three bricks top to bottom。

 Let's using some aski art， So to speak pure text Iment the tiniest portion of this screen namely those three bricks。

 How might we do it using some of our building blocks thus far。 Well。

 let me go back to over to Bs code。 Let me go ahead and create a new file appropriately called。

 say Mario pi。 And in this file， let's just print out three bricks。

 Now the easiest way to do this would be to print out unquote a hash mark。

 And I can use any symbol here， but this looks the closest to I would say one of those bricks。

 and just copy paste it three times。 Let probably know where this is going。

 This is probably not the best solution。 but let's at least try it Python of Mario pi。

 and we get brick brick brick。 and we get our three brick wall。 All right。

 I don't like this for reasons we explored earlier， which is that copy pasting。 It's sort of。😊。



![](img/f4dde6592256d1f95c23cf86a105feca_280.png)

Claim vulnerable to mistakes down the line。 And it's just kind of unnecessary to have this kind of redundancy of identical lines like these。

 So how else might I do it？ Well， we've seen before that I can go ahead and do four I。

 or if I don't care about the variable name for underscore in the range of three because I do care about three in this case。

 let's go ahead and just print out a single hash。 if I run this version of the program again with three hashes。

 I get exactly the same as before。 Well， what if I want to pick off a different part of the problem。

 and for instance， want to consider something like this in this screen here。

 we actually have some question marks in the sky 4 of them in a row instead of in a column。

 What are some of the ways in which I could implement this idea。 Well。

 I dare say I could again use some kind of loop。 But just to keep things interesting。

 why don't we go ahead and use one of our more clever one liners and in this case。

 I could do quite simply print out unquote a question mark four times Now if I go down to my terminal and clear it。

 run Python。

![](img/f4dde6592256d1f95c23cf86a105feca_282.png)

![](img/f4dde6592256d1f95c23cf86a105feca_283.png)

Of Mari pi。 I think I'll get exactly those four question marks， one at a time。

 Notice I'm not getting four new lines because I didn't do explicitly backlash n。

 but I am getting one new line for free because print at the very end by default always moves the cursor down to a new line for me。

 Well， how might we do something even more interesting than that。 Well。

 if you go underground in one of the levels of mara， you start to see a lot of bricks like this。

 And if we sort of arbitrarily focus on maybe just these here。

 this looks to my eye like a three by three grid of bricks。

 So it's two dimensional now instead of one dimensional。

 And we haven't really had an occasion to explore possibilities like these。

 So let me again go back to Vs code。 I'll clear my terminal here。

 and let me propose that we could solve this problem in a few different ways。

 one of which is as follows for underscore or this time I'll be explicit I in range of three because I want to iterate over three rows and three columns。

 for each of these and let me think of。

![](img/f4dde6592256d1f95c23cf86a105feca_285.png)

![](img/f4dde6592256d1f95c23cf86a105feca_286.png)

I as maybe being the rows initially， I think this will work out best。😡。

For each of those rows iterate from j in the range of three as well And then inside of that nested4 loop。

 which we haven't seen before， let's go ahead and print out a hash but not yet a new line because I only want to print out a new line down here and recall that some functions can indeed take zero arguments。

 print among them and per the documentation if you call print with no arguments。

 all you get is the new line。 So at first glance， this is admittedly a bit cryptic。

 but let's think about what this means for I in range of three。

 So this first line is telling Python to do something three times Well。

 what do you want to do on the first pass of those three things。 Well， for j in range 3。

 Well this too is telling Python to do something three things。 So you're trying to do three things。

 three times that's going to give me a three by three of something eventually。

 So what do I want to do on that inner nested loop on line 2 Well I want。



![](img/f4dde6592256d1f95c23cf86a105feca_288.png)

Print out a single hash， but no new line。 Why because I know if I'm iterating three times this inner loop is gonna iterate again and again。

 each time printing a hash symbol， but no line ending once though I'm done with the loop here on lines 2 and3。

 I do want a new line because I want to move to the next row of bricks So I do print out just a blank line and then notice the indentation。

 I'm going to go back to the second iteration of the outer loop and eventually the third outer iteration of the outer loop。

 to make this a little more clear， I can move away from I and J。

 which are reasonable conventions I J K if you get more than three levels of nesting。

 probably doing something wrong and there's a better way to do it。

 but I and J maybe K is sometimes reasonable depending on the problem what could I do to make this more clear。

 well semantically I could just give these variables。

 better names like for row in range and for call or explicitly if you prefer for column in range。



![](img/f4dde6592256d1f95c23cf86a105feca_290.png)

![](img/f4dde6592256d1f95c23cf86a105feca_291.png)

This would allow me to sort of annotate my code implicitly in a way that makes me realize， okay。

 the outer lupus for rows， the inner lupus for columns got it。

 even though technically I'm not really using those variable names in this case。😡。



![](img/f4dde6592256d1f95c23cf86a105feca_293.png)

So let's go ahead and run this down here。If Im run Python of Mario pi enter。

 there it is my three by three grid。 It's not quite as square as the actual bricks were in Mario。

 That's just because these hash symbols are a little taller than they are wide。 but it is， in fact。

 a three by three grid。 Now， arguably I could solve this problem so many different ways。

 but let me propose just one way that might help you think about how to solve problems like these because I already have。

 of course， after years of programming experience in instinct for how to do things and I knew that I probably just want a nest two loops with each other in this way。

 But what if you didn't know that and you wanted to approach the problem a little more methodically and break down a big scary problem like printing out a two dimensional grid which we've never done before into a smaller problem that you are more comfortable with。

 Well， to print out this same pyramid， let me go into Vs code here after clearing my terminal and let me do something super easy Let me go ahead and define a function called print row I don't yet know how to deal with a two dimensional structure。

 but I pretty sure I can figure out how to print。

![](img/f4dde6592256d1f95c23cf86a105feca_295.png)

![](img/f4dde6592256d1f95c23cf86a105feca_296.png)

A row。 So I'm going to define a function called print row。

 It's going to take as an argument a with with parameter so that I can tell it 3，4，5。

 whatever it is inside of this function， I'm gonna to print out a single hash times that width。

 So if it's three， I get three of them。 If it's4， I get four of them。

 But I've designed this function to be dynamic and take as input how many bricks I actually want。

 So that's it。 And I think even at this point in the story if you're new to all of this。

 hopefully you're on board with the reality that this line of code on line too。

 indeed is going to print that many hash symbols and I've packaged it up now in a function called print row so that I can use this again and again。

 Now， why is this useful。 Well， let me propose some abstraction out of sight out of mind。

 Let me hit enter an arbitrary number of times to bring us back down to line 42。

 but we'll undo that eventually at the top of this program Let me go ahead as we've done in the past to find a main function that just makes clear what is the main part of my code。

Sorry， ignore that。At the top of my file， let me define a main function here。 let's do that again。

 At the top of my file， let me define a main function here that represents the main part of my code。

 And in there， let's do something that maybe is more comfortable to you。 Even at this stage。

 Let me say for I in range of three， go ahead and do the following three times。 Please print a row。

3 to。Of with three， sorry， let me fix my audio。Let me go back here to the top of my file。

 to a function called main that represents the main part of my code。

 and then in there let me do something more familiar like for I in range of three。

 so do the following three times， please print a row。😡，With three bricks。

 So I've decomposed the problem of printing a twodimenal structure into arguably a smaller problem of just printing three rows。

 I don't know or have to care at this point， how rows are implemented why because I did that earlier。

 And it's all the way down here。 And I've abstracted away what print row means。

 Now I can clean this up and get rid of all these gratuitous line breaks。

 And at the bottom of this file， kickickstart the whole process by calling main itself。

 but I think this might just be an alternative way of thinking about the problem by breaking it down into smaller parts and plucking off each part in turn。

 Now， if I go ahead here and run Python of Mario do pi and enter， there's my three by three grid。

 And I could go one step further and make this even fancier。

 And instead of hard coding3 and then three in two places because that is duplication。

 And that's what a programmer might call a magic value。

 Like your hard coding that is typing permanently the number three。

 But why and why is it in multiple places。 So I could factor that out， I could put it in。



![](img/f4dde6592256d1f95c23cf86a105feca_298.png)

Vable or it could ask the user what number they want。 There are ways to solve that。

 but for now the key point here is that when faced with a larger problem。

 what programmers typically do is they try to decompose larger problems into one or more smaller problems as well otherwise known as hierarchical decomposition and it's really a problem solving technique that lets you distill big problems into small ones that you can solve such that the composition of those solutions gives you the solutions to the problem you actually care about。

😡。

![](img/f4dde6592256d1f95c23cf86a105feca_300.png)

So what then are some other problems we might care about Well so many programmers have come before us and indeed there are in the world what are called libraries。

 software that other people have written that you and I can use sometimes you have to pay for it。

 sometimes you don't sometimes you can download it。

 sometimes it comes with the system already it entirely depends but there's a wonderfully vibrant community of open source software especially or OSs for short。

 which refers to source code that other people have written that under some terms and conditions。

 sometimes you can use， but you can also read the source code it hasn't been compiled into zeros and ones or obfuscate it into Btecode of some form。

 you can actually look at the code， the upside of which is that you can gain some comfort。

 perhaps that this code does what the person says it does because you can literally visually audit it yourself or have a more technical colleague do the same you can also make changes to the code if you really want and if allowed by the license under which you can use the software you can fix bugs in mistakes。

😡。

![](img/f4dde6592256d1f95c23cf86a105feca_302.png)

The software or by contributing them back to the community。

 So this is one of the most powerful things about the world of software is just how frequently we all stand on each other's shoulders。

 not just using functions that came with the language itself like Python's print function and input function and more but also by installing or downloading other people's software。

 thirdpart software so to speak that we can similarly incorporate into our own programs so libraries are incredibly powerful technique and even within organizations and companies might you have your software engineers write your own libraries of code that other employees can use too so that you can write code once and reuse it thereafter and not solve the same problem again and again and certainly not copy paste past solutions to future problems just to reuse that code So let's do a few examples thereof let me go back into VS code now and move away from Mario and Toto program say called generate via which I might want to generate some random values maybe like simulating。



![](img/f4dde6592256d1f95c23cf86a105feca_304.png)

![](img/f4dde6592256d1f95c23cf86a105feca_305.png)

![](img/f4dde6592256d1f95c23cf86a105feca_306.png)

Flipping a coin。 if I want to make a decision somehow randomly。

 Let me code up a file called generate pi。 Let me in my new tab now do something like this。

 Turn out that Python itself comes with out of the box。 So to speak。

 a library called the random library， a module or more or depending on the library in question。

 a package more broadly， that allows you to import that functionality into your own program。

 and it's installed somewhere else on the system already came with in this case， Python itself。

 What might I use this for。 Well， let me declare a variable called coin。

 It in order to simulate a coin flip。I will set this equal to the random library's choice function。

 which comes with it。 and I know this from the documentation。

 the choice function takes as input a list of possible values from which you want to choose like quote unquotetails and quote unquote heads。

😡，Let's do that again。Like quote unquote heads and quote unquote tails。

 And then given that the length of that list is two by design。

 the random dot choice function will give you back a return value of heads or tails 50% of the time each。

 If you passed in a third value， you'd get back each with one third probability over time。

 Suppose I want to then see the result。 I can quite simply print out this coin value and see if this function works as intended。

 Let me increase the size of my terminal here。 Let me run Python of generate dot pi and see what the first coin toss is。

 Tas。Ts。Heads。Tales。Heads。Tales and so forth。 And if we did this an infinite number of times。

 it really should work out to be statistically 50，50。 Now that said， random is a bit of a misnomer。

 It's not truly random because at the end of the day， these devices need to be programmed by humans。

 They can't just come up with a random number like we humans can off the top of our heads。

 They need to be told what to do。 So these numbers are technically pseudo random numbers。

 sort of random numbers that statistically， if properly implemented。

 should be indistinguishable from actual random numbers And among the techniques that programmers use to achieve that pseudoranness is maybe looking at the current time And then basing the results on the sorry。

 I got distracted。

![](img/f4dde6592256d1f95c23cf86a105feca_308.png)

![](img/f4dde6592256d1f95c23cf86a105feca_309.png)

![](img/f4dde6592256d1f95c23cf86a105feca_310.png)

Let me fix something here。 At some point， Design 50 and styleyle 50 appeared here。

 but they were not here originally。I hate to say it。

 but can we theoretically mask that out in all of the laptop shots？They're always in the same place。

Yeah。Well， no， they popped up at some point they weren't there in the beginning because I checked visually。

I'm sorry， just FYI。Okay， let me rewind。Uhhu。With 50 for probability ta ta。



![](img/f4dde6592256d1f95c23cf86a105feca_312.png)

这。Let me figure out where we were。

![](img/f4dde6592256d1f95c23cf86a105feca_314.png)

Okay。So what programmers could use to achieve pseudo randomness is looking at the current time of the computer's clock and basing the choice of random value on that。

 taking into account ambient information like ambient noise or temperature or something else that doesn't necessarily follow a pattern And so with high probability。

 can these pseudoran number generators give you the distribution of values you want。

 even though technically they're not truly random That said， what else might we want to generate。

 Well， if we want to go ahead and write the same program a little more succinctly。

 we don't have to import the entire random library。 We can actually import only what we want。

 So for instance， I can do this， let me clear my terminal window and back up into my code。

 let me go ahead and say from the random library， I the choice function only Now。

 I do not need to use this dot notation， which we've seen in other contexts as well to specify that choices associated with random。

 Now I've just imported the symbol， the name， choice from the random library so that I。



![](img/f4dde6592256d1f95c23cf86a105feca_316.png)

D access to it as well。 How else might I use this library？ Well。

 if I want to use something like another function， I can import the random int function。

 Rand int for short， whereby instead of choosing among heads and tails。

 Let's do something like choose a random number between 1 and 10。 So here I could do Rand int。

 and then inside of its arguments， I can pass in a lower bound and an upper bound。

 And now let me go ahead and change the variable name to something more appropriate for an integer like number rerun Python of generate dot pi。

 and I get one。 I get 3。 I get 3。 I get 10。 I get 9 and so forth。 if I run this again and again。

 I should get each of those values with equal probability over time。 What more can I do。 Well。

 what if I want to implement a sort of card game here。 Well， let's start， as we did before。

 let's import the whole random library this time。 Let's declare a few cards as you might see in the casino。

 Some of whose values are jack， for instance， and queen and。

And we'll keep it simple with just those three cards。

 then let's go ahead and use the random librarys shuffle function to shuffle those cards that is randomly order them。

 then for each card。In that card' variable that's just been shuffled。

 go ahead and print that card one at a time。 Let's now see what we see on the screen。

 If I run now Python of generate do pi enter， I get queen Jack King， if I run it again。

 Queen King Jack， if I run it again， Queen King Jack， But if I run it again， Queen King Jack。

 if I run it yet again， Jack King Queen。 So if we only run it a few times， we might。

 in fact see a coincidence of the same values being outputted， But again， if you give me forever。

 you will see that uniform distribution。 Well， what else can we do。 Well。

 we can actually implement pretty powerful statistical techniques， even simple ones， too。

 with very few lines of code。 For instance， let me go ahead and code up a file called average。



![](img/f4dde6592256d1f95c23cf86a105feca_318.png)

![](img/f4dde6592256d1f95c23cf86a105feca_319.png)

Dot pi in order to calculate the average of some value by importing this time the statistics library instead of random。

 then let's go ahead and print some statistics。 like for instance。

 statistics dot mean for the average of values of these two values。 for instance。

100 that I just got on my exam and maybe a 90 which I got on the previous one。

 Now this should be pretty easy to do in one's head calculating the average of these。

 But if you had a whole list of lots of numbers and ones that aren't as mathematically straightforward is 1 hundred90 on10 point scale。

 let's go ahead and see what the program can do for me running Python of average pi and there I have it95。

 it just took care of the mathform me， much like Excel and Apple numbers and Google spreadsheets can as well。

 Well， what more can we do with Python using these libraries。 Well we haven't used this yet。

 But I have been using this feature。 I have many times now run the python command and the code command And with those commands。

 I have been passing command line arguments。 So we've seen that word。



![](img/f4dde6592256d1f95c23cf86a105feca_321.png)

Beforefo functions can take arguments but commands in your terminal window at that prompt can also take arguments as well called in that context command line arguments how can I write my own program that like Python itself and the code command takes an argument right at the terminal without having to prompt the user with the input function。

 well I can do this in a few ways let me go into my terminal here let's code up a program called name dot pi to get the user's name let's import the system library which comes with Python2 and let's do this print out quote unquote hello my name is just like a name tag and then close comma cis argv bracket1 now this is cryptic for sure but the system library gives me access to like system level functionality Agv is a variable that exists inside of that library a list if you will an argument vector that contains。

😡。

![](img/f4dde6592256d1f95c23cf86a105feca_323.png)

All of the words that the human has typed at the prompt。 So in fact。

 watch what happens now if I run Python of name do pi， but without waiting to be prompted。

 type in my name right away， I and my code will be able to access D V IDd as the value of cis orrgv bracket1 Why because Argv argument vector is a list of values。

 those values are all of the words the human has typed at the prompt and it's a list in python so I can use square brackets to index into the right location。

 if I hit enter now I'll see hello my name is David but why did I use one instead of0 well I literally mean all of the words that the human types in after the python command itself。

 if I change one to a0 rerun the same exact command with my name I'll instead see hello my name is name do pi because that's the name of the file So the first word after the python command that's typed is in location 0 the next one is in location1 insofar as I。

About the latter， it was， in fact， correct for me to use cis do orv1。

 So that's how the code command and the Python command itself effectively are gaining access to the file names that you want to create or interpret。

 Now things can go wrong and let me induce that let me clear my terminal window Let me run Python of name pi but forget about typing my name enter。

 and I get another one of these tracebacks。 an error message that says something went wrong and this time it's an index error list index out of range and notice per these squiggles Python is trying to draw my attention to where the issue probably is Now I've done this mistake a lot。

 I've written a lot of python code。 I know this means that location one that is index one must not exist。

 Why because I didn't type anything in now I could just rerun the program and cooperate and type in David but this is not very user friendlyly software。

 you should not have to expose a scary looking error message to the user for them to cooperate properly like this is why we write better code。



![](img/f4dde6592256d1f95c23cf86a105feca_325.png)

![](img/f4dde6592256d1f95c23cf86a105feca_326.png)

So among the ways to fix this is as follows。 If I go back into my code turns out in Python。

 there's a technique for catching what just happened and what just happened is generally called an exception。

 something exceptional happened。 And in this case， exceptional is not a good thing。

 It means something happened that shouldn't have it was out of the norm。

 But you can try to execute lines of code in Python and catch any such exceptions as follows。

 instead of just blindly running this line of code。

 let me literally try to run this line of code indenting it underneath that try keyword。

 except if there's an error specifically an index error， otherwise known as an exception。

 in which case， you know what， go ahead and warn the user too few arguments。

 unquote So now the effect will still be the same， the program's not going to work， as I intend。

 but at least I'm telling the user in an explanatory way。 why it's not working。

 So if I again run Python of named pi。

![](img/f4dde6592256d1f95c23cf86a105feca_328.png)

![](img/f4dde6592256d1f95c23cf86a105feca_329.png)

![](img/f4dde6592256d1f95c23cf86a105feca_330.png)

With David at the prompt， it works as intended。 If I run the same command without my name and hit enter。

 at least I don't get this scary looking message。 So if you're in the habit of the real world of running some software in once in a while。

 you do see some scary looking message， maybe not in a black and white window like this， but a modal。

 a dialogue window pops up with some cryptic error message or in a browser。😡。

It's not so much your fault as it is the fault of the programmer who didn't catch that error somehow and explain it in a more user friendlyrily way。

 Alright， well， what more can we do here， Well， I could certainly hedge against this in different ways。

 just to tie a lot of our ideas together。 instead of just blindly trying to do this。

 I could do something like this。 if the length of the cis dot Rrg V list is less than2， Well。

 I know already that there's too few arguments。 So let's just tell the user without even trying anything。

 Let's print out quote unquote， too few arguments。 How about， though。

 else if the length of cis dot Rrg V。Is greater than2。 Well， I don't even know what's going on there。

 maybe they type their last name。 Maybe they type some nonsense。

 Let's just go ahead and say to many arguments and just not tolerate it at all else。

 now go ahead and safely print out hello， my name is quote unquote cis Rv bracket1。 In other words。

 in Python， there's at least two different models here， you can try to do something。

 and catch the error if it happens， or you can code more defensively。

 check if the thing you're worried about has happened and then do or don't do something else as a result。

 So if I run this now and run Python of name pi with nothing， I get too few arguments。

 If I run it with my name， I get hello， my name is David。 if I run it with my name and last name。

 that is too many arguments。 at this point。

![](img/f4dde6592256d1f95c23cf86a105feca_332.png)

Alright， let's have a little fun with libraries that don't come with Python libraries that I had to install in advance。

 The first of which is an old favorite in computing circles， namely called cow say。

 And I'm going to go ahead and do this。 I'm going to open up a file called say dot pi。

 I am going to import a library called ca say， which is the Python implementation of an old program。

 I'm going to declare a name variable and set it equal to the input functions return value when asked what's your name question mark。

 And then I'm going to call cow say dot say， And I'm going to pass in。



![](img/f4dde6592256d1f95c23cf86a105feca_334.png)

Quote unquote， hello name。 Just say hello to that person。 but。

 butt but but Now I want to put an F before。 Let's fix that。Just so we have the recording。

I'm going to run。 I'm going to call cow say dot say， quote unquote hello comma name in curly braces。

 But this string is meant to be formatted。 So I'm going to put that F before the first quote。

 Then I'm going to go ahead and in my terminal。 make it larger。 clear it， run Python of say dot pi。

 I'll go ahead and。Oh， I didn't install it in advance， I thought I did， sorry。Pip and saw。 Oh。

 we'll make this a teachable moment。Okay。This is perfect。All right。Going to run first。

 let's create a program called say dot Pi。 And at the top of this file。

 I'm going to go ahead and import a library called cow say。 Just read about it online。

 It sounds really cool。 So I'm going try to use it in my program。 This one note， though。

 does not come with Python itself。😊，Name equals input is going to be how I create a variable and store the return value of input in it。

 quote unquote， what's your name question mark。 Then I'm going to call Ca say dot say。Damn it。

 And actually， let's rewind because I think I said earlier that I installed in advance。

 and that's gonna then contradict the error， the point that I'm now making。So。Let's go ahead。

Let's now go ahead and use another library that doesn't come with Python that's even a little more fun。

 So let me go back to my terminal window here。 and after clearing it。

 let me create a program called say dot Pi so that Ta it。😡，Okay。

Let's now write a program that uses another library。 This one that doesn't come with Python。

 Ive read about it online sounds pretty cool。 It gets a cow to say something on the screen using again。

 askI art。 let's go ahead and create a file called say dot pi because I want the cow to say something。

 I'm going to import the library with import cow say per its documentation。

 then I'm going to create a variable called name， set it equal to the input function。

 quote unquote what's your name question mark， then on the next line I'm going to call cow say dot。😡。

Damn it， I did again。 one last time。还 thinkよ。Yeah， that's smarter。

Let's now write a program using a third party library that doesn't come with Python itself。

 I read about it online。 soundss like it'd be fun to use。 So let's use it。

 I'm going to go ahead and run code of say dot pi so that I can get this program to say something。

 I'm going now go ahead and import the library called cow say per its documentation。

 That's how I import it。 I'm going then create a variable called name。

 set it equal to the input functions return value when asked of the user what's your name question mark。

 And now per the documentation， I'm going to do cow say do cow quote unqu hello name。

 but I want to format this string as always， So I'm gonna to put my f in front of the first quote。

 So I think this is gonna to use the library to say hello David or hello so and so。

 Let me go ahead and increase my terminal window here and clear it and run Python of say dot pi and see what this library does。

 enter。😡，Absolutely nothing。 So it seems that even though I read about this library online。

 cow say it's actually not a module that's installed Indeed in advance。

 It doesn't come with Python itself， but it is free and open source。 So I can install it。

 And while there's different ways to do this， what I'm going do on this system is Pip， install。

Cow say， which would often be in its documentation too， when I clearly just missed that step。

 Once the program is installed， I can go ahead and rerun Python of say do pi enter Here we go。

 Ask my name crossing fingers， perhaps which will help and there I have it an adorable cow saying something to me on the screen。

 However， I did spend a bit of time reading the documentation further。

 And it turns out that this cow say library doesn't just have cow saying things you can have other things as well。

 Let me clear my terminal and shrink it again。 Let me go back into my code instead of a cow。

 I read up that there's a T Rex， aterrannosaurus Rex as well。

 Let me go back to my terminal and make it large。 Let me rerun Python of say do pi。

 let me go ahead and type in my name again and enter。 and now we have too big to fit on the screen。

 even atyrannosaurus Rex that is also telling me hello and there's other Easter eggs in there if you'd like to poke around and read up on what it can do。

 but that's just now a little fun with a thirdpart library。



![](img/f4dde6592256d1f95c23cf86a105feca_336.png)

I did in fact have to install myself now on the one hand。

 this is great and fun and hopefully this library didn't do anything bad but that's actually the risk too just because something is documented online just because it's free and or open source doesn't mean the code is actually safe and so in industry and enterprises you might actually want to hesitate before just running a command like I did and installing something onto your system or worrisomely your entire systems as well so this is where lessons in cybersecurity can come into play but more on those two another time but for now beware and for more reasons than one All right what else can we do with third party libraries well let me go ahead。

Let me fix this。

![](img/f4dde6592256d1f95c23cf86a105feca_338.png)

Well， what more can we do with third partyy libraries Well let me clear my terminal and shrink it again。

 let's close out this cow and actually now create a program that uses the iTunes API。

 so long story short， there's a lot of companies and individuals out there that offer what are called APIs application programming interfaces and these are standardized ways of talking to someone else's system someone else's code and providing input and getting output for yourself that you can incorporate into your own program or product For instance。

 iTunes， the music service actually has an API via which you can search for music albums using keywords。

 In fact， what I'm going to do here is run a program write a program called iTunes Pi。😡。



![](img/f4dde6592256d1f95c23cf86a105feca_340.png)

![](img/f4dde6592256d1f95c23cf86a105feca_341.png)

And in this program， I'm going to do a couple of things。 One。

 I'm going import the cis library as before， so I can take command line arguments。

 and I'm also going to import the requests library。

 which is a library via which I can make httP requests that is web request as though I'm a browser but in code So that is to say I can actually visit webs using code and not my mouse and a browser I can simulate being a browser if you will with this library let me now go ahead and just do a sanity check here so to speak and say if the length of cis orrgv does not equal to then go ahead and just exit entirely。

 I'm going to use another function entirely called exit in the system library and I know from its documentation this is just going to abort my program right now in the event that the user has not provided the right number of command line arguments。

 Now this is going to be a mouthful。 but what I'm gonna type now is the following I'm going give myself a variable called response because I want a web server's response I'm going set it equal to this requests。

get function。 It turns out that get is an operative word when it comes to browsers getting data from a server。

 so I'm going to use an identically named function here just because it's a long line。

 I'm going hit enter and move the parentheses onto separate line so that I can put the whole URL on a line of its own and I'm going to say HttPS colon iTunes apple do co s search question mark entity equals song because I want to search for songs and I'm going limit it to just one response even though I might get back many songs。

 I'm just going to get the first and the search term that I'm going to search for。😡。

After making limit equal to one and the search term I'm going to search for is going to be whatever the human has typed out at the command line。

 which I know from before is insist。 orrgv bracket1 so in other words I'm using Python code to construct a URL。

 most of which I know in advance， but I don't know the keyword that the human's going to type in advance。

 but I do know that it's supposed to per apple's documentation come after this equal sign after the word term and in fact limit equals1。

 I know from the documentation will do just that it will limit the responses to just one song and the type of things I'm going to be searching for are songs indeed and so these ampersss just separate what curiously are yet another example of key value pairs using equal signs now instead of Python's own colons but we're inside of a big string were inside of a URL which is a different beast altogether。

😡，So now at the bottom of this code， I'm going to just print out what that response is specifically using a function called JSON。

 which stands for JavaScript Ob Notation， and in the world of APIs， application。

 programming interfaces，😡。

![](img/f4dde6592256d1f95c23cf86a105feca_343.png)

Json is an incredibly common format for sending data from a server to a client。

 whether that client is a browser or in this case， an actual program。 It's a textbased format。

 It's all about key value pairs that you can have lists or socalled a raise in it as other as well as other values。

 This is not a useful program yet， I'm just gonna dump to the screen。

 what I'm getting back from Apple server。 So what I'm going to do now is go back to my terminal and make it larger so we can see as much as possible。

 I'm going run iTunes do pi， but I do need to give it an argument。

 And let's go ahead and search for someone like Taylor Swift quote unquote and I want to pass in her whole name。

 So I'm indeed going to pass it in in quotes at the command line。

 So it ends up entirely in Rrgv1 instead of in Rv1 and2 one word per each enter。



![](img/f4dde6592256d1f95c23cf86a105feca_345.png)

Now this is kind of a mess。 There's a lot to see on the screen here。

 but allow me to draw your attention to a few features。 One， there's colons all over the place。

 Now even though this is jascript object notation， which is a different language altogether Javascript we're doing with Python many languages use the same syntax for certain things。

 So it's actually similar in this case to Python but there's some other similar syntax too I see a curly brace here。

 I see a curly brace here and the corresponding ones later。

 I see a square bracket here and the corresponding one later。

 So even though as is this is very hard to read， it turns out that what Apple has responded with。

 is indeed javascript object notation but specifically the data they've responded with are essentially dictionaries and lists。

 key value pairs and lists of values and jascript happens to use the same syntax。

 curly braces and square brackets for the same concepts。

 Javascript happens to call them objects and arrays， Python happens to call them dicks and lists but。

Ideas are exactly the same。 Now， I can actually clean this up。 Let me clear my terminal window。

 Let me go back to my code and let me， having read the documentation。

 pass in another argument here to print then just this。 instead of passing in response dot Json。

 let me call Json dot dump S for dump string response dot Json。 and specifically indent。

Please two spaces per Now I'm going to go up here and import now the JSson library。

 which is a feature of Python that just gives me access to Json related functions just to clean this up。

 This is not useful programmatically， this is useful for us the humans。

 Let me go back to the terminal and make it bigger。 Run Python of iTunes dot pi。

 I'll type in again in quotes Taylor Swift。 And now I'm gonna get back， I think the same response。

 but it will be pretty printed。 so to speak with nice anddentation in white space all over the place just so that we can see a little more clearly what's going on。

 Now， it's still too big to fit on the screen， but let me scroll down。



![](img/f4dde6592256d1f95c23cf86a105feca_347.png)

So that I can see the very top。 And here's what I got back。 I got back a curly brace first。

 which means hair comes a dictionary of key value pairs。 What's the first key result count。

 the value of which is one。 that makes sense because I told the API to limit me to one response。

 What's the next key。 quote unquote results。 What's the value of that key。 Well。

 per the square bracket here， it's a list of values。 What's the first value。 Well。

 according to this curly brace， the first and only value is itself a dictionary of more key value pairs。

 Hence you're seeing my claim that these key value pairs and these dictionaries more generally are wonderfully convenient mechanisms for sharing data。

 The first key value pair has a raper type of track don't quite know what that means。

 but I'm sure the documentation would reveal the kind of song the kind of response I understand It's a song。

 Apparently this is Taylor Swift's unique identifier as an integer。

 this is the collection to which the song belongs。 The artist's name is indeed Taylor Swift。

Collection name is Taylor Swift， the bonus track version and so forth。

 And there's a lot of other key value pairs here， but long story short。

 if I were trying to implement my own piece of software that somehow uses music data in this way and lets users search for it。

 I could do exactly this。 And I could print out in this case exactly these。



![](img/f4dde6592256d1f95c23cf86a105feca_349.png)

Results， in fact， let's make one change here。 Let me clear my terminal window and shrink it and let me go back into my code here。

 And instead of limiting the results to one let's go ahead and get rid of that so that I actually get back more than a single result。

 Then down here， I'm going to change my code slightly and not just dump the result。

 We're going to do this a little more elegantly。 I'm going to create my own variable called O for object。

 which is conventional and set it equal to that Json response， though as always。

 I could call these variables anything。 But I'm doing this so that I can iterate over the results therein。

 so for each result in that dictionaries， results keyword。😡。

I'm going to go ahead and print out that results track name。 In other words。

 I have having looked at the format of that JO response earlier and having checked the documentation。

 I know that there is a results key and in turn a track name key。

 the values of which I'm interested in。 So let me go back to my terminal and make it bigger。😡。



![](img/f4dde6592256d1f95c23cf86a105feca_351.png)

Run Python of iTunes do Pi， quote unquote Taylor Swift enter。

 And I now see a whole bunch of track name song titles by Taylor Swift。

 at least based on that keyword search alone。 So you can imagine now making this much more feature for。

 you can make your own streaming media service， It would seem if you could link directly to those songs on iTunes。

 But it's all a matter of using some code that I wrote using libraries of code that other people wrote。

 And in this case， using an documented API provided by someone else。 In this case， Apple。😊。



![](img/f4dde6592256d1f95c23cf86a105feca_353.png)

WellWhat more can we do， Well， let me go ahead and do this。

 I'm going actually switch from my cloudbased version of VS code to my own Mac inside of which I have my own terminal window。

 and any of you that have Mac OS and even Windows if you install some additional tools。

 you can have your own terminal window on your Mac or PC via which you have your own command line interface or CI。

 I've made it look like the one we've been using， but now the code is running on this actual laptop。

 not somewhere else in the cloud because what I'd like to do is now the following。



![](img/f4dde6592256d1f95c23cf86a105feca_355.png)

Sorry， give me just one second。Mmhm。What I'd like to do is the following。I'm going to go ahead now。

I'd like to do is the following。 I'd like to do some facial recognition of some familiar faces。

 perhaps whereby in the folder I'm in in my command line interface。

 I have these four files at the moment。 I've just run a command that I could have actually been typing in my VS code environment called list or。

 sorry。

![](img/f4dde6592256d1f95c23cf86a105feca_357.png)

![](img/f4dde6592256d1f95c23cf86a105feca_358.png)

And do this。In my command line interface here， I'm inside of a folder and in that folder。

 already four files， two of which are images， two of which are actual files of code。

 These code files have the ability to detect faces based on photographs。

 And that's not because I know how to implement the underlying artificial intelligence to do that。

 But because I installed in advance a library called face recognition that has been designed and trained to do exactly that。

 So for instance， let's go ahead and do this。 Let me go ahead and open up first。

 a photograph of some perhaps familiar faces， namely the characters from here， the office。 And sorry。

 let me clean this up before we do this。

![](img/f4dde6592256d1f95c23cf86a105feca_360.png)

Oops， sorry。That works。

![](img/f4dde6592256d1f95c23cf86a105feca_362.png)

All right， I think I should。Yeah。

![](img/f4dde6592256d1f95c23cf86a105feca_364.png)

Okay。Do this。Mm。😊，In here on my Mac's own command line interface。

 I'm inside of a folder that already has four files， two images and two files of Python code。

 The images contain faces that might already be familiar to you。 In fact。

 if I go ahead and on my own Mac open this image called Office do Jpeg。 you'll see these faces here。

 Now among them are quite a few faces and it might be nice to sort of recognize each of those faces individually Now how to do this。

 odds are you can detect sort of two eyes， a nose， a mouth， two ears in general。

 but I don't really know yet how to write that code， but indeed。

 if I've installed a library in advance， I can write maybe less code that allows me to use someone else's logic to achieve this goal。

 So in fact， let me go back to my own command line interface。

 my own terminal window and using a program other than VS code。

 I'm going to go ahead and show you what's inside of this file。

 The file itself is called detect dot pi and here we have just a few lines of code the top of which are some comments from which the code came and you'll see near the top of the file I'm importing from the P。

On image library， some kind of image related feature。 I'm then importing。

 seemingly magically face recognition as a feature。 Thereafter， I'm creating a variable called image。

 and I'm somehow loading an image file called office do Jpeg。 Thereafter。

 I'm declaring a variable called face locations。 and I'm somehow using the face recognition library to find all of the face locations in that image passing it in as an argument。

 Then I've got a for loop。 And somehow or other。 I'm iterating over all of the locations in that image that would seem to be a human face。

 And I'm going to show each of those faces in turn。😊，So how's this going to work， Well。

 let me go back to my terminal Windows prompt and let me go ahead and run Python of detect dot pi thereby running the code on my own Mac。

 I'm going to hit enter。 It's going to analyze the photo and take just a moment and you'll see quite rapidly all of these little images opening up that represent some excerpted faces。

 Let me go ahead and scroll through each of these。😡。



![](img/f4dde6592256d1f95c23cf86a105feca_366.png)

And you can perhaps identify each character in turn。 and somehow or other。

 This third party library has detected what it knows to be faces based on seemingly common patterns among them。

 But we can do more than that。 For instance， supposeose that we have per this library。

 a known face that we're looking for。 We don't have to just look for two eyes， a nose。

 mouth and two ears。 We can look for a specific face， even if it's not quite the same photo。 In fact。

 in my terminal window， let's go ahead and open up a picture of the office's own Toby。

 whose mugshot looks a bit like this， he's in that photo， but not necessarily posing that way。

 Let me close that image， go back to my terminal window。 And this time run Python of recognized。

 because I now want to recognize a specific face。 I won't open up this whole file because there's more lines of code here。

 But most of them rely on this thirdpart library having done the heavy listeninging for us。

 I'm going go ahead and enter The code is opening both of the images now。 And there it goes。

 if I zoom in here。 It is not only found。

![](img/f4dde6592256d1f95c23cf86a105feca_368.png)

![](img/f4dde6592256d1f95c23cf86a105feca_369.png)

![](img/f4dde6592256d1f95c23cf86a105feca_370.png)

Toby it has identified him by drawing a green box thereupon。

So not too bad for just some lines of code on top of a third party library to get all of this functionality myself。

 Well， what else can I do， Well， let me zoom out of that， Let me close all of these office faces。

 And let me go ahead and propose that we write some of our own code that does speech。



![](img/f4dde6592256d1f95c23cf86a105feca_372.png)

Let me go back， let me go back， let me go back into my terminal window。 and let's write some okay。

Let's go back into my terminal window。 and this time write some code that synthesizes speech using another third party library that I've installed in advance。

 I'm going to go ahead here and use another program an alternative to VS code that's more lightweightly called vim。

s。Sorry。Let's go back now into my terminal window and write another program that uses a thirdpart library。

 this one to synthesize speech here again， I'm not going to use VS code but a lighter weight program at my terminal called VI or Vm。

 and I'm going to create a program called speechch dot Pi in this file what I'm going to do is import the library of installed in advance。

 which is pi to text to speech sorry。😡，Sorry， I'm fumbling this part in my environment。

Let me now go back into my terminal window。 and this time let's write a program that uses another thirdpart library this time to synthesize speech。

 instead of VS code， I'm again going to use a lighter weight program within my terminal environment called V or vim and let's create this file as follows at the top of the file Let's go ahead and import Python text to speech version 3 which indeed is the library I've pre-installed let's create a variable called engine because this is a text to speech engine。

 let's go ahead and set that equal to the library in it function。

 which simply initializes the library doing whatever it is the programmers needed to do then let's use that engines say function to quite simply say for now hello comma world and then per the documentation。

 let's call engine do run and weight since it might take a moment for it to actually synthesize and then say these two words let me save that file and return to my prompt。

 let me go ahead now and run Python of speech do pi and let's have a listen。😡，Hello， world。Well。

 that took quite a while to synthesize that speech as short as it was， but it did， in fact。

 synthesize it accordingly。 Well， let's go ahead and make a change and make it a little more interesting。

 let me go back into speech do pi and this time let me have it say hello to someone's name So before I actually say hello world。

 let's ask the user as we've long done for their own name with name equals input quote unquote what's your name。

 question mark then down here let's actually substitute in that person's name and then over here format the string accordingly。

 let's save out of this file rerun Python of speech do pi I'm prompted in a moment after the librarys done initializing with this familiar now phrase。

 what's your name David and let's have a listen to this。Hello， David， There we go。

 So much of the time was spent initially initializing in the library。 But once we provide that input。

 it actually synthesized it quite quickly。 So a simple example， and I。

 as a programmer might have no idea how I convert text to speech。

 But the third party library did so long as it's installed。 Now， what else can I do。

 Why I can even have my computer start listening to me in a few different ways。

 Let's do another example here again using this program called V I or Vim to implement listen dot pi Lastly。

 I'm going to go ahead here。😊，And at the top of the file， I'm going to ask the user for some words。

 which I'll store in a variable called words。 I'm going to set it equal to the return value of the input function that simply asks the user to say something。

 not very descript。 Then let's go ahead and actually。

 I'll insert a new line just to force the cursor onto a new line this time。

 And I'm going to force the user's input to all lowercase。 Then let's go ahead and do this。

 If the user has said the word hello in their words。 Then go ahead and print out。 For instance。

 after。Indenting four spaces， hello to you，2。 In other words， conditionally。

 if the word hello is in the words that came back from the user， greet them as well。 Now。

 in is not a key word we've used in this way， but it does allow me to check if a string on the left is in the string on the right。

 how else might we proceed， Well， if they don't say something like hello， but maybe they say。

 if how are you。In their words， then let's go ahead and print out， say， I am well， thanks。

 exclamation point。 else， if the user has said something like goodbye in their words。

 let's go ahead and print out reasonably。 Good bye to you too。 exclamation points， else。

 if they didn't say any of those things。 and we don't know really what they said in this version。

 We can print out something like， because it's not yet recognized。 All right。

 if I now save this file and return to my prompt and type listen dot pi。

 I can now listen textually for the user's prompts。

 let me go ahead and say something like hello there。 Oh， hello to you， too， let me run it again。😊。

Hello there。 How are you。 Que mark here again， We get hello to you too， Even though I did say。

 how are you， it came after the hello， So that makes sense because that Boolean expression was asked first。

 So if we ask the same question alone， let me clear my screen and run it again， I now can say hey。

 how are you。 And because we're not looking for hey， it will know that we've said， how are you。

 if now I'm getting a little bored with this， I might run it again and say， goodbye now。

 and it will say goodbye to me now too。 And of course， if I type in anything else。

 it will say because I haven't actually written some code for that。 Well。

 let me propose that we this time use a thirdpart library that allows me to write just a little more code。

 but to actually have my microphone， allowow me the human to verbalize what I have in mind。

 similar in spirit to your Google assistant or Alexa or Siri or some other device nowadays。

 I'm going go now into the same file。Delete everything we've done。

 and I'm going to go ahead and import this time speech recognition。 Thereafter。

 I'm going to create a variable called recognizer， I could call it anything I want。

 set it equal to speech recognition and dot recognizer。

 which I know from the documentation is how I start using speech recognition。

 I'm then going to say the following with the speech。😡，Recognitions， microphone。As my source。

 which again， I know only from the documentation， I'm going to say the same thing as before。

 say something， asking the user for just that。 I don't need the backslash end because I'm not using input this time。

 but the print function itself。 Next， I'm going to go ahead and declare a variable called audio。

 and set it equal to that recognizer's Listen function passing in the source to listen to namely my microphone。

😡，After all of that， I'm just going to tell the user what they said just to prove that this works。

 I'm going to print out you said colon， and then I'm going to print out recognizer do recognize Google audio。

All right， how now is this going to recognize my speech。

 essentially by sending the request off to Google， let me save this file。

 run after clearing my screen， Python of Listen do pi。Definitely going across my fingers this time。

 and hit enter。Hello， world。Hello， world。Hello world。Something's wrong。Yeah， I tested this Okay。

 stand by， please。You don't have to bring the audio down。嗯。Yeah， oh， for this example。

Let me for consistency， this is the last example。 It's honestly probably。

Iddeal if we just black this mask this out。Rather than change it midstream。Hello， world。

It's worked before class。Possibly。Oh。Hello， world。No。Nice， okay。

We'll fix this in post if that's okay。嗯。Let me make sure my version works。

Python of listened up pi hello world。Amazing， I wrote it， right，Here we go。

Let me save the file and go back to my term。 oh we don't want to see that。I thought。

Let me save my file and go back to my terminal。 This time running Python of listen do pi again。

 definitely across my fingers this time。Hello， world。And it worked， let's try once more。How are you？

So it's detecting my own human words， so it would seem that if thanks to the speech recognition library。

 I have the ability to understand human words， I can combine a couple of these ideas now and search for some of those same words。

😡，Among the words that came out of my mouth。 So let's actually do this。

 Let's go back into listen op pie。 Let's go ahead now and not just spit out you said。 But instead。

 let's go ahead and store in a variable called words， the recognizer's use of the recognize。

Google function passing in that same audio。 And now as before， if hello is in words。

Then go ahead and print hello to you to exclamation point， L if quote unquote， how are you。

Is in word， sorry。L， if， how are you。Is in words， let's go ahead and print out， quote unquote。

 I am well， thanks。L if quote unquote goodbye is in words。

 then let's go ahead and print out quote unquote， goodbye to you too。Else， as before。

 if we just don't recognize any of the words therein。

 we can print out something like or handle that differently。 All right。

 let me save this version now and go back to my terminal， Cling it again and running once more。

 Listen dot pi， and we'll try again。Hello， world。And now it's detected and recognized what I've said。

 Let's try another。Hey， how are you？I am well thanks and final flourish。Thanks so much， goodbye。



![](img/f4dde6592256d1f95c23cf86a105feca_374.png)

And that， too， was detected。 So suffice it to say。Okay。And that works too。

 Let's add one final flourish and demonstrate with yet another library。

 this one that comes with Python， how we can not only detect and recognize audio。

 we can also now extract individual pieces of information much like today's voice assistant can Let me go back into listen dopi and let me import at the top of this another library called R for regular expression a very fundamentally powerful feature of not only Python。

 but many languages as well， that allows us to use patterns to find or extract information from strings of text。

 In fact， what I'm going to do down here now is this I'm going to delete all of these conditionals and Boolean expressions and what I'm now going to do is this create a variable called matches set it equal to that regular expression librariess search function。

 I'm going to search for my name is but I'm going to expect that any human who says that is probably going to say literally their name next I'm going to use a pattern which is represented。



![](img/f4dde6592256d1f95c23cf86a105feca_376.png)

Of a regular expression， we're using dot star where the dot in this context represents any character and the star or asterisks represents zero or more of those characters。

 and then I'm going to close that quote so this is going to be a pattern that looks for someone saying my name is and I'm going to try to extract from that the name right after and I'm going to pass in as input the words that they've said。

😡，If there are such matches， I am then going to。Print out， for instance， hey， comma。

 And then inside of my curly braces here， the first such match，0 contains another value。

 but matches bracket1 per the documentation for the R E library will indeed contain the first match that I care about。

 I'll go ahead and complete my thought there， close my parenthesis And at the beginning。

 because I want to format this string， add our familiar F。 else， if there are no matches。

 I guess we'll just have to make do and say something like hey， you and leave it as follows。

 All right， with one final flourish， let's go ahead and run this version here after clearing my screen。

 Listen dot pi and hit enter。😊，Hello there。 Nice to meet you。 My name is David。



![](img/f4dde6592256d1f95c23cf86a105feca_378.png)

Hey， David， as our final flourish。This then was all about practicing programming， a crash course。

 if you will， in Python specifically， but programming more generally。

 Python is indeed representative of quite a few languages out there and it is indeed so very popular nowadays for data science。

 for websites and so much more， and we hope that it serves for you as representative of not only what you can do with code。

 but probably what some of your colleagues， friends or family members are already doing every day and makes you all the more conversant in discussing just that and more with them。

😡。

![](img/f4dde6592256d1f95c23cf86a105feca_380.png)

Look at that five o'clock on the dot。All right， I think we're good unless there were pickups。Thanks。

 man， that was long。