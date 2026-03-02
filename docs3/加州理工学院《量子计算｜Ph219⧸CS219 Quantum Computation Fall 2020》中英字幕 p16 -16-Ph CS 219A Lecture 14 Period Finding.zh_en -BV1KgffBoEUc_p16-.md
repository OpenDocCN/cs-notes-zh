# 加州理工学院《量子计算｜Ph219⧸CS219 Quantum Computation Fall 2020》中英字幕 p16 -16-Ph CS 219A Lecture 14 Period Finding.zh_en -BV1KgffBoEUc_p16-

Hey， quantum friends， welcome back for more Quantum fun and physicsic， Comp Science 219 a。

Good to see you again。 I appreciate your loyalty。Now we're going to continue building on our discussion from last time on query complexity and separations between query complexity in the quantum and classical settings。

So， here we go。

![](img/3c0d6a32489f5780f2c0b2baaf64f29c_1.png)

So last time， remember， we talked about。In the case of the black box model。

 the difference between classical and quantum queries。

We have a box which in principle can handle coherent superpositions as queries。

And to get a grasp of the power of quantum computing。

 we're going to want to compare the case in which the queries are limited to classical ones that is computational basis states。

 in other words， bit strings。As opposed to coherent superpositions of those bit strings。

 which we'll see in some cases， can provide much additional power for solving certain problems。

An example of that， which we discussed and analyzed last time， was Simon's problem。

Where we have a function from n bits to n bits， it satisfies a certain promise。

And we saw that we can solve the problem of characterizing that function。

With a number of queries which is linear in the size of the input to the function。

 the number of input bits。That we query it with。嗯。Whereas in the classical case。

 in order to solve the same problem， even with randomized queries。

The number of queries needed would be exponential in N。

So this is an example of an oracle relative to which we can separate classical and quantum computing。

 we can say relative to that oracle that BPP is not the same as BQP。Now。

 Simon's problem is not known to have practical applications。

Today I want to talk about a related problem which does have some practical implications。

 so this will be the problem of finding the period of a function we have a black box。

Which can evaluate the function。 We are promised that it's periodic。 We're not told it's period。

 we need to determine the period。 And here， too， we're going to see that there is an exponential separation in query complexity。

Between the quantum and classical settings。And the nice thing about this example。

Is that all the processing that we need to， well this is true of Simon as well。

 the processing that we need to do aside from the queries is all is efficient to solve the problem。

 but to make it practical， we'd like to have a way of instantiating the black box。

In a situation where even if we know the structure of the function and how it's computed by the box。

 even so we can solve a hard problem。If we can compute the function efficiently。

 then we don't need the box。 We can simulate the box by efficiently computing the function。

 And so what this example will be telling us is that for any efficiently computable function。

 efficiently computable classically we can use a quantum computer to find the period of the function if it's a periodic function。

 and that actually is a powerful result and we'll discuss next time how it is the。

Crooks of Shore's famous algorithm。For finding the prime factors of large composite integers。

So I remind you about Simon's problem。Here's one way of formulating it。

 we're promised that a function f is a two to one function。

With the property that two different inputs are pre images of the same output。

 if and only if the bit wise x or of the two inputs， x and y is the nbit string A。

 and the problem is to find a。And of course， the number of possibilities for a is exponential in N。

 so that's not a problem that we can find easily the solution by randomly querying the oracle with just classical queries。

But quantumly， we were able to do it。We。Quered the box that evaluated the function with a superposition of input values。

 and then we measured the input register。In the complementary basis。

 we did a bitwise had em wirered on the n bits and then we measured in the computational basis。

 and it turned out that by doing so we were sampling from strings which are orthogonal to the string A in the bitwise inner product and if we repeat that enough times we can find n minus one。

Binary vectors of length n， which are orthogonal to a， and that's enough to determine A。

 and it's an easy computation at that point classically to find a okay。

The problem that we're going to discuss today has a somewhat similar structure。

Now we're considering a function which takes integers to bit strings， let's say to M bit strings。

And now we're promised。That the function maps two inputs to the same output。

F of x is equal to F of y， if and only if the difference of x and y is some period of the function times an inature。

And we're also promised that there's some upper bound on what that period is。Let's call it capital M。

So another way of saying what the promise is is that the function is periodic。

Its period is less than or equal to m and on its period it is one to one so if I keep incrementing the value of the argument。

 if I think of the the input as an integer。I keep adding one to the input value and I get a different output。

 different output， different output until I finally added R。

To the input and then the the cycle repeats we know that's the structure of the function what we don't know is what is this period we all we have is an upper bound on it so the size of the input to the problem。

We can take the number of to be the number of bits that we need to specify that upper bound。

 so it's the log to the base two of that upper bound on the period and so we're imagining that M itself is an exponentially large number。

 it might be thousands of bits long， there are vast number of possibilities for what the period could be and if we just tried random guessing we'd have wed need a huge number and exponential number of queries to find the period。

We can also formulate this as a decision problem if we want to。Just as we can with Simon's problem。

 for example， it might be that there are two possibilities that there is such a period which is less than or equal to M or there is no such period in the latter case the function really is one to one on values of x ranging from zero to M and we want to answer the question which is it is it periodic with some non-trivial period。

Or not。So save it as a decision problem， we can say the problem is an NP relative to the oracle。

I just have to give you as a witness the period itself。

 and you can evaluate the function by querying the box twice。With inputs X and y。

 whose differences are， and if you get the same output then you'll know indeed there is a period which is less than or equal to m and that will answer the question in the case where it is periodic。

