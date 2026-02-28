# 《计算机科学教育中遗漏的一学期｜The Missing Semester of Your CS Education 2020》中英字幕 - P1：-01-.Lecture 1_ Course Overview + The Shell (2020).zh_en - GPT中英字幕课程资源 - BV1Y3yhBHEip

All right， everyone。Thanks for coming in。 This is the missing semester of your C S education。

 At least that's what we chose to call the class。 If you're not here for this class。

 then you're in the wrong room， we will be here for about an hour just to set your expectations。

And I want to talk to you a little bit first about why we're doing this class。

 So this class stems out of an observation that Anish and Jose and I have made while T Aing various classes at MI T。

 which is that。Basically， all of us， computer scientists。

 we know that computers are great at doing these repetitive tasks and automating things。

 but we often fail to realize that there are lots of tools that can make our own development processes better。

We can be a lot more efficient about how we use our computers。

 because we can use the computer as a tool for ourselves， not just for building websites or software。

 those sorts of things。And this class is an attempt to address this It' an attempt to show you some of the tools that you can use to great effect in your day to day。

 in your research and in your studies， and it's going to be a class where we want you to teach you both how to make the most of the tools that you already know。

 but also hopefully teach you about some tools that you don't know from before。

 and how to combine those tools to produce more powerful things than you think you might be able to do with what you know today。

The class is going to be structured as a series of 111 hour lectures and each one is going to cover a particular topic。

 you can see the website which is also listed there for the list of lecture topics and what date will do each one they will mostly be independent and so you can sort of show up for the ones that you're interested in。

 but we will sort of assume that you've been following along so that as we get to later lectures。

 I'm not going to be teaching you bash all over again for example。

We we are also going to post both the lecture notes and recordings of the lectures online exactly when we do that。

 we haven't established yet， but it will be after the lectures obviously the videos have to be posted after the class is gonna to be run by me John and An niche sitting over there and Jose who is not currently here but we'll be holding tomorrow's lecture and keep in mind that we're trying to cover a lot of ground over the course of just 111 hour lectures。

 And so we will be moving relatively rapidly but please do stop if there's anything where you feel like you're not following along if you feel like there's something you wish we would spend more time on just let us know。

 please interrupt us with questions and also after each lecture。

 we're going to hold office hours on the9 floor of building 32 the data center。

 the computer science building So if you show up up in the ninth floor lounge there and the Gates Tower then you can come and try some of the exercises we get。

For each lecture or just ask us other questions about。

Things we've talked about in lecture or other things about using your computer efficiently。嗯。

Due to the limited time that we have available， we're not going to be able to cover all tools in full detail。

 And so what we'll try to do is highlight interesting tools and interesting ways to use them。

 We won't necessarily dig into the deep details about how all of it works or more elaborate use cases。

 But if you have questions about them， please come ask us about that too。

 Many of these tools are tools that we have used for years。

 and we might be able to point you to additional interesting things you can do with them。

So take advantage of the fact that we're here。This class is going to。

 I don't want to say ramp up quickly， but what's going to happen over the course of this particular lecture is that we'll cover many of the basics that we assume that you will know for the rest of the semester。

 things like how to use your shell in your terminal and I'll explain what those are to those of you are not familiar with them and then we'll pretty quickly ramp up into more advanced tools and how to use them。

 you can already see from the lecture notes the kind of topics that we're going to be covering。

And so that brings us to today's lecture in which we are going to cover the shell and the shell is going to be one of the primary ways that you interact with your computer once you want to do more things than what the sort of visual interfaces you might be used to allow you to do the visual interfaces are sort of limited in what they allow you to do because you can only do the things that there are buttons for。

 sliders for input fields for。Often， these textual tools are built to be both composable with one another。

 but also to have tons of different ways to combine them or ways to program and automate them。

 And that is why in this class， we will be focusing on these command line or text based tools。

And the shell is the place that you will do most of this work。

 So for those of you who are not familiar with the shell。

 most platforms provide some kind of shell on Windows， this is often powerhell。

 but there are also other shells available on Windows， on Linux， you will find tons of terminals。

 these are windows that allow you to display shells。

 and youll also find many different types of shells。

 the most common of which is bash or the born again shell。 because it's such a common shell。

 it is the one were primarily going to be covering in these lectures。 If you're on MacOS。

 you will probably also have bash， maybe an older version of it， if you open the terminal app。

 And if you want to follow along on any of these platforms， feel free。

 But keep in mind that most of this is gonna to be sort of Linux centric in terms of how we teach it。

 even though most of these tools work on all the platforms。

If you want to install a terminal in a shell and you don't know how to do it。

 well we're happy to show you at office hours， or it's usually very easy to just Google like your platform plus like terminal and you will get one。

