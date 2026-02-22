# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p16 16 I_O.zh_en -BV17jcReyETC_p16-

个出施言。

![](img/8530f17059e7fbf7c64f073d1939349c_1.png)

系要系。

![](img/8530f17059e7fbf7c64f073d1939349c_3.png)

老死，对。Okay， I expect a lot of people are trying to take a break and doing the exam。

 which is fine and hopefully'll pick up this lecture。I had some other time on the video。啊So。

Last time I didn't get through all the signals and what I plan to do since I don't want to keep falling behind is I'm going to cover today's lecture first。

 make sure that's done and then go back and cover just a little piece of signals that's pretty important for you to know。

In order to do this upcoming wayup， which will be available to you starting tomorrow。

So the topic today is on input and output and particularly understanding the sort of low level or system level aspect of it。

 and this is material that is sort of of general interest。

 but it's of particular interest you'll be using it a little bit in your upcoming lab you'll have to understand some of these aspects。

And then toward the end of the term， when you do your final assignment。

 you're going to have to understand it too。But between those two times you're going to forget it all so what I'm going to try and do is just plant enough seeds in your head so you'll remember toward the end of the term a few keywords that you can use to retrieve and look and write parts of the book。

And we're going to cover various aspects of IO first is sort of the low level perspective of the operating system or UniX IO。

And a little bit about how。The system supports multiple。

I O files and how it can share files and things。 how it handles redirection when you put a greater than or less end sign on your command line。

 how that's implemented， which will be very relevant to your shell web。And。

We'll also talk about standard IO， which is the type you're more familiar with when you say printf F printntf。

 scanf， those are standard IO， and that's what he normally use。

 we'll talk about how that's layered on top of UniX IO。

 and then we'll talk about a package that was written for this class and for the textbook that you're going to really want to use in your final assignment so if you just remember the keyword RIO or Rio。

 that'll be a good trigger point。So as I mentioned you're probably more familiar with。

What's called standard IO， and you know when you say pound include standard STDo。h。

You're gaining access to that library of functions， and that's what's used for 99。

9% of all application programmers programs when they're reading and writing data。

But there is a lower level set of operations that you can do， what it's called sometimes raw IO。

Where you're really down at the operating system， exactly how it represents files and manipulates。

And there's various times when that's useful to be able to do that directly。

And then what we're going to add to this mix is yet another set of IO library that's specific for this book that's again layered on top of the UniX IO。

 and it's incompatible。With the standard IO， So basically for any given connection you want to make。

 you have to choose which of these various flavors you're going to use and you can't really mix and match them very well。

So what we'll do is go through what these three are and why they exist in different forms and what are their compatibilities and incompatibilities。

So in EX， EX， if you remember， was started at Bell Labs in the 70s and is really the。Basis of Linux。

 the operating system。 So we'll use the term Muix and Linux interchangeable here。

But UniX has a very simple view of files， which is just a sequence of bytes。And in fact。

 UniX uses this concept of a file for a lot of things。

 not just for data that you're storing in a directory somewhere。

 it uses all the IO devices are viewed as files large parts of the operating system are represented as files。

 and。And one of the interesting things is it sort of creates a common frame to reference and one of the important ones that we'll get into later。

Is。When you sending messages over a network。or reading messages back from a network connection。

 those are actually represented as a file so that you're right in order to send something over a network connection and you read to receive something and so that's why this idea of a file gets provided in a very general form and there's a lot of different aspects to that。

So at any given time then the set of operations you can do with files in this lowest level is pretty small。

 you can open a file， you can close it， you can read from it and you can write to it and what it means to reader or write is at any given time。

for an open file， there is a concept of its current position， which is where within this by sequence。

Is the it's like a pointer and when you read。It'll start reading from that position。 If you write。

 it will start writing to that position， possibly overriding values that are already there。

 Or if you're at the end of the file， you'll be appending new values on this sequence。

And there's a function called seek，' the lowest version is called L See that lets you set the position。

So one of the weird things is that makes sense in some places， but not in another。 So， for example。

 if you have a sort of standard file at some。Text file on a， on a disk。

Then seeking is a convenient way to be able to sort of move back and forth in there。

But another thing that's represented as a file is standard input。And。No matter how hard you try。

 you can't really go backwards very far on a。Terminal you can't actually you can go back a little bit or no not on a raw file sorry。

 you can't go back into the paths that's just not what our current computers are set to do。

So some of these capabilities， whether they are actually possible or not depends on which type of file you're dealing with。

 but at least in principle， there's this idea of the current file position as think of it as an index into this light sequence。

So the UniX really only thinks of there being about half a dozen different types of files。

 One is a regular file， which is。As you can imagine， just what it says。

 another is a directory is a special cap type of file that contains information about other files。

And a socket is how we talk about network connection。So a socket is like the it's actually half。

The network connection from one side of that connection， and then at the remote site。

 there's another socket。And I start writing to my socket。And at the other end。

 the process will read from its socket and lo and behold the stuff I sent will be。

Provided into the remote process and same going back the other direction。So a socket is a file。

 but it's a very special type of file for network connections。

