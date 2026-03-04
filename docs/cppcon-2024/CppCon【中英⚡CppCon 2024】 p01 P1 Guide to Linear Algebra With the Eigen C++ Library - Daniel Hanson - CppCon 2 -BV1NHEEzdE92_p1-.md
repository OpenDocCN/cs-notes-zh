# CppCon【中英⚡CppCon 2024】 p01 P1 Guide to Linear Algebra With the Eigen C++ Library - Daniel Hanson - CppCon 2 -BV1NHEEzdE92_p1-

🎼All the presenters， everyone that attends this conference is so friendly， so willing to teach。

 so willing to learn from you too， so it's not just watching these videos。

 it's kind of getting that insight afterwards and around at dinner at drinks。

 like all the other aspects of the conference besides just like that technical information。😊。



![](img/150a29fa8a0a8c25b979a270be1b9e5a_1.png)

Okay， well， good afternoon everybody， welcome， thanks for coming。



![](img/150a29fa8a0a8c25b979a270be1b9e5a_3.png)

As you can see， we're going to be talking about linear algebra in C++ and in particular the eigen Library。

 but we'll also get into some few other topics related to linear algebra。So just a little outline of。

How I thought we'd proceed first， I thought I'd help if I bring it up。

 I thought we'd go through like a short and high level history of linear algebra and C++ going back to around 1998 and then up to the present day。

Well then shift focus to the Eigen Library， which is the main point of this talk。And then。

We'll look at。The new linear algebra interface coming in C plus plus 26， Itll just be。

High level basics， but。We'll also look at how it can。Work together with Eigen。Okay。

 so just a few disclaimers and caveats。This presentation is more on solving problems using the Eigen Library and what's called the St B proposal in C++ 26。

 so I'm not affiliated with eigen。I've used it in financial programming。

 That's my background and in teaching。 So I'm not an expert on the source code。 I'm not an expert on。

On expression templates。But。I should also point out that， again。

 as I mentioned my backgrounds in finance， so there will be a couple of examples that come from that domain。

But I think that they'll be。嗯。They should be fairly straightforward and reasonably clear。

 so they could be applied to any other。A number of other domains。嗯。

So my goal here is just to share some things that I know。

And some topics that I thought you might be interested in。And hopefully useful。



![](img/150a29fa8a0a8c25b979a270be1b9e5a_5.png)

You have to excuse me。I think being high and dry in Denver is kind of caught up with anything。All。

All right， so。Let's take a little trip back to 1998。

 and we will fly back with the queen of the skies at the time， the Venerable 7，47，400。

And around this time。The Hal 9，000 computer was operational at the University of Illinois research facilities in Champaign。

 Urbana。Since then， though， they've came out with this miniature version that。Can show you here。

I'm sorry that。嗯爸妈。嗯。嗯。Anyway。You probably had one of those big， heavy CRT monitors and。

Probably running Windows 95。And we were。Just building up to the dot com bubble。

 which two years later popped。So some of you might remember that。嗯。All right。In 1998 around then。

C++ is really growing in popularity。And especially in financial programming， it's really， really big。

 you know， the。The financial software companies and financial institutions are。Eager to adopt C++。

But。For those of us who。We're in quantitative programming。 So like。

Option pricing models and risk management， that sort of thing。

We found that there was no support for linear algebra。So kind of left us pining for Fortran。

So your options at the time essentially work， you could。Write your own matrix class and operations。

Or you could try to convince your boss to buy a commercial library。

So I thought I'd go through a few of the open source linear algebra libraries that started to appear in the early 2000s。

What I'm going to go through here， though， it's not an exhaustive list。

 These are just libraries that I'm familiar with， a few I've worked with。But there are。

 this is by no means an exhaustive list， there are a number。A few more。

But the first one that I worked with was the U B library。In， in Bo。

 and Blaaz stands for basic linear algebra subroutines， which have their origin in Fortran。

This was released in November 2002。It。Had the bs functionality， and that meant。

Matrix and vector representations。Matrix addition and subtraction。Mattrix multiplication。

 and there were several types， so matrix by matrix， multiplication， matrix by vector。

Vectctor dot products。And scalar multiplication。It also computed matrix and vector norms。

So you were still on your own though， for linear solvers and matrix decompositions。

The authors themselves on the Bo website state that it offered good but not outstanding performance。

So I did use it for a project， it wasn't bad， I just found it a little difficult to figure out how to use it。

Also as they have on the website。Its last major improvement was in 2008。So if we move a little bit。

Further in time of what we'll call next generation linear algebra libraries， and again。

 this is not an exhaustive list。Eigen came out in 2006。Aradillo in 2009。

And then later was the Blaze Library in 2012。These are all expression template based libraries。

 Aradililla was not originally， but as I understand it， they've moved。Towards。

More of an expression template based library。Sorry， excuse me。嗯。

So they include the usual bs functionality that。I mentioned previously。Plus。

 number of decompositions and solvers。 So things that you might have found in the old LA P libraries in Fortn。

I've not used Blalaze， but I attended this talk in 2016 CPP Con when we were back in Bellevue。As是。

A bit more convenient for me， but。could just roll out of bed。I get my car and drive over。Anyway。

It was a really good talk and if you want to learn more about it， highly recommend checking it out。

But interestingly， he。Did performance tests against a number of different libraries。

 I can't remember something like 8 to 10 different libraries。And， interestingly。

One of them was eigen， and interestingly， it placed actually quite high。

 was it was above most of the competition。Okay， so now bring us back to the present day。

I'm going to mention MD span。This is how they describe it in the proposal。Essentially。

It can impose a non owning multidimenional array on a one dimensional。Contiguous me container excuse。

看看。他是。Afraid that's going to happen。嗯。嗯。Sorry。So for example， you could have a vector。Stood vector。

 and you could impose then a two dimensional。Structure on a one dimensional vector。

And that can represent a matrix。You could also use an eigenvector Xd type。

 which we'll talk about shortly。

![](img/150a29fa8a0a8c25b979a270be1b9e5a_7.png)