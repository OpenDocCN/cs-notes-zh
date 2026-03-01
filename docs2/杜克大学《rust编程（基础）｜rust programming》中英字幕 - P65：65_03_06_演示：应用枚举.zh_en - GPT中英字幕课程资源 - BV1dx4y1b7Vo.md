# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P65：65_03_06_演示：应用枚举.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/658635711e7e07bed27d631503dd4822_0.png)

Let's take a real world scenario of using an inum and in this case we are going to do we're going to do the one that is file size。

 we're going to have byte， kilobytes， megabytes and gigabytes and what we're going to do is we're going to have a thing。

 a function a piece of code that formats that nicely so in the past I've had to build something similar to these many different times and just for sake of formatting you always have like some sort of function that will do the conversion for you so。

The idea is that you will get like a size in bytes。 You know。

 many command line tools will provide the size in bytes， not necessarily like human readable format。

 So what we want in this case is to provide a human readable format， depending if it's bytes。

 kilobytes， megabytes or gigabbytes。 Okay， so we have。

We have these four different types of variants for the file size and numerator inum file size and what we're going to do is this format size function is going to take an argument called size and depending on the size we're going to say let file size be a match of size they can be any of these four different options if the size is from0 to 999 inclusive。

 remember that equal sine， then it will be bytes and otherwise it will be kilobytes。

 megabytes and gigabytes and so on and so forth and you see that the number we're using to divide will continue to increase if it's always going to be a if it's a if it's a we're not doing an division we're just returning an as and then finally here we're going to do another match and in this case we are going to pass in。

The bytes or the kilobytes， megabytes or gigabytes。

Passing in from depending on the type of depending on the type of variant that we have been using and in this case。

 we are going to say well it's aretes or we're going to be doing another operation here So we're going to use kb as f64 and kb is coming from here so you are going to be able to format that as it's coming in al right so now let's take a look at our main function and we're going to say we're going to pass in this very big number which is bytes and we're going to run it and we're going gonna see what we get so we get 0。

01 gigabytes that's pretty good let's add a couple of0 see what we get now now we're gonna get 0。

69 gigytes let's add like a couple of numbers over there so all of these are bytes and we're get in 630。

6。9ine gigabytes and so on and so forth so that is a very very normal way where you could you know grab an enummerator and inum in this case file size and use a function to do some formatting but one thing that you can actually do is make an associated function or method just like a struck this is actually possible in rust so let's actually update all of this code and remove that and make that implementation so I already have done it from before I'm gonna to paste it here so that you can see how it's done instead of you me type everything again from scratch alright so what is it that we have so we have file size the inum right here everything stays the same but we are extending it with with an implementation。

keyword right here。 So the implement keyword will allow us to extend just like we've seen fourstructs。

 but in this case for the inum So what we're going to do is we're going to define this one function that takes that takes actually self and returns a string which is kind of like way want we want to get that formatting very nicely and depending on what we're gonna to get。

 we are going to be able to format that。 and then the other piece of code that we had before。

 which was that loop now it's going to go into main and we're going to do the heavy processing here。

 now yes， this could get abstracted into a function but for now it's fine as it is right here。

 So let's run it in this case we got 10 megabytes， let's take a look at the code again we have that size that looks pretty good now let's add another a number over there。

 let's run it again and we can we can actually keep tweaking that。In this case we got 0。

04 meytes and there is still a small bug in here because if we add more numbers。

 we will get0 gigabytes， which is not what we're looking for and not exactly kind of like what you would expect。

 but now we're getting4 gigabytes and so on and so forth so we can actually tweak it to make it a little bit better。

 but important thing here rather than that small bug that we have in our small implementation is that we took these。

This little logic outside of the big function that we had before and we broke the function that we had before into this one other part over here so that it would extend it would extend the inum file size so file size will have now these format size and the way we call it is file size that format size and it makes perfect sense to to have those helpers be tightly coupled because format size will probably be always tied to that file size and numerator so those are two ways where we can apply or you can see how we can apply inums in real world use case scenarios and actually how you can extend it with associated functions and methods。



![](img/658635711e7e07bed27d631503dd4822_2.png)