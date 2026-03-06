# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p14 P14 Systems programming： Midterm review (COP-3402 Fall 2024) -BV1v6vdBKEHB_p14-

All right， welcome back to System softwareware。 We finished our system programming section。

 and now we're on to the midterm。 So today we'll be reviewing。Everything you'll need for the exam。

 the exam is created， I have the answer sheet。And I've tried to make sure to cover everything that's on the exam in this set of questions。

 so it' go over them today， stop me about what you need more clarification on。

 what's more useful to you。But let me go over some of the mechanics first。

 so this will be next Tuesday in person if you have。

Accommodations with SAS that will be uploaded I still need to upload that but that'll be uploaded you'll be able to do that there if you talk to me separately about needing to move it I know we move the exam so most people don't seem to have a problem with it。

 but there I think there are some people who still need to move it make sure remind me willll do a makeup a modified version of the exam for the makeup。

But okay， here's the you know， the syllabus had some description of the midterm。

 material will be taken from homework， projects and lectures。We'll talk about final later。

 this is our in class review， you can bring notes。Make them reasonably sized。

 don't play any tricks with you know like magnifying glass or， don't put answers。

 complete answers if you'd like somehow figure out what the questions are。

 but otherwise eight double sized pages， these should be letter pages I should probably specify trying to avoid gaming。

 I'm sure someone will figure out ways to game this but yeah so eight lecture doublesided pages of notes。

It's got to be held during class。This is the set of questions， the types。

 so there'll be six multiple choice questions， seven short answer questions。

 so they might not be easy， but the answer will be no longer than you know。

Probably a few words or a sentence。And there are three long answer。Questions， which could be coding。

 which could be long form description。Writing file trees。呃。Writing algorithms， writing C code。

There'll be a separate， I like to have a separate answer sheet that makes grading easier。

 and so I've put the actual answer sheet， what it looks like so you don't have any surprises in the format if people you have issues with。



![](img/6cc703f4520c87175a25a1fbec099ff0_1.png)

As I do with the notation and format of things being confusing during exam day so there's no surprises here on what the answer sheet looks like。

 so here's your six multiple choice questions they come first。

 here's your seven short answer questions andm almost positive you'll be able to write in all of these if you have reasonably sized handwriting。

And then there are three open ended questions so this question。I think this is enough space for you。

 I think this is enough space for you here in 15 and 16， this should be enough space for 16。嗯。

These will all be printed individual pages so the back will be available you know if you really need it。

 scratch paper will be available if you need it， I'll try to make sure to bring extras of these。

 sit on remind me to bring extra or sit on print out extra ones。In case people make mistakes。

Make sure you put your name and your NID on each page because I think we're not going to staple these just to make grading easier。

 so name and NID on each page。Questions about the format。Yeah。Oh that's a good question yeah。

 I don't see why they can't be typed yeah。That's a good question。

So this is what the exam answer sheet looks like， and then the exam question sheet。

 that's a secret until Tuesday。

![](img/6cc703f4520c87175a25a1fbec099ff0_3.png)

But it's sort of a subset of the content here。That will go over today Any other questions about the exam format。

 so yeah， no other items unless you'll have specific accommodations besides your writing implement and the paper on your desk。

 put your full name and NID on every page can't emphasize that enough。



![](img/6cc703f4520c87175a25a1fbec099ff0_5.png)

Make sure you do the course policies about cheating and unauthorized assistance with coursework。

 including exams。

![](img/6cc703f4520c87175a25a1fbec099ff0_7.png)

Yeah， so the exams worth eight points。So if you remember my clever little grading scheme for the class。

 a point in the class is one percentage point of your grade。And because there's 16 questions。

 I like nice round even numbers， each question on the exam is worth half a point regardless of difficulty in the past I found if you make harder questions。

 have more points then actually it definitely makes that much harder。

 but yeah so 16 questions half a point each so you can expect exactly how this is going to affect your total grade。

Sa what。Yeah， yeah we'll do partial credit， so I'll be grading the long form ones or at least overviewing the grading and of course you can come to office hours。

 argue for grades。 yeah， so yeah they'll be partial credit like025 of a point or whatever。

 but yeah I'll give I'll try to come up with a rubric for partial credit that applies applies there one you can always come to office hours and let me know if I make a if you make a mistake in grading for sure。



![](img/6cc703f4520c87175a25a1fbec099ff0_9.png)

All right， other questions before we get to the content？All right。So let's go over the questions。

File systems， what makes a UniX file system hierarchical， this was in the reading。

 we talked about this in class， what does this mean and why is it the case？Yeah。

So what are the types of files that can have children in this hierarchy？

