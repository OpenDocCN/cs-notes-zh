# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p34 34_03_06_三个终止密码子.zh_en -BV18U411U729_p34-

![](img/4bd6b0e18e0cce94c3ea37dccaf0221a_0.png)

All right， so far you have developed an algorithm that would find these start and stop codons。

 figure out that the length is a multiple of three and return the DNA string for this gene。

Now it is time to add another layer of realism and thus complexity。

 there are actually three different stop codons， TAA， TGA and TG。

 so far your algorithm has only looked for TAA， but now it is time to make it look for the first one of any of these three stop codons that is a multiple of three away from the start codon count。

So which one of these stop codons is the one you want？

Well the first TGA is not a multiple3 from the start codon， so that isn't the one you want。

 The second TGA is also not a multiple of three from the start， so you don't want that either。

 That leaves you with TAG and TAA， which are both multiples of3 away。

 you want the one that comes first In this case， the TAG codon at index 12。



![](img/4bd6b0e18e0cce94c3ea37dccaf0221a_2.png)

Okay， so now you know what the problem is， let's solve it。To do this。

 let's go back to our algorithm that we have from before。

 the only thing that was specific to looking for TAA was these two occurrences of TAA in steps 3 and7。

 Could we start from this algorithm and have most of our work done for us？

The best way to do this is to split the problem up。

 We want to abstract out the part that searches for a stop codon into its own method。

We'll call it find stop codon。And it will take the DNA string to search in the index to start from and the particular stop codon strings such as TA TGA or T G to search for the algorithm will need a few changes such as returning the index instead of the text and looking for any of the three stop codons。

 not just TA。 However， the basic mechanics of the algorithm searching for a codon that is a multiple of three from the start remain the same。

 We'll come back to those changes in a minute。 for now we'll just assume we have a fine stop codon method that works。

Once we have extracted that out into its own function， we could use it to find the TAA Sco on。



![](img/4bd6b0e18e0cce94c3ea37dccaf0221a_4.png)

And call the method again to find the TAG stop codedon。Then one more time to find the TGA stop codon。

Note how this corresponds to what we did by hand， we identified the positions of the TAA。

 TAG and TGA stop codons， it is a bit different from our example by hand since P stop codon will only give us a position that is a multiple three away from start index。

 whereas we showed a TGA that was not a multiple three for the purposes of illustration。

Now that we have those three positions， we want the one that comes first。

 so we would just need to take the minimum of three values， which we will call min index。Finally。

 our answer is the substr from start index to Min index plus3。

Now let's look at what we need to do to the algorithm that we abstracted out inDe stop codon。First。

 these will no longer always be TAA。Instead， they will be the stop codon parameter。

 which tells us the particular stop codon we are looking for。

The other change is that we want to give back the index where we found the stop codon instead of the text between the start and stop codons。

Why our other algorithm needs these indices to compare。

 to figure out which one to use before it gets the text。

Whenever we find a valid stop co on in step four， we can just give current index as our answer。

However， what should we give back to represent no valid index found in step 6？

Negative one is often a good choice to indicate no valid index。

 but let's see how this would work with the way we are using the result of this function。

If we were to return negative1， we could make it work。

 but we would have to change this code to do more complex comparisons than just taking the minimum of these three values。

Youll see this approach later and learn a new concept in the process。But for now。

 let's make this work such that we can just take the minimum here。



![](img/4bd6b0e18e0cce94c3ea37dccaf0221a_6.png)

Instead， we can return the length of the DNA string since that is larger than any vent index。

Of course， now that we are doing that， we should explicitly check for the case where no valid stop codon was found。

If min index is the length of the DNA string， none of the three stop codons was found。Okay， great。

 now we have an algorithm， let's go turn this into code， Thank you。

