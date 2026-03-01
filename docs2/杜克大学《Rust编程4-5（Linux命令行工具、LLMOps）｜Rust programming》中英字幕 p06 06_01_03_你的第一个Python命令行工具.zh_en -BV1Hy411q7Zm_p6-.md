# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p06 06_01_03_你的第一个Python命令行工具.zh_en -BV1Hy411q7Zm_p6-

![](img/72cf0499f30ea0cf911586b5346cba65_0.png)

Let's work with one command line tool example project that we have here and what we'm going to do is well I'm going to show you a few of these files。

 but I won't go into a lot of detail into them yet because some of these features like C the Pi which is more meant for packaging we'll see in detail later。

 Let's start with the problem scenario。 What are we trying to solve here So I'm going to open up a terminal。

And in this terminal the thing that we're going to do here is when to run LS block。

 so LS block is a commander will list block devices and the output that we get is pretty straightforward we get the names of the devices。

 some information there for the major minor and RM which I don't remember what it stands for what's the size in human readable format you can see that we have 32 gigabytes and some other 500 megabytes if it's read only if it's a loop device or a partition or a whole disk and if it's mounted where it's mounted。

 so pretty straightforward what is the problem we're trying to solve and this is something that will come up when you're doing kind of like devop tools that will help you is that usually LS block。

 if we do dash dash help and we scroll the way to the top。

You will pass in an optional device if you don't pass the device we' will list all of the devices right so let's take a quick look at what happens here where do Ls block we have all of those devices so ideally I could pass in something like SDA and whether we get LS block SDA is not a block device which is wrong because it is let's try it with SDA1 which is a child of SDA。

And also the same and actually we can try with anything here and we'll get the same problem as the B as D V1。

 Let's try one of the lu devices， loop 0， not a block device。 Now， why is this happening。

 This is happening because behind the scenes I'm in a container and because I'm in a container these are not real block devices these are kind of like sort of like emulated。

 but not quite emulated， The details of why that happens is not important。

 The task at hand is that we're going develop a tool that we're going to be able to use。

 the information that else block provides so that we can get that information nicely produced with a command line tool。

 All right， so that's the problem What is it that we're going do so So I'm going close these open up one of the examples I have here and what' the simplest example here Now one of the things that happens in vicious serial code is that。

When I don't have extensions installed， I get that prompt， yes。

 I want to go ahead and install it and this will give me all of the things that I need so in case I don't have that available in my environment I will get that a prompt to get that installed so perfect that's it that will take a second and I will give me all of the intelligent recommendations there that I need so I'm going to close these。

And let's walk through the simple pie I'm gonna close the extensions there for a second to make this bigger。

 and let's walk through some of the things that I have here。 I'm not going install Pyin right now。

 I I'm going start at the very bottom So in a command line tool the most simplest command line tool that you can build。

 you will start off by and in these lines at the very bottom So what this thing does is that it make sure that when you're executing when you're running this script。

 this Python file that you have with with Python as the executor then it will run this part。

 So this will allow you to also use this as a library if you were to choose that and only execute this if you are running on the terminal and executing with Python So if I do Python and then what the name of this file simple the P this portion will execute so。

's perfectfect And next， what happens is that we have this kind of weird looking cyst that Rv and then square brackets minus-1。

 What does that mean the-1 means that we will get the very last argument that is passed on to the command line tool call on the terminal So regardless of of the argument。

 What this is doing is essentially saying I don't care what arguments you have。

 I'm just gonna pick up the last one and use that as the argument that I need to pass into main this will always come in the way I have it here you will always come in as a simple string regardless if you're passing numbers or actual strings or something else this will always come in as a string So no dependencies nothing needs to be installed。

 everything that I'm going to use I'm going to scroll the way to the top。

 everything that I'm using is in the standard library I'm going to use as a process S H legsx。

S however are you want to say it and Jason these are all modules from the standard library so so that that's very powerful because you can build actually pretty good command line tools in a single Python file without worrying about packaging we're out worrying about all things the only thing you will need to worry is about having Python installed in your system which I have all right so the main function the only thing that it does it receives the device argument and as you know that will be the last thing that we're passing。

