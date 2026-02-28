# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p74 08_02_08_代码转换.zh_en -BV18U411U729_p74-

![](img/7ff72ac032647a4054edac10b5a34918_0.png)

Okay， now that you've developed the algorithm for Caesar cipher， it's time to turn it into code。

 We've started here with the Caesar cipher class， which has an encrypt method。

 which takes the input to encrypt and an integer for the key to use to encrypt it。

I've written here the comments with the pseudocode that we just developed in our algorithm。

 and I've gone ahead and written the first two lines of code。

The first step is to make a new string builder with the input and call it encrypted。

 and the second is to write down the alphabet， which is a string。

The next thing is to compute the shifted alphabet， so we're going to make a string。Shifted alphabet。

And remember， we saw in previous videos that we can use substr to do this。

 Alphabet dot substr key concatenated with。 That's what plus means for strings， alphabet。

About that dot sub string。0 comma key。 That will slice the alphabet up into two pieces and concatenate them back together to give us the shifted alphabet that we want。

Now we want to count from0 to being less than the length of encrypted。

 and we want a college number that we count I。 so this is going to be accounting for a loop for int I equals 0。

 I is less than encrypted dot length， the length of encrypted I plus plus。



![](img/7ff72ac032647a4054edac10b5a34918_2.png)

And what do we want to do， Well， we want to look at the IF character and call it cur cha cha cur cha equals encrypted dot。

Char at I。Then we want to find the index of curchar in the alphabet int。I D X， we said over here。

 call it ID X equals。Alphabet。Dot index of。Kirchhar。Then we want to see if that's in the alphabet。

 as you've seen before， index of will return negative1 if something is not there and some other number if it is。

 so it would not be there if IDX is index or is negative1。

We want not equal to negative one to mean it is there。Now we want the IDX cha of shifted alphabet。

And we want to call that new char。Quals shifted alphabet。Dotchar at。I X。

And now I want to replace the IF character of encrypted with new cha。 So encrypted。Set cha at。

And then I want the I character to be nu cha。That's everything I want to do inside sight of that。

 If otherwise do nothing， I don't need to write an al if I don't want to do anything otherwise。

This curly brace closes my counting for loop。 And at the end here， I said。I want my answer。

 so I want to return something to be the string inside of encrypted。 so encrypted dot2 string。

I'm going to compile that。It no syntax errors。And I've written here already this method test Caesar。

 which is going to make a new file resource， so it'll prompt us for a file。

 read it all in as a string encrypt it。 It will print out the encrypted message。

 and then it will also decrypted and print out the decrypted message because if we just saw a jumble of random characters。

 we wouldn't really be able to tell if we did it right。

 but being able to tell that we got the original back makes us more confident that what we did was correct。

I'm going to go over here。To Blue Jay， I'm going to say New Caesar cipher。I'm gonna say。Test Caesar。

And it's going to prompt me for a file and I have here this message in a file called message1。

text that says free cake in the conference room， maybe I want to send this to Robert without Owen seeing it and being able to get all the cake。

 and so I'm going to choose messages1。TxT and we can see the encrypted message here， WIVV， etcter。

 etc。It's it's been made more difficult to read and then we can see down here where it decrypted it correctly。

 so I'd be a little more confident in this I'd want to go through and check by hand that this actually came out with the correct key before I'd be completely certain that this test case worked correctly。



![](img/7ff72ac032647a4054edac10b5a34918_4.png)