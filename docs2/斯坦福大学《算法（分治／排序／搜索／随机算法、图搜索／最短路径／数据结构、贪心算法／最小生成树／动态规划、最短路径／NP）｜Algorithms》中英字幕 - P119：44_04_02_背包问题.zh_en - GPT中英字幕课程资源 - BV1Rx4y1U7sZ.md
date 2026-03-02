# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P119：44_04_02_背包问题.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/4057cf9bb80a1032088b4156fdec5ad2_0.png)

So in these next two videos， we'll give our second application of the dynamic programming paradigm。

 it's to a quite wellknown problem， it's called the NApsack problem and we'll show how following the exact same recipe that we used for computing independent sets in path graphs leads to the very well-known dynamic programming solution to this problem。

So let's jump right into the definition of annapsack problem， so the input is given by n items。

So each item comes with a value v sub I， the more the better for us， and also a size W sub I。

We're going to assume that both of these are non negative。

 for the sizes we're going to make an additional assumption that they're integral。

In addition to these two n numbers we're given one more， which is called a capacity capital W， again。

 we'll assume this is both non negative and an integer。

The role of these integralality assumptions will become clear in due time。In the Napsack problem。

 the responsibility of an algorithm is to select a subset of the items。What do we want。

 what we want as much value as possible is we want to maximize sum of the values of the items that we select。

So what prevents us from picking everything， well some of the sizes of the items that we pick have to total to at most the capacity capital W。

Now I could tell you some cheesy story about a burglar breaking into a house with a knapsack with a certain sized capital W and wants to make away with sort of the best loot possible。

 but that would really be doing a disservice to this problem which is actually quite fundamental this problem comes up quite a bit。

 especially as a subroutine in some larger task。Really just whenever you have sort of a budget of a resource that you can use and you want to use it in the smartest way possible。

 that's basically thenapsackack problem， so you can imagine how it would come up in a lot of contexts。

So let's now execute a recipe for developing a dynamic programming algorithm。

 remember the key to any dynamic programming solution is to figure out what is the right set of subproblem and we're going to arrive at the subproblem for the NApsAC problem just as we did from Maxwa In sets by doing a thought experiment about the optimal solution and understanding what it has to look like in terms of solutions to smaller subproblem。

The bottom line of this thought experiment， the deliverable will be a recurrence。

 it will be a formula which tells us how the optimal value of one sum problem depends on the value of smaller sub problems。

So to begin the thought experiment， fix an instance ofnapsack and let capital S denote an optimal solution。

 a max value solution。We began our previously thought experiment with the content free statement that the final vertex of a path is either in the optimal solution or it's not。

 Now， what is the analog of the rightmost vertex in thisnapsack problem。 Well unlike a path graph。

 there is no intrinsic sequentiality to the items that were given。

 They're just an order under its set， but it's actually useful to think of the items is sort of literally ordered1。

2，3 all the way up to n。 and then the analog of the rightmost vertex is just the final item。

 So the content free statement we're going to work with here is either the last item belongs to the optimal solution capital S。

 or it doesn't。We'll again， start with the easy case， when it doesn't。

What we argued in the path graph problem was that the max weight independence set in the analogous case1 has to be optimal if we just delete that rightmost edge from the graph。

 so here the analogous claim is that this set S should still be optimal if we delete the final item n from the Napsack instance。

The argument is the exact same near trivial contradiction。

 If there is a different solution as star amongst the first n -1 items with weight even bigger than down of S。

 well we could regard this equally well as a superior knapsack feasible solution back with all n of the items。

 but that contradicts the purported optimality of S。

So let's go through these slightly trickier case  two together， using a quiz。

So suppose the Anapsack solution does in fact make use of this final item N。

