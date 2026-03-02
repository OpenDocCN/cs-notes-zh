# 哈佛大学《R语言编程入门2024｜CS50R Introduction to Programming with R》中英字幕（豆包翻译 - P7：-7-CS50R - Lecture 6 - Testing Programs.zh_en - GPT中英字幕课程资源 - BV1Vw4m1e75r

![](img/69636fccd899480325fbb2bf55edefaa_0.png)

![](img/69636fccd899480325fbb2bf55edefaa_1.png)

Well hello one and all and welcome back to CSTT's introduction to programming with R。

 My name is Carteranki。 and this is our lecture on testing programs。

 We'll see today all the ways our programs could go wrong。

 learn how to handle these things called errors and see how to test our programs to ensure they behave as we intend。

 So let's jump in and see all the ways a function I've written could go a little bit wrong。

 I have here in our studio a function I've defined called average and this function average is defined in this file called average do R and the purpose of this average function is to take as input a vector of numbers and return to me the single average number it finds across all of those numbers in that vector So notice here how I'm using the builtin functions。

 sum and length and you might know if you're familiar with averages or means that that's defined as taking these sum of numbers you have and dividing by the number of numbers you have。

 So it's exactly what I'm doing here with sum and length。 and let me go ahead and presume that。

I figure that sum and length are correctly implemented。

 I can rely on these functions just as well in my own function， called average。

Now it turns out there is already a function called mean。

 which does this very same thing built into R， it turns to us the mean or the average of some set of numbers。

 but our goal today is to write our own version of that function called average so you can kind of see the design decisions that went into writing a function like mean in R so here is my average function let's go ahead and try it and think about what could go wrong actually so I said before that this function average should take as input a vector of numbers。

😡，But we've seen some ways a user could give us not numbers but text。

 if you're called using readline， you might know that readline by default takes input text and hands us back text。

 so maybe might have forgotten to convert that text to a number I could run average in my console here first defining it up above online one I could run average and let's say I've forgotten to convert some input from the user to a number and I instead have now a vector of characters or character representations of these numbers here。

 So I'll pass has input this vector one2 and three。

 but those's not numbers per se they're actually characters here。

 I'll go ahead and run average and now I'll see this error。

 this is probably not the first time you've seen an error。

 probably when yourre programming you've seen lots and lots of errors。

 but let's get these errors a more formal name So these errors are more formally called exceptions and an exception occurs when something exceptional happens in your program but not in a good way it happens when our program encounter some situation some scenario doesn。

How to handle， and instead， it stops entirely。So the question then becomes。

 how can we handle these exceptions or these errors in our code and one way to do so is hale them more proactively preempt them and do something else instead of encountering this error or this exception So let's see if we could take that approach now in our own function here called average。

 I'll come back now to our studio and let's think through what exactly caused this exception。

 if I look at it here， I'll see that I gave the some function。

 it seems some invalid type character of argument。 So it seems like the problem was in fact that I gave as input to the average function。

 this vector of characters。 So what could I do to check for this before I maybe pass this input down into some and length。

 I could probably use something like a conditional to ask some question but what question would I ask probably could ask is this vector numeric or is it not and maybe I would consider the case where it isn't numeric where I might get an exception handle that case in particular。

So here before I run line3 now trying to sum these numbers and finding their length and dividing therein。

 why don't I go ahead and try to ask the question is let's say this vector x is it not numeric just like this so I'm going to make use of now this function is dot numeric which ask the question returns me true or false。

 is x a vector of numbers or is it not when I use this exclamation point here I'm essentially asking is the vector x not full of numbers and now I have the option here of handling that error before it might happen down here on line 5。

So what could I do to handle this error Well a convention sometimes in the R world is to return a special value。

 one like NA。 so if we give us input to our function average a vector that doesn't include numbers。

 I could say no no， let's stop here and just return NA instead of getting this error ultimately so I'll go ahead and do just that on line3。

 I'll say if we find that this vector X is not full of numbers is not numeric。

 I'll go ahead and return an A instead and hopefully I'll now avoid this error by kind of preempting it and handling it up above。

Letm me go ahead and redefine my average function now to update what it has included here。

 I'll go ahead and run the same thing I did before。

 giving as input to average this vector of characters。

 and I'll see I'll get back now just an A and no error now we've handled it。

 preempted it before it has had the chance to arise in this case。

But if we're going to do something a little unexpected here。

 like return NA when the user might have thought they were getting back a number。

 it's worth thinking about how to alert the user to that fact right now we're handling this error silently if you will。

 meaning we're not going to raise anything to the user we're going to hand them back NA and unless they looked at the return value well they wouldn't know anything in particular was wrong or that they had done anything wrong。

 so it's thinking through how we could alert the user here and let them know what it is exactly we're doing here。

Now one way to do that is to make use of this function built into R called message message allows you to essentially send a message to the console while a function is running。

 so let's see if we could use message here， I'll go back now to my function。

 and maybe before I return an A I could let the user know what it is I'm about to do I could decide to send them a message using the message function and it turns out that as input to this message function。

 I can provide the character string showing the message I want to tell the user。



![](img/69636fccd899480325fbb2bf55edefaa_3.png)

![](img/69636fccd899480325fbb2bf55edefaa_4.png)