嗯。Now， when you open a terminal， you get something that looks a little bit like this。

 So it will usually have just a single line at the top。 And this is what's known as the shell prompt。

 You can see that my shell prompt looks like this。 It has my username。

 the name of the machine that I'm on the current path I'm on。

 And we will talk about paths a little bit later。 And then it's really just sort of blinking there asking me for input。

 And this is the shell prompt where you tell the shell what you want it to do。

And you can customize this prompt a lot and when you open it on your machine。

 it might not look exactly like this， it might look something like this if you've configured it a little。

 or it might look all sorts of different ways。We won't go too much into customizing your shell in this particular lecture。

 we'll do that later here we're just going to talk about how do you use this shell to do useful things。

嗯。And this is sort the main textual interface you have to your computers through the shell on the shell prompt。

 you get to write commands and commands can be relatively straightforward things。 Usually。

 it'll be something like executing programs with arguments。 What does that look like。 Well。

 one program we can execute is the date program。 We just type date to presenter。

 And then it will show you， unsurprisingly， the date and time。😊。

You can also execute a program with arguments。 This is one way to modify the behavior of the program。

 So， for example， there's a program called Echo。 and echocho just prints out the arguments that you give it。

 And arguments are just white space separated things that follow the program name。 So we can say。

 hello。 And then it will print To back。 perhaps not terribly surprising。

 But this is the very basics of arguments。 One thing that you'll notice is that I said that arguments are separated by white space。

 And you might wonder， well， what if I want an argument that's multiple words。

 You can also code things。 So you can do things like echo。



![](img/901105306c5e0abe3c9a541fd8f26060_1.png)

![](img/901105306c5e0abe3c9a541fd8f26060_2.png)

Hello space world。 And now the E program receives one argument that contains the string Ho world with a space。



![](img/901105306c5e0abe3c9a541fd8f26060_4.png)

You can also use single quotes for this and the difference between single quotes and double quotes will get back to and when we talk about batchsh scripting。

 you can also just escape single characters。 So， for example， hello world。

 this will also work just fine。

![](img/901105306c5e0abe3c9a541fd8f26060_6.png)

![](img/901105306c5e0abe3c9a541fd8f26060_7.png)

![](img/901105306c5e0abe3c9a541fd8f26060_8.png)

All of these rules about how you escape and how you parse and quote various arguments and variables we'll cover a little bit later。

 Hopefully you won't run into too many oddities about this。

 Just keep in mind at least that spaces separate arguments。

 So if you want to do something like make a directory called my photos。

 you can just type like make directory my photos。 it will create two directories。

 one called my and one called photos。 and that is probably not what you want。



![](img/901105306c5e0abe3c9a541fd8f26060_10.png)

m now。One thing you might ask is， how does the shell know what these programs are when I type date or when I type Echo。



![](img/901105306c5e0abe3c9a541fd8f26060_12.png)

How does it know what these programs are supposed to do？

And the answer to this is program your computer has a bunch of built in programs that comes with the machine。

 just like your machine might chip with like the terminal app or it might chip with like Windows Explorer or it might chip with some kind of browser。

 it also ships with a bunch of terminal centric applications。

 and these are stored on your file system。

![](img/901105306c5e0abe3c9a541fd8f26060_14.png)

![](img/901105306c5e0abe3c9a541fd8f26060_15.png)

And your shell has a way to determine where a program is located。

 basically has a way to search for programs。 It does this through something called an invariant environment variable。

 an environment variable is a variable like you might be used to for programming languages。

 It turns out that the shell and the B again shell in particular is really a programming language。

 This prompt that you're given here is not just able to run a program with arguments。

 you can also do things like while loops for loops， conditionals。

 All of these you can define functions， you can have variables and all of these things you can do in the shell。

 Well cover a lot of that in the next lecture on shell scripting。For now， though。

 let's just look at this particular environment variable。

 Environment variables are things that are set whenever you start your shell。

 There are not things you have to set every time you run your shell。

 There are a bunch of these that are set things like， where is your home directory。

 What is your username。 And there's also one that's critical for this particular purpose。

 which is the path variable。 So if I echo out dollar path。

 This is going to show me all of the paths on my machine that the shell will search for programs。😊。



![](img/901105306c5e0abe3c9a541fd8f26060_17.png)

![](img/901105306c5e0abe3c9a541fd8f26060_18.png)

![](img/901105306c5e0abe3c9a541fd8f26060_19.png)

![](img/901105306c5e0abe3c9a541fd8f26060_20.png)

You'll notice that this is a list that is colon separated。 It might be kind of long and hard to read。

 but the essentials is that bash， whenever you type the name of a program is going to search through this list of paths on your machine。

 and it's going to look in each directory for a program or a file whose name matches the command you try to run。

