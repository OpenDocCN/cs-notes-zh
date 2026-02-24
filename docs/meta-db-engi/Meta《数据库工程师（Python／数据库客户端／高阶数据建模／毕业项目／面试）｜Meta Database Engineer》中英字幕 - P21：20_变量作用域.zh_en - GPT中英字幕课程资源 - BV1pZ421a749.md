# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P21：20_变量作用域.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

The concept of scoping in Python allows for greater control over elements in your code which reduces the chances of accidental or unwanted changes By the end of this video you'll be able to understand the basics of scoping in Python and identify the four types of scope。

Before you explore scope and its intricacies， it's important to know that Python has different types of scope。

You'll examine each one in detail and I'll demonstrate them with coding examples。😊。

In order of ascending coverage， the four scopes are local， enclo， global and built in。Together。

 they are referred to as L EGB variables within the built in and global scope are accessible from anywhere in the code。

For example， if there's a variable A in the global scope。

 it can be called in code at the local level。😡，The purpose of scope is to protect the variable。

 so it does not get changed by other parts of the code。For instance。

 let's say you've declared variable B in the enclosed scope and variable C locally。

While B can be called in local code， it doesn't work the other way around。😡。



![](img/6ad9791a74d243d21e728d42ff5a0f97_1.png)

As a rule， global S is generally discouraged in applications as it increases the possibility of mistakes in output。

Now I'll explore using the four different types of Python scopes in this practical demonstration。😊。

The first one I want to use is global S I declare a variable called MyG and then give it a value of 10。

So the next thing I do is declare a function and I call it FN1。😊，And inside this function。

 I'll declare another variable， which I'll call local variable or local V and give it a value of5。😊。

To show that my global variable is accessible from anywhere， I can do a print statement。

 say access to global and then print out the value of the MyG variable and if I want to run that function I need to specifically call it so FN1。

😊，Click on run and then the value of 10 is printed out for the global variable。

But if I try and print out the local variable inside FN1 outside the function。

 it will return an error。So I access to local and then put out local underscore V。

I then clear the console， click on run and I get an error saying name error。

 name local underscore V is not defined that's because it's only accessible from within the local scope of the function fN1。

😊，Next， to illustrate an enclosing scope， I'm going to declare a second function inside FN1 called FN2。

I then declare an enclosed variable， which I call enclosed fee and assign it the value of8。😊。

The local V will be local to the FN2 I'll now explain how enclosed scope works。Within FN2。

 I've got access to the enclosed fee， which I can demonstrate by doing another print statement and printing out the enclosed V variable。

😊，I'll just test that this all works by calling the FN1 function and then making sure that I call our FN2 function inside FN1。

 I must physically call a function to make it run。😊，So I clear the console， click on Run。

 and then print out access to Global 10 and access to Enclosure 8。😊。

The way slooping works is that the innermost function has access to almost everything from the outside。

You can access the enclosed variable at this level and then also access the global variable at the outer level。

😊，The same rules still apply from the outside， so if I try and access the variable of enclosed V or try and access the variable of local V。

 I get the same error that the variable enclosed V is not defined The nested items have access to both the global and the enclosed but from the outside it can't be accessed from a nested or an enclosed scope both the local and enclosed。

😊，The last scope is built in scopepe， which you've been using when writing code in Python。

Built in scope refers to what's called the reserve keywords， such as print and death。

Built in scopepe covers all the language of Python。

 which means you can access it from the outermost scopes or the innermost scopes in the function classes。

That's a brief demonstration of S in Python， including examples of global， local。

 enclosed and built in。

![](img/6ad9791a74d243d21e728d42ff5a0f97_3.png)

By completing this video， you've gained a broad understanding of why scoping is important in Python programming。

 and you are now able to identify the four types of scope。😊。