WellI want to tell them what it is I'm doing and probably tell them why I'm doing it。

 so first I'll say that maybe this input x here or vector。

 I'll say that xop x here must be a numeric vector so this is the cause of why I'm returning NA and not let's say the actual average and now I could say what I'm doing instead I'm going to return NA instead now if I were to run this function and need to first redefine it。

 go back down my console and provide the same input and now let's see what happens。😡。

I'll see that message。 So now we're not being silent anymore， the user who's run this function。

 they would get back NA as a return value， but now they would know it。

 say they would say x must be a numeric vector vector returning NA instead so we've kind of gone away from being silent and now the user knows exactly what has gone wrong perhaps in this function。

 so a little more intuitive now。😡，But it turns out that by convention。

 message is often used when things are going just smoothly。

 we're trying to tell the user exactly what's going on。

 it kind of tells them a bit of a progress indicator。

 gives them an idea of what their function is doing。

 it's meant to be used in cases where something has not gone wrong。But I'd argue in this case。

 like something has gone wrong。 We gave us input to the average function and input。

 it should not have been given。 So there are ways to take a message and to escalated if you will in severity to let the user know that actually something has gone wrong。

 there might be a potential issue here。 Now， if we were to escalate this message。

 we could instead converted into something called a warning。 Now。

 a warning is good when your function encounter， something is a potential issue。

 It's a bit similar to if you've driven a car and your check engine like pops up whether you're driving that car。

 you'll know that well your car will continue running。

 but you might want to check under the hood and make sure everything is going as you expect it to。

 So a warning tells a user that something has gone wrong that could be a potential issue and think this is more in line what's happened here。

 The user has given us a value that they really shouldn't have given us。

 instead of messaging them warn them and tell them that look you should not have done this。

 you should make sure this is exactly what you want in the end。 as far as the return value。



![](img/69636fccd899480325fbb2bf55edefaa_6.png)

![](img/69636fccd899480325fbb2bf55edefaa_7.png)

So I'll convert message here to a warning instead， just like this。

 and now that means that the user will not get a regular old message。

 they'll get a warning indicating some potential issue。

I'll go ahead and back to line1 and I'll redefine this function。

 and now it will happen if I run it again with that same input。 I'll see I get not a message。

 but a warning message。 In this case， I see warning message in my function and its input here。

 the exact message I typed on line 3 X must be a numeric vector returning NA instead。

 So this is a way of alerting the user that they might get some value they didn't expect because there was a potential issue。

 which is they didn't give us an actual numeric vector。



![](img/69636fccd899480325fbb2bf55edefaa_9.png)

So a warning then is good for some potential issue in your function that could still recover from。

 we could still return NA here。But there is one more level of severity going from a warning to a fullfledged error。

 I think we could here have a discussion of whether a warning or an error is best for this scenario。

 On the one hand， I could argue that this function average is supposed to fundamentally take a vector of numbers and return to me a number。

 If I haven't done that， my function cannot accomplish its goal at all。In that case。

 I might not want to just warn the user and return NA。 I might want to just stop entirely and say。

 look， you've given me an input and I have no idea what to do with it。 I can't handle it at all。

 I'm going to stop my function in its entirety。 So let's see what it would look like if we actually not just warn the user but stop the function entirely。

 Now just so turns out that R has this function called stop that allows us to raise or to throw this error。

 So let's upgrade now our warning to a fullfledged error using stop letting the user know that we simply cannot proceed with the input they have given us。

 I'll go back now to my average function and let me go ahead and use stop much like I used message and warning I'll give it an error message in this case。

 but now what I should do is not return NA。 In fact， if I were to run this code。

 I would never get to line 4 because as stop implies my function will stop on line 3。

 it will not continue， it will not return。

![](img/69636fccd899480325fbb2bf55edefaa_11.png)

urAny kind of value in this case。 Why don't I go ahead and remove line 4 now？

 And now it will happen is this。 We're gonna to ask the question， is this input numeric or is it not。

 if it's not numeric， I will throw or raised this error that the user will now see。

 let me go ahead and run or redefine this average function passes input。

 the same thing we've been doing so far。 And now I'll see well。

 an error and we're kind of back where we started giving an error now， but this one is more precise。

 It's one that we've raised or thrown ourselves and it tells us exactly what has happened and why it has happened here we see error in our function average X。

 the input must be a numeric vector returningops returning NA instead and actually that's probably not true anymore。

 So this stop on line 3 doesn't seem to return us anything， at least not NA now。

 So let's go ahead and go ahead and remove that message here and make sure that the user doesn't anticipate in an NA。

 why don't we just say x must be a numeric vector。 I'll go ahead and redefine it。And now werun it。

 and we should see exactly the error we were hoping to see here。

So we've seen now how to talk to the user and message them about these kinds of fact issues in their functions。

 we've seen message we've seen warning， we've seen stop let me ask now what questions we have about any of these functions so far and how we convey or communicate about these errors that could happen in our functions What's the difference between using message versus print versus CA to display error message So a good question we've seen so far these functions like print and like cat and now this one called message that all seem to show us some text in the console a message is more special kind of text output that we could later on choose to suppress so you've probably seen so far suppress warnings there might also be a function called suppress message you could use to hide those message as they come up there is no such feature though for print or for cat a message more particular and exclusive to showing the user message they could either view or decline to view later on。



![](img/69636fccd899480325fbb2bf55edefaa_13.png)

![](img/69636fccd899480325fbb2bf55edefaa_14.png)

