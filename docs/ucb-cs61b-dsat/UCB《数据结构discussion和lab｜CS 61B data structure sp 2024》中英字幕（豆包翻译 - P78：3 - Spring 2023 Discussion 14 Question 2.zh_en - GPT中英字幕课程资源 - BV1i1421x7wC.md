# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P78：3 - Spring 2023 Discussion 14 Question 2.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

🎼发明发明。🎼Ba必。

![](img/0cc805ad1ab98dd8ab1ade735c9617b1_1.png)

![](img/0cc805ad1ab98dd8ab1ade735c9617b1_2.png)

![](img/0cc805ad1ab98dd8ab1ade735c9617b1_3.png)

All right， let's move on to question two， which is all about Radix sort and part A we're asked to sort the following list using LC Radix sort with counting sort。

 show the steps taken after each round of count sort the first row is the original list and the last two rounds are already filled for you okay so。

嗯。Really quickly remember that in El Ra sort we're only concerned with sorting the least significant digit at a time right we'll look at the least significant digit then the next least significant digit and so on and so forth until we fully sorted the list right so what we want to do is we only want to focus on the one place here in fact let's just pretend。

Like。We don't see any of the rest of these numbers， we only see what's in the ones place so。

What we're going to do is take a look at all these numbers that we see。 So we see a2。

 We see a5 a5 and a6。 So let's reput these numbers in order according to just the one's place。 Okay。

 so let's do 43，0，9，2。3，0，3，9，5。3。0，3，2， oh， sorry，3，1，5。 and then 3，0，3，2，6。 Okay。

 so you'll notice here that this is pretty interesting because why did we put a 43000 in the way beginning。

 Like we， of course， know that 43000 is going to be much larger than these 30000 right。

 and it's gonna to it should end up in the last element of our array， right。

But you have to remember that again we only looked at the one place we did not care about the other places at all and we're in an intermediary step of our ratingdic sort we're not done yet right we just need to look at all of the place positions before we finish sorting right which is why it seems super out of order Another thing to note is that over here you'll notice that there was a five and a five and I put the 395 before the 315 because that was the original order in which they were in in the original list and this is kind of a spoiler for part C but that's totally okay but I'll talk a little bit more about it then but you want to keep these numbers in order because we want LSC to be LC ratingd sort to be stable okay。

So， no。嗯。What this is going to look like is we've already seen the ones place great so now we only want to focus on the1 place right because it's the next it's the next least significant digit that we haven't already seen right so at this point you can be confident and be like yes we already sorted the ones place so I know that relative to each other at least the ones place has been sorted so we don't really need to care about the ones place anymore let's just focus on the1s place so what we see here is we see a one a two a9 and a9 so let's reorder our array so i'm going to put。

😊，33，1，5，33，2，6，43，092。And 3395 and again， remember notice that I broke ties by putting it just in the order in which the numbers already were in。

 okay？Then next， we've already seen the Ts place， let's move on to the hundredth place。We see a zero。

 a three， a three and a three oof， okay， that's fine， let's just resort based on that。

So we're going to put 43092 and then since these are all tied。

 we'll just put them in the original order they were in。Oops。

 I did not mean to write the same number three times in one second that should be 3315 3326 and 3395 Okay so we're at a point where we filled in note table of the remaining blanks in the table but let's walk through the rest of the table anyway okay so when we get to line three what we want to sort on next is the thousands place。

We see a zero a0 a0 and a three great mor ties， so we're going to put the 3315 over here。

 the 3326 over here， the 3395 over here and we have a three over here and that's going to be in the 420092 it's going to be the last position in our way。

😊，So you might ask yourself like wait a second why why do we have this fifth line because it's literally just a repeat of line for right well you need to remember that in LSD ratingdic sort there's no way for us to like exit early we have to go through every position in our digits in order to fully confirm and verify that we do in fact have these digits in sorted order and as an example to think about this let's say we got to this point in line for and we've only seen these the thousands place right？

Oh I don't know why I drew them under the00 sorry， but we've only seen the thousandsth place。

 if we tried to stop here and call it a day， we don't know if this is like a five。

 we don't know if this is like a seven right they might all have like the same numbers after the 10。

000 place but we have no clue what is actually in a 1000 plate right and that plays a really large role in determining the overall order of the numbers in our underlying list。

Which is why in line four we need to finish out by looking at the 10。

000 plates of each of the numbers。Even though these are all in sorted order like our computer remember a computer is not very smart a computer only can do exactly what you tell it to right whatever program you tell it to do so in that case we can't exit early and we have to check the 43000 and the 30。

000， we have to check the 10000th place which is why we have this extra line which looks like a repeat of line for okay。

