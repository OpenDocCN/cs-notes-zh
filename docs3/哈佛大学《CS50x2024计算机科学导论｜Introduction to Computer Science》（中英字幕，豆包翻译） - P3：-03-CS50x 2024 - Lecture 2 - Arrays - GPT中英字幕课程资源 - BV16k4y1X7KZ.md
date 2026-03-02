# 哈佛大学《CS50x2024计算机科学导论｜Introduction to Computer Science》（中英字幕，豆包翻译） - P3：-03-CS50x 2024 - Lecture 2 - Arrays - GPT中英字幕课程资源 - BV16k4y1X7KZ

![](img/9bd24c440e3404fd993981bcfdb792d7_0.png)

![](img/9bd24c440e3404fd993981bcfdb792d7_1.png)

![](img/9bd24c440e3404fd993981bcfdb792d7_2.png)

All right， this is CS50， this is week two wherein we will ultimately learn how to use memory。

 but we thought we'd first begin with a bit of story time and in fact allow me to walk over to our brave volunteers who have joined us already。

 first here on my left we have who。Hi， I'm Akshaa。 I'm a first year in Matthews。

 and I'm planning on concentrating in chemical and physical biology and C。 S。

 wonderfulnderful welcome。 And let me have you hang on to the microphone first because we've asked Ashaia to tell us a short story。

 So in your envelope， you have the beginnings of a story。 If you wouldn't mind reading it aloud。

 And as she reads this， allow us to give us some thought as to what level Ashaa reads at。

 so to speak。 All right it's a long one， get ready。😊，One fish， two fish， red fish， blue fish。

All right， it's very well done。 What grade level would you say she reads at if you think back to your middle school。

 grade school， when maybe teacher said you read at this level or maybe this level or this one here。

It's okay， no offense taken yet。Are we sorry？First grade。 Okay， so first grade is just about right。

 And in fact， according to one algorithm， this text here， one fish，2 fish， redfish。

 blue fish would indeed be considered to actually be first grade or just before first grade。

 So let's and why is that， though， Why did you say first grade。😡，意思。Is very basic。

 But what is it about these words that are very basic。 Do you want to identify yourself。 Sure。

 they're all one syllable， and they're very simple like colors and stuff like that。 spot on。

 So like they're very short words， They're very short sentences。

 And you would expect that sort of of a younger person。 Allright。

 let's go ahead and hand the mic to your， your next volunteer here。

 If you'd like to introduce yourself。 Yes， hi， I'm Ethan。 I'm a first year in Canada。

 I will be concentrating in economics。 wonderfulnderful。 And in your folder。

 we have another story to share。😊，Congratulations， the is your day。 You're off to great places。

 You're off in a way。 So this text might sound familiar， particularly on the heels of high school。

 perhaps what grade level might he be reading at。😊，So maybe  fifth grade and why5th grade。O。Yeah。

 so a little more complicated， like the words， we've got some more punctuation。

 We have an apostrophe。 we have longer sentences。 and indeed， according to one algorithm。

 not quite fifth grade， but we would adjudicate your reading level to be third。

 but let's see if we can't do one final flourish here。

 if you'd like to introduce yourself in your story。 Hi， I'm Mike。 I'm also a first year。 I'm in Weld。

 and I'm planning on concentrating in biomedical engineering。 Welcome and your tale。



![](img/9bd24c440e3404fd993981bcfdb792d7_4.png)

It was a bright， cold day in April and the clocks were striking 13， Winston Smith。

 his chin nuzzled into his breast in an effort to escape the vile wind。

 slipped quickly through the glass doors of victory mansions。

 though not quickly enough to prevent a swirl of gritty dust from entering along with him。

So escalated quickly and someone's guess at this reading level。okay。

1984 is indeed the text in question。 And in what grade did you perhaps read that book。

So I'm hearing 8。 I'm hearing 10th to indeed，10th grade is what a certain algorithm would actually adjuddicate that reading level to be at。

 And consider now the heuristics。 So we started with very small words， very small sentences。

 very easy words。 and then things sort of escalated into more interesting。

 more sophisticated English， more interesting sentence construction and the like。

 So I bet if we could somehow capture those characteristics of text。

 the length of the words and the lengths of the sentences and the position of the punctuation。

 I dare say even using week1 material and today， week two material we'll be able to actually write code and implement an algorithm like that that can take these spoken words。

 put them to paper and actually analyze roughly what that reading level might be。

 So that's just a teaser of what lies ahead for now， allows us to thank our volunteers。

 each of whom gets a wonderful parting gift here to read it home。😊。



![](img/9bd24c440e3404fd993981bcfdb792d7_6.png)

All right， and thank you all so much。So with that said。

 there's another domain that we'll explore this week and indeed what you'll find in the coming weeks is that beyond just focusing on some of the fundamentals and the basics like we've really done the past couple of weeks talking about loops and conditionals and bullolean expressions really building blocks or puzzle pieces that we can assemble together we're going to increasingly start talking about applications of these ideas which after all is why any field is perhaps important and applicable so here for instance。

 we consider not only reading levels today and in turn in problem set two this week。

 but also the world of cryptography， which is the arts， the science of scrambling。

 encrypting information， andciphering it in such a way that you can send a message securely through the internet through the air through any medium。

 even though someone might intercept it ideally thanks through cryptography they shouldn't be able to decrypt it or actually determine what it there says So for instance。

 if you were to receive a message like this at first glance it's indeed a bit cryptic three words maybe。

😡。

![](img/9bd24c440e3404fd993981bcfdb792d7_8.png)

By's end we' have decrypted even this message for you。 So up until now， though。

 we've had some sort of conceptual training wheels on。

 And I gave us this picture last week when we introduced the tool make via which you can make programs out of your source code because you need to turn that source code into machine code。

 the zeros and ones。 And in the middle here was this thing called a compiler。

 But it really has been kind of an abstraction for us。

 And we've sort of had these metaphorical and sort of physical training wheels here in the sense that we haven't really needed to care like what the compiler is doing。

 how it works and so forth。 But today， what we thought we do is peel back a bit of that layer So that even though after today。

 you'll continue to be able to use commands like make and sort of return to the beautiful abstraction that is not caring about some of these lower level details will'll offer you a glimpse of how some of these things work because so that inevitably。

 when something goes wrong。 you've got some bug。 You're having some problem you'll have a bottom up understanding of what it could actually be。

 And indeed， these basics， you'll find。😊，Very often help you troubleshoot problems and really solve problems more generally。

 So here， for instance， is the code that we keep coming back to。

 And this code here is the simplest of C programs that just says hello world。

 This is the source code this we claimed was the corresponding machine code。

 And it was that program called a compiler that converted one into the other。

 But let's dive a little more deeply this week into what we mean by compiling code。

 like what is happening so that by days in， nothing really feels like magic anymore。

 It's not just that it goes from source code to machine code and that's that you understand like what's actually being done for you。

 And frankly， what other humans have done over the decades to make make as beautifully abstract and as simple as it now might seem to be。

 So here are the couple of commands that you've been in the habit of running when you want to first compile your code and then execute your code。

 But it turns out that make is actually running another command for you。

 The first of several white lies will tell in the course is that make itself is not a compile。

per se it's actually a program that automatically runs a compiler for you。 And by that， I mean this。

 let me go over to VS code here。 and let me create our familiar hello dot C program。

 And I'm going to go ahead and do include standard I O dot H。

 int main void and inside of the curly braces printf， Ho， comma world backslash N semicolon。

 So that's the code that we keep writing again and again。 And up until now。

 if I wanted to compile that， I would do make hello。😊，Dot slash hello and walla。

 Now my program is made and it actually executes。 But what's actually going on underneath the hood there is that make is running an actual compiler for you。

 And the reveal today is that the compiler we have been using is something called clang for C language。

 And this is just another program whose purpose in life is actually to do the conversion of source code to machine code。

 But it turns out that clang by itself can be used very simply， like you see here， clang hello do C。

 but it doesn't behave nearly is user friendly as you might like。 So in particular。

 let me go ahead and do this。 I'm gonna go ahead and remove my compiled program by running Rm for remove。

 which I alluded to briefly last time。 And then I'm gonna say why for yes， remove that regular file。

 And if I go ahead now and run just clang of hello do C and hit enter it seems to be successful。

 at least insofar as there's no error messages。 But if I try to do dot slash hello enter。

 there is no such file or directory called hello。 That is。😊，Because by default。

 clang somewhat goofly like just outputs a file name called a dot out like Y a。 well。

 it's sort of a simple name， a dot out， technically for asmbr output。

 But this just means this is the default file name that Kang is gonna give us。

 So okay it turns out I can do dot slash a dot out enter andila that now is my program。

 But thiss just kind of a stupid name for a program It's not very user friendly。

 It's certainly not an icon you would want to put on people's desktops or phones。

 So how can we do better。 Well， it turns out with Kang。

 We can configure it using what we'll call command line arguments and command line arguments are actually something we've been using thus far。

 we just didn't slap this word on it。 But command line arguments are additional words or sort of shorthand notation that you typed at your command prompt that's somehow modify the behavior of a program。

 And you can perhaps guess where this is going。 It turns out that if I actually want to create a program called hello not a dot out。

 which is the default。 I can actually do this。Clang， space， dash， lowercase O， space。

 hello or whatever I want to call the thing。 space， hello dot C。 And now if I hit enter。

 nothing seems to happen。 but now if I do dot slash hello and enter。

 Now I've actually got that program。 So why is make useful。 Well。

 it just saves us the trouble of having to type out this longger line of command。

 anytime we actually want to compile the code， but in fact。

 it gets even worse than that with commands like clang or compilers in general。

 because consider this code here， not just the version of hello world。

 but maybe the second version wherein last week， I started to get user input by adding the CS50 library using get string and then saying hello comma David。

 Well， if I go back to Vs code and I modify this program to be that same one。

 So let me go ahead and include CS 50 do H at the top。

 let me get rid of this simple print line and instead give myself a string called name equals。

 get_ string。What's your name， question mark just like we did in scratch， then I can do printf。

 quote unquote， hello comma， and previously I typed world。

 I obviously don't want to type David because I wanted to be dynamic。

 what did I type last week for as a placeholder。😡，So yeah， just not command S， but percent S。

 So percent S in this case， which is a placeholder for any such string。

 Then I can still do my new line， close quote comma。

 and then I can substitute in something like the value of the name variable。 Allright。

 so if I go ahead now and compile this。 Now， last week， I could just do make hello。

 and I'm on my way。 It work just fine。 But if I instead do clang manually。

 it turns out that this is not gonna be sufficient now， clang dash O hello space hello dot C。

 exact same thing I typed a moment ago。 But I think I'm gonna see some errors。

 So what's this error hinting at here。 Well， at the very bottom， it's a bit arcane with its output。

 And much of this you can ignore。 but there are some certain keywords。

 What's the first maybe keyword， you recognize in these three lines of erroneous output。

 So it's mention main， that's not that much of a clue because that's the only thing I wrote so far。

 Second line， though， get string。 if there's some issue with an undefined reference to get string。



![](img/9bd24c440e3404fd993981bcfdb792d7_10.png)

Now， why might that be， I did include C S 50 dot H。

But that's apparently not enough to teach the compiler about get string。 Well。

 it turns out that if you're using a third party library。

 one that doesn't necessarily come with C the language， something like C 50s。

 it turns out that additionally have to tell the compiler that you want to use that library and not just by including the header file。

 but by an additional command as well。 So when you run Kang。

 you want to provide an additional rather command line argument， literally L for library。

 which is a term I use last week， C 50， a library is just code that someone else wrote that you want to use in your project。

 So if I really want to compile this version that uses the CS 50 library。

 I can still do clang o hello hello dot C。 but before I finish my thought。

 I need to tell the compiler to link so to speak in the library C S 50。

 and now I hit enter the error message goes away， I can do dot slash hello。

 I can type in my name And we're back to week1。 And this is why suffice it to say we introduce make。

 which is not。CS5 this is a popular tool that the real people in the real world use to automate these kinds of processes。

 So unbeknownst to you make has been using the O for you make unbeknownst to you has been using L CS50 for you just because it makes our lives easier but today we thought we would deliberately sort of peel back this layer so at least understand what's going on behind this abstraction that is make itself and compiling more generally so let me propose that compiling itself is not quite what we've described it to be compiling is like this catch all phrase that apparently I claim goes from source code to machine code。

 but if we really want to get pedantic， which well do briefly but this is not a sign of things to come because this too will we abstract away compiling is just one of four steps that are involved in turning source code that you and I write into those zeros in ones but through an understanding of these four steps today you'll hopefully better understand how to troubleshoot issues like that and just kind of know what's happening。

