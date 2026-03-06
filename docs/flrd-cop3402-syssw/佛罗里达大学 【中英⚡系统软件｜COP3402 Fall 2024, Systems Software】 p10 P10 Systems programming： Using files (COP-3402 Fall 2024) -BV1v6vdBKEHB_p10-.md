# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p10 P10 Systems programming： Using files (COP-3402 Fall 2024) -BV1v6vdBKEHB_p10-

All right， so welcome back to System softwareware。Today we're starting our systems programming segment for the next couple of weeks。

 so we'll look at some replicating some core tools and we'll look at some of the common assist calls。

 system calls that you have available in the kernel， but before we get into that。

Let's quickly go over the homework， so the homework from last time was to read some introductory material about Linux programming from this book。

 the Linux programmingming Inter。So the question was how do you check what kind of error is thrown by a system call。

 so how do you check it？Okay， you check the error no level value， is that all you need to do， yeah？

First， you have to see if there is an error， so how do you check if there is an error？Yeah。

 for many functions it's negative one and we'll go over today how you can read the documentation and it'll tell you exactly what the return values are going to be and what the air condition is so exactly right so you have to check and so in the kind of UniX philosophy you have to check for these errors yourself it's very easy to write systems code and just make these calls calls calls calls not do an error checking because。

You know， the kernel is not going to stop you unless you get a seg fault or something。

So and we'll go over that more today this error checking。

And it's kind of a good exercise in programming in general because it's very easy to program optimistically without thinking about what can go wrong。

 and in kernel systems programming， it makes air handling by the developer very。

 very explicit and very， very manual， very much do it yourself， air handling approach。All right。

 any other questions on the homework？Yeah。A hello project right yeah。ごさ？It's okay。You mean。

 file does not exist？It's okay， you can get around that by using RN F。Instead。So RMFF will not。

It won't， yeah， it'll ignore those errors。So yeah， that's okay， that's okay， yeah。

This is what I have so far。My vision is not that good to see that from here。

So after class I can take a look at an office hours， so I have office hours today。

 so the project is due today。As listed， hopefully it's clear I know some people had issues with the PMAM。

differenceifference between the homework and the project。

 but it is due today still time till one minute before midnight tonight。Yeah， question。

Which one to submit？The one works。嗯。Number two， okay， so yeah。

 you can write git add and then the file name you want to stage for commit and then git commit and the name of the file as well。

 so one way to do this。I don't even have the helllo project。

 but one way you could do this is to say gett add。Hello dot C。Let me have a。Like I have a。Actually。

 how don't' to go to use this。Let me just make。Thank you， hello。Directory。

So you just do git add and the name of the file let me make。The file。

So just say get add the name of the file， so okay， so when you type gett status。

It'll tell you you have untracked files， that means those source files have not been documented in the repository database。

 GitAd will stage it。So we kind of went over briefly last time what staging was about。

 you can collect together the individual files and lines that you want。

 get separates staging and commit and when you run Gi status it'll tell you these are changes to be committed。

 that means they're staged。And then get commit and the same name of the file。

 it'll pop up your editor。Put your message in。And now when you type get status。

 it'll tell you that there's nothing left to commit because you see more stuff to commit like untracked files and you can add those and commit those。

Does that answer your question？Yeah。You can do that you can do that too so I'm not going to go into too much detail about like software engineering practice in this class。

 It's best practice to pick the individual lines you want to commit I pointed to did anybody read that Google engineering guide you read that。

That guide that I。Sent out。I have a link to it here。This actually goes into so Google is very。

 very good at this collaborative engineering， the source version control。

 and they'll actually give you guidance on having good， I think is what of these change logs。

 I think they're called。They're using this， this is the Google linko。

 they'll actually tell you how to make these。嗯。Basically how to make these commits and using Git Lo。

But in this class say I'm not really checking that pick processes do senior design。

 actually work with other people who will suffer from your like unclear engineering practices and then you'll eventually learn how to do this in a good way。

 but here it's fine， use GitHve' like it is super flexible。You can add all the files if you want。

 there's a way to add everything is that's untracked， I think， to。

 there are like lazy ways to use Gi。All right， other questions on the hellello Project yeah。

You mean like running git revert？Oh， deleting the whole repository。Had you already pushed to the？

So that database still exists on our grading server。

So yeah deleting it locally just means your local copy of the database is deleted and so you'll still okay。

 so maybe you tried to push again and it said I can't push anymore so I think what to do in that case is to clone again。

 clone your repository again。And start from the database that you have you might be able to do Git pushush F to force it。

 but I think that server does not I think I tried that the server does not permit you to do that if you ran your own server you could actually like GiHub will if you don't protect against it you can actually force it to overwrite the branch but I think Gito light won't so I think the best thing you do is just clone your existing repository and just like you do in real engineering instead of saying oh I messed up let me go back and change history just fix it going forward so any double check the know use this selfcheck process to see whether you have all the files there you use Git status to make sure all these are committed does that kind of kind of help there is actually a Git revert command which will automatically undo a commit if you really like think one of your commits is bad but you can always just。

Like you could， for instance， make a commit that deletes all your files and then you'd have a the repository wouldn't be empty。

 but the current snapshot of it would be。So it's like it's like a you know an append only log。

 a forward moving log only so you should yeah if you have trouble like modifying the current data to say I've come off hours and I'll help you work through it。

 but you should be able to。Just add more commits that will fix whatever issue you have。

That makes sense。Yeah。So the way to do that is to use this self check section。

This is exactly what our grader is going to run， our grader is going to run this get clone command for your NID。

And so if it works for you， it'll work for him。And so this is like exactly I told him， hey。

 look at the self check， write your automated scripts to just run this for all the students。

So that way， that's kind of the nice part about computing as you can。Check yourself。

 you don't have to rely on anyone to prove it for you。

 you can actually check for yourself whether it's correct。

