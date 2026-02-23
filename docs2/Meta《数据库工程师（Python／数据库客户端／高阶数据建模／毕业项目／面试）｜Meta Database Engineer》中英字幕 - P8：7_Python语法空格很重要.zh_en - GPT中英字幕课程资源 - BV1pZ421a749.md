# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P8：7_Python语法空格很重要.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

In this video， you will explore Python syntax and learn how both white space and indentation can impact a program when used incorrectly。

 in VS code I create a new file called Python_ syntax。pyy。



![](img/e3b2e85c5994753ffa9ac561347cb64f_1.png)

I start by using a print statement to generate a line of text。

 Don't worry if you're not familiar with print or variable declaration at this point。

 as that will be covered later in the course。I type print followed by the string， hello。

When I click on the Run button， the text Ho appears in the terminal panel Now let's say we want to use another print statement on the same line。

 which will output the text value world。So I add a space and then type another print statement with a string world。

 and we expect this to give us the wordsHello world。But when I click on run。

 we actually get an error。 specifically， it says syntax error invalid syntax。

 This happens because the interpreter doesn't know when the new line or statement occurs。

There are two ways to solve this problem。 One is to move the second print statement to another line。

I do this by placing the text cursor before the print statement for world and then pressing the enter key to move it down one line。

 When I click on run this time， there is no error， and I get the words hollowo and world on separate lines。

Let me undo the edits I made to my code by pressing Controlrl and Z or command Z on a Mac。

 and then try the second method， which is separating the two print statements with a semicolon in a space。

When I click on Run again， it also runs both statements as expected。Next。

 youll cover the impact of white space in Python syntax。

I first clear my screen and then declare a variable and assign it a value by typing x equals 1 plus 2 On the next line。

 I will add a print statement for x。Before I click on Run， however。

 I'll go back to my variable assignment and add a random number of spaces around the plus symbol。

Doing this will not cause any problems with this line， however。

 issues will arise if I add a new line or an end statement to demonstrate it。

 let's input a new line in type+ 3。Rritning this code then returns a value of 3。

 What has happened is that the interpreter has executed our first line of1+ 2 correctly despite the extra white space。

 but it did not account for the plus3 on the second line。

There are a few ways to work around this issue。The simplest approach is to use a force line to do this。

 I type a back slash at the end of the first line。 Now， when I click on run， it returns a value of 6。

 which means that both lines have been accounted for。

 to summarize any amount of white space or indentations on a line is fine。

 But keep in mind that if you are combining it with additional lines。

 Then you will need to give clear indicators of where a new line has occurred。 Next。

 you will explore indentation in Python。I start by clearing my screen and declaring the new variable name with the string value of John。

I want to write an if statement which will return John only if the name variable has a new value of John。

I do this by  tapping if name， double equals John。And then on a new line。

 I input a print statement for name。To make this program work。

 I need to have an indentation before the print statement， which VS code added automatically。

 when I click on Run， I get back John as expected。But what happens when the indentation isn't there if I delete the indentation from my code and then run it again。

 I get the error indentation error expected in indented block。

This tells us that an indentation was not found where it should have been。 Fortunately。

 the error message directs us to the specific line where the issue was detected。

 I could then edit my code and fix it。

![](img/e3b2e85c5994753ffa9ac561347cb64f_3.png)

When writing programs in Python， it's a good habit to read the output whenever you encounter an error。

 as you are often given the specifics of whats went wrong and where it happened， as you noticed here。



![](img/e3b2e85c5994753ffa9ac561347cb64f_5.png)