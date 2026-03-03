# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P96：21_02_06_最小生成树研究现状与开放问题-进阶选学.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/a25bd0c14b4847fbffb7b4ae6b927d3c_0.png)

In this optional video， I'm going to give you a glimpse of the research frontier on the problem of computing minimum cost span and trees。

We've now seen two excellent algorithms for this problem。

 Prims algorithm and Crusco's algorithm and with suitable data structures both run a near linear time Big O of M log n where M is the number of edges and is the number of vertices。

 Now on the one hand we should be pretty happy with those algorithms were only a log factor slower than what it takes to read the input。

 but again， the good algorithm designers should never be content， never be complacent。

 should always ask can we do better， maybe we can do even better than M log N。



![](img/a25bd0c14b4847fbffb7b4ae6b927d3c_2.png)

Well， believe it or not， you can do better than his implementations， at least in principle。

 at least in theory， you have to work pretty hard， and I'm definitely not going to discuss the algorithms or the analysis that prove this fact。

 but let me just mention a couple references that give MST algorithms with asymptotic runtime even better than M login。

So quite shockingly， if you're happy with randomized algorithms as we were with say the quick sort sorting algorithm then the minimum cost spanning tree problem can be solved in linear time。

 that's obviously an optimal algorithm you have to look at the whole graph to compute the minimum cost spanning tree。

 but you can solve the problem in time a constant factor larger than what it takes to read the input。

This algorithm is much， much newer than Pri and Crusco's algorithm as you might expect。

 it does date back to the 20th century， but definitely the latter stages of last century。

So the names of a couple of the inventors of this algorithm will already be familiar to those of you that paid close attention in part1。

 so the Car here is the same as the author of the randomized Men cut algorithm we studied in Part one。

 Tarjjan's name is coming up a couple times in these courses， but for example。

 when we discuss stronglylly connected component algorithms。

So what if you're not happy with a bound just on the expected running time with the expectation over the coin flips of the algorithm。

 What if you want a deterministic algorithm。 So if we think of this randomized algorithm as being analogous to quick sort in the sorting problem。

 what would be the analog of merge sort。 Well， it turns out we do not know whether or not there's a linear time deterministic algorithm for minimum spanning trees。

 That's an open question。 You might think here at this late date 2012，2013。

 wed know everything there is to know about minimums cost spanning trees。

 we do not know if there exists a linear time deterministic algorithm。

 We do know that there's a deterministic algorithm with running time absurdly close to linear。



![](img/a25bd0c14b4847fbffb7b4ae6b927d3c_4.png)

Specifically， there's an algorithm with running time M， the number of edges times alpha of n。

 so what you ask is alpha of n what is this function。

 Well it's something called the inverse acromen function。

So defining the ackerman function and its inverse actually takes a little bit of work。

 so I'm not going to do it right now for those of you that are curious you should check out the optional material on the union find data structure。

 which is yet another context where sort of unbelievably this inverse ackerman function arises but for the present context what you should know is that this is a crazy slowg function It's not constant for any number C I can exhibit a large enough value of n so that this function values is at least C so that alpha n is at least C So it's not bounded by a constant but it's mind boggling how slow growing this function is。

 let me actually just give you an incredibly slow growing function which actually goes much faster than the inverse ackermen just to prove the point。

Specifically， if the inverse acrament function grows quite a bit slower than log star N。

 log star n I can define for you easily。 Re recall our definition of log base 2 way back when we first demystified logarithms to the beginning of part 1。

 If you type n into your calculator and you keep dividing by 2。

 you count the number of times you divide by 2 until you drop below1。

 That's log base2 of n for log star， instead of dividing by2。

 you're going to hit the log button on your calculator。

 and you count how many times you hit log until the result drops below1。 That number。

 the number of times you hit log is defined to be log star of n。

The log star function as the inverse of the function， which is a tower of twos。

 the function which takes as input， an integer， say t and raises2 to itself t times。

