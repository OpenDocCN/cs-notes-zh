# 加州理工学院《量子计算｜Ph219⧸CS219 Quantum Computation Fall 2020》中英字幕 p17 -17-Ph CS 219A Lecture 15 Factoring.zh_en -BV1KgffBoEUc_p17-

![](img/979b40f7b5d04c5d99f51695a950fb37_0.png)

All right， hi everybody， welcome back to Phyic Comp Science 219A for some more quantum fun。Whoa。

 whoa， whoa， I almost forgot to share the screen。Okay， I'm not going to make that mistake again。Okay。

And today， we're going to talk about a topic which was of great historical importance。

In igniting interest in quantum computation。Back in the 1990s。

 which I realized to my shock and dismay。Was before many of you were born。

And that is the discovery that。A quantum computer can be used to efficiently find the prime factors of large composite integers。

To remind you last time we talked about the quantum Fourier transform。

 how it can be executed efficiently on a quantum computer and can be used to solve the problem of period finding in a black box setting with an exponential speedup。

You can query a function。And then you can use the quantum Fourier transform and measure。

 we call that Fourier sampling of the output from the box。And from a constant number of samples。

 you can with high success probability。 if you're promised that that。

Box is evaluating period a periodic function， fine the period。

And while that can be done in the black box setting with just a constant number of queries。

 if we were limited to classical queries of the function。

 it would require an exponential number of queries if the period is an exponentially large number。

Now， that period finding algorithm that we discussed last time is， in fact， the engine that powers。

The factoring algorithm。That was discovered by up Peter Shore。

And I want to discuss that connection today now the truth is。

Once we have the period finding algorithm， the rest of it isn't really quantum。

 we need some number theory to figure out how period finding and help us solve problems of interest。

Outside the black box setting and actually sure had the problem of figuring this out， he had。

Read about Simon's algorithm。Saw that it admitted the same idea。

 admitted this kind of generalization to period finding。

 and then he had to figure out what period finding was good for and he found two applications one is to evaluating discrete algorithms i'm not going to go through that in。

Sorry， I said algorithms again， I make that mistake fairly often discrete logarithms。

And I'm not going to talk about the details of that， although there are more details in the notes。

Actually， he discovered that one first。And and then。He realized it could be used for factoring。

And both of those applications turn out to be important in modern cryptography。Now。

 after explaining the connection between period finding。And factoring。

We'll say a little bit more about period finding and see that it can be placed in kind of broader context that we can think of the method that we use。

 namely Fourier sampling。As a way of。Estimating the eigenvalues of a unitary operator。

And what's remarkable about that is that we can do that estimate with modest query complexity。

 even when the unitary is。Is exponentially large， at least if we can evaluate that unitary and powers of the unitary efficiently。

Now I've actually updated the lecture notes for。For chapter six。On the course website。呃。

I had been completely。Finished the changes that I wanted to make there。

 But I added a lot of material that had been missing。 They hadn't been updated since。

I first taught this subject。Before you， well， I guess you were probably born by then around 1998。

 maybe not， no， maybe not。So they badly needed updating and there's still more changes that I should make。

 but I did add a lot of new material， I didn't really change the stuff that we're covering today。

 although I usually could have cleaned that up a bit。

 but I added some other stuff which we're going to be covering in the rest of the course。

Some of it we're just not going to have time to cover。

 there's a rather somewhat detailed discussion there of a generalization of period finding called the Abelian hiddenden subgroup problem I'll say a little bit more about that at the end of this lecture。

And we're not going to cover that in class， it's a little technical anyway and would take a lot of time and I gave you a homework assignment。

 oh I forgot to say that here there's a new homework assignment。H。Problem set four。

And it presumes some familiarity with Grover's algorithm for doing exhaustive search with a quantum computer which we haven't covered yet。

 so I need to move on to that and the next lecture which I hope will drop not too long after this one will discuss Grover's algorithm。

There was already a discussion of Grover's algorithm in the old notes， I've revised it some。嗯。

And in the new notes， and then I added some other material。

 which we'll get to in the subsequent lectures， how to use a quantum computer to simulate the evolution of quantum systems。

 which we think is going to be one of the most important。Applications。And。

And then something which will probably be the last thing that we discuss。If we get to it。

Which is the。An example of a so called QMA complete problem。And。

That's the section on the local Hamiltonian problem at the end of。The revised notes。

These notes were actually produced by typing up some handwritten notes that were already on the lecture note page of the。

Course website and of with minor edits， it's more or less the same content as those handwritten notes。

 but。I'm aware that my handwriting can be challenging to read so having them typed will be nice there are a few figures in those handwritten notes which I haven't yet。

Recreated in the typed version and so there are a few places where I just wrote figure。

And in those cases， if you really find it necessary。

 you can find what the picture was by looking at the appropriate place in those handwritten notes。

Okay， so let's get going。嗯。All right， so。As I already said。

 the quantum part of Sho's algorithm is the subrout for finding the period。

Of any function we can compute efficiently right we discuss it in the black box setting I guess I should move this little guy's face so he's not。

In the way。U。Yeah， any function we can compute efficiently。

 we can use that order finding algorithm for because。

 of course we described it in the black box setting， but if we can simulate the box ourselves。

 we can still use the same idea。And well， I already said this too that I want to explain the connection to factoring because。

It's an important application and it will have an impact on our privacy。

Which I'll say a little bit about later in the lecture as well。Okay。

 so I have to explain to you the function that we're going to apply order finding， oh。

 I haven't said what order finding is yet。嗯m。哎呀。I'm going to explain an application of period finding to a particular function where it'll become what I'll call order finding。

So to get started， I want to consider the multiplicative group。Modulo N。

Of the integers and so what I mean by that。Is consider any integer？And then consider all of the。

Integers， which are positive。And less than the integer n， which have no common factor with n。

 so I wrote that as greatest common divisor of n and B equal to 1。And the key thing to notice。

Is that multiplication mod n for those numbers， which have no common factor within。Is a group。

And what does it mean that it's a group， well， the key thing is that the multiplication is invertible。

For every element， there's another element such that when you multiply the two elements together。

The result modo N is the multiplicative identity， multiplicative identity， namely one。

So obviously you can multiply numbers together， module N， the key content of the statement。

Is the invertibility， So how do we convince ourselves that the inverse actually exists and is unique？

So that we have a multiplicative group。Well we can think about it this way， fix any element of a。

 I want to show you that there is an inverse of a。U。And so let's consider。The product of A and B。

 where B is any other element of ZN star that is the positive integers less than n with no common factor within I'm calling ZN star for some reason。

And the。Key remark is that all of these elements will be distinct。For no two values of B。

 will I get the same product modular N？How do I know that Well suppose it's not true suppose that there are elements B and B prime of ZN star such that A B and A B prime modular n are actually equal the same remainder when I divide by n for both A B and A B prime。

Okay。This was a mistake， I guess。This is supposed to be a minus sign if I take the difference。

Of AB and A B prime。That means that zero mod n if ab is equal to ab prime， in other words。

 the difference。Is I don't know， should I try to fix that in real time。

Should probably do that kind of thing more often because I always wind up。

Coming back and doing this later。Okay， let's see if that fixed it。Okay， look I'm even still sharing。

 this is cool。All right， so I take the difference of a B and A B prime。

 I can factor that of course into a times b minus b prime。

And that has to be an integer times n if ab is equal to ab prime not n now we know that a。

 because it's an element of Z n star by definition has no common factor within n so what that means is that b minus b prime has to divide n。

