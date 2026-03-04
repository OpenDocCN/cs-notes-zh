# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p112 14_12_mcons-for-mutable-pairs -BV1bw4m1D7MM_p112-

In this segment I want to introduce MCon cells， which are separate from con cells。

 and the differences in MConN cells supports changing the contents of the car and cutter fields。



![](img/7d6ca30fbc3682cea34f7dc79dc2f00a_1.png)

So what if you had a conel like we've been studying like we've learned is just a pair and you wanted to change its car。

 So it didn't have 42。 It had 43 or you wanted to change its cutter so it didn't have null it had some other value。

 Well， in racket， it turns out there is no way to do that。

 And this is the biggest change between racket and its predecessors like scheme and listsp。

 And the reason why they made this change is so we could use conces to make pairs and lists that were immutable and get all the advantages we had in M when we saw that lists and tuples were immutable。

The biggest advantage we like to emphasize is that it made aliasing irrelevant。

 It did not matter if one part of a list was alias was another part of another list because no one would ever be able to tell the difference because we couldn't update things。

 We made a big deal about this back in Section 1。 And it's nice that we can program with con cells in racket and get the same advantages。

As a minor side point， it turns out in a dynamically tight language like rackque。

 there's another advantage， which is the implementation of the list question mark procedure we saw in the previous segment can be more efficient。

Because when we create a conse， we know at that moment whether or not it will be a list and it will always be a list because no one can ever change any of the contents of any of the con cells that are relevant to it being a list or not。

 and so the implementation is able to record that fact and not have to implement list question mark by running down the entire list seeing if the list is actually proper or not。

But suppose that you did want to mutate things。 How might you go about it， What would work。

 what would not， And this is important because we are going to have some programming idioms come up where mutation is going to be useful in its typical limited only because we really want to do it way。

 So the first thing I want to emphasize is that set bang really does not mutate con cells。

 So here's a little list I've defined。 I bounded to X X holds the list 14。

 If I say that y is now X and y also holds the list 14。

 Suppose I said set bank X to be some different list。



![](img/7d6ca30fbc3682cea34f7dc79dc2f00a_3.png)

We saw set bank。 What that does is change X to refer to some new and different thing。

 So if I ask what x is， I get this new list。 But if I ask what y is， it's still the list holding 14。

 because when I defined Y previously， I looked up X。 I got the current value for x 14 and null。

 And so that's what y is set bank changed X。 but it did not change the con cell that x referred to。

 there is still a con cell out there with 14 in the car and null in the cutter。

 And so if I ask car of y， I get 14， x now refers to a different con。 So car of x returns 42。

So if we wanted to change the contents of a conll， something so that if say。

 Z and x both referred to the same。

![](img/7d6ca30fbc3682cea34f7dc79dc2f00a_5.png)

Thing， and then I wanted to update that thing so that the car of the cutter would be different。

 That is what racket does not support。 So you might think you could do something like， oh。

 we'll change the car of x to B 45。And that's just not what setbank does。

 Setbank only works on identifiers on variables and change changes what they refer to。Now scheme。

 the predecessor to racket， had a feature set car bang that would do exactly kind of what we want。

 it would look up X in the environment， get a cons and mutate the car field of that conel to be 45。

 and it's an advantage of racket that we cannot do that set car bank simply does not exist。

 but what if we wanted to。Well， rackcet understands there are situations where you may want that。

 And so it defined a different builtin data type for that thing。

 and the function that you can use is m cons， which is just like cons。

 except it does not make a con cell。 It makes an m con cell。 So here's a little example。

 where I'm actually going to make two m con cells where the outer one has a car of one and a cutter of true that it's itself an m con cell。

 And then the nested m con cell has a car of true and a cutter of high。 Now。

 you can't ask car of an m， you can't ask coter of an m， but you can ask M car。



![](img/7d6ca30fbc3682cea34f7dc79dc2f00a_7.png)

![](img/7d6ca30fbc3682cea34f7dc79dc2f00a_8.png)

![](img/7d6ca30fbc3682cea34f7dc79dc2f00a_9.png)

![](img/7d6ca30fbc3682cea34f7dc79dc2f00a_10.png)

Of an emperor and M Kter of an emperor。 And， of course， since the M Kter in this case。

 is itself a conse， we could ask something like M car of M cutter of emperor。

 And that would get out the Boolean true。Now， the difference between m cons and cons is that these things are mutable and there is in fact something called M Kter bang。

Right， M Kterb， I could apply to the con and emperor changes to 47。 and now sorry， Emperor。

Holds the con where the car is one and the cutter is 47。I could change it back。

I could change it back to Mcon's true high。Al， and now emperor is back like this。

 I could even set M car bang of M coter of Emper to say， 14。And now， if I ask emperor。

 you'll see that the car of the Qter of Emperor is now 14。 It's been changed。So this is how it works。

 You cannot mix and match things。 As I pointed out。

 So length is a wonderful builtin function that works just fine on lists like this。

 So this is a plain old list that returns true。 lengthngth gives an error on improper lists。

 like we saw in the previous section， lengthngth also gives an error on an m cons。

 Even if that you're using mcons is in a way that is like proper lists。

 You cannot use mcons to make proper lists。 lengthngth requires a proper list。

 and so you're not allowed to mix and match these things。 And， of course。

 something like mcar bang is not going to work on a con cell that is not an mcon cell。😊。



![](img/7d6ca30fbc3682cea34f7dc79dc2f00a_12.png)

![](img/7d6ca30fbc3682cea34f7dc79dc2f00a_13.png)

![](img/7d6ca30fbc3682cea34f7dc79dc2f00a_14.png)

So that's the idea。 Let me just flip back to the slides to emphasize that all we've really done is introduce a new set of functions and constructs that are separate from con cells。

 we make a mutable con with m cons， get its first thing with mcar second thing with mCter。

 we can find out if we have one， this is the one thing I didn't demonstrate for you with m pair question mark set the content set the car field with set mcar bang and set the cutter field with set m cutter bang so when we need a mutable data structure。

 something that has multiple pieces whose contents can change， we'll use mcon cells。

 and when we do not want mutability we'll use regular cons cells。



![](img/7d6ca30fbc3682cea34f7dc79dc2f00a_16.png)