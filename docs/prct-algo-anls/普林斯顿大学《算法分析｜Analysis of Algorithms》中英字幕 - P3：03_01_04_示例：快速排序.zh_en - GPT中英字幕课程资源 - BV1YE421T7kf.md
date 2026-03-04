# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P3：03_01_04_示例：快速排序.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/16dbf17db8914f680b453011cd65d7ee_0.png)

Next， we'll do a complete example of the analysis of algorithms。

 a classic analysis of perhaps the most widely used sorting algorithm， Quick sort。

So this is the code for QuickSt right out of section 2。

3 of our algorithms book and I encourage you to download that code from our book site and I'll talk more about just how to do that later on。

It's a recursive method down at the bottom， the sort method that is based on doing a process called partitioning。

 which is the third line from the bottom， partitioning takes an array to be sorted and divides it into two pieces at a position J with the property that every element with an index less than J is less than a of J and every index with every element with an index bigger than A of J is bigger than a of J or maybe equal。

 so if partitions the array into those two parts， and if an array has that property then you can get it sorted simply by making the two recursive calls that do the sort sort the left half。

 sort at the right half。The partitioning process is handled by running two indices，1 I and 1 j。

 I going from low to high and j going from high to low， and we simply scan from the left。

 incrementing I as long as we have elements that are less than the partitioning element which we put at a to low to start up。

And then scanning from the right， as long as we have bigger ones。

 if we found a small one on the right and a big one on the left， we exchanged them。

And then we keep going until those pointers cross at which point we put the actual partitioning element into the place。

If you're not familiar with that， read about the details in Alrith's 4th edition or on the book site。

 that's a quick review。So we have to make some preliminary decisions when we're going to study that kind of code and so the first thing is the cost model and cost we're going to talk about is the running time but really it's better to come up with an abstraction that we're not really talking like about microseconds or seconds but we want to do is talk about something abstract and for sorting algorithm what it is is compares what the algorithms doing most often is comparing two items so let's just count compares and then the work we do for counting compares takes us from time to just a discrete counting process and that will mean that our analysis is valid for any kind of machine at all we get the frequency of execution that compares and then the time is just how quickly can you do a compare that all rolled up into the constant。

So our hypothesis is going to be if the number of compares is C。

 then the running time is tilde AC on any computer。

 now A is going to be different for different computers or different systems or different languages。

 but it's a reasonable hypothesis and it bears out in many， many practical situations。

So that's a big decision at the beginning to get away from time and get in something abstract associated with the algorithm without losing the ability to make some scientific studies later on。

So the input model， we're going to assume the input to be randomly ordered。 And as I mentioned。

 in the case of sorting algorithms， that's pretty easy to arrange。 We just randomly order them。Also。

 just to make the math simpler in this first cut， we're going to assume the keys to be all different。

 that's not always so easy to arrange and I'll have more to say about that in a little later。

So it's a key question are these assumptions realistic and I think the answer is we'll get into that。

 but we made these assumptions and these models with the knowledge that we're going to be able to test them scientifically and we can go ahead and do that and that's part of the process that I'll describe。

So the bottom line from this slide is that we're going to count compares and we're going to assume that the keys are randomly ordered and distinct。

So in that context now there's some relevant questions about this quick sort code。

 so we're going to assume ray ofs n entries distinct and randomly ordered。

 so first question is let's break out the partitioning process。

 so how many compares are involved for this partitioning process。Well。

 that doesn't take much analysis to see that what happens is that every item in the array is touched in order to get the partitioning done and actually there's one extra because there partitioning elements crossed。

 so it's M plus1。So that's one relevant fact。Now， if they're randomly ordered。

 what's the probability that the partitioning element is the k smallest for any particular value of k。

 Well， if they're randomly ordered， then it's going to be the same for each values of K。

 it's going to be1 over n， no matter what K is。So that's another relevant fact。u。Now。

 what about the what's the size of the subs if the partitioning element is the ks smallest Well everybody to the left is less。

 So there's k minus1 of those and everybody to the right is bigger。 There's n minus K of those。

 Add those together， You get n minus-1。 and then there's a partitioning element gives n。

 So that's a relevant question that we need to know the answer to。

 What's the size of the subrays in that case。And then there's another detail that takes a little bit of thought。

 and it was a problem in older implementations， but you need the subars to be if they were randomly ordered before。

 are they randomly ordered afterwards and this implementation doesn't do anything that would disturb that so the answer of that is yes。

