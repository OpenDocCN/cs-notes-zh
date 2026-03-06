# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p02 P2 The file system (COP-3402 Fall 2024) -BV1v6vdBKEHB_p2-

All right。So let's go over today's lecture， so just to kind of situate ourselves in this。

In the syllabus。Last time we just went over the mechanics of the course and today I want to give。U。

Give everybody an overview of the file system。As I talked about last time。

 this is one of the main things that I want everyone to be comfortable with when you leave this class。

 not be wondering where your file is or where it gets downloaded or how to find things on the command line。

 but it takes knowing the kind of theory the idea behind the hierarchical file system was not。

Derived from nature it was made by people， they designed it。

 so if you've read the most of you have read the UniX time sharing system paper。

 this is the original kind of public publication on the UniI system which described their hierarchical file system。

 they didn't invent all aspects of it， but they invented the design that is really still in use today by most computer systems that you'll use。



![](img/da68893ba5c517e8c08dd7f6cf464dfb_1.png)

![](img/da68893ba5c517e8c08dd7f6cf464dfb_2.png)

all right， so let me go over the。Go over this file system。

So many of you may look at this and think well， this is the file system when I think of the file system I think of this graphical interface that allows me to。

😡，Click on files， open things， run things。 but this is not really the file system。 This is the。

File browser or file Exper， this is an application that interfaces。

With the file system to let you do operations on files like moving things， copying things。

 browsing things。So this is really just a view of the file system。

 but there's much more under the hood that files do。In the operating system。



![](img/da68893ba5c517e8c08dd7f6cf464dfb_4.png)

And so the main thing to take away here is that files are not some physical thing that lives on disk。

 they're an abstraction， they're a way to group sequences of binary data。

 that's basically all files are， there's no naming， there's no hardware specific。

 there's no file formats。And the purpose of the file abstract， we'll talk about the purpose of it。

 but the reason is is that there's lots of different ways to store data on hardware。

And there's also lots of ways to do IO for a machine。And in the Uniply。

 the file abstraction is the way to capture all of these different types of hardware。

 different types of IO in a single abstraction。So why is it an abstraction？

It's an abstraction because just like any abstraction it captures what's common about something in this case it captures what's common about IO。

 and we're going to talk mostly about storage files in this class。

So what files do is they capture what's common about storage hardware。

So what are some different data storage technologies that you can think of？Fppy disk， okay。

 that's an old one。Others， yeah。SSD。Yeah， hard drives， which are different。

 and they all have different physical properties to them。

 they evolved different ways to actually store data and depending yeah， good ahead。对。Sure。

 you can think of a cloud as a storage mechanism， if you have some interface to access data to it。

 you could use files as abstract of that。USB stick， yeah。

So it has a different bus interface than like a hard drive， yeah。A charger。So the charger。

 unless it's like a malicious charger that can do more than just deliver power than it shouldn't be。

 it shouldn't be except doing IO， you would hope yeah。Magnetic ape， yeah， sure。

 so all of these are different physical media。And depending on the bus that they're connected to。

 they there's different instructions that you have to send to them in order to read and write data。

Well， what the file does is it abstracts away all the differences between this different hardware。

And it gives you a very， very simple interface， it allows you to use all of these different storage media。

With the same commands， with the same functions that I'm sure you're all familiar with。

 so you can read sequences of data， sequences of bytes。And you can write sequences of bitetes。

Now of course， it's a little more complicated this you can open files， you can close files。

There's permissions and all this。But at the end of the day， the file abstraction。

 it just takes any piece of hardware or any piece of software and turns it into something that you can read and write sequences of bytes from。

So in this class， we're going to be using the Uni style。File abstraction。

 this is used pretty much everywhere， even Windows I think supports the Poits compliance。

 the UniIX standards。O。🤧So to illustrate this distinction between the file and the stuff around it。

 like its name， where it's stored， see the abstract part of it， let's take a look at the contents。

Of fire。This is the terminal here on the right。So we'll start next week。

 we'll go over actual like terminal commands， but I just want to illustrate for you what's inside of these files。

 So this is so let me actually show you what this is。

 so this is just a simple hello world program if you were to open this up in your editor。

And so from the OS point of view， the contents of this file is a sequence of bytes。

 and this is a sequence of the bytes in Hex code。And hexadecimal。And with the staff C flag。

 I can ask it to convert those hack bites into ASCI。So if you were to。Read this disk raw。

 not mediated through a file system， and you were to examine what bits were set you would see。

Lced written in he decimal here， these sequences of bits。🤧Are set。

For the file that corresponds to Hello doy。And so notice that there's no notion of text here。

We have to interpret these sequences of B's text and that's what the ASCI Convention does。

 the ASI Convention just assigns numbers to Latin and other characters。The sea flag adds this。

