# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P29：28_Python中的文件处理.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

Yeah。File handling is an essential part of learning Python Python has several built in functions to create and manipulate files。

Fire handling includes opening， reading and writing files amongst other operations。As a developer。

 you'll probably work with large amounts of data and far handling makes that easier。😊。

This is why it's important to learn how to work with files。

Whether you're working with data on your computer， on the web， or in the cloud。

 it will most likely be saved in some type of file。There are two file handling functions in Python。

 open and close。Let's explore the open function first。The open function is used for reading， writing。

 and creating files。The open function accepts two arguments。

The first is the file name and or the file location， and the second argument is the mode。

The mode indicates what action is required， such as reading， writing or creating。

It also specifies if you want the file output in text or binary format。

Let's explore the modes of file handling you can use in Python first you have R which is used to open and read a file in text format and RB opens and reads a file in binary format you'll learn more about this later R+ on the other hand opens the file for both reading and writing and W opens the file for writing。

Note that W will overwrite the existing file。😡，Lastly， A opens files for editing or appending data。

Next， there's the close function。The close function is used for closing the open file connection。

 note that it does not take any arguments。There is one more way to open and close a file in Python。

 and that's with the with open function。The advantage of using it is that it closes the file automatically。

 the with open function will be demonstrated shortly。By now。

 you understand how to open files for certain actions。

 but you might be wondering what the difference is between opening a file in text and binary format。

In Python you generally handle files in two ways， either in text or binary format。

The text format is more user friendly because humans can read it。😡。

You'll not be able to read files in binary formats。

 but they are much more compact and therefore result in better performance。😡。

Now let's cover how to specify the type of file handling in Python。

Python uses text as the default format for file handling。

 so just passing in any mode for reading or writing a file will automatically set it to a text format。

To set the file handling to binary， you need to pass the letter B along with either the read or write option。

 for example， you write open the file name and RB to read a file in binary format or AB to append or add to a file in binary format。



![](img/8617dc98c84b690487ed294a942211f3_1.png)

You'll now explore file handling in code。First， I declare a simple variable called file and assign the open function to it to gain access to a file。

But before I can use the open function， I first need to create a new file for testing。

 let's call it test。txt。Inside this text file， I add a simple line of text hell over。😊，Good。

 let's go back to the Python file inside the parentheses of the open function。

 I can now add the first argument， namely test do Txt between quotation marks since it's a string。

For the second argument， I type in the word mode， equal sign。

 and then I will just use R for read also between quotation marks。So far。

 the variable called File will have access to the contents of the test dot TxT。

But to actually read the file， you need to add a read line or read lines function。

Readedline will just return the first line of the file while Read liness will output an array with multiple lines。

Since we only have a single line of text in this file， I'll just use the read line function。

 I type file dot， read line and parentheses。I assigned the line of code to a new variable name data。

Then I add a print statement to print the contents of data。Lastly。

 I add a close function that will close access to the last text do Txt file。

 I simply close with a set of parentheses。I click on Run and the content of the file is printed out namely the hello there。

Next， I'll demonstrate another way to gain access to a file in Python。

 I'll change the open function to the with open function I'll just clear the screen。

To assign a variable to the with open function， you need to add as after the parentheses and then the variable name。

 why would you use the with open function？The width open function is better at exception handling and will automatically close the file for you。

Just like before， I create a second variable data， readline， and then print the content of data。

I'll click on run and just like before the contents of the file are printed。😊。



![](img/8617dc98c84b690487ed294a942211f3_3.png)

You've covered how to work with files in Python， this includes the built in functions to create and manipulate files and the functions to open。

 read and write files。