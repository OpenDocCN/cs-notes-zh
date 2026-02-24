# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P71：3 - Spring 2023 Discussion 13 Question 2.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

🎼发明发明。🎼Ba比。

![](img/e59cfdb478426b1be21bd367f0815de7_1.png)

🎼And。🎼Yeah。

![](img/e59cfdb478426b1be21bd367f0815de7_3.png)

All right， let's move on to question two it's called Crystal has been waiting for this little fun fact about this question The reason why is this is called this is because when I first joined staff in spring 2021 we were all on zoom and we had no idea how tall the like the other staff members were and there was a joke that went on about making a question an exam question on quick sort where we would have like the short people on staff be like the worst pivots and then there was a lot of uproar about that because I had a friend who was very sure I think like5 zero or something and so she was like I don't want to be exposed and that was the inspiration for this question because I finally wrote it after waiting for someone to write it for like two or three years anyways so。

Andcent of this problem is Claine Ada2 alumni 61 B Ts are trying to sort the Ts by height so they can snap a photo can you help them out over here。

 we have a class public class T it has a name variable。

 a height instance variable and then a constructor that just like sets the name in the height based on whatever you passed in so we want to implement T comparator below such that it compares to T's height recall that compare returns a negative number when01 is less than02 positive number when01 is greater than02 and0 when they are the same okay so a couple of things I want to address before we get started with this question is that it's pretty common and you know you may even have done this in when you were doing project2 B with Nornet when you are dealing with like a popularity of words right you might have had to create a comparator。

😊，So comparators are really useful for us when we are trying to compare reference types in particular like analyst right we're trying to sort reference types and the reason for that is remember that like so far in the discussion in question one and during content review we were sorting numbers right but we won't always be sorting numbers like over here we're trying to compare Ts by height but Ts themselves are objects in Java they're not inherently numerical right so that's where comparators come in because they're really helpful for help like telling Java basically like I want to sort this collection of elements and here I'm going to tell you exactly how I want these elements to be sorted even if they aren't inherently numerical and value right and so the whole point of this compare function is for us to generate a numerical value that actually can be compared okay。

😊，So over here we have public class T comparator implements comparator and we see that this is parameterized by something actually we don't actually need to parameterize a comparator。

 but it makes our life a little bit easier because then we don't have to cast things from an object right so here I'm saying that I want to implement a comparator over TA objects I know that the kinds of objects I will be comparing are going to be of type TA so likewise in the compare function over here when we're comparing01 and02 I know that what we'll be comparing our Ts。

😊，ok。So now let's get into the details over here。 Compare returns a negative number when01 is less than02。

 Po number when01 is greater than02 and 0 when they are the same。

 So when we say it returns a negative number。 It could be any negative number。

 but I think typically for the purposes of。Like Java and just code cleanliness。

 we usually default to negative one and positive one when we're talking about compare returning a negative number and a positive number respectively and you'll notice that I put01 is less than02 in quotes because remember O1 is a T and O2 is a T right these are not numbers inherently we need to find some way to compare them numerically So what we're going do is we can do something like。

If。01 dot heights。Is less than02 dot height than 01 is shorter than 02， right？

So here we're going to return a negative number。Otherwise， if。Oh wondernda系。

Is greater than 02 do height， which means that 01 is taller than02， right？

That means that we want to return a positive number。And otherwise， if they're the same height。

 then we could just return。Zero。Right。😊，ok。Okay let's move on to part B。

 so Jenny suggests that we use Quicks with the comparator we just define above given the following list of Ts who would make the worst pivot and what about the best pivot。

 so as a reminder that when we talk about QuickSo Quicks is really unique because it uses the idea of a pivot or a partition to split up your list right so the pivot would just be an element in the list and hopefully when you partition you would have elements to the left of the pivot which are representative of the elements that are smaller than the pivot and elements to the right of the pivot which is representative of the elements in the list that are larger than the pivot and in the best possible case。

You want to pick a pivot every single time we recurse in quicksort such that when we recurse we approximately split the list that is not containing the pivot into two approximately equal length lists right so in a sense of like let's say I had like one。

5，3，4 and2 the best pivot that we could pick here is three right because then we could evenly split the list into like one two and five。

4 right and so when we recurse on quick sort the subproble each becomes smaller right so that's like the best case scenario where we pick someone like approximately in the middle right versus what about the worst pivot so if we chose a really bad pivot actually let me go back to this example。

