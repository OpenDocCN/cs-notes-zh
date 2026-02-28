# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p80 14_02_04_使用数组计数.zh_en -BV18U411U729_p80-

What are the most common words in the English language。

There are many ways to find common words using search tools to find shared data that has been curated from thousands and thousands of available text helps here。

Others have already done such to figure out what the most common words are。 For example。

 they have determined that the word the is used more than any other word。



![](img/afcbdb4ccf9defd38bbd0097b6c6560b_1.png)

Did Shakespeare use common words， we can use our Edu。duke classes。

 public domain versions of Shakespeare's plays， and some simple array code to help answer this question。

In this example， we will examine several of Shakespeare's plays and count how many times he uses the most common words。

 All right， So I've started the code for counting the most common words in Shakespeare's plays。

 So here's the code。 Let's look at it。 I've got this method called count Shakespeare。

 And you can see here， actually， this is a new thing。 This shows you how you can initialize an array。

Right here can we've got the array plays， which is an array of strings。

And we can just put curly brackets and list the items in the array。

 And so what I've done here is I've listed six data files that we've gotten that have text from six of Caesars sorry。

6 of Shakespeare's place。We've also got another string array called common。

And there's a method called get common。 Let's go look at that and see what that does。

Here's Gett Common。And here you can see there's another data file。 This one's called common dot text。

 And that's where I've already put 20 common words。

 the most common words that somebody else has determined are the most common English words。

 We're just going to read that in。 And since I happen to know there's 20 words in there。

 that's important。 I can create the common string array of size 20。

Because arrays have to know the actual size。 So I'm reading that in， just reading in this loop here。

 All as it does is it goes through and just reads them in one at a time and puts them in there。

So we read in the 20 most common words that's all get common di。 Let's go back down here。

So we've got the plays， we've got the common words。

 and now we have a loop which is going to go over and it's going to read in each play。

 I've got the plays stored in a data folder so you can see I'm adding data slash right before the name of the play。

And then I'm going to call count words， which is going to count for each word in the play。

 whether if it is going to check and see if it's one of the common words， and if it is。

 it's going to count how many times each common word appears。

And then we just print a message that says， hey， we're done with the place。

Once we've counted all the common words， then we go through and we're going to print for each common words。

 for example， the， we're going to print the， and then how many times it occurs in all six of Shakespeare's place。

So let's go ahead and run this and see what happens。We'll compile it。It's compiled。

We will create an object。And we'll just go ahead and run it。Count Shakespeare。And you can see。

Doest work quite right？It's only counting of a lot。So let's go back and look at the code。

 It turns out I haven't given you all the code。 We still have to write one of the methods。Alright。

 so let's go see。 we are going to have to write。Index of。So what index of does。Is it takes。

A list of words。And a word。And we would like it to look for the word in the list of words。

Or the Arist awards。And see if it's in there。And count how many times it appears。

 or actually we want it to give you the location， the index of of where it appears in there。

So what we're going to have to do is we're going to have to loop over all the words in the array list and check to see if word is equal to one of them。

And if it is， we'll return the location of where it is。 So this。Let's， let's go ahead and start that。

All right， so we will start with a for loop。So in order to loop over the array。

 we'll need a four loop。 So let's say we'll need a variable and K。We'll start at 0。

And then as long as we don't go off the end of the array。 So we'll say K less than list dot length。

And then we need to update our counter K by one。Okay。

 so we'll go through and then what we need to do is for each case slot。

 we need to check and see if the word matches the word that's in that slot。So， we'll ask if。

What is the word in list K？And we need to compare it to words， so we'll use dot equals。

And if it equals it， we found it。So we can return the location of it。Return。Okay。

So this loop will go through and check to see this word equal this word， this word， this word。

 And if we find it in Sot K， we return K。 If we don't find it， we need to indicate we don't find it。

 So we need to fix this return。 That's after the for loop after we've looked at everything。

We'll change this to -1， which is not a position in the array。

 and that will indicate that we didn't find it。Now， let's see how indexo is being used。

We come over here。Inindex is being used in count words。Which is right here。And you can see here。

We call index of for each word， we're getting each word out of the file。

 we pass the common words and we pass the word， and then we check to see does it match。

 if it matches， then we're going to use the counts array， to update that count。

 so for the word the we'll keep track of how many times we find it every time we find it。

 we will update the counter counts which is in the same slot as the word the。

 which is in the common array。Alright， let's try and run this now。We'll compile it。No syntax ears。

 that's good。We'll come over here and we'll run it。So we're going to run count Shakespeare。

There we go。So。What this does。First of all， you can see I've got six data files， Caesar。text， A。text。

 Hamlet， like it， Macbeth and Romeo。And we've read all of those in。 and for each word in that file。

 we've checked to see if it matches one of these common words。

 Here you can see the common words are the of and and so on。

 And you can see that the appears in one of those or in the combination of those six texts。42。

4237 times。And then you can see another one，4 appears 1071， so you can see。

How many times each of these common words appear， So it looks like Shakespeare did use a lot of common words。

Now， how do we know this is actually correct？They're just big numbers。 How do we know。

 So what I'm going to do is I'm gonna gonna modify my program so I can run it on a really small file just to make sure and convince myself that I'm counting these numbers correctly。

So I will come back over here。And you can see here， I have this file called Small dot text。

 where I just put a few words in there。And what I want to do now is modify my code。

So that I look at this file small dot text。So back here in count Shakespeare。

What I'm going to do is I'm going to comment out this line here。These two lines。

 and I'm going to create my string plays just to be that one file。So， I will say。String。😔。

Plas is going to equal just the one file， which is smalled up text。That's all I have to do。

 and now I'm going to run it。And this time， it will just look at that one file。So let's compile it。

We got it compiled， we need to run it。And there we go。So， let's see。So if you look in small dot text。

 you can see the word the appears 1，2， three times。 If you look over here。

 you can see we counted the three times。 That looks good。Of appears twice。 We got two。

 and and appears twice。 We got a appears once a。 so it looks like it worked。 Now。

 I'm really more convinced that I counted the Shakespeare words correctly。



![](img/afcbdb4ccf9defd38bbd0097b6c6560b_3.png)

Alright， that's it， thanks。

![](img/afcbdb4ccf9defd38bbd0097b6c6560b_5.png)