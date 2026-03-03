# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P69：Chapter 5 16.Memory Arrays in SystemVerilog.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/2032a5f3555d0a238de4eaadfad06c1c_0.png)

So let's show the system barrel for our memory arrays。 So this is a 256 by 3 bit Ram。

 So the word size is 3， and we have our our address size is 8。We have two to the eight。

Kind of that's the depth。Two to the eight words or 256 words。And so we have our inputs。Crk。嗯。

Write enable A。 And we also have right data。 So this is a single ported memory。

 but its port is can be read or written。And so our read is performed。

 We read this array combinationally。 So we have this RA array。That depth is 0 to 255 or 256 words。

 and its width is3 bits。So here's the width。This is the depth。And we read。

 so our read data RD is going to be equal to whatever value is stored at address A in that RAM array。

And we're going to write well， we want to only write at the clock edge because we want to make sure the data that we're writing that right data WD is stable so and we want to not only make sure that's stable。

 but make sure we actually want to write the array so we're going to have this right enable a Poage clock if write enable then。

Ram at address， a。Gets written with。The right data with this three but right data input。WD。

Now here' is a system B RAM array， it's 128 by 32 bits， so its width is 32 bits。

 that's the word size and it has seven bits of address。So 128 is the depth or2 to the seven。

And you'll notice that this only has a single input and a single output。

 so it has the address input and read data RD as the output。

And so this roM is initialized with the contents of a file， in this case， my file that dad。And。

Is initialized from that file。And then whenever we get an address， it just combinationally feeds out。

Whatever whatever data is at that。Address in the wrong array。And so we can look。

And here are the contents of that data file file。 and it can contain up to 128 lines of 32 bit hex numbers。

Address is 0， would have that value，0，1，2，3，4，5，6，7。 This is address。One， this is address 2。

 this is address 3。And so forth。We can also have memories with multiple ports。

 So a port is an address data pair。 This example below， we have a。

3 ported memory has two read and one write port。 The array， the array is still a same。

 there's still a single array memory array。 In this case， we have our address size is n bits。

 So this is a two to the n。By that's the depth。 and the the data size is M bits。

 either the right data or the read data。 So we have a2 to the n by M bit array。

It's still a single array， memory array， but we can read two addresses at a time and write to a third address all at the same time。

 so here's our two read ports address one， read data  one address two read datata 2。

 there's the two read ports and then we also have a write port。Addres 3， right data 3。

 and then we also have this right enable3。And so this。

This small memory will be written when right enable3 is one。And we get a clock edge， write， whatever。

Address is indicated by address 3， and it will write the data value on WD3。

And we'll use these multiported memories to implement register files in chapter seven。

For storing a bunch of values。And then accessing them through both reading and writing。

Here's the system very log representation of the memory array that small multipoed memory array that we just showed。

 this is a 32 by 32 that register file， so the depth is 32 and the word size。Is the width is 32。

 So we're going to need a five bit address。To access this memory array。

And this has two read port and one write port。The read reports are RA1， RA2 or the addresses。

 five bit addresses， and the data corresponding data that's read from those two read reports is1 R2。

And then we have our signals for our。Write port， right address3， right data three。

 and right enable three。And here's our single array of memory that stores that。

 you know all of the memory。And always at positive edge clock， if right Na3 is true。

 then we write whatever is in right data 32。The memory array at right address 3。And then our。

Read is done combinationally。So ignore this part first。

Right R D1 is equal to the whatever stored in the register file at right read address A and R D2。

The read data to is whatever is stored at right address too。

And so we have a special thing in this register file in that， as we'll see in chapter6 and7 that。😊。

Register 0 happens to always hold the value0。 So if the right， the read address is0。

 then it returns 0。And。Otherwise， it returns。The value stored in the register file。

At the given address。For both RD1 and RD2。

![](img/2032a5f3555d0a238de4eaadfad06c1c_2.png)