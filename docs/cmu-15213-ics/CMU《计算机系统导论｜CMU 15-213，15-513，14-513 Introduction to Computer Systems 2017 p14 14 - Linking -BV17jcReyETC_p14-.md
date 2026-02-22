# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p14 14 - Linking -BV17jcReyETC_p14-

I死了。ね。はじゃ、じゃこですません。

![](img/f83b09787c2af946c2cdcf84e77e1d66_1.png)

いですね。

![](img/f83b09787c2af946c2cdcf84e77e1d66_3.png)

![](img/f83b09787c2af946c2cdcf84e77e1d66_4.png)

Its really like I'm money like you。Okay， let's go ahead and start。あよし。So。

Today we're going to talk about a part of the whole compilation process that sort of。

The part that doesn't get any respect nobody ever talks about， but it' called linking。

 which is the concern of when you've compiled your code typically as a set of multiple files。

 how does it all get pulled together along with the various library code to form an executable program？

And like I said， it's an area that is sort of an offbeat area。

I think that the chapter in the book we have is probably about the most extensive coverage you'll ever see of LinkIn。

But it's an area where if you don't understand it， you can really get yourself into trouble。

 I'll show some examples of that。And if you really understand it。

 you can become a certain of power user and do some pretty cool things， so we'll cover that as well。

So， imagine we have。A program that's sitting in two different files。

Main do C and some dot C and mainine， of course is the main。Function。

 but it calls a function called a sum， and some is declared in main dot C， but not defined。

And then there's a separate file called sum。 C where the file， this particular function is defined。

 so that's one important distinction， declarationation means there's some statement about in a case of a function。

 what return type it has， what argument types it has。

But a definition is where you actually provide the code for the function。

So the job of a linker then is to with the normal compiler。

Is would take those two files and create dot files。

But those are sort of only partially parts of executable code the do files they're like the representation of the individual files on their own and it's a job in the linker to then pull those two together and also some information about the。

啊。The library is to create an exable program， which we'll call pro。

And so that's sort of the fundamental job of the linker that is somehow to resolve the。

These different pieces that there's a function declared in one file and used in another。

 so how does then the final code get pulled together and know how that original function is supposed to call this external function。

So why are there winers at all Well partly this idea of separate compilation you want to be able to compile individual files and you can imagine for the kind of scale projects we do in this class it's not so important。

 but when you have an entire operating system or the code base of a major corporation there's a huge amount of code that all has to get pulled together to form things and you don't want have to run the compiler over and over again every time you change some one line of code somewhere so this idea of separate compilation is important and the other idea is this idea of libraries that we make use of printF and A2I and ScF and malic and free。

 all these functions we call routinely and somehow those have to get the code for those has to be brought in so that our program connect system as well。

And then there's so part of it is just the convenience factor。

 the other is efficiency that we want to be able to have this executable program when it's all set up to run without a lot of overhead making calls to maybe external functions and also we don't want to have to。

Replate copies of say the entire C library over and over again in every executable program we make。

 and so that's an idea we'll call dynamic linking and that's a big part of what we'll talk about。

So the the key part of it then is this resolution， the sort of key activities。

 what they call resolving symbol， so a symbol is。The name of a variable or a function。And somehow。

 we have to。啊， we might。Reference it in one place we might。Thequet and others。

 we might define it in some and where does that all get put together？So。

We can see this sort of with our real simple example， is actually a pretty good starting。

As I mentioned， there's actually in this code， there's three different symbols。 there's within main。

 there's。This global。Variable called array。With。And then there's the main function。

 and then in the function sum， there's a function called sum。

And so those are the three symbols in this program one thing you'll notice is that R C， R V Val。

Those aren't symbols because they're just locally declared or vocally used variables。

 and so the linker doesn't know anything about them。

Only this things that somehow have a global extent or involve global decorations。

Exist in a way that the link isnt notice about。So let's actually just look at some examples。



![](img/f83b09787c2af946c2cdcf84e77e1d66_6.png)

And our friend， Object D。When you give it the flag minus t。

Can tell you about the symbol table in functions and of course。

 like a lot of things it looks very cryptic until you get used to what it's saying。

But you'll see down below。啊。The three symbols in the function that are somehow appear in the function main。

 The first is the main function itself。And it's the as part of the text。 Remember， text is the。

this named where the code is， it's not text to identify its strings。And。There's this array。

That's also declared there。And then you'll see some is listed。

 but it has this parameter star UND star， meaning it's not defined in this particular function。

 but it's。打。Somehow reference， so it's something that the winer is going to have to help resolve。

If we look at the code。For Maine。With object jump。If you say show me relocation information and。Code。

 so you remember what you've disassembled code， you'll see that there's。啊。我 look at this。

On the slide， but the first。There's some funny entries there。

 you see the R of your score x866432 and PC 32。That's information。

 basically what's happened with objectject is it's merged information from the symbol table into the disassembled code。

 that's what this argument I gave and you saw it was minus RD。

 so disassemble and shall relocation information。And what that's saying is that this particular line。

The first one is going to be where the。Aress of array。

 this global variable will be put somehow inserted into the code。

