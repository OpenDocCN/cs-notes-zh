# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p03 P3 Using the command-line： Navigation (COP-3402 Fall 2024) -BV1v6vdBKEHB_p3-

Welcome back to System Software。

![](img/540cfeca98b08ac39d48d199b55e4988_1.png)

So today we're going to go over using the command line and navigating the file system。

 modifying the file system。

![](img/540cfeca98b08ac39d48d199b55e4988_3.png)

Last time we went over the file system itself， the theory behind it。

And today we're actually going to use this knowledge in order to orient ourselves。

 navigate the file system。And modify it。Before I do that， let me go over the homework from。Last time。

So last time the homework was to take a list of paths。And reconstruct。

The file tree from this list of paths。And remember that there were two kinds of paths。

 two kinds of ways to specify paths on the file system， absolute and relative。

Absolute pads are paths that start with a forward slash。 that is they start with the root directory。

Relative paths in order to know where on the file tree this file is referring to。

 we need to know the working directory and every process has a working directory as managed by。

The operating system kernel。And when we're in the shell， as we'll see today。

 the shell will maintain the working directory and you'll be able to refer to files。

Using a relative path from that working directory。Okay， so let me go through each of these。

Paaths and construct the full file tree from it。Let let's take the first one。

Our working directory is home。But this is an absolute path。

 so the working directory isn't taken into account for this path because we already have an absolute path。

 we already know exactly where on the file tree this file lives。So starting from the root， every。

File system has。A root folder denoted by forward slash。

And this absolute path starts from root and then brings us to the home。File。As we'll see。

 this home file is a directory。And similarly， for the next line， slash dev。

 this is also an absolute path， so even though we're in the route as a working directory。嗯。

That's not taken into account when trying to determine where on the file tree slash Devs。

Slash tab is also an absolute path。 it starts with a forward slash。And it therefore。

 de is underneath。The redirecty。For Bo， the same applies。No matter what the working directory is。

 because we have an absolute path， we know。百部。Is a child of root。

So this working directory could be anything if we have an absolute path。嗯。This working directory。

 we don't need to take it into account in order to determine what directory the absolute path is referring to or what file it's referring to。

Okay， now we get to relative paths。So here， the working directory does matter。

Here we're in the working directory。Of root。So I'll use this orange dot to denote the current working directory。

So our current working directory is also root。Then relative paths are effectively like absolute paths。

呃。One way to think of it is that we append。The prepen the working directory to the path。

So we get slash and then whatever the relative path is， user。

And so this user file is also a child of root。And again， at this point。

 I don't know whether it's a folder or not。But it is， we know that it's a file。Okay。

 so now we have a different relative path here。Path， the working directory here is home。

So I'll show that with by moving this dot。To denote the。Working directory to the home directory。

So if my relative path is just Paul， then it's relative to the current working director。

 you can think of this as。Concatenating slash homelash with the folder or file。

So this poll file is a child of。Home。Here's where we get to see the use of dot dot folders。

Now my working director here is dev， so let me move。The working directory dot to be dev。

And so remember that each folder or each folder in。The Uni world。Has two special folders。

 a dot folder， which refers to itself and a dot dot folder。The dot dot folder。I's a hard link to。

The containing folders parent， the containing directorys parent。

 so dev's dot dot directory is a hard link to its parent。Okay， so we're in the dev working directory。

Let's follow this relative directories sequence of paths to figure out where。This path is referring。

Okay， so we started in the working directory slash devev。Then we follow the dot dot directory。

 the dot dot directory is a hard link to the root。The next element of this path is slash home。

 so that brings us to。The home directory， the child of root。The next component of this path is Paul。

 so that brings us to the poll directory。So this doesn't tell us there's any new files。

 this is actually the same。File as。The previous。Entry where we had home as a working directory slash home as the working directory and Paul as the relative path。

This line here where we've got slash Dev as the working directory。And dot dot/ho sPa。

 these are actually referring to the same file。Because we've。嗯。

Use dot dot to move to the root directory and then refer to slash home slash poll。

So there's one more component to this path here。/lash SRC。So this slash HRRC。

Is a child of slash home slash poll， so to go over this one more time when we're in。Deev。

 we follow dot dot to go to our root。from Ro， the next component is home。

The next component after home is Paul， and then source。Okay， let me do the next entry。

So here the working directory is slash user。And the relative path is been。走边。Again。

 taking slash user and concatenating it with bin， we get slash user or slash bin。

Our working directory is user。And so the relative path refers to a file that's immediately a child of user。

