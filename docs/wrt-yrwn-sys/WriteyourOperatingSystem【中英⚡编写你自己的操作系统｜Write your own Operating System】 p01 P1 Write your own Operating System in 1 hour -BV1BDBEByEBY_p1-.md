# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p01 P1 Write your own Operating System in 1 hour -BV1BDBEByEBY_p1-

Hello， my name is Victor Engerman and in this video I'm going to show you how to write your own operating system。

But first things first， I want to thank to websites or Sdef。org and low level EU。



![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_1.png)

These are two websites， which。Talk about writing your own operating system。

 and I have learned a lot there。嗯。And okay， before we start， I。I should tell you what my specs are。

 so。

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_3.png)

If you want to follow what I'm doing， it's probably the best idea to also use Linux Linux Mint 17。呃。

And I guess the rest trips probably work out no matter what process are you're using。嗯。Okay。

 so the software you will need for this is you will need the new compiler collection C plus plus compiler G++。

The Gnu assemblymbler， A S。And a package called Li C 6 deaf I 386。



![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_5.png)

So from what I've just said， you probably already deduced that I'm going to write this operating system in C++。

And， well， many people prefer to write the operating systems in C。And okay， C is fast， you know。

 and that's an advantage。 But on the other hand， I prefer object oriented programming。

So I think really， procedural programming is a thing of the past。Now， granted。

 you can do quasi object oriented programming in C。 But to me。

 it just feels unnatural and kind of hackckish and。I don't think C is really designed for it。Yeah。

 I I really think C++ is the best compromise between the performance of on the one side and modern modern programming paradigms on the other hand。

So before we start， we should talk about what happens when you start your computer。So。Let's see。

So here's your main board。And on your main board， you have。Your bias。嗯。

And attached to your main board， you have your hard drive。Okay， this looks more like an iPod。嗯。Okay。

 and also on your main board， you have your CPU。O。And I guess you already know a little bit of asemmbler because I don't think it's a good idea to start writing an operating system if you don't know any assemler at all。

嗯。That if you know a little bit Asmb， you know that a CPU has several registers。嗯。

And we'll be dealing with the Regs， A X， B， X。嗯。As a stack pointer， and。

And it also has an instruction point up。O。No。When you start your computer。Then the main board will。

Do the following， it will take the data from the bio。It contains， really。Basically。

 something like as code。 So it's your firmware。And it copies the content from the bio to the Ram。

Okay， here's he run。Okay， so it copies the firmware from the bios to the re。 Now you have it here。

Here's the feware。And then it tells the processor， okay。

 please put your instruction pointer into this。Po。And this now means that the CPU will read the instruction that is there and execute it。

 Okay， so。Basically， what this does is the CPU will now execute the firmware。

The firmware will then tell the CPU Ho CPU。Please talk to the hard drive。

And it will talk to the hard drive relatively low level。 I don't think its。Nose。

Partition tables or file systems。 So it will just look in the raw data。 You know， the first。

 I don't know。 maybe two MBgaby of the。Hard drive is the boot sector or master boot record。And。Well。

 this。Will then be loaded also into the RAm。This is a boot loader。

In this tutorial we will be using the bootloader Gr。Many people say。

 if you write your own operating system， you also have to write your own boot loader and。

I kind of agree with that， but trust me， you are not at the point where you can。

 where you are able to write your own boot loader。 Okay。

 so we'll just stick with with the grab boot loader for now。嗯。So， yeah。

 this is loaded from the masterbook record into the Ram。

 And then the formula will just basically proceed and tell the CPU to jump into。This boot load， okay。

So now the CPUU will execute the boot loader。The boot loader is a bit more sophisticated。

 It knows about partition tables， and。File systems so it can deal with directory structures。

So it will be able to go to the second partition。嗯。And look into the directory slash wood， slash gr。

Slash。Grab dot CfG， so it will load this file。And then it will read this file。

 and it will contain some menu entries， which。Contain information about yeah which operating system is where on the hard drive。

 Okay， so if you check this file out， yeah， you will find several entries， for example。

 when when we look into mine grab CG later， you will see entries for Windows and for Linux Mint。

Other things。嗯。Okay， so。Now， the boot loader will just。

