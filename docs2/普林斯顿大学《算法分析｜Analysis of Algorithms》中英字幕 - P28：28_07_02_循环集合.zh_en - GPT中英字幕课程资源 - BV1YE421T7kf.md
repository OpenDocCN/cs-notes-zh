# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P28：28_07_02_循环集合.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/0c953f72f3f35cac8aa9258d1eeb423a_0.png)

Okay， next we're going to extend the kind of analysis that we did when we introduced permutations in the fifth lecture and look at permutations as sets of cycles with restrictions on the cycle length。

 recall that we study this when looking at introducing analytic combinatorics with the following kind of construction and permutation as a set of cycles。

Then from the symbolic transfer theorem for labeled objects。

 that means that the generating function satisfies for set its exponential for cycle its natural log。

 so P of z equals E to the log of1 over1 minus z， which is1 over1 minus z。

 so therefore the counting sequence is n factorial coefficientency and that is which is n factorial。

And if you want to extend that to same analysis to count the number of derangements。

 that's the permutations with no singleton cycles， then we just restrict the length of the cycle to be bigger than one。

 which corresponds to leaving off the Z。In natural log of1 over1 minus z。

 So natural log1 over1 minus Z minus Z is z squared over 2 plus E could like and so forth。

Or another way look at it's just natural log of one of where my z minus Z and then。

That's e to the minus z over 1 minus z， so coefficient is z to v and that is a convolution。

 which is minus1 of the K over k factorial， which is asymptotic to 1 over E。

And then we did the generalized derangements if we restrict to no short cycles of length less than or equal to parameter n。

And it's just a straight generalization of the argument for derangements where now it's E and then we started z the m plus1 over m plus 1。

 or that's log1 minus z minus all the ones less than or equal to M。

 which is E to the minus z minus and so forth over1 minus z。

 and then we showed an analytic transfer theorem that tells us that the asymptotics of that is in factorial over E to the H of M。

So that's a review of what we talked about in terms of permutations with cycle length restrictions when introducing analytic combinatorics and now we'll look at another problem of that flavor and that's involutions an involution is a permutation where all the cycles have to be short so and there either have to be a length of one or two in an involution。

 so out of the 24 permutation。Of length  four， only 10 of them have cycles of length。

 all of length of one or two， the others have either one cycle of length 3 or one cycle of length four。

 similar only four are the permutations of size3 that don't have any three cycles and so forth。

 so a question we're going to want to take a look at it's how many involutions there are。

Involutions are actually interesting combinatorial objects with lots of applications。

 One way to see it is to think again about inverses。

 remember a permutations a mapping if we look at the permutation a mapping of the numbers one through end to itself。

 then the inverse is the inverse of that mapping， So if we think of students in rooms and sort by room and flip the roads we get the inverse what's the inverse of an involution and if you take an involution and compute the inverse by again sorting by the bottom。

Sorting the columns so that in order by the bottom row and then flipping。

 you see immediately that you get back the invol。 So what's the inverse of an evolutionvol。

 it' itself。And if you think about the cycle representation taking the mapping and the cycle representation is just moving one step in the cycle。

 So if you move one step， if you have a two cycle， you move one step and then another step you get back to where you were if you have a one cycle you just stay where you were so always with two steps you're going to get back to the same place。

 So that's why invols are significant。In the significance of so in the lattice representation。

 the one cycles correspond to elements that are on the diagonal and then the two cycles have to be symmetric。

 one goes to 9，9 goes to one， and if you transpose it you get the same thing back so an evolutionvols its own inverse and you see that from the lattice representation immediately。

In terms of applications， there's the idea of a reciprocal cipher， so if you use an involution。

 then what you can do is encrypt and decrypt with the same machine and actually a famous example of that is the Enigma machine。

 aigma machine that was used by the germs in World War I， one of its components was an involution。

So the idea is you have your our letters from A to Z and minus for blank again if the。

Permutation that we use to encrypt is an involution。 Then we don't need to compute the inverse。

 The involution is its own inverse。 So we don't need a separate。A table to decrypt。

 if we have our plain text， and then we get the cphertext， A goes to D and so forth。

 Then to decrypt we use the same。Involution or permutation。

 which is an involution and that same thing says D goes to a and K goes to T and so forth。

 so involutions permutation that its own its own inverse and again it's still susceptible to the character frequency attack。

 but it's proven useful as a component in a cipher machine because it can greatly multiply the number of possibilities that a eesdper has to consider and that's how it was used in the enigma。

 so for example， if you want to know how many enigma different enigma settings you have to find then you have to know something about enumerating invols。