Let's go to our next working directory， our next working directory is slash。Home。Slash poll。

 so here's our working directory。And here。Our relative path is dot slash bin。

So remember that each folder has a dot folder and a slash folder。

The dot folder refers to the directory itself。And do dot refers to the parent。So in this case。

 dot just refers to Paul itself。And then following the slash， the child is bid。So in this case。

If our working directory is s home slashPa。A relative path of dot slash bin， and just bin。

Those would refer to the same file。Why are these two bins different。

 these two bins are different because they have different working directories。

So this bin is the child of dot slash because that's the slash user because that's the working directory you're in。

And this dot slash bin is a child of slash home/lash Paul。

Because the working directories are different。Okay， and so to finish this up。

Keeping the work directory slash home/lash Paul。Where does this home file live？Well。

 it's not this one because our working directory is slash home slash Paul。

 so our working directory is not this， our directory is not this home。

Our working director is slash homem/lashPa。So。The home here is actually a child of Paul。Okay。

 so let's take this list。More complicated one。Referring to another Paul file。

 So let's see whether or not it's the same as this。

Our working directory is also something a little more complicated at slash dev。Dat do。Slash home。

Slash Paul and then slash home， this other home directory。

So our working directory is this home directory。So if we have Paul relative to this home directory。

 we have。A different file or directory here。Okay， so that's the。Solution to the last homework。Okay。

 so let's take， let's do the。Presentation from today。

Navigating the file system from the command line。So take a look at the syllabus for guides on。

Using SSH on your particular operating system。And so I'll assume you're able to log in to use this。

 let me know if you have any issues asked on Ed discussions or come to office hours。

 but I'll assume that you're able to get in to use this。And so you can get it to Eust like this。

 SSshH， your Nd@ustace。eecs。ucf。edu。Okay， so you should see something like。This， when you log in。

You'll see a welcome message。And a prompt that has your N I D at some。Hot name。

So one common shortcut that I use frequently is control L， control L clears your screen。

So if I've typed a lot of stuff。I can tell you control L， you don't have to type out。

 you can also type out the clear command， but control L will also do that for you。Okay。

 so in order to run commands， we put a name like。PwD。And just hit enter， hit the enter key。

So there's two things that I always do when I'm in a file tree just to orient myself。

I use the PWD command print working directory。And Ls for list。

So these two commands will help you orient yourself。In the file tree。

 because PWD will give you an absolute path。To your current working directory。

So that any relative paths you use would be you'll know what it's relative to。

 you'll know that it's relative to the to this current working directory and LS just lists。

All of the files that are in your current folder， all the children of the current working directory。

Now commands also take arguments， I could and these arguments are command specific。

 so LS will take a path to another directory that you'd like to list。So I could， for instance。

 use an absolute path to the user include directory， which includes C header files， system wide。

 C header files。And I just typed LS space。And then the name of a path。

And that will pass an argument to LS to change its behavior。Typing that。

 you'll see I'll get this long list of。Dot header files。If I made a mistake in typing。

The path that will give me an error telling you that there's no file at that path。Okay。

 so we've seen where am I with PWD， what's here with LS？

And let's look at how we can change the working directory。

So let's change our working directory to this user include folder。

I noticed that on this shell configuration。The prompt will actually include。

The name of the path that of our working directory here for us， which kind of helps orient ourselves。

 you can also see that with PWD。The Tilde path is just a shortcut for your home folder。

So if I change directory to Tilde。That will put me in the。

Administrator defined home folderer for you， each user will have its own its own home folder or their own home folder。

Okay， so let's use CD to go to the include directory。I'll clear the screen。See where I am。

 list what folders files are here。So this， this is an absolute path， this path I went to。

Is an absolute path。I can also to use relative paths so for instance。

 the dot dot folder is the parent folder， so what folder what directory will I be in when I change the working directory to the parent of the current folder。

 well I'll be in slash user so we can confirm that with print working directory。

Now I'm in the user directory。I can also use other types of relative paths like。嗯。

To get into this subdirecty。 So to go back into this include directory。

 I can just CD the include without typing out the whole absolute path because。

The path that we're going to change directory to is the working directory here。嗯。

Concatenated with whatever relative path I pass on the command line here。

So one kind of quick question is what if I had？Change directory to so here I'm。

In slash user slash include， what if I change directory to dot dot slash include。

 what directory will I be in？Well， I'll be in the same directory。

Because dot dot will take me to the parent， which is slash user。

And include will take me to the include path， which is the same path that I'm currently in。Okay。

 so let's see one of the some useful tricks for making navigating the file system much。

 much faster than typing out everything。The first and probably most important and useful trick is T completion。

 this is a feature of bash and other shells。That will automatically type for you like autocomplete。