And then it will run run underscore LS block， so what is that run L block8 is this function over here？

And this function over here， what it does， let's take a look。

 this is the command that I would run passing dash J because I want Json output and I want specific homess in this case I want the name。

 the size， the type and the mount point so the JON output that comes out I will have block devices as as the main entry point which contain a list of array of items and each item will represent some of the items that I'm interested in so the idea here is that I will poke around the names。

 the name values and based on that if anything matches the argument that I'm passing in will return it So let's take a look at what happens here will start right here with the command that's the command I want to run we're going to use this utility show in a second that is called run underscore command we're going load the output in JO and then we're going to loop over the output the。

Jason that load S means load the string using JN and essentially in Python it will load the JN and put it as a dictionary。

 so we look for parent in devices， the devices are the ones that are coming from block devices。

 if the parent name matches the device it will return the parent so in this case if I pass PA it will return that whole thing。

Otherwise keep looping to the child items you know children are part of this list or this array in Jason and you might have one or more or zero more actually children and we'll go and look for those and then return the child that's it that's for run ats block and let's take a look at run command。

And what we'm going to do is we're gonna to split the command so we can pass it as a single string。

 this is a fairly common construct here for splitting string into various pieces is something that comes from sub process that is required for this subprocesed module when you're running check output so that command will come in here and then we'll return the output as a big blob of string now this is not doing any error checking which is something that we should fix at some point and we will but for now this is super simple I'm to run a command。

 we're going to process the output I'm going to check the names and then we' to return the output with that set let's open up the terminal again and going do that and then without I'm going to clear the this output and without doing anything or installing anything I'm going to go to examples I'm going to check the Python version that I have in this case is Python 310 perfect I'm going to clear the terminal and I'm going to do Python。

I'm going I say simple that pie andm pass， I'm going to pass， let's say VD。So there's nothing there。

 let's run El block once again to see what are some of the things that I have So there's no V perfect。

 So I'm going to pass something that does exist。 So how about SD DB。Great。

 we do get some output there。 SB comes out。 This is this output is exactly what I would expect because coming from here。

 you can see the size is 16 gig。 Let's check that perfect 16 GB right there。

 How about we capture one of the children。 So S D B1。 So that works is mounted in slash temp。

 let's try a loop device loop0。 So great。 So we have these producing very good。

 very nice output based on what we want。 So let's see some of the things that we've covered in these very simple examples。

 I'm gonna close the terminal and go back to these very simple example， simple file。 So first off。

 we're making sure that we are using only。😊，Modules and libraries are coming from a standard library。

 This is important because by not requiring external libraries it allows me to get this script copied over to many systems that I may want to use it and make it available as long as Python is installed。

 we're good to go now we have separate functions we have like this very error prone function that is not checking for errors just yet and then we have the run L block function that will process the output this is also not checking for errors and is blindly trusting that device will always work and then the main function over here will allow you to again execute that and run L block by using print and anF string and at the end as I mentioned we'll have to use this snippet so that when we're running we're executing with Python then this will execute actually。

If I may really quickly， I'm going to comment this out so that you can see what happens if I comment that out。

 I toggle the terminal and I run that， nothing happens。 So why nothing is happening because。

Because then Python doesn't understand that it needs to execute main or the device has to come up with an argument right there。

 so if I uncommon these and clear here and run it again， well things will work， no problem。

So there you go， this is the very simple， very straightforward command line tool that can take arguments and C Rv actually one last thing。

That I want to do is I want to print system Rv so that you can see what you're dealing with。

 This is actually pretty useful。 you want to do a little bit more things that are now very complicated。

Simple and loop are the two arguments， so this is kind of surprising uses the name of the script and any arguments that we're passing so there you go this is very useful。

 you have certain components that you can reuse for Python to build Python command line tools and distribute them without any libraries or packaging that might get you into more complex development environment。



![](img/72cf0499f30ea0cf911586b5346cba65_2.png)