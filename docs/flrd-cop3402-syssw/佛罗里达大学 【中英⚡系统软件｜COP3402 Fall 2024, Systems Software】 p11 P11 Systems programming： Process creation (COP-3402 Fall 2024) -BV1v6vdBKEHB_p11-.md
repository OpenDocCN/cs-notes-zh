# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p11 P11 Systems programming： Process creation (COP-3402 Fall 2024) -BV1v6vdBKEHB_p11-

So'sSo welcome back to System Soware I'm recording now， let's get back into the class， so we're here。

In the middle of the system programming section， where we learn how to use our kernel。

 how to use the functions that it gives us， the system calls that it gives us in order to manipulate these kernel abstractions that abstract away the hardware so we can use the processor。

 we can use storage， we can use memory， all without having to know the details of the hardware。

 and with these more convenient abstractions。So last time we went over using the file system。

covered system calls。So what's the most important thing to remember about system calls whenever you make a system call？

Check for errors， make sure you do error checking， Air checking is up to you， the developer。

So make sure after every system call， you're checking it's air handling and how can you find documentation on？

The error return， like how do you figure out what to check for when there's an error yet？

Can you note in the manual， yeah， read the manual， RTFM， right， you can use the man command to read。

The manual so and what was this number in remember what this number was to the manual？Section number。

 so section two are the system calls， section three are the library calls open yeah open is one of the system calls that Colonel exposed to you。

 so the open for opening files。the return value and error section are the key parts to look at。Oh。

 so if you remember when we talked about the file system， the file。

 the notion of a file is an abstraction。Because it doesn't literally translate to bytes on disk。

It's an object that's maintained by the kernel that allows you to read and write bytes to it。

 and so you can certainly use a storage as the backing of that abstraction。

 but you could also use network IO or pipes， as we'll see that the file abstraction is just just like if you learned about abstract data types。

 you' learn about abstract data types。Nobody learned about ADTs CS1 yeah。

 CS1 ADDT that's direct data types right， so you can implement a list in multiple ways。

 you can use an array， you can use a linked list， a doubly linked list。

 lots of ways to implement a list。The list data structure is an abstract data structure。

 it doesn't include the details of how it's implemented。

 and so these file and process abstractions are much the same thing where the details of how they're implemented on disk or over an ethernet card。

You don't need to know that in order to actually use the abstraction and the kernel exposes this abstraction to you through its system calls。

Okay， so we learned about errors。We get the error number example。

Questions on the- so I went over the file example first where you're opening and reading。A file。

Questions on this example from last time， so we use the open command here。

 given a path to get ourselves。Poiner， so to speak of a file descriptor that refers to that open file。

 read to read bytes from it and close the tele kernel， we're not using file anymore。Right， yeah。

 so FO， so yeah， we talked about this a little last time。

 who can tell me the difference FO yeah FO opens a file。Well， so both open a file。

 so FO is in section three， of the main page。And it's the C library。Version of opening a file。

 and it gives you additional functionality， it gives you buffering。

 it gives you other features like using F print F， for instance。

 so you can use F print F which is not a system called， the kernel doesn't provide F print F。

But with FP and F， I can print a string， I can put formatting in that string。

 it'll do buffering for me。Mularloin doesn't do that， so with the open， so for instance， F scan F。

Or F get care， these give you characters， they give you formatting， they give you buffering。

 and under the hood， they're calling read。And all readed gives you is a way to read raw bitetes。

From the underlying。File。So F open is calling open and then open is calling the kernel。To do its job。

So you can think of this as a different file abstraction， a file abstraction as strings。

That have other features to them， whereas。The kernel file abstraction is just bytes。

 reading and writing bytes， I don't know， does that answer your question？Whoever asked it。

 wasn't over here？啊。All right， other questions on the file example。All right。

 let me review the myLS project the next project in the class。

 and so in this we're going to create our own version of LS。What does LS do？Yeah。

 list files in a directory。To make it a little less， you know。

 so you're not going to copy the LS command exactly。

 but I've given you special output that you should have for LS。And a specific format。So that， yeah。

 you'll be able to use various aspects of the file system abstraction。So at its core。

 it's going to list the contents of a different given directory， the usages here。

 so by convention when you see these brackets around an argument。

 so this is the program name that you're running。This is the argument。

 so how do you read arguments in a C file？Actually no。

 that's how you read from Standard In or from a file。Yeah， ArcV and ArcC。

 did you guys learn this in CS1 or intro they didn't teach about ArcV？Some people did a little bit。

 okay， so I have example code that I'll show you this， so for instance here。呃。

This is example code of using。AV。But that's how you read the command line arguments。

 they get passed by the C runtime as an argument to your main yeah。就是这后一。RC is like how many。

Exactly exactly exactly right， so AC is the number of arguments， ArgV is an array of strings。

 that's why it's a double pointer， so the care star is a string in C and so a pointer to a string in C would be care star star。

Do we put VIM？So this is not stat。 C， this is a different one， this is files。

