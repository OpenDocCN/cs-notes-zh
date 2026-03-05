# 伊利诺伊大学【中英⚡算法｜CS473 Fall 2022 Algorithms】 p02 P2 2. Fast Fourier Transform + -BV1RdBTBrEdx_p2-

![](img/d4154c8dd909c771c06a8a259ac2962a_0.png)

Okay。So welcome back to CS473。U。We're still in the middle of setting things up。

 there's still a fair amount of churn which is why the video for Tuesday's lecture wasn't up on the Media space website until about an hour ago。

😡，I will hopefully get better at that as the semester progresses。

Most of you at this point seem to have found your way。You have to。Crate an account。

Your Illinois buddy do you address。You can't use your favorite Gmail or whatever to log in。

Same goes for a great scope。嗯。Yeah， there's a question back there。Sorry， oh， okay。

Places to upload solutions to zero on grade scopepe should be up。

Sometime later today or possibly tomorrow morning。Again， the homework isn't due until Tuesday。

 so we've got a bit of slack for that。officeffice hours have started I posted an announcement on Ed discussion and I put a list of all of the office hours at the bottom of the main web page most of the office hours are on。

Fridays and Mondays， because the homeworks are due Tuesday evening。

But if everybody comes to the Monday afternoon office hours。

 nobody is going to be helped by the Monday afternoon office hours。

So please start on the homework early， I know a few of you have actually started on the homework and in fact a few of you have actually finished the homework。

That's great， keep it up， but please don't wait until the last minute to get started。

 the earlier you can start the earlier you can act for help if you need it and the earlier you can help other people if you don't need help yourself。

Any administrative or logistical questions？Oh， one question that I got yesterday。

 I don't know if this has been cleared up。There's still a small number of seats。

 but because of the way the CS Department runs things。

 they weren't available on Tuesday that may have been cleared up by now。

If you're still unable to register by Tuesday， please come talk to me otherwise just sort of watch the registration system。

 things may open up。Uh we've got a cap of 200 and the last I checked， we had 188 people here。

So there is a little bit more room。Yeah。So。So。So okay， at the beginning of the semester。

 I enrolled everybody who was registered into grade scopepe。😡，If you registered late。

Send me either an email or a direct message on Ed discussion， and I'll add you to gradeco。

Other questions。Cool， so。😡，Last time。I talked about。Recursion。And in particular。

 flavor recursion that we call divide and conquer， and specifically I talked about fast algorithms for multiplying integers。

There's this algorithm by Anatoole Ktsubba。Which instead of the naive and squared running time。

 which comes from the algorithm that you learned as a kid， runs in time about n to the 1。6。

And I mentioned that a steady sequence of improvements for that that ultimately as of 2019 led to an N log N5 algorithm。

And the key component of that。😊，Is something called a fast Fourier transform。Now。

If you were a physicist， if you were an electrical engineer。

You are a certain flavor of mathematician， you already know Fourier transforms as a way of taking a continuous signal。

Sming it from amplitude space into puy space basically is a way of doing frequency analysis。

I'm going to be doing a that。😡，And the motivating application。For this。To keep things simple。

 I'm not going to talk about manipulating integers with。😡，many digits。

 rather I'm going to be talking about manipulating polynomials。😡，So polynomial。

Is any function of the form？啊。A sub I x to the I and of course， the coefficient here should be。

The index on the for loop should be an eye。嗯。That way looking thing。

 this is a computer science class， so that's pronounced for loop。嗯。So。For all I from one to N。

 I add the product of AMI， which is something fixed coefficient。😡。

To the if power of the quantity that I input into my function。So， I mean。

 you can see that exact formula written out in pseudocode。😡，Over here on the left。

 this is code to evaluate the polynomial represented by an array of coefficients。😡。

Add a particular value x and it's out that value is y and for the mathematicians in the room。

 this little device right here。😡，Its pronounced sigma。嗯。But okay。

 so we've got these these polynomial functions they're used。😡。

Everywhere they're used for signal processing， they're used in computer graphics。

 they're used in scientific computing for doing physics simulations。

 but just taking the polynomial and value and evaluating is not the only thing we want to do。

 we want to play with these functions。Be able to combine them in various ways。 so in particular。

 it would be really nice to be able to take two polynomials and compute their sum as a new polynomial。

So that's what this second piece of pseudocode does。And given two arrays of coefficients， P and Q。

 and I compute a third array of coefficients R。And the polynomial represented by the array R is the sum of the polynomials represented by P and Q。

And it's exactly what you would think。The Jth coefficient of R is just the sum of the Jth coefficients of P and Q。

😡，Right。This is exactly mirroring the standard algorithm for adding long integers except we don't have to worry about carriess。

