# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p18 -18-xv6 Kernel-18_ uart.c and console.c.zh_en -BV11CkSBsEtN_p18-

![](img/9d532f9a7d6978d199dcb694aa7da97b_0.png)

This video is part of a series on the XV6 operatinging System kernelel。In this video。

 I'll talk about the serial input output system， and I will cover the files UA。c and console。c。

Let's begin with an overview of the system。The 165。

50 a chip is something that comes from the early days of computing。

 but the interface that it provides and the protocol that it uses is still in use today。

 And the risk emulator that X V6 runs on uses this particular chip。

 So the kernel is interfacing to something that emulates a 165，50 a chip。

And this is the hardware in this dark box here， and it interfaces with the display and keyboard somehow。

 And to send a character to the display， there is a register。 and you write。

 the kernel code will write to some particular location， a byte。

 and that will ultimately appear on the display。 And likewise， to get a character from the keyboard。

 the kernelel will read from some particular by。 And this is what goes on inside the kernel。

The chip itself may or may not contain some FiO cus to make the communication go a little bit more smoothly。

But these internal fful cues can be ignored。The kernel provides an output queue called the U art transmit buffer and an input Q called the console buffer。

 Each of these cues is protected by its own lock。 So to do output。

 the kernel code we' call a function U art put C， which will add a character to the output 50 Q and to read data from the serial input。

 we call a function console read， which will get characters from the input buffer。

We also have some other pathways here in particular， whenever a character is read from the input。

 it will automatically be echoed by the kernel software and immediately displayed and that echoing will bypass the output buffer in case the output buffer is full or we would。

 you know if it were full， we would have to grab the lock and acquire the lock and that might delay the echoing。

 So this basically it goes to the front of the line。

 shall we say and outputs the character immediately。

So the interface to the whole system basically is in these three functions here。

Print app is used by the kernel to print error messages。

 and those error messages are considered sort of critical。

 and we want those to go to the front of the line too and be output immediately。

 But the console read and console write functions are used by the user mode programs to get data from the input and write data to the output。

 And so those will use the buffering here。So let me start by talking about the output pro。

And here is a picture of it。 It's called the U are transmit buffer。 and it's a PIO buffer。

 It has a limited size。 It's actually 32， not 8， but you get the idea。

 And there are two indexes into this buffer， a read index and a write index。

 So to add to this buffer。 we store a byte there and increment W。

 and to get a character out of this buffer。 We read at the R index and then increment R。

And if there's nothing in the buffer， it's indicated when R and W catch up to each other。

 And so when they're equal， that's an empty buffer situation。Now this is a。Wrap around buffer。

 And so here's the code we actually use to store something into the buffer。

 We use the W and we store something into the buffer using that array。

 but and then we increment after that but we do it modular the size of the buffer and likewise to read something we use the R index incrementing it after we fetch the thing。

 but we take the index modular the size。 So R and W just keep increasing。

 And so we could have a situation like this。 Our buffer here is8 characters long。

 and it stores A B C， D E F。 And so w is continuing to advance here。 but whenever we use W。

 were doing it modo the size of the buffer。 So were really effectively looking at W right here and likewise with the read index and using this technique where W and R just keep incrementing how。

Because we can distinguish a full buffer situation from an empty buffer situation。

So here's what a full buffer situation looks like。 When W exceeds are by exactly the size of the buffer。

 then we have a full condition。 And here the buffer is full of ABC， the E FG H。Okay。

And if we take W modo the size of the buffer it would come back to five。

 but here we can check for a full buffer and you can ask yourself what would happen when these indexes are and W ultimately wrap around。

 know after lots of input and output， they're going to wrap around and you can think about when under what situations this might be safe and might not cause a bug。

But one other thing we need to think about is the fact that this buffer will be accessed by multiple processes and multiple cores。

 So it needs to be protected by a lock。 And it is the name of the lock is the U transmit lock。

And now let's take a look at the read。Buffffer， it's a little bit different。

We have three indexes into this buffer。 So here's the buffer it some。

 some array and called console buffer。 And we've got indexes for read， write and the end， I guess。

 as well as a lock that guards this particular buffer。 And again， it's a5fo buffer。

 So we're reading when we take stuff out of the buffer from the index R。However， when we add stuff。

 we're adding it at the E index。 So we add here， but we also have the capability when we're typing input to hit a control U。

 and that will erase everything that's the last line of input that's in the buffer。