Good question。Okay so let's consider other scenarios here that we could try to address in our function。

 We've considered so far what happens if we don't get the type of input we're expecting in this case。

 a nonnumeric input， but there are other scenarios we should probably consider and anticipate and one of them might be if our input has NAs in it so we've seen that the mean function if it's given some input that has NA。

 well it returns to us NA instead， so if we want our function to do the very same thing。

 maybe we could have a check here， maybe after I check to see if the input is numeric I could ask another question。

I can ask this one here if any， let's say， if any of the values in this x vector are and a。

 just like this。 why don't we go ahead and do something else， before we run now line 8。

 but what is it I should do if any of these numbers R and R NA。 Well， I could of course。

 return NA like we decided do earlier， but now there's a question here。

 I don't want to silently return NA， and I have three options， I could either message the user。

 I could warn them or I could throw an error using stop， Let me actually ask our audience here。

 What would you use， Would you use message or warning or stop in this case。

 how might you try to handle。

![](img/69636fccd899480325fbb2bf55edefaa_16.png)

This particular input I think it because is if something error happened it a good point。

 So we've seen that message is good for just conveying information when there's nothing really wrong going on Where a warning is good dimension mention。

 a potential issue， the user to take a closer look at。 And I'd argue that in this case。

 a warning is probably better。 We're doing something a little unexpected。

 We're returning NA as opposed to in this case， the average user might have been expecting。

 So think a warning would be best here to the user that there might be some potential issue here。

 I'll come back to our studio。 And let's go ahead and actually implement now this warning。

 the same way before with warning here before I return NA I'll give a warning and in this case。

 I'll say as follows that X。

![](img/69636fccd899480325fbb2bf55edefaa_18.png)

Our input now contains one or more NA values just like this。

 So now my function is looking a little bit better at handling these kinds of cases。

 I might not have anticipated first， if we get a nonnumeric input， we're going to go ahead and stop。

 We fundamentally cannot continue with a with a nonnumeric input then we're going ask the question。

 if any of the values in our vector x R NA， we're gonna to warn the user and tell them that x contains one or more NA values。

 they might not know that yet and we're going to ourselves return NA by convention here。

 if though none of these conditions are true， we're going go down to the bottom here and we're going to return the average just as we would otherwise So go ahead and run this definition for the average function。

 I'll go ahead and give it， let's say some faulty input like we saw before。

 I'll get the error like we see why don't I try not giving it an input with some NAs。

 I'll give it one the number to the。And 3 and A， let's see。

Now I get NA back and this warning message down below。

 well let's try a normal input average and I'll give it one，2， and3。

 all numbers here we'll see the average of those numbers two so I think our function now is much better designed We're able to handle these edge cases that the user might have given us and now it can alert them to exactly what we're going to do to handle those cases。

Now， when we come back， we'll see how to actually test this program， this function in particular。

 and make her behaving like we intend， we'll come back in five and see how to test programs like these。

Well， we're back and we've seen so far how to preempt a few potential errors and functions we've written。

 What's next is actually test our code to make sure it behaves as we intend and we'll do so by writing what we'll call unit test Now a unit test is some code that we write ourselves to test some unit of our program but what are those units we'll function programs are composed of individual units called functions So unit tests now our code we can write to test individual functions inside of our programs and we'll go ahead and write some unit tests of our own by now testing our average function So let's go ahead and do just that I'll go back to our studio and I will by convention to test this function average create a new file called test average R So I will do go ahead down here and I'll say I want to create a new file called test average R and I'll see that file was created for me if I now go to my file Expr over here I can。

Open up test average and I'll see a blank page in which I can write my tests for this average function Well again。

 by convention， what I'll do is write a function to test this code that I've written now in average R in particular this function average I can call it test underscore average just like this and I'll make sure it is a function doesn't take any inputs for now。

 but within this test here that I've written this function I can use to test my code I'll then provide one or more test cases Now a test case is some representative scenario our function might encounter and we want to ask the question did our function return the right value for this particular scenario。

So if I want to ask a question， like I could do that using a conditional as we've seen。

 so maybe I'll ask the question here， if let's say average and they call our function and give it as input。

 this vector we saw earlier，1，2 and3 all numbers if the return value of average given this input is equal to2。

 well what should I say I could probably say in this case that average my function average past the test。

 and I'll go to a smiley face is for fun here。Otherwise， though， if I don't get that value back。

 what should I show to the user to myself here， the programmer I could probably say something like well。

 average failed the test and give me a little sad face to make sure I know what's going on So this is my first test for this function average notice how I've defined one test case my test case is when I give average the input1。

2 and3 as a list I then expect that I'll get back the value2 and if I do I'll the average past the test if not I'll go ahead and say we failed the test and now for cleanliness here。

 let me go ahead and say backlash end at a new line to each of these messages here and why don't we go ahead and try to run this test average function before we do so we probably want to know a few things one is I've only defined the test average function here I've defined it as having this test case here but if I want to run it。

 I should still call this function probably down at the bottom of my file down here I'll say let's run。

Test average。And one thing you might notice you're being particularly observant here is that I'm calling the average function。

 but at least within this file here， test average。 R， well I don't see average defined。

 well what we don't want to do is this， I don't want to go over to average。 R。

 copy and paste this and put it over and test average。R。

 what I can do more simply is run source within this file， I could say source。

 and then the name of the file I want to run before I run the rest of the code now in this program here。



