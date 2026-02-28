# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p82 16_02_06_总结_1.zh_en -BV18U411U729_p82-

![](img/a73e05cd81f46a844a172e58a2c8d6f9_0.png)

Hello， in this module， you learned about arrays and how to use arrays to crack a Caar cipher。

 you'll continue to solve problems using arrays。 they're a powerful programming tool。



![](img/a73e05cd81f46a844a172e58a2c8d6f9_2.png)

Arays are indexed collections in Java use brackets to indicate an array variable。

 and arrays can store strings or ins or even storage resources。

 Almost anything can be stored in an array。

![](img/a73e05cd81f46a844a172e58a2c8d6f9_4.png)

The power of an array is that one variable name can represent two10 or a million different values。

 and each value can be accessed separately from the others。



![](img/a73e05cd81f46a844a172e58a2c8d6f9_6.png)

![](img/a73e05cd81f46a844a172e58a2c8d6f9_7.png)

This access is done by a numeric index， a value that starts at 0 for the first element in the array。

 just like you did with strings。Just as a group of mail or post boxes can be found quickly using a number。

 accessing an array element by its numeric index helps in storing and accessing values。

Here's a quick overview of how arrays work in Java In Java， arrays are created using new。

 and once an array has been created， its size does not change。 However。

 the values stored in each indexed array cell can change。

 And that's what makes arrays useful and powerful。 arrayrays are created using new and brackets are used both to indicate that a variable like names is an array of strings。

 And as part of the syntax in new to specify the number of items in the array。



![](img/a73e05cd81f46a844a172e58a2c8d6f9_9.png)

![](img/a73e05cd81f46a844a172e58a2c8d6f9_10.png)

![](img/a73e05cd81f46a844a172e58a2c8d6f9_11.png)

![](img/a73e05cd81f46a844a172e58a2c8d6f9_12.png)

![](img/a73e05cd81f46a844a172e58a2c8d6f9_13.png)

You can define arrays of int values in Java just as you can define arrays of string values。

Int values in an array are initialized to 0， string and other object values are initialized to null。



![](img/a73e05cd81f46a844a172e58a2c8d6f9_15.png)

![](img/a73e05cd81f46a844a172e58a2c8d6f9_16.png)

You can assign values to an array using an index。And you can access an array to update the contents as well。



![](img/a73e05cd81f46a844a172e58a2c8d6f9_18.png)

You've used indices to access array elements， and loops are typically used to access all the elements in an array。



![](img/a73e05cd81f46a844a172e58a2c8d6f9_20.png)

Here's a loop that starts at the first index0 and loops through the last valid index。

 which is one less than the length of the array list。

 This is typical code that loops over array elements。



![](img/a73e05cd81f46a844a172e58a2c8d6f9_22.png)

![](img/a73e05cd81f46a844a172e58a2c8d6f9_23.png)

![](img/a73e05cd81f46a844a172e58a2c8d6f9_24.png)

In the loop body， the loop control variable is usually used to access each element in the array。



![](img/a73e05cd81f46a844a172e58a2c8d6f9_26.png)

In this loop， the value of k is used to indicate the index at which a word is found in the array parameter list。



![](img/a73e05cd81f46a844a172e58a2c8d6f9_28.png)

In general， this pattern of looping over all elements using indices is very common in solving problems using arrays。

 We used arrays to solve several problems， including cracking code。



![](img/a73e05cd81f46a844a172e58a2c8d6f9_30.png)

![](img/a73e05cd81f46a844a172e58a2c8d6f9_31.png)

![](img/a73e05cd81f46a844a172e58a2c8d6f9_32.png)

You saw how arrays were used in cracking the Caesar cipher method of encrypting messages。



![](img/a73e05cd81f46a844a172e58a2c8d6f9_34.png)

Using frequencies obtained from the message by using indexing and arrays made it possible to crack a Caesar cipher。



![](img/a73e05cd81f46a844a172e58a2c8d6f9_36.png)

Indexing was also used in both encrypting and decrypting， as well as in cracking the code。

It's good to know that the encryption used on the internet to protect your transactions is far more secure than the Caesar cipher。

 Scientists and mathematicians don't think that today's internet encryption can be hacked or cracked using brute force or even smart algorithms。

😊，But you should be careful online with your personal information in any case。