The problem is not in BPP relative to the oracle for the same reason that Simon's problem is not。

 if we're limited to classical queries， the only way we're going to get information about the period is if we get lucky if we happen to query the box with a pair of numbers which is a multiple of the period then we would learn something about it。

 but the period is so huge that that's extremely unlikely。

So we're thinking of that period as an exponentially large number。

 the input to the problem has a size which goes like the log of that。So， for example。

 it's the same argument as with Simon's algorithm。 suppose we make R to the one quarter queries each time we。

Make a pair of classical queries。The chance that they got mapped to the same output。

 the probability is just one over r minus1。Because once you've done one of the queries。Then。You know。

Here。Of all the other possible queries， just that fraction of them will get mapped to the same output。

We can bound the success probability if we have altogether say R to the one quarter queries by saying how many pairs of input values do we have well that's just the number of queries choose two and each time we have a probability one over our minus one of hitting pay dirt so the probability of success is still exponentially small it scales like R to the minus one half so even with an exponentially large number of queries we have an exponentially small probability of successfully learning about the period if we're limited to classical queries so the point of today's story is the situation will be much better if we can make quantum queries if we can query in superposition。

In fact。The quantum query complexity， as we'll see， is actually a constant。If you want to have some。

哦。High probability of success。 It's enough to query just a constant number of times to solve the period finding problem。

 That's even better than Simon's problem where we needed a number of queries。

 which was a linear in the input size。 Here， it's actually a constant。And as a matter of fact。

 as was the case with Simon's problem。The quantum post processing needed to identify the period aside from the queries themselves is something we can do efficiently so as I've already said。

For any function that we can compute efficiently。So we can turn the black box into a white box。

 we can really evaluate ourselves。The solution to the period finding problem gives us a method for determining the period of that efficiently computable function in polynomial time。

So the idea of the algorithm is quite similar to Simon's algorithm。

 which is why I told you about Simon's algorithm first。嗯。

Except that you're member in Simon's algorithm。Before measuring in the computational basis。

 we applied a headamard to all the bits。Here we're going to do something a little different because。

The problem is framed differently and we're considering a function on the integers and want to find a period。

 which is an additive integer we're going to use the Fourier transform well that's what people use in signal processing and physics。

To learn about periodic structure， they foray transform and they measure。

 and that's what we're going to do。The quantum Fourier transform is a unitary transformation well i'll explain later in the lecture why it is that we can do it efficiently。

 but for the purpose of discussing。Query complexity， that's not even the point。

 is just enough to know that it's some unitary transformation that we can do ourselves。

And here's what it does， it does what you think it does。 It takes a computational basis state x。

To a superposition of computational basis states with phases which have the form e to the2 pi I Y x over n。

 So n capital n is here the base of the Fourier transform for our purposes。

 we can usually think of it as being2 to the little n。

If we're considering performing the Fourier transform on Nqubits。

 but for much of the discussion that's not going to be so important。

 so I'm just going to call it capital M。Cital n is the dimension of a space to which we're applying this unitary transformation and as I guess you know it's。

It has a simple inverse。The inverse of this unitary transformation has essentially the same structure。

 except with a minus sign and the exponential instead of a plus sign。嗯。Okay。

 I guess I said that already。So how's it going to work， so just like in Simon's algorithm。

We're going to query and superposition， we're going to prepare a uniform。

A superuperposition of all the input values。And I guess I kind of used a mixed notation here。

 but that's okay sometimes I said capital N and sometimes I said two to the N if we're really talking aboutqubit on how to make that uniform superposition。

 we already did it in talking about Simon's problem， you just apply a hadamard to everyqubit。

 if you start in the all zero state and that gives you that uniform superposition。

Another way of doing it would be to use the the Fourier transform if you apply the Fourier transform to the all zero state you get a uniform superposition so if you have a way of efficiently doing that that's another way to prepare the。

Uiform superposition， but remember in the context of query complexity。

 we don't care about how hard it is， it's just some unitary transformation so of course we can do it。

In principle。Remember to determine complexity， we only count queries in this setting we're considering now。

 but anyway。We prepare this uniform superposition。And then we query。

 And so we're going to make this massively entangled state。

A lot like what happened in Simon's algorithm， we're going to sum over all values of x in the input register that will be correlated with the corresponding value of F of x。

And then we can imagine that we measure the output。Register just like with Simon's problem。

 whether we really measure it or not doesn't matter because we're not going to use the any information that we gain when we do the measurement。

 so we might as well do the measurement and throw the answer away。

 but that's really just the same thing as tracing out。The answer register。

 and then we get a mix date in the input register。Whether we measure or not。

 but for the purpose of describing how it works。It's convenient to imagine that we actually do measure。

And so。I guess I didn't say it， but let's suppose that the result of performing that measurement is that we get the outcome f of x0 or x0 is some particular input value。

And then what we prepare in the input register is a uniform superposition of all of the pre images of that output value。

 and because of our assumption about periodicity， those are equally spaced。嗯。

Separated by R the period okay so what we've just managed to do is to prepare this uniform superposition of all the inputs that get mapped to the same value。

 so I can imagine this x0 is something less than R and then all the additional values are obtained by adding multiples of R and Im although I'm imagining that my function can be defined on any integer。

 I'm not going to be so bold as as to attempt to apply it to a uniform superposition of all integers。

 I'm only going to consider a summing x from values0 to n minus1 where n is some very large integer So the number of terms in the superposition is whatever the least integer is that is greater than or equal to n over R that will be the number of values which are less than n which。

Get mapped to a particular output。Okay， so so what we're going to do just like Simon's problem。

 except with the Fourier transform now instead of the bitwise hadtiar。

