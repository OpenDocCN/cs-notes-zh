# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p24 24_03_05_万物皆数字.zh_en -BV1Kp42117vh_p24-

![](img/7c949512248f036d89fba66d72ac0cfb_0.png)

You just read about how everything is a number， but let's see how this principle applies to some things that may not seem like numbers at first Gr glance。

Strings are numbers。You have seen literal sequences of characters before， such as hellello world。

 But did you think about how the computer stores them as numbers。

 Each character occupies some of the computer's memory。

 We'll talk about exactly how much later so you can think of each character conceptually in a box。

In terms of hardware， though， the computer stores each character as a number。

 You can look up the decimal or hexadecial values of different characters in an ASI table。

 And you can see the decimal values of these particular characters here。 Of course。

 the computer stores them as binary numbers。 One fun consequence of computer storing letters as numbers is that we can do math on them。

 This principle underlies most modern methods of cryptography。

Another thing that may not seem to be a number at first is an image like this one of some flowers。

 This image is made up of about a million pixels。Which each numerically represent the colors in the image to see these pixels。

 let's zoom in on this small section of the image Here。

 you can see the image magnified several times。 You can see how this image looks blocky or pixelated。

 This is what the image actually looks like if you could look that closely。

Note that if you try this yourself， you might end up with something that looks much smoother like this。

 Most image software will apply algorithms to smooth out the pixelation When you enlarge an image。

 You have to turn that off to see the original pixels。

Let us return to our enlarged image that shows the original pixels more clearly。

If we look only at a subset of this image and blow it up even further。

 we can see and talk about the individual pixels more easily。

 Here are 16 pixels from the original image， which had about a million pixels just to give you an idea of how much we have zoomed in now。

This dark purple pixel has a red value of 55， a green value of 27， and a blue value of 75。Meanwhile。

 this golden pixel has drastically different RGB values， 166， 136 and 41。

 giving it an entirely different color。Sound is another important thing that computers process。

 As I'm talking， you can see the waveforms of what I'm saying。

 The computer encodes these as numbers and sends them to the sound hardware。

 which uses them to determine how to move the speaker generating the desired sound。

 There are many other types of data you might want to represent in Comp on。

 You'll learn about data that is formed from sequences in course 3。 For now。

 you're going to learn aboutstructs and type defs。

![](img/7c949512248f036d89fba66d72ac0cfb_2.png)