So in my case， when I try to run data Echo， it's going to walk through these one at a time until it finds one that contains a program called data Echo。

 and then it's going to run it。If we want to know which one it actually runs。

 there's a command called witch， which let us do that。

 So I can type which Echo and will tell me that if I were to run a program called Echo。

 I would run this one。It's worth pausing here to talk about what paths are。

 So paths are a way to name the location of a file on your computer。On Linux and Oma OSOS。

 these paths are separated by slashes， forward slashes。

 so you'll see here that this is in the root directory。

 so the slash at the very beginning indicates that this is starting from the top of the file system。

Then look inside the directory called USR。Then look inside the directory bin and then look for the file called Echo。

On Windows， paths like this are usually separated by backslashes instead。

And where on Linux and MacOS， everything lives under the root namespace。

 So all paths start with a slash or all absolute paths。 on Windows。

 there is one root for every partition。 So you might have seen things like C colon back slash or D colon backslash。

 So Windows has separate sort of file system path hierarchies for each each drive that you have。

 whereasas on Linux and Mac OS， these are all mounted under one namespace。😊。

You'll notice that I said the word absolute path。 And you might not know what that means。

 So absolute paths are。Pas that fully determine the location of a file。 So in this case。

 this is saying this is talking only about a specific echo file。 and it's giving you the。

 the full path to that file。But there are also things known as relative paths。

 So a relative path is relative to where you currently are。

And so the way we find out where we currently are is you can type PWD for present working directory。

 present print working directory。So if I type PWD， it will print out the current path that I'm in。

So currently I'm in the home directory under the Ro and then John under that。

 and then Dev under that， etc。From here， I can then choose to change my current working directory。

 and all relative paths are relative to the current working directory。

 which is basically where you currently are。In this case， for example。

 I can do CD slash home C is change directory This is the way that I change what my current working directory is In this case I changed to home and I am now you'll see my shell prompt change to say that I am now in home It just gives me the name of the last segment of the path。

 but you can also configure your terminal to give you the full path whenever you're anywhere。

And now if I type PWD again， it will tell me I'm in slash home。

There are also a couple of special directories that exist， there is dot and dot dot。

Dot means the current directory。Dot dot means the parent directory。

 So this is a way that you can easily navigate around the system。 For example， here。

 if I type C D dot dot。It will tell me that I am now in slash。

 So I'm now in the root of the file system。 I was in slash home。 Now I'm in slash。And indeed。

 if I type PWD， it will do that right thing。And I can also then use relative paths to go down into the file system。

 right so I can do C dot slash home， and this is going to Cd into the home directory under the current directory。

Right， so this will bring me back to slash home。 If I now tried C D dot slash home again。

 it will say theres no such directory because there is no home directory under the current directory I'm on。

 which I changed by doing C D。Right？嗯。And I can sort of CDd all the way back to the place that I was。

Using relative paths。 And I can also do things like dot， dot， dot， dot， dot， dot。

To get back to somewhere deep in my fum， this happens to be all the way back to the root。

 So here there's a bin directory and under bin， there's an echo file。 and so then I can do world。

 and that runs the echo program under bin。So this is a way that you can construct paths to arbitrarily traverse your file system。

 Sometimes you want absolute paths and sometimes you want relative ones。

 usually you want to use whichever one is shorter。 but if you want to， for example。

 run a program or write a program that runs the program like E or date and you want it to be able to run be run from anywhere you either want to just give the name of the program like date E and let the shell use the path to figure out where it is or you want to give its absolute path because if you gave a relative path。

 then if I ran it in my home directory and you run it in some other directory。

 it might work for me but not for you。嗯。In general， when we run a program。

 it is going to be operating on the current working directory， at least by default。

 unless we give it any other arguments。 And this is really handy because it means that often we don't have to give full paths for things。

 We can just use the name of files in in the directory that we're currently in。

One thing that's really useful is to figure out what is in the current directory we're in so we already saw PWD which prints where you currently are。

 there's a command called LS which will show you it will list the files in the current directory So if I type LS here。

This is all the files in the current directory。And this is a handy way to just quickly navigate through the file system。

You'll see that if I sort of Cd dot dot and then do LS。

 it'll show me the files in that directory instead。But with L S， I can also give it L S dot dot。

 like I can give it a path。 and then it will L S that file instead of the one that I'm currently in or L S that directory。

嗯。And you can see this if I go all the way to the root as well， right， rootot has different files。

One handy trick you might not know about here is there are two other special things you can do。

 One is the Tilda character。 This character brings you to your home directory。

 So Tilda always expands to the home directory and you can do relative paths to it。

 So I can do Tilda slash dev slash Pdos classes missing semester。 And now I'm there。

 because Tilda expanded to slash home slash John。😊，There is also for C D， in particular。

 a really handy argument you can give， which is dash。 If you do C D dash， it will C。

 D to the directory you were previously in。So if I do CDD， I go back to root。If I do CDD again。

