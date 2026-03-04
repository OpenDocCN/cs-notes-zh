# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P30：30_07_06_熟悉示例.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/a07a849fe58cbad3a0febb90f1e3f57f_0.png)

We're going to see many， many examples going forward。

 but let's finish up with a couple examples from programs that we've already seen。For example。

 the gamblers ruin， so how long is it going to take to compute the chance of doubling a million dollars。

 betting a dollar at a time？Again， to figure this out。

 we put in the timing code in red in there that estimates how long our program runs for given a dollar amount and we can just run it so this is for doubling 1。

000 and now we do $100 trials to damp out the possibility of other things going on in the computer and also to get a more accurate probabilistic estimate。

 so we're doing 100 trials we run it again and we compute， we double to $2，000 and。2000 experiments。

And then we compute the running time in the ratio， then we double to 4000。

 which is our initial stake， compute the running time in the ratio。

 and as we go we notice that the ratio of running time seems to be about four。

And that coincides with our math model that we talked about since the running time should be proportional to n squared and now we have a running time for just significant large value of n that it' going to kind of stabilize and tell us what the constant is on the particular machine we're using and we can just use the constant4 to extrapolate to the next higher values and to get to a million it's four to the six and so it comes back to the same kind of result 4。

8 million seconds to run this program for a million it's about two months so maybe we have two months or maybe we want to work with some smaller number。

 but we have some understanding of how this program is running and we can use it to quickly predict what the running time is。

So here's just another simple example， it's the same thing。

 suppose we have these observations now our ratios are all four and if we want to get for 64，000。

 we just keep multiplying by two to get to 64，000， keep multiplying the time by four and then we get to 20。

000 seconds and then what's the order of growth。Well。

 that ratio is 2 to the B if the order growth is n to B， so in this case B is 2。

 so it's going to be n squared。Just take the binary log of that ratio and that gives the order of growth。

 so that's the example of simply running the experiments。

 doing the extrapolation and learning the order of growth from the ratios。

What about coupon collector， How long does it take to simulate collecting a million coupons？

And again， we just add the timing same way as before， find the time before we start。

 find the time after we're done and run it for。Different numbers of coupons。

 So now we have to run it for a pretty high number of coupons to get something interesting。

 So it's 125000 takes7 seconds 250，000 takes 14 500000 takes 31 the ratio is looking like two so that means to do a million we just double it and so takes about a minute to simulate coupon collector for a million coupons。

 and again， the math model says it should be about n log n so that matches with the doubling ratio being two because it's only the exponent of n that matters。

So these programs， the gambler and coupon collector look quite similar in many ways。

 their experimental results， but with the doubling test。

 we can very quickly get some understanding of their performance， which is quite different。

So about one minute to do a million coupons now in this case you can run out of memory before you run out of time and I should mention that another thing that we often have to do is analyze memory requirements because as in this example。

 a program might take a lot of memory。So that is very system dependent but we can for Java programs usually come up with a decent estimate of the memory requirements of a program。

 so the basic unit of memory is a bit， but actually in Java it's a byte the smallest addressable unit that's8 bits。

And your computer maybe has a gigabyte or about a billion bytes。

 ancient computers had a megabyte or about a million bytes。

And then you just have to know for each primitive data type。

 how many bytes are used to represent a data type value and actually in Java， a Boolean。

 even though you think it should be one bit actually uses a whole byte。ARr uses two bytes。

 it's in Uniicode， 16 bits， and int uses4， floatat also uses4， long uses 8。

 double uses8 and so forth。And then data structures depends on the system。

 you have to do some experiments with your own programs。

 but a typical array of n ins is going to use4 n plus 16 bytes or four doubles is8 n plus 16 so it's eight bytes for each double plus some overhead to handle the array and then if you use multiple dimensional arrays then we can use the tilde to really it's efficient in terms of an n by n array it' got n squared things and if each one of them are take four bytes it's about four n squared bytes and so forth。

String has higher overhead， and you can work it out for different systems。So。So for example。

 a 2000 by 2000 double array uses about 32 megabytes and you can do these kinds of estimates if you have programs that start to use significant amounts of memory。

So the summary is you can use experiments， you can use mathematical analysis and the scientific method and the simple doubling experiment approach that we discussed to figure out whether your program might be useful to solve a large problem。

If it's not fast enough， then you you might want to buy a new computer。solve bigger problems。

 if it that's if its if it scales， that is it is running time in log n or N。's run。

 if it doesn't scale， then you got to look for a better algorithm。 maybe there's one out there。

 And if you find one， then you can go back and iterate this process。 And if it does scale。

 then you're fine。 if you can find one。 well， maybe you can invent a better algorithm。

 that's a worthy thing to think about anyway， because there's many more problems。

 then we know algorithms for solving。For example， we don't know how to solve a threesome problem efficiently as efficiently as we'd like。

We can solve it in square， but not less than that。So that's a basic summary and just a particular case in point。

 it wasn't that long ago， there were two computer science grad students at Stanford that had a program to index and rank everything on the web so as to enable search on the web。

And for a while they were doing pretty well with that by buying a new computer solving bigger problems。

 but they weren't quite at the point where they're changing the world so what they did was invent a better algorithm and iterate the process for a while。

 that algorithm is known as page rank and it's discussed in the book those grad students where Larry Pageage and Sergey Bn and that led to Google which certainly has had a major impact on the world and the lesson of this is that performance really does matter if you're going to address a large problem。



![](img/a07a849fe58cbad3a0febb90f1e3f57f_2.png)

![](img/a07a849fe58cbad3a0febb90f1e3f57f_3.png)