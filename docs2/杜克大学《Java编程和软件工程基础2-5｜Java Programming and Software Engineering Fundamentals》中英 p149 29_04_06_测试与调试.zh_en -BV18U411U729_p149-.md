# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p149 29_04_06_测试与调试.zh_en -BV18U411U729_p149-

![](img/f328b24b763d704343d5560903c7c9dc_0.png)

Wait a minute。 I don't think his output is right。It's kind of hard to tell when it's random like that。

 But when he did mark off3 and it still looked like gibberish， I don't think that's right。

 If you think about it。We're using Markov3。 We've got three characters that should be together。

 and we're looking at a character that follows it。So we should have in our output。

 every group of four characters， every sub stringing of four characters。

Should be four characters from the actual training text， but that still looked a lot like gibbish。

 So I'm going to try and see if I can debug his program and see if there was a bug in it。

So here's his get random text method。 We're going to look at Markov 2， which is where he was。

 and it's doing one thing， or at least I'm looking at my code。

 and I think it's going to do one thing， but it's actually doing something else。

 So how do I figure that out， I'm going to have to print out some information。Now。

 I don't want to work with a big file， so I'm going to come back to Markov Runner。

And the first thing I'm going to do is just put in a small string。So I'll just set S T equal to。

This is a test。 Yes， a test。 So something really small。 And that'll just block out the file。

 even though we're going to load a file， we're just going to replace it immediately with this small string for testing。

And then in my Markov two class， what we're going to do is。We need to。

 let's print out the key and the follows that we're getting back to see if those are correct。

 So I'm going to add a print statement here。Let's say key。

And then we'll just put the so we'll print in the key。 and we're gonna print also beside it。

 the follows array。If we can spell it， right。Okay， so again。

 we have a small amount of data we're working with now。 So let me go back over here to Markov Runner。

And let's see。We'll make this smaller， too。And let's compile it。And let's see what happens now。

This is always helpful to figure out what your program's doing because you think it's doing one thing。

 but it might be doing something else。Now， we're gonna to load a data file。

 but then we're gonna ignore itcause we have that string。 So I have to load Romeo。



![](img/f328b24b763d704343d5560903c7c9dc_2.png)

Here we go。So I would did this so we could look at the follow set， but I'm looking at this and。

 oh my gosh。We're supposed to have a key that's two characters long。

 And you can see our key is only one character long。The first key is two characters。

 but all the rest are just one character， that is a problem。

Our character should be our key should always be two characters。

 so the way Markov works is you take your old key and then with Markov2。

 we want to start with we want to shift a little bit and use take off the first character and add the new follow character we used and use that to predict the next character。

 So let's look at our code。Here's get random text。So， you can see。

Here we set the key in this line here。Up here， we set the key， and it is two characters。

 That's the first key。 And where do we change the key， We change it down here。

 and we're just setting it to that next character。 So that's wrong。 What we want to do。

Is we want it to be the old key。Minus the first character， so we'll just start it at substr 1。

And then we'll tack on at the end the new character that we just found。

 We'll just shift it a little bit each time。 So let's try running that。We'll compile it。Okay。

 so we're going to run it now。Again， we're running it on our test data to see if that works。Here now。

 oh， yes。 And that looks much better。 And you can see we have all our keys are two digits。

 Some of them have a space in there。 So they look funny。 And then we have text。

 So now let's run it on a file。 Let's run it on Romeo now。😊。



![](img/f328b24b763d704343d5560903c7c9dc_4.png)

So we need to comment out what we just put in Markov2。

We're going to comment out the print statement here。This extra print statement。

 we don't need that now。Okay， that's good。 And then we'll come back over to Markov Runner and we'll ignore this extra small string we put in there so we can now run it on Romeo。

And we'll also change this back to 500。 We can look at a big thing now。

And let's compile it and run it。So we're going to select Romeo to run it on。



![](img/f328b24b763d704343d5560903c7c9dc_6.png)

And there that looks a little bit better， more like Romeo。But let's run it on Markov 3 now。

 So this is what he had done before。 If we come back over here， Markov 2。

He said there was three changes we needed to make。 and now we， we can make those same three changes。

 Here we go。呃。We're going to change the key length to three。Let's see。Everywhere we see a two。

 we change it to a three。And this should give us even better when we run it。

Even a better random tax generation that looks more like Romeo。

 so those are the three things he changed before， our key down here will still be the same。

 it'll be of link  three every time。Let's try that。Let's compile Markov runner。

And so it says Markov2， but we're really running Markov 3。And we're going to run it on Romeo。

And let's see what we get。 Oh， yeah。 There we go。 Nurse。 Good height me。 might go all。

 Those look like words。 So that looks pretty good。 Now， love ear eyes for the。

 So we're getting almost real words now for most of these that looks much better。

 So sometimes when your program doesn't look quite right。

 you're going to have to think small test cases and add some print statements to print out to figure out what's going on because you may think one thing and something else is going on。

 Anyway， this looks a lot better Thank you。😊。