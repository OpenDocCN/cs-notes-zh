# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p81 15_02_05_算法开发.zh_en -BV18U411U729_p81-

![](img/6c357a0f98e3384c9e672503a656c0e8_0.png)

We'd like to automate the cracking or breaking of the Caar cipher to do this。

 we rely on frequencies of letters in English text。



![](img/6c357a0f98e3384c9e672503a656c0e8_2.png)

If you're encrypting a message in another language。

 you'll need to use the frequencies from that language， but the approach will be the same。

We'll write code to find the character that occurs most frequently in the message being decrypted。

We'll assume this is the letter E， since E occurs more frequently than any other letter in English text in Russian。

 for example， the letter O occurs more frequently than E。 If our assumption about E is wrong。

 we won't decrypt the original message。It's possible to use more than just E。

 but to rely on the frequencies of all the letters and use statistical approaches to break the Ca cipher in some cases。

 these approaches will break other encryption methods。

Though not the methods used to encrypt data for online shopping and secure transactions。



![](img/6c357a0f98e3384c9e672503a656c0e8_4.png)

Let's look at the code for decryption in two steps。

 We need to count the occurrences of each letter A through Z in the message we're encrypting。

We'll have code to scan each letter of the text， an incrent calendar for each of the 26 different letters。

Initially， all the counters are zero since we haven't started scanning the text letter by letter。

Each counter is numbered from 0 to 25 because the counters are array elements。



![](img/6c357a0f98e3384c9e672503a656c0e8_6.png)

The index from a string of 26 letters will help us find the right index for the counter will increment as we scan the text。

As we scan the message， looking at each character will increment the counter at index 7 for H。

Then as we scan I we'll increment the counter index 8。

 which is the index of I in our alphabet string。We won't increment for the comma。Or for the space。

 then we'll increment the counter at index 3 for the D。The counter at indexX 14 for the O。

We won't incomement for the space because space doesn't occur in the alphabet。

Then we'll increment the counter at index 24 for y。

And we'll set the counter at index 14 to 2 when we scan the second O in the message。When we're done。

 scanning every character will have these values for each counter。

 If you look carefully at these values， you see that our decryption method is likely to fail。

 The value of the counter with index 4 is 0。 There are no easiness message。

 but this is a very unusual message。Now we'll look at the code for this idea。



![](img/6c357a0f98e3384c9e672503a656c0e8_8.png)

We scan the message character by character using a standard for loop。



![](img/6c357a0f98e3384c9e672503a656c0e8_10.png)

We find where the character occurs in a string of each letter in the alphabet so that E will be found at index 4。

 notice that we converted the characters in the message being decrypted to a lower case。

We use the index in the alphabet to increment the corresponding encounter as part of decrypting the message。

If the character wasn't in the letters of the alphabet。

 the dot index of method returned negative one， and we don't increment any counter。

The code that uses the idea of E occurring most frequently is straightforward developed from the ideas。

 algorithm， and code you just see。

![](img/6c357a0f98e3384c9e672503a656c0e8_12.png)

As you can see， the code isn't very long， that we've created two helper methods and relied on this CSesar cipher class to help。

We've called a method count letters， which we just discussed。

 this method will count the occurrences of every character in the string encrypted with A being stored in the first or index0 location of the array。

Returned by the function and referenced here by the variable freaks。



![](img/6c357a0f98e3384c9e672503a656c0e8_14.png)

Then we call a method match index， which will return the index of their entry in freaks。

 That is the largest。 The location we will assume is where the E was shifted。

We'll find a distance from this location to E， E has index 4 since we start with0 for a and then get B。

 D， E41，2，3，4 respectively。If the maximal index is less than4。

 we'll need to wrap around from 26 to find the shift used for E。

If the value D key was used to encrypt， then 26 minus D key is used to decrypt and we return to decrypted string。

You'll be ready to use your programming knowledge to finish the task of decrypting and then apply this knowledge in the mini project with a different cipher。

 but there are some details we want to highlight。

![](img/6c357a0f98e3384c9e672503a656c0e8_16.png)

The array freaks in the code we just saw has a relationship between the index and the value in the array。

 For example， freaks of 8 is how often。I occurs since I is the ninth letter and has index 8。

 Remember， we start with index 0。

![](img/6c357a0f98e3384c9e672503a656c0e8_18.png)

When looking for a maximumimal value， as with the method max index that we call it and whose implementation you see here。

We return the index of the largest value， not the largest value itself。

 We use the index to find the distance from E。Using the existing Caar cipher class made decryption much more straightforward。

In general， it is a good idea to use code that has already been developed and tested rather than reinventing it half fun coding。

