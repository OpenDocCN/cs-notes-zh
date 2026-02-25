# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P76：1 - Spring 2023 Discussion 14 Content Review.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

🎼发比发比。🎼Oh比。

![](img/ef4fa646be212e8def2cebdfe6813f05_1.png)

🎼And。

![](img/ef4fa646be212e8def2cebdfe6813f05_3.png)

![](img/ef4fa646be212e8def2cebdfe6813f05_4.png)

Hi everyone and welcome to CS6 UNB spring 2023's walkthrough of discussion number 14。

 which is about more sorting APAA a little bit more on Quicks which we covered last week in discussion 13 as well as a new kind of sort which is counting sorts and specifically we'll look more into ratingd sorts so some quick announcements before we begin the week 13 survey is due on Monday April 17 Project3 phase two is due on Monday。

 April 24th and there are going to be no extensions because we do have to grade and present these projects in lab that week homework4 is going to be due on Friday May 5th and also no extensions because we release solutions the next day okay。

So now let's get right into things。For content review first up。

 let's talk a little bit about what like a radix is as well as counting sort So a radix can be thought of as the alphabet or set of digits to choose from in some system properly it is defined as the base of a numbering system so the radius size of the English alphabet is 26 and the radis size of Arabic numerals is 10 so0 through9 inclusive and ras can be like really anything it's just like a set of distinct elements or like kind of like an alphabet right and I believe in lecture professorfessor H uses like the suite of cards like the club diamond heart sorry club D heart spade as an example that could be a radix of size4 and radix sorts work by using counting sorts to sort the list one digit at a time this contrasts with what we've learned with comparison sorts which compares items in the list directly and to build a little bit of intuition about this I'm going draw an example with the counting sort so。

Let's say that we are trying to sort the list9，2， one， zero， and nine。Okay， so。Here。

 if we were to use a comparison sort。For example， let's use selection sort。Let's say X selection。

 What we would do is we would。Go through the elements in the array and try to find the minimum element in our array right and wed go through and go through and we'd see that the minimum element in our array is 0。

 and we've sorted nothing so far。 and we found the minimum element in our entire list of elements we're trying to sort。

 So what we're going to do is we're going to swap the zero with the element in index 0。

 And what that's going to look like。Is this so we'd get zero219 and nine and we're going to repeat the process for the remainder of this array so you'll notice that what we did here is we compared the two elements directly or we compared the elements in the listed directly right we compared like nine to two and two to one and so on and so forth countuting sorts are a little bit different from that。

So an accounting sort。The ras of the elements matters right so in this example over here we just have single digit numbers right so our radix or alphabet here is going to go to be the numbers from 0。

1，2，3，4，5，6，7，89 okay it's only going to take on values within that range。

So when we use accounting sort。What we want to do is we want to have like accounts array。

So the counts array is going to be length R where r is the rate size and o。

The reason why we have that is we want a space in our counts array for every single possible element that we could see like as a distinct element right so you'll notice here that we have 10 elements in our counts array because the values in the array we're trying to sort can take on the number0。

1，2，3，4，5，67，8 or 9 that's 10 numbers total right and what we're going to do is we are going to go through every number in our array that we're trying to sort and basically tally up how many times we see that number so over here we're going to see the nine and we're like。

 hey I see a nine so I know that my counts array should have one。In index 9， okay。

 because this tells me that I know that there're going to be nine in numbers sorry。

 there's going to be a number9 in my count in my underlying array Then I move on I'll see that I see the number two great so I'm going to mark up。

Two over here and say that I have a two in my array  moving on we're going to mark a one on index one we're going mark a one on index0 right because we have a one in our array we have a zero array and then when we come back over here to our last element which is also a nine we're going to go over to our count array with nine see that there's a one there and we'll tally it up to two。

So and I'm going to populate the rest of this array with a bunch of zeros。

 which is like kind of trivial， but it's just so we can visualize what happens when we're actually counting things up at the end。

 so our counts array over here。Is basically like a representation of the original array that we have。

 but according to how many elements of each type are in our array so if we read it from left to right we'll see that there are 10 there's 1。

1 there's1，2 there's 0，3，04，05 so on and so forth，08 and there's2 nines so what we're going to do now is after we have our counts array is we're going to run through our counts array and for every index we are going to try to put elements into our sorted array so I'm going to say like sorted。