And so the first argument A v0 is the name of the。The name of the program that you ran。

 it's whatever。The user passed as the first thing on the command line will be Arc。A zero。

 and then after that will be each of these space separated or white space separated。

And so if you want to like check so in this case I'm checking whether there are fewer than two arguments because if there's one argument。

 it means or if there's one ArgV。The first one is myLS。

So I'm checking whether there are at least two。So if there're more than two I don't read that and then here I'm taking the second argument remember C is base  zero。

 so I'm taking the second argument。Which is given here。So in your program。

 you'll have to check whether there is an argument first if there isn't an argument。

 so these brackets here mean optional arguments。So for instance， you look at LS。

This is just a convention in Muixs documentation that if there's brackets。

 it means that argument is optional。So file you don't have to provide a file to LS。

 what does it do if you type LS without giving an argument？Working directory exactly right。

 so it's the same thing here， the working directory if an easy way to get the working directory is use the dot。

Dictory， it's one of the benefits of having a dot directory is you can always refer to the working directory or the current directory without having to know its path。

 you can just use the dot directory。Okay， so myLS takes a directory or defaults to the working directory。

And it outputs。A list of every file in the directory， yeah。すれ可愛い。Yeah。Well， you just。

So it's past two men。いやいや。Yeah， yeah it's passedim made， so if you've ever wondered why。

ArcC and AV are here why you have to do that， that's what it's for it the。

Command line arguments being passed in， so you know this sea runtime that's kind of designed around this command line interface。

Okay， so the output is a list of all files in the directory。

 so the first column is the names so I've given a list of various columns of information that you'll provide for each file and all of this can be gathered from the system calls that I'm going to show you show you today so the name of the file。

The number of hard links to the file。 so that's the number of other references to that file and other directories。

 the type of file。The size of the file， if it's a directory， then give the number of entries。

 if it's a file， then give the size and bytes。And if it's a regular file that is just not a directory。

 not a device， then preview the first 16 characters and spit them out。

So this is designed to kind of get you comfortable with using the various system calls and using the documentation to figure out how to get each piece of the strut that's given to you all the data that's given to you back。

To make things a little easier， I've given you the exact format strengths to use for F printF。

 you could just use print F。For this， and these are the exact format strings to use for each of these。

 so that when we do grading， your output will be exactly what's expected。Yeah， standard output。

 standard output。Yeah。Well， standard out is a file， but yeah you can use printntf。

So this is what it looks like when you have the correct output， we have the name of each。

File in the directory here。The number of hard links。Pointing to that file， what type of file it is。

 so it's either a directory or a regular in this case。

Size of the directory that is a number of elements of the directory。Size and bytes of regular files。

 and then there's a little for regular files， there's a little preview。

Of the contents of these files。Yeah。Yeah。Type it just as string。Yeah。

 so here I have a little note here describing this。呃。These are described in the output contents。

And I have some example code today of how to do that， how to like yeah。

These are the string versions of the file type。But yeah， a good question。

 and there was another question。For these string literals。They're here。

 they're in the output contest。So there's a little note under this table saying， well。

 here's how you get。PRI， DmX， here's where you get the string literals。

Yeah hopefully that's sufficient。All right， so that's the。IO of the my LS tool， questions on that。

I'm sure you have a question on how to do it。Questions on the specification of the problem。Yeah。

I we point point that。ビI。Well that's just editing a file， then' Sta。c will'll open a file， but this。

 you can name the C file whatever you like， but the program should be called myS。ないでい。

But like it staff stuff， he fought around。Yes， Stats that C is where you'll get most of this information so okay。

 so let let me get into stat then if there's any other questions on the myLS project description。

Okay， so there's actually a program called Stat， which displays。

File metadata that's stored by the kernel for each file。So， let's look at， say。Ano。c。

So it gives you the name of the file， gives you the size in bytes， I think。

 number of blocks that it used on disk。And it gives you other metadata like how many hardlinks you have。

 permissions。Dates of when it was accessed modified， et cetera。嗯。

And so this is just a program that ask the kernel for file status and then print out that information。

To do this programmatically in our C program。There's a system call， so I just did man two stats。

 that system calls， there's a system call called Stat。Which if you give it a path。And。Yeah。

 a pointer to a stat buffer structure。 It will populate that structure with。A set of data。And。

So it populates that wherestruct。Here's the structure。Oh whoops， so I have a little mistaken here。

 so man3 staat will give you the data structure。Documentation of the stat buff data destruction。

 So this is。The names of all the fields in that stat data structure that's given to you by the stat system call。

So here's the。File type。And mode， here's the file type， here's the number of hard links。

Here's the size and bytes。And so this is where you're going to get most of the information from for this。

Output。What about the file name， so there's nothing here about the file name。

 where's the file name come from？where's the file name stored？

Remember the UniX style file system design。Or is the name of the file stored if it's not stored with。

The file metadata that the kernel returns for you， yeah。Yeah， exactly， it's the directory。

 the directory has the name and it points to an I number points to this unique identifier for the file。

 so the name itself。Is not stored with the file itself。