It is autocomplete， actually， think it predates autocomplete on phones。

 it will automatically fill out paths for you。And this satisfies a couple of the programmer virtues that we talked about in the first class。

 one being impatience。So don't spend time having to type out each path when you can just use tab completion or auto completion to fill out paths for you。

And also laziness。Because instead of having to try to remember the whole file tree。

 instead of having to type LS all the time。Tab completion will actually also list out。

What files are there available for you on the command？All right。

 so let's take a look at a couple of examples。So here we're in slash user s includelude。

If I type LS GN UM and I don't touch anything else， I don't hit En。If I hit tabab。

The T completion system is going to write the rest of the file name for it。

So I can appear to type really fast with tab completion。

 but really I'm just hitting a single key tab。In order to fill out the whole name of the headerophile Gnu make。

h。Now， that works great if there is only one file that starts with GNU M。

But what if there are multiple files？When I hit tabab， no completion happens。

Hitting tab a second time will list out all of the files that have the GNU prefix for me。

So I can just keep hitting tab whenever I'm trying to navigate or look at files in my file system。

And the TA completion system will explore for me， help me interactively explore what files。

Are available to me。And then once I continue typing。So here I put the hyphen in。

 And once we have an unambiguous prefix prefix that can only go to one file， hitting tab again。

Will give us the unique file page。So to make things fast for you。

 make it a habit to hit tab because not only will it help type for you。

 it'll help you confirm the existence of a file， it'll make sure if you say have a typo。

Hitting Ted and getting nothing。We'll give you a signal that that file doesn't exist。

More importantly， instead of typing out paths yourself， used have completion。

To not only type for you， but also confirm that that path is there。

 that that element of the path is there。And by hitting tab multiple times。

It will list out for you all the possibilities so you can interactively。Explore this file trip。Okay。

 there are also some。To make things fast， you can also。Addit the commands more quickly。

 And here's just a little cheat sheet for。Eiting commands。

 C A and control E will go to the beginning and end of the line。

 you can also use home and end on your keyboard most likely in your terminal。

Backspace deletes characters， alt backspace will delete entire words for you。

So you don't necessarily have to remember all these right now。嗯。

But you can kind of learn these as you go along。Similarly for deleting characters and moving around between characters。

You can use C D to delete a character in front of you。You can use control B for back。

 control F or forward。And you can use， just like you can use alt delete to delete a whole word behind you。

 you can use alt D to delete a word in front of it。There are also shortcuts for cutting and pasting。

 and I'll just let you explore these on your own time。Okay， so another really important tip。

For the command line is being able to rerun commands you've written already。

 So if you spend a lot of time。Saing typing out。えや。GCC command， some long GCC command。

Instead of having to rewrite that。Or remember what the entire command was in patience and laziness。

 You can use the。History in order to。Repeat prior commands that you've used before。

 so here you can use control P or the up arrow。To immediately type out the previous command that you've written。

And you can cycle through all the previous commands you've had by hitting the up arrow or control P for previous。

If you want to go back down to later commands， hit the downarrower or control and for the next command。

And in fact， the history command。We'll print it out。

The entire known history of commands that you've written in the past up to some threshold limit。

So this is really useful for not having to。Type out some complicated command that you've already figured out or also going back and inspecting what you did on the command line。

So with T completion， the command history will help make running and rerunning and say recompiling and testing code much。

 much， much faster on the command line。Another little trick that I'll let you explore on your own。

 you don't necessarily have to remember this is you can search for previous commands with control R。

So you type R。And start typing text， and it'll search。Your prior command history4。

Prior commands that you've written。One little trip that works along with command histories is。

You can kind of sort of save a command by commenting it out theh。Symbol is the comment in Bsh。

 and so if I find some previous command， I can use home or A to go to the beginning of the line control A。

And so to hash， and when I hit enter， this command won't be run。

But it will become the most recent command。So if I go back and delete that hash symbol。

 I can run GCC， so here I made an error， I can go back， fix the command。

And rerun this modified version of a previous command。Okay。

 so those two tricks or there's several tricks here。

 but the two main tricks to remember here are T completion to make typing paths really fast and。

The history to make repeating previous commands really fast。

So it should also note that T completion is not just for。Fileles， it's also four。

Commands and arguments to commands。So for instance， for the LS command here， if I type s slash。

 which is the convention for arguments and hit tab。

 it will tell me all the other options that are available for the LS command。If I say type C here。