Directories and what are directories are they。Our directory'iess files。Yeah。

 directors are just other types of files， and what's the content of a directory？A yeah， it's a list。

 it's a data structure， it's like a mapping， a dictionary between names。Yeah。

 it's related related to Home that。 so you can think of a directory as a。

Single level tree where the directory is a file that contains a mapping of other files。

And so that gets at why it's hierarchical because if directories are also files and directories can contain any types of files。

 including directories。You can create this tree。This hierarchical tree of files and directories。

And in fact， with hard links， it actually ends up being like a dag。For our purposes。

 we'll just think of it as a tree。All right questions on that。🤧嗯。And yeah。

 recall the homework that we had for that。We had a couple of pieces of home or just one。

A bit of homework for that。Where I ask you to look at a set of paths and reconstruct the file tree。

So let's， let's go into that。 What is what's difference between absolute。 Well， first of all。

 what's a path。In the context of a file system。It's like an address， so how does it work？Exactly。

 I how to get to house to do the other directories starting from where in the UniX world。The root。

 the root or yeah， or the working directory short or the working directory。

 so which is which what's the difference between starting from the working directory versus starting from the absolute oh oh my God。

 starting from the root directory， I just gave the answer yeah。Exactly， which is which。

 so which is the absolute？From the root good and the relatives。Working director， all right。

 very good， so that's difference Institute absolute relative paths。

So if you're in a working directory， oh yeah， sorry， question。Well， they start with no slash。

 they start from the working directory， why is it the case that？

So why is it the case that if I have a relative path like， you know， like let's just say bin？Hello。

 why is it the case？That these two relative paths point to the same file。Yeah。

 dot points to the directory itself。 So it's not that dot slash is another way to specify。

A relative path from the working directory， It's just that you're starting from the working directory and then you're pointing to the same directory。

And you can do that， that's why if you do dots top I top slash。

This will be the same file as this and this and this and this， these are all the same file。

The dot is just a pointer too。😡，The directory itself and actually in that case， it's not just a bagg。

 it's actually a graph of cycles if you include these special directories。Okay， so in that same vein。

 how do we so this is how we reference the current directory if we're in a relative path or if we're in any path。

 then we want to reference the parent directory。Dot do。All right， good。嗯。

And so all I may ask you questions like here's a file tree。Let let me get the notes from this。

So we did this。We did this in class， so for instance。

 if I give you a file tree and say what's the path， what's the absolute path to Joe？

What would you say？Yeah。Yeah， good so here actually at the。The route was missing， but it's the same。

 yeah slash home， slash Paul slash home， slash Joe， so like right here。

This part of the path is the absolute path to the Joe file。

Good question so what's the difference between having the slash at the beginning and not having a slash？

Yeah， so if it's a slash， it's an absolute path， which means it always starts from the root if there's no sla。

 yeah。

![](img/6cc703f4520c87175a25a1fbec099ff0_11.png)

Exactly， exactly， that's how to tell a difference。That's why if you saw。

 there was a little trick here in the homework too。That said， here's your working directory。

 but we have an absolute path。So the working directory is irrelevant in determining。

The location of a file， given an absolute path， you always start from the route。If there's no slash。

 it's a relative path and relative to what？The working directory。

 So you have to know the working directory in order to。Use a relative path。So here。嗯。

You might be asked to reference a file from working directory or give an absolute path。Yeah。

 that that's a good question。Usually， well， so in the most of the tools。

 if you put a slash at the end of a directory， it'll interpret it as a directory。Um。

It really depends on how you're using the file， so I think most of the time when you see tooling they'll omit the path at the end。

 there are some tools where the path the slash does actually make a difference。

 but you can think of ending a file with a slash kind of designates it as a directory in some sense but no it's really part of the URL。

 the file separator for the URL， so the name of the file for instance does not include the name of re does not include the slash。

So if you look at the directory entries like。Here。This files is a folder as a directory and the name of it does not include the slash slash is really part of the the。

Pa。All right， and you may need to draw a file system tree， just like in homeworkmark3。homework too。

 sorry。All right， questions on file systems。All right， all right， let's go over navigation。

So I think we all over what the working directory is。

What's the command in Dash for displaying the work PWD a good print working directory。

 all right good， what about renaming a file， how do you rename a file in the UniX world？Move MV。

 good， what's， Yeah， let's our？Exactly， yeah， old name and new name。

 and move also will move files between directors as well。T completion， what does TA completion do？

Yeah， kind of autofills， files， commands。Actually， anything。

 you can actually write a tool and write your own little completion specification and have completion work on your own tool。

やての。Hitting tab， that's a Windows thing， hitting tab several times in the UniX world will。