I go back to missing semester。 So this is a handy way。

 If you want to toggle between two different directories。嗯。In the case of L S or in the case of C D。

 there might be arguments that you don't know about， right Currently。

 we haven't really been doing anything except giving paths。

 But how do you even discover that you can give a path to L S in the first place。 Well。

 most programs take what are known as arguments like flags and options。

 These are things that usually start with a dash。 One of the handyies one of these is dash help。

 Most programs implement this， And if you run， for example， L S dash help， itll helpful print out。

A bunch of information about that command。 And you'll see here that its says the usage is L S。

 and you can give some number of options， and you can give some number of files。

 The way to read that usage line is。Triple dot means one， like 0 or one or more。

 and the square bracket means optional。 So in this case。

 there's an optional number of options and there's an optional number of files。

And you'll see that it says what the program does and also specifies a number of different types of flags and options you can give。

 usually we call things that are single dash and a single letter。

 a flag and anything that or anything that doesn't take a value of flag and anything that does take a value an option。

 So for example， dash A and dash all are both flags and dash C or dash color is an option。

One thing you'll see under here， if you scroll down far enough is the dash L。Flag， that's unhelpful。

 The dash L flag。The dash L flag uses a long listing format。

 not that that's particularly helpful in and of itself， but let's see what it actually does。

So if I do LS L。It still prints the files in the current directory。

 but it gives me a lot more information about those files。

And this is something you'll find yourself using quite a lot because the additional information it gives you is often quite handy。

嗯。Let's look at what some of that information is。So first of all。

 the D at the beginning of some of these entries indicate that something is a directory。

 so the underscore data entry here， for example， is a directory whereas 404。 HTML is not a directory。

 it's a file。The following letters after that indicate the permissions that are set for that file。

So this， like we saw earlier， I might not be able to open a given file or I might not be able to see the into a given directory。

 And this is all dictated by the permissions on that particular file or directory。

The way to read these is that the first group of three are the permissions that are set for the owner of the file。

 All of these files you'll see are owned by me。 The second group of three characters is for the permissions for the group that owns this file。

 In this case， all of these files are also owned by the John Group。

And a final group of three is a list of the permissions for everyone else。

 So anyone who's not a user owner or a group owner。

This directory is perhaps kind of boring because all of the things are owned by me。

 but if we do something like CD to slash and do LS L，You'll see that here。

 all of them are owned by root。We'll get back to what the root user is。

But here you'll see some of the permissions are a little bit more interesting。

 the groups of three are read， write， and execute。😊。

What these mean differs for files and for directories。 For files， it's pretty straightforward。

 If you have read permissions on a file， then you can read its contents。

 If you have write permissions on a file， then you can save the file。

 you can add more to it or you can replace it entirely。 And if you execute the X bit on a file。

 then you're allowed to execute that file。 So if we do LS dash A L in slash bin That's un awful。

 in user bin， you'll see that all of them have the execute bit set。

 even for people who are not the owner of the file。 And this is because the E program， for example。

 we want everyone on the computer to be able to execute。

 There's no reason to say only certain users can run echo that doesn't really make any make any sense。

For directories， though， these permissions are a little bit different。So read translates to。

 are you allowed to see which files are inside this directory。

 So think of read as list for a directory。 Are you allowed to list its contents。

Wite for a directory is whether you are allowed to rename， create。

 or remove files within that directory。So it's still kind of right。

 but notice that this means that if you have right permissions on a file。

 but you do not have right permissions on its directory， you cannot delete the file。

 You can empty it， but you cannot delete it because that would require writing to the directory itself。

And finally， execute on directories is something that trips people up a lot。

Execute on a directory is what's known as search。 And that's not terribly helpful。 a name。

 But what that means is， are you allowed to enter this directory。If you want to get to a file。

 if you want to open it or read it or write it， whatever you want to do。

 basically to C D into a directory， you must have the execute permission on all parent directories of that directory and the directory itself。

So， for example， for me to access a file inside slash user slash bin， such as user bin Echo。

 I must have executed on root。 I must have executed on user， and I must have executed on bin。

If I do not have all those execute bits， I will not be allowed to access that file。

Because I won't be able to enter the directories along the way。

There are a number of other bits that you might come across。

 like you might see S's or T's in these lists， you might see L's。

 those we could talk about in office hours， if you're curious。

 they will mostly not matter for anything you will do in this class。

 but they are handy to know about so if you're curious about them。

 look them up on your own or come ask us in office hours。

There are some other programs that are handy to know about。 Oh， sorry。

 There's one more thing I should mention。 If you just have a dash。

 it means you do not have that permission， right， So if it says， for example， R dash X。

 it means that you have read and execute， but you do not have right。

