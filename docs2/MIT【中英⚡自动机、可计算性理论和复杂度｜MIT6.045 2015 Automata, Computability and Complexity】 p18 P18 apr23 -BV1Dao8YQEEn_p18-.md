# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p18 P18 apr23 -BV1Dao8YQEEn_p18-

Okay， good morning， by the way， if anyone still hasn't picked up their midterms。

 you know I've got them up here， maybe come down the class。😊，All right。

 so the graders I think are mostly done PSet four should be finished any day PSet5 is due you know tomorrow at five and then PSet six。

 which will be the last PS set。Hay will be out， should be out over the weekend and then know you'll have a fault two weeks to do that one。

 you know I would give you more time but I'm not allowed to have PSATs do during the last week of class。

 right？Okay。And then there's just the final and then you know and then we're done so all right。

 so today what we're going to do basically is just finish talking about randomized algorithms。

 probabilistic complexity classes just wrap that up and then we're going to start on cryptography okay which is the second to last unit of the course and should be a really fun one you know and then well that'll be you know three or four lectures and then we'll do a few lectures on quantum computing okay。

😊，So last week we talked about how probabilistic algorithms have this extremely useful property you can amplify them。

 okay， you can always just run the algorithm a whole bunch of times。

 you know with different randomness strings and then take the majority vote among the among the outcomes。

 and if you do this， then the probability of making that your algorithm is going to make an error decreases exponentially quickly with the number of repetitions。

 okay， and that's you a crucial fact for all sorts of reasons。😊。

And you know in the case of randomized algorithms with twosided error。

 you know or in other words BPP algorithms， know it takes a little bit of work to prove that exponential amplification property right you know you have to do like you could say a little bit of statistical analysis or analysis normal random variables to see how how the tails of a bell curve fall off。

 and they do indeed fall off at an exponential rate。

 but we sort of have a quick and dirty version of analysis of normal variables that we use in theoretical computer science。

 which is called the turnoff bound okay so last week we prove the turnoff bound it's application to amplifying BPP and we also talked about one。

Example of a randomized algorithm， in this case， I guess an RP algorithm that no one to this day knows how to derandomize。

 that is no one knows how to get a deterministic algorithm with any similar performance and that algorithm was for what I call the non-zero circuit problem and that's not a standard name but it's。

It's the the。The problem is basically just you're given an arithmetic circuit so you're given a circuit like composed of addition subtraction and multiplication gates which can take as input some sort of small constants like let's say zero and1 and then it can do arithmetic operations on them so and and what you'd like to know is just does the circuit output something nonze sos a very simple question and you would think it would be very simple to answer but unfortunately it may not be and the reason is that know arithmetic circuits can very very quickly produce enormous numbers by using the trick of repeated squaring so you can very very quickly produce numbers that would take exponentially many bits even just to write them down and so then you don't get a polynomial time algorithm。

If you're willing to use some randomness then we do know an algorithm okay and the algorithm that we know is basically that you pick a random prime number with some polynomial number of bits and then you do all of the arithmetic modulo that prime number okay and that reduces the size of the numbers to something manageable that you can store but and furthermore if the original circuit output something non-zero then with high probability your new circuit that does everything mod a random prime number p is also going to output something nonzero。

 there's a small chance it will fail， if the original circuit output happen to output a multiple of the prime number p that you happen to pick you could get really unlucky okay but you can do an analysis that shows that with high probability over the choice of prime number this is not going to happen okay and you a crucial point。

😊，I can't stress enough is that this analysis holds for every arithmetic circuit okay so it's not we're not saying that the algorithm works for most arithmetic circuits or something。

 you know that wouldn't be good enough， okay， we're saying that for every arithmetic circuit。

 you know the algorithm will work with high probability over the choice of prime number。😊。

Okay and the prime number is something that you pick yourself。

Okay you know the arithmetic circuit is something that your worst enemy hands do okay so that's the difference between the two right you can't assume you know that the arithmetic circuit was truly random。

 it may have been you know chosen diabolically to be you know the hardest imaginable case okay but you get to pick the prime number and so if the algorithm works with extremely high probability over the choice of prime number then that's a really good guarantee。

All right。So。So I should say， you know this nonze circuit problem is usually discussed like in a more general setting。

 which is called。Polynomial identity testing or pit。 Okay， And in this problem， you know。

 you also have an arithmetic circuit and you want to know whether it output 0 or not。 Okay。

 but now the the twist is that。Your arithmetic circuit can take variables as input， okay。

 it can take indetermmininates as input， so you can take x， let's say。

 and I could say here here's an example， I could do x plus1， I could do。嗯。This is x minus1， right？

I could multiply them。I could multiply X by itself。I could do。That minus1。I could subtract these two。

 does this circuit output put something zero or non zero？Well over here I've got x squared minus1。

 over here I've got x plus1 times x minus1。and then I'm subtracting them okay so this outputs the zero polynomial right you know x squared minus1 minus itself so in this case we would say that the encoding of this circuit is not in our language right you know if it output something non-zero then it is in our language so so the question is you know given is input you know an encoding of arithmetic circuit and say you know over constants and also over x does it not output the zero polynomial and so this this is a generalization of the non-zero circuit problem and this can also be solved in polynomial time by by an RP algorithm by a randomized algorithm okay so you you again have this issue that you could get coefficients in。

polynomial that could take exponentially many bits to write down okay you again handle that issue by doing all of the arithmetic modulo some you know randomly chosen prime number okay。

 but what about x， how do you deal with the fact that there's an x there and that you know you。

