# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p01 -P01-Lec 01 - What is a Compiler_.zh_en -BV1zQ27BeEfF_p1-

![](img/dbf1b61a40715d4708928ed8c38e560e_0.png)

![](img/dbf1b61a40715d4708928ed8c38e560e_1.png)

All right， let's go ahead and get started。So first of all。Hello everybody， huge welcome， I'm Sarah。

 I'm super excited to meet all of you and I cannot overstate how excited I am to get to do this particular class with yall。

I know that I am extremely biased because this is my research area。

 but I just think that this particular class touches on some of the concepts that sit at the core of computer science and help us understand what we're doing when we're programming I suspect most of the people in this room have at some point had that experience of just understanding something and having that feeling of oh。

 I think I'm just smarter now and one of the things that I really love about compilers is that I get to have that feeling all the time is just constantly putting me in touch with that oh。

 I'm wrestling with something that I thought was familiar this programming experience feels so natural and I'm used to it but now I'm doing something different。

 thinking about the program differently and it has make it suddenly unfamiliar to me and then I get it and it clicks and I get to feel smart again。

So I hope that some of y'all will get to enjoy some of that experience with this class。

 I think it's really built to try to give you all the opportunity to have that experience as much as possible with ideally as little of the sort of messing with random nonsense and sort of incidental complexity we're really trying to maximize that。

 I wrestled with something hard and I got it and minimize that。

 oh I have to deal with this sort of random other stuff over here that's not really connected to the core of the class。

And so that's what we' are going to be thinking about here today。

There is a lot that we're going try to cover over the course of the semester。

 so I'm honestly going start pretty much with just diving right in on content。

 I have left a little bit of time at the middle of the class session right around when we'll take the break where we'll just talk a little bit about logistics。

 but other than logistics chat。 The main thing that we're gonna to be doing today is we'll start with talking about what even is a compiler。

 and then diving in on live programming we're gonna spend a bunch of our time in these class sessions on live programming and then following the break we'll dive in on some handson activities。

 which is the other main thing that we'll be doing in class sessions。Honestly。

 a lot of it is gonna to be live programming and handson activities。

 That's what we're mostly going be doing。😊，All right， I'm going to go ahead and start us in。So。

 taking a look at。Our very first and kind of unsurprising side。

 I suspect that since y'all have chosen to appear in this class。

 you might have some idea of the answer to this question。that's not true， totally understood。

 maybe it's just a convenient time， that's fine if however you have some idea of what a compiler is。

 turn to the person next to you， chat about it for a moment and then we'll shout out our answers about what is a compiler。

All right， what do we think？What is a compiler， go ahead and shout it out for me。Don't be shy。可以没以。

Almost like a translator I love it， I'm hearing translator， absolutely。What else have we got？Oh。

 sorry。It。Text into machine code， okay， you got it， what are we got？Source code to assembly。

 I like it， what else we got。Performs optimizations， love that。Okay。

 so if I were going to sort of generalize a little bit above all of these answers。

 I think the thing that I'm hearing is we definitely expect that there's going to be some kind of transformation step in there。

 whether that's translation， whether that's optimization。

 there's going to be an arrow doing to something so it's converting something into something else。

 so let's go ahead and write this out in more or less the language we'll be using over the course of the semesterve。

So we're going to go ahead and say that a compiler has type we use colon to mean hasS type and we're going to do that for a couple reasons both because that's how you do it in math。

 but also because that's how you're going to do it in O Caml。

 which is one of the languages that we will be using over the course of this semester。

And what is the type， Well， it's going to be translating a source program。Into。Target program。

I think it's really interesting that we heard a lot of in those answers。

 we were hearing a lot of maybe this target program， oops， didn't mean to erase there。

Heard a lot of maybe this target program is going to be something low level， right。

 Maybe it's going to be assembly。 maybe it's going to be machine codes。

 Maybe it's going to be something low level。 And often that is the case， right。

 because we often are trying to convert our source program into something that we already know how to actually use in order to get a value。

However， sometimes we're actually just doing from a subset of a language to a subset of the same language。

 that's also totally fine。 that is also a compiler is often sometimes called a transpir。

 that is also a compiler and we're also going to count it in this definition。😊。

Any questions about what we mean when we say compiler so far。

 are we feeling good about the idea that we've got a source program we're following that error。

 we're doing some translation， getting a target program。Amazing， okay。

 so now I want you to turn to the person next to you and say。

 what is going to be the type of an interpreter？We often think about interpreters and compilers at the same time。

 what is going to be the type of an interpreter。Discuss with folks nearby。はない。It行。交给。All right。

 it sounds like we have some ideas because we're quieting down。 So what do we think。

 what's going to be the type of an interpreter。It is a little weird， isn't it？I love it， okay。

 so we're hearing we've got our interpreter。And it's going to have the type。Text to。

And then I think you said something that can be compiled， I like this general instinct。

 what else have we got？Yeah。A computation graph， okay？I'm hearing output of the program。Yeah。

 so this is very interesting， right， What if I ran my Python interpreter on my program that I wrote and it said something like。

 I don't know。 it did some big computation， and I wanted to get out the output and it gave me something else back。

 right， It just gave me another program。 that would not actually be what I was trying to get by running my program。

 And so what we're actually going to be saying is that what we're having in the interpreter is it's going to take a source program in。

😊，Source program， right， same type as our compiler。 But what we're going to get back is a value。

 You might also hear people say string to string。 that's not super compelling to that's right。

 We want to actually say this could be a number， this could be whatever。

 right So that output that we're expecting。And this kind of makes sense in some ways because we know that we do have ways of actually running programs and actually getting a value out of them。

But if we're requiring an interpreter in order to get this。

 then what are we doing with these compilers， right， how are we getting out some other program？😡。

And actually getting a value from it at the end， we're like。

 why is it interesting to us to have assembly code coming out the other side of that compiler？

