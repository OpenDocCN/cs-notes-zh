# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P16：16_02_04_Strassen次立方矩阵乘法算法.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

In this video we apply the divine and conquer algorithm design paradigm to the problem of multiplying matrices。

 This will culminates in the study of Strasin's matrix multiplication algorithm。

 And this is a super cool algorithm for two reasons。 First of all。

 Strason's algorithm is completely nontried。 It's totally non obviousous， very clever。

 not at all clear how Strasen ever came up with it。

 The second cool feature is it's first such a fundamental problem。

 So computers as long as they've been in use from the time they are invented up till today。

 a lot of their cycles is spent multiplying matrices because just comes up all the time in important applications。

 So let me first just make sure we're all clear on what the problem is of multiplying two matrices。

So we're going to be interested in three matrices， X， Y and Z。

 I'm going to assume they all have the same dimensions N by N。

The ideas we'll talk about are also relevant for multiplying nons matrices。

 but we're not going to discuss it in this video The entries in these matrices。

 you know you can think of it as whatever you want， maybe they're integers， maybe they're rationals。

 maybe they're from some finite field， it depends on the application but the point is they're just entries that we can add and multiply。

So how is it that you take two n by n matrices X and Y and multiply them producing a new n by n matrix Z？

Well， recall that the IJ entry of Z， that means the entry in the Ith row and the J column is simply the dot product of the I row of x with the Jth column of y。

So if IJ was this red square， this red over in the Z matrix。

 that would be derived from the corresponding row of the x matrix and the corresponding column of the Y matrix。

And recall what I mean by dot product， that just means you take the products of the individual components and then add up the results。

So ultimately， the ZIJ entry boils down to a sum over n things where each of the constituent products is just the XIK entry。

 the IK entry of the matrix x with the KJ entry of the matrix Y or your K is ranging from1 to n。

So that's how ZIJ is defined for a given pair of indices INJ。

One thing to note is that where we often use n to denote the input size here we're using n to denote the dimension of each of these matrices。

 the input size is not n， the input size is quite a bit bigger than n。

 specifically each of these are n by n matrices and contains n squared entries。

So since presumably we have to read the input which has size n squared and we have to produce the output。

 which also has size n squared， the best we could really hope for for a matrix multiplication algorithm would be a running time of n squared so the question is how close can we get to it？

Before we talk about algorithms for matrix multiplication。

 let me just make sure we're all crystal clear on exactly what the problem is。

 so let's just actually spell out what would be the result of multiplying two different two by two matrices so we can parameterize two generic2 by2 matrices by just giving the first one entries A。

 B， C and D for these four entries could all be anything and then we're multiplying by a second two by2 matrix let's call it entries EF G and H。



![](img/102617291f5e45096f165d7ad23660c6_1.png)

Now， what's the result of multiplying these where， again， it's going to be a  two by2 matrix。

 where each entry is just the corresponding doc product of the relevant row of the first matrix and column of the second matrix。

 So to get the upper left entry， we take the dot product of the upper row of the first matrix and the first column of the left column of the second matrix。

 So that results in。AE plus B G。To get the upper right entry。

 we take the dot product of the top row of the left matrix with the right column of the second matrix。

 so that gives us A F plus BH。And then filling in the other entries in the same way。

 we get CE plus DG and CF plus DH。 so that's multiplying two matrices and we've already discussed the definition in general。

Now， suppose you had to write a program to actually compute the result of multiplying two n by n matrices。

 One natural way to do that would just be to return to the definition and which defines each of the n squared entries in the z matrix as a suitable sum of products of entriesrices entries of the X and Y matrices So in the next quiz I'd like you to figure out exactly what would be the running time of that algorithm as a function of the matrix dimension n where as usual。

 we count the addition or multiplication of two individual entries as a constant time operation。



![](img/102617291f5e45096f165d7ad23660c6_3.png)

So the correct response to this quiz is the third answer that the running time of the straightforward inerative algorithm runs in cubic time relative to the matrix dimension N to see this。

 just recall what the definition of the matrix multiplication was。

 the definition tells us that each entry Z Ij of the output matrix Z is defined as the sum from k equal 1 to n of。

