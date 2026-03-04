# Rustfully【中英⚡Rust 初学者教程（2025）｜Rust for beginners (2025)】 p79 P79 Rust中的重复模式很棒 -BV1eyAkzPEhj_p79-

In the previous video we started learning about repetition patterns in rust so now we're going to continue learning about repetition patterns。

 so let's get started by talking about multiple repetitions in rust you can have multiple repetitions in the same pattern and they must have the same number of matches。

 This is perfect for something like key value pairs So here we're going to create a variable called config which uses the hashmap macro and the key value pairs that we provide。

 then we're going to display the configuration file and when we run this what we should get as an output is that the config holds this data going back up to the macro what you should notice is that both key expression and value expression are both repeated the same number of times The macro system ensures they match up for each key。

 there's a corresponding value。 This is how key value pairs work in macros and it's a very common pattern。



![](img/705964c04e1873f8171b389f3e5fd375_1.png)

![](img/705964c04e1873f8171b389f3e5fd375_2.png)

![](img/705964c04e1873f8171b389f3e5fd375_3.png)

![](img/705964c04e1873f8171b389f3e5fd375_4.png)

![](img/705964c04e1873f8171b389f3e5fd375_5.png)

![](img/705964c04e1873f8171b389f3e5fd375_6.png)

![](img/705964c04e1873f8171b389f3e5fd375_7.png)

![](img/705964c04e1873f8171b389f3e5fd375_8.png)

![](img/705964c04e1873f8171b389f3e5fd375_9.png)

Can just type in time out without providing a value。



![](img/705964c04e1873f8171b389f3e5fd375_11.png)

This will not work。 We need to make sure that we provide both key and value pairs up next we have conditional repetition。



![](img/705964c04e1873f8171b389f3e5fd375_13.png)

Wwhichch can make parts of a repetition optional So for this example we're going to create a macro called call with log and we're going to be using the question mark operator for this which will help us create a macro with optional arguments and to use it we're going to create two dummy functions。

 one called greet and one called add then inside main we can call with log and we can greet Alice or we can print line the result call with log and add one plus2 and this will also work if we have a trailing comma Now if we were to run this what you'll notice is that we will get the log and the original call。



![](img/705964c04e1873f8171b389f3e5fd375_15.png)

![](img/705964c04e1873f8171b389f3e5fd375_16.png)

![](img/705964c04e1873f8171b389f3e5fd375_17.png)

![](img/705964c04e1873f8171b389f3e5fd375_18.png)

![](img/705964c04e1873f8171b389f3e5fd375_19.png)

![](img/705964c04e1873f8171b389f3e5fd375_20.png)

![](img/705964c04e1873f8171b389f3e5fd375_21.png)

![](img/705964c04e1873f8171b389f3e5fd375_22.png)

And the same thing goes for the addition。

![](img/705964c04e1873f8171b389f3e5fd375_24.png)

Going back up to the macro here we have the question mark which makes the trailing comma optional This is a very common pattern in macros to make them more flexible and user friendly。

 it allows users to write code in their preferred style Now sometimes you need to know how many times something will be repeated you can do this by using the repetition itself Let's create a macro that formats a message with a count So here we're going to have a macro called format with count。



![](img/705964c04e1873f8171b389f3e5fd375_26.png)

![](img/705964c04e1873f8171b389f3e5fd375_27.png)

![](img/705964c04e1873f8171b389f3e5fd375_28.png)

And to demonstrate what it does， we're going to go to main。



![](img/705964c04e1873f8171b389f3e5fd375_30.png)

And run the following code。And what it's going to do is turn the items or format the items into a vector。

And count them。

![](img/705964c04e1873f8171b389f3e5fd375_32.png)

This works by generating one statement per repetition to count them。

 each iteration increments the counter， so we end up with the total count。

This is useful when you need to know how many arguments were passed so now that we understand repetition we can create this macro。

 a custom Vec macro and this is the simplified version if there are no arguments which is going to create a new vector otherwise we're going to create a vector from those arguments it's that simple so inside main。



![](img/705964c04e1873f8171b389f3e5fd375_34.png)

![](img/705964c04e1873f8171b389f3e5fd375_35.png)

![](img/705964c04e1873f8171b389f3e5fd375_36.png)

![](img/705964c04e1873f8171b389f3e5fd375_37.png)

We're going to create an empty vector。😊。

![](img/705964c04e1873f8171b389f3e5fd375_39.png)

And we're going to create a regular vector Now when we run this。

 we should end up with an empty vector and one that contains those numbers。

 and this demonstrates the core concept of the vector macro the real vector macro is more optimized It preallocates capacity when possible but this shows how repetition makes it possible to handle any number of arguments。

 You can also use repetition to generate multiple items not just expressions。

 Let's create a macro that generates multiple constants and this macro will be called constants。

 Now to use the constant macro， we're going to just type in constants and define our constants and below that we can use them as normal。

 they have now become constants in our program。

![](img/705964c04e1873f8171b389f3e5fd375_41.png)

![](img/705964c04e1873f8171b389f3e5fd375_42.png)

![](img/705964c04e1873f8171b389f3e5fd375_43.png)

![](img/705964c04e1873f8171b389f3e5fd375_44.png)

![](img/705964c04e1873f8171b389f3e5fd375_45.png)

![](img/705964c04e1873f8171b389f3e5fd375_46.png)

As you can see， we have the max size， the default timeout and the buffer size here we are generating entire constant declarations。

 not just expressions。 This shows that repetition can generate any kind of rust code。

 not just values which is useful for reducing boilerplate when defining many similar items。

 And finally I just want to show you some common repetition patterns you'll see in real code。

 The first one being a list with an optional trailing comma， As you can see here。

 another pattern is key value pairs， which will look something like this。

 as you can see we have a key， we have the arrow and we have the value。

 Then we have alternating patterns， which is like a key value pair but with different syntax。

 Then we have the next pattern。😊。

![](img/705964c04e1873f8171b389f3e5fd375_48.png)

![](img/705964c04e1873f8171b389f3e5fd375_49.png)

![](img/705964c04e1873f8171b389f3e5fd375_50.png)

![](img/705964c04e1873f8171b389f3e5fd375_51.png)

Which is nested with a separator。 And finally， we have one for generating multiple items。

 These patterns cover most use cases。 Once you understand them。

 you can combine and modify them for your specific needs。

 The key is understanding how the repetition syntax maps to the code you want to generate。



![](img/705964c04e1873f8171b389f3e5fd375_53.png)