Print this list of operating systems on your screen。AndNow with with your arrow keys。

 you can select one of these operating systems。Let's say you selected this one。Then Gr will say。

 okay， this operating system， it's the one on the maybe on the third partition here。

 So and now I need to load slash boot。Slash。啊。Colonner dot bin， for example。

So it will load this file。Might be here。So， then it。And it will copy this kernel bin。Also。

 to the Ram。Now the kernel bin is loaded in the RA。And then it will tell the CPU。To Trump。

Into the current。Okay， and this is a point where we come。Into play。 Okay。

 so this is the point at which our code will start to be executed。This is a point。

Where our entry point will be calleded。Of our current。Okay。We have a big problem at this point。

The boot laer。Will not set this register as the stack pointer。

And this is a big problem because C++ programs expect the standpoint to be set before they start running。

 okay。嗯。So what we will have to do now is。We have to write two different files， one asmbler file。

 which we will call load。Dot S。And this will basically just set the stack point and then jump into。

NowThe other file， which is kernel dot CPP。Okay。So。Yeah。

The loader dot S file will be compiled using the new Asmbler A S。

 and then we'll get a file called loader。Dot O。And the kernel CPP will be compiled with 3 plus plus。

And this will create a fire call kernel。Not our。So the problem now is we have two different object files from two different programming languages。

And now they need to be combined into one。One common file， okay。And yeah， there to do this。

 we will use a program called LD。Which is a linker。

And this will combine these two files and give us the file kernel。Dot bin。Okay。

 and this is a file that we will then just put into。The boot directory。

 and well have to write an entry in the G CG。嗯。So that the。So that。Boootloader can find it。Okay。

So one thing I should mention。When you start your group computer， even， I mean， it's 2016 now， Okay。

64 bit processor are the standard nowadays。But even today， when you start your computers。

 the CPU will start out in a 32 B compatibility mode。 Okay， so。At the start of the。Of the kernel。

 we are in a32 bit mode and。To be honest， I don't actually even know how to switch to 64 bit mode。

And so we'll just make all this stuff 32 B。 So it will be compatible to the mode that the CPU is in at the startup of the program。

 okay。Okay， so let's start。So here's an empty directory。And I will create th filess。

Loader dot S as I've told you。Well。KnerCP。Liner dot L。And a make fire。Okay。

 I will edit this in a program called Kate。Okay， so。I assume you know a little bit about make files。

 and I'm not going to teach you a lot about it。 I'll just put。Some usual stuff here。

 like to create a dot O file from a。Dot CPP file。What do we do Well we call 3 plus plus。With some。呃。

With some parameters， which will be taken from a variable。嗯。And I will well further 32 bit mode。

This will be one of the parameters。The output should be the target file。😔。

And we want to compile the input file。Exexes。Okay。Now， if we want to create a dot O file from。呃。

ButS file。How do we do that where we use the asmbler A S。With。ASpars。嗯。

The output file is the target file。And we will be using the input file as input file。Okay。

And this variable as。Proms。We set just to。32。But。O。Now，In the end， it's we want to create the file。

My kernelel。That pin。And this will depend on。The linker dot LD file and also the object files。Okay。

 and the object files。Not just。Loer dot O， and。Colonel do Paul。Okay。Okay。

 how do we create that using L。With。AD。Prameters。As input file， we will use the linker LD， so。

The first of the dependent files。He will create the target file。And as inputs。

 we will use all the object cloud。O。And in the end， when the micro bin is completed， then we will。

 we want to be able to install it。So this depends on。My colonel。Thatt pin。And it will just。苏州食频音。😔。

So kind of been to。Slash boot。My可 with bit。Okay， so。W wait。

 I've forgotten to declare the variable LED parameters。O。

So this isn't all we have to do in the make file， but。This should be sufficient for now。

So let's look into the kernel CPP。Yeah， we will just have some。长春。will。

 we can call it whatever we want。 I will call it kernelel Ma。嗯。And let's say， it's supposed to。

Just print out a message。O。So at the end of this function。

 we don't want this program to stop in a way。 I mean， what does it mean that a kernel stops。

 it doesn't really even make sense to talk about it。嗯。So at the end， we will just。

Go into an infinite loop， okay。So。This is supposed to be our。What our kernel does。嗯。Now。

 let's look at the load S。So as I've told you， there is a problem that the stack pointer isn't set to anything at the start of the。

