# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P37：37_02_07_演示：Rust中的break与continue语句.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/deef64b6a41ced892eb7f7cb86cc6247_0.png)

Let's see two keywords in rust that allows us to have a little bit more control in loops。

 This is not specific to for loops it will also apply to while loops and the other looping techniques that we've seen so far so in particular we want to take a look at continue and take a look at break so if you're coming from a language like Python or a little bit of Python you'll know that continue it's kind of like skipping and going to the next iteration so let's focus a little bit on what's going on here and let's go Lambal line so line number two we're going to do for 10 times starting at the number one and then ending at number 10 inclusive we are going to be looping so for every number we're going to get here to line number3 and if it's module。

2 that means it can be divided by 2 with a0 remainder。

Then it means that we' going we're not interested we're only so this is a very common construct if you want to find even numbers so if you're not interested in even numbers then you catch that condition and then you say you know what I am going to continue I'm going to skip I am going to move over to the next iteration so in this case if this was a two it will go to the next one which will be a number three。

Alright， so if this condition doesn't match so like that condition actually doesn't match and like continues not going to get executed。

 it's going to go right here to this next block so it's going to print the number now if it's  seven and let's just say for example you're looking for actually 4 a7 then it will break it will break right here and break what does break mean well it will it will get it will finalize it doesn't matter if this is like you know7 million it will get to seven and this loop will stop executing so ideally if we're running this whole piece of block。

 this whole for loop will only see like two things we will only see odd odd numbers like 35 and 7 and1 and it will stop at at7 and we will never see nine。

To to be displayed。 So actually go ahead and run it and you can see here1，3，5 and 7。

 those are all displayed。 so thats that's pretty straightforward we could you know we could change。

 of course， these around let's if we say you know by1100 here you should probably expect the same behavior I run it again。

 it will stay at 7。 so those those control keywords for loops will allow you to have a better better control on your loop and set certain conditions to try to manipulate the behavior。

 the flow of the loop either for a regular for loop or a while loop or any of the other looping constructs that we've already seen。



![](img/deef64b6a41ced892eb7f7cb86cc6247_2.png)