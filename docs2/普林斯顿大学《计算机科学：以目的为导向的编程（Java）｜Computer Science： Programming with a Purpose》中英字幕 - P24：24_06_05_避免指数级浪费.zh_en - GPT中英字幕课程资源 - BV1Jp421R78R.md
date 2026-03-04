# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P24：24_06_05_避免指数级浪费.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/17d5e293126edeb1902b4093df13e065_0.png)

Now we're going to look at a performance pitfall with recursion that's often ignored。

 but it's very important， and it will also lead us to another important programming scheme。

Let's start with the Fibonacci numbers， we've used it as an example before。

 and you're certainly familiar with it。It's the sequence defined with f0 equals 0， f1 equals 1。

 and then from then on， each number is computed and the sequence is computed by adding the previous two。

So one plus two is3， then the fourth one is the fifth one is2 plus3 is 5，3 plus5 is 8。

5 plus8 is 13 and so forth。That's the Fibonacci numbers。

Now it's actually widely found in art and architecture and we'll look at a couple of applications if Fibonacci studied it for actually studying rabbit populations and we'll see plenty of other examples and it's a very interesting to study just within discrete mathematics。

 For example， it's known that the ratio between two Fibonacci numbers approaches the golden ratio in Renaissance in classical art and architecture contains this golden ratio and we'll see some examples of that's another way of looking at it if you just add a square proportional to the previous Fibonacci number。

 you can arrange them in this kind of sequence if you actually draw in semicircle through every square you get an interesting curve lots of facts that I'm just throwing up on this slide。

To show you the ubiquity of the Fibonacci numbers。呃。

And so the Parthenon comes in those ratios that appears in nature that's a Nautilus show， sunflower。

 galaxy， Mona Lisa herself。Here's our friend， the Pascals Triangle。

 and if you look at it that kind of an angle， you get the Fibonacci numbers kind of amazing。

Even Darth Vader involves the golden ratio and the Fibonacci numbers。

So very interesting sequence and in the present context， what we're interested in is computing them。

 so somebody might say， well， I've got a computer， what's the 60th Fibonacci number and a naive programmer might say okay。

 I'll just that's obvious you can write a recursive program for that and come up with that program。

Recursive program we'll use long because it's probably going to be a big number， n equals0， return0。

 n equals 1， return one， otherwise recursively call for FN minus1， fN minus2。Looks pretty good。

 Take our。The number we want from the command line and then just call this recursive function。

And sure enough， it works pretty well， get numbers that I recognize， 12th1s， 144， so let's go for it。

 what's the 50th one。It actually in your computer， it's going to take a little while to compute that one。

 And if you try to do 60。Novice programmer is going to say， wait a minute。

 there's something wrong with my computer。It's not really what's wrong is understanding the cost of recursion properly。

So let's look at the recursive call tree for Fibonacci numbers， say when we're computing F of6。

 so to compute F of6， we have to compute F of5 and f of4 and so forth。

 that's what the tree looks like。So let's take a look at the recursive call tree for F of 60。

 So we'll define the number of times that F of N is called to be C sub n。

And so if we're computing F of 60， then we call F of 60 just once。

 and we'll just note that that's F of1。 That's the first Fibonacci number。

F of 59 also gets called just once and just note that's F of 2， the second Fibonacci number。58。

 it's called twicew， and that turns out to be F of3。57， it's called three times， and again。

 you can actually， after you see the pattern prove that the number of times F of n is called as n decreases goes up with the Fibonacci numbers。

And so we have a sequence of Fibonacci numbers increasing。

 which is the number of times that f of n is called and when we get down to f of0。

 that gets called F of 61 times， and that's a problem because F of 61 is a huge number。

And it's easy to see why if we've already computed F of 58 at whatever cost over here。

 we're computing it all over again and similarly， it's exponentially wasteful to recompute all these values。

 it's trillions of calls on F of zero and not to mention the calls on all the other ones。

 these are values that we already know and we threw that information away。Remember。

 F of n grows as golden ratio to the nth power。 So it's going to be an exponential cause just to know that F of0 equals  one。

So obviously not an efficient way to proceed。And if you're going to engage in waste like this。

 you will not be able to solve a large problem。G this lecture in the 1970s where we had a computer。

 maybe it would take minutes to compute F of 30 and hours to compute F of 50 years to compute F of 60。

 this is a small computer that maybe could do a million instructions a second so but nowadays even though we have a machine that's 10。

000 times faster， it just means that we can get just a little bit further so we used to say in the 70s。

 that program is not going to compute F of 60 before you graduate now we just say it's not going to compute F of 80 before you graduate so the point is you don't want to engage in exponential waste。

Now the thing is it's very easy to avoid， and there's a technique called memmoorization。

And so what we're going to do is just remember all the computed values。

 we use an array memo and if we already remember that value， we just return it， otherwise compute it。

 remember it and then return it。And so this is a general technique that can be applied to lots of programs。

 so we do know that the numbers are going to get huge and so F of 100 is not going to fit in along。

 so that's a bound on the size of that array。So now if we want to compute F of N， well。

 we can still have our base case for 0 and1， but otherwise we look to see if we've computed that value before。

And if we。If not computed that value before the memo for thatll be zero。

 so we just go ahead and do the recursive calls and then save away that value and then when we're done。

 we return it so that simple change all of a sudden gives an extremely fast program。

 a very easy way to avoid exponential waste and we can do 50， 60 or 80 with that simple change。



![](img/17d5e293126edeb1902b4093df13e065_2.png)

So you want to know that now in some of the cases that we did like the Tower of Hanoi and the Age tree and the Brownian Cloud。

 we actually were running the thing it was exponential in our parameter n。

 but we were cutting off way before we were wasting anything we actually wanted to compute all those pixels or all those moves。

 but in a case like this， which is also typical you cannot assume that computers fast enough。

 to beat exponential waste。And this is also important because it's a simple example of a very important programming technique called dynamic programming。

 it's related to recursion， it's kind of like recursion with memorization or working without doing the recursion。

 and that's what we're going to look at next。

![](img/17d5e293126edeb1902b4093df13e065_4.png)