Okay， because that's the only way in which this product could be a multiple event。So in other words。

 b minus b prime is0 mod n or b is equal to b prime mod n。

 so the only way for a B to be equal a B prime。Is for Bnb prime to be the same elements of ZN star。

 in other words， equal to one another mod n。Okay， so that means as we let B range over the elements of ZN star。

 the elements A B for any fixed A are all going to be distinct。

 so that means all elements of ZN star will occur in the list of values of a B as B ranges over ZN star one of those elements is going to be the identity and only one okay。

All elements of ZN star will occur once and only once as B ranges over ZN star with a fixed。

So there's some unique B for which a B is equal to1 mod n， that's the inverse B。

 such B is the inverse of a， it exists and is unique。It's convenient to。Have a notation。

For the order of Zen star， the number of elements of this group。

 That's what I meant by this notation。 In other words， the number of positive integers less than n。

 which have no common factor within。That's an important enough quantity to have a name。

 It's called the Eer Phi function。 I'm writing it as Phi event。That'll be useful to know。Now。

 for any element of Zen star， that element has what I'll call。And the order is the minimum power。

Of a， which is equal to the identity。ok。嗯。And I'll denote that as ord a comma N。

 it depends on both and the particular multiplicative group we're talking about and the element A。

 okay。We're always going to get the identity eventually。嗯。Because the powers of a actually。

We'll always form a subgroup of the group。And so they contain that the powers of A contain the identity。

 and there will be a lowest value of R for which we get the identity and that's what we call the order。

And the order of NeEA。We can regard as the period of a function。

That function is the exponential function。 Well， we call it the modular exponential function because we're talking about。

Products， modo and。In ZN star， so consider a function of x， it depends on a。

 the element of ZN star and on the integer N。It's。A to the power X mod n。

 that's what I mean by the modular exponential。ok。So like for any function。

 we can use the period finding algorithm to find the period of this function。

 the period of the function is the order。Because this obeys exactly the conditions that we assumed in period finding for。

Powers of a， which are less than the order， each power of a gives us a distinct element until we finally get to x equals r and then we start over again。

 it comes back， well， a to the r plus one will be a again。Okay。And then the cycle repeats。

 and I know that all the elements of the form a to the x when x is less than R are going to be distinct。

Because otherwise， the order would have to be something less than our because there would be。

It would mean that。There's some power of a a to the x for x less than r。

 which is equal to the identity， and so r couldn't be the order。Okay， so this is a function which is。

Periodic， it period is the order， it's one to one on its period and so we can use our period finding algorithm to find the order。

 but furthermore， this isn't completely obvious。The modular exponential is efficiently computable。

It's efficiently computable even when the exponent is exponentially large， in other words。

 I can evaluate the modular exponential in a number of steps。Which is。Poly log of the period。

I guess it actually goes like log of the period。Okay。Or I shouldn't say it that way。

It goes like log of x， Okay， and of course we will only have to worry about。

Evaluating this in our period finding algorithm。For powers， which are。You know。

 as large as the square of the period because remember in period finding。

That's what we did in order to find the period with order one success probability。

So how are we going to find an efficient way of computing the exponential even when X？

Is an exponentially large number， well the trick that we use is called repeated squaring。

Let's consider the binary expansion of an integer。Which has a。

Representation as a string of bits and bits。Xm minus1， xm minus2 dot dot dot of x0。

The integer that that represents is x m minus1，2 to the m minus1 plus x m minus2，2 to the m minus2。

And so on， so what we want to do is evaluate the modular exponential。

A to the x for some fixed element A。And that's just going to be。

A to the two to the M minus1 to the power X to the M minus1。

 which remember each one of these is a bit。 so that's either zero or one， if it's zero then。

We're just talking about one， and if it's one， then it's a to the two m minus1 and then times a to the two to the m minus2。

to the power x to the m minus2 and so on， down to a to the x0。

 and all of these products of these elements are to be evaluated in modo n to divide by n and find the remainder。

Now。This means that I need if x is exponentially large to compute powers of a。

 which are exponentially large， that still sounds hard。Well， these are powers of a。

 which are powers of two。So there's actually an easy way to do that。

If I want to find a to the two to the M。I square a at each step I divide by n and just keep the remainder。

 so I'm doing the multiplication modular n。And then I square that number again。

 and now I've got a of the fourth， Monlo N。And then I square it again and I have a to the8 and so on。

 so I only have to square m times to get the exponentially large2 to the M power of a that's what I mean by a repeated squaring。

Okay。And this is stuff we can do on a quantum computer efficiently。

 we can do multiplication efficiently in the number of bits。

 we can do the dividing by n and find the remainder efficiently。

 and I'm not going to go through that of course there's nothing particularly quantum about that either。

 but I think you know how to multiply and divide。And。That you can。Easly convince yourself。

That the number of steps that we need to do these multiplications is just going to go like a power of the number of bits in the numbers。

Okay。And because everything's modular N， I'll never need a number of bits larger than log capital N。

And。So all these things can be done efficiently。Meaning in a number of steps。

 which is polylong capital N。Okay。So。Remember for the。Period finding。

Which in this case is going to amount to order finding because I'm finding the period of the exponential function。

 we are to prepare。The sum。Over all values of x up to some maximum。

 which is going to be order un squared。If want period finding to work with high success probability。

Of x in an input registered tensored with the value of our function and then output register。

So I have to prepare this guy， but what I need is a。Quantum circuit that does the。

Evaluation of the function， and then I will consider the superposition over all all input acts。

And evaluate the function in order to generate this。Now。

 these powers of a that we just talked about found by repeated squaring。

All that can be done with a classical computer， of course。I can。

 if I'm interested in finding the order of some particular A， I can pre compute。A， a squared。

 a to the fourth， a to the eighth， and so on， I can store those in a memory。

 I can use them to construct the quantum circuit。That we're going to need so this these little boxes here represent all the operations that we need to multiply by a。

 which is some number that we know。Long capital and bits long。

And this means multiplication by a squared， this means multiplication by a to the fourth。

But we want to perform these as controlled multiplications。

So we take all the steps that we need to multiply by a， multiply by a squared and so on。

 and all of the gates inside this box， we make conditional operations conditioned on the value of another qubit。

So。This means multiply by a conditioned on x0， don't do anything if x0 is equal to 0 and multiply by a if x0 is equal to 1。

 so in other words， that's multiplying by a to the power x0。And this means multiply by a squared。

Conditioned on the value of x1， that's the same thing as multiplying by a squared raised to the power a1 and here we're。

Multiplying by eight to the fourth。Race of the power x2 and so on。Okay。

 so with a number of with this M of those controlled multiplications using the multiplication by the numbers that we pre computeutd。

I can。Evaluate the modular exponential。Okay。And that means if I consider the uniform superposition of all the values of x。

 I prepared this state。And I started out with one in this output register。

 so I'd be multiplying1 by a to the x0， a squared to the x1。

 a to the fourth to the x2 and so on okay to prepare the state we want and now you know what to do。

 you can throw away the output register and youup fourier sample the input register。

 you perform the Fourier transform， and then you measure in the computational basis and after doing that。

A constant number of times you'll be able to find the period of this function with high success probability。

 And that means you've solved order finding。 So we have an efficient way。

Of finding the order of an element or finding， in other words。

 the period of the modular exponential because we can efficiently compute。The modular exponential。

And it turns out， and I don't think this was widely appreciated before Sho's paper， as far as I know。

