# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P32：32_08_01_受限比特串.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/d1fa843de4aabd2db8f3ace7707ae7e3_0.png)

Next we're going to talk about strings and triess these are combinatorial objects that have really come under scrutiny because of computational applications。

 but they're very well suited to the analytic techniques that we've been talking about。Again。

 we're in the second half of the class and this is lecture8 and we're going to look at these data structure。

 these commential objects as unlabeled classes mostly。

 so we'll be talking about OGFs and again we'll give some examples in lecture but there are many more in chapter8 of the book。

So first thing we're going to talk about is bit strings with restrictions and we did some examples of this as our motivating examples for the analytic combinatorics in lecture5 but what we'll talk about today is answering questions like this so this is a number of random bit strings of 70 or 80 bits and I've got highlighted in there the first occurrence of 000 in each bit string so a natural question is what's the expected wait time that is how many random bits do we need to see before we get to000 in a random bit string or what's some of these bit strings have no zero0 zeros。

think well， maybe not。So but if you look at shorter ones like that this distance then there'd be no 000 so the question is what's the probability that you don't have 000 in an end bit random bit string and questions like this actually have lots of important practical applications where the zeros and ones correspond to electrical signals and certain kinds of devices can take long strings of offs for example。

So let's review what we talked about for the symbolic method for bit strings。

 it' one of the very simplest examples of analytic combininatorics。

 how many binary strings are there within bits， of course they're two to the n。

 and we can do that with the symbolic method by constructing this class of all binary strings B as a sequence of zero or one bits。

And then our normal symbolic transfer takes z0 plus z1 to 2z and sequence of anything of 1 over1 minus that。

 so that tells us that the OGF that enumerates the number of binary strings is B of z equals 1 over1 minus 2 z。

 and so the coefficient is z to the n and that is 2 to the M。

 that's our basic construction for binary strings using the symbolic method。

And then we had an alternate way of expressing the same thing。

 if you say that a bit string is either empty or it's a bit followed by a bit string。

 recursive definition， then you get down to the same result。

And this one generalizes to help us answer questions like how many inbit strings have no two consecutive zeros？

And again， using the same reasoning， we can say that a bit stringing with no consecutive two consecutive zeros is either empty or it's a single zero。

 or it's a1 or a zero one followed by a bit string with no two consecutive zeros。

 that's the natural construction for this class of combinatorial objects。

 and then that translates through the normal translation theorem to this OGF equation。

1 plus z plus quantity z plus z squared times be0 z and then we can solve that and we get a polynomial ratio of two polynomials for the generating functions and ourmp that's a classic example in asymptotic analysis the coefficient of Z to the n in that function is going to be。

 well in this case it's exactly the Fibonacci numbers。

 but in general if it's any polynomials you look at the largest root of the polynomial in the denominator in。

That gives an asymptotic expression for the coefficient of B to VN in that generating function。

So simply by finding the appropriate root of the polynomial。

 we get the asymptotics and for any polynomial it's going to be a form of constant times the root to the anth power unless there happened to be multiple roots so in this case the it's the a golden ratio p to the anth power and then the constant also is explicitly determined that's example that we did in chapter5。

So first thing we want to do today is extend that how many binary strings have no runs of P consecutive zeros。

 and that's going to extend in a natural way， very much like the derivation that I just did。

So the construction then is a string with no runs of P consecutive zeros。

 is a string of zeros of length less than p followed by either an empty string or a one followed by a string with no。

Runs of P consecutive zeros。So that's just a generalization of the construction that I did on the last slide。

 and again that immediately translates a string of zeros of length less than p is 1 plus z plus so forth up to z to the p minus1。

 and then E translates to 1 andBp of z。And so。Solving that。

Equation gives Bp of Z equals again a ratio of two polynomials。

 and again the coefficient of z to the n in that is asympttic to a constant times largest root to the n power where that dominant root is something we can calculate and also the coefficient is explicitly available。

So this no runss of P consecutive zeros， comes down to finding the dominant root of that polynomial 1 minus 2 z plus z to the p plus 1。