And the way to do aversion control is just clone out a fresh copy of your repository so that you didn't accidentally miss some commits that you didn't push or miss some changes that you didn't commit。

Other questions other questions on this？Yeah。えか？一般？Could you make a make file， what do you mean。

 a make file that doesn't have anything in it？そでもれる。

You mean a make file to run grading to like down yeah， yeah， absolutely you can make a grading。

 you can make a grading script to do that， you'd still need to have a list of the NIDs。

And input them somehow， I think I recommended he use Python。To do this。Yeah。

 you could use make probably。Who submitted hello， who submitted the project？Okay， pretty good。

 pretty good， so I do have office hours today right after this if you have questions and remember that you can always resubmit as long as you make a submission today。

 so just to refresh you on the project rules unlike in previous semesters。

 if you looked at my previous syllabi。In this version of the class。

 you have to make some submission first， even if it completely fails， it doesn't work at all。

 make a submission。And then you can always resubmit again after that。

But if you don't submit by today， then no reubmissions。

And that's just to make sure everybody's like staying on track in the class there were just too many people who waited till not only the end of the semester。

 but sometimes after the end of the semester would be like I'm now starting this project so I'm removing a little bit of that flexibility yeah。

Just pushing your repository yeah， and that'll be the case for all projects it'll just be submitting so that's kind of the nice part for us about using version control is that。

Using synchronizing your repository is the same thing as submitting your project。

 just like you would do in real world software engineering。

Push it to some publicly available repository now the whole world has it available to you。All right。

 everybody good on yeah， yeah。I。No， yeah， as long as they have Git the Git tool， then yeah。

 they can get your source code。でか。Yeah， it depends。

 yeah you have to yeah you have to install on all systems I know there's like somebody told me there's in Windows there's git bash。

 I think it's called there's like a bash tool or a sorry git。ProMaybe I cant remember what's called。

 but Windows has like a piece of software that will give you the Uni tools in one package。

 including Git。或真。何やの？There is WFL， but there's one that's like native， I think it's called Git bash。

It does。

![](img/bd2a1c882db7724510a8cdd51f4cced9_1.png)

Okay， so are yeah， there are get tools for Windows， get dashash， yeah， this is it。Yeah。

 so WSL is like virtualized， like you're running a different operating system。

 you're running in Buntu， but this， I think is a native tool。But yeah， again is just it's a program。

And as long as you can port it other。Operating systems， then you can run that on other systems。

 you don't need bash。Necessarily。All right， everybody， good on the hellello project。



![](img/bd2a1c882db7724510a8cdd51f4cced9_3.png)

So hopefully this kind of will work out a bunch of the kinks in。The project submission process。

 that's why I did it this way I tried to give a project that where the programming part。

As I think I promise you all the programming part is really easy。

 but all the stuff around it may not be so easy， especially if you haven't seen this before。

 but this is kind of the classic systems program and really just development a workflow。

Code in your in your editor。Use build automation to build your project and use gett to deploy at least deploy the software the source code for your project so if you if you can kind of wrap your head around these three steps and at least。

A little muscle memory for some of the basic parts of each of these。Eiting， building。

 version control， and you'll be well set up for most software engineering workflows because I think pretty much all of them in any professional setting will use these three stages。

 at least。All right， so hopefully everybody's hopefully everybody's comfortable with this and then you know in the next project I'll just ask you to make a make file and I'll still give you some gi commands because we're going to create the Git repository in a different way。

Pone it from the beginning so that way you won't， anyway， you'll see it in the next project。

 that we'll go over that today。Okay， so let's go on to the main content of this lecture。

 first lecture of systems programming。Using files now I think so who's youve used like F open。F。

 did everyone learn this in like intro to C？Just covered in there。Okay。

 so did anyone ever just use open without the F just open？Or read or write？All right。

 so these are the system call versions of those functions， so to speak。

 and we'll go into details about how EO and how those other functions are actually implemented using the kernel。

So which part of a software system？Manaages files。At least in the Linux world。

Or how are files created？Who does it， who manages files？Where is the file system created the disk？

Itself have the file system on it。Sort of。Yeah。So we have the operating system and specifically the kernel of the operating system。

 the kernel is a library kind of talked when we talked about processes and files that the kernel provides this abstraction layer over the hardware。

And so just to give you a little refresher。I showed you this picture in the very first day of class where we have all the hardware components down here that the electrical engineer spent decades developing。

 providing us an interface to their hardware to do things like，Run mathematical operations。

 store bits。bits on physical media。And up here we have all the applications that we all love and use want to use on computing。

 and in between we have the kernel， which provides this virtualized or idealized or emulation layer。

 whatever you want to call it。That kind of gives you this abstract or idealized form of the hardware and why why did this。

 Why was this useful， then remember what what you like why bother doing this。

 Why not just write your， I want to just write your applications on the hardware。

 Why bother having a kernel at all， yeah。Protects the hardware。

 so like if there are a lot of users and a lot of applications。

 you don't want one application to be able to blow away what all the other programs are doing yeah。

It's easier， yeah， why is it easier？You don't have to learn assembly and yeah。Yeah。

 you have abstractions so related to what your col was saying you can abstract away or find the commonalities in different hardware media。

 so the engineer who designed this spinning disk，They may have some bus。

It used to be IDE bus years and years ago。Other pieces of hardware may use a Sa of bus。

 and those have different sets of commands that you have to run in order to access your storage device。

 the kernel abstracts those away。Exactly exactly right yeah。

 that that the kernel is what does that kernel is what unifies those I mean the hardware layer does it a little bit like a common bus。

But yeah， it's the kernel that makes makes it so and if you remember when we talked about files beyond just storage。

 files could be used for other things like setting up pipes or network operations doesn't necessarily have to be。

Storage， anything that has reading and writing can be modeled as a file in the Linux world。

 and so it's the kernel that manages those abstractions for you。

