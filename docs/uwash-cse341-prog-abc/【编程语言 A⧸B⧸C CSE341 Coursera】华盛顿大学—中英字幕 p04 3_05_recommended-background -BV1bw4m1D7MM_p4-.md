# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p04 3_05_recommended-background -BV1bw4m1D7MM_p4-

In this video I want to discuss the recommended background for the course。

 which is a very important topic but also a difficult one to discuss and so many people have so many different backgrounds that could be a good fit for what we're going to study。

 So the key thing to emphasize is that on the one hand this is not an introductory programming course that the way I've designed the material assumes you have done programming before just in different languages。

 it doesn't have to be a lot of programming however。

 if you've taken one or two other programming courses and succeeded at them。

 this will probably be fine it doesn't have to have been courses you could have picked it up on the job or done your own learning or whatever on the other hand this is not an advanced programming languages course。

 I typically teach this on campus to sort of second year students。

 not people with years of professional industry experience or not even what I would consider a last yearear undergraduate course so it's not an introductory course you should have programd before but it's not a particular。

advancedvanced course。 I want to give you a little better sense of that。

 So here are some topics that I assume you would have seen when programming before。

 So things like variables and having arguments to a method or function or procedure。

 any if you've called things methods that's fine， but things that take arguments and return results。

 some kind of if statement， some kind of branching for I do this in some situations in other situations。

 I do that。 you've probably seen some sort of loop， you've probably seen some sort of array。

 even though here in at least part A of programming languages。

 we're not going to have loops or arrays。I do assume that you've seen recursion before now we're going to get a lot more practice with recursion。

 we're going to use recursion on almost every problem， on almost every homework assignment。

But we're going to go awfully fast if you've never seen it before。

 recursion is the idea of defining some computation in terms of itself。

 defining some data in terms of itself， and we'll get lots more practice。

 but the way I've organized this course assumes some exposure before。

 and if you haven't seen that you may find it a little extra difficult in the beginning。

The next thing， implementation versus interface， the idea that clients of some code only have a high levelvel idea of what the code is doing and should not have exposed to them the implementation details and they should not rely on those implementation details this goes by a lot of different names like abstraction or modularity you may have seen this in terms of an object oriented programming setting。

 something that we won't do until part C of the course doesn't matter where you've seen it and again it's the sort of thing you may be able to pick up along the way。

 but it is kind of assumed background the sort of thing one would see in a first programming course I'll refer to some basic data structures like linked lists and binary trees that often come up in introductory courses as well and dynamic dispatch or method overriding or subclassing is something that students generally have seen before but we're actually not going to need it until late in the course and even then it will be reviewed so if everything on this slide that you'd probably be okay without this。

Be it。Now you'll notice I haven't really emphasized what language you need to have programmed in before because it doesn't really matter。

 I tend to sometimes assume more of a Java or C sharpp sort of background。

 but not in the actual material， not anything you'll have to do for the homeworks or have to understand in a video if you've only programmed in Python or jascript or something else。

 that's probably fine what matters are the concepts on the previous slide。

 Now I'll sometimes an optional videos compared to Java for those of you that know it。

 And if you only know C sharpp Java will probably be fine and I'll sometimes compare to C。

 which is lower levell programming language that is often a really nice contrast for some of the concepts we'll study in the course。

 but all of those specific language comparisons will always be an optional material and one reason why it doesn't matter what language you've used before is that we're really going to start over from the beginning that particularly early in the course。

 you may find it even more for us or if you have a lot of programming experience because using Ml can feel so foreign and so。

Different and that's actually a great thing because it means it doesn't matter exactly where your prior experience is。

 it's just we're going to go fast enough that if you haven't programmed before。

 it's going to just not make a whole lot of sense what we're doing。😊。

Okay so what I want to do now is do an example of the sort of code that students at my university would be able to write or at least follow along with prior to taking the course that this MOOC is based on Now I want to emphasize that if you haven't seen Java before this might not make sense hopefully some of it make sense you should also understand that as I write this code first of all。

 I'm the teacher so I know what I'm about to do and second I'm actually cheating I actually have a copy of the code I'm writing for you nearby and I just looked at it so don't take this as intimidating just take it as an example of how throughout the course I am going to write a lot of code and I'm going to discuss concepts as I write the code that should even if they sound a little foreign to you because of the strange syntax or maybe you haven't used exactly this terminology before some of what I'm doing should look like programming and feel like the sort of thing you have seen before So it give you some sense of what I mean by programming experience。

But again with all the different backgrounds and everything。

 it's just not something that I can you know promise will make sense to everyone and that's okay All right so here I am。

 I often write code in front of you and here is the only time for a long long time I will write Java code for you but in Java we would declare a class for a binary tree of integers this would be something where any tree that's not empty which will represent with Javas null we'll have an integer in it and we'll have a left subtree and a right subtree those are the two child branches of the tree so this is a data structure where each part of the structure has an int and then two other structures which we're calling left and right in Java we would create one of these with something called a constructor and this is how you define a constructor in Java that takes three arguments and because I'm using a nice big fontier very little fits。



![](img/368c3cf827347cb7fc9e0b6807741559_1.png)

On a line and then this would be some code， this is a method。

 although constructors are a little different in Java where we would initialize the fields of our object to in this case just be the three arguments passed in allright。

 and that's how we would create such a thing we could then write a method on a tree that would say sum up all the numbers in a tree so just take a tree and sum up all the numbers。

And the way I would do that here I'm going to do it recursively is I would compute an answer。

 which I'm eventually going to return， and I'm going to include the I field。

 which I could write this dot I or I could just write I that this dot is not necessary in Java here。

 And then if the left child。Is not null。 Then I need to add to ants。

 And there's a faster way to write this。 I know the result of calling the sum all method on the left child。

 and I then need to further add on。The sum of recursively adding all the numbers in the right child。

 And this is how you would do such a recursive algorithm in Java。 And if I've made any mistakes here。

 I always fix up the code before I post it。 I actually， of course。

 am coding in front of you here and maybe making small typos as I go。

 And that would be our sum all method。 Let me show you one other thing。

 And here I'm going to just paste this in。So that you don't have to watch me type it all out。

 Here is another method。 This one happens to be a static method that's a distinction that doesn't matter to us too much that just takes in an array of integers that has nothing to do with binary trees anymore and just returns the maximum element if you think about it returning the maximum element for a collection doesn't work very well if you don't have any numbers So this code happens to assume that the array has at least one element。

 which I'm putting in a comment here。 and the way it does it is it starts with the first element of the array。

 which counts from zero in Java in many programming languages and then has a four loop that keeps seeing if the next element of the array is greater than the answer computed so far If so it updates it when we're done with this four loop we return the answer。

 So this is just an example of how I code in class in a language here that you may or may not be familiar with。

 but when we get into Ml and the first real section of the course I will go slower。

 I will explain everything I'm doing but this is how I talk about programming。In this case。

 relying on some experience you may have seen， but more generally by explaining every little thing as I go。

 the class will feel a lot like this， but with everything explained one piece at a time。



![](img/368c3cf827347cb7fc9e0b6807741559_3.png)