Asci interpretation of the。Of the bites to your right。Yeah， what's that。How come the what？Oh， oh， oh。

 that's a very good question。So I think this is because of endingianness。

 So you see these are these every bite has swapped here， so 2，3，6，9，6，4 so I think。

It must also be reinterpreted the ending this ending the in this。

 so this is probably showing the whole 16 bit， I guess word。And this is not。

 this is showing the eight bit ones。Let me， let me look at the。So it actually doesn't say in here。

 but I think that's what's going on。際。はいああと。Right喂。Oh yeah，I don't like。No it's just a manual page。

 so yeah， this is just because of the Indianianists so I guess in this canonical format。

 I don't know which one is which I guess this is interpreting the Indiandianness and this is not this is just however it's stored I think that's what's going on。

Don't worry about that yet that we'll assign that in several weeks。

 this is just to show you files in the file system。Okay， so that's the contest of a file。

 in this case， the helloworld。c file， even though your editor reads it as or interpret it for you as ASI characters as Latin characters on disk it's just a sequence of bites。

So this has a dot C extension， so what does that mean， and it turns out that files don't capture。

The extension at all， they don't even capture the name。

And at least in the UniX design of file systems， the data within the file has nothing to do with。

The the name is not captured in the file。So let to show an example of what this looks like。

So there's a youthful command。In a UniX world calledFile。

 and it'll tell you the type of file that it is。So here it's telling us that this is C source code and it's ASI textex。

If I take， say， an MP3 file， which is a music file。It'll tell me， oh， okay。

 this is an audio file containing emG， et cetera， et cetera， et cetera。But notice if I say rename。

Hello to hello。mp3。What is this file， what do you think this file command is going to tell us。

 what kind of file is it going to tell us this is？C source， who says sea source？Who says MP3？

Who doesn't know， okay？So it still tells us its CSA， still tells us's ASI text， why？Why， because。

It's looking at the contents of the file。And not。The actual name。

 it's not looking at the name of the file， so this is an example of the map is not the territory problem。

 so the name is just referencing the file the file itself。It's just sequences of bytes， yeah。

Like why you hear the。Well， so I changed it here and I didn't get a warning。

 so you must be talking about a very specific interface that's giving a warning。Wdows， so Windows。

 if you use the file explore this application， so the programmer added a feature to avoid。

 I guess a mismatch between the file contents and the extension。

 I'm going actually show some examples where malware uses this distinction between the name。

versus the actual contents to like deceive people， so applications will indeed somehow of some file explorelorer applications like Mac does this as well will warn you or either try to prevent you from changing the extension。

But it's really to avoid this。Mismatch between the name and the actual file。

 so I copied it to an MP3 file， I could move it as well。

And I'm not going to get any complaints from my move command doing this。But yes， applications。

 the applications developers do that。To avoid headaches on your end。Stands for copy CPCOPY。

And we'll go over that next week。So yeah， so similarly。

 I can do this with the MP3 file and as I hope now you can guess that even if I rename it to dot C。

This file command still knows that it's actually an MP3 file。

So let's see why that is for in this case。So if I look at the。

 that's the whole contents of the M3 file。That's a lot， so just look at the top of it。

 you'll see at the very beginning， there's a sequence of bytes， ID3。

And so let me move on here and show why this happened， so there's lots of types of files。

That are regardless of what the extension is， what the found name is。

There are several types of files based on how they're used， so text files are strings of characters。

 ASCI characters， and so you can figure out whether something is an ASCI file or not by whether it has ASI numbers or not。

 if you have numbers that are outside the range of ASCI then。

It's probably not an ASCI file program files or sequence of machine code。

 images music like my MP3 file here， where there's these custom binary file formats for different kinds of audio encoings。

And so what this file command does。s there is a it basically just has a database。Of。

It has a database of these magic bitetes。So when non malicious users files operate。

 they insert these magic bytes at the head of the file at the very beginning of the file to help applications identify what kind of file it is。

And so this ID3 prefix is the magic bytes for audio files that have these tags in them。

 the type of file is not so important， the important part here is this notion of magic bytes。

And so that's what we see， that's what we saw at the head of this MP3 file。So anyway。

 this is all to say that。😡，The contents of the file are not at all related to what the name is。

 the contents of the file does not know what the name is。

 and the name does not know the contents of the file does not reflect the contents file because I can just change the extension and lie to you。

And this actually has， yeah， good。AhThat's a really good question。

 we'll see that in a couple of slides where the name is actually stored。

 and it's quite clever how it works。So just to kind of give a little quick security preview。

 this has like real world security consequences， so for instance。

One of the earliest largest computer worm， the I Love you computer worm。

 exploited this distinction between the name and what it actually represents。

And what they did is they。Took this。VB script program with a virtualtual Laic script。

 which is a program。That in Windows at the time would just automatically run when you double click on it。