😡，And then we also like to be able to multiply。😡，Polynomials。

 so given two arrays of coefficients for two polynomials P and Q。

 we'd like to produce the array of coefficients for their product。And again。

 just like we do normally for integers， we can express the multiplication algorithm in terms of a pair of nested loops。

😡，Where in the innermost loop， we're multiplying one coefficient of one polynomial by some other coefficient of the other。

And then taking that partial product and adding it as a contribution to the correct coefficient of the output polynomial。

So again， ignoring carries， this is exactly the same as the standard。😡。

Alrithm that you learned as a kid for multiplying numbers。So these things are relatively simple。

 relatively well known and relatively fast。But already。

You should maybe be getting a little bit excited because， well。

Excited maybe putting it a bit strongly。 if you're a math nerd， maybe be getting a little excited。

Because we've got this pdratic algorithm here that resembles integer multiplication and we already know ways of speeding that up。

So that is in fact what we're aiming to speed up and by the end of the lecture。😡。

We'll have an algorithm to replace this thing on the right that runs in in log in time。😡，Okay。Now。

The interesting thing about this， though。I。We've chosen a data structure。To represent polynomials。

We've decided that we're going to represent our polynomials by an array of coefficients。

But that is not the only useful representation。It's not the only way we can represent these functions。

So there are at least two other ways of doing this。嗯。Suggestions。Yeah。Okay， so by points。

 I can remember back from high school geometry that two points in the plane determine a unique line。

😡，Saying that differently， if I know the value of a degree one polynomial at x1 and x2。😡。

That completely determines the degree one polynomial， otherwise known as a line。Okay， so I can。啊。

Use a sample representation。Fix for purposes of discussion enough。

Sample positions that when you know the values， you specified the function uniquely， so let's fix。

For a polynomial of degree n， you need n plus one of these， so I'm going to start to count at zero。

So these are， this is where I'm going to evaluate。😡，The polynomial。And now my representation。

Is y0 y1 up through Yn。Where each y subbi is the value of the polynomial。At that sample position X S。

是。So。It sounds way a bit。U。Essentially， what I'm doing is drawing a plot。I'm saying here， here， here。

 and here， if I know the values of this， say a degree three polynomial at those four points。

Then there is exactly one。Cubic polynomial that interpolates through those three points。H。Okay。

So let's go through the operations that we might want to perform。😡，On polynomials。

 how would we add two polynomials in this sample representation。

 assuming that they sample at exactly the same location？😡，Yeah， you add the y values together。

So the value of the sum at x0。Is the value of one polynomial x0 plus the value of the other polynomial at x0？

Now how would you multiply two polynomials represented by sample values？嗯，好，这个搞了。

You can just multiply the y values。😡，The value of the product at x0 is the value of p at x0 times the value of Q at x0。

😡，Now with a slight。The small subtly here， you need to sample the original polynomials P and Q at enough points。

So that when you compute the product at every sample point。

 you have enough sample values to specify the product uniquely。😡，Okay。

 so if I want to multiply two polynomials of degree three。😡，Because the result has degree six。

 I need to start off with seven samples for each of those two polynomials。😡，Okay， but。You know。

 I can add。In linear time。I can multiply。With some caveats。In linear time。So this is much better。

Then the coefficient representation。😡，For doing arithmetic。

So why don't we just always do it this way？And part of the answer to this is。In some contexts。

 in some applications of polynomials， we do always do it this way。

But if I want to support all three of these operations。Each with small running time。What goes wrong？

Oh。I want to evaluate the polynomial now at a new value x。How do I do that？And well， the answer is。

 well， there's this lovely formula here。Whi of course you should have thought of immediately。

 this is a formula by LaGrange from the 1700s that says， okay。

 if I want to compute the value of the polynomial at a new value x。Then I need to take thesm。

For loop。Of this weird expression， which involves。Another layer of four loops。

 I know it's not a back it's a you know， it's upside down you instead of a side with them。

 but it's still pronounced four loop。😡，Um， so I've got a four loop with two four loops inside it。

But if I evaluate this expression。Plugging in the unknown value X in the right place。😡。

I will get out the value of the polynomial at this unknown value x。And well， it's nested for loops。

So if I want to do valuation。Now suddenly I need n squared time。So I've made multiplication faster。

 but at the expense of evaluation。Okay。Now I claim that there's actually a third representation where you can do both evaluation and multiplication quickly。

😡，Yeah， in the back。Roots。You can store the roots of the polynomial。

 so the fundamental theorem of algebra says every polynomial degree N has exactly n roots。

 some of these roots may be imaginary， some of these roots may coincide。