And it certainly makes it much easier to write code， portable code across different hardware yeah。

So yeah， that's a good question， so the bio is kind of like a built in kernel of sorts。

 actually nowadays with EFI， the modern- I don't know。

 I guess you still called a bio is very fully featured。

 I mean it's almost like its own kernel on its own， but old school bio was like a very。

 very low level kernel provided very， very basic operations like writing characters to the screen。

 almost like a very， very mini operating system， and that would be used by the operating system as a common way to start up。

Because if everyone had their own way of initializing the hardware and their own set of commands to initialize hardware。

 maybe。Yeah， it's almost like a low layer kernel， and there are more sophisticated versions of this like EFI these days。

嗯。Yeah， if you let me know， I can point you to， there's a good wiki page called that I was showing another student。

 I think it's called OSdev。wiki。呃。This is a great resource if you want to learn more about the OA operating system development。

And I think they'll probably go into biases。Somewhere in here。Yeah。

 they're go into detail about that。Okay， so for the system software， system software is。

It it's like applications in that it's sitting on top of the kernel and the hardware。

 what distinguishes it of know it's kind of a vague term。

 but what distinguishes it is that it provides low level functionality that bridges the kernel or the hardware end。

Applications and so when you're doing systems programming。

 you're working a lot with the low level kernel abstractions。So for instance。

 the F open and F print F。Those are C library standard functions that call the kernel in order to help you manage files。

 reading and writing files。So let me go into the kernel design very briefly。

 if you read chapter three of the Linux programming interface that talks about this。

 and we already talked about that already， it abstracts way hardware differences。

And so one one very simple way to look at。The kernel is that it's kind of like a library。

 it provides this。So provides there's this boundary between the kernel and what the kernel provides and what system software and other applications use in the kernel。

So for instance， when you want to call open a file。There's an open library call。

 just like any other library that you'd write， there's an open library call。

That you make from user space in order to ask the kernelel， hey。

 I'd like to use the abstraction that you've created in order to read this data on disk。

And so under the hood， this open command。We'll do a bunch of low level stuff in order to manage。

Layout of that file on disk。So here's the hardware layer。And the kernel kind of mediates。

File operations between user space and the disk and also at the same time providing this common abstraction so that you don't have to worry about the hardware differences。

And so this is sometimes called kernel mode or kernel space and user space。嗯。And in modern hardware。

 I mean， hardwarers for like the last 40 years， this boundary is not just a library boundary。

 just like it is in C， it's enforced by the hardware。

And this is how protection works in modern computers。

If you're running in a user spaces program and there's no holes in the kernel design or the hardware design。

 then you can't actually directly access any of the hardware。

 there are assembly commands that you can run to access hardware directly。But the hardware itself。

 the CPU will prevent you from doing that， so if you write a program that has those commands。

 it will not run them。And if you want to access any kind of hardware。

You have to go through the kernel and there is a trick。

That is shown in programming Inter Facebook to go across this boundary。

 so if you're a user space application and you can't access hardware。

Then there's a special functionality in the hardware in order to switch。

kernel mode so that the processor can start accessing hardware。

So this is just the layer opened up a little bit， each of these cis calls is defined in the kernel and there is a special wrapper in a seed library to make the transition between user mode and kernel mode。

So as I kind of pointed out already， these system calls will operate on the kernel abstractions。

 processes， memory files， if you want to learn more about how the kernel creates these abstractions。

 take an operating system course or read the operating system three easy pieces book that I've linked in these notes or you can Google it。

So let's take a look briefly at this。Linux programming interface diagram that they've got here。

So it's not unlike when you write a C function and you want to call that C function。

All that happens is basically a branch， a jump happens， so when you go to call that function。

 the program counter， you guys learned about this in computer organization， how functions work。

 you just have a branch instruction and it jumps change of the program counter and goes through a different part of the code。

Effectively， the same thing happens with the kernel。Except the。Except at the hardware level。

 we need to make this switch between user space， which doesn't allow us to do any hardware operations and kernel space。

 which does allow us to do operations and so there's a special interrupt。

We learned about interrupts in computer organization， they taught this right。

 now did they teach this？A couple of people remember。嗯。Yeah， so it interrupts our events。

That the hardware manages and the operating system installs event handlers or interrupt handlers to run code once these interrupts happen。

 like for instance， if network network data comes in on the network of the storage media rights to memory。

 and there are things called software interrupts that allow userspace applications to send an event to the processor。

And that event will transition to Colel space， and then the colon will take over。

 it'll run a little command， take over。And in the case of in HeX 80。

 which is the Linux interrupt code that's used for transitioning to kernel space。

 the kernel will see that as a signal to run a system call。And in user space。

 you set up which system call you want the arguments。call this interrupt。

 the hardware will enter the kernel for you and the kernel has the definition of this the actual code for this system call。

 it executes it once it's done， puts the return value in any error code back into user space。

 and then your program continues on just like any other function call would。So this is super brief。

 this is more like operate operating system level stuff than any quick questions on this。

On this design， yeah。A different one？They're run inside the system so that well。

 the terminals a program running on the operating system is running on the machine， and so yeah。

 this is all running on the same machine， this is all running on the same machine。

So it's what yeah one。Yeah， yeah， this is running on one machine， one if you have one processor。

 it's all running on the same processor。And this whole design is really around hardware protection to prohibit the user spaces applications from directly touching hardware。

 and this is the scheme that。I don't know who set it up， maybe， I mean。

 Intel got to popularize it they have these rings of protection。

And they just set up this mechanism where in assembly。

 you can trigger the processor to enter this different state， enter this hard kernel node state。

And because when the system boot it up。The colonel took control of what programs would run or what code would run whenever these interrupts happened。

Prevents user space applications from accessing protected hardware。