And then the second is where the call to。Some is going to be。

 and somehow that's going to be put into。So the pointing that this original dot O file。

Although it contains this in binary form executable code， it's incomplete。

 there's some words in there that aren't fully filled in and it's the job of the linker to actually insert into those bytes and the code。

 the exact address information that's going to be used in the executable program。



![](img/f83b09787c2af946c2cdcf84e77e1d66_8.png)

So we'll see how that takes place here。

![](img/f83b09787c2af946c2cdcf84e77e1d66_10.png)

One of the kind of interesting lessons about this too is。How the linker is really。



![](img/f83b09787c2af946c2cdcf84e77e1d66_12.png)

啊。It's not a compiler。😡。

![](img/f83b09787c2af946c2cdcf84e77e1d66_14.png)

It's sort of a past it assumes that the code has already been compiled and there's just enough information in the symbol table for it to be able to do its job。

 which is simply to。

![](img/f83b09787c2af946c2cdcf84e77e1d66_16.png)

Overwrite a few bytes here and there of code and then pull it all together in one big file so that you have an executable program。

So the job of the linker then is to merge these separate code files and the data section。

Of the program， you remember， Dan is where the。Globally， do create variablesable are。Into。

Common areas in the final thought。And then to deal with these symbols that need to be resolved。

And make it all so that the final file is the executable code that you want。So as I mentioned。

 there's。The dot O file is。It's sort of the start of an executable program。

 but not a complete program， it's called relocatable object font。

And it just has the code that the compiler has generated that。

Describes everything except the global variables are kind of。In this odd state。

 partially not unresolved state。Then the final file that becomes the executable is called an Adot out file in ancient times。

 I guess maybe it's still true if you don't give a minus little O designation to GCC。

 it will produce a file called A dotL。And then there's another kind of file that we'll look at called an SO file which is used for shared libraries and we'll come to that。

 so a shared library is a little like a doO file except it contains information that allows the linking to be done right at the last minute of the program。

If you're familiar if you ever were a Windows user and you're always struggling with VLLs。

 dynamically linked libraries。That's what a dot SO file is。

And so all these are represented in a common format called elf。Which is a standard。

That actually isn't just for X86， it's across any sort of Linux style of machine。

 all have this common format called health。And so you'll see that term elf binaries。

And an elf file then contains a lot of little pieces to it， and when we use objectject dump。

 what we're doing is we're sort of examining bits and pieces of that file。

 so if we say minus D it says we want to look at the text section and disassemble it for it。

If we use the minus T flag， were saying， just tell me the give me the symbol table out of this alpha file。

Some other ones that are useful to know about are。啊。Sort of general information and the header。

 like what class of machine it is， what's the Indianness of this program。And so forth。

 the dot text section is the executable code。The RO data is for data that's read only but globally declared。

 and that will typically include things like string constants。

 you know your printf format strengths will end up in this RO data。Then there's dot data。

 which are the。Global variables that have been initialized and then another region called BSS， which。

好。Has various。Interpretations， but I like the term better save space。

The idea of a dot data section is it's an array that you've given or。

That you've given some non zero value to potentially and so that all that information has to be stored in the。

Executable program to be able to read it out some tables。But if you just declare。An array。

It just gets thrown into BSS if you don't initialize it。

 and what happens is when that all gets pulled together it gets zeroed out。

So it saves a little space in the executable because it's just going to set it to zero so it doesn't have to store the actual zero values in the executable。

And then there's the various sections that are shown in gray。

 which are more used for resolving some of this information。I'll also mention it。

 we won't really go into it， but the dot debug section is interesting that's how GDP works。

So or any other debugger， you've noticed you can when you have a source code available。

You can set break points and examine variables based on their names in the program。

And you might think that somehow this GDP actually has access to your source code。

And it's figuring all this out。 It's actually the the secret is all contained in this dot debug section。

 which we're not going to really talk about， but it contains basically the line numbers。

Of all the program points and the names of all the variables and how those map to parts the executable file so that you can it looks like it sort of knows what it's doing。

 but it really doesn't。GUP doesn't really know much except it can have a pointer from your。

In this table， to say。If the user says set a breakout line number 171。

 well 171 corresponds to this address on the codes instead of break point。

And so that's described here so the dot real information is this relocation information that's how to。

嗯。Relocate both the text or the code and the data of the global variables。

 And so I showed you that a version of running object dump。

 What it's doing is it's taking the REl dot text section。

And mapping that and showing how those fit into the different parts of the code。Okay， so。

There's a few kind of general principles we have to understand here first。One is this idea of symbol。

 so I said a symbol is either a。Variable or a function。 And somehow that。

Kind of escapes out of this particular file and is known to the Winer。啊。And so in general。

 those will be。Ones that are are defined in one part of the code and reference to potentially referenced in another。

And so within a file， then there's some external symbols， ones that it。

The definitions exist elsewhere and some local symbols。

 ones that are defined in this particular file。And so symbol resolution is basically figuring out what symbol means what。

 what file is actually contains the real definition of this particular symbol and that the linker should then reference from all other files。