And use T completion， it will tell me all of the programs that are available or commands that are available to run。

あ。With let's start， let's see。Okay， let's look at a few more。嗯。Commands here。

 so cat also short for concatenate。Willll write files to the terminal force or write files to output for us。

That's the cap command。More is like cat， but。Mo is light cat。

But if I have a particularly particularly long。File， like let's say， I want to print out standardIo。

h。It will only show one page full of text at a time so I can hit space。To go down an entire page。

 so you can see it maintains a percentage of the file that I've seen so far or enter to build one line at a time。

If I want to stop early， I can use Q。One problem with more is that it only goes in one direction once you've seen the top of the file。

 you can't go back and revisit the file Oh， actually， and this command has been updated。

 so historically you actually can use Page up to for you prior commands， I think。

Before more was modified， there was a new version of more called less， the joke is less is more。

 and with less you can do more than just navigate the file， navigate up and down。You can can search。

For files you can I think you can write write stuff out so anyway I use less more often it's a little more has a little more complicated interface than more。

 but if you find yourself stuck in the less program use Q or escape Q to。Get out of the less command。

Okay， so those are examples of the。Commands keyboard shortcuts for navigating。The less。Command。

So let's look at something that we're going to use for homework， so for homework。

I've given you a file tree here in this tarR file， tar file is just like a zip file， it's a package。

And you can download it from the command line with the W get command W get。

 you give it a URL and it'll download the file at that command can do other things like Sc websites as well。

 download multiple follow links， but here we're just going to use it to download a single file。

 this Hw3。tR file。So let's run this command here and you'll see that it'll save the。HW3。 tar54。

 we can use LS to confirm that it's here。Even better。

 we can use LS and then T completion to help us put the name of the file。To unpack this file。

 you can use the tarAR command。So I've explained what these arguments are， but for our purposes。

 you can just remember or copy this tarA command here。



![](img/540cfeca98b08ac39d48d199b55e4988_5.png)

And tar has unpacked all of the。Directories and folders and sorry directories and files。



![](img/540cfeca98b08ac39d48d199b55e4988_7.png)

That were packaged in this HW3。 tar file。Okay， so this is what you'll start with in order to modify the。

Modify the file system for homework 3。So for homework three。

 your task will be to take the existing tree here。So if we look at the。Miss the command here。

 we're supposed to download the file on Torret and then change directory into homework 3。

So here we are in homework three。If you type tree and the current directory， you should see。

This file tree note that the order of the files are not maintained。In a directory。

 they're going to be whatever order they happen to be entered in。

 so the order of like just like a tree structure， the order， the children are ordered unordered。

In a typical tray， the order of these。Fles doesn't matter。

 but the tree structure is what should be the same。 So you should see that F S has E X T 2。

As a child in the X T2 has ACL。 C as a child。 So you should see something similar。Modulular。

 the order of。Children in a directory tree。And the homework is to write a sequence of commands。

 dash commands that will turn the given tree into the new tree written here。Okay。

 so let's first go over the commands that we can use too。Modify a file tree。

So let' let's make an example folder here。Okay， so touch will create a regular file。

So I'm going to touch rec file。And now when I type Ls， I have this new file rank file here。

RM for remove will remove a regular file。You can see our file is gone。Okay， so let's make。

And a new file here， right file2。Move when move within the same。Direectctory is effectively renamed。

So I'm going to the move command takes two arguments first is。

A file or path to a file that you want to move from。

 and the second is the new path or new file name of the。Of the of the file。

 So when I type move rankg file2 to rank file new name。I should see when I type LS。

 I should see Re file new name in this directory。Copy has a similar interface。So if I want to。

 but instead of moving it， it'll make a new。File that has the same contents as the old file。

So here now I have two files。MKDer， or make directory will make a directory for us。

So let's make a directory called subder。嗯。My terminal will use， you know because I have color coding。

 it will actually color code the types of files to help identify what they are。

And we can move not only to change file names。Theres red Cloud copied。 We can also move to new paths。

 So if the second argument is a directory。Instead of renaming the file。

 it will move that entry from whatever directory we're currently in to。The given directories。Enries。

So here we can see that rank file copied is no longer in this directory。But if we use tree。Or LS。

 the subdirecty， we can see that reg file copied is now in the subdirecty。

You can also use if you put not just a directory， but you put a file name。Then it will not only move。

Reg file name， Regg file new name to subder， but it'll also give it a new name in subders director entries。

 So you can see that now。RG file new name has become new file name under Subder。

And it indeed is under subdiears directory entries。We can remove an empty directory with RM Deer。