So when I start at the very first element of my counter array。

 this is representing the number of zeros right we'll see that there's a one in position zero which tells us that there is one0 and the array that we're trying to sort so what I would do here is I would pop in a zero as the first element of my sorted array right likewise I'm going to move on to index one I'll see that there's one1 in my array that I'm trying to sort so I'm going to pop the one next into the array that's sorted okay do the same thing for two I'll go to index two see that there's one two and I'll pop the two。

Into my sorted array next and then trivially we're to go through the three4。

 five six there's going to be 0，30405 so we know we are not going to add any threes fours or five six or sevens or eights into our sorted array then finally when we get to the nines we'll see that hey I have two nines so that means that i'm going to put two nines in my sorted array。

And that is how I sort array with counting sort so you'll notice here that the only reason why this counting sort really works is because when we set up this problem where each of the digits was only a single digit we established that our ratedic size or the size of our alpha or the total number of distinct elements that our values in our to sort could take on there were only 10 of them right and we knew that those 10 numbers had an inherent ordering we know that zero is less than one one is less than two so on and so forth right until we get to9 so the 0123456789 these numbers are like the order of numbers from least to greatest sequentially so when we do the counts array we can read off from left to right starting from index zero to tell us。

In what order we should put the elements in our， and that's how counting sort works。

So a little bit of intuition building before we move on to rating sort。

 which is like the core the core focus kind of counting sort that we use in this class the runtime of the sorting algorithm with counting sort that we just did is dependent on two things right so first of all。

We couldn't get around going through every single element in our sort in the array we're trying to sort right so we know that n is going to have some contribution to our overall runtime right we have to go through every element that we're trying to sort right then after that when we go through the array we're trying to sort we put it into the counts array。

😡，That takes end time。 and then from there we have to go through our count array and for every element in our count array。

 which is dependent on rated size， right？We have to figure out where to put each element we have like10。

 we have 11，1 two，0 three so on and so forth right and that'll tell us the positions in which we should put elements on our sorted array final array right so。

Basically， what that means is after we do this linear work from the counts， Oh sorry。

 when we after we do the linear work from putting the original array into the counts。

 we have to pass through the counts， and that's dependent on us doing our work， right。

 because the counts array is of length R。 We want one index or one position for every valid。

Valid and possible。Distinct element that the items in the array we're trying to sort could take on。

 right， So that's going to give us n plus R runtime for ratingdix。 Oh sorry。

 enough for ratingd sort for counting sort， okay。So now how do we transpose this over to Radix sort so counting sort is kind of like a super set of Radix sort right like a Radix sort is a kind of counting sort and how it works is it sorts numbers by sorting them by digit from the lowest digit to the largest digit we'll see an example of this on the worksheet but basically what we mean by this is LSD stands for least significant digit so what that means is that when we're sorting by LSD we only care about the smallest digit like the one's place in this example right so if we have a list of this numbers and we're trying to sort them with LSD Radix sort we completely ignore I'm going highlight in green we completely ignore what is to the left of the ones place in each of these numbers because basically we want to sort only by the least significant digit first then we sort by the next most sorry the next least significant digit。

😊，Okay， and we'll see an example of this in the works， it's okay if doesn make sense right now。

 but basically just know that when we start off with LSD rating sort。

 we're only concerned with the smallest possible digit place before we move on to the next digit place Okay so the general runtime of LSD rating sort is going to be pretty similar to what we saw about with counting sort right we saw n plus R but over here in the general runtime。

 we see that there's a w and this w term is used to represent the width of the longest key in the list right so in this example over here where we have these five numbers the longest key in the list they're actually all the same length here but they are。

😊，3 digits wide， right，1，20，923。 There's three digits in this。 So in this case。

 we would say like W is3。And then n is representative of the number of elements being sorted。

 so we would say that like n is5 here and R is the radix size and so when we are sorting like regular decimal numbers。

 our ratingdius size is just going to be 10 right because we know that the numbers can possibly take on values from zero to nine inclusive right one more thing that I would like to point out is that LSD Radix sort is basically just regular counting sort except we it's also dependent on the width of the longest key in the list and the reason for this is that in LSD Radix sort。

Since we have to compare the numbers like like。Place by place if we were trying to sort for example like 23 and 155 we use a tactic called left padding so basically we would left pad the 23 with a zero so that they're all approximately the same with right so we don't have to deal with like nasty edge cases and that's why we use W here okay。