So that's why we have this third index。 So here we've typed in W O RLD。

 but we haven't hit the new line yet。 So if we hit a control U at this point。

 what is going to happen is that E will be backed up okay to this point here。If we get a control。

 sorry， if we get a new line， we'll instead of control U。

 we'll store it here and we'll advance W to this point。

 we'll advance both W and E to this point here。 And so we will have in the buffer between the read index and the right index。

 A number of lines， each one being terminated by a new line character。When we read from the buffer。

 we'll read a whole line and then stop okay， so that's how the three indexes are used。

So now let's look a little bit at the。你。Hardware here I mentioned that the hardware contains a couple of 50qs that are essentially hidden。

 we won't worry too much about these。 And to write a character， we， we write a byte to some location。

 and to read from the device we read a byte from some location。 Well， those locations。

 those are memory mapped location and the way it works is we have this device。

 this U art device being memory mapped into some location。

 some address in the physical memory address space。 and in particular。

 the address is indicated by this constant U art0。 and it happens to be equated to some particular address。

 and at that address， there are several bytes。 and these bytes are considered to be。I owe registers。

 if you will。 And the key register is the one that's at all set 0。

 And if we store into that particular location， that's the transmit hold register。

 we will be sending a by to the output。 And if we read from that same location。

 here I'm saying store into this location at all set 0。

 And here I'm saying load from the location at all set 0。

 That register has a different name The read。Register， read， hold， register。

 and we are getting a bite from the keyboard。So those two are our main registers。

 there are some other registers that we need when we set things up and in particular。

 we want to enable interrupt， so we have to write some special stuff to this register and if we want to use the onship POs。

 we need to write some stuff to that register and we the line control register is used for setting the Bo rate that's the transmission rate up which would be relevant for real hardware。

And we also have another important one is the line status register。 This has two bits。

 that are important to us。 One bit tells us whether there is any input in the read， hold register。

 So we can read this register all we want， But is， are we getting new data or are we getting the previous character over and over。

 So we might want to check this bit here。 And likewise， the。

The the other bit tells us whether the transmit hold register is ready to receive the next output by。

 So if we write to this register prematurely， that by might not actually make it to the output。

 It might might get lost。Next， let's look at the functions that are in the Uart C file。

 and there are five of them that I want to look at。 We'll start with Uar put C sync。

 And this is used to send the character to the hardware output as soon as possible。

 and it's used by print F。To print error messages， we want to print them to the display as quickly as possible。

 bypassing the output Q。 and for echoing the input characters， again。

 we want to bypass the Fial Q here。Next we have you are Puty。This will be called by console， right。

 and it will add a character to the output Q and。In order to do that。

 it will first have to acquire the lock， and it will have to test for the condition of the buffer having some extra space in it。

 so it may wait。But after it does that， after it puts a character in， it will call you art start。

 And what you art start does is handle this link here。 It sends the next character to the hardware。

 If there is a character in the buffer and if the hardware is ready to receive another character。

On the input side， we have UA get C， which is a little function that will read the next byte from the hardware if it is ready and just return it。

 it will not wait instead， if there is no data ready from the keyboard。

 it will just return a minus1 code。And。Finally， we have this UAt interrupt function。

Whenever an input character is available to be fetched from the hardware or whenever the hardware is ready to receive the next output character。

 the hardware will generate an interrupt， and that interrupt will then invoke the U art interrupt function。

 So it's called when the hardware interrupts。And what this function will do is it will retrieve as many input characters from the hardware as are available。

 and for each one of these， it will call console interrupt。

 which is another function passing it one character for each call。

 and it will use that function to add those characters to the buffer。

And it will also call your start to send the next output character from the output buffer to the hardware。

So every time the output is able to display a character and is ready for the next character。

 an interrupt will occur， and the UA interrupt function will move the next character from the 50q into the hardware。

Okay， next， let's move on to the functions and console do C。

So the functions we want to talk about are these four functions here。The console right function。

Will be used to call you Art put C character by character and add characters to the output buffer。

 So that's what happens。 And since you are put C may sleep， this function may sleep as well。

Console read will wait for input to be ready in the console input。 in particular。

 it waits until the right index has been moved to someplace beyond the next new line or control D for In file。

 And so that means there's some input ready to be retrieved。

 and what it will do is it will copy characters from the input buffer and move them into the user space somewhere until it encounters a new line character or the InDe file control D character。