And part of the reason for that is you could have multiple file names。

 multiple paths pointing to the same file。Okay， so let me go over the stat， an example of the stat。

Data structure。Okay， so this program， just like before。Just like all the examples here。

 it reads in one argument。And。We don't even have to open the file， we can just call the stat。呃。

System call。Oh， yeah， sure。So here is a call to the stat system call。

We need to pass it pointer to astruct。To store the resulting data。

 the kernel is not going to create that data for you instead you pass it a pointer to thestruct。嗯。

To CS1 intro to C， they showed youstructs right， is they showed yous okays and pointers right learned about pointers so here I'm just initializing a new struct。

 the statbuff struct。And what does the Ampersand do？Yeah。

 pass by pass by reference gives the address of it so this is going to be a pointer to。

This stat buff struck。So the stat system call， you just give it the path。

To a file and you give it a pointer。To some stat data structure。

 to some struct that you already instantciated。And going you。

 it's going to populate this data structure。Thisstruct is going to be populated with all the information about that file that you asked for。

Questions areね， yeah。So basically， it's checking。Yeah， well， if the file doesn't exist， then yeah。

 it's going to return negative one so this is the。Stat system call。

Which if you look at the return value here， it returns negative one。If it fails， yeah。

So this is it if you do man3 stat。

![](img/9c783bfa599d70f3b992078431855fcf_1.png)

This is the structure definition。

![](img/9c783bfa599d70f3b992078431855fcf_3.png)

Well， the， the kernel will check whether that file exists。 So if the file exists。

 So if you look at the documentation of。The stat system call。

If it successfully gets the file' metadata， then it gives you returns zero。

 otherwise it returns negative one， so if the file doesn't exist or it doesn't successfully run。

 you can just quit， you don't have to。Give information about that file。That's right， yeah。

 well that's where it's defined， that's where the structure is defined。And yeah。

 you could look an that header file for the structure probably as well。

 but the manual page is probably the easiest place to look to get all of the fields。For this。

Man three stat。Well， so yeah， man two is the system call man3 is the structure。Second。Yeah。

 I'm actually not sure why， I guess because it's part of the map I guess it's part of the standard library。

 the C standard Library。Oh oh maybe that's uselessustace。Okay。

 I think that might be why I changed it。Okay， so it's actually in man， too in that。 Okay。

 so my local machine documentation is slightly。Different。Apparently， apparently we can。

 that's kind of surprising actually。So sorry about that， yeah， it's here under man two stat。On那。Yeah。

 I don't know， this is 2020。M's 2023， so maybe it's older documentation。

 they must have moved it around。Because my local machine is 2023 here。Apparently， yeah。But yeah。

 if you look I useace that data structure， so that's why I had changed it actually。嗯。Yeah。

 so that data structure is here。Yeah。Oh， so this is VI commands。

 so you can do J or K to scroll up or down or space。To do it。Or control the allP。

Orarrow keys should work too。All right， so that's the。Stat data structure。

 and here's examples of getting the information from thestruct。Coincidentally。

 the same information you're going to need for this My project。

So here I'm just printing out the number of。Hard links。That this file has。

 so this is ST underscore N link。Same for size， so I just get the。I'm going to use N three here。

 but so I just refer to the struck field in order get that to get that data。

So there's size and there's end link。Qu신 전에ね。Yeah。Yeah， exactly， exactly。Yeah， yeah。Yeah。

 for most of them， for most of them， so one is the name。Most of them are hard links。

 once you get to the last two fields it's a little trickier because for directories I've asked you to give the number of files in the directory rather than the size of the file。

 the directory file， and for regular files I've asked you to give a preview of the file。

 so that means you're going to have to open and read the contents of the file。Sure， yeah。

You give stat， and then。A path， a string that holds the path。And then a pointer to a stat struct。

So this is。How you call， and so I've set the string here and the C a data structure here。

And so I just caused that。Other questions on this？So I'd recommend actually like hand typing out these examples。

 it's going to be tough to both write myLs from scratch and also tough if you just do try to do cut and paste that's called cargoult program it's going to be hard to do either way。

 so I'd recommend。Walking through these examples and maybe hand typing them so you kind of get the feel of how to use these system calls。

And then sitting down and trying to pull these several system calls together to make the myS。Project。

Just as a hint。I gave you the。Code that gets you basically gets you started on myLS， it reads。

 opens a directory and lists all the files in that directory so if remember from last time。

You call open Deer。Which gives you a pointer to a directory entry。And then you just loop over。

You just repeatedly call read Deer with that directory entry pointer。

In order to iterate over each element of the directory， each entry in the directory。

And then the only field you're going to-， I think one of the fields you need from that data structure is called D。

So this is this I showed this last time， but this was all documented in。Think can open dear。

This is described in the project。Yeah， so this is。This is described in these man pages。