And there's other files that we won't really talk about， pipes。

 if you've ever used the vertical bar for linking two programs together that's called a pipe。

We're not going to really talk about pipes， there's something called a symbolic link which is a way you can create an alias for a file and the various other things that are interesting but not really part of the discussion today。

So and we'll mostly look at just regular files。Soockets will come later in the term when we start talking about networking and as I mentioned that will be relevant to。

S me your later assignments。So for regular files， often， as I said。

 UniX does not have any idea of file types， it doesn't know that this is a word document or PowerPoint or that it contains a MG。

 you know the things that you see as little dot blah， blah。

 blas in your file name extensions are completely unknown to。To the operating system。

 in the case of Linux， it's different for Microsoft。Some other operating system。And。

But often we think about there being a distinction between text files and binary files。

And particular text files， especially with ASI or just the eight bit characters are common。

 but you also probably have dealt with UniIcode files， which lets you。

Encode the characters of other languages。But like I said。

 the operating system doesn't really know that， but one thing you've probably had to deal with is in a text file。

 there are different ways to terminate the end of a line。And so in a UniX file system。

Every line is terminated with the character that has hex code A。And it's called a line feed。

If you've ever dealt with windows。And you'll also discover this with some of the internet protocols and every line ends with a carriage return followed by a line fee。

So I thought just for those of you who are。Of your generation。

Probably never put your hands on a typewriter right a real manual typewriter， you know。

 they go click， quick， quick， quick， click king you ever heard that or king So Kaing was you would。

Actually， this is electric typewriter。Theing is you grab this little bar at the right end of the thing and you。

Push it over that way， so that was the carriage return。And then linefe was， as you did that。

 it would go jink like this， the roller， it's called a platin。

Go jink for one line so that then I'd start typing the next line Actually， no。

 I'm sorry it is if you think about you want to。In English。

you want to slam this thing to the right and now you start typing from the left to the right and the goose goes over so if you ever wonder what's a carriage return。

 what's a line feed， those refer to terminology that is totally obsolete。But anyways。

 you've probably encountered this， it's really annoying to transfer files between。

Different operating systems， depending on whether they use just a line feed or a carriage return line feed。

 that's a bit of an aside that that's all text files and like I said。

 the operating system really has no concept of any of that stuff。

 that's all application layer things。And a directory， as I mentioned， is it's treated as a file。

 but it's a special file that the operating system understands that contains entries about all the files that are within that directory。

And as you know， in UniX， there's always at least two files in every directory that can be accessed。

 one is dot， which is the local directory， and dot dot is linked to the parent directory。

And you've seen the standard commands for dealing with directories。

So one thing again that you've experienced is that in UniX and actually most file systems。

 including windows and so forth， theres a sort of it's viewed as a tree representation of all the files in the system where the route is just labeled as slash and then you can access various subdirecties and so you'll typically have a home directory and you can build and manage the directories that are within it。

 but there's other ones that are maintained by the operating system with various types of information where。

Code is where the IO devices are， some of the system configuration information。And things like that。

And so there actually technically should be a distinction in。Euns。

 when you say a file name is just the name of。Just the short name of a file。If you want to。

 so a lot of times when you use the term file name， we really need path name。

 which is some indication of。Where this file is， and that can be either in absolute terms using the slash as your starting point to give a complete path。

 or it can be a relative one using the dot or dot dot notation。So the simplest beginning then of a。

A file is to open it。And this is using the low level。Operation， so this is the UniX IO。

 you can open a file， you give its path name， and then you give a set of flags。

That talk about something about the nature of this opening。

And that you'll find it has a whole set of possible。A predefined constants to define it。

 so to say oh underscore readway means RG Onway means I only want to read this file。

And what that will return is something called a file descriptor。And this will get important。

 the file descriptor is a small integer， like two， three or four。That the operating system assigns。

As the identity of this particular open file。Now if it returns something less than zero。

 that's an indication that this file or path name is not valid。And already。

 whenever you start a process， as you know， you have three different IO connections and those are given the first three file descriptors。

 so zero is standard in。One is standard out and two is standard error。

And then as you open more files， they'll be assigned successive values， three， four， and so forth。

And then when you've done with the file， you can close it。And。

So these should be fairly familiar to you opening and closing files you've done with other types of IO。

 but this is。of the version that's used in the UniX aisle。And so you can close the file。

And then the read operation， there's just a very simple call called read that you give it as an argument。

 a file descriptor。Which， as I mentioned， is an integer。A pointer to。

Some type of location where the RE should occur。And then you give a limit for the maximum number of bytes that you want to read。

 which is typically the size of this buffer。But the interesting thing about this is it's actually saying I want to read up to that number of bytes into this buffer。

 but it's possible that it won't read quite that many and so what the value that's returned by read is exactly how many bytes did it return and so that number will be。

Somewhere between  zero and 512。Or else actually it can be negative。

 meaning there is some type of error occurred。So if it's less than zero， it's an error。好。

But it's possible to have some value less than zero， that's called a short count。