And they named it do Txt。vBS， and I think by default the extension is hidden。

 so you should probably be suspicious that there's a dot Txt extension when they're hidden but this many。

 many people I'm sure it would have fooled me， I don't think I was full by it hopefully but I don't think I ever received it。

 but you can see that the trick here was the file extension was hidden。

 so users thought that this was the TXT file thought it was。

Totally fine to see who the secret admirer was and double click on it。

 but then this VB script program ran and spread itself and emailed lots and lots of other people。

So that was one fun example of messing with people's impressions of file extension and how they don't necessarily match up what they are。

 there are also cases where malware will hide files。

 they'll call them something innocuous like dotTXT， but during the course of their installation。

 they'll rename them so that they can be executed。呃。And there's a whole bunch of examples of this。

 if you're really interested in like security and this masquerading file type issue。

 which derives from the distinction between the name and the actual contents。

 take a look at these links。てにやす。So it wasn't actually hidden。

 it was hidden because if I remember remembering correctly。

 it was hidden because the operating system would hide file extensions by default。

And so what the user saw was a name with the extension， but you know， you can be forgiven for。

For mistaking that， if you're forgetting that the fasciism' is hiding it。Yeah。

 so the extension wasn't actually hidden in this case。

 or it was actually there on the file in the email attachment。

 but I was think it was just hidden by default。ビ you like。

Well it's a program So viruses are nothing more than programs that you don't want to run on your program I mean there's no distinction between a virus and a legitimate program and there are some legitimate programs that act like viruses it's really just about you need like a model of what you want to run on your machine so viruses are things that usually other people are running on your machine that you probably don't want to run。

If that makes sense。So if virus are really just program。

 they're just applications that run and they're developed like applications these days。Okay。

 so the very good prescient question from your colgue how do files get their names。

 if the file name has nothing to do with the actual contents， well how do they get their names okay？

So to get their names through directories， so if you read the UniX time sharing system。

 you'll talk about their kind of directory， their hierarchical file system and their directory structure。

So directories are really just。Things that map names to files， the actual file。

 so you can think of this like pointers in C where the name is the pointer and the file is the actual thing being pointed to or like phone numbers where if you have a phone book it's mapping people's names to their landline to people still use landline to their landline and similarly there may be many people pointing to the same landline。

And there may be changes of those names， but the landline number stays the same。

So the way this works under the hood， and we're not going to go into how it's implemented。

 but the operating system assigns a unique number to every file， every sequence of bytes。

That's stored on disk， for instance。To every file。Okay， so why do this。

 why separate the name from the file， why might this be useful？Obviously， it has problems， yeah。

Sure yeah， you could avoid instead of a tree， you could have a little directed graph and you could store the same give the same file many names another example I just put it up but you can rename really easily。

 you don't have to actually have to touch the file to rename it to rename anything。

So the other kind of clever part of this is that the directories。

 these mappings between file names and the actual file I note number。

 those themselves are also files because it gets very kind of meta and mindwarping here。

 where the directory is just another kind of file。And so if you read that read the paper。

 they have this philosophy that files are more than just storage。

They're an abstraction or a model of IO of all kinds of IO in the system， yeah。ポインル？

So the way the file system is implemented is implemented like a linked list。

 but the i node you can think of it as the head of the list。

But the directors themselves are not like。Well， I mean they're a tree or a graph so in that sense they're like links the directory does provide links so as know to foreshadow a little bit directories can contain other directories because they're just files。

 they're just matched to files， but so directories are just files。

 they're just special files that store mappings between names。And these in numbers。

 and so it's directories that give names to files to the operating system。

 the file is just some unique number with a sequence of bytes。いか。バオ。答辩人。Moving the location。

Just like。Okay， so。If you move， yes， if you copy， you are telling the operating system to make a fresh version of that file。

😡，So abstractly， you could edit the copy and it wouldn't change the original。Now under the hood。

 the operating system will use caching in order to avoid having to。

 I think they may wait to do that writing disk， but at the end of the day， if you do a copy。

 the semantics of copy is I want a fresh distinct。Copy of those bytes in a new file。Move， but move。

 yeah， as I think I pointed out， move basically requires no copy。

 only the directory gets edited in a move。All question so far。Yeah。こ。

Yeah that's exactly right so you can freely rename and move files。

 but on disk they may never actually move anywhere。

 they may stay the same place and that's actually true of deleting files as well I didn't put this in here。

 but if you so- calledled delete a file a say forensic analyst could just still search。

The bytes that are written on your disk and recover those files or undlete files。

So that's another reason why。one consequence of this scheme is that if I delete a file。

 all that really happens when you remove a file is you just remove this entry。😡。

And so the operating system may no longer be aware of this file， the data for it is still on disk。

