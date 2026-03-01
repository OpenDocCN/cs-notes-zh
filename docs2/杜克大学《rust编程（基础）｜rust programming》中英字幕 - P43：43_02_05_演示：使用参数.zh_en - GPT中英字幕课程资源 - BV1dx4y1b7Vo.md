# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P43：43_02_05_演示：使用参数.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/9bf023e9de116e5538e4c16a0a0ef0ac_0.png)

In the many different examples that we've been working with we've seen arguments to functions in this case。

 main doesn't take any arguments that's signaled by the empty par that you can see here。

 but it is dependent on or is actually calling this other function called sum and some has a par and these par right here will essentially require a numbers argument and that has a type so that type is signaled by the colon and then this thing right here in this case it is using the m percent so it's borrowing the value。

And it is actually using a slice of I32 that's the actual type and what is going to return an I32 so it's an integer of 32 bits so it is a way of representing the integer like we have integers and these are 32 bits long so we're being very specific as to what we're going to do and this is going to do is just going to add them all all the items and at the end is going to return the final the final sum。

 the addition of all of the items now this specifics are not that important we want to pass in some numbers now in some other languages like Python you could actually passing any number of arguments if you wanted to and the signature would be very different to something。

but in rust we don't have veryatic arguments that means that all arguments have to be very well definedfin。

 including their types， so one way to have that veryatic argument support with actually not having it supported by rust itself is to use something like what we have here where we are passing many different ones into a data structure in this case we are passing a slice of numbers so that that is one way to deal with that and definitely something that you might want to get used to now you can also use vectors and we haven't quite touched yet on vectors but the ability of passing many different values en capsulate it in a data structure is definitely one way to deal with that and in this case we're definitely complying。

We're passing we're borrowing the slices here and then it's making some computation。

 it's not actually modifying that value which is actually correct and then return the result which is an I32 and then that complies and that is how we can use veryatic arguments in rust without actually without having rust supporting veryatic arguments which means any number of arguments is zero or more which at the end of the day in languages like Python at the end of the day it will translate to having some sort of like a itable where you can in Python I think it's a tuple but here it's essentially the same thing so you have to think a little bit more about what you're passing and ways of supporting it and using a slice is definitely something valid。



![](img/9bf023e9de116e5538e4c16a0a0ef0ac_2.png)