![](img/69636fccd899480325fbb2bf55edefaa_20.png)

![](img/69636fccd899480325fbb2bf55edefaa_21.png)

![](img/69636fccd899480325fbb2bf55edefaa_22.png)

I'm going to run now the code in average。 R， which will give me access to this average function and I can then later on call it in this file so we're kind of if you will importing this function into this file here。

 we're not able to use any function we've defined in average。 R in this new file， test average。

 R because we've sourced it， we run it before we run any code in this file here。



![](img/69636fccd899480325fbb2bf55edefaa_24.png)

So I think this is all we'll need to test our average function。

 Why don't I go ahead and run this test here。 I'll go ahead and click on source to run this file now and we'll see。

Average past the test。 So it seems like in this case， if I give my average function the input 1。

2 and3， it will return to me the value2。 Well what are some other test cases we could think of like ideally we think through some representative cases that we should know how to handle。

 but also ones that kind of cover a broad range of scenarios here I've been testing positive numbers but it would be worthwhile to test if average can work with negative numbers2。

 so let's add a new test case I might just kind of copy and paste this for now。

 I'll take my test case here and add a new one down below and why don't I change now the input to the average function。

 I'll give it now some negative numbers， more representative examples here， negative one。

 negative2 negative 2 and negative3 and what should I get back Well。

 negative two is the average of negative  one， negative2 and negative 3 that's what I should expect。

Here I've tested it now， both positive and negative numbers。

But it's probably worth testing0 to which is neither positive nor negative。

 I'm trying to think of scenarios that might go beyond the usual cases but are still important for me to be able to handle appropriately so why don't now make a new test case。

 one that involves zero I'll go down here and add a new one maybe I'll do a negative one and a zero to use that number and then one so now we're going between negative and positive and neither negative or positive and the average here should be well zero。

So here I have three test cases in this one test function first I'll test positive numbers。

 then I'll test negative numbers， then I'll test positive。

 negative and neither positive nor negative numbers hoping for the right output in each case I'll still run my test average function down below let me clear my console click on source and now I'll see average seems to have passed all three tests so my code seems to doing pretty well here but if we wanted to keep going and adding more test cases to this。

 I'd argue that we get pretty bored pretty quickly and it would be a。

 a lot of copy paste like I've already written here 21 lines of code to test off function that was 10 lines of code and if we wanted to test our programs and every time had to write three4 times an hour of code to test that function well nobody would test their code we want to test their code so thankfully people who are in the R community have develop。

Their own package to allow us to make testing easier and arguably more fun。

 So a package that is canonical in the our community to test your programs is called test that。

 It allows you to test that your function behaves as you might expect so let's go ahead and use test that now to improve the design of our test make it easier to write test cases like these now test that comes with a function called test underscore that which allows me to make a new test for my code but before I can use it I of course need to install test that so if you haven't already let me go down to your console down here and say install packages and install test that once you've installed it you then need to load it so Ill go ahead and load test that just like this by doing library followed by test that now I'll go ahead and enter here and I'll see that I've now loaded test that and I have access to functions like test underscore。

😊。

![](img/69636fccd899480325fbb2bf55edefaa_26.png)

![](img/69636fccd899480325fbb2bf55edefaa_27.png)

So I think what I've written here so far， I mean is' pretty good。

 it at least has some good test cases， but I don't need any of this to use test that anymore。

 I'm going to go ahead and delete most of it， but still include now my average。 R import。

 if you will， I'm taking whatever I've written averaget R and it able to making myself able to use it now in test average。

 R。

![](img/69636fccd899480325fbb2bf55edefaa_29.png)

![](img/69636fccd899480325fbb2bf55edefaa_30.png)

![](img/69636fccd899480325fbb2bf55edefaa_31.png)

Now we said before that test that comes with a function called test underscore that and we use this function to define a new test for some function that we have so I'll go ahead and go back to test average R and I'll go ahead and use test underscore that and the first input to test that is a description of the test I want to run so here I'll say I want to test that I want to test that that average let's say the average function here calculates the mean or in this case the average of these numbers。

 so this is kind of an English sentence now I'm going to test that average calculates mean。



![](img/69636fccd899480325fbb2bf55edefaa_33.png)

Well， the next argument is the set of test cases I want to run to ensure that test or to ensure that average calculates the mean appropriately。

By convention， I'll put these test cases inside of these curly braces as a second argument now。

 and I can now provide several test cases inside of this one function that I've decided to create here。

Now how could I say or express a test case Well test that comes with some functions we can use and we really use them by expecting or saying what we expect to happen when our function returns as some value one of these functions here is expect equal we could expect that when our function is run。

 we should get back a return value that is equal to some other value。

 much like we just did with our conditionals earlier but now I'll use expect equal letm me go back now to my code and inside of my test here I'll go ahead and define a few test cases。

 the first one will be I want to expect equality between the return value of the average function when given one to and three as input and this value2 on the right hand side。



![](img/69636fccd899480325fbb2bf55edefaa_35.png)

![](img/69636fccd899480325fbb2bf55edefaa_36.png)

So to be clear here， the first input to expect equal is the argument the value will get back from in this case our average function。

 and the next argument is the value we expect to find as the return value of average I'm going to expect those are now equal and this is our test case there no conditionals not nothing else。

 we're going to go ahead and just use this to test， did average return to us2。

 when we gave it as input a vector of1，2 and3。😊，Well， let's not add our other test cases。

 I could copy paste this and change the input， I'll do negative 1， negative2。

 and negative 3 to test now for negative values。The expected value is negative2 now。