So go ahead and take just 20 seconds to talk to the people nearby。

 what is it that is going to turn that assembly code into the output that we actually want？Alright。

 so I'm starting to hear this in your conversations。

 which is I'm hearing that well maybe we we'll feed in the output from one compiler into another compiler and we'll get something even lower level and we'll feed into another compiler we'll get something even lower level and we'll keep going。

 we can string all of these different compilers together。

 keep on going and get something really low level。 But then eventually eventually at the end of that whole process。

 we had better be able to feed it into an interpreter in order to actually get that output out we're gonna to need to actually run this thing and find that value And so a very important interpreter for our purposes is going to be the processor in your machine right So my laptop that we're gonna be running a bunch of code on X 86 machine。

 we are gonna go ahead and be treating the machine as basically an interpreter for the assembly that we are gonna be writing over the course of the semester。

 And that's how however many compilers， we end up streaming together mashing together we are eventually going be able to go from whatever that source program was right at the very start to what is the value associated with actually running that program。

😊，So do we have questions right off the bat about compiler versus interpreter。

 This is something we're going to be revisiting。 This is not going to go away。Yeah。Yeah。

 so how is the Python interpreter actually working So inside something had better be figuring out how to make something that your machine can actually run。

 right So your processor is eventually going to have to execute some instructions order to get that value So inside the interpreter and we're actually we're going to see some examples of this。

 In fact， over the course of the semester， you are going to be designing in parallel a compiler and interpreter for a series of languages and you're always going to have them matched。

😊，Basically， you are taking advantage of something else has already figured out how to create machine code and run it。

 right， So you are actually writing a program that is going to go ahead and interpret your program as data。

 right， That's the input。 That's the thing on the left side of the arrow。

 And that's going go in the arrow and out the other end。

 We're gonna have something that is eventually going to send off machine code and produce a value。

So yeah， there can be interpreters other than the processor。

 the processor is just one of our interpreters。Other compiler versus， oh， yes。fi。Yeah。

 so if you take a look at basically these types right so let me go ahead and swap to highlight letter mode here。

 so we've got source program， we've got target program， we've got source program。

 we've got value so in general。As long as the let's see a new pointer。

 the the target program that's produced by this compiler can be treated as input to another compiler。

 we can keep on stringing them together， right， So if we have something that translates our rust to see。

 and we have something that translates C to assembly and we have something that translates assembly to the thing that's actually going run on the processor。

 we're good to go。 right， That's all good。 As soon as we do our interpretation。

 that's not a programming anymore， right， we've got our value。

 that's no longer the thing that we actually want to be piling in to a compiler anymore。

So that's where the string is going to end。It's not really like a。

Interpreter can be freestanding absolutely right， so like inside the interpreter。

 there's going to be something that's figuring out how to actually get that value out。

Which means realistically， because the sort of end process。

 the end thing that we're going to be relying on is going to be the computer's processor。

 And that's not going be taking in， say， Python， right。

 Something in there is going to be doing that translation。But yes。

 it is totally fine to go straight to interpretation。Okay， this is a topic we'll revisit。

 So it's not as if we have to be done with questions on this topic。 but I think let's。

 let's talk briefly about。Why we study compilers and then we'll actually transition into writing our first one。

 so over the course of today we're actually going to write our very first one。

So there are a couple of reasons why you might be heard。 These ones might not align with y'alls。

 but these are some of the reasons why I get really excited about thinking about compilers。

 So the first thing is iss fun。 we kind of touch that one already。

 and it might be more fun for others than than it's going to depend whether you find it fun for me。

 I think it's pretty fun。 I think it's pretty common to find sort of these brain teas or puzzle type things inside the topic。

 Another big thing is that this is this very nice sort of marriage of things that are theoretical with things that are more practical handson systems building。

 You sort of get to have both together at once。 you get this practice with actually building a big system。

 something that's actually very complex and is doing something really complicated with treating programs as data。

😊，Another good reason is you might actually develop a better relationship with whatever compiler has been torturing you。

 latelyly。 So if you're getting really annoying error messages from the compilers that you're using in your day to day life。

 often that's because for a very long time， we basically develop compilers in such a way that they were expressing problems with your program in terms that are understandable to the compiler writer much more than to the end programr right It is sort of speaking the language of the compiler instead of speaking the language of your program And so one of the things that you might be able to get out of this class is understanding more of what's happening inside the programming languages that you're actually using in the day to day and using that to actually understand better the programs that you are writing in the day to day。

😊，The other thing that we're going to touch on a lot over the course of the semester is it turns out a lot of the skills that you develop over the course of implementing programming languages。

 implementing the pilots， implementing interpreters are also really useful for learning a new language and so ideally at the end of this course you're going to feel a lot more comfortable teaching yourself the next language that you need to learn。

So those are some of the things that might be drawing you in。

 We're actually also going to spend some time on next Tuesday reflecting on what makes this class connected to you and your values。

 but these are a couple of things to have as food for thought。Okay。

I'm going to go ahead and dive us into developing our first compiler of the semester。

 It is going to be for a very simple language， But that's okay。 Let's go ahead and swap views。😊。

Great， okay， so I'm going to go ahead and open up probably a familiar interpreter。 So let's go into。

The Python interpreter。Someone yell out a simple program。All right， let's do。I love it。

 we have printed Hello worlds。InSome ways， it's true that that is a simple program。In other ways。

 that's a very complicated program。We are going ahead and doing this print thing。

 That's actually kind of complex。 We have this representation of strings。 y'all are， in fact。

 going to implement strings over the course of the semester， but that's actually pretty complex。

 I think we might be able to get an even simpler program。What else might we have in mind？Love it。

2 times 10。I love that。 That's a very nice simple program。 I'm gonna argue we can go even simpler。

 You know what I think is a nice substitute for two times 10。

 I think 20 is a really nice substitute for two times 10 that's a real simple program So since we're just talking about what we can implement over the course of one class session today we are gonna implement a compiler for numbers we're going take in a program that just has a number and then it's going to go ahead and produce all of the assembly that we need in order to actually treat that as a program and eventually produce it as output So that's what we' are gonna be working on today。

 It's a little bit simple， but you know we're talking about one class session it's gonna be a little bit simple。

😊，So let's go ahead and dive in。 this is basically going to be our lesson on printing a number。

 the extremely long， extremely slow way。 but that's all right。

 We will be building up the infrastructure that we're actually going to use for the course compiler that we build out over the entirety of this semester。

 So this same sort of overly structure that you're going to see today is actually going to be part of the course compiler that will be linked on the website and that we will be developing over the course of the entire semester。