So it's not permissions for the file， this is permissions to run a set of hardware instructions。

 so you can think of like your ISA your set of instructions that the CPU supports。In protected mode。

 there's only a subset that you're allowed to run。And when you switch to kernel mode or protected heart。

I think it's called supervisor mode。You can't remember the term。

 then the set of commands you're allowed to run is larger。That makes sense。

 so there's only a subset of commands you're allowed to run。In user space。And when you trigger this。

 interrupt。The kernel has already installed at boot time code that will run。

 that will run the kernel code， so in memory you basically have like a set of code that's the kernel code。

That you can only enter through these system calls。And that's the only code。you know。

 barring any vulnerilities， that's the only code that can run in supervisor mode that can run with the full set of hardware processor instructions。

The processor has does does that kind of make more sense？All right， so taking a last class。

 this stuff is pretty cool， you can actually even write your own kind of simple versions of this if you can actually boot your machine。

Without having to have an operating system， you can write your own programs。

That run just kind of on the bare metal and I think this page will go through that it'll actually go through some examples of just。

Boooting to your own。To your own program and then you'll have。You won't be in protected mode。

 you'll be able to run whatever hardware instructions you'd like。Okay， so let's go over system calls。

 from our point of view， as the programmers， they work just like C functions。

You call them just like a C function， they give you a return value like a C function。And。Here this。

 there's a wrapper， as they call it a raper in the Sea library。

That handles all of the argument passing and collecting the return value and error codes handles all that for you so the function will behave。

Just like a C function。U。There's one little difference and that's in error handling。

 error handling is done in this standard way in the unit and we'll go over those details of how to use that。



![](img/bd2a1c882db7724510a8cdd51f4cced9_5.png)

If you want to see what system calls are available。



![](img/bd2a1c882db7724510a8cdd51f4cced9_7.png)

よし。呃。You can use the man page to show you a list of the system calls。

And so here's the list of them that Linux provides。You can see there's a lot probably many that you。

Don't use。Let's see if there's any that are in common use， probably an intro to see。

Probably you use C library。Functions like F open So if I search for F open here， there's no F open。

But there is open。The open command。It's different from F open， yeah， it's different from F Open。

And let me go into yeah， let me go into what these what these differences are all right。

 so if you when you run man， you'll notice that there's this number here too。

That's not an argument to the function， and this is not a function。

And so the man pages are divided into these predefined。

Sections like sections of a book or chapters of a book or volumes。 and we can see what those are by。

Kind of self referentially looking at the man page for the man command。买卖。

And so these are the sections of。Documentation we have， so section two documents the system calls。

And section three documents the library calls， for instance， F open。

 and so open open is the system call that allows you to open open， read， write， close。

 these operate on files at the kernel level。And when you use F open or F print F or F scan F。

 these are C library functions， so those don't directly call the kernel。

 instead they use the kernel file operations in order to implement more convenient file handling for you。

So that's why libraries are a type of system software because they mediate your application and the kernel。

And so when you're trying to look up the documentation， you can explicitly。

Put the number of the section that you want to look up the function so if I look up。

 try to look up open， which is a system call inside the C library documentation。

 it's going to tell me there's no entry。But if I use F open。In section three，voila。

 I get the documentation for F open。If you ever like forget， there's a dash A which will。

Open all of them。All the ones that match。In section one， which is for commands。

 it'll open that when you quit， it'll just you can go to the next one， you can go to every。

Every section that has a match with open。If you forget。

 and it'll always tell you which section you're in here at the top。Okay。

 so that'll be useful when you're writing your systems code because it's hard to remember exactly the details of these library calls。

 I mean that's also true for see standard library calls， you know this will tell you。

The function signatures。And more importantly， it'll tell you。Return value。So you know。

Exactly what to expect。And it'll tell you error conditions， what the return value is for an error。

And when there's an error， it'll tell you all the different kinds of errors。

That it will throw what the air state will be when you have an error。Okay。

 so let's look at the system call versions of these。Of these functions。

So as you I guess everyone learned in。呃。Intro to C。You have F open， F print F， F scan， F。

 and I guess F close， right， F close as well， What's that？FCc。Oh F right， to move within a file。

 and so the system call versions of these are open。And right。And read。And close。

 and I guess the seek is not。I think seek。Is some functionality that's provided by the。

Library for you。Actually， they're a sick。Reposition， okay， no I just provided by the kernel as well。

 to reposition the location。Okay， so that's how you can look up the documentation for these calls。

All right， so the UniX way of doing error handling。Is to。Give it to the developer。

 give it to the programmer the operating system is going to give you very little help in error handling and if you want to look at some of the background。

Behind this， there's this kind of classic essay called Rise of Wores Better about this Unix design versus other kernel designs。

But in the UniX world this kind of airhand can is kicked down the road to you the developer so basically whenever you're doing any system calls or really any library calls。

 you should have kind of reflexively think what are the error states of this。

 what will happen when this go wrong and actually in any program you should be thinking worst case。

 what's going to happen？If this goes wrong and how do I even represent something going wrong。

 so here's the Uni way of representing something going wrong。This is the open command。

So you give it some path。There are flags for saying whether you want read only or write only。

 et cetera。And。To handle the error， we check the return value to see if it's the return value associated with an error。

And then this error number， error NO is set for you。

To some error code that corresponds to the error that you got。

So that's the basic process you run assist call。Look at its return value。

Every time you run a system call， you check its return value。

 so if you looked into a Linux programming or Facebook。

 you'll see lots and lots of error checking after every call。

 there's always an if statement checking， sometimes the function is one little trick and see is that you can put the function call in the if conditional。

 which you can't really do in many other languages。But every time you run a cis call。

You got to run a check for the return value。So a lot of these system calls have。嗯。

