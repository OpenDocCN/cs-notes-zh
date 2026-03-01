# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P83：83_04_02_测试介绍.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/c2955579a171a3c77d96aa9400ffabf7_0.png)

Testing is crucial Now you may be thinking well do I really need to do and write tests in rust。

 Is it really necessary， It's a strongly type language。

 I'm already defining very granularly the types that my functions are receiving。

 the types that I'm expecting the types that I'm returning if I'm returning anything at all with my functions in the code that I'm building why do I need to test well it will increase your confidence in a robust best practice when developing any programming language and especially so in a language that like rust that it lends itself so well for testing you should definitely go ahead and feel comfortable with testing defining types。

 defining arguments and return types and values， it's great。But you still need to test the logic。

It is not necessarily okay to test something that doesn't have any logic at all。

 but if you're expecting different behavior on certain situations or a function or a piece of code that should do something in certain when certain conditions are met。

 then that's an excellent example for testing and we'll see how to get started with testing in rust。

 and we'll see how organizing your tests should look like if you need to create a directory called tests or you need to add some files or even if you need to add tests to existing code that doesnt it's already part of your library。

 for example， in in the use case that we' we've defined and we've been trying to solve in the project that were working with so we'll put all of that together and we'll make a work we add some tests and we'll try to make a very。

 very robust library project so that we can build these with confidence。