There are some other handy programs to know about at this point。

 One of them is move or the M V command。 So if I see back to missing semester here。

 M V lets me rename a file。 and rename here takes two paths。 It takes the old path and the new path。

 This is means that move， lets you both rename a file。 Like if you change the name of the file。

 but not the directory or it lets you move a file to complete different directory。

 It just you give the path to the current file and the path to where you want that file to be and that can change its location and its name。

So for example， I can move dot files。md to be food dotm unhelpfully， right， and similarly。

 I can move it back。😊，嗯。There's also the C command， the C or copy is very similar。

 It lets you copy a file。 C P also takes two arguments。

 It takes the path that you want to copy from and the path that you want to copy to。

 And these are full paths。 So I could use this， for example， to say。

 I want to copy dot file dot M to dot dot slash do M。Sure， food。t MD。And now， if I do Ls dot dot。

 you'll see that there's a food dot M D file in that directory。So the C P as well， take two paths。

 It does not have to be in the same directory。And similarly， there's the RM command。

 which lets you remove a file， and there too， you can give paths。 In this case。

 I'm removing dot dot slash food。You should be aware for removing， especially on Linux。

 removal is by default， not recursive， so you cannot remove a directory using RM。

You can pass the dash R flag， which lets you do a recursive remove and then give a path that you want to remove and it will remove everything below it。

There is also the RMDIR command， which lets you remove a directory。

 but it only lets you remove that directory if it is empty。

So the idea here is to sort of be a safety mechanism for you so you don't accidentally throw away a bunch of your files。

And the final little command that's Sandy to use is maked， which as you create a new directory。

 And this we talked about before， you don't want to do something like this because it will create two directories for you。

 one called my and one called photos。 If you actually want to create a directive like this。

 you would either escape the。😊，The space or quote the string。

If you ever want more information about how any command， basically on these platforms work。

 there's a really handy command for that as well。 There is the program called Man for manualual pages。

 This program takes as an argument the name of another program and gives you its manual page。 So。

 for example， we could do Man L S。And this shows us a manual page for L S。

 You'll notice that in the case of L S， it is fairly similar to what we got with L S dash help。

 but it's a little easier to navigate and a little easier to read。 Usually towards the bottom。

 you will also get examples， information about who wrote it。

 where you can find more information and that sort of stuff。 One thing that can be confusing。

 Sometimes at least until a recent version where they added this three at the bottom where it says Q to quit。

 They did not use to say this。 you press Q to quit this program。 It can be really hard to quit it。

 if you do not know that。handy keyboard shortcut here， by the way， is controll L。

 which lets you clear your terminal and go back to the top。



![](img/901105306c5e0abe3c9a541fd8f26060_22.png)

So so far， we've only talked about programs in isolation。

 but where much of the power of the shell really comes through is once you start combining different programs。



![](img/901105306c5e0abe3c9a541fd8f26060_24.png)

RightSo rather than just like running C， running LS， and et cetera。

 you might want to chain multiple programs together。

 you might want to interact with files and have files operate in between programs and the way we can do this is using this notion of streams that the shell gives us。

Every program by default has， I'm going to simplify a little and say two primary streams。

 It has an input stream and an output stream。By default， the input stream is your keyboard。

 Basically， the input stream is your terminal。 and whatever you type into your terminal is going to end up into the program。

And it has a default output stream， which is whenever the program prints something。

 it's going to print to that stream。 And by default， that is also your terminal。

 This is why when I type E hello， it gets printed back to my terminal。

 But the shell gives you a way to rewire these streams to change where the input and output of a program are pointed。

way the most straightforward way you do this is using the angle bracket signs。

So you can write something like this， or you can write something like this。

 The left angle bracket indicates rewire the input for this program to be the contents of this file。

And the end angle bracket means rewire the output of the preceding program。Into this file。

So let's look at an example of what that would look like if I do echocho hello。

 I can say I want that context content to be stored in a file called hello dot text。

 and because I gave this is a relative path right， this will construct a file in the current directory called hello dot text and at least in theory its contents should be the word hello。



![](img/901105306c5e0abe3c9a541fd8f26060_26.png)

So if I run this， notice that nothing got printed to my output。

The previous time when I ran Echo hello， it printed hello。

 Now that hello is gone into a file called Ho dot text。

 And I can verify this by using the program called cat。

 So cat prints the contents of a file so I can do cat hello dot text。 And there it shows me hello。😊。



![](img/901105306c5e0abe3c9a541fd8f26060_28.png)

But cat is also something that supports this kind of wiring。 so I can say cat。

 which by default just prints its input， just duplicates its input to its output。 I can say。

 I want you to take your input from Ho dot text。What will happen in this case is that the shell is going to open hello dot text。

 take its contents and set that to be the input of cat。

 And then cat is going to just print that to its output， which since I haven't rewired it。

 it's just going to be my terminal。 So this will just print hello to the output。