So let's try to remove subder。But because the directory is not empty。

 the subder command or the remove to your command is not going to remove it。

So how can we actually remove？The contents of a non empty directory， well。

 one thing we can do is we can use the RM command。To remove。Whatever files are in here first。

And now that we've got an empty directory。We can use。So how could you write an algorithm to do this。

 little little something to think about。additional options or commands to the RM to remove non empty directories。

 I'll let you take a look at these themselves because they can easily be used to blow away your whole file system。

Okay， so just to okay， so let me go over what the homework is first。

So and an example of the homework， so starting from your home directory。

So you can type C tillil shortcut is it just type CD， which will take you to your home directory。

You'll download。 So let me show downloading on tarring this again。 I've already downloaded it， so。

The WG command will not overwrite what you downloaded it， it'll just make a new file， download it it。

 download it， Tarre it， untarre it。And then enter the file tree。So to go back to home， use CD。

If you find that you've made a mistake in your homework three folder and you'd like to try again。

 you can move。The folder out of the way， into some。New folder， we can also move folders。

 And so now I don't have a homework3 directory anymore。 So if I go and Untar。This file that I。

Already downloaded。I'll get a new homework read。Directory。

So do that if just move the old version out of the way if you find that you've made a mistake。

So now'll go into the homework free directory。Here's what the original tree looks like。

And now our goal is to turn the original tree into this tree using。

Really only the commands that you only need the commands that you see。嗯。

You should only need these commands too。Turn。This directory the per previous directory tree into the new one。

So this is a little bit of a puzzle solvinging exercise because you've got to look at compare these two trees and see what's different Now notice here that FS is in a different place。

The order of directories in a or the order of children in a directory are irrelevant。

 the operating system doesn't enforce any particular ordering。

 doesn't remember any particular ordering。So this is just like a general tree that you might have learned in CS1 or CS2。

 they're order insitive， what the file system does maintain is the structure。

The parent childil relationships between the files and the tree。

 and so that you just want to make sure that even if you're in a different order here。

 that your file tree structure is the same as this one。Okay， so let's take one example here。

 Let's take F， S， E X， T2。ACclL。c this set of files here。So in the new tree。

 the structure is similar whereas FS and then， a child that has ACcl。c。

But the name of his child is different， the name is EXT4 instead of EXT2。

So there's several ways you could solve this， so one way is to rename or move EXT4。

So you could enter the FS directory and rename it here。

But you don't actually have to do that because these commands for file operations will take paths instead of just a single file name so we could write。

The path to EX T2。Using T completion to help us。And we could give this。Dictory， EXT2， a new name。

With the second argument and give it the name EXT4。So now when I look at my tree。

The FS directory now contains。A file called E X T 4， instead of。EXT2。So take your time doing this。

 look what's different between the trees。Then look at the commands that are available to rename。Copy。

 delete， make new regular files， or make new directories。Or remove directories。And yeah。

 use the tree command to confirm。Whether your new tree matches。The one given in the homework。

And remember， again， that the order。Of entries for a particular subdirecty。

Doesn't matter for the file system， so if you see FS before。呃。HID here， for instance。

Then it's still the same tree， just make sure that the tree structure that is the parent child relationships。

Are the same。As what's given in no work here。Okay， so that concludes。

The lecture for or actually let me。那にあ。Review。I added a review section here for the for what we learned today。

 what's its kind of takeaway going forward in this class I showed a lot of material。

 but there's a small number of things that you should absolutely remember and look at this review section to remember those so the first is orienting yourself so use PWD and LS to figure out where you are and what's here。

Use change directory to move around the file system。So to change your working directory。

So here's examples of going to a directory， going to a parent。

 you can go to the home folder with change directory Tilda。You can use CD hyphen。

 so this is a hyphen。This is a Tilda。This will take you back to。Whatever director you in previously。

 and you can use the bash history to。Go to the previous command and quickly swap between two directories。

CD without anything will also take you home。Tamp completion is one of the most useful things to make typing fast so I can very quickly。

Type out the path to user include。Very， very quickly。By heading tab。Before I complete。And it typing。

One element of a path， so I can very quickly。Just with one， two， three， four， five， six， seven。

 eight。A呃。Pressses on the keyboard I can change directlyy to。でか。The history。

So being able to hit the up arrow or control P。To navigate or to inspect prior commands that you've run。

And here's just a list of modifying the file trade。All right。

 so that's all should be all you need for completing the homework and I'll see you next time。



![](img/540cfeca98b08ac39d48d199b55e4988_9.png)