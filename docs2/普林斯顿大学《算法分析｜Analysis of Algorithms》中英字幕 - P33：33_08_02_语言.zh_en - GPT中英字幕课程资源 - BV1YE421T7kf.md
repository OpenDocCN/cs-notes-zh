# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P33：33_08_02_语言.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/8757e9fc2a5ae8537a2b67289cb4e3b7_0.png)

So now we're going to just briefly take a look at the relationship between the symbolic method and formal languages from computer science。

So probably for people that have studied formal languages， these kinds of questions have occurred。

So a formal language is a set of strings， and natural question is。

 how many strings of length n are there in a given language？Well。

 then the answer is that we can use an OGF to enumerate them and we can essentially use the symbolic method or view the symbolic method as an approach to solving this problem it's a very systematic way to solve problems like this now there's an issue when it comes to counting that has to do with ambiguity typically in a formal language we're just concerned about specifying the set and it could be that there's more than one way to derive a particular string and that's a key issue in understanding formal languages and building compilers and other things like that。

So if there's more than one way to derive a string。

 we're going to count really all the ways to derive the string。

 so we want to work with unambiguous languages now without getting into detail of the study of ambiguity and formal languages。

 I'm just going to give some examples。So let's look at regular expressions。

 so a regular expression uses the concatenation or the or the star operation to specify a formal language and if you're not familiar with regular expressions。

 go read up on them and then come back to this。And the theorem。

 which is really the same as what we did for the symbolic method。

 but just with different notation is if you've got enumerating OGFs for two REEs and you take the or。

 then the OGF is the sum， if you take the concatenation。

 the OGSs the product and if you take a star it's1 over1 minus and it's really the same proof as the symbolic method with different notation as long as the REs are unambiguous。

So one thing that this says is that the OGF for an unambiguous REE is rational because all you get out of here it a ratio of two polynomials no matter how you apply these operations。

 you're going to get the ratio of two polynomials for the OGF。So just to kind of highlight the point。

 another way to say this is that OGFs that enumerate regular languages are rational。

So that is a language， regular language。there exists in or it doesn't necessarily have to be unambiguous but there is a construction。

 a well knownn construction that gives an unambiguous regular expression for any regular language。

 one way to define a regular language is that there exists a finite state automaton for the language。

And then Cly theorem is if you look at the details of Ci theorem。

 it takes a finite state machine and gives a regular expression that is unambiguous。

 and then if there's an unambiguous RE， then it's rational so that's just a quick look at the landscape with regular expressions。

And it's a kind of fun way to think about enumeration problems because people maybe are more used to regular expressions。

 but there is the issue of ambiguity so like we did binary strings with no zeros。

 this is that derivation in regular expression language。

 so that's an RE for binary strings with no000。An unambiguous one。

 and then just applying the theorem， it's going to be for the stars。

 one over one minus and for the tail part， it's just that it's pretty much the same。

Ratio of two polynomials that we had in the case when we did it using a symbolic method。

 we get the same result， of course。And again， expand it in the same way。

Here's another example what about binary strings that represent multiples of three。

 this is a famous example of say a finite state machine with three states you can derive a finite state machine for this or you can get this regular expression and again that's about regular expressions to believe that this is multiples of three。

 but that's the one this is3，6，9， 12， 15 and so forth。

So how many binary strings represent multiples of three well we can just apply the theorem to that regular expression and we get this rational function that after a while we can simplify down to that simple ratio to polynomials and this one actually expands explicitly with partial fractions it's going to be asymptootic to two to the n minus1 over three。

And that's what you'd expect， you always have a one bit and then you get two to the n minus one possibilities and a third of them are going to be multiple to three。

 approximately there's a minus1 to the end and make it come out exactly。

But this is a fine example of enumerating regular languages。

 so it's just the symbolic method in different notation。

So similarly for context free languages where we have non terminalmins and we use or concatenation。

 again， the same idea works as for the symbolic method。

 the key is to make sure that it's unambiguous。And now it's a more complicated situation because we have multiple equations and there's a discussion in the text about the idea that OGFs that enumerate context free grammars are algebraic。

So in algebraic functions of function satisfies the polynomial equations。

 coefficients or polynomials with rational coefficients。And again。

 it's just a natural follow on from just the basic rules that we're using to develop these generating functions。

Now， actually the constructions that we've considered are all unambiguous context free grammars just using different notation。

So that's binary trees， but this is binary trees as a contextfr grammar。

 and so then the OGF is going to satisfy it's an algebraic function because it's a solution to an equation like that。

Yeah。It can be recursive so this is for bit strings and it's a little more complicated to represent it as a CFG。

 but not that big a story， really it's just different notation and bit strings in those00 and so forth。

So now because of ambiguity， not all context free grammars correspond to combinatorial classes that we can enumerate in this way and not all constructions that we consider in the sic method are context free grammars because there's other operations that we use besides just。

Concatenation and ore there's many， many other operations that we use that make the commonat classes that we're talking about different from context free grammars typically。

 but still there's lots of cases where it's the same thing in those cases know it's worthwhile to be aware of that so this is just an example for the study of random walks so a walk is a sequence of plus and minus characters and there's lots of applications random walks and so-called gamblerss ruin problems and also the study of some sorting algorithms these are discussed in the text。

So and just from the idea of a sequence of plus and minus characters。

 there's all kinds of natural questions that arise like how many different walks of lengthIn are there。

 or how many different walks of LiIn are there where every pretext has more pluses than minuses。

 that is it stays above the line because you're're going plus more than you go minus always。

 and similar questions like that are studied in all different types of applications it's a relatively general framework。

And so the key to studying random walks in this context is to come up with an unambiguous way to decompose them。

 so that's a typical walk and here's one way to come up with an unambiguous decomposition。

First one is to consider the class U where the walk always stays above the line。

 always got more pluses than minuses。So you can make a U by either just taking a plus。

Or by having a u and then appending another u to it and then having a minus。

So it starts at the baseline with a plus and it ends at plus one， never hits zero， that's a U。

And that's anambiiguous way to define a U， and similarly you can have a D that starts with minus ends of minus1。

 never hits zero and you get a D by putting two d's together。

And then what those are good for is that they give way to define a random walk that begins at zero and ends at zero。

 so either it's a U that takes another minus to get at zero and then you have one that begins at  zero and ends at zero or the first step is down and you have a D and then you go up and then have another S。

So this is a context free grammar just using these three constructions。

 that's an unambiguous decomposition of a random walk that starts at the origin and ends at the origin。

And that construction then。IfIt's a context free language。

 then we can use the symbolic method to get generating functions equations。

 and this times there's three equations in these three unknowns。

In solving those equations simultaneously， they're like the tree equation， actually。

 and the end result is that the number of such walks is to and choose in。

There's lots of easier ways to prove this result， but the approach generalizes to cover many similar。

 more difficult problems you can read about in the text。



![](img/8757e9fc2a5ae8537a2b67289cb4e3b7_2.png)

So that's context free languages， counting and context free languages using the symbolic method。Next。

 we'll look at tries。

![](img/8757e9fc2a5ae8537a2b67289cb4e3b7_4.png)