Now let's move on to MSD rating sort。So we want to show the up takingking after each round of counting sort the first row is the original list and the first three rounds are already fulfill for you so if we start out looking at the most significant digit over here right。

😊，And we saw it based on just the most significant digit。This means that we would see a three。

 a three， a four， and a three， and we'd pop these first three in the order in which they were seen into the first three elements of our list。

 and we have the 43，000 number in the last element of our list。

So you'll notice here that there's like a bar I think Professor Hugg refers to as a barrier。

 but basically the idea here is like oh， since the most significant digit when all of our digits are like the same with right since like a distinct sequence of most significant digits would already tell us like an inherent ordering we already know that the 43000 is sorted in the last position right because we sell a three a three a three and a4 the four is the only one that's distinct and we know the four is the largest of all of these numbers right so we know for sure that it's going to end up in the last position of our array and we're going draw like a barrier here to represent like hey I know this 43000 should be in the last position no matter what。

Because we're starting from the most significant digit right so in subsequent runs of MSD rating sort don't include the 43000 because I don't want to get looped into this and look at like the other digits in my in my number because I know the 43000 is already like in place okay so what we're going to do next is let's look at the next number over so we saw the most significant digit let's now look at the thousands place so we see a zero zero and a zero great that's not super helpful so we're just going copy over those numbers again right？

Because we can't really discern the order based off of just the zeros right and once again we don't touch the 42。

000 because there's a barrier there。Then when we come down here to line three。

 we see that the next number we're looking at the hundreds is a three we see a three and we see another three great so we can't really make any assumptions off of that。

 but what we're gonna to do now is we want to look at the next number right the next number in the tense place over here because we've established oh I know I wasn't very consistent about it in2a but in2 B in the the given lines if the number is underlined that means it's already been sorted by those numbers so by with the time we get to line three we've already sorted these numbers by the first three numbers so basically what this means is that in line four we need to consider。

😊，The1s place， right， the next most significant digit。So here what we would do。😊，Is we would see。

That we have a nine， a two， and a one。That's great for us because a1 a2 and a9 they're all distinct。

 right， So now we can actually put our numbers into order。 So we have a 33，1，5， you a 33，2，6。

 and we have a 30。😊，3，9，5。 and trivially， we had this barrier here already。And at this point。

 we can actually stop execution of MSD ratingatic sort because we're done， right because？In index。

In sorry not index in the1 place we had distinct numbers and we know that in our rads we have an inherent ordering right like one is less than two2 is less than9 and if we know that we've sorted everything else up to that point equivalently and we see these distinct numbers then it can stop right because it literally does not matter what comes after the one here it doesn't matter what comes after the two here or the nine here because we know that the1 place takes precedence when we're sorting numbers right because it's more significant then whatever comes to its right so we actually finish our MSU ratingdix sort here and trivially you could copy over the rest with like barriers of their own but we're just going stop here for now okay。

Now， let me move on to Part C。We want to give the best case runtime worst case runtime and whether or not the sort is stable for both LSD and MSD ratingd sort。

 So assume that we have n elements， a radix R aka the alphabet right that tells what the size of our alphabet is at a maximum number of digits in an element W So this is a little bit tricky but let's start off with like I think what I would consider like the more intuitive case So an LSD ratingd sort I was talking about in 2 a is like we had to go through every single digit in each number there is no chance of us exiting early because the most significant digit is really what determines the ordering of the list ultimately but we start at the least significant digits。

 we have to go all the way to the end So that means there's no chance of us exiting early and we have to do the same amount of work in both the best in the worst case for LSD ratingdix sort。

So that's why our LLC Rad sort is going to take w times n plus our work in both the best and the worst case。

So to intuit a little bit of where we got these numbers in case you didn't see the content review is that because LCC Radix sort is a accounting sort。

 that's where the n plus R comes from right we have to go through every number in the list and put each of those numbers in their appropriate buckets and by bucket I mean like whichever radix they belong to and then so that's going to take end time right and then we have to go through the counts list with all the buckets to tell us like how many elements of each type there are so we can like allocate space or allocate like the inices directly for where we should put like the zeros and the ones and twos right because we know that there's an inherent ordering in our radix so that's going to take our time。

And because we are doing LSD rate so we're only sorting one digit at a time。

 we have to do this for all w digits in the in the elements right so a w is the maximum number of digits in an element so。

This is where the runtime comes from for the best and the worst case and I kind of gave it away earlier but LLC ratingd sort is stable and the whole sh with like LLC RadO is that it really depends on the sort being stable right because we start from the least significant digit and we work our way up to the most significant digit。

 it doesn't really make sense for us to not have a stable sort because that would kind of ruin the whole point of LSC ratingd because we're only building it up one digit at a time from the least significant digit right？

