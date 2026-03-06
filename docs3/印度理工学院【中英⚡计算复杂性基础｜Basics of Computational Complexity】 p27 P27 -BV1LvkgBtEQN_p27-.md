# 印度理工学院【中英⚡计算复杂性基础｜Basics of Computational Complexity】 p27 P27 -BV1LvkgBtEQN_p27-

![](img/6bd037e029df9363df8834cb828983a4_0.png)

So， last time we。Started defining complexity classes。To capture counting。

RightSo the primary counting problem is sharp set。Which is a functional problem。

 So it takes a boolean formula and it outputs how many satisfying assignments there are of this Boolean formula filehi。

嗯。And to capture efficiency in functional efficient functional problems。We define the class Fp。

Which is。Collection of functions， F。That are computable by poly time Ting machines。

And the open question is， subsetet is not in。Efficient，ly solvable functions。

So this class defines its own this problem defines its own complexity class sharp P。So， that is。

Those functions。Which have a turing machine， Who's。Kind of number of accepting parts they count。Okay。

 so if you think of M X comma Y as a N DTM。And why is as an accepting path？

So how many accepting parts are there number of wises that is the。That is what F of X computes。

So this sharp set is in Shaie， and it is supposed to be a hard problem。

 So Shar P is supposed to be a。Class， harder than that。Har than N。It clearly contains F P， and。

Given that， you can solve Np and you can solve its itself in P space。In the same space。

 you can do counting。So， let us now move to。A new class that comes out of Shaie。So， Shaie has。

And analogs。Decision version。Which is B P。So language L in P， P。

Language L will be put in the class P P if。There exists a poly time。Duringing machine M。

And constant C。Such that。For all x， for all input x。X is in L。

If and only leave the number of accepting parts。Such that。M X y is one。So P stands for probabilistic。

Polynomial time and what。Will happen here is the number of accepting parts will be more than half or at least half。

Okay to amongst the bats。At least half of them are accepting when that happens， then we say。

Then x is a yes string。 Okay， if you only leave。So such problems， which are solvable by this。

You can think of it as a。For now， as a probabilistic tuuring machine。With probability。

 half it accepts。And less than half it rejects。So， there is a。

Mincule advantage that it is giving to the yes string。Which is half。Su。Fun in P， P。Computs。

The most significant。The most significant bit of the corresponding function。In short peak。Okay。

 that's the first observation。We can make that。A boolean function， Boolean function in P P。

Let me add bulloleing here。 That's important。So Boolean function， for example， is land language L。

This is in P， so it means that you are able to compute the most significant bit。Right。

 so basically if you see in binary the number of accepting parts。

 then the most significant bit is one if。Half of the parts are accepting。 otherwise， it is 0。

And that is what。Deines P P。So we will now prove some interesting facts。

That actually P and Shap are in a way equivalent。So， what will show is。Shop set。

Sharp set can be solved using P。As in orracle。Okay， so if you can compute the most significant bit。

 then using that as a subroutine。You can actually compute。The whole string giving you the count of。

Accepting parts。 Okay that's that's an interesting consequence。And hence， it would imply that。

If you can compute Shar P， then using that oracle。Like shops at Oracle， you can solve P P。Okay。

 so to a polymer time machine， sharp oracle is equivalent to PP oracle。

G when that send P P and shop here。Kind of equivalent。Okay。

 there is a kind of equivalence in computing the most significant bit and the。

Wold string of the count。So the key thing is to show the first property， which is how do you compute。

The number of satisfying assignments， if you know that the assignments are。

Satisfying assignments are at least half。So let five year boolean formula given in the input。

In variables， x1 to x。So， using P P。We know。If the number of satisfying assignments of five。Okay。

 this notation will mean number of satisfying assignments。Is greater than equal to。2 is twin -1。

Or not。Okay， so we well be basically able to compute the MSB of number of satisfying assignments。嗯。

So since its in n variables， half is2 2 n minus-1。But then from this， how do we actually compute。

