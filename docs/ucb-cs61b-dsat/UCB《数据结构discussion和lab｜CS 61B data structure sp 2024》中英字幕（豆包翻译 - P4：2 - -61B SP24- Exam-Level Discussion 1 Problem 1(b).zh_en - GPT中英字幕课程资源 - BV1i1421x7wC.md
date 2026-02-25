# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P4：2 - -61B SP24- Exam-Level Discussion 1 Problem 1(b).zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

Hello， I'm circlecle Chen， and in this video， I'll be walking through exam prep discussion 1 problem 1 B for spring 24。

 So this is a slightly modified problem from the previous semester。 So that's why I made this video。

So the previous problem 1 a is the same as the quick maths problem from the previous semester exam question2。

 so I encourage you to check out the video for that on part 1 a。

Now part 1 B builds on swapping primitive values。So as we see here， we have two values。A and B。

A and B are inter variables and the values are 6 and7。Now， Java is passed by value。

 so we cannot just swap A and B by using the swap function like we did in part A。If we did that。

 that would just be swapping the copies of A and B， and this would not work。So in this problem。

 we're actually using an inrapper to help us solve this issue。Now。

 an inrapper is just a class that has a one single instance variable called x。 and this x is just。

The value of that integer。We have a constructor that takes in value。

 and then what it does is that it sets the x， that instance variable to the value that's passed in。

So with that， what we can enable ourselves to do is just to create two intrapper objects。

Of the A and B。So we can do here is int wrapper。We can do x equals the new interrupter。



![](img/e31ca206c2d1a2d4f3f30546a83c3428_1.png)

And then I'm going to put a in there。Now， the second one， just the same thing。

I'm just going to write it short。

![](img/e31ca206c2d1a2d4f3f30546a83c3428_3.png)

Now， once we created those inrappers， we can think of passing these inrappers inside the swap method。



![](img/e31ca206c2d1a2d4f3f30546a83c3428_5.png)

Now， this swap method is something well also need to code。

So it's going to take in these two inrappers。Let's name them first。



![](img/e31ca206c2d1a2d4f3f30546a83c3428_7.png)

And second。So recall how Java deals with reference types when we pass an X and Y into the swap method。

The pointers to those objects actually gets used in the arguments。



![](img/e31ca206c2d1a2d4f3f30546a83c3428_9.png)

So we have x and y。That is。6 and 7。

![](img/e31ca206c2d1a2d4f3f30546a83c3428_11.png)

Then when we actually use swap， we open up a new frame and first would point to this interper object。



![](img/e31ca206c2d1a2d4f3f30546a83c3428_13.png)

And second。We point to this and on。

![](img/e31ca206c2d1a2d4f3f30546a83c3428_15.png)

Interrappper object。

![](img/e31ca206c2d1a2d4f3f30546a83c3428_17.png)

Now， we want to be able to swap those things。 So ideally， inper。



![](img/e31ca206c2d1a2d4f3f30546a83c3428_19.png)

Now， I should have been 7 and should have been 6。Well a naive solution might be just to say we create temp。

 another intrarapper pointer that points to these things。

 and then we swap things around using this three variable method like we did in part A。



![](img/e31ca206c2d1a2d4f3f30546a83c3428_21.png)

![](img/e31ca206c2d1a2d4f3f30546a83c3428_22.png)

![](img/e31ca206c2d1a2d4f3f30546a83c3428_23.png)

![](img/e31ca206c2d1a2d4f3f30546a83c3428_24.png)

Now， this wouldn't really work because what we're actually doing is that we're just reassigning wherever first and second arere pointing to。

 we will just be swapping first to point to here and we'll just be swapping second to point to here。

 Now this wouldn't really affect what X and Y are pointing to。

 So this is not a correct method of swapping X and Y。



![](img/e31ca206c2d1a2d4f3f30546a83c3428_26.png)

What we really want to do is that we want to swap the instance variables X inside these entropers。



![](img/e31ca206c2d1a2d4f3f30546a83c3428_28.png)

So what we can do is。We can set a new into temp。To be。X， sorry， not X first。



![](img/e31ca206c2d1a2d4f3f30546a83c3428_30.png)

First， do x。So that saves the xa first。

![](img/e31ca206c2d1a2d4f3f30546a83c3428_32.png)

And then， we're gonna have。We're gonna have first， start x。To be second dotx。

We can do this because we already saved the previous value of first dot X。

 So we don't have to worry about being overwritten。



![](img/e31ca206c2d1a2d4f3f30546a83c3428_34.png)

Now we can just simply set second on x。

![](img/e31ca206c2d1a2d4f3f30546a83c3428_36.png)

To temp。Now when we want to call the swap method， we're just going to pass in X and y。



![](img/e31ca206c2d1a2d4f3f30546a83c3428_38.png)

![](img/e31ca206c2d1a2d4f3f30546a83c3428_39.png)

Now， once we're done with swapping these things， what this is going to do is that it's going modify whatever is stored。

 and this is going to change from 6 to 7。 It's going to change from 7 to 6。 Now。

 we just want to revert these changes and reflect that to be in a to those into A and in B。

 so we can just reassign those things back。 So a is equal to。



![](img/e31ca206c2d1a2d4f3f30546a83c3428_41.png)

![](img/e31ca206c2d1a2d4f3f30546a83c3428_42.png)

![](img/e31ca206c2d1a2d4f3f30546a83c3428_43.png)

X dot x。And then B is equal to y dot x。

![](img/e31ca206c2d1a2d4f3f30546a83c3428_45.png)

![](img/e31ca206c2d1a2d4f3f30546a83c3428_46.png)