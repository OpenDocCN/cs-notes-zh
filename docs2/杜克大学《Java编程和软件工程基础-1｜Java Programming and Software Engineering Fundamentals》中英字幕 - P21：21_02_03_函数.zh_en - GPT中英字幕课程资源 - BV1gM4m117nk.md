# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P21：21_02_03_函数.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

Methods combine together multiple potentially complex steps that operate on a specific object。

There's a similar concept which does not work on an object called a function。For example。

 print X is a call to the print function passing in X。 print X will print out whatever x is。

 This is a function as it does not belong to any particular object。

Notice there is no object dot before the word print， but the syntax is otherwise the same。

You can write your own functions， which can be quite useful to avoid duplicating code and to make testing and debugging easier。

 you can write your own methods too， but we are not going to talk about writing classes and methods in this course。

We will， however， discuss them in Java in the later courses。

To see an example of writing your own function， let us take a look at this relatively simple example。

A function that takes a number and squares it。We have defined the function first and then called it later。

Now let's break down the syntax， then see the semantics。First， we have the keyword function。

 which says that we are about to define a new function。Then we have the name of the function。

 as with variables， you can pick most any name you want， but it should be descriptive。 In this case。

 square is a good name， since it describes what the function does。 Squares a number。

Next we have the parameter list and parentheses。 Here we are declaring the names of the parameters。

 these will act like variables， which are initialized by the values passed in when the function is called。

They tell the function what specifically it should do。In this case。

 the parameter says what particular number to square？We decided to call it X。

 if there were multiple parameters， we could separate their names by commas。

Next is the body of the function， this is the code that specifies what the function should do。

The body of the function is always inside of curly braces。

There's a new type of statement in the body of this function， return ANS semicolon。

This is a return statement， which is how a function says what it its answer is。

 The syntax of a return statement is the key word return。

 followed by an expression whose value is what the function should give back as its answer。

Followed by a semicolon。Later in the code， we have a call to this function。

 which is how we make use of it。Here we are squaring4 and using the result of that computation to initialize a variable y。

Now that you have seen the syntax of declaring and calling a function。

 let's step through the behavior。The declaration itself is not executed。

 It just tells the computer what the function means for later use。

So we start here right before the variable declaration。

The first thing that we need to do when we call a function is create a frame for it。

This is a space for the function to have its own parameters and variables， As you will see soon。

 they go away when the function is done。Next， we need to make a box for each parameter that square expects。

In this case， square expects one parameter called x， so we're going to create one box named X。

We will initialize the x parameter with the value 4。

 since that is what was passed into the function call。Next。

 we're going to make a note of where we called square from。

We note it with a one in the top corner of the frame and in the code on top of the call。

This may seem trivial in this example， but if the square function were more complicated and called in many places。

 we might forget where to come back to。Now that the frame is set up。

 we jump into the code for square。Our execution arrow moves into the body right before the first line of code。

Now we begin executing the code here， according to all the normal rules。

We make a box for A and S and initialize it to 4 times 4， which is 16。Now。

 we are right before a return statement。 Return statements are a new concept。

 but they tell the computer to give an answer back from this function。In this case。

 the answer to give back is 16， since we are returning ANS and the value of A&S is 16。

This means that the call to square that we are executing will evaluate to 16。

Now our execution returns to where we made the call， and we finish the assignment statement normally。

Okay， great。 now you know how to call methods and functions。

 as well as the basics of how to write your own function。But why are these so important？Well。

 they are a great example of abstraction。 They package up a computation which may be quite complicated。

 or which may require knowing details that you should not need to be concerned with and give that computation a simple interface。

😊，For example， the interface of the simple image method get with is that you call it on an image and it gives you the image width。

The implementation is hidden in the Duke learn toprogram。com libraries， and you've not seen it all。

 nor do you need to see it to use it。Thank you。😊。