This。Shar will fight。This is just one bit。 How do we compute the other bits。

Somehow we have to fill this difference， right this unknown， unknown difference。

Between two race 2 and -1 and sharp5。So for that， let us define the difference as。So， the idea is。嗯。

To find。The minimum。Non negative integer key。Such that。K plus。😔。

Key plus number of satisfying assignments。Is tourist twin。At least two2， right。

 so greater than equal to。 But since we are saying minimum K， its actually an equality。Using。

Binary search。And。😔，N plus one。Non deterministic bits。Okay， so well compute the difference。

Using binary search and many non deterministic bits。So， with that。What we would have shown is。That。

Yeah using P P。We have solved shop set。In deterministic polynomial time。K B machine has to be F P。So。

 consider N DTM。M。That on input。Fi。😔，And keyi。😔，Uses。Non deterministic bits。5，0，2。Weaiin。As follows。

So on y 0 equal to 1。M guesses。Wai。These n bits it makes this guess and outputs。5i Webar。

So basically on it is just guessing a satisfying assignment right。

 it will be one output will be one if I only leave。A satisfying assignment was guest。Otherwise。

So this is kind of point number one or step  one is， is the part of。Haashfei。Right。

 you can think of this as step 1。And the step 2 will be corresponding to k。

And that so that the sum comes out to be。To days twin。So on y 0 equal to 0。M accepts。Exactly。

 case strings。Vbar。That's the key part。Right， so y 0 equal1 is covering。

Hash file and y 0 equal to 0 is covering k。And。The total number of accepting parts。Is， by definition。

Tourist twin。So let's write that down。So number of accepting parts。Number of accepting parts。Of M。

5 k is。K plus。😔，This， this is by definition the way it is accepting， right。While the possible parts。

This is exactly。呃。All possible values of y 0 to y n， which is2 is 2 n plus  one。Right， so。

 so we have basically made two race to n half of two race to n plus one。Okay。

 in this by this orange definition。We have an N DTM where。

If the number of accepting parts is half or more。That will be enough to。Compute key。So。

But you have to start with a k。 So basically the idea is that you guess k and then verify it by using PP record。

Okay， to do a binary search。And by that。In around any traditions。

You will be able to find the right value of k。So K plus the number of assignments。

 satisfying assignments greater than equal to two is to n。This。Can be learn。Bike wedding。비비오라클。

On Fike。Okay， so you can start with key。Let's say， one。Check this by P Pacle。If this is false。

 then it means that you should increase k so double k which is 2。If this also fails， then you go to。

4 k equal to 4， and so on。So。So， find came in。So starting with。K to be 1 then 2， then4， then 8。And。

 ultimately。Key maximum can be tourist to end。Try all these en one possibilities。 So find came in。

From M， SP to LB。Bbitit by bit。Eat using。Or query to P Pacle。So， in N  one calls。In at most。

 n plus  one。Calls to reckon。Vfind。We find Camen。And so it means that we have computed。

The number of satisfying assignments。Right， so。Once we find came in。

 then the difference gives us the number of satisfying assignments。 So that is。

 this is just an F P computation， right with n plus one。Orracle calls to a P P problem like。Oh。😔。

The hardest problem in P， P。So if you can solve P， P， then you can solve。Shop set。Thus。Shopet。

Is in F， P to the P， P。So that's a nice。Reduction from shops of P， P to。Of shop set to P P。

And the second proposition。Is now immediate。Okay， so how do you do that。Did solve that。So。

 we have already shown。That。P is to shop set。Is contained in。P is to P， P。

if you can solve PP then making those calls， you can solve Shaet and so any problem。That is。

Calling shopet as an oracle。Those calls can be replaced by。

PP or calls so P is to shopet is in P to P。And。But you wanted to show an equality。In fact。