And it's pretty simple in this case。嗯。For example， array is a symbol that's defined and referenced in the same file。

Our main is。Defined in the main function， and then that's of course used by the compiler to set up the beginning of the program。

A sum is a case where it's defined in one file and reference to another。And as I mentioned。

 things like Valal and Arg C and Arg V don't show up in any symbol tables because they're not known they don't exist。

The linker doesn't have to keep track of that。And similarly， these other variables within sum。

So here's a little。Pastion of your thinking。Here's a bunch of names on the right。And the question is。

 which of those actually become symbols in this file called symbols。c？

So let's just do a this the answer is either yes or no。 So let's just do a little。What about time？

Yes， time is a global variable。F。啊，A。B。Right， so those are all local variables。It's same with RB。

 RGC， what about Maine？Pre de。Anything else here that looks like a symbol to you？

This is a trick question。So actually， this format string。Shows up in the symbol table。

Because it goes into read only data。So you can look。We can。



![](img/f83b09787c2af946c2cdcf84e77e1d66_18.png)

嗯。We can get our answer then with tools， we can see at the bottom food main print S and time are all symbols。

 and then there's something called Ardata。t1。1。And you can't see the value of it。

 but that's actually that format string。So。It's kind of an obscure point。

 but the point is that constant strings like this are sort of treated a little like global variables。

 but they're put into readon data so that they if you tried to modify that string。



![](img/f83b09787c2af946c2cdcf84e77e1d66_20.png)

嗯。You get an error。

![](img/f83b09787c2af946c2cdcf84e77e1d66_22.png)

![](img/f83b09787c2af946c2cdcf84e77e1d66_23.png)

Yes。

![](img/f83b09787c2af946c2cdcf84e77e1d66_25.png)

Well， even if you assign it to a variable。So if you said something like Carestar。



![](img/f83b09787c2af946c2cdcf84e77e1d66_27.png)

Athic equals quote， how do。quote，That would actually that string。

 how do would be allocated and stored in RO data。And then your variable would be given a name。

And now if you said if that name is， actually， that's a good question。We'd have to try that。

 so you said Carestar S is equals to some string， and then you edit there。

I don't think I don't like that， they will not be happy。Yeah， you can try it Now。

 if you said carestar buff of 10 is equal to a quoted string。

Then you can modify the elements of busuff。Because what you're doing is creating an array and initializing it。

But if you give it a string constant， that's just what it says， it's a constant。

So you can change S to point to a different string， but you couldn't change the contents that string。

I'm pretty sure that you could double check by trying to compile and picture that。

That's a good question。Okay， now there's an interesting sort of nuance here。

 which is the things that are declared as static in a file。 so you know that static has。

Like a lot of things you'll see has multiple meanings， depending on context。

So one of them is if within if you want to。A sort of semi global variable。

 a variable that's accessible within this particular file， but not by the rest of the program。

Then you should declare it staff。 and static is actually a very good habit to get into。

And including making your functions static if they're not going to be referenced elsewhere。

 just to avoid sort of。Name confusion， especially if you use names like X。So anyways。

 you know that to say something is static in a。And a file makes it sort of a variable that's global within this file。

 but not accessible outside。嗯。And then there's another version of static。

 which is if you declare a variable within a function。

 a local variable within a function to be static。Then it's essentially shared across all calls to this function。

So for example， you see three different x's here。Those here actually will all be three different。

Variables。The main one called x is accessible， for example， by this function， H。The function。

 the one within F is only accessible by calls to F and the one。And G is only called by a calls to G。

 And the other trick is that where its it's given a value like 17 or 19。

 but that's only done the first time the function is。Invoked。Or maybe。Yeah。

 the first time it's invoked and thereafter it will change。 So it's a way you can。好。

It's just a tricky way you can sort of hide information。说明。

So it turns out that all three of these will end up being symbols。

Even though they're local to this and that the linker is going to have to help resolve them。

And then you say， yeah， but how does the linker keep track of three different x's all in the same file？

Well， what it does if we look？

![](img/f83b09787c2af946c2cdcf84e77e1d66_29.png)

一？I got a bunch of examples here。You'll see up through the midway through。

 see if my query is working。嗯。That there's three x's。

 but one of them is the sort of global variable X。That's for the whole file。

 and then this x dot 1721 and x dot 1724 are the sort of hidden versions that are within this particular set of functions。

And so。嗯。If I look at the。Yeah， it's kind of messy to figure it out。

 but you'll see that somehow all three of these functions need to have some relocation information。

Without going into the details soon。

![](img/f83b09787c2af946c2cdcf84e77e1d66_31.png)

So the point is even if you declare a variable。

![](img/f83b09787c2af946c2cdcf84e77e1d66_33.png)

If you declare a variable is static。嗯哦。What the answer。



![](img/f83b09787c2af946c2cdcf84e77e1d66_35.png)

If we can figure out。Yeah， it's not totally clear from here that like the variable X is only accessible within this particular file。

But I think somehow that's built into the symbol table。

I don't remember all the exact meanings of those various。Gese and capital Os。



