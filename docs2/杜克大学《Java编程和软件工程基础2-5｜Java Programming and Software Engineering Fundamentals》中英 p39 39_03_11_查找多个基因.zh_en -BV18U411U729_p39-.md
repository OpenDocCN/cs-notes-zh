# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p39 39_03_11_查找多个基因.zh_en -BV18U411U729_p39-

![](img/76ada0568212f3cd108d34698630bc12_0.png)

H。So far， you've written a method to find a gene and gradually improved it。

It's gotten much more sophisticated than when you first started。

 although it's still a bit of a simplication of what you'd actually do。

Rather than continuing to refine this method， let's ponder a different facet of searching for genes。

So far， you've only been looking for the first gene in the string。 However。

 strings may have many genes。What if you wanted to find them all and print them all out？😡。

You can already find one。Although you might want to make some slight adjustments to the methods。

 so you can start looking midway through the string。



![](img/76ada0568212f3cd108d34698630bc12_2.png)

Since you can find one， and you want to find many， you want to repeat steps using a loop。

 Lo should be getting pretty familiar by now， since you might want to repeat things as long as there are more genes you can make use of the wild loop that you recently learned about。

However， there's a bit of a difficulty here。We won't know if there are more genes until we start searching for them。

This may make it seem hard to write the loop condition。

There are many ways to deal with this situation and code。

 but the one we're going to teach you about is how to use a brake statement to leave the middle of the body of a loop。

We'll work through a slightly shorter example than we normally walk through in developing the algorithm to print all genes。

If you don't understand this completely when we finish， pause the video and work through steps one。

 two， and three yourself。We're going to show you how it operates on this DNA string as we write it。

First， we're going to set start index to zero。Start index will represent where we start looking for the next gene。

Then we're going to repeat some steps as long as there are more genes after start index。

We want to find the next gene after start index， we want to print that gene out。

And then set start index to just pass the end of the gene we found。

To show you how the algorithm would continue working on the string， we then go back to step two。

And keep repeating these steps。As there are more genes after start index。

 notice this is the difficulty we alluded to before。

We need to know if we will find more genes or not。But we haven't looked for them yet。

We'd find the next gene。Print it out。Update start index。

And then realize we should stop repeating steps because there are no more genes。However。

 we have this difficulty。 We need to know if there are more genes in step 2。

 but we don't look for a gene until step 3， which makes the algorithm a bit awkward to implement。

 Really， we'd like to make a decision about whether to keep going or to stop right here between steps 3 and 4。

Here's a slightly modified version of the algorithm， which does exactly that。

Notice that our repetition instructions no longer have any condition。

 they just say repeat these steps。We'll figure out later when to stop。Likewise。

 we now have another step in the middle of the loop that says。

 leave the loop if we did not find any genes。This will be much easier to implement。

Once we learn how to translate these kinds of steps into code。For step two。

 repeating steps without checking any particular condition， you can simply write while true。

If the condition of a while loop is simply true。The code will always enter the loop body when we reach the top。

 because true always evaluates to true。The other new piece of Java syntax will' need is the break statement。

 This is how you say leave this loop。In this example。

 we've translated if no gene was found into an if statement that says if gene dot is empty。

The is empty method for a string returns true if the string is the empty string and false otherwise。

 remember， our gene finding method returns the empty string whenever it can't find a gene。



![](img/76ada0568212f3cd108d34698630bc12_4.png)

Inside the if statement， we've seen leave this loop translated into a break statement。

A break statement which is written in Java simply with the keyword break followed by a semicolon。

 causes Java to leave the current loop。Regardless of whether it's a while loop or a for loop or any kind of loop you might yet learn about like a do while loop。

Basically， Java jumps past the close right curly brace that ends the loop。

Now we know how to implement these steps， let's turn the algorithm into code and try it out。

 we'll find every kind of gene there is。Have fun。

![](img/76ada0568212f3cd108d34698630bc12_6.png)