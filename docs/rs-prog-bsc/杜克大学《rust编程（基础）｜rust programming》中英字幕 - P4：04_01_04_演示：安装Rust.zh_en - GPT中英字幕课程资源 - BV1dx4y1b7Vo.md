# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P4：04_01_04_演示：安装Rust.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/4450a1cead5c1734aaafb0bf56bfbd2b_0.png)

Installing rust is very straightforward。 I'm using a Linux system for this example。

 which will work very well if I use these now this installation method will also work with a Mac computer and an Apple computer if you open up the terminal So that's what we're gonna to try out but just in case you're not using either Linux or you're not using something like a Mac computer。

 you can definitely go and take a look at the other supported installers。

 you have the ability to download the rust stop in it executable for Windows So definitely you have several different options。

 Now I'm going follow up with the command here and I'll go through some of the things that we need to do。

 so I click on on this button to get that hole command copied over it will essentially download a script and then it will execute with the shell。

 so I'm going switch over to the terminal。I have a running terminal here。

 let's take a look at what type of system I have here in this case I have a Linux operating system and to take a look at thatm I'm going to go and look at that content of OS release so in this case it's Ubutu 2004 it's a long termm supported release。

So that's fine。 So it's a devviianbased Linux operating system。 So that's fine。

 let's clear that out and paste the commands。 Okay so I've pasted the commands and I have curl here protocol is HtPS that's fine It's going to use that version of TlS I's going to have some extra flags here and I am going to be again downloading that script and executing it on the file。

 this is actually a pipe if you're not familiar with those it will just retrieve the contents and then execute them so I'm gonna to hit return。

And what that happens is that there's a download the installer gets downloaded and I'm presented with several different options so I'm going to scroll a bit over to the top I get the welcome rust I get several different things that will get created on the fly for me some utilities like cargo will have their separate directory we will dive into what cargo is and how it works later but this sets everything up so is' very。

 very convenient some of the things that will get updated are going to be in in these files。

 these configuration files which which will help me get the right path for the tool that I'm installing so let's go ahead and review the options this is going to be used in the Linux is going to install the default version rust profile default is fine and modify variable path variable yes I want to modify the path variable that means that。

The commands that I have available in the terminal。

 we get updated to include the rust and all the other rust tools that the installer will get。

 So I'm going to say that I want to continue and proceed with the installation。

 almost always this is the option that you will want to use in some other corner cases you might want to have some custom custom installation that you want to tweak and that's fine。

 you can definitely go ahead and and dive into those but for these lesson will just proceed with a regular installation。

 so I'm gonna to click one or type1 and then enter this will take a quick second and let's just wait it out until it completes great rust is now installed and things appear to have completed successfully So how do you verify that this works Well the first thing you might want to say or to do is to type rust C but if you do this right away you will get a command not found Why is that because I haven't。

Updated my path。 So my path， if I do echo dollar path will not have an。

 I know that this is a lot because this is pointing to several different things that have。

Executables， but none of these paths here will contain the actual path that contains my rust binaries and all of the extra tooling。

 So what I need to do is run these source home cargo M。 So let's go ahead and do that。

And now if I do rust C you will get the whole menu。

 So if I do which rust C to see where this is coming from。

 you will see that this is coming from do cargo bin directory in my home directory So that's pretty useful to know and it is the way where we verify how rust where my binary。

 my executable。 So I install， I'm going scroll the way to the top and you can see here I'm getting the help menu and lots of different options for rust C。

 there are other tools that have been installed as well like cargo。

 So if I say which cargo it will point to the dot cargo subdirecty in my home directory if I do cargo dash help and I clear that and run it again we will get several different things there as well for the output。

 So all in all D is a very straightforward way of installing rust and it's very。



![](img/4450a1cead5c1734aaafb0bf56bfbd2b_2.png)

Very concise， very， very easy to follow， especially if you're not tweaking things around。

 and you follow the prompts， remember I had to source。

 had to actually call source on the command line and that made sure that wherever the bin the executables are installed for the tool chain that I'm working with in rust are going to be available in my system。

