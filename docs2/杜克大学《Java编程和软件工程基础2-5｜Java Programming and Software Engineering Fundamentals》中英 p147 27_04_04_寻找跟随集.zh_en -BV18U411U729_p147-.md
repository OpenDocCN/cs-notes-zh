# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p147 27_04_04_寻找跟随集.zh_en -BV18U411U729_p147-

![](img/80cf874920e5f804df60a7e37576e79a_0.png)

Hi， we'll use our seven step process to develop the key algorithm for Markov models beyond Markov Ze。

 We've developed Java programs for the Markov Zero model of text generation。



![](img/80cf874920e5f804df60a7e37576e79a_2.png)

![](img/80cf874920e5f804df60a7e37576e79a_3.png)

Characters were chosen at random from the training text， so if E occurs more often than a。

 it's more likely to be chosen in generating random text After seeing the code to generate random text using a Markov zero model。

 it's time to develop the key algorithm for implementing a Markov 12 or more model for generating text randomly in a Markov1 model if we generate T we need to choose next from all characters that follow T。

In a Markov two model， if we generated T H， we'd find all characters that follow every occurrence of T H。

 We use these follow characters to continue the process of random text generation。

 The key algorithm is finding these follow characters。

 We'll use our seven step process for a markov one model。

 but generalizing to two or more is very simple。

![](img/80cf874920e5f804df60a7e37576e79a_5.png)

The first step in our seven step process is to work an instance。

 we'll use this sample training text that reads this is an attempt to illustrate the algorithm。

 we'll find the following characters of the letter T to develop the algorithm。

 but will generalize to any letter not just to T， just as we' generalize to any training text。

 the character H at index1 follows the first T found at index0。The next T is founded index 12。

The following character is the T at index 13。Then comes the letter E following the T found at index 13。

We'll need to decide what to do with the T founded index 17。 There are no follow characters。

 so we'll need to ignore this T or choose another course of action when we develop the algorithm and write code。



![](img/80cf874920e5f804df60a7e37576e79a_7.png)

Step two of the seven step process is to write down what we did we start with a follow list that's empty。

And we'll write down what we do to find characters that follow T in our training text。

 We search for the first occurrence of T starting at0。 We found the T at index 0。

 So we add the following character an H at index1 to follow。



![](img/80cf874920e5f804df60a7e37576e79a_9.png)

Then we find the first D starting at index1， the first index we haven't examined in searching for a T。

Then we find the T at index 12 and add the T at index 13 to the follows list。

 we're ready to continue writing steps down since we haven't searched all the training text。

Let's look at what we get in writing down all the steps Here are all the steps in getting to the list of letters that follow the key letter T in this training text。

 the follows list we have shows the three letters but it's initially empty we searched for a T starting at index 0 and we found the T at index 0。

 we added the next character， the H of index 1 to the follow list。

 then we search for a T starting at index1， since that index hasn't yet been searched for。



![](img/80cf874920e5f804df60a7e37576e79a_11.png)

Not coincidentally， our search starts at the index of the most recent follow character。

We find a T at index 12 and add the next character， the T at index 13 to the follow list。

 then we search for a T starting in index 13， we find a T at that index。

 and so we add the next character the E at index 14 to the follows list。

Then we search for T starting in index 14。 We find the T at index 17。

 but we can't add a follow character since there isn't one。

So we stop and we have the complete follows list with three characters， H， T， and E。

Now that we've written down all the steps， we move on to step three。

 finding patterns and generalizing， we can see the process of finding an occurrence and adding the letter that follows in steps2 and three of those steps we wrote down the same pattern occurs as steps 4 and5 for the next occurrence of T。

Then the pattern occurs again as step six and seven。

We've shown step eight as part of the same pattern， but there's no follow character。

 so the pattern isn't completely duplicated。In looking for patterns and generalizing。

We often try to connect the patterns we find Steps two and three were the first occurrence of T。

Steps 4 and 5 were the second occurrence， and steps 6 and 7 were the last of occurrence of T that had a follow character。

 Step 8 was part of the same pattern， but it did not have a follow character。

Note that the index of the follow character in one step。

Is the index at which the search starts in the following step。

 We find patterns and relations between them in generalizing what we wrote down。

As we get ready to write down the algorithm to test it with new data。

 we'll think about the steps we've written down， we'll think about how to initialize the algorithm and how to know when to stop our repeated steps。

 We start searching the training text at index0 with an empty follows list when will we know when we're done searching so that we're done searching for keyT in our example。



![](img/80cf874920e5f804df60a7e37576e79a_13.png)

![](img/80cf874920e5f804df60a7e37576e79a_14.png)

If we don't find a T， say after the last occurrence， we'll stop。



![](img/80cf874920e5f804df60a7e37576e79a_16.png)

If we run off the end of the training list， as with the last T， we'll also need to stop。

Now you're ready to write down the general algorithm。

 You'll start searching an index 0 with an empty follows list。

 We'll use the variable pause to indicate where we start the search。

 While there's more searching to do meaning we might find the key we're searching for as we loop through the steps。

 we find the first occurrence of key starting at pause。 remember that pause is initially zero。

 but it changes in our loop。 We store the location of the occurrence in variable index。

 If we find the key， we've added it to the following list。

 We've used index as the variable of where the key is found。 So index plus one is the next character。

 So we're using a one character key。We update pause to be the index of the follow character if we didn't find an occurrence of key in the previous step。

 we'd stop or break out of the loop。Before you turn this into code。

 it's time to test out the algorithm， give it a try on this training set with the key being the letter E excuse me A。

Did you get the right answer？If you're doing the algorithm carefully。

 you'd notice that even though you computed follows correctly。

 you never actually said follows is the answer， oops， that's an easy mistake to make。

 but when you translate your algorithm into code， you have to explicitly return the answer you want。

 we'd better add that。😡，Now the a going to produce the right answer， NP， space， and Y。

 all follow the letter A。Happy coding。