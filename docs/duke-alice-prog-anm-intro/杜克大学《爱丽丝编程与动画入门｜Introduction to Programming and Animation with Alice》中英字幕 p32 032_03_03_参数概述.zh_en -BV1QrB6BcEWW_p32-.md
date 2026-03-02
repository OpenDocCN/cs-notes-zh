# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p32 032_03_03_参数概述.zh_en -BV1QrB6BcEWW_p32-

![](img/5df1edb389cbb8cd5a9e77b73e3bb4e8_0.png)

In this lesson， you will see how instructions can be limited and what you can do to make them more flexible。

 Let's think about that rectangular hop instruction。

We're going to be working with rectangular hop as it's the easiest of the three hop instructions。

The rectangular hop instruction always has the bunny hop upwards one unit and also the bunny hop forwards one unit。

 While this is a fine instruction， it may not be what we want。

Imagine that the bunny needs to hop over an obstacle。 Remember， it always hops one unit upwards。

If the object was half a unit tall， the bunny would waste lots of energy hopping one unit up when it only needed to hop half a unit up to clear the obstacle。

Alternatively， what if the obstacle was two units tall？Actually。

 this is one of the ways animation is different from the real world。In the real world。

 a bunny trying to hop one unit high to get over an obstacle that was two units tall would lead to a loud crash。

In Alice， the bunny would go through the obstacle。 that would look strange indeed。

One solution to this problem is to have three rectangular hop instructions。

One rectangular hop instruction has the money hop， half a unit up in the air。

The second would have the bunny hop one unit up， and the third could have the bunny hop two units up。

While this is a solution， It's rather clumsy， we have to write three separate instructions with lots of duplication。

There's got to be a better way。What we would like to have is a single rectangular hop instruction where we can pass information to the instruction for how high we would like the bunny to hop。

 And then the rectangular hop instruction would have the bunny hop， the correct height。😊。

This makes sense。 And Alice already allows this customization for the primitive instructions。

When we ask the bunny to move， we tell the move instruction two important pieces of information。

 The direction we want the bunny to move and how far it should move。Likewise。

 for the turn instruction， we specify the rotation direction， left， right， forward or backwards。

The bununny should turn， along with how many revolutions it should turn。

So Alice should allow us to add this flexibility to any of the instructions we create。And Alice does。

 We can customize any instruction we write。We can make our instructions more flexible by adding parameters to an instruction and then using arguments in place of the parameters。

In an instruction， a parameter is defined as a placeholder for the input you want to use with the instruction。

The parameter must have a name so that it can be used in the instruction。

The parameter must also have a type such as number or object。

 This is the type of information to be passed to the instruction。

An argument is the value you pass to the parameter。

The parameter will use this value throughout the instruction。

You can pass in a different value as the argument each time you call the instruction。

Let's look at an example。 Consider the instruction rectangular hop here， the bunny moves up。

 then it moves forward。 Finally， it moves back down。

Its height up in the hop is always exactly one unit。Now。

 let's add a parameter so the bunny can hop different heights。

We will click on the Add parameter button at the top of the instruction。

We need to give the parameter a name。 We have named our parameter How high。

 since it represents how high the bunny will hop。We also have to describe what type of value we can pass in。

How high the bunny can hop should be a number， So we will define it as a decimal number。

 There is other information here， which we will explain in a minute。After adding the parameter。

 its type and name appears on the same line as the name of the instruction。

We have added the parameter how high， but we have not used it yet。Currently。

 the bunny always moves up one and moves down one。We need to change the amount to move up to be our parameter。

 how high and also change the amount to move down to also be our parameter， how high。

We replace both ones with the parameter。 How high。 Now we can pass in any value for how high and the bunny should move up that value and then move down the same value。

Let's see how adding parameters has affected the calls to rectangular hop。

The top picture shows how we called rectangular hop before we added the parameter。

Every time we called it， the bunny hopped exactly one unit high。

The bottom picture shows that we added a parameter to rectangular hop， But in my first method。

 it does not know the value of the argument we want to send。

 That is how high we want the bunny to hop each time。

Because these calls to rectangular hop existed when we added the parameter how high。

 Alice shows the location of the arguments as red。To remind you that you need to add values here。

I selected the bunny to hop 0。5， to hop over the cat， which was just about 0。5 in height and 2。

0 to hop over the hairre who's just under two units in height。

We can now watch the bunny jump over the cat and then over the ha。

 Both of the jumps are just high enough to jump over the animal。

Using parameters will allow you to write flexible instructions and also fewer instructions here。

 we just need one rectangular hop instruction instead of two top over two animals of different heights。

Have fun making bununnies hop。

![](img/5df1edb389cbb8cd5a9e77b73e3bb4e8_2.png)