X Ik times Y Kj that is the dot product of the I row of the x matrix and the J column of the Y matrix。

 I certainly assuming that we have the matrices represented in a way that we can access a given entry in constant time and under that assumption。

 remember each each of these products only takes constant time and so then to compute Zj。

 we just have to add up these n products， so that's going to be theta of n time to compute a given Zj and then there's an n squared entries that we have to compute there's n choices for IN choices for J so that gives us n squared times n or cubic running time overall for the natural algorithm which is really just a triple4 loop which computes each entry of the output array separately using the dot product So the question as always。

 for the keen algorithm designer is can we do better Can we beat n cubed time from multiplying two matrices。



![](img/102617291f5e45096f165d7ad23660c6_5.png)

And we might be especially emboldened with the progress that we've already seen in terms of multiplying two integers。

 we applied the divide and conquer algorithm to the problem of multiplying two indiigit integers and we had both a naive recursive algorithm and a seemingly better algorithm due to Gauss which made only three recursive calls now we haven't yet analyze the running time of that algorithm but as we'll see later that does indeed beats the quadratic running time of the grade school algorithm so it's very natural to ask can we do exactly the same thing here there's the obvious and cube algorithm which follows straight from the definition。

 perhaps analogous to Gauss we could have some clever divide and conquer method which beats cubic time so that's what we're going to explore next。



![](img/102617291f5e45096f165d7ad23660c6_7.png)

![](img/102617291f5e45096f165d7ad23660c6_8.png)

Let's recall the divide and conquer paradigm what does it mean to use it Well we first have to identify smaller subpro so if we want to multiply two end by n matrices。

 we have to identify multiplications of smaller matrices that we can solve recursively once weve figured out how we want to divide the given problem in smaller ones then the conquer step we simply invoke our own algorithm recursively that's going to recursively multiply the smaller matrices together and then in general we'll have to combine the results of the recursive calls to get the solution for the original problem in our case to get the product of the original two matrices from the product of whatever sub matrices we identify。

So how would we apply the divide and conquer paradigm to matrices。

 so we're given two n by n matrices and we have to somehow identify smaller pairs of square matrices that we can multiply recursively。



![](img/102617291f5e45096f165d7ad23660c6_10.png)

So the idea， I think， is fairly natural， So we start with a big and by n matrix x。

So there's n rows and n columns we have to somehow divide it into smaller pieces Now the first thing you might think about is you put it into its left half and its right half analogous to what we've been doing with array arrays。

 but then we're going to break X into two matrices which are no longer square which are n over two in one dimension and have linked n in the other dimension and we want to recursively call a subroutine that multiplies square matrices。

 so what seems like the clear thing to do is to divide x into quadrants。

Okay so we have four pieces of X， each is going to be n over2 by n over2 corresponding to the different quarters of this matrix。

 so let's call these different quadrants or blocks in matrix terminology A B， C and D。

 All of these are n over 2 by n over two matrices as usual for simplicity I'm assuming that n is even and as usual doesn't really matter。

 and we can do the same trick with Y。So we'll divide y to quadrants。

N number two by N number two matrices， which we'll call E FG。Beach。

So one thing that's cool about matrices is when you split them in the blocks and you multiply them。

 the blocks just behave as if they were atomic elements。

So what I mean by that is that the product of X and Y can be expressed in terms of its quadrants and each of its four quadrants。

 each of its four corners can be written as a suitable arithmetic expression of the quadrants of X and Y。

 so here's exactly what those formulas are， they're exactly analogous to when we just multiplied pair of2 by two matrices。

So I'm not going to formally prove this fact I'm sure many of you have seen it before familiar with it。

 and if you haven't， it's actually quite easy to prove。

 it's not obvious you can't see it off the top of your head necessarily。

 but if you go back to the definition it's quite easy to verify that indeed when you multiply x and Y you can express its quadrants into blocks in terms of the blocks of x and Y。

So what we just did is completely analogous to when talking about integer multiplication and we wanted to multiply two integers。

 little X and little Y and we broke them into pairs of n over two digits。

 and then we just took the expansion and we observed to have that expansion could be written in terms of products of n over two digit numbers same thing going on here except with matrices So now we're in business as far as a recursive approach we want to multiply X and y their' n by n matrices we recognize we can express that product X times y in terms of the products of n over2 by n over two matrices things were' able to multiply recursively plus additions and additions it's clearly easy to multiply two different matrices with say n squared entries each it's going to be linear in the number of entries so it's going to be n squared time to add two matrices that are n by n。



![](img/102617291f5e45096f165d7ad23660c6_12.png)

So this immediately leads us to our first recursive algorithm。To describe it。

 let me quickly rewrite that expression we just saw in the previous slide。