In the bad pivot， let's say we chose one to be the pivot。

So to the left of one we would want all elements that are smaller than one and to the right of one we would want all elements that are larger than one right but there's no elements that are smaller than one in this list so we would put everything into our right list and this whole mass is like unsorted right we know that they're all larger than one but we don't really know much beyond that right so that's when QuickSo becomes a little bit nastier and a little bit slower when we pick a bad pivot so。

The idea here is that the best pivot is one that will give us n log n runtime right we approximately split the subproblem into two equal halves every time we run and recurse on quicksert and the worst pivot would be when we choose someone whos at like the extremes in terms of the ordering of the list right either the minimum more than maximum and in that case when we recurse the problem instead of breaking in half breaks from n to n minus1 to n minus2 to n minus3 which gives us n squared runtime right so I'm just going to make a note about like best would be like median ish。

And the worst would be extreme。 So the maximum。And if I were to draw out all of our TAs over here by height and you'll notice that I used your TAs from this semester and hopefully they've been very helpful for you to in office hours you recognize their names。

But yeah， so let's say I wrote out everybody is u。Oops， that should be  Kenneth。Heights， Aitsha 6。

3 is seven。Eric and Austin are eight。And then we have。呃Ddy。No。And Sherry。Oops。

 I you like Rotarys name really badly。So here I have all the TAs in sorted order by height。

And when we look at the worst case， I'll put box their names so audit and sherry would make pretty bad pivots right because they are the maximum of minimum height of the list respectively so for example。

 if we used audit as the pivot and we are trying to partition。

 we'd see that everyone else in the list would end up in the right partition of audit because there's no one who's shorter than audit。

 right。Likewise with Sherry， if we tried to partition on Sherry。

 everyone would end up in the left part of the partition because there's no one taller than Sherry。

 everyone is shorter than sherry right so that would break the problem into an n to n minus1 to n minus2 like kind of recursive work done at each level so that gives us endd work at the end。

😊，As for the like the best case scenario， we kind of want the we or not we kind of we do want like the most median values as possible because we know that they'll split the list approximately evenly right so we want the media values in this list unfortunately because there's 10 people in this list we don't really have a median value。

But the best answers here would be like the middle two values and the middle two values under seven and8。

 which is covered by three people， so I'll box them in light blue。 so Sri would be a good pivot。

 Eric would be a good pivot。 Austin would be a good pivot because they all approximately separate the list into equal numbers of elements right so for example。

 if we look at Sri we'd see that I know I like trivially sorted this list already。

 but it's just for us to easily visualize if we took Sri as the best or as the pivot here we would separate audit Haley Kenneth and An niche into Sri's left partition and Eric Austin Ju to Noan Sherry would go into Sri's right partition So it's approximately down the middle and that's how we get that subprom to break into haves right which gives us that nice N log and runtime。

😊，Okay。Okay， so now when we move on to Part C， Austin points out that even though he got in line after Eric。

 he ended up in front of him in theest sortred list produced by Quick sort because which he doesn't like because that makes it seem like he's shorter than Eric。

 how might we ensure that Austin ends up behind Eric so？If we come back up here。

 we'll see that we'll actually highlight their names in green， Eric and Austin。

 Austin got in line after Eric， right， whether're the same height they both have a height8。

 but after Quicksort， we ran Quicksort， Austin ended up in front of Eric。

 which is not something that we want， right？😊，So if we want to preserve the ordering of same valued elements in the original collection when we sort it。

 we should use a stable sort。And rese stability when we talked about it is basically this idea of like if we have two duplicate elements in our list。

After we sort it with the sorting algorithm， are we guaranteed to have those two elements in the same original order in the list and you'll remember that Quicksort is not stable right and this has to do with the fact that when we swap things it's not necessarily like accounting for the intermediate elements right we aren't guarantee that we're swapping over elements in the middle that or basically aren't guaranteeing the ordering of the elements in the middle with respect to what's being swapped over those elements right and an example of this I talked a little bit about it in content review which is with like selection sort where you don't really know what you're swapping over when you like move the minimum element into the first position in the array right。

So we could use a stable sort， so some examples of stable sorts would be like insertion sort。😊，Or。

Merge short。And technically speaking， we could use like a stable quick sort。

 but we don't use it that often and like the un sorry the stable quick sort that we use uses three way scan partitioning。

 which we'll talk a little bit more about next week， so I'll say。Quicksort can be stable。