So with these questions， we can transfer the problem of counting the number of compares needed by Quicksort to a pure mathematical formulation of the problem。

So it's a recursive program that has a random input model and it leads to a formula called a recurrence relation。

 and we'll look at recurrence relations in detail later on。

We got n entries distinct and randomly ordered if we let CN be the expected number compares used by Quicksort。

 then we can write down an equation for CN that is a mathematical model that reflects the recursive model of the program itself。

You need n plus1 compares to do the partition so that's the first thing then for every possible value of k。

 that value is the partitioning element with probability 1 over n。

 and then it leaves two subars to get partitioned to get sorted afterwards and those are randomly ordered so the cost of doing the left subarray。

 which is a size k minus1 is just c sub K minus1 and the cost of doing the right subar is c sub n minus k。

So that's a formula that describes the running time， that number compares used by Quicksortt。

 there's one more detail if there's only one element we don't do anything and so we have to make sure that we define the small values of N appropriately。

But what this has done for us is taken our program and our abstract problem and so forth and reduced it to a mathematical problem。

 we have to be able to solve mathematical problems like this。

 and so that's what we're going to go into next。So I'm going to do it for this specific recurrence and then in a couple of lectures we'll talk more generally about how to solve problems like this that's a mathematical problem Cn equals in1 how are we going to possibly approach something like this now in this one there's a couple of tricks that get the job done and I'm not going to try to explain the origin of those tricks what I want to show is how simple the calculation is but we'll get this thing solved in just a couple of slides。

So the first thing to notice is the sub fileses are really kind of the same and actually if you kind of write this out in different notation。

 both of them are C0 plus c1 plus do plus cn minus1 that is the sub fileses could be any one of those sizes with equal probability so the two sums are the same so you can reduce it to just one sum with a factor of 2 over n and the one of n is not inside the sum。

 so that's a simpler form right there just the observation either just totally mechanically that the two sums are the same or you can argue more broadly that there's no difference between the two sub filesles so you could start with this one if you want it they're symmetric。

Okay， now the next thing that's complicated is this n and the denominator。

 So what we do is multiply both sides of the equation by n。And so that's just multiplying by end。

 there's no problem there。Now the next trick is to get rid of the sum。

And the way that we're going to get rid of the sum is write down the same formula for n minus1 and then subtract。

So if we do that on the left， we get NCn minus n minus1 cn minus1。

 same formula for n minus1 on the left， and then on the right， this term。

 n times n minus1 minus n minus1 times n just leaves2 n。So that's a little algebra。

 And then what' the reason we did it is if you take this formula for n and subtract the same formula for n -1。

 all that's left is just one term on the right， the 2 cn minus-1。

 So now we have a recursive recurrence relation that has no sum in it and that's clearly going to be much simpler to deal with and then just collecting terms we have this very simple recurrence relation describing the number compares taken by Quicksortt at the bottom it's not a solution yet。

 but it's way simpler than what we started with and certainly way simpler than scratching our head looking at the program trying to understand how many compares that it takes。

And so actually， this is a pretty good milestone in the analysis of this algorithm because we've got now a pretty efficient algorithm for computing the result。