The polynomial x squared has two roots，0 and0。But nevertheless。

 I can identify any polynomial uniquely。By telling you its roots。And one small。Adjustment so。

I can write。P of x as。For loop from i equals1 to n of。X minus the I root。

But then in order to completely remove ambiguity， I need to adjust this by multiplying by a scalar factor。

😡，So no matter what scalar factor I put in there， that for loop is going to evaluate to zero at each of the roots。

 and so when I multiply it's going to do the right thing， but I need to。😡。

Adjust for vertical scaling in the graph。I could do that by fixing the scalar multiple at the beginning。

Yeah。Okay。So， now。When I want to do evaluation， well I just plug X into that single for loop。

 there's no nesting， so that's order N。How do I multiply two polynomials in this representation？

I just take the vector of roots of one and the vector roots of the other， and I concatenate them。😡。

And I multipied the scale vectors。Right， so。That's。Mulipplication。That's also order N。嗯。

How do I add them？It kind of crude。There's no sensible relationship between the roots of two polynomials in the roots of their sum。

😡，You can't just add the roots or something simple like that really the simplest way to do this is to convert。

From this root representation， multiply those mononoials out to get coefficients and then add those coefficients。

😡，And then you have to compute the roots of a polynomial。And we're in the wrong class for that。

 That's numerical analysis。We're generally going to be dealing with exact answers and so and that's not even possible in principle if the polynomial has degree greater than four and that no。

 just this is not the representation we want。So really is no good way。

To do addition when you use this root representation。 so we're kind of left with。嗯。

These two useful representations for our purposes。😡。

One of which has fast evaluation and slow multiplication。

 the other has slow evaluation and fast multiplication， and both of them support fast addition which。

We threw out roots because you can't do addition at all。嗯。So。This is annoying。This is by the way。

 a very， very common phenomenon when you're designing algorithms or more generally when you're designing data structures that you design the data structure that you want to support several different types of operations。

 depending on which data structure you use， some operations will be fast while others are slow。😡，And。

It won't actually turn out to be true here， but sometimes those trade offs are forced。😡。

There is no sense in which one choice is objectively better than the other。

 just depends on how you're using them。😡，In this case we'll be able to get a way to move around quickly so that everything is efficient yeah why can't you just evaluate both the phnoials and then add the sum together in。

嗯。Because what you just got was a sum of sample values。Not the root of the sum polynomial。Yeah。

 if you want to end up in the same representation that you started with。

You can convert from roots to sample values， or you can convert from roots to coefficients。

But then after you've done the addition， you need to convert back and we don't know how to do that。好。

Yeah。All right。So。I want to figure out a way to do。This conversion。You know， so the question is。

 can we？Convert。From one representation to another quickly。

Because if we could convert from coefficients to samples quickly。

 the way you would multiply two polynomials in coefficient representation。😡。

You take your coefficient vector and you turn it into a sample vector。

 do the fast thing to multiply polynomials in sample representation。

 and then do quick conversion back to coefficients。😡，For symmetrically。

 if I wanted to evaluate a polynomial represented by samples。

 I could first quickly convert it into coefficient form and then run the linear time evaluation procedure。

😡，系。So。Be nice if I could convert back and forth between these things quickly。😡。

So let's think a little bit about what that conversion actually is。

 so here I have this lovely little matrix equation。😡，U。This is the conversion from。😡，Coicients。

The vector of A's。To sample values。T wise。Okayy so。嗯。Converting。coefficients。To samples。

Is a linear transformation？In fact， what you're doing。😡。

Is you're exploiting the fact that the space of all polynomials with degree n minus1。😡。

Is a vector space with dimension N。Where you can use。Coordnates to specify polynomials in one basis。

And you can use samples to specify those vectors in a different basis。

 So when you're doing this matrix vector multiplication。

 what you're really doing is defining a new basis for the vector space of polynomials。

That supports fast。Mulplication。From a basis that supports fast evaluation。还有。I think that's right。

Okay。This object here。This is called sorry。嗯。Vandermon matrixtri。嗯。

Specifically the leftmost columns all ones， the second column is the sample positions。

 the third column is the squares of the sample positions and so on up through higher and higher powers。

 this matrix is guaranteed， not to be singular， it's determinant is not equal to zero。

 there's actually fairly straight fairly simple expression for the determinant of this matrix。

Which is basically buried in that LaGrange formula。So I can。Do。The conversion from。Coics。

To sample values by evaluating this matrix vector product。

So how long does it take to complete this matrix vector product？Anyone remember？N squared。Right。

 the naive algorithm， yeah question。I'm sorry， yeah， if some samples happens to be at the root。

 we have this create。If some sample happens to be at the root， then you'll get a zero over here。