If it completes。It'll add of space and then hitting tab again will give you all available files as an option。

 depending on the context of the tab。There's not a single file that matches your prefix。

 it will show you all the available files rather than saying it， let me show it。

So if I do LSP and I hit tab many times it's going to show me all of the possible completions from this prefix and then if I hit tabab when there's only a unique completion。

 it'll give me the completion and you can actually see it actually automatically puts the slash for me as well because it's a directory。

Okay， so T completion， you should all be using it。 You should all be using the command line。

 I really want everyone to use the command line。 I knows it's a struggle for some。

 And I said I know some love it and some like。It's a drag， but use tab completion。

 and it'll be a loty here。The first one。So how do you display the working directory。

 what's the command to show you the working directory？不在。PWD， PWD， Yeah， so WD， like yeah。

 WD is the kind of abbreviation for working directory， PWD， so rename a file， it's MV for move。

What's Grp do？Does anyone remember what Cft does， yeah？And which file does it search？True， yeah。

 if you give it a file， it will search that file。What if you don't give a file， what file does it？

Well， if I just say Gr。By itself。Let's say I want to grab for the word hello， yeah。Standard in， yeah。

 this is the UniX convention that these standard tools use standard in and out and so without any other arguments running these commands。

 I mean you have to give the match command the string you want to match without any of the arguments。

 it just pulls from standard in so I can just start typing。In my dash prompt here。

Because when you run a bash thing as we talked about last time。

 when you run bash and you fork a process from bash， it inherits standard in and standard out。

 so Gr inherits standard in standard out， which is my terminal。Now。

 a lot of these commands also allow arguments。To be given as well。

 So the first argument is the string to match。And then the other arguments are the files you want to match。

 so it'll not use standard in instead it'll use whatever file you open。

 probably just redirecting it internally， I don't know how GrP is written。

 but it may do something like that you can actually grip all files with star stars like will expand to all the current files but anyway。

 this is and you can do redirection as well are the file redirection。Okay， so that's what GEP does。

 GEP matches。A string in each line。Of the input file。

So it does string matching for you so the REE there I don't know what the whole term is for。

 but the RE is like regular expression and you can do some more powerful matching I don't really know why it's called GrP。

 maybe global regular expression or something like that I don't know why it's called that。

But the REE part is like regular expressions， if you took discrete， you may have learned about these。

Okay， how do you change your working directory in Bsh， CD， CD， change directory。

 how do you change director your home directory？CD slash。So what does CD slash do。

 what kind of path is it slashed by itself？Absolute to wear the root， yeah， very good。

 so what was your correction？Tilda， yeah， you can also do just C D by itself and。



![](img/6cc703f4520c87175a25a1fbec099ff0_13.png)

knowGood having good defaults， this is another kind of unix or system design philosophy。

 have good defaults。

![](img/6cc703f4520c87175a25a1fbec099ff0_15.png)

So CDD itself will just go to your home directory。And another trick that I was trying to point out to。

Wops， a student today this。Just for your own kind of speed speed hack。

 C hyphen will go to the last directory you are in。So if you repeatedly type CD hyphen。

 you'll toggle back and forth between two directories， it's a little trick I use frequently。Okay。

 how do you delete a file in Uni？RM for remove。And how does this work。

 is the content of the file wiped from your disk when you do RM？No， why， what happens？

What file gets edited when you type RM？😡，The directory， yeah， the directory gets edited。😡。

Because the name of a file is not part of the data in the file。

It's created by the directory which maps names to files and so remove can be very。

 very fast because all you have to do is just delete the entry。

 it's like deleting a name from a phone book， the phone numbers still there but that association between the name and the phone book is gone this is also why you know like computer forensics experts can recover so-called deleted files because they're not actually deleted from storage the content of them yeah。

Yeah， actually there is， there's a tool called shhred。Let me see if this is on Eustace。

 So this is the kind of standard， I guess it's a standard。Yeah， there's a tool called shred。Which。

So it doesn't remove the file by default， it overwrites the contents of it。

 which is really the only way to delete in the sense of removing the contents of a file。know。

 that storage medium is still there。And there are even， I don't know computer forensics well。

 but apparently， even if you overwrite it once， the like low level， like magnetism of the。

If it's spinning this hard drive will have some like remnants of the original setting that it had。

 so these shred commands run will overwrite many times with like random data and zeros。

 this is outside my expertise is like computer forensic world。

 also if you try to do this on say an SSD。Soli state drive。