When the boot loader is done。 So what we'll have to is。Action dot text， you know。

 this is this should be familiar when you have when you are。嗯。When you know some as。Next time。可能。😔。

Main。So this is so here I tell the assmbbller that there is going to be something called kernel Ma。

So it assess function and。We want to be able to jump into that。 So we are telling。The aser here。

 if we want to call Colonel Maine， just assume it will be there， the linker will take care of it。

Okay， so。跟。We meet。Well， this is the program entry point。Nothing spectacular。 Also。

 if you know a little bit of assem。And what we will do now is the first thing we will do is we will just set the stack pointer。

嗯。And what do we set it to well to something， to some pointer for some stack。Okay， so where is that。

This isn't declared yet。And we will declare that at the end of the file。U。In its own section。

 which we will call B， S S。嗯。And yeah， here， this is just a position fund for the kernel。Okay。

So this is the pointer where。We set the EP register to。 Okay， so now we have another problem。

So let's say this is a kernel， okay？あ。Okay， so here's maybe， maybe here's。

The instructions that sets the EP。 But where does it set it， Well， it would set it relatively close。

Close by。 And that would be a problem because， well， the stack is going to the left。

 So when we push just a few things there， we will be overwriting stuff， and it will be。

Not a good idea。 Okay， so what we will do now is we will just put some empty space in between。

And then have this kernel stack point up。Behind this space， okay。

So so that we reset set the kernels next point up。Such that there's。

We will just use two megabytes of space in between， okay。So this can be done using dot。Space。嗯。

Two times。1024 times 1024。So this is two makeite。O。So now the stack pointer is set to something same。

嗯。And as I've told you at the end of the kernel main。

 we will be going into an infinite loop so when we call so when we jump into the kernel main。嗯。

It's not supposed to ever come out of that again， but just to make sure。We'll just have some。

Another infinite loop after that， so。Okay， so this is another infinite loop。



![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_7.png)

O。No。The next big problem we have is。That the boot loader will not recognize this as a kernel。

 because a boot loader。嗯。

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_9.png)

when the bootloader looks at this file， the kernel bin。

 it will look for a so calledled magic number in that file， and if it's not there。

 it will not assume that it will not believe that this is actually the kernel。

So what we have to do now is we need to put this magic number in there。Okay。So。Yeah。So。

 this metric number is。The X adjust the number。0 x，1。BAD。B0，02。

 So we need to put that into this file so that the boot loader will accept it。As a con。Okay。

 so let's do that。First， I will just store this in a compiler variable。This will not。Actually。

 be put in the。Resulting that O file。嗯。Also， we need to set some flags。

 This is all also just for the boot loader。And we also need to set a check sum。

To minus the metric number。Plus， flex。Okay。And now we have to actually put these into the dot O file。

 So we do this by。Using a section。Section multi board。And it contains。Just these variables。Okay。Okay。

 so this should actually work already。嗯。But there's another thing。嗯。When the boot loader has decided。

 okay， this is a kernel， I will load it， and I want to jump in this。嗯。It actually。

 before it does that， it actually stores some informations on。Somewhere in the Ramm。So。At some point。

 there is going to be this so called multibo structure。

So multibo structure containing some information， for example。

 the size of your RamM would be stored in there。 and I think it's not a bad idea to really use it。So。

And， I mean， why not have that。 If the boot loader gives a set， why not。Take it。So。

What does a boot loader do， Well it creates a structure。And then it stores a pointer to that。

In the Ax register。O。So， and also， it copies the metric number into the BX register。Okay。

 this is also what it does。So。I think it's not bad idea to。To just take these informations。

 as I said， why not？So。So just before we call the current N， we just。不ush。嗯。A X and。不ush。B x。And now。

 we。In in the kernel main， we have to to accept this information， you know so。

You will you will find online files like multiboot dot H from the Gnu project。嗯。

You can use that to store。To accept this multi good structure for now。

 I will just use a void pointer。So that the compiler won't bother us。And it。Also， gives us。

Sosymmetric number。As un'mign。Inte drop。Okay，Actually。

 I don't know why we should be interested in having the magic number again。

 but maybe for some error checking or whatever， let's just have it there， it doesn't hurt us。So。