You know， you could have you know， I mean your polynomials right。

 could have exponentially you know at intermediate points could involve exponentially many different powers of x。

 and so that again would take too many bits to write down。

 can anyone think of how you would handle that。What。Yeah。

 exactly just substitute in a random value for x， you know。

 randomness is useful right this is the kind of thing it's useful for， okay。

 you can just substitute in a random value for x Okay now now and then you know check whether that gives you something non-zero okay。

 and then now the question is why why is that going to work Okay so for example。😊。

Let's say that you had a polynomial like this， let's say that you had a polynomial that was zero you know at all but one of the possible values that you might substitute in let's say the values are this。

 this， this， this， this， this， this you know and this right okay then you know almost every random value that you would substitute in you know you're going to just see the outcome of zero and you're going to output zero even though your polynomial was non-zero Okay so that that's going to give you the wrong answer with high probability yes。

Yeah， okay good question so you can you can substitute reels but the issue is if you do that。

 then we're going to have to worry about issues of like numerical precision and roundoff and all of that crap so we would you know so it's sort of for theoretical purposes it's more convenient to work over a finite field yeah。

😊，收少点嘅。Yeah。Yeah， yeah， you could substitute in a fraction and okay and then you have to worry that as you do arithmetic operations like the numerator and denominator of the fraction could grow to some enormous size right so so again it's more convenient to just do everything over a finite field and you know exactly how many bits it takes to represent every element of that field。

 namely if it's a field of P elements then you need log based2 of P bits but all right。

 but I claim that actually this scenario is not something that we really have to worry about and can anyone give me a reason why not。

😊，I'll give you a hint it has an important sounding math name。So。

You know the fundamental theorem of algebra？Okay， what it says is。😊，Well， it has several parts。

 but the only part that's going to be relevant for us is that。

So that if you have a degree D polynomial， say in one variable and it's not the all zero。

 you know it's not the zero polynomial， then it can have it most d roots there could be at most d places where it evaluates to zero why because for every point a where P of a equals0 that means that the polynomial must have a factor of x minus a and so you know if it has a degree degree at most d that it can have at most d such factors。

 mean that's the intuitive reason you have to you should be a little bit more rigorous about it but。

Okay， but now what can we- if we have like an arithmetic circuit like this。

 and what can we say about the degree of the polynomial that it produces？Well。

 so if I have a plus gate。Then you know， what is that that let's say I had two polynomials。

 P and Q on the leaves， then the degree of their sum， right？

Is at most the maximum of the degree of pay and the degree of Q？Right。Okay， if I have。A timess gate。

Then the degree of the product of P and Q is。Well， equal to， I guess the degree of pay。Plus。

 the degree of Q。That's how the degrees of polynomials work。So in fact。

 the degree of the polynomial is just going to be。You know most like if I have n gates in my circuit。

 the degree will be at most two to the end， because you know。

 the worst case is that I have a whole bunch of times gates and each one doubles the degree。Okay。

So I know an upper bound on the degree of my polynomial and now all I need to do is just choose a prime you know to work mod which is larger than2 to the n much larger。

 let's say you like you at least 10 times two to the n or something okay so I work over a finite field whose size know is many。

 many times larger than the degree of my polynomial now what's the advantage if I do that anyone。

Well， why do we want a field which is much， much larger than the degree of the polynomial yeah？

べち売ってる。Exactly， that's exactly it， yeah， so what we want is that， you know， if I pick a random point。

😊，In my field。Then with high probability I am not going to get a root right so so I want you know I want to be able to say that a non-zero polynomial actually evaluates to something nonzero on most points okay you know and that will be true by the fundamental theorem of algebra as long as I'm working over a large enough field yeah。

Yep。Nope， why not， anyone， yeah。没有。Yep。Yes， exactly you see that you know there's you know you know there are two to the n elements。

 but to represent each particular element only takes n bits or in general。

 know log of P bits where P is our number that's somewhat larger than 2 to the n。😊，So。

So that' that's the basic idea of this RP algorithm for polynomial identity testing right and you know and this is actually useful right like if you have you know some complicated algebraic expression right you want to know like whether it equals some other complicated algebraic expression right what this is telling you is that you know just look at you know。

You know， I mean， like you could just try to expand them both out and then compare if they're equal right。

 but you know it could be that expanding them out just gives you like you know trillions of terms and you know would be totally unfeasible okay what this is telling you is you really can just plug in some random values and just see whether they evaluate to the same thing on a bunch of random values and as long as you're working over as long as you make sure you're working over a large enough field that will be okay that will really work that will really that can really you know if that always checks out that can give you extreme confidence that these two algebraic expressions actually represent the same thing。

so that's a cool thing all right so so you know there's a major challenge that you know people have been working on for at least 20 years。

 which is to you know that they would like to derandomize polynomial identity testing okay which is to say you know they would like a deterministic polynomial time algorithm that you know would solve this problem and you know like the most obvious way of doing it would be to just find some like some deterministic way of choosing some you know the X's。

 the substitute find some you know and also for picking the primes the work modo。

 let's say right if you could find the deterministic way of choosing those things and then you could prove that it always work you know in other words that it worked for let's say every you know so so for every end。

😊，You could deterministically choose a polynomial in n number of X's and of primes。

 and you could prove that those worked for every arithmetic circuit of Pi N。

 okay then that would derandomize polynomial identity testing okay which would be you a major breakthrough in theoretical computer science for a bunch of reasons you know and people have。