Even if the file is actually- and so why can short counts happen， I'll get into that in a minute。

And then there's an inverse operation called Bte， which is just to write some number of bytes。

From a buffer into the file。But again， it's possible for the right to。Have a short count。

 which sounds a little weird， it doesn't write the full collection of bitetes into it。

 and so what it will return is the number of bitetes that were written。And so again。

 that's called a short Count and I'll talk about what that means。So here's a very simple。

And not very efficient program。That simply reads one character at a time from the standard input。

And writes it to standard output， so you can think of it as just whatever you type would go directly to the output。

And you notice that it's。Very， it's limiting the number of bytes。At a time to one。

And so it's just picking up a character and dropping it back。

This would be a very inefficient way to read from a file。Because every one of these reads。

Has to make a system called to the operating system， which as we talked about a couple times ago。

 means it will actually transfer control up into the kernel， the kernel will do whatever it wants。

 and then it will restore back so it's treated as one of these exceptional events。

 exceptional control for events。And it takes。Multiple thousands of cog cycles。To do that。

10 plus thousand0 clock cycles， which in a gigahertz processor， it's not a big deal。

It's a few microseconds， but。If you do that a lot， it'll add up。

So but this just demonstrates that there are actually times when you want to do single character reads。

So you have this very low level control over what happens with reading。

So what did I told you a short count going to occur both on reading and writing？So on a read。

 it can happen for the simple reason that you've run out of bytes to read。

 you've come to the end of the file， there is only 10 bytes left in the file when you started to read。

 and so it will just return that count。Sly， if you're。Reading from the standard input。

And the person has stopped typing， it will。啊。It will only return the number that it won't wait for the user to type more just because you've asked for more。

 it will return immediately with however many characters are available。

And it also happens when you're using network sockets， both reading and writing。

 so when you send a message from over a network connection。That's split up into packets。

 little chunks of data that are then routeutd over the internet。

Via series of hops to the other place。 and those chunks actually depend on the particular parts of the network that you're passing through。

 But it's typically no more than 1500 bys or so at a time。 So if you said。

Over a socket that you want to write a megabyte file。To transfer it to some distant place。

The networking software。Is going to break that up into a bunch of little packets and send them all over。

And then when it comes to the other end。And you'll see that as you write。You'll get it right。

 but it'll actually be a short count of just the first packet that's gets sent。

 so you have to write a loop that will just keep cycling through and pushing all those bys out from the file and similar the other end as you read it。

 every packet that comes in will be a return from a read with however many bytes were in that packet。

So typically at both ends， you end up running new。

![](img/8530f17059e7fbf7c64f073d1939349c_5.png)

![](img/8530f17059e7fbf7c64f073d1939349c_6.png)

This is not convenient。I'm not a Windows fan， casesey haven't noticed。他。So anyways。

 the point is short counts can happen in different contexts and you have to be somewhat aware of what they imply and what it means for handling and that can get tricky。

 like I said， you want to think about， say a terminal input is a very different animal than a file input is a different than a leading from a socket and you kind of have to understand。

Which conditions apply where？So let's talk about pretty interesting。

about some of these lower level features of files first of all。

 associated with a file is a whole pile of information about that file that's referred to as metadata。

 it's not the actual contents of the file， it's information about the file。

 and that's what the general term metadata means。And there's actually。

A functions that you can call in the library called Sta and Ft that return a。

 you pass it a pointer to astruct。Of some。Particular kind and it will fill in the contents thatstruct with all these little useful tidbits。

Including things like not just a time associated with the file， but when it was last modified。

When it was last accessed and various other pieces like that， it will talk about。Information。

 the I note is refers to where's actually stored。In the permanent location for it。

 it'll have the protection information that you've seen， you know a file can be executable。

 readable or writeable。We'll talk some about the ownership and it will say how many bytes is it total。

 so that information all exists about every file and there's times when you'll want to pull query that information for some programmer。

so just keep in the back of mind if that's something you can do。

But here's a particularly important set of ideas here。

We're going to go over and the main thing is it will help you understand things like redirection and file sharing。

This is and there's a number of fairly subtle points to this。So as I mentioned。

The file descriptors tend to be these small integers。

 and the reason they're small is they're actually indexes into a table that you're。

That's part of the state data， the information about your process is a list of all the files associated with this process。

啊。And so each process has this array or table stored somewhere within its representation。

And then for every file， well theres every file in the system has a V node entry。

 which is some information about。嗯。About that file where it's located all that protection information。

 because that if it's a file that you want to save over time。

 that information has to live beyond the time of a particular process。

And then at any given time across the whole system， some subset of these files is open。

Being accessed by one or more processes。And so again， for every open file。嗯。There's it a table。

And actually， there can be for a given file， there can be。呃。Not all of these。

Records indicating that's keeping track of this particular open file and we'll see examples here。

 you can have two entries for the same file open。And what's important about that data is first of course。

 it has to point to the V node information， the information that long lived information about this file。

 but it will also contain a record of what's the current position in that file for reads and writes that I mentioned at the beginning at any given time。