It's not， in fact， magic。 It's just the result of years of humans developing these four steps here。

 So when you run make what's happening。 or in turn， when you run clang。

 four different things are happening。 And the first one is called preprocessing。

 So what is this all about。 Well， let's consider this code here。

 And this code's a little bit interesting in so far as it's one of the more complicated examples from last week。

 And you'll notice， for instance， that I had include standard Io at the top。 So I could use printf。

 I had main down here， whose purpose in life was just to meow three times。 and then recall。

 we made our own Miow function just like we did in week 0 with scratch that just printed out quote unquote Miow。

 But I also included this line here， which we called what。This was a。Prototype。

 and why did I have to include it there or equivalently。

 what would happen if I didn't include a prototype up at the top there yeah。关。Exactly。

 if I didn't include it up here， the program when trying to compile main would not know what Miow is because it's not defined until later。

 So this is kind of like a little hint of what is to come。 Ally。

 we could just move this whole thing up at the top of the file。

 But I claim that that just devolves into a big mess eventually once you have many different functions。

 Like you can't realistically put them all at the top to solve this problem。

 So these prototypes solve that problem。 So nothing new here。

 just a reminder of what motivated this one line of prototype。

 Now let's consider this simpler program， which is just the one we wrote most recently in VS code。

 This program prompts the human for their name and that says hello to that person。

 but it has two includes at the top of the file。 And in fact。

 any line of C that starts with this hash symbol is what we'll call now a preprocessor directive。

 It's not really a word you need to remember in your vocabulary。

 but it is a little bit different from most every other line because it starts with that hash。

 That's sort of a special symbol in C。 And what this means。I the following this very first line。

 CS50 dot H is indeed a file that I and CS50 staff wrote。

 and we installed somewhere in VS code for you， somewhere in the cloud。



![](img/9bd24c440e3404fd993981bcfdb792d7_12.png)

![](img/9bd24c440e3404fd993981bcfdb792d7_13.png)

And I've claimed you need to use this header file in order to use get stringing。So just logically。

 what is probably inside of CS50 dot H。Yeah。Super close。

 So the function called get string that does the getting of a string。

 but it's not quite as much as the function itself。 It's actually a little bit less than that。

 But you're on the right track。 What is inside of C 50 dot H。Presumably。Just a what。

Just a prototype4。😡，For which function。Getstr。 So admittedly， there's some other stuff in there， too。

 But the important line for today's discussion is that inside of CS50 dot H is indeed one line of code that defines what the return value。

 what the name is and what the arguments。 If any are to get string and some other stuff。

 And so what happens effectively， when you compile your code。 step 1 is this preprocessing line。

 And essentially， there is some code that someone else wrote inside of the clang compiler that looks for a line that starts with hash include。

 And when it sees that it goes and finds this file。

 and effectively copies and pastes the contents of that file right there into your code。

 so that you don't have to go find the file， copypy and paste it and make a mess of your own code。

 So in particular， it's effectively as though you're copying and pasting the prototype of get string to the very top of your file there by teaching the compiler that it exists by that same logic。

 What is probably in standard I O dot H。The prototype 4。For print F。 And indeed， exactly that。

 So this line effectively gets replaced with the equivalent of the prototype for printf。

 which for today's purposes is a bit more complicated。

 So let me wave my hand at the dot dot dot just because it takes a variable number of arguments。

 depending on how many placeholders or format codes you have。

 But effectively that too is what's happening。 So the preprocessor step。 Step 1 of4。

 just does that find and replace， if you will。 Now there's again， some other stuff in that file。

 and this too is kind of a white lie printf probably has its own file。

 because that's a really big library， But the essence of it is exactly this。

 So preprocessing converts all of those hash include lines to whatever the underlying prototypes are within the file plus some other stuff。

 Now， compiling。 we use it as this catch all phrase。

 But it turns out it has a very specific meaning that's worth knowing about even though after today。

 you can go back to using compiling as the sort of catch all phrase。

 So when you've got this same code here after the preprocessing step has happened。

 So this is essentially happening。In the computer's memory。

 it's not changing your hello dot C file permanently or anything like that。

 This code gets quote unquote， compiled into something that looks more like this。

 And this is a scarier language that we won't spend time on in this particular class。

 This is what's known as assembly language。 And back in the day before there was C。

 humans wrote this to program their computers，  Similarlyly before there was assembly code back in the day。

 humans very initially used what instead。😡，So zeros in ones like they actually wrote the machine code painfully。

 be it in code or be it in punch cards like physical objects or the like。 So again。

 these are sort of abstractions， but we're rewinding for today in time。

 but what this compiler for C is doing is converting C into this other language called assembly language and even though this looks very esoteric there's at least some juicy things in here if I highlight get string is mentioned in this code print F is mentioned in this code and even some of these keywords here that are spelled a bit weirdly this relates to subtracting and moving something in memory and calling a function calling a function So there's some semantics that are probably somewhat familiar even though this is not code we ourselves will write。

 But unfortunately this is not yet machine code and that's where step3 comes in So step3 of this force。

 that process is technically called assembling and thesembling just takes that assembly code and converts it thankfully to the thing we do care about the zeros in ones。

Assembling takes assembly code， converts it to zeros and ones as an aside。

 And I alluded to this earlier， The reason that clang names its files a do out by default asser output is kind of a side effect of that being one of the steps in this process dealing with assembly language and it subsequent output。

 All right， so here are some zeros and ones。 But unfortunately。

 there's still that fourth and final step， which is a word that I also used earlier， namely linking。

 So let me take a step back and look at this code here。 And even though this code is exactly。

 as I wrote in V S code in hello dot C。 So no copying and pasting。

 no prototypes have been plugged in here。 This is my code， technically。

 there's three different files involved in compiling even something relatively simple like this。

 There's obviously this thing itself， hello dot C， which I wrote， there's apparently C50 do H。

 and there's apparently standard I O dot H。 But technically。

 and you don't have to know this file name per se， somewhere else on the computers hard drive。

 So to speak， is。A CS50 do C file， which actually contains the staff's implementation of Getstr and Get int and getflow in all of those other functions somewhere on the server's hard drive is standard Io do C that implements printf in all of these other functions as well。

 So the dot C is just inferred from the dot H here。 you don't ever mention the do C file。

 but someone else wrote those files， someone else stored them in the server for you。

 CS50 staff in this case。 So technically even when compiling a relatively short program like this。

 you're really combining three files at least at the end of the day。

 and I'll write them from left to right。 hello do C， which I wrote which CSs50 do C。

 which the staff wrote and then standard io do C as well。

 So somewhere there's these three files and clang or compiler needs to compile each of these into the corresponding zeros and ones。



![](img/9bd24c440e3404fd993981bcfdb792d7_15.png)

![](img/9bd24c440e3404fd993981bcfdb792d7_16.png)

Lastly， this is not yet sufficient because these zeros and ones haven't been linked together。 I mean。

 I deliberately left a gap here to imply that these are three separately compiled files。

 So that fourth and final step called linking， takes all of these zeros and ones。

 and an intelligent way combines them into just one final file names hello names a dot out。

 whatever the file name is of choice。 So what you and I。

 for the past week have just been calling compiling。

 And that's what a typical normal person will use henceforth to describe this whole process。

 technically， there's these four different steps underneath the hood。

 each of which is sort of a representative of an evolution of technology over the years。

 And nowadays， if we fast forward a few weeks in class， when we start talking about Python。

 which is another more modern language， that， too is gonna to be conceptually even higher level。

 even though underneath the hood， there's gonna be some lower level principles at work。

So any questions on just terminology or these processes。Known as compiling， yeah。Sure， compiling。

 if I rewind， is the process of taking your source code， which looks like this recall。

 whoops this and converting it into assembly code。 So preprocessing just converts all of those hash include lines and a few others to their equivalents。

 So that step one， compiling converts the C code into the underlying assembly code。

 the assembly step， step 3 converts the assembly code to zeros and ones。

 and then the fourth step linking combines all of the zeros and ones from the one， the two。

 the three or more files that are involved in your project and links them all together for you magically。

 But at the end of the day， all of this is sort of happening automatically for you。

 If I jump now to the end here， whereby just by running make， which in turn runs clang for you。

 like all of this is abstracted away。 But the key here is that even with these commands that we've been running。

 be it's the make command or the。😊，And command， everything should be explainable。

 what you are typing at the prompt ultimately， each of those things has a purpose。

 So any questions then on what we've just now called compiling。

Even though it's only when you take another CS course that you might spend more time on assembly language or these lower level details。

啊，对啊对。A good question。 Are there other types of compilers。 Yes， back when I took C S 50。

 I used a popular compiler called GCC， the Ga new compiler collection。

 which still exists actually in the code space that you're using for C50。

 Kang is somewhat more recent。 It's gaining popularity。 And frankly。

 we use it in large part because its error messages are slightly more user friendly。

 you might not believe us， because if you encountered some errors with your code this past week。

 they were probably just as arcane as the error message I saw。

 but it's better than it was some years ago。 And there's alternatives to compiling too。

 But more on that， when we get to Python as well。😊，Other questions。All right。

 Well what are the implications of the fact that we're going from source code to machine code？ Well。

 it stands to reason that if you can compile code， maybe you can decompile it。

 that is going the reverse direction to go from zeros and ones to actual source code Now that would be handy if you want to go in as a program like change something in a program that you or someone else already wrote。

 it's maybe not ideal for your intellectual property。

 though if you are the person who wrote that program in the first place if you are Microsoft and you wrote Microsoft Word or Excel that people with Mac and PCs and phones have installed on their devices。

 know it doesn't actually sound very appealing if any old customer can take those zeros and ones and reverse them reverse engineer them so to speak into the original source code because then they can have their own version of Microsoft Word and make changes to it without really having put in all of the R and D that might have taken to build the first version thereof。

 but it turns out that reverse engineering So sort of doing things in the opposite direction is easier。

Then done because there are multiple ways， as you've seen already to implement programs like loops alone。

 you can use for loops， while loops， even do while loops。 And so there's other ways。

 there's multiple ways to solve the same problem。 So even if you try to reverse engineer or program and convert machine code back to source code。

 there's not necessarily going to be an obvious way to do so。

 And the reality is that it ends up being such a mess because you lose the variable names。

 typically you lose the function names typically that what you end up looking at might very well be C code。

 but it's completely difficult for you， even a good programmer to read and generally the sort of mindset is if you're really good enough to decompile code in that way and read it subsequently even without good variable names。

 good function names， good documentation and the like you could probably have just implemented the program in the first place yourself without jumping through those hoops。

 So there's sort of some practicality pushing back on what are otherwise potential threats to say your intellectual property。

 But that's not。The case later on in the term when we do get to languages like Python to some extent。

 other languages like jascript， some of those are actually going to be readable by anyone。

 any of your customers， any of your friends any of your family that actually use your programs。

 So with that said， let's introduce now another tool to our toolki that will hopefully make some of the pain from this past week when you did encounter bugs a little more manageable and indeed。

 part of the process of writing code to this day is debugging it。

 And it is a rare thing to write a program， be it in C or any other language and get it 100% write the first time。

 I mean， to this day， I still 20 plus years later， still write buggy code。

 hopefully a little bit less of it。 But anytime you're adding a new feature。

 anytime you're doing something for the first time。

 you're not necessarily going to see all of the possible mistake。

 So even in industry bugs are omnipresent which is really to say having techniques to debug code that is eliminate bugs is super compelling。

 Now， just for a bit of history Here ismiral。

![](img/9bd24c440e3404fd993981bcfdb792d7_18.png)

![](img/9bd24c440e3404fd993981bcfdb792d7_19.png)

Grace Hopper， who was actually in not only the military。

 but also a faculty of Harvard years ago and worked on a Harvard computer called the Harvard Mark1。

 which is actually on display at the School of engineeringing and applied scientists If you take a tour over there sometime but also when working on the Harvard Mark2 she is known for having at least popularized the phrase bug to mean a mistake in a computers program in a mistake in a computers code and the etymology of this supposedly is this here log book wherein she and her colleagues were sort of documenting processes being computerd on computers that a moth actually got stuck in one of the relays。

 one of the the electric relays inside of the very old now computer and someone very cleverly wrote first actual case of bug being found。

 So it wasn't she who actually discovered it。 but this was a story she was thereafter fond of telling is a famed computer scientist thereafter we now know bugs to be all too。

Far when it comes to writing our own code。 And I thought I would deliberately write some buggy code based on some of the programs with which we experimented last week。

 So let me go back over to VS code here and let me propose that I do something somewhat simplistic。

Just like this to print out a column of bricks of height 3。 So I'm going into VS code。

 and I'm going deliberately call this program buggy dot C because I intend to do this poorly。

 I'm going to include standard I O do H as before， int main void as before and in here。

 if I want to print a pyramid of height 3， I'm gonna do four int I gets all right。

 I'm still new to programming in my mind here。 So like I know I'm supposed to start counting it0 okay and I want to do this until I count up to three。

 So I'm gonna do that。 and then I plus plus I remember from class in this way。

 And now I might go ahead and print out just a hash mark back slash n。

 which I do want because I want to move this cursor to the next line to make this vertical。

 But of course， if you' noticed with your I already。

 when I do make buggy it compiles okay So no typos， no syntactical errors。 But when I run this。

 I'm gonna see how many bricks。So for in this case。 Now。

 this is meant to be a simplistic example so that we don't spend time trying to figure out what the bug is。

 but rather focus on techniques for actually identifying the bug。 So finding rather the bug。

 So what's one of the first tools in your toolkit。 literally one you have already。

 printf is your friend。 And it is a very quick and dirty tool for just seeing what's going on inside of the computer when you don't have more sophisticated tools or even the time to use them。

 And so in this case， for instance， what I'd propose is that all right。

 I'm obviously seeing four hashes。 and let me play a little slow here。

 it'd be helpful for me to understand why logically I'm ending up with four。

 even though I'm starting at 0， like I remember from class and I'm going up to3 as we did in class like I'm just not seeing it in in this particular story。

 So what I would commonly do， is going into my code。 and just help me see what's going on。

 And I might literally write us print Fline like I is percent I backlash N comma。