Is we're going to take that input register， we're going to apply the quantum Fourier transform to it。

And then we're going to measure in the computational basis。Okay。

 so this is how the quantum Fourier transform is defined。A unitary transformation。

 I want to apply it to this uniform superposition。 So I'm going to be summing over all the values of J。

 And for each one of the values of J， I'm going to have a sum over。

All values of y as in the definition of the quantum Fourier transform over here。

And then a computational basis state y and the phase that appears will be e to the2 pi I y over n times that input value x0 plus JR。

 So I factored that into a piece that depends on J in a piece that doesn't depend on J。

The piece that doesn't depend on J is just the x0 part that gives me e to the 2 pi I x0 y over n。

And the piece that does depend on J has the J R part， multiplying2 pi I y over n。Okay。

 that is when I perform the sum over J that gives me the coefficient。The amplitude for computational。

Basis state y in this。In this state of the register。

Assuming that we you know got this particular output when we measured and now when we measure why I want to know what the probability distribution is for the measurement outcome。

 so I just take for each y the amplitude squared。And。

ForOnce I fix Y this phase that depends on x0 is just an overall phase。

 so that's not going to affect the probability of getting outcome y when I take the absolute value squared to the amplitude。

 so the probability distribution isn't going to care about x0 at all。

 that's why it wasn't really necessary for me to do the measurement I don't need to know what x0 is。

Or what F of x0 is。And so then。嗯。Let's see what we've got， I guess I for。Reasons which。

Maybe we'll become clear I wrote one over NA， which is the square of this coefficient。

As a over n times 1 over a squared， so I put an A over N in front。And then inside the sum。

 which gets squared， I put a one over a and I did that because this is a sum of。嗯。A term。

 so that's the natural way to normalize that sum。Now。

 what we're going to see is that this probability distribution for the outcome of the measurement after we do the Fourier transform and after the query。

Is about very strongly peak distribution for most values of Y it's very close to zero。

And for some special values of Y。There's an appreciable probability。

 that's what I mean by sharply peaked。And from the value of Y。

 we're going to learn something about the period because where those peaks are has to do with what the value of r is。

So we'd like to understand that work how that works and to keep things simple at first。

 let's suppose that n is a multiple of R so the period actually happens to divide n the。

Dimenssion of the Hilbert space that we chose， the base of our Fourier transform， of course。

 in practice， that's not very likely。N was just Rs to choose， R is something we don't know。

 and they're both exponentially large， but let's suppose it anyway because things are very simple in that case。

Okay， so this is the sum that we have。And now I want to suppose that n over R is an integer。

 n is a multiple of R， and that will actually be a in this case。

 the number of terms in the sum will be precisely that integer。And over R。

And now in the case where y is equal to a that is n over r times an integer。

 the phase appearing here is exactly equal to one。And。That means。That。

We get a terms and we have the coefficient one over a， so the sum is going to be equal to1。

And so the probability in that case。下。碌晒界。For some reason left out the square here。

 but sorry about that。 anyway， the probability in that case is just going to be this pre factor a over n。

 which is it actually is equal to1 over R。 So in the case where y is equal to a that is n over R times an integer we're going to get the probability for that particular outcome to be1 over R。

Now， in fact， there are such values。Okay， so the probabilities all sum up to one and that's already enough to see without doing any further calculation。

That for all the other values of y， the probability is0。

For all the cases in which y is a multiple of n over R， we get probability one over R。

 and there are such cases， and for all other values of y we get zero。So in other words。

 when we query the box， evaluate the function with a coherent superposition of all possible input values。

And then we Fourier transform the input register。And then we measure that input register。

 we are sampling uniformly from all the values of， let's say， y over n。嗯。

Which are equal to an integer K over R， where K is an integer。Okay， well there's a maximum value。

 I mean， it's not really all integers。Because there's maximum value y。

But for all the integer values of k， such that。Such that y is less than or equal to n。

 they all occur with equal probability。So just like in Simons。

 algorithm than we were sampling uniformly from something interesting。

 namely the values of the input that were orthogonal to the period we were trying to find for that bitwise function for the bit string A。

 here we're sampling uniformly from the values of Y。Which are of the form。

Integer over R and R is that。That period we're looking for。Okay。

 but remember so far we've made that assumption that。Unlikelikely assumption。

That N overRxC is an Ninger。So we want to see what happens when that's not the case。

 the more realistic case， well， things aren't that much different。嗯。If N is not a multiple of ours。

 as I'm about to show you， will still be sampling。From values of。

Of y that are very such that y over N is close to K over R with an order one success probability and almost uniformly。

So in other words。There are。Our values are that period， our values of why。

Such that the difference between y over n and some integer over R。Is no larger than one over2n。

Okay so the idea here is if you look at the values of y over n， they're equally spaced。

Rational numbers between zero and one。The distance between successive numbers is one over n。

And so if I consider any value of k over R， where k is an integer， which is less than or equal to R。

Then one of the values of y over n is going to be at least as close as half the distance between those neighboring points。

And。They're separated by one over and so half the distance is one over 2 n。ok。

Take any value you want in the unit interval and there will be some y over n， which is at least。

Within distance 1 over 2 n of that number。Okay。So let's write y over n as k over R plus delta。

 where delta is some small deviation。Of y over n from an inteature over R。

 and small means it's not going to be larger than one over 2 n。And then when we take the phase。

 the exponential of2 pi I， a y over n。RJ like we have here。That's going to be。All this。

 it's going to be the exponential of two pi I K over R。 That's what we had in the case where a was。