Yeah。So this is more of a question for O class， but the operating system maintains a list of all data that's used and not used。

 just like in memory， if you learned about MalC。That might be an operating system too。

 but the operating system manages where on disk， the file system manages where on disk。

 blocks are free and blocks are not free。So they'll get overwritten over time as well we happen。

 so immediately it'll still be there， but then they'll be overwritten over time。

So what happens when you。はい最。So this is getting more sort of advanced file system there are two types of links hard links。

 hard links are just using the same iNot number in different directories。

 soft links is a new file that contains the path to the other file so don't worry about that too much hard links you can look this up with the LN command I can talk about this maybe next week but yeah there are two kinds of links in the UniX world。

Other questions， other questions on this？Yeah， there be some way to maybe take it really？Absolutely。

 yeah。 yeah。 So this is what like。Digital forensics people do they'll they have tools to just search through the kind of raw bitetes of the hard drive and look and basically reconstruct the file if it's recently deleted the file in its entirety will be there because the deletion does not happen。

On the file itself， it happens in the directory。So this entry will just be removed。

 but all of the data for that file will still be on disk。You just won't know the name。Necessarily。

 but yeah，ll it'll still be there， so yes， you can absolutely cover deleted files from a disk as long as。

More you know file operations haven't happened， so you know SSDs have this problem where if you write to the same bite under the hood。

 they're actually not writing to the same physical location， it's called where leveling。

Because SSDs have this limited lifespan。And so the firmware will actually write to different locations so that the same locations don't get used a lot so they don't wear out as evenly。

 so SSDs are notoriously hard to delete really delete files in I think one thing you can do is just like fill up the entire hard drive maybe I I wouldn't recommend trying to do that I think what the government does is they just destroy the physical media if you really want to destroy the data you have to physically destroy there's some great videos on how to destroy physical media from like Decon and stuff like that。

But yeah， you yeah。Other questions。Yeah。story。In every case iss all all the stuff。

Like the level is that all taken care of like at that at the hard level。

 like the weight interfaces with machine is always like。

I think so so I'm no expert on the hardware level， but from my understand there is a chip inside of all these storage devices of firmware chip that there is a common interface on the bus that you say to read and write to and then it can basically do whatever it wants to write。

To desk， so I think in the old days。The protocol matched like the physical contents of a disk。

But I think firmware these days does more sophisticated stuff， for instance。

 if part of the disk is dead， can't be written， they'll like gloss over that somehow。

 but this is really outside of my expertise， but from my understand it is。

 the firmware is doing extra work besides just literally writing to a specific location for you。

All right， so this is the magic of directories， so directories are just files that hold names。

And the actual iode number， the telephone number to the sequence of bytes on disk。

 so this is why you have these masquerading file type problems， this is why you can move files very。

 very quickly because you don't actually have to move the file you just。

Change its name in the directory。And so this we already kind of talked about this。

So moving a file and renaming a file， they're the same thing。

 there's only a single command in UniX for moving a file and it's the same as renaming。

Because both of them do all either of them do is just edit。This directory file。

To change the name of the file， that's all it does。Yeah。Refresh a note number。Or reuse one。いうわれです。

And I know numbers just the operating system provides it， whenever you make a new file。

 the operating system provides a new unique ID， think of it like a telephone number。

 you know you go to the telephone for a company， the operating system manages this。To the file。

 yeah to the file， so in your mind think of the file as just a sequence of bytes on disk。

 the operating system has a unique IP to refer to each one。Yeah。Exactly， exactly。

 so if I rename this to Bob。Then it'll just change this name and the IO number will stay the same。

 yeah， good clarification yeah。So to make that clear。

 let me go into how the hierarchical directory structure works so yeah renaming it's obvious here right because you just change the directory so let me make that clear。

By asking this question， can directories contain other directories？Yeah。

 because directors are just files， so there's nothing stopping you from having this in number reference a directory file instead of a regular file。

 a file that contains data。AsI text。And so to answer your question about how you move a file。

 well you just add take like say we're moving hello to a different directory。

 we would just remove it from this directory's entry and just add it to a different directory files entry。

And now over here。The number will be the same。So all moves and renames do nothing to the。I know file。

 actually let me。I can。I can prove this to you， so LS dash I will show you。

We'll show you i note numbers。And so I could move， hopefully this word。 I haven't tried this。

 So let's just move it to。New file。And let's see if it keeps the same I number。

 so it originally had 4421401。And yeah， same in number， I could even make a subdirectory。

Move that new file into the subdirecty。And look at the in number， and it's still the same。Yeah。一て。なか。

There'll be screen。very。Oh so somebody saying they forced shut down their machine without shutting it down safely。

 that's just because the operating system keeps stuff in memory in RA， part of their files in RAM。

 so your file system probably had not synced back to physical disk yet they use RAM to make file operations faster the。

