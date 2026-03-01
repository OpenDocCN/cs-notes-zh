# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P28：28_02_07_演示：变量赋值与不可变性.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/5d9400d685ebad2cdd15a59ae0c229b0_0.png)

Let's see how variable assignment works in rust and some of the problems that we may get into when we're running running rust and running the compiler and although we're not looking specifically at a whole section for compiler errors will be running these and going through compiler errors as we move along。

 so we have here a main function we'll always have a main function for these short examples and variable assignment is a very straightforward you use the let word or keyword and then the name of the variable and you pass in here what you want in this case。

 this is a string and we're using the semicolon to indicate that that's the end of the statement and then here we're defining weight 190 now we're letting the compiler infer what types we're using we are not kind of like required to do that so that's fine。

And we have here and I just saved and we have here like a curly red curly underline so something's going on。

 we're able to do expressions in this case we're doing weight divided by 2。

2 that's kilos and then we're printing what that output is now this is also red so what's going on here。

If we run it。round here we'll get some well some compiler errors and we can see that there' is no implementation for integer divided by a float that is why that is the reason why is because a weight is an integer and here we're dividing by a float so that's interesting and where we have to do here is basically well we need to use floats everywhere and the help is already pretty nifty and allowing us to to get some information。

But that's fine and let's hover here and see what we can get cannot divide integer by float It's not implemented。

 The following order types implemented trade by RHS。

 So essentially what we need to do is use one of those so if I do divided by or assign that as a 190。

0 and save that and it goes away and then that's fine and then if I run it it'll probably run it says it finished everything's fine I'm still getting some complaints though well yes I assign kilos and never used it so we can we can actually a little bit more here and let's just use it here say kilos will be that and then that underline goes away if I run it everything works and we are good to go so 190 is almost like 86 kilos 10 190 pounds so there you go that's how you go variable。

Assignment。Now what one thing that I didn't mention is that all of these variables by default are immutable here coming from all languages where mutability is allowed from the get go not so much in rust they are all immutable So what does that mean well if I go to main that are rest here some other one let's see what are some of the things that will happenoo I just saved and all of these things are red so let me run these and this is what we'll get into problem heres cannot assign twice to immutable variable So what's the deal here here we're saying we're assigning we're green a new string and we're naming it name Alfredo Hyde and here we're saying well we want to clear the contents that that clear call means that means that it will clear the contents of the string So I can't because I'm going hover can mutate immutable variable message can borrow message as beautiful。

It's not declared clear I mean all kinds of different errors here So what's what's the deal where well the thing is that message variable we're declaring it by default fault it's immutable so how can we make it mutable if we really really really want to make sure that we want to change it well we'll use the mute or mutable keyword here allow us to say hey by the way this message is fine now we can use clear and no problem so height is now not used first assignment to hide that's fine but its well actually we are using it right here but this is kind of like a warning hey you are using it but you are really fine in a here so what's the deal well the thing is that we are we're assigning the variable twice but you notice that one thing that is different other。

TheNumber we are not using the lead keyword in the second one， so we're using lead here。

 but not here。 The reason why is because once you define the variable ones with lead。

 you dont like if it exists in their current scope， you don't need to use lead again。

So why are we getting a curly underline because again cannot mutate immutable variable height So now we're seeing some of the errors from the compiler right and you can see here cannot assign twice to immutable variable height so two ways that we can do this we can say we can say this height to I mean that's a horrible that's a horrible name but like that it makes everything go away if I run it。

 it runs， but itos me that that's not used now if we really want to change it right if we want to really change it。

 we can say this is mutable， save it run it and now we are able to make it make it work so that is fine and that allow us to give us like a a very good idea like an initial idea actually how to the variables and why they're immutable by default。

 but if we really want to make changes。You can assign the mute keyword。



![](img/5d9400d685ebad2cdd15a59ae0c229b0_2.png)