If you can solve order finding， then you can efficiently factor。Here's how it works。

It's a randomized algorithm。We choose a uniformly at random selected element of a。

Which is in ZN star， an element less than n。Which has no common factor within。Well， of course。

If we pick a random elements and it has a common factor within。

 we can easily find that common factor。So then we'd be done with finding a factor event。嗯。

And actually， I explained in the notes and I'm not going to explain here in class that there's an efficient classical algorithm for finding the greatest common divor。

Of two integers， we can use the Euclidean algorithm for that。So I just take my word for that。

so anyway， we can easily check that A and N have no common factor and if they do。

 we've already found a factor of n and we're very happy。嗯。

And then we find the order of a by running our order finding algorithm。Now a might be even a odd。

 and actually if it's on what the rest of what I'm going to say isn't going to work。

 until so we're going to try again with another value of a。But suppose it's even。Okay， so。

We found our the order， we know。That means that a to the r minus1 is visibleible by n。

 a to the r and1 are on the same modular n。And I can take since our is even。

This is the difference of squares， I can factorize it。

As a to the r over2 minus1 times a to the r over 2 plus1。Now we know that N。😊。

Does not divide a to the r over 2 minus1， okay， because r is the order of a。

 it's the minimal power of a， which is equal to 1 mod n。

And so it can't be that a to the r over 2 is equal to1 mod n because then r wouldn't be the order。

 it would be r over2 or something smaller。Okay， so we know n divides this product。

 it doesn't divide the first factor a the r over 2 minus1， so there are two possibilities。

It may be that a divides the second factor here， a to the R over 2 plus one。

The other possibility is that n has a common factor with both factors。

8 to the R over2 minus one and8 to the R over two plus one， and as I said， by a classical algorithm。

 if there is a common factor， we can efficiently find it。ok嘅。So we can run that algorithm。

 Euclidean algorithm， find that common factor， we find the greatest common divor。

And then we found a factor of men and we're very happy。

So there are two ways in which this routine could fail to find a factor。

 it might be that the order is actually odd rather than even and then I can't do this vectorization。

Where R over two is an in power of A。UIt may be that it turns out that the first alternative here occurs that n actually divides a to the R over2 plus one。

And I'm not going to explain it in class， but there's a discussion in the notes that in fact。

 if we just uniformly at random select a。Then half the time where these failure modes don't occur and we actually succeed in finding a factor。

Okay。So if we don't succeed first， we try again and after a few trials。

 we're very likely to succeed in finding a factor。If you want a more complete factorization。

 then you can run it again on that smaller number and find a factor of it and so on。

So we found factors of composite integers efficiently。We believe。

That this is a hard problem classically， that if n is the product of two very large primes。

Then finding one of those prime factors。Is hard classically。Why do we think that？

Because we don't know how to do it， really smart people have been trying for decades。

 strongly motivated by the application to cryptography， which I'll explain in a moment。2。

Find the prime factors of a composite inger efficiently。And it's not known how。

Best classical algorithms have a runtime which explodes as the number of bits。

In the integer n increases， not quite exponential， but super polynomial in the number of bits in n so that in practice。

 if the number n is thousands of bits long，With the best algorithms we have running on the best classical hardware。

 you know， it would take eons to。Find the prime factors。Hard problem classically， as far as we know。

 and， you know， somebody could come along tomorrow and。Discover a classical algorithm that。

Factors efficiently。That would not。Shake the foundations of complexity theory so much， you remember。

When we talked about NP completeness， I emphasize that factoring。

Is believe not to be an NP complete problem？It has the feature of being both an NP and Co NP。

 remember。Under。Widely believed assumptions。The problems that are in the intersection of NPp and Co NPP。

Are not NPP complete， so this would not cause you know NPP to come crashing down。

 it wouldn't mean p is equal to NPp nevertheless it would be quite a shock。

It would mean those really smart people have been trying to factor。All these years。

 I weren't quite as smart as we thought， certainly possible。So when Sho discovered this algorithm。

In 1994。It was exciting because a lot of excitement， I was excited。

It's funny that I got so excited really， because I was not。

Particularly interested in or knowledgeable about cryptography or anything like that。

But I had been sort of notally aware of the idea of quantum computing。

I had overlapped with Feynman on the Caltech faculty for five years， and I was well aware of his。

Interest in the topic。And he never discussed that months， we used to talk about other things。

And we had had a postdoc at Caltech before 1994 Seth Lloyd。

 who was very interested in quantum computing and he's now a famous professor at MIT and leading quantum computing researcher。

 so I had thought a little bit about these things I had read Deutst's paper。

 I hadn't been that impressed。Because I， well， I had a very wrong idea。

That quantum computing would not。Well I want to explain what the idea was it was wrong I had reasons for thinking quantum computing would not really be that powerful。

 so I was prepared to be surprised by the discovery that you could factor efficiently with the quantum computer and。

I， you know， was quite struck by it because it seemed like。

The whole idea of I wasn't an expert on complexity theory or anything。

 but the whole idea that some problems are too hard to solve and some can be solved efficiently needed to be reconsidered the difference between hard and easy problems。

Was different it seemed than。It otherwise would be because。

The world is described by quantum mechanics。I don't know if I would have known what it meant at the time to say BPP is not equal to BQP but that was the thing I was impressed by and others as well。

嗯。Again， the evidence that BPP is not equal to BqP is that we don't think。

Though we can't prove it that you can factor efficiently in randomized classical computing。

 so factoring is in BQP sure had shown。But not in BPP。So that was exciting。

 but there was another reason people were excited。Which is that the difficulty of factoring。

 the presumed difficulty of factoring is the foundation。Of schemes for doing public key cryptography。

 which are in widespread use。And which we rely on。To protect our privacy。On a daily basis。When you。

You know， when you have that little key， when you go to an H TTPS site。

It's using a public key scheme。To encrypt your communication over the internet。

 so you don't have to worry at least not as much about your credit card number being stolen much seems to get stolen every again anyway。

 but。Presumably， it's not because somebody is breaking the public key crypto。

 but for some other reason。That somebody finds out my credit card number。And。Well。

 when quantum computers are widely available。Then。Because these schemes are founded on the hardness of factoring and other problems like。

Discrete logarithms。Um。That are presumed to be hard classically when everybody's got a quantum computer that's not going to be true anymore and that will shake up electronic commerce and has implications for national security。

 not just for the US， but nations around the world rely on public key cryptography for。

Enncrypting sensitive information and you know if you can't buy things from Amazon using your credit card number anymore。

 have to we'll have to go back to real stores so it'll really。Have an impact on our lives。

So let me say something more about。What factoring has to do with cryptography？

Another hard problems actually。What we need for public key cryptoys。

Is something called a one way function。That means it's a function that's easy to compute。

 but not so easy to invert。And the existence of one way functions is itself a conjecture pretty。

Well founded one， a widely believed one。That there are functions that we can compute。Efficiently。

 but if you know the output of the function， you it's a hard problem to find the pre image。

 but we need more than that in these public key schemes。Not just a one way function。

 but what's called a trap door one way function。So。

We want it to be a function that's easy to compute and hard to invert。But in addition。

 there will be some publicly available information and some private information which。

Will be used in the evaluation of the function or of its inverse。

The publicly available information we call the public key。

Private information we call the private key。If you have the public key。

 then you can compute the function easily using the。Public key。

But you can't easily invert it unless you have the private key， if you have the private key。

 then you can invert the function。And without the private key， it's hard to invert。

That's what I mean by a trap door one way function。

