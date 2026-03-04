# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P27：27_07_03_实证分析.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/e0c47ff1cd60e22019f50f54a9ed49ab_0.png)

Well， we've got a working program and first thing we can do to study its performance is to run it in some kind of controlled way。

So in order to do that we're going to need some kind of representative inputs。

 so one thing that we could do is to collect the actual input data that we want to run the program on or another one that we'll use for now is to write a program thatll generate representative inputs either option is fine with option option two in this example we have a little bit more flexibility。

So here's a program that's going to generate input for a three sum program and all we do is we take a value M。

 which is the range of our integers from the command line， and then we take n from the command line。

 and then we simply print integers， they're uniform randomly distributed between minus M and M。

So if we run this with value of n value of n， we get n integers in the range minus m to M and this provides good flexibility。

 for example， if we take m equals a million this is 10 integers between minus a million and a million。

 and in that kind of input even if we have a lot we're going to have not much chance of getting a3 sum which might be representative of some problem that we're solving。

On the other hand， if we make the range small， then we get a lot of integers。

This is between minus 10 and 10，10 integers between minus10 and 10。

 we're going to have a very good chance of getting a three sum so there'll be lots of three sums and maybe that models some other input situation so with this input generator we could do a lot of testing of our program not just for performance but also for debugging so that's always a first step is to try to think about what the inputs are going to be like and write a program that you can use to generate inputs for your program to test it。

So first thing we can do we've got a running program is we'll just run it。

 we'll just run some experiments， we'll start with a moderate input size。

 measure and record the running time so it on end to be large enough that we can observe the running time and then double the input size and repeat and see what happens then when we're done with that after a while it'll get very slow。

 we can tabulate and plot the results。So the way that we measure the running time is add calls to Java's current time and milliseconds function。

 which gives us the current time in milliseconds， divide by10 gives the current time in seconds。

So before we call our function， we save the current time in a variable start。

After we call our function， we saved the current time at that point。Another variable now。

And then now minus start is the amount of time it took to call for our function to compute the number of triple system to zero in our array。

So。For example， if we run for  a000 numbers between minus a million and a million。

 it finds 59 triples and takes not a measurable amount of time in seconds。

 but if we double the input size to 2，000， then it takes finds 522 triples， but that takes 4 seconds。

We double it again， finds about 4，000 triples， and takes 31 seconds。And double it again。

 now it's taking substantial number of seconds， so that's about four minutes。It finds 31000 triples。

 So now we're ready to see what the plot of these results looks like。 So we just。

Plant time versus problem size， and we get this curve， which is the empirical analysis。

 the result of experimenting with our program。Now I just want to point out that there's no excuse for not doing experiments with computer programs because the cost of doing experiments is almost free compared to other sciences if you're doing a chemistry experiment or dissecting in the animal or setting off an atom bomb。

 those are generally very expensive experiments。But a couple of lectures ago。

 we did lots of experiments just to study our self avoiding walk paradigm。

 so whereas they only get to do one experiment， we got to do a million even in an early lecture。

There's no excuse not for doing experiments to understand costs in computer science。

So I just want to reinforce that point where really I have the luxury of doing lots of experimental work to try to understand what's going on and not much cost。

So now let's analyze our data and again， we're in better shape than a lot of scientists because we can generate really a lot of data if we want to。

So what we're going to do is we're going to use a log log scale。

So we'll see how that works in just a second， this is actually common in trying to understand experimental data。

So we have our in and the amount of time that it took。

And then we just compute the binary log of both of those。

And then we'll plot those numbers in the right most two columns。And when we do that。

 we get a straight line。So this gives us a way to fit a curve that these points fit。

So if the points are on a straight line in a log log pot。

 it means that there's going to be a curve of the form A and to the B for some constants A and B。

 and this is really how much simpler than it looks in this case， the straight line is of slope3。

That that means that the exponent is three， so the running time is proportional to a constant times in Q。

And then what we can do is use the data to solve for A， so here's the math in this one。

So the fact that the line is of slope3 means that log of the time。Is equal to log of a plus 3 log n。

And so that x intercept is that constant log A。And that's the equation for just the equation for a straight line of slope3。

 So if we take two to a power of both sides， you get T sub n equals a and cubed。And so now。

 say for 8，000， we plug in t sub n is 248 is a a times 8000 cube。And you solve for that。

 you get a equals 4。84 times 10 to the minus 10th。So， that means that。

We think that from doing this math， that the data， the time to solve the problem for input of size n is going to be about 4。

84 times 10 to the minus10 times n Q。And we can plug our values of n back into to that curve and see that sure enough。

 we get a really exact fit of the data。So。That's a lot of information。

 our experiments give us an idea of what the running time might be。

 even for values of N that we didn't run experiments for。

So the scientific method that's what we say is let's form a hypothesis that that's what the running time is going to be no matter what end is。

So for example， we could use that to predict， so if we double the next time。

Then we can plug in n equals 16，000 and we're saying we think that's going to take 1982 seconds to solve the thing for n equals 16。

000， so that's quite a bit of time that's half an hour or so。

 and we could actually do this math while we're waiting for the thing to run for 16，000。

And so sure enough， if we run it and go out to lunch and come back， it takes 1985 seconds。

 so that's nice verification that our hypothesis might be correct。And now bolstered by that。

 we can say， okay， how long is it going to take for n equals a million， and the answer is， well。

 it's going to take 484 million seconds and you can just type that in your search window nowadays and they'll tell you that's about 15 years。

So by running some experiments we're able to predict and now we have a good idea of how long our program is going to take for this value of n equals a million。

 so the question can you use this program to solve a problem for a million points。

 the answer is not unless you're willing to wait 15 years。

There's just one other hypothesis that I want to mention this if you ran this。

 I didn't actually run this experiment， particular experiment in the 70s。

 but if you were to do so on an old computer that's much slower。

 you could do smaller values of N but you get a different formula because the computers's slower and way slower。

 so this is what it might have taken on a Vax 11 in the 1970s。

 and it's five times 10 in the minus6 times N cube seconds。

Whereas the experiment we just talked about the computers 10。

000 times faster and it's 10 to the minus constant 10 to the minus 10 seconds。

 but the curve looks the same， and so there's a hypothesis in there that we're going to think that the running times on different computers generally are going to differ only by a constant factor so this analysis doesn't depend so much on the computer。

 it's only the constant that depends on the computer and we'll come back to that idea a little bit later when we look at mathematical analysis to try to validate these kinds of results。



![](img/e0c47ff1cd60e22019f50f54a9ed49ab_2.png)

![](img/e0c47ff1cd60e22019f50f54a9ed49ab_3.png)