Hey， people have actually you know。succeeduced in derandomizing special cases of this problem。

 in fact I've mentioned many times in this course that a huge breakthrough 13 years ago was when we had discovered a deterministic polynomial time algorithm for primity testing right or the algorithm of AKS。

 Agrial Kyle and Sucina， okay。I can actually， can say a tiny bit about how it works because it's interesting。

嗯 어。Okay， so here's an example of a polynomial identity， okay。

 something I just wrote down now is what I just wrote down true。okay， well， if I just wrote。

 you know， x plus y squared you know equals x squared plus y squared or something right that's you know I think that's sometimes called the freshman identity or something right you know that's certainly not true you know in general right but but not the MIT freshman identity of course okay but。

😊，But but if you know， but now I'm going to tell you that you're working mod p okay， so for example。

 x you know if I looked at x plus y squared mod2 you know that's x squared plus2 xy plus y squared okay but two times anything mod2 is0。

 so then this actually does hold so so you could say when p equals 2。

 this thing holds you know you know you could check that it also holds when does it hold when p equals 3 for。

😊，Yeah， yeah， because when p is3， you get x cubed plus you know3 x squared y plus 3 x y squared plus y cubed right。

 but then the multiples of three just die out when we mark mod3 okay so in general。

 you know we're really just asking a question about the rows of Pascal's triangle here if you think about it okay know what we're really just asking is you know。

You've all seen this thing， right？Okay， these give you the coefficients when you raise x plus y to higher and higher powers。

Okay， and。Let let me just do one more。I could just do this all day。Alright。Okay。

 and the question that we want the answer to is you know other than the one and the one。

 you know if I look at the pth row of Pascal's triangle or all of the entries divisible by p right well let's look you know。

 is that the okay and I'm going to call this like you know row0， row 1。

 row2 and so forth so is that true for row2？😊，Yes， it's true for row3。Is it true for Ro four？No。

 is it true for row5？Yeah， is it true for Ro six？No， is it true for Ro Ste？Okay。

 can anyone guess a pattern？It's true for all and for only the prime numbered rows。 Okay。

 This is an identity which you can prove holds if and only if P is prime， All right。

I don't know if I'll put that on a piece at or not， but that's。

 you know is that is something that you can prove without much difficulty Okay。

It's a fun thing to prove you just look at the binomial coefficients， you look at the， you know。

 whatever， you know。And she Ks right， know， you write them out。Like this。

And then you look at what things cancel and you look at you。I should I should have called this P。

And you look at what happens you know when P is prime versus when P is composite， so I' yeah。Yes。

 you're right you're right， you could also use well well we'll wait Fma's little theorem would tell you that this holds when P is prime right but then you also want that it doesn't hold when p is composite okay so what this tells you in some sense is that you know primity testing can be reduced to polynomial identity testing so you know in fact this is a different way to derive that there is a randomized algorithm for polynomial identity testing right okay well you have to be a little bit careful because problem is like P could be an exponentially large number it's a number with some polynomial number of digits in it that you want to know is a prime or composite。

And。And so now you're raising know， x plus y to some exponentially large power。

I I think this actually just works I think this just works okay I mean I mean you can do the arithmetic。

 you know you could substitute in random values for x and y all right fine the thing that you know the thing you have to be careful about is that your work you have polynomials of degree P but you're also working modo p right and so you you know what we really want is to work over a much larger field than you know so if I were to substitute in random values for x and y then I would want to be working over a field of size much larger than p but here I'm only working over a field of size p and the way that I deal with that is that I don't substitute in random values for x and y instead what I do is I take the remainder when I divide in other polynomial and I substitute in like a random random values for R。

😊，And I look at everything mod x to the R minus1 and then you can prove that that works and this gives you a randomized algorithm for primality testing which is different than the original ones that were discovered in the 70s okay so AKS first noticed that but then what they noticed was that you with enough effort you could prove that there's actually a deterministic list of choices for this you know x to the R minus1 a polynomally long list of them you know that will actually work that will tell you you so in other words that will have the property that if P is composite then this equality will fail to hold mod you at least one of the x to the R minus ones that you tried so they were able to derandomize a very special case of polynomial identity testing that was enough to show that primality testing is in P。

Okay， which。嗯。So。So that's just one small indication of the importance of this problem。

 it would mean lots of things for a complexity theory if we knew how to do it in general。

 but I can tell you what the conjecture is today， and it surprises some people to learn that this is the conjecture。

The conjecture of most complexity theorists is that polynomial identity testing actually should be in P and more generally。

P should equals EPP， should equal RPp should equal BPP， you know。

 they should all just come crashing down to P。Okay。

 that's kind of the popular belief today and Wally， I mean， you know this is you know。

 at first glance this is kind of funny right because usually you know we have pairs of complexity classes。

 you know， usually we can't prove they're equal， we can't prove that they're unequal。

 that's par for the course， but usually you know， you know。

 when we're in that situation we conjecture that they're not equal。😊，Right。But in this case。

 you know， you know， people conjecture that they're equal。 Okay， and the reason for that has to do。

Well， you know， mean I mean， I mean you could say one reason is the number， you know。

 there have been many， many randomized algorithms that people have figured out over the years how to derandomize how to make into deterministic ones。

 you know， primity testing being one major example of that， but you know the reason why。