![](img/901105306c5e0abe3c9a541fd8f26060_30.png)

And I can use both of these at the same time。 So for example。

 if I want to copy a file and I don't want to use the CP command for some reason， I can do this。



![](img/901105306c5e0abe3c9a541fd8f26060_32.png)

![](img/901105306c5e0abe3c9a541fd8f26060_33.png)

And in this case， I'm telling the cat program nothing at all。 I'm just saying， do your normal thing。

 right， The cat program does not know anything about this redirection。

 but I'm telling the shell to use hello dot text as the input for cat and to write anything the cat prints to Ho2 dot text。



![](img/901105306c5e0abe3c9a541fd8f26060_35.png)

![](img/901105306c5e0abe3c9a541fd8f26060_36.png)

![](img/901105306c5e0abe3c9a541fd8f26060_37.png)

Again， this prints nothing to my terminal， but if I cat Ho to dot text。

 I get the output as I would have expected。

![](img/901105306c5e0abe3c9a541fd8f26060_39.png)

Which is a copy of the original file。

![](img/901105306c5e0abe3c9a541fd8f26060_41.png)

There is also a double end bracket， which is appendned instead of just overwrite。



![](img/901105306c5e0abe3c9a541fd8f26060_43.png)

![](img/901105306c5e0abe3c9a541fd8f26060_44.png)

So you'll notice that if I do catalo dot text to hello2 dot text again。

 and then I cat hello2 dot text， it still just contains hell low。

 even though it already contained a low。

![](img/901105306c5e0abe3c9a541fd8f26060_46.png)

![](img/901105306c5e0abe3c9a541fd8f26060_47.png)

If I switch that to instead be a double in bracket， it means aend。 and if I now count that file。

 it has hell load twice。These are pretty straightforward。

 they're usually just ways to interact with files， but where it gets really interesting is an additional operator the shell gives you called the pipepe character。

 so pipe is just a vertical bar and what pipe means is take the output of the program to the left and make it the input of the program to the right。

😊，Right。So what does this look like Well， let's take the example of LS slash or LS dash L slash。

 This prints a bunch of things。 Let's say that I only wanted the last line of this output。 Well。

 there's a command called tail and tail prints the last n lines of its input and I can do dash n1。

 So this is a flag called n you can also use dash dash lines if you want to use it as a longer option。

 but in this case this is saying just print the last line。😊。

And I can wire these together so I can say LS dash L slash， pipe， tail， dash n1。

And notice here that L S does not know about tail and T does not know about L。 S。

 They are different programs and have never been programmed to be compatible with one another。

 All they know how to do is read from input and write to output。

And then the pipe is what wires them together。And in this particular case。

 I'm saying I want the output of LS to be the input to tail and that I want the output of tail to just go to my terminal because I haven't rewired it。

 I could also rewire this to say I want the output to go to LS dot text。 And in this case。

 if I cut LS dot text， I would get the appropriate output。

And it turns out you can do some really neat things with this。

 We're going to cover this a lot more in the data wrangling lecture than will be in。

 I think four days or something on the kind of fancy stuff you can do when you start building more advanced pipelines。

One， to give you one example， we can do something like curl， D head。Silent， Google dot com。

So just to show you what that looks like， this gives me all the HTP headers for accessing Google。com。

And I can pipe that to。Gre does ignore case or just D I if I want。Content length。

So this is going to print the content length header。

 GrEP is a program that we'll talk about later that lets you search in an input stream for a given keyword。

We can pipe that through， say the cut command， which takes a delimiter。I set that to be space。

 and I want the second field， and this prints just the content length。

This is sort of a silly example， right， Like this just lets you extract the content length and bytes of Google dot com from the command line。

 It is not a very useful thing to do。 But you can see how by chain these together。

 you can achieve a bunch of really interesting text manipulation effects。

 And it turns out pipes are not just for textual data。

 You can do this for things like images as well。 You can have a program that manipulates a binary image on its input and write a binary image to its output。

 and you can change them together in this way。 And we'll talk about some of those kinds of examples later on too。

 You can even do this for video if you want。 You can stream。 This is， for example， a great way。

 if you have a chromromecast at home。 You can stream a video file like this。

 by having the last program in your pipe。 be a chromromecast send program。😊。

So you stream a video file into it， and it streams over HDP to your Chromecast。嗯。

We' we'll talk a lot more about this in the data wrangling lecture。

 but there's one more thing that I wanted to talk to you about about sort of how to use the terminal in a more interesting and perhaps more powerful way that you might be used to and this is perhaps even going to be interesting for the ones of you who feel like you're already comfortable with the terminal。

 But first we need to cover an important topic when it comes to Linux systems and MacOS is in particular。

 which is the notion of the root user。 The root user is sort of like the administrator user on Windows。

 and it has user ID0。 The root user is special because it is allowed to do whatever it wants on your system。



