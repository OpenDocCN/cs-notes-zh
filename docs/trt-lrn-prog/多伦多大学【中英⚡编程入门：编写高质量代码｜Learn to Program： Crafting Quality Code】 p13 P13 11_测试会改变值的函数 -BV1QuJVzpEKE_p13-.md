# 多伦多大学【中英⚡编程入门：编写高质量代码｜Learn to Program： Crafting Quality Code】 p13 P13 11_测试会改变值的函数 -BV1QuJVzpEKE_p13-

![](img/3ac34e223bb17ef782aaaf6bcd291990_0.png)

In this video， we'll explore how to test a function that mutates a parameter。

 We'll start with a doc test example， and then we'll translate it to unit test。

Here is a function that removes items from one list that appear in another list。

The algorithm is straightforward for each item in the second list。

 If that item appears in the first list， remove it。In the doc test， we create two lists。

 We have intentionally not used L1 and L2 as variable names in order to remind everyone that parameters are local variables。

 and we can use any name we like for the two lists outside of the function。

Now we call function Remove Sha。The function has no return statement。 It produces none。

This means that when we call the function， there is no useful return value to examine in our test。

Instead， we examine list one and then list 2。We want to make sure that list 1 has been mutated properly。

 and we want to make sure that listist 2 has not been mutated。For thorough testing。

 it's important to check this。 If you pass imm mutable value to a function that isn't supposed to mutate that value。

 make sure to check that it hasn't been mutated。Let's write the unit test version。

Every unit test starts out by importing unit test， as well as the module containing the functions that we're testing。

We need a subclass of test case。 We'll name it based on the function we're testing。

 and we'll write a brief doctrineuring for our new class。

We'll write only one method because there is only one call on function removed shared in the doc test。

 Remember that every unit test test method has to start with the letters， T， E， S T。

Because our test involves two lists where there are some shared items and some non shared items We'll choose test general case for earning。

The dock string should describe the test。 Remember that if the test fails。

 then this do string is part of the output。 So try to make it clear and helpful。Now。

 let's write the actual testing code。 We'll copy and paste from the doc test to initialize our two lists。

Once we call remove shared， we expect the lists to look like this。

We need to call function remove shared。And then we need to assert that the two lists are equal to what we expected。

And now， if variable underscores name refers to the string underscores main。

 then we'll run our unit testss。Let's see how we did。 We'll run our doc tests。

Notice that there is no output， that's a good thing。And now we'll run our unit test。

The single do indicates that our only test method past。

And that's how you test a function that mutates a parameter。

If you wanted to thoroughly test function remove shared。

 you would have to decide what your tests should be and then write one test method for each test you came up with。



![](img/3ac34e223bb17ef782aaaf6bcd291990_2.png)

We'll leave that as a practice exercise。