So well how does that help with cryptography well here's how we would use a trapor one way function if say Alice wants to communicate privately to Bob Alice wants to send a message to Bob she wants to encrypt it。

In such a way that an adversary listening to their communication of the adversary is usually known as Eve。

 which is short for Eavesdtropper。If Eve is listening in to what Alice and Bobop are saying to one another。

 she still won't be able to break the crypto system， okay， Alice。

Can encryptpt and Bob will be able to decrypt， but Eve listening in won't be able to decrypt Alice's encoded message all right now。

A way of doing that， which actually is sometimes used， which goes back thousands of years。

Is to use some kind of shared secret key that Alice and Bob know。And but nobody else knows。

It can be just a very long string of random bits。Okay， if we had a source of randomness。

Alice could generate a long list of random bits， and then she could bit wise。

Add the bits of that long random key to the message and then because those bits are random。

 the resulting encrypted message would be completely uncorrelated。

With the actual content of the message。 And so she could send that encrypted message to Bob。

 So what's Bob supposed to do with it。 Well， it's just garbage to Bob unless he also has that secret random string。

And if he does， then he can just add it bit wise to what he receiveds。

And then he'll be able to decrypt， but you see the catch， Alice and Bob have to have a shared key。

 they have to both have the same string of random numbers and how are they going to do that。

If Alice is in Pasadena and Bob is in Chicago， okay？Well， one way。

 which is actually sometimes used is that a courier who we trust can take the secret key and put it in a briefcase and lock it to his wrist。

And make sure nobody opens that briefcase or gets a hold of it。

 and then I carry it under his close scrutiny on a plane。From LA to Chicago。

And give it to Bob and make sure Eve never has access to it so that's one way。

 but it's not very convenient in the age of the internet to communicate privately that way。

So public key is a solution to that problem， it allows Alice and Bob to communicate。

 to establish a key they can use for their private communication without the need for the courier who carries the key between them。

So here's how it works。We want Alice to send a message to Bob。Bob gets started。 He creates。

A one way function。He announces the public key， it's a trap door one way function。

 and he also generates the private key， but he doesn't tell anybody that he keeps the private key secret and only he knows it。

Now， Alice has the public key。So she can evaluate the function， our trapped or one way function。

 and she does。So she takes her。Message。And she converts it just to a string of bits。

 she writes it in an ASI code or something。And then she evaluates the function F since she has the public key。

 she can do that。With argument a， the clear text of a message and thereby obtains the encrypted form。

 the cipher text。Which is B equals F of a。All right。Now， Bob has the private key。

 so he knows how to invert the function。 He uses the private key when he receives avet。

 and he applies F inverse to it。And then he recovers the clear text， all right， and that's it。Now。

 what about poor Eve who's listening into all this？Well， she doesn't know the private key。

 so she doesn't have any way of applying F inverse if it's really a trapped or one way function。

And she can't decipher the message。If we're right about the hardness of factoring。

Then this protocol is secure or not the hardness of factoring。

 the hardness of inverting the function in general。

 I haven't said what that has to do with factoring yet that's coming in a minute。

Now notice that anybody with the public key can send a message to Bob。

once he's publicly announced the public key， not just Alice。

 but also Kathy and Danielle and Edduna and so on can all send messages to Bob。

 but only Bob will be able to decipher those messages since he's the one who has the private key。

There are other applications of these trappedor one way functions I'll just give you one more。

To give you an indication。We can use it to sign a message for a so called digital signature。

 so if there's some document。Which is a public document。

And we want to be able to verify that Bob actually signed this message。

Then there's a way of doing that with a trapor one way function。Again， Bob。

Creates our trappedor one way function， he announces the public key。

But he keeps the private key secret and now we do what I described。Before。For sending a message。

 but kind of do it in reverse。 first， Bob uses the private key。And he。Therefore。

 because he has the private key， can evaluate the inverse。Of F。And that's his signature。

 he takes the inverse of F。Applied to the public document。And that generates a signature B。

Now we want to be able to verify that that Bob， the one who Bob。

 I mean we don't necessarily know is a real name， but he's the guy who announced the public key and we want to make sure that the person who signed was really the。

I has the same identity as the person who announced the public key。So now Alice。

 who wants to check Bob's signature using the public key just evaluates。F。

Which anybody can evaluate if you have the public key applied to the signature and she checks that she gets back the public document A。

 all right。So in this case。Anyone who has the public key can verify the signature。

 but Bob's the only one who can sign。Because。He's the one who can evaluate the inverse of F。

 nobody else can。He's the only one with the private key。

The security of this signature protocol or the communication protocol rests on the hardness。

Of inverting the function when you don't have the private key。Okay。So now how does factoring come in？

A factoring is a particular way of constructing the hardness of factoring gives us a way of constructing。

A one way function。The so called RSA crypto system， which is widely used nowadays。

Is based on the hardness of factory。RSA is the name。Of three people。Revet。Simmon and Adelson。

 I think。Anyway， that's what the RSA stands for。And here's how it goes。Okay。

We got to construct this one way function。With a trap door。So Bob is going to start out。

By choosing two large prime numbers。Maybe thousands of bits long。

And he can verify that they're prime numbers。It turns out there's a。

Classical algorithm that efficiently checks the numbers of prime there's actually a much faster randomized algorithm as well。

Which succeeds with very high probability。And so we can check that they're prime。

And then he takes their product that's easy to do and typically the way RSA is used in practice nowadays。

 the resulting composite number。Is 2048 bits long。Big number， Hard to factor too many beds。

Now Bob can compute the Euler phi function of that composite， in fact， if he knows P&q。

 that's really easy。Because remember， the phi function is the number of numbers。Positive integers。

Less than n， which have no common factor。So the numbers less than n that have a common factor are the multiples of P and the multiples of Q。

 there n minus one positive integers less than1。Of which Q minus1 are multiples of P and p minus1 are multiples of Q。

And so phi is just the product of p minus1 and Q minus1 Bob knows。PNq， and so he can easily。

You can easily compute phi N。Now Bob， in generating the public and private key。

 is just going to choose some integer。Which is less than phi of n。

Which has no common factor with PhiM。Okay， such that the greatest common advisor。

Of that number E and5 n is equal to1。And then he computes the inverse modo po n of that number E。

 which I'm calling D。And I'm not going to explain that now。

 but there is some discussion in the notes of how finding the inverse in modular arithmetic is something that we can do efficiently。

B a classical algorithm， so that's no problem for Bob to find D。The inverse of E modulo phi n。

So now he's ready to make his public announcement。He announces the value of n。

 that's going to be the key that people are going to use and。Of E， another part of the public key。

Which we're going to use for encryption。But what he keeps secret is D。That's his private key。Oh。

 somebody wants to encrypt like Alice。What she evaluates is the modular exponential。

She takes the message that she wants to encrypt。And she raises it to the power E。

 which is part of the。Public key， modular N， and also being part of the key。

And she can do that efficiently because she uses repeated squaring。

 she's computing some exponentially large power of a。But repeated squaring makes that easy。

And then when Bob once to dec cryrypt， he's supposed to invert the function。

 what he does is he takes the ciphert and he raises it， he raises it to the power D。

That's his private key， again， moduleular N， and I claim that that's going to return the clear text。

 the message that Alice wants to send。All right， let's just verify the claim。Well。

 here's a true fact。That。A， you know， which we're taking to be。Some。S in less than n。嗯。And。Well。

 we can it's very unlikely to have a common factor within so we can take it to be an element of ZN star。