Equal exactly then over R an integer was that was when delta is equal to 0 now delta is small。

 so I have to keep that delta in there it's not equal to0 K over R plus delta times Rj。

 but just as here the K over R part just gives me a trivial phase。

 the argument of the exponential is2 pi I times an integer。The only thing that matters is the deelta。

So the phase is actually going to be e to the2 pi I Dlta Rj。Okay。And now。

RJ is not going to be larger than N。Right。And。Delta isn't going to be larger than one over 2 in。

So the argument of the exponential here is actually a2 pi i times a number which in absolute value is less than one half。

So that means the phase can range from。E to the minus i pi over 2 to e to the i pi over  two。下。

I guess that's right。And that means all of the points are going to be on the same side of the unit circle。

 all on the right hand side。And。That means we're going to get constructive interference when we add up all these terms。

Okay。They can they might， they're going to be distributed in some way。Around the unit circle。

 they won't all be sitting right at one， but they're all going to be on the right hand side。

 and so when we add up all the faces， we're going to get a big number and so we'll be able to get an order one probability。

Of obtaining one of these values of y such that y over n plus k over R y over n is minus k over R is less than1 over 2 n。

 we're going to get a value like that with a total success probability。

 which is order one okay that's what's going to happen in general。

 so what's going on is we're using constructive interference to our advantage。

There are certain values of y which are going to be useful to us。

 Those are the ones such that y over n is close to an integer over R。And indeed。

 when y over n has that value， constructive interference makes that probability occur with some appreciable value。

 but all the phases destructively interfere when y doesn't satisfy that condition or when it's far from satisfying that condition。

 and so those values apply are going to occur only with a relatively small probability。Okay。

 so well let's be a little more quantitative about that and just kind of have the picture now。嗯。

Some that we have to do is just a geometric series， a finite geometric series。

 so that's an easy sum to do。I decided to write it in terms of the primitive enroroid of unity。

 which I call omega here。So the sum is。E to the what we're summing over J is e to the2 pi I。

 J R Y over n。That's what occurs in the expression for the probability of y。

 and then we have to normalize that and take its absolute value squared。So in terms of omega。

 we have omega to the RY。Race of the power J and we're summing J over these a values。

 and this is what the sum of the geometric series will be。

It's going to be this factor omega to the RY raised to the power a minus1 in the numerator divided by omega to the RY minus1 in the denominator。

 omega equals e to the 2 pi I over n。Okay， so coming back to our expression for the probability of getting outcome Y。

This is what I had written down before here now I've done the sum substituted in this。

 and so that's the thing whose absolute value squared we have to take。Of course。

 I can factor out a phase from the numerator denominator in the numerator， for example， once I do so。

 this is going to be e to the I pi AY over n minus e to the minus I pi AY over n。

 so in other words it's just up to a factor of2i。The s of an angle we're going to take the square of that and the two is going to divide out between numerator and denominator so what I get in the numerator is the s squared of pi A R y over n in the denominator there's no a so it's just the sine squared of pi R y over n and。

Well， again， there really was a one over NA， which I had written as taking an A out in front and putting a one over a squared。

 but anyway， here's that one over NA multiplying the expression I just described。Okay。Now。

 for the values of y that I was just talking about。

 the values of y that I claim are going to occur when we make the measurement with appreciable probability。

Delta is a pretty small number， it's less than or equal to one over 2 n。And remember。

 AR is also less than or equal to n。Because a is the number of multiples of R that will fit in between0 and n。

And while this is just a fact about the sine function。

 if the argument of the sine function is less than or equal to pi over two。

 if I take the s of the argument divided by the argument，In absolute value。

 that's going to be at least two over pi， you know when the argument is close to zero that's close to one and the smallest it can be is when the argument gets to be pi over two when the sign is one and the argument is pi over two so in other words two over pi is a lower bound。

On。Well would I chose to write sine cx over Cx as long as cx in absolute value is less than or equal to pi over  two？

So what we have here。Is s cx over x the Cs divide out and I'm saying that's greater than or equal to2 over pi c and the reason I care about that is that's the kind of expression I have here except that I squared it。

So the one over NA still in front， we have this ratio of sine squared pi R delta。

Divided by sine squared pi R delta， and according to the bound that I just stated。

We can say that that will be greater than or equal to1 over N times the quantity 2a over pi。

 which gets squared because it's a sine squared divided by a sine squared。

So now I've got an a squared in the denominator， sorry。

 an a squared in the numerator name the denominator and a over N overall。And。

Two over pi quantity squared。In front for our lower bound on the probability。

And that's true for each one of the values of y， which are have the property that y over n is delta close。

To integer over R。 But remember there altogether are such values。

 So the total probability of getting one of those values is going to be R times this。

R is equal to n over a。So the total probability of obtaining a value of y that satisfies this property such that y over n is close to in inger over R。

Is going to be at least four over pi squared， which a little better than 40%。

Now the probability distribution isn't precisely uniform in K。Because the delta can。Pa。What I guess。

Yeah， I guess that's right because for different values okay， the delta might have different values。

But it's not very highly biased， all the values of k occur with you know appreciable probability。

 so I'm getting a pretty fair sample of the possible values of k。Now remember。

We have a promise in the formulation of the period finding problem we know that R can't be larger than M。

 So now what we want to do is choose n large enough。

So that we'll be able to infer a unique value of k over R。

 which we don't a priority know from what we do know。

 which is n and y the outcome of our measurement。And I claim that choosing n to be at least as large as m squared will be good enough to do the job if we choose n at large。

 then whenever。We obtain an outcome such that a y over n is within distance 1 over2 n of some integer over R willll be able to find that rational number k over R。

