# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p100 11_01_03_测试与验证.zh_en -BV11y411z7Dn_p100-

![](img/578360c240b7dbf8a73ea866665b6c2f_0.png)

Testing is one of those things that when I started transitioning from being a system administrator to being a software engineer was some of the concepts that I had to learn very fast。

 Now software engineering， best practices like testing can be applied to a project in in not only like regular projects outside of software engineering。

 but also when you're talking about system configuration and ensuring that your changes are all good。

 these same concepts can be applied everywhere。 So this is again， our sample project called redactor。

 and the specifics of the project don't matter that much because what I want to talk about right now is testing。

 So let me show you here the code that we're gonna be working with this is the actual code that we have here and it's all good but there's a lot of things going on。

 there's memory usage。 Let's keep going， we have。Something that looks like an index that is an endpoint and if you were new。

 if you were just joining a team and you see something like this。

 the first thing that has to go through your mind is how can I make sure that this project that I'm now responsible for is working correctly even if you're not the developer even if you are just in charge of implementing DevOs practices and you need to make sure that you're collaborating with the software engineers and making sure that this works。

 how do you make sure that whatever goes into production is not going break well let me keep scrolling here all the way to end until we go into the functional test So there's different types of testing。

 one of them is functional and when someone talks about functional test it means that you're going to have something that runs the application and the testing will go through many different layers steps or parts of the application usually。

It means the application will run in some way or the other and a test will have to go through several pieces of the application to try to run this test now this is a rust project and is going to make some assertion。

 So let's take at the first test with which is this one I'm going to make this a little bit bigger so that you can take a quick a better look at exactly what is what is going on here。

 so this is a test that will test that the get request to the index method to the to the main to the route of the website。

 which is defined by this one by this piece here that is successful so it configure and creates the service for testing。

 it creates a new application right here and it says hey Im going to send a request to slash or the root of the website I'm I make a get request and is's going to have to。

It has to go to index， so it goes and does the request and says， hey。

 I'm going going to receive plain text and then awaits the response and then he checks that the status is correct。

This is a very basic test and a couple things here is that this test is okay。

 it's kind of simple and simple is fine， but if this fails。

 you might want to have some better context as to why it's failing。

So let's scroll here to the other test which is a post and is' sending things Now this is sending Jason which is implies that there's going to be a post with body and then the response has to be from Alfr Smith and John Do went to the store。

 the response needs to be person one and person2 went to the store so first off。

 this test name is not very good when you say test red post it could be slightly better so we could actually have more burbos names。

 but let me go ahead and show you how this looks I'm going to toggle the terminal and I'm going do cargo run cargo test now we haven't seen cargo we haven't seen test before I'm going to run these so that I can show you how it looks when I run these so you can see that the tests are running and they are all。

But seeing tests that are passing is not necessarily useful because you want to know what happens when it doesn't when it doesn't and things are messed up and things are failing。

 So let's just make these slightly different I'm gonna make a typo right there and'm gonna run this again so that we can take a look at what happens when we're doing cargo tests Allright so we now we get a failure So'm gonna go all the way to the top。

 So in a CCd system which we haven't seen but we' see later on if you are automating this。

 you want to make sure that everything' is running and working correctly。

 you will see in this case we only have three， but you can see you know hundreds of tests if you see a failed you need to understand why that is failing and why is this important and what can we do or the team do in order to make a pass So in this case there's an assertion failed and we have a diff that is telling us that well。

This is this is extra and is missing from this one so the test name is test redact post。

Now you can see that well the name is not very good， so we can make that a little bit better。

 We can say make sure that redact post redact post request is successful in transforming text or something similar。

 It can be it can get very ver don't be afraid of making that slightly more ver so that we can have better a better name here。

 also you can include several descriptions to the test when those fail。 but then again。

 so now we're seeing how these fails。 I'm going to close these。

 I'm going make it go back and and do that so that the tests are actually passing So why is this important。

 Well， you are a Devops engineer， you want to make sure that these applications are working。

 when you see an application that doesn't have tests。

 you want to have some sort of validation to increase the confidence that this will go into production and work and when it doesn't。

To understand why and when you identify that there's something， for example。

 I'll go all the way to the top。 this application has a health endpoint and that doesn't have any tests so if this is failing。

 you better be adding tests or suggesting tests so that you can validate that this is correctly doing things that are going to be important for you when you're launching to production so testing and validation。

Those are going to be essential core parts of your automation of your CICD platform whenever you want to send things to production and you want to make sure that these things are working in this case this is a rust application but these concepts should apply for anything else as well。



![](img/578360c240b7dbf8a73ea866665b6c2f_2.png)