For any element of Zan star， if I raise it to the power phi N。I get the identity of the group。

 so a to the phi of n is equal to one modular n。Okay。

Why is that well it's something that if you ever learned about finite group theory。

 it's a special case of what you know。Which is that for any finite group and any element of the group。

If you。Raise that element to a power equal to the order of the group。

 you get the identity of the group。😊，Why is that， well， I'll just remind you。

That if you take powers of any element。嗯。That。You know， if that you're going to get a subgroup。

Of the group G。And we also know that the order of a subgroup。

Is always a advisor of the order of the group？Okay。So the。

We know the order of a is going to be the size of the subgroup that's generated by powers of a。

And that's going to have to be。A divor of the order of the group， so if I raise a to a power。

 which is the order of the group， I always get the identity。And so that's what's happening here。

 phi of n is the order of the group。ZN star A is an element。

 so a to the file verand is equal to the identity。So now。Modulular N are。Cyphert was a to the E。

And then Bob， in order to decpt， raises that to the power D。 So now we have a to the E D modular N。

 But remember， D was chosen to be the inverse of E modo Phi N。

So that means the product E is equal to one。Plus， a mini multi P and。

But a to the phi of n is equal to the identity。 So a to the1 plus phi of n times integer is a。

And so indeed， raising to the power D。Invert our trapped or one way function。And that's how。

Bob decrys。All right。Actually。嗯。To break RsA， it would be enough to solve the order finding problem。

 we usually say that you factor。To break RSA， well。

 that would also work and is part of the public key and suppose you have。An efficient way。

Of factoring N。So then you know P and Q， that means now you're as well off as。As Bob。

 you know everything Bob knows and so in particular， you know P and Q， you can compute phi of n。

And then you can inverse module， you can invert to number modulo5 of n。

 you can compute the private key yourself。And that means you'll break the protocol and you know how to decrypt。

And actually， it's enough to solve order finding。Order of A to the E and A are actually the same。

The group generated by powers of A and the group generated by powers of A to the E。

 they're the same group。In fact， we know that because we know。Well。

 we just know it we can invert a to the E we just saw。And so， of course， we don't know。

We don't know A， and that's the message Alice is trying to send。But we do know a to the。

 its's encrypted form。And so Eve。Can。Use order finding to find the order。Of the element B。

 which is sent as the cipher text。And so he knows the order of A。And he。

 what he then can do if she solves order findings， she knows the order of A。

She can and she knows E as well， so she can compute the inverse of E。Moulo， the order of a。And。

Then that's enough for her to decrypt because she can raise。The Cyphertex A to the E。

To the power detailed， I call it the inverse of E modular order of a。

 And so that's going to give her a to the power order of a times integer plus1。

 and that's just a because a to the order of a。Is equal to one。Okay。So。

If everybody had a quantum computer， RSA would not be secure。Because with quantum computers。

We can solve order finding， we can solve factoring。And。We can decpt。

So what's going to happen when everybody has a quantum computer， well， we better not use RSA anymore。

To protect our privacy。Well， you could try using longer and longer keys。

That makes it harder and harder to solve the problem， but only polynomially and since it's rather。

Unpredictable， the rate at which quantum computers will continue to advance。

 that wouldn't be a very prudent thing to do to rely on longer keys。嗯。So what are we going to do？

Well， we could say， look， it's really hard to run Sho's algorithm on a quantum computer from the perspective of current technology。

 I talked a little bit about that gap， I think in the first lecture。

We are now in what has been called the N eraa， we have devices with。Tens of qubits。

 maybe more than 50 qubits。They're noisy。And so we can。We can't。

Run very large computations on them because we just get random junk。

So we can only run relatively low up circuits and we only have in the near term maybe we'll have hundreds of qubits now for sure's algorithm we need if we wanted to break RsA we want to factor numbers which are 2048 bits long say。

嗯。Then all the arithmetic that we want to do， you know the scratch space and so on。

 maybe increases the number of bits by some modest factor。

 maybe we need three times 2048 bits or five times or something like that， than fewer than 10。

000 qubits。To evaluate that modular exponential and make the state to which we apply the Fourier transform。

And you know， the modular are exponential。Is efficient。

 but it's still fairly expensive for numbers that are thousands of bits long。

Because the modular exponential。Can you take a time which goes like the cube of the number or something like that。

And so it actually involves billions of elementary operations。And we'll need thousands。Ofquids。

And so we will need an error per gate because it's billions of operations。

Which is significantly better than one part in a billion。And。You know。

 we'll need thousands of qubits and from perspective of the current。Technology where。

We can't get the error raid per gate yet。Below the level of 10 to the minus 3。

 let alone 10 to the minus 10 or something like that。which we're going to need。

 we'll probably have to use quantum error correction。

 and that's going to blow up the cost and number of qubits。

 most likely to millions of physical qubits。And that sounds pretty far away。

Nobody really knows how far away。And that's kind of a problem that nobody knows。Well。

 nobody knows there's a spectrum of opinion about it， but it's just opinion。So you could say， well。

 let's not worry about it for now because nobody's got a quantum computer and they're not likely to have one for a long time。

But actually we should worry about it even now because there are three types of time scales we should worry about。

So one is how long will the protocols we're using now like RSA be safe against attack by quantum computers。

NotTo clear what the answer is to that。But another question is。

If we need to replace the public key infrastructure we use now by something new。

 how long is it going to take？To replace what we're using now。

By alternative protocol and all the infrastructure to support it and having it embedded in everybody's devices。

嗯。It's going to take a while too。Deploy a new standard。

And to have confidence that the new standard is secure。Another thing is when we communicate today。

Eve might be intercepting the traffic。So she knows the cipher text that we use in some secret message today。

And maybe in the future， she's going to develop a quantum computer and at that point she'll be able。

To。To figure out。What the secret message was。And we might be concerned about the communication we're doing today being deciphered in the future as well。

 in fact， when the US government。Introduces a new crypto system。

 the usual standard is they would like it to remain in use for 20 years。

 and they would like the interceptive traffic to remain secure against tag for another 30 years beyond that。

So let's say we think 30 years is the amount of time we want our。

Interceptive traffic to remain secure， let's be more modest and say， 20 years。What it。Also。

 we might think that deploying a quantum self， a quantum safe alternative will take。1en or 15 years。

So now we're talking about a total of。35 years。And so if somebody's going to have a computer。

 a quantum computer running in 2055。35 years from now。嗯。They can run Sho's algorithm and break RSA。

 though we need to worry and nobody can promise you that in 30 or 40 years。

 we won't have quantum computers。That can break these protocols。What should we do about it。

 and we should be thinking now。About the alternatives to current public key schemes that we're using today。

And there are two ways to go。One is called post quantum cryptography。

That means we use the communication infrastructure that we have now。

Using different classical public key schemes than RSA。

 which we think are secure against attack by quantum computers。So we need。

Just as RSA is based on a computational assumption。

That the adversary won't be able to factor efficiently。

 these new post quantum crypto schemes have to be based on computational assumptions that the hard problem。

 the basis of the trapor one way function，Is something that's hard to。Invert for a quantum computer。

And there are candidates for that which are being vetted。

 actually NIS the National Institute for Standards and Technology， which is supposed to come up。

With crypto standards is currently conducting a competition。

Testing different proposed post quantum crypto schemes。With the goal of selecting a few。

 which will become standardized and adopted and eventually brought into widespread use。

