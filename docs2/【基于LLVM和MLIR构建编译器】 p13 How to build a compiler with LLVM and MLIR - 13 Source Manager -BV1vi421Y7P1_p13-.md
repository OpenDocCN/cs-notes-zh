# 【基于LLVM和MLIR构建编译器】 p13 How to build a compiler with LLVM and MLIR - 13 Source Manager -BV1vi421Y7P1_p13-

Hey folks， welcome back to the channel。I hope you' are having a fantastic time wherever you are。

 and in today's episode we're going to have a look at our source manager implementation。

Let me start this episode by answering one of the。Question that I get often。

People usually ask me about my environment， like what tools do I use and stuff like that？

So I have an editor which is an Emax based editor。I'm working on it for about 11 or 12 years now and it went through lots of iterations。

 I'm working on the V3 at the moment this is what you see both my editor and my window manager both of them are practically my editor so I boot into my editor directly and as for。

What I use for the presentation， I guess， I use org mode， which is like a imageax library。

It's like amazing。And。So I was thinking of creating another video series in parallel to this one just about that editor and the work I'm doing in that area。

 it's actually really nice， I love it， I use it for a long time now and it might be a good idea to share my experience with other people as well。

So hopefully I'm going to start that one soon as well。

 it's going to be all about E and how to create an editor or。Set up the environment， how do they。

I don't know， created different API， different interfaces for。

Different tasks that I usually do all my daily routines and stuff like that。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_1.png)

I'm like that reduce is。Like I don't have any specific plan for that one yet。

 but it's going to happen soon， hopefully。These days， I'm pretty much busy with the third board。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_3.png)

Speaking of serene。Updates as usual。Im still working on the JIT and。To be honest，'s。Or。

More complicated than I expected。 And obviously， it's going to take a while to finish it up。

 I tried different approaches to create any J IC。And they went well， but。

Since serene is not like a aesthetic static language。

It's not easy to actually finish up finish up the JI as soon as possible。 I have to eat like。

Ittererate with some ideas， create some POC code and kind of evaluate the。

Different approaches I have， blah， blah， blah， but。

Long is story short I'm still working on it and I'm confident that I。Sorry。

I'm confident that this time I'm on track， but it's going to take a while to finish it up but luckily after today's episode we like we end up with we're going to end up with the JIT anyway so next episode we're going to have a look at the JIT fundamentals and。

而且啊。😔，Go over some of the concepts that we need to know before we jump to the actual implementation。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_5.png)

That's what I'm doing these days， but as for today's episode。呃。First of all， I forgot lucky。

In the previous episode， we talked about the code generation and how to generate the target code。

I forgot to actually show you how to do it like I showed you the code， but I didn't show you like。

An example of how we actually generate the target code。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_7.png)

Let's do that right now and。Let's see。 what's going。 Okay， so I actually did it already。嗯。

So if you remember， we talked about the serenency in the previous episode。

We have some like the certain see that CPP file is our entry point to the compiler and as I mentioned we're not going to keep it forever。

 it's going to change in the future， in the near future。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_9.png)

So if like right here， what I've done is that after I compiled the project。

 just I just ran CC and passed two dashL parameters to kind of。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_11.png)

Imply that I want the home directory and the current directory to be in my load path。Then， I。

Like use the name of space。As my entry point， like I'm asking Ser to compile this name and space for me。

And then I specified the build directory to be the current directory。

 and finally I'm asking the compiler to emit some target code for me。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_13.png)

Besides beside target， I can actually use object as well， if I want only the object file。

 I can use object otherwise when I use target it means like give me the binary。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_15.png)

And as you can see。Like in the。Output like I have two new files one called output and output O this is the object file and like we talked about it in the previous episode when we link the object files together。

 we're going to get the binary executable binary。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_17.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_18.png)

嗯。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_20.png)

Again， if I want to change the name， I provide the dash oh parameter to say， okay。

 here's the output name I want。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_22.png)

It creates the output for me as well。But。The reason I have all this is that because it's the take I'm second take on this episode I already recorded it once but。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_24.png)

There was some wrong information I had to rerecor it。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_26.png)

So anyway， if we look at the object file to see what symbols does it contain。

 we see that there's a main and main one symbol and if we look at the look at the executable file。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_28.png)

Again， we see some other symbols that is created by our link here。

 we don't care about them right now， but what's important is main one and main function。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_30.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_31.png)