Now we want to talk about this being somehow composed of an optimal solution to a smaller subproble。

 so if we're going delete the last item， then we can't talk about S because S has the last item。

 so we need to remove the last item from S before we talk about its optimality that's analogous to back in the independent set problem。

 we remove the rightmost vertex from the optimal solution before talking about its optimality in a smaller subproble So the question then is if we take capital S the optimal solution we remove item N in what sense is the residual solution optimal。

 put differently for what kind ofnapsack instance if any， is that an optimal solution for。



![](img/4057cf9bb80a1032088b4156fdec5ad2_2.png)

All right， so the correct answer is C。So back in the independent set problem。

 what we said is that if we remove the rightmost vertex。

 then what's left is optimal for the residual independent set problem we get by plucking off the rightmost two vertices here when we remove the n item from the optimal solution S。

 the claim is what we get is optimal for thenapsack problem。

Involving the first n minus1 items and a residual Napsack capacity of capital W minus little W sub。

 so the overall the original Napsack capacity with space reserved or deleted for the nth item。

So before I give you a quick proof， let me just briefly explain why a couple of the other answers are not correct。

 So first of all， answer B， I hope you could rule out quickly， it just doesn't tight check。

 So capital W， that's the Napsack capacity。 So that's in units of size。

 little v sub n that's the itemss values that's in dollars so it doesn't really make sense to talk about the difference between those two they're just it's apples and oranges Part D。

 if you are worried about feasibility at any point。

 So if you take capital S and removed the item what have you done。

 you've taken a set of items whose size was at most capital W by feasibility of S and you've removed an item with size W n from it。

 So what remains has total size at most capital W minus little W n。

 So S minus n wouldn't indeed be feasible for this reduced this residual Napsack capacity。

 capital W minus little W n。A muchuch more subtle point is part A。

 that's a very natural one to guess。 That turns out to not be correct。

 So it turns out there might be smarter ways of using the first n -1 items than S minus item N。

 if you had a full NApsack capacity of capital W to work with。

 So that's a subtler point and it's a good exercise for you to actually convince yourself that a is wrong that there's no reason that when you take out item n from S and you still keep using the original NApstack capacity that this has to be optimal。

 that's not going to be true。All right， so why is capital C correct。

 well this is going to have the same spirit of case2 of our weighted independent set thought experiment？

So let me give you the proof the proof is gonna to be the usual contradiction analogous to case2 of our argument in the weighted independent set problem。

 So suppose there was something better than S with n removed with the residual capacity。

 capital W minus little w sub n called that supposedly better solution S star So what can we do to get a contradiction。

 well， let's just take S star， which involves only the first n minus1 items。

 let's add item n to it since S star has total size of most capital W minus little w sub n。

 and item n has size w sub n， the result has total size of most capital W。

 So it's a feasible solution to take S star and extend it by item number n。

 and if s star had more value than S with n removed， then S star with n included。

 has more value than S。 So for example， if S had total value 1100。

100 of which was coming from the n item than S with n removed， had value 1000 if S star was better。

 it had value 1050。Well then we just put n back in and it has value 1150 which contradicts the purported optimality of S star which had total value merely 1100 so notice what's going on here so in taking away W sub n from the NApsat capacity before we look at the residual problem we' in effect reserving a buffer for item N if we ever need it。

 that's how we know we're feasible when we stick n back into this solution as star that's analogous to deleting the penultimate vertex of the path again as a buffer to ensure feasibility when we include the n vertex back in the independent set problem。

So what was the point of this whole thought experiment， which we've now completed Well， again。

 the point was to say the optimal solution， whatever it is， it has to have only one of two forms。

 we've narrowed the list of candidates down to two possibilities。

 either you just inherit the optimal solution with one less item and the same NAsack capacity or you look at the optimal solution with one less item and less NASack capacity by W sub n and you extend that by item N but those are the only two possibilities。

 So again， if we only knew which of these two cases were true。

 if we only knew whether or not item N was in the optimal solution or not in some sense we could recursively compute the rest of the solution So just as that was enough to get us going with a dynamic programming algorithm for weighted independent sets so it goes with Napsack as I'll show you in the next video。