And the other possibility is to use quantum cryptography that is to actually use a new communication infrastructure based on quantum communication to generate secret keys。

In which Alice and Bob are connected by quantum channel and can generate a key based on principles of quantum physics。

 namely that。Quantum information can't be cloned that you can't eavesdrop on quantum communication without altering or damaging the communicated information in some way that's detectable。

And you can leverage that to come up with a scheme for key exchange。Which does not。

Require computational assumptions， it's what we call information theoretically secure。

The security rests on just the laws of quantum physics， that's good。Now。

 actually implementing it in a way which is say from attack is a different story and one has to be very careful because of so called side channel attacks。

If we're not careful， then even though the core。Of the protocol based on quantum physics might be in principle secure。

We might implement it in a way which makes it susceptible to attack。

 but although the more important issue is。We if we want to use this。

 then we're going to have to connect the world with a whole new type of communication network。

 a quantum network， maybe we'll do that someday， but it's a big deal and we have a long way to go to achieve that。

So it's important for the quantum algorithm algorithm experts， the mathematicians。

 the cryptographers。To vet carefully， these proposed post quantum crypto schemes that's called quantum resistant crypto sometimestime resistant to quantum attacks。

To convince ourselves that there really are schemes that we can trust。

That can't be broken by quantum computers。And if we're going to go the way of quantum cryptography。

 then we need a way of extending the range of quantum communication right now it's limited。By loss。

 the way you do quantum communication today is you send photons， of course。

Those are the most mobile of qubits， you can encode information in single photons。

And send it through optical fiber or through free space， but there's loss in these quantum channels。

In。The optical fiber， for example。Has a loss of。17 Db for a kilometer。

And what that means is that you can send。Photons through， let's say。嗯。100 kilometers。Of。

Optical fiber。And。10 to the 1。7 is about 50。Then。What did I say， it's 17。Well， okay。17。T B per 100 k。

 So I think I think， yeah， it's one，1 photon and 50 you'll get through。But if you try to send。

Photons1 thousand0 kilometers through optical fiber are essentially none get through like one out of 10 to the 17。

Home。So if you if you're going to extend the range to a global scale。

 we have to figure out a way of sending quantum information over those。Much longer distances。

 and that's a big challenge it'll be done someday using quantum error correction ideas。

 but it's pretty far off。The important thing is that today's cryptographers。

 if they're thinking ahead about protecting private communication decades into the future。

 they need to know。About quantum computing， they need to know what are the problems for quantum computers。

And。Only by taking that into account， can we come up with safe methods which the world could sensibly deploy？

All right， now let me come back to period finding。嗯。

I'd like to look at it from a slightly different point of view。

 sort of put it in the context of a broader task。Which we can think of what we're doing with。

The Fourier sampling。Evaluating quantum Fourier transform then measuring。

I call that Fourier sampling。It's a method for estimating eigenvalues of unitary operators。In fact。

Suppose。I consider some integer A less than n with no common factors within。Then if I consider a。

Operation， which maps computational basis state x to Ax mod n。In Hilbert space who's。Denssion。Is。

It's capital N。Then this is actually unittary。It preserves inner products。

Because it's an invertible operation。The inverse of a exists。

Because there's no common factor of A and D。And that means this is actually an invertible map of basis states to basis states okay。

 there's another unitary which multiplies by a inverse。That undoes it。Now。

Suppose the order of the element a is R。Then。The art power of this unitary is equal to the identity。

That means that the eigenvalues of the unitary are all going to be art roots of unity。

Complex numbers。Modulus1， such that when you raise to the Earth power， you get one。

Those at the form need the 2 pi I K over R。Were K。Is a non negative integer less than R？

And the corresponding eigen states are easily constructed。The state， there are a bunch of them。

 they depend on some number x0。嗯。With eigenvalue lambda K， either the 2 pi I K over R。

Can be written as a。Coherent up to phases。A uniform up to phases。

 a coherent superposition of the computational basis states given by a to the J x0。Mlaan。

Jith power of a times x0 mod went。Okay。And well， you can see that those are indeed eigenstates of this operator。

With this eigenvalue。If we multiply by a， that changes the power of a to a to the J。

It out there it goes。And so J becomes J plus one if I shift the summation here。

Replace j to the J minus1， then that means I pull out a factor of e to the 2 pi i k over R that's the eigenvalue。

Of this operator。For this eigen state。ok。So suppose I have a machine。😊。

Which can evaluate the unitary。And I would like to。Estimate eigenvalues of this unitary。Well。

 let's suppose that we have an input state。Which is an eenstate of the unitary U。

And we can do a controlled operation that applies you to some input state。Now in general。

 I'm going to have a state which is a。Superposition of different eigenstates。

 but let's suppose for now I have as an input to the unitary， an eigenstate to the unitary。

 so all it's going to do is multiply the state by the eigenvalue which I'm calling lambda so I'm denoting k lambda。

 meaning eigenstate of u with eigenvalue lambda， that's suppose we do the following thing。

We prepare a superposition of 0 and1， the Xigen state1 over two，0 plus one。

We apply this unitary to this incoming state。Conditioned on this。Cubbit register。

 which we prepared as0 plus one。So that's going to， I'll give us the state one over squared to two。

0 plus lambda 1。Lambda， I canvalue the unitary， some complex number of modlus1。

 I'd like to know what Lambda is。What am I going to do well now I'm going to measure in the basis0 plus 1。

0 minus1， or if you like， I apply headamard and then I measure in the computational basis this extra qubit。

So what's the probability when I measure in the basis0 plus or minus one that the outcome is the plus state？

Well， that's going to be the overlap squared of this state。嗯。The state of this extra andsicqubit。

With zero plus one。Or0 minus-1。 So let's say we're talking about the。Probably of the plus outcome。

 I take the inner product。Of1 over square root of 2，0 plus lambda 1 with one over square root of 2。

0 plus 1， that inner product is one half one plus lambda， take the absolute value squared to that。

Or if I want to know the probability of getting the outcome minus。

 I take the inner product of one over root20 plus lambda 1。With。1 over square root of 20 minus1。

And take the absolute value squared of that。 And so that would be  one minus lambda times1 half absolute value squared。

Let's say it's the plus case。So here I'm going to get one quarter。1 plus lambda plus lambmbda star。

Plus absolute value of lambda squared。Absolute value of lambda squared is one。

So what I have is one quarter， one plus1 plus lambda plus lambda star。Or in other words。

 one half times one plus the real part of lambmbda。If I have the minus sign here。

 it becomes one minus the real part of lambda。And so if。I。Carry out this procedure many times。

By sampling enough times， I can get an estimate of the probability of the plus outcome。

 the probability of the minus outcomes。 They sum up to one。 Of course， the probability sum up to one。

And that will give me an estimate of lambmbda。In fact， if I were promised that。

The eigenvalue is either plus one or minus one for you。Then in one shot。

I would be able to determine which it was。Since then I would always get a plus。

 if the eigenvalue is plus one， I'd always get a minus if the eigenvalue is minus one。Okay。😊。

Now that's only going to tell me about the real part of Lambda。

 I'd like to know the imaginary part as well。And I could find that out by doing the same thing。

 but now I would query state0 minus I1， I wouldn't prepare with a hatam mark。

 but with some other single cubbit unitary to make the y eigen state instead of an X eigen state。

A0 minus1。Over sorry，0 minus i1 over1 over squared of  two， put the phase I in here。

So that would become0 minus i lambda 1。But again， I'm going to measure in the x basis。嗯。