I'll do the same now， but for negative 1，0 and1 the expected value now is going to be0 and why don't we go ahead and just add some more test cases now it's just so easy for us one thing I could do is test maybe more than an odd number of numbers like I've always been testinging three here maybe I'll test four as another scenario I'll go ahead and do let's say negative to negative one1 and2 so now we test both positive and negative numbers but now we are giving an even number of numbers as input and we should get back of course0 in the end。

So this then is our test of our average function let's go ahead and see what could happen here notice how at top of our studio I now see a button called run tests。

 this means we're going to run every test we see in this file I could alternatively go down to the bottom of my console and just source this file to run it I could say source test average R and let's see what kind of output we get go ahead and run this and test pass little gold metal here to say our function worked as we intended it to here I can see that average war turn to me all these values for each of these test cases making it much easier now to write test cases like these thanks to test that。



![](img/69636fccd899480325fbb2bf55edefaa_38.png)

Let me ask now what questions do we have on defining these test cases and using a package like test that we have a source because if now use file we only want to test one function1 would be like a good ideaed source that a good question so notice here how I actually ran source test。

 R because my goal was to run these tests here top to bottom test average。

 R already sources or runs if you will average R giving me access to any functions inside of that file here when we come back another time next lecture。

 we'll see how to make packages of our code and we'll see how to write test that don't require us to put source up top put so long as we're not running packages and just testing our code we're going to need to include source average R up top to give us access to average so we can run it inside this test file here。

What other questions do we have on test that or testing our code so far When is an appropriate time to write tests Yeah。

 when is it appropriate to write tests and what time is appropriate to write test So there are so I just say many varying philosophies on this there is a kind of a movement or philosophy called test drivenrin development which argues you should write tests before you even write your code and by writing your tests you kind of get your mind around what you want your code to do and then you write code to pass those tests On the other hand folks might say well I just want to get something done I'll write the code and then I'll test it。

 there's arguments on both sides to be made it's going be up to you and your team to decide when you want to test and how you want to test This is telling us how we could test now using packages like test that but good question on when to test as well。



![](img/69636fccd899480325fbb2bf55edefaa_40.png)

Okay so here we've written a pretty good test case or many test cases here for average function。

 but there are still other scenarios to test in particular。

 we saw what could happen if we gave average some input that included NA values we could just as well test the result of average when it's given some NA values as we could some regular values like these so let's go back now and add some new tests and test cases to our file here Now if I want to test what average does when it's given some input includes NA values。

 well I could keep adding test cases here to my single function or if my single test。

 average calculates mean but if I were to keep going and adding more and more tests like this function will become quite quite long So ideally what I want to do instead is maybe divide up my test my test cases iny that makes logical sense here。

 I argue I'm going to have all my test cases that are giving。



![](img/69636fccd899480325fbb2bf55edefaa_42.png)

Some pretty typical inputs， numbers， going to find the average of them and get it back and check for equality。

But if I'm going to give average some new type of input like inputs that include NAs。

 well maybe I should make a new test for that and I can do that by including more than one instance of this test that function。

 I could say I want to test that now， average average， let's say means everyone word this。

 I want to say test that average warrantns about NAs in input so we saw before that our goal when we wrote the average function was to test and to make sure that it gave us a warning when the input X included NA values。

 so we could write some test cases to make sure that that is what is happening with our average function。

So here's my description of this test， I'll go ahead and give myself some space now for test cases。

Well I want to test that average raises or throws a warning here and it seems like expecting equality might not work because this me just test two distinct values but a warning is something else entirely well thankfully in test that we have access to other expectations we can say one including test warning or expect warning in this case。

 we can say we want to expect a warning from this function or expect no warning at all so let me go over here and say I want to expect that I'll get a warning from the average function when I give it some input like this。

 maybe one NA and3 so some input involves an NA。

![](img/69636fccd899480325fbb2bf55edefaa_44.png)

![](img/69636fccd899480325fbb2bf55edefaa_45.png)

I could do the same thing down below and I could say why don't I give it maybe all NAs here。

 a vector of three nas and now I could expect that when I run average in this way。

 well I expect I'll get a warning so let's go ahead and rerun our tests now testing for both a calculation of a mean and a warning from average let me go ahead and run this and what do we see。

😊，Test failed， so let's see what happened here if I scroll back up， I'll see that one test passed。

 that seems to be my first one here， average still seems to calculate the mean。

 but if I look down below my next test is that average warns about NAs in the input and in fact。

 what I've gotten it seems from average is not a warning but an error。

 error in average when I gave it NA NA NA x must be a numeric vector。

So although I expected a warning on line 12， it seems like I got an error instead。

 so that's probably caused for me to go back to my code and see what could happen so I could fix it and make sure it adheres to these expectations of my function Let me come back now to average R and think through what could be going wrong here Well we got it seems this error that X must be a numeric factor when we want。

 it seems this warning down below。So maybe what happened is that when I gave it a vector of all NAs。

 maybe it found that that vector is not numeric， which it might well have done。

 so go at my console here and test this， I could say is dot numeric and give as input NA NA NA and ask。

 is that numeric or not？HSo it's not， so because this vector of Ns is not numeric。

 I would first throw my error that x must be a numeric vector。