Unlike a hard spinning disk drive where you actually can tell it where the kernel will tell where on the disk to make changes to the disk。

 the SSD will。Change where in the physical medium the placement of a bitete of that disk so in other words。

 the reason for this is that SSDs have like a lifetime of writing。

 they'll wear out and so there's algorithms called where leveling which will change where you read and write files from even if it's the same file so if you open up a file and rewrite it or you edit a file it might actually be stored in a different part of the physical medium。

 so even if you try to delete do this on an SSD drive， your data may still be there and recoverable。

So if you're worried about privacy， use encryption， use full disk encryption。

 I'm sure there are problems with that as well， but that'll make sure that the data is not readable without。

You doing something to dec the data。But yeah， good question。 So yeah， shred。

 shhred will let me not do this。So shred will not even delete the file。It'll just， well。

 it has no content in it， but it'll just overwrite the contents of the file and then you can tell it to。

With D year， I think you can tell to delete delete the file anyway， Yeah， so yeah， good question。

All right， any other questions on navigation， so know the comment comment yeah。我在。RMD。 Yeah， good。

 Yeah。 So just yeah， review that in the navigation section， there's like。

Several tables here that show the command。 So what does cat do？Prince and where does it print it to？

Good more than anyone remember more。It's like cat， but it does screenfuls at a time。Less。

It's the same thing that you can navigate backwards and forwards through the file I don't think I ask about these on yeah。

つは先生そ。こいあ。I mean， well， there are multiple answers， right， you know you can use an editor， right。

 you can use VI to show the content of the file。No， no， you can do a command， yeah， of course。

 of course。You can mean， as an instructor， you can't ask a question that has multiple answers and then penalize somebody for giving a right answer。

That's。Yeah， that's not right， that's not right。Yeah， and so I don't think I ask about these。

 but W get， you saw these your in your example， so you should definitely know these。

What does touch do？It creates a new file， it's basically making a new entry。

 making a new file that has no content and no data in it， but sets up the file in the storage medium。

I don't know， Well touch also， so what touch does is it。It。So they know making new file here。

Actually， let me go to my， Where's my。Scratch folder。

So what touch really does is it updates the metadata of a file。

So you can see it updates the access and modification times of a file to the current time。

 So that's that's like what the tool is meant to or like nominally it's supposed to do。

 So here I've got a readme file that was made at 1214。

 If I were on touch on readme the file already exists。 you can see now。The readMe file is 1247。

So that's what touch really does， but it will like by default， create the file for you。

Some design decision by the creator this yeah。Yeah， yeah。

 you can make a file with the net or you can make a file by redirecting to it。Using redirection。

So you'll see me do that a lot in class， I made this new file just by using CA。Yeah。

 this is kind of the beauty of these set of Mu tools， it's kind of like Lego blocks。

 you can arrange these however you like to achieve the same purpose or achieve lots of different purposes can。

Build these up together without having to actually write any C code at all。

 you can just use these existing tools to solve common sets of problems。All right。

 other questions on navigation。All right， processes， so this is like the command line process stuff。

Yeah， so how do you redirect standard standard IO to a file， so if you want to redirect GP or CA。

 how do you redirect file to files to and from files？Yeah， greater than sign， less than sign。

 which one's redirect standard out？Greater than which one's threedirect standard in？Le that， good。

 okay。How do you redirect standard out from one command to standard in to another command？Pippe。

 good。 Yeah， the pipe command。 So the vertical bar。 So I always show L S。Pped to WC， what's WC do？

Word count， What's LS do list， LS list， Yeah， good， Okay， so well， not everyone is calling it out。

 Some people are， but any questions， any questions on us。

Oh so sorry about that this is my muscle memory of like show hidden files。

 show them in a list format with metadata， sort by time， reverse sort by time。

 and then human readable sizes， so I just I kind of worked this out like 10 years ago and just like remembered it rather than making the yeah。

Oh， that's a pen。Aend and then double input sign is a here document。

 but you don't need to worry about that， you can write a whole document until the end of it。

 but yeah they're called here Do and double greater than sign is append。

 so if I go to new file again。This is appended。Oops， I didn't pan。This is really authentic。So yeah。

 that depends all right other questions on。Proce is on the command line。Yep， exactly LS pipe WC。

Exactly， so you take LSS standard out， which would have been this。

 so let's say there's four lines here。And then I can do to WC。

 they'll do word count so there's five lines， so this is the number number of lines。

 or I can pass it to GP and say， giveive me all the lines that have hello in it。

And you can see GrP will filter out the output of LS。So greater than redirects to a file。

This is my output。You see that's the output of the command and then input。呃。

So if I search for 15 in this output file that redirects the input， so I took this file。

 which of the contents are here， redirect it into GP and it'll match all the lines that have 15 of it。

O。Editor。How do you edit files in VIm or EMX？诶。I want to make sure， everyone knows。

 I'm going to get someone new。Yeah。Then the name of the file， okay， how do you quit？Right。と論で。