So this load dot S should already work。

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_11.png)

Let's try this out。

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_13.png)

Yes， there is the loader dot O。Wonderful。O。And we can also try to compile the kernel。

 but it won't work。

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_15.png)

But why doesn't it work？然ello。Well， it says print F was not declared。



![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_17.png)

Okay， so this should not surprise you because I didn't include standard I O or whatever。 you know。

 the the usual。The usual files for， for the。Writing of text to the screen。Now， the problem was that。

Is。We are at this point， we are outside of an operating system， know。The regular print F。

That you can include with standard I O or whatever。It's inside dynamic library。

So usually when you write a program， you have your operating system around it like say Linux。

And here's your program inside of that environment。 Here's your program。And when you call print F。嗯。

Well， when， when you start your program Linux， will see， okay， your program is using stuff from。

L print F stuff from the G Lips C library。So standard library for seed programs。

So when you start your program inside Linux， when Linux will use the dynamic linking to。

To load Gleps C and connect your program to Gleps C。Now， problem  one。

 we don't have Glib C in for our operating system yet。

 And we also don't have an operating system around us， which connects this for us。 So we have no。

Dynamic linking。 We have no libraries。 We actually， we have nothing。 We have。 we don't have。

dynamicynamic memory management。 so we cannot use meoc and free。

 and we have nothing to to write something on the screen。 Nothing， absolutely nothing is there。 Okay。

 everything we want to do， we have to write ourselves， okay。So。

What we have to do now is we have to write our own print F。O。And okay。

 this is probably if you want to write a complete print， as this will be madness， probably。嗯。

But we will have a small， simpler。Version of print S。嗯。And yeah， how do we write it。Basically。

 you just need to know how this works。So。If this is your re。And this is your screen。

There is a specific memory location。And it's the location with the hexadadeimmal address，0 x。B 8，0，0。

0。嗯。And whatever you write here。Will be put on the screen by the。That a graphics card。

 So if you write an A here and a B here。When。The graphics card will write AB here。The question is。

 what is with these bytes in between。Well， they are for color information。嗯。Yeah要有。Despiteite has。

For high bids and for low bids and。They are for the foreground and background color of the character。

 okay， but。We will not be using this at this point。 So we will just use black and white text。 Okay。

 a good thing， though， is that。On your program startup， these。

These bits in between already have same values in them。

 so you don't have to set this color explicitly just to have white text on black background okay so this combination black background white text is already in there from the beginning。

 we just have to to make sure that we don't overwrite that okay。So。How do we do that？😔，So。

 we will have。A pointer to this。 we would store a pointer to this memory location un signedigned。

Short。Penter。Okay。And now we will just have to copy the string to this location， okay？Okay。

 so this would already work， but。What we are doing now is I've declared this as an array of。

Un Im short。 So of2 by。At once， so。These two bytes are grouped together。

 these two bytes are grouped together and so on。 So this is element0，1，2， and so on。So。

If I do it like this， there's the problem that if I set it like this， I'm overwriting this highb。

So I need to stop doing that。How do I do that？ Well。

 I'll just copy the high that has been there before。Video memory eye。But only the high by it。

And combine that with those trigger。Okay。I think this。Should work now。



![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_19.png)

So， let's see。

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_21.png)

I。Stake。

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_23.png)

Okay， will you get a normal warning when you convert strings to chart pointers。

We will just ignore that。

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_25.png)

But他。Yeah， we have another problem。So。As I've told you。

 we are not inside a Linux environment where there is a GlipC library。嗯。

And a lot of other things that Linux would deal with for us， like， for example。

 exception handling and。Dynamic memory， dynamic memory management and exception handling and stuff。

 which was done by Linux。And yeah， the compiler would usually assume where there is an operating system。

 I can just do this and that。嗯。But if we try to run this outside of an operating system。

 it just will not work。 So what we have to do is we need to tell the compiler。

 Don't assume that there is a Gy。 Don't assume that there is an object。

 something that deals with exceptions and。That gives that gives you an answer to the interrupt for。

For dynamic memory management and stuff。

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_27.png)

So， we do that。In the make file。So。We just need to give G plus plus additional parameters。嗯。Okay。

 what are the additional parameters？We need F， no。看了啊。Use。C X， A。At。