But what I really want to do is return NA if I get a vector of Ns。

 so I think' probably reorder here this handling of my errors。

 let me go ahead and reorder this and put this up top first。

So now what we'll do is first check is an or is the vector is the vector got is input put to average here。

 does it include NA values， If so we'll raise a warning and return NA and then we'll check if it's numeric。

 I think this might help us solve our problem here。 let me go back to test average。 R。

 let me rerun these tests with our updated version of average。 R and we'll see。All the tests pass。

 we have a little confetti， some rainbows we seem to be moving along pretty well so what questions do we have on this new version of our test we've expected how average calculate the mean and' look looks if we get a warning now。

 what should we do next and what questions do we have before we move on？😊。



![](img/69636fccd899480325fbb2bf55edefaa_47.png)

When you user get a warning can we use best to user input warning So I'm hearing a question about handling these errors or warnings as they come up in our code and it turns out that R actually has a function called try and a function called try catch let us handle errors and warnings as they arise in our code we won't focus on those today but certainly even more about them if you're curious about them too let's keep going here and see what else we should test so I argue that we've tested that average returns us the right value to calculate the mean that it also warns about NAs in input but what else could we test well it seems like we should also test that average actually returns to us if we give it an NA value here we're only expecting a warning and we're not so much testing if we're getting back the right return value So let me do just that I'll go ahead and add a new test case when that tests that average returns and。



![](img/69636fccd899480325fbb2bf55edefaa_49.png)

I'll test that here， average returns NA with。Ns in our input just like this。

 and I'll go ahead and add some more test cases。 Well here it seems like expect equal might work for me。

 I'm going to test that the return value of average will be equal to an NA value。

 so I'll go ahead and expect equal。 I'll go ahead and give the same kind of input I gave down below here。

 One NA and3， I'll expect that to be equal now to NA and let me go down over here and say I expect equal between this vector of just all NA values and the NA value itself。

 Let me go ahead and actually make this a vector。It like that and make this a vector as well。

 and now we' be passing into average those same inputs down below。

 but now I'm testing to see if the return value is an A。

 I'll go back to my console now and run these tests that I've just added and we'll see。😊。



![](img/69636fccd899480325fbb2bf55edefaa_51.png)

Something a little bit curious， I'll see test passed。And I'll see test past， but I'll see a warning。

 it seems in my second test that average returns NA with NA as an input。

 and I get back a warning that x contains one or more NA values。Hm。Well。

 that is kind of expected because if we look at at our average function。

 we'll see that if we do give our function NA values， we're going to throw this warning。

 but what we're testing in this test is not so much that we get a warning or not。

 we already did that down below we're testing if the return value is equal to NA so this would be a good chance for us to use a function like suppress warnings。

 we're saying we don't really care about the warning we get。

 we want to test the return value in this case， so I'll wrap the average function in this case。

Inside of suppress warning， suppress warning。Suppressed warning， sorry。

 let me make it plural up above。And now I think we should probably solve our problem here。

 I'll go ahead and rerun these tests and now we'll see I have three tests passing overall。

 Well what else could we test， we saw before in average R that we also want to stop。

 we want to end our function。 throw an error if we give it some nonnumeric input。

 We could just as well test for that。 I have this other set of functions。

 thanks to test that one's called expect error and expect no error。

 those test if my function has stopped given some given input。 so I could use now expect error。

 we come back to test average and go down below and say I'll test that， maybe average。



![](img/69636fccd899480325fbb2bf55edefaa_53.png)

![](img/69636fccd899480325fbb2bf55edefaa_54.png)

Stops if X our input is nonnumeric just like this， and now I'll go ahead and expect that I'll get back some error if I give as input to the average function。

 some value that is not numeric， maybe something like something like quack just like this or something like that test we saw before one as a character two as a character and3 as a character so this is nonnumeric input let's see if we get back the error from average。

 I'll go ahead and run or first say my file I'll then run test average and now I'll see four test passing2 so here we've seen how to write test cases for our code thanks to expect warning。

 expect equal and expect error。

![](img/69636fccd899480325fbb2bf55edefaa_56.png)

What other questions do we have on testing our code using these kinds of test cases and test that more generally one thing which comes up very much in computer science is floating point inaccuracies right so can we account for that。



![](img/69636fccd899480325fbb2bf55edefaa_58.png)

A really good question actually an excellent segue what I' was just going talk about now so it seems like in our code we are testing integer numbers like I have here one。

2 and3 and we get back a whole number like two same for these other test cases。

 but to your point we've missed an important kind of test case which involves these floating point or decimal numbers and due to what you've said about decimal numbers and whether theyre presented。

 there are special considerations we take into account before we can test those kinds of numbers so let's see what we should take into account before we test in this case。

 floating point or decimal values， so let's actually go ahead over here and think through how we could test it at least hypothetically I could use here。

 expect equal still and give now as input the average function but I'll give it some floating point values maybe in this case I will try to test these 0。

1 and 0。5 taking the average of this which will be 0。3。

Now it seems to us as humans that if we were to do this kind of calculation。

 we would get the following kind of answer that 0。1 plus 0。5 divided by2 is equal to exactly 0。3。

 this is the average of these numbers， 0。1 and 0。5。