It also has something called a reference count。 and a reference count is simply how many。

File descriptors。Are pointing to this particular record here。

And so the initial value when you first open a file is one， there's you've created a file。

 but when you start sharing files， then that reference count can increase and when you。Cosaophile。

You can decrease can decrease that reference count。So let's see how that all works。So as I mentioned。

 it's possible if you call open twice with the same file number。You'll have。

Two different descriptors in this open file table， even the same process。 So if I called open open。

I will get two different descriptors。Or records in this open file table。

 both pointing to the same file。 And the important fact about that is all'll have different positions and think about this。

 If you're like， for some reason， you're reading a file and you decide you want to。Make another。

 open that file again and start reading。You don you'd like the ability to sort of keep those two file positions independent。

 and so that's what happens because there are different descriptors in this table。

So if you call open twice， then you' not really， you're sharing the file。

 but you're not sharing information about its file position。

And so the reference count would stay one。But what it gets interesting in various ways when you can actually start really sharing entries in this descriptors of this open file table。

And one way that will happen is by fork。啊，这个。As you remember。

 ForRC is the way we create a new process。啊。By replicating an existing process。

 and you might have noticed。With those little toy programs that I demoed。A week ago， I guess。

That it would print。Both the child and the parent processes would print on the same screen as I was using and that's because they actually shared the same standard output file。

So let's see how that happens。So if I call four because you remember it， it sort of replicates。啊。

Makes a clone of the parent， and that includes the parent's descriptor table。

So when you first fork a child， fork a process。Its descriptor table is an exact copy of the Par descriptor table。

And now what will happen is there'll be for every one of those file descriptors the parent had。

 there'll be its counterpart for the child， and my reference count will be incremented appropriately。

And so that has implications， because the main point to observe is these two connections are sharing the same file position。

And that's not so interesting was standard out where there's no real position。

 but if it's a regular text file。What it means is I will。Potentially those two。

 if they're reading from using the same descriptor， they're basically in a sort of strange way。

Jumping over each other's character。So that can have some weird effects and effects that make great example questions。

 by。Another sort of related idea that you can understand by seeing this table is this idea of how does redirection work？

So you remember in Linux， if you say run a command but。Instead of。

Printing its output on the screen or on standard output， direct it to a file。

 in some way I can use redirection to read instead of from standard input from a file。

So how does that work， well， it works by messing with file descriptors， basically。

And so there's a function that's with a very unhelpful name and a very non intuitive。

Set of arguments called Duke2。And what Duke 2 does is it says。

 I want you to copy all the information about the old file descriptor。

Into the slot for this new file descriptive。So for example， if I say Dukeke 2，41。

What it says is I want to redirect standard output or file descriptor 1 to be whatever file descriptor 4s file is。

For example， it might be an open copy of foodoc text。

And so what will happen then is I'll have now two copies of the same pointer into the same descriptor table。

And so what will happen？For example。Let me step through this example。Yeah， so imagine I have a。

My child。Go far。Let's see。No， this is don't worry about the child business。

 Just imagine I want to redirect， implement redirection。 So I start off with a。

Standard output just at wherever it normally is。But if I say do two and give as the second argument one our standard output。

Then what I'm doing is shifting the standard output away from its terminal output to a file。

 and that file will be whatever file descriptor for tells me it should be。And so now as I do that。

 I'll increment the reference count for。The second file。

 and also the duping will decrement the file descriptor。

 the reference count for the original file descriptor that was in this first argument。

 So file descriptor 1。We'll get redirected here in this information about its previous。

Where that was directed to will get set to reference count zero。

 which means that the file is no longer accessible。

So that's a real simple version of how IO redirection can work then is by using this dupe2 and now any right to standard output will be instant to this file B。

So this is an example of the kind of question， like I said。

 there's a lot of exam questions we can make and I can promise you these won't be on the midterm。

 but they will't be on the final。So let's just do a quick step through one of these。

So here you'll see that I have a file name。That's actually I'm getting off the command line but that doesn't really matter and I will open it three times and get three different file descriptors。

 Typically these will be three， four and five， but you don't really need to worry about that。

 but you'll see I'm calling this Duke2。And that's going to mess things up。

And now I'm going to read characters from these three file descriptors。

 and I'm going to print them out and the question is。

 and assume that the file just contains the string， ABC， D E， what will be printed？Any guesses？

So for example， what if this Duke two were not there？What would happen？If I read。

 I open the file three times and I start reading， but from three different file descript。Yeah。Well。

 that would be one guess。What would be the other guys？Hey， hey， hey， yes。

 you know it's going to be one of those two。So why would it be AA。

 it's because each of these file descriptors has a separate position。

It's a separate entry in this open file tape。And so since I opened it three times and I'm reading from three different ones。

这样。It doesn't pop along like what you said。Okay， so that's。

Part B of sort of weird stuff Now part C is now let's throw Duke two into there to mess us up。So。

And remember， Duke2， that now F3。Will be a cone of F2 in terms of its file descriptor。