People think that this is true in general have to do with the notion of pseudorandom generators okay a pseudorandom generator is just you know we're going to give a formal definition of it later but it's basically just an algorithm that takes a very。

 very short random seed and then deterministically expands it into a much。

 much longer string you know and there's much longer string obviously will not be completely random bits right because we started we's say with only a tiny amount of randomness and so can' you can't get blood from a stone you can't you you if there was kbits of randomness to start with and I did something deterministically you know then there's only K bits of randomness you know in the final outcome okay but the longer string will look random okay and you know this is a very very you know like like anyone who's done any program。

I mean it's familiar with pseudoran generators right when you call the random you know the random function or whatever is the random number function in your favorite programming language okay what it's really doing is probably just using some linear conruential random number generator okay people know what that is it's。

It's basically。you start with some number X called the seed okay the seed has to be gotten from somewhere that you think of as random generate the seed using quantum mechanical random events there actually are peripherals that you can buy。

 you can order them online that will generate quantum mechanical random numbers to order okay or or you can go on the internet and get them。

 I think random。org so so you can get a starter kit of random numbers the more common thing is that you would use the current system time at what time it is when you start the program you would ask the user to just type some random stuff on the keyboard these are all things that are actually done。

Or you would go online and maybe look at like the last digit of the Dow Jones Industrial average。

 or you know， something like that， the last digit of the temperature outside。😊。

And then once you have the seed， then you know， to keep generating more and more random numbers。

 you'll。So you'll have some fixed values。Of A and B， and。

And then you know every time you want a new quote unquote random number。

 you're just going to you know take the previous x and replace it by Ax plus B mod P that's what's called a linear congruential generator okay now these are very。

 very obviously not true random numbers in other words。

 if you were looking for a pattern in these numbers。

 you could find it okay you you could tell that you that the successive x's where were generated in this kind of way that I believe will be a piece at 6 you'll figure out how to break this generator okay but the point is that for most applications where you need random looking numbers like you know if you were writing a video game and you just wanted some bad guy to behave unpredictably you to the user or something or。

You were doing a Monte Carlo simulation and you just wanted some numbers that more or less spread out over the region that you wanted to test right this will probably work fine。

 you know for most such applications repeat do not use this for cryptography okay we'll get into that later for cryptography you're going to want much。

 much higher powered pseudoran number generators than this one okay but for sort of non-adversarial applications this usually works fine。

Good。😊，Well， you know so let's say that A B and P are just fixed once and for all。

 I think that in many programming languages， they actually- I'm not making this up。

 they fix P to be like a 32，767 you which is two to the 15 minus1。

 which is a convenient prime number just you know and other programming languages may make a different choice。

 okay or you could allow the user to specify it。😊，呃。Yeah。So you。

 this is sort of getting into the black arts， okay， you。

 we're not doing anything theoretically justified here。

Just doing something you know that tends to work in applications so okay。

 so this this you know you know you could say you know there are randomized algorithms for which you know you could actually prove rigorously that you know if you generate your random numbers using a linear congruential number generator and you feed those numbers to the randomized algorithm in place of true random numbers。

 then it will still work。😊，Okay， the randomized algorithms for which you can prove that tend to be very。

 very simple ones right you know， that's like you know， but you could say those ones， you know。

 at least you can derandomize in this way。 Okay now it's true that you still you know。

 even after you've done this， you still need a little bit of randomness right because you still do need the randomness of the seed Okay。

 but now there's a trick。And the trick。Is。Let's say that you have a pseudoran number generator which is good enough that it can take a seed with only o of log n bits and it can expand that to a random looking string。

 which is n bits which and let's say that the generator was so good that the outcome could not be distinguished from true randomness by any algorithm running it at most n squared time or something like that。

 now I take the outcome and I feed it to a randomized algorithm that takes n squared time。Okay。Okay。

 and the algorithm produces some output now now by assumption。

 you know know this has to be good this has to be just as good as feeding true random numbers to this algorithm okay because otherwise if it weren't then by that very fact would mean that this algorithm could distinguish would be distinguishing you know this pseudoran number generator from true randomness which we assumed was impossible okay you know the very fact that it worked with true random numbers and didn't work with the pseudoran numbers would mean that it was distinguishing the too okay but now how do we deal with the fact that we still need this random seed know if we want a fully deterministic algorithm。

😊，I'll give you a hint and we're going to use the fact that the seed is only log in bits along。

What can you do if something is only logger and bits long？Yeah。

 so we now want a fully deterministic algorithm that produces the same。

 you know where it runs in polynomial time， which could be more than n squared time。

 that's okay and which simulates this randomized algorithm that runs in n squared time without using any randomness at all。

Okay， we've assumed that this algorithm still works if you feed it a pseudorandom string。

 which was obtained by pumping out a seed that started with only log of n。

 oh of log n truly random bits。Yeah。Exactly， that's exactly it。 Yes， what you can do。😊。

2 use this equation2 to the O of log n equals n to the l of1 okay the exponential of a log is a polynomial okay depending on what constant is in front of this log it might be a polynomial you know or what constant is hidden in this o this might be a constant this might be a polynomial a very high degree but it is a polynomial okay guys say you can loop over every possible value of the seed。

 okay try you know each of them expand each one out。

 feed all of the resulting strings into the randomized algorithm you know then just take the majority among the results okay and then you know by the assumption you that this randomized algorithm could not distinguish this pseudoran generator from a truly random string that will be equivalent to feeding the algorithm a truly。

