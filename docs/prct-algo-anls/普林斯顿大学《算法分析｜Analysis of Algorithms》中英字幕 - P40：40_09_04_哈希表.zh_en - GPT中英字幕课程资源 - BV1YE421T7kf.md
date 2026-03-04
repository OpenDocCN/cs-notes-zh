# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P40：40_09_04_哈希表.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/8a42d604ec36f45949ac823605546965_0.png)

I just want to briefly discuss hash tables because they're quite closely related to words and balls and Ers problems。

 but won't spend a lot of time in lecture on it， there's more information in the book。So we。

We talked just briefly about the balls and ERns model and of course this is very heavily studied in classical combinatorics and so we talked about well what's probability that noAN has more than one ball with probability that noAns empty。

 you might want to know how many empty the urns there are， how many urns have K balls and so forth。

 these so-called occupancy problems are well studied dating back many， many decades。

So in the classical result is simply from the binomial distribution。

 the probability and we looked at this briefly when we talked about asymptotics。

 the probability that a value occurs k times， a given value turns k times in a random m word of length n is n choose k1 over m to the k 1 minus1 over m to the n minus k。

 that is you get your value k times with probability 1 over m。

 and the other values are not yours with probability 1 minus1 over m to the n minus k。

So that's in given in balls and imns， a probability given urn has K balls。

Now we looked at the Poisson approximation that works for the situation where N over M is alpha and is fixed in K is a small constant。

 that's the so-called Poisson approximation and we showed how to come up with that approximation when we talked about asymptotics。

呃。So and this is a very good approximation， so for example。

 this plot gives for this is for alpha equals 10， so n equals 10，000 n equals 1。

000 that's a plot of the binomial distribution so it's centered at 10 and that's where the peak is。

 and this is the poa approximation for that same case with alpha equals 10 and the curves are nearly identical。

And so the Boston approximation is a little bit easier to work with。

 so that's why it's so often used。So an application is in hashing algorithms。

 so people in computer science are very familiar with these algorithms。

 I'll just briefly describe them for people in math that maybe haven't seen them。

 they're very well covered in books sign algorithms like。Our book or Canose book。

 the idea is we want an efficient way to put key value pairs in a symbol table and we talked about this for binary search trees and rise and you want to search the table for the pair corresponding to a given key。

So the hashing strategy is to come up with a function that maps each key onto a random value between0 and M minus1 and then develop a collision strategy to figure out what to do when two keys hash to the same value。

And the basic algorithms that we'll talk about， one's called separate chaining where we essentially represent the urn with a linked list。

 another one's called linear probing where we just use an array and we never let to get in the same place where we scan through the empty spots on a collision and I'll talk about briefly about both of those algorithms and the model that we use is this idea that the hash function we assume what's called the uniform and hashing assumption that the hash function maps each key into a random value between zero and m minus one。

And it's been shown to be not so difficult for typical types of keys to get hash functions that reasonably approximate this uniform assumption。

So that's the setup， so hashing with separate chaining is really easy to implement and this is just a diagram from our algorithms book that shows a hash table of size5 and so the keys are letters and then the hash values are supposed to be random values between zero and five it's just a word so the sequence of hash values is just a random word and then we store the letters in list indexed by the hash values so those are the urns and the keys and the associated values are the balls。

So that's easy to implement and of course we're going to be interested in how long these lists are so again。

This is the just the balls and urns model for hashing with separate chaining and probably spending too much time on animations but。

うは。So what we want to know is when we're going to search for an item in this。

 we're going to have to go through all the balls in the urn。

 and so we want to know the average number of balls in each ur say。Well that's obvious。

 there's N balls， there's M urns on average there's n over M balls in each urn and actually that doesn't depend on anything。

 it's not very helpful at all， if all the balls fall in one urn still your average number of balls per urn is N over M doesn't have to be random even so that observation is not much help。

So and we know the probability that a given urn has k balls， that's the occupancy distribution。

 generally we're going to have try to keep the number of urns large enough that are a number of balls per urn is a constant like alpha so we know that。

 but what the programmer wants to know is something about what's the chances that they're distributed evenly。