That's okay。The the the。Then the value will be zero。😡，对二。

I should say if the sample positions have to be distinct。

 so you can't have two sample positions that coincide。😡，Then then you would get a degeneracy。

All right。嗯。But I claim that there's a degree of freedom here that I haven't exploited。And。

This is always， you know， if you want to look for how to improve your algorithm。😡。

A very common way of finding a place where you can crack into the algorithm and make it better is ask。

A I making things too general？😡，Is there a degree of freedom where I have choice that I haven't exploited？

And。I do have a degree of freedom here。This expression here and this ncord algorithm works。😡。

No matter which sample positions I choose。😡，等会。Well， so as you can start thinking now。

 maybe I can design better a specific set of sample values。That gives this matrix more structure。

And that because this matrix has more structure， I can compute this matrix vector product more quickly。

So one suggestion was maybe we could have the sample values be evenly spaced along the number line that as far as I'm not sure if that would work。

At least I'm not sure what structure that would impose that would give you a faster algorithm。

I'm not saying that's not corrected Im saying I just don't know how to do it。Um， butum。

There is a way to do this。And I can kind of describe。

The property that I want the sample values to have。And the algorithm underlying。That assumption。

And then we'll figure out how to derive an explicit set of sample values that satisfies those constraints。

Okay。So。I want to think in terms of divide and conquer algorithms。😡，Now。

 when we talked about Kt Suba's algorithm。We took a number called x and a number called Y。

And we multiplied them and the way we did that was by taking the arrays of digits and splitting them into smaller arrays。

😡，And reducing to various multiplications involving these smaller numbers， AB，C and D。😡，I took the。

The top half and the bottom half。Of the digits。I'm going to do something that seems a little bit strange。

 but actually seems to work out better。I'm going to write P of x。As the sum of two polynomials。

 but it's not going to be like one polynomial captures the most significant coefficients and the other captures the lower。

 less significant coefficients。😡，Instead。Let me make sure I get this right。X times that。

Okay so I'm going to take the even coefficients and the even degree coefficients and I'm going to pull them off。

😡，To get a polynomial of degree N number two。And our N minus one over two。

And I'm going to take the odd coefficients and pull them off to get a different polynomial degree and minus1 over two。

 so if my polynomial is x cubed plus 3 x squared minus2 x plus 5，This is P of x。

Then P odd is going to have the odd coefficients and P even is going to have the even coefficients。

So。These odd terms end up here。And these even terms end up here。So these are really just in memory。

 these are just going to be represented as as。So。U I guess。

Probably I put the least certificate in on the left so5 minus23， one， and that would be split into。5。

3。And minus21。So this expression that I've written here in red is really what I want to exploit。

 I want to reduce the evaluation of a single degree n polynomial at X。😡。

To two instances of evaluating a degree n over two polynomial at x squared。

So I'm reducing the degree by a factor of two。Now。The thing is when I do this。

I'm going to be taking a set of end sample values and trying to apply this logic。😡。

And so'm but in order to kind of do things recursively。

 I need to make sure that when I do the recursion， I really only have n over two distinct sample values that I need to evaluate so I'm going to define。

😡，My set acts to be。Collapsible。If one of two things happens。Well。

 there's the trivial base case where X only has one value in it。

 they only need to compute one sample value， it's the constant coefficient。

 it's also the value of the polynomial， so it is simultaneously a coefficient representation and a sample representation。

嗯。And。The set x squared， which is just the set of all squares of elements in this set X。I'm sorry or。

Is collapsible？And has。嗯。X over two elements。So if I had a collapsible set of sample positions。

Then I could evaluate my polynomial at every single one of those positions。😡。

By pulling off the even coefficients， evaluating that lower degree polynomial。

Over the smaller collapsible set x capital x squared and pull off all the even coefficients and evaluate that smaller degree polynomial again over this smaller set of sample values called capital x squared。

Okay， so I've reduced evaluating a polynomial degree n at N places。😡，To evaluating。

One polynomial degree n over two at n over two places and another polynomial evaluate。

And evaluating another polynomial degree at N over two places。Yes。Excuse me。Thanks。Well， rumor。

 this is a polynomial of degree N。So it only has n non zero coefficients。

If all the odd ones happen to be zero。Then the first recursive call is always going to return zero。

But then they still have the second recursive call over the P even。Which is going to be yeah so。

A changing A here or as well Im assuming because if you're changing coefficients then or just rearranging a over there or not no this so this this array here is a。

 this is the array of coefficients。You don't at all。 this change access of。

So P is represented by an array A of coefficients。P odd is represented by an array A oddd of coefficients。

 which contains all of the odd index entriesries in a。