And this is using the SAage mathematical system to just find those roots and you can use any system that you want。

 and I didn't calculate the constants。But let's look at- so anyway those are those results。

 now let's look at what we can infer from that result。

So this is a summary of where we were for consecutive zeros。

The OGf S sub P of z is going to be the sum on n， the number of bit strings of length n with no runs of p consecutive zero times z to the n。

 and that we have an explicit formula for that OGF 1 minus z to the P over 1 minus 2 z plus z to the p plus1。

Now this is similar to the situation we had with permutations。

 we can convert that into a probability by appropriate evaluating at appropriate value of the argument。

 if you look at SP of z over 2， then the z to the n becomes 1 over2 to the n z over 2 to the n。

So what that is is the probability that a Bi string of LinkedIn has no run of P0。

 so that's a PGFing just by evaluating the article， the argument at Z over2。

So now if we take z equals1， then that's just summing the what is that that's the sum on n of the number of bit strings n with no runs of p0s divided by 2 to the n。

 which is the sum on n， the probability that the first n bits have no runs of p0。

So and that's the same as the sum of the probability that the end of the first run of P zeros is bigger than n。

So a number of bits strings of length in， no run divided by to then。

 the sub probability that the first end bits have no runs of p0s。

 and that's the same as the probability that the position of the end of the first run of P0s is bigger than n。

But that's exactly the average position at the end of the first run of p zeros so that's the average wait time so this argument just gives us these two theorems so first one is the probability that an end bit random bit string has no run of p zeros is the coefficient Z to then in SP evaluated z over 2 that's the second line here。

And so。Going from the solution on the previous slide。

 it's going to be our dominant route divided by2 to the end。

 and then the other thing is the expected wait time is just our generating function evaluated at one half。

If you evaluate that generating function at1 half， you'll see that all that's left。

 the 1 minus2z cancels out， so it's 1/ half to the p plus1 in the denominator。

 so it becomes2 to the p plus1 minus2。So that's using the symbolic method。

 get information explicit version of the generating function。

 and then evaluating that generating function to get the analysis of the properties of the consecutive zeros in a random bit string。

So just to summarize for small values of p which are usually what's of interest。

 so that's our generating function when p equals 1 is 1 minus e over 1 minus20 z squared。

 so the probability of approximate probability of no0 in Rnda bitstr string ofs n is 12 to the n。

 and then 10 that's 0。0010 and 100 it's 10 to the minus 30th and the average weight time is two for30s。

 then we can do the explicit。Those are the values of the roots and it turns out that probability of no run of two zeros in 10 bits is about 0。

14 in 100 bits it's 10 to the minus 9 and the wait time for the first run of two zeros is about six。

For three zeros now。Probably of no run of three zeros becoming more and more likely。

 so for 10 bits it's about even chance that there's no run of  three zeros for 100 bits still fairly unlikely。

Four zeros now 10 bits， three quarters of the time you're not going to have four zeros in a row。

 you have to wait 30 bits to get your first run of four zeros on average。

 but for 100 bits it's still pretty unlikely that you won't have four zeros in a row。

And then for five zeros now it's almost 90% chance that you're not going to have five consecutive zeros and 10 random bits。

 20% chance， you're not going to have five consecutive zeros in 100 random bits and the wait time is 62 and then for six zeros。

 it's almost certain and there's even chances in a string a random string of 100 bits that you won't have six consecutive zeros in your wait time is over 100。

 126。So those are packs that we can derive from this analysis and actually this type of statistic is one way to test whether a set of strings is random。

In fact， it's always worthwhile to validate these types of mathematical results and in situation like this。

 when it's so easy to write code to validate these results， we should go ahead and do it。

So this is a Java program that takes as argument a size in and a number of trials and what it's going to do is it's going to this one actually reads the bits from standard in so we separate out what the bits are from analyzing them so this will read W bits at a time from standard in so like in that example W was 75 and there are a bunch of occurrences of 75 bits that we're supposed to be random and then for each P it'll check whether there's zero P consecutive zeros and then it'll just print out the empirical probabilities and then this is just the code to just check for P consecutive zeros so this is a very straightforward program that reads in a bunch of bit strings and then prints out out of all those bit strings what's the empirical probability that。

