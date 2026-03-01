# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p02 02_01_05_逐步执行算法.zh_en -BV1Kp42117vh_p2-

![](img/a43aa2523768887e359bb3dd66957ae2_0.png)

Let us briefly take a look at an example algorithm and how you might follow it steps yourself。

 We don't need to know anything about programming to do these steps。

 We just need to be able to do some math and keep careful track of what we are doing。

This algorithm does not accomplish a really useful task， but gives us a simple example to start from。

The algorithm says given a non negative integer in， so it is parameterized over in。

 we need a value of n to actually do these steps， so let's pick n equals 2。

We are also going to want a place to write down the output that the algorithm produces。

 that is everything that we are told to write down， we will write in this output box。

We need to keep track of where we are。 So we are going to use this green arrow to remember what step we are currently on。

 We'll start at the start。The step right after the arrow says to make a variable called x and set it equal to n plus 2 n is 2 and 2 plus 2 is 4。

 so we want to note that x is initially4。Our next step calls for us to count from0 to n。

 We will want to give a name to the number we are counting so that we can use it in our other steps here。

 we decided to call it I。As we count， we are going to repeat steps。

 We have used indentation here to indicate which steps are repeated for each number we count。

 as well as explicitly noting in the step after that you do it when you finish counting。

We start with I being0， since that is the first number we said to count Our next step says to write down x times I。

4 times 0 is 0， so we write down 0。Our next step says for us to update the value of x。

 what is its new value， 4 plus 0 times 2 is 4， so we would update it to be4。It's already four。

 which is fine， we just keep its value as four。Now we have reached the end of the steps that we said to do as we count。

 we need to go back and count the next number， so we move our arrow back to the top of the steps we are doing for each number and make I the next number we would count in this case one。

Now we begin doing these steps again with I having the value 1。 what is x times I now。

 4 times 1 is 4， so we write down the number 4 in our output。

 Next we are going to update x again This time x plus I times n evaluates to 6 so we are going to change the value of x from 4 to 6。

We have again reached the end of our repeated steps， so we need to count our next number。

 We go back to the top and then count our next value， which is 2。 and make that the value of I。

 we said to count from0 to n and in is 2。 So are we done counting in these steps。

 we said to include both ins。 So we are going to do these steps when I has the value 2。

 So we go in and do the repeated steps one more time。Now x times I has the value 12。

 so we write down 12 in our output and we go to the next step。

 Our next step says to update the value of x again， evaluating x plus i times n。

 we get 10 this time so we update the value of x to be 10 and move past that step。Once more。

 we've reached the end of the steps we want to repeat as we count。

 So we return to the step where we said to count。 When we return here。

 we look at our steps and realize that we've already counted all of the numbers we were supposed to0。

1 and 2。 So we are done counting。 Now we want to go to the steps after we finish counting and do them。

This one says to write down the value of x X currently has value 10， so we write that in our output。

 Now our arrow is at the end of our steps， there's nothing left to do， so we are done。0，4。

1210 is the sequence of numbers that this algorithm wanted us to generate for n equals 2 which we see in our output box。