P even is represented by an array A even of coefficients。

 which contains all the even indexed entries in a。Yeah。Okay。嗯。So if we。White T of n is the time。

To evaluate。Polynomial。Of degree N。At a collapsible set。Of and sample positions。

Then we have a recurrence。Which。You've probably seen before。

I make one recursive call to deal with the even coefficients at the smaller sample set。

I make another recursive call to deal with the odd coefficients and the smaller sample set。

 and then I need linear time to do things like addition shifting by N， bookkeeping。

 running the for loops。Yes。I。It's only mortgage taxes。Okay， so if x is not collapsible。😡。

Then when I need to evaluate， right， remember， I'm trying to evaluate this polynomial P of x at n different values。

😡，So in order to do that， I need to evaluate all p odd of x squared。😡。

Where x ranges over all of those n sample values。😡，So if x is a set of integers， one，2，3，4，5。

 then x squared is a set of integers， 1，4，9，16，25。It's not degree n over 2 at n over2 sample values。

 it's degree n over2 at n sample values。😡，Now I could split that up。

Into these n over two samples and those n over two samples。

 but then this two would turn into a4 and this forcurrence would evaluate to n squared。Makes sense。

This is the same recurrence that we use to evaluate merge sort。

So I trust that you believe the answer is in login。

Hopefully you've all seen that recurrence before yeah。A？So not all sets are collapsible， the set one。

 two， three， four is not collapsible。😡，Because the set 14，916 does not have two elements。

When I square all the entries。The total number of values I get should go down by a factor of two。

The set minus1 plus one is collapsible。😡，Because when I square both of those values， I get one。

So just to give an example。So the set containing the integer  one。

 that's collapsible because there's only one entry。

 the set containing the number squared of 17 is also collapsd。😡，Right， here's another。

Collapsible set。Negative 11 or negative 5，5， that's collapsible because when I take the squares of all numbers in this set。

There's only one value。That I get instead of two instead instead of minus11。

 I just get one value one。So the set， if this is X。Then the set x squared is。1。

Which I just said was collapsible。So squaring the set gives me a。Half sized collapsible set。Yeah。

Yeah。Yeah。That's right， so every non trivialbual collapsible set when you square you have to be able to identify two values in the set X that have the same square。

😡，You can't have more than two values of that the same square by the fundamental theorem of algebra。

 you can't have， you know the polynomial x squared minus a has exactly two roots。

So I have to be able to take whatever my collapsible set is。

 I have to say these two things have the same square and so this is the negative of that。😡，In fact。

 this sort of gives me a recipe for constructing collapsible sets by taking square roots。😡，Hey。

So I start with the set one， and then by taking square roots， I get minus one1。

And then by taking square roots， what do I get？I minus I minus1，1。And then by taking square roots。

 I get。Squared2 over2， well， plus minus this plus minus squared of 2 over 2 I and also I minus I。

Minus one and one。And so on。So what I end up with。Is well， in general。

 not necessarily and I end up with complex fruits of unity。嗯。Now。

Some of you just got very uncomfortable。And。There are two reasons why some of the different subsets of you got uncomfortable。

 some people got uncomfortable because suddenly I'm using imaginary numbers。😡。

Complex numbers are just pairs of real numbers that you do funny things to when you you implement you overload the arithmetic operations by doing something more complicated。

 that's all they are。😡，It's not nothing to be scared of in terms of the implementation。

There's another reason to feel uncomfortable， though。Square to two。Ohh。Floating point。嗯。

I'm not going to say too much about this。😡，But basically。If you're doing signal processing。

 it's actually really okay to do floating point arithmetic when you're doing the FFT calculations。

Because theres noise in the signal anyway and wave your hands。Um。

 it's not going to matter in the end， it's not it's going to。Change the noise。

 but it's not going to like destroy the calculations completely。

If you really want to do discrete Fourayier transforms。

 if you really want to evaluate or manipulate polynomials with say integer coefficients。

 you don't do this with complex numbers， you do this with modular arithmetic。😡，But I。

The idea is exactly the same， I pick some large prime number。😡。

And I talk about square roots mod that prime number。😡，or square is mod that prime number and again。

 you get this effect that when you take square roots。

 you have two possible values and so really these roots of unity are roots of unity mod my favorite prime。

But。Discussing this in detail， kind of。哦。The details are a little bit hairy。

If you look in Wikipedia under something called the number theoretic transform， that's what this is。

 this is the Fast Fourier transform modo a large prime。😡。

That gets rid of all the floating point calculations。For purposes of this class。

We'll just imagine that we can do this exactly。And because in practice。

 we can do something similar exactly or and or in practice， we can do floating point。

 and it'll be fine。I realized that's a bit yeahh。But let's go with it。Thanks。嗯。😊，So。