So I read from F1 and that's， as he said， A。I read from F D2。And that will be。A， right。

 just like before， but I read from F3 and that will be。B， exactly， because B。

I've sort of whereas before F1，1，2 and3 were sort of independent。

 now two and three will be sort of codependent， they'll both be sharing the same position pointer。

So that's why you get AAB out of this。Okay， now this one's a sort of a relateded idea。

That I'm calling。The main point is I have a process and I'm opening a file and I'm reading from that same file descriptor in both the parent and the child。

So。And again， let's assume this file is ABC DE。So can I predict exactly what this is going to print？

No， right， because there's basically。I think it's a similar idea to before。If I took out that du。

 too， remember， if I'， I'm just open a file。Actually， it's different。

Because these two are the same a file descriptor and even when I forked it。

 they're still pointing to the same entry， so they're sharing this position pointer。

 so one of them is going to read an A and the other is going to be a B。That much you can be sure of。

 but you can't tell necessarily which is going to go first the parent of the child this one sort of set up to kind of be like a random talk coin toss that will sleep as you'll see is。

The lowest bit of the process ID。Which you can think of as a number that will change every time you call it。

And so it will either sleep for one second on one side and zero seconds on the other。

 so it will sort of this race condition， this competition is going to go one way or the other depending on S。

 but you can't tell in advance， which will be yes question so do reason。Yes。So yes。

 if I started both， there's only one position。The same position is used for both reading and writing。

 but maybe that's what you meant if I were to now start writing。

 although I didn't open the file to write it， I only opened it to read it。

But if I opened it to read write。And this is true for even anyIO that。If you mix reads and writes。

 you're still always moving the file position together。Okay。So。Go online and you should find a quiz。

嗯。I this。Too many people have gotten this quiz done yet。Oh wait， you did figure out the second pair。

Except you got the wrong answer。

![](img/8530f17059e7fbf7c64f073d1939349c_8.png)

![](img/8530f17059e7fbf7c64f073d1939349c_9.png)

So。One great thing about。Problems like this is you can just write the program and see what it does。

So I think this was the problem， right？That the one you had？嗯。

So this is really a question about exec。You'll see， it has nothing to do with signals or IO。

But what is' this very peculiar program。And what it will do is if will。

Basically recursively call itself。Over and over again。Each time it will decrement。

It's the first character of its argument。And wait until that。

Hits something less than the character A。 So if I start this。With C。

 which I think is what you're asked for。Ohoops。Oh， I think。Actually， I don't have。

 I don't know logged in here。I think it's still a run as eight out， I compiled it before。

 and if I give an argument C， what it will do is，Prined out。

It's arguments in order it started with C the next time it was B， then A， and then it was done。

And so the idea of this。Is that exactlyec if you remember， you're given a command。

Wsted arguments and。And there's no environment pointer here。

So the command was just whatever I passed。 I'm just passing the same arguments that I had originally in。

 So it's really just like a。A recursive loop。I'll stop it。

 so you can see I' started with C then B than H。And the other part of the question is you'll notice that the process ID。

Is the same2， three，1，5 both times， and of course that will change from one run to the next。嗯。

Because my process ID will keep changing， but you'll see it's always the same ID and that's again。

 the point of this that exec。What it does is that whatever the running program is now。

 it will change it to be whatever you've asked it to be， which in this case is just a copy of itself。

So it's a sort of arcane piece of code but it does demonstrate a few interesting features。



![](img/8530f17059e7fbf7c64f073d1939349c_11.png)

![](img/8530f17059e7fbf7c64f073d1939349c_12.png)

![](img/8530f17059e7fbf7c64f073d1939349c_13.png)

![](img/8530f17059e7fbf7c64f073d1939349c_14.png)

Okay， so let's continue on with IO， as I mentioned。

 we've just gotten a little glimpse of the lowest level of IO in Uniix with readrite file descriptors and stuff like that。

 most of the time you use a library that's referred to as standard IO and sometimes as buffer IO。

And it provides a slightly higher level interface than you saw with。The standard， the Uniile。

And sometimes these are referred to as streams， these files， you'll hear that term so。

And as you know， you're always given your program has access to three streams， standard in。

 standard out and standard error， those are just stream versions of these first three file descriptors you saw。

嗯。But one of the things it does is called buffering。

 you saw that example before where I was reading and writing one character at a time。

 and that's expensive in terms of calling the operating system。But then again。

 if you think about when you're generating files， it's not uncommon for you to want to pk out one character at a time or read one character at a time with say。

 get see， get care or put see or put care。Or you'll spit out just a few characters at a time as you're building a longer one。

So what the？啊。This library does this provide buffering。

And what above her means is that at any given time。

It will have accumulated some collection of characters。好。Well， some of them。

 let's look at it from the read perspective， so I want to read a bunch of characters。

But when I what happens， but maybe I'm going to just read them one at a time。

 what will happen is that the system will read a bigger chunk of stuff。And start in a buffer。

 And then keep track of a position within that buffer where up to here。

 if I'm calling get care gettse， it'll read up to this point。 And now， as I do more getses。

 it will continue moving to the right。 So this is different from the file position。

 which is maintained by the operating system。This is internal in a buffer that's part of this library。