Precisely from the known value of y and N。So why do I say that？Well， it's pretty simple。

Suppose there are two rational numbers。Here they are， A over S and B over t。

 I suppose they're not equal to one another， so their difference is not zero。

What is their difference？Well， I can write it as a numerator， 1 A minus B。Divided by S T。Okay。

 and if both denominators are no larger than M。Remember。

 we're considering the case in which r is in the denominator and we know that R can't be larger than M。

Then this difference of rationalal numbers has to be at least as large as one over m square。ok。

And so what we're going to want to do is to choose our N to be at least as large as one over m squared。

And then we know Y over N。And we want to， but now n might be much larger than the period n could be you know much larger than M。

 however， there will be a unique rational number。Which was。Within distance a1 over 2N。Of。

Which has a denominator。Which is less than m。See， I chose En large enough， so we get a fine enough。

Sampling。Of the value of y over N， that there will be a unique rational number。

 We don't know what R is， but we know it can't be larger than M。

 We'll be able to find a unique rational number with the denominator， which is no larger than M。

When we get those outcomes that occur with reasonable probability with 40% probability， okay？

So every time we run our procedure， I'll remind you once more what it is。

We create a uniform superposition。We query the function。

 the periodic function with that uniform superposition， we throw away the answer register。

 we apply the quantum Fourier transform to the input register， and then we measure。

 we get some value of y we know the value of y over n。

We chose n to be at least m squared and now we'll be able to find the rational number， which。

Will be unique with the denominator R， which is no larger than M。

 which is within distance 1 over 2 n。Of y over N， Okay。

 so that is going to tell us something about the period。We will。

 at least with some reasonable success probability with this  40。5% success probability。

Learn a rational number， which has the form integer over R， where R is the。

Period that we're trying to find。So it might be that K and R K is pretty much， randomly sampled。

From values which can range from。No from zero to R。

And it might be that there's no common factor of KNR。And then we take that rational number。

That we've determined， which has a denominator no larger than M。 We reduce it to its lowest terms。

 making sure there are no common factors between numerator and denominator。And the denominator is R。

 we found our Hooray。And once we found our， it's easy to check that it's right。

We can query the function twice with。X and x plus r and see that we get the same output。嗯。

It might be though。That our randomly sampled value of k。Shahares a common factor with R。

And then the rational number that we learn is some K1 over r1， say。

Where we divided out that common factor。And then the denominator is not R。

 but it is a factor of R okay because we divided out something from numinator and denominator to get K1 over r1 so that r1 is going to be a factor of R it's something that divides R so we've definitely gained some useful information。

 we've learned something about R。But now we just keep going。Okay。

 it turns out that R1 isn't the period， how do I know well I tried it now I queried with F of x and F of x plus r1。

 I didn't get the same answer。So I know the actual period is some multiple of our one。

 not our one itself， So what do I do？I do the whole thing again。And with that 40。

5% success probability， I'll get another value of y over n。

Which is very close to some integer over R， very close， meaning at least as close as one over 2n。And。

So good so I get another chance and maybe this second time I get K2 over r2。

 maybe the numerator and denominator had you know no common factor and I've learned R this time。

 but even if not I still have a chance because。It may be that the。Well， I guess I'm kind of。

Changing my story a little bit。嗯。Oh， it's okay。The values of K that I get。

I didn't think I wrote the right thing here。嗯。Well， the idea is。That。If。The K I get the first time。

And the Cape prime， I get the second time。Don't have a common factor。With one another。

But they do both have a common factor with our。Then I've learned。Something about R in both cases。Now。

 if。The K and the K prime。Have no common factor。Then I've divided out different numbers from the denominator in the ratio k over R and the ratio K prime over R。

 and that means that R will be the least common multiple of the two denominators that I found R1 and R2。

Okay。Well， maybe it didn't work again， or maybe there was a common factor of the two values of k。

But that's okay， I do it again。And if。After multiple trials。The values of k that I sample。Our。

Don't have any common factor， then it will be the case that the least common multiple of all of the denominators is equal to R。

And I won't explain this in detail， there's a little bit about it in the notes， but in fact。

 if we sample random integers less than some really big value。Mip times。

 then with high probability after a few trials， there will be no common factor of all the integers。

It's just because the prime number is thin out fast enough。

So that there's not likely to be a prime number that divides all of them。

And so that's good because after I've done it a few times。

 the values of k that I sample now have no common factor。

 so I take the denominators of the rational number that I found in each case。

 take their least common multiple and that's going to be R and so after a constant number of trials with high probability。

 we will succeed in finding R。There are two things I have to worry about， first of all。

 there's an almost 60% probability that when I sample， I don't get a value of Y overrun。Which is。

Delta equals 1 over 2 n close to some k over R。But you know， after a few trials， I'll have。You know。

 several instances in which it is true that y over n minus k over R is less than1 over2 n。

And then I have to worry about the fact that the values of k that appeared randomly had common factories with R。

 but after I've done it a few more times， I'm not going to be encountering the same common factor。

UMore than once and so when I take the least common multiple。

Things are good and I found our and that's how it works。

 that's how we can solve period finding with a constant。嗯。Number of queries。Pretty great。All right。

 well， next time I'm going to talk about an application of that。But first， to conclude this lecture。

 I'd like to say something about。The quantum Fourier transform for the query complexity argument。

 it wasn't important that I could do it efficiently。

 but for real applications it's going to be very important。And I want to show you that I can。

So again， the quantum Fourier transform is this unitary transformation， we want to find a circuit。