So we ended up with like executable file with the functions that we actually need。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_33.png)

So。What was it hello yeah this is the ser code that we compiled to the executable binary as you can see we have two functions the sorry main and main one and we had them in the。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_35.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_36.png)

Symbols as well since we since our language， it doesn't have any aspect yet and we're not kind of。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_38.png)

We don't want to have that and think about that at this stage。This is the best thing we can get。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_40.png)

like our executable doesn't do anything at all， but the fact that we can actually generate target code。

 legit target code is good enough for us， remember for the first stage of the compiler。

 we just want the wiring， we want all the pieces in place with the most basic functionality possible and we want them to work together to do something。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_42.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_43.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_44.png)

And later on we're going to build upon that and enhance any every component on its own。

 so thats one more thing I wanted to mention， but was it？Yeah， I can't remember。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_46.png)

So let's go back to the slides。That was the only thing that I forgot to do from the previous episode。

 so about today's episode， the main topic。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_48.png)

So source manager is a concept that is not really related to LLVM。

 it's something related to the front end code， so every front end might have like might manage the source code。

Differently。But if you look at the little VMs examples and like documents。

 you get to see the source manager quite a lot。My fear said like。

At first I didn't have any source manager， I used to just load the file， like read the file manually。

Was stored somewhere in the memory， and。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_50.png)

Do some stuff on it。But little by little， I was like， okay。

 I need to use an entity to manage my source code。All the sources。

 not just like sources on the file system， and that is what a source manager do， right？So。

's a source manager by definition， manages all the source codes and owns everything related to the source files on the disk。

 it doesn't have to be on the disk， you can like I don't know， you can read it from like network。

 you can extract it from an archive or whatever right。

 but the most basic and the most common use case is to read a file on the file system and do something。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_52.png)

And that's what we're going to do again， most basic functionality。We have this entity。

 it owns the source code and。Like we have to use it for whatever we need on source code level on source file level。

 like including different files。Associating name and spaces with five names and stuff like that or like。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_54.png)

Actually， in the。Example that I showed you just showed you right we asked the compiler to compile this name and space for us。

 we didn't say where to find it right so this is actually one of the functionalities that we need to implement in our source manager。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_56.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_57.png)

That being said， I trust to you。 So Eium comes with。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_59.png)

Buildu in source manager。 I tried to use it。But unfortunately the current implementation of the LLVM source manager is heavily tied to K compiler。

 so I'm going to show you the official source manager first by official I mean like the LLVN version first and then I'm going to show you our own version。

So。WellActually， let's， let me just show you the。Coold。Include a support personal。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_61.png)

So this is the actual source manager that you can find on the LM。Stthory。

It's quite simple like it does some basic stuff for。To begin with it it has a victory of buffers。

That each buffer obviously represents a file on the file system。And。

All the functionalities that the source manager actually provides is going to be helper functions around the same idea like we have a vector of buffer pairs and we have some help pairs that do some stuff to that vector。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_63.png)

呃。To begin with， there's a there's a kind of。I don't know what to call it actually like a Lium source manager has this idea。

 it's not generic enough， but it it led you to customize some of this stuff， right。

 I wish it would have been like if the source manager was more generic， I would have used it。

But it's not that generic， it has some it led you to customize some of the aspects， but in general。

 it's not one of those aspects is the diagnostic handle so。

The front end should have its own diagnostic engine， right。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_65.png)

When something happened， something bad happens like。Ral error or like a panic or something。

 or even like normal errors that we need to show to user， we're going to use that diagnostic engine。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_67.png)

I'm going to show it to you in the future our own version is not complete yet， it's just there to。

A as a proof of concept code， but it's not complete at all。Right now， as you can see here。

 we can pass like a function pointer as a diagnostic handler to the source manager and ask like to handle any failure。

It should it should be a function that gets like SM diagnostic and a pointer to a thing called context。

 like an opaque pointer。嗯。Basically， whenever something bad happens in the source manager and source manager needs to raise an error。

 it calls to this hand。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_69.png)

There's a built in structure called the SRC buffer， which is quite simple。

 it's just a pointer to a memory buffer and some functions to work with it。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_71.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_72.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_73.png)

Functions like like we hold the。All the like all the end of line positions in our buffer to kind of e the buffer into lines and do some calculations and like some function to get on a specific line based on like a pointer or like a line number or a stuff like that。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_75.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_76.png)