![](img/901105306c5e0abe3c9a541fd8f26060_49.png)

![](img/901105306c5e0abe3c9a541fd8f26060_50.png)

Even if a file is like not readable by anyone or if it's not writeriable by anyone。

 Root can still access that file。 Root is sort of a super user。 that gets to do whatever they want。

And most of the time you will not be operating as the super user。 You will not be root。

 You will be a user like John or whatever your name is。

 And that's gonna be the user you act with because if you were operating your computer as the root user at all times。

 if you ran the wrong program， it could just completely destroy your computer and you don't want that right But every now and again。

 you want to do something that requires that you are root。Usually for these cases。

 you will use a program called Su SUDO。Or do as Sue and Sue in this case， is super user。

 So this is a way to do the following thing as the super user。

Usually the way pseudo works is you write pseudo and then a command like you would normally on your terminal。

 and it will just run that command as if you were root as opposed to the user you actually are。

Where might you need something like this well？There is a special。

 there are many special file system on your computer， but in particular， there's one called sis FS。

 If use Cd to slash cis。😊，This is a whole new world。

 This file system is are not actually files on your computer instead these are various kernel parameters。

 so the kernel is like basically the core of your computer。

 This is a way for you to access various kernel parameters。



![](img/901105306c5e0abe3c9a541fd8f26060_52.png)

![](img/901105306c5e0abe3c9a541fd8f26060_53.png)

Through what looks like a file system。

![](img/901105306c5e0abe3c9a541fd8f26060_55.png)

You'll see here that if I CDd into class， for example。

 it has directories for a bunch of different types of devices that I can interact with or various cues I can access or all sorts of weird knobs internally。

And because they're exposed as files， it means that we can also use all the tools we've been using so far in order to manipulate them。

 One example of this is if you go into cis class backlight。

So this backlight directly lets you configure the backlight on your laptop if you have one。

 so I can seed into Intel backlight， This is an Intel laptop In here you'll see there's a file called brightrightness and I can cat the brightness。

 This is the current brightness of my screen。😊，But not only that。

 I can modify this too in order to change the brightness of my screen。

So you might think that I could do， let's see what the max brightness is here。 Okay。

 so it's currently set to the max brightness。You might imagine that I could do something like if I do echo。

 let's do half。Or something。 Echo 500 to brightness。If I do this， it says permission denied。

 I'm not allowed to modify brightness because in order to basically in order to change things on the kernel。

 you need to be the administrator。 And you might imagine that the way to solve this is to write pseudo Echo 500。

 but I still get a permission denied error。But why is that。It's because， as I mentioned before。

 these redirections of input and output is not something the programs know about。

When we piped L S into tail， Ta did not know about LS and L S did not know about tail。

 The pipe and the redirection was set up by the shell。 So in this case。

 what's happening is I'm telling my shell， run the program pseudo with the arguments's echocho in 500 and send its output to the file called brightrightness。

But the shell is what is opening the brightness file， it is not the pseudo program。😡，So in this case。

 the shell， which was running as me， tries to open the brightness file for writing。

 and it's not allowed to do that， and therefore I get a permission to error。

You might have seen this if you like search for something， end up on stack overflow。 And it tells。

 just run this command。 and you'll see that it does something like。They give you instructions like1。

2， cis， what' an example， net IPV 4 forward。 for example。

 this is something you may have seen if you're setting up a firewall and this command is intended to work because this little pound symbol indicates run this as root。

 This is something that is very rarely explained。 but that is what the pound symbol means。

 You'll see on my prompt as a dollar symbol instead。

 and the dollar indicates you are not running as root。So the question is， how do I get around this。

 Well， I could switch into a route terminal。 So one way to do this is to run pseudooss。

 Suoss is saying， run the following commandus route and Sue is。😊。

A complicated command that effectively gets you a shell as the super user。

So if I do this type of password， then now you'll see that the username at the beginning changed from John to root。

 and the prompt changed from a dollar to a pound。If I now echo into that file。

 if I do echo 500 to brightness。My screen got a little dimmer， but you can't see it。

 you just have to trust me and now I didn't get an error and this is because the shell is now running as root。

 it is not running as John， and the root user is allowed to open this file。

But given our knowledge that we have of the terminal now。

 there's actually a way for us to do this without having to drop to a root shell。

 And that is as follows。Let's I guess restore it to 1060。So do you see why this is different？Here。

 I'm telling my shell to run the E 1060 command。 which is gonna echo 1060。

 and I'm telling it to run the pseudo T brightness command。

 And I'm telling you to send the output of echo into pseudo T。😊，In order to understand this。

 you need to know what the T command does。 The T command takes its input and writes it to a file。

 but also to standard it out。So T is a convenient way if you have， say。

 a log file that you want to like send to a file to store for later。

 but you also want to see it yourself。Then you can pipe it through T， give it the name of a file。

 and it will write whatever its input is， both to that file and to your screen。

