# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p77 11_02_01_简介_1.zh_en -BV18U411U729_p77-

![](img/b4cb63ea863be5f65fb2751a63861a0d_0.png)

Hi， I'm Jeff Forbes， a computer science professor at Duke University and a friend of Susan， Owen。

 Robert and Drew。I do research in computer science education and learning analytics。

 but I also teach the data structures and algorithms course using Java。

I'm really excited to be able to give a guest lecture about using arrays to break or crack a Caar cipher。

 a method of encryption I know you've been studying。😊。

You or someone else hasn't implemented a program to encrypt text using a Caesar cipher。

This is a very basic and historically interesting form of descriptionryption。

 though it's not secure given patience or access to a computer in your skills at programming。

The concepts in cracking the cipher are useful in solving other problems too。

A key is used to encrypt to shift all letters in a message。But how do we decrypt？

We know that decryption must be possible since the intended recipient must be able to decrypt and read the encrypted message being sent。



![](img/b4cb63ea863be5f65fb2751a63861a0d_2.png)

Because a shift of 26 is the same as a shift of zero。Encrypting with the shift of 7。

 followed by decrypting with the shift of 19， will result in the original message。

 just like a shift of 26。How does knowing this help us crack a cipher？

A thief or hacker could find the key， which is a number。Keys are often numbers。

 both in the Caesar cipher and many other forms of encryption。

The hacker simply subtracts from 26 and will be able to decrypt the message。

If the hacker or thief doesn't have the key， is it possible to use brute force or some other way to crack the cipher？

Broooot force means trying every possible key with a human helping。

 using brute force with a Caesar cipher makes it relatively easy to decrypt the message。



![](img/b4cb63ea863be5f65fb2751a63861a0d_4.png)

![](img/b4cb63ea863be5f65fb2751a63861a0d_5.png)

Suppose we intercept this message， which is too difficult to pronounce。

Can we tell what this message says simply by looking at it， that seems unlikely。



![](img/b4cb63ea863be5f65fb2751a63861a0d_7.png)

If we know the key used to encrypt this message， we could easily decrypt it。



![](img/b4cb63ea863be5f65fb2751a63861a0d_9.png)

But how many keys are there， perhaps we can simply try them all。

 that's what a brute forest approach is。The basic idea is to try every key。



![](img/b4cb63ea863be5f65fb2751a63861a0d_11.png)

We already have the code to encrypt the message。We'll use every key from 1 to 26 or 25 to encrypt the message we're trying to decrypt。

Since the decryption shift is just 26 minus the original encryption shift， if we try all 26 shifts。

 we'll find the original message。We can try every key using this brute force approach because the number of keys is small and trying each key is fast。

 the same approach won't work for other forms of encryption because there might be too many keys。

It's also possible that using。Each key to encrypt could take a long time。

Before we talk about an approach that's more sophisticated than brute force。

 let's work to understand brute force in what we call eyeball decryption。

Our goal is to unlock or decrypt an encrypted message。



![](img/b4cb63ea863be5f65fb2751a63861a0d_13.png)

We don't have the key used to decrypt， we're not that fortunate。



![](img/b4cb63ea863be5f65fb2751a63861a0d_15.png)

However， we do have the key use to encrypt from the class Caesar cipher。

 using that we can try all 26 keys。To decrypt using a human or eyeball approach we'll create a Caar cipher object。

We'll try all 26 keys from 0 to 25。We'll use our Caesar cipher object named cipher to shift the message。

With each of the 26 keys。Then we'll print the result of the shift。As we'll see。

 we can decrypt the message if we recognize words。How do we find the original message When we run the code we just discussed。

 we'll be able to view or eyeball the result of encrypting 26 times。😊。



![](img/b4cb63ea863be5f65fb2751a63861a0d_17.png)

We'll scan all 26 strings produced by 26 different keys and we'll do this methodically。

As we eyeball each string， we look carefully to see if the string is recognizable as English。

 since we're looking for an English language message。This line isn't recognizable。

This line doesn't look like English， but let's look closely。No， it's not English。

We'll look at the next line。Let's examine this line closely。

This line is easily recognized as English text， and we see that encryption and security are fundamental parts of today's internet。

