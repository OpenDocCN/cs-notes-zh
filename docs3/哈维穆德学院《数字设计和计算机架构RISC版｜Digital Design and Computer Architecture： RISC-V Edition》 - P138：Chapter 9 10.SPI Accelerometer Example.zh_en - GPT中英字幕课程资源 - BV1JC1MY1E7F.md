# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P138：Chapter 9 10.SPI Accelerometer Example.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video we'll take a walk through an example of hooking an accelerometer to a microcontroller over SPI。



![](img/3155c1647656d69e5fb4fc0c14002de8_1.png)

So we'll be using the LIS 3DH， which is a 3 axis's accelerometer。It measures acceleration in the x。

 Y， and z axes。And it's configured with full scale of up to two to8 Gs。

It sends the data over 16 B interface over SPI。For each axis。

With a sensitivity of as little as one millie。The chip comes in the 16 pin land grid array package。

hi is pretty sturdy， it needs to be if you're bouncing the thing around at8Gs。

But they're very difficult to solder yourself because the paths are underneath the ship。

So conveniently add of fruit and spark fun， make these boards。That include the chip。

The supporting capacitors and resistors。And then。Some pins。For hooking this thing up to。Everybody。

So this way we can easily get the fancy accelerometer on tote rightboard。So internally。

Accelerometer is a pretty nifty device。 It's got some microelectromechanical or mems cantils。

 These are beams of silicon that are actually etched out over a void in a tiny smaller than a square millimeter piece of chip。

And there's some capacitance， there's a conductor on the beam and another conductor underneath and the pit under the beam。

And as you apply force to a beam， as you apply。In acceleration， the beam moves。

 It gets closer or further from the other plate， which changes its capacitance。

And then there's a very precise analog to digital converter that senses that capacitance。

Reads out the acceleration。There's a some thermal expansion that takes place。

As temperature changes and so this device actually contains a temperature sensor as well to compensate for a temperature。

So it's a lot of technology packed away into a little chip， but from our point of view。

 it's just a box with an SPI interface and we can send commands to configure its mode and then send more commands to read the acceleration in each axis。

And you see here it's got both an SPI interface and an I squared C interface will be focused on the SPI。

So here's how you could hook up the LIS3DH to a red5 board。First of all。

 we always connect ground together， so we have common reference。The accelerometer needs power supply。

So we take the 3。3 volt output of the red5 board， hook it up to the VCC pinned of the accelerometer。

Be sure it's not5 volts， 5 volts can cook this accelmeter。

Then we need four more pins for the SPI interface。There's a serial clock going from the red five master to the accelerometer slave。

 there's master out to S in， going to the accelerometer。

 and then the accelerometer sends back master in slave out。

From the point of view of the accelerometer， Mosie is known as SDI。

And Mia is known as STO for a slaveve data out。And finally， we have a chip select， let's use pin2。

And that chip select needs to be low to indicate that we're sending a message to the accelator。

So the accelerometer itself actually has a set of internal registers。

And the microcontroller can communicate with the S by reading and writing those registers。

So each register on the accelerometer has a six bit address and contains eight bits of data。

And to access it， we use a 16 bit SPI transaction。So， the。First bit is a read write bar。

 it's a one to indicate read a zero for the right bar。So one means read zero means right。

Then there's a multiple or single bar to say whether we want to be accessing multiple registers or a single register。

Let's keep that at zero to access a single register at a time。And then to send a message。

 we need to make the chip select go low。Orre all 16 clock cycles。And we do two8 bit SPI transactions。

And the first eight bits。We send the readwrite bar。And the。Single mode and the six bit address。

Of which register we want to access。And the second eight clock cycles if。We are doing a right。

We send。The eight bits of data to write。If we're doing a read， we get back。

The eight bits from the excel。So breaking that down a little further for right。Again。

 we do two eight bit transactions。First。We send。Right bar。zero because we want to write。

Single mode is zero， then we write the six bit address of which register we want to talk to。

And then we write the eight bit data that we want to be putting into that register。We get back8 bits。

 but they're meaningless， so we just discard those。To do an SPI read。

 now the first bit is one for read。Next bit again is zero because we're accessing a single register。