ASD rate sort， on the other hand， is a little bit trickier。

And I'm just going to say right now that MSD Radis sort in this class at least it's stable。

 we don't really talk about the unstable version of MSC Radic sort， but I guess it could be。

 especially if you have like an unstable subroutine。

 which we didn't really talk about in this discussion but it's the idea that like because MSD Radic sort can exit early it's a little bit parallelizable in that you can break it into subroutines but we're not going to get into the nitty gritty of that。

 but for MSD Ra sort in the worst case scenario you have something similar to LSC Radic sort which is you have to go through every element。

In your array every digit in each number right and we also have to make that pass over the counts array。

 which is of size r the radix right so that's like the worst case scenario。

But in the best case scenario remember how in part2 B we like exited early。

 we got to this point and we saw that hey all these numbers are distinct in in the like most next most significant spot that we haven't already seen were done right so in the best case scenario I gave an example of this in the content review but let's say we had the numbers111555333222 and444 if we were running MSD ratingd sort on this。

We'd see a one a five a three a two and a four and we'd be like hey I'm done because these elements are all distinct so I know that whatever comes after the hundredth place of each of these numbers does not matter because I know that one is less than two two is less than three three is less than four four is less than five so I made one pass through my away and bound it's over i'm finished so。

😡，In that case we would only need to do one pass right and one pass of counting sort is going be n plus R right we only need to do that for one digit and that's where that special best case runtime for MSD rating sort comes from and that's the reason why the MSD rating sort when we describe its runtime generally we use big O to describe it we say big O of w times n plus R instead of as opposed to LSD rating sort where we could fully bound the general case runtime with big theta of w times n plus R okay。

So now in part D， we just saw above that ratingd sort has great runtime with respect to the number of elements in the list。

 given this fact， should we say that ratingd sort is the best sort to use overall and to like really like really get into this point as an example。

 we know that comparison sorts are going to take like n log n。😊，On the average case， right。

 we're ignoring the fact that like insertions sort might get like a really nice runtime on an already sorted list。

But we know that comparison sorts are going to run an un N， right？

And as an example of what we're talking about with Rad sorts having really great runtime is let's say I have a list that only has single digits。

 so maybe there's like a five and a nine and a one。😊。

And then like an eight or something like that and let's say that there are 20。

000 elements in this list of this list of only single digits okay。

 so if we were to use a comparison sort that would give us a runtime of 20，000 log 20。

000 and this is basically base two， but we're not going to page10 the base here， right？And if we did。

 for example， like MSD Radix sort， actually， let's do LSD Radic sort because it's a little bit slower in certain cases。

 if we did LSD Radix sort。呃。Okay， L Rax sort。是。Its run time in the worst case is going to be。

N plus r times w right and if we sub our numbers w would be one because we have like single digits only right so the width of the longest word in our list is going to be one。

N is 20，000。And our since this is again only single digits。

 we know that the rating size is going to be 10， so when we calculate this out。

 we'd get something like 1 times 20，000 plus 10， which is like 20010。



![](img/0cc805ad1ab98dd8ab1ade735c9617b1_5.png)

So when we compare these two numbers at the end， 20010 versus 20，000 log base two of 20，000。

Like LSD Radix sort kicks comparison sort completely out of the ballpark right like it's way faster than comparison sort so going back to this like example that I just gave where we see that LSD Radix sort like absolutely crushes comparison sort in terms of runtime should we say that Radic sort is the best sort to use overall。

So the intuition behind this is hopefully you picked up on it is pretty similar to what we saw last week in discussion 13 Quetion 3012 sort where we wrote this linear time sort and we were super excited about it but the reason why we couldn't always use it is because we were stipulating that the array that this linear sort was already always sorting only contained elements01 and2 right it's the same idea here in part D where like in the example that I gave I gave you an example where the list only contains single digits which is not very representative of the real world and the real world we might have really really large numbers right like we might have numbers where W is like 100 and we have to sort these that's not super great for our overall runtime and in those cases we probably would want to use comparison sort over LSC ratingdic sort。

 especially as our rate size gets really large especially as our width gets really large it's possible that W times n plus R which seemed linear to us at first。

😊，Could overtake and log n right so we can't always use Radic sort Another thing to consider is that Radic sort works best when we have like a set or like a finite kind of alphabet right and especially when that alphabet or the radic size is low but we really can't guarantee that in the real world right and we really only use radic sort on numbers because that's like the best way to use them and we have like a finite amount of or like a finite radic size。

 but not all objects can be broken down into numbers right like for example。

 if we're using a reference type if we are comparing a list of dogs we can't really easily break the dogs down into numbers super like easily so that's the case in which maybe we'd want to use a comparison sort instead of a radic sort all right and that's it for part D。

