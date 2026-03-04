# Rustfully【中英⚡Rust 初学者教程（2025）｜Rust for beginners (2025)】 p77 P77 深入探索Rust宏 -BV1eyAkzPEhj_p77-

In the last episode， we learned the basics of macro syntax。

 Now let's dive deeper into pattern matching。 Pat matching is the heart of how declarative macros work。

 They match patterns in your code and generate code based on what they find The more patterns you understand the more powerful your macros become Let's look at practical examples that you might actually use in real code。

 Sometimes you want to match a type to create type alias or generic helpers Let's create a macro that generates a result type alias So here we're going to use macro rules as always and the name will be result type This time the identifier is going to equal the result with okay ander or this is the pattern we're going to match against And when that happens we'll generate this code So to use it we're going to type in result type as a macro and create something called my result which will equal a result of I32 and string then we can create a simple function that returns my result And from that point onward we can handle that。



![](img/9ccfa8b60feff587b5bb515d85680373_1.png)

![](img/9ccfa8b60feff587b5bb515d85680373_2.png)

![](img/9ccfa8b60feff587b5bb515d85680373_3.png)

![](img/9ccfa8b60feff587b5bb515d85680373_4.png)

![](img/9ccfa8b60feff587b5bb515d85680373_5.png)

![](img/9ccfa8b60feff587b5bb515d85680373_6.png)

![](img/9ccfa8b60feff587b5bb515d85680373_7.png)

![](img/9ccfa8b60feff587b5bb515d85680373_8.png)

ExampSo here we will match the example if it's okay we'll print success with the value otherwise if there's an error。

 we will print the error with its error message so what's important to note Tia is that OKtyy ander Ty match the types in that this macro creates a type alias for a result type which can make year code more readable when you use the same result type in many places next let's move on to matching literals literals are useful when you want to ensure compile time constants let's create a macro that generates constants from literals so as always we're going to use macro rules and this time the name will be constant from literal and what's important to note Tia is that we're using the literal specifier which ensures we only accept actual literals not variables and this is going to be very useful for creating constants that must be known at compile time then inside here we create a constant with the name。



![](img/9ccfa8b60feff587b5bb515d85680373_10.png)

![](img/9ccfa8b60feff587b5bb515d85680373_11.png)

![](img/9ccfa8b60feff587b5bb515d85680373_12.png)

![](img/9ccfa8b60feff587b5bb515d85680373_13.png)

![](img/9ccfa8b60feff587b5bb515d85680373_14.png)

![](img/9ccfa8b60feff587b5bb515d85680373_15.png)

![](img/9ccfa8b60feff587b5bb515d85680373_16.png)

![](img/9ccfa8b60feff587b5bb515d85680373_17.png)

![](img/9ccfa8b60feff587b5bb515d85680373_18.png)

And we strify it now to use this all we have to do is call the macro with a name of our choice and from that point onward。

 we can use it as a constant as you can see when we run this what we get as an output is the API version and the default port using the Cons next let's talk about matching paths using the path specifier paths are useful when working with modules let's create a macro that helps with importing and using items from paths So here we will create a macro called use and call and this will take a path or we'll match a path and in a real scenario。

 this would use the path but in this example we're just going to print it Next we can use the macro and insert a path such as this one over here that creates a new hashmap or we can also use standard out and now when we run this we're going to see in the console that we're using each。



![](img/9ccfa8b60feff587b5bb515d85680373_20.png)

![](img/9ccfa8b60feff587b5bb515d85680373_21.png)

![](img/9ccfa8b60feff587b5bb515d85680373_22.png)

![](img/9ccfa8b60feff587b5bb515d85680373_23.png)

![](img/9ccfa8b60feff587b5bb515d85680373_24.png)

![](img/9ccfa8b60feff587b5bb515d85680373_25.png)

![](img/9ccfa8b60feff587b5bb515d85680373_26.png)

![](img/9ccfa8b60feff587b5bb515d85680373_27.png)

![](img/9ccfa8b60feff587b5bb515d85680373_28.png)

These the path specifier matches qualified paths This is useful when creating macros that work with different modules or crs。

 though in practice you typically use use statements directly Up next we're going to match blocks blocks are powerful for creating control flow macros Let's create a more useful timing macro that also prints what's being tiedd So in this example we're going to create a benchmark macro。



![](img/9ccfa8b60feff587b5bb515d85680373_30.png)

![](img/9ccfa8b60feff587b5bb515d85680373_31.png)

![](img/9ccfa8b60feff587b5bb515d85680373_32.png)

And this takes the name of the expression and the block Then here we get the start time The result will be how long it took to execute the block and the duration will be the time since start then we will print the time it took to execute that block and return the result Then inside here we can create some functionality which uses the benchmark macro and the name will be calculate sum then inside here the code we will use I this one over here which just adds I to total a lot of times and then at the bottom we can also print the result So right now if we were to run this what we should get as an output is that it took1。

2 milliseconds and at the result is this number over here I tried to read it。

 but I failed So here block block matches a block of code this macro wraps the block with timing code and a label making it easy to benchmark different parts of your code This is a practical use case you might actually end up using Next let's talk about matching state。