![](img/f83b09787c2af946c2cdcf84e77e1d66_37.png)

Yes。

![](img/f83b09787c2af946c2cdcf84e77e1d66_39.png)

Does the exercise？Yes，If you were to run this， which I don't think I have set up to do。

This X is shadowing this。So。ID。Theses， these functions all refer to different the three different xs。

Yes， right。Yes。WWhy is the static？せ合で。啊，可以的啊。It's still the job of the linker to merge remembering that in these dial files。

 it has each of these sections。The different data sections in the text section。

Are all in there and then in the final elf file it needs each of those sections。

 but it has to sort of pull them out and concatenate them together from the different files。

 so it needs that information to kind of build up the executable。

 even if it's not trying to resolve the symbols across the different files。Pちゃ。

These are good questions， bud。

![](img/f83b09787c2af946c2cdcf84e77e1d66_41.png)

![](img/f83b09787c2af946c2cdcf84e77e1d66_42.png)

So thisT just says what I said， allocate space。Actually， they allocate them in BSS。

No should to help them data。And then but it gave unique names to the different ones。So。

When there's multiple symbols declared in multiple files， how is the linker supposed to know？

Which one to you use is it where is it actually defined， which definition should it use？

And so there is sort of a klue way that happens by default。

 and I'll talk about the way you can make sure it really happens the way you want it。

 but let's talk about the kluge way first。And that is every symbol is either classified as strong or weak。

 and a strong symbol is one where there's an assignment made to a variable or there's a definition of a。

As a function。And a weak symbol is one where it's just referenced or it's declared。

 but it's not actually given any definition。So for example， in this case。

 you see that fo is strong in P1 and weak in P2。And the functions P1 is strong in P1 and P2 is strong in P2 and not weak in either place and not used in the other places。

And so the general rule is if you have multiple strong symbols， then you'll get a linker error。

Multiple decorations， blah， blah， blah， and it won't link your coat。

The other is if there's a strong in one place in a week in another。

 then the strong winds beats the week because you can imagine from minute。刚。

And if there's multiple weak symbols， this is the collugy part。It'll just pick one and say， oh， okay。

 that looks good， we'll use that one。Which can get you into trouble。

 so let's look at some problematic aspects of these rules。Actually， let's do some puzzles first。嗯。

So imagine running these。Each of these pairs will be imagine code sitting in two different files。

 we try to compile and link it what's going to happen。So here。

 what will happen with the first storm if we try to comp on？So is P1。

 is it stronger weak in than two files？It's strong in both right， so that'll give an error。

 the Winker will say can't do it。嗯。What about the second one？

So now I'm calling P1 and P2 so they're distinct。And x is weak in both places。

 and so it will just say， okay， I guess x is。It wouldBasically arbitrarily choose which of the。

X is to call sort of the globally used X。Now we get into some funky stuff。So what if we have。

 you'll see x here on the next one is weak and in both places， but it's dec with two different types。

What do you suppose will happen there？This is where it getss Fuji。Yeah， I think。If you hand up。Yeah。

他是。Yes， potentially， actually。If you run this code， you'll get a warning to say。

Two different sizes because the double is eight bytes of one than four of the other。

But it will actually link the code for you and when you run it。

 probably what will happen is when you change。A in the right hand file， it'll zap。

The values of both x and y in the left hand。Prob you。

 all these are sort of dependent on random things happening。The point is， it will。Do， and actually。

 let me just。I'm going to run through this example and I'll show you some code where it really does do some fishy stuff。

嗯。And then this is a case where it's。A similar problem except it instead of just sort of。

When we choosing， it's strong on the left and weak on the right。

 but the point is the linker does not do type check。Thelin actually， it knows how big something is。

 but it doesn't know its data type。So as I mentioned。

 I think what you'll get on these is a warning message。

 but not an error message that says you're trying to link things and these variables have different sizes。

啊。And then the final case is sort of the good thing。

 so this sounds really bad and you could see a lot of bad things happening。And in fact。

 here's a real example。Where I declared。A long int。 so it's an eight byte integer。And a double。

And you'll see that the linker。Is perfectly happy linking these two files。

With no error messages at all。And。So let's see what happens。



![](img/f83b09787c2af946c2cdcf84e77e1d66_44.png)

So I type mismatch and it's supposed to print the value of x。And it prints some long， big number。



![](img/f83b09787c2af946c2cdcf84e77e1d66_46.png)

![](img/f83b09787c2af946c2cdcf84e77e1d66_47.png)

![](img/f83b09787c2af946c2cdcf84e77e1d66_48.png)

So anyone figure out why I printed that number？Yeah二。So， you know， story with double。

And we access point at mainstream see us tension as liquidity in value。

You've got it exactly so there's some bit pattern to 3。14， which is， as you know。

 there's all the bits up at the front with the。And so it ends up getting a lot of bits。

 a lot of one is in there。And now the name thinks it's a long end， and so it just prints it as head。

The point was that the compiler didn't complain， the linker didn't complain。

 everybody was happy except for me because I this。Really back stuff execution。

 And you could imagine that happening。 Imagine that in。You're working at major global tech company。

