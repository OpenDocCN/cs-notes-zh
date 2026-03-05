# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p22 P22 01_第一课1-1-1：哈希简介 -BV1KnLCzXEcQ_p22-

![](img/e9a6646657aa742b0fb93cb9029ba5e6_0.png)

![](img/e9a6646657aa742b0fb93cb9029ba5e6_1.png)

Today we're going to move over to an entirely new type of algorithm。

 and this algorithm is often computer scientist favorite algorithm because you're going to find the results of hashing is going to give us a fantastic runtime for certain operations。

Let's dive into what it means to do hashing。😡，Mathematicically。

 we define hashing as a key space that we want to transform into a number of different values。

 So everything inside of our key space is going to be every possible key that we can have inside of our dictionary。

And our goal of a hash table is to be able to map every single key to the value that it contains in that dictionary and do so as quickly and as efficiently as possible。

You may already be familiar with hashing if you've ever used a dictionary structure in a language like Python or jascript at the core of these native data types。

 we have the idea of hashing。 Let's go ahead and look at what it might mean to actually do some hashing。

 So， for example， let's look at a hash table。 And the first example。

 I can remember about hashing is thinking all the way back to high school in high school。

 I went to a large school that had a number of lockers and every single person was assigned a locker。

And I remember all the way back for my high school days that here in this hash table。

 I was assigned the locker at 103。 So that was my locker。

And then I knew the locker numbers of some of my friends because they were kind of。

 if I wanted to see some of my friends between courses。

 I would go to their locker and meet them at their locker。

 and that way I could find exactly they were they were gonna be located。 I could go directly there。

 even to this day， I remember some people's locker。

 One of my best friends Blake was at locker number 92。

And there's a number of different lockers here at the school。

 The one thing to note is that the lockers are a unique key value that every single locker has some integer number。

And that that locker is associated with some data。 The data here is the name of the person who owns a locker。

I imagined somewhere in the administration， there was a mapping between the student who owned the locker and the locker number so that given any locker number。

 you could quickly look up which student had that locker。

A hash table is going to allow us to do exactly that。

 Were going to input a number into our hash table， and we're going to use some function so we can go ahead and map every possible number input into a fixed sized output。

Because ultimately， in a locker key space， we might know exactly how many lockers there are。

But we may also consider things like an identifier。

 such as a social Security number or other identifier。

 That may be a random number that's not entirely filled up in the key space。

 So we know the key space can be any possible integer。

 and we want to be able to map any possible integer into our output space。

 So the entire goal of hashing is always going to revolve around this diagram。

 Here we have input coming in。This is gonna be something like an integer。

 some function that we're going define later that's going to transform this function。

 This integer or string or whatever our input is into a number that is in the range 0 to whatever the size of our array is。

 which I'm going to call in the transformation of this key input into a number。

And then how we manage that array and ensuring to deal things with tech collisions。

Is exactly what we're gonna to be talking about as we talk about hashing。 So specifically。

 when we define a hash table， there's always going be three things at play。

 And we're going dive into what each of these three things means。 The first thing is。

 we need some function， a hash function。That's going to map our input space into an array index。

 So if we have a string as our input， we need to map that string from the string input type down to some integer between 0 and 8。

The second thing we need to look at is we need to actually have an array。That stores the actual data。

 So notice that here at the hash table， we have an array that's going to store our data that's going to be indexed in by our hash function。

The very last thing is we can imagine that sometimes we're going to have two things in the same spot in the array。

 And we know that's not allowed。 So we need some way to。Decide what we want to do in collisions。

So when we have collisions， we want some collision handling strategy。

That's going to allow us to handle the collisions that occur when our hash function maps two different values to the same point in the array。

The combination of all three of these ideas is going to be the subject of this week's videos。

 and we're going to dive in to exactly what it means to build a good hash function。

 what it means to have a good strategy with array and exactly what we do when we do have a collisions。

😡，So while this may be a little confusing right now。

 it will become clear as we move through these videos。

 Let's get started with the hash function in our next video。 I'll see you there。



![](img/e9a6646657aa742b0fb93cb9029ba5e6_3.png)