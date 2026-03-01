# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p12 12_01_05_VecDeque水果沙拉演示.zh_en -BV11y411z7Dn_p12-

![](img/902267d9911a8f398e8bf39816ad4cb1_0.png)

All right。 In this example， we have a V deck， a doubleend cu similar to Python's deck from the collections module。

 And one of the really cool things about this is it has O to the one time complexity for operations on both in。

 So this means that it's very efficient in terms of using it to have operations on maybe the front or the back。

 and this can introduce new paradigms that could be very useful for your code。

 Let's go ahead and take a look at this comment here。

 It says this code starts with an initial v deck， converts it to a V for shuffling again。

 a V as a list and then converts it back to V deck after that， it pushes pomegranate。

 of fruit to the front of the deck and fig and cherry to the back of the deck。 Finally。

 it prints out the final fruit salad。 And this， again， is a double ended Q。😊。

Which means that you can push and pop from both ends at the same time。 So again。

 depending on what you're doing， this pattern is very useful。 So again。

 I use some randomness here by saying use R sequence slice random。

 We can go ahead and take a look at the cargo file， you see here。

 I'm able to introduce that dependency。 Finally， in the main function here。

 you can see that I first create a mutable data structure here first。 And I push to the back。

 And this is pretty useful and pretty intuitive。 right， you just say dot push underscore back。

 And in this case， I put this fruit in the next one， and then I put the third one in here。

 strawberry tree be。😊，I go ahead and I scramble it， then I convert it back to a V deck。

 So how do I do this， Well， I just create a new data structure here。

 and I say fruit dot enter dot collect。 And then in this case。

 I can actually add fruits to both the end of the queue after shuffling。

 So I say fruit dot push front， fruit dot push back to the fig push back to the cherry。

 And then I go ahead and I print out the fruit salad right here by enumerating it。

 And let's go ahead and run it。 Let's go ahead and type in cargo run。There we go。

 And if I run it again， we'll obviously get the same results here。

Depending on what it is that I'm doing， I could add further optimizations to do scrambling。



![](img/902267d9911a8f398e8bf39816ad4cb1_2.png)