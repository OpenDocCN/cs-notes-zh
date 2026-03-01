# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p93 27_03_06_ArrayList的优势与问题.zh_en -BV18U411U729_p93-

![](img/543473c72978789fa404a8ad2b6a435e_0.png)

Hi， you've seen array list at work and how useful they are。 Arrays are extremely useful， too。

 So we're going to go through a quick walk through of code to show where arrayrays don't work so well。

😊，Creating an array is easier in terms of syntax than creating an array list。

 Far fewer characters to type， for example， It's much easier to access values in an array since a sub K can work to either read from an array location or write to the array location。

 given the index K。 In contrast， with array list。 you use dot get and dot set for reading and writing respectively。

With int values， arrays often have more benefits in some ways than array arrayists do。

Although most conversions between it and integer happen automatically， occasionally。

 these conversions can lead to hard to find bugs if you don't have a thorough understanding of how the itten and integer conversion works。

It's easy to increment the value in an array， given the index。However， in an array list。

 you have to call dot get and dot set since the code to simply increment the result returned by dot get does not work。



![](img/543473c72978789fa404a8ad2b6a435e_2.png)

However， arrays don't grow， and that's a really large concern。Let's write some code。

 Now we want to find the number of unique words in a file。

 but we want to use or at least try to use an array。So that's what we're going to do here。

I've started this program， the class is called words with Ars。

 and the first problem we run into is is we want to read in all the words from a file。

 but we don't know how many words there are in the file， so we don't know how big to make our array。

 so we can't really use an array for that。 so we'll use a storage resource for that part of the program so I've already started here。

 we've got my words which is a storage resource。We have。

Created the storage resource in our constructor。

![](img/543473c72978789fa404a8ad2b6a435e_4.png)

And then we have read words， which is going to read all the words from the file and put it into our storage resource。

 My words， note it's also going to add them in as lowercase。

 so all of the words have been lowercased。We have a method called containstains where we're going to pass in an array of type string and a word。

 and we want to know is that word in our array？So what what contains is going to do is it's going to look through the array and see if the word that we're passing in matches anything。

 and if it does， it returns true。If we go through the whole thing and we don't see it anywhere。

 we're going to return falses。Now， we have。Number of unique words。And the first thing we've done。Is。

We are going to create an array here to store all the words that are unique。

So you can see I've started that here， I've gone ahead in putting words as an array of type string。

 I have to create a new one， so I do that， and then I get to the part about the size and I don't know how big to make it。

So I don't know how many unique words they're going to be。

 So the only thing I can do is just make it as big as my storage resource。 So I made the size。

 my words that size。 That's the only safe thing to do because all the words could be unique。

Now we're going to iterate over my words， and we're going to check and see for each one。Is it in。

Words， which is going to be just the unique words。 So is it already in there， If it's not in there。

 we found a new unique word， and we're going to put it in there。So you can see here。On this line。

 we add it in， and then we're also keeping track of how many unique words we have because this method is going to return the number of unique words。

 And so every time we find a new unique word， we're going to add one。To that count。

The next thing we have is we have a tester method so we can test this out right down here。

 So we're just going to call it and test it out。 So let's compile this。's sorry。

 compiled it looks like。And so we'll go ahead and run it。We have to create our object。

And then we'll call the tester class。

![](img/543473c72978789fa404a8ad2b6a435e_6.png)

And we have to pick a file， so I'm going to pick Confucius。text。Oh dear。 We got an error。

So it says down here。We got a no pointer exception。Also over here。This is our output here。

 You can see that it did read in all the words from the file。 It says there was 34582 words read in。

 but you can see also it got a pointer exception and you can see where that exception is。

 it says in word in the tester on line 45。And then in number of unique words。

 there's a line for that and then contains on line 23。

 and so that top one is probably where the error is。 and if we click on that。

 it goes to where this error is highlighted here。

![](img/543473c72978789fa404a8ad2b6a435e_8.png)

And you can see our errors in contains。So what is the problem？Well， the problem is。

We're using this array to put all the unique words， but we don't have any in there yet。

And then we're actually iterating over the whole thing which is all empty， it's initialized to null。

 and so we're checking does a value that's null equal a word and that's why it crashed because you can't compare null to a string。

So。We need to fix this。So what we really want to do is we want to keep track of how many unique words we have in there。

 because we just want to check the unique words that are actually in there that we've actually put in there。

And so what we'll have to do in order to fix that。Is， first of all。

 we'll have to add another parameter。 So we know how many words we've actually put in there。

 So I'm going to add a parameter here。Called number。And we actually have to give it a type。

 so it's going to be an integer。It it number。And then when we iterate。

 we just want to iterate over the words we put in there。

 So we want to replace list at length instead of looking at the whole gigantic array。

We want to look at just the ones that are already in there。

 So number tells us how many are currently in there。Now we also have to fix where we call contains。

 which is down here。we have to put a value here。That value。 remember。

 we're keeping track of how many words we put in there that are unique words。

 That is the variable nu stored。 So we'll pass numb。Stored here。

Let's compile that and see if that works。We got no syntax errors。Let's try and run it。



![](img/543473c72978789fa404a8ad2b6a435e_10.png)

And it works。So you can see here we've had a lot of trouble trying to use an array。

 This problem really should use an array list， because here。

 what's happened is this is a file that has 34000 words， of which only the unique words are 6558。

 So that means the array we're using is a size 3400。But。😔，There's only 6500 unique words。

 so we have a lot of extra space。 That's another reason why an array list would be better for this problem。

All right， happy coding。

![](img/543473c72978789fa404a8ad2b6a435e_12.png)