And there's a very famous story about the crypt analysis of the enigma involving Alan Tring and so forth。

 if you don't know that story， it's definitely worthwhile to look it up and read about it。

So as a warmup， let's take a look at the number of permutations that are composed entirely of two cycles。

 So there's only one permutation size 2。 that's all two cycles。

 There's three different ones of size 3 that are all two cycles and so forth。

And actually an example of this is called Ro 13， so it's the world's weakest crypto system where we just take the letters and rotate them 13 positions。

 so A goes to N N goes to A， B goes to O or goes to B and so forth and you can read about this one on the web。

 it's a hacker's delight because anyone can。Encode or decode and people get so they can read in this and so forth。

 so it's a very light crypto system that hackers use to just lightly to put stuff out on the web that maybes inappropriate content。

 but you have to be at least able to decrypt in this way and nobody get offended if they ran across it accidentally。

嗯。So again， since it two cycles， it's a reciprocal cipher。

 so you just use the same table to decrypt and encryptrypt。

So how many permutations are controls entirely of two cycles， well。

 a permutation well call it R is it's just a set of two cycles。

 two cycles is e to the z squared over 2 so the equation is e to the z squared over2 and so all we want is the coefficient of n factororial times coefficient z to the n in that。

 so。That's going to be says z squared over 2， so we've got the z squared。

 so it's n over  two factorial。That's the equation。

 and we can do the asymptotics from Sterling's approximation to get the number of two cycles。

 so very simple and straightforward with basic intellect comatoatorics and asymptotics。

But what about evolutions。Well， the construction is pretty similar。

 It's a set of one cycle started with a set of two cycles。

 So they're just permutations where all the cycles are of length one or two。

So that immediately goes to E。 it's a E to the z plus z squared over 2。 So cycle 1， z， cycle 2 z。

 and then a set of those is E to the z plus z squared over 2。呃。The first one is E to Z。

 second one is E Z squared over 2。So now we want to extract the coefficients。

 so what's n factorial coefficients of Z to the n in that function。

 well that gets to be a discrete sum that is maybe not so easy to analyze。

In factorial over K factorial 2 to the K and2 K factorial。

 So it's a convolution of a term like the one that we had for just two cycles and then whatever in factorial。

 And that's easy to verify。So the asymptotics of that is。A bit more complicated。

 It's got a square root。2 fourth root of E in it and it's definitely a intricate looking function and that's available from the laplace method for sums remember the laplace method we isolate where some most weight of the sum is and then estimate with an integral there and also bound the tails and so forth and that's done in canuth volume 3 or later on in part two we'll see how to with complex asymptotics directly get that answer out。

So with analytic commonatorques， we can get directly to results like that。

Although the asymptootics of that is definitely not trivial。And then if we're going to generalize。

How about no big cycles where we parameteritize the cycle length by M same way as we did for derangements？

So now the construction is its a set of one cycles start with a set of two cycles and so forth。

 up to a set of m cycles e to the z squared plus z squared over 2 plus out to z to the M over M that's direct from the symbolic method the coefficient asymptotics of that one is one of the most difficult derivations in our analytic combinatoric book。

 but we can know the asymptototics of that through analytic combinatorics。嗯呃。As an example， now。

 for some applications， you might not need to actually work out the full asymptotics。

 And just as an example， I want to show an exercise。 So。

 so this is the generating function for the number of permutations that have no cycles of length bigger than five。

So let's say we have perrimutations of length 10。 we want to know how many of those have no cycles of length bigger than5。

 so the answer to that question is coefficient of z to the 10 in that function。

So that's a very specific question and still it's worthwhile looking at a calculation like that to get some facility for types of problems that sometimes arise。

So。If we write。The generating function in say， the other form， the alternate alternate form。

 It's log of one over one minus Z minus than the bigger terms。

So that's equivalent log of1 over1 minus z is the sum of z the K over k。

 and if we subtract off the ones bigger than6， then we get the ones less than or equal to 5。

And now with that， we can take e log1 over minus c is just 1 over 1 minus e。

 and then we have the other terms multiplied out。Now。

 the key idea here is that each one of those terms， if we use Taylor's theorem to expand them。

 we're going to need to keep the first term E to the minus Z6 over 6 is。

