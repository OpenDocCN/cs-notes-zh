# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p158 38_04_08_equals方法实现.zh_en -BV18U411U729_p158-

![](img/aae6f09287a05211fbf9f2911beb2f7e_0.png)

We're going to see where it might be useful to write your own equals operator。

So we're going to be looking at word Gram Tester， which I have here。

And I have one method called test Word gra。And if you see here。

 we're just going to use sort of a simple string。 We have this string here that just is this is a test。

 this is a test， This is a test of words。 So we've got some repetition in there。

And what we're going to do with that long string is we're going to create some word grams of size4。

 and then we're just going to print them out。 So I'm going to just run this。So I'll create my object。

And run test word gram。And you can see we got several word grams。 They're all four letter words。

 And you can also notice that the one at index 0， the first one。

 this is a test is the same as the one at index 4 and also at index 8。

So that's just printing out the word grant。 So we go back to the code。

You can see that we go through and we just print out the index position。

 the length of the word gram and the word gram。 How do we do that Let's go look at the word gram class and you'll see in there it has a length method that's how it knows how to print out the length and for all of those it was four because there's four words。

And it also has a two string method， so it knows how to print out each word gra。

 and essentially what it's doing is it's going through and just printing out all the words in the word gram。

By building a string and printing out the string。So now I've also got。 we want。

 we want to focus on equals。 So I've also got this other method here called test word gram equals。

And let's see what that does。Again， we are generating word grams from the same string that we had before。

And this time， when we generate them， we're actually creating an array list of type word gram。

 and we're storing them in there instead of printing them。So you can see that in the first for loop。

Then what we're doing is we get the first word gram。

And we're going to compare it to all the other word grams to see if any of them are equal。

 And if you remember， the first one at index 0 and the one at index 4 and index 8 were all the same。

 This is a test。So let's see what happens。If we just run this。So it's already compiled。

So this time we're running test word gram equals。Oh， and you can see it only matched the first one。

And that one if you remember the very first one we we're getting here in our code。

 and then we're comparing it with the first one and then all the others。

 So it only matches the ones that are exactly the same。 They're actually the same object。

But it's not matching the other ones that have the same words in them。So let's see what we have here。

So we want to try and fix this。 So here again， here's our code。

You can see we're getting the first one。And then we're printing out checking。

 and then we go through the loop starting at0。 So we are checking the first one with itself。

 That's the mat one match we found。 and then。We compare first double equals with list。 get K。

And we only found one match， even though we should have found three matches。

So what we're going to do， let's first try to change this to something else。 Instead。

 let's try using the dot equals operator。 So if we say first dot equals。Let's see if that works。

 So instead instead of using the double equals， we're going to use the dot equals。

 So we'll compile it。 Let's see if that works better。And we run it， and we still only get one match。

 the first match， because they're the same object。 So what we'd like to do is we'd like to write our own equals operator。

So we're going to go back to the word gram class over here。And we're going to add a new method。

Equals operator is gonna be of type return type bullan。We're going to have to pass in object。Oh。

And we're going to create a word gram。Calling it other。And essentially， what we're doing is we're。

We will convert the object that we pass in so it lets it know that it's a word gra。So， we will cast。

Word Graham。Oh。Now， I'm just gonna make sure this works。 So I'm just gonna have it return trip。

And we'll make sure this works before we finish writing the equals method。

Becauseuse all this should do is it should always return true。 So let's see what happens。

 We should get all the matches。Yes， okay， so we compile it。And we come over here。And。

So now if we run it。

![](img/aae6f09287a05211fbf9f2911beb2f7e_2.png)

We get everything's a match because we just always return true。 that's not quite what we wanted。

 but at least we know that we are getting that equals operator。

Because before when we ran it without that equals operator in there， we only got one match。

 So we know the code we just put in there is forcing it to at least run the equals method that we just wrote。

 Allright， so now we need to develop it a little bit further。Okay。

 so the first thing we should probably do with word grams is make sure that if we're comparing to word grams。

 they have the same number of words in them。 So let's do that first。So， we'll check。

The length of the object， this。If that is not equal to。The other dot length。So again。

 we're passing in some word， other。 And we want to compare it to the actual object that it's comparing to。

 So we have。If the links are different， hey， we know right away， they're not equal。 So at that point。

 we want to return falses。Now， if they are the same。

 then what we need to do is we need to go through and compare word by word to make sure the first words in each are equal。

 the second words in each are equal and so on。 So we need a loop for that。

So we're gonna have to create a for loop。And then my word length is the length of an ingram。Okay。

 so we'll iterate through all the words in my words。

And we now we have an index position for each of those。

And then what we want to check is we want to check and see we compare the first two words if they don't match。

 we know right away the ingrams， the word grams aren't equal。So。We'll say， if it's not true。That。

 my words。Ki。😔，In the case position。Dot equals。So here we're using the dot equals for two strings。

And then， we want to know。The corresponding word in other， which is going to be at other dot。Word at。

 okay。So if that is not true， that means those two words do not match。Then we know again。

 that's fault and we can just return right away without checking any of the other words。

So we'll just say return faults again。And if we manage to get through checking all the words and we don't find any of them false。

 that means they all match， then we'll get to the bottom of our method and return true。

So let's try this out。Okay， so now we've got it compiling and let's see what happens when we run it。

And it worked't because it found the three matches that are identical at slot 0，4 and 8。

 So here's a case where sometimes you need to write your own equals operator and we wrote it。

 and we saw that it worked。 And that's pretty exciting。 Happy programming。😊。

