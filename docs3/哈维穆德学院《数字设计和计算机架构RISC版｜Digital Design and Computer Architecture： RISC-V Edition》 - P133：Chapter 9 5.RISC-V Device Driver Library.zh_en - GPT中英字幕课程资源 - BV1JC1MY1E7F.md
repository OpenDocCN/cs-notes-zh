# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P133：Chapter 9 5.RISC-V Device Driver Library.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video， we'll be talking about Jeff I drivers。

 and in particular we will write an easy red5 IO device driver library that will give an easy control of the GPIO pins on our red 5 T plusboard。



![](img/41ae8c2c862ad5bf5ed8096fecbadd59_1.png)

So so far we've been controlling memory map Di with pointers。

And that's clear in that we know exactly what memory locations we're manipulating。

But it's error prone when you get to a larger system。Couple drawbacks。

 The first one is it's hard to see the big picture。

 If you're just writing to specific locations in memory。

 you've got to be consulting another table to say what those locations do。

And so if you're not intimately familiar with the memory map dial， that would be confusing。Secondly。

 it's easy to mistype the addresses of all those pointers in the GPIO if you have a single character wrong out of those8 x decimal digits。

 you'll be writing some random location and memory and nothing at all will happen。And third。

 many beginning C programmers don't really understand pointer access all that well。

 and so if you could write some functions that manipulate the IO with a clearly defined name of a function rather than an obscure pointer right then it makes your。

I O easier for a casual user。So we're going to write a device driver that hides the details and lets us access the GPIOs more abstractly。

This live device driver will call easy red 5IO when we create a header file that defines all these functions。

It will give an Arrduino style interface to access things。

 and we'll start with writing the GPIO part。So as we do this。

 we're going to use structures instead of simple pointers to define our memory map di。

 you may recall that as structure， we can point to the location of the structure in memory and then access subsequent elements in memory as elements of the structure。

This means we don't have to type all the addresses in the way we would if we were using pointers and it gives us cleaner C code that's easier to read。

So here is the definition of the GPIO in our E red 5 IO library。Let's define。

Input to be mode 0 and output to be mode 1 for when we get to pin modes。

And now let's declare a structure。For the G O registers。

This structure contains a bunch of 32 B unsigned integers。 These are the registers of the GIO。

And remember an offset of zero is where the input value， offset of four input enable， offset of8。

 output enable and offset of C for the output value。

 so those are the first four registers within that part of the memory map title。Next。

 we'll define the base address of the GPIO to be 1，0，0，1，2，0，0，0。

Remember that's where the GPIO began in the memory map。

 the U at the end of this number indicates that it's an unsigned hexadecimal number。

And we'll call this GPIO0 base ourship only implements up to 32 GPIOs。

 so it only needs one GPIO memory。High area， but subsequent versions of chip might implement more。

Finally。We'll declare GPIO0 to be a pointer to a GPIO structure at that base address。

So now we have a pointer to a structure where the elements of that structure correspond to。

Memory locations where hardware happens。Now let's look at using that structure to access the GPIOs so we can write a nice friendly function。

 digital read it takes the pin number that we want to read from， and it returns a0 or a 1。

 that's the value on that pin。And it does it by going to our handy dandy GPIO0 structure。

Which is really a pointer to the beginning of that。Memory mapped GIO。And will read the input value。

Field of that structure。That gets us。From 10，0，1，2000。Reads this all 32 bits of the input。

 Then remember， we write shift。To get the desired GP pinned into the bottom position and end it with one to discard the other pins。

 And now we're left with either a0 or one corresponding to the value of that pin。

Digital right is similar。We'll take the pin number that we want to write and the value。

If the value is1， if we want to write a1， then we'll or a1 into the appropriate column of the GPIO output value register。

Otherwise will end with ones in every column， except the one of interest is0 in the column of interest。

To turn off that pin。Finally。Let's talk about a pin mode function。

So we'll give it the pin number and the function， either input or output。So if the function is 0。

Input。Then we want to turn on that pin as an input by oring a one into that column for the input enabled。

And we'll turn off the output and and IO function enable so that it's an input。

 not an output or a special function。Similarly， if we wanted to make that pin and output。

We would order one into that column of the output enable register。

And turn off the input and IO function registers。All right。

 let's apply all of this library to write a easier to read program that now can look at three switches and turn on three LEDs as a consequence。

So we'll pound include this easy red 50o。h file being in quotes instead of brackets indicates to look for the file in our project folder instead of an assistant folder。

Now our main program。

![](img/41ae8c2c862ad5bf5ed8096fecbadd59_3.png)

嗯。So let's say the switches are hooked up to GPIO2 through4。

Which on a red5 red board would be D 18 through D20。So we'll make those three pins be inputs。

Let's say the LEDs are hooked up to GPI08 through 10， so we'll make those three pins be outputs。

And then we can keep repeating forever。We will read。The value from GP out2， which is this switch。

And we'll write it to Gpeo 8， which turns on that LED。Do the same for。Second pair and the third pair。

And there we have our program。