# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p49 48_21_accumulators-for-tail-recursion -BV1bw4m1D7MM_p49-

In this segment， I want to continue our discussion of tail recursion and show you the common pattern of how we create tail recursive functions and the role that accumulators play in that process。



![](img/d3dd7a0bd205eb9b1c9589780b9cf2c1_1.png)

![](img/d3dd7a0bd205eb9b1c9589780b9cf2c1_2.png)

So what I'm trying to emphasize is that when we have tail recursion。

 we do have significantly more efficient functions， so if it's reasonably elegant， if it's simple。

 and if performance is important， it can be worth rewriting your function to be tail recursive。

 so a tail recursive function is just one where all the recursive calls are themselves tail calls。

 so we have the situation where when we do the recursion there is no more work for the caller to do after the recursive call is done。

And it turns out there is a methodology that can often guide this transformation a way for you to take your code and make it tail recursive。

 and that is to create a helper function that takes an accumulator。

 something that combines answers as you go along to hold the answers so far。

 and what typically happens is the old base case from your recursion is your initial accumulator。

And in the recursive accumulator style function， your final result is just your accumulator。

 And it turns out that this works any time that you can combine your results in essentially any order in order to get the same result。

 So in our previous example where we had factorial， that's indeed the case。

 it doesn't matter to us what order we multiply all these numbers。

 three times two times1 or one times two times3， and therefore this transformation worked just fine。

 So indeed， if you think a factorial in your head as multiply n by the recursive factorial of n -1。

 that's the traditional version。 but the tail recursive version， which we have here。



![](img/d3dd7a0bd205eb9b1c9589780b9cf2c1_4.png)

Uses our methodology。 We have a local helper function O that takes an extra argument。

 The accumulator， the initial accumulator in this call here between the in and the end。Passes in one。

 which used to be our base case。 And then in the tail recursive helper function， our base case。

 when n equals 0 is to just return the accumulator。

 And so we are still recursively calling ox each time with n -1。

 But we're multiplying numbers as we go。 So when we get to0 the accumulator as our answer。

 And that's why this worked out。 So let me show you two more examples。

 The second one will actually be more interesting。 The first example is just summing all the elements in the list。

 It turns out that at the top， we've written functions like this many times。

 this is not a tail recursive function in the recursive call here where we call sum with x is prime。

 the caller still has work to do after this call finishes。 we need to add X to that result。



![](img/d3dd7a0bd205eb9b1c9589780b9cf2c1_6.png)

But our methodology will work here because we don't care what order we sum numbers up。

 and so we can create a helper function ox。It can take an additional argument and accumulator。

 itss base case can just return that accumulator。 When we have our recursive call now。

 we make sure it's tail recursive。 There will be no more work to do by the caller after we complete this call and we pass in for our new accumulator X plus a so that we're adding things as we go。

 and then our initial accumulator 0 is what our base case was above when we had our traditional version of some。

So that was also a fairly easy example。 factorial and some are fairly similar。

 Let's do a more interesting example。 This is something I haven't shown you before。

 Let's take a list and reverse it。so if we get had the list 1，2，3。

 we want to come up with the list 3，2，1， and it turns out in this case the traditional version is not very good and we're going to look at why。

So I take in a list X's。 the way you reverse the empty list is you return the empty list。

 No problem there。 Otherwise， aha， we do want to recursively reverse x's prime。

 sorry that should be x's prime right there and that's fine but then what we need to do is put X at the end and it won't work to write cons X because cons can't have a list in the first position and element in the second position。

 Now what we need to do is we need to make a list holding x and then append those two lists together and it turns out that's remarkably inefficient。

 as we'll talk about on the next slide， but if we just do our tail recursive version。

 everything will work out normally。So here's the tail recursive version。

 create a local helper function that takes in the accumulator。

 let's start that accumulator with the empty list， let's pass in x's for the argument。

 and here if x's is empty then just return the accumulator。

 but now what we should do in the recursive case is yes， pass in x's prime for x's。

 and then this accumulator which is the reversal of the list so far。

 we just want to put x on the front of that。Okay， so if we were to reverse 1，2，3。

 the initial accumulator would be empty， then the next accumulator would be one cons on to empty。

 then two cons down to one onto empty。 and indeed， our natural accumulator pattern is reversing the list quite simply with a simple tail recursive function。

 and this will be as efficient as a loop that takes a list and produces a new list that is the reverse of the list you started with。



![](img/d3dd7a0bd205eb9b1c9589780b9cf2c1_8.png)

Okay， so as promised， let's dig a little deeper here on what's so bad。

 so inefficient about the traditional version。 Okay。

 so it turns out that it's not just that we're going to build up a call stack every time here。

 It's actually that this append operator always copies the first list。 It has to。

 That's how aend works。 The same thing happens in the version of aend we would write。

 whether aend is tail recursive or not。So it turns out that this code。

 if you were reversing a list of length proportional to some number， let's call it K。

The amount of work this is doing is proportional to K squared。

 It's growing quadraically with the length of the list that was not true for factorial。

 It was not true for some。 It's because。IfWhen we have these k recursive calls。

 one of them is going to copy a list of length 1， one a length of list2，1 a length of list 3。

 all the way up to one of list of length K minus1 or maybe even K。

 and the sum of the numbers from one to K is approximately k squared over2。

 it is only about it is about half as big as k squared。

 and that is a lot more work than our tail recursive function。

 Our tail recursive function did not use this append right， It only used cons。

 The total amount of work this bottom version is doing is proportional to the length of the list whereas the top version is doing a total amount of work proportional to the length of the list squared。

 So this is an interesting point。 The moral here is don't just obsess about whether your tail recursive or not。

 you should also beware of aending things。 that if you are recursively appending at every step。

 your algorithm。

![](img/d3dd7a0bd205eb9b1c9589780b9cf2c1_10.png)

![](img/d3dd7a0bd205eb9b1c9589780b9cf2c1_11.png)

Sometimes significantly less efficient than you might expect it to be。



![](img/d3dd7a0bd205eb9b1c9589780b9cf2c1_13.png)