These are the the the the。Roots of unity， so general the primitive and fruit of unity。😡。

Is cosine of2 pi over n plus i times sine of2 pi over n？In the complex plane。

 the roots of unity are evenly spaced around a circle of radius one centered at the origin。

 it always includes one if and as even it always includes two。Sorry， it always includes negative one。

 then is a multiple4， it always includes i and minus I。So omega， this is omega 8。

So's primitive8 root of unity， if I square omega 8。I square the amplitude which was one。

 so I get one and I double the argument， the angle， so I just go to the next point。

So this is omega 8， omega 8 squared， omega 8 cubed， and so on all the way around。嗯。So。

I'm going to use these as my sample values， because the set of。

Roots of unity provided the number of roots of unity I choose as a power of two has this collapsible property。

😡，And that means that I can evaluate at those evenly space points on the circle using a divide and conquer strategy。

😡，That divide and conquer strategy is called the Fast Fourier transform。😡。

The values that you get are called the discrete Fourier transform。😡，So the DftT。

 the discrete Fourier transform of a polynomial P， is defined。😡，By saying the J sample value。Is。

The value of my polynomial。Evaluated at the J。En through divudity。

J steps around the circle with unevenly space points。And you。

 I can write that again in the usual for loop syntax。Oh。嗯。

Where again I'm taking powers of this thing， this just means I'm taking， you know。

Omega to the JK means I take J steps and then J more steps and then J more steps a total of k times。

😡，Or K steps， K steps a total of J times， it means I'm JK mod n steps around the circle。

So the things that show up here。Are always roots of unity。

 they're always some point somewhere useful on the circle。And it's really the periodic。

Nature of these roots of unity that make things work。Again。

4H transforms if you're a physicist or an engineer。Or about transforming frequencies， you know。

 periodic signals like my finger。Into evaluating their frequency spectrum。哎有。So at least intuitively。

 it kind of makes sense。嗯。So if I want to actually implement this。😡，I've got all the pieces。

Just write it down。Okay this looks more complicated than it is。

 but because we have to write down all the details。

 but it's really not so bad so let me just walk through it。😡，I want to compute。

The discrete Fourier transform of a polynomial of degree N represented by this coefficient vector P。

If the degree of the polynomial is zero， that means there's only one coefficient。😡。

I just returned that coefficient。嗯。Otherwise。I copy here the even coefficients into an array P and the odd coefficients into an array Q。

And now what happens when I square the in fruits of unity？Is。Well。

 I'm actually that's the same thing as picking out every other point around this circle。

 this is this collapsing property。So everything is ready to set up。

 I want to evaluate this even polynomial U at all of the n over two roots of unity。

 I want to evaluate the polynomial V at all of the n over twoth roots of unity。

 those give me the discrete Fourier transforms of U and V， which I'll call U star and V star。😡。

Now I've got sample representations。😡，Of U star and V star， which I need to somehow combine。

And so here I'm just， I'm evaluating the original polynomial by taking， you know。

The polynomial value equals the even polynomial value at x squared plus x times the odd polynomial value at x squared。

😡，嗯。So。This is a recursive call that takes T event over two time。

This is a recursive call that takes T event over two time。Everything else。Takes order end time。

And at the end。I get。The discrete Fourier transform of the polynomial I want I started with。

All right。The first five times I saw this。😡，At this point of reading through it。My brain had a big。

Thought bubble over it。With four characters in it， WTF question mark。嗯。

So I'm throwinging a lot out here， there's some linear algebra， which is not that complicated。

 but if you haven't put linear algebra in your L1 cache。

 it's going to take some time to actually get it close to your brain。

 there's a bit of complex numbers in here， which is not that complicated。

 but if you haven't gotten complex numbers into your L1 cache。

 it's going to take some time to load it into your brain。

 I'm doing fairly fast manipulation of arrays and data structures and dividing conquer stuff。

 so if you don't really believe in the recursion ferry。

 it's going to take some time to get that into your brain， so the thing that I would。😡。

Strongly recommend doing is。Take the polynomial of degree 4。And the algorithm。

And notice that what you're computing is the value of that polynomial at one negative1 negative I。😡。

Um， and you could do it by just evaluating the polynomial by brute forest。At those four values。

Or you can do it by walking through the algorithm， splitting it into two degree。

 two polyium is with degree with two coefficients。😡，And instead of recursing。

 just evaluate those two linear polynomials directly。嗯。That'll give you I think。

 a better sense of what's actually going on。So。😡，Where does this algorithm come from？

This algorithm is universally known as the Coli Tki Radix2 Fastphoia transform。😡。

Because it was popularized in the 1950s by two defense researchers named Couly andtuki who were specifically interested in modeling。

