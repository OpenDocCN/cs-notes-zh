# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p36 36_03_08_三个终止密码子编码第二部分.zh_en -BV18U411U729_p36-

![](img/3e8e522ea188cf7b203688dffb538648_0.png)

This will be a very straightforward use of the abstract method findtop codon that I've already done。

 so I'll do this very quickly， find the first occurrence of AG。

 the start codon and store that in start index。Int start index gets。DNA dot index of。8。Zi。

If start index is negative 1， I'm done。 There's no start codon， so I can't find a gene。

 So if start index equals negative 1。Return negative 1， I did not， sorry， return the empty string。

That's what it says right here and this method returns a string。

 so I'm returning the empty string Now I'm going to store in TAA index the result of this method call。

 so I'm just going to copy and paste this method call， even though as you've learned。

 copy and paste does not always work as you intended。So store in TAA index。That method call。

And then I'm going to store in TAG index。The same thing， but it says use TAG。

And then I'm going to store in TGA indexex。That call with TGA。

 I'm looking to make sure that my copy and pastes worked properly because copy and paste can sometimes be your friend。

 but sometimes it can get you into trouble。So I've done that， I've used TAA In， TAG In。

 and TGA index， I've got all those variables。The next comment says store in Min index。

 the smallest of these three values， so I have to find the smallest of all these values。

And one way to find the smallest value is to use the min function in the math library。

 so I can say int min index。Gets mathth。t min of TAA indexex and TAG indexex。

That's the smallest of these two。Maybe I call that temp。And then， I'll store in。Min index。

The minimum。Of temp， which is the first two and the last one， which is TGA index。

 Let me go over that again。I've found the minimum of TAA index and TAG index， that's these two。

And then I found the minimum of that value， which is the smallest of two and my last index TGA index。

 and it says if this is DNA dot length， I return the empty string， so if。

Min index is equal to DNA dot length。Return the empty string。Otherwise。

 the answer is the text from start index to Min index plus3， and as you saw before。

 that uses the DNA substring method from start index。To min index plus3。

I'm going to make sure I've got that right。Compile。Cannot find symbol mint index。

And that's because I spelled that wrong there。Now compiled in no syntax errors just compiling doesn't mean my code works。

 I really need to test it， so we'll leave it to you to test this just as I found a test method here。

 you could write a test method to test these it'd be very similar to the one that you saw in the previous video。

 but I could use TAA and TAG and TGA Once that test method is done。

 I'll be confident that my method work correctly。One final thing。

 this use of math dot min to store in temp and to store in Min index just to。Let you see。

 it would be possible to do that on one line。 I could say math dot min of。

TAA index and Math dot min of TAG index and TGA index it's possible to chain the occurrences of Min index together like that。

 I'll leave that as a comment so you can look at it and think about it。



![](img/3e8e522ea188cf7b203688dffb538648_2.png)

![](img/3e8e522ea188cf7b203688dffb538648_3.png)

And that's it for coding with DNA and three different stop codons。Have fun。😊。