So the depends on which you mean have a file type， do you mean the extension or the。So。

Extension has no bearing at all on the i note number so I could rename。This new file to a PDF。And。

Its i note number stays the same。The file command still knows that it's this was a compile。

 this was an object file that I compiled。So it still knows it's。诶。An L file。

 which is the machine code format used on Linux。Because the IO didn't change。

 the data didn't change on disk at all， just the directory mapping of names to IO numbers changed。

 that's it。All right。Good on this concept， other questions on this？

So once you could wrap your head around this， it makes it a little easier to think about the hierarchical file system。

 I think。Okay， so。When directories contain other directories。

 this is where the hierarchical file system emerges， there were early operating systems。

 I think early versions of Dos had no hierarchy they just you could have like one level of directories and that's it。

Sorry， Tiette's。Let's actually get into some。I want to illustrate for you graphically this hierarchical file system and some of the conventions that UniX style systems use。

🤧。So root every file system on a Uni system has a single root directory and it's called root and it's denoted with a forward slash。

 so if you've ever seen forward slash at the beginning of a path。

 this is where it comes from it's the top level of the file system so I think everyone's learned about trees and so you can think of this as the root of a tree or the root of a directed graph。

And。When we have nested directories because we can have directories and and directories。

 we separate their names with a forward slash as well。And I'll get into these next to how they work。

 but all directories also contain。A directory called Dot。That refers to itself。

And so you might wonder， why would you need a directory every first itself， and we'll get to that。

It also contains a special directory called dot dot。Which refers to its parent directory。

So let me go through some examples to explain how this works and why。Oh， that's a good question。

 the redirecty's parent is itself。So it points to itself， that's how they resolve that。

Infinary address problem。Okay， so let me actually get a。Let me get， let me get the。Whiteboard up。

Or digital board。なれ選です。Yeah， you'll draw a tree， you'll draw a tree。Okay， so let me write out a。

Example directory structure here。All right， so I'm going to make whoops。

I'm going to put directories in green here。Is this visible？Not really， all right。

Let me make this thicker。偷 sir其次咧。So that's our root directory。I'll put directories in green here。

I'll put files in blue。So， here's a。Text file。And I'll also by convention。

 put a forward slash after the name of directories to make also doubly clear that they are directories。

Okay， so me draw out this。Example。Diirectctorory path here。使う。Let's make another file under here。

Well that's see。I've also got another directory under my directory called home as well。Okay。

 so here's my file system。At the root， I've got ay directory called Root。

 and inside of the root directory there are two files。One is Hello。tTXT。Which is a regular file。

And one is another directory called Home。Under that home directory， there is one file called Paul。

That fileile is a special directory file and it contains。Two files， file at C and another。

Directorory， this directory is also called the home。

And so even though both these files are named home， because there are different directories。

That's allowed。 There's no name cl here we can uniquely。Identify these files。

That own directory contains。One file， it's a special file， the directory file called Joe。

 and that also contains a file called file。c。So quick quiz， this file thaty and this file that see。

 are they the same file？Probably not， it technically could be with hard links， but。

Let's forget about links in this case。Because they're in interdifferent directory， right？

So excluding links between files， which are kind of advanced thing。

 assuming there's no links there in different directories。

 so you can' assume that they're the same file。O。Yeah。Yeah。

 the iode is what distinguishes a unique file so yeah good。Hard links they'd be the same file。

 it's actually the same in。So that's what a hard link does is it it gives different names or different paths to the same iNot。

We can talk about that next week if you really want to see it， but it makes it confusing。

 they're not used。That much acceptable。Yeah。Yeah， yeah exactly right。

 so like if you look at like a file browser， yeah， this would be one of the folder icons and you open it up and you see these other ones or if you show it as a tree。

 then you'll see a tree that looks like this， you see a tree。Okay， so let's go over pads。

 pads are a really important convention to learn about。

 theyll they basically help you uniquely point to one file on this tree。

So let's talk about absolute paths first。So an absolute path。Is。A。Description of all the directories。

That you need to get through in order to find the file that you're referring to so let's say I want to refer to。

This file。c。What does my absolute path look like， well， starting from the root？I put the。Root。

Directorory name， which is always forward slash。And home。

Is the directory that files parent is contained in？

This is the home directory that I have to go through。ThePa directory and then finally。File。c。

So this little convention here is a way to uniquely identify every， at least name of a file。

 so excluding hard links， let's forget about hard links for a second。

 this is how we can uniquely identify every file named。In our file system hierarchy。

And if you are familiar with URLs， web URLs comes from the same concept。

 a unique identifier for some resource， some data。In this case。

 it's on a file system and actually probably predates URLs and probably influenced them。

But this is how this is an absolute path because we start from the root。

And we list every directory that we need to enter in order to find。