Gool and WQ， okay， good。 What's in between W and Q and Vim？Yeah。WCs you quits。

 you can even do them separately， what about EMX or are my EMX users？Control X control C。

 that's how you quit， how do you save any max？Ctrol X， control X， okay， okay， good。Yeah。

This is exclusive or， so one or the other。No， no nano。

 no nanono you if you want the Na experience use EmX because Emax is more wizzy wig like you can use the hours and stuff。

 I'm going to try to spungge nanono from from just look online the kind of。

Or people fight about Vmerimax， but they don't fight about nanono in the like。Elite community。

 you know， the elite hex or community。But yeah， I don't use nano。It's kind of slow to use。Okay。

 that's the editor。Not not going to ask too much about that。

 I hope everyone is using the command line editor， I know might be a little bit of a struggle。

 but I hope everybody's using the command line。All right， build automation。

 this is one that we definitely should review because I think this one's pretty esoteric。嗯。

Wheres my question any close on to this？Okay， so。I'm sure everybody completely remembers this and has it imprinted in their mind。

 but the syntax of a make rule is very esoteric syntax。What's the target for？Yeah。Yeah， yeah。

 that's what you type in。嗯。And it's what the user types in and what is the target supposed to be after you type it？

Could be exutable？It can be anything， it's supposed to be。

 it's telling me this is the file I'm creating。So when you say make hello。It's you're telling。

 make that。This is the file that I'm generating。And so that's important because if that other files depend on it。

 make is going to look at that rule。To build that file。

So target is the file that you're creating from this rule。

 so this whole thing is a rule that will generate some file。

So what we talked about in class is generating。A program binary from source files。

 but it could be anything， it could be generated documentation。It could be。

It could be publishing my course， which is what I actually use a build file to publish this course and generate it yeah。

Absolutely， yeah， so let's talk about prerequisites so yeah and actually if you don't oh yeah， okay。

 let's talk about prerequisites， what are prerequisites so yeah yes guys what arerequisites。Right。

 things things you need in order to build this recipe， so if this is。

Or's an example of this so for instance， here。In this build script。

 if the thing I'm generating is the main executable or some file called mainine。

The prerequiites are saying in order to build this， you first need to build these dot files。

So that make uses this information in order to automatically order the sequence。

Bils for you so because you've told make， okay， I need these built first before I can build Ma。

 when you go to try to build Maine， make will automatically look for how to build each of these prerequisites yeah。

嗯。So you definitely don't have to name the binary after the source files and in fact。

 when you have a large program with lots of source files， you may not at all。

 so like Linux for instance， I don't think there's any Linux。C file。

 but the resulting binary depending on how you build is called VM Linux。

But all the files are called other things。Colonnal scheduler or something like that are called other things So yeah don't you don't have to at all you're free to make this whatever you want You do want to make sure that this main is generated by the recipe you've written here。

Because otherwise， if something else depends on Maine。

 make is going to try to build it and it's not going to work， and then your build is going to fail。

But if it's the last thing being built then， it actually kind of doesn't matter。Yeah， yeah yeah。Yeah。

 yeah， this is insensitive to the order of arguments and optional arguments。、それで。Ex example a cフ。

Well， so this is how you actually compile a C file。In with Gcc。

 the dash C flag will just compile that source file when you call Gcc without dash C without any other arguments。

 so it' is just telling what the output should be， it's doing more than just compiling。

 it's also linking it。And we'll talk about that after the exam when we get into how the system works。

Oh， yeah。Ah， well so。So okay， so yeah， I was a little strict in that saying built first。

 they have to exist on the file system first。嗯。And so if a file already exists and there's no build rule for it。

 then make will just use that file， so yeah it's a good catch。

 so this is kind of the leaves of the tree。That's how make stops building but yeah。

 so if you have a file that exists already and there's no rule to build it then it'll just use the file in the file system it's just like super integrated with the file system because it assumes that you know。

And there's no check on this， but it assumes that the recipe will create whatever the name of your target is。

 that's the convention。But yeah， good question。So yeah。

 this rule here is saying mainine do see is burex， it must exist。

Not necessarily be built but must exist before it， and if it doesn't exist like in the case of these。

 or if it exists， but it's stale that the file modification stamp is older or is。Older。

 and it needs to be built older then。This one， then it needs to be rebuilt。

 so it'll go out and build it， but good catch， you have a question。

Dashhow is just telling GCC the name of the binary to create。

 so without Dhow what binary gets created or what's the name of the file？8 out out。