So let's now look at kind of a weird program， so I'm going to have us take a look， is this visible。

 is that a little small， maybe that's a little bit better。So here we've got。

A weird little C program I'll give you a second to look it over。

Nothing particularly interesting here。 We've got this little entry thing that seems to be in charge of getting us this 4。

000，0 something value。 and then we're going to go ahead and get out whatever entry gives us。

 and then we're going to print it。So this really is not a particularly interesting program。

 but let's just see what happens when we run it。So now we've compiled it。Okay。

 it's done the thing we expected it to do。 That's all right。 That seems okay so far。 Now。

 what actually had to happen for us to get that output。 Well， you can see this thing appeared。

 This program thing。 So my editor is saying， oh， no， you don't want to read that。

 That's not going to be fun for you to look at。 Let's insist。Yes， let's use that。It was right。

 I did not want to read that。 right， It turns out that is not a super fun thing for me to interpret or to try to understand what is going on in there。

 right。Basically， to me， this looks like unreadable garbage。 It not very helpful。

 It turns out that this is machine code in binary format。Very useful for handing off to my processor。

 not very useful for me to read。 So let's give us something that's going to be a little bit more intelligible for us。

 So let's do GCC。 don't worry， you don't have to remember all these flags。

 I haven't even memorized these flags。 I've written them down。Okay， so now what did we get back well？

We got this。So this is S。 This is the file ending。 we're going to be associating with assembly in this class。

 and you can see that this is looking a little more readable。

 We can see there are some sort of relationships between what we wrote in the program in the C version。

 Let's show the C version。 There are some relationships。

 We can see this entry thing appeared here in the C version。

 we can see this main thing appeared here in the C version， and we're also actually no。

 not in that one。 let's stop looking at that one we can see that in the assembly we' are also seeing that。

 So we see this entry thing seems to be starting here。

 we can see that this main thing seems to be starting here。

 So it looks like we're seeing some shared structure。😊，So okay， this is a fine program。

 it doesn't really honestly look like a compiler yet。

 but it does start to look a little bit like a runtime。

So if you look at any of the languages you use in your day to day。

 there's probably a lot of the compiler for those languages that is directly translating into some output target。

On the other hand， there's probably a lot that is actually implemented in a runtime。

 So the runtime is basically the snippet of program that is going to get included in every single program that is actually made with your language right。

 So the C runtime appears in every single C program， right。

 It's just something that's there is available to you。

 It lets you do the various things that you might need to do And so we're actually going to go ahead and turn this program into。

A runtime for our new。Programming language that we are going to implement。 So， okay。

 what are we going to need to do in order to treat this as a runtime？ Well。

 just hard coding that the value we should get back from every single program is going to be40。

 That's pretty unsatisfing。 right， Probably we're gonna want to do something else。

 So let's go ahead and get rid of that。And now， even though we have this thing in our runtime that's going to take charge of printing for us。

 right， going ahead and implementing printing just directly in assembly would be kind of painful。

 So we're going to go ahead and let our runtime take care of that for us。

But we are going to want to go ahead and get our value from somewhere else。

 So let's go ahead and mark this as X。Basically saying， I'm not providing this entry thing。

Here in this program。I am going to promise that I will provide it to you somehow。

 but it's not going to appear here。😡，So let's go ahead。And compile our runtime now。Okay。

 so now we have compiled this runtime， it's going to be available to us。

 And once we have some assembly that is directly generated for our language。

 our tiny little language that just has numbers。 once we are going go ahead and actually generate from assembly some assembly from that。

 we're going to be able to sort of paste it together with the assembly that is generated by C for this runtime。

So okay， back to our entry function。Right now， our entry function doesn't look super friendly。

 So I'm gonna make a simpler version of this that's going be more fun for us to play with。

 So let's go ahead and say。😊，I'm going to provide entry， don't worry。

 I'm totally going to provide it。This is it， here's the entry thing I'm going to give it to you。

And then let's choose some value。 And so this is starting to get interesting。

 What's happening here is if you remember your architecture classes。

 your computer organization classes， RAX is one of our named registers and specifically the reason that it's interesting to us right now is that it's a register where C and this is relevant because we have a C runtime where C is expecting to find the return value right So if we go ahead and put 5000 inside RAX C is going know to find that when we're actually going and referencing the output from entry right here。

So let's go ahead and do our return。I want to ask if there are questions about this so far。

 I know it's a little bit weird hooking together this assembly that we've written。With。The runtime。

Yes。😊，Yeah， absolutely。 so inside runtime do C， we have to know about entry because we are gonna call it down here right down here。

 we're actually going ahead and saying yep， please call entry and please go ahead and actually print out whatever you get back from entry However。

 nothing in this runtime C program has actually defined entry right and so we have to say I know we didn't define it。

 but we promise we're gonna give it to you somehow So don't worry about it。

 don't freak out because we haven't given you a definition assume that something else externally right so external is going to actually give it to you。

Okay。So now we're starting to get to something that we can tie together right。

 we've gone ahead and already compiled our runtime。

 but let's go ahead and actually pull together our our program as a whole。 So program do S right。

 So remember we were writing directly inside program do S。

 So we're going to go ahead and turn this into our fully assembled program。Again。

 don't worry about these flags too much。Okay。Okay。Looks good。 Looks like we're able to do that。

 We've got the thing that we want。 And now we're going do something that's a tiny bit unsatisfying。

 which is we're going use GCC to link together the program with the runtime。

 And it's very annoying right， because Gcc is a compiler。 And here we are。

 We're supposed to be building towards our compiler。

 But I'll show you in a moment that it really is just doing the linking。

 which is basically we can think of it as just mashing together the program that we have written by hand and assembly with the runtime。

 So let's go ahead and do the。😊，Runhe。0。Program。Okay， and I'll show you that it really is。

