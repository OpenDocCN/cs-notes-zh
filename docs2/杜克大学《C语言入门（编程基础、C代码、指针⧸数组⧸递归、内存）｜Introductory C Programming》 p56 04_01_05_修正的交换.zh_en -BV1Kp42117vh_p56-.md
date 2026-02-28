# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p56 04_01_05_修正的交换.zh_en -BV1Kp42117vh_p56-

![](img/a683655c3e924103bd91295447239353_0.png)

In this video， we're going to examine and step through a swap function that was written with pointers。

Previously， we looked at a swap function that was written without pointers that didn't actually work。

 This one does。 and it's been written slightly differently。 First， let's examine the differences。

 The first thing you'll notice is that swap takes two arguments。 X and y。

 which are pointers to integers。 You'll see here that we have written an int star than a space than an X。

 and an int star than a space and then a y。 You could also write it in the following way with the X right next to the star。

 Both of these are correct。 And you'll see both when you look at C code。😊，Now。

 x and Y are pointers to integers， so as we access the values of the integers that x and y point to in the code inside swap。

 we're going to have to dereence x and Y， and so that's why we'll see these stars in front of x and y throughout the code。

The final difference is how you call this function in the main， instead of passing in A and B。

 we now have to pass in the address of A and the address of B。So let's step through this function。

 We begin in the main。 We have a variable A and a variable B that have initial values 3 and 4。Now。

 when we call the swap function， instead of passing in 3 and 4。

 as we did in the previous version of this function。

 we now need to pass in the address of a and the address of B。

 So we're going to create variables X and Y， and X will point back to A， and Y will point back to B。

Let's step into the function。 We're going to mark the call site location1 and hop into the swap function。

Inside of swap， we're going to make a new variable called tempemp。

 and that's where we're going to temporarily store the value that x points to。

 which is the value of a， which is 3。Now we can take the value that y points to。

 which is the value of B or4 and store that in the value that x points to， namely the variable a。

Finally， we're going to take the temporary variable 3 and store that into the integer that y points to。

 which is the variable B。When we step out of the function， we see that our original variables。

 A and B， have indeed been swapped。So when we execute the print statement。

 we now have a equals 4 and B equals 3， which is what we were expecting to have from a correctly working swapped function。



![](img/a683655c3e924103bd91295447239353_2.png)