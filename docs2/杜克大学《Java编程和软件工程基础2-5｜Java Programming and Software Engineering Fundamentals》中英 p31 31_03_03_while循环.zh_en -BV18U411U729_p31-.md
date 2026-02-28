# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p31 31_03_03_while循环.zh_en -BV18U411U729_p31-

![](img/214b98a8b5f3d0af94253c162b9d56fc_0.png)

As you have been learning about strings， you have been improving on your algorithm to find genes in DNA。

 however， let us take a moment to think about what your algorithm will do on this string。

It will find the start code on ATG at index 0。Then it will find the stop code on TAA at index 8。

It will then check if the distance between them， which is8 is a multiple of three。

 because8 is not a multiple of three， your algorithm will conclude that this is not a valid gene between the ATG and TAA。

 there is one full codon ATC and two thirdds of another codon GC。

But if you were to keep looking past this TAA， you would find another TAA at index 15。

Now the distance between the ATG and TAA is 15， which is a multiple  three， so this is a valid gene。

The first TAA that we found was not actually a codon， but rather pieces of two adjacent codons。

 the T from GCT and the AA from an AAT， your next improvement to the gene finding algorithm is to add this functionality to make the algorithm keep looking until it finds a stop codon that is a multiple of three away from the start codon。

Having just worked that example， let us now do step two of the seven step process and write down what we just did。

The first thing we did was to the ATG。Then we found the first occurrence of TAA after the ATG。

 which was right here at indexex 8。

![](img/214b98a8b5f3d0af94253c162b9d56fc_2.png)

Then we checked if the distance between them was a multiple of three or not。In this case， it was not。

So we found the next TAA after this first one。 The second one is right here at indexex 15。

Then we checked if the distance between this TAA and the start codon was a multiple of three。It was。

 so all of the substring from 0 up to 18 was our answer。In this particular set of steps。

 we checked in two places to see if the distance was a multiple three。

If this works in the general case， you can just implement this algorithm with familiar if else statements。

 however。Do we always only need to check twice。Let's look at a different DNA string。

With this DNA string。We would need to check three times。

The first two TAAs are not a multiple three away from the start codon。But the third one is。

Would checking three times be enough？Could we have to check four times， 5， 10， 50 times？

This raises the question of how many times we have to check in general。

 and the answer is that we cannot pick a particular number of times。

 even if you wrote 50 if else statements， we could come up with a DNA string that has more than 50 TAs that are not a multiple three away from the start codon before finding a valid one。

Instead， we need to write our algorithm so that it repeats the checking however many times it needs to。



![](img/214b98a8b5f3d0af94253c162b9d56fc_4.png)

As you have seen before， repetition in your algorithm will turn into a loop when you translate the algorithm into code。

To express your algorithm with repetition， you will need to make the repetitive steps the same。And。

Figure out what to loop over。Previously， you have seen four loops which iterate over the elements in some iterable。

Such as pixels and an image。Now you're going to learn about a new kind of loop known as a wild loop。

Which lets you iterate as long as some condition holds。

Before we try to generalize these steps by finding repetition。

 let's be a bit more precise about what we did。We found the first ATG at index zero。

For the first T AA， we started looking at index 3 and found it at index 8。



![](img/214b98a8b5f3d0af94253c162b9d56fc_6.png)

Which Act 8 was a multiple of three。It wasn't。So we started looking at index 9 for the second TAA。

 and we found it at index 15。Which Act of 15 was a multiple of three。It was。

 so everything between was our answer。Now， let us take these steps and generalize them。

We looked for ATG here。Why was that？We always want to look for ATG because it is the start codon。

What about the fact that we found it at index0？We're not always going to find it at index 0。 However。

 we are going to want to use that information。 So let's give that a name。When we turn this into code。

What will be a variable that we will assign to this in this line and then use later？In particular。

 we'll call it Start index。What about looking for TAA？

We will always want to look for TAA since that is the stop co on。Will we always start at index3。

 probably not？Why don' we start at index3 here？We started there because it was right after the start codon that we found。

In the general case， this would be start index plus3。We won't always find it at index8 either。

 so let's give that a name too。We'll call it。Current index。

Let's also be a bit more specific about the distance between them。

 it is current index minus start index。Which happens in both of these steps。Next。

 you aren't always going to start looking from index 9。 but why do we start at 9 here。

If you look back at where we worked， the problem and wrote down our steps。

 we started at nine because the previous one started at eight。In our generalized algorithm。

 we named the previous location Cur index， so we can start from current index plus one。

We also should name the location where we found it。Should we give it a new name such as next index？

Or should we just update an existing name， such as Cur index？In this case。

 we want to update current In since that represents where we have found the most recent TAA。

If you did not realize this right away and gave it a different name。

 you would realize it later on as you try to make the steps uniform so that you can express the repetition。

Finally， we'll generalize the last step to just indicate that the text between them is the text from start index to current index plus3。

Now these steps look repetitive。The repetition may be a bit hard to see since it only happens twice。

 but if you wrote down the steps for a string with more TAAs that don't work。

 you would see that you do these steps over and over again。To make this repetitive。

 let's write it down like this。 Notice that steps 4，5 and 6 are what we will repeat。

 We've slightly adjusted the steps from before to reflect the choice we were making in step 4 and the two possible outcomes in steps 5 and 6。

 However， we have left the conditions under which we repeat these steps blank here。

How do we know when to stop repeating them？Also， what would you do after you stop repeating this loop？

We would stop if we run out of TAs， if that happened， current index would be minus1。

Which you know from having learned that you get -1 when you cannot find something in a string。

If you were to encounter this case， it would mean that there is no valid gene in the string。

So you should give an answer of the empty string。If you did not see this right off。

 what could you do to figure it out？You should work more examples until you understand the pattern。

Now your algorithm is generalized。But you'll need to learn about while loops before you can translate this into code。

Thank you。