And the same thing goes with output but instead of read， say written， so already written。

But there'll be other ones that I've put in this buffer。

 but I haven't pushed it out onto the actual file yet。So as an example， if I do a printf。

Of one character at a time。Then actually， all it will do is accumulate all that string in a buffer。

And if I really want to force it to get printed out， then I have to call a。诶呀。Function called flush。

 F flush。And only after that happens， in response to F call will this buffer IO。

 this library routine do the actual right of this six characters， and you can even trace that。

If you write a simple example and you use a program called Strace。

 which lets you track what system calls are being made。By a program。It's a little。

 remember I showed you before how you can track calls to library functions by what's called inter positioning S trace sort of does inter positioning for all system calls。

And what you'll find is that those calls to printf。

Followed by the F flush just generated one single right。啊。To an actual ex， right。

But it printed the entire string hello with the return character as a six by right。

So the point of bufferford IO is that instead of making one at a time calls the operating system。

 it tries to accumulate as much as it can and then stick that up and similarly if you read from a file。

 you don't actually read，Some number of characters out of that file itself。

 and then you can pick things out of the buffer and those actions。

 operations on the buffer don't require system calls because they're all internal to this library that's just running in your process。

And as I mentioned， what we'll find。As we get into networking is that neither the LoA reads and writes of UniX files nor the buffered operations of the standard IO library really are appropriate for using for network connections。

 these socket connections， and so there's another library that's described in the book called Rio reliableable IO。

 and it gives you versions that are sort of like，看呀。

There are a fairly thin layer of extra features on top of the standard IO， I'm sorry。

 not the standard IO that the UniX IO functions。So for example。

Both the read and the write operations， you remember， have the possibility of doing short counts。

And sometimes that's good， like if it's the end of file， you really want it to come up short。

 but other times like I mentioned that you have a network connection and it's just coming up with short counts because of the way this data has been divided into packets。

So what I'd really like to do is just say。Just read the darn thing。

Do whatever hoop you need to do to get the whole thing and then come back and tell me about it。

 and so that's sort of what the Rio package will provide for you and similar for rights it will just do whatever right you ask。

And so those are the read in and write end， it also provides a read line which is sort of like F Gs that you can read all the way up to a return。

Linefe。You know， end of the line。And normally those。And then as a result of that。

 it does that using buffering， and because there's a buffer now you have to use a special flavor if you want to read from that same file descriptor the same file。

 but some arbitrary stuff not worrying about line breaks。Because of the buffering。

 the problem is once you've read something into a buffer。

 if another readed comes along and doesn't know about that buffer。

 it'll skip over some collection of bites， So these two are designed to work together and again。

 this is stuff you'll really appreciate later in the term for your final project but you're not going to touch it right now。

So the。Idea then of this。Read down and write end is sort of the same idea as。

The Unix versions of them， except it will do short counts。

Or it will only do a short count on read if it counts it in a file。

So one thing you don't want to use this if you're not sure how many bytes。

They usuallys going to send you because it will just sit there and tell either。There is a。

It reads that many bytes， or there's an end to file signal， for example。

 when you terminate a connection。In the right end will never have a short count。

 itll just keep it basically as a loop to keep writing until it's done。

So it's worthwhile actually looking at the code for this。

 and I'll just skim over a little bit of it to show what it's like。 But for example， this is read N。

 So as I mentioned， it has read。 and the main point of it is it has a loop。

Around the regular Unix Reed operation。 and what it's doing is。In general。

 it's going to keep reading until it's got as many characters as it's been asked to read。

Each time it will get some number and read， and it will decrement the number left that it's waiting for by that number。

啊。And it also handles various error conditions and endde file conditions in between。So that's。

A pretty good demo of all these code is sort of a fairly small wrapper extra functionality added around its Uni counterpart this code is。

The total package is only a few hundredvins of coat。And as I mentioned， there's bufferford IO。

 which is a way you can do more efficient reading and you can do line by line reading too。

 which you can't normally do with a UniX file， the only way you can read line by line in a UniX file is to do single character reads。

Looking for that return character because if you。好。Well， no， I guess it's safe otherwise。

You can do more， but then you'll end up with some leftover stuff because it will read right past that line character and keep going to the next line and the next line if they're there。

 and so somehow you have to keep track of， oh， now I'm at the end of one line at the start of the next。

So you can think of this as just sort of a more convenient version that handles some of that low level stuff。

So you can。Basically， provide a。诶呀。The same it looks like a read except it will stop when it hits a line fee。

And the general idea of it then is the same as we saw for the UniX IO。

There's a data structure that's actually you。That you allocate yourself called a Rio buff that contains an array of characters。

 enough space to hold this buffer that it maintains。And so at any given time then。嗯。You have。

The Ri Buff will be some part of the UniX file， so the UniX it will read if this is a read。

 for example， it'll read ahead， like I mentioned， it might read through multiple lines of a file。

