# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P23：-023-Lists Chap3 Video 1.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We took a deep dive into Ocaml functions， now we're going to go back to data。

We'll start with Ocael lists。A list in Ocael is written inside of square brackets。

 That's the empty list。 I didn't have to put the space in between those。

 The empty list contains no elements， and its type is alpha list。

 You can read that type from right to left， if you like， It's a list of elements of type alpha。

 Why Al， because there's nothing in it yet。 It's parametric in the type of the element at this point。

There's nothing in it， so it doesn't need to have any particular element type。

But once we put something in a list， say the integer 1， now we've got an int list。

 It's a list of ints if you read it right to left。We celebrate elements of a list by semicollon。

 so there's the list  one，2。1，2，3。And of course， we can have elements of different types in a list。

 We could have a list of floating point numbers if we like。That would be a float list。

 a list of booles， if we like。 That would be a bo list。 We can have even have lists of lists。

 So here's the list that has one，2 as its first element。3，4 as its second element。And 5。

6 as its third element。So we've got nested lists going on。 This is an int list list。

A good way to read that is， again， from right to left， a list of list of integers。

There's another syntax for writing lists。If you already have a list， say two， three。

And you want to put another element in front of it。You can write that with double colon。

That gives you the list 1，2，3。 It puts the element 1 on the front of that list。 And， in fact。

 I could even write the entire list using only double colons to just keep adding elements on。

And end with the empty list。So that's the list 1 two，3。

 and you can see Oll simplifies it and just writes it inside of square brackets for me。

Ochemmo lists are immutable， like other data we've seen so far in Ochemel， you cannot change them。

 Once you have created a list， you cannot go in and remove one element of it or change an element to something else。

 All you can do is construct new lists out of old lists。



![](img/5ac9d364c9328438877f20cf52e3d22f_1.png)

![](img/5ac9d364c9328438877f20cf52e3d22f_2.png)

![](img/5ac9d364c9328438877f20cf52e3d22f_3.png)

![](img/5ac9d364c9328438877f20cf52e3d22f_4.png)

That's what we did with double Co。

![](img/5ac9d364c9328438877f20cf52e3d22f_6.png)

Ocamo lists are singly linked。Now， Sly linked lists are just one data structure for representing lists in 20110。

 you will have also learned about array lists， for example， that's a different implementation。



![](img/5ac9d364c9328438877f20cf52e3d22f_8.png)

![](img/5ac9d364c9328438877f20cf52e3d22f_9.png)

![](img/5ac9d364c9328438877f20cf52e3d22f_10.png)

The lists that are built into Oammel are singly linked because they happen to work very nicely。



![](img/5ac9d364c9328438877f20cf52e3d22f_12.png)

But that doesn't mean they're always going to be exactly what you need for the job at hand。



![](img/5ac9d364c9328438877f20cf52e3d22f_14.png)

Data structures are tools， just like languages or tools。 There's no perfect data structure。



![](img/5ac9d364c9328438877f20cf52e3d22f_16.png)

Ocal's Sly linked lists are good for。

![](img/5ac9d364c9328438877f20cf52e3d22f_18.png)

Processing data， if you need sequential access of， say short to medium length lists。

 it's a little hard to put an exact number on that， but say somewhere up to 10000 elements。

 these lists are going to work well for you。 And if that's not what you want， no big deal。

 you can reach for another library implementation if you need to some day。



![](img/5ac9d364c9328438877f20cf52e3d22f_20.png)

![](img/5ac9d364c9328438877f20cf52e3d22f_21.png)

![](img/5ac9d364c9328438877f20cf52e3d22f_22.png)

![](img/5ac9d364c9328438877f20cf52e3d22f_23.png)

But you'll find as you get used to them， that these are pretty good for whatever it is you need to do。



![](img/5ac9d364c9328438877f20cf52e3d22f_25.png)

Next week we'll study the implementation of lists in OCAML。



![](img/5ac9d364c9328438877f20cf52e3d22f_27.png)