# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p152 32_04_01_介绍_3.zh_en -BV18U411U729_p152-

We're going to use our Markov programs as the basis for studying Java class design as part of how Java works with object oriented concepts。

We'll use the concepts developed in the programs that generated text using Markov processes but will extend those concepts instead of choosing letters based on other letters。

 we'll choose words based on other words。In an order zero program， we'd choose words at random。

 as though the keys on our typewriter had words from a training text rather than letters。

But in order one program would use one word to predict or choose the next word so that the word cat would likely be more likely to follow the depending on the training text。

 but less likely to follow dinosaur。We'll use the Java interface developed in the last lesson。

 but expand on the idea to study new Java concepts by generating what we hope are amusing stories。

In particular， we'll look at how to design a class in Java so that it can be used like string is used。

We'll look at a word equivalent of string， so we'll support methods like dot length and dot substr。

But we'll see that we need to develop code so that dot equals works。

And code so that an object can be a key in a hash mapap。

These are standard Java concepts that apply to many classes， not just the word class。

 will design and implement。Let's look at the output of a word Markov program。

We'll compare the output of an order  one example using letters and one using words。

 We'll see that we can read the word example more easily， but it won't make grammatical sense。

 When we use an order 2 or order three word program， the output will make more sense grammatically。

Is the training text for this order one letter Markov program recognizable。It's unlikely。

 and the words are hard to pronounce。Hingngebo， Owap。Doesn't make much sense， for example。

If we use an order 1 Markov program， all the words are real words in that they occur in the training text。

 But the order of words often doesn't make sense。 As you can see here with， I beg your tongue。

However， you might recognize some of the words and be able to determine that the training text is Lewis Carroll's Alice and Wonderland。

You'll be able to train your program with any data， not just old children's books。



![](img/0e7a3cf2318aba14f6866745a630edec_1.png)

Is this order one text recognizable again， the individual words are hard to pronounce。

The Markov word1 class will develop can be run from the same Markov runner class as the program that uses letters rather than words。

 This is part of what Java interfaces enable。Depending on your interests。

 you may have an easier time recognizing the training text that generated these words。

If you don't recognize it， don't worry。 It don't matter。

This training text is the song Hello by Adele。 This might be recognizable today day。

 but will it be in a few years， Hopefully， you'll still be programming then to find out。



![](img/0e7a3cf2318aba14f6866745a630edec_3.png)