If you ever just ran like if you're on Gcc hello。c， you'll get A do out by default， so again。

 you know UniX philosophy have good defaults or have a default。

 A do out is the default program that gets created， dashhow changes the name of that file。

From A out out to now it'll be main instead。AndSo that's all this does。So technically no。

 it's inexecutable， so we'll talk about that more in next week。Yeah。

 GCC is doing a lot more than compiling when you run GCC。

 and one of the things it does is it links and creates an executable file。

That's ready for the system to load it and run it。呃。Yeah。

 so the object files are just the compiled C source code to a binary。

 but we'll talk about that more next。Thursday after the exam。All right。

 and then the last piece of the make file the recipe， what's the recipe？Well。

 technically this whole thing's called the rule， so more specifically， what goes in the recipe？

What to do， what to do to do what？Yeah， to build the target， yeah。

 the set of commands to run in order to generate this file。So now strictly speaking。

 if you make a mistake。If you put hello here instead of Maine。Then。

Your recipe is sort of written incorrectly， makes not going to check that。

 I don't know if there's a make static analyzer that will check that for you。

But you can certainly make a mistake。And not actually generate this。 So for instance， here。

If I wrote gcccc hellello。c。Maine。0 would not be created。And so every time you go to Bill Main。

 it would think， okay， this is still missing， it wouldn't get created。But anyway。

 this is supposed to be the sequence of commands that make should run in order to generate the target。

So just to review， the target is the file， the name of the file that you want to create。

The recipe is the sequence of instructions that create that file。

 and the prerequisites are the files that should exist。

Before you go to run this recipe to create the target。Questions， questions on this。

There's a whole bunch of other wrinkles of make files like phony targets and all this stuff。

 which you just tell makeFile that this will never be a file so don't try to look for a file。

 but these are the broad strokes of what a make fileile rule does。And the beauty of it is that。

You can declare how to build each part of your tool。

 including documentation or generated files and build that make will figure out the order。

Things to run in order to build it for you， so especially in to get into bigger projects。

 this kind of build automation is really key。Annoying to maintain this in some script file。

Kind of more brittle to do that。All right， other questions on， well。

 let's see what other questionss I have for make。Im sorry by convention， what's the clean target do？

Yeah。And what are those， yeah， so what are those command with？Remove what？Which files？Yeah。

 executable to binaries， the generated stuff， so by convention clean removes the generated stuff。

And you have to write that yourself， you know， sort of more modern build automation will like help manage this for you。

 but in the make world is just done by convention。And then be able to write a make file that will。

You know， just be able to make file for like hellello world that has two source files。

 and so there's an example of this。In here， this is building a binary multiple source files yeah。No。

 yeah that's not about funny tell。All right， any other questions on build automation？Yeah。Oh。

 this one。So this step here is just doing linking it's not actually compiling the source code because I'm just passing the object files I'm not going to ask you this kind of detail about this part of this this will be next Thursday yeah。

Y， you have the whole class time， an hour and 20 minutes。

that's what's in my UCF it's an hour and 20 minutes。The semester， so yeah。Okay。

 what Gi command copies from the local repository to the remote repository？Push， good。Bush。

Which get command copies from the remote to the local。Pll， I think I didn't really。

 we didn't have to use this in class but that poll。Yeah， I'd accept comm I'd accept clonene too。

 yeah， so clone， yeah， clone creates an initial， yeah， clone also does that， that's true。

What about staging a new file？Add and then which command creates a log of the change to a staged file to the local repository that's commit。

 that's just a long minutes way to say commit。Then you can use add。

You can use ad to do that there's like an interactive ad， I never ever use this command。

 but you can do add to stage I just use my EmX integrated thing to stage stuff。But yeah。

 you can use I don't know any other way to do it。All right， so that's version control。

Other questions on Git？All rightLet's get into the more recent， slightly harder stuff。U。

Using the open cis call。Open a path。Given given some string in the file path variable。

So how to you use the open cis call to do this can go into the。Using files。

So here's an example of using Open。That's how you do it， you just give the path and some。

Can say read only， you can give anything you like here， I just ask for open。Any questions on that。

 that's literally just how you use the Open Ci call。要是さ的場だ。Second again。We look all。

I read only is what？I mean， yeah， these are all numbers， but this is yeah， yeah， these are all like。

These are defined by the system。But the whole point of having a name for them is you don't need to know。

The number these are。O不是。These are in the。These are given to you here。And。

And their man page has the full list of them。You can see here。 So here's。Read out。

But I'm not going to ask you the details about those flags， we didn't really go over that class。

