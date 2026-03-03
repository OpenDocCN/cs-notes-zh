# 斯坦福大学《算法启蒙（第1册）：基础篇｜Algorithms Illuminated, Part 1： The Basics》中英字幕 - P31：-30-8   6   Omegan log n Lower Bound for Comparison Based Sorting Advanced - GPT中英字幕课程资源 - BV1vSVAzXE2r

This optional video will be more or less the last word that we have on sorting for the purposes of this course and it'll answer the question can we do better remember that's the mantra of any good algorithm designer I've shown you N log n algorithms for sorting。

 merge sort in the worst case， quick sort on average。

 can we do better than N log N indeed for the selection problem we saw we could do better than N logN and we could do linear time。

 maybe we can do linear time for sorting as well。The purpose for this video is to explain to you why we cannot do sorting in linear time。

 so this is a rare problem where we understand quite precisely how well it can be solved。

 at least for a particular class of algorithms called comparison based sorts。

 which I'll explain in a moment， so here's the formal theorem I want to give you the gist of in this video。

So in addition to restricting to comparison based sorts， which is necessary。

 as we'll see in a second， I'm going to make a second assumption which is not necessary。

 but is convenient for the lecture， which is that I'm going to think only about deterministic algorithms for the moment。

I encourage you to think about why the same style of arguments gives an n log n lower bound on the expected running time of any randomized algorithm。

 maybe I'll put that on the course side as an optional theory problem。

 so in particular a quick sort is optimal in the randomized sense。

 it has average n log n time and again the claim is that no comparison based sort can be better than that even on average。

So I need to tell you what I mean by a comparison based sorting algorithm。

What it means it's a sorting algorithm that accesses the elements of the input array only via comparisons。

 It does not do any kind of direct manipulation on a single array element。

 All it does is it picks pairs of elements and ask the question is the left one bigger or is the right one bigger I like to think of comparisonbased sorts as general purpose sorting routines they make no assumptions about what the data is other than that it's from some totally ordered set I like to think of it really as a function that takes as an argument a function pointer that allows it to do comparisons between abstract data types there's no way to access the guts of the elements all you can do is go through this API which allows you to make comparisons and indeed if you look at the sorting routine and set the Uni operating system that's exactly how it's set up you just pass it to function pointer to a comparison operator。



![](img/ab89434b54ae68e7e2bb70bda2fb08ed_1.png)

I know this sounds super abstract， so I think it becomes clear once we talk about some examples。

 there's famous examples of comparison based sorts including everything we've discussed in the class so far。

 there's also famous examples of non-comparison based sorts which we're not going to cover。

 but perhaps some of you have heard of or at the very least they're easier to look up on Wikipedia or wherever。

So examples include the two shorting algorithms we've discussed so far， merged short。

The only way that merge sort interacts with the elements in the input array is by comparing them and by copying them。

Similarly， the only thing Quicksortt does with the input array elements is compare them and swap them in place。

For those of you that know about the HeAP data structure。

 which we'll be reviewing later in the class， HeAP sort where you just heify a bunch of elements and then extract the minimum and times。

 that also uses only comparisons。So what are some famous non examples。

 I think this will make it even more clear what we're talking about。

So bucket sort is one very useful one。So bucket sort is used most frequently when you have some kind of distributional assumption on the data that you're sorting。

 And remember that's exactly what I'm focusing on avoiding in this class I'm focusing on general purpose subroutines where you don't know anything about the data if you do know stuff about the data bucket sort can sometimes be a really useful method For example。

 suppose you can model your data as IID samples from the uniform distribution on zero1 So they're all rational numbers bigger than0 less than one and you expect them to be evenly spread through that interval then what you can do in bucket sort is you can just preallocate n buckets where you're gonna collect these elements Each one is going to have the same width with one over n。

 the first bucket， you just do a linear pass through the input array。

 everything that's between 0 and one over n you stick in the first bucket。

 everything between one over n and two over n you stick in the second bucket two over ran and three over and you stick in the third bucket and so on So with a single pass you've classified the input elements according to which bucket they belong in Now because the data is assumed to be uniform at random that means you expect each of。