So to appreciate just how slow growing the log star function is。

 let alone the inverse ackerment function， what you should do is type in the biggest number you can into your nearest calculator or computer。

 just keep typing in nines as long as you can。 then go ahead and evaluate log star keep applyinging the log function till drops below one。

 Probably the results gonna to be something in the neighborhood of five。

 So log star of the biggest number in your calculator computer is going be5。

's how that's how slow growing this function is。So the upshot is that the algorithmgas community has the time complexity of the MST problem almost nailed but not quite in the deterministic case。

 the right answer is somewhere between M and M times inverse acromin function and we don't know where。

 but you know what， it gets weirder。So check out the following result of Pety and Rammanchandran。

They， in a sense， solved the determin st minimum cost spanning sheet problem by exhibiting an algorithm whose to complexity is optimal。

 So they gave an algorithm and they gave a proof just in the spirit of what we did for sorting。

 they gave a proof that no algorithm could have running time asymptically better than theirs。

 But what they didn't do is explicitly evaluate what the time complexity of their algorithm is。

 So they managed to prove optimality without actually evaluating exactly what' its running time。

 So it certainly somewhere between linear and linear times inverse acromen。

 We know that's the true time complexity of the problem。

 We know an algorithm that achieves that optimal complexity。 But to this day。

 we do not know what that optimal time complexity actually is as a function of the graph size。

So those are some of the most advanced things that we do know about the minimum cost spanning tree problem。

 let me just mention a couple things that we still to this day do not know。

So let me start with the randomized algorithms Now maybe your reaction is there's no open questions in the randomized algorithms world because we know you need linear time to solve the problem and I've told you that there is a randomized algorithm with expected running time that is linear so what more could you want Well what I want is I want an algorithm that's not just a linear time but also simple enough that I can teach it to other people so ideally it would be in an undergraduate course like this。

 but I would actually be very happy to have a randomized algorithm linear time simple enough to cover in a graduate course The current linear time algorithms do not have that property they're more complicated than I can even cover in a graduate course。



![](img/a25bd0c14b4847fbffb7b4ae6b927d3c_6.png)

To accomplish this task， it turns out to be enough to solve a seemingly simpler task。

 namely to get a simple randomized linear time algorithm for the MST verification problem。

 So let me tell you what that means。 So in the MST problem。

 you're supposed to optimize amongst all exponentially many spanning trees you got to find me the one with the smallest sum of edge costs and MST verification。

 the job seems simpler。 I'm actually going to hand you a candidate MST or I'm going to hand you a spanning tree and may or may not be the best one and you just need to check is it the optimal one or not。

 Furthermoremore， in the event that it's not optimal you should tell me edges that are not in the minimum spanning tree edges that are too expensive that I should throw out。

The reason it's enough to design a linear time algorithm for this seemingly simpler problem is that the content of the cargo Kin tar paper is a reduction。

 a randomized reduction from optimizing over spanning trees to this seemingly simpler problem of MST verification。

 Moreover， all of the novel content in the cargo Kin tar algorithm。 It's linear time。

 It's randomized and it is really simple。 I teach the stuff in that paper in my graduate classes。

 but it needs this MST verification subroutine as a black box and the only known implementations that are linear time for MST verification are quite complicated。

 So find a simple way to do MST verification that runs a linear time and you're good to go with your simple optimal MST algorithm。

For deterministic algorithms， the holy grail is obvious。

 we'd love to have a deterministic algorithm for MST that runs in linear time。

 or at the very least we just need to figure out know what is the best possible time complexity of any deterministic MST algorithm。

So one of the takeaways of this discussion is that for all the amazing advances by computer scientists on the design and analysis of algorithms over the past 50 years or so。

 there are still totally fundamental things that we do not understand。

 so there's still great ideas to come in the future。

So if you've been intrigued by some of the things I've said in this video and you want to learn more about these advanced minimum cost spanning tree algorithms。

 for further reading I'd recommend a survey by Jason Eisner called State of the Art Minimum Spning Tre algorithmrims。

 it's about 15 years old now but it's still an amazing resource for learning about this advanced material。

