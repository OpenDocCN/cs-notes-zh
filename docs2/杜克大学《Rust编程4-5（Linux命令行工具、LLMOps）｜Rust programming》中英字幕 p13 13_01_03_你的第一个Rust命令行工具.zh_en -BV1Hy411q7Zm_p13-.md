# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p13 13_01_03_你的第一个Rust命令行工具.zh_en -BV1Hy411q7Zm_p13-

![](img/8a03fe3ff2d9d536c9a8dbfbe45b4071_0.png)

So before we get into the first command line tool that we're going see with rust。

 let's very quickly go ahead and take a look at what we're working with like we're in a different environment right now and the way we're going take a look is looking at OS release and we're working with Uuntu version 20 that's 04 a long term support version of Ubutu。

 So that's very good。 And now we're going to run。The， the。Rust up command。 I I allow here。

 we're using cool spaces here。 and this is something that I said I was not going to get into details。

 but it is worth going and proceeding with installation。

 and you will see everything that is getting downloaded and making sense for what we want to do Now this will take a quick second because look at all of the stuff that is getting installed cargo clippy some of these we've already seen some of those we haven't seen yet。

 So I will go ahead， this is a fresh botu version that I've just installed and available and it just completed perfect。

 So the next thing I'm going to do is going to do this source home cargo。

 I'm like now next time I open up the terminal that's going to work And the thing that this does is it gives me the ability of saying which。

Wch rust see， for example， and which cargo。 And that's pointing to the right the correct place。

 So now let's take a look at what version of rust to have version 1。68。2 perfect。

 So let's thats that's good。 That's great。 We have rust installed。 I'm gonna close the terminal now。

 And now let's take a look at what we're gonna be working with。 Again。

 the problem statement that we're gonna solve is actually running Els block and why is Els block so important。

 We need to find the business requirement here is we're going to open this again。

 The business requirement is that we can run Els block。 as you can see。

 this is the same as we did for Python。And it prints out this information that's perfect。

 But if I do Ls block。 So say， for example， SDb， then we say， hey， this is not not a block device。

 SDb1， this is not a block device。 So this is the problem that we want to solve let's take a look at the code that will implement a replacement for Ls block that will work。

 And the reason why this is not working， by the way。

 if we missed it when we're talking about Python is that we are in a containerized environment and L block is not well。

 these are not real， real block devices。 So L block refuses。

 So we' want to do is use Ls block in JO format。 So if we do。If we do that then pass pass in dash J。

Well， it doesn't like if we do it like these， there we go。

 So we're gonna grab all of that information and parse that and get specific information。 Allright。

 so I am going to close these and let's take a look at main Rs main that Rs is where everything happens for our command line tool rust by default will execute these main function first and from here it will you know it will go through all all the R function。

 So one advantage aside from Python is that this is the default。

 you know the goal length does something similar where the main the main function is the main entry point。

 it is actually pretty straightforward to create a command line tool So all you need to do it will be to create a function a main function and then you get to go。

So that's the code。 there's a lot of going on here。 so let me scroll all the way to the top。

 I'm gonna get rid of the file Exper。 I'm going to scroll the way to the top and walk you through what are we going to be doing here so lets let's see so we have a run command This is very straightforward we're going to do here is going to passing a command over here and that command is going to go to a vector。

 a vector if you're not sure about rust's like a listing python and it will collect some items that are all strings and it will split the command into into white spaces and then collect it will produce that vector then it will run command which was imported right here and we're going to we're going to run we're going to run this is going to be the executable and then the arguments are everything else and then we're gonna to parse the output。

And then we're going to expect that that's going to work if it's not this is going to raise a race。

 but bubble up that problem that error with a fail to execute command man now this is not very good just yet but that's fine we're just walking through what we're trying to do and then finally we're going to capture the center out and send that back as a strain perfect and then the run else block is going to receive。

Well， it's going to define that command that we're going run and then it's going to use a run command here。

 which is this function over there and then we're going to load the serialized。

 remember we're passing Jason that dash J flag means that we're gonna get Jason back we're going assume that that's going to work perfectly there's a lot of assumptions going on for for this to work and then we're going to look at block devices and we're going to loop over for every single parent and if the name matches we're going return that if the channel matches we're going to return that otherwise we're going panic for now I mean this is not production code production ready code because we're panicking and and we shouldn't be to end that way we should be bowling up nicely the errors。

 but for an example command tool this is good enough All right so how do we do this let's toggle the terminal again we are the first thing we to do is we want to run cargo check let's see。

