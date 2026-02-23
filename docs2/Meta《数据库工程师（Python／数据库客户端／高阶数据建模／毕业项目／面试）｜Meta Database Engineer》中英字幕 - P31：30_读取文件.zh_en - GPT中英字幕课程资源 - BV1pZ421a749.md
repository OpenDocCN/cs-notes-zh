# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P31：30_读取文件.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

You already know how to handle files in Python， but do you know how to read the content of a file？

Being able to read files is essential when working with stored data in Python and Python offers several built in functions to make this easier。

The three methods we'll explore in this video are read， readline and read lines。Let's start with Re。

The read method returns the entire content of the file as a string that will contain all the characters。

You can also pass in an integer to return only the specified number of characters in the file。

The second method to read filess and Python is Readline， let's explore this method。

The read line function returns a single line as a string。If for example。

 you have a file with two lines of text that say this is the first line and this is a second line。

 the read file function will return as the output， only the first line of text。

 this is the first line。The Read line function can also include an integer argument for returning a specified number of characters on a single line。

 let's say you use the same testing file but pass an integer of 10。

 your output will be the first 10 characters of the first line。In this case。

 the words this is and the letters TH for a totalal of 10 characters。

The third method to read files in Python is read lines。Let me demonstrate this method。

The Read liness method reads the entire content of the file and then returns it in an ordered list。

This allows you to iterate over the list or pick out specific lines based on a condition if for example you have a file with four lines of text and pass a length condition。

 the read files function will return the output or the lines in your file in the correct order。

Fileles are stored in directories and they have paths。

 reading files from the same directory is straightforward， you only need the name of the file。

When working with different locations， however， it's important that you know the difference between absolute and relative paths let's start with absolute paths。

Absolute paths contain a leading forward slash or drive label。

An absolute file path includes all the information you need to locate a file。

 whether you are in that files directory or not。Relative paths normally don't contain any reference to the route directory and are normally relative to the calling file。

A relative file path only includes the information you need to locate a file in your current working directory。



![](img/9b1a5492fe173e56976c6c802a1ab47a_1.png)

I'm now going to demonstrate how you can read files in Python。I start with a simple sample TXT file。

It just has some text with a couple of lines that I'll use and demo some of the options there are for reading and files I start by using with open and I pass in my file name。

 which is sample do TxT。I just want to read in the content so I set the mode to be R and I assign it to a file variable。

The first option to read a file is to print the entire contents of the file。To do this。

 I use the function print file dot read and I click on the run button。

 notice that the entire contents of the file is printed out as is。

The second option allows me to print out only a certain section of the file， for example。

 let's say I only want to print out the quick brown fox jumps over the lazy dog that's 44 characters。

I could pass in a parameter to the read function， which tells the function to read in the first 44 characters。

To do this， I enter the number 44 and you notice that it prints out only the first line when I click Run。

😊，The way this works is that it starts at the very beginning based on the index of zero and 44 is the last character that needs to be printed out。

In this way， I can control what sections are printed out。

The third option I have is to read in a line。So the function I want is dot read line and it will only take in the very first line from the file。

I click on run and it prints out only the first line of text within that file。

 The fourth option is to use the dot read lines function that will return a list of lines。

I click on run and you notice that the text in the file is now wrapped in square brackets。Lastly。

 because it's a list I can assign it to a variable， for example。

 I can say data equals file dot read lines and then I can write a full loop for x in data。😊。

I print the value of X， and then when I click on run。

 you'll notice that the list items are printed out line by line。😊。

Something to note is that when you use the with open and you get as file。

 it returns a list by default， I can just change the for loop so that it points to the file variable。



![](img/9b1a5492fe173e56976c6c802a1ab47a_3.png)

When I click Run the same option is returned， these are just some of the methods you can use in Python for reading in files。

You should now be able to describe how to read files in Python and demonstrate how to output different formats using the read。

 read line and read lines functions。