I am going to find the overlap of this state with one over square root to 20 plus one or1 over square root to 2。

0 minus1。And that means I have the probability squared。

Of one minus i lambda in the case of plus outcome times1 half squared。

Or one plus i lambda times1 half absolute value squared for the probability of the minus outcome。

So the point is that now， let's say it's the minus outcome。I'm going to get one quarter times one。

Minus I lambmbda。Plus， I Lambda star plus absolute value of lambmbda squared。

 So that's going to be one half times one plus or minus the imaginary part of Lada。Allright。

So I do that enough times and I can get a good estimate of the imaginary part as well。 In fact。

 once I know the real part。Then。There are only a few possibilities for the imaginary part。

And because the absolute value is one。哦。A modulus of complex number is one。

 and I can distinguish those pretty easily。Okay， so this is a method for determining。

The eigenvalues of a unitary。But there's a better method。

 a more efficient method that makes use of the quantum Fourier transform。Okay。

If we can compute high powers of U efficiently， then we can actually get high precision in determining the eigenvalues of a unitary。

Okay。And indeed， that's what we were able to do in our order finding algorithm。

Because we could use repeated squaring to compute modular exponentials and for the unitary that multiplies by a。

That amounted to computing high powers of the unitary。All right。So。

We do the same sort of thing that we did in our order finding algorithm， except。Here。

 just to be more general instead of considering multiplying by a or a squared or a to the fourth。

I consider applying the unitary or the square of the unitary or the fourth power of the unitary and so on。

Conditioned on。The input bits。X0， x1， x2。Which are， I guess I called them why this time。

 for some reason。And。These hademamas prepare the uniform superposition。So here， what do I have。

 I had zero plus one divided by square root of two coming in。And then for the zero。

 I do nothing for the one， this conditional unitary applies u， so it multiplies the one times lambda。

And in this register， I had one over square root of two，0 plus1， but I applied u squared。

 so the one gets multiplied by lambda squared。Here the one gets multiplied by land to the fourth and so on。

So let's some since remember Lambda。Is just a phase， I'll write it as E to the two pi I phi。

F a real number。And so what I have in this output register here。Friend the。

This least significant bit， I have one over squared to two0 plus e to the two pi I phi times 1。

Tenssored with in the second register，  one over squared to20 plus e to the 2 pi I phi times 2 times 1。

 tensored with one over the squared of 20 plus e to the2 pi I phi times 4， multiplying1， etc。

And so when we expand that all out。😊，All bit stringings occur。With equal weight except for phases。

The phase is going to be either the 2 pi I5 times y。啊。In other words。

 if I consider the binary expansion of Y。If。If a bit of y is plus one。

 then I have E2 pi I phi times the corresponding power of two， and if a bit of y zero。

 then this just becomes one okay but what this guy is when we expand out。

 it just one over the square root of2 to the n， the sum over all the values of y up to2 to the n minus1。

 if we're doing this with altogether。N of these ensyllbitates。啊。Computational basis statewide。

Alright。Well， let's suppose just for convenience。That Phi。

Has a binary expansion that terminates after unbits。

It is a bit string and bits long after the decimal point and followed by all zeros。Or in other words。

 Phi is a rational number， which I can write as manager over two to the end。Well。

 then if I do the Fourier transform。Then the Fourier transform， this is just becomes， you know。

 E to the two pi I。KY over two to the N。Which is the。

Image of the Fourier transform applied to the Bi string K。

 So if I apply the inverse Fourier transform， it's going to give me K back。And so。I can then measure。

The after doing the Fourier transform in the computational basis， and I find k。All right。

 so if I ever promise that the binary expansion。Of Phi terminates after n bits。

For a sampling would tell me exactly the value of phi that would give me， in other words。

 the eigenvalue lambda of the unitary transformation to end bits of precision。In order to do that。

 I needed to be able to compute。U up to an exponentially high power two to the n minus1。Okay。Like。

 which we were able to do in the case。A order finding in the case of the。

Modular exponential because we could do repeated squaring。Now。Of course。

 the input state here might not be an eigen state， it could be some superposition of eigenstates。

Let's say it's a superposition of eigen states。With eigenvalues。

 all of which have a binary expansion in the phase that terminates after and bits。

So this superposition， coherent superposition of eigenstates comes in。Then I do this thing。

 I for a sample measure that's going to project out a particular eigenvalue。

I measure K and then I know I have projected out in this register。The eigen State of you， which has。

The eigenvalue e to the two pi I k over 2 to the n。

And then with that Ien state I can do whatever I want with it。

 I can measure some efficiently computable observable， for example， in that state。Or learn。

Other properties I'm interested in of that state by doing suitable measurements。Now。

 it might not be that the eigenvalue Lada has the property of being either the 2 pi I k or phi。啊。

K over two to the end， E the  two pi I。P。Okay， over two to the n。But。You know。

 we can use the same trick as in our period finding algorithm。Are we。

Do this with high enough powers of U so that the Fourier transform， although not perfectly peaked。

 will be sharply peaked and will be able to get a rational approximation。

To the phase in the eigenvalue to some large number of bits of precision。So。In other words。

If we can compute you。To a power。In particular， powers that are。Powers of two。

And let's say we can do that efficiently。Um，Up to some power t。

 then that's enough for us to measure eigenvalues of u to precision。

 which is some constant times one over t。We do it by Fourier sampling we do it by creating a state that looks like this well here i'm i'm prejuiccing you a little bit because I want to。

Advertise this as a kind of time uncertainty time energy， uncertainty relation。

Think of the eigenvalue。As an eigenvalue of a time evolution operator。

 e to the minus I Hamiltonian times t。Or think of what we're trying to learn as an energy eigenvalue。

So we have an energy eigenstate， we can evolve according to some Hamiltonian。

 the energy eigenstate phase。Rotates like e to the minus IET， where E is the energy eigenvalue。And。

We evolved for time T conditioned on the time in some input register， these are the input registers。

So what I prepare here。In another language。Is a。For each eigenvalue E。I get a superposition。

Of the time register， the value of little T。With the phase E the minus IET。

That sum will be multiplying the energy eigenstate with energy E。

Then I do the quantum Fourier transform to this time register。To measure a frequency。Well。

 the frequency is E it's the。Circular frequency at which。The phase is rotating as a function of time。

So if I can。Evaluate。The time evolution operator， which applies e to the minus Iht where H is a Hamiltonian。

To an income state efficiently。Up to some time。Little or capital T。

 Then I will be able to use this phase estimation method。

To find the energy eigenvalue to a precision， which goes like one over capital T。

 that time of evolution that I'm able to simulate。And that's the method that we're going to use in a future lecture。

Two estimate energy eigenvalue as well， I pretty much already told you how it works。

But I'll revisit it a little bit later。Now this method for estimating the the end that on my last slide。

 I guess it is yeah。

![](img/979b40f7b5d04c5d99f51695a950fb37_2.png)

![](img/979b40f7b5d04c5d99f51695a950fb37_3.png)

For estimating eigenvalues of unitaries， this was discovered by Catayev after Sho's algorithm。

Later that same year， it's interesting story， Alexigatiev at the time was at the Landau Institute in Moscow。

And。He heard the rumor。That Peter Shore had made a striking discovery how to efficiently factor numbers。

On a quantum computer。But he didn't have access to the preprint it was not on the preprint archive it could have been。

 but it wasn't， so you had to be in the circle of acquaintances of Peter Shor and his friends。

To actually get a hold of it。So I heard about Shore's algorithm in May of 1994。