And as I mentioned in the U art interrupt function。

 we call this function console interrupt for each input character and what console interrupt is going to do is add a character to the input buffer so it's going to add the character here and advance E It's also going to process characters like backspace and control U as well as echoing the character to the output。

If it hits a。New line or the In file character。 then it's going to say， okay。

 we've got enough so that we can enable the input reader to get something。

 And so it's going to advance W2 E and then it's also going to wake up any sleeping functions that are waiting for input。

 So it it might wake up a console read function right the console read function sleeps until there is something available that is R and W are not the same。

 And so a console read function may be sleeping So once we read all the way up to a new line or the In file。

 we call wake up to wake up anybody that's to wake up all the functions that are waiting。And finally。

 we've got a function to initialize things。Okay， if you just want an idea of what's going on。

 you can probably stop here Next， I'm going to look at the code in more detail。Okay。

 now that I've introduced the main organization of these two files。

 I'm going to go over the code that's in the UA。c and the console。c files。 let's start with U。

c and we see the offsets for the registers。 remember in this diagram here。

 I showed the offsets for the register such as LSR is at offsetet 5 and we see LSR at offsetet5 here we see the transmit hold register and receive hold register。

And we have a little macro function here that is used to add the base address of the UA memory map device to the offset。

 and we also have a couple functions here， one is to go out and retrieve the value from this memory map register and a second function。

 write register， which writes the value V into memory map register。I had the transmit buffer， okay。

 that's this buffer here with its read and write indices。And that's defined right here。

 the U transmit buffer， and the size is 32 here。Here is the read and the write。

 Here are the read and write indices， and here is the lock that protects this buffer。

We've also going to be referencing a variable called panicked。 and we'll see that in a second。

 But let's first move to the second page， which is the initial initialized function， so。

Here we are writing to what's called the interrupt En register to disable interrupts from this device。

 so it won't be interrupting at least for the duration of this code。

And then we are doing something with these four rights that are setting the Bo rate to 38。4K。

 and so we do that that gets this device initialized properly， and we also reset the internal FiIOs。

In this picture here， I indicated that the device might have some internal buffering going on and so here we are initializing and enabling that internal buffering。

And finally， we are writing to the interrupt A register to cause it to。

Interrupt whenever we get a character received or whenever the transmit channel is ready to receive another output character。

And we are also initializing the lock。 All right，  moving on to the next page， we have。



![](img/9d532f9a7d6978d199dcb694aa7da97b_2.png)

Actually， I think I want to do this one first， the UA put C sync。Because I think that's simpler。

 you can see that what it's doing， it's got a while loop here and it's just reading the line status register and checking the bit to see whether it's set and as long as it's clear it does a busy loop and the minute this bit is set that is the hardwares way of saying it's ready to receive another byte to transmit。

 And so at that point we write the character that it's passed into the output register。

 We also see see a couple of other things。 we see it disabling interrupts and reenabling interrupts。

And we also see this code here。Panked is a global variable that gets set to true after any hardware error error or sorry。

 any kernel error。 So whenever we call the panic function， after printing the message。

 we set the panicked flag。 And what this does is frees up all future output。

 So if that flag has already been set from a previous error。 We have an infinite loop here。

 This core， when it hits this， it's disabled， the interrupts。

 it's just going to go into an infinite loop and lock up this core。

 And the purpose of that is to once you get an error message， you don't want to see anything else。

 You don't want to see any other output。 If the thing is looping or something。

 you don't want to see a bunch of of output。 You want to freeze up the other cores and prevent them from doing any output。

 So now let's take a look at。User you are put C。 and that is the function here。

 I described it with this。Picture here that's going to grab the lock on the output buffer and add a bite to that。

 So we see that we are acquiring the lock first。 and we'll release it down below。 And again。

 we have this panic stuff。 if， if we've had an error message already。

 this will just basically freeze up the core。 But assuming we haven't had that。

 then what we've got here is a while loop。 And we check right here。

 and this is to a check to see whether the buffer is full。 Remember in my diagram here。

 I said that if the difference between R and w is the size of the buffer。

 then we have a full condition。 And that's what's being tested here。

 If read plus the size of the buffer is equal to the right， then the buffer is full。

 And we don't have an ability to add another character to the buffer。

 we don't want to lose that character， we want to wait。 So here we go to sleep。 And the。