And then just print out the value of I。 I just want to see on every iteration， what is I， What is I。

 What is I， just to help me see what the computer already knows。

 So let me go ahead and recompile buggy， let me rerun buggy。

 and then let me make my terminal window bigger just to make clear what's going on。

 And now it's a little more pedantic。😡，Now I is 0。 I get a hash。 I is 1。 I get a hash。 I is 2。

 I get a hash， Wait a minute。 I is 3。 I get a hash。

 So clearly now it should be maybe more obvious to you。

 especially if the syntax itself is unfamiliar。 I certainly don't want this last one printing or maybe equivalently。

 I don't want the first one printing。 So I can fix this in a couple of ways， but the solution。

 the most canonical solution is probably to do what with my code。😡，To change what to what， yeah。Yeah。

 so change the less than or equal sign to just a less than sign。

 So even though this is like counting from 0 to，3。 instead of one through 3。

 it's the more typical programmatic way to write code like this。 And now。

 of course if I do make buggy andll increase my terminal window again dotlash buggy now I see what's going on inside of the code。

 now it matches my expectations。 And so now the bug is gone。 Now， of course。

 if I'm submitting this or shipping it， I should delete the temporary printf and let meclaim that using printf in this way。

 just to help you see what's going on， is generally a good thing。

 But generally adding a printf and a printf and a printf and a printf like it starts to devolve into just trial and error and you have no idea what's going on。

 So you're just printing out everything， let me propose that if you ever find yourself slipping down that hill into just trying this。

 trying this trying this， you need a better tool not just doing printf。 And frankly。

 it's annoying to use printf because every time you add a printf， you have to re。Hild the code。

 rerun the code。 It's just adding to the number of steps。 So let me propose instead that we do this。

 I'm gonna go back into VS code here， and I'm gonna to write a different program that actually has a a helper function。

 So to speak a second function。 whose purpose in life is maybe just to print that column for me。

 So I'm gonna say this void print column though I could call it anything I want。

 And this function is gonna to take a argument or a parameter called height。

 which will tell it how many bricks to print how many vertical bricks。

 I'm going do the same kind of logic for int I equals 0。

 I is less than I'm gonna make the same mistake again less than or equal to height I plus plus。

 And then inside of this for loop， Let me go ahead and print out the hash mark。

 So I've made the same mistake。 But I've made it in the context now of a helper function only because in main。

 what I'd like to do now just to be a little more sophisticated is get int from the user for the height。

😊，And when I do get that ant， I want to store in a variable called N。

 but I do need to give that variable a type like last week。 So I'll say that it's an integer。

 And now lastly， I can print， underscore column passing in actually。

 I'll call it H just because height is H print column H semicolon。😡，Okay。

 so it's the exact same program， except I'm getting user input now。 So it's not just going to be 3。

 It's going to be a variable height， but I've done something stupid。I've done two stupid things。

 So this， of course， is not supposed to be there。 So I'll fix that and someone else。

 What else have I done。Yeah， I'm missing the prototype。 And this is。

 let me reiterate probably the only time where copy paste is okay。

 Once you've implemented the function， you can copy paste its first line at a semicolon so that it teaches the compiler that this function will exist。

3 stupid things。 Okay， thank you， so。Good。Include CS5。h， and now anyone want to go for four。No。

Alright， slightly unintended here。 So let's see make buggy。 Okay， no syntax errors。

 Thanks to you all。 So the code compiles。 But of course。

 when I run buggy and I type in something like three manually， I'm still gonna get 1，2，3，4 out。

 So let me now introduce a more powerful tool that's generally known as a debugger。

 And within the VS code environment that you're using。

 We actually have a command that makes it a little easier to use this tool。

 but we didn't write the tool itself， you are about to see a very graphical。

 a very popular industry standard tool called the debugger。

 but we'll start the debugger using a C50 specific command called debug 50。

 which just makes it easier with a single command to start the debugger without having to configure a text file with all of your preferred settings and all of that。

 It's just an annoying hoop otherwise to jump through。

 So what I'm gonna to do is go back to my code here。

I have already compiled it but just for a good measure。

 I'll make buggy again because the debugger needs your code to be compiled。

 It's not gonna help with syntax errors like the stupid mistakes I just made unintentionally。

 it will help you with programmatic errors， logical errors in your code once your code is running。

 So to run debug 50， I'm gonna do this debug 50 space。

 and then the exact same command I would normally run to just run the program itself。

 So dotlash buggy So exact same thing dot buggy， but I prefix it now with debug 50。

 when I hit enter a whole bunch of another error is gonna pop up on the screen。

 which is a good reminder because this will happen to you too invariably it's reminding me that I have to set what's called a break point。

 And as that word suggests it is the point at which you want your code to break。

 not break in make the situation worse sense。 but rather where do you want to pause execution。

 break execution， like hitting the brakes on a car。 So the program doesn't run all at once。

 and you can put this any number of places and you might have done。



![](img/9bd24c440e3404fd993981bcfdb792d7_21.png)

Acciddentally， if you've ever hovered over the gutter of VS code。

 the left hand side next to your line numbers， see the little red dot that appears。

 If I click on any of these lines， that's going to set a break point。 so to speak。

 And I want to break execution at main。 So I'm just gonna click to the left of line 6 in this case that makes it a darker red circle a stop sign of sorts that tells the debugger to pause execution on that line。

 though I could put it elsewhere if I so choose。 Let me go ahead and rerun debug 50 dot slash buggy enter。



![](img/9bd24c440e3404fd993981bcfdb792d7_23.png)

And now a bunch of things are gonna happen on the screen。 It's gonna to look a little overwhelming。

 perhaps at first glance。 but there's some useful stuff that just happened。 So one。

 my code is still here， but the line that I set the break point on is rather the first line of actual executable code at or below the break point I set is highlighted in this yellowish green here。

 which says this line of code has not yet been executed。 We broke at this point。

 But if I click a button， this line of code will be executed because up until now every C program you write runs as fast as that。

 I want to pump the brakes and pause here。 But notice a few other aspects of the window here。

 So notice that up here， some weirdness there's mentions a variables and we're familiar with these local is a term we'll use this week。

 But there's this variable H， which weirdly， where did the value 21912 come from So it turns out in C。

 before you initialize a variable with a value。I literallyterally typing the number three or by using a function like get int。

 It often contains what's called a garbage value more on those in a couple of weeks。

 But a garbage value is you can think of it as like remnants of whatever was in the computer's memory before you ran your program。

 And that's a bit of oversimplification。 but you cannot trust that a variable will have a certain value in this case。

 if you did not put ones there yourself。 So for now， it is sort of nonsensical。 It's a garbage value。

 it means nothing。 But once I execute this line， it should contain whatever the human types in。

 All right， down here， there's a watch section， which is a more sophisticated feature down here is what's called the call stack more on that in the future。

 But what this means for now is that I'm executing the main function， not for instance， print column。

 So notice up here， these are the most useful controls within the interface。

 if I hit this play button， it's just gonna actually run my program to the end of it without bothering me further。

 However， I can actually step over this line of code and execute it。

 or I can step into this line of code and actually。around the contents of get int。

 if it's available on the system。 So conceptually， you can either execute this line or you can dive down conceptually deeper and see what's inside of that function。

 Lastly， this will let you step out。 This will allow you to restart the whole process。

 and this will just stop the debugger。 So these buttons are gonna be our friends。

 And the one I'll click first， is the first 1 I described， which is step over。

 So step over doesn't mean skip this step。 It just means execute it。

 but don't bother me by going into the weeds of what is on the specific line， namely get in。

 So when I click this button in a moment， you'll see that my terminal， which is still at the bottom。

 prompts me for a height。 I'm gonna go ahead and type 3。

 As soon as I hit enter what part of the screen probably will change。Based on what I've said。So H。

 the variable H should hopefully take on the number 3。

 And I'll probably see a different line of code highlighted。

 probably line 9 next once I'm done executing line 8。

 So let me go ahead and hit enter and watch the top left of the screen。

Andvoila H now has the value 3 and execution has now paused on line 9。

 because the debugger is allowing me to step through my code line by line。 Now。

 let me go ahead and print out。 Let me go ahead and just say， all right， I'm done with this。

 Let's go ahead and run the rest of the program。 It clearly got the value 3， but wait a minute。

 And at this point， it close the window in which I would have seen the output。

 I would have still seen four hashes。 So let me actually do this again。

 Let me go back into debug 50 by running the exact same command again。 It's gonna think for a moment。

 It's gonna reconfigure the screen。 I'm gonna do the exact same thing。 I'm gonna step over this line。

But I'd like to actually see what's going on inside of my print column function。 So this time。

 instead of just saying run to the end and close all the windows on me。

 let me go ahead and step into my print column function。 So don't step over step into。

 because if I step over。 And now this is what I meant to show earlier。

 you can see that it's still printing out4。 So in fact， let me undo this。

 Let just stop the whole thing。 Let me rerun the command a final time。

 So it goes back to where we began before。 It's gonna prompt me again once I step over line 8 for a number like3。

 But this time， instead of stepping over line 9， let's poke around。 I wrote print column。

 So let's look at print column step by step。 step into it and watch what happens to the yellow highlight。

 It now jumps logically to the inside of print column there letting me walk through this code。

 And now I can just step over each of these lines one at a time。 So Step over。 Okay。

 so what did it do。 It did that whole narrative that I did verbally。Last week。

 where it compared I against height， it then when inside of the loop， when I step over。

 watch what happens in my terminal，1 hash prints out。 Now， line 14 is highlighted again。

 It's comparing per the Boolean expression。 I is it less than or equal to height。 If so。

 it's going to go ahead and print out the hash。 It's going to do this again， Print out the hash。

 But notice at the top left of the screen。 He is still the same。 It's still3。

 But what has been changing， apparently。I on each iteration。

 So the debugger is letting me see what's going on slowly inside of this loop because I keeps getting incremented。

 So if I step over this line now， notice that I've now printed3。 So ideally， I want this loop to end。

 But if I click step over once more， notice that the value of I at top left is3。

 But three is less than or equal to height。 Oh， now I get it， if I play along here。

 now I see why less than or equals to mathematically is clearly incorrect。

 and as soon as that light bulb goes off， you can just sort of bail out。

 click the red stop button to turn the debugger off， go back in， fix your code and voila recompile。

 run it and you're back in business。 So the takeaways here really are just what tools now exist。

 Printf is your friend， but only for quick and dirty sort of debugging techniques。

 get into the habit now of using debug 50 and in turn VS codes debugger。

 you will invariably not take this advice。 say for problem set two。



![](img/9bd24c440e3404fd993981bcfdb792d7_25.png)

As you first begin because， you know， it's gonna feel easier and quicker just to use printf just to use printf。

 Just to use printf。 And the problem with that logic is that you begin to build up like technical debt。

 So to speak， where you really should have learned it earlier。

 You really should have learned it earlier。 You really should have learned it earlier at which point you end up spending more time wasted using printf and doing things manually。

 Then if you just spent 10 minutes，30 minutes， just learning the user interface and the buttons of a proper debugger。

 So please take that advice because it will save you significant amounts of time over time。😊。

Questions on print F or debugging in this way。Any questions on this？No， okay。

 so let me give you a third and final technique for debugging。

 which has kind of been looming over us here for some time。

 So there is actually this technique known as rubber duck debugging。

 and in the absence of a roommate who's taking C50 or who has taken C50 or knows how to program in the absence of having a TF or T A or C A sitting next to you in the absence of having a family member available to ask questions of if you have simply an inanimate object on your desk goes the tradition。

 just talk to that inanimate object better yet if it's an adorable rubber duck in this way。

 And the idea of rubber duck debugging is that simply by verbalizing。

 literally out loud to this inanimate object probably with the door closed and no one knowing that you're talking to this rubber duck。

 you invariably end up hearing any ill logic in your own thoughts at which point the proverbial light bulb tends to go off and you're like。

 oh I'm an idiot， it's supposed to be less than not less than or equal to。

 So literally just explaining to a duck or any inanimate object。

Going on in your code will quite frequently just help you see in your mind's eye what it is you've been doing wrong。

 So rubber duck debugging is indeed a very effective technique。

 even if you don't happen to have a small or large rubber duck Of course。

 you're also welcome to use the C S 50 duck who lives at C 50 AI and also within a pain in V S code at C 50 dev。

 you can ask the CS 50 duck about concepts you don't understand， or you can even copy。

 pay certain lines of code with which you might be having trouble and ask the duck for its own advice。

 All right， so with those tools in our toolkit， let me propose now that we do that we introduce now a few lower level features of C itself and better understand how we can start solving some of those problems like the readability of text or the encryption of data。

 These were our socalled types last week， when we introduced at least a subset of them or use them。

 just to store data in a certain format。 so to speak。 like in week 0。



![](img/9bd24c440e3404fd993981bcfdb792d7_27.png)

