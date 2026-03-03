# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P6：06_01_09_归并排序伪代码.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

Okay， so let's move on and actually discuss the pseudocode for the merge short algorithm。First。

 let me just tell you the pseudocode leaving aside exactly how the merg subroutine is implemented and thus high level should be very simple and clear at this point。

So there's gonna to be two recursive calls and then there's gonna to be a emerging step。

 Now I owe you a few comments because I'm being a little sloppy again， as I promised。

 this isn't something you would directly translate into code， although it's pretty close。

 but so what are a couple of the ways that I'm being sloppy well first of all。

 in any recursive algorithm， you gotta have some base cases。

 you got to have this idea that when the inputs sufficiently small， you don't do any recursion。

 you just return some trivial answer。 So in the sorting problem。

 the base case would be if you're handed an array that has either zero1 elements， well。

 it's already sorted， there's nothing to do so you just return it without any recursion。

 so to be clear， I haven't written down the base cases。

 although of course you would if you're actually implementing it merge sort let make a note of that a couple of things I'm ignoring I'm ignoring what to do if the array has odd length So if it has say nine elements。

 obviously you have to somehow break that into five and4 or4 and5 So you would do that just in either way and that would be fine and then secondly I'm ignoring the details of what it really means to sort of recursively sort So for example。

 I'm not discussing。

![](img/63c1050cc8a6da6498a2c1a4668c2e98_1.png)

Exactly how you would pass these subs onto the recursive calls that's something that really would depend somewhat on the programming language so that's exactly what I want to avoid I really want to talk about the concepts which transcend any particular programming language implementation so that's why I'm going to describe algorithms at this level okay。

All right， so the hard part relatively speaking then is how do you implement the merge step。

 the recursive calls have done their work， we have these two sorted subars of half the numbers。

 the left half and the right half， how do we combine them into one and in English I already told you on the last slide the idea is you just populate the output array in sorted order by traversing pointers or just traversing through the two sorted subars in parallel So let's look at that in some more detail Okay so here is the pseudocode for the merge step。



![](img/63c1050cc8a6da6498a2c1a4668c2e98_3.png)

So let me begin by introducing some names for the characters in what we're about to discuss。

So let's use C to denote the output array。 So this is what we're supposed to spit out with the numbers in sorted order and then I'm going to use A and B to denote the results of the two recursive calls。

 Okay so the first recursive call has given us array A which contains the left half of the input array and sorted order Similarlyly B contains the right half of the input array again in sorted order So as I said we're going to need to traverse the two sorted subars A and B in parallel So I'm going to introduce a counter I to traverse to A J to traverse through B I and J well if we initialize to one to be the beginning of their respective arrays and now we're going to do。

We're going to do a single pass through the output array poping it an increasing order。

 always taking the smallest from the union of the two sorted sub arrays and if there's one idea in this mergerch step。

 it's just the realization that the minimum element that you haven't yet looked at in A and B has to be at the front of one of the two lists so for example at the very beginning of the algorithm。

 where is the minimum element overall， well whichever of the two arrays that lands in A or B it has to be the smallest one there so the smallest element overall is either the smallest element in A or it's the smallest element in B so you just check both places the smaller one's the smallest。

 you copy it over and you repeat and that's it。So the purpose of K is just to tra the output array from left to right。

 That's the order we're going to populate it currently looking at position I in the first array and position J and the second array。

 so that's how far we've gotten， how deeply we probed into both of those two arrays。

 We look at which one has the current smallest and we copy the smallest one。

Okay so if the entry in the I position of a is smaller， we copy that one over。

 of course we have to increment I， we probe one deeper into the list A and symmetrically for the case where the current position B has the smaller element Now again I'm being a little bit sloppy so that we can focus on the forest and not sort of and not get bogged down with the trees。

 I'm ignoring some n cases so if you really wanted to implement this you'd have to add a little bit to keep track of when you fall off either A or B so you'd have additional checks for when I or J reaches the end of the array at which point you copy over all the remaining elements into C All right so I'm going to give you a cleaned up version of that pseudocode so that you don't have to tolerate my questionable handwriting any longer than it's absolutely necessary this again is' just the same thing that we wrote on the last slide the pseudocode for the merge step。

Now， so that's the Mer algorithm。Now let's get to the meaty part of this lecture， which is okay。

 so merge short produces a。sortrted array， what makes it if anything better than much simpler non divide and conquer algorithms。

 like say， insertion sort， in other words， what is the running time of the merge sort algorithm？

Now I'm not going to give you a completely precise definition of what I mean by running time and there's good reason for that。

 as we'll discuss shortly， but intuitively you should think of the running time of an algorithm。

 you should imagine that you're just running the algorithm in a debugger and every time you press enter you advance one line in the program through the debugger and then basically the running time is just the number of operations executed the number of lines of codes executed so the question is how many times you have to hit enter on your debugger before the program finally terminates so we're interested in how many such lines lines of code get executed for merge sort when the input array has n numbers so that's a fairly complicated question so let's start with a more modestco rather than thinking about the number of operations executed by merge sort which is this crazy recursive algorithm which is calling itself over and over and over again let's just think about how many operations are going to get executed when we do a single merge of two sorted subarrays that seems like it should be an easier place to start So let remind you the pseudocode of the merge subroutine Here it is。

So let's just go and count up how many operations that are going to get used。

So there's the initialization step， so let's say that I'm going to charge us one operation for each of these two initializations。