I basically just want you to be of a right。A system call。Okay， so and then you know。

 how do you check for errors？In the open cis call or other system calls。この正ろ。Not quite。

 so the error number is not guaranteed to be written if there's no error。

 so don't check the error number。I saw this rumor going around。

 don't check the error number to check for this call， yeah。So good。Yeah。

 you check the return value of open。So yeah， don't check air no because A no won't be written if there is an error。

 so if you had an older error that you recovered from。

 you may check error number and get some stale information。

So yeah the way you do error management of the system calls is check the return value of the system call。

For most of these， it's negative one， some of them it's not。嗯。

You don't have to remember exact in detail the man page， you know。

 just remember the witch ci calls there are， what they do， yeah。For that statement。Fwall records。

Standard error yeah， yeah， so why is standard error， why can you be sure that standard error exists？

It's part of a standard IO， it's part of the convention。

 and that is supported by the kernel that whenever a process is created， you get three open files。

In out and error。So as long as when the process is created。

 you'll be guaranteed to have an open file for standard error。比。Can use what。

PR yeah for sure for sure。 So I show this in class。 Oh this is F print F。 let me here's the error。

 the PR version。 Ab you can use PR。 So if you sort of know this snippet of code。

 this kind of encapsulates calling system calls， checking for errors， printing out the error。

 So if you can do this。It should be good。Okay， so a little long winded。

 but how do you use the read system call to read 200 bytes of a file that's already open。

 so let's say FD's already open yeah how do you read 200 bytes from it？Yeah， you can do that。

 that's like the Linux programming book had done that。Here's an example of using read。

 so you need a buffer。You can make a single character， you can have a 200 buffer， you can have a 100。

 if you like， easiest way to do it is just make a buffer of the size 200。And then call read。

 passing the file descriptor。The buffer， the number of bitetes to read。

And then here's error checking。But this is how use the read cis call。

So the main thing to remember here is that you know。

 you assume you already have an open file descriptor from open， that three turn value open。

 you need to give the kernel。Some allocated space， a buffer。

And you need to tell the kernel how many bytes you want to read。That's the read system call。Okay。

Write a program that uses Open Deer and read Dear to list the names of files in the current working directory。

This one probably should sound familiar。So that's here。That's this program。

 so I know it looks like a lot， but there's only three commands。

 what are the three system calls you need to do this。Open dear。Read dear。Close here。

So what does open Deer give you？Gives you this pointer to some structure。

 this is actually a library call， the manual page recommends not using the system for this。

 but this library call gives you this pointer to a directory。And then every time you call redeer。

 it gives you the next directory entry。So what system call will give you？

Information about a file like， oh， sorry， question。Yeah。Yeah。

 I mean ideally yeah you do the error handling that's the right way to do it。

 but yeah we can talk about partial credit when we get to the exam or what system call will give you this yeah size number hard lengths。

 stat， yeah exactly stat so there's an example here of using stat。

I'm not going to make you remember like all these very specific。Data structures and return values。

Okay。What cisol can you use to find the name of a file？Yeah。Yeah。Well， that's not a cis call right。

 that's a data structure， so what's cis call。水重とオーペンで。これでこでロて。完全い由で。Yeah。

 so the trick here is just a reminder that files don't contain their own names necessarily。

 it's the directory that does it， so you would need to use Open Deer and read Deer somehow。

If you actually had an open file description you somehow didn't know the path。

 you probably have to just like search through your whole file system to like find that file somehow。

O。Questions on file system calls， so just know the main system calls， these are listed。

In table form here， these are the main system calls。

 you don't need like what I call it a photographic memory image of the entire man page。

 but just sort of know how these system calls use know that they you need to do air checking。

 know that。You need to give a buffer for a read， know that you loop over， read deer over and over。

Yeah， you can assume heteroerophiling good， yeah。It doesn't have to be exactly compilable code。

 but you should have the system calls。The order of the inputs doesn't matter as long as you get the right inputs。

 the error checking should be more or less right， but you know， if you don't have a。

memoryory of the exact， I don't want you to print out the man pages for all these， you know。

 so don't't worry about that， but just have you know the fundamentals of what their IO is。

And that's sufficient。All right。Processes， pipe system， oh yeah。小会有啊。あかこう。Pro very important on。

The very。No， you don't need to know， yeah， yeah don't worry about that。

 I didn't even show that in class。Okay， so how do we use。Standard cis。

 new standard Cis calls to create a new process that runs the LS command。Fork。Are we done。

 so let's say I'm Dash and I call Fork， am I running LS now？No， exec， yes， you need Fork and execs。

 remember， to create a new running program。ADifferent running program in Munichix， you Fork。

 and what does Fork do？Duplicates the existing process， including its program code。

And then how do you change what program a process is running？Exec， no new process is created。

 it's literally just changing the program text。Okay。呃。So same idea， write write a oh yeah。

 so write a program that。Creates a new process。Where the original process writes the word parentent and the new process writes childd。