Just running the linker。 So if you see right there， this is the bit， this L bit。 this is saying， yep。

 we're just running the linker。 And so now we've run it。

 So let's go ahead and actually run this program。Great， so now we have 5，000。

 the value that we had right here that we put into RAX， we have that coming up。So okay。

 we've gotten ourselves part of the way towards that first compiler that we want。

 We are indeed mashing together assembly that we have generated through some means other than the C compiler with the runtime。

 we're going to actually know run those。 We've been able to sort of tie them together and run them。

 But if we look at this assembly。 This is clearly not a compiler， right。

 This is a particular piece of assembly that I just typed in here directly。

 And so it's always going give back 5000。 But we're expecting to be able to take any number while any integer as our input and go ahead and turn that into our program。

 treat it as our program。 So let's go ahead and keep pushing on this。

 So we want to be able to turn a program that looks like。

That right just looks like a number into assembly that looks like this。

 What is that going to require？ So now we get to do something very exciting。

 We get to actually write our first Ocal program of the semester Ocal is basically if you talk to programming languages people they'll often say this is basically a domain specific language for writing compilers。

 And so this is one of the ways that we're going be able to write so many compilers in so many interpreters so quickly over the course of this semester。

 So let's go ahead and open our nice blank compiled do Ml。

 We are going to be spending a lot of time over the course of the semester in this file。

 but we're going to start with something that really is actually very simple。

 So let's go ahead and make our compile function。 So。Compile。Program has type string。

 here's our has type notation that we've talked about before。

 I mentioned that sometimes people treat compilation as string to string。

 that's what we are going to be doing right here。Okay， great。 so far， so good。 Now。

 what do we want to actually produce in here， I think， you know。

 we know that we're gonna want something that looks a little bit like this to come out the other end。

 So let's actually start really simple。 Let's just paste that in。😊，Right okay。

 this is kind of weird right This isn't exactly what we want。

 so we know that we're going want to go ahead and produce a string in the end。

 so let's go ahead and work towards making this into a string。

 we can start by treating it as an array of strings。

 It turns out that we are actually going to need to keep that spacing in there。

 those tabs Those are going to matter。 so let's go ahead and keep those。

We forgot a semicolon up there。 So okay， we're getting real close。 We are in fact。

 at the point now where we have something that is just an array of strings， but O Camel isn't happy。

 So take 20 seconds to chat with someone nearby。 Why isn't Ocael happy。

 We are about to all be wrestling with a lot of Ocael complaints。

 So start making some guesses 20 seconds。All right， what have we got， why is it mad at us？

Please feel free to shout out。What did we promise it we were going to give？Yeah。

 we promised a string and it's true that we've got some strings in here。

 but we promised one string right we said that our return type。

 that's what we were actually saying up here。 we promised that our return type was going to be string and it turns out we tried to give it an array of strings。

 it's not going to like that so let's just turn this into one。

And we can mash them together with new lines。 Okay， and now it is happy with us。

 So we're starting to get kind of close here。 So let's go ahead and start exploring what it looks like to run this。

 So first， let's do Utah。 So this is how we're going to interact with Ocal。

 We're going just be running our Ocal programs in here。 So let's go ahead and say use compile。😊。

Dot M L。Did it actually keep track of what's in there。 And let's make sure it's actually got it。

 Okay， great。 for a moment， I was worried there because it didn't say， oh。

 we know about this compile thing， but that's because I hadn't saved the file。

 Now I ran it again once we actually had saved the file and now it knows about this compile thing。

 So okay， let's go ahead and actually try running something let's see what shall we actually try it with we can try it with well any value。

 So compile。😊，7， well，8， my typing is not great。 Okay， this is looking good in some ways， right。

 so on the one hand， we're clearly getting back something that looks like assembly。

 On the other hand， we sure do seem to have 5000 when I gave 8 as our input。

 That's a little unsatisfying。 Let's go fix it。 right So we haven't actually use this program thing。

 That's the thing that's missing。 I just hard coded 5000。 So let's go ahead。

 Let's go in and change that。 So we are， in fact， doing the thing that we should be doing， which is。

 let's just use our stream formatting。F dot print F。And let's turn this into。

We're going to sub a string and the string we want is program。Okay， so now。Great。

 now we see 8 is showing up there instead of 5000。 So we're starting to see that we are actually compiling。

 We're actually doing the thing that we intend to be doing。

 We are producing assembly associated with the input program， the teeny。

 tiny simple input program for the input program that we're actually producing。 So let's go ahead。

 Let's start putting it all together。 We will go ahead and make ourselves a little helper。😊。

We'll call this let compile。To file。And all we're going to do is actually pop this into program do S so we can start treating exactly the same as the program do S that we have used before。

 right we want to go ahead and put it in here so we can go ahead and do what we've been doing to run it。

 right， We don't want to just print out this string。 that's not that interesting。

 So let's go ahead and take in program。String。😔，This is just our way of saying， nope。

 we're not giving you anything back from this， no return value。

We're going to say we're going to open a file that we are going to output into program。 S。

And we're going to go ahead and do output， string。Compile program right so here we are calling this compile function that we have right up there right。

 we're calling it on program， which is our input。 And then whatever we get back from that。

 we're going to go ahead and put that into this file that we have opened right here。

 so we're going to put it into program dot S。 and then we can just close out this file。 So close。

Out file。All right， what did I do wrong？So I misspell output string。

 is it actually happy and it's not playing nice？Oh yeah， okay， great。

Let's go ahead and that's something we're going to be talking about real soon。 Great， okay。Great。

 so now we know about this compile to file。 so let's go ahead and do compile to file on 20 and just make sure that it actually oops。

Let's make sure that it actually shows up。In program do S the way we expect。

 So let's look at program do S。 fantasticastic。 We're seeing 20 in there。

 Look like we're really starting to get to the point of having compile compiler。

 And then I will paste in a little extra helper function。

 which is basically just going to do all of those same commands that we were running at the command line before right So if we take a look at what's happening。

 it says let's go ahead and take program do S and turn it into the kind of code that we can actually run on the machine because even though assembly is pretty low level。

 It's not all the way down。 And then let's go ahead and connect it together， right。

 This is the part that's just running the linker， let's connect it together with our runtime。

 and then we can actually run the program。 we can go ahead and pop out the output。

 So this is basically just a convenience function。 This is saying tie everything together and run it for me。

 So now let's make sure that this is all gonna play nice。😊，And。Let's do compile and run。