Negative one as a return value， but not always。How can I search that？Got the wrong open。So here。

 so now I examples of I'll give examples of all the system calls that you'll need for the projects in this class。

 but if you ever are in doubt or you don't want to look through my code。

 you can always do the page and look and see what the error。What the error return value is。

 so in this case it says on error， negative one return and error number is set。Questions on this。

P straightforward4， right？Just takes little discipline every time you run a system call to do the error checking and in this class。

So okay， so one of the benefits of this from the system programming world。

Of doing error checking is that you can more gracefully handle this error。

 like let's say you're writing a program that you know maybe it's like。

A drawing application that has somebody's doing drawing。

 you probably don't just want to quit the application if you encounter any cisca error。

You might want to save that person's work or try to recover from the error or repeat the open。

 there's all sorts of different designs of your system that you can implement when error checking is left up to you。

 the developer。Yeah，Yeah。Oh， so so well this is because I want to print stuff out more easily and I want to use the easier library for printing stuff out。

So the differences for read and W writeite and printnt F， et cetera。

 is that this has like string processing。This format string be you can put like placeholders in it。

 the system call version， which is just right， it's just working with raw bitetes。To a file。Oh， oh。

 I just wonder， oh sorry why use oh sorry， sorry， why I use F printf。

 F printf because I want to write the standard error。😡，That's why， yeah， yeah。

If it outputs a negative 1， it is an error。So this is saying if open returns negative one。

 then know according to the documentation。Negative one is only returned on an error or on an error。

 negative one is returned， you would hope that it's definitely if。

And so this piece of code is your error handling code。Yeah。Here个。Yeah。

You never have to define error ever yeah。When yeah， whenever error happens， this is a pretty。

 what's it？The error number。嗯。Yeah， oh yeah you include this， you include this。

 you can include this for the definition， but it's。It's kind of like。

 I can't remember if it's done by， I think it is done by the。By the Sea library。

 I don't know if it's done by the sea library or by the colon。

 I don't know the step where the error number is being set。But yeah。

 it's like a hard codeed name that the C library。Probably not the kernel。

 but the C library will just set this value for you after if there's an error， yeah。

This is the- so if you remember the standard IO， the stuff on standard IO。

 every process is opened with or run with three open files， standard in。

 standard out and standard error。And when you're running the best terminal。

 standard Air and standard out， go to the same place， they go to your terminal window。

But it's just a convention for separating the kind of real output of your application。

 so for instance， we're going to do a file listing application。

All of the content that is supposed know when you list files that should be the output whenever there's an error。

 you don't want to like pollute your output with that error so you keep them separate。

 so for instance， if I'm doing LS of some file that doesn't exist。

This text is being printed out to standard error， whereas if I just say。LS， hello dot C。

 this is standard out。 You can't see this on the terminal。

 but you can kind of prove it to yourself by。Redirecting standard error is how you redirect standard error to not print。

Whereas if the file exists and I redirected my standard error。I can still see standard out。

So this is just a convention in the UniIX world， use this convention for your application because I kind of rigorously define or try to extensively define your output and the output standard out does not include the error messages。

All right， other questions on the basics of error handling？And systems。World。

So basically every time you use a system call。Do this check。I mean for this class。

 all you really need to do is like quit， we're not going to be checking。やします。

AhThat's a really good question so somebody knows about Pierre， who's used Pierre。

 did you guys learn this？Okay， not many， all right， so there is a helper function called P error。

 which will interpret error number for you。So if you look at this man page。For se open。

 keep doing the wrong one。嗯。In this error section， it'll list out all of the different ways。😡。

That the colonel will report。That your system call went wrong。

And each one of these codes here corresponds to a number。

 I think they're defined with macros probably， so there's a unique number for error number。

That can be referenced with this name。So these are all the ways that your kernel can。

For the open command can go wrong， can say， I can't do this command。 So for instance。

 if it's the E exists。Air number。It means that the path already exists。

And so this is very common in computing systems and in programming that the handling of errors is just as detailed and comprehensive as the handling of expected output。

Which for every programmer， you should be aware of error handling。In your code so it's very。

 very detailed it standardized， I think for all of these these system calls。

 each system call has its own。Has its own set of errors and this whole set of errors across all system calls is all predefined。

呃。By the kernel， so for instance， there's no more memory available in the kernel。

 which would be pretty bad if that happened。呃。Not a directory。

 so this is the extensive list permissions issues， this is the extensive list of all the things that can go wrong when you call the error。

And now for this class， you're not going to have to do any detailed error handling。

 but if you're a systems developer。You can use this to implement various error handling methods for a robust system。

So just like I was talking about you have a drawing application。

 let's say you have an airplane that's flying， you don't want to stop the computer。

 you want to try to recover from the air， you want to either rerun it again or signal to the user that something went wrong。

 like for instance， hey you don't have permissions access this file。

 what do you want to do now for a lot of the low level like LS， you just run the can again。

 but if you're running a long running system？You may want to employ better air handling options than just like crashing or stopping。

Okay， so Pierre will just print out a message， it'll translate that error number into an error message for you。

And I'll show an example of this in a little bit when I go into when we do some actual systems calls。

All right， other questions on air handling because this is going to be pretty critical。As you'll see。

 as I'll show， if you don't do the air handling， the kernel will not necessarily stop for you。

The program will continue running。And you maybe get very， very unexpected results。

 maybe very hard to find what's causing this， like for instance。

 you may have a little typo in your path and the kernel couldn't open and then when you keep trying to read or write that file。

 you're going to get errors。Somewhere else in the program where the error actually didn't happen so make sure every time you do a system call do error handling as well and you only have to exit there's also this convenient exit code for you exit failure that you can use oh that was your question so there's there's a yeah so these are you know this is kind of the principle of no magic numbers en codingd。

So you don you want to have names instead of numbers。

 and so the system in header files defines a bunch of names for these magic numbers。

 like each of these error numbers， possibilities has its own name in a macro。