But it turns out that computers can't do math exactly like this。

 that there are actually an infinite number of floating point numbers of decimal numbers and only a finite number of bits we can use to represent them。

 which leads to this problem known as floating point imprecision We have so many decim1 of us represent and only so few bits represent them that we can't represent all of them precisely and in fact。

 a computer， even one running R might perform that same calculation and arrive at this 0。1 plus 0。

5 divided by 2 is equal to 0。299999 lots of nines then。A lot of other values after that。

 So not exactly 0。3。 And so because of this， we need to allow for some tolerance when we test our floating point values。

 but before we do that let let me kind of prove to you this is happening in R even I'll come back to my computer here and let's get an idea of this imprecision that happens in floating point values。

 Let go back down to my console here。 And if I were to print， let's say this value， 0。3。

 I'll get back 0。3。But if I push R just a little bit and I ask it what really is 0。3。

 I could say print 0。3 and show me now 17 digits after the decimal point， let's see what we get。H0。

2999999999 so it turns out that 0。3 is just one of those decal numbers we can't properly represent due to having so many floating point values and so few bits to represent them。

Now because of this reality， like we said， we didn need to allow for something called tolerance and we're testing code like this。

 Now tolerance is the range of values I will accept above or below my expected value as being equal to that expected value mathematicalmaticly we could say this maybe my expected value is 0。

3 but in terms of number law it comes being equal to 0。3 I'll say any number between this range here。

 plus or minus let's say1 times 10 to the negative8 some small number here Now this number is our tolerance and we can change if we wanted to2 depending on our needs for precision or how're representing these numbers here then come back now to our studio and show you that expect equal actually as a parameter called tolerance we could use to change this value here I'll come back over and let's look now at expect equal if I clear my console and go here and say in this particular test I want to set some tolerance here I could say as another parameter。



![](img/69636fccd899480325fbb2bf55edefaa_60.png)

lerance and of equal to some small value， let's say1 times 10 to negative 8。

 which I represent now is with 1 e negative8 here。Now it turns out that test that gives you some default tolerance it's already been decided。

 so I'm actually going to rely on them to choose my tolerance for me here。

 but you could if you wanted to override it with this parameter called tolerance。

So we've seen now this idea of floating point imp precision and this idea of tolerance which we can use to better test our floating point values inside of our tests let me ask now what questions we have on either of these topics here while you' writing code spending much time to test another code well you can go to the code that you wrote and just test it simply a really good questions maybe in the habit of kind of just testing your code in the console for instance kind like I did earlier to come back over here maybe I wrote the average function and I decided you know I'm pretty confident this' will work assign it to be the average here and I'll just run a few test cases like average know C1。

2，3 here okay that seems to work maybe I'll do average and then maybe C negative one negative2 negative3 that seems to work as well now the reason you might not do this and instead spend more time to write your own tests is simply just robustness of your tests notice I can very quickly test for a lot of different scenarios in my tests here and make sure that my。



![](img/69636fccd899480325fbb2bf55edefaa_62.png)

Works as it expects。It's also very useful if you're collaborating with others。

 let's say you're both somebody else and you are both writing the average function。

 well you could collectively decide on what tests you will run to make sure that the average function is correct and if somebody later were to go into the average function and make a change that it could test to make sure that their change did not break the code altogether。

 so this is a good way to standardize what it means for your code to be correct as well but a good question on why would even spend time writing tests like these。

😡，Okay， so I think we've so far seen a lot of good tests for our code now， when we come back。

 we'll see how to test not just numbers like we did here， but also strings as well。

 and focus on these two philosophies， one called test driven development and one called behavior driven development。

 we'll see you all in a few。

![](img/69636fccd899480325fbb2bf55edefaa_64.png)

Well， we're back and so we're going to next focus on testing these return values that will be strings as well as focus on a few philosophies of testing。

 namely test driven development and behavior driven development Now what is test driven development Well it is an answer to when and how we should write our test and central to this philosophy is that test should be at the heart of your development process In fact it even argues you should probably be writing tests before you write the code Now let's consider here I want to write a function that says hello to a user one like greet well to make that happen I should probably first write the tests for that code and then write the code itself let's do just that now over in our studio come back over here and create a file that will test this function called theG that doesn't yet exist I'll do file do create and then I'll say I want to create this file called testG R and I'll say it was create。

I'll go ahead and go to my file Exper and open up testgreet。or。

 and now I could start finding some tests to test this code that doesn't even exist yet。



![](img/69636fccd899480325fbb2bf55edefaa_66.png)

Why would I do that Well by writing tests， I make it much clearer to me and others what it is I want this code to do and once I have in mind what I want the code to do。

 I'm better able to write that code itself。😡，So the very first thing I probably want to test here is what that test。

 the greet function that it can say， let's say， hello。

To a user just like this that's the core part of this greet function I'm going to write that it says hello to a user and now I could define some test cases to make sure that this is the reality。

 why don't I go ahead and define at least one and I'll say I'm going to expect that if I were to run greet and give it as input Carter。

 I would get back as the return value now hellello comma space Carter。

So here is my very first test and test case for this function greet that doesn't yet exist。

 I'm going to say that I want to be able to use greet in a way that it passes in a user's name and returns to me then the user's name。

 but with a prefix of hellello comma space。So that is our very first test。

 let me go ahead and make sure I include this eventual file that I will create calledG。

R in which I'll defineG itself。And once I've done this， well I could probably start developing。

 let me go ahead and now go back to my file Explorer and I could either create a new file ahead this plus button here or I could go ahead and do file。

