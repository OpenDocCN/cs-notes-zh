# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P84：84_04_03_演示：组织测试文件.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

Within our project here， we haven't written actual tests and we've had several different things that we've added like dog tests that we've been working with now。



![](img/a2f49f754b4ae6bbc85c058703c2127e_1.png)

To write tests， you might be wondering what is the best， what is the best strategy here。

 And Russ has a couple of different things Here we have a。

Tests directory with a test underscore standard in that Rs file。

 and in there we're going to be adding some tests for some other file now。

This is a thing that you can do。 You can structure your tests in this way。 And actually。

 one thing that I like is to use tree to demonstrate the actual structure versus just using the Expr right here。

 So let me go ahead and do that。 So if I open my terminal here and I do a list。

 you will see that I have tests I have source target and the readme file and other files。

 So if I do three tests， you'll see that I only have a single file。

 So one thing that you can do is as you keep adding more files to to your project。

 you will be adding them to the tests directory。 So why would you want to do that， well。

 anything that is int will not be made part of your final cr when you're building when you're creating these project when you're building it and publishing it you won't be including the tests with them because they are separate theres。

It's a special， it's a special directory that cargo will understand and you will know that some of these files will contain test code and those will not get included。

 but it is not the only place where you may want to see or you may expect to see some tests there are other tests that are available outside of that and those can be within source files so let's see we have a file right here。

 let's try config that RRS。And I'm going scroll the way to the bottom。 So for example。

 we have the LibdRS file here and I'm going to scroll all the way to the bottom and you'll see several different functions in there。

 but we have this mod tests and we have this thing right here in line 43 actually we also had it on test under in on line number three and that is an attribute that lets us tell rust or cargo actually that this is actually a test and it should be automatically discovered and executed。

 So let's go back to Lib thatRS and we have a couple of tests here So what is the deal well the deal is that sometimes you might find a module within within like in this case LibRS that has some tests and the reason why that maybe is because we are going to probably want to get access to certain things that are not publicly available out。

side of the module， so it shouldn't be surprising to see some tests module within within a module and see a few or perhaps many tests in there。

 but I would say that is a good reason to have tests in there。

 but otherwise you will see tests in a top level directory called tests and then the modules or the files the rust files within that test directory so that's roughly what you would need to organize so start organizing your tests as you start building out your project。



![](img/a2f49f754b4ae6bbc85c058703c2127e_3.png)