The same proof shows。That for any problem in Shaee。P is2 L is in P 2 P P。Well。

 this is because we didn't really use Shopacks specific properties。Right。

 you can do the same thing with the。Any problem in Shaie， so。For any Shaie problem， L。

 P S2 L is in P S2 P P。And what does this mean this actually implies。That P is 2。Sobi。😔，Ist P is2 P。

 P。Every call can be replaced by a PP P U recall call。So， we have shown both ways。While P is to P。

Is trivially in Paris to shop。Keep Py Pas and so Shaie because well， if you have Shaie access。

Do you have access to all the bits of the count。 So you obviously can also compute the most significant bit。

So that is trivial， which means that。Peier is to pe Ps Pi to shoppe。Okay， so that finishes。

This equivalence。 So again， we started with functional。Complexity class Shaie。

 we ended up showing that。It's actually equivalent to a decision。To a normal complexity class。

 which is P， P。And now we will investigate Shaie further。Okay。

 sharp P actually has complete problems， so let's investigate them。So。Call function。If。😔。

Shop be complete。If。😔，First of all， it should be in。Shpe itself。And。

Every problem in Shaie or reduce to this function， so。Sopi。😔，Is should be in。F， P given F。Okay。

 so this is a nice way to say that every problem in Shaie reduces 2 f。Basically。

 Shaie should be a subset of。Functional， efficiently solvable。

Functional problems using F S an oracle。So， this is called。Shoppie heartt。

So what this is saying is that f is sharppy hard， if it is also in P sharppy then it becomes sharppy complete。

This thing， by the way， is also called tuing reduction。So this is also the notion of。

Duringing reduction。Okay， in contrast to the car production we saw。So here， actually。

 subroutine calls are being made。 So whatever you can solve by。Calling F as a subroutine。

 so there will be many calls， possibly polymly many calls。Oh。So if using this。

 if you can solve a problem G， then you call it。A curing reduction from G to F。Suppose G is here。

Then notion of tu reduction。Of G2 F。Okay， this is the。This is more。

 this is much more powerful than car production。Now， from this。Deduction。

Or or the completeness notion， Shapy completeness。What you can see trivial is。

If a Shaie complete problem is an F P。So， F is。Short be complete。And F is an F P。D。F P。Xiaobi。😔。

Because。If you can already solve F in functional polynomial time， then。

Funal poly time calling functional polyial time as an oracle。Is still functional polynomial time。

 Okay， just because of that， Sha P will be inside F P。 That's the simple proof。

And what is a Shaie complete problem？Is there a natural problem that is sharppy complete？

So we have been looking at shop set and that happens to be。Shall be complete。

Follow from Cooklevin directly。She shop sacked。Is Shaie complete。So， we know。That shop at。

Isn't Shaie。And now we have to show that it is also sharpy， hard。

Every problem in Shaie should reduce to this。In the above sense， right， during， during sense。A late。

力iz。Bin shaoppe。With corresponding。So G is computing number of accepting parts of N DTM。And。So。

 since。Es computation。Can be converted to a boolean formula。

Okay M's computation can be converted to a boolean formula by cooklevin。

So what it means is that for all input text。This G of X。Is equal to。Number of。Accepting parts。

Of M1 x。Which is also equal to。嗯。So let me call the Boolean formula of fire。

Which is also included to the number of satisfying assignments。Right， which implies that G。

Is in F P to D shop set。Think of cook le reduction as a。A efficientffic to function。Which it is。

It was just quadratic blow and then you can make a shop set call。Right。

 and once you have the shop set call， you will know。The value geofi。So this。

 you know since G was anything in Shaie， it means that。Sharie as a whole is。F P to the shop set。

And now。So， that's a hardness。It shops at a sharpy hard， and hence， it is complete。Yeah。

 so that gives a pretty good understanding of Shaie we have。A complete problem of Shape。

 We have a Boolean version of Shape。And what we'll do next is something even more brilliant。

Which is an algebraic formulation of Shaie。Okay。🎼。

![](img/6bd037e029df9363df8834cb828983a4_2.png)