# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p41 41_03_01_关注点分离.zh_en -BV18U411U729_p41-

![](img/0ac37058b4c01c75198fdfc4c55fd7da_0.png)

All right。 Now， you can iterate over all the genes in a DNA string and print them out。

 If you wanted to iterate over the genes in a DNA string and do something else to them。

 the algorithm would be pretty similar。In fact， for whatever you want to do with each gene。

 it would look pretty much like this。 The line in blue is the only thing you would change to do whatever you might want to。



![](img/0ac37058b4c01c75198fdfc4c55fd7da_2.png)

Maybe printing only those genes that meet some condition， counting genes， saving them to a file。

 building a web page with all of them or anything else you can think of。

So if you wanted to do these other things， you might copy the algorithm you have past。

 paste it into a new method and edit that line to make small changes。This approach works。

 but it's generally a bad idea。 Why？ Well， for one thing， copy and paste is errorprone。

 You might forget to change some things that you need to。 even worse。

 if you find a bug in your original implementation after you have made copies。

 you need to go fix every copy you made。It is also tedious。 You have to go find the method。

 copy and paste it， and change it。This may not be so bad if you want one variation。

 but if you want to do five different things， it's pretty boring。And finally。

 it indicates bad programming design choices。Whenever you find yourself wanting to copy and paste。

 there's almost always a better approach。

![](img/0ac37058b4c01c75198fdfc4c55fd7da_4.png)

Let's take a moment to see something that we could improve about this algorithm。

 Why it would make a lot of work if we leave it as is and copy， paste change。

 and then we'll understand the motivation for how to fix it。

This is our algorithm to print all the genes in a string。

We're going to condense it down to a small description at the bottom and then copy and paste it and change line 5 to print only the genes with a high CG ratio。



![](img/0ac37058b4c01c75198fdfc4c55fd7da_6.png)

And then we'll condense that down to a short description。



![](img/0ac37058b4c01c75198fdfc4c55fd7da_8.png)

Now we're going to copy， paste， and edit to make several other algorithms to do various things with the genes from our DNA string。

 like printing genes in HTML。Writing genes to an output file。Counting genes with the codon CGA。

Or whatever else you want to do， all of these algorithms are the same。

 except for the details of what they do to the DNA string。 So at first。

 copying pastcing does not seem like a big deal。

![](img/0ac37058b4c01c75198fdfc4c55fd7da_10.png)

Later， we end up with some other DNA data， which lists all of the genes in a file，1 gene per line。

 We need to do the same sorts of operations on this data， too。

 but the algorithm will be slightly different。 It will have a for each line in the file loop。

Then do the same operations for the genes with our copy and paste approach。

 we now need to write and test six algorithms。They are pretty similar to each other。

 so it may not be so hard， but it tedious errorprone work。

Then if we end up with some other source of data， we're going to have to go make all six algorithms again for that data source。

Likewise， if we end up with a new operation that we need to do。

 we're going to have to write three copies of it， one for each data source。 Iick。 What a mess。

What we would really like to do is redesign our algorithm to use separation of concerns。

Our initial algorithm does two task。 One is getting all the genes from some source of data。

 and the other is printing them or whatever else we want to do to each of them。



![](img/0ac37058b4c01c75198fdfc4c55fd7da_12.png)

We would like to split these up by having the algorithms that find the genes put them into some structure that can hold a list of all the genes。

Then having the algorithms that print the genes， count the genes or whatever else we want to do to the genes。

 they should operate on that list。Now， if you need to add some new source of data。

 you just write away to get its genes into our list。

 and it automatically works with every processing algorithm you already wrote。Likewise。

 if you need to write a new processing algorithm， it automatically works with every source of data that you already wrote。

No copying and pasting is ever needed。So what is this thing that can hold all the genes or algorithms fine？



![](img/0ac37058b4c01c75198fdfc4c55fd7da_14.png)

We're going to start by using a class from the Eduu。duke package called St Resource。

 which is a simplified way of doing this。

![](img/0ac37058b4c01c75198fdfc4c55fd7da_16.png)

Later on， once you have learned a few more concepts。

 you will transition to using the standard Java uil do array list class。

 which has similar functionality， but it's a lot more complex。



![](img/0ac37058b4c01c75198fdfc4c55fd7da_18.png)

Thank you。