hing that we're using for the channel to sleep on is the address of the read index variable。

 So this is just a number that we use to coordinate the sleep here with the wake up that happens in the U art start function。

So that's the channel right there， and we're passing at the lock as we do with the sleep function。

And once we are able to once the buffer is not full， we come down and execute this code here。

Which will add。The character C to the transmit buffer at location W。 Okay， and it will do it mod。

 the buffer size and then increment W。 And we also call U art start in case the hardware is ready to receive the next output byte。

 We want to get it going on that。 So we call your art start here。

And then we release the lock and exit the loop and return。So next let's look at。You are startk。

And that is here。응。So we have a while loop here。 and what we're doing is checking to see whether the buffer is empty。

 Okay， if the buffer is empty， there's no nothing to be sent to the output。

 So if the read and write index are equal， then we immediately just give up and return。

 But assuming there is something in the buffer， we need to keep going。

 So here we read the status register， the line status register。 and we ask whether。

The bit that indicates that the hardware is ready to receive a byte is is clear or not。

 And so if the hardware is ready to receive the next byte， then we can proceed。 But if it's not。

 we just return immediately。 If it's not ready， then they will interrupt us later。

 when it is ready to receive a byte。 But if it's not ready， we， there's nothing we can do。

 So we just return。 Okay， so the hardware is ready at this point， when we get to this point。

 So we get a character from the buffer。Okay， so we are going to advance。

 so we're going to grab the read index and mod buffer size。

 grab that character and then increment the read index。

 and we have now started up the output and we have freed a position in the output buffer。

 So we might want to wake up awaiting U art put C。 Remember， we just did a sleep on that amount。

 So here's where we do a wake up。 And again， we're using the address of the。

Receive or the read index as our channel key。And we also need to send that character actually to the hardware。

 So that's done at this point here。Next， we have the go through the get C， the U get C function。

 and that is called to get an input character， get a character from the keyboard。 if one is ready。

 but not wait。 So here what we do is we read an input character from the hardware。

 But if none is weight， if none is ready， then we return -1。

 And we just read the status register and check the bit。

 And if it says there's something ready in the read holding register， then we grab it。

 Otherwise we return -1。And finally， we have this。You are interrupt and whenever the hardware is ready to receive the next output character or because some input has arrived and is ready to be fetched。

 there's an interrupt and so this is going to be called from the function device interrupt。

 which is in Tra do C。And so here we read the incoming characters as many as are there。

 And here we send characters to the next character to the output。 So here we。

Call the U art get C to read a character。 And if there's nothing there。

 then we're done reading all the input characters。 Otherwise， we call console interrupt console。

 we're， we're in the interrupt handler。 So console interrupt will not sleep。

 If there are too many characters and no room in the input buffer。 They just get dropped。 We。

 we don't wait。 We just drop them and that will happen in the console interrupt。Okay。

 then we call U Art start to send characters to the output buffer。Next。

 I want to walk through the code in console。c。And I'm going to start with this macro function C here from time to time。

 we need to deal with control characters。 So for example， right here。

 we're asking whether the character is equal to a control D。

 and we also are concerned with things like control P and control U and control H。

So remember what these control characters are。 These are ASI characters。

 It's a way of specifying any ASI value that has a very low number。

 So they start with the Ampersand and control A corresponds to number one， Control B is2 and so on。

 Control D corresponds to number4。And normally， we're used to using things like backslash escapes to deal with control characters。

 For example， the new line characters backslash in。 Well， that's equivalent to decimal 10 or hex A。

 Okay， you can also type control J。 to to achieve the same thing。

 So you can try that on your keyboard。 If you try to control J。

 It's probably equivalent to hitting the enter or return key。We also have control D。

 which is an important one， and that is equivalent to number four， so control D is number four here。

And so what this macro is doing is just allowing us to specify with a letter。

 and it's just subtracting the ampersand， which is for control zero here。

 And so that's what's going on there。This defined constant backspace is a number that's greater than any ASI number。

 The ASCI codes go all the way up to hex 7 F or 127。

 and this is disimal 256 so it's not an ASCI code。诶。😊，Now let's move into cons put C。

 Con C is basically called to send a character directly to the output。

 So it actually sits between print app and U Art put C sync print app actually doesn't call this directly。

 but it calls console put C。 and console put C just called U Art put C。 So switchs past a character。

 and then it passes it on through where it is then sent directly to the output hardware。However。

 it's also used for echoing and for that purpose， it checks to see whether we have a special case of the backspace。