😊，ranandom string of the appropriate length okay that will you know that will tell you or know that will tell you the same answer okay so what this says is that in order to derandomize you know any randomized algorithm you know know that takes polynomial amount of time so in order to prove that P equals BP you know all you would need to all quote unquote you would need to show is that for every you know fixed polynomial amount of time like n squared and cubed whatever there is some pseudorandom generator that starts with a seed of logarithmic length and that fools every polynomial time algorithm running in that amount of time。

Okay， so in other words， as long as you have good enough pseudo around them number generators。

 but ones that seem totally within the realm of possibility that you could construct them。

 then p equals BPPP。😊，Okay， all right， but it's actually stronger than that。Okay。

 so there's a famous theorem of Emallyazto andvison， 1997。

 which built on a long line of a previous work， but here's what it says and says。

And saysSose that we just make some very， very mild computational hardness assumption。Okay。

 namely the following one。Okay， so says suppose that there is a language that you can you know decide in two to the end time in exponential time such that。

You know， even if I allowed a nonuniform algorithms。

 even if I allowed a different algorithm for each input length or in other words。

 I allowed just a different circuit for each input length。

 you know it would still require exponential time okay that seems really。

 really plausible right because you know how on earth right is you know is it telling you you know letting the algorithm depend on the input length going to always transform something that you know requires exponential time into something that you know that can be done in sub exponential time that's you you know letting you have a different algorithm for you know for each input length seems like a really really weak concession all right。

 so let's say you know this is plausible okay they say then using only that assumption they can construct a pseudorandom number generator with the required property you know exactly this kind here and so therefore。

😊，P would equal BPP。Okay， so this is part of why we believe this。Okay。Okay。

 but now you know to you know say more about you know you I mean a pseudorandom number generators。

 know probably like the main use of them or certainly the most you know the most important factor that sort of drove their development development of ones that were sort of powerful enough to get this kind of thing was cryptography okay and cryptography you know has other uses besides deranomization it cryptography actually you know predates computer science you know it's been cryptography is something that's been used for thousands of years I think the ancient Egyptians or something used it so I want to you know cryptography is like I think a really spectacular application area for a lot of the concepts that we've been talking about in this course right？

It's often called it' know it's the area of you know it's the part of computer science。

 maybe like where the distance you know where theory has the most direct applications you know and why well first of all。

 you know like we don't have to in cryptography we don't have to sort of tell a whole story about well you know just this problem you know fine。

 it it's almost always easy in practice， you know but we can prove it has hard cases。

 we can prove it's NP complete okay in cryptography you know you know if everything's as working as it should。

 almost every case of your problem is going to be you astronomically hard to solve okay why because we made it that way okay。

So。U。So I want to sort of in the rest of this lecture tell you about sort of some of you know the very basics of cryptography like I think it'll take me a half hour or so to cover the first few thousand years of cryptography and then and then it'll take me a few lectures to cover you the last 30 years because the truth is that know for most of you know the history of civilization people were sort of not thinking mathematically about cryptography and as a direct result of that。

 they were coming up with codes that they thought were secure but were often very。

 very easily broken。😊，Okay。Okay， so。So you know， the two most important figures in the history of cryptography are Alice and Bob。

Okay。And the most basic problem of cryptography is that Alice is trying to send Bob a message， oh。

 there's also Eve， I'm sorry。Sorry， is this should I？Okay， should she not be wearing a dress？

I don't know。是这实的。All right， there。She's okay， okay， so Alices Bob and Eve。

 these are the conventional names。😊，So Alice is trying to send a message to Bob。So she has an M。

 let's say you know。This we call the plain text。Okay， and。And she wants to send it to Bob。

 but whatever she sends is going to be read by Eve。So。

 so you know and she wants Bob to be able to read the message but Eve to not be able to read it。

 Okay so how does she do that well， you know the you know。

 for thousands of years what was assumed is that okay。

 clearly Alison and Bob were going to have to agree beforehand on some kind of code。

 some kind of you know， they're going to have to share some secret in advance that Eve does not know。

 okay， we could call that the key， okay。And then the purpose of a crypto system is to provide sort of encryption and decryption functions。

We could say that Alice sends an encryption of her plain text M using the keyK。

 and this we also call the cipher text。Okay， and then Eve sees C。

 but because you know she doesn't know K， then you know she should not be able to recover M from that Okay that's the help anyway and then but Bob gets C and Bob knows K right he agreed you know on it with Alice in advance and so now Bob can apply some decryption function to C。

😊，It'll called D sub K of C， and that is supposed to produce the plain text app。Allright。

That's the idea。And as we'll see， there are many， many other things that we also want to do in modern cryptography。

 like digital signatures and secure protocols， a whole bunch of other things it's okay。

 but this is the traditional task。Okay。So。So what kinds of， you know。

 instantiations of this scheme were used for most of history， Okay， well， maybe you know。

 the simplest example that。You know。Anyone learns is the Caesar cipher okay after Julius Caesar。

 apparently what he would do is he would just encrypt a message by adding three to each letter。

 okay like you know and if you reach Z， then you wrap back around to a okay so in other words you could say we add three moduleo 26。

😊，Okay， so let， let's take like a common sentence that anyone might say like 6045 rules， okay。

Here I'll end it with a Z so what's the Caesar encryption of this anyone？😊，Well。

 what's the encryption of S？V。 yeah， all right。You get the idea。I encrypted this right before class。

Okay， how do you decrypt well you subtract three from each of these okay wrapping back around a z when you read a all right。

 now you know this is not what we would consider an excellent cryptoy okay you know because all well you know all Eve has to know is that you are using the cipher you know and then she's done and even if she didn't know that she could probably very quickly figure it out。