That everything at the end of the day is just zeros and ones binary。

 And I claim sort of conceptually that how a computer knows if a set of bits is a number versus a letter versus a color or a sound or an image or a video is just context dependent Like are using Photoshop or using Microsoft Word or something else。

 But last week， we saw a little more precisely that it's not quite as broad strokes as that is's more about what the programmer has told the software。

 is being stored in a given variable。 Is it an integer， I it a char， a character。

 Is it a whole string， I it a longer integer or the like， So you now have this control。

 The catch though recall， though， is that each of these types has only finite amount of space allocated to it。

 So， for instance， an integer is typically4 B and 4 B is 32 B because it's 8 times 432 B we claim is roughly 4 billion。

 But if you want to represent negative and positive numbers。

 the biggest integer you can store is like。2 billionion now。

 that's really big for a lot of applications。 But you， years ago， Facebook， for instance。

 was rumored to be using integers when they had you know fewer users。

 but now that they have billions of users， three plus billion users and integer is no longer big enough for the Facebooks。

 the Googles， the Microsoft and so forth of the world， So we also have longs。

 which use twice as money bytes， but exponentially bigger range of values。 Meanwhile， a bull。

 interestingly， as a byte， which is kind of bad design in what sense。



![](img/9bd24c440e3404fd993981bcfdb792d7_29.png)

![](img/9bd24c440e3404fd993981bcfdb792d7_30.png)

![](img/9bd24c440e3404fd993981bcfdb792d7_31.png)

Why might that be bad design。It's it should only be 21 B rather because a 0 or 1 should suffice。

 turns out it's just easier to use a whole by， even though we're wasting 7 those bits。

 but bulls are represented nonetheless with one by Chars are gonna be1 B Fs tend to be4 B。

 doubles tend to be 8 B， Some of this is system dependent。 But nowadays on modern computers。

 This tends to be a useful rule of thumb。 The only1 I can't commit to here is a string because a string recalls a sequence of text。

 And maybe it has no characters，1 character to10100。

 So it's a variable number of bys presumably where each by represents a given character。

 So with that said， how do we get from an actual computer to information being represented therein。

 Well， let me remind us that this is what's inside of our Mac PC's phones。

 even though this isn't a scale， and it might not be the same shape。 This is memory。

 randomand access memory。 And on these black chips on the circuit board here are the bys that we keep talking about。

 In fact， let's go ahead and zoom in on one of these chips。Fill the screen here。

 And just for artist's depictions's sake， let me propose that if you've got， I don't know。

 a megabyte， a gigabyte， like a lot of bytes packed into this chip nowadays。

 it stands to reason that no matter how many of them you have。

 we could just number them from top to bottom。 And we could say that this is by 1 or you know what this is by 0。

1，2，3， and this is maybe by 1 billion or whatever it is。

 So you can think of memory as having addresses or just locations。

 numeric indices that identify each of those bys individually。

 Why a by individual bits are not that useful。 So 8 again。

 one byte tends to be the de facto standard。 Let me So for instance。

 if you're storing just a single character， a char。

 it might be stored literally in this top left corner。 So to speak of the chip of memory。

 if you're storing maybe an integer 4 bys， it might take up that many bys， if you're storing along。

 it might take up that many bys instead。 Now we don't have to dwell on the particulars of the circuit board in。

😊，Traces and all the connections。 So let me just kind of abstract this away and claim that what your computer's memory really is is just kind of this canvas。

 I mean， kind of in the Photoshop sense。 if you've ever made pictures。

 it's just a grid of pixels up down left right， that's really all your memory is。

 It's this canvas that you can manipulate the bits on to store numbers anywhere you want in the computer's memory。

 So， in fact， let's zoom in here。 and let's consider how your computer is actually storing information using just these bytes at the end of the day。

 no matter how sophisticated your Mac， your PC， your phone is like this is all it has access to for storing information。

 It's a canvas of bytes and what you do with this now， really invites design decisions。

 So let's consider this Here is an excerpt from a program wherein maybe I'm prompting the user for three scores。

 like three test scores， exam scores， something like that。

 and the purpose in life of this program is maybe to average those three scores together。

 if you want to get a sense of where you stand in some class。 So we can certainly。😊。

Wip up some code like this。 And in just a moment， let me go ahead and flip over to VS code here。

 and I'll write up a new program called scores C。😡，And in this。

 let me go ahead and first include standard I O dot H。In main void at the top。 And in here。

 let me go ahead and assume that it's up in the greatest semester。 So my first score。

 which I'll call score1 was a 72。 My second score was a 73， but my third score score 3 was like a 33。

 now you might remember these numbers in another context， they might spell the message。

 but in this case， it's just integers。 It's just numbers because I'm telling the computer to treat these as ins。

 Now if I want to figure out what my average is， I can do a bit of math。

 So let me just print out that my average is and I don't want to shortchan myself。

 I'm not gonna to use percent I because I don't want to lose even anything after the decimal points。

 you're gonna use a float instead And my average I claim will be score1 plus score2 plus score 3 divided by3 semicolon with parentheses because just like grade score math like order of operations。

 I parentthesize the numerator。 so I can divide the whole thing by3。 But I have screwed up already。

 I am gonna short change。😊，And not give myself as high a grade as I deserve， but this one's subtle。

What have I done wrong？Yeah， I might want to cast these scores to floats， right。

 because if you do integral math， divideivide an integer or the sum of an integer sum integer by an integer。

 it's going to be an integer as the result。 So it's going to throw away anything after the decimal point。

 even if it's something。1， something。5， something。9， that fraction is going be thrown away。

 There's a bunch of ways to fix this。 I could just use floats or doubles for all of these。

 I could cast score 1 score2 or score3 as you proposed， frankly。

 the simplest way is just change the denominator。 because so long as I've got one float involved in the math。

 This will sort of promote the whole arithmetic expression to being floating point math instead of integer math。

 So let me go ahead now and do make scores enter so far so good dot scores。

 And my average seems to be not great， but 59。3333。 So in the third。

 but I would have lost that third。 if I hadn't used a float in this particular way。 Well。

 let's consider now what's actually going on inside of the。Computer。

 when I store these three variables。 So back to the grid here。

 just my canvas of memory doesn't really matter where things end up。 I might put it here。

 I might put it there。 The computer makes these decisions。 But for the artist's sake。

 I'm gonna put it at the top left hand corner here， so。Score 1 is containing the integer 72。

 Why is it taking up four squares， though。Because。It's an integer。 And on this system。

 an integer is 4 by。 So I've drawn it to scale， if you will。 Score2 is the number 73。

 It also takes 4 B。 by coincidence， but also by convention。

 it will likely end up next to the first integer in memory because I've only got three variables going on anyway。

 So the computer quite likely will store them back to back to back。 And indeed， by that logic。

 score 3 containing the number 33 is going to fill in this space here。 We'll consider down the road。

 what happens if things get fragmented， something here， something here or something here。

 But for now， we can assume that this is probably contiguous， though not necessarily so。 All right。

 so that's pretty straightforward。 But what's really going on。 Well， these are just bys of memory。

 that is bits of memory times 8。 And so what's really going on is this pattern of zeros and ones is being stored to represent 72。

 This pattern of zeros and ones is being stored to represent 73 and similarly 33。

 But that's a very low level detail that we don't really。😊，Ca about。

 So we'll generally just think about these as numbers like 72，73，33。 All right。

 so if we go back to the actual code， though， here。I wonder if this is the best idea。

 These three lines of code are correct。 I got my 59 and a third for my average。

 which I claim is correct。 But code wise， this should maybe rub you the wrong way。

 even if you hadn't programmed before C， S 50。😊，Why might this not be the best approach to storing things like scores。

In a program。How might this get us in trouble， yeah。Yeah。

 it's not the best because you have to use a whole bunch of different variables for each score。

 They're almost identicalally named， though， but just imagine in almost any question involving the design of your code。

 what happens as M。 The number of things involved gets larger。

 am I really gonna start writing code that has score 4， score 5， score 6， scoreore 10， score 20。

 I mean， your codes just gonna look like this mess of mostly copy paste except that the number at the end of the variable is changing。

 like that should make you cringe a little bit because it's not gonna end well eventually in typographical errors are gonna get in the way。

 Most likely because we'll make mistakes。 So how can we do a little bit better than that。 Well。

 let me propose that we introduce what we're gonna now call an array。

 An array is a sequence of values back to back to back in memory。

 So in array is just a chunk of memory。😊，Storing values back to back to back。 So no gaps。

 no fragmentation from left to right， top to bottom， just as I already drew。

 But these arrays can see， at least are going to give a slightly new syntax that addresses exactly your concern。

 So here instead， is I would propose how you define。A one variable， not three。

 one variable called scores plural。😡，Each of whose values is gonna be an int。

 and you want three integers tucked away in that variable。

 So now I can sort of pluralize the name of my variable because by using square brackets in the number3。

 I'm telling the compiler， give me enough room for not one， not two， but three integers in total。

 And the computer is gonna do me a favor by storing them back to back to back in the computer's memory。

 Now， assigning values to these variables is almost the same。

 but the syntax looks like this to assign the first value。 I do scores。

 bracket 0 equals whatever 72 scores， bracket 1 equals 73， scores bracket 2 equals 33。

 and it's square brackets consistently。 And notice this is a feature or a downside of C。

 We very frequently use the same syntax for slightly different ideas。

 This first line tells the computer， give me an array of size 3。

 These next three lines mean go into this array at location 0 and put this value there location。1。

 put this value there。 Lo2， put this value there。 So same syntax， but different meaning。

 depending on the context here。 But the equal sign。

 indeed means that this is assignment from right to left， just like last week。

So what does this mean in the computer's memory？😡，Well， in this case here。

 we now have a slightly different way of doing this。 And actually， let me do it first in code。

 Let me go back to V S code here， and let me propose that。

Instead of having these three separate variables， let me give myself an int scores variable of size 3。

 and then do scores bracket 0 equals 72， scores bracket 1 equals 73， scores bracket 2 equals 33。

 And now I have to change this syntax slightly。 But same idea。 scores， bracket 0。Scores bracket1。

 and lastly scoreses， bracket2。 So a couple of key details。 I started counting at 0。

 Y that's just the way it is with arrays。 You must start counting at0。

 unless you want to waste one of those spaces。 and what you definitely don't want to do is go into scores bracket 3。

 because I only ask the computer for three integers。 if I blindly do something like this。

 you're going too far。 you're going beyond the end of the chunk of memory and bad things will often happen。

 So we won't do that just yet， But for now，01 and2 are the first second and third locations。

 So if I recompile this code。 So make scores seems okay。

 dots scores and I get the exact same answer there。

 But let me make it more dynamic because this is a little stupid that I'm compiling a program with my scores hard coded。

 What if I have a fourth exam tomorrow or something like that。

 So let's make it more dynamic And I think the syntax will start to make a little more sense。

 Let's go ahead and use get int and ask the user first score。 Let's go ahead。

Get in and ask the user for another score。 Let's go ahead and get in and ask the user for a third score now storing the return values in each of those variables。

 If I now do make scores。😡，D't it？Mistake。Similar to one I've made before。

 but we didn't see the error message last time。 Would I do wrong， yeah。



![](img/9bd24c440e3404fd993981bcfdb792d7_33.png)

Okay， what did I do wrong have about over here。Yeah， so I'm missing the C 50 header file。

 So how do you know that， Well， implicit declaration of function get in。

 So it just doesn't know what get in is。 Well， who does know what get into is the C S 50 library。

 That should be your first instinct。 Allright， let me go to the top here and let me go ahead and squeeze in the C 50 library like this。

 Now， let me clear my terminal， make scores again。 We're back in business。 And notice。

 I don't need to do dash L C S 50 anymore。 Make is doing that for me for Kang。

 but we don't even see clang being executed， but it is being executed underneath the hood。



![](img/9bd24c440e3404fd993981bcfdb792d7_35.png)

So to speak， All right， so dot slash scores， here we go。72，73，33， math is still the same。

 But now the program is more interactive。 Now， this， too， hopefully should rub you the wrong way。

 This is correct。 I would claim。😊，But bad design still sort of reeks of week 0 inefficiencies， yeah。

Okay， so I could ask the human how many scores do you want to input。 Let's come back to that。

 But I think even in this construct， what better could I do。

Use a loop because I'm literally doing the same thing again and again。

 and notice this number is just changing slightly。 I would think that a little plus plus could help there。

 get in score， get in score， get in score。 That's the exact same thing。

 So a loop is a perfect solution here。 So let me go over into this code here。

 And I can still for now declare it to be of size 3。

 but I think I could do something like this 4 int I get0。 I is less than3。

 So I'm not gonna make the same buggy mistake as I made earlier。 I plus plus inside of the loop now。

 I can do scores bracket I and now aer getting really interesting because you can use and reuse them。

 but dynamically go to a specific location equals get int quote unquote score。

 Now I can type that phrase just once。 and this loop ultimately。

 we'll do the same thing but it's getting better。 The code is getting better designed because it's more compact。

 And I'm not repeating myself，72，73，33 still works the same。

 but we're iteratively improving the code here。Now， how else there's one？

Design flaw here that I still don't love。 It's a little more subtle。 Any observations。



![](img/9bd24c440e3404fd993981bcfdb792d7_37.png)

Interesting， so instead of dividing by 3。0， maybe I should divide it by their array size。

 which at the moment is technically still 3。 but I do concur that that is worrisome because they could get out of sync。

 but there's something else that still isn't quite right， yeah。I'm okay。

 moving to this zero indexed model。 So this is a new term of art to index into an array means to go to a specific location。

 So here I'm indexing into location I， but I is going start at 0 and then 1， and then  two。

 I'm actually okay with that。 even though in common day life， we would say score 1， score，2。

 score 3 as a programmer。 I just have to get into the habit of saying score 0， score 1， score2 now。

 But something else， yeah。

![](img/9bd24c440e3404fd993981bcfdb792d7_39.png)

