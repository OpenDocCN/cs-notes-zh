# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P31：3 - Fall 2022 Discussion 7 Question 2.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/f2ffdd6de5f3a67f3043cac30951a148_0.png)

![](img/f2ffdd6de5f3a67f3043cac30951a148_1.png)

Oh。Okay， on to the next part， we have virtually the same setup as before。

 but this time we want our desired runtime to be theta of log n so pattern matching a little bit from the previous part where we needed to have basically an iterations of the loop in order to get to the desired runtime right we needed n iterations of one work each in order to get linear time。

Here we're going to need log n iterations of one work each right because it's the same setup where were just printing something so here we know that I is going to start at one it's going to stop before n and overall we need to basically get from one to n in a log n time steps okay so the easiest way to do that is updating I not that at increments but that it。

Is like multiplied by a constant factor every time。 So， for example。

 we could do something like I times equals2。Where I takes on the values of124816 all the way up to n divided by2 right and basically the number of terms here right the number of terms it takes to get from one to n will be log based two of n but once again we more constant so we just generalize it to log n and you can kind of think about this in terms of like the height of a tree like how would we like get to it from the top to the bottom of the tree based on n same thing but yeah you'll notice that if we multiply by two or three or four whatever it takes log n time because it's like a jump from one to2 to four and so on and so forth okay。

Next we have a desired runtime of constant okay this is a little bit new once again we have a setup with a for loop where I begins at one we have to determine the stopping condition but we know that I is going to increment by one every single time and it does constant work so in our little table over here we know that I will take on the values of one。

2， three all the way up to something that we don't know but that we will determine based on our stopping condition right and we know that it does one work per iteration of the loop。

So how do we make sure that this runs in constant time？

So the solution to that is actually we can just make the stopping condition based on a content on a constant sorry。

 so as long as the stopping condition is not based on N here。

 it doesn't really matter how many times we increment I because it's going to run a constant number of times like no matter what value we pass in for n n could be zero n could be negative5 n could be 10 million000 billion or whatever。

 but we're going to ever only ever run this loop like 999 times right which is why we consider this constant and know that the solution is actually just I is less than C where C is some constant independent of the input n so what we're just saying is it just can't be based on n。

All right。So now lastly we have a really tough question to be honest this one's really tricky and our desired runtime is big theta of 2 to the n okay so in F4 we take in some number N and we have a nested for loop and this is where I said in the content review to really watch out because nested for loops are not always going to give you n squared time based on the stopping conditions and also the index updating conditions right？

😊，This one is really tricky and as a hint I want you to think about the dominating term in the sum1 plus2 plus4 plus8 plus 16 all the way up to f of n where f is just some function of n okay so over here we know that I is going to begin at one we know it's going to double with every iteration of the loop okay so it's going to count from one to two to four to eight all the way up to some number that we don't really know。

😊，And then this inner for loop is going to run based on what I is。

 so it starts at zero and so when J is sorry when I is1 is going to run once。

 when I is2 is going to run two times when I is four is' going to run four times so on and so forth。

 right？So this means that the total work that we're doing for F form is going to be one plus  two plus 8 plus 16 plus whatever right like all the way up to something so knowing to determine what that something is well if you remember that。

The sum over here， the 1 plus 2 plus4 where it's doubling every time。

What this dominating term is it's actually going to be F of n。

 so the dominating term of this sum ends up just converging to F of n。 so that means that。

If we want to converge to two to the n， then we can just pop that in into whatever the last value is for the iteration the iteration of the outer loop。

 right， because we know that。The work done per iteration of the outer loop is dependent on the index of the outer loop right so if we said that I is less than math dot poweru2 n so that's just how you write  two to the n in Java you're going to get a sum that looks like one plus two plus4 plus a plus 16 all the way up to two to the n minus1 which gets dominated by the two to the n minus1 and it doesn't really matter because oh sorry actually this should be2 to the n minus1 with like the。

What is it called？Like the minus one should be up with the exponent that's my bad sorry。

 but basically that's going to。Like we're going to ignore the constants because that would just be one half2 to the n right and so that would give us our desired run time of theta of two to the end。

 okay？Okay onto2 b which is an extra problem that's just good practice for worst and best case so here we want to give the worst case and best case running time in big theta notation and n and we can assume that the cahow function is takes constant time and returns a boolean so we see here that we have two nested four loops the outer loop counts from zero to n and it increments each time and the inner for loop is a little bit interesting so j starts at one and it says we're going to run the group while j is less than M but there's no set incrementing or like changing condition for j here and instead we see here that the changing condition of j is dependent on the outcome。

Of ko， Okay， so now I'm just going to draw a bit of a table like I did with the previous problem。

 So I'm going to write out the values that I takes on right because I is our outer loop。

And then we know that I is going to take on the values of0，1，2， three。

4 all the way up to n minus one right it's not including n and now we have to split things into the best and the worst case work per by okay so usually like what I look for when I'm trying to find out best in worst case is I try to look for things like branching conditions or like if statements right because like over here we'll see that this if statement。

😊，With this if statement that based on this if statement's outcome J gets updated differently right and I'm going to hone in on these update conditions so if Kachao is true。

 then J plus equals one otherwise J gets doubled right and remember that in the best case scenario we're trying to look for what takes us what will like。

Get us to finish executing the function fastest right。

 so which one is faster J incrementing by one up to M or J doubling each time up to M。

So the answer is going to be that J doubling up to M will only take log m time steps right versus if J got incremented then it would take a linear time if it has to get incremented every single time right so that means that we're going to in the best case Ka howo always returns false so we're going to go into this case over here J times equals2 and J effectively gets doubled n sorry log based two of n times but we're going to generalize that's a log n so J gets doubled log n times up to M。

Okay， so that means that with each iteration of the outer loop I in a best case scenario。

 we're going to hit the J doubling case every single time。

 so this is going to give us log M work per iteration of I。Okay。😊，Now on the worst case。

 it's kind of like the inverse of what we just did right we're trying to find out well what would give us the slowest time that it would take for us to finish executing this function。

So over here that would be this J plus equals one line right if Kacho was true every single time。

 then we could do J plus equals one all the way up to m and that would take linear time with respect to m right so that means that for every single iteration of I it would take linear time like to be specific it's going to take m minus one time but that's going to generalize out to。

To like linear time with respect to m Okay， so now we have to think about our overall run times right so in the best case we do log m work per I and there are n iterations of I so that means that the total work that we do in the best case is going to be。

N log M okay and similarly we want to do something like we want to do the same thing for the worst case work per I。

 there's n iterations of I and in the worst case we do M work per iteration of I so the worst case scenario is going to be n times n okay so this is just like an interesting practice problem with two different variable sizes that like the runtime will depend on okay。



![](img/f2ffdd6de5f3a67f3043cac30951a148_3.png)