# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p12 -12-xv6 Kernel-12_ Linking the Kernel.zh_en -BV11CkSBsEtN_p12-

![](img/9d924c13dc7436ff5882e550a8f85dfe_0.png)

This video is part of a series on the XV6 operating System kernelel。In this video。

 I'm going to talk about the linking of the object files to produce the image file。

I'm going to talk about the file kernelel dot LD。 This is not a C program and not an assembly program。

 Instead， it is a linker script file， which gives commands to the linker to tell how to put things in memory。

So I'm going to start with talking about how memory is used by the kernel。So here is。

A picture of the memory of the kernel code and data。

And the linker will essentially place all the code in memory and figure out where everything is going。

 doesn't actually put it in memory。 It just figures out where in memory it's going。

The linker is normally something that you don't think too much about as a C programmer。

The defaults that are used for the linker will usually work for most user level programs。

 but for building a kernel， we need to be more specific and include some commands。

 and so I'll be talking about the file that gives those commands to the linker。

 and what the linker will do is we'll take all of the data from the object files。And combine it into。

The excutable file。So here in green， I'm showing what comes from the object files from the various parts of the kernel。

 and the linker will figure out where in memory to place all of that material。

 and then it will build the executable file， which contains all of the data to be loaded in memory。

Later， when we get ready to load the kernel and run the kernel， Kimu。

 the emulator that will be that is being used， will read the executable file and put this stuff in memory at the addresses that the linker has chosen。

So remember that when you compile something。A C program。

 It produces assembly code and the assembly code is compiled or sorry， assembled。

 and that produces an object file。Or maybe you just write assembly code like we have in this file entry。

 s， and the asmbler produces object file。An object file for that。

The object trials contain a number of segments， or sometimes I call them sections。

 but each segment will contain a bunch of data that should be placed somewhere together in memory。

 but。The compiler and the asmbler don't really know where in memory that segment will be placed。

So there can be several kinds of segments。 And these are given names。 The dot text is a name。

 The dot read only data， dot R O data is a name， dot data。Dot B， S S。

 these are the different kinds of segments。 And I'm not sure whether you want to call these the names of the segments or sort of generic types of the segments。

 but its doesn't really matter。The dot text segments will contain executable code。

The dot data segments will contain the variables of the program。

 These are the things that will be both read and updated and may have initial values。

We also have read only data， and。That kind of a segment will contain data that is to be initialized。

 but it will never be updated at runtime。 So it's read only。

And we also have something called the BSS segments。Is contained。

Data that is not initialized with any particular value。 Instead。

 it is to be zero filled or initialized with zeros when loaded into memory。

 And so these segments don't need don't have any initializing data so they could be quite small in the object files and the executable files since they don't have the data。

Okay， so。As a result of。Compiling and assembling a bunch of pieces。

 all the files that we've talked about and we'll talk about in future videos。

 we have a bunch of segments。We have a bunch of tech segments， data segments， and so on。

The Lincoln figures out where in memory to place these things。

 and it will place them starting at this location here， which is the two gigabyte boundary。

 and it will put all the text segments together， all the data segments together。

 all the other segments， all the BSS segments together and the read data segments together。

We also have a special segment which we give a specific name to。 This is for the trampoline code。

 and that's called the tramp sec for the trampoline section or segment。

And that has to be placed specially。On the Lier's command line。

Will specify a number of different object files， and the segments will be grouped together。

 All the text segments from each of the object files will be grouped together。

 and they will be placed in order， according to the order of the object files as they are listed on the command line。

The command line to the linker will list。The object file for this entry code。 Remember， willll。

 we'll go into depth on the entry file。 It's an assembly language。File that very short。

 but it's the first thing that gets executed。 Yeah， the object file for entry is listed first。

 So that code will be the very first code， and it contains this file contains a label called underscore entry。

 And it's actually the label of the very first instruction in that file。

 So that text segment will go first。 The linker will place it first。

 And so we will begin execution by jumping to the very first location of the kernel。

 That's the so-called entry point。 and then it will include the text segments from all the other C files。

 There are a bunch of them more than I've shown here。We have this special tramp。Tmpoline segment。

 and it'll place that。 And then it will group all the read only segments together from the different object files。

All the data segments and all the B，S S segments， and it will produce an executable file that has four segments。

 It will It will combine all the text segments into one dot text segment。

All the read only data segments into one segment， all the data segments into one data segment and all the B。

S S segments into one B，SS segment。In the course of placing these things in memory。

Lilinker will figure out the addresses of everything。

 and this will allow it to fill in a lot of material that cannot be filled in until this point。

 For example， when we load a variable in our code with the address or some variable。 Well。

 the address of that variable is not known by the compiler and not known by the simpler and will only be determined at link time。

 and so at that point， the linker will go back and modify the code to insert the exact number。

 And we may store， we may initialize some variables with addresses and the linker will go into the exact location of that variable and and modify or or initialize that data to be the correct address。