There is something called this one is kind of important。

 this line is called which is like include location。

This is actually one of those features that are kind of cllanangy。

In C and C plus plus as you already know， we have the include Mac preprocessor。

 so we can actually include other files in our current file and this thing in here hold the location SMM location is like a location type in LLVM。

 it's like a single。Single location。 No， I can't remember what what is S M stands for。 Oh。

 source manager。 Yeah， source manager location。 So it just points to a character in our buffer and it like we a source manager uses include location to remember that。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_78.png)

Like the current buffer is included in。Like what like where， basically， right， So when。

We include a file into our current file。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_80.png)

Kleline would use the source manager to。Figure out where that file is and load it into memory into that buffer and then use the include location to point to the actual location in the original file where this file got included。

嗯。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_82.png)

One other thing is the actual vector that I was talking about is here。

 so it's just a vector of SRC buffers and SRC buffer by itself is just like a unique pointer to a memory buffer。

 no nothing like e thresholdial。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_84.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_85.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_86.png)

And some other metadata that source manager needs to operate like include directories again。

 like a C plus C and C+ plus C concept， like where to look for header files and stuff like that。

 or not header files only like for include directories。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_88.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_89.png)

嗯。Like some setters and get here nothing really special。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_91.png)

And the。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_93.png)

Yep， and some functions to actually deal with any warning。

 any error or basically work with the diagnostic handle。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_95.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_96.png)

This is the actual LLVM implementation。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_98.png)

It's really like。One of the actual。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_100.png)

Problems that I had with the LVsource manager is that。It designed for Kang。

 and it designed with C and C++ in mind。I looked into Kang apparently it has its own source manager。

 but when I talked to LLVM folks and LLVM developers， they told me that the KLangs version is old。

 they want to use LLVMs version， that's why the source manager is like this。

I actually suggested that on the meetinging basis I started a discussion around。

First manager to kind of make it more generic， it's not generic enough。

 so I can't customize it the way I wanted to use it in my front end。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_102.png)

But in my understanding。The stores manager in LLVM is supposed to be internal， it's not a public API。

 but we can see it in like many tutorials and examples。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_104.png)

And that's why I had to actually copy paste the code and I remove the pieces that I don't want add the stuff that I need to for our own front end and I ended up with our own version of the source manager that I'm going to show you。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_106.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_107.png)

Just really quick， I forgot to tell you about something。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_109.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_110.png)

So。There's some other classes here like SM fixit and SM diagnostics diagnostic。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_112.png)

The fix it is kind of like a data structure that holds hints for any possible issue in the source code。

 like when the source manager passes the file， there might be some issues that we can actually hint the user to fix it。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_114.png)

We use this data structure to provide hints to the user to fix difference in tax issues。

 and SM diagnostic or source measure diagnostic is just a data structure to report back diagnostics to the handleer。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_116.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_117.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_118.png)

If we take a look at our own source manager。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_120.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_121.png)

So this is our own source manager。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_123.png)

It started as a copy of El Gm's source manager， but I had to change it little bit。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_125.png)

the SRC buffer is the same， just few different tweaks like instead of holding an SM location to point to the included location。

 we have something called import location and we use our own location range because like our own location。

 we can easily convert it to any LLVM or MLIR type location， location type。

 sorry and that's easier for us， we're going to we use location range everywhere。

 why not to use it here as well， it's easier to use it。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_127.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_128.png)

And as you can see there's no diagnostic handler anymore because we have our own diagnostic engine。

 we really don't need our source manager to be generic of like it's inside our own compiler we're not going to serve it as like a library for other front ends。

 we're like a leaf node in the tree of different abstraction layers， compiler needs， so。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_130.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_131.png)

Nobody is going to be depends on our source managers。

 that's why we don't need to be generic so I remove the diagnostic handler and we're going to use our engine directly。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_133.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_134.png)

Which is baked into our context I'm going to show you in the future。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_136.png)

Some other stuff that I added is。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_138.png)

啊嗯。Wheres it I added something like a hash mapap called NST。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_140.png)

It's a string map， a string map is like a hash map with a string keys。

 a string keys maps to whatever type you provide at a template。That I use the unsigned type here。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_142.png)

What it does is to map the name of a name of space to the buffer ID。

 we use the buffer ID to locate the buffer in our vector， so for example。

 buffer ID10 is the like first buffer in the vector。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_144.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_145.png)

