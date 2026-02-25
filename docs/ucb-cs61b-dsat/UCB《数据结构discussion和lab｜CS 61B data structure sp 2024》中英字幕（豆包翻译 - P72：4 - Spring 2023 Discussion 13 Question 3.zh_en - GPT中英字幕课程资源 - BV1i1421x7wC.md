# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P72：4 - Spring 2023 Discussion 13 Question 3.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

🎼发明哈明。🎼Oh。

![](img/fd6ab132e59d53bf06ccb97077bc42b6_1.png)

![](img/fd6ab132e59d53bf06ccb97077bc42b6_2.png)

Okay let's now move on to the last question on this discussion012 step。

 I think this is a super cool question and it's actually a pretty common design pattern I would say especially when you get to interviews so the problem statement says that given an array that only contains zeros ones and2s right an algorithm to sort it in linear time without creating a new array okay we want this done in place which we will talk a little bit more about in Part C you may want to use the provided helper method swap so over here in our special sort and I know this should returnvo sorry about that we have a skeleton code that gives us three variables front equals zero back equals r dot length minus1 and cur equals zero let we have a while loop。

😊，And over here we have three if if else statements okay。

 so we have three cases to account for basically and we're told that we might want to use the provided helper method swap so swap just takes in the array in which you want to swap some elements the indices within that array and then it tries to swap the or not it tries it actually swaps the elements in that array Okay act those indices so。

Now let's put a little bit of intuition behind this。We want it to be linear time。

 which means that we can't just call like。We can't just call it quick sort on this list right that is not exactly going to be super helpful because that's going to give us n log end time it would give us the list and sorted order but it's not the runtime that we want so now we have to build a little bit of intuition about how we're going to actually do this so over here I just gave an example list of2101201 and after we read special sort on it it should give us 00111 and22。

😊，Okay， so the reason why I talked a little bit about horror partitioning during content review was that。

Horror partitioning shows us a really cool way to partition a list into like a pivot the element smaller than the pivot and the element larger than the pivot in like linear time right it's also in place as well we don't need to create a new ray for it so the idea with behind this question is that we kind of want to adopt the same idea that we had with horror partitioning where we pick a pivot and we put everything to the left of the pivot as smaller than the pivot everything to the right of the pivot is larger than the pivot right and the question now becomes well how do we do that well remember if in horror partitioning that we had two pointers right we had like a left pointer and a right pointer and they walked together as far as they possibly could until they run into an element that they didn't like right？

😊，And once they run into an element that they didn't like， they would swap in advance。

 That's kind of the algorithm that we want to keep in mind when we're filling out this。

The special sort Okay so hopefully after talking about that we've intuited a little bit about the the front back and curve so front and back are going to be like almost like our left and right pointers is that we use in horror parting right it's pointing to position element sorry index0 and back is pointing to the less element in our list and basically these kind of represent like hey these are。

😊，The next positions respectively in which you should put a zero and a two right oops I kind of gave that away but the idea with this question is like because you only have zeros ones and twos in your in your array we can kind of pick one to be our pivot right it's almost like we're running quick sort but it's only like three possible elements in our array so if we pick one as our pivot as opposed to zero and two one is going to evenly split zero and two right we know for sure that zero is going to be less than one and two is going to be greater than one right so wherever you have a one there should be like twos after this one and zeros should be before the one if they're in the list at all right。

😊，So cycling back to what I was saying before I gave the spoiler the front kind of is like the next index in which you should put a zero if you can find it right because the front is like the front of your array that hasn't already been filled with like a smaller element than the pivot and the back is kind of like the index pointing to the next part of the array in the back half of the array in which you haven't already filled a two or a number that's larger than one right and cur is just going be like your starting point in your array so let's draw these out to visualize so front。

And cur are both0。Back。Is a radar length minus one。

 and we want to walk front and back as close together as we possibly can， right？

So this was a common misconception that I saw in my discussion and honestly when I was doing this when I was a student and I was doing this question。

 I had the same like misconception is there's a tendency when you go through while loop。

 you just be like， oh， while K is less than the array dot link because you have to go through the entire list。

Right。😊，But you have to remember that like because we are kind of like doing swaps along the way with the zeros。

 ones and twos and we're moving the front and the back pointers。

Eventually like there's a possibility that we'll reach the back pointer before we reach the array dot length right because the back pointer might swap into positions and keep hopping back if it keep seeing twos right so there's no guarantee that we need to necessarily go through the entire array we just need to go until we hit back because back is kind of the point at which we're like okay we've seen all the twos that we possibly can so when curve bumps into back then we know we fully sorted our list right because curve is going to advance from left to right and so it's going to sort all the zeros and ones before it gets to all the twos。

So。We might do something like this。But then here's a very small。

 small caveat to consider we can't do curves less than back。

 and the reason for that is let me provide an example array for you。Let's say we had01。

02 and let's say that。This was front。嗯。This was cur。This was also back。

 so current and back are both at index2。If we look at this list， clearly it's not sorted， right。

 we should swap the one and the0 over here， but occur and back， they're on the same index。

 So curve is no longer less than back。 So we break out of the w loop right so we don't want that。

 We have to guarantee that we have to look at whatever back is before we exit so。

