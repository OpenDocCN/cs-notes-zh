# 多伦多大学【中英⚡编程入门：编写高质量代码｜Learn to Program： Crafting Quality Code】 p23 P23 05_编写特殊方法 __str__ -BV1QuJVzpEKE_p23-

In this video， we'll explore one more special method underscores STR。

Here is our class cash register with our special methods init and EQ， as well as get totalal add。

And分 move。Then at the bottom， we create three cash registers and we print whether they are equal in various ways。

Let's print CR1 as well as CR2 and see what Python produces for us。When we run it。

 we see output that looks a lot like what we saw in the debugger for a cash register object。



![](img/35789e86ecd9d8acf8672571de5b9244_1.png)

We first printed what CR1 referred to， and that's a cash register object and a particular memory address that ends in 550。

The object that CR2 refers to is a cash register object that a memory address in C90。



![](img/35789e86ecd9d8acf8672571de5b9244_3.png)

This might be useful for debugging， but it's not particularly useful for presenting information to a human。

Function Bt calls underscore stir on the object that it's printing。

So that's right one for our cash register。Here's the header with self as the only parameter。

 and for an example， let's go grab a cache register and then modify it so that all the values for loooneies to these five1s and ws are different。

Now we'll call this special method。Now we need to decide what we want this output to look like。

We' say the cash register has $160 in it， we did a quick calculation off screen。

And let's put in parenthses， how many looNies there are， how many tuies there are， and so on。

For the type contract， SL refers to a cash register object， and this method returns a string。

 in fact it returns a string representation of this cash register。For the method body。

 we'll return the string cash register followed by a coal in a space and a dollar symbol。

Followed by the total amount of money in this cash register。

What comes next is the number of loonnieies。We'll start in line and then add the number of tunings。

And fives。Whohoops， I forgot myself。Then comes the number of tens。And finally， 20s。Last。

 we need a closing parenthesis。

![](img/35789e86ecd9d8acf8672571de5b9244_5.png)

It's time to try running it and there's an error。We see here that we have a type error。

 we can't convert int object to stir implicitly。

![](img/35789e86ecd9d8acf8672571de5b9244_7.png)

The problem is that self do tens and 2s and loomies and tus。

 those are all ints and you can't add an int to a stir。That's easy to fix。

 although it's going to make our expression even uglier。

All we need to do is convert our ints to strings。When we try again。

 we find that we've forgotten one int， the result of get total。Running once more。

 we see that we're almost there， we just need one more space after the total number of dollars。

We'll add that space。 Run it。And it looks like we're done。But wow is this ugly？

We're going to introduce you to another string method that can help clean this mess up。

This method is called St dot format， it's not a special method， but it is pretty powerful。



![](img/35789e86ecd9d8acf8672571de5b9244_9.png)

We're going to go take a look again at this output that we have in our doc test where we have cash register and a cold and so on。

 and it would be nice to be able to base our return value。

 our string on the format that we have here。

![](img/35789e86ecd9d8acf8672571de5b9244_11.png)

And in fact， we can， let's copy this and paste it。In order to keep the line length short。

 we're going to deal with the cash register part separately from the numbers。

We also want to replace these numbers with placeholders that we're going to fill in later with whatever values we want。

These placeholders are integers indicating the order in which we're going to substitute values。

The substitution will be performed by method format。



![](img/35789e86ecd9d8acf8672571de5b9244_13.png)

This first placeholder should be replaced by the result of calling self。get total。

 x does the number of loonies， then tuies， fives。

![](img/35789e86ecd9d8acf8672571de5b9244_15.png)

Ts and twenties0s。I hope you can see how much easier this is to read as well as to write。

We can comment out what we had。And run it。And we see that we have exactly the output that we used to have。

 but in a much cleaner fashion。Special method stir is called whenever we print an object。

 call function stir on an object， or any other time that we need a human readable version of an object。



![](img/35789e86ecd9d8acf8672571de5b9244_17.png)