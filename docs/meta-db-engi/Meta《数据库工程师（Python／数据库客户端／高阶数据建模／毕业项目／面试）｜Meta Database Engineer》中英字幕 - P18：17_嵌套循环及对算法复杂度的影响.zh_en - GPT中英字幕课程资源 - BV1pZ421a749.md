# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P18：17_嵌套循环及对算法复杂度的影响.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

In Python nested loops can be used to solve more complex problems； for example。

 the nested for loop is written by indentation inside the outer loop。

Let's explore this further now and break down how a nested loop works。First。

 the outer loop will start and then step into the inner loop。

Then the inner loop will run until its range limit is met 10 in this case。😡。

Once the inner loop completes， it will come back to the outer loop for the next iteration and then step into the inner loop again。

This will happen until the outer loop has reached its limit。

Now let's explore an example using nested loops to iterate over two lists for example。

 suppose you have two lists of integers from one to nine an account variable that is set to zero。😊。

You again have two loops， the outer loop， which will iterate over list one and the inner loop which iterates over list two。

If you run this code， it gives an output of 90。Let me break it down for you。

The outer loop runs a total of nine times， the inner loop runs a total of nine multiplied by9。

 which is 81 times and 9 plus 81 gives a total of 90。To help visualize how this would look。

 you can make some minor changes to the loop to output what it looks like。



![](img/5f8ff93d7d2523e4ee664652aba19992_1.png)

Okay， so you now know that the number of times a loopers run is based on the size of the list now that you've learned about nested loops。

 let me demonstrate some code examples of nested loops。

So I have VS code open and first let me start with a simple example and write a for loop。

I type4 I and I use the range function， so I have in range 10。Above the loop。

 I label it with a comment outer loop。😡，This first four loop is considered an outer loop and inside I will have an in loop。

I write a comment in a loop right under the first four loop。Now I type 4 J in。

 then I use the range function again， and I pass in a 10 and end with a colon。😡。

The ten0 indicates a number of times the loop will iterate or repeat。In this example。

 I print out zero and then I use end equals and a string with space in double quotes to ensure it prints out in an even manner。

😊，And lastly， I'm going to print out an empty line so that it goes to a new line in each iteration。😊。

If I run the for loop， the system prints out a 2D array grid。

This is just to demonstrate how the for loop works。If I want to print out a single line。

 I can change the outer loop to one。I clear my screen， run it again。

 and this time a single line of zero is printed out because the outer loop only iterated once。😊。

This is all based on the outer loop only。😡，It runs once。

 but when it goes to the inner loop that it runs 10 times and prints out a zero for each item on the same line。

😡，Every time the outer loop starts， it will go into the inner loop。😡。

The inner loop must finish before it comes back to the outer loop to start on two， three， four。

 and so on。I can showcase that by simply changing the outer loop range2。In this case。

 only two lines are printed。😊，So the first when I equals zero。

It comes into the inner loop and prints out 10 times。When that's finished。

 it comes back to the outer loop。😊，Then I is incremented again to one and then it will be printed out from J's inner loop and another 10 zeros again the other issue to consider with nestcent loops is the complexity or what is commonly known as time complexity。

The larger the array， the more time is going to take to run my code。

Let me showcase this by running a for loop for a larger range， but also putting a timestamp on it。😊。

I import the time module to put a timestamp in what's printed out I class it as the start time equals time dot time。

 which is the function that I want to call。😊，The start time is initialized the moment I run the script。

😊，I also want to print out how long it took to finish。

 I do that by putting a print statement outside the for loop。😊。

I then calculate the time as in the time it took to finish and then subtract that from the start time above。

This is going to print out many decimal places， so I use another function named roundund。

 which rounds numbers to a decimal of my choice。In this case， I round it off to two decimal points。😡。

Let me clear my screen one more time。I click on run and it outputs the time of zero dot0 seconds。

This makes sense because the time my code takes to run is really short。😡。

Now let me increase the range in the outer loop to 100。

 and I also increase the range in the inside loop to 100 and I click on run one more time。

The time now goes up 0 do01。😡，In this case， it's not a big difference。

 but when you're dealing with large data sets， this will have a huge effect on the running time of my code。

😊，This time， let's say for example， that I keep the outer loop to 100。

 but I increase the inner loop to 1000。ICl the screen and click on Run。The time increases to 0。04。

If I increase the inner loop one more time to 10000 and I clear the screen and click run now the time goes up to 0。

45。😡，So the larger the array or the larger the range， in this case。

 the more time it's going to take for a program to complete。

It's always important to remember how you can optimize code to make it run more efficiently and consider the amount of time your code will take to run。

You just covered nested four loops and learned about the issue of time complexity。😡。



![](img/5f8ff93d7d2523e4ee664652aba19992_3.png)

In this video， you learned about nested loops and how they work。