The system calls。Okay， so that's the myLs project， Other questions。On the project。

 the system calls yeah。套菜。Yeah， yeah， this is this is it。

 so this is how you you'll loop over all the。Ellen， all the files in a directory。

So I didn't specify any order， it'll be the order of the the under that the kernelel has stored the file entries。

 so they'll be an ordering there ordering。Should it matter？I mean。

 if you get a bad grade because of that， then let me know。

 but I'm going to tell the grader that order shouldn't matter。This is際。Do you want like。

I was or used。What do you mean， use them own？Yeah。To meet the specifications of the assignment。ストはい。

All staff were just use。Oh no， well， it's the same thing， I mean， the code and stat。c。

Shows an example of using。The stat call， So I've basically given you like examples that are going to be very relevant to。

 you know that you can you can draw from。To write the myS program。Yeah。I mean。

 if so it's not the complete project， if you just copy and paste it， it won't work。

You'll have to put things together。Arrangenge things together so that the mys project works so these are just examples of using each of these system calls。

 So I've given you like an example somewhere of using these system calls。

 but when you go to write your program you'll have to。Write the algorithm that creates this output。

And to do that， you'll need all of these system calls。And so I haven't given you the exact results。

 but I've given you examples of using the system call so that you can use them in your algorithm at the right place。

 if that makes sense。Yeah。We want。Exactly， yeah， so I've given you。

 and I'll post other public test cases， my grading staff has created some more test cases。

 but I've given you one example and you can download and run。

Your myLs on this example to see if you get the output。So I've already given you。 so this is。

You knowThe good way to do development where you have some ground truth。

 you have some output that you want， and then as you do development， you can check。

 you can test to make sure that your program works the way it's supposed to so these set of commands I think you've used W you get already in this class。

 right？Yeah， oh for this。Well， it'll。It'll expand into new directory so I can show you what this looks like just。

CallW downloads it and then you ontar it。So that's expanding expanding it。

 and so then we get this myLS example folder。And it contains。Some subdirecty。You can use L S to。

Look at it， which I actually just did。And then run your tool on。That folder， that example folder。

 and this is what the output should look like when you run your tool。Modulular ordering differences。

 but otherwise yeah。Right right I mean these should be in the first column so this is going to be the directory entry order that the kernelel represents the directory and if you unpack it it's very likely that this。

This ordering should match the order that they were added to the file system。

So at least for our examples， if you untar them。The order should match。

 I don't see why they wouldn't， if you've modified them by hand， they may or moved them around。

 they may not， but the order should match， but not going to grade you if they're ordering differences。

Yeah。Yeah， this this will， yeah， so I'm using tabs here to make these tabs separated。

 that's why they're all nicely lined up。嗯。And so for instance。

 this is limiting the name of the file to 16 characters。呃。Yeah。

 so if you just use these format strings to print out the data in each of the columns。

 get you'll get this output。All right， another questions on myLS。

 so try it out you have all the system calls available。Try it out， start small。

 start with just listing the entries in the directory。

 which I've already given an example of doing that， and then try， for instance， stat and say。

 all right， can I get this metadata， and it doesn't have to be for metadata just see if you can use the command correctly。

And then， you know， the next step is， okay， can you get the size of a directory。

 number of entries of directory， and then finally， can you get the。

Open and read the file to get the preview。And then once you have that。

 you can just double check against our test cases to make sure your format strings are right。

 make sure you have no bugs。Makes sense。Yeah。せする。So spacing will be sensitive， but these， yeah。

 the grading scripts I'll ask them to do exact spacing， but if you use these format strings。

 the spacing will be right because this has the。Tab character inside of it。

 so that's why it's lined up like this that the T character is ensuring that spacing works the way you expect。

Yeah。Aha， that's a good question。😊，So you'll have to make sure。

That you print out only the first 16 bytes。Of the file。So just as a little hint as to。

How that you can achieve that， remember that the RE command。

Or the read system call requires you to give the number of fighttes you'd like to read。All right。

 other questions on ILS？So you got a couple weeks for this one or like a week and a half， but yeah。

 let me know if you have issues， confusion， ask on E STM， come to office hours。

I hope it's not too bad， I think once you do it， it's not going to be that bad。

 the trickiest part is just the conventions of the system cis calls。

 but use the main pages to keep track of the fields。And what the return value should be。

 otherwise the algorithm from an algorithm point of view， it's not that that bad， you know。

 just have a loop。And you have several printf statements for each of these fields。

And one little wrinkle is getting the number of elements of the directory。

 you'll have to open that directory and read it again。

 but otherwise from an algorithmic point of view， it's pretty straightforward it's just putting together all of the system calls。

 which makes this more complicated。2。So let's move on to processes。

 so this and the next two lectures will prepare us for the next。Homework assignment。

 which is writing a little command line shell interpreter。嗯。So I'll go over that next week。

But in order to do that， we'll have to learn how to manage processes。

So we learned about managing the file system using system calls。