And let's what's the number we want to paste in。1，64， great choice。 lovely number。 Love that。A。

 all right， we have a compiler， right， we can paste in whatever numbers we want to get back。

 And even though this is just numbers and numbers and pretty simple， right。

 we can take a look at program do S and see that that's actually showing up in there。

 We have made our very first compiler of the semester。😊。

So are there any questions about that before we take our break， thanks， y'all。

 are there any questions about that before we take our break？😊，Yeah。Yes， I love this question。 Yes。

 so let's just talk through where our values are coming from and what's happening。

 So what's happening is we when we run one of these lines right。

 this is the input program that I am providing as input to this compile and run function and we wrote this compile and run function right here in compile M。

 So this is our compiler right this is the whole thing that's doing compilation for us。

 It's whole charge is to come up with assembly right something that looks kind of like these things tied together。

 assembly that is going put the appropriate value inside RAX。So when we go ahead and put 165 in here。

 we go ahead and pass it along from here， we call compile to file that gets passed to here。

 we go ahead and we actually open up the program do S。

 we figure out what we even want to put in program do S that's determined by what's happening inside the compile function we figure out。

 okay we want this line of assembly， this line of assembly， this line of assembly。

 this line of assembly， and then that does all in fact appear right here in program S。

Does that answer the question？走。Are there questions about our first yes？I love this question。 Yes。

 so if we were looking at just compile to file， fantastic compile to file is clearly going to be a compiler right because we can see that the input is 165 and the output is just this string clearly not our output value and so clearly know this is another program。

 this seems to be a compiler。 On the other hand， our little helper function compile and run。

 absolutely that's an interpreter right It's taking us all the way from this input program to the value associated with actually running that program。

 So absolutely this function is going to be an interpreter。 This function is a compiler。

 Eventually we are also going to have a separate Ocal file that's called interpret Ml or something and will be separately building up an interpreter that doesn't bother to directly produce assembly and it's going to rely on Ocal the Ocamel compiler to actually produce assembly for it。

 So there's multiple different ways to implement an interpreter， which is something。😊。

We'll be playing around with。Yeah。After compile the file inside compiler great question。

 Okay so this is where we're saying， okay， we've got this。

 you remember how the byte code that we looked at was like really ugly and we didn't want to look at it。

 So we've got to get that out somehow。 And so even though what we're producing is this sort of assembly that looks pretty low level to us。

 It's not all the way。 And so this line is taking care of turning that all the way down into the ugly stuff that we don't want to look at this line is saying go ahead and stitch that together with our runtime right So if you remember we have our little runtime。

 that has to also get turned into machine code something that the machine can actually run and then something has to stitch those together。

 And so that's the linker。😊，And then once we have stitched those together。

 we actually just run the program right so we're just saying yeah， okay。

 we've got it now go ahead and run it， and that's how we can actually see the value once we make this line right so we can go ahead and actually see that that's just the output from running that program。

😊，Great question。Okay， if you come up with more questions， ask them after the break。

 we'll take a little five minute break we try to always take a five minute break because this session is kind of long and we want you to stretch your legs。

 grab water or whatever so we will come back together in five minutes。对。よしいます。てで。在这前。All right。

Let's go ahead and come back together， so before we keep going。

 were there any other questions that came to mind over the little break？I know we moved pretty quick。

Okay cool in that case， I'm going to talk for a moment about how weird this compiler is。

 So first it's pretty weird that we just have numbers going in right like that's a pretty boring programming language but here's another thing that's a little bit wacky。

 So here you can see I've actually run it on this string test。And yeah， you know。

 we're getting an error。 So it's kind of doing what we would maybe want， right。

 we've said aloud that what we want is to just get numbers going in。 But， you know。

 this isn't really what we would like to have happening。

 And then I think we can even make it weirder， right， So here， this is definitely not a number right。

 This is clearly a string。But if we run that。Oh。RightSo that is going to go ahead and just produce8 as our output。

 If I had asked you to sort of write down what should be the semantics of our language。

 what should our language do， you probably wouldn't have said that that string should produce the evaluate is my guess based on what we've talked about so far the idea that all that should be coming in as numbers and all that should be coming out as numbers。

 I would say that's probably bad behavior。 we're sort of getting this silent weird behavior on this string because I know what thebier is doing and I know that all that's happening is that's getting pasted into the assembly。

 So eventually we're going to want be doing things that are a lot fancier than just treating these as strings and that is going be coming down the pipeline real' soon。

So for now， I want to briefly preview what's coming up for this language as we make it more complicated and more interesting。

 So obviously right now， all we've got numbers very simple long term we're going to get to a lot of the features you are familiar with you are going to be able to write real programs in this programming language that we're building together and I want to draw our attention particularly to the last item on here so because we are using Ocall。

 which is basically going to let us write a lot of interpreters。

 a lot of compilers real real quick we' are going to be able to get to some really complicated stuff that is actually pretty you not particularly standard for compilers classes to cover because you often don't have time and so getting to the point of actually y'all implementing first class functions is one of the things that we're gonna to be able to do before the end of this semester and I'm really excited for you allall to get there。

Okay， I'm going to hop back and do a little bit of logistics chat。 So let's briefly chat。

About the course website has all of the details of how things are going work in this course。

 Check it out。 Maybe bookmark。 I don't know。We do have one assignment out。

 honestly our main goal for this assignment is just to make sure that everyone has you installed OAMl right that's sort of a big thing just make sure that you can run programs in OAMl。

 that's the primary goal。In terms of what is going to be graded work in this class。

 it's going to be these things right here， so we're going to have drills。