And then it will， if you then say get a line， it'll just keep choing through this buffer until it comes to the end and then go ahead and do some more reading。

 so this is layered on top of the regular UniX file。不 me。

So this is a slightly more elegant way of reading from standard input and writing to standard output。

 where it does it on a line by line basis。It will。So what I want is I create a。A buffer。

That I call Rio。Astructive type RiO T。I initialize it to say。

 I want this to be a buffer of the standard input， and then I'll start calling Rewine on that buffer。

And then for each line， it will return， and then I'll do it right。To standard output of that。

Of what I've read， so you'll see the output in this case is not buffered， it's just a direct right。

But the input is。Okay， so to finish this up then。As I say， we've really talked about three different。

Types of files， one is the low level UniX version， the other is the familiar standard IO。

 and the third is this Rio stuff。And so let's just sort of review what they get used for it。So forth。

So Uniix IO is sort of the bases case。 it's the standard that is used， as I said。

 to handle this whole variety of different types of IO devices from。

Fileles you might have on disk to network connections。

And so it has all these different features to it， but it's also very low level and rather painful I should mention that。

We talked about signal handle lawyers have to have OE call functions that are async signal safe。

And one of the most annoying features in the universe is that。

None of these functions are async signal safe。And we'll talk later in this term。

 I'll give you a demo of what can happen if you do it。

 but basically suffice it to say if you call one of these functions in a signal hand or you can have your whole program just lock up on you。

 it's annoying。So you're not supposed to do that and basically the only things you can do are direct use of this UniX aisle。

That's totally safe。So as I mentioned， the problem with this is it's low level and so it's got all these features。

 short counts to try and do text lines， you have to introduce some kind of buffering。And so forth。

 so that's the why there's these other packages that are built on top。Standard IO， as I mentioned。

 is sort of the normal thing you want to do for routine file applications。啊。

Its not they're not async signal safe， so you can't see them in signal handwis and we'll find they' work you don't want to do this on network connections for various reasons。

嗯。So just to summarize then you use standard IO for kind of the common file operations。

 raw IO for signal handlers or sort of other special cases。

And Rio will see that's useful when you're doing network programming。

One thing to mention and this will really be important on your final assignment。

Is people often don't realize that binary files are very different animals and text files and some functions are really bad to use。

 So for example， if you call Stland。On a binary file。It will return some number。

 but it probably isn't what you want。It won't be the length of if you set up a， you know。

 you read like a JPEG image into memory。Into an array of some length。 And you ask。

 how long is that image， you know， the data for that image。

 The problem is Sterland will hit stop the first time it hits a nullbi a0。

And it's totally possible within a data a binary file to have zeros in it， that's pretty common。

 in fact， and Stland will stop at that point。 Similarlyly。

 if you try to copy binary data from one place to another and you use stir copy。

 it'll stop as soon as it hits the null， So that's a really bad idea and you'd say。

 well who would ever do that。You'd be amazed how many？Versions of the final assignment。

 the way we call the proxy web。啊。Students are can't get it to work， can't get it to work。

 you look at the code， Oh， you know， you're using stir copy even if this is copying a JpeEG image。

So people do it and it's not easy， and so that's why Rio is particularly good。Okay。

 so now I wanted to。Go back。

![](img/8530f17059e7fbf7c64f073d1939349c_16.png)

2。The lecture from last time。

![](img/8530f17059e7fbf7c64f073d1939349c_18.png)

![](img/8530f17059e7fbf7c64f073d1939349c_19.png)

And there's just a few little things that I really wanted to cover in that one。



![](img/8530f17059e7fbf7c64f073d1939349c_21.png)

So his context， we were talking， remember last time about the idea of signal hand words。

 which are pieces of code， you can write that when a signal occurs， some type of exceptional event。



![](img/8530f17059e7fbf7c64f073d1939349c_23.png)

Then instead of the default action， which is typically to either terminate the process or to ignore it。

It will instead execute your code。And we talked in particular the idea of we're showing a shell。

As a simple example。A simple example where the。嗯。Typically a shell。

 then it's sort of program that's the command line interpreter for you。

And you want to be able to tell it to run other programs。 And so the shell will fork a child。

 The child will execute that。Code。And then the child will exit。

And what we found last time was if that you ran that child in the background。

 then the shell had no way of knowing that the child had completed。

 and it would therefore fail to reap the child。 and it would become a zombie。Which is not good。

 as you can imagine by the neighborhood。

![](img/8530f17059e7fbf7c64f073d1939349c_25.png)

So。The thing that comes to your rescue on this。

![](img/8530f17059e7fbf7c64f073d1939349c_27.png)

Just comment。I'm supposed to be neutral about operating systems， right？这啊。嗯。

So the Sig child is a signal that gets sent when a child completes。

 gets thisig child signal gets sent to the parent， and that's the mechanism by which the parent can know。

 oh， my child's done。So what you'll do in a shell then。

 if you're creating background jobs is you'll fork it。

You'll let it run in the background and then when it completes， the Sig child signal will come。

 and then the handr， I'll have a handware for Sig childd that will do whatever it takes to sort of finish off that operation。

