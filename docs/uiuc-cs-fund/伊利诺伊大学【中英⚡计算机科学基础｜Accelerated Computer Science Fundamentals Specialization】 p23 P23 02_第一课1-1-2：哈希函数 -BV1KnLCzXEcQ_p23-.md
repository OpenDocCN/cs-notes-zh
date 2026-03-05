# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p23 P23 02_第一课1-1-2：哈希函数 -BV1KnLCzXEcQ_p23-

![](img/2ad6b71c2245d1c6ae1f13d91d3bda6d_0.png)

![](img/2ad6b71c2245d1c6ae1f13d91d3bda6d_1.png)

To really understand what a hash function does， let's take a look at a couple different hash functions through examples of data being put into a hash table。

So this first example is a number of faculty who teach courses here at the University of Illinois。

Here' at the University of Illinois。There are courses like 2，41。

 which is taught by Professor Lawrence Engrave。421， Professor Beckman，2，10， Professor Cunningham，1，0。

1， Professor Davis。Carl Evans teaches 126。I forfessor Fa Omchiner， teach 225。

 and we can see the little goes on and on and on。Here we need to figure out a function that allows us to map all of these names into an array index。

😡，So if you noticed， I chose a particularly unique set of professors and list them in a particular special order so that we can have a really great function。

Notice that there is exactly one professor for every single name in the alphabet。

Our key function here may be the function where we look at our key string and we take index 0。

 and we subtract to character value A。So engrave is going to be character value A minus character value A。

 which equals0。 So our key engrave is going to be placed in index0。And his value is 241。Beckman B。

 B minus A is going to be equal1 and Beckman。Can be placed into the second index or the second position。

 index 1 in our array。For 421。And we can continue this on， and you'll notice that C goes into index2。

 D， E， F， G， and H。Each of these letters have a perfect mapping into our array from our keyspace。

And in fact， every single element in our array is filled and has a unique mapping back to the original data。

This idealized hash function， this perfect hash function is something we mathematically call an on to function。

That every single element in the array is full， and we can map every single element into our data onto that array。

This is an amazing setup and that's going to be the absolute goal of what we want。

But there's a slight problem。A new faculty might have arrived。

Who had a name that's similar to one of these names？When we have to consider that faculty member。

 there's no longer space。So if we have a new factory member， Professor Charles。

 Professor Charles is unfortunately going to land right here where Professor Cunningham is currently at。

That's a problem。 And we're going to need to handle that collision。 So let's think of。

 let's remember that problem and we'll deal with it again in a second。

A second hash function is one of my favorite dice games。 So whenever I have a group of people。

 And if you were here in person， I would roll a number of dice for you。

 and I would show the result of this dice and give you a number of what that dice is。 So here。

 let's look at this set of dice。 Here we have a dice that has the pips 1 up， 2，3，4， and  one。😊。

I would give you the number two as the mapping to this set of dice。😡。

I could roll this dice a number of times and give you numbers different set of numbers。😡。

And what I'm doing is something called petals around the rows。

This is a particularly fun example because it will take a while for people to figure out。

 so I encourage you to try it。But what I'm doing is I'm simply counting any dice that has a center pip that's active。

 such as the three and counting how many petals around that pip。Here one。

 it does have the center node， but has no pedals around it。 Four doesn't have the center node。

 so I'm not counting it， only three and the dice 5。Are counted。In petals around the rows。

So here my hash function is the function pals around the rows。

This function allows us to look at any set of input here input our dices and map that to a value inside our array。

 So look at this first set where I have the dice 1，2，3，4， and1。 my hash function。

 as we discussed earlier， maps it to2。 So that means here in 2。I have the value， one， dice 2， dice3。

Stys 4。And dice one again。So we know that the value2 is going to map to that data。

Or some other information associated with it。 One thing I might do is actually just keep a tally of exactly how many there are。

So let's actually discuss some things that are going to happen to this hash table。

So given that we know that there's always going to be either two or four petals around the rows。

