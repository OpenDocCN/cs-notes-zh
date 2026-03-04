# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P30：30_07_06_应对难解性问题.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/f281cd7d72c67a945aa16c9b59ea8e9e_0.png)

So it looks like intractable problems are something that we're going to have to live with。

 so let's talk about different approaches。So first of all。

 we're saying when you encounter an MP complete problem。

 it's pretty safe to assume that's intractable， so what should you do？Well。

 I'll talk about at least four approaches that are successful。

 so first and most important is don't try to solve it， you ought to know what you're doing。

 you're not going to find very unlikely to find a guaranteed polynomial time algorithm for your problem。

But one thing that you can do is take a look at the inputs， the types of instances that you have。

 and remember that this whole theory is talking about the worst case。

 it's talking about guaranteeing that you have polynomial time in all inputs。

 maybe the ones that you have to solve in the real world are not the hard ones。

Another thing to do is to look for not complete solutions， the best traveling salesman tour。

 but one that's close to the best， I'm not going to talk much about that。

 but there's been a lot of emphasis on that。And the other thing is to just take advantage of the idea of intractability。

 and I will give an example of that。So don't try to solve intractable problems and these are cartoons from the Gary and Johnson book on intractability that was the first to really just after CAp within not many years after CAp to formulate hundreds and hundreds of these problems and develop the theory and this cartoon is from the book so if you're somebody that knows no theory and your boss says。

 I've got salesmen go get me the optimal tour， all you could do is say， well。

 I can't find an efficient algorithm。I guess I'm just too dumb and note the spelling of two。

So that's where you'd be pretty stuck with your boss。Now。

 if you know about Turing and computability and the boss asks you to write a program that takes any program's input and tells whether it halts。

 you could say I can't find an algorithm because there's actually no algorithm possible and I can prove that to you and you're the one that's too dumb。

 but now with intractability， what you can say is well I can't find an efficient algorithm but neither can all of these famous people。

 so you're in pretty good ground， as long as you understand when you're facing intractability。Well。

 here's an important example from scientific field statistical physics and this is just a sketch。

 but it's something that's going on all over science since the importance of this theory has been recognized。

 so this the icing model for phromagnetism and mathematical model and in the 1930s the field of statistical mechanics。

 an important research direction was developing a closedform solution to this model and in 44 there was an amazing paper that impressed people working in this field that was a closedform solution to the two-dimensional version of this problem。

 so spurred on by that success Richard Feynman and many others， many very accomplished scientists。

 were seeking for many years a closedform solution to the 3D version。Which is。

 of course the one that we have to cope with in the real world。

But around 2000 in which researchers showed that this problem is NP complete。

 which meant that all that effort for 50 years was really kind of wasted if those people had known about intractability they would know not to try to find a close form solution or at least do it with the understanding that it would be the scientific breakthrough of the century。

So work on another problem or work hard on just proving that P equals NP。

 maybe this is the way to show that P equals NP， but you least ought to know that， and again。

 thousands and thousands and thousands of problems or in this category and you don't want to be the situation of beating your head against a brick wall for 50 years trying to solve a problem that we know is very unlikely to have an efficient solution。

So again， one thing that you can do that I mentioned is that in practice you might not have these worstcase inputs。

 so it might be that there's a few some inputs， a small number of inputs that cause an algorithm to take exponential time so therefore you can't guarantee that it'll run in polynomial time but the ones that you have to solve might be easier so a reasonable approach is to say just take away the condition that it has to work on all inputs maybe it's enough that it works on the inputs that we care about and there's lots of examples of this。

 this is a very fruitful way to look at the situation so there's a program that solves 10。

000 variable instances of SA now these things are not running in time proportional to two to the 10000 they fast polynomial time algorithms this is actually develop by an undergraduate independent work in 2000。

And。The joke is that if you've got a large satAT instance。

 you can tell the difference between a theoretician and a practitioner。

 practitioner say if I can make my problem into a SAAT instance。

 then I can solve it using a thing like this， whereas a theoretician would say。

 if all you can do is get it to sat， you have to give up because satAT's intractable。

Even traveling salesman problem， people have there's a program called Concord that routinely solves huge real- worldld instances and they did 10 years ago they were doing 80。

000 city instance and it's much higher now and even integer linear programming。

 there's Cplex which routinely solves huge real- worldld instances for big corporations solving problems that they need in order to get their work done and also many scientific applications so living with intractability is certainly a fruitful approach and worthy of a lot for their study and then there's exploiting intractability in certainly a famous example of that is the RSA crypto system。

So they don't have to sell cryptography nowadays everywhere on the web。

 cryptography plays an important role because financial transactions depend for their security on secure communications and good cryptography and there's a very。

 very long list of applications， the RSA cryptoytem which was developed at MIT in the 70s is a method that exploits the intractability the difficulty of factoring。

So to use it， what you do is multiply and divide two long integers。 And that's relatively easy。

 So that's polynomial time in the number of digits in the integers。 But to break the system。

 you have to be able to factor a long in a long integer。

 We actually don't even know if that's intractable。 There's no reduction from Sain。

 And I'll talk about that in a minute。 but certainly seems difficult。

 So multiplication is easy factoring is difficult。So for example， go ahead。

 try to write a program to factor this 212 digit integer。

And Revesmeir and Aelman offered a prize for this。 Now it's a little bit outside our theory because there's no reduction from satin known。

 so a efficient algorithm for factor would be would break the crypto system。

 but it wouldn't prove that P equals NP P。So you can say factor not known to be impeccably。

 it could be that we just don't know the reduction。

But it's pretty safe to assume that it's difficult or even intractable。

 it's not as safe this assumption as for an MP complete problem， if you solve factor。

 you just solve factor， you don't prove the people's MP you don't solve all those other problems。

But still， that's a good example of exploiting the difficulty of a problem。

So what RSE actually wound up doing was creating an e-commerce company that actually was worth billions really based on this idea from theoretical computer science there's actually a prize now for resolving P equals NP since 2000 you get a million dollars if you resolve P equals NP you probably win a Turing award nowadays and get another million dollars so a theoretical computer science definitely can make you some money and by the way。

 if you broke P's NP， maybe you wouldn't want to claim the money because you would break e-commerce or you can sell t-shirts is another way to go so just one final thought and it's an important question nowadays so we talked about the difficult。

factoring and the idea of can we assume that it's intractable， well。

 maybe we could but there's something else that has come up。

 It seems like we've made the simplest assumptions that we possibly could。

 but in the mid-1990s Peter Sho proved that there's a method for factoring and end bit integer in just N cube steps。

 polynomial time on a device known as a quantum computer。

Quantum computing is something that many people have heard of。

 you can argue whether it's a reasonable model of computation or not。

 but you have to think about whether you still believe in the extended churchterring thesis nowadays。

 the one that says that resource is used by all reasonable machines within a polynomial factor of one another。

 if a quantum computer can be built and exist and that would break that would falsify this thesis。

 but whether or not this happens， I think the important finishing point for this lecture is that intractability is something that we need to understand it might even tell us something about the universe in which we live。



![](img/f281cd7d72c67a945aa16c9b59ea8e9e_2.png)

![](img/f281cd7d72c67a945aa16c9b59ea8e9e_3.png)