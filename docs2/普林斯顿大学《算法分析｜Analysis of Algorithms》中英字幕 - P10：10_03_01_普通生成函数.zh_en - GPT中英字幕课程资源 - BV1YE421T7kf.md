# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P10：10_03_01_普通生成函数.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/a522ca107739d02821533cd57db21422_0.png)

Today we're going to talk about generating functions， as you'll see。

 generating functions are the central object of study in analytic combinatorics。

But they also have a rich history in many uses and will show at first how they're used for solving recurrence relations and then ease into their use in more general contexts。

So to start out， we're going to talk about just what is a generating function and the first thing we'll talk about is what's called ordinary generating functions。

So there's a definition of what is an ordinary generating function？

It's a function that's defined as an infinite sum involving a free variable Z in this case。

 over a sequence， so given a sequence， a0， A1 infinite sequence。

 like the types that we were working with with the recurrences。

The ordinary generating function of that sequence is obtained by multiplying the k term by z to the K and then summing over all k。

We also use the notation that inside brackets z to the n of A of z is the coefficient of z to the n in A of z。

And a lot of times we want to refer to what the coefficient is。And we'll see how it applies。

 but let's just talk formally about some examples of generating functions first， so for example。

 if the sequence is all once， then the generating function for that sequence is the sum n greater can0 z to Vn。

 which is geometric sum1 over 1 minus z。Or if you have one，12，16124。

 the sequence is one over n factorial， the generating function of that sequence is some n bigger than0 z to the n over n factorial。

 that's e to the z。So that's examples of generating functions and would say the coefficient of z to the N in e to the z is1 over n factorial。

So that's ordinary generating functions。 Now， the significance of defining a generating function is that it allows us to represent an entire infinite sequence with a single function。

Rather than carrying around the infinite sequence one over in factorctorial。

 we just work with the single function E of Z， and that turns out to have all kinds of benefits when we're doing analysis of algorithms and studying properties of combinatorial structures。

But before getting into the applications， let's look again at some more basic operations on generating functions that we'll use in order to be able to。

 we need to be able to find the generating function of a given sequence and we need to be able to get the sequence back given in the generating function and we use some relatively simple operations to get these jobs done so for example。

 here's the scaling operation。If you have a of Z， which is generating function for some sequence。

 if you multiply the argument by a constant C， so just evaluate A of C Z， then just do the math。

 that's the sum of C to the K， z to the K， that's the generating function of the sequence A0， CA1。

 C squared A2， C cubed A3， and so forth。And that's just from the maths， CK ZKs is the。

Is the generating function of that sequence so here for example。

 if you have the sequence that's all once with its OGF1 over1 minus z。

 then1 over 1 minus2z is a sum of 2 to the n z to the n which is a generating function for the powers of twos so that's scaling so that's an easy way to get generating functions for different sequences out of a known sequence。

And again， would say coefficient of z to the n and 1 over1 minus 2 z is 2 to the n。

So that's scaling let's look at another example addition。

 that's an easy operation on generating functions。 If you have two generating functions on two different sequence。

 then the sum of the generating functions is the the OGF of the term by term sum of the sequences。

 So for example， these two generating functions that we've developed here。

 if we subtract the say we subtract the first one from the second over1 minus2 z minus1 over1 minus z。

 that's the generating function for powers to2 minus1。So with each one of these operations。

 we enrich the set of sequences that we know generating functions for。Differentiation。

 that's another thing if we have a generating function a of z equals aKz to the K。

 if we differentiate that， that's z a prime is z that's k aKz to the K。

 that's the generating function of this sequence， A1，2A2，3， a3， and so forth。

So and then that's a useful operation that we can use again to get generating functions for more sequences。

 so for example， if we start with our simple geometric sum for the sequence that's all once and differentiate that。

Differentiate the left side。 It's z over 1 minus z squared in the right side tells us that's the generating function for the natural numbers sequence 0。

1，2，3，4，5 and we can do that again。 we can continue differentiating and get a richer set of functions。

 So differentiate again it's z squared over 1 minus z Q。

And that's the generating function for the binomeomeial coefficients。

 and choose 2 n times n -1 over 2。And actually we can get a generating function for binomial coefficients on the lower index by differentiating M times in this way。

 and you can check that out， the generating function for n choose M is z to the M over 1 minus z to the m plus1。

And as we saw， special number sequences like the binomial coefficients arise when we're studying algorithms and combinatorial structures。

 so with generating functions we can work with all these kinds of sequences with just one function。

So。Oh and this is just dividing by dividing out Z to the M。

 we get a slightly different look at that same generating function。

We'll have use for applying all of these equations， which are in tables in the book later on。Okay。

 we can go the other way and we can integrate if you have a OGF， if you integrate it from0 to z。

 if you do a term by term in the definition， you see that that gives us the OGF of the sequence a1 over 2a2 over 3 and so forth。

So taking our standard， integrating it on the left， it natural log of1 over 1 minus z on the right。

 it's the sum z to the n over n or the generating function for the sequence， one， one half， one。

 third， one fourth， and so forth。So that's integration。

