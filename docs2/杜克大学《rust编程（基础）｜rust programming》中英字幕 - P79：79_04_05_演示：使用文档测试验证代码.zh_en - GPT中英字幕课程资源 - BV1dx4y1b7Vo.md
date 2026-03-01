# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P79：79_04_05_演示：使用文档测试验证代码.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/8882cfe5f77d8a26d34fac8ae50bb891_0.png)

We've been adding functions and functionality to other files。

 we've been declaring them on LibarRS we're saying P mod colors and we may be making a lot of changes and we've been documented。

 so this is great。But how do we verify everything's working， We don't have a main function。

 This is not an executable。 We have a LibRS。 How can we try to make sure that we're doing the right thing Well when we start documenting things like these with the triple with the triple back slashes in this way you are essentially creating documentation for for your project。

 but this documentation is also executable do you see this use statement right there that means that that's required to make this example work and we have a thing that you may have noticed that is called run doc test So what is that and how can we make use of that well if I click on it。

We will get output in a close file Exper here and we can say test result okay so what is it actually testing Well it is actually testing the documentation there。

 it's doc test，s it's called Doc test and it's executing the examples that I have right here so remember we were saying UCla U tills colors red was possible because inlib and RRS。

 we have public module colors， What happens if we forget to to do us we'm going to comment that out to simulate that situation。

And now I'm not even able to run the doctors because this is no longer working。

So we don't even get that。 I can say that and file not included in module tree。 So right away。

 this is not going to work。 So let's go ahead， do that。

And if I go to colors then I'll be able to run the do test so that's perfect。

 itifies it verifies that it works。 So if I if this was， for example。

 something like blue and I save that and I run the doc test what is going to have we're going have a failure could not compile the test we have some failures no red in colors so these example wouldn't work so isn't it that nice like we're able to not only document our code。

 but we're able to say。We're able to say， hey， by the way。

 like the documentation has to match correctly。 what we're trying to do。

 Otherwise this is not going to pass the tests。 So that is pretty good。

 what are some the other options that we have。 So we could also have the ability to document the actual model module。

 So if we have more things like say， for example， blue。

 and we do something like these that would be fine。

 but what are some of the things that we could do here。

 We could actually document at the module level， and we could do that with。A double double slash。

And exclamation signs。 I'm gonna to say ancol codes with using terminal output with helper functions and throughout up yeah that looks okay and I'm gonna have the examples and the examples are going to look pretty simple So I'm going say UCite deal colors red and blue and let rest string and blue string that look correct and triple backwards。

 We don't have any panics I'm gonna save that So why would you want to do something like this because at the module level you might want to have some top level examples Now these are silly examples because they're repeating what what I have here。

 but if you had something different that would go there further what are some of the other things that something like this would allow it to do if I go back to lid that rest you can now see that run doc test is there if I don't have this if I'm cut it and save it then I don't have I don't have the ability to。

run the doc test from there。 but if if I do and save it back again， doc test will appear。

 So when I run that you'll see that it runs absolutely everything inside the colors that are as module that allows me to have more confident that as I'm moving things around and I don't have yet my unit test and other types of like integration test I can very easily verify things are working。

 including things that are in the LibRS module in this case。

 I'm running this other one so I'm fairly confident that things are looking correct and that my documentation and examples are also correct。



![](img/8882cfe5f77d8a26d34fac8ae50bb891_2.png)