When the user types the backspace key or the delete key。

 the old serial I terminals required the terminal to back up and print a blank to overwrite the character。

 So， for example， if the user types a W and then a backspace， it displays a W。

 and then the terminal needs to back up one character。

 display a bank blank to get rid of the W and then back up one more time so that the next character will go where the W had gone before。

 So that's what's going on here。 If we have that situation。

 we send to the output terminal to the display， a backspace character followed by a blank character followed by another backspace character。

Okay， next let's move on to this， the second page and remember that our output buffer。Was defined。

 I pictured it here like this。 And it has these three indices。 And we see that going on here。

 Here is the。cans。bufferffer。Of 128 by。 And here are our three indexes。

 And we've also got a cons lock， a lock associated with this that protects the buffer and the indexes。

So next， let's look at the right function。 and it's。Called to send characters to the output buffer。

 So it's called here whenever we have a bunch of characters and we want to send them to the output。

 it's got to add them to the buffer 1 by one。 And so it will call your put C for each individual character to add it to the buffer。

 And that's what's going on here。It's past a pointer source and the count of characters to send the output。

 And it's got a loop that does that many times。 And for each character， it calls Uar putse。Now。

 source points to the place where the characters are to be found and in is the number of characters we want to send to the output。

These characters can either be located in the colonel's address space， or they can be located in。

User virtual memory。 And this bullolean flag right here tells which。

 So this determines whether those characters will be gotten from the virtual address space。

 which requires mapping or from a direct mapped address。

 And so that's what this function here is doing。 It is past a place to put the characters and the number of characters to get。

 and it's getting one character at a time。 And it's getting them from this address。 Okay。

 so we're incrementing through the source buffer one by one。

 And we're getting one character at a time。 And we're passing at this flag to tell whether they're coming from user address space or not。

 And the local variable C is just a place where we put them before we send them to the output。

And then we return the number of characters that we successfully wrote。And if anything goes wrong。

 for example， the user。Provides a virtual address that's no good or that then we return -1 from this。

 And that will cause us to break。 And so we'll stop sending characters the output if we run into a bad virtual address。

Okay， let's move on to the next page and this is the console read function。And it， too。

 is past a buffer。 Here's the address of the buffer。

 and here's the number of characters in the buffer。

 And we want to get all the characters from this buffer。 And sorry。

 we want to read from the keyboard and send the data to the user by placing those characters in this buffer。

So。We， we will be getting characters out of the buffer here。 And so we need to。

Acquire the lock on that。 So we've got a while loop here。

 And what we're going to do is we're going to。Get characters out of the buffer。

 And that's going on right here。 You can see that we're grabbing a character from the buffer using the R index。

 and then we're incrementing it。 And let me skip this part right here。 but going down further。

 we decrement our count and when we've gotten as many characters as we want we then terminate the loop。

 release the lock and we return。 and we need to return how many characters we actually successfully red。

 So that's what's going on with target okay this target is saved here， local variable， if we want。

 for example，100 characters， we remember that we want 100 characters and then we decrement down and if something goes wrong and we execute this we exit the loop early we won't have gone all the way to0。

 But if we get all the characters then in will'll be decrement it all the way to zero and we can just return target。

 But if we exit the loop prematurely， then we return something。Less than target。

So as we are getting the characters， let's go back to this point where we get the characters。

 We get a character C， and then。Here， what we're going to do is use this function either copy out。

 And it's going to move。 Well， we're moving one character at a time。 And where are we putting them。

 Well， this is the。嗯。The place where we're getting them from。 okay。

 that's this local variable C buff here。 and destination is the address that was provided for us。

 That's where we are to place them and user destination is a boolean that tells whether this is the user's virtual addresserspace or not。

 So we're passing that and copy out， we'll then move one in this case。

 one character from here to the destination。 And if that worked okay。

 then it won't return a  minus-1。 But if we had any problems we'll break and just we won't have succeeded in in moving that character so we don't decorrement in and said we return some number short of our target。