And here I'm taking advantage of that program。 I'm saying run T as root and have T right into the brightness file。

And so in this case， the T program， which is what is opening the brightness file。

 is running its route。 And so it is allowed to do this。 If I run this， it will now， again。

 you can't see， but the brightness has now been turned on by my laptop， and I don't get any errors。

 And I never had to drop into a root cell and run commands there。

 which can often be somewhat dangerous。If you want to explore this file system a little bit more。

 there's a lot of interesting stuff in here。 If you just sort of start browsing around。

 you can find all sorts of fun things。 So， for example。

 we noticed that there was a fun brightness command here。

 I wonder about other kinds of brightness I can set。😊，So I can use the find command。

 which we'll also talk about in a coming lecture， I want to look any file whose name。

It's a little like brightness in the current directory。 that's unhelpful。 Maybe they're not files。

Did I misspell brightness？why is it being annoying？诶。

Oh apparently it does not want to search for brightness for me。Oh well。Luckily for you。

 I know of one already。Hy that。 There is a subdirecty called LEDs。 and LEDs have brightness， too。

 What kind of LEDs are there。 lots of things。 For example， the scroll lock LED Now。

 most of you probably don't know what the scroll lock LED is or much less what scroll lock is。

 But you might have seen a key on your keyboard name named scroll lock。 basically。

 no one knows what it means anymore。 No one really uses it for anything。

 It's mostly just a dead key and also a dead LED What if you wanted to configure it so that every time you get email。

 your scroll lock LED lights up because there's no other reason why it would light up。 Well。

 if we see into this particular directory。😊，There's a brightness place and it's set to zero， well。

 what happens if I write one into it？You probably should not just be writing random numbers into random files in this directory because you are affecting your kernel directly。

 like look up what the files do in this particular case。

 I have worn safety goggles and I have done my research so now you can't tell that on my keyboard。

 the scroll lock LED is now lit。So now， if I wrote a program that like did some checking of mail and stuff。

 I could have it at the end， run a program that echoes one into this file。

 And now I have a way for my LED to my keyboard to indicate when I have new email。At this point。

 you should know roughly your way around the terminal around the shell and know enough to accomplish at least basic tasks。

 at least in theory now you shouldn't need to use like point and click interfaces to find files anymore theres one remaining trick you might need and that is the ability to open a file so far I've only really given you ways to find files but one thing you should know about is。

Ming semester X， D G dash open。 This will probably only work on Linux on Mac OS。

 I think it's just called open on Windows。 Who knows X D G open。

 you give the name of a file and it will open it in the appropriate program。 So if you open。

 if you do X D G open an H L file， it will open your browser and open that file。

 And once you have that program in theory， you should no longer need to open like a finder window ever again。

 You might want to， for other reasons。 But in theory。

 you can accomplish it all using the tools that we've learned today。

This might all seem relatively basic for some of you， but as I mentioned。

 this is sort of the ramp up period of now we all know how the shell works and a lot of what we'll be doing in future lectures is using this knowledge to do really interesting things using the shell that sort of this is learning the interface that we're going to be using and so it's important we all know it。

We're gonna talk a lot more in the next lecture about how to automate tasks like this。

 how to write scripts that run a bunch of programs for you and have to do things like conditionals and loops and stuff in your terminal and do things like run a program until it fails which can be handy in classes where you want to run something until your test suite fails for example。

 So that's the topic for next week's lecture。 Did you have a question Yeah just related to what you've been demo directoryre if you're subsist。

That is a good question。 I don't know whether the Windows subsystem for Linux will expose the ci file system。

 If it does， it probably only exposes a very small number of things。 it might because there are。

I don't know。 Check it out。One thing you'll see is the lecture notes for this lecture are already online and at the very bottom of the file there are a bunch of exercises。

 some of them are relatively easy， some of them are a little bit harder and what we encourage you to do is to take a stab at going through them if you know this stuff already it should go really quickly if you don't it might teach you a bunch of things that you might not realize you didn't know and for the office hours that we're going to do right after this lecture we will happily help you get through all of those or if there are other commands you learn in the process you want to know how to use more efficiently and then in next lecture which is tomorrow we'll basically be assuming that you know the kind of stuff that the exercise is going to teach you。

There's also an email address on the website where you can send us questions if you think of something like after the office hours are finished。

Are there any questions before we end today？Now然。Right， well。

 we will have office hours on the9th floor of the Gates building of Building 32 in like5 minutes。

Sweet， see you there。