I added like I changed the include directories like repurpos it to load paths。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_147.png)

And like find file find file in load pass is one of the most important。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_149.png)

Functions in our class。 And then。Another we have a like we have some k and setter it's not important。

 like give me the a reference to the buffer ID bh or get me a reference to a buffer that belongs to name and space Blah。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_151.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_152.png)

Right。And。We have a function which is our kind of the official entrance to our source manager。

 read name and space， it gets us a context and a name it's supposed to be a care。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_154.png)

Ne a space name and finally location for import location。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_156.png)

Let's have a look at the actual implementation。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_158.png)

The source manager。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_160.png)

So。First of all， we have a helper function called convert name aspace2 path， but it does。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_162.png)

Is to actually convert the name and space name to a pass with some rules。

 So the basic rule is that replace any dot in the name and space with underlyingline。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_164.png)

So if we have a name and space， for example， certain dots。User is going to be translated into。3。

Underline。Sorry， and eventually， we're going to attach the。

F also so fixed to it its going to be in the up like this right Nothing especially it just a helper to do that。

 And like we use the internal， not internal， a library in LLVM that is provided to do some like past manipulations like convert this past to a。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_166.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_167.png)

Platform native pass。 So on Linux， it's going to have a slide of like the。

Directory separator would be a slash on like a Windows system。

 it would be a back slash or stuff like that。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_169.png)

嗯。Then we have a find file in the load pass， it actually quite simple。

 it gets two references one to an string for the NS name and then to another string for imported file。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_171.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_172.png)

嗯。It converts the name to a path and then it tries to find like loop over all the paths we have in the load path。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_174.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_175.png)

And try like try to find the file in the load paths in order that provided by the user If you find the file。

 it's going to set the import file to the full path and return otherwise like and read the file。

 put it in the buffer list buffer director and。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_177.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_178.png)

AReturn a reference to it。 Otherwise， it's going to return null pointer。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_180.png)

Sorry， I said。Reference， but we need a pointer here。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_182.png)

It returns a point， actually。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_184.png)

And finally， the most important function， read name and space， gets a context。

 N name and import location。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_186.png)

Try to find the file in the loadpa if there wasn't such file return and error。

 otherwise add the source buffer to our vector， the vector buffer that we had。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_188.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_189.png)

And get the buffer ID。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_191.png)

And then you set the N S table， assign the N S name with the buffer I D。 If the buffer I was 0。

 there's something wrong， actually， I。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_193.png)

I mentioned earlier that the buffer ID is actually referred to the index of each buffer in the vector beside zero。

 zero is a different story for us。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_195.png)

So it should be begin with one。And finally get a pointer to a buffer， pass it to the read function。

 I had to change the read function to actually use the new source manager and memory buffer and everything。

 I'm going to show it to you in a bit， if there wasn't any syntax error if there was return it。

 otherwise create a name ofspace， expand the tree， I have to show you the expand tree。

 expand the name ofspace tree with the ASD that we got from the reader and finally return the reference。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_197.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_198.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_199.png)

No， return a shared pointer to the name and space。U so one thing to mention here is that like I like this is how we return errors in our implementation。

 if you remember from few episodes like，I guess like two to three episodes， previous episodes。

We have a。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_201.png)

Wheres it。We have a type called Re。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_203.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_204.png)

Which we use it quite a lot， it has two different estate， either a success case or an error case。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_206.png)

And。Like here we return a maybe。And maybe Ns， right。

 maybe Ns defined as a result to a name a space pointer， which is a shade pointer to a name of space。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_208.png)

For the success case and for an error case， we return an error3。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_210.png)

If we look at the  error tree，  error  tree is just a vector of  error pointers and  error pointers are just shared pointer to errors。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_212.png)

So。What happens is when we want to return an error。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_214.png)

We need to actually return a vector of error pointers。

 and I created some helper functions around them to。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_216.png)

Make it easier for me to actually handle the entire situation for example。

 make error tree gets like import location in what location this error is happening。

 what type of error it is like this is and finally a reference to the message which we have here。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_218.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_219.png)

I can show you the error stuff， but it does there its own episode。Right now。Right now。

 like it's not really， I didn't do it。Be the best design。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_221.png)

Here no， actually。Yeah， I have a file that I keep like I make errors in it like I have a reason。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_223.png)

