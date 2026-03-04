# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P4：04_02_06_归并排序.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/b1660378474c6d7f719051fd990fff08_0.png)

That fast algorithm for sorting that we're going to look at is called merge sort。

And it's a very simple method， we take the array that we need to sort and we divide it into two halves。

And then what we do is recursively weresort each of the halfs， so now we have two sorted subars。

 half the size of the original one。And then we merge the two halves together to make a sorded whole。

That's merge sort， and it was invented actually by one of the pioneers of computing John von Neumman。

 we'll talk about him later on in the course。The early focus when computers were first being built was on numerical calculations。

 but what von Neumman did was invented merge sort really as a test to see how the computer would work on other tasks。

 and merge sortrt definitely has stood the tests of time。

So let's look in more detail at how merge sort works。

First what we need to do is implement the merge now it turns out that mergging is a little more complicated than you might think one thing that is hard to do is to sort to merge an array in place if we have our two sorted sub arrays to do it within the same array is a little tricky。

 is very tricky in fact，So instead， what we're going to do is take an auxiliary array。

 an extra array to put the results into。And then when we've got the merge done then we'll copy it back。

 so this is a flaw of merge sort， there's other methods that don't have this characteristic that you need an extra array and you can learn about those in an algorithm course。

So we're going to keep an array called aux that's an extra array and then we're going to。

Right this program merge that behaves as if it did the merge in place， so that is we take our array。

 we take low mid and high， and it's going to say low mid again using our notation doesn't include mid and then mid high and donation doesn't include I and then we're going to put the result into a and then merge it back。

And then copy it back as if the merge happened in place， so that sets up our indices。

 all we do is maintain one pointer I that points to the low part of the array。

 another pointer J that points to the high part of the array。

 we compute the number of things that we're going to have to do。

 which is just high minus low and then k is an index into a the result。So。If our。

We get to a point where the low part is exhausted， we copy over。

 this is an edge case that we'll talk about later， we just copy over。

 but the main part of this is to check the element at J against the element at J at I and then move the smaller one into a and increment that pointer and so if J is less than we move the one at J if I' is less we move the one at I。

And then we copy it back into A。So let's look at how this works。

 so I starts out pointing to Alice and Jay starts out pointing to Bob。So Alice is smaller。

 so we move that one over and now Bob's smaller， so we move that one over each time k gets the oxux of K gets the next element that belongs there。

 but all we're doing each time is one comparison picking the smaller from the two sub rays。

So now Eve is smaller， so that's going to go and Frank is smaller， so that's going to go。

And the one that we move， that's the index that we increment。

 it's quite a simple process and you look at this code， you'll understand how it works。

And then eventually one of the arrays exhausts， and that's what the two first conditions in the if statement are for just to move everything from the other one over。

So that's merge， and then we copy it back， so the effect is as if we did it in place。

 but we have that auxiliary array。Now， given that merge。

 then merge sort is a recursive program that uses that abstract in place merge to get the job done。

And so there's the merge method and the AX is a global array that everybody can refer to。

 and we do that so that we within our sort method， we allocate that array just once and then call a recursive method that takes indices just like binary search did。

 and here's the recursive method that sorts the subarray of an array A between index low and high。

 again， not including A of high using our standard notation。

So we compute in if it's less than one element we return， otherwise we compute our midpoint。

 sort the smallest the half of the smallest indices， sort the half of the larger indices。

 and then merge。And so all of that's set up for the merge is to make this code so transparent。

 divide the array in halve， sort the two halves， merge the two halves to make a sorted whole。

 that's merge sort， and we'll use the same test client as for insertion which is just read strings off standard input and then sort them。

AndAgain， this is going to sort for our example， and we'll do a trace in just a minute。

That's a merge sort， pretty straightforward implementation。

 although you have to make sure that you get the auxiliary array part right if you put that within the recursive routine。

 it would be too slow。Okay， so let's look at how it works dynamically so what do we have to do to sort that array。

 we have to first sort the first half， what do we have to do to that one。

 we have to first sort the first half of that one sort that one we have to sort Wey analysis and finally we get down to an array of size one that can be considered sorted。

So then we have to consider the other size， array of size one and now those are considered sorted。

 and they are sorted， they're just one， and now we merge those two sorted sub filesles together to get Alice and Wendy in the proper order。

Now we do the second half of the array of size4 at the beginning。

 and we have Dave and Walter in therere already in order。

 now we have two subarrays of size2 that we can merge together to get the first four elements in sorted order。

Now we're finished with the first half of the array of size8 at the beginning。

 and we can work on the second half in the same way。It's a file of size two。Second file size two。

 merge those together to get two sub filesles of size4。

 and now we can merge those together to get the first eight elements sorted。

Now we do the same thing for the second half of the array and you can follow through the dynamics of merge sort and now we have the one of size4 sorted。

 we do the second one of size4 same way。Now merge together those two forests to get an eight and now we have the two8s and we can merge those together to get the entire array sorted。

That's merge sort。So let's do the analysis， so to make it even simpler willll count just the number of times a string moves from one array to the other。

 the comparisons is a little more complicated analyze this is quite simple and again we'll do the analysis for when n is the power of 2 this time and that's now if big n equals2 to the little n little n is exactly log base2 of big n。

And we have we start out with an array of size2 to the little n and we split it in half。

 we have two arrays of size2 to the little n minus1 divide 2 the n by  you get two to the little n minus1 and split all those in half you get four subarrays of size 2 to the n minus2 now if you look down at the bottom it does the calculation of how many data moves do you do well the merge for at the beginning you do emerge two things of size n over 2 into the auxiliary array so that's n data moves and then you move them back so it's two n data moves and that's true for each subarray but if we do it for two subarrays then it's going to be two n data moves total for both of those subarrays。

And going all that way， every time the total number of data moves for all arrays of that size is going to be2 in。

So that means the total number of data moves is 2 n natural log n because we have n phases that's counted by the sub array size。

 little n phases， which is log of big n， so the total number is 2 n natural log of big n。

That's a quick way to see that the running time merge source proportional to in log n， and again。

 this basic argument works even when N is not a power of two and you can learn more detail about that in a course on algorithms。

That's our mathematical model， and again we want to do empirical tests to check the mathematical model。

 again， using the same model that we use for insertion sort。

And now it takes just a second to do a million， two seconds to do 2 million， and then in 16 million。

 20 seconds you could do a billion in not too much time in a few minutes 20 minutes to do sort a billion items。

 which is definitely fast enough for Alice and Bob type applications。

And it confirms the hypothesis that the order growth is either linear in log n。And all right。

 her math model at N log N in this confirms that， so that's a fast sorting method。

 now sorting is so important that people have studied other methods and their methods that are constant factors faster than this。

 but certainly by comparison with insertion sort， this method solves our problem。



![](img/b1660378474c6d7f719051fd990fff08_2.png)

It scales and that's what we need is a scalable method so that as our company grows。

 we can grow with it。Along with Moore's law。And so Alice says， okay， I'm ready to go now。

 I've got my white list generator。

![](img/b1660378474c6d7f719051fd990fff08_4.png)