You've got exit success and exit failure for conventions on what exit code to you use。

For your application。And so yeah， this is the basic pattern that you'll use。

 check what the return value is for an error for your system call that you're running。

 but this is the basic pattern of air handling that that's all I're really expecting in this class。

Yeah。Oh this this is just your error message， so this will just this is like printf。

 it'll just print out open and then it'll print out the error message let me show an example of that in a second。

 but there I don't have any I don't think，I don't think I said we're going to actually check the value of that。

 we're just going to check to make sure that that you exited properly。

Or that your program doesn't have any bugs because you didn't do air handling。So for instance。

 we'll give you a file that doesn't exist。And then this is how you gracefully handle that。

You actually checked the error open， will'll throw an error if you give it a file that doesn't exist。

And then or at least for Reed， it'll give you an error。

And so we'll just throw you files that don't exist and see what your program does。All right。

 other question on air handling， this is probably the most salient thing to remember from this you know all system program it's really about air handling。

安全で。Ohh， thats a good question， you mean like checking whether you've checked the error code。

You could， I don't know if there are analyzers that will do that。

 but it would not be hard to write a static analyzer to do that。

 you can take my compilers class and you can write that as a project or you can do it as a bonus project。

 but it's not that hard actually to write a very， very simple checker。

It won't necessarily cut all cases， but you could， yeah。

 you could write a checker that will automatically do this， but this is very beyond。This class。

 this is a program analysis task。But you certainly could， yeah。

 I don't know if there's any EM plugins， yeah， Google it， see if that exists。

I feel like there must be， I feel like there must be， it's a common thing。So yeah。

 check yourself and so the rule is if you're using system call。Check the error。

 check the error condition and all the only error handling you really need to do in this class。

Perhaps with one exception in Michel that we'll talk about is just exit。🤧Okay。

 so I put a full example of using error number here。

 but I'm going to skip ahead just for the sake of time so we get into all of the other system calls that you'll need for the LS project。

Okay， so let's start with files。So the only ones you need for this project are opening files。

 reading files， and closing them。And for the reading tonight for homework。Oh actually， okay。

 I didn't provide this as a reading because I。I actually thought people had used to open open and read and close already。

 but it was F open that people used， so if you want to read more about these uses。

 you know this is the chapter to read。In the Linux programming Inter Facebook。Did I exc you four it？

No， it was only one in three。So if you want to learn more about these， read this。

But I'm going to go over an example here that should be all you need for doing the LS project。

So maybe before we go on， let me go over what the LS project is briefly。

 then I'll go into all the system calls you need yeah。せか？sMaybe there's an issue with Eus this？

Do you mean to get in to uset this right now， oh yeah？哦没。It's there。But。よし。Okay， so。I don't know。

 I don't know， we'll have to email the IT so if there's an issue and people no one could submit yeah。

 let me know。And sounds like several people having issues。So if you can't submit。

 so just let me know， go on Ed STM and not other people you know， pile on and say， yeah， I can't。

 I can't， I can't go and then I'll have a strong signal that that something's wrong with use this。

Yeah， not sure。What's going on。Wait， no it's asking me for- so when you put in your password。

 it just denies you。Trying now， maybe。你点到话。All right， something's going all with Eustace。

Unfortunately， but yeah， just let me know on that Stan， keep me up to date。

And we'll see we still have。You know，11 hours for submission， but yeah， let me know I can yeah。

 of course， if used this as an option and you can't submit then。You won't get penalized for that。

All right， so let me go over in the next project。呃。My LS， so remember the LS command。

 what does the LS command do？Thisss all the files in your directory or a directory given on the path。

So everyone is going to write their own version of LS called My LS。It's much simpler。

 it's only going to take a single argument。That argument is optional， just like with LS。

It can be relative or absolute。And if you don't provide the directory。

 it'll be the current working directory， what's the current working directory？

That's how you can find it you can find the print working directorys。

 every process is it started up with a working directory， so in your command line shell。

When you're in bash。That director you're in that you can type LS， that's your working directory。

And of course， air handling， and so the output， let me just give you an example of the output。

So it's going to be very different from the LS command。It's going to be a list of。Every file。

including dot and dot dot， which if you list out the directory。

 it's going to be in every single file and some metadata and data about these files。

So I'll go over this in detail， but basically you'll read the number of links。

 the kind of file it is， its size or number of files in the directory， and if it's a regular file。

 then you'll print out a little preview。Of the file。Yeah。Sorry。嗯哼。😊。

It's going to be a C program and you'll use these system calls to do it。

 so please don't you know use other system calls like F open and stuff like that。

 which will make it easier use these system calls。And only these， you know。

 for printing and stuff like that， of course， you can use the standard libraries。

 but for doing file management， use these system calls。So we already went over PR and exit。

 And so now let's go over these three sets。 So we'll go over how to。

Open and read files we'll go over how to get metadata about files with the stat command and we'll go over how to read and navigate directories。

 which you'll need in order to list out all stuff in the directories。rightQuest， questions on this。

 yeah。Yes， so in my example code。You'll see all the header all the header files will be there for the example that you need for it annotated。

 All right， so let me actually just go into the。Let me go into the code， so this is going to be。



![](img/bd2a1c882db7724510a8cdd51f4cced9_9.png)

牛皮。

![](img/bd2a1c882db7724510a8cdd51f4cced9_11.png)

![](img/bd2a1c882db7724510a8cdd51f4cced9_12.png)

![](img/bd2a1c882db7724510a8cdd51f4cced9_13.png)

Okay， so this program here is a。Well， so the source code is the final source code is in the will be in the class notes。

So， I will。That will be available on。The website， but let me I would just want to walk you through。

Step by step。呃。This code， so let me build it up。嗯。It's on the website， it's on the website。嗯嗯。Okay。

 so sorry， in each of these are examples that tells you all the header files you need。