But not with Hs partitioning。Which we typically use for quicks， okay？Now in part D。

 our TAs have just been sorted by height， but suddenly Angelina and Am come running in late。

 which sort will do the most minimal work to get the two of them in their correct spots and what is the additional runtime it will take not including the runtime for sorting all the other TAs phrase so what we mean by this is I'm just going to actually copy over this list。

And so let's say， you know， we're about to take this photo。 They all got in high order。

 This is great and then。😊，Autham and Angelina came in。And we have no clue what their heights are。

 right。And now we need to sort our list again， basically。

 which is kind of annoying because it's like thing。

 we pretty much already sorted like everyone else besides Ottoman Angelina， right， oops？

I'll just rewrite that as fine。We pretty much sorted everyone already besides Art and Angeline。

 oh my God， it keeps disappearing on me， that's fine。

But everyone else is pretty much in sorted order and it's like pretty annoying for us to have to like go through everything and resource everyone。

Right， so basically the question that we're really asking ourselves here is like is there a sort that will take the least amount of time for us to do if our list is pretty much already sorted right so let's run run down the list the possible source that we know so selection sort selection sort runs consistently in n squared time right it doesn't matter if your list is pretty much already sorted。

 you still have to parse through the rest of the like the entire array every single time in order to find the minimum value and put it in the correct spot right because we don't know where the minimum value will be in the rest of the array So selection sort is not really helpful for us merge sort。

And quick sort are two interesting ones because they kind of they they。

Mergehor and Quicksort they recurse indiscriminately right Merchhor and Quicksort do not care if your list is basically already sorted because it's just going to try to split the list anyway right it doesn't really matter so Quicksort and mergesort are like going to run an n log n at the very fastest right the both of them on the list containing everyone here。

Then if we consider something like He sort， He sort is also not necessarily going to be super great and it He sorts best case runtime。

 which is。Which is linear comes when I believe everything is already。

 I believe when everything is a duplicate， I'm I hope I'm not just speaking there。

 but if I recall correctly it's when everything is a duplicate and so you don't really need to like bubble up and bubble down。

 you can just keep popping off elements， right？So heap sort is not is not super great in this scenario either because you can imagine that putting things into our heap when they're not all duplicates and reheapifying every time is still going to give us like M log n runtime right so that leaves insertion sort So remember that insertion sorts runtime comes based off of the number of swaps that it has to do right and in the very worst case scenario insertion sort has to make n swaps then n minus1 swaps right in a completely reversed order list which gives an n squared time。

 but that also means that in the best case we have the kind of the con scenario of the completely reverse list right in the best case we have a completely sorted list or an almost completely sorted list right and let's talk a little bit about。

😊，The intuition behind this。 So if we were to look at our list over here。

 let's not include Aum and Angelina if we were trying to insert and sort this already sorted list。

 we'd look at audit， see that audit doesn't need to swap Haley does not need to swap left Kenneth doesn't need to swap left so on and so forth right we'd make one linear pass all the way to the end we'd get to sharerry and be like Sherry does not need to swap left we're done this list looking at it took us the linear time because it was almost already in sort this was already in sorted order right so in the worst case。

 let's say Autum and Angelina are the two shortest people on staff Okay let's say as an example Autum is high zero and Angelina's height like negative one I know you can't have a negative height but just for the purposes of this example let's just do that okay。

So。If we had our original list over here and we tacked on Autumum to the end and Angelina after。

 in a very worst case scenario， we'd have to swap Autum all the way back to the front of the list。

Right so that would be edge swaps basically right and then when we went to Angelina。

 we can do the same thing， we look at Angelina。Id swap all the way back to the front of the list。

 even in front of autumn。Autumn worst case。Would be end swaps。Right， Angelina's case would be。

N plus one swaps， right， And that's just like a trivial constant that we add because our on is here。

 right， So when we add these two together。We get approximately two end swaps， which is。

En time right it was just an additional time that it took on top of sorting all the other Ts first right because we sorted all the other Ts first and then when we tack Angelina on on at the end at the very worst they were going give us approximately two end time to get to the front of the list right and that's where we get this nice like linear time additional sort which is great for us right and that should be the end of question too。



![](img/e59cfdb478426b1be21bd367f0815de7_5.png)