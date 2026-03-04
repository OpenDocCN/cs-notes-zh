# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P134：-134-Hash Table Find and Remove Implementation Chap8 Video 18.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Next， let's implement find this one's actually much easier All we need to do is index into the buckets and get out the right element of the association list。

😡，So we get the correct bucket and we just look up the key in that bucket easy。Finally。

 let's implement remove。 Let's start like we did with insert by factoring this into two pieces。

 actually doing the removal and then doing the resize if any。Okay， we'll pause here。

 we've created a helper function for doing the remove without the resize。

And we can reuse the resize function we already wrote for the table when we did insert。

 So half the implementation is done for us。 Now we just need to implement the remove。All right。

 the implementation of that is almost the same as insert no resize。

 we're still trying to find the index of the bucket， get the old bucket。

 it's just this time we do a remove from the association list instead of an insert into it。

 and we also have to do the negation of the guard for the if expression and decrement size instead of increment it。

Could we maybe try to factor out some kind of common piece of code between insert and remove？

Possibly， but it's not really going to be clarifying at this point to try to factor out a common implementation between the two。

 I would personally leave these the same， even though there is a certain amount of code that looks similar between them。

 they aren't really trying to accomplish exactly the same purpose。😡。

What about the efficiency of this， Well， it's really the same analysis as we did before for insert。

The efficiency is going to be expected constant。And therefore the same is going to hold for remove。

 it's going to be expected linear time because in the worst case we do have to do the resize。

 and that finishes our implementation of hashmap。We could go and add a bindings function to it as well as an of list function like we had for our previous two data structures。

 you will find the code for that in the repo and in the textbook for these videos。



![](img/88cdbcbb2a941c890f0726eb43db84d4_1.png)