And if we do succeed in moving the character into the user's address space。

 then we increment the pointer for the next time around the loop。If we had just moved the new line。

 we've then we've。Properly read a full， complete line。 And we need to return at that point。

 So after moving the new line into the user's buffer， we break out of the loop here。God。

 there's one other thing moving back up to this point in the loop。

We are checking to see whether we got a control D。Now， if this is the。

First character that we've gotten。 Okay， in other words。

 this is the first time through the loop in and target are equal， then。This will not be true。

 and we will simply break。 We will gotten no characters。 So the target here will be returned as 0。

And。Then the next time around， we'll read some more characters。 So that's the way Unix works。

 When we get a control D， we have to return an empty string， a string of length 0。

 But then after that， we can keep going。On the other hand。

 if we've already moved some characters into the user's buffer。

Then we basically need to not do the control D here。 We need to stop。 Okay， and that's so we break。

 but we also need to remember that we have hit at a control D。 And so the next time around。

 we're gonna need to return a line of zero characters。 So that's why we decrement this R here。

 So the next time we're called in this in this function， we can return0 characters。Okay。

 moving on to the next function in this file， we have the console interrupt function。

 and this is past a single character。Remember how this is used whenever the U art interrupt function is。

Getting a character from the keyboard。 It's going to call this function for each character。

 So going back to。That you are interrupt function。 It's basically looking to see whether there are any input characters ready from the hardware。

 And if there are for each one， it's going to call this function。So we've got a character。

 and we need to do something with it。 Okay， the character is C。

 and we are going to be putting it into the input buffer。

 So we need to acquire the lock that protects the input buffer， the console buffer。

 and we acquire it。 Then we have a switch statement。 And we look at what kind of character it is。

 It is。 And。

![](img/9d532f9a7d6978d199dcb694aa7da97b_4.png)

Then following down here after the switch statement， we released the lock on the buffer and return。

So we do a couple things if we。See that the input character is a control P。

 We handle it specially by。Printing the process list， we call proc dump。

 So that could be useful for debugging the kernel and seeing what's going on。 It's not。If it is a。

 let's do control H。The backspace character will send a control H that is an ASI 0。

8 character to the hardware。 And the delete key generally will send the ASI character Hex 7 F， so。

Regardless of which are the two characters is or two keys is pressed or which character we receive。

 we want to treat them by backing up。 And so we asked here， do we have anything in the input。

 In other words， have we gotten anything。Is E greater than W， if so。Then we want to back up E 1 B。

 And we want to call Ks putty with a special backspace。Code。

 which will obliterate the character by doing a backspace and then a blankk and then printing another backspace。

 So that's how we deal with a backspace or delete key。 And if we get a control U。

 we do something similar。 We ask we basically are going to do the same thing repeatedly until we back up E to the next control in。

 that is sorry， new line character。 Or until we hit W。 So that's what's going on with this loop。

As long as E we can back up some that is E and W were different and we haven't yet hit the new line character。

 Then we do the same thing。 We decrement E and call cons puts see with this backspace code。

Now let's look at what happens for everything else。If the character is a null character。We ignore it。

And if the buffer is completely full， we ignore it。 Okay。

 so we just drop the character if the buffer is full here we're asking doing the the buffer full test with this right here。

If you hit the inner key or the return key on different terminals can either return the so called ASCI return code or the ASCI new line code。

This is decimal 10， and this is decimal 13， also 0 X， O， D or0 x 0， A。

Some of us have memorized these。If it is return， we convert it to the new line character with this。

 Otherwise， we keep it whatever it is。Then we echo it back to the output。

And then we store it into the buffer。 So here we're using E。 So we add it here。

 whether it's a new line or something else， we add it here and increment E。

 And so that's what's going on at this point。And then we determine whether we've got something that we need to wake up the reader。

 Okay， so if it was a control， a new line。Or it was a control D。Or the buffer was full。

 Then we need to wake up any sleeping console read function。 Okay， so that's what we do here。

 First of all， we update W So that moves W all the way up to here。

 which means that the reader can read as much as as is available。And then we do wake up。

 So this is using as a channel。The address of the read index variable。And so that。

Concludes this function。 We've got。So just we've got one more function after that here's the end of that switch statement and the release。

 and then we've got an initialized function that is going to initialize the console lock and it's also going to call the UA initialized function。

Don't want to really get into that this here， but we're saving pointers to the console read and Con write functions。

Okay， that's it to see you in the next video。