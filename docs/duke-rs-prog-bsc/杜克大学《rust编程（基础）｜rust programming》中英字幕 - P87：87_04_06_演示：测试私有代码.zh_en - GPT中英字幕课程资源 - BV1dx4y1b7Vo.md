# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P87：87_04_06_演示：测试私有代码.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/d08eb35e1b8aaa7667b5648887184577_0.png)

One of the problems that we haven't seen yet is how to test private code。

 So what we have here is we have a function called read standard in and our function has one problem and that problem is that right now as it is。

 it doesn't take any arguments， and it defines the standard in as input right here in line 24 and then later it uses a standard in that lock to create that mutable reader variable that's fine for this function but how can we test is if we don't have access to standard in log。

 So let let me explain a little bit further what we're trying to do here I'm trying to think about how I'm going to inject input to to this read that standard in so that we can。

Craft the conditions for these function to work。 and I can't because this is not taking an argument and it's calling standard in right there。

 So what I'm going to do and there's definitely many different ways to approach this problem。

 but what I'm going to do is I am going to break this into two functions。

 So the first thing I'm going to do is I'm going to grab all of that I'm going to take it away and then going to create a separate a separate private function。

 I'm going to do going to prefix it with an underscore。 I'm going to say it read standard in。

And then that is going to actually， we're going to make this a generic。

 I'm going to make it the type R。 I know we haven't seen generics in detail yet。

 but I what I'm saying essentially is that this is going to take a reader。

Of the type it can be as long as it implements， the buffer rate is going to be fine。

And we're gonna say who's going to be a mutable type。 And then it's going to， yes， return a string。

And then what we're going to say is not only let create a mutable line variable and say， yes。

 this is going to be a new one。But then we're going to simply return the reader with the read line and then expect。

 however， we're also going to want to return line the trim just like it was before to string because that's what we wanted to return。

 So great， we've broken this one apart。 And now here on line 25， I'm going to open up。

 and'm going to say read standard in and then mutable reader。 Okay。

 so what have we've done we've extracted this portion of code from the read standard in。

 So now the read standard in is going to call to read this underscore read underscore standard in。

 So why are we doing that。 Well， the reason why we're doing that is because now we are able to。

Pass in an argument to this function。 this reader argument to this function can be any type that as long as implements the above read properties and functions and methods。

 We're going to be good to go。 This will allow us to test。

 So now I can construct that and be no problem at all。 This is going to actually work。

 So that also means that I wouldn't necessarily be able to test read center。

 But that's fine because defining these two variables is kind of like acceptable。

 I'm going to be okay with that。Not being tested， but the most important portion of what I'm trying to test is right here。

 and that I want to test that makes it so that whenever someone wants to use my API is going to be doing that and not necessarily looking at this function here that allows me to pass in certain things as an argument in construct things and make it easier for me to test because it's accepting reader argument。

 All right， so what does that mean， how can I test private code because now do you see that I didn't add a pub。

 I didn't prefix this function with pub， this one is pub。

 this one isn't So this one is able to use read underscore read center in because this one is in the same module no problem So how do we go about testing this private code。

 we cannot go back to our tests because then this is not publicly available。

 So we wouldn't be able to。Get that axis， right， We can， we can go and say CI U。

 like if I change this to read standard in。Like that。 it would。 it wouldn't work。

 if I save that and run this do test， it will say if I scroll a backup up。

 it will say private function， right， it's not， it's I can access that。 So I this is not。

 this is not gonna work。 Alright， so let's， let's get back that in work in order。 actually。

 let's get that one there。 And if I run the do test just to make sure that everything works， Yes。

 it works。 Okay， perfect。 So now what I'm gonna do， I'm gonna write test。

 So how do you write test for a private， for a private。For a private function。

 So first I'm going to yes， I'm going to define these confit test。

 I'll tell you what that is in a second。 I'm going to declare mod tests。

 and I'm going to say the first thing you want to do is like I'm creating a module called tests。

 One way of doing this is creating a use super and then that double column。

 but that means is like I want to bring into scope everything that is declared in this module。

 I'm going to try to be explicit here， and I'm going to say super。

 and I'm just going to bring read standard in。 I do have access to that because I'm mean the same module So that will work and the next thing yes I'm going to use the cursor because that allows me to create that that argument to our function。

 this one right here， this reader， I'm going to create with this cursor that I'm bringing into the scope。

 Next I'm going to start creating a test。 I'm gonna write a test right here。 I'm going to。

So with that attribute， and I'm going to say function test， read standard in。

And then I'm going to open up a curly bracket and then I am going to say yes。

 the mutable reader is going to be cursor new test。

 and then I am going to accepted like that and then I can try and run that test so what I'm doing here I'm creating I'm creating this test read standard in that looks correct to me and then I'm going to test by using the underscore read standarding。

 which is a private function that is coming from right there。

 that reader which is actually a cursor implements b read so nowhere is there it should actually work and now if we run it we're getting an OK so let's take a quick look at the assert here and we're saying that the line from read standard in which is this one right here。

 it is actually coming from from this one on line 44。We're saying， hey。

 even though I'm passing with like an extra new line character。

 what I should be getting is actually a test， no new line character。

 that happens because of the trim and I'm able to compare it to a string。

So there we go That is how you test how you test a private function and you can keep going on to add more tests so for example。

 we can say function test read standard in empty like if we want to say like you know what if my cursor is completely empty So there we go that that would be empty now we're missing the attribute and I notice because I'm getting the curly underlined so you can see it's never used so let me go ahead and do that。

And then if I run that test， we'll get an okay。 So now if I do if I open up the terminal。

 I can do cargo test， dash dashlib。 and if I do that。

 you will see that both test read standard in empty and read standard in will work。

 Why am I doing the dash dashlib because if I just do cargo tests。

 you will see that there's a lot of output there that happened。

 including my do test So it's running absolutely everything including the tests， but dash dashlib。

 the difference from what we've seen before is that will ignore all the do test and it will only include tests that are defined within the code that is coming from my library。

 my package that I've created my crate So that is how you add those two things And the last thing that we need to see is why did I add a Cfg or。

hi is accepts an argument and in this case is test Well this is a way so that we can tell cargo。

 hey by the way when you're building my library as and you're doing all of that code do not include this code because this code is just only going to be for a test and I don't want to include that less explicitly unless explicitly I'm asking to include the code for test so this is a way of easily nicely being able to exclude code。

From compiling from a release that is going to go out so that this is not necessarily part of the library。

 the package， whatever I'm going to be releasing in a crate， so there you go。

 this is testing we've done a little bit of surgery。

 we split the read standard in into another function that allow me to test it very nicely because I was able to fitting the reader that way my external API looks very nice and clean is just a simple call it doesn't require the user to be constructing that standard in and then we're able to do some actual testing here because we're able to use the private function that is not exposed by using some test live inside of in this case live that rest notice I didn't use an external test directory with another test module inside the test directory。



![](img/d08eb35e1b8aaa7667b5648887184577_2.png)