If we try to compute the result from the original recurrence it'd take quadratic time。

 so that's the code and I'll talk more about using code to learn about recurrences but in order to do N you have to do a double four loop you have to for every n you have to do for every K quadratic time。

 so we can use that to try to estimate the value of Cn for say n equals a million we don't have a million squared cycles even on past computers today or a billion or a trillion people are trying to sort files that much so so we would want to be able to compute it but that original thing is not good enough to do it。

 but with the manipulations that we just made we have a linear time algorithm for computing it just start at zero and just use this formula to compute later。

Values， so we might not know too much about what it is。

 but we know enough to calculate the number of compares for anyEN just by running this simple program and it is interesting to think of really I talked about suppressing detail really what we want is a fast way to compute the running time of a program and this is a good there's a lot of algorithms we like to be able to get this far on。

Actually， we're going to have much， much faster way。

 We just want to compute it with just evaluating a few elementary functions。

 So let's look at how to do that next。So now we're going to actually solve it。

 so that's we're going to express this quantity in terms of familiar elementary functions。

 So how we're going to do that。Now the first step is a magic step， it's kind of tricky。

 but actually there's solid motivation for it that we'll talk about later on。

 I'm going to take both sides of the equation and divide by n times n plus1。So on the left。

 NCn divided by n times n plus1 is just cn over n plus1 On the right， the n plus1s canceled。

 we get cn minus1 over n， and then 2 n over n times n plus1 is just 2 over n plus 1。

That looks like a little bit more complicated form。

 but it's actually a much simpler form because the first term on the right is the same as the term on the left is just with n reduced by one。

And what that means is we can apply this same formula to that term。

And so if we apply that same formula to that term， then so thats cn plus 1 equals c 2 minus1。

 if we plug in cn minus1 equals cn minus2 over n minus1 plus 2 over n， then we have that formula。

 and then we can continue doing that until we get down to our starting point， C1。

And then there's no unknowns on the right hand side， and that's a solution。

The simple version of this solution there's a small constant term left out is that CNn is tilde2 n times the sum from k from1 to n over 1 over k minus2 n and that's just running that out and then multiplying by n plus1 and doing the sum that's a simple version with no unknowns on the right now this looks more complicated than what we started with because it's got a sum back in there so what do we do about that Well with sums often simple sums we can approximate with integrals and again this may be familiar to many of you but certainly we go into the math behind approximating sums with integrals so this is close to integral of1 over Xdx plus gamma which is Oulers' constant which is about 0。

57721 and that gives us a formula for C。With in terms of familiar mathematical functions。

 it's 2 and natural log n minus this constant times n， and that's a Cn is tilde of that value。Now。

 there are approximations and we will be talking about how to be precise about making these approximations。

 but this is other than that， this is fairly straightforward mathematical manipulations that get us to a solution for the number of compares used by QuickSot。

So now even when we're just doing math for the analysis of algorithms。

 we can always check our math with a computer and that's always worthwhile I said I'm claiming that this is pretty close to CN Well I can just write a program to compute this that's to map that log and Java is natural log of n minus and look a boiler's constant that's a value and I can also as I mentioned。

 compute the actual values of CN and then I can just print out a table and sure enough that's a check we're within 30 for a million that's pretty close and we could actually get closer if we want it。

That's the first thing that's wonderful about the analysis of algorithms even for beginners。

 is that you can always check your work。It's very specific what this thing is and you're saying I think I have something that's close to it well you can check and then you can know and then you can have confidence to move on so that's the first thing so that we've checked the math but there's one other thing that we have to check and that's to check the model and so we thought that if it's randomly ordered distinct keys that should be the running time so what we'll do is we'll run the code and this is a thousand trials for each value of n for n from one to I don't know1 thousand I think and there's a gray dot for each trial in this plot and you can hardly see the gray dots with a red dot right in the middle which is the average for each n so that's what the experiment gives us is actual results which is the number of compares。

And then what we want to compare that against is this function。

 so we can just plot that function and boom it's right on。

Run the algorithm here we run the algorithm maybe a million times。

 and that experiment shows us that the formula that we got for the number compares is right on。