And we can actually integrate more and get more answers。

 but let's look at another thing and that is partial sum if you have a generating function and you multiply by 1 minus z。

 then you get the generating function of the partial sums of the sequence。

 so the original sequence is a0a1 and so forth， partial sums are a0 plus a1。

 a0 plus a1 plus a2 and so forth。Let's look at a proof of that fact。

 so that's just writing down the definition of the two sequences。

1 over 1 minus z is some k bigger in0 zk and A of z is by definition some in gradient or A and ZN。

 so we have the product of those two sums。So we distribute to bring in the powers of Z together and give us that double sum。

 then the next thing is to in the inner sum change n to n minus k。

And so then we have a n minus k and z to the n， so there's only n in the exponent of z。

And then switch order of summation， so k bigger than equal to 0 n bigger than equal to k。

 if we switch order of summation， that's the same as n bigger than0。

 but K restricted to B between 0 and n。And then in that inner sum， we can change k to n minus k。

 and then we see that we have the partial sums， so the generating function。

 so this product is the generating function of that sequence， which is the partial sums。

So that's another fine operation to be able to perform。

 to give us a richer set of functions of sequences that we know generating functions for。

So for example， if given our two of the generating functions that we've already derived。

 two of the sequences that we've already derived generating functions for。

 if we multiply those together or1 over1 minus e times log 1 minus E。

 we get the generating function for the harmonic numbers。

Harmonic numbers is sum from of k goes from one to n of over1 over k。

And we saw that the harmonic numbers arose in the analysis of Quick sort and they actually arise in many places in the analysis of algorithms。

 and now we can represent them with that single function。

 one over1 minus z natural log of1 over1 minus Z。And that partial sum idea generalizes to the idea of a convolution。

 if you have any two generating functions， you can multiply them together and you get the generating function for this convolved product。

 some from where the nth term in the sequence is some from zero goes from K to n of aK， Bn minus k。

And here's the proof of that， it's just pretty much the same as the proof that we just did for partial sums where we distribute。

 then we change in the inner sum， we change n to n minus k。And then we switch order a summation。

 and that gives us the convolved product。So that's convolution。So for example。

 if another way to derive the generating function for the natural numbers is just to square the generating function for ones。

 and then that you can do the math to see that this canvol product is just n plus one in that case。

 that's a different way to derive the generating function for the natural numbers。

So that's a convolution。So the summary is that we can do what's called expanding a generating function by expressing an unknown generating function as a power series。

 that's finding the coefficients。And you can look at what we've been doing as both directions。

 given a sequence what's the generating function or given a generating function， what's the sequence。

 so let's look at the first one， given the second one given a generating function。

 what's the sequence。What we've really been using is Taylor's theorem that if you can differentiate the function。

 then you can expand it and know the coefficients of z to the n it's just the n derivative of the function divided by n factorial that's really what's behind the series that I gave for e to the z is z to the n over n factorial or for one over one minus z。

 the geometric series， the derivatives give factorials and the cancel't out and you get1 so you can get your basic starting point from the Taylor theorem usually and thats that's what I just mentioned。

 but also you can reduce to known generating functions as we did for example。

 if we have one over one minus z natural log of one over one minus Z。

 we know how to find the coefficients of Z to the n in that by the process of convolution。

So that's a summary of what we do to find coefficients given a generating function。

And so the other way， if we're given this sequence， how do we find the generating functions。

 the same is just the same thought just to work the other way。

 we integrate one over1 minus z to get the generating function for1 over k and then convolve it with 1 minus z to get our generating function。

 so that's working with generating functions just using the basic operations that we've talked about。

So here's an exercise that you should think about to cement your understanding of the idea of ordinary generating functions and the sequences that。

The sequences that they。Represent。So let's prove that using generating functions。

 prove that the sum of the harmonic numbers from k goes from one to n has this value remember when we talked about solving recurrences we said that we going to find that we're going to have sums that we need to evaluate on how we're going to evaluate a sum like that if it's going to turn up and generating functions are a reasonable tool for doing something like this。

 so think about if you can solve that problem to apply your understanding of the last couple of slides in the lecture。

So what we do is for the left hand side， So what's the generating function for the left hand side Well。

 we know the generating function for the harmonic numbers。

 that's one over 1 minus z log of1 over1 minus Z。 If we multiply that by one minus Z。

 then we get the generating function for the sum。 So first thing that gives us the generating function for the left hand side。

So now to what we want to do is we want to extract coefficients from that generating function in a different way。

 and what we'll do is we'll convolve natural log of 1 minus z with1 over1 minus z squared to get the coefficients。

So that tells us right away that the coefficient of z to the n in this it's a convolution。

 it's sum on K， the coefficient of z to the n in that one well n minus it and the coefficient z the n and that one1 over K。

 so that's just a convolution of simple convolution of those two generating functions It's a sum but it's all the pieces of that sum we can do we just have to do a little bit of math It's n plus1 times h of n that's the first term and then minus k over k and there's n terms it's just minus n and then just need to note that H of n is h of n plus1 minus1 over n plus1 and then a little algebra gives us the solution。

So that's an introduction to ordinary generating functions and some calculations that gives us useful ways to work with sequences and evaluate sums and do other operations just because of the idea that we can represent an entire sequence with a single mathematical function。



![](img/a522ca107739d02821533cd57db21422_2.png)

![](img/a522ca107739d02821533cd57db21422_3.png)