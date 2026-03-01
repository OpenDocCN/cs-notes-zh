# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p157 37_04_07_equals与hashCode方法.zh_en -BV18U411U729_p157-

![](img/8da2b6e6f213b2b12225188b78cb1b61_0.png)

Hi， we're going to develop a few of the methods that make word Gm functional in our Markov programs。



![](img/8da2b6e6f213b2b12225188b78cb1b61_2.png)

We'll use the program wordGtester。Java to demonstrate techniques。

 ideas and test methods you might implement in any class， but in particular for WordGraM。



![](img/8da2b6e6f213b2b12225188b78cb1b61_4.png)

![](img/8da2b6e6f213b2b12225188b78cb1b61_5.png)

We'll show how to test do2 string and the word Gra constructor， though these are already written。



![](img/8da2b6e6f213b2b12225188b78cb1b61_7.png)

We'll see why dot equals is needed， and although we've discussed dot equals in a previous course。

 this will be a brief discussion on implementing dot equals， not just calling it。

The dot equals method will be needed for markoff Wordge follows to work correctly。

That will be enough for the Markov runner class to work with Markov word and generating random text。

 but we'll touch briefly on an advanced method。We'll see how to implement dot hash code so that word Gra objects can be added to a hash mapap。

With knowledge of dot2 stringing dot equals and dot hash code。

 you'll be ready to tackle lots of class and program design。Let's look at dot equals first。

In previous programs， you've seen why you need to call dot equals with strings。



![](img/8da2b6e6f213b2b12225188b78cb1b61_9.png)

Using double equals doesn't work because that test whether two objects are the same object that is the same memory location。

 not whether they contain the same information。

![](img/8da2b6e6f213b2b12225188b78cb1b61_11.png)

![](img/8da2b6e6f213b2b12225188b78cb1b61_12.png)

And other programs you've called dot equals。 now we'll look at what's needed to write it。

We must adhere to Java's requirements for writing God equals。

The first requirement is that the parameter has type object。

 that's the base or parent class for every class in Java。

 The reasons for requiring this type will be explored if you take a more advanced course in object oriented programming。

We won't be calling dot equals with any types other than word gra。

 so the first thing we do is cast the parameter O so that the compiler will treat it as a word gra object。

Casting by putting the type in parentheses makes the compiler treat the object referenced by parameter O as having type word gra。

 which we do using the variable we've named other， but any name can be used。

Then we compare our length with the length of the word gram object， reference by other。

 and return faults if the links differ。 That's the first step in implementing dot equals。

With dot equals and do two stringing we're ready to code the mark off word classes。

 but we'll take a look ahead at what you'll study in later courses and as an enhancement to the markov classes we've been using。

We could store all the keys used in generating text in a hashmap。

 We'd map the keys to a list of all characters that follow the key。😊。

This technique works with letter or word Markov models。

 We'll show this with this training text and a two letter Markov model。

 The training text starts with the heardd， then。

![](img/8da2b6e6f213b2b12225188b78cb1b61_14.png)

![](img/8da2b6e6f213b2b12225188b78cb1b61_15.png)

And continues with more letters， not shown。The idea is to avoid scanning the text many。

 many times for keys like he。In our motto， we find he and a follow character。

 Then the next occurrence of he。Then the next occurrence of he。 If we ever see the key he again。

 we'd need to rescan the text， looking for follow characters。

 repeating work we've already done before。 This could happen every time we generate he as a key and need to find the follow characters。



![](img/8da2b6e6f213b2b12225188b78cb1b61_17.png)

Instead of scanning， we could look up the key in a hash map and retrieve the following characters stored in a list。

 This could be efficient， as we'll see for this to work。

 we need to implement the dot hash code method。We'll provide a high level overview of hash maps enough to get some understanding。

 but not lots of detail。The idea is to convert an object into an integer hash code。

This hash code works as an index into the hash map。



![](img/8da2b6e6f213b2b12225188b78cb1b61_19.png)

For strings， the object Ho might be converted to have the hash code 3。217。

 It's some number that tells us where in the hash map defined find Ho。

The simplest idea for a hash code is to make every object have the same index。 a number like 17。

 If we did this， our code would work correctly if dot equals was correct。

 But the performance would be really bad because every object would be stored in the same bucket。

 The word used for a place in a hash mapap where objects are stored。 Ially。

 each object has a different number。 So finding an object in a bucket is easy because it's the only object in the bucket。

😊。

![](img/8da2b6e6f213b2b12225188b78cb1b61_21.png)

![](img/8da2b6e6f213b2b12225188b78cb1b61_22.png)

You'll see details of how this works if you take another Java a course。

 like the UCSD specialization that follows this one。

A simple idea with better performance is possible to simply add the hash codes of each string in the word gra。

Have fun with hashing objects， hopefully into lots of different buckets， so your hash is fast。