The file that we're trying to refer to。Questions on that， does that make sense？变。

Can you replace the power。So paths by convention are the names， not the i note numbers。

 so if you have the i note number you wouldn't need the path you already have a way to refer to the。

The context of the file。🤧So the pads are purely an artifact of this hierarchical file system where directories are mapping names to IO numbers。

🤧好きな。All right， so what would be the absolute path to this file dot C？😡，Sa个。Okay， so root。

 and then what's the next directory？好。So we're trying to go to this file。What's the next directory。

 anyone？中。And we separate drugs with a slash and then yeah， home。Good， Joe。私は？Good， yeah。

 so you can think of an absolute path as just a way to start from the root because there's only one root in the entire file system。

And it tells you each directory that you need to enter。So that you can find。But theyin't file。

In your file trade。🤧。Questions， questions on that。根本な翻なま。

AhThat's because you're on a Windows file system。The Windows file system does not historically have a unique route。

 it has multiple roots。And that was from the doss where each route was like a different hardware device。

水える。And that's the root of one of the storage devices。Yeah， the Linux world。

They have the file system unified into a single tree。

 than if you have other devices as described in the paper。

Those other file systems will be mapped to some directory in this tree。

 I won't worry about this too much but you can basically mount an external disk to be Paul。

 for instance， and that it will be kind of absorbed into this one giant file tree。

This is more for an IT or OS class。Yeah， so windows it does not apply to have。A tree of flag systems。

But yes you can think of C and S， and they also use backslash。As their path separated。

At least historically， okay， questions about absolute path。Pretty straightforward， right。

 it's just a little language or a little sort of way to。Describe a node on a tree。

So I think you all learned about treaties in CS1， CS2， so a URL or a path。Is just a。

Basically one path。Or one trace。Of a path from a root to some leaf node on the tree。Okay。

 so let's talk about relative pests because this is a much， much more confusing part of。

The UniX world。Okay。So in order to understand what a relative path is。

 we have to understand a couple of concepts。There's this notion of a working directory。

And this is a design。Iea in the UniX world that whenever a program is running。

It's running given a initial。Diectctory that it runs in。

So I'm going to use this orange bubble to denote the working directory。So for instance。

 when I was in my。Command line prompt here。This。Teaching COP， et cetera。

 this is the working directory of my Shell program。So any。

Any operations I do will be with respect to that working director yet。Second it， of them。Well。

 so this is a path。So this is the absolute path。that I'm currently in so you know about absolute paths right。

 so there's only one directory that's working you only have one directory that you're working in。

And so this is the working directory that I'm currently in。

And so this is totally just this is a design notion。

 this's a made up notion that the operating system maintains with the running application。

So if I am a running application， like like so for instance。

 if you ever opened up like Firefox your browser， you went to save a file and it just opened up in a specific directory。

Maybe it remembered it， you can think of that as like a working director。

Rather than always starting at the root。The application maintains。A current working directory。

 it's called。So I'm going to denote the current working directory with an orange dot here。

It's a relative path。Is a path that starts from the working directory。

So if this is my current working directory。Now， how can I refer to file。c？Well， I can omit the， okay。

 yeah， go ahead。Right， so by convention， if you omit。The first forward slash， first forward slash。

Because only the root file system is named forward slash。Then if you omit that forward slash。

Then the system assumes that you're referring to a file from the current working directory。

 our current working directory here is。Slash home， slash。

So I'll put here that our current working directory is slash home slash here。

So if I then want to reference file。c if my current working directory。They slash home slash。

So what idea was to do slash Paul。The problem here is we won't be able to know the difference between an absolute path and a relative path。

So by convention。Any paths that start with？Let me use a different color here。ま。Yeah。

 any paths that start with a slash。Means。Absolute。Because that's the root。And I mean。

 this is all by design， something people invented this design， but this is the convention。

That we use in the Uni world， but if you start with a forward slash。

 you're talking only about an absolute path。If it's not a forward slash。

It's always relative and relative to the current working directory。

So if my current working directory has slash home。In order to refer to this file see， I can just say。

Pa。Slash。File dot c。That shorter。千ま？对。I mean， it's a shorter path。

You mean if you're writing on the command line， yeah， it can be shorter on the command line， yeah。

It kind of like。And you're working。这样。Yeah， yeah， you can think it like that。

I don't remember if the paper actually。Goes into this。Yeah， they don't really mention relative paths。

's I think it's just convenience。 It's also that every application。Starts in a working directory。

 yeah， starts running。電話か。I'm sorry， the relative path is just this black。

 this is supposed to be black Yeah， so I'm just trying to highlight what the working directory is。

So let me take this out to make it less confusing， so if this is my working directory。

Then this refers to。So what about file。 here？😔，This file。

 how would I refer to it as a relative path if I already have my working directory being？