😊，USo。😊，You know， in 2006 or so the head of the Sicilian mafia was you know。

 was finally caught or was finally like the Italian government was able to prosecute him after trying to build a case for 40 years or so。

 the core of the case relied on you know messages that he was sending to his subordinates。

 which he encrypted using the Caesar cipher by hand。

 which was apparently you know the traditional method in the Sicilian mafia and you know。

 he was still doing this like in the 1990s or something。 so you know。

 I guess it can be worth it to know about these things。

 you know if you're the police or whatever right， you know。

 was like you know you could just imagine the Italian version of the NSA saying， you know， seriously。

 you know。This is what you're giving。😊，U。All right。

 well you know and a very obvious problem here is that you know there's not even any randomness whatsoever in the system right so you know for thousands of years people would design cryptoyem just by just coming up with like the most complicated thing they could think of but then that complicated thing would just be fixed and and then the problem is like as soon as the adverary just knows that one complicated thing then doesn't matter anymore how complicated it is then they can break it well so eventually people learn to design cryptoytems in a very。

 very different way， which is to make the encryption and decryption algorithms themselves actually as simple as possible okay the simpler they are。

 the better but all of。The secrecy， of course there still has to be secrecy。

 but all of the stuff that Eve doesn't know should be sort of shunted into this random choice of a key K and so you should be able to sort of point to the key and say。

 you know this is the part that Eve does not know。Okay，Okay， so the。

So a simple example of that would be the latter substitution cipher。

This is just like all this means is a generalization of the Caesar cipher。

Where instead of just incrementing by three。😊，We can do an arbitrary permutation of the alphabet okay so this is you know like the word puzzles in the newspaper okay so you know it could be that every C becomes a P。

 every D becomes an X， you know， every E becomes a G。

Maybe just for good measure B goes to itself okay why not you know every A becomes an L and so forth okay so we can you know among all the 26 factorial possible permutations we choose one of them at random and then that is the KK shared by Alice and Bob and then Alice just applies you know this permutation pointwise to each of her letters sends the result to Bob and then Bob applies the inverse permutation pointwise to each of the letters you know he maps every L back to an A every P back to a C and so forth okay how do you you know this is also not a very very good cipher okay in practice how do you break a letter substitution cipher what's one way of doing it yeah。

😊，Exactly yeah， the easiest thing to do is just look at frequencies right in the English language you know E is by far the most common letter okay x is the least common letter right you have any large enough sample of text you unless it's like that that novel that was written without using the letter E you know just to prove that it could be done but you know you look at any ordinary sample of text okay you and whatever is the most common letter that one is going to be E okay so now you know E you know you know something right and you know and then you can use that you know to guess more letters right you know there's probably the word the appearing very often so whatever is E you if you see two letters appearing before that a lot of the time they may be t and H right but in general you know you can just by knowing the letter frequencies you you can figure out most of it。

😊，Okay， so so so this is also， you could say not very good。

 so what people were doing for sort of hundreds of years was really just sort of designing more and more complicated versions of the letter substitution cipher okay and in some sense you know the enigma what the Nazis were using during World War II was was some more complicated variant of letter substitution。

 it was very hard to break using just letter frequency analysis or anything like that。

 and in fact you did have to do some amount of brute force searching to break it。

 but brute force searching was you just barely within the technological capabilities of the time and so you've probably many of you have seen the movie。

you know， you know the story that Alan Touring， you know。

 really just a few years after inventing the touring machine you know was。

 you know at Bletchley Park and was involved with along with a bunch of other people you know the movie makes it like it's you know it's just his idea but it's you know there were like 10。

000 people involved， you know you know he did play a really really crucial role。

 but you know they built machines that basically you know each day the Germans would actually change the key K okay so they had a whole like codebook of different keys K you know the。

Each each uboat each submarine would have this book and on each day they would switch to a different key okay that's part of what made it so difficult okay that even if you could break the system。

 you know by brute force searching you in a matter of months by the time you broke it。

 it it's no longer the intelligence is no longer relevant。

 okay so it was needed was a really fast way of doing the brute force search so that each day you could decrypt the messages that day you could thereby know in the north where exactly in the North Atlantic。

 each of these submarines were， you could then send the American convoy ships to England in a way that maneuvered around them。

Okay， so。So that's what basically some of the first digital computers were built for for automating that bra process。

You know， I mean it was also you know there's a lot of factors in the story。

 you know it was also important that they had managed to actually capture one of the codebooks from one of the Ubos so they knew and that was like a dramatic story itself。

 the submarine was sinking but because they knew how important it was they got onto it as it was sinking and they got the book out and that still didn didn't tell you everything but you know that's sort of let you get started。

 so。at some point， so amazingly， actually the Nazis never figured out that the enigma had been broken。

 know in the entire war they did at one point you say just they knew that something was wrong they knew that like the rate of Uboat kills。

 had just declined dramatically like at some point and like 41 or 42 okay they knew that something was wrong。

 their main theory was that it was a spy within their ranks so they kept picking various Nazi officers and calling them spies and executing them at one point they said you know just to be on the safe side。

 you know they added like one more they basically increased the key size by one more ladder that then you made all the decryption go dark for six months。