These are technically graded， but they're graded for do you do them。

 right So this is going to be once a week。 It's just going to be us trying to get a sense of what concepts y'all are understanding versus what concepts y'all are not understanding。

 Hopefully it's also useful for you' all to figure out what concepts you're understanding versus what concepts you're not understanding。

 but the main goal for us is that we figure out what has been left unclear so we can go back and revisit and maybe just design a section around it。

 whatever the case may be。Homeworks， that's sort of our we're gonna use homeworks and projects interchangeably over the course of this class。

 Those are going mean the same thing。 Those are assignments that you're gonna to do solo。

 we have intentionally scaled them to be doable to do as you know groups of size one So that's gonna be basically your chance to apply these techniques hands on and get comfortable with the concepts that we are talking about in these class sessions and that of course we're going eventually cover on the exams which leads to the last thing midterm and exam。

 So we're gonna have one midterm in this class。 if you take a look at the course calendar on the website。

 you will see what day it is going to be we're also going have an exam the midterm is going happen during a class session。

 the exam is going to happen in whatever the official slot is that they give us and there are not alternate times so please。

 please， please now is the time to make sure that you're not gonna have conflicts with those times。

Also， please decide which section you are going to come to。

 So that is going to be starting up next week。now is a great time for questions about logistics， yes。

Sections are not mandatory。 I will mention that in general， when folks are feeling like， oh。

 I really wanted more hands on。Activities for the concepts that are appearing on the midterm of the exam。

 That's usually the people who weren't going to section。 So I definitely highly recommend section。

 but no， they're not mandatory。Yll are in charge of your own desties， you know。

 like do what feels right to you yes。The website is definitely up on the Internet。 Is it linked from。

 I will ask the GI if it's actually linked from the， but it is definitely alive on the Internet。

 I think if you sort of search for this class this year， you should be able to find it。😊，Oh。

 it still linky to the Spring 25， I'll let the GSI know。

I have asked for the class size to be expanded。 I haven't heard anything back yet。Hopeful。

 I will also mention there is often churn during the first one or two weeks。

 so historically most of the folks on the wait list have gotten seats。I can't make any promises。

 I'm sorry， I would love to expand the class。So we've got the request in。

There is a cl policy for the exam。 Yes， if you score higher on the exam than on the midterm。

 the exam grade will get counted for。Yes。If you go to the Es homepage。It's linked there。

 but if you search。😡，Just C164。 it doesn't show up on the official Es home page Oh， great， okay。

 so good to know。 thank you for checking that out。 It sounds like there's at least some link we can follow to find it。

 amazingazing， Thank you。Any other logistics in question？Okay， cool。

 I'll mention one other thing here as we're talking about sort of course structure。

 overall stuff that's happening。 and that is that the thing that y'all have just seen here of us doing a lot of time on live programming is gonna be a huge part of class sessions overall。

 I completely understand if that style doesn't work for you。

 but that is gonna be pretty consistent throughout so if it doesn't work for you now's the time to realize and maybe find a different class。

 we're gonna be spending a lot of time on that kind of thing。

 we're also going be spending a lot of time on these handson activities that we're about to see an example of once we finish with logistics chat。

So that's sort of the other big part of class that's going to be happening。Okay。

 a couple other teeny tiny logistics note。 drills are due in 9 PM on Thursdays。

 homeworkworks are do at 9 PM on Thursdays。 The goal here is that in prior semesters。

 we heard feedback from students that it was really annoying to have multiple different deadlines in a week。

 However， I completely understand if you're like， oh man。

 suddenly two things are due at the same time。 Don't like that。 In which case。

 please pretend that I said that drills are due on Wednesday and 9 PM。😊。

So go ahead and feel free to set your own internal reminders for a different time。

 We are going to intentionally design them so that you can do the drills before that time。呃。

You see all the details on the website， the tiny compiler that we built today。

 this is the start of all the various compilers that we are going to build over the course of the semester。

 we're going to keep growing and growing it。We are going to have the repository for that compiler available to y' all。

 We also have on the website a set of sort of compiler implementation notes。

 and those are basically for walking through the steps that we take for building that compiler in class。

 it's not a good substitute for actually class sessions because it doesn't cover the activities。

 it doesn't cover all of the conceptual content that we cover during sessions。

 So if you are missing sessions probably rewatching the lectures later is the right way to catch up rather than just relying on those notes。

 but those are there if you want to go back through the process of actually building up this course compiler yourselfsels。

 which I highly recommend it's very fun。嗯。The other thing that we're gonna be doing other than the other than the the live coding and that I briefly mentioned earlier is active learning。

 So these hands on activities， again， totally understand if that style is not for you。

 But the way that this class is structured， the core goal is to sort of give you the confidence that you can build。

😊，Not just the compiler that we're building in class but compilers of your own design for languages that you design yourselves going forward。

 and so everything in this course is kind of structured to support you in building the confidence to do that and so the particular kinds of content that we cover during lectures。

 the fact that you'll see me building compiler components throughout the course。

 the kinds of activities and discussions that we'll do in class it is all designed to try to make you comfortable designing and building compilers of your own。

This means some things about how to sort of engage with the materials that we have online。

 So in particular， if you read ahead in the course notes。

 the course sort of compiler construction notes， A， love that totally feel free。

 But in that situation。 If you've been doing that。 and then you're doing one of these sort of group discussion activities with your peers。

 please don't give away the answers， because it turns out to be actually in general。

 the teaching literature says that it is actually more beneficial for people to sort of invent these things themselves than to just passively be given them or to read them。

 that's one of the big reasons why we do these active learning activities to give you all the chance to sort of invent these ideas yourselves。

 It's totally fine if that's just not for you。 And you want to go ahead and read ahead。

 but just don't change them the way that your peers are discovering the material。 if you don't mind。

 I hope that makes sense。 that makes sense， yes。😊，Recommend。Especially for the。Yeah。

 so I definitely think that because live programming is not a huge part of every class that you'll go into。

 there are gonna be some folks who just can't get comfy with it。 And so in that case。

 like try to figure that out early and go ahead and find another class that has a style that works better for you。

 but the other big thing is usually by the time we hit like the third class session。

 people are comfortable sayinga that was way too fast， what's happening。

 walk me back through it please please please do that right if youre wondering about something that I did on their way too fast。

 everyone else in the class is wondering the exact same thing So please do if it is moving too quick。

 if it is confusing， stop me and say， whoa， whyd we do that know what's this assembly doing whatever whatever。