So could you write that code？Let's take a look at the process creation。

So this is that code I mean actually that's the。This is that code。So you call fork。

And how do you tell whether you're in the child or the parent？The idea。

 the process I that gets returned。Process zero means or return value zero means you're in the child。

Negative one is an error， and then otherwise you're in the child。So if you can， you know。

 just remember that PIB， what， you know， just remember the IO of Fork， what is the input to Fork？

Nothing， you just call fork and magically the kernel creates a new copy of that process for you and starts running it immediately。

Who not sleep。Yeah， I didn't cover weight too specifically， try to remember it。

 but it's not that big sleep is not part of sleep is not necessary for this。

 this is just for illustrative purposes， yeah。Yeah。Yeah， that's all you do。

 I could put S here or print， yeah of。Yeah。Well， so if the question is just。Have the parent， I mean。

 you could， you could run exec and like Exec Echo or something。

But a simple way to do it is to just fork and not exec because remember when you fork。

 you duplicate the process except for the return value and so you can do different things so the parent process will run this code。

 the child process will run this code， even though it's the same program。

They run different code and why do they run different code？Well， there's no。Well。

 there is filelo here standard out， but why do they run different code， if I call fork here。

 why is it that one process runs this code and another process runs this code。

 even though it's the same program。They're not the same process。

 but they're running the same exact code。それかで。There's well， they have different PIDs， true， but what？

You mean this PID， Yeah， so the return value of fork。It's different。So the processes are identical。

 same running program， same position in the program， same open files。But the only difference is。

The return value of fork is different depending on which process you're in。

 and so even though we have the same program。As you know。

 if you have if statements in your program and you take different input and the if statements test those。

 your program will execute different lines of code。

 you'll have a different trace through the program。So same thing here。

The kernel will give a different return value to fork， and so even though it's the same program。

 they can run different lines code。都解。No， no， it has the same position。

 the same program counter guess fork， so when Fork returns， you'll be at the next line of code。

AndIn the program， but the return value will be different。

So when the code to set PID to copy the return value of fork into return value happens that。

Even though the program is the same， now its data is different。

 and so if your program is the same but you have different data。

Then the program can take different paths through conditions。のい。No， no。

 you can just pick one and if get you don't get the exact path stuff or environment wrong。

 that's okay， just know that exec does not create a process， it just replaces， you know。

 it swaps out the brains of the process。All right。So。

This is just saying how do I write a program that replaces the current processes running program program with a different program。

 what command does that？Exact， that's exact okay。So this is where it gets a little tricky。

 we talk about this over the last week， write a program that opens a pipe and reads to and writes from it。

That same pipe。So I didn't have this exact。Code in class。

But you can just create a pipe and you have two file descriptors and you can just read to it and write and write from it so it'll look。

Almost exactly like。嗯。This pipe program here except no fork so if you run pipe without fork。

 you still have a pipe you can read to it and write from it just like you can read to and write from any files so in the same way here I've got writing to one end。

And reading from the other。I can do that in a single program without calling Fork this is the version where you for a process and do it between two processes。

Okay， write a program that redirects the standard out of its own process to a file called outputput that text。

 I didn't show this exact code， but what system calls would be involved in doing this so I have was that？

So who says fork？So any new processes， I'm not asking to create any new processes， so no fork。

 all right， exec， do we need exec here？No change in what program is running， then I heard do。

 who thinks dope Yeah so what does dope do？が。Well redirects any file descriptor overwrite a file descriptor with another file descriptor so if you want to redirect the standard out you can use dupe2 and so you can open。

 you can literally call open on output dot thatll give you a file descriptor and then you call Dupe2 to overwrite standard out with that file descriptor so the same thing we do with the pipe except instead of redirecting to the pipe by using dope you redirect to the open file descriptor so kind of the shows pseudocode real quick。

That would look something like。Open output that text and I know this is just pseudocode。

 this is not the full thing now we've got a file descriptor。

And there's nothing stopping because it's a file， everything is a file here in UniX。

 I can use Dupe 2 to take this file descriptor and overwrite my whatever it was， my standard out one。

And done and then any， you know， I didn't ask to do this in the assignment， but any printing。

We'll end up going to put that text。That's how like Bash does redirection。

So same principle is piping， but a simpler context for it。All right。

 so I think I'm a minute over Que any last questions？So I know that was like really fast。

 but hopefully you can look at the。Recording of this and look at all the code snippets I gave。

 look at all the sections in the text then。See you next Tuesday。



![](img/6cc703f4520c87175a25a1fbec099ff0_17.png)