So it'll be tall。哦。じ。主有。Bad writing。まが。And file that seat。Questions about relative path。

 you may question why you have a working director。都是た size岁。If you don't specify。

A forward class at the beginning。The file system or the operating system will still be able to find what file you're talking about uniquely。

Because it will just take。The current writing process is working directory。For instance， this。

Path here that the shell is in。And it'll refer to the file from that working director。Yeah对。

It also includes like the do。Yes， so good question， so dot and double dots。

Let's go into dot and double dot。Oops。Okay， quick questions， but before we move on。

 questions on this relative path and the current working director yeah。You can think of it like that。

 so there's this command we'll see next week called PWD which means print Working directory。

 I think the operating system is maintaining the current working directory of the running process。でま。

Sort of， yeah， you can think of it like that， but the operating system is maintaining it yeah。

Is it just basically。That I don't know。I'm not sure。

 I guess an operating system could do that and could use it for caching purposes。

 I think it's really probably designed around the shell。

Because this interactivity so that you'd had you know， in an interactive use of the operating system。

 it's useful to have a current path you're working in so you don't have to write。

holehole paths all the time， so kind of like what you were saying before。

 I think that's probably more the inspiration for it。Okay。

 so let me get into these dot and dot dot directories。So as I said earlier。

 by convention or just by the UniIX standard， every directory has two special directories inside。

And so I didn't write these initially because it makes things a little bit messier。

 but really inside of every。Every one of these directories。Is contained。嗯。yeah。

 I'll just I'll put it on here。Inside of each one of these directories is contained two other special directories。

 adopt do directory。And the dot dot directory。So each one of these。Directories also contains。

Direy called Dot and a director called Dot dot。第二。打た。他。また？嗯。Actually should let me。This is getting。

It's as clear as this too busy？ClClear enough， okay。Okay。

 so it adds a lot of contents to the directory and these are hidden by default when you list things in the Uni system。

呃。Yeah， this is going to get messy really fast， let me make a new。Let me make a new directory tree。

Let's just replicate the home directory here。Li do require。TheyYeah。

 they're mandated by the Unix design。That every directory contains these two special entries。So。

 they are。Always there， at least conceptually。Probably not super easy to look at。嗯。But okay。This。

Doctor Ey。I mean at least he's a different color for this。So this is our working directory here。

This stop directory。Points to。Itself。This parent directory points to。The parent。Of。

So Paul's dodo directory points to his parent。So what about this home directory here？

Its dot directory points to which directory， which directory does the dot directory point to under home？

Oh， so it points to itself。And this dot dot directory， which directory does a pointpoint to？Paul。

 it's parent directory。O。So that's， yeah， good ahead。Out of the directory you？Theyあ like。Not quite。

 we'll see what dot is used for in a second yeah。我 aboutて。じ对。Oh so I left out the rest of this tree。

 but it would refer to this dot dot would refer to。It's parent， which is root。And root。

s to always its parent refers to itself。🤧う。O。So here's my working directory。

 my working directory is still this home directory。And here's a quick quiz。

 so let's say I have the path dot slash。婆。Slash。File。c。

Which node on this tree am I referring to if I say dot/lashp/fi。c？不则。The first home this one。

This is my working directory。So okay， so there's two file do Cs on this tree， which one does this？

Path refer to this filedy or this file。🤧De one。So why is that because my working directory？It's tall。

And when I go to the dot directory。Well， that's just。Referring back to the same home director。

So now I'm in the home directory and I say go to the Paul directory and go here。

And when I go to the file。C directory， I go here。Yeah。Between the dog flash ball。

In terms of the file it refers to nothing， it's the same file。Because we have these。

Back edges on the tree， we could also say something like dot， slash dot， slash dot， slash dot。

Flash Paul slash file。Which file does this refer to？The same one filed that here。

So dot is like a cycle， it points to itself， so you can say dot slash dot slash as many times you like and it's still the same directory yeah。

Just dot Paul。So dot is allowed in file names， so this would be referring to a file called dot Paul insideside of the Home directory。

 but that file doesn't exist。So I could have a file named。You know， dot Paul。Dot text。

And that is a legal file name。The US。Yeah。So why have dots left so there let's see？

I thisI put this in my notes somewhere。But I else。So why would you want to have dot slash？Yes。

So yeah， you've probably encountered this running and executable。 You've， you've tried to build like。

Your。Hello program I build Hello。c have this program or I now have this program called hellello。

And it doesn't run。So one reason that Hello is used is to make clearly distinguish。Hello。

 which is a program that's installed on your system from one that's in your current directory。

So by default， the UniI system won't run applications from your current directory。Instead。

 it looks at I was， I think I was going to talk about this next week， but instead it'll look at。

A series of predefined directories where executables are installed。

And look in those directories for an executable。So in order to explicitly tell your exactec function that you want to explicitly give a path。