So that's checking the model and very successful in the case of Quicks。

So just as an observation that maybe we're not just interested in the average cost。

 maybe we're interested in the distribution of costs。

 how likely is the actual thing supposed be to how close is the actual running time of my one sorting problem going to be to this average。

 and you can see from the narrowness of these gray dots is that it comes pretty close to the average。

 it's very typical in the analysis of algorithms that standard deviation is slower growing function than the average and so it regresses to the average as in increases。

 but there's interesting mathematical questions， plenty of interesting and challenging mathematical questions when we start looking at problems like this。

 what is the distribution of course， most people would say， well， maybe it's a normal distribution。

 maybe it's a bell curve？But it's not normal and actually it was only 10 years ago after Quicksword was discovered in 1960 and people were looking for a long time to try to understand is it normal and it's actually not normal。

 so that's the exact distribution from the recurrence which we can compute。

 not just the probability that the averages certain value we can compute for every k the probability that it takes exactly k comparisons and then what this plot is is taking those curves and centering them on the mean to get an idea of what kind of curve we come close to and it's not a bell curve。

 it's kind of a tail off to the right。And actually。

 this is just an empirical validation of running again a million sorts just to show that the actual behavior is like that。

 And that's an interesting mathematicalematic。 What is this curve， It's a new function。

 It's not a normal distribution。 It's definitely worthy of mathematical study。 After all。

 this is probably one of the world's most heavily used algorithms。

 we might want to understand this property of it， maybe that'll help us understand something else in the future。

So the bottom line from all of this work， and this is just a summary of the 50 years of research on QuickSot is that really a lot is known about the performance of QuickSot and there's plenty of interesting research problems in the literally thousands of papers that have been written about QuickSot in the 50 years since it was discovered。

And that's not the end of the story and I want to have two more comments so the first one is about prediction and this is something that we teach in the very beginning of the algorithms book that just using hypothesis like this makes it simple to predict performance even of extremely complicated algorithms on in extremely complicated scenarios So if that's our hypothesis what we're going to do is run the experiment for some input size in。

 some big end and maybe run it a bunch of times to get a good average on the running time if we wanted to that's enough information to solve for a whatever our time is for whatever n is then AZ only unknown and we could go ahead and compute A but actually we usually don't need to even do that we can just predict the time for some constant times in just by doing the math so say we wanted to predict。

Time for 10 n knowing that we have the running time for N。 Well， if you just do the math。

 if we take a times 10 n log 10 n over a and log n， the A is canceled。

 we don't even have to know the constant it says that the running time is going to increase by a factor of 10 plus one over log based 10 of n and this gets smaller as and gets bigger so it's going to increase the problem size by about 10。

 you're going to increase the running time about 10 and that's a very accurate prediction that's useful and that we now teach to first year students in fact we teach to nearly 70% of all Princeton students this simple idea that if you run a program for a big input and you have a decent model for its performance you can predict the running time。

So like， for example， run it for 100000，100 times。 And again。

 we can run as many experiments as we want nowadays。 and it takes four seconds。

So that means that I'm going to predict that it's going to take just a little more than 40 seconds for a million。

So this is an experiment and then I'll run it for a million and takes a little bit longer。

 it takes 40 seconds and I could observe the running time of 41 seconds that gives me a lot of confidence to predict how long it would take for a billion which is maybe the problem that I really need to solve。

 it's going to take 11 hours to solve for a billion。

And that really any programmer can have this kind of understanding of the performance of programs。

 It's all about getting that first model， if all you're interested in is prediction of running times。

 It's very powerful now I'm not saying that we shouldn't have an accurate mathematical model。

 it's also important to have the mathematical model。

 you might want to think about the reason for that and I'll show an example later on and you have an exercise The reason is that there might be parameters that are involved in the running time of the program。

 and we might have the freedom to set the values of those parameters。Even for one parameter。

 and you'll see an example of that in the exercise。