And now our first recursive algorithm is simply to evaluate all of these expressions in the obvious way。

 so specifically in step one， we recursively compute all of the necessary products。

And observe that there are eight products that we have to compute。

 eight products of N over2 by N over2 matrices， there are four entries in this expansion of x times y each of the blocks is the sum of two products and none of the products reoccur。

 they're all distinct so naively if we want to evaluate this。

 we have to do eight different products of N over 2 by N over2 matrices。

Once those recursive calls complete， then all we do is do the。Necessary for additions。

As we discussed， that takes time proportional to the number of entries in the matrix。

 so this is going to take a quadratic time overall， quadratic an in。Linear in the number of entries。

Now， the question you should be asking is， is this a good algorithm， Was this good for anything。

 This recursive approach splitting X and y into these blocks。

 expanding the product in terms of these blocks and then recursively computing each of the blocks。

 And I want to say it's totally not obvious。 It is not clear what the running time of this recursive algorithm is。

 I'm going go ahead and give you a spoiler， which is going to follow from the master method that we'll talk about in the next lecture。

 But it turns out with this kind of recursive algorithm where you do eight recursive calls each on a problem with dimension half as much as what you started with and then do quadratic time outside。

 the running time is going to be。Cubic， so exactly the same as with the straightforward iterative algorithm that follows from the definition。

 that was cubic， it turns out， and that was clearly cubic， this one， although it's not obvious。

 is cubic as well， so no better， no worse than the straightforward iterative algorithm。

So in case you're feeling disappointed that we went through all this work and this sort of seemingly clever dividing conquer approach for matrix multiplication and came out at the end no better than the iterative algorithm well there's really no reason to despair because remember back in integer multiplication we had a straightforward recursive algorithm where we had to do four recursive calls。

 products anywhere over two digit numbers but then we had Gaus' trick which said oh if we only did more clever products and more clever additions and detractions then we can get away with only three recursive calls and we'll see later that that is indeed a significant savings in the time needed integer multiplication and we've done nothing analogously clever to Gausss trick for this matrix multiplication problem all we did is the naive expansion in terms of submatrices and the naive evaluation of the resulting expressions so the $64。

000 question is then can we do something clever to reduce the number of recursive calls from eight down to something lower and that is where Strenss algorithm comes in。



![](img/102617291f5e45096f165d7ad23660c6_14.png)

So at a high level， Strasen's algorithm has two steps。

 just like the first recursive algorithm that we discussed。

 it recursively computes some products of smaller matrices， N over2。

 roughly N over two by N over2 matrices。But there's only going to be seven of them。

If they will be much less straightforward， they will be much more cleverly chosen than in the first recursive algorithm。

And step two then is to actually produce the product of X and Y。

 produce each of those four blocks that we saw with suitable additions and subtractions of these seven products。

 and again these are much less straightforward than in the first recursive algorithm。

And so while the additions andtracts involved will be a little bit more numerous than they were in the naive recursive algorithm。

 it's only going to change the work in that part of the algorithm by a constant factor。

 so we'll still spend only theta of n squared work adding and subtracting things and we get a huge win in decreasing the number of recursive calls from 8 to7 Now just in case you have the intuition that shaving off one of eight recursive calls should only decrease the running time of an algorithm by 18 by 12。

5% In fact， it has a tremendously more amplified effect because we do one less recursive call over and over and over again as we keep recursing in the algorithm So it makes a fundamental difference in the eventual running time of the algorithm as we'll explore in detail in the next set of lectures when we discuss the master method So again。

A bit of a spoiler alert。What you're going to see in the next set of lectures that indeed Straston's algorithm does beat cubic time。

 it's better than endCub time， you'll have to watch the next set of lectures if you want to know just what the running time is。

 but I'm going to tell you now that savings of the eighth recursive call is what changes the algorithm from Cbic to subcubic。

Now，1969 was obviously quite a bit before my time， but by all accounts from people I've talked to who are around then and from what the books say。

 Straston's algorithm totally blew people's minds at the time。

 everybody was assuming that there's no way you could do better than the iterative algorithm。

 the cubic algorithm， it just seen the matrix multiplication intuitively fundamentally required all of the calculations that are spelled out in the definition。

 So Straston's algorithm is an early glimpse of the magic and of the power of clever algorithm design that if you really have a serious ingenuity。

 even for super fundamental problems， you can come up with fundamental savings over the more straightforward solutions。