And this happens。And。じ。Somebody's going to come around and point a gun at these two people saying。

 why do you commit that file？呃。So something should be done， right？So how can we， well， actually。

 it turns out there's a couple things。That are pretty important。

 one is to if something really is not going to be shared across files。

 you should declare it as static， just kind of keep it within the fold。

And if it's going to be a global thing that you need， then you should use this external decoration。

And external is sort of like a weak symbol， except it's even weaker， meaning that。If the linkquor。

You saw it with these weak symbols that in the end it will choose one and use that。

If there's no strong declarationation。An externalt。

 if there's no strong symbol with that name somewhere， then the linker is going to complain， it says。

You told me there'd be something called x， but I don't know what x is。Yes。😊。

So external is external and the interesting thing， let's see。Here's an example。

demonstratingmon this idea。And this is sort of one of the ideas of making use of a dot H file。

And you see in my dot H file， I declare G to be an external in。

And I found included in two different files。So in the upper file。

 you see that it's truly as external that in G does not， it's just referenced here。

 but there's no definition。You'll see in C2。C， it's actually。Defined in here。

 but the compiler is happy with that， I was just reading to make sure I believe this。

You can say in this because remember pound include is not something magic。

 it's literally a direct expansion of that text。Within your file。

 it's done as a preproces step before the compiler really touches your cover。So。

It's as if you just copied that those two lines directly into this file。And so effectively。

 within a single file， I'm saying。There's an external ink， called G。And there's an int called G。对。

But it's fine。That' sort of it's。That's purposely allowed so that you can do these condo clues。

And so the G will be resolved then to be this unique integer G that's defined in this particular file。

And the good news about that you see is if I do it this way now。

 I won't have that mismatch of types if everyone's using the right dot H file。

If it was used as a double in one place and as an int in another。

 then would you'd have a complaint by the compiler because it would say， okay。

 you said the G is an external int and now you're trying to create a double codex and you can't do that。

That makes sense to people。 So that's sort of the part of the purpose of。Of dot H files and the idea。

Question。そ一个どこ的。Even if you don't put an extra above it。And that make it a week symbol Yes。

 so you could do you could do the same idea of。Just take out that external in Gobo。

h and that would become a weak symbol。And it would， in this case， give you the exact same effect。

The difference is。If I omit that line， if g equals0。And I still have an externalern。

 it will give me a linker error or say， you've told me there'd be something called G。

 but nobody's defined it。So with that externaltern， I have to in one of the files actually。

Deeclar it。So it's the same idea。It's a little bit cleaner to say Extern。

And this is another example that a previous lecture put together。

 so I thought I'd show it is another style of dot H files。It's considered of in a single file。

Kind of have different sections based on whether it's the the。呃。And Mo。

 the one that's actually defining this。Whatever the file is。

 this variable and the other that is just consuming that information。

And that would be especially if you have a file。 H that's the name of some where you're declaring whatever data structure and API that you're going to give to some module。

Then you might want different sections on whether this is the pound include within this particular file or So the example here is if I say pound if def。

 it means if there's a compile time constant called initialized that's been defined。Then。

 use the red code。And if not， the news is wh。So now if I。And include。Gbo。t H。

 after I'm defined initialize and the default value initializes it defines it to be one。point isですね。

De fine。Then， here。This in it。And this G。Would refer to the red code。

And up here where I don't define initialize， it would refer to this black。

And so this example is a little too small to appreciate it。

 but you'll see that's a fairly common pattern of like if you look。

 if you go back to the C programming lab。You'll see that I did some tricks to。

Use different versions of the。Of different functions， depending on whether it was internal or。

 whether it was your code or micro。I'll show you that in a minute。Okay， so as I mentioned earlier。

 in response to one of the questions is。Each of these doO files has its own little。

 it's a complete L file， so it has all these various sections。And the job with the。

Makeer then is to pull those together and create the relevant sections in the final exeable。And。

This is something I already showed you。When I used object dump minus RD， so where you。

Disassemble with relocation information， and you saw this function called Maine that。给。

Needs to know where some is stored and so that's what this first relocation information is about and then also。

I'm sorry where array is stored and then it has to be able to call the function sum。

 and so it has relocation information there too。And actually， if you look carefully。

You'll see that the initial pattern here is just all zeros。For both where this array is stored。

And what function it's calling。You can think of that as a placeholder in the code of four0 bytes that will get filled in by the linker with the exact bytes to use。

And so when you finally compile this and link it together into a executable program。

You'll see that in the end。This call has been。show in with。With value 5。

And this idea is it's so called PC relative。 so it actually the true address of。

S is given by adding phi to this address， the return address。

 and you see that gives you this 4 e page address。And then up here。

Its the global variable called array has been stored in address 6101018 and so that's been inserted into these bytes of this moving instrument。

So the linker actually then。Hold the text together。

 but it also inserted the appropriate values in some of the bytes of this code to give it。

A the right references。 So when the program finally runs， then。

It just is calling the right functions and accessing the stuff。

 so the linker has done the real work of getting this program ready to run。