That does that and。For convenience， I'd like to consider now capital N to be2 to the little n。And。

Affic circuit will be one which has a size which is polynomial and little N or polynomial in the log of capital N。

ok。So in the context of what I just said。Remember， I wanted to choose n。To be larger than m squared。

Where M is the upper bound that we're given on the。The period of the function。

And so what I'm going to do to use the Fourier transform in this form when the base n capital n is two to the little n is I'll choose n to be。

The smallest power of two that's larger than m squared。ok。So to see how it works。

 it'll be nice to use the binary notation。Of an integer。Which we're implicitly using anyway。

Referring to bit strings as integers and what I mean by that is I'm thinking of the bit string as representing。

A binary expansion of the integer to be more explicit。So x is an integer。Written in binary notation。

 it would be xn minus1， xn minus2， xn minus3， blah， blah， blah， x1， x0。

All together and bit string and just to remind you what that means。

Each one of the x of Js is a binary digit， it's either zero or1。

 and so the integer is xn minus1 times 2 to the n minus1 that's its most significant pit。

Plus x of n minus-2，2 to the n minus-2， the next two most significant bit。Blah， blah。

 blah down to x1 times 2 plus x0 and the least significant bits。And same thing for why。

 Y has a similar expansion。Hm。Y n-1，2 to the n-1 plus y n-22 to n -2 plus and so on。

Now what appears in the exponential？In the quantum Fourier transform。The amplitude。

 when I consider the result of applying the quantum Fourier transformed to computational basis state x of the computational basis state y is this phase。

Now any piece of x y over n， which is an integer we're not going to care about because that's not going to contribute to the phase。

 we only care about the non integer part， in other words， we subtract away the largest integer。

Less the X y over on。And。And then what we're left with is all the matters in determining the phase。

Now， in our case， remember capital n is equal to2 to the n， so I'm interested in x y over 2 to the n。

 and I want to throw away any integer part。So let's consider。

The terms in the expansion of xy over 2 to the n that depend on y sub n minus1。Well。

The only thing that's going to matter is the product of y sub n minus1 and x0 because y sub n minus1 times x1。

Is going to be multiplying2 to the n。 So when I divide by 2 to the N and I just get one。

 that's an integer。 it doesn't matter。So the only thing I'm going to care about is2 to the n minus1 times。

Y sub n minus1 times x0 divided by2 to the n。 So that means one half of the product。

Of x0 and y n minus1， that's the only part that's going to depend on yn minus1。

And it's convenient here to use the binary decimal notation。

 that's kind of a oxymoron to say it that way， but I'm writing fractions in terms of you know a quote unquote decimal point or binary point。

 if you like。So when I write point x0， what I mean is x0 over  two， if I write， say point x2， x1 x0。

I mean， x2 over2 plus x1 over4 plus x0 over eight， okay， and so on， if there are more。

Bits going further to the right of the decimal point。So I'm going to write it this way。

 y and minus1 times 0 x0。That's the only part that depends on y sub n minus1。

 What depends on y sub n minus2。Well， I'm not going to care about y some n minus2 times x2 and x3 and so on。

Because that's going to be multiplying something which is two to the n or a multiple of two to the n so I get an integer when I divide by 2 to the n。

There are only two terms I'm going to care about。Involving y sub n minus2。

 y sub n minus2 times x0 times 2 to the n -2 over 2 to the n。 That's one quarter y。N minus2 times x0。

 so I'm putting that in here as point0 x0 or x0 in the second place to the right of the decimal point that means x0 over four。

And the other term I care about is y n minus 2，2 to the n minus 2 times x1 times 2。

So that gives n minus1 powers of 2， when I divide by 2 to the n。

 I get1 half y sub n minus 2 times x1， and that's the point x1 here and the expression multiply y sub n minus2。

And so you see how it goes， likewise， the terms that involve y and minus2 are going to be1 half time y n minus2 times x2。

Plus one quarter y， I said y n minus2， I guess I wouldn't and y is sub n minus3。

So one quarter y sub n minus3 x1 plus 18， y n minus3 times x0， and that's all。And so on。 And finally。

 when I got down to the terms that involved。Yhy zero？

Now all of the bits in the binary expansion of x are going to matter because when I divide by 2 to the n。

 I get a number which is less than1， namely I get1 half x of n minus1 plus1 quarter， xn minus2。

 and so on all that multiplying y0。So all that dropping the integer part is what I get from Xy over 2 to the n。

Now， in the quantum Fourier transform， this amplitude is the phase either the2 pi I Xy over n。

And as you can see because the exponential is now the exponential little sum。

 I can of course write that as product of exponentials and that's what I've done here so it's the exponential of this term。

E to the2 pi I y sub n minus 1 times 0。0 plus the exponential sorry times the exponential of this term。

E to the 2 pi I y sub n minus 2 dot x1x0 and so on。Product， product product。

 the last factor in the product is either to the two pi I y0 times this point and minus1。At point。

X of n minus1， x of n minus2 dot dot dot。O。So now。Actually。

 what we can see is this quantum foier transform is pretty simple。

It maps a computational basis state to another product state。I claim that this expression。

The what computational basis state x gets mapped to this superposition of。

Basis states y times phases can be written in this way。

There's a one over square root of n associated with each one of the N qubits。

And then I have in the most significant bit in the why register。

Z plus e to the 2 pi I dot x0 times 1 in the next most significant bit。

0 plus e to the 2 pi I dot x1 x01 and so on， and finally for the least significant bit in the y register。

Z plus e to the2 pi I dot x sub n minus1， x sub n minus2 dot dot dot x0。1。