He discovered it in April。The people close to shore found out about it soon later。

 soon after actually gave a talk about it at Bell Labs where he was working at the time。And。

But I wasn't in that circle， however。Aror record at that time， a professor at。At Oxford。

Visited Caltech in May of 1994 and he gave a talk at which was actually about quantum cryptography。

 but he mentioned this factoring algorithm at the end that was the first I heard about it I was fascinated by it he was kind enough to。

Share the paper with me。The preprint。And not long after I went to。Cambridge for a workshop。

 it was actually about black holess， I was there for a month。And so most of the time。

 we were having very interesting discussions about the quantum physics of black holes。

 but secretly when I was in the privacy of my office， I was trying to understand Sho's paper。

 which was a bit challenging for me。Since it involved a lot of ideas I wasn't very familiar with。

 I didn't know much about algorithms or the number theory and this was a rather terse version of the paper later a more discursive expanded version appeared。

But that was kind of how I got started on quantum computing， not realizing。

That as I got deeper into the subject， I was in the midst of a kind of。

Mid career transition in my area of study from。Particle physics to quantum computing。

But that's what happened Now there's an interesting story about Shoa's discovery he。

 as I mentioned earlier in the lecture， read Simon's paper。

And he had the idea that you could use a method similar to the one in Simon's algorithm。

To solve the problem of period finding。He did not immediately know what that was good for。

HeI'll explain this in a minute。He。First， discovered a method for。AComp discrete logarithms with。

Period finding。And that also has cryptographic implications。

 which I mentioned in the lecture notes I'm not going to go over that now。

 that can be used to break a method for key exchange called the Diffy Heman protocol。

 if you can which is based on the hardness。Of inverting the exponential function of computing。

Discreet logarithms。And he gave a talk at Bell where he。He spoke about this。

Algorithm for solving discrete logarithms。Now， meanwhile， in Berkeley。

 Uish Vasani was interested in quantum computing and had written a foundational paper about it the year before。

嗯。And。Somehow the rumor managed tod driftft across the country。From Bell Labs to Berkeley。

And Uish heard about it， but when he heard about it。He heard a slightly garbled version meanwhile。

Peter caught a cold and he was sick in bed。And while he was pondering what you could do with period finding。

Having already discovered the application to discrete logarithms， he realized that you could。

Use period finding to factor， as I explained earlier in the lecture。And not within minutes。

 according to the story that Peter told me， after coming to that realization。

 the phone rang and it was Uish Baserrai and he said，"Peter。

 I've heard you discovered how to factor numbers with the quantum computer。

Which was rather amazing because Peter just realized it， you know， that day all in his sick bed。

But what had happened was that as the rumor had propagated。From the East Coast of the West Coast。

 it had been garbled into the form that it wasn't discrete logarithms。

 but factoring that had been solved。Which actually turned out to be true。

Now what about discrete logarithms， there's some discussion in the notes which。

I'm not that happy with， I think it should be clearer。

 but it's part of what I added to the revised version of the notes which were just posted。

Discussion of the obbelian hidden subgroup problem。And this is a generalization of period finding。

You can think of it as period finding in higher dimensions。嗯。That is。We can。Consider。A。Well。

 consider finding periods on a。On a higher dimensional lattice。

You knowIf you think about factoring or about period finding。

There's some function of a single integer。And the。The function is periodic。And with Fourier sampling。

 we can learn the period， but I could consider and set a function of many integers。

And now the we can think of， say。And tuole of endinatures as being like a point on a lattice。

 think of a hypercbic lattice。All the。The integer valued。And tus form a lattice。Of points in space。

 which has a。You know， a periodicity property， the lattice。

 if you shifted it by one unit in any one of n directions， the lattice returns to itself。

But we can consider a function。Which takes points on that lattice as input。

Which has the property of being constant and distinct on some sublatuce。

So in the one dimensional case where we're talking about period finding。That means that。

The sublatuce consists of points which are separated by distance R。

And so there are a bunch of different sublates that you can get by shifting until you've shifted by R and then you get back to the。

The original lattice with spacing R。And on each one of those sublauces。

 the function takes a different value。On a single sublatuce it takes a fixed value。

 so all the points in that sublatuce get mapped to the same output。

Now we can think of a higher dimensional version。Of that where now we have。This hyper cubic。

And dimensional lattice and a function which is constant and distinct on some subla。Okay。

 and then the problem is to find that sublatuce just like in one dimension。

 the problem was to find the period。And this is called the Abelian hiddendden subgroup problem。

Because it can be thought of in group theory language。Where u。In fact， any ob billionian group。Well。

 I'm goingt have to go into all that can you can think of the sublatuce as being a subgroup of an abelion group。

And so but the problem is finding this subplanttius。

 that's called the abelian hidden subgroup problem。And the way you do it is by four you sampling。

Now you do the Fourier transform not in one dimension， but in n dimension。And when you Fourier。

Analyze。A lattice in a sublat of these。You know because again， same story as before。

 you consider some fixed output and then you have a uniform superposition of all the points of which are mapped to that output and those are all the points in the sublat you want to find the sublat。

Similar to period finding or Simon's algorithm。And the way you do it is by doing a Fourier transform and measuring。

And by Fourier tramps transforming and measuring by Fourier sampling。

 you actually sample from what is called the dual lattice of that sublatuce。

If you've taken a course on solid state physics， you're familiar with this notion of dual lattice。

 sometimes in the condensed matter literature called reciprocal lattice。You have a lattice。

And then you can consider all the vectors which are orthogonal to all the points on that lattice that forms the reciprocal lattice or dual lattice。

And if you know the dual lattice， then you can find the lattice。

And so the idea is you query a function which is constant and distinct on some sublatuce。

And and then you for sample， so you are sampling points from the dual lattice once you have enough samples。

 you can uniquely fix the dual lattice and from that you can learn the lattice and that's how the ailian hidden subgroup problem is solved。

So coming back to Alexi Kataya， stuck in Moscow， he wasn't able to get a hold of the preprint。

 but being a pretty smart guy， he figured he knew this is the key thing， he knew the answer。

 he knew it was possible。To find an efficient factoring algorithm and all he had to do was figure out how to do it so he did that on his own。

And the way he did it was he solved this more general problem。

 well not quite as general as what I just said， but essentially the idea。

Of Fourier sampling to determine dual lattice to find a lattice using the。

 and he also invented this idea of phase estimation。Of using Fourier sampling。To find。

Eigenvalues of a unitary operator。 I'm giving him a little bit too much credit， but essentially。

 he figured all that out without having access to the paper， but he had two things going for him。One。

 he knew it was possible to find a factoring algorithm and he was determined to do it。

 it's much easier when you know it's possible and also he's a genius so he was able to figure it out。

Well， like I said， I have some stuff in the notes about this more general problem。

 the ailian hidden i'm not going to go through that in class because really I want to get to。

To discussing using quantum computers for exhaustive search for speeding up exhaustive search。

 the so called Grover's algorithm。Because there are homework problems， which I asked you to do。

Would have to do with Grover's problem so I have a Grover's algorithm。

 I have some obligation to cover it in lecture。And that's what I'm going to do in the next lecture。

So until then， it's been a pleasure to see you all again。



![](img/979b40f7b5d04c5d99f51695a950fb37_5.png)

Thanks for viewing these lectures， I hope you're enjoying them。

And I look forward to seeing you again soon， in the meantime。Take care of yourselves。

 everyone be well， and I'll see you soon， bye bye。