I could also compute the average in a loop because indeed I this is kind of only going solving the problem halfway。

 I'm gathering the information in the loop。 but then I'm manually writing it all out。

 So it does feel like there should be a better solution here。

 But let me also identify one other issue。 I really don't like。 and this is indeed subtle。

 I've got three here。 I've got three here。 And I essentially have three here。

 albeit be at a floating point version。 This is just ripe for me making a mistake eventually and changing one of those values。

 but not the other two。 So how might I fix this。 I might at least do something like this。

 I could say integer， maybe n for scores。 I'll set that equal to3。 I could then use n here。

 I could use n here。 I could use n here， but that's a step backwards because I don't want an in because I'm going run into the same math issue as before。

 but I could convert it。 that is cast it to a float。 and we did that briefly last week。



![](img/9bd24c440e3404fd993981bcfdb792d7_41.png)

But there's one other thing I could do here that we did introduce last week。

 This is better because I don't have a magic number kind of floating around in multiple places。😊。

Yeah， if I really want to be proper， I should probably say this should be a constant intoteger Y because I don't want to accidentally change it myself。

 I don't want to be collaborating with a colleague and they foolishly change it on me。

 This just sends a stronger signal to the compiler do not let the humans change this value。

 And now just to point out one other feature of C， if you have a number like this。 like the number3。

 I've deliberately capitalize this variable name really for the first time。

 anytime you have a constant， it tends to be a convention to capitalize it。

 just to draw your attention to it， it doesn't mean anything technically capitalizing a variable does nothing to it。

 but it draws attention visually to it to the human。 So if you declares something as a constant。

 it's commonplace to capitalize it just because Moreover。

 if you have a constant that you might want to occasionally modify maybe next semester when there's four exams or five exams instead of three。

 it actually is okay sometimes to define what might be called a global variable。

 a variable that is not inside of curly braces。

![](img/9bd24c440e3404fd993981bcfdb792d7_43.png)

It's literally at the top of the file outside of mainine and despite what I said about scope last week。

 a global variable like this on line floor， a line4 will be in scope to every function in this file。

 so it's actually a way of sharing a variable across multiple functions。

 which is generally fine if you're using a constant if you intend to change it。

 there's probably a better way than actually using a global variable。

 but this is just in contrast to what I previously did which I would call by contrast。😡。



![](img/9bd24c440e3404fd993981bcfdb792d7_45.png)

![](img/9bd24c440e3404fd993981bcfdb792d7_46.png)

A local variable。 But again， I'm just trying to reduce the probability of making mistakes somewhere in the code。

 And I do agree。 I don't like that I'm still adding all of these scores manually。

 even though clearly I had a loop a moment ago。 But for now。

 let's at least consider what's been going on inside of the computer's memory。 So with this array。

 I now have not three variables， score 1， score2 score 3， I have one variable。

 an array variable called scores plural。 And if I want to access the first element。

 it scores bracket 0。 If I want to access the second element， It scores bracket 1。

 if I want to access the third element， it scores bracket 2。

 If I were to make a mistake and do scores bracket 3， which is the fourth element。

 I'd end up in kind of in no man's land here， and worst case your program could crash or some something weird will happen。

 spinning beach balls， those kinds of thing， just don't make those mistakes。

 And C makes it easy to make those mistakes， So the onus is really on you programmatically。Questions。

On these， this use of arrays。Question on this use of race。 Yeah， and back。A really good question。

 Is there any way to create an array just by using syntax alone without prompting the human for it。

 short answer。 Yes， if you want to have an array of integers called， for instance， array。

 you could actually do like 1342，50， something like this， This would give you an array。

 If you use this syntax。 This would give you an array of size 3 where the three values by default are 1342 and 50。

 It's not syntax will use for now， but there is syntax like that。 It's not quite as user friendlyend。

 though， as other languages。 if you've indeed programmed before。

Other questions on this use of arrays。Yeah， in front。Is there a way to copy what？😡，Oh。

 is there a way to calculate the length of an array。 Short answer。 No。

 And I'm about to show you one demonstration of this。

 Those of you who have programme before in Java in Java script and certain other languages。

 is's very easy to get the length of an array。 You essentially just ask the array。 What's its length。

 C does not give you that capability。 The onus is entirely on you and me to remember。

 as with another variable like N how long the array is。 And so， in fact， let me go ahead and do this。

 I'm gonna go ahead and open up sort of baking style， a program that I wrote in advance here。

 which kind of escalates quickly， but there's not really too many new ideas here。

 except for the array specifics。 So this is scores dot C premade this time。 and notice what I have1。

 I've included C 50 dot H and standard I O dot H at the top。 So that's the same。

 I have declared a constant called n set equal to 3。

 That is now the same as of my most recent change。 I did introduce an。



![](img/9bd24c440e3404fd993981bcfdb792d7_48.png)

Average function， which was one of the remaining concerns that I could compute the average with some kind of loop to。

 That average function is gonna return a float， which is what I want。

 I'm want my average to be a float with the fraction。 But notice this in answer to your question。

 If I want a function called average to do something like iterate over an array step by step by step。

 add up all of the numbers and divide by the total number of numbers。

 I need to give it the array of numbers。 And I need to tell it how many of those numbers are。

 So I literally have to pass into values。 Meanwhile， this code is the same as before inside of main。

 I'm declaring a variable called scores of size N。 I'm iterating from I to N。 and actually， y。

 and then in this loop， I'm assigning each of the scores。 a return value of get in。

 The last line of main is this print out the average with percent F。

 But don't just do it manually by adding and dividing with parentheses。 Call the average function。

Pass in the length of the array and the array itself and hope that it returns a float that then gets plugged into percent F。

 So I would claim that pretty much all of this， even though it's a lot， should be familiar。

 There's no real new ideas except for this use of the global variable now。 And this average function。

 So let me scroll down to the average function， because this is the takeaway from this final example。

 In this example here。Let me scroll up to the average function。

 copy pastted the prototype for the very first line， and here's how I'm computing the average。

 There's different ways of doing this， but here's kind of an accumulator way on line 28。

 I'm declaring a variable inside of the average function called sum and I'm just initializing it to0 why mentally I want to add up all of the person' scores and then I want to divide by the total and that's my mathematical average。

 So here's my loop where I'm iterating from0 up to。

 but not through the length so that should be three times I am adding to the sum variable。

 whatever is at the eighthh location， so to speak of the array， so this is array bracket 0。

 a bracket1 array bracket2 on each iteration and then the last thing I'm doing is kind of a nice one liner。

 I'm dividing the sum which is an int which is the sum of 72。

7333 divided by the length which is three， but three is not a float， so I cast it to a float。

 so that the end value， hopefully is gonna to be 59。



![](img/9bd24c440e3404fd993981bcfdb792d7_50.png)

Po3，3，3，3，3，3， and so forth。 So the only thing that's weird syntactically is this， though。

 when you define a function and C that takes an argument that isn't just a simple char。

 isn't just a simple integer。 It's actually an array。

 You don't have to know the array's length in advance。

 You can just put square brackets after the name you give it。 And I don't have to call it array。

 I could call it X or y or Z or anything else。 I call it array just to make clear that it's an array。

 But you do need to know the length。Somehow。Okay， questions。On combining those ideas。In that， there。

Wei。Any questions？No， all right。 Well， we've only dealt with numbers thus far。

 It would be nice to actually deal with letters and， and words and paragraphs and the like。

 much like our readability example。 But I think first。

 some snacks and some fruit are served in the transs。 So we'll see you in 10。 See you in 10。😊。

Alright， so we're back and up until now we've been representing just numbers underneath the hood。

 but we've introduced arrays， which gave us this ability。

 recall to store numbers back to back to back。 So it turns out you actually had this capability for the past week。

 even though you might not have realized it。 And let me propose that we first consider very simple example of three chars instead of three integers。

 And for simplistically， I'm going to call them C1 C2 and C3 just for the sake of discussion。

 But I'm going to put our familiar characters H exclamation point in those variables using single quotes。

 because again， that's what you do when using individual chas to make the point that I can store three chars in three separate variables。

 So let me go ahead and go over to VS code here。 and let me create something called high dot C。

 And in this program I'll first include standard I O do H in main void as before。

 And then inside of main， let's just do exactly that char C1 equals quote unquote capital H char C2 equals unquote capital I。

Char C 3 equals quote unquote， exclamation point。 So clearly not the best approach。

 but just for demonstrations sake。 And here now that you understand for hopefully from week 1。

 that really number and really from week 0， that numbers are just letters。

 which can be something more too。 We can really just use our basic understanding of C to tinker with these ideas now and see them such that there is indeed gonna be no magic happening for us ultimately。

 So let me go ahead and print out three characters， percent C， percent C， percent C。😊，Backslash n。

 and then print out C1 C2， C3。 So I've got three separate placeholders。

 and we haven't really had occasion to use percent C。

 but it means put char here unlike percent S which is put a whole string here or percent I put an integer。

 Let me go ahead and make hi No syntax errors， dot slash high and it should print out high in exclamation points because I'm printing out just three simple characters。

 but per our discussion as far back as we 0。 letters are just numbers and numbers are just letters。

 it just depends on the context in which we use them。 So let me change this percent C to an I。

 and I'm gonna add a space just so that you can obviously separate one number from another change this to I change this to I。

 but still print out C1 C2 C 3。 So no integers per say。 let me just print out those chas。

 Let me do make high No errors， dot slash high。 And now I see 72，73，33。

 So in the case of chas and ints， you can actually treat one。As the other。

 so long as you have enough bits to fit one in the other。

 you don't have to cast even or do anything explicitly。

 you do have to cast one sort of converting an integer to a float to make clear to the compiler that you really intend to do this because that could be destructive if it can't quite represent the number as you intend。

 But in this case here， I think we're okay just poking around and seeing what's going on underneath the hood。

 Well， what is going on underneath the hood memory wise。 Well， something very similar。

 Here's that canvas of memory， and maybe we got lucky and it's in the top left hand corner like this。

 C1， C2， C3。 But these are just three individual characters。

 but we're getting awfully close to what we last week called a string， which are just characters。

 a sequence of characters from left to right。 And in fact。

 I think if we combine sort of this revelation that these are just numbers underneath the hood back to back to back。

 combined with the idea of an array from earlier， we can start to kind of see what's really going on because indeed underneath the hood。

 This is just a number 。

![](img/9bd24c440e3404fd993981bcfdb792d7_52.png)

273，33。 And really， if we go lower level than that， it's these three patterns of zeros and ones。

 That's all that's going on inside of the computer。

 but it's our use of int that shows it to us as an integer。

 It's our use of char that makes it clear that it's a cha or equivalently percent I and percent C respectively。

 But what exactly is a string。 Well， it's really just a sequence of characters。

 And so why don't we go there。 let me propose that we actually give ourselves an actual string。

 call it S will'll use double quotes this time。 So if I go back to B S code here。

 let me shorten this program and just give myself a single string S。

 said it equal to high exclamation point in double quotes。 and then below that。

 let's go ahead and print out percent S backlash n and then S itself and then turns out for reasons we'll soon see。

 I do need to include the C 50 library。 So as to use the actual keyword string here。

 even though I'm not using get string， but more on that another time。 But if I now do。



![](img/9bd24c440e3404fd993981bcfdb792d7_54.png)

Make high。 It does compile dots slash high。 and it still prints out the exact same thing。

 But what's going on inside of the computer's memory when I use a string called S instead of three chars。

 or you can kind of think of the string as taking up at least three Bs。 H I exclamation point。

 but it's not three separate variables， It's one variable， But what is this really look like now。

 especially if I add back the yellow lines。 S is really just。😊，An array of characters。

 So we called it a string last week。 And I claim today that this is kind of an abstraction in the C 50 library that's giving us this phrase string。

 But it's really just an array of size at least three here where S bracket 0。

 presumably gives me the H S bracket1 is the I S bracket 2 is the exclamation point。

 But just by saying string， all of that happens automatically。

 I don't even need to tell the computer how many chars are going to be in the string all at once。

 So in fact， let me go over to maybe a variance of this program。 And we can see this syntactically。

 So instead of printing out the whole string with percent S。

 let me actually be a little curious and print out percent C， percent C， percent C。

 and then change S to S bracket 0， S bracket1， S bracket 2， which is not better in any sense。

 This is way more tedious now， but it does demonstrate that I can treat S here in week 2。

 as though it's an array， which means even in week 1， it was an array， we just didn't know it。😊。

We didn't have the syntax with which to express that。

 So if I now do make high still compiles dot slash high same exact output。

 but I'm now just kind of manipulating the string in these different ways because I know a string is just an array of character So I could treat S with the square bracket notation。

 But how do I know how does the computer know where high ends。

 and this is where strings get a little dangerous like a char is one byte。

 no matter what one char one character， that's it。 But a string。

 recall my question mark from earlier could be no bytes if it you would think could be zero bytes if you have nothing in it inside the quote。

 it could be one character to1010 like I claimed But how does the computer know where strings end。

 like how does the computer not know that the string is not the whole row of memory here。

 How does it know that it ends here Well， it turns out all this time when we've been using quote unquote string and using get string from the CS50 library there's actually。



![](img/9bd24c440e3404fd993981bcfdb792d7_56.png)