So those are the main points I wanted to talk about Strasen's algorithm。

 how you can beat Cbic time by saving a recursive call with suitably chosen clever products and clever editions subions。

 maybe a few of you are wondering you know what are these cleverly chosen products Can you really do this and I don't blame you there's no reason to believe me just because I sort of spelled out this high level idea It's not obvious this should work you might want to actually see the products So for those of you like that this last slide is for you。

So here is Strasen's algorithm in its somewhat gory detail。

 so let me tell you what the seven products are that we're going to form。



![](img/102617291f5e45096f165d7ad23660c6_16.png)

I'm going to label them P1 through P7 and they're all going to be defined in terms of the blocks of the input matrices X and Y。

 so let me just remind you that we think of X in terms of its blocks。ABCD。

And we think of why in terms of its blocks。E FG H， remember A through H are all N over two by N over two sub matrices。

 So here are the seven products P1 through P7。P1 is a times quantity F minus H。

P2 is quantity A plus B times H。P3 is c plus D tones E。P4 is D times G minus E。

P5 is quantity A plus D times quantity E plus H。P 6 is quantity B minus D times quantity G plus H。

And finally， P7 is quantity A minus C。E plus F。So I hope you'll agree that these are indeed only seven products and we could compute these with seven recursive calls。

 so we pre processcess with a little bit of additions and subtractions。

 we have to compute F minus H A plus B c plus D and so on。

 we compute all of these new matrices from the blocks and we can then recursively with seven recursive calls do these seven products that operate on n over2 by n over2 matrices Now the question is why is this useful Y and Earth would we want to know the diaries of these seven products。

 so the amazing other part of the algorithm is that from just these seven products we can using only addition and subtraction recover all four of the blocks of a x times Y。

So x times y， you'll recall we expanded it in terms of the blocks。

So we previously computed this to be AE plus BG in the upper left corner and then similar the expressions for the upper right。

 lower left and lower right blocks， so this we already know。

 so the content of the claim is that these four blocks also arise from the seven products in the following way。



![](img/102617291f5e45096f165d7ad23660c6_18.png)

So the claim here is that these two different expressions for x times Y are exactly the same。

 and they're the same block by block。 So in other words， what the claim is that this。

Crazy expression， P5 plus P4 minus P2 plus p6， where those are four of the products that we've listed above。

 that is precisely AE plus BG。Similarly， we're claiming that P1 plus P2 is exactly AAF plus BH that's actually easy to see P3 plus P4 is C plus Dg that's also easy to see and then the other complicated one is that P1 plus p5 minus P3 minus P7 is exactly the same as CF plus DH so all four of those hold so let me just so you believe me because I don't know why you would believe me unless I actually showed you some of this derivation。

Let's just look at the proof of one of the cases of the upper left corner。So that is。

 let's just expand out this crazy expression， p5 plus P4 minus P2 plus p6， what do we get？Well。

 from P5， we get Ae。Plus， A H。Plus D。Plus Dh。And we add P4， so that's going to give us。Plus， Dg。

Minus D E。 Then we subtract P2。 So that gives us a minus。A H minus B， H。

And then we add in P6 so that gives us a。Bg。Plus， B， H minus D G minus D， H。Okay。

 so what happens next， well now we look for cancellations， so we cancel the AHs。We cancel the DEs。

We cancel the DHs。We canceled the DGs。We cancel the BHs。And the holy cow， what do we get， we get Ae。

Plus BG， that is we get exactly what we were supposed to in the upper left block of x times y。

 so we just actually verified that this equation holds for the upper left block。

 it's quite easy to see that it holds for the upper right and lower left blocks and an comparable calculation verifies it for the lower right blocks of the two so summarizing because this claim holds because actually we can recover the four blocks of x times y from these seven products Strasson's algorithm works in the following way。

 you compute the seven products P1 through p7 using seven recursive calls。

 then you just compute the four blocks using some extra additions and subtractions as shown in the claim so seven recursive calls on n by n over2 by n over2 matrices plus n squared work due to the necessary additions and as you'll see in the master method lecture that is actually sufficient for subtuubic to。

Now I sympathize with you if you have the following question。Which is。

 how on earth did Stras and come up with this？And indeed。

 this sort of illustrates the difference between checking somebody's proof and coming up with a proof。

 given that I told you the magical seven products and how you from them can recover the four desired blocks of x times y it's really just mechanical to see that it works it's a totally different story of how do you come up with P1 through P7 in the first place so how did Strs and come up with them。

Honestly， your guess is as good as mine。