# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P147：19_02_06_P与NP问题.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

So I hope that pretty much all of you had heard about the P versus NP question before you enrolled in this class。

 but if you haven't， you can pretty much guess what that question is。



![](img/79c6537d192647f2d87ae57f0e57fb3a_1.png)

I've defined for you both of these classes of problems。

 P is the class of problems that are polynomial time solvable。

Whereas the problems in NP have the property that at least given a solution。

 you can quickly verify that it is indeed a correct solution。

It's widely conjecture that P is not equal to NP。 That is merely the ability to efficiently verify purported solutions is not sufficient to guarantee polynomial time solvability。

 Indeed， Edmonds back in 1965 before we even had the vocabulary NP P。

 Remember that came along only in 71。 Edmonds already in 65 was essentially conjecture that P is not equal to NP P。

 In the form that he was conjecture and there's no polynomial time algorithm that solved the traveling salesman problem。

But let me emphasize， we genuinely do not know the answer to this question。

 There is no proof of this conjecture。P versus MP question is arguably the open question in computer science。

 It's also certainly one of the most important and deepest open questions in all of mathematics。

 For example， in 2000， the Clay Mathematics Institute published a list of seven millennium prize problems。

 The P versus MP question is one of those seven problems。

 All of these problems are extremely difficult and extremely important。

 The only one that's been solved to date is the Poquere Conjecture。

 The Rimon Hypothesis is another example on that list。

And they're not called the Millennium Prize problems for nothing。

 If if you solve one of these mathematical problems， you get a cash prize of $1 million。Now。

 while a million dollars is obviously nothing to sneeze at。

 I think it sort of understates the importance of a mathematical question like P versus NPp。

 and the advance in our knowledge that a solution to the question would provide。

 I think would be much more significant than a price check。

So how come so many people think that P is not equal to NP rather than the opposite p equals NP？Well。

 I think the dominant reason is sort of a psychological reason。

 Naly that if it were the case that P is equal to N， then all you'd have to do。 Remember。

 is exhibit a polynomial time algorithm for just one N P complete problem。

 And there are tons of N complete problems。 And a lot of extremely smart people have had N complete problems that they've really cared about。

 And either on purpose or accidentally， They've been trying to develop efficient algorithms for them。

 No one has ever succeeded in over a half century of serious computational work。

The second reason is sort of philosophical P equals NP just doesn't seem to jive with the way the world works Think about for example when you do a homework problem in a class like this one and consider two different tasks the first task is I give you a question and I ask you to come up with a correct solution。

 say a proof of some mathematical statement。The second task would be just grade somebody else's suggested proof。

 Well， generally， it seems a lot harder to actually come up with a correct argument from scratch compared to just verifying a correct solution provided by somebody else。

 And yet， peak was NP would be saying that these two tasks have exactly the same complexity。

 It's just as easy to solve homeworkr problems as it is to just read and verify the correct solutions。

So I don't know about you， but it's always seemed to me to be a lot harder to come up with a mathematical argument from scratch as opposed to simply bradiding somebody else's solution。

 Somehow it seems to require a degree of creativity to pluck out from this exponentially big space of proofs。

 a correct one for the statement at hand。 Yet peak was NP would suggest that that creativity could be efficiently automated。

But of course， you know P versus NP being a mathematical question。

 we'd really like some mathematical evidence of which way it goes， for example。

 the P is not equal to NP。And here we really know shockingly little。

 There just isn't that much concrete evidence at this point that， for example， P is not equal to N P。

Now， maybe it seems bizarre to you that we're struggling to prove that P is not equal to N P。

 Maybe it just seems sort of obvious that there's no way that you can always construct proofs in time polynomial in what you need to verify proofs。

 But the reason this is so hard to prove mathematically is because of the insane richness of the space of polynomial time algorithms。

 And indeed， it's this richness that we've been exploiting all along in these design and analysis of algorithms classes。

 Think， for example， about matrix multiplication。 Had I not shown you Strasens's algorithm。

 I probably could have convinced you more or less， that there was no way to solve matrix multiplication faster than cubic time。

 you just look at the definition of the problem。 It seems like you have to do cubic work。 Yet。

 Strasin's algorithm and other follow up show you can do fundamentally better than the naive cubic running time algorithm for matrix multiplication。

So there really are some quite counterintuitive and hard to discover unusually efficient algorithms within the landscape of polynomial time solutions。

 And who's to say that there aren't some more exotic species in this landscape of polynomial time solvability that have yet to be discovered。

 which can make inroads even on and becomple problems at this point， we really don't know。

At the very least， our currently primitive understanding of the fauna within the complexity class P is an intimidating obstruction to a proof that P is not equal to NPP。

I should also mention that as an interesting counterpoint to Edmundd's conjecture in 65 was a conjecture by Grdel。

 This is the same logician Kirkrdle of Grdle's completeness and incompleteness theorems。

 He wrote a letter to John Von Neuumman in 1956， where he actually conjectured the opposite that P is equal to N P。

 So who knows。So I've tried to highlight for you the most important things that an algorithm designer and serious programmer should know about NP problems and NP completeness one thing I haven't explained。

 which you might be wondering about is what on earth does NP stand for anyways？

A common guess would be not polynomial。But this is not what it stands for。

The answer is going to be a little bit more obscure， and indeed it's a bit of an anachronism。

 non deterministic polynomial。So this is referring to a different but mathematically equivalent way to define the complexity class NP in terms of an abstract machine model known as nondeterministic Tring machines。

 but generally for someone who's thinking about algorithms is generally for the programmer。

 I would advise against thinking about problems in NP in terms of this original definition with this abstract machine model。

 and it's dead strongly encourage you to think about the definition I gave you in terms of the efficient recognition。

 the efficient verification of purported solutions， Again。

 their mathematically equivalent and I think efficient verification makes more sense to the algorithm designer。

Maybe you're thinking that NP is a perhaps not that good and somewhat inscrutable definition for what's a super important concept。

 but it's not for lack of discussion and effort on the community's part。

 So very soon after the work of cook and carp， it was clear to everybody working in the West on algorithms and computation that this was a super important concept and people needed to straighten out the vocabulary。

 AAP。

![](img/79c6537d192647f2d87ae57f0e57fb3a_3.png)

Don Cannuth ran a poll amongst members of the community。

 He reported on the results in his Sigac news article from 1974， a terminological proposal。

 and emptycompleness was the winner， and that was then adopted in the landmark book。

 design and analysis of algorithms by Aho hopcroft and Oman。 And that's the way it's been ever since。

 There is one suggestion that was passed over， which I find quite amusing。 Let me tell you about。

The suggestion was petT PE E T。 So what is PE acronym for， Well， it's flexible。

 So initially the interpretation would be possibly exponential time problem。Now。

 suppose that someday people prove that p is not equal to NP。

 then the meaning would change to provably exponential time。

So now is not the time to nitpick with the suggestion that you could prove P not equal to NP without actually proving an exponential lower bound。

 merely a super polynomial bound， let's leave objections like that aside and ask what would happen if P actually turned out to be equal to NP Well then you could call PET previously exponential time problems。

But of course， at this point， PE is nothing more than an amusing historical footnote。

 NP Compte is the phrase that you got to know。