We send eight bits of which register we want to access， sorry six bits of which registered。

And then eight more dummy bits， that could be all zero。just to fill space。

 but what we're interested in is the eight bits we get back that are the contents of that register we just requested。

So let's take a look at what registers are on the SPI。First register is called Who am I。

 and this is a great one to start with to know if your SPI interface is working。So who am I？

Is register0F。So the address is 0，0，1111， it's 0 f。And。When we read from it。

 we should get the pattern back 0，011，0011， or hexadeademal 33。Or decimal 51。And if we get that back。

 we know our SPI interface is working， we're receiving data from。The accelerator。

Once we know that the thing is working， we can write to the control registers。To configure the SP。

And then we can read。The output registers to measure the acceleration in X， Y， and z。Now。

The accelerometer is fairly high precision it's。0，0，1 G resolution out of a full scale of 8 Gs。

 So we need 16 Bs to represent acceleration on each axis。

 So each axis has a high and a low H and L register that collectively contain the。

Accceation of that axis。So here's the who am I register？This is showing the S clock see。

16 data pulses here。And， 16 clock pulses。And then coming back from the slave。First， it's all ones。

But then we get。zeros and we get two ones， two zeros and two ones again， so that's 0011，0011。

 which is hexademal 33， that's the who am I register returns。



![](img/3155c1647656d69e5fb4fc0c14002de8_3.png)

Msy。嗯。

![](img/3155c1647656d69e5fb4fc0c14002de8_5.png)

For who am I， we needed to send。To 0。For our。Sorry。Ne to send a one。To her read。0 for single mode。

 And then the who am I register is address 0 F。 So that's 0，0，1，1，11。

So this is what we send on the first eight bits of Mosi and the next eight bits of Mosey or junk。

 they're all zeros or anything we wanted to send。Now let's take a look at some of the control registers。

Control Reg 1 is at address 20。And that's used to turn on。啲暗。Axes and set the sampling。Al right。So。

We need to enable the X， Y and Zaxes if we want to measure acceleration all three dimensions。

 so these are all ones。We can leave low power mode in zero。And then we can set the output data rate。

IfWe set it to 0111。That's this row。Which allows us to sample at up to 400 hertz。

So that's a nice fast sampling of the acceleration in each axis。

We also need to set up control Register number four。And we can write into a 8 hex 88， which is 1，0，0。

0，1，0，0，0。So。This zero here。Is for SPI。The next two zeros are for self test mode。

 00 to disable the self test。And then the one in high resolution。

Means high resolution modes on we're getting a 16 bit value instead of 8 bit value。Full scale of0，0。

Means we're on a full scale of  two Gs for maximum acceleration。BL E， bigger little Indian。

 So0 is we're going to。Have the least significant bit of the data at the lower address。

And then block data update with one。That means each time we read out。

The high and low bys of an acceleration。Next conversion will take place and update the out。

Other registers。All right， so let's make this concrete。And see how we really use this。

We've got two output registers for each axis。And we need to read the eight bits from each and combine them into a 16 bit2s complement number。

And then the acceleration will be the value we read as a 16 B2 complement number minus some offset because0 acceleration doesn't give exactly 0 on the sensor times some scale。

Ideally， so that full scale makes the full two Gs that we said。

But not all these devices are exactly identical， so if we want precision。

 we should calibrate the offset and scale。And we do that by reading the accelerometer when it's level。

 and then when it's rotated by plus and minus 90 degrees new axis。

 and that will tell us what the offset is when we're level。

And what scale we need to go to full G1G un in given access？

So let's look at some code to do that will include our standard Integer library and our E red5 IO with the SPI calls we just talked about。

And here's some code to read and write the accel route。So to do a right。

We take an 8 bit number specifying the address。 Only 6 bits of that are meaningful。

 and then an 8 bit value that we want to write to that。Register on the SPI。

We'll declare two8 bit values that come back from SPI because SPI always returns something even if it's junk。

On our system。We need to remember， we need to pulse。The。Chhiip select for the entire 16 bits。