Figuring out a way that they could detect Soviet nuclear weapons tests。From seismic data。系。嗯。This is。

 you know。An outgrowth of several years of research by other people。And in fact。

 Coy and Tuki described a more general algorithm that instead of just dividing into evens and odds when the degree is a power of 2。

 as long as the degree is composite， the degree of the polynomial is say you know I really should have used the letter P there。

 but let's say the degree of the polynomial is s times t。

 then fact I can reduce to computing some degree P。😡。

Forier transforms in some degree Q Fourier transforms and combining them the right way。嗯。But in fact。

嗯。This entire algorithm。😡，In full recursive generality。Was first， as far as we know first。

 developed by Calfred Gaus。In the 1800s。Gaus was trying to predict the orbits of asteroids。😡。

So given sample values of the position of the asteroid， people had been。

 you know doing observations of the sky for at that point a few hundred years and so there was lots of data。

And so he wanted to reconstruct the orbit of the asteroids from those sample values。

And so he developed。😡，What's now known as the FFT。Of course。

 he described it in Latin and he never published it。😡。

Because he only believed in publishing things if they were really， really done。

Few but ripe as he put it。U。And after developing the FFT and saying， yeah。

 it takes a little bit to get used to， but the more you play with it， the easier it gets。嗯。

He eventually abandoned it。And the reason he abandoned it is essentially。

 he discovered that 16th century observations of asteroids are noisy。

And the FFT doesn't give you good results when there's significant noise in the sample values。

It kind of skews off pretty quickly。 So instead， Gaus said， well。

 I know from Kepler's laws that these orbits ought to be ellipses。

 So what I should find instead is the ellipse that best fits the observations。And so he threw out。

His invention of Fastphoria transforms and instead invented Lee squares。

Which is the reason why and you know evaluating least squares。

 that's the reason why we call the process that we normally use solve systems of linear equations。

 Gaussian elimination， because Gauss used it to do least squares。

And that's also why we often refer to normal distributions as Gaussian distributions。

 because that was in Gausse's explanation of why Lee squares works。Assuming Gaussian error。

 you actually get the most likely ellipse at the end if you're fitting an ellipse。

Even though neither Gaussian elimination nor Gaussian distributions were discovered first by Gauss。😡。

So it all washed out in the end。Gas got credit for something he didn't do and he didn't get credit for something he did。

😡，Hey。嗯。I find the latter quite a bit more satisfying than the farm because Gauss had a habit。

He did this with the development of hyperbolic geometry， which also happened in the late 1800s。

 Yaish Boi， who's one of the people who discovered hyperbolic geometry， wrote to Gaus all excited。

 look at this thing that I did and Gaus said， yeah。

 that's pretty much what I figured out 20 years ago。I wish I could say it was good。

 but that would be praising myself。But you asshole， you know， no。So gas was kind of a jerk。但。

Which is why so many things are named after him。She。All right。So。Here's your algorithm。

That runs in N log in time。like I said， this algorithm assumes that the degree of the polynomial is a power of two。

 there's a more general algorithm that works。😡，At least produces the smaller degrees when the degree is any composite number and there's yet another algorithm which gas didn't invent which works when the degree the polynomial is prime but if you just want to use this one you could just pad the coefficients with zeros up until you get a polynomial of degree it's a power of two。

 that's the simplest thing so you get n log in time。Yeah。U。So let's back up。Now。

To what we want to do with polynomials so we know。We can go this way。

In N log N time using the fast Fourier transform。Given the coefficient vector。

 we can produce a vector of sample values at a very carefully chosen set of sample positions。😡。

Using this divide and conquer strategy and analog in time。Well。

 that's great if I want to multiply two polynomials given by a arrays of coefficients。

 I convert each one。😡，can then log n time two set of sample values。

I multiply those two sample values。By lining them up and multiply sample value by sample value in the near time。

Only now I need to convert those sample values back。So I need to undo。The FftT。So。Remember you the。

The way we do evaluations。😡，To convert from coefficients to sample values is we say， well。

 the array of sample values is equal to。This。Vanandermond matrix times the array of coefficients。

So vector of sample values。Rightい。So if I want to make this go backwards。Well。

I just need to invert the matrix。Anyone who does numerical analysis has just caught their shotgun because I uttered the phrase invert the matrix。

YouN actually want to invert a matrix。😡，But it turns out。That I don't have to invert the matrix。😡。

Because the inverse of this particular matrix looks almost exactly the same as this particular matrix。

😡，I'm not going to walk through the proof， but there is a short proof in the lecture notes。

 it's just grindy algebra。😡，Um， that the inverse of this particular vandermon matrix where I filled it in with roots of unity。

