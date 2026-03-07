# 多伦多大学【中英⚡编程入门：编写高质量代码｜Learn to Program： Crafting Quality Code】 p03 P3 05_回文算法-2 -BV1QuJVzpEKE_p3-

![](img/3db39730f941b403dd6f66174001668f_0.png)

In this lecture， we'll implement our second algorithm for determining whether a string is a palindrome。



![](img/3db39730f941b403dd6f66174001668f_2.png)

As before， we start with the same results of following our design recipe as we did for the last lecture。

For our second algorithm， we split the string into two halves。 reverseverse the second half。

 and then compare that reversed second half to the first half。Again， we need to reverse a string。

 so let's go get that code from the previous version。As a quick reminder。

 if I have an even length string， then I'm going to divide this in half。

Reverse the second half and then compare it to the first half。

I'm going to write some indices at the top， 01。Two and three。

If I have an odd length string on the other hand。Such as race car。

My approach is to not include the E。And just reverse everything after the E that should give me R A C。

 which I then compare to。The first half。And again。I'm going to write the。Indices。

Of each letter above。The last example that we have is。Dentted。Split that in half。

Reverse the last half。And then unsuccessfully compare the reversed second half to our first half。

And now it's time to play with indices because we need to know exactly where we're going to slice each string。

The length of noon is four。4 divided by 2 is2， so that tells us the index to slice from for to get the second half of this strip。

 four divided by2。The length of race car is7。Seven divided by two。Well。

 if I just do straight division， then that gives me three and a half， but if I do。Integer division。

 then that gives me three。So three is the number of characters in each half。

 but I don't want to include the E there。 so I would I'm going to have to figure out how to work around this with my slicing。

 perhaps。I can take some links。And subtract。7 divided by 2，7 divided by 2 is 3。 Oops。

 I forgot a slash there。 Sorry，7-7 divided by 2。 That gives me 4。

 which is the first index of the character that I want。Now is that going to work over here？

4 minus4 integer division 2， well4 integer division 2 is 2， 4 minus2 is 2 and indeed。

That gives me the index that I need in order to start the slice to grab the second half of the string。

In general， then the length of the string divided by two。 that gives me the。

Number of characters for each slice。I can use this result as the last index in a slice then in order to grab the first half of the string。

And I can take the length of s minus this value。In order to find the index of the first character in the second half。

To grab。 So over here，7-7 divided by 2 gave me 4， and that is indeed the index over the first character in the second half that I want to reverse。

We're done thinking hard。We know that the first half that we want to grab is everything up to the length of S divided by two。

And we know that we want to grab everything from the length of S minus the length of S divided by2 for the second half。

And。That we want to reverse the second half。And check to see if it's equal to the first half。

That's a little bit convoluted because we have a whole bunch of repetitions of Le of S。

 So I am going to。Have one separate step where I grab that length。And。

Make it so that we only have to do that calculation once。

Think the code is a little bit clearer this way。 Your opinion may differ。

Getting rid of the scribbles。We're just going to add a couple of comments where so that other people who might be reading this code later can understand what we were doing and is。

Of characters in S， and。Here， what we're doing is we are comparing。The first half of us。

To the reverse of the second path。Because we so painfully figured out that we were omitting the middle character in an ob length string。

 let's actually mention that。All that's left now is for us to test。Tryune。And looks good so far。

 How about race car。 yep， that's also good。 And last。Enend it。Good， were done。



![](img/3db39730f941b403dd6f66174001668f_4.png)