Would you recommend life？Or just。Great question。 Yes， so if you want to do it on your own computer。

 I would highly recommend doing that after class session。 doing it during。

 I think is pretty distracting because we do move somewhat quickly。 And so just， you know。

 taking the attention to be typing it out on your own machine in real time。

 I think would be pretty tough。😊，So yeah， I would recommend doing that maybe after class。

 if that's something you're interested in， I do think it's really fun。Okay。Feeling pretio， yes。No。

 yeah。 you can totally attend whichever section。 probably if we're like in the next couple of weeks。

 we're gonna figure out which sections are really popular。

 And because we do have a pretty small core staff， we might end up cutting some of the sections。

 So I think the GS size might even be sending out an official survey to be like， hey。

 which of these section types do you want， We'll figure that out going forward。 yeah。い前責た。

There is an extension policy。 There's no extension for drills because we really are trying to use drills to figure out like where everyone is right now in the class and we're actually like changing class content in order to adapt to the answers。

 So that becomes a lot less useful if that gets extended。

 but it truly is just participation right that one is literally just free points right just like show us that you're actually engaging with the thing and we'll give you the points。

嗯。But for homeworks， yes， so you have 15， I believe it is late days that you can just use without even coming talking to us after that。

 just come talk to us。Yeah。Yes。W， what a good question。

 I think it's already up on the course website， but if not it is in the。

 if you like search the Berkeley class calendar， it should be in there somewhere if you like scroll down to the bottom of the page or something。

Yes， sorry， I know it's annoying to find that stuff。There is an Ed。

 We are using it a little bit differently， so we're gonna to have  Ed as an opportunity for y'all to talk to each other。

 The core staff are not going be on there。 So we are really， really。

 really going be encouraging everyone to come and talk to us in person。

 And this is because one of the main things that we're focusing on this semester is really trying to prevent anyone falling through the cracks falling behind。

 And it turns out that if we have a lot of sort of digital access that doesn't seem to happen Where if folks come talk to us。

 we can sort of figure out when stuff's going wrong， make a plan。

 figure out what can we do to avoid stuff going wrong in future。

 And so we're really trying to encourage folks to come and interact with us I。Great question。

All right， cool， as more logistics questions come in。

 feel free to find us at office hours at these class sessions that discussion。

 we will figure out how to get your questions answered。😊，So okay。

 we are going to spend the remaining， how much time do we have？

We're going to spend the remaining 20 minutes。So right，ow time flies。

 we're going to spend the remaining 20 minutes on a little bit of an activity。

 so let's go ahead and swap back over here。

![](img/dbf1b61a40715d4708928ed8c38e560e_3.png)

![](img/dbf1b61a40715d4708928ed8c38e560e_4.png)

And we are going to see， if you look on， oh yeah， here' the here's the website。

 So if you were having trouble finding the website before。

 here's one of the ways that you can find it。And we are gonna to look at the activity that is linked right here on the schedule。

 Don't worry if you don't want to open it on your own machine right now。 That is totally fine。

 I'm going to put it on the computer right now so that everyone can just see it。

 And then we're going go ahead and do one of our little handson activities。

 So here we are on our Ocal intro plus language learning skills first activity。

 Let's see make this any bigger a little bit。 So for this activity。

 We're going to work on a strategy that we can use pretty broadly。

 But right now we're specifically going to use it to figure out some stuff about Ocal because we're expecting that this is a language that you probably haven't worked with before。

 So there's no expectation in this class that you have seen Ocabell before that you're comfortable with it before we're gonna spending a bunch of time over the next couple class sessions。

 really trying to get you comfortable with it。So one of the things we're going to be engaged in is trying to sort of form hypotheses about what a program is going to do。

 and then I know step three is a little bit silly， but I want you to actually seriously write down the thing that you predict is going to happen。

Because it's going to go ahead and be sort of that commitment mechanism。

 Like I really think I understand it。 and I am ready to predict what is going to come out the other end of running this program。

And then you can go ahead and actually run the program and check if your prediction was right。

 And that's going to be a pretty good way for us to sort of refine our mental model of what this programming language is doing。

 I'm going to run us through actually doing this process a few times。 So let's start with。😊，This one。

And I'm going to ask you to turn to one or two of the people next to you and work on this together。

 what are we going to go ahead and have if we put this line at the end of this program。

 what about if we put this line at the end of this program。

 what if we put this line at the end of this program？Go ahead and discuss。All right， let's chat。

 So what do we think someone shouted out， what do we think might be the output for A？

I'm hearing default test， if you think the answer is going to be default test， please hum right now。

If you think it's going to be something else， please hum right now。Nice， great work team。 Yes。

 so that is gonna be default test。 We have landed on the correct answer。 Our mental model was right。

 I am so glad that's lovely。 What about for B。😊，Someone shouted out。I'm taking this yes， okay。

 so I'm hearing I am taking this now， go ahead and hum if you think it's that。😊。

if you think it's something else？All right， same page， I like it， what have we got for C？

I'm here in Type Air。I'm hearing default 164。😊，All right， so let's hum for type error。

Let's hunt for default 164。Let's hunt for anything else。Okay。

 we've got some confusion about this one。 Fortunately， we can find out the answer。 And in fact。

 we can find out the answer real easy。 So let's go over here to Ocael Playground our very nice little thing that is going run Ocal for us in a simple way。

 if you are currently on your laptop。 but doesn't have Ocal installed。

 So you can go ahead and use this yourselfselves。 So here we've got the thing that we had at the start。

 this is still 164 in the string。 So if I recall， the one that we are confused about is 164。

 not in the string。 So let's find out what happens。😊。



![](img/dbf1b61a40715d4708928ed8c38e560e_6.png)

If we go ahead and run that。Whoa oh， we've got an error。What's going on okay。

 go ahead and chat with the folks nearby for 20 seconds， Why do we get an error？All right。

 so just to show that this really does work if we go ahead and add that back in。No problem。

 I'm taking this now， but then as soon as we convert it into not a string anymore。

We get our little errorer。So。What's happening？Yeah。😊，Yeah。

 it's kind of telling us right there in the error message right so it's got our back it's saying。

 hey， in some places you are using this as though it is a string right you are comparing this X thing to strings that means that you are expecting it to be a string but then you gave me this number thing this number thing is not good to compare with a string so it's watching our backs。