re we can't afford to run experiments for every possible value of the parameter。

 but if we have a mathematical model， then we can use the mathematical model to find the optimum value of the parameter and that's a very strong reason to keep working towards good mathematical models。

Now。As I mentioned， the other thing that really we should do is validate our model in applications。

And not many researchers get down into that place， but more and more nowadays because the running time of algorithms is very important thing to understand for people who are trying to build new internet companies or trying to analyze huge amounts of scientific data So validating the model in a real application is something that goes on continuously in practice by people who have knowledge of the kind of the scientific background of the performance of programs that I've been talking about。

 And for Quickwordt in particular， it's been going on for really a long time。

 I'll just give you three examples from different decades that I've been involved in right when I got out of school。

 I was involved in a project where we were sorting on the Cray1。

 which was the world's fastest supercomputer at the time。

 and this was for cryptography and there was。Unlimited amount of data。

 And one of the ways the crytographers tried to understand the data was to take it in as big chunks as they could get and sort it。

 and as many times as possible theyd sort it。 So you got data that's supposed to be random。

 If it's not random， we can ring a bell and read the code。's supposed to be random。

 And we're sorting it as fast as we can。 And so it was very important to be able to shave every microsecond off that sorting running time。

 And we were in the machines of those days。 and particularly the crray1 wouldn't even work unless every instruction took precisely the amount of time that it said in the manual。

 And we could work with machine language versions of quick sort and predict the running time to within a microsecond。

 which is predicting the running time for doing it a million times to within a second or within a billion times within a few hours。

 It's a fine example of the。A successfuluc application of the analysis of algorithms。

Another example came along in the 1990s when Quicksortt was used as the Uniix system sort。

 and this code is still around and people were very interested in having a general purpose library sort that everyone could use。

And what happened was that a user came along and had an application that violated one of our assumptions。

 he had files that had only a couple of different distinct values in it and his application performed poorly so people went in and looked more carefully and over a few years time John Bentley who was one of the researchers at Bell Laboratories and and some others came up with ideas for addressing this situation and those things are described in the fourth edition of algorithms where we modify the algorithm with a better understanding of it to handle this situation now to go back and do the analysis and refine the model and check scientifically required some serious research and that was only recently that we came to the resolution of how those algorithms performed in practice。

But still that gave library models that gave us much more robust sorting algorithms whose efficiency did not depend on this idea that the keys must be distinct in so much broader use of libraries that was only enabled through trying to get the analysis of algorithms right。

 let's try to get a model that reflects what's seen in applications and that's ongoing just recently was contacted by somebody working in a network colleagues working in a networking startup and what they need to do is sort a billion records that are about a00 characters each that's a and they had to do it fast or their competition would beat them and they' go out of business and he found a refinement to our threeway partitioning methods for strings that was able to improve it even further。

And so again， this is over over 4050 years the analysis of algorithms really helping us to best understand the performance of this important problem now I'm not going to be talking that much about the systemy stuff in this course。

 but I wanted to go through this example in detail because the math is very relevant to what we do in this course and I want to make sure that people are motivated to look into the kind of math that we're going to be talking about so that's a full example of the analysis of algorithms that's quickword and Canuth succinctly express the idea that I want to leave you with for this example people who analyze algorithms have double happiness first they experience the sheer beauty of elegant mathematical patterns that's surround elegant computational procedures just in terms of。



![](img/16dbf17db8914f680b453011cd65d7ee_2.png)

Pure math， what programs bring to the table is another level of interesting mathematics。

 but then if you're in the analysis of algorithms you get a practical payoff because your theories make it possible to get other jobs done more quickly and more economically so it's not just the math it's that the math is helping us press forward in all kinds of important and identifiable ways。

So that's a full introduction to the analysis of algorithms through the study of Quicksortt。



![](img/16dbf17db8914f680b453011cd65d7ee_4.png)