You find one， two， three， four， five up to P consecutive zeros。

And so for the example that I used on the first slide， this is the data that it gives。

 and so actually those are the first line of 10，000 bits， 10，000 bit strings of size 100。

 and for those bit strings， those are the probabilities that 0，1，2，3，4，5 and 60s occurred or not。

And those compare very favorably with what we just saw was predicted by the theory。

So we can think that those bits are past this test for randomness。

 or we can think of this as validating the theory that we just arrived predicting， for example。

 that you have a 45% chance of finding， say， six consecutive zeros in the random bit strings。Okay。

 so that's a fine generalization of the simple example that we did for how many bit strings don't have two consecutive zeros。

Now， so check。So now the next thing that we want to do is consider other specified patterns。

 so say it's not 000 that we're interested in， but say 001， so now in blue you can hardly see。

 but the wait time for 000 that's the one that I did before is in red and it's an average about 18 for these。

But in blue is the weight times for 001， so in the first line。

 the first occurrence of 001 is starting at the ninth bit and the second it's at the fourth bit and so forth。

And this time the expected wait time for 001 in this set of bit strings is only six， it's much。

 much less and now we're wondering are these bit strings really random what's going on here？Well。

 the fact is that the pattern itself definitely is a factor in what the wait time is。

 and that's what we're going to look at next。So we showed before that the probability that an end bit or bit string doesn't have four zeros in a row is about 0。

96 to the end。So in the expected wait time is 30 and the question is。

 does that same thing hold for 0001 or any other pattern of four bits？And the answer is no。

So in every。One that we did， the 001 occurs much earlier than the 0000。

So there's a little intuition behind that， so let's say consider the first occurrence of three zeros in a row。

Now， the next bit could be either zero or1， so our two patterns are equally likely once we found 000。

But the thing is if we were looking for 000， then that would mean that we're looking for four zeros and we didn't find it。

 it would mean that we have 0001 in our bit string and we're going to have to wait at least four more bits before we could find 000。

But if we were looking for 0001 and we had a mismatch。

 it'd mean that there's four zeros and the next bit could give us a match。

So if we're going from left to right， looking for these two patterns。

 it's not surprising that we're going to find 0001 first。Find zeros in a row。

 we got a good chance of being the next bit， but if we're finding looking for four zeros in a row and we find three zeros then we're going to have to wait a long time for the next bit。

 that's the intuition behind why it occurs much earlier。So， but now we want to answer this question。

 what's the probability that a random Biitz stringing doesn't contain that pattern 0001 It's a little bit counterintuitive that it's not the same for any set of four bits。

 but it's definitely not as we'll see。Or what's the wait time for the first occurrence of 0，0，0，1？

And what about other patterns like 1110 or 1111 and so forth？

So the idea that it's the pattern itself that determines the probability existence in the expected wait time has to do with a phenomenon called autocorrelation。

 that's what we're going to look at next。So what we'll do is use the symbolic method to get explicit equations for the generating function。

 for number of bit strings， not containing a specified pattern。

And it's remarkably easy to develop such an equation with the symbolic method。

So what we'll say is we'll take any pattern P， so that's a pattern of bits。

 and s sub P is the binary strings that do not contain that pattern at all。

And then we'll define T sub B P to be the binary strings that end in P and have no other occurrence of P inside。

So that's two well defined sets of bit strings。And so what we're going to do is have two different constructions that relate these classes of bit strings。

So the first one is based on the following observations。These two sets are disjoint。

 that is the TCP has the pattern in it SP does not have the pattern in it。

 so there's no string that's in both of them。Empty string doesn't contain the pattern， so it's in SP。

And the other thing is if we have a string in SP。And we add one bit to it。

Either we're going to get a string that's in S sub P or that bitll complete the pattern and we'll get a string that's in T sub P。

 the only occurrence of the pattern。So based on those observations。

 we have this symbolic equation or construction that relates these classes of strings S subP plus T subP is either empty or it' S subP with a bit added。

