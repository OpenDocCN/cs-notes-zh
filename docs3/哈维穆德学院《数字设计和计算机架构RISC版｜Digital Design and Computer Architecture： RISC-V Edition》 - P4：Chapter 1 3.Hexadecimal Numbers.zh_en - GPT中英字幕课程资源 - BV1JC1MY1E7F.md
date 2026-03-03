# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P4：Chapter 1 3.Hexadecimal Numbers.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/72e080482c899750a7ac9630638702f0_0.png)

The next topic in our conversation about number systems are hexadecimal numbers。

 You'll see hexadecimal numbers quite frequently when you're dealing with digital systems。

 and that's because theyre an efficient way to represent binary digits。



![](img/72e080482c899750a7ac9630638702f0_2.png)

So if we look at the chart here， you can see hexadecimal digits。

 which are base 16 numbers range from 0 to 9， but then also have the letters A through F included to represent the decimal equivalents 10 through 15。

 And you can see on the right hand column we have the binary equivalents for each of the decimal equivalent and hexadecial digits。

And the nice thing about hexadecimal numbers is they're going to act as a convenient way to represent four binary digits。

So for example， if we have the binary number。Wan。0。1，0， base 2。 This is going to be equivalent to。

10 in decimal。Cause if we assign the places here， we have the eighths place， the fours place。

 the two's place and the one's place。And so， this is gonna be 10。Base 10。 and in hexadecimal。

 this is going to be represented by。A。So you can see here that we only need to represent these four binary numbers。

 we only need one hexadecimal digit， and so this is going to offer us a much more compact way to represent really long binary numbers because now we have one letter that can represent or number that can represent four binary digits。

So if we look here， let's do two conversions。 you can see how this works。 So， for example。

 if we're going to convert from hexadecimal to binary， again， this is pretty easy。

 We're going to take each of our hexadecimal digits。

 convert it to its appropriate binary representation and then just append those one to each other。

 So for example， to convert 4 AF base 16。 This is also written with this precursor 0 x here。

 which indicates that it's hexadecimal number。 we can take the each of the hexadecimal digits and separately convert them to binary。

 So first， we have4 base 16。A， base 16 and f， base 16。

 And if we convert these to binary 4 is going to be 0，1，0，0， base 2。 a is going to be 1，0，1，0。

 base 2。 and f is going to be 1，1，1，1， base 2。 And to get our final answer。

 we're just going to smush these all together。 and we're going to get 0，1，0，0。1，0，1，0。1，1，1，1。

 And that's all base 2。And if we wanted to do the opposite conversion to go from binary to hexadecimal。

 the process is basically just the same。 We're going to start on the right hand side and group our binary number into groups of four digits and then convert each of those groups of four into a hexadecimal digit。

So we can also see here how to convert to decimal to something that we have a more concrete idea of from kind of our natural understanding of mathematics。

 And so if we want to convert this to decimal， we can either convert it to the binary and then convert it to decimal。

 But if we think about how we would convert a binary number to a decimal number where we're going to take the the value of each each location in the number and then convert that。

 we can do the same thing with hexadecial。 So here we just have to represent the places that we have。

 So we have the F digit here is in the 16 to the zero spot。A is in the 16 to the first power spot。

 and 4 is into the 16 squared spot。 So if we want to represent this as a decimal number。

 we're going to take  four times 16 squared plus a。

 which we know in decimal is 1010 times 16 to the first power， plus F。

 which we know is 15 times 16 to the zeroth power。If we work all these out。

 we have four times 16 squared is 256， so this is going to be 1024。Plus，10 times 16 is 160 plus 15。

And so our answer at the end of the day is going to be 1199 based 10。So you can see that it's， again。

 pretty straightforward， you're just going to treat each of the hexadecimal digits and multiply it by the value of its placeholder as we did in this example。

So again， another thing you may commonly see in programming languages are the prefixes。

 it's kind of hard to do subscripts in text files and so to indicate the base of a certain number we assume no no prefixes for decimal numbers but if we want to represent a number as a hexadecimal number we'll use this prefix 0 X which you'll see and also if we want to represent a number as binary。

 we'll use the prefix 0 B and so this is a common way to represent the subscripts that we would use to indicate the base and is something you'll commonly see in computer programming。



![](img/72e080482c899750a7ac9630638702f0_4.png)