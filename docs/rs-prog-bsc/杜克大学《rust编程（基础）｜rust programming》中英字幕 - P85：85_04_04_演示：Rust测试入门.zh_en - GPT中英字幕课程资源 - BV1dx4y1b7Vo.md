# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P85：85_04_04_演示：Rust测试入门.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/5792bf113dfdcd9268a9796801cc1b64_0.png)

The most simplest test that you can write is in rust is very straightforward。

 We have here a test directory。 It doesn't have anything in there。

 So let's try to add a simple file here When I say test underscore score simple that R。

 it doesn't have anything in there for writing a test will have to add the attribute for testing and that attribute is this one and that attribute will tell the test runner。

 hey， by the way， I have here a function that we need to test with。 So let's say test simple。

 let's not do anything too complicated here。We are going to do a simple。

A search statement here that will say true。 And then that's fine。

And that's the as simple as you can get。 Now。 We've been using the help of。

V vi see the code and the rust analyzer to run these。 we can if we run it， we。

 we get this test simple。 Okay， what happens if we remove。If we remove that attribute。

 we immediately get that not picked up， but this is not how you know other systems would run it。

 let's see how we would do that with the terminals so I'm going to closely explorer here so we would use cargo and cargo has cargo test it has a lot of different things that we can do and we can actually do several different past different flags to verify that these work works we have to run cargo test now tests that go into these directory are called are usually called integration tests。

 but you can certainly put their unit test as well like there's no actual hard rule。

 but if you do that just to understand that usually by convention people that write rust will call that integration tests even though you can absolutely 100% put unit test in there so。

The way we're going to do this is when I run cargo test。

 dash dash test and when I say test everything here and test simple will be right there。

 so if we say these we change these to false， we should get a false right there and we run that and we get a failure。

Now， because this is the simplest case possible， we're actually not doing anything too complicated here。

 We're just making a plain simple assertion。 Let's again go through some of the components。

 We have a test simple that RRS file inside。 well， this is actually the function。

 and this is the file， and this is the directory。 We have a test directory again。

 Ru developers might call this the integration tests destination the directory will put。

Test that our integration。 This doesn't is not hard rule。

 You can actually put unit tests there as well but convention is integration test and unit test would go inside your library files themselves。

 We will see that later。 Now we have this attribute， which is test。 It we remove it。

 We can run this test。 The way to define a test is by saying function and then test and the test that you want to do and then you make your assertion。

 This is the body of your code。 You can do any kind of setup in there。

 It doesn't necessarily need to be public。 We can actually remove that and toggle the terminal and run that again and we will get that failure because we were saying assert false。

 let's change that to true and save it run this again， it will pass everything so good。 So next。

 we're gonna have the assertion。 This is the trick here。

 and then we're gonna have the thing that we're going to be assert with。

 Now this doesn't necessarily need to be an assertion。 You could very well。

Comment that out and run a print line a macro and saying hello， and then that would still work。

 So if we run that test and when I make these convenient thing。

 we'll still get the okay and well print that hello to the terminal right there。

 So those are the components and that is how you would be adding some tests to a project now we haven't pulled anything into scope。

 we'll see that next。

![](img/5792bf113dfdcd9268a9796801cc1b64_2.png)