Exit this has to do with memory management。No STD lit。So we don't have a giy。嗯。If， no。Built in。

Have no runtime type identification。Yeah。no。Exceptions。And another one， F no。leaing。Under。

So this has to do with the naming of the。呃。Of the sections on in， in the resulting dot O file。

If we didn't have that， then。The loader would not be able to， to call kernel main。

 It would have to be underscore kernel main， but that's。Just a minor nothing。So。Okay。So。



![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_29.png)

Then let's look at the linker。

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_31.png)

How do we link this now？😔，I mean， if we use if we had different files from the same programming language。

 we could tell the compiler to deal with that for us。

 but when we have files from different compilers then we can do that and we have to take care of it ourselves。

And I'll admit， I'm not an expert with dealing with the linker。 I usually compile stuff。

All stuff within one language。 So I'm usually， I usually don't have that problem。 but here we。

We have that。嗯。Okay， here we tell the the linker that。

This position of the loader dot S is the entry point of the resulting bin file。

The output architecture is going to be I 3，86， column on I 3。6。And the output format is going to be。

F 32。5，3，86。Okay， what we do now is we need to。To select the sections from the different dot O files okay。

So。So we collect the sections from the different O files and combine them to new sections。

And I'm not 100% sure what this actually does。嗯。This is just from。From a tutorial that I've read。

Okay， we create a new text section。Which contains。Where the text sections of the other files。So。

 star。Point text。し？Okay。Then， it will also。I mean， before the text section。

 it will contain this multiboot section here。So。Star红。Mti boards。And I'm not。Really sure what。

But this section is for， I guess it's。Probably comes from C plus plus。Okay。

 so this is a new text section。Then we put a new data section， which contains。With it。

I think this is。For the construction of the。Of the global object。 You know。

 if you have global variables， this。Well make sure they are that constructors are called。

And we come do that。😔，Okay， and it will also contain the data。Sts。From the。That all files。Okay。

 so the last thing we okay， it's not。 not the last thing。We also need to put the stack。

Here's this section， this B S S section。Into t。Okay， and now if we linked these files with this。

The link would。嗯。Would not be happy because at the end of the when it's finished。

 it would have some symbols left over， which haven't been put in the new。Binary files。

 So we need to tell it that it's okay that these symbols are left， so。So for example。嗯。Here。

 we have the。Comments。So comments can be can be removed。 This is what we tell it here。

 If we have a comment， it's okay if it's removed。Okay， I think this should work now。 Let's see。



![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_33.png)

嗯。

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_35.png)

Line and。Cent X L。啊。There's the code I'm missing here。



![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_37.png)

And also， here。

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_39.png)

Okay， one small problem we have。I。It tells us the kernel main was not found。

The loader is trying to jump into kernel main， right？And there is this kernel main here。

 but the problem is that G plus+ has a different naming convention。

 So when G plus+ writes this into the dot O file， it will change the name a little。

And we just have to。To tell it not to do that。

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_41.png)

Like this。

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_43.png)

Okay， so now the kernel is recompiled。There's this warning message again。

 and now the linking has worked。And here's your kernel bin。Okay， so let's install this。

My bin to my bin okay。

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_45.png)

So make install。No。And there's this micro bin in the boot folder。 And now we just have to。

To enter it in the Gr C FG， okay。Yeah。Okay， so this is a lot of stuff here。嗯。Okay， so let's。

En to this。Okay， so this is really easy。 We just have to say menu。Entry。Give it a name， let's say。嗯。

妈啊。Operating system。And in here， we just have to。Put。Multibo。Slash。W。My kernelel。P。And。Booot。So。Safe。



![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_47.png)

Quit。And this should be everything we have to do。 So I'm going to reboot the computer now。



![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_49.png)

啊。

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_51.png)

Okay， you see there's the in in the menu。My operating system。

And there you see the operating system does what it is supposed to do。So there you have it。

 I hope you'll have funes。 I mean it feels really great to have your own operating system doesn't it And yeah。

 tune next time in the next video， I will show you how to install your operating system in a virtual machine because you are not going to reboot your computer every time you have made a little change on your operating system So you really want to have this in an virtual machine。

 So see you next time。