to have a very small population just a few elements in it。

 So remember if elements are drawn uniform from the interval 01。

 then it's equally likely to be in each of the n available buckets and since there's n elements that means you only expect one element per bucket so each one is going to have a very small population having bucketed the data you can now just use say insertion sort on each bucket independently you're going be doing insertion sort on a tiny number of elements so that run in constant time and then there's going to be a linear number of buckets with linear time overall so the upshot is if youre willing to make really strong assumptions about your data like it's drawn uniformly a random from the interval 01 then there is not an n log n lower bound。

 In fact you can elude the lower bound and sort in linear time。So just to be clear。

 in what sense is bucket sort not comparison- based。

 in what sense does it look at the guts of its elements and do something other than access them by pairs of comparisons。

 well it actually looks at an element in the input array and it says what is its value and the checks of its value is 0。

17 versus 0。27 versus 0。77 and according to what value it sees inside this element it makes the decision of which bucket to allocate it to。

 so it actually stares at the guts of an element to decide what to do next。Another non example。

 which can be quite useful is counting sort。So this sorting algorithm is good when your data。

 again you're going to make an assumption on the data when they're integers and they're small integers。

 so say they're between0 and K where k is say ideally at most linear and n so then what you do is you do a single pass through the input array again you just bucket the elements according to what their value is it's somewhere between0 and K and it's an integer by assumption so you need k buckets and then you do a pass and you sort of depulate the buckets and copy them into an output array and that gives you a sorting algorithm which runs in to O of n plus K where k is the size of the biggest integer so the upshot with counting sort is that if you're willing to assume the data are integers bounded above by some factor linear and n proportional to n then you can sort them in linear time。

Again， counting sort does not access the array elements merely through comparisons。

 it actually stares at an element， figures out what its value is and uses that value to determine what bucket to put the element in so in that sense it's not a comparison based sort and it can under various assumptions beat the n log in lower bound so a final example is the well-known algorithm called Radix sort I think of this is sort of an extension of counting sort although you don't have to use counting sort is the inner loop you can use other so-called stable sorts as well and is stuff you can read about in many programming books or on the web and the upshot of Rad is again you assume that the data are integers。

 you think of them in digit representation， say binary representation and now you just sort one bit at a time starting from the least significant bits and going all the way out to the most significant bits and so the upshot of rating sort it's extension of counting sort in the sense that if your data is integers that are not too big polynomally bounded in n then it lets you sort in linear time。

So summarizing a comparison- based sort is one that can only access the input array through this API that which you do comparisons between two elements。

 you cannot access the value of an element so in particular you cannot do any kind of bucketing technique。

 bucket sort， count sort and rating sort all fundamentally are doing some kind of bucketing and that's why when you're willing to make assumptions about what the data is and how you are permitted to access that data。

 that's what you can bypass in all of those cases， this n log n lower bound。

 but if you're stuck with a comparison based sort， if you want to have something general purpose。

 you're going to be doing n log N comparisons in the worst case， let's see why。

So we have to prove a lower bound for every single comparison based sorting method， so a fixed one。

And let's focus on a particular input length， call it in。Okay。

 so that would simplify our lives now that we're focused on a comparison based sorting method。

 one that doesn't look at the values of the array elements just in the relative order。

 we may as well think of the array as just containing the elements 1，2。

3 all the way up to n in some jumbled order now some other algorithm could make use of the fact that everything is small integers but a comparison based sorting method cannot so there's no loss in just thinking about an unsorted array containing the integer is at one to n inclusive。

Now despite seemingly restricting the space of inputs that we're thinking about。

 even here there's kind of a lot of different inputs weve got to worry about right so n elements can show up in n factorial different orderings there's n choices for who the first element is than n minus1 choices for the second element and minus two choices for the third element and so on。

 so there's n factorial choices for how these elements are arranged in the input array。

