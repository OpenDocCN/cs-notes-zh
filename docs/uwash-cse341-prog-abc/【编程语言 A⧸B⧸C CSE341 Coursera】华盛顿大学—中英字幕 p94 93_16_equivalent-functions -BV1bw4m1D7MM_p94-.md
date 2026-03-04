# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p94 93_16_equivalent-functions -BV1bw4m1D7MM_p94-

The last major topic we will consider in this section is a deeper and more precise understanding of when two functions are the same。

 or I'll call them equivalent。

![](img/97448be8a7a71cfa5b29859a88c1fd97_1.png)

So this is important to look at carefully， I'm not going to show you any new coding idioms or clever new things or language constructs。

 but it's such a fundamental idea in software engineering that I think it's worth focusing on。

We're going to see that you can replace one function with another if you're very careful and you know what it means for two things to be equivalent and we'll see that things are more likely to be equivalent when you are using more abstraction and when you have fewer side effects。

 if you can assume that other computations don't do things like mutate references or print things out。

 then additional things are equivalent。

![](img/97448be8a7a71cfa5b29859a88c1fd97_3.png)

So let me motivate why we're looking at this。 I believe that developers。

 people programming think about equivalence all the time。When you are maintaining code and you say。

 oh， I have a nicer style way， I have a nicer way to express this。

 What you're really saying is to express this same thing or to express an equivalent thing。

 no one will be able to tell that I did this code cleanup。

You are also thinking about this all the time when you're looking at backward compatibility。

 can I add new features without changing how this software behaves for any of the old features。

 It still behaves equivalently for all old possibilities。Code optimization， whether manual。

 when you're writing the code or if you're implementing a language is all about equivalence。

 can I speed up this code without changing how it behaves on any inputs。And finally。

 when we were studying our module system， we did this a bit as well。

 Can an external client tell if I replace this implementation with another implementation。😊。

Now what we're going to look at here is not necessarily related to modules or abstract types。

 instead what we'll do is say here are two functions。

 are they equivalent for all possible calls to them？So maybe I'm implementing a library。😡。

I don't know all the clients in my library。 I might be putting this code up on the Internet for people to use。

 I want to be able to think about， could I replace this function with this other function without any possible call to these functions ever being able to tell。

 That's what equivalence is all about。

![](img/97448be8a7a71cfa5b29859a88c1fd97_5.png)

Now we need to define what it means for two functions to behave the same way。

 and I will say that they have the same observable behavior， if given equivalent arguments。

 they meet all of these bullet points you see here on the slide。Clearly。

 they need to always return the same answer。 If one takes3 and returns 7 and the other takes 3 and returns 8。

 this is no good， right， but that's not enough。They also have to have the same nontermination behavior if one of them doesn't terminate on nine。

 the other needs to not terminate on nine， and similarly。

 they need to terminate on all the same arguments。They have to have any effects that they have on mutable references that other parts of the program can see be the same if one of them updates a reference to a different value than the other does。

 then after the call completes some other code in the program might be able to tell that you replace the first function with the second function。

😡，They have to have the same input output behavior。

 We can't have one printing something and the other not printing the same thing and they have to raise the same exceptions。

 We can't have one of them choose to raise an exception in a situation where the other one doesn't and I may have even forgotten things here。

 but I think this is a pretty good list All right Now notice it's going to be easier for two functions to be equivalent if users of these functions cannot use them with as many arguments。

For example， if you have a nice strong type system。

 that will ensure that say these functions only take string star string as arguments。

 and we don't have to think about well， what would happen if someone passed an int instead because no such calls will ever touch it。

We will also see。That it's much easier for two functions to be equivalent。

 If our language is a functional language where there are fewer ways to make side effects。

 and sometimes people even assume that you won't make side effects， even if the language allows them。

 I'll show you an example of that in just a second。



![](img/97448be8a7a71cfa5b29859a88c1fd97_7.png)

Okay。So let's finish up this segment with a few examples and then we'll move on to some more universal notions of function equivalents。

 so on the top here I have two functions F that are equivalent。

The function on the left takes in an argument， returns x plus x。

 The one on the right takes in an argument， returns y times X。

 This is defined in an environment where y is 2。 Both these functions always double their argument。

 They have no other side effects。 they always terminate they equivalent in every way。

 No M program using the function on the left would ever be able to tell if you swap it out for the function on the right and vice versa。

 So that's a good example。Here's an example where you might be surprised that the two functions are not equivalent。

We are not careful about our assumptions。So the function on the left。

 G takes in a function F an argument X and returns F applied to x plus F applied to x。

The one on the right multiplies F applied to x by y and Y is bound to2。

So these will always return the same answer， assuming F is a function that always returns the same thing when given the same argument。

But the code on the left calls F twice and the code on the right calls F once。

 and that is a problem if F could have side effects。 Suppose it increments a reference every time。

 Well， then the code on the left will set that reference to two more than it used to have the code on the right one more an even simpler example is if F always prints something out like this function here。

 if you pass this for F， it prints out high and then returns its argument。

 the code on the left will print high twice， the code on the right will print high once。So。

When you are in a functional programming language， we typically have functions that don't do this sort of thing。

 and if you assume these things don't happen， then the functions are equivalent。

 Some languages like Haskell is a good example， force a notion of pure functional programming。

 most functions in the language， those that you can pass the other functions like this cannot do things like printout。

 and as a result， the corresponding code in a language like Hakell is equivalent on the left and the right。

 So this is sort of yet another advantage of avoiding side effects in your code。



![](img/97448be8a7a71cfa5b29859a88c1fd97_9.png)

Let's do one more example here it's a few more lines of code。

 it's actually very simple that's going on。 The function F here on the left assumes that we have in our environment some functions G and H。

 it calls G with x calls H with x and returns a pair of the results。

The code on the right is the exact same except it just calls H and G in the opposite order。

 So unlike in the previous example， there's no number of calls problem here。

 both of these call G once and call H1。 So are they equivalent Again， if G and H are pure functions。

 they don't have side effects， they just compute something and return a result， then yes。

 they're equivalent。But if GN H can have side effects， then no， not necessarily。

Suppose G print something and H print something， well then the code on the left will print those outputs in one order。

 the code on the right will print them in the opposite order。Here's another example。

 Suppose G sets some mutable reference and H reads that same mutable reference。

 Then in the code on the left， H is going to see the new value after whatever g wrote to it and in the code on the right。

 H is going to see the value before G does its right because H executes before G executes。

 So once you have mutation， side effects printing we suddenly have to worry about the order we do things and different orders lead to functions that are not equivalent。

 but if we stick to a functional style where we don't write functions with side effects。

 then we do not have to worry about order， and we can execute these functions in either order with one final caveat that if G of x and H of x both raise exceptions and raise different exceptions。

 then the order could matter again and the code on the left would raise one exception and the code on the right would rate as another exception。



![](img/97448be8a7a71cfa5b29859a88c1fd97_11.png)