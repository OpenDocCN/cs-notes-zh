# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P6：Chapter 1 5.Binary Addition.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello and welcome to the next exciting installment of digital design。😊。



![](img/f4a0935f55c5fa6b8720236ba1aa14bd_1.png)

The topic of this video is number systems， and in particular， addition。So to think about addition。

 let's again start with addition in our familiar decimal number system。Imagine we wanted to add。

3734 plus 5168。Just like we learned in elementary school， we would do 4 plus 8， makes 12。

 You can't write 12 as a single digit。 So instead we write a2。

 and we carry a one to the next column that has 10 times the weight。

Now we can do 1 plus 3 plus 6 makes 10。 Again， you can't write 10 as a single digit。

 So we added 0 and a one in the next column。1 plus 7 plus 1 makes 9，3 plus 5 makes 8。And we're done。

Bine area is similar。 Let's say we wanted to do one plus one that would make  two， which in binary 1。

0。 That's not a single digit。 So we write the 0， and we carry the one to the next column。Next。

 we do one plus 1 plus 1 would make3， which in binary is 1，1。It's not a single digit。 So again。

 we write the bottom one and we carry the upper one to next column。

1 plus 0 plus 0 makes1 and1 plus 0 makes one。We could check this。1，0，1。

1 is 8 plus 2 plus 1 is 11 base 10。0 plus 1，0 plus 1 plus 1。Three base 10。And the sum 1 plus 1。

 sorry，8 plus 4 plus 2 is 14。In base 10， sure enough。Let's do some more examples。Sai。9 plus 5。

1 plus 1 is 0。 Car a 1，1 plus 0 plus 0 is 1，0 plus1 is 1， and one plus1 is  one。 So again。

 this mix 14。On the other hand， if we were doing 13 plus 6， sorry， that's not 13。This is。11。Plus。6。

1 plus 0， mix 1。1 plus 1 make 0。 carry a 1，1 plus 0 plus1， make 0。 carry a 1，1 plus 1 plus 0， make 0。

 carry a 1。We get 10，0，0。Which is 19。That's correct。 But our answer is no longer4 Bs。

This is called overflow。Where we have another digit beyond what we start with。

So digital systems often operate on a fixed number of bits。

And overflow would occur when the result is too big to fit in the number of available bits。

 Like when we added those24 B numbers and we get a 5 B result。Often， the extra bit is discarded。

 which would lead to a potentially incorrect result。

An infamous example of overflow is on the Aion5 rocket。In 1996， this was our next generation rocket。

The version 4 worked just fine， and the five had a larger engine。When it took off。

 it veered out of control and after 40 seconds， veered off of control， broke up and exploded。

Carrying a half billion dollars of rocket and cargo。

So the problem was traced back to the larger engine and the control system for that。

The horizontal velocity of the rocket was stored in a 16 B integer。And with a more powerful engine。

 the velocity got faster， and the number overflowed gave an incorrect version， In result。

 sending the rocket out of control。So as you can see， overflow can be a big deal。

 and when you're working with binary numbers， you need to think about the range and avoid overflow。



![](img/f4a0935f55c5fa6b8720236ba1aa14bd_3.png)