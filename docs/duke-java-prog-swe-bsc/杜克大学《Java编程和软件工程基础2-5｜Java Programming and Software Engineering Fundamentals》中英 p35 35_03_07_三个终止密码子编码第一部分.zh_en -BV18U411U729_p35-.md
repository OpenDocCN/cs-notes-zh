# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p35 35_03_07_三个终止密码子编码第一部分.zh_en -BV18U411U729_p35-

![](img/faea899848111260c37ede4eca922242_0.png)

Hi， welcome to another version of gene Find。In today's episode。

 we're going to look for three different stop codons。In the previous coding exercises。

 you've seen code that found one stop code on， making sure it was a multiple three away from the start codedon。

In this version of the code that you've already seen described previously。

 we're going to look for three different stop codons。 as you can see here， we have TAA。

TA G and TGA and in order to find each of those， we're going to write another method。

 a method called find stop Co on that we saw outlined before with our seven step method。Up here。

 I've got this method， find stop codon， and it has three parameters， DNA stir。

 the string of DNA in which we're searching for a gene， start index。

 the location at which we're going to begin the search。And stop codon。

 the specific codon we're going to be looking for。We've got the code from our seven step process and what we're going to do here is write the code that goes along with this。

 You can see here， as we saw in the previous version of code。

 I'm going to create a variable cur index， and I'm going to make it the location of the first stop code on starting at start index plus3。

 So as we've seen before， the way we do that is create。An integer variable， curve index。

And we write current index gets the location in DNA stir。Of the stop codon。Starting at Start index。

That's exactly what it says here。 Find the stop code。

 Find the stop code on starting from start index plus 3。

 So I better make sure I'm moving that correctly and store that value in cur index。 Now。

 as long as current index is not equal to negative one。 And as you've already learned。

 that's a while loop。 So we're going to say， while cur index。Its not equal to negative one。

 and when I type the right curly brace， as you see here。

 I'm going to make sure I put in a left curly brace at the same time。Indented the same way。

 And one thing I can do there to make sure that I've got it right is to compile my program。

 So I'm compiling it。 You can see I've got no syntax errors。 So I know I'm on shape。 Now。

 as long as current index is not equal to negative one。 So Im I've just coded that。

 check to see if current index minus start index is a multiple of three。

I'm going to store that difference， I'm going to say int diF gets cur index minus start index。

 Now you don't need a new variable for that， as you saw in the previous video。

 you can just say if cur index minus start index mod 3 is equal to0。

 but this is sometimes easier conceptually to say if di mod 3 is equal to0。That means。

 and you can see I've already got my curly braces in there。Return current index。

 because it's my answer。 So I'm just going to say return cur index。 That's what it says here。

 Check if current index minus start index is a multiple of three。 And if so。

 current index is the answer。 returnturn it。 So I've got those two things taken care of。



![](img/faea899848111260c37ede4eca922242_2.png)

And it says， if not， update cur index。So if not， that would be else， and if you think carefully。

 you might see that although I don't need the else because I've already returned。

 but it's probably easier to write it that way in terms of thinking about it。

 it says updated cur index looking for stop codon again。

 starting from cur index plus1 so you can see up there how I looked for it so I'm going to do the same thing cur index gets DNAtir。

 index of I'm still looking for stop codon。And remember， that's a parameter to this method。

 and I'm starting。According to our comments at Cur index plus1， so Cur index plus one。And。

If we exit the loop， we didn't find the stop codedon， so we returned DNA stird dot length。

 you can see here that the loop is going to continue while current index is not equal to negative1。

If it is equal to negative 1， we've exhausted the string， the DNA strand in which we're searching。

 and so it says return DNA stir do length， as we'll see later。When we write this code。

 that's to ensure that when we find the minimum value that our code works properly。

So I'm going to make sure that my method looks right。Find the stop Codon。

And I started at index plus 3， so that's the last comment I have I'm going to get rid of that comment now。

So I've stored in cur index the location of stop code on while that's not negative one。

 if it's a multiple of three， I'm done， and if it's not， I need to keep searching。My class compiles。

 but just compiling doesn't indicate at all that I'm done。I've written some test code down here。

 test find Stop， and you can see as you saw in the previous coding video。

 I've created a strand of DNA and I'm going to look for TAA。Which is one of the stop codons。

 and I've got it in two different places。When I run the method， you'll see what it does。

 And then I'll describe how that testing works。 So here's my workbench。 I'm going to。

Right click on this and make a new object。It comes in the object workbench。

 I'm going to right click again， and I'm going to run test find stop。

And you can see it printed tests finished， that means all the tests work correctly because if there was an error。

 my print statements would have indicated that let's look at that testing code so you can see how I did that。

In testing fine stop， the first thing I did was look for the stop code on T AA starting at index 0。

 And you can see here I've got the indices printed above the string。 So TA here is at index 99-0 is。

 in fact， a multiple of 3。 So it should have returned 9 that it found T AA。 And if it wasn't 9。

 I got an error to see how it might work。If it returned the wrong thing。

 suppose I said if DX is not equal to 10。Now that would be a mistake because we know it returns nine and it's supposed to return nine。

 you'll see in this case when I run it。That it will print something。Right click to create the object。

Right click to invoke the find stops and you can see error on。



![](img/faea899848111260c37ede4eca922242_4.png)

Now， that wasn't an error because I had I knew I was supposed to get 9。

 All these tests print something if there was an error and if there's no error。

 they don't print anything。 My last print statement prints when the tests are finished。

 So what we have now is this method find stop codedon written。And tested。

And we're ready to move on to the next method， which was。

The same method that you saw before for finding just a single start stop co on。

 And now we're going to find。Any occurrence of a stop codon。

 any occurrence of three different stop cos， we're going to find TAA or TAG or TGA。