Only the linker can do this because only the linker knows where things will actually go in memory。

Okay， now let's look at this。Oh， one other thing I want to mention is。

After the after we finish the linking and begin the emulation and came with the loads this thing into memory。

 And the kernel actually begins executing。 then the kernel will。😊，See where the pages are。

 and it will mark those pages as either。Executable or not， and either writeable or not。 and readable。

 So the kernel， once it's executing， will build a page table that will describe these these。

 the data that's in memory， and it will mark everything that was in the text segment as executable。

 and it will mark everything else as readrite。The linker will also determine the values for a couple of important variables and in particular Etext is the boundary at the end of the code and the beginning of the data portion of the kernel。

 and end is the point at the very end of the data section。

So it will set these variables and will also set this variable underscore trampoline。

That can only be done by the linker。 And once the linker figures out where in memory things will be placed。

 it will place， it will define those values， and it will fill in those values in the code wherever those symbols are used。

These little tick marks here indicate page boundaries， by the way。

 and we'll see how the script file for the linker causes things to be aligned properly。

 So now let's take a look at this file， kernelonel do LD。

 This is written in a sort of a special language that the linker will understand。 And as I said。

 most times when you use the linker， you don't have a script file and the defaults or the default commands will be used and you don't have to worry about this stuff。

But this is essentially a sequence of commands， and it's saying that produce an output executable file for the risk5 architecture that's what we're dealing with here。

 And this symbol named underscore entry， which is defined by an assembly code statement in the entry dot S file。

 that will be the entry point for the program。 okay and then it's saying in the output file。

 create several sections， create a text segment， a read only data segment。

 a data segment and a BSS segment。 So it's saying create the text segment。

 read only data and BSS segments。Okay， so。Dot indicates the current location or the an address。

 And so what this is saying is begin at this fixed location。 So it's telling the link or two。

 put things at at this memory location here。 So start there and work up in memory。

And now it says for the text segment， in order to create that， grab。

All of the dot text segments and anything that begins with this is a wild card here that the asterisktra secures a wild card。

 grab all of the segments from all the files and throw them in to this segment that we're creating。

 This star here is saying this file namess。 It's think from all the object files that we're on the command line。

 grab those segments。 Okay， so it does。 It grabs them and puts and puts them into the text segment。

 This is the text segment that we're creating。Here。

And these are the text segments that are coming from all the files here。

Normally they're just called dot text， but this wall cardt picks up anything else that we have。

These are done in order as they are specified on the command line。

 so the first object file on the command line will be the one for entry。

The entry dot O entry dot O for the entry。Not S file。 And that will go first。

 and that will put our entry right at the very beginning。Next， we say dot equals a line。

 And this is basically forcing it to move up to the next page boundary。

 So that's the linker will then insert some。Unused memory here up to the next page boundary。

 And that gets us up to here。And then it says， define this label。

 underscore trampoline as that as the new current location， so that。

tells the linker that we want to name a symbol， underscore tramline and we want its value to be that address right there。

And then we're saying include the segment that's called tramp sec。Trmp section。

 the trampoline section from whatever file it comes from。 And so any and all segments with this name。

 and there will only be one is then placed here。And then we have another line。

 So we skip up to the next page boundary。 S up to the next page boundary。

 And that's what I'm showing here。 And then it says。诶。

Assert that the current location minus trampoline is exactly one page。 And if it's not。

 we print out an error message that the trampoline code was larger than one page。 It won't be。

 But we checked that right here by doing the subtraction。 And then finally。

 we define this symbol E text。At the current location。So that's what we're doing here。

 Now we build the read only data segment。 And it's， we do alignment。 This is 16 by alignment。

 We see that occurring in several places。 These segments should be aligned on。Qudword boundaries。

16 by or 128 bit boundaries。And we're saying， pick up any， any segments that begin with。

Dot S read only data or dot R O data and some variations。

Then that creates the read only data segment。 Then we have the data segment。 And again。

 it says do some alignment。 We're not doing page alignment。

 We're just doing a 16 by alignment and pick up everything from。 remember。

 this is a wildcard for the file and it's picking up all the dot data segments。

 and we have some variations on the different names。 I don't want to go into details。

 I'm going try to even understand all these details。BSS， again， we have a similar thing going on。

 we're picking up all the segments or the sections that have names that start with do BSS。

And finally， we are defining a name end。 So here we're defining the name end wherever we end。

 So we might not be on a page boundary because there was no alignment here for a page alignment。

 So we just mark end right there。 oops， we mark end right there。😊。

So I'm indicating that it may not be on a page boundary。

And that then allows the linker to produce the executable file that we want。

 and it will be loaded into memory at the right when if it's loaded into memory at this address。

 then the code will work properly， So that's it for the linker， if you didn't understand all that。

 don't worry about it， I think you can understand the kernel in isolation from understanding this linker script file。

Okay， I will see you in the next video。

![](img/9d924c13dc7436ff5882e550a8f85dfe_2.png)