😊，Are there questions about that？Yes。😊，Great question。Yeah。

 so we could have said I actually want this to be an int that's coming in。

 I want this to be a string that's coming in， and it would have still complained because we just don't have the match right so everything has to agree in order for O Caml to be like。

 all right， I'm gonna let you run that。😡，Was there another question， yeah。It's tremendousd time。

For example。Great question， fortunately it's very easy for us to find out。So basically。

 all that Ocael really cares about， right Like it's phrased in this way that's a little bit surprising of I expected a string or I expected an int。

 All that actually matters is for them to match， right， All it's really telling you。

 even though it's saying I expected one or the other is they didn't line up right And so that's all we should actually interpret it to be saying is in some places you're using this as though this is a string。

 in some places， you're using this as though it's an int。

 We're not actually sort of privileging one of those over the other。Does that make sense？Go for it。

Yes， so we could absolutely say， hey， I wanted this to be an int or I wanted this to be a string in this case。

 this still wouldn't work because again， we're actually doing both right。

 And so one of these wouldn't agree。 but yes， we can say， yes。

 I want this to have type string or I want this have type int。 That's totally fine。

I think I spotted another question。Maybe not， maybe we're feeling good。Yes。😊。

Right around the end of the semester， we are indeed going to talk about type checking。

 We're not going to implement it for well。This is sort of true and sort of untrue。

 We are going to do some type checking for our language that we're implementing。

We are going to do some talk about static type checking at the end。

 we are not going to do type inference mostly a little little bit。Great question。Other questions。

In that case， onto the second variant of this activity。

 let's go ahead and turn again to our neighbors。😊。

![](img/dbf1b61a40715d4708928ed8c38e560e_8.png)

And let's decide。Basically the same questions as above， but with these lines and this starter code。

Go ahead and discuss for just maybe a minute this time。All right。

 does someone want to shout out what we think it might be for A？Well， it's sna braracking。

I'm hearing default。All right， I'm going to go ahead and ask us to hum if we think default。

How if we think default test？How if we think something else？Okay， cool。 yeah。

 So here's where I'm gonna briefly pause to explain this little thing is string and cat。

 So in case we were wondering what that little carrot symbol was。 that's string and cat。 Yeah。

 very good clarification for us to have。 Okay， so cool。 Now， what do we think about B。

 Does anyone want to shout out an answer for B。😊，I'm hearing I'm taking this now home。

 if you think I'm taking this now。I don't know if you think something else。Okay cool， same page。

 I completely agree， that's what we're going to be getting out。What about for。I'm hearing error。

 you want to hum along for error。Home for anything else？Yeah， oh man， same page。 everybody。

 y'all are doing so great。 So this is awesome。 So y'all's predictions were， in fact。

 completely aligned with what Ocael is going to do for us。😊。

And so I want to take a moment here just to pause on what we've had learned from this activity so far。

 so one is if and else's seem to be pretty familiar from things we've seen so far。

 we've learned that that little carrot symbol is string con cat that's useful for us to know we have found out that Ocael is watching our back in terms of how types work that is saying hey。

 you tried to use this string as though it's an int and it's going to complain and wh and not let you do that。

And we've also figured out that we can use this match thing。

 this thing that maybe is not so familiar， we can use this match to do things that maybe look a little bit like ifs and El's that maybe are more familiar。

 although soon， very soon indeed， we will see that in fact we can also use it for other purposes as well。

 but we'll pick that back up on Tuesday， Thank you everybody for a very fun first class。H let。

So I introduced myself Marius， it's great to meet you I'm Sarah。

Also I want to check I was trying to use the tutorials point I'm so sorry I do think it's gotten really bad I would go ahead and use can you see the URL on this one？



![](img/dbf1b61a40715d4708928ed8c38e560e_10.png)

I think this Ocal playground is way better for that now I mean。

 obviously soon you'll actually have Ocamol installed then you'll the like for now if you're just playing around with stuff thank you。

Oh wow， hi。Like in software engineering。And like。Amazing， yes。Because we're an election student。

 So I think。Got you have wait for the to that。Go ahead and put down your names and emails there so I can make sure like there's not a ton of lovers that I can pull back there。

 but I'll see what I can do Yeah yeah， thumb totally Oh I'm so glad I look I love this topic This is a really fun topic to work。

I am so glad， yeah。Other。な。い。I don't have access to it and I have the get go button on the website it says you don't have access I can you Yeah。

 that'd be great。Im sureYeah， I wonder if there's some kind of。Yeah。For example，Yeah。

That is so weird I wonder if this might be because the B courses is not officially published yet。

Potentially。So you should be able to already see the homework assignment because of the homework assignment just being linked from the webpage so for now I would just play with that and then I will go chat with the GSF Gi that is very weird drill if that works。

Well， that's not hooked up to grade scope works homework that is very weird I will talk to the geosize and make sure that anything and tell you what why don't you write at the bottom of that list。

 go ahead and write your email and just put a little asterisk next to that says grade scope。Hi。Yeah。

 yeah， okay， great fantastic， thank you。😊，Thanks so much y'all， have a great rest of your day。



![](img/dbf1b61a40715d4708928ed8c38e560e_12.png)

汚い。Understood， understood， yes absolutely like chances of getting in because there's a lot of people on the wait list。

 but I don't know how much you're going to open I think the chances any students on the wait please。

I'm not totally sure that' true I think there are some slots that are specifically reserved Are they reading I think so thought thes Department had a policy that they can only enroll concurrent enrollment students if no Berkeley student is the waitlist or something So I don't know we are all impending Oh yeah it will take like two weeks or something more for a decision which means we have to take like 10 courses at the same time right now So for the first two weeks you're just like attending everything damn I'm so sorry that's brutal。

What do you think it might be for lotss available or the department might extend the course fingers crossed I have requested to get the course extended I think the constraint mind might end up being sort of room sized because we do have sort of in-per exams but today Yeah I thought it was okay so I think it might actually be totally fine maybe many people don't show up and they just put the course again。

I do also think around that first homework often may get some drops。

 so it might be just totally fine for that reason。

![](img/dbf1b61a40715d4708928ed8c38e560e_14.png)