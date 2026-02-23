# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P64：63_应用TDD.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

In this video， you'll learn about how to apply the test driven development methodology。😊。

In conventional testing， you followed the process of writing code and then writing test cases to ensure the integrity of that code。

In test driven development or TDD， the approach is the other way around。

 and test cases are where you must begin your thinking。😊，The steps involved are as follows。

Write test cases with some functionality in mind， write code in accordance with the test cases ensuring that they pass and reffactor code in case the tests fail。

 Let me demonstrate an example to design a test case that check students enrollment with data stored in a database The test needs to check the integrity of the names entered。

First I'll demonstrate how to design the test case and then write some code。



![](img/76519d432dde9c1af978e83bc0b910d6_1.png)

Let's say I'm checking student enrollmentr for a class exam against a list of names that I already have。

To keep things straightforward， I'm going to use a Python list with the names instead of a database I want to make sure that the names I enter are on the list。

And I also want to ensure data integrity， which means that I must be sure that the names are entered in the correct format。

I've created two files。😊，The first is test underscore Find string， which is my testing file。

And the second fine string is my main file。😊，I already have the pi test package installed。

 and because this is test driven development， I'll write my test function first。

 I begin by importing a curss module that will help me check the A C II characters with a present。

 Then I import the pi test module， as well as the fine string module， which is my main file。

 I define a function named test underscore is present。

 and I add an assert statement to check if the is present function works。

 because I'm going to use it to validate my data entry Con to the conventional approach of writing code。

 I first write test underscore fine string dot Py。 and then I add the test function named test underscore is present。

 In accordance with the test， I create another file named file string dot Py。

 in which I'll write the is present function。😊，I define the function named is present and I pass an argument called person in it。

Then I make a list of names written as values。After that。

 I create a simple if else condition to check if the past argument is present inside the list。

So the function called iss present will check if the name pass is present in the list。

Let me test my code。😡，Note that the test has passed because the name Al is in the list。

 but this doesn't ensure the integrity of entries I may add。 For example。

 I might not want numeric characters in the names。To address this issue。

 I write another function named test underscore No digit I'm going to update some of the code in my main program fine string do PY in accordance with a newly added test。

To do this， I create a function called No digit that matches my test。

 and again I create a simple if else condition。I run the code and you'll note that one of the tests have passed and the other one has failed。

 so the name Al passed because it's on the list of names。

 but the value of N7 didn't pass because it contains a numeric character。

I could also add more test cases and modify my code so that it's suitable for the test cases and I can repeat the cycle until I have no more failed tests congratulations you've now explored a test driven development methodology。



![](img/76519d432dde9c1af978e83bc0b910d6_3.png)