Now for MSD rating sort， it's a lot like LC rating sort。

 but instead of starting from the least significant digit。

 we want to start with the most significant digit so we sort the numbers by sorting them from the largest digit to the smallest digit and again we'll see an example of this on the worksheet。

 but just to illustrate I'm going to underline the most significant digit。

So in this situation if we were trying to sort these five numbers。

 we only care about the hundreds place here the one， the9。

 the one the three and the one right once again I'm going to highlight these to represent that we're completely not paying attention to them in the first iteration of MSD Rad sort we don't care what the rest of the number looks like just the hundreds place here and something really interesting about MSD Radic sort that distinguishes it from LSD Radic sort is that you'll notice that the general runtime we use big O of w times n plus R so in LSD Radic sort we use a big theta which meant this bound as type which means that it is upper and lower bounded by the same runtime right so the idea behind LSD Rad sort is because we have to like left pad numbers and we're starting from the smallest number positions possible there's no way for us to kind of like exit early from LSD Radix sort we have to go through every single digit of every single number there's no way for us to be like oh okay I saw this ordering and we're done because we don't know what lies ahead and really what determines the order。

Of a number is like the most significant digit， basically， right？

That's why we can't exit early with LSD Readsort。But for MSD ratingd sort。

 we use a big O to describe the general runtime because MSD ratingd sort can exit early。

 so as an example， I'm going to draw let's say we had5，5，5，6，7，8，2 and3 and like three，4。

5 if we were looking at just the most significant digits here in this list we're trying to sort。😊。

Well， after one pass we're basically done right because we see that these are all distinct right there's a one。

 a two， a three， a five and a six and so we don't have to tie break beyond that right if we pad all the numbers correctly we don't have to tie break beyond this at all because we know that hey the hundreds place when they all line up they're all distinct so I know that after one pass I can get my numbers in sorted order just with one pass of counting sort and so that's why we see that MSU rating sort can kind of like exit early okay and that's why I use big O to represent the runtime。

So now let's shift gears a little bit because we talked a bit about Quicks last week。

 but we didn't really talk about the other partitioning schemes beyond who so there's a kind of partitioning scheme that is not in place but it is stable usually when we talk about Quicks we talk about unstable Quickst because we use who are pitch partitioning because it takes a little less space but in threeway partitioning or three scan partitioning it's a simple way of partitioning an array around a pivot you do three scans of the list first putting in all elements less than the pivot then putting in elements equal to the pivot and finally elements that are greater than the pivot and this technique is not in place but it is stable so usually we create like a separate array for this right so as an example let's just。

Let's just pick the first element to be the pivot， okay？

So what we would do in three scan partitioning I personally think that three scan partitioning is the most intuitive partitioning scheme for QuickSo。

 but maybe you think a little bit different， but and what we're going to do is kind of we're going put the three into our array okay。

 and I'm draw barriers around it to represent like this is the split for elements that are less than three and this is the split for elements that are greater than three。

😊，So what we would do is let's scan the array for elements that are smaller than our pivot， okay？

So what I'm going to do is I'm going to go through the one， the two。

 the five and the floor and I'm going to see that the one and the two are less than the three so I'm going to pop them into the rate to the left of the three and when I do another scan for for elements that are larger than the three。

 I'll go through one through five and four， one，2， five and4 and I'll see that the five and the four are larger。

😊，Then my pivot so after my three scan partitioning。

 this is what my array is going to look like and after I partition this remember that quickword is recursive so I'm going to recurse onto the left and right parts sorry left and right sublists of my partition list and do the same thing and repartition those lists and call quickword on those。

So this is like a little bit more intuitive to me personally than who partitioning which we're going to review so horror partitioning is an unstable in place algorithm for partitioning we use a pair of pointers that start at the left and right edges of the array skipping over their pivot so once again using the same example let's say this is our pivot。

😊，What we want to do is we're going to have a left and a right pointer we're gonna to call these L and G to represent less than and greater than and also because Professor Hugg uses LNng in lecture so let's just keep it a little consistent here we're going to use we're gonna put the L pointer at the left edge of the array that isn't the pivot and we're going put the G pointer at the right edge of the array that isn't the pivot okay so the left pointer likes items that are less than the pivot and I mean strictly less than the pivot so no less than are equal to and the right likes items that are strictly greater than the pivot and then we have the pointers to walk toward each other until they see that something that they don't like and once both have swap oh sorry。