![](img/9ccfa8b60feff587b5bb515d85680373_34.png)

![](img/9ccfa8b60feff587b5bb515d85680373_35.png)

![](img/9ccfa8b60feff587b5bb515d85680373_36.png)

![](img/9ccfa8b60feff587b5bb515d85680373_37.png)

![](img/9ccfa8b60feff587b5bb515d85680373_38.png)

![](img/9ccfa8b60feff587b5bb515d85680373_39.png)

![](img/9ccfa8b60feff587b5bb515d85680373_40.png)

![](img/9ccfa8b60feff587b5bb515d85680373_41.png)

Statements are useful for generating code that executes multiple times。

 Let's create a macro that retries a statement。 So here we're going to create a macro called retry。

 the expression will be called max attempts and the statement will just be named statement here we're going to keep track of the attempts and create a loop。

 Then we can insert the statement。 and each time we run it， we're going to add one to the attempts。

 If the attempts is greater than or equal to the max attempts， we're going to break out of this loop。

 Now to use this we're going to create a counter and then inside here we're going to call the retry macro and inside the retry macro we're adding the number of the attempts followed by the statement we want to execute Now when we run this what we should get as an output is attempt1 attempt2 and attempt 3 So as you can see the statement Specifier matches statement this example shows how you might create a retry mechanism though in practice you。



![](img/9ccfa8b60feff587b5bb515d85680373_43.png)

![](img/9ccfa8b60feff587b5bb515d85680373_44.png)

![](img/9ccfa8b60feff587b5bb515d85680373_45.png)

![](img/9ccfa8b60feff587b5bb515d85680373_46.png)

![](img/9ccfa8b60feff587b5bb515d85680373_47.png)

More sophisticated error handlingNext， we're going to talk about combining matches。

 You can combine multiple matches to create powerful macros。

 Let's create a macro that generates astruct with a constructor。



![](img/9ccfa8b60feff587b5bb515d85680373_49.png)

![](img/9ccfa8b60feff587b5bb515d85680373_50.png)

So for this example we're going to create a macro calledstruct with new and what this macro does is create astruct definition along with a new constructor。

 it matches an identifier for thestruct name then a block with field definitions and finally each field has a name and a type。

 this is more useful than just creating the struct， it also generates a convenient constructor。



![](img/9ccfa8b60feff587b5bb515d85680373_52.png)

![](img/9ccfa8b60feff587b5bb515d85680373_53.png)

![](img/9ccfa8b60feff587b5bb515d85680373_54.png)

To show you how it works， we're going to go to main and create a point usingstruct with new then we can create a new point using thatstruct and finally we can print the point and its values and when we run this what we should get as an output is a point with the values of three and4 Next let's take a look at how we can match specific tokens to create custom syntax let's create a macro that provides a cleaner way to create key value pair So here we'll create a macro called Kv which takes a key as an identifier and a value as an expression and what it does is turn that into a key value pair then we're going to create a person named Alice and we're going to let the age equal 30 and to use our macro we just need to call Kv exclamation mark provide an identifier and the value then to see what's inside we can print pair 1 and pair 2 and as soon as we print that we should get back these key values。



![](img/9ccfa8b60feff587b5bb515d85680373_56.png)

![](img/9ccfa8b60feff587b5bb515d85680373_57.png)

![](img/9ccfa8b60feff587b5bb515d85680373_58.png)

![](img/9ccfa8b60feff587b5bb515d85680373_59.png)

![](img/9ccfa8b60feff587b5bb515d85680373_60.png)

![](img/9ccfa8b60feff587b5bb515d85680373_61.png)

![](img/9ccfa8b60feff587b5bb515d85680373_62.png)

![](img/9ccfa8b60feff587b5bb515d85680373_63.png)

![](img/9ccfa8b60feff587b5bb515d85680373_64.png)

![](img/9ccfa8b60feff587b5bb515d85680373_65.png)

So here we're matching the arrow token to create a DSL like syntax for key value pairs。

 The macro automatically converts the identifier to a string which can be useful for configuration or logging and finally as the last part of this video we're going to talk about conditional matching you can create macros that handle different cases flexibly let's create a macro that works with or without a trailing comma which is a common pattern in rust macros So here we create a macro called create array and what this macro is going to do is allow us to create an array with or without a trailing comma As you can see here we have 123 without a trailing comma and we have 4。

56 with a trailing comma and what's cool about this is that both of them work Now I know this looks like a lot of syntax but what's important to note here is that right here we're telling rust with the question mark that this should optionally match a comma This makes the macro more flexible。



![](img/9ccfa8b60feff587b5bb515d85680373_67.png)

![](img/9ccfa8b60feff587b5bb515d85680373_68.png)

![](img/9ccfa8b60feff587b5bb515d85680373_69.png)

![](img/9ccfa8b60feff587b5bb515d85680373_70.png)

![](img/9ccfa8b60feff587b5bb515d85680373_71.png)

![](img/9ccfa8b60feff587b5bb515d85680373_72.png)

And user friendly， it works whether or not there's a trailing comma。

 and this is a very common pattern in rust macros。

![](img/9ccfa8b60feff587b5bb515d85680373_74.png)