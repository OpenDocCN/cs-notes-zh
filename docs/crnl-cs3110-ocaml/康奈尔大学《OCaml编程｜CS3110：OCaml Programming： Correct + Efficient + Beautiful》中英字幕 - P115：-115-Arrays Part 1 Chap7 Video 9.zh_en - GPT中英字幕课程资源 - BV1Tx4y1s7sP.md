# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P115：-115-Arrays Part 1 Chap7 Video 9.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

O Camel has arrays， which are quite similar to as that you would find in any other language。

The syntax is just a little bit different。In fact， it looks like a blend between the Oaml syntax for lists and for mutable fields。

We can create an array by writing something that looks almost like a list。

That's the list that contains the number one。But we put an extra set of vertical bars on either side。

That is now an int array that contains the number one。

And we use semicolon to separate values in it as well。That's the in that contains one to end。

To access an element of an array， we use a dot syntax。So we could bind that array to a name a。

And then use a do 0 to access the first elements of it。That gets us one。

 So arrays are0 indexed in Ocael， like in most other languages。

 And if you try to index past the end of the array， you'll get an out of bounds exception。

To mutate an element of array， you can use the left arrow syntax， like for fields。

And now a sub0 is five instead of one。Let's write some more sophisticated code with arrays。

 Let's model vectors like you might have from physics or linear algebra。

So we could have a type for vectors， which is a float array， say。

How about we start off just by printing a vector？Well。

 if you're used to doing this in an imperative language。

 probably the first thing that you're going to think of is let's write a loop over all of the elements of the array to print out each one of them。

 we can do that in OCbell。Okay， now I've written a function to print a vector。

 it loops over every index in that array and prints out the float that it finds at that index in the array。



![](img/2e18786c13549bd5d8ea25a42e5398fe_1.png)

![](img/2e18786c13549bd5d8ea25a42e5398fe_2.png)

So we have our vector V， which has one as its first component，0 is its second component。

 and we print it out and we get each component on a separate line。

Notice how when we loop over all the elements in the array。

 we can use array dot length to get the length of the array。



![](img/2e18786c13549bd5d8ea25a42e5398fe_4.png)

And if the length is2， that means the valid indices are 0 and1。 So as usual。

 we have to deduct one from that length to loop over each of the indices。



![](img/2e18786c13549bd5d8ea25a42e5398fe_6.png)

There are more clever ways to implement our vector printing function though。

 using ideas from functional programming and higher order programming。Let's look at them。



![](img/2e18786c13549bd5d8ea25a42e5398fe_8.png)

There's a function in the array module of the standard library called Ittter。

That function takes in a function of type alphapha arrow unit。It also takes in an alpha an array。

And it applies that function to every element of the array， so it's like saying F of a0， F of A1。

 semicolon and so forth， all the way up to the end of the array。



![](img/2e18786c13549bd5d8ea25a42e5398fe_10.png)

By using iter， we get away from having to write a loop。

That also means we don't make mistakes with our loop indices。

 Like it's very easy to forget that -1 there， at which point you'll get an index out of bounds exception。

With a dot iter， we don't even have to write a loop。

We can just pass in a function that prints each element of the array。

Notice the nice separation of concerns that we have here。

 we have a separate function for what's supposed to happen for each element of the array。

 That's my print element function。And we have a radar iter。

 which handles all of the iteration over the elements of your array so that we don't have to write a loop and maybe get the loop wrong。

Both functions print the same thing as for shortening this code up even further。

 What if we could write a function that prints an element of an array。

 but do it in sort of just one line。Well， the print F module in the standard library gives us a way of doing that。

If you're familiar with the print F function from C or any other imperative language。

 this is going to feel pretty familiar to you。And that's all there is to it。

That printf function takes in what's called a format specifier。

 a string that says how to print an argument。

![](img/2e18786c13549bd5d8ea25a42e5398fe_12.png)

![](img/2e18786c13549bd5d8ea25a42e5398fe_13.png)

Percent F here means to print a floating point number， the back slash N means to print a new line。

We do get slightly different output than we did before you see all the additional decimal places being printed。

 that's because the standard percent F prints out floating points in that style。

 if you want to print them out in the standard Oaml style that leaves off all the zeros。

 you can do that too。

![](img/2e18786c13549bd5d8ea25a42e5398fe_15.png)

Notice we use a capital F for that。And now we have the same output as we did before。



![](img/2e18786c13549bd5d8ea25a42e5398fe_17.png)

But we get it with a very short function。That doesn't require us to implement a lot of code and potentially make a lot of mistakes in that code。



![](img/2e18786c13549bd5d8ea25a42e5398fe_19.png)