We are going to make this while curve is less than or equal to back， keep running this s， okay。

 so that's just a very small kind of caveat here。So now we have three if else cases to take care of and hopefully this is a bit more intuitive because there are only three kinds of values that we could come across right either we see a one a zero or a two so let's deal with like the zero case first so we could say that if the array。

😊，At index curve。Is less than one aka it's just a zero right then we know that hey。

 we know that we're pivoting on one。 So if we see any zeros。

 they should be in the frontmost part of the array as we can possibly put them right so that's where the swap function comes in。

 We're going to want to swap the element to index curve。

Which we have established as zero to position front right because front is representative of the next index in which we should put a zero if we see a zero。

 so what that's going to look like is we're going to call swap。On the array。Kurt。And front。

And what we're going to do after that then is well we know that we just put a zero into front so we actually need to advance front right because the next time we see a zero we want it to go in a fresh new location。

 a fresh new index we don't want it to overwrite the other zero that was previously there so we're going to advance s and we just saw the element index occur right and we know that anything to the left。

Of Kurt should have a zero in it， right， if we're advancing through this array， so we can just。

Increment curve because we're like， okay， we've already seen it。

 it's probably going to be a zero right it's a0 that should go in the left of a curve。Cool。

So now the other case is what if the ray index curve is greater than one？So it's a two， right？

If it's greater than one， then now we need to swap with the back right so we're going to do something similar with what we did up here where we're going to swap the array index curve with the array index back because back represents the next element that we haven't already seen。

I'm sorry， Bob represents the next index in which you should put a two if you see a two， right？

So we're going to swap these two。K。Back。And now we only have one more blank and what we need to do now is we're going to need to do something similar with what we did up here when we saw zero。

 which is we need to decrement back right because we don't want to overwrite back accidentally or sorry we don't want to overwrite the original back accidentally with like another two because we want to keep moving it so that back is pointing to the next unfilled two spot like spot that's reserved for a two right in our。

So， now， you'll notice them。We only had two lines in this case the reason for that is that we don't increment cur and the reason we don't increment cur is let's use this list as an example。

 so let's run one iteration of this loop。If we go and look at this two。

 we end up in this case right we're going to swap the two with the one over here。

 that means one ends up in this position zero right and we decrement back。

If we were to increment the cur to be over here， we'd completely miss over the fact that we actually have a one in this front position right and that's not good because we established up here like hey I want everything to the left of curve to be a zero right I want this guarantee that I know for sure that I've already seen the zeros to the left of me so I don't need to touch them again but if we were to advance cur again。

After decrementing back and swapping with the back we might completely miss over the fact that there's actually a one here and it's not sorted at the end of the day right or if it or if we just leave that there there's a possibility we could overwrite this one with a zero when we see a zero right it would overwrite the front so that's not good either so that's why after we decrement the back we don't touch curve and we instead reassess what is at curve to make sure that we for sure swap everything into the right place okay。

So that's like kind of like a like a really subtle caveat okay， so now in the last case。If we have。

In the else case， we see a one。If we see a one， then we're like， okay， well。

 I know that it's just a one and this is kind of my pivot。 So let's just move on until like later so。

Yunddu occur。Plus equals one。All right。And that is it for question 3 a。

 Now when we move on to question B， we say we just wrote a linear time sort， how cool。

 why can't we always use this sort， even though it has better runtime than merge or quick sort。

 So the answer here is like， you know， in the real world。

 unfortunately we can't guarantee that we're always going to get a list of zeros。

 ones and twos right only three elements where one middle element can be the pivot so。😊，Basically。

 it's like this list。Only has。Three elements。Which is not representative of the real world。

 unfortunately， so we can't always use this sort。Now the last question we ask ourselves is the sort that we wrote above is also in place。

 what does it need to sort in place and why would we want this？😊。

I talked very briefly about this during content review but for a sort to be in place it means it doesn't take up significant extra space。

 so to some people this means that it takes up no extra space besides like a constant amount of space to other people it means。

It doesn't take up more than logarithmic space， which is the definition we'll use in this class。

 So we'll say in place。Uses。Less than or equal to log end space。ok。

And so you'll see here that we had a constant number of variables it was just like three variables right so and these three variables were not dependent on like the size of our input right we'll always have three variables no matter how larger our input is so we would say that this sort was in place right we didn't create like an extra array。

And some examples of some sorts that are like in place would be like selection so or like insertion so and heap so。

 they can all be done within the same array but something like merge sort would probably require extra like extra arrays and actually I think merge sort can be done in place we don't typically talk about it and quicksort is also in place actually yeah Quicksort is actually also in place because it uses logarithmic space for the recursive calls so why do we even want to sort something in place right so we often talk about time complexity in 61 B where we talk about like the runtime of a function but you also have to remember that space complexity is equally as important in the real world right。

It's not great to have a program that takes up a whole lot of memory on your computer because it just makes it like inefficient。

 And also it takes up a lot of space。 and you can't do a lot of other things at the same time。

 right that's how would want to sort something in place。 And even though we typically。

Focus on time complexity and6q and B， just remember that space complexity is equally as important。

 okay， and that's the end of question three。

![](img/fd6ab132e59d53bf06ccb97077bc42b6_4.png)