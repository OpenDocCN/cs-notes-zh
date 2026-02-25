# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P26：1 - Spring 2023 Exam Level 06 Problem 1.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

可南家。If one Russia。

![](img/0b8c90462d99a4eae4350a6acb5d4184_1.png)

Everyone， this is Sherry and this is the CS61B spring 2023 exam level 06 walkthrough in this video I'll be going over Proble1 asymptotics introduction。

 so this problem is just our very basic iterative asymptotics and we're going to be analyzing the runtime of a few functions just to warm up。

So let's start with the first function F1。And in general， for iterative asymptotics。

 I like to just write out a little table of the work that each loop does and usually you only have two nested loops so you can just format this as a 2D table。

 so I can put my I here and myj here。And let's write down what values my I takes on。

 so it's going to take on1，2，3 all the way to n minus1 and what values is my j going to take on for each value of I right because for each value of I I'm going to do this entire inner loop here so in this problem my J is going to start at1 and it's going to go up to I so in the first loop there's actually nothing that happens because it starts at one and then it doesn't iterate anymore is because I is1。

In the second loop it's going to go up to one in the next loop it's going to go one， two。

 and then in the next loop it's going to go one， two， three。

 do do dot in the very last loop all the way up until it hits n minus2 because it's going to go up until I。

And then what I do is I write down the work for each row。

 so in the first row there's zero work in the next row there's one work in the next row there's two work。

 and then all the way at the bottom there's n minus two work because that's just the number of iterations。

And then the final thing we do is we just sum up all the work that we added up per row across all the rows。

 so we do0 plus1 plus two plus dot dot dot and minus2。

And this might remind you of a sum that we already know which is that one plus2 plust n equals theta of n squared。

 well this is basically the same sum except we just start。

 we have an extra zero at the beginning which doesn't add anything and we're missing two terms at the n。

 but asymptotically it's still the same， so it's going to be n squared。

So that's it for the first part now let's move on to the next part which is the F2 function and again we're going to use the same approach of drawing out our table。

 writing the work per row and then summing up the work across all the rows so let's start by just writing I and J and let's write down the values of I if we look here we notice that our i values are going to be a little bit different because they start at one but instead of incrementing they're doubling each time so we go1248 dot dot dot all the way to n over four and then n over2 and then we stop before we reach n。

And then for J we're going to go the same thing where we increment J up to I so again in the first loop there's not going to be any j values because we're going to hit one and then we're going to stop and then the next loop we're going to hit one and then the next loop we're going to hit one。

 two and then in the next loop we're going to hit one，2， three，4， five， six all the way up to seven。

And then finally let's look at the last couple rows it's going to be a similar pattern where j starts at one and then it goes all the way up to n over4 minus1 and then in the next loop it's going to go one。

 two， three and it's going all the way up to n over。

2 minus1 so again let's draw how much work is done in each row and in the very first row there's zero in the next row there's one in the next row there's three in the next row there's7 and then up in these last two rows there's n over4 minus1 loops and then the very last row there's n over2 minus1 loops So again we just want to write out this sum and see what it sums up to in this case it's 0 plus1 plus3 plus7 plus dot dot dot n over two sorry n over4 minus1 plus n over2 minus1 and what we notice is that this is basically the same as another sum that we already know which would be1 plus4 plus8 plus dot dot dot n over4 plus n over2。

And again from class， we know that when we have a geometric sum。

 the runtime is just the last term in the geometric sum。

 so in this case it would be theta of n over  two and since we ignore constant factors in asymptotics。

 this would just be theta of n so this final function is theta of n。

That's it for this problem for my weekly exam tip if you have iterative asymptotics。

 it's always a good idea to draw a table that looks like this where you have your eyes along the column and then you have your Js along the row and then all you have to do is write how much work there is per row and then sum it up to one of the two sums that you know in this class。

 the arithmetic or the geometric。That's it for this problem， if you have any comments or questions。

 please leave them below and good luck in the rest of 61B。



![](img/0b8c90462d99a4eae4350a6acb5d4184_3.png)