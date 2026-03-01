# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p68 02_02_02_密码学简史.zh_en -BV18U411U729_p68-

![](img/5ae945cb38c86adb3bf73086177e5631_0.png)

Welcome back Today， you're going to learn a little bit about security。

 which will show the importance of the problems youre going to solve in this module。

 Suppose you want to buy something online。 You use your computer。

 which is connected to the internet so it can communicate with the servers at the online store from which you're making your purchases to complete your purchase。

 you put your credit card or other payment information into your computer。



![](img/5ae945cb38c86adb3bf73086177e5631_2.png)

When you purchase the items in your shopping cart， for example。

 your computer sends that information with your credit card information across the internet to the online store。

 But what if a thief is looking at the data going across the Internet。

 This thief might be able to intercept your credit card information and use it to make fraudulent purchases。

 You certainly don't want that and neither does the online store， it wants your business。

So what makes online shopping safe， What actually happens is that your computer encrypts the information before it sends it to the Web servers for the online store。

 The two computers agree on a special piece of data called the key， and then use。😊。



![](img/5ae945cb38c86adb3bf73086177e5631_4.png)

That with an encryption algorithm to transform the data so that only another computer with the key can decrypt the data。

 Now， your computer sends the encrypted data across the Internet and any potential thief is thwarted。

 The thief can only see the encrypted data and cannot understand what the message says the receiving computer。

 which has the key can then decrypt the data and understand the original message。

 When you are doing anything online， your web browser will tell you if you have a secure connection。

 For example， Chrome displays the H TTPS in green and shows a green lock icon next to it。

 The S in H TTPS is forec。It's a different kind of connection to a web server than the standard HTTP。

If you were to click on the lock icon， it would tell you the technical details of the encryption used to secure the connection。

 There are many algorithms involved in securing your Internet connection。

 an algorithm called Aes is typically used to encrypt the data that is sent to the server once the connection is set up。

 However， your computer and the server must agree on the key in a secure fashion before any information can be sent。

 While this may sound quite difficult。 there are algorithms that can make this happen。

 In this example， my computer used to two algorithms to securely set up the connection with the server。

 One called elliptic curve diiffy Heman and one called RSA。

 These algorithms are very important to secure to the secure operation of the Internet。

 but the math involved is a bit advanced to go into here。 to implement these encryption algorithms。

 you would need to spend several days or months just learning that math。

 which is not the focus of this course。 If you are interested in advanced cryptography。

 Coursera has some excellent courses on the subject。



![](img/5ae945cb38c86adb3bf73086177e5631_6.png)

Which you could take after you've mastered basic programming。

Even though modern cryptography requires some advanced math， you can however。

 learn a lot about cryptography by looking to the past classical cryptography。

 the cryptographic algorithms used in past centuries involve simple mathematics and even predate computers。

 These algorithms are not secure today， they can be easily cracked by computers。

 but learning how they work and implementing them will teach you some important lessons。 Furthermore。

 learning how to break them will teach you a critical lesson。

 do not try to make up your own cryptographic scheme。

 If you need security use a well testedested implementation of a modern cryptographic library。

So how far into history will we need to look to find the first use of cryptography？

The first known use of something resembling cryptography comes from ancient Egypt 4000 years ago。

 however， historians believe that the hiding of messages was not a serious attempt to guard secrets。

If you look forward a few hundred years to Mesopotamia around。1500 BCE。

 you will find records of craftsmen using simple encryption schemes to guard their secrets when they recorded them on stone tablets。



![](img/5ae945cb38c86adb3bf73086177e5631_8.png)

Going further forward to the Roman Empire， the Caesar cipher。

 which you will learn about in the rest of this module， is named after Julius Caesar。

 who used it extensively。Looking forward another 1，500 years， you will find the visionre cipher。

Goon Baista Belllosa actually described this algorithm in 1553。

 but it is named after Blazes visionire in the 19th century。

 This algorithm is historically very important， as it was long regarded as unbreakable。 However。

 in the mini project， you are going to write a program to break it。Continuing forward to the 1940s。

 cryptography was a critical part of World War Ii。 The allies devoted significant resources to breaking the German codes with the core of that effort taking place at Bletchley Park in England。

 Alan Turing was a leader in this code breaking effort and made many important contributions to computer science。

 In fact， he is so important that the highest honor in computer science is called the Turing Award。

 So now that you know a bit about cryptographic history。 What will you be doing。😊，In this module。

 you're going to learn about the Caesar cipher， you will implement it and then break it。

In the mini project at the end of this course， you're going to learn about the visionre cipher and will also implement it and break it。

 Of course， all of these problems are going to teach you several important skills that can help you solve a wide variety of other problems。

