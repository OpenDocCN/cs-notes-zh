# Rustfully【中英⚡Rust 初学者教程（2025）｜Rust for beginners (2025)】 p76 P76 我喜欢Rust中的声明式宏 -BV1eyAkzPEhj_p76-

Now that we understand what macros are， let's learn how to write them。

 the syntax for declarative macros uses the macro rules macro itself， which is a bit meta。

 but you'll get used to it， the basic structure of a macro looks like this。

we have macro rules followed by the macro name， the pattern to match against and degenerated code。

 but let's start with a simple macro that takes one argument and this macro is going to double a number macro rules declares a new macro double is the name for the macro This part over here is the pattern that matches an expression dollar sign x is known as a meta variable that captures the matched value This part over here is a fragment specifier that says match and expression Then we have the code that gets generated and dollar sign x gets replaced by whatever was matched and to show you how it works we can create a variable called result and that's going to use the double macro and inside will insert a5 then we can print the double of5 and when we run this what we should get as an output is 10 Otherwise we can just remove all。



![](img/4433d454240e5883e6646814476786f5_1.png)

![](img/4433d454240e5883e6646814476786f5_2.png)

This and insert the double of 10 plus5， whatever that might be。And as a result。

 we're going to get 30。 But going back to the example with5， when we call double5。

 the macro system matches 5 against the pattern dollar sign x X or expression。

 It captures5 in the meta variable of x。 Then it generates the code of 5 times 2。

 which means at the end it replaces double with5 times 2。

 and the same thing happens when we do something such as 10 plus 5。 This part over here。

Gets inserted here And in this part over here replaces this bit。 Moving on。

 I want to talk about fragment specifiers。 This part right here is called a fragment specifier。

 It helps the macro system what kind of rust code to expect。

 Now here the most common ones you will encounter。 We have X。

 which matches any expression like5 x plus y or a function。

 We have iddent which matches an identifier like x my function or my struct。

 Then we have Ty also known as thank you。 Not really it actually matches a type like i32 string or a vector which contains U8。

 Then we have path which matches a path like the hash mapap from the standard library。

 We also have a literal， which matches a literal like 42 hello and true。

 then we have block which matches a block of code like x plus y we can also have a statement which matches a statement like x equals5。



![](img/4433d454240e5883e6646814476786f5_4.png)

![](img/4433d454240e5883e6646814476786f5_5.png)

And Pat which matches a pattern like some X or underscore We'll see more of these as we go。

 but expert and iddent are the most commonly used next let's create a macro that uses iddent to create a variable So instead of double we're going to create a macro called createva and this time we're using a meta variableable called name along with iddent Now to use this we can type in Cva my number and when we print my number what we should get as an output is 42 here dollar sign name iddent matches an identifier when we call createva with my number the macro expands to let。



![](img/4433d454240e5883e6646814476786f5_7.png)

![](img/4433d454240e5883e6646814476786f5_8.png)

![](img/4433d454240e5883e6646814476786f5_9.png)

![](img/4433d454240e5883e6646814476786f5_10.png)

![](img/4433d454240e5883e6646814476786f5_11.png)

My number equal 42 this is useful when you want to generate code with specific variable names macros can also have multiple patterns。

 which is useful for handling different cases， let's create a macro that can work with one or two arguments。



![](img/4433d454240e5883e6646814476786f5_13.png)

![](img/4433d454240e5883e6646814476786f5_14.png)

And this macro is going to be called greet。 The first one takes a single name and greets that name。

 The second pattern takes a name and a greeting and then uses both of those in case we want a custom greeting。

 Now to use it， we can type in greet exclamation mark， pass in Alice。



![](img/4433d454240e5883e6646814476786f5_16.png)

Which is my talented scriptwriter。And we're going to greet。Bob。

 who's a great figment of my imagination。

![](img/4433d454240e5883e6646814476786f5_18.png)

And when we run this， what you should notice is that we get Ho Alice as an output and we get the custom greeting as an output。

 When you call greet， the macro system tries to match against each pattern in order。

 The first pattern that matches is used So greet Alice matches the first pattern and greet Bob with good morning matches the second pattern。

 This is quite similar to function overloading in other languages。

 but it happens at compile time with pattern matching but now let's create a macro that's actually useful one that creates a hash map with some initial values。

 This is something you might want to do frequently。😊。



![](img/4433d454240e5883e6646814476786f5_20.png)

![](img/4433d454240e5883e6646814476786f5_21.png)

To get started， we're going to import hashmap from collections。

 then we're going to create our macro rules and call it hashmap。

 Now inside here we're going to have quite a funky pattern and this pattern is going to generate the following code。



![](img/4433d454240e5883e6646814476786f5_23.png)

It's going to create a new hash map and insert the keys and values into the map and then return the map。

 This macro uses repetition， which we will cover in detail in a couple of videos For now just notice that it allows us to create a hash map like this。

 So inside main we're going to create a map and that's going to use the hashm macro and all we need to do is provide keys and values too simple Then we can print the values inside and when we run this。

 we'll get that map at the index of one is equal to one or contains one and that two contains two this is much cleaner than writing let mutable hashmap equal a new hash mapap and inserting each key one by one and again。

 we'll learn how the repetition syntax works in a couple of videos。

 but for now just appreciate how macros can make code more expressive。 Next。

 I want to talk about macro hygiene。

![](img/4433d454240e5883e6646814476786f5_25.png)

![](img/4433d454240e5883e6646814476786f5_26.png)

![](img/4433d454240e5883e6646814476786f5_27.png)

![](img/4433d454240e5883e6646814476786f5_28.png)

![](img/4433d454240e5883e6646814476786f5_29.png)

![](img/4433d454240e5883e6646814476786f5_30.png)

![](img/4433d454240e5883e6646814476786f5_31.png)

![](img/4433d454240e5883e6646814476786f5_32.png)

One important thing to understand about macros is hygiene Ru macros are hygienic。

 which means they won't accidentally capture or conflict with variables from the surrounding code Let's see an example。

So here we're going to create a macro called increment， and all it does is increment a value。

 Now inside main， we can create a variable called X。We can try to increment that variable。

 and then we can print the increment， And what's important to note here is that we're printing both X and the result。

 And now when we run this， what you'll see is that the increment of5 is equal to6。

 X will not be affected by the macro。 Once again， the macro expands to x plus1。

 but it doesn't modify the original x。 This is because macros generate code。 They don't execute。

 The generated code is inserted with the macro was called。 and it follows normal rust scoping rules。

 This is generally a good thing。 it prevents macros from having unexpected side effects。

 but sometimes you might want a macro to create variables that are visible outside the macro。

 which we'll see in later examples and finally， when writing macros。

 there are a few common mistakes to avoid。 The first one being forgetting the semicolon。

 Each pattern needs to end with a semicolon。

![](img/4433d454240e5883e6646814476786f5_34.png)

![](img/4433d454240e5883e6646814476786f5_35.png)

Number two， using a wrong fragment specifier， for example， using Exp when you need iddents。

 number three， not handling all cases， make sure your patterns cover all valid inputs and number four。

 infinite recursion be careful not to create macros that expand forever and personally I recommend starting simple and testing your macros thoroughly macro errors can be confusing so it's better to build up complexity gradually。



![](img/4433d454240e5883e6646814476786f5_37.png)

![](img/4433d454240e5883e6646814476786f5_38.png)