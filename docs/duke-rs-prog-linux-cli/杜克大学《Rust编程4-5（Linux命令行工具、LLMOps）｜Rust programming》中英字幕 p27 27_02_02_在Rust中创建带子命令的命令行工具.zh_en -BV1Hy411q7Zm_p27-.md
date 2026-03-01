# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p27 27_02_02_在Rust中创建带子命令的命令行工具.zh_en -BV1Hy411q7Zm_p27-

![](img/c5cbed008654686fbf82c6162e8355ce_0.png)

Let's add a subcom to our rust application here again， this is Ls block， which is a wrapper。

 this tool that we have here with rust is a wrapper to Ls block if we open up the Expr。

 you'll remember that we have here or Lib at Rs and that is not going to change it is effectively calling Ls block right here。

 parsing the commands and doing some Json parsing Now before we add the subcomd and to close explorer here for a second if I go back to mainine we're no longer going to use this approach where we have the matches with new command that we're building like these。

 we're going to make some surgery to this file so that we use the rife capacity or feature from clap and before we do that I've updated my cargo that Tail so that it。

As this derived feature This is key because otherwise nothing in here is going to work correctly so I'm going to close my cargo doal going back to here to our file and what are some of the things that we're going to do Well we are going to remove some of these things we're going to leave the block Rs library。

 the run under Scres block function and then from clLab we're going to change the imports and of course things are going to start getting into a lot of underlines there because things are going to start breaking while I do some surgery here。

 So let's start by just using the parser there。And the next step we're going to do is we're going to do the ri。

 So we' going to say the right parser。And the right parsel is going to allow us to do nifty things here like saying command and the command is going to look very much like this。

 it's going to look much， much nicer。So that looks pretty neat and we have version author and about so basically the same thing that we had here and is's going to make sense to organize and you're going to see how clean this looks later so I'm going to build thestruct here I'mm not going accept what compile that is suggesting here I'm going to dostruct ops that looks correct to me。

 but instead I'm going to say clap and I'm going to say help menu is going to be this is actually not right。

 So clap and help is going to be the vice to query。

 So I'm going to keep it the same as it was before。And that looks okay to me when I remove that。

And then this is going to have the numerical sign there。 I say the is a string。

 and I'm going to save that。 So that's fine。 And then we're going to remove all of these in main。

 and we're going to make these a very simple， very straightforward。 I parse the options。

 and when I save the output。Is what we have to serialize remember。

 so we have Sir Jason to string pretty that looks， we can say we can accept the string pretty but we can check if that works correct and then we print it out Now if we run these then I believe these should just work but see how much more simplify these is it's things are in a separate place and that looks much much much cleaner and I really like these way so that's the ri feature that we have here for clap so let's run it and call the terminal and we're gonna clear these and then run and say cargo run video1 and see what happens okay so that completed it runs correctly and now we have effectively what we've had before and we have a tool that works。

ectly， it's like it uses the string pretty there to have like this nice representation of the a that is coming in。

 but we want to add a subcom。 So how do we do this。

 let's actually close that and start building what we want here we're gonna have to make。

 unfortunately， more surgery to this file so that we can have a command so now that we have thisstruct over here online 10。

 we're gonna have to make some changes to that。 So the first thing is that we're not going to we're no longer accepting the device as is at the very root we' are going to use a subcom And the way we're going to do that is by adding something slightly similar。

 So instead of clap help device to query， we're gonna to say we're going to say subcom right here going remove that So whenever you're building a subcom。

 you're gonna have something something like this and instead of the here we're going to say CMD for command。

AndAnd here we're going to pass a command。 Now， where is this command coming from because right now it it's not coming from anywhere。

 we're going to have to create it。 and that command is going to be a we're going to have to say it's derived right parser again。

 as always to try to associate it with a parser for clap。 and we're going to create the en numerator。

 So I'm going to say en numerator is going to command to be command。

 the suggestion from Coella is not quite right here。 We're going say in this case， this command。No。

 it's not going to be device。 We're going to say clap and clap。

 we're going to start adding things here。 So I'm going to say info is going to be our sub command and about is going to be。

Get info about a device。 So that looks correct to me。 And I'm going to say info。

 we're gonna to say info options。 So we're going to separate the options into something else that is not going to be an enummerator is going to be one and then again。

 we need to use the right parser once again。 this is going to be astruct。

 So let's take a look at the suggestion。 we're going to accept that。

 So this arrived parser is always required。 you can see it right there and right there。

 So that is what gets us into this parser that now clap understands how to figure out all of these things。

 how they go together。 So this final piece here for the subcomd。

 basically now does have the device because these options are the one available for the command that is going to be called info and you can see that I'm defining exactly how that is called。

 if I wanted something else that would be definitely changed right there。Alright。

 so one last thing that needs to change here is that these no longer would work because we need to we're using a numerator on the command。

 in this case it's info and we need to match right Otherwise how we're gonna like this is not like if we actually wanted to run this it it wouldn't work and we can actually test this pretty pretty quickly and we're going to start getting unknown fields as you see here。

 All right， so let's make this work。 let's remove the terminal option right there and let's start doing slightly more surgery right here。

 So the one line that is going to stay the same is this one So the options are going to stay right there。

 Now we need to match on the options command。And this is， this looks right。 So I'm going accept that。

 So what's going on here， Let's break it down because I just accepted a suggestion from Copit。

 So we're matching on the command。 We have potentially one or many commands。 in this case， Of course。

 you know that we only have。One well an enummerator called command and that only has one item called info。

 So we need to match on info。 How do we do that， We'll look at all of the commands and if the command is a command info we are going to say what is the device what is the output and we're going to print print that out as you can see right there。

 So let's open up the terminal once again， so we're run cargo run V1 which is our device that we want to query and we're going to get an error why it's an error because we're no longer we don't have a subcomd V1 we're no longer taking the device name as an argument。

 So now we can say cargo run dash dash help that double dash that I just added right here will allow us to pass this dash help onto our application that cargo will build otherwise cargo with things like that dash。

Help is for me and I need to consume that and that's not correct so let's do that and you can see now that info is right here that this get info about the device is right this one coming from the numerator from command if we actually change this to something else。

We can say how about part just to call it something something completely different。

 And if I run help， it will take a second for these to build All right that did take a couple of seconds more than a few seconds in a slower machine it took almost 26 seconds to build but the part you can see now that this is no longer info it's called part All right。

 but now let's run it properly so we can say part and we can say Vda1 and that should actually work pretty well and you can see that the J is right here doing its work no problem。

 So that is getting past in and that is working working like we were expecting。

 So this is now how we've added a subcom and let's actually close the terminal。

 let's look at our code that we have right here we did some surgery。

 this looks more compartmentalized more modular work。Things are isolated in the same thing。

 we have our options right here， we have our command and our actual command right here that is coming from info like this info right here is coming from these and it is all connected together and working very very nicely now when the one thing is that when we're matching we need to make sure that the info is coming right there now I did make that change of renaming these from info to part that might get confusing if you start having names that don't map quite well to these things because or wise you're gonna say why is this called part and why is this called info if everything's info wise is in this info as well so try to have some consistency that will help you when you're building these subcoms。



![](img/c5cbed008654686fbf82c6162e8355ce_2.png)