A special sentinel value at the end of every string in a computer's memory that tells the computer string stops here and the sentinel value And by Sentinel。

 I just mean special value that the world decided on decades ago， is all0 bit。

 If you have a byte with all zero bits in it， that means string ends here。

 So the implication is that the computer now using a loop or something can print out char， char。

 char done because it sees this special value。 If it didn't have that it might blindly go char， char。

 char， char， char printing out values of memory that don't belong to that given string。

 So I was correcting myself verbally a moment ago， because I said that this string is of length 3。

 It's three B but it's not every string in the world both last week and now this is actually n plus1 B where n is the actual human length that you care about H exclamation point or three。

 but it's always going use one extra byte for this socalled zero value。😊，At the end。

 and this zero value as very tedious to write as0 as 8，0 bits。

 So we would actually typically just write it as a 0。

 but you don't want to confuse a0 on the screen is actually being like the number 0 on the keyboard。

 And so we would actually typically write this symbol with a backslash 0。

 So this is the charbased representation of0。 So it means the exact same thing。

 This is just C notation that indicates that this is 80 bits。

 but the slash just makes clear that it's not literally the number 0 that you want to see on the screen。

 It's a sentinel value that is terminating this here string。

 So now what can I do once I know this information。 Well， I can actually even see this。

 Let me go back to this code here in V S code。 Let me change these percent Cs to percent I just like before。

 And now we'll see again， those same numbers make high dot slash high。 there are the three。

 I can technically poke around a little bit further。 percent I  one more。

 And let's look at S bracket 3。 I。😊。

![](img/9bd24c440e3404fd993981bcfdb792d7_58.png)

Not exaggerating earlier。 when I said in general， if you go past the end of an array。

 bad things can happen。 but in this case， I know that there is one more thing at the end of this array。

 because this is how strings are built。 This is not a C S 50 thing。 This is a thing in C。

 Every string in the world in double quotes ends with a back slash 0。 That is 8，0 bits。

 So if I really want， I can see this by printing out s bracket 3。

 which is the fourth and final location。 if I recompile my code now make high dot slash high。

 I should see 72，73，33 and0， That's always been there。

 So I'm always using4 bys somewhat wastefully but somewhat necessarily so that the computer actually knows where that string ends。

 So if we go back to the memory representation of this year。

 it's just as though you have an array of integers being stored contiguously back to back to back。

 the last one of which means this is the end of the array of characters。 but because I'm using。



![](img/9bd24c440e3404fd993981bcfdb792d7_60.png)

![](img/9bd24c440e3404fd993981bcfdb792d7_61.png)

Qu unquote string， because I'm using percent S and C。 I'm not seeing these numbers by default。

 I'm seeing H exclamation point unless I explicitly tell printf。 No， no， no， show me with percent I。

 these actual integers。 This then is how you can think about the string。

 Like you don't really need to think about it as being individual characters。 This is just S。

 and it has some length here。 but it does not necessarily an array that you yourself have to create。

 you sort of get it automatically just by using a string。

 Now there's just not to add onto the jargon。 this backslash 0， these 80 bits。

 there's actually a technical term for them。 You can call them null。

 It's typically written in all caps like this。 confusingly in a couple weeks。

 we're gonna see another word pronouncedun null but spelled N UL L Left hand wasn't talking right hand years ago。

 But N U means this is the0 byte that terminates strings that indicate the end of a string。

 And fun fact， you've actually seen this before。Even though we glossed over it。

 here's that ASCII chart from last time， if I focus on the leftmost column。

 guess what is the zero ASII character？😡，N， U， L， you never see N U L on the screen。

 It's just how you pronounce 8，0 bit。WQuestions。On this representation of strings， yeah。

Our string structured differently in other languages。 Yes， they are more powerful in other languages。

 In C， you have to build them yourself in this way。 More on that when we get to Python。

 Other questions， yeah。Really good question。 Does that mean we don't have a function to get the length of a string。

 Do we have to create it。 Short answer。 There is a function， but you have to。

 someone had to write code for it。 You can't just ask the string itself like you can in Javascript or Java。

 What is the。YeahYou can。 It's actually more similar to Python than it is to jascript or Java。

 but we'll see that in just a few minutes。 In fact。 So let's introduce maybe a couple of strings。

 So here's two strings in the abstract called S and T。

 And I've initialize them arbitrarily to high and by just so we can kind of explore what's gonna actually happen underneath the hood。

 So let me go back to V S code， let me just completely change this program to be that instead。

 So string S equals unquote string T equals unquote by in all caps。

 And then let's print them both out very simply percent S backlash N S print out percent S backlash N T just so we can see what's going on。

 if I do make high dotlash， I should of course， see these two strings。

 But what's going on inside of the computer's memory。

 Well in this computer's memory assuming these are the only two variables involved And assuming the computer is just doing things top to bottom hi is probably going be stored somewhere like this。

 And my canvas of memory by is。😊。

![](img/9bd24c440e3404fd993981bcfdb792d7_63.png)

Going to be stored there and it's wrapping around， but that's just an artist's representation。

 but notice that it is now really important that there is this null byte at the end of each string because it's how the computer is going to know where high ends and where by begins Otherwise you might see high by all on the screen at once。

 if there weren't the sentinel value indicating to printf stop at this character。

 But that's all that's going on in your program when you have two variables in this way。 And in fact。

 what's really going on and things get a little more interesting here。

 if I were to want two of these things Not that I could refer to them to as a So S bracket 0，1。

2 and even three t bracket0，1，2 and even3 and 4。 But if I want to actually really kind of blend some ideas just kind of playing around with these basic principles now。

 notice what I can do in this version， if I know I've got two arrays in VS code。



![](img/9bd24c440e3404fd993981bcfdb792d7_65.png)

Don't strictly need to do string S and T and U and V。

 right That's kind of devolving back into the scores1， scores 2。

 scores 3 mantra where I had multiple variables， almost the same name。

 even though I'm using different letters of the alphabet。

 What if I want what if I do this string words。 And if I want to store two words in the computer's memory fine。

 create an array of two strings。 But what is a string， a string is an array of characters。

 So it's getting a little bit a little bit trippy here。

 But the ideas are still gonna be the same Word bracket 0 could certainly equal high Word bracket1 can certainly equal by。

 just like the scores example。 And then if I want to print these things with percent S。

 I can print out words bracket 0。 And then I can print out percent S backlash N， words bracket1。

 and the example is not going be any different in terms of its output。 But I've now avoided S and T。

 I now just have one variable called words containing both。Of these here things。

 And if I really want to poke around， here's where things get even more sort of visually overwhelming。

 but just the logical extension of these same ideas right now is the previous version where I had two variables S and T。

 if I now use this new version where I have one variable called words just like this here。

 the picture should follow logically like this。 words bracket 0 is this string。

 Word bracket 1 is this string。 But what is each string。 It's an array of characters。

 And so you can also think of it like this。 where this H is words bracket 0， bracket 0。

 So the0 character of the0th word。 And this is words bracket 0，1 words bracket 0，2， words bracket 0。

3。 And then words bracket 10。 So it's kind of like a two dimensional array almost。

 you can think about it that way of helpful。 But for now。

 it's just applying the same principles to the code。 So if I go to my。😊。



![](img/9bd24c440e3404fd993981bcfdb792d7_67.png)

HereAnd I've got my high and my by。 This is gonna look a little stupid。

 but let me change this percent S to percent C percent C percent C and print out words bracket 0。

 words bracket0， bracket1。 words bracket 0 brackets2 to print out that three letter word。

 And now down here， let me print out percent C percent C percent C percent C because it's four letters in by exclamation point。

 This is words bracket 1， but the first character， words bracket1， the second character。

 words bracket1， the third character in words bracket1， the fourth character。

 It's hard to say when you'retyping a different number， but that's what we get by using0 indexing。

 So to speak。 make high， no mistakes high， says the same thing。 So again， there's no magic。

 Like you are fully in control over what's going on inside of the computer's memory。

 And now that we have this array syntax with square brackets， you can both create these things。

 and then manipulate them or access them however you so。😊，Choose。Questions。

On arrays or strings in this way。Yeah， over here。Good question。

 Can you have an array with multiple different data types， Short answer， no longer answer sort of。

 but not in nearly the same user friendly way as with languages like Python or Javascript or others。

 But so assume for now， array should be the same type in C。Other questions Yeah， over here。Oh。

 really good question。 It will So for those who can hear if you were to look past the end of one array。

 would you start to see the beginning of the second， in this case。

 maybe the word by could depend on the particulars of your code in the computer， let's try this。

 So let's get a little greedy here and go one past H I exclamation point null character by looking at words bracket 0。

3， which should actually be our null character。 So that's gonna be there。 And actually。

 let's see let's go ahead and do this。 make hi dot slash high， still works as expected。

 but let me change this to integer integer。 So we can actually see what's going on。 integer。

 now if I recompile， make high， I should see the same thing but numerically。

 And now what I think you're proposing is let's get a little crazy and go even past that to what could be location 4。

 But we know semantically doesn't exist。 But maybe is bumping up against by。 So make high。😊。

Dot slash high。 And guess what 66 is。Its well just the B， but yes， its 66。

 recall is capital B because in week 0， capital A was 65。

 So indeed now we're really poking around and you can get crazy。

 Like what's 400 characters away and see what's going on there。 eventually。

 your program will probably crash。 And so don't poke around too much。

 But more on that in the coming days。 All right， Well。

 how about some other revelations and problem solving now。

 coming back to the question about strings length earlier。

 And we'll see if we can then tie this all together to something like cryptography in the end and manipulating strings for the purpose of sending them securely。

 So let me propose that we go into V S code here again in a moment。

 And I'm gonna create a program called length。 Let's actually figure out ourselves the length of a string initially。

 So I'm gonna go ahead and code length do C， I'm gonna go ahead and include C 50 dot H。

 I'm gonna include standard I O dot H in main void。 And then inside of main。

 I'm gonna prompt the user for their name， get string unquote name。😊。



![](img/9bd24c440e3404fd993981bcfdb792d7_69.png)

And then I'm going to go ahead and。I want to count the length of this string。

 but I know what a string is now。 It's char char char char。 and then eventually the null character。

 So I can look for that。 And I can write this in a few different ways。

 I know a bunch of different types of loops now， but I'm going go with a while loop by first declaring a variable n for number of characters set it equal to0。

 like starting to count with your fingers all down。

 And I want to do the equivalent of this counting each of the letters that I type in So I can do that as follows while the name variable at location n does not equal quote unquote back slash0。

 which looks weird， but it's just asking the question is the character at that location equal to the so-called null character which is written with single quotes and backlash0 by convention。

 And what I want to do while that is true is just add one to n。 And then at the very bottom here。

 let's just go ahead and print out with percent I the value of n。Presumably。

 if I type in high exclamation point， I'm starting at 0， and I'm going to have H I exclamation point。

 null character。 So I don't increment N a fourth time。 So let's go ahead and run down here。

 make length。Dot slash length。 enter well， I guess I'm asking for name。 So I'll do my name for real。

 David，5 characters。 and I indeed get five。 If I used a four loop， I could do something similar。

 but I think this while loop approach much like our counter from the past is fairly straightforward。

 But what if I want to do this。 What if I want to make another function for this。 Well。

 I could do that。 Let me all right， let's do this。 let's write a quick function called string length。

 It's gonna take a string called S or whatever as input。 And then you know what。

 let's just do this in that function。 I'm gonna borrow my code from a moment ago。

 I'm gonna paste it into this function。 But I'm not gonna print out the length。

 I'm gonna return the length。 So I have a helper function of sorts that's gonna hand me back the length of the string。

 And that's why this returns an int but takes a string as its argument。 How do I use this。 Well。

 first， I do need to copy the prototype。 So I don't get into trouble as before， semicolon。

 and then in my main function。 What I think I can do now。😊，With something like this。

 I can do int length equals， get the string length。Of the name variable that was just typed in。

 And now using print F percent I print out length， semicolon。 So exact same logic。

 the only thing I've done that's different this time is I've added a helper function。

 just to demonstrate how I can take some pretty basic functionality。

 Find the length of a string and modularize it into a function， abstracttract it away。

 So I never again have to copy paste that for loop。

 I now have a function called string length that will solve this problem for me。

 dot slash whoops strong program。 make length。😊，Ha use of undeclared identifier name。

What did I do wrong， Apparently on line 16 of length do C。What did I do wrong here， Yeah in front。

Good。Rare。Good， perfect terminology。 So name is local to main。 The scope of name is main。

 Those sound similar but different words。 And so I'm actually should be calling this S because S is the name of the local variable being passed in even though it happens to be one in the same as name because online 9。

 I'm indeed passing in name as the argument。 Allright， so this is where again。

 copy paste can sometimes get you into trouble， let's try to make length again now it works do slash length D V I D And now we have a function that seems to be working。

 But this is such like commodity functionality like my God。

 like surely someone before us has written a function to get the length of a string before。

 and indeed， other people have。 So it turns out that in C， just as you have the standard I O library。

 you also have a string library whose header file is called appropriately string dot H。 In fact。

 C5 has documentation there in its own manual pages。

 So to speak along with some sample usage thereof。 But it turns out in the。😊，String library。

 there is a very popular function analogous to the Python one that you asked about earlier called Stling where Stling。

 one word no underscores just figures out the length of a string。 And honestly。

 I've never looked at its source code， but it probably uses a while loop， maybe uses a for loop。

 but it certainly uses the same idea of just iterating that is walking from left to right over a variable in order to figure out what the length of a given string is。

 So how do we use this。 if I go back to the S code here。

 I can throw away the entirety of my string length function。

 I can throw away the prototype therefore， and I can include a third header file string dot H inside of which I claim now is this function called St length that I can just now use out of the box for free because someone else wrote this function for me and string dot H will teach the compiler that it exists。

 So if I now do make length and dotlash length now I have a similarly。