1 minus z6 over 6 plus z12 over over。And two factorial times 12。

 but we don't need the next term because z to the 12th and we our interested in z to the 10th。

 so anything that z to 12 multiplies by is going to be bigger than z to the 10th and we don't even need to carry that term。

 so this is exactly in equality， we just keep the ones that could possibly contribute to the coefficient of z to the 10。

So now the exponentials are gone and we have this list of polynomials。

But if you do the same thing with the 1 over1 minus z。

 then we only need to keep the first 10 terms of that one。And then for each one of these。

 you cross multiply each one of these， not really you only need to keep the one where you pick like z to the8 over8 and it multiplies by one and all the other terms。

 So that's the z to the8 over 8。 that multiplies to any one of those others。

 It's going to get something bigger than z to the 10th that can't contribute coefficient to z to the 10th。

So now we just have product of two terms and coefficient of z to the10 is easy in that because the cross multiply。

 there's one contribution from each one it's just1 minus 16， minus17 and so forth so the minus6。

16 comes from z to the 6 over6 times z to the fourth and z17 is z to the  seventh over 7 times z cubed and so forth。

 so if you look at that derivation you pretty much convince yourself you can't easily convince yourself that that's an effective way to calculate a coefficient like that for a particular problem。

As an application， we're going to consider a problem known as the 100 prisoners problem。

 this actually was a Google interview question for a while。So the idea is， you have。

 it's a story where you have 100 prisoners each that each have a unique identity card。

 So the prisoners are numbered from one to 100 and each have a card。

 Now they've been sentenced to death because they're on the wrong side of a civil war or whatever。

 but they're given a last chance， And so the last chance is that the。

Id cards are all collected in this cabinet that has 100 numbered drawers。

 cards are collected and shuffled， put in random order。

 and then they're put in the drawers one card per drawer。

So now that's the setup and now the prisoners one at a time are allowed to go into the room that has a cabinet and open a drawer。

 look at a card and en close a drawer， and they get to do that at most 50 drawers。

So each prisoner can open and can look at 50 drawers， but not all of them。

 and so then when the prisoner comes out， they have to announce whether what drawer their number is in。

 and if all of them find their own number， then they won't be executed。

 but they have to all find their own number， if any one of them doesn't， then they're all executed。

I mean one prisoner can't find the number they're all executed。

So now one of the prisoners is a mathematician， prisoner A， and he says， well， this is hopeless。

 we're all going to die because we can each only open 50 drawers in the randomly ordered。

 so that means that we each have only half a chance of one half of finding our number and there's a00 of us so the chance that we' all find our number is2 to the minus 100 and that is an exceedingly unbelievably small number we have no chance。

In fact。it won't take too long before somebody can't find their own number。

But there's another prisoner who knows some analytic combinatorics and he said。

 I think I have an idea， I know a strategy where at least we have a 30% chance of success。

So that's the Google interview question is what's the strategy， So really。

 what prisoner A was saying was that his strategy was going to be picked drawer at random。

And obviously， that's not the best strategy。So what's prisoner Bs strategy， Well， from the context。

 maybe many of you have figured it out。 So the strategy is that each prisoner should follow the cycle。

 That is each prisoner should。He knows what his number is， say he number five。

 so he should open the drawer that has number five。

 and then use that number to decide what drawer to open next and then just keep going。

Now he's going to continue until he finds the drawer that contains his own ID。

And so that's going to be the strategy。 Well， he also， has to stop if he gets to 50 drawers。

 So if you think about that， when does the strategy succeed and when does it fail， Well。

 it's going to succeed。

![](img/0c953f72f3f35cac8aa9258d1eeb423a_2.png)

If the permutation that represents the cards of the drawers has no long cycles。

 no cycles of length greater than 50。So what's the chance that a random permutation has no cycles of length greater than 50。

 well it's the coefficient of z to the 100 in E to the z plus z z over 2 plus so forth， z over 50。

And that's just a slight generalization of the little exercise that we just did to see that that coefficient is going to be1 minus 100harmonic number minus the 50th。

 which is about1 over log 2。31。That's a solution to the 100 prisoners problem in an application of a study of the cycle structure of permutations。



![](img/0c953f72f3f35cac8aa9258d1eeb423a_4.png)