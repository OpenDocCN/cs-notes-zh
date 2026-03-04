# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P123：-123-Association Lists_ Insert, Find, Remove Chap8 Video 7.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

![](img/c080ad54d6ba363b688cfd8134970a8e_0.png)

We have insert， find and remove left， because I think you now get the idea of test driven development。

 I will move more quickly through these and abandon that methodology， even though I shouldn't。

 just for the sake of keeping these videos shorter。To insert a binding into a map。

 all I need to do is to put the pair binding that key to the value in the front of the map。😡。

If I were worrying about duplicates， I would have more work to do here。

 but I'm not worrying about them。What's the efficiency of that operation， Well， it's constant time。

 All I'm doing is forming a pair and conziing it on to the front of the list。

How do I find a binding of a key and a map。Well， there's a library function for association list that's already implemented that we'll do this for。

As so opt returns the value associated with a key in a list of pairs actually。

 since it takes the same arguments in the same order， I can simplify this even a bit more。

What is the efficiency of that operation， it has to walk down the whole list， its linear。

As for remove， I need to remove all bindings from the key in the list because there could be duplicates。

 Unfortunately， there isn't a standard library function for association list that does this。

 The remove that's provided only removes the first binding， not all of them。

 So I'll have to code this up myself。

![](img/c080ad54d6ba363b688cfd8134970a8e_2.png)

What I want to do is filter out all the elements that are not equal to that keyK。

 so I'm just passing list thought filter a function that is going to eliminate anything that is unequal to K。



![](img/c080ad54d6ba363b688cfd8134970a8e_4.png)

What's the efficiency of that， Well filter has to you walk down the entire list that's passed in。

 so again， worst case linear。And that finishes our implementation of the map ADT with association lists Now as a good programmer。

 I ought to also finish my test suite here and really I should have been building it out as I went I should use black box testing against the specifications and I could even use glass box testing and bisect in order to figure out whether I have covered all my code Let's keep track for each of our three implementations of the map ADT of what the efficiency of these three important operations are In。

 find and remove。😊。

![](img/c080ad54d6ba363b688cfd8134970a8e_6.png)

For association lists， we were able to implement insert in constant time。

 we were able to just cons and elements onto the front of the list。

 Of course that's because we were allowing duplicates。

The find operation in the worst case has to walk down the entire list。

 that's just a built in limitation of association lists as a representation type it might well be the key that we need is at the very end of that list。

 so we're not going to be able to do better than worst case linear time。😡。

Remove is the same problem we're going to have to potentially walk down the entire list if we want to find the key that we need to remove and so in the worst case it has to be linear time。



![](img/c080ad54d6ba363b688cfd8134970a8e_8.png)