And the built in chip Select control on our SPPI port of this chip won't do that for us automatically。

 so we're going to take control of the chip selector。We're going to。

And another future page will set a pin two， instead of being controlled by the SPI。

 we'll make it a GPIO output。And we'll write it to zero to begin the transaction。

 so that's going to select the accelerometer。Then we'll send the first8 bits containing the address。

And the next eight bits containing the value。And the top two bits of that address include that RW flag and the multi single bar。

Fck。So if we write our value to the desired address， and then we turn off the chip select。

And we can discard the high and low that came back because the right doesn't take anything back that we care about。

For a read from the accelerometer， we take。An8 bit number containing the address and the rer。所系。We啊。

also have two A registers again for the。Two things coming back。We post the chip select low。Then。

 we're going to send。诶啊。Address。Horard with a one and the most significant bit。

So the address has six interesting bits， and we put a one in the most significant bit to set read write bar true to indicate that this is a read instead of a write。

Now we send another 8 Bs of dummy information because we just needed 8 clock pulses to get the values back。

 the things that come back。On that second eight f cycles we'll put in a variable called low。

Now we'll release the chip select and we'll return this eight bits and low to the value we read from the register on the accelerometer。

So here we can put it all together。Let's have an eight bit registered。

To see what comes back from who am I？And2，16 bit numbers for X and Y acceleration。

So we'll call that SI in function。This is actually the SI net of 15 comma0， comma 0。

Because we wanted to set the bo rate to 500 kilohertz。Phase and polar to normal。

We will prepare pin2 to be an output first we'll set it to one so that we don't get any undesired pulse on the chip and able。

And then we will use pin mode to set pin to an output so that we can control it。

From SI write and SI read。Now let's do an SPI read of register0 F。Which is the who am I register？

And we'll put that answer in debug。 You could look at that value in the debugger。

 and you should see comeback Hex 33， which in the debugger will show up as decimal 51。Next。

 we wanted to write to the two control registers。Register 20。

 we wanted to write 77 at that set the 400 Hertz conversion and turned on all axes x y and z。

And then to register 23， that was the other control register we wanted to send eight。

Whi put us in high resolution mode with a block update， like we talked about a little。

Now let's do some reads。From the accelerometer， so we'll have a loop to just continuously read。First。

 to read the X axis。The x。Low register was 28 and the high register was 29。

 so we'll read both of those， we'll shift。The X high。Into the upper eight bits。

And put x low in the bottom 8 bits。 And this way， we get a 16 bit。

Number representing the acceleration in the x axis。We'll do the same thing for the Y axis。

 we could do the Z axis as well， but let's say we don't care about it。And then we have a small delay。

嗯。You could delay for 100 milliseconds， you could delay for a lot less than that because we're in the fast mode。

 we could go up to400 hertz。But here we're just sampling at 10 hertz every 100 milliseconds。



![](img/3155c1647656d69e5fb4fc0c14002de8_7.png)

Now in lab8， you're going to be building a digital level。

And you'll start with the accelerometer code from the previous page provided to you。

And your goal will be to take those two numbers of acceleration。Clibrate your accelerometer。

 so you know what zero。Gs is what sitting flat on the table is。

 and what you get when you tilt the accelerometer and x or Y axis。And then就。Pook up。And 8 by 8。

LED matrix。That has 64 Ls。To keep things simpler， we're only going to use seven by seven of them。

So that we could have a dot that's centered when your board is flat。And as you tilt it。

 let's say you tilt this side。The dot will move over to the side。Same way if you tilt this side。

 dot will go that way if you'll tilt it up。は佢教我。So that will tell us whether our boards level into aes。

And by using seven by seven， there's a center point。

This means we're going to need 14 wires to hook up these LEDs。

 and you're going to need to figure out how to do that。

 And this is an example of a parallel interface， because from the。Med5 board。It will have 14 GPIOs。

Going to the LED array。And you'll need resistors on some of these to make sure that you don't have too much current flowing through an LED and burn it out。

So that concludes our example of using the SPI accelerometer。

