# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P55：55_03_03_演示：理解String与str.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/d771fcae6fa60a0bad969756c7837840_0.png)

Let's see some of the differences between string and string slices in rust， we have a string slice。

 which is this thing right here， which is STR， almost always you will see with an m percent。

 which means it's almost always going to be a pointer to a reference to some existing piece of data that is owned by someone else。

 the difference， one of the difference many differences between that and string is that you cannot mute。

 you cannot mutate， you cannot change， you cannot modify STR or the string slice。

 Sometimes rust programmers will call these a string and this thing a string as well。

But most commonly is most correct to say this is a string slice and this is a string type。

 let's start playing around with a little bit of the differences that we have here and we are creating a string slice here let's take a look at what we have here when we say when we ask a vicious Studio code to tell us what are the types so you'll see here that this is STR and that's effectively how you create a string slice we're passing it here to the point or print underscore STR which will just print it out that that is fine and you see that we're asking for the ampers here we don't need to we don't need to say we don't need to use the ampers here as well because once when we're passing it this is already the right this is the right type so we're passing it。

Works and is fine。 Now， like I said， it is not possible to mutate。

 it's not possible to change these strings。 So there's no， there's no push underscore underscore SDR。

 which allows us to change a string object。 So what are some of the options if you are dealing with a situation like this。

 Well， you can create a new string。You can say like that and you can definitely called S2 string。

 which would convert convert that。 So that's definitely one way to do it。

 so you can say new string over here。 and then that would work。

 and if I run these you will get the hello world over there。 So that is good。

 and then we can actually go ahead and do new string that push underscore SDR and say something like some other string here and the semicolon there。

 but we get this image like underline because we need to make this mutable and then we save it and then it's fine and then we run these well get hello world plus some other string。

 Now that's the ability of making that a string but you can also do a formatting so you can actually create this whole new thing called lead new string。

And say， format。Right and then we can add other stuff to these which will make it a new string actually。

 if we we find a type， we'll see that this is a string and format is providing that to us So if we want to add other stuff here that will also work and then we run it and youll get hello world other stuff here as well definitely a couple of options that you have there when you want to go from a situation where you have an immutable string slices and using the string the string type now that's fine。

 And then we also have the salutation here variable that is passed into print string that that is fine is not mutable by default we can make it mutable we will need to set mute here so this will require putting mutable right there before the yes so there you go。

Diffences you can definitely start manipulating string over here in this function。

 you just have to be careful with the borrowing and the moving concept if you're making some changes and perhaps if you are try to return a string as well depending on what you want to do So there you go those are primarily two differences between the string between string and string slices and another thing to consider is that in general you should use string when you need to create a string that can grow or change over time so if this main function was something as a command line tool used as a command line tool and you have argument parsing as input you will probably want to use string you wouldn't be able to use a string slice because a string slice is known at compilation time and regular string is not So there you go those are a few differences in a couple of things that you can。

You can not do with both these different types。

![](img/d771fcae6fa60a0bad969756c7837840_2.png)