You can use dot instead of writing out the whole working directory， you can use dot to refer。

 think of dot as referring to current working directory， that's one way that you can use it。Yeah。

That's similar joy。こな後は。Source。You don't have to like source python。Yeah， exactly。

 so if you run Python， yeah， yeah， if it's installed in one of these predefined or these system defined directories。

The best shell will look for in your paths it'll look for that direct that that program and execute it so that's like one of the main reasons I can think of it also just makes it explicit that you're saying。

This is the directory that I'm referring to rather than providing no directory。Okay。

 we have a little bit left。All right， so doc directory， it may seem a little superfluous。

 but the one place you do use it is when you write C programs， you want to execute it。

You say dot slash because and now hopefully you know the reason for it， the reason is that。

Uix will not just run programs assuming that they're in your current working directory。

 it's also kind of a good safety reason to do that so you don't accidentally run a program that you didn't want to run。

 but what dot slash does is it just explicitly refers to your current working directory so that when you want to run a program you just say this is the directory I'm running it from so you can think of programs if they're not in your system paths。

 you have to give a full path either relative or absolute to that program in order to execute it。

Questions on the dot path。So this is again， just like the hierarchical file system。

 it's designed by people， you just have to remember it。It has some other use as well。

 but I can't remember that right now， but it's anytime you want to explicitly refer to your current working directory。

Yeah。name was adopted。No， the name of the dot is dot。

So if you look at the so I'll talk about this next time。

 but there are any files beginning with a dot are hidden by default。

 they won't be printed out by this by the you know convention and so they're literally named dot in the。

And you can even print out there。Theyre in numbers and they are the i note numbers of the directory。

Oh yeah， yeah， yeah， yeah。Sure， yeah， so every directory contains a dot directory and a dot dot directory。

 so let's look at Paul here， so Paul's， I made this treat really complicated so Paul's dot dot directory。

So what is really going on under the hood is that the directory has an entry。😡。

Whose string name is dot dot and its i note number is the i note number。

And to make this more sort of mechanical。And it also has a dot directory。

 the string name is literally dot。And that dot directory has the iode number of。The very directory。

That is itself it has its own i note number。In its director Andrew。まこれピる。F， that's it。

So it depends on what your current working directory is if your current director directory is here at home slash。

Then you would just say dot to refer to the current directory， which is home slash。

Let me zoom out a little bit current working directors home slash Paul。

 which is a directory within home。And file。se， which is in Paul。But that makes sense。Questions。

 questions on that， more questions on that。If your working director is Paul， okay。

 good question so if your working directory is Paul。Then how would you refer to file。c。

 there's a number of ways。What's one with？Yeah， you can say dot slash file see if your current working directory is Paul。

 then you can say dot slash， which refers to this directory。File that seat Yeah so。Is running。す。

So period one。Right out。I think by default， the shell will make whatever your current working directory of the shell is。

 the current working directory of the running program。

So you can run programs that are in other directories。

 but the working director would be the one that your shell is currently in。So it might have。Well。

 yeah， if you've ever had to like try to write scripts and you sort of forgot about the relative or you just just assumed things about the paths。

 yeah， you can run into problems。Very quickly， yeah。这个？Z d四四 d。CD， oh change directory。

we'll talk about the next week， we'll talk about next week Okay so one more thing I know you're eager to go we have do have three more minutes left。

 the class is till 20， I think。So okay， the dot dot， this is a much more useful one。

 dot dot refers to the parent directory。So let's say this is my working director again home。

And I want to refer to Ex， yeah and I want to refer to say。This Paul here。If I say dot slash。

He's black。If I say dot slash home。Slash Paul。That's the same thing as saying。No， that's not right。

If I say dot slash Paul。That's the same thing as saying dot dot home。Slash Paul。

So dot refers to home slash Paul。If I say dot dot。That refers to the parent， which is root。

Then I say， home。And Paul。So D just refers to whatever the parent directory is。

So as we'll see next week when we do navigation， this makes it very convenient for you to work。

 move around your file system interactively。And do file operation。All right。

 so that's relative paths。We talked about the working directory， we talked about parents directories。

So just to wrap this up， the file abstraction is used for all sorts of things， not just storage。

 it's used for networks pipes， RAM itself， you can actually touch RAM through the file system if you like graphics cards。

 things like this all right， so you can look at the notes for the rest of this。And oh yeah。

 your homework。Your homework。So your homework is to take this table of paths。

 I've given you absolute and relative paths here。And just construct a tree that contains all of these files and directories in the right place on the tree。

That kind of makes sense， questions on that， questions on that， homework， yeah。边位我。

You can do it on paper， you can do ASCI art either way。All right， take care everyone。



![](img/da68893ba5c517e8c08dd7f6cf464dfb_6.png)