Program that doesn't bother having me write unnecessary code。

 So this is another example of a library。 The string library is just going to make our lives easier。

 but not having to for us not having to reinvent some wheel。 All right， Well。

 where else does this get interesting。 How about something like this。

 Let me go back into V S code here。 Let's create a program called string dot C。

 We'll play around with our own string that's going start similarly。 So let's include Cs 50 dot H。

 Let's include standard I O dot H。 Let's include string dot H。

 So we can use that same Stling function in main void。 And inside of this， let's do this。

 Let's get a string S and prompt the user for any old string as input。Alright。

 and then let's go ahead and maybe print out quote unquote， output。

 And I'm just gonna line up my spaces just right because these words are slightly different length。

 But we'll see why I'm doing this is just for aesthetics sake in a moment。

 And let's go ahead now and do this。 If I want to print out every character in a string。

 How can I now do this。 Well， this is actually pretty common task。 Even though this version thereof。

 well seem pointless for int I get 0。 I is less than the length of S I plus plus is just the conventional way to start a loop that iterates from left to right over a string of that length。

 And then let's go ahead and print out each character percent C。😊。

Printing out the string at location I using our fancy new array syntax。

 And at the very end of this program， let's just print out a new line character just to move the cursor to the bottom。

 like we've done in the past。 So this is kind of a stupid program。

 Like I am reinventing the wheel that is the percent S format code。

 I already know that printf can print out a whole string。 S it didn't。

 supposeupp I forgot about percent S。 And I only knew about percent C。

 These lines of code here collectively will print out the entirety of a string character by character based on its length。

 So if I if I compile this program， make string dot slash string and type in my name。 for instance。

 David， The output is D A V I D。 And here's why I hit the space bar an extra time because I wanted input an output to line up nicely。

 so we could see that they're， in fact， the same length。

 So let me just stipulate This code is correct。😊。

![](img/9bd24c440e3404fd993981bcfdb792d7_71.png)

But there is an inefficiency with this line of code。 Let's talk about design， instinctively。

What is maybe bad about this line of code 9， line 9 that I've highlighted。This one is subtle。

Let's go over here。Yeah。I'm calling Stlang inside of the loop again and again and again。

 Why well recall how four loops worked When we walked through it last week。

 that middle part of the for loop in between the semicolon keeps getting checked。

 keeps getting checked， keeps getting checked。 And so if you put a function call there。

 which is totally fine syntactically， you're asking the same damn question again and again and again。

 and the length of David D ID is never changing。 So Stl implemented decades ago by some other human has some kind of loop in it。

 and you're literally making that code run again and again， and again。

 just to get the same answer 5 again and again。 So I think your instinct is right。

 I could come up with another variable outside of the loop， I could do something like this。

 int length equal Stl of S。 And then I could just plug that in。

 But there's a slightly more elegant way。 if you like doing things with slightly less code。

 This is correct， as I've now written， It's less more efficient。

 because I'm only calling Stling once now on this new line 9。 but a。



![](img/9bd24c440e3404fd993981bcfdb792d7_73.png)

common way to write this would typically be to do something like this。After initializing I。

 you can also initialize something else like length。 And you can set length equal to stirl of S。

 Then your semicolon。 And now you can say while I is less than that length。

 or I can tighten this up further。 if it's just a number， and it's a super short loop。

 might as well just call it N。 So this now would be sort of a canonical way of implementing the exact same idea。

 but without the inefficiency， because now you're calling stirl in the initialization part of your for loop。

 not inside of the Boolean expression that gets checked and executed again and again， yeah。😊，Correct。

 well， I'm declaring I as an int。 but by way of the comma， I am also declaring n as an int。

 So they've got to be the same type for this trick to work。Good observation。 Other questions。

On this one here。Now， all right， Well， let's kind of play around further here。

 Let me propose that there's other libraries and header files as well that you might find useful。

 There's also something called C type， which relates to types and C's。

 that's got a bunch of useful functions that we can actually see if we visit the documentation here。

 But before we get there。 let me actually whip up a program that maybe does something a little bit fun albeit low level like forcing some string to uppercase。

 If the human types it in in lowercase。 So let me go ahead and write a program called uppercase do C。

 let me go ahead and give myself the same header files include Cs 50 dot H include standard I O dot H。

 And for now， let's include string dot H for the length。

 And let's go ahead and have main void as before。 and inside of main。

 let's give myself a string S equaling get string before。Just so I know what the string is initially。

 Now I'm gonna to print out proactively after with two spaces just so that things line up aesthetically on the screen。

 because after is one character shorter。 And now I'm gonna to do the same technique as before。

 for int。I equals0， n equals the string length of S。😡，I is less than n I plus plus。

 And then inside of this loop。 what do I want to do logically。

 I want to force these characters to uppercase if they are， in fact， lowercase。

 And so how might I do this， Well， there's a bunch of ways to express this。

 but I'm gonna kind of do it maybe the most straightforward way， even if you've not seen this before。

 if the current letter in the string at location I because I'm in a loop starting from 0 all the way up to but not through the string length。

Is greater than equal to a lower case A in single quotes？😡。

And that letter is less than or equal to a lowercase Z。 What does this mean in English？ Well。

 this essentially means if lower case。Logically， if it's greater than or equal to little A and less than or equal to little Z。

 it's somewhere between A and Z in lowercase。 What do I want to do。

 Why I want to force it to uppercase。 So I want to print out a character。

Without a new long yet that prints out the current character， but force it to uppercase。 Well。

 how can I do this？ Well， this is where this sort of gets into like some low levell hacking。

 But notice the same ASi chart。 Here's our uppercase letters from last time。

 Here's our lowercase characters。 And let me highlight those。😊。

Does anyone notice a relationship between capital A and lowercase A that happens to be the same for capital A B and lowercase B。

有完。Yeah， like this pattern is true。 So 97，65 is 32。

 and that's true for every lowercase and uppercase letter respectively。

 So I can kind of leverage that。 And like this is not a C 50 thing。 Like this is ASi。

 This is in turn Uniicode。 Like this is how modern computers work。 So if I go back to V S code here。

 You know what I could do， let's just literally subtract 32。

 but because I'm displaying this as a cha， not as an int。

 I'm gonna see the lowercase letter seemingly become uppercase。 instead， else， if it's not lowercase。

 Maybe it's maybe it's already uppercase， maybe it is punctuation。

 let's just go ahead and print out with percent C， the original character unaltered。

 And then at the very end of this program， let's print a new line just to move the cursor to the next line。

😊，Alright， so let's do make uppercase。 and let me type dot slash uppercase。

 and I'll type in D V Id all lowercase And now you'll see it's in all caps。

 If though I type in maybe my last name， but capitalized M。 That's okay。

 The rest of it will still be capitalized for me。 Now I don't love this technique。

 It's a little bit fragile， because I kind of had to do some math。

 I had to check my reference sheet and then incorporate it into my program。

 even though it will be correct， I could be a little more clever。

 I could actually do something like this。 whatever the value of lowercase is lowercase a is minus whatever the value of capital A is。

 And I could actually do it arithmeically， even though that too is somewhat inefficient in that it's asking the same question again and again。

 but the compiler probably smart enough to optimize that。 And frankly， for those more comfortable。

 a good compiler will also notice no no no， you don't want to call Sterling again and again the compiler can do some of these optimizations for you。

 but it's still good practice to get into yourself。 But there's probably a better way。 instead。😊。

Of rolling this solution ourselves and subtracting 32 or doing any arithmetic。

 Let's use that C type library。 Let me go back up to my header files。

 Let's additionally include C type dot H。 let's pretend like I read the documentation in advance。

 which I did in fact， and let's instead of doing any math here。

 let's use a function that exists in that library called to upper and pass to it whatever the current character is in S at location I。

 Otherwise I still print out the unchanged character and let me go ahead and do make uppercase。😡。

Dot slash uppercase。 And now without any math， no subtracting 32， that too also works。

 But it gets better。 If you read the documentation for two upper。

 it turns out its documentation tells you， if C is already uppercase。

 it just passes it through for you。 So you don't even need to ask this conditional question。

 I can actually cut this to my clipboard get rid of all of this and just repae that one line only and just let two upper handle the situation for me because。

 again， it documentation has assured me that if it's already uppercase。

 it's just gonna return the original value。 So if I make uppercase this time。 dot slash uppercase。

 now it works。 And now things are getting kind of fun。 I mean， these are mundane tasks admittedly。

 but at least I'm standing on the shoulders of smart people who came before me who implemented the string library。

 the C type library。 I can even the Cs 50 library。 So I don't need to reinvent any of those wheels。



![](img/9bd24c440e3404fd993981bcfdb792d7_75.png)

Questions。😡，On any of these library techniques。It's all still arrays。

 It's all still strings and chas。 But now we're leveraging libraries to solve some of our problems。

For us。 Allright， so let's come full circle to where we began。

 where and I mentioned that some programs include support for command line arguments like Kang takes command line arguments。

 word words after the word clang C D， which you've used in Linux takes command line arguments。

 If you type C space P at one or C space Mario in order to change directories into another folder。

 If you do R M like I did earlier， you can remove a file by using a command line argument。

 A second word that tells the computer what to remove。 Well。

 it turns out that you2 can write code that takes words at the command prompt and uses them as input up until now。

 you and I have only gotten user input via get string， get in， get flow and functions like that。

 You too can write code that take command line arguments， which frankly。

 just save the the human time。 They can type their entire thought at the command line。

 hit enter and boom， the program can complete without prompting them and repromping them again。

 So here's where we can now start to。😊，Take off some more training wheels。 up until now。

 we've just put void inside of the parentheses here anytime we implement vein mainin。

 It turns out that you can put something else in parentheses when using C。 It's a mouthful。

 but you can replace void with this。Big expression， but it's two things。

 int called Arg C by convention， and a string， but not a string。

 actually an array of strings called Arg V。 And these terms are a little arcane。

 but Rrg C means argument count。 How many words did the human type at the prompt。

 Rrg V stands for argument vector， which is generally another term for an array。

 you've heard it perhaps for mathematics。 It's like a list of values， or in this case。

 a list of command line arguments。 So C is special。

 If you declare main as not taking void inside of parentheses。

 but rather an int and an array of strings。 C will figure out whatever the human typed at the prompt and hand it to you as an array and the length thereof。

 So if I want to leverage this， I can start to implement some programs of my own that actually incorporate command line arguments。

 For instance， let me go back in a moment here to V S code， let me create a program， for instance。

 called greet dot C。 that's just gonna greet the use。😊。



![](img/9bd24c440e3404fd993981bcfdb792d7_77.png)

Or in a few different ways。 So let me first do it the old way C 50 do H。

 Let me include standard Io do H。 Let me do int mainin void still。 So the old way。

 and if I want to greet myself or Carter or Yulia or anyone else。

 I could do old fashioned now get the answer from the user get string let's prompt for what's your name question mark just like we did in scratch and then do printf hello comma percent S backlash N answer。

 So we've done this many times now this weekend last this is the old school way now of getting command line of getting user input by prompting them for it。

 So if I do make greet dot slash greet， there's no command line arguments at the prompt。

 I'm literally just running the program's name If I hit enter though now get string kicks in asks me for my name and the program then greets me but I can do otherwise I could do something like this instead first answers a little generic。

 So let's first change this。Back to name and back to name。 But that's a minor improvement there。

 just stylistically。 let's though introduce now a command line argument so that I can just greet myself by running the program hitting enter and being done。

 No more get string。 So I'm gonna go ahead and change void to int Arg C string Rrg V with square brackets。

 String means the square brackets means it's an array。 Str means it's an array of strings。

 and Rrg C again is just an integer of the number of words typed。 Now。

 I'm gonna somewhat dangerously gonna do this。 I'm going get rid of my use of get string altogether。

😊，And I'm going to change this line to be not name， which no longer exists。

 But I'm going to go into this array called Arg V。 And I'm going go into location1。

So I'm doing this kind of on faith。 I haven't explained what I'm doing yet。

 but I'm gonna to do make greet now dot slash greet。

 And now I'm gonna type my name at the command line， just like with R M with Kang with C， D。

 with any of the commands you've written with multiple words。 I'm going greet literally David。

 So I hit enter。Andvoila， I've somehow gotten access to what I typed at the prompt by accessing this special parameter called Arg V。

 technicalnly， you could call it anything you want。

 But the convention is Arg V and Arg C from right to left here。 Just to guess then。

 What if I change this to print out bracket 0 and recompile the code。

 And I run dot slash greet David。 What might it say instinctively。😊，Any hunches。Yeah。

 so it's gonna say hello dot slash greet。 So it turns out you get what kind of one for free。

 Whatever the name of your program is is always accessible in Argv at location 0。

 That's just because it's a handy feature。 in case there's an error or you need to tell the user how to use the program。

 You know what the command is that they ran。 But at location1， maybe two。

 maybe3 are the additional words that the human might have typed in。 Well。

 let's do something a little smarter than this， let me go back to version 1。 let me recompile it。

 make greet。 Let me rerun dotlash greet， David， and this seems to work fine。

 What if I get a little curious and print out location 2。 Let me recompile the code。

 make greet do slash greet David enter。 Okay， there's null， And I mentioned we'd see N U L。

 in here's one incarnation thereof。 but this is clearly wrong。

 So I probably don't want even let the user do this because I don't want them to see bogus output like this is arguably a bug in the code that it even bother to show this by default。