To do this， but I'm going to like explain it in a dedicated episode。

 but what I'm going to tell you here is that when you see this file。

 if you look in the source code and you came across this you come across this file。

 don't panic this thing is going to go away and be replaced by a table gen backend so we're going to define our errors in like ODSS style。

 a syntax and I'm going to write a backend for table gen to kind of generate everything from that ODSS style。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_225.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_226.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_227.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_228.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_229.png)

scriptcrip， maybe I don't know what to call it。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_231.png)

Let's go by， let's go back to the main topic， so this is how we actually return errors everywhere in this function。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_233.png)

So as a short summary， what we're doing here is we asked the source manager to find and load the nam space for us。

It go on like it tried to figure out where on the file system that name a space like lives。

 it tried to finds it in the load path by looping over every pass in the load path。

And if it finds that it's going to pass it to the reader and then。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_235.png)

Call a function called expand tree in of the name of space and return a Sha pointer to that name of space this expansion tree is a little bit important。

 so let's have a look at what it is。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_237.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_238.png)

By the way， if you look at the master branch， this exptry。

Is renamed to add three there's a reason for it I'm going to tell you when we talked about when we're going to talk about the JITS stuff。

But right now， expry gets on ESD and ran the semantic analyzer on it。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_240.png)

If everything was alright， expand the current tree that the current Ne space holds with the given。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_242.png)

Not that given with the。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_244.png)

ASD that is resulted from the semantic analyze。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_246.png)

And if you remember when we talked about the name and space stop。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_248.png)

Name is based actually。Have a。What we call it in C loss a member yeah has a member called ASD with the type of with the type ASD。

 which is called tree， this ASD here is a vector of node so。Practically。

 this vector here holds all the nodes that current name ofspace holds。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_250.png)

嗯。Yeah， but let's have a look at the reader next。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_252.png)

色ろろ thisする。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_254.png)

All the changes that that I had to make was on the fact that we need to。あ。

Work with buffer managers as well。 So the read function has two variant right now。

 It can get a a reference to a memory buffer or can get like a string graph。

 like get the string as the input。 So memory buffers on their own we can actually reference them with a string graph as well。

 so we can use a string graph in this。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_256.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_257.png)

Let me rephrase so we can actually。Pass a string reference to a memory buffer。

 So treated as an string as a reference to an string inside a buffer， right。

 That's what the read function， like， that's how I changed the read function。

 And then if I remember correctly， I used like previously， we used to。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_259.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_260.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_261.png)

We used to。Pail in place when we had an issue in like a syntax error anywhere。

 we had to raise an exception， but now we actually return。Errrors like before， right？



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_263.png)

So yeah， as you can see。O no。I messed up something。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_265.png)

So right now。We don't return anything like in we do in master， but not in this branch。

 which is for E 13。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_267.png)

What we do is to actually raise an exception with the diagnostic engine and terminate the execution flow。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_269.png)

This thing is changing the master。But。It's not in the current branch and I'm going to leave it like this for now because there's a reason to change it in the future。

 which I did in master so that's the entire changes that I had to make for。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_271.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_272.png)

The reader to make it kind of。Integrated with the source manager。 And finally。

 on the content context header file， I added the source manager here。 And if we have a look at our。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_274.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_275.png)

s right。Sa in。See。at our7 C file， like the entry to our compiler。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_277.png)

Instead of the previous approach which we had to kind of find the file loaded in read it and use the content。

 pass it to the reader， we just call the readname and space now the function as I showed you so in the context there should be a there's like a source manager object that we can use to work with the file system and file source files。



![](img/eeac6f665f9b88d3ccd50e726b93f9a2_279.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_280.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_281.png)

It's quite simple， return the name ofspace， check whether there's a result or not if there's an error。

 return， like do something with that or otherwise， use the value success value。

 which is a shared pointer to a name ofspace and。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_283.png)

Do the same stuff as before。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_285.png)

So。That's it for today folks source manager is not really complicated if you have a look at the source code you'll find it quite easy。

It it's something that kind of depends on different front ends。Each rather light。

Do some things like it might do it differently， but。I try to stick with what LLVM。

 like with the culture of LLVM。Use the same terminology and everything。And。It does what I need。

 so I'm happy with it。Thanks again， if you like what I'm doing please subscribe to the channel and see you in the next episode。

 have a fantastic time。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_287.png)