And so today we're going to learn about how we manage processes。So recall that process。

 so what our processes is in the UniX world？一 sir收到你系啦边。Perect well， okay， so the're programs。Okay。

 very good。 a running program。 so I can have a program on disk like this。Fileles program。

And you know， it's just a bunch of。Binary data。But a process is a running program per that's currently running。

 And why， you know， why can't we just run the program。

 We could just tell the CPU jump to this line of code and memory and just run it。

 Why bother having the kernel have manage some。Fancy process abstraction。

 why don't just tell the kernel to start running this yeah。やスタト。Exactly。

 so if we have a machine that's only one got to ever run one program。

 you know we could make a special purpose machine that does that maybe like a refrigerator or something。

 but if we want to have time sharing if we have，Fewer resources or limited resources。

Then what the kernel can do for us is it can share these resources and one of those resources is the CPU。

And usually， I mean， even today， few machines have more than one or a few processors。

 at least for commodity commercial stuff。But you may have lots and lots of programs that you want to run at the same time。

And rather than having to design a system where you sort of do custom transfers between these different running programs。

 the kernel provides you this general purpose abstraction on parent process。

 and you can just tell the kernel， here's all the processes I want to run at any time you'd like。

 you can end and start these processes whenever you want。

 and it will handle actually starting and stopping these on the processor for you。

In the best way that it thinks is possible， though there's all sorts of research on scheduling algorithms to decide when to switch between processes。

 when to prioritize certain processes。But you can just kind of trust your kernel in most of your probably common workloads to give you the impression that all these programs are running at the same time。

 so if you're on like a laptop right now and you have a browser open and your mail and whatever video game you're playing or YouTube videos there's dozens of processes involved in all of those and you have the feeling that they're all running at the same time when in reality。

 they're sharing a single or a few course。On your machine and the kernel is just switching very。

 very rapidly between running all these programs。Okay， so that's the process abstraction。

 that's why it's useful。So let's see how we actually。Use the process abstraction。

Making a new process， making a new running program is pretty straightforward to make a new process you just call Fork。

And that will duplicate an existing process。And then when you want to have that process run a new program。

 you call exec。And it's really just two system calls in order to get a new running program on a Uni system。

So if you read the。If you read the reading from last time for the homework。

This is a diagram of what this process looks like。So this assumes that you've got an already running process。

 so why is it that we can so if processes are only created from other processes。

How can we be sure that we'll have a process to fork on a Uni system？Yeah， it's exactly right。

 during during including， exactly what you said， the init process。

Is created and run when you boot the machine so and user space don't have any control over that。

 but as soon as you boot the system and log in there's already processes running。

And through other aspects of the system。Logging in creates the bash process for you。

 creates this running dash process when you run Bash and you execute a program。

 Bash is the parent process that you're forking from and so Bash will call ForRC for LS or whatever program you're running。

And so given the process that's already running， you call fork。

And now there are two processes already。And these two processes are virtually duplicates of each other。

 they have the same running program， same files， same memory， at least when it starts。

And so you have two versions of the same running program doesn't seem very useful， right。

 like now there's two versions of the same program。So。Okay， let me get to it， all right。

 so this is how Fork works， it duplicates the program just to review the homework from last time。嗯。

The Homer question。Was。Let me get the exact homework question。So。

 when you have a fork and make a new process， what happens to the open files in that process？

If you remember from your reading。Yeah。They're duplicated， yeah。

 so this diagram shows it where if we have two open files。

 so descriptors are a number assigned to each of your open files in a process。When we do a fork。

 the child inherits or duplicates all the open files。

 so you actually have two processes with the same file open at the same time。

 so if both right to that file， they're both going to be able to add context to that file now as the book points out that may be undesirable because you're。

The data that you're printing out may be mixed up between the two。Yeah， got it well， yeah， yeah。

Kind of like yeah， yeah， so you know you can do locking or other communication to avoid that。

And then here's a case of closing some of the file descriptors so that the parent and the child are now pointing to different files。

But so everything is duplicated。When you call fork， basically。Okay， so the question though， is。

 if Fork duplicates process， how do we avoid both， just doing build processes just doing the exact same thing？

So what would they in the book get？Well， so that's so if they're the same running program。

How will you know to pause the parent versus the child。

 so if you just call fork and then sleep or wait or something？Do you remember in the book？I mean。

 do you remember the book what they said to， so how do you- so when you do Fork。

 you have literally the same running program， so you write one C program， you call Fork。

And now there's two copies of that program running。

 and so they're going to have the exact same sequence of instructions if you don't do anything else。

 yeah。Exactly， that's right。 So the trick is， is that。

Where you can detect a difference between the two processes is that the return value of fork cleverly returns something different depending on whether it's the parent or the child。

So if this didn't happen， you thered be no way to tell the difference whether。

 if you were writing the program， you'd have no signal to tell you， I'm the parent。

Process versus on the child process。So the way around this is the forRC function forRC Cisco call returns two different values depending on whether you're the parent or the child。