😡，Is， well， except for the scaling factor of n， the complex conjugate of the original matrix。

 meaning any place I said blah plus blip I， I should write blah minus blip I instead。😡。

Or equivalently。I should reverse the order of the rose。So inverting the FFT。😡，Is again。

 except for that factor of n at the end。Morally identical to computing the AFT to begin with。😡。

In fact， if I apply the FftT twice， what I'm going to get is the coefficient vector in reverse order。

😡，Except off by factor event。Okay， so that means that， well， here here's the inverse FftT。

 the only changes that I made。😡，From the original FFT algorithm are this minus used to be a plus。

 and I put in this extra divide by two to adjust for that scaling factor。

Or I could just compute the FFT and do the adjustment。😡。

So converting back from samples to coefficients。😡，Is basically exactly the same process as converting from coefficients to。

Simple values。It's what mathematicians like to refer to as an invol。

 it's an operation where if you apply it twice， you end up back where you started。Again。

 the mathematical details， nobody likes to watch people do algebra so I'm not going to put you through that。

 but it really is just elementary algebra。😡，And so that means finally。

 if I want to multiply two polynomials， once I've implemented the FFT and its's inverse。I take。

My two polynomials P and Q say P has degree M， Q has degree N。😡。

I need to pad those coefficient vectors out。😡，With zeros to be big enough。

That I have enough sample values to represent the product。

I compute the discrete Fourier transform of P， I compute the discrete Fourier transform of Q。

 now I have sample representations for P and Q。😡，I multiplied the sample values at corresponding places to get a sample representation of the product R。

 and then to get back to。😡，The coefficient representation， I invert the FFT。So。

Everything is linear except。This step， this step and this step。Each take order N log N time。

Everything else is just simple four loops that take linear time。And so this is how you multiply。😡。

Two polynomials in analog loggen time。Yes。Yeah。Thanks。可以。Yeah。

And here I'm really exploiting the fact that n is a power of two and just at every level of recursion。

 I take care of one power of two instead of doing them all at the end。嗯。Okay。嗯。Questions。

So we're still thinking about how to you know what kinds of problems to put into the homework。

 but one thing that I want to sort of keep in mind。This is more generally。

This operation of multiplying two polynomials。😡，If you think about this as an operation on。

Sequences or vectors is usually called convolution。So if I take one sequence a。A0。

 a1 up through a let's say m minus1。And I have another sequence B。Just B0， B1 up through Bn minus1。

Then the convolution， which is normally written with a star， is the vector C。C0。

 C1 up through c of M plus n minus1。Where C sub K is equal to the sum over all coefficients I plus J the I and J the sum decay of AI。

Bj。So when you're multiplying two polynomials， when I want to compute。😡。

The coefficient of say the k power， the k term in the output。

 what I'm going to do is put my left index finger on a0， my right index finger on B sub k。

 multiply add to my move the fingers in， multiply， add to my accumulator， move the fingers in。

 multiply add， so I consider every pair AI， BJ where I plus J equals k。😡。

And multiply them together again， this is this is ignoring the carries。

 this is exactly the process that you learned to multiply large integers。

But this idea of doing convolutions of vectors has other。😡，啊。

Applications besides multiplication to polynomials。

If I implement convolution directly from the definition as for each。😡，Subscript K， I run a for loop。

That's going to take n squared time。But if I use fast Fourier transforms。

 I can compute the convolution of two vectors of Linked n in analog log N time。😡，嗯。

Which is useful for。Build the algorithms。嗯。This is pretty much one I wanted to say。

I'm happy to take questions。😡，But I do recognize that。Some of those questions might be better asked。

Online later， after you've had a little bit more time to absorb and think about things。But as I said。

 I've got five more minutes， I'm happy to answer any questions you have now。Yes。

 let's say I want to calculate X4 to the eighth power exactly how is ambassador within your I want to compute what I want to compute let's say I want to fill in the matrix that I'm an X4 to the eighth powerbasor。

You've given me one value so I can any any any algorithm that takes in a constant amount of data runs in constant time。

 so I don't know what you're asking。Calculating entire matrix like log no。

 I'm not calculating the entire matrix ever， I'm calculating the product of that matrix with a vector。

I'm not calculating the matrix。😡，We're just of getting the Y values out yes。

 I put the a values in as input， I do some algorithmic magic， I get the y values out as output。

I never write down the matrix。对不对对。All right。I'm going to turn the recording off。

 please come up if you have other questions。

![](img/d4154c8dd909c771c06a8a259ac2962a_2.png)

Thank you。So its multiifying of large integers just like。



![](img/d4154c8dd909c771c06a8a259ac2962a_4.png)