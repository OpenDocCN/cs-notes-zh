# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p27 27_03_06_枚举类型.zh_en -BV1Kp42117vh_p27-

![](img/3a47a6ff05a2f9ff39888f2e8a260fa0_0.png)

Now， we're going to show you how to define and use your own enumerated type at the top of the screen。

 we take a color coded threat level of a standard security system and encode it into an enumerated type。

 There are five possible levels， low， guarded， elevated， high and severe。

 We can refer to these levels using exactly these words throughout our code。Next。

 there are two helper functions whose definitions we will show you later。

 The first function is print threat， which prints this string associated with a particular enumerated type。

The second function is print shoes， which prints whether a person is required to take off their shoes given the current threat level。

Our main initializes a threat level， prints it out， and then calls these two helper functions。

Let's take a closer look at our enumerated type。 C creates a correspondence between each of these words and an integer value。

 so low has the value 0 and severe has the value 4。



![](img/3a47a6ff05a2f9ff39888f2e8a260fa0_2.png)

Notice how the function print threat can refer to these levels using exactly these words throughout its definition。

 making the code much easier to read。Print shoes does this as well。Inside the main。

 we declare a new variable of type threat level T called my threat。

 We initialize this variable to the enum high， which has the integer value 3。

In order to print out the current threat level， we call the function print threat。

 we create a stack frame for print threat in which the argument my threat will be referred to as threat。

We mark the call site location and step into print threat。Inside print threat。

 there is a switch statement which checks the value of the threat and jumps to the corresponding case here we're jumping to case high。

Inside of this case， we print orange slash high， and the break exits us from the switch statement。

Now we return to the function that called print threatre， which is our main。Upon returning。

 the stack frame for print threat is destroyed。 Next， we execute the call to print shoes。

 creating a stack frame for print shoes in which the argument。

 my threat is referred to as cur threat。We mark the call site location and step into print shoes。

Inside print shoes， there is an if else statement。 The if clause tests whether the current threat is greater than or equal to elevated。

 In this case， we're testing whether 3 is greater than or equal to 2。 Since it is。

 we step into the then clauses， print out the message。

 Please take off your shoes and exit the clauses。Now we return to the function that called print shoes。

 which is our main。Upon returning， the stack frame for print shoes is destroyed。Finally。

 the program exits the main and its stack frame is destroyed。

Notice how much easier the code is to read because we've used an enumerated type。

If instead we had an int called threat level with values 0 through4。

 the code would be littered with a lot of numbers whose meaning might be unclear to the reader enumerated types make it easier to read。

 write， and modify code。