Think about what happens for the hash value1。Will anything ever get mapped to one？It won't。

 The only way we're going to count petals is for a three， we count2 or for a five， we count4。

So every single odd number is never going to be reached in our hash table。

 So this hash table is not going to be perfectly filled。

And if we think about all the possible roles of a dice。

Think about the fact that we may have a lot of roles that contain just a single five。

So there may be a lot of different values that get mapped to the value4。

Both of these problems are concerns that we need to have to fix。

To ensure that we have a great hash function。We need to consider a hash function that works really。

 really well。For all of our key spaces。And there's going to be three characteristics that we can analyze to determine whether or not we have a great hash function。

So to dive into this hash function， we want to look at the hash function in two different pieces。

The first piece of the hash function that we need to look at is we need to look at the function itself。

 How we transform whatever our input is into a number。

 So we say that hash itself is going to transform an input。Into an integer。

Here in this initial transformation， I'm often going to not worry about the bounds of that integer。

 So I'm just need some generic function that's going to turn whatever my input is into a numeric form。

 into an insure form。 The second part of my hash function is gonna be a compression to make sure that hash function is within the bounds of the array。

 The compression can be easily done with a mod operator。 so I can do that using mod in。😡。

So I encourage you， as you're thinking about hash functions。

 to not create a new hash function yourself yet。That is actually really。

 really hard to make a good hash function。 And there's some amazing hash functions out there。

 So we want to understand how to analyze a hash function before we go about creating your own。😊。

As I mentioned earlier， there are three different characteristics that we're going to care about when we're building a hash function。

The first one is， is we need to make sure our hash function runs in constant time。

 we want to ensure that the time to computer hash is going to be O of one。

 We need to absolutely make sure our hash function runs in constant time。

 and we prefer if this was a very， very， very fast function。

It is absolutely essential that the computation time of the hash is extremely quick。

 If we're spending a long time computing the hash。Then we're gonna to spend a long time in this algorithm because we have to compute the hash every time we see a piece of data。

 So the first thing that makes a great hash function is that hash function must run in O of one time。

The second thing we need to absolutely make sure is true about a hash function is that hash function must be deterministic。

What this means is if we hash a string once。And we have to exact same string a second time。

Those two results must be exactly the same。What we cannot do is throw a random number in there。

We might love to do this because it'll randomize exactly where our input is in the result。😡。

But by throwing a random number in there， we no longer have a deterministic hash Every time you want to hash the number 103 or hash your string weighade。

 you absolutely must ensure that that string comes out at the other side。

As the same index into our array。 So that hash function's second requirement is。

 it must be deterministic。The third requirement is the hardest requirement to ensure is true。

 And this requirement is called the simple uniform hashing assumption， or Suha。

The symbol uniform hashing assumption says that the result of our hash algorithm must be uniform across the entire key space。

So what that means is under Suha， it means that given two values。

 so we're going to take the hash of some value A in a second hash function of B。

When we hash these two functions， we need the probability of the hash of a to be equal to the hash of B。

To be equal to one over the size of the array。😡。

![](img/2ad6b71c2245d1c6ae1f13d91d3bda6d_3.png)

If a does not equal B。So if we have two different values。

 the simple uniform hashing assumption says that at random two values are going to randomly be in different place in an array with equal probability Anytime you have bunching of data such the petals around the rows example earlier where you have multiple piece of data hashing to the same value and some of that data never hashing to odd numbers。

 we no longer have a simple uniform hashing assumption because you can see the probability of hashing to1 is0。

 while the probability of hashing to values like two or four was quite high。

So if we have a function that runs in constant time is deterministic and is a simple and satisfies a simple uniform hashing assumption。

 then we have an absolutely great start to building a great hash function。

We'll largely use other people's hash functions for most of our work here since it's so hard to ensure that uniform distribution。

 but we'll do some analysis on hashing functions to understand exactly their runtime。😡。

We'll talk about some of this analysis and dive into a few more examples in the next lecture。

 I'll see then。