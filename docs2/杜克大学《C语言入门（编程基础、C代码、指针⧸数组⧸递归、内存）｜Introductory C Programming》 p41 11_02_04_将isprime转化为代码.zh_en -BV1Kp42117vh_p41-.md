# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p41 11_02_04_将isprime转化为代码.zh_en -BV1Kp42117vh_p41-

![](img/053983bef7b2d9a5129d89a331b5b33a_0.png)

Now， we're ready to translate our steps to code。 We'll take our algorithm shown here and write it as comments so that we can translate line by line。

 We start with a function declaration written around our steps。 If you were doing this yourself。

 you could add the algorithm as comments in your editor without leaving space for code。😊。



![](img/053983bef7b2d9a5129d89a331b5b33a_2.png)

The first thing we need to do is check if n is less than or equal to one。

 We're checking a condition and deciding what to do based on that。 So we want an if statement。

 If n is less than or equal to one， we want to do something。 Otherwise。

 we want to do everything after it。 If so， we want to answer no， and that is a return statement。

 We want to leave this function immediately since we know our answer and we don't want to do anything else。

So we return zero。Recall that0 means false or no， and non0 numbers generally one mean true or yes。

 Next， we want to count from2 to n and call each number that we count I。

 counting corresponds to a four loop。The number we want to count is I。

 So we're going to declare int I equals 2。 We want to count to n exclusive。

 So we choose the conditional statement。 I less than n。 Also， we're counting by one。

 So our increment statement is going to be I plus plus The body of the loop will be the steps we want to take for each number that we count。

 The first of those is check if n mod I is equal to 0。This is again， an if statement。

 because I want to check a condition and make a decision about what to do next based on the result of that。

N mod I， I write N% sine I， since that is the mod operator。 I want to see if it's 0。

 So I use equals equals。 recall that two equal signs compare for equality。

 Then I have curly braces around what I want to do if this condition is true。 If so， answer no。

Is again， return0， We would know our answer immediately is no， so we would return 0 in this case。

After all of this， if we finish counting， that is after the body of the for loop。

 If we haven't returned and left this function， we answer yes。We put return1。

 This code would work fine。But we're going to do just a little cleanup。 General。

 when we're programming， we don't like capital letters for variables。

 All capital letters is usually reserved for a constant， so we'll use lowercase N for this variable。

Now we have it a function that will compute whether or not n is prime。



![](img/053983bef7b2d9a5129d89a331b5b33a_4.png)