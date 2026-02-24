# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P56：9_在Windows上使用Bash.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Okay， so I've opened up my terminal window， let's navigate to my home directory。



![](img/10617bd121415f9ebd62d20d6587a2a4_1.png)

I type the CD command and then ailda。Followed by the enter key。

Then I use the L S dash L A command to return all of the files in a list， including all hidden files。

 Notice two files， a bash RRC file and a bash profile file。 For now。

 I want you to focus on the bash RRC file first。 I can use the command less dot bash RRC to check this file。

 The bash RRC file is mainly for configurations。 It is essentially a script file that's executed when you first open the terminal window。

 What's in there will be configurations for the shell itself。 For example。

 the types of colorss that I'm using。 I can also add in things around my shell history like how much history of previous commands I want to store and so on。

 So any configuration options that I put in here will be executed when the terminal session begins。

 I press the Q key to exit the less environment。 The other file is the bash profile file。

 So I can run the last command again， this time with dot profile。 This tends to be。

environment variablesFor example， I can use it for setting environment variables from my Java home directory or my Python home directory or whatever is needed during development again。

 I press the Q key to exit。Now I will create a simple shell script for this example I will use ViIm。

 which is an editor that I can use which accepts input， so type Vim。

 and then I create a new file by typing the testhell。sh and press the enter key。

And then at the top of the file， I put in what type of file I want it to be。 In this case。

 it's going to be a bash file。 If I press the I key on my keyboard， it'll set insert mode。

 Then I put in a hash symbol followed by an exclamation mark。A forward slash， the word bin。

Another forward slash and then the word bash， this lets the operating system know that this is a bash script。

The script is very simple。 I want to print out some type of text onto the screen。

 so I use the echo command and type in what I want to print out。In this case， hello world。

Press E to get out of insert mode。Then I type Col WQ exclamation mark to save the file。Press enter。

 And if I look in the directories now， notice there is now a file named Testhell dot S H。

 The other thing to notice is that this file can't be run at the moment。 In other words。

 it's not executable。 It's just a read write file， but I wanted to be executable。

 which requires that I have an X being set on it in order to do that， I have to use another command。

 which is called C H mod After using this command。 I type in the type of permissions that I want。

 So I type in 755。 And then I want to set the file that I want to add the permissions to。

 which is test shell dot S H。And if I use the L S dash L A command again。

 I notice that the file has now been turned into an executable file。

 This means that I can now run the file from the command line to run the file I press dot forward slash testhell dot S H followed by the enter key。

 And now you notice the words hellello world are printed out on the screen。

 This is how you can create simple scripts and make them executable within the bashhell。



![](img/10617bd121415f9ebd62d20d6587a2a4_3.png)

![](img/10617bd121415f9ebd62d20d6587a2a4_4.png)