Create， I'll use greet。R， not hello。 R and then I'll go ahead and go to file Explorer here and open up greet。

 this blank canvas for me here and now I could define my greet function to do exactly what I see it should do in my test。

😊，Well， I'll say I have this function here called greette and I'll define it as a function that takes some input maybe in this case the input is called2 because we're going to say hello to someone in this case。

 I'll go ahead and say that this function should return some value and we've seen this function called paste before that concatenate strings。

 bet that's what we might need here I'll use paste just like this and I'll paste together。

 hello comma and then whatever value is supplied as input to this function under the argument or parameter2。

And notice how pacee here well take care of the space between the comma and who we're saying hello to。

So now thanks to my test， I have a very clear idea of what this code should do。

 And if I were to run this now， testgre。 R， we'll see that the test pass so it seems like now greet is working for me。

 I could go ahead and add more test cases。 In fact this is an iterative process。

 I might write some tests， write some code， write some tests。

 write some code here now I could test other names， maybe you'll say expect equal。

 all greet Mario and hope to see hello Mario， I'll do maybe peakach as well and hello to peach。

 I'm just choosing some representative names I might get now and pass into this greet function。

 let's do Bowser as well。So now with these expanded test cases。

 I'll go ahead and test my code again and I'll see that it still seems to be working。

 and now if I were to modifyG in myGet。R file， I could very quickly test。

 make sure I didn't break it with any changes that I had made。

So this is one philosophy of development， test driven development。

 but there is a related philosophy that is still interesting to learn about。

 one called behavior driven development， so test driven development focuses on designing these test cases for our code。

 giving it representative cases and seeing if it actually follows through on the expected values。



![](img/69636fccd899480325fbb2bf55edefaa_68.png)

Behavior driven development is slightly different and that it requires us to first define what it is。

 we want our function to do and describe its behavior Now test that allows us to use behavior driven development and actually gives us a few functions we can use that kind of operate a bit like an English language to define what it is our function behavior should be let me show you what I mean so I'll come back over here and the two functions we have and test that to engage in behavior driven development are these describe and it we're describe as way of describing what it is we want our function to do and it is a way of saying that our function should do something in particular so let's go ahead and switch now to this philosophy of testing I'll avoid using test that and now I'll start using describe so in particular describe lets me do something like this I want to describe now my Greek function and by convention。



![](img/69636fccd899480325fbb2bf55edefaa_70.png)

ically I'll include these empty curly braces here and now I can say inside these curly braces what it is I want my function to do inside these curly braces。

 I'll describe what my function now should do using this it function I could say that it in this case can say hello to a user and as a second argument now to it。

 I'll provide some test cases that show examples of it saying hello to the user namely this I could say maybe I have this object called name all set equal to Carterter and I'll expect that when I run greet and passes input name I should see hello Carter similar now to before but notice what it is we've done We've kind of used a bit of English language in the form of these functions here I'm going to describe my greet function Well what should it do it can say hello to a user and here's an example of it doing。

JustThatSo pretty cool。 Let me go ahead and now run test greet using this other philosophy here。

 Test greet dot R。 And I'll see that that test has passed。😊，哦。What else could our function do。

 what kind of behavior do we wanted to exhibit， Well maybe I could also say that it describing greet now can say hello to the world。

 just like this， and now I'll provide an example of it saying hello to the world。

 I'll expect equal that when I run greet without any input at all， I'll say hello to the world。

 I back I'll get that back out as a return value now。

So here we see a fuller version of a description of greet first。

 it can say hello to a user and it can say hello to the world and by convention。

 I'm using this can say can say here because when we use it it read more like English to say it can do this。

 it can do that so by convention here we're just using that grammar here。

 but I could use any kind of text inside this it function here。😊，Let me go ahead and try to run this。

 I'll say source testgre。or and we get whoop。Seems like I scroll up now that one of our tests has failed。

So here we see error in greet， Greek can say hello to the world。

 but we can actually get back an error and not in this case， hello world。

 error in greet argument2 is missing with no default。

HSo let's look now at greet dot R and see what could have happened here。 I ran greet with no input。

 And if I go look at greet itself well。Now it kind of makes sense because I didn't supply a default value for two if none is supplied。

 so what should I do， maybe supply a default value here。

 I can go ahead and say that two has a default value of world and fix this code after I have described how it should work already and I go ahead and now rerun these tests with this updated version ofG and we'll see that both of my tests have passed thatG can say hello to a user and I can say hello to the world。



![](img/69636fccd899480325fbb2bf55edefaa_72.png)

So we've seen now how to test these strings for equality。

 how to use test driven development and behavior driven development。

 so what questions do we have on test driven development or behavior driven development？



![](img/69636fccd899480325fbb2bf55edefaa_74.png)

Seeing none so it's books on last one last topic for today。

 one called test coverage now the goal of today is been to help you write tests that systematically test your code and one measure you can use to figure out how much of the code you're testing is one called test coverage when you have programs are composed of not just one function or two。

 but many test coverage can tell you how many of those functions you've tested reliably。😡。

Now we've seen today how to spot errors in our programs。

 how to handle those errors and how to write tests to test our code to ensure it behaves as we intend we come back we'll go ahead and see how we can package our code up and share it with the world。

 we'll see you then。

![](img/69636fccd899480325fbb2bf55edefaa_76.png)