It's fetching fetching cre that I owe that index because we're using a dependency while that's running。

 let's take a look at our dependency cargo Tael we are going to close these and we're using these dependency called third Jason it is a library it allows us to serialize Jason perfect so let's open up let's open up our terminal it is still fetching let's just wait it out until complete and all the dependencies are downloaded great everything download it everything's good cargo check was didn't find any problem so now we're going to do we're going to clear all of these I'm going get rid of that I'm going to say。

Cargo， well， we， there's， there's two things that we can do here。 We can do car cargo build。

 And actually， let's just try that first。 So it's building， is's compiling。

 It's producing our CI example。 What's the name of the CI example。 Well。

 if you go here and you go to cargo Ta And we get this a little bit lower。R 2 is going to be named。

Block Rs。 That's the name of our tool。 So that's what we've built。 That's our binary。

 And where is our binary going to be is going to be in the target directory。

 So let's let's find out and let's actually go to target and then debug and it's going to be should be。

Bill， actually。Lock Rs is right there。 and if we run it， train， threat main panic。

 that device now found because we didn't pass any arguments。

 so actually I forgot to mention that let's take a look at the code。

We forgot to mention that the main function is looking at the arguments on the command line。

 and it's using the last one as the argument for the device。 We didn't pass anything。

 So we are breaking the tool。 So let's pass something that we know exists。 So SDB。

Now we get we get the output there that we want， so that looks pretty good， so that's SDb。

 how about SDb1， perfect， that looks correct to me。So we build it。

 but do you want to build every time you're working with the tool， Probably not。

 sometimes you want to just run it all in one go because remember we want first we let's scroll back up here。

 first we did the cargo build and then we executed the actual tool So instead of like doing this in steps we have the ability of doing this cargo run and say SDP1。

 So this will do the compiling and the running。 So this is the compilation and this is the running of the tool and you can even see we get the full path right here and this is the argument and perfect it works just as fine。

 So now we're developing now we're taking control of our tool that we we have here we're still not getting into all of the details we know it's working。

 know we have something that works well that functions well and now we've seen。

Cargo built and cargo run， which are also part of a development workflow that you can use when you're building your command line tool application in this case。

 Okay， so that puts us in in a very， in a very good， good spot。

 let's let me close this here and let's walk through some of the things that we need to。

 we need to make sure that we're not， we're not quite doing。 So first off in。In rust development。

We are really not supposed to be doing a panic like like here。 we we should， we should be， you know。

 this is run as else block should probably handle layers。 we're going to handle layers later。

 We're going improve these。 We're going make a better。

But for now this is all fine and at the end we're printing the output but we're not dealing with any errors whatsoever。

 what happens for example if we say LL as block and we say we togg the terminal and we do cargo run andre going to we're going to get into a panic because。

We're going to get a not found message。 not so no such file or directory。 We'll deal with that later。

 But one thing that is important here is that when this was compiling it compiled again and it took slightly better half a second to compile versus 0。

01 seconds before because here I was rerunning and here I'm running again yes。

 but with new code So there needs to be some compilation and it runs the target again so perfect。

 So that is a。A very brief overview of what this tool looks like with let's actually unbreak it again。

And we are looking at block devices again， we're looking at the output， and if it's found。

 then it gives you hey， like I find it or it's panicking device not found。

So this is a very straightforward， just three functions we have run command over here。

 we have the run L block。Function over here and then the main the main function。

 which is processing the arguments directly from the command line。 Now。

 this is not using any command line tool frameworks which well see later to make some of these easier to provide a help menu to provide error handling and all of the other extra things that are useful from command line tool frameworks。

 So that's it that those are some of the components that this tool has。

 That's the problem scenario we installed cargo we use cargo built and cargo run。

 and that should get you ready to work with with these command line tool。



![](img/8a03fe3ff2d9d536c9a8dbfbe45b4071_2.png)