And then when your program first starts off up， when you invoke it。

 it's called loading when it brings it into memory and as I we mentioned a previous lecture。

That's all spread around this virtual address space of your program。

 some of it's used for your stack。But the parts of the linkers set up are these various sections that are。

嗯。Code， data， some of it read on with， some of it readable and writeable。Okay， so pull up here。

Laptops。 And let's give this。Quz a try。有。Okay， let's go ahead and see how you did。

I have to confess that I didn't get all the answers right when I did it the first time。

What's your general feeling about Can， by the way？Well， let's see。

 let me just go through it with you。Okay， sorry。Technical difficulties。Question one。

 you have two source files you want to share them， which approach should you take？What did you think？

That should be kind of what I this second。Exterern， you've got that。Yeah。How many of them following。

 which in the Let's just turn this into a witch。Which of the following will be in the symbol table。

 my global2？Yeah， my share in global。Yeah， it will be in the symbol table。

 just be marked as not defined here。And then， soup。All right， so the answer is three。Okay。

Back to Casius。If B equals4， capital B is4， that means four bytes per block and it's a 64 byte cache and it's direct match。

他问你下。16 right， it has nothing to do with the address size that was a misleading。It just says that。

Because it's a direct map so that。So the E is one， so it means that。

Each of these bites of each qua is part of a different。是。Okay。And then the last one is。

It's sort of a。Actually， the official answer is it's undefined。

What I believe would happen if you ran it is it would actually compile OK。

 and then the linker would give you a warning。and it's not because it knows the difference between a double and an in。

 it knows the difference between eight bytes and four。But yes。

 it's an undefined would be a good way of saying。Okay， so I don't know who got what answer。

 but that's the answer。

![](img/f83b09787c2af946c2cdcf84e77e1d66_50.png)

Okay， so let's move on now， we sort of now have a sense of what this thing is supposed to do。



![](img/f83b09787c2af946c2cdcf84e77e1d66_52.png)

嗯。And let's sort of。

![](img/f83b09787c2af946c2cdcf84e77e1d66_54.png)

The basic idea of linking， we've only looked at how do we link our own files together。

 but the sort of one of the really big roles of linking is how do we link in all the library stuff？



![](img/f83b09787c2af946c2cdcf84e77e1d66_56.png)

So back in the battle days， basically this would all be brought into a single file。

 you just compile the whole thing every time。嗯。But nowadays in another previous era。

 you do what was called static linking， so static linking is linking except you bring in all the files into the final executable。

啊。And you can do that， you can actually force it to happen。So， if I。

The library files are in an archive format called dot A。嗯。

And you can call a program called R for Archivver。And create， excuse me。Your own library。Code。🤧。

Excuse me， so this imagines it if you were。Creating the file for the C library called Li C。

You can archive them all together and create a big dot A file。And then when you go to compile。

And so for example， if you look on a machine。You can use the archive program。

 which a little like tar except without the T in terms of the arguments you give it。So。

If you archive， you can actually look at。All the functions。

 you can list all the functions that are available in the C library， each of them like printntf。

 they're eachA in separate files。AndBut that file is。Is 4。6 megabytes。And the Y M。

 which is the math library， is two megabytes。So the point is those all exist。

 they're in the standard place on a Unix or Linux system thats used their s live。And the other thing。

 you know when you。啊。So I can actually simulate， I can do this myself。By setting up。

 if I have some other library I want to use andally link it。

 I can do that sort of the same way that the C library is。

 so I can create an archive file called livevector。a。And then within。

Some file that can make use of these， just like you would use prints that I can call a function called AdV。

 which。I've defined in this doh file called vector。h。

 and then somewhere off I can have built up this whole library of functions and then ask the compiler to link those in。

So。So what happens if you declare in GCC if you say ST？It will do all the linking statically。

And it will actually create a file that's almost a megabyte just for this very simple program because it has to have。

Copies of all the function， not all of。Of YMC， but all the functions that it uses。

 which are a lot of them that are sort of under the hood there。啊。

But the point is that I can have introduced my own library here。

And there's a little bit of a convention， you'll see that when you give the minus L flag and give a name。

 the default is that the actual archive file then is live。LIB， then that name。A。

And so minus L says include in the linking。A file called Y vector。A。

And this minus capital L dot is saying。The capital L is telling the linker what directories should it be looking in for dot A files？

The default is in user wide。But and。By saying dot， that means in this local directory。

 so it's saying also look for dotA files in my local directory。

Which is where I happen to have this live vector。 A5。So all that obscure notation is。Is there to。

Tell the linker where to pull this stuff together to create the final fight。

So this is actually a pretty useful thing to know if you ever have to maintain a large library but you'll end up。

Using these dotA files quite a bit。But it's not very efficient for a really large library。

 as you've seen， the other problem with it is。嗯。So anyways， there's a。A whole thing here， about。

How does the linker find these files， how does it know which ones to pull together。

 and basically it will scan through the command line。In the order that it's wasted。And it will。啊。

Have the。Pull in the files and so if my library code calls TriDF。And my main original code didn't。

