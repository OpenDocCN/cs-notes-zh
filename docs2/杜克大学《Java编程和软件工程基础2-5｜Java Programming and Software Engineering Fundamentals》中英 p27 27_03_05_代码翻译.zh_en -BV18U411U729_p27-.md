# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p27 27_03_05_代码翻译.zh_en -BV18U411U729_p27-

![](img/bb45b3ff54e854d76611602e51549238_0.png)

Hi， we're going to find a gene in a DNA strand， we're going to do a very simple algorithm in order to find our gene。

So I've started some code here， we have an algorithm fine gene method called fine gene simpleimple。

And we haven't done much with it yet， but what I've also done down here is I've written a couple of DNA strands that we will use to test the code that we write。

 so you can see here we have string DNA， we're going to print our DNA strand。

 we're going to call find gene simple， and then print out our gene and then I just have done this with four different strands of DNA。

So let's write the code now。So I've started by just saying the resulting gene is just going to be called a variable called result。

 and I've set it to null， the null string。And。If you remember from the video。

 we are going to look for the start codon in the strand of DNA and the start codon is AG。

 the string AG。So we can use the new string functions that we learned about。So I'm going to。

Start by creating a variable that will hold the index position of the start code on。

So we'll call it start index。And then we are going to look in the strand of DNA。

And we'll use the index of function to look for ATG。

And the indexo function is going to go through the string。

 and it's going to stop when it finds A T G， and it's going to return the index location of where it starts。

 So that'll be the starting position of our gene。We also have to look for the stop codon。

 and that is TAA。 so we're going to create a variable for that。Called stop index。

For the position of where the stop codon is， again， we will look in our DNA strand。

 DNA will use index of。But if you just look for TAA。

It will start at the beginning of the string and we want to look for the stop codon after the start codon so we know where the start codon is。

 it's in the variable start index and we want to start looking past that so you can add a second parameter to the index of function and so we will add that and say start looking where AG is。

 which is start index。Plus3， which is the length of ATG。

So now we have the start index and the stop index of where start index of ATG and the stop index of TAA。

 and now we want the strand that includes those two and everything in between it。

 so I'm going to call that our result。Again， we'll use a string function。

 so we'll use the string function called substring。

And the way substring works is you have to say I want a piece of a string and I want to start。

 where do we want to start， we want to start where ATG is， so we'll start at the start index。

And then the rest of our gene is going to be everything past ATG up until TAA。

 which is at the stop index。But we also want to include TAA， so we'll add three。

So that means take our substring from where ATG starts， go all the way to the stop index plus3。

 which is the first character after TAA， and the way substr works is it says start the first start index and then go all the way up to but not including the second parameter。

And then。Let's compile this and see if it works。Okay， so it compiles fine。So let's go over here。

And we'll create a new。fine gene。And now we'll run our test method that we wrote。And there it is。

 so we can see here's the first DNA strand and youd look for ATG， there it is。

 and then look for TAA and there's the T first TA that's after it。

 and you can see there's the gene that we found right here。And then the next example here's ATG。

 we look for TAA all the way here， and you can see here that's the gene we found。

Here's the third example， AG all the way to TAA， and you can see we got a big gene there。

 and then here's the last example， AG TAA， so that works good too。All right， but。

What happens if AG is not there？Or what happens if T AA is not there。 So let's look at our example。



![](img/bb45b3ff54e854d76611602e51549238_2.png)

Here， and let's change one of our strings。Let's change this string。We'll just save this one。

And let's change it too。A string that does not have ATG in it。

 let's see what happens if we run that example。

![](img/bb45b3ff54e854d76611602e51549238_4.png)

So we're going to come back over here。And we'll run our test find and。We got an error down here。

 You can see it says string index out of bounds exception minus1 string index out of range。

 What happened， Let's go look at our code。So we looked for ATG and we didn't find it and what the index of function does if it doesn't find the string you're looking for。

 it returns 1， so start index has the value minus1。

 and then we're trying to build a string starting at -1 and minus1 doesn't exist， so we got an error。

So what are we going to do， We need to fix this code。So let's check right after we ask for AG。

 let's put an if statement in there to check to make sure that ATG was there。

So we can ask if start index。Is equal to minus1。That means there is no AG。In that case。

We need to there is no gene。 There is no gene if there's no AG， there's no start。

 So what we'll do is we'll just return the empty string。

So we should compile this now and if we run it。this。So we'll create fine gene。

And then we'll run test find。And it ran， but there's no gene here。 that's because there's no AG。

 Let's try another example。We'll change our code again to give another example。

Let's just change this one here。Let's create a string where we have ATG， but we don't have TAA。

So we have the start code on， but not the stop codon。So I'll create a string， CG AG。G， T， T T A A A。

A gt。So there's no， oh， there is， let's get rid of it。Z。😔，There we go。 So now we have。

AT G right here and to the right of it， there is no TAA。So， let's。Compile。And we'll run it。

And you can see it's not there。There's no gene for this second one because ATG， but there's no TAA。



![](img/bb45b3ff54e854d76611602e51549238_6.png)

All right， so just like we。We put a check for if there's no E TG。

 We should do the same for if there's no stop code on。 So no T AA。 So let's add that code too。

We would add it right after we get the value for stop code on。So right here。

 we can check and see if stop。If the stop index。Equals -1。At that point。

 we know there's no stop co on。 and so there's no gene。 And so we can again。

 just return the empty string。Return。Empty string。So that's just a safe way。

 If there's no start code on or no stop code， unless's add a commentt here， this is the case for。No。

😔，TAA。We'll compile our code。And we'll just double check and make sure that works。

So it compiles and willll run it。And now we have our first string is good， we find a gene。

 our second string， there is no gene， we have an ATG， but we don't have a TAA。This string looks good。

This string has no AG and it actually does have a TAA but that doesn't matter because it has no ATG and so this gene there is no gene for that one either so anyway that is the way to find a simple gene in a strand of DNA we look for the start codon and then if there's a start codon we look past it for a stop codon and if we find both of those then we can return the start codon。

 the stop codon and everything in between it as the gene Thank you。



![](img/bb45b3ff54e854d76611602e51549238_8.png)