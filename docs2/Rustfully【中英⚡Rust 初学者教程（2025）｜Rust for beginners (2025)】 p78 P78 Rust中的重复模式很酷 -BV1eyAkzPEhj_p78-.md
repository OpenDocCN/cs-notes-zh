# Rustfully【中英⚡Rust 初学者教程（2025）｜Rust for beginners (2025)】 p78 P78 Rust中的重复模式很酷 -BV1eyAkzPEhj_p78-

![](img/7a6ba087f1ecf34337436d6a9abe678a_0.png)

How's it going everyone in today's video we're going to continue learning about Declarative macros in rust one of the most powerful features of declarative macros is repetition。

😊，This allows you to match and generate variable amounts of code if you've ever wondered how Vc can take any number of arguments。



![](img/7a6ba087f1ecf34337436d6a9abe678a_2.png)

This is how repetition is what makes macros truly powerful。

 They can generate code that would be tedious or impossible to write by hand。

 Let's look at practical examples you'll actually use starting with the basic repetition syntax Reetition in macros uses special syntax。



![](img/7a6ba087f1ecf34337436d6a9abe678a_4.png)

With the asterisk we will match zero or more times with the plus we will match one or more times and with the question mark。

 we will match zero or one time inside the parentheses。

 you put the pattern to repeat outside you put what to generate for each match Let's start with a practical example。

 a macro that creates a tuple from any number of values and as always I need to place the function under and to use it we would do something like this we would let t1 equal a tuple with these values or we would let T2 equal a tuple with all of these values and now when we run it we should get two tus tu1 and tuple2。



![](img/7a6ba087f1ecf34337436d6a9abe678a_6.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_7.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_8.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_9.png)

Wwhichch were generated through the macro which we created。

 but considering that I didn't explain anything regarding the macro。

 let me quickly explain this syntax。 This part here matches zero or more expressions separated by commas Then we have this part right here which optionally matches a trailing comma and that allows us to add a comma at the end of these tus as you can see when we run this we will end up with the same result and finally we have this section here which generates a tuple with all matched items。

 The asterisk means zero or more So this macro works with any number of arguments。



![](img/7a6ba087f1ecf34337436d6a9abe678a_11.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_12.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_13.png)

Next， let's talk about the repetition operators and the three repetition operators work like this。

 the asterisk， which is considered zero or more， means that the pattern can appear 0，1。

2 or more times Then we have the plus operator。

![](img/7a6ba087f1ecf34337436d6a9abe678a_15.png)

Wwhich is also known as one or more and that tells us that the pattern must appear at least once。

 And finally， we have the question mark， which is0 or1 and that tells us that the pattern must appear at least zero or one time let's see some practical examples of each starting with zero or more which can be empty and this is quite useful for optional parameters and then we can create another macro called min and this works with one or more so this must have at least one item and this is useful for required lists Now to use these we can call log and we can log info and error and say that the application started or that it fail to connect and to use min we would just call min with the numbers Now if we were to run this we would get the log messages and the min of whatever numbers we inserted。



![](img/7a6ba087f1ecf34337436d6a9abe678a_17.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_18.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_19.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_20.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_21.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_22.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_23.png)

Important to note here is that log can work with zero format arguments。 All it needs is a message。

 We don't need to include any format arguments， While min does require at least one value。

 If we were to remove all the values here and try to run the program， it would not compile。

 So use the asterisk when you want to allow zero matches。



![](img/7a6ba087f1ecf34337436d6a9abe678a_25.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_26.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_27.png)

And the plus when you need at least one value next。

 let's talk about separators in repetition patterns， you can specify a separator between items。

 Different separators can create different syntaxes。 For this example， we're going to create a macro。

 which allows us to create sets。

![](img/7a6ba087f1ecf34337436d6a9abe678a_29.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_30.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_31.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_32.png)

And it's going to look like this and what you should notice inside here is that we have two patterns。

 one which checks four commas and one which checks for semicollons。



![](img/7a6ba087f1ecf34337436d6a9abe678a_34.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_35.png)

Both of them create new sets from the data which we provide and because of that we can now use both commas and semicollins to create new sets As you can see when we run this。

 we're going to get two sets from the data that we provided and you can use any token as a separator whether they are comms semicollins arrows。

 the plus symbol or even custom tokens the separator must appear between each repetition in both the pattern and the expansion This allows you to create different syntaxes for the same macro。



![](img/7a6ba087f1ecf34337436d6a9abe678a_37.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_38.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_39.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_40.png)

Up next we have nested repetition。 You can nest repetitions to handle more complex patterns。

 Let's create a macro that creates a 2D array， a， a 2D array also known as a matrix with a clean syntax。

 So here we're going to create a macro called matrix。

 Then to use it we're going to create a matrix from these containers。



![](img/7a6ba087f1ecf34337436d6a9abe678a_42.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_43.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_44.png)

And we're going to print each row。In that matrix， once we run this。

 what we should get as an output is the full wing matrix， so here we have outer repetition。

 which starts here and ends here， which allows us to match multiple rows。



![](img/7a6ba087f1ecf34337436d6a9abe678a_46.png)

![](img/7a6ba087f1ecf34337436d6a9abe678a_47.png)

Then we have the inner repetition which matches the items in each row and finally in the expansion。

 we have a pattern which generates a vector for each row。

 This demonstrates how powerful nested repetition can be You can create complex data structures with clean readable syntax and there still quite a bit to cover on the repetition syntax。

 but I'm going to end the video here for today because I am short on time。

But we'll continue with this repetition syntax in the next video。😊。



![](img/7a6ba087f1ecf34337436d6a9abe678a_49.png)