Then at the end， it will also pull in printf of the YC。

 so it has to be able to sort of pull in more and more pieces of code as it reads code and those reference others。

And you can get into sort of quirky linker errors where the order in which you list your files。

Will make it work or not work depending on。They' wondering which things you defined。

 and it could get pretty tedious。But that's a little off topic for right now。

There's a few problems then with these statically linked libraries。

 one is that it's just you end up with bloated code。

 you end up with copies of the same code in a bunch of places。

But a perhaps more serious one is what happens if there's a bug in a library and somebody wants to fix it？

😔，If that library has been statically linked in a bunch of other places。

Then there's no way to track those down and update them and so there's stories and this there's a link here to a。

Wb post in Google， where they discovered a。A weakness in one of the commonly used libraries is exploitable fllock。

 and the biggest problem they had was tracking down all the places where that library code had been linked in statically and therefore even if they fixed the bug and their version of the code that fix wouldn't get propagated to all these kinds。

呃，So they写这个呃。A couple of reasons then why you don't want to statically link。

And so that brings in this idea of dynamic linking with shared libraries。And so for example。

 and as I mentioned， those usually have the extensionion。 SO。And。

Those will be dynamic linking and there's actually two forms of dynamic linking。

One is called mode time， meaning when the program is first brought into memory。

 getting ready to execute。Then it will go and pull all the library information in and add that to the pile。

 and that's the sort of default， that's what normally happens。

But there's another more clever thing where you can do runtime linking。

 where you can basically wait until the program is started and then link in a library。

And I'll show you some of that。So let's just look at。



![](img/f83b09787c2af946c2cdcf84e77e1d66_58.png)

My example is a little different。So。That program。This see个。Oh， the one that involves main and some。

This one， so main calls some。That gets compiled in the state linked version of it is called probegue。

two。See。And it's all statically linkeded and if I were to object dump that。

 I don't know if you'll be able to see that。

![](img/f83b09787c2af946c2cdcf84e77e1d66_60.png)

ま。

![](img/f83b09787c2af946c2cdcf84e77e1d66_62.png)

As you know， from looking at bombs。嗯。Its is。I can't get the right answer。

But the the the one that's the more standard is called probe 2 L was just generated by the sort of default commands。

 And if you do， the runner program called。LDD。You'll see that LDD tells it what information does the。

啊。Oh I'm sorry Pro2 is a different program probe2 is this one with the vector library。So probe two。

 let me just go back to what I said， it's the example I said where there's us。

Vectctor library that we want to link in so you'll see that probe2。Requires the standard YC。

 but it's also looking for a file called webvector。sO。

And it actually tells where those are located as well。



![](img/f83b09787c2af946c2cdcf84e77e1d66_64.png)

So that's an example then where I have set up。

![](img/f83b09787c2af946c2cdcf84e77e1d66_66.png)

My own version of a dynamic linked。

![](img/f83b09787c2af946c2cdcf84e77e1d66_68.png)

Library， and that takes a little bit of。

![](img/f83b09787c2af946c2cdcf84e77e1d66_70.png)

Weird stuff with。With GCC。So first of all， I need to create a。诶呀。There's a mistake in this slide。

Excuse me。It little fix on the fly。

![](img/f83b09787c2af946c2cdcf84e77e1d66_72.png)

So with this magic incantation creates this dot SO file， the dynamic wave winable vector。

 and so you see when I compiled it。I had to give this flag minus F P。

Pix stands position independentdependent code。And it's a particular way of compiling the code and its references in a way that makes it possible for the。

Linkker to be able to shift the position that code around in the file without。

In a fairly straightforward way。So that's required for executable library code， it's not the default。

And now when I。Want to create this。Dont SO file， I have to now say。

You give this5 minus share to tell it that what I really want to do is and so even though it says it's to Gcc。

 it's really to the linker itself， it says create a file soand so。

SO containing these Donno files and if you haven't compiled it with PIC it'll complain。

So that's all sort of this picture sort of shows that whole thing always one step。

 you can start with the dot C files。Tell it that you want position independent code and that it should be shared into a vector and that will create that'll do what those two steps I just showed were。

You't create this thing called livevector。sso。And then the。Winker will build this all together。

 but as I showed you before， once I load the program is what it actually。Brings that library in。

And assems it together into the actual program that's running on your machine。

So this is called load time， meaning that the。The actual library code gets added to your code。

The time the program is first being started up。Now you can do even a more exotic thing。

 which is you can basically within your own program called the Lier。

And so that's called runtime linking。And I'm not sure why you want to do this， but you can。I mean。

 I can think of some scenarios where you want to do it， but it's a little bit obscure。

But the basic point is there's a library a program called DL Open that you see， it opens。

A dot Sl file。And it does what's called lazy。Meaning it just opens it。

 but it doesn't do anything until you。啊。Don't to do more。And then there's a function called DL Sim。

 which means resolve a symbol。Of。And you give the name of the function。As a string。

 and basically it will create it will resolve that symbol for you using the linker。Functionality。

To create now a pointer to something。Which will be this function called a。

And now you'll see I can call AdvVc just like before。