So how do I see that's true well， of course， when you expand this out。

This tensor product that I've written here on the right。It contains all possible bid strings。

Because I can take from each factor， either the0 or the one。

 And each one of those bit strings is accompanied by a phase。

 And it's exactly the same phase as what I've written over here。 Or， in fact， this phase， because。If。

Y sub j is equal to0， then I don't get any phase at all。Right， because。These。

 I get nontrial phases here only associated with the bits of y equal to1。

 not the ones that are equal to zero。So you say you see each time I pick a zero from the most significant next most significant and so on bit of why there's no phase。

 but each time I pick a one there is an associated phase and so here this corresponds to y sub n minus1 equals1 it picks up the phase either the two pi I dot x0 just like I had here。

And here， if I choose a one in the next most significant bit， well。

 that's going to be associated with the phase， which is e to the 2 pi I y sub n minus 2 dot x1x0。

Like I have here and so on all the way down。So the whole thing is a product state。

 but with the phases chosen just right， so as to match the phases in the Fourier transform associated with each one of the computational basis states。

Okay。So now I just have to convince you that preparing that state。嗯。

Or mapping X to that state can be done by a relatively simple quantum circuit。

 which you probably won't be surprised to hear now that we see that it's just mapping it to a product state that shouldn't be so hard。

And here is a circuit that does it。Well， I just sketch it out for the case of。Of three bits。

To make it easy to see how it works and then generalizing that to end bits is。

Easy to understand once we see how it works in a simple special cases。

So here's the circuit the three。Input bits to the Fourier transform or labeled x0 x1x2。

I want my circuit to map that too。嗯。The product of the three states that we just talked about。U。

So it's just the n equals three case of what I wrote down here。

So one of the bits will be 0 plus e to the 2 pi I。X01。

The next one will be 0 plus e to the 2 pi I dot x1 x01， and the next one，0 plus e to the 2 pi I。嗯。

Dot x2， x1， x0， in each case， there's a one over squared root of2 to normalize it。

So I claim this circuit does the job， let's see how that works。

Well we talked before about how you can think about what the Haamard does， you remember the Hatiard。

 the guy that。Maps the basis of。Poly Z eigen states to poly X eigen states。

 so acting on a computational basis state。X sub k oh where x of k is either0 or one。

 it takes it to the linear combination of0 and one。

 which either has a plus sign in the superposition when x sub k is equal to zero and a minus sign when x sub k is。

Is equal to one。And this is just another way of writing that。E to the2 pi i dot xk。

 well that's e to the i pi otherwise known as minus1 when xk is1 and it's one when xk is zero。

 so that's just a way of writing what the head of mark does。Now， in this circuit。

 you see I also have conditional。Rotations， these are rotations about the z axis。

 just to remind you of the notation， what does this mean where I have the dot and the r1 well that means I apply r1 conditioned on the value of x1。

If x1 is equal to1， I apply our1 to this x2 register。And if x1 is equal to zero， I don't do anything。

And same thing here， conditional r2 and when the x0 register reads one， I apply。A two to the。

X2 register， so what are these are1 r2 and so on， they are rotations。

About the Z axis up to an overall phase。 In other words， their diagonal matrices。Acting on qubits。

Are in the computational basis？They change the relative phase of the0 and the1 by this phase factor。

 either the I pi over 2 to the D。D you can think of as standing for distance it's how far apart the two bits are so I have r1 as what is conditionally applied for。

Bits in the string that are distance one apart by distance， I just mean。

You know how they're placed in the binary expansion。And R subP two。

 when the bits are distance two apart and R subP3， when they're three apart and so on。

And each time the distance increases by one。Phase rotation gets smaller by a factor of  two。

 so I have this e to the i pi over 2 to the D。So let's just walk through what this circuit does。

Remember in this incidentally， you'll notice。I've done something kind of funny here。

 I changed the order of the bits。This is the going in， I have the x0。

 x1 and x2 registers and what's coming out is the Y0， y1 and y2 registers in the opposite order。

That's just this convenient way of writing what this circuit does。Um。So in this y zero register。

 what I want is this state。That's what the Fourier transform is supposed to do in that register。

And I claim the circuit does that。 So first of all， the headamard is applied。

And here it's applied to the x2 register， so that's going to give me0 plus e to the I2 pi i do x2。

 so that got the most significant bit right here。But I need the other two bits in this decimal expansion。

 Okay， well， our one is going to help with that。 It's going to apply a phase。

 which is E to the two pi I over 4。X1。嗯。If。If the state in the two register is one。Okay。

 because you see R sub D is。Only going to do anything interesting to the basis state one is just the identity acting on basis state zero。

and saying that it's conditional just means that you take that phase。And you raise it to a power。

 which is the X1 power。Well， that I can just as well write as either of the two pi I dot0 x10。Okay。

 because it's x1 over4 multiplying the2 pi I。So that took care of the next bit。

And then that the conditional R2 takes care at the last bit。Because if register two is a one。

 it's going to apply the additional phase e to the I pi over two squared or e to the two pi I over2 cubed。

 and that's going to give me the e to the two pi I。Dot  zero，0 x0 that I need to complete。

The correct relative phase of these two basis states，011。Okay。

 same thing going on here in the second register first I do the hadamard。

That's going to give me zero plus e to the 2 pi I dot x11， very good。

 but I have to take care of that additional phase。So I get the x0。

 the next most significant bit in the phase， and that's what the conditional R1 is going to do。

Because if x0 is equal to one， then it's going to give me an extra phase E to the two pi I。