So that's the first equation。Here's a second construction that relates these two combinatorial classes。

 it's based on the idea of what's called an autocorrelation polynomial that is a property of a pattern。

And the idea is we take the pattern in black and then slide the pattern to the left over itself。

And so well at the beginning， the pattern matches itself in the number of trailing bits we use as an exponent。

 so we start out with the Z to the zero on the polynomial。And then we slide over one， two，3，4。

 five positions when we slide over five positions then the trailing bits match the leading bits of the pattern well the 1010 at the beginning match the trailing four bits and we slid five positions so we put Z to the fifth and then two more positions。

 the two trailing bits match the two leading bits as z to the7 so in all the possible slides the only match of the trailing bits with the leading bits is at positions zero。

5 and seven。That defines the autocorlation polynomial of the pattern for this one。

 its correlation polynomial is1 plus z to the fifth plus z to the7。

And that's going to play a role in the development of another relationship between the two combinatorial classes we just defined。

 this is the second construction。So remember， SCP doesn't contain the pattern。

And TCP ends in the pattern， but has no other occurrence of the pattern。

And so the idea is if you take any string in T sub P。

And then you add a tail corresponding to the tail that you'd get to complete the pattern in the autocorlation。

 so the first one's null and the second one， if you add the five bits that you shift it off at the end of the pattern you get an occurrence of the pattern and again if you add the seven bits you get an occurrence of the pattern。

 so those three cases null one corresponding to each bit in the autocorrelation polynomial you'll get a string that if you have a string in SP that does not contain the pattern。

 if you add the I'm sorry if you have a string in T subP and you add these tails then you'll get a string in SP from knocking off the pattern so every time the result is a string in SP followed by the pattern。

So SP times the pattern is T subB times the one place for each bit in the correlation polynomial。

So that's going to give us the combinatorial construction， so we have those two constructions。

 one if you add a bit to a string in S you get either string in S& P and the other one is if you take a string in T and you got a chance for every bit in the autocorrelation polynomial to make a string in S followed by the pattern。

Those are the two construction and these use these two constructions are set up for the symbolic method。

 they just use the basic operations， so they immediately correspond to generating function equations。



![](img/d1fa843de4aabd2db8f3ace7707ae7e3_2.png)

First one， z0 plus z1 is 2 z， and otherwise it just directly corresponds to the adding the generating functions。

In the second one， the pattern has OGfZ to the P， so sp times z to the p equals TP and then what's left over here is the correlation polynomial itself。

So now we have two equations in S& P that we can solve and the correlation of polynomial of the pattern is part of the answer。

So that's the solution of those two simultaneous equations。

This is the OGF for the class of binary strings that contain no occurrence of a specified pattern。

Now for any particular pattern， we can plug in the correlation polynomial。

 and again we have a ratio of two polynomials， we find the dominant root of the one in the denominator and our count is asymptotic to that root to the nth power multiplied by a constant that we can compute explicitly。

So this is a methodology that's going to work for any pattern at all。

So here's the end result for four bit patterns， so of all possible four bit patterns。

 actually there's only four different possibilities for the autocorlation。It turns out。

That classifies the four bit patterns。With those autocors。

 they all start with the one and well those are the autocors that can come up and so those lead to these different OGS and so they all have different dominant roots and I didn't compute the constants here they're all pretty close to one and then you can see that this one with 100 it's a slightly smaller number when we raise that number to the tenth0th power we're going to get a smaller number and for 00th power it's going to be much much smaller。

It's interesting and maybe counterintuitive， but these are the results。

 you're going to wait about twice as long for4 zeros or41s as you are for any one of those six patterns。

Or another way to look at it is that 000040s is100 times more likely to be absent in 100 bit string than all of these other patterns。

0010110111 so studying this table maybe is a good way to win some bar bets perhaps。

It's kind of surprising that we can so completely characterize this problem with analytic combinatorics。

That's the study of Bistrs with restrictions and these studies extend in various ways。



![](img/d1fa843de4aabd2db8f3ace7707ae7e3_4.png)

![](img/d1fa843de4aabd2db8f3ace7707ae7e3_5.png)