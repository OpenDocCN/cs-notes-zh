# 【从零开始学习 ARM 汇编语言II Udemy】 p31 p30 07.5. Coding  Calling ADC Subroutines from C code -BV1RJU6YwEM8_p31-

Hello， welcome back。In this lesson， were going to see how to call our。

ADC subroutines from a C program。 We're going to create a new project or come over here。

 New U visionion project。I'll create a new folder for this。Coon AC。😔，From C。

Thenll call the project simply ADC like this。😔。

![](img/98ca0ce0deea0dd0618a6ad2cfc9e1a5_1.png)

And my board is ETem 32。😔，F 4，1，1， V， E T。

![](img/98ca0ce0deea0dd0618a6ad2cfc9e1a5_3.png)

And then okay。And the CMm says， I'm going to select the core and a device or select the startup。😔。



![](img/98ca0ce0deea0dd0618a6ad2cfc9e1a5_5.png)

Target is my STM 32 board。Soce group。是APP。So I'm going to add two files here。

 I'll come to add new item。Dot S over here。I'll select ADC to create an ADC。 S file outside type ADC。

 sorry。

![](img/98ca0ce0deea0dd0618a6ad2cfc9e1a5_7.png)

And then I'll create another file known as main dot。😔，Main dot C file。

 o like dot C over here and then give it the name， main。Like this。

I'm going to open our previous ADC project and copy the driver from there。

 this is our ADC project that we created in the last lesson， I'm going to open that。

It's open over here。

![](img/98ca0ce0deea0dd0618a6ad2cfc9e1a5_9.png)

And I'm going to copy everything in that project， we kept everything in a file known as made of S file。

 I'm going to do control a。For all and then Ct C to copy， and then once that is done。

 I'm going to close this， then I'm going to paste this into the ADC dot S file。😔。

In know a new project and in this project。We don't。 We're not running over here。So I can。

I can sort of delete。I can delete this bit the part for testing。 We don't need this。

We don't need even this。We have to simply export our ADDC subroutins。

 So I'm going to copy this and paste it over here。And then I'm going to export ADDC in it as well。😔。

Export。It is one in it。Then。I'm going to delete entry， this is no longer the entry。

And then I'm going to export LED control。AndThen I'm going to export it is one read。Right。Okay。

 so thiss our ADC dots S file。 So I'm going to import these functions in our。In our main fall。

 so come over here。Let's see， I'm going to copy them， I'm simply going to copy them。😔，I'll put them。

 page them over here。😔，I'm going to use them as files。 I'm going to use them as notes。

 I've commented them out because I just want to remember the name of the functions。

 So because the exist and external file， I'm going to use the external keyword。I'll see extend。

This function returns nothing。😔，And then it takes no argument。

And then the next function is the ADC in it。I'll see X 10。😔，It's going return。It takes no argument。😔。

The next one is the ADC read。Extend。This one is going to return U int 32 bit data type。😔。

And it takes no argument。And then the function after this is the LED control。It'sSo external。

It takes no argument just the name of the function。😔。

And then the reason we have this is we've got to include SDD in H。 So come over here。Include。

S TD and dot H。And then I can clean our comment from here。😔，Right。Okay。So here are our functions。

 and I'm going to include the header file for our microcontroller by doing right click and then include file。

 I'm going to select SDM 32 f4 x X dot H。O。Interesting， maybe we don't even need our head of our。

 Let's see。It should be able to work without the header file， so inter main our main function。

Open close。😔，We're going to start off by initializing our GIO。And then initialize our ADC。And then。

I'm going to。I'm going to create a global variable here to hold a sense of value。

Call the central value。And I'm going to open my infinite loop here。Pall1。And in here。

 I'm going to say sense of value。Equs。It is you won't read。And then。

I'm going to blink LED after that。I'm gonna to call LED control here。Right。Okay。

 I'm going to delete this。Letlesss see what we have。I'llClick here to build。

It's builted successfully。Click here to download onto my po。I've got to set my target options， debug。

😔，S the link debugger， click over here settings， flash download， reset and run， O， and then O。

Download onto the board， it's downloaded successfully。

And I'm gonna go to my debug view to monitor this variable here。 Since of value， click OK over here。

I'm going to double click on sensor of value， right click。Add to watch window。

 I' going to pull this out。😔，We shape it a bit。And I'm going to right click and then disable extra there more display。

 and then I'll click here。And this is my sense of value。 I'm turning the potential meter。

As you can see， I've tendend to the leftmost。Of1 it to the leftmost end。

 And this is the maximum value。 And you can see the LEDs on as well。

 I'm going turn it to the opposite direction。 The LED has gone off。

 and you can see the sensor reading is this。 right？ Yeah。

 I'll include a video of the potential meter。Of meter and a potential meter。

 but it's the same as the video we saw。In the previous lesson of my hand 10 in the potential meter and the LED on。

 So anyway， I use the potential meter in this experiment you can use any sensor you have if you have a light sensor or a temperature sensor is exactly the same way。

 So this all there is what is lesson if you have any questions at all just let me know and I'll see you in the next lesson have nice。



![](img/98ca0ce0deea0dd0618a6ad2cfc9e1a5_11.png)