And so let's just start with some。So I'm just setting up my。All right， so let me get rid of。

All of this。So this is the kind of template for showing you examples。

 this isn't necessarily what your final program will look like。

Although you can use code similar to this to read in a path， remember it's optional。

 this is a not optional path， does anyone have any questions about this code here？Oh， yeah。

Any questions on this？だか。おあお。こい。I wasn't use yeah。Boy， you can cut and paste。As well。

Cutting and pasting。だな。Well， you can use the code that I provide as a template。

If I provide it on for you for class， it's not cheating to use that code if it's in my notes。Okay。

 so anybody have questions on this， this is just reading in one argument。

From the command line and assigning it to this path variable。I think everyone's done this， right。

 who's read in arguments from the command line and intro to C。Only half the people， okay。

So this is the code to do it。To read in an argument。Just an argument on the command line。

 so when I run files， this is my argument here。So let me let me。

So just to show you what this looks like here， I'm just recompiling files。And if I。Print out path。

It should just print out。So you can see all this program does is it takes。

The one command line argument and print it out。I could change this too。

So what should be printed out when I run this program？Whatever I typed in， so this is my argument。

 so whatever I put here on the command line。That's going to be what gets printed out。Do all what。

This is my argument。So this is just besh。This is this is the terminal， this is the terminal。

So this is how you run C program， I'm telling everyone's done this， right。

 you compile a C program and you run it with dot slash。Okay， so I've now have some， you know。

 whatever the command line argument it is in the path variable。To use the open system call。

Here I'm going to open it up as read only， which you won't need to write files for this project。

And so I've just done a system call open what's the next thing I need to do？Air checking。

So if you are in any doubt about this function。Or the assistant call， you can check。

It's return values and it tells me， okay， negative one means。That。I've had an error。

So I need to write a condition， so what can I use to。What in this class。

 at least is the error handling strategy in this class？Print it out。

 so PR you can use to help you print it out， you can put whatever message really you want in there and that's going to read error number for you。

And then。Just exit， that's all you'll need to do for these。rokenIn these broken cases。Okay。

 so if I run。HereHere's my program， I open a file。And if I get an error。

I run the pre air command to print out the error。Otherwise， I pass that。

Call print F no air So for this。Execution here at the Fi program。

 what's going to be printed out by my program。Open air unless this file exists in my directory。

 which you've code of。Assume that it didn't， so this is what PR does for you。え。

Takes whatever message you put here。And then it gives you this nice。

Message that corresponds to error number。So in contrast， if I had。

Put a file that does exist like the file source code。

This does not get triggered because the return value is not negative one。Whatever you。Yeah。

It just gets printed out。s smell have there。嗯。Okay。So now that we have a file open。

 and so at the kernel level， each file is just assigned a number called open file is assigned a number called a file descriptor。

 that's why it's an integer， and so with that file descriptor in hand I can read from this file now that it's open。

So this is a little bit of。感觉す。Common style C coding。

I hope everyone who's done like array and buffers and reading。

 I think everyone should have this in intro to see。If you don't， let me know couple off hours。

 I can help go over some of this。But this is kind of pretty standard C。Making a character buffer。

 just an array of buff size， how many elements are in this？Oh， that's a typo， thanks， that's a typo。

And okay， and so here is my read system call read takes in a file descriptor。It takes in a buffer。

So it takes in a filescriptor， takes in a buffer。And it takes how many bytes you'd like to read。

Kind of different from like SKNF or other helper library functions here you have to be really。

 really precise about exactly what you want to read， you have to handle the buffo yourself。

So this is what the kernel provides you directly and probably why you learned FO and FFCC and F because that avoids having to manage a lot of this very precise management of file contents。

So how much should I read in？We don't want to overread our buffer or overwrite our buffer。

 so we'll read in。That much content。Okay， I've done a read command here。So what we need to do next。

 error checking， very good， we need to do error checking。

 so let me put it to do there to do error checking。But before I do that， let's run this。And okay so。

If I run this。And I didn't have this error handling。First of all。

Let me show you what happens if I don't have any hair handling at all and I just run open so this is I commented all this out and I just run open what do you think's going to happen？

Nothing happens。Its silent failure。So the colonel reported the error to you， but the kernel's like。

 okay， the developers got it。He handled it， but we didn't。

And so if I had failed to do this error handling。And then I went on。

And tried to read the file with this filescriptor。Now， what do you think is going to happen？

So let's look at the。Okay， I don't think this tells you。What a file yeah。

We have some error handling on the read function like。FD is not a valid file descriptor。

So as you correctly said， we're going to get some kind of error， but where。

 where is this error going to happen？So let's run this， so we've got open with no checking。

 and then we've got read with no checking。What's going to happen？It says no error。

So the colonel didn't care。That you didn't handle the errors， it's just going to go on。

 And then when you go to try to do the project。And you miss some bug。

 you're not going to get the right output。Because you got a silent error。

 it's going to look like you got the right air or right output， but yeah。是。So this one doesn't， okay。

 so let's do some error handling on read。To see see what the what the colonel said about this re command。

 So I gave。嗯。Sorry， so how do we。Let let me not do this code clo， let's do this from。

Let's do this by hand all right， so let's look at the return value for read。So on error。

 negative one is returned。So negative one equals， where's the return value of read？

It said bites good。And I am going to do a little coat on here because I。I'm lazy。

So let's just say we had anarrow on Re。All right， so what value is read getting for FD here？

In this execution of the program。It's getting negative one， yeah， whatever open was。

 and in this case here where I have a file that doesn't exist。It's negative one。

 So here I've got an error that I caught on the read command。But where's the error？

The air is not on the re command， right， the error was actually here on F open。

But without doing that air checking， your program are going to proceed as if nothing was wrong。

With values that you don't think really that you don't want for the rest of your program。