Okay that was a huge huge problem for Bletchby Park that they had to deal with the fact that they had added one to the key size okay but they but they you know but basically they were operating on the theory that this was an unbreakable cipher right how are you going to do it right so this is part of the you the danger of just just sort of assuming that you know something is unbreakable without a mathematical analysis behind it okay ironically you know by this time you there already was a cryptographic code that had been proved to be unbreakable if used correctly。

 is not a very convenient one and this is why it's you it's only used for sort of you super duper high security you application so？

These days， I think militaries do use it。So the system that is theoretically unbreakable if used correctly。

 you know， I' going to have to keep adding that proviso okay is called the onetime pad。

 okay and the idea of the one-time pad you know is so ridiculously simple that it's kind of incredible that it took as long as it did for it to be discovered。

 I think it was not discovered until the 1920s， but you know the idea is this。You know。

 let's first of all， let's just forget about the fact that English has 206 letters in it， okay。

 that's just an irreleance okay， let's you know， from a modern perspective。

 a message is just a string of ones and zeros， right， it's a binary string。😊，Okay， so M， you know。

 the plain text or something like that，😊，key point is we're going to choose a keyK。

 which is also a string of bits and which is as long as M itself。

 okay the key has to be as long as the message is and the key is going to be chosen uniformly at random。

This is。If you're wondering， this is a uniformly random string。Okay and。Okay。

 so Alice and Bob have to share in advance a random string of bits。

 which is as long as whatever message they might want to exchange in the future。Okay。

And then how are we going to get the key sorry， how are we going to get the cipher text？

The cipher text is just going to be the bitwise exclusive ore of the plain text with the key。Okay。

 so 1，1，0，1，1，0，1， and so forth in this case。Okay， it's just a bitwise exclusive war。Okay。

So we could write that as it is。Excle it or K。 Okay。

 How do you if you have the cipher tax and you also have the key， how do you decrypt it anyone？Yeah。

 you see exactly the in fact， you know this is a completely symmetric crypor system right the decryption is exactly the same operation as encryption okay。

 we can say that the decryption of the ciphertex is just C exclusive order with k right you just you know exclusive order second time and then you know that just sort of takes the key off right it just you know sort of unmasks the thing okay this is C plus k which is M plus k plus K。

😊，Which is M right？😊，So the system works in a sense。And now the question is。

 what argument can we make for its security？you know so so let's say that Eve does not know K doesn't know anything about K okay you know she might have some guesses about what M is right right like like you know you can't assume that Eve knows nothing about M Gu because you in the Aent Touring movie if you saw it you you one of you they have Aent Touring has this eureka moment at some point like all these messages are starting out with you know Hail Hitler or something right and so you you can use that to help you to help you guess right in fact they did use facts like that。

 but they knew them from the very beginning， they didn't know you know。

 it didn't take them years to figure that out，😊，Okay so Alice might know something or sorry Eve might know something know about M。

 you know， but we're going to assume that K is completely random and that Alice knows nothing about it or sorry I'm sorry that Eve knows nothing about it so now what can we then say about the security of the system like what argument can we make at this point？

Well。We。Yeah。嗯。Yeah。Yeah， that's exactly the right intuition。

 I mean formally what we could say is that you know whatever M was， you know。

 we can even just take M to have been fixed okay then as we look at M bit wises exclusive word with K and as we vary this over all the possible values of K you know if these are n bit strings。

 then there are two to the end possible values of K and from Eve's point of view。

 each of those is equally likely okay then you know as we vary over over all of these possibilities。

 we are just going to get。😊，A uniformly random and bit string okay so in a very precise sense。

 Eve has zero information you know about， you know so like observing the ciphert tells Eve nothing more about M than she would have already known before okay because you know from her point of view。

 the ciphertex is just a completely random string which is completely uncorrelated with M。

 you know which contains no information about M。😊，Okay。

 so that's the security guarantee that you have right and it's a very powerful one， okay。

 this is well you know in this business it's called information Theore security。😊，Okay。

And what that means is that you know we don't have to make any assumption about you know Eve being limited in her computational power。

 limited to polynomial time， anything like that， right it doesn't matter if Eve can you know has an oracle for the halting problem okay。

 doesn't matter you know if she has infinite computing power。

 okay as long as she's not you bashing down Alice's door with an ax or something。

 you know and finding the KK doing something like that， right。

 you know observing the ciphertex just literally gives her no information。

 no additional information about him。Okay， so。Okay， now why is it called the one time pad anyway。

Yeah， bet you because it's really， really important that the keyK only be used once， you do not。

 you know， in order to preserve the security guarantee that we just sort of proved。

 it is crucial that you do not reuse the same keyK to encrypt two different plain texts。Okay。

 why is that， And does anyone know why that is？In some sense that's exactly right。

 if you reused it enough times， it would become like the substitution cipher。

 that's a good way of putting it。Mmhmm。Just check the。Yeah， and in fact。

 let me show you something very concrete that you can do if the one time pad is even just used twice。

Okay， so let's suppose that Alice you know got lazy and she sent Bob you know M1 plus K okay。

 but actually you know or maybe she wasn't even lazy， maybe she was just desperate， okay。

 maybe she had run out of keybits to use， but now she needed to send Bob another message。

 so she said what would be the harm。And just using the same K to encrypt， you know。

 just one more message。 M2。 Okay， and she sent both of these over。 Okay， now。

 what can Eve do having both of these， anyway。Yeah。She can exor them together， right。

 and what happens when she does that， she gets M1， X or K， X or M2， X or K。 What is that， anyone？