So I don't want to prove this super formally， but I want to give you the gist。

 I think the good intuition Now we're interested in lower bounding the number of comparisons that this method makes in the worst case。

 so let's introduce a parameter K， which is its worst case number of comparisons that is for every input each of these in factorial inputs by assumption this method makes no more than K comparisons。

The idea behind the proof is that because we have n factorial fundamentally different inputs。

 the sorting method has to execute in a fundamentally different way on each of those inputs。

 but since the only thing that causes a branch in the execution of the sorting method is the resolution of a comparison and we have only K comparisons。

 it can only have two to the K different execution paths。

 so that force is2 to the K to be at least n factorial and a calculation then shows that that force is K to be at least omega n log n。

So let me just quickly fill in the details。

![](img/ab89434b54ae68e7e2bb70bda2fb08ed_3.png)

So across all n factorial possible inputs， just as a thought experiment。

 we can imagine running this method in factorial times and just looking at the pattern of how do the comparisons resolve right for each of these n factorial inputs。

 we run it through the sorting method， it makes comparison number one and comparison number two。

 the comparison number three and the comparison number four。

 comparison number five and it gets back a zero than a1 than a1 than a0。

 maybe in some other input it gets back a1 than a1 than a0 than a0 and so on。

 the point is for each of these n factorial inputs， it makes it most k comparisons。

 we can associate that with a K bit string， and because there's only k bits。

 we're only going to see two to the K different K bit strings。

 two to the k different ways that a sequence of comparisons resolves。Now to finish the proof。

 we are going to apply something which I don't get to use as much as I'd like in an algorithm class。

 but it's always fun when it comes up， which is the Pieonhole principle。

The pigeonon principle you recall is the essentially obvious fact that if you try to stuff K plus1 pigeons into just K cupuppy holes。

 one of those cupbby holes has got to get two of the pigeons。

 okay at least one of the cubby holes gets at least two pigeons。

So for us what are the pigeons and what are the holes so our pigeons are these n factorial different inputs。

 the different ways you can scramble the integers one through n， what are our holes。

 those are the two to the K different executions that the sorting method can possibly take on。Now。

 if。The number of comparisons K used is so small that two to the K。

 the number of distinct executions， the number of distinct ways comparisons can resolve themselves is less than the number of different inputs that have to get correctly sorted then by the pigonal principle one cut gets two holes。

 that is two different inputs get treated in exactly the same way by the sorting method。

 they are asked exactly the same k comparisons and the comparisons resolve identically so it's one juling of1 through n and you get a 0。

1，101。 and it's a totally different jumbling of n and again， you get a 0，1，1，0，1 And if this happens。

 the algorithm is toast in the sense that it's definitely not correct because we fed it two different inputs and it is unable to resolve which of the two it is so it may be one permutation of1 through n or it totally different permation of one through n。

 the algorithm is tried to learn about what the input is to these K comparisons， but it has。

Exactly the same data about the input in the two cases so if it outputs the correct sorted version in one case。

 it's going to get the other one wrong so you can't have a common execution of a sorting algorithm uncrable totally different permutations。

 it cannot be done。So what have we learned， we've learned that by correctness。

2 to decay K is in fact， at least aninfactorial。So how does that help us but we want to lower bound K K is the number of comparisons this arbitrary stor method is using we want to show that's at least n log n so to lower bound K we better lower bound n factorial so you know you can do Sterlings approximation or something fancy but we don't need anything fancy here we'll just do something super crude we'll just say well look this is the product of n things n times n minus1 times n minus2 blah blah。

 blah， blah and the largest of those the n over two largest of those n terms are all at least n over two the rest willll just ignore。

Pretty sloppy， but it gives us a lower bound of n divided by2 raised to the n divided by2 Now we'll just take log base two of both sides。

And we get the K。Is at least n over 2， log based2 of n over 2。Also known as mega of n log n。And that。

 my friends， is why a correct determinist sorting algorithm that's comparison based has got to use analog log N comparisons in the worst case。



![](img/ab89434b54ae68e7e2bb70bda2fb08ed_5.png)