And so that' that's kind of the yeah， that's the critical thing here。

 so even if I had done no air checking at all。Nothing happens with my program。

 it has a zero exit code because it's us the developers that define what errors are in R。

Lux kernelnel did its job， it gave us the error messages， we just decided to ignore it。

And pretend that everything was okay to our user，No， no， it'll be whatever the last one。

 if you want to save all the errors， yeah， you can do that， but yes。

 and it's only set when the error happens。m， so if you try to read it again later or you can even。

 I don't know if it's constant， you might be able to write it。

 you could probably get your program to write it。But it's only set when the error happens。

So it's not， you know， if this error didn't happen， error number is not going to be set。

 it's going to be some stale value from a previous error。All right， so here is open and read。With。

Proper air handling。In both cases， so the air on the open is cut。But if I have a real file here。

No air， Reed had no error， open had no error。All right， questions on this， questions on this。

So this is just opening and reading a file， all these lines of code。

 to do it like correctly and safely。In the Linux world all right so let's print out。

Another difference between F open and。read。Is that？systemstem call works with bytes。

 it gives you the raw bytes of the file， it doesn't assume that it's a text file or anything like this like scanf and other features it just gives you bytes。

So if we want to。Write out these， we could。Just iterate over our little buffer here。呃。

Now we can assume their characters。Wwhichch might not be a safe assumption at all files。

 but this is the printf for has anyone seen the printf for characters anyone have to do this I'm not sure what like people have seen or not so you can you know ask me questions if you haven't seen stuff。

 but here。What's up。Okay。And that's a good question， so let's look at percent Ss， yeah。

 what do you think's going to happen？哎呀， what's your question。Yeah。

 percent3 will interpret it as a character， percent S will interpret it as a string。

 so what's the definition of a string in C？Noll terminated。Yeah， very good， null terminated。

There's nothing here that guarantees null termination we just read the first 10 bytes if available of our file。

 there's no null string there then yet。I。Oh yeah， thank you。 Yes， it should be off， thank you。

But here let me let's print out the string and see what mayhem it reaks so you can see here we got the kind of classic problem that you see if you don't have an null terminated string so it looks like there was an nu terminate at some point。

But yeah， this is not a string in the Cs。 This is just literally bytes。

 Strings are an interpretation of bytes that require that they're no terminated。

 characters are interpretation of bytes。That require that they ASI code， basically。Okay。

 so let's see what happens when we print out each character of this buffer。

 let me just print it out without。Your line。So here we get。The first 10 bytes of this file。

And indeed， if I look at the。The beginning of this file。Then yeah， these are the first 10 bytes。

Of the file。This includes stuff here。Questions on this？And then close， same deal。

 I'm going to do the little trick here where we run clothes。Inside of the if condition。

And same thing with close， although。Clos kind of matters less because。

L's Colel Man recommends you don't try to reclo or anything。

 so there's not much you can do if close fails。个就。Yeah， exactly right。 exactly right。 Yeah。

 this is like the beginnings of doing cat Now， dealing with Re is kind of annoying because you have to read them in。

😊，Predefined chunks， you have to say how much to read every time and so C standard libraries will do buffering for you and like make it easier to do that yeah。

How can clothes fail？呃。Let's see。Nothing to close， yeah。

 the file descriptionscript is invalid if you try to call close again。It got interrupted。

 so this is a big。U。Annoyance of dealing with Linux system calls technically。

 you may have to retry system calls actually， so these are all the air conditions so you can just read the manual and see what the air conditions for clothes are。

Yeah，我 the。Sp one。So one is a magic number， exit failure is like a Possic standard for whatever that code is。

 I actually don't know what exit failure is but。We can see what it is。So it is one， it is one。

 I guess， yeah， so you don't have to remember the number， you just use the code。All right。

 let me go over one more set of system calls。Let me go over director readinging because this one is critical for your。

For your project。All right， so we're going to start the same way。And there are。

Only a couple of command in need， just like with files you have open directory。

 read directory and closed directory and so these are actually not system calls。

 these are library calls， but the manual recommends that we don't do the actual system calls for these。

 but they're pretty they're still pretty low level， so let me just show you quickly how these。

How this works。There's a data structure， or actually there's a type called directory。

 when you open a directory under a given path， it gives you a pointer to this directory listing。

And so after we call a system call or even a library call， what do we need to do？Air handling。

So look at Emmamanuel in this case。If the pointer is null。

 it signals an error and we can use the same。Air handling approach that we have。

For pretty much everything in this class。And the way you can。

Look at what all the contacts of your directory are。Is to。Use。This。Read， dear。Function。

Readed Deer takes the pointer that you got from opening the directory。And every time you call it。

 it gives you the next entry。In the directory。Very。

 very low level you don't just have a nice array where you can look at everything。

 you just have to execute this instruction over and over and over。

And so the kind of C tricky way to do this。Is to run。Read directory in a loop。And print out。

Whatever information you want about this directory。 So this， this is all in the reading for tonight。

 I've given you the reading for。For this for tonight， it's all in the manual。嗯。Oh， it is working。

Oh sorry okay reading is here if you want to look at it so I can I'll go over this more next time since it looks like I'm running out of time to go in more detail。

 but you can also look at my examples online for doing this。And also。Look in the manual。

 so here's what happens when I。Run this program here。

 opens the directory and then iterates over each entry in the directory。

 I get a listing of all the files in my directory， including dot and dot。Were。Yeah。

 yeah exactly right， yeah， you just interviewly read each element of the directory， yeah。

Does order matter， no， order doesn matter， it'll be in directory entry order。

 which you can see with LS dash。All right， so I guess you guys decided class is over。

 so place is over， we'll finish up the last command next time。

 which is just file status that's pretty straightforward and all right everyone have a good day。

 let me turn off。

![](img/bd2a1c882db7724510a8cdd51f4cced9_15.png)