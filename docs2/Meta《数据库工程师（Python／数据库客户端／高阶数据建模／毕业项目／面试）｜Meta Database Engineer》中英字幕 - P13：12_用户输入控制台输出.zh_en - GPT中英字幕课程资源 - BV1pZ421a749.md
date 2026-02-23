# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P13：12_用户输入控制台输出.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

Like other programming languages， Python focuses on taking inputs from users or other services and providing output。

Python has many helper functions that make it easy to perform both of these actions。

You may recall that you use the print function to output variables and other values。In this video。

 you'll learn more about the print function and how to use another new function called input。

The input function is designed to get data from a source of input。

 and it can be used in different ways。For example， one of its most basic uses is when you use the input function to get data that the user typed in the keyboard。

 this input can then be printed to the screen。In many cases。

 you want to get input directly from a user。For example， when you ask for a user's email address。

 let's say you want to use the input function to prompt the user to enter their email address and then save that input to a variable called email。

If you run this code， the user will be presented with a prompt to enter their email。

The email variable will then contain the email address。Okay， let's switch back to the print function。

 which is used for outputs in Python。It can be used to print all different types of data and it allows for more complex formatting。

The print function itself accepts any number of arguments。For example。

 comm separated to print numbers in sequence， arithmetic to print the output of an equation and string concatenation to join or concatenate two strings together。

Python's print function also has reserved keywords that can be passed as additional arguments。

These include objects that is values that are printed on screen。

 SP which defines how the objects being printed are separated and end。

 which defines what gets printed at the end。There's also a file which specifies where values get printed to。

 and by default it is STD out。And lastly， flush， a boooleing expression to flush the buffer which essentially just moves the data from a temporary storage to the computer's permanent memory storage。

😊，For example， suppose you can pass three parameters to the print function， the word hellello。

 which is a string， the word U， which is another string and CP。

 which is a built in parameter whose value is set to a string containing a comma and a space。

This will be used as a separator between the Ho and U strings， and the output is hello U。

Often while programming， you need to know the value of a variable and output it onto the screen Python allows for direct formatting inside the print statement。

You can also control the order by specifying the numbers inside the curly brackets。For example。

 if you print the same statement twice， but with a number switched， the output will differ。

Let's move on to a more practical application of what you've just learned using some code examples of input and output。



![](img/725bf4ab4524b8d50130d57c3a46be79_1.png)

I'll demonstrate how to use input and output in Python。

 I'll begin by demonstrating the input function。I start by typing input。

Opening parenthesis and closing parenthesis。I then click on the run command and you'll notice that it runs the input function。

 and I'm provided with a console where I can actually type an input so I type hellello there and I press En。

Nothing happens because I'm not actually collecting data， I'm just triggering the input function。

 and by default it'll open up access to the command line or the console and allow me to input data。😊。

I can also add a prompt to the input function， for example。

 I can ask a question to the user such as please enter a number。

 so I type please enter a number in between the parentheses after the word input。

First I clear the console and then I click on run again。

You'll notice that the output now asks me to enter a number。I type five and press enterer。Again。

 nothing shows up from an output perspective， this is because I haven't actually done anything with the input value。

 I'm just demonstrating how the input function works。😊，If I want to get the value of the input。

 I need to assign a variable， so I type in nu equals input， please enter a number。

 I clear my console screen again and I click on the Run button。

It asks me for a number in the console and I enter the number six this time。Now。

 the nu or number value will contain the number six。😡，But in order to see that。

 I have to output that variable to the screen。I can do this by using another function called a print function。

So in this case， I print the number after the input itself by typing print， opening parenthesis。

 the abbreviation nu， and a closing parenthesis。I clear my screen again and click on Run。

This time I typed the number7 when asked to enter a number。

I press enter and you'll notice that the output prints 7 Now I want to show you that you can collect more than one input as part of the input because inputs work in a sequential manner。

So I call this variable nu1， and I enter another variable called nu2 on the next line。

The input for this variable is please enter a second number and I just change the first variables input to please enter a first number so that the instructions are clearer。

I print out the value of nu1 and nu two。The print statement accepts both variables because they are separated by a comma。

And it'll print out each one in that order。😊，Again， I clear my con and I click run。

I type4 as the first number， I press enter and type5 is a second number followed by the enter key again。

 you'll notice four and five are printed out。You can also do arithmetic within the print statement。

In other words， you can do addition， subtraction， standard multiplication and division。

So instead of using commas in the print statement， I typed nu1 plus nu2。

I clear the screen once more and I click Run。I enter the numbers five and4 again， and I get back 54。

😡，Now this isn't exactly what I intended to do and the reason is because both variables are strings。

 this goes back to what you've learned previously with data types。

If I want to do the arithmetic calculation， I'll need to convert each variable into an integer first。

So I can use the integer function on nu one and nu two。

I click on the run button once more and I enter the same two numbers， five and four。

 but now what I get back is nine。If I want to see what type the input is。

 I can check the data type by using the type function。To do this， I type print， opening parenthesis。

 the word type， opening parenthesis， nu one， followed by two closing parentheses。

Let me just clear the screen。I click on run and enter the numbers five and4 again in the console。

 and it says that the class is string and not integer。

 which is the type I actually want to do arithmetic。

So just be mindful when you are using input that you will get a string。

You'll most likely need to use the explicit data type counting to convert it to the data type that you need。

The print statement can also be used for concatetnation。So instead of nu1。

 I change it to STR1 or string1， and I do the same with nu2 by changing it to STR2。

Then I amend the input to read， please enter your first name for string one。

 and please enter your second name for string two。After that。

 I print out Hello and then use concatenations so that the user can be greeted by their first and second name。

😊，Now I want to run this program， I'll just clear the terminal quickly and then I click on run。😊。

In the console， I type Tom for the first name and Jones for the second name。

And the result is the output of Ho Tom Jones， so concatenation can be used with a print statement as well。

Finally， you can also change how you assign variables， you don't have to use concatenation。

 you can just use string replacement。I'm going to use a function within Python called format for this。

😊，Based on the order of the bracket， you can pass in the variables that you want it to be replaced with。

 in this case string1 and 2。Once more， I click Run and I enter the username of Tom Jones andHello Tom Jones gets printed。



![](img/725bf4ab4524b8d50130d57c3a46be79_3.png)

In this video， you've expanded your knowledge by learning about the input and output function in Python。

