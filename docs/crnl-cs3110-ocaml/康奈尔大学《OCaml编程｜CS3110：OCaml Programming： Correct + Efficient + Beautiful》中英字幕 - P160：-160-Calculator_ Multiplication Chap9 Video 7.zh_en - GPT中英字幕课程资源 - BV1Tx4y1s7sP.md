# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P160：-160-Calculator_ Multiplication Chap9 Video 7.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Next， let's make multiplication work。So we have a test case here for multiplication that I want to make past next。

We can test and make sure that it does fail right now。Indeed， it does fail。

So now we'll go back and basically redo the same work that we did for Plus。

 but with multiplication in order to implement it， I will go a bit more quickly through this。

I now have a multiplication operator for my binary operator type。

I'll have my Leer return a times token when it sees the asterisk character。

I'll add a new part to the expert parsing rule here。

 which says what to do with times and that's to return a multiplication。



![](img/90e478cb27b76f2a5af205e769157664_1.png)

And I'll finish by adding a branch for pattern matching of multiplication to reduce that operator。

I didn't get a warning or a to do from my compiler here because I did have a catch all case here。

 so that's why it's dangerous to have those sometimes。😡，Now our multiplication tests should work。Yea。

 it does。

![](img/90e478cb27b76f2a5af205e769157664_3.png)