So what could I do instead， well， what if I do this if Arg C equals equals2。

 then go ahead and comfortably say print F hello Argv bracket1 else if the human did not give exactly two arguments at the prompt。

 let's just print out some default value like hello world like from last week In other words。

 now I'm doing this error checking with a conditional。

 making sure with this Boolean expression only if Arg C equals equals 2 and therefore has two words in ArgV do you want to proceed And so now if I do make greed again。

 dots s Greek， David， this now works， but if I don't cooperate and I just run Greek。

 what should it say。😡，Just tello world， If I run David Main as two words， what should it say。

Hello world， because that's not exactly equal to 2。 Again。

 the first word in Arg V is always the program's name。

 The second word is whatever the human then has typed。 Now。

 if we don't even know in advance how many words they're gonna be， we can combine today's ideas。

 This is gonna look a little weird， but it's the same thing as before for int I gets 0。

 I is less than how about Rrg C， I plus plus， and then inside of this loop。

 I can print out percent S， maybe backslash N comma and then print out Rrg V bracket。

I so I can have a loop that iterates Arg C number of times once for every word at the prompt。

 I can print out Rrgv bracket I， which is the I word in that array from left to right。

 And so if I now make greet and I do dot slash greet alone， I just see the program's name。

 if I do dotlash David， I see those two one after the other。 if I do David Main。

 I get those three words。 if I keep going， I'll get more and more words。

 So using just the length of the array and the name of the array。

 I can actually do quite a bit there。 Now， there's actually some fun things you can do with this。

 And this is sort of beside the point。 But there's this thing in the world called ASi art。

 which is making pictures and beautiful things， just using ASi or maybe nowadays unicode characters。

 But without using emoji like emoji kind of make this a little too easy。

 But if all you have are traditional largely English letters and punctuation。

 you can actually do some interesting things。 on Linux systems。 For instance。

 if I go back to V S code here， let me increase。😊，Size of my terminal window here。

 And it turns out that we've preinstalled really for no compelling reason， but just for fun。

 a program called cow say， which has a cow say something。

 So if I want to have a cow say mu in ASI art， I can do this。

 and you get an adorable cow saying something like mu on the screen。

 But mu is a command line argument that is clearly modifying the output of this program because I could also change it to say hello comma world and now the cow is going say that instead。

 So it takes multiple command line arguments， if you will。

 But it also takes what are called flags or switches whereby any command line argument that starts with a dash is usually like a special configuration option that you would only know exist by reading the documentation or seeing a demonstration。

 And if I have my syntax right， if I do cow say dash F。

 and maybe Ill do let's see instead of this cow say how about I'll do dash F for file。

 and I'm going change it into duck mode。 and I'm going to have this version of the ASI art say。😊。

Quck， so it's a tiny little duck there。 but it's saying quack。

 and you can kind of waste a lot of time doing this。

 I can do cow say dash F dragon and say something like Ra。 and this is just amazing again。

 not really academically compelling， but it does demonstrate， again， command line arguments。

 which are everywhere and you've indeed been using them already。

 But there's one other feature we wanted to introduce you to today。

 which will be a useful building block， which will also reveal one other thing about the code that we've been writing。

 It turns out that all of the programs we've been writing thus far。

 eventually obviously exit because you see your prompt again unless you have an infinite loop such that it never ends。

 But eventually they exit。 And secretly， every program we've written thus far。

 actually has what's called an exit status。 It's like a special return value from the program itself that by default is always 0。

0 as a number in the world generally means everything's okay。

 The flip side of that is because the world tends to use integers and you've got like 4 billion。😊。

Like every other number in the world when it comes to a program's exit status is bad。 If it's one。

 it's probably bad。 If it's negative one， it's bad。 And in fact。

 you've probably seen this in the real world。 If you've ever had like a random error message on the screen。

 Here's a screenshot of Zoom for instance。 And that screenshot somewhat confusingly or sort of unknowingly has an error code like 1。

1，32， that probably means that the zoom software that some other humans wrote incorrectly。

 somehow had an error and it did not exit with status 0， it exited with status 1132。

 and somewhere at zoom， there's probably a file or a book that tells the programmers what this error code actually means。

 this is not useful for you and me， there's some programmer at Zoom who would probably be like， oh。

 I know what I date or my colleague did wrong in this case。 You've seen this elsewhere。

 even though this is not quite the same thing。 but we'll talk about this in a few weeks。

 If you've ever seen 404。 like numbers are everywhere。 And on the Web 404 means。Like file not found。

 It means you made a typo， the web server deleted a file or something like that。

 but this is just to say numbers are so often used to signify or represent errors。

 even though that's not an exit status per se。 That's an HtTP status code which will soon see。

 But you have access to exit statuses as it relates to command line software already up until now。

 this is how we've been writing main now with command line arguments。

 but we've also been writing main within int return value。 And you've never used this。

 we didn't talk about this last week， I just ask that you trust me and just keep copying and pasting this。

 but that int means that even your programs can return values which can be useful。

 even if you don't use command line arguments。 and we just go back to the original version like void。

 So for instance， if I go ahead and open up for instance， VS code again， I'll get rid of the dragon。

 And let's do one other program here called status。 just to kind of play around with the idea。😡。

Of these so called exit statuses， let me just demonstrate the idea with an include CS50。h。

 include standardIo。h into Maine。😡，And here I'll do int Arg C string Arg V。 And then inside of main。

 Let's do a similar program to before like the hello world。

 So print F hello comma percent S backslash n。 then let's print out R V 1。

 But I only want to execute that line。 if the human gave me a command line argument。 Otherwise。

 I don't want to even say some default like hello world。

 I just want to abort early and just exit the program。 No output whatsoever。

 So I could do this if Arg C does not equal to， and it's a single equals。

 but it's a bang and exclamation point means not equals。 So this is the opposite of equals equals。

 Then previously， I would have just print hello world。

 but now I want to print out an error message like missing command line argument just to explain to the user why the program is about to terminate。

 and then I can return1。 It's kind of arbitrary。 I could also return 1，1，3，2， but why start there。

 This is the only。Possible error that could go wrong in my program。 So I'm gonna start it one。

 Zoom clearly has100 plus possible things that can go wrong in their source code。

 which is why the number got as big as 1132。 but I'm just going to arbitrarily but conventionally return one。

 But if everything is okay and I do it is not the case that Arg C does not equal to。

 and I actually get to line 11， I'm gonna return  zero because 0 again， I claim signifies success。

 And all of this time every program we've written you've written has secretly exited with 0 by default。

 But now that our program are getting more sophisticated when something goes wrong。

 it turns out it's useful to have the power to just return some other value。

 even though the users not gonna see it。 even though the zoom user shouldn't see it。

 it's still there， it's diagnostically useful to you or in the case of a class to your TF or T or C。

 So if I do make status now to compile this program and run dot slash status and type my first name。

I think this is a success。 It should say hello， David and secretly exit with0。

 If you really want to see the zero。 there's this arcane command you can type。

 you can literally type it your prompt E dollar sign question mark。 It's weird symbology。

 but it's what the humans chose decades ago， this will just show you what did the most recently run program。

 secretly exit with。 So if I do this in VS code， I can do exit dollar sign question mark。

 enter and there's that secret0。 I could have been doing this this weekend last week。

 it's just not that interesting。 but it is interesting or at least marginally so if I rerun status。

 and maybe I don't provide a command line argument or I provide too many。

 So ay does not equal to and I hit enter， I get yelled at with the error message。

 but I can see the secret status code， which is indeed one。

 And so now if you're ever in the habit in either a class like this or in the real world where you're automatically testing your code。

 be it with check 50 or in the real world things called unit tests and other thirdpart software。



![](img/9bd24c440e3404fd993981bcfdb792d7_79.png)

Those tests can actually detect these status code exit statuses and know did your code succeed or fail 0 or one。

 And if there's different types of failures， they can detect status 2 Sta 3。

 status 1132 It's just one other tool in your toolkit but all of that is terribly low level and really the goal of this week and really today and really code more generally to solve problems so let's consider an increasingly important one。

 which is the ability to send information securely。

 whether it is in file format wirelessly or any other cryptography is the art and the science of encrypting scrambling information so that even if I write a secret message to you。

 and I send it through this open audience with so many nosy eyes who could look at the message if I've encrypted this message none of them should be able to read it only you whoever you are to whom I intended that message in the world of encryptptography。

 then encryption means scrambling the information so that the only you in the recipient can receive it So if we。

Our black box， like in week 0 and one。 Here is the problem to be solved。

 And let me propose a couple of pieces of vocabulary。

 Plain text is any message written in English or any human language that you want to send and write yourself。

 cipher text is what you want to convert it to before you just hand it off to a bunch of random strangers in the audience or a bunch of servers on the Internet。

 Any one of whom could look at your message。 So in the black box is what we're gonna call a cipher an algorithm for encrypting or scrambling information in a reversible way。

 It doesn't suff you just scramble the information randomly。

 Otherwise the recipient can't do anything with it， it's an algorithm。

 a cipher that encrypts it in such a way that someone else can decrypt it。 And here's a common way。

 Most ciphers take as input， not only the plain text message in English or whatever else。

 but also a key。 And it's metaphorically like a key to open a lock。

 but it's technically generally a number， like a really big number made up of lots of bits and not even 32。

 not even。64， sometimes 1000，24 bit， which is crazy， unpronounceably large。

 But the probability that someone is gonna guess your key is just so。

 so small that for all intents and purposes， you are in fact， secure。 So what's an example of this。

 for instance， suppose the secret message I want to send is innocuously just high exclamation point。

 Well would be pretty stupid to write high on a piece of paper hand it to someone in the audience and expected to get all the way to the back without someone kind of like glancing at it and obviously seeing and reading the plain text。

 So what if I though， agree with someone in back， for instance， that our secret is gonna be one。

 And we have to agree upon that secret in advance。 But one just means that that is my key。

 And let me propose that according to one popular cipher。 if I want to send high exclamation point。

 change the H to an I and the I to a J。 that is increment effectively。

 every letter of the alphabet by one。 And if you get to a Z wrap back around to a， for instance。

 So shift the alphabet by one place in this case and send this message now instead。



![](img/9bd24c440e3404fd993981bcfdb792d7_81.png)

So is that secure。 Well， if one of you kind of nosily looks at this sheet of paper。

 you won't see high。 you will see some information leak in this algorithm。

 You'll see an exclamation point。 So I'm enthusiastically saying something but you won't know what the message is。

 unless you decrypt it Now that said， is this very secure， really in practice， I mean， not really。

 like if you know， I'm just using a key。 And I'm using the English alphabet。

 you could probably brute force your way to a solution by just trying one， trying to trying3。

 trying 25， go through all the possibilities tediously， but eventually it's probably gonna pop out。

 This is actually known， though as the Caesar cipher。

 And back in the day before anyone else knew about or invented encryption Caesar。

 Julius Caesar was known to use a cipher like this using a key of3， literally。

 And I guess it works okay。 if you're literally the first cumin in the world by by lore to a thought of this idea。

 But of course， anyone who intercepts it could attack it nonetheless and figure things out a bit mathematically。

13 is kind of more common。😊，I's called Rot 13 on the Internet for rotate the letters of the alphaphabet 13。

 that changes high to UV exclamation point。 You might think what's better than 13。 Well。

 let's double the security， Ro 26。 Why is this stupid？😡，I mean。

 there's like 26 letters in the alphabet。 So like A becomes a。

 So that doesn't really Oh wait you I'm pointing at something that's not on the screen damn。

 supposeose the message is more lovingly。 I love you instead of just high same exact approach。

 whether or not there's punctuation。 I love you with an input of 13 might now become this。

 And now it's getting a little less obvious。 what the cipher text actually represents。

 And now what's twice as secure is 13。 while 26 is surely better。 But， of course。

 if you rotate 26 place that， of course， just gives you the same thing。 So there's a limit to this。

 But again， that just speaks to the cipher being used， which is very simple。 there's much。

 much better， more sophisticated mathematical ciphers that are used。

 We're just starting with something simple here。 As for decryption。 If I'm using a key of one。

 how do I reverse the process。😊，Yeah， so I just -1。 So B becomes A。 C becomes B， A becomes Z。

 And if it's 13。 I subtract 13 instead or whatever the key is。

 So long as sender and receiver actually know it。 So in this case here。

 this is actually the message with which we began class。 if we have this message here。

 and I use the key of one to encrypt it。 Well， decrypting it might involve doing something like this。

 Here's those same letters on the screen。 And I think in a moment before we adjourn。

 I'll mention too that we might have encrypted a message in8 characters this whole day。

 So if any of you took the time， and procrastinated and figured out with the light bulb spell。

 and they didn't seem to spell anything in English。 Well， here now is the solution for cracking it。

 This， if I subtract one becomes what you becomes。😊，T， and this is obviously。

 see where we're going with this。 And if we keep going subtracting one。 So indeed。

 we're at the end of class now， because this was C S 50。

 And the last thing we have to say is we have hundreds of ducks waiting for you outside。

 So on the way out， grab your own rubber duck。😊。