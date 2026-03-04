# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P87：-087-Glass Box Testing Chap6 Video 17.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

With glass box testing， the tester gets to see the internals of the functionality being tested。

This does have some advantages over black box testing。

The tester can determine whether a new test case really yields any additional information about the correctness of the implementation or whether it's just redundant with respect to the other test cases already invented。

Glass box testing also can address likely errors that are not apparent from the specification when you get to look at the source code。

 maybe you realize that the implementer is using a function that they are likely to misuse and so there is some tests that are suggested by that。

Glass box testing though， supplements black box， it does not replace examination of the specification。

Really， both methodologies should be used if at all possible。In glass box testing。

 our goal is to cover the entire program with test cases。That is to ensure that the entire program。

 all of the pieces of source code， have been exercised by the tests。

The thing that makes this challenging is branches。So a branch is any kind of language construct that lets you do conditionally one piece of code versus another。

If expression， a match expression， Boolean operators， raising exceptions。

 having loops or recursive functions， all of these involve branches and make it challenging to achieve good coverage。

The exact definition of coverage is flexible。 Three of the mainkind are statement。

 condition and path coverage。With statement coverage。

 and this is the name that was invented in the context of imperative languages， so bear with me。

With statement coverage， what we're trying to do is cover the program by causing every statement in the program to be executed at least once。

😡，To put that in a more functional context， that means。

Having enough tests to make sure that every expression in the program will be evaluated at least once。

I will continue to call this statement coverage， even though we're in the context of a functional language because that's the name it's known by。

With condition coverage。We're trying to get an even more fine grain coverage of the program by causing every Boolean or in a functional language。

 every pattern match as well。To evaluate to every possible value。

So it's not just enough to make sure that the guard of the I statement gets evaluated at least once。

You want at least two tests， one that causes the guard to evaluate to true。

 one that causes it to evaluate to false。Or with a pattern match。

 you want to make sure you have enough tests to cause every possible branch of that pattern match to eventually be evaluated。

Path coverage is even finer grained， still。With PA coverage。

 you want to cause every possible execution path through the program to occur。

It's not just enough to evaluate every possible branch at least once。

For every sub branchch that's part of it， you want to explore all the paths through it as well。

Path coverage is therefore quite difficult to achieve。

Let's make this concrete in this example with max of three numbers。Max of X， Y。

 and Z returned the maximum of those three。You could write all kinds of black box tests for this using the methodology we've already explored。

 and that's a good thing to do as well。But if you look at the particular implementation here。

 you'll see there's really only four possible ways this function can return。😡。



![](img/985dd4a150da0f18af9c6277ddbe52d5_1.png)

![](img/985dd4a150da0f18af9c6277ddbe52d5_2.png)

So。For good glass box coverage， we really only need to write for test cases。One。

 to explore each of those paths through the if expressions。

The advantage here is we get to write a much smaller test suite。

The disadvantage is we haven't really tested against the specification。

 and if someone comes along and changes the implementation。

 now our tests are going to be out of date， so we also ought to have the black box。

To achieve good coverage， we should include test cases for each branch of every nested diff expression and each branch of every nested pattern match。

Some things to watch out for， particularly are base cases of recursive functions。

Making sure to trigger the recursive call for every recursive function and making sure you have tests for every place where an exception might be raised。

 Suppose you were trying to do glass box coverage of this leapier function。

 which determines whether a year Y is a leap year in the Gregorian calendar。

So you can see the implementation here is based on Boolean Opre。

Now suppose you have a test suite that already tests the inputs 202010 and 2020。

What kind of coverage does that test suite achieve？Is it statement coverage or condition coverage？

Well， let's work through and figure it out。😡，I've created a table here。😡，The rows are the test cases。

 the columns are each of those boolean expressions， and I want to fill in this table。

 I'm going to enter true or false if the Boolean expression gets evaluated to true or false with that particular input or not evaluated because not all of these inputs are going to cause all of the expressions to be evaluated。

You might want to pause here and fill in the table yourself before continuing。😡。



![](img/985dd4a150da0f18af9c6277ddbe52d5_4.png)

The input 2000 causes all three expressions to be evaluated。



![](img/985dd4a150da0f18af9c6277ddbe52d5_6.png)

But 2010 and 2020 leaves some of them unevalueed。So this test suite does achieve statement coverage because every expression in the program is caused to be evaluated somewhere in the entire test suite In fact。

 it turns out 2000 suffices for that。😡，But condition coverage is not achieved。



![](img/985dd4a150da0f18af9c6277ddbe52d5_8.png)

If you look at the column for y mod 400 equals 0， there's no place in which that expression evaluates to false。



![](img/985dd4a150da0f18af9c6277ddbe52d5_10.png)

You manage to get true， but not false。So to achieve condition coverage。

 we need to add another test case。2100 would suffice and could cause that final boolean expression to evaluate to false and get condition coverage。



![](img/985dd4a150da0f18af9c6277ddbe52d5_12.png)

![](img/985dd4a150da0f18af9c6277ddbe52d5_13.png)