Once both pointers have stopped swap their items and then advance the pointers again towards each other the process is going to complete once they have crossed and when they have crossed we're going to swap our pivot with the pointer that originated on the right and then we're done with one iteration of horror partitioning okay so let's draw out the example so I've just initialized my left and right pointers over here and what each of these pointers arere going to do is I remember that our left pointer likes items that are smaller than the pivot so I'm going to look at my left item and see that hey I'm on a one I like this because one is smaller than three so what I'm going to do is I'm going move on to two。

😡，Right， and then when I move on to two。Oops， when I move on to two， I'll once again。

 take a look and be like， oh wow， I'm on a two， two is lesson than three， I like this。

 Let me keep moving。Now when I get to five， I'll be like wait a second。

 the left pointer does not like 5 because five is greater than3。 Oh， I'm going to stop here。

 so now let's try to walk our right pointer。 Okay， so our right pointer。

 remember it like items that are strictly larger than our pivot so we're going to try to walk over。

To the left from four so I'm going to look at this four and be like hey I like this number because four is larger than three so what i'm going to do is I'm going to move on once again i'm going to take a look at where my right pointer is pointing it's pointing to five and be like oh I still like five because it's strictly larger than three and I'm going to move on。

And I'm going to stop here because。The pointers have already crossed。Okay。

 so we've reached a point where our pointers have crossed and so now we need to stop and complete our process right and we complete our process by at this point when our left and right pointers crossed we're going to swap our pivot with the pointer that originated on the right so what that's going to look like is。

I am going to swap the two and the three so that two goes here and three goes here so my list after one partition is gonna be 2。

1，3，5，4 and basically at this point we'll be like yeahy we have our pivot that was three and now again because quicksort is recursive。

 we need to do the same partition on the left and the right subli because over here we've established that the two and the one they're smaller than three right but we don't know if they're already sorted likewise over here we know five and four are larger than three but we don't know if they're already sorted right so we just need to quick sort and partition these subli recursively until we get to the base case and then we propagate back up and then we got a sorted list right and that's horror partitioning for quicksort。

Okay and the final slide that we have here is just a summary of comparison sorts which was actually in discussion 13 but we've now added a column about in place so oh really quickly remember that comparison sorts are not the same thing as counting sorts right remember that in comparison sorts we're comparing elements in the list directly versus counting sorts we have a set rads that has an inherent ordering that we know ahead of time so we don't really need to compare elements like one by one exactly anyway so the in place column over here in this class we define in place to mean that an algorithm takes less than or equal to logars logarithmic space so。

You'll notice that most of these are in place merge is usually not in place because you'll need to like create extra arrays and quicksort with horror partitioning uses login space。

 which is the upper limit of what we would consider in place so we say that quicksort with horror partitioning is in place but if we use quick sort with like three scan partitioning which we discussed above it's not going to be considered in place because we need to allocate extra arrays for like the scans right so something down here a note。

😊，Comparison sorts cannot run faster than N log in n in the average case。

 so I know over here in insertion so and heap or and the best possible cases these are linear。

 but we're talking about like the average case right because the insertion so and heap sort cases when it's the best case are like highly specific scenarios so in the average case we can't really run faster than N log N and the reason for this and I'm not going to go too deep into this but you can like learn more about it if and when you decide to take CS170 when I think you will actually do a formal proof of as to why comparison sorts can't be faster than N log n but like the very like basic reason behind it is that when you make a comparison in your。

When you make a comparison in your underlying array you eliminate at most half of the possiblele probe permutations when you compare these two elements。

 like for example， if you decide that a should come first。

 then you've eliminated that all other permutations where B came first right so that has to do with like elimining half at each step and then that's like logarithmic I'm not going to get into like the nitty gritty of that but this is in comparison to counting sorts Okay so in counting sorts we established above that the runtime of like for example。

 L Z rate sort is theta of W times n plus R right if r is like a really small number and w is also a really small number then we could potentially get like。

IBa like a linear time sort right on a list。We're going to discuss the pros and cons a little bit more during well as we go through the worksheet。

 but that's something to definitely keep in mind of like comparison sorts can be faster than N log N。

 but count sorts there are a select few scenarios where you might want to use a accounting sort over comparison sort but also vice versa and that's going to be it for our content review。



![](img/ef4fa646be212e8def2cebdfe6813f05_6.png)