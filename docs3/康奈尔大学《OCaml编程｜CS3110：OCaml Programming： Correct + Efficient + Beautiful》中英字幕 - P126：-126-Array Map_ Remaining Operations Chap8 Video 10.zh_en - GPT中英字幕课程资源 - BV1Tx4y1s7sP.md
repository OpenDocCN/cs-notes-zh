# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P126：-126-Array Map_ Remaining Operations Chap8 Video 10.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Insert， find， and remove are actually all quite easy to implement。😡，All right。

 so I partway through doing the implementation， I decided to call the argument A instead of M for each of those just to emphasize that it's an array。

But I'm getting a lot of compulation errors here。Indeed。

 it looks like I forgot to do something earlier。I forgot to change the return type of remove to you。

That fixes the compilation error down here。Okay， so insert， what is it going to do。

 it's just going to mutate array component K to store the value at it。😡。

Find is just going to index into the array to return whatever option is there and remove is just going to set the binding at that array location to be none to indicate it's no longer bound。

All of those are constant time operations。We have a couple more functions to implement involving lists and binding。

To implement of list， we can create an array of the appropriate capacity and then just put in all of the bindings that are supposed to be in that array by iterating over the list。

😡，So I'm relying on the functions I've implemented earlier。

 I use create to create an array of the appropriate capacity。And then I use list。

 Ittter to iterate over every element of the association list that's passed in。

 and for every element in it which has a key value binding。

 I call insert on that key in value into the array。😡，Finally， since L dot E only returns unit。

 I use semicolon A to return A as the result of this entire operation。What's the efficiency of this？

Well， we know that creating the array of capacity C is going to be big O of C。

And we know that iterating over that entire list there， well。

 let's see how many elements could be in that。There could be up to big O of n elements in it。

 where n is the number of elements in that list。 And for each one of those。

 we're doing constant work to do the insertion into the array。 So that's all。Big O of N。

Now what's the relationship between N and C here？Well。

 if we look back at the specification for of list。It says list does not contain any duplicate keys。

So that means the maximum length of that list。Would have to be the same as the capacity that is passed into the array。

Because all of those elements have to be unique。And none of them can be out of belt。So N and C here。

 in the worst case， are actually going to be the same thing。Therefore。

 the efficiency of this entire operation is big O C。Finally， to compute the bindings in an array。

 we get to write a good old fashioned loop。Finally， to implement bindings。

 one possibility is just to write a good old fashioned loop。



![](img/06911ec5a05bd3fc7dc6fa3ee12ea40f_1.png)

So let's pause here， the idea is I'm going to create a ref to an empty list。

And then I'm going to keep updating that ref throughout the body of this loop in order to put new bindings in it。

 I haven't done that yet。And then at the end of the loop。

 I'm going to go ahead and return the list inside of that ref that I've been mutating a along。Okay。

 I've gotten a little further here， I want to match each element that I find in the array。

 and if it's nothing， then there's nothing I need to do with it because there's no binding to add there。

 but if there is some value there， then I need to go ahead and add that into the list that I am。😡。

Okay， so if there's no binding there， then I'm going to go ahead and just return unit as the result of that iteration through the loop。

 I'm not doing anything with that。If there is a binding there。

 I go ahead and mutate the list B to add the new pair K V onto the beginning of that list。

What's the efficiency of this operation， Well， it's going to be a number of iterations through the loop。

And at each iteration through the loop， we're only doing a constant amount of work。

Indexing into the array is constant time， creating a new cons is a constant time operation。

 doing the pattern matches constant time。So the whole loop is actually going to be big O of。

That means the efficiency of this entire operation is the capacity there。



![](img/06911ec5a05bd3fc7dc6fa3ee12ea40f_3.png)