So we have to do a little more math to provide that answer。So here's what a programmer might say。

 so if I make sure that M is big enough so that M or RA is less than some constant alpha and it turns out to be not difficult to do that then the average number of probes for search is going to be less than alpha I know that but what's the chance that some search will' use way too many probes under the uniform hashing assumptions。

 say five alpha probes， well that's actually not too difficult to calculate so what it is is that we know the probability for K probes。

 we could sum that for all K bigger than five alpha。And。

The trick is to use Sterling's formula to bound K factorial and then if you do that。

 then we get something that converges very rapidly so it's something like e to the minus alpha times e over 5 to the5 alpha and say for alpha equals 10 that's but 15 zeros 10 to the minus 15。

 so you can say to a programmer that if you take alpha equals 10。

 this is extremely extremely unlikely to happen and that's the kind of information the programmer needs。

So that's hashing with separate chaining， that's a typical calculation using classical occupancy distribution and some of the asymptotics that we did in lecture4。

The other hashing method is called linear probing and in this method we throw the balls into the urns。

 but we only leave room for one ball。And everything's fine until we get a collision where Er would take two balls and we know from the birthday problem that's going to happen relatively soon usually。

And when it happens， we just scan to the right till we find an empty ur。呃。

Now you don't want to do this if the table starts to get full as we'll see。

 but still we're going to want to know have analysis that tell us the average number of collisions when we use this algorithm。

 and it's a relatively easy algorithm to implement as well。呃。

And found in standard algorithms books as well。So that's the key question。

 what's the average number of probes to find one of the keys if you use this algorithm hashing with linear probing？

Well， this was proven over 50 years ago by Canuth to be this sum from K bigger than zero of n over M and minus1 over M down to M minus k plus 1 over M。

 which is。Really the proof is given in 10 pages in the textbook and it really was a landmark result。

 people were thinking this is too difficult a problem to really address and Canuth was able to show this result and if you let the table get full。

 you let n get to M then it's ramanuin function， and if you don't let the table get full which we don't in practice say don't let it get more than half full。

 then it's going to be one over one minus alpha， you don't let get more than half full then it's about two probes so in practice that's very important result。

Now。呃。I just want to tell a little bit of a story， so Canf has Canoe's books as four volumes now and more planned in volume 3 there's one footnote and Kuth taught that good writers don't use footnotes and technical writing but he said he couldn't resist putting in this one footnote that said that he formulated this derivation。

 it was the first nontrivial algorithm he had ever analyzed satisfactorily and he says it had a strong influence on the structure of these books。

 it really is where the analysis of algorithms began was when Canuth to solved this problem。

Now when Philippe and I wrote the Inuction analysis of Alrims textbook and we're learning about analytic combinatorics。

 it seemed reasonable that we should be able to analyze linear probing with the symbolic method。

So we couldn't resist putting in one footnote in our book either。

 and that one said that we don't know the answer to this exercise and we couldn't figure out how to use the symbolic method to analyze linear probing it seemed like their answer was so simple and so similar to birthday and coupon collector that we should be able to get it。

 and really we put this in as a challenge to students and researchers really we should be able to do this one。



![](img/8a42d604ec36f45949ac823605546965_2.png)

And it took some years， but eventually， and you can read about this in the second edition of the book。

 turn out this problem has very deep connections to properties of combinatorial objects like random graphs。

 the gambler ruined problem， paths links and trees in many other classic algorithms。

 and it's explained by a distribution called an airy law。

 and a very fascinating amount of mathematics to explain this。

And Canuth was one of the people who solved it in Philippe and some co-authors solved it as well。

 although actually still we don't quite exactly precisely know the answer of this exercise。

 we know quite a bit so there's actually still a footnote left in the second edition。

But linear probing is worth studying to see both the potential and limitations of what we know about analysis of algorithms at this point。

One of the foundations mentioned here is properties of mappings and that's what we're going to talk about next。



![](img/8a42d604ec36f45949ac823605546965_4.png)