Over four or x0 over four。And。That makes this phase， right。And in this case。

 there's really nothing to do except the hadamard。嗯。That's going to take the。Input。Value x0。2。

1 over square root of 20 plus e to the 2 pi I do x01 because that's what the head ofR does。

So we did it at this simple circuit。It's a fourier transform applied to three bits。

 and I think you see how it works if I want to do it for N bits。

I'm going to do the conditional rotations。In the appropriate order。

 so I'll apply conditional here I have the the most significant bit of the input that's going to get mapped to the least significant bit of the output。

I do the hadamard on that most significant bit， the conditional rotations that act on that most significant bit。

 now I'm done with the most significant bit， I've taken care of it。

 the angular rotation falls off with the distance like one over two to the D。

When I'm done with the most significant bit I get to the next one first I do the headam mar。

 then I do the conditional rotations to get the rest of the phase and so on。So in all。

 if we have end bits， they're going to be n head marks。

And therere going to be as many conditional rotations as there are pairs of bits， so n choose to。

 that means I have n headamards and I have n times n minus1 over two of these controlled rotation gates。

 twoqubit gates altogether n times n plus one over two gates， so the circuit has a size。

 a number of gates， which is this quadratic and n pretty simple circuit。Incidentally。

Since we're going to measure。Right after we do the Fourier transform， we can make it even simpler。

We don't even need to do those two Cupid gates。It's enough to measure the qubits in the right order。

And then after measuring， apply rotations to other qubits which have not yet been measured。

Conditioned on the measurement outcomes that we've gotten so far。

And let me explain that a little better。Well， you know this notation I'm using is a little deceptive。

It looks like it treats the control qubit and the target qubit for the rotation in kind of an asymmetric way。

 one is the control and one is the target。But in fact。

 it's completely symmetric between the control and the target。

Another way of saying what it does is that if you then consider the four base states for the two qubits。

 0，0，01， 10 and 11， it doesn't do anything unless the state is 11。

And this nontrial phase gets applied only to the state 11。

So I could just as well write it the other way， I could write the controlled r one with。

The x2 register as the control and the x1 register as the target， and it's exactly the same thing。

Now why is it convenient to look at it that way， I like doing it this way because I thought it made it a little easier to see how the circuit works。

But I'll get exactly the same probability distribution from the measurement outcomes if I foray transform and then measure。

 if I do it a different way。Namely， I start with that most significant bid。And。I呀。Apply the handard。

 and then I measure。Well， it's the most significant bit of the input。

 but it's the least significant bit of the output。When I measure。I then。If I get the value zero。

 I don't do anything more。If I get the value one， then I apply rotations to the other registers。

 so let's stick with the three qubit example。So I measure the Y zero register。

 which is really the same thing as the x2 register。I get the value zero。

 I don't do anything if I get the value one， then I apply the R1 rotation。To the X1 register。

And I apply the R2 rotation to the X register。You see it because。嗯。

Here I applied conditional rotations conditioned on x2 to the x1 and x0 registers。

 but then I measured， so since I'm measuring in the 01 basis。I know whether the。

Control bit is a zero or1。Once I've measured it。And so if it's zero。

 then the controlled unitary wouldn't have done anything if it's a one。

 it would have done the rotation。So if I measure it， I know it's over one。

 it's not too late for me to do that rotation because I haven't measured the target yet。

 and I apply in the case that the measurement gives a 1 r1 to the x1 register and r2 to the x0 register。

Right。And then I can go on like that。For the X1 register， I do the handard first。

Then I measure if I get the result zero， I don't do anything。

 if I get the result one well then this gate， which I can think of as controlled by the x1 register with the x0 at the target。

 now I just apply R1 to the x0 register。If the outcome was one。And then。

There's only one more to measure first I do the headard， then I measure。Now， I'm done。

And I'm going to get exactly the same distribution of outcomes doing it that way。

As if I did the Fourier transform and then measured using the circuit that I wrote down in the first place。

So that's really simple because we never have to do twoqubbit gates。To do the Fourier transform。

 we only have to do heademards and single qubit rotations。By angles， which are。You know， pie over。

2 to the D。And。And then measure， so that's it。Okay。

 so I've explained how to do the quantum Fourier transform。

 not important for the query complexity argument， but very important if we want to use the quantum Fourier transform in real applications because we want to be able to do it efficiently on a quantum computer and we can't and it's actually a very beautiful and remarkable thing that we can。

 Fourier transforms are pretty useful。They're useful for they're often used in engineering and in physics applications for identifying periodic structure for extracting signals from noisy situations and。

The quantum Fourier transform will play that role for us。Inum。Applications of quantum computing。

So the thing that we learned here that was pretty cool is that entanglement and superposition are。

Play个。An essential role in giving us this quantum speed up。For one thing。

 we made this very highly entangled state when we queried。Because we got a complicated correlation。

Between the input and output registers when we did so。But then。

Constructive interference was the key to our story。

That there were special values of y that we hoped to find when we measured and because of phases adding up constructively。

Those special good values of Y occurred when we made the measurement with appreciable probability。

 the bad values of y which wouldn't teach us anything occur only with very low probability。

 so we have a randomized algorithm which is useful and indeed can be used for solving period finding and really can be used to find the periods of functions that we can compute efficiently ourselves。

So I think that will be enough for today and next time I'd like to talk about how we can use the ability to find a period。

Two factor large numbers of Peter Sho's great discovery。All right。See you next time。Be well。

 take care of yourselves。I'll see you soon。

![](img/3c0d6a32489f5780f2c0b2baaf64f29c_3.png)

Bye bye。