And what we found is that if we just call the function called weight or in particular weight P。

That will cause the operating system to do what's known as reaping the child。 So will。

Basically go from being a zombie to being dead。That's the good outcome for a zombies to die。嗯。

Why my understanding， I'm not too into zombies but。呃。

So this is an example of a very simple SIig child handwear。Which， in fact， when you look at it。

 you go， wait a minute， I remember last lecture you told me to write a loop in my Sig child handler。

And that's generally true， but in this case， I'm only going to be waiting for one child so it will work。

So the point is that there's some code I can write that will term properly terminate a child when it gets invoked。

嗯。And so now what will happen， this is sort of what roughly what the loop of what the interpretation loop of it of。

Sorry， of a。Sll will do is it will fork a child。And normally， then it would call exec。呃。

In that child to run the new job in the background。

 but I've just made this super simple by saying exit。And then。

What happens is when it comes time for the。Parent to wait for this child to complete。

There's various options。 So you， you remember like in a shell。

 you can start something in the background， but then you can bring it to the foreground。

 meaning that the shell should wait until。This process， this child process is completed。

So what I'll do here is I'll wait。 I'll do what's known as a busy wait。

 I'll just sit there looking at this global variable， called Pi。PID， which was set。Excuse me。

Which is set by this Sig child handler。 Remember， the signal handlers are considered the same process as the main program。

 And so any global variables they set will be visible to the。This executing program。So basically。

 what this program is doing is in what looks like an infinite loop， except lo and behold。

 eventually this child will complete。 a signal will get sent。 My Sig child handler will be invoked。

 It'll set Pi to something at nonzero， and I'll be able to exit this loop。

So this is a perfectly functioning code。Considered really， really bad form to busy weight。嗯。

So you'd think， well， okay， what can I do to sort of？Avoid just sort of sitting there。

 executing a program that's just in a loop doing nothing and using up this processor。Well。

 one call you could make is there's a function called Pis and pies just means。

Sit and wait until a signal comes through。And so。That's sort of what you want to do， you'd say。

 just basically suspend this process until a signal comes through and let the signal handle handle that and then wake me up after that's done。

And so this code kind of works， but not quite， and the reason is there's a race condition。嗯。

Anyone see what the race condition is？It's actually a little bit tricky。So imagine。

This program checks his value P。And sees that it's still zero。And so it says， oh。

 I'm going to jump into pause， but before it can start that。Zing comes as Sig child。It。

Fies up the signal handr， the signal hand completes。And reaps a child。

It runs a signal handr before it actually starts。They's called a pause。

Well now pause is waiting for a signal， but that signal has already come and gone。

So now it will basically hang and pause forever。And so this is extremely low likelihood of happening。

 But one of the things you have to when you write this kind of code is。Not think， well。

 it probably won't happen， so I should be okay。 You have to really make sure it won't happen because imagine you write code that's used by a million people around the world。

 maybe。If something has a one in a million chance， I mean， somebody's going to get it。So you really。

 this kind of code has to be really very carefully written。

So there's another version of it that actually works。 It's sort of a hack。 as you just say， okay。

 I'm not going to just in a busy group。 I'm just going to。啊。

This is sometimes called polling that you test for something。If it that action isn't appropriate。

 then you'll sleep。 you'll just wait for， in this case， a second and you'll come back。

 So this code actually is functional。But a second is really a long time on a computer。

 and so you generally don't want to do that。That kind of thing。

So the trick is there's a special function available as part of the signal stuff called SG suspend。

And six supend is sort of a version of pause。Except that you give it a mask。

And it will apply that mask before it calls pause， and it will guarantee to be atomic。

 meaning that it wont it's not possible for anything to happen between setting this mask and。

And calling pots。And so what will happen， the correct code for this then will look like。嗯。Like this。

 it will the same idea as before。It will test the PI。嗯。But meanwhile， I have。

Let me make sure I've got this right。Before I called it， I blocked。The Sig child。

By setting this call here， you'll see I blocked。I added Sig childild is a set of signals I'm blocking。

 so that's still in effect。And so it will do this test。

And it's not possible at this point for that signal handler to be woken up because it's blockeded。

And what it will do is it will call sig suspend using the previous version of the set of signals。

 which I'm hoping does not have Sig childil blocked。

 So what it will do it is will temporarily unblock Sig child。And then call pause。

 And because it's atomic， there's no danger that it will。Unblock。

If you tried to do this with direct code， you'd have， again， this race condition。

 I might unblock the signal， but before I could call pause。

 then zing the Sig childil handler gets invoked and it's done。So。

By making this atomic so there's no possible action between these two。

 then I'm safely basically opening it up， it says， okay， Sig childild。

 I'm ready for you and then I'm pausing， I'm waiting for that Sig child to come in and there's no risk of some bad thing happening in between。

So this is sort of a little subtle point， but you can imagine。

ThatThis kind of thing will be useful is here？Coordinating the jobs in your shell。

 and so I wanted to cover that today。

![](img/8530f17059e7fbf7c64f073d1939349c_29.png)

And that will take care of us for today。