But the point being that Edbcgo had no meaning whatsoever until I made this call to GLSim。

 it was an no point before。So it will actually fire the linker。

Pollman resolved do all the appropriate resolutions of the symbols and so forth。

Create a pointer that then you can use as a yes。需用微信的。番す。我啊增家到好。Oh in。

 the linker will do the same thing that the dotA files is is if you have a bunch of functions in different separate files。

In only put the files that you're actually referd。任不放弃。

If you had a bunch of files in a bunch of functions in one file， it'll pull that whole file。

The linker is not that clever， right， The linker kind of knows about lots of stuff。

And it had various pointers to it， but it really doesn't have this granuary of individual function。

So the lesson on that is if you're creating a library and you're worried about that。

 you should use a bunch of files。Good question。So this is all the magic you need to make that run。

 which is quite a bit。And you have to include this library， the dynamic link。Library。

You have to include it because that library now becomes。

This code that's used to do the actual linking。Okay。

 I want to just finish with one real quick thing that's。That actually gets pretty useful。

And what's called interpositioning， which is when you want to track the calls to some function。

And the most straightforward version of that is。Like for profiling， or for example， you've seen in。

When you did the。C programming lab， you you thought you were calling malequin free。

 but you weren't calling the library versions of that you were calling versions that we had where we were being a little careful about making sure you didn't have any。

Orphans left over you you freed everything and you'd get error messages if you hadn't。

 and Valgri's a little bit similar that you can run vgrid on a program and somehow magically it's keeping track of all your calls to Malican free and figuring out if you have any invalid references in there。

So Valelgrind is also making use of this idea of interpositioning。嗯。So there's sort of。

 and this is covered in the book， so we're going to run out of time。

 but let me just show you three ways you can do interpositioning。

The most straightforward is compile time， and it just makes use of macros。 So imagine I have。

A library instead of。Call it a little library where I've declared my own versions of。Mican free。

But I want the uses of this library to think that they're actually calling regular meican free。Well。

 if I just provide a DtH file that uses Po to。To sort of alias。啊。

My Malic with MalC and My free with free then in that users' code。

They might not know that they're being tripped right。

 and that's exactly what the C programming library does and you'll see that later this term when you look at the milk。

You're going to write functions called mein free， but they aren't really mein free。

They'll get their areass to some other name。And the advantage of that is now it only works if you have control at compile time。

 but now I can do things， you know， my milk and my free， the difference here is that they。

Print information about what's being mount and freed。

There's another version which is called link time interpositioning， so this happens。As， as the。

Liiner is doing its work， so it's still part of the compilation process。

 but it's after the dot o file has been generated and's it's really cly idea that they set up just for this purpose is that。

They put these little prefixes on standard names。So there's one called real and there's other called rap。

And so the wrap is the one in your。In the code that's being。

Interposed on and the other real is the one that calls the actual library routine。So for example。

 I can declare functions called rap Maic and rap free。啊。

And they call real Maikin real free because real Maikin real free are the real thing and the wraps are the phonies。

 but the linker will。Waier substitute in the rap names in there。

And then if I pass a whole bunch of flags to GCC。To do all this wrapping of malin free。

You'll see that it actually will。Create this code that is。啊。Is making use of this？This new library。

 this interposed library。And the final version I'll just describe it here， and like I said。

 it's worth reading this part of the book， this is interesting to you， is this really clever one。

Where you make use of this dynamic linking。And you。Basically。At runtime。

As the program is basically being pulled into memory。

 it magically will interpose on the library and just to demonstrate。



![](img/f83b09787c2af946c2cdcf84e77e1d66_74.png)

This possibility for you， let me show you something totally cool。



![](img/f83b09787c2af946c2cdcf84e77e1d66_76.png)

Yeah， totally cool if you're a nerd。

![](img/f83b09787c2af946c2cdcf84e77e1d66_78.png)

So the idea is there's this program called EnTR Interpose。And if I。呃。If you look at the code。

 it's just calling now for as many bytes as you're passing on the command line argument。

And the normal version doesn't do anything interesting， but if I。

Set an environment variable called load preload。With the name of a。My library， my desk。so file my。

Dynaically linkable now library。Then I will。When I call this function。

 then into our this program at the link， when it's being pulled together。

 it will actually use that library rather than the standardlyc。A。

And what's interesting about this is you can interpose anything as long as it was set up for dynamically link。

So， even the。LS， a command in UniX。You see。Makes a bunch of calls to malan free。嗯。And you can see。

Exactly what calls its man。There， even though I didn't recompile LS， I didn't relink LS。

 what I did is LS is a dynamically linked piece of code that usually sits in。

I'm not sure where usually sits， but it's just a piece of code there that normally gets pulled in。

 dynamically linked with the regular C libraryrarian executed。But in this case， I sort of told it。

 oh， use my own custom library to do it so you can imagine。

If you're trying to track down you're given an executable program that you don't have access to。

 but you want to understand it better， you can use this interposing trick in some pretty clever ways。

Okay。Take care of。

![](img/f83b09787c2af946c2cdcf84e77e1d66_80.png)