So let's call this two operations。Just an Ia1 and Jal one。Then we have this for loop。

 so clearly the four loop executes a total number of n times。

 so in each of these n iterations of this for loop。

 how many instructions get executed Well we have one here。

 we have a comparison so we compare AI to BJ and either way the comparison comes up。

 we then do two more operations， we do an assignment here or here。

And then we do an incremented relevant variable either here or here。

 so that's going to be three operations per iteration。

 and then maybe I'll also say that in order to increment K。

 we're going to call it a fourth iteration Okay so for each of these n iterations of the four loop。

 we're going to do four operations。So putting it all together。

 what we have is the running time for merge， so let's say the upshot。

So the upshot is that the running time of the merged subroutine given an array of m numbers is at most4 m plus2 So a couple of comments。

 first of all， I've changed a letter on you so don't get confused in the previous slide we're thinking about an input size of n here I've just made I've changed the name of the variable to M that's going to be convenient once we think about merge short which is recursing on smaller subproble but it's exactly the same thing and and whatever So an array of m entries it doest most4 m plus two lines of code。

 The second thing is there's some ambiguity in exactly how we counted lines of code on the previous slide So maybe you might argue that you know it really each loop iteration should count as two operations not just one because you don't just have to increment K but you also have to compare it to the upper bound of n maybe would have been5 m plus2 instead of4 m plus2 So it turns out these small differences in how you count up the number of lines of code executed are're not going to matter and we'll see why shortly So amongst friends。

Let's just agree， let's call it4M plus two operations for merge to execute an array of exactly M entries。

So let me abuse our friendship now a little bit further with an inequality which is true but extremely sloppy。

 but I promise it'll make our lives just easier in some future calculations， so rather than 4M plus2。

 it' two sort of getting on my nerves， let's just call this at most6M。Because M is at least one。

You have to admit it's true。6 m always is at least4 m plus2。 It's very sloppy。

 These numbers are not anything close to each other for m large。

 but let's just go ahead and be sloppy in the interests of future simplicity Now I don't expect anyone to be impressed with this rather crude up or bound and the number of lines of code that the merge subroutine needs to finish to execute the key question to recall was how many lines of code does merge sort require to correctly sort the input array。

 not just this subroutine and in fact analyzing merge sort seems a lot more intimidating because it keeps spawning off these recursive versions of itself so the number of recursive calls。

 the number of things we have to analyze is blowing up exponentially as we think about various levels of the recursion Now if there's one thing that we have going for us it's that every time we make a recursive call it's on a quite a bit smaller input than what we started with it's on array of only half the size of the input array So there's some kind of tension between on the one hand explosion of subpro。

 a proliferation of subproblem and。

![](img/63c1050cc8a6da6498a2c1a4668c2e98_5.png)

that successive sub problemsm only have to solve smaller and smaller subpro and resolving these two forces is what's going to drive our analysis merge short So the good news is is I'll be able to show you a complete analysis of exactly how many lines of code merge sort takes and I'll be able to give you and in fact a very precise upper bound so here's going to be the claim that we're going to prove in the remainder of this lecture so the claim is that merge short never needs more than。



![](img/63c1050cc8a6da6498a2c1a4668c2e98_7.png)

S times n times the logarithm of n log base two if you're keeping track plus an extra 6 n operations to correctly sort an input array of n numbers。

 Okay so let's discuss for a second， is this good Is this a win knowing that this is an upper bound on the number of lines of code that merge sort takes。

 Well， yes， it is。 And it shows the benefit to the divine and conquer paradigm。

 recall in the simpler sorting methods that we briefly discussed like insertion sort selection sort and bubble sort。

 I claimed that their performance was governed by a quadratic function of the input size。

 that is they need a constant times n squared number of operations to sort an input array of length n merge short by contrast needs it most a constant times n times log n。

 not n squared but n times log n lines of code to correctly sort an input array So to get a feel for what kind of win this is。

 Let me just remind you for those of you that are rusty or for whatever reason have lived in fear of the logarithm just exactly what the logarithm is。

So the way to think about the logarithm is as follows。So you have the X axis。Or you have N。

Which is going from one up to infinity。And for comparison。

 let's think about just the identity function。Okay， so。The function， which is just。F of n equals n。

Okay and let's contrast this with a logarithm。 So what is the logarithm。 Well， for our purposes。

 we can just think of the logarithm as follows。 Okay so the log of n log base 2 of n is you type the number n into your calculator then you hit divide by2 and then you keep repeating dividing by2 and you count how many times you divide by two until you get a number that drops below1 So if you plug in 32。

 you got to divide 5 times by  two to get down to1 log base  two of 32 is 5。 if you put in 1024。

 you have to divide by 210 times till you get down to 1。

 So log base2 of 10024 is 10 and so on so the point is you can already see this if log of 1000 roughly is something like 10。

 then the logarithm is much， much smaller than the input so graphically with a logarithm is going to look like is it's going to look like。

A curve， which。Becomes very flat， very quickly as end grows large。Okay， so then。

Being a log based2 of n， and I encourage you to do this perhaps a little more precisely on a computer or a graph calculator at home。

 but log is wearinging much， much much slower than the identity function and as a result。

 sorting algorithm which runs in time proportional to n times log n is much， much faster。

 especially as n grows large than a sorting algorithm with running time that's a constant times n squared。



![](img/63c1050cc8a6da6498a2c1a4668c2e98_9.png)