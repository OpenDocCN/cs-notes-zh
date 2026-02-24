# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P60：13_重定向.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

In this video， you will learn about redirection and the different types of redirection you can use。

The basic workflow of any Linux command is that it takes an input and gives an output。

 The standard input device is the keyboard。 The standard output device is the screen with redirection。

 you can change the standard input and or output。 There are three types of IO or input output redirections。

 Standard input standard output and standard error。

 The shell keeps a reference of standard input output and error by a numbering system。

 The zero is for standard input one is for standard output and two is for standard error。

Now you will learn about each of these redirection types， let's start with standard input。

Taking input normally refers to a user typing information from the keyboard。

We use the less than sign for user input。The CAD command can be used to record user input and save it to a file How do we take input and stored it in a file such as a dot TXT file let me explain how you can do this by using an example to store user input to a text file so I have just launched my terminal but how do we take input and stored it in a file such as a dot TXT file。



![](img/49fc3993cf2ce4bbc3045f02a65d023a_1.png)

One of the commands you learn to use frequently in this course is the CAD command this command is actually set up to take in input。

😊，On my terminal， I type the CA command followed by a greater than sign and then follow it by the name of the input file in this scenario input。

txt press enter。Now I can add text to the text file created。At the end of the text， press enter。Next。

 press control D to tell the CA command that's the end of the file。

To output the contents of the file， enter CA followed by a less than sign。

 followed by input dot TXD press enter， notice that the text that I added from the keyboard displays。



![](img/49fc3993cf2ce4bbc3045f02a65d023a_3.png)

Let's discuss standard output now。A lot of the commands we have already used， for example。

 LS send their output to a special file called the standard output。

Output direction is handled with a greater than sign IO allows us to use redirection to control where the output goes。



![](img/49fc3993cf2ce4bbc3045f02a65d023a_5.png)

Now I will demonstrate how you can send output to a text file。Everything in UniX Linux is a file。

 this means every time you run a command like LS and pressEnter。

 it sends the output of the file to an STD out file in Linux if you want to control where the output goes。

 you can use a redirection how do we do that？Enter the LS command， enter L to print it as a list。

 instead of pressing enter at a greater than sign redirection。

Now we have to tell it where we want the data to go in this scenario I choose an output do Txt file。

 the output dot Txt file has not been created yet， but it will be created based on the command I've set here with a redirection flag press enterter type LS。

 then press enter again to display the directory。The output file displays to view the content of that file use the last command followed by output dot Txt and pressent the content that displays using the LS minus L directory includes the different files available errors occur when things go wrong when using redirection you also have to specify that the error should be written to a file you can do that by explicitly setting the number two before the output arrow。



![](img/49fc3993cf2ce4bbc3045f02a65d023a_7.png)

And you can also combine it with a standard output of2 greater than m%1 to print both the standard output and error if any occurs。

You have already learned that input is represented by zero according to the shell output is represented by1。

 the input stream uses the less than sign， the output stream uses the greater than sign and the error stream uses two followed by the greater than sign。



![](img/49fc3993cf2ce4bbc3045f02a65d023a_9.png)

It may happen that an error occurs when you are outputting data to a text file。

 remember that the error will not correspond with the output stream。

 it will change to use the error stream which is represented by two。

Let me now demonstrate how this works。So I've the terminal open and I'm running a similar example to the standard output。

 type the LS command。Follow this by dash L to try and print it as a list instead of using a directory that we know exists。

 I'm going to use one that doesn't exist， enter forward slash bin forward/lash USR。

Now typer greater than sign， followed by the name of the output file， in this scenario type error。

txt。Press enter。Notice that the message cannot access。

 it states that there is no such file or directory。Normally。

 you think that it would still print the contents of the file， but because an error occurred。

 it prints it to the console。There are two ways to send the contents to the error dot TxD file。

I type LS L forward/ bin forward/lash USR， then add the number two which represents the error output followed by the greater than sign Now enter the name of the output file Air dot TX press enter。

To see what we have inside the error file type less followed by the file name in this case。

 error do TXD press enter the error message LS cannot access forward slash bin forward slash no such file or directory displays If you want to handle both cases where it may find data or may not find data you can pass in a different redirection so it handles each one both for output and for error to do this again enter Ls L forward slash bin forward slash USR Next add the greater than sign for output followed by the file name error underscore output do TXD。

This time we're going to use another redirection to signify that we also want to get errors to do this。

 I enter a two followed by a greater than sign。This is followed by an ampers% sign and the number one to get the output that is available。

 press enter。To have a look inside the error file， type lessss error underscore output dot TxD and press enterter。

Notice that the air is contained inside the error dot output file displays。



![](img/49fc3993cf2ce4bbc3045f02a65d023a_11.png)

And that brings us to the end of this video now you know what redirection is and how to use the three types of input output redirections。

Well done。