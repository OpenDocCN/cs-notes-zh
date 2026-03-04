# Rustfully【中英⚡Rust 初学者教程（2025）｜Rust for beginners (2025)】 p16 P16 Rust中的控制流 -BV1eyAkzPEhj_p16-

In today's video， we're going to cover if else expressions in rust。 I was going to say Python。

 but we are still in rust。 and if else is one of the most fundamental concepts that you'll see being used in practically every programming language。

 It gives you more control over what your code does because it allows your functionality to run based on certain conditions。

 For example， imagine you want to check the length of a password that the user is creating so you can ensure they are creating a strong enough password to do this。

 we're going to create a validation function， and it's going to be called check length and that's going to take some sort of password。

 which will be a type string slice， and it's going to return to us or it's not going to return to us anything yet。

 We're just going to use print statements here。 And the length of the password is going to equal the password dot length。

 which is a method we can use on strings。 Next， we can add a condition。

 so we can type in if the length is greater than or equal to 10。 Then we want the following。

And here we can print line that the password is long enough。

And that should be a macro plus semicolon else。 and this is what happens if this condition fails。

 we're going to print line， I'm going to copy this section here。

Paste it directly in say password is not long enough。 Please add more characters。 So just like that。

 we were able to add a condition to our code， which would execute this code if this condition evaluate too true Otherwise if it evaluates too false it's going to execute this line of code and it doesn't have to be a single line of code。

 It can actually be several lines of code as long as it's inside the block and what we can do next is check the length of some sort of password such as Bob has a hat 1。

2，3 and we can duplicate that and type in Bob 1，2，3 and now。If we were to run this。

 what we're going to get back is that Bob has a hat 123 is long enough while Bob 1，2。

3 is not long enough， please add more characters So as you can see based on this condition。

 we were able to tell rust which line of code to execute and something else we can do is use the if else expression to evaluate from an expression For example。

 I'm going to remove all of that and remove this function entirely because I want to create a new function called long enough and that's going to return to us a boolean but once again this should take a password as a parameter and here we can type in let length equal password dot length once again and below that we can check whether the length is more than or equal to 10 or greater than or equal to 10 I know some of you guys hate when I say more than or equal to 10 it's just so hard to get rid of that habit。

And if it is greater than or equal to 10， we're going to return true else。

 We're going to return false。And just like that， we're able to return a value based on a condition。

 which means inside our main function， we can do this。 we can check if long enough。

 and here we can pass in a password such as Bobb 1，2，3 and since that returns to us a Boolean。

 we can work with this once again， we can type in print line。



![](img/9572ccb583933d4cecb2170f1ff6a8c0_1.png)

![](img/9572ccb583933d4cecb2170f1ff6a8c0_2.png)

Password is long enough else we will print。That the password。Is too short。

 And now when we run this code， we're going to get that the password is too short because this does not meet the criteria of this condition。

 If we type in Bobb 1，2，3， underscore 56，78，910 that's going to be more than 10 characters and that just means that when we run this。

 the condition is going to pass So the first line is executed or the if block is executed。 Also。

 if you are an experienced programmer， you'll know that this is very silly。

 this isn't something you do in nearly any programming language。

 if you want to return either true or false from a condition。

 you can actually just return the condition directly for example。

 we can remove if and remove all of this and this condition will evaluate to either true if false on its own so we can exclude the if else check I just wanted to show you that it's possible to return a value using the if else block。

 but that's all I wanted to cover in today's video in the next video we will cover。

If which is another pair of keywords that we can use with our if else block。



![](img/9572ccb583933d4cecb2170f1ff6a8c0_4.png)