Yeah， that's just the ks cancel out so that's just M1 X or M2 Okay now that's you know。

 you could say， you know， it's not immediately clear that this is that this is useful right you know you know you know Eve now has the X or of two different plain texts you know great but you know let's say you know but but this already lets her get started doing you know crypt analysis right because you know let's suppose for example that that M1 and M2 were both bitmap images Okay here here's a good example so M1 and M2 you know are both strings that just you know encode the pixels of a bitmap okay and one of these these images you know is。

😊，You know， shows a nuclear missile silo right， shows you know the exact location of you know。

 something like that over here Okay， the other one is just a nice landscape scene， okay， it just。

 you know。😊，Has the， you know， here's the sun， here's some clouds， you know。

 but most of it is just sky， all right， now she gets these two images superimposed on each other。

 okay you know？😊，She Eve can still figure out where the Miss silo was，So yeah。

 so getting if the Eavesdroroppper can get the Xor of two different plain texts。

 then you this can be very， very bad from a security perspective and you can talk about it as a theoretical thing okay any of you heard of Julius and Ethel Rosenberg they were the famous well at least Julius was was very famous as a Soviet spy who who passed details about the Manhattan project to the Soviet Union thereby probably let them build nuclear weapons several years before they would otherwise have been able to do so in 1949 or so and the US like knew that that there were such spies they couldn't find them。

The way that they found them was actually this was one of the earliest things that the NSA did right was you know so the Soviets know had by this time they more or you know they'd learned something about cryptography and they were using onetime pads okay but guess what。

 sometimes the spies got lazy and they reus the key twice。

 okay they used the same key twice and that was exactly how they were able to get the intelligence that they led to capturing Julius and Ethel Rosenberg。

Qu according to stuff that was declassified in the 1990s。Okay， yeah。What is。Yep。

K that they use that key。 So no， that's very important that in this case you don't need to know anything about the key。

Right， yes。Like yeah wants。Oh yeah， that's right。 That's exactly right you need to know you know you need to have a shared you know understanding of which key you are using right so you know you what you could do right as long as you let's suppose you're not trying to hide the fact that you're using cryptography at all if you're doing that。

 that's called steganography that's a whole different game but let's you don't care if someone knows you're sending an encrypted message as long as know they don't know what's in it okay then you just say look you know Alice can just say look Bob。

 you go to your codebook， start on page you know 467 and start using the key from that point on。Okay。

Okay。So so you know the onetime pad you know you know。

 was like the first cryptoyt with a real theoretical analysis that you tells you that it's unbreakable if used properly。

 but it's also really hard to use properly because of this onetime nature because you know you need a huge random key key that's just as long as the message and you can't and you can then never reuse it so what this means is you know if Alice and Bob or spies right they have to agree in advance on at least as many random bits as you know they're ever going to want to communicate to each other in the future and then if they run out of key then they're out of luck。

Okay， so you know it took until the 1940s when you know Claude Shannon who we've met before was doing actually you classified work at Bell Ebs during World War II and you know he decided to just work finally just sit and you work out some of the theoretical foundations of cryptography and then I think later after the war he was able to publish it okay so the first question that Shannon asked was you know could you have a crypto system that was just like the onetime pad you know had the same theoretical you know unbreakability but that required much。

 much smaller keys what does anyone think， does anyone think that that's possible？

Well what Shannon managed to prove is that in some sense the answer is no okay you you know at least if we're not willing to make any assumptions about Eve。

 then we we then any information any information theoretically secure cryptoy requires a key that is at least as long as the message okay so how did Shannon prove that statement。

 I can actually prove it in the you know remaining three minutes of the class because it's a very like like almost everything Shannon did you know it is like you know like epically historically important and it takes two minutes to prove you know once you once you have the idea okay so。

So what we do is we consider。All the possible plain text that you know there could possibly be right let's say you know there are two to the n different plane texts right then these are just these are just all the different n bit strings that there could be so this one is0 to the n。

 this one is one to the n you know you've got everything in between All right and then。

We've also got a whole bunch of cipherts。You know， the cipherts we're not going to assume are only end bits long。

 You know， they might be longer。 Okay， but you know now we're going to assume。

Is that you know we've got some key K which is， let's say is shorter than n bits okay it's shorter than the plain text messages now a key property that you that any cryptoy has to have is decryptability so once we've got a cipher text okay then it must be that once you know a cipher text and once you know a key then get you can get uniquely back to the plain text so what that means is that each every key has to has to give you some mapping between ciphertex and plain texts and once you fix the key this be this should be a one to one you know like every。

Once you fix the key， then every ciphertex is going to map to a different plain text right every plain text is going to map to a different ciphertex Okay。

 so once we fixed the key then we've got。You know， let's say C1， you know。

 or let's say we've got M1 going to C of 42 and we've got you know M2 going to C of 78。

 you know and so forth， right， you know each key induces some mapping between ciphert and plain texts。

😊，Okay。Okay， now what we do is we， you know， we imagine that Eve has one particular cipher text。

 right that that's what Eve gets。 Okay， and now she considers now let's say Eve asks herself the question。

 what are all of the possible plain texts that could have led to this cipher text， Okay。

 assuming that I know nothing whatsoever about the key， you know as I'm not supposed to Okay now。

Okay， let's say that the key K is。Is L bits long okay。

 let's say that the key is a string in 01 to the L Okay then then then Alice， sorry。

 if Eve sees some cipher text then knowing nothing about the key。

 how many different plain texts does she now regard as possible？

2 to the L exactly right so there is one you know at most one possible plain text from Eve's point of view for each possible value of k but now。

😊。