So if you're the parent， the process ID of the child is returned。If you're the child。

 the zero is returned and then of course， negative one if work fails。So that's the main trick。

 so let me get into actually coding this。All right， so let's give ourselves。A little template here。

All right， so these as before these， I' give you all the header files and that you need for all of these system calls so you can just look in my example code。

So the trick is we want to save the PID and there's like a special data type for the PID。

 although it ultimately is a number。And so the one thing we can do is we can use a switch statement or you can use a conditional statement。

When we。Fork。We can check。Whether the return value。So if you want to be very clever。

 you can call the fork inside of the switch statement or inside of the if statement。

And then check all of the cases。So if it's a negative one， we have an error。If it's zero。

 then what does it tell us if fork returns zero？We're in the child， so we're in the child here。

And then finally， if it's anything else。So。If it's anything else， then we know we're in the parent。

So even though we have a single program that we've written。

Now we have a way to distinguish child and parent and we can。Effectively。

 we have two different programs running， even though it really is the same program。

 we now have two different traces of code running inside the parent and the child。Okay， so let me。

Let me actually turn these into print statements。So， we can see。What happened？Okay， so that's。

So let's actually run this program， so I'm going to run this program here I forked。And。

You can see that even though there's a switch statement here。

 there's no way two branches of a switch statement could run， at least if few have break statements。

And so you can see that both these lines inside the parent and inside the child。Are being run。Yeah。

 so for we've now created two processes， actually， let me add a little extra code here。2。

So I'm going to sleep。Both of these processes。And then。Let me actually print out the。

Child idea as well。Okay， so。呃。So I've paused this program。And you can see。

That there are actually two processes， so Fork is the name of my program。

And there are actually two processes here。Be are running。So without this fork command。If I adjust。

Donn sleep。这。Not quit， so let me just comment out the fork。And。So now this program is still running。

Here I have one process。From this running， one process from this program， sorry。

 this program started running。 I have one process， yeah。Yeah， it， it's seconds。

 so you can always look at the， that's the command。Yeah， that's a number of seconds。

So I would would this is just to illustrate that there are actually two。Processess running。

So here now when I run Fork I've now have。My for command。And the child is sleeping for 10 seconds。

 The parent's sleeping for 10 seconds。 So I a run fork。

Both the parent and child have their printF statements， so literally when I ran Fork。

The entire running process is duplicated， all of its code， all its files。

 and so there are two running programs and without doing anything else。

 they'll both continue to run until the end， so both are， but because I did this case statement。

 there's different lines of code that are being executed by the parent and the child。

And so we can see that， oh， I have some existing processes running。Let me run these again。

And so we can see using the PS command to show us the running processes。

That indeed I have actually created a new process。So there are actually two running processes。

Now these two processes are technically the same program， right。

 because I only wrote a single program。I call fork in it to create a new process。

 but both of them are the fork。Command， they're both。Technically the same program。

 those two programs do different things depending on whether child or parent。

But it's the same program being run。So questions， questions on this。Yeah。Oh makeg fork。

 that's just when I run fork。Here。Or here。In the terminal， I'm just running this program on the left。

So this is a C program on the left that I called Fork。Maybe that's not a great name。

Maybe that's not a great name for it， but I have a program called Fork fork。c。And oh。

 so I have a little， I'm using a make file to build it， but I'm just compiling the program。Call fork。

 I could call it anything I want， for for example。And I'm just running it。

So you can see there's two copies of this program running， two processes of it running。

Other questions on it， yeah。Yeah， that's a good question。Don't think it has to be。It's probably just。

Because the I don't know， I would just to throw a wild guess， I'm guessing that。

That process already running， there's probably a little lag in creating the new process so the scheduler just so happens to continue running the parent or maybe there's even a sing decision I don't actually know。

 but I don't think it's necessarily guaranteed by the system。ここいで。Oh， so this is。

So this switch statement is doing it。So we could also have written this to make this。

 maybe maybe I should make this a little less seed like here。So we could have written it like this。

Or I just say if。Zero equals PID。Then I'm inside the child， maybe there's a little less esoteric。

And I could have written it like this。Or I could say something like if。PID is greater than zero then。

Inside the parent。Could also have written like this。The book。

 the Linux programminging interface uses this kind of clever switch statements。

 switch statements can be。More efficient。辩论。And yeah， it can be more efficient。Yeah， that's right。

 it's the test of PID。For For is giving you the PID and depending on whether you're in the parent process or the child process。

 that number is going to be different， that return value is going to be different so。

Even though it's the same running program， there's a program value that differs between the and so you can give the impression that there's two different running programs。

 but really it's just a different path through the program。見てるね。Yeah。Where does what？They okay。

 so they're literally duplicating all the state including the position in the program that you're running。

 so as soon as Fork is called yeah good。Exactly yeah， so the program counter is also copied。

 the program counters the position in the program that's being run in the processor。

And so as soon as you're on fork。As soon as the return， I。

I don't know exactly when it happens before the return or after the return。

 but a new process created and the same program counter， the same position。

 probably the position right after fork。Is for both processes and so like here or this test。

So both the processes are going to run this test here， but because PID is different。

Only the parent process is going to say true on this or I sorry。

 only the child process only it's going to say true。On this。こい。Yeah， exactly， exactly， yeah， yeah。

Yeah。Well， I mean it looks like that's what's happening。

 so somebody else asked this that it seems like the parent child is running first。

 I don't think there's any guarantee of that， I think that just naturally falls out of the implementation of like the schedule because I think the I don't know that's my suspicion。

But I don't actually know， I don't think it's guaranteed to run first。

Oh that's a very good question we'll look at that next time process communication there are several methods for process communication like map memory pipes。

 you can use the file system to do it as well sockets so actually。

One way to think of internet sockets， when you have two。

 you're going into your browser and asking a website for their browser。

 you can actually just think of it as two running processes that don't know or care where they're running。

But they've opened up some IO between them。And so actually the API for having network communication is very。

 very similar to like file IO， and in fact， there were competing standards for doing network communication。

 the UniIX people wanted file style sockets， and they actually still have sockets on UniX。Yeah。

 same same idea， these are really just files that you open that you can read and write bytes from between two different processes。

 it's a type of inter process communication， so you're literally just communicating between two processes on different machines with TCP or IP。

But yeah， it's a good question， how do you do process communication and we'll look at that technique next time。

Or we'll use pipes to communicate between two different processes in order to。

Implement pipes that we use in D。最初はいける。Yeah， exactly， yeah。Actually no。

 they don't yeah so we'll see it next time but the way it works is that pipes are just files and you write to one file and you can read so you write to the pipe and anyone who can read the pipe will see whatever's written there so they don't necessarily have to terminate。

To finish just like in a program， you can write to files as much as you like， you can open a file。

 write a few bytes， do some other computation， write more bytes。It like an alternative。

Actually we'll use standard out to do it， we'll use standard out to do this。

 but yeah we'll see that next time how that works but yeah how do you communicate with new processes yeah there's all sorts of ways to do this one is memory mapping。

 you can have shared memory between them， you can use files to do it including pipes you can use sockets those are some of the main ways I don't know if there's other ways there's also signals they talk about in the book but I didn't cover that for this class。

All right， questions on forking。Yeah。啊。That's a great question why so if you just do fork。

 if you ever want to have any multipro， you're going to have to write just like one giant program and like。

But fork， if you want to actually create a new running program with that's a different program。

 fork is paired with exec。So let me go back to the。Diagram here。

So at least what we're going to use it for and what fork is。

I guess typically or at least conventionally used for is that you fork a new process。

And then so that you can have a different program running， you call Zec on the child。

And that will replace the current processes running program with a new program and start running that program。

So is this is the two step process to getting a new running program on your UniX machine。

 you call Fork first to make a new process， but that's the same program。

 it just duplicates that program and then you call exec and exec just overrites。

The current processes program or text segment。With a new one and then starts running that。All right。

 so that's a good segue into。Execec， so let's look at exec first。I've have a。呃。

Simple version of exec here， so independently of ForRC。

 you can always call exec to replace your current running program。So let me again set this up。

Give myself a main method。O。So there's a whole bunch of different variations of exec。

 and I think I asked this as a homework question。But for now， we're going to use this。Exec VE。呃。

Version。So just to show you the documentation。There's lots of different variations of it。

 I think the book goes into。Some of the detail on it。嗯。

But it's not really important for our purposes， all of them will replace the current running processes program with a new program found at that path。

So all of them take a path。To a file， and that file contains the text of a program or the binary of a program。

And then there are， you know there are other。There are other parameters to this。

 so this is where AGV comes from AGV is passed to the system via the Exec command。

And in this version of it， we also passed the environment。

 so if you remember environment variables where like path and stuff is stored。

So when Bsh creates a new program， it actually passes in RV to the system and then the system and the runtime eventually hand that down to main for your RV。

 So this is kind of where RV comes from， But for now， let's ignore those。And just look at the。

Program， so here we're going to take our program， which we wrote so let me。Puts some。Text here。

So did you believe that I？变。Ex example。And when I run this program。

 it's going to print out my own exact example， and then it's kind of called the Exec system call passing in userr bin LS。

 so what's Use bin LS？Yeah， this is the full path to the LS command。

 this is actually where the LS program is stored on our system。

And just to kind of illustrate something else here。Oh， yeah， sorry。Okay。

 so my program will print out。The text my own exact example。And it will call exec passing in。

User bin LS， which is the path to the LS program。And then afterwards。

 I'm going to print out the end of my thing。Okay， so here is my。やらせる。Here I compiled it。

That's one exec。All right。So I didn't print out any of my printF statements。

Because when I I blew away， I blew away the print F buffer。So it should if I do this。嗯。

So it getting into the weeds a little bit on how。The standard IO works。

 but here just to convince you that I actually was running my own program。Here's the text。

 my own exact example。And then when I run exec。For LS。LS runs， right。

 this is what the output of LS is。And I think I could even， oh， should I？



