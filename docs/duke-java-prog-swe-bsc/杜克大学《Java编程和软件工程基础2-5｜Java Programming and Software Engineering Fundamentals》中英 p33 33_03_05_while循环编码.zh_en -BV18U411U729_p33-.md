# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p33 33_03_05_while循环编码.zh_en -BV18U411U729_p33-

![](img/a92070253f2c18c621e84f9c967acf9f_0.png)

Okay， now you've learned about while loops and are ready to turn this algorithm into code。

 which will search for a TA， which is3， a multiple of three away from the AG。

 even if there are other Ts in between， which are pieces of two different co on stuck together。

 So here's the algorithm that we came up with。 And now we're ready to turn it into code。

Our first step is to find the first occurrence of ATG。And call its index start index。

 So as you're hopefully becoming familiar with by now。

 we're going to say int start index equals DNA do index of。ATG。

 because that's going to find us the first index of AG。

Our second step says find the TAA starting from start index plus 3 and call this resultcur index。

 I'm going to say int。

![](img/a92070253f2c18c621e84f9c967acf9f_2.png)

Kurt index equals DNA。t index of and we're looking for T AA。

 and we want to start from start index plus 3。 This should also be becoming hopefully familiar to you with index of starting from a position。

Now we're going to say as long as cur index is not equal to negative1。

 this is what you've just learned is a while loop， I want to repeat some steps as long as some condition is true so while Cur index is not equal to negative one。

 I want to do these steps here and I'm going to go ahead and put I've in my steps to match the grouping that was in our algorithm in the slides and I'm going to just go ahead and put the curly brace here so I won't get confused。

Later。All right， and so what do we want to do as long as currentinex is negative  one？

Or is not negative 1。 We want to check if current index minus start index is a multiple of three。

 You've seen how to do this previously， where we can subtract。Curt index， minus start index。

Take that mod 3 and see if it's equal to0。And we said， if so， we want to do one thing and if not。

 we want to do another thing， and as you've probably gotten familiar with by now。

 if not is going to be else， we want to do some other thing in this case。So if so。

The text between start index and Cur index plus3 is your answer。

 so anytime a method knows its answer right away and is done。

 we're going to return that answer back to who called us。

 which finishes the method and gives back the answer so we want return and we want the text between start index and Cur index plus3。

What method would you use for this？Hopefully， you've become familiar enough with string methods by now that substring is is what comes to mind is what you'd want。

 So DNA dot substring， start index。C index， plus 3。And then we said， if not。

 update cur index to the index of the next TA starting from cur index plus1。

 So anytime we want to update a variable， we're going to use an assignment statement and we can find the next one after that again。

 using index of to search from a specific position index of。T A a from Kt index。Plus one right。

 so that just wrote that that step down as it was。Ebrace is not intendeded right。

 So I'm just going to fix that。 And then if we get to the end of this loop。

 if we keep going and current index is negative one， meaning we couldn't find any more T As。

Then our answer is going to be。The empty string。All right， so I'm going to save that。

I'm going to go over here， and I'm going to hit compile。And it saysRe into file while parsing。

And oops， I messed up in here somewhere I'd written some test cases before we started。

 you'll notice that it's highlighting this curly brace and if I scroll up。

 it's highlighting this curly brace， when I wrote these test cases。

 I forgot to put the curly brace that ends the method。Fix that really quickly。Compilile it。

And find Jean simple， yeah I copied and pasted this testing code。

And changed the method name and didn't change that。So we'll fix a couple careless mistakes there。

This is the danger of copying and pasting， you should never do it。Now， really， it will compile。

 alright， so I'm going to make one of these。And you'll notice here that I've written。

A little test method like we've had in the previous ones since things are getting a little more complicated with our test cases。

 I've put these comments here just to mark where the codons are so this AG is one codon and then I've just marked here that this CTG is another codon and so we can see that this TAA here for example is a whole codon and this TAA here is not a whole codon so we would expect this method to find。

This gene right here。And similarly， for these other ones。

 So I'm just going to run this method really quickly。Okay。And for this first one， what did we expect。

 we expected AGC， GT。A A T， T A A。AT G， C GT， A A T TAA。

 so we got exactly what we wanted and notice this is where that while loop we wrote just came in into use because。

This looks like a TAA， but we would have found that it wasn't a multiple of three and we would have kept going and found there actually is one later on。

 And then similarly， we've done this other string， which is a little bit longer。

 has some more things that look like maybe they're Ts but they're not but it does have a TAA at the end so we get that really long gene there and then at the end here if you look we don't actually have any Ts and we get the empty string which is what we'd want。



![](img/a92070253f2c18c621e84f9c967acf9f_4.png)

So there we go， we've turned this algorithm into code using a while loop。

 and now it will look for any TA， which is a multiple of three。

 not even if there's one that's earlier that's not a multiple of three away so that we can get the right answer。