![](img/9c783bfa599d70f3b992078431855fcf_5.png)

Try to do something like this or I give it a command line argument。

 I don't know if that's going to work。Now。All right， it's the second one。



![](img/9c783bfa599d70f3b992078431855fcf_7.png)

So I think I can even pass it。Oh， that brought， let's let's not do that。But anyway。

 you can see that the LS program is being executed now。But my second print statement here。

Even if I use this flush， then you can see that the end of my exact example is not being executed why。

Yeah。Yeah， well， okay， so that's sort of on the right track。So we're in the same process。

 so the process has not changed so if I put a。Sleep here。呃。

So let me use find here as an example because find takes a really long time to run。

So let me pause it for real quick， so this is my process ID。Here。One，3， six， four， four nine。

Let me do。Let me do this in。上。Long running directory。So here's my process ID， 136479。

And here's a really long running command， find。It's the same process ID。Actually。

 it changed the name of it， it's the same process idea。So I haven't changed any process here。

 this is all the same process。😡，All exec does is mess with。actually the memory of the process。

 and specifically the text segment， where the set of binary instructions， your machine code lives。

So all Exec does is it takes the same process and it just replaces。The program text。

 the program binary。In the process and then just starts running。code。Yeah。Yeah， so let's see if they。

No， it doesn't no， it it opens the file and then copies that binary code into the text segment of your running process。

Is it weird？So by itself， it's like why do I mean， there could be reasons why you'd want to do this。

 you know， you may have a program， a helper program that manages running other programs and you don't actually want to come back。

To your program， so the consequence of this is that exec never returns。Exec never returns。

Unless there's an error。Exactly， so very insightful， so if you use Fork and Exec together。

 you get both a new process and a new running program。

So four can Exec together give you a new running program。

And so they're decoupled the same way that a lot of this kind of low level programming is。

 it gives you a lot of flexibility， so there may be cases where you want to fork， for instance。

 if you have a web server。You actually may not want another running program。

 you want to have one program and do some multi processing。No， no， exact creates no new process。

 it's the same process。So just like here with this， when I exact find。

The process idea is exactly the same as it was when I first ran a program。

 so just to show you this again。So this is。The Exec program 137-570， so this is inside the sleep。

And when I continue running this。It exactecs find。And it's the same process ID。

So if the process contains in memory， it contains the binary of your program。

So the way what a running program is is when the system runs a program， it loads the program。

It copies the binary code into memory。And then tells the CPU， okay。

 start at the beginning of this program and start running。

And so what exec does is it takes the process， which is independent of the running program。

 it's the abstraction in the kernel， and it replaces that section in memory with a different set of binary instructions taken read from that file。

That's why so for creates the process， exec changes the running program。

So if a process is a running program。Then the program part is that sequence of binary code that you have stored on desk and not you compile。

And the process just has a place and memory where it stores that。Binary code。So I think there's。

Let me show another。Diagram。Okay， so this is。From the Linux programming interface， this is chapter 6。

 I dont't think I had you read this but。Probably in computer organization。

 did you learn about the stack and the heap and memory layout？So in memory。

 there's the stack in a heap。And there's also the tech segment。

 so that's where the program is stored。Historically， it's called the text segment。

 even though it's machine code， it's not like ASI text。And so when you call Zec。

One of the things it does is it replaces the binary code in this segment。

And then starts running from the beginning of that tech segment。So yeah。

 so exec doesn't create a process fork does， but Fork doesn't change what program you're running。

 it just duplicates exactly the same program， and so to have a new running program。

 you call Fork to make a new process and then exec to change what program is running。Yeah。ごじ。Exactly。

 that's why it's not running because， yes， exactly right。

 that's why the last print statement doesn't run。Because so if you look at the man page for exec。

So exec only returns if there was an error， so it's ci call so you have to check。

 you you got to check whether it had an error。If it doesn't， if there was no error。

 then this function never returns。So whatever code you have after that is all that code。

Exec is not supposed to return。Well， it's like you've called the function and that function's running。

 but that function is never going to return to you。Yeah。Yeah。So even if you have that。

 this program is never going to be returned to because you've swapped out the program text。

So this printf statement is after I call exec。This process doesn't even have the binary instructions to run Princes。

It's gone effectively。So yeah， exec is like one way。

 once you replace your process with the learninging program。

 that program is obliterate your previous program is gone， it's never going to be returned to。

So now you could have multiple processes， so this is where process communication comes in。

 if you do want to have two processes running， but you want to have them coordinate in some way。

 know you want to signal one process， hey， I'm done with this task， let me run。

There are other techniques for doing that， there's inner process communication for doing that。

But this is just for creating a new running program。That's what exec is for。All right， questions。

 questions on this。All right， I think I actually finished it in time I think this is all